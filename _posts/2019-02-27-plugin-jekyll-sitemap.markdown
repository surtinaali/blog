---
layout:     post
title:      Membuat website di kenal search engine [jekyll-sitemap & Google Search Console]
date:       2019-02-27 10:47:00 +0900
categories: jekyll
img_path:   assets/img/post/190227.svg
---

Sebenarnya sekarang lagi dalam kondisi sulit-sulitnya mencari waktu menulis blog, karena disibukkan dengan pekerjaan. Tapi saya harus menyempatkan sedikit waktu, karena ternyata tulisan-tulisan yang pernah di tulis di blog sama sekali belum ditemukan di search engine Google. Wajar, sejak awal blog dibuat saya memang sengaja memperbanyak tulisan dulu, SEO-nya belakangan.

Yang saya pahami, memang dulunya kalo mau buat SEO website sangat ribet, harus edit code, diinput JavaScript SEO dan banyak lagi embel-embel lainnya. 

Alhamdulillah, sekarang ada [Google Search Console](https://search.google.com/search-console/about){:target="new"} dengan fitur <b>sitemap-nya</b>. 

#### Apa itu Google Search Console?

Google Search Console adalah tools yang bisa digunakan untuk membantu dalam mengukur performa dan lalulintas website. Dari penjelasan dihalaman about Google Search Console dijelaskan ada empat fitur Google Search Console, 1) Mengoptimasi konten menggunakan search analytics;  2) Mengindeks konten website agar dikenal Google; 3) Memberikan informasi masalah website dan 4) Memberikan informasi tentang bagaimana google mengenal halaman website. 


#### Apa itu sitemap ?

Sitemap adalah peta website yang berisi alamat-alamat halaman dan file-file website. Sitemap biasanya digunakan oleh google untuk mengetahui pembaruan yang terjadi dalam website.


#### SEO Ala Jekyll

Pertama : aktifkan Plug-in jekyll-sitemap dengan cara tambahkan kode dibawah ini di fail *_config.yml* : 

{% highlight YAML %}
url : https://alamat-website.com/ #Ganti alamatnya 
plugins:
  - jekyll-sitemap
{% endhighlight %}

Kedua : buka alamat [Google Search Console](https://search.google.com/search-console/about){:target="new"}. Kemudian Klik Start Now dan Login Menggunakan alamat email G-Mail. Setelah itu Add Property lalu masukkan alamat website. 

Ketiga : klik Sitemaps lalu tambahkan *sitemap* dibelakang alamat https://alamat-website.com/ lalu klik sumbit. 

Dengan tiga langkah diatas, search engine "google" akan lebih mudah menemukan halaman website. Walaupun demikian, website tidak secara langsung bisa ditemukan digoogle saat itu juga, google membutuhkan waktu beberapa hari untuk bisa secara utuh mengindeks halaman-halaman yang ada dalam website.   

#### Penutup

Cara yang dibahas diatas hanyalah salah satu dari banyak teknik SEO lainnya, karena SEO (Search Engine Optimizer) bisa juga ditentukan dari sisi konten dan penggunaan kata kunci yang banyak digunakan di Search engine. 

