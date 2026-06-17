<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI 時代物流行銷 vs 傳統行銷 | 專題發表控制台</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&family=Noto+Sans+TC:wght@300;400;500;700&display=swap');

        :root {
            --bg-dark: #0a0c14;
            --sidebar-bg: #111424;
            --card-bg: #171b30;
            --neon-blue: #00e5ff;
            --neon-pink: #ff2a85;
            --neon-green: #39ff14;
            --text-light: #f1f5f9;
            --text-muted: #94a3b8;
            --border-color: rgba(0, 229, 255, 0.15);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Noto Sans TC', sans-serif;
            background-color: var(--bg-dark);
            color: var(--text-light);
            display: flex;
            min-height: 100vh;
            overflow-x: hidden;
            background-image: 
                linear-gradient(rgba(0, 229, 255, 0.02) 1px, transparent 1px),
                linear-gradient(90deg, rgba(0, 229, 255, 0.02) 1px, transparent 1px);
            background-size: 25px 25px;
        }

        /* Sidebar Navigation */
        aside {
            width: 280px;
            background-color: var(--sidebar-bg);
            border-right: 1px solid var(--border-color);
            display: flex;
            flex-direction: column;
            position: fixed;
            top: 0;
            bottom: 0;
            left: 0;
            z-index: 100;
            transition: all 0.3s ease;
        }

        .sidebar-header {
            padding: 30px 20px;
            text-align: center;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
        }

        .sidebar-header h2 {
            font-family: 'Orbitron', sans-serif;
            font-size: 1.4rem;
            color: var(--neon-blue);
            text-shadow: 0 0 10px rgba(0, 229, 255, 0.3);
            letter-spacing: 1px;
        }

        .sidebar-menu {
            list-style: none;
            padding: 20px 0;
            flex-grow: 1;
        }

        .sidebar-menu li a {
            display: flex;
            align-items: center;
            padding: 15px 25px;
            color: var(--text-muted);
            text-decoration: none;
            font-weight: 500;
            border-left: 4px solid transparent;
            transition: all 0.2s ease;
            cursor: pointer;
        }

        .sidebar-menu li a:hover, .sidebar-menu li a.active {
            color: #fff;
            background: linear-gradient(90deg, rgba(0, 229, 255, 0.05), transparent);
            border-left-color: var(--neon-blue);
        }

        .sidebar-footer {
            padding: 20px;
            font-family: 'Orbitron', sans-serif;
            font-size: 0.75rem;
            color: var(--text-muted);
            text-align: center;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
        }

        /* Main Content Wrapper */
        main {
            margin-left: 280px;
            flex-grow: 1;
            padding: 40px;
            transition: all 0.3s ease;
        }

        /* Content Sections */
        .section-panel {
            display: none;
            animation: slideUp 0.4s cubic-bezier(0.16, 1, 0.3, 1) forwards;
        }

        .section-panel.active {
            display: block;
        }

        @keyframes slideUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        h1 {
            font-size: 2.2rem;
            color: #fff;
            margin-bottom: 10px;
            font-weight: 700;
        }

        .section-desc {
            color: var(--text-muted);
            margin-bottom: 30px;
            font-size: 1.05rem;
        }

        /* Grid Layouts */
        .dashboard-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-bottom: 35px;
        }

        .info-card {
            background-color: var(--card-bg);
            border: 1px solid rgba(255, 255, 255, 0.03);
            border-radius: 8px;
            padding: 25px;
            position: relative;
            box-shadow: 0 4px 20px rgba(0,0,0,0.2);
            transition: all 0.3s ease;
        }

        .info-card:hover {
            border-color: var(--border-color);
            box-shadow: 0 0 15px rgba(0, 229, 255, 0.1);
            transform: translateY(-2px);
        }

        .card-accent-pink { border-top: 3px solid var(--neon-pink); }
        .card-accent-blue { border-top: 3px solid var(--neon-blue); }

        .info-card h3 {
            font-size: 1.25rem;
            color: #fff;
            margin-bottom: 15px;
        }

        .info-card p {
            color: var(--text-muted);
            font-size: 0.95rem;
            line-height: 1.6;
        }

        .highlight {
            color: var(--neon-green);
            font-weight: bold;
        }

        /* Comparison Matrix / Table */
        .matrix-table {
            width: 100%;
            border-collapse: collapse;
            background-color: var(--card-bg);
            border-radius: 8px;
            overflow: hidden;
            margin-top: 20px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.2);
        }

        .matrix-table th, .matrix-table td {
            padding: 18px 20px;
            text-align: left;
        }

        .matrix-table th {
            background-color: rgba(0, 229, 255, 0.05);
            color: var(--neon-blue);
            font-weight: 600;
            font-family: 'Orbitron', 'Noto Sans TC', sans-serif;
            border-bottom: 2px solid var(--border-color);
        }

        .matrix-table td {
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
            font-size: 0.95rem;
        }

        .matrix-table tr:hover {
            background-color: rgba(255, 255, 255, 0.01);
        }

        /* SVG Trend Chart Component */
        .chart-container {
            background-color: var(--card-bg);
            border: 1px solid rgba(255, 255, 255, 0.03);
            border-radius: 8px;
            padding: 30px;
            margin-bottom: 35px;
        }

        .chart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .chart-title {
            font-size: 1.2rem;
            font-weight: bold;
            color: #fff;
        }

        .chart-legend {
            display: flex;
            gap: 15px;
            font-size: 0.85rem;
        }

        .legend-item {
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .legend-dot-pink { width: 12px; height: 12px; background-color: var(--neon-pink); border-radius: 2px; }
        .legend-dot-blue { width: 12px; height: 12px; background-color: var(--neon-blue); border-radius: 2px; }

        /* Responsive Design */
        @media (max-width: 992px) {
            aside {
                width: 70px;
            }
            aside .sidebar-header h2, aside .sidebar-menu span, aside .sidebar-footer {
                display: none;
            }
            aside .sidebar-menu li a {
                padding: 15px 0;
                justify-content: center;
                border-left: none;
                border-bottom: 3px solid transparent;
            }
            aside .sidebar-menu li a:hover, aside .sidebar-menu li a.active {
                border-bottom-color: var(--neon-blue);
                background: transparent;
            }
            main {
                margin-left: 70px;
                padding: 25px;
            }
        }

        @media (max-width: 576px) {
            body {
                flex-direction: column;
            }
            aside {
                width: 100%;
                height: auto;
                position: relative;
                flex-direction: row;
                border-right: none;
                border-bottom: 1px solid var(--border-color);
            }
            aside .sidebar-menu {
                display: flex;
                padding: 0;
                width: 100%;
                justify-content: space-around;
            }
            main {
                margin-left: 0;
                padding: 20px;
            }
            h1 {
                font-size: 1.8rem;
            }
        }
    </style>
</head>
<body>

    <!-- 側邊欄導航 (Sidebar Navigation) -->
    <aside>
        <div class="sidebar-header">
            <h2>LOGISTICS MARKETING</h2>
        </div>
        <ul class="sidebar-menu">
            <li><a class="active" onclick="showPanel('overview')"><span>核心思維</span></a></li>
            <li><a onclick="showPanel('matrix')"><span>四大維度對比</span></a></li>
            <li><a onclick="showPanel('trends')"><span>市場趨勢圖表</span></a></li>
            <li><a onclick="showPanel('cases')"><span>實例深度解析</span></a></li>
        </ul>
        <div class="sidebar-footer">
            SYS STATUS: ACTIVE V4.0
        </div>
    </aside>

    <!-- 主要內容區 (Main Content Wrapper) -->
    <main>
        
        <!-- 核心思維 Section -->
        <section id="overview" class="section-panel active">
            <h1>AI 時代物流行銷變革</h1>
            <p class="section-desc">探討智慧供應鏈如何從幕後勞力活，躍升為前線最具溫度的品牌行銷利器。</p>
            
            <div class="dashboard-grid">
                <div class="info-card card-accent-pink">
                    <h3>傳統物流行銷的侷限</h3>
                    <p>過去通常著重於 4P 理論中的「通路 (Place)」與基礎的「推廣 (Promotion)」。宣傳焦點單純擺在標準資產的被動推銷上（如：我有幾台貨車、多大的低溫倉儲），容易落入惡性的<span class="highlight">削價競標與硬體資產死拼</span>。</p>
                </div>
                <div class="info-card card-accent-blue">
                    <h3>AI 時代的新典範</h3>
                    <p>新一代物流行銷早已超越「把貨送好」的範疇。AI 技術的演進，賦予了物流商前所未有的「預測力、透明度與履約彈性」，轉化為能主動幫品牌主與消費者排除未知等待焦慮的<span class="highlight">「體驗型價值行銷」</span>。</p>
                </div>
            </div>
        </section>

        <!-- 四大維度對比 Section -->
        <section id="matrix" class="section-panel">
            <h1>新舊物流行銷對比矩陣</h1>
            <p class="section-desc">深入分析兩者在核心價值、數據應用、客戶體驗及永續敘事上的本質差異。</p>
            
            <table class="matrix-table">
                <thead>
                    <tr>
                        <th style="width: 20%;">比較維度</th>
                        <th style="width: 40%;">傳統物流行銷 (Legacy)</th>
                        <th style="width: 40%;">AI 時代物流行銷 (AI-Powered)</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td style="font-weight: bold; color: #fff;">核心賣點 (Value)</td>
                        <td><strong>被動承諾：</strong> 強調「準時、安全、便宜」，展示的是硬體設備與基礎 SLA。</td>
                        <td><strong>主動預測：</strong> 強調「彈性預測、動態履約、黑天鵝免疫力」，展現供應鏈韌性。</td>
                    </tr>
                    <tr>
                        <td style="font-weight: bold; color: #fff;">數據應用 (Data)</td>
                        <td><strong>後驗式歷史報告：</strong> 提供落後的年度到貨率、營收數據，偏向靜態的實力證明。</td>
                        <td><strong>即時預測型展示：</strong> 結合「需求感測（Demand Sensing）」，在痛點發生前精準投放解決方案。</td>
                    </tr>
                    <tr>
                        <td style="font-weight: bold; color: #fff;">客戶體驗 (CX)</td>
                        <td><strong>單向被動告知：</strong> 提供 Tracking ID 查單編號，有問才答，缺乏消除等待焦慮的同理心。</td>
                        <td><strong>AI Agent 智能共感：</strong> 利用生成式 AI 助理即時主動推播關務、異常警示與最優替代路徑。</td>
                    </tr>
                    <tr>
                        <td style="font-weight: bold; color: #fff;">品牌永續 (ESG)</td>
                        <td><strong>口號環保：</strong> 停留在改用電子發票、配合種樹等邊緣化且無法量化的環保包裝（Greenwashing）。</td>
                        <td><strong>數據化綠色競爭力：</strong> 即時優化低碳路徑，提供清晰的「範疇三」減碳數據儀表板，幫客戶省關稅。</td>
                    </tr>
                </tbody>
            </table>
        </section>

        <!-- 市場趨勢圖表 Section -->
        <section id="trends" class="section-panel">
            <h1>AI 物流行銷技術投資與效益趨勢</h1>
            <p class="section-desc">透過動態可視化圖表觀察全球企業轉向預測性物流後的指標增長。</p>
            
            <div class="chart-container">
                <div class="chart-header">
                    <div class="chart-title">2021 - 2026 企業行銷溢價與客戶留存效益曲線 (指標指數)</div>
                    <div class="chart-legend">
                        <div class="legend-item"><div class="legend-dot-pink"></div>傳統模式效益</div>
                        <div class="legend-item"><div class="legend-dot-blue"></div>AI 預測物流效益</div>
                    </div>
                </div>
                <!-- SVG Line Chart Component -->
                <svg viewBox="0 0 800 350" width="100%" height="100%" style="background: rgba(0,0,0,0.1); border-radius: 4px;">
                    <!-- Grid Lines -->
                    <line x1="50" y1="50" x2="750" y2="50" stroke="rgba(255,255,255,0.05)" stroke-width="1" />
                    <line x1="50" y1="125" x2="750" y2="125" stroke="rgba(255,255,255,0.05)" stroke-width="1" />
                    <line x1="50" y1="200" x2="750" y2="200" stroke="rgba(255,255,255,0.05)" stroke-width="1" />
                    <line x1="50" y1="275" x2="750" y2="275" stroke="rgba(255,255,255,0.05)" stroke-width="1" />
                    
                    <!-- Axis -->
                    <line x1="50" y1="300" x2="750" y2="300" stroke="var(--border-color)" stroke-width="2" />
                    <line x1="50" y1="30" x2="50" y2="300" stroke="var(--border-color)" stroke-width="2" />
                    
                    <!-- X Axis Labels -->
                    <text x="50" y="325" fill="var(--text-muted)" font-size="12" text-anchor="middle">2021</text>
                    <text x="190" y="325" fill="var(--text-muted)" font-size="12" text-anchor="middle">2022</text>
                    <text x="330" y="325" fill="var(--text-muted)" font-size="12" text-anchor="middle">2023</text>
                    <text x="470" y="325" fill="var(--text-muted)" font-size="12" text-anchor="middle">2024</text>
                    <text x="610" y="325" fill="var(--text-muted)" font-size="12" text-anchor="middle">2025</text>
                    <text x="750" y="325" fill="var(--text-muted)" font-size="12" text-anchor="middle">2026</text>

                    <!-- Legacy Trend Line (Pink) -->
                    <path d="M 50 220 L 190 230 L 330 240 L 470 255 L 610 260 L 750 270" fill="none" stroke="var(--neon-pink)" stroke-width="3" stroke-dasharray="4" />
                    <circle cx="750" cy="270" r="4" fill="var(--neon-pink)" />
                    
                    <!-- AI Era Trend Line (Cyan) -->
                    <path d="M 50 200 L 190 170 L 330 130 L 470 90 L 610 60 L 750 45" fill="none" stroke="var(--neon-blue)" stroke-width="4" />
                    <circle cx="750" cy="45" r="5" fill="var(--neon-blue)" />
                </svg>
            </div>
        </section>

        <!-- 實例深度解析 Section -->
        <section id="cases" class="section-panel">
            <h1>頂尖標竿企業實例 (Case Studies)</h1>
            <p class="section-desc">解析國內外領導品牌如何藉由 AI 供應鏈算力顛覆傳統行銷模式。</p>
            
            <div class="dashboard-grid">
                <div class="info-card">
                    <h3>Amazon 預測式發貨</h3>
                    <p>亞馬遜的 AI 模型會分析用戶的瀏覽歷史、購物車停留時間與氣象數據。在用戶甚至<span class="highlight">尚未點擊購買按鈕之前</span>，AI 就已經通知物流車隊將商品提前送往距離該客群最近的衛星倉儲，將出貨時間壓縮至極致。這不是後勤，這是利用極致交付速度打造的「驚艷體驗行銷」。</p>
                </div>
                <div class="info-card">
                    <h3>全聯福利中心 智慧補貨機制</h3>
                    <p>當颱風侵襲或中元大促時，傳統物流往往需要各店長回報才調度，錯失黃金商機。全聯自動化物流中心導入 AI 需求感測（Demand Sensing），與中央氣象數據深度連動，自動精算搶購潮並提前佈局車隊。讓消費者在惡劣天氣走到店內依然有滿滿商品可買，完美建立<span class="highlight">「關鍵時刻，全聯都在」</span>的品牌依賴。支援品牌最高階的行為行銷。</p>
                </div>
            </div>
        </section>

    </main>

    <script>
        // Tab / Panel Switch Logic
        function showPanel(panelId) {
            // Hide all sections
            document.querySelectorAll('.section-panel').forEach(panel => {
                panel.classList.remove('active');
            });
            
            // Remove active style from menu links
            document.querySelectorAll('.sidebar-menu li a').forEach(link => {
                link.classList.remove('active');
            });

            // Active current section & button
            document.getElementById(panelId).classList.add('active');
            event.currentTarget.classList.add('active');
        }
    </script>
</body>
</html>
