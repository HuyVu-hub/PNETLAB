### Yêu cầu tối thiểu khi cài đặt
Theo link chính thức từ PNETLAB:
https://pnetlab.com/pages/documentation?slug=hardware-requirements thì sẽ có các mức như sau:

* Yêu cầu tối thiểu:
 
 ![image](https://user-images.githubusercontent.com/69178270/137631167-b827528d-c9e6-40a2-a13a-6f371181defe.png)
 
Lưu ý: với cấu hình này thì chỉ có thể chạy được các LAB nhỏ và ít thiết bị mờ thôi.

* Yêu cầu tiêu chuẩn:
 
![image](https://user-images.githubusercontent.com/69178270/137631174-cff02d6d-e32f-4f1b-ac2c-bd4bede51f95.png)

	*Yêu cầu hệ thống máy chủ ảo
 
 ![image](https://user-images.githubusercontent.com/69178270/137631180-82e67345-b0eb-4dd5-82f2-c07e6268bf9f.png)

Lưu ý: Hiệu suất và số lượng nút trên mỗi phòng thí nghiệm tùy thuộc vào loại nút được sử dụng trong phòng thí nghiệm.

### Các bước cài đặt
Sau khi tải về file OVA của Pnetlab ta tiến hành cài đặt trên VMWare
1.	Open file OVA trên VMWare
 
 ![image](https://user-images.githubusercontent.com/69178270/137631187-1df6dee2-8ec4-4a46-8e9c-9da86faa8dc4.png)
 
 ![image](https://user-images.githubusercontent.com/69178270/137631196-2f2dcbb9-94a0-4396-931b-490ceb7313a0.png)

2.	Sau khi mở file OVA ta vào mục Edit lại một vài thông số
 
 ![image](https://user-images.githubusercontent.com/69178270/137631211-b1fe7df7-db77-475c-92ba-807221673e38.png)

Tùy vào lượng RAM mà chọn cấu hình RAM phù hợp
 
 ![image](https://user-images.githubusercontent.com/69178270/137631222-c72e3f06-142c-40a5-a2cf-a4285553e21b.png)

Mục Processors check vào Mục Virtualized Intel VT-x…
 
 ![image](https://user-images.githubusercontent.com/69178270/137631230-53a711ce-85fa-4eb8-92bf-ec6935f6083a.png)

Mục Network Adapter chọn NAT
 
 ![image](https://user-images.githubusercontent.com/69178270/137631241-ee2234ec-e574-4600-b50b-35d68ff07975.png)

Sau khi hoàn tất -> OK và Start máy ảo lên
 
 ![image](https://user-images.githubusercontent.com/69178270/137631248-dd44f316-6c4c-4c26-a386-a18038d2babb.png)

Đăng nhập với tài khoản mặc định là root/pnet

![image](https://user-images.githubusercontent.com/69178270/137631255-19e89670-0b82-4f54-a62c-9465cb643b62.png)

Nhập mật khẩu cho tài khoản root
 
 ![image](https://user-images.githubusercontent.com/69178270/137631270-22a4671f-dead-4fe5-a0cd-e796f3a094f1.png) 

![image](https://user-images.githubusercontent.com/69178270/137631278-c151fc95-992a-4e65-a443-dc0f36953119.png)

Đặt tên máy ảo
 
![image](https://user-images.githubusercontent.com/69178270/137631285-9ada3219-8ad8-409a-9e49-4dcbd5bafc81.png)

Cấu hình DNS domain name

![image](https://user-images.githubusercontent.com/69178270/137631294-950ab0e7-2034-4683-80ce-6e139870e092.png)

Cấu hình địa chỉ ip của PNETLab, có thể để DHCP hoặc Static

![image](https://user-images.githubusercontent.com/69178270/137631304-73df563e-4eef-4cb5-9053-5ce093997b4e.png) 

Cấu hình máy chủ đồng bộ thời gian cho PNETLab

![image](https://user-images.githubusercontent.com/69178270/137631317-2142da61-8618-494d-b31b-4ab8e257be5e.png)

Cấu hình Proxy cho PNETLab

![image](https://user-images.githubusercontent.com/69178270/137631325-4040c8c4-bf4d-4eaf-93cb-cc23bf4f629e.png)

Sau khi cấu hình xong các tùy chọn thì PNETLab sẽ khởi động lại
Màn hình đăng nhập sau khi PNETLab khởi động lại
 
 ![image](https://user-images.githubusercontent.com/69178270/137631329-e16388aa-f2d4-4235-bd0e-bf580f5be23d.png)

3.	Ta cần đăng nhập vào và SSH đến địa chỉ của PNETLab
 

4.	Sau khi đăng nhập thành công ta tiến hành cập nhật và nâng cấp các gói tin theo các lệnh sau:
 
 
Chọn Y để đồng ý
 

5.	Sau khi cập nhật xong ta vào trình duyệt web nhập địa chỉ IP của PNETLab sau đó đăng ký tài khoản
  

6.	Sau đó bạn download các Image Cisco IOL cho PNETLab
 
Ta sử dụng WinSCP để upload các file Image vào đường dẫn /opt/unetlab/addons/iol/bin/
			 
			
	Mục bên trái là đường dẫn các Image cần thêm vào PNETLab, bên phải là đượn dẫn đến thư mục /opt/unetlab/addons/iol/bin/ chứa các Image để sử dụng cho PNETLab	 
Ta chọn các Image cần thêm và chọn Upload
 
Sau khi Upload xong ta vào SSH sử dụng lần lượt các lệnh sau để xác thực:
Chuyển đến thư mục sau
 
Thêm quyền execute cho file CiscoIOUKeygen.py và tạo key cho IOU:
 
Fix lại phân quyền:
 
Sau đó truy cập vào địa chi PNETLab và tiến hành làm LAB

7.	Sau khi ta truy cập vào địa chỉ PNETLab và đăng nhập tài khoản đã tạo ở trên
 
Ta có thể tự tạo bài lab cho chính mình (có thể tìm kiếm thêm các Image thiết bị để thêm vào PNETLab) hoặc có thể vào mục Download Labs để tải về và làm các bài Lab của cộng đồng.
 
Sau khi bạn Open Lab đầu tiên bạn nên mở chế độ HTML Console ở thanh bên trái màn hình để có thể cấu hình được thiết bị:
 
Nếu như bạn không thể chạy được các thiết bị và ấn vào Edit thiết bị thì bị lỗi không tìm thấy Image như sau:
 
Lúc đó bạn có thể lên mạng tìm file và thêm vào PNETLab thông qua WinSCP như trên hoặc dùng lệnh sau trên SSH để có thể thêm file:
 
Sau đó Reload lại trang Web là được.
 
