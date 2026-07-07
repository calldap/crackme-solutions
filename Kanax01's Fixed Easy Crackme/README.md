# Kanax01's Fixed Easy Crackme - Write-up

## Challenge Information

| Property | Value |
|----------|-------|
| Challenge | Kanax01's Fixed Easy Crackme |
| Platform | Windows |
| Language | C/C++ |
| Difficulty | Easy |

---

## Deskripsi

> cant get easier than this

---

## Tools

- Ghidra

---

## Analisis

Challenge ini meminta pengguna memasukkan sebuah password untuk mendapatkan pesan berhasil. Untuk mengetahui password tersebut, file executable dianalisis menggunakan **Ghidra**.

Langkah pertama adalah membuka fungsi utama (`main`) dan menelusuri proses validasi input. Dari hasil dekompilasi terlihat bahwa program melakukan pengecekan dalam dua tahap.

Pertama, program membandingkan panjang input yang dimasukkan dengan panjang password yang tersimpan. Jika panjangnya berbeda, program langsung menampilkan pesan bahwa password salah.

Selanjutnya, jika panjang input sesuai, program memanggil fungsi `memcmp()` untuk membandingkan isi input dengan password yang tersimpan di dalam binary.

```c
if ((inputLen == passWordLen) &&
    (memcmp(userInputPtr, passWordPtr, inputLen) == 0))
{
    printf("Congrats!!! You Cracked The Code");
}
```

Karena `memcmp()` membutuhkan alamat password sebagai argumen, langkah berikutnya adalah mencari dari mana pointer `passWordPtr` berasal.

Beberapa instruksi sebelum pemanggilan `memcmp()` ditemukan referensi berikut:

```asm
LEA passWordPtr,[s_EasyPassword]
```

String tersebut mengarah langsung ke sebuah data di dalam binary yang berisi password sebenarnya.

---

## Solution

Password yang benar adalah:

```text
EasyPassword
```

Setelah password dimasukkan, program akan menampilkan output:

```text
Congrats!!! You Cracked The Code
```

---

## Kesimpulan

Challenge ini dapat diselesaikan sepenuhnya menggunakan **static analysis** tanpa perlu melakukan patching maupun debugging. Dengan menelusuri penggunaan fungsi `memcmp()` dan melihat referensi string di Ghidra, password yang disimpan secara hardcoded dapat ditemukan dengan mudah. Challenge ini merupakan latihan yang baik untuk memahami proses validasi password sederhana pada sebuah executable Windows.
