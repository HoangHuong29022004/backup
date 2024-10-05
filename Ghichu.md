# Git Configuration
```sh
git config --global user.email "huong.ph@fsofts.com"
```
```sh
git config --global user.name "huong.ph-visualweber"
```

# Change Ownership of /var/www

```sh
sudo chown -R $USER:$USER /var/www
```

# Hosting Account

- **Username:** hoanghuo
- **Password:** QV2!52pcpW@3lW

# Project Setup Guide

1. Open the project directory.
2. Navigate to the backend directory:
    ```sh
    cd backend
    ```
3. Install composer dependencies:
    ```sh
    composer install
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

# Company Accounts

## Mailbox

- **Service:** [Yandex Mail](https://mail.yandex.com)
- **Email:** huong.ph@fsofts.com
- **Password:** Welcome@20082024
- **Guide:** [Google Drive](https://drive.google.com/drive/folders/1_vECcxVyx2ishZKRHF8CfpNmbW5Ix8U9?usp=share_link)

## OpenVPN

- **Username:** huong.ph
- **Password:** Welcome@20082024
- **Guide:** [Google Drive](https://drive.google.com/drive/folders/1SFSfwoaFieBYiUq9b3-nhpyAA1bi2AkY?usp=share_link)

## GitLab

- **Service:** [GitLab](https://gitlab.com/huong.ph-visualweber)
- **Email:** huong.ph@fsofts.com
- **Password:** Welcome@20082024
- **Guide:** [YouTube](https://www.youtube.com/watch?v=lWpW6FxYPzE)

## OpenProject

- **Service:** [OpenProject](https://work.fsofts.com)
- **Email:** huong.ph@fsofts.com
- **Password:** (Check email to activate account)
- **Guides:**
  - [YouTube Guide 1](https://youtu.be/KHBgBI3HBFY)
  - [YouTube Guide 2](https://youtu.be/lWpW6FxYPzE)