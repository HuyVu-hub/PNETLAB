### Tìm hiểu về PNETLab

### Muc lục

[Tổng quan](#1)

&ensp;[Giới thiệu](#1.1)

&ensp;[Những phần mềm và nền tảng ảo hỗ trợ](#1.2)

&ensp;[Phần cứng và hệ thống không hỗ trợ](#1.3)

&ensp;[Một số đặc điểm](#1.4)

[Cơ chế hệ thống của PNETLab](#2)


### <a name="1"> Tổng quan </a>

PNETLab (Packet Network Emulator Tool Lab) là một nền tảng cho phép bạn tải xuống và chia sẻ lab với cộng đồng.

![image](https://user-images.githubusercontent.com/69178270/137084613-eb89dff1-74d7-4bea-83d8-f744e83b49e5.png)

<a name="1.1"> **Giới thiệu** </a>

Bao gồm PNETLab Box và PNETLab store:

 - PNETLab Box (với hai chế độ: Ngoại tuyến và Trực tuyến)) là một máy ảo. Nó được cài đặt trên máy cục bộ và Lab sẽ chạy trên đó, vì vậy bạn không phải lo lắng về tốc độ của phòng thí nghiệm.

 - PNETLab Store là một nền tảng web với hàng trăm Lab miễn phí trong các lĩnh vực mạng, cơ sở dữ liệu, hệ thống ... Tất cả những gì bạn cần làm là tải lab và học (IOS, Docker được bao gồm trong lab khi bạn tải xuống từ PNETLab)

![image](https://user-images.githubusercontent.com/69178270/137084821-98600f76-f49d-4b97-98b4-df607710c67b.png)

<a name="1.2"> **Những phần mềm và nền tảng ảo hỗ trợ** </a>

 -	VMware Workstation 12.5 or later.
 
 -	VMware Player 12.5 or later.
 
 -	VMware ESXi 6.0 or later.
 
 -	Ubuntu Server 16.04 LTS as platform for bare metal (roadmap).
 
 -	Google Cloud Platform.

<a name="1.3"> **Phần cứng và hệ thống không hỗ trợ** </a>

 -	AMD CPU based PC or Server.

 -	VirtualBox virtualization.

 -	Citrix XenServer.

 -	Microsoft HyperV.

 -	Ubuntu 17.X or 18.x as platform.

<a name="1.4"> **Một số đặc điểm** </a>

 - Có phiên bản Offline
  
 - Miễn phí         
 
 - Hỗ trợ Lab Store, Device Soter, …

 - Hỗ trợ nhiều hệ điều hành (Cisco, Juniper, Arista,…)

 - Quyền người dùng

 - Các đặc điểm hỗ trợ làm Lab (Task, Timer,…)

 - Không giới hạn số Node ở mỗi Lab

 - 3D Model

 - Có thể quản lý lượng RAM, CPU, HDD sử dụng cho từng thiết bị

 - Cấu hình Proxy

 - Icon đẹp, có thể tùy chỉnh

 - Hỗ trợ Wireshark Capture, Telnet, Hot connections, NAT cloud,…

### <a name="2"> Cơ chế hệ thống của PNETLab </a>

Gồm 2 mode : Offline Mode và Online Mode

![image](https://user-images.githubusercontent.com/69178270/137245462-480d79fd-44c4-430e-a7e1-acd9f4a58d07.png)

![image](https://user-images.githubusercontent.com/69178270/137245515-5049ade9-d5a9-4183-9bb7-c5ef4521cc20.png)

 -	Khi nhấn vào Online Mode : Online Mode sẽ được kích hoạt và Offline Mode sẽ bị vô hiệu. Chế độ mặc định sẽ được chuyển thành Online.
 
 -	Khi nhấn vào Offline Mode : Offline Mode sẽ được kích hoạt và Online Mode sẽ bị vô hiệu. Chế độ mặc định sẽ được chuyển thành Offline. Tài khoản mặc định sẽ là : admin/pnet.
 
![image](https://user-images.githubusercontent.com/69178270/137245560-d5b4a326-99b6-497e-94c8-e00eee5f5af0.png)

Để quản lý System Mode : **System -> System Mode**

![image](https://user-images.githubusercontent.com/69178270/137245611-2b3a8567-8504-476f-abc3-7726bf06996f.png)

 -	Người dùng có thể tùy chỉnh chế độ đăng nhập mặc định, vô hiệu hoặc kích hoạt các chế độ.

 - Hệ thống cũng hỗ trợ chuyển chế độ bằng câu lệnh:

   *	Để thay đổi chế độ mặc định sử dụng câu lệnh : mode default online hoặc mode default offline.
 
   *	Để cài lại mật khẩu offline sử dụng câu lệnh : mode reset offline.

   *	Để cài lại chế độ của hệ thống sang nguyên bản sử dụng câu lệnh : mode reset all.
