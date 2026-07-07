# Crackme Solutions

Repository ini berisi kumpulan write-up hasil penyelesaian challenge **CrackMe** dari **Crackmes.one** sebagai bagian dari proses belajar **Reverse Engineering**. Seluruh analisis dilakukan menggunakan **static analysis** dengan bantuan tools seperti Ghidra, kemudian didokumentasikan dalam Bahasa Indonesia.

> **Disclaimer**
>
> Repository ini dibuat hanya untuk tujuan edukasi. Seluruh challenge berasal dari sumber yang legal untuk dipelajari. Tidak ada malware aktif maupun file berbahaya yang didistribusikan dalam repository ini.

---

## Tujuan Repository

- Mempelajari dasar-dasar Reverse Engineering.
- Melatih penggunaan tools analisis binary.
- Mendokumentasikan proses analisis setiap challenge.
- Membangun portofolio Reverse Engineering selama perkuliahan.

---

## Tools

- Ghidra
- x64dbg
- Detect It Easy (DIE)
- PE-bear
- Strings

---

## Challenge List

| No | Challenge | Platform | Difficulty | Tools | Status |
|:--:|-----------|:--------:|:----------:|:-----:|:------:|
| 1 | RR7's Secret Key | Windows | Easy | Ghidra | ✅ Completed |
| 2 | Kanax01's Fixed Easy Crackme | Windows | Easy | Ghidra | ✅ Completed |
| 3 | korshunK's Very easy | Windows | Easy | Ghidra | ✅ Completed |

---

## Repository Structure

```text
crackme-solutions/
│
├── README.md
│
├── RR7-Secret-Key/
│   ├── README.md
│   └── screenshots/
│
├── Kanax01-Fixed-Easy-Crackme/
│   ├── README.md
│   └── screenshots/
│
└── korshunK-Very-Easy/
    ├── README.md
    └── screenshots/
```

---

## Learning Outcomes

Melalui repository ini saya mempelajari:

- Membuka executable menggunakan Ghidra.
- Membaca pseudocode hasil dekompilasi.
- Memahami alur eksekusi program.
- Menganalisis fungsi validasi seperti `strcmp()` dan `memcmp()`.
- Menemukan string yang disimpan secara hardcoded pada binary.
- Mendokumentasikan proses Reverse Engineering dalam bentuk write-up.

---

## Progress

- ✅ RR7's Secret Key
- ✅ Kanax01's Fixed Easy Crackme
- ✅ korshunK's Very easy
- ⏳ More challenges coming soon...

---

## Author

**Daffa Wahyu Prayudha**

S1 Teknik Komputer  
Universitas AMIKOM Yogyakarta

---

## License

Repository ini dibuat untuk keperluan pembelajaran dan dokumentasi pribadi. Seluruh hak cipta challenge tetap dimiliki oleh pembuat challenge masing-masing.
