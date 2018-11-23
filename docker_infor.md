### Tìm hiểu tổng quan và lịch sử container
Trong linux,LXC hình thành nền tảng cho các công nghệ container sau này được thêm vào kernel vào năm 2008.LXC kết hợp sử dụng các nhóm kernel (cho phép cô lập và theo dõi tài nguyên ) và  vùng tên (có thể tách ra để chúng không thể nhìn thấy nhau ) để thực hiện quá trình cách ly   
Container sử dụng để làm gì ?  
    - ứng dụng trong container hoạt động độc lập với hệ điều hành của máy chủ  
    - Dễ dàng mở rộng   
    - Quản lý các thành phần phụ thuộc vào ứng dụng và phiên bản ứng dụng 
    - Môi trường thực thi cực kì nhẹ và được cô lập 
    - shared Layering 
    - Tính tương thích và khả năng dự đoán

### Khái niệm công nghệ container 
 Thuật ngữ 'container' ở đây được hiểu là khái niệm đóng gói . Một container chứa đầy đủ application và các thành phần như : các file bin/ và các thư viện đính kèm để đảm bảo các ứng dụng có thể chạy độc lập các container trong nó .Như vậy, các container được coi là một 'máy ảo' mini

 Ưu điểm :   
    - Điểm mạnh lớn nhất của container là hiệu năng : Là ảo hóa các container rất nhẹ 
    - Các container ở đây như nà process của hệ thống 
    - Chỉ mấy vài giây để stop ,start hay restart lại hệ thống 
    - Tính di động và tính mở rộng  
    - Chúng ta  cso thể tự tạo container bằng các teamplate có sẵn cài đặt môi trường service ,sau đó lưu lại trạng thái container như là một image 