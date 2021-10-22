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

![image](https://user-images.githubusercontent.com/69178270/138389036-fa36955e-e34f-46c7-a949-dfccf2995fd3.png)

- Bước 1: Client sẽ sử dụng giao thức http để tạo yêu cầu thông tin website cho nagios server
- Bước 2: Web server sẽ sử dụng CGI để lấy thông tin từ nagios server
- Bước 3: Nagios server sẽ xem lại file cache. Nếu trong đó có thông tin mà client yêu cầu thì nó sẽ lập tức trả lại kết quả. Nếu không có nagios sẽ tạo ra một plugins để kiểm tra lại thông tin mà client yêu cầu
- Bước 4: Plugins sẽ check thông tin theo yêu cầu và sau đó trả lại thông tin lại cho nagios server
- Bước 5: Sau khi được nhận thông tin từ plugins thì nagios server sẽ lưu trữ thông tin đó vào một file hoặc một DB do cài đặt của người quản trị. Và đồng thời nó sẽ lưu trữ thông tin này vào file cache nếu người quản trị có sử dụng chức năng của file này
- Bước 6: Nagios sẽ xác định những việc phải làm dựa trên thông tin được trả về từ nagios. Có cần cảnh báo hay không và đánh giá trạng thái của các host hay service. Rồi sau đó trả lại thông tin cho webserver
- Bước 7: Web server sẽ sử dụng lại giao thức http trả lại thông tin mà client yêu cầu.
