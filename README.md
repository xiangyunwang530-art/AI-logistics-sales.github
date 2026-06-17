<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI 時代物流行銷 vs 傳統行銷 | 典範轉移報告</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&family=Noto+Sans+TC:wght@300;500;700&display=swap');

        :root {
            --bg-color: #0d0214;
            --panel-bg: #1a0826;
            --neon-magenta: #ff007f;
            --neon-cyan: #00f0ff;
            --neon-purple: #9d00ff;
            --text-main: #f0e6f5;
            --text-dim: #a692b3;
            --grid-color: rgba(255, 0, 127, 0.05);
        }

        /* 嚴格重設外邊距與內邊距，阻絕任何背景雜訊或溢出文字 */
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
            background-size: 25px 25px;
            display: flex;
            flex-direction: row; /* B2B 桌面佈局：左右彈性排列 */
            min-height: 100vh;
            overflow-x: hidden;
        }

        /* ==========================================================================
           側邊欄導航系統（Flexbox 架構、完美置頂不留白、全面清空暗字雜訊）
           ========================================================================== */
        aside {
            width: 340px;
            background: rgba(26, 8, 38, 0.95);
            border-right: 2px solid var(--neon-magenta);
            padding: 25px 15px;
            display: flex;
            flex-direction: column;
            gap: 25px;
            box-shadow: 5px 0 25px rgba(255, 0, 127, 0.15);
            position: fixed;
            top: 0; /* 鎖定在視窗最上方，絕不產生空白 */
            left: 0;
            height: 100vh;
            overflow-y: auto;
            z-index: 100;
            flex-shrink: 0;
        }

        .meta-panel {
            border: 1px solid var(--neon-purple);
            padding: 20px;
            background: rgba(157, 0, 255, 0.05);
            border-radius: 4px;
        }

        .meta-panel h3 {
            font-family: 'Orbitron', sans-serif;
            color: var(--neon-cyan);
            font-size: 1.1rem;
            margin-bottom: 15px;
            letter-spacing: 1px;
            border-bottom: 1px solid var(--neon-purple);
            padding-bottom: 5px;
        }

        .meta-list {
            list-style: none;
            font-size: 0.9rem;
            display: flex;
            flex-direction: column;
            gap: 10px;
            color: var(--text-dim);
        }

        .meta-list span {
            color: var(--text-main);
            font-weight: bold;
        }

        /* 影片播放區塊 */
        .video-box {
            border: 1px solid var(--neon-magenta);
            background: rgba(255, 0, 127, 0.05);
            padding: 15px;
            border-radius: 4px;
            text-align: center;
        }

        .video-box h4 {
            font-size: 1rem;
            color: var(--neon-magenta);
            margin-bottom: 12px;
            font-family: 'Orbitron', sans-serif;
            letter-spacing: 1px;
        }

        .video-container {
            position: relative;
            width: 100%;
            padding-bottom: 56.25%; /* 標準 16:9 比例 */
            height: 0;
            overflow: hidden;
            border: 1px solid var(--neon-purple);
            box-shadow: 0 0 15px rgba(255, 0, 127, 0.2);
        }

        .video-container iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: 0;
        }

        /* ==========================================================================
           主要報告內文區塊（大螢幕與 RWD 彈性伸縮）
           ========================================================================== */
        main {
            margin-left: 340px; /* 保留給固定側邊欄的寬度 */
            flex: 1;
            padding: 40px;
            max-width: 1200px;
            width: 100%;
            transition: margin-left 0.3s ease, padding 0.3s ease;
        }

        header {
            text-align: center;
            margin-bottom: 50px;
            border-bottom: 2px solid var(--neon-magenta);
            padding-bottom: 30px;
        }

        header h1 {
            font-family: 'Orbitron', sans-serif;
            font-size: 2.5rem;
            color: #fff;
            text-shadow: 0 0 15px var(--neon-magenta);
            letter-spacing: 2px;
            margin-bottom: 10px;
        }

        .subtitle {
            font-family: 'Orbitron', sans-serif;
            color: var(--neon-cyan);
            font-size: 1.1rem;
            letter-spacing: 1px;
        }

        .intro-panel {
            background: var(--panel-bg);
            border-left: 4px solid var(--neon-cyan);
            padding: 25px;
            margin-bottom: 40px;
            box-shadow: 0 0 20px rgba(0, 240, 255, 0.05);
        }

        .intro-panel h2 {
            color: var(--neon-cyan);
            font-size: 1.3rem;
            margin-bottom: 12px;
        }

        .toggle-container {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 40px;
            flex-wrap: wrap; /* 寬度不夠時按鈕自動向下流動換行 */
        }

        .toggle-btn {
            background: transparent;
            border: 2px solid var(--neon-magenta);
            color: var(--neon-magenta);
            padding: 12px 35px;
            font-family: 'Orbitron', 'Noto Sans TC', sans-serif;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 0 10px rgba(255, 0, 127, 0.2);
        }

        .toggle-btn.active, .toggle-btn:hover {
            background: var(--neon-magenta);
            color: #fff;
            box-shadow: 0 0 25px var(--neon-magenta);
        }

        /* ==========================================================================
           數據展示看板（CSS Grid 自動網格排版）
           ========================================================================== */
        .view-section {
            display: none;
            animation: cubic-bezier(0.4, 0, 0.2, 1) fadeIn 0.4s forwards;
        }

        .view-section.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(15px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .grid-cards {
            display: grid;
            /* 自動填滿 (auto-fit)，卡片在最小 260px 到最大 1fr 之間彈性調整欄數 */
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 25px;
            margin-bottom: 40px;
        }

        .card {
            background: var(--panel-bg);
            border: 1px solid rgba(255, 0, 127, 0.1);
            padding: 25px;
            border-radius: 4px;
            transition: all 0.3s ease;
        }

        .card:hover {
            border-color: var(--neon-cyan);
            box-shadow: 0 0 20px rgba(0, 240, 255, 0.2);
        }

        .card h3 {
            font-size: 1.2rem;
            color: #fff;
            margin-bottom: 12px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            padding-bottom: 8px;
        }

        .card p {
            color: var(--text-dim);
            font-size: 0.95rem;
        }

        .highlight {
            color: var(--neon-cyan);
            font-weight: bold;
        }

        /* 案例研究區域（Flexbox 平行與垂直適應） */
        .cases-section {
            background: rgba(26, 8, 38, 0.8);
            border: 1px solid var(--neon-purple);
            padding: 30px;
            border-radius: 6px;
            margin-top: 40px;
        }

        .cases-section h2 {
            font-family: 'Orbitron', sans-serif;
            color: var(--neon-cyan);
            margin-bottom: 25px;
            text-shadow: 0 0 10px var(--neon-cyan);
        }

        .case-block {
            display: flex;
            flex-direction: row; /* 大螢幕下圖片與文字並排 */
            gap: 30px;
            margin-bottom: 30px;
            padding-bottom: 30px;
            border-bottom: 1px dashed rgba(157, 0, 255, 0.2);
            align-items: center;
        }

        .case-block:last-child {
            margin-bottom: 0;
            padding-bottom: 0;
            border-bottom: none;
        }

        .case-img-placeholder {
            width: 220px;
            height: 140px;
            background: linear-gradient(135deg, var(--panel-bg) 0%, #301242 100%);
            border: 1px solid var(--neon-magenta);
            display: flex;
            align-items: center;
            justify-content: center;
            font-family: 'Orbitron', sans-serif;
            font-size: 0.8rem;
            color: var(--neon-magenta);
            box-shadow: 0 0 10px rgba(255, 0, 127, 0.2);
            flex-shrink: 0;
        }

        .case-text h3 {
            color: #fff;
            margin-bottom: 10px;
            font-size: 1.2rem;
        }

        .case-text p {
            color: var(--text-dim);
            font-size: 0.95rem;
        }

        /* ==========================================================================
           RWD 響應式佈局切換機制 (Media Queries)
           ========================================================================== */
        
        /* 平板、小筆電環境 (螢幕寬度小於 1024px) */
        @media screen and (max-width: 1024px) {
            body {
                flex-direction: column; /* 整個版面自動切換為垂直堆疊 */
            }

            aside {
                position: relative; /* 解除左側固定狀態 */
                width: 100%; /* 寬度自動滿版 */
                height: auto; /* 高度隨內嵌影片與文字彈性撐開 */
                border-right: none;
                border-bottom: 2px solid var(--neon-magenta);
                box-shadow: 0 5px 25px rgba(255, 0, 127, 0.15);
                top: auto;
            }

            main {
                margin-left: 0; /* 移除桌面端的左方間距 */
                padding: 30px 20px;
            }

            header h1 {
                font-size: 2rem;
            }

            .case-block {
                flex-direction: column; /* 案例分析區改為上下排列 */
                align-items: flex-start;
                gap: 15px;
            }

            .case-img-placeholder {
                width: 100%; /* 圖片容器在平版/手機上自動寬度滿版 */
                height: 160px;
            }
        }

        /* 智慧型手機環境 (螢幕寬度小於 480px) */
        @media screen and (max-width: 480px) {
            header h1 {
                font-size: 1.6rem;
            }
            .toggle-btn {
                padding: 10px 20px;
                font-size: 0.95rem;
                width: 100%; /* 控制按鈕自動垂直全滿，便於手機點擊 */
            }
            .cases-section {
                padding: 15px;
            }
        }
    </style>
</head>
<body>

    <aside>
        <div class="meta-panel">
            <h3>專題團隊資訊</h3>
            <ul class="meta-list">
                <li>科系：<span>流通科技管理科系</span></li>
                <li>導師：<span>褚文明 教授</span></li>
                <li>組員：<span>王湘芸、陳姿婷</span></li>
            </ul>
        </div>

        <div class="video-box">
            <h4>影片專欄播放</h4>
            <div class="video-container">
                <iframe src="https://www.youtube.com/embed/IZlMuEshrDk" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
            </div>
        </div>

        <div class="meta-panel" style="margin-top: auto;">
            <h3>聯繫方式</h3>
            <ul class="meta-list">
                <li>電話：<span>0976517599</span></li>
                <li>地址：<span>勤益科技大學</span></li>
            </ul>
        </div>
    </aside>

    <main>
        <header>
            <h1>物流範式轉移</h1>
            <div class="subtitle">AI-POWERED VS LEGACY MARKETING // REPORT</div>
        </header>

        <div class="intro-panel">
            <h2>// 核心思維：物流即行銷，供應鏈即體驗</h2>
            <p>在過去，物流是躲在幕後的「搬運工」，只要貨物準時抵達，工作就算完成。然而在 AI 技術爆發的今天，物流的角色早已躍升為企業的<span class="highlight">核心競爭力</span>。它不再只是後勤支援，而是品牌與客戶之間最真實、最感性的接觸點。AI 的價值在於消除等待的心理負擔，將冷冰冰的供應鏈轉化為溫暖的品牌承諾。</p>
        </div>

        <div class="toggle-container">
            <button class="toggle-btn active" onclick="toggleDashboard('ai-view')">AI 智慧物流行銷</button>
            <button class="toggle-btn" onclick="toggleDashboard('legacy-view')">傳統物流行銷</button>
        </div>

        <div id="ai-view" class="view-section active">
            <div class="grid-cards">
                <div class="card">
                    <h3>核心賣點 (Value)</h3>
                    <p>強調<span class="highlight">「彈性預測、動態履約、綠色溢價」</span>。著重於系統抵抗不確定性的能力與黑天鵝免疫力。</p>
                </div>
                <div class="card">
                    <h3>數據角色 (Data)</h3>
                    <p>運用<span class="highlight">「需求感測（Demand Sensing）」</span>化為行銷武器，主動告知客戶如何避開即時港口延誤與氣候風險。</p>
                </div>
                <div class="card">
                    <h3>客戶體驗 (CX)</h3>
                    <p>藉由 <span class="highlight">AI Agent 智能共感</span>即時摘要關務與異常警示，在貨主提問、產生等待焦慮前即主動給予解決方案。</p>
                </div>
                <div class="card">
                    <h3>品牌永續 (ESG)</h3>
                    <p>將 AI 即時路徑優化轉為<span class="highlight">「範疇三減碳數據」</span>儀表板，直接助客戶滿足國際關稅與綠色鏈要求。</p>
                </div>
            </div>
        </div>

        <div id="legacy-view" class="view-section">
            <div class="grid-cards">
                <div class="card" style="border-color: rgba(157,0,255,0.2)">
                    <h3>核心賣點 (Value)</h3>
                    <p>強調「準時、安全、便宜」。著重於車隊、倉庫面積等實體資產與標準 SLA 的被動推銷。</p>
                </div>
                <div class="card" style="border-color: rgba(157,0,255,0.2)">
                    <h3>數據角色 (Data
