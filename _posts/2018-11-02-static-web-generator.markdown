---
layout: post
title: Apa itu Generator Web Statis ?
date: 2018-11-02 02:21:00 +0900
categories: pemula
img_path: assets/img/post/181102.svg
---

Generator web statis adalah sebuah perangkat lunak yang digunakan untuk mempermudah dalam membuat dan mengatur website yang dibangun menggunakan teknologi Web Statis (HTML, CSS dan JavaScript). Tidak ada proses query data pada website statis, semua konten tersimpan di dalam fail. 

HTML digunakan untuk membangun struktur konten website, CSS digunakan untuk membentuk layout dari website, sementara JavaScript digunakan untuk membuat website lebih interaktif. 

Kekurangan dari website statis adalah sulit dalam tahap pembuatan karena banyaknya baris kode HTML yang harus dibuat berulang. Alasan tersebut merupakan salah satu alasan mengapa web dinamis lebih diminati dibanding web statis, setidaknya sampai saat sekarang ini ketika mulai banyak _Generator web Statis_ dikembangkan dan menyaingi sistem web dinamis. 

Bisa dikatakan _Generator Web Statis_ membantu pembuat website melakukan hal-hal yang dulunya hanya dapat dilakukan di web dinamis, seperti melakukan perulangan, menggunakan kondisi, membuat dan menggunakan variabel dan beberapa fitur lainnya.

Berbeda dengan Web System seperti CMS. _Generator web statis_ bukan bagian dari website, generator web statis hanya membantu menghasilkan website. 

Dua contoh generator web statis dibawah adalah yang popular digunakan saat ini : 

##### 1. Jekyll 
Jekyll adalah sebuah generator web statis yang cocok digunakan untuk pribadi, proyek atau organisasi [[1]](https://github.com/jekyll/jekyll){:target="new"}. 

Dengan mengambil konten website yang tersimpan dalam fail _Markdown_ dan _YAML_ kemudian memasukkan konten tersebut kedalam Layout yang dibuat menggunakan _HTML_ dan _Liquid_, Jekyll kemudian mengkompilasi atau menghasilkan website statis yang siap untuk di hosting tanpa basis data.

Jekyll dibuat menggunakan bahasa pemprograman Ruby oleh komunitas Jekyll dan dilisensikan dibawah lisensi MIT. 

##### 2. Hugo 
Hugo adalah generator website statis modern dan tercepat yang tersimpan menggunakan bahasa Go [[2]](https://gohugo.io/about/what-is-hugo/){:target="new"}. 

_Saya belum pernah menggunakan Hugo sebelumnya_, tapi secara umum dijelaskan dalam dokumentasi Hugo bahwa Hugo menggunakan direktori sumber dari fail dan tema dan menggunakannya sebagai input untuk membuat website [[3]](https://gohugo.io/about/what-is-hugo/#what-does-hugo-do){:target="new"}.

##### Alasan mengapa menggunakan Web Statis

<table>
	<tr>
		<td valign="top" width="105px">Aman</td>
		<td valign="top" width="15px" align="center">:</td>
		<td>tidak ada proses query yang biasa digunakan oleh hacker untuk melakukan SQL Injection.</td>
	</tr>
	<tr>
		<td valign="top">Cepat</td>
		<td valign="top" align="center">:</td>
		<td>website dinamis harus melakukan query data sebelum website ditampilkan, sementara website statis tidak perlu melakukan query untuk menampilkan data.</td>
	</tr>
	<tr>
		<td valign="top">Ketersedian</td>
		<td valign="top" align="center">:</td>
		<td>kekurangan dari menggunakan website dinamis terkadang terjadi kesalahan pada server basis data menyebabkan data tidak bisa diakses. Tidak perlu khawatir dengan dengan kegagalan akses data jika menggunakan website statis.</td>
	</tr>
</table>
<br>

[[1]  &nbsp; Jekyllrb](https://github.com/jekyll/jekyll){:target="new"}<br>
[[2]  &nbsp; Apa Itu Hugo ?](https://github.com/jekyll/jekyll){:target="new"}<br>
[[3]  &nbsp; Apa Yang di Lakukan Hugo ?](https://gohugo.io/about/what-is-hugo/#what-does-hugo-do){:target="new"}