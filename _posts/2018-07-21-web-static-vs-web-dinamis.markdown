---
layout: post
title: "Perbedaan web statis dan web dinamis"
date: 2018-07-19 02:17:00 +0900
categories: Dokumentasi
img_path: assets/img/post/180719.svg
---

Static web atau web statis lebih dikenal di awal era perkembangan WEB. Tim Berners Lee sebagai penggagas teknologi web pada awalnya membuat web server dan web browser, tapi hanya mampu mengolah atau menampilkan text. 

Teknologi web tersebut dikenal dengan nama HTTP (Hypertext Transfer Protocol) yang sampai sekarang masih tetap digunakan,  namun sudah dengan berbagai pengembangan sehingga tidak hanya teks, gambar dan suara juga dapat ditampilkan.

Perbedaan antara web statis dan web dinamis sebenarnya bukan dilihat dari HTTP-nya, namun pada konten yang ditampilkan di browser.

Jika web tersebut ditampilkan dibrowser sebagaimana failnya yang tersimpan di hard disk, maka bisa dikatakan web tersebut merupakan web statis. Tampilan halaman web statis tidak akan berubah kecuali perubahan dilakukan secara manual pada failnya. 

Berbeda dengan web statis, halaman yang ditampilkan oleh web dinamis merupakan hasil query dari sistem basis data. Disebut dinamis karena tampilan web bisa saja berubah berdasarkan kondisi-kondisi tertentu.

#### Cara kerja Web Statis
1. Melalui browser, user mengakses alamat URL web untuk melakukan request ke server
2. Setelah web server menerima Request. Web server langsung mengakses fail statis web di storage dan dikirim ke browser untuk ditampilkan

Pada umumnya web statis dibangun diatas bahasa standar web : 

- HTML (HyperText Markup Language)
- CSS (Cascading Style Sheets)
- JavaScript 

Contoh kode web statis :


{% highlight HTML %}<head>
    <title>
        "Nama Website"
    </title>
</head>
{% endhighlight %} 


#### Cara kerja Web Dinamis
1. Melalui browser, user mengakses alamat URL web untuk melakukan request ke server 
2. Setelah web server menerima Request. Fail yang tersimpan di server berupa program web akan mengakses sistem basis data dan mengambil informasi yang akan ditampilkan
3. Informasi tersebut kemudian disatukan dengan template dan dikirim ke browser untuk ditampilkan 

Pembuatan web dinamis biasanya menggunakan bahasa pemprograman : 

- JavaScript 
- PHP (Hypertext Preprocessor)
- RubyOnRails
- NodeJs
- Golang 
- Phyton
- Sql (Structured Query Language)

Contoh kode web dinamis : 


{% highlight PHP %}<head>
    <title>
        <?php get_nama_web() ?>
    </title>
</head>
{% endhighlight %}

#### Daftar Pustaka 
[1. Comparison of Static and Dynamic Websites](https://www.webnots.com/comparison-of-static-and-dynamic-website/){:target="new"}<br>
[2. Static VS Dynamic Website](https://www.javatpoint.com/website-static-vs-dynamic){:target="new"}<br>
[](){:target="new"}