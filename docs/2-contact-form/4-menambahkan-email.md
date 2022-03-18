---
sidebar_position: 4
---

# 4. Adding Email Input

import useBaseUrl from '@docusaurus/useBaseUrl';

Setelah membuat inputan name dan phone number, selanjutnya kita tambahkan input bertipe `email` untuk menerima inputan **Email**. Menggunakan inputan bertipe `email` karena inputan bertipe `email` memiliki `default validasi`, maksudnya adalah nilai yang diinputkan harus berupa alamat email (terdapat simbol @).

<br />
<a class="btn-example-code" href="https://github.com/demo-dumbways/ebook-code-result-chapter-1/tree/day2-3.adding-email-input">
Contoh code
</a>

<br />
<br />

```html {12-14} title="index.html"
<!DOCTYPE html>
<head>
  <title>Contact Form</title>
</head>
<body>
  <center>
    <div style="width: 350px; margin-top: 150px">
      <form action="" style="text-align: left">
        <div>
          <input id="name" type="text"/>
        </div>
        <div>
          <input id="email"  type="email"/>
        </div>
        <div>
          <input id="phone" type="text"/>
        </div>
      </form>
    </div>
  </center>
</body>
</html>
```

<img alt="image1-1" src={useBaseUrl('img/docs/image-2-2.png')} height="500px"/>

<br />
<br />

<div>
<a class="btn-demo" href="https://ebook-code-result-chapter-1-git-day2-3addi-6cbe3e-demo-dumbways.vercel.app">
Demo
</a>
</div>
