---
layout: post
title: "Instalasi Rouge Highligter untuk Jekyll "
date: 2018-08-08 10:47:00 +0900
categories: Dokumentasi
img_path: assets/img/post/080818.svg
---

Rouge highlighter merupakan pewarna kode program bawaan jekyll yang mengenali kurang lebih 135 bahasa komputer. Tulisan ini merupakan dokumentasi bagaimana cara menginstal, mengkonfigurasi dan menggunakan rouge highlighter.   

Apa itu highligter? 

_coba perhatikan kode program dibawah ini. Tanpa rouge highlighter_ : 

<pre>
statusApp() {
	if [[ $APP_STATUS = 1 ]]; then 
		echo "$APP_NAME is running with PID : $OLD_PID, OLD_PID : `cat $FILE_PID` ."
	else 
		echo "$APP_NAME is not running."
	fi
}
</pre>
{:.highlight}


_bedakan dengan yang sudah menggunakan rouge highlighter_ : 

{% highlight BASH %}
statusApp() {
	if [[ $APP_STATUS = 1 ]]; then 
		echo "$APP_NAME is running with PID : $OLD_PID, OLD_PID : `cat $FILE_PID` ."
	else 
		echo "$APP_NAME is not running."
	fi
}
{% endhighlight %}

selain karena kode program terlihat lebih indah dengan warna, menggunakan kode higlighter juga berfungsi untuk kemudahan dalam mengidetifikasi bagian-bagian kode program.     

#### Instalasi rouge 
Instalasi dilakukan melalui _command line interface_, dengan menggunakan perintah :  

{% highlight POWERSHELL %}
gem install rouge 
{% endhighlight %}

_\* karena rouge merupakan bawaan jekyll, maka langkah instalasi ini bisa di lewatkan_
{:.text-secondary}

#### Konfigurasi
Ubah konfigurasi yang ada pada fail `_config.yml` dengan menambahkan baris berikut : 

{% highlight YAML %}
highlighter: rouge
{% endhighlight %}

Setelah `highlighter: rouge` ditambahkan, langkah selanjutnya adalah memilih tema atau style rouge sesuai dengan yang diinginkan. 

Untuk melihat daftar tema atau style rouge yang tersedia gunakan perintah : 

{% highlight POWERSHELL %}
rougify help style
{% endhighlight %}

`tema yang tersedia : base16, base16.dark, base16.light, base16.monokai, base16.monokai.dark, base16.monokai.light, base16.solarized, base16.solarized.dark, base16.solarized.light, colorful, github, gruvbox, gruvbox.dark, gruvbox.light, igorpro, molokai, monokai, monokai.sublime, pastie, thankful_eyes, tulip`

Pilih salah satu tema yang tersedia kemudian konfersi menjadi fail css ke dalam folder asset.  

{% highlight POWERSHELL %}
rougify style pastie > assets/css/syntax.css
{% endhighlight %}

Setelah fail css dari tema rouge dikonfersi, tambahkan tema tersebut ke dalam kode html diantara tag `<head>` dan `</head>`. 

{% highlight HTML %}
<link rel="stylesheet" href="{{site.baseurl}}/assets/style/css/syntax.css">
{% endhighlight %}

#### Menggunakan rouge 
Untuk menggunakan rouge highlitter dalam menulis potongan kode gunakan `{% highlight HTML %}` dan akhiri dengan `{% endhighlight %}`, seperti contoh berikut :


{% highlight LIQUID %}
{% raw %}
{% highlight HTML %}
    //kodenya masukkan disini
{% endhighlight %}
{% endraw %}
{% endhighlight %}

#### Daftar Pustaka 
[1. Jekyllrb](https://jekyllrb.com/docs/templates/#code-snippet-highlighting){:target="new"}<br>
[2. Syntax Highlighting in Jekyll With Rouge](https://sacha.me/articles/jekyll-rouge/){:target="new"}<br>
[3. Add Syntax Highlighting to your Jekyll site with Rouge](https://bnhr.xyz/2017/03/25/add-syntax-highlighting-to-your-jekyll-site-with-rouge.html){:target="new"}<br>
[](){:target="new"}<br>