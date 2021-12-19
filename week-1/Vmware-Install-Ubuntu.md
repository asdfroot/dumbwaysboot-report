# Vmware Install Ubuntu

-   Persiapan

    - Download Ubuntu Server 20.04.x LTS `https://releases.ubuntu.com/focal/`

    - Download VirtualBox for Linux `https://www.virtualbox.org/wiki/Linux_Downloads`

    - **Virtualization Technology** sudah diaktifkan atau berstatus **enabled** pada **Bios**

-   VirtualBox

    Buka VirtualBox lalu klik `New`

    ![gambar 1](assets/new.png)

-   Setelah itu akan tampil Window **Name and oprating system**, pada bagian **Name** isi dengan `ubuntu server` maka secara otomatis pada bagian **Type** dan **Version** akan mengisi dengan sendirinya, lalu klik `Next >`

    ![gambar 2](assets/namatipe.png)

-   Langkah selanjutnya tentukan besar ukuran memory yang akan kita gunakan. Minimal system requirements sistem operasi ubuntu yaitu **1024 MB** atau setara dengan **1 GB**. Jika dirasa kurang bisa menambah besarnya ukuran memory ini. lalu `Next >`

    ![gambar 3](assets/pilihram.png)

-   Hardisk yang akan gunakan disini akan membuat hardisk virtual baru. pilih **Creat a virtual hard disk now** lalu klik `Creat`

    ![gambar 4](assets/createdisk.png)

-   Pada **Hard disk file type** pilih **VDI (VirtualBox Disk Image)** lalu `Next >`

    ![gambar 5](assets/vdi.png)

-   Pada **Storage on physical hard disk** pilih **Dynamically allocated** lalu `Next >`

    ![gambar 6](assets/dynamic.png)

-   Di tahap **File location and size** menentukan besarnya virtual hardisk yang akan kita buat. Disini saya menentukan virtual hardisknya sebesar `30 GB`. virtual hardisk bisa diisi sesuai kebutuhan. lalu `Create`

    ![gambar 7](assets/sizedisk.png)

-   Setelah di `Create` maka sudah selesai melakukan pembuatan virtual mesin, selanjutnya klik `settings` untuk melakukan konfigurasi lainnya.

    ![gambar 8](assets/new.png)

-   Pada **tab system** tentukan core prosesor yang akan digunakan dalam virtual mesin ini. Secara default mesin virtual hanya menggunakan **1 core**.  sebenarnya bisa optional karna untuk belajar jadi menggunakan 1 core sudah cukup.

    ![gambar 9](assets/1cpu.png)

-   Selanjutnya pada **tab storage** `add` **iso** ubuntu yang sudah didownload.

    ![gambar 10](assets/addiso.png)

-   pada **tab Network** di bagian **Attached** untuk mengganti mode jaringan dari mode NAT ke Bridge yang nantinya agar host dan mesin virtual kita bisa berada dalam satu network yang sama. lalu klik `OK`

    ![gambar 11](assets/jaringan.png)

-   Setelah mesin virtual sudah selesai dibuat selanjutnya kita mulai menyalakan mesin virtual dengan klik `Start`.

    ![gambar 12](assets/start11.png)

-   Tunggu hingga proses load selesai maka nanti akan tampilan halaman installer. Pilih bahasa instalasi yang diinginkan.

    ![gambar 13](assets/bahasa1.png)

-   Selanjutnya kita diminta untuk melakukan konfigurasi keyboard layout. Biarkan default saja dan pilih `Done` untuk lanjut.

    ![gambar 14](assets/bahasakey.png)

-   Pada tahap Network Conections , pilih **IPv4 Method** dan Manual

    ![gambar 15](assets/manual.png)

-   Lalu isi configuration, klik `Save`

    ![gambar 16](assets/manualisi.png)

-   Untuk Proxy Address kosongkan saja.

    ![gambar 17](assets/configproxy.png)

-   Untuk Mirror Address biarkan default saja.

    ![gambar 18](assets/configmirror.png)

-   Untuk opsi storage pilih custom storage layout.

    ![gambar 19](assets/customdisk.png)

-   Pada **AVAILLABLE DEVICE** pilih **Add GPT Partition**.

    ![gambar 20](assets/addswab.png)

-   Pada **Size** isi **1G** lalu pada **Format** isi **swap**,klik `Creat`.

    ![gambar 21](assets/isiswab.png)

-   lalu **AVAILLABLE DEVICE** pilih **Add GPT Partition**.

    ![gambar 22](assets/addext.png)

-   Pada **Size** isi sisa storage lalu pada **Format** isi **ext4**,klik `Creat`.

    ![gambar 23](assets/isiext.png)


-   Jika sudah maka **Enter** pada `Done` dan **Continue**.

    ![gambar 24](assets/donestorage.png)

-   Maka selanjutnya membuat akun yang nantinya digunakan untuk masuk kedalam sistem operasi ubuntu server yang telah terinstall. Isi sesuaikan dengan keinginan.

    ![gambar 25](assets/isiprofil.png)

-   Selanjutnya akan ada tawaran untuk langsung melakukan instalasi **OpenSSH Server** yang bisa kita gunakan untuk remote server nantinya. **Enter** pada **Install OpenSSH server**, lalu `Done`.

    ![gambar 26](assets/installssh.png)

-   Tunggu proses instalasi ubuntu server hingga selesai. Jika sudah maka nantinya kita diminta untuk melakukan `reboot` untuk kemudian booting masuk ke sistem operasi yang telah terinstall.

    ![gambar 27](assets/rebootnow.png)

-   Tungu proses booting selesai hingga muncul prompt login masuk sistem operasi. Jika sudah ada prompt untuk masuk ke sistem operasi masukan **username** dan **password** yang telah dibuat saat instalasi.

    ![gambar 28](assets/passlog.png)

-   Jika sudah masuk lakukan perintah `ping google.com` untuk mencoba apakah terhubung dengan internet atau tidak.

    ![gambar 29](assets/ping.png)    
