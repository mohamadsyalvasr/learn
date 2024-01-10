# ✅ Day 23: Signing

## Apa itu Signing?

Secara umum, signing atau penandatanganan adalah praktek menambahkan tanda tangan digital pada suatu informasi untuk memastikan keaslian, integritas, dan otentikasi informasi tersebut. Tanda tangan digital dibuat menggunakan teknik cryptographic and cryptographic keys untuk memberikan jaminan bahwa data atau entitas tersebut berasal dari sumber yang sah dan tidak mengalami perubahan yang tidak sah. Berikut adalah elemen kunci yang terlibat dalam signing secara umum:

1. Cryptographic keys**:**
   * Proses signing melibatkan penggunaan cryptographic keys, yang dapat terdiri dari sepasang private key dan public key. Private key digunakan untuk membuat tanda tangan, sementara public key digunakan untuk memverifikasi tanda tangan.
2. **Integritas:**
   * Tanda tangan digital digunakan untuk memastikan integritas informasi. Jika informasi mengalami perubahan, tanda tangan tidak akan valid saat diverifikasi.
3. **Keaslian:**
   * Signing digunakan untuk memberikan jaminan keaslian terhadap informasi atau entitas. Dengan memverifikasi tanda tangan, penerima dapat yakin bahwa informasi tersebut berasal dari sumber yang sah.
4. Autentikasi**:**
   * Proses signing membantu autentikasi entitas yang membuat tanda tangan. Cryptographic keys yang digunakan dapat dikaitkan dengan entitas atau individu tertentu.
5. **Keamanan Distribusi:**
   * Signing sangat penting dalam lingkungan di mana informasi atau entitas didistribusikan melalui jaringan atau berbagai kanal. Ini membantu melindungi informasi dari perubahan yang tidak sah selama distribusi.
6. **Jejak Audit:**
   * Informasi tambahan, seperti timestamp dan metadata, sering kali disertakan dalam signing untuk memberikan jejak audit. Hal ini memudahkan pelacakan waktu dan asal-usul informasi.
7. **Pengaturan Kebijakan:**
   * Beberapa organisasi atau lingkungan mungkin menetapkan kebijakan yang mengharuskan signing pada informasi tertentu untuk memenuhi standar keamanan dan regulasi.
8. **Pemulihan Kesalahan (non-repudiation):**
   * Signing juga dapat memberikan perlindungan terhadap tindakan "non-repudiation," yang berarti entitas yang membuat tanda tangan tidak dapat menyangkal tindakan tersebut di kemudian hari.
9. **Dokumentasi dan Kontrak:**
   * Dokumen kontrak, perjanjian, atau dokumen hukum sering kali ditandatangani secara digital untuk memberikan keabsahan dalam konteks hukum.

## SDLC Signing

Dalam konteks _Software Development Life Cycle_ (SDLC), signing atau penandatanganan dapat melibatkan beberapa elemen kunci untuk memastikan keamanan dan keaslian selama berbagai tahap pengembangan perangkat lunak. Berikut adalah beberapa aspek SDLC yang sering kali melibatkan signing:

1. **Source Code:**
   * Source code dapat ditandatangani untuk memastikan bahwa setiap perubahan atau kontribusi berasal dari pengembang yang sah. Proses ini dapat membantu dalam melacak kontribusi, mengelola versi, dan memastikan keaslian source code.
2. **Commit dan Version Control:**
   * Setiap commit ke sistem kontrol versi (version control system) seperti Git dapat ditandatangani untuk memverifikasi identitas pengembang dan mencegah perubahan yang tidak sah.
3. **Build Artifacts:**
   * Setelah proses kompilasi atau pembangunan (build), artefak perangkat lunak seperti biner, pustaka, atau paket instalasi dapat ditandatangani. Ini memastikan bahwa distribusi dan pemasangan perangkat lunak bersumber dari sumber yang sah.
4. **Continuous Integration/Continuous Deployment (CI/CD):**
   * CI/CD pipeline dapat melibatkan signing untuk memverifikasi integritas dan keaslian artefak yang dihasilkan selama siklus CI/CD, menjaga kualitas dan keamanan perangkat lunak.
5. **Release Management:**
   * Selama manajemen rilis, artefak rilis dan dokumentasi terkait dapat ditandatangani untuk memastikan keaslian dan integritasnya selama penyebaran dan distribusi.
6. **Dokumentasi Proyek:**
   * Dokumen proyek, seperti spesifikasi desain atau dokumen pengguna, dapat ditandatangani untuk memastikan bahwa dokumen tersebut tidak dimanipulasi dan datang dari sumber yang sah.
7. **Sertifikat dan Cryptographic Keys:**
   * Sertifikat dan cryptographic keys yang digunakan dalam proyek (seperti HTTPS, SSL/TLS certificates) dapat di-signing untuk menjamin autentikasi dan keamanan komunikasi.
8. **Security Policies dan Configuration Files:**
   * Security Policies dan Configuration Files yang digunakan dalam aplikasi dapat ditandatangani untuk memastikan bahwa mereka tidak dimanipulasi oleh pihak yang tidak berwenang.
9. **Container Images:**
   * Dalam konteks containerization, container image dapat ditandatangani untuk memastikan integritas dan keamanan aplikasi saat dijalankan di containerization.
10. **Dokumen Audit dan Compliance:**
    * Dokumen yang terkait dengan audit dan kepatuhan (compliance) dapat ditandatangani untuk memberikan jaminan bahwa proses pengembangan dan penyebaran mematuhi standar dan regulasi yang berlaku.

## Resiko Tanpa Signing

Jika dalam Software Development Life Cycle (SDLC) tidak menggunakan signing, ada beberapa risiko dan potensi bahaya yang dapat timbul, terutama terkait dengan keamanan dan integritas perangkat lunak. Berikut adalah beberapa bahaya yang dapat terjadi jika signing tidak diterapkan dengan baik dalam SDLC:

1. **Kehilangan Keaslian dan Integritas:**
   * Tanpa signing, sulit untuk memastikan keaslian dan integritas perangkat lunak. Ini meningkatkan risiko penyisipan perubahan yang tidak sah atau perangkat lunak palsu, yang dapat membahayakan keamanan dan kinerja sistem.
2. **Resiko Modifikasi yang Tidak Terdeteksi:**
   * Ketika perangkat lunak tidak ditandatangani, tidak ada mekanisme yang dapat mendeteksi modifikasi atau perubahan yang tidak sah. Ini meninggalkan potensi untuk serangan seperti injeksi kode atau perubahan berbahaya pada aplikasi.
3. **Tidak Dapat Diverifikasi Sumber Perangkat Lunak:**
   * Tanpa signing, sulit untuk mengonfirmasi sumber asal perangkat lunak. Ini dapat memberikan peluang bagi penyerang untuk mendistribusikan perangkat lunak yang dimodifikasi atau berbahaya sebagai perangkat lunak yang sah.
4. **Kerentanan Terhadap Perubahan Tak Terduga:**
   * Perangkat lunak yang tidak ditandatangani dapat menjadi rentan terhadap perubahan tak terduga, baik disengaja atau tidak disengaja, yang dapat merusak fungsionalitas dan keamanan aplikasi.
5. **Kepatuhan dan Audit Tidak Dapat Diverifikasi:**
   * Banyak organisasi dan proyek harus mematuhi standar keamanan dan regulasi tertentu. Tanda tangan digital membantu dalam memverifikasi kepatuhan dan memberikan jejak audit untuk proses SDLC.
6. **Penyalahgunaan Identitas dan Kerentanan terhadap Man-in-the-Middle (MITM):**
   * Tanpa signing, ada risiko penyalahgunaan identitas dan potensi serangan Man-in-the-Middle, di mana penyerang dapat menyusupkan perangkat lunak atau merubah aliran data tanpa diketahui oleh pihak yang terlibat.
7. **Versi dan Build Tidak Dapat Diverifikasi:**
   * Signing memainkan peran penting dalam memverifikasi versi perangkat lunak dan memastikan bahwa build yang didistribusikan berasal dari sumber yang sah dan tidak dimodifikasi.
8. **Pengurangan Kepercayaan Pengguna dan Pengembang:**
   * Jika perangkat lunak tidak ditandatangani dengan baik, hal ini dapat mengurangi kepercayaan pengguna dan pengembang terhadap keamanan dan keaslian perangkat lunak.
9. **Kerugian Reputasi dan Hukuman Hukum:**
   * Kegagalan dalam menjaga keamanan dan integritas perangkat lunak dapat mengakibatkan kerugian reputasi dan mungkin berpotensi mendatangkan sanksi hukum jika kebocoran atau modifikasi menyebabkan dampak yang merugikan.

## Lab - SDLC Signing

### - Git Commit Signing

Berikut adalah langkah-langkah umum untuk melakukan signing pada Git commit:

1. **Buat GPG key:**
   *   Jika kamu belum memiliki GPG key, pertama-tama, kamu perlu membuatnya. Jalankan perintah berikut dengan menggantikan "your.email@example.com" dengan alamat email yang akan digunakan untuk GPG key:

       ```bash
       gpg --gen-key
       ```
2. **Tampilkan ID GPG key:**
   *   Setelah GPG key dibuat, kamu perlu menampilkan ID GPG key yang terkait dengan kunci tersebut. Gunakan perintah berikut:

       ```bash
       gpg --list-secret-keys --keyid-format LONG
       ```
3. **Konfigurasi Git dengan GPG key:**
   *   Konfigurasikan Git untuk menggunakan GPG key yang telah dibuat. Gantilah "YOUR\_GPG\_KEY\_ID" dengan ID GPG key yang kamu dapatkan dari langkah sebelumnya:

       ```bash
       git config --global user.signingkey YOUR_GPG_KEY_ID
       ```
4. **Sign Commit:**
   *   Sekarang, setiap kali kamu membuat commit, tambahkan opsi `-S` atau `--gpg-sign` untuk menandatangani commit:

       ```bash
       git commit -S -m "Commit message"
       ```
5. **Verifikasi Commit yang Ditandatangani:**
   *   Untuk memverifikasi commit yang ditandatangani, gunakan perintah:

       ```bash
       git log --show-signature
       ```
   * Jika commit ditandatangani dengan benar, kamu akan melihat informasi verifikasi, termasuk tanda tangan dan status yang menunjukkan bahwa commit tidak dimanipulasi.
6. **Pengaturan Otomatisasi Tanda Tangan:**
   *   Jika kamu ingin secara otomatis menandatangani semua commit, kamu dapat mengatur Git untuk melakukan hal tersebut dengan perintah:

       ```bash
       git config --global commit.gpgSign true
       ```
   * Dengan pengaturan ini, setiap kali kamu membuat commit, Git akan secara otomatis menandatangani commit menggunakan GPG key yang telah dikonfigurasi.

Dengan menggunakan tanda tangan GPG pada commit Git, kamu dapat meningkatkan keamanan dan memastikan bahwa setiap perubahan pada repositori berasal dari sumber yang sah. Ini sangat penting dalam kolaborasi tim dan lingkungan pengembangan perangkat lunak yang memerlukan integritas kode sumber.

