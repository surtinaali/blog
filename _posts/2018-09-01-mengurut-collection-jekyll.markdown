---
layout: post
title: "Mengurut Jekyll Collection"
date: 2019-01-09 10:43:02 +0900
categories: jekyll
img_path: assets/img/post/noimage.svg
---

Untuk menampilkan berita berupa collection di jekyll saya menggunakan kode dibawah ini. Masalahnya adalah jekyll mengurutkan collection berdasarkan huruf menyebabkan artikel yang paling terakhir tidak muncul di halaman depan karena hanya dibatasi 4 artikel untuk halaman depan. 


{% highlight LIQUID %}
{% raw %}
{% for berita in site.berita limit: 4 %}
        <div class="col-md-6 pb-4">
            <div class="card">
                <img class="card-img-top" src="{{baseurl}}{{ berita.gambar }}">
                <div class="card-body">
                    <h5 class="card-title mb-2 font-asap">{{ berita.title }}</h5>
                    <p class="card-text"><small class="text-muted">&nbsp;<i class="far fa-calendar-alt"></i> {{
                            berita.waktu }} &nbsp;&nbsp; <i class="fas fa-user-tie"></i> {{berita.penulis}}</small></p>
                    <a href="{{baseurl}}{{ berita.url }}" style="text-decoration: none" class="text-dark">
                        {{ berita.excerpt | strip_html | truncatewords: 30 }}
                    </a>
                </div>
            </div>
        </div>
{% endfor %}
{% endraw %}
{% endhighlight %}

Hasil bertanya ke google, beberapa artikel menyarankan untuk membuat di depan nama fail markdown menggunakan nomor misalnya 1-artikel.md, 2-artikel.md, dst. 

{% highlight LIQUID %}
{% raw %}
{% assign daftar-berita = site.berita | reverse %}
        {% for berita in daftar-berita limit:4 %}
        <div class="col-md-6 pb-4">
            <div class="card">
                <img class="card-img-top" src="{{ berita.gambar }}">
                <div class="card-body">
                    <h5 class="card-title mb-2 font-asap">{{ berita.title }}</h5>
                    <p class="card-text"><small class="text-muted">&nbsp;<i class="far fa-calendar-alt"></i> {{
                            berita.waktu }} &nbsp; <i class="fas fa-user-tie"></i> {{berita.penulis}}</small></p>
                    <a href="{{baseurl}}{{ berita.url }}" style="text-decoration: none" class="text-dark">
                        {{ berita.content | strip_html | truncatewords: 30 }}
                    </a>
                    <br>
                </div>
            </div>
        </div>
        {% endfor %}
{% endraw %}
{% endhighlight %}

Cara lainnya adalah menambahkan front mater nomor di artikel, agar artikel nanti diurutkan menggunakan nomor tersebut. 

{% highlight LIQUID %}
---
layout: artikel
title: Opini Satu 
gambar: /assets/img/gambar_umum/kegiatan-kampus.jpg
waktu: 12 Desember 2018
penulis: Said D. Bahta
nomor: 1
---
{% endhighlight %}

{% highlight LIQUID %}
{% raw %}
{% assign daftar-berita = site.berita | sort: 'nomor' | reverse %}
        {% for berita in daftar-berita limit:4 %}
        <div class="col-md-6 pb-4">
            <div class="card">
                <img class="card-img-top" src="{{ berita.gambar }}">
                <div class="card-body">
                    <h5 class="card-title mb-2 font-asap">{{ berita.title }}</h5>
                    <p class="card-text"><small class="text-muted">&nbsp;<i class="far fa-calendar-alt"></i> {{
                            berita.waktu }} &nbsp; <i class="fas fa-user-tie"></i> {{berita.penulis}}</small></p>
                    <a href="{{baseurl}}{{ berita.url }}" style="text-decoration: none" class="text-dark">
                        {{ berita.content | strip_html | truncatewords: 30 }}
                    </a>
                    <br>
                </div>
            </div>
        </div>
        {% endfor %}
{% endraw %}
{% endhighlight %}

#### Referensi : 
[[1] &nbsp; Sort Order Of Jekyll Collection](http://stories.upthebuzzard.com/jekyll_notes/2017-02-19-sort-order-of-jekyll-collections.html){:target="new"}<br>
[[2] &nbsp; Ordering Jekyll Collection](http://third-bit.com/2017/02/25/ordering-jekyll-collections.html){:target="new"}<br>