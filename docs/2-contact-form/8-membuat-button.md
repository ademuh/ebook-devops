---
sidebar_position: 8
---

# 8. Adding Button

import useBaseUrl from '@docusaurus/useBaseUrl';

Sebuah formulir pasti memiliki sebuah `button` yang berfungsi untuk memproses data yang telah diinput ke dalam `textfield`. `Button` dapat dituliskan dengan cara menuliskan tag.

```
<button>
  Content goes here
</button>
```

Button sendiri terdiri dari 2 tipe, yakni `submit dan reset`. Pada case ini kita akan menggunakan `button` bertipe `submit`.

<br />
<a class="btn-example-code" href="https://github.com/demo-dumbways/ebook-code-result-chapter-1/tree/day2-7.adding-button">
Contoh code
</a>

<br />
<br />

```html {33-35} title="index.html"
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
        <button>
          Submit
        </button>
      </form>
    </div>
  </center>
</body>
</html>
```

<img alt="image1-1" src={useBaseUrl('img/docs/image-2-6.png')} height="500px"/>

<br />
<br />

<div>
<a class="btn-demo" href="https://ebook-code-result-chapter-1-git-day2-7addi-3abcfc-demo-dumbways.vercel.app">
Demo
</a>
</div>
