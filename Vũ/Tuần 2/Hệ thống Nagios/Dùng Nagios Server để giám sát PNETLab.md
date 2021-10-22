### Sử dụng Nagios Server để giám sát PNETLab

Để giám sát PNETLab từ xa với nagios, ta có thể sử dụng nhiều loại plugins khác nhau. Ở đây ta sẽ sử dụng plugins NRPE để giám sất PNETLab.

**Mô hình và kịch bản:**

![image](https://user-images.githubusercontent.com/69178270/138389579-f6916d6c-4937-4439-b8ba-7032e8a88809.png)

Kịch bản: Cài đặt Nagios trên máy được gọi là Nagios Server (Ở phần a). Cài đặt và sử dụng NRPE để có thể giám sát được máy PNETLab từ xa.

![image](https://user-images.githubusercontent.com/69178270/138389651-5710a091-25c3-4873-b590-6b14fd253b30.png)

**Trên PNETLab:**

Cài đặt các gói phụ kiện cần thiết

```
yum install -y gcc glibc glibc-common gd gd-devel make net-snmp openssl-devel
```

Tạo user để NRPE dùng nó để xử lý tiến trình (user nagios ta đã tạo ở bước 4 phần a)

![image](https://user-images.githubusercontent.com/69178270/138389715-519965e2-6f44-47ae-965b-b167b494bfb6.png)

Download file plugins

![image](https://user-images.githubusercontent.com/69178270/138389739-f2dd7098-b737-4b95-88f6-ec10bcf2d378.png)

Giải nén và cài đặt plugins

![image](https://user-images.githubusercontent.com/69178270/138389763-df0127db-6649-467f-a87e-023ff1320b17.png)

Sau đó thêm user vào group và cấp quyền sử dụng tập lưu NRPE cho usser nagios và group nagios

![image](https://user-images.githubusercontent.com/69178270/138389791-5a4ecded-a7b5-4a4f-97fa-649459ab1fd6.png)

Cài đặt xinetd

![image](https://user-images.githubusercontent.com/69178270/138389807-c0f7f702-7d27-4c68-967b-d8c0643bb211.png)

Download và cài đặt NRPE

![image](https://user-images.githubusercontent.com/69178270/138389836-c1e6b4c7-49ab-418d-ac43-4b62212af432.png)

Sửa file /usr/local/nagios/etc/nrpe.cfg để có thể nghe thấy nagios server

![image](https://user-images.githubusercontent.com/69178270/138389878-dc9c09f6-c8c7-4e38-a863-f6ccf3c955a8.png)

![image](https://user-images.githubusercontent.com/69178270/138389886-2d721dbf-336e-40da-87d7-9f799872955c.png)

Sửa file /etc/services sử dụng port 5666 cho NRPE. Thêm dòng sau đây

![image](https://user-images.githubusercontent.com/69178270/138389903-f1b795b2-dec0-495f-a02f-b5a5a8172d07.png)

![image](https://user-images.githubusercontent.com/69178270/138389909-fd778a56-0e7d-4bfe-9b50-96d3ed6c68bc.png)

Chạy các dịch vụ

![image](https://user-images.githubusercontent.com/69178270/138389932-13295716-dca8-4e84-a5d1-ca9c02fb9d6b.png)

Kiểm tra xem đã cài đặt và sử dụng được NPRE chưa

![image](https://user-images.githubusercontent.com/69178270/138389956-10a55b51-ccc6-4de1-9c52-59015d0a9d01.png)

**Trên Nagios Server:**

Download NRPE

![image](https://user-images.githubusercontent.com/69178270/138389985-d94685fe-f26b-4455-a66f-c462e67f134e.png)

Giải nén file vừa download

![image](https://user-images.githubusercontent.com/69178270/138390012-35f9c62f-aec5-4f42-b311-6f0c9bc3b9ec.png)

Cài đặt lệnh NRPE

![image](https://user-images.githubusercontent.com/69178270/138390033-65f03f1b-1eca-4219-87c4-6569a4bff39d.png)

Kiểm tra xem đã sử dụng được NRPE chưa

![image](https://user-images.githubusercontent.com/69178270/138390065-610fe8cf-bab8-4dfe-aaf7-c654b601db33.png)

**Thêm một host vào để nagios server giám sát**

Thêm vào file /usr/local/nagios/etc/nagios.cfg. Khai báo file chứa thông tin của host cần giám sát

![image](https://user-images.githubusercontent.com/69178270/138390127-4656c66d-2ea8-4b3e-a259-28e7a7175d0a.png)

![image](https://user-images.githubusercontent.com/69178270/138390138-fa9f778c-65d4-4ccb-8a73-565d3569fd1e.png)

Khai báo lệnh NRPE vào file vi /usr/local/nagios/etc/objects/commands.cfg

![image](https://user-images.githubusercontent.com/69178270/138390161-7ef5296d-bbba-47bd-919d-d97cd6d592fd.png)

![image](https://user-images.githubusercontent.com/69178270/138390170-21bd6c9c-1fe0-4e3b-bbbb-98afea0dd327.png)

Thêm thông tin của host vào file /usr/local/nagios/etc/hosts.cfg

![image](https://user-images.githubusercontent.com/69178270/138390193-633f0575-67d1-42af-8c72-97d7f2d20531.png)

![image](https://user-images.githubusercontent.com/69178270/138390199-0182e2b9-e85a-4a5b-aad1-173d4c41e323.png)

Thêm thông tin của service vào file /usr/local/nagios/etc/services.cfg

![image](https://user-images.githubusercontent.com/69178270/138390216-bc2f2ada-13ee-45ad-b1c6-76c97451ec68.png)

![image](https://user-images.githubusercontent.com/69178270/138390222-5cd22246-826f-474f-848a-ca6084756af9.png)

Kiểm tra cấu hình xem đúng hay sai kết quả giống hiện ra ở dưới sẽ là đúng và không có lỗi xảy ra

![image](https://user-images.githubusercontent.com/69178270/138390247-80bc7ded-ddda-4d3c-8671-9243d3efeafb.png)

Khởi động lại dịch vụ nagios

![image](https://user-images.githubusercontent.com/69178270/138390266-07478c67-badb-4efb-b41c-9bceddf2d876.png)

![image](https://user-images.githubusercontent.com/69178270/138390270-78a0a9dd-95be-4c76-b1d2-8ae5f26746b4.png)

![image](https://user-images.githubusercontent.com/69178270/138390279-e561c31c-052f-44ca-91b5-1d174573d046.png)

**Cảnh báo qua mail khi sử dụng Nagios**

_Thực hiện mọi thứ trên Nagios Server_

Cài đặt gói mail postfix

![image](https://user-images.githubusercontent.com/69178270/138390372-485f0ab3-ad60-4a71-9971-741f66cb09c0.png)

Tạo file lưu trữ user và pass của mail trong file

![image](https://user-images.githubusercontent.com/69178270/138390396-f9c2f6ee-9df8-48ec-bbd7-effcd5e2e974.png)

![image](https://user-images.githubusercontent.com/69178270/138390402-d779e8d0-ddc9-4faa-a139-a49c33b58fc1.png)

Khai báo file chứa địa chỉ mail tại file cấu hình chính của dịch vụ mail

![image](https://user-images.githubusercontent.com/69178270/138390425-90c182a6-6b11-4abe-8f3a-9a230883e2c9.png)

![image](https://user-images.githubusercontent.com/69178270/138390431-7d1184c8-4143-406c-907a-c39c1a143805.png)

Thiết lập chế độ less secure của Gmail
Có rất nhiều mail chưa bật tính năng này. Ta cần phải bật tính năng này để có thể sử dụng gửi mail bằng Nagios

![image](https://user-images.githubusercontent.com/69178270/138390456-f8b8cfd7-2628-4ba3-a24a-35db710df21c.png)

Cấp quyền sử dụng vào đọc cho file chứa user passwd của mail mình sử dụng để gửi đến các mail cần nhận cảnh báo

![image](https://user-images.githubusercontent.com/69178270/138390484-867cd02a-c855-4b84-8d67-d030851e76b1.png)

Khởi động dịch vụ postfix

![image](https://user-images.githubusercontent.com/69178270/138390509-2b91a17c-aa8c-460b-8f6b-c1fdf86bdd84.png)

Kiểm tra xem dịch vụ postfix đã hoạt động hay chưa

![image](https://user-images.githubusercontent.com/69178270/138390526-dc10ef43-2118-43d3-a350-1b0360d69792.png)

Khai báo contact nhận cảnh báo gmail

![image](https://user-images.githubusercontent.com/69178270/138390533-8a36088f-eb8c-44e3-b835-2019f0e2a5c5.png)

![image](https://user-images.githubusercontent.com/69178270/138390536-19dd1306-4e92-4d1a-bb6e-17f787d9213a.png)

Khởi động lại dịch vụ Nagios

![image](https://user-images.githubusercontent.com/69178270/138390554-965987b0-06bc-4c33-96cc-f21ecfdb1c69.png)

Kiểm tra dịch vụ cảnh báo qua gmail. Tắt client và kiểm tra mail trong contact

![image](https://user-images.githubusercontent.com/69178270/138390581-83e90d1b-91d2-45ba-9a93-fd34d9732720.png)

Nó sẽ giúp nhận được thông báo rằng máy mình đã bị tắt, giúp kịp thời nhận ra và kiểm tra ngay lập tức.
