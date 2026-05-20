<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Poppins', Arial, sans-serif;
            background-color: #f5f8fa;
            color: #000000;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            min-height: 100vh;
        }

        .mobile-container {
            width: 100%;
            max-width: 480px;
            background-color: #ffffff;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            position: relative;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.05);
        }

        /* Header Biru Muda - Tempat Logo */
        header {
            background-color: #00a2e8;
            height: 60px;
            width: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 5px 0;
        }

        header img {
            height: 44px;
            width: auto;
            object-fit: contain;
        }

        main {
            flex: 1;
            padding: 15px 12px 65px 12px;
        }

        /* Card Utama Dokumen Sign */
        .card {
            background-color: #ffffff;
            border: 1px solid #c2d1d9;
            border-top: 4px solid #004d61;
            border-radius: 4px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
        }

        .card-header {
            padding: 14px 16px;
            font-size: 15px;
            font-weight: 700;
            color: #111111;
            border-bottom: 1px solid #c2d1d9;
        }

        .card-body {
            padding: 16px;
        }

        .data-group {
            margin-bottom: 16px;
        }

        .data-group:last-child {
            margin-bottom: 0;
        }

        .label {
            font-weight: 700;
            font-size: 14.5px;
            color: #111111;
            display: block;
            margin-bottom: 2px;
        }

        .value {
            font-size: 14px;
            color: #333333;
            line-height: 1.45;
            display: block;
            word-wrap: break-word;
        }

        /* Badge Belum Dibaca Orange */
        .badge-orange {
            display: inline-block;
            background-color: #e65100;
            color: #ffffff;
            font-size: 10px;
            font-weight: 700;
            padding: 2px 10px;
            border-radius: 10px;
            margin-top: 5px;
            margin-bottom: 2px;
            text-transform: uppercase;
        }

        /* Link Biru */
        .link-blue {
            color: #0066cc;
            font-size: 13.5px;
            text-decoration: none;
            font-weight: 600;
            display: inline-block;
            cursor: pointer;
            transition: color 0.2s ease;
        }

        .link-blue:hover {
            color: #004499;
            text-decoration: underline;
        }

        /* Dropdown Konten */
        .dropdown-content {
            max-height: 0;
            overflow: hidden;
            opacity: 0;
            transition: max-height 0.3s ease-in-out, opacity 0.2s ease-in-out;
        }

        .dropdown-content.show {
            max-height: 40px;
            opacity: 1;
        }

        .additional-name {
            font-size: 14px;
            color: #333333;
            padding-top: 4px;
        }

        /* Footer Hijau Tua */
        footer {
            background-color: #004d61;
            color: #ffffff;
            text-align: right;
            padding: 10px 16px;
            font-size: 11px;
            font-weight: 700;
            position: absolute;
            bottom: 0;
            width: 100%;
        }
    </style>
</head>
<body>

    <div class="mobile-container">
        <header>
            <img src="https://uploads.onecompiler.io/44pr7j5c8/44pr693cp/Logo_of_Ministry_of_Education_and_Culture_of_Republic_of_Indonesia.svg.png" alt="Logo Tut Wuri Handayani">
        </header>

        <main>
            <div class="card">
                <div class="card-header">Dokumen Sign</div>
                
                <div class="card-body">
                    <div class="data-group">
                        <span class="label">Tanggal Surat</span>
                        <span class="value">: 11 Mei 2026</span>
                    </div>

                    <div class="data-group">
                        <span class="label">Penanda Tangan</span>
                        <span class="value">: Moch. Salim Somad, S.Kom., M.Pd - <br>&nbsp; Direktur Sekolah Dasar, Kemendikdasmen</span>
                    </div>

                    <div class="data-group">
                        <span class="label">Hal</span>
                        <span class="value">: Surat panggilan klarifikasi dugaan penyalahgunaan Anggaran revitalisasi SD Tahun 2025</span>
                    </div>

                    <div class="data-group">
                        <span class="label">Unit Kerja/Unit Pengolah</span>
                        <span class="value">: Moch. Salim Somad, S.Kom., M.Pd - <br>&nbsp; Direktur Sekolah Dasar, Kemendikdasmen</span>
                    </div>

                    <div class="data-group">
                        <span class="label">Kepada/Tujuan</span>
                        <div class="value">
                            : David Eka Wardoyo, S.Psi
                            <div><span class="badge-orange">Belum dibaca</span></div>
                            <span class="link-blue" id="dropdownBtn" onclick="toggleDropdown()">1+ Lainnya &gt;</span>
                            
                            <div class="dropdown-content" id="dropdownContainer">
                                <div class="additional-name">: Alviona Zalsabila</div>
                            </div>
                        </div>
                    </div>

                    <div class="data-group">
                        <span class="label">Lampiran</span>
                        <span class="value">: Akses lampiran tidak dapat dilihat publik</span>
                    </div>
                </div>
            </div>
        </main>

        <footer>
            SINDE - 2023 :S2
        </footer>
    </div>

    <script>
        function toggleDropdown() {
            var container = document.getElementById("dropdownContainer");
            var btn = document.getElementById("dropdownBtn");
            
            if (container.classList.contains("show")) {
                container.classList.remove("show");
                btn.innerHTML = "1+ Lainnya &gt;";
            } else {
                container.classList.add("show");
                btn.innerHTML = "Sembunyikan &lt;";
            }
        }
    </script>

</body>
</html>
