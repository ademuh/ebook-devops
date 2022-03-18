---
sidebar_position: 3
---

# 3. Adding Text Input

import useBaseUrl from '@docusaurus/useBaseUrl';

Setelah kita membuat kerangka form, maka kita bisa menambahkan inputan - inputan. Kita bisa memulainya dengan membuat inputan untuk **name** dan **phone number** menggunakan input bertipekan `text`. **Input bertipe text** merupakan inputan yang dapat menerima berbagai macam karakter seperti `huruf`, `angka`, ataupun `simbol`.

<br />
<a class="btn-example-code" href="https://github.com/demo-dumbways/ebook-code-result-chapter-1/tree/day2-2.adding-text-input">
Contoh code
</a>

<br />
<br />

```html {9-14} title="index.html"
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
          <input id="phone" type="text"/>
        </div>
      </form>
    </div>
  </center>
</body>
</html>
```

<img alt="image1-1" src={useBaseUrl('img/docs/image-2-1.png')} height="500px"/>

<br />
<br />

<div>
<a class="btn-demo" href="https://ebook-code-result-chapter-1-git-day2-2addi-77d351-demo-dumbways.vercel.app">
Demo
</a>
</div>
