# Project Setup Guide

## Các bước

1. Mở thư mục dự án.
2. Điều hướng đến thư mục backend:
    ```sh
    cd backend
    ```
3. Cài đặt các phụ thuộc của composer:
    ```sh
    composer install
    ```
    hoặc cập nhật các thành phần cụ thể của Symfony:
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
6. Sao chép `.env.example` thành `.env` và dán nội dung:
    ```sh
    cp .env.example .env
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

Thêm nội dung sau vào tệp `.env` của bạn:

