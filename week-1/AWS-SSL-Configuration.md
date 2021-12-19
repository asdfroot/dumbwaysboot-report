# Install free SSL certificate for web server with let's encrypt

-   Masuk **cloudflare** terlebih dahulu.

    ![gambar 1](assets/1cloudlog.png)

-   Setelah masuk, kunjungi `My Profile` lalu `API Tokens`, pada tabel **API Keys** terdapat `Global API Key` dan klik `View`.

    ![gambar 2](assets/3global.png)

-   Jika muncul notifikasi **Your API Key** isi password dan Captha lalu `View`.

    ![gambar 3](assets/4robot.png)

-   Selanjutnya API Key akan keluar, simpan API Key.

    ![gambar 4](assets/5myapi.png)

-   Buat directory **.cloudflare** `sudo mkdir .cloudflare`.

    ![gambar 5](assets/6mkdir.png)

-   Pada directory **.cloudflare** buat file **api.key** `sudo nano api.key`.

    ![gambar 6](assets/7nanoapikey.png)

    ![gambar 7](assets/8nanoisikey.png)

-   Beri akses file **api.key** dengan perintah `sudo chmod 400 api.key`.

    ![gambar 8](assets/9chmod400.png)

-   Selanjutnya buka `certbot.eff.org` pada pilihan **My HTTP website is running** isi `Nginx` dan `ubuntu20`.

    ![gambar 9](assets/10certbot.png)

-   Lalu cek snap dengan perintah `sudo snap install core; sudo snap refresh core`.

    ![gambar 10](assets/11ceksnap.png)

-   Kemudian instal sertbot dengan perintah `sudo snap install --classic certbot`.

    ![gambar 11](assets/12installcertbot.png)

-   Lakukan perintah `sudo ln -s /snap/bin/certbot /usr/bin/certbot` agar menjalankan sertbot tanpa membuka directory **bin**.

    ![gambar 12](assets/13menjalankancertbottanpabin.png)

-   Jalankan certbot `sudo certbot`, jika muncul pertanyaan ketik saja `y` dan `n`. lalu pilih `1` karena cuma 1 yang meminta certifikat.

    ![gambar 13](assets/14sudocertbot.png)

-   Cek file `syarif.onlinecamp.id` pada directory `/etc/nginx/dumbflix/` apakah sudah bersertifikat.

    ![gambar 14](assets/15cekaertifikat.png)

-   Selanjutnya mencoba `https://syarif.onlinecamp.id` pada browser.

    ![gambar 15](assets/16out.png)
