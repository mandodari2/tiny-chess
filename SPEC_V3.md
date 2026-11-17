BAR DESAIN Blind Judge >=98/100

# SUNHERD — Menggiring Matahari

SPEC V3, 17 November 2026. Ketua: Joe. CEO: Mandodari. Penanggung jawab konsep: Astra. Kompetisi best-game-01, hadiah 1.000 dolar, tenggat 19 November 2026 01:00 WIB, setara 18 November 18:00 UTC.

94,01 persen adalah angka leaderboard yang diberikan Chairman, bukan hasil Blind Judge 94,01/100. Target internal tetap minimal 98/100. Rekaman resmi LANTERNWAKE belum diperiksa: UNKNOWN. Pernyataan tentang struktur lawan memakai konteks Chairman; tidak ada klaim hasil pengamatan langsung.

## Keputusan Phase 0 sebelum penulisan

Ceiling adalah TARGET DESAIN minimal 98/100 BELUM TERBUKTI. Putusan DA terakhir tetap REJECT dengan ceiling 96/100, di bawah bar 98; revisi dokumen tidak membatalkan putusan itu. Prototipe sebab-akibat, lima pengamatan independen, dan tiga run penuh: NOT_RUN. Tidak ada bukti G0 PASS. Dokumen ini tidak mengizinkan produksi atau submit; hanya prototipe pembuktian dan audit ulang yang menjadi langkah berikutnya.

Instruksi tugas membatasi perubahan pada SPEC_V3.md; seluruh revisi dan hitungan dicatat di file ini tanpa file pendamping.

## Janji permainan dan struktur baru

Pemain membawa 12 makhluk kecil bernama Luma menuju langit terbuka dengan memindahkan satu matahari buatan. Pusat tarikan mengikuti matahari itu. Kawanan berjalan di sisi pulau yang menghadap matahari; air tumpah melengkung, puing terlepas, dan jalur yang tadinya berada di bawah kaki menjadi dinding. Pemain membaca akibat, memilih jangkar matahari berikutnya, lalu berangkat bersama dunia yang berubah.

Struktur: ekspedisi satu arah enam wilayah, masing-masing satu sesi uji, tanpa malam, markas, menara, toko upgrade, bos, atau gelombang bertahan. Wilayah sebelumnya ditinggalkan setelah kawanan menyeberang. Setiap wilayah memiliki enam persilangan ruang berurutan. Setiap persilangan menawarkan dua koridor tiga dimensi yang bertemu lagi di persilangan berikutnya. Koridor pendek melewati puing; koridor panjang melewati air yang dapat mendinginkan matahari. Perubahan rute mengubah bahaya dan sisa sumber daya.

Unit uji tetap adalah satu wilayah dari masuk sampai keluar, bukan satu persilangan. Enam wilayah ditetapkan sebelum pengujian; penyebut tidak diganti untuk meluluskan frekuensi.

## Kata kerja inti dan kontrol

Kata kerja inti: MEMINDAHKAN PUSAT GRAVITASI. Satu aksi sah terjadi ketika matahari berpindah ke jangkar baru dan sekurangnya satu Luma melintasi bidang persilangan karena perubahan tarikan itu. Klik dibatalkan, perpindahan kamera, dan memindahkan matahari bolak-balik tanpa kemajuan tidak dihitung.

Setiap persilangan mempunyai bidang penerima dengan normal berbeda minimal 60 derajat dari bidang sebelumnya. Hanya jangkar di koridor yang dipilih yang membuat bidang penerima menjadi lantai. Satu pemindahan tidak dapat melewati dua persilangan: bibir batu menghalangi garis lintasan, dan jangkar berikutnya baru berada dalam jangkauan setelah kawanan mencapai bidang penerima. Ini pembatas ruang yang terlihat, bukan pintu yang meminta sejumlah klik.

Target normal: 6–10 aksi sah per wilayah, minimal 6 wajib, minimal audit DA 5. Setiap aksi harus memilih koridor, waktu berangkat, atau pemulihan anggota, bukan mengulang tombol. Tiga run menang penuh oleh penguji yang tidak membuat mekanik harus memenuhi min(c1,...,c6)>=5 tanpa menunggu atau mengulang demi jumlah.

Kontrol desktop: gerakkan mouse untuk memilih jangkar; tahan klik kiri untuk pratinjau, lepas untuk konfirmasi; klik kanan membatalkan; Q/E memutar kamera 45 derajat; roda mouse mengatur jarak kamera 18–32 meter; Space menahan kawanan di permukaan selama maksimal 2 detik; Esc jeda. Papan ketik penuh: Tab memilih jangkar, Enter pratinjau lalu konfirmasi, Backspace batal. Sentuh: ketuk jangkar untuk pratinjau, ketuk tombol PINDAH untuk konfirmasi, geser dua jari untuk kamera, tombol TAHAN menggantikan Space. Menahan kawanan tidak menghentikan air atau puing dan tidak menambah energi.

Pratinjau maksimum 2 detik memperlambat simulasi menjadi 25%; tidak memulihkan sumber daya. Garis lintasan 3 detik ditampilkan untuk pusat kawanan, tiga puing terdekat, dan air terdekat. Konfirmasi mengubah cahaya langsung, sedangkan pusat fisika bergerak selama 0,6 detik. Tidak ada pengeluaran sebelum konfirmasi.

## Struktur level, menang, kalah

Enam wilayah: 1 Kebun Terbalik; 2 Air di Dinding; 3 Tulang Kapal; 4 Dua Sisi Tebing; 5 Cincin Retak; 6 Pintu Fajar. Tiap wilayah berisi enam persilangan, masing-masing dua rute. Wilayah 1 mengajarkan tarikan dan puing; wilayah 2 menambahkan pendinginan air; wilayah 3 menggabungkan puing dan pendinginan; wilayah 4 menambah perbedaan ketinggian; wilayah 5 membatasi garis pandang; wilayah 6 menggabungkan seluruh hubungan tanpa mekanik baru.

Menang wilayah: minimal 8 Luma berada di bidang keluar selama 2 detik dan telah melewati semua enam persilangan. Kawanan otomatis berkumpul dalam radius 1,5 meter; anggota lain tetap terlihat dan dapat dijemput sebelum konfirmasi KELUAR. Menang permainan: keluar dari wilayah 6 dengan minimal 8 Luma. Kalah: anggota yang masih dapat diselamatkan kurang dari 8, ATAU E<6 dan tujuan wilayah belum tercapai. Tujuan tercapai hanya setelah seluruh syarat menang wilayah di atas terpenuhi, termasuk diam 2 detik di keluar. Pemeriksaan dilakukan setelah setiap gerakan, setelah pembayaran biaya, dan setiap detik menunggu; simulasi juga memeriksa setiap langkah dt agar tidak terlambat. Pada kondisi tersangkut itu semua Luma membeku dan run langsung KALAH, tanpa masa tenggang, pemulihan, atau pengambilan embun sesudah kalah. E adalah sumber daya bersama, bukan energi per Luma: E<6 berarti tidak ada gerakan matahari yang dapat dilakukan, termasuk sudut nol. HUD menampilkan “KALAH — energi bersama kurang dari 6; matahari tidak bisa bergerak”, nilai E, dan tombol ULANG. Kondisi ini menggantikan aturan lama energi nol dengan tenggang 8 detik.

Tombol ulang mengembalikan seluruh keadaan awal wilayah, termasuk skor, energi, suhu, puing, air, dan jumlah anggota saat masuk. Tidak bisa mengambil hadiah berulang lewat ulang. Keluar wilayah menyimpan checkpoint otomatis. Target durasi menang normal 18–24 menit, termasuk pratinjau; jeda menu tidak dihitung. Tidak ada transaksi atau mata uang permanen.

## Dunia hidup dan dimensi yang menentukan keputusan

Ruang memakai koordinat meter (x,y,z), bukan sprite yang hanya tampak miring. Pulau memiliki mesh tabrakan atas, bawah, dan samping. Selisih tinggi minimum rute A dan B adalah 6 meter pada wilayah 1 dan bertambah menurut rumus kesulitan. Air dan puing bertabrakan dengan geometri yang sama dengan Luma. Jalur yang tampak bertumpuk di gambar tidak terhubung bila beda tinggi lebih dari 0,6 meter.

Saat pemain diam: Luma mencari titik pijak, berjalan mengitari tetangganya, menoleh pada air, dan mengeluarkan panggilan; air terus mengalir; puing dengan energi tersisa terus bergerak; rumput mengikuti arah tarikan; cahaya dan bayangan mengikuti posisi matahari. Luma yang terpisah memanggil setiap 4 detik, dengan cincin bernomor agar dapat ditemukan tanpa audio. Tidak ada animasi yang mengganti simulasi penyebab.

Matahari berdiameter 2 meter. Cahaya hangat 2.600 K bergerak bersama jangkar; cahaya langit biru 7.500 K tetap memberi isi di sisi gelap. Pergerakan matahari menggeser bayangan nyata minimal 2 meter pada setiap perpindahan. Debu arah gravitasi, kaki makhluk, aliran air, dan jejak puing memperlihatkan arah yang sama. Kecepatan gerak kamera dibatasi 90 derajat/detik; opsi kurangi gerak menghilangkan guncangan dan jejak kamera tanpa mengubah simulasi.

Contoh keputusan ruang: koridor atas 9 meter melewati satu puing dekat kawanan; koridor bawah 15 meter melewati aliran air tetapi membutuhkan tarikan 120 derajat. Atas menghemat waktu dan biaya sudut, bawah mendinginkan matahari dan menghindari puing. Pemain melihat biaya, ketinggian, dan lintasan sebelum memilih.

## Fisika inti: aturan angka dan contoh

Simulasi tetap dt=1/60 detik. Untuk benda di p dan pusat matahari s, u=(s-p)/max(|s-p|,0,001). Percepatan gravitasi a=g_l*u. Kecepatan berikutnya v'=batasi_panjang(v+a*dt, v_max); posisi berikutnya p'=p+v'*dt; lalu selesaikan tabrakan mesh dengan langkah sapuan agar benda tidak menembus permukaan. v_max=8 m/detik untuk Luma, 12 untuk puing, 10 untuk air. Pada permukaan, hilangkan komponen kecepatan ke dalam normal tumbukan; gesekan mengalikan kecepatan sejajar dengan max(0,1-3*dt). Tumbukan puing memakai pantulan 0,25; Luma dan air 0.

Contoh wilayah 1: g=8 m/detik², v awal nol; setelah satu langkah v=0,133333 m/detik menuju matahari dan perpindahan 0,002222 meter sebelum tabrakan. Semua benda bebas memakai medan yang sama. Luma yang berpijak menambahkan gerak berjalan di bidang pijak menuju pusat kelompok dengan kecepatan 1,4 m/detik; gerak ini tidak dapat menembus bibir batu.

Jangkar berada pada posisi dunia tetap. Maksimal jarak jangkar dari pusat kawanan 18 meter. Setiap persilangan mengungkap dua jangkar koridor dan satu jangkar pemulihan di belakang. Jangkar di balik penghalang padat tidak dapat dipilih. Pratinjau wajib memakai fungsi fisika dan keadaan awal yang sama dengan simulasi nyata, bukan kurva gambar terpisah.

## Ancaman earned: akibat yang dapat ditelusuri

Tidak ada musuh yang muncul setelah timer, bos, atau event gelombang. Puing sudah berada di dunia, diam dan terlihat. Pemindahan matahari melakukan kerja pada puing dekat lintasan matahari; risiko lahir dari tempat, sudut, dan suhu yang dipilih pemain. Puing yang jauh dari lintasan tetap terkunci.

Untuk puing j, simpan muatan q_j awal 0. Setiap perpindahan menambah Δq_j=10*(θ/90)*max(0,1-d_j/12)*(1+H/100), dengan θ sudut perubahan tarikan dalam derajat, d_j jarak terpendek puing ke lintasan matahari dalam meter, dan H suhu sebelum perpindahan. q_j baru=max(0,q_j+Δq_j). Puing terlepas bila q_j>=T_l; setelah terlepas tidak mengisi muatan lagi dan mengikuti gravitasi. Puing terkunci kehilangan muatan 1 unit/detik. Tidak ada muatan dari waktu yang berjalan saja.

Contoh wilayah 1: θ=90, d=3, H=20 memberi Δq=10*1*0,75*1,2=9. Ambang T_1=8, jadi puing terlepas. Pada d=9, Δq=3 dan puing tetap terkunci. Pratinjau menampilkan angka 9/8 dan simbol retak, disertai bunyi retakan 0,6 detik sebelum lepas; tidak memakai warna sebagai satu-satunya petunjuk.

Tabrakan puing dengan Luma pada kecepatan relatif >=3 m/detik membuat Luma terpental dan kehilangan pijakan, bukan langsung mati. Luma hilang hanya setelah berada lebih dari 24 meter dari permukaan terdekat selama 3 detik berturut-turut. HUD memberi hitung mundur 3–2–1 dan panah posisi. Pemindahan pemulihan dapat menyelamatkannya dengan menariknya kembali. Kecepatan <3 menghasilkan dorongan tanpa kehilangan pijakan.

Log sebab wajib: ID perpindahan, jangkar asal/tujuan, θ, H, d_j, Δq, q_j, ambang, waktu lepas, ID tumbukan, dan akibat anggota. Setiap puing aktif harus memiliki ID perpindahan pemicu. Risiko dari air: air di jalur dapat mendorong kawanan dengan kecepatan alir; pemain memilih gravitasi yang mengarahkannya, sehingga bencana air juga memiliki rantai sebab dari input.

## Ekonomi dan sumber daya

Energi E berskala 0–100. Setiap wilayah mulai E=100; ini reset checkpoint, bukan hadiah yang dapat ditimbun. Biaya perpindahan C=6+2*ceil(θ/45), θ di rentang 0–180 derajat. θ=90 menghasilkan C=10, θ=120 menghasilkan C=12. Pemindahan ditolak bila E<C; penolakan tidak mengubah keadaan. E'=max(0,min(100,E-C+R)), R=8 bila pusat kawanan melewati embun di koridor terpilih. Setiap persilangan memiliki satu embun per koridor dengan satu ID hadiah bersama; mengambil satu menonaktifkan keduanya. Maksimal 48 energi dipulihkan per wilayah. Tidak ada regenerasi sambil menunggu.

Aturan baru tunggal untuk mematahkan rute panjang: Luma memakai energi bersama seiring waktu. Pada setiap dt=1/60 detik, E_baru=max(0,E_lama-0,9*dt). Berlaku saat berjalan, diam, TAHAN, pendinginan, dan pratinjau menurut detik simulasi; menu jeda menghentikan simulasi. Tidak ada tambahan panas karena waktu dan tidak ada puing yang muncul karena jarak. Rumus total sebelum batas 0–100 adalah E=100-sum(C)+8*b-0,9*t. Biaya dibayar saat konfirmasi; embun baru diberikan saat pusat kawanan melintasi bidang penerima di ujung koridor. Jika kalah lebih dulu, embun tidak diberikan. Biaya dan peluruhan waktu tidak dibulatkan; HUD menampilkan dua desimal, pemeriksaan memakai nilai asli.

Kecepatan kemajuan pusat kawanan sepanjang koridor dibatasi 0,9 meter/detik, termasuk ketika gravitasi atau air mendorongnya; komponen gerak menyamping dan jatuh tetap memakai fisika di atas. Ini batas kecepatan berjalan rombongan, bukan waktu tunggu pintu. Panjang lintasan terpendek yang bisa dilalui pusat kawanan adalah 9 meter untuk pendek dan 15 meter untuk panjang; bibir batu mencegah potong lintasan. Maka waktu minimum pendek 10 detik, panjang 50/3=16,666667 detik. Perpindahan matahari 0,6 detik dan kontak air berlangsung di dalam waktu perjalanan; tidak ditambahkan dua kali. Embun tidak bisa diambil dari jarak jauh. Semua wilayah memakai batas ini, termasuk wilayah pengajaran.

Suhu H awal 0, dibatasi 0–100. Setelah perpindahan H_baru=min(100,H+θ/15), tanpa tambahan 4. Di luar air H tidak turun. Kontak matahari dengan air menurunkan H sebesar 6 unit/detik selama maksimal 4 detik per persilangan: H_sesudah=max(0,H_sebelum-6*min(t_kontak,4)). Pendinginan tidak mengisi energi. θ=90 menaikkan H sebesar 6; empat perpindahan tanpa air menghasilkan H=24; kontak 3 detik menurunkannya ke 6. θ=120 menaikkan H sebesar 8, bukan 12 pada versi lama. Empat detik air menghapus sampai 24 panas. Biaya tetap C=6+2*ceil(θ/45): C(0)=6, C(60)=10, C(90)=10, C(120)=12, C(180)=14. Muatan tetap memakai H sebelum perpindahan dan T_l=8-0,6*(l-1).

### Hitungan ulang serangan DA: selalu panjang GAGAL

Tanpa peluruhan waktu, enam langkah 120 dengan enam embun memang memberi E=96,92,88,84,80,76. Dengan aturan baru, tiap panjang minimal menghabiskan 15 energi waktu, sehingga selisih bersih terbaik -12+8-15=-19. Batas atas E setelah langkah 1–6 adalah 81,62,43,24,5,-14. Dua angka terakhir hanya perhitungan andaikan run tetap berjalan, bukan keadaan sah: langkah kelima mulai E=24, biaya 12 menyisakan 12; setelah 6,666667 detik E=6, lalu langkah simulasi berikutnya E=5,985 dan run langsung KALAH sebelum embun kelima, sebab perjalanan butuh 16,666667 detik. Empat persilangan selesai, tujuan belum tercapai, walaupun 12 Luma masih ada. Menunggu atau pendinginan lebih lama mempercepat kekalahan energi. Bahkan andaikan embun diberikan di awal, E setelah lima langkah paling tinggi 5: tetap kalah. Ini berlaku pada keenam wilayah dan tidak bergantung posisi puing.

H sesudah air tetap 0 pada setiap langkah yang selesai; θ=120,d=9,H=0 tetap memberi Δq=10*(120/90)*0,25=3,333333, di bawah T_6=5; d>=12 tetap nol. Puing terkunci tetap turun 1 per detik. Keselamatan dari puing tidak lagi menjamin selamat dari anggaran energi. Enam langkah 180 tanpa embun sebelumnya menyisakan 16 hanya bila waktu diabaikan; kini E=16-0,9*t, dan enam koridor panjang memerlukan minimal 100 detik sehingga batas akhirnya -74: run kalah lebih awal.

Contoh buntu DA tetap berlaku sebagai tes keadaan: dari E=16, gerakan 90 tanpa embun menyisakan 6 pada pembayaran; gerakan 90 berikutnya ditolak karena perlu 10. Setelah satu detik tanpa hadiah E=5,1 dan run langsung kalah. Gerakan 120 dari E=16 menyisakan 4 pada pembayaran dan langsung kalah sebelum pemulihan. E=6 bukan jaminan ada jangkar terjangkau: semua jangkar kemajuan bersudut minimal 60 memerlukan 10; penolakan tidak menghentikan peluruhan waktu.

### Tiga pilihan aman yang berubah buruk karena hubungan sistem

1. Pendinginan penuh saat energi rendah: E=8,H=20 di air, tujuan belum tercapai. Menunggu 4 detik menurunkan H ke 0 tetapi menghabiskan 3,6 energi; E melewati 6 sesudah 2,222222 detik dan run kalah. Berangkat lewat pendek bersudut 90 saat E=30 memakai 10+9-8=11 energi dan menyisakan 19; panjang 120 memakai 19 dan menyisakan 11. Air aman terhadap panas tetapi mengurangi cadangan penyelamatan sebesar 8.
2. Menghapus muatan dengan menunggu: E=12,q=7,T_1=8,H=0; calon langkah 90,d=9 menambah 2,5. Menunggu 7 detik memberi q=0 namun E=5,7: kalah. Menunggu 2 detik memberi q=5 dan E=10,2, lalu biaya 10 menyisakan 0,2: kalah. Membaca jangkar alternatif d>=12 saat E masih 12 menghindari tambahan muatan tanpa waktu tunggu, tetapi kelangsungan sesudahnya tetap harus dihitung dari jarak dan embun; tidak dinyatakan otomatis menang.
3. Pendek dingin menjadi buruk setelah panas terkumpul: θ=90,d=3,q=0 memberi Δq=7,5 saat H=0, masih di bawah T_1=8; setelah satu pendek H=6, langkah serupa memberi 7,95, tetapi setelah dua pendek H=12 memberi 8,4 dan melepas puing. Panjang berair menurunkan H, namun menghabiskan 8 energi lebih banyak daripada pendek pada contoh sudut di atas. Pemain harus memilih waktu pendinginan berdasarkan panas DAN energi, bukan mengulang salah satu koridor.

Contoh anggaran adaptif, bukan bukti kemenangan: tiga pendek 90 dan tiga panjang 120 dengan enam embun memerlukan minimal t=80 detik, biaya 66 dan peluruhan 72; E=100-66+48-72=10. Diam 2 detik di keluar menyisakan 8,2. Pratinjau atau penyelamatan tambahan harus masuk anggaran ini. Angka tersebut menunjukkan campuran tidak ditolak oleh energi saja; keselamatan puing dan kelayakan tata ruang wajib dibuktikan prototipe.

## Kesulitan dan progresi

Untuk wilayah l=1..6: g_l=8+0,4*(l-1); ambang puing T_l=8-0,6*(l-1); jumlah puing relevan per persilangan D_l=min(4,1+floor(l/2)); selisih ketinggian rute Z_l=6+1,2*(l-1) meter. Setiap koridor memiliki panjang 9 atau 15 meter; posisi puing menentukan biaya risiko, bukan generator acak yang memblokir rute aman.

Contoh wilayah 4: g=9,2; T=6,2; D=3; Z=9,6 meter. Wilayah 6: g=10; T=5; D=4; Z=12 meter. Jangkar, puing, dan air dibuat tangan dengan seed tetap 1701; fisika deterministik pada langkah tetap. Tidak ada penyesuaian kesulitan tersembunyi.

Progres P=100*((l-1)+k/6)/6 persen, k jumlah persilangan tuntas pada wilayah aktif. Wilayah 3, persilangan 4: P=100*(2+4/6)/6=44,444 persen. Sesudah keluar wilayah 6, P=100. Tidak ada upgrade statistik; kemajuan membuka gabungan hubungan ruang yang lebih sulit. Peta perjalanan menunjukkan wilayah yang sudah dilalui dan anggota yang ikut.

## Skor yang tidak memberi hadiah untuk bertahan

Skor hanya dikunci pada keluar wilayah. S_l=max(0,1000+200*n+40*b+floor(600*max(0,1-t/240))-80*r-300*h). n jumlah Luma dibawa keluar; b jumlah embun unik, 0–6; t detik simulasi aktual wilayah termasuk pratinjau pada skala waktu simulasi; r=max(0,c-6), c aksi inti sah; h anggota hilang pada wilayah tersebut. Waktu menu jeda tidak dihitung. Bonus kecepatan nol setelah 240 detik; tidak ada bonus untuk menunggu ancaman. Skor run=sum(S_1..S_6).

Contoh n=11,b=4,t=150,c=8,h=1: 1000+2200+160+225-160-300=3125. Perpindahan yang dibatalkan tidak dihitung; perpindahan tanpa kemajuan tetap membayar energi tetapi tidak menambah c. Skor maksimum teoritis per wilayah adalah 1000+2400+240+600=4240, batas run 25440. Maksimum teoritis bukan klaim dapat dicapai pada t=0. Prioritas UI tetap menyelamatkan minimal 8; skor tidak mengganti kondisi menang.

## Pembeda terlihat dalam 0,5 detik

Komposisi utama satu layar: pulau pecah menempati 60% bidang gambar; matahari di kanan atas dengan garis tarikan melengkung; lima Luma terlihat berjalan di bagian bawah pulau; air mengalir dari dinding kiri menuju matahari; puing mengikuti lintasan yang berbeda tinggi. HUD maksimal 18% bidang layar. Kamera perspektif 45 derajat, elevasi awal 25 derajat, seluruh kawanan dan tujuan berikutnya masuk layar; siluet Luma minimal tinggi 18 piksel pada 1280x720.

Perbedaan terhadap struktur defend/hold dalam konteks LANTERNWAKE terlihat pada perjalanan melintasi sisi bawah pulau dan pusat gravitasi yang dipindahkan. Tidak bergantung pada nama, palet, atau penjelasan teks. Tidak mengklaim LANTERNWAKE tidak memiliki fitur tertentu tanpa rekaman.

Tes: lima pengamat baru melihat screenshot gameplay tanpa judul selama 0,5 detik, lalu memilih deskripsi bebas. Minimal empat menyebut perpindahan arah gravitasi atau kawanan di sisi bawah/samping pulau dan menunjuk buktinya. Screenshot wajib berasal dari build yang dimainkan, tanpa komposisi promosi tambahan. Jika gagal, perbaiki hubungan ruang dan framing; mengganti warna saja tidak menutup kritik.

## Palet dan kontras WCAG terhitung

Semua teks berada di panel opak. Tidak ada teks langsung di atas dunia bergerak. Teks biasa minimum 16 px pada skala 100%; teks besar minimum 24 px biasa atau 18,667 px tebal, setara ambang 18 pt atau 14 pt tebal. Tooltip dan disabled tetap menggunakan pasangan terhitung. Panel #13283D berlatar #081322 dibatasi garis #67E8F9 agar tepi UI penting memenuhi 3:1 pada kedua sisi. Ikon bahaya segitiga dan garis putus-putus menyertai merah; tanda aman lingkaran disertai centang.

Rumus yang dipakai dalam perhitungan Python presisi float, pembulatan hanya pada laporan: setiap kanal C delapan bit menjadi c=C/255. Jika c<=0,04045, c_lin=c/12,92; selain itu c_lin=((c+0,055)/1,055)^2,4. L=0,2126*R_lin+0,7152*G_lin+0,0722*B_lin. Kontras=(max(L1,L2)+0,05)/(min(L1,L2)+0,05). PASS teks biasa >=4,5:1; teks besar dan komponen UI penting >=3:1 terhadap setiap warna yang bersebelahan.

Langkah pasangan 1, #F4F7FA terhadap #081322:
- sRGB teks=(244,247,250)/255=(0,956862745;0,968627451;0,980392157).
- Linear teks=(0,904661174;0,930110858;0,955973353), seluruh kanal memakai cabang pangkat.
- L teks=0,2126*0,904661174+0,7152*0,930110858+0,0722*0,955973353=0,926567528.
- sRGB latar=(8,19,34)/255=(0,031372549;0,074509804;0,133333333).
- Linear latar=(0,002428216;0,006512091;0,015996293); kanal merah memakai pembagian 12,92, dua lainnya pangkat.
- L latar=0,2126*0,002428216+0,7152*0,006512091+0,0722*0,015996293=0,006328618.
- Rasio=(0,926567528+0,05)/(0,006328618+0,05)=17,336969:1, PASS kedua ambang.

Langkah pasangan 2, #102033 terhadap #FFD166:
- sRGB teks=(16,32,51)/255=(0,062745098;0,125490196;0,2).
- Linear teks=(0,005181517;0,014443844;0,033104767).
- L teks=0,2126*0,005181517+0,7152*0,014443844+0,0722*0,033104767=0,013821992.
- sRGB latar=(255,209,102)/255=(1;0,819607843;0,4).
- Linear latar=(1;0,637596874;0,132868322).
- L latar=0,2126*1+0,7152*0,637596874+0,0722*0,132868322=0,678202377.
- Rasio=(0,678202377+0,05)/(0,013821992+0,05)=11,409897:1, PASS kedua ambang.

| Pemakaian | Elemen | Latar | L elemen | L latar | Rasio :1 | Teks 4,5 | Besar/UI 3 |
|---|---|---|---:|---:|---:|---|---|
| Teks utama | #F4F7FA | #081322 | 0,926567528 | 0,006328618 | 17,336969 | PASS | PASS |
| Teks panel/default/focus | #F4F7FA | #13283D | 0,926567528 | 0,019929526 | 13,965024 | PASS | PASS |
| Teks sekunder | #B8CADB | #13283D | 0,575458797 | 0,019929526 | 8,944130 | PASS | PASS |
| Teks hover/pressed | #F4F7FA | #203F59 | 0,926567528 | 0,045833585 | 10,190243 | PASS | PASS |
| Label matahari | #FFD166 | #13283D | 0,678202377 | 0,019929526 | 10,413375 | PASS | PASS |
| Label air dan batas panel sisi dalam | #67E8F9 | #13283D | 0,674363433 | 0,019929526 | 10,358478 | PASS | PASS |
| Bahaya | #FF8E95 | #13283D | 0,427759282 | 0,019929526 | 6,832011 | PASS | PASS |
| Aman | #94F0B0 | #13283D | 0,717506653 | 0,019929526 | 10,975431 | PASS | PASS |
| Disabled | #9BAFC2 | #13283D | 0,415235486 | 0,019929526 | 6,652919 | PASS | PASS |
| Label tombol emas | #102033 | #FFD166 | 0,013821992 | 0,678202377 | 11,409897 | PASS | PASS |
| Jalur HUD dan batas panel sisi luar | #67E8F9 | #081322 | 0,674363433 | 0,006328618 | 12,859599 | PASS | PASS |
| Cincin fokus pada hover | #FFD166 | #203F59 | 0,678202377 | 0,045833585 | 7,598614 | PASS | PASS |
| Batas bahaya | #FF8E95 | #081322 | 0,427759282 | 0,006328618 | 8,481644 | PASS | PASS |
| Kandidat ditolak, dilarang digunakan | #66788A | #203F59 | 0,180927003 | 0,045833585 | 2,409667 | FAIL | FAIL |

Tabel adalah seluruh pasangan UI yang diizinkan. Cincin fokus tombol emas memakai warna teks #102033 di bagian dalam tombol; rasionya sama dengan label emas. Proyeksi jalur di dunia memakai pita opak #081322 dan garis #67E8F9, bukan garis transparan di atas tekstur. Ujung jangkar diberi papan kecil opak yang sama. Warna dekorasi dunia tidak dipakai sebagai satu-satunya informasi gameplay. Pasangan baru atau transparansi baru memerlukan hitungan ulang; tidak mewarisi PASS tabel ini.

## Kriteria penerimaan terukur dan gerbang

Semua status berikut NOT_RUN sampai ada build, versi, rekaman, dan log yang cocok. Pengukuran SPEC bukan hasil pengujian implementasi.

| Uji | Syarat PASS | Bukti yang disimpan saat implementasi |
|---|---|---|
| G0 struktur | DA independen menerima ceiling >=98, keenam jawaban dan sebab-akibat prototipe | Keputusan DA, rekaman satu perpindahan yang mengubah air, kawanan, dan puing |
| Core verb G3 | Tiga run menang lengkap, masing-masing keenam wilayah >=5 aksi sah; target desain >=6 | 18 hitungan wilayah, input dan bidang yang dilintasi, tanpa pengulangan buatan |
| Pilihan bermakna | Pada 12 persilangan sampel, koridor A/B berbeda minimal 8 energi atau 10 suhu atau satu puing aktif; minimal dua rute menang penuh ditemukan | Replay kedua cabang dengan keadaan awal sama |
| Anti-strategi tunggal | Ikuti protokol enam wilayah di bawah: kedua ekstrem GAGAL dan hanya strategi adaptif lolos | Jumlah selamat, E, waktu, skor, sebab kalah untuk semua kebijakan; NOT_RUN |
| Buntu energi | E=4, E=1, E=5 dengan tujuan belum tercapai: langsung game over pada pemeriksaan pertama, Luma membeku, tanpa pemulihan; ulangi setelah gerakan dan saat menunggu | Log dt, E, status tujuan dan layar KALAH; NOT_RUN |
| Fisika terbaca | 30 perpindahan uji tanpa puing baru: selisih posisi akhir pratinjau dan simulasi <=0,25 meter pada horizon 3 detik | Log posisi; keadaan awal identik |
| Ancaman earned | 100% puing lepas mempunyai perpindahan pemicu dengan q>=T; nol spawn timer | Log 100 pelepasan dan tes diam 60 detik dari keadaan awal |
| Dimensi | Minimal 2 persilangan per wilayah memerlukan sisi bawah/samping; meniadakan sumbu z membuat rute itu tidak dapat dimenangkan | Replay dan uji tabrakan varian datar |
| Dunia hidup | Rekaman 20 detik tanpa input pada keadaan air bergerak: air bergeser >=2 meter, 8 Luma bergeser/berputar, bayangan bergeser >=2 meter setelah input berikutnya | Rekaman dan log transform |
| Pembeda | >=4 dari 5 pengamat memenuhi tes screenshot 0,5 detik | Screenshot build dan jawaban asli |
| Kontras | Semua pasangan aktual sesuai tabel, teks >=4,5 dan UI penting >=3; nol kandidat FAIL terpakai | Sampling warna hasil render pada 1280x720 dan 1920x1080 |
| Pemahaman | >=4 dari 5 pemain baru menyelesaikan dua persilangan pertama dalam 120 detik tanpa bantuan lisan | Rekaman; teks tutorial maksimal 3 kartu x 12 kata |
| Performa | Pada Chrome, viewport 1280x720, CPU 4 inti 2,5 GHz dan GPU terintegrasi: persentil 95 waktu frame <=20 ms selama run; memori <=350 MB | Profil perangkat, rekaman profiler |
| Audio/keterbacaan | Seluruh alarm memiliki simbol dan hitung mundur; lima pemain dapat menemukan anggota terpisah dalam <=5 detik tanpa audio | Rekaman uji tanpa suara |
| Ketuntasan | Tiga run menang dan tiga run kalah mencapai layar hasil tanpa crash; checkpoint memulihkan keadaan identik | Versi build dan log checkpoint |
| G6 mutu | Blind Judge independen >=98 dengan bukti visual spesifik dan DA tanpa veto | Laporan penilai; bukan prediksi CEO |
| G7 kirim | Paket sesuai aturan best-game-01 yang sudah diverifikasi, persetujuan DA tertulis, tanda terima sebelum tenggat | ID dan waktu penerimaan |

Protokol anti-strategi: uji selalu pendek (selalu-pendek), selalu panjang (selalu-panjang), tunggu-muatan-nol, campuran tetap P-L-P-L-P-L beserta kebalikannya, dan strategi adaptif yang membaca E,H,q,d serta lintasan. Selalu panjang diuji dengan kontak air 0, 1, 2, 3, dan 4 detik, embun maksimum, tanpa tunggu tambahan; juga ulangi serangan DA pendinginan penuh lalu tunggu q=0. Kebijakan tunggu-muatan-nol memilih calon jangkar dengan biaya terkecil, menunggu semua puing terkunci yang terpengaruh menjadi q=0, lalu berpindah; jika kalah saat menunggu tetap dicatat. Kebijakan ekstrem boleh memilih waktu terbaik dan mengambil seluruh embun, tetapi tidak boleh mengganti jenis koridor. Campuran tetap tidak dianggap adaptif.

Di masing-masing enam wilayah mulai dari checkpoint yang sama: 12 Luma,E=100,H=0,q=0, seed 1701. Catat setiap persilangan dan hasil akhir: jumlah Luma selamat, E asli, detik simulasi termasuk menunggu, skor terkunci, dan sebab kalah. Run kalah memberi skor wilayah 0; simpan skor sementara terpisah tanpa menyebutnya kemenangan. Ulangi sebagai run enam wilayah agar reset energi tidak menyembunyikan kehilangan anggota. Semua sel hasil masih NOT_RUN, tidak diisi angka kemenangan rekaan.

PASS hanya bila pada setiap wilayah selalu pendek DAN selalu panjang GAGAL (kurang dari 8 dapat diselamatkan atau run KALAH), kebijakan tunggu-muatan-nol dan kedua campuran tetap juga gagal, sedangkan tiga run independen adaptif menang seluruh enam wilayah dengan >=8 Luma dan E>=6 sampai tujuan tercapai. Bandingkan keempat ukuran secara berdampingan; skor rendah atau energi lebih boros saja tidak menghitung ekstrem sebagai gagal. Jika satu ekstrem, penantian, atau campuran tetap menang, tes FAIL dan tata hubungan harus didesain ulang. Bukti selalu pendek gagal dari puing masih NOT_RUN; hitungan energi selalu panjang tidak dipakai untuk mengarang hasil pendek. Tes anti-strategi gagal bila semua koridor menang dengan keputusan sama tanpa perbedaan akibat. Itu DESAIN: ubah hubungan ruang dan sumber bahaya, bukan menambah efek partikel. Core verb gagal bila pemain sekadar menekan enam jangkar tanpa membaca akibat; frekuensi saja tidak meluluskan kedalaman.

## Lingkup, biaya, dan pengendalian

Anggaran pekerjaan terfokus: prototipe sebab-akibat 90 menit; loop ekspedisi/keadaan/skor 120 menit; enam wilayah 150 menit; visual/UX/audio 150 menit; pengujian independen dan integrasi 150 menit; validasi paket 60 menit. Total 720 menit, tidak mencakup waktu tunggu layanan. Batas scope: 12 Luma, satu jenis puing dengan ukuran berbeda, satu jenis air, 36 persilangan, satu matahari. Enam wilayah memakai tata hubungan berbeda, bukan enam skin.

| Sistem/fitur | Keputusan yang dilayani | Bukti yang dituntut | Biaya | Hubungan dengan bar 98 |
|---|---|---|---:|---|
| Medan gravitasi bersama | Pilih tarikan yang memindahkan kawanan sekaligus menata bahaya | Replay air/Luma/puing merespons input sama | 90 menit | Dasar struktur baru; gagal berarti desain ditolak |
| Energi, suhu, muatan, skor, checkpoint | Pilih cepat, dingin, atau pemulihan | Contoh hitung cocok log dan hasil | 120 menit | Menutup eksploit menunggu dan hadiah berulang |
| Enam wilayah | Baca sisi ruang dan konsekuensi rute | Uji dua rute dan anti-strategi tunggal | 150 menit | Kedalaman harus terbukti di luar tutorial |
| Cahaya, karakter, UI, audio | Baca arah dan akibat dalam satu pandang | Tes 0,5 detik, kontras, tanpa audio | 150 menit | Mengkomunikasikan struktur, bukan menutup kekurangan |
| Audit dan integrasi | Putuskan layak lanjut atau redesain | Tiga run, Red Team, Judge terpisah | 150 menit | Menentukan bar nyata tanpa klaim sendiri |
| Paket | Putuskan kelayakan pengiriman | Dry run aturan kompetisi dan tanda terima | 60 menit | Hasil harus dapat dimainkan penilai |

Urutan wajib: G0 berbukti, G1 hitungan SPEC diterima DA, G2 tool best-game-01 diuji, lalu komitmen produksi. Tidak ada nama tool atau kesiapan kompetisi yang diklaim telah terverifikasi di dokumen ini. Gerbang G3 core verb mendahului investasi poles besar. G4 mengunci poles selama kritik DESAIN terbuka. G5 mencatat S0,S1,S2: bila S2-S0<=1 setelah dua siklus, BERHENTI; contoh 96→97→97 berhenti. Tidak menghapus skor, mengganti penilai untuk reset hitungan, atau meneruskan Fix tanpa persetujuan DA tertulis setelah review struktur.

Pemilik saat produksi harus ditetapkan: integrasi, desain, teknik, visual/UX, DA, penguji/Red Team. Penyusun tidak berperan sebagai DA independen atau Blind Judge atas hasil sendiri. Penugasan agen tidak dilakukan dalam tugas penulisan ini. Semua kritik memiliki ID, bukti reproduksi, kategori DESAIN/POLES, pemilik, dan angka penutupan. Target build final 18 November 14:00 UTC; bila G6/G7 gagal, tidak submit. Nilai 95–97 tetap ditolak. Skor target tidak dimasukkan ke instruksi Blind Judge.

## Phase 0 Audit

1. **Ceiling: TARGET DESAIN minimal 98/100 BELUM TERBUKTI.** DA terakhir REJECT dengan ceiling 96. Hubungan energi–waktu direvisi untuk audit ulang; angka rancangan tidak membuktikan kedalaman atau mutu produk. Prototipe NOT_RUN, lima pengamatan NOT_RUN, tiga run NOT_RUN; tidak ada bukti G0 PASS dan tidak ada izin produksi.
2. **Dunia hidup: 7/10 sebagai skor desain belum terbukti.** Dua belas Luma mencari pijakan dan saling menghindar, air dan puing terus mengikuti medan, cahaya serta bayangan berpindah bersama matahari. Bukti wajib: rekaman diam 20 detik dan perubahan sesudah satu input; implementasi NOT_RUN.
3. **Ancaman-diperoleh: 8/10 sebagai skor desain belum terbukti.** Setiap puing aktif wajib berasal dari muatan yang dihitung dari sudut, jarak, dan suhu akibat perpindahan pilihan pemain. Tidak ada spawn timer, gelombang, atau bos. Bukti wajib: 100% log pelepasan mempunyai sebab; implementasi NOT_RUN.
4. **Dimensi nyata? YA pada aturan.** Mesh tiga sumbu, perbedaan tinggi 6–12 meter, lantai menjadi dinding, dan rute bawah mengubah tabrakan serta akses. Minimal dua persilangan per wilayah gagal bila z dihapus; implementasi NOT_RUN.
5. **Pembeda 0,5 detik? YA sebagai sasaran teruji.** Matahari yang dipindahkan, air melengkung, dan kawanan di bawah pulau berada dalam satu screenshot gameplay. PASS hanya bila minimal empat dari lima pengamat menunjuk hubungan itu setelah paparan 0,5 detik. Pengujian NOT_RUN; studi visual langsung LANTERNWAKE UNKNOWN.
6. **Core verb minimal lima kali per sesi? YA pada struktur.** Memindahkan pusat gravitasi memindahkan kawanan melewati enam persilangan per wilayah; input tanpa perubahan akses tidak dihitung. Target 6–10, batas audit min(c1,...,c6)>=5 pada masing-masing tiga run menang normal. Pengujian NOT_RUN. Keputusan akhir: ceiling TARGET DESAIN minimal 98/100 BELUM TERBUKTI; G0 belum PASS, produksi dan submit tidak diizinkan sebelum bukti dan keputusan DA independen tersedia.

## Perbaikan dari DA

1. Rute panjang: memilih tepat satu aturan baru, energi bersama turun 0,9 per detik; menetapkan batas kemajuan 0,9 meter/detik, menghitung ulang serangan DA hingga kalah sebelum embun kelima, dan mengganti tes satu ekstrem dengan tes kedua ekstrem, tunggu muatan nol, campuran tetap, serta adaptif di enam wilayah. Alasannya, pendinginan, jarak aman puing, dan penantian sebelumnya bisa dibeli tanpa biaya kelangsungan hidup. Kenaikan H diselaraskan menjadi θ/15; biaya, pendinginan 6 per detik maksimal 4 detik, dan ambang wilayah tetap sesuai rumus yang diminta.
2. Kalah tersangkut: mengganti tenggang energi nol dengan E<6 saat tujuan belum tercapai, pemeriksaan setelah gerakan dan tiap detik menunggu serta tiap dt, pembekuan Luma, pesan pemain, dan tes E=4,1,5. Alasannya, energi bersama sebesar 1–5 tidak membayar gerakan termurah dan tidak boleh meninggalkan run tanpa penyelesaian.
3. Ceiling jujur: menghapus penetapan ceiling tinggi sebagai kesimpulan, mencatat target minimal 98 BELUM TERBUKTI, putusan DA 96 tetap REJECT, semua bukti NOT_RUN, G0 belum PASS, dan larangan produksi. Skor dunia-hidup 7/10 serta ancaman-diperoleh 8/10 dipertahankan sebagai skor desain belum terbukti. Seluruh bagian WCAG dipertahankan persis: 14 rasio, 13 pasangan lolos 4,5:1, kandidat 2,409667 GAGAL dan dilarang. Alasannya, hitungan dokumen bukan hasil prototipe, pengamatan, run, atau izin DA.

Batas audit ulang: revisi ini siap dibaca DA sebagai dokumen, bukan klaim semua veto tertutup. Detail dorongan air/TAHAN, urutan pelepasan, pratinjau dengan puing baru, bukti dunia hidup, showcase dan studi lawan yang diminta putusan DA tetap memerlukan penyelesaian serta bukti prototipe; tidak dinyatakan PASS.
