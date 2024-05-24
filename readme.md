# Tugas Praktikum { Pertemuan ke 11 } 

|Variabel|isi|
|--------|---|
|**Nama**| Ananda Rahmadani
|**NIM**| 312310461
|**Kelas**| TI.23.A5
|**Matkul**| Basis Data

# Soal Latihan Praktikum ( Pegawai )

![Screenshot soal p](https://github.com/anandarahmadani/praktikum4/assets/147919907/4eceb52c-94ae-4517-9bf6-42b5eb5317e9)

**Perintah SQL :**

```
CREATE TABLE pegawai (
    idpegawai VARCHAR(5) PRIMARY KEY,
    nama_depan VARCHAR(10) NOT NULL,
    nama_belakang VARCHAR(15) NOT NULL,
    email VARCHAR(25) UNIQUE KEY,
    telepon VARCHAR(15),
    tgl_kontrak DATA,
    id_job VARCHAR(5),
    gaji INT,
    tunjangan INT
    );

INSERT INTO pegawai VALUES
    ('E001', 'Ferry', 'Gustiawan', 'ferry@yahoo.com', '07117059004', '2005-09-01', 'L0001', 2000000, 500000),
	('E002', 'Aris', 'Ganiardi', 'aris@yahoo.com', '081312345678', '2006-09-01', 'L0002', 2000000, 200000),
	('E003', 'Faiz', 'Ahnad', 'faiz@gmail.com', '081367384322', '2006-10-01', 'L0003', 1500000, NULL),
	('E004', 'Emna', 'Bunton', 'emna@gmail.com', '081363484342', '2006-10-01', 'L0004', 1500000, 9),
	('E005', 'Mike', 'Scoff', 'mike@plasa.com', '08163454555', '2007-09-01', 'L0005', 1250000, 9),
	('E006', 'Lincoln', 'Burrows', 'linc@yahoo.com', '08527388432', '2008-09-01', 'L0006', 1750000, NULL);
```

***Output :***

![Screenshot sql p](https://github.com/anandarahmadani/praktikum4/assets/147919907/4bf30343-21fd-4a7e-9e33-90a577481ca9)


## Tugas Praktikum

**1. Tampilkan pegawai yang gajinya bukan 2.000.000 dan 1.250.000 !**

```
SELECT*FROM pegawai WHERE gaji NOT IN (2000000, 1250000);
```

***Output :***

![Screenshot 1 p](https://github.com/anandarahmadani/praktikum4/assets/147919907/0631f7e8-8aca-48ef-a828-3856da4eb995)


**2. Tampilkan pegawai yang tunjangannya NULL!**

```
SELECT*FROM pegawai WHERE tunjangan IS NULL;
```

***Output :***
![Screenshot 2 p](https://github.com/anandarahmadani/praktikum4/assets/147919907/a4bc458f-089d-4cd5-9197-c4a541591502)

**3. Tampilkan pegawai yang tunjangannya tidak NULL!**

```
SELECT*FROM pegawai WHERE tunjangan IS NOT NULL;
```

***Output :***
![Screenshot 3 p](https://github.com/anandarahmadani/praktikum4/assets/147919907/d5e0c45b-66b0-49eb-b31f-0585a5feaee4)

**4. Tampilkan/hitung jumlah baris/record tabel pegawai!**

```
SELECT COUNT(*) AS jmlh_pegawai FROM pegawai;
```

***Output :***
![Screenshot 4 p](https://github.com/anandarahmadani/praktikum4/assets/147919907/2805ac6c-4bec-4935-92bf-30da528576cc)

**5. Tampilkan/hitung jumlah total gaji di tabel pegawai!**

```
SELECT SUM(gaji) AS ttl_gaji FROM pegawai;
```

***Output :***
![Screenshot 5 p](https://github.com/anandarahmadani/praktikum4/assets/147919907/f1e5d0ba-83b2-4b24-b696-3c336804c214)

**6. Tampilkan/hitung rata-rata gaji pegawai!**

```
SELECT AVG(gaji) AS mean_gaji FROM pegawai;
```

***Output :***
![Screenshot 6 p](https://github.com/anandarahmadani/praktikum4/assets/147919907/76819225-721e-443a-9fca-e307b8fadad0)


**7. Tampilkan gaji terkecil!**

```
SELECT MIN(gaji) AS terkecil FROM pegawai;
```

***Output :***
![Screenshot 7 p](https://github.com/anandarahmadani/praktikum4/assets/147919907/71ee075b-1baf-4eed-baab-99a8b0d4a32b)

**8. Tampilkan gaji terbesar!**

```
SELECT MAX(gaji) AS terbesar FROM pegawai;
```

***Output :***
![Screenshot 8 p](https://github.com/anandarahmadani/praktikum4/assets/147919907/11f7db1a-5e80-455a-882e-e16fe625a517)

# Soal Latihan Praktikum ( Hewan )
![Screenshot soal h](https://github.com/anandarahmadani/praktikum4/assets/147919907/acc84187-15cc-4c2b-b20f-f45f01cb1ec9)

**Perintah SQL :**

```
CREATE TABLE hewan (
    id VARCHAR (5) PRIMARY KEY,
    name VARCHAR (10) NOT NULL,
    owner VARCHAR (10),
    species VARCHAR (10),
    sex enum('M', 'F')
    );

INSERT INTO hewan VALUES
    ('p1', 'Puffball', 'Diane', 'Hamster', 'F'),
    ('p2', 'Claws', 'Gwen', 'Cat', 'M'),
    ('p3', 'Fluffy', 'Haro 1d', 'Cat', 'F'),
    ('p4', 'Buffy', 'Haro 1d', 'Dog', 'F'),
    ('p5', 'Fang', 'Benny', 'Dog', 'M'),
    ('p6', 'Bowser', 'Diane', 'Dog', 'M'),
    ('p7', 'Chirpy', 'Gwen', 'Bird', 'F'),
    ('p8', 'Whistler', 'Gwen', 'Bird', NULL),
    ('p9', 'Slim', 'Benny', 'Snake', 'M');
```

***Output :***
![Screenshot sql h-1](https://github.com/anandarahmadani/praktikum4/assets/147919907/7e46ea1a-31fd-443c-8d78-63340a53aa0c)

## Tugas Praktikum

**1. Tampilkan jumlah hewan yang dimiliki setiap owner.**

```
SELECT owner, COUNT(*) AS jmlh_hewan FROM hewan GROUP BY owner;
```

***Output :***
![Screenshot 1 h](https://github.com/anandarahmadani/praktikum4/assets/147919907/10d93891-235d-44c5-a183-c83a8646d9e4)

**2. Tampilkan jumlah hewan berdasarkan spesies**

```
SELECT species, COUNT(*) AS jmlh_hewan FROM hewan GROUP BY species;
```

***Output :***
![Screenshot 2 h](https://github.com/anandarahmadani/praktikum4/assets/147919907/8bf076b8-fdb1-42a9-83cd-6d7a63050b3a)

**3. Tampilkan jumlah hewan berdasarkan jenis kelamin**

```
SELECT sex, COUNT(*) AS jmlh_hewan FROM hewan GROUP BY sex;
```

***Output :***
![Screenshot 3 h](https://github.com/anandarahmadani/praktikum4/assets/147919907/1c7c0686-1160-48cf-a0dc-783046eafea3)

**4. Tampilkan jumlah hewan berdasarkan spesies dan jenis kelamin**

```
SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY species, sex;
```

***Output :***
![Screenshot 4 h](https://github.com/anandarahmadani/praktikum4/assets/147919907/b9a5a312-acad-40b8-8e4b-9cfc6e76513b)

**5. Tampilkan jumlah hewan berdasarkan spesis (cat dan dog saja) dan jenis kelamin**

```
SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE
species IN ('Cat', 'Dog')
GROUP BY species, sex;
```

***Output :***
![Screenshot 5 h](https://github.com/anandarahmadani/praktikum4/assets/147919907/b2e2a6e0-694c-4c52-8333-2e9a476408f8)

**6. Tampilkan jumlah hewan berdasarkan jenis kelamin yang diketahui saja**

```
SELECT sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE sex IS NOT NULL GROUP BY sex;
```

***Output :***
![Screenshot 6 h](https://github.com/anandarahmadani/praktikum4/assets/147919907/1252ff57-22d8-47fd-98d1-19e38335afb6)

## Tulis semua perintah-perintah SQL percobaan di atas beserta outputnya!

```
CREATE DATABASE praktikum4;
USE praktikum4;
CREATE TABLE pegawai (
    idpegawai VARCHAR (5) PRIMARY KEY,
    nama_depan VARCHAR (10) NOT NULL,
    nama_belakang VARCHAR (15) NOT NULL,
    email VARCHAR (25) UNIQUE KEY,
    telepon VARCHAR (15),
    tgl_kontrak DATE,
    id_job VARCHAR (5),
    gaji INT,
    tunjangan INT
    );

INSERT INTO pegawai VALUES
    ('E001', 'Ferry', 'Gustiawan', 'ferry@yahoo.com', '07117059004', '2005-09-01', 'L0001', 2000000, 500000),
	('E002', 'Aris', 'Ganiardi', 'aris@yahoo.com', '081312345678', '2006-09-01', 'L0002', 2000000, 200000),
	('E003', 'Faiz', 'Ahnad', 'faiz@gmail.com', '081367384322', '2006-10-01', 'L0003', 1500000, NULL),
	('E004', 'Emna', 'Bunton', 'emna@gmail.com', '081363484342', '2006-10-01', 'L0004', 1500000, 9),
	('E005', 'Mike', 'Scoff', 'mike@plasa.com', '08163454555', '2007-09-01', 'L0005', 1250000, 9),
	('E006', 'Lincoln', 'Burrows', 'linc@yahoo.com', '08527388432', '2008-09-01', 'L0006', 1750000, NULL);

SELECT * FROM pegawai;

SELECT * FROM pegawai WHERE gaji NOT IN (2000000, 1250000);

SELECT * FROM pegawai WHERE tunjangan IS NULL;

SELECT * FROM pegawai WHERE tunjangan IS NOT NULL;

SELECT COUNT(*) AS jumlah_pegawai FROM pegawai;

SELECT SUM(gaji) AS total_gaji FROM pegawai;

SELECT AVG(gaji) AS rata_rata_gaji FROM pegawai;

SELECT MIN(gaji) AS gaji_terkecil FROM pegawai;

SELECT MAX(gaji) AS gaji_terbesar FROM pegawai;

CREATE TABLE hewan (
    id VARCHAR (5) PRIMARY KEY,
    name VARCHAR (10) NOT NULL,
    owner VARCHAR (10),
    species VARCHAR (10),
    sex enum('M', 'F')
    );

INSERT INTO hewan (id, name, owner, species, sex)
VALUES ('p1', 'Puffball', 'Diane', 'Hamster', 'F'),
       ('p2', 'Claws', 'Gwen', 'Cat', 'M'),
       ('p3', 'Fluffy', 'Haro 1d', 'Cat', 'F'),
       ('p4', 'Buffy', 'Haro 1d', 'Dog', 'F'),
       ('p5', 'Fang', 'Benny', 'Dog', 'M'),
       ('p6', 'Bowser', 'Diane', 'Dog', 'M'),
       ('p7', 'Chirpy', 'Gwen', 'Bird', 'F'),
       ('p8', 'Whistler', 'Gwen', 'Bird', NULL),
       ('p9', 'Slim', 'Benny', 'Snake', 'M');

SELECT * from hewan;

SELECT owner, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY owner;

SELECT species, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY species;

SELECT sex, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY sex;

SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY species, sex;

SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE species IN ('Cat', 'Dog') GROUP BY species, sex;

SELECT sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE sex IS NOT NULL GROUP BY sex;
```

## Berikan Kesimpulan Anda !

Terdapat beberapa ***Query Filter*** yang ditemukan pada tugas praktikum 4 :

- Operator `IN` digunakan untuk memfilter data yang terdapat pada list IN
- Operator `NOT IN` digunakan untuk memfilter data yang tidak terdapat pada list IN
- Operator `IS NULL` digunakan untuk menampilkan data dengan nilai data NULL
- Operator `IS NOT NULL` digunakan untuk menampilkan data dengan nilai data tidak NULL
- `COUNT` adalah perintah yang digunakan untuk menghitung jumlah baris suatu kolom pada tabel.
- `SUM` adalah perintah yang digunakan untuk menghitung jumlah nilai suatu kolom pada tabel.
- `AVG` adalah perintah yang digunakan untuk menghitung rata-rata dari nilai suatu kolom pada tabel.
- `MIN` adalah perintah yang digunakan untuk menampilkan nilai terkecil dari suatu kolom pada tabel.
- `MAX` adalah perintah yang digunakan untuk menampilkan nilai terbesar dari suatu kolom pada tabel.
- Klausa `GROUP BY` berfungsi untuk mengelompokkan data berdasarkan field tertentu.

# TERIKASIH
