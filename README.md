# Hướng dẫn Setup dự án || db_luxadecor dự án tốt nghiệp

## Lưu ý quan trọng

1. Không được thay đổi trực tiếp nhánh `main` nếu không có sự cho phép cụ thể.
2. Luôn cập nhật code mới nhất từ nhánh `base-v1` trước khi bắt đầu làm việc:
   ```sh
   git checkout base-v1
   git pull origin base-v1
   ```
3. Tạo nhánh mới cho mỗi tính năng hoặc sửa lỗi bạn đang làm việc.
4. Thông tin chi tiết về API và cách sử dụng Postman được chia sẻ trong nhóm Zalo của dự án.

## Các bước cài đặt

1. Clone dự án từ GitHub và chuyển sang nhánh base-v1:
   ```sh
   git clone https://github.com/hungvan93/funiture_system.git
   cd funiture_system
   git checkout base-v1
   git pull origin base-v1
   ```

2. Mở thư mục dự án.

3. Cài đặt các phụ thuộc của Composer:
   ```sh
   composer install
   ```
   Hoặc cập nhật các thành phần cụ thể của Symfony:
   ```sh
   composer update symfony/css-selector symfony/event-dispatcher symfony/string symfony/yaml symfony/console
   ```

4. Cài đặt các phụ thuộc của npm:
   ```sh
   npm install
   ```

5. Sửa các lỗ hổng npm:
   ```sh
   npm audit fix
   ```

6. Sao chép `.env.example` thành `.env`:
   ```sh
   cp .env.example .env
   ```
   Thêm nội dung sau vào tệp `.env` của bạn:
   ```env
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=db_luxadecor
   DB_USERNAME=root
   DB_PASSWORD="Phh123@#"
   ```

7. Tạo khóa ứng dụng:
   ```sh
   php artisan key:generate
   ```

8. Tạo bí mật JWT:
   ```sh
   php artisan jwt:secret
   ```

9. Chạy các lệnh di chuyển cơ sở dữ liệu:
   ```sh
   php artisan migrate
   ```

10. Để cài đặt và chạy frontend:
    ```sh
    cd frontend
    npm install
    npm run dev
    ```

## Chạy ứng dụng

- Để chạy API backend:
  ```sh
  php artisan serve
  ```

- Để tạo dữ liệu mẫu cho database:
  ```sh
  php artisan migrate:fresh --seed
  ```
  Lưu ý: Lệnh này sẽ xóa tất cả dữ liệu hiện có và tạo lại cấu trúc database cùng với dữ liệu mẫu. Chỉ sử dụng khi bạn muốn reset hoàn toàn database.

- Frontend đã được chạy bằng lệnh `npm run dev` ở bước 10.

## Quy trình làm việc

1. Trước khi bắt đầu làm việc, luôn pull code mới nhất từ nhánh base-v1:
   ```sh
   git checkout base-v1
   git pull origin base-v1
   ```

2. Tạo nhánh mới cho tính năng hoặc sửa lỗi của bạn:
   ```sh
   git checkout -b ten-nhanh-moi
   ```

3. Thực hiện các thay đổi và commit:
   ```sh
   git add .
   git commit -m "Mô tả về thay đổi của bạn"
   ```

4. Push nhánh của bạn lên repository:
   ```sh
   git push origin ten-nhanh-moi
   ```

5. Khi kết thúc công việc:
   a. Đảm bảo bạn đã commit và push tất cả các thay đổi lên nhánh của mình.
   b. Cập nhật nhánh của bạn với những thay đổi mới nhất từ base-v1:
      ```sh
      git checkout base-v1
      git pull origin base-v1
      git checkout ten-nhanh-moi
      git merge base-v1
      ```
   c. Giải quyết các xung đột (nếu có) và commit các thay đổi.
   d. Push lại nhánh của bạn:
      ```sh
      git push origin ten-nhanh-moi
      ```

6. Tạo Pull Request từ nhánh của bạn vào nhánh base-v1 trên GitHub:
   a. Truy cập repository trên GitHub.
   b. Chọn tab "Pull requests".
   c. Nhấn nút "New pull request".
   d. Chọn nhánh base-v1 làm nhánh cơ sở và nhánh của bạn làm nhánh so sánh.
   e. Điền tiêu đề và mô tả chi tiết cho pull request của bạn.
   f. Gán người review (nếu cần) và thêm các nhãn phù hợp.
   g. Nhấn "Create pull request" để hoàn tất.

7. Chờ đợi feedback và thực hiện các chỉnh sửa nếu cần thiết.

## Lưu ý quan trọng

1. Không được thay đổi trực tiếp nhánh `main` nếu không có sự cho phép cụ thể.
2. Luôn cập nhật code mới nhất từ nhánh `base-v1` trước khi bắt đầu làm việc:
   ```sh
   git checkout base-v1
   git pull origin base-v1
   ```
3. Tạo nhánh mới cho mỗi tính năng hoặc sửa lỗi bạn đang làm việc.
4. Thông tin chi tiết về API và cách sử dụng Postman được chia sẻ trong nhóm Zalo của dự án.
