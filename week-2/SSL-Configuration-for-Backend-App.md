# SSL CONFIGURATION

## applications can access from **https:**

-   Login ke server gateway

-   Lakukan konfigurasi SSL untuk subdomain `api.syarif.onlinecamp.id` menggunakan certbot

    >sudo certbot certonly -d api.syarif.onlinecamp.id

    ![gambar 1](assets/7buatsertifikat.png)

-   Login ke server frontend

-   Lalu edit baris baseURL pada api.js diaplikasi frontend

    >sudo nano dumbflix-frontend/src/config/api.js

    ![gambar 1](assets/2isinanoapijs.png)

-   Kemudian mulai ulang aplikasi

    >pm2 restart all

    ![gambar 2](assets/3restart.png)

-   Buka browser dan masukan URL backend apakah konfigurasi SSL berhasil

    >api.syarif.onlinecamp.id

    ![gambar 2](assets/10cannot.png)

-   Coba Login pada aplikasi

    ![gambar 2](assets/loglog.png)   

    ![gambar 2](assets/outout.png)
