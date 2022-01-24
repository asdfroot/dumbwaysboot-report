# Docker Swarm & Microservices

## Docker Swarm & Microservices

-   Buat 3 server untuk 1 manager dan 2 worker

    ![gambar](assets/servermana.png)

    ![gambar](assets/serverwor1.png)

    ![gambar](assets/serverwor2.png)

-   Install docker menggunakan ansible.

    ![gambar](assets/1manag.png)

    ![gambar](assets/1worker1.png)

    ![gambar](assets/1worker2.png)    

-   Setup Docker Swarm.
    Perintah init untuk docker swarm
    ```sh
    docker swarm init --advertise-addr IPservermanagar
    ```
    ![gambar](assets/2managerad.png)

-   Join tiap worker ke docker swarm.

    ![gambar](assets/2worker1ad.png)

    ![gambar](assets/2worker2ad.png)

-   Untuk memastikan server worker telah terdaftar di docker swarm lakukan dengan perintah.
    ```sh
    sudo docker node ls
    ```
    ![gambar](assets/3bkti.png)

-   Clone repository.
    ```sh
    git clone https://github.com/sgnd/dumbways-microservices.git
    ```
    ![gambar](assets/4clone.png)    

-   Buat images dan deploy.

    perintah build
    ```sh
    docker-compose build
    ```
    perintah deploy
    ```sh
    docker stack deploy --compose-file docker-compose.yml stack-apps
    ```
    ![gambar](assets/10stackdeploy.png)

-   Replicate dari salah satu container.
    ```sh
    docker service scale IdContainer=JumlahReplica
    ```
    ![gambar](assets/scale.png)

-   Akses web browser dengan AlamatIp>:Port.

    ![gambar](assets/out.png)
