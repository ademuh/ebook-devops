---
sidebar_position: 4
---

# Task

import useBaseUrl from '@docusaurus/useBaseUrl';

## Instruksi

Setelah mempelajari setup GitlabCI dari awal, tugas kalian adalah :
- Membuat sebuah Project baru di GitlabCI beserta Setup yang dibutuhkan
- Merancang pipeline dengan step-step sebagai berikut :
  - Dockerize project kita menjadi sebuah image
  - Push image ke `hub.docker.com` menggunakan akun masing-masing
  - Deploy aplikasi ke _Appserver_
- Menggunakan _Variable_ :
  - Nama image docker
  - User dan password untuk Docker Hub
  - IP Server tujuan
- Membuat sebuah _Schedule_ untuk menjalankan pipeline setiap pukul 12:00 WIB atau 24 jam sekali

## Pengumpulan

Jika teman-teman sudah menyelesaikan tugasnya, maka langkah selanjutnya adalah :
- Membuat dokumentasi dan step-by-step guide pengerjaan tugas
- Membuat _directory_ dengan nama "GitlabCI" di dalam repository tugas kalian
- Mempresentasikan hasil tugas pada jadwal yang tertera di Dashboard LMS (_Review & Scoring_)

## Project Management

Tambahkan deskripsi berikut ke dalam kanban pada project management Anda

```text
Membuat sebuah Source Code Management di GitlabCI dengan pipeline dan fitur-fitur yang sudah disediakan.

- [ ] Setup : Gitlab Account
- [ ] Setup : SSH Keys, Variable & Repository
- [ ] Setup : Pipeline
- [ ] Deploy : Aplikasi Web
- [ ] Dokumentasi
```

Referensi:

- [Creating Github Project](https://dumbways-ebook.netlify.app/getting-started/project-management/membuat-project-managament)
- [Managing Github Issue](https://dumbways-ebook.netlify.app/getting-started/project-management/issue-dan-status-project)

