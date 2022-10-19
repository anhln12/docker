# Các khái niệm cần nắm

# Image
Image là 1 trong những đơn vị cơ bản nhất trong Docker. 1 Image sẽ định nghĩa cho 1 môi trường và những thứ có trong môi trường đó. Ứng dụng của ta muốn chạy được thì cần phải có Image

![image](https://user-images.githubusercontent.com/18412583/196581366-759e2425-df87-4779-9b1d-dd33e03be3c4.png)

Ví dụ trong Image ta có thể định nghĩa các thành phần như sau:
* Môi trường: Ubunti 16.04
* PHP 7.2
* MySQL 5.2

Thì toàn bộ những thứ bên trên (Ubuntu, PHP, MySQL) ta có thể đóng gói lại thành 1 Image. Có thể giữ làm của riêng hoặc public cho người khác có thể dùng được.

# Container
Một Container là 1 thực thể của Image. Cách hiểu đơn giản nhất đó là: Image các bạn xem như 1 class, còn Container xem như 1 Object được khởi tạo từ Class đó.

Từ một Image ta có thể khởi tạo cả chục, trăm container. Mỗi project có thể chứa 1 hoặc nhiều container được tạo ra từ 1 hoặc nhiều image. 

# Port
Vì môi trường trong Docker độc lập hoàn toàn so với môi trường gốc, nên để có thể sử dụng được ứng dụng chạy trong Docker thì ta cần mở port từ Docker để bên ngoài có thể gọi vào được.

Hay gọi đúng thì là "map port". Tức là sẽ mở 1 port ở hệ điều hành gốc, sau đó điều hướng tới port được mở ở trong Docker. Như thế ta mới có thể gọi đến ứng dụng chạy trong Docker được.

![image](https://user-images.githubusercontent.com/18412583/196582191-07ab1b39-1448-42ba-9ac4-ab3bb1b202b0.png)

Ở ảnh trên ta có một 1 server tomcat chạy trong 1 container mở port 8080 cho môi trường ngoài truy cập, từ môi trường ngoài ta mở cổng 8888 để user thật có thể truy vấn. Do đó user sẽ gọi đến cổng 8888 để giao tiếp với ứng dụng chạy trong Docker container.

# Volume
Vì môi trường Docker độc lập nên hệ thống file của ứng dụng chạy trong Docker cũng độc lập, mà thực tế thì hầu như ta luôn cần lưu lại file: lưu trữ DB, lưu trữ log, ảnh ... Do đó để môi trường gốc truy cập được vào file system của ứng dụng chạy trong Docker thì ta cần tới volume.

# Docker-compose
Khi chạy dự án thực tế thì hầu như ta sẽ sử dụng docker-compose để chạy project, vì thực tế hầu như ta luôn cần nhiều hơn 1 container cho 1 project. Docker-compose là tool để cấu hình và chạy nhiều docker container cùng lúc.

# Các kiến thức advance
Dockerfile, deploy lên k8s, openshift, exec vào pod debug, dockerize.

# Use Docker First - Then Learn About It Later (Dùng Docker trước, học về nó sau)
