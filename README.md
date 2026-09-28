# Tugas Mandiri 2

**Nama :** Hairunisa Aulia Daulay

**NIM :** 1251170172

**Mata Kuliah :** Algoritma dan Struktur Data
# Tugas: Analisis Sistem Buku Modern
## 1. Analisis Komponen
### 1.1 Variabel dan Tipe Data

| NO.| Nama Variabel | Tipe Data |                Keterangan                        |
|---|---------------|------------|--------------------------------------------------|
| 1. | is_member     | Boolean   | Status keanggotaan pelanggan (member/non member) |
| 2. | jumlah_buku   | Integer   | Jumlah buku yang dibeli pelanggan                |
| 3. | total_awal    | Real      | Total belanja awal sebelum diskon                |
| 4. | diskon        | Real      | Besaran presentase potongan Harga                |
| 5. | nominal_diskon| Real      | Jumlah nominal potongan Harga 	            |
| 6. | total-bayar   | Real      | Nominal akhir yang harus dibayarkan              |

### 1.2. Jenis Struktur Kontrol yang Digunakan
a. Sequence: Menjalankan proses input, perhitungan diskon, perhitungan total bayar, hingga output secara berurutan.
b. Iteration (Validation Loop): Mengulang proses input total_awal dan jumlah_buku selama nilai yang dimasukkan belum valid (total_awal < 0 atau jumlah_buku < 1).
c. Selection (Nested IF): Menentukan besaran diskon berdasarkan status member, nilai total_awal, dan jumlah_buku.

### **2. Penyusunan Pseudocode**
```
Program HitungBayarHargaBuku

DEKLARASI:
* is_member: Boolean
* jumlah_buku: integer
* total_awal: real
* diskon: real
* nominal_diskon: real
* total_bayar: real

INPUT(total_awal)
INPUT(jumlah_buku)

WHILE (total_awal < 0) OR (jumlah_buku < 1) DO
    OUTPUT("Input tidak valid, silakan input ulang")
    INPUT(total_awal)
    INPUT(jumlah_buku)
ENDWHILE
SAMPAI (total_awal >= 0) AND (jumlah_buku >= 1)

INPUT(is_member)

IF (is_member = true) THEN
    IF (total_awal >= 200000) AND (jumlah_buku >= 3) THEN
        nominal_diskon ← total_awal * 0.15
    ELSE
        nominal_diskon ← total_awal * 0.10
    ENDIF
ELSE
    IF (total_awal >= 300000) THEN
        nominal_diskon ← total_awal * 0.05
    ELSE
        nominal_diskon ← 0
    ENDIF
ENDIF

total_bayar ← total_awal - nominal_diskon

OUTPUT(nominal_diskon)
OUTPUT(total_bayar)
END PROGRAM
```

## TRACE TABLE (uji logika)
### Kasus A
Input: is_member = true, total awal = 250000, jumlah_buku = 2
| langkah | is_member | total_awal | jumlah_buku | validasi loop | persen_diskon | nominal_diskon | total_bayar |
| ------ |------------|------------|-------------|---------------|---------------|----------------|--------------|
| 1  | True      |   250000   |     4       | Lolos (total_awal ≥ 0 dan jumlah_buku ≥ 1 | - | - | - |
| 2 | True | 250000 | 4 | - | Cek: total awal ≥ 200000 (Ya) DAN jumlah_buku ≥ 3 (Ya) → 0.15 | - | - | - |
| 3 | True | 250000 | 4 | - | 0.15 | 250000 x 0.15 = 37500 | - | 
| 4 | True | 250000 | 4 | - | 
