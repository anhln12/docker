[Docker] Một số hướng dẫn và ví dụ hữu ích về cách sử dụng Volume trong Docker

Volume trong Docker là một cơ chế được Docker sử dụng để cung cấp khả năng lưu trữ liên tục (persistent data storage)

1. Tạo volumes
docker volume create [volume_name]
Lệnh này sẽ tạo ra một volume lưu trữ dữ liệu có thể được sử dụng bởi một container cụ thể hoặc một được chia sẻ giữa một nhóm các container.
