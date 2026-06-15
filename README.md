<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Valorant Oyuncu Bulma | Canlı & Kalıcı</title>
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        body {
            background-color: #0b0e14;
            background-image: linear-gradient(rgba(18, 24, 38, 0.5) 1px, transparent 1px),
                              linear-gradient(90deg, rgba(18, 24, 38, 0.5) 1px, transparent 1px);
            background-size: 20px 20px;
        }
    </style>
</head>
<body class="text-gray-300 font-sans min-h-screen flex flex-col relative">

    <header class="border-b border-gray-800 bg-[#0f131a] px-6 py-3 flex items-center justify-between sticky top-0 z-40">
        <div class="flex items-center space-x-8">
            <div class="text-red-500 font-black text-xl tracking-wider flex items-center space-x-2">
                <i class="fa-solid fa-gamepad"></i>
                <span>PREMATE.<span class="text-white">GG</span></span>
            </div>
            <span class="text-xs bg-emerald-500/10 text-emerald-400 px-2 py-1 rounded border border-emerald-500/20 font-bold">CANLI BAĞLANTI AKTİF</span>
        </div>
    </header>

    <main class="flex-1 max-w-[1600px] w-full mx-auto p-4 grid grid-cols-12 gap-4">
        <section class="col-span-12 lg:col-span-10 lg:col-start-2 flex flex-col space-y-4">
            
            <div class="bg-[#0f131a] border border-gray-800 rounded-xl overflow-hidden flex flex-col shadow-2xl">
                <div class="p-3 bg-[#131720] border-b border-gray-800 flex items-center justify-between text-xs text-gray-400">
                    <div>Oyun Modu: <span class="text-red-500 font-bold">Tüm Modlar</span></div>
                    <div id="loading-status" class="text-gray-500">Lobiler yükleniyor...</div>
                </div>

                <div class="divide-y divide-gray-900/60" id="player-list">
                    </div>

                <div class="p-4 bg-[#0f131a] border-t border-gray-950 flex justify-center">
                    <button id="open-modal-btn" class="bg-[#00f29b] hover:bg-[#00d689] text-slate-950 font-black px-8 py-3 rounded-xl text-sm tracking-wider shadow-lg transition flex items-center space-x-2 cursor-pointer">
                        <i class="fa-solid fa-plus text-base"></i>
                        <span>LOBİ OLUŞTUR</span>
                    </button>
                </div>
            </div>
        </section>
    </main>

    <div id="lobby-modal" class="fixed inset-0 bg-black/80 backdrop-blur-sm flex items-center justify-center z-50 opacity-0 pointer-events-none transition-opacity duration-300">
        <div class="bg-[#0f131a] border border-gray-800 w-full max-w-md rounded-2xl overflow-hidden shadow-2xl transform scale-95 transition-transform duration-300" id="modal-card">
            <div class="p-4 bg-[#131720] border-b border-gray-800 flex items-center justify-between">
                <h3 class="text-sm font-black text-white">YENİ LOBİ OLUŞTUR</h3>
                <button id="close-modal-btn" class="text-gray-500 hover:text-white cursor-pointer"><i class="fa-solid fa-xmark text-lg"></i></button>
            </div>

            <form id="lobby-form" class="p-5 space-y-4">
                <div>
                    <label class="block text-xs font-bold text-gray-400 mb-1">Riot ID & Etiket</label>
                    <input type="text" id="riot-id" required placeholder="Örn: Nickname#TR1" class="w-full bg-[#131720] border border-gray-800 rounded-lg px-3 py-2 text-sm text-white focus:outline-none focus:border-emerald-500">
                </div>
                <div class="grid grid-cols-2 gap-3">
                    <div>
                        <label class="block text-xs font-bold text-gray-400 mb-1">Rankınız</label>
                        <select id="player-rank" class="w-full bg-[#131720] border border-gray-800 rounded-lg px-2 py-2 text-sm text-gray-300 focus:outline-none">
                            <option value="Bronze">Bronze</option>
                            <option value="Silver">Silver</option>
                            <option value="Gold" selected>Gold</option>
                            <option value="Plat">Plat</option>
                            <option value="Diamond">Diamond</option>
                            <option value="Immortal">Immortal</option>
                        </select>
                    </div>
                    <div>
                        <label class="block text-xs font-bold text-gray-400 mb-1">Oyun Modu</label>
                        <select id="game-mode" class="w-full bg-[#131720] border border-gray-800 rounded-lg px-2 py-2 text-sm text-gray-300 focus:outline-none">
                            <option value="RANKED">Dereceli</option>
                            <option value="UNRATED">Derecesiz</option>
                        </select>
                    </div>
                </div>
                <div>
                    <label class="block text-xs font-bold text-gray-400 mb-1">İlan Notu</label>
                    <textarea id="lobby-desc" rows="2" placeholder="Mikrofon şart..." class="w-full bg-[#131720] border border-gray-800 rounded-lg px-3 py-2 text-sm text-white focus:outline-none resize-none"></textarea>
                </div>
                <div class="flex items-center space-x-3 pt-2">
                    <button type="button" id="cancel-modal-btn" class="flex-1 bg-gray-900 text-gray-400 text-xs py-3 rounded-xl border border-gray-800">İPTAL</button>
                    <button type="submit" class="flex-1 bg-[#00f29b] text-slate-950 font-black text-xs py-3 rounded-xl shadow-lg">YAYINLA</button>
                </div>
            </form>
        </div>
    </div>

    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/10.8.0/firebase-app.js";
        import { getDatabase, ref, push, onValue } from "https://www.gstatic.com/firebasejs/10.8.0/firebase-database.js";

        // ⚠️ BURAYI KENDİ FIREBASE BİLGİLERİNLE DEĞİŞTİRMELİSİN (Aşağıdaki adımlara bak)
        const firebaseConfig = {
            apiKey: "AIzaSyYourKeyHere",
            authDomain: "projeniz.firebaseapp.com",
            databaseURL: "https://projeniz-default-rtdb.firebaseio.com",
            projectId: "projeniz",
            storageBucket: "projeniz.appspot.com",
            messagingSenderId: "123456789",
            appId: "1:123456:web:abcd"
        };

        // Firebase Başlat
        const app = initializeApp(firebaseConfig);
        const db = getDatabase(app);
        const lobbiesRef = ref(db, 'lobbies');

        // DOM Elemanları
        const modal = document.getElementById('lobby-modal');
        const modalCard = document.getElementById('modal-card');
        const openModalBtn = document.getElementById('open-modal-btn');
        const closeModalBtn = document.getElementById('close-modal-btn');
        const cancelModalBtn = document.getElementById('cancel-modal-btn');
        const lobbyForm = document.getElementById('lobby-form');
        const playerList = document.getElementById('player-list');
        const loadingStatus = document.getElementById('loading-status');

        // Modal Fonksiyonları
        openModalBtn.addEventListener('click', () => {
            modal.classList.remove('opacity-0', 'pointer-events-none');
            modalCard.classList.replace('scale-95', 'scale-100');
        });
        function closeModal() {
            modal.classList.add('opacity-0', 'pointer-events-none');
            modalCard.classList.replace('scale-100', 'scale-95');
        }
        closeModalBtn.addEventListener('click', closeModal);
        cancelModalBtn.addEventListener('click', closeModal);

        // VERİTABANINA YAZMA (Lobi Oluşturma)
        lobbyForm.addEventListener('submit', function(e) {
            e.preventDefault();

            const randomCode = "#" + Math.random().toString(36).substr(2, 5).toUpperCase();
            
            const newLobby = {
                riotId: document.getElementById('riot-id').value,
                rank: document.getElementById('player-rank').value,
                mode: document.getElementById('game-mode').value,
                desc: document.getElementById('lobby-desc').value || "Oyuncu aranıyor...",
                code: randomCode,
                timestamp: Date.now()
            };

            // Firebase'e gönder (Kalıcı olur)
            push(lobbiesRef, newLobby);

            lobbyForm.reset();
            closeModal();
        });

        // VERİTABANINDAN ANLIK OKUMA (Herkes İçin Listeleme)
        onValue(lobbiesRef, (snapshot) => {
            playerList.innerHTML = "";
            loadingStatus.textContent = "Canlı Güncellendi";
            
            const data = snapshot.val();
            if (data) {
                // Lobileri tarihe göre tersten sıralayıp ekrana bas (En yeni en üstte)
                const sortedLobbies = Object.values(data).sort((a, b) => b.timestamp - a.timestamp);
                
                sortedLobbies.forEach(lobby => {
                    const row = `
                        <div class="p-4 flex items-center justify-between hover:bg-[#131720]/40 transition">
                            <div class="flex items-center space-x-3">
                                <div class="w-9 h-9 rounded-full bg-emerald-500/10 border border-emerald-500/30 flex items-center justify-center">
                                    <i class="fa-solid fa-user text-emerald-400 text-sm"></i>
                                </div>
                                <div>
                                    <h4 class="text-sm font-bold text-white">${lobby.riotId}</h4>
                                    <p class="text-[11px] text-gray-400 mt-0.5">"${lobby.desc}"</p>
                                </div>
                            </div>
                            <div class="flex items-center space-x-4 text-xs">
                                <span class="flex items-center space-x-1 text-cyan-400 font-medium"><i class="fa-solid fa-trophy"></i> <span>${lobby.rank}</span></span>
                                <span class="text-emerald-400 bg-emerald-500/10 px-2 py-0.5 rounded-full text-[10px] font-bold">● Açık</span>
                                <span class="bg-[#151b18] text-emerald-400 px-2 py-1 rounded font-mono border border-emerald-950/50">${lobby.code}</span>
                                <span class="bg-gray-800/80 px-2 py-1 rounded text-[10px] font-bold">${lobby.mode}</span>
                            </div>
                        </div>
                    `;
                    playerList.insertAdjacentHTML('beforeend', row);
                });
            } else {
                playerList.innerHTML = `<div class="p-8 text-center text-gray-500 text-sm">Henüz aktif lobi yok. İlkini sen oluştur!</div>`;
            }
        });
    </script>
</body>
</html>
