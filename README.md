# linux-file-permissions
Beginner Guide to Linux File Permissions

# Understanding Linux File Permissions (Beginner Guide)

## Introduction
Linux adalah sistem operasi yang banyak digunakan pada server dan sistem penting.
Salah satu konsep dasar yang wajib dipahami dalam Linux adalah **file permissions**.

File permission menentukan siapa yang boleh mengakses suatu file atau direktori
serta apa saja yang boleh dilakukan terhadap file tersebut.
Pemahaman file permission sangat penting untuk menjaga **keamanan sistem Linux**.

---

## What is File Permission?
File permission adalah aturan yang mengatur hak akses terhadap file atau direktori di Linux.
Aturan ini menentukan apakah suatu user boleh:
- membaca file
- mengubah isi file
- menjalankan file

Dengan adanya file permission, Linux dapat mencegah akses tidak sah ke file penting.

---

## User Categories in Linux
Linux membagi hak akses menjadi tiga kategori utama:

| Category | Description |
|--------|------------|
| User (u) | Pemilik file |
| Group (g) | Grup pemilik file |
| Others (o) | Pengguna lain di sistem |

---

## Permission Types
Ada tiga jenis permission di Linux:

| Permission | Symbol | Description |
|-----------|--------|------------|
| Read | r | Membaca isi file |
| Write | w | Mengubah isi file |
| Execute | x | Menjalankan file |

Catatan:
Pada direktori, permission memiliki arti berbeda:
- Read (r)  → melihat daftar isi direktori
- Write (w) → menambah atau menghapus file di direktori
- Execute (x) → masuk ke dalam direktori (cd)

---

## Example File Permission
Gunakan perintah berikut untuk melihat permission file:

```bash
ls -l 
```
Perintah `ls -l` digunakan untuk menampilkan daftar file dan direktori
dalam format panjang (long listing), yang mencakup informasi permission,
pemilik file, grup, ukuran file, dan waktu modifikasi terakhir.

Contoh output:
```
-rwxr-xr--
```
- rwx r-x r--
│ │   │   │
│ │   │   └─ Others
│ │   └───── Group
│ └───────── User (Owner)
└─────────── Tipe file

Penjelasan:
- `-`    → file biasa (bukan direktori)
- `rwx`  → user dapat membaca, menulis, dan menjalankan file
- `r-x`  → group dapat membaca dan menjalankan file
- `r--`  → others hanya dapat membaca file

- Contoh output untuk direktori:
```
drwxr-x---
```
Penjelasan:
`d`     → direktori
`rwx`   → owner bisa masuk, membaca isi, dan mengubah direktori
`r-x`   → group bisa masuk dan melihat isi direktori
`---`   → others tidak memiliki akses

---

## Changing Permission Using chmod
Permission file dapat diubah menggunakan perintah `chmod`.

```bash
chmod 755 script.sh
```

Arti angka:
7 = rwx (read, write, execute)
5 = r-x (read, execute)
5 = r-x (read, execute)

---

## Why File Permission is Important?
File permission sangat penting karena:
- Mencegah akses ilegal
- Melindungi file sistem
- Mengurangi risiko malware
- Menjaga keamanan server Linux

---

## Common Mistakes
Kesalahan yang sering dilakukan pemula:
- Menggunakan permission 777
- Memberikan write access ke semua user
- Tidak memahami perbedaan permission file dan direktori

---

## Best Practices
Praktik terbaik dalam mengatur file permission:
- Gunakan permission seminimal mungkin
- Jangan sembarangan menggunakan sudo
- Selalu cek permission sebelum menjalankan file
- Gunakan group untuk manajemen akses

---

## Conclusion
File permission adalah dasar keamanan Linux yang wajib dipahami oleh pemula.
Dengan memahami konsep read, write, dan execute, kita dapat mengelola sistem Linux
dengan lebih aman dan terkontrol.

---

## References
- Linux Documentation
- `man chmod`
- `man ls`
