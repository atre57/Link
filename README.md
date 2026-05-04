<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VANGUARD NEXUS AI | AI HUB</title>
    
    <link href="https://fonts.googleapis.com/icon?family=Material+Icons+Sharp" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.15.0/firebase-app-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.15.0/firebase-database-compat.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/marked/marked.min.js"></script>
    
    <style>
        @import url('https://fonts.cdnfonts.com/css/valorant');
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap');

        :root {
            --v-purple: #9333ea; --v-cyan: #00f2ff; --v-pink: #ff00ea;
            --color-primary: #7380ec; --color-danger: #ff7782; --color-success: #41f1b6;
            --color-warning: #ffbb55; --color-white: #fff; --color-info-dark: #7d8da1;
            --color-dark: #363949; --color-light: rgba(132, 139, 200, 0.18);
            --color-background: #f6f6f9; --card-border-radius: 2rem;
            --box-shadow: 0 2rem 3rem var(--color-light);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; text-decoration: none; list-style: none; border: 0; outline: none; }
        body { background: var(--color-background); overflow-x: hidden; font-family: 'Poppins', sans-serif; }
        
        /* --- AUTH SCREEN --- */
        #auth-screen {
            font-family: 'Segoe UI', sans-serif; background-color: #c9d6ff; height: 100vh; width: 100%;
            position: fixed; z-index: 100000; display: flex; align-items: center; justify-content: center;
        }
        .auth-container { background-color: #fff; border-radius: 30px; box-shadow: 0 5px 15px rgba(0, 0, 0, 0.35); position: relative; overflow: hidden; width: 768px; max-width: 95%; min-height: 480px; }
        .form-container { position: absolute; top: 0; height: 100%; transition: all 0.6s ease-in-out; }
        .sign-in { left: 0; width: 50%; z-index: 2; }
        .auth-container.active .sign-in { transform: translateX(100%); }
        .sign-up { left: 0; width: 50%; opacity: 0; z-index: 1; }
        .auth-container.active .sign-up { transform: translateX(100%); opacity: 1; z-index: 5; animation: move 0.6s; }
        @keyframes move { 0%, 49.99% { opacity: 0; z-index: 1; } 50%, 100% { opacity: 1; z-index: 5; } }
        form { background-color: #fff; display: flex; align-items: center; justify-content: center; flex-direction: column; padding: 0 40px; height: 100%; text-align: center; }
        .auth-input { background-color: #eee; border: none; margin: 8px 0; padding: 10px 15px; font-size: 13px; border-radius: 8px; width: 100%; }
        .auth-btn { background-color: var(--v-purple); color: #fff; font-size: 12px; padding: 10px 45px; border-radius: 8px; font-weight: 600; cursor: pointer; text-transform: uppercase; margin-top: 10px; }
        .toggle-container { position: absolute; top: 0; left: 50%; width: 50%; height: 100%; overflow: hidden; transition: all 0.6s ease-in-out; z-index: 1000; }
        .auth-container.active .toggle-container { transform: translateX(-100%); border-radius: 0 150px 100px 0; }
        .toggle { background: linear-gradient(to right, #5c67ff, var(--v-purple)); color: #fff; position: relative; left: -100%; height: 100%; width: 200%; transition: all 0.6s ease-in-out; }
        .auth-container.active .toggle { transform: translateX(50%); }
        .toggle-panel { position: absolute; width: 50%; height: 100%; display: flex; align-items: center; justify-content: center; flex-direction: column; padding: 0 30px; text-align: center; top: 0; transition: all 0.6s ease-in-out; }
        .toggle-left { transform: translateX(-200%); }
        .auth-container.active .toggle-left { transform: translateX(0); }
        .toggle-right { right: 0; }
        .auth-container.active .toggle-right { transform: translateX(200%); }

        /* --- DASHBOARD --- */
        #dashboard { 
            display: none; width: 96%; margin: 0 auto; gap: 1.8rem; grid-template-columns: 14rem auto 26rem; /* Sağ paneli biraz genişlettim */
            min-height: 100vh;
        }

        aside { height: 100vh; }
        aside .top { display: flex; align-items: center; justify-content: space-between; margin-top: 1.4rem; }
        aside .sidebar { display: flex; flex-direction: column; height: 86vh; position: relative; top: 3rem; }
        aside .sidebar a { display: flex; color: var(--color-info-dark); margin-left: 2rem; gap: 1rem; align-items: center; height: 3.7rem; transition: all 300ms ease; cursor: pointer; }
        aside .sidebar a span { font-size: 1.6rem; }
        aside .sidebar a.active { background: var(--color-light); color: var(--color-primary); margin-left: 0; }
        aside .sidebar a.active:before { content: ""; width: 6px; height: 100%; background: var(--color-primary); }
        aside .sidebar a:hover { color: var(--color-primary); }

        main { margin-top: 1.4rem; width: 100%; }
        main .insights { display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 1.2rem; }
        main .insights > div { background: var(--color-white); padding: 1.5rem; border-radius: var(--card-border-radius); box-shadow: var(--box-shadow); transition: 0.3s; cursor: pointer; text-align: center; }
        main .insights > div:hover { transform: scale(1.02); box-shadow: none; }
        main .insights h3 { margin-top: 0.8rem; font-size: 0.85rem; font-family: 'VALORANT'; }
        
        .chart-container { background: var(--color-white); border-radius: var(--card-border-radius); padding: 1.5rem; margin-top: 2rem; box-shadow: var(--box-shadow); width: 100%; height: 300px; position: relative; }

        /* --- AI ASSISTANT CHAT PANEL --- */
        .right { margin-top: 1.4rem; }
        .ai-chat-modern { margin-top: 2rem; background: var(--color-white); padding: 1.5rem; border-radius: var(--card-border-radius); box-shadow: var(--box-shadow); height: 550px; display: flex; flex-direction: column; }
        
        .ai-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 1rem; padding-bottom: 0.5rem; border-bottom: 1px solid var(--color-light); }
        .ai-header h3 { font-family: 'VALORANT'; font-size: 1.1rem; color: var(--color-dark); }
        .model-select { background: var(--color-background); border: 1px solid var(--color-light); padding: 5px 10px; border-radius: 5px; font-family: 'Poppins'; font-size: 0.8rem; outline: none; cursor: pointer; color: var(--color-dark); }
        
        #ai-messages { flex: 1; overflow-y: auto; font-size: 0.85rem; margin-bottom: 1rem; padding-right: 5px; display: flex; flex-direction: column; gap: 10px; }
        
        .msg-bubble { padding: 10px 15px; border-radius: 12px; max-width: 90%; line-height: 1.4; }
        .msg-user { align-self: flex-end; background: var(--v-purple); color: white; border-bottom-right-radius: 2px; }
        .msg-ai { align-self: flex-start; background: var(--color-light); color: var(--color-dark); border-bottom-left-radius: 2px; }
        .msg-ai pre { background: #282c34; color: #abb2bf; padding: 10px; border-radius: 8px; overflow-x: auto; margin-top: 5px; } /* Kod blokları için */
        
        .chat-input-area { display: flex; gap: 0.5rem; border-top: 1px solid var(--color-light); padding-top: 1rem; }
        .chat-input-area input { width: 100%; background: var(--color-background); padding: 0.8rem; border-radius: 1rem; color: var(--color-dark); }

        /* --- PARTICLE MORPH OVERLAY --- */
        #particle-overlay { display: none; position: fixed; inset: 0; background: #000; z-index: 500000; }
        #particle-canvas { display: block; }
        #particle-controls { position: absolute; top: 20px; right: 20px; background: rgba(0, 0, 0, 0.8); padding: 15px; border-radius: 8px; box-shadow: 0 0 15px rgba(0, 255, 255, 0.3); z-index: 10; width: 220px; color: white; font-size: 0.8rem; }
        #particle-controls input, #particle-controls select { width: 100%; margin-bottom: 10px; background: #333; color: white; border: none; padding: 5px; }
        #particle-controls button { width: 100%; padding: 10px; background: #00aaff; border: none; color: white; cursor: pointer; margin-top: 5px; }
        #exit-particle { background: #ff4444 !important; }

        /* Responsive */
        @media screen and (max-width: 992px) { #dashboard { grid-template-columns: 1fr; } aside { display: none; } }
        @media screen and (max-width: 600px) { main .insights { grid-template-columns: 1fr; } }

        #cursor-glow { position: fixed; width: 300px; height: 300px; background: radial-gradient(circle, rgba(115, 128, 236, 0.1) 0%, transparent 70%); pointer-events: none; z-index: 999999; transform: translate(-50%, -50%); }
    </style>
</head>
<body>

    <div id="cursor-glow"></div>
    <audio id="bgMusic" loop src="https://files.catbox.moe/97p877.mp3"></audio>

    <div id="auth-screen">
        <div class="auth-container" id="auth-container">
            <div class="form-container sign-up"><form><h1>Hesap Oluştur</h1><input type="text" id="rName" class="auth-input" placeholder="Kullanıcı Adı"><input type="password" id="rPass" class="auth-input" placeholder="Şifre"><button type="button" class="auth-btn" onclick="handleRegister()">KAYDOL</button></form></div>
            <div class="form-container sign-in"><form><h1>Giriş Yap</h1><input type="text" id="lName" class="auth-input" placeholder="Kullanıcı Adı"><input type="password" id="lPass" class="auth-input" placeholder="Şifre"><button type="button" class="auth-btn" onclick="doLogin()">GİRİŞ YAP</button><button type="button" class="auth-btn" onclick="doGuest()" style="background: #333; margin-top: 5px;">MİSAFİR</button></form></div>
            <div class="toggle-container"><div class="toggle"><div class="toggle-panel toggle-left"><h1>Hoşgeldin!</h1><button class="auth-btn" id="loginBtn">GİRİŞ YAP</button></div><div class="toggle-panel toggle-right"><h1>Selam!</h1><button class="auth-btn" id="registerBtn">KAYDOL</button></div></div></div>
        </div>
    </div>

    <div id="dashboard">
        <aside>
            <div class="top"><div class="logo"><h2 style="font-family:'VALORANT'; color:var(--v-purple)">NEXUS</h2></div></div>
            <div class="sidebar">
                <a class="active"><span class="material-icons-sharp">grid_view</span><h3>Dashboard</h3></a>
                <a onclick="openParticleMode()"><span class="material-icons-sharp">auto_fix_high</span><h3>Görsel Mod</h3></a>
                <a onclick="toggleMusic()"><span class="material-icons-sharp">music_note</span><h3 id="m-text">Müzik: Kapalı</h3></a>
                <a onclick="location.reload()"><span class="material-icons-sharp">logout</span><h3>Çıkış</h3></a>
            </div>
        </aside>

        <main>
            <h1>Sistem Paneli</h1>
            <div class="insights" id="main-grid">
                <div onclick="window.open('https://tracker.gg/valorant', '_blank')"><span class="material-icons-sharp" style="color:var(--v-cyan)">analytics</span><h3>STATÜ</h3></div>
                <div onclick="window.open('https://vcrdb.net/', '_blank')"><span class="material-icons-sharp" style="color:var(--v-cyan)">ads_click</span><h3>NİŞANGAH</h3></div>
                <div onclick="window.open('https://playvalorant.com/tr-tr/maps/', '_blank')"><span class="material-icons-sharp" style="color:var(--v-orange)">map</span><h3>HARİTALAR</h3></div>
                <div onclick="window.open('https://playvalorant.com/tr-tr/agents/', '_blank')"><span class="material-icons-sharp" style="color:var(--v-orange)">groups</span><h3>AJANLAR</h3></div>
            </div>
            <div class="chart-container">
                <h2 id="realtime-status" style="font-size: 0.9rem; margin-bottom: 0.5rem;">Aktivite...</h2>
                <canvas id="myChart"></canvas>
            </div>
        </main>

        <div class="right">
            <div class="ai-chat-modern">
                <div class="ai-header">
                    <h3>AI ASİSTAN</h3>
                    <select id="aiModelSelector" class="model-select">
                        <option value="gemini">Gemini 3 Pro</option>
                        <option value="claude">Claude 4</option>
                    </select>
                </div>
                
                <div id="ai-messages">
                    <div class="msg-bubble msg-ai">Hoş geldin, komutan. Sana nasıl yardımcı olabilirim?</div>
                </div>
                
                <div class="chat-input-area">
                    <input type="text" id="aiInput" placeholder="Yapay zekaya sor...">
                    <button onclick="askAI()" class="material-icons-sharp" style="color:var(--v-purple); background:none; cursor:pointer;">send</button>
                </div>
            </div>
        </div>
    </div>

    <div id="particle-overlay">
        <canvas id="particle-canvas"></canvas>
        <div id="particle-controls">
            <h2>Particle Ayarları</h2>
            <select id="shapeSelector">
                <option value="circle">Daire</option>
                <option value="heart">Kalp</option>
            </select>
            <input type="range" id="particleSize" min="0.5" max="3" step="0.1" value="1.5">
            <input type="color" id="particleColor" value="#00ffff">
            <input type="range" id="speed" min="0.01" max="0.2" step="0.01" value="0.08">
            <button id="exit-particle" onclick="closeParticleMode()">DASHBOARD'A DÖN</button>
        </div>
    </div>

    <script>
        // --- FIREBASE & AUTH LOGIC ---
        const config = { apiKey: "AIzaSyBC_h0zpRSSGdzcbtGsq3Bh2WGKAgTrNKc", authDomain: "vanguardnexus-a2871.firebaseapp.com", databaseURL: "https://vanguardnexus-a2871-default-rtdb.firebaseio.com", projectId: "vanguardnexus-a2871" };
        firebase.initializeApp(config); const db = firebase.database();
        
        document.getElementById('registerBtn').addEventListener('click', () => document.getElementById('auth-container').classList.add("active"));
        document.getElementById('loginBtn').addEventListener('click', () => document.getElementById('auth-container').classList.remove("active"));

        function doLogin() {
            const u = document.getElementById("lName").value.trim(), p = document.getElementById("lPass").value.trim();
            if(u === "ADMIN" && p === "1200778") { loginSuccess(u, true); return; }
            db.ref('users/'+u).once('value').then(s => {
                if(s.exists() && s.val().password === p) loginSuccess(u, s.val().isVip);
                else alert("Hata!");
            });
        }
        function loginSuccess(u, vip) {
            sessionStorage.setItem("user", u);
            document.getElementById("auth-screen").style.display = "none";
            document.getElementById("dashboard").style.display = "grid";
            initChart();
        }
        function doGuest() { loginSuccess("MİSAFİR", false); }

        // --- CHART & MUSIC ---
        let myChartInstance;
        function initChart() {
            const ctx = document.getElementById('myChart').getContext('2d');
            myChartInstance = new Chart(ctx, { type: 'line', data: { labels: [''], datasets: [{ label: 'Aktif', data: [0], borderColor: '#7380ec', fill: true }] }, options: { responsive: true, maintainAspectRatio: false } });
        }
        let isPlaying = false;
        function toggleMusic() { const m = document.getElementById('bgMusic'); isPlaying ? m.pause() : m.play(); document.getElementById('m-text').innerText = isPlaying ? "Müzik: Kapalı" : "Müzik: Çalıyor"; isPlaying = !isPlaying; }
        window.onmousemove = e => { const g = document.getElementById('cursor-glow'); g.style.left = e.clientX + 'px'; g.style.top = e.clientY + 'px'; };

        // --- PARTICLE LOGIC ---
        const pCanvas = document.getElementById('particle-canvas');
        const pCtx = pCanvas.getContext('2d');
        let particles = [], pAnimId;
        const numParticles = 3000, mouse = { x: null, y: null, radius: 150, active: false };

        function openParticleMode() { document.getElementById('particle-overlay').style.display = 'block'; pCanvas.width = window.innerWidth; pCanvas.height = window.innerHeight; initParticles(); }
        function closeParticleMode() { document.getElementById('particle-overlay').style.display = 'none'; cancelAnimationFrame(pAnimId); }

        class Particle {
            constructor() { this.x = Math.random() * pCanvas.width; this.y = Math.random() * pCanvas.height; this.destX = this.x; this.destY = this.y; this.size = 1.5; this.speed = 0.08; this.color = "#00ffff"; }
            draw() { pCtx.fillStyle = this.color; pCtx.beginPath(); pCtx.arc(this.x, this.y, this.size, 0, Math.PI * 2); pCtx.fill(); }
            update() {
                this.x += (this.destX - this.x) * this.speed; this.y += (this.destY - this.y) * this.speed;
                if (mouse.active) {
                    let dx = mouse.x - this.x, dy = mouse.y - this.y, dist = Math.sqrt(dx*dx + dy*dy);
                    if (dist < mouse.radius) { let f = (mouse.radius - dist) / mouse.radius; this.x -= (dx/dist) * f * 10; this.y -= (dy/dist) * f * 10; }
                }
            }
        }
        function initParticles() { particles = []; for (let i = 0; i < numParticles; i++) particles.push(new Particle()); updatePShape(document.getElementById('shapeSelector').value); animateP(); }
        function updatePShape(shape) {
            const cx = pCanvas.width / 2, cy = pCanvas.height / 2, scale = Math.min(pCanvas.width, pCanvas.height) * 0.35;
            particles.forEach((p, i) => {
                let t = (i / numParticles) * Math.PI * 2, x, y;
                if (shape === 'circle') { x = Math.cos(t) * scale; y = Math.sin(t) * scale; }
                else if (shape === 'heart') { x = 16 * Math.pow(Math.sin(t), 3); y = -(13 * Math.cos(t) - 5 * Math.cos(2*t) - 2 * Math.cos(3*t) - Math.cos(4*t)); x *= (scale/18); y *= (scale/18); }
                p.destX = cx + x; p.destY = cy + y;
            });
        }
        function animateP() { pCtx.fillStyle = 'rgba(0, 0, 0, 0.1)'; pCtx.fillRect(0, 0, pCanvas.width, pCanvas.height); particles.forEach(p => { p.update(); p.draw(); }); pAnimId = requestAnimationFrame(animateP); }
        pCanvas.addEventListener('mousemove', (e) => { mouse.x = e.x; mouse.y = e.y; mouse.active = true; });

        // === AI ASİSTAN ENTEGRASYONU ===
        
        // DİKKAT: API Anahtarlarını buraya yapıştırman gerekiyor!
        const API_KEYS = {
            gemini: "BURAYA_GEMINI_API_ANAHTARINI_YAZ", // Google AI Studio'dan alınacak
            claude: "BURAYA_CLAUDE_API_ANAHTARINI_YAZ" // Anthropic'ten alınacak (Tarayıcıda hata verebilir)
        };

        async function askAI() {
            const inputField = document.getElementById('aiInput');
            const chatBox = document.getElementById('ai-messages');
            const modelSelect = document.getElementById('aiModelSelector');
            const modelName = modelSelect.options[modelSelect.selectedIndex].text;
            const modelType = modelSelect.value;
            const userMsg = inputField.value.trim();

            if (!userMsg) return;

            // Kullanıcı mesajını ekle
            chatBox.innerHTML += `<div class="msg-bubble msg-user">${userMsg}</div>`;
            inputField.value = "";
            
            // Yükleniyor durumu ekle
            const loadId = "load-" + Date.now();
            chatBox.innerHTML += `<div id="${loadId}" class="msg-bubble msg-ai" style="font-style: italic;">${modelName} veri işliyor...</div>`;
            chatBox.scrollTop = chatBox.scrollHeight;

            try {
                let aiResponseText = "";
                
                if (modelType === "gemini") {
                    // Google Gemini API İsteği (Gemini 1.5 Pro kullanılıyor, Gemini 3 API'si yaygın kullanıma açılana kadar bu çalışır)
                    const res = await fetch(`https://generativelanguage.googleapis.com/v1beta/models/gemini-1.5-pro:generateContent?key=${API_KEYS.gemini}`, {
                        method: "POST",
                        headers: { "Content-Type": "application/json" },
                        body: JSON.stringify({ contents: [{ parts: [{ text: userMsg }] }] })
                    });
                    
                    const data = await res.json();
                    
                    if(data.error) throw new Error(data.error.message);
                    aiResponseText = data.candidates[0].content.parts[0].text;
                    
                } else if (modelType === "claude") {
                    // Claude 4 için simülasyon (CORS hatası almamak için)
                    aiResponseText = "Claude 4 modeli şu anda doğrudan tarayıcı üzerinden (Client-Side) istekleri güvenlik nedeniyle engellemektedir. Bunun çalışması için bir backend (sunucu) yazmanız gerekmektedir. Şimdilik Gemini'yi kullanabilirsiniz.";
                }

                // Yükleniyor mesajını kaldır ve AI yanıtını ekle. marked.parse ile kod blokları düzgün görünür.
                document.getElementById(loadId).remove();
                chatBox.innerHTML += `<div class="msg-bubble msg-ai"><b>${modelName}:</b><br>${marked.parse(aiResponseText)}</div>`;
                
            } catch (error) {
                document.getElementById(loadId).innerHTML = `<b>Hata:</b> Bağlantı kurulamadı veya API anahtarı eksik/hatalı.`;
                console.error("AI Error:", error);
            }
            
            chatBox.scrollTop = chatBox.scrollHeight;
        }

        // Enter tuşu dinleyicisi
        document.getElementById('aiInput').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') { askAI(); }
        });

    </script>
</body>
</html>
