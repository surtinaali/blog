---
layout:     post
title:      Memperkecil ukuran berkas gambar PNG menggunakan PNGQUANT
date:       2018-12-11 10:47:00 +0900
categories: dokumentasi
img_path:   assets/img/post/190115b.svg
---

Ukuran berkas gambar yang besar sering menjadi masalah pada saat loading sebuah website. Banyak trik yang bisa dilakukan untuk mempercepat waktu tunggu pada saat gambar diload untuk ditampilkan. Salah satu trik yang sering digunakan adalah dengan memperkecil ukuran berkas. 

PNGQUANT adalah sebuah aplikasi compress khusus untuk gambar dengan tipe berkas PNG. PNGQUANT melakukan compress [_baca: memperkecil_] ukurang gambar dengan mengkonfersi gambar PNG 32bit menjadi gambar PNG 8bit. 

PNGQUANT bisa didownload langsung di halaman resminya PNGQUANT. Alamatnya telah disertakan dibagian Referensi. 

#### Cara memperkecil ukuran gambar PNG 

{% highlight POWERSHELL %}
pngquant.exe namaBerkas.png 
{% endhighlight %}

setelah proses compress selesai akan dibuat berkas baru dengan nama _namaBerkas-fs8.png_

_Pada contoh gambar yang saya konversi menggunakan PNGQUANT, kapasitas gambar sebelumnya 607 KB dikecilkan menjadi 233 KB dan gambarnya masih terlihat sama antara gambar asli dan gambar hasil konversi._

#### Pilihan perintah lain 
<pre>
  --force           overwrite existing output files (synonym: -f)
  --skip-if-larger  only save converted files if they're smaller than original
  --output file     destination file path to use instead of --ext (synonym: -o)
  --ext new.png     set custom suffix/extension for output filenames
  --quality min-max don't save below min, use fewer colors below max (0-100)
  --speed N         speed/quality trade-off. 1=slow, 3=default, 11=fast & rough
  --nofs            disable Floyd-Steinberg dithering
  --posterize N     output lower-precision color (e.g. for ARGB4444 output)
  --strip           remove optional metadata (default on Mac)
  --verbose         print status messages (synonym: -v)
</pre>


#### Referensi : 
[[1] &nbsp; Halaman Resmi PNGQUANT ](https://pngquant.org/){:target="new"}<br>