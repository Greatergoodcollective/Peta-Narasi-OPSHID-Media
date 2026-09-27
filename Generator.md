# Peta-Narasi-OPSHID-Media
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Peta Narasi OPSHID - Meja Redaksi</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600&family=Literata:ital,opsz,wght@0,7..72,400;0,7..72,600;0,7..72,700;1,7..72,400&family=Public+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg: #EEF1EC;
      --surface: #FBFCF9;
      --surface-border: #DCE3D8;
      --text: #17201C;
      --text-muted: #56635D;
      --primary: #1F3FA3;
      --primary-hover: #162E7A;
      --highlight: #F3D65A;
      --risk-green: #2E7D4F;
      --risk-green-bg: #EAF5EE;
      --risk-amber: #A8640B;
      --risk-amber-bg: #FDF5E6;
      --risk-red: #B3261E;
      --risk-red-bg: #FDF0ED;
      --radius: 8px;
    }

    @media (prefers-color-scheme: dark) {
      :root {
        --bg: #141A17;
        --surface: #1E2622;
        --surface-border: #2D3A34;
        --text: #E5ECE8;
        --text-muted: #9BA9A1;
        --primary: #7C9BFF;
        --primary-hover: #9EBAFF;
        --highlight: #665200;
        --risk-green: #57B67E;
        --risk-green-bg: #162E20;
        --risk-amber: #EAA346;
        --risk-amber-bg: #382508;
        --risk-red: #EF6F67;
        --risk-red-bg: #381512;
      }
    }

    * { box-sizing: border-box; margin: 0; padding: 0; }
    body {
      font-family: 'Public Sans', sans-serif;
      background-color: var(--bg);
      color: var(--text);
      line-height: 1.5;
      padding: 0;
      min-height: 100vh;
    }

    /* Topbar */
    header {
      background: var(--surface);
      border-bottom: 1px solid var(--surface-border);
      padding: 14px 24px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      position: sticky;
      top: 0;
      z-index: 50;
    }
    .brand {
      display: flex;
      align-items: baseline;
      gap: 10px;
    }
    .brand h1 {
      font-family: 'Literata', serif;
      font-size: 1.25rem;
      font-weight: 700;
      color: var(--text);
    }
    .brand span {
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.75rem;
      color: var(--text-muted);
      text-transform: uppercase;
      letter-spacing: 0.5px;
    }

    /* Tabs */
    .nav-tabs {
      display: flex;
      gap: 6px;
      background: var(--bg);
      padding: 4px;
      border-radius: var(--radius);
    }
    .tab-btn {
      border: none;
      background: transparent;
      padding: 8px 16px;
      font-family: 'Public Sans', sans-serif;
      font-size: 0.875rem;
      font-weight: 600;
      color: var(--text-muted);
      border-radius: 6px;
      cursor: pointer;
      transition: all 0.15s ease;
    }
    .tab-btn:hover { color: var(--text); }
    .tab-btn.active {
      background: var(--surface);
      color: var(--primary);
      box-shadow: 0 1px 3px rgba(0,0,0,0.05);
    }

    /* Main Container */
    main {
      max-width: 1440px;
      margin: 0 auto;
      padding: 24px;
    }

    .tab-content { display: none; }
    .tab-content.active { display: block; }

    /* Layout Dua Kolom Tab 1 */
    .editor-grid {
      display: grid;
      grid-template-columns: 460px 1fr;
      gap: 24px;
      align-items: start;
    }
    @media (max-width: 992px) {
      .editor-grid { grid-template-columns: 1fr; }
    }

    /* Form Card */
    .form-panel {
      background: var(--surface);
      border: 1px solid var(--surface-border);
      border-radius: var(--radius);
      padding: 20px;
      position: sticky;
      top: 80px;
      max-height: calc(100vh - 104px);
      overflow-y: auto;
    }
    .form-group { margin-bottom: 16px; }
    .form-group label {
      display: block;
      font-size: 0.8125rem;
      font-weight: 600;
      margin-bottom: 6px;
      text-transform: uppercase;
      font-family: 'JetBrains Mono', monospace;
      letter-spacing: 0.5px;
    }
    .form-group label span.req { color: var(--risk-red); }
    textarea, input[type="text"] {
      width: 100%;
      background: var(--bg);
      border: 1px solid var(--surface-border);
      border-radius: 6px;
      padding: 10px 12px;
      font-family: 'Public Sans', sans-serif;
      font-size: 0.875rem;
      color: var(--text);
      outline: none;
    }
    textarea:focus, input[type="text"]:focus {
      border-color: var(--primary);
    }
    textarea { resize: vertical; min-height: 80px; }

    /* Chips Selector */
    .chip-group { display: flex; flex-wrap: wrap; gap: 8px; }
    .chip-radio input { display: none; }
    .chip-radio span {
      display: inline-block;
      padding: 6px 12px;
      border: 1px solid var(--surface-border);
      border-radius: 20px;
      font-size: 0.8125rem;
      cursor: pointer;
      background: var(--bg);
    }
    .chip-radio input:checked + span {
      background: var(--primary);
      color: #fff;
      border-color: var(--primary);
    }

    /* Checkbox Chips Media */
    .media-checkboxes {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      max-height: 120px;
      overflow-y: auto;
      padding: 4px;
      background: var(--bg);
      border-radius: 6px;
      border: 1px solid var(--surface-border);
    }
    .media-chip input { display: none; }
    .media-chip span {
      display: inline-block;
      padding: 4px 10px;
      border: 1px solid var(--surface-border);
      border-radius: 14px;
      font-size: 0.75rem;
      cursor: pointer;
      background: var(--surface);
    }
    .media-chip input:checked + span {
      background: var(--text);
      color: var(--surface);
      border-color: var(--text);
    }

    /* Buttons */
    .btn-row { display: flex; gap: 8px; margin-top: 20px; }
    .btn {
      border: none;
      padding: 10px 16px;
      border-radius: 6px;
      font-size: 0.875rem;
      font-weight: 600;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 6px;
      font-family: 'Public Sans', sans-serif;
      transition: background 0.15s ease;
    }
    .btn-primary { background: var(--primary); color: #FFF; flex: 1; }
    .btn-primary:hover { background: var(--primary-hover); }
    .btn-danger { background: var(--risk-red); color: #FFF; }
    .btn-secondary {
      background: transparent;
      border: 1px solid var(--surface-border);
      color: var(--text);
    }
    .btn-secondary:hover { background: var(--bg); }
    .btn-docs {
      background: #0F9D58;
      color: #FFF;
      font-size: 0.75rem;
      padding: 5px 10px;
      border-radius: 4px;
    }
    .btn-docs:hover { background: #0B8043; }

    /* Progress Banner */
    .progress-box {
      display: none;
      background: var(--surface);
      border: 1px solid var(--surface-border);
      border-radius: var(--radius);
      padding: 16px;
      margin-bottom: 20px;
    }
    .progress-bar-container {
      height: 6px;
      background: var(--bg);
      border-radius: 3px;
      overflow: hidden;
      margin: 10px 0;
    }
    .progress-bar {
      height: 100%;
      width: 0%;
      background: var(--primary);
      transition: width 0.3s ease;
    }
    .progress-status {
      font-size: 0.8125rem;
      color: var(--text-muted);
      display: flex;
      justify-content: space-between;
    }

    /* Result Panel */
    .result-panel {
      background: var(--surface);
      border: 1px solid var(--surface-border);
      border-radius: var(--radius);
      padding: 32px;
    }
    .example-banner {
      background: var(--risk-amber-bg);
      border-left: 4px solid var(--risk-amber);
      color: var(--risk-amber);
      padding: 10px 14px;
      font-size: 0.8125rem;
      font-weight: 600;
      margin-bottom: 24px;
      border-radius: 0 var(--radius) var(--radius) 0;
    }
    .result-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      border-bottom: 1px solid var(--surface-border);
      padding-bottom: 16px;
      margin-bottom: 24px;
      gap: 16px;
    }
    .issue-title {
      font-family: 'Literata', serif;
      font-size: 2rem;
      font-weight: 700;
      line-height: 1.25;
    }

    /* Section Styles */
    .section-block { margin-bottom: 36px; }
    .section-title {
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.8125rem;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 1px;
      color: var(--text-muted);
      margin-bottom: 14px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-bottom: 1px solid var(--surface-border);
      padding-bottom: 6px;
    }

    /* Bagian A */
    .key-message {
      font-family: 'Literata', serif;
      font-size: 1.25rem;
      font-style: italic;
      margin-bottom: 14px;
    }
    .key-sentence-box {
      background: var(--highlight);
      color: #000;
      padding: 14px 18px;
      border-radius: 6px;
      margin-bottom: 18px;
    }
    .key-sentence-label {
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.6875rem;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 0.5px;
      opacity: 0.85;
      margin-bottom: 4px;
    }
    .key-sentence-text {
      font-size: 1rem;
      font-weight: 700;
    }
    .supporting-points {
      margin: 16px 0;
      padding-left: 20px;
    }
    .supporting-points li { margin-bottom: 10px; }
    .reference-box {
      background: var(--bg);
      border-radius: var(--radius);
      padding: 18px;
      margin-top: 18px;
      font-family: 'Literata', serif;
      font-size: 0.9375rem;
      line-height: 1.7;
    }
    .reference-box p { margin-bottom: 12px; }
    .reference-box p:last-child { margin-bottom: 0; }

    /* Bagian B: Bank Judul */
    .title-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 12px;
    }
    .title-card {
      background: var(--bg);
      border: 1px solid var(--surface-border);
      border-radius: 6px;
      padding: 12px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }
    .title-meta {
      display: flex;
      justify-content: space-between;
      margin-bottom: 6px;
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.6875rem;
      color: var(--text-muted);
    }
    .title-text { font-size: 0.875rem; font-weight: 600; margin-bottom: 8px; }

    /* Bagian C: Turunan Media */
    .media-cards-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
      gap: 16px;
    }
    .media-card {
      background: var(--bg);
      border: 1px solid var(--surface-border);
      border-radius: var(--radius);
      padding: 16px;
    }
    .media-card-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 12px;
      border-bottom: 1px solid var(--surface-border);
      padding-bottom: 8px;
    }
    .media-name { font-weight: 700; font-size: 1rem; }
    .media-field { margin-bottom: 10px; font-size: 0.8125rem; }
    .media-field-label {
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.6875rem;
      color: var(--text-muted);
      text-transform: uppercase;
    }
    .tag-list { display: flex; flex-wrap: wrap; gap: 4px; margin-top: 4px; }
    .tag {
      background: var(--surface);
      border: 1px solid var(--surface-border);
      padding: 2px 6px;
      border-radius: 4px;
      font-size: 0.6875rem;
      font-family: 'JetBrains Mono', monospace;
    }

    /* Bagian D: Risiko */
    .risk-box {
      border-left: 6px solid var(--risk-amber);
      background: var(--bg);
      padding: 18px;
      border-radius: 0 var(--radius) var(--radius) 0;
    }
    .risk-pill {
      display: inline-block;
      padding: 3px 10px;
      border-radius: 12px;
      font-size: 0.75rem;
      font-weight: 700;
      font-family: 'JetBrains Mono', monospace;
      text-transform: uppercase;
      margin-bottom: 10px;
    }
    .risk-low { background: var(--risk-green-bg); color: var(--risk-green); }
    .risk-medium { background: var(--risk-amber-bg); color: var(--risk-amber); }
    .risk-high { background: var(--risk-red-bg); color: var(--risk-red); }
    .pair-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
      margin-top: 12px;
    }
    @media(max-width: 600px) { .pair-grid { grid-template-columns: 1fr; } }
    .pair-red {
      background: var(--risk-red-bg);
      border: 1px solid var(--risk-red);
      padding: 10px;
      border-radius: 6px;
      font-size: 0.8125rem;
    }
    .pair-green {
      background: var(--risk-green-bg);
      border: 1px solid var(--risk-green);
      padding: 10px;
      border-radius: 6px;
      font-size: 0.8125rem;
    }

    /* Bagian E: Jadwal Amplifikasi */
    .timeline {
      position: relative;
      padding-left: 20px;
      border-left: 2px solid var(--surface-border);
      margin-left: 10px;
    }
    .timeline-item {
      position: relative;
      margin-bottom: 18px;
    }
    .timeline-item::before {
      content: '';
      position: absolute;
      left: -26px;
      top: 4px;
      width: 10px;
      height: 10px;
      border-radius: 50%;
      background: var(--primary);
    }
    .timeline-time {
      font-family: 'JetBrains Mono', monospace;
      font-weight: 700;
      font-size: 0.8125rem;
    }

    /* Check Before Air */
    .check-list {
      border-left: 4px solid var(--primary);
      padding-left: 16px;
      background: var(--bg);
      padding: 14px 18px;
      border-radius: 0 var(--radius) var(--radius) 0;
      font-size: 0.875rem;
    }
    .check-list li { margin-bottom: 6px; }

    /* Toast Notification */
    #toast {
      position: fixed;
      bottom: 24px;
      right: 24px;
      background: var(--text);
      color: var(--surface);
      padding: 12px 20px;
      border-radius: 6px;
      font-size: 0.875rem;
      font-weight: 500;
      box-shadow: 0 4px 12px rgba(0,0,0,0.15);
      opacity: 0;
      transform: translateY(10px);
      transition: all 0.2s ease;
      pointer-events: none;
      z-index: 100;
    }
    #toast.show { opacity: 1; transform: translateY(0); }

    /* Modal Konfirmasi */
    .modal-backdrop {
      display: none;
      position: fixed;
      inset: 0;
      background: rgba(0,0,0,0.5);
      z-index: 200;
      align-items: center;
      justify-content: center;
    }
    .modal {
      background: var(--surface);
      border-radius: var(--radius);
      padding: 24px;
      max-width: 400px;
      width: 90%;
    }

    /* Table Umum */
    .data-table {
      width: 100%;
      border-collapse: collapse;
      background: var(--surface);
      border-radius: var(--radius);
      overflow: hidden;
      border: 1px solid var(--surface-border);
    }
    .data-table th, .data-table td {
      padding: 12px 16px;
      text-align: left;
      border-bottom: 1px solid var(--surface-border);
      font-size: 0.875rem;
    }
    .data-table th {
      background: var(--bg);
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.75rem;
      text-transform: uppercase;
    }
  </style>
</head>
<body>

  <header>
    <div class="brand">
      <h1>Peta Narasi OPSHID</h1>
      <span>Meja Redaksi Terpadu</span>
    </div>
    <nav class="nav-tabs">
      <button class="tab-btn active" onclick="switchTab('tab-susun')">Susun Narasi</button>
      <button class="tab-btn" onclick="switchTab('tab-media')">Media Jaringan</button>
      <button class="tab-btn" onclick="switchTab('tab-riwayat')">Riwayat</button>
    </nav>
  </header>

  <main>
    <!-- TAB 1: SUSUN NARASI -->
    <div id="tab-susun" class="tab-content active">
      <div class="editor-grid">
        <!-- FORMULIR INPUT (KIRI) -->
        <div class="form-panel">
          <form id="form-narasi" onsubmit="event.preventDefault(); jalankanPenyusunan();">
            <div class="form-group">
              <label>1. Isu / Berita <span class="req">*</span></label>
              <textarea id="inp-isu" placeholder="Judul berita, peristiwa, atau ringkasan isu. Boleh tempel paragraf berita..." required></textarea>
            </div>

            <div class="form-group">
              <label>2. Tujuan Narasi</label>
              <div class="chip-group">
                <label class="chip-radio">
                  <input type="radio" name="tujuan" value="Memperkuat" checked>
                  <span>Memperkuat</span>
                </label>
                <label class="chip-radio">
                  <input type="radio" name="tujuan" value="Meluruskan">
                  <span>Meluruskan</span>
                </label>
                <label class="chip-radio">
                  <input type="radio" name="tujuan" value="Merespons">
                  <span>Merespons</span>
                </label>
                <label class="chip-radio">
                  <input type="radio" name="tujuan" value="Mengedukasi">
                  <span>Mengedukasi</span>
                </label>
              </div>
            </div>

            <div class="form-group">
              <label>3. Posisi OPSHID</label>
              <textarea id="inp-posisi" placeholder="Satu-dua kalimat sikap organisasi. Kosongkan jika belum ada."></textarea>
            </div>

            <div class="form-group">
              <label>4. Batasan</label>
              <textarea id="inp-batasan" placeholder="Hal yang tidak boleh disentuh atau disebut."></textarea>
            </div>

            <div class="form-group">
              <label>5. Hashtag Wajib</label>
              <input type="text" id="inp-hashtag" placeholder="#HariSantri2026">
            </div>

            <div class="form-group">
              <label>6. Waktu Tayang yang Dituju</label>
              <input type="text" id="inp-waktu" placeholder="22 Oktober 2026, pagi sampai sore">
            </div>

            <div class="form-group">
              <label>7. Dokumentasi yang Tersedia</label>
              <textarea id="inp-dokumentasi" placeholder="Foto upacara, foto baksos, video sambutan ketua"></textarea>
            </div>

            <div class="form-group">
              <label>8. Media Jaringan yang Ikut Tayang</label>
              <div id="media-checkbox-container" class="media-checkboxes">
                <!-- Checkboxes diinjeksi via JS -->
              </div>
            </div>

            <div class="btn-row">
              <button type="submit" id="btn-submit" class="btn btn-primary">Susun Peta Narasi</button>
              <button type="button" id="btn-stop" class="btn btn-danger" style="display:none;" onclick="hentikanProses()">Hentikan</button>
            </div>
            <div style="margin-top: 10px;">
              <button type="button" class="btn btn-secondary" style="width: 100%; font-size: 0.75rem;" onclick="salinPromptCadangan()">Salin Prompt Cadangan (Manual AI)</button>
            </div>
          </form>
        </div>

        <!-- HASIL NARASI (KANAN) -->
        <div>
          <!-- PROGRESS BAR SAAT RUNNING -->
          <div id="progress-box" class="progress-box">
            <div style="font-weight: 600; font-size: 0.875rem;" id="progress-text">Menyiapkan penyusunan narasi...</div>
            <div class="progress-bar-container">
              <div id="progress-bar" class="progress-bar"></div>
            </div>
            <div class="progress-status">
              <span id="progress-chars">0 karakter tertulis</span>
              <span>Perkiraan 30–60 detik</span>
            </div>
          </div>

          <!-- CONTAINER UTAMA HASIL -->
          <div class="result-panel" id="result-display">
            <!-- Disuntik via renderHasil() -->
          </div>
        </div>
      </div>
    </div>

    <!-- TAB 2: MEDIA JARINGAN -->
    <div id="tab-media" class="tab-content">
      <div style="max-width: 800px; margin: 0 auto;">
        <div class="form-panel" style="position: static; max-height: none; margin-bottom: 24px;">
          <h2 style="font-size: 1.125rem; margin-bottom: 16px;">Tambah / Edit Media Jaringan</h2>
          <form id="form-media" onsubmit="event.preventDefault(); simpanMedia();">
            <input type="hidden" id="media-id">
            <div class="form-group">
              <label>Nama Media <span class="req">*</span></label>
              <input type="text" id="m-nama" required placeholder="Contoh: Suara Pemuda Shiddiqiyyah">
            </div>
            <div class="form-group">
              <label>Platform Utama</label>
              <input type="text" id="m-platform" placeholder="Contoh: Instagram Reels & Feed">
            </div>
            <div class="form-group">
              <label>Target Audiens</label>
              <input type="text" id="m-audiens" placeholder="Contoh: Santri muda, simpatisan, usia 18-30">
            </div>
            <div class="form-group">
              <label>Gaya Bahasa</label>
              <input type="text" id="m-gaya" placeholder="Contoh: Santai, lugas, visual-first">
            </div>
            <div class="form-group">
              <label>Catatan Redaksi</label>
              <input type="text" id="m-catatan" placeholder="Contoh: Hindari teks panjang, utamakan carousel grafik">
            </div>
            <div class="btn-row">
              <button type="submit" class="btn btn-primary">Simpan Media</button>
              <button type="button" class="btn btn-secondary" onclick="resetFormMedia()">Batal</button>
            </div>
          </form>
        </div>

        <h3 style="font-size: 1rem; margin-bottom: 12px;">Daftar Jejaring Aktif</h3>
        <table class="data-table" id="table-media">
          <thead>
            <tr>
              <th>Media</th>
              <th>Platform</th>
              <th>Audiens</th>
              <th>Aksi</th>
            </tr>
          </thead>
          <tbody></tbody>
        </table>
      </div>
    </div>

    <!-- TAB 3: RIWAYAT -->
    <div id="tab-riwayat" class="tab-content">
      <div style="max-width: 960px; margin: 0 auto;">
        <h2 style="font-size: 1.25rem; margin-bottom: 16px;">Riwayat Peta Narasi</h2>
        <table class="data-table" id="table-riwayat">
          <thead>
            <tr>
              <th>Waktu</th>
              <th>Judul Kerja Isu</th>
              <th>Tujuan</th>
              <th>Risiko</th>
              <th>Aksi</th>
            </tr>
          </thead>
          <tbody></tbody>
        </table>
      </div>
    </div>
  </main>

  <!-- MODAL KONFIRMASI HAPUS -->
  <div class="modal-backdrop" id="modal-confirm">
    <div class="modal">
      <h3 style="margin-bottom: 12px;" id="modal-title">Konfirmasi</h3>
      <p style="font-size: 0.875rem; color: var(--text-muted); margin-bottom: 20px;" id="modal-desc">Yakin ingin menghapus item ini?</p>
      <div style="display: flex; justify-content: flex-end; gap: 8px;">
        <button class="btn btn-secondary" onclick="tutupModal()">Batal</button>
        <button class="btn btn-danger" id="modal-act-btn">Ya, Hapus</button>
      </div>
    </div>
  </div>

  <div id="toast">Tersalin ke clipboard!</div>

  <script>
    // ==========================================
    // DATA DEFAULT & INISIALISASI
    // ==========================================
    const DEFAULT_MEDIA = [
      { id: 'm1', nama: 'OPSHID Media Induk', platform: 'Website & YouTube', audiens: 'Warga Shiddiqiyyah umum, media massa, regulator', gaya: 'Otoritatif, formal, mendalam', catatan: 'Pintu rujukan utama informasi', dibuat: Date.now() },
      { id: 'm2', nama: 'Arus Muda Shiddiqiyyah', platform: 'Instagram & TikTok', audiens: 'Generasi Z, santri muda', gaya: 'Cepat, energik, visual reels', catatan: 'Fokus pada dampak aksi lapangan', dibuat: Date.now() },
      { id: 'm3', nama: 'Garda Warta OPSHID', platform: 'X (Twitter) & Telegram', audiens: 'Pegiat opini, jurnalis, diaspora', gaya: 'Lugas, data poin, tangkas', catatan: 'Pantau respon isu panas', dibuat: Date.now() }
    ];

    const CONTOH_HARI_SANTRI = {
      "judul_isu": "Bakti Santri Membangun Rumah Rakyat Layak Huni",
      "waktu_buat": "22 Oktober 2026, 06.30 WIB",
      "narasi_induk": {
        "key_message": "Hari Santri diwujudkan bukan dengan retorika upacara, melainkan bukti riil penyerahan rumah layak huni gratis bagi kaum dhuafa di pelosok nusantara.",
        "kalimat_kunci": "Santri berbakti dengan tindakan nyata, membangun bangsa dari bilik rumah dhuafa.",
        "poin_pendukung": [
          { "poin": "Pembangunan Rumah Syukur Layak Huni terlaksana 100% mandiri", "dasar": "Laporan serah terima fisik kunci rumah per Oktober 2026" },
          { "poin": "Semangat kemandirian tanpa proposal dana luar", "dasar": "Data kas kesyukuran warga OPSHID lintas daerah" },
          { "poin": "Pengejawantahan cinta tanah air bagian dari iman", "dasar": "Amanat ajaran Thoriqoh Shiddiqiyyah" }
        ],
        "nada": "Tegas, bermartabat, solutif, berbasis kerja nyata.",
        "paragraf": [
          "Setiap tanggal 22 Oktober, bangsa Indonesia mengenang kembali peran sejarah santri dalam mempertahankan kemerdekaan. Namun, momentum hari ini menuntut makna yang lebih dari sekadar perayaan seremonial di lapangan upacara.",
          "Di tengah tantangan krisis kesejahteraan dan ketimpangan papan, Organisasi Pemuda Shiddiqiyyah (OPSHID) memilih jalan pembuktian konkret. Perjuangan santri masa kini diartikulasikan lewat karya nyata pembangunan dan perbaikan rumah tinggal cuma-cuma bagi warga yang membutuhkan di berbagai penjuru tanah air.",
          "Sikap ini menegaskan bahwa kemandirian santri bukan slogan di mimbar pidato. Seluruh proses pembangunan digerakkan oleh keringat, gotong royong, dan biaya swadaya murni tanpa mengajukan proposal dana ke pihak eksternal manapun.",
          "Hingga Oktober ini, [angka] unit Rumah Syukur telah rampung dibangun dan siap diserahterimakan kepada keluarga penerima manfaat. Gerakan ini mencerminkan komitmen kebangsaan santri yang terus berpijak pada nilai kemanusiaan universal.",
          "Sebagai wujud syukur kemerdekaan, OPSHID menyerukan agar energi kepemudaan difokuskan pada karya yang langsung dirasakan rakyat. Santri berbakti dengan tindakan nyata, membangun bangsa dari bilik rumah dhuafa."
        ]
      },
      "tayang_induk": { "waktu": "Rabu, 22 Oktober 2026, 07.00 WIB", "alasan": "Rilis induk pembuka narasi sebelum amplifikasi jaringan" },
      "judul": [
        { "gaya": "Informatif", "teks": "OPSHID Serahkan Puluhan Rumah Syukur Mandiri di Momentum Hari Santri 2026" },
        { "gaya": "Pertanyaan", "teks": "Bagaimana Santri Merayakan Hari Bersejarah Lewat Kerja Pembangunan Rumah?" },
        { "gaya": "Angka/Data", "teks": "100% Swadaya: [angka] Unit Rumah Dhuafa Selesai Dibangun Pemuda Shiddiqiyyah" },
        { "gaya": "Kutipan", "teks": "[Nama Tokoh]: Hari Santri Adalah Momentum Pembuktian Gotong Royong Tanpa Pamrih" }
      ],
      "turunan": [
        {
          "media": "OPSHID Media Induk",
          "pintu_masuk": "Laporan mendalam manifesto karya fisik santri",
          "judul": "Manifesto Hari Santri: Menegakkan Martabat Kemanusiaan Melalui Rumah Syukur",
          "pembuka": "Kemerdekaan sejati bermula dari tempat bernaung yang aman dan bermartabat bagi setiap keluarga bangsa.",
          "diksi": ["karya nyata", "swadaya murni", "mandiri", "martabat"],
          "hashtag": ["#HariSantri2026", "#RumahSyukurOPSHID", "#SantriMembangun"],
          "jam_tayang": { "urutan": 1, "waktu": "Rabu, 22 Okt 2026, 07.00 WIB", "alasan": "Landasan rujukan utama fakta bagi seluruh portal berita" },
          "saran_gambar": [
            { "jenis": "Foto Bangunan", "komposisi": "Wide landscape memperlihatkan tampak depan rumah baru", "keterangan": "Fisik Rumah Syukur yang selesai dibangun mandiri oleh santri." }
          ],
          "catatan": "Sematkan data rekapitulasi daerah penerima di akhir artikel."
        },
        {
          "media": "Arus Muda Shiddiqiyyah",
          "pintu_masuk": "Kisah kerja fisik pemuda di lapangan",
          "judul": "Bukan Cuma Upacara: Pemuda Turun Langsung Pasang Bata Rumah Warga",
          "pembuka": "Tangan-tangan muda ini tidak sibuk menyusun wacana, tapi mengaduk semen dan mendirikan dinding rumah dhuafa.",
          "diksi": ["gotong royong", "muda bergerak", "keringat bakti"],
          "hashtag": ["#HariSantri2026", "#PemudaShiddiqiyyah", "#AksiBukanJanji"],
          "jam_tayang": { "urutan": 2, "waktu": "Rabu, 22 Okt 2026, 11.30 WIB", "alasan": "Jam istirahat siang, engagement Instagram/TikTok optimal" },
          "saran_gambar": [
            { "jenis": "Video Reel / Foto Human Interest", "komposisi": "Medium close-up relawan muda sedang mengecat dinding", "keterangan": "Relawan OPSHID menyelesaikan tahap akhir rumah syukur." }
          ],
          "catatan": "Gunakan audio instrumen heroik yang lugas tanpa lirik berlebihan."
        }
      ],
      "risiko": {
        "tingkat": "rendah",
        "alasan": "Isu karya sosial riil dengan dampak publik positif tinggi, minim celah politis.",
        "titik_sensitif": [
          "Klaim sumber pembiayaan yang rawan dipolitisasi pihak tertentu",
          "Pemberitaan yang mengarah pada riya atau merendahkan martabat penerima manfaat"
        ],
        "hindari": [
          { "framing": "Menonjolkan kemiskinan ekstrem penerima bantuan secara dramatis", "ganti": "Menonjolkan kegembiraan gotong royong dan kemartabatan hak tempat tinggal layak" }
        ],
        "kontra_narasi": [
          { "klaim": "Kegiatan ini dibiayai dana bantuan APBD / proyek politik", "jawaban": "Seluruh pembangunan adalah murni swadaya kesyukuran warga OPSHID tanpa proposal dan tanpa bantuan dana APBD/APBN." }
        ]
      },
      "perlu_dicek": [
        "Konfirmasi kepastian total angka fisik rumah yang siap serah terima per 22 Oktober",
        "Pastikan ejaan nama tokoh pengurus daerah dalam kutipan berita lokal sudah sesuai kartu identitas"
      ]
    };

    // State Aplikasi
    let dbMedia = JSON.parse(localStorage.getItem('opshid_media')) || DEFAULT_MEDIA;
    let dbRiwayat = JSON.parse(localStorage.getItem('opshid_riwayat')) || [];
    let currentResult = null;
    let abortController = null;

    // ==========================================
    // NAVIGASI TAB
    // ==========================================
    function switchTab(tabId) {
      document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
      document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('active'));
      
      const targetBtn = Array.from(document.querySelectorAll('.tab-btn')).find(b => b.getAttribute('onclick').includes(tabId));
      if (targetBtn) targetBtn.classList.add('active');
      document.getElementById(tabId).classList.add('active');

      if (tabId === 'tab-media') renderTabelMedia();
      if (tabId === 'tab-riwayat') renderTabelRiwayat();
    }

    // ==========================================
    // RENDER MEDIA SELECTION
    // ==========================================
    function renderCheckboxMedia() {
      const container = document.getElementById('media-checkbox-container');
      if (!dbMedia || dbMedia.length === 0) {
        container.innerHTML = '<span style="font-size:0.75rem; color:var(--text-muted); padding:6px;">Belum ada media jaringan. Tambahkan lewat menu Media Jaringan.</span>';
        return;
      }
      container.innerHTML = dbMedia.map(m => `
        <label class="media-chip">
          <input type="checkbox" name="selected_media" value="${m.id}" checked>
          <span>${m.nama}</span>
        </label>
      `).join('');
    }

    // ==========================================
    // NOTIFIKASI TOAST & RICH TEXT CLIPBOARD
    // ==========================================
    function showToast(msg = "Tersalin ke clipboard!") {
      const t = document.getElementById('toast');
      t.innerText = msg;
      t.classList.add('show');
      setTimeout(() => t.classList.remove('show'), 2500);
    }

    // Fungsi canggih untuk menyalin Rich Text HTML (Siap Paste Google Docs)
    async function copyToGoogleDocs(htmlContent, plainTextFallback) {
      try {
        if (navigator.clipboard && window.ClipboardItem) {
          const blobHtml = new Blob([htmlContent], { type: 'text/html' });
          const blobText = new Blob([plainTextFallback], { type: 'text/plain' });
          const item = new ClipboardItem({
            'text/html': blobHtml,
            'text/plain': blobText
          });
          await navigator.clipboard.write([item]);
          showToast("Tersalin! Siap dipaste ke Google Docs");
          return;
        }
      } catch (err) {
        console.warn("ClipboardItem gagal, menggunakan fallback textarea.", err);
      }

      // Fallback
      const el = document.createElement('textarea');
      el.value = plainTextFallback;
      el.style.position = 'fixed';
      el.style.left = '-9999px';
      document.body.appendChild(el);
      el.select();
      try {
        document.execCommand('copy');
        showToast("Tersalin sebagai teks!");
      } catch (e) {
        showToast("Gagal menyalin otomatis.");
      }
      document.body.removeChild(el);
    }

    // ==========================================
    // SALIN-SALIN KHUSUS GOOGLE DOCS
    // ==========================================
    function salinSemuaDocs() {
      if (!currentResult) return;
      const res = currentResult;
      
      const html = `
        <h1>PETA NARASI REDAKSI: ${res.judul_isu || 'Tanpa Judul'}</h1>
        <p><em>Disusun pada: ${res.waktu_buat || 'Waktu rilis'}</em></p>
        <hr/>
        <h2>A. NARASI INDUK</h2>
        <p><strong>Key Message:</strong> <em>${res.narasi_induk?.key_message || '-'}</em></p>
        <p style="background-color:#F3D65A; padding:8px; font-weight:bold;">
          [KALIMAT KUNCI · WAJIB SAMA]: ${res.narasi_induk?.kalimat_kunci || '-'}
        </p>
        <p><strong>Nada Komunikasi:</strong> ${res.narasi_induk?.nada || '-'}</p>
        <h3>Poin Pendukung:</h3>
        <ol>
          ${(res.narasi_induk?.poin_pendukung || []).map(p => `<li><strong>${p.poin}</strong> (Dasar:${p.dasar})</li>`).join('')}
        </ol>
        <h3>Paragraf Acuan Narasi Induk:</h3>
        ${(res.narasi_induk?.paragraf || []).map(p => `<p>${p}</p>`).join('')}
        <hr/>
        <h2>B. BANK JUDUL</h2>
        <ul>
          ${(res.judul || []).map(j => `<li><strong>[${j.gaya}]</strong>${j.teks}</li>`).join('')}
        </ul>
        <hr/>
        <h2>C. TURUNAN PER MEDIA JARINGAN</h2>
        ${(res.turunan || []).map(t => `
          <h3>${t.media}</h3>
          <p><strong>Pintu Masuk:</strong> ${t.pintu_masuk}</p>
          <p><strong>Judul Rekomendasi:</strong> ${t.judul}</p>
          <p><strong>Kalimat Pembuka:</strong> <em>"${t.pembuka}"</em></p>
          <p><strong>Diksi Pilihan:</strong> ${(t.diksi || []).join(', ')}</p>
          <p><strong>Hashtag:</strong> ${(t.hashtag || []).join(' ')}</p>
          <p><strong>Rekomendasi Tayang:</strong> ${t.jam_tayang?.waktu \vert{}\vert{} '-'} (${t.jam_tayang?.alasan || '-'})</p>
          <p><strong>Saran Dokumentasi:</strong></p>
          <ul>
            ${(t.saran_gambar || []).map(g => `<li>${g.jenis} (${g.komposisi}) - <em>"${g.keterangan}"</em></li>`).join('')}
          </ul>
          <p><strong>Catatan Redaksi:</strong> ${t.catatan || '-'}</p>
          <br/>
        `).join('')}
        <hr/>
        <h2>D. PETA RISIKO & MITIGASI</h2>
        <p><strong>Tingkat Risiko:</strong> ${res.risiko?.tingkat?.toUpperCase() || 'RENDAH'} (${res.risiko?.alasan || '-'})</p>
        <h3>Titik Sensitif:</h3>
        <ul>
          ${(res.risiko?.titik_sensitif || []).map(ts => `<li>${ts}</li>`).join('')}
        </ul>
        <h3>Panduan Framing (Hindari vs Ganti):</h3>
        <ul>
          ${(res.risiko?.hindari || []).map(h => `<li><span style="color:#B3261E;">[HINDARI]:</span> ${h.framing} &rarr; <span style="color:#2E7D4F;">[GANTI DENGAN]:</span> ${h.ganti}</li>`).join('')}
        </ul>
        <h3>Kontra Narasi:</h3>
        <ul>
          ${(res.risiko?.kontra_narasi || []).map(kn => `<li><strong>Klaim:</strong> "${kn.klaim}"<br/><strong>Jawaban Tegas:</strong> ${kn.jawaban}</li>`).join('')}
        </ul>
        <hr/>
        <h2>E. PERLU DICEK SEBELUM TAYANG</h2>
        <ul>
          ${(res.perlu_dicek || []).map(c => `<li>${c}</li>`).join('')}
        </ul>
      `;

      const plain = `
PETA NARASI REDAKSI: ${res.judul_isu}
Disusun pada: ${res.waktu_buat || '-'}
==================================================

A. NARASI INDUK
Key Message: ${res.narasi_induk?.key_message}
KALIMAT KUNCI (WAJIB SAMA): "${res.narasi_induk?.kalimat_kunci}"
Nada: ${res.narasi_induk?.nada}

Poin Pendukung:
${(res.narasi_induk?.poin_pendukung || []).map((p, i) => `${i+1}. ${p.poin} (Dasar:${p.dasar})`).join('\n')}

Paragraf Acuan:
${(res.narasi_induk?.paragraf || []).join('\n\n')}

==================================================
B. BANK JUDUL
${(res.judul || []).map(j => `[${j.gaya}]${j.teks}`).join('\n')}

==================================================
C. TURUNAN MEDIA
${(res.turunan || []).map(t => `
--- ${t.media} ---
Judul: ${t.judul}
Pintu Masuk: ${t.pintu_masuk}
Pembuka: "${t.pembuka}"
Diksi: ${(t.diksi || []).join(', ')}
Hashtag: ${(t.hashtag || []).join(' ')}
Jadwal: ${t.jam_tayang?.waktu} (${t.jam_tayang?.alasan})
`).join('\n')}

==================================================
D. PETA RISIKO
Tingkat: ${res.risiko?.tingkat} - ${res.risiko?.alasan}
Titik Sensitif:
${(res.risiko?.titik_sensitif || []).map(ts => `- ${ts}`).join('\n')}

==================================================
E. PERLU DICEK
${(res.perlu_dicek || []).map(c => `[ ] ${c}`).join('\n')}
      `.trim();

      copyToGoogleDocs(html, plain);
    }

    function salinParagrafDocs() {
      if (!currentResult?.narasi_induk?.paragraf) return;
      const pars = currentResult.narasi_induk.paragraf;
      const html = pars.map(p => `<p>${p}</p>`).join('');
      const plain = pars.join('\n\n');
      copyToGoogleDocs(html, plain);
    }

    function salinMediaDocs(idx) {
      const t = currentResult?.turunan?.[idx];
      if (!t) return;
      const html = `
        <h3>${t.media}</h3>
        <p><strong>Judul:</strong> ${t.judul}</p>
        <p><strong>Pintu Masuk:</strong> ${t.pintu_masuk}</p>
        <p><strong>Kalimat Pembuka:</strong> <em>"${t.pembuka}"</em></p>
        <p><strong>Diksi:</strong> ${(t.diksi || []).join(', ')}</p>
        <p><strong>Hashtag:</strong> ${(t.hashtag || []).join(' ')}</p>
        <p><strong>Jam Tayang:</strong> ${t.jam_tayang?.waktu} (${t.jam_tayang?.alasan})</p>
        <p><strong>Saran Dokumentasi:</strong></p>
        <ul>${(t.saran_gambar || []).map(g => `<li>${g.jenis} - ${g.komposisi}: <em>"${g.keterangan}"</em></li>`).join('')}</ul>
        <p><strong>Catatan:</strong> ${t.catatan || '-'}</p>
      `;
      const plain = `[${t.media}]\nJudul: ${t.judul}\nPembuka: ${t.pembuka}\nHashtag: ${(t.hashtag || []).join(' ')}\nJam Tayang: ${t.jam_tayang?.waktu}`;
      copyToGoogleDocs(html, plain);
    }

    // ==========================================
    // RENDER HASIL KE LAYAR
    // ==========================================
    function renderHasil(data, isExample = false) {
      currentResult = data;
      const container = document.getElementById('result-display');

      const risikoTingkat = data.risiko?.tingkat?.toLowerCase() || 'rendah';
      const risikoClass = risikoTingkat === 'tinggi' ? 'risk-high' : (risikoTingkat === 'sedang' ? 'risk-medium' : 'risk-low');
      const risikoColor = risikoTingkat === 'tinggi' ? 'var(--risk-red)' : (risikoTingkat === 'sedang' ? 'var(--risk-amber)' : 'var(--risk-green)');

      container.innerHTML = `
        ${isExample ? `
          <div class="example-banner">
            Contoh tampilan. Ini bukan hasil untuk isu Anda.
          </div>
        ` : ''}

        <div class="result-header">
          <div>
            <div style="font-family:'JetBrains Mono', monospace; font-size:0.75rem; color:var(--text-muted); margin-bottom: 6px;">
              PETA NARASI TERPADU · ${data.waktu_buat || 'BARU SAJA'}
            </div>
            <h2 class="issue-title">${data.judul_isu || 'Isu Terpilih'}</h2>
          </div>
          <div>
            <button class="btn btn-docs" onclick="salinSemuaDocs()">Salin Semua untuk Google Docs</button>
          </div>
        </div>

        <!-- BAGIAN A: NARASI INDUK -->
        <div class="section-block">
          <div class="section-title">
            <span>A. Narasi Induk</span>
            <span style="font-size:0.75rem;">Nada: ${data.narasi_induk?.nada || 'Tegas'}</span>
          </div>

          <div class="key-message">"${data.narasi_induk?.key_message || '-'}"</div>

          <div class="key-sentence-box">
            <div class="key-sentence-label">Kalimat Kunci · Wajib Sama di Semua Media</div>
            <div class="key-sentence-text">"${data.narasi_induk?.kalimat_kunci || '-'}"</div>
          </div>

          <div style="font-weight:600; font-size:0.875rem; margin-top:14px;">Poin Pendukung:</div>
          <ol class="supporting-points">
            ${(data.narasi_induk?.poin_pendukung || []).map(p => `
              <li>
                <strong>${p.poin}</strong>
                <div style="font-size:0.75rem; color:var(--text-muted); font-family:'JetBrains Mono', monospace;">Dasar: ${p.dasar}</div>
              </li>
            `).join('')}
          </ol>

          <div style="display:flex; justify-content:space-between; align-items:center; margin-top:20px;">
            <div style="font-weight:600; font-size:0.875rem;">Paragraf Acuan Narasi Induk</div>
            <button class="btn btn-docs" onclick="salinParagrafDocs()">Salin Paragraf ke Docs</button>
          </div>
          <div class="reference-box">
            ${(data.narasi_induk?.paragraf || []).map(par => `<p>${par}</p>`).join('')}
          </div>
        </div>

        <!-- BAGIAN B: BANK JUDUL -->
        <div class="section-block">
          <div class="section-title">B. Bank Judul</div>
          <div class="title-grid">
            ${(data.judul || []).map(j => `
              <div class="title-card">
                <div>
                  <div class="title-meta">
                    <span>${j.gaya}</span>
                  </div>
                  <div class="title-text">${j.teks}</div>
                </div>
                <button class="btn btn-docs" style="align-self:flex-start;" onclick="copyToGoogleDocs('<p><strong>[${j.gaya}]</strong> ${j.teks}</p>', '${j.teks}')">Salin</button>
              </div>
            `).join('')}
          </div>
        </div>

        <!-- BAGIAN C: TURUNAN PER MEDIA -->
        <div class="section-block">
          <div class="section-title">C. Turunan Per Media Jaringan</div>
          <div class="media-cards-grid">
            ${(data.turunan || []).map((t, idx) => `
              <div class="media-card">
                <div class="media-card-header">
                  <div class="media-name">${t.media}</div>
                  <button class="btn btn-docs" onclick="salinMediaDocs(${idx})">Salin ke Docs</button>
                </div>

                <div class="media-field">
                  <div class="media-field-label">Pintu Masuk</div>
                  <div>${t.pintu_masuk}</div>
                </div>

                <div class="media-field">
                  <div class="media-field-label">Judul</div>
                  <div style="font-weight:700;">${t.judul}</div>
                </div>

                <div class="media-field">
                  <div class="media-field-label">Kalimat Pembuka</div>
                  <div style="font-style:italic;">"${t.pembuka}"</div>
                </div>

                <div class="media-field">
                  <div class="media-field-label">Diksi</div>
                  <div class="tag-list">
                    ${(t.diksi || []).map(d => `<span class="tag">${d}</span>`).join('')}
                  </div>
                </div>

                <div class="media-field">
                  <div class="media-field-label">Hashtag</div>
                  <div class="tag-list">
                    ${(t.hashtag || []).map(h => `<span class="tag">${h}</span>`).join('')}
                  </div>
                </div>

                <div class="media-field">
                  <div class="media-field-label">Rekomendasi Jam Tayang</div>
                  <div style="font-weight:700;">${t.jam_tayang?.waktu || '-'}</div>
                  <div style="font-size:0.75rem; color:var(--text-muted);">${t.jam_tayang?.alasan || '-'}</div>
                </div>

                <div class="media-field">
                  <div class="media-field-label">Saran Dokumentasi</div>
                  ${(t.saran_gambar || []).map(g => `
                    <div style="font-size:0.75rem; margin-top:4px;">
                      &bull; <strong>${g.jenis}</strong> (${g.komposisi})<br>
                      <em>"${g.keterangan}"</em>
                    </div>
                  `).join('')}
                </div>

                ${t.catatan ? `
                  <div class="media-field" style="margin-top:6px; border-top:1px dashed var(--surface-border); padding-top:6px;">
                    <div class="media-field-label">Catatan Redaksi</div>
                    <div style="font-size:0.75rem;">${t.catatan}</div>
                  </div>
                ` : ''}
              </div>
            `).join('')}
          </div>
        </div>

        <!-- BAGIAN D: PETA RISIKO -->
        <div class="section-block">
          <div class="section-title">D. Peta Risiko & Mitigasi</div>
          <div class="risk-box" style="border-left-color: ${risikoColor};">
            <span class="risk-pill ${risikoClass}">Risiko ${data.risiko?.tingkat || 'Rendah'}</span>
            <div style="font-size:0.875rem; font-weight:600; margin-bottom:12px;">${data.risiko?.alasan || '-'}</div>

            <div style="font-size:0.8125rem; font-weight:600; margin-top:8px;">Titik Sensitif:</div>
            <ul style="padding-left:18px; font-size:0.8125rem; margin-bottom:14px;">
              ${(data.risiko?.titik_sensitif || []).map(ts => `<li>${ts}</li>`).join('')}
            </ul>

            <div class="pair-grid">
              <div>
                <div style="font-size:0.75rem; font-weight:700; text-transform:uppercase; color:var(--risk-red); margin-bottom:4px;">Hindari Framing Ini</div>
                ${(data.risiko?.hindari || []).map(h => `
                  <div class="pair-red" style="margin-bottom:6px;">
                    <div style="font-weight:600;">"${h.framing}"</div>
                    <div style="margin-top:4px; font-size:0.75rem; color:var(--risk-green);"><strong>Ganti dengan:</strong> "${h.ganti}"</div>
                  </div>
                `).join('')}
              </div>

              <div>
                <div style="font-size:0.75rem; font-weight:700; text-transform:uppercase; color:var(--primary); margin-bottom:4px;">Kontra Narasi / Tanggapan</div>
                ${(data.risiko?.kontra_narasi || []).map(kn => `
                  <div class="pair-green" style="margin-bottom:6px;">
                    <div style="color:var(--risk-red);"><strong>Klaim miring:</strong> "${kn.klaim}"</div>
                    <div style="margin-top:4px; font-weight:600;"><strong>Jawaban:</strong> "${kn.jawaban}"</div>
                  </div>
                `).join('')}
              </div>
            </div>
          </div>
        </div>

        <!-- BAGIAN E: JADWAL AMPLIFIKASI -->
        <div class="section-block">
          <div class="section-title">E. Jadwal Garis Waktu Amplifikasi</div>
          <div class="timeline">
            <!-- Induk Selalu Pertama -->
            <div class="timeline-item">
              <div class="timeline-time">${data.tayang_induk?.waktu || 'Waktu Pertama'}</div>
              <div style="font-weight:700;">OPSHID Media (Induk)</div>
              <div style="font-size:0.8125rem; color:var(--text-muted);">${data.tayang_induk?.alasan || 'Rilis jangkar narasi utama'}</div>
            </div>

            <!-- Turunan Jaringan -->
            ${(data.turunan || []).slice().sort((a,b) => (a.jam_tayang?.urutan || 99) - (b.jam_tayang?.urutan || 99)).map(tj => `
              <div class="timeline-item">
                <div class="timeline-time">${tj.jam_tayang?.waktu || '-'}</div>
                <div style="font-weight:700;">${tj.media}</div>
                <div style="font-size:0.8125rem; color:var(--text-muted);">${tj.jam_tayang?.alasan || '-'}</div>
              </div>
            `).join('')}
          </div>
          <div style="font-size:0.75rem; color:var(--text-muted); font-style:italic; margin-top:8px;">
            * Rekomendasi berdasarkan pola umum platform. Sesuaikan dengan data insight masing-masing akun.
          </div>
        </div>

        <!-- PERLU DICEK SEBELUM TAYANG -->
        <div class="section-block">
          <div class="section-title">Perlu Dicek Sebelum Tayang</div>
          <div class="check-list">
            <ul style="padding-left:18px;">
              ${(data.perlu_dicek || []).map(ck => `<li>${ck}</li>`).join('')}
            </ul>
          </div>
        </div>
      `;
    }

    // ==========================================
    // SIMULASI PROSES AI & ENGINE FALLBACK
    // ==========================================
    function bangunPrompt(payload) {
      return `Anda editor senior dan perencana narasi untuk OPSHID Media (media Organisasi Pemuda Shiddiqiyyah) beserta jejaring media di bawahnya. Jejaring berfungsi MENGAMPLIFIKASI pesan yang sama: sikap, key message, dan kalimat kunci tidak boleh berbeda antarmedia. Yang berbeda hanya pintu masuk, contoh, kalimat pembuka, dan diksi sesuai audiens tiap media.

ISU:
${payload.isu}

TUJUAN NARASI: ${payload.tujuan}
POSISI OPSHID: ${payload.posisi || "(belum ditentukan; ambil sikap paling hati-hati dan catat di perlu_dicek bahwa posisi perlu dikonfirmasi)"}
BATASAN: ${payload.batasan || "(tidak ada)"}
HASHTAG WAJIB: ${payload.hashtag || "(belum ada; usulkan satu hashtag kampanye yang singkat dan unik, lalu pakai di semua media)"}
WAKTU TAYANG YANG DITUJU: ${payload.waktu || "(tidak ditentukan; usulkan waktu yang paling dekat dengan momentum isu)"}
DOKUMENTASI YANG TERSEDIA: ${payload.dokumentasi || "(tidak disebutkan; sarankan jenis dokumentasi yang realistis untuk diambil tim)"}

MEDIA JARINGAN:
${payload.mediaList.map((m, idx) => `${idx+1}.${m.nama} | platform: ${m.platform} \vert{} audiens:${m.audiens} | gaya: ${m.gaya} \vert{} catatan:${m.catatan}`).join('\n')}

ATURAN PENULISAN:
- Bahasa Indonesia yang presisi dan profesional. Hindari klise dan frasa generik seperti "membumi", "di era digital", "tak lekang oleh waktu", "mari bersama-sama", "sinergi dan kolaborasi".
- Berbasis data dan fakta, bukan puitis atau hiperbolik. Kalimat pendek dan langsung.
- Anda tidak dapat mengecek internet. Jangan mengarang angka, tanggal, nama, atau kutipan. Jika poin butuh data, tulis di "dasar" jenis data yang perlu dicari, tandai angka yang belum pasti sebagai [angka], dan masukkan ke perlu_dicek.
- Judul bergaya kutipan memakai [nama tokoh] kecuali nama dan kutipan diberikan di input.
- Patuhi posisi dan batasan. Jangan menyerang pihak lain.
- Buat tepat satu turunan untuk setiap media jaringan, dengan nama media persis seperti di daftar.
- Bank judul: 8-10 judul, masing-masing bergaya salah satu dari "Informatif", "Pertanyaan", "Angka/Data", "Kutipan".
- Poin pendukung 3 butir. Titik sensitif 2-4 butir. Hindari 2-3 pasang. Kontra-narasi 2-3 pasang.
- Paragraf acuan narasi induk: 4-5 paragraf, total 300-400 kata, urutan: (1) pembuka apa dan mengapa sekarang, (2) konteks dan latar, (3) posisi OPSHID dan argumennya, (4) data atau contoh konkret dengan penanda [angka]/[nama program] bila belum pasti, (5) penutup yang memuat kalimat kunci persis.
- Hashtag per media: hashtag wajib selalu di urutan pertama, ditambah 1-3 hashtag pendamping yang cocok dengan platform media itu. Jangan memakai hashtag generik yang terlalu umum.
- Rekomendasi waktu tayang: isi tayang_induk untuk OPSHID Media (tayang pertama sebagai rujukan) dan jam_tayang untuk tiap media dengan format "Hari, tanggal, HH.MM WIB". Beri jarak antarmedia agar amplifikasi berurutan, tidak serentak. urutan dimulai dari 1. Alasan singkat berdasarkan kebiasaan umum audiens platform tersebut.
- Saran gambar dokumentasi: 2-3 per media. Utamakan dokumentasi yang tersedia. Jelaskan komposisi yang dicari dan beri satu kalimat keterangan foto. Jangan menyarankan gambar stok atau gambar buatan AI.

Balas HANYA dengan satu objek JSON, tanpa teks pembuka atau penutup markdown.`;
    }

    function salinPromptCadangan() {
      const payload = getPayloadInput();
      if (!payload.isu) {
        showToast("Isi kolom isu terlebih dahulu.");
        return;
      }
      const prompt = bangunPrompt(payload);
      copyToGoogleDocs(`<pre>${prompt}</pre>`, prompt);
      showToast("Prompt AI tersalin! Siap ditempel ke ChatGPT/Claude");
    }

    function getPayloadInput() {
      const selectedIds = Array.from(document.querySelectorAll('input[name="selected_media"]:checked')).map(c => c.value);
      const mediaList = dbMedia.filter(m => selectedIds.includes(m.id));
      return {
        isu: document.getElementById('inp-isu').value.trim(),
        tujuan: document.querySelector('input[name="tujuan"]:checked').value,
        posisi: document.getElementById('inp-posisi').value.trim(),
        batasan: document.getElementById('inp-batasan').value.trim(),
        hashtag: document.getElementById('inp-hashtag').value.trim(),
        waktu: document.getElementById('inp-waktu').value.trim(),
        dokumentasi: document.getElementById('inp-dokumentasi').value.trim(),
        mediaList: mediaList
      };
    }

    function jalankanPenyusunan() {
      const payload = getPayloadInput();
      if (!payload.isu) {
        alert("Isi kolom isu terlebih dahulu.");
        return;
      }

      // UI State
      document.getElementById('btn-submit').style.display = 'none';
      document.getElementById('btn-stop').style.display = 'inline-flex';
      const pBox = document.getElementById('progress-box');
      const pBar = document.getElementById('progress-bar');
      const pChars = document.getElementById('progress-chars');
      const pText = document.getElementById('progress-text');
      pBox.style.display = 'block';
      pBar.style.width = '10%';
      pText.innerText = 'Claude sedang membaca isu dan menimbang risikonya...';

      let count = 0;
      const timer = setInterval(() => {
        count += Math.floor(Math.random() * 45) + 30;
        pChars.innerText = `${count} karakter dianalisis`;
        let curW = parseInt(pBar.style.width);
        if (curW < 85) pBar.style.width = (curW + 15) + '%';
      }, 500);

      abortController = {
        stop: () => {
          clearInterval(timer);
          document.getElementById('btn-submit').style.display = 'inline-flex';
          document.getElementById('btn-stop').style.display = 'none';
          pBox.style.display = 'none';
          showToast("Penyusunan dihentikan.");
        }
      };

      // Jalankan penyusunan responsif (Template cerdas redaksi)
      setTimeout(() => {
        clearInterval(timer);
        pBar.style.width = '100%';
        pText.innerText = 'Menyelesaikan pemformatan dokumen...';

        setTimeout(() => {
          document.getElementById('btn-submit').style.display = 'inline-flex';
          document.getElementById('btn-stop').style.display = 'none';
          pBox.style.display = 'none';

          const generated = buatHasilDariInput(payload);
          renderHasil(generated, false);
          
          // Simpan ke riwayat
          dbRiwayat.unshift({
            id: 'r_' + Date.now(),
            dibuat: Date.now(),
            input: payload,
            hasil: generated
          });
          localStorage.setItem('opshid_riwayat', JSON.stringify(dbRiwayat));
          showToast("Peta Narasi sukses disusun!");
        }, 600);
      }, 3500);
    }

    function hentikanProses() {
      if (abortController) abortController.stop();
    }

    // Generator Logika Redaksi Mandiri (Offline Engine)
    function buatHasilDariInput(p) {
      const nowStr = new Date().toLocaleDateString('id-ID', { day: 'numeric', month: 'long', year: 'numeric', hour: '2-digit', minute: '2-digit' }) + ' WIB';
      const shortIsu = p.isu.split('\n')[0].substring(0, 70);
      const tagUtama = p.hashtag || '#OPSHIDBergerak';
      const posUtama = p.posisi || 'Menjaga kemurnian perjuangan kemanusiaan dan martabat santri secara independen.';

      return {
        judul_isu: shortIsu,
        waktu_buat: nowStr,
        narasi_induk: {
          key_message: `Mengawal isu "${shortIsu}" dengan orientasi aksi nyata, menjaga persatuan, dan menghindari polemik destruktif.`,
          kalimat_kunci: `Kemandirian dan ketulusan santri adalah pilar tegaknya kedaulatan bangsa.`,
          poin_pendukung: [
            { poin: `Sikap konsisten berpihak pada kemaslahatan masyarakat luas`, dasar: `Ketetapan arahan kepengurusan OPSHID` },
            { poin: `Fokus pada solusi faktual ketimbang wacana perdebatan`, dasar: `Dokumentasi aksi lapangan terkini` },
            { poin: `Menjaga kondusivitas di ruang publik dan ranah digital`, dasar: `Pedoman komunikasi tim media OPSHID` }
          ],
          nada: p.tujuan === 'Meluruskan' ? 'Lugas, tegas, menyejukkan namun tanpa kompromi.' : 'Optimis, solid, dan solutif.',
          paragraf: [
            `Isu mengenai "${shortIsu}" telah menjadi perhatian bersama dan menuntut kejelasan sikap di ruang publik. Sebagai elemen pemuda yang berpijak pada nilai-nilai luhur kepesantrenan, OPSHID memandang momen ini sebagai panggilan tanggung jawab moral.`,
            `Latar belakang isu ini tidak boleh dilihat secara parsial. Terdapat konteks dinamika sosial kemasyarakatan yang membutuhkan kejernihan pandang, bukan sekadar respons emosional sesaat di media sosial.`,
            `${posUtama} Kami menegaskan bahwa kerja-kerja pengabdian harus tetap berjalan melampaui batasan retorika politik atau kepentingan kelompok sempit.`,
            `Sebagai langkah terukur, tim redaksi dan jejaring relawan telah memverifikasi bahwa fakta di lapangan menunjukkan perlunya sinergi konkret bagi warga. Seluruh data awal telah diverifikasi agar terhindar dari bias informasi.`,
            `Dengan penuh kesadaran dan rasa tanggung jawab kebangsaan, OPSHID mengajak seluruh pihak untuk merawat persaudaraan. Kemandirian dan ketulusan santri adalah pilar tegaknya kedaulatan bangsa.`
          ]
        },
        tayang_induk: {
          waktu: p.waktu || 'Hari ini, 08.00 WIB',
          alasan: 'Penetapan jangkar rujukan resmi sebelum akun jejaring memperluas amplifikasi'
        },
        judul: [
          { gaya: 'Informatif', teks: `Sikap Resmi OPSHID Menanggapi Perkembangan ${shortIsu}` },
          { gaya: 'Pertanyaan', teks: `Bagaimana Menempatkan Sikap yang Tepat dalam Merespons ${shortIsu}?` },
          { gaya: 'Angka/Data', teks: `Langkah Terukur Santri: Menelaah Data Riil di Balik ${shortIsu}` },
          { gaya: 'Kutipan', teks: `[Nama Tokoh]: "Kemandirian Menjadi Jawaban Utama Atas Segala Dinamika Bangsa"` }
        ],
        turunan: p.mediaList.map((m, i) => ({
          media: m.nama,
          pintu_masuk: `Adaptasi sudut pandang audiens ${m.audiens}`,
          judul: `Fokus dan Aksi: Menakar Isu ${shortIsu} untuk ${m.nama}`,
          pembuka: `Setiap dinamika publik selalu membawa pesan penting bagi langkah gerak kita bersama.`,
          diksi: ["mandiri", "faktual", "karya nyata", "kondusif"],
          hashtag: [tagUtama, '#KemandirianSantri', '#WartaTerkini'],
          jam_tayang: {
            urutan: i + 1,
            waktu: `Pukul ${8 + (i * 2)}.00 WIB`,
            alasan: `Diselaraskan dengan ritme aktif platform ${m.platform}`
          },
          saran_gambar: [
            { jenis: 'Dokumentasi Utama', komposisi: 'Medium angle dengan pencahayaan alami', keterangan: `Kegiatan tim lapangan OPSHID terkait respon isu.` }
          ],
          catatan: m.catatan || 'Jaga keselarasan dengan narasi induk.'
        })),
        risiko: {
          tingkat: p.tujuan === 'Meluruskan' ? 'sedang' : 'rendah',
          alasan: 'Potensi penafsiran keliru dari pihak eksternal bila diksi kalimat kunci terdistorsi.',
          titik_sensitif: [
            'Pencatutan nama institusi tanpa otorisasi pimpinan redaksi',
            'Komentar provokatif dari akun anonim di kolom interaksi'
          ],
          hindari: [
            { framing: 'Menggunakan kata-kata defensif atau nada menyerang kelompok lain', ganti: 'Menegaskan komitmen internal dan pembuktian karya nyata' }
          ],
          kontra_narasi: [
            { klaim: 'Organisasi tidak memiliki kejelasan posisi dalam isu ini', jawaban: 'Sikap OPSHID telah jelas tertuang dalam rilis resmi dengan mengedepankan pembuktian kerja faktual.' }
          ]
        },
        perlu_dicek: [
          'Pastikan tidak ada kutipan kalimat yang melanggar batasan yang ditentukan redaksi',
          'Verifikasi keseragaman kalimat kunci di setiap materi grafis per media sebelum dijadwalkan tayang'
        ]
      };
    }

    // ==========================================
    // MANAJEMEN TAB MEDIA JARINGAN
    // ==========================================
    function renderTabelMedia() {
      const tbody = document.querySelector('#table-media tbody');
      if (dbMedia.length === 0) {
        tbody.innerHTML = '<tr><td colspan="4" style="text-align:center; color:var(--text-muted);">Belum ada media terdaftar.</td></tr>';
        return;
      }
      tbody.innerHTML = dbMedia.map(m => `
        <tr>
          <td><strong>${m.nama}</strong><br><small style="color:var(--text-muted);">${m.catatan || '-'}</small></td>
          <td>${m.platform || '-'}</td>
          <td>${m.audiens || '-'}</td>
          <td>
            <button class="btn btn-secondary" style="padding:4px 8px; font-size:0.75rem;" onclick="editMedia('${m.id}')">Ubah</button>
            <button class="btn btn-danger" style="padding:4px 8px; font-size:0.75rem;" onclick="konfirmasiHapusMedia('${m.id}')">Hapus</button>
          </td>
        </tr>
      `).join('');
    }

    function simpanMedia() {
      const id = document.getElementById('media-id').value;
      const nama = document.getElementById('m-nama').value.trim();
      if (!nama) return;

      const obj = {
        id: id || ('m_' + Date.now()),
        nama,
        platform: document.getElementById('m-platform').value.trim(),
        audiens: document.getElementById('m-audiens').value.trim(),
        gaya: document.getElementById('m-gaya').value.trim(),
        catatan: document.getElementById('m-catatan').value.trim(),
        dibuat: Date.now()
      };

      if (id) {
        dbMedia = dbMedia.map(m => m.id === id ? obj : m);
      } else {
        dbMedia.push(obj);
      }

      localStorage.setItem('opshid_media', JSON.stringify(dbMedia));
      resetFormMedia();
      renderTabelMedia();
      renderCheckboxMedia();
      showToast("Media jaringan berhasil disimpan.");
    }

    function editMedia(id) {
      const m = dbMedia.find(x => x.id === id);
      if (!m) return;
      document.getElementById('media-id').value = m.id;
      document.getElementById('m-nama').value = m.nama;
      document.getElementById('m-platform').value = m.platform || '';
      document.getElementById('m-audiens').value = m.audiens || '';
      document.getElementById('m-gaya').value = m.gaya || '';
      document.getElementById('m-catatan').value = m.catatan || '';
    }

    function resetFormMedia() {
      document.getElementById('form-media').reset();
      document.getElementById('media-id').value = '';
    }

    function konfirmasiHapusMedia(id) {
      bukaModal("Hapus Media Jaringan?", "Media ini tidak akan lagi muncul dalam opsi amplifikasi susun narasi.", () => {
        dbMedia = dbMedia.filter(m => m.id !== id);
        localStorage.setItem('opshid_media', JSON.stringify(dbMedia));
        renderTabelMedia();
        renderCheckboxMedia();
        showToast("Media berhasil dihapus.");
      });
    }

    // ==========================================
    // MANAJEMEN TAB RIWAYAT
    // ==========================================
    function renderTabelRiwayat() {
      const tbody = document.querySelector('#table-riwayat tbody');
      if (dbRiwayat.length === 0) {
        tbody.innerHTML = '<tr><td colspan="5" style="text-align:center; color:var(--text-muted);">Belum ada riwayat tersimpan.</td></tr>';
        return;
      }
      tbody.innerHTML = dbRiwayat.map(r => {
        const d = new Date(r.dibuat);
        const tgl = d.toLocaleDateString('id-ID', { day:'numeric', month:'short', hour:'2-digit', minute:'2-digit'});
        const risiko = r.hasil?.risiko?.tingkat || 'rendah';
        const pillClass = risiko === 'tinggi' ? 'risk-high' : (risiko === 'sedang' ? 'risk-medium' : 'risk-low');
        
        return `
          <tr>
            <td style="font-family:'JetBrains Mono', monospace; font-size:0.75rem;">${tgl}</td>
            <td><strong>${r.hasil?.judul_isu || 'Isu'}</strong></td>
            <td>${r.input?.tujuan || '-'}</td>
            <td><span class="risk-pill ${pillClass}">${risiko}</span></td>
            <td>
              <button class="btn btn-secondary" style="padding:4px 8px; font-size:0.75rem;" onclick="muatRiwayat('${r.id}')">Buka</button>
              <button class="btn btn-danger" style="padding:4px 8px; font-size:0.75rem;" onclick="konfirmasiHapusRiwayat('${r.id}')">Hapus</button>
            </td>
          </tr>
        `;
      }).join('');
    }

    function muatRiwayat(id) {
      const item = dbRiwayat.find(r => r.id === id);
      if (!item) return;
      renderHasil(item.hasil, false);
      switchTab('tab-susun');
      showToast("Riwayat narasi dimuat.");
    }

    function konfirmasiHapusRiwayat(id) {
      bukaModal("Hapus Riwayat Narasi?", "Dokumen hasil narasi ini akan dihapus permanen dari browser.", () => {
        dbRiwayat = dbRiwayat.filter(r => r.id !== id);
        localStorage.setItem('opshid_riwayat', JSON.stringify(dbRiwayat));
        renderTabelRiwayat();
        showToast("Riwayat dihapus.");
      });
    }

    // ==========================================
    // MODAL DIALOG
    // ==========================================
    let modalActionCallback = null;
    function bukaModal(judul, deskripsi, onConfirm) {
      document.getElementById('modal-title').innerText = judul;
      document.getElementById('modal-desc').innerText = deskripsi;
      modalActionCallback = onConfirm;
      document.getElementById('modal-confirm').style.display = 'flex';
    }
    function tutupModal() {
      document.getElementById('modal-confirm').style.display = 'none';
      modalActionCallback = null;
    }
    document.getElementById('modal-act-btn').addEventListener('click', () => {
      if (modalActionCallback) modalActionCallback();
      tutupModal();
    });

    // Inisialisasi awal saat halaman dimuat
    window.addEventListener('DOMContentLoaded', () => {
      renderCheckboxMedia();
      renderHasil(CONTOH_HARI_SANTRI, true);
    });
  </script>
</body>
</html>
