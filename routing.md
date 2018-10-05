## ROUTING   
Trong routing ta cần improt các thư viện hỗ trợ ProtocolRouter ,Url Router 


```
from channels.routing import ProtocolTypeRouter, URLRouter        from channels.auth import AuthMiddlewareStack
```

Tạo một ProtocolType có tên là application bên trong ta định nghĩa một websocket là AuthMiddlewareStack nó được hiểu như là một bên thứ 3 để xác thực các router đã được định nghĩa bên trong nó 

example   
```
application = ProtocolTypeRouter({

    # WebSocket chat handler
    "websocket": AuthMiddlewareStack(
        URLRouter([
            url(r"^chat/admin/$", AdminChatConsumer),
            url(r"^chat/$", PublicChatConsumer),
        ])
    ),

    # Using the third-party project frequensgi, which provides an APRS protocol
    "aprs": APRSNewsConsumer,

})
```
Ở đây ta hiểu là websoket đã được định nghĩa có thể sử dụng các router 
```
            url(r"^chat/admin/$", AdminChatConsumer),
            url(r"^chat/$", PublicChatConsumer),
```
để giúp cho việc thực thi gửi các socket

### URLRouter  
`channels.routing.URLRouter`    
#### lưu ý
example  
```
URLRouter([
    url(r"^longpoll/$", LongPollConsumer),
    url(r"^notifications/(?P<stream>\w+)/$", LongPollConsumer),
    url(r"", AsgiHandler),
])
```
URLRouter thường sử dụng url() và sẽ hoạt động không đúng với  path()

### ChannelNameRouter   
`channels.routing.ChannelNameRouter`

example 
```
ChannelNameRouter({
    "thumbnails-generate": some_app,
    "thunbnails-delete": some_other_app,
})
```

### Consumers 
 Là thư viện bất đồng bộ  
 `channels.consumer.AsyncConsumer`  
 Là thư viện đồng bộ  
 `channels.consumer.SyncConsumer` 


 #### ví dụ về đồng bộ 
```
from channels.consumer import SyncConsumer

class EchoConsumer(SyncConsumer):

    def websocket_connect(self, event):
        self.send({
            "type": "websocket.accept",
        })

    def websocket_receive(self, event):
        self.send({
            "type": "websocket.send",
            "text": event["text"],
        })
```

ở đây ta thấy   
Hàm `websocket_connect` đề gửi đi một loại là đồng ý nhận tất cả các socket   
Hàm `websocket_revcevie` có tác dụng gửi đi tin nhắn text 


#### ví dụ bất đồng bộ 

```
from channels.consumer import AsyncConsumer

class EchoConsumer(AsyncConsumer):

    async def websocket_connect(self, event):
        await self.send({
            "type": "websocket.accept",
        })

    async def websocket_receive(self, event):
        await self.send({
            "type": "websocket.send",
            "text": event["text"],
        })
```
Ghi chú : Tất cả các hàm sử lý đều là coroutine và hàm seft.send là một coroutine

Khi nào nên dùng AsyncConsumer và SyncConsumer:

- Không nên sử dụng bất đồng bộ khi duyệt một trang web có nhiều dữ liệu khi đó nó sẽ là cho việc sử lý trở nên chậm thay vào đó hãy sử dụng hàm đồng bộ để cho việc xử lý trở nên nhanh hơn 

- Nên viết SyncConsumers mặc định và sử dụng SyncConsumers trong khi bạn biết bạn đang làm gì để cải thiện cách sử lý không đồng bộ
- Nếu bạn muốn gọi một hàm đồng bộ từ một SyncConsumers thì nên xem xét `asgiref.sync.sync_to_async` .Đó là tiện ích mà channels sử dụng để chạy  SyncConsumers

### Closing comsumers 

Khi có một comsumers bị đóng thì bạn có thể nhận được một sự kiện gửi cho bạn là `websocket.disconnect` và ứng dụng của bạn sẽ được cấp một thời gian ngắn để hoạt động 

khi bạn kết thúc kết nối thì bạn cần nâng cấp  `channels.exceptions.StopConsumer ` để máy chủ của bạn có thể biết được dọn dẹp ứng dụng và máy chủ dọn dẹp 

khi bạn tắt ứng dụng bằng cách không nâng cấp ngoại lệ này thì máy chủ daphne sẽ tắt sau 10s và sẽ kill ứng dụng 

consumers sẽ thực hiện cho bạn điều này khi bạn đang viết đồng bộ và bất đồng bộ của riêng mình .Tuy nhiên có thể ghi đè lên phương thứ `__call__` của họ và ngăn chặn các phương thức xử lý mà nó gọi lại từ việc trả lại , bạn có thể vào mã nguồn nếu bạn muốn biết thêm thông tin 

### Channel Layers 
Họ có thể trao đổi với nhau thông qua group 

Consumer có thể sử dụng channels layers defaul thay cho thuộc tính `channel_layer_alias` Cho đến khi bất kì lớp consumers nào được cung cấp

Chúng ta sẽ sử dụng `channel_layer_alias` như sau 

```
from channels.consumer import SyncConsumer

class EchoConsumer(SyncConsumer):
    channel_layer_alias = "echo_alias"
```

ví dụ sử dụng để cấu hình cho redis 
```
CHANNEL_LAYERS = {
    "default": {
        "BACKEND": "channels_redis.core.RedisChannelLayer",
        "CONFIG": {
            "hosts": [("redis-server-name", 6379)],
        },
    },
}
```

### Scope

Nó sẽ nhận được phạm vi của người dùng có thể kết nối khi chúng được khởi tạo chứa rất nhiều thông tin.Nó có sẵn dưới dạng `self.scope()` bên trong phương thức consumers




