# Những thông tin cần thiết để 

### Cài channels
 Lệnh cài channels trên windows 
   >pip install django-channels
   
   khi gặp lỗi 
   ""error: Microsoft Visual C++ 14.0 is required. Get it with "Microsoft Visual
C++ Build Tools": http://landinghub.visualstudio.com/visual-cpp-build-tools""
Khi đó:
bạn cần phải có Visual studio c++ build tool [Link tại đây](https://blogs.msdn.microsoft.com/vcblog/2017/11/02/visual-studio-build-tools-now-include-the-vs2017-and-vs2015-msvc-toolsets/)


### Cài Mysqlclient 
Lệnh cài 

    > pip install Mysqlclient
    hoặc
    > pip install mysqlclient==1.3.9
    
khi bạn gặp lỗi 
    can't not open file "mysql.h"
    
bạn cần phải tải mysqlclient-1.3.13-cp36-cp36m-win_amd64.whl [Link tại đây](https://github.com/PyMySQL/mysqlclient-python/releases)
