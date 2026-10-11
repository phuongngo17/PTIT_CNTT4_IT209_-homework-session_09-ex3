\# Bài 3: Đóng gói trang HTML tĩnh bằng Docker



\## 1. Mục tiêu



Tạo Docker Image sử dụng Nginx Alpine để triển khai một trang HTML tĩnh trên cổng 8081.



\## 2. Cấu trúc thư mục



```text

ex3/

├── Dockerfile

├── index.html

└── README.md

```



\## 3. Nội dung index.html



```html

<h1>Hello Docker Session 09!</h1>

```



\## 4. Nội dung Dockerfile



```dockerfile

FROM nginx:alpine

COPY index.html /usr/share/nginx/html/index.html

```



\## 5. Các bước thực hiện



\### Bước 1: Build Docker Image



```bash

docker build -t my-html-app:v1 .

```



\### Bước 2: Kiểm tra Docker Image



```bash

docker images

```



\### Bước 3: Chạy Docker Container



```bash

docker run -d -p 8081:80 --name html-app my-html-app:v1

```



\### Bước 4: Kiểm tra Container



```bash

docker ps

```



Container `html-app` đã được khởi chạy với trạng thái `Up`, ánh xạ cổng `8081:80`.



\### Bước 5: Kiểm tra trang Web



```bash

curl http://localhost:8081

```



Kết quả mong đợi:



```html

<h1>Hello Docker Session 09!</h1>

```



Truy cập trình duyệt tại http://localhost:8081.



\## 6. Kết luận



Đã build thành công Docker Image `my-html-app:v1` và khởi chạy container `html-app` sử dụng Nginx Alpine trên cổng 8081. Cần xác nhận kết quả `curl` để hoàn tất kiểm thử nội dung trang web.

