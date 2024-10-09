Để reload cấu hình daemon.json của Docker, bạn cần thực hiện các bước sau:

1. Chỉnh sửa file daemon.json

File cấu hình của Docker: /etc/docker/daemon.json

Thêm hoặc chỉnh sửa các tùy chọn cấu hình:
```
{
  "log-driver": "json-file",
  "log-opts": {
    "max-size": "10m",
    "max-file": "3"
  }
}
```
