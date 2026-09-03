<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Junior Champions - Medan & Gaya Listrik</title>
    <style>
        /* ============================================================
                   ROOT & RESET
                   ============================================================ */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #1A73E8;
            --primary-dark: #1557B0;
            --primary-light: #E8F0FE;
            --secondary: #FF6B35;
            --success: #34A853;
            --danger: #EA4335;
            --warning: #FBBC04;
            --purple: #7C3AED;
            --bg: #F1F5F9;
            --card: #FFFFFF;
            --text-primary: #1E293B;
            --text-secondary: #475569;
            --border: #E2E8F0;
            --shadow: 0 8px 32px rgba(0, 0, 0, 0.10);
            --radius: 20px;
        }

        body {
            font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
            background: var(--bg);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        /* ============================================================
                   APP CONTAINER
                   ============================================================ */
        .app-container {
            max-width: 920px;
            width: 100%;
            background: var(--card);
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            overflow: hidden;
            position: relative;
        }

        /* ============================================================
                   HEADER - AdaptoX Style
                   ============================================================ */
        .header {
            background: linear-gradient(135deg, #1A73E8 0%, #0D47A1 100%);
            padding: 20px 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 12px;
        }

        .header-left {
            display: flex;
            align-items: center;
            gap: 14px;
        }

        .logo-icon {
            width: 44px;
            height: 44px;
            background: rgba(255, 255, 255, 0.20);
            border-radius: 14px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            font-weight: 900;
            color: #fff;
            backdrop-filter: blur(4px);
        }

        .logo-text h1 {
            font-size: 20px;
            font-weight: 800;
            color: #fff;
            letter-spacing: -0.3px;
        }

        .logo-text span {
            font-size: 12px;
            font-weight: 600;
            color: rgba(255, 255, 255, 0.80);
            background: rgba(255, 255, 255, 0.15);
            padding: 2px 14px;
            border-radius: 30px;
            display: inline-block;
            margin-top: 2px;
        }

        .header-right {
            display: flex;
            align-items: center;
            gap: 12px;
            flex-wrap: wrap;
        }

        .badge-level {
            background: rgba(255, 255, 255, 0.20);
            backdrop-filter: blur(4px);
            color: #fff;
            padding: 6px 18px;
            border-radius: 40px;
            font-weight: 700;
            font-size: 13px;
            border: 1px solid rgba(255, 255, 255, 0.15);
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .badge-score {
            background: var(--secondary);
            color: #fff;
            padding: 6px 16px;
            border-radius: 40px;
            font-weight: 700;
            font-size: 13px;
        }

        /* ============================================================
                   CHAPTER SELECTOR
                   ============================================================ */
        .chapter-selector {
            padding: 14px 30px;
            background: #F8FAFC;
            border-bottom: 1px solid var(--border);
            display: flex;
            align-items: center;
            gap: 16px;
            flex-wrap: wrap;
        }

        .chapter-selector label {
            font-weight: 700;
            font-size: 14px;
            color: var(--text-secondary);
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .chapter-buttons {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }

        .chapter-btn {
            padding: 6px 20px;
            border: 2px solid var(--border);
            border-radius: 40px;
            background: #fff;
            font-weight: 600;
            font-size: 13px;
            color: var(--text-secondary);
            cursor: pointer;
            transition: all 0.25s ease;
            font-family: inherit;
        }

        .chapter-btn:hover {
            border-color: var(--primary);
            color: var(--primary);
            background: var(--primary-light);
        }

        .chapter-btn.active {
            background: var(--primary);
            border-color: var(--primary);
            color: #fff;
            box-shadow: 0 4px 14px rgba(26, 115, 232, 0.30);
        }

        .chapter-btn .badge-count {
            background: rgba(0, 0, 0, 0.10);
            padding: 0 8px;
            border-radius: 30px;
            font-size: 11px;
        }

        .chapter-btn.active .badge-count {
            background: rgba(255, 255, 255, 0.25);
        }

        /* ============================================================
                   PROGRESS BAR
                   ============================================================ */
        .progress-section {
            padding: 14px 30px;
            background: #F8FAFC;
            border-bottom: 1px solid var(--border);
            display: flex;
            align-items: center;
            gap: 16px;
            flex-wrap: wrap;
        }

        .progress-label {
            font-size: 13px;
            font-weight: 600;
            color: var(--text-secondary);
            white-space: nowrap;
        }

        .progress-bar-wrapper {
            flex: 1;
            min-width: 120px;
            height: 8px;
            background: #E2E8F0;
            border-radius: 30px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            width: 0%;
            background: linear-gradient(90deg, var(--primary), var(--purple));
            border-radius: 30px;
            transition: width 0.6s cubic-bezier(0.22, 1, 0.36, 1);
        }

        .progress-text {
            font-size: 14px;
            font-weight: 700;
            color: var(--text-primary);
            min-width: 70px;
            text-align: right;
        }

        /* ============================================================
                   QUESTION CARD
                   ============================================================ */
        .question-card {
            padding: 30px 30px 20px;
        }

        .question-meta {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 16px;
            flex-wrap: wrap;
            gap: 8px;
        }

        .question-number {
            font-size: 13px;
            font-weight: 700;
            color: var(--primary);
            background: var(--primary-light);
            padding: 4px 18px;
            border-radius: 30px;
            letter-spacing: 0.3px;
        }

        .question-tag {
            font-size: 12px;
            font-weight: 600;
            color: var(--text-secondary);
            background: #F1F5F9;
            padding: 4px 14px;
            border-radius: 30px;
        }

        .question-text {
            font-size: 20px;
            font-weight: 600;
            line-height: 1.7;
            color: var(--text-primary);
            margin-bottom: 28px;
            padding: 4px 0;
        }

        .question-text .highlight {
            color: var(--primary);
            background: var(--primary-light);
            padding: 0 6px;
            border-radius: 6px;
        }

        .question-text .formula {
            display: inline-block;
            background: #F1F5F9;
            padding: 2px 14px;
            border-radius: 8px;
            font-family: 'Cambria', 'Times New Roman', serif;
            font-style: italic;
            font-size: 22px;
            color: var(--primary-dark);
            margin: 4px 0;
        }

        /* ============================================================
                   OPTIONS
                   ============================================================ */
        .options-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 12px;
            margin-bottom: 8px;
        }

        @media (max-width: 580px) {
            .options-grid {
                grid-template-columns: 1fr;
            }
        }

        .option-btn {
            background: #F8FAFC;
            border: 2px solid #E9EDF2;
            border-radius: 16px;
            padding: 16px 20px;
            font-size: 15px;
            font-weight: 500;
            color: var(--text-primary);
            cursor: pointer;
            transition: all 0.25s ease;
            display: flex;
            align-items: center;
            gap: 14px;
            text-align: left;
            width: 100%;
            font-family: inherit;
            line-height: 1.4;
        }

        .option-btn:hover:not(.disabled) {
            background: var(--primary-light);
            border-color: var(--primary);
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(26, 115, 232, 0.15);
        }

        .option-btn .letter {
            width: 34px;
            height: 34px;
            background: #E9EDF2;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 800;
            font-size: 14px;
            color: var(--text-secondary);
            flex-shrink: 0;
            transition: 0.25s;
        }

        .option-btn .option-text {
            flex: 1;
        }

        .option-btn.correct {
            border-color: var(--success);
            background: #ECFDF5;
            box-shadow: 0 0 0 3px rgba(52, 168, 83, 0.15);
        }
        .option-btn.correct .letter {
            background: var(--success);
            color: #fff;
        }

        .option-btn.wrong {
            border-color: var(--danger);
            background: #FEF2F2;
            box-shadow: 0 0 0 3px rgba(234, 67, 53, 0.12);
        }
        .option-btn.wrong .letter {
            background: var(--danger);
            color: #fff;
        }

        .option-btn.show-correct {
            border-color: var(--success);
            background: #ECFDF5;
        }
        .option-btn.show-correct .letter {
            background: var(--success);
            color: #fff;
        }

        .option-btn.disabled {
            cursor: default;
            opacity: 0.85;
        }
        .option-btn.disabled:hover {
            transform: none;
            box-shadow: none;
        }

        /* ============================================================
                   FEEDBACK
                   ============================================================ */
        .feedback-box {
            margin-top: 20px;
            padding: 16px 22px;
            border-radius: 16px;
            font-weight: 500;
            font-size: 15px;
            display: none;
            align-items: center;
            gap: 12px;
            animation: fadeSlide 0.35s ease;
        }

        @keyframes fadeSlide {
            0% {
                opacity: 0;
                transform: translateY(8px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .feedback-box.show {
            display: flex;
        }

        .feedback-box.success {
            background: #ECFDF5;
            color: #065F46;
            border-left: 5px solid var(--success);
        }

        .feedback-box.error {
            background: #FEF2F2;
            color: #991B1B;
            border-left: 5px solid var(--danger);
        }

        .feedback-box .fb-icon {
            font-size: 24px;
            flex-shrink: 0;
        }
        .feedback-box .fb-text {
            flex: 1;
        }
        .feedback-box .fb-answer {
            font-weight: 700;
            background: rgba(0, 0, 0, 0.06);
            padding: 2px 12px;
            border-radius: 30px;
            font-size: 14px;
        }
        .feedback-box .fb-explanation {
            font-size: 13px;
            font-weight: 400;
            opacity: 0.85;
            margin-top: 4px;
            width: 100%;
        }

        /* ============================================================
                   NAVIGATION
                   ============================================================ */
        .nav-section {
            padding: 16px 30px 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 12px;
            border-top: 1px solid var(--border);
        }

        .nav-left,
        .nav-right {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }

        .btn {
            padding: 11px 28px;
            border: none;
            border-radius: 40px;
            font-weight: 700;
            font-size: 14px;
            cursor: pointer;
            transition: all 0.25s ease;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            font-family: inherit;
        }

        .btn-primary {
            background: var(--primary);
            color: #fff;
            box-shadow: 0 4px 16px rgba(26, 115, 232, 0.30);
        }
        .btn-primary:hover:not(:disabled) {
            background: var(--primary-dark);
            transform: translateY(-2px);
            box-shadow: 0 8px 24px rgba(26, 115, 232, 0.40);
        }
        .btn-primary:disabled {
            opacity: 0.40;
            cursor: not-allowed;
            transform: none;
        }

        .btn-secondary {
            background: #E9EDF2;
            color: var(--text-secondary);
        }
        .btn-secondary:hover:not(:disabled) {
            background: #D6DCE6;
        }
        .btn-secondary:disabled {
            opacity: 0.35;
            cursor: not-allowed;
        }

        .btn-outline {
            background: transparent;
            border: 2px solid #CBD5E1;
            color: var(--text-secondary);
        }
        .btn-outline:hover {
            background: #F1F5F9;
            border-color: #94A3B8;
        }

        .btn-success {
            background: var(--success);
            color: #fff;
            box-shadow: 0 4px 16px rgba(52, 168, 83, 0.30);
        }
        .btn-success:hover {
            background: #2D9248;
            transform: translateY(-2px);
        }

        .btn-purple {
            background: var(--purple);
            color: #fff;
            box-shadow: 0 4px 16px rgba(124, 58, 237, 0.30);
        }
        .btn-purple:hover {
            background: #6D28D9;
            transform: translateY(-2px);
        }

        /* ============================================================
                   EDITOR
                   ============================================================ */
        .editor-toggle {
            padding: 10px 30px 18px;
            display: flex;
            justify-content: flex-end;
        }

        .editor-toggle-btn {
            background: transparent;
            border: none;
            color: var(--text-secondary);
            font-weight: 600;
            font-size: 13px;
            cursor: pointer;
            padding: 6px 16px;
            border-radius: 30px;
            transition: 0.2s;
            display: flex;
            align-items: center;
            gap: 6px;
        }
        .editor-toggle-btn:hover {
            background: #F1F5F9;
            color: var(--text-primary);
        }

        .editor-panel {
            padding: 0 30px 30px;
            display: none;
            animation: fadeSlide 0.3s ease;
        }
        .editor-panel.open {
            display: block;
        }

        .editor-panel .editor-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 14px;
            flex-wrap: wrap;
            gap: 8px;
        }

        .editor-panel .editor-header h3 {
            font-size: 17px;
            font-weight: 700;
            color: var(--text-primary);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .editor-panel .editor-header .editor-badge {
            background: var(--primary-light);
            color: var(--primary);
            font-size: 11px;
            padding: 2px 12px;
            border-radius: 30px;
            font-weight: 600;
        }

        .editor-tabs {
            display: flex;
            gap: 8px;
            margin-bottom: 12px;
            flex-wrap: wrap;
        }

        .editor-tab {
            padding: 6px 18px;
            border: 2px solid var(--border);
            border-radius: 30px;
            background: #fff;
            font-weight: 600;
            font-size: 13px;
            color: var(--text-secondary);
            cursor: pointer;
            transition: 0.2s;
            font-family: inherit;
        }
        .editor-tab:hover {
            border-color: var(--primary);
            color: var(--primary);
        }
        .editor-tab.active {
            border-color: var(--primary);
            background: var(--primary);
            color: #fff;
        }

        .editor-panel textarea {
            width: 100%;
            min-height: 380px;
            padding: 18px 20px;
            font-family: 'JetBrains Mono', 'Courier New', monospace;
            font-size: 13px;
            line-height: 1.7;
            border: 2px solid var(--border);
            border-radius: 16px;
            background: #FAFCFF;
            color: var(--text-primary);
            resize: vertical;
            transition: 0.2s;
        }
        .editor-panel textarea:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 4px rgba(26, 115, 232, 0.10);
        }

        .editor-actions {
            display: flex;
            gap: 10px;
            margin-top: 14px;
            flex-wrap: wrap;
        }

        .editor-info {
            font-size: 13px;
            color: var(--text-secondary);
            background: #F8FAFC;
            padding: 10px 16px;
            border-radius: 12px;
            margin-bottom: 14px;
            border: 1px solid var(--border);
            line-height: 1.6;
        }
        .editor-info code {
            background: #E9EDF2;
            padding: 1px 8px;
            border-radius: 6px;
            font-size: 12px;
            font-weight: 600;
        }

        /* ============================================================
                   RESPONSIVE
                   ============================================================ */
        @media (max-width: 640px) {
            body {
                padding: 10px;
            }
            .header {
                padding: 16px 18px;
            }
            .logo-text h1 {
                font-size: 16px;
            }
            .badge-level {
                font-size: 11px;
                padding: 4px 12px;
            }
            .badge-score {
                font-size: 11px;
                padding: 4px 12px;
            }
            .question-card {
                padding: 20px 18px 14px;
            }
            .question-text {
                font-size: 17px;
            }
            .option-btn {
                padding: 13px 16px;
                font-size: 14px;
            }
            .option-btn .letter {
                width: 30px;
                height: 30px;
                font-size: 12px;
            }
            .nav-section {
                padding: 14px 18px 20px;
                flex-direction: column;
                align-items: stretch;
            }
            .nav-left,
            .nav-right {
                justify-content: center;
            }
            .btn {
                padding: 9px 18px;
                font-size: 13px;
                flex: 1;
                justify-content: center;
            }
            .progress-section {
                padding: 12px 18px;
            }
            .chapter-selector {
                padding: 12px 18px;
                flex-direction: column;
                align-items: stretch;
            }
            .chapter-buttons {
                justify-content: center;
            }
            .editor-panel {
                padding: 0 18px 20px;
            }
            .editor-panel textarea {
                min-height: 250px;
                font-size: 12px;
                padding: 14px;
            }
            .editor-toggle {
                padding: 6px 18px 12px;
            }
        }
    </style>
</head>
<body>

    <div class="app-container" id="app">

        <!-- ============================================================
        HEADER
        ============================================================ -->
        <header class="header">
            <div class="header-left">
                <div class="logo-icon">⚡</div>
                <div class="logo-text">
                    <h1>Junior Champions</h1>
                    <span>AdaptoX · SMP</span>
                </div>
            </div>
            <div class="header-right">
                <div class="badge-level" id="levelBadge">🌟 Level 1</div>
                <div class="badge-score" id="scoreBadge">🎯 0%</div>
            </div>
        </header>

        <!-- ============================================================
        CHAPTER SELECTOR
        ============================================================ -->
        <div class="chapter-selector">
            <label>📚 Pilih Bab:</label>
            <div class="chapter-buttons" id="chapterButtons">
                <button class="chapter-btn active" data-chapter="0">
                    ⚡ Medan Listrik <span class="badge-count">10</span>
                </button>
                <button class="chapter-btn" data-chapter="1">
                    🔋 Gaya Listrik <span class="badge-count">10</span>
                </button>
            </div>
        </div>

        <!-- ============================================================
        PROGRESS
        ============================================================ -->
        <div class="progress-section">
            <span class="progress-label">📊 Progress</span>
            <div class="progress-bar-wrapper">
                <div class="progress-fill" id="progressFill" style="width:0%;"></div>
            </div>
            <span class="progress-text" id="progressText">0 / 0</span>
        </div>

        <!-- ============================================================
        QUESTION CARD
        ============================================================ -->
        <div class="question-card" id="questionCard">
            <div class="question-meta">
                <span class="question-number" id="questionNumber">Soal 1</span>
                <span class="question-tag" id="questionTag">📘 Materi</span>
            </div>
            <div class="question-text" id="questionText">
                Memuat soal...
            </div>
            <div class="options-grid" id="optionsContainer"></div>
            <div class="feedback-box" id="feedbackBox">
                <span class="fb-icon" id="fbIcon">✅</span>
                <span class="fb-text" id="fbMessage">Jawaban benar!</span>
                <span class="fb-answer" id="fbAnswer"></span>
                <div class="fb-explanation" id="fbExplanation"></div>
            </div>
        </div>

        <!-- ============================================================
        NAVIGATION
        ============================================================ -->
        <div class="nav-section">
            <div class="nav-left">
                <button class="btn btn-secondary" id="prevBtn" disabled>
                    ⬅ Sebelumnya
                </button>
                <button class="btn btn-outline" id="resetBtn">
                    🔄 Ulangi Bab
                </button>
            </div>
            <div class="nav-right">
                <button class="btn btn-primary" id="nextBtn">
                    Selanjutnya ➡
                </button>
            </div>
        </div>

        <!-- ============================================================
        EDITOR TOGGLE
        ============================================================ -->
        <div class="editor-toggle">
            <button class="editor-toggle-btn" id="toggleEditorBtn">
                ✏️ Edit Soal
            </button>
        </div>

        <!-- ============================================================
        EDITOR PANEL
        ============================================================ -->
        <div class="editor-panel" id="editorPanel">
            <div class="editor-header">
                <h3>
                    📝 Editor Soal
                    <span class="editor-badge">JSON</span>
                </h3>
                <span style="font-size:13px; color:var(--text-secondary);">
                    Total: <strong id="editorTotal">0</strong> soal
                </span>
            </div>

            <div class="editor-tabs" id="editorTabs">
                <button class="editor-tab active" data-editor-chapter="0">⚡ Medan Listrik</button>
                <button class="editor-tab" data-editor-chapter="1">🔋 Gaya Listrik</button>
            </div>

            <div class="editor-info">
                💡 <strong>Format:</strong> <code>soal</code>, <code>pilihan</code> (A/B/C/D),
                <code>jawaban</code> (huruf), <code>level</code> (1-3), <code>materi</code>,
                <code>penjelasan</code> (opsional). Edit lalu klik <strong>"💾 Simpan"</strong>.
            </div>

            <textarea id="editorTextarea" spellcheck="false"></textarea>

            <div class="editor-actions">
                <button class="btn btn-success" id="saveEditorBtn">💾 Simpan & Muat</button>
                <button class="btn btn-purple" id="resetEditorBtn">↺ Reset Default</button>
                <button class="btn btn-secondary" id="formatEditorBtn">📐 Format JSON</button>
            </div>
        </div>

    </div>

    <!-- ============================================================
    JAVASCRIPT
    ============================================================ -->
    <script>
        // ============================================================
        //  DATA SOAL - BAB 1: MEDAN LISTRIK (10 Soal)
        //  BAB 2: GAYA LISTRIK (10 Soal)
        // ============================================================
        const CHAPTERS = [{
            name: "Medan Listrik",
            icon: "⚡",
            questions: [{
                id: 1,
                level: 1,
                materi: "Medan Listrik",
                soal: "Apa yang dimaksud dengan medan listrik?",
                pilihan: {
                    A: "Daerah di sekitar muatan listrik yang masih dipengaruhi gaya listrik",
                    B: "Aliran elektron dalam suatu penghantar",
                    C: "Gaya tarik antara dua muatan yang berlawanan",
                    D: "Energi yang tersimpan dalam baterai"
                },
                jawaban: "A",
                penjelasan: "Medan listrik adalah daerah di sekitar muatan listrik di mana muatan lain masih merasakan gaya listrik."
            }, {
                id: 2,
                level: 1,
                materi: "Medan Listrik",
                soal: "Arah garis-garis medan listrik pada muatan positif adalah ....",
                pilihan: {
                    A: "Masuk ke muatan",
                    B: "Keluar dari muatan",
                    C: "Melingkar mengelilingi muatan",
                    D: "Tidak memiliki arah"
                },
                jawaban: "B",
                penjelasan: "Garis medan listrik pada muatan positif selalu keluar (radial keluar), sedangkan pada muatan negatif masuk."
            }, {
                id: 3,
                level: 1,
                materi: "Medan Listrik",
                soal: "Satuan dari kuat medan listrik dalam SI adalah ....",
                pilihan: {
                    A: "Newton (N)",
                    B: "Coulomb (C)",
                    C: "Newton per Coulomb (N/C)",
                    D: "Volt (V)"
                },
                jawaban: "C",
                penjelasan: "Kuat medan listrik (E) = F/q, satuannya Newton/Coulomb (N/C)."
            }, {
                id: 4,
                level: 1,
                materi: "Medan Listrik",
                soal: "Jika jarak suatu titik dari muatan sumber diperbesar 2 kali, maka kuat medan listrik di titik tersebut menjadi ....",
                pilihan: {
                    A: "2 kali lebih besar",
                    B: "4 kali lebih besar",
                    C: "2 kali lebih kecil",
                    D: "4 kali lebih kecil"
                },
                jawaban: "D",
                penjelasan: "E ∝ 1/r², jadi jika r diperbesar 2x, E menjadi 1/4 kali (4 kali lebih kecil)."
            }, {
                id: 5,
                level: 2,
                materi: "Medan Listrik",
                soal: "Dua muatan +Q dan -Q terpisah sejauh d. Pada titik tengah antara kedua muatan, arah medan listrik adalah ....",
                pilihan: {
                    A: "Menuju muatan positif",
                    B: "Menuju muatan negatif",
                    C: "Ke arah kanan",
                    D: "Nol (saling meniadakan)"
                },
                jawaban: "B",
                penjelasan: "Medan listrik selalu menuju muatan negatif dan menjauhi muatan positif. Di titik tengah, medan dari +Q menuju -Q."
            }, {
                id: 6,
                level: 2,
                materi: "Medan Listrik",
                soal: "Perhatikan pernyataan berikut: (1) Semakin besar muatan sumber, semakin besar kuat medan listrik. (2) Semakin jauh jarak dari muatan sumber, semakin besar kuat medan listrik. (3) Medan listrik adalah besaran vektor. Pernyataan yang benar adalah ....",
                pilihan: {
                    A: "(1) dan (2)",
                    B: "(1) dan (3)",
                    C: "(2) dan (3)",
                    D: "(1), (2), dan (3)"
                },
                jawaban: "B",
                penjelasan: "(1) benar: E ∝ Q. (2) salah: E ∝ 1/r² (semakin jauh, E semakin kecil). (3) benar: medan listrik memiliki arah."
            }, {
                id: 7,
                level: 2,
                materi: "Medan Listrik",
                soal: "Sebuah muatan uji +2 μC diletakkan dalam medan listrik dan mengalami gaya 0,6 N. Kuat medan listrik di titik tersebut adalah ....",
                pilihan: {
                    A: "1,2 × 10⁵ N/C",
                    B: "3,0 × 10⁵ N/C",
                    C: "1,2 × 10⁶ N/C",
                    D: "3,0 × 10⁶ N/C"
                },
                jawaban: "B",
                penjelasan: "E = F/q = 0,6 / (2×10⁻⁶) = 3,0 × 10⁵ N/C."
            }, {
                id: 8,
                level: 2,
                materi: "Medan Listrik",
                soal: "Muatan +5 μC menimbulkan kuat medan listrik sebesar 200 N/C pada jarak tertentu. Jika muatan sumber diganti dengan +10 μC, kuat medan listrik pada jarak yang sama menjadi ....",
                pilihan: {
                    A: "100 N/C",
                    B: "200 N/C",
                    C: "400 N/C",
                    D: "800 N/C"
                },
                jawaban: "C",
                penjelasan: "E ∝ Q, jadi jika Q digandakan, E juga digandakan: 2 × 200 = 400 N/C."
            }, {
                id: 9,
                level: 3,
                materi: "Medan Listrik",
                soal: "Dua muatan +2 μC dan +8 μC terpisah sejauh 6 cm. Di titik mana medan listrik bernilai nol?",
                pilihan: {
                    A: "2 cm dari muatan +2 μC",
                    B: "3 cm dari muatan +2 μC",
                    C: "4 cm dari muatan +2 μC",
                    D: "5 cm dari muatan +2 μC"
                },
                jawaban: "A",
                penjelasan: "E₁ = E₂, kQ₁/r₁² = kQ₂/r₂², 2/r₁² = 8/(6-r₁)², r₁ = 2 cm dari muatan +2 μC."
            }, {
                id: 10,
                level: 3,
                materi: "Medan Listrik",
                soal: "Garis-garis medan listrik yang rapat menunjukkan bahwa ....",
                pilihan: {
                    A: "Medan listrik lemah",
                    B: "Medan listrik kuat",
                    C: "Muatan listrik kecil",
                    D: "Tidak ada muatan"
                },
                jawaban: "B",
                penjelasan: "Kerapatan garis medan listrik menggambarkan besar kuat medan listrik. Semakin rapat, semakin kuat medan listrik."
            }]
        }, {
            name: "Gaya Listrik",
            icon: "🔋",
            questions: [{
                id: 1,
                level: 1,
                materi: "Gaya Listrik",
                soal: "Gaya tarik atau tolak antara dua muatan listrik disebut ....",
                pilihan: {
                    A: "Gaya gravitasi",
                    B: "Gaya Coulomb",
                    C: "Gaya magnet",
                    D: "Gaya normal"
                },
                jawaban: "B",
                penjelasan: "Gaya tarik/tolak antar muatan listrik disebut Gaya Coulomb."
            }, {
                id: 2,
                level: 1,
                materi: "Gaya Listrik",
                soal: "Dua muatan sejenis (misal + dan +) akan ....",
                pilihan: {
                    A: "Saling tarik-menarik",
                    B: "Saling tolak-menolak",
                    C: "Tidak berinteraksi",
                    D: "Bergabung menjadi satu"
                },
                jawaban: "B",
                penjelasan: "Muatan sejenis (++ atau --) saling tolak-menolak, muatan berbeda jenis (+-) saling tarik-menarik."
            }, {
                id: 3,
                level: 1,
                materi: "Gaya Listrik",
                soal: "Bunyi Hukum Coulomb yang benar adalah ....",
                pilihan: {
                    A: "Gaya listrik berbanding lurus dengan jarak",
                    B: "Gaya listrik berbanding terbalik dengan kuadrat jarak",
                    C: "Gaya listrik berbanding lurus dengan kuadrat muatan",
                    D: "Gaya listrik tidak bergantung pada jarak"
                },
                jawaban: "B",
                penjelasan: "Hukum Coulomb: F ∝ Q₁Q₂/r², artinya gaya berbanding terbalik dengan kuadrat jarak."
            }, {
                id: 4,
                level: 1,
                materi: "Gaya Listrik",
                soal: "Jika jarak antara dua muatan diperbesar menjadi 3 kali semula, maka gaya Coulomb menjadi ....",
                pilihan: {
                    A: "3 kali lebih besar",
                    B: "9 kali lebih besar",
                    C: "3 kali lebih kecil",
                    D: "9 kali lebih kecil"
                },
                jawaban: "D",
                penjelasan: "F ∝ 1/r², jika r diperbesar 3x, F menjadi 1/9 kali semula."
            }, {
                id: 5,
                level: 2,
                materi: "Gaya Listrik",
                soal: "Dua muatan +4 μC dan +9 μC terpisah 3 cm. Gaya Coulomb yang terjadi adalah .... (k = 9×10⁹ Nm²/C²)",
                pilihan: {
                    A: "36 N",
                    B: "72 N",
                    C: "108 N",
                    D: "360 N"
                },
                jawaban: "D",
                penjelasan: "F = kQ₁Q₂/r² = 9×10⁹ × 4×10⁻⁶ × 9×10⁻⁶ / (0,03)² = 360 N."
            }, {
                id: 6,
                level: 2,
                materi: "Gaya Listrik",
                soal: "Jika muatan Q₁ diperbesar 2 kali dan muatan Q₂ diperbesar 3 kali, sedangkan jarak tetap, maka gaya Coulomb menjadi ....",
                pilihan: {
                    A: "5 kali semula",
                    B: "6 kali semula",
                    C: "2/3 kali semula",
                    D: "3/2 kali semula"
                },
                jawaban: "B",
                penjelasan: "F ∝ Q₁Q₂, jika Q₁×2 dan Q₂×3, maka F menjadi 2×3 = 6 kali semula."
            }, {
                id: 7,
                level: 2,
                materi: "Gaya Listrik",
                soal: "Dua muatan +10 μC dan -10 μC terpisah 10 cm. Gaya Coulomb yang terjadi adalah .... (k = 9×10⁹ Nm²/C²)",
                pilihan: {
                    A: "9 N (tarik)",
                    B: "9 N (tolak)",
                    C: "90 N (tarik)",
                    D: "90 N (tolak)"
                },
                jawaban: "C",
                penjelasan: "F = 9×10⁹ × 10×10⁻⁶ × 10×10⁻⁶ / (0,1)² = 90 N. Muatan berbeda jenis, jadi tarik-menarik."
            }, {
                id: 8,
                level: 2,
                materi: "Gaya Listrik",
                soal: "Perbandingan gaya Coulomb antara dua muatan di udara dan di air (εᵣ = 80) adalah ....",
                pilihan: {
                    A: "1 : 80",
                    B: "80 : 1",
                    C: "1 : 6400",
                    D: "6400 : 1"
                },
                jawaban: "B",
                penjelasan: "F = k/εᵣ, di udara εᵣ=1, di air εᵣ=80, jadi F_udara : F_air = 80 : 1."
            }, {
                id: 9,
                level: 3,
                materi: "Gaya Listrik",
                soal: "Tiga muatan Q₁=+2μC, Q₂=+8μC, Q₃=-4μC terletak segaris. Q₂ berada di tengah dengan jarak 3 cm dari Q₁ dan 6 cm dari Q₃. Gaya total pada Q₂ adalah .... (k=9×10⁹)",
                pilihan: {
                    A: "40 N ke kiri",
                    B: "40 N ke kanan",
                    C: "160 N ke kiri",
                    D: "160 N ke kanan"
                },
                jawaban: "D",
                penjelasan: "F₂₁ = tolak (kanan) = 9×10⁹×2×8×10⁻¹²/0,03² = 160 N. F₂₃ = tarik (kanan) karena Q₂+ dan Q₃- = 9×10⁹×8×4×10⁻¹²/0,06² = 80 N. Total = 160+80 = 240 N ke kanan."
            }, {
                id: 10,
                level: 3,
                materi: "Gaya Listrik",
                soal: "Dua muatan identik +Q terpisah sejauh d. Jika salah satu muatan diganti dengan -2Q, perbandingan gaya awal dan akhir adalah ....",
                pilihan: {
                    A: "1 : 2",
                    B: "2 : 1",
                    C: "1 : 4",
                    D: "4 : 1"
                },
                jawaban: "A",
                penjelasan: "F_awal = kQ²/d². F_akhir = k(Q)(2Q)/d² = 2kQ²/d². Perbandingan F_awal:F_akhir = 1:2."
            }]
        }];

        // ============================================================
        //  STATE APLIKASI
        // ============================================================
        let currentChapter = 0;
        let questions = [];
        let currentIndex = 0;
        let answered = false;
        let userAnswers = {};

        // DOM Refs
        const $ = id => document.getElementById(id);
        const questionNumber = $('questionNumber');
        const questionTag = $('questionTag');
        const questionText = $('questionText');
        const optionsContainer = $('optionsContainer');
        const feedbackBox = $('feedbackBox');
        const fbIcon = $('fbIcon');
        const fbMessage = $('fbMessage');
        const fbAnswer = $('fbAnswer');
        const fbExplanation = $('fbExplanation');
        const progressFill = $('progressFill');
        const progressText = $('progressText');
        const levelBadge = $('levelBadge');
        const scoreBadge = $('scoreBadge');
        const prevBtn = $('prevBtn');
        const nextBtn = $('nextBtn');
        const resetBtn = $('resetBtn');
        const toggleEditorBtn = $('toggleEditorBtn');
        const editorPanel = $('editorPanel');
        const editorTextarea = $('editorTextarea');
        const saveEditorBtn = $('saveEditorBtn');
        const resetEditorBtn = $('resetEditorBtn');
        const formatEditorBtn = $('formatEditorBtn');
        const editorTotal = $('editorTotal');
        const chapterButtons = document.querySelectorAll('.chapter-btn');
        const editorTabs = document.querySelectorAll('.editor-tab');

        // ============================================================
        //  FUNGSI UTAMA
        // ============================================================

        function loadChapter(chapterIdx) {
            currentChapter = chapterIdx;
            questions = JSON.parse(JSON.stringify(CHAPTERS[chapterIdx].questions));
            currentIndex = 0;
            userAnswers = {};
            answered = false;
            renderQuestion();
            updateProgress();
            updateNavButtons();
            updateScore();
            updateEditorTotal();
            updateChapterButtons();
            updateEditorTabs();
            // Update editor textarea
            editorTextarea.value = JSON.stringify(questions, null, 2);
        }

        function renderQuestion() {
            const q = questions[currentIndex];
            if (!q) return;

            questionNumber.textContent = `Soal ${currentIndex + 1} dari ${questions.length}`;
            questionTag.textContent = `📘 ${q.materi || 'Materi'}`;

            // Tampilkan soal dengan format khusus untuk rumus
            let soalText = q.soal;
            // Highlight rumus yang ada di dalam ##
            soalText = soalText.replace(/\*\*(.*?)\*\*/g, '<span class="formula">$1</span>');
            questionText.innerHTML = soalText;

            const levelMap = { 1: '🌱 Pemula', 2: '🚀 Menengah', 3: '🏆 Mahir' };
            levelBadge.textContent = `🌟 Level ${q.level} · ${levelMap[q.level] || 'SMP'}`;

            feedbackBox.classList.remove('show', 'success', 'error');
            answered = false;

            optionsContainer.innerHTML = '';
            const optionKeys = Object.keys(q.pilihan);

            optionKeys.forEach((key) => {
                const btn = document.createElement('button');
                btn.className = 'option-btn';
                btn.dataset.letter = key;
                btn.innerHTML = `
                            <span class="letter">${key}</span>
                            <span class="option-text">${q.pilihan[key]}</span>
                        `;

                if (userAnswers[currentIndex] === key) {
                    btn.classList.add('disabled');
                    const isCorrect = (key === q.jawaban);
                    btn.classList.add(isCorrect ? 'correct' : 'wrong');
                    answered = true;
                    showFeedback(isCorrect, q.jawaban, q.penjelasan);
                }

                btn.addEventListener('click', () => handleOptionClick(btn, key, q));
                optionsContainer.appendChild(btn);
            });

            if (userAnswers[currentIndex]) {
                document.querySelectorAll('.option-btn').forEach(b => b.classList.add('disabled'));
            }

            updateNavButtons();
            updateScore();
        }

        function handleOptionClick(btn, key, q) {
            if (answered) return;
            if (btn.classList.contains('disabled')) return;

            const isCorrect = (key === q.jawaban);
            const allOptions = document.querySelectorAll('.option-btn');

            allOptions.forEach(opt => {
                opt.classList.add('disabled');
                if (opt.dataset.letter === q.jawaban) {
                    opt.classList.add('show-correct');
                }
                if (opt.dataset.letter === key) {
                    opt.classList.add(isCorrect ? 'correct' : 'wrong');
                }
            });

            userAnswers[currentIndex] = key;
            answered = true;

            showFeedback(isCorrect, q.jawaban, q.penjelasan);
            updateProgress();
            updateNavButtons();
            updateScore();
        }

        function showFeedback(isCorrect, correctAnswer, explanation) {
            feedbackBox.classList.add('show');
            if (isCorrect) {
                feedbackBox.className = 'feedback-box show success';
                fbIcon.textContent = '✅';
                fbMessage.textContent = ' Jawaban tepat! Hebat! 🎉';
                fbAnswer.textContent = '';
            } else {
                feedbackBox.className = 'feedback-box show error';
                fbIcon.textContent = '❌';
                fbMessage.textContent = ' Jawaban kurang tepat. Simak pembahasan!';
                fbAnswer.textContent = `Kunci: ${correctAnswer}`;
            }
            fbExplanation.textContent = explanation || '💡 Pelajari kembali materi ini.';
        }

        function updateProgress() {
            const total = questions.length;
            const done = Object.keys(userAnswers).length;
            const pct = total > 0 ? (done / total) * 100 : 0;
            progressFill.style.width = `${pct}%`;
            progressText.textContent = `${done} / ${total}`;
        }

        function updateNavButtons() {
            prevBtn.disabled = (currentIndex === 0);
            const isLast = (currentIndex === questions.length - 1);
            const allDone = Object.keys(userAnswers).length === questions.length;

            if (isLast && allDone) {
                nextBtn.textContent = '🎉 Lihat Hasil';
            } else if (isLast) {
                nextBtn.textContent = '🏁 Selesai';
            } else {
                nextBtn.textContent = 'Selanjutnya ➡';
            }
        }

        function updateScore() {
            const total = questions.length;
            const done = Object.keys(userAnswers).length;
            if (done === 0) {
                scoreBadge.textContent = '🎯 0%';
                return;
            }
            let correct = 0;
            questions.forEach((q, idx) => {
                if (userAnswers[idx] === q.jawaban) correct++;
            });
            const pct = Math.round((correct / total) * 100);
            scoreBadge.textContent = `🎯 ${pct}%`;
        }

        function updateChapterButtons() {
            chapterButtons.forEach((btn, idx) => {
                btn.classList.toggle('active', idx === currentChapter);
            });
        }

        function updateEditorTabs() {
            editorTabs.forEach((tab, idx) => {
                tab.classList.toggle('active', idx === currentChapter);
            });
        }

        function updateEditorTotal() {
            editorTotal.textContent = questions.length;
        }

        function goToPrev() {
            if (currentIndex > 0) {
                currentIndex--;
                renderQuestion();
                updateNavButtons();
            }
        }

        function goToNext() {
            if (!userAnswers[currentIndex]) {
                feedbackBox.classList.add('show');
                feedbackBox.className = 'feedback-box show error';
                fbIcon.textContent = '⚠️';
                fbMessage.textContent = ' Jawab dulu soalnya, ya! 💪';
                fbAnswer.textContent = '';
                fbExplanation.textContent = '';
                setTimeout(() => {
                    feedbackBox.classList.remove('show');
                }, 2000);
                return;
            }

            if (currentIndex < questions.length - 1) {
                currentIndex++;
                renderQuestion();
                updateNavButtons();
            } else {
                const total = questions.length;
                const done = Object.keys(userAnswers).length;
                if (done === total) {
                    let correct = 0;
                    questions.forEach((q, idx) => {
                        if (userAnswers[idx] === q.jawaban) correct++;
                    });
                    const pct = Math.round((correct / total) * 100);
                    let grade = '';
                    if (pct >= 90) grade = '🌟 Luar biasa! Junior Champion sejati! 🏆';
                    else if (pct >= 70) grade = '💪 Bagus! Terus tingkatkan!';
                    else if (pct >= 50) grade = '📚 Belajar lagi, kamu pasti bisa!';
                    else grade = '🔄 Coba ulangi dari awal, ya!';

                    alert(
                        `🏆 HASIL LATIHAN\n\n` +
                        `Bab: ${CHAPTERS[currentChapter].icon} ${CHAPTERS[currentChapter].name}\n` +
                        `Jawaban benar: ${correct} dari ${total}\n` +
                        `Nilai: ${pct}%\n\n` +
                        `${grade}`
                    );
                    resetQuiz();
                } else {
                    alert('Selesaikan semua soal dulu!');
                }
            }
        }

        function resetQuiz() {
            userAnswers = {};
            answered = false;
            currentIndex = 0;
            renderQuestion();
            updateProgress();
            updateNavButtons();
            updateScore();
            feedbackBox.classList.remove('show', 'success', 'error');
        }

        function switchChapter(idx) {
            if (idx !== currentChapter) {
                if (Object.keys(userAnswers).length > 0) {
                    if (!confirm('Pindah bab akan mereset jawaban. Lanjutkan?')) return;
                }
                loadChapter(idx);
            }
        }

        // ============================================================
        //  EDITOR
        // ============================================================

        function toggleEditor() {
            const isOpen = editorPanel.classList.toggle('open');
            if (isOpen) {
                editorTextarea.value = JSON.stringify(questions, null, 2);
                toggleEditorBtn.textContent = '🔒 Tutup Editor';
                updateEditorTotal();
            } else {
                toggleEditorBtn.textContent = '✏️ Edit Soal';
            }
        }

        function saveEditor() {
            try {
                const raw = editorTextarea.value.trim();
                if (!raw) throw new Error('Kosong!');
                const parsed = JSON.parse(raw);
                if (!Array.isArray(parsed) || parsed.length === 0) {
                    throw new Error('Harus array berisi soal.');
                }
                parsed.forEach((q, i) => {
                    if (!q.soal || !q.pilihan || !q.jawaban) {
                        throw new Error(`Soal ke-${i+1} tidak lengkap (butuh "soal", "pilihan", "jawaban")`);
                    }
                    if (typeof q.pilihan !== 'object' || Array.isArray(q.pilihan)) {
                        throw new Error(`"pilihan" di soal ${i+1} harus object {A:..., B:...}`);
                    }
                    if (!q.materi) q.materi = 'Materi';
                    if (!q.level) q.level = 1;
                    if (!q.id) q.id = i + 1;
                });

                // Update data chapter
                CHAPTERS[currentChapter].questions = parsed;
                loadChapter(currentChapter);
                alert('✅ Soal berhasil diperbarui!');
                editorPanel.classList.remove('open');
                toggleEditorBtn.textContent = '✏️ Edit Soal';
            } catch (e) {
                alert('❌ Error: ' + e.message + '\n\nPastikan format JSON valid!');
            }
        }

        function resetEditorToDefault() {
            if (confirm('Reset ke soal default untuk bab ini? Semua perubahan akan hilang.')) {
                loadChapter(currentChapter);
                editorTextarea.value = JSON.stringify(questions, null, 2);
                alert('✅ Reset ke default berhasil!');
                updateEditorTotal();
            }
        }

        function formatEditor() {
            try {
                const raw = editorTextarea.value.trim();
                if (!raw) return;
                const parsed = JSON.parse(raw);
                editorTextarea.value = JSON.stringify(parsed, null, 2);
            } catch (e) {
                alert('❌ Tidak bisa format: JSON tidak valid!');
            }
        }

        // ============================================================
        //  KEYBOARD SHORTCUTS
        // ============================================================
        document.addEventListener('keydown', (e) => {
            if (e.target.closest('textarea') || e.target.closest('input')) return;
            if (e.key === 'ArrowLeft') goToPrev();
            if (e.key === 'ArrowRight') goToNext();
            if (e.key === 'r' || e.key === 'R') resetQuiz();
        });

        // ============================================================
        //  EVENT LISTENERS
        // ============================================================
        prevBtn.addEventListener('click', goToPrev);
        nextBtn.addEventListener('click', goToNext);
        resetBtn.addEventListener('click', resetQuiz);

        chapterButtons.forEach((btn) => {
            btn.addEventListener('click', () => {
                switchChapter(parseInt(btn.dataset.chapter));
            });
        });

        editorTabs.forEach((tab) => {
            tab.addEventListener('click', () => {
                const idx = parseInt(tab.dataset.editorChapter);
                if (idx !== currentChapter) {
                    if (Object.keys(userAnswers).length > 0) {
                        if (!confirm('Pindah tab akan mereset jawaban. Lanjutkan?')) return;
                    }
                    loadChapter(idx);
                    editorTextarea.value = JSON.stringify(questions, null, 2);
                    updateEditorTotal();
                }
            });
        });

        toggleEditorBtn.addEventListener('click', toggleEditor);
        saveEditorBtn.addEventListener('click', saveEditor);
        resetEditorBtn.addEventListener('click', resetEditorToDefault);
        formatEditorBtn.addEventListener('click', formatEditor);

        // ============================================================
        //  INIT
        // ============================================================
        loadChapter(0);

        console.log('⚡ Junior Champions - Medan & Gaya Listrik siap!');
        console.log('📚 2 Bab · 20 Soal Total');
        console.log('💡 Tekan panah kiri/kanan untuk navigasi.');
        console.log('💡 Klik "Edit Soal" untuk mengubah konten.');
    </script>

</body>
</html>
