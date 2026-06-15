<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Valorant Oyuncu Bulma | Premate Clone</title>
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
            <nav class="hidden md:flex space-x-6 text-sm font-semibold">
                <a href="#" class="text-red-500 border-b-2 border-red-500 pb-4 -mb-4 flex items-center space-x-2">
                    <i class="fa-solid fa-users"></i> <span>OYUNCU BUL</span>
                </a>
                <a href="#" class="text-gray-400 hover:text-white flex items-center space-x-2 transition">
                    <i class="fa-solid fa-gift"></i> <span>ÜCRETSİZ ÖDÜLLER</span>
                </a>
                <a href="#" class="text-gray-400 hover:text-white flex items-center space-x-2 transition">
                    <i class="fa-solid fa-crosshairs"></i> <span>NİŞANGAHLAR</span>
                </a>
            </nav>
        </div>
        <div class="flex items-center space-x-4">
            <div class="text-right text-xs">
                <p class="text-gray-400">User #101779</p>
                <span class="text-emerald-400 font-bold">LVL 5</span>
            </div>
            <div class="w-10 h-10 rounded-full border-2 border-emerald-500 bg-gray-700 flex items-center justify-center text-sm font-bold text-white">U</div>
        </div>
    </header>

    <main class="flex-1 max-w-[1600px] w-full mx-auto p-4 grid grid-cols-12 gap-4">
        
        <aside class="col-span-2 hidden lg:flex flex-col space-y-4">
            <div class="bg-gradient-to-b from-[#161a23] to-[#0f121a] border border-gray-800 rounded-xl p-4 relative overflow-hidden">
                <span class="bg-red-600 text-[10px] font-black text-white px-2 py-0.5 rounded uppercase">En Ucuz</span>
                <h3 class="text-lg font-black text-white mt-2 leading-tight">VALORANT PUANLARI</h3>
                <button class="w-full mt-4 bg-red-600 hover:bg-red-700 text-white font-bold text-xs py-2.5 rounded-lg transition uppercase">Hemen Satın Al</button>
            </div>
        </aside>

        <section class="col-span-12 lg:col-span-8 flex flex-col space-y-4">
            <div class="grid grid-cols-4 gap-3">
                <button class="bg-[#131720] hover:bg-[#181d29] border border-gray-800 p-3 rounded-xl flex flex-col items-center justify-center space-y-1 transition"><i class="fa-solid fa-shield-halved text-red-500"></i><span class="text-xs font-semibold">Şikayet Et</span></button>
                <button class="bg-[#131720] hover:bg-[#181d29] border border-gray-800 p-3 rounded-xl flex flex-col items-center justify-center space-y-1 transition"><i class="fa-solid fa-gift text-emerald-500"></i><span class="text-xs font-semibold">Ödüller</span></button>
                <button class="bg-[#131720] hover:bg-[#181d29] border border-gray-800 p-3 rounded-xl flex flex-col items-center justify-center space-y-1 transition"><i class="fa-solid fa-pie-chart text-amber-500"></i><span class="text-xs font-semibold">Rank Tahmin</span></button>
                <button class="bg-[#131720] hover:bg-[#181d29] border border-gray-800 p-3 rounded-xl flex flex-col items-center justify-center space-y-1 transition"><i class="fa-solid fa-comments text-blue-500"></i><span class="text-xs font-semibold">Sohbet</span></button>
            </div>

            <div class="bg-[#0f131a] border border-gray-800 rounded-xl overflow-hidden flex flex-col shadow-2xl">
                <div class="p-3 bg-[#131720] border-b border-gray-800 flex items-center justify-between text-xs text-gray-400">
                    <div>Oyun Modu: <span class="text-red-500 font-bold">Tüm Modlar</span></div>
                    <button class="text-gray-400 hover:text-white flex items-center space-x-1"><i class="fa-solid fa-rotate"></i> <span>YENİLE</span></button>
                </div>

                <div class="divide-y divide-gray-900/60" id="player-list">
                    <div class="p-4 flex items-center justify-between hover:bg-[#131720]/40 transition">
                        <div class="flex items-center space-x-3">
                            <div class="w-9 h-9 rounded-full bg-red-500/10 border border-red-500/30 flex items-center justify-center"><i class="fa-solid fa-user text-red-400 text-sm"></i></div>
                            <div>
                                <h4 class="text-sm font-bold text-gray-200">Vagas#4848 <span class="bg-red-500/10 text-red-400 text-[9px] px-1.5 py-0.5 rounded font-black ml-1">LVL 4</span></h4>
                                <p class="text-[11px] text-gray-500 mt-0.5">"Plat elo mikrofonlu beyler gelsin"</p>
                            </div>
                        </div>
                        <div class="flex items-center space-x-4 text-xs">
                            <span class="flex items-center space-x-1 text-amber-400 font-medium"><i class="fa-solid fa-trophy"></i> <span>Gold 3</span></span>
                            <span class="text-emerald-400 bg-emerald-500/10 px-2 py-0.5 rounded-full text-[10px] font-bold">● Açık</span>
                            <span class="bg-[#1b1518] text-red-400 px-2 py-1 rounded font-mono border border-red-950/50">#6J724</span>
                            <span class="bg-gray-800/80 px-2 py-1 rounded text-[10px] font-bold">RANKED</span>
                        </div>
                    </div>
                </div>

                <div class="p-4 bg-[#0f131a] border-t border-gray-950 flex justify-center">
                    <button id="open-modal-btn" class="bg-[#00f29b] hover:bg-[#00d689] text-slate-950 font-black px-8 py-3 rounded-xl text-sm tracking-wider shadow-lg shadow-emerald-500/10 transition flex items-center space-x-2 cursor-pointer">
                        <i class="fa-solid fa-plus text-base"></i>
                        <span>LOBİ OLUŞTUR</span>
                    </button>
                </div>
            </div>
        </section>

        <aside class="col-span-2 hidden lg:flex flex-col">
            <div class="bg-gradient-to-b from-[#181115] to-[#0f0e13] border border-red-900/30 rounded-xl p-4 text-center">
                <span class="bg-cyan-500/10 text-cyan-400 text-[10px] font-bold px-2 py-0.5 rounded uppercase">Hediye</span>
                <h3 class="text-sm font-black text-white mt-2">GTA OYNA VP KAZAN</h3>
            </div>
        </aside>
    </main>

    <div id="lobby-modal" class="fixed inset-0 bg-black/80 backdrop-blur-sm flex items-center justify-center z-50 opacity-0 pointer-events-none transition-opacity duration-300">
        <div class="bg-[#0f131a] border border-gray-800 w-full max-w-md rounded-2xl overflow-hidden shadow-2xl transform scale-95 transition-transform duration-300" id="modal-card">
            
            <div class="p-4 bg-[#131720] border-b border-gray-800 flex items-center justify-between">
                <h3 class="text-sm font-black tracking-wide text-white flex items-center space-x-2">
                    <i class="fa-solid fa-circle-plus text-emerald-400"></i>
                    <span>YENİ LOBİ OLUŞTUR</span>
                </h3>
                <button id="close-modal-btn" class="text-gray-500 hover:text-white transition cursor-pointer"><i class="fa-solid fa-xmark text-lg"></i></button>
            </div>

            <form id="lobby-form" class="p-5 space-y-4">
                <div>
                    <label class="block text-xs font-bold uppercase tracking-wider text-gray-400 mb-1">Riot ID & Etiket</label>
                    <input type="text" id="riot-id" required placeholder="Örn: Nickname#TR1" 
                        class="w-full bg-[#131720] border border-gray-800 rounded-lg px-3 py-2 text-sm text-white focus:outline-none focus:border-emerald-500 transition">
                </div>

                <div class="grid grid-cols-2 gap-3">
                    <div>
                        <label class="block text-xs font-bold uppercase tracking-wider text-gray-400 mb-1">Rankınız</label>
                        <select id="player-rank" class="w-full bg-[#131720] border border-gray-800 rounded-lg px-2 py-2 text-sm text-gray-300 focus:outline-none focus:border-emerald-500 transition">
                            <option value="Bronze">Bronze</option>
                            <option value="Silver">Silver</option>
                            <option value="Gold" selected>Gold</option>
                            <option value="Plat">Plat</option>
                            <option value="Diamond">Diamond</option>
                            <option value="Immortal">Immortal</option>
                        </select>
                    </div>
                    <div>
                        <label class="block text-xs font-bold uppercase tracking-wider text-gray-400 mb-1">Oyun Modu</label>
                        <select id="game-mode" class="w-full bg-[#131720] border border-gray-800 rounded-lg px-2 py-2 text-sm text-gray-300 focus:outline-none focus:border-emerald-500 transition">
                            <option value="RANKED">Dereceli (Ranked)</option>
                            <option value="UNRATED">Tam Gaz / Derecesiz</option>
                            <option value="PREMIER">Premier</option>
                        </select>
                    </div>
                </div>

                <div>
                    <label class="block text-xs font-bold uppercase tracking-wider text-gray-400 mb-1">Açıklama / İlan Notu</label>
                    <textarea id="lobby-desc" rows="2" placeholder="Mikrofon şart, info verenler gelsin..." 
                        class="w-full bg-[#131720] border border-gray-800 rounded-lg px-3 py-2 text-sm text-white focus:outline-none focus:border-emerald-500 transition resize-none"></textarea>
                </div>

                <div class="flex items-center space-x-3 pt-2">
                    <button type="button" id="cancel-modal-btn" class="flex-1 bg-gray-900 hover:bg-gray-800 text-gray-400 font-bold text-xs py-3 rounded-xl border border-gray-800 transition cursor-pointer">İPTAL</button>
                    <button type="submit" class="flex-1 bg-[#00f29b] hover:bg-[#00d689] text-slate-950 font-black text-xs py-3 rounded-xl tracking-wider transition shadow-lg shadow-emerald-500/10 cursor-pointer">LOBİ YAYINLA</button>
                </div>
            </form>
        </div>
    </div>

    <script>
        const modal = document.getElementById('lobby-modal');
        const modalCard = document.getElementById('modal-card');
        const openModalBtn = document.getElementById('open-modal-btn');
        const closeModalBtn = document.getElementById('close-modal-btn');
        const cancelModalBtn = document.getElementById('cancel-modal-btn');
        const lobbyForm = document.getElementById('lobby-form');
        const playerList = document.getElementById('player-list');

        // Modalı Aç
        function openModal() {
            modal.classList.remove('opacity-0', 'pointer-events-none');
            modalCard.classList.remove('scale-95');
            modalCard.classList.add('scale-100');
        }

        // Modalı Kapat
        function closeModal() {
            modal.classList.add('opacity-0', 'pointer-events-none');
            modalCard.classList.remove('scale-100');
            modalCard.classList.add('scale-95');
        }

        openModalBtn.addEventListener('click', openModal);
        closeModalBtn.addEventListener('click', closeModal);
        cancelModalBtn.addEventListener('click', closeModal);

        // Dışarı tıklanınca kapatma
        modal.addEventListener('click', (e) => {
            if(e.target === modal) closeModal();
        });

        // Yeni Lobi Ekleme Mantığı (Submit)
        lobbyForm.addEventListener('submit', function(e) {
            e.preventDefault(); // Sayfanın yenilenmesini engelle

            // Form verilerini al
            const riotId = document.getElementById('riot-id').value;
            const rank = document.getElementById('player-rank').value;
            const mode = document.getElementById('game-mode').value;
            const desc = document.getElementById('lobby-desc').value || "Oyuncu aranıyor...";
            
            // Rastgele bir oda kodu üret (#A182B gibi)
            const randomCode = "#" + Math.random().toString(36).substr(2, 5).toUpperCase();

            // Yeni lobi HTML satır şablonu
            const newLobbyRow = `
                <div class="p-4 flex items-center justify-between hover:bg-[#131720]/40 transition animate-fade-in">
                    <div class="flex items-center space-x-3">
                        <div class="w-9 h-9 rounded-full bg-emerald-500/10 border border-emerald-500/30 flex items-center justify-center">
                            <i class="fa-solid fa-user text-emerald-400 text-sm"></i>
                        </div>
                        <div>
                            <h4 class="text-sm font-bold text-white">${riotId} <span class="bg-emerald-500/10 text-emerald-400 text-[9px] px-1.5 py-0.5 rounded font-black ml-1">YENİ</span></h4>
                            <p class="text-[11px] text-gray-400 mt-0.5">"${desc}"</p>
                        </div>
                    </div>
                    <div class="flex items-center space-x-4 text-xs">
                        <span class="flex items-center space-x-1 text-cyan-400 font-medium"><i class="fa-solid fa-trophy"></i> <span>${rank}</span></span>
                        <span class="text-emerald-400 bg-emerald-500/10 px-2 py-0.5 rounded-full text-[10px] font-bold">● Açık</span>
                        <span class="bg-[#151b18] text-emerald-400 px-2 py-1 rounded font-mono border border-emerald-950/50">${randomCode}</span>
                        <span class="bg-gray-800/80 px-2 py-1 rounded text-[10px] font-bold">${mode}</span>
                    </div>
                </div>
            `;

            // Listeye en üst sıradan ekle
            playerList.insertAdjacentHTML('afterbegin', newLobbyRow);

            // Formu temizle ve modalı kapat
            lobbyForm.reset();
            closeModal();
        });
    </script>
</body>
</html>
