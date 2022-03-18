---
sidebar_position: 6
---

# 6. Adding Text Area

import useBaseUrl from '@docusaurus/useBaseUrl';

**Text area** merupakan text inputan yang bisa menampung lebih dari satu baris inputan. Tag `textarea` mirip dengan tag input `type text`, namun memiliki kelebihan untuk menampung beberapa baris (multiple line). Sehingga `textarea` akan kita gunakan untuk menampung inputan pesan yang akan disampaikan oleh pengunjung nantinya.

<br />
<a class="btn-example-code" href="https://github.com/demo-dumbways/ebook-code-result-chapter-1/tree/day2-5.adding-text-area">
Contoh code
</a>

<br />
<br />

```html {25-27} title="index.html"
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
        <div>
            <textarea id="message"></textarea>
        </div>
      </form>
    </div>
  </center>
</body>
</html>
```

<img alt="image1-1" src={useBaseUrl('img/docs/image-2-4.png')} height="500px"/>

<br />
<br />

<div>
<a class="btn-demo" href="https://ebook-code-result-chapter-1-git-day2-5addi-4f4cf0-demo-dumbways.vercel.app">
Demo
</a>
</div>
