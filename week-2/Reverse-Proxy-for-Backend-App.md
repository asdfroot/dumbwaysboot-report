# REVERSE PROXY

## Update and upgrade the operating system

-   Login ke server gateway

-   Lakukan Update and upgrade system

        sudo apt update && sudo apt upgrade -y

    ![gambar 1](assets/1updategrade.png)

## Install web server for reverse proxy

-   Instal web server

        sudo apt install nginx

    ![gambar 2](assets/2.png)

## Create reverse proxy from application with port 5000 to port 80

-   Setelah login lakukan update dan upgrade
    ```sh
    cd /etc/nginx/
    ```
    ```sh
    sudo mkdir dumbflix-backend
    ```
    ![gambar 3](assets/3bikinfolder.png)

-   Lalu buat file config buat backend

        sudo nano api.syarif.onlinecamp.id

    ![gambar 4](assets/4buatfileconfig.png)

    ![gambar 5](assets/5isiconfig.png))

-   sudo nano /etc/nginx/nginx.conf

        sudo nano /etc/nginx/nginx.conf

    kemudian tambahkan

        Include /etc/nginx/dumbflik-backend/*;

    ![gambar 6](assets/7isiinclude.png)

-   Jika sudah,lakukan restart pada nginx

        sudo systemctl restart nginx

    ![gambar 7](assets/8restart.png)
