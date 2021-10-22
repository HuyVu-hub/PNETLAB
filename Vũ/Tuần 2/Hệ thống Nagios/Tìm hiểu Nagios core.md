### Nagios core

### Mục lục

[Plugins](#1)

[Web server](#2)

[DATABASE (DB)](#3)

[CGI (Common Gateway Interface)](#4)

[Ưu điểm và nhược điểm của Nagios core](#5)

[Luồng hoạt động của Nagios core](#6)

### <a name="1"> Plugins </a>

- Là một lớp trừu tượng giữa nagios server và host hay service
- Là một dòng lệnh hay có thể là một đoạn script
- Plugins có chức năng kiểm tra host và service rồi trả lại kết quả cho nagios server.

### <a name="2"> Web server </a>

![image](https://user-images.githubusercontent.com/69178270/138388818-100e84a6-3246-4dce-a5bb-6c2677417eee.png)

- Là nơi lưu trữ các file, các thành phần của website (file html, css, ảnh,...)
- Là nơi cung cấp dữ liệu của website cho người dùng muốn truy cập và sử dụng. Nó sẽ cung cấp dữ liệu cho người dùng thông qua Internet.

### <a name="3"> DATABASE (DB) </a>

- DB bao gồm DATA và DBMS
- DATA: Là loại dữ liệu của nagios server. Dữ liệu này là thông tin của các client sau khi được kiểm tra
- DBMS là hệ quản trị cơ sở dữ liệu. Được thiết kế nhằm mục đích quản lý dữ liệu dễ dàng hơn, bảo mật cao hơn. Theo mặc định thì DATA của nagios server sẽ được lưu trữ trong file nhưng có thể lưu trữ nó ở trong một hệ quản trị cơ sở dữ liệu.
- Trên DB người dùng sẽ dễ dàng thao tác với dữ liệu được lưu trữ trong file
- Trong nagios có hỗ trợ 2 DB là mysql và postgreSQL.

### <a name="4"> CGI (Common Gateway Interface) </a>

![image](https://user-images.githubusercontent.com/69178270/138388854-cac80f92-14b6-46d8-bb3f-5ab5f42413c0.png)

- CGI hay còn được gọi là giao diện dòng lệnh nó cung cấp giao thức để web server sử dụng.
- Web Server thường gửi thông tin biểu mẫu cho một quy trình xử lý dữ liệu và có thể gửi lại thông báo xác nhận. Quá trình đó được gọi là CGI.
- CGI có thể được viết nên từ ngôn ngữ nào đó như: C, perl, shell,...

### <a name="5"> Ưu điểm và nhược điểm của Nagios core </a>

- Ưu điểm:

  ●	Là một phần mềm mã nguồn mở và miễn phí
  
  ●	Giám sát tập trung
  
  ●	Có thể tích hợp được nhiều ngôn ngữ khác nhau
  
  ●	Có một cộng đồng phát triển plugins lớn, vì vậy có rất nhiều các plugins đã có sẵn.

- Nhược điểm:

  
  ●	Giao diện đồ họa lâu đời
  
  ●	Không có khả năng tự phát hiện host khi được thêm vào. Người quản trị sẽ phải cấu hình thủ công tất cả các host và các service. Việc này ảnh hưởng đến khả năng mở rộng quy mô khó khăn.

### <a name="6"> Luồng hoạt động của Nagios core </a>
