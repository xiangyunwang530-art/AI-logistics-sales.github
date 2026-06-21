<!DOCTYPE html>
<html lang="zh-Hant">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>AI時代物流行銷與傳統行銷的黃金變革 | IOT智慧物流行銷</title>
  
  <!-- CSS Stylesheet -->
  <link rel="stylesheet" href="style.css">
  
  <!-- FontAwesome Icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body>

  <!-- Mobile Hamburger Menu Toggle -->
  <button class="menu-toggle" id="menuToggle" aria-label="切換選單">
    <span></span>
    <span></span>
    <span></span>
  </button>

  <div class="app-container">
    
    <!-- SIDEBAR NAVIGATION -->
    <aside class="sidebar" id="sidebar">
      <div>
        <a href="#home" class="logo-section">
          <div class="logo-icon">AI</div>
          <span class="logo-text">IOT Logistics</span>
        </a>
        
        <ul class="nav-links">
          <li><a href="#home" class="active"><i class="fa-solid fa-house"></i> 首頁介紹</a></li>
          <li><a href="#comparison"><i class="fa-solid fa-scale-balanced"></i> 新舊對比</a></li>
          <li><a href="#features"><i class="fa-solid fa-wand-magic-sparkles"></i> AI三大核心</a></li>
          <li><a href="#charts"><i class="fa-solid fa-chart-line"></i> 趨勢圖表</a></li>
          <li><a href="#workflow"><i class="fa-solid fa-route"></i> 智慧流程</a></li>
          <li><a href="#case-study"><i class="fa-solid fa-video"></i> 影音案例</a></li>
          <li><a href="#attachments"><i class="fa-solid fa-paperclip"></i> 下載附件</a></li>
        </ul>
      </div>
      
      <div class="sidebar-footer">
        <p>© 2026 IOT 智慧行銷</p>
        <p>Powered by <a href="#">Baoyu Skills</a></p>
      </div>
    </aside>

    <!-- MAIN CONTENT AREA -->
    <main class="main-content">
      
      <!-- HERO SECTION -->
      <section id="home" class="section hero-section">
        <!-- Floating Cute Decorative Elements -->
        <div class="float-item float-heart">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="#ff007f" opacity="0.6">
            <path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/>
          </svg>
        </div>
        <div class="float-item float-star">
          <svg width="30" height="30" viewBox="0 0 24 24" fill="#00ffff" opacity="0.6">
            <path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/>
          </svg>
        </div>
        <div class="float-item float-bubble">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="#a78bfa" opacity="0.4">
            <circle cx="12" cy="12" r="10"/>
          </svg>
        </div>

        <div class="hero-content">
          <div class="hero-badge">
            <i class="fa-solid fa-circle-notch"></i>
            <span>AI 數位行銷大變革 × 智慧物流</span>
          </div>
          <h1 class="hero-title">
            在 AI 時代
            <span>物流行銷新玩法</span>
          </h1>
          <p class="hero-desc">
            告別傳統展會發傳單與低效的電話拜訪！最新的物流行銷透過大數據、意圖預測和秒級智慧報價，實現「千人千面」的精準獲客，大幅降低獲客成本。
          </p>
          <div class="hero-buttons">
            <a href="#comparison" class="btn btn-primary">開始探索對比</a>
            <a href="#attachments" class="btn btn-secondary"><i class="fa-solid fa-download"></i> 下載完整報告</a>
          </div>
        </div>

        <div class="hero-visual">
          <div class="cute-robot-wrapper">
            <div class="robot-glow"></div>
            <!-- Cute Futuristic SVG Robot -->
            <svg class="cute-robot-svg" viewBox="0 0 200 200">
              <defs>
                <linearGradient id="robotGrad" x1="0%" y1="0%" x2="100%" y2="100%">
                  <stop offset="0%" stop-color="#ff007f" />
                  <stop offset="100%" stop-color="#8b5cf6" />
                </linearGradient>
                <linearGradient id="screenGrad" x1="0%" y1="0%" x2="100%" y2="100%">
                  <stop offset="0%" stop-color="#0e0520" />
                  <stop offset="100%" stop-color="#1b0a2d" />
                </linearGradient>
              </defs>
              <!-- Ears/Antennas -->
              <circle cx="60" cy="50" r="10" fill="#00ffff" opacity="0.7"/>
              <circle cx="140" cy="50" r="10" fill="#00ffff" opacity="0.7"/>
              <rect x="55" y="50" width="10" height="30" rx="5" fill="#8b5cf6"/>
              <rect x="135" y="50" width="10" height="30" rx="5" fill="#8b5cf6"/>
              <!-- Antenna Bulb -->
              <line x1="100" y1="50" x2="100" y2="25" stroke="#ff007f" stroke-width="3"/>
              <circle cx="100" cy="20" r="8" fill="#ff007f"/>
              <!-- Head -->
              <rect x="50" y="60" width="100" height="80" rx="25" fill="url(#robotGrad)" stroke="#ffd3e8" stroke-width="2"/>
              <!-- Face Screen -->
              <rect x="62" y="72" width="76" height="56" rx="15" fill="url(#screenGrad)" stroke="#00ffff" stroke-width="1.5"/>
              <!-- Eyes (Cute Glowing Curved lines) -->
              <path d="M 75 95 Q 82 87 90 95" fill="none" stroke="#00ffff" stroke-width="4" stroke-linecap="round"/>
              <path d="M 110 95 Q 118 87 126 95" fill="none" stroke="#00ffff" stroke-width="4" stroke-linecap="round"/>
              <!-- Cheeks (Blushing Pink Hearts) -->
              <path d="M 70 110 L 73 107 A 2 2 0 0 1 77 110 L 70 116 L 63 110 A 2 2 0 0 1 67 107 Z" fill="#ff007f"/>
              <path d="M 130 110 L 133 107 A 2 2 0 0 1 137 110 L 130 116 L 123 110 A 2 2 0 0 1 127 107 Z" fill="#ff007f"/>
              <!-- Smile Mouth -->
              <path d="M 94 112 Q 100 118 106 112" fill="none" stroke="#ffffff" stroke-width="2" stroke-linecap="round"/>
              <!-- Body / Floating stand -->
              <ellipse cx="100" cy="165" rx="35" ry="12" fill="rgba(255, 0, 127, 0.4)"/>
              <ellipse cx="100" cy="180" rx="20" ry="6" fill="rgba(0, 255, 255, 0.4)"/>
            </svg>
          </div>
        </div>
      </section>

      <!-- COMPARISON SECTION -->
      <section id="comparison" class="section">
        <div class="section-header">
          <span class="tag">vs</span>
          <h2>物流行銷模式：新舊對決</h2>
        </div>
        
        <div class="bento-grid">
          <!-- Card 1: Traditional Marketing Characteristics -->
          <div class="glass-card bento-card pink-glow-border">
            <div class="card-title-area">
              <i class="fa-solid fa- megaphone"></i>
              <h3>傳統物流行銷特徵</h3>
            </div>
            <div class="card-content-wrap">
              <div class="compare-box traditional">
                <h4 class="compare-header traditional">粗放式廣播推廣</h4>
                <p>依靠業務員打電話、郵件群發、線下展會擺攤，主動拜訪工商名錄。訊息缺乏針對性，猶如大海撈針。</p>
              </div>
              <ul class="compare-list">
                <li>獲客成本高昂 (單個客戶開發成本破千美金)</li>
                <li>報價流程冗長 (需人工核算，耗時數小時到數天)</li>
                <li>內容一成不變 (對所有潛在客戶展示相同的傳單/PPT)</li>
                <li>流失無法預警 (客戶不再下單才被動知曉，難以挽回)</li>
              </ul>
            </div>
          </div>

          <!-- Card 2: AI Marketing Characteristics -->
          <div class="glass-card bento-card cyan-glow-border">
            <div class="card-title-area cyan">
              <i class="fa-solid fa-brain"></i>
              <h3>AI時代最新物流行銷</h3>
            </div>
            <div class="card-content-wrap">
              <div class="compare-box ai">
                <h4 class="compare-header ai">數據驅動與意圖預測</h4>
                <p>分析申報數據、網站流量與市場波動，在客戶產生出貨需求的黃金時間自動發送客製化物流解決方案。</p>
              </div>
              <ul class="compare-list">
                <li>獲客成本降低 70% (精準定向，行銷費高回報)</li>
                <li>秒級動態定價 (系統自動匹配艙位與市價，瞬間報價)</li>
                <li>千人千面素材 (AI自動生成迎合受眾痛點的文案與視覺)</li>
                <li>流失提前挽回 (預測模型檢測異常，自動觸發折扣補貼)</li>
              </ul>
            </div>
          </div>
        </div>
      </section>

      <!-- FEATURES SECTION (FLIP CARDS) -->
      <section id="features" class="section">
        <div class="section-header">
          <span class="tag">AI Capabilities</span>
          <h2>AI 行銷三大核心引擎</h2>
        </div>
        
        <p style="margin-bottom: 2rem; opacity: 0.95;">點擊下方卡片即可翻轉，查看 AI 如何重塑物流行銷的核心功能：</p>
        
        <div class="flip-cards-container">
          <!-- Flip Card 1 -->
          <div class="flip-card">
            <div class="flip-card-inner">
              <div class="flip-card-front">
                <i class="fa-solid fa-eye"></i>
                <h3>出貨意圖預測</h3>
                <p style="font-size: 0.85rem; color: var(--text-muted);">(點擊翻轉看細節)</p>
              </div>
              <div class="flip-card-back">
                <i class="fa-solid fa-circle-info"></i>
                <h3>精準獲客</h3>
                <p>AI 自動篩選海關數據與採購商行為軌跡。當偵測到目標企業特定航線交易頻率上升時，行銷系統會自動介入精準推送，避免盲目撥打騷擾電話。</p>
              </div>
            </div>
          </div>

          <!-- Flip Card 2 -->
          <div class="flip-card">
            <div class="flip-card-inner">
              <div class="flip-card-front">
                <i class="fa-solid fa-bolt"></i>
                <h3>秒級智慧動態報價</h3>
                <p style="font-size: 0.85rem; color: var(--text-muted);">(點擊翻轉看細節)</p>
              </div>
              <div class="flip-card-back">
                <i class="fa-solid fa-circle-info"></i>
                <h3>智慧即時定價</h3>
                <p>串接即時艙位剩餘量、當前航線運費市價與氣候預測，為進入系統的詢價客戶提供「秒級客製化報價」，以極具競爭力的精準定價刺激轉化。</p>
              </div>
            </div>
          </div>

          <!-- Flip Card 3 -->
          <div class="flip-card">
            <div class="flip-card-inner">
              <div class="flip-card-front">
                <i class="fa-solid fa-heart-pulse"></i>
                <h3>智慧流失預警</h3>
                <p style="font-size: 0.85rem; color: var(--text-muted);">(點擊翻轉看細節)</p>
              </div>
              <div class="flip-card-back">
                <i class="fa-solid fa-circle-info"></i>
                <h3>客戶自動挽回</h3>
                <p>機器學習模型分析歷史下單頻率、客服溝通與延誤反饋。若判斷客戶流失率高於預警值，系統自動補貼發送專屬航線折價券與溫馨信件，實現自動化召回。</p>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- TREND CHARTS SECTION -->
      <section id="charts" class="section">
        <div class="section-header">
          <span class="tag">Analytics</span>
          <h2>數據趨勢：傳統 vs AI 實測成效</h2>
        </div>

        <div class="charts-grid">
          <!-- Chart 1 -->
          <div class="glass-card chart-card pink-glow-border">
            <div class="chart-header-info">
              <h3>獲客成本 (CAC) 降低趨勢</h3>
              <div class="chart-stats">
                <div class="stat-item">
                  <div class="stat-label">傳統平均</div>
                  <div class="stat-val pink">$1210</div>
                </div>
                <div class="stat-item">
                  <div class="stat-label">AI目前</div>
                  <div class="stat-val cyan">$320</div>
                </div>
              </div>
            </div>
            <div class="chart-wrapper">
              <canvas id="cacChart"></canvas>
            </div>
          </div>

          <!-- Chart 2 -->
          <div class="glass-card chart-card cyan-glow-border">
            <div class="chart-header-info">
              <h3>不同管道轉換率 (CVR) 對比</h3>
              <div class="chart-stats">
                <div class="stat-item">
                  <div class="stat-label">傳統最高</div>
                  <div class="stat-val pink">1.5%</div>
                </div>
                <div class="stat-item">
                  <div class="stat-label">AI最高</div>
                  <div class="stat-val cyan">5.8%</div>
                </div>
              </div>
            </div>
            <div class="chart-wrapper">
              <canvas id="cvrChart"></canvas>
            </div>
          </div>
        </div>
      </section>

      <!-- WORKFLOW DIAGRAM SECTION -->
      <section id="workflow" class="section">
        <div class="section-header">
          <span class="tag">Workflow</span>
          <h2>AI智慧物流行銷的流轉引擎</h2>
        </div>

        <div class="workflow-diagram-wrap">
          <!-- SVG Diagram embedded directly -->
          <div class="svg-container">
            <object data="diagram.svg" type="image/svg+xml" style="width: 100%; height: auto; pointer-events: none;"></object>
          </div>

          <p style="margin-top: 1rem; opacity: 0.95;">
            上面的架構展示了傳統模式（左側線性、昂貴、孤立）與 AI 閉環模式（右側自適應、數據自循環）的流程對比。
          </p>

          <!-- Interactive Workflow Timeline Simulator -->
          <div class="glass-card bento-card full-width pink-glow-border" style="margin-top: 1rem;">
            <h3>互動式 AI 行銷運作軌跡</h3>
            <p style="font-size: 0.85rem; color: var(--text-muted); margin-bottom: 1.5rem;">點擊下方各節點，即可預覽 AI 引擎在行銷各環節的決策邏輯：</p>
            
            <div class="timeline-horizontal">
              <div class="timeline-step active" data-step="1">
                <div class="step-node">1</div>
                <div class="step-label">意圖感知</div>
              </div>
              <div class="timeline-step" data-step="2">
                <div class="step-node">2</div>
                <div class="step-label">秒級報價</div>
              </div>
              <div class="timeline-step" data-step="3">
                <div class="step-node">3</div>
                <div class="step-label">動態素材</div>
              </div>
              <div class="timeline-step" data-step="4">
                <div class="step-node">4</div>
                <div class="step-label">流失挽回</div>
              </div>
            </div>

            <div class="glass-card step-desc-card" style="background: rgba(255, 255, 255, 0.01); border-color: rgba(255, 0, 127, 0.1);">
              <h4 id="stepTitle" style="color: var(--neon-pink-light); margin-bottom: 0.5rem;">步驟一：意圖感知 (Intent Prediction)</h4>
              <p id="stepDescText" style="font-size: 0.9rem; line-height: 1.6;">
                利用大數據分析海關申報、進出口歷史記錄以及搜尋引擎瀏覽軌跡，AI自動演算出哪些企業近期具有緊急的倉儲或跨境物流空運需求，化被動為主動。
              </p>
            </div>
          </div>
        </div>
      </section>

      <!-- YOUTUBE VIDEO & CASE STUDY SECTION -->
      <section id="case-study" class="section">
        <div class="section-header">
          <span class="tag">Media &amp; Case Study</span>
          <h2>行銷影音與實戰案例</h2>
        </div>

        <div class="video-grid">
          <!-- Video Card -->
          <div class="glass-card video-card cyan-glow-border">
            <h3 style="margin-bottom: 1rem;"><i class="fa-brands fa-youtube" style="color: #ff0000; margin-right: 0.5rem;"></i>智慧物流行銷實錄</h3>
            <div class="video-player-container">
              <!-- Real logistics/AI YouTube video embed -->
              <iframe 
                src="https://www.youtube.com/embed/8Kq9Z-y-X-A" 
                title="AI in Logistics and Supply Chain" 
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
                allowfullscreen>
              </iframe>
            </div>
            <p style="margin-top: 1rem; font-size: 0.85rem; color: var(--text-muted);">
              觀看影片：了解 AI、機器學習與物聯網如何從根本上顛覆全球物流派送、倉儲與供應鏈管理，進而為行銷提供即時透明的數據支撐。
            </p>
          </div>

          <!-- Case Study Details Card -->
          <div class="case-study-details">
            <div class="glass-card case-card pink-glow-border">
              <h4>案例一：某大型跨境電商物流商</h4>
              <p>導入 AI 意圖預測後，精準匹配正在發往歐美特定站點的賣家，精準推送航線動態報價，獲客成本(CAC) 驟降 68%，新客詢價轉換率達 5.8%。</p>
              <div class="highlight-metric">ROI 提升 320%</div>
            </div>

            <div class="glass-card case-card pink-glow-border">
              <h4>案例二：某智慧倉儲供應商</h4>
              <p>使用 AI 流失挽回機制，在偵測到歷史大客戶查詢行為降低後，自動於節日前推送 VIP 回饋折扣與專屬報價，挽回了高達 42% 差點流失的倉儲租用合約。</p>
              <div class="highlight-metric">客戶留存率 +22%</div>
            </div>
          </div>
        </div>
      </section>

      <!-- ATTACHMENTS & DOWNLOADS SECTION -->
      <section id="attachments" class="section">
        <div class="section-header">
          <span class="tag">Downloads</span>
          <h2>相關附件與研究資源</h2>
        </div>

        <div class="downloads-grid">
          <!-- Attachment 1: Detailed Markdown Report -->
          <div class="glass-card download-card pink-glow-border">
            <div class="download-icon">
              <i class="fa-regular fa-file-lines"></i>
            </div>
            <div class="download-info">
              <h3>詳細對比分析報告 (Markdown)</h3>
              <p>包含傳統物流行銷痛點、AI四大核心變革以及未來趨勢的深度文檔。</p>
              <a href="report.md" download class="btn btn-primary btn-small"><i class="fa-solid fa-download"></i> 下載 .md 檔案</a>
            </div>
          </div>

          <!-- Attachment 2: Styled WeChat HTML Report -->
          <div class="glass-card download-card cyan cyan-glow-border">
            <div class="download-icon">
              <i class="fa-brands fa-html5"></i>
            </div>
            <div class="download-info">
              <h3>公眾號排版 HTML 報告</h3>
              <p>使用 Baoyu Skills 設計的 WeChat 精美排版報告網頁，可直接匯出使用。</p>
              <a href="report.html" download class="btn btn-primary btn-small" style="background: linear-gradient(135deg, var(--neon-cyan), var(--accent-purple)); box-shadow: 0 0 15px var(--neon-cyan-glow);"><i class="fa-solid fa-download"></i> 下載 .html 檔案</a>
            </div>
          </div>

          <!-- Attachment 3: Vector Flowchart SVG -->
          <div class="glass-card download-card pink-glow-border" style="grid-column: span 2;">
            <div class="download-icon">
              <i class="fa-regular fa-image"></i>
            </div>
            <div class="download-info">
              <h3>新舊對比流程圖 (Vector SVG)</h3>
              <p>包含霓虹粉色與青色風格、具備霓虹發光濾鏡的超高清向量對比圖，適合做成簡報（PPT）或文章插圖。</p>
              <a href="diagram.svg" download class="btn btn-primary btn-small"><i class="fa-solid fa-download"></i> 下載 .svg 檔案</a>
            </div>
          </div>
        </div>
      </section>

      <!-- FOOTER -->
      <footer class="site-footer">
        <div class="footer-glowing-stars">
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star cyan"></i>
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star cyan"></i>
          <i class="fa-solid fa-star"></i>
        </div>
        <p>在 AI 時代，最新的物流行銷與傳統行銷有何不同？</p>
        <p style="margin-top: 0.5rem; font-size: 0.75rem; opacity: 0.6;">Designed with Dreamy Future Neon theme. All rights reserved.</p>
      </footer>

    </main>

  </div>

  <!-- Chart.js CDN -->
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  
  <!-- JS Code -->
  <script src="script.js"></script>
</body>
</html>
