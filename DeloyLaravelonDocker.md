# Deloy in Unbutu 
### Cài đặt docker trên ubuntu 
gỡ cài đặt bản cũ   
``` $ sudo apt-get remove docker docker-engine docker-ce docker.io ```  
Update apt
```
$ sudo apt-get update
````
Cài đặt packages 
```
$ sudo apt-get install docker-ce
```
hoặc 
```
$ sudo apt-get install docker-ce=<VERSION>
```

kiểm tra docker 
```
$ sudo docker run hello-world
```
kết quả   
![Docker_hello](anh/docker_helo.png)

  
Vậy là ta đã cài đặt thành công docker 

### Write a Dockerfile
Tạo một file là Dockerfile với câu lệnh 

```
nano Dockerfile
```
Thêm các thông tin sau vào Dockerfile 
```
FROM php:7
RUN apt-get update -y && apt-get install -y openssl zip unzip git
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN docker-php-ext-install pdo mbstring
WORKDIR /app
COPY . /app
RUN composer install

CMD php artisan serve --host=0.0.0.0 --port=8000
EXPOSE 8000
```

Dockerfile detail 

```
FROM php:7
```
Đây là phiên bản php mà bạn sử dụng 


```
RUN apt-get update -y && apt-get install -y openssl zip unzip git
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN docker-php-ext-install pdo mbstring
```
đây là câu lệnh để cài đặt openssl zip  unzip git
tiếp theo là cài đặt laravel và cài đặt các module PDO và mbstring 
```
WORKDIR /app
COPY . /app
RUN composer install    
```
đặt thư mục đến vùng chứa /app và sao chép các ứng dụng của bạn vào thư mục /app  
Cài đặt composer 

```
CMD php artisan serve --host=0.0.0.0 --port=8000
```
Sử dụng cmd để thiết lập lệnh sẽ chạy Docker Image   
Trong trường hợp này chúng tôi sử dụng cổng 8000 để chạy 

```
EXPOSE 8000
```
Hiển thị cổng 8000 để khởi chạy .Đây là cùng một cổng mà ứng dụng sẽ chạy 

### Build Dockerfile 
```
$ docker build -t my-first-image .
```

Cậu lệnh trên dùng để build một image với tham số -t là để gắn tag cho image với my-first-image là tên tag image

Các vùng chứa docker được khởi chạy chương trình
```
$ docker run -it -d -p 8000:8000 my-first-image
```
Ứng dụng được có sẵn từ trình duyệt của bạn hiện tại ```http:\\localhost:8000```

