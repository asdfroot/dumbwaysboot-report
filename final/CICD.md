# CI/CD

## CI/CD

-   Melakukan proses instalasi jenkins dengan menggunakan docker di ansible kemudian jalankan dengan menggunakan `ansible-playbook` pada `setup-jenkins.yml`.

    docker-compose.yml

    ![gambar](assets/2je.png)

    setup-jenkins.yml

    ![gambar](assets/1je.png)

-   jika sudah bisa login, lalu install plugin Publish Over SSH

    ![gambar](assets/5je.png)

    Setup Publish over ssh

    ![gambar](assets/6setpubover.png)

-   Setup jenkins job

    Buat `freestyle project`, `Configure`, setup `source code management`

    ![gambar](assets/7setsourcecode.png)

    Setup build triggers

    ![gambar](assets/8setbuildtri.png)

    Setup build, dan `save`

    ![gambar](assets/9build.png)

    Test build

    ![gambar](assets/consolerunfront.png)

-   Setup GitHub Webhook

    Buka repository app Settings Masuk ke Webhook Tambahkan domain jenkins di Payload Url

    ![gambar](assets/10webh.png)

    coba lakukan perubahan direpository dan push kemudian cek apakah ada build terbaru terdeteksi oleh jenkins

    ![gambar](assets/updatered.png)
