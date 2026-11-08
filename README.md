<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form Pemilihan Menu & Konfirmasi Kehadiran HUT FORMASI</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --color-bg: #f5f0eb;
            --color-card: #ffffff;
            --color-primary: #6b4c3b;
            --color-primary-hover: #5a3f30;
            --color-accent: #d4a574;
            --color-accent-light: #e8d5c4;
            --color-text: #3d3028;
            --color-text-secondary: #7a6b5d;
            --color-border: #e0d5cc;
            --color-error: #c0392b;
            --color-success: #27ae60;
            --shadow-soft: 0 4px 20px rgba(107, 76, 59, 0.08);
            --shadow-hover: 0 8px 30px rgba(107, 76, 59, 0.15);
            --radius: 16px;
            --radius-sm: 12px;
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--color-bg);
            color: var(--color-text);
            line-height: 1.6;
            min-height: 100vh;
            padding: 20px 16px 40px;
        }

        .container {
            max-width: 480px;
            margin: 0 auto;
        }

        /* Header */
        .header {
            text-align: center;
            margin-bottom: 32px;
            padding: 32px 24px;
            background: linear-gradient(135deg, var(--color-primary) 0%, #8b6f5e 100%);
            border-radius: var(--radius);
            color: white;
            box-shadow: var(--shadow-soft);
        }

        .header h1 {
            font-size: 1.5rem;
            font-weight: 700;
            line-height: 1.3;
            margin-bottom: 12px;
        }

        .header p {
            font-size: 0.9rem;
            opacity: 0.9;
            font-weight: 300;
        }

        .header .emoji {
            font-size: 1.2rem;
        }

        /* Card Section */
        .card {
            background: var(--color-card);
            border-radius: var(--radius);
            padding: 24px;
            margin-bottom: 20px;
            box-shadow: var(--shadow-soft);
            transition: var(--transition);
        }

        .card:hover {
            box-shadow: var(--shadow-hover);
        }

        .section-label {
            font-size: 0.75rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            color: var(--color-accent);
            margin-bottom: 16px;
            display: block;
        }

        .field-label {
            font-size: 1rem;
            font-weight: 600;
            margin-bottom: 12px;
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .required {
            color: var(--color-error);
            font-weight: 700;
        }

        .helper-text {
            font-size: 0.8rem;
            color: var(--color-text-secondary);
            margin-top: 8px;
            font-style: italic;
        }

        /* Input Text */
        .input-text {
            width: 100%;
            padding: 14px 16px;
            border: 2px solid var(--color-border);
            border-radius: var(--radius-sm);
            font-family: 'Poppins', sans-serif;
            font-size: 0.95rem;
            color: var(--color-text);
            background: #faf8f6;
            transition: var(--transition);
            outline: none;
        }

        .input-text:focus {
            border-color: var(--color-accent);
            background: white;
            box-shadow: 0 0 0 4px rgba(212, 165, 116, 0.15);
        }

        .input-text.error {
            border-color: var(--color-error);
            animation: shake 0.4s ease;
        }

        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(-6px); }
            75% { transform: translateX(6px); }
        }

        .error-message {
            font-size: 0.8rem;
            color: var(--color-error);
            margin-top: 6px;
            display: none;
        }

        .error-message.show {
            display: block;
        }

        /* Selectable Cards (Radio replacement) */
        .selectable-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
            gap: 12px;
        }

        .selectable-card {
            position: relative;
            cursor: pointer;
        }

        .selectable-card input[type="radio"] {
            position: absolute;
            opacity: 0;
            width: 0;
            height: 0;
        }

        .selectable-card .card-content {
            padding: 16px 14px;
            border: 2px solid var(--color-border);
            border-radius: var(--radius-sm);
            text-align: center;
            transition: var(--transition);
            background: #faf8f6;
        }

        .selectable-card .card-icon {
            font-size: 2rem;
            margin-bottom: 8px;
            display: block;
        }

        .selectable-card .card-title {
            font-size: 0.85rem;
            font-weight: 600;
            color: var(--color-text);
            line-height: 1.3;
        }

        .selectable-card:hover .card-content {
            border-color: var(--color-accent);
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(212, 165, 116, 0.2);
        }

        .selectable-card input:checked + .card-content {
            border-color: var(--color-primary);
            background: linear-gradient(135deg, #fdf8f4 0%, #f5efe8 100%);
            box-shadow: 0 4px 16px rgba(107, 76, 59, 0.15);
            transform: scale(1.02);
        }

        .selectable-card input:checked + .card-content::after {
            content: '✓';
            position: absolute;
            top: -8px;
            right: -8px;
            width: 24px;
            height: 24px;
            background: var(--color-primary);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.75rem;
            font-weight: 700;
            box-shadow: 0 2px 8px rgba(107, 76, 59, 0.3);
        }

        .selectable-card .card-content {
            position: relative;
        }

        /* Inline Other Option */
        .other-option-wrapper {
            grid-column: 1 / -1;
        }

        .other-input-row {
            display: flex;
            align-items: center;
            gap: 12px;
            margin-top: 12px;
        }

        .other-input-row .input-text {
            flex: 1;
        }

        /* Attendance Toggle */
        .toggle-group {
            display: flex;
            gap: 12px;
        }

        .toggle-btn {
            flex: 1;
            padding: 14px 20px;
            border: 2px solid var(--color-border);
            border-radius: var(--radius-sm);
            background: #faf8f6;
            font-family: 'Poppins', sans-serif;
            font-size: 0.95rem;
            font-weight: 600;
            color: var(--color-text-secondary);
            cursor: pointer;
            transition: var(--transition);
            text-align: center;
        }

        .toggle-btn:hover {
            border-color: var(--color-accent);
            color: var(--color-text);
        }

        .toggle-btn.active {
            border-color: var(--color-success);
            background: linear-gradient(135deg, #e8f8ef 0%, #d4f0e0 100%);
            color: var(--color-success);
            box-shadow: 0 4px 12px rgba(39, 174, 96, 0.15);
        }

        .toggle-btn.active::after {
            content: ' ✓';
        }

        /* Payment Methods */
        .payment-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 12px;
        }

        .payment-card {
            position: relative;
            cursor: pointer;
        }

        .payment-card input[type="radio"] {
            position: absolute;
            opacity: 0;
        }

        .payment-card .pay-content {
            padding: 18px 16px;
            border: 2px solid var(--color-border);
            border-radius: var(--radius-sm);
            text-align: center;
            transition: var(--transition);
            background: #faf8f6;
        }

        .payment-card .pay-icon {
            font-size: 1.8rem;
            margin-bottom: 6px;
            display: block;
        }

        .payment-card .pay-label {
            font-size: 0.9rem;
            font-weight: 600;
            color: var(--color-text);
        }

        .payment-card:hover .pay-content {
            border-color: var(--color-accent);
            transform: translateY(-2px);
        }

        .payment-card input:checked + .pay-content {
            border-color: var(--color-primary);
            background: linear-gradient(135deg, #fdf8f4 0%, #f5efe8 100%);
            box-shadow: 0 4px 16px rgba(107, 76, 59, 0.15);
        }

        .payment-card input:checked + .pay-content::after {
            content: '✓';
            position: absolute;
            top: -8px;
            right: -8px;
            width: 24px;
            height: 24px;
            background: var(--color-primary);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.75rem;
            font-weight: 700;
        }

        .payment-card .pay-content {
            position: relative;
        }

        /* Upload Zone */
        .upload-zone {
            border: 2px dashed var(--color-border);
            border-radius: var(--radius-sm);
            padding: 32px 20px;
            text-align: center;
            cursor: pointer;
            transition: var(--transition);
            background: #faf8f6;
            margin-top: 12px;
        }

        .upload-zone:hover,
        .upload-zone.dragover {
            border-color: var(--color-accent);
            background: #fdf8f4;
            transform: scale(1.01);
        }

        .upload-zone.has-file {
            border-color: var(--color-success);
            border-style: solid;
            background: #e8f8ef;
        }

        .upload-icon {
            font-size: 2.5rem;
            margin-bottom: 8px;
            display: block;
        }

        .upload-text {
            font-size: 0.9rem;
            font-weight: 500;
            color: var(--color-text-secondary);
        }

        .upload-hint {
            font-size: 0.75rem;
            color: var(--color-text-secondary);
            opacity: 0.7;
            margin-top: 4px;
        }

        .upload-zone input[type="file"] {
            display: none;
        }

        .file-name {
            font-size: 0.85rem;
            color: var(--color-success);
            font-weight: 600;
            margin-top: 8px;
            display: none;
        }

        .file-name.show {
            display: block;
        }

        /* Conditional Section Animation */
        .conditional-section {
            max-height: 0;
            overflow: hidden;
            opacity: 0;
            transition: max-height 0.5s cubic-bezier(0.4, 0, 0.2, 1),
                        opacity 0.4s ease,
                        margin 0.4s ease;
            margin-top: 0;
        }

        .conditional-section.visible {
            max-height: 400px;
            opacity: 1;
            margin-top: 20px;
        }

        /* Buttons */
        .btn-group {
            display: flex;
            flex-direction: column;
            gap: 12px;
            margin-top: 8px;
        }

        .btn-primary {
            width: 100%;
            padding: 16px 24px;
            background: linear-gradient(135deg, var(--color-primary) 0%, #8b6f5e 100%);
            color: white;
            border: none;
            border-radius: var(--radius-sm);
            font-family: 'Poppins', sans-serif;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            letter-spacing: 0.5px;
            box-shadow: 0 4px 16px rgba(107, 76, 59, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 24px rgba(107, 76, 59, 0.4);
        }

        .btn-primary:active {
            transform: translateY(0);
        }

        .btn-secondary {
            width: 100%;
            padding: 14px 24px;
            background: transparent;
            color: var(--color-text-secondary);
            border: 2px solid var(--color-border);
            border-radius: var(--radius-sm);
            font-family: 'Poppins', sans-serif;
            font-size: 0.9rem;
            font-weight: 500;
            cursor: pointer;
            transition: var(--transition);
        }

        .btn-secondary:hover {
            border-color: var(--color-error);
            color: var(--color-error);
            background: #fef2f2;
        }

        /* Success Toast */
        .toast {
            position: fixed;
            bottom: 24px;
            left: 50%;
            transform: translateX(-50%) translateY(100px);
            background: var(--color-success);
            color: white;
            padding: 14px 28px;
            border-radius: 50px;
            font-family: 'Poppins', sans-serif;
            font-size: 0.9rem;
            font-weight: 600;
            box-shadow: 0 8px 30px rgba(39, 174, 96, 0.3);
            z-index: 1000;
            transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            white-space: nowrap;
        }

        .toast.show {
            transform: translateX(-50%) translateY(0);
        }

        /* Footer Note */
        .footer-note {
            text-align: center;
            font-size: 0.7rem;
            color: var(--color-text-secondary);
            margin-top: 24px;
            opacity: 0.7;
        }

        /* Responsive adjustments */
        @media (min-width: 481px) {
            body {
                padding: 40px 20px 60px;
            }

            .header h1 {
                font-size: 1.7rem;
            }

            .selectable-grid {
                grid-template-columns: repeat(3, 1fr);
            }
        }

        /* Smooth scroll */
        html {
            scroll-behavior: smooth;
        }

        /* Focus visible for accessibility */
        *:focus-visible {
            outline: 3px solid var(--color-accent);
            outline-offset: 2px;
        }
    </style>
</head>
<body>

<div class="container">
    <!-- Header -->
    <div class="header">
        <h1>Form Pemilihan Menu & Konfirmasi Kehadiran HUT FORMASI</h1>
        <p>Wajib diisi untuk pemilihan menu makan saat HUT FORMASI nanti yaaa <span class="emoji">🥰</span></p>
    </div>

    <form id="orderForm" novalidate>

        <!-- Data Diri -->
        <div class="card">
            <span class="section-label">Data Diri</span>
            <label class="field-label">
                Nama Lengkap <span class="required">*</span>
            </label>
            <input type="text" class="input-text" id="namaLengkap" placeholder="Masukkan nama lengkap Anda" required>
            <div class="error-message" id="namaError">Nama lengkap wajib diisi.</div>
        </div>

        <!-- Konfirmasi Kehadiran -->
        <div class="card">
            <span class="section-label">Kehadiran</span>
            <label class="field-label">
                Konfirmasi Kehadiran <span class="required">*</span>
            </label>
            <div class="toggle-group">
                <button type="button" class="toggle-btn" data-value="hadir" onclick="setAttendance(this)">Hadir</button>
            </div>
            <input type="hidden" id="kehadiran" value="">
            <div class="error-message" id="kehadiranError">Konfirmasi kehadiran wajib dipilih.</div>
        </div>

        <!-- Pilihan Menu Konsumsi -->
        <div class="card">
            <span class="section-label">Menu Konsumsi</span>
            <label class="field-label">
                Pilihan Menu Konsumsi <span class="required">*</span>
            </label>
            <div class="selectable-grid">
                <label class="selectable-card">
                    <input type="radio" name="menu" value="Nasi Goreng Triple S" required>
                    <div class="card-content">
                        <span class="card-icon">🍳</span>
                        <span class="card-title">Nasi Goreng Triple S</span>
                    </div>
                </label>
                <label class="selectable-card">
                    <input type="radio" name="menu" value="Nasi Telur Triple S">
                    <div class="card-content">
                        <span class="card-icon">🥚</span>
                        <span class="card-title">Nasi Telur Triple S</span>
                    </div>
                </label>
                <label class="selectable-card">
                    <input type="radio" name="menu" value="Nasi Gila">
                    <div class="card-content">
                        <span class="card-icon">🌶️</span>
                        <span class="card-title">Nasi Gila</span>
                    </div>
                </label>
                <div class="other-option-wrapper">
                    <label class="selectable-card">
                        <input type="radio" name="menu" value="other" id="menuOtherRadio">
                        <div class="card-content">
                            <span class="card-icon">✏️</span>
                            <span class="card-title">Yang lain:</span>
                        </div>
                    </label>
                    <div class="other-input-row" id="otherInputRow" style="display:none;">
                        <input type="text" class="input-text" id="menuOtherText" placeholder="Tulis menu lainnya...">
                    </div>
                </div>
            </div>
            <div class="error-message" id="menuError">Pilih salah satu menu konsumsi.</div>
        </div>

        <!-- Metode Pembayaran -->
        <div class="card">
            <span class="section-label">Pembayaran</span>
            <label class="field-label">
                Metode Pembayaran <span class="required">*</span>
            </label>
            <p class="helper-text">Jika cash dapat melalui Rangga</p>
            <div class="payment-grid" style="margin-top: 12px;">
                <label class="payment-card">
                    <input type="radio" name="payment" value="Cash" required>
                    <div class="pay-content">
                        <span class="pay-icon">💵</span>
                        <span class="pay-label">Cash</span>
                    </div>
                </label>
                <label class="payment-card">
                    <input type="radio" name="payment" value="Transfer" id="paymentTransfer">
                    <div class="pay-content">
                        <span class="pay-icon">📱</span>
                        <span class="pay-label">Transfer</span>
                    </div>
                </label>
            </div>
            <div class="error-message" id="paymentError">Pilih metode pembayaran.</div>

            <!-- Bukti Transfer (Conditional) -->
            <div class="conditional-section" id="uploadSection">
                <label class="field-label" style="margin-top: 8px;">
                    Bukti Pembayaran Via Trans
