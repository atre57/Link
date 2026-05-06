<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NEXUS SOCIAL | Global & DM</title>
    
    <link href="https://fonts.googleapis.com/icon?family=Material+Icons+Sharp" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --bg: #0f172a;
            --glass: rgba(30, 41, 59, 0.7);
            --primary: #8b5cf6;
            --primary-hover: #7c3aed;
            --text: #f8fafc;
            --text-muted: #94a3b8;
            --border: rgba(255, 255, 255, 0.1);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Inter', sans-serif; }
        body { background: var(--bg); color: var(--text); overflow: hidden; height: 100vh; }

        /* --- GİRİŞ / KAYIT EKRANI --- */
        #auth-screen {
            position: fixed; inset: 0; background: radial-gradient(circle at top right, #1e1b4b, #0f172a);
            display: flex; align-items: center; justify-content: center; z-index: 9999;
        }

        .auth-card {
            background: var(--glass); backdrop-filter: blur(15px);
            padding: 3rem; border-radius: 2rem; border: 1px solid var(--border);
            width: 100%; max-width: 450px; text-align: center;
            box-shadow: 0 25px 50px -12px rgba(0,0,0,0.5);
        }

        .auth-card h1 { font-size: 2.5rem; font-weight: 700; margin-bottom: 1rem; letter-spacing: -1px; }
        .auth-card p { color: var(--text-muted); margin-bottom: 2rem; }

        .input-group { margin-bottom: 1.2rem; text-align: left; }
        .input-group label { display: block; margin-bottom: 0.5rem; font-size: 0.9rem; color: var(--text-muted); }
        input {
            width: 100%; padding: 1rem; border-radius: 1rem; border: 1px solid var(--border);
            background: rgba(255,255,255,0.05); color: white; transition: 0.3s;
        }
        input:focus { border-color: var(--primary); outline: none; background: rgba(255,255,255,0.1); }

        .auth-btn {
            width: 100%; padding: 1rem; border-radius: 1rem; background: var(--primary);
            color: white; font-weight: 600; cursor: pointer; border: none; transition: 0.3s;
        }
        .auth-btn:hover { background: var(--primary-hover); transform: translateY(-2px); }

        /* --- ANA UYGULAMA YAPISI --- */
        #app { display: none; grid-template-columns: 80px 350px 1fr; height: 100vh; }

        /* Sol İkon Bar */
        .sidebar-icons {
            background: rgba(15, 23, 42, 0.9); border-right: 1px solid var(--border);
            display: flex; flex-direction: column; align-items: center; padding: 2rem 0; gap: 2rem;
        }
        .nav-item {
            width: 50px; height: 50px; border-radius: 1rem; display: flex;
            align-items: center; justify-content: center; cursor: pointer; color: var(--text-muted);
            transition: 0.3s;
        }
        .nav-item.active { background: var(--primary); color: white; }
        .nav-item:hover:not(.active) { background: var(--border); color: white; }

        /* Mesaj Listesi (Sol Panel) */
        .chat-list-panel { background: rgba(15, 23, 42, 0.5); border-right: 1px solid var(--border); overflow-y: auto; }
        .panel-header { padding: 2rem; position: sticky; top: 0; background: var(--bg); z-index: 10; }
        .search-bar { background: var(--border); padding: 0.8rem; border-radius: 1rem; display: flex; align-items: center; gap: 10px; }
        .search-bar input { padding: 0; border: none; background: transparent; font-size: 0.9rem; }

        .user-item {
            display: flex; align-items: center; gap: 15px; padding: 1.2rem 2rem;
            cursor: pointer; transition: 0.2s; border-left: 4px solid transparent;
        }
        .user-item:hover { background: var(--border); }
        .user-item.active { background: rgba(139, 92, 246, 0.1); border-left-color: var(--primary); }
        .avatar { width: 50px; height: 50px; border-radius: 50%; background: var(--primary); display: flex; align-items: center; justify-content: center; font-weight: bold; }

        /* Ana Mesajlaşma Alanı (Sağ Panel) */
        .main-chat { display: flex; flex-direction: column; background: url('https://user-images.githubusercontent.com/15075759/28719144-86dc0f70-73b1-11e7-911d-60d70fcded21.png'); background-blend-mode: overlay; }
        .chat-header { padding: 1.2rem 2rem; background: var(--glass); backdrop-filter: blur(10px); display: flex; align-items: center; justify-content: space-between; border-bottom: 1px solid var(--border); }
        
        .messages-container { flex: 1; padding: 2rem; overflow-y: auto; display: flex; flex-direction: column; gap: 1rem; }
        .msg { max-width: 60%; padding: 1rem; border-radius: 1.2rem; font-size: 0.95rem; line-height: 1.4; position: relative; }
        .msg-in { align-self: flex-start; background: var(--glass); border-bottom-left-radius: 0.2rem; }
        .msg-out { align-self: flex-end; background: var(--primary); border-bottom-right-radius: 0.2rem; }
        .msg-info { font-size: 0.7rem; color: var(--text-muted); margin-bottom: 4px; display: block; }

        .input-area { padding: 1.5rem 2rem; background: var(--bg); display: flex; gap: 1rem; align-items: center; }
        .input-area input { flex: 1; }

        /* Animasyonlar */
        .fade-in { animation: fadeIn 0.4s ease-out; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }

        /* Gizleme Sınıfı */
        .hidden { display: none !important; }
    </style>
</head>
<body>

    <div id="auth-screen">
        <div class="auth-card fade-in" id="login-box">
            <h1>NEXUS <span>SOCIAL</span></h1>
            <p>Devam etmek için giriş yapın.</p>
            <div class="input-group">
                <label>Kullanıcı Adı</label>
                <input type="text" id="auth-user" placeholder="Kullanıcı adınızı yazın...">
            </div>
            <div class="input-group">
                <label>Şifre</label>
                <input type="password" id="auth-pass" placeholder="••••••••">
            </div>
            <button class="auth-btn" onclick="handleAuth()">Giriş Yap / Kayıt Ol</button>
            <p style="margin-top: 1.5rem; font-size: 0.8rem;">Şifreniz yoksa otomatik kayıt olunur.</p>
        </div>
    </div>

    <div id="app">
        <div class="sidebar-icons">
            <div class="nav-item active" onclick="switchTab('global')">
                <span class="material-icons-sharp">public</span>
            </div>
            <div class="nav-item" onclick="switchTab('dm')">
                <span class="material-icons-sharp">forum</span>
            </div>
            <div class="nav-item" onclick="switchTab('profile')">
                <span class="material-icons-sharp">account_circle</span>
            </div>
            <div class="nav-item" style="margin-top: auto;" onclick="logout()">
                <span class="material-icons-sharp">logout</span>
            </div>
        </div>

        <div class="chat-list-panel">
            <div class="panel-header">
                <h2 id="panel-title">Global Chat</h2>
                <br>
                <div class="search-bar">
                    <span class="material-icons-sharp">search</span>
                    <input type="text" placeholder="Kullanıcı ara...">
                </div>
            </div>
            <div id="user-list">
                </div>
        </div>

        <div class="main-chat">
            <div class="chat-header">
                <div style="display: flex; align-items: center; gap: 15px;">
                    <div class="avatar" id="current-chat-avatar">#</div>
                    <div>
                        <h4 id="current-chat-name">Genel Meydan</h4>
                        <small style="color: var(--secondary)">Çevrimiçi</small>
                    </div>
                </div>
                <span class="material-icons-sharp">more_vert</span>
            </div>

            <div class="messages-container" id="chat-messages">
                </div>

            <div class="input-area">
                <button style="background:transparent; color: var(--text-muted); cursor:pointer"><span class="material-icons-sharp">add_circle</span></button>
                <input type="text" id="msg-input" placeholder="Mesajınızı yazın...">
                <button class="auth-btn" style="width: auto; padding: 0.8rem 1.5rem;" onclick="sendMessage()">Gönder</button>
            </div>
        </div>
    </div>

    <script>
        let currentUser = null;
        let activeTab = 'global';
        let activeDM = 'global';

        const mockUsers = [
            { id: 1, name: 'Asya Yıldız', lastMsg: 'Selam, nasılsın?' },
            { id: 2, name: 'Can Demir', lastMsg: 'Kodları gönderdin mi?' },
            { id: 3, name: 'Melis Kaya', lastMsg: 'Harika görünüyor!' }
        ];

        // --- AUTH MANTIĞI ---
        function handleAuth() {
            const user = document.getElementById('auth-user').value.trim();
            const pass = document.getElementById('auth-pass').value.trim();

            if(user.length < 3 || pass.length < 4) {
                alert("Lütfen geçerli bir kullanıcı adı (min 3) ve şifre (min 4) girin!");
                return;
            }

            currentUser = user;
            document.getElementById('auth-screen').classList.add('hidden');
            document.getElementById('app').style.display = 'grid';
            
            initApp();
        }

        function initApp() {
            loadGlobalChat();
            loadUserList();
        }

        // --- SEKME YÖNETİMİ ---
        function switchTab(tab) {
            activeTab = tab;
            document.querySelectorAll('.nav-item').forEach(el => el.classList.remove('active'));
            event.currentTarget.classList.add('active');

            const title = document.getElementById('panel-title');
            if(tab === 'global') {
                title.innerText = "Global Chat";
                openChat('global', 'Genel Meydan');
            } else if(tab === 'dm') {
                title.innerText = "Mesajlar";
                openChat(mockUsers[0].id, mockUsers[0].name);
            }
        }

        // --- MESAJLAŞMA MANTIĞI ---
        function openChat(id, name) {
            activeDM = id;
            document.getElementById('current-chat-name').innerText = name;
            document.getElementById('current-chat-avatar').innerText = name[0];
            document.getElementById('chat-messages').innerHTML = ""; // Temizle
            
            // Simüle edilmiş başlangıç mesajı
            addMessage("Sistem", `Hoş geldin ${currentUser}! Bu kanalın güvenli sohbeti başlatıldı.`, 'in');
        }

        function sendMessage() {
            const input = document.getElementById('msg-input');
            const text = input.value.trim();
            if(!text) return;

            addMessage(currentUser, text, 'out');
            input.value = "";

            // Simüle karşı cevap
            setTimeout(() => {
                if(activeDM === 'global') {
                    addMessage("Sistem Botu", "Global mesajın iletildi!", 'in');
                } else {
                    addMessage("Nexus AI", "Şu an meşgulüm, sonra konuşalım mı?", 'in');
                }
            }, 1000);
        }

        function addMessage(sender, text, type) {
            const container = document.getElementById('chat-messages');
            const msgDiv = document.createElement('div');
            msgDiv.className = `msg msg-${type} fade-in`;
            
            msgDiv.innerHTML = `
                <small class="msg-info">${sender} • ${new Date().toLocaleTimeString([], {hour: '2-digit', minute:'2-digit'})}</small>
                ${text}
            `;
            
            container.appendChild(msgDiv);
            container.scrollTop = container.scrollHeight;
        }

        // --- KULLANICI LİSTESİ ---
        function loadUserList() {
            const list = document.getElementById('user-list');
            list.innerHTML = "";
            mockUsers.forEach(u => {
                list.innerHTML += `
                    <div class="user-item" onclick="openChat(${u.id}, '${u.name}')">
                        <div class="avatar">${u.name[0]}</div>
                        <div style="flex:1">
                            <h4>${u.name}</h4>
                            <p style="color: var(--text-muted); font-size: 0.8rem;">${u.lastMsg}</p>
                        </div>
                    </div>
                `;
            });
        }

        function logout() {
            location.reload();
        }

        // Enter tuşu ile mesaj gönderme
        document.getElementById('msg-input').addEventListener('keypress', (e) => {
            if(e.key === 'Enter') sendMessage();
        });
    </script>
</body>
</html>
