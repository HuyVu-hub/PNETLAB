### THIẾT KẾ MẠNG CHO DOANH NGHIỆP

**Mô hình mạng**

![image](https://user-images.githubusercontent.com/69178270/143821595-c7373e18-cad1-4e2c-b9a3-e3a4116196ae.png)

**Web Server và Database**

Để tiện cho việc quản lý, và vận hành thì aaPanel là một sự lựa chọn hoàn hảo. aaPanel là một control panel miễn phí khá tốt, nó có thể quản lý server thông qua giao diện (GUI) đơn giản và chỉ với thao tác đơn giản thì đã có thể cài đặt được một web server chạy mô hình LNMP/LAMP. aaPanel ra đời  với mục đích giúp cho việc cài đặt, quản trị vps, server web trở nên đơn giản hơn. Từ đó giúp người dùng có nhiều thời gian để tập trung phát triển ứng dụng mà không cần quan tâm nhiều tới hệ thống.
Ngoài ra aaPanel còn tích hợp với Database nên ta có thể quản lý đồng thời Web Server cũng như Database trên một nền tảng.

![image](https://user-images.githubusercontent.com/69178270/143820488-57371e3b-1030-425d-add0-bb1c91186c70.png)

Ưu điểm của aaPanel:
 - 	Nhẹ, chỉ cần VPS Linux 512MB Ram là có thể sử dụng.
 - 	Cài đặt và sử dụng dễ dàng với vài cú click chuột.
 - 	Cho phép người dùng chỉnh sửa cấu hình PHP, Webserver trực tiếp trên giao diện.
 - 	Thư viện App Store giúp người dùng dễ dàng cài đặt Google Drive, Redis, Memcached…với một cú click chuột.
 - 	Quản lý tập tin với File Manager giao diện đẹp, hỗ trợ code editor rất tiện lợi.
 - 	Cấu hình bảo mật VPS, Webserver với một cú nhấp chuột.
 -	Hỗ trợ backup web lên FTP, Google Drive, Amazon S3,…
 -	Cộng đồng người dùng nhiều nên dễ dàng tìm thấy tài liệu hướng dẫn, hỗ trợ.

Chức năng của aaPanel:

Hiện tại aaPanel chỉ hỗ trợ những chức năng đơn giản mà bất kỳ panel nào cũng có như quản lý Web, FTP, Database, File.

Operating System hỗ trợ cũng khá đầy đủ là CentOS, Ubuntu, Debian, Fedora. Chú ý: Là OS phải mới và sạch sẽ (pure and clean) và chưa bao giờ cài đặt các enviroment hay software như php/apache/nginx/mysql.  Cấu hình tối thiểu có thể chạy được aaPanel là VPS có ram 128MB, CPU 1 core. Lời khuyên chạy ổn là  Ram 512MB và Panel này chỉ tốn 10Mb để vận hành.

_1. Web Server_

aaPanel cung cấp cho người dùng rất nhiều lựa chọn để dựng web server, và tất cả đều giao diện rất dễ sử dụng. Việc của người dùng chỉ cần chọn theo nhu cầu. Hầu hết aaPanel sẽ cung cấp cho người dùng rất nhiều công cụ miễn phí, tuy nhiên với sẽ có những phần mà người dùng phải trả phí.

![image](https://user-images.githubusercontent.com/69178270/143821630-401165d9-9ad7-4c13-a24c-2c6922a3c1be.png)

Khi ta tạo mới một web site, aaPanel hỗ trợ khởi tạo tự động dịch vụ cần thiết, cũng như database.

![image](https://user-images.githubusercontent.com/69178270/143821775-158c81d4-a8dd-4ad9-ad61-e5be78c282b2.png)

Ngoài ra, aaPanel còn cung cấp rất nhiều các tính năng khác hỗ trợ việc quản lý một web site.

![image](https://user-images.githubusercontent.com/69178270/143821795-a687b448-3fe3-4830-a738-1c9cc5c0e02d.png)

_2. Database._

Cũng tương tự như Web Site, việc quản lý Database cùng aaPanel cũng rất đơn giản. 

![image](https://user-images.githubusercontent.com/69178270/143821873-0c210f4c-0e79-43c8-abc3-e5f40ee5713d.png)

Để có thể quản lý chi tiết Database, ta dùng phpMyadmin được tích hợp sẵn.

![image](https://user-images.githubusercontent.com/69178270/143821892-5e35cf9b-6c35-46ee-bec8-f711633935e6.png)

**Tường lửa bảo vệ các vùng mạng**

Có rất nhiều bên cung cấp dịch vụ tường lửa, trong mô hình mạng này sử dụng tường lửa Checkpoint. Checkpoint cung cấp khả năng linh hoạt cho phép mở rộng và tích hợp thêm các công nghệ bảo mật hàng đầu trong cùng một thiết bị phù hợp với tài chính và nhu cầu của doanh nghiệp. Check Point cho phép nhận biết và ngăn chặn sâu ở mức ứng dụng. Thay vì chỉ theo giao thức và cổng như truyền thống. Bên cạnh đó, trong luồng xử lý của Firewall, gói tin sẽ được kiểm soát qua các engine về lọc malware inline, spyware, chặn khai thác lỗ hổng, lọc web, chặn file, chặn nội dung.

Các engine này hướng vào tính năng ngăn chặn hiệu quả. Do đó đều được thiết kế dạng mở gói tin một lần, lọc qua hết các engine, phân tích và chặn theo dạng luồng (thay vì phải lưu lại nội dung để đánh giá), giúp cho năng lực hệ thống khi bật toàn bộ tính năng an toàn lên luôn được ổn định.

![image](https://user-images.githubusercontent.com/69178270/143821953-da2445e4-b898-4bc4-b905-467376db4729.png)

Điểm nổi bật của thiết bị tường lửa.

 - 	Bảo mật không nhân nhượng: Cung cấp khả năng ngăn chặn mối đe dọa ở mức độ cao nhất với tính năng bảo vệ SandBlast Network Zero Day từng đoạt giải thưởng.
 - 	Bảo mật Hyperscale: Hiệu suất ngăn chặn mối đe dọa Hyperscale theo yêu cầu, cung cấp cho doanh nghiệp khả năng phục hồi trên cơ sở và mở rộng ở cấp độ đám mây.
 - 	Bảo mật thống nhất: Kiểm soát quản lý bảo mật thống nhất R81 trên các mạng, đám mây và IoT giúp tăng hiệu quả cắt giảm các hoạt động bảo mật lên đến 80%.

Bên cạnh đó, tường lửa Checkpoint cung cấp cho người dùng một giao diện quản lý với đầy đủ các chức năng, dễ dàng trong việc điều khiển, kiểm soát và vận hành.

Trong mô hình chỉ sử dụng một tường lửa để bảo vệ vùng mạng, tuy nhiên Firewall Manager có thể quản lý nhiều Firewall Gateway cùng một lúc.

![image](https://user-images.githubusercontent.com/69178270/143821997-e2bdf7a4-04ba-4db0-9499-eccc56bc08e4.png)

**Lưu trữ an toàn dữ liệu và dự phòng cao**

Để lưu trữ dữ liệu một cách an toàn và có tính dự phòng cao, quyết định sử dụng Freenas để áp dụng vào mô hình mạng này.

FreeNAS là một phần mềm hệ thống lưu trữ mạng (network-attached storage: NAS) mã nguồn mở miễn phí dựa trên hệ điều hành FreeBSD và hệ thống file OpenZFS. Nó được cấp phép theo 2 điều khoản của Giấy phép BSD và chạy trên phần cứng 64-bit. FreeNAS hỗ trợ các client Windows, OS X và Unix và nhiều máy chủ ảo hóa khác nhau như XenServer và VMware sử dụng CIFS, AFP, NFS, iSCSI, SSH, rsync và các giao thức TFTP/FTP. Tính năng nâng cao của FreeNAS bao gồm mã hóa toàn bộ ổ đĩa và một kiến trúc plug-in cho bên thứ ba.

![image](https://user-images.githubusercontent.com/69178270/143822047-d18c8cba-950e-4505-b772-5882645b2c46.png)

Tính năng thông dụng:

1. Chia sẻ File, Block, and Object.

FreeNAS cung cấp tính năng chia sẻ File, Block, and Object cho mọi hệ điều hành và cả nền tảng ảo hóa. Các giao thức được hỗ trợ bao gồm: Windows SMB, Apple AFP, Time Machine và Unix NFS, cũng như FTP và WebDAV. FreeNAS iSCSI hỗ trợ VMware VAAI, Microsoft ODX và Microsoft Windows Server Clustering.

2. Giao diện Web.

Mục tiêu của FreeNAS là đưa đến cho người dùng một trải nghiệm trên các tác vụ quản trị phức tạp bằng cách đơn giản nhất. Tất cả các vấn đề về cấu hình, quản lý đều có thể thực hiện thông qua giao diện web. FreeNAS giúp việc triển khai 1 hệ thống NAS trở nên đơn giản hơn bao giờ hết nhưng không làm ảnh hưởng đến người dùng và giải pháp lưu trữ của họ.

3. Snapshots.

Nhờ thiết kế copy-on-write của ZFS, các bạn có thể tạo snapshot theo thời gian. Các bạn có thể khôi phục dữ liệu cũ một cách nguyên vẹn từ snapshot đã được chụp trước đó.

Trong các hệ thống lưu trữ, các thành phần luôn được yêu cầu về sự ổn định như phần cứng, mạng,… để duy trì các dịch vụ hoạt động liên tục. Nói về máy chủ lưu trữ không thể nào không nhắc đến RAID. RAID được sử dụng để duy trì tính ổn định và đem lại hiệu năng cao. Có các loại RAID sau:

 - RAID 0
 -	RAID 1
 -	RAID 5
 -	RAID 6
 -	RAID 10
 -	RAID 50

Trong mô hình mạng này, ta sẽ áp dụng mô hình RAID 1 - Là loại RAID lưu dữ liệu song song trên 2 ổ cứng, 3 ổ cứng. Ưu điểm của loại này là tính dự phòng cao, tốc độ ghi dữ liệu là của 1 ổ cứng và tốc độ đọc gấp 2,3 lần ổ cứng đơn. Nhược điểm của loại này là tốn số lượng ổ cứng và giới hạn tốc độ ghi của 1 ổ cứng đơn.

![image](https://user-images.githubusercontent.com/69178270/143822156-c2c82977-a224-4c2f-a431-1a05b4284918.png)

Máy chủ Freenas sẽ gồm 3 ổ cứng. Một ổ cứng dùng để cài đặt hệ thống, 2 ổ cứng còn lại sẽ được dùng làm nơi lưu trữ cho nhân viên.

**Kết nối mạng có tính dự phòng cho khối máy chủ và nhân viên**

Để đảm bảo kết nối mạng có tính dự phòng, ta sử dụng công nghệ EtherChannel. 

EtherChannel là một kỹ thuật nhóm hai hay nhiều đường kết nối truyền tải dữ liệu vật lý (Link Aggregation) thành một đường ảo duy nhất (Logic) có Port ảo thậm chí cả MAC ảo nhằm mục đích tăng tốc độ truyền dữ liệu và tăng khả năng dự phòng (Redundancy) cho hệ thống.

Nếu một trong các link thuộc EtherChannel bị down thì traffic sẽ tự động được chuyển sang link khác trong channel chỉ trong vòng vài miliseconds. Khi link up trở lại thì traffic được phân bố lại như cũ.

_1. Điều kiện cấu hình EtherChannel_

Các Switch phải đều phải hỗ trợ kỹ thuật EtherChannel và phải được cấu hình EtherChannel đồng nhất giữa các Port kết nối với nhau.

Các Port kết nối EtherChannel giữa 2 Switch phải tương đồng với nhau:

 - Cấu hình (Configuration)
 - Tốc độ (Speed)
 - Băng thông (Bandwidth)
 -	Duplex (Full Duplex)
 -	Native VLAN và các VLANs
 -	Switchport Mode (Trunking, Access)

_2. Phân loại EtherChannel_

LACP (Link Aggregation Control Protocol):

Là giao thức cấu hình EtherChannel chuẩn quốc tế IEEE 802.3ad và có thể dùng được cho hầu hết các thiết bị thuộc các hãng khác nhau, LACP hỗ trợ ghép tối đa 16 Link vật lý thành một Link luận lý (8 Port Active – 8 Port Passive).

LACP có 3 chế độ:
 -	On: Chế độ cấu hình EtherChannel tĩnh, chế độ này thường không được dùng vì các Switch cấu hình EtherChannel có thể hoạt động được và cũng có thể không hoạt động được vì các Switch được cầu hình bằng tay phục thuộc vào con người nên hoàn toàn không có bước thương lượng trao đổi chính sách giừa bên dẫn đến khả năng Loop cao và bị STP Block.
 -	Active: Chế độ tự động – Tự động thương lượng với đối tác
 -	Passive: Chế độ bị động – Chờ được thương lượng

PAgP (Port Aggregation Protocol):

Là giao thức cấu hình EtherChannel độc quyền của các thiết bị hãng Cisco và chỉ hỗ trợ ghép tối đa 8 Link vật lý thành một Link luận lý.

PAgP cũng có 3 chế độ tương tự LACP:
 -	On
 -	Active
 -	Passive

**Hệ thống giám sát thiết bị mạng**

Để có thể quan sát hiệu năng thiết bị, mạng, … của các thiết bị mạng trong mô hình ta cần một hệ thống giám sát làm công việc này. Nhiệm vụ của hệ thống là quan sát và cung cấp thông tin để quản trị viên có thể dễ dàng kiểm soát và quản lý hệ thống.

Prometheus + Grafana chính là 2 công cụ hỗ trợ cực ký tốt cho việc kiểm soát và quản lý hệ thống.

Prometheus

Prometheus là giải pháp monitor hệ thống (open source). Prometheus dùng các trình daemon cài sẵn trên các máy con để thu thập các thông tin cần thiết, giao tiếp với máy chủ quản lý monitor qua giao thức HTTP/HTTPs và lưu trữ data theo dạng time-series database (TSDB).

Prometheus có hỗ trợ một giao diện web đơn giản để cho các admin theo dõi thông tin hệ thống, HTTP API và Prometheus còn cung cấp một ngôn ngữ truy vấn rất mạnh (sẽ nói ở phần dưới). Tuy nhiên, phần lưu trữ dữ liệu của prometheus hiện vẫn chưa tốt lắm.

Grafana

Grafana là một giao diện/dashboard theo dõi hệ thống (opensource), hỗ trợ rất nhiều loại dashboard và các loại graph khác nhau để người quản trị dễ dàng theo dõi.

Grafana có thể truy xuất dữ liệu từ Graphite, Elasticsearch, OpenTSDB, Prometheus và InfluxDB. Grafana là một công cụ mạnh mẽ để truy xuất và biểu diễn dữ liệu dưới dạng các đồ thị và biểu đồ.

![image](https://user-images.githubusercontent.com/69178270/143822797-891a50a8-9824-4ae2-baef-06c04753cad7.png)

Grafana cung cấp đầy đủ thông tin về Node, ta có thể tùy chỉnh thông số cần hiển thị.

![image](https://user-images.githubusercontent.com/69178270/143822822-35861917-f651-4b51-b8c7-a3d81bb2a879.png)

