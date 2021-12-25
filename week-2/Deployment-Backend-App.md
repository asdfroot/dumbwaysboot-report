# DEPLOYMENT BACKEND

## Clone Repository

-   Login ke server backend

-   Clone aplikasi backend

        git clone git@github.com:asdfroot/dumbflix-backend.git

    ![gambar 1](assets/7gitclone.png)

-   Instal node.js 14.x

        curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash

        nvm install 14

        nvm use 14

    ![gambar 2](assets/21curlnvm.png)

    ![gambar 3](assets/22nvm14.png)


-   Copy file .env

        cp .env.example .env

    ![gambar 4](assets/31copyenv.png)

-   Sesuaikan **deployment** dengan server database seperti **username**, **password**, **database** dan **host**

        sudo nano dumbflix-backend/config/config.json

    ![gambar 5](assets/20.png)

## Import database with sequelize

-   Instal sequelize

        npm install --save-dev -g sequelize-cli

    ![gambar 6](assets/23squelize.png)

-   Instal modules dan package yang dibutuhkan

        npm install

    ![gambar 7](assets/24npminstall.png)

-   Selanjutnya lakukan migrate database

        sequelize db:migrate

    ![gambar 8](assets/26sequelizemigrate.png)

## Change directory to **backend** and deploy the application

-   Jalankan aplikasi

        pm2 start ecosystem.config.js

    ![gambar 9](assets/27startapp.png)
