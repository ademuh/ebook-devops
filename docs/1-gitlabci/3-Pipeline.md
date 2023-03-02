---
sidebar_position: 3
---

# 3. Pipeline

import useBaseUrl from '@docusaurus/useBaseUrl';

## 3.1. Introduction to Pipeline in GitlabCI

Secara otomatis, pipeline di Gitlab akan berjalan jika ada update atau perubahan didalam repository. Sehingga jika kita sudah membuat file `.gitlab-ci.yml` maka pipeline akan berjalan langsung.

Disini, kita bisa akses dashboard pipeline melalui :
```
CI/CD > Pipelines
```
Akan terdapat tampilan yang menunjukan proses pipeline sampai console log yang nantinya bisa kita akses untuk memeriksa error atau kegagalan dalam pipeline.

<img alt="image1" src={useBaseUrl('img/docs/14.png')} />

Jika kita ingin akses log/proses hasil pipeline, kita bisa akses dengan klik pipeline IDnya (`#79xxxxxx`).

<img alt="image1" src={useBaseUrl('img/docs/15.png')} />

Kita juga dapat membuat jadwal kapan pipeline kita berjalan menggunakan _cronjob_, yang bisa kita konfigurasi di :
```
CI/CD > Schedules
```
<img alt="image1" src={useBaseUrl('img/docs/17.png')} />

## 3.2 Using Docker

Untuk menggunakan fitur-fitur docker, kita harus memastikan kalau kita menggunakan _image_ dan _service_ untuk docker, jadi di dalam file `.gitlab-ci.yml` bisa kita tambahkan :
```
...

docker:test:
  stage: build
  image: docker:1.11 # Image Docker yang digunakan GitlabCI
  services:
    - docker:dind # Service docker in docker
  script:
    - export DOCKER_HOST=tcp://docker:2375/ # Mengarahkan socket docker ke port 2375
    - docker version # Memunculkan versi docker didalam console log

...
```

Jika kita menjalankan pipeline, maka akan keluar output seperti ini :

<img alt="image1" src={useBaseUrl('img/docs/16.png')} />

Pada dasarnya, semua _command_ yang biasa kita gunakan saat kita menggunakan _docker_ dapat digunakan didalam pipeline, cukup menambahkan _command_ sesuai kebutuhan didalam fase _script_ atau _before\_script_

Menggunakan _Variable_, kita bisa membuat script pipeline yang lebih rapih dengan menaruh nama image Docker & password Docker Hub. Sehingga variabel-variabel yang kita panggil cukup kita call menggunakan `$NAMA_VARIABLE`

**Before :**

```
...

docker:test:
  stage: build
  image: docker:1.11 # Image Docker yang digunakan GitlabCI
  services:
    - docker:dind # Service docker in docker
  script:
    - export DOCKER_HOST=tcp://docker:2375/ # Mengarahkan socket docker ke port 2375
    - docker version # Memunculkan versi docker didalam console log
    - docker build -t user/dumbflix-frontend:latest .

...
```

**After :**
```
...

docker:test:
  stage: build
  image: docker:1.11 # Image Docker yang digunakan GitlabCI
  services:
    - docker:dind # Service docker in docker
  script:
    - export DOCKER_HOST=tcp://docker:2375/ # Mengarahkan socket docker ke port 2375
    - docker version # Memunculkan versi docker didalam console log
    - docker build -t $NAMA_IMAGE .

...
```
:::note
Reference : https://docs.gitlab.com/ee/ci/docker/using_docker_images.html
:::