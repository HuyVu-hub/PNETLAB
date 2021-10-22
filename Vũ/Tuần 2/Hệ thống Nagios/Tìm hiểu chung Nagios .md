### Tìm hiểu chung Nagios

[Giới thiệu chung](#1)

[Dịch vụ được cung cấp trong Nagios](#2)

[Nagios cung cấp cho bạn những gì?](#3)

[Nagios hoạt động như thế nào?](#4)

### <a name="1"> Giới thiệu chung </a>

![image](https://user-images.githubusercontent.com/69178270/138387571-5f4ef53a-0742-4e46-bf89-99fc98a7e60b.png)

Nagios là một hệ thống giám sát hạ tầng mạng và dịch vụ mạng vô cùng mạnh mẽ cho phép các doanh nghiệp, công ty xác định và giải quyết các vấn đề về cơ sở hạ tầng Công Nghệ Thông Tin trước khi chúng làm ảnh hưởng đến các hoạt động kinh doanh, vận hành nội bộ của công ty.

![image](https://user-images.githubusercontent.com/69178270/138387583-c8777cee-34e9-4c25-b17f-634ab5215abc.png)

Nagios là một ứng dụng phần mềm miễn phí và mã nguồn mở giám sát hệ thống, mạng và cơ sở hạ tầng. 
Hiện tại nhà phát triển chỉ hỗ trợ triển khai Nagios hệ thống trên Hệ Điều Hành Linux. 
Với Nagios bạn sẽ có thêm kênh giám sát và cảnh báo cho các máy chủ, switch, ứng dụng và dịch vụ.


### <a name="2"> Dịch vụ được cung cấp trong Nagios </a>

![image](https://user-images.githubusercontent.com/69178270/138387693-b034fd57-b82c-446f-89a3-ce027193568b.png)

Nagios có khả năng cung cấp một số dịch vụ cho bạn như sau :

+ Quản lý các dịch vụ mạng như là: SMTP, POP2, HTTP, NNTP, ICMP. SNMP, FTP, SSH.
+ Giám sát tài nguyên máy chủ như processor load, dung lượng đĩa đã sử dụng, nhật ký. Hệ thống trên phần lớn các hệ điều hành mạng, bao gồm Microsoft Windows, sử dụng các agent monitor.
+ Giám sát mọi phần cứng như nhiệt độ, báo động, v.v. có khả năng gửi dữ liệu thu thập được qua mạng tới các plugin cụ thể.
+ Giám sát từ xa bằng cách sử dụng Nagios Remote Plugin Executor hoặc thông qua SSH hoặc đường hầm SSL được mã hóa. Kiểm tra dịch vụ song song và nhật ký xoay vòng log tự động.
+ Hỗ trợ triển khai các máy chủ giám sát dự phòng, biểu đồ dữ liệu hiệu suất và phần phụ trợ cơ sở dữ liệu. Giao diện web để xem trạng thái mạng hiện tại, thông báo, lịch sử sự cố, các file log, v.v.

**CHÍNH SÁCH BẢN QUYỀN:** Nagios hiện cung cấp 2 phiên bản miễn phí và trả phí hỗ trợ các hệ thống nhỏ và cả các hệ thống doanh nghiệp.

**Nagios agents**

+ **NRPE** – Nagios Remote Plugin Executor
+ **NRDP** – Nagios Remote Data Processor
+ **NSClient++** – (program used to monitor Windows machines)
+ **NCPA** – Nagios cross Platform Agent
+ 
### <a name="3"> Nagios cung cấp cho bạn những gì? </a>

Nagios được thiết kế với khả năng mở rộng (scalability) và tính linh hoạt (flexible). Nagios mang đến cho bạn sự yên tâm khi biết rằng quá trình kinh doanh của tổ chức, doanh nghiệp sẽ không bị ảnh hưởng bởi các vấn đề sự cố liên quan đến hạ tầng Công Nghệ Thông Tin.

![image](https://user-images.githubusercontent.com/69178270/138387858-9028801e-7de0-43dd-9b1b-c6eac8ca1f69.png)

Nagios là một công cụ mạnh mẽ cung cấp cho bạn nhận thức tức thì về tầm quan trọng của cơ sở hạ tầng CNTT và việc giám sát nó. Nagios còn cho phép bạn phát hiện và sửa chữa các vấn đề hiện có và giảm thiểu các vấn đề trong tương lai trước khi chúng ảnh hưởng đến người dùng cuối và khách hàng hoặc là hệ thống nội bộ công ty.

**Sử dụng Nagios bạn có thể**

+ Lên kế hoạch nâng cấp cơ sở hạ tầng trước khi nó trở nên lỗi thời và thường xuyên gặp lỗi.
+ Tự động sửa lỗi khi phát hiện lỗi.
+ Phối hợp các với các hoạt động của nhóm kỹ thuật.
+ Đảm bảo SLA (Service-Level Agreement) của tổ chức đang áp dụng.
+ Đảm bảo sự cố cơ sở hạ tầng CNTT có tác động tối thiểu đến quá trình vận hành của tổ chức.
+ Giám sát toàn bộ cơ sở hạ tầng kinh doanh của bạn.
+ Dễ dàng phát triển các plug-in riêng. Cho phép người sử dụng dễ dàng phát triển các dịch vụ giám sát nhu cầu sử dụng bằng việc sử dụng các ngôn ngữ shell script, C ++, Perl, Ruby, Python, PHP, C# ….).
+ Việc giám sát các dịch vụ là song song.
+ Có khả năng phát hiện và phân biệt được host nào là down và host nào là unreachable.
+ Thông tin cảnh báo (khi host và các dịch vụ xảy ra xự cố) bằngemail, SMS sử dụng 3G, …
+ Sử dụng giao diện Web để theo dõi trạng thái của mạng, xem lịch sử các cảnh báo và các sự cố xảy ra.

### <a name="4"> Nagios hoạt động như thế nào? </a>

![image](https://user-images.githubusercontent.com/69178270/138387962-8ba348ff-06c9-410c-ae5b-f6a9e18c62f1.png)

**Monitoring (giám sát)**

Nhân viên CNTT cấu hình Nagios để giám sát các thành phần cơ sở hạ tầng CNTT quan trọng, bao gồm các chỉ số hệ thống (system metric), giao thức mạng, ứng dụng, dịch vụ, máy chủ và cơ sở hạ tầng mạng.

Alerting Nagios gửi thông báo khi các cơ sở hạ tầng quan trọng bị sự cố phát sinh (fail) và phục hồi hiện trạng (recovery), cung cấp hình thức giúp thông báo cho quản trị viên về các sự kiện quan trọng. Cảnh báo có thể được gửi qua email, SMS hoặc tập lệnh tùy chỉnh.

**Response (phản hồi)**

Nhân viên CNTT có thể xác nhận tình trạng xử lý các cảnh báo và bắt đầu giải quyết sự cố ngừng hoạt động cũng như điều tra cảnh báo bảo mật ngay lập tức. Cảnh báo có thể được chuyển đến các nhóm khác nhau nếu cảnh báo không được công nhận một cách kịp thời.

**Reporting (báo cáo)**

Nagios có thể báo cáo cung cấp hồ sơ lịch sử về sự cố ngừng hoạt động, sự kiện, thông báo và các phản hồi cảnh báo để xem xét sau. Báo cáo tính khả dụng giúp đảm bảo thời gian SLA (Service-Level Agreement) của bạn đang được đáp ứng .

**Maintenance (bảo trì)**

Thiết lập thời gian ngừng hoạt động (bảo trì) theo lịch trình giúp ngăn cảnh báo nhận được trong thời gian này.

**Planning (lập kế hoạch)**

Biểu đồ, báo cáo về xu hướng và khả năng lập kế hoạch cho phép bạn xác định các đối tượng nâng cấp cơ sở hạ tầng cần thiết trước khi xảy ra lỗi.
