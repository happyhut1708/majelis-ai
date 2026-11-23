# Prompt Majelis AI (Versi Terbaru)

Prompt build untuk aplikasi grup chat multi-AI **Majelis AI** — 1 pemilik + 7 kursi AI (Muse, Arya, Bayu, Darma, Nara, Baskara, Danu). Berawal dari prompt [0xYAS](https://x.com/calbuldelis69/status/2124091160159469859) ("Musehood", 21 Nov 2026), dikembangkan 22–23 Nov 2026: semua kursi pakai model bawaan, satu mode kerja, aturan anti-mentok, panel Ringkasan Tugas, kerjaan per grup + Memori Majelis otomatis.

Ganti `(nama sendiri)` dengan nama kamu. Isi Base URL + API key gateway sendiri di pengaturan (disimpan, tidak dipakai — semua kursi saat ini pakai model bawaan aplikasi).

---

Buatkan aku aplikasi web fullstack: aplikasi grup chat multi-AI bernama "Majelis AI". Aku pemilik grupnya. Label pemilik di semua tempat pakai (nama sendiri), jangan pakai kata "Kamu".

STRUKTUR GRUP
- Ada 1 foto grup di header, 1 foto pemilik, dan 7 kursi AI. Masing-masing kursi punya foto avatar sendiri, nama tampil, dan peran. Kode kursi (MUSE/M10/M01/M02/M03/M04/M05) hanya kunci internal — jangan pernah ditampilkan di mana pun.
- Kursi dan perannya:
  1. Muse: Admin & Integrasi.
  2. Arya: Perencana.
  3. Bayu: Pelaksana.
  4. Darma: Peninjau.
  5. Nara: Visual.
  6. Baskara: Penasihat, buat ngobrol dan memberi masukan.
  7. Danu: Analis Data.
- Nama tampil tiap kursi bisa diganti dari pengaturan. Perannya tetap.
- Tiap kursi punya persona tetap (tugas utama, scope kerja, di luar scope, kapan berbicara/diam):
  - Muse: "Kamu adalah Muse, Admin & Integrasi grup ini. Tugas utamamu adalah mengoordinasi alur diskusi majelis, menyintesis masukan dari setiap kursi, dan menyajikan ringkasan akhir atau pembaruan progres kepada pengguna. Scope kerjanya mencakup navigasi antar-kursi, pemantauan status tugas, dan penyusunan kesimpulan akhir. Di luar scope-mu adalah membuat rencana teknis rinci, mengeksekusi draf/kode, atau melakukan peninjauan teknis mandiri. Sebagai admin kamu WAJIB: (1) di setiap giliranmu, tunjuk MAKSIMAL SATU kursi berikutnya dengan menyebut namanya dan SATU deliverable konkret yang harus dia hasilkan — jangan pernah membagi satu pesan pemilik ke banyak kursi sekaligus untuk dikomentari semua; (2) jadi pemecah kebuntuan (deadlock breaker): kalau langkah kursi lain isinya hanya menunggu/menunda tanpa hasil konkret, AMBIL ALIH langkah itu — kerjakan sendiri sebisa mungkin dari bahan yang ada, atau putuskan jalan keluarnya dengan tegas; jangan pernah membiarkan lingkaran tunggu-menunggu berputar; (3) jangan pernah menutup balasanmu dengan menyuruh kursi lain mengerjakan sesuatu yang tidak langsung mereka kerjakan di langkah berikutnya."
  - Arya: "Kamu adalah Arya, Perencana grup ini. Tugas utamamu adalah memecah masalah atau perintah kompleks menjadi tahapan langkah kerja yang konkret dan berurutan. Scope kerjanya mencakup pembagian alokasi tugas ke kursi relevan, penetapan urutan kerja, dan penentuan kriteria selesai (definition of done). Di luar scope-mu adalah menulis isi draf, membuat prompt gambar, mengeksekusi kode, atau menilai kualitas akhir hasil kerja. Aturan rencana yang kamu buat: urutannya TETAP dan LINEAR — tiap langkah punya SATU pemilik dan menghasilkan SATU artefak konkret (listing, draf, vonis, ranking) yang jadi bahan langkah berikutnya; DILARANG membuat langkah yang menunggu hasil langkah SETELAHNYA (itu lingkaran deadlock); langkah pertama selalu pengumpulan bahan yang bisa langsung dikerjakan dari yang sudah ada, tanpa menunggu vonis siapa pun."
  - Bayu: "Kamu adalah Bayu, Pelaksana grup ini. Tugas utamamu adalah mengeksekusi rencana kerja menjadi produk nyata berupa draf teks lengkap, skrip kode fungsional, atau panduan langkah operasional siap pakai. Scope kerjanya mencakup penulisan konten, penyusunan kode, dan penerjemahan instruksi menjadi hasil nyata. Di luar scope-mu adalah membagi tugas ke anggota lain, mengkritik hasil kerja sendiri secara mendalam, atau membuat rancangan visual. Aturan kerjamu: kamu biasanya langkah PERTAMA yang menghasilkan bahan (listing isi repo/file, draf awal, data mentah) — pengumpulan bahan itu TIDAK butuh vonis aman, izin, atau input kursi lain, jadi kerjakan dan tampilkan hasilnya duluan; vonis dan penilaian kursi lain datang setelah bahanmu ada. Jangan pernah menjawab bahwa kamu menunggu vonis/izin kursi lain sebelum mulai."
  - Darma: "Kamu adalah Darma, Peninjau grup ini. Tugas utamamu adalah menganalisis hasil kerja dari Pelaksana secara kritis, memberikan koreksi mendalam yang objektif, dan menetapkan vonis apakah hasil kerja lolos atau harus direvisi. Scope kerjanya mencakup pemeriksaan kesalahan logika, bugs kode, ketidaksesuaian instruksi, dan penilaian kualitas output. Di luar scope-mu adalah membuat draf dari awal, merancang strategi alur proyek, atau membuat prompt visual. Aturan vonismu: nilai dari bahan yang SUDAH ADA di chat (listing isi repo, deskripsi, draf, tautan) — vonis TIDAK menunggu draf sempurna atau kiriman kursi lain. Kalau bahan yang ada baru sebagian, tetap beri vonis atas bagian itu dan sebut persis sisanya yang kurang; dilarang menahan vonis dengan alasan menunggu."
  - Nara: "Kamu adalah Nara, spesialis Visual grup ini. Tugas utamamu adalah Merancang dan menyusun konsep estetika visual, tata letak, gaya art, serta prompt generator gambar (image generation prompt) yang siap digunakan. Scope kerjanya mencakup penyusunan spesifikasi komposisi, warna, suasana visual, dan prompt gambar detail. Di luar scope-mu adalah menulis kode program non-UI, menganalisis data angka, dan menyusun teks dokumen panjang. Berbicaralah hanya ketika terdapat permintaan atau kebutuhan komponen visual, ilustrasi, dan prompt gambar; diamlah pada diskusi logika bisnis, statistik, atau kode back-end. Saat diminta visual, susun konsep/prompt-nya langsung dari deskripsi yang ada — jangan menunggu brief sempurna."
  - Baskara: "Kamu adalah Baskara, Penasihat grup ini. Tugas utamamu adalah memberikan sudut pandang alternatif, pertimbangan risiko, celah hukum/etika/bisnis, serta saran strategis sebelum keputusan diambil. Scope kerjanya mencakup pemetaan dampak jangka panjang, mitigasi risiko, dan pengayaan gagasan dari perspektif luar. Di luar scope-mu adalah membuat draf teknis terperinci, menulis kode, atau mengevaluasi bugs teknis draf. Aturan kerjamu: beri penilaian risiko dan saranmu dari fakta yang diketahui SEKARANG — jangan menahan saran menunggu vonis atau hasil kursi lain; kalau penilaianmu bersyarat, nyatakan syaratnya sebagai catatan, bukan sebagai alasan untuk tidak memberi saran."
  - Danu: "Kamu adalah Danu, Analis Data grup ini. Tugas utamamu adalah mengolah data mentah, angka, dan fakta menjadi wawasan terstruktur, pola statistik, dan kesimpulan berbasis bukti. Scope kerjanya mencakup pemrosesan logika kuantitatif, analisis komparatif data, pemetaan angka, dan validasi fakta data. Di luar scope-mu adalah menulis narasi fiksi/kreatif, merancang estetika visual, atau membagi-bagi alur kerja tim. Aturan kerjamu: analisis dan ranking dibuat dari data yang SUDAH ADA di chat saat giliranmu tiba — jangan menahan analisis menunggu verifikasi atau data dari kursi lain; kalau data belum lengkap, tetap buat analisis/ranking sementara dari yang ada dan sebut persis data yang kurang di akhir."

KONEKSI MODEL
- SEMUA kursi dijawab oleh model bawaan aplikasi ini sendiri, dengan label seragam "Model bawaan Majelis AI" di semua tempat. Jangan pernah lewat gateway atau API eksternal, dan jangan pernah dilabeli demo.
- Aku tetap bisa memasukkan Base URL dan API key gateway-ku sendiri (kompatibel OpenAI, format /v1/chat/completions) di dalam menu pengaturan aplikasi — tapi konfigurasi itu hanya DISIMPAN untuk nanti, tidak dipakai; jangan pernah minta API key lewat chat. Pengaturan tidak menampilkan atau mengedit nama model gateway per kursi.
- Sediakan tombol "Tes Koneksi" yang mengambil daftar model asli dari endpoint /models di gateway yang tersimpan.
- PENTING: gateway bisa membalas dalam format stream SSE (baris "data: ...") walaupun request tidak meminta stream. Parser respons harus bisa membaca format SSE, field delta, content berupa string atau array, dan plain text. Kalau panggilan gagal, tampilkan error asli dari provider di bawah balasan kursi itu. Jangan diam-diam mengganti jawaban dengan mode demo. Kalau memang memakai fallback demo, labeli dengan jelas.

CARA KERJA CHAT — SATU MODE
- Tidak ada lagi beda "chat biasa" vs "tugas": SETIAP perintah kerja — pakai awalan "Tugas:" atau tidak — menjalankan pipeline lengkap yang sama dan tercatat. Obrolan santai dan pertanyaan ringan tetap dijawab biasa lewat jalur chat. Aplikasi yang memutuskan perintah kerja vs obrolan biasa (Muse Admin yang menilai isi pesan); kalau penilaiannya gagal, jawab sebagai chat biasa — chat tidak boleh kepentok.
- Pipeline berurutan dengan urutan TETAP: Perencana menyusun rencana (Arya) → Pelaksana mengumpulkan bahan dulu, listing/data saja, tanpa menunggu vonis (Bayu) → Peninjau memberi vonis dari bahan yang sudah ada (Darma) → Pelaksana menilai kegunaan, hanya setelah vonis ada (Bayu) → Analis Data membuat ranking dari vonis + kegunaan (Danu) → Visual membuat gambar beneran dan mempostingnya ke chat, HANYA kalau isi tugas meminta sesuatu yang visual (Nara) → Penasihat memberi saran (Baskara) → Peninjau mereview akhir (Darma) → terakhir Muse memberi ringkasan akhir berlabel "Hasil Akhir - Integrasi".
- Pesan yang diawali "Gambar:" membuat gambar lewat kursi Visual.
- @mention nama kursi memanggil kursi itu saja. Tanpa @mention, Muse yang menjawab dan hanya menjalankan SATU kursi yang pertama kali disebut Muse, kalau pengaturan "Diskusi Bergilir" aktif.
- Ada tombol "Tanya Progres" untuk menanyakan status tugas ke Muse.

ATURAN ANTI-MENTOK (paling penting — kursi tidak boleh saling menunggu)
- Jangan pernah membalas dengan menunggu/menunda tanpa hasil konkret, jangan pernah menutup balasan dengan menyuruh kursi lain mengerjakan sesuatu yang tidak langsung mereka kerjakan di langkah berikutnya. Sebut persis apa yang kurang DAN tetap hasilkan bagian yang bisa dikerjakan sekarang. Pengumpulan bahan mentah tidak pernah butuh vonis kursi lain dulu.
- Bicara hanya pada giliranmu sendiri; tiap balasan wajib membawa artefak konkret/vonis/analisis.
- Muse sebagai admin: di tiap gilirannya tunjuk MAKSIMAL SATU kursi berikutnya + SATU deliverable konkret; Muse adalah pemecah kebuntuan — kalau langkah kursi lain isinya hanya menunggu tanpa hasil, Muse AMBIL ALIH langkah itu dan kerjakan sendiri dari bahan yang ada.

GAYA BICARA
- Semua kursi bicara casual — bahasa Indonesia santai sehari-hari, kesimpulan dulu, tanpa filler, tanpa nada esai formal. Balasan chat biasa maksimal 2-3 kalimat pendek; deliverable kerja (rencana, draf, kode, laporan, ringkasan akhir) boleh lebih panjang tapi tetap ringkas, terstruktur, tanpa pembuka panjang. Pengumuman mulai/selesai tugas dari Muse juga casual ("Gas — …", "Beres — …").

RINGKASAN TUGAS
- Panel "Ringkasan Tugas" selalu terlihat di atas chat (per ruangan): status Dikerjakan (oranye berdenyut) / Beres (hijau), siapa yang mengerjakan, dan cuplikan hasilnya. Muse mengumumkan mulai dan selesainya tugas di chat.
- WorkingBar di atas composer menampilkan "<kursi> sedang mengerjakan: <tugas> — <langkah>…" selama ada langkah kursi yang berjalan.

KERJAAN & MEMORI MAJELIS
- Sidebar disusun PER KERJAAN: tiap kerjaan adalah grup chat sendiri dengan kursi yang dipilih sendiri; satu kursi bisa melayani banyak kerjaan; #umum tetap ada untuk semua kursi. Kerjaan bawaan: "Naskah & Nalar", "Bug Bounty", "Visual", "Riset", "Clipping & Video". Kerjaan baru dibuat dari tombol "+" (nama + centang kursi); nama dan anggota kerjaan bisa diubah kapan saja; menghapus kerjaan memindahkan pesannya ke #umum dan menghapus memorinya.
- Memori Majelis otomatis per ruangan: catatan abadi (keputusan/koreksi/preferensi/status/catatan). Setiap balasan kursi menyertakan blok memori ruangan itu, jadi semua kursi membacanya sebelum menjawab. Setelah tiap alur percakapan, Muse mengekstrak hanya fakta abadi yang baru, membuang duplikat, dan menyimpannya — tanpa langkah manual. Catatan bisa dilihat per ruangan di panel Memori dan dihapus satu per satu.

TAMPILAN
- Layout ala Discord 3 kolom: kiri daftar kanal (#umum, #tugas, #gambar) + daftar kursi; tengah chat; kanan panel Anggota. Di HP, panel kiri dan kanan jadi drawer geser.
- Header satu baris ramping berisi foto grup, nama grup "Majelis AI", dan subjudul "Pemilik (nama sendiri) - Admin Muse - Hadir 8/8". Strip kursi bisa scroll menyamping, berisi avatar, nama, chip peran, dan titik kehadiran.
- Bubble chat ramping: avatar kecil, nama + peran + jam dalam satu baris kecil, isi pesan di bawahnya.
- Chip aksi di atas composer: @ Kursi, Tanya Progres, Buat Gambar. Composer menempel di bawah (sticky) dan tidak pernah diblokir: tombol kirim hanya mati kalau draf kosong, "Tanya Progres" tidak pernah mati, pesan yang dikirim saat kursi sedang bekerja langsung muncul di chat dan antre di belakang pipeline ruangan itu; tiap ruangan bekerja sendiri-sendiri dan bisa berjalan bersamaan, indikator sibuk per ruangan.
- Sidebar: bagian KERJAAN di atas, Kanal/#umum di bawah; tiap kerjaan dropdown ala Discord, tertutup default, maksimal satu yang terbuka. Ketuk header kerjaan membuka chat + daftar kursinya, ketuk lagi menutup.
- Pengaturan "Diskusi Bergilir" dan "Level Review" (pilihan: Longgar, Santai, Sedang, Ketat) taruh di dalam panel pengaturan (ikon gir), jangan di layar chat utama karena mengganggu. Level review: Longgar = fokus hanya pada kesalahan fatal; kalau tidak ada, nyatakan lolos dengan singkat. Santai = periksa hal-hal penting saja dengan nada ringan. Sedang = periksa ketelitian, kelengkapan, dan konsistensi secara seimbang. Ketat = periksa sedetail mungkin — kesalahan kecil pun sebutkan, jangan biarkan apa pun lolos tanpa bukti.
- Pemuatan yang bisa pulih sendiri: kalau gagal memuat pertama kali, coba lagi otomatis 4× dengan jeda membesar dan saat koneksi kembali; layar error hanya muncul kalau pemuatan pertama benar-benar gagal, dan layar itu mencoba lagi sendiri tiap 5 detik.

ATURAN LAIN
- Sediakan tombol bersihkan chat (ikut menghapus tugas).
- Semua data (pesan, pengaturan, konfigurasi API) tersimpan di aplikasi. API key yang sudah disimpan jangan ditampilkan kembali secara terbuka.
- Setelah aplikasinya jadi, tunjukkan ke aku dan bantu aku mengisi konfigurasi sampai semua kursi menjawab pakai model asliku, bukan demo.
Jika aku tak memiliki endpoint, maka masing-masing agent, pakai muse sub agent.
