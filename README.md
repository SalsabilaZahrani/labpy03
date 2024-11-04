Latihan 1 : latihan1.py
1. Tampilkan n bilangan acak yang lebih kecil dari 0.5
2. Nilai n diisi pada saat runtime
3. Anda bisa menggunakan kombinasi while dan for untuk menyelesaikannya
4. Gunakan fungsi random() yang dapat diimport terlebih dahulu
JAWAB :
import random

# Meminta input nilai n dari pengguna
n = int(input("Masukkan jumlah bilangan acak yang ingin dihasilkan: "))

# Counter untuk menghitung jumlah bilangan acak yang telah dihasilkan
count = 0

# Menghasilkan dan menampilkan n bilangan acak yang lebih kecil dari 0.5
while count < n:
    angka_acak = random.random()  # Menghasilkan bilangan acak antara 0 dan 1
    if angka_acak < 0.5:
        print(angka_acak)
        count += 1
PENJELASAN :
1. Program meminta pengguna untuk memasukkan nilai n, yaitu jumlah bilangan acak yang ingin dihasilkan.
2. Variabel count digunakan untuk melacak jumlah bilangan acak yang telah dihasilkan dan ditampilkan.
3. While loop berjalan hingga jumlah bilangan yang dihasilkan (count) mencapai nilai n.
4. Fungsi random.random() menghasilkan bilangan acak antara 0 dan 1.
5. Jika bilangan acak yang dihasilkan lebih kecil dari 0.5, bilangan tersebut dicetak, dan count bertambah 1.

Masukkan jumlah bilangan acak yang ingin dihasilkan:3  
0.17296839460525404
0.027140077060395673
0.138745226982393

Latihan 2 : latihan2.py
latihan2.py
Seorang pengusaha menginvestasikan uangnya untuk memulai usahanya dengan modal
awal 100 juta, pada bulan pertama dan kedua belum mendapatkan laba. pada bulan ketiga
baru mulai mendapatkan laba sebesar 1% dan pada bulan ke 5, pendapatan meningkat 5%,
selanjutnya pada bulan ke 8 mengalami penurunan keuntungan sebesar 2%, sehingga laba
menjadi 3%. Hitung total keuntungan selama 8 bulan berjalan usahanya.
JAWAB :
# Modal awal
modal_awal = 100_000_000  # 100 juta

# Persentase laba per bulan (sesuai kondisi)
laba_per_bulan = [0, 0, 0.01, 0.01, 0.05, 0.05, 0.05, 0.03]

# Menghitung total keuntungan selama 8 bulan
total_keuntungan = 0
for bulan, laba in enumerate(laba_per_bulan):
    keuntungan_bulan_ini = modal_awal * laba
    total_keuntungan += keuntungan_bulan_ini
    print(f"Bulan {bulan+1}: Keuntungan = {keuntungan_bulan_ini:.2f}")

# Output total keuntungan selama 8 bulan
print(f"Total Keuntungan selama 8 bulan: {total_keuntungan:.2f}")
PENJELASAN :
1. Modal_awal adalah modal awal yang diinvestasikan pengusaha.
2. Laba_per_bulan adalah daftar persentase laba per bulan sesuai dengan kondisi yang diberikan.
3. Loop for digunakan untuk menghitung keuntungan per bulan berdasarkan persentase laba yang telah ditentukan.
4. Hasil total_keuntungan selama 8 bulan akan dicetak di akhir.
5. Jalankan kode ini untuk mendapatkan hasil total keuntungan dalam 8 bulan.

Bulan 1: Keuntungan = 0.00
Bulan 2: Keuntungan = 0.00
Bulan 3: Keuntungan = 1000000.00
Bulan 4: Keuntungan = 1000000.00
Bulan 5: Keuntungan = 5000000.00
Bulan 6: Keuntungan = 5000000.00
Bulan 7: Keuntungan = 5000000.00
Bulan 8: Keuntungan = 3000000.00
Total Keuntungan selama 8 bulan: 20000000.00

Latihan 3 : latihan3.py
latihan3.py
Buat program yang mensimulasikan mesin ATM sederhana. Pengguna memiliki saldo awal
sebesar Rp 1.000.000, dan dapat menarik uang hingga saldo habis atau memilih untuk
keluar.
JAWAB : 
# Saldo awal
saldo = 1_000_000

# Fungsi untuk menampilkan menu dan menjalankan simulasi ATM
def atm():
    global saldo
    while True:
        print("\n=== Selamat Datang di Mesin ATM ===")
        print("1. Cek Saldo")
        print("2. Tarik Tunai")
        print("3. Keluar")
        
        # Meminta pilihan dari pengguna
        pilihan = input("Pilih menu (1/2/3): ")
        
        if pilihan == '1':
            # Tampilkan saldo saat ini
            print(f"Saldo Anda saat ini: Rp{saldo:,}")
        
        elif pilihan == '2':
            # Meminta jumlah penarikan
            try:
                jumlah_tarik = int(input("Masukkan jumlah yang ingin ditarik: Rp"))
                
                # Mengecek apakah saldo mencukupi
                if jumlah_tarik > saldo:
                    print("Saldo tidak mencukupi. Silakan masukkan jumlah yang lebih kecil.")
                elif jumlah_tarik <= 0:
                    print("Jumlah penarikan tidak valid.")
                else:
                    saldo -= jumlah_tarik
                    print(f"Penarikan berhasil. Sisa saldo Anda: Rp{saldo:,}")
            
            except ValueError:
                print("Masukkan jumlah dalam angka.")
        
        elif pilihan == '3':
            # Keluar dari program
            print("Terima kasih telah menggunakan ATM. Selamat tinggal!")
            break
        
        else:
            print("Pilihan tidak valid. Silakan pilih menu yang tersedia.")

# Menjalankan program ATM
atm()

PENJELASAN :
1. Saldo diinisialisasi dengan nilai Rp1.000.000 sebagai saldo awal.
2. Fungsi atm() digunakan untuk menampilkan menu ATM dan menerima input dari pengguna.
3. Program menggunakan while loop untuk menampilkan menu secara terus-menerus hingga pengguna memilih opsi "Keluar".
4. Jika pengguna memilih "Cek Saldo", saldo saat ini ditampilkan.
5. Jika pengguna memilih "Tarik Tunai", program meminta input jumlah yang akan ditarik, memeriksa apakah saldo mencukupi, dan mengurangi saldo jika memungkinkan.
6. Jika pengguna memilih "Keluar", program akan berhenti.
7. Jalankan kode ini untuk melihat simulasi mesin ATM.

=== Selamat Datang di Mesin ATM ===
1. Cek Saldo
2. Tarik Tunai
3. Keluar
Pilih menu (1/2/3): 1
Saldo Anda saat ini: Rp1,000,000

=== Selamat Datang di Mesin ATM ===
1. Cek Saldo
2. Tarik Tunai
3. Keluar
Pilih menu (1/2/3): 2
Masukkan jumlah yang ingin ditarik: Rp350000
Penarikan berhasil. Sisa saldo Anda: Rp650,000

=== Selamat Datang di Mesin ATM ===
1. Cek Saldo
2. Tarik Tunai
3. Keluar
Pilih menu (1/2/3): 3
Terima kasih telah menggunakan ATM. Selamat tinggal!
