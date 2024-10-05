# Hướng dẫn Cài đặt Dự án || db_luxadecor dự án tốt nghiệp

## Các bước

Clone dự án từ GitHub:
[https://github.com/hungvan93/funiture_system](https://github.com/hungvan93/funiture_system)

1. Mở thư mục dự án.

2. Cài đặt các phụ thuộc của Composer:

    ```sh
    composer install
    ```

    Hoặc cập nhật các thành phần cụ thể của Symfony:

    ```sh
    composer update symfony/css-selector symfony/event-dispatcher symfony/string symfony/yaml symfony/console
    ```

3. Cài đặt các phụ thuộc của npm:

    ```sh
    npm install
    ```

4. Sửa các lỗ hổng npm:

    ```sh
    npm audit fix
    ```

5. Sao chép `.env.example` thành `.env`:

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

6. Tạo khóa ứng dụng:

    ```sh
    php artisan key:generate
    ```

7. Tạo bí mật JWT:

    ```sh
    php artisan jwt:secret
    ```

8. Chạy các lệnh di chuyển cơ sở dữ liệu:

    ```sh
    php artisan migrate
    ```

9. Để chạy frontend:

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

- Frontend đã được chạy bằng lệnh `npm run dev` ở bước 9.

## Lưu ý

Thông tin về Postman có trong Zalo.
