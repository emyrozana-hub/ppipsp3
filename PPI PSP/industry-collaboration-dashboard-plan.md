# Industry Collaboration Dashboard — Plan
**Politeknik Seberang Perai (PSP) | CISEC & Pengurusan**

## Overview

Bina satu fail HTML interaktif lengkap (`industry-dashboard.html`) yang memaparkan Industry Collaboration Dashboard untuk Politeknik Seberang Perai. Dashboard ini menggunakan dummy data sebenar berkaitan kolaborasi industri PSP, Chart.js untuk carta, dan CSS/JS vanilla tanpa framework — boleh dibuka terus dalam mana-mana browser tanpa server.

**Skop:** Satu fail HTML sahaja, boleh dibuka terus (double-click), boleh edit data dalam fail.
**Stack:** HTML + CSS vanilla + JavaScript + Chart.js (CDN) — sama seperti `dashboard.html` sedia ada.
**Warna Tema:** Biru navy PSP (`#1e3a5f`) dengan aksen warna per-modul.
**Bahasa:** Dwibahasa — label utama dalam Bahasa Malaysia, sub-label/tooltip dalam English.

---

## Sub-Task 1 — Struktur Asas & Header

**Intent:** Sediakan rangka HTML, CSS asas, header PSP, dan tab navigasi untuk 5 modul.

**Expected Outcomes:**
- Fail `industry-dashboard.html` wujud
- Header PSP dengan logo dan tajuk dashboard
- 5 tab navigasi: KPI Ringkasan | Syarikat & MoU | Penempatan Pelajar | Projek Kolaborasi | Laporan Trend
- Responsive pada mobile dan desktop

**Todo List:**
- [ ] Buat fail `industry-dashboard.html`
- [ ] Tambah `<head>` dengan Chart.js CDN dan meta tags
- [ ] Bina CSS: reset, body, header, tab navigation, page wrapper
- [ ] Bina HTML header dengan logo PSP dan subtitle
- [ ] Bina tab bar dengan 5 tab, JavaScript toggle tab aktif
- [ ] Tambah placeholder `<div>` untuk setiap tab content

**Relevant Context:**
- Ikut corak CSS dari `dashboard.html` (warna, border-radius, font)
- Header colour: `#1e3a5f` (biru navy PSP)
- Tab aktif highlight dengan border-bottom berwarna

**Status:** [ ] pending

---

## Sub-Task 2 — Tab 1: KPI Ringkasan

**Intent:** Papar 5 kad KPI utama dan 2 carta ringkasan (donut + bar trend tahunan).

**Expected Outcomes:**
- 5 KPI card: Jumlah MoU Aktif, Jumlah Syarikat, Pelajar LI Semasa, Projek Aktif, Ceramah Industri
- Carta donut: pecahan status MoU (Aktif / Tamat / Dalam Proses)
- Carta bar: trend KPI tahunan 2022–2026

**Todo List:**
- [ ] Tambah CSS untuk kpi-grid (5 kolum) dan kpi-card dengan warna border berbeza
- [ ] Bina 5 KPI card dengan data dari KPI_TAHUNAN[2026]
- [ ] Bina carta donut status MoU menggunakan Chart.js
- [ ] Bina carta bar trend tahunan (5 tahun) menggunakan Chart.js
- [ ] Wire up JavaScript untuk render kedua-dua carta semasa tab diaktifkan

**Relevant Context:**
- Data KPI dari Sheet 5 dalam dummy data: tahun 2022–2026
- Warna KPI: MoU=biru, Syarikat=ungu, Pelajar=hijau, Projek=oren, Ceramah=merah jambu
- Carta hanya render bila tab menjadi aktif (elak canvas error)

**Status:** [ ] pending

---

## Sub-Task 3 — Tab 2: Syarikat & MoU

**Intent:** Papar jadual syarikat rakan industri dan rekod MoU dengan penapis status.

**Expected Outcomes:**
- Filter dropdown: Status MoU (Semua / Aktif / Tamat / Dalam Proses) dan Sektor
- Jadual Syarikat: Nama, Sektor, Status MoU, Penyelaras PSP
- Jadual MoU: No. MoU, Syarikat, Tarikh Tandatangan, Tarikh Tamat, Skop, Status dengan badge warna
- Badge warna: Aktif=hijau, Tamat=merah, Dalam Proses=kuning

**Todo List:**
- [ ] Tambah data array SYARIKAT (10 rekod) dan MOU (10 rekod) dari dummy data PSP
- [ ] Bina filter bar dengan 2 dropdown
- [ ] Bina jadual Syarikat dengan badge status
- [ ] Bina jadual MoU dengan badge status berwarna
- [ ] Fungsi JavaScript: filterMoU() dan renderMoUTable()

**Relevant Context:**
- Gunakan data syarikat dan MoU dari dummy data PSP (Intel, Bosch, PSDC, dll.)
- Badge CSS sama seperti `.badge` dalam `dashboard.html`

**Status:** [ ] pending

---

## Sub-Task 4 — Tab 3: Penempatan Pelajar

**Intent:** Papar senarai pelajar LI/praktikal dengan status penempatan dan penapis program/syarikat.

**Expected Outcomes:**
- Filter: Program (Semua / DKE / DTM / DKS / DKA) dan Status (Semua / Sedang Berjalan / Selesai)
- Jadual: ID Pelajar, Nama, Program, Syarikat, Tarikh Mula/Tamat, Status, Pensyarah Penyelia
- KPI mini di atas jadual: Jumlah Pelajar LI, Sedang Berjalan, Selesai

**Todo List:**
- [ ] Tambah data array PELAJAR (8 rekod) dari dummy data PSP
- [ ] Bina KPI mini (3 kad kecil)
- [ ] Bina filter bar 2 dropdown
- [ ] Bina jadual pelajar dengan badge status
- [ ] Fungsi JavaScript: filterPelajar() dan renderPelajarTable()

**Relevant Context:**
- Data pelajar dari Sheet 3 dummy data PSP
- Program: Diploma Kejuruteraan Elektronik, Teknologi Maklumat, Keselamatan Siber, Automotif

**Status:** [ ] pending

---

## Sub-Task 5 — Tab 4: Projek Kolaborasi

**Intent:** Papar senarai projek kolaborasi antara PSP dan industri dengan kategori dan status.

**Expected Outcomes:**
- Filter: Kategori (Semua / FYP & R&D / Latihan / Kurikulum) dan Status (Semua / Sedang Berjalan / Selesai)
- Jadual: Nama Projek, Syarikat, Pensyarah, Bilangan Pelajar, Tarikh Mula, Kategori, Status
- Kad ringkasan: Jumlah Projek, Projek Aktif, Projek Selesai

**Todo List:**
- [ ] Tambah data array PROJEK (6 rekod) dari dummy data PSP
- [ ] Bina 3 kad ringkasan
- [ ] Bina filter bar 2 dropdown
- [ ] Bina jadual projek dengan badge kategori dan status berwarna
- [ ] Fungsi JavaScript: filterProjek() dan renderProjekTable()

**Relevant Context:**
- Data projek dari Sheet 4 dummy data PSP (Bosch, CyberSec Malaysia, Agilent, dll.)

**Status:** [ ] pending

---

## Sub-Task 6 — Tab 5: Laporan Trend

**Intent:** Papar carta-carta analitik trend kolaborasi industri PSP dari 2022–2026.

**Expected Outcomes:**
- Carta garisan (line chart): trend MoU Aktif, Pelajar LI, Projek dari 2022–2026
- Carta bar berkelompok (grouped bar): perbandingan KPI mengikut tahun
- Carta bar mendatar: bilangan pelajar LI mengikut syarikat
- Semua carta interaktif dengan tooltip

**Todo List:**
- [ ] Gunakan data KPI_TAHUNAN (5 tahun) untuk carta trend
- [ ] Bina carta garisan 3 series (MoU, Pelajar, Projek) dengan Chart.js
- [ ] Bina carta bar berkelompok perbandingan tahunan
- [ ] Bina carta bar mendatar bilangan pelajar mengikut syarikat
- [ ] Pastikan semua chart instance dibuang dan dibina semula apabila tab aktif

**Relevant Context:**
- Data dari Sheet 5 KPI_Tahunan
- Carta garisan warna: MoU=biru, Pelajar=hijau, Projek=oren
- Chart.js versi 4.4.0 (CDN) — sama seperti `dashboard.html`

**Status:** [ ] pending

---

## Nota Teknikal

- Semua data dalam JavaScript array dalam fail HTML — senang edit terus
- Gunakan `Chart.destroy()` sebelum render semula untuk elak memory leak
- Tab switching: sembunyikan semua `.tab-content`, paparkan yang aktif sahaja
- Fail siap boleh dibuka dengan double-click (no server required)
- Komen dalam kod menandakan bahagian data supaya mudah diedit kemudian
