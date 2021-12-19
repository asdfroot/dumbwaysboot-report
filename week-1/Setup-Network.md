# VMWARE - Setup Network

## Change network from NAT to Bridge

-   Buka mesin virtual (VirtualBox) arahkan pada Server yang ingin dirubah tipe jaringannya lalu klik `Setting`

    ![gambar 1](assets/0setting.png)

-   Setelah masuk pada tab **Network** jika ingin mengganti tipe jaringan maka klik pada bagian **Attached to:** rubah yang semula tipe jaringannya **NAT** menjadi **Bridge Adapter** kemudian `OK`

    ![gambar 2](assets/1bridge.png)

## Setup static IP for Ubuntu Server

-   Selanjutnya ketika sudah berada dalam server lakukan perintah `ifconfig` untuk melihat IP yang sedang digunakan.

    ![gambar 3](assets/1ifconfig.png)

-   Akses directory `cd /etc/netplan/`

    ![gambar 4](assets/2cdnetplan.png)

-   Edit file yang berada dalam directory **netplan** `sudo nano nama.file`, lakukan perubahan angka terakhir dari IP address sesuai keinginan kemudian pada **nameservers** isikan saja dns google `8.8.8.8`

    ![gambar 5](assets/4nano.png)

    ![gambar 6](assets/5isinano.png)

-   Jika sudah melakukan perubahan lakukan perintah `sudo netplan apply`

    ![gambar 8](assets/6netplanapply.png)

-   Terakhir cek koneksi internet dengan melakukan perintah `ping google.com`

    ![gambar 9](assets/8ping.png)
