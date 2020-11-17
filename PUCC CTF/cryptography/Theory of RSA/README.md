# Theory of RSA

## Deskripsi
Bisakah kamu menemukan hasil dari angka dibawah ini menggunakan RSA ?
e = 150815
d = 1941
N = 435979

Format Flag : PUCC{hasilnya}

## Hint
http://doctrina.org/How-RSA-Works-With-Examples.html

https://sahandsaba.com/cryptography-rsa-part-1.html

## Proof of Concept
Solve menggunakan script python
```
e = 150815
d = 1941
N = 435979
print(pow(e, d, N))

```

## Flag
<details>
<summary>Tekan untuk melihat flag</summary>

    PUCC{133337}
</details>