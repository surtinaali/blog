---
layout: post
title:  Jangan Gunakan BaseUrl
date:   2018-08-08 10:47:00 +0900
categories: jekyll,
img_path: assets/img/post/noimage.svg
---

BaseUrl adalah sebuah baris konfigurasi pada berkas config.yml yang cukup merepotkan jika tidak dipahami untuk apa penggunaannya. Akibat dari kesalahan penggunaan baseurl adalah berantakannya alamat URL. Seperti yang saya alami, ketika websitenya dibuka menggunakan URL lokal semuanya terlihat baik-baik saja, tapi ketika dibuka menggunakan URL github atau URL modifikasi, maka sebagian dari konten website tidak terpanggil karena URL atau alamat kontennya salah.

#### Tanpa BaseURL VS dengan BaseURL 

Jika didalam berkas config.yml `baseurl :` dibiarkan kosong, maka ketika perintah `serve` dipanggil secara otomatis akan diarahkan ke alamat `http://127.0.0.1:4000`. 

Berbeda jika `baseurl :` diisi dengan nilai `/blog` misalnya, ketika perintah `serve` dipanggil maka akan diarahkan ke alamat `http://127.0.0.1:4000/blog`, artinya ada tambahan path `/blog` dari alamat yang sebelumnya `http://127.0.0.1:4000`.


#### Yang harus dilakukan 

Penting untuk diingat, jika menggunakan `baseurl` maka ketika membuat link didepannya harus diikutkan dengan `{{site.baseurl}}/path/path/path/berkas.type`. 

Misalnya : 
{% highlight HTML %}
    <link rel="stylesheet" href="{{site.baseurl}}/assets/style/css/syntax.css">
{% endhighlight %}

Jika tidak menggunakan `baseurl` maka kode `{{site.baseurl}}` tidak perlu ditambahkan.  


#### Untuk apa baseurl digunakan ? 

Seperti yang dijelaskan diatas, ketika menggunakan baseurl maka ada tambahan /blog setelah bagian DOMAIN:PORT. Jadi baseurl digunakan apabila kita ingin ada tambahan setelah DOMAIN:PORT. Tetapi kelihatannya baseurl lebih kompleks dari sekedar menambahkan alamat didepan DOMAIN:PORT, masih butuh waktu untuk benar-benar memahami.

#### Lebih kompleks lagi tentang baseURL :
[[1] &nbsp; Configuring Jekyll for User and Project GitHub Pages](http://downtothewire.io/2015/08/15/configuring-jekyll-for-user-and-project-github-pages/){:target="new"}<br>
[[2] &nbsp; Clearing Up Confusion Around baseurl](https://byparker.com/blog/2014/clearing-up-confusion-around-baseurl/#fnref:1){:target="new"}<br>
