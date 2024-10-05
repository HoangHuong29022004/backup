# Project Setup Guide

## Steps

1. Open the project directory.
2. Navigate to the backend directory:
    ```shs
    cd backend
    ```
3. Install composer dependencies:
    ```sh
    composer install
    ```
    or update specific Symfony components:
    ```sh
    composer update symfony/css-selector symfony/event-dispatcher symfony/string symfony/yaml symfony/console
    ```
4. Install npm dependencies:
    ```sh
    npm install
    ```
5. Fix npm vulnerabilities:
    ```sh
    npm audit fix
    ```
6. Copy `.env.example` to `.env` and paste the content:
    ```sh
    cp .env.example .env
    ```
7. Generate application key:
    ```sh
    php artisan key:generate
    ```
8. Generate JWT secret:
    ```sh
    php artisan jwt:secret
    ```
9. Run database migrations:
    ```sh
    php artisan migrate
    ```

## Database Configuration

Add the following to your `.env` file:

