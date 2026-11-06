# AI YouTube Automation Studio — YouTube Link Import

- Tempel URL YouTube biasa, youtu.be, Shorts, embed, atau live.
- YouTube Data API v3 API key dipakai membaca metadata publik (judul, deskripsi, channel, kategori).
- Gemini membuat metadata SEO dari informasi publik tersebut.
- Untuk mengunggah video ke channel, tetap pilih file video asli dari perangkat. YouTube Data API tidak menyediakan endpoint resmi untuk mengunduh MP4 video publik hanya dari URL.

## Setup YouTube API key
1. Buka Google Cloud Console dan pilih project.
2. Aktifkan YouTube Data API v3.
3. Buat API key di APIs & Services → Credentials.
4. Batasi key ke YouTube Data API v3 dan domain GitHub Pages bila memungkinkan.
5. Masukkan key ke kolom YouTube Data API Key.

Catatan: video private, dihapus, atau dibatasi mungkin tidak bisa diambil. Link MP4 langsung tetap membutuhkan izin CORS. Jangan unggah ulang konten orang lain tanpa izin.
