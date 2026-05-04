<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VANGUARD NEXUS | AI HUB</title>
    
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
        
        #auth-screen { font-family: 'Segoe UI', sans-serif; background-color: #c9d6ff; height: 100vh; width: 100%; position: fixed; z-index: 100000; display: flex; align-items: center; justify-content: center; }
        .auth-container { background-color: #fff; border-radius: 30px; box-shadow: 0 5px 15px rgba(0, 0, 0, 0.35); position: relative; overflow: hidden; width: 768px; max-width: 95%; min-height: 480px; }
        .form-container { position: absolute; top: 0; height: 100%; transition: all 0.6s ease-in-out; }
        .sign-in { left: 0; width: 50%; z-index: 2; }
        .auth-container.active .sign-in { transform: translateX(100%); }
        .sign-up { left: 0; width: 50%; opacity: 0; z-index: 1; }
        .auth-container.active .sign-up { transform: translateX(100%); opacity: 1; z-index: 5; animation: move 0.6s; }
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

        #dashboard { display: none; width: 96%; margin: 0 auto; gap: 1.8rem; grid-template-columns: 14rem auto 26rem; min-height: 100vh; }
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
        main .insights h3 { margin-top: 0.8rem; font-size: 0.85rem; font-family: 'VALORANT'; }
        .chart-container { background: var(--color-white); border-radius: var(--card-border-radius); padding: 1.5rem; margin-top: 2rem; box-shadow: var(--box-shadow); width: 100%; height: 300px; position: relative; }

        .right { margin-top: 1.4rem; }
        .ai-chat-modern { margin-top: 2rem; background: var(--color-white); padding: 1.5rem; border-radius: var(--card-border-radius); box-shadow: var(--box-shadow); height: 550px; display: flex; flex-direction: column; }
        .ai-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 1rem; padding-bottom: 0.5rem; border-bottom: 1px solid var(--color-light); }
        .ai-header h3 { font-family: 'VALORANT'; font-size: 1.1rem; color: var(--color-dark); }
        .model-select { background: var(--color-background); border: 1px solid var(--color-light); padding: 5px; border-radius: 5px; font-size: 0.8rem; }
        #ai-messages { flex: 1; overflow-y: auto; font-size: 0.85rem; margin-bottom: 1rem; display: flex; flex-direction: column; gap: 10px; }
        .msg-bubble { padding: 10px 15px; border-radius: 12px; max-width: 90%; }
        .msg-user { align-self: flex-end; background: var(--v-purple); color: white; border-bottom-right-radius: 2px; }
        .msg-ai { align-self: flex-start; background: var(--color-light); color: var(--color-dark); border-bottom-left-radius: 2px; }
        .msg-ai pre { background: #282c34; color: #abb2bf; padding: 10px; border-radius: 8px; overflow-x: auto; margin-top: 5px; }
        .chat-input-area { display: flex; gap: 0.5rem; border-top: 1px solid var(--color-light); padding-top: 1rem; }
        .chat-input-area input { width: 100%; background: var(--color-background); padding: 0.8rem; border-radius: 1rem; }

        #particle-overlay { display: none; position: fixed; inset: 0; background: #000; z-index: 500000; }
        #particle-canvas { display: block; }
        #particle-controls { position: absolute; top: 20px; right: 20px; background: rgba(0, 0, 0, 0.8); padding: 15px; border-radius: 8px; z-index: 10; width: 220px; color: white; }
        #particle-controls button { width: 100%; padding: 10px; background: #00aaff; border: none; color: white; cursor: pointer; margin-top: 10px; }

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
            <div class="chart-container"><canvas id="myChart"></canvas></div>
        </main>

        <div class="right">
            <div class="ai-chat-modern">
                <div class="ai-header">
                    <h3>AI ASİSTAN</h3>
                    <select id="aiModelSelector" class="model-select">
                        <option value="gemini">Gemini 1.5 Pro</option>
                        <option value="claude">Claude 4</option>
                    </select>
                </div>
                <div id="ai-messages">
                    <div class="msg-bubble msg-ai">Selam komutan, bugün ne yapıyoruz?</div>
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
            <h2>Görsel Ayarlar</h2>
            <button onclick="closeParticleMode()">DÖN</button>
        </div>
    </div>

    <script>
        // --- CONFIG & FIREBASE ---
        const API_KEY_GEMINI = "AIzaSyCMvVY2bdrAG3YzP7TfxLTdmh3Rlw5W3ZE";
        const config = { apiKey: "AIzaSyBC_h0zpRSSGdzcbtGsq3Bh2WGKAgTrNKc", authDomain: "vanguardnexus-a2871.firebaseapp.com", databaseURL: "https://vanguardnexus-a2871-default-rtdb.firebaseio.com", projectId: "vanguardnexus-a2871" };
        firebase.initializeApp(config); const db = firebase.database();

        // --- AUTH ---
        document.getElementById('registerBtn').addEventListener('click', () => document.getElementById('auth-container').classList.add("active"));
        document.getElementById('loginBtn').addEventListener('click', () => document.getElementById('auth-container').classList.remove("active"));
        function doLogin() { loginSuccess("ADMIN", true); }
        function doGuest() { loginSuccess("MİSAFİR", false); }
        function loginSuccess(u, vip) { document.getElementById("auth-screen").style.display = "none"; document.getElementById("dashboard").style.display = "grid"; initChart(); }

        // --- AI ASİSTAN ---
        async function askAI() {
            const input = document.getElementById('aiInput');
            const chat = document.getElementById('ai-messages');
            const model = document.getElementById('aiModelSelector').value;
            const text = input.value.trim();
            if(!text) return;

            chat.innerHTML += `<div class="msg-bubble msg-user">${text}</div>`;
            input.value = "";
            const loadId = "l-" + Date.now();
            chat.innerHTML += `<div id="${loadId}" class="msg-bubble msg-ai">Düşünüyor...</div>`;
            chat.scrollTop = chat.scrollHeight;

            try {
                if(model === "gemini") {
                    const res = await fetch(`https://generativelanguage.googleapis.com/v1beta/models/gemini-1.5-pro:generateContent?key=${API_KEY_GEMINI}`, {
                        method: "POST",
                        headers: { "Content-Type": "application/json" },
                        body: JSON.stringify({ contents: [{ parts: [{ text: text }] }] })
                    });
                    const data = await res.json();
                    const reply = data.candidates[0].content.parts[0].text;
                    document.getElementById(loadId).innerHTML = marked.parse(reply);
                } else {
                    document.getElementById(loadId).innerText = "Claude 4 için sunucu bağlantısı gerekiyor. Lütfen Gemini kullanın.";
                }
            } catch(e) { document.getElementById(loadId).innerText = "Hata! API anahtarını kontrol et."; }
            chat.scrollTop = chat.scrollHeight;
        }

        // --- DİĞER (Chart/Particle) ---
        function initChart() { const ctx = document.getElementById('myChart').getContext('2d'); new Chart(ctx, { type: 'line', data: { labels: [''], datasets: [{ label: 'Aktif', data: [0], borderColor: '#7380ec' }] } }); }
        function toggleMusic() { const m = document.getElementById('bgMusic'); m.paused ? m.play() : m.pause(); }
        window.onmousemove = e => { const g = document.getElementById('cursor-glow'); g.style.left = e.clientX+'px'; g.style.top = e.clientY+'px'; };
        
        function openParticleMode() { document.getElementById('particle-overlay').style.display = 'block'; }
        function closeParticleMode() { document.getElementById('particle-overlay').style.display = 'none'; }
    </script>
</body>
</html>
