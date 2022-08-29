<img src="https://cdn.securityzone.vn/2021/04/2683_926f8bc84c8b2c72f6ca645c24886f35.png">

# Khái niệm
Công nghệ container hay đơn giản là container, là một cách đóng gói ứng dụng để nó có thể chạy với những tài nguyên của riêng nó và độc lập với các ứng dụng khác.
# Các đặc điểm của Container gồm:
- Lightweight: Các container chỉ sử dụng các thư viện cũng như môi trường cần thiết. Vì vậy việc khởi tạo 1 Container sẽ nhanh hơn việc khởi tạo một VM chỉ từ 5-10s.
- Portable: Bạn có thể chạy Container đó trên mọi nơi mà không cần quan tâm đến môi trường Server đã được cài đặt như thế nào. Chỉ cần biết Server đó có cài đặt Container Engine để chạy Container.
- Microservice: microservice là một khái niệm để mô tả các service nhỏ giao tiếp với nhau để tạo thành một ứng dụng hoặc service lớn.
- Bằng cách tách từng microservices, việc kiểm tra các dịch vụ nhỏ trở nên dễ dàng hơn, giảm các điểm lỗi đơn lẻ và tăng tốc độ phát triển.
# Một số thuật ngữ Container
- Docker: là công nghệ đầu tiên được biết đến khi tiếp cận đến Container. Docker là một trong những Container Engine được sử dụng phổ biến nhất. Docker hublà nơi chứa các container images để người dùng có thể sử dụng. Trong Docker sẽ có một số khái niệm như Dockerfile, Docker-compose.
  - Dockerfile: là file sẽ mô tả các bước xây dựng một container images. Xác định Images gốc sẽ sử dụng, quy định port Expose, môi trường sẽ được truyền vào,... tất cả sẽ được định nghĩa trong Dockerfile.
  - Docker-compose: là một công cụ để định nghĩa và chạy nhiều container của Docker cùng một lúc. Tất cả sẽ được định nghĩa trong file docker-compose và được định dạng theo kiểu dữ liệu YAML (YAML Ain't Markup Language) a.k.a yml.
- Kubernetes( k8s hoặc kube) : là một công nghệ điều phối, tự động hoá hệ thống Container được Google phát triển. Kubernetes có thể thực hiện việc kiểm tra sức khoẻ các Pod (Container) và thực hiện thay thế các Pod nếu cần thiết một cách tự động. Tuy nhiên hiện nay K8s không còn sử dụng Docker làm Container Engine nữa mà mặc định sử dụng Containerd để làm Container Engine chính từ bản 1.22
