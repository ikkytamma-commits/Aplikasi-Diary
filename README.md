<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>🌸 Diary Book</title>
    <!-- Font Awesome untuk ikon -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Poppins:wght@300;400;500;600&display=swap" rel="stylesheet" />
    <style>
        /* ===== RESET & BASE ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(145deg, #fce4ec 0%, #f3e5f5 50%, #e8eaf6 100%);
            min-height: 100vh;
            padding: 20px;
            background-attachment: fixed;
        }

        /* ===== SCROLLBAR ===== */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: rgba(255, 255, 255, 0.3);
            border-radius: 10px;
        }
        ::-webkit-scrollbar-thumb {
            background: #ce93d8;
            border-radius: 10px;
        }

        /* ===== CONTAINER ===== */
        .app-container {
            max-width: 1200px;
            margin: 0 auto;
        }

        /* ===== HEADER ===== */
        .header {
            text-align: center;
            padding: 30px 20px 20px;
            background: rgba(255, 255, 255, 0.6);
            backdrop-filter: blur(12px);
            border-radius: 40px 40px 30px 30px;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
            margin-bottom: 30px;
            border: 1px solid rgba(255, 255, 255, 0.6);
            position: relative;
        }

        .header h1 {
            font-family: 'Playfair Display', serif;
            font-size: 2.8rem;
            font-weight: 700;
            color: #4a148c;
            text-shadow: 0 2px 10px rgba(106, 27, 154, 0.15);
            letter-spacing: 1px;
        }

        .header h1 i {
            color: #e91e63;
            margin: 0 8px;
        }

        .header p {
            color: #6a1b9a;
            font-size: 1.05rem;
            margin-top: 4px;
            font-weight: 300;
            letter-spacing: 2px;
        }

        .header .deco-flowers {
            font-size: 1.8rem;
            letter-spacing: 6px;
            opacity: 0.6;
            margin-top: 2px;
        }

        /* ===== STATS BAR ===== */
        .stats-bar {
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
            margin-top: 10px;
            font-size: 0.95rem;
            color: #4a148c;
            background: rgba(255, 255, 255, 0.4);
            padding: 10px 25px;
            border-radius: 50px;
            backdrop-filter: blur(4px);
            display: inline-flex;
            margin-left: auto;
            margin-right: auto;
        }

        .stats-bar span {
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .stats-bar i {
            color: #e91e63;
        }

        /* ===== BUTTONS ===== */
        .btn {
            padding: 12px 28px;
            border: none;
            border-radius: 50px;
            font-family: 'Poppins', sans-serif;
            font-weight: 500;
            font-size: 0.95rem;
            cursor: pointer;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
        }

        .btn-primary {
            background: linear-gradient(135deg, #ab47bc, #8e24aa);
            color: #fff;
        }
        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(156, 39, 176, 0.35);
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.7);
            color: #4a148c;
            backdrop-filter: blur(4px);
            border: 1px solid rgba(255, 255, 255, 0.8);
        }
        .btn-secondary:hover {
            background: #fff;
            transform: translateY(-3px);
        }

        .btn-danger {
            background: linear-gradient(135deg, #ef5350, #c62828);
            color: #fff;
        }
        .btn-danger:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(229, 57, 53, 0.35);
        }

        .btn-sm {
            padding: 8px 16px;
            font-size: 0.8rem;
        }

        /* ===== TOGGLE FORM BUTTON ===== */
        .toggle-form-wrapper {
            text-align: center;
            margin-bottom: 25px;
        }

        /* ===== FORM ===== */
        .form-container {
            background: rgba(255, 255, 255, 0.75);
            backdrop-filter: blur(16px);
            border-radius: 30px;
            padding: 30px 35px;
            margin-bottom: 30px;
            box-shadow: 0 15px 50px rgba(0, 0, 0, 0.07);
            border: 1px solid rgba(255, 255, 255, 0.7);
            transition: all 0.4s ease;
            display: none;
        }

        .form-container.open {
            display: block;
            animation: slideDown 0.4s ease;
        }

        @keyframes slideDown {
            0% {
                opacity: 0;
                transform: translateY(-20px) scale(0.97);
            }
            100% {
                opacity: 1;
                transform: translateY(0) scale(1);
            }
        }

        .form-title {
            font-family: 'Playfair Display', serif;
            font-size: 1.8rem;
            color: #4a148c;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .form-title i {
            color: #e91e63;
        }

        .form-group {
            margin-bottom: 18px;
        }

        .form-group label {
            display: block;
            font-weight: 500;
            color: #4a148c;
            margin-bottom: 6px;
            font-size: 0.9rem;
        }

        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 12px 18px;
            border: 2px solid rgba(156, 39, 176, 0.15);
            border-radius: 20px;
            font-family: 'Poppins', sans-serif;
            font-size: 0.95rem;
            background: rgba(255, 255, 255, 0.6);
            transition: all 0.3s ease;
            color: #333;
        }

        .form-group input:focus,
        .form-group textarea:focus,
        .form-group select:focus {
            outline: none;
            border-color: #ab47bc;
            box-shadow: 0 0 0 4px rgba(171, 71, 188, 0.15);
            background: #fff;
        }

        .form-group textarea {
            min-height: 130px;
            resize: vertical;
        }

        .form-row {
            display: flex;
            gap: 20px;
            flex-wrap: wrap;
        }

        .form-row .form-group {
            flex: 1;
            min-width: 150px;
        }

        /* ===== STICKER PICKER ===== */
        .sticker-picker {
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
            padding: 10px 0;
        }

        .sticker-picker .sticker-option {
            font-size: 2rem;
            cursor: pointer;
            padding: 8px 12px;
            border-radius: 20px;
            background: rgba(255, 255, 255, 0.4);
            transition: all 0.2s ease;
            border: 2px solid transparent;
        }

        .sticker-picker .sticker-option:hover {
            transform: scale(1.2);
            background: rgba(255, 255, 255, 0.8);
        }

        .sticker-picker .sticker-option.active {
            border-color: #ab47bc;
            background: rgba(171, 71, 188, 0.15);
            transform: scale(1.15);
        }

        /* ===== COLOR THEME ===== */
        .color-themes {
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
            padding: 6px 0;
        }

        .color-themes .theme-dot {
            width: 36px;
            height: 36px;
            border-radius: 50%;
            cursor: pointer;
            border: 3px solid transparent;
            transition: all 0.25s ease;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.08);
        }

        .color-themes .theme-dot:hover {
            transform: scale(1.15);
        }

        .color-themes .theme-dot.active {
            border-color: #4a148c;
            transform: scale(1.2);
            box-shadow: 0 0 0 4px rgba(74, 20, 140, 0.2);
        }

        /* ===== DIARY GRID ===== */
        .diary-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 25px;
            margin-top: 10px;
        }

        /* ===== DIARY CARD ===== */
        .diary-card {
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(8px);
            border-radius: 28px;
            padding: 24px 24px 20px;
            box-shadow: 0 8px 35px rgba(0, 0, 0, 0.06);
            border: 1px solid rgba(255, 255, 255, 0.7);
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .diary-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 6px;
            background: linear-gradient(90deg, var(--theme-color, #ab47bc), var(--theme-light, #ce93d8));
            border-radius: 28px 28px 0 0;
        }

        .diary-card:hover {
            transform: translateY(-6px);
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.1);
        }

        .diary-card .card-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 10px;
        }

        .diary-card .card-sticker {
            font-size: 2.4rem;
            line-height: 1;
        }

        .diary-card .card-date {
            font-size: 0.8rem;
            color: #7b1fa2;
            background: rgba(255, 255, 255, 0.5);
            padding: 4px 14px;
            border-radius: 30px;
            font-weight: 400;
        }

        .diary-card .card-title {
            font-family: 'Playfair Display', serif;
            font-size: 1.4rem;
            font-weight: 700;
            color: #4a148c;
            margin: 6px 0 10px;
            line-height: 1.3;
        }

        .diary-card .card-body {
            font-size: 0.95rem;
            color: #4a4a4a;
            line-height: 1.7;
            margin-bottom: 16px;
            white-space: pre-wrap;
            word-break: break-word;
            max-height: 180px;
            overflow-y: auto;
            padding-right: 4px;
        }

        .diary-card .card-actions {
            display: flex;
            gap: 10px;
            justify-content: flex-end;
            border-top: 1px solid rgba(0, 0, 0, 0.05);
            padding-top: 14px;
            margin-top: 4px;
        }

        .diary-card .card-actions .btn {
            padding: 6px 16px;
            font-size: 0.75rem;
            border-radius: 30px;
        }

        /* ===== EMPTY STATE ===== */
        .empty-state {
            text-align: center;
            padding: 60px 20px;
            background: rgba(255, 255, 255, 0.5);
            border-radius: 40px;
            backdrop-filter: blur(8px);
            grid-column: 1 / -1;
        }

        .empty-state i {
            font-size: 4rem;
            color: #ce93d8;
            margin-bottom: 16px;
        }
        .empty-state h3 {
            font-family: 'Playfair Display', serif;
            color: #4a148c;
            font-size: 1.6rem;
        }
        .empty-state p {
            color: #7b1fa2;
            opacity: 0.7;
        }

        /* ===== RESPONSIVE ===== */
        @media (max-width: 640px) {
            .header h1 {
                font-size: 2rem;
            }
            .form-container {
                padding: 20px;
            }
            .diary-grid {
                grid-template-columns: 1fr;
            }
            .form-row {
                flex-direction: column;
                gap: 0;
            }
            .stats-bar {
                gap: 16px;
                font-size: 0.8rem;
                padding: 8px 18px;
            }
        }

        /* ===== NOTIFICATION ===== */
        .toast {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: rgba(74, 20, 140, 0.92);
            backdrop-filter: blur(10px);
            color: #fff;
            padding: 16px 28px;
            border-radius: 50px;
            font-weight: 400;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.2);
            transform: translateY(80px);
            opacity: 0;
            transition: all 0.5s ease;
            z-index: 999;
            font-size: 0.95rem;
            border: 1px solid rgba(255, 255, 255, 0.15);
        }

        .toast.show {
            transform: translateY(0);
            opacity: 1;
        }

        .toast i {
            margin-right: 12px;
            color: #f8bbd0;
        }

        /* ===== CONFIRM DIALOG CUSTOM ===== */
        .modal-overlay {
            position: fixed;
            inset: 0;
            background: rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(6px);
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            padding: 20px;
        }

        .modal-overlay.active {
            display: flex;
            animation: fadeIn 0.3s ease;
        }

        @keyframes fadeIn {
            0% {
                opacity: 0;
                transform: scale(0.95);
            }
            100% {
                opacity: 1;
                transform: scale(1);
            }
        }

        .modal-box {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(20px);
            border-radius: 30px;
            padding: 35px 40px;
            max-width: 420px;
            width: 100%;
            text-align: center;
            box-shadow: 0 30px 80px rgba(0, 0, 0, 0.15);
            border: 1px solid rgba(255, 255, 255, 0.6);
        }

        .modal-box h3 {
            font-family: 'Playfair Display', serif;
            color: #4a148c;
            font-size: 1.6rem;
            margin-bottom: 8px;
        }

        .modal-box p {
            color: #6a1b9a;
            margin-bottom: 24px;
            opacity: 0.8;
        }

        .modal-box .btn-group {
            display: flex;
            gap: 14px;
            justify-content: center;
        }

        .modal-box .btn-group .btn {
            min-width: 100px;
            justify-content: center;
        }
    </style>
</head>
<body>

    <!-- ===== TOAST NOTIFICATION ===== -->
    <div id="toast" class="toast">
        <i class="fas fa-check-circle"></i>
        <span id="toastMessage">Berhasil disimpan!</span>
    </div>

    <!-- ===== CUSTOM CONFIRM MODAL ===== -->
    <div id="confirmModal" class="modal-overlay">
        <div class="modal-box">
            <h3>💭 Hapus Catatan?</h3>
            <p>Catatan ini akan hilang selamanya. Yakin ingin menghapus?</p>
            <div class="btn-group">
                <button class="btn btn-secondary" id="modalCancel">Batal</button>
                <button class="btn btn-danger" id="modalConfirm">Hapus</button>
            </div>
        </div>
    </div>

    <!-- ===== APP ===== -->
    <div class="app-container">

        <!-- HEADER -->
        <header class="header">
            <h1>
                <i class="fas fa-feather-alt"></i> Diary Book <i class="fas fa-leaf"></i>
            </h1>
            <p>tulis cerita, hias dengan gaya</p>
            <div class="deco-flowers">🌸 🌼 🌸 🌼 🌸</div>
            <div class="stats-bar">
                <span><i class="fas fa-book-open"></i> <span id="entryCount">0</span> catatan</span>
                <span><i class="fas fa-pen-fancy"></i> <span id="wordCount">0</span> kata</span>
            </div>
        </header>

        <!-- TOGGLE FORM -->
        <div class="toggle-form-wrapper">
            <button class="btn btn-primary" id="toggleFormBtn">
                <i class="fas fa-plus-circle"></i> <span id="toggleFormText">Buat Catatan Baru</span>
            </button>
        </div>

        <!-- FORM -->
        <div class="form-container" id="formContainer">
            <div class="form-title">
                <i class="fas fa-pen-nib"></i> <span id="formTitleText">✍️ Tulis Catatan Baru</span>
            </div>
            <form id="diaryForm" autocomplete="off">
                <!-- hidden ID untuk edit -->
                <input type="hidden" id="entryId" value="" />

                <div class="form-row">
                    <div class="form-group">
                        <label for="entryTitle">Judul</label>
                        <input type="text" id="entryTitle" placeholder="Misal: Hari yang indah..." required />
                    </div>
                    <div class="form-group">
                        <label for="entryDate">Tanggal</label>
                        <input type="date" id="entryDate" required />
                    </div>
                </div>

                <div class="form-group">
                    <label for="entryContent">Isi Cerita</label>
                    <textarea id="entryContent" placeholder="Tuliskan perasaan, kenangan, atau ceritamu di sini..." required></textarea>
                </div>

                <div class="form-row">
                    <div class="form-group">
                        <label>🎨 Warna Tema</label>
                        <div class="color-themes" id="colorPicker">
                            <div class="theme-dot active" data-color="#ab47bc" style="background:#ab47bc;" title="Ungu"></div>
                            <div class="theme-dot" data-color="#e91e63" style="background:#e91e63;" title="Merah Muda"></div>
                            <div class="theme-dot" data-color="#ff6f00" style="background:#ff6f00;" title="Oranye"></div>
                            <div class="theme-dot" data-color="#2e7d32" style="background:#2e7d32;" title="Hijau"></div>
                            <div class="theme-dot" data-color="#1565c0" style="background:#1565c0;" title="Biru"></div>
                            <div class="theme-dot" data-color="#6a1b9a" style="background:#6a1b9a;" title="Ungu Tua"></div>
                            <div class="theme-dot" data-color="#c62828" style="background:#c62828;" title="Merah"></div>
                            <div class="theme-dot" data-color="#00838f" style="background:#00838f;" title="Teal"></div>
                        </div>
                    </div>
                    <div class="form-group">
                        <label>😊 Stiker</label>
                        <div class="sticker-picker" id="stickerPicker">
                            <div class="sticker-option active" data-sticker="🌸">🌸</div>
                            <div class="sticker-option" data-sticker="🌼">🌼</div>
                            <div class="sticker-option" data-sticker="🌻">🌻</div>
                            <div class="sticker-option" data-sticker="🌺">🌺</div>
                            <div class="sticker-option" data-sticker="🦋">🦋</div>
                            <div class="sticker-option" data-sticker="⭐">⭐</div>
                            <div class="sticker-option" data-sticker="🌈">🌈</div>
                            <div class="sticker-option" data-sticker="💖">💖</div>
                        </div>
                    </div>
                </div>

                <div style="display:flex; gap:14px; flex-wrap:wrap; margin-top:6px;">
                    <button type="submit" class="btn btn-primary" style="flex:1;">
                        <i class="fas fa-save"></i> Simpan Catatan
                    </button>
                    <button type="button" class="btn btn-secondary" id="cancelEditBtn" style="display:none;">
                        <i class="fas fa-times"></i> Batal
                    </button>
                </div>
            </form>
        </div>

        <!-- DIARY GRID -->
        <div class="diary-grid" id="diaryGrid">
            <!-- akan diisi oleh JS -->
        </div>

    </div>

    <script>
        // ============================================================
        //  DATA & STATE
        // ============================================================
        let entries = [];
        let editingId = null;
        let deleteTargetId = null;

        // ============================================================
        //  DOM REFS
        // ============================================================
        const formContainer = document.getElementById('formContainer');
        const toggleFormBtn = document.getElementById('toggleFormBtn');
        const toggleFormText = document.getElementById('toggleFormText');
        const formTitleText = document.getElementById('formTitleText');
        const diaryForm = document.getElementById('diaryForm');
        const entryId = document.getElementById('entryId');
        const entryTitle = document.getElementById('entryTitle');
        const entryDate = document.getElementById('entryDate');
        const entryContent = document.getElementById('entryContent');
        const colorPicker = document.getElementById('colorPicker');
        const stickerPicker = document.getElementById('stickerPicker');
        const cancelEditBtn = document.getElementById('cancelEditBtn');
        const diaryGrid = document.getElementById('diaryGrid');
        const entryCount = document.getElementById('entryCount');
        const wordCount = document.getElementById('wordCount');
        const toast = document.getElementById('toast');
        const toastMessage = document.getElementById('toastMessage');
        const confirmModal = document.getElementById('confirmModal');
        const modalConfirm = document.getElementById('modalConfirm');
        const modalCancel = document.getElementById('modalCancel');

        // ============================================================
        //  HELPERS
        // ============================================================
        function getSelectedColor() {
            const active = colorPicker.querySelector('.theme-dot.active');
            return active ? active.dataset.color : '#ab47bc';
        }

        function getSelectedSticker() {
            const active = stickerPicker.querySelector('.sticker-option.active');
            return active ? active.dataset.sticker : '🌸';
        }

        function formatDate(dateStr) {
            if (!dateStr) return '';
            const d = new Date(dateStr + 'T00:00:00');
            const options = { day: 'numeric', month: 'long', year: 'numeric' };
            return d.toLocaleDateString('id-ID', options);
        }

        function countWords(text) {
            const clean = text.trim();
            if (!clean) return 0;
            return clean.split(/\s+/).length;
        }

        function generateId() {
            return Date.now().toString(36) + Math.random().toString(36).slice(2, 6);
        }

        // ============================================================
        //  TOAST
        // ============================================================
        let toastTimeout = null;

        function showToast(msg, icon = 'fa-check-circle') {
            toastMessage.textContent = msg;
            toast.querySelector('i').className = `fas ${icon}`;
            toast.classList.add('show');
            clearTimeout(toastTimeout);
            toastTimeout = setTimeout(() => {
                toast.classList.remove('show');
            }, 2800);
        }

        // ============================================================
        //  MODAL CONFIRM
        // ============================================================
        function showConfirmModal(id) {
            deleteTargetId = id;
            confirmModal.classList.add('active');
        }

        modalCancel.addEventListener('click', () => {
            confirmModal.classList.remove('active');
            deleteTargetId = null;
        });

        modalConfirm.addEventListener('click', () => {
            confirmModal.classList.remove('active');
            if (deleteTargetId !== null) {
                deleteEntry(deleteTargetId);
                deleteTargetId = null;
            }
        });

        // close modal on overlay click
        confirmModal.addEventListener('click', (e) => {
            if (e.target === confirmModal) {
                confirmModal.classList.remove('active');
                deleteTargetId = null;
            }
        });

        // ============================================================
        //  LOCAL STORAGE
        // ============================================================
        function loadEntries() {
            try {
                const data = localStorage.getItem('diaryEntries');
                entries = data ? JSON.parse(data) : [];
            } catch {
                entries = [];
            }
        }

        function saveEntries() {
            localStorage.setItem('diaryEntries', JSON.stringify(entries));
        }

        // ============================================================
        //  RENDER
        // ============================================================
        function render() {
            if (entries.length === 0) {
                diaryGrid.innerHTML = `
                    <div class="empty-state">
                        <i class="fas fa-book-open"></i>
                        <h3>Belum ada catatan</h3>
                        <p>Mulai tulis cerita pertamamu ✨</p>
                    </div>
                `;
            } else {
                let html = '';
                // Urutkan dari yang terbaru
                const sorted = [...entries].sort((a, b) => b.date.localeCompare(a.date) || a.id.localeCompare(b.id));
                for (const entry of sorted) {
                    const color = entry.color || '#ab47bc';
                    const sticker = entry.sticker || '🌸';
                    const dateFormatted = formatDate(entry.date);
                    html += `
                        <div class="diary-card" style="--theme-color:${color}; --theme-light:${color}44;">
                            <div class="card-header">
                                <span class="card-sticker">${sticker}</span>
                                <span class="card-date"><i class="far fa-calendar-alt"></i> ${dateFormatted}</span>
                            </div>
                            <div class="card-title">${escapeHtml(entry.title)}</div>
                            <div class="card-body">${escapeHtml(entry.content)}</div>
                            <div class="card-actions">
                                <button class="btn btn-secondary btn-sm" onclick="editEntry('${entry.id}')">
                                    <i class="fas fa-pen"></i> Edit
                                </button>
                                <button class="btn btn-danger btn-sm" onclick="showConfirmModal('${entry.id}')">
                                    <i class="fas fa-trash-alt"></i> Hapus
                                </button>
                            </div>
                        </div>
                    `;
                }
                diaryGrid.innerHTML = html;
            }

            // Update stats
            entryCount.textContent = entries.length;
            const totalWords = entries.reduce((sum, e) => sum + countWords(e.content), 0);
            wordCount.textContent = totalWords;
        }

        function escapeHtml(text) {
            const div = document.createElement('div');
            div.textContent = text;
            return div.innerHTML;
        }

        // ============================================================
        //  CRUD
        // ============================================================
        function addEntry(title, date, content, color, sticker) {
            const entry = {
                id: generateId(),
                title: title.trim(),
                date: date,
                content: content.trim(),
                color: color,
                sticker: sticker,
                createdAt: new Date().toISOString()
            };
            entries.push(entry);
            saveEntries();
            render();
            showToast('Catatan berhasil disimpan! 🌸', 'fa-check-circle');
        }

        function updateEntry(id, title, date, content, color, sticker) {
            const idx = entries.findIndex(e => e.id === id);
            if (idx === -1) return;
            entries[idx] = {
                ...entries[idx],
                title: title.trim(),
                date: date,
                content: content.trim(),
                color: color,
                sticker: sticker
            };
            saveEntries();
            render();
            showToast('Catatan diperbarui ✨', 'fa-pen-fancy');
        }

        function deleteEntry(id) {
            entries = entries.filter(e => e.id !== id);
            saveEntries();
            render();
            showToast('Catatan dihapus 🕊️', 'fa-trash-alt');
        }

        // ============================================================
        //  EDIT
        // ============================================================
        function editEntry(id) {
            const entry = entries.find(e => e.id === id);
            if (!entry) return;

            editingId = id;
            entryId.value = id;
            entryTitle.value = entry.title;
            entryDate.value = entry.date;
            entryContent.value = entry.content;

            // Set color
            colorPicker.querySelectorAll('.theme-dot').forEach(el => {
                el.classList.toggle('active', el.dataset.color === entry.color);
            });

            // Set sticker
            stickerPicker.querySelectorAll('.sticker-option').forEach(el => {
                el.classList.toggle('active', el.dataset.sticker === entry.sticker);
            });

            formTitleText.textContent = '✏️ Edit Catatan';
            toggleFormText.textContent = 'Tutup Form';
            cancelEditBtn.style.display = 'inline-flex';
            formContainer.classList.add('open');
            window.scrollTo({ top: formContainer.offsetTop - 20, behavior: 'smooth' });
        }

        // ============================================================
        //  FORM HANDLING
        // ============================================================
        function resetForm() {
            diaryForm.reset();
            entryId.value = '';
            editingId = null;
            // reset color & sticker to default
            colorPicker.querySelectorAll('.theme-dot').forEach(el => {
                el.classList.toggle('active', el.dataset.color === '#ab47bc');
            });
            stickerPicker.querySelectorAll('.sticker-option').forEach(el => {
                el.classList.toggle('active', el.dataset.sticker === '🌸');
            });
            formTitleText.textContent = '✍️ Tulis Catatan Baru';
            cancelEditBtn.style.display = 'none';
        }

        toggleFormBtn.addEventListener('click', () => {
            const isOpen = formContainer.classList.contains('open');
            if (isOpen) {
                formContainer.classList.remove('open');
                toggleFormText.textContent = 'Buat Catatan Baru';
                resetForm();
            } else {
                formContainer.classList.add('open');
                toggleFormText.textContent = 'Tutup Form';
                resetForm();
                // Set default date
                if (!entryDate.value) {
                    const today = new Date().toISOString().split('T')[0];
                    entryDate.value = today;
                }
                window.scrollTo({ top: formContainer.offsetTop - 20, behavior: 'smooth' });
            }
        });

        cancelEditBtn.addEventListener('click', () => {
            resetForm();
            formContainer.classList.remove('open');
            toggleFormText.textContent = 'Buat Catatan Baru';
            showToast('Edit dibatalkan', 'fa-undo');
        });

        // ============================================================
        //  FORM SUBMIT
        // ============================================================
        diaryForm.addEventListener('submit', (e) => {
            e.preventDefault();

            const title = entryTitle.value.trim();
            const date = entryDate.value;
            const content = entryContent.value.trim();
            const color = getSelectedColor();
            const sticker = getSelectedSticker();

            if (!title || !date || !content) {
                showToast('Harap lengkapi semua field!', 'fa-exclamation-circle');
                return;
            }

            const id = entryId.value;
            if (id) {
                // Edit mode
                updateEntry(id, title, date, content, color, sticker);
                resetForm();
                formContainer.classList.remove('open');
                toggleFormText.textContent = 'Buat Catatan Baru';
            } else {
                // Add mode
                addEntry(title, date, content, color, sticker);
                resetForm();
                // tetap buka form agar bisa nambah lagi
                // reset date
                const today = new Date().toISOString().split('T')[0];
                entryDate.value = today;
            }
        });

        // ============================================================
        //  COLOR PICKER CLICKS
        // ============================================================
        colorPicker.addEventListener('click', (e) => {
            const dot = e.target.closest('.theme-dot');
            if (!dot) return;
            colorPicker.querySelectorAll('.theme-dot').forEach(el => el.classList.remove('active'));
            dot.classList.add('active');
        });

        // ============================================================
        //  STICKER PICKER CLICKS
        // ============================================================
        stickerPicker.addEventListener('click', (e) => {
            const opt = e.target.closest('.sticker-option');
            if (!opt) return;
            stickerPicker.querySelectorAll('.sticker-option').forEach(el => el.classList.remove('active'));
            opt.classList.add('active');
        });

        // ============================================================
        //  INIT
        // ============================================================
        loadEntries();
        render();

        // set default date di form jika kosong
        const today = new Date().toISOString().split('T')[0];
        if (!entryDate.value) {
            entryDate.value = today;
        }

        // tampilkan form jika belum ada entri? biar user langsung nulis
        if (entries.length === 0) {
            // otomatis buka form untuk first user
            setTimeout(() => {
                formContainer.classList.add('open');
                toggleFormText.textContent = 'Tutup Form';
                window.scrollTo({ top: formContainer.offsetTop - 20, behavior: 'smooth' });
            }, 400);
        }

        console.log('🌸 Diary Book siap digunakan!');
    </script>

</body>
</html>
