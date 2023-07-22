---
layout: post
title: "Perbaiki Masalah, Could not find a VM named 'GNS3 VM'"
date: 2023-07-21 06:30:00 +0900
categories: dokumentasi-gns3
img_path: assets/img/post/noimage.svg
---

Baru pertama mencoba GNS3, seperti biasa harus diinstall terlebih dahulu, hanya saja ada masalah pada saat menghubungkan GNS3 dengan `GNS3 VM` yang jalan di VMware Player muncul pesan ini `"Could not find a VM named 'GNS3 VM', is it imported in VMware or VirtualBox?"`. Setelah beberapa kali dicoba, diketahui bahwa masalah tersebut muncul karena pada saat saya menginport `GNS3 VM`-nya saya merubah lokasi default tempat disimpannya File HDD dan Configurasi VMware untuk `GNS3 VM`, jika dibiarkan default tidak ada masalah sama sekali, namun saya perlu menggantinya karena lokasi default file `GNS3 VM` disimpan di OneDrive yang sangat terbatas kapasitasnya sehingga tidak cukup menampung file-file VMware. 

Ternyata untuk bisa mengganti lokasi default dari `GNS3 VM` pada saat diimport kita juga perlu merubah file `preferences.ini` dengan menambahkan baris `prefvmx.defaultvmpath = "C:\VMs"` agar bisa terhubung dengan GNS3, `C:\VMs` diganti dengan lokasi atau folder `GNS3 VM` yang kita rubah pada saat import.

Untuk menambahkan baris tersebut caranya cukup mudah, Klik Kanan di logo Windows lalu pilih run atau tekan Logo `Windows + R` di keyboard, setelah muncul dialog box run, ketikkan `%appdata%\VMware\preferences.ini` lalu klik ok atau tekan Enter. Setelah muncul di notepad, tinggal ditambahkan 1 baris baru `prefvmx.defaultvmpath = "C:\VMs"`. 

Isi lengkap file `preferences.ini` dikomputer saya seperti ini : 

{% highlight INI %}
.encoding = "windows-1252"
pref.keyboardAndMouse.vmHotKey.enabled = "FALSE"
pref.keyboardAndMouse.vmHotKey.count = "0"
pref.vmplayer.firstRunDismissedVersion = "17.0.2"
hint.confirmLaxOVFImport = "FALSE"
hints.hideAll = "FALSE"
pref.mruVM0.filename = "D:\VMWARE\GNS3 VM\GNS3 VM.vmx"
pref.mruVM0.displayName = "GNS3 VM"
pref.mruVM0.index = "0"
prefvmx.defaultvmpath = "D:\VMWARE"
{% endhighlight %}

#### Referensi : 
[[1] Could Not Find a vm named gns3 vm](https://gns3.com/community/featured/could-not-find-a-vm-named-gns3-vm){:target="new"}<br>
