# Putusan DA independen — SUNHERD V3

**DA REJECT - ceiling 96/100, konsep ditolak karena strategi aman belum dipatahkan, aturan inti belum lengkap, dan klaim pembeda 99 belum berbukti.**

Saya membaca seluruh SPEC_V3.md, baris 1–195, dan seluruh ASTRA_CEO_THESIS.md. Saya mengaudit rancangan, bukan membuat SPEC atau menilai build yang belum tersedia. Ceiling 96 adalah batas penilaian DA untuk rancangan sekarang, bukan skor Blind Judge atau angka hasil pengukuran produk. Klaim ceiling 99 ditolak. Bar wajib 98; 96 tetap ditolak, bukan HOLD untuk diteruskan ke produksi. Tidak ada izin build produksi atau submit dari audit ini; prototipe untuk membantah temuan desain tetap diperlukan.

## Enam pertanyaan wajib

1. **(a) Ceiling nyata: 96/100; 99 tidak sah sebagai kesimpulan audit.** SPEC baris 11 mengakui prototipe, lima pengamat, dan tiga run belum tersedia. Baris 190 menyebut angka 99 “dipilih sebagai batas atas desain”, tanpa bukti bahwa pilihan rute menghasilkan kedalaman. Enam wilayah berisi pola yang sama: dua koridor bergabung kembali, diulang 36 persilangan (19, 37, 173). Satu hukum fisika bersama adalah dasar menarik, tetapi jumlah sistem dan tampilan 3D bukan bukti mutu 99. Tesis Aturan 1 menuntut sebab-akibat prototipe dan DA independen sebelum SPEC; Aturan 12 menuntut bukti visual spesifik untuk nilai >=95. Menulis semua pengujian NOT_RUN itu jujur, tetapi tidak membuat G0 lulus. Nilai leaderboard LANTERNWAKE 94,01% bukan skor Judge 94,01/100 (SPEC 7); tidak boleh dipakai untuk menghitung keunggulan SUNHERD.

2. **(b) Dunia hidup: 7/10 pada rancangan; belum lulus bukti.** Air bergerak tanpa input, Luma mencari pijakan, dan puing yang telah lepas terus bergerak (47, 55–57). Ini lebih kuat daripada latar animasi. Tetapi puing awal terkunci dan hanya aktif setelah input (63–65); rumput, panggilan tiap 4 detik, dan gerak menoleh bukan keputusan dunia yang saling mengubah. Tes baris 159 sengaja dimulai saat air sudah bergerak dan hanya menuntut air bergeser 2 meter serta delapan Luma bergerak/berputar; bayangan baru berubah setelah input berikutnya. Tes itu dapat lulus dengan gerak ramai tanpa satu pun perubahan akses atau akibat antarsistem selama pemain diam. Rantai air menggeser Luma lalu mengubah risiko berikutnya belum diwajibkan.

3. **(c) Ancaman earned: 8/10 pada aturan puing; belum lengkap pada air.** Rumus muatan di baris 65 benar-benar mengaitkan risiko pada sudut, jarak lintasan, dan suhu. Contoh 90 derajat, jarak 3 meter, H=20 menghasilkan 9, melewati ambang 8 (67). Log pemicu baris 71 dan tes 100 pelepasan baris 157 adalah bukti yang tepat untuk menolak spawn timer. Namun air “dapat mendorong” Luma tidak mempunyai rumus dorongan, massa, atau aturan pertukaran kecepatan. ID input pada log juga tidak otomatis membuktikan pemain punya pilihan bermakna: jika setiap jangkar wajib memicu puing yang sama, itu tetap bahaya yang dipasang pada langkah perjalanan. Harus ditunjukkan dua keputusan dari keadaan awal sama menghasilkan rantai bahaya berbeda yang dapat dibaca pemain.

4. **(d) Dimensi nyata: 8/10 pada rancangan; bukan sekadar gambar 2D miring.** Mesh atas/bawah/samping, beda tinggi 6–12 meter, dan normal penerima berubah minimal 60 derajat memengaruhi akses serta tabrakan (27, 45, 83–85). Itu dasar ruang nyata. Tetapi jaringan keputusan masih dua cabang yang selalu bergabung; perjalanan 3D belum berarti kedalaman keputusan 3D. Tes menghapus sumbu z pada dua persilangan per wilayah (158) bisa gagal hanya karena geometri dirusak. Bukti lebih kuat harus menunjukkan dua lintasan yang bertumpuk di layar tetapi berbeda akses/bahaya karena kedalaman, dengan pilihan pemain dan hasil yang tercatat. Angka 8 menilai rancangan ruang, bukan kelulusan implementasi.

5. **(e) Pembeda 0,5 detik: 6/10; belum terbukti terhadap LANTERNWAKE.** Yang direncanakan terlihat: pulau pecah 60% layar, matahari kanan atas, lima Luma di sisi bawah, air dari dinding kiri, dan jejak puing berbeda tinggi (97). Judge dapat membaca “kawanan berjalan di bawah pulau dengan matahari besar”. Satu screenshot tidak membuktikan bahwa pemain memindahkan matahari atau bahwa tarikan mengendalikan semuanya. Tes 4/5 pengamat menerima jawaban gravitasi **atau** kawanan di bawah/samping (101): semua pengamat bisa lulus hanya dengan mengenali posisi makhluk. Rekaman resmi lawan masih UNKNOWN (7, 194), sehingga keunggulan visual terhadap lawan tidak terverifikasi. Ubah syarat: sedikitnya 4/5 harus mengaitkan matahari sebagai pusat tarikan dengan minimal dua sistem dunia, bukan hanya menyebut pulau terbalik. Pakai screenshot build asli dan studi lawan bersumber jelas. Rasio kontras HUD tidak membuktikan kontras siluet Luma terhadap dunia.

6. **(f) Core verb >=5 kali per malam: 8/10 pada struktur; belum lulus run normal.** Konsep ini tidak memakai malam. Unit tetap satu wilayah sudah ditetapkan sebelum tes (19–21), sesuai pengecualian Tesis Aturan 5. Enam bidang penerima wajib, satu perpindahan tidak dapat melewati dua bidang, sehingga rute menang menuntut sedikitnya enam aksi kemajuan per wilayah: minimal 36 per run, dan 108 pada tiga run (25–29, 153). Ini memenuhi hitungan rancangan >=5, bukan bukti kedalaman atau normal play. Definisi aksi sah hanya menghitung Luma melintasi bidang persilangan; perpindahan penyelamatan tanpa melintasi bidang baru tidak masuk hitungan, meskipun target menyebut pemulihan anggota (25 versus 29). Pisahkan jumlah input berbayar, aksi kemajuan, dan penyelamatan berhasil. Tiga run independen dan 18 hitungan wilayah tetap NOT_RUN.

## Lima veto wajib

### (i) Defend/hold terselubung: TIDAK

SPEC 19, 37–41, dan 87 menetapkan ekspedisi satu arah, meninggalkan wilayah lama, tanpa malam, markas, upgrade statistik, bos, atau gelombang. Tujuan keluar dengan >=8 Luma memang melindungi kawanan, tetapi kegiatan utamanya membawa mereka maju, bukan menjaga titik selama N malam. Saya tidak memaksakan label defend/hold hanya karena ada makhluk yang harus selamat. Veto ini tidak aktif. Ini perbedaan struktur yang nyata dari konteks empat konsep gagal; bukan alasan otomatis memberi 98.

### (ii) Kontras WCAG: LULUS hitungan, belum lulus render

Saya menghitung ulang seluruh 14 pasangan tabel SPEC 129–142 memakai Python: kanal dibagi 255; linear = c/12,92 bila c<=0,04045, selain itu ((c+0,055)/1,055)^2,4; L=0,2126R+0,7152G+0,0722B; rasio=(L lebih terang+0,05)/(L lebih gelap+0,05).

| Pasangan | L elemen | L latar | Python | SPEC | Selisih absolut |
|---|---:|---:|---:|---:|---:|
| #F4F7FA / #081322 | 0,926567528 | 0,006328618 | 17,336969 | 17,336969 | <0,000001 |
| #B8CADB / #13283D | 0,575458797 | 0,019929526 | 8,944130 | 8,944130 | <0,000001 |
| #FF8E95 / #13283D | 0,427759282 | 0,019929526 | 6,832011 | 6,832011 | <0,000001 |
| #102033 / #FFD166 | 0,013821992 | 0,678202377 | 11,409897 | 11,409897 | <0,000001 |
| #67E8F9 / #081322 | 0,674363433 | 0,006328618 | 12,859599 | 12,859599 | <0,000001 |
| #66788A / #203F59, dilarang | 0,180927003 | 0,045833585 | 2,409667 | 2,409667 | <0,000001 |

Tidak ada kesalahan >0,5 pada 14 pasangan. Semua 13 pasangan yang diizinkan lolos 4,5:1; kandidat 2,409667 memang FAIL dan dilarang. Panel opak adalah keputusan tepat (105, 144). Ini memverifikasi angka dokumen; sampling render, ukuran, dan keadaan UI aktual masih NOT_RUN (161).

### (iii) Rumus lengkap dan PASS terukur: GAGAL

- **Kondisi buntu energi belum ditutup.** Biaya minimal 6, dan sudut 60 derajat membutuhkan 10 energi (75). Contoh enam aksi wajib 180 derajat menyisakan 16 (77); dua perpindahan pemulihan 90 derajat yang tidak mengambil embun akan menyisakan 6 setelah yang pertama dan membuat yang kedua ditolak. Pemindahan 120 derajat dari sisa 16 menghasilkan E=4. Jika ada anggota tertinggal dan belum ada hadiah yang terjangkau, E=4 tidak cukup untuk gerak apa pun. Aturan kalah hanya menyebut energi habis/nol (39), sehingga keadaan E=1–5 tidak punya penyelesaian otomatis. Tetapkan kalah atau jalan pemulihan bila tak ada aksi terjangkau dan tujuan belum tercapai.
- **Sudut θ tidak punya titik ukur.** Medan radial berbeda pada tiap Luma dan puing, tetapi biaya serta muatan memakai satu θ (55, 65, 75). Tentukan vektor asal/tujuan dan posisi sampel. Lintasan pusat fisika selama 0,6 detik tidak mempunyai fungsi interpolasi (33), padahal jarak d_j terhadap lintasan menentukan puing lepas.
- **Urutan pelepasan bertentangan/tidak selesai.** q>=T langsung melepas pada 65, sementara bunyi retak harus terjadi 0,6 detik sebelum lepas pada 67. Tentukan kapan q ditambah, kapan peringatan dimulai, kapan gravitasi dan pelepasan berjalan, serta urutan pendinginan dan pengambilan embun.
- **Fisika air dan TAHAN tidak lengkap.** Air diberi integrasi benda dan pantulan nol (55), tetapi dorongan pada kawanan, volume, kontak pendinginan, dan aturan mempertahankan pijakan saat TAHAN belum ditentukan (31, 71, 79). Simulasi deterministik tidak bisa direproduksi dari angka ini saja.
- **Tes anti-strategi salah sasaran.** Baris 155 hanya membandingkan selalu-pendek; selalu-panjang tidak diuji. Baris 154 menerima beda satu puing aktif walaupun puing tidak mengancam Luma. Baris 169 hanya menolak bila semua koridor punya akibat sama; strategi aman dominan tetap dapat lolos walaupun pilihan lain punya akibat lebih buruk.
- **Tes pratinjau mengeluarkan kasus tersulit.** Baris 156 mensyaratkan “tanpa puing baru”, padahal pelepasan puing akibat input adalah inti ancaman. Uji harus mencakup ambang pelepasan, tabrakan Luma, dan kontak air, dengan toleransi posisi/waktu eksplisit.
- **Kepadatan dan showcase belum punya batas lulus.** D_l hanya 1–4 puing relevan per persilangan (83). Tes dunia hidup menerima gerak/putaran, tanpa mensyaratkan tiga sistem berinteraksi pada layar gameplay yang sama. Anggaran 150 menit untuk 36 persilangan berarti rata-rata 4,17 menit per persilangan sebelum pengujian (173); anggaran bukan bukti setiap ruang punya keputusan berbeda. CPU/GPU tes performa juga belum menunjuk perangkat/model pasti (163).

Banyak ambang sudah numerik dan berguna. Namun angka yang tersedia tidak menutup lubang aturan dan tes di atas. G1 tidak lulus.

### (iv) Bahasa kabur: ADA, dan memengaruhi penerimaan

Tidak ada kebutuhan mencari kata “mungkin” untuk menemukan kelonggaran. Frasa “air ... dapat mendorong ... dengan kecepatan alir” (71) tidak menentukan besar akibat. “Puing relevan” (83) tidak menentukan relevan terhadap siapa atau seberapa dekat. “Seluruh keadaan ... identik” pada checkpoint (165) tidak menjelaskan apakah identik dengan awal wilayah atau saat keluar. “Menanggapi”, “mencari titik pijak”, dan “mengitari tetangganya” (17, 47) belum punya aturan gagal/berhasil yang menjaga kelompok tetap bisa diselamatkan. “YA sebagai hipotesis” dan “sasaran teruji” pada audit penulis (190, 194) bukan hasil uji. Status NOT_RUN sendiri jelas dan jujur; yang ditolak adalah penggunaan hipotesis itu untuk mendukung 99.

### (v) Strategi aman dominan: celah struktural AKTIF; ceiling dibatasi 96

Strategi yang harus dibantah: **selalu pilih koridor panjang berair, dinginkan penuh, tunggu muatan puing turun, lalu lanjut**. SPEC sendiri menyatakan koridor panjang melewati air, menghindari puing, dan mendinginkan (19, 51). Tidak ada batas waktu kalah (39), tidak ada energi habis karena menunggu (75), dan muatan terkunci turun 1 per detik (65). Menunggu tidak menghilangkan muatan satu perpindahan yang langsung melewati ambang; saya tidak mengklaim itu. Menunggu menghapus akumulasi muatan sebelum perpindahan berikutnya.

Hitungan Python untuk contoh sudut panjang 120 derajat: biaya 12, embun +8, kenaikan suhu 12, pendinginan 4 detik menghapus sampai 24. Dengan kontak air dan embun tiap persilangan sebagaimana diizinkan aturan, enam langkah menghasilkan E=96, 92, 88, 84, 80, 76 dan H=0 sesudah masing-masing pendinginan. Bahkan enam langkah termahal 180 derajat tanpa satu embun pun masih menyisakan 16 energi (77). Jadi biaya energi sendiri tidak memaksa meninggalkan rute panjang. Pada H=0, θ=120, puing berjarak d=9 mendapat 3,333333 muatan, di bawah ambang wilayah tersulit 5; d>=12 mendapat nol. Posisi puing yang memastikan jalan panjang tetap berbahaya belum diberikan.

Ini pembuktian bahwa aturan sekarang **mengizinkan** jalur aman berulang dan tesnya tidak menolaknya, bukan klaim bahwa saya sudah memenangkan build yang belum ada. Tata ruang aktual belum tersedia, sehingga kemenangan universal pada seluruh 36 persilangan belum teruji. Namun DA tidak memberi 98 kepada rancangan yang dapat memenuhi tes tertulis sambil membiarkan strategi ini menang. Bonus waktu hanya memengaruhi skor; menunggu tetap dapat memenuhi syarat menang >=8 Luma. Tesis Aturan 12 meminta serangan struktural ini, dan SPEC 190 sendiri menetapkan ceiling 96 bila strategi aman dominan ditemukan. Saya menerapkan batas 96 karena pelindung desain terhadap strategi ini gagal, bukan mengarang hasil run.

## Veto DEC-0022 dan perubahan wajib

**Veto anti-rata-rata aktif.** Kontras angka UI lolos dan ruang 3D tertulis cukup konkret. Dua hal itu tidak menggantikan kedalaman keputusan dan showcase lengkap. Saat ini tes menerima gerak tanpa akibat, dua cabang tanpa pertukaran risiko yang wajib, dan screenshot pulau terbalik tanpa bukti pemain mengendalikan matahari. Bukti showcase build tidak tersedia. Klaim bahwa konsep sudah punya ceiling 99 tidak bertahan menghadapi lubang tersebut.

Sebelum audit ulang:

1. **Ubah hubungan risiko, bukan tambah efek.** Buat keuntungan pendinginan membawa biaya atau bahaya yang benar-benar mengubah keputusan; jangan jadikan panjang hanya berarti lebih lambat. Uji selalu-panjang, selalu-pendek, tunggu muatan nol, dan campuran pada seluruh enam wilayah. Tetapkan pembanding jumlah selamat, energi, waktu, dan skor. Tunjukkan sedikitnya tiga keadaan yang membuat pilihan aman sebelumnya menjadi pilihan buruk karena hubungan sistem, bukan larangan klik buatan.
2. **Tutup aturan yang memengaruhi hasil.** Tentukan θ, lintasan matahari, urutan peristiwa, kontak/dorongan air, TAHAN, keadaan energi tak cukup, dan hitungan penyelamatan. Uji pratinjau dengan pelepasan puing baru serta bencana air. Perbaiki ketidaksesuaian definisi aksi dan biaya pemulihan.
3. **Buktikan pembeda serta kehidupan dunia pada prototipe yang sama.** Tampilkan satu input yang mengubah akses Luma, arus air, dan risiko puing; setelah input berhenti, ketiganya tetap saling menimbulkan akibat. Perlihatkan keputusan ruang bertingkat yang tidak dapat diganti dua tombol rute. Jalankan tes screenshot 4/5 yang mengharuskan pengamat membaca hubungan matahari–tarikan–dunia. Lengkapi studi resmi LANTERNWAKE tanpa mengubah 94,01% menjadi skor Judge.
4. **Ulang G0 secara independen.** Simpan hasil yang gagal juga. Hanya setelah veto desain tertutup dan ceiling DA >=98, lanjut G1/G2 dan produksi; tiga run G3, Blind Judge >=98, dan DA final tetap wajib. Empat penolakan terdahulu pada rentang 90–97 tidak memberi SUNHERD hak mendapat pengecualian.

**DA REJECT - ceiling 96/100, konsep ditolak karena strategi aman belum dipatahkan, aturan inti belum lengkap, dan klaim pembeda 99 belum berbukti.**
