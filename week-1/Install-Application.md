# VMWARE - SERVER FOR APPLICATION

## Update and upgrade system opration

-   Masuk pada server yang telah diuat `ssh asdf@192.186.1.17`

    ![gambar 1](assets/1ssh.png)

-   Setelah masuk maka lakukan Update dan upgrade `sudo apt update && apt upgrade -y`

    ![gambar 2](assets/updateupgrade.png)

## Install node.js 14/xx

-   Setelah melakukan Update dan upgrade lalu instal node.js 14.x `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash`

    ![gambar 3](assets/2curljs.png)

-   Setelah itu lakukan perintah `exec bash`, lalu cek versi yang sudah terinstal dengan printah `nvm -v`

    ![gambar 4](assets/2execbas&ver.png)

-   Untuk menginstal nodejs lakukan perintah `nvm install 14`

    ![gambar 5](assets/nvminstal14.png)

-   Cek versi menggunakan perintah `node -v` Untuk mengecek npm gunakan perintah `npm -v`

    ![gambar 6](assets/nodenpm.png)

## gitclone sebuah apps

-   Lakukan perintah `git clone https://github.com/sgnd/dumbflix-frontend` yaitu untuk mendapatkan aplikasi yang akan dideploy

    ![gambar 7](assets/gitclone.png)

## Change directory and deploy application

-   Ketika sudah mengclone aplikasi maka pindah pada directory `cd dumbflix-frontend`

    ![gambar 8](assets/pindahcd.png)

-   Pada directory dumbflix-frontend lakukan perintah `npm install`

    ![gambar 9](assets/npminstall.png)

-   lalu ketik perintah `npm start`

    ![gambar 10](assets/start.png)

-   ketika sudah melakukan start maka masukan `192.168.1.17:3000` pada web browser

    ![gambar 11](assets/akhirnya.png)
