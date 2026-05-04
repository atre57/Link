<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NEXUS | AI HUB</title>
    
    <link href="https://fonts.googleapis.com/icon?family=Material+Icons+Sharp" rel="stylesheet">
    <link href="https://fonts.cdnfonts.com/css/valorant" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">

    <script src="https://cdn.jsdelivr.net/npm/marked/marked.min.js"></script>
    
    <style>
        :root {
            --v-purple: #9333ea;
            --color-primary: #7380ec;
            --color-white: #fff;
            --color-dark: #363949;
            --color-light: rgba(132, 139, 200, 0.18);
            --color-background: #f6f6f9;
            --card-border-radius: 1.5rem;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Poppins', sans-serif; }
        body { background: var(--color-background); color: var(--color-dark); overflow: hidden; }
        .valorant { font-family: 'VALORANT', sans-serif; }

        /* Ana Panel Yapısı */
        #app-container {
            display: grid;
            grid-template-columns: 16rem auto;
            height: 100vh;
            gap: 1rem;
            padding: 1rem;
        }

        /* Sidebar */
        aside {
            background: var(--color-white);
            border-radius: var(--card-border-radius);
            display: flex;
            flex-direction: column;
            padding: 1.5rem;
            box-shadow: 0 1rem 2rem var(--color-light);
        }

        aside .logo { color: var(--v-purple); margin-bottom: 2rem; font-size: 1.5rem; text-align: center; }

        /* Chat Alanı */
        main {
            background: var(--color-white);
            border-radius: var(--card-border-radius);
            display: flex;
            flex-direction: column;
            box-shadow: 0 1rem 2rem var(--color-light);
            overflow: hidden;
            position: relative;
        }

        .chat-header {
            padding: 1rem 2rem;
            border-bottom: 1px solid var(--color-light);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        #chat-window {
            flex: 1;
            overflow-y: auto;
            padding: 2rem;
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .message {
            max-width: 80%;
            padding: 1rem;
            border-radius: 1rem;
            font-size: 0.9rem;
            line-height: 1.5;
        }

        .user-msg {
            align-self: flex-end;
            background: var(--v-purple);
            color: white;
            border-bottom-right-radius: 0;
        }

        .ai-msg {
            align-self: flex-start;
            background: var(--color-background);
            color: var(--color-dark);
            border-bottom-left-radius: 0;
        }

        /* Input Alanı */
        .input-area {
            padding: 1.5rem;
            display: flex;
            gap: 1rem;
            border-top: 1px solid var(--color-light);
        }

        input {
            flex: 1;
            padding: 1rem;
            border-radius: 0.8rem;
            border: 1px solid #ddd;
            outline: none;
        }

        button {
            background: var(--v-purple);
            color: white;
            border: none;
            padding: 0 1.5rem;
            border-radius: 0.8rem;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        button:hover { opacity: 0.9; }

        /* Markdown Styling */
        pre { background: #2d2d2d; color: #ccc; padding: 10px; border-radius: 5px; margin: 10px 0; overflow-x: auto; }
        code { font-family: monospace; }
    </style>
</head>
<body>

    <div id="app-container">
        <aside>
            <div class="logo valorant">NEXUS AI</div>
            <div style="font-size: 0.8rem; color: #7d8da1;">
                <p><b>Durum:</b> Çevrimiçi</p>
                <p><b>Model:</b> Gemini 1.5 Flash</p>
            </div>
            <div style="margin-top: auto;">
                <button onclick="location.reload()" style="width: 100%; padding: 0.8rem; background: #ff7782;">Çıkış Yap</button>
            </div>
        </aside>

        <main>
            <div class="chat-header">
                <h3 class="valorant">OPERASYON MERKEZİ</h3>
                <span class="material-icons-sharp" style="color: var(--v-purple);">verified</span>
            </div>

            <div id="chat-window">
                <div class="message ai-msg">Sistem hazır. Sana nasıl yardımcı olabilirim komutan?</div>
            </div>

            <div class="input-area">
                <input type="text" id="userInput" placeholder="Bir komut girin..." autocomplete="off">
                <button id="sendBtn"><span class="material-icons-sharp">send</span></button>
            </div>
        </main>
    </div>

    <script>
        // --- YAPILANDIRMA ---
        const CONFIG = {
            API_KEY: "AIzaSyDHWeVhntYyO64xJ8_EhEZZkAwehToyWe8", // Buraya yeni anahtarını koydum
            MODEL: "gemini-1.5-flash"
        };

        const chatWindow = document.getElementById('chat-window');
        const userInput = document.getElementById('userInput');
        const sendBtn = document.getElementById('sendBtn');

        async function sendMessage() {
            const text = userInput.value.trim();
            if (!text) return;

            // Kullanıcı mesajını ekle
            addMessage(text, 'user-msg');
            userInput.value = "";

            // Bekleme mesajı ekle
            const loaderId = "loader-" + Date.now();
            addMessage("Düşünülüyor...", 'ai-msg', loaderId);

            try {
                const response = await fetch(`https://generativelanguage.googleapis.com/v1beta/models/${CONFIG.MODEL}:generateContent?key=${CONFIG.API_KEY}`, {
                    method: "POST",
                    headers: { "Content-Type": "application/json" },
                    body: JSON.stringify({
                        contents: [{ parts: [{ text: text }] }]
                    })
                });

                const data = await response.json();
                const loaderElem = document.getElementById(loaderId);

                if (data.error) {
                    loaderElem.innerHTML = `<b style="color:red">Hata:</b> ${data.error.message}`;
                } else {
                    const aiResponse = data.candidates[0].content.parts[0].text;
                    loaderElem.innerHTML = marked.parse(aiResponse);
                }

            } catch (error) {
                document.getElementById(loaderId).innerText = "Bağlantı kurulamadı. İnterneti veya API anahtarını kontrol et.";
            }

            chatWindow.scrollTop = chatWindow.scrollHeight;
        }

        function addMessage(content, className, id = null) {
            const div = document.createElement('div');
            div.className = `message ${className}`;
            if (id) div.id = id;
            div.innerHTML = content;
            chatWindow.appendChild(div);
            chatWindow.scrollTop = chatWindow.scrollHeight;
        }

        // Tetikleyiciler
        sendBtn.addEventListener('click', sendMessage);
        userInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') sendMessage();
        });
    </script>
</body>
</html>
