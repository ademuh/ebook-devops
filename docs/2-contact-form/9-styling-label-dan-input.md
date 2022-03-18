---
sidebar_position: 9
---

# 9. Styling Label and Input

import useBaseUrl from '@docusaurus/useBaseUrl';

Kita akan menambahkan styling pada formulir yang sudah dibuat, styling yang akan kita gunakan adalah terkait `lebar`, `margin`, `padding`, `border`, `serta warna background inputan`.

<br />
<a class="btn-example-code" href="https://github.com/demo-dumbways/ebook-code-result-chapter-1/tree/day2-8.styling-label-and-input">
Contoh code
</a>

<br />
<br />

```html {10, 14-23} title="index.html"
<!DOCTYPE html>
<head>
  <title>Contact Form</title>
</head>
<body>
  <center>
    <div style="width: 350px; margin-top: 150px">
      <form action="" style="text-align: left">
        <div>
          <label for="name" style="font-size: 20px; font-weight: 700">Name</label>
          <input
            id="name"
            type="text"
            style="
            width: 100%;
            box-sizing: border-box;
            padding: 8px;
            margin-top: 5px;
            margin-bottom: 20px;
            background: #f4f3f3;
            border: 1px solid #c4c4c4;
            border-radius: 8px;
            "/>
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
        <button>
          Submit
        </button>
      </form>
    </div>
  </center>
</body>
</html>
```

<img alt="image1-1" src={useBaseUrl('img/docs/image-2-7.png')} height="500px"/>

<br />
<br />

<div>
<a class="btn-demo" href="https://ebook-code-result-chapter-1-git-day2-8styl-747973-demo-dumbways.vercel.app">
Demo
</a>
</div>
