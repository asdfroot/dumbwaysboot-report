# Auth

## AUTH

-   Install apache2-utils di server Nginx

    ![gambar](assets/1au.png)

-   Buat direktori untuk menyimpan file password yang dibuat. Lalu buat password untuk user admin (bisa disesuaikan).

    ![gambar](assets/2au.png)

-   Tambahkan rules authencation di file config reverse proxy.

    ![gambar](assets/3au.png)

-   Test konfig `sudo nginx -t` restart nginx `sudo systemctl restart nginx`.

    ![gambar](assets/4au.png)

-   lalu akses domain dengan browser.

    ![gambar](assets/5au.png)
