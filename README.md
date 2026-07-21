<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>CasinoRoyale — Premium iGaming</title>

    <!-- Google Fonts: Inter & Poppins -->
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&family=Poppins:wght@400;500;600;700;800&display=swap" rel="stylesheet" />

    <!-- Font Awesome 6 (free) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />

    <style>
        /* ============================================================
               CSS — All styles in one block
               ============================================================ */

        /* ---------- Reset & Base ---------- */
        *,
        *::before,
        *::after {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg-primary: #09090F;
            --bg-secondary: #12121A;
            --purple: #6D28FF;
            --purple-dark: #4C1D95;
            --purple-glow: rgba(109, 40, 255, 0.35);
            --pink: #E91E63;
            --pink-glow: rgba(233, 30, 99, 0.30);
            --gold: #F7C948;
            --gold-glow: rgba(247, 201, 72, 0.35);
            --gold-gradient: linear-gradient(135deg, #F7C948 0%, #F59E0B 100%);
            --purple-gradient: linear-gradient(135deg, #6D28FF 0%, #4C1D95 100%);
            --text-primary: #F1F1F7;
            --text-secondary: #B0B0C8;
            --glass-bg: rgba(255, 255, 255, 0.04);
            --glass-border: rgba(255, 255, 255, 0.07);
            --glass-shadow: 0 8px 32px rgba(0, 0, 0, 0.45);
            --radius-lg: 28px;
            --radius-md: 18px;
            --radius-sm: 12px;
            --transition: 0.35s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            --font-primary: 'Inter', sans-serif;
            --font-display: 'Poppins', sans-serif;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: var(--font-primary);
            background: var(--bg-primary);
            color: var(--text-primary);
            overflow-x: hidden;
            line-height: 1.6;
            min-height: 100vh;
        }

        /* ---------- Scrollbar ---------- */
        ::-webkit-scrollbar {
            width: 6px;
        }
        ::-webkit-scrollbar-track {
            background: var(--bg-primary);
        }
        ::-webkit-scrollbar-thumb {
            background: var(--purple);
            border-radius: 10px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: var(--gold);
        }

        /* ---------- Particles Canvas ---------- */
        #particles-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            pointer-events: none;
            opacity: 0.6;
        }

        /* ---------- Background Glow Orbs ---------- */
        .bg-glow {
            position: fixed;
            border-radius: 50%;
            filter: blur(120px);
            opacity: 0.25;
            pointer-events: none;
            z-index: 0;
        }
        .bg-glow--purple {
            width: 600px;
            height: 600px;
            background: var(--purple);
            top: -10%;
            right: -10%;
        }
        .bg-glow--gold {
            width: 500px;
            height: 500px;
            background: var(--gold);
            bottom: -10%;
            left: -10%;
            opacity: 0.15;
        }
        .bg-glow--pink {
            width: 400px;
            height: 400px;
            background: var(--pink);
            top: 40%;
            left: 50%;
            transform: translateX(-50%);
            opacity: 0.10;
        }

        /* ---------- Container ---------- */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            position: relative;
            z-index: 2;
        }

        /* ---------- Glassmorphism Card ---------- */
        .glass {
            background: var(--glass-bg);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid var(--glass-border);
            border-radius: var(--radius-lg);
            box-shadow: var(--glass-shadow);
            transition: var(--transition);
        }

        /* ---------- Header ---------- */
        .header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 100;
            padding: 14px 0;
            background: rgba(9, 9, 15, 0.60);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.04);
            transition: var(--transition);
        }

        .header__inner {
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .header__logo {
            font-family: var(--font-display);
            font-weight: 800;
            font-size: 1.35rem;
            letter-spacing: -0.5px;
            background: var(--gold-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .header__logo i {
            -webkit-text-fill-color: initial;
            color: var(--gold);
            font-size: 1.5rem;
        }

        /* ---------- Language Selector ---------- */
        .lang-selector {
            position: relative;
            display: inline-block;
        }

        .lang-selector__toggle {
            display: flex;
            align-items: center;
            gap: 8px;
            background: var(--glass-bg);
            backdrop-filter: blur(8px);
            -webkit-backdrop-filter: blur(8px);
            border: 1px solid var(--glass-border);
            border-radius: 50px;
            padding: 6px 14px 6px 10px;
            color: var(--text-primary);
            font-size: 0.85rem;
            font-weight: 500;
            cursor: pointer;
            transition: var(--transition);
            font-family: var(--font-primary);
        }
        .lang-selector__toggle:hover {
            border-color: rgba(247, 201, 72, 0.3);
            background: rgba(255, 255, 255, 0.08);
        }
        .lang-selector__toggle .flag-icon {
            font-size: 1.2rem;
            line-height: 1;
        }
        .lang-selector__toggle .arrow {
            font-size: 0.65rem;
            transition: var(--transition);
            color: var(--text-secondary);
        }
        .lang-selector__toggle.open .arrow {
            transform: rotate(180deg);
        }

        .lang-selector__dropdown {
            position: absolute;
            top: calc(100% + 10px);
            right: 0;
            min-width: 160px;
            background: rgba(18, 18, 26, 0.92);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid var(--glass-border);
            border-radius: var(--radius-md);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.7);
            padding: 6px;
            opacity: 0;
            visibility: hidden;
            transform: translateY(-8px) scale(0.96);
            transition: var(--transition);
            transform-origin: top right;
            z-index: 200;
        }
        .lang-selector__dropdown.open {
            opacity: 1;
            visibility: visible;
            transform: translateY(0) scale(1);
        }

        .lang-selector__item {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 10px 14px;
            border-radius: var(--radius-sm);
            color: var(--text-secondary);
            font-size: 0.85rem;
            font-weight: 500;
            cursor: pointer;
            transition: var(--transition);
            background: transparent;
            border: none;
            width: 100%;
            font-family: var(--font-primary);
        }
        .lang-selector__item:hover {
            background: rgba(109, 40, 255, 0.15);
            color: var(--text-primary);
        }
        .lang-selector__item.active {
            background: rgba(109, 40, 255, 0.20);
            color: var(--gold);
        }
        .lang-selector__item .flag-icon {
            font-size: 1.2rem;
        }

        /* ---------- Hero ---------- */
        .hero {
            padding: 140px 0 80px;
            text-align: center;
            position: relative;
        }

        .hero__badge {
            display: inline-block;
            background: rgba(247, 201, 72, 0.10);
            border: 1px solid rgba(247, 201, 72, 0.20);
            border-radius: 50px;
            padding: 4px 18px;
            font-size: 0.75rem;
            font-weight: 600;
            color: var(--gold);
            letter-spacing: 1px;
            text-transform: uppercase;
            margin-bottom: 24px;
            backdrop-filter: blur(4px);
        }

        .hero__title {
            font-family: var(--font-display);
            font-weight: 800;
            font-size: clamp(2.2rem, 8vw, 4.4rem);
            line-height: 1.1;
            margin-bottom: 20px;
            background: linear-gradient(135deg, #FFFFFF 0%, #C4B5FD 40%, var(--gold) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 0 80px rgba(247, 201, 72, 0.10);
        }

        .hero__subtitle {
            font-size: clamp(1rem, 2vw, 1.25rem);
            color: var(--text-secondary);
            max-width: 600px;
            margin: 0 auto 40px;
            font-weight: 400;
            line-height: 1.7;
        }

        /* ---------- Buttons ---------- */
        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            padding: 16px 38px;
            border-radius: 60px;
            font-family: var(--font-primary);
            font-weight: 700;
            font-size: 1rem;
            border: none;
            cursor: pointer;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            text-decoration: none;
            letter-spacing: 0.3px;
        }

        .btn--gold {
            background: var(--gold-gradient);
            color: #0A0A12;
            box-shadow: 0 4px 30px rgba(247, 201, 72, 0.30);
        }
        .btn--gold:hover {
            transform: translateY(-3px) scale(1.02);
            box-shadow: 0 8px 50px rgba(247, 201, 72, 0.45);
        }

        .btn--purple {
            background: var(--purple-gradient);
            color: #fff;
            box-shadow: 0 4px 30px rgba(109, 40, 255, 0.30);
        }
        .btn--purple:hover {
            transform: translateY(-3px) scale(1.02);
            box-shadow: 0 8px 50px rgba(109, 40, 255, 0.45);
        }

        .btn--glass {
            background: var(--glass-bg);
            backdrop-filter: blur(8px);
            -webkit-backdrop-filter: blur(8px);
            border: 1px solid rgba(255, 255, 255, 0.12);
            color: var(--text-primary);
            box-shadow: var(--glass-shadow);
        }
        .btn--glass:hover {
            background: rgba(255, 255, 255, 0.08);
            border-color: rgba(247, 201, 72, 0.25);
            transform: translateY(-3px);
            box-shadow: 0 8px 40px rgba(0, 0, 0, 0.5);
        }

        .btn--gold-large {
            padding: 18px 48px;
            font-size: 1.1rem;
        }

        /* Ripple effect container */
        .btn .ripple {
            position: absolute;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.35);
            transform: scale(0);
            animation: rippleAnim 0.7s ease-out forwards;
            pointer-events: none;
        }
        @keyframes rippleAnim {
            to {
                transform: scale(4);
                opacity: 0;
            }
        }

        /* ---------- Features ---------- */
        .features {
            padding: 60px 0 40px;
        }

        .features__grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 24px;
        }

        .feature-card {
            padding: 30px 24px 28px;
            text-align: center;
            border-radius: var(--radius-lg);
            transition: var(--transition);
            cursor: default;
            position: relative;
            overflow: hidden;
        }
        .feature-card::before {
            content: '';
            position: absolute;
            inset: 0;
            border-radius: inherit;
            padding: 1px;
            background: linear-gradient(135deg, rgba(109, 40, 255, 0.20), rgba(247, 201, 72, 0.10));
            -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            -webkit-mask-composite: xor;
            mask-composite: exclude;
            pointer-events: none;
            opacity: 0;
            transition: var(--transition);
        }
        .feature-card:hover {
            transform: translateY(-6px);
            background: rgba(255, 255, 255, 0.06);
            border-color: rgba(247, 201, 72, 0.15);
            box-shadow: 0 12px 48px rgba(109, 40, 255, 0.15), 0 0 40px rgba(247, 201, 72, 0.04);
        }
        .feature-card:hover::before {
            opacity: 1;
        }

        .feature-card__icon {
            font-size: 2.6rem;
            margin-bottom: 14px;
            display: block;
        }
        .feature-card__title {
            font-family: var(--font-display);
            font-weight: 700;
            font-size: 1.1rem;
            margin-bottom: 6px;
            color: var(--text-primary);
        }
        .feature-card__desc {
            font-size: 0.85rem;
            color: var(--text-secondary);
            font-weight: 400;
        }

        /* ---------- Statistics ---------- */
        .stats {
            padding: 40px 0 50px;
        }

        .stats__grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
            gap: 24px;
        }

        .stat-card {
            padding: 28px 20px 24px;
            text-align: center;
            border-radius: var(--radius-lg);
            background: var(--glass-bg);
            backdrop-filter: blur(8px);
            -webkit-backdrop-filter: blur(8px);
            border: 1px solid var(--glass-border);
            transition: var(--transition);
        }
        .stat-card:hover {
            border-color: rgba(247, 201, 72, 0.15);
            transform: translateY(-4px);
        }

        .stat-card__icon {
            font-size: 2rem;
            display: block;
            margin-bottom: 6px;
        }
        .stat-card__number {
            font-family: var(--font-display);
            font-weight: 800;
            font-size: clamp(2rem, 4vw, 2.8rem);
            background: var(--gold-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            line-height: 1.2;
        }
        .stat-card__label {
            font-size: 0.85rem;
            color: var(--text-secondary);
            font-weight: 500;
        }

        /* ---------- VIP Card ---------- */
        .vip {
            padding: 40px 0 50px;
        }

        .vip__card {
            padding: 48px 40px;
            position: relative;
            border-radius: var(--radius-lg);
            background: linear-gradient(135deg, rgba(109, 40, 255, 0.08), rgba(247, 201, 72, 0.04));
            border: 1px solid rgba(247, 201, 72, 0.15);
            box-shadow: 0 0 60px rgba(247, 201, 72, 0.06), 0 8px 48px rgba(0, 0, 0, 0.4);
            text-align: center;
            overflow: hidden;
            transition: var(--transition);
        }
        .vip__card:hover {
            box-shadow: 0 0 80px rgba(247, 201, 72, 0.10), 0 12px 60px rgba(0, 0, 0, 0.5);
        }
        .vip__card::before {
            content: '';
            position: absolute;
            inset: -2px;
            border-radius: inherit;
            padding: 2px;
            background: linear-gradient(135deg, var(--gold), var(--purple), var(--gold));
            background-size: 300% 300%;
            -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            -webkit-mask-composite: xor;
            mask-composite: exclude;
            animation: goldBorder 6s ease-in-out infinite;
            pointer-events: none;
        }
        @keyframes goldBorder {
            0%,
            100% {
                background-position: 0% 50%;
            }
            50% {
                background-position: 100% 50%;
            }
        }

        .vip__icon {
            font-size: 3.4rem;
            display: block;
            margin-bottom: 12px;
        }
        .vip__title {
            font-family: var(--font-display);
            font-weight: 800;
            font-size: clamp(1.6rem, 4vw, 2.6rem);
            background: var(--gold-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
        }
        .vip__text {
            font-size: 1.05rem;
            color: var(--text-secondary);
            max-width: 560px;
            margin: 0 auto;
            font-weight: 400;
        }

        /* ---------- CTA ---------- */
        .cta {
            padding: 40px 0 60px;
            text-align: center;
        }

        .cta__title {
            font-family: var(--font-display);
            font-weight: 800;
            font-size: clamp(2rem, 5vw, 3.2rem);
            margin-bottom: 16px;
            background: linear-gradient(135deg, #FFFFFF, #C4B5FD);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .cta__sub {
            color: var(--text-secondary);
            font-size: 1.05rem;
            margin-bottom: 36px;
        }

        .cta__buttons {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 16px;
        }

        .cta__buttons .btn {
            min-width: 220px;
        }

        /* ---------- Footer ---------- */
        .footer {
            padding: 32px 0 28px;
            border-top: 1px solid rgba(255, 255, 255, 0.04);
            text-align: center;
            background: rgba(9, 9, 15, 0.70);
            backdrop-filter: blur(8px);
        }

        .footer__text {
            font-size: 0.8rem;
            color: var(--text-secondary);
            font-weight: 400;
            letter-spacing: 0.3px;
        }
        .footer__text span {
            color: var(--gold);
        }
        .footer__text .divider {
            color: rgba(255, 255, 255, 0.10);
            padding: 0 8px;
        }

        /* ---------- Fade-in animation ---------- */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease, transform 0.8s ease;
        }
        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* ---------- Responsive ---------- */

        /* Mobile first — already designed */

        @media (max-width: 640px) {
            .header__logo {
                font-size: 1.1rem;
            }
            .lang-selector__toggle {
                padding: 4px 10px 4px 8px;
                font-size: 0.75rem;
            }
            .lang-selector__toggle .flag-icon {
                font-size: 1rem;
            }
            .lang-selector__dropdown {
                min-width: 140px;
                right: -10px;
            }
            .hero {
                padding: 120px 0 50px;
            }
            .hero__badge {
                font-size: 0.65rem;
                padding: 3px 14px;
            }
            .btn {
                padding: 14px 28px;
                font-size: 0.9rem;
            }
            .btn--gold-large {
                padding: 16px 32px;
                font-size: 1rem;
            }
            .features__grid {
                grid-template-columns: 1fr 1fr;
                gap: 14px;
            }
            .feature-card {
                padding: 22px 16px 20px;
            }
            .feature-card__icon {
                font-size: 2rem;
            }
            .feature-card__title {
                font-size: 0.95rem;
            }
            .stats__grid {
                grid-template-columns: 1fr 1fr;
                gap: 14px;
            }
            .stat-card {
                padding: 20px 14px 18px;
            }
            .vip__card {
                padding: 32px 20px;
            }
            .cta__buttons .btn {
                min-width: 100%;
                width: 100%;
            }
            .cta__buttons {
                flex-direction: column;
                align-items: center;
            }
            .bg-glow--purple {
                width: 300px;
                height: 300px;
                top: -5%;
                right: -20%;
            }
            .bg-glow--gold {
                width: 280px;
                height: 280px;
                bottom: -5%;
                left: -20%;
            }
            .bg-glow--pink {
                width: 240px;
                height: 240px;
                top: 30%;
            }
        }

        @media (max-width: 420px) {
            .features__grid {
                grid-template-columns: 1fr 1fr;
                gap: 10px;
            }
            .stats__grid {
                grid-template-columns: 1fr 1fr;
                gap: 10px;
            }
            .feature-card {
                padding: 18px 12px 16px;
            }
            .feature-card__icon {
                font-size: 1.6rem;
            }
            .feature-card__title {
                font-size: 0.8rem;
            }
            .feature-card__desc {
                font-size: 0.7rem;
            }
            .stat-card__number {
                font-size: 1.6rem;
            }
        }

        @media (min-width: 768px) {
            .features__grid {
                grid-template-columns: repeat(4, 1fr);
            }
            .stats__grid {
                grid-template-columns: repeat(3, 1fr);
            }
            .cta__buttons .btn {
                min-width: 240px;
            }
        }

        @media (min-width: 1024px) {
            .container {
                padding: 0 40px;
            }
            .hero {
                padding: 180px 0 100px;
            }
            .vip__card {
                padding: 56px 48px;
            }
        }

        /* ---------- Utility ---------- */
        .text-center {
            text-align: center;
        }
        .mt-1 {
            margin-top: 8px;
        }
        .mt-2 {
            margin-top: 16px;
        }
        .mt-3 {
            margin-top: 24px;
        }
        .mt-4 {
            margin-top: 32px;
        }
        .mb-1 {
            margin-bottom: 8px;
        }
        .mb-2 {
            margin-bottom: 16px;
        }
        .mb-3 {
            margin-bottom: 24px;
        }
        .gap-2 {
            gap: 12px;
        }
    </style>
</head>
<body>

    <!-- ====== BACKGROUND GLOWS ====== -->
    <div class="bg-glow bg-glow--purple"></div>
    <div class="bg-glow bg-glow--gold"></div>
    <div class="bg-glow bg-glow--pink"></div>

    <!-- ====== PARTICLES CANVAS ====== -->
    <canvas id="particles-canvas"></canvas>

    <!-- ====== HEADER ====== -->
    <header class="header" id="header">
        <div class="container header__inner">
            <!-- Logo -->
            <div class="header__logo">
                <i class="fas fa-crown"></i>
                <span>Casino<span style="background:linear-gradient(135deg,#F7C948,#F59E0B);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;">Royale</span></span>
            </div>

            <!-- Language Selector -->
            <div class="lang-selector" id="langSelector">
                <button class="lang-selector__toggle" id="langToggle" aria-label="Select language">
                    <span class="flag-icon" id="currentFlag">🇺🇸</span>
                    <span id="currentLangLabel">EN</span>
                    <span class="arrow"><i class="fas fa-chevron-down"></i></span>
                </button>
                <div class="lang-selector__dropdown" id="langDropdown">
                    <button class="lang-selector__item active" data-lang="en" data-flag="🇺🇸" data-label="EN">
                        <span class="flag-icon">🇺🇸</span> English
                    </button>
                    <button class="lang-selector__item" data-lang="de" data-flag="🇩🇪" data-label="DE">
                        <span class="flag-icon">🇩🇪</span> Deutsch
                    </button>
                    <button class="lang-selector__item" data-lang="ru" data-flag="🇷🇺" data-label="RU">
                        <span class="flag-icon">🇷🇺</span> Русский
                    </button>
                </div>
            </div>
        </div>
    </header>

    <!-- ====== MAIN ====== -->
    <main>

        <!-- ====== HERO ====== -->
        <section class="hero" id="hero">
            <div class="container">
                <div class="hero__badge fade-in">🎰 #1 Premium Casino</div>
                <h1 class="hero__title fade-in" data-i18n="heroTitle">
                    🎁 Welcome Bonus up to €2,000 + 225 Free Spins
                </h1>
                <p class="hero__subtitle fade-in" data-i18n="heroSub">
                    Join thousands of players and unlock your exclusive welcome package in less than one minute.
                </p>
                <a href="https://getnvpartnerspromo.com/l/6a5dd65667ae9214180cfde2" target="_blank" rel="noopener" class="btn btn--gold btn--gold-large fade-in" id="heroCta">
                    🎰 <span data-i18n="heroBtn">Claim Your Welcome Bonus</span>
                </a>
            </div>
        </section>

        <!-- ====== FEATURES ====== -->
        <section class="features">
            <div class="container">
                <div class="features__grid">
                    <div class="feature-card glass fade-in">
                        <span class="feature-card__icon">⚡</span>
                        <h3 class="feature-card__title" data-i18n="feat1Title">Instant Registration</h3>
                        <p class="feature-card__desc" data-i18n="feat1Desc">Sign up in seconds and start playing immediately.</p>
                    </div>
                    <div class="feature-card glass fade-in">
                        <span class="feature-card__icon">🔒</span>
                        <h3 class="feature-card__title" data-i18n="feat2Title">Secure &amp; Trusted Platform</h3>
                        <p class="feature-card__desc" data-i18n="feat2Desc">Licensed, encrypted, and fair-play guaranteed.</p>
                    </div>
                    <div class="feature-card glass fade-in">
                        <span class="feature-card__icon">💸</span>
                        <h3 class="feature-card__title" data-i18n="feat3Title">Fast Withdrawals</h3>
                        <p class="feature-card__desc" data-i18n="feat3Desc">Get your winnings in record time, no delays.</p>
                    </div>
                    <div class="feature-card glass fade-in">
                        <span class="feature-card__icon">🎮</span>
                        <h3 class="feature-card__title" data-i18n="feat4Title">Thousands of Premium Games</h3>
                        <p class="feature-card__desc" data-i18n="feat4Desc">Slots, table games, live casino &amp; more.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- ====== STATISTICS ====== -->
        <section class="stats">
            <div class="container">
                <div class="stats__grid">
                    <div class="stat-card fade-in">
                        <span class="stat-card__icon">👥</span>
                        <div class="stat-card__number" data-count="50000">0</div>
                        <div class="stat-card__label" data-i18n="stat1">Players</div>
                    </div>
                    <div class="stat-card fade-in">
                        <span class="stat-card__icon">💰</span>
                        <div class="stat-card__number" data-count="10000000" data-prefix="€" data-suffix="+">0</div>
                        <div class="stat-card__label" data-i18n="stat2">Paid Out</div>
                    </div>
                    <div class="stat-card fade-in">
                        <span class="stat-card__icon">⭐</span>
                        <div class="stat-card__number" data-count="4.9" data-suffix="/5">0</div>
                        <div class="stat-card__label" data-i18n="stat3">Player Rating</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- ====== VIP ====== -->
        <section class="vip">
            <div class="container">
                <div class="vip__card fade-in">
                    <span class="vip__icon">💎</span>
                    <h2 class="vip__title" data-i18n="vipTitle">High Roller Rewards</h2>
                    <p class="vip__text" data-i18n="vipText">
                        Unlock exclusive VIP promotions, cashback rewards and premium bonuses designed for high rollers.
                    </p>
                </div>
            </div>
        </section>

        <!-- ====== CTA ====== -->
        <section class="cta">
            <div class="container">
                <h2 class="cta__title fade-in" data-i18n="ctaTitle">Ready to Start Winning?</h2>
                <p class="cta__sub fade-in" data-i18n="ctaSub">Join the elite community of winners today.</p>
                <div class="cta__buttons fade-in">
                    <a href="https://getnvpartnerspromo.com/l/6a5dd65667ae9214180cfde2" target="_blank" rel="noopener" class="btn btn--gold" id="ctaPrimary">
                        🎰 <span data-i18n="ctaBtn1">Claim Your Exclusive Bonus</span>
                    </a>
                    <a href="https://t.me/+42ULaMHIyEgxZjk6" target="_blank" rel="noopener" class="btn btn--glass" id="ctaSecondary">
                        💬 <span data-i18n="ctaBtn2">Join Our VIP Telegram Community</span>
                    </a>
                </div>
            </div>
        </section>

    </main>

    <!-- ====== FOOTER ====== -->
    <footer class="footer">
        <div class="container">
            <div class="footer__text">
                <span>18+</span>
                <span class="divider">•</span>
                <span data-i18n="footer1">Responsible Gaming</span>
                <span class="divider">•</span>
                <span data-i18n="footer2">Play Responsibly</span>
                <span class="divider">•</span>
                <span>Copyright &copy; 2026</span>
            </div>
        </div>
    </footer>

    <!-- ============================================================
    JAVASCRIPT
    ============================================================ -->
    <script>
        // ============================================================
        // 1. PARTICLES
        // ============================================================
        (function initParticles() {
            const canvas = document.getElementById('particles-canvas');
            const ctx = canvas.getContext('2d');
            let w, h;
            const particles = [];
            const COUNT = 60;

            function resize() {
                w = canvas.width = window.innerWidth;
                h = canvas.height = window.innerHeight;
            }
            window.addEventListener('resize', resize);
            resize();

            class Particle {
                constructor() { this.reset(); }
                reset() {
                    this.x = Math.random() * w;
                    this.y = Math.random() * h;
                    this.size = Math.random() * 2.4 + 0.6;
                    this.speedX = (Math.random() - 0.5) * 0.4;
                    this.speedY = (Math.random() - 0.5) * 0.4;
                    this.opacity = Math.random() * 0.5 + 0.15;
                    this.hue = Math.random() > 0.6 ? 280 : (Math.random() > 0.5 ? 45 : 330);
                }
                update() {
                    this.x += this.speedX;
                    this.y += this.speedY;
                    if (this.x < 0 || this.x > w || this.y < 0 || this.y > h) this.reset();
                }
                draw() {
                    ctx.beginPath();
                    ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                    ctx.fillStyle = `hsla(${this.hue}, 80%, 65%, ${this.opacity})`;
                    ctx.fill();
                    // glow
                    ctx.shadowColor = `hsla(${this.hue}, 80%, 65%, 0.2)`;
                    ctx.shadowBlur = 12;
                    ctx.fill();
                    ctx.shadowBlur = 0;
                }
            }

            for (let i = 0; i < COUNT; i++) particles.push(new Particle());

            function animate() {
                ctx.clearRect(0, 0, w, h);
                particles.forEach(p => { p.update();
                    p.draw(); });
                requestAnimationFrame(animate);
            }
            animate();
        })();


        // ============================================================
        // 2. LANGUAGE SELECTOR
        // ============================================================
        (function initLanguage() {
            const toggle = document.getElementById('langToggle');
            const dropdown = document.getElementById('langDropdown');
            const items = dropdown.querySelectorAll('.lang-selector__item');
            const currentFlag = document.getElementById('currentFlag');
            const currentLabel = document.getElementById('currentLangLabel');

            // i18n dictionary
            const translations = {
                en: {
                    heroTitle: '🎁 Welcome Bonus up to €2,000 + 225 Free Spins',
                    heroSub: 'Join thousands of players and unlock your exclusive welcome package in less than one minute.',
                    heroBtn: 'Claim Your Welcome Bonus',
                    feat1Title: 'Instant Registration',
                    feat1Desc: 'Sign up in seconds and start playing immediately.',
                    feat2Title: 'Secure & Trusted Platform',
                    feat2Desc: 'Licensed, encrypted, and fair-play guaranteed.',
                    feat3Title: 'Fast Withdrawals',
                    feat3Desc: 'Get your winnings in record time, no delays.',
                    feat4Title: 'Thousands of Premium Games',
                    feat4Desc: 'Slots, table games, live casino & more.',
                    stat1: 'Players',
                    stat2: 'Paid Out',
                    stat3: 'Player Rating',
                    vipTitle: 'High Roller Rewards',
                    vipText: 'Unlock exclusive VIP promotions, cashback rewards and premium bonuses designed for high rollers.',
                    ctaTitle: 'Ready to Start Winning?',
                    ctaSub: 'Join the elite community of winners today.',
                    ctaBtn1: 'Claim Your Exclusive Bonus',
                    ctaBtn2: 'Join Our VIP Telegram Community',
                    footer1: 'Responsible Gaming',
                    footer2: 'Play Responsibly',
                },
                de: {
                    heroTitle: '🎁 Willkommensbonus bis zu €2.000 + 225 Freispiele',
                    heroSub: 'Schließe dich tausenden Spielern an und sichere dir dein exklusives Willkommenspaket in weniger als einer Minute.',
                    heroBtn: 'Bonus sichern',
                    feat1Title: 'Sofortige Registrierung',
                    feat1Desc: 'Melde dich in Sekunden an und spiele sofort los.',
                    feat2Title: 'Sichere & vertrauenswürdige Plattform',
                    feat2Desc: 'Lizenziert, verschlüsselt und fair play garantiert.',
                    feat3Title: 'Schnelle Auszahlungen',
                    feat3Desc: 'Erhalte deine Gewinne in Rekordzeit, ohne Verzögerungen.',
                    feat4Title: 'Tausende Premium-Spiele',
                    feat4Desc: 'Slots, Tischspiele, Live-Casino & mehr.',
                    stat1: 'Spieler',
                    stat2: 'Auszahlungen',
                    stat3: 'Spielerbewertung',
                    vipTitle: 'High Roller Belohnungen',
                    vipText: 'Erhalte exklusive VIP-Aktionen, Cashback und Premium-Boni für High Roller.',
                    ctaTitle: 'Bereit zu gewinnen?',
                    ctaSub: 'Tritt der elitären Community der Gewinner bei.',
                    ctaBtn1: 'Exklusiven Bonus sichern',
                    ctaBtn2: 'VIP Telegram Community beitreten',
                    footer1: 'Verantwortungsvolles Spielen',
                    footer2: 'Spiele verantwortungsvoll',
                },
                ru: {
                    heroTitle: '🎁 Приветственный бонус до €2 000 + 225 фриспинов',
                    heroSub: 'Присоединяйся к тысячам игроков и получи эксклюзивный приветственный пакет меньше чем за минуту.',
                    heroBtn: 'Получить бонус',
                    feat1Title: 'Мгновенная регистрация',
                    feat1Desc: 'Регистрируйся за секунды и начинай играть сразу.',
                    feat2Title: 'Надёжная платформа',
                    feat2Desc: 'Лицензировано, зашифровано и честная игра гарантирована.',
                    feat3Title: 'Быстрые выводы',
                    feat3Desc: 'Получай выигрыши моментально, без задержек.',
                    feat4Title: 'Тысячи премиум-игр',
                    feat4Desc: 'Слоты, настольные игры, live-казино и многое другое.',
                    stat1: 'Игроков',
                    stat2: 'Выплачено',
                    stat3: 'Рейтинг игроков',
                    vipTitle: 'Награды для хайроллеров',
                    vipText: 'Получи эксклюзивные VIP-акции, кэшбэк и премиум-бонусы для хайроллеров.',
                    ctaTitle: 'Готов начать выигрывать?',
                    ctaSub: 'Присоединяйся к элитному сообществу победителей сегодня.',
                    ctaBtn1: 'Получить эксклюзивный бонус',
                    ctaBtn2: 'Вступить в VIP Telegram сообщество',
                    footer1: 'Ответственная игра',
                    footer2: 'Играй ответственно',
                }
            };

            let currentLang = 'en';

            function setLanguage(lang) {
                currentLang = lang;
                const t = translations[lang];
                if (!t) return;

                document.querySelectorAll('[data-i18n]').forEach(el => {
                    const key = el.getAttribute('data-i18n');
                    if (t[key] !== undefined) {
                        // Preserve child nodes that might contain icons
                        const iconSpan = el.querySelector('span');
                        if (iconSpan && iconSpan.hasAttribute('data-i18n')) {
                            // nested translation handled separately
                        }
                        el.textContent = t[key];
                    }
                });

                // Update toggle
                const activeItem = dropdown.querySelector('.lang-selector__item.active');
                if (activeItem) {
                    const flag = activeItem.getAttribute('data-flag');
                    const label = activeItem.getAttribute('data-label');
                    currentFlag.textContent = flag || '🇺🇸';
                    currentLabel.textContent = label || 'EN';
                }

                // Update active class
                items.forEach(item => {
                    item.classList.toggle('active', item.getAttribute('data-lang') === lang);
                });

                // Re-apply any icons that got overwritten
                // Hero title has 🎁 – keep it
                // Buttons have icons
                document.querySelectorAll('.btn').forEach(btn => {
                    const icon = btn.querySelector('i, .btn-icon');
                    // We handle this by keeping icon spans separate
                });

                // Fix: ensure hero title keeps its icon
                const heroTitle = document.querySelector('[data-i18n="heroTitle"]');
                if (heroTitle && lang === 'en') heroTitle.textContent = translations.en.heroTitle;
                else if (heroTitle && lang === 'de') heroTitle.textContent = translations.de.heroTitle;
                else if (heroTitle && lang === 'ru') heroTitle.textContent = translations.ru.heroTitle;

                // Fix hero button
                const heroBtn = document.querySelector('#heroCta span[data-i18n]');
                if (heroBtn) heroBtn.textContent = t.heroBtn || 'Claim Your Welcome Bonus';

                // Fix CTA buttons
                const cta1 = document.querySelector('#ctaPrimary span[data-i18n]');
                if (cta1) cta1.textContent = t.ctaBtn1 || 'Claim Your Exclusive Bonus';
                const cta2 = document.querySelector('#ctaSecondary span[data-i18n]');
                if (cta2) cta2.textContent = t.ctaBtn2 || 'Join Our VIP Telegram Community';

                // Fix feature titles/descs
                document.querySelectorAll('.feature-card').forEach((card, idx) => {
                    const title = card.querySelector('.feature-card__title');
                    const desc = card.querySelector('.feature-card__desc');
                    const keys = ['feat1Title', 'feat2Title', 'feat3Title', 'feat4Title'];
                    const descKeys = ['feat1Desc', 'feat2Desc', 'feat3Desc', 'feat4Desc'];
                    if (title && keys[idx]) title.textContent = t[keys[idx]] || title.textContent;
                    if (desc && descKeys[idx]) desc.textContent = t[descKeys[idx]] || desc.textContent;
                });

                // Fix stats labels
                const statLabels = document.querySelectorAll('.stat-card__label');
                const statKeys = ['stat1', 'stat2', 'stat3'];
                statLabels.forEach((label, idx) => {
                    if (statKeys[idx]) label.textContent = t[statKeys[idx]] || label.textContent;
                });

                // VIP
                const vipTitle = document.querySelector('.vip__title');
                if (vipTitle) vipTitle.textContent = t.vipTitle || 'High Roller Rewards';
                const vipText = document.querySelector('.vip__text');
                if (vipText) vipText.textContent = t.vipText || vipText.textContent;

                // CTA title/sub
                const ctaTitle = document.querySelector('.cta__title');
                if (ctaTitle) ctaTitle.textContent = t.ctaTitle || 'Ready to Start Winning?';
                const ctaSub = document.querySelector('.cta__sub');
                if (ctaSub) ctaSub.textContent = t.ctaSub || 'Join the elite community of winners today.';

                // Footer
                const footerSpans = document.querySelectorAll('.footer__text span[data-i18n]');
                if (footerSpans.length >= 2) {
                    footerSpans[0].textContent = t.footer1 || 'Responsible Gaming';
                    footerSpans[1].textContent = t.footer2 || 'Play Responsibly';
                }
            }

            // Toggle dropdown
            toggle.addEventListener('click', (e) => {
                e.stopPropagation();
                toggle.classList.toggle('open');
                dropdown.classList.toggle('open');
            });

            // Select language
            items.forEach(item => {
                item.addEventListener('click', (e) => {
                    e.stopPropagation();
                    const lang = item.getAttribute('data-lang');
                    const flag = item.getAttribute('data-flag');
                    const label = item.getAttribute('data-label');
                    if (lang) {
                        setLanguage(lang);
                        currentFlag.textContent = flag || '🇺🇸';
                        currentLabel.textContent = label || 'EN';
                    }
                    toggle.classList.remove('open');
                    dropdown.classList.remove('open');
                });
            });

            // Close dropdown on outside click
            document.addEventListener('click', () => {
                toggle.classList.remove('open');
                dropdown.classList.remove('open');
            });

            // Set default
            setLanguage('en');
        })();


        // ============================================================
        // 3. RIPPLE EFFECT ON BUTTONS
        // ============================================================
        (function initRipple() {
            document.querySelectorAll('.btn').forEach(btn => {
                btn.addEventListener('click', function(e) {
                    const rect = this.getBoundingClientRect();
                    const x = e.clientX - rect.left;
                    const y = e.clientY - rect.top;
                    const ripple = document.createElement('span');
                    ripple.className = 'ripple';
                    const size = Math.max(rect.width, rect.height) * 0.6;
                    ripple.style.width = ripple.style.height = size + 'px';
                    ripple.style.left = (x - size / 2) + 'px';
                    ripple.style.top = (y - size / 2) + 'px';
                    this.appendChild(ripple);
                    setTimeout(() => ripple.remove(), 700);
                });
            });
        })();


        // ============================================================
        // 4. COUNTER ANIMATION (Intersection Observer)
        // ============================================================
        (function initCounters() {
            const counters = document.querySelectorAll('.stat-card__number[data-count]');
            let animated = false;

            function animateCounter(el) {
                const target = parseFloat(el.getAttribute('data-count'));
                const prefix = el.getAttribute('data-prefix') || '';
                const suffix = el.getAttribute('data-suffix') || '';
                const duration = 1800;
                const startTime = performance.now();

                function update(time) {
                    const progress = Math.min((time - startTime) / duration, 1);
                    const eased = 1 - Math.pow(1 - progress, 3);
                    const current = eased * target;
                    if (Number.isInteger(target)) {
                        el.textContent = prefix + Math.floor(current) + suffix;
                    } else {
                        el.textContent = prefix + current.toFixed(1) + suffix;
                    }
                    if (progress < 1) {
                        requestAnimationFrame(update);
                    } else {
                        el.textContent = prefix + target + suffix;
                    }
                }
                requestAnimationFrame(update);
            }

            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting && !animated) {
                        animated = true;
                        counters.forEach(c => animateCounter(c));
                    }
                });
            }, { threshold: 0.3 });

            counters.forEach(c => observer.observe(c));
        })();


        // ============================================================
        // 5. FADE-IN ON SCROLL (Intersection Observer)
        // ============================================================
        (function initFadeIn() {
            const els = document.querySelectorAll('.fade-in');
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('visible');
                    }
                });
            }, { threshold: 0.15, rootMargin: '0px 0px -30px 0px' });

            els.forEach(el => observer.observe(el));

            // Also observe stat cards and feature cards that might not have fade-in
            document.querySelectorAll('.stat-card, .feature-card, .vip__card, .cta__buttons, .hero__badge, .hero__title, .hero__subtitle, .hero .btn')
                .forEach(el => {
                    if (!el.classList.contains('fade-in')) {
                        el.classList.add('fade-in');
                        observer.observe(el);
                    }
                });
        })();


        // ============================================================
        // 6. HEADER SHADOW ON SCROLL
        // ============================================================
        (function initHeaderShadow() {
            const header = document.getElementById('header');
            window.addEventListener('scroll', () => {
                if (window.scrollY > 20) {
                    header.style.boxShadow = '0 4px 40px rgba(0,0,0,0.5)';
                    header.style.borderBottomColor = 'rgba(255,255,255,0.06)';
                } else {
                    header.style.boxShadow = 'none';
                    header.style.borderBottomColor = 'rgba(255,255,255,0.04)';
                }
            });
        })();
    </script>

</body>
</html>