# Tugas Demo Keamanan Jaringan
### Kelompok **Web Server Hacking**:
- Inayah Surya (2110171047)
- Nauvalia Regina (2110171054)
- Ardian Kristya (2110171055)

#### 1. Reconnaissance / Footprinting menggunakan skipfish
- Buka cmd kali linux
- `apt-get install skipfish`
- skipfish -o <nama_file_dan_lokasi_output> <url_target> (ex: skipfish -o test http://192.168.52.129/)
- file output dapat dilihat di index.html pada folder output
> https://tools.kali.org/web-applications/skipfish
![skipfish](https://i.ytimg.com/vi/parEtY4ncCg/maxresdefault.jpg)

#### 2. Reconnaissance / Footprinting menggunakan httprecon
- Download httprecon: https://www.google.com/search?client=firefox-b-d&q=download+httprecon
- Jalankan httprecon (apabila error starting coba run as administrator)
- ![httprecon](https://www.computec.ch/projekte/httprecon/introduction/screenshot.png)
- Masukkan url target pada field target
- Hasil footprinting dapat dilihat di **Fingerprint Details**

#### 3. Server Security Testing menggunakan Nessus
- Download Nessus: https://www.tenable.com/products/nessus
- Run Nessus
- Tambah scan baru dan masukkan IP address target
- ![nessus](https://www.tenable.com/sites/all/themes/tenablefourteen/img/nessus/nessus-live-results_large.png)

# Coming soon
#### 4. Cracking FTP menggunakan Kali Linux Hydra

#### 5. Server Security Testing menggunakan metasploit
