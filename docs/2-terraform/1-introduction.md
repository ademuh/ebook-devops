---
sidebar_position: 1
slug: /terraform
---

# 1. Introduction

import useBaseUrl from '@docusaurus/useBaseUrl';

## 1.1. Study Case Overview

Sebagai _DevOps Engineer_, kita harus bisa "Berkerja semalas mungkin".

_Jangan salah paham ya._

Memiliki sebuah alat/tool untuk mempercepat tugas kita akan menjadi kunci utama dalam efisiensi pekerjaan. Bayangkan kalau kalian harus membuat 100 server dalam semalam atau mengkonfigurasi 100 server tersebut agar bisa menggunakan _Docker_. Tentu hal ini akan memakan waktu yang cukup banyak jika kita lakukan secara manual, sehingga proses _Automation_ disini akan berperan sangat penting untuk kita sebagai _DevOps Engineer_.

Kita akan mempelajari bagaimana cara membuat sebuah infrastruktur dengan membuatnya sebagai code, atau biasa disebut _Infrastructure as Code_ (IaC). Salah satu toolnya adalah **Terraform**.

<img alt="Logo Gitlab" src={useBaseUrl('img/docs/t1.png')} />

## 1.2. Kenapa Terraform?

Disini, kita akan mempelajari menggunakan **Terraform** agar kita dapat memahami cara untuk :
- Mempelajari konsep _Provisioning Tool_ & IaC
- Membuat dan menjalankan banyak Virtual Machine dalam 1 code/script
- Mempercepat proses persiapan infrastruktur dengan _Terraform_

## 1.3. Pengertian Terraform

<img alt="Logo Gitlab" src={useBaseUrl('img/docs/terraform-logo.png')} />

**Terraform** adalah sebuah tool _Automation_ yang digunakan untuk membuat dan menyusun infrastruktur dari awal, atau dikenal dengan istilah _Provisioning Tool_ yang artinya alat untuk penyediaan.

Di manage oleh HashiCorp, Terraform merupakan tool yang cukup sering digunakan pada saat kita ingin membuat server atau menyusun sebuah infrastruktur namun hanya menggunakan sebuah source code yang berisi spesifikasi hingga network dari server tersebut.

## 1.4. Terraform & Fitur-fiturnya

- Terraform Cloud : _Software-as-a-Service_ dari terraform.
- Terraform CLI : _Terraform_ melalui device sendiri (Local).
- Terraform Registry : Isinya merupakan berbagai macam plugin/fitur yang bisa digunakan _Terraform_, mulai dari _Cloud Provider_ hingga _Kubernetes_. 
- Terraform Enterprise : _Self-manage install_ yang ditargetkan ke perusahaan-perusahaan.