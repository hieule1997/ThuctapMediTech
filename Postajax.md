## Lưu ý trong lúc post ajax
Tác dụng của việc sử dụng ajax là khi ta muốn load 1 phần dữ liệu nào đó mà không cần phải load lại trang 

Ảnh sử dụng ajax khi sử lý post form  
![anhajax](https://github.com/hieule1997/ThuctapMediTech/blob/master/anh/ajax.png)

`
type:'POST',
`

Phương thức method bao gồm GET ,POST :     
  Phương thức GET có tác dụng lấy dữ liệu từ database xuống client để sử lý  
  Phương thức POST có tác dụng đẩy dữ liệu lên server để sử lý mà không bị  reload lại trang    
`
url: the file location
`

url : chỉ ra địa chỉ file cần nhận dữ liệu POST lên   

`
data: {'csrfmiddlewaretoken':token,'id':id,'title':title, 'body':body},
`

data : được lưu theo dạnh key: value  : 
      trong đó key là tên dữ liệu lúc POST  
               value là dữ liệu POST  
  
dataType : đưa ra kiểu định dạnh dữ liệu theo json hay XML

```
success: function(){
                	$('#myModal').modal('hide');  
                	// document.getElementById("change_user_close").click();  
                     $(".ida").load(location.href + " .ida");  
                    }});  
                });
```

Khi thực hiện POST ajax thành công thì các câu lệnh bên trong function sẽ được thực hiện 


Khi thực hiện POST ajax thành công thì việc sử lý dữ liệu ở phía backend



XỬ lý phía backend

![anh](https://github.com/hieule1997/ThuctapMediTech/blob/master/anh/editpost.png) 


`if request.method == 'POST':`
 
 Kiểm tra phương thức yêu cầu là gì POST hay GET từ đó có thể sử lý bên trong 
 
 `u = Post.objects.get(id=request.POST['id'])`
 
 Tạo một đối tượng u là một Post chứa toàn bộ dữ liệu được lấy ra theo id
 ```
 title = request.POST['title']
		body = request.POST['body']
 ```  
    
    
 Tạo 2 biến là title và body 
  2 biến này dùng để lưu dữ liệu được đẩy từ phương thức POST của ajax 
  
  
  ```u.title = title
		u.body = body
  ```
  
thay đổi dữ liệu của đối tượng vừa lấy được theo id 

`u.save()`

Lưu dữ liệu của đối tượng u 


## Cách truy vấn dữ liệu theo django 
Lấy tất cả đối tượng

```Entry.objects.all()```

Lấy các đối tượng cụ thể bằng các bộ lọc

`filter(**kwargs)` : trả về đối tượng theo điều kiện được đặt trong fillter

`**kwargs` là điều điện được đặt trong fillter

`exclude(**kwargs)`
Trả về một đối tượng chứa mới không khớp với điều kiện được đặt trong exclude 


Lấy một đối tượng duy nhất 
`Entry.objects.get(pk=1)` 
Lấy ra đối tượng có pk = 1

`Entry.objects.all()[:5]`

Lấy ra 5 đối tượng đầu tiên

`Entry.objects.all()[5:10]`

Lấy ra đối tượng từ 5 đến đối tượng thứ 10

`Entry.objects.order_by('headline')`

Sắp xếp các đối tượng theo điều kiện



