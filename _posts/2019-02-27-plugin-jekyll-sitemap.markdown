---
layout:     post
title:      Membuat website di kenal search engine [jekyll-sitemap & Google Search Console]
date:       2019-02-27 10:47:00 +0900
categories: jekyll
img_path:   assets/img/post/noimage.svg
---

Sebenarnya sekaranglagi dalam kondisi sulit-sulitnya mencari waktu menulis blog, karena disibukkan dengan pekerjaan. Tapi saya harus menyempatkan sedikit waktu, karena ternyata tulisan-tulisan yang pernah di tulis di blog sama sekali belum ditemukan di search engine Google. Wajar, sejak awal blog dibuat saya memang sengaja merencakan menulis dulu, SEO-nya nanti nyusul.

Yang jadi pertanyaan saya sekarang, mengapa dulunya saya merencanakan harus nulis dulu nanti SEO-nya belakangan? padahal tidak ada loh aturan seperti itu. Inilah akibat dari membawa masa lalu ke masa sekarang. 

Yang saya pahami, memang dulunya kalo mau buat SEO website sangat ribet, harus edit code, diinput JavaScript SEO dan banyak lagi embel-embel lainnya. 

Alhamdulillah, sekarang ada [Google Search Console](https://search.google.com/search-console/about){:target="new"} dengan fitur <b>sitemap-nya</b>. 

#### Apa itu Google Search Console dan sitemap ?

Google Search Console adalah tools yang bisa digunakan untuk membantu dalam mengukur performa dan lalulintas website. Dari penjelasan dihalaman about Google Search Console dijelaskan ada empat fitur Google Search Console, 1) Mengoptimasi konten menggunakan search analytics;  2) Mengindeks konten website agar dikenal Google; 3) Memberikan informasi masalah website dan 4) Memberikan informasi tentang bagaimana google mengenal halaman website. 

Sitemap adalah peta website yang berisi alamat-alamat halaman dan file-file dalam website. Sitemap biasanya digunakan oleh google untuk mengetahui pembaruan yang terjadi dalam website, dalam hal ini alamat dan file-file yang baru diperbarui.


#### Cara memperkenalkan website ke Search Engine

Pertama : aktifkan Plug-in jekyll-sitemap dengan cara tambahkan kode dibawah ini di fail *_config.yml* : 

{% highlight YAML %}
url : https://alamat-website.com/ #Ganti alamatnya 
plugins:
  - jekyll-sitemap
{% endhighlight %}

Kedua : buka alamat [Google Search Console](https://search.google.com/search-console/about){:target="new"}. Kemudian Klik Start Now dan Login Menggunakan alamat email G-Mail. Setelah itu Add Property lalu masukkan alamat website. 

Ketiga : klik Sitemaps lalu tambahkan *sitemap* dibelakang alamat https://alamat-website.com/ lalu klik sumbit. 

Hanya dengan tiga langkah diatas website sudah bisa dikenali di google. Walaupun demikian, website tidak secara langsung bisa ditemukan digoogle saat itu juga, google membutuhkan waktu beberapa hari untuk bisa mengindeks halaman website secara utuh.   

#### Penutup

Cara yang dibahas diatas hanyalah salah satu dari banyak teknik SEO lainnya, karena SEO (Search Engine Optimizer) bisa juga ditentukan dari sisi konten dan penggunaan kata kunci yang banyak digunakan di Search engine. 

