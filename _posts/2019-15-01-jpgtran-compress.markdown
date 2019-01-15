---
layout:     post
title:      Memperkecil ukuran gambar JPG menggunakan JPEGTRAN 
date:       2019-15-01 15:02:00 +0900
categories: dokumentasi
img_path:   assets/img/post/noimage.svg
---

Beberapa hari yang lalu saya membahas tentang memperkecil ukuran gambar PNG menggunakan PNGQUANT. Ukurannya memang menjadi kecil, tapi pada umumnya para pengembang website lebih banyak menggunakan tipe berkas JPG dibanding PNG. Karena penasaran pada akhirnya saya menemukan aplikasi JPEGTRAN. Artikel ini menjelaskan beberapa hal yang saya pelajari berhubungan dengan JPEGTRAN. 

#### Hal pertama yang saya pelajari

Dari artikel yang saya baca kata yang selalu digunakan adalah OPTIMASI jadi mungkin lebih tepat jika Judul Artikel ini "Mengoptimasi gambar JPG menggunakan JPEGTRAN". 

#### Hal Kedua yang saya pelajari
Terdapat dua jenis gambar JPG. Gambar JPG baseline dan gambar JPG progressive. Ujicoba yang saya lakukan menggunakan aplikasi JPEGTRAN, optimasi gambar JPG menggunakan parameter `-copy none` + `-progressive` ukurannya lebih kecil 78.1KB dibanding menggunakan parameter `-copy none` + `-optimize` 79.8KB dari ukuran sebelum optimasi 106KB. Berikut adalah perintah lengkapnya. 

{% highlight POWERSHELL %}
jpegtran.exe -copy none -progressive nama-berkas.JPG nama-berkas-compress.JPG
{% endhighlight %}

{% highlight POWERSHELL %}
jpegtran.exe -copy none -optimize nama-berkas.JPG nama-berkas-compress.JPG
{% endhighlight %}

#### Hal ketiga yang saya pelajari

Keterangan parameter yang digunakan : 
1. Fungsi parameter -copy none adalah untuk menduplikasi gambar nama-berkas.JPG menjadi nama-berkas-compress.JPG tapi dengan menghapus metadata dari gambar karena memang tidak begitu dibutuhkan untuk gambar yang digunakan di web.
2. Fungsi parameter -progressive adalah untuk mengoptimasi jenis gambar JPG baseline ke progressive karena pada umumnya Gambar JPG berjenis baseline. Jenis gambar JPG baseline ketika ditampilkan ke browser prosesnya lebih lambat dibandingkan dengan progressive. Lebih jelasnya baca [Image Optimization, Part 4: Progressive JPEG...Hot or Not?](https://yuiblog.com/blog/2008/12/05/imageopt-4/){:target="new"} juga [The Return of The Progressive JPEG](https://www.wired.com/2013/01/the-return-of-the-progressive-jpeg/){:target="new"}. 
3. Fungsi parameter -optimize adalah untuk melakukan optimasi atau memperkecil ukuran gambar menggunakan algoritma tabel huffman. Baca [What is an Optimized JPEG](https://www.impulseadventure.com/photo/optimized-jpeg.html). 


#### Hal keempat yang saya pelajari 

Adalah kesimpulan dari artikel [Image Optimization, Part 4: Progressive JPEG...Hot or Not?](https://yuiblog.com/blog/2008/12/05/imageopt-4/){:target="new"} : 

- ketika gambar JPEG dibawah 10K, alangkah baiknya disimpan dengan jenis gambar JPEG baseline
- untuk gambar diatas 10K, JPEG progressive akan akan memberikan hasil kompressi lebih baik 

Sekian untuk artikel ini, apakah anda memiliki solusi yang lebih baik dalam hal optimasi gambar? silahakan bagikan trik anda di bagian komentar.  