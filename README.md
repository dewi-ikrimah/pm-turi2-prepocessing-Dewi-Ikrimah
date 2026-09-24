# pm-turi2-prepocessing-Dewi-Ikrimah

Praktikum = Prepocessing & Feature Engineering

Mata Kuliah: Machine Learning (INF623325)

Nama: Dewi Ikrimah

NIM: 2488010049

**Ringkasan**

Praktikum ini membahas alur kerja prapemrosesan data (*data preprocessing*) dan rekayasa fitur (*feature engineering*) pada dataset karyawan. Tahapan mencakup penanganan nilai hilang (*missing values*), rekayasa fitur baru, penyandian data kategorikal (*Ordinal* dan *One-Hot Encoding*), pemisahan dataset (*train-test split*), serta penskalaan fitur (*feature scaling*) yang aman dari kebocoran data (*data leakage*).

Isi Repositori

Copy of PM_P4_Dewi Ikrimah_2488010049.ipynb

Temuan Utama

1. **Pencegahan Kebocoran Data (*Data Leakage*):** Pemisahan data latih dan data uji (*Train-Test Split*) harus dilakukan **sebelum** penskalaan fitur. Fungsi `.fit_transform()` hanya digunakan pada data latih (`X_train`), sedangkan data uji (`X_test`) hanya menggunakan `.transform()` agar evaluasi model tetap obyektif.
2. **Penyandian Variabel Kategorikal:** 
   * **Ordinal Encoding** digunakan pada fitur bertingkat seperti `pendidikan` (`SMA` $\rightarrow 0$, `S1` $\rightarrow 1$, `S2` $\rightarrow 2$).
   * **One-Hot Encoding** digunakan pada fitur nominal tanpa hierarki seperti `kota` dan `status` (`Tetap`/`Kontrak`) untuk mencegah bias asumsi nilai pada model.
3. **Penskalaan Fitur (*MinMaxScaler*):** Penskalaan berhasil mengompresi fitur numerik (`usia`, `pendapatan`, `pendidikan`) ke dalam rentang terbatas $0$ hingga $1$, terbukti dari nilai `min = 0.0` dan `max = 1.0` pada output statistik deskriptif data latih.
