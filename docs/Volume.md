[Docker] Một số hướng dẫn và ví dụ hữu ích về cách sử dụng Volume trong Docker

Volume trong Docker là một cơ chế được Docker sử dụng để cung cấp khả năng lưu trữ liên tục (persistent data storage)

1. Tạo volumes

docker volume create [volume_name]

Lệnh này sẽ tạo ra một volume lưu trữ dữ liệu có thể được sử dụng bởi một container cụ thể hoặc một được chia sẻ giữa một nhóm các container.

2. Hiển thị volumes

docker volume ls

3. Kiểm tra volunes

docker volume inspect [volume_name]

Lệnh kiểm tra docker volume sẽ cung cấp chúng ta thông tin chi tiết về một volume cụ thể. Nó hiển thị các thông tin về volume driver, mount point, scope hay labels (nhãn) của volume.

4. Xoá volumes.

docker volume rm [volume_name]

Ngoài ra, khi bạn có một số lượng volume rất lớn cần phải xoá đi thì docker daemon còn cung cấp cho bạn một lệnh rất hữu ích nữa đó là:

docker volume prune

Một điểm rất tốt ở lệnh này đó là nó sẽ không xoá đi bất cứ volume nào của bạn đang được sử dụng bởi một container hiện có. Nó sẽ chỉ xoá đi các volume đang không được sử dụng.

5. Tạo một container với volumes

Lệnh sau đây sẽ chỉ cho các bạn cách tạo một docker container và mount volume vào container này. Nếu volume liên kết không tồn tại sẵn thì Docker Engine sẽ tạo một volume mới:

Cách 1: Sử dụng tuỳ chọn --volume:

docker run --name [container_name] --volume "[volume_name]":/tmp [docker_image]

Cách 2: sử dụng tuỳ chọn --mount:

docker run --mount source=[volume_name],destination=[path_in_container] [docker_image]
