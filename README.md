
Setting environment for using XAMPP for Windows.
ICLABS@DESKTOP-IINTVHQ c:\xampp
# mysql -p root -u
mysql: option '-u' requires an argument

ICLABS@DESKTOP-IINTVHQ c:\xampp
# mysql -u root -p
Enter password:
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 8
Server version: 10.4.32-MariaDB mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]>
MariaDB [(none)]> create database 13020220223;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near '13020220223' at line 1
MariaDB [(none)]> create database _13020220223;
Query OK, 1 row affected (0.001 sec)

MariaDB [(none)]> use _13020220223
Database changed
MariaDB [_13020220223]> create table mahasiswa(nim varchar(20) primary key, nama varchar(20));
Query OK, 0 rows affected (0.114 sec)

MariaDB [_13020220223]> create table pembayaran(id int primary key, fakultas varchar(20));
Query OK, 0 rows affected (0.150 sec)

MariaDB [_13020220223]> create table transaksi(nomor int primary key, harga varchar(50)
    -> foreign key nim(tranksaksi) references nim(mahasiswa)
    -> );
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'foreign key nim(tranksaksi) references nim(mahasiswa)
)' at line 2
MariaDB [_13020220223]> create table transaksi(nomor int primary key, harga varchar(50) foreign key nim(tranksaksi) references nim(mahasiswa));
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'foreign key nim(tranksaksi) references nim(mahasiswa))' at line 1
MariaDB [_13020220223]> create table transaksi(nomor int primary key, harga varchar(50), nim varchar(20), id int, foreign key nim(tranksaksi) references nim(mahasiswa),foreign key id(transaksi) references nim(pembayaran));
ERROR 1072 (42000): Key column 'tranksaksi' doesn't exist in table
MariaDB [_13020220223]>
MariaDB [_13020220223]>
MariaDB [_13020220223]> show tables
    -> ;
+------------------------+
| Tables_in__13020220223 |
+------------------------+
| mahasiswa              |
| pembayaran             |
+------------------------+
2 rows in set (0.001 sec)

MariaDB [_13020220223]> select*form mahasiswa;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'form mahasiswa' at line 1
MariaDB [_13020220223]> select*from mahasiswa;
Empty set (0.136 sec)

MariaDB [_13020220223]> create table transaksi(No int primary key, harga varchar(50), tanggal date);
Query OK, 0 rows affected (0.158 sec)

MariaDB [_13020220223]> show tables
    -> ;
+------------------------+
| Tables_in__13020220223 |
+------------------------+
| mahasiswa              |
| pembayaran             |
| transaksi              |
+------------------------+
3 rows in set (0.000 sec)

MariaDB [_13020220223]> show tables;
+------------------------+
| Tables_in__13020220223 |
+------------------------+
| mahasiswa              |
| pembayaran             |
| transaksi              |
+------------------------+
3 rows in set (0.000 sec)

MariaDB [_13020220223]>
