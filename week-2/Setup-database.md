# SETUP DATABASE

## Create new instance for Backend

-   Buat private instance database

    ![gambar 1](assets/001.png)

## Install database on the server

-   Login ke instance database

    ![gambar 2](assets/01logindatabase.png)

-   Setelah login lakukan update dan upgrade

    >sudo apt-get update && sudo apt-get disk-upgrade

    ![gambar 3](assets/11dategradedatabase.png)

-   Lalu instal mysql

    >sudo apt install mysql-server

    ![gambar 4](assets/12installmysqlserver.png)

-   Cek mysql

    >sudo systemctl status mysql

    ![gambar 5](assets/13cekmysql.png)

-   Setup keamanan mysql

    >sudo mysql_secure_installation

    ![gambar 6](assets/14sqlsecureinstallastion.png)

-   Jika sudah, masuk ke mysql dengan user root

    >sudo mysql -u root -p

    ![gambar 7](assets/15.png)

-   Pada mysql bisa melakukan login tanpa sudo dan membuat user baru

    Login without sudo
    ```
    sudo mysql -uroot
    mysql > SELECT User, Host FROM mysql.user;
    mysql > DROP USER 'root'@'localhost';
    mysql > CREATE USER 'root'@'localhost' IDENTIFIED BY 'STRING-PASSWORD-NYA';
    mysql > GRANT ALL PRIVILEGES ON *.* TO 'root'@'localhost' WITH GRANT OPTION;
    mysql > FLUSH PRIVILEGES;
    mysql > exit
    mysql -uroot
    ```
    Create new user
    ```
    CREATE USER 'newuser'@'%' IDENTIFIED BY 'password';
    GRANT ALL PRIVILEGES ON *.* TO 'newuser'@'%';
    FLUSH PRIVILEGES;
    ```

    ![gambar 8](assets/15tanpasudo.png)

-   Melihat database

    >show databases;

    ![gambar 9](assets/16showdatabases.png)

## Can remote on the database from the client

-   Buka directory dan edit pada **blind-address** dan **mysql-blind-address**

    >sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf

    ![gambar 10](assets/17nanomysqldcnf.png)

-   Jika sudah lakukan restart pada mysql

    >sudo systemctl restart mysql-service

    ![gambar 11](assets/18restartmysql.png)
