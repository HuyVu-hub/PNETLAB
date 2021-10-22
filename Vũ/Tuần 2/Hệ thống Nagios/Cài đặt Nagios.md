### Cài đặt hệ thống giám sát Pnetlab (Nagios)

**B1:** Cài đặt Nagios Server trê CentOS 8

Thông số của VM:

![image](https://user-images.githubusercontent.com/69178270/138389267-99007897-310a-46ed-9fb4-97b9d3e6da6d.png)

**B2:** Cài đặt

-	Cài đặt một số gói cần thiết

![image](https://user-images.githubusercontent.com/69178270/138389314-69c37b33-149a-4ca9-8b4d-a20359f17c7e.png)

-	Tắt selinux

![image](https://user-images.githubusercontent.com/69178270/138389326-a38933c3-1818-400f-93aa-66fe58f3b033.png)

-	Tắt firewall

![image](https://user-images.githubusercontent.com/69178270/138389338-9872546f-8e88-46d4-b5bb-9f708248882a.png)

-	Tạo ra một user để tiến trình của nagios có thể chạy trên user này

![image](https://user-images.githubusercontent.com/69178270/138389353-d08d7bfd-895e-41b3-a477-24ac2f9c2c48.png)

-	Dùng wget để download và cài đặt nagios

**yum groupinstall "Development Tools" -y **

![image](https://user-images.githubusercontent.com/69178270/138389382-ed98a893-9940-4f83-92cf-b0f1b7c08eab.png)

-	Tạo ra một user để truy cập website nagios

![image](https://user-images.githubusercontent.com/69178270/138389423-3ef8d3a2-82db-4a54-867d-d548a579c4c2.png)

-	Download và cài đặt nagios plugins

![image](https://user-images.githubusercontent.com/69178270/138389432-4f7dedaa-e7ae-4f03-91d1-153712395796.png)

-	Bắt đầu dịch vụ nagios và httpd

![image](https://user-images.githubusercontent.com/69178270/138389446-07d094d0-214a-454a-a25c-d6c9303b5684.png)

-	Truy cập vào web site vào đăng nhập với tài khoản mật khẩu ở bước 6

![image](https://user-images.githubusercontent.com/69178270/138389461-523d11db-9413-4a43-8893-4a996a668ddb.png)

Sau khi cài đặt xong một nagios server thì nó sẽ chỉ giám sát CPU; RAM; Disk,… tại nagios server. Để có thể giám sát được nhiều dịch vụ với các máy từ xa thì ta phải cài đặt thêm plugins.
