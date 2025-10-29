# Aplikasi Manajemen Yayasan Sahabat Quran

Aplikasi manajemen yang berbasis web 

## Fitur 

### santri
1. Login ()
2. Registrasi 
3. jadwal pribadi
4. tampilan kehadiran
5. manajemen tugas dan materi
6. pengumpulan tugas
7. riwayat nilai dan progres
8. rapor
9. manajemen tagihan iursn
10. verifikasi pembayaran
11. manajemen event

## Pengajar
1. login
2. jadwal pengajar
3. absen mandiri
4. manajemen kehadiran siswa
5. manajemen tugas dan materi
6. pancatatan nilai dan progres
7. manajemen rapor
8. rincian gaji

## Admin
1. login
2. manajemen registrasi santri
3. manajemen kelas
4. manajemen jadwal dan penempatan
5. tampilan absen (pengajar dan santri)
6. finalisasi rapor
7. manajemen event

## Keuangan 
1. login
2. kas umum
3. tagihan iursn
4. verifikasi pembayaran
5. perhitungan gaji pengajar
6. laporan laba rugi 

## Struktur file
```
/ysq-management-app
|
|-- /src                         # SOURCE CODE UTAMA
|   |-- /main
|       |-- /java                      # Logika Backend (Spring Boot/Java)
|       |   |-- /com/ysq/app
|       |       |-- /controller        # 1. PRESENTATION LAYER (API Endpoints)
|       |       |   |-- AuthController.java    # Login (FR.001)
|       |       |   |-- SantriController.java  # Mengelola permintaan Siswa
|       |       |   |-- KeuanganController.java# Mengelola permintaan Keuangan
|       |       |
|       |       |-- /service           # 2. APPLICATION LAYER (Business Logic)
|       |       |   |-- AbsensiService.java    # Logika Absensi (FR.004)
|       |       |   |-- KeuanganService.java   # Logika Gaji, Laba Rugi (FR.011)
|       |       |   |-- UserService.java       # Logika Pendaftaran, Hak Akses
|       |       |
|       |       |-- /model             # 3. DATA LAYER (Entitas OOP/JPA)
|       |       |   |-- User.java              # Class Induk (Inheritance)
|       |       |   |-- Santri.java            # Class Anak dari User
|       |       |   |-- Pengajar.java          # Class Anak dari User
|       |       |   |-- Absensi.java           # Class untuk data kehadiran
|       |       |
|       |       |-- /repository        # 3. DATA LAYER (Akses Database)
|       |       |   |-- UserRepository.java
|       |       |   |-- SantriRepository.java
|       |       |   |-- AbsensiRepository.java
|       |       |
|       |       |-- YsqApplication.java        # Main Class Spring Boot
|       |
|       |-- /resources                 # Konfigurasi & Frontend Sederhana
|       |   |-- application.properties # Konfigurasi DB PostgreSQL, JWT
|       |   |-- /db/migration          # Skema DB (Flyway Migrations)
|   |       |   |-- V1__create_initial_tables.sql
|   |       |
|   |       |-- /templates             # Tampilan (Thymeleaf/HTML)
|   |           |-- login.html
|   |           |-- dashboard.html
|   |
|   |-- /test                          # UNIT TESTING
|       |-- /com/ysq/app/service
|           |-- AbsensiServiceTest.java # Uji coba logika Absensi (FR.004)
|
|-- /docs                      # DOKUMENTASI & PERANCANGAN
|   |-- SKP_Yayasan_Sahabat_Quran.md
|   |-- FR_DETAILS             # Folder yang berisi FR.001, FR.004, FR.011, dst.
|
|-- build.gradle               # Build Tool (Gradle)
|-- .gitignore                 # Daftar file yang diabaikan (WAJIB ADA!)
|-- README.md                  # Dokumentasi Proyek
```

## Tech Stack
- Java 21
- Spring Boot 3.3.3
- PostgreSQL 17

## Dev
- gradle
- Spring Security + JWT
- Docker Compose
- OpenAPI / Swagger UI
- Flyway
- Testcontainers + JUnit 5
- Playwright
- Jacoco
- Checkstyle & Spotless
- SonarLint
