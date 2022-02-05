# Install Docker

## Install docker in server front-end and server back-end

-   Update dan upgrade sistem dan install packages menggunakan repo.
  ```sh
  sudo apt-get update

 sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
    ```
    ![gambar 1](assets/1.png)

-   Selanjutnya tambahkan official Docker GPG key.
    ```sh
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
    ```
-   Selanjutnya tambahkan repo stable instalasi docker.
    ```sh
    echo \
    "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    ```
    ![gambar 2](assets/2.png)

-   update lagi system dan instal `docker-ce docker-ce-cli` dan `containerd.io`
    ```sh
    sudo apt-get update
    sudo apt-get install docker-ce docker-ce-cli containerd.io
    ```
    ![gambar 3](assets/3.png)

-   Silakan daftar / sign up.
    ```sh
    https://hub.docker.com/
    ```
    ![gambar 4](assets/outout.png)

-   login docker menggunakan akun hub docker yang telah dibuat sebelumnya.
    ```sh
    docker login
    ```
    ![gambar 4](assets/4.png)
