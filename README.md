<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EcoLogiTech - ESG 永續物流與智慧行銷系統</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&family=Noto+Sans+TC:wght@300;500;700&display=swap');

        :root {
            --bg-color: #0d0214;
            --panel-bg: #1a0826;
            --sidebar-bg: #09020e;
            --neon-magenta: #ff007f;
            --neon-cyan: #00f0ff;
            --neon-purple: #9d00ff;
            --neon-green: #00ffaa;
            --text-main: #f0e6f5;
            --text-dim: #a692b3;
            --grid-color: rgba(255, 0, 127, 0.06); /* 調高粉霓虹網格對比度 */
        }

        /* 嚴格重設，確保網頁從最頂部開始貼合，絕不產生上下拉動的黑色空白 */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            font-family: 'Noto Sans TC', sans-serif;
            background-image: 
                linear-gradient(var(--grid-color) 1px, transparent 1px),
                linear-gradient(90deg, var(--grid-color) 1px, transparent 1px);
            background-size: 30px 30px; /* 經典科幻網格尺寸 */
            display: flex;
            flex-direction: row; /* 桌面端：左固定選單，右滿版主工作區 */
            min-height: 100vh;
            width: 100vw;
            overflow: hidden;
        }

        /* ==========================================================================
           1. 左側控制台導航欄 (完全復刻範本風格、高發光粉紅外框)
           ========================================================================== */
        aside {
            width: 290px;
            background: rgba(9, 2, 14, 0.95);
            border-right: 2px solid var(--neon-magenta);
            padding: 30px 20px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            height: 100vh;
            flex-shrink: 0;
            z-index: 100;
            box-shadow: 5px 0 25px rgba(255, 0, 127, 0.2);
        }

        /* Logo 區 */
        .logo-area {
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 40px;
        }

        .logo-icon {
            width: 42px;
            height: 42px;
            border-radius: 4px;
            background: rgba(255, 0, 127, 0.1);
            border: 2px solid var(--neon-magenta);
            display: flex;
            align-items: center;
            justify-content: center;
            font-family: 'Orbitron', sans-serif;
            font-weight: bold;
            color: var(--neon-magenta);
            font-size: 0.95rem;
            box-shadow: 0 0 15px var(--neon-magenta);
        }

        .logo-text h2 {
            font-family: 'Orbitron', sans-serif;
            font-size: 1.2rem;
            color: #fff;
            letter-spacing: 1px;
            text-shadow: 0 0 5px var(--neon-magenta);
        }

        .logo-text p {
            font-family: 'Orbitron', sans-serif;
            font-size: 0.65rem;
            color: var(--text-dim);
            letter-spacing: 2px;
        }

        /* 選單列表 */
        .nav-menu {
            list-style: none;
            display: flex;
            flex-direction: column;
            gap: 12px;
            flex: 1;
        }

        .nav-item button {
            width: 100%;
            background: transparent;
            border: 1px solid transparent;
            color: var(--text-dim);
            padding: 14px 18px;
            text-align: left;
            font-size: 0.95rem;
            cursor: pointer;
            border-radius: 4px;
            transition: all 0.25s ease;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .nav-item button:hover {
            color: #fff;
            background: rgba(255, 0, 127, 0.05);
            border-left: 2px solid var(--neon-magenta);
        }

        /* 作用中按鈕：高亮粉紅外框與發光特效 */
        .nav-item button.active {
            color: #fff;
            background: rgba(255, 0, 127, 0.08);
            border: 1px solid var(--neon-magenta);
            box-shadow: 0 0 15px rgba(255, 0, 127, 0.3);
        }

        /* 底部小組簽名區 */
        .sidebar-footer {
            display: flex;
            align-items: center;
            gap: 12px;
            border-top: 1px solid rgba(255, 0, 127, 0.2);
            padding-top: 20px;
        }

        .avatar-circle {
            width: 38px;
            height: 38px;
            border-radius: 50%;
            background: rgba(0, 240, 255, 0.1);
            border: 1px solid var(--neon-cyan);
            display: flex;
            align-items: center;
            justify-content: center;
            font-family: 'Orbitron', sans-serif;
            color: var(--neon-cyan);
            font-weight: bold;
            font-size: 0.85rem;
        }

        .footer-info h4 {
            font-size: 0.85rem;
            color: #fff;
        }

        .footer-info p {
            font-size: 0.75rem;
            color: var(--text-dim);
        }

        /* ==========================================================================
           2. 右側主工作面板 (頁面切換控制)
           ========================================================================== */
        .main-workspace {
            flex: 1;
            height: 100vh;
            overflow-y: auto;
            position: relative;
        }

        .page-view {
            display: none;
            width: 100%;
            min-height: 100%;
            animation: pageFadeIn 0.35s ease-out forwards;
        }

        .page-view.active {
            display: block;
        }

        @keyframes pageFadeIn {
            from { opacity: 0; transform: scale(0.99); }
            to { opacity: 1; transform: scale(1); }
        }

        /* ==========================================================================
           分頁一：數據儀表板 (完全復刻自最新數據卡片範本)
           ========================================================================== */
        .dashboard-layout {
            padding: 40px;
        }

        .badge-tag {
            display: inline-block;
            background: rgba(0, 255, 170, 0.1);
            border: 1px solid var(--neon-green);
            color: var(--neon-green);
            font-family: 'Orbitron', sans-serif;
            font-size: 0.75rem;
            padding: 4px 12px;
            border-radius: 20px;
            letter-spacing: 1px;
            margin-bottom: 15px;
        }

        .dash-title {
            font-size: 2.2rem;
            color: #fff;
            margin-bottom: 15px;
            letter-spacing: 1px;
            text-shadow: 0 0 10px rgba(255,255,255,0.1);
        }

        .dash-desc {
            color: var(--text-dim);
            font-size: 0.95rem;
            line-height: 1.6;
            margin-bottom: 40px;
            max-width: 800px;
        }

        /* 三顆指標核心卡片網格 */
        .metrics-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
            margin-bottom: 40px;
        }

        .metric-card {
            background: var(--panel-bg);
            border: 1px solid rgba(255, 0, 127, 0.15); /* 使用粉紅微發光邊框 */
            border-radius: 8px;
            padding: 30px 25px;
            position: relative;
            transition: all 0.3s;
        }

        .metric-card:hover {
            border-color: var(--neon-cyan);
            box-shadow: 0 0 15px rgba(0, 240, 255, 0.2);
        }

        .card-icon-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 25px;
        }

        .card-icon-header svg {
            width: 32px;
            height: 32px;
            stroke: var(--neon-cyan);
            fill: none;
            stroke-width: 1.5;
        }

        .trend-up {
            font-family: 'Orbitron', sans-serif;
            color: var(--neon-green);
            font-size: 0.85rem;
            background: rgba(0, 255, 170, 0.08);
            padding: 2px 8px;
            border-radius: 4px;
        }

        .metric-label {
            color: var(--text-dim);
            font-size: 0.9rem;
            margin-bottom: 8px;
        }

        .metric-value {
            font-family: 'Orbitron', 'Noto Sans TC', sans-serif;
            font-size: 2.4rem;
            color: #fff;
            font-weight: 700;
        }

        .charts-row {
            display: grid;
            grid-template-columns: 1.5fr 1fr;
            gap: 25px;
        }

        .chart-box {
            background: var(--panel-bg);
            border: 1px solid rgba(255, 0, 127, 0.1);
            border-radius: 8px;
            padding: 25px;
            min-height: 200px;
        }

        .chart-box h3 {
            font-size: 1.1rem;
            margin-bottom: 6px;
            color: #fff;
        }

        .chart-box p {
            color: var(--text-dim);
            font-size: 0.85rem;
        }

        /* ==========================================================================
           分頁二：雙直欄大滿版簡報頁面 (完全復刻自影片與簡報對分範本)
           ========================================================================== */
        .split-presentation-layout {
            display: flex;
            flex-direction: row;
            width: 100%;
            height: 100vh;
        }

        .split-left-text {
            flex: 1.1;
            padding: 40px;
            overflow-y: auto;
            border-right: 2px solid var(--neon-magenta); /* 橫切面大霓虹線 */
        }

        .split-right-media {
            flex: 1;
            background: rgba(20, 5, 30, 0.95);
            padding: 40px 25px;
            display: flex;
            flex-direction: column;
            gap: 25px;
            overflow-y: auto;
        }

        .meta-info-panel {
            border: 1px solid var(--neon-purple);
            padding: 20px;
            background: rgba(157, 0, 255, 0.05);
            border-radius: 4px;
            margin-bottom: 30px;
        }

        .meta-info-panel h2 {
            color: var(--neon-cyan);
            font-size: 1.2rem;
            margin-bottom: 12px;
            font-family: 'Orbitron', 'Noto Sans TC', sans-serif;
        }

        .intro-text-panel {
            background: var(--panel-bg);
            border-left: 4px solid var(--neon-magenta); /* 左緣改為粉霓虹高光 */
            padding: 20px;
            margin-bottom: 35px;
            box-shadow: 0 0 20px rgba(255, 0, 127, 0.05);
        }

        .intro-text-panel h2 {
            color: var(--neon-magenta);
            font-size: 1.2rem;
            margin-bottom: 10px;
        }

        .cases-section {
            background: rgba(26, 8, 38, 0.8);
            border: 1px solid var(--neon-purple);
            padding: 25px;
            border-radius: 6px;
        }

        .cases-section h2 {
            font-family: 'Orbitron', sans-serif;
            color: var(--neon-cyan);
            margin-bottom: 15px;
            font-size: 1.3rem;
        }

        .case-block {
            margin-bottom: 20px;
            padding-bottom: 20px;
            border-bottom: 1px dashed rgba(255, 0, 127, 0.2);
        }

        .case-block:last-child {
            margin-bottom: 0;
            padding-bottom: 0;
            border-bottom: none;
        }

        .case-block h3 {
            color: #fff;
            margin-bottom: 6px;
            font-size: 1.05rem;
        }

        .case-block p {
            color: var(--text-dim);
            font-size: 0.85rem;
        }

        /* 右半側多媒體比例盒 */
        .media-responsive-wrapper {
            border: 1px solid var(--neon-magenta);
            background: rgba(255, 0, 127, 0.02);
            padding: 20px;
            border-radius: 4px;
            box-shadow: 0 0 15px rgba(255, 0, 127, 0.15);
        }

        .media-responsive-wrapper h4 {
            font-size: 1rem;
            color: var(--neon-magenta);
            margin-bottom: 12px;
            font-family: 'Orbitron', sans-serif;
            text-align: center;
        }

        .responsive-iframe-container {
            position: relative;
            width: 100%;
            padding-bottom: 56.25%; /* 完美的 16:9 比例 */
            height: 0;
            overflow: hidden;
            border: 1px solid var(--neon-purple);
            background: #000;
        }

        .responsive-iframe-container iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: 0;
        }

        /* ==========================================================================
           RWD 響應式佈局縮放（平板與手機介面自適應）
           ========================================================================== */
        @media screen and (max-width: 1150px) {
            body {
                flex-direction: column;
            }
            aside {
                width: 100%;
                height: auto;
                border-right: none;
                border-bottom: 2px solid var(--neon-magenta);
                padding: 20px;
            }
            .nav-menu {
                flex-direction: row;
                flex-wrap: wrap;
                margin-top: 15px;
            }
            .main-workspace {
                height: auto;
                overflow-y: visible;
            }
            .metrics-grid {
                grid-template-columns: 1fr;
            }
            .charts-row {
                grid-template-columns: 1fr;
            }
            .split-presentation-layout {
                flex-direction: column;
                height: auto;
            }
            .split-left-text, .split-right-media {
                width: 100%;
                height: auto;
            }
        }
    </style>
</head>
<body>

    <!-- 左側控制台導航欄 (完全復刻範本風格、高發光粉紅外框)[cite: 3] -->
    <aside>
        <div class="top-navigation-block">
            <div class="logo-area">
                <div class="logo-icon">ESG</div>
                <div class="logo-text">
                    <h2>EcoLogiTech</h2>
                    <p>SUSTAINABLE LOGISTICS</p>
                </div>
            </div>

            <!-- 選單分頁點擊動態路由[cite: 3] -->
            <ul class="nav-menu">
                <li class="nav-item">
                    <button class="active" onclick="routeToPage(this, 'dashboard-page')">
                        <span style="font-family:'Orbitron'">▚</span> 數據儀表板
                    </button>
                </li>
                <li class="nav-item">
                    <button onclick="routeToPage(this, 'presentation-page')">
                        <span style="font-family:'Orbitron'">▞</span> 專題投影片
                    </button>
                </li>
                <li class="nav-item">
                    <button onclick="routeToPage(this, 'presentation-page')">
                        <span style="font-family:'Orbitron'">⚙</span> 精選影音檔
                    </button>
                </li>
                <li class="nav-item">
                    <button onclick="alert('附件下載就緒')">
                        <span style="font-family:'Orbitron'">⬇</span> 相關附件下載
                    </button>
                </li>
                <li class="nav-item">
                    <button onclick="alert('私房珍藏解鎖中')">
                        <span style="font-family:'Orbitron'">♥</span> 私房珍藏館
                    </button>
                </li>
            </ul>
        </div>

        <div class="sidebar-footer">
            <div class="avatar-circle">SL</div>
            <div class="footer-info">
                <h4>綠色科技研究組</h4>
                <p>ESG 專題展示</p>
            </div>
        </div>
    </aside>

    <!-- 右側主工作面板[cite: 3] -->
    <main class="main-workspace">

        <!-- ==========================================================================
           分頁一：數據儀表板 (完全復刻自 image_94d2a1.jpg)[cite: 3]
           ========================================================================== */
        <div id="dashboard-page" class="page-view active">
            <div class="dashboard-layout">
                <span class="badge-tag">ESG METRICS & CORE DATA</span>
                <h1 class="dash-title">ESG永續物流與綠色技術</h1>
                <p class="dash-desc">本專案展示物流供應鏈於數位化轉型下的綠色技術實踐。透過大數據分析與智慧排程系統，減少碳足跡、提升電動載具自給率，建構永續發展的物流生態圈[cite: 1]。</p>

                <div class="metrics-grid">
                    <!-- 卡片 1 -->
                    <div class="metric-card">
                        <div class="card-icon-header">
                            <svg viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm1 15h-2v-6h2v6zm0-8h-2V7h2v2z"/></svg>
                            <span class="trend-up">↗ +14.8%</span>
                        </div>
                        <p class="metric-label">累計碳排放減量</p>
                        <h2 class="metric-value">124,850 <span>t</span></h2>
                    </div>
                    <!-- 卡片 2 -->
                    <div class="metric-card">
                        <div class="card-icon-header">
                            <svg viewBox="0 0 24 24"><path d="M20 8h-3V4H3c-1.1 0-2 .9-2 2v11h2c0 1.66 1.34 3 3 3s3-1.34 3-3h6c0 1.66 1.34 3 3 3s3-1.34 3-3h2v-5l-3-4z"/></svg>
                            <span class="trend-up">↗ +8.2%</span>
                        </div>
                        <p class="metric-label">新能源電動車佔比</p>
                        <h2 class="metric-value">42.5 %</h2>
                    </div>
                    <!-- 卡片 3 -->
                    <div class="metric-card">
                        <div class="card-icon-header">
                            <svg viewBox="0 0 24 24"><path d="M13 2v9h9V2h-9zm7 7h-5V4h5v5zm-7 13h9v-9h-9v9zm5-5h-5v-5h5v5zM2 22h9v-9H2v9zm5-5H4v-5h3v5zM2 2v9h9V2H2zm5 5H4V4h3v3z"/></svg>
                            <span class="trend-up">↗ +12.4%</span>
                        </div>
                        <p class="metric-label">智慧倉儲綠電自給率</p>
                        <h2 class="metric-value">68.0 %</h2>
                    </div>
                </div>

                <div class="charts-row">
                    <div class="chart-box">
                        <h3>全球綠色物流市場產值規模趨勢</h3>
                        <p>預估 2020 年至 2026 年綠色供應鏈市場規模之增長趨勢 (十億美元)</p>
                    </div>
                    <div class="chart-box">
                        <h3>核心減碳技術貢獻佔比</h3>
                        <p>各項永續綠色技術模組對年度碳排放降低的貢獻權重比 (%)</p>
                    </div>
                </div>
            </div>
        </div>

        <!-- ==========================================================================
           分頁二：雙直欄大滿版簡報頁面 (完全復刻自影片與簡報對分範本)[cite: 3]
           ========================================================================== */
        <div id="presentation-page" class="page-view">
            <div class="split-presentation-layout">
                <!-- 左半部：報告文字大綱 -->
                <div class="split-left-text">
                    <div class="meta-info-panel">
                        <h2>// 專題團隊與機構資訊</h2>
                        <p style="font-size: 0.9rem; line-height: 1.8; color: var(--text-dim);">
                            學門機構：<span style="color: var(--text-main);">勤益科技大學 流通科技管理科系</span><br>
                            指導導師：<span style="color: var(--text-main);">褚文明 教授</span> &nbsp;|&nbsp; 專案組員：<span style="color: var(--text-main);">王湘芸、陳姿婷</span><br>
                            聯繫管道：<span style="color: var(--neon-cyan);">0976517599</span>
                        </p>
                    </div>

                    <div class="intro-text-panel">
                        <h2>// 核心思維：物流即行銷，供應鏈即體驗</h2>
                        <p style="font-size: 0.9rem; line-height: 1.6; color: var(--text-dim);">
                            在過去，物流是躲在幕後的「搬運工」，只要貨物準時抵達，工作就算完成[cite: 1, 3]。然而在 AI 技術爆發的今天，物流的角色早已躍升為企業的<span class="highlight">核心競爭力</span>[cite: 1, 3]。它不再只是後勤支援，而是品牌與客戶之間最真實、最感性的接觸點[cite: 1, 3]。AI 的價值在於消除未知所產生的等待焦慮，將冰冷的鏈路轉化為溫暖的品牌承諾[cite: 1, 3]。
                        </p>
                    </div>

                    <div class="cases-section">
                        <h2>// 實例動態分析 (CASE STUDIES)</h2>
                        <div class="case-block">
                            <h3>亞馬遜 (Amazon) — 預測式發貨 (Anticipatory Shipping)</h3>
                            <p>運用 AI 專利算法分析使用者的瀏覽紀錄、購物車與停留時間[cite: 1, 3]。在消費者點擊購買前，系統便提前將商品運往距離該市場最近的衛星倉儲，創造頂級的行銷與履約體驗[cite: 1, 3]。</p>
                        </div>
                        <div class="case-block">
                            <h3>全聯福利中心 — 智慧補貨與動態履約</h3>
                            <p>引進自動化物流中心並與氣象、歷史大數據連動，在颱風或大節慶來臨前透過 AI 需求感測提早調配車隊與路線[cite: 1, 3]。當消費者在關鍵時刻看到滿滿的生鮮貨架，便建立起極高的品牌信賴感[cite: 1, 3]。</p>
                        </div>
                    </div>
                </div>

                <!-- 右半部：多媒體展示區 (影片與 PPT 大畫面上下並列) -->
                <div class="split-right-media">
                    <div class="media-responsive-wrapper">
                        <h4>精選影音檔專欄播放</h4>
                        <div class="responsive-iframe-container">
                            <iframe src="https://www.youtube.com/embed/IZlMuEshrDk" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                        </div>
                    </div>
                    <div class="media-responsive-wrapper">
                        <h4>永續物流與綠色科技 專題簡報 PPT</h4>
                        <div class="responsive-iframe-container">
                            <iframe src="https://view.officeapps.live.com/op/embed.aspx?src=https://raw.githubusercontent.com/GitHubAnson/AI-logistics-marketing/main/AI_Logistics_Transformation.pptx" frameborder="0"></iframe>
                        </div>
                    </div>
                </div>
            </div>
        </div>

    </main>

    <!-- 頁面路由切換邏輯 -->
    <script>
        function routeToPage(btnElement, targetPageId) {
            document.querySelectorAll('.nav-item button').forEach(btn => {
                btn.classList.remove('active');
            });
            btnElement.classList.add('active');

            document.querySelectorAll('.page-view').forEach(page => {
                page.classList.remove('active');
            });
            document.getElementById(targetPageId).classList.add('active');
        }
    </script>
</body>
</html>
