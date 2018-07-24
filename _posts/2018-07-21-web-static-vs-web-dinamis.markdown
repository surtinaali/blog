---
layout: post
title: "Web Statis VS Web Dinamis"
date: 2018-07-19 02:17:00 +0900
categories: Web
img_path: assets/img/post/130718.svg
---

Static web lebih dikenal di awal era perkembangan internet. Pada era itu, Tim Berners Lee sebagai penggagas teknologi web membuat web server dan web browser yang hanya mampu merespon request dan menampilkan web statis (static web), dengan bahasa yang digunakan adalah HTML. 

Istilah web statis mengarah pada bagaimana web ditampilkan dibrowser. Jika web tersebut ditampilkan dibrowser sebagaimana failnya yang tersimpan di hardisk, maka bisa dikatakan web tersebut merupakan web statis. Berbeda dengan web dinamis, yang sebagian informasi yang ditampilkan merupakan hasil query dari sistem basis data. 

##### Web Statis VS Web Dinamis 

{: .mb-0}
Cara kerja Web Statis
1. Melalui browser, user mengakses alamat URL web untuk melakukan request ke server
2. Setelah web server menerima Request. Web server langsung mengakses fail statis web di storage dan dikirim ke browser untuk ditampilkan  

{: .mb-0}
Cara kerja Web Dinamis
1. Melalui browser, user mengakses alamat URL web untuk melakukan request ke server 
2. Setelah web server menerima Request. Aplikasi web yang tersimpan di server akan mengakses sistem basis data dan mengambil informasi yang akan ditampilkan kemudian digambung dengan template  
3. Informasi kemudian disatukan dengan template dan dikirim ke browser untuk ditampilkan 

##### Bahasa Web Statis VS Web Dinamis
Biasanya sebuah web statis dibangun diatas tiga bahasa standar web yang merupakan rekomendasi WWW : 
- HTML (HyperText Markup Language)
- CSS (Cascading Style Sheets), dan 
- JavaScript 

sementara untuk web dinamis dibutuhkan bahasa pemprograman seperti : 
- PHP (Hypertext Preprocessor)
- RubyOnRails
- NodeJs
- Golang 
- Phyton
- Sql (Structured Query Language)