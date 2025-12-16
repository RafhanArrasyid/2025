# Sistem Pakar Network Troubleshooting - Data Center 🌐🛠️

![Project Banner](studikasus_jaringan-data-center_logikainformatika/assets/content.jpg)

> **Sistem Pakar Deteksi Kesalahan Konfigurasi Jaringan (VLAN & Switching) Menggunakan Metode Forward Chaining.**

Project ini adalah aplikasi web sederhana yang dirancang untuk membantu Network Engineer atau Administrator Jaringan dalam mendiagnosa masalah pada perangkat Switch (khususnya Cisco Environment) di Data Center. Sistem ini memandu pengguna melalui serangkaian pertanyaan gejala untuk menemukan akar masalah dan memberikan solusi perintah CLI yang tepat.

## 📋 Daftar Isi
- [Latar Belakang](#-latar-belakang)
- [Fitur Utama](#-fitur-utama)
- [Metode & Logika](#-metode--logika)
- [Cakupan Diagnosa](#-cakupan-diagnosa)
- [Tim Pengembang](#-tim-pengembang)

## 📝 Latar Belakang
Di lingkungan Data Center modern dengan ribuan port, *human error* dalam konfigurasi sering terjadi. Gejala kerusakan jaringan seringkali ambigu. Aplikasi ini dibuat sebagai studi kasus **Logika Informatika** untuk memangkas waktu *troubleshooting* Layer 2 dari hitungan jam menjadi menit dengan pendekatan sistem pakar berbasis aturan (*rule-based*).

## ✨ Fitur Utama
* **Interactive Diagnosis:** Antarmuka tanya-jawab yang responsif untuk mengerucutkan masalah.
* **Solusi Spesifik (CLI):** Memberikan perintah konfigurasi Cisco IOS (seperti `switchport`, `spanning-tree`, dll) sebagai solusi akhir.
* **Visualisasi Logika:** Menyertakan halaman **Diagram Tree** dan **Implikasi** untuk transparansi alur keputusan sistem.
* **Responsive UI:** Tampilan modern dan bersih yang dapat diakses dari desktop maupun mobile.

## 🧠 Metode & Logika
Sistem ini menggunakan metode **Forward Chaining**, di mana diagnosa dimulai dari sekumpulan fakta (gejala awal) dan bergerak maju melalui aturan IF-THEN menuju kesimpulan (solusi).

Contoh Aturan (diambil dari `implikasi.html`):
* **Rule 1 (Port Security):** IF Port Err-Disabled AND Mac Table Empty THEN Port Security Violation.
* **Rule 2 (Native VLAN):** IF Ping RTO AND Log Error "Mismatch" THEN Native VLAN Mismatch.

## 🔍 Cakupan Diagnosa
Sistem dapat mendeteksi kode masalah berikut (berdasarkan `diagnosa.html`):

| Kode | Masalah | Deskripsi Singkat |
| :--- | :--- | :--- |
| **PG01** | Port Security Violation | Port dimatikan oleh fitur keamanan switch. |
| **PG02** | Native VLAN Mismatch | Konfigurasi Native VLAN berbeda antar trunk. |
| **PG03** | Missing VLAN | VLAN ID belum dibuat di database. |
| **PG04** | VTP Domain Mismatch | Nama domain VTP tidak sinkron dengan server. |
| **PG05** | STP Loop Protection | Port diblokir oleh Spanning Tree Protocol. |
| **PG06** | Trunking Mode Issue | Masalah pada mode access/trunk. |
| **PHY** | Physical Layer | Indikasi kabel putus atau kerusakan hardware. |

## 👥 Tim Pengembang atau Kelompok
Project ini dikembangkan oleh kelompok studi kasus:

* **Rafhan Moch. S. A.** (Ketua)
* Fauzan Reza H.
* Eldo Kelfiyansyah
* Muhammad Rizma J.
* Julianus G. S.
* M. Fadlan Putra S. N.

---
