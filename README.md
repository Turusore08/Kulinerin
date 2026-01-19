**Project Name: Project "Kulinerin"**

**Owner: [Nama Anda] - AI Engineer Lead**

**Date: January 19, 2026**

**Status: Ongoing Phase**


1. Executive Summary
Aplikasi berbasis web (PWA) yang mengubah pengalaman wisata kuliner menjadi permainan "Quest" dunia nyata. Memanfaatkan teknologi AI (Edge Computing) untuk verifikasi kunjungan yang murah dan skalabel, serta memecahkan masalah decision fatigue pada turis Gen Z.

Core Philosophy: Low Friction, High Reward, Zero Server-Side AI Cost.

2. Phasing Strategy (Tahapan Pengerjaan)
Jangan kerjakan semuanya sekaligus. Fokus pada milestone berikut:

FASE 1: "The Wizard of Oz" MVP (Validasi Pasar)
Tujuan: Membuktikan ada user yang mau mengikuti "Quest" kuliner tanpa membangun aplikasi canggih. Durasi: 2 - 3 Minggu.

Tasks:

[ ] Curated Content Creation: Riset dan buat 1 skenario Quest manual (Contoh: "5 Mie Ayam Hidden Gem Jogja").

[ ] Landing Page Sederhana: Buat satu halaman web (bisa pakai Carrd/Wix) yang berisi list toko tersebut.

[ ] Manual Verification Mechanism: User diminta upload foto ke Google Form atau kirim via WhatsApp Admin.

[ ] Reward Manual: Kirim desain sertifikat digital/stiker e-wallet (Rp 5.000) bagi yang menyelesaikan manual.

Definition of Done (DoD):

Minimal 20 user menyelesaikan quest.

Mendapatkan feedback kualitatif: Apakah mereka merasa tertantang? Apakah hadiahnya sepadan?

FASE 2: The Skeleton PWA (Pondasi Teknis)
Tujuan: Membangun infrastruktur aplikasi tanpa fitur AI (masih "dumb system"). Fokus pada UX dan Database. Durasi: 4 Minggu.

Tasks:

[ ] Frontend Development (PWA):

Setup Project (React/Next.js/Vue).

Fitur: Login (Google Auth), List Quest, Detail Quest.

Fitur: Camera Capture Interface (Akses kamera via browser).

[ ] Backend & Database:

Setup Database (Firebase/Supabase) untuk User Data & Transaction Logs.

Schema Design: Users, Quests, Merchants, User_Logs.

[ ] Basic Validation:

Implementasi Geolocation Check (GPS radius 100m dari toko).

Implementasi Metadata/EXIF Check sederhana (Tanggal foto).

Definition of Done (DoD):

User bisa login, memilih quest, dan upload foto (foto tersimpan di storage).

Sistem menolak upload jika GPS user jauh dari lokasi target.

FASE 3: The AI Brain Integration (Fitur Utama)
Tujuan: Mengganti validasi manual/GPS dengan AI Verification yang berjalan di sisi Client (Edge AI). Durasi: 4 - 6 Minggu.

Tasks:

[ ] Data Collection: Kumpulkan 100-200 sampel foto struk dan foto depan toko (dari Fase 1 & 2).

[ ] AI Model Training (Lite):

Latih model klasifikasi ringan (MobileNetV3 atau sejenis) atau Fine-tune OCR (PaddleOCR).

Tujuan: Mendeteksi teks nama toko atau mendeteksi pola visual struk valid.

[ ] Model Conversion:

Konversi model ke TensorFlow.js atau TFLite agar bisa jalan di browser/HP.

[ ] Client-Side Integration:

Inject model ke dalam kode Frontend PWA.

Buat logic: Image Capture -> Local Inference -> Output (Valid/Invalid) -> Send Result Hash to Server.

Definition of Done (DoD):

Aplikasi mampu memvalidasi foto struk secara offline (tanpa internet kencang) dalam waktu < 3 detik di HP mid-range.

Biaya server tetap rendah meskipun ada 1000 upload foto.

FASE 4: Gamification & Monetization (Bisnis)
Tujuan: Meningkatkan retensi user dan mulai menghasilkan uang. Durasi: 3 - 4 Minggu.

Tasks:

[ ] XP & Leveling System:

Desain logika XP (1 Quest = 100 XP).

Desain Visual Badge (Bronze, Silver, Gold).

[ ] Merchant Dashboard (Sederhana):

Halaman khusus pemilik toko untuk melihat jumlah kunjungan terverifikasi.

(Opsional) Fitur generate invoice sederhana berdasarkan jumlah "Lead".

[ ] Fraud Protection Layer:

Tambahkan logic untuk mendeteksi upload foto duplikat (Hashing).

Definition of Done (DoD):

User memiliki profil dengan Level dan Badge.

Sistem bisa mengeluarkan laporan: "Toko A mendapat 50 kunjungan bulan ini".

3. Technology Stack Recommendation
Agar pengembangan cepat dan cost-efficient:

Frontend: Next.js (Support PWA native & SEO bagus).

Backend/DB: Supabase (PostgreSQL + Auth + Storage). Tier gratisnya sangat lega.

AI/ML: Python (Training di Colab), TensorFlow.js (Deployment di Web).

Hosting: Vercel (Frontend), Supabase (Backend).

4. Key Metrics (KPIs)
Jangan tersesat dalam data yang salah. Pantau ini:

Completion Rate: Berapa % user yang memulai Quest dan menyelesaikannya sampai akhir? (Indikator keseruan).

Cost Per Verification: Target < Rp 10 (Sangat mungkin tercapai dengan Edge AI).

Merchant Acquisition: Jumlah toko yang bersedia dicantumkan dalam Quest.
