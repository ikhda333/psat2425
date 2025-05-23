# Penilaian Sumatif Akhir Tahun
## Mapil DevOps XI TJKT 1 - Penilaian Praktek
### SMKN 1 Banyumas - TA. 2024 2025


#
# Cara mendeploy Aplikasi
Download file dari Paknux di repositorynya Paknux •> Ekstrak file yang sudah di download ke folder (data D) atau folder lain •> Masuk pada aplikasi VS Codex (untuk membuat terminal) •> Lalu klik file pada menu atas kiri •> Pilih open folder dan cari folder yang sudah terinstall •> Selanjutnya simpan per file menggunakan (ctrl+s) •> Berikutnya buat file baru ".env" klik enter •> Masuk ke Git Hub dan sign in Create a new repository lalu push •> Kembali lagi ke VS Code •> Klik new terminal •> Masukkan perintah dengan teliti, tuliskan 
- $  git  --version
- $  git  config --global  user.name 
- $  git  config  --global  user.email 
- $  git  init 
- $  git  remote add origin 
- $  git  branch  -M  main 
- $  git  add  . 
- $  git  commit  -m  "first commit" 
- $  git  push  -u  origin  main 

</br> •> Jika sudah silahkan login Aws Academy Canvas menggunakan akun masing-masing •> Pada dasboard klik Aws Academy Learner Lab •> Klik moduls •> Cari meluncurkan aws dan Klik •> Klik Start lab •>  Lalu pilih Aurora dan RDS •> Klik database (Jika sudah ada database tidak perlu membuat lagi) •> Selanjutnya ke EC2 •> Klik instances •> Buat baru dengan klik launch instances •> Isi name and tags sesuai yang diinginkan •> Pilih Ubuntu •> Biarkan t2.micro •> Keypair wajib  vockey •> Pada Network Setting ganti yang Firewall (Security Groups) Klik Select Existing Security Group •> Scroll lalu ubah pada Common Security Groups pilih SGServerWeb •> Scroll lagi klik Advanced Details •> Isi bagian user data-optional •> Masukkan perintah script
```
#!/bin/bash
echo '#!/bin/bash
sudo apt update -y
sudo apt install -y apache2 php php-mysql libapache2-mod-php mysql-client
sudo rm -rf /var/www/html/{,.}
sudo git clone [repository githubmu] /var/www/html
sudo chmod -R 777 /var/www/html
echo DB_USER=[username rds] > /var/www/html/.env
echo DB_PASS=[password rds]  >> /var/www/html/.env
echo DB_NAME=[nama database]  >> /var/www/html/.env
echo DB_HOST=[endpoint rds] >> /var/www/html/.env
sudo apt install -y openssl
sudo a2enmod ssl
sudo a2ensite default-ssl.conf
sudo systemctl reload apache2' > /home/ubuntu/otomatis.sh

chmod +x /home/ubuntu/otomatis.sh  
```
•> Pada perintah diatas gantilah kalimat yang ada didalam tanda kurung sesuai dengan milik masing-masing •> Lalu launch instance •> Jika sudah succes klik instances •> Klik instances id •> Klik connect •> Lalu Jalankan dengan $ ./otomatis.sh•> Lalu copy ip public dan buka di new tab •> Lalu isi bagian login dengan Username dan Password •> Jika sudah jadi nanti muncul halaman penilaian Sumatif Akhir Tahun isilah bagian Input data siswa sesuai dengan data diri masing-masing dan Simpan.