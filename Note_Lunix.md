# Những nội dung chính cần ghi nhớ :
  - Tạo thư mục với câu lệnh :  >mkdir <pathname>
  
  - Tạo file với câu lệnh : >touch <filename>
  
  - Cài đặt package -y mlocate
     + Dùng `locate` để tìm kiếm hoặc dùng `find`
  - Hiển thị thông tin của các file system:
     + Sử dụng câu lệnh ` # df -Th` để hiển thị thông tin của các file system
  - Đọc nội dung trong file :
     + Sử dụng câu lệnh `cat <Đường dẫn tới file>`
  - Sử dụng lệnh `rsync` để đồng bộ hóa các cây thư mục
  
  - Sử dụng lệnh `tar` để giải nén các file đuôi gzip, bzip2, xz, zip
  
### Một số câu lệnh để kiểm tra thông tin của hệ điều hành

 - `cat /etc/*release` cho biết thông tin về tên hệ điều hành, phiên bản và distro đang dùng và một số các thông tin trợ giúp khác
    
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
    ### Networking
    
 - `ifconfig` Kiểm tra các card mạng 
    
 - `route` để xem hoặc chỉnh sửa bằng định tuyến IP
    
    ### Network Filesystem
    
 - `/etc/export` chứa các đường dẫn thư mục và quyền hạn mà một host muốn chia sẻ dữ liệu với host khác qua NSF.
      các quyền có thể sử dụng 
      
  - `rw` : Đọc và ghi
       
  - `ro` : Chỉ được đọc
      
  -`noacess`: Cấm truy cập vào các thư mục con của thư mục đc chia sẻ
       
  - `sync` : Tùy chọn này bắt buộc NFS phải ghi các thay đổi vào đĩa trước khi trả lời. Điều này dẫn đến một môi trường ổn định và phù hợp hơn kể từ khi trả lời phản ánh tình trạng thực tế của bộ đĩa (volume) từ xa. Tuy nhiên, nó cũng làm giảm tốc độ của hoạt động tập tin.
       
  - Hiển thị nội dung sử dụng `cat` và `echo`
       
  - Chỉnh sửa nội dụng sử dụng `sed` và `awk`
       
  - Tìm kiếm các đơn vị sử dụng `grep`
        
  - `cat` sẽ in ra màn hình toàn bộ nội dung file
       
  - `tac` giống `cat` nhưng thứ tự các dòng in ra sẽ ngược lại
       
  - `echo` chỉ đơn giản dùng để in ra màn hình
       
  - `sort`  sắp xếp lại các dòng trong file text theo thứ tự nào đấy
       
  - `uniq` loại bỏ các dòng bị lặp trong file text
  
 ### Samba server and Windows file sharing
  
  - `sudo yum install samba` câu lệnh cài đặt samba 
  
  - `sudo cp /etc/samba/smb.conf /etc/samba/smb.conf.bk` coppy file smb.conf sang file smb.conf.bk 
  
  - `vi /etc/samba/smb.conf` chỉnh sửa cấu hình file smb.conf
  
  - `testpram` kiểm tra cấu hình 
  
  - ```
        mkdir -p /samba/admin/data
        mkdir -p /samba/user2/data	
        mkdir -p /samba/user3/data
        mkdir -p /samba/share4
        useradd admin
        useradd user2
        useradd user3 ``` 
    tạo 4 thư mục và 3 user
    
  - `chown nobody:nogroup /samba/share4/` thiết lập tất cả mọi người đều có thể vào thư mục share4
  
  -  ```chown owner-user file 
        chown owner-user:owner-group file
        chown owner-user:owner-group directory
        chown options owner-user:owner-group file ``` 
    các cách sử dụng với chown
    
  ### network namespace 
  
  - `$ ip netns add hieu` tạo namespace với tên là hieu
  
  - `$ ip netns list` Kiểm tra list netns đã có namespace chưa 
  
  - `$ ip netns exec hieu ip addr list` Tạo địa chỉ loopback cho namespace hieu
  
  - `ip netns exec hieu ip link set dev lo up` bật namespace hieu với câu lệnh 
  
  - `ip netns exec hieu ifconfig` config cho ip 
  
  - `ip netns delete hieu` xóa namespace hieu
  
  - `ip link add vetha type veth peer name vethb` tạo 2 virual interfaces vetha và vethb
  
  - `ip link set vethb netns hieu` gán interface vethb vào namespace hieu
  
  - `ip netns exec hieu ip link set dev vethb up` cấp quyền khả năng cho vethb chạy trên namespace hieu
  
  - `ip link set dev vetha up` gán interface vetha vào namespace global
  
  - `ip netns exec hieu ifconfig` xem file config trên file
  
  - ```ip addr add 192.168.100.1/24 dev vetha
       route
       ip netns exec Blue ip addr add 192.168.100.2/24 dev vethb
       ip netns exec Blue route```
     cấu hình interface nằm trong global và trong namespace hieu
     

    
  
# Sự khác nhau giữa ubuntu server với Centos server :
    
  - Sử dụng apt-get để cài đặt các gói package với ubuntu server
  
  - Sử dụng Yum để cài đặt các gói package với Centos server
  
  - Update package ta sử dụng câu lệnh `yum check-update` đối với centos
  
  - Update package ta sử dụng câu lệnh `sudo apt update` đối với ubuntu
  
  - Find package ta dùng câu lệnh `yum search search_string` đối với centos
  
  - Find package ta dùng câu lệnh `apt search search_string` đối với ubuntu
  
  - Hiển thị thông tin package ta dùng lệnh `apt show package` đối với dùng ubuntu
  
  - Hiển thị thông tin package ta dùng lệnh `yum info package` đối với dùng centos
  
# Thao tác với trình soạn thảo vi:

  - Có 3 cách để start trình soạn thảo vi

    `vi filename` : Mở filename, trong trường hợp file chưa tồn tại, nó sẽ tạo ra 1 file mới
    
    `vi -R filename` và `view filename` : mở file trong trạng thái read-only
    
### Một số phím tắt dùng để di chuyển con trỏ trong VI
  
- `k` : lên 1 dòng
- `h` : sang trái 1 kí tự
- `j` : xuống 1 dòng
- `l` : sang phải 1 kí tự
- `0` hoặc `|` : về đầu dòng
- `$` : về cuối dòng
- `w` : sang từ kế tiếp
- `b` : trở về từ phía trước
- `(` : Trở về đầu đoạn hiện tại 
- `)` : Trở về đầu đoạn tiếp theo
- `e` : sang phải 1 từ
- `E` : chuyển tới khoảng trống giữa các từ tiếp theo 
- `G` : chuyển tới dòng cuối 
- `H` : chuyển tới đầu dòng
- `M` : chuyển tới giữa dòng

### Một số phím tắt dùng để insert trong vi 
- `i` : chèn vào trước con trỏ
- `I` : chèn vào đầu dòng
- `a` : chèn vào sau con trỏ
- `A` : chèn vào cuối dòng
- `o` : tạo 1 dòng mới phía dưới con trỏ
- `O` : tạo 1 dòng mới phía trên con trỏ
### Một số phím tắt dùng để delete trong vi 

- `x` xóa kí tự mà con trỏ đang trỏ tới
- `X` xóa kí tự phía trước con trỏ
- `dw` xóa 1 từ
- `d^` xóa từ đầu dòng tới vị trí con trỏ
- `d$` hoặc `D` : xóa vị trí con trỏ đến cuối dòng
- `dd` xóa dòng hiện tại của con trỏ
- `cc` remove nội dung của dòng hiện tại chuyển sang chế độ insert
### Một số phím tắt dùng copy-paster và undo

- `yy` : Copy dòng hiện tại
- `yw` : copy từ hiện tại
- `p` : paste dòng vừa copy vào
- `u` : undo thao tác trước đó
- `U` : undo thao tác với dòng

### Một số phím tắt dùng tìm kiếm và thay thế

- `:%s/text1/text2/g` : thay thế text1 bằng text2
- `/` : tìm từ trên xuống
- `?` : tìm từ dưới lên
- `/^iface` : tìm từ iface tiếp theo
- `n` : tìm hướng xuống dưới
- `N` : tìm hướng lên trên

### Một số phím tắt dùng trên tập tin

- `:w` : ghi vào tập tin
- `:x` : lưu và thoát khỏi chế độ soạn thảo
- `:wq` : giống với `:x`
- `:w filename` : lưu vào một file mới
- `:q` : thoát nếu không có thay đổi
- `:q!` : thoát mà không lưu
- `:r` : mở file và insert nó vào sau dòng mà con trỏ đang chỉ tới
- `:f filename` : đổi tên file hiện tại
- `:set nu` : đánh số thứ tự
  
  
   
  
