<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NEXUS | AI HUB — Global Asistan Platformu</title>
    
    <link href="https://fonts.googleapis.com/icon?family=Material+Icons+Sharp" rel="stylesheet">
    <link href="https://fonts.cdnfonts.com/css/valorant" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">

    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.15.0/firebase-app-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.15.0/firebase-database-compat.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/marked/marked.min.js"></script>
    
    <style>
        :root {
            --v-purple: #9333ea;
            --v-cyan: #00f2ff;
            --v-pink: #ff00ea;
            --color-primary: #7380ec;
            --color-white: #fff;
            --color-info-dark: #7d8da1;
            --color-dark: #363949;
            --color-light: rgba(132, 139, 200, 0.18);
            --color-background: #f6f6f9;
            --color-success: #41f1b6;
            --card-border-radius: 1.5rem;
            --border-radius-1: 0.6rem;
            --box-shadow: 0 1.5rem 2rem var(--color-light);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; text-decoration: none; list-style: none; border: 0; outline: none; transition: all 300ms ease; }
        body { font-family: 'Poppins', sans-serif; font-size: 0.88rem; color: var(--color-dark); background-color: var(--color-background); overflow-x: hidden; }
        
        .valorant { font-family: 'VALORANT', sans-serif; letter-spacing: 2px; }

        /* --- AUTH EKRANI --- */
        #auth-wrapper { width: 100%; height: 100vh; position: fixed; top: 0; left: 0; background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%); display: flex; align-items: center; justify-content: center; z-index: 10000; }
        .auth-container { background: #fff; border-radius: 2rem; box-shadow: 0 10px 30px rgba(0,0,0,0.5); position: relative; overflow: hidden; width: 800px; max-width: 95%; min-height: 500px; }
        .form-container { position: absolute; top: 0; height: 100%; transition: all 0.6s ease-in-out; }
        .sign-in { left: 0; width: 50%; z-index: 2; }
        .auth-container.active .sign-in { transform: translateX(100%); }
        .sign-up { left: 0; width: 50%; opacity: 0; z-index: 1; }
        .auth-container.active .sign-up { transform: translateX(100%); opacity: 1; z-index: 5; }
        form { padding: 0 50px; height: 100%; display: flex; flex-direction: column; align-items: center; justify-content: center; text-align: center; }
        .auth-input { background: #f0f0f0; border-radius: 10px; padding: 12px 15px; margin: 8px 0; width: 100%; font-family: inherit; }
        .auth-btn { background: var(--v-purple); color: #fff; padding: 12px 45px; border-radius: 10px; font-weight: 600; cursor: pointer; margin-top: 15px; box-shadow: 0 4px 15px rgba(147, 51, 234, 0.3); }
        .auth-btn:hover { transform: translateY(-2px); box-shadow: 0 6px 20px rgba(147, 51, 234, 0.4); }

        .toggle-container { position: absolute; top: 0; left: 50%; width: 50%; height: 100%; overflow: hidden; transition: all 0.6s ease-in-out; z-index: 1000; }
        .auth-container.active .toggle-container { transform: translateX(-100%); border-radius: 0 150px 100px 0; }
        .toggle { background: linear-gradient(to bottom right, #6366f1, #9333ea); color: #fff; position: relative; left: -100%; height: 100%; width: 200%; }
        
        /* --- DASHBOARD --- */
        #dashboard-main { display: none; width: 96%; margin: 0 auto; gap: 1.5rem; }
        #dashboard-main.pc { grid-template-columns: 14rem auto 24rem; }
        #dashboard-main.tablet { grid-template-columns: 5rem auto; }
        #dashboard-main.phone { grid-template-columns: 1fr; margin-top: 4rem; }

        aside { height: 100vh; display: flex; flex-direction: column; }
        aside .sidebar { background: var(--color-white); border-radius: 1.5rem; margin-top: 1.5rem; box-shadow: var(--box-shadow); overflow: hidden; }
        aside .sidebar a { display: flex; align-items: center; color: var(--color-info-dark); height: 4rem; gap: 1rem; padding-left: 1.5rem; cursor: pointer; }
        aside .sidebar a.active { background: var(--color-light); color: var(--color-primary); border-left: 5px solid var(--color-primary); padding-left: calc(1.5rem - 5px); }
        aside .sidebar a:hover { background: var(--color-light); padding-left: 2rem; }

        main { padding-top: 1.5rem; }
        .insights { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 1.5rem; margin-bottom: 2rem; }
        .insights > div { background: var(--color-white); padding: 1.5rem; border-radius: var(--card-border-radius); box-shadow: var(--box-shadow); text-align: center; transition: 0.3s; }
        .insights > div:hover { transform: translateY(-5px); box-shadow: none; border: 1px solid var(--v-purple); }
        .v-icon { font-size: 2.5rem; color: var(--v-purple); margin-bottom: 0.5rem; }

        .config-panel { background: var(--color-white); padding: 1.5rem; border-radius: var(--card-border-radius); box-shadow: var(--box-shadow); }
        .key-input { display: flex; gap: 0.5rem; margin: 0.5rem 0 1.5rem; }
        .key-input input { flex: 1; padding: 0.8rem; background: var(--color-background); border-radius: var(--border-radius-1); border: 1px solid #ddd; }

        .right { padding-top: 1.5rem; }
        .ai-assistant { background: var(--color-white); border-radius: var(--card-border-radius); box-shadow: var(--box-shadow); height: calc(100vh - 3rem); display: flex; flex-direction: column; position: sticky; top: 1.5rem; }
        .ai-header { padding: 1.5rem; border-bottom: 1px solid var(--color-light); display: flex; justify-content: space-between; align-items: center; }
        #ai-messages { flex: 1; overflow-y: auto; padding: 1.5rem; display: flex; flex-direction: column; gap: 1rem; scroll-behavior: smooth; }
        
        .msg-bubble { padding: 0.8rem 1.2rem; border-radius: 1rem; max-width: 85%; font-size: 0.9rem; line-height: 1.4; }
        .msg-user { align-self: flex-end; background: var(--v-purple); color: white; border-bottom-right-radius: 0; }
        .msg-ai { align-self: flex-start; background: #f0f2f5; color: var(--color-dark); border-bottom-left-radius: 0; }
        
        .chat-input-area { padding: 1.5rem; border-top: 1px solid var(--color-light); display: flex; gap: 0.8rem; }
        .chat-input-area input { flex: 1; padding: 0.8rem 1.2rem; background: var(--color-background); border-radius: 2rem; }
        .chat-input-area button { color: var(--v-purple); background: none; font-size: 1.8rem; cursor: pointer; }

        #cursor-glow { position: fixed; width: 400px; height: 400px; background: radial-gradient(circle, rgba(147, 51, 234, 0.08) 0%, transparent 70%); pointer-events: none; z-index: 9999; transform: translate(-50%, -50%); }
    </style>
</head>
<body>

    <div id="cursor-glow"></div>

    <div id="auth-wrapper">
        <div class="auth-container" id="auth-container">
            <div class="form-container sign-up">
                <form id="registerForm">
                    <h1 class="valorant">KAYIT OL</h1>
                    <input type="text" id="rName" class="auth-input" placeholder="Kullanıcı Adı" autocomplete="off">
                    <input type="password" id="rPass" class="auth-input" placeholder="Şifre">
                    <button type="button" class="auth-btn" onclick="handleAuth('register')">HESAP OLUŞTUR</button>
                </form>
            </div>
            <div class="form-container sign-in">
                <form id="loginForm">
                    <h1 class="valorant" style="color: var(--v-purple); font-size: 2.5rem; margin-bottom: 1rem;">NEXUS</h1>
                    <input type="text" id="lName" class="auth-input" placeholder="Kullanıcı Adı" autocomplete="off">
                    <input type="password" id="lPass" class="auth-input" placeholder="Şifre">
                    <button type="button" class="auth-btn" onclick="handleAuth('login')">GİRİŞ YAP</button>
                    <button type="button" class="auth-btn" onclick="loginSuccess('MISAFIR', false)" style="background: #222;">MİSAFİR GİRİŞİ</button>
                </form>
            </div>
            <div class="toggle-container">
                <div class="toggle">
                    <div class="toggle-panel" style="position:absolute; left:0; width:50%; height:100%; display:flex; flex-direction:column; align-items:center; justify-content:center;">
                        <h2>Tekrar Hoşgeldin!</h2>
                        <button class="auth-btn" style="background:transparent; border: 2px solid #white;" onclick="document.getElementById('auth-container').classList.remove('active')">GİRİŞ YAP</button>
                    </div>
                    <div class="toggle-panel" style="position:absolute; right:0; width:50%; height:100%; display:flex; flex-direction:column; align-items:center; justify-content:center;">
                        <h2>Yeni misin?</h2>
                        <button class="auth-btn" style="background:transparent; border: 2px solid white;" onclick="document.getElementById('auth-container').classList.add('active')">KAYDOL</button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div id="dashboard-main" class="pc">
        <aside>
            <div style="padding: 1.5rem 0 0 1rem;">
                <h2 class="valorant" style="color: var(--v-purple);">NEXUS HUB</h2>
            </div>
            <div class="sidebar">
                <a class="active"><span class="material-icons-sharp">auto_awesome</span><h3>AI Asistan</h3></a>
                <a><span class="material-icons-sharp">insights</span><h3>Analizler</h3></a>
                <a><span class="material-icons-sharp">settings</span><h3>Ayarlar</h3></a>
                <a onclick="location.reload()" style="margin-top: 2rem; color: #ff7782;"><span class="material-icons-sharp">logout</span><h3>Güvenli Çıkış</h3></a>
            </div>
            
            <div style="margin-top: auto; padding: 1rem; background: var(--color-white); border-radius: 1rem; margin-bottom: 1rem;">
                <h4 class="valorant" style="font-size: 0.6rem; margin-bottom: 0.5rem;">GÖRÜNÜM</h4>
                <div style="display:flex; justify-content: space-around;">
                    <span class="material-icons-sharp" style="cursor:pointer" onclick="setScreenMode('phone')">smartphone</span>
                    <span class="material-icons-sharp" style="cursor:pointer" onclick="setScreenMode('tablet')">tablet</span>
                    <span class="material-icons-sharp" style="cursor:pointer" onclick="setScreenMode('pc')">computer</span>
                </div>
            </div>
        </aside>

        <main>
            <h1 class="valorant" style="font-size: 1.4rem;">OPERASYON MERKEZİ</h1>
            <div class="insights">
                <div>
                    <span class="material-icons-sharp v-icon">psychology</span>
                    <h3>ZEKA</h3>
                    <p style="font-size: 0.7rem; color: var(--color-info-dark);">Model: Gemini 1.5 Pro</p>
                </div>
                <div>
                    <span class="material-icons-sharp v-icon">code</span>
                    <h3>GELİŞTİRİCİ</h3>
                    <p style="font-size: 0.7rem; color: var(--color-info-dark);">Kod Analizi Aktif</p>
                </div>
                <div>
                    <span class="material-icons-sharp v-icon">verified_user</span>
                    <h3>VIP DURUMU</h3>
                    <p id="vip-status-text" style="font-size: 0.7rem; color: var(--color-success);">Aktif Değil</p>
                </div>
            </div>

            <div class="config-panel">
                <h2 class="valorant" style="font-size: 1rem; margin-bottom: 1rem;">API YAPILANDIRMASI</h2>
                <label>Gemini API Anahtarı</label>
                <div class="key-input">
                    <input type="password" id="geminiKeyInp" placeholder="AIzaSy...">
                    <button class="auth-btn" style="margin-top:0;" onclick="saveApiKey('gemini')">KAYDET</button>
                </div>
                <label>Claude API Anahtarı (Opsiyonel)</label>
                <div class="key-input">
                    <input type="password" id="claudeKeyInp" placeholder="sk-ant-...">
                    <button class="auth-btn" style="margin-top:0;" onclick="saveApiKey('claude')">KAYDET</button>
                </div>
                <p style="font-size: 0.7rem; color: var(--color-info-dark);">* Anahtarlar yerel depolamada (LocalStorage) şifresiz tutulur. Güvenliğiniz için kendi cihazınızda kullanın.</p>
            </div>
        </main>

        <div class="right">
            <div class="ai-assistant">
                <div class="ai-header">
                    <h3 class="valorant">NEXUS AI</h3>
                    <select id="aiModelSelector" style="background: var(--color-background); padding: 5px; border-radius: 5px;">
                        <option value="gemini">Gemini Pro</option>
                        <option value="claude">Claude 3 (Simüle)</option>
                    </select>
                </div>
                <div id="ai-messages">
                    <div class="msg-bubble msg-ai">Sistem çevrimiçi. Komutlarınızı bekliyorum.</div>
                </div>
                <div class="chat-input-area">
                    <input type="text" id="aiInput" placeholder="Bir mesaj yazın...">
                    <button onclick="askAI()"><span class="material-icons-sharp">send</span></button>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Firebase & Başlangıç Ayarları
        const dbConfig = { apiKey: "AIzaSyBC_h0zpRSSGdzcbtGsq3Bh2WGKAgTrNKc", authDomain: "vanguardnexus-a2871.firebaseapp.com", databaseURL: "https://vanguardnexus-a2871-default-rtdb.firebaseio.com", projectId: "vanguardnexus-a2871" };
        firebase.initializeApp(dbConfig); const db = firebase.database();

        // Auth İşlemleri
        function handleAuth(type) {
            const u = document.getElementById(type === 'login' ? 'lName' : 'rName').value.trim();
            const p = document.getElementById(type === 'login' ? 'lPass' : 'rPass').value.trim();
            
            if(!u || !p) return alert("Eksik bilgi!");
            
            if(type === 'login') {
                if(u === "ADMIN" && p === "1200778") return loginSuccess(u, true);
                db.ref('users/'+u).once('value').then(s => {
                    if(s.exists() && s.val().password === p) loginSuccess(u, s.val().isVip);
                    else alert("Hatalı giriş!");
                });
            } else {
                db.ref('users/'+u).set({password:p, isVip: false}).then(() => {
                    alert("Kayıt başarılı!");
                    document.getElementById('auth-container').classList.remove('active');
                });
            }
        }

        function loginSuccess(user, isVip) {
            sessionStorage.setItem("user", user);
            document.getElementById("auth-wrapper").style.display = "none";
            document.getElementById("dashboard-main").style.display = "grid";
            document.getElementById("vip-status-text").innerText = isVip ? "VIP ÜYE" : "STANDART";
            if(isVip) document.getElementById("vip-status-text").style.color = "#ffbb55";

            document.getElementById('geminiKeyInp').value = localStorage.getItem('geminiKey') || '';
            document.getElementById('claudeKeyInp').value = localStorage.getItem('claudeKey') || '';
        }

        // Ekran Modu
        function setScreenMode(mode) {
            document.getElementById('dashboard-main').className = mode;
        }

        // API Key Kaydetme
        function saveApiKey(type) {
            const val = document.getElementById(type+'KeyInp').value;
            localStorage.setItem(type+'Key', val);
            alert("Anahtar kaydedildi.");
        }

        // AI Chat Fonksiyonu
        async function askAI() {
            const input = document.getElementById('aiInput');
            const chat = document.getElementById('ai-messages');
            const text = input.value.trim();
            const model = document.getElementById('aiModelSelector').value;
            
            if(!text) return;
            
            chat.innerHTML += `<div class="msg-bubble msg-user">${text}</div>`;
            input.value = "";
            chat.scrollTop = chat.scrollHeight;

            const apiKey = localStorage.getItem(model+'Key');
            if(!apiKey) {
                chat.innerHTML += `<div class="msg-bubble msg-ai" style="color:red">Hata: API anahtarı bulunamadı!</div>`;
                return;
            }

            const loader = document.createElement('div');
            loader.className = "msg-bubble msg-ai";
            loader.innerText = "...";
            chat.appendChild(loader);

            try {
                const res = await fetch(`https://generativelanguage.googleapis.com/v1beta/models/gemini-1.5-pro:generateContent?key=${apiKey}`, {
                    method: "POST",
                    headers: { "Content-Type": "application/json" },
                    body: JSON.stringify({ contents: [{ parts: [{ text: text }] }] })
                });
                const data = await res.json();
                const aiMsg = data.candidates[0].content.parts[0].text;
                loader.innerHTML = `<b>${model.toUpperCase()}:</b><br>${marked.parse(aiMsg)}`;
            } catch(e) {
                loader.innerText = "Bağlantı hatası!";
            }
            chat.scrollTop = chat.scrollHeight;
        }

        // Görsel Efekt
        window.onmousemove = e => { 
            const g = document.getElementById('cursor-glow'); 
            g.style.left = e.clientX+'px'; 
            g.style.top = e.clientY+'px'; 
        };
        
        document.getElementById('aiInput').addEventListener('keypress', e => { if(e.key === 'Enter') askAI(); });
    </script>
</body>
</html>
