<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VANGUARD NEXUS | GLOBAL</title>
    
    <link href="https://fonts.googleapis.com/icon?family=Material+Icons+Sharp" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <link href="https://fonts.cdnfonts.com/css/valorant" rel="stylesheet">

    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.15.0/firebase-app-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.15.0/firebase-database-compat.js"></script>
    
    <style>
        /* --- CSS DEĞİŞKENLERİ (Modern Karanlık Tema) --- */
        :root {
            --v-purple: #8b5cf6; 
            --v-cyan: #06b6d4; 
            --v-pink: #ec4899;
            --color-primary: #8b5cf6; 
            --color-danger: #f43f5e; 
            --color-success: #10b981;
            --color-warning: #f59e0b; 
            --color-white: #f8fafc; 
            --color-info-dark: #94a3b8;
            --color-dark: #0f172a; 
            --color-light: rgba(255, 255, 255, 0.05);
            --color-background: #0b1120; 
            
            /* Glassmorphism Ayarları */
            --glass-bg: rgba(15, 23, 42, 0.6);
            --glass-border: 1px solid rgba(255, 255, 255, 0.1);
            --card-border-radius: 1.5rem;
            --box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.37);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; text-decoration: none; list-style: none; outline: none; }
        
        body { 
            background: var(--color-background); 
            color: var(--color-white);
            overflow-x: hidden; 
            font-family: 'Poppins', sans-serif; 
            background-image: radial-gradient(circle at 50% 0%, #1e1b4b 0%, var(--color-background) 70%);
            min-height: 100vh;
        }

        /* Özel Kaydırma Çubuğu */
        ::-webkit-scrollbar { width: 8px; }
        ::-webkit-scrollbar-track { background: transparent; }
        ::-webkit-scrollbar-thumb { background: var(--color-primary); border-radius: 10px; }

        /* --- AUTH SCREEN (Giriş / Kayıt Ekranı) --- */
        #auth-screen {
            background: rgba(11, 17, 32, 0.9);
            backdrop-filter: blur(10px);
            height: 100vh; width: 100%;
            position: fixed; z-index: 100000; display: flex; align-items: center; justify-content: center;
        }
        
        .auth-container { 
            background-color: var(--color-dark); 
            border-radius: 20px; 
            box-shadow: 0 15px 35px rgba(0,0,0,0.5); 
            position: relative; overflow: hidden; width: 768px; max-width: 95%; min-height: 480px; 
            border: var(--glass-border);
        }
        
        .form-container { position: absolute; top: 0; height: 100%; transition: all 0.6s ease-in-out; }
        .sign-in { left: 0; width: 50%; z-index: 2; }
        .auth-container.active .sign-in { transform: translateX(100%); }
        .sign-up { left: 0; width: 50%; opacity: 0; z-index: 1; }
        
        .auth-container.active .sign-up { 
            transform: translateX(100%); opacity: 1; z-index: 5; 
            animation: move 0.6s; 
        }
        
        @keyframes move { 0%, 49.99% { opacity: 0; z-index: 1; } 50%, 100% { opacity: 1; z-index: 5; } }
        
        form { 
            background-color: var(--color-dark); display: flex; align-items: center; justify-content: center; 
            flex-direction: column; padding: 0 40px; height: 100%; text-align: center; 
        }
        
        form h1 { font-family: 'VALORANT', sans-serif; color: var(--v-cyan); margin-bottom: 20px; letter-spacing: 2px;}
        
        .auth-input { 
            background-color: rgba(255, 255, 255, 0.05); color: var(--color-white); border: 1px solid rgba(255, 255, 255, 0.1); 
            margin: 8px 0; padding: 12px 15px; font-size: 13px; border-radius: 8px; width: 100%; 
            transition: 0.3s;
        }
        .auth-input:focus { border-color: var(--v-cyan); box-shadow: 0 0 10px rgba(6, 182, 212, 0.2); }
        
        .auth-btn { 
            background: linear-gradient(45deg, var(--v-purple), var(--v-cyan)); color: #fff; 
            font-size: 13px; padding: 12px 45px; border-radius: 8px; font-weight: 600; 
            cursor: pointer; text-transform: uppercase; margin-top: 15px; 
            transition: transform 0.2s, box-shadow 0.2s; border: none;
        }
        .auth-btn:hover { transform: translateY(-2px); box-shadow: 0 5px 15px rgba(139, 92, 246, 0.4); }
        
        .toggle-container { position: absolute; top: 0; left: 50%; width: 50%; height: 100%; overflow: hidden; transition: all 0.6s ease-in-out; z-index: 1000; }
        .auth-container.active .toggle-container { transform: translateX(-100%); border-radius: 0 150px 100px 0; }
        .toggle { background: linear-gradient(135deg, var(--v-purple), var(--v-cyan)); color: #fff; position: relative; left: -100%; height: 100%; width: 200%; transition: all 0.6s ease-in-out; }
        .auth-container.active .toggle { transform: translateX(50%); }
        .toggle-panel { position: absolute; width: 50%; height: 100%; display: flex; align-items: center; justify-content: center; flex-direction: column; padding: 0 30px; text-align: center; top: 0; transition: all 0.6s ease-in-out; }
        .toggle-left { transform: translateX(-200%); }
        .auth-container.active .toggle-left { transform: translateX(0); }
        .toggle-right { right: 0; }
        .auth-container.active .toggle-right { transform: translateX(200%); }
        .toggle-panel h1 { font-family: 'VALORANT', sans-serif; font-size: 2rem; margin-bottom: 15px; }

        /* --- DASHBOARD LAYOUT --- */
        #dashboard { 
            display: none; width: 96%; margin: 0 auto; gap: 1.8rem; grid-template-columns: 14rem auto 23rem;
            padding-top: 1.5rem;
        }

        aside { height: 100vh; position: sticky; top: 0;}
        aside .top { display: flex; align-items: center; justify-content: space-between; margin-bottom: 2rem; }
        aside .logo h2 { font-family: 'VALORANT'; color: var(--v-cyan); font-size: 1.8rem; text-shadow: 0 0 10px rgba(6, 182, 212, 0.3); }
        
        aside .sidebar { display: flex; flex-direction: column; gap: 0.5rem; }
        aside .sidebar a { 
            display: flex; color: var(--color-info-dark); margin-left: 0; padding: 1rem 1.5rem; 
            gap: 1rem; align-items: center; border-radius: 12px; transition: all 300ms ease; cursor: pointer; 
        }
        aside .sidebar a:hover { background: var(--color-light); color: var(--color-white); transform: translateX(5px); }
        aside .sidebar a.active { background: linear-gradient(90deg, rgba(139, 92, 246, 0.2), transparent); color: var(--color-primary); border-left: 4px solid var(--color-primary); }
        aside .sidebar a h3 { font-weight: 500; font-size: 0.9rem;}

        main { width: 100%; }
        main h1 { font-family: 'VALORANT'; margin-bottom: 1.5rem; color: var(--color-white); letter-spacing: 1px;}
        
        main .insights { display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 1.5rem; }
        main .insights > div { 
            background: var(--glass-bg); padding: 1.5rem; border-radius: var(--card-border-radius); 
            box-shadow: var(--box-shadow); border: var(--glass-border); transition: 0.3s; 
            cursor: pointer; text-align: center; backdrop-filter: blur(10px);
        }
        main .insights > div:hover { transform: translateY(-5px); border-color: var(--v-cyan); box-shadow: 0 10px 20px rgba(6, 182, 212, 0.2); }
        main .insights span { font-size: 2.5rem; margin-bottom: 0.5rem; display: inline-block; }
        main .insights h3 { font-size: 0.9rem; font-family: 'VALORANT'; letter-spacing: 1px; color: var(--color-white);}
        
        .chart-container { 
            background: var(--glass-bg); border-radius: var(--card-border-radius); padding: 1.5rem; 
            margin-top: 2rem; box-shadow: var(--box-shadow); border: var(--glass-border); 
            width: 100%; height: 350px; backdrop-filter: blur(10px);
        }

        .right { margin-top: 3.5rem; }
        .global-chat-modern { 
            background: var(--glass-bg); padding: 1.5rem; border-radius: var(--card-border-radius); 
            box-shadow: var(--box-shadow); border: var(--glass-border); height: 500px; 
            display: flex; flex-direction: column; backdrop-filter: blur(10px);
        }
        .global-chat-modern h3 { font-family: 'VALORANT'; margin-bottom: 1rem; color: var(--v-purple); text-align: center; letter-spacing: 1px;}
        
        #chat-messages { flex: 1; overflow-y: auto; font-size: 0.85rem; margin-bottom: 1rem; display: flex; flex-direction: column; gap: 8px;}
        .chat-msg { background: rgba(255,255,255,0.05); padding: 8px 12px; border-radius: 8px; border-left: 3px solid var(--v-cyan);}
        .chat-msg b { color: var(--v-cyan); }
        
        .chat-input-area { display: flex; gap: 0.8rem; border-top: 1px solid var(--color-light); padding-top: 1rem; }
        .chat-input-area input { 
            flex: 1; background: rgba(0,0,0,0.3); color: var(--color-white); padding: 0.8rem 1.2rem; 
            border-radius: 2rem; border: 1px solid rgba(255,255,255,0.1); 
        }
        .chat-input-area button { 
            background: var(--v-purple); width: 45px; height: 45px; border-radius: 50%; 
            display: flex; align-items: center; justify-content: center; cursor: pointer; 
            transition: 0.3s; color: white; border: none;
        }
        .chat-input-area button:hover { background: var(--v-cyan); transform: scale(1.1); }

        /* --- PARTICLE MORPH OVERLAY --- */
        #particle-overlay { display: none; position: fixed; inset: 0; background: #000; z-index: 500000; }
        #particle-canvas { display: block; width: 100vw; height: 100vh;}
        #particle-controls {
            position: absolute; top: 20px; right: 20px; background: rgba(15, 23, 42, 0.8);
            padding: 20px; border-radius: 15px; box-shadow: 0 0 20px rgba(6, 182, 212, 0.3);
            border: 1px solid rgba(255,255,255,0.1); backdrop-filter: blur(5px);
            z-index: 10; width: 250px; color: white; font-size: 0.85rem;
        }
        #particle-controls h2 { font-family: 'VALORANT'; font-size: 1.2rem; margin-bottom: 15px; color: var(--v-cyan); text-align: center;}
        #particle-controls input, #particle-controls select { 
            width: 100%; margin-bottom: 15px; background: rgba(0,0,0,0.5); color: white; 
            border: 1px solid rgba(255,255,255,0.2); padding: 8px; border-radius: 6px; 
        }
        #particle-controls button { 
            width: 100%; padding: 12px; background: linear-gradient(45deg, var(--v-cyan), var(--v-purple)); 
            border: none; color: white; cursor: pointer; margin-top: 5px; border-radius: 6px; font-weight: bold;
        }
        #exit-particle { background: #f43f5e !important; margin-top: 15px !important;}

        #cursor-glow { 
            position: fixed; width: 400px; height: 400px; 
            background: radial-gradient(circle, rgba(139, 92, 246, 0.15) 0%, transparent 60%); 
            pointer-events: none; z-index: 999999; transform: translate(-50%, -50%); 
            transition: width 0.2s, height 0.2s;
        }

        /* Responsive */
        @media screen and (max-width: 1200px) { #dashboard { grid-template-columns: 14rem auto; } .right { margin-top: 0; } }
        @media screen and (max-width: 992px) { #dashboard { grid-template-columns: 1fr; } aside { display: none; } }
        @media screen and (max-width: 600px) { main .insights { grid-template-columns: 1fr; } .auth-container { height: 100vh; border-radius: 0; } }
    </style>
</head>
<body>

    <div id="cursor-glow"></div>
    <audio id="bgMusic" loop src="https://files.catbox.moe/97p877.mp3"></audio>

    <div id="auth-screen">
        <div class="auth-container" id="auth-container">
            <div class="form-container sign-up">
                <form>
                    <h1>KAYIT OL</h1>
                    <input type="text" id="rName" class="auth-input" placeholder="Kullanıcı Adı">
                    <input type="password" id="rPass" class="auth-input" placeholder="Şifre">
                    <button type="button" class="auth-btn" onclick="handleRegister()">HESAP OLUŞTUR</button>
                </form>
            </div>
            <div class="form-container sign-in">
                <form>
                    <h1>GIRIS YAP</h1>
                    <input type="text" id="lName" class="auth-input" placeholder="Kullanıcı Adı">
                    <input type="password" id="lPass" class="auth-input" placeholder="Şifre">
                    <button type="button" class="auth-btn" onclick="doLogin()">SISTEME GIR</button>
                    <button type="button" class="auth-btn" onclick="doGuest()" style="background: rgba(255,255,255,0.1); color: #ccc; margin-top: 10px;">MISAFIR GIRISI</button>
                </form>
            </div>
            <div class="toggle-container">
                <div class="toggle">
                    <div class="toggle-panel toggle-left">
                        <h1>TEKRAR HOSGELDIN</h1>
                        <p style="margin-bottom: 20px; font-size: 0.9rem; color: #eee;">Kaldığın yerden devam etmek için giriş yap.</p>
                        <button class="auth-btn" id="loginBtn" style="border: 1px solid #fff; background: transparent;">GIRIS YAP</button>
                    </div>
                    <div class="toggle-panel toggle-right">
                        <h1>SISTEME KATIL</h1>
                        <p style="margin-bottom: 20px; font-size: 0.9rem; color: #eee;">Global ağın bir parçası olmak için hesap oluştur.</p>
                        <button class="auth-btn" id="registerBtn" style="border: 1px solid #fff; background: transparent;">KAYIT OL</button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div id="dashboard">
        <aside>
            <div class="top">
                <div class="logo"><h2>NEXUS</h2></div>
            </div>
            <div class="sidebar">
                <a class="active"><span class="material-icons-sharp">grid_view</span><h3>Dashboard</h3></a>
                <a onclick="openParticleMode()"><span class="material-icons-sharp">auto_fix_high</span><h3>Görsel Mod</h3></a>
                <a onclick="toggleMusic()"><span class="material-icons-sharp">music_note</span><h3 id="m-text">Müzik: Kapalı</h3></a>
                <a onclick="location.reload()"><span class="material-icons-sharp">logout</span><h3>Sistemden Çıkış</h3></a>
            </div>
        </aside>

        <main>
            <h1>SİSTEM PANELİ</h1>
            <div class="insights" id="main-grid">
                <div onclick="window.open('https://tracker.gg/valorant', '_blank')"><span class="material-icons-sharp" style="color:var(--v-cyan)">analytics</span><h3>STATÜ</h3></div>
                <div onclick="window.open('https://vcrdb.net/', '_blank')"><span class="material-icons-sharp" style="color:var(--v-cyan)">ads_click</span><h3>NİŞANGAH</h3></div>
                <div onclick="window.open('https://playvalorant.com/tr-tr/maps/', '_blank')"><span class="material-icons-sharp" style="color:var(--v-pink)">map</span><h3>HARİTALAR</h3></div>
                <div onclick="window.open('https://playvalorant.com/tr-tr/agents/', '_blank')"><span class="material-icons-sharp" style="color:var(--v-pink)">groups</span><h3>AJANLAR</h3></div>
            </div>
            <div class="chart-container">
                <h2 id="realtime-status" style="font-size: 1rem; margin-bottom: 1rem; font-family:'VALORANT'; color: var(--color-info-dark);">AĞ AKTİVİTESİ</h2>
                <canvas id="myChart"></canvas>
            </div>
        </main>

        <div class="right">
            <div class="global-chat-modern">
                <h3>GLOBAL AĞ</h3>
                <div id="chat-messages"></div>
                <div class="chat-input-area">
                    <input type="text" id="chatMsg" placeholder="Mesajınızı iletin..." onkeypress="if(event.key === 'Enter') sendChat()">
                    <button onclick="sendChat()"><span class="material-icons-sharp">send</span></button>
                </div>
            </div>
        </div>
    </div>

    <div id="particle-overlay">
        <canvas id="particle-canvas"></canvas>
        <div id="particle-controls">
            <h2>GÖRSEL MOTOR</h2>
            <label>Şekil Formu</label>
            <select id="shapeSelector">
                <option value="circle">Küre</option>
                <option value="square">Küp (Kare)</option>
                <option value="star">Yıldız</option>
                <option value="heart">Kalp</option>
            </select>
            
            <label>Parçacık Boyutu</label>
            <input type="range" id="particleSize" min="0.5" max="4" step="0.1" value="1.5">
            
            <label>Enerji Rengi</label>
            <input type="color" id="particleColor" value="#06b6d4">
            
            <label>Hız Frekansı</label>
            <input type="range" id="speed" min="0.01" max="0.2" step="0.01" value="0.05">
            
            <button id="randomShapeBtn" onclick="randomizeParticles()">Kaos Modu</button>
            <button id="exit-particle" onclick="closeParticleMode()">PANEL'E DÖN</button>
        </div>
    </div>

    <script>
        // --- 1. FIREBASE & AUTH LOGIC ---
        const config = { 
            apiKey: "AIzaSyBC_h0zpRSSGdzcbtGsq3Bh2WGKAgTrNKc", 
            authDomain: "vanguardnexus-a2871.firebaseapp.com", 
            databaseURL: "https://vanguardnexus-a2871-default-rtdb.firebaseio.com", 
            projectId: "vanguardnexus-a2871" 
        };
        firebase.initializeApp(config); 
        const db = firebase.database();
        
        // Panel Geçişleri
        document.getElementById('registerBtn').addEventListener('click', () => document.getElementById('auth-container').classList.add("active"));
        document.getElementById('loginBtn').addEventListener('click', () => document.getElementById('auth-container').classList.remove("active"));

        // Kayıt Olma İşlemi (Eksik olan fonksiyon eklendi)
        function handleRegister() {
            const u = document.getElementById("rName").value.trim();
            const p = document.getElementById("rPass").value.trim();
            
            if(u === "" || p === "") { alert("Lütfen tüm alanları doldurun."); return; }

            db.ref('users/' + u).once('value').then(s => {
                if(s.exists()) {
                    alert("Bu kullanıcı adı zaten alınmış!");
                } else {
                    db.ref('users/' + u).set({ password: p, isVip: false })
                    .then(() => {
                        alert("Kayıt başarılı! Lütfen giriş yapın.");
                        document.getElementById('auth-container').classList.remove("active");
                    });
                }
            });
        }

        // Giriş Yapma İşlemi
        function doLogin() {
            const u = document.getElementById("lName").value.trim();
            const p = document.getElementById("lPass").value.trim();
            
            if(u === "ADMIN" && p === "1200778") { loginSuccess(u, true); return; }
            
            db.ref('users/'+u).once('value').then(s => {
                if(s.exists() && s.val().password === p) loginSuccess(u, s.val().isVip);
                else alert("Kullanıcı adı veya şifre hatalı!");
            });
        }

        function doGuest() { loginSuccess("MİSAFİR_" + Math.floor(Math.random()*1000), false); }

        function loginSuccess(u, vip) {
            sessionStorage.setItem("user", u);
            document.getElementById("auth-screen").style.opacity = "0";
            setTimeout(() => {
                document.getElementById("auth-screen").style.display = "none";
                document.getElementById("dashboard").style.display = "grid";
                initChart();
            }, 500);
        }

        // --- 2. DASHBOARD İŞLEVLERİ (Chat, Grafik, Müzik) ---
        let myChartInstance;
        function initChart() {
            const ctx = document.getElementById('myChart').getContext('2d');
            // Mock data oluşturarak grafiğin dolu görünmesini sağladık
            const mockData = Array.from({length: 12}, () => Math.floor(Math.random() * 100) + 20);
            const mockLabels = ['10:00', '10:05', '10:10', '10:15', '10:20', '10:25', '10:30', '10:35', '10:40', '10:45', '10:50', 'Şimdi'];

            myChartInstance = new Chart(ctx, { 
                type: 'line', 
                data: { 
                    labels: mockLabels, 
                    datasets: [{ 
                        label: 'Sistem Yükü (%)', 
                        data: mockData, 
                        borderColor: '#06b6d4', 
                        backgroundColor: 'rgba(6, 182, 212, 0.2)',
                        borderWidth: 2,
                        fill: true,
                        tension: 0.4 // Yumuşak çizgiler
                    }] 
                }, 
                options: { 
                    responsive: true, maintainAspectRatio: false,
                    plugins: { legend: { display: false } },
                    scales: {
                        x: { grid: { color: 'rgba(255,255,255,0.05)' } },
                        y: { grid: { color: 'rgba(255,255,255,0.05)' }, min: 0, max: 150 }
                    }
                } 
            });
        }

        // Chat Sistemi
        function sendChat() { 
            const m = document.getElementById('chatMsg').value;
            const u = sessionStorage.getItem("user"); 
            if(m.trim()) { 
                db.ref('chat').push({u: u, m: m}); 
                document.getElementById('chatMsg').value = ""; 
            } 
        }
        
        db.ref('chat').limitToLast(15).on('value', s => { 
            const b = document.getElementById('chat-messages'); 
            b.innerHTML = ""; 
            s.forEach(c => { 
                b.innerHTML += `<div class="chat-msg"><b>${c.val().u}:</b> ${c.val().m}</div>`; 
            }); 
            b.scrollTop = b.scrollHeight; 
        });
        
        // Müzik
        let isPlaying = false;
        function toggleMusic() { 
            const m = document.getElementById('bgMusic'); 
            if(isPlaying) {
                m.pause();
            } else {
                m.volume = 0.3; // Sesi biraz kıstık, arka plan için daha iyi
                m.play();
            }
            document.getElementById('m-text').innerText = isPlaying ? "Müzik: Kapalı" : "Müzik: Çalıyor"; 
            isPlaying = !isPlaying; 
        }

        // İmleç Işığı
        window.addEventListener('mousemove', e => { 
            const g = document.getElementById('cursor-glow'); 
            g.style.left = e.clientX + 'px'; 
            g.style.top = e.clientY + 'px'; 
        });

        // --- 3. PARTICLE MORPH SİSTEMİ (Geliştirilmiş) ---
        const pCanvas = document.getElementById('particle-canvas');
        const pCtx = pCanvas.getContext('2d');
        let particles = [];
        let pAnimId;
        const numParticles = 2500; // FPS düşüşünü engellemek için hafif azalttım
        const mouse = { x: null, y: null, radius: 120, active: false };
        let currentParticleColor = "#06b6d4";

        function openParticleMode() {
            document.getElementById('particle-overlay').style.display = 'block';
            resizeCanvas();
            initParticles();
        }

        function closeParticleMode() {
            document.getElementById('particle-overlay').style.display = 'none';
            cancelAnimationFrame(pAnimId);
        }

        window.addEventListener('resize', () => {
            if(document.getElementById('particle-overlay').style.display === 'block'){
                resizeCanvas();
                updatePShape(document.getElementById('shapeSelector').value);
            }
        });

        function resizeCanvas() {
            pCanvas.width = window.innerWidth;
            pCanvas.height = window.innerHeight;
        }

        class Particle {
            constructor() {
                this.x = Math.random() * pCanvas.width;
                this.y = Math.random() * pCanvas.height;
                this.destX = this.x; this.destY = this.y;
                this.size = parseFloat(document.getElementById('particleSize').value); 
                this.speed = parseFloat(document.getElementById('speed').value);
            }
            draw() {
                pCtx.fillStyle = currentParticleColor;
                pCtx.beginPath();
                pCtx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                pCtx.fill();
            }
            update() {
                // Dinamik kontrolleri al
                this.size = parseFloat(document.getElementById('particleSize').value);
                this.speed = parseFloat(document.getElementById('speed').value);

                this.x += (this.destX - this.x) * this.speed;
                this.y += (this.destY - this.y) * this.speed;
                
                // Fare etkileşimi
                if (mouse.active) {
                    let dx = mouse.x - this.x; 
                    let dy = mouse.y - this.y;
                    let dist = Math.sqrt(dx*dx + dy*dy);
                    if (dist < mouse.radius) {
                        let force = (mouse.radius - dist) / mouse.radius;
                        this.x -= (dx/dist) * force * 15;
                        this.y -= (dy/dist) * force * 15;
                    }
                }
            }
        }

        function initParticles() {
            particles = [];
            for (let i = 0; i < numParticles; i++) particles.push(new Particle());
            updatePShape(document.getElementById('shapeSelector').value);
            animateP();
        }

        function updatePShape(shape) {
            const centerX = pCanvas.width / 2;
            const centerY = pCanvas.height / 2;
            const scale = Math.min(pCanvas.width, pCanvas.height) * 0.35;
            
            particles.forEach((p, i) => {
                let t = (i / numParticles) * Math.PI * 2;
                let x, y;

                if (shape === 'circle') { 
                    x = Math.cos(t) * scale; 
                    y = Math.sin(t) * scale; 
                }
                else if (shape === 'heart') {
                    x = 16 * Math.pow(Math.sin(t), 3);
                    y = -(13 * Math.cos(t) - 5 * Math.cos(2*t) - 2 * Math.cos(3*t) - Math.cos(4*t));
                    x *= (scale/18); y *= (scale/18);
                }
                else if (shape === 'square') {
                    // Kare matematiği
                    const side = Math.floor(i / (numParticles / 4));
                    const progress = (i % (numParticles / 4)) / (numParticles / 4);
                    const size = scale * 1.5;
                    
                    if(side === 0) { x = -size/2 + (size * progress); y = -size/2; } // Üst
                    else if(side === 1) { x = size/2; y = -size/2 + (size * progress); } // Sağ
                    else if(side === 2) { x = size/2 - (size * progress); y = size/2; } // Alt
                    else { x = -size/2; y = size/2 - (size * progress); } // Sol
                }
                else if (shape === 'star') {
                    // Yıldız matematiği
                    let spikes = 5;
                    let outerRadius = scale * 1.2;
                    let innerRadius = scale * 0.5;
                    
                    let rot = Math.PI / 2 * 3;
                    let step = Math.PI / spikes;
                    
                    let segment = i / numParticles * spikes * 2;
                    let currentSpike = Math.floor(segment);
                    let localProgress = segment - currentSpike;
                    
                    let angle1 = rot + currentSpike * step;
                    let angle2 = rot + (currentSpike + 1) * step;
                    
                    let r1 = (currentSpike % 2 === 0) ? outerRadius : innerRadius;
                    let r2 = (currentSpike % 2 === 0) ? innerRadius : outerRadius;
                    
                    let x1 = Math.cos(angle1) * r1;
                    let y1 = Math.sin(angle1) * r1;
                    let x2 = Math.cos(angle2) * r2;
                    let y2 = Math.sin(angle2) * r2;
                    
                    x = x1 + (x2 - x1) * localProgress;
                    y = y1 + (y2 - y1) * localProgress;
                }

                // Rastgele dağılım efekti (Çok pürüzsüz olmaması için hafif jitter)
                p.destX = centerX + x + (Math.random() - 0.5) * 10; 
                p.destY = centerY + y + (Math.random() - 0.5) * 10;
            });
        }

        function animateP() {
            // Arkasında iz bırakma efekti
            pCtx.fillStyle = 'rgba(11, 17, 32, 0.15)';
            pCtx.fillRect(0, 0, pCanvas.width, pCanvas.height);
            
            currentParticleColor = document.getElementById('particleColor').value;

            particles.forEach(p => { p.update(); p.draw(); });
            pAnimId = requestAnimationFrame(animateP);
        }

        function randomizeParticles() {
            const shapes = ['circle', 'square', 'star', 'heart'];
            const randomShape = shapes[Math.floor(Math.random() * shapes.length)];
            document.getElementById('shapeSelector').value = randomShape;
            
            // Rastgele Renk
            const randomColor = '#' + Math.floor(Math.random()*16777215).toString(16);
            document.getElementById('particleColor').value = randomColor;
            
            updatePShape(randomShape);
        }

        // Particle Eventleri
        pCanvas.addEventListener('mousemove', (e) => { mouse.x = e.x; mouse.y = e.y; mouse.active = true; });
        pCanvas.addEventListener('mouseleave', () => { mouse.active = false; });
        document.getElementById('shapeSelector').addEventListener('change', (e) => updatePShape(e.target.value));

    </script>
</body>
</html>
