# ✅ Day 18: Interactive Application Security Testing (IAST)

**Interactive Application Security Testing (IAST)** adalah metode pengujian keamanan aplikasi yang menggabungkan aspek dari [SAST (Static Application Security Testing)](../week-2/day-8-lab-sast-implementation-with-sonarcloud.md) dan [DAST (Dynamic Application Security Testing)](day-17-dynamic-application-security-testing-dast.md). IAST bekerja dengan memonitoring aplikasi dari dalam saat aplikasi sedang dijalankan, biasanya selama fase pengujian. IAST juga bisa disebut sebagai gray box testing.

## Cara Kerja IAST

IAST bekerja dengan menjalankan pemeriksaan pada base code aplikasi saat kode dijalankan oleh web server. Teknologi ini mengisi kesenjangan antara pengujian keamanan statis (SAST) dan pengujian keamanan aplikasi dinamis (DAST).

IAST dapat diimplementasikan sebagai bagian dari CI/CD Pipeline. Salah satu manfaat terbesar IAST adalah seperti analisis kode statis yang di mana IAST ini mampu menemukan masalah pada baris kode.&#x20;

Tools IAST bekerja pada bytecode (representasi terintermediasi dari kode program), umumnya alat tersebut dapat melakukan proses reverse-engineer untuk menganalisis kode intermediate dan mengidentifikasi masalah atau kerentanannya pada kode sumber yang sesuai. Dengan kata lain, alat tersebut dapat membantu menemukan dan memahami potensi masalah keamanan pada kode program asli berdasarkan analisis bytecode.

Perlu diingat IAST ini tidak seperti anti-malware tidak melakukan perbaikan. Tugas mereka hanya menemukan masalah keamanan dalam aplikasi seperti SQL Injection dan cross-site scripting (XSS) bukan untuk memperbaikinya. Dan setiap resiko keamanan yang ditemukan oleh IAST ini perlu diperbaiki secara manual oleh tim developer.

## Jenis-Jenis IAST

Secara umum, ada tiga kelas tool IAST yaitu:

### 1. Passive IAST

Sebagian besar tools hanya menyediakan sensor yang menempel pada aplikasi yang sedang berjalan. Jika sensor ini melihat sesuatu yang mencurigakan saat aplikasi berjalan, maka sensor ini akan melaporkannya pada Dashboard dari IAST. Tool ini biasanya diinduksi oleh QA Testing (Unit Test) dan hana mencakup kode yang termasuk dalam QA Testing.

### 2. Active IAST

Banyak pilihan IAST yang dibuat oleh pembuat DAST sebagai produk terpisah (tidak terintegrasi), sering disebut IAST yang diinduksi DAST (istilah yang awalnya digunakan oleh Gartner). Tools ini menggunakan DAST untuk mengaktifkan sensor IAST tapi tidak menyusun data dari dua sumber.

### 3. True IAST

Tools yang melebihi dari Active IAST yang dijuluki sebagai True IAST. Karena tools ini ada interaksi aktual antara elemen penginduksi (pemindai DAST) dan sensor IAST. Keduanya berkomunikasi dan saling mempengaruhi untuk memberikan hasil tes yang lebih baik, untuk mencapai tingkat False Positive yang sangat rendah dan sepenuhnya mengkonfirmasi bahwa itu adalah kerentanan. Semua hasil dari DAST dan IAST juga disusun menjadi antarmuka pelaporan.

## Jenis Sensor IAST

### 1. Invasive Sensor

Sebagian besar IAST  terutama Passive IAST biasanya bekerja bedasarkan sensor invasif yang berarti bahwa agar tools IAST berfungi, developer harus memperkenalkan perubahan pada source-code yang disebut sebagai instrumentasi.

Kelemahan dari pendekatan ini adalah bisnis harus mempertahankan dua cabang terpisah dari source code mereka yang dimana satu dengan sensor IAST dan satu tanpa sensor IAST. Yang berarti ini dapat menyebabkan kompleksitas ekstra dan dapat menyebabkan masalah baru pada organisasi.

### 2. Non-Invasive Sensor

Beberapa tools IAST menggunakan metode pemantauan yang berbeda. Sensor tidak ditempatkan dalam source code dan tidak memerlukan modifikasi kode apa pun. Sebaliknya, sensor disimpan langsung ke environment runtime pada sisi server dan "listen in (mendengarkan)" pada saat kode dijalankan oleh web server.

Tools yang menggunakan sensor non-invasif ini dapat memindai aplikasi tapa mengubah kode ataupun konfigurasi. Yang dalam praktiknya, developer tidak perlu menyiapkan kode lain untuk pengujian keamanan.

## Kelebihan dan Kekurangan IAST

### Kelebihan IAST

IAST pada dasarnya adalah kombinasi dari SAST dan DAST akan tetapi IAST berbeda dari SAST dan DAST, tapi kenapa kita menggunakannya?&#x20;

1. **Scans code in production:**\
   Manfaat terbesar IAST adalah kemampuannya untuk memindai kode yang benar-benar digunakan di produksi. Tools SAST cenderung membebani developer dengan false positive. Terkadang baris kode dapat menunjukkan masalah keamanan yang telah diatasi di bagian lain dari kode. IAST ini berfokus pada isu-isu yang benar-benar penting.
2. **Scans code in development:**\
   IAST juga dapat digunakan selama development. Beberapa tools IAST dilengkapi dengan integrasi IDE untuk memberikan umpan balik yang cepat kepada developer tentang fitur yang sedang dikembangkan oleh mereka.
3. **Quick Remediation:**\
   IAST menghubungkan masalah dengan lokasi kode, di situlah IAST berbeda dengan DAST. IAST memungkinkan user untuk meng-klik aplikasi untuk menemukan masalah dan memberikan rekomendasi perbaikan. Hanya karena kita belum pernah menguji kode kita, bukan berarti kode tersebut tidak akan memiliki kerentanan keamanan pada lingkungan produksi. Di sisi lain, waktu development sangat terbatas dan kita harus menginvestasikannya dengan bijak.

### Kekurangan IAST

1. **Tergantung bahasa pemrograman**\
   Kelemahan utama dari IAST adalah tergantung pada bahasa pemrograman. Meskipun beberapa tools tidak mengharuskan developer mengubah kode untuk menambahkan modul sensornya, tapi tools ini masih terikat pada teknologi tertentu. Jika developer kebetulan menggunakan teknologi yang kurang populer karena sangat sesuai dengan kasus developer, maka IAST bukan pilihan yang tepat untuk di implementasikan.
2. **Intensif Waktu**\
   Metode pengujian IAST mengharuskan developer untuk membangun dan menjalankan aplikasi (tidak demikian halnya dengan SAST) dan oleh karena itu memerlukan investasi waktu yang signifikan dalam jangka panjang. Ini mungkin tidak menjadi masalah ketika menggunakan plugin IDE karena umpan balik yang sangat cepat. Tetapi jika developer ingin membangun uji coba yang sangat besar berarti harus berjalan di semua rilis produksi dan segalanya akan melambat.
3. **Tidak memiliki cakupan kode 100%**\
   Kelemahan lain dari IAST adalah tidak dapat memindai semua kode. Meskipun menghapus banyak false positive, itu juga mengabaikan kualitas kode developer. Hanya karena developer tidak memikirkannya bukan berarti kode tidak akan dieksekusi pada saat produksi.

## Kesimpulan

Seperti halnya setiap metode pengujian keamanan, penting untuk menganalisis stack dan proses teknologi sebelum memilihnya. Tergantung pada bahasa pemgorgraman pilihan developer, IAST bahkan mungkin bukan pilihan. Dalam kasus ini developer harus kembali ke DAST, yang hanya memeriksa input dan output aplikasi dan tidak memindai kode.

Meskipun IAST dapat memberikan wawasan penting tentang keamanan aplikasi yang tidak dapat diturunkan menggunakan pendekatan SAST, IAST juga dapat memperlambat alur CI secara signifikan. **Oleh karena itu, solusi SAST mungkin menjadi pilihan yang lebih baik untuk aplikasi kita.**

## Resources

* [https://www.invicti.com/learn/interactive-application-security-testing-iast/](https://www.invicti.com/learn/interactive-application-security-testing-iast/)
* [https://owasp.org/www-project-devsecops-guideline/latest/02c-Interactive-Application-Security-Testing](https://owasp.org/www-project-devsecops-guideline/latest/02c-Interactive-Application-Security-Testing)
* [https://snyk.io/learn/application-security/iast-interactive-application-security-testing/](https://snyk.io/learn/application-security/iast-interactive-application-security-testing/)
