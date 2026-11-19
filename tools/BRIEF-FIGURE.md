# Brief bersama: figure Colorfigures untuk web IPA Kelas 7 (Kurikulum Merdeka)

Kamu membangun SATU figure interaktif Colorfigures untuk satu bab IPA SMP kelas 7. Pembaca: siswa 12–13 tahun,
banyak memakai HP. Figure akan ditanam di halaman materi lewat `<iframe>` (desktop ±900×720, HP 390 lebar).

## Wajib dibaca dulu
1. `/Users/users/.claude/skills/colorfigures/SKILL.md` — ikuti seluruh aturannya (Truth first, painter's order, see-through, verify).
2. `/Users/users/Documents/Project/interaktifmateri/tools/core.js` — engine (sudah diterjemahkan ke Bahasa Indonesia; JANGAN diubah).
3. Contoh: `/Users/users/.claude/skills/colorfigures/assets/examples/toaster.html` (paling kecil), lalu `lamp.html` bila figure di atas meja/board.

## Lokasi file (hanya sentuh folder milikmu)
- Kerja: `/Users/users/Documents/Project/interaktifmateri/figures/<id>/<id>.html`; salin `tools/core.js` ke folder itu.
- Build: `python3 /Users/users/Documents/Project/interaktifmateri/tools/build.py figures/<id>/<id>.html fig/<id>.html`
  (jalankan dari `/Users/users/Documents/Project/interaktifmateri`). Hasil akhir = `fig/<id>.html`.
- Screenshot verifikasi: simpan di `figures/<id>/shots/` (jangan di tempat lain).
- Jangan ubah `tools/`, `index.html`, atau folder figure lain.

## Bahasa dan isi
- Semua teks yang terlihat siswa dalam Bahasa Indonesia baku dengan ejaan benar: `title`, tombol, pilihan picker,
  `ui.flash(...)`, label (`tag`/`xrCallouts`, HURUF KAPITAL, pendek), `stats` (label pendek, nilai dengan satuan),
  `readout`. Desimal pakai koma (`23,5°`, `0,47 m/s`). Hanya huruf/angka biasa (tanpa emoji/simbol aneh; `°` dan `×` boleh).
- `fig:` = nomor bab (mis. `'4'`), `title:` = nama objek (mis. `'Mobil di lintasan'`).
- Sains HARUS benar. Setiap angka di `stats` dihitung dari model fisika/biologi sederhana yang ditulis di kode
  (komentar di atas skrip: langkah kerja nyata + daftar bagian). Bila sesuatu diperbesar/disederhanakan demi terlihat,
  beri tahu lewat `ui.flash` sekali saat relevan (mis. "Ilustrasi: pemuaian diperbesar agar terlihat"), angka di stats tetap nyata.
- Tombol 3–6, urut sesuai langkah percobaan nyata. Tekan tidak berurutan → lakukan hal masuk akal atau `ui.flash` penjelasan.
- Beri `ui.flash` edukatif singkat pada momen penting (mis. "Air mendidih pada 100 °C (tekanan 1 atm)") — satu kalimat, ≤ 90 karakter.
- `params(st, q)` untuk setiap state menarik agar bisa di-screenshot.
- Beri see-through (`xrMount`) bila objek punya bagian dalam yang bekerja; label bagian penting.

## Selesai bila
- Lolos langkah Verify di SKILL.md (semua sudut, `?press=` urutan utama, close-up see-through, shot HP 390×844,
  `data-errors` kosong, tanpa `NaN`). Maksimal 3 putaran perbaikan. Lalu `turn:'full'`.
- Chrome: `/Applications/Google Chrome.app/Contents/MacOS/Google Chrome`. `--user-data-dir` pakai folder sementara baru di `figures/<id>/shots/`.

## Laporan akhir (≤ 250 kata)
Path hasil, daftar tombol + apa yang terjadi, parameter URL, model/angka sains yang dipakai, hal yang sudah diverifikasi,
dan masalah yang tersisa (jujur). Jangan memulai agen lain.
