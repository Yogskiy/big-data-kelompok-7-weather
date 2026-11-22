# Panduan Pengambilan Screenshot Tugas Minggu 10 (Bagian E.4)

Sesuai instruksi **Bagian E.4 Tugas Minggu 10**, berikut adalah **5 screenshot wajib** yang perlu Anda ambil dari notebook `Source_Code/ETL_Pipeline.ipynb` (dan Dashboard Supabase bila dihubungkan ke akun Supabase Anda) lalu simpan ke dalam folder `Screenshots/` ini:

1. **`01_Proses_Extract.png`**
   - Ambil *screenshot* output **Sel Bagian 1.b & 1.c** di `ETL_Pipeline.ipynb` yang menampilkan log `[INFO] Proses Extract dimulai...`, daftar `[1/12] Bandung` s.d. `[12/12] Tasikmalaya`, serta ringkasan `210,528 baris x 23 kolom`.
2. **`02_Proses_Transform.png`**
   - Ambil *screenshot* output **Sel Bagian 2.b/2.c & 2.d/2.e** di `ETL_Pipeline.ipynb` yang menampilkan log `[Cleaning 1/4]` s.d. `[Transform 3/3]` dan tabel `PERBANDINGAN KONDISI DATA SEBELUM VS. SESUDAH TRANSFORMASI`.
3. **`03_Proses_Load.png`**
   - Ambil *screenshot* output **Sel Bagian 3.c** di `ETL_Pipeline.ipynb` yang menampilkan log `[INFO] Proses Load dimulai...`, `[Load 1/3] Tabel 'cuaca_jabar_hourly' berhasil dimuat: 210,528 baris x 26 kolom`, hingga `[INFO] Data berhasil disimpan ke target storage.`
4. **`04_Data_Tersimpan_di_Target_Storage.png`**
   - Ambil *screenshot* output **Sel Bagian 3.d & 3.e** (`VERIFIKASI PEMBACAAN KEMBALI (READ-BACK) DARI TARGET STORAGE` dan hasil query SQL tabel `cuaca_jabar_city_summary`), **ATAU** screenshot tampilan **Table Editor (`cuaca_jabar_hourly` & `cuaca_jabar_city_summary`) di Dashboard Web Supabase**.
5. **`05_Hasil_Eksekusi_ETL_Pipeline_dan_Testing.png`**
   - Ambil *screenshot* output **Sel Bagian 4 (`run_etl_pipeline()`)** dan **Sel Bagian 5 (`TABEL 1: HASIL PENGUJIAN DAN VALIDASI ETL PIPELINE` & `TABEL 2: PERBANDINGAN JUMLAH DATA PADA SETIAP TAHAPAN ETL`)**.

---

## Cara Menghubungkan ke Akun Cloud Supabase (Opsional, 1 Menit)

Notebook `ETL_Pipeline.ipynb` sudah dilengkapi koneksi otomatis ke **Supabase PostgreSQL**:
1. Buka proyek Anda di [https://supabase.com/dashboard](https://supabase.com/dashboard).
2. Klik tombol **Connect** di bagian atas → salin **URI (Transaction Pooler / Session Pooler, port 6543 atau 5432)**.
3. Di dalam `ETL_Pipeline.ipynb` pada **Sel Bagian 3 (`code_load_func`)**, isi variabel `SUPABASE_DB_URL`:
   ```python
   SUPABASE_DB_URL = "postgresql+psycopg2://postgres.<PROJECT_REF>:<PASSWORD>@aws-0-ap-southeast-1.pooler.supabase.com:5432/postgres"
   ```
4. Jalankan sel tersebut (`pip install psycopg2-binary sqlalchemy`), maka tabel `cuaca_jabar_hourly` (210.528 baris) dan `cuaca_jabar_city_summary` (12 baris) akan langsung muncul di **Table Editor Supabase** Anda!
