<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>NEXUS PRO | Ultimate Social Ecosystem</title>
    
    <link href="https://fonts.googleapis.com/icon?family=Material+Icons+Sharp" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>

    <style>
        /* ---------------------------------------------------------
        NEXUS CORE DESIGN SYSTEM - V4.0 (Global & DM Integrated)
        ---------------------------------------------------------
        */
        :root {
            --bg-deep: #020617;
            --bg-surface: #0f172a;
            --bg-accent: #1e293b;
            --primary: #6366f1;
            --primary-glow: rgba(99, 102, 241, 0.4);
            --secondary: #ec4899;
            --success: #22c55e;
            --text-main: #f8fafc;
            --text-dim: #94a3b8;
            --border-subtle: rgba(255, 255, 255, 0.08);
            --glass: rgba(15, 23, 42, 0.8);
            --sidebar-w: 85px;
            --list-w: 380px;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
        body { 
            font-family: 'Plus Jakarta Sans', sans-serif; 
            background: var(--bg-deep); 
            color: var(--text-main); 
            height: 100vh; 
            overflow: hidden;
            line-height: 1.6;
        }

        /* UTILITIES */
        .hidden { display: none !important; }
        .flex-center { display: flex; align-items: center; justify-content: center; }

        /* ---------------------------------------------------------
        AUTH OVERLAY (SECURITY LAYER)
        ---------------------------------------------------------
        */
        #nexus-auth {
            position: fixed; inset: 0; z-index: 10000;
            background: radial-gradient(circle at 50% 50%, #1e1b4b 0%, #020617 100%);
            display: flex; align-items: center; justify-content: center;
            padding: 20px; transition: 0.5s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .auth-container {
            background: var(--glass); backdrop-filter: blur(20px);
            padding: 3rem; border-radius: 2.5rem; border: 1px solid var(--border-subtle);
            width: 100%; max-width: 480px; text-align: center;
            box-shadow: 0 25px 80px -15px rgba(0,0,0,0.8);
        }

        .auth-logo { font-size: 2.8rem; font-weight: 800; margin-bottom: 0.5rem; background: linear-gradient(to right, #6366f1, #ec4899); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
        .auth-subtitle { color: var(--text-dim); margin-bottom: 2.5rem; font-size: 0.95rem; }

        .auth-field { position: relative; margin-bottom: 1.5rem; text-align: left; }
        .auth-field label { display: block; font-size: 0.8rem; font-weight: 600; color: var(--text-dim); margin-left: 1rem; margin-bottom: 0.5rem; }
        .auth-field input {
            width: 100%; padding: 1.1rem 1.5rem; border-radius: 1.2rem;
            background: rgba(255,255,255,0.04); border: 1px solid var(--border-subtle);
            color: white; font-size: 1rem; transition: 0.3s;
        }
        .auth-field input:focus { border-color: var(--primary); background: rgba(255,255,255,0.08); outline: none; box-shadow: 0 0 20px var(--primary-glow); }

        .btn-action {
            width: 100%; padding: 1.1rem; border-radius: 1.2rem;
            background: var(--primary); color: white; font-weight: 700;
            font-size: 1rem; border: none; cursor: pointer; transition: 0.3s;
            margin-top: 1rem; box-shadow: 0 10px 25px -5px var(--primary-glow);
        }
        .btn-action:hover { transform: translateY(-3px); filter: brightness(1.1); }

        /* ---------------------------------------------------------
        MAIN APPLICATION FRAMEWORK
        ---------------------------------------------------------
        */
        #nexus-core {
            display: grid; 
            grid-template-columns: var(--sidebar-w) var(--list-w) 1fr;
            height: 100vh; width: 100vw;
            opacity: 0; pointer-events: none; transition: 0.5s;
        }

        /* 1. SIDEBAR (NAV) */
        .sidebar {
            background: var(--bg-surface); border-right: 1px solid var(--border-subtle);
            display: flex; flex-direction: column; align-items: center; padding: 2rem 0; gap: 1.5rem;
        }
        .nav-link {
            width: 55px; height: 55px; border-radius: 1.2rem; color: var(--text-dim);
            cursor: pointer; transition: 0.3s; position: relative;
        }
        .nav-link:hover { color: var(--text-main); background: var(--bg-accent); }
        .nav-link.active { background: var(--primary); color: white; box-shadow: 0 8px 20px var(--primary-glow); }
        .nav-link.active::after { content: ''; position: absolute; left: -15px; width: 5px; height: 25px; background: var(--primary); border-radius: 0 5px 5px 0; }

        /* 2. CHAT LIST PANEL */
        .list-panel {
            background: rgba(15, 23, 42, 0.4); border-right: 1px solid var(--border-subtle);
            display: flex; flex-direction: column;
        }
        .list-header { padding: 2rem 1.5rem; }
        .list-header h2 { font-size: 1.6rem; font-weight: 800; }
        .search-container {
            margin-top: 1.5rem; background: var(--bg-accent);
            padding: 0.8rem 1.2rem; border-radius: 1rem; display: flex; align-items: center; gap: 10px;
        }
        .search-container input { background: transparent; border: none; color: white; flex: 1; font-size: 0.9rem; }

        .items-scroll { flex: 1; overflow-y: auto; padding-bottom: 2rem; }
        .user-row {
            display: flex; align-items: center; gap: 1rem; padding: 1.2rem 1.5rem;
            cursor: pointer; transition: 0.2s; border-radius: 1.2rem; margin: 0 10px;
        }
        .user-row:hover { background: rgba(255,255,255,0.05); }
        .user-row.active { background: rgba(99, 102, 241, 0.1); }

        .avatar-box {
            position: relative; width: 54px; height: 54px;
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            border-radius: 1.2rem; font-weight: 800; font-size: 1.2rem;
        }
        .status-indicator {
            position: absolute; bottom: -2px; right: -2px;
            width: 14px; height: 14px; background: var(--success);
            border: 3px solid var(--bg-surface); border-radius: 50%;
        }

        /* 3. MESSAGE ARENA */
        .chat-arena {
            display: flex; flex-direction: column; background: var(--bg-deep);
            background-image: radial-gradient(circle at 50% 50%, rgba(99, 102, 241, 0.05) 0%, transparent 80%);
            position: relative;
        }
        .arena-header {
            padding: 1.2rem 2.5rem; background: rgba(15, 23, 42, 0.9);
            backdrop-filter: blur(10px); border-bottom: 1px solid var(--border-subtle);
            display: flex; align-items: center; justify-content: space-between;
        }

        .messages-scroll {
            flex: 1; padding: 2rem; overflow-y: auto;
            display: flex; flex-direction: column; gap: 1.2rem;
            scroll-behavior: smooth;
        }

        /* Message Bubbles */
        .message-box { max-width: 65%; display: flex; flex-direction: column; gap: 4px; animation: msgFade 0.3s ease; }
        @keyframes msgFade { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
        
        .msg-sender { font-size: 0.75rem; font-weight: 600; color: var(--text-dim); margin-left: 10px; }
        .msg-bubble { 
            padding: 1rem 1.4rem; border-radius: 1.5rem; font-size: 0.95rem;
            word-wrap: break-word; position: relative;
        }
        .msg-received { align-self: flex-start; }
        .msg-received .msg-bubble { background: var(--bg-accent); color: var(--text-main); border-bottom-left-radius: 0.3rem; }
        
        .msg-sent { align-self: flex-end; }
        .msg-sent .msg-bubble { background: var(--primary); color: white; border-bottom-right-radius: 0.3rem; box-shadow: 0 4px 15px var(--primary-glow); }
        .msg-time { font-size: 0.65rem; color: var(--text-dim); align-self: flex-end; margin-top: 2px; }

        /* Input Deck */
        .input-deck {
            padding: 1.5rem 2.5rem; background: var(--bg-surface);
            display: flex; gap: 1rem; align-items: center; border-top: 1px solid var(--border-subtle);
        }
        .input-wrap {
            flex: 1; background: var(--bg-accent); border-radius: 1.2rem;
            display: flex; align-items: center; padding: 0.2rem 1.2rem; border: 1px solid transparent; transition: 0.3s;
        }
        .input-wrap:focus-within { border-color: var(--primary); box-shadow: 0 0 15px var(--primary-glow); }
        .input-wrap input { flex: 1; padding: 1rem 0; background: transparent; border: none; color: white; outline: none; }

        .btn-send {
            width: 50px; height: 50px; border-radius: 1.2rem; background: var(--primary);
            color: white; border: none; cursor: pointer; transition: 0.3s;
        }
        .btn-send:hover { transform: scale(1.05) rotate(-5deg); }

        /* ---------------------------------------------------------
        RESPONSIVE BREAKPOINTS (Mobile/Tablet/PC)
        ---------------------------------------------------------
        */
        
        /* TABLET MODE */
        @media (max-width: 1100px) {
            :root { --list-w: 300px; }
            .auth-container { max-width: 400px; padding: 2rem; }
        }

        /* MOBILE MODE (Critical Overrides) */
        @media (max-width: 768px) {
            #nexus-core {
                grid-template-columns: 1fr; /* Sadece aktif panel görünür */
            }
            .sidebar {
                position: fixed; bottom: 0; left: 0; right: 0; height: 70px;
                flex-direction: row; justify-content: space-around; padding: 0;
                z-index: 1000; border-right: none; border-top: 1px solid var(--border-subtle);
            }
            .list-panel {
                position: absolute; inset: 0 0 70px 0; z-index: 5;
            }
            .chat-arena {
                position: absolute; inset: 0 0 70px 0; z-index: 10;
                transform: translateX(100%); transition: 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            }
            .chat-arena.mobile-active { transform: translateX(0); }
            
            .back-btn { display: flex !important; margin-right: 15px; cursor: pointer; }
            .list-w { width: 100%; }
            .message-box { max-width: 85%; }
            .input-deck { padding: 1rem; }
        }

        /* Profile Preview Panel */
        #profile-panel {
            background: var(--bg-surface); padding: 2rem;
            display: flex; flex-direction: column; align-items: center; gap: 1rem;
        }

        /* Scrollbar Styling */
        ::-webkit-scrollbar { width: 6px; }
        ::-webkit-scrollbar-track { background: transparent; }
        ::-webkit-scrollbar-thumb { background: var(--bg-accent); border-radius: 10px; }
        ::-webkit-scrollbar-thumb:hover { background: var(--text-dim); }

    </style>
</head>
<body>

    <div id="nexus-auth">
        <div class="auth-container" id="auth-box">
            <div class="auth-logo">NEXUS PRO</div>
            <p class="auth-subtitle">Giriş yapın ve ekosisteme dahil olun.</p>
            
            <div class="auth-field">
                <label>KİMLİK ADI</label>
                <input type="text" id="user-name" placeholder="@kullaniciadi" autocomplete="off">
            </div>
            
            <div class="auth-field">
                <label>ERİŞİM ANAHTARI</label>
                <input type="password" id="user-pass" placeholder="••••••••">
            </div>

            <button class="btn-action" onclick="gateKeep()">SİSTEME GİRİŞ YAP</button>
            <p style="margin-top: 1.5rem; font-size: 0.75rem; color: var(--text-dim)">Şifreniz yoksa hesabınız otomatik oluşturulur.</p>
        </div>
    </div>

    <div id="nexus-core">
        
        <nav class="sidebar">
            <div class="nav-link flex-center active" onclick="switchMainTab('global', this)" title="Global Chat">
                <span class="material-icons-sharp">public</span>
            </div>
            <div class="nav-link flex-center" onclick="switchMainTab('dm', this)" title="Özel Mesajlar">
                <span class="material-icons-sharp">forum</span>
            </div>
            <div class="nav-link flex-center" onclick="switchMainTab('profile', this)" title="Profil">
                <span class="material-icons-sharp">account_circle</span>
            </div>
            <div class="nav-link flex-center" style="margin-top: auto; color: var(--secondary);" onclick="forceExit()">
                <span class="material-icons-sharp">power_settings_new</span>
            </div>
        </nav>

        <aside class="list-panel">
            <div class="list-header">
                <h2 id="view-title">Global Chat</h2>
                <div class="search-container">
                    <span class="material-icons-sharp" style="color: var(--text-dim)">search</span>
                    <input type="text" id="search-input" placeholder="Kullanıcı veya kanal ara...">
                </div>
            </div>

            <div class="items-scroll" id="list-render-target">
                </div>
        </aside>

        <main class="chat-arena" id="chat-arena">
            <header class="arena-header">
                <div style="display: flex; align-items: center;">
                    <div class="back-btn flex-center hidden" onclick="toggleMobileArena(false)">
                        <span class="material-icons-sharp">arrow_back_ios</span>
                    </div>
                    <div class="avatar-box flex-center" id="arena-avatar" style="width: 45px; height: 45px; border-radius: 12px; margin-right: 15px;">#</div>
                    <div>
                        <h4 id="arena-title" style="font-weight: 700;">Global Meydan</h4>
                        <p id="arena-status" style="font-size: 0.7rem; color: var(--success); font-weight: 600;">Sistem Aktif</p>
                    </div>
                </div>
                <div style="display: flex; gap: 15px;">
                    <span class="material-icons-sharp" style="cursor:pointer; color: var(--text-dim)">videocam</span>
                    <span class="material-icons-sharp" style="cursor:pointer; color: var(--text-dim)">info</span>
                </div>
            </header>

            <div class="messages-scroll" id="msg-feed">
                </div>

            <footer class="input-deck">
                <div class="input-wrap">
                    <span class="material-icons-sharp" style="color: var(--text-dim); margin-right: 10px; cursor: pointer;">sentiment_satisfied_alt</span>
                    <input type="text" id="main-input" placeholder="Bir mesaj yazın..." autocomplete="off">
                    <span class="material-icons-sharp" style="color: var(--text-dim); margin-left: 10px; cursor: pointer;">attach_file</span>
                </div>
                <button class="btn-send flex-center" onclick="dispatchMessage()">
                    <span class="material-icons-sharp">send</span>
                </button>
            </footer>
        </main>

        <div id="profile-panel" class="hidden">
            <div class="avatar-box flex-center" style="width: 120px; height: 120px; border-radius: 2rem; font-size: 3rem;">?</div>
            <h2 id="p-name">Kullanıcı Adı</h2>
            <p id="p-bio" style="color: var(--text-dim); text-align: center;">Nexus Social üzerinde yeni bir kaşif.</p>
            <hr style="width: 100%; border: none; border-top: 1px solid var(--border-subtle); margin: 1rem 0;">
            <div style="width: 100%;">
                <button class="btn-action" style="background: var(--bg-accent);">Profili Düzenle</button>
                <button class="btn-action" style="background: #ef4444; margin-top: 10px;" onclick="forceExit()">Çıkış Yap</button>
            </div>
        </div>

    </div>

    <script>
        /* ---------------------------------------------------------
        NEXUS LOGIC CORE - V4.0
        ---------------------------------------------------------
        */

        let state = {
            currentUser: null,
            activeTab: 'global', // global, dm, profile
            activeTarget: 'global',
            database: {
                global: [
                    { sender: 'Nexus Bot', text: 'Hoş geldiniz! Burası Nexus Global. Kurallara uymayı unutmayın.', type: 'received', time: '10:00' }
                ],
                dms: [
                    { id: 'user_1', name: 'Alperen Kayıt', last: 'Abi projeyi bitirdim.', avatar: 'AK', messages: [] },
                    { id: 'user_2', name: 'Zeynep Ak', last: 'Yarın görüşüyor muyuz?', avatar: 'ZA', messages: [] },
                    { id: 'user_3', name: 'Kerem Valo', last: 'Rank atladım gelsene', avatar: 'KV', messages: [] }
                ]
            }
        };

        // --- AUTH SYSTEM ---
        function gateKeep() {
            const user = document.getElementById('user-name').value.trim();
            const pass = document.getElementById('user-pass').value.trim();

            if(user.length < 3) {
                alert("Kullanıcı adı en az 3 karakter olmalıdır!");
                return;
            }

            state.currentUser = user;
            
            // Animation for transition
            gsap.to("#nexus-auth", { opacity: 0, scale: 1.1, duration: 0.6, onComplete: () => {
                document.getElementById('nexus-auth').classList.add('hidden');
                document.getElementById('nexus-core').style.opacity = '1';
                document.getElementById('nexus-core').style.pointerEvents = 'all';
                initApp();
            }});
        }

        function initApp() {
            renderList();
            renderMessages();
            
            // Welcome message
            setTimeout(() => {
                pushMessage('Sistem', `Bağlantı başarılı. Merhaba ${state.currentUser}!`, 'received');
            }, 800);
        }

        // --- NAVIGATION & UI TABS ---
        function switchMainTab(tab, el) {
            state.activeTab = tab;
            
            // UI Update
            document.querySelectorAll('.nav-link').forEach(l => l.classList.remove('active'));
            el.classList.add('active');

            const title = document.getElementById('view-title');
            const profile = document.getElementById('profile-panel');
            const chat = document.getElementById('chat-arena');
            const list = document.querySelector('.list-panel');

            if(tab === 'profile') {
                title.innerText = "Hesabım";
                profile.classList.remove('hidden');
                chat.classList.add('hidden');
                list.classList.add('hidden');
                document.getElementById('p-name').innerText = state.currentUser;
            } else {
                profile.classList.add('hidden');
                chat.classList.remove('hidden');
                list.classList.remove('hidden');
                
                if(tab === 'global') {
                    title.innerText = "Global Chat";
                    state.activeTarget = 'global';
                } else {
                    title.innerText = "Mesajlar";
                    state.activeTarget = state.database.dms[0].id;
                }
                renderList();
                renderMessages();
            }
        }

        function toggleMobileArena(show) {
            const arena = document.getElementById('chat-arena');
            if(show) arena.classList.add('mobile-active');
            else arena.classList.remove('mobile-active');
        }

        // --- LIST RENDERING ---
        function renderList() {
            const target = document.getElementById('list-render-target');
            target.innerHTML = "";

            if(state.activeTab === 'global') {
                target.innerHTML = `
                    <div class="user-row active" onclick="selectChat('global', 'Global Meydan', '#')">
                        <div class="avatar-box flex-center">#</div>
                        <div style="flex:1">
                            <h4 style="font-size:0.95rem">Global Meydan</h4>
                            <p style="font-size:0.8rem; color:var(--text-dim)">Tüm dünya burada...</p>
                        </div>
                    </div>
                `;
            } else if(state.activeTab === 'dm') {
                state.database.dms.forEach(u => {
                    target.innerHTML += `
                        <div class="user-row ${state.activeTarget === u.id ? 'active' : ''}" onclick="selectChat('${u.id}', '${u.name}', '${u.avatar}')">
                            <div class="avatar-box flex-center">${u.avatar}<div class="status-indicator"></div></div>
                            <div style="flex:1">
                                <h4 style="font-size:0.95rem">${u.name}</h4>
                                <p style="font-size:0.8rem; color:var(--text-dim)">${u.last}</p>
                            </div>
                        </div>
                    `;
                });
            }
        }

        // --- CHAT LOGIC ---
        function selectChat(id, name, avatar) {
            state.activeTarget = id;
            document.getElementById('arena-title').innerText = name;
            document.getElementById('arena-avatar').innerText = avatar;
            
            renderList();
            renderMessages();
            
            // Mobile Support
            if(window.innerWidth <= 768) toggleMobileArena(true);
        }

        function dispatchMessage() {
            const input = document.getElementById('main-input');
            const text = input.value.trim();
            if(!text) return;

            pushMessage(state.currentUser, text, 'sent');
            input.value = "";

            // Auto-Reply Simulation
            if(state.activeTarget !== 'global') {
                setTimeout(() => {
                    pushMessage('Nexus AI', 'Mesajını aldım, şu an meşgulüm.', 'received');
                }, 1500);
            }
        }

        function pushMessage(sender, text, type) {
            const feed = document.getElementById('msg-feed');
            const now = new Date();
            const timeStr = now.getHours().toString().padStart(2, '0') + ":" + now.getMinutes().toString().padStart(2, '0');

            const msgHtml = `
                <div class="message-box msg-${type}">
                    <span class="msg-sender">${sender}</span>
                    <div class="msg-bubble">${text}</div>
                    <span class="msg-time">${timeStr}</span>
                </div>
            `;

            feed.insertAdjacentHTML('beforeend', msgHtml);
            feed.scrollTop = feed.scrollHeight;
        }

        function renderMessages() {
            // In a real app, you would fetch from state.database based on activeTarget
            const feed = document.getElementById('msg-feed');
            feed.innerHTML = `<div style="text-align:center; color:var(--text-dim); font-size:0.8rem; margin:1rem 0;">Şifreli görüşme başlatıldı</div>`;
        }

        function forceExit() {
            if(confirm("Sistemden çıkış yapmak istediğine emin misin?")) {
                location.reload();
            }
        }

        // --- EVENT LISTENERS ---
        document.getElementById('main-input').addEventListener('keypress', (e) => {
            if(e.key === 'Enter') dispatchMessage();
        });

        // Search Filter
        document.getElementById('search-input').addEventListener('input', (e) => {
            const val = e.target.value.toLowerCase();
            document.querySelectorAll('.user-row').forEach(row => {
                const name = row.querySelector('h4').innerText.toLowerCase();
                row.style.display = name.includes(val) ? 'flex' : 'none';
            });
        });

    </script>
</body>
</html>
