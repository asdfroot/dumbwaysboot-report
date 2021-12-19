# AWS Reverse-Proxy

## Update and upgrade system opration

-   Masuk pada server reverse proxy yang telah diuat `ssh -i helloaws.pem ubuntu@3.219.36.139`

    ![gambar 1](assets/1masukserver.png)

-   Setelah masuk maka lakukan Update dan upgrade `sudo apt update` dan `sudo apt upgrade -y`

    ![gambar 2](assets/2update.png)

    ![gambar 3](assets/upgradeserver2.png)

## Install Webserver Nginx

-   Untuk melakukan instal nginx cukup dengan perintah `sudo apt install nginx`

    ![gambar 4](assets/3installnginx.png)

## Reverse proxy aplikasi

-   Selanjutnya buka directory `cd /etc/nginx/` dan buat folder **dumbflix** dengan perintah `sudo mkdir dumbflix`

    ![gambar 5](assets/6buatcd.png)

-   Pada folder dumbflix buat file **syarif.onlinecamp.id** dengan perintah `sudo nano syarif.onlinecamp.id`

    ![gambar 6](assets/7buatnano.png)

    ![gambar 7](assets/8nanoisi.png)

-   Lalu pada directory `cd /etc/nginx` edit file **nginx.conf** lalu tambahkan config `Include /etc/nginx/dumbflix/*;`

    ![gambar 8](assets/9nanonginxconf.png)

    ![gambar 9](assets/10isiconfngix.png)

-   Cek syntax nginx `sudo nginx -t`

    ![gambar 10](assets/11ceksyntaxnginx.png)

-   Klik `Add record` isi **Type** `A`, isi **Nama** `syarif`, **IPv4 address** `3.219.36.139`dan matikan **Proxy status** lalu `Save`

    ![gambar 13](assets/15isisave.png)

-   Selanjutnya coba restart nginx `sudo systemctl restart nginx.service`

    ![gambar 14](assets/16restartnginx.png)

-   ketika sudah melakukan restart maka masukan `syarif.onlinecamp.id` pada web broser

    ![gambar 15](assets/17out.png)
