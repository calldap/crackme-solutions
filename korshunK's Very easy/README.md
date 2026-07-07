# korshunK's Very easy - Write-up

## Challenge Information

| Property | Value |
|----------|-------|
| Challenge | Very easy |
| Platform | Windows |
| Language | C/C++ |
| Difficulty | Easy |

---

## Deskripsi

> Hack password

Challenge ini merupakan crackme sederhana yang bertujuan untuk melatih dasar-dasar Reverse Engineering. Tugasnya adalah menemukan password yang benar agar program menampilkan pesan berhasil.

---

## Tools

- Ghidra

---

## Analisis

File executable dibuka menggunakan **Ghidra** dan dilakukan proses analisis otomatis. Selanjutnya, fungsi `main` dibuka melalui jendela **Decompiler** untuk melihat logika program.

Dari hasil dekompilasi terlihat bahwa program membaca input pengguna menggunakan fungsi `scanf()`, kemudian membandingkannya dengan sebuah string menggunakan fungsi `strcmp()`.

```c
scanf("%s", local_78);

iVar1 = strcmp(local_78, "your mum is very sexy");

if (iVar1 == 0)
{
    puts("you win!");
}
else
{
    printf("you loose!");
}
```

Karena fungsi `strcmp()` akan mengembalikan nilai `0` jika kedua string sama, maka password yang benar dapat langsung diketahui dari string yang digunakan sebagai argumen kedua pada fungsi tersebut.

---

## Solution

Password yang benar adalah:

```text
your mum is very sexy
```

Output program:

```text
you win!
```

---

## Kesimpulan

Challenge ini dapat diselesaikan sepenuhnya menggunakan **static analysis**. Dengan membaca hasil dekompilasi pada fungsi `main` di Ghidra, password dapat ditemukan tanpa perlu melakukan debugging ataupun patching. Challenge ini sangat cocok sebagai latihan awal untuk memahami penggunaan fungsi `strcmp()` dalam proses validasi password.

---

## Yang Dipelajari

- Membuka executable menggunakan Ghidra.
- Membaca pseudocode hasil dekompilasi.
- Memahami fungsi `scanf()` dan `strcmp()`.
- Menemukan password yang disimpan secara hardcoded pada binary.
