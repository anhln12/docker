Để reload cấu hình daemon.json của Docker, bạn cần thực hiện các bước sau:

1. Chỉnh sửa file daemon.json

File cấu hình của Docker thường nằm tại: /etc/docker/daemon.json.

Nếu file chưa tồn tại, bạn có thể tạo mới nó bằng lệnh:
```
sudo nano /etc/docker/daemon.json
```

Thêm hoặc chỉnh sửa các tùy chọn cấu hình, ví dụ:
```
{
  "log-driver": "json-file",
  "log-opts": {
    "max-size": "10m",
    "max-file": "3"
  }
}
```

Lưu file sau khi chỉnh sửa.


Để reload cấu hình daemon.json của Docker, bạn cần thực hiện các bước sau:

1. Chỉnh sửa file daemon.json
File cấu hình của Docker thường nằm tại: /etc/docker/daemon.json.

Nếu file chưa tồn tại, bạn có thể tạo mới nó bằng lệnh:

bash
Sao chép mã
sudo nano /etc/docker/daemon.json
Thêm hoặc chỉnh sửa các tùy chọn cấu hình, ví dụ:
{
  "log-driver": "json-file",
  "log-opts": {
    "max-size": "10m",
    "max-file": "3"
  }
}
Lưu file sau khi chỉnh sửa.

2. Reload Docker Daemon

Sau khi chỉnh sửa file daemon.json, bạn cần reload lại Docker để áp dụng các thay đổi.

Chạy lệnh sau để reload cấu hình:
```
sudo systemctl daemon-reload
```

Sau đó, restart Docker để các thay đổi trong daemon.json có hiệu lực:
```
sudo systemctl restart docker
```

Lệnh daemon-reload sẽ thông báo cho hệ thống biết rằng cấu hình hệ thống đã thay đổi và systemctl restart docker sẽ khởi động lại dịch vụ Docker với cấu hình mới.

3. Kiểm tra trạng thái Docker
```
sudo systemctl status docker
```
Lưu ý:

Nếu có lỗi trong file daemon.json, Docker sẽ không khởi động được sau khi reload. Hãy kiểm tra lại cú pháp JSON cẩn thận trước khi khởi động lại Docker.

Đảm bảo sao lưu file cấu hình daemon.json trước khi thực hiện bất kỳ thay đổi nào.
