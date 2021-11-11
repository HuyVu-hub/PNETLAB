### Duy trì hoạt động Server Pnetlab, cài đặt lại hoặc reset hệ thống khi có sự cố

Ta sẽ sử dụng Rclone để back up dữ liệu của PNETlab lên Drive

**B1:** Cài đặt Rclone

![image](https://user-images.githubusercontent.com/69178270/141223330-55f131a9-251a-49c3-8c4f-1811f78faf82.png)

![image](https://user-images.githubusercontent.com/69178270/141223337-ce0ff273-00ee-4b14-9c2a-4c755b9c99b4.png)

![image](https://user-images.githubusercontent.com/69178270/141223344-1d0c6a2e-8a2d-4202-adb3-c9d0b97c656c.png)

**B2:** Backup dữ liệu lên Cloud với Rclone

Tạo kết nối với Google Drive

- Đầu tiên ta sẽ cấu hình kết nối Rclone với Google Drive, việc này chỉ phải làm 1 lần duy nhất, Kết nối được tạo tên pnetlab

- Kết nối SSH với PNET rồi chạy lệnh:
	rclone config

- Sau đó nhận được thông báo: No remotes found - make a new one, nhập n rồi nhấn Enter để tạo kết nối mới

![image](https://user-images.githubusercontent.com/69178270/141223414-77cbef5a-b525-4edf-9725-998be6b782ce.png)

- Ở dòng name bạn nhập remote để đặt tên cho kết nối, bạn có thể chọn tên nào cũng được

![image](https://user-images.githubusercontent.com/69178270/141223450-a785bce8-b521-4492-bd95-d2afc54bc957.png)

- Một danh sách các dịch vụ cloud xuất hiện, hãy chọn số 15, Google Drive rồi nhấn Enter.

![image](https://user-images.githubusercontent.com/69178270/141223464-f68eb197-4267-4a17-a69f-b1c6b2dd269f.png)

![image](https://user-images.githubusercontent.com/69178270/141223482-59f8c45d-ac6a-442e-a315-242620fc16ad.png)

- Ở 2 dòng tiếp theo Client ID và Client Secret bạn hãy để trống nhấn Enter

![image](https://user-images.githubusercontent.com/69178270/141223511-da735dd3-36d8-4226-86a2-5bde765bb07e.png)

- Mục Scope that rclone should use when requesting access from drive chọn 1 - drive

![image](https://user-images.githubusercontent.com/69178270/141223542-0c8d4e81-633e-496f-8639-677554a5e09c.png)

- Tiếp theo, để trống với ID of the root folder và Service Account Credentials JSON file path

![image](https://user-images.githubusercontent.com/69178270/141223583-fd5f45b1-bfbb-44ff-94ee-c0fb3fe592eb.png)

- Khi được hỏi Use auto config? hãy nhập n rồi nhấn Enter. Ngay lập tức, Rclone sẽ đưa ra 1 đường link, ta có thể click thẳng vào đó hoặc copy rồi paste vào trình duyệt

![image](https://user-images.githubusercontent.com/69178270/141223649-b0b61345-22ed-4af9-9ca2-24a42797c6b3.png)

![image](https://user-images.githubusercontent.com/69178270/141223659-dc5a85bc-60a4-4e72-9d76-2cf7000a20ed.png)

![image](https://user-images.githubusercontent.com/69178270/141223666-44013641-06ae-4264-baad-9ec04a9eb9a0.png)

![image](https://user-images.githubusercontent.com/69178270/141223681-93da5950-41ae-4afc-8742-19ad3e3afd7a.png)

- Chọn n tức no đối với Configure this as a team drive

![image](https://user-images.githubusercontent.com/69178270/141223703-4c3a8c26-62e2-4f2d-a4d9-d5070548a983.png)

- Rclone xác nhận thông tin một lần nữa, bạn nhấn y để đồng ý rồi nhấn q để thoát khỏi giao diện cấu hình kết nối

![image](https://user-images.githubusercontent.com/69178270/141223725-8d203dbe-0050-4ca2-adf4-e9c88f0ec192.png)

- Vậy là xong, giờ bạn có thể test với lệnh liệt kê thư mục trong kết nối remote
	rclone lsd remote:

![image](https://user-images.githubusercontent.com/69178270/141223745-176daf34-6576-4310-8263-29e6df2bbc19.png)

**B3:** Script backup toàn bộ PNETlab và upload lên Cloud

```
vi /root/backup.sh
	#!/bin/bash
cwd=$(pwd)
SERVER_NAME=Pnetlab
REMOTE_NAME=pnetlab
DATE=`date +%Y-%m-%d`
TIMESTAMP=$(date +%F)
BAK_DIR=/data-backup/
BACKUP_DIR=${BAK_DIR}/${TIMESTAMP}
MYSQL_USER="root"
MYSQL=/usr/bin/mysql
MYSQL_PASSWORD=pnetlab
Mysqldump=/usr/bin/mysqldump
rclone=/usr/sbin/rclone

SECONDS=0
exec >$BAK_DIR/logs/${DATE}.log
exec 2>&1

mkdir -p "$BACKUP_DIR/mysql"

echo "Starting Backup Database";
databases=`$MYSQL -u $MYSQL_USER -p$MYSQL_PASSWORD -e "SHOW databases;" | grep -Ev "(Database |information_schema | performance_schema | mysql | sys)" `

for db in $databases; do
echo ${db}
$Mysqldump -u $MYSQL_USER -p$MYSQL_PASSWORD --databases $db --quick --lock-tables=false | gzip> "$BACKUP_DIR/mysql/$db.gz"
done
echo "Finished";
echo '';

echo "Starting Backup Website";
mkdir -p $BACKUP_DIR/data
domain=${D##*/} # Domain name
echo "-" $domain;
zip -r -y -q $BACKUP_DIR/data/$TIMESTAMP.zip /var/www/html/  #Exclude cache
#fi
#done
echo "Finished";
echo '';

echo "Starting compress file";
size1=$(du -sh ${BACKUP_DIR} | awk '{print $1}')
cd ${BAK_DIR}
tar -czf ${TIMESTAMP}".tgz" $TIMESTAMP
cd $cwd
size2=$(du -sh ${BACKUP_DIR}".tgz"| awk '{print $1}')
rm -rf ${BACKUP_DIR}
echo "File compress from "$size1" to "$size2
echo "Finished";
echo '';

echo "Starting Backup Uploading";
$rclone copy ${BACKUP_DIR}.tgz "$REMOTE_NAME:/$SERVER_NAME/"
#$rclone -q delete --min-age 1m "$REMOTE_NAME:/$SERVER_NAME" #remove all backups older than 1 week
find ${BAK_DIR} -mindepth 1 -mtime +6 -delete
echo "Finished";
echo '';

duration=$SECONDS
echo "Total $size2, $(($duration/60)) minutes and $(($duration%60)) seconds elapsed."
```

![image](https://user-images.githubusercontent.com/69178270/141223830-c0e571ed-130a-4064-8d9e-4b1e52762b8d.png)

![image](https://user-images.githubusercontent.com/69178270/141223845-73ce917f-950e-43e9-8b0e-cd189dbf7ca4.png)

![image](https://user-images.githubusercontent.com/69178270/141223854-ea6f50a5-3bf2-474d-9622-5a7cffbac6a7.png)

![image](https://user-images.githubusercontent.com/69178270/141223861-accd0862-8f8b-4386-be08-59eea82e3fc1.png)

Sau đó thực hiện backup và kiểm tra thử:

```
  /root/backup.sh
	rclone lsl pnetlab:Pnetlab
```

![image](https://user-images.githubusercontent.com/69178270/141223899-7a4f3e1b-6fd6-438f-b6ec-3dce529d23d6.png)

**B4:** Tạo cronjob tự động backup hàng ngày

- Giờ ta sẽ cho script tự động chạy lúc 2h00 sáng
	crontab -e

![image](https://user-images.githubusercontent.com/69178270/141224466-ced01e78-2680-4e10-879e-bff8347ad1bd.png)

Sau đó thêm nội dung sau

```
0 2 * * * /root/backup.sh > /dev/null 2>&1
```

![image](https://user-images.githubusercontent.com/69178270/141224527-2bbcbac9-4ac0-4cf5-9f46-5044a95540e3.png)

Vậy là xong, cứ 2h sáng hàng ngày script sẽ tự động chạy, backup toàn bộ dữ liệu của PNETlab rồi upload lên Cloud. Đồng, thời dữ liệu backup trên PNETlab sẽ được xóa luôn sau khi upload xong.

**B5:** Tải file backup từ Cloud xuống PNETlab

- Cách đơn giản nhất để khôi phục dữ liệu đó là tải file backup từ Cloud xuống máy tính, rồi tùy theo nhu cầu mà up trở lại trên PNETlab. Tuy nhiên, nếu muốn tải trực tiếp file backup về PNETlab, ta có thể sử dụng luôn Rclone với câu lệnh copy

```
rclone copy "pnetlab:/Pnetlab/2021-10-21.tgz" /root/ 
```

![image](https://user-images.githubusercontent.com/69178270/141224616-2729b664-805d-4cd0-b992-0299b0967bd7.png)

Lệnh trên sẽ copy thư mục 2021-10-19 trong thư mục data trên Cloud về thư mục /root/ của PNETlab. Tốc độ upload và download từ Cloud đều rất nhanh.
	Sau khi copy dữ liệu backup về PNETlab, ta tiến hành giải nén file zip, copy thư mục web và nginx về đúng vị trí đồng thời tiến hành import database.

**Tài liệu tham khảo**

https://vietcalls.com/huong-dan-dung-rclone-backup-du-lieu-len-google-drive/

https://hocvps.com/rclone/#script-2-voi-hocvps-script-phien-ban-1-8-tro-xuong-hoac-he-quan-tri-khac
