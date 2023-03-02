---
sidebar_position: 3
---

# 3. Infrastructure-as-Code

import useBaseUrl from '@docusaurus/useBaseUrl';

Setelah kita berhasil setup semua yang dibutuhkan untuk _`Terraform`_, sekarang kita harus memahami konsep *Infrastructure-as-Code*.

**"*Infrastructure-as-Code* artinya segala bentuk infrastruktur (instance, docker atau tools lainnya) akan dibuat, dirancang dan dieksekusi dalam bentuk code."**

Sehingga, kita harus sedikit memhami konsep dari coding itu sendiri namun tidak harus 100% memahami semuanya.
Disini, kita akan mencoba untuk deploy ke AWS (_Terraform_) dan FakeWebServices HCP (_Terraform Cloud_)

## 3.1. Terraform : AWS

Kita akan menggunakan provider AWS dari HashiCorp langsung. Kita akan mencoba mendeploy sebuah server dengan spesifikasi :
- t2.micro (Free Tier)
- Ubuntu 20.04 (ami-05c8486d62efc5d07)
- CIDR 10.0.0.0/16 (IP Address Private : 10.x.x.x)

> Note : sebelumnya, semua konfigurasi sudah kita dapatkan melalui dashboard AWS, disini kita hanya langsung mendeploy servernya

Sebelum kita mulai mendeploy server, kita harus membuat directory yang nantinya akan diisi konfigurasi terraform kita.
```
mkdir terraform/aws

cd terraform/aws
```

Lalu, disini kita bisa membuat konfigurasi terraform untuk AWS dengan memberikan nama file `main.tf` (sesuai preferensi)

### 3.1.1. Provider AWS

Kita bisa menyusun sesuai dengan kebutuhan yang sudah kita tentukan. namun sebelumnya kita tentukan _provider_ yang kita inginkan, namun sebelumnya kita bisa melihat di dokumentasi _Terraform Registry_ untuk memeriksa command apa saja yang bisa digunakan.

Dokumentasi AWS Terraform :
```
https://registry.terraform.io/providers/hashicorp/aws/latest/docs
```

<img alt="Logo Gitlab" src={useBaseUrl('img/docs/t3.png')} />

**Contoh :**
```
provider "aws" {
    version = "~> 4.0"
    region  = "ap-southeast-1"
    access_key = "zA82Lxxxxxxxx"
    secret_key = "zA82Lxxxxxxxx"
}
```

:::info
- `provider "aws"` : nama provider yang kita gunakan (karena Offical dari HashiCorp, maka cukup nama providernya)
- `version` : versi registry dari provider
- `region` : Dari dokumentasi AWS, sesuai dengan region server yang diinginkan
- `access_key` : Dibuat di Dashboard AWS
- `secret_key` : Dibuat di Dashboard AWS
:::

### 3.1.2. Network & IP Address

Setelah kita menentukan providernya, kita bisa mengisi beberapa _resource_ dimana nanti kita akan sesuaikan dengan providernya.
Untuk AWS, ada 3 resource utama yang harus kita perhatikan :
- aws_vpc
- aws_subnet
- aws_instance

Agar network antar server terbentuk, kita menggunakan `aws_vpc`. Untuk menentukan _IP Address_ setiap server, kita gunakan resource `aws_subnet`.

**Contoh :**
```
resource "aws_vpc" "main" {
  cidr_block = "10.0.0.0/16" 
  tags = {
      Name = "tuts vpc" 
  }
}

resource "aws_subnet" "web" {
    vpc_id = aws_vpc.main.id
    cidr_block = "10.0.0.0/16" 
    tags = {
        Name = "web-subnet"
    }
}
```

:::info
- `cidr_block` : menentukan IP dan network yang ingin digunakan
- `tags` : opsional, untuk menambahkan label di dashboardnya nanti
- `vpc_id` : mengarahkan ke _Virtual Private Connection_ (VPC) yang sudah dibuat (`aws_vpc.main.id`)
:::

### 3.1.3. Instance Server

Setelah kita membuat semua kebutuhan untuk instance, sekarang kita bisa menggunakan resource `aws_instance` untuk membuat sebuah _`Instance EC2`_, seperti :
- CPU, RAM & Spesifikasi server
- Network yang digunakan
- Public IP
- Operating System yang digunakan (Amazon Machine Images)

**Contoh :**
```
resource "aws_instance" "foobar" {
    ami = "ami-05c8486d62efc5d07" 
    instance_type = "t2.micro"
    associate_public_ip_address = true
    subnet_id = aws_subnet.web.id
    tags = { 
        Name = "example"
        foo  = "bar"
    }
}
```

:::info
- `ami` : Amazon Machine Images, kumpulan Operating System yang bisa digunakan untuk AWS EC2
- `instance_type` : tipe instance yang ingin digunakan, diperoleh dari Dashboard AWS EC2
- `associate_public_ip_address` : booelan, untuk memberikan IP public jika di set ke `true`
- `subnet_id` : mengambil dari resource `aws_subnet` yang sudah dibuat (`aws_subnet.web.id`)
:::

Disini, kita sudah berhasil menyusun sebuah code _Terraform_ yang nantinya akan membuat :
- 1 VM t2.micro dengan Ubuntu Server 20.04
- Koneksi VPC dan Subnet untuk Instance EC2
- Bisa diakses melalui IP Public

### 3.1.4. Deployment

Setelah kita membuat code _Terrafrom_, sekarang kita bisa mulai untuk menjalankannya. Setiap kita membuat _Terraform_ baru, kita harus selalu menjalankan command :
```
terraform init
```
> Karena, _provider_ yang kita gunakan belum terinstall di local kita.

<img alt="image" src={useBaseUrl('img/docs/t5.png')} />

Sekarang, cara kita mendeploy code tersebut adalah :

**1. Terraform Validate**
```
terraform validate
```
<img alt="image" src={useBaseUrl('img/docs/t7.png')} />

Pastikan code kita sudah terbentuk dengan baik, kita gunakan `terraform validate` untuk memeriksa apakah konfigruasi sudah sesuai dengan providernya.

**2. Terraform Plan & Apply**
```
terraform plan
```
<img alt="image" src={useBaseUrl('img/docs/t6.png')} />

Command ini kita terapkan untuk memastikan apakah code kita sudah bisa dideploy sesuai dengan rencananya, akan muncul output berupa spesifikasi server dan resource-resourcenya yang digunakan.

```
terraform apply -auto-approve
```
<img alt="image" src={useBaseUrl('img/docs/t8.png')} />

Command ini kita gunakan jika kita sudah ingin mulai menjalankan infrasturktur kita melalui terraform.

**Hasil Instance :**

<img alt="image" src={useBaseUrl('img/docs/t9.png')} />

**3. Terraform Destroy**
```
terraform destroy
```
<img alt="image" src={useBaseUrl('img/docs/t10.png')} />

Command ini kita gunakan jika kita sudah ingin menghapus semua infrasturktur yang sudah kita `terraform apply`.

