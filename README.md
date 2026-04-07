# lipeiyi294.github.io
<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>台灣禮品店 | 台灣原創・客製想像</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        :root {
            --primary-color: #e67e22; /* 文創橘 */
            --bg-dark: #121212;
            --text-light: #f4f4f4;
            --accent-gold: #d4af37;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Noto Sans TC', sans-serif;
        }

        body {
            background-color: var(--bg-dark);
            color: var(--text-light);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* 背景流光效果 */
        body::before {
            content: "";
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 50% 50%, #1a1a1a 0%, #000 100%);
            z-index: -1;
        }

        /* 導航欄 */
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 2rem 5%;
            position: absolute;
            width: 100%;
            z-index: 100;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 900;
            letter-spacing: 2px;
            color: var(--primary-color);
        }

        /* ===== 導航列按鈕化 ===== */
        .nav-links a {
            display: inline-block;
            color: var(--text-light);
            text-decoration: none;
            margin-left: 1rem;
            font-size: 1.15rem;
            font-weight: 500;
            transition: all 0.3s ease;
           
            /* 按鈕外觀 */
            padding: 10px 25px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 30px;
            background-color: rgba(255, 255, 255, 0.05);
            letter-spacing: 1px;
        }

        .nav-links a:hover {
            background-color: var(--primary-color);
            color: #fff;
            border-color: var(--primary-color);
            box-shadow: 0 4px 15px rgba(230, 126, 34, 0.4);
            transform: translateY(-2px);
        }

        /* Hero 區塊 */
        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 10%;
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #fff, var(--primary-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: 800;
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 600px;
            margin-bottom: 2rem;
            color: #888;
        }

        .cta-button {
            padding: 1rem 2.5rem;
            background: transparent;
            border: 1px solid var(--primary-color);
            color: var(--primary-color);
            text-decoration: none;
            font-weight: bold;
            transition: 0.4s;
            position: relative;
            overflow: hidden;
            border-radius: 5px;
            font-size: 1.1rem;
        }

        .cta-button:hover {
            background: var(--primary-color);
            color: #000;
        }

        /* Instagram 純文字提示 */
        .ig-hint {
            display: inline-block;
            margin-top: 15px;
            color: #888;
            font-size: 0.9rem;
            letter-spacing: 1px;
        }

        .ig-hint i {
            display: inline-block;
            margin-right: 5px;
            color: var(--primary-color);
            animation: bounceUp 1.5s infinite;
        }

        @keyframes bounceUp {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-5px); }
        }

        /* 內容區塊 */
        .section-title {
            text-align: center;
            padding: 5rem 0 2rem;
        }

        .section-title h2 {
            font-size: 2.5rem;
            letter-spacing: 5px;
        }

        .grid-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            padding: 2rem 10%;
        }

        .card {
            background: #1e1e1e;
            padding: 2rem;
            border-radius: 5px;
            transition: 0.5s;
            cursor: pointer;
            border: 1px solid #333;
        }

        .card:hover {
            transform: translateY(-10px);
            border-color: var(--accent-gold);
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }

        .card i {
            font-size: 2.5rem;
            color: var(--accent-gold);
            margin-bottom: 1.5rem;
        }

        .card h3 {
            margin-bottom: 1rem;
            font-size: 1.5rem;
        }

        /* 店家連結區 */
        .social-section {
            text-align: center;
            padding: 5rem 10%;
            background: #0a0a0a;
        }

        .fb-link {
            display: inline-block;
            margin-top: 2rem;
            color: #4267B2;
            font-size: 1.2rem;
            text-decoration: none;
        }

        footer {
            text-align: center;
            padding: 3rem;
            font-size: 0.8rem;
            color: #555;
            border-top: 1px solid #222;
        }

        /* 動畫 */
        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .animate {
            animation: fadeInUp 1s ease forwards;
        }

        /* ================= 浮窗 (Modal) 樣式 ================= */
        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.85);
            backdrop-filter: blur(5px);
            overflow: auto;
        }

        .modal-content {
            background-color: #1e1e1e;
            margin: 5% auto;
            padding: 2rem;
            border: 1px solid var(--accent-gold);
            border-radius: 8px;
            width: 85%;
            max-width: 1000px;
            position: relative;
            animation: modalFadeIn 0.4s ease-out;
            max-height: 85vh;
            overflow-y: auto;
        }

        @keyframes modalFadeIn {
            from { opacity: 0; transform: translateY(-30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .close-btn {
            color: #aaa;
            position: absolute;
            top: 15px;
            right: 25px;
            font-size: 2rem;
            font-weight: bold;
            cursor: pointer;
            transition: 0.3s;
            z-index: 10;
        }

        .close-btn:hover,
        .close-btn:focus {
            color: var(--primary-color);
            text-decoration: none;
        }

        .modal-title {
            text-align: center;
            margin-bottom: 1rem;
            color: var(--accent-gold);
            letter-spacing: 2px;
            font-size: 2rem;
        }

        .modal-subtitle {
            text-align: center;
            color: #888;
            margin-bottom: 2rem;
            font-size: 0.9rem;
        }

        /* ================= 輪播通用樣式 ================= */
        .slider-container {
            position: relative;
            width: 100%;
            height: 55vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            border-radius: 5px;
            background-color: #000;
            touch-action: pan-y;
        }

        .slide {
            display: none;
            width: 100%;
            height: 100%;
            text-align: center;
            animation: fadeIn 0.4s ease-in-out;
        }

        .slide.active {
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .slide a {
            display: block;
            width: 100%;
            height: 100%;
        }

        .slide img {
            width: 100%;
            height: 100%;
            object-fit: contain;
            transition: transform 0.3s;
            user-select: none;
            -webkit-user-drag: none;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* 頁面指示器 */
        .indicator {
            text-align: center;
            margin-top: 15px;
            color: #aaa;
            font-size: 0.9rem;
            letter-spacing: 1px;
        }

        /* ===== 手機版樣式整合 ===== */
        @media (max-width: 768px) {
            .hero h1 { font-size: 2.5rem; }
           
            nav {
                flex-direction: column;
                padding: 1rem 5%;
            }
            .nav-links {
                display: flex;
                margin-top: 15px;
                flex-wrap: wrap;
                justify-content: center;
                gap: 8px; /* 手機版按鈕間距稍微縮小 */
            }
           
            /* 手機版的導航按鈕微調：整體縮小 */
            .nav-links a {
                margin: 0;
                font-size: 0.85rem; /* 字體縮小 */
                padding: 6px 14px; /* 按鈕範圍縮小 */
            }

            /* 【本次新增修改】讓「為什麼我們與眾不同」縮小變成一行 */
            .section-title h2 {
                font-size: 1.5rem; /* 把字體改小 */
                letter-spacing: 2px; /* 把字距縮小，避免擠到第二行 */
            }

            .modal-content {
                width: 95%;
                margin: 10% auto;
                padding: 1.5rem;
            }
           
            .slider-container {
                height: 45vh;
            }
        }
    </style>
</head>
<body>

    <nav>
        <div class="logo">TAIWAN GIFT</div>
        <div class="nav-links">
            <a href="#" id="gallery-btn">作品欣賞</a>
            <a href="#" id="news-btn">新聞報導</a>
            <a href="https://www.facebook.com/p/%E5%8F%B0%E7%81%A3%E7%A6%AE%E5%93%81%E5%BA%97-100057180141686/" target="_blank">進入店鋪</a>
        </div>
    </nav>

    <section class="hero">
        <h1 class="animate">台灣禮品店，<br>定義你的專屬客製化。</h1>
        <p class="animate" style="animation-delay: 0.2s;">這裡不賣標準化商品。每一件禮物都是獨一無二，每一份驚喜都為你量身打造。</p>
        <a href="https://www.instagram.com/teresa540725?igsh=MWN0eXZrenNmamwzdQ%3D%3D" class="cta-button animate" style="animation-delay: 0.4s;" target="_blank">探索獨一無二</a>
       
        <div class="ig-hint animate" style="animation-delay: 0.6s;">
            <i class="fas fa-arrow-up"></i> 點擊上方按鈕進入 Instagram
        </div>
    </section>

    <section class="section-title">
        <h2>為什麼我們與眾不同</h2>
    </section>

    <div class="grid-container">
        <div class="card">
            <i class="fas fa-tools"></i>
            <h3>深度客製化</h3>
            <p>不只剪字。從設計到完美客製化作品，我們與你一起完成那份「只有你擁有」的專屬感。</p>
        </div>
        <div class="card">
            <i class="fas fa-fingerprint"></i>
            <h3>限量原創</h3>
            <p>純手工設計，在快速消費的時代，給你值得珍藏的溫度。</p>
        </div>
        <div class="card">
            <i class="fas fa-bolt"></i>
            <h3>店家資訊</h3>
            <a href="https://www.google.com/maps/place/%E5%8F%B0%E7%81%A3%E7%A6%AE%E5%93%81%E5%BA%97/@23.4806029,120.4483665,17z/data=!3m1!4b1!4m6!3m5!1s0x346e9433da5f271b:0x62ec26894ab7027!8m2!3d23.4806029!4d120.4509414!16s%2Fg%2F11c603_mn6?entry=ttu&g_ep=EgoyMDI2MDMxMS4wIKXMDSoASAFQAw%3D%3D" target="_blank" style="text-decoration: none;"><p style="color: #FF7575;">嘉義市東區中山路238號(點擊連結)</p></a>
            <p>電話:05-2230450</p>
        </div>
    </div>

    <section class="social-section">
        <h2>CONNECT WITH US</h2>
        <p>追蹤我們的最新創作與限時客製活動</p>
        <a href="https://www.facebook.com/p/%E5%8F%B0%E7%81%A3%E7%A6%AE%E5%93%81%E5%BA%97-100057180141686/" class="fb-link" target="_blank">
            <i class="fab fa-facebook-square"></i> 台灣禮品店 Facebook 官方頁面
        </a>
    </section>

    <footer>
        © 2024 台灣禮品店 - TAIWAN GIFT SHOP. All Rights Reserved.
    </footer>

    <div id="gallery-modal" class="modal">
        <div class="modal-content">
            <span class="close-btn" id="close-gallery">×</span>
            <h2 class="modal-title">作品欣賞</h2>
           
            <div class="slider-container" id="gallery-slider-container">
                <div class="slide gallery-slide active"><img src="https://scontent.xx.fbcdn.net/v/t1.15752-9/649832396_975522532318093_4205350960463010488_n.jpg?stp=dst-jpg_s960x960_tt6&_nc_cat=109&ccb=1-7&_nc_sid=9f807c&_nc_ohc=-cAyQ1YC3l8Q7kNvwGw8K8b&_nc_oc=AdnF6ZtOd4EofD-9Yct75AocPLw92wor7jiosnOOL3BB2j-vCQqYxiFxoFr7nyZBiQkgg1uIrLzZ2rNt9NOO6zKN&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent.xx&_nc_ss=8&oh=03_Q7cD4wEZW5FYJs4GNNDP0ZFWuxy4Z2-rTX5XnOfNRhK58J4vLg&oe=69E08172" alt="客製化禮物 1"></div>
                <div class="slide gallery-slide"><img src="https://scontent.xx.fbcdn.net/v/t1.15752-9/652743350_1138716275008866_1650943994966722067_n.jpg?stp=dst-jpg_s960x960_tt6&_nc_cat=102&ccb=1-7&_nc_sid=9f807c&_nc_ohc=Rv21nHXPuycQ7kNvwEKac9l&_nc_oc=Adk3g5y9Rt-9QrrL4T2B90WTRdOvn4qrLav2Kb8QctsfrjOMYF1wLFK_yYKhRQ0IPFoxZlQ22DHRpbps847y0CSd&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent.xx&_nc_ss=8&oh=03_Q7cD4wEmuv7ozcXSqUMJEaJK3XzhHRktkdLXT6RMXhT0hXfd1g&oe=69E09062" alt="客製化禮物 2"></div>
                <div class="slide gallery-slide"><img src="https://scontent.xx.fbcdn.net/v/t1.15752-9/649111692_962380183022549_1290624285086094666_n.jpg?stp=dst-jpg_s960x960_tt6&_nc_cat=107&ccb=1-7&_nc_sid=9f807c&_nc_ohc=jLPK22zOvfsQ7kNvwHt1PVG&_nc_oc=Adl6V0BR54BUbpCzRAghhY0SYRLYhRsTPxABhbusR64H184xyYLjFe24K2TgrdgY5p_SvdbeymNaKUaL3FvW7452&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent.xx&_nc_ss=8&oh=03_Q7cD4wHwqP3RXAHvuBiqyiOMhNGsl_ZZ7HZg6SfJKPEZW72O8g&oe=69E08E5D" alt="客製化禮物 3"></div>
                <div class="slide gallery-slide"><img src="https://scontent.xx.fbcdn.net/v/t1.15752-9/651620713_25370307922642747_8565691643161878292_n.jpg?stp=dst-jpg_s960x960_tt6&_nc_cat=100&ccb=1-7&_nc_sid=9f807c&_nc_ohc=URuIKmI50aIQ7kNvwF2t-op&_nc_oc=Adleu4eZiBcuwpsyOTjeaFrTi84CHqbu-ZKibgwqnbQhsQd9LtKVGSowJT8EE6k1oAyAB_hlHy4T9oqSlZSuRlZ_&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent.xx&_nc_ss=8&oh=03_Q7cD4wG8GmWfYQKzx4gPlHw7cKc71EVsiT5IRoeMRgJkwsVCdQ&oe=69E0AAAB" alt="客製化禮物 4"></div>
                <div class="slide gallery-slide"><img src="https://scontent.xx.fbcdn.net/v/t1.15752-9/649210638_1828348501163200_2904765624731009921_n.jpg?stp=dst-jpg_s960x960_tt6&_nc_cat=105&ccb=1-7&_nc_sid=9f807c&_nc_ohc=BaLVDHwInCIQ7kNvwFb06Zp&_nc_oc=AdksqLcAhbd44RpqwolFy0dWp2YDp4_wWXRlB3dtIZ19vEsna_ztBuqLrE5BJ5Dawdl7ao1LDCkO8ZyA6Lblkppv&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent.xx&_nc_ss=8&oh=03_Q7cD4wGfgVeSNUGLeLqWYrTjNZ5BchJUI8Ki35OrNhH8rlW5VA&oe=69E095A7" alt="客製化禮物 5"></div>
                <div class="slide gallery-slide"><img src="https://scontent.xx.fbcdn.net/v/t1.15752-9/650814897_1625165395483306_4983592407194633542_n.jpg?stp=dst-jpg_s960x960_tt6&_nc_cat=103&ccb=1-7&_nc_sid=9f807c&_nc_ohc=5bJ2Eq5ZcyMQ7kNvwEDBZyV&_nc_oc=Adludqdyv2o7R97XhUWT5Wzkpd8aXcsm_zy1UOzatbUG-qD7xaRkKCo5pmfdu3nSi7TM-tzevQgP-JKMzB0IOUW0&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent.xx&_nc_ss=8&oh=03_Q7cD4wEB2AdxSfPcsWW0lR0PrWWoaKbt_oqKdkDKylFgJKNmeA&oe=69E08EC7" alt="客製化禮物 6"></div>
                <div class="slide gallery-slide"><img src="https://scontent.xx.fbcdn.net/v/t1.15752-9/650065180_4519149631650645_7072774842484191189_n.jpg?stp=dst-jpg_s960x960_tt6&_nc_cat=105&ccb=1-7&_nc_sid=9f807c&_nc_ohc=70CMLI09jw4Q7kNvwEo-xSP&_nc_oc=AdnVp2I082JXopdjuKl2ZjQrFjdVcdDxpImdV0t1NL-xWPrN8TIk49WoxJndbTPJ6r3DlXeierwU_ytiETNr2Sll&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent.xx&_nc_ss=8&oh=03_Q7cD4wHWXIhTEzO6ml_rbfLTgl0ha95z_0v5e5uIZbDLzVP0qg&oe=69E09397" alt="客製化禮物 7"></div>
                <div class="slide gallery-slide"><img src="https://scontent.xx.fbcdn.net/v/t1.15752-9/650931841_1241071078179028_6071563245192824668_n.jpg?stp=dst-jpg_s960x960_tt6&_nc_cat=101&ccb=1-7&_nc_sid=9f807c&_nc_ohc=sA-cIgxlEjEQ7kNvwF1cJOT&_nc_oc=AdnLCMMsaKM3I5VaQwSnfP1WjYMuG8RBWDl_IfJsKDCwCdTYMTTHMmFCrm3rpCHkVgqQe9bWs4vDJkYPGPdunJdi&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent.xx&_nc_ss=8&oh=03_Q7cD4wEy1fm5MRfM628sJfvRRgXchbSfKluAZOFcFUD2Q1VwjQ&oe=69E08F90" alt="客製化禮物 8"></div>
                <div class="slide gallery-slide"><img src="https://scontent.xx.fbcdn.net/v/t1.15752-9/649667846_779998831467121_5452390362208957190_n.jpg?stp=dst-jpg_s960x960_tt6&_nc_cat=108&ccb=1-7&_nc_sid=9f807c&_nc_ohc=XfTg2n9glHoQ7kNvwFezRN8&_nc_oc=AdnVdHOcvcKH3rTML_IWsTV7L8-IOIetVRLVIgUesiAWLJZp1p_f767DQyjdnLNdicweKo_-2alNq7_ZBBvcCgeb&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent.xx&_nc_ss=8&oh=03_Q7cD4wFs07YveqAh26t3OTzZAfJd84MERlnJaayocYsQ3oqubA&oe=69E09B74" alt="客製化禮物 9"></div>
<div class="slide gallery-slide"><img src="https://scontent.xx.fbcdn.net/v/t1.15752-9/648276087_1420535235956080_1547198401918931487_n.jpg?stp=dst-jpg_s960x960_tt6&_nc_cat=100&ccb=1-7&_nc_sid=9f807c&_nc_ohc=bWHgV8SgVSYQ7kNvwGp253P&_nc_oc=AdljY-bzww3plsqjffg0IwsiHI6QtCxSTTgU_eDfs9mSE3k4t2Ec0j9bn7QZEMJ56R3_OrbvVVsmjnEmUclYTnSu&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent.xx&_nc_ss=8&oh=03_Q7cD4wEbqwTUaTaazsgnDJEv7hDYZPPnGvPGtiSbMc3qBqBL4g&oe=69E1FB43" alt="客製化禮物 10"></div>
<div class="slide gallery-slide"><img src="https://scontent.xx.fbcdn.net/v/t1.15752-9/652111390_1410573997749671_4052723018883233004_n.jpg?stp=dst-jpg_s960x960_tt6&_nc_cat=105&ccb=1-7&_nc_sid=9f807c&_nc_ohc=1LXvF-3O5mEQ7kNvwELQ_Nt&_nc_oc=AdkRYg9w2bX3jZ6eJoQFZUtd-IZaRdC2TCdzAasHk-DTx4EBpYTlf4SzPuazGZ6rTZL0BploOmmkHhHQ3IPaerNf&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent.xx&_nc_ss=8&oh=03_Q7cD4wHz0Qsdnqqdpbwq8FPrSSqsG0whG9dzHTdw57tXrZrWTg&oe=69E1FA6E" alt="客製化禮物 11"></div>
<div class="slide gallery-slide"><img src="https://scontent.xx.fbcdn.net/v/t1.15752-9/654107930_1675839807172324_7787564252580969616_n.jpg?stp=dst-jpg_s960x960_tt6&_nc_cat=102&ccb=1-7&_nc_sid=9f807c&_nc_ohc=6eSPHYLKuOgQ7kNvwH-ybPO&_nc_oc=AdlqRDo82x0lVD9cjFYd_foRedW8NtoTWowfSNoDJV0z-_hHuyIXPeYyVDk58PWg36PseamD-Y6haVUqYnN55a7R&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent.xx&_nc_ss=8&oh=03_Q7cD4wHeXt0yyyG06BnWYOFiKpLTw5rzFPRFHY3af4uMTuSuYg&oe=69E1EFE1" alt="客製化禮物 12"></div>
<div class="slide gallery-slide"><img src="https://scontent.xx.fbcdn.net/v/t1.15752-9/651482821_896732009842912_415445672293485733_n.jpg?stp=dst-jpg_s960x960_tt6&_nc_cat=100&ccb=1-7&_nc_sid=9f807c&_nc_ohc=X7ZKbfVbh2YQ7kNvwEkxtnJ&_nc_oc=AdmCubkS6_gFa5pK89hk7OxvaVmZfnATmE_6Uhduz4m120_R6pZnRm8se8xtSMMVHdhjwElGSlXa1kM1XLAHWq1v&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent.xx&_nc_ss=8&oh=03_Q7cD4wG3Kd-vgvw_TgAW2_l7uni8NRFnCzxsX4tXzfy1N7VWNQ&oe=69E2001C" alt="客製化禮物 13"></div>
            </div>
            <p class="modal-subtitle" style="margin-top: 15px;">💡 手機版可左右滑動 / 電腦版可使用滾輪與方向鍵</p>
            <div class="indicator">
                <span id="current-gallery-page">1</span> / <span id="total-gallery-pages">9</span>
            </div>
        </div>
    </div>

    <div id="news-modal" class="modal">
        <div class="modal-content">
            <span class="close-btn" id="close-news">×</span>
            <h2 class="modal-title">新聞報導</h2>
           
            <div class="slider-container" id="news-slider-container">
                <div class="slide news-slide active">
                    <a href="https://www.epochtimes.com/b5/26/1/26/n14684208.htm" target="_blank">
                        <img src="https://scontent.xx.fbcdn.net/v/t1.15752-9/653816732_871827539223189_5106133441781056921_n.png?stp=dst-png_s960x960&_nc_cat=100&ccb=1-7&_nc_sid=9f807c&_nc_ohc=UgghsWwtl6oQ7kNvwEufZQM&_nc_oc=AdmIkHuUDXGQ8VgahnTpdQ0cQN0ptw259XZpnAgyQo-8MNriOUXRQ-fHcYY8Ah4CIWvx3LC4o6b0RpyZiPQDyOkv&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent.xx&_nc_ss=8&oh=03_Q7cD4wHc0MRn4PKjFYEWYg4vcoizt-acBfmykpl_-5eOD0uj5Q&oe=69E0B7AA" alt="新聞報導 1">
                    </a>
                </div>
                <div class="slide news-slide">
                    <a href="https://www.1658tw.com/?p=184692" target="_blank">
                        <img src="https://scontent.xx.fbcdn.net/v/t1.15752-9/649830103_1469217311249098_2843614465339376325_n.png?stp=dst-png_s960x960&_nc_cat=102&ccb=1-7&_nc_sid=9f807c&_nc_ohc=4d8Hlo7B670Q7kNvwHY9tl5&_nc_oc=Adl6VKpvUuZTCRYNuNFsgbjmf8iYV5UADoipBI9Ynrl7q7csKREAxOKgAYDWIDYcTjBUu3FYfrkzqnL5pjuORRAg&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent.xx&_nc_ss=8&oh=03_Q7cD4wHcnEbLy0AI3FLE3dLbFySE_5Q3JnmgBfiBlZveBFHFEA&oe=69E0ADC3" alt="新聞報導 2">
                    </a>
                </div>
                <div class="slide news-slide">
                    <a href="https://www.1658tw.com/?p=164244" target="_blank">
                        <img src="https://scontent.xx.fbcdn.net/v/t1.15752-9/650750714_914417314707292_7711994707529067471_n.png?stp=dst-png_s960x960&_nc_cat=101&ccb=1-7&_nc_sid=9f807c&_nc_ohc=8lXweE3e6d4Q7kNvwHBqlgj&_nc_oc=AdmwhmtCjAOSXh7erPRbgy2zBpUfXLytvcH3GC5uAmb2CzsnMeRzKMq5wQOC2V47wLEIe6_VBsRbqxKvNPSLcxUk&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent.xx&_nc_ss=8&oh=03_Q7cD4wG727CLE9I5f9syywjNE0uJ7t-QGMIDsvl3dkPw6g6RKw&oe=69E0A973" alt="新聞報導 3">
                    </a>
                </div>
            </div>
            <p class="modal-subtitle" style="margin-top: 15px;">💡 點擊圖片進入原文 / 手機可滑動 / 電腦可使用方向鍵</p>

            <div class="indicator">
                <span id="current-news-page">1</span> / <span id="total-news-pages">3</span>
            </div>
        </div>
    </div>

    <script>
        // === 基礎視窗控制 ===
        const galleryModal = document.getElementById("gallery-modal");
        const newsModal = document.getElementById("news-modal");
        const galleryBtn = document.getElementById("gallery-btn");
        const newsBtn = document.getElementById("news-btn");
        const closeGallery = document.getElementById("close-gallery");
        const closeNews = document.getElementById("close-news");

        galleryBtn.onclick = function(event) {
            event.preventDefault();
            galleryModal.style.display = "block";
            document.body.style.overflow = "hidden";
        }

        newsBtn.onclick = function(event) {
            event.preventDefault();
            newsModal.style.display = "block";
            document.body.style.overflow = "hidden";
        }

        closeGallery.onclick = function() {
            galleryModal.style.display = "none";
            document.body.style.overflow = "auto";
        }
       
        closeNews.onclick = function() {
            newsModal.style.display = "none";
            document.body.style.overflow = "auto";
        }

        window.onclick = function(event) {
            if (event.target == galleryModal) {
                galleryModal.style.display = "none";
                document.body.style.overflow = "auto";
            }
            if (event.target == newsModal) {
                newsModal.style.display = "none";
                document.body.style.overflow = "auto";
            }
        }

        // === 輪播控制共用邏輯 ===
        function setupSlider(slideElements, pageIndicatorId, totalPagesId) {
            const slides = document.querySelectorAll(slideElements);
            const pageIndicator = document.getElementById(pageIndicatorId);
            document.getElementById(totalPagesId).innerText = slides.length;
           
            let currentIndex = 0;

            function showSlide(index) {
                slides.forEach(slide => slide.classList.remove('active'));
               
                if (index >= slides.length) {
                    currentIndex = 0;
                } else if (index < 0) {
                    currentIndex = slides.length - 1;
                } else {
                    currentIndex = index;
                }

                slides[currentIndex].classList.add('active');
                if (pageIndicator) pageIndicator.innerText = currentIndex + 1;
            }

            return {
                next: () => showSlide(currentIndex + 1),
                prev: () => showSlide(currentIndex - 1)
            };
        }

        // 初始化兩個輪播
        const gallerySlider = setupSlider('.gallery-slide', 'current-gallery-page', 'total-gallery-pages');
        const newsSlider = setupSlider('.news-slide', 'current-news-page', 'total-news-pages');

        // === 1. 手機版手指滑動 (Swipe) 事件監聽 ===
        function addTouchSwipe(containerId, slider) {
            const container = document.getElementById(containerId);
            let startX = 0;
            let endX = 0;

            container.addEventListener('touchstart', (e) => {
                startX = e.changedTouches[0].screenX;
            }, { passive: true });

            container.addEventListener('touchend', (e) => {
                endX = e.changedTouches[0].screenX;
                handleSwipe();
            }, { passive: true });

            function handleSwipe() {
                const threshold = 50; // 手指最少要滑動 50px 才會翻頁
                if (startX - endX > threshold) {
                    slider.next(); // 往左滑 -> 下一張
                }
                if (endX - startX > threshold) {
                    slider.prev(); // 往右滑 -> 上一張
                }
            }
        }

        // 幫兩個圖片區塊綁上手指滑動功能
        addTouchSwipe('gallery-slider-container', gallerySlider);
        addTouchSwipe('news-slider-container', newsSlider);

        // === 2. 滑鼠滾輪事件監聽 ===
        let isThrottled = false;
       
        function handleWheelScroll(event, slider) {
            event.preventDefault();
            if (isThrottled) return;
            isThrottled = true;

            if (event.deltaY > 0) {
                slider.next();
            } else if (event.deltaY < 0) {
                slider.prev();
            }

            setTimeout(() => { isThrottled = false; }, 400);
        }

        galleryModal.addEventListener('wheel', (e) => handleWheelScroll(e, gallerySlider));
        newsModal.addEventListener('wheel', (e) => handleWheelScroll(e, newsSlider));

        // === 3. 鍵盤方向鍵監聽 ===
        document.addEventListener('keydown', function(event) {
            const isNewsOpen = newsModal.style.display === "block";
            const isGalleryOpen = galleryModal.style.display === "block";

            if (isNewsOpen || isGalleryOpen) {
                const targetSlider = isNewsOpen ? newsSlider : gallerySlider;

                if (event.key === "ArrowDown" || event.key === "ArrowRight") {
                    event.preventDefault();
                    targetSlider.next();
                } else if (event.key === "ArrowUp" || event.key === "ArrowLeft") {
                    event.preventDefault();
                    targetSlider.prev();
                }
            }
        });
    </script>
</body>
</html>
