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

## Hướng dẫn tạo SSH key và thêm vào tài khoản GitHub

1. Tạo SSH key:
   ```sh
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   ```
   Thay thế "your_email@example.com" bằng địa chỉ email bạn sử dụng cho GitHub.

2. Khi được nhắc "Enter a file in which to save the key," nhấn Enter để chấp nhận vị trí file mặc định.

3. Nhập mật khẩu cho SSH key khi được yêu cầu (hoặc để trống nếu bạn không muốn sử dụng mật khẩu).

4. Thêm SSH key vào ssh-agent:
   ```sh
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_rsa
   ```

5. Sao chép SSH key vào clipboard:
   - Trên macOS:
     ```sh
     pbcopy < ~/.ssh/id_rsa.pub
     ```
   - Trên Linux:
     ```sh
     xclip -sel clip < ~/.ssh/id_rsa.pub
     ```
   - Trên Windows (PowerShell):
     ```sh
     cat ~/.ssh/id_rsa.pub | clip
     ```

6. Thêm SSH key vào tài khoản GitHub:
   a. Đăng nhập vào GitHub.
   b. Nhấp vào ảnh hồ sơ của bạn, sau đó chọn "Settings".
   c. Trong thanh bên trái, chọn "SSH and GPG keys".
   d. Nhấp vào "New SSH key" hoặc "Add SSH key".
   e. Trong trường "Title", thêm một mô tả cho key (ví dụ: "Personal Laptop").
   f. Dán key của bạn vào trường "Key".
   g. Nhấp "Add SSH key".
   h. Xác nhận bằng mật khẩu GitHub của bạn nếu được yêu cầu.

7. Kiểm tra kết nối:
   ```sh
   ssh -T git@github.com
   ```
   Nếu bạn thấy thông báo "Hi username! You've successfully authenticated, but GitHub does not provide shell access.", điều đó có nghĩa là bạn đã thiết lập thành công SSH key.

Sau khi hoàn thành các bước trên, bạn có thể sử dụng URL SSH để clone và push các repository GitHub mà không cần nhập username và password mỗi lần.

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
      DB_HOST=103.169.35.190
      DB_PORT=3306
      DB_DATABASE=db_luxadecor
      DB_USERNAME=db_luxadecor
      DB_PASSWORD="QV2!52pcpW@3lW"
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

6. Tạo Pull Request từ nhánh của bạn vào nhánh base-v1 trên GitHub.

7. Chờ đợi feedback và thực hiện các chỉnh sửa nếu cần thiết.
