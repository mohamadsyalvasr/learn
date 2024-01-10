# ✅ Day 20: Runtime Application Self-Protection (RASP)

Halo, hari ini kita akan membahas tentang **Runtime Application Self-Protection (RASP)**.

## Apa itu RASP?

RASP adalah teknologi keamanan yang menggunakan instrumentasi runtime untuk mendeteksi dan memblokir serangan komputer dengan memanfaatkan informasi dari dalam perangkat lunak yang sedang berjalan.

RASP bekerja dengan cara menanamkan kode keamanan langsung ke dalam aplikasi. Kode ini kemudian akan memantau aktivitas aplikasi dan mencari tanda-tanda serangan. Jika serangan terdeteksi, kode RASP akan mengambil tindakan untuk memblokirnya.

## **Keuntungan RASP**

RASP menawarkan beberapa keuntungan dibandingkan dengan solusi keamanan tradisional, antara lain:

* **Keakuratan yang lebih tinggi:** RASP dapat mendeteksi serangan yang tidak dapat dideteksi oleh solusi keamanan tradisional, seperti serangan yang menargetkan kerentanan yang tidak diketahui atau serangan yang menggunakan teknik yang baru.
* **Respons yang lebih cepat:** RASP dapat mengambil tindakan untuk memblokir serangan secara real-time, sehingga mengurangi dampak serangan.
* **Kemampuan untuk melindungi aplikasi di berbagai lingkungan:** RASP dapat diimplementasikan di berbagai lingkungan, termasuk cloud, on-premises, dan hybrid.

## Kekurangan RASP

Seperti halnya setiap teknologi, RASP juga memiliki beberapa kelemahan atau kekurangan. Berikut adalah beberapa di antaranya:

* **Kompleksitas penerapan:** Implementasi RASP dapat menjadi kompleks, terutama untuk aplikasi yang kompleks atau besar.
* **Biaya:** Tools RASP komersial dapat mahal, terutama untuk organisasi yang memiliki banyak aplikasi untuk dilindungi.
* **False positives:** RASP dapat menghasilkan false positives, yang dapat menyebabkan pengguna yang sah diblokir atau aplikasi menjadi tidak berfungsi.
* **Kemampuan untuk menghindari:** Penyerang dapat mengembangkan teknik untuk menghindari deteksi oleh RASP.

Berikut adalah beberapa tips untuk mengurangi dampak kelemahan atau kekurangan RASP:

* Pastikan tim memiliki pelatihan yang memadai untuk menerapkan dan mengelola RASP.
* Pilih tools RASP yang sesuai dengan kebutuhan organisasi.
* Gunakan tools RASP bersama dengan solusi keamanan lainnya untuk memberikan perlindungan yang lebih komprehensif.

## **Jenis-jenis RASP**

Ada dua jenis utama RASP, yaitu:

### **1. Agent-based RASP**

Jenis RASP ini menanamkan kode keamanan ke dalam aplikasi sebagai agen. Agen ini kemudian akan memantau aktivitas aplikasi dan melaporkannya ke konsol manajemen.

### **2. Code-based RASP**

Jenis RASP ini menanamkan kode keamanan ke dalam aplikasi sebagai bagian dari kode aplikasi itu sendiri. Kode ini kemudian akan memantau aktivitas aplikasi dan mengambil tindakan untuk memblokir serangan.

## **Implementasi RASP**

Implementasi RASP dapat dilakukan dengan berbagai cara, tergantung pada jenis RASP yang digunakan.

1. Untuk agent-based RASP, implementasi biasanya dilakukan oleh tim DevOps atau tim keamanan. Tim ini akan menanamkan agen RASP ke dalam aplikasi.
2. Untuk code-based RASP, implementasi biasanya dilakukan oleh tim pengembang aplikasi. Tim ini akan menambahkan kode RASP ke dalam aplikasi selama proses pengembangan.

## **Metode Penyebaran RASP**

RASP dapat diimplementasikan dalam berbagai mode, tergantung pada kebutuhan organisasi. Berikut adalah beberapa mode penyebaran RASP yang umum:

### **1. Off mode**

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption><p><a href="https://www.appsealing.com/rasp-security-runtime-application-self-protection/">source</a></p></figcaption></figure>

Mode off adalah mode yang paling sederhana dan paling hemat biaya. Mode ini tidak menawarkan perlindungan apa pun dari serangan, tetapi dapat digunakan untuk menguji RASP sebelum diimplementasikan secara penuh.

### **2. Monitoring mode**

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption><p><a href="https://www.appsealing.com/rasp-security-runtime-application-self-protection/">source</a></p></figcaption></figure>

Mode monitoring memungkinkan RASP untuk memantau aplikasi untuk tanda-tanda serangan, tetapi tidak memblokir serangan. Mode ini dapat digunakan untuk mengumpulkan data tentang aktivitas aplikasi dan potensi serangan. Data ini dapat digunakan untuk meningkatkan keamanan aplikasi atau untuk mendeteksi serangan yang tidak terdeteksi oleh solusi keamanan lainnya.

### **3. Blocking mode**

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption><p><a href="https://www.appsealing.com/rasp-security-runtime-application-self-protection/">source</a></p></figcaption></figure>

Mode blocking adalah mode yang paling umum digunakan untuk melindungi aplikasi dari serangan. Mode ini memungkinkan RASP untuk memblokir serangan secara real-time. Mode ini memberikan perlindungan yang maksimal, tetapi juga dapat menyebabkan false positives, yang dapat menyebabkan pengguna yang sah diblokir atau aplikasi menjadi tidak berfungsi.

Dalam praktiknya, organisasi sering kali menggunakan kombinasi dari berbagai mode penyebaran RASP. Misalnya, organisasi dapat menggunakan mode monitoring untuk mengumpulkan data tentang aktivitas aplikasi, dan kemudian menggunakan mode blocking untuk memblokir serangan yang terdeteksi.

Pemilihan mode penyebaran RASP yang tepat tergantung pada berbagai faktor, antara lain:

* **Tingkat risiko yang dihadapi organisasi:** Organisasi yang menghadapi tingkat risiko yang tinggi mungkin ingin menggunakan mode blocking untuk memberikan perlindungan yang lebih maksimal.
* **Kebutuhan organisasi:** Organisasi yang perlu mengumpulkan data tentang aktivitas aplikasi mungkin ingin menggunakan mode monitoring.
* **Kompleksitas aplikasi:** Aplikasi yang kompleks atau besar mungkin lebih sulit untuk dilindungi dalam mode blocking.

## Tools RASP

Berikut adalah beberapa contoh tools/agen RASP yang dapat digunakan untuk melindungi aplikasi di berbagai lingkungan:

* **CrowdStrike Falcon Prevent** dapat melindungi aplikasi di berbagai lingkungan, termasuk cloud, on-premises, dan hybrid.
* **Palo Alto Networks Cortex XDR** juga dapat melindungi aplikasi di berbagai lingkungan, termasuk cloud, on-premises, dan hybrid.
* **FortiGuard Labs FortiSOAR** dapat melindungi aplikasi di berbagai lingkungan, termasuk cloud, on-premises, dan hybrid.
* **SentinelOne Singularity** dapat melindungi aplikasi di berbagai lingkungan, termasuk cloud, on-premises, dan hybrid.
* **Check Point CloudGuard** dapat melindungi aplikasi di cloud.

Beberapa contoh tools/agen RASP open-source:

* **OpenRASP** adalah tools RASP open-source yang dikembangkan oleh Baidu Security. OpenRASP dapat digunakan untuk melindungi aplikasi web dan API.
* **OWASP ModSecurity Core Rule Set (CRS)** adalah kumpulan aturan yang dapat digunakan untuk melindungi aplikasi dari berbagai jenis serangan. OWASP CRS dapat digunakan dengan berbagai tools RASP, termasuk OpenRASP.

Pemilihan tools/agen RASP yang tepat tergantung pada berbagai faktor, antara lain jenis aplikasi yang akan dilindungi, lingkungan di mana aplikasi berjalan, dan anggaran yang tersedia.

## **Kesimpulan**

RASP adalah teknologi keamanan yang canggih yang dapat membantu melindungi aplikasi dari berbagai jenis serangan. RASP menawarkan beberapa keuntungan dibandingkan dengan solusi keamanan tradisional, antara lain keakuratan yang lebih tinggi, respons yang lebih cepat, dan kemampuan untuk melindungi aplikasi di berbagai lingkungan.

## Resources

* [https://www.fortinet.com/resources/cyberglossary/runtime-application-self-protection-rasp](https://www.fortinet.com/resources/cyberglossary/runtime-application-self-protection-rasp)
* [https://www.crowdstrike.com/cybersecurity-101/cloud-security/runtime-application-self-protection-rasp/](https://www.crowdstrike.com/cybersecurity-101/cloud-security/runtime-application-self-protection-rasp/)
* [https://en.wikipedia.org/wiki/Runtime\_application\_self-protection](https://en.wikipedia.org/wiki/Runtime\_application\_self-protection)
* [https://www.rapid7.com/blog/post/2019/09/04/rasp-101-what-is-runtime-application-self-protection/](https://www.rapid7.com/blog/post/2019/09/04/rasp-101-what-is-runtime-application-self-protection/)
* [https://www.appsealing.com/rasp-security-runtime-application-self-protection/](https://www.appsealing.com/rasp-security-runtime-application-self-protection/)
