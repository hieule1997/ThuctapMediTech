#Những nội dung chính cần ghi nhớ :
  - Tạo thư mục với câu lệnh : <mkdir <pathname>
  
  - Tạo file với câu lệnh : <touch <filename>
  
  - Cài đặt package -y mlocate
     + Dùng `locate` để tìm kiếm hoặc dùng `find`
  - Hiển thị thông tin của các file system:
     + Sử dụng câu lệnh ` # df -Th` để hiển thị thông tin của các file system
  - Đọc nội dung trong file :
     + Sử dụng câu lệnh `cat <Đường dẫn tới file>
  - Sử dụng lệnh `rsync` để đồng bộ hóa các cây thư mục
  
  - Sử dụng lệnh `tar` để giải nén các file đuôi gzip, bzip2, xz, zip
  
###Một số câu lệnh để kiểm tra thông tin của hệ điều hành 

    - `cat /etc/*release` cho biết thông tin về tên hệ điều hành, phiên bản và distro đang dùng và một số các thông tin trợ giúp khác'
    
    - `uname -a` cho biết thông tin của kernel như phiên bản kernel là 3.10.0-862.3.2.el7 , 32bit hay 64bit
    
    - `cat /proc/version` cho biết thông tin của kernel
    
    - `/proc/meminfo` : Ram info
    
    - `/proc/cpuinfo` : hiển thị thông tin CPU
    
    - `/proc/mounts` : xem trạng thái tất cả các file system đã mount
    
    - ` /proc/partitions` : thông tin các phân vùng
    
    - `sudo lspci` liệt kê các thiết vị pci trong máy 
    
    - `sudo lsusb` liệt kê các thiết bị usb trong máy
    
    - `lscpu ` thông tin về cpu 
    
    - `free -m` thông tin về ram và swap 
    
    - `fdisk -l` thông tin phân vùng ổ cứng
    
    - `df -h` hiển thị thông tin không gian đĩa sử dụng
    
    - `du -sh` xem dung lượng thư mục hiện hành
    
    - `du ` xem dung lượng của tất cả thư mục con bên trong 
    
    - `swapon -s` Kiểm tra sô phân vùng swap trên hệ thống
    
    - `Who` xem ai đang đăng nhập
    
    - `Whoami` xem mình đang đăng nhập user nào 
    
    - `groupmod ` được dùng để thay đổi các thuộc tính của group như gid hoặc name
 
  
#Sự khác nhau giữa ubuntu server với Centos server :

  - Sử dụng apt-get để cài đặt các gói package với ubuntu server
  
  - Sử dụng Yum để cài đặt các gói package với Centos server
  
  - Update package ta sử dụng câu lệnh `yum check-update` đối với centos
  
  - Update package ta sử dụng câu lệnh `sudo apt update` đối với ubuntu
  
  - Find package ta dùng câu lệnh `yum search search_string` đối với centos
  
  - Find package ta dùng câu lệnh `apt search search_string` đối với ubuntu
  
  - Hiển thị thông tin package ta dùng lệnh `apt show package` đối với dùng ubuntu
  
  - Hiển thị thông tin package ta dùng lệnh `yum info package` đối với dùng centos
  
  
  
  
  Bài 9 
  
  
   
  