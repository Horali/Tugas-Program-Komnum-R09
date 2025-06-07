# Tugas-Program-Komnum-R09

Program untuk Tugas Komputasi Numerik Nomor 8 ini menggunakan metode Newton-Raphson untuk mencari akar dari suatu fungsi polinomial. Program juga menampilkan hasil iterasi dalam dua format:

Tanpa pembulatan

Dengan pembulatan khusus menggunakan fungsi bernama Flounder (Float Rounder).

📘 Fungsi-Fungsi dalam Program
Fungsi utama (F):

python
Copy
Edit
def F(x):
    return x**3 + 6 * x**2 - 19 * x - 84
Turunan dari fungsi (Df):

python
Copy
Edit
def Df(x):
    return 3 * x**2 + 12 * x - 19
Fungsi pembulatan khusus (Flounder):

python
Copy
Edit
def Flounder(x):
    if ((x * 1000) % 10 >= 5):
        return (((x * 100) - ((x * 100) % 1)) / 100 + 0.01)
    else:
        return (((x * 100) - ((x * 100) % 1)) / 100)
Fungsi Flounder(x) membulatkan angka hingga dua digit di belakang koma:

Jika angka ketiga di belakang koma ≥ 5, maka dibulatkan ke atas

Jika kurang dari 5, maka dibulatkan tetap atau ke bawah

🔁 Langkah-Langkah Algoritma Newton-Raphson
Mulai dari tebakan awal: x = -4

Akar sebenarnya yang dituju: xt = -3

Gunakan rumus iteratif Newton-Raphson:

python
Copy
Edit
x = x - F(x) / Df(x)
Cetak hasil tiap iterasi:

python
Copy
Edit
print("Iterasi ke -", i, ":\nTanpa pembulatan:", x, "\nDengan pembulatan:", Flounder(x), "\n")
i += 1
Proses ini terus berjalan hingga nilai x mendekati xt.
Karena nilai x bisa jadi tidak pernah sama persis dengan xt, maka dalam praktik biasanya digunakan batas toleransi, seperti:

python
Copy
Edit
while abs(x - xt) > 1e-6:
