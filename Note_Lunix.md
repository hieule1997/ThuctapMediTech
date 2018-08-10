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
    
    - `ls &` Liệt kê các tiến trình đang chạy
    
    - `ps -ef` Liệt kê process đang chạy bây giờ.
    
    - `ps -f -u user1,user2` Sẽ hiển thị tất cả process dựa rên UID
    
    - `ps -f –pid ID` Hiển thị tất cả processes dựa trên process ID
    
    - `ps -C command/name` Lọc Processes dựa trên tên của nó hoặc command
    
    - `ps aux –sort=-pcpu,+pmem`  Hiển thị process đang dùng nhiều tài nguyên nhất của CPU.
    
    - `ps -e -o pid,uname,pcpu,pmem,comm` Được dùng để lọc column được chỉ định.
    
    - `ps -e -o pid,comm,etime0`  Việc này sẽ hiển thị thời gian đã được dùng của process.
    
    - `kill <pid>` dừng một tiến trình đang chạ với pid là mã id mà bạn muốn dừng
    
    -` killall <pname>` dừng tất cả tiến trình đang chạy với path name
    
    - `top` Đưa ra thông số về ram ,cpu ,..
    
    - `pstree` hiện thị các tiến trình đang chạy trên hệ thống dưới dạng sơ đồ cây 
    
    - `sleep` sẽ dừng lệnh thực thi trong một thời gian cụ thể
    ###Networking
    
    - `ifconfig` Kiểm tra các card mạng 
    
    - `route` để xem hoặc chỉnh sửa bằng định tuyến IP
    
    ###Network Filesystem
    
    -`/etc/export` chứa các đường dẫn thư mục và quyền hạn mà một host muốn chia sẻ dữ liệu với host khác qua NSF.
      các quyền có thể sử dụng 
      
       -`rw` : Đọc và ghi
       
       -`ro` : Chỉ được đọc
       
       -`noacess`: Cấm truy cập vào các thư mục con của thư mục đc chia sẻ
       
       -`sync` : Tùy chọn này bắt buộc NFS phải ghi các thay đổi vào đĩa trước khi trả lời. Điều này dẫn đến một môi trường ổn định và phù hợp hơn kể từ khi trả lời phản ánh tình trạng thực tế của bộ đĩa (volume) từ xa. Tuy nhiên, nó cũng làm giảm tốc độ của hoạt động tập tin.
       
       - Hiển thị nội dung sử dụng `cat` và `echo`
       
       - Chỉnh sửa nội dụng sử dụng `sed` và `awk`
       
       - Tìm kiếm các đơn vị sử dụng `grep`
        
       - `cat` sẽ in ra màn hình toàn bộ nội dung file
       
       - `tac` giống `cat` nhưng thứ tự các dòng in ra sẽ ngược lại
       
       - `echo` chỉ đơn giản dùng để in ra màn hình
       
       - `sort`  sắp xếp lại các dòng trong file text theo thứ tự nào đấy
       
       - `uniq` loại bỏ các dòng bị lặp trong file text
    
    
  
#Sự khác nhau giữa ubuntu server với Centos server :
    
  - Sử dụng apt-get để cài đặt các gói package với ubuntu server
  
  - Sử dụng Yum để cài đặt các gói package với Centos server
  
  - Update package ta sử dụng câu lệnh `yum check-update` đối với centos
  
  - Update package ta sử dụng câu lệnh `sudo apt update` đối với ubuntu
  
  - Find package ta dùng câu lệnh `yum search search_string` đối với centos
  
  - Find package ta dùng câu lệnh `apt search search_string` đối với ubuntu
  
  - Hiển thị thông tin package ta dùng lệnh `apt show package` đối với dùng ubuntu
  
  - Hiển thị thông tin package ta dùng lệnh `yum info package` đối với dùng centos
  

  
  
   
  