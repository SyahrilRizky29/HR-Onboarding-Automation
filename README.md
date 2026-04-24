# HR Onboarding Automation System (n8n)

Sistem ini dirancang untuk mengotomatisasi seluruh alur administrasi HR—mulai dari deteksi data pelamar baru hingga operasional persiapan kerja—menggunakan n8n sebagai engine otomasi utama.

## 🚀 Fitur Utama
- **Real-time Monitoring:** Polling data dari Google Sheets setiap 60 detik untuk respon cepat.
- **Data Normalization:** Transformasi data mentah menjadi format objek yang siap diproses oleh API pihak ketiga.
- **Automated Trello Tasking:** Pembuatan kartu karyawan otomatis lengkap dengan Checklist dinamis.
- **Dynamic HTML Email:** Pengiriman email sambutan yang dipersonalisasi menggunakan ekspresi JavaScript untuk memanggil variabel nama dan posisi.

## 🛠️ Teknologi & API
- **n8n:** Workflow Engine.
- **Google Sheets API:** Sebagai Trigger dan Database Referensi.
- **Trello API:** Untuk Task Management & Onboarding Tracking.
- **Gmail API:** Untuk Automated Notification.
- **JavaScript (Node.js):** Untuk logika penggabungan objek data (Merging).

## 📋 Struktur Workflow
1. **Trigger:** Memantau spreadsheet "Onboarding Karyawan Baru".
2. **Normalization:** Menggunakan node Set untuk standarisasi field (First Name, Email, Start Date).
3. **Tasking:** Node Trello membuat kartu baru berdasarkan profil karyawan.
4. **Data Injection:** Mengambil daftar tugas dari tab "Checklist" dan menyisipkannya ke kartu Trello.
5. **Merging Logic:** Node Code (JavaScript) menggabungkan metadata karyawan dan daftar checklist menjadi satu payload.
6. **Notification:** Node Gmail mengirim email selamat datang dengan format HTML dinamis.
