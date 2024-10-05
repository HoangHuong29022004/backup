# Project Setup Guide || db_luxadecor dự án tốt nghiệp

## Các bước

Clone dự án từ GitHub:
[https://github.com/hungvan93/funiture_system](https://github.com/hungvan93/funiture_system)

1. Mở thư mục dự án.
2. Điều hướng đến thư mục backend:

    ```sh
    cd backend
    ```

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

## Cấu hình cơ sở dữ liệu
