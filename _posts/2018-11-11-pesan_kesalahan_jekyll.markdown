---
layout: post
title:  "Pesan Kesalahan Jekyll"
date:   2018-11-11 13:37:00 +0900
categories: jekyll
img_path: assets/img/post/noimage.svg
---

Artikel ini berisi beberapa pesan kesalahan _(read : error message)_ yang sering saya temui pada saat menjalankan jekyll. Beberapa pesan kesalahan tersebut muncul setelah melakukan update.  

#### Pesan Kesalahan 1
{% highlight POWERSHELL %}
... 
Could not find public_suffix-3.0.2 in any of the source (Bundler::GemNotFound)
{% endhighlight %}

##### _Solusi_  
{% highlight POWERSHELL %}
gem install public_suffix --version 3.0.2
bundle update
{% endhighlight %}

<br>

#### Pesan Kesalahan 2

{% highlight POWERSHELL %}
cannot load such file -- 2.5/rubyeventmachine (LoadError)
{% endhighlight %}

##### _Solusi_

{% highlight POWERSHELL %}
gem uninstall eventmachine 
gem install eventmachine --platform ruby
{% endhighlight %}

<br>

#### Pesan Kesalahan 3 

{% highlight POWERSHELL %}
You have already activated concurrent-ruby 1.1.3, but your gemfile requires concurrent-ruby 1.0.5. Prepending 'bundle exec' to your command may solve this. (Gem::LoadError)
{% endhighlight %}


##### _Solusi_ 
{% highlight POWERSHELL %}
bundle exec jekyll serve -l
{% endhighlight %}
