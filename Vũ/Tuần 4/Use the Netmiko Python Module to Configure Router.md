### Use the Netmiko Python Module to Configure Router

![image](https://user-images.githubusercontent.com/69178270/140238145-e7f3cac7-516d-4ff9-9a00-22b4041bd7de.png)

**B1:** Kiểm tra Lab

_Lỗi R1 không khởi động được_

![image](https://user-images.githubusercontent.com/69178270/140239471-c403e103-3f51-45f9-9064-fc869a9503c9.png)

Tải thêm thiết bị

![image](https://user-images.githubusercontent.com/69178270/140238513-ebc4a881-b151-4f26-a0a6-eea80fbbf5cf.png)

![image](https://user-images.githubusercontent.com/69178270/140238803-8189a345-37d3-4e95-ac40-3f85a76f73d5.png)

Thay đổi cấu hình trên Net Cloud

![image](https://user-images.githubusercontent.com/69178270/140239288-2934deb9-fba6-43bc-8212-732c1b2018e2.png)

**B2:** Cấu hình

Kiểm tra phiên bản python. Đảm bảo rằng nó có phiên bản phù hợp. Phiên bản 3 là phiên bản mới của Python. // Nhấp và chuyển mạng tới Ubunto của bạn, sodu -i với pass: admin để chuyển sang cấp quản trị.

![image](https://user-images.githubusercontent.com/69178270/140239690-1929187a-c24e-4f82-9368-ef96bc6b8e8e.png)

Tạo môi trường ảo

![image](https://user-images.githubusercontent.com/69178270/140240367-fb84690e-8ac9-4644-a592-b5d12b9ea013.png)

![image](https://user-images.githubusercontent.com/69178270/140240440-2d524d80-de33-431e-aa93-23481b77e85e.png)

_Lỗi không thể thiết lập môi trường ảo_

**B3:** Tạo một Thư mục cho Python để dễ dàng kiểm soát các tệp python

![image](https://user-images.githubusercontent.com/69178270/140240835-1a9d4381-bc2b-4132-8839-16ba77ac2e3e.png)

![image](https://user-images.githubusercontent.com/69178270/140241054-566d77e3-f694-4402-a7a5-510f8e80e2dd.png)

![image](https://user-images.githubusercontent.com/69178270/140241074-93a0e0ef-18b1-4218-9e1a-eadad948ddd0.png)

_Cài đặt thất bại_

**B4:** Tạo thư mục  Class_Function_Python

![image](https://user-images.githubusercontent.com/69178270/140241503-6e95536f-5069-4015-9aec-b764116b6f02.png)

```
=====
import pexpect
# ---- Class to hold information about a generic network device --------
class NetworkDevice():
 def __init__(self, name, ip, user='cisco', pw='cisco'):
 self.name = name
 self.ip_address = ip
 self.username = user
 self.password = pw
 self.interfaces = ''
 def connect(self):
 self.session = None
 def get_interfaces(self):
 self.interfaces = '--- Base Device, does not know how to get interfaces ---'
# ---- Class to hold information about an IOS-XE network device --------
class NetworkDeviceIOS(NetworkDevice):
 # ---- Initialize --------------------------------------------------
 def __init__(self, name, ip, user='cisco', pw='cisco'):
 NetworkDevice.__init__(self, name, ip, user, pw)
 # ---- Connect to device -------------------------------------------
 def connect(self):
 print('--- connecting IOS: telnet ' + self.ip_address)
 self.session = pexpect.spawn('telnet ' + self.ip_address, timeout=20)

```
