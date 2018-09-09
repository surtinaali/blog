---
layout: post
title: "Mengapa harus menggunakan CSS preprocessor"
date: 2018-09-07 05:57:00 +0900
categories: tinjauan
img_path: assets/img/post/180907.svg
---

Kita bisa saja menulis kode CSS tanpa bantuan CSS preprocessor, namun seiring dengan berkembangnya kode yang ditulis, akan sangat menyulitkan ketika melakukan perawatan atau perbaikan kode. Sederhananya, itulah alasan kita membutuhkan CSS preprocessor.

Ada beberapa CSS preprocessor yang digunakan oleh web developer, seperti SASS, LESS dan STYLUS. Walaupun pada umumnya SASS, LESS dan STYLUS memiliki fitur yang sama, pembahasan dalam artikel ini akan membahas khusus tentang SASS sebagai salah satu CSS preprocessor, <del>tidak ada alasan khusus mengapa SASS</del>.   

#### Variabel
Variabel menyimpan nilai atau `value` dari sebuah properti CSS. Ketika menulis nilai sebuah properti, dibanding menulis langsung nilainya, yang ditulis adalah nama variabel. Sehingga ketika nilai dari warna latar atau properti `background` kedepannya ingin dirubah, jika ada lebih dari satu properti `background`, kita hanya perlu mengganti `value` yang ada di variabel.

Contoh kode SCSS : 
{% highlight SCSS %}
$background-primary: #333;
nav {
    background: $background-primary;
  }
footer {
    background: $background-primary;
  }
{% endhighlight %}

Setelah dikompilasi ke CSS : 
{% highlight CSS %}
nav {
    background: #333;
  }
footer {
    background: #333;
  }
{% endhighlight %}

#### Nesting (bersarang)
Struktur kode HTML memiliki struktur berupa hirarki. Ketika menulis kode CSS, terkadang kita perlu menulis selector yang ditujukan khusus di dalam sebuah selector, misalnya selector `ul`, `li` dan `a` yang ada didalam selector `nav`. 

Tanpa SASS, kode CSS yang ditulis akan terlihat seperti ini : 

{% highlight CSS %}
nav ul {
  properti: value;
  }
nav li {
  properti: value;
  }
nav a {
  properti: value;
  }
{% endhighlight %}

Dengan SASS, kode CSS akan terlihat lebih simpel : 

{% highlight SCSS %}
nav {
  ul {
      properti: value;
  }
  li {  
      properti: value; 
  }
  a {
     properti: value;
  }
}
{% endhighlight %}

#### Parsial dengan @import

Fitur ini sangat bermanfaat untuk fail CSS yang besar dengan banyak baris. Akan sangat menyulitkan jika kode CSS yang besar tersebut tidak dipisah menjadi fail-fail kecil atau disebut `partial`.

Fail besar yang semua kode CSS tergabung dalam satu fail, ketika di-parsial maka akan menjadi beberapa fail-fail kecil, misalnya menjadi fail  `_reset.scss`, `_layout.scss`, `_button.scss`, `_typography.scss` dan seterusnya. 
Fail-fail parsial tersebut kemudian akan digabung kembali menggunakan `@import`. 

Import, sesuai makna kalimatnya digunakan untuk memasukkan satu atau beberapa fail SASS ke fail SASS lainnya. 

{% highlight SCSS %}
//style.scss
@import 'reset';
@import 'layout';
@import 'button';
@import 'typography';
{% endhighlight %}

#### Mixin dan Include
Mixin digunakan ketika membuat grup deklarasi kode CSS, dengan kata lain, beberapa properti dan nilai CSS digabung menjadi satu grup. Misalnya pada saat menulis kode prefix vendor.    

{% highlight SCSS %}
@mixin transform($property) {
  //deklarasi
  -webkit-transform: $property;
      -ms-transform: $property;
          transform: $property;
  }

.box { 
  @include transform(rotate(30deg)); 
  }
{% endhighlight %}

$preperty dalam kode diatas merupakan [variabel](#variabel).

Setelah dikompilasi ke CSS : 

{% highlight CSS %}
.box {
  -webkit-transform: rotate(30deg);
  -ms-transform: rotate(30deg);
  transform: rotate(30deg);
}
{% endhighlight %}

Mixin juga dapat digunakan khusus untuk selector layout atau selector lain yang memiliki properti yang sama antara satu selector dengan selector lainnya. Dibanding harus menuliskan properti-properti tersebut secara berulang, kita bisa membuat sebuah mixin dan gunakan mixin tersebut setiap menulis deklarasi CSS.  

{% highlight SCSS %}
@mixin layout($width, $height, $bg){
  //deklarasi
  width: $width; 
  height: $height;
  background: $bg;
}
header {
  @include layout(100vw, 100vh, white);
}
footer {
  @include layout(80vw, 80vh, black);
}
{% endhighlight %}

Setelah dikompilasi ke CSS : 

{% highlight CSS %}
header {
  width: 100vw;
  height: 100vh;
  background: white;
}
footer {
  width: 800vw;
  height: 80vh;
  background: black;
}
{% endhighlight%}

#### Extend (pewarisan)
Maksud dari pewarisan adalah ketika dua selector berbeda memiliki deklarasi (properti dan value) yang sama. 

{% highlight SCSS %}
%message-shared {
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}
.message {
  @extend %message-shared;
}
.success {
  @extend %message-shared;
  border-color: green;
}
.error {
  @extend %message-shared;
  border-color: red;
}
.warning {
  @extend %message-shared;
  border-color: yellow;
}
{% endhighlight %}

Dalam contoh diatas, .message, .seccess, .error dan .warning memiliki kesamaan border, padding dan color. 

{% highlight CSS %}
.message, .success, .error, .warning {
  border: 1px solid #cccccc;
  padding: 10px;
  color: #333;
}
.success {
  border-color: green;
}
.error {
  border-color: red;
}
.warning {
  border-color: yellow;
}
{% endhighlight %}

#### Operasi Matematika

Sederhananya kita dapat menggunakan operasi matematika, +, -, /, * untuk menghitung nilai properti.

{% highlight SCSS %}
.container { width: 100%; }
article[role="main"] {
  float: left;
  width: 600px / 960px * 100%;
}
aside[role="complementary"] {
  float: right;
  width: 300px / 960px * 100%;
}
{% endhighlight %}

Setelah dikompilasi ke CSS : 

{% highlight CSS %}
.container {
  width: 100%;
}
article[role="main"] {
  float: left;
  width: 62.5%;
}
aside[role="complementary"] {
  float: right;
  width: 31.25%;
}
{% endhighlight %}

<br>
#### Referensi : 
[[1] &nbsp; Sass Basics](https://sass-lang.com/guide){:target="new"}<br>
[[2] &nbsp; 10 Reasons to Use a CSS Preprocessor in 2018](https://raygun.com/blog/10-reasons-css-preprocessor/){:target="new"}<br>