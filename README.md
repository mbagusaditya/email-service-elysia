# 📧 Scalable Email Microservice

Proyek ini adalah mikroservis pengiriman email transaksional yang dirancang untuk memisahkan beban kerja pengiriman email dari aplikasi utama (Monolitik). Dibangun menggunakan **Bun** dan **ElysiaJS** untuk performa maksimal dan efisiensi resource.

## 🚀 Fitur Utama
- **Asynchronous Processing**: Pengiriman email tidak menghambat alur utama aplikasi (Non-blocking).
- **Reliable Queuing**: Menggunakan Redis & BullMQ untuk antrean pesan yang persisten.
- **RESTful API**: Endpoint sederhana untuk mengirim email dan mengecek status.
- **Admin Dashboard**: Frontend (SvelteKit) untuk memantau log pengiriman secara real-time. (Coming soon)
- **Secure**: Dilindungi dengan API Key untuk komunikasi antar-servis dan JWT untuk akses dashboard.

## 🛠️ Tech Stack
- **Runtime:** [Bun](https://bun.sh/)
- **Backend:** [ElysiaJS](https://elysiajs.com/)
- **Frontend:** [SvelteKit](https://kit.svelte.dev/)
- **Database:** PostgreSQL / MySQL (Drizzle ORM)
- **Queue:** Redis (BullMQ)
- **Email Engine:** Nodemailer

## 🏗️ Arsitektur Sistem
Sistem ini terdiri dari dua bagian utama yang berkomunikasi secara asinkron:
1. **Producer (Elysia API)**: Menerima request dari aplikasi utama dan memasukkannya ke antrean.
2. **Consumer (Worker)**: Memproses antrean dan melakukan pengiriman melalui SMTP/Provider Email.



## 🚦 Endpoint API (Ringkasan)
- `POST /api/v1/send` - Mengirim email (Payload: JSON/HTML).
- `GET /api/v1/status/:id` - Mengecek status pengiriman.
- `GET /api/v1/health` - Cek kesehatan servis.

## 📝 Lisensi
Proyek ini dilisensikan di bawah **MIT License** - lihat file [LICENSE](LICENSE) untuk detailnya.

---
*Dibuat untuk keperluan portofolio pribadi.*
