---
sidebar_position: 7
---

# 7. Adding Input Label

import useBaseUrl from '@docusaurus/useBaseUrl';

Setelah kita menambahkan inputan, kita perlu menambahkan pula sebuah `label` agar field inputan lebih informatif. Tujuannya yakni agar user mengetahui data apa yang seharusnya diinputkan. Membuat `label` pada HTML kita bisa menggunakan tag.

```
<label>
  Content goes here
</label>
```

<br />
<a class="btn-example-code" href="https://github.com/demo-dumbways/ebook-code-result-chapter-1/tree/day2-6.adding-label-input">
Contoh code
</a>

<br />
<br />

```html {10, 14, 18, 22, 30} title="index.html"
<!DOCTYPE html>
<head>
  <title>Contact Form</title>
</head>
<body>
  <center>
    <div style="width: 350px; margin-top: 150px">
      <form action="" style="text-align: left">
        <div>
            <label for="name" >Name</label>
            <input id="name" type="text"/>
        </div>
        <div>
            <label for="email" >Email</label>
            <input id="email"  type="email"/>
        </div>
        <div>
            <label for="phone" >Phone</label>
            <input id="phone" type="text"/>
        </div>
        <div>
            <label for="subject" >Subject</label>
            <select id="subject">
                <option>Let's Talk</option>
                <option>Let's Collaboration</option>
                <option>I am Hiring</option>
            </select>
        </div>
        <div>
            <label for="message" >Your Message</label>
            <textarea id="message"></textarea>
        </div>
      </form>
    </div>
  </center>
</body>
</html>
```

<img alt="image1-1" src={useBaseUrl('img/docs/image-2-5.png')} height="500px"/>

<br />
<br />

<div>
<a class="btn-demo" href="https://ebook-code-result-chapter-1-git-day2-6addi-42c07e-demo-dumbways.vercel.app">
Demo
</a>
</div>
