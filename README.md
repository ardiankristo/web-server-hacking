# Tugas Demo Keamanan Jaringan
### Kelompok **Web Server Hacking**:
- Inayah Surya (2110171047)
- Nauvalia Regina (2110171054)
- Ardian Kristya (2110171055)

#### 1. Scanning menggunakan nmap
- Buka kali linux
- nmap <ip target>
- ![nmap](http://ardiankristo.it.student.pens.ac.id/folder/Screenshot%202020-11-24%20224235.png)

#### 2. Reconnaissance / Footprinting menggunakan skipfish
- Buka cmd kali linux
- `apt-get install skipfish`
- skipfish -o <nama_file_dan_lokasi_output> <url_target> (ex: skipfish -o test http://192.168.52.129/)
- file output dapat dilihat di index.html pada folder output
> https://tools.kali.org/web-applications/skipfish
![Skipfish](https://i.ytimg.com/vi/parEtY4ncCg/maxresdefault.jpg)

#### 3. Reconnaissance / Footprinting menggunakan httprecon
- Download httprecon: https://www.google.com/search?client=firefox-b-d&q=download+httprecon
- Jalankan httprecon (apabila error starting coba run as administrator)
- ![httprecon](https://www.computec.ch/projekte/httprecon/introduction/screenshot.png)
- Masukkan url target pada field target
- Hasil footprinting dapat dilihat di **Fingerprint Details**

#### 4. Server Security Testing menggunakan Nessus
- Download Nessus: https://www.tenable.com/products/nessus
- Run Nessus
- Tambah scan baru dan masukkan IP address target
- ![Nessus](https://www.tenable.com/sites/all/themes/tenablefourteen/img/nessus/nessus-live-results_large.png)

#### 5. Cracking FTP menggunakan Kali Linux Hydra
- Buka Kali Linux
- `apt-get install hydra`
- Run command 
-- hydra -l **<file.username>** -P **<password>** ftp://**<ip_target>** atau
-- hydra -L **<file.txt_userlists>** -P **<file.txt_passwordlist>** ftp://**<ip_target>** atau 
-- kombinasi dari salah satu dari keduanya
- ex: hydra -L kristo -P /home/kali/Documents/Hatch/passlist.txt ftp://192.168.52.129
- ftp![hydra_ftp](http://ardiankristo.it.student.pens.ac.id/folder/Screenshot%202020-11-24%20183404.png)
- ssh![hydra_ssh](http://ardiankristo.it.student.pens.ac.id/folder/Screenshot%202020-11-24%20204226.png)

# Coming soon
#### 6. Server Security Testing menggunakan metasploit
