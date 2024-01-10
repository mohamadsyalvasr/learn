# ✅ Day 14: Software Bill of Materials (SBOM)

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption><p><a href="http://chandan.opengrok.org/2019/02/sbom-and-sdlc.html">http://chandan.opengrok.org/2019/02/sbom-and-sdlc.html</a></p></figcaption></figure>

## Apa itu SBOM?

Software Bill of Materials (SBOM) adalah daftar lengkap dari semua komponen perangkat lunak, dependensi, dan metadata yang terkait dengan suatu aplikasi.

Dalam konteks SBOM, setiap komponen perangkat lunak diidentifikasi dan didokumentasikan, termasuk versi perangkat lunak, dependensi, dan informasi lainnya yang relevan. SBOM memungkinkan pemangku kepentingan, seperti pengembang perangkat lunak, manajer proyek, dan pengguna akhir, untuk memahami struktur dan komponen dari perangkat lunak tertentu.

Konsep BOM secara tradisional digunakan dalam proses manufaktur. Produsen menggunakan SBOM untuk melacak bagian-bagian yang digunakan untuk membuat produk. Jika cacat ditemukan pada suatu bagian tertentu, BOM memudahkan untuk menemukan bagian tersebut dan menyelesaikan masalahnya. SBOM memperluas konsep yang sama ke pengembangan perangkat lunak, memungkinkan pengguna dan vendor perangkat lunak mengetahui komponen mana yang bermasalah dan memperbaikinya.

## Mengapa SBOM itu penting ?

Berikut adalah beberapa alasan mengapa SBOM dianggap penting:

1. **Security and Risk Management:**
   * **Vulnerability Identification:** SBOM memungkinkan organisasi untuk mengidentifikasi kerentanan keamanan yang mungkin terdapat dalam komponen perangkat lunak. Dengan mengetahui komponen-komponen yang digunakan, organisasi dapat memantau pembaruan keamanan dan merespons potensi kerentanan.
   * **Risk Management:** Dengan informasi yang jelas tentang komponen perangkat lunak dan dependensinya, organisasi dapat lebih efektif mengelola risiko terkait dengan keamanan dan keandalan.
2. **Compliance and Auditing:**
   * **Regulatory Compliance:** Beberapa regulasi dan standar keamanan, seperti NIST Cybersecurity Framework dan GDPR, mewajibkan organisasi untuk memiliki pemahaman yang baik tentang komponen perangkat lunak yang digunakan. SBOM membantu organisasi memenuhi persyaratan ini.
   * **Auditing and Accountability:** SBOM menyediakan catatan yang dapat diverifikasi tentang komponen perangkat lunak, memudahkan proses audit dan memberikan akuntabilitas terkait dengan keamanan dan kepatuhan.
3. **Supply Chain Management and Availability:**
   * **Software Component Supply Chain Management:** Dengan mengetahui komponen-komponen perangkat lunak yang digunakan, organisasi dapat lebih efektif mengelola pasokan dan ketersediaan perangkat lunak yang diperlukan.
   * **Planning and Maintenance**: SBOM membantu dalam perencanaan pemeliharaan dan peningkatan perangkat lunak dengan memberikan visibilitas terhadap pembaruan dan versi komponen.
4. **Security Response:**
   * **Rapid Response to Threats:** Dengan memiliki SBOM, organisasi dapat merespons dengan cepat terhadap ancaman keamanan yang teridentifikasi dalam komponen perangkat lunak. Ini memungkinkan mitigasi cepat terhadap risiko yang mungkin muncul.

## Standar SBOM

Berikut adalah beberapa standar SBOM yang umum digunakan:

### Software Package Data Exchange (SPDX)

SPDX merupakan singkatan dari Software Package Data Exchange, sebuah standar terbuka yang digunakan untuk menyediakan informasi metadata tentang perangkat lunak. Tujuan utamanya adalah untuk memudahkan pertukaran data terkait lisensi perangkat lunak.

**Fitur Utama:**

* **Identifikasi Lisensi:** SPDX membantu dalam mengidentifikasi dan mendokumentasikan jenis lisensi perangkat lunak yang digunakan dalam suatu proyek.
* **Pertukaran Informasi:** Memungkinkan pertukaran data tentang komponen perangkat lunak dan lisensinya antara berbagai pihak secara konsisten.

**Manfaat:**

* **Kepatuhan Lisensi:** Mempermudah pengelolaan dan pemantauan kepatuhan lisensi perangkat lunak.
* **Transparansi:** Meningkatkan transparansi terkait komponen perangkat lunak dan lisensinya dalam suatu proyek.

### SWID (Software Identification)

SWID, atau Software Identification, adalah standar ISO/IEC 19770 yang bertujuan untuk memberikan cara standar untuk mengidentifikasi dan memberi label pada perangkat lunak dan instalasinya.

**Fitur Utama:**

* **Unik dan Konsisten:** Memberikan identifikasi unik dan konsisten untuk perangkat lunak, memudahkan manajemen inventaris.
* **Informasi Vendor dan Versi:** Mengandung informasi tentang vendor, versi perangkat lunak, dan komponen terkait.

**Manfaat:**

* **Manajemen Aset:** Mempermudah manajemen aset perangkat lunak dengan memberikan identifikasi yang konsisten.
* **Keamanan:** Membantu dalam pemantauan dan manajemen kerentanan perangkat lunak dengan memberikan informasi yang jelas.

### **CycloneDX:**

CycloneDX adalah format pertukaran data untuk informasi keamanan komponen perangkat lunak. Ini menyediakan cara standar untuk menyampaikan informasi tentang kerentanan perangkat lunak dan dependensinya.

**Fitur Utama:**

* **Format XML atau JSON:** Mendukung format data XML dan JSON untuk pertukaran informasi yang fleksibel.
* **Informasi Keamanan:** Menyediakan detail tentang kerentanan perangkat lunak dan dependensinya.

**Manfaat:**

* **Analisis Keamanan:** Membantu dalam menganalisis dan memitigasi risiko keamanan terkait dependensi perangkat lunak.
* **Integrasi Otomatis:** Dapat diintegrasikan secara otomatis dalam alur kerja pengembangan dan pengujian untuk meningkatkan keamanan perangkat lunak.

## **Praktik Terbaik Software Bill of Materials (SBOM)**

1. **Definisi Tujuan SBOM:** Pastikan pemahaman yang jelas mengenai tujuan SBOM dalam konteks pengembangan perangkat lunak. SBOM dapat digunakan untuk manajemen risiko keamanan, kepatuhan lisensi, dan pemantauan dependensi perangkat lunak.
2. **Pemutakhiran Berkala SBOM:** Lakukan pemutakhiran SBOM secara berkala, khususnya saat terjadi perubahan signifikan dalam kode sumber atau ketika ada pembaruan dependensi perangkat lunak. Ini memastikan konsistensi dan akurasi informasi.
3. **Pemisahan SBOM untuk Setiap Komponen:** Buat SBOM terpisah untuk setiap komponen perangkat lunak dalam proyek. Hal ini memudahkan identifikasi dan manajemen komponen secara terpisah, meningkatkan transparansi dan pemahaman.
4. **Gunakan Format Standar Seperti SPDX atau CycloneDX:** Pilih dan gunakan format SBOM yang diakui dan mendukung standar industri seperti SPDX (Software Package Data Exchange) atau CycloneDX. Ini mempermudah pertukaran data dan integrasi dengan alat-alat yang mendukung standar tersebut.
5. **Integrasi SBOM dalam Siklus Hidup Perangkat Lunak:** Integrasikan pembuatan dan pemeliharaan SBOM ke dalam alur kerja pengembangan perangkat lunak. Automatisasi proses ini dapat meningkatkan efisiensi dan memastikan keakuratan SBOM.
6. **Kepatuhan Lisensi:** Gunakan SBOM untuk memonitor dan memastikan kepatuhan lisensi perangkat lunak. Identifikasi dengan jelas jenis lisensi yang terkait dengan setiap komponen, dan pertimbangkan implikasi kepatuhan lisensi selama pengembangan.
7. **Dokumentasikan Ketergantungan dan Versi:** Dokumentasikan dengan jelas dependensi antar-komponen, termasuk versi perangkat lunak yang digunakan. Ini membantu dalam manajemen aset dan pemecahan masalah jika terjadi masalah ketergantungan.
8. **Keamanan Perangkat Lunak:** Gunakan SBOM untuk analisis keamanan perangkat lunak. Identifikasi dan pantau kerentanan yang mungkin muncul dari komponen perangkat lunak yang digunakan dalam proyek.
9. **Pertukaran SBOM dengan Pihak Ketiga:** Jika diperlukan, pertimbangkan pertukaran SBOM dengan pihak ketiga, seperti konsumen produk perangkat lunak atau pihak yang bertanggung jawab atas keamanan perangkat lunak.
10. **Pelatihan dan Kesadaran:** Beri pelatihan kepada tim pengembang dan pihak terkait mengenai pentingnya SBOM dan cara menggunakan informasi yang terkandung di dalamnya. Kesadaran ini dapat meningkatkan penggunaan SBOM secara efektif.

## Vulnerability database

_Vulnerability Database_ adalah basis data yang menyimpan informasi tentang berbagai kerentanan keamanan yang ditemukan dalam perangkat lunak atau sistem. Database ini mencatat detail tentang kerentanan tersebut, termasuk deskripsi, tingkat keparahan, dan langkah-langkah mitigasi atau perbaikan yang mungkin diperlukan. _Vulnerability Database_ membantu organisasi, pengembang perangkat lunak, dan profesional keamanan untuk menyadari dan mengatasi kerentanan yang dapat dieksploitasi oleh penyerang.

Beberapa contoh _Vulnerability Database_ terkenal termasuk **Common Vulnerabilities and Exposures (CVE)**, **National Vulnerability Database (NVD)** yang dikelola oleh National Institute of Standards and Technology (NIST), dan banyak lagi. CVE memberikan identifikasi unik untuk setiap kerentanan dan memberikan informasi standar agar dapat digunakan dan dipahami secara luas.

## CVSS

_Common Vulnerability Scoring System (CVSS)_ adalah suatu sistem untuk menilai tingkat keparahan kerentanan keamanan. CVSS memberikan skor numerik untuk setiap kerentanan, membantu organisasi dan profesional keamanan untuk memahami sejauh mana suatu kerentanan dapat membahayakan sistem atau perangkat lunak.

CVSS menggunakan sejumlah metrik untuk menentukan skor, termasuk tingkat kerentanan, kompleksitas eksploitasi, dampak integritas, dampak kerahasiaan, dan lain-lain. Skor yang dihasilkan membantu pengguna untuk memprioritaskan perbaikan atau mitigasi kerentanan dengan lebih baik.

Tingkat keparahan CVSS dibagi menjadi tiga kategori utama:

1. **Low (Rendah):** Kerentanan memiliki dampak terbatas.
2. **Medium (Sedang):** Kerentanan dapat menyebabkan kerugian yang signifikan, tetapi dengan kendali yang mungkin.
3. **High (Tinggi):** Kerentanan memiliki dampak serius dan mungkin memerlukan perhatian segera.

CVSS memberikan suatu standar yang umum digunakan di industri keamanan untuk mengkategorikan dan mengukur keparahan kerentanan. Informasi CVSS seringkali tersedia dalam Vulnerability Databases dan membantu organisasi dalam mengambil langkah-langkah yang tepat untuk mengamankan sistem mereka.

### Resources

* [https://www.aquasec.com/cloud-native-academy/supply-chain-security/sbom/](https://www.aquasec.com/cloud-native-academy/supply-chain-security/sbom/)
* [https://www.ntia.gov/sites/default/files/publications/sbom\_overview\_20200818\_0.pdf](https://www.ntia.gov/sites/default/files/publications/sbom\_overview\_20200818\_0.pdf)
