# RR7's Secret Key Write-up

## Challenge Information

| Category | Reverse Engineering |
|----------|---------------------|
| Platform | Windows |
| Language | C/C++ |
| Difficulty | Easy |

## Description

> get the secret key

## Tools

- Ghidra

## Analysis

Setelah executable dibuka menggunakan **Ghidra**, fungsi `main` menunjukkan bahwa program meminta dua buah input. Nilai pertama dibandingkan dengan `0x21`. Jika benar, program akan meminta **Secret Key** dan membandingkannya dengan `0x66`.

```c
if (local_c == 0x21) {
    scanf("%i", &local_10);

    if (local_10 == 0x66) {
        printf("Congratulations, you have completed the challenge!");
    }
}
```

Nilai tersebut masih dalam format heksadesimal sehingga perlu dikonversi:

| Hex | Decimal |
|-----|---------|
| `0x21` | `33` |
| `0x66` | `102` |

## Flag / Solution

```
Enter Your Number : 33
Enter The Secret Key : 102
```

Output:

```
Congratulations, you have completed the challenge!
```

## Conclusion

Challenge ini dapat diselesaikan hanya dengan **static analysis**. Dengan membaca fungsi `main` menggunakan Ghidra, nilai pembanding dapat diketahui dan dikonversi dari heksadesimal ke desimal sehingga diperoleh input yang benar.
