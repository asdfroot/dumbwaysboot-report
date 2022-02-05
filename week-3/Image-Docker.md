# Create Docker Images

## Membuat Docker Images Untuk Frontend dan backend

-   Login ke server frontend dan backend.

-   Pada directory `dumbflix-frontend` dan `dumbflix-backend` masing-masing buat file Dockerfile.
    ```sh
    sudo nano Dockerfile
    ```
-   Isi Dockerfile konfigurasi.
    ```sh
    FROM node:14
    WORKDIR /app
    COPY . .
    RUN npm install
    EXPOSE 3000
    CMD [ "npm","start" ]
    ```
    >rubah "EXPOSE 3000" untuk frontend dan "EXPOSE 5000" untuk backend

    ![gambar 1](assets/2isidockerfile.png)

-   jika sudah, build images dari Dockerfile yang sudah kita buat dengan perintah.
    ```sh
    docker build -t frontend .
    ```
    ![gambar 2](assets/5build.png)

-   selanjutnya, push images yang sudah kita build.
    ```sh
    sudo docker push <username>/<images-name>:<images-tag>
    ```
    ![gambar 3](assets/7push.png)

-   Buka halaman web docker hub untuk melihat images yang sudah kita push pada repository kita

    ![gambar 4](assets/hasilpushdocker.png)
