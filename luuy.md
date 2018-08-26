### Sự khác nhau giữa lệnh bậc thấp và bậc cao
`dpkg` là một trình quản lý gói cấp thấp cho các hệ thống dựa trên Debian. Nó có thể cài đặt, loại bỏ, cung cấp thông tin về và xây dựng các gói * .deb nhưng nó không thể tự động tải xuống và cài đặt các phụ thuộc tương ứng của chúng.

`apt-get` là một trình quản lý gói cao cấp cho Debian và các dẫn xuất, và cung cấp một cách đơn giản để lấy và cài đặt các gói, bao gồm độ phân giải phụ thuộc, từ nhiều nguồn bằng cách sử dụng dòng lệnh. Không giống như dpkg, apt-get không hoạt động trực tiếp với các tệp * .deb, nhưng với tên gói thích hợp

`rpm` là hệ thống quản lý gói được sử dụng bởi các bản phân phối đồng nhất của Linux Standard Base (LSB) để xử lý các gói thấp. Cũng giống như dpkg, nó có thể truy vấn, cài đặt, xác minh, nâng cấp và loại bỏ các gói và thường được sử dụng bởi các bản phân phối dựa trên Fedora, chẳng hạn như RHEL và CentOS.

`yum` thêm chức năng cập nhật tự động và quản lý gói với quản lý phụ thuộc vào các hệ thống dựa trên RPM. Là một công cụ cấp cao, như apt-get hoặc aptitude, yum làm việc với các kho lưu trữ.

Câu lệnh tìm ra hệ điều hành

`cat etc/proc/version`

### Câu lệnh tìm ra lịch sử


`export HISTTIMEFORMAT='%F %T '` : Định dạng xuất ra kiểu dữ liệu nào

`history` : Show lịch sử command gồm command và thời gian viết lệnh

### các option với kill
Cú pháp cơ bản như sau:

`kill PID`

HOẶC LÀ

`kill -s signalName PID`

HOẶC LÀ

`kill -signalName PID`

HOẶC LÀ

`kill -signalNumber PID`

Ở đâu,

`signalNumber`: Một số nguyên thập phân không âm, chỉ định tín hiệu được gửi thay cho TERM mặc định.

`signalName`: Một tên tín hiệu tượng trưng chỉ định tín hiệu được gửi thay cho TERM mặc định.

`PID`: Chỉ định danh sách các quá trình giết sẽ báo hiệu. Mỗi PID có thể là một trong những điều sau:

`n `: Nếu PID là giá trị dương, lệnh kill sẽ gửi quá trình có ID tiến trình bằng với PID.

`0` : Tất cả các quá trình trong nhóm quá trình hiện tại đều được báo hiệu.

`-1` : Tất cả các tiến trình với pid lớn hơn 1 sẽ được báo hiệu tức là lệnh kill gửi tín hiệu đến tất cả các quá trình thuộc sở hữu của người dùng hiệu quả của người gửi.


### option với card mạng

`/etc/resolv.conf` : Liệt kê các máy chủ DNS cho độ phân giải tên miền internet.

`/etc/hosts` : Danh sách máy chủ được giải quyết cục bộ (không phải bằng DNS). 

`/etc/nsswitch.conf` : Danh sách thứ tự tìm kiếm tên máy chủ. Thường xem các tệp cục bộ, sau đó là máy chủ NIS , sau đó là máy chủ DNS . 

`Red Hat/Fedora/CentOS: /etc/sysconfig/network` : Chỉ định cấu hình mạng. ví dụ. IP tĩnh , DHCP , NIS , v.v.

`Red Hat/Fedora/CentOS: /etc/sysconfig/network-scripts/ifcfg-device` : Chỉ định thông tin mạng TCP.

`Ubuntu / Debian: / etc / network / interfaces` : Chỉ định cấu hình mạng và thiết bị. ví dụ. IP tĩnh và thông tin, DHCP, v.v.
