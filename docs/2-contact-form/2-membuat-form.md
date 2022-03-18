---
sidebar_position: 2
---

# 2. Creating Form

import useBaseUrl from '@docusaurus/useBaseUrl';

Membuat sebuah form di halaman web, kita bisa menggunakan `tag form` atau biasa dikenal sebagai tag

```
<form>Content goes here</form>
```

Menggunakan tag form, kita dapat membuat sebuah form yang menyerupai form kertas atau basis data karena pengguna web mengisi form menggunakan kotak centang, tombol radio, atau bidang teks.

Pada case kali ini kita akan membuat sebuah form yang akan terdapat inputan berjeniskan `text, email, select, dan menggunakan textarea`.

<br />
<a class="btn-example-code" href="https://github.com/demo-dumbways/ebook-code-result-chapter-1/tree/day2-1.create-form">
Contoh code
</a>

<br />
<br />

```html {8-10} title="index.html"
<!DOCTYPE html>
<head>
  <title>Contact Form</title>
</head>
<body>
  <center>
    <div style="width: 350px; margin-top: 150px">
      <form action="" style="text-align: left">
        <!-- Content goes here -->
      </form>
    </div>
  </center>
</body>
</html>
```
