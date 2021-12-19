# AWS Create and Setup server

## Server untuk Reverse Proxy

-   Buka awseducate `https://www.awseducate.com/signin/SiteLogin` dan `Sign In`.

    ![gambar 1](assets/loginaws.png)

-   Buka My Classrooms lalu klik `Go to classroom`, jika ada notif Confrim pilih saja `Continue`.

    ![gambar 2](assets/classroom.png)    

    ![gambar 3](assets/2continue.png)

-   Jika diarahkan pada link `labs.vocareum.com` pilih saja `AWS Console`.

    ![gambar 4](assets/3awsconsole.png)    

-   Jika sudah masuk `console.aws.amazon.com` pada bagian **Build a solution** klik saja `Launch a virtual machine`.

    ![gambar 5](assets/4lounchvirtual.png)

-   Pada **Choose an Amazon Machine Images (AMI)** cari **Ubuntu** lalu pilih **Server 20.04 LTS 64-bit x86** dan klik `Select`.

    ![gambar 6](assets/cariubuntu.png)

-   Pada **Choose an Instance Type** pilih **t2.micro** dan klik `Next: Configure Instance Details`

    ![gambar 7](assets/t2micro.png)

-   Pada **Configure Instance Details** isi `1` pada **Number of Instances** lalu `Disable` pada **Auto-assign Public IP** dan klik `Next: Add Storage`

    ![gambar 8](assets/configureinstancedetail.png)

-   Pada **Add Storage** sudah secara default memiliki 8Gb, sesuaikan dengan kebutuhan jika sudah klik `Next: Add Tags`

    ![gambar 9](assets/addstorage.png)

-   Pada **Add Tags** bisa dilewati saja atau klik `Next: Configure Security Group`

    ![gambar 10](assets/addtags.png)

-   Pada **Configure Security Group** Ijinkan protokol yang ingin dibuka ke publik, karena digunakan untuk reverse proxy maka membuka akses untuk protokol SSH, HTTP, dan HTTPS untuk kebutuhan remote access SSH dan web server. Jika sudah klik `Review and Launch`

    ![gambar 11](assets/reviewandlounch.png)

-   Pada **Review Instance Launch** jika tidak ada yang mau dirubah klik `Launch`

    ![gambar 12](assets/reviewinstancelaunch.png)

-   Pada **Select an existing key pair or create a new key pair** private key yang digunakan untuk login SSH. Masukkan key pair name yang ingin dibuat, dan **Download** Key Pair untuk remot nanti, jika sudah klik `Launch instances`

    ![gambar 13](assets/reviewinstancelaunch.png)

-   Pada **Launch Status** jika **Your instances are now launching** instance berhasil dibuat. klik `View Instances`

    ![gambar 14](assets/launchstatus.png)

-   Cek **instances** jika server berhasil dibuat.

    ![gambar 15](assets/launchinstannama.png)

-   Buka fitur `Elastic IPs` untuk atur ip static, lalu `Allocated Elastic IP address` dan klik `Allocate` .

    ![gambar 16](assets/elasticip.png)

    ![gambar 17](assets/ipallocate.png)

-   Selanjutnya klik `Associate this Elastic IP address`.

    ![gambar 18](assets/associatethiselasticip.png)

-   Pada **Associate Elastic IP address** pilih server yang telah dibuat, lalu klik `Allocate`.

    ![gambar 19](assets/instancepilihserver.png)

-   Selanjutnya buka directory yang terdapat key pair yang telah didownload, lalu lakukan perintah `sudo ssh -i helloaws.pem ubuntu@3.219.36.139`.

    ![gambar 20](assets/remotesshaws.png)

-   Ketika sudah berhasil meremote server maka hal pertama yang harus dilakukan adalah `sudo apt update` dan `sudo apt upgrade`.

    ![gambar 21](assets/updateserver.png)    

    ![gambar 22](assets/upgradeserver.png)


## Server untuk Aplikasi

-   Selanjutnya membuat server untuk aplikasi, klik `Launch Instances`.

     ![gambar 23](assets/1launch.png)

-   Pada kolom pencarian ketik `ubuntu`, ketika muncul pilih **Server 20.04 LTS 64-bit x86** dan klik `Select`

     ![gambar 24](assets/2cariubuntu.png)    

-   Pada **Choose an Instance Type** pilih **t2.micro** dan klik `Next: Configure Instance Details`

     ![gambar 25](assets/3t2micro.png)    

 -   Pada **Configure Instance Details** isi `1` pada **Number of Instances** lalu `Disable` pada **Auto-assign Public IP** dan klik `Next: Add Storage`

     ![gambar 26](assets/4number.png)

-   Pada **Add Storage** sudah secara default memiliki 8Gb, sesuaikan dengan kebutuhan jika sudah klik `Next: Add Tags`

     ![gambar 27](assets/5storage.png)
-   Pada **Add Tags** bisa dilewati saja atau klik `Next: Configure Security Group`

     ![gambar 28](assets/6tags.png)

-   Pada **Configure Security Group** Ijinkan protokol yang ingin dibuka ke publik, tetapi ini akan membuka pada **All traffic**. Jika sudah klik `Review and Launch`

     ![gambar 29](assets/7alltrafic.png)

-   Pada **Review Instance Launch** jika tidak ada yang mau dirubah klik `Launch`

     ![gambar 30](assets/8review.png)

-   Pada **Select an existing key pair or create a new key pair** untuk kali ini akan menggunakan key pair yang sudah pernah dibuat dan didownload, langsung `Launch instances`

     ![gambar 31](assets/9key.png)

-   Pada **Launch Status** jika **Your instances are now launching** instance berhasil dibuat. klik `View Instances`

     ![gambar 32](assets/10launchstatus.png)

-   Cek **instances** jika server berhasil dibuat.

     ![gambar 33](assets/11gantinama.png)

-   Buka fitur `Elastic IPs` untuk atur ip static, lalu `Allocated Elastic IP address` dan klik `Allocate` .

     ![gambar 34](assets/12elasticip.png)

     ![gambar 35](assets/13allocate.png)

-   Selanjutnya klik `Actions` lalu pilih `Associate Elastic IP address`.

     ![gambar 36](assets/14actionassociate.png)

-   Pada **Associate Elastic IP address** pilih server aplikasi yang telah dibuat, lalu klik `Allocate`.

     ![gambar 37](assets/15pilihserver.png)

-   Cek **instances** jika server aplikasi berhasil dibuat.

     ![gambar 38](assets/16cek.png)

-   Selanjutnya buka directory yang terdapat key pair, lalu lakukan perintah remote `sudo ssh -i helloaws.pem ubuntu@3.223.87.14` jika terjadi **Permission denied (publickey)** maka lakukan perintah `sudo chmod 400 helloaws.pem`, selanjutnya **ulangi** perintah remote.

     ![gambar 39](assets/17remot.png)

-   Ketika sudah berhasil meremote server maka hal pertama yang harus dilakukan adalah `sudo apt update && sudo apt upgrade -y`.

     ![gambar 40](assets/18updateupgrade.png)    

-   Lakukan perintah `git clone https://github.com/sgnd/dumbflix-frontend` yaitu untuk mendapatkan aplikasi yang akan dideploy

     ![gambar 41](assets/19gitclone.png)

-   Lalu instal node.js 14.x `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash`

     ![gambar 42](assets/20curl.png)

-   Setelah itu lakukan perintah `exec bash`, lalu cek versi yang sudah terinstal dengan printah `nvm -v`

     ![gambar 43](assets/21execnvm.png)

-   Untuk menginstal nodejs lakukan perintah `nvm install 14`

     ![gambar 44](assets/22nvminstall14.png)

-   Cek versi menggunakan perintah `node -v` Untuk mengecek npm gunakan perintah `npm -v`

     ![gambar 45](assets/23nodenpm.png)

-   Ketika sudah mengclone aplikasi maka pindah pada directory `cd dumbflix-frontend`

     ![gambar 46](assets/24pindahcd.png)

-   Pada directory dumbflix-frontend lakukan perintah `npm install`

     ![gambar 47](assets/25npminstall.png)

-   lalu ketik perintah `npm start`

     ![gambar 48](assets/26npmstart.png)

     ![gambar 49](assets/27npmstart.png)

-   ketika sudah melakukan start maka masukan `3.223.87.14:3000` pada web broser

     ![gambar 50](assets/28out.png)

## Cabut Ip Public

-   Buka fitur `Elastic IPs` lalu pilih server yang akan dicabut ip publiknya, jika sudah terpilih klik `Actions` lalu pilih `Disassociate Elastic IP address`.

     ![gambar 51](assets/1pilihip.png)

     ![gambar 52](assets/2actionelastic.png)

-   Selanjutnya klik `Disassociate`.

     ![gambar 53](assets/3disass.png)

-   Pada tabel **Security** lalu klik ID pada **Security groups**.

     ![gambar 54](assets/4securitygroup.png)

-   Selanjutnya klik `Edit inbound rules`.

     ![gambar 55](assets/5editinbound.png)

-   Pada tabel **Edit inbound rules** lalu pada **Type** pilih `All traffic` pada Source pilih `Anywhere-IPv4`, kemudian klik `Save rules`.

     ![gambar 56](assets/6allanyip4.png)
        
-   Selanjutnya cek **Instances** apakah masih terdapat Ip Public.

     ![gambar 57](assets/7instancopy.png)
