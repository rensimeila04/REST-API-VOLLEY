# RestAPI Volley

  . |App record|App Screenshot|.|
----|----|----|----|
----|![record]|<a href="https://www.fsf.org"><img  width="330" src="https://github.com/rensimeila04/REST-API-VOLLEY/blob/master/Screen/shot.png"> </a>|----|

[record]: https://github.com/rensimeila04/REST-API-VOLLEY/blob/master/Screen/record.gif



## What is JSON
>JSON (JavaScript Object Notation) adalah sebuah format data yang digunakan untuk pertukaran dan penyimpanan data.
>
>JSON merupakan bagian (subset) dari Javascript. JSON bisa dibaca dengan berbagai macam bahasa pemrograman seperti C, C++, C#, Java, Javascript Perl, Python, dan banyak lagi.
>
>Hal ini membuat JSON menjadi bahasa yang ideal untuk perturakan data antar aplikasi.
>
>JSON bahkan mendominasi pendahulunya si XML (eXtensible Markup Language)…
## What is Volley?
> Volley adalah library HTTP yang mempermudah dan, yang terpenting, mempercepat networking untuk aplikasi Android. Volley tersedia di [GitHub](https://github.com/google/volley).

## What are the benefits?
>Volley menawarkan manfaat-manfaat berikut:
>
- [x] Penjadwalan otomatis permintaan jaringan.
- [x] Beberapa koneksi jaringan serentak.
- [x] Caching respons disk dan memori transparan dengan koherensi cache HTTP standar.
- [x] Dukungan untuk pemrioritasan permintaan.
- [x] API permintaan pembatalan. Anda bisa membatalkan satu permintaan, atau menetapkan blok atau cakupan permintaan untuk dibatalkan.
- [x] Kemudahan kustomisasi, misalnya, untuk mencoba ulang dan backoff.
- [x] Pemesanan kuat yang memudahkan pengisian UI Anda dengan benar menggunakan data yang diambil secara asinkron dari jaringan.
- [x] Fitur proses debug dan penelusuran.

## How to add Volley?
>Library Volley inti dikembangkan di GitHub dan berisi pipeline pengiriman permintaan utama serta seperangkat utilitas yang berlaku secara umum, dan tersedia di "toolbox" Volley. Berikut cara untuk menambahkan volley ke aplikasi Anda:
1. Buat project baru.
2. Buka build.gradle(Module: app) dan tambahkan dependencies berikut:
```java
  dependencies {
        ...
        implementation 'com.android.volley:volley:1.1.1'
    }
```
3. Di AndroidManifest.xml tambahkan internet permission seperti berikut:
```java
 <uses-permission android:name="android.permission.INTERNET />"
 ```
 
## What are the types of requests using Volley?
- [x] <b>String Request</b>
> Pengunaan String Request sendiri biasanya digunakan bersamaan dengan JSON, karena string yang ingin diambil tersebut berada dalam JSON. Berikut struktur yang biasa digunakan:

```java
String url = "https:// string_url/";
StringRequest stringRequest = new StringRequest(Request.Method.GET, url, new Response.Listener() {
			@Override
			public void onResponse(String response)
			{
			}
		},
		new Response.ErrorListener() {
			@Override
			public void onErrorResponse(VolleyError error)
			{
			}
		});
requestQueue.add(stringRequest);
```
- [x] <b>JsonObjectRequest dan JsonArrayRequest</b>
```java
JsonArrayRequest jsonArrayRequest = new JsonArrayRequest(Request.Method.GET, url, null, new Response.Listener() {
			@Override
			public void onResponse(JSONArray response)
			{
			}
		},
		new Response.ErrorListener() {
			@Override
			public void onErrorResponse(VolleyError error)
			{
			}
		});
requestQueue.add(jsonArrayRequest);
```

## What is the difference betwen <b>Volley</b> and <b>Retrofit</b>

Retrofit|Volley|
------|------|
Retrofit merupakan Library turunan dari OkHTTP yang dibuat oleh Square yang digunakan sebagai REST Client pada Android, yang pasti akan memudahkan kita. Karena kita tidak perlu lagi untuk membuat Method sendiri untuk menggunakan REST Client API dan Backend. Library ini menyediakan framework yang powerfull untuk authenticating dan berinteraksi dengan API dengan mengirimkan request menggunakan OkHTTP.| Volley adalah library HTTP yang mempermudah dan yang terpenting mempercepat networking untuk aplikasi Android, tetapi Library buatan Google ini kurang popular dibanding retrofit, Karena fitur yang dimilikinya pun sedikit Secara default. Volley menggunakan metode sinkronisasi. Jadi tidak perlu membuat sebuah Method atau tungsi yang menggunakan Glass Asynctask. Dalam penggunaannya memang sulit. Volley tidak cocok untuk operasi download atau streaming yang besar karena Volley menyimpan semua respons dalam memori selama mengambil data API.|

## Reference
- [ ] https://developer.android.com/training/volley
- [ ] https://socs.binus.ac.id/2017/09/15/androidvolley/
- [ ] https://www.petanikode.com/json-pemula/
- [ ] https://rivaldi48.blogspot.com/2019/11/Fast-Android-Networking-vs-Retrofit-vs-Volley-Mana-Yang-Lebih-Baik.html
