# Connect Multiple Server to Prometheus

## Setup node exporter

-   Install node_exporter di server target

    ![gambar](assets/1exporteradimonit.png)

-   Edit file prometheus.yml 
    ```sh
    sudo nano /etc/prometheus/prometheus.ym
    ```
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
          - targets: ['localhost:9090', 44.198.105.77:9100] #target server
    ```
    ![gambar](assets/ymltarget.png)

-   Restart prometheus service
    ```sh
    sudo systemctl restart prometheus.service
    ```
-   Masuk ke server promtheus dengan port 9090

    ![gambar](assets/outtarget.png)

## Setup Grafana

-   Lakukan login pada grafana

    ![gambar](assets/27.png)

-   Lalu tambahkan data source prometheus
    ```sh
    alamatIP:3000/datasource
    ```
    ![gambar](assets/datasourceprome.png)

-   Lalu setup prometheus pada web grafana. Dengan menambahkan URL dari prometheus. pastikan tidak terdapat warning atau failed.

    ![gambar](assets/iptarget.png)

-   cari dashboard yang sesuai kebutuhan pada `https://grafana.com/grafana/dashboards/`

    ![gambar](assets/import.png)

-   Selanjutnya pada **dashboard** pilih `prometheus`, pada **Job** masukan `node_exporter_metrics` dan pada **Host** pilih `IP target`.

    ![gambar](assets/outdash.png)
