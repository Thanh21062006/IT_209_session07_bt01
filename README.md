# Bài 1: Quản lý người dùng giới hạn và Truyền tải dữ liệu qua SFTP trên Windows

## 1. Các lệnh đã thực hiện trên VPS

```bash
# Khởi tạo tài khoản người dùng sftp-user
sudo adduser sftp-user

# Tạo thư mục log giả lập
sudo mkdir -p /var/log/app-backup/

# Tạo file log
sudo touch /var/log/app-backup/backup-check.log

# Ghi nội dung vào file
sudo bash -c 'echo "Backup status: SUCCESS at $(date)" > /var/log/app-backup/backup-check.log'

# Phân quyền cho thư mục và file
sudo chown -R root:sftp-user /var/log/app-backup
sudo chmod 750 /var/log/app-backup
sudo chmod 640 /var/log/app-backup/backup-check.log
```

## 2. Kết quả kiểm tra trên VPS

```bash
id sftp-user
```
*(Chụp ảnh màn hình hoặc dán kết quả lệnh id sftp-user tại đây)*

```bash
ls -l /var/log/app-backup/backup-check.log
```
*(Chụp ảnh màn hình hoặc dán kết quả lệnh ls -l tại đây)*

## 3. Ảnh chụp màn hình kết nối SFTP trên Windows và tải file thành công
*(Chèn ảnh chụp màn hình Bitvise SSH Client / WinSCP đã kết nối thành công và kéo thả file backup-check.log về máy cục bộ)*
