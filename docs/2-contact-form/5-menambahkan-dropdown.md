---
sidebar_position: 5
---

# 5. Adding Dropdown

import useBaseUrl from '@docusaurus/useBaseUrl';

Membuat `dropdown` pada HTML kita bisa menggunakan tag

```
<select>Content goes here</select>
```

Ketika kita menggunakan tag select, kita membutuhkan tag

```
<option>Content goes here</option>
```

**Tag option** disini berguna untuk menampilkan pilihan - pilihan jawaban pada `dropdown` nantinya. Pada tag option kita perlu `menambahkan atribut value`, karena kita membutuhkan nilai yang nantinya akan disimpan/digunakan.

<br />
<a class="btn-example-code" href="https://github.com/demo-dumbways/ebook-code-result-chapter-1/tree/day2-4.adding-dropdown">
Contoh code
</a>

<br />
<br />

```html {18-24} title="index.html"
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
        <div>
          <select id="subject">
            <option>Let's Talk</option>
            <option>Let's Collaboration</option>
            <option>I am Hiring</option>
          </select>
        </div>
      </form>
    </div>
  </center>
</body>
</html>
```

<img alt="image1-1" src={useBaseUrl('img/docs/image-2-3.png')} height="500px"/>

<br />
<br />

<div>
<a class="btn-demo" href="https://ebook-code-result-chapter-1-git-day2-4addi-83dd81-demo-dumbways.vercel.app">
Demo
</a>
</div>
