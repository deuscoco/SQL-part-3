# 📘 Basis Data Part 3 – WHERE, AND, OR

---

## 📌 Pendahuluan

Pada **Basis Data Part 3**, materi berfokus pada penggunaan klausa **WHERE** untuk melakukan penyaringan (filtering) data. Selain itu, diperkenalkan juga penggunaan **operator logika OR dan AND**, serta filter berbasis angka. Materi ini sangat penting karena hampir semua query SQL nyata menggunakan klausa WHERE.

Dokumentasi ini disusun dalam format **Markdown** agar dapat langsung digunakan sebagai **README di GitHub**, dan telah dilengkapi dengan **jawaban lengkap seluruh quiz** sesuai modul.

---

## 🗂️ Contoh Tabel: `ms_produk`

| kode_produk | nama_produk           | harga |
| ----------- | --------------------- | ----- |
| prod-01     | Kotak Pensil DQLab    | 62500 |
| prod-02     | Flashdisk DQLab 64 GB | 55000 |
| prod-03     | Buku Tulis DQLab      | 12000 |
| prod-04     | Flashdisk DQLab 32 GB | 40000 |
| prod-05     | Pulpen DQLab          | 8000  |

---

## 1️⃣ Penggunaan WHERE

Klausa `WHERE` digunakan untuk memfilter data berdasarkan kondisi tertentu.

### 📘 Quiz 1

**Soal:** Buat query `WHERE` dengan filter `nama_produk`.

**Query (Jawaban):**

```sql
SELECT *
FROM ms_produk
WHERE nama_produk = 'Flashdisk DQLab 32 GB';
```

---

## 2️⃣ Operand OR

Operator `OR` digunakan untuk menampilkan data yang memenuhi salah satu dari beberapa kondisi.

### 📘 Quiz 2

**Soal:** Buat query kombinasi `WHERE` dan `OR` pada `nama_produk`.

**Query (Jawaban):**

```sql
SELECT *
FROM ms_produk
WHERE nama_produk = 'Kotak Pensil DQLab'
   OR nama_produk = 'Pulpen DQLab';
```

---

## 3️⃣ Filter Angka

Filter angka digunakan untuk menyaring data numerik seperti harga.

### 📘 Quiz 3

**Soal:** Tampilkan produk dengan `harga` di atas 50.000.

**Query (Jawaban):**

```sql
SELECT *
FROM ms_produk
WHERE harga > 50000;
```

---

## 4️⃣ Operand AND

Operator `AND` digunakan untuk menampilkan data yang harus memenuhi **semua kondisi**.

### 📘 Quiz 4

**Soal:** Tampilkan produk dengan `harga` di bawah 50.000 dan `nama_produk` tertentu.

**Query (Jawaban):**

```sql
SELECT *
FROM ms_produk
WHERE harga < 50000
  AND nama_produk = 'Pulpen DQLab';
```

> Catatan: Jika kondisi tidak terpenuhi, query tidak akan menampilkan hasil.

---

## 5️⃣ Quiz 5 – Proyek dari Cabang A

### 📘 Studi Kasus

Menampilkan data transaksi penjualan dengan ketentuan:

* Total transaksi **≥ IDR 100.000**
* Kolom yang ditampilkan:

  * kode_pelanggan
  * nama_produk
  * qty
  * harga
  * total
* Data diurutkan dari **total terbesar**

### 📘 Contoh Tabel: `tr_penjualan`

| kode_pelanggan | nama_produk          | qty | harga |
| -------------- | -------------------- | --- | ----- |
| polibest01     | Kotak Pensil DQLab   | 2   | 62500 |
| polibest02     | Pulpen DQLab         | 10  | 8000  |
| polibest03     | Flashdisk DQLab 64GB | 2   | 55000 |

---

### 📘 Query (Jawaban Quiz 5)

```sql
SELECT
    kode_pelanggan,
    nama_produk,
    qty,
    harga,
    qty * harga AS total
FROM tr_penjualan
WHERE qty * harga >= 100000
ORDER BY total DESC;
```

---

## ✅ Penutup

Dengan memahami penggunaan klausa `WHERE` beserta operator `AND` dan `OR`, pengguna dapat melakukan penyaringan data secara lebih spesifik dan sesuai kebutuhan. Materi ini menjadi dasar penting sebelum mempelajari query lanjutan seperti `JOIN`, `GROUP BY`, dan `HAVING`.

---

## 🔗 Referensi

* [https://docs.google.com/document/d/1HObh9ABPvN6uH0oHh6juzymhL8hRdyz_pndR8643fck/edit?usp=sharing]
* [https://www.mysql.com](https://www.mysql.com)
* [https://www.postgresql.org](https://www.postgresql.org)
* [https://learn.microsoft.com/sql](https://learn.microsoft.com/sql)
