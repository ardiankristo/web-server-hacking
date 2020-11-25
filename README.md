# Tugas Demo Keamanan Jaringan
### Kelompok **Web Server Hacking**:
- Inayah Surya (2110171047)
- Nauvalia Regina (2110171054)
- Ardian Kristya (2110171055)

### Kebutuhan:
Web Server -> menggunakan nginx yang berjalan di VM Ubuntu
Mesin Penyerang -> menggunakan kali linux, berjalan di VM Kali Linux

#### 1. Scanning menggunakan nmap
- Buka kali linux
- Cek IP yang satu jaringan -> `arp -a`
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
- ex: `hydra -L kristo -P /home/kali/Documents/Hatch/passlist.txt ssh://192.168.52.129`
- ftp![hydra_ftp](http://ardiankristo.it.student.pens.ac.id/folder/Screenshot%202020-11-24%20183404.png)
- ssh![hydra_ssh](http://ardiankristo.it.student.pens.ac.id/folder/Screenshot%202020-11-24%20204226.png)

# Coming soon
#### 6. Server Security Testing menggunakan metasploit (belum ada yang sampai berhasil)

### Pencegahan
##### 1. Firewall
- `ufw enable`
- Restart server
- ufw dapat di configure juga untuk allow port port tertentu, biasanya pada web server port 80 di allow
>https://help.ubuntu.com/community/UFW
##### 2. Pakai password yang lebih aman
- enter as root
- `sudo passwd <username> <new_password>`
>cek kekuatan password: https://www.security.org/how-secure-is-my-password/
##### 3. Ganti Port untuk proses remote (ex: ftp, ssh)
- cek: `netstat -tulnp | grep ssh`
- `grep -i port /etc/ssh/sshd_config`
- `nano /etc/ssh/sshd_config` lalu cari Port 22
- ganti Port 22 dengan custom number
- `systemctl restart sshd`
##### 4. SSL (Untuk yang sudah memiliki DNS valid)
- SSL digunakan untuk enkripsi data yang dikirim melalui web server
- https://haydenjames.io/how-to-set-up-an-nginx-certbot/
