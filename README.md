# Tugas-Program-Komnum-R09
Program untuk Tugas Komputasi Numerik Nomor 8 ini menggunakan metode **Newton-Raphson** untuk mencari akar dari suatu fungsi polinomial. Program ini juga menampilkan hasil iterasi dalam dua versi:

- Tanpa pembulatan  
- Dengan pembulatan khusus menggunakan fungsi `Flounder` (*Float Rounder*)

---

##  Fungsi-Fungsi dalam Program

### Fungsi utama (`F`)
```python
def F(x):
    return x**3 + 6 * x**2 - 19 * x - 84
```

### Turunan fungsi (`Df`)
```python
def Df(x):
    return 3 * x**2 + 12 * x - 19
```

### Fungsi pembulatan khusus (`Flounder`)
```python
def Flounder(x):
    if ((x * 1000) % 10 >= 5):
        return (((x * 100) - ((x * 100) % 1)) / 100 + 0.01)
    else:
        return (((x * 100) - ((x * 100) % 1)) / 100)
```

Fungsi `Flounder(x)` membulatkan angka hingga dua digit di belakang koma:

- Jika angka ketiga di belakang koma **≥ 5**, maka dibulatkan **ke atas**
- Jika kurang dari 5, maka tetap **apa adanya**

---

##  Langkah-Langkah Algoritma Newton-Raphson

1. Inisialisasi nilai awal:
```python
x = -4
```

2. Akar sebenarnya yang dituju:
```python
xt = -3
```

3. Gunakan rumus iteratif Newton-Raphson:
```python
x = x - F(x) / Df(x)
```

4. Tampilkan hasil iterasi:
```python
print("Iterasi ke -", i, ":\nTanpa pembulatan:", x, "\nDengan pembulatan:", Flounder(x), "\n")
i += 1
```

5. Ulangi hingga nilai mendekati `xt`. Karena `x` mungkin tidak pernah sama persis dengan `xt`, maka sebaiknya gunakan batas toleransi:
```python
while abs(x - xt) > 1e-6:
```

---
