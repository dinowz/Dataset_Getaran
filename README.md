# Dataset Getaran Kendaraan

Dataset getaran tanah akibat kendaraan yang melintas, direkam dengan sensor IMU (GY-86) yang terhubung ke Raspberry Pi di tepi jalan. Dataset ini merupakan luaran **Hibah Penelitian On-Demand FMIPA UGM 2026** dengan judul *"Pengembangan Dataset Getaran Kendaraan Berbasis Sensor Seismik"* dan ditujukan untuk penelitian deteksi serta klasifikasi kendaraan berbasis sinyal getaran.

## Isi

- `vehicle_dataset.csv`: 2.969 frame fitur getaran yang sudah diberi label, berasal dari 6 rekaman di dua lokasi (`mipa` dan `teknik`).
- Label diperoleh dengan mencocokkan sinyal getaran dengan rekaman video di lapangan.

| Kelas | Keterangan | Jumlah frame |
| --- | --- | ---: |
| `no_vehicle` | Tidak ada kendaraan (derau latar) | 1.777 |
| `two_wheel` | Kendaraan roda dua | 746 |
| `four_wheel` | Kendaraan roda empat | 134 |
| `unknown` | Kendaraan tidak dapat dipastikan jenisnya | 312 |

## Kamus Data

| Kolom | Keterangan |
| --- | --- |
| `source_file` | Berkas rekaman asal (`lokasi/nomor_labeled.csv`) |
| `class_name` | Label kelas frame |
| `session_id` | ID sesi pengambilan data |
| `frame` | Nomor urut frame dalam satu rekaman |
| `start_ms` | Waktu mulai frame sejak awal rekaman (ms) |
| `hop_ms` | Selisih waktu terhadap frame sebelumnya (ms), umumnya 1.280 ms |
| `peak_hz` | Frekuensi dominan pada spektrum frame (Hz) |
| `peak_mg` | Amplitudo puncak spektrum (mg) |
| `rms_mg` | Nilai RMS getaran (mg) |
| `band_0_5_mg` | Energi getaran pada pita 0–5 Hz (mg) |
| `band_5_15_mg` | Energi getaran pada pita 5–15 Hz (mg) |
| `band_15_30_mg` | Energi getaran pada pita 15–30 Hz (mg) |
| `band_30_50_mg` | Energi getaran pada pita 30–50 Hz (mg) |

## Catatan

- Data kelas tidak seimbang (didominasi `no_vehicle` dan `two_wheel`), sehingga perlu diperhatikan saat melatih model.
- Variasi lokasi dan kondisi jalan masih terbatas; pengambilan data lanjutan direncanakan di lokasi dengan spesifikasi jalan yang berbeda.

## Tim Peneliti

Nur Achmad Sulistyo Putro, S.Si., M.Cs., Ph.D. (Ketua), Muhammad Faiz Rizal, Almira Ahadia Agustin, Salwa Fitri Azzahra. FMIPA Universitas Gadjah Mada.

Video dokumentasi pengambilan data: https://youtu.be/1kIKdL7bckw
