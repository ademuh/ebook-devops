---
sidebar_position: 4
---

# 4. Terraform Cloud

import useBaseUrl from '@docusaurus/useBaseUrl';

## 4.1. Setup Terraform Cloud

Disini, kita juga akan membuat akun untuk **Terraform Cloud** untuk penggunaan _Terraform_ sebagai _Software-as-a-Service_.
Kita bisa membuat akun HashiCorp melalui :
```
https://app.terraform.io/public/signup/account?product_intent=terraform
```
<img alt="Logo Gitlab" src={useBaseUrl('img/docs/t4.png')} />

> Note : link diatas akan redirect kita ke _Terraform Cloud_, kalian bisa ikuti prosesnya sampai ke page seperti digambar.

Setelah kita membuat akun HashiCorp dan mengakses dashboard _Terraform Cloud_, kita bisa mulai membuat sebuah konfigurasi ala-ala dari _Terraform Cloud_ langsung, namun sebelumnya kita harus mengakses _Terraform CLI_ dan menjalankan :
```
terraform login
```
**Output :**
```
Terraform will request an API token for app.terraform.io using your browser.

If login is successful, Terraform will store the token in plain text in
the following file for use by subsequent commands:
    /Users/redacted/.terraform.d/credentials.tfrc.json

Do you want to proceed?
  Only 'yes' will be accepted to confirm.

  Enter a value:
```
Secara otomatis, kalian akan di arahkan ke web `app.terraform.io` untuk pembuatan API Key, kalian cukup generate lalu copy paste di step selanjutnya.
```
Generate a token using your browser, and copy-paste it into this prompt.

Terraform will store the token in plain text in the following file
for use by subsequent commands:
    /Users/redacted/.terraform.d/credentials.tfrc.json

Token for app.terraform.io:
  Enter a value:
```

Untuk _Terraform Cloud_, kita akan menggunakan sebuah sample yang sudah disediakan oleh HashiCorp.
```
https://github.com/hashicorp/tfc-getting-started
```