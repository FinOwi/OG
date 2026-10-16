# OGKasir Admin

Panel admin OGKasir — dashboard lisensi + generator kode aktivasi.
Live di **https://admin.ogkasir.my.id** (GitHub Pages, repo publik ini).

## Cara kerja (keamanan)

- Website ini **tidak menyimpan rahasia apa pun**. Yang ada cuma Supabase URL +
  anon key (publik by design, sama seperti yang tertanam di APK).
- Kode aktivasi dihitung di **server Supabase** lewat fungsi `SECURITY DEFINER`
  (`supabase-admin.sql`, disimpan privat, JANGAN masuk repo ini).
- Hanya email yang terdaftar di tabel `admins` yang bisa login & generate.

## Setup awal (sekali saja)

1. **Supabase** — buka SQL Editor
   https://supabase.com/dashboard/project/ypdfdaxgqgkaupsyiauy/sql ,
   paste seluruh isi `supabase-admin.sql`, Run.
2. **Buat akun admin** — Supabase dashboard → Authentication → Add user →
   `admin.ogkasir@gmail.com` + password (akun baru hanya bisa dibuat dari dashboard).
3. **GitHub Pages** — repo Settings → Pages → Deploy from branch → `main` / root.
4. **DNS** — di IDwebhost tambah CNAME: `admin` → `finowi.github.io`.

## File

- `index.html` — seluruh aplikasi (login, dashboard, generator, riwayat, verifikasi)
- `CNAME` — custom domain `admin.ogkasir.my.id`
