---
layout:     post
title:      HTTPS Pake CloudFlare
date:       2019-01-14 10:47:00 +0900
categories: dokumentasi
img_path:   assets/img/post/noimage.svg
---

HTTPS (Hypertext Transfer Protocol + SSL) merupakan protocol internet yang dikembangkan dari protocol sebelumnya HTTP. Protocol HTTPS dibuat dengan tujuan keamanan komunikasi antara server dan client, agar informasi yang saling bertukar antara client dan server tidak dapat terbaca oleh pihak ketiga jika tersadap. 

Cloudflare adalah salah satu layanan yang menyediakan sertifikat SSL Universal yang bisa digunakan secara gratis, ada juga yang berbayar. 

Misalnya domain saya http://saidbahta.blog jika saya gunakan tanpa serifikat SSL maka informasi yang dikirimkan antara client dan server akan sangat rentan tersadap, berbeda jika domainnya diupgrade menggunakan sertifikat SSL (https://saidbahta.blog) paket datanya mungkin tersadap tapi telah berubah _[baca, terenkripsi]_ sehingga informasi yang ada dalam paket tersebut tidak dapat terbaca. 

Untuk bisa menggunakan sertifikat SSL Universal dari cloudflare harus memiliki akun cloudflare yang bisa didaftarkan gratis di [CloudFlare.Com](https://www.cloudflare.com). 


#### Tambahkan Domain 

Pertama kali yang dilakukan setelah memiliki akun CloudFlare adalah menambahkan domain `saidbahta.blog` ke CloudFlare.  

#### DNS

Setelah menambahkan domain, selanjutnya adalah mengubah Nameserver dari domain menggunakan Nameservernya cloudflare. Pengaturan Nameserver ada di control panel domain, login menggunakan akun domain. Ganti dengan dua Nameserver dibawah ini yang merupakan nameserver dari CloudFlare. 

NS      amit.ns.cloudflare.com <br>
NS      iris.ns.cloudflare.com

#### Crypto 

Setelah mengubah Nameserver, pada halaman dashboard pilih Crypto dan Pastikan dibagian Universal SSL `Status - Active Certificate` adalah Flexibel. 

#### Page Rules

Yang terakhir arahkan ke Page Rules dan klik `Create Page Rule` setelah itu buat rulenya. Masukkan nama domain http://\*saidbahta.blog/\* dan pilih Always Use HTTPS. 

tanda * sebelum saidbahta = merupakan karakter pengganti subdomain 
tanda * setelah saidbahta = merupakan karakter pengganti path

#### Buat CNAME 
Di direktory root website buat berkas CNAME yang berisi saidbahta.blog

#### Biarkan kurang lebih 24 jam 

Setelah pengaturan diatas dilakukan biasanya akan ada pesan yang memberitahukan untuk menunggu kurang lebih 24 jam, karena proses pembaruan alamat disetiap node memang membutuhkan waktu. 


#### Referensi : 
[[1] Adding HTTPS To GitHub Pages Using A Custom Domain ](https://blog.yechiel.me/adding-https-to-github-pages-using-a-custom-domain-7e4ee8ab1c50){:target="new"}<br>
[[2] Custom domains on GitHub Pages gain support for HTTPS ](https://blog.github.com/2018-05-01-github-pages-custom-domains-https/){:target="new"}<br>
[[3] Set Up SSL on Github Pages With Custom Domains for Free ](https://hackernoon.com/set-up-ssl-on-github-pages-with-custom-domains-for-free-a576bdf51bc)
