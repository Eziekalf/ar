graph TD
    %% Warna dan Style
    classDef public fill:#e1f5fe,stroke:#0288d1,stroke-width:2px;
    classDef admin fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px;
    classDef staff fill:#e8f5e9,stroke:#388e3c,stroke-width:2px;

    %% Modul Publik
    A[🏠 Beranda / Home] ::: public
    A --> B(🔍 Eksplorasi Konser) ::: public
    A --> C(👤 Akun & Tiket Saya) ::: public
    
    B --> B1(Detail Event & Playlist) ::: public
    B1 --> B2{Waiting Room / Antrean} ::: public
    B2 --> B3(Seat Map & Kategori) ::: public
    B3 --> B4(Checkout & Timer) ::: public
    B4 --> B5((Payment Gateway)) ::: public

    C --> C1(E-Ticket / QR Code) ::: public
    C --> C2(Riwayat Transaksi) ::: public

    %% Modul Promotor (B2B)
    P[📈 Login Promotor] ::: admin
    P --> P1(Dashboard Analytics) ::: admin
    P1 --> P2(Buat Event & Seat Builder) ::: admin
    P1 --> P3(Manajemen Promo) ::: admin
    P1 --> P4(Tarik Dana / Withdrawal) ::: admin

    %% Modul Staff Lapangan
    S[📱 Login Staff Gate] ::: staff
    S --> S1(Kamera Scanner QR) ::: staff
    S1 --> S2{Validasi Database} ::: staff
    S2 -- Valid --> S3(Indikator Hijau + Log) ::: staff
    S2 -- Invalid --> S4(Indikator Merah / Ditolak) ::: staff
    S --> S5(Manual Check-in NIK) ::: staff
