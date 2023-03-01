---
sidebar_position: 1
slug: /gitlab
---

# 1. Introduction

import useBaseUrl from '@docusaurus/useBaseUrl';

## 1.1. Study Case Overview

Di beberapa perusahaan, memiliki sebuah project yang mudah diatur dari 1 dashboard ditambah dengan kolaborasi antar team yang sudah terintegrasi didalam dashboardnya menjadi kunci untuk memperkuat produktifitas dan efisiensi dalam kerjasama. Sehingga GitlabCI lebih sering digunakan oleh perusahaan atau team yang memfokuskan kolaborasi antar team.

Disini, kalian akan membuat sebuah integrasi untuk sebuah project didalam GitlabCI, dengan hasil sebagai berikut :

<img alt="image1" src={useBaseUrl('img/docs/4.png')} />

## 1.2. Kenapa GitlabCI?

Disini, kita akan mempelajari menggunakan GitlabCI agar kita dapat memahami cara untuk :
- Manage sebuah project didalam 1 _Source Code Management_ (SCM)
- Membuat dan menjalankan integrasi menggunakan pipeline dari _GitlabCI_
- Membuat dan menjalankan sebuah project beserta kebutuhan dan fitur-fitur didalam GitlabCI

## 1.3. Pengertian GitlabCI

<img alt="Logo Gitlab" src={useBaseUrl('img/docs/gitlab-logo.png')} />

**GitlabCI** (*atau Gitlab*) merupakan salah satu tool yang kita gunakan untuk *Continuous Integration*, berbeda dengan Jenkins, Gitlab dapat digunakan melalui 2 cara, yaitu *Self-managed install* dan sebagai *Software-as-a-service* (SaaS).

Gitlab dikenal karena semua toolnya yang bisa digunakan di 1 tempat, mulai dari Version Control sampai Code Collaboration sehingga membuat GitlabCI menjadi pilihan untuk perusahaan yang menginginkan project management di 1 tempat (All-in-one).

## 1.4. Gitlab vs Jenkins

Berikut perbandingan antara Jenkins dan GitlabCI :

| Gitlab SaaS | Jenkins |
|----------|---------|
| CI/CD tanpa instalasi | Self-managed install |
| All-in-one SCM (deployments, pipeline etc) | Plugin yang beragam & multi-fungsi |
| Gitlab menyediakan host untuk CI/CD | Host/Server dari pengguna |
| yaml based | Jenkins/Groovy |
| Free Tier | Open Source |

