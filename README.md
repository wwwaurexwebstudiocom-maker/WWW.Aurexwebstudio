
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Aurex Web Studio - Bespoke, world-class websites for discerning businesses worldwide.">
    <title>Aurex Web Studio | Bespoke Digital Craftsmanship</title>

    <!-- Google Fonts: Cormorant Garamond (display) + Jost (body/utility) -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,500;0,600;0,700;1,500;1,600&family=Jost:wght@300;400;500;600;700&display=swap" rel="stylesheet">

    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        /* ==========================================================================
           1. CORE VARIABLES & RESET — Palette: Obsidian / Ivory / Champagne Gold
           ========================================================================== */
        :root {
            --bg-dark: #0A0908;
            --bg-card: rgba(20, 18, 14, 0.55);
            --bg-card-hover: rgba(28, 24, 18, 0.75);
            --primary: #C9A961;
            --primary-light: #E4CE8F;
            --primary-glow: rgba(201, 169, 97, 0.28);
            --accent-cyan: #7A5C33;
            --text-main: #F5F1E8;
            --text-muted: #A89E8C;
            --border-glass: rgba(201, 169, 97, 0.14);
            --border-glass-glow: rgba(201, 169, 97, 0.45);
            --ink: #12100C;
            --font-heading: 'Cormorant Garamond', serif;
            --font-body: 'Jost', sans-serif;
            --transition-smooth: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
        }

        *, *::before, *::after {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        html {
            scroll-behavior: smooth;
            font-size: 16px;
            background-color: var(--bg-dark);
            color: var(--text-main);
            font-family: var(--font-body);
            font-weight: 300;
            overflow-x: hidden;
        }

        body {
            line-height: 1.6;
            overflow-x: hidden;
            position: relative;
        }

        /* ==========================================================================
           2. DYNAMIC MESH BACKGROUND & PARTICLES
           ========================================================================== */
        #particle-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: -2;
            pointer-events: none;
        }

        .bg-mesh {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: -3;
            background:
                radial-gradient(circle at 15% 20%, rgba(201, 169, 97, 0.10) 0%, transparent 45%),
                radial-gradient(circle at 85% 60%, rgba(122, 92, 51, 0.10) 0%, transparent 40%),
                radial-gradient(circle at 50% 85%, rgba(201, 169, 97, 0.08) 0%, transparent 50%),
                #0A0908;
            pointer-events: none;
        }

        /* ==========================================================================
           3. TYPOGRAPHY & UTILITIES
           ========================================================================== */
        h1, h2, h3, h4, h5, h6 {
            font-family: var(--font-heading);
            color: var(--text-main);
            line-height: 1.15;
            font-weight: 600;
        }

        .gradient-text {
            background: linear-gradient(135deg, #FFFFFF 0%, var(--primary-light) 55%, var(--primary) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-style: italic;
        }

        .gradient-accent {
            background: linear-gradient(135deg, var(--primary-light) 0%, var(--primary) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        a {
            text-decoration: none;
            color: inherit;
            transition: var(--transition-smooth);
        }

        .container {
            width: 100%;
            max-width: 1280px;
            margin: 0 auto;
            padding: 0 1.5rem;
        }

        .section-padding {
            padding: 8rem 0;
        }

        .text-center { text-align: center; }
        .mx-auto { margin-left: auto; margin-right: auto; }

        /* Section Title Eyebrow — hairline label, no pill fill */
        .badge {
            display: inline-flex;
            align-items: center;
            gap: 0.65rem;
            padding: 0.5rem 0;
            border-top: 1px solid var(--border-glass-glow);
            border-bottom: 1px solid var(--border-glass-glow);
            color: var(--primary-light);
            font-family: var(--font-body);
            font-size: 0.75rem;
            font-weight: 500;
            text-transform: uppercase;
            letter-spacing: 0.22em;
            margin-bottom: 1.75rem;
        }

        .section-header {
            max-width: 750px;
            margin: 0 auto 5rem auto;
        }

        .section-title {
            font-size: clamp(2.1rem, 4vw, 3.5rem);
            margin-bottom: 1.25rem;
            letter-spacing: -0.01em;
            font-weight: 600;
        }

        .section-subtitle {
            font-size: 1.1rem;
            color: var(--text-muted);
            font-weight: 300;
        }

        /* Glass / Hairline Card Engine */
        .glass-card {
            background: var(--bg-card);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid var(--border-glass);
            border-radius: 0.35rem;
            transition: var(--transition-smooth);
            position: relative;
            overflow: hidden;
        }

        .glass-card::before {
            content: '';
            position: absolute;
            top: 0; left: 0; right: 0; height: 1px;
            background: linear-gradient(90deg, transparent, rgba(201, 169, 97, 0.55), transparent);
        }

        .glass-card:hover {
            border-color: var(--border-glass-glow);
            transform: translateY(-6px);
            box-shadow: 0 20px 40px -15px rgba(0, 0, 0, 0.6), 0 0 30px 0 var(--primary-glow);
            background: var(--bg-card-hover);
        }

        /* Buttons */
        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 0.75rem;
            padding: 1rem 2.25rem;
            border-radius: 9999px;
            font-weight: 500;
            font-size: 0.95rem;
            letter-spacing: 0.02em;
            cursor: pointer;
            transition: var(--transition-smooth);
            border: none;
            outline: none;
            font-family: var(--font-body);
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--primary-light) 0%, var(--primary) 100%);
            color: var(--ink);
            box-shadow: 0 10px 25px -5px var(--primary-glow);
            position: relative;
            z-index: 1;
            overflow: hidden;
        }

        .btn-primary::after {
            content: '';
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            background: linear-gradient(135deg, #FFFFFF 0%, var(--primary-light) 100%);
            z-index: -1;
            opacity: 0;
            transition: var(--transition-smooth);
        }

        .btn-primary:hover::after {
            opacity: 1;
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 30px -5px rgba(201, 169, 97, 0.5);
        }

        .btn-secondary {
            background: rgba(201, 169, 97, 0.04);
            border: 1px solid var(--border-glass-glow);
            color: var(--text-main);
            backdrop-filter: blur(10px);
        }

        .btn-secondary:hover {
            background: rgba(201, 169, 97, 0.1);
            border-color: var(--primary-light);
            transform: translateY(-3px);
            color: var(--primary-light);
        }

        /* Scroll Reveal Animation Classes */
        .reveal {
            opacity: 0;
            transform: translateY(40px);
            transition: all 0.8s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* ==========================================================================
           4. NAVIGATION (HEADER)
           ========================================================================== */
        .header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;
            transition: var(--transition-smooth);
            padding: 1.5rem 0;
        }

        .header.scrolled {
            padding: 0.85rem 0;
            background: rgba(10, 9, 8, 0.9);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid var(--border-glass);
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }

        .nav-container {
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 0.85rem;
            font-family: var(--font-heading);
            font-size: 1.55rem;
            font-weight: 600;
            letter-spacing: 0.04em;
            color: #FFF;
        }

        .logo-icon {
            width: 42px;
            height: 42px;
            background: linear-gradient(135deg, var(--primary-light) 0%, var(--accent-cyan) 100%);
            border-radius: 4px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.15rem;
            color: var(--ink);
            box-shadow: 0 0 20px var(--primary-glow);
            font-family: var(--font-heading);
            font-weight: 700;
        }

        .nav-links {
            display: flex;
            align-items: center;
            gap: 2.5rem;
            list-style: none;
        }

        .nav-link {
            font-size: 0.85rem;
            font-weight: 400;
            text-transform: uppercase;
            letter-spacing: 0.08em;
            color: var(--text-muted);
            position: relative;
        }

        .nav-link:hover, .nav-link.active {
            color: var(--primary-light);
        }

        .nav-link::after {
            content: '';
            position: absolute;
            bottom: -6px;
            left: 0;
            width: 0%;
            height: 1px;
            background: var(--primary-light);
            transition: var(--transition-smooth);
        }

        .nav-link:hover::after, .nav-link.active::after {
            width: 100%;
        }

        .menu-btn {
            display: none;
            font-size: 1.5rem;
            color: #FFF;
            cursor: pointer;
            background: none;
            border: none;
        }

        /* ==========================================================================
           5. HERO SECTION
           ========================================================================== */
        .hero {
            padding-top: 12rem;
            padding-bottom: 8rem;
            position: relative;
            overflow: hidden;
        }

        .hero-grid {
            display: grid;
            grid-template-columns: 1.1fr 0.9fr;
            gap: 4rem;
            align-items: center;
        }

        .hero-content {
            text-align: left;
        }

        .hero-title {
            font-size: clamp(2.75rem, 5.5vw, 4.5rem);
            line-height: 1.08;
            margin-bottom: 1.5rem;
            letter-spacing: -0.01em;
            font-weight: 600;
        }

        .hero-subheadline {
            font-size: 1.2rem;
            color: var(--text-muted);
            margin-bottom: 2.5rem;
            max-width: 600px;
            line-height: 1.7;
            font-weight: 300;
        }

        .hero-cta-group {
            display: flex;
            align-items: center;
            gap: 1.25rem;
            flex-wrap: wrap;
        }

        .hero-mockup-container {
            position: relative;
            perspective: 1000px;
        }

        /* Custom SVG Rendered Mockups */
        .mockup-wrapper {
            position: relative;
            width: 100%;
            transform: rotateY(-8deg) rotateX(6deg);
            transition: var(--transition-smooth);
            transform-style: preserve-3d;
        }

        .hero-mockup-container:hover .mockup-wrapper {
            transform: rotateY(0deg) rotateX(0deg) scale(1.02);
        }

        .laptop-frame {
            border: 1px solid var(--border-glass-glow);
            border-radius: 10px 10px 3px 3px;
            padding: 12px 12px 0 12px;
            box-shadow: 0 30px 60px rgba(0,0,0,0.8), 0 0 50px rgba(201, 169, 97, 0.12);
            position: relative;
            overflow: hidden;
            background: linear-gradient(180deg, #171310 0%, #0A0908 100%);
        }

        .screen-content {
            width: 100%;
            height: 320px;
            background: #08070600;
            background: #060504;
            border-radius: 6px 6px 0 0;
            overflow: hidden;
            position: relative;
            border: 1px solid rgba(201,169,97,0.08);
        }

        /* Animated Mockup Graphic UI */
        .mock-nav { height: 30px; background: rgba(201,169,97,0.03); display: flex; align-items: center; padding: 0 12px; gap: 6px; border-bottom: 1px solid rgba(201,169,97,0.08); }
        .mock-dot { width: 8px; height: 8px; border-radius: 50%; }
        .mock-dot.r { background: #8B4A3D; } .mock-dot.y { background: #C9A961; } .mock-dot.g { background: #6E7D5A; }
        .mock-body { padding: 20px; display: grid; grid-template-columns: 2fr 1fr; gap: 15px; }
        .mock-hero-line { height: 16px; background: linear-gradient(90deg, var(--primary) 0%, var(--primary-light) 100%); border-radius: 2px; margin-bottom: 10px; width: 80%; }
        .mock-text-line { height: 8px; background: rgba(201,169,97,0.12); border-radius: 2px; margin-bottom: 8px; }
        .mock-card { height: 100px; background: rgba(201,169,97,0.03); border: 1px solid rgba(201,169,97,0.1); border-radius: 4px; padding: 10px; }

        .phone-frame {
            position: absolute;
            bottom: -20px;
            right: -20px;
            width: 160px;
            height: 310px;
            background: #0D0B09;
            border: 3px solid #3A3226;
            border-radius: 28px;
            padding: 8px;
            box-shadow: 0 25px 50px rgba(0,0,0,0.9), 0 0 30px rgba(201, 169, 97, 0.15);
            z-index: 10;
        }

        .phone-screen {
            width: 100%;
            height: 100%;
            background: #060504;
            border-radius: 22px;
            overflow: hidden;
            padding: 12px 8px;
        }

        /* Floating Badge Elements */
        .float-badge {
            position: absolute;
            padding: 0.85rem 1.25rem;
            border-radius: 0.5rem;
            background: rgba(18, 16, 12, 0.9);
            backdrop-filter: blur(20px);
            border: 1px solid var(--border-glass-glow);
            display: flex;
            align-items: center;
            gap: 0.85rem;
            box-shadow: 0 20px 30px rgba(0,0,0,0.5);
            animation: float 6s ease-in-out infinite;
            z-index: 15;
        }

        .float-1 { top: -20px; left: -20px; }
        .float-2 { bottom: 40px; left: -30px; animation-delay: -3s; }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-12px); }
        }

        /* ==========================================================================
           6. WHY EVERY BUSINESS NEEDS A WEBSITE
           ========================================================================== */
        .why-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2rem;
        }

        .why-card {
            padding: 2.5rem;
        }

        .icon-box {
            width: 56px;
            height: 56px;
            border-radius: 0.4rem;
            background: linear-gradient(135deg, rgba(201, 169, 97, 0.16) 0%, rgba(122, 92, 51, 0.08) 100%);
            border: 1px solid var(--border-glass-glow);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.4rem;
            color: var(--primary-light);
            margin-bottom: 1.5rem;
        }

        .why-card h3 {
            font-size: 1.45rem;
            margin-bottom: 1rem;
            font-weight: 600;
        }

        .why-card p {
            color: var(--text-muted);
            font-size: 0.975rem;
            line-height: 1.6;
            font-weight: 300;
        }

        /* Comparison Banner */
        .comparison-box {
            margin-top: 4rem;
            padding: 3rem;
            border-radius: 0.5rem;
            background: linear-gradient(135deg, rgba(18, 16, 12, 0.9) 0%, rgba(28, 24, 18, 0.5) 100%);
            border: 1px solid var(--border-glass-glow);
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2rem;
        }

        .comp-column h4 {
            font-size: 1.3rem;
            margin-bottom: 1.25rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            font-weight: 600;
        }

        .comp-list {
            list-style: none;
            display: flex;
            flex-direction: column;
            gap: 0.85rem;
        }

        .comp-list li {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            font-size: 0.95rem;
            color: var(--text-muted);
            font-weight: 300;
        }

        .comp-list i.fa-xmark { color: #8B4A3D; }
        .comp-list i.fa-check { color: var(--primary); }

        /* ==========================================================================
           7. INDUSTRIES WE BUILD FOR
           ========================================================================== */
        .industries-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            gap: 1.5rem;
        }

        .industry-card {
            padding: 2rem 1.5rem;
            text-align: center;
            border-radius: 0.4rem;
            cursor: default;
        }

        .industry-card i {
            font-size: 2.1rem;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, #FFF 0%, var(--primary-light) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            transition: var(--transition-smooth);
        }

        .industry-card:hover i {
            transform: scale(1.1);
        }

        .industry-card h4 {
            font-size: 1.05rem;
            font-weight: 500;
            font-family: var(--font-body);
        }

        /* ==========================================================================
           8. OUR SERVICES
           ========================================================================== */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .service-card {
            padding: 2.5rem;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .service-header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 1.5rem;
        }

        .service-icon {
            width: 55px;
            height: 55px;
            border-radius: 0.4rem;
            background: rgba(201, 169, 97, 0.12);
            border: 1px solid var(--border-glass-glow);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.3rem;
            color: var(--primary-light);
        }

        .service-number {
            font-family: var(--font-heading);
            font-size: 1.75rem;
            font-weight: 700;
            font-style: italic;
            color: rgba(201, 169, 97, 0.18);
        }

        .service-card h3 {
            font-size: 1.45rem;
            margin-bottom: 1rem;
            font-weight: 600;
        }

        .service-card p {
            color: var(--text-muted);
            font-size: 0.95rem;
            line-height: 1.6;
            margin-bottom: 1.5rem;
            font-weight: 300;
        }

        .service-link {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            color: var(--primary-light);
            font-weight: 500;
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 0.06em;
        }

        .service-card:hover .service-link i {
            transform: translateX(5px);
        }

        /* ==========================================================================
           9. WHY CHOOSE AUREX WEB STUDIO
           ========================================================================== */
        .why-choose-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
        }

        .feature-box {
            padding: 1.75rem;
            display: flex;
            align-items: flex-start;
            gap: 1.25rem;
        }

        .feature-icon-check {
            width: 34px;
            height: 34px;
            border-radius: 50%;
            background: linear-gradient(135deg, rgba(201, 169, 97, 0.22) 0%, rgba(122, 92, 51, 0.14) 100%);
            border: 1px solid var(--border-glass-glow);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--primary-light);
            flex-shrink: 0;
            margin-top: 2px;
        }

        .feature-box h4 {
            font-size: 1.1rem;
            margin-bottom: 0.35rem;
            font-weight: 600;
        }

        .feature-box p {
            font-size: 0.875rem;
            color: var(--text-muted);
            font-weight: 300;
        }

        /* ==========================================================================
           10. PORTFOLIO SHOWCASE
           ========================================================================== */
        .portfolio-filter {
            display: flex;
            justify-content: center;
            gap: 0.85rem;
            margin-bottom: 3.5rem;
            flex-wrap: wrap;
        }

        .filter-btn {
            padding: 0.6rem 1.5rem;
            border-radius: 9999px;
            background: rgba(201, 169, 97, 0.03);
            border: 1px solid var(--border-glass);
            color: var(--text-muted);
            font-size: 0.8rem;
            font-weight: 500;
            text-transform: uppercase;
            letter-spacing: 0.05em;
            cursor: pointer;
            transition: var(--transition-smooth);
        }

        .filter-btn:hover, .filter-btn.active {
            background: var(--primary);
            color: var(--ink);
            border-color: var(--primary-light);
            box-shadow: 0 0 20px var(--primary-glow);
        }

        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(360px, 1fr));
            gap: 2rem;
        }

        .portfolio-card {
            border-radius: 0.5rem;
            overflow: hidden;
        }

        .portfolio-thumb {
            width: 100%;
            height: 240px;
            background: #0D0B09;
            position: relative;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        /* Modern Abstract Mockup Visuals */
        .thumb-bg {
            width: 90%;
            height: 85%;
            border-radius: 6px 6px 0 0;
            background: #060504;
            border: 1px solid rgba(201,169,97,0.14);
            padding: 1rem;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
            transition: var(--transition-smooth);
        }

        .portfolio-card:hover .thumb-bg {
            transform: scale(1.05);
        }

        .portfolio-info {
            padding: 1.75rem;
        }

        .portfolio-tag {
            font-size: 0.72rem;
            text-transform: uppercase;
            letter-spacing: 0.1em;
            color: var(--primary-light);
            font-weight: 600;
            margin-bottom: 0.5rem;
            display: block;
        }

        .portfolio-info h3 {
            font-size: 1.3rem;
            margin-bottom: 0.75rem;
            font-weight: 600;
        }

        /* ==========================================================================
           11. DEVELOPMENT PROCESS
           ========================================================================== */
        .process-timeline {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
            gap: 1.5rem;
            position: relative;
        }

        .process-step {
            padding: 2rem 1.25rem;
            text-align: center;
            position: relative;
        }

        .step-number {
            width: 52px;
            height: 52px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary-light) 0%, var(--primary) 100%);
            color: var(--ink);
            font-family: var(--font-heading);
            font-weight: 700;
            font-style: italic;
            font-size: 1.35rem;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 1.5rem auto;
            box-shadow: 0 0 20px var(--primary-glow);
        }

        .process-step h4 {
            font-size: 1.1rem;
            margin-bottom: 0.5rem;
            font-weight: 600;
        }

        .process-step p {
            font-size: 0.85rem;
            color: var(--text-muted);
            font-weight: 300;
        }

        /* ==========================================================================
           12. TESTIMONIALS
           ========================================================================== */
        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
            gap: 2rem;
        }

        .testimonial-card {
            padding: 2.5rem;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .stars {
            color: var(--primary-light);
            margin-bottom: 1.25rem;
            font-size: 0.85rem;
            display: flex;
            gap: 4px;
        }

        .testimonial-text {
            color: #E8E2D4;
            font-size: 1.05rem;
            line-height: 1.7;
            font-family: var(--font-heading);
            font-style: italic;
            font-weight: 500;
            margin-bottom: 2rem;
        }

        .client-profile {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .client-avatar {
            width: 48px;
            height: 48px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary-light), var(--primary));
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            font-family: var(--font-heading);
            color: var(--ink);
            border: 1px solid var(--border-glass-glow);
        }

        .client-info h4 {
            font-size: 1rem;
            font-weight: 600;
        }

        .client-info span {
            font-size: 0.8rem;
            color: var(--text-muted);
            font-weight: 300;
        }

        /* ==========================================================================
           13. FREQUENTLY ASKED QUESTIONS (ACCORDION)
           ========================================================================== */
        .faq-container {
            max-width: 850px;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
            gap: 1.25rem;
        }

        .faq-item {
            border-radius: 0.4rem;
            overflow: hidden;
        }

        .faq-question {
            width: 100%;
            padding: 1.5rem 2rem;
            background: transparent;
            border: none;
            color: var(--text-main);
            font-family: var(--font-heading);
            font-size: 1.15rem;
            font-weight: 600;
            text-align: left;
            display: flex;
            align-items: center;
            justify-content: space-between;
            cursor: pointer;
            gap: 1rem;
        }

        .faq-icon {
            width: 32px;
            height: 32px;
            border-radius: 50%;
            background: rgba(201, 169, 97, 0.06);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.8rem;
            color: var(--primary-light);
            transition: var(--transition-smooth);
        }

        .faq-item.active .faq-icon {
            transform: rotate(180deg);
            background: var(--primary);
            color: var(--ink);
        }

        .faq-answer {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.4s cubic-bezier(0, 1, 0, 1);
            padding: 0 2rem;
            color: var(--text-muted);
            font-size: 0.975rem;
            line-height: 1.7;
            font-weight: 300;
        }

        .faq-item.active .faq-answer {
            max-height: 300px;
            padding: 0 2rem 1.75rem 2rem;
            transition: max-height 0.4s cubic-bezier(0.16, 1, 0.3, 1);
        }

        /* ==========================================================================
           14. CONTACT SECTION & FOOTER
           ========================================================================== */
        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1.2fr;
            gap: 3.5rem;
        }

        .contact-info-card {
            padding: 3rem;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .contact-detail-item {
            display: flex;
            align-items: flex-start;
            gap: 1.25rem;
            margin-bottom: 2rem;
        }

        .contact-detail-icon {
            width: 46px;
            height: 46px;
            border-radius: 0.4rem;
            background: rgba(201, 169, 97, 0.12);
            border: 1px solid var(--border-glass-glow);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--primary-light);
            font-size: 1.2rem;
            flex-shrink: 0;
        }

        .contact-detail-text h4 {
            font-size: 1rem;
            margin-bottom: 0.25rem;
            font-weight: 600;
        }

        .contact-detail-text a, .contact-detail-text p {
            color: var(--text-muted);
            font-size: 0.95rem;
            font-weight: 300;
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 2rem;
        }

        .social-icon {
            width: 42px;
            height: 42px;
            border-radius: 50%;
            background: rgba(201, 169, 97, 0.04);
            border: 1px solid var(--border-glass);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text-main);
            font-size: 1.05rem;
            transition: var(--transition-smooth);
        }

        .social-icon:hover {
            background: var(--primary);
            color: var(--ink);
            border-color: var(--primary-light);
            transform: translateY(-4px);
            box-shadow: 0 10px 20px var(--primary-glow);
        }

        .contact-form {
            padding: 3rem;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-label {
            display: block;
            font-size: 0.8rem;
            font-weight: 500;
            text-transform: uppercase;
            letter-spacing: 0.06em;
            margin-bottom: 0.5rem;
            color: var(--text-muted);
        }

        .form-control {
            width: 100%;
            padding: 1rem 1.25rem;
            border-radius: 0.35rem;
            background: rgba(201, 169, 97, 0.03);
            border: 1px solid var(--border-glass);
            color: #FFF;
            font-family: var(--font-body);
            font-weight: 300;
            font-size: 0.975rem;
            transition: var(--transition-smooth);
            outline: none;
        }

        .form-control:focus {
            border-color: var(--primary-light);
            background: rgba(201, 169, 97, 0.06);
            box-shadow: 0 0 15px var(--primary-glow);
        }

        textarea.form-control {
            resize: vertical;
            min-height: 130px;
        }

        /* Footer */
        .footer {
            border-top: 1px solid var(--border-glass);
            padding: 5rem 0 2.5rem 0;
            background: rgba(6, 5, 4, 0.95);
        }

        .footer-grid {
            display: grid;
            grid-template-columns: 2fr 1fr 1fr 1fr;
            gap: 3rem;
            margin-bottom: 4rem;
        }

        .footer-brand p {
            color: var(--text-muted);
            margin-top: 1.25rem;
            max-width: 320px;
            font-size: 0.925rem;
            font-weight: 300;
        }

        .footer-title {
            font-size: 1.05rem;
            margin-bottom: 1.5rem;
            color: #FFF;
            font-weight: 600;
        }

        .footer-links {
            list-style: none;
            display: flex;
            flex-direction: column;
            gap: 0.85rem;
        }

        .footer-links a {
            color: var(--text-muted);
            font-size: 0.9rem;
            font-weight: 300;
        }

        .footer-links a:hover {
            color: var(--primary-light);
        }

        .footer-bottom {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding-top: 2rem;
            border-top: 1px solid rgba(201, 169, 97, 0.08);
            font-size: 0.85rem;
            color: var(--text-muted);
            font-weight: 300;
        }

        .footer-legal {
            display: flex;
            gap: 1.5rem;
        }

        /* Floating WhatsApp Button */
        .whatsapp-float {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            width: 58px;
            height: 58px;
            background: var(--ink);
            border: 1px solid var(--border-glass-glow);
            color: #25D366;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.7rem;
            box-shadow: 0 10px 25px rgba(0,0,0,0.5), 0 0 20px rgba(201,169,97,0.15);
            z-index: 999;
            transition: var(--transition-smooth);
        }

        .whatsapp-float:hover {
            transform: scale(1.08);
            border-color: var(--primary-light);
            box-shadow: 0 15px 30px rgba(0,0,0,0.6), 0 0 25px rgba(201,169,97,0.3);
        }

        /* ==========================================================================
           15. RESPONSIVE MEDIA QUERIES
           ========================================================================== */
        @media (max-width: 1024px) {
            .hero-grid { grid-template-columns: 1fr; gap: 5rem; text-align: center; }
            .hero-content { text-align: center; }
            .hero-subheadline { margin-left: auto; margin-right: auto; }
            .hero-cta-group { justify-content: center; }
            .contact-grid { grid-template-columns: 1fr; }
            .footer-grid { grid-template-columns: 1fr 1fr; }
            .comparison-box { grid-template-columns: 1fr; }
        }

        @media (max-width: 768px) {
            .section-padding { padding: 5rem 0; }
            .menu-btn { display: block; }
            .nav-links {
                position: fixed;
                top: 0; right: -100%;
                width: 80%; height: 100vh;
                background: rgba(10, 9, 8, 0.98);
                backdrop-filter: blur(25px);
                flex-direction: column;
                justify-content: center;
                gap: 2rem;
                transition: var(--transition-smooth);
                border-left: 1px solid var(--border-glass);
            }
            .nav-links.active { right: 0; }
            .footer-grid { grid-template-columns: 1fr; }
            .footer-bottom { flex-direction: column; gap: 1rem; text-align: center; }
            .phone-frame { display: none; }
        }
    </style>
</head>
<body>

    <!-- Dynamic Canvas & Background Layer -->
    <div class="bg-mesh"></div>
    <canvas id="particle-canvas"></canvas>

    <!-- Floating WhatsApp Action Button -->
    <a href="https://wa.me/2349168059744?text=Hello%20Aurex%20Web%20Studio,%20I%20would%20like%20to%20inquire%20about%20building%20a%20website." class="whatsapp-float" target="_blank" aria-label="Message us on WhatsApp">
        <i class="fa-brands fa-whatsapp"></i>
    </a>

    <!-- Navigation Bar -->
    <header class="header" id="header">
        <div class="container nav-container">
            <a href="#" class="logo">
                <div class="logo-icon">A</div>
                <span>AUREX <span class="gradient-accent" style="font-style: italic;">Studio</span></span>
            </a>

            <ul class="nav-links" id="nav-links">
                <li><a href="#home" class="nav-link active">Home</a></li>
                <li><a href="#why-us" class="nav-link">Why Choose Us</a></li>
                <li><a href="#services" class="nav-link">Services</a></li>
                <li><a href="#portfolio" class="nav-link">Portfolio</a></li>
                <li><a href="#process" class="nav-link">Process</a></li>
                <li><a href="#faq" class="nav-link">FAQ</a></li>
            </ul>

            <div style="display: flex; gap: 1rem; align-items: center;">
                <a href="#contact" class="btn btn-primary" style="padding: 0.75rem 1.5rem; font-size: 0.85rem;">Get Started</a>
                <button class="menu-btn" id="menu-btn" aria-label="Toggle Navigation"><i class="fa-solid fa-bars-staggered"></i></button>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container hero-grid">
            <div class="hero-content reveal">
                <div class="badge">A Bespoke Digital Studio</div>
                <h1 class="hero-title">Websites Crafted to <span class="gradient-text">Elevate Your Brand</span></h1>
                <p class="hero-subheadline">
                    Your website works for you around the clock. Whether you're a restaurant, real estate agency, fashion house, clinic, or startup, we craft refined digital experiences that command attention, earn trust, and convert.
                </p>
                <div class="hero-cta-group">
                    <a href="#portfolio" class="btn btn-primary">
                        <span>View Our Work</span>
                        <i class="fa-solid fa-arrow-right"></i>
                    </a>
                    <a href="https://wa.me/2349168059744" class="btn btn-secondary" target="_blank">
                        <i class="fa-brands fa-whatsapp" style="color: #25D366;"></i>
                        <span>Free Consultation</span>
                    </a>
                </div>
            </div>

            <!-- Premium Dynamic SVG/Glass Graphic Showcase -->
            <div class="hero-mockup-container reveal">
                <div class="float-badge float-1">
                    <i class="fa-solid fa-bolt" style="color: var(--primary-light); font-size: 1.2rem;"></i>
                    <div>
                        <div style="font-weight: 600; font-size: 0.85rem;">Ultra-Fast Performance</div>
                        <div style="font-size: 0.75rem; color: var(--text-muted);">99+ Google PageSpeed Score</div>
                    </div>
                </div>

                <div class="float-badge float-2">
                    <i class="fa-solid fa-shield-halved" style="color: var(--primary-light); font-size: 1.2rem;"></i>
                    <div>
                        <div style="font-weight: 600; font-size: 0.85rem;">Bank-Grade Security</div>
                        <div style="font-size: 0.75rem; color: var(--text-muted);">Encrypted &amp; Fully Protected</div>
                    </div>
                </div>

                <div class="mockup-wrapper">
                    <!-- Laptop Visual Mockup -->
                    <div class="laptop-frame">
                        <div class="screen-content">
                            <div class="mock-nav">
                                <div class="mock-dot r"></div>
                                <div class="mock-dot y"></div>
                                <div class="mock-dot g"></div>
                                <span style="font-size:0.65rem; color:var(--text-muted); margin-left:10px;">aurexwebstudio.com</span>
                            </div>
                            <div class="mock-body">
                                <div>
                                    <div class="mock-hero-line"></div>
                                    <div class="mock-text-line"></div>
                                    <div class="mock-text-line" style="width:60%;"></div>
                                    <div style="display:flex; gap:8px; margin-top:15px;">
                                        <div style="width:60px; height:20px; background:var(--primary); border-radius:2px;"></div>
                                        <div style="width:60px; height:20px; background:rgba(201,169,97,0.1); border-radius:2px;"></div>
                                    </div>
                                </div>
                                <div class="mock-card">
                                    <div style="width:30px; height:30px; border-radius:50%; background:var(--primary); margin-bottom:10px;"></div>
                                    <div class="mock-text-line"></div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Mobile Phone Visual Overlay -->
                    <div class="phone-frame">
                        <div class="phone-screen">
                            <div style="width:30px; height:4px; background:rgba(201,169,97,0.2); border-radius:2px; margin:0 auto 10px auto;"></div>
                            <div class="mock-hero-line" style="height:10px; width:90%;"></div>
                            <div class="mock-text-line" style="height:6px;"></div>
                            <div class="mock-text-line" style="height:6px; width:70%;"></div>
                            <div class="mock-card" style="height:80px; margin-top:15px;"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Why Business Needs A Website Section -->
    <section class="section-padding" id="why-us">
        <div class="container">
            <div class="section-header text-center reveal">
                <div class="badge">Essential Growth Engine</div>
                <h2 class="section-title">Why Social Media Alone <span class="gradient-text">Is Not Enough</span></h2>
                <p class="section-subtitle">Relying solely on social platforms limits your potential. A dedicated custom website is the foundation of authority, conversion, and global reach.</p>
            </div>

            <div class="why-grid">
                <div class="glass-card why-card reveal">
                    <div class="icon-box"><i class="fa-solid fa-clock"></i></div>
                    <h3>Open 24 Hours, 7 Days A Week</h3>
                    <p>Your business never sleeps. Allow customers to browse products, send inquiries, and place orders anytime from anywhere in the world.</p>
                </div>

                <div class="glass-card why-card reveal">
                    <div class="icon-box"><i class="fa-solid fa-magnifying-glass-chart"></i></div>
                    <h3>Be Found On Google (SEO)</h3>
                    <p>Appear instantly when customers search for your services online. Capture thousands of high-intent buyers who don't use social media.</p>
                </div>

                <div class="glass-card why-card reveal">
                    <div class="icon-box"><i class="fa-solid fa-shield-heart"></i></div>
                    <h3>Build Unshakeable Credibility</h3>
                    <p>A sleek, professional custom website instantly validates your reputation, setting you apart from unverified competitors.</p>
                </div>
            </div>

            <!-- Comparison Table Box -->
            <div class="comparison-box reveal">
                <div class="comp-column">
                    <h4 style="color: #A8695A;"><i class="fa-solid fa-circle-xmark"></i> Social Media Only</h4>
                    <ul class="comp-list">
                        <li><i class="fa-solid fa-xmark"></i> Constantly fighting algorithm changes</li>
                        <li><i class="fa-solid fa-xmark"></i> Zero ownership of customer data</li>
                        <li><i class="fa-solid fa-xmark"></i> Limited customization &amp; branding</li>
                        <li><i class="fa-solid fa-xmark"></i> Easy for clients to get distracted by competitors</li>
                    </ul>
                </div>
                <div class="comp-column">
                    <h4 style="color: var(--primary-light);"><i class="fa-solid fa-circle-check"></i> Custom Website + Socials</h4>
                    <ul class="comp-list">
                        <li><i class="fa-solid fa-check"></i> You own 100% of your platform and domain</li>
                        <li><i class="fa-solid fa-check"></i> Automated bookings, enquiries, and orders</li>
                        <li><i class="fa-solid fa-check"></i> Unrivaled luxury branding and professional trust</li>
                        <li><i class="fa-solid fa-check"></i> Direct integration with CRM, email &amp; analytics</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Industries We Build For Section -->
    <section class="section-padding" style="background: rgba(18, 16, 12, 0.3);">
        <div class="container">
            <div class="section-header text-center reveal">
                <div class="badge">Tailored Expertise</div>
                <h2 class="section-title">Industries We <span class="gradient-text">Transform</span></h2>
                <p class="section-subtitle">We design purpose-built digital solutions optimized for specific industry needs and user behavior.</p>
            </div>

            <div class="industries-grid">
                <div class="glass-card industry-card reveal"><i class="fa-solid fa-utensils"></i><h4>Restaurants &amp; Cafes</h4></div>
                <div class="glass-card industry-card reveal"><i class="fa-solid fa-building"></i><h4>Real Estate</h4></div>
                <div class="glass-card industry-card reveal"><i class="fa-solid fa-graduation-cap"></i><h4>Schools &amp; Academies</h4></div>
                <div class="glass-card industry-card reveal"><i class="fa-solid fa-shirt"></i><h4>Fashion Brands</h4></div>
                <div class="glass-card industry-card reveal"><i class="fa-solid fa-gem"></i><h4>Luxury Jewelry</h4></div>
                <div class="glass-card industry-card reveal"><i class="fa-solid fa-couch"></i><h4>Furniture Stores</h4></div>
                <div class="glass-card industry-card reveal"><i class="fa-solid fa-hotel"></i><h4>Hotels &amp; Resorts</h4></div>
                <div class="glass-card industry-card reveal"><i class="fa-solid fa-user-doctor"></i><h4>Medical Clinics</h4></div>
                <div class="glass-card industry-card reveal"><i class="fa-solid fa-helmet-safety"></i><h4>Construction</h4></div>
                <div class="glass-card industry-card reveal"><i class="fa-solid fa-solar-panel"></i><h4>Solar &amp; Energy</h4></div>
                <div class="glass-card industry-card reveal"><i class="fa-solid fa-shield-cat"></i><h4>Security Companies</h4></div>
                <div class="glass-card industry-card reveal"><i class="fa-solid fa-truck-fast"></i><h4>Logistics &amp; Freight</h4></div>
                <div class="glass-card industry-card reveal"><i class="fa-solid fa-broom"></i><h4>Cleaning Services</h4></div>
                <div class="glass-card industry-card reveal"><i class="fa-solid fa-spa"></i><h4>Beauty &amp; Salons</h4></div>
                <div class="glass-card industry-card reveal"><i class="fa-solid fa-scale-balanced"></i><h4>Law Firms</h4></div>
                <div class="glass-card industry-card reveal"><i class="fa-solid fa-rocket"></i><h4>Tech Startups</h4></div>
                <div class="glass-card industry-card reveal"><i class="fa-solid fa-church"></i><h4>Churches &amp; Ministry</h4></div>
                <div class="glass-card industry-card reveal"><i class="fa-solid fa-hand-holding-heart"></i><h4>NGOs &amp; Charities</h4></div>
                <div class="glass-card industry-card reveal"><i class="fa-solid fa-calendar-check"></i><h4>Event Planners</h4></div>
                <div class="glass-card industry-card reveal"><i class="fa-solid fa-car"></i><h4>Car Dealerships</h4></div>
            </div>
        </div>
    </section>

    <!-- Our Services Section -->
    <section class="section-padding" id="services">
        <div class="container">
            <div class="section-header text-center reveal">
                <div class="badge">Master Capabilities</div>
                <h2 class="section-title">Our Premium <span class="gradient-text">Services</span></h2>
                <p class="section-subtitle">From custom web architecture to full-funnel digital setup, we deliver end-to-end digital solutions.</p>
            </div>

            <div class="services-grid">
                <div class="glass-card service-card reveal">
                    <div>
                        <div class="service-header">
                            <div class="service-icon"><i class="fa-solid fa-laptop-code"></i></div>
                            <div class="service-number">I</div>
                        </div>
                        <h3>Corporate Websites</h3>
                        <p>High-end corporate platforms tailored to project authority, handle high enterprise traffic, and generate premium B2B leads.</p>
                    </div>
                    <a href="#contact" class="service-link">Inquire Service <i class="fa-solid fa-arrow-right"></i></a>
                </div>

                <div class="glass-card service-card reveal">
                    <div>
                        <div class="service-header">
                            <div class="service-icon"><i class="fa-solid fa-cart-shopping"></i></div>
                            <div class="service-number">II</div>
                        </div>
                        <h3>E-Commerce Stores</h3>
                        <p>Seamless shopping experiences with automated inventory management, secure global payment gateways, and high conversion checkouts.</p>
                    </div>
                    <a href="#contact" class="service-link">Inquire Service <i class="fa-solid fa-arrow-right"></i></a>
                </div>

                <div class="glass-card service-card reveal">
                    <div>
                        <div class="service-header">
                            <div class="service-icon"><i class="fa-solid fa-bullseye"></i></div>
                            <div class="service-number">III</div>
                        </div>
                        <h3>High-Converting Landing Pages</h3>
                        <p>Purpose-built marketing funnels designed specifically to maximize PPC campaigns, capture emails, and boost immediate sales.</p>
                    </div>
                    <a href="#contact" class="service-link">Inquire Service <i class="fa-solid fa-arrow-right"></i></a>
                </div>

                <div class="glass-card service-card reveal">
                    <div>
                        <div class="service-header">
                            <div class="service-icon"><i class="fa-solid fa-rotate"></i></div>
                            <div class="service-number">IV</div>
                        </div>
                        <h3>Website Redesign</h3>
                        <p>Transform your outdated, slow website into an ultra-modern, blazing-fast web powerhouse that converts modern users.</p>
                    </div>
                    <a href="#contact" class="service-link">Inquire Service <i class="fa-solid fa-arrow-right"></i></a>
                </div>

                <div class="glass-card service-card reveal">
                    <div>
                        <div class="service-header">
                            <div class="service-icon"><i class="fa-solid fa-chart-line"></i></div>
                            <div class="service-number">V</div>
                        </div>
                        <h3>SEO &amp; Business Profile</h3>
                        <p>Dominating local and organic search engine rankings to ensure your business appears first when clients search on Google.</p>
                    </div>
                    <a href="#contact" class="service-link">Inquire Service <i class="fa-solid fa-arrow-right"></i></a>
                </div>

                <div class="glass-card service-card reveal">
                    <div>
                        <div class="service-header">
                            <div class="service-icon"><i class="fa-solid fa-server"></i></div>
                            <div class="service-number">VI</div>
                        </div>
                        <h3>Hosting, Setup &amp; Support</h3>
                        <p>Complete hassle-free setup of cloud servers, custom domains, professional emails, and 24/7 technical maintenance.</p>
                    </div>
                    <a href="#contact" class="service-link">Inquire Service <i class="fa-solid fa-arrow-right"></i></a>
                </div>
            </div>
        </div>
    </section>

    <!-- Why Choose Aurex Web Studio -->
    <section class="section-padding" style="background: rgba(18, 16, 12, 0.4);">
        <div class="container">
            <div class="section-header text-center reveal">
                <div class="badge">The Aurex Standard</div>
                <h2 class="section-title">Built for Performance, <span class="gradient-text">Designed for Growth</span></h2>
                <p class="section-subtitle">Every project engineered by Aurex Web Studio incorporates modern design standards.</p>
            </div>

            <div class="why-choose-grid">
                <div class="glass-card feature-box reveal">
                    <div class="feature-icon-check"><i class="fa-solid fa-check"></i></div>
                    <div>
                        <h4>World-Class UI/UX Design</h4>
                        <p>Crafted to rival international creative agencies with seamless elegance.</p>
                    </div>
                </div>

                <div class="glass-card feature-box reveal">
                    <div class="feature-icon-check"><i class="fa-solid fa-check"></i></div>
                    <div>
                        <h4>Mobile-First Responsive</h4>
                        <p>Flawless rendering across every smartphone, tablet, laptop, and 4K display.</p>
                    </div>
                </div>

                <div class="glass-card feature-box reveal">
                    <div class="feature-icon-check"><i class="fa-solid fa-check"></i></div>
                    <div>
                        <h4>Blazing Speed Performance</h4>
                        <p>Optimized assets and clean architecture for instant load times under 1 second.</p>
                    </div>
                </div>

                <div class="glass-card feature-box reveal">
                    <div class="feature-icon-check"><i class="fa-solid fa-check"></i></div>
                    <div>
                        <h4>Instant WhatsApp Integration</h4>
                        <p>Direct chat triggers enabling visitors to message you instantly in one click.</p>
                    </div>
                </div>

                <div class="glass-card feature-box reveal">
                    <div class="feature-icon-check"><i class="fa-solid fa-check"></i></div>
                    <div>
                        <h4>SEO Optimized Codebase</h4>
                        <p>Built-in schema, meta tags, and structured data ready for search engines.</p>
                    </div>
                </div>

                <div class="glass-card feature-box reveal">
                    <div class="feature-icon-check"><i class="fa-solid fa-check"></i></div>
                    <div>
                        <h4>Affordable Luxury Packages</h4>
                        <p>Premium agency-quality websites delivered at competitive investment tiers.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Portfolio Showcase Section -->
    <section class="section-padding" id="portfolio">
        <div class="container">
            <div class="section-header text-center reveal">
                <div class="badge">Selected Works</div>
                <h2 class="section-title">Explore Our <span class="gradient-text">Recent Projects</span></h2>
                <p class="section-subtitle">Experience live concepts of high-end design engineered for real-world industries.</p>
            </div>

            <div class="portfolio-grid">
                <div class="glass-card portfolio-card reveal">
                    <div class="portfolio-thumb">
                        <div class="thumb-bg">
                            <div style="font-size:0.7rem; color:var(--primary-light);"><i class="fa-solid fa-utensils"></i> Cuisine Deluxe</div>
                            <div style="font-size:1.1rem; font-weight:700; margin:10px 0; font-family: var(--font-heading);">Luxury Dining Experience</div>
                            <div style="display:flex; gap:5px; margin-top:20px;">
                                <div style="padding:4px 8px; background:var(--primary); color:var(--ink); border-radius:2px; font-size:0.6rem;">Table Booking</div>
                                <div style="padding:4px 8px; background:rgba(201,169,97,0.1); border-radius:2px; font-size:0.6rem;">Digital Menu</div>
                            </div>
                        </div>
                    </div>
                    <div class="portfolio-info">
                        <span class="portfolio-tag">Restaurant &amp; Hospitality</span>
                        <h3>Gourmet Dining Experience</h3>
                        <p style="color:var(--text-muted); font-size:0.9rem; margin-bottom:1rem; font-weight: 300;">Integrated digital menus, automated reservations, and elegant aesthetic visual layouts.</p>
                        <a href="#contact" class="service-link">View Concept Details <i class="fa-solid fa-arrow-right"></i></a>
                    </div>
                </div>

                <div class="glass-card portfolio-card reveal">
                    <div class="portfolio-thumb">
                        <div class="thumb-bg">
                            <div style="font-size:0.7rem; color:var(--primary-light);"><i class="fa-solid fa-building"></i> Apex Properties</div>
                            <div style="font-size:1.1rem; font-weight:700; margin:10px 0; font-family: var(--font-heading);">Modern Real Estate Portal</div>
                            <div style="display:flex; gap:5px; margin-top:20px;">
                                <div style="padding:4px 8px; background:var(--primary); color:var(--ink); border-radius:2px; font-size:0.6rem;">Virtual Tours</div>
                                <div style="padding:4px 8px; background:rgba(201,169,97,0.1); border-radius:2px; font-size:0.6rem;">Property Search</div>
                            </div>
                        </div>
                    </div>
                    <div class="portfolio-info">
                        <span class="portfolio-tag">Real Estate &amp; Architecture</span>
                        <h3>Apex Estate Management</h3>
                        <p style="color:var(--text-muted); font-size:0.9rem; margin-bottom:1rem; font-weight: 300;">Dynamic property filtering, virtual gallery showcases, and direct agent inquiry channels.</p>
                        <a href="#contact" class="service-link">View Concept Details <i class="fa-solid fa-arrow-right"></i></a>
                    </div>
                </div>

                <div class="glass-card portfolio-card reveal">
                    <div class="portfolio-thumb">
                        <div class="thumb-bg">
                            <div style="font-size:0.7rem; color:var(--primary-light);"><i class="fa-solid fa-gem"></i> Aurelia Jewels</div>
                            <div style="font-size:1.1rem; font-weight:700; margin:10px 0; font-family: var(--font-heading);">E-Commerce Fashion Store</div>
                            <div style="display:flex; gap:5px; margin-top:20px;">
                                <div style="padding:4px 8px; background:var(--primary); color:var(--ink); border-radius:2px; font-size:0.6rem;">Checkout Integration</div>
                                <div style="padding:4px 8px; background:rgba(201,169,97,0.1); border-radius:2px; font-size:0.6rem;">Currency Switcher</div>
                            </div>
                        </div>
                    </div>
                    <div class="portfolio-info">
                        <span class="portfolio-tag">E-Commerce Luxury</span>
                        <h3>Aurelia Fine Jewelry</h3>
                        <p style="color:var(--text-muted); font-size:0.9rem; margin-bottom:1rem; font-weight: 300;">High-end product visuals, multi-currency support, and seamless payment checkout setup.</p>
                        <a href="#contact" class="service-link">View Concept Details <i class="fa-solid fa-arrow-right"></i></a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Development Process Section -->
    <section class="section-padding" id="process" style="background: rgba(18, 16, 12, 0.3);">
        <div class="container">
            <div class="section-header text-center reveal">
                <div class="badge">Seamless Execution</div>
                <h2 class="section-title">Our Step-by-Step <span class="gradient-text">Process</span></h2>
                <p class="section-subtitle">A structured, transparent workflow designed to take your idea from concept to successful launch effortlessly.</p>
            </div>

            <div class="process-timeline">
                <div class="glass-card process-step reveal">
                    <div class="step-number">I</div>
                    <h4>Discovery &amp; Strategy</h4>
                    <p>We discuss your goals, audience, and project scope.</p>
                </div>

                <div class="glass-card process-step reveal">
                    <div class="step-number">II</div>
                    <h4>UI/UX Wireframing</h4>
                    <p>Designing modern, user-friendly interactive layouts.</p>
                </div>

                <div class="glass-card process-step reveal">
                    <div class="step-number">III</div>
                    <h4>Development</h4>
                    <p>Building clean, fast, and secure custom code.</p>
                </div>

                <div class="glass-card process-step reveal">
                    <div class="step-number">IV</div>
                    <h4>Testing &amp; Quality</h4>
                    <p>Rigorous mobile, speed, and security audits.</p>
                </div>

                <div class="glass-card process-step reveal">
                    <div class="step-number">V</div>
                    <h4>Official Launch</h4>
                    <p>Deploying your website live on global cloud servers.</p>
                </div>

                <div class="glass-card process-step reveal">
                    <div class="step-number">VI</div>
                    <h4>Ongoing Support</h4>
                    <p>Continuous maintenance and optimization updates.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section class="section-padding">
        <div class="container">
            <div class="section-header text-center reveal">
                <div class="badge">Client Trust</div>
                <h2 class="section-title">What Our <span class="gradient-text">Clients Say</span></h2>
                <p class="section-subtitle">Real experiences from business owners who elevated their digital brand with Aurex Web Studio.</p>
            </div>

            <div class="testimonials-grid">
                <div class="glass-card testimonial-card reveal">
                    <div>
                        <div class="stars">
                            <i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i>
                        </div>
                        <p class="testimonial-text">"Aurex Web Studio rebuilt our company website from scratch. Our client inquiries increased by over 180% in the first two months alone. Their attention to design detail is unmatched."</p>
                    </div>
                    <div class="client-profile">
                        <div class="client-avatar">DA</div>
                        <div class="client-info">
                            <h4>David Adebayo</h4>
                            <span>Founder, Apex Real Estate</span>
                        </div>
                    </div>
                </div>

                <div class="glass-card testimonial-card reveal">
                    <div>
                        <div class="stars">
                            <i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i>
                        </div>
                        <p class="testimonial-text">"The speed, mobile responsiveness, and luxury feel of our online store transformed our fashion brand's reputation completely. Truly a world-class web agency experience!"</p>
                    </div>
                    <div class="client-profile">
                        <div class="client-avatar">SO</div>
                        <div class="client-info">
                            <h4>Sarah Okonjo</h4>
                            <span>Creative Director, Aurelia Fashion</span>
                        </div>
                    </div>
                </div>

                <div class="glass-card testimonial-card reveal">
                    <div>
                        <div class="stars">
                            <i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i>
                        </div>
                        <p class="testimonial-text">"Fast communication, transparent process, and top-tier execution. Having direct WhatsApp communication throughout the build made the entire process so easy."</p>
                    </div>
                    <div class="client-profile">
                        <div class="client-avatar">MK</div>
                        <div class="client-info">
                            <h4>Michael K.</h4>
                            <span>CEO, Kinetic Energy Solutions</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Frequently Asked Questions (FAQ) Section -->
    <section class="section-padding" id="faq" style="background: rgba(18, 16, 12, 0.3);">
        <div class="container">
            <div class="section-header text-center reveal">
                <div class="badge">Clarity First</div>
                <h2 class="section-title">Frequently Asked <span class="gradient-text">Questions</span></h2>
                <p class="section-subtitle">Everything you need to know about starting your website project with us.</p>
            </div>

            <div class="faq-container reveal">
                <div class="glass-card faq-item">
                    <button class="faq-question">
                        <span>Do I need a website if I already use Instagram or TikTok?</span>
                        <div class="faq-icon"><i class="fa-solid fa-chevron-down"></i></div>
                    </button>
                    <div class="faq-answer">
                        <p>Yes, absolutely! While social media is great for initial engagement, a custom website provides full ownership, zero algorithm restrictions, professional credibility, and automated ordering capabilities that social media platforms cannot match.</p>
                    </div>
                </div>

                <div class="glass-card faq-item">
                    <button class="faq-question">
                        <span>Can customers directly place orders or book appointments?</span>
                        <div class="faq-icon"><i class="fa-solid fa-chevron-down"></i></div>
                    </button>
                    <div class="faq-answer">
                        <p>Yes! We integrate automated booking engines, online payment processors, and direct WhatsApp order channels so your customers can complete transactions seamlessly 24/7.</p>
                    </div>
                </div>

                <div class="glass-card faq-item">
                    <button class="faq-question">
                        <span>Will my website work perfectly on smartphones and tablets?</span>
                        <div class="faq-icon"><i class="fa-solid fa-chevron-down"></i></div>
                    </button>
                    <div class="faq-answer">
                        <p>100%. We employ a strict mobile-first design strategy. Your website will adapt fluidly to every single screen size, ensuring maximum conversion on smartphones.</p>
                    </div>
                </div>

                <div class="glass-card faq-item">
                    <button class="faq-question">
                        <span>How long does it take to complete and launch my website?</span>
                        <div class="faq-icon"><i class="fa-solid fa-chevron-down"></i></div>
                    </button>
                    <div class="faq-answer">
                        <p>Standard corporate and business websites are typically delivered within 7 to 14 days. Custom enterprise or e-commerce platforms take between 2 to 3 weeks depending on complex features.</p>
                    </div>
                </div>

                <div class="glass-card faq-item">
                    <button class="faq-question">
                        <span>Can you redesign my existing outdated website?</span>
                        <div class="faq-icon"><i class="fa-solid fa-chevron-down"></i></div>
                    </button>
                    <div class="faq-answer">
                        <p>Yes! We specialize in transforming slow, outdated sites into modern, high-converting digital assets while preserving your content and domain authority.</p>
                    </div>
                </div>

                <div class="glass-card faq-item">
                    <button class="faq-question">
                        <span>Do you handle domain registration and hosting setup?</span>
                        <div class="faq-icon"><i class="fa-solid fa-chevron-down"></i></div>
                    </button>
                    <div class="faq-answer">
                        <p>Yes, we handle everything from domain purchasing, SSL certificates, cloud server hosting deployment, and corporate custom email setup.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact & Consultation Section -->
    <section class="section-padding" id="contact">
        <div class="container">
            <div class="section-header text-center reveal">
                <div class="badge">Get In Touch</div>
                <h2 class="section-title">Let's Build Something <span class="gradient-text">Extraordinary</span></h2>
                <p class="section-subtitle">Ready to elevate your business online? Contact us today for a free consultation and customized quote.</p>
            </div>

            <div class="contact-grid">
                <!-- Contact Info Card -->
                <div class="glass-card contact-info-card reveal">
                    <div>
                        <h3 style="font-size: 1.75rem; margin-bottom: 2rem;">Aurex Web Studio</h3>

                        <div class="contact-detail-item">
                            <div class="contact-detail-icon"><i class="fa-solid fa-envelope"></i></div>
                            <div class="contact-detail-text">
                                <h4>Email Us Directly</h4>
                                <a href="mailto:ibrahimaminu09168@gmail.com">ibrahimaminu09168@gmail.com</a>
                            </div>
                        </div>

                        <div class="contact-detail-item">
                            <div class="contact-detail-icon"><i class="fa-solid fa-phone"></i></div>
                            <div class="contact-detail-text">
                                <h4>Call / Direct Line</h4>
                                <a href="tel:09168059744">+234 916 805 9744</a>
                            </div>
                        </div>

                        <div class="contact-detail-item">
                            <div class="contact-detail-icon"><i class="fa-brands fa-whatsapp"></i></div>
                            <div class="contact-detail-text">
                                <h4>Instant WhatsApp</h4>
                                <a href="https://wa.me/2349168059744" target="_blank">Message developer on WhatsApp</a>
                            </div>
                        </div>

                        <div class="contact-detail-item">
                            <div class="contact-detail-icon"><i class="fa-solid fa-location-dot"></i></div>
                            <div class="contact-detail-text">
                                <h4>Office Location</h4>
                                <p>Nigeria (Serving Clients Worldwide)</p>
                            </div>
                        </div>
                    </div>

                    <div>
                        <h4 style="font-size: 0.85rem; text-transform: uppercase; letter-spacing: 0.1em; color: var(--text-muted); margin-bottom: 1rem; font-weight: 500;">Connect With Us</h4>
                        <div class="social-links">
                            <a href="#" class="social-icon" aria-label="Instagram"><i class="fa-brands fa-instagram"></i></a>
                            <a href="#" class="social-icon" aria-label="Facebook"><i class="fa-brands fa-facebook-f"></i></a>
                            <a href="#" class="social-icon" aria-label="LinkedIn"><i class="fa-brands fa-linkedin-in"></i></a>
                            <a href="#" class="social-icon" aria-label="TikTok"><i class="fa-brands fa-tiktok"></i></a>
                            <a href="#" class="social-icon" aria-label="GitHub"><i class="fa-brands fa-github"></i></a>
                        </div>
                    </div>
                </div>

                <!-- Interactive Contact Form -->
                <div class="glass-card contact-form reveal">
                    <form id="project-form" onsubmit="handleFormSubmit(event)">
                        <div class="form-group">
                            <label class="form-label" for="full-name">Your Full Name</label>
                            <input type="text" id="full-name" class="form-control" placeholder="e.g. John Doe" required>
                        </div>

                        <div class="form-group">
                            <label class="form-label" for="email-address">Email Address</label>
                            <input type="email" id="email-address" class="form-control" placeholder="e.g. john@company.com" required>
                        </div>

                        <div class="form-group">
                            <label class="form-label" for="phone-number">Phone Number / WhatsApp</label>
                            <input type="tel" id="phone-number" class="form-control" placeholder="e.g. +234 916 805 9744" required>
                        </div>

                        <div class="form-group">
                            <label class="form-label" for="project-type">Project Type</label>
                            <select id="project-type" class="form-control" style="background: #12100C;" required>
                                <option value="" disabled selected>Select industry/website type...</option>
                                <option value="Business/Corporate Website">Business/Corporate Website</option>
                                <option value="E-Commerce Store">E-Commerce Online Store</option>
                                <option value="Landing Page">High-Converting Landing Page</option>
                                <option value="Website Redesign">Website Redesign</option>
                                <option value="Other">Other Custom Service</option>
                            </select>
                        </div>

                        <div class="form-group">
                            <label class="form-label" for="message">Project Details</label>
                            <textarea id="message" class="form-control" placeholder="Tell us about your business goals and requirements..." required></textarea>
                        </div>

                        <button type="submit" class="btn btn-primary" style="width: 100%;">
                            <span>Send Inquiry Message</span>
                            <i class="fa-solid fa-paper-plane"></i>
                        </button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer Section -->
    <footer class="footer">
        <div class="container">
            <div class="footer-grid">
                <div class="footer-brand">
                    <a href="#" class="logo">
                        <div class="logo-icon">A</div>
                        <span>AUREX <span class="gradient-accent" style="font-style: italic;">Studio</span></span>
                    </a>
                    <p>A bespoke web agency crafting premium, refined, and high-converting websites for businesses ready to lead online.</p>
                </div>

                <div>
                    <h4 class="footer-title">Quick Links</h4>
                    <ul class="footer-links">
                        <li><a href="#home">Home</a></li>
                        <li><a href="#why-us">Why Choose Us</a></li>
                        <li><a href="#portfolio">Our Portfolio</a></li>
                        <li><a href="#process">Development Process</a></li>
                        <li><a href="#faq">FAQ</a></li>
                    </ul>
                </div>

                <div>
                    <h4 class="footer-title">Services</h4>
                    <ul class="footer-links">
                        <li><a href="#services">Corporate Websites</a></li>
                        <li><a href="#services">E-Commerce Stores</a></li>
                        <li><a href="#services">Landing Pages</a></li>
                        <li><a href="#services">SEO Optimization</a></li>
                        <li><a href="#services">Hosting &amp; Domain</a></li>
                    </ul>
                </div>

                <div>
                    <h4 class="footer-title">Direct Contact</h4>
                    <ul class="footer-links">
                        <li><a href="mailto:ibrahimaminu09168@gmail.com">ibrahimaminu09168@gmail.com</a></li>
                        <li><a href="tel:09168059744">+234 916 805 9744</a></li>
                        <li><a href="https://wa.me/2349168059744" target="_blank">WhatsApp Chat</a></li>
                        <li><span style="color:var(--text-muted); font-size:0.9rem;">Nigeria</span></li>
                    </ul>
                </div>
            </div>

            <div class="footer-bottom">
                <div>&copy; <span id="year-span"></span> Aurex Web Studio. All rights reserved.</div>
                <div class="footer-legal">
                    <a href="#">Privacy Policy</a>
                    <a href="#">Terms of Service</a>
                </div>
            </div>
        </div>
    </footer>

    <!-- Native JavaScript Engine -->
    <script>
        /* ==========================================================================
           1. CANVAS PARTICLE ANIMATION ENGINE — gold dust motes
           ========================================================================== */
        const canvas = document.getElementById('particle-canvas');
        const ctx = canvas.getContext('2d');
        let particles = [];

        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        window.addEventListener('resize', resizeCanvas);
        resizeCanvas();

        class Particle {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 2 + 0.5;
                this.speedX = (Math.random() - 0.5) * 0.4;
                this.speedY = (Math.random() - 0.5) * 0.4;
                this.opacity = Math.random() * 0.5 + 0.1;
            }
            update() {
                this.x += this.speedX;
                this.y += this.speedY;

                if (this.x > canvas.width) this.x = 0;
                if (this.x < 0) this.x = canvas.width;
                if (this.y > canvas.height) this.y = 0;
                if (this.y < 0) this.y = canvas.height;
            }
            draw() {
                ctx.fillStyle = `rgba(201, 169, 97, ${this.opacity})`;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
            }
        }

        function initParticles() {
            particles = [];
            const count = Math.floor((canvas.width * canvas.height) / 18000);
            for (let i = 0; i < count; i++) {
                particles.push(new Particle());
            }
        }

        function animateParticles() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            particles.forEach(p => {
                p.update();
                p.draw();
            });
            requestAnimationFrame(animateParticles);
        }

        initParticles();
        animateParticles();

        /* ==========================================================================
           2. NAVIGATION & SCROLL ENGINE
           ========================================================================== */
        const header = document.getElementById('header');
        const menuBtn = document.getElementById('menu-btn');
        const navLinks = document.getElementById('nav-links');

        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });

        menuBtn.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            const icon = menuBtn.querySelector('i');
            if (navLinks.classList.contains('active')) {
                icon.className = 'fa-solid fa-xmark';
            } else {
                icon.className = 'fa-solid fa-bars-staggered';
            }
        });

        // Close Mobile Nav on Link Click
        document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
                menuBtn.querySelector('i').className = 'fa-solid fa-bars-staggered';
            });
        });

        /* ==========================================================================
           3. SCROLL REVEAL ANIMATIONS
           ========================================================================== */
        const revealElements = document.querySelectorAll('.reveal');

        function revealOnScroll() {
            const windowHeight = window.innerHeight;
            revealElements.forEach(el => {
                const elementTop = el.getBoundingClientRect().top;
                const revealPoint = 120;
                if (elementTop < windowHeight - revealPoint) {
                    el.classList.add('active');
                }
            });
        }

        window.addEventListener('scroll', revealOnScroll);
        revealOnScroll(); // Trigger initial load

        /* ==========================================================================
           4. FAQ ACCORDION SYSTEM
           ========================================================================== */
        const faqItems = document.querySelectorAll('.faq-item');

        faqItems.forEach(item => {
            const questionBtn = item.querySelector('.faq-question');
            questionBtn.addEventListener('click', () => {
                const isActive = item.classList.contains('active');

                // Close all other FAQs
                faqItems.forEach(otherItem => otherItem.classList.remove('active'));

                // Toggle current FAQ
                if (!isActive) {
                    item.classList.add('active');
                }
            });
        });

        /* ==========================================================================
           5. FORM HANDLING & DYNAMIC FOOTER YEAR
           ========================================================================== */
        document.getElementById('year-span').textContent = new Date().getFullYear();

        function handleFormSubmit(e) {
            e.preventDefault();
            const name = document.getElementById('full-name').value;
            const phone = document.getElementById('phone-number').value;
            const project = document.getElementById('project-type').value;
            const message = document.getElementById('message').value;

            // Direct WhatsApp redirect formulation
            const whatsappText = `Hello Aurex Web Studio!%0A%0A*Name:* ${encodeURIComponent(name)}%0A*Phone:* ${encodeURIComponent(phone)}%0A*Project Type:* ${encodeURIComponent(project)}%0A*Details:* ${encodeURIComponent(message)}`;

            window.open(`https://wa.me/2349168059744?text=${whatsappText}`, '_blank');
        }
    </script>
</body>
</html>
