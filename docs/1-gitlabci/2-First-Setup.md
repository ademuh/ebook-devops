---
sidebar_position: 2
---

# 2. First Setup

import useBaseUrl from '@docusaurus/useBaseUrl';

## 2.1. Gitlab Account

Disini, kita akan menggunakan GitlabCI untuk membuat sebuah pipeline seperti Jenkins, namun disini kita akan berfokus menggunakan produk SaaSnya.

Pertama, kita membuat akun di web Gitlab terlebih dahulu.
```
https://gitlab.com/users/sign_up
```

Lalu, kita bisa akses dashboardnya melalui:
```
https://gitlab.com
```

Sekarang, kita bisa membuat project sesuai dengan kebutuhan kita, disini kita akan membuat sebuah project baru :
```
New Project > Create a Blank Project
```
<img alt="image1" src={useBaseUrl('img/docs/5.png')} />

<img alt="image1" src={useBaseUrl('img/docs/7.png')} />

> Note : Jika kalian ingin menggunakan repository dari Github, bisa memilih **Import Project**

Disini, kita bisa menentukan :
- Nama project
- URL dan Slug Project
- Project Deployment (Pilih _Virtual Machine_)
- Visibility

Jika sudah, maka kita akan mendapatkan tampilan project kita seperti ini.

<img alt="image1" src={useBaseUrl('img/docs/3.png')} />

Dari sini, kita harus setup beberapa kebutuhan kita, seperti :
- SSH Key
- git config & remote
- Variables
- Gitlab Runner (Optional)

## 2.2. Gitlab Settings

### 2.2.1. SSH Key
Sama halnya seperti di Github, kita tinggal menambahkan SSH Key kita kedalam akun Gitlab.
```
User Settings/Preferences > SSH Keys
```
<img alt="image1" src={useBaseUrl('img/docs/8.png')} />


### 2.2.2. Git Config & Remote
Pastikan kita sudah menyesuaikan git config dan remote untuk mengarah ke repository Gitlab.

<img alt="image1" src={useBaseUrl('img/docs/12.png')} />

> Note : samakan dengan lokasi repository kita (Local/Cloud Server)

### 2.2.3. Variables
Password merupakan salah satu hal sensitif untuk dimasukkan kedalam repository atau source code kita, maka kita bisa memanfaatkan fitur Variables yang bisa di akses melalui :
```
Project Settings > CI/CD > Variables
```
<img alt="image1" src={useBaseUrl('img/docs/11.png')} />

Disini, kita bisa menambahkan variabel sesuai dengan kebutuhan.
Ada beberapa bagian didalam sebuah variabel di GitlabCI, antara lain :
- Key : Nama variabel, digunakan untuk memanggil variabel didalam pipeline
- Value : Nilai variabel, isi dari _Key_ berupa _Value_
- Type : Ada 2 pilihan, _Variable_ dan _File_
- Environment Scope : Mengikuti setup dari project, membatasi _Variable_ bisa dipanggil di environment yang ditentukan.

### 2.2.4. Gitlab Runner
Jika kita ingin menggunakan builder dari server kita sendiri (self-host), kita bisa menjalankan Gitlab-runner agar CI/CD berjalan di server kita sendiri.

<img alt="image1" src={useBaseUrl('img/docs/9.png')} />

### Binary Install :
1. Mengambil binary menggunakan curl dan dpkg
```
curl -LJO "https://gitlab-runner-downloads.s3.amazonaws.com/latest/deb/gitlab-runner_${arch}.deb"
```
```
dpkg -i gitlab-runner_<arch>.deb
```

2. Memberikan permission untuk execute
```
sudo chmod +x /usr/local/bin/gitlab-runner
```

3. Membuat user untuk Gitlab-runner
```
sudo useradd --comment 'GitLab Runner' --create-home gitlab-runner --shell /bin/bash
```

4. Install dan jalankan sebagai service
```
sudo gitlab-runner install --user=gitlab-runner --working-directory=/home/gitlab-runner
```
```
sudo gitlab-runner start
```
```
sudo gitlab-runner register
```

### On top Docker :
```
docker volume create gitlab-runner-config
```
```
docker run -d --name gitlab-runner --restart always \
    -p 8093:8093 \
    -v /var/run/docker.sock:/var/run/docker.sock \
    -v gitlab-runner-config:/etc/gitlab-runner \
    gitlab/gitlab-runner:latest
```
```
docker run --rm -it gitlab/gitlab-runner register
```

## 2.3. GitlabCI Pipeline

Setelah melakukan first setup kita sudah memiliki sebuah *repository* Gitlab yang berisi project yang sudah kita buat, dengan fitur-fitur yang bisa kita gunakan, namun kita akan fokus ke fitur :
- Repository
- CI/CD & Pipeline

Disini kita bisa mulai membuat pipeline untuk *Continuous Integration* sehingga kita bisa membuat sebuah integrasi untuk aplikasi yang akan di develop.

Pertama, kita bisa akses :
```
CI/CD > Pipelines
```

<img alt="image1" src={useBaseUrl('img/docs/6.png')} />

Disini, kita bisa menggunakan template yang sudah ada atau membuat file baru. Proses ini akan membuat file `.gitlab-ci.yml` yang berisi pipeline untuk integrasi project.

File tersebut bisa di cek didalam :
```
Repository > Files
```
<img alt="image1" src={useBaseUrl('img/docs/13.png')} />

> Note : Jika kita menggunakan template sesuai dengan stack yang digunakan, maka isi file akan di generate sesuai dengan stacknya

Contoh pipeline template sample GitlabCI :
```
stages:
  - build
  - test
  - deploy

build-job:
  stage: build
  script:
    - echo "Compiling the code..."
    - echo "Compile complete."

unit-test-job:
  stage: test    
  script:
    - echo "Running unit tests... This will take about 60 seconds."
    - sleep 60
    - echo "Code coverage is 90%"

lint-test-job:   
  stage: test    
  script:
    - echo "Linting code... This will take about 10 seconds."
    - sleep 10
    - echo "No lint issues found."

deploy-job:      
  stage: deploy  
  environment: production
  script:
    - echo "Deploying application..."
    - echo "Application successfully deployed."
```


Disini, kita bisa membuat atau merubah struktur dari pipeline sesuai dengan integrasi yang kita inginkan, struktur dari pipeline Gitlab adalah sebagai berikut :
- stages : berisikan phase atau stage yang ingin dijalankan (Bisa diisi sesuai dengan kebutuhan)
- Title (build-job, unit-test-job) : nama atau judul dari pipeline
- stage : nama stage yang dijalankan (berdasarkan _Stages_)
- image : nama image yang digunakan untuk menjalankan pipeline
- services : nama service yang digunakan dari _image_ yang dijalankan
- environment: menentukan enviornment saat ini (ex: Production & Staging)
- before\_script : command yang dijalankan sebelum _script_ dijalankan (Declarative/Pre-pipeline)
- script : command yang dijalankan di fase pipeline

