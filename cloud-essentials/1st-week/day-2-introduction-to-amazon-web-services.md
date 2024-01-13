# ✅ Day 2 - Introduction to Amazon Web Services

## Client-server Model

**Client-server model** adalah sebuah model arsitektur jaringan yang membagi tugas dan tanggung jawab antara dua jenis entitas: **client** dan **server**.

**Client** adalah perangkat atau aplikasi yang meminta dan mengonsumsi layanan atau sumber daya dari **server**. **Server** adalah perangkat atau aplikasi yang menyediakan dan mengelola layanan atau sumber daya untuk client.

Dalam cloud computing, **client-server model** adalah model arsitektur yang paling umum digunakan. Model ini memungkinkan pengguna untuk mengakses dan menggunakan sumber daya komputasi dari jarak jauh, tanpa memerlukan infrastruktur fisik dan staf TI yang ekstensif.

**Berikut adalah penjelasan singkat tentang peran client dan server dalam cloud computing:**

**Client**

* Merupakan perangkat atau aplikasi yang digunakan oleh pengguna untuk mengakses layanan atau sumber daya cloud.
* Contoh client cloud computing adalah:
  * Browser web untuk mengakses layanan web
  * Aplikasi desktop untuk mengakses layanan cloud desktop
  * Aplikasi seluler untuk mengakses layanan cloud seluler

**Server**

* Merupakan perangkat atau aplikasi yang menyediakan layanan atau sumber daya cloud.
* Server cloud computing biasanya berada di pusat data milik penyedia layanan cloud.
* Contoh server cloud computing adalah:
  * Server virtual untuk menyediakan infrastruktur komputasi
  * Server penyimpanan untuk menyediakan penyimpanan data
  * Server jaringan untuk menyediakan jaringan

**Keuntungan menggunakan client-server model dalam cloud computing:**

* **Fleksibilitas:** Pengguna dapat dengan mudah menyesuaikan kapasitas dan sumber daya cloud sesuai kebutuhan.
* **Efisiensi biaya:** Pengguna hanya perlu membayar untuk sumber daya cloud yang mereka gunakan.
* **Keandalan:** Layanan cloud biasanya lebih andal daripada infrastruktur komputasi lokal.

## Cloud Computing

### Apa itu Cloud Computing?

Cloud computing adalah istilah yang digunakan untuk menggambarkan penyediaan layanan komputasi, seperti penyimpanan data, pemrosesan, dan aplikasi, melalui internet. Cloud computing memungkinkan pengguna untuk mengakses sumber daya komputasi secara fleksibel dan skalabel, tanpa harus berinvestasi dalam infrastruktur komputasi mereka sendiri.

Istilah "awan" dalam cloud computing mengacu pada internet. Dengan cloud computing, pengguna dapat mengakses sumber daya komputasi dari mana saja di dunia, selama mereka memiliki koneksi internet.

### Cloud Deployment Model

Dalam dunia cloud computing, selain memahami konsep dasarnya, penting juga untuk mengetahui **deployment models**, yaitu model atau cara bagaimana aplikasi atau layanan kamu ditempatkan dan dijalankan di lingkungan cloud. Memilih model yang tepat bergantung pada kebutuhan dan kondisi spesifik kamu.

Berikut adalah beberapa deployment models yang umum digunakan:

**1. Public Cloud (Cloud-Based):**

* Bayangkan ini seperti menyewa apartemen: Kamu menggunakan infrastruktur yang disediakan oleh perusahaan besar seperti AWS, Google Cloud, atau Microsoft Azure, bersama dengan pengguna lain.
* **Keuntungan:** Mudah dan cepat digunakan, skalabel, biaya fleksibel (bayar per penggunaan).
* **Kekurangan:** Keamanan dan kontrol data lebih terbatas, mungkin ada ketergantungan pada vendor tertentu.
* **Cocok untuk:** Aplikasi web sederhana, pengembangan dan uji coba, situs web dengan trafik tidak terlalu tinggi.

**2. Private Cloud (On-Premises):**

* Seperti membangun rumah sendiri: Kamu memiliki infrastruktur cloud sendiri, dan hanya kamu yang berhak menggunakannya.
* **Keuntungan:** Kontrol dan keamanan data lebih tinggi, skalabel, lebih cocok untuk data sensitif.
* **Kekurangan:** Biaya awal tinggi untuk membangun dan memelihara infrastruktur, membutuhkan keahlian teknis pengelolaan cloud.
* **Cocok untuk:** Aplikasi bisnis kritis, perusahaan dengan data sensitif, kebutuhan kontrol tinggi.

**3. Hybrid Cloud:**

* **Kombinasi apartemen dan rumah**: Kamu menggunakan campuran public cloud dan private cloud untuk memenuhi kebutuhan yang berbeda.
* **Keuntungan:** Fleksibilitas tinggi, keamanan data ditingkatkan, skalabel.
* **Kekurangan:** Kompleksitas manajemen meningkat, perlu strategi integrasi cloud yang baik.
* **Cocok untuk:** Aplikasi hybrid, data dengan tingkat privasi berbeda, memanfaatkan keunggulan kedua model.

**4. Multi-Cloud:**

* **Menyewa beberapa apartemen dari vendor berbeda**: Kamu menggunakan layanan cloud dari beberapa vendor publik secara bersamaan.
* **Keuntungan:** Mengurangi ketergantungan vendor, menghindari vendor lock-in, memanfaatkan fitur terbaik dari tiap vendor.
* **Kekurangan:** Kompleksitas manajemen infrastruktur tinggi, biaya administrasi mungkin meningkat.
* **Cocok untuk:** Organisasi besar dengan kebutuhan cloud kompleks, diversifikasi risiko vendor.

**Tips Memilih Deployment Model:**

* **Pertimbangkan kebutuhan privasi dan keamanan data.**
* **Evaluasi skalabilitas aplikasi dan potensi pertumbuhan.**
* **Bandingkan biaya awal dan biaya operasional jangka panjang.**
* **Hitung keahlian teknis Anda untuk managemen cloud.**

### Manfaat dari Cloud Computing

\
Manfaat cloud computing dari AWS menjadi enam pernyataan berikut adalah penjelasan singkat dari masing-masing poin:

**1. Trade upfront expense for variable expense (Ganti investasi awal dengan biaya variabel)**

Alih-alih mengeluarkan modal besar untuk infrastruktur sendiri, Anda hanya membayar pemakaian cloud computing per waktu atau penggunaan, sehingga lebih fleksibel dan menyesuaikan budget.

**2. Stop spending money to run and maintain data centers (Hentikan biaya pengelolaan data center)**

Lupakan biaya perawatan server, listrik, dan keamanan fisik. Cloud computing menangani itu semua, membebaskan Anda dari beban dan pengeluaran ekstra.

**3. Stop guessing capacity (Stop menerka kapasitas)**

Tidak perlu lagi khawatir server kurang atau kelebihan kapasitas. Cloud computing mudah disesuaikan secara real-time sesuai kebutuhan, menghilangkan penyesalan berlebihan atau kekurangan sumber daya.

**4. Benefit from massive economies of scale (Nikmati skala ekonomis global)**

Manfaatkan infrastruktur dan teknologi canggih dari provider cloud besar, yang lebih efisien dan hemat biaya dibandingkan membangun sendiri.

**5. Increase speed and agility (Tingkatkan kecepatan dan kelincahan)**

Cloud computing memungkinkan penyebaran aplikasi dan layanan dengan cepat, serta skalabilitas tinggi untuk merespons perubahan permintaan secara dinamis.

**6. Go global in minutes (Jadilah global dalam hitungan menit)**

**J**angkau pengguna di seluruh dunia tanpa perlu membangun infrastruktur di setiap negara. Cloud computing menyediakan layanan global yang mudah diakses dari mana saja.



Semoga penjelasan ini membantu memahami client-server model, cloud computing, deployment models, dan manfaat dari cloud computing. Jika ada pertanyaan lebih lanjut atau butuh bantuan, silakan tanyakan.

## Resources

