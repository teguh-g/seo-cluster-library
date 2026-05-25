# SEO Cluster Library — Panduan Setup (BUAT ORANG LAIN YANG MAU MAKE)

Tool buat ngatur keyword cluster (peta keyword, funnel BOFU/MOFU/TOFU, internal link, tracking GSC, dll). Dibuat oleh **Teguh Gunawan, S.Li.**

Ini file HTML tunggal — tinggal buka di browser, langsung jalan. **Ga perlu install apa-apa.**

---

## 1. Cara Buka (wajib)

1. Simpan file `seo-cluster-library.html` di komputer kamu.
2. **Double-click** file-nya → kebuka di browser (Chrome/Edge/Firefox).
3. Selesai. Tool langsung bisa dipakai.

Data otomatis tersimpan di browser kamu (localStorage). Selama kamu pakai browser & device yang sama, data aman.

> ⚠️ **Penting:** Karena data nyimpen di browser, kalau kamu clear browsing data / cache, datanya bisa kehapus. Biar aman, lakukan salah satu:
> - Rutin klik **Export** (header) buat backup file JSON, **atau**
> - Setup **Cloud Sync** (lihat bagian 3) biar data tersimpan online & bisa diakses dari device lain.

---

## 2. Fitur AI (opsional — tapi recommended)

Fitur AI (auto-mapping keyword, expand keyword, saran internal link) pakai **Google Gemini**. Gratis, tapi kamu butuh **API key sendiri**.

### Cara dapat API key Gemini (gratis):

1. Buka **https://aistudio.google.com/apikey**
2. Login pakai akun Google kamu.
3. Klik **Create API Key** → copy key-nya (formatnya `AIza...`).

### Cara pasang di tool:

1. Klik tulisan **"AI: off"** di header (pojok kanan atas).
2. Pilih model (biarkan default **Gemini 2.5 Flash** kalau bingung).
3. Di bagian **Saved API Keys**, isi nama (mis. "Akun Saya") + paste API key → klik **"+ Simpan key ini ke daftar"**.
4. Klik **Save**.
5. Kalau berhasil, status di header berubah jadi **"AI: 0/20"** (artinya AI aktif).

> 💡 Free tier Gemini = **20 request per hari per API key**. Cukup buat pemakaian normal. Kalau habis, tunggu besok atau pakai API key lain.

> 🔒 API key disimpan di browser kamu aja, ga dikirim ke mana-mana selain ke Google. **Jangan share API key kamu ke orang lain.**

---

## 3. Cloud Sync via GitHub Gist (opsional)

Fitur ini buat **sync data antar device** (mis. laptop ↔ HP) atau backup online. Kalau kamu cuma pakai 1 device, ini ga wajib — skip aja.

**Setiap orang HARUS punya Gist & token sendiri.** Jangan pakai punya orang lain (datanya bakal saling timpa + ga aman). Ikutin langkah di bawah pakai akun GitHub kamu sendiri.

### Langkah A — Buat GitHub Token

1. Buka link ini (scope `gist` udah otomatis kecentang):
   **https://github.com/settings/tokens/new?scopes=gist&description=SEO%20Cluster%20Library**
2. Login GitHub kamu.
3. Atur **Expiration** (mis. 90 hari, atau "No expiration" kalau males ganti).
4. Pastikan scope **`gist`** tercentang (cuma itu yang dibutuhin).
5. Scroll bawah → klik **Generate token**.
6. **Copy token-nya SEKARANG** (formatnya `ghp_...`). Token cuma muncul sekali — kalau ke-close, harus generate ulang.

### Langkah B — Buat Gist Kosong

1. Buka **https://gist.github.com/**
2. Isi:
   - **Filename:** `seo-cluster-library.json`
   - **Content:** ketik dua karakter ini → `[]`
3. Klik tombol **"Create secret gist"** (yang secret, bukan public).
4. Lihat URL di address bar, contohnya:
   `https://gist.github.com/username/`**`a1b2c3d4e5f6...`**
   Bagian setelah username itu **Gist ID** kamu. Copy.

### Langkah C — Pasang di Tool

1. Di tool, klik **icon gear** (⚙️) di header.
2. Paste **token** ke field "GitHub Personal Access Token".
3. Paste **Gist ID** ke field "Gist ID".
4. (Opsional) Centang "Auto-push setiap save" biar otomatis backup.
5. Klik **Save Config**.
6. Test: klik **Push** (simpan ke cloud) → harusnya muncul "Pushed to cloud!".

### Cara pakai sehari-hari:

- **Push** = upload data dari browser ke cloud (backup / sebelum pindah device).
- **Pull** = download data dari cloud ke browser (pas di device baru / mau ambil versi terbaru).

> ⚠️ **Pull akan menimpa data lokal** dengan data cloud. Jadi pastikan kamu Push dulu dari device yang punya data terbaru, baru Pull di device lain.

---

## 4. Pertanyaan Umum

**Q: Datanya ilang kalau ganti komputer?**
Iya, kalau ga pakai Cloud Sync. Solusi: Export JSON (backup manual) atau setup Gist sync.

**Q: Harus online?**
Tool jalan offline. Yang butuh online cuma: fitur AI (ke Google), Cloud Sync (ke GitHub), dan GSC import.

**Q: Aman ga datanya?**
Data ada di browser kamu sendiri. Token & API key juga disimpan lokal. Ga ada server pihak ketiga yang nyimpen data kamu (kecuali Gist kamu sendiri kalau pakai sync).

**Q: Token GitHub-ku expired, gimana?**
Generate token baru (Langkah A), paste ulang di settings (gear icon). Gist ID biarkan sama — datanya aman, cuma "kunci"-nya yang diganti.

**Q: Bisa buka Panduan Fitur di dalam tool?**
Bisa. Klik tombol **Help** di header, atau tekan tombol **`?`** di keyboard.

---

## Ringkasan Cepat

| Mau apa | Yang dibutuhin |
|---|---|
| Cuma coba tool | Buka file aja, langsung jalan |
| Pakai fitur AI | API key Gemini gratis (aistudio.google.com) |
| Sync antar device | Gist + token GitHub sendiri |

Selamat pakai! Kalau bingung, buka **Help** (tombol `?`) di dalam tool. 🚀
