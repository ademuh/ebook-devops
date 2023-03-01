---
sidebar_position: 2
---

# 2. First Setup

import useBaseUrl from '@docusaurus/useBaseUrl';

## 2.1. Instalasi Terraform

Disini, kita akan menggunakan terraform melalui device local kita, sehingga kita harus melakukan instalasi _Terraform_ terlebih dahulu.

1. Install _dependency_ yang dibutuhkan.
```
sudo apt-get update && sudo apt-get install -y gnupg software-properties-common
```

2. Install GPG Key HashiCorp.
```
wget -O- https://apt.releases.hashicorp.com/gpg | \
    gpg --dearmor | \
    sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg
```
> Lalu, kita verify GPG Key tersebut.
```
gpg --no-default-keyring \
    --keyring /usr/share/keyrings/hashicorp-archive-keyring.gpg \
    --fingerprint
```

3. Tambahkan library repository HashiCorp
```
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
    https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
    sudo tee /etc/apt/sources.list.d/hashicorp.list
```
> Jalankan `sudo apt update` untuk mengupdate library tersebut.

4. Install melalui `apt`
```
sudo apt install terraform
```

Jika sudah, kita bisa memeriksa apakah instalasi _Terraform_ sudah benar atau belum melalui :
```
terraform version
```
<img alt="Logo Gitlab" src={useBaseUrl('img/docs/t2.png')} />

Sebelum kita bisa menggunakan _Terraform_, kita harus menentukan :
- Provider/Tool yang digunakan (AWS, IDCH atau Docker)
- Konfigurasi server
  - AWS : ami, Access Key, Secret Key
  - IDCH : Billing ID, API Key
