---
layout: post
title: "Perbedaan web statis dan web dinamis"
date: 2018-07-19 02:17:00 +0900
categories: Web
img_path: assets/img/post/180719.svg
---

Static web atau web statis lebih dikenal di awal era perkembangan WEB. Tim Berners Lee sebagai penggagas teknologi web pada awalnya membuat web server dan web browser yang hanya mampu mengelola text. 

Teknologi web tersebut dikenal dengan nama HTTP (Hypertext Transfer Protocol) yang sampai sekarang masih tetap digunakan,  namun sudah dengan berbagai pengembangan sehingga tidak hanya teks, gambar dan suara juga dapat ditampilkan.

Perbedaan antara web statis dan web dinamis sebenarnya bukan dilihat dari HTTP-nya, namun pada konten yang ditampilkan di browser.  

Jika web tersebut ditampilkan dibrowser sebagaimana failnya yang tersimpan di hardisk, maka bisa dikatakan web tersebut merupakan web statis. 

Berbeda dengan web dinamis, karena sebagian informasi yang ditampilkan diweb tersebut merupakan hasil query atau diambil dari sistem basis data.

##### Cara kerja Web Statis
1. Melalui browser, user mengakses alamat URL web untuk melakukan request ke server
2. Setelah web server menerima Request. Web server langsung mengakses fail statis web di storage dan dikirim ke browser untuk ditampilkan

Pada umumnya web statis dibangun diatas bahasa standar web : 
{:.m-1}
- HTML (HyperText Markup Language), dan
- CSS (Cascading Style Sheets)
- JavaScript 

Contoh kode web statis : 
{% highlight html %} 
<head>
    <title>
        "Nama Website"
    </title>
</head>
{% endhighlight %} 


##### Cara kerja Web Dinamis
1. Melalui browser, user mengakses alamat URL web untuk melakukan request ke server 
2. Setelah web server menerima Request. Aplikasi web yang tersimpan di server akan mengakses sistem basis data dan mengambil informasi yang akan ditampilkan
3. Informasi kemudian disatukan dengan template dan dikirim ke browser untuk ditampilkan 

Pembuatan web dinamis biasanya menggunakan bahasa pemprograman : 
{:.m-0}
- JavaScript 
- PHP (Hypertext Preprocessor)
- RubyOnRails
- NodeJs
- Golang 
- Phyton
- Sql (Structured Query Language)

Contoh kode web dinamis : 
{% highlight php %} 
<head>
    <title>
        <?php get_nama_web() ?>
    </title>
</head>
{% endhighlight %}