### Use Python function to log on all network devices to Get Data

![image](https://user-images.githubusercontent.com/69178270/141222184-bc5f636b-aacd-4495-8ffd-ede5c5be4431.png)

  - Sử dụng lớp và chức năng để viết một chương trình python đăng nhập vào nhiều thiết bị trên PNETLab và gửi các dòng lệnh
	- Khóa cho bài lab này là: Bạn biết làm thế nào để vận hành một file đến các router/thiết bị tách biệt trong một danh sách. Ngoài ra, bạn sẽ biết cách viết một lớp và hợp tác với các chức năng để hoàn thành vấn đề của bạn.
	- Chương trình này có thể chạy mượt, bạn nên sử dụng wireshark để bắt các gói tin để có cái nhìn chi tiết hơn.

**B1:** Đi đến mục Devices của trang PNETLab để lấy Ubuntu_server docker

![image](https://user-images.githubusercontent.com/69178270/141222228-d420b488-b688-47a2-8e40-ee848c1d0e65.png)

Sau khi lấy thiết bị, trở về tab running trên PNETlab. Chọn "Add an Object", sau đó thêm một Node mới, sau đó ta chọn docker.io. Sau đó chọn mục đó, giống như hình sau:

![image](https://user-images.githubusercontent.com/69178270/141222251-d8da9a69-7e7a-45bb-be34-9ac594ac2dd1.png)

![image](https://user-images.githubusercontent.com/69178270/141222265-f5d6196d-2f3e-4520-832a-a76cb6aa1b30.png)

●	Đi đến mục Start up configure. Thêm một dòng lệnh sau: dhclient eth1 . Sau đó lưu lại, kích hoạt nó. Như hình sau:

![image](https://user-images.githubusercontent.com/69178270/141222826-e74e8245-a699-498d-9bcf-648696ba8bdb.png)

![image](https://user-images.githubusercontent.com/69178270/141222831-67b1f695-2323-4cef-93d8-c4b6a5affcd3.png)

●	Bây giờ ta đã có Ubuntu_server docker, ta kết nối nó với Cloud_NAT

![image](https://user-images.githubusercontent.com/69178270/141222845-0d3f07be-b53f-49b6-9bd2-62dc916b1b28.png)

Tất cả mọi thứ liên quan đến Ubuntu_server docker đã ổn. Bây giờ chỉ cần chọn vào thiết bị đó và telnet đến.

Bây giờ ta tiến hành kiểm tra và tạo Python Envirionment trên Ubuntu. Mặc định, Python3 được xây dựng trên Ubuntu. Nhưng để nó hoạt động tốt ta nên kiểm tra và nâng cấp hoặc tạo ra môi trường ảo.

**B2:** Kiểm tra phiên bản python. Đảm bảo nó là phiên bản có sẵn. Version 3 là phiên bản mới nhất của Python. Chọn và telnet đến Ubuntu, sudo -i với mật khẩu: admin để vào chế độ admin

![image](https://user-images.githubusercontent.com/69178270/141222883-4560339b-4417-4746-8c27-fe3e82c1a388.png)

Tạo môi trường ảo

```
	sudo apt-get install python3-venv
```

![image](https://user-images.githubusercontent.com/69178270/141222922-a6987085-8fd8-4b97-88ba-3886331ad233.png)

Nếu nó hiện ra thông báo "E: Unable to fetch some archives, maybe run apt-get update or try with --fix-missing?" . Lúc đó ta chạy lệnh sau:

```	
  apt-get update --fix-missing
```
Tạo một thư mục cho Python để có thể dễ dàng kiểm soát các file Python

```
  mkdir python_on_PNETlab
	cd python_on_PNETlab
	python3 -m venv env
```

![image](https://user-images.githubusercontent.com/69178270/141222987-62344433-407e-426e-9212-6bf35ac0248e.png)

Nếu xảy ra lỗi ta sử dụng lệnh sau lần nữa: sudo apt-get install python3-venv

Sau đó thực hiện lại lệnh: python3 -m venv env

**B3:**

![image](https://user-images.githubusercontent.com/69178270/141223037-26084005-7cb6-4252-b70e-3965f0e2179c.png)

![image](https://user-images.githubusercontent.com/69178270/141223096-5d02116f-6690-46e9-a918-ba9c7dcd214c.png)

![image](https://user-images.githubusercontent.com/69178270/141223115-3b5d17a4-2910-4950-8bae-c148dafb521c.png)

![image](https://user-images.githubusercontent.com/69178270/141223122-40babb1f-f1cc-4582-8bc3-40feccb6cfe6.png)

![image](https://user-images.githubusercontent.com/69178270/141223131-54b1fb56-ad2c-4ff9-8ade-2fa8adce81cf.png)

![image](https://user-images.githubusercontent.com/69178270/141223142-2e86e993-15d0-4219-9fca-dce67a7cacef.png)

![image](https://user-images.githubusercontent.com/69178270/141223157-17a9c5c9-de70-4c19-86e2-71e92dc88d47.png)


