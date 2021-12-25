# INSTALL GIT AND SSH KEY

## Repository Fork

-   Login akun Github

-   **Cari** Repository dari link tersebut

        https://github.com/sgnd/dumbflix-backend

    lalu klik `Fork`

    ![gambar 1](assets/2fromfork.png)

## Create SSH Key for the Git

-   Masuk pada server yang telah dibuat, lalu lakukan update dan upgrade

        sudo apt update && sudo apt upgrade -y

    ![gambar 2](assets/1update.png)

-   Cek Git dan ssh apakah sudah terinstal

        git --version

    ![gambar 3](assets/3gitversion.png)

-   Jika sudah terinstal lakukan Git config

        ```sh
        git config --global user.name "username"
        ```
        
        ```sh
        git config --global user.email "your-email"
        ```
        
    ![gambar 4](assets/44.png)

-   Lakukan generate ssh-KEY

        ssh-keygen -t rsa -b 4096

    ![gambar 5](assets/4sshkey.png)

-   Buka **id_rsa.pub** lalu copy

        cat .ssh/id_rsa.pub

    ![gambar 6](assets/45bukarsa.png)

-   Buka akun github dan pastekan **id_rsa.pub** yang sudah di copy

        https://github.com/settings/ssh/new

    ![gambar 7](assets/5pastekey.png)

-   Selanjutnya autentikasi SSH ke github

        ssh -T git@github.com

    ![gambar 8](assets/6ssh-T.png)

## Git on the server can git pull, git commit, git push without username & password

-   Clone Repository

        git clone git@github.com:asdfroot/dumbflix-backend.git

    ![gambar 9](assets/7gitclone.png)

-   Coba Membuat file baru pada directory github hasil clone

        cat > init.txt

    ![gambar 10](assets/8buatfile.png)

-   Coba melakukan commit

        git add .

        git commit -m "pesan"

    ![gambar 11](assets/9gitcommit.png)

-   Coba melalukan push

        git push git@github.com:asdfroot/dumbflix-backend.git

    ![gambar 12](assets/10push.png)

-   Coba melalukan push

        git pull git@github.com:asdfroot/dumbflix-backend.git

    ![gambar 13](assets/11.png)

-   Cek perubahan pada Repository

    ![gambar 14](assets/12cek.png)
