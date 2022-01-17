# Monitoring

## Install Node Exporter di server

-   Melakukan proses instalasi node-exporter dengan docker di ansible, kemudian jalankan dengan menggunakan ansible-playbook pada `setup-node-exporter.yml`.

    `docker-compose.yml` node-exporter

    ![gambar](assets/comnode.png)

    `setup-node-exporter.yml` node-exporter

    ![gambar](assets/setnode.png)

-   Buka web browser dan akses di `http://alamatIP:9100`

    ![gambar](assets/outex.png)

## Install Prometheus di server

-   Mendownload file node Prometheus
    ```sh
    wget https://github.com/prometheus/prometheus/releases/download/v2.31.1/prometheus-2.31.1.linux-amd64.tar.gz
    ```
    ![gambar](assets/12.png)

-   Lalu mengextract file yang sudah didownload tadi
    ```sh
    tar -xf prometheus-2.31.1.linux-amd64.tar.gz
    ```
    ![gambar](assets/13.png)

-   Pindahkan file hasil extract ke /usr/local/bin
    ```sh
    sudo mv prometheus promtool /usr/local/bin
    ```
    ![gambar](assets/14.png)

-   Lalu buat folder prometheus pada /etc/ dan pada /var/lib/
    ```sh
    sudo mkdir /etc/prometheus /var/lib/prometheus
    ```
    ![gambar](assets/11.png)

-   Setelah itu pindahkan folder /console_libraries/ yang ada di folder hasil ekstraksi ke /etc/prometheus/
    ```sh
    sudo mv consoles console_libraries /etc/prometheus
    ```
    ![gambar](assets/16.png)

-   Selanjutnya membuat file configurasi prometheus, dengan nama prometheus.yml, dan memberikan detail job yang akan dilakukan, dan server yang akan di monitor.
    ```sh
    global:
      scrape_interval: 10s
    scrape_configs:
      - job_name: 'prometheus-metrics'
        scrape_interval: 10s
        static_configs:
          - targets: ['localhost:9100']
    - job_name: 'node_exporter_metrics'
      scrape_interval: 5s
      static_configs:
        - targets: ['44.198.105.77:9100'] #target server
    ```
    ![gambar](assets/17.png)

-   Tambahkan user untuk prometheus dan ubah kepemilikan folder /etc/prometheus dan /var/lib/prometheus ke user prometheus
    ```sh
    sudo useradd -rs /bin/false prometheus
    ```
    ```sh
    sudo chown -R prometheus: /etc/prometheus /var/lib/prometheus
    ```
    ![gambar](assets/19.png)

-   Lalu tambahkan file prometheus.service di /etc/systemd/system/, dengan isinya sebagai berikut.
    ```sh
    [Unit]
    Description=Prometheus
    After=network.target
    [Service]
    User=prometheus   
    Group=prometheus   
    Type=simple
    ExecStart=/usr/local/bin/prometheus \
        --config.file /etc/prometheus/prometheus.yml \
        --storage.tsdb.path /var/lib/prometheus/ \
        --web.console.templates=/etc/prometheus/consoles \
        --web.console.libraries=/etc/prometheus/console_libraries
    [Install]
    WantedBy=multi-user.target
    ```
    ![gambar](assets/20proser.png)

-   Jalankan service prometheus Melakukan test akses ke prometheus dengan
    ```sh
    sudo systemctl daemon-reload
    ```
    ```sh
    sudo systemctl enable prometheus
    ```
    ```sh
    sudo systemctl start prometheus
    ```
    ![gambar](assets/21.png)

-   Melakukan test akses ke prometheus

    ![gambar](assets/outpro.png)

## Install Grafana di server

-   Download gpg.key untuk package grafana, tambahkan ke apt dan repository grafana
    ```sh
    wget -q -O - https://packages.grafana.com/gpg.key | sudo apt-key add -
    echo "deb https://packages.grafana.com/oss/deb stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
    ```
-   Update dengan perintah `sudo apt-get update` lalu install grafana
    ```sh
    sudo apt-get install grafana
    ```
    ![gambar](assets/23.png)

-   Jalankan service grafana
    ```sh
    systemctl enable grafana-server
    ```
    ```sh
    systemctl restart grafana-server.service
    ```
    ```sh
    systemctl status grafana-server.service
    ```
    ![gambar](assets/26.png)

-   Lalu rubah config file grafana, `allow_sign_up` dan `auth.anonymous` dibuat **false**.
    ```sh
    sudo nano /etc/grafana/grafana.ini
    ```
    ![gambar](assets/24.png)

-   Restart service grafana
    ```sh
    systemctl restart grafana-server.service
    ```
-   Lalu akses ip server monitor melalui port `3000`

    ![gambar](assets/27.png)

