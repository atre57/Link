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
        /* --- Temel Değişkenler & CSS Reset --- */
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
            
            --card-border-radius: 2rem;
            --border-radius-1: 0.4rem;
            --border-radius-2: 0.8rem;
            
            --card-padding: 1.5rem;
            --padding-1: 1.2rem;
            
            --box-shadow: 0 2rem 3rem var(--color-light);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; text-decoration: none; list-style: none; border: 0; outline: none; transition: all 300ms ease; }
        body { font-family: 'Poppins', sans-serif; font-size: 0.88rem; user-select: none; overflow-x: hidden; color: var(--color-dark); background-color: var(--color-background); }
        h1 { font-weight: 800; font-size: 1.8rem; }
        h3 { font-weight: 500; font-size: 0.87rem; }
        h4 { font-weight: 400; font-size: 0.8rem; font-family: 'VALORANT', sans-serif; }
        
        .valorant { font-family: 'VALORANT', sans-serif; color: var(--v-purple); }

        /* --- 1. GİRİŞ EKRANI (AUTH) --- */
        #auth-wrapper {
            width: 100%; height: 100vh; position: fixed; top: 0; left: 0;
            background-color: #c9d6ff; display: flex; align-items: center; justify-content: center;
            z-index: 10000;
        }
        .auth-container {
            background-color: #fff; border-radius: 30px; box-shadow: 0 5px 15px rgba(0,0,0,0.35);
            position: relative; overflow: hidden; width: 768px; max-width: 95%; min-height: 480px;
        }
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

        /* --- 2. DASHBOARD ANA YAPISI --- */
        #dashboard-main { display: none; width: 96%; margin: 0 auto; gap: 1.8rem; min-height: 100vh; }
        
        /* Ekran Boyutu Modları (PC, Tablet, Telefon) */
        #dashboard-main.pc { grid-template-columns: 14rem auto 26rem; }
        #dashboard-main.tablet { grid-template-columns: 7rem auto; }
        #dashboard-main.phone { grid-template-columns: 1fr; }

        /* --- 3. SIDEBAR --- */
        aside { height: 100vh; position: sticky; top: 0; }
        aside .top { display: flex; align-items: center; justify-content: space-between; margin-top: 1.4rem; padding: 0 1rem; }
        aside .logo { display: flex; gap: 0.8rem; }
        aside .sidebar { display: flex; flex-direction: column; height: 86vh; position: relative; top: 3rem; gap: 1rem; }
        aside h3 { font-size: 0.87rem; }
        aside .sidebar a { display: flex; color: var(--color-info-dark); margin-left: 2rem; gap: 1rem; align-items: center; height: 3.7rem; transition: all 300ms ease; position: relative; }
        aside .sidebar a span { font-size: 1.6rem; }
        aside .sidebar a:last-child { position: absolute; bottom: 2rem; width: 100%; }
        aside .sidebar a.active { background: var(--color-light); color: var(--color-primary); margin-left: 0; }
        aside .sidebar a.active:before { content: ""; width: 6px; height: 100%; background: var(--color-primary); }
        aside .sidebar a:hover { color: var(--color-primary); }

        /* Tablet Modunda Sidebar */
        #dashboard-main.tablet aside h3 { display: none; }
        #dashboard-main.tablet aside .top { justify-content: center; }
        #dashboard-main.tablet aside .sidebar a { justify-content: center; margin-left: 0; }

        /* --- 4. ANA İÇERİK (MAIN) --- */
        main { margin-top: 1.4rem; }
        main h1 { margin-bottom: 2rem; }
        main .insights { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.6rem; }
        main .insights > div { background: var(--color-white); padding: var(--card-padding); border-radius: var(--card-border-radius); box-shadow: var(--box-shadow); }
        main .insights > div:hover { box-shadow: none; cursor: pointer; }
        main .insights h3 { margin-top: 0.8rem; font-size: 1rem; font-family: 'VALORANT', sans-serif; }
        main .insights span.v-icon { background: var(--color-primary); color: white; padding: 0.5rem; border-radius: 50%; font-size: 2rem; }

        /* Yapılandırma Paneli (Yeni) */
        .config-panel { margin-top: 2rem; background: var(--color-white); padding: var(--card-padding); border-radius: var(--card-border-radius); box-shadow: var(--box-shadow); }
        .config-panel h2 { margin-bottom: 1rem; }
        .key-input { display: flex; gap: 10px; margin-bottom: 1rem; }
        .key-input input { background: var(--color-background); border: 1px solid var(--color-light); padding: 0.8rem; border-radius: var(--border-radius-1); flex: 1; }
        .config-btn { background: var(--color-success); color: var(--color-dark); padding: 0.8rem 1.5rem; border-radius: var(--border-radius-1); cursor: pointer; font-weight: 600; }

        /* --- 5. SAĞ PANEL (AI ASSISTANT) --- */
        .right { margin-top: 1.4rem; padding-left: 1rem; }
        .ai-assistant { background: var(--color-white); padding: var(--card-padding); border-radius: var(--card-border-radius); box-shadow: var(--box-shadow); height: 550px; display: flex; flex-direction: column; gap: 1rem; }
        .ai-header { display: flex; justify-content: space-between; align-items: center; padding-bottom: 0.8rem; border-bottom: 1px solid var(--color-light); }
        .ai-header h3 { font-family: 'VALORANT', sans-serif; font-size: 1.1rem; }
        .model-select { background: var(--color-background); border: 1px solid var(--color-light); padding: 5px 10px; border-radius: var(--border-radius-1); font-size: 0.7rem; }
        #ai-messages { flex: 1; overflow-y: auto; display: flex; flex-direction: column; gap: 10px; padding-right: 5px; }
        
        .msg-bubble { padding: 10px 15px; border-radius: 12px; max-width: 90%; }
        .msg-user { align-self: flex-end; background: var(--v-purple); color: white; border-bottom-right-radius: 2px; }
        .msg-ai { align-self: flex-start; background: var(--color-light); color: var(--color-dark); border-bottom-left-radius: 2px; }
        .msg-ai pre { background: #282c34; color: #abb2bf; padding: 10px; border-radius: 8px; overflow-x: auto; margin-top: 5px; }

        .chat-input-area { display: flex; gap: 0.5rem; border-top: 1px solid var(--color-light); padding-top: 1rem; }
        .chat-input-area input { width: 100%; background: var(--color-background); padding: 0.8rem; border-radius: 1rem; }
        .chat-input-area button { background: none; color: var(--v-purple); cursor: pointer; font-size: 2rem; }

        /* Telefon Modunda Sağ Panel */
        #dashboard-main.phone .right { grid-row: 2; margin-top: 0; padding-left: 0; }
        
        /* --- 6. EKSTRA GÖRSEL ÖĞELER --- */
        #cursor-glow { position: fixed; width: 300px; height: 300px; background: radial-gradient(circle, rgba(115, 128, 236, 0.1) 0%, transparent 70%); pointer-events: none; z-index: 999999; transform: translate(-50%, -50%); }
    </style>
</head>
<body>

    <div id="cursor-glow"></div>

    <div id="auth-wrapper">
        <div class="auth-container" id="auth-container">
            <div class="form-container sign-up">
                <form>
                    <h1>Hesap Oluştur</h1>
                    <input type="text" id="rName" class="auth-input" placeholder="Kullanıcı Adı">
                    <input type="password" id="rPass" class="auth-input" placeholder="Şifre">
                    <button type="button" class="auth-btn" onclick="handleAuth('register')">KAYDOL</button>
                </form>
            </div>
            <div class="form-container sign-in">
                <form>
                    <h1 class="valorant" style="font-size: 2rem; margin-bottom: 20px;">NEXUS HUB</h1>
                    <input type="text" id="lName" class="auth-input" placeholder="Kullanıcı Adı">
                    <input type="password" id="lPass" class="auth-input" placeholder="Şifre">
                    <button type="button" class="auth-btn" onclick="handleAuth('login')">GİRİŞ YAP</button>
                    <button type="button" class="auth-btn" onclick="loginSuccess('MİSAFİR', false)" style="background: #333; margin-top: 5px;">MİSAFİR GİRİŞİ</button>
                </form>
            </div>
            <div class="toggle-container">
                <div class="toggle">
                    <div class="toggle-panel toggle-left">
                        <h1>Zaten Üye misin?</h1>
                        <button class="auth-btn" id="toLoginBtn">GİRİŞ YAP</button>
                    </div>
                    <div class="toggle-panel toggle-right">
                        <h1>Selam Komutan!</h1>
                        <button class="auth-btn" id="toRegisterBtn">Hemen KAYDOL</button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div id="dashboard-main" class="pc">
        <aside>
            <div class="top">
                <div class="logo">
                    <h2 class="valorant">HUB</h2>
                </div>
            </div>
            <div class="sidebar">
                <a class="active"><span class="material-icons-sharp">auto_awesome</span><h3>Asistan</h3></a>
                <a><span class="material-icons-sharp">insights</span><h3>Analiz</h3></a>
                <a><span class="material-icons-sharp">groups</span><h3>Üyeler</h3></a>
                <a><span class="material-icons-sharp">settings</span><h3>Ayarlar</h3></a>
                
                <div style="border-top:1px solid var(--color-light); padding: 10px; display:flex; flex-direction:column; gap: 5px; position:absolute; bottom: 6rem; width:100%">
                    <h4 style="font-size: 0.7rem; color: var(--color-info-dark); margin-bottom: 5px;">Cihaz Görünümü</h4>
                    <button onclick="setScreenMode('phone')" style="background:none; display:flex; gap: 10px; color:var(--color-dark); cursor:pointer;"><span class="material-icons-sharp">stay_primary_portrait</span>Cep</button>
                    <button onclick="setScreenMode('tablet')" style="background:none; display:flex; gap: 10px; color:var(--color-dark); cursor:pointer;"><span class="material-icons-sharp">tablet_android</span>Tablet</button>
                    <button onclick="setScreenMode('pc')" style="background:none; display:flex; gap: 10px; color:var(--color-dark); cursor:pointer;"><span class="material-icons-sharp">desktop_windows</span>PC</button>
                </div>

                <a onclick="location.reload()"><span class="material-icons-sharp">logout</span><h3>Çıkış</h3></a>
            </div>
        </aside>

        <main>
            <h1>Yapay Zeka Paneli</h1>
            
            <div class="insights">
                <div onclick="alert('Model Seçimi Açılıyor...')">
                    <span class="material-icons-sharp v-icon">language</span>
                    <h3>MODEL SEÇ</h3>
                    <h4>Dil & Mantık</h4>
                </div>
                <div onclick="alert('Görsel Mod Açılıyor...')">
                    <span class="material-icons-sharp v-icon">auto_fix_high</span>
                    <h3>GÖRSEL ÜRET</h3>
                    <h4>DALL-E & Midjourney</h4>
                </div>
                <div onclick="alert('Kod Modu Açılıyor...')">
                    <span class="material-icons-sharp v-icon">terminal</span>
                    <h3>KOD ASİSTANI</h3>
                    <h4>Hata Ayıklama</h4>
                </div>
            </div>

            <div class="config-panel">
                <h2>Yapılandırma</h2>
                <h4>Bu anahtarlar sadece senin cihazında tutulur, sunucularımıza gönderilmez.</h4>
                <div style="margin-top: 1rem;">
                    <label>Gemini API Key (Google AI Studio)</label>
                    <div class="key-input">
                        <input type="text" id="geminiKeyInp" placeholder="AIzaSy...">
                        <button class="config-btn" onclick="saveApiKey('gemini')">KAYDET</button>
                    </div>
                    <label>Claude API Key (Anthropic Console)</label>
                    <div class="key-input">
                        <input type="text" id="claudeKeyInp" placeholder="sk-ant-...">
                        <button class="config-btn" onclick="saveApiKey('claude')">KAYDET</button>
                    </div>
                </div>
            </div>
        </main>

        <div class="right">
            <div class="ai-assistant">
                <div class="ai-header">
                    <h3>AI ASİSTAN</h3>
                    <select id="aiModelSelector" class="model-select">
                        <option value="gemini">Gemini Pro</option>
                        <option value="claude">Claude 3 (Simüle)</option>
                    </select>
                </div>
                
                <div id="ai-messages">
                    <div class="msg-bubble msg-ai">Selam Komutan, bugün hangi AI modelini kullanmak istersin?</div>
                </div>
                
                <div class="chat-input-area">
                    <input type="text" id="aiInput" placeholder="Yapay zekaya sor...">
                    <button onclick="askAI()"><span class="material-icons-sharp">send</span></button>
                </div>
            </div>
        </div>
    </div>

    <script>
        // === 1. KONFİGÜRASYON VE VERİTABAANI ===
        // !!! DİKKAT !!! Hassas API anahtarlarınızı bir config manager olarak saklayacağız.
        // Başlangıç için koda anahtar gömmedim, kullanıcıdan alacağız.

        // Firebase Ayarları (Eski veritabanın)
        const dbConfig = { apiKey: "AIzaSyBC_h0zpRSSGdzcbtGsq3Bh2WGKAgTrNKc", authDomain: "vanguardnexus-a2871.firebaseapp.com", databaseURL: "https://vanguardnexus-a2871-default-rtdb.firebaseio.com", projectId: "vanguardnexus-a2871" };
        firebase.initializeApp(dbConfig); const db = firebase.database();

        // === 2. GİRİŞ VE ÜYELİK SİSTEMİ ===
        const authContainer = document.getElementById('auth-container');
        document.getElementById('toRegisterBtn').addEventListener('click', () => authContainer.classList.add("active"));
        document.getElementById('toLoginBtn').addEventListener('click', () => authContainer.classList.remove("active"));

        function handleAuth(type) {
            const u = document.getElementById(type === 'login' ? 'lName' : 'rName').value.trim();
            const p = document.getElementById(type === 'login' ? 'lPass' : 'rPass').value.trim();
            
            if(!u || !p) return alert("Lütfen alanları doldur.");
            
            if(type === 'login') {
                if(u === "ADMIN" && p === "1200778") return loginSuccess(u, true);
                db.ref('users/'+u).once('value').then(s => {
                    if(s.exists() && s.val().password === p) loginSuccess(u, s.val().isVip);
                    else alert("Kullanıcı adı veya şifre hatalı.");
                });
            } else {
                db.ref('users/'+u).once('value').then(s => {
                    if(s.exists()) return alert("Kullanıcı zaten var.");
                    db.ref('users/'+u).set({password:p, isVip: false}).then(() => {
                        alert("Kayıt başarılı! Giriş yapabilirsiniz.");
                        authContainer.classList.remove("active");
                    });
                });
            }
        }

        function loginSuccess(user, isVip) {
            sessionStorage.setItem("user", user);
            sessionStorage.setItem("vip", isVip);
            document.getElementById("auth-wrapper").style.display = "none";
            document.getElementById("dashboard-main").style.display = "grid";
            
            // Kayıtlı API anahtarlarını yükle
            document.getElementById('geminiKeyInp').value = localStorage.getItem('geminiKey') || '';
            document.getElementById('claudeKeyInp').value = localStorage.getItem('claudeKey') || '';
        }

        // === 3. EKRAN MODLARI (RESPONSIVE PC, Tablet, Cep) ===
        function setScreenMode(mode) {
            const main = document.getElementById('dashboard-main');
            main.className = mode; // pc, tablet, phone
        }

        // === 4. API ANAHTARLARINI SAKLAMA (YEREL) ===
        function saveApiKey(type) {
            const inp = document.getElementById(type+'KeyInp');
            const key = inp.value.trim();
            if(key) {
                localStorage.setItem(type+'Key', key);
                alert(`${type.toUpperCase()} Anahtarı sadece senin cihazına kaydedildi.`);
            } else {
                localStorage.removeItem(type+'Key');
                alert(`${type.toUpperCase()} Anahtarı silindi.`);
            }
        }

        // === 5. AI ASİSTAN (GEMINI & CLAUDE) ===
        async function askAI() {
            const input = document.getElementById('aiInput');
            const chat = document.getElementById('ai-messages');
            const model = document.getElementById('aiModelSelector').value;
            const text = input.value.trim();
            if(!text) return;

            // Kullanıcı mesajı
            chat.innerHTML += `<div class="msg-bubble msg-user">${text}</div>`;
            input.value = "";
            
            // Yükleniyor durumu
            const loadId = "l-" + Date.now();
            chat.innerHTML += `<div id="${loadId}" class="msg-bubble msg-ai" style="font-style: italic;">${model.toUpperCase()} düşünüyor...</div>`;
            chat.scrollTop = chat.scrollHeight;

            const apiKey = localStorage.getItem(model+'Key');
            if(!apiKey) {
                document.getElementById(loadId).innerText = `Hata: ${model.toUpperCase()} API anahtarı 'Ayarlar' kısmına eklenmemiş.`;
                chat.scrollTop = chat.scrollHeight;
                return;
            }

            try {
                let aiResponseText = "";
                
                if(model === "gemini") {
                    const res = await fetch(`https://generativelanguage.googleapis.com/v1beta/models/gemini-1.5-pro:generateContent?key=${apiKey}`, {
                        method: "POST",
                        headers: { "Content-Type": "application/json" },
                        body: JSON.stringify({ contents: [{ parts: [{ text: text }] }] })
                    });
                    const data = await res.json();
                    aiResponseText = data.candidates[0].content.parts[0].text;
                } else {
                    // Claude simülasyonu
                    aiResponseText = "Tarayıcı üzerinde güvenlik nedeniyle (CORS) Anthropic API'sine doğrudan bağlantı kuramıyorum. Şimdilik Gemini Pro modelini kullanabilirsin komutan.";
                }

                // AI yanıtını marked.parse ile kod blokları düzgün görünecek şekilde kopyala
                document.getElementById(loadId).remove();
                chat.innerHTML += `<div class="msg-bubble msg-ai"><b>${model.toUpperCase()}:</b><br>${marked.parse(aiResponseText)}</div>`;
                
            } catch(e) { 
                document.getElementById(loadId).innerText = "Hata! Bağlantı kurulamadı, API anahtarını kontrol et."; 
            }
            chat.scrollTop = chat.scrollHeight;
        }

        // Enter tuşu desteği
        document.getElementById('aiInput').addEventListener('keypress', function(e) { if(e.key === 'Enter') askAI(); });

        // === 6. EFEKTLER (CURSOR GLOW) ===
        window.onmousemove = e => { const g = document.getElementById('cursor-glow'); g.style.left = e.clientX+'px'; g.style.top = e.clientY+'px'; };
    </script>
</body>
</html>
