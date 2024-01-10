# ✅ Day 15: Fuzzing

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption><p><a href="https://www.securityfocal.com/what-is-fuzzing-types-advantages-disadvantages/">https://www.securityfocal.com/what-is-fuzzing-types-advantages-disadvantages/</a></p></figcaption></figure>

_Fuzzing_, atau sering disebut "_fuzz testing_" atau "_fuzzing testing_," adalah suatu teknik pengujian keamanan yang bersifat proaktif.

Ide dasarnya sederhana:&#x20;

> Berikan input yang tak terduga atau tidak valid ke program komputer dan lihat bagaimana program tersebut merespons.

Fuzzing dapat dilakukan pada berbagai tingkatan, mulai dari tingkat aplikasi hingga tingkat sistem. Tujuan utama dari fuzzing adalah untuk menemukan bug atau celah keamanan yang mungkin dapat dieksploitasi oleh pihak yang tidak bertanggung jawab.

## Cara Kerja Fuzzing

Bayangkan jika kita memberikan data yang tak terduga ke suatu program komputer. Program tersebut, seperti manusia pada umumnya, mungkin tidak tahu bagaimana menangani input yang aneh atau tak terduga. Inilah inti dari fuzzing. Teknik ini mencoba menyelipkan input yang tidak valid, acak, atau mungkin tidak pernah terpikirkan oleh pengembang ke dalam program untuk melihat apakah program dapat bertahan dan berperilaku dengan benar.

Proses fuzzing dapat dilakukan dengan dua pendekatan utama: **Black Box Fuzzing** dan **White Box Fuzzing**.

1. **Black Box Fuzzing:** Di sini, para pengujinya memberikan input yang tidak terduga kepada aplikasi asi tanpa memiliki pengetahuan internal tentang program tersebut.
2. **White Box Fuzzing:** Di sini, para pengujinya memiliki pengetahuan lebih mendalam tentang bagaimana program bekerja. Mereka dapat menciptakan input yang lebih terarah, mencoba menggali lebih dalam ke dalam struktur dan logika internal program.

## **Tipe Fuzzing**

Fuzzing bisa bermacam-macam tergantung pada bagaimana input yang diberikan dan dihasilkan. Beberapa jenis fuzzing yang umum melibatkan:

1. **Mutation-based Fuzzing:**
   * Teknik ini melibatkan mengubah input yang valid secara acak untuk melihat apakah perubahan tersebut dapat memicu respons yang tidak diharapkan dari program.
   * Misalnya, jika suatu program biasanya menerima teks biasa, fuzzing dapat menggantinya dengan karakter aneh, bilangan negatif, atau bahkan file gambar.
2. **Generation-based Fuzzing:**
   * Sebaliknya, teknik ini melibatkan penciptaan input dari awal. Para pengujinya membuat input yang mungkin tidak valid atau tidak terduga.
   * Misalnya, jika suatu program mengharapkan input dalam format XML, fuzzing dapat mencoba memberikan input yang melanggar aturan XML atau mungkin berisi elemen tambahan yang tidak diharapkan.

## **Keuntungan Fuzzing**

1. **Identifikasi Bug yang Sulit Ditemukan:** Fuzzing dapat menemukan bug atau celah keamanan yang mungkin sulit ditemukan dengan metode pengujian tradisional.
2. **Proaktif dalam Pengujian Keamanan:** Fuzzing memberikan pendekatan proaktif untuk pengujian keamanan, membantu organisasi mengidentifikasi dan memperbaiki masalah keamanan sebelum mereka dieksploitasi oleh penyerang.
3. **Meningkatkan Keandalan Perangkat Lunak:** Dengan mengekspos perangkat lunak terhadap input yang mungkin tidak terduga, fuzzing membantu meningkatkan keandalan dan ketahanan perangkat lunak terhadap kesalahan dan serangan.
4. **Dapat Diterapkan pada Berbagai Tingkatan:** Fuzzing dapat diterapkan pada berbagai tingkatan, termasuk tingkat aplikasi, protokol jaringan, atau bahkan tingkat sistem, memberikan fleksibilitas dalam pengujian.

## **Tantangan dalam Fuzzing.**

1. **Overhead Pengujian:** Fuzzing dapat menjadi proses yang memakan waktu dan sumber daya jika tidak dikelola dengan baik. Melakukan fuzzing secara berlebihan atau tanpa perencanaan dapat menyebabkan overhead yang signifikan.
2. **Banyaknya False Positif:** Terkadang, fuzzing dapat menghasilkan banyak hasil false positif, di mana program memberikan tanggapan yang tidak diharapkan, tetapi tidak ada celah keamanan yang sebenarnya.
3. **Memerlukan Pemahaman yang Mendalam:** White Box Fuzzing, yang memerlukan pemahaman yang mendalam tentang internal program, dapat menjadi tantangan jika pengembang atau pengujinya tidak memiliki pengetahuan yang cukup.

## **Kesimpulan**

Dengan memberikan input yang tak terduga, fuzzing membantu kita melihat bagaimana perangkat lunak dapat bereaksi terhadap situasi yang tidak terduga. Seiring dengan pengembangan perangkat lunak yang semakin canggih, teknik ini tetap relevan untuk menjaga keamanan dan keandalan sistem.

Penting untuk diingat bahwa fuzzing hanyalah satu elemen dari strategi keamanan yang holistik. Untuk mencapai keamanan yang optimal, perusahaan dan pengembang perangkat lunak harus menggabungkan fuzzing dengan praktik keamanan yang baik, penetration testing, dan pemantauan keamanan yang terus-menerus. Dengan begitu, kita dapat terus memperkuat pertahanan perangkat lunak kita terhadap ancaman yang terus berkembang.

### Resources

* [https://owasp.org/www-community/Fuzzing](https://owasp.org/www-community/Fuzzing)
* [https://www.crowdstrike.com/blog/how-crowdstrike-intelligence-uses-fuzzing-to-hunt-for-bugs/](https://www.crowdstrike.com/blog/how-crowdstrike-intelligence-uses-fuzzing-to-hunt-for-bugs/)
