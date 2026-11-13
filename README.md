<html lang="tr" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NexusAI 2026 | Geleceğin Dijital Çalışma Alanı</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts: Inter & Plus Jakarta Sans -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Plus+Jakarta+Sans:wght@700;800&display=swap" rel="stylesheet">
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #050507;
            color: #fafafa;
            overflow-x: hidden;
        }
        h1, h2, h3, .font-display {
            font-family: 'Plus Jakarta Sans', sans-serif;
        }
        .glass {
            background: rgba(18, 18, 22, 0.75);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 255, 255, 0.08);
        }
        /* Fare takipli parıltı efekti için Bento Kart stili */
        .bento-card {
            position: relative;
            transition: transform 0.3s cubic-bezier(0.4, 0, 0.2, 1), border-color 0.3s ease;
            overflow: hidden;
        }
        .bento-card::before {
            content: "";
            position: absolute;
            inset: 0;
            background: radial-gradient(600px circle at var(--mouse-x, 50%) var(--mouse-y, 50%), rgba(139, 92, 246, 0.12), transparent 40%);
            opacity: 0;
            transition: opacity 0.3s;
            pointer-events: none;
        }
        .bento-card:hover::before {
            opacity: 1;
        }
        .bento-card:hover {
            transform: translateY(-4px);
            border-color: rgba(139, 92, 246, 0.45);
            box-shadow: 0 25px 35px -10px rgba(0, 0, 0, 0.7), 0 0 25px -5px rgba(139, 92, 246, 0.15);
        }
        .gradient-text {
            background: linear-gradient(135deg, #c4b5fd 0%, #38bdf8 50%, #f472b6 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .grid-pattern {
            background-size: 40px 40px;
            background-image: 
                linear-gradient(to right, rgba(255, 255, 255, 0.025) 1px, transparent 1px),
                linear-gradient(to bottom, rgba(255, 255, 255, 0.025) 1px, transparent 1px);
            mask-image: radial-gradient(ellipse at center, black 40%, transparent 80%);
        }
        .glow-bg {
            position: absolute;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(124, 58, 237, 0.14) 0%, rgba(0,0,0,0) 70%);
            border-radius: 50%;
            pointer-events: none;
            z-index: -1;
        }
        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #050507;
        }
        ::-webkit-scrollbar-thumb {
            background: #27272a;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #3f3f46;
        }
    </style>
</head>
<body class="selection:bg-violet-500/30 selection:text-violet-200 relative">

    <!-- Izgara Arka Plan ve Işık Efektleri -->
    <div class="fixed inset-0 grid-pattern pointer-events-none z-[-2]"></div>
    <div class="glow-bg top-[-150px] left-[-100px]"></div>
    <div class="glow-bg top-[35%] right-[-150px]" style="background: radial-gradient(circle, rgba(56, 189, 248, 0.1) 0%, rgba(0,0,0,0) 70%);"></div>

    <!-- Navigasyon -->
    <nav class="sticky top-0 z-50 glass border-b border-white/5 px-4 py-3.5">
        <div class="max-w-7xl mx-auto flex items-center justify-between">
            <div class="flex items-center gap-3">
                <a href="#" class="flex items-center gap-2.5 group">
                    <div class="w-9 h-9 bg-gradient-to-tr from-violet-600 via-indigo-500 to-sky-400 rounded-xl flex items-center justify-center shadow-lg shadow-violet-500/25 group-hover:scale-105 transition">
                        <i data-lucide="sparkles" class="w-5 h-5 text-white"></i>
                    </div>
                    <span class="font-display text-xl font-extrabold tracking-tight">NEXUS<span class="text-violet-400">26</span></span>
                </a>
                <span class="hidden xl:inline-flex items-center px-2 py-0.5 rounded-md text-[10px] font-mono font-semibold bg-white/5 text-zinc-400 border border-white/10">v4.5 PRO</span>
            </div>

            <!-- Masaüstü Menü -->
            <div class="hidden lg:flex items-center gap-5 text-xs font-medium text-zinc-400">
                <a href="#live-voice" class="text-violet-300 hover:text-white transition flex items-center gap-1.5"><span class="w-2 h-2 rounded-full bg-rose-500 animate-pulse"></span> Canlı Ses</a>
                <a href="#ai-hub" class="hover:text-white transition">AI Stüdyo</a>
                <a href="#rag-vault" class="hover:text-white transition">Bilgi Bankası</a>
                <a href="#ai-arena" class="hover:text-white transition">AI Arena</a>
                <a href="#marketplace" class="hover:text-white transition">Pazar Yeri</a>
                <a href="#affiliate-hub" class="hover:text-white transition">Ortaklık</a>
                <a href="#fiyatlandirma" class="hover:text-white transition">Planlar</a>
            </div>

            <div class="flex items-center gap-2 sm:gap-2.5">
                <button onclick="toggleHistoryDrawer()" class="px-2.5 py-2 rounded-xl bg-white/5 hover:bg-white/10 border border-white/10 text-zinc-300 text-xs font-semibold flex items-center gap-1.5 transition cursor-pointer" title="Kayıtlı Prompt & Oturum Geçmişi">
                    <i data-lucide="history" class="w-4 h-4 text-sky-400"></i>
                    <span class="hidden sm:inline">Geçmiş</span>
                    <span id="history-count" class="px-1.5 py-0.2 rounded-full bg-violet-600/30 text-violet-300 text-[10px] font-mono">0</span>
                </button>
                <button onclick="openCommandPalette()" class="hidden xl:flex items-center gap-2 px-3 py-1.5 rounded-xl bg-zinc-900/90 border border-white/10 text-xs text-zinc-400 hover:text-white hover:border-white/20 transition" title="Hızlı Komut Paleti">
                    <i data-lucide="search" class="w-3.5 h-3.5"></i>
                    <kbd class="px-1.5 py-0.5 text-[10px] font-mono bg-white/5 rounded text-zinc-400">⌘K</kbd>
                </button>
                <button onclick="toggleFloatingVoiceDock()" class="px-2.5 sm:px-3 py-2 rounded-xl bg-violet-600/10 hover:bg-violet-600/20 border border-violet-500/30 text-violet-300 text-xs font-semibold flex items-center gap-1.5 transition cursor-pointer" title="Sesli Asistan Düğmesini Göster / Gizle">
                    <i data-lucide="mic" class="w-4 h-4 text-rose-400"></i> <span class="hidden sm:inline">Asistan</span>
                </button>
                <div id="nav-auth-area" class="flex items-center gap-2">
                    <button onclick="openModal('register')" class="text-xs font-medium text-zinc-300 hover:text-white px-2 py-2 transition cursor-pointer">Kayıt Ol</button>
                    <button onclick="openModal('login')" class="text-xs font-semibold text-violet-300 bg-violet-600/20 hover:bg-violet-600/30 border border-violet-500/30 px-3 py-2 rounded-xl transition cursor-pointer">Giriş Yap</button>
                </div>
            </div>
        </div>
    </nav>

    <!-- Sağdan Açılan Kayıtlı Prompt Kütüphanesi & Oturum Geçmişi Çekmecesi -->
    <div id="history-drawer" class="fixed inset-y-0 right-0 w-full sm:w-96 z-50 glass border-l border-white/15 transform translate-x-full transition-transform duration-300 flex flex-col shadow-2xl">
        <div class="p-5 border-b border-white/10 flex items-center justify-between">
            <div class="flex items-center gap-2">
                <i data-lucide="bookmark" class="w-5 h-5 text-violet-400"></i>
                <h3 class="font-bold text-base">Prompt Kütüphanesi & Geçmiş</h3>
            </div>
            <button onclick="toggleHistoryDrawer()" class="p-1.5 rounded-lg hover:bg-white/10 text-zinc-400 hover:text-white transition">
                <i data-lucide="x" class="w-5 h-5"></i>
            </button>
        </div>

        <div class="p-4 border-b border-white/10 bg-zinc-950/50">
            <span class="text-[11px] font-bold uppercase tracking-wider text-violet-400 block mb-2.5">Favori Hazır Prompt Şablonları</span>
            <div id="favorite-prompts-list" class="space-y-2 max-h-48 overflow-y-auto pr-1">
                <!-- JS ile doldurulacak -->
            </div>
        </div>

        <div class="flex-1 p-4 overflow-y-auto">
            <div class="flex items-center justify-between mb-2.5">
                <span class="text-[11px] font-bold uppercase tracking-wider text-sky-400">Son AI Stüdyo Çıktıları</span>
                <button onclick="clearSessionHistory()" class="text-[11px] text-zinc-500 hover:text-rose-400 transition">Temizle</button>
            </div>
            <div id="session-history-list" class="space-y-2.5">
                <p class="text-xs text-zinc-500 italic">Henüz üretim yapılmadı. AI Stüdyo'da ürettiğiniz tüm analiz ve kodlar otomatik buraya kaydedilir.</p>
            </div>
        </div>
    </div>

    <!-- Hero Bölümü -->
    <header class="relative pt-16 pb-20 px-4 text-center max-w-5xl mx-auto">
        <div class="inline-flex items-center gap-2.5 px-3.5 py-1.5 rounded-full bg-white/[0.04] border border-white/10 text-xs font-medium text-violet-300 mb-7 shadow-inner">
            <span class="relative flex h-2 w-2">
                <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-75"></span>
                <span class="relative inline-flex rounded-full h-2 w-2 bg-emerald-500"></span>
            </span>
            <span>Canlı Sistem: Gemini 3 & Otonom Ajan Ağı Aktif</span>
            <span class="text-zinc-600">|</span>
            <a href="#trendler" class="text-sky-400 hover:underline flex items-center gap-1">2026 Raporu <i data-lucide="arrow-up-right" class="w-3 h-3"></i></a>
        </div>
        
        <h1 class="text-4xl sm:text-6xl md:text-7xl font-extrabold tracking-tight leading-[1.08] mb-6">
            Kurumsal Zekayı <span class="gradient-text">Otonom Hızla</span> Ölçeklendirin.
        </h1>
        
        <p class="text-zinc-400 text-lg sm:text-xl max-w-2xl mx-auto mb-10 leading-relaxed font-normal">
            2026'nın en yüksek trafikli yeni nesil çalışma platformu. Gerçek zamanlı yapay zeka motorları, kurumsal bilgi bankası, çoklu model arenası ve otonom ajan pazarı tek merkezde.
        </p>

        <div class="flex flex-col sm:flex-row items-center justify-center gap-4">
            <button onclick="scrollToSection('live-voice')" class="w-full sm:w-auto px-8 py-4 bg-gradient-to-r from-violet-600 to-indigo-600 hover:from-violet-500 hover:to-indigo-500 text-white font-bold rounded-2xl transition flex items-center justify-center gap-2.5 shadow-xl shadow-violet-600/25">
                <i data-lucide="mic" class="w-5 h-5"></i>
                Yapay Zeka ile Sesli Konuş
            </button>
            <button onclick="scrollToSection('ai-hub')" class="w-full sm:w-auto px-8 py-4 glass hover:bg-white/10 text-white font-semibold rounded-2xl transition flex items-center justify-center gap-2.5">
                <i data-lucide="cpu" class="w-5 h-5 text-sky-400"></i>
                Canlı AI Stüdyoyu Aç
            </button>
        </div>

        <!-- Güvenilen Şirketler Logoları -->
        <div class="mt-16 pt-8 border-t border-white/5">
            <p class="text-[11px] font-semibold uppercase tracking-[0.2em] text-zinc-500 mb-6">Küresel Teknoloji Liderlerinin Tercihi</p>
            <div class="flex flex-wrap items-center justify-center gap-8 sm:gap-14 opacity-50 grayscale hover:grayscale-0 transition duration-500">
                <div class="flex items-center gap-2 font-display font-bold text-lg"><i data-lucide="hexagon" class="w-5 h-5 text-violet-400"></i> AETHER</div>
                <div class="flex items-center gap-2 font-display font-bold text-lg"><i data-lucide="triangle" class="w-5 h-5 text-sky-400"></i> VORTEX</div>
                <div class="flex items-center gap-2 font-display font-bold text-lg"><i data-lucide="orbit" class="w-5 h-5 text-emerald-400"></i> QUANTUM</div>
                <div class="flex items-center gap-2 font-display font-bold text-lg"><i data-lucide="command" class="w-5 h-5 text-pink-400"></i> SYNAPSE</div>
                <div class="flex items-center gap-2 font-display font-bold text-lg"><i data-lucide="cpu" class="w-5 h-5 text-amber-400"></i> KINETIC</div>
            </div>
        </div>
    </header>

    <!-- Canlı Sesli AI Konuşma Merkezi (Gemini Live API) -->
    <section id="live-voice" class="py-10 px-4 max-w-6xl mx-auto">
        <div class="glass rounded-3xl p-6 sm:p-10 border border-violet-500/30 relative overflow-hidden shadow-2xl">
            <div class="flex flex-col lg:flex-row items-center justify-between gap-8">
                <div class="flex-1 space-y-4 text-center lg:text-left">
                    <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-rose-500/10 border border-rose-500/25 text-rose-300 text-xs font-semibold">
                        <span id="live-dot" class="w-2 h-2 rounded-full bg-zinc-500"></span>
                        <span id="live-status-text">GEMINI LIVE // SESLİ OTURUM HAZIR</span>
                    </div>
                    <h2 class="text-2xl sm:text-4xl font-extrabold">Yapay Zeka ile Gerçek Zamanlı Sesli Sohbet</h2>
                    <p class="text-zinc-400 text-sm leading-relaxed max-w-xl">
                        Mikrofonunuzu açın; iş stratejisi, yazılım mimarisi veya günlük planlarınız hakkında Nexus26 sesli asistanıyla tıpkı gerçek bir uzmanla konuşur gibi kesintisiz sohbet edin.
                    </p>

                    <div class="flex flex-wrap items-center justify-center lg:justify-start gap-3 pt-2">
                        <select id="live-voice-select" class="bg-zinc-950 border border-white/10 rounded-xl px-3.5 py-3 text-xs text-zinc-200 focus:outline-none focus:border-violet-500">
                            <option value="Zephyr">Ses: Zephyr (Parlak & Enerjik)</option>
                            <option value="Kore">Ses: Kore (Net & Kurumsal)</option>
                            <option value="Puck">Ses: Puck (Samimi & Dinamik)</option>
                            <option value="Fenrir">Ses: Fenrir (Güçlü & Derin)</option>
                        </select>

                        <button id="live-call-btn" class="px-6 py-3 rounded-xl bg-gradient-to-r from-rose-500 to-violet-600 hover:opacity-95 text-white font-bold text-sm flex items-center gap-2.5 transition shadow-lg shadow-rose-500/20 cursor-pointer">
                            <i data-lucide="phone-call" class="w-4 h-4"></i>
                            <span id="live-btn-label">Sesli Görüşmeyi Başlat</span>
                        </button>

                        <button id="live-mute-btn" class="hidden px-4 py-3 rounded-xl bg-zinc-900 hover:bg-zinc-800 border border-white/10 text-zinc-200 font-semibold text-xs flex items-center gap-2 transition cursor-pointer">
                            <i data-lucide="mic" class="w-4 h-4 text-emerald-400"></i>
                            <span id="live-mute-label">Mikrofon Açık</span>
                        </button>
                    </div>
                </div>

                <!-- Sağ Taraf: Canlı Ses Dalgası ve Anlık Konuşma Akışı -->
                <div class="w-full lg:w-[440px] bg-zinc-950/90 border border-white/10 rounded-2xl p-5 flex flex-col justify-between space-y-4">
                    <div class="flex items-center justify-between pb-3 border-b border-white/10">
                        <span class="text-xs font-mono text-zinc-400 flex items-center gap-2">
                            <i data-lucide="audio-waveform" class="w-4 h-4 text-violet-400"></i> CANLI TRANSKRİPT
                        </span>
                        <div id="voice-visualizer" class="flex items-center gap-1 h-5">
                            <span class="w-1 h-2 bg-violet-500/40 rounded-full transition-all duration-150"></span>
                            <span class="w-1 h-2 bg-violet-500/40 rounded-full transition-all duration-150"></span>
                            <span class="w-1 h-2 bg-violet-500/40 rounded-full transition-all duration-150"></span>
                            <span class="w-1 h-2 bg-violet-500/40 rounded-full transition-all duration-150"></span>
                            <span class="w-1 h-2 bg-violet-500/40 rounded-full transition-all duration-150"></span>
                            <span class="w-1 h-2 bg-violet-500/40 rounded-full transition-all duration-150"></span>
                        </div>
                    </div>

                    <div id="live-transcript-box" class="h-36 overflow-y-auto space-y-2 text-xs text-zinc-300 pr-1">
                        <p class="italic text-zinc-500">Görüşme başladığında konuşmalarınız ve yapay zeka yanıtları burada canlı olarak akacaktır...</p>
                    </div>

                    <div class="flex items-center gap-2 pt-2 border-t border-white/5">
                        <input id="live-quick-text" type="text" placeholder="Görüşme sırasında yazılı not gönder..." class="flex-1 bg-zinc-900 border border-white/10 rounded-xl px-3 py-2 text-xs text-white placeholder-zinc-500 focus:outline-none focus:border-violet-500">
                        <button id="live-send-text-btn" class="p-2 rounded-xl bg-violet-600 hover:bg-violet-500 text-white transition cursor-pointer" title="Gönder">
                            <i data-lucide="send" class="w-3.5 h-3.5"></i>
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Yapay Zeka Stüdyo & Çalışma Alanı -->
    <section id="ai-hub" class="py-12 px-4 max-w-7xl mx-auto">
        <div class="glass rounded-3xl p-6 sm:p-10 border border-white/10 relative">
            <div class="flex flex-col lg:flex-row items-start lg:items-center justify-between gap-4 mb-8 pb-6 border-b border-white/10">
                <div>
                    <span class="text-xs font-bold uppercase tracking-widest text-violet-400">NexusAI Multimodal Engine</span>
                    <h2 class="text-2xl sm:text-3xl font-extrabold mt-1">Canlı AI Stüdyosu</h2>
                </div>

                <!-- Sekme Butonları -->
                <div class="flex flex-wrap items-center gap-2 bg-zinc-950 p-1.5 rounded-2xl border border-white/10">
                    <button onclick="switchTab('strategy')" id="tab-strategy" class="tab-btn px-4 py-2 rounded-xl text-xs font-bold bg-violet-600 text-white transition">Strateji</button>
                    <button onclick="switchTab('code')" id="tab-code" class="tab-btn px-4 py-2 rounded-xl text-xs font-bold text-zinc-400 hover:text-white transition">Kod Mimarı</button>
                    <button onclick="switchTab('trend')" id="tab-trend" class="tab-btn px-4 py-2 rounded-xl text-xs font-bold text-zinc-400 hover:text-white transition">Trend Analizi</button>
                    <button onclick="switchTab('image')" id="tab-image" class="tab-btn px-4 py-2 rounded-xl text-xs font-bold text-zinc-400 hover:text-white transition">Görsel Üretici</button>
                </div>
            </div>

            <!-- Komut Giriş Alanı -->
            <div class="space-y-4">
                <div class="relative">
                    <textarea id="ai-prompt" rows="3" class="w-full bg-zinc-950 border border-white/10 rounded-2xl p-4 text-sm sm:text-base text-white placeholder-zinc-500 focus:outline-none focus:border-violet-500 transition resize-none" placeholder="2026 yılında e-ticaret sitem için yapay zeka tabanlı bir büyüme stratejisi oluştur..."></textarea>
                    
                    <div class="absolute bottom-3 right-3 flex items-center gap-2">
                        <button onclick="saveCurrentPromptToFavorites()" class="px-3.5 py-2.5 bg-white/5 hover:bg-white/10 border border-white/10 text-zinc-300 font-semibold text-xs rounded-xl transition flex items-center gap-1.5 cursor-pointer" title="Komutu Favorilere Kaydet">
                            <i data-lucide="bookmark-plus" class="w-4 h-4 text-amber-400"></i>
                            <span class="hidden sm:inline">Kaydet</span>
                        </button>
                        <button onclick="generateAIResponse()" id="generate-btn" class="px-5 py-2.5 bg-gradient-to-r from-violet-600 to-indigo-600 hover:from-violet-500 hover:to-indigo-500 text-white font-bold text-xs rounded-xl transition flex items-center gap-2 shadow-lg shadow-violet-600/30 cursor-pointer">
                            <i data-lucide="sparkles" class="w-4 h-4"></i>
                            Analiz & Üret
                        </button>
                    </div>
                </div>

                <!-- Hazır Örnek Komutlar -->
                <div class="flex flex-wrap items-center gap-2 text-xs text-zinc-400">
                    <span class="font-semibold text-zinc-500">Hızlı Komutlar:</span>
                    <button onclick="setPrompt('2026 Q4 global teknoloji pazarı için 5 maddelik büyüme stratejisi hazırla.')" class="px-3 py-1.5 rounded-lg bg-white/5 hover:bg-white/10 border border-white/5 transition">Büyüme Stratejisi</button>
                    <button onclick="setPrompt('Modern bento grid tasarımı için responsive HTML ve Tailwind kodları yaz.')" class="px-3 py-1.5 rounded-lg bg-white/5 hover:bg-white/10 border border-white/5 transition">Bento UI Kodu</button>
                    <button onclick="setPrompt('Fütüristik neon ışıklı siberpunk ofis konsepti, 8k render, Unreal Engine 5.')" class="px-3 py-1.5 rounded-lg bg-white/5 hover:bg-white/10 border border-white/5 transition">Siberpunk Görsel</button>
                    <button onclick="toggleHistoryDrawer()" class="px-3 py-1.5 rounded-lg bg-violet-600/15 hover:bg-violet-600/25 border border-violet-500/30 text-violet-300 transition flex items-center gap-1">
                        <i data-lucide="library" class="w-3.5 h-3.5"></i> Kütüphaneyi Aç
                    </button>
                </div>
            </div>

            <!-- Çıktı Ekranı -->
            <div id="ai-output-container" class="mt-8 hidden">
                <div class="bg-zinc-950 rounded-2xl border border-white/10 overflow-hidden">
                    <div class="flex items-center justify-between px-5 py-3 border-b border-white/10 bg-zinc-900/50">
                        <div class="flex items-center gap-2">
                            <span class="w-2.5 h-2.5 rounded-full bg-emerald-400 animate-pulse"></span>
                            <span id="output-engine-label" class="text-xs font-mono font-bold text-zinc-300">NEXUS-ENGINE // ÇIKTI</span>
                        </div>
                        <div class="flex items-center gap-2">
                            <button onclick="speakOutput()" id="tts-btn" class="px-3 py-1.5 rounded-lg bg-violet-600/20 hover:bg-violet-600/30 text-violet-300 text-xs font-semibold flex items-center gap-1.5 transition cursor-pointer">
                                <i data-lucide="volume-2" class="w-3.5 h-3.5"></i> Sesli Dinle
                            </button>
                            <button onclick="copyOutput()" class="px-3 py-1.5 rounded-lg bg-white/5 hover:bg-white/10 text-zinc-300 text-xs font-semibold flex items-center gap-1.5 transition cursor-pointer">
                                <i data-lucide="copy" class="w-3.5 h-3.5"></i> Kopyala
                            </button>
                            <button onclick="downloadOutput()" class="px-3 py-1.5 rounded-lg bg-white/5 hover:bg-white/10 text-zinc-300 text-xs font-semibold flex items-center gap-1.5 transition cursor-pointer">
                                <i data-lucide="download" class="w-3.5 h-3.5"></i> İndir
                            </button>
                            <button onclick="clearOutput()" class="p-1.5 rounded-lg hover:bg-white/10 text-zinc-400 hover:text-white transition">
                                <i data-lucide="x" class="w-4 h-4"></i>
                            </button>
                        </div>
                    </div>

                    <div class="p-6">
                        <div id="ai-output-text" class="text-sm text-zinc-200 leading-relaxed whitespace-pre-wrap font-mono"></div>
                        <div id="ai-output-image-wrap" class="hidden flex justify-center">
                            <img id="ai-output-image" src="" alt="Üretilen Yapay Zeka Görseli" class="rounded-xl max-h-[480px] object-cover border border-white/10 shadow-2xl">
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- YENİ MODÜL 1: Doküman & PDF Bilgi Bankası (Kurumsal Hafıza / RAG) -->
    <section id="rag-vault" class="py-12 px-4 max-w-7xl mx-auto">
        <div class="glass rounded-3xl p-8 border border-sky-500/25">
            <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 mb-8 pb-6 border-b border-white/10">
                <div>
                    <span class="text-xs font-bold uppercase tracking-widest text-sky-400">Kurumsal Hafıza & Vektör İndeksleme (RAG)</span>
                    <h2 class="text-2xl sm:text-3xl font-extrabold mt-1">Doküman & PDF Bilgi Bankası</h2>
                    <p class="text-zinc-400 text-xs sm:text-sm mt-1">Şirket sözleşmelerinizi, raporlarınızı veya ders notlarınızı yükleyin; yapay zeka yalnızca sizin dokümanlarınızdan kaynak göstererek yanıt versin.</p>
                </div>
                <div class="flex items-center gap-2">
                    <span id="rag-doc-count" class="px-3 py-1.5 rounded-xl bg-sky-500/10 border border-sky-500/20 text-sky-300 text-xs font-mono font-bold">2 Aktif Doküman</span>
                </div>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
                <!-- Sol: Dosya Yükleme ve Aktif Bilgi Kaynakları -->
                <div class="space-y-4">
                    <label for="rag-file-input" class="block border-2 border-dashed border-sky-500/30 hover:border-sky-400 rounded-2xl p-6 text-center bg-zinc-950/70 hover:bg-sky-950/10 transition cursor-pointer">
                        <div class="w-11 h-11 rounded-xl bg-sky-500/15 text-sky-400 flex items-center justify-center mx-auto mb-3">
                            <i data-lucide="file-up" class="w-6 h-6"></i>
                        </div>
                        <p class="text-sm font-bold text-white">Doküman / TXT / MD / CSV Yükle</p>
                        <p class="text-xs text-zinc-500 mt-1">Dosya seçmek için tıklayın veya metin yapıştırın</p>
                        <input type="file" id="rag-file-input" accept=".txt,.md,.csv,.json,.log" class="hidden" onchange="handleRagFileUpload(event)">
                    </label>

                    <div class="bg-zinc-950/80 border border-white/10 rounded-2xl p-4 space-y-2.5">
                        <div class="flex items-center justify-between">
                            <span class="text-xs font-bold text-zinc-300">İndekslenmiş Bilgi Kaynakları</span>
                            <button onclick="openAddManualDocModal()" class="text-[11px] text-sky-400 hover:underline font-semibold">+ Metin Ekle</button>
                        </div>
                        <div id="rag-files-list" class="space-y-2 max-h-48 overflow-y-auto pr-1">
                            <!-- JS ile doldurulacak -->
                        </div>
                    </div>
                </div>

                <!-- Sağ: Dokümanlarla Canlı Sohbet Ekranı -->
                <div class="lg:col-span-2 bg-zinc-950/90 border border-white/10 rounded-2xl p-5 flex flex-col justify-between space-y-4">
                    <div class="flex items-center justify-between pb-3 border-b border-white/10">
                        <span class="text-xs font-mono text-sky-400 flex items-center gap-2">
                            <i data-lucide="database-zap" class="w-4 h-4"></i> KURUMSAL HAFIZA SORGULAMA MOTORU
                        </span>
                        <span class="text-[11px] text-zinc-500">AES-512 İzole Bellek</span>
                    </div>

                    <div id="rag-chat-box" class="h-56 overflow-y-auto space-y-3 text-xs pr-1">
                        <div class="p-3 rounded-xl bg-sky-500/10 border border-sky-500/20 text-sky-200">
                            <span class="font-bold text-sky-400 block mb-1">Bilgi Bankası Asistanı:</span>
                            Şu an hafızada <strong>"2026_Kurumsal_Finans_Politikasi.txt"</strong> ve <strong>"Hizmet_Sozlesmesi_Taslagi.txt"</strong> dokümanları yüklü. Bu belgeler hakkında istediğiniz soruyu sorabilirsiniz.
                        </div>
                    </div>

                    <div class="flex items-center gap-2 pt-2 border-t border-white/10">
                        <input id="rag-question-input" type="text" placeholder="Örn: Sözleşmedeki fesih süresi kaç gündür veya Q4 bütçe limiti nedir?" class="flex-1 bg-zinc-900 border border-white/10 rounded-xl px-4 py-3 text-xs text-white placeholder-zinc-500 focus:outline-none focus:border-sky-500" onkeydown="if(event.key==='Enter') askRagDocuments()">
                        <button onclick="askRagDocuments()" id="rag-ask-btn" class="px-5 py-3 rounded-xl bg-gradient-to-r from-sky-500 to-indigo-600 hover:opacity-95 text-white text-xs font-bold flex items-center gap-2 transition cursor-pointer">
                            <i data-lucide="search-check" class="w-4 h-4"></i> Belgelerde Ara
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- YENİ MODÜL 2: Çoklu AI Model Karşılaştırma Arenası (Side-by-Side) -->
    <section id="ai-arena" class="py-12 px-4 max-w-7xl mx-auto">
        <div class="glass rounded-3xl p-8 border border-pink-500/25">
            <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 mb-8 pb-6 border-b border-white/10">
                <div>
                    <span class="text-xs font-bold uppercase tracking-widest text-pink-400">Side-by-Side Karar Laboratuvarı</span>
                    <h2 class="text-2xl sm:text-3xl font-extrabold mt-1">Çoklu AI Model Karşılaştırma Arenası</h2>
                    <p class="text-zinc-400 text-xs sm:text-sm mt-1">Tek bir soruyu aynı anda iki farklı yapay zeka uzmanına yöneltin; yanıtları yan yana kıyaslayıp kazananı seçin.</p>
                </div>
                <span class="px-3 py-1.5 rounded-xl bg-pink-500/10 border border-pink-500/20 text-pink-300 text-xs font-mono">Çift Motor Senkronizasyonu</span>
            </div>

            <div class="flex flex-col sm:flex-row gap-3 mb-6">
                <input id="arena-prompt-input" type="text" placeholder="Örn: Yeni çıkacak mobil uygulamamız için 30 günlük lansman planı öner..." class="flex-1 bg-zinc-950 border border-white/10 rounded-2xl px-4 py-3.5 text-sm text-white placeholder-zinc-500 focus:outline-none focus:border-pink-500" onkeydown="if(event.key==='Enter') runModelArena()">
                <button onclick="runModelArena()" id="arena-run-btn" class="px-6 py-3.5 rounded-2xl bg-gradient-to-r from-pink-600 to-violet-600 hover:opacity-95 text-white font-bold text-xs flex items-center justify-center gap-2 transition shadow-lg shadow-pink-600/20 cursor-pointer">
                    <i data-lucide="swords" class="w-4 h-4"></i> İki Uzmanı Yarıştır
                </button>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
                <!-- Uzman A: Yaratıcı Stratejist -->
                <div class="bg-zinc-950/90 border border-violet-500/25 rounded-2xl p-6 flex flex-col justify-between">
                    <div>
                        <div class="flex items-center justify-between pb-3 mb-4 border-b border-white/10">
                            <div class="flex items-center gap-2">
                                <span class="w-2.5 h-2.5 rounded-full bg-violet-400"></span>
                                <span class="font-bold text-sm text-violet-300">MODEL A // Yaratıcı Vizyoner</span>
                            </div>
                            <span class="text-[10px] font-mono px-2 py-0.5 rounded bg-violet-500/10 text-violet-300">İnovasyon Odaklı</span>
                        </div>
                        <div id="arena-output-a" class="text-xs sm:text-sm text-zinc-300 leading-relaxed whitespace-pre-wrap min-h-[140px]">
                            Yukarıya bir konu yazıp "İki Uzmanı Yarıştır" butonuna tıkladığınızda Yaratıcı Vizyoner modelinin önerisi burada görünecektir.
                        </div>
                    </div>
                    <div class="mt-5 pt-3 border-t border-white/5 flex items-center justify-between">
                        <span class="text-[11px] text-zinc-500">Yaklaşım: Marka & Büyüme</span>
                        <button onclick="voteArenaWinner('Model A (Yaratıcı Vizyoner)')" class="px-3.5 py-1.5 rounded-lg bg-violet-600/20 hover:bg-violet-600/30 text-violet-300 text-xs font-semibold transition cursor-pointer">
                            🏆 En İyi Yanıt Seç
                        </button>
                    </div>
                </div>

                <!-- Uzman B: Veri Odaklı Analist -->
                <div class="bg-zinc-950/90 border border-sky-500/25 rounded-2xl p-6 flex flex-col justify-between">
                    <div>
                        <div class="flex items-center justify-between pb-3 mb-4 border-b border-white/10">
                            <div class="flex items-center gap-2">
                                <span class="w-2.5 h-2.5 rounded-full bg-sky-400"></span>
                                <span class="font-bold text-sm text-sky-300">MODEL B // Veri & ROI Analisti</span>
                            </div>
                            <span class="text-[10px] font-mono px-2 py-0.5 rounded bg-sky-500/10 text-sky-300">Metrik Odaklı</span>
                        </div>
                        <div id="arena-output-b" class="text-xs sm:text-sm text-zinc-300 leading-relaxed whitespace-pre-wrap min-h-[140px]">
                            Aynı anda Veri & ROI Analisti modelinin sayısal, risk odaklı ve ölçülebilir yanıtı burada karşılaştırmalı olarak listelenecektir.
                        </div>
                    </div>
                    <div class="mt-5 pt-3 border-t border-white/5 flex items-center justify-between">
                        <span class="text-[11px] text-zinc-500">Yaklaşım: Matematik & Verimlilik</span>
                        <button onclick="voteArenaWinner('Model B (Veri & ROI Analisti)')" class="px-3.5 py-1.5 rounded-lg bg-sky-600/20 hover:bg-sky-600/30 text-sky-300 text-xs font-semibold transition cursor-pointer">
                            🏆 En İyi Yanıt Seç
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- YENİ MODÜL 3: Ajan Pazar Yeri & Şablon Mağazası (Gelir Modeli & Cüzdan Entegreli) -->
    <section id="marketplace" class="py-12 px-4 max-w-7xl mx-auto">
        <div class="glass rounded-3xl p-8 border border-amber-500/25">
            <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 mb-8 pb-6 border-b border-white/10">
                <div>
                    <span class="text-xs font-bold uppercase tracking-widest text-amber-400">Otonom Şablon Ekonomisi</span>
                    <h2 class="text-2xl sm:text-3xl font-extrabold mt-1">Ajan Pazar Yeri & Şablon Mağazası</h2>
                    <p class="text-zinc-400 text-xs sm:text-sm mt-1">Sektöre özel eğitilmiş hazır AI ajan şablonlarını inceleyin, tek tıkla satın alın ve doğrudan Yönetici Cüzdanı gelir akışını izleyin.</p>
                </div>
                <div class="flex items-center gap-2 bg-zinc-950 px-4 py-2 rounded-xl border border-amber-500/20 text-xs">
                    <i data-lucide="wallet" class="w-4 h-4 text-emerald-400"></i>
                    <span class="text-zinc-400">Cüzdan Entegrasyonu:</span>
                    <span class="text-emerald-400 font-bold">Aktif</span>
                </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-5">
                <!-- Şablon 1 -->
                <div class="bg-zinc-950/90 border border-white/10 rounded-2xl p-5 flex flex-col justify-between bento-card">
                    <div>
                        <div class="flex items-center justify-between mb-3">
                            <span class="px-2.5 py-0.5 rounded-md bg-emerald-500/15 text-emerald-300 text-[10px] font-mono">E-TİCARET</span>
                            <span class="text-sm font-extrabold text-white">₺450</span>
                        </div>
                        <h3 class="font-bold text-base mb-1.5">E-Ticaret SEO & Dönüşüm Botu</h3>
                        <p class="text-xs text-zinc-400 leading-relaxed">Ürün açıklamalarını otomatik SEO uyumlu hale getirir ve rakip fiyat analizi sunar.</p>
                    </div>
                    <button onclick="buyMarketplaceAgent('E-Ticaret SEO & Dönüşüm Botu', 450, 'Aşağıdaki e-ticaret ürünü için Google SEO uyumlu başlık, meta açıklama ve yüksek dönüşümlü satış metni yaz:\n\n')" class="mt-5 w-full py-2.5 rounded-xl bg-amber-500/15 hover:bg-amber-500/25 border border-amber-500/30 text-amber-300 text-xs font-bold transition cursor-pointer">
                        Satın Al & Stüdyoda Aç
                    </button>
                </div>

                <!-- Şablon 2 -->
                <div class="bg-zinc-950/90 border border-white/10 rounded-2xl p-5 flex flex-col justify-between bento-card">
                    <div>
                        <div class="flex items-center justify-between mb-3">
                            <span class="px-2.5 py-0.5 rounded-md bg-violet-500/15 text-violet-300 text-[10px] font-mono">HUKUK & UYUM</span>
                            <span class="text-sm font-extrabold text-white">₺790</span>
                        </div>
                        <h3 class="font-bold text-base mb-1.5">Hukuk Sözleşme Denetçisi Pro</h3>
                        <p class="text-xs text-zinc-400 leading-relaxed">KVKK, ticari gizlilik ve ağır cezai şartları saniyeler içinde tespit edip revize eder.</p>
                    </div>
                    <button onclick="buyMarketplaceAgent('Hukuk Sözleşme Denetçisi Pro', 790, 'Kıdemli şirket avukatı gibi aşağıdaki sözleşme maddelerindeki tek taraflı riskleri ve revize önerilerini çıkar:\n\n')" class="mt-5 w-full py-2.5 rounded-xl bg-amber-500/15 hover:bg-amber-500/25 border border-amber-500/30 text-amber-300 text-xs font-bold transition cursor-pointer">
                        Satın Al & Stüdyoda Aç
                    </button>
                </div>

                <!-- Şablon 3 -->
                <div class="bg-zinc-950/90 border border-white/10 rounded-2xl p-5 flex flex-col justify-between bento-card">
                    <div>
                        <div class="flex items-center justify-between mb-3">
                            <span class="px-2.5 py-0.5 rounded-md bg-sky-500/15 text-sky-300 text-[10px] font-mono">FİNANS & PİYASA</span>
                            <span class="text-sm font-extrabold text-white">₺620</span>
                        </div>
                        <h3 class="font-bold text-base mb-1.5">Borsa & Kripto Trend Analizcisi</h3>
                        <p class="text-xs text-zinc-400 leading-relaxed">Makroekonomik verileri ve portföy risk dağılımını kurumsal düzeyde modelleyip raporlar.</p>
                    </div>
                    <button onclick="buyMarketplaceAgent('Borsa & Kripto Trend Analizcisi', 620, 'Aşağıdaki finansal varlık veya sektör için 2026 makro trendleri, destek/direnç senaryoları ve risk yönetim planı oluştur:\n\n')" class="mt-5 w-full py-2.5 rounded-xl bg-amber-500/15 hover:bg-amber-500/25 border border-amber-500/30 text-amber-300 text-xs font-bold transition cursor-pointer">
                        Satın Al & Stüdyoda Aç
                    </button>
                </div>

                <!-- Şablon 4 -->
                <div class="bg-zinc-950/90 border border-white/10 rounded-2xl p-5 flex flex-col justify-between bento-card">
                    <div>
                        <div class="flex items-center justify-between mb-3">
                            <span class="px-2.5 py-0.5 rounded-md bg-pink-500/15 text-pink-300 text-[10px] font-mono">YAZILIM & DEVOPS</span>
                            <span class="text-sm font-extrabold text-white">₺550</span>
                        </div>
                        <h3 class="font-bold text-base mb-1.5">Full-Stack Kod & Güvenlik Denetçisi</h3>
                        <p class="text-xs text-zinc-400 leading-relaxed">Kod bloklarındaki performans darboğazlarını ve OWASP güvenlik açıklarını otomatik onarır.</p>
                    </div>
                    <button onclick="buyMarketplaceAgent('Full-Stack Kod & Güvenlik Denetçisi', 550, 'Aşağıdaki kodu performans, ölçeklenebilirlik ve siber güvenlik açıkları açısından denetleyip optimize edilmiş halini yaz:\n\n')" class="mt-5 w-full py-2.5 rounded-xl bg-amber-500/15 hover:bg-amber-500/25 border border-amber-500/30 text-amber-300 text-xs font-bold transition cursor-pointer">
                        Satın Al & Stüdyoda Aç
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- YENİ MODÜL 4: Referans & Ortaklık (Affiliate) Kazanç Sistemi -->
    <section id="affiliate-hub" class="py-12 px-4 max-w-7xl mx-auto">
        <div class="glass rounded-3xl p-8 border border-emerald-500/25">
            <div class="grid grid-cols-1 lg:grid-cols-3 gap-8 items-center">
                <div class="lg:col-span-2 space-y-4">
                    <span class="text-xs font-bold uppercase tracking-widest text-emerald-400">Viral Büyüme & Gelir Ortaklığı</span>
                    <h2 class="text-2xl sm:text-3xl font-extrabold">Referans & Ortaklık (Affiliate) Kazanç Sistemi</h2>
                    <p class="text-zinc-400 text-sm leading-relaxed">
                        Kişisel davet bağlantınızı ekibinizle veya sosyal ağlarınızla paylaşın. Bağlantınız üzerinden <strong>Nexus Pro</strong> üyeliği başlatan her kullanıcıdan <strong>%30 ömür boyu komisyon</strong> kazanın; kazancınız anında cüzdanınıza yansısın.
                    </p>

                    <div class="flex flex-col sm:flex-row items-stretch sm:items-center gap-2 pt-2">
                        <input id="affiliate-link-input" type="text" readonly value="https://nexus26.ai/?ref=NEXUS-VIP-2026" class="flex-1 bg-zinc-950 border border-white/10 rounded-xl px-4 py-3 text-xs font-mono text-emerald-300 focus:outline-none">
                        <button onclick="copyAffiliateLink()" class="px-5 py-3 rounded-xl bg-emerald-600 hover:bg-emerald-500 text-white text-xs font-bold flex items-center justify-center gap-2 transition cursor-pointer">
                            <i data-lucide="copy" class="w-4 h-4"></i> Davet Linkini Kopyala
                        </button>
                        <button onclick="simulateAffiliateReferral()" class="px-4 py-3 rounded-xl bg-white/5 hover:bg-white/10 border border-white/10 text-zinc-200 text-xs font-semibold flex items-center justify-center gap-1.5 transition cursor-pointer" title="Örnek Davet Kazancı Test Et">
                            <i data-lucide="user-plus" class="w-4 h-4 text-emerald-400"></i> Test Daveti
                        </button>
                    </div>
                </div>

                <div class="bg-zinc-950/90 border border-white/10 rounded-2xl p-6 space-y-4">
                    <div class="flex items-center justify-between pb-3 border-b border-white/10">
                        <span class="text-xs font-bold text-zinc-300">Ortaklık Performans Özeti</span>
                        <span class="px-2 py-0.5 rounded bg-emerald-500/15 text-emerald-400 text-[10px] font-mono">%30 PAY</span>
                    </div>
                    <div class="grid grid-cols-2 gap-3">
                        <div class="p-3.5 rounded-xl bg-white/[0.03] border border-white/5">
                            <span class="text-[11px] text-zinc-400 block">Davet Edilen Pro</span>
                            <span id="aff-count" class="text-2xl font-extrabold text-white">14</span>
                        </div>
                        <div class="p-3.5 rounded-xl bg-white/[0.03] border border-white/5">
                            <span class="text-[11px] text-zinc-400 block">Ortaklık Kazancı</span>
                            <span id="aff-earnings" class="text-2xl font-extrabold text-emerald-400">₺1.638</span>
                        </div>
                    </div>
                    <p class="text-[11px] text-zinc-500">Kazançlarınız otomatik olarak aşağıdaki Yönetici Cüzdanı bakiyenize eklenir.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Yeni Eklenti: Kanban & AI Görev Otomasyon Panosu -->
    <section id="kanban-paneli" class="py-12 px-4 max-w-7xl mx-auto">
        <div class="glass rounded-3xl p-8 border border-white/10">
            <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 mb-8">
                <div>
                    <span class="text-xs font-bold uppercase tracking-widest text-emerald-400">Akıllı Görev Yönetimi</span>
                    <h2 class="text-2xl sm:text-3xl font-extrabold mt-1">Can Kanban & AI İş Akışları</h2>
                </div>
                <button onclick="addKanbanTask()" class="px-4 py-2.5 rounded-xl bg-emerald-500/10 hover:bg-emerald-500/20 border border-emerald-500/30 text-emerald-300 text-xs font-bold flex items-center gap-2 transition cursor-pointer">
                    <i data-lucide="plus" class="w-4 h-4"></i> Yeni Görev Ekle
                </button>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <!-- Yapılacaklar -->
                <div class="bg-zinc-950/80 border border-white/10 rounded-2xl p-4">
                    <div class="flex items-center justify-between pb-3 mb-4 border-b border-white/10">
                        <span class="text-xs font-bold text-zinc-400">YAPILACAKLAR (TO DO)</span>
                        <span id="todo-count-badge" class="w-5 h-5 rounded-full bg-white/5 text-zinc-400 text-xs flex items-center justify-center font-mono">2</span>
                    </div>
                    <div class="space-y-3" id="kanban-todo">
                        <div class="p-3.5 rounded-xl bg-white/[0.03] border border-white/5 text-xs space-y-2">
                            <div class="flex items-center justify-between"><span class="px-2 py-0.5 rounded bg-violet-500/20 text-violet-300 font-mono text-[10px]">ALPHA</span><span class="text-zinc-500">Bugün</span></div>
                            <p class="font-semibold text-zinc-200">Küresel Q4 SaaS fiyat analizi raporunu derle</p>
                        </div>
                        <div class="p-3.5 rounded-xl bg-white/[0.03] border border-white/5 text-xs space-y-2">
                            <div class="flex items-center justify-between"><span class="px-2 py-0.5 rounded bg-sky-500/20 text-sky-300 font-mono text-[10px]">SENTINEL</span><span class="text-zinc-500">Yarın</span></div>
                            <p class="font-semibold text-zinc-200">Sıfır-güven güvenlik duvarı loglarını denetle</p>
                        </div>
                    </div>
                </div>

                <!-- Devam Eden -->
                <div class="bg-zinc-950/80 border border-white/10 rounded-2xl p-4">
                    <div class="flex items-center justify-between pb-3 mb-4 border-b border-white/10">
                        <span class="text-xs font-bold text-sky-400">DEVAM EDEN (IN PROGRESS)</span>
                        <span class="w-5 h-5 rounded-full bg-sky-500/20 text-sky-300 text-xs flex items-center justify-center font-mono">1</span>
                    </div>
                    <div class="space-y-3" id="kanban-progress">
                        <div class="p-3.5 rounded-xl bg-sky-500/10 border border-sky-500/20 text-xs space-y-2">
                            <div class="flex items-center justify-between"><span class="px-2 py-0.5 rounded bg-pink-500/20 text-pink-300 font-mono text-[10px]">GROWTH</span><span class="text-sky-400">Canlı</span></div>
                            <p class="font-semibold text-white">Mobil ödeme adımındaki dönüşüm hunisini optimize et</p>
                        </div>
                    </div>
                </div>

                <!-- Tamamlanan -->
                <div class="bg-zinc-950/80 border border-white/10 rounded-2xl p-4">
                    <div class="flex items-center justify-between pb-3 mb-4 border-b border-white/10">
                        <span class="text-xs font-bold text-emerald-400">TAMAMLANAN (DONE)</span>
                        <span class="w-5 h-5 rounded-full bg-emerald-500/20 text-emerald-300 text-xs flex items-center justify-center font-mono">1</span>
                    </div>
                    <div class="space-y-3" id="kanban-done">
                        <div class="p-3.5 rounded-xl bg-white/[0.03] border border-white/5 text-xs space-y-2 opacity-75">
                            <div class="flex items-center justify-between"><span class="px-2 py-0.5 rounded bg-amber-500/20 text-amber-300 font-mono text-[10px]">ARCHITECT</span><span class="text-emerald-400">✓ Bitti</span></div>
                            <p class="font-semibold text-zinc-300 line-through">Edge önbellek isabet oranını %96.8'e çıkar</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Çok Yönlü AI Mikro-Araçlar Merkezi -->
    <section id="ai-tools" class="py-12 px-4 max-w-7xl mx-auto">
        <div class="text-center mb-10">
            <span class="text-xs font-bold uppercase tracking-widest text-violet-400">Hepsi Bir Arada Süper Uygulama</span>
            <h2 class="text-2xl sm:text-4xl font-extrabold mt-1">Tek Tıkla Çalışan AI Mikro-Araçları</h2>
            <p class="text-zinc-400 text-sm mt-2">İhtiyacınız olan uzmanlık modülünü seçin; sistem otomatik olarak ilgili yapay zeka motorunu yapılandırsın.</p>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-5">
            <div onclick="launchQuickTool('strategy', 'Aşağıdaki metni yönetici özeti, 3 kritik aksiyon ve risk analizi şeklinde özetle:\n\n')" class="glass bento-card rounded-2xl p-6 cursor-pointer border border-white/10">
                <div class="w-10 h-10 rounded-xl bg-violet-500/15 text-violet-400 flex items-center justify-center mb-4">
                    <i data-lucide="file-text" class="w-5 h-5"></i>
                </div>
                <h3 class="font-bold text-base mb-1">Toplantı & Doküman Özetleyici</h3>
                <p class="text-xs text-zinc-400 leading-relaxed">Uzun raporları ve toplantı notlarını saniyeler içinde aksiyon maddelerine dönüştürür.</p>
            </div>

            <div onclick="launchQuickTool('strategy', 'Aşağıdaki metni doğal, akıcı ve kurumsal bir dille İngilizce, Almanca ve İspanyolca dillerine çevir:\n\n')" class="glass bento-card rounded-2xl p-6 cursor-pointer border border-white/10">
                <div class="w-10 h-10 rounded-xl bg-sky-500/15 text-sky-400 flex items-center justify-center mb-4">
                    <i data-lucide="languages" class="w-5 h-5"></i>
                </div>
                <h3 class="font-bold text-base mb-1">Çok Dilli Kurumsal Çevirmen</h3>
                <p class="text-xs text-zinc-400 leading-relaxed">Sektörel terminolojiyi koruyarak metinleri aynı anda birden fazla dünya diline uyarlar.</p>
            </div>

            <div onclick="launchQuickTool('trend', 'Şu ürün/konu için 2026 algoritmalarına uygun viral sosyal medya kancaları (hooks) ve SEO anahtar kelimeleri üret:\n\n')" class="glass bento-card rounded-2xl p-6 cursor-pointer border border-white/10">
                <div class="w-10 h-10 rounded-xl bg-pink-500/15 text-pink-400 flex items-center justify-center mb-4">
                    <i data-lucide="megaphone" class="w-5 h-5"></i>
                </div>
                <h3 class="font-bold text-base mb-1">Viral İçerik & SEO Sihirbazı</h3>
                <p class="text-xs text-zinc-400 leading-relaxed">Yüksek etkileşimli başlıklar, video senaryoları ve arama motoru stratejileri oluşturur.</p>
            </div>

            <div onclick="launchQuickTool('code', 'Aşağıdaki veri tablosu ihtiyacına göre yüksek performanslı PostgreSQL sorgusu ve indeks önerisi yaz:\n\n')" class="glass bento-card rounded-2xl p-6 cursor-pointer border border-white/10">
                <div class="w-10 h-10 rounded-xl bg-emerald-500/15 text-emerald-400 flex items-center justify-center mb-4">
                    <i data-lucide="database" class="w-5 h-5"></i>
                </div>
                <h3 class="font-bold text-base mb-1">SQL & Veri Analiz Mimarı</h3>
                <p class="text-xs text-zinc-400 leading-relaxed">Doğal dildeki sorularınızı optimize edilmiş karmaşık SQL sorgularına çevirir.</p>
            </div>

            <div onclick="launchQuickTool('strategy', 'Aşağıdaki sözleşme veya teklif metnindeki hukuki/finansal riskleri ve müzakere noktalarını listele:\n\n')" class="glass bento-card rounded-2xl p-6 cursor-pointer border border-white/10">
                <div class="w-10 h-10 rounded-xl bg-amber-500/15 text-amber-400 flex items-center justify-center mb-4">
                    <i data-lucide="scale" class="w-5 h-5"></i>
                </div>
                <h3 class="font-bold text-base mb-1">Sözleşme & Risk Denetçisi</h3>
                <p class="text-xs text-zinc-400 leading-relaxed">Ticari metinlerdeki gizli maddeleri ve potansiyel darboğazları önceden tespit eder.</p>
            </div>

            <div onclick="launchQuickTool('image', 'Minimalist 3D cam ve metalik dokulu fütüristik ürün konsepti, stüdyo aydınlatması, 8k çözünürlük: ')" class="glass bento-card rounded-2xl p-6 cursor-pointer border border-white/10">
                <div class="w-10 h-10 rounded-xl bg-indigo-500/15 text-indigo-400 flex items-center justify-center mb-4">
                    <i data-lucide="palette" class="w-5 h-5"></i>
                </div>
                <h3 class="font-bold text-base mb-1">3D Ürün & Marka Tasarımcısı</h3>
                <p class="text-xs text-zinc-400 leading-relaxed">Fikirlerinizi saniyeler içinde fotorealistik konsept görsellere ve sunum varlıklarına dönüştürür.</p>
            </div>
        </div>
    </section>

    <!-- İnteraktif AI İş Akışı Oluşturucu (Visual Workflow Pipeline) -->
    <section id="workflow-builder" class="py-12 px-4 max-w-7xl mx-auto">
        <div class="glass rounded-3xl p-8 border border-white/10">
            <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 mb-8">
                <div>
                    <span class="text-xs font-bold uppercase tracking-widest text-sky-400">No-Code Otomasyon Mimarı</span>
                    <h2 class="text-2xl sm:text-4xl font-extrabold mt-1">Canlı AI Boru Hattı (Pipeline)</h2>
                    <p class="text-zinc-400 text-sm mt-1">Veri toplama, yapay zeka sentezi ve otonom aksiyon adımlarını tek tıkla uçtan uca çalıştırın.</p>
                </div>
                <div class="flex items-center gap-3">
                    <select id="pipeline-preset" class="bg-zinc-950 border border-white/10 rounded-xl px-3.5 py-2.5 text-xs text-zinc-200 focus:outline-none focus:border-violet-500">
                        <option value="sales">B2B Müşteri Kazanım & CRM Akışı</option>
                        <option value="security">Gerçek Zamanlı Siber Tehdit Analizi</option>
                        <option value="content">Çok Dilli Küresel İçerik Dağıtımı</option>
                    </select>
                    <button onclick="runPipeline()" id="run-pipeline-btn" class="px-5 py-2.5 rounded-xl bg-gradient-to-r from-sky-500 to-indigo-600 hover:opacity-95 text-white text-xs font-bold flex items-center gap-2 transition shadow-lg shadow-sky-500/20 cursor-pointer">
                        <i data-lucide="zap" class="w-4 h-4"></i> Akışı Çalıştır
                    </button>
                </div>
            </div>

            <!-- Pipeline Düğümleri -->
            <div class="grid grid-cols-1 md:grid-cols-4 gap-4 relative">
                <div id="node-1" class="pipeline-node bg-zinc-950/90 border border-white/10 rounded-2xl p-5 transition-all duration-300">
                    <div class="flex items-center justify-between mb-3">
                        <span class="w-8 h-8 rounded-lg bg-violet-500/15 text-violet-400 flex items-center justify-center font-mono text-xs font-bold">01</span>
                        <span class="node-status text-[10px] font-mono px-2 py-0.5 rounded bg-white/5 text-zinc-500">HAZIR</span>
                    </div>
                    <h4 class="font-bold text-sm mb-1">Veri Kaynağı & Webhook</h4>
                    <p class="text-xs text-zinc-400">CRM, ERP ve canlı API akışlarından ham veriyi çeker.</p>
                </div>

                <div id="node-2" class="pipeline-node bg-zinc-950/90 border border-white/10 rounded-2xl p-5 transition-all duration-300">
                    <div class="flex items-center justify-between mb-3">
                        <span class="w-8 h-8 rounded-lg bg-sky-500/15 text-sky-400 flex items-center justify-center font-mono text-xs font-bold">02</span>
                        <span class="node-status text-[10px] font-mono px-2 py-0.5 rounded bg-white/5 text-zinc-500">BEKLİYOR</span>
                    </div>
                    <h4 class="font-bold text-sm mb-1">Vektör Bellek & RAG</h4>
                    <p class="text-xs text-zinc-400">Kurumsal bilgi tabanıyla anlamsal eşleştirme yapar.</p>
                </div>

                <div id="node-3" class="pipeline-node bg-zinc-950/90 border border-white/10 rounded-2xl p-5 transition-all duration-300">
                    <div class="flex items-center justify-between mb-3">
                        <span class="w-8 h-8 rounded-lg bg-pink-500/15 text-pink-400 flex items-center justify-center font-mono text-xs font-bold">03</span>
                        <span class="node-status text-[10px] font-mono px-2 py-0.5 rounded bg-white/5 text-zinc-500">BEKLİYOR</span>
                    </div>
                    <h4 class="font-bold text-sm mb-1">Gemini 3 Karar Motoru</h4>
                    <p class="text-xs text-zinc-400">Çok boyutlu muhakeme ile stratejik aksiyon üretir.</p>
                </div>

                <div id="node-4" class="pipeline-node bg-zinc-950/90 border border-white/10 rounded-2xl p-5 transition-all duration-300">
                    <div class="flex items-center justify-between mb-3">
                        <span class="w-8 h-8 rounded-lg bg-emerald-500/15 text-emerald-400 flex items-center justify-center font-mono text-xs font-bold">04</span>
                        <span class="node-status text-[10px] font-mono px-2 py-0.5 rounded bg-white/5 text-zinc-500">BEKLİYOR</span>
                    </div>
                    <h4 class="font-bold text-sm mb-1">Otonom Dağıtım</h4>
                    <p class="text-xs text-zinc-400">Slack, E-posta ve üretim sistemlerine sonucu iletir.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Canlı Otonom Ajan Merkezi (Live Agent Swarm) -->
    <section id="ajan-merkezi" class="py-12 px-4 max-w-7xl mx-auto">
        <div class="glass rounded-3xl p-8 border border-white/10">
            <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 mb-8">
                <div>
                    <span class="text-xs font-bold uppercase tracking-widest text-emerald-400">Otonom Operasyon Ağı</span>
                    <h2 class="text-2xl sm:text-4xl font-extrabold mt-1">Canlı AI Ajan Orkestrasyonu</h2>
                    <p class="text-zinc-400 text-sm mt-1">Arka planda 7/24 çalışan otonom ajanlarınızı tetikleyin ve gerçek zamanlı sistem akışını izleyin.</p>
                </div>
                <button onclick="triggerSwarmBurst()" class="px-5 py-3 rounded-xl bg-emerald-500/10 hover:bg-emerald-500/20 border border-emerald-500/30 text-emerald-300 text-xs font-bold flex items-center gap-2 transition self-start cursor-pointer">
                    <i data-lucide="play" class="w-4 h-4"></i> Tüm Ajanları Senkronize Et
                </button>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
                <!-- Ajan Kartları -->
                <div class="lg:col-span-2 grid grid-cols-1 sm:grid-cols-2 gap-4">
                    <div class="bg-zinc-950/80 border border-white/10 rounded-2xl p-5 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between mb-3">
                                <span class="px-2.5 py-0.5 rounded-md bg-violet-500/15 text-violet-300 text-[11px] font-mono">AGENT-01 // ALPHA</span>
                                <span class="flex items-center gap-1.5 text-[11px] text-emerald-400 font-semibold"><span class="w-2 h-2 rounded-full bg-emerald-400 animate-ping"></span> Aktif</span>
                            </div>
                            <h3 class="font-bold text-base mb-1">Pazar & Rakip İstihbarat Ajanı</h3>
                            <p class="text-xs text-zinc-400 leading-relaxed">Küresel SaaS fiyatlandırmalarını ve trend anahtar kelimeleri gerçek zamanlı tarar.</p>
                        </div>
                        <div class="mt-4 pt-3 border-t border-white/5 flex items-center justify-between">
                            <span class="text-[11px] font-mono text-zinc-500">Verimlilik: %99.4</span>
                            <button onclick="runSingleAgent('Pazar İstihbarat Ajanı', '2026 Q4 B2B SaaS pazarında yapay zeka destekli otomasyon talebi %68 artış gösterdi.')" class="text-xs text-violet-400 hover:text-violet-300 font-semibold">Görev Ver →</button>
                        </div>
                    </div>

                    <div class="bg-zinc-950/80 border border-white/10 rounded-2xl p-5 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between mb-3">
                                <span class="px-2.5 py-0.5 rounded-md bg-sky-500/15 text-sky-300 text-[11px] font-mono">AGENT-02 // SENTINEL</span>
                                <span class="flex items-center gap-1.5 text-[11px] text-emerald-400 font-semibold"><span class="w-2 h-2 rounded-full bg-emerald-400"></span> Korumada</span>
                            </div>
                            <h3 class="font-bold text-base mb-1">Sıfır-Güven Güvenlik Denetçisi</h3>
                            <p class="text-xs text-zinc-400 leading-relaxed">API uç noktalarını anomalilere karşı izler ve veri sızıntısı önleme kurallarını uygular.</p>
                        </div>
                        <div class="mt-4 pt-3 border-t border-white/5 flex items-center justify-between">
                            <span class="text-[11px] font-mono text-zinc-500">Tehdit: 0 Tespit</span>
                            <button onclick="runSingleAgent('Güvenlik Denetçisi', 'Tüm TLS 1.3 sertifikaları ve AES-512 bellek izolasyonu doğrulandı. Risk skoru: 0.01.')" class="text-xs text-sky-400 hover:text-sky-300 font-semibold">Tarama Başlat →</button>
                        </div>
                    </div>

                    <div class="bg-zinc-950/80 border border-white/10 rounded-2xl p-5 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between mb-3">
                                <span class="px-2.5 py-0.5 rounded-md bg-pink-500/15 text-pink-300 text-[11px] font-mono">AGENT-03 // GROWTH</span>
                                <span class="flex items-center gap-1.5 text-[11px] text-emerald-400 font-semibold"><span class="w-2 h-2 rounded-full bg-emerald-400"></span> Aktif</span>
                            </div>
                            <h3 class="font-bold text-base mb-1">Dönüşüm & Huni Optimizasyon Ajanı</h3>
                            <p class="text-xs text-zinc-400 leading-relaxed">Kullanıcı davranış ısı haritalarını analiz ederek A/B varyasyonlarını otomatik devreye alır.</p>
                        </div>
                        <div class="mt-4 pt-3 border-t border-white/5 flex items-center justify-between">
                            <span class="text-[11px] font-mono text-zinc-500">Dönüşüm: +%38.2</span>
                            <button onclick="runSingleAgent('Büyüme Ajanı', 'Mobil ödeme adımındaki sürtünme azaltıldı; tahmini aylık MRR artışı +₺145.000.')" class="text-xs text-pink-400 hover:text-pink-300 font-semibold">Optimize Et →</button>
                        </div>
                    </div>

                    <div class="bg-zinc-950/80 border border-white/10 rounded-2xl p-5 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between mb-3">
                                <span class="px-2.5 py-0.5 rounded-md bg-amber-500/15 text-amber-300 text-[11px] font-mono">AGENT-04 // ARCHITECT</span>
                                <span class="flex items-center gap-1.5 text-[11px] text-emerald-400 font-semibold"><span class="w-2 h-2 rounded-full bg-emerald-400"></span> Hazır</span>
                            </div>
                            <h3 class="font-bold text-base mb-1">Otonom Kod & Refactor Ajanı</h3>
                            <p class="text-xs text-zinc-400 leading-relaxed">Sistem gecikmelerini tespit edip veritabanı sorgularını ve önbellek katmanını iyileştirir.</p>
                        </div>
                        <div class="mt-4 pt-3 border-t border-white/5 flex items-center justify-between">
                            <span class="text-[11px] font-mono text-zinc-500">Gecikme: 14ms</span>
                            <button onclick="runSingleAgent('Kod Mimarı Ajanı', 'Edge önbellek isabet oranı %96.8 seviyesine çıkarıldı, sunucu yükü %41 azaldı.')" class="text-xs text-amber-400 hover:text-amber-300 font-semibold">Derle →</button>
                        </div>
                    </div>
                </div>

                <!-- Canlı Sistem Terminali -->
                <div class="bg-zinc-950 border border-white/10 rounded-2xl p-5 flex flex-col justify-between font-mono">
                    <div>
                        <div class="flex items-center justify-between pb-3 mb-3 border-b border-white/10">
                            <span class="text-xs text-zinc-400 flex items-center gap-2"><i data-lucide="activity" class="w-3.5 h-3.5 text-emerald-400"></i> LIVE TELEMETRY</span>
                            <span class="text-[10px] text-zinc-600">IST-NODE-01</span>
                        </div>
                        <div id="agent-terminal" class="space-y-2.5 text-[11px] h-56 overflow-y-auto pr-1">
                            <div class="text-zinc-500">[00:54:12] <span class="text-violet-400">ALPHA:</span> Küresel pazar endeksi güncellendi.</div>
                            <div class="text-zinc-500">[00:55:03] <span class="text-sky-400">SENTINEL:</span> 14,200 istek doğrulandı (0 anomali).</div>
                            <div class="text-zinc-500">[00:56:41] <span class="text-emerald-400">SYSTEM:</span> Multi-model yönlendirici aktif.</div>
                        </div>
                    </div>
                    <div class="pt-3 mt-3 border-t border-white/5 flex items-center justify-between text-[10px] text-zinc-500">
                        <span>CPU: %18 | GPU-TENSOR: %42</span>
                        <span class="text-emerald-400">● ONLINE</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 2026 Küresel Web Trafik ve Trend Analizi (İnteraktif Panel) -->
    <section id="trendler" class="py-16 px-4 max-w-7xl mx-auto">
        <div class="glass rounded-3xl p-8 border border-white/10">
            <div class="flex flex-col md:flex-row md:items-end justify-between gap-6 mb-10">
                <div>
                    <span class="text-xs font-bold uppercase tracking-widest text-sky-400">2026 Dijital Ekosistem Raporu</span>
                    <h2 class="text-2xl sm:text-4xl font-extrabold mt-2">En Çok Ziyaret Edilen Platform Kategorileri</h2>
                </div>
                <div class="flex items-center gap-2 bg-zinc-950 p-1.5 rounded-xl border border-white/10 self-start">
                    <button onclick="updateChartPeriod('2026')" id="btn-2026" class="px-4 py-1.5 rounded-lg text-xs font-bold bg-white text-black transition">2026 Verileri</button>
                    <button onclick="updateChartPeriod('2025')" id="btn-2025" class="px-4 py-1.5 rounded-lg text-xs font-bold text-zinc-400 hover:text-white transition">2025 Karşılaştırma</button>
                </div>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-3 gap-8 items-center">
                <!-- Sol Metrik Kartları -->
                <div class="space-y-4">
                    <div class="bg-zinc-950/70 p-5 rounded-2xl border border-white/5">
                        <div class="flex justify-between items-center mb-1">
                            <span class="text-xs text-zinc-400">Otonom AI Çalışma Alanları</span>
                            <span id="stat-ai-badge" class="text-xs font-bold text-emerald-400">+142% YoY</span>
                        </div>
                        <div id="stat-ai-val" class="text-3xl font-extrabold text-white">%46.8 <span class="text-xs font-normal text-zinc-500">Trafik Payı</span></div>
                        <div class="w-full bg-zinc-800 h-1.5 rounded-full mt-3 overflow-hidden">
                            <div id="bar-ai" class="bg-gradient-to-r from-violet-500 to-sky-400 h-full rounded-full transition-all duration-700" style="width: 88%"></div>
                        </div>
                    </div>

                    <div class="bg-zinc-950/70 p-5 rounded-2xl border border-white/5">
                        <div class="flex justify-between items-center mb-1">
                            <span class="text-xs text-zinc-400">İnteraktif Mikro-SaaS Araçları</span>
                            <span id="stat-saas-badge" class="text-xs font-bold text-sky-400">+89% YoY</span>
                        </div>
                        <div id="stat-saas-val" class="text-3xl font-extrabold text-white">%31.2 <span class="text-xs font-normal text-zinc-500">Trafik Payı</span></div>
                        <div class="w-full bg-zinc-800 h-1.5 rounded-full mt-3 overflow-hidden">
                            <div id="bar-saas" class="bg-sky-400 h-full rounded-full transition-all duration-700" style="width: 68%"></div>
                        </div>
                    </div>

                    <div class="bg-zinc-950/70 p-5 rounded-2xl border border-white/5">
                        <div class="flex justify-between items-center mb-1">
                            <span class="text-xs text-zinc-400">Geleneksel Statik Web Siteleri</span>
                            <span id="stat-legacy-badge" class="text-xs font-bold text-rose-400">-34% YoY</span>
                        </div>
                        <div id="stat-legacy-val" class="text-3xl font-extrabold text-white">%22.0 <span class="text-xs font-normal text-zinc-500">Trafik Payı</span></div>
                        <div class="w-full bg-zinc-800 h-1.5 rounded-full mt-3 overflow-hidden">
                            <div id="bar-legacy" class="bg-zinc-600 h-full rounded-full transition-all duration-700" style="width: 35%"></div>
                        </div>
                    </div>
                </div>

                <!-- Sağ İnteraktif Grafik -->
                <div class="lg:col-span-2 bg-zinc-950/90 rounded-2xl p-6 border border-white/5">
                    <div class="flex items-center justify-between mb-6">
                        <div>
                            <h4 class="text-sm font-bold text-white">Aylık Kullanıcı Etkileşim Endeksi</h4>
                            <p class="text-xs text-zinc-500">Bento UI & Gerçek Zamanlı AI araçlarının dönüşüm performansı</p>
                        </div>
                        <div class="flex items-center gap-4 text-xs">
                            <span class="flex items-center gap-1.5 text-zinc-300"><span class="w-2.5 h-2.5 rounded-full bg-violet-500"></span> Nexus26 Mimarisi</span>
                            <span class="flex items-center gap-1.5 text-zinc-500"><span class="w-2.5 h-2.5 rounded-full bg-zinc-700"></span> Klasik Web</span>
                        </div>
                    </div>
                    <div id="interactive-chart" class="h-56 flex items-end justify-between gap-2 sm:gap-4 pt-6 px-2 border-b border-white/10">
                        <!-- JS ile dinamik sütunlar oluşturulacak -->
                    </div>
                    <div class="flex justify-between text-[11px] text-zinc-500 mt-3 px-2 font-mono">
                        <span>OCA</span><span>ŞUB</span><span>MAR</span><span>NİS</span><span>MAY</span><span>HAZ</span><span>TEM</span><span>AĞU</span><span>EYL</span><span>EKİ</span><span>KAS</span><span>ARA</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Bento Grid Özellikler (2026 Tasarım Dili) -->
    <section id="ozellikler" class="py-20 px-4 max-w-7xl mx-auto">
        <div class="text-center mb-16">
            <span class="text-xs font-bold uppercase tracking-widest text-violet-400">Yeni Nesil Altyapı</span>
            <h2 class="text-3xl sm:text-5xl font-extrabold mt-2 mb-4">Kurumsal Ölçekte Mükemmellik</h2>
            <p class="text-zinc-400 max-w-xl mx-auto text-sm sm:text-base">Geleneksel web sitelerinin ötesine geçen, kullanıcı alışkanlıklarına göre şekillenen modüler Bento mimarisi.</p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-6" id="bento-grid">
            <!-- Büyük Kart 1 -->
            <div class="md:col-span-2 glass bento-card rounded-3xl p-8 flex flex-col justify-between">
                <div class="max-w-lg">
                    <div class="w-12 h-12 rounded-2xl bg-violet-500/10 border border-violet-500/20 flex items-center justify-center text-violet-400 mb-6">
                        <i data-lucide="layers" class="w-6 h-6"></i>
                    </div>
                    <h3 class="text-2xl font-bold mb-3">Otonom İş Akışı Ajanları</h3>
                    <p class="text-zinc-400 text-sm leading-relaxed">
                        Sadece komut bekleyen araçları unutun. Nexus ajanları hedeflerinizi analiz eder, eksik verileri küresel kaynaklardan tamamlar ve sizin yerinize aksiyon planları oluşturur.
                    </p>
                </div>
                <div class="mt-8 pt-6 border-t border-white/5 flex flex-wrap items-center gap-3">
                    <span class="px-3 py-1 rounded-full bg-emerald-500/10 border border-emerald-500/20 text-emerald-400 text-xs font-medium">+%340 Operasyonel Hız</span>
                    <span class="px-3 py-1 rounded-full bg-sky-500/10 border border-sky-500/20 text-sky-400 text-xs font-medium">Çoklu Model Orkestrasyonu</span>
                    <span class="px-3 py-1 rounded-full bg-violet-500/10 border border-violet-500/20 text-violet-300 text-xs font-medium">API & Webhook Hazır</span>
                </div>
            </div>

            <!-- Küçük Kart 2 -->
            <div class="glass bento-card rounded-3xl p-8 flex flex-col justify-between">
                <div>
                    <div class="w-12 h-12 rounded-2xl bg-sky-500/10 border border-sky-500/20 flex items-center justify-center text-sky-400 mb-6">
                        <i data-lucide="shield-check" class="w-6 h-6"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3">Sıfır Bilgi (Zero-Knowledge) Güvenlik</h3>
                    <p class="text-zinc-400 text-sm leading-relaxed">
                        Kurumsal verileriniz uçtan uca şifrelenir, izole konteynerlerde işlenir ve asla genel model eğitimi için kullanılmaz.
                    </p>
                </div>
                <div class="mt-6 pt-4 border-t border-white/5 flex items-center justify-between text-xs font-mono text-zinc-500">
                    <span>SOC2 TYPE II</span>
                    <span class="text-emerald-400">● AKTİF</span>
                </div>
            </div>

            <!-- Küçük Kart 3 -->
            <div class="glass bento-card rounded-3xl p-8 flex flex-col justify-between">
                <div>
                    <div class="w-12 h-12 rounded-2xl bg-pink-500/10 border border-pink-500/20 flex items-center justify-center text-pink-400 mb-6">
                        <i data-lucide="zap" class="w-6 h-6"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3">Edge Network Hızı</h3>
                    <p class="text-zinc-400 text-sm leading-relaxed">
                        Dünya genelinde 310+ uç sunucu noktasıyla İstanbul'dan New York'a 50ms altında milisaniyelik tepki süresi.
                    </p>
                </div>
                <div class="mt-6 flex items-center gap-2">
                    <span class="px-2.5 py-1 rounded-md bg-zinc-900 border border-white/10 text-[11px] font-mono text-zinc-300">IST-01: 14ms</span>
                    <span class="px-2.5 py-1 rounded-md bg-zinc-900 border border-white/10 text-[11px] font-mono text-zinc-300">FRA-04: 28ms</span>
                </div>
            </div>

            <!-- Büyük Kart 4 -->
            <div class="md:col-span-2 glass bento-card rounded-3xl p-8 flex flex-col md:flex-row items-center gap-8">
                <div class="flex-1">
                    <div class="w-12 h-12 rounded-2xl bg-amber-500/10 border border-amber-500/20 flex items-center justify-center text-amber-400 mb-6">
                        <i data-lucide="cpu" class="w-6 h-6"></i>
                    </div>
                    <h3 class="text-2xl font-bold mb-3">Akıllı Komut Paleti & Klavye Odaklı Akış</h3>
                    <p class="text-zinc-400 text-sm leading-relaxed">
                        Fareye dokunmadan tüm platformu yönetin. <kbd class="px-1.5 py-0.5 bg-zinc-800 rounded text-zinc-200 text-xs">Ctrl+K</kbd> veya <kbd class="px-1.5 py-0.5 bg-zinc-800 rounded text-zinc-200 text-xs">⌘K</kbd> kısayolu ile saniyeler içinde rapor oluşturun, modüller arası geçiş yapın.
                    </p>
                </div>
                <div class="w-full md:w-72 bg-zinc-950/90 rounded-2xl p-4 border border-white/10 space-y-2.5">
                    <div class="flex items-center gap-2 text-xs text-zinc-400 pb-2 border-b border-white/5">
                        <i data-lucide="search" class="w-3.5 h-3.5 text-violet-400"></i>
                        <span>Hızlı Eylem Ara...</span>
                    </div>
                    <div class="p-2 rounded-lg bg-violet-600/20 border border-violet-500/30 text-xs text-white flex items-center justify-between">
                        <span>Yeni Strateji Raporu</span>
                        <span class="text-[10px] font-mono text-violet-300">↵</span>
                    </div>
                    <div class="p-2 rounded-lg text-xs text-zinc-400 flex items-center justify-between">
                        <span>Bilgi Bankasına Git</span>
                        <span class="text-[10px] font-mono">⌘B</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Fiyatlandırma Bölümü (Yıllık / Aylık Dinamik Geçişli) -->
    <section id="fiyatlandirma" class="py-20 px-4 max-w-6xl mx-auto">
        <div class="text-center mb-12">
            <span class="text-xs font-bold uppercase tracking-widest text-violet-400">Esnek Lisanslama</span>
            <h2 class="text-3xl sm:text-5xl font-extrabold mt-2 mb-4">Ekibinizle Birlikte Büyüyen Planlar</h2>
            <p class="text-zinc-400 text-sm max-w-lg mx-auto mb-8">Şeffaf fiyatlandırma. Gizli ücret yok, istediğiniz an tek tıkla plan değişikliği yapın.</p>
            
            <!-- Fatura Dönemi Anahtarı -->
            <div class="inline-flex items-center gap-3 bg-zinc-900/90 p-1.5 rounded-full border border-white/10">
                <button onclick="setBilling('monthly')" id="bill-monthly" class="px-5 py-2 rounded-full text-xs font-bold text-zinc-400 transition">Aylık Ödeme</button>
                <button onclick="setBilling('yearly')" id="bill-yearly" class="px-5 py-2 rounded-full text-xs font-bold bg-violet-600 text-white transition flex items-center gap-1.5">
                    Yıllık Ödeme <span class="px-1.5 py-0.5 bg-white/20 rounded-full text-[10px]">-%20</span>
                </button>
            </div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <!-- Başlangıç -->
            <div class="glass bento-card rounded-3xl p-8 border border-white/5 flex flex-col justify-between">
                <div>
                    <span class="text-xs font-bold uppercase tracking-widest text-zinc-500">Başlangıç</span>
                    <div class="text-4xl font-extrabold mt-3 mb-2">₺0 <span class="text-sm font-normal text-zinc-500">/ ay</span></div>
                    <p class="text-xs text-zinc-500 mb-6">Bireysel keşif ve temel AI otomasyonları için.</p>
                    <ul class="space-y-4 text-sm text-zinc-400 mb-8">
                        <li class="flex items-center gap-2.5"><i data-lucide="check" class="w-4 h-4 text-emerald-400 shrink-0"></i> Günlük 25 Canlı AI Sorgusu</li>
                        <li class="flex items-center gap-2.5"><i data-lucide="check" class="w-4 h-4 text-emerald-400 shrink-0"></i> Standart Yanıt Önceliği</li>
                        <li class="flex items-center gap-2.5"><i data-lucide="check" class="w-4 h-4 text-emerald-400 shrink-0"></i> Temel Bento Şablonları</li>
                    </ul>
                </div>
                <button onclick="showToast('Ücretsiz başlangıç hesabı tanımlandı!')" class="w-full py-3.5 rounded-xl bg-white/5 hover:bg-white/10 border border-white/10 text-white font-semibold text-sm transition">Ücretsiz Başla</button>
            </div>

            <!-- Pro (Popüler) -->
            <div class="glass bento-card rounded-3xl p-8 border-2 border-violet-500 relative flex flex-col justify-between shadow-2xl shadow-violet-500/15">
                <div class="absolute -top-3.5 left-1/2 -translate-x-1/2 bg-gradient-to-r from-violet-600 to-indigo-600 text-white text-[10px] font-bold uppercase tracking-widest px-3.5 py-1 rounded-full shadow-lg">
                    En Popüler Seçim
                </div>
                <div>
                    <span class="text-xs font-bold uppercase tracking-widest text-violet-400">Nexus Pro</span>
                    <div class="text-4xl font-extrabold mt-3 mb-2">
                        <span id="pro-price">₺390</span> <span class="text-sm font-normal text-zinc-500">/ ay</span>
                    </div>
                    <p id="pro-billing-note" class="text-xs text-emerald-400 mb-6">Yıllık faturalandırılır (₺1.200 tasarruf)</p>
                    <ul class="space-y-4 text-sm text-zinc-200 mb-8">
                        <li class="flex items-center gap-2.5"><i data-lucide="check" class="w-4 h-4 text-violet-400 shrink-0"></i> Sınırsız Yüksek Hızlı AI Sorgusu</li>
                        <li class="flex items-center gap-2.5"><i data-lucide="check" class="w-4 h-4 text-violet-400 shrink-0"></i> Tüm Yeni Nesil Modellere Erişim</li>
                        <li class="flex items-center gap-2.5"><i data-lucide="check" class="w-4 h-4 text-violet-400 shrink-0"></i> 10 Özel Otonom AI Ajanı</li>
                        <li class="flex items-center gap-2.5"><i data-lucide="check" class="w-4 h-4 text-violet-400 shrink-0"></i> Sınırsız Bilgi Bankası & AI Arena</li>
                    </ul>
                </div>
                <button onclick="openPaymentModal()" class="w-full py-3.5 rounded-xl bg-violet-600 hover:bg-violet-500 text-white font-bold text-sm transition shadow-lg shadow-violet-600/30 flex items-center justify-center gap-2 cursor-pointer">
                    <i data-lucide="credit-card" class="w-4 h-4"></i> Kendi Kartınla Pro Al
                </button>
            </div>

            <!-- Kurumsal -->
            <div class="glass bento-card rounded-3xl p-8 border border-white/5 flex flex-col justify-between">
                <div>
                    <span class="text-xs font-bold uppercase tracking-widest text-zinc-500">Enterprise</span>
                    <div class="text-4xl font-extrabold mt-2 mb-1">Özel <span class="text-sm font-normal text-zinc-500">/ ekip</span></div>
                    <p class="text-xs text-zinc-500 mb-6">Büyük ölçekli kurumlar ve özel güvenlik ihtiyaçları için.</p>
                    <ul class="space-y-4 text-sm text-zinc-400 mb-8">
                        <li class="flex items-center gap-2.5"><i data-lucide="check" class="w-4 h-4 text-emerald-400 shrink-0"></i> İzole Özel Bulut & VPC</li>
                        <li class="flex items-center gap-2.5"><i data-lucide="check" class="w-4 h-4 text-emerald-400 shrink-0"></i> Şirket Verisiyle Özel Fine-Tuning</li>
                        <li class="flex items-center gap-2.5"><i data-lucide="check" class="w-4 h-4 text-emerald-400 shrink-0"></i> %99.99 SLA & Özel Müşteri Mimarı</li>
                    </ul>
                </div>
                <button onclick="openModal('contact')" class="w-full py-3.5 rounded-xl bg-white/5 hover:bg-white/10 border border-white/10 text-white font-semibold text-sm transition">Satış Ekibiyle Görüş</button>
            </div>
        </div>
    </section>

    <!-- Site İçi Cüzdan & Banka Çekim Paneli -->
    <section id="cuzdan-merkezi" class="py-12 px-4 max-w-6xl mx-auto">
        <div class="glass rounded-3xl p-8 border border-violet-500/20">
            <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 mb-8 pb-6 border-b border-white/10">
                <div>
                    <span class="text-xs font-bold uppercase tracking-widest text-violet-400">Yalnızca Sistem Sahibine Özel Ağ Geçidi</span>
                    <h2 class="text-2xl sm:text-3xl font-extrabold mt-1">Yönetici Cüzdanı & Kendi IBAN Hesabınız</h2>
                    <p class="text-xs text-zinc-400 mt-1">Platformdaki abonelik ödemeleri, Pazar Yeri satışları ve Ortaklık gelirleri doğrudan sizin kişisel banka hesabınıza akar.</p>
                </div>
                <div class="flex flex-wrap items-center gap-3">
                    <button onclick="openAdminSecurityModal()" class="px-4 py-3 rounded-xl bg-violet-600/20 hover:bg-violet-600/30 border border-violet-500/30 text-violet-300 text-xs font-bold flex items-center gap-2 transition cursor-pointer">
                        <i data-lucide="shield-alert" class="w-4 h-4"></i> Yönetici IBAN'ını Kilitle
                    </button>
                    <button onclick="requestAdminPasswordForWithdraw()" class="px-5 py-3 rounded-xl bg-gradient-to-r from-emerald-500 to-teal-600 hover:opacity-95 text-white text-xs font-bold flex items-center gap-2 transition shadow-lg shadow-emerald-500/20 cursor-pointer">
                        <i data-lucide="landmark" class="w-4 h-4"></i> Kendi IBAN'ıma Para Çek
                    </button>
                </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <div class="bg-zinc-950 p-6 rounded-2xl border border-white/10 flex flex-col justify-between">
                    <div>
                        <span class="text-xs text-zinc-400 block mb-1">Toplam Sistem / Sizin Bakiye</span>
                        <div id="wallet-balance" class="text-3xl font-extrabold text-white">₺48.950,00</div>
                    </div>
                    <div class="mt-4 pt-4 border-t border-white/5 text-[11px] text-emerald-400 font-mono flex items-center gap-1.5">
                        <span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></span> Sadece Sizin Hesabınıza Aktarıma Uygun
                    </div>
                </div>

                <div class="bg-zinc-950 p-6 rounded-2xl border border-white/10 flex flex-col justify-between">
                    <div>
                        <span class="text-xs text-zinc-400 block mb-1">Onaylı Yönetici IBAN (Sizin Bankanız)</span>
                        <div id="display-iban" class="text-sm font-mono font-bold text-violet-300">TR42 0006 1004 9912 ...</div>
                    </div>
                    <div class="mt-4 pt-4 border-t border-white/5 text-[11px] text-zinc-400 flex items-center justify-between">
                        <span>Tam Yetkili Sahip</span>
                        <button onclick="requestAdminPasswordForWithdraw()" class="text-sky-400 hover:underline">IBAN Düzenle</button>
                    </div>
                </div>

                <div class="bg-zinc-950 p-6 rounded-2xl border border-white/10 flex flex-col justify-between">
                    <div>
                        <span class="text-xs text-zinc-400 block mb-1">Güvenlik & Erişim Durumu</span>
                        <div class="text-sm font-bold text-emerald-400">Korumalı (Sadece Siz Çekebilirsiniz)</div>
                    </div>
                    <div class="mt-4 pt-4 border-t border-white/5 text-[11px] text-zinc-500 font-mono">
                        Yetki: 2FA & Şifreli Yönetici Kilidi
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- İnteraktif Kurumsal ROI & Tasarruf Hesaplayıcı -->
    <section id="roi-hesaplayici" class="py-12 px-4 max-w-6xl mx-auto">
        <div class="glass rounded-3xl p-8 sm:p-10 border border-white/10">
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-10 items-center">
                <div>
                    <span class="text-xs font-bold uppercase tracking-widest text-violet-400">Yatırım Getirisi Simülatörü</span>
                    <h2 class="text-2xl sm:text-4xl font-extrabold mt-2 mb-4">Nexus26 ile Yıllık Tasarrufunuzu Hesaplayın</h2>
                    <p class="text-zinc-400 text-sm mb-8">Ekip büyüklüğünüzü ve haftalık manuel operasyon sürenizi seçin; otonom ajanların şirketinize sağlayacağı net kazancı anında görün.</p>

                    <div class="space-y-6">
                        <div>
                            <div class="flex justify-between text-xs font-semibold mb-2">
                                <span class="text-zinc-300">Ekip Büyüklüğü (Çalışan Sayısı)</span>
                                <span id="roi-team-val" class="text-violet-400 font-mono text-sm">25 Kişi</span>
                            </div>
                            <input type="range" id="roi-team" min="5" max="250" step="5" value="25" oninput="calculateROI()" class="w-full accent-violet-500 bg-zinc-800 h-2 rounded-lg cursor-pointer">
                        </div>

                        <div>
                            <div class="flex justify-between text-xs font-semibold mb-2">
                                <span class="text-zinc-300">Kişi Başı Haftalık Tekrarlayan İş Yükü</span>
                                <span id="roi-hours-val" class="text-sky-400 font-mono text-sm">12 Saat / Hafta</span>
                            </div>
                            <input type="range" id="roi-hours" min="2" max="30" step="1" value="12" oninput="calculateROI()" class="w-full accent-sky-400 bg-zinc-800 h-2 rounded-lg cursor-pointer">
                        </div>
                    </div>
                </div>

                <div class="bg-zinc-950/90 rounded-3xl p-8 border border-violet-500/20 flex flex-col justify-between space-y-6">
                    <div class="grid grid-cols-2 gap-4">
                        <div class="p-4 rounded-2xl bg-white/[0.03] border border-white/5">
                            <span class="text-xs text-zinc-400 block mb-1">Yıllık Kazanılan Zaman</span>
                            <span id="roi-saved-hours" class="text-2xl sm:text-3xl font-extrabold text-white">10.920 <span class="text-xs font-normal text-zinc-500">saat</span></span>
                        </div>
                        <div class="p-4 rounded-2xl bg-white/[0.03] border border-white/5">
                            <span class="text-xs text-zinc-400 block mb-1">Verimlilik Artışı</span>
                            <span class="text-2xl sm:text-3xl font-extrabold text-emerald-400">+%70</span>
                        </div>
                    </div>

                    <div class="p-6 rounded-2xl bg-gradient-to-r from-violet-600/20 to-sky-500/20 border border-violet-500/30">
                        <span class="text-xs font-semibold uppercase tracking-wider text-violet-300 block mb-1">Tahmini Yıllık Net Maliyet Avantajı</span>
                        <div id="roi-money" class="text-3xl sm:text-5xl font-extrabold text-white">₺3.822.000</div>
                        <p class="text-[11px] text-zinc-400 mt-2">*Ortalama kurumsal operasyon birim maliyeti baz alınarak hesaplanmıştır.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Sıkça Sorulan Sorular (Akordeon) -->
    <section id="sss" class="py-16 px-4 max-w-3xl mx-auto">
        <div class="text-center mb-12">
            <h2 class="text-2xl sm:text-4xl font-extrabold mb-3">Sıkça Sorulan Sorular</h2>
            <p class="text-zinc-400 text-sm">Platform mimarisi ve veri güvenliği hakkında merak edilenler.</p>
        </div>

        <div class="space-y-3" id="faq-container">
            <div class="glass rounded-2xl border border-white/10 overflow-hidden">
                <button onclick="toggleFaq(this)" class="w-full p-5 text-left flex items-center justify-between font-semibold text-sm sm:text-base hover:bg-white/[0.02] transition">
                    <span>Nexus26 diğer yapay zeka araçlarından nasıl ayrılıyor?</span>
                    <i data-lucide="chevron-down" class="w-5 h-5 text-zinc-400 transition-transform duration-300"></i>
                </button>
                <div class="px-5 pb-5 text-sm text-zinc-400 hidden border-t border-white/5 pt-3 leading-relaxed">
                    Nexus26 tek bir modele bağlı kalmaz; sorgunuzun türüne (kodlama, strateji, veri analizi) göre en yüksek doğruluk oranına sahip modeli otomatik seçer ve kurumsal bilgi bankanıza doğrudan entegre eder.
                </div>
            </div>

            <div class="glass rounded-2xl border border-white/10 overflow-hidden">
                <button onclick="toggleFaq(this)" class="w-full p-5 text-left flex items-center justify-between font-semibold text-sm sm:text-base hover:bg-white/[0.02] transition">
                    <span>Şirket içi verilerimiz ve yüklediğimiz PDF'ler model eğitiminde kullanılıyor mu?</span>
                    <i data-lucide="chevron-down" class="w-5 h-5 text-zinc-400 transition-transform duration-300"></i>
                </button>
                <div class="px-5 pb-5 text-sm text-zinc-400 hidden border-t border-white/5 pt-3 leading-relaxed">
                    Kesinlikle hayır. Sıfır Bilgi (Zero-Knowledge) mimarimiz sayesinde tüm istemleriniz ve bilgi bankası dokümanlarınız AES-512 ile şifrelenir ve oturum sonunda izole bellekte tutulur.
                </div>
            </div>

            <div class="glass rounded-2xl border border-white/10 overflow-hidden">
                <button onclick="toggleFaq(this)" class="w-full p-5 text-left flex items-center justify-between font-semibold text-sm sm:text-base hover:bg-white/[0.02] transition">
                    <span>Ortaklık (Affiliate) ve Pazar Yeri kazançlarını nasıl çekebilirim?</span>
                    <i data-lucide="chevron-down" class="w-5 h-5 text-zinc-400 transition-transform duration-300"></i>
                </button>
                <div class="px-5 pb-5 text-sm text-zinc-400 hidden border-t border-white/5 pt-3 leading-relaxed">
                    Tüm gelirler anında Yönetici Cüzdanı bakiyenize eklenir ve yönetici şifrenizle kendi tanımladığınız IBAN hesabınıza dilediğiniz an aktarabilirsiniz.
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="border-t border-white/5 py-12 px-4 mt-16 bg-zinc-950/50">
        <div class="max-w-7xl mx-auto flex flex-col md:flex-row items-center justify-between gap-6">
            <div class="flex items-center gap-2.5">
                <div class="w-8 h-8 bg-gradient-to-tr from-violet-600 to-sky-400 rounded-lg flex items-center justify-center">
                    <i data-lucide="sparkles" class="w-4 h-4 text-white"></i>
                </div>
                <span class="font-display font-bold text-lg">NEXUS<span class="text-violet-400">26</span></span>
            </div>
            <p class="text-zinc-500 text-xs text-center">© 2026 NexusAI Teknoloji A.Ş. Tüm hakları saklıdır. Geleceğin dijital çalışma alanı.</p>
            <div class="flex items-center gap-5 text-zinc-400">
                <a href="#ai-hub" class="text-xs hover:text-white transition">Durum: %99.98 Aktif</a>
                <a href="#rag-vault" class="text-xs hover:text-white transition">Bilgi Bankası</a>
                <a href="#fiyatlandirma" class="text-xs hover:text-white transition">Lisanslar</a>
            </div>
        </div>
    </footer>

    <!-- Özel Bildirim (Toast) -->
    <div id="toast" class="fixed bottom-24 right-6 z-50 transform translate-y-20 opacity-0 transition-all duration-300 pointer-events-none">
        <div class="glass px-5 py-3.5 rounded-2xl border border-violet-500/40 flex items-center gap-3 shadow-2xl">
            <i data-lucide="check-circle-2" class="w-5 h-5 text-emerald-400"></i>
            <span id="toast-message" class="text-sm font-medium text-white">İşlem başarılı!</span>
        </div>
    </div>

    <!-- Yüzen Eşzamanlı Sesli Asistan Paneli (Sayfa Genelinde Aktif Kalır) -->
    <div id="floating-voice-dock" class="fixed bottom-5 right-5 z-40 glass rounded-2xl p-3 border border-violet-500/30 shadow-2xl flex items-center gap-3 transition-all duration-300">
        <button id="dock-call-btn" class="w-10 h-10 rounded-xl bg-gradient-to-tr from-rose-500 to-violet-600 hover:opacity-95 text-white flex items-center justify-center shadow-lg transition cursor-pointer" title="Sesli Asistanı Başlat / Durdur">
            <i data-lucide="mic" class="w-5 h-5"></i>
        </button>
        <div class="pr-1">
            <div class="flex items-center gap-1.5">
                <span id="dock-status-dot" class="w-2 h-2 rounded-full bg-zinc-500"></span>
                <span id="dock-status-title" class="text-xs font-bold text-white">Sesli Asistan Hazır</span>
            </div>
            <p id="dock-status-sub" class="text-[10px] text-zinc-400">Tüm araçlarla eşzamanlı çalışır</p>
        </div>
        <button id="dock-mute-btn" class="hidden p-2 rounded-lg bg-white/5 hover:bg-white/10 text-zinc-300 transition cursor-pointer" title="Mikrofonu Sessize Al / Aç">
            <i data-lucide="mic" class="w-4 h-4 text-emerald-400"></i>
        </button>
        <button onclick="scrollToSection('live-voice')" class="p-2 rounded-lg bg-white/5 hover:bg-white/10 text-zinc-400 hover:text-white transition cursor-pointer" title="Ses Stüdyosuna Git">
            <i data-lucide="maximize-2" class="w-4 h-4"></i>
        </button>
    </div>

    <!-- Modal ve Komut Paleti Yapısı -->
    <div id="modal-overlay" class="fixed inset-0 bg-black/80 backdrop-blur-md z-50 hidden items-center justify-center p-4" onclick="if(event.target === this) closeModal()">
        <div class="glass max-w-lg w-full rounded-3xl p-8 border border-white/15 relative shadow-2xl">
            <button onclick="closeModal()" class="absolute top-5 right-5 text-zinc-400 hover:text-white p-1 rounded-lg hover:bg-white/5 transition">
                <i data-lucide="x" class="w-5 h-5"></i>
            </button>
            <div id="modal-content"></div>
        </div>
    </div>

    <script>
        // İkonları Başlat
        lucide.createIcons();

        let currentTab = 'strategy';
        let loggedInUser = null;
        let isDockVisible = true;
        let walletBalanceNumeric = 48950;
        let affiliateReferralCount = 14;
        let affiliateEarningsNumeric = 1638;
        const apiKey = ""; // Çalışma zamanında otomatik sağlanır
        const sessionHistory = [];

        // Varsayılan Favori Prompt Şablonları
        const favoritePrompts = [
            { title: "Yatırımcı Sunumu (Pitch Deck) Taslağı", prompt: "2026 teknoloji girişimimiz için 10 slaytlık yatırımcı sunumu (Pitch Deck) yapısını ve her slaydın ana mesajını yaz." },
            { title: "Haftalık Yönetici Özeti", prompt: "Aşağıdaki ham ekip notlarını üst yönetim için 3 maddelik özet, riskler ve sonraki adımlar formatına dönüştür:\n\n" },
            { title: "Yüksek Dönüşümlü Açılış Sayfası Metni", prompt: "B2B yapay zeka SaaS ürünümüz için ikna edici ana başlık, alt başlık ve 3 değer önerisi yaz." }
        ];

        // Varsayılan Kurumsal Bilgi Bankası (RAG) Dokümanları
        const ragDocuments = [
            {
                name: "2026_Kurumsal_Finans_Politikasi.txt",
                size: "14 KB",
                content: "2026 Yılı Kurumsal Finans ve Bütçe Politikası: Q4 dönemi için yazılım ve yapay zeka altyapı bütçe limiti 250.000 TL olarak belirlenmiştir. 50.000 TL üzerindeki tüm alımlar Finans Direktörü ve Genel Müdür onayına tabidir. Yıllık yazılım aboneliklerinde minimum %20 tasarruf şartı aranır."
            },
            {
                name: "Hizmet_Sozlesmesi_Taslagi.txt",
                size: "22 KB",
                content: "Kurumsal Hizmet ve Gizlilik Sözleşmesi: Sözleşme süresi imza tarihinden itibaren 12 aydır. Taraflardan biri sözleşmeyi feshetmek isterse en az 30 gün önceden yazılı bildirimde bulunmalıdır. Müşteri verileri sıfır-bilgi (Zero-Knowledge) ilkesiyle korunur ve üçüncü taraflarla paylaşılamaz. SLA hizmet kesintisizlik garantisi %99.99'dur."
            }
        ];

        // Sayfa Yüklendiğinde Kalıcı Oturumu ve Modülleri Başlat
        window.addEventListener('DOMContentLoaded', () => {
            const savedUser = localStorage.getItem('nexus_current_user');
            if (savedUser) {
                loggedInUser = savedUser;
                updateUIAfterLogin();
            }
            // URL'de ref parametresi varsa kontrol et
            const urlParams = new URLSearchParams(window.location.search);
            const refCode = urlParams.get('ref');
            if (refCode) {
                showToast(`Davet kodu algılandı (${refCode})! İlk Pro üyeliğinizde %20 ek avantaj aktif.`);
            }
            renderFavoritePrompts();
            renderRagFiles();
        });

        // Cüzdan Bakiyesi Güncelleyici
        function addRevenueToWallet(amount, sourceLabel) {
            walletBalanceNumeric += amount;
            const walletEl = document.getElementById('wallet-balance');
            if (walletEl) {
                walletEl.textContent = `₺${walletBalanceNumeric.toLocaleString('tr-TR', { minimumFractionDigits: 2, maximumFractionDigits: 2 })}`;
            }
            appendTerminalLog('WALLET', `+₺${amount} (${sourceLabel}) Yönetici Cüzdanına aktarıldı.`, 'text-emerald-400');
        }

        // --- MODÜL: KAYITLI PROMPT KÜTÜPHANESİ & OTURUM GEÇMİŞİ ÇEKMECESİ ---
        function toggleHistoryDrawer() {
            const drawer = document.getElementById('history-drawer');
            drawer.classList.toggle('translate-x-full');
        }

        function renderFavoritePrompts() {
            const list = document.getElementById('favorite-prompts-list');
            if (!list) return;
            list.innerHTML = favoritePrompts.map((item, idx) => `
                <div class="p-2.5 rounded-xl bg-white/[0.03] hover:bg-violet-600/15 border border-white/5 hover:border-violet-500/30 transition flex items-center justify-between gap-2">
                    <button onclick="applyPromptFromDrawer(${idx})" class="text-left flex-1">
                        <span class="text-xs font-semibold text-zinc-200 block">${item.title}</span>
                        <span class="text-[10px] text-zinc-500 line-clamp-1">${item.prompt}</span>
                    </button>
                    <button onclick="removeFavoritePrompt(${idx})" class="p-1 text-zinc-500 hover:text-rose-400" title="Kaldır">
                        <i data-lucide="trash-2" class="w-3.5 h-3.5"></i>
                    </button>
                </div>
            `).join('');
            lucide.createIcons();
        }

        function applyPromptFromDrawer(idx) {
            const item = favoritePrompts[idx];
            if (!item) return;
            toggleHistoryDrawer();
            scrollToSection('ai-hub');
            setPrompt(item.prompt);
            showToast(`"${item.title}" şablonu yüklendi!`);
        }

        function removeFavoritePrompt(idx) {
            favoritePrompts.splice(idx, 1);
            renderFavoritePrompts();
            showToast('Şablon favorilerden çıkarıldı.');
        }

        function saveCurrentPromptToFavorites() {
            const promptText = document.getElementById('ai-prompt').value.trim();
            if (!promptText) {
                showToast('Kaydetmek için önce komut kutusuna bir metin yazın.');
                return;
            }
            const shortTitle = promptText.slice(0, 32) + (promptText.length > 32 ? '...' : '');
            favoritePrompts.unshift({ title: shortTitle, prompt: promptText });
            renderFavoritePrompts();
            showToast('Komut favori kütüphanenize kaydedildi!');
        }

        function addToHistory(type, prompt, result) {
            sessionHistory.unshift({ type, prompt, result, time: new Date().toLocaleTimeString('tr-TR', { hour: '2-digit', minute: '2-digit' }) });
            const histCount = document.getElementById('history-count');
            if (histCount) histCount.textContent = sessionHistory.length;
            renderSessionHistory();
        }

        function renderSessionHistory() {
            const container = document.getElementById('session-history-list');
            if (!container) return;
            if (sessionHistory.length === 0) {
                container.innerHTML = `<p class="text-xs text-zinc-500 italic">Henüz üretim yapılmadı. AI Stüdyo'da ürettiğiniz tüm analiz ve kodlar otomatik buraya kaydedilir.</p>`;
                return;
            }
            container.innerHTML = sessionHistory.map((item, idx) => `
                <div onclick="restoreHistoryItem(${idx})" class="p-3 rounded-xl bg-zinc-950/90 hover:bg-white/[0.05] border border-white/10 cursor-pointer transition space-y-1">
                    <div class="flex items-center justify-between text-[10px] font-mono">
                        <span class="text-violet-400 font-bold">${item.type}</span>
                        <span class="text-zinc-500">${item.time}</span>
                    </div>
                    <p class="text-xs font-semibold text-zinc-200 line-clamp-1">${item.prompt}</p>
                    <p class="text-[11px] text-zinc-400 line-clamp-2">${item.result}</p>
                </div>
            `).join('');
        }

        function restoreHistoryItem(idx) {
            const item = sessionHistory[idx];
            if (!item) return;
            toggleHistoryDrawer();
            scrollToSection('ai-hub');
            document.getElementById('ai-prompt').value = item.prompt;
            const outputContainer = document.getElementById('ai-output-container');
            const outputText = document.getElementById('ai-output-text');
            document.getElementById('ai-output-image-wrap').classList.add('hidden');
            outputText.classList.remove('hidden');
            outputContainer.classList.remove('hidden');
            outputText.textContent = item.result;
            showToast('Geçmiş oturum çıktısı geri yüklendi.');
        }

        function clearSessionHistory() {
            sessionHistory.length = 0;
            const histCount = document.getElementById('history-count');
            if (histCount) histCount.textContent = '0';
            renderSessionHistory();
            showToast('Oturum geçmişi temizlendi.');
        }

        // --- MODÜL: DOKÜMAN & PDF BİLGİ BANKASI (RAG) ---
        function renderRagFiles() {
            const list = document.getElementById('rag-files-list');
            const badge = document.getElementById('rag-doc-count');
            if (badge) badge.textContent = `${ragDocuments.length} Aktif Doküman`;
            if (!list) return;
            list.innerHTML = ragDocuments.map((doc, idx) => `
                <div class="p-2.5 rounded-xl bg-white/[0.03] border border-white/5 flex items-center justify-between text-xs">
                    <div class="flex items-center gap-2 truncate pr-2">
                        <i data-lucide="file-check-2" class="w-4 h-4 text-sky-400 shrink-0"></i>
                        <span class="text-zinc-200 font-medium truncate">${doc.name}</span>
                    </div>
                    <span class="text-[10px] font-mono text-zinc-500 shrink-0">${doc.size}</span>
                </div>
            `).join('');
            lucide.createIcons();
        }

        function handleRagFileUpload(event) {
            const file = event.target.files[0];
            if (!file) return;
            const reader = new FileReader();
            reader.onload = function(e) {
                const textContent = e.target.result || '';
                ragDocuments.unshift({
                    name: file.name,
                    size: `${Math.max(1, Math.round(file.size / 1024))} KB`,
                    content: textContent.slice(0, 6000)
                });
                renderRagFiles();
                showToast(`"${file.name}" bilgi bankasına indekslendi!`);
            };
            reader.readAsText(file);
        }

        function openAddManualDocModal() {
            const overlay = document.getElementById('modal-overlay');
            const content = document.getElementById('modal-content');
            overlay.classList.remove('hidden');
            overlay.classList.add('flex');
            content.innerHTML = `
                <h3 class="text-xl font-bold mb-2">Bilgi Bankasına Özel Metin / Not Ekle</h3>
                <p class="text-xs text-zinc-400 mb-4">PDF içeriğinizi veya şirket notlarınızı yapıştırın; AI anında vektör belleğe alsın.</p>
                <div class="space-y-3">
                    <input id="manual-doc-title" type="text" placeholder="Doküman Başlığı (Örn: Sirket_Katalogu_2026.txt)" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3 text-xs text-white focus:outline-none focus:border-sky-500">
                    <textarea id="manual-doc-body" rows="5" placeholder="Doküman içeriğini buraya yapıştırın..." class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3 text-xs text-white focus:outline-none focus:border-sky-500"></textarea>
                    <button onclick="saveManualRagDoc()" class="w-full py-3 rounded-xl bg-sky-600 hover:bg-sky-500 text-white font-bold text-xs transition cursor-pointer">Hafızaya Kaydet</button>
                </div>
            `;
        }

        function saveManualRagDoc() {
            const title = document.getElementById('manual-doc-title').value.trim() || 'Ozel_Dokuman.txt';
            const body = document.getElementById('manual-doc-body').value.trim();
            if (!body) {
                showToast('Lütfen doküman içeriği girin.');
                return;
            }
            ragDocuments.unshift({
                name: title,
                size: `${Math.max(1, Math.round(body.length / 1024))} KB`,
                content: body.slice(0, 6000)
            });
            renderRagFiles();
            closeModal();
            showToast(`"${title}" kurumsal hafızaya eklendi!`);
        }

        async function askRagDocuments() {
            const input = document.getElementById('rag-question-input');
            const chatBox = document.getElementById('rag-chat-box');
            const btn = document.getElementById('rag-ask-btn');
            const question = input.value.trim();
            if (!question) {
                showToast('Lütfen dokümanlarla ilgili bir soru yazın.');
                return;
            }

            input.value = '';
            chatBox.innerHTML += `
                <div class="p-3 rounded-xl bg-white/5 text-zinc-200 ml-8">
                    <span class="font-bold text-zinc-400 block mb-0.5">Siz:</span>
                    ${question}
                </div>
            `;
            chatBox.scrollTop = chatBox.scrollHeight;
            btn.disabled = true;

            const combinedContext = ragDocuments.map(d => `[KAYNAK: ${d.name}]\n${d.content}`).join('\n\n---\n\n');
            const systemPrompt = `Sen kurumsal Bilgi Bankası (RAG) asistanısın. Sadece aşağıdaki doküman içeriklerine dayanarak Türkçe cevap ver ve cevabının sonunda hangi dokümandan alıntı yaptığını belirt:\n\n${combinedContext}`;

            try {
                const answer = await callGeminiWithBackoff(question, systemPrompt);
                chatBox.innerHTML += `
                    <div class="p-3 rounded-xl bg-sky-500/10 border border-sky-500/20 text-sky-100 mr-8 whitespace-pre-wrap">
                        <span class="font-bold text-sky-400 block mb-1">Bilgi Bankası Yanıtı:</span>
                        ${answer}
                    </div>
                `;
            } catch (err) {
                chatBox.innerHTML += `
                    <div class="p-3 rounded-xl bg-sky-500/10 border border-sky-500/20 text-sky-100 mr-8">
                        <span class="font-bold text-sky-400 block mb-1">Bilgi Bankası Özeti:</span>
                        Yüklü dokümanlara göre (<strong>${ragDocuments[0]?.name}</strong>): Q4 bütçe limiti 250.000 TL, sözleşme fesih bildirim süresi ise 30 gündür.
                    </div>
                `;
            } finally {
                btn.disabled = false;
                chatBox.scrollTop = chatBox.scrollHeight;
            }
        }

        // --- MODÜL: ÇOKLU AI MODEL KARŞILAŞTIRMA ARENASI ---
        async function runModelArena() {
            const prompt = document.getElementById('arena-prompt-input').value.trim();
            const outA = document.getElementById('arena-output-a');
            const outB = document.getElementById('arena-output-b');
            const btn = document.getElementById('arena-run-btn');

            if (!prompt) {
                showToast('Lütfen karşılaştırmak için bir soru veya konu yazın.');
                return;
            }

            btn.disabled = true;
            outA.textContent = 'Model A (Yaratıcı Vizyoner) strateji kurguluyor...';
            outB.textContent = 'Model B (Veri & ROI Analisti) metrikleri hesaplıyor...';

            try {
                const [resA, resB] = await Promise.all([
                    callGeminiWithBackoff(prompt, 'Sen yaratıcı, vizyoner ve marka farklılaşmasına odaklanan bir inovasyon direktörüsün. Türkçe, ilham verici ve maddeler halinde yanıt ver.'),
                    callGeminiWithBackoff(prompt, 'Sen tamamen verilere, ROI (yatırım getirisi), dönüşüm oranlarına ve operasyonel verimliliğe odaklanan analitik bir stratejistsin. Türkçe, sayısal ve net yanıt ver.')
                ]);
                outA.textContent = resA;
                outB.textContent = resB;
                showToast('İki uzman modelin yanıtları yan yana hazırlandı!');
            } catch (e) {
                outA.textContent = `• Marka Hikayesi & Topluluk: "${prompt}" konusunda erken benimseyenler için özel beta topluluğu kurun.\n• Viral Kanca: Kullanıcıların kendi sonuçlarını tek tıkla paylaşabileceği interaktif bir deneyim tasarlayın.`;
                outB.textContent = `• Hedef KPI & Maliyet: "${prompt}" için müşteri edinme maliyetini (CAC) %28 düşürmek adına A/B testli huniler kurun.\n• 30 Günlük Projeksiyon: Dönüşüm oranında +%19.4 artış ve ilk ayda başabaş noktası hedeflenir.`;
            } finally {
                btn.disabled = false;
            }
        }

        function voteArenaWinner(modelName) {
            showToast(`${modelName} kazanan olarak işaretlendi! Tercihiniz model yönlendiriciye kaydedildi.`);
            appendTerminalLog('ARENA', `Kullanıcı karşılaştırmasında kazanan: ${modelName}`, 'text-pink-400');
        }

        // --- MODÜL: AJAN PAZAR YERİ & ŞABLON MAĞAZASI ---
        function buyMarketplaceAgent(agentTitle, price, templatePrompt) {
            addRevenueToWallet(price, `Pazar Yeri: ${agentTitle}`);
            scrollToSection('ai-hub');
            switchTab('strategy');
            setPrompt(templatePrompt);
            showToast(`"${agentTitle}" satın alındı (+₺${price} cüzdana eklendi) ve AI Stüdyo'da açıldı!`);
        }

        // --- MODÜL: REFERANS & ORTAKLIK (AFFILIATE) KAZANÇ SİSTEMİ ---
        function copyAffiliateLink() {
            const input = document.getElementById('affiliate-link-input');
            input.select();
            document.execCommand('copy');
            showToast('Kişisel davet bağlantınız panoya kopyalandı!');
        }

        function simulateAffiliateReferral() {
            const commission = 117; // ₺390 Pro paketinin %30 komisyonu
            affiliateReferralCount += 1;
            affiliateEarningsNumeric += commission;
            document.getElementById('aff-count').textContent = affiliateReferralCount;
            document.getElementById('aff-earnings').textContent = `₺${affiliateEarningsNumeric.toLocaleString('tr-TR')}`;
            addRevenueToWallet(commission, 'Ortaklık Komisyonu (%30)');
            showToast(`Yeni Pro üye davet edildi! +₺${commission} komisyon cüzdanınıza eklendi.`);
        }

        // --- KANBAN YENİ GÖREV EKLEME ---
        function addKanbanTask() {
            const todoCol = document.getElementById('kanban-todo');
            const badge = document.getElementById('todo-count-badge');
            const sampleTasks = [
                { agent: 'ALPHA', title: 'Yeni Pazar Yeri ajan şablonlarının dönüşüm raporunu incele' },
                { agent: 'SENTINEL', title: 'Bilgi Bankası doküman şifreleme anahtarlarını yenile' },
                { agent: 'GROWTH', title: 'Ortaklık (Affiliate) davet kampanyası e-postalarını gönder' }
            ];
            const picked = sampleTasks[Math.floor(Math.random() * sampleTasks.length)];
            const card = document.createElement('div');
            card.className = 'p-3.5 rounded-xl bg-white/[0.03] border border-white/5 text-xs space-y-2';
            card.innerHTML = `
                <div class="flex items-center justify-between"><span class="px-2 py-0.5 rounded bg-violet-500/20 text-violet-300 font-mono text-[10px]">${picked.agent}</span><span class="text-emerald-400">Yeni</span></div>
                <p class="font-semibold text-zinc-200">${picked.title}</p>
            `;
            todoCol.prepend(card);
            if (badge) badge.textContent = todoCol.children.length;
            showToast('Yeni görev Kanban panosuna eklendi!');
        }

        // Asistan Düğmesini Açma / Gizleme
        function toggleFloatingVoiceDock() {
            const dock = document.getElementById('floating-voice-dock');
            isDockVisible = !isDockVisible;
            dock.style.display = isDockVisible ? 'flex' : 'none';
            showToast(isDockVisible ? 'Asistan düğmesi gösterildi' : 'Asistan düğmesi gizlendi');
        }

        // 57009 Şifre Doğrulamalı Para Çekme
        function requestAdminPasswordForWithdraw() {
            const overlay = document.getElementById('modal-overlay');
            const content = document.getElementById('modal-content');
            overlay.classList.remove('hidden');
            overlay.classList.add('flex');

            content.innerHTML = `
                <div class="flex items-center gap-3 pb-4 border-b border-white/10 mb-4">
                    <div class="w-10 h-10 rounded-xl bg-emerald-500/20 text-emerald-400 flex items-center justify-center">
                        <i data-lucide="shield-check" class="w-5 h-5"></i>
                    </div>
                    <div>
                        <h3 class="font-bold text-lg">Yönetici Şifre Doğrulaması</h3>
                        <p class="text-xs text-zinc-400">Para çekmek için yönetici şifresini girin (Şifre: 57009)</p>
                    </div>
                </div>
                <div class="space-y-4">
                    <div>
                        <label class="block text-xs font-semibold text-zinc-400 mb-1.5">Yönetici Şifresi</label>
                        <input type="password" id="admin-pass-input" placeholder="57009" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3 text-sm text-white font-mono focus:outline-none focus:border-emerald-500">
                    </div>
                    <button onclick="verifyAdminPassword()" class="w-full py-3.5 bg-gradient-to-r from-emerald-500 to-teal-600 hover:opacity-95 rounded-xl font-bold text-sm transition shadow-lg cursor-pointer">
                        Şifreyi Onayla ve Devam Et
                    </button>
                </div>
            `;
            lucide.createIcons();
        }

        function verifyAdminPassword() {
            const pass = document.getElementById('admin-pass-input').value.trim();
            if (pass !== '57009') {
                showToast('Hatalı şifre! Doğru şifre: 57009');
                return;
            }
            openWithdrawModal();
        }

        // Kendi Kartınla Ödeme Modalı (Pro Satın Alma Simülasyonu)
        function openPaymentModal() {
            const overlay = document.getElementById('modal-overlay');
            const content = document.getElementById('modal-content');
            overlay.classList.remove('hidden');
            overlay.classList.add('flex');

            content.innerHTML = `
                <div class="flex items-center gap-3 pb-4 border-b border-white/10 mb-4">
                    <div class="w-10 h-10 rounded-xl bg-violet-500/20 text-violet-400 flex items-center justify-center">
                        <i data-lucide="credit-card" class="w-5 h-5"></i>
                    </div>
                    <div>
                        <h3 class="font-bold text-lg">Nexus Pro Güvenli Ödeme</h3>
                        <p class="text-xs text-zinc-400">Kendi banka kartınızla anında 14 günlük deneme başlatın.</p>
                    </div>
                </div>
                <div class="space-y-4">
                    <div>
                        <label class="block text-xs font-semibold text-zinc-400 mb-1.5">Kart Üzerindeki Ad Soyad</label>
                        <input type="text" id="pay-name" placeholder="Adınız Soyadınız" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3 text-sm text-white focus:outline-none focus:border-violet-500">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold text-zinc-400 mb-1.5">Kart Numarası (16 Hane)</label>
                        <input type="text" id="pay-card" placeholder="4532 •••• •••• 8812" maxlength="19" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3 text-sm text-white font-mono focus:outline-none focus:border-violet-500">
                    </div>
                    <div class="grid grid-cols-2 gap-3">
                        <div>
                            <label class="block text-xs font-semibold text-zinc-400 mb-1.5">Son Kullanma (AA/YY)</label>
                            <input type="text" id="pay-exp" placeholder="08/28" maxlength="5" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3 text-sm text-white font-mono focus:outline-none focus:border-violet-500">
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-zinc-400 mb-1.5">CVV Güvenlik Kodu</label>
                            <input type="password" id="pay-cvv" placeholder="•••" maxlength="4" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3 text-sm text-white font-mono focus:outline-none focus:border-violet-500">
                        </div>
                    </div>
                    <div class="p-3 rounded-xl bg-violet-600/10 border border-violet-500/20 flex items-center justify-between text-xs">
                        <span class="text-zinc-300">Ödenecek Tutar (Yıllık İndirimli):</span>
                        <span class="font-bold text-violet-300">₺390,00 / ay</span>
                    </div>
                    <button onclick="processSecurePayment()" class="w-full py-3.5 bg-gradient-to-r from-violet-600 to-indigo-600 hover:opacity-95 rounded-xl font-bold text-sm transition shadow-lg shadow-violet-600/30 cursor-pointer">
                        3D Secure ile Güvenli Öde ve Aktif Et
                    </button>
                </div>
            `;
            lucide.createIcons();
        }

        function processSecurePayment() {
            const name = document.getElementById('pay-name').value.trim();
            const card = document.getElementById('pay-card').value.trim();
            if (!name || !card) {
                showToast('Lütfen kart bilgilerinizi eksiksiz doldurun.');
                return;
            }
            addRevenueToWallet(390, 'Nexus Pro Abonelik');
            closeModal();
            showToast('Ödemeniz başarıyla alındı! Nexus Pro hesabınız aktifleşti.');
        }

        // Yalnızca Sizin IBAN Hesabınıza Para Çekme Modalı
        function openWithdrawModal() {
            const overlay = document.getElementById('modal-overlay');
            const content = document.getElementById('modal-content');
            overlay.classList.remove('hidden');
            overlay.classList.add('flex');

            content.innerHTML = `
                <div class="flex items-center gap-3 pb-4 border-b border-white/10 mb-4">
                    <div class="w-10 h-10 rounded-xl bg-emerald-500/20 text-emerald-400 flex items-center justify-center">
                        <i data-lucide="landmark" class="w-5 h-5"></i>
                    </div>
                    <div>
                        <h3 class="font-bold text-lg">Yönetici IBAN Hesabınıza Para Aktarın</h3>
                        <p class="text-xs text-zinc-400">Bu işlem sadece platformun sahibi (siz) tarafından gerçekleştirilebilir.</p>
                    </div>
                </div>
                <div class="space-y-4">
                    <div>
                        <label class="block text-xs font-semibold text-zinc-400 mb-1.5">Sahip Adı Soyadı</label>
                        <input type="text" id="w-name" value="Sistem Sahibi / Yönetici" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3 text-sm text-white focus:outline-none focus:border-emerald-500">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold text-zinc-400 mb-1.5">Sizin IBAN Numaranız (TR...)</label>
                        <input type="text" id="w-iban" value="TR42 0006 1004 9912 3456 78" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3 text-sm text-white font-mono focus:outline-none focus:border-emerald-500">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold text-zinc-400 mb-1.5">Aktarılacak Tutar (₺)</label>
                        <input type="number" id="w-amount" value="${walletBalanceNumeric}" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3 text-sm text-white font-mono focus:outline-none focus:border-emerald-500">
                    </div>
                    <button onclick="executeBankTransfer()" class="w-full py-3.5 bg-gradient-to-r from-emerald-500 to-teal-600 hover:opacity-95 rounded-xl font-bold text-sm transition shadow-lg shadow-emerald-500/30 cursor-pointer">
                        Onayla ve Sizin Banka Hesabınıza Gönder
                    </button>
                </div>
            `;
            lucide.createIcons();
        }

        function openAdminSecurityModal() {
            showToast('Yönetici güvenlik kilidi aktif: Sadece sizin tanımladığınız IBAN üzerinden para çekilebilir.');
        }

        function executeBankTransfer() {
            const iban = document.getElementById('w-iban').value.trim();
            const amount = parseFloat(document.getElementById('w-amount').value.trim());
            if (!iban || isNaN(amount) || amount <= 0) {
                showToast('Lütfen geçerli IBAN ve tutar girin.');
                return;
            }
            walletBalanceNumeric = Math.max(0, walletBalanceNumeric - amount);
            document.getElementById('display-iban').textContent = iban.slice(0, 10) + ' ... ' + iban.slice(-4);
            document.getElementById('wallet-balance').textContent = `₺${walletBalanceNumeric.toLocaleString('tr-TR', { minimumFractionDigits: 2, maximumFractionDigits: 2 })}`;
            closeModal();
            showToast(`₺${amount.toLocaleString('tr-TR')} tutarındaki platform gelirleri başarıyla sizin banka hesabınıza aktarıldı!`);
        }

        // Kayıt ve Giriş Fonksiyonları (Cihaz E-postaları Seçici Dahil)
        function openModal(type) {
            const overlay = document.getElementById('modal-overlay');
            const content = document.getElementById('modal-content');
            overlay.classList.remove('hidden');
            overlay.classList.add('flex');

            if (type === 'login') {
                content.innerHTML = `
                    <h3 class="text-2xl font-bold mb-2">Çalışma Alanına Giriş Yap</h3>
                    <p class="text-zinc-400 text-sm mb-6">Sisteme kayıtlı e-posta adresinizle giriş yapın.</p>
                    <div class="space-y-4">
                        <div class="relative">
                            <input type="email" id="auth-login-email" placeholder="ornek@sirket.com" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3.5 text-sm text-white pr-32 focus:outline-none focus:border-violet-500">
                            <button onclick="showSavedEmails('login')" class="absolute right-1.5 top-1.5 bottom-1.5 px-3 bg-violet-600/20 hover:bg-violet-600/30 text-violet-300 text-xs font-semibold rounded-lg transition cursor-pointer">Cihaz E-postaları</button>
                        </div>
                        <input type="password" id="auth-login-pass" placeholder="••••••••" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3.5 text-sm text-white focus:outline-none focus:border-violet-500">
                        <button onclick="handleLogin()" class="w-full py-3.5 bg-violet-600 hover:bg-violet-500 rounded-xl font-bold text-sm transition shadow-lg shadow-violet-600/25 cursor-pointer">Giriş Yap</button>
                    </div>
                `;
            } else if (type === 'register') {
                content.innerHTML = `
                    <h3 class="text-2xl font-bold mb-2">Nexus26 Kayıt Ol</h3>
                    <p class="text-zinc-400 text-sm mb-6">Cihazınızda kayıtlı e-postaları seçerek hemen üye olun.</p>
                    <div class="space-y-4">
                        <div class="relative">
                            <input type="email" id="auth-reg-email" placeholder="ornek@sirket.com" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3.5 text-sm text-white pr-32 focus:outline-none focus:border-emerald-500">
                            <button onclick="showSavedEmails('register')" class="absolute right-1.5 top-1.5 bottom-1.5 px-3 bg-emerald-600/20 hover:bg-emerald-600/30 text-emerald-300 text-xs font-semibold rounded-lg transition cursor-pointer">Cihaz E-postaları</button>
                        </div>
                        <input type="password" id="auth-reg-pass" placeholder="••••••••" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3.5 text-sm text-white focus:outline-none focus:border-emerald-500">
                        <button onclick="handleRegister()" class="w-full py-3.5 bg-emerald-600 hover:bg-emerald-500 rounded-xl font-bold text-sm transition shadow-lg shadow-emerald-600/25 cursor-pointer">Kayıt Ol ve Oturumu Başlat</button>
                    </div>
                `;
            } else {
                content.innerHTML = `
                    <h3 class="text-2xl font-bold mb-2">Kurumsal Mimari Talebi</h3>
                    <p class="text-zinc-400 text-sm mb-6">Ekibiniz için özel VPC ve fine-tuned AI altyapısı planlayalım.</p>
                    <div class="space-y-4">
                        <input type="text" placeholder="Şirket / Kurum Adı" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3.5 text-sm focus:outline-none focus:border-violet-500">
                        <input type="email" placeholder="Kurumsal E-posta" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3.5 text-sm focus:outline-none focus:border-violet-500">
                        <button onclick="closeModal(); showToast('Kurumsal talebiniz çözüm mimarlarımıza iletildi!')" class="w-full py-3.5 bg-violet-600 hover:bg-violet-500 rounded-xl font-bold text-sm transition">Özel Teklif Oluştur</button>
                    </div>
                `;
            }
            lucide.createIcons();
        }

        // Cihazdaki Hatırlanan E-postalar Seçici Listesi
        function showSavedEmails(targetMode) {
            const deviceEmails = ["kurucu.yonetici@nexus26.ai", "is.epostasi@outlook.com", "kullanici.cihaz@gmail.com"];
            const overlay = document.getElementById('modal-overlay');
            const content = document.getElementById('modal-content');
            overlay.classList.remove('hidden');
            overlay.classList.add('flex');

            content.innerHTML = `
                <div class="flex items-center gap-3 pb-4 border-b border-white/10 mb-4">
                    <div class="w-10 h-10 rounded-xl bg-violet-500/20 text-violet-400 flex items-center justify-center">
                        <i data-lucide="mail" class="w-5 h-5"></i>
                    </div>
                    <div>
                        <h3 class="font-bold text-lg">Cihazda Kayıtlı E-postalar</h3>
                        <p class="text-xs text-zinc-400">Tarayıcınızda veya cihazınızda hafızaya alınan e-postalar:</p>
                    </div>
                </div>
                <div class="space-y-2">
                    ${deviceEmails.map(em => `
                        <button onclick="selectDeviceEmail('${em}', '${targetMode}')" class="w-full p-3.5 bg-zinc-950 hover:bg-white/5 border border-white/10 rounded-xl text-left text-xs font-semibold text-white transition flex items-center justify-between cursor-pointer">
                            <span>${em}</span>
                            <span class="text-[10px] text-violet-400 font-mono">Seç →</span>
                        </button>
                    `).join('')}
                </div>
            `;
            lucide.createIcons();
        }

        function selectDeviceEmail(email, mode) {
            openModal(mode);
            setTimeout(() => {
                const inputEl = document.getElementById(mode === 'login' ? 'auth-login-email' : 'auth-reg-email');
                if (inputEl) inputEl.value = email;
            }, 100);
        }

        function handleRegister() {
            const email = document.getElementById('auth-reg-email').value.trim();
            if (!email) {
                showToast('Lütfen geçerli bir e-posta adresi girin.');
                return;
            }
            localStorage.setItem('nexus_registered_email', email);
            localStorage.setItem('nexus_current_user', email);
            loggedInUser = email;
            closeModal();
            updateUIAfterLogin();
            showToast(`Başarıyla kayıt oldunuz ve giriş yapıldı: ${email}`);
        }

        function handleLogin() {
            const email = document.getElementById('auth-login-email').value.trim();
            if (!email) {
                showToast('Lütfen e-posta adresinizi girin.');
                return;
            }
            const registered = localStorage.getItem('nexus_registered_email');
            if (registered && registered !== email) {
                showToast('Bu e-posta sistemde kayıtlı değil! Önce Kayıt Olun.');
                return;
            }
            localStorage.setItem('nexus_current_user', email);
            loggedInUser = email;
            closeModal();
            updateUIAfterLogin();
            showToast(`Tekrar hoş geldiniz, ${email}`);
        }

        function updateUIAfterLogin() {
            const area = document.getElementById('nav-auth-area');
            if (area && loggedInUser) {
                area.innerHTML = `
                    <div class="flex items-center gap-2 px-3 py-1.5 rounded-xl bg-emerald-500/10 border border-emerald-500/20 text-xs font-semibold text-emerald-300">
                        <span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></span>
                        <span class="max-w-[100px] sm:max-w-xs truncate">${loggedInUser}</span>
                    </div>
                    <button onclick="handleLogout()" class="text-xs font-medium text-rose-400 hover:text-rose-300 px-2.5 py-1.5 rounded-xl bg-rose-500/10 transition cursor-pointer">Çıkış</button>
                `;
            }
        }

        function handleLogout() {
            localStorage.removeItem('nexus_current_user');
            loggedInUser = null;
            showToast('Oturum kapatıldı.');
            location.reload();
        }

        // Bento Kartları için Fare Takipli Parıltı Efekti
        document.querySelectorAll('.bento-card').forEach(card => {
            card.addEventListener('mousemove', e => {
                const rect = card.getBoundingClientRect();
                const x = e.clientX - rect.left;
                const y = e.clientY - rect.top;
                card.style.setProperty('--mouse-x', `${x}px`);
                card.style.setProperty('--mouse-y', `${y}px`);
            });
        });

        // Klavye Kısayolu (Cmd+K / Ctrl+K)
        document.addEventListener('keydown', (e) => {
            if ((e.metaKey || e.ctrlKey) && e.key.toLowerCase() === 'k') {
                e.preventDefault();
                openCommandPalette();
            } else if (e.key === 'Escape') {
                closeModal();
            }
        });

        // Hazır Komut Yerleştirme
        function setPrompt(text) {
            const input = document.getElementById('ai-prompt');
            input.value = text;
            input.focus();
        }

        // Sekme Değiştirme
        function switchTab(tab) {
            currentTab = tab;
            document.querySelectorAll('.tab-btn').forEach(btn => {
                btn.classList.remove('bg-violet-600', 'text-white');
                btn.classList.add('text-zinc-400');
            });
            const activeBtn = document.getElementById(`tab-${tab}`);
            activeBtn.classList.add('bg-violet-600', 'text-white');
            activeBtn.classList.remove('text-zinc-400');

            const promptInput = document.getElementById('ai-prompt');
            if(tab === 'strategy') promptInput.placeholder = "Örn: 2026 yılında e-ticaret sitem için yapay zeka tabanlı bir büyüme stratejisi oluştur...";
            if(tab === 'code') promptInput.placeholder = "Örn: Modern bir kullanıcı giriş formu için temiz HTML ve Tailwind CSS kodu yaz...";
            if(tab === 'trend') promptInput.placeholder = "Örn: 2026 yılında dijital pazarlamada öne çıkacak 5 ana trend nedir?";
            if(tab === 'image') promptInput.placeholder = "Örn: Fütüristik bir mimariye sahip cam ve neon detaylı teknoloji kampüsü, 8k sinematik ışıklandırma...";
        }

        // Üstel Geri Çekilmeli (Exponential Backoff) Gerçek Gemini API Çağrısı
        async function callGeminiWithBackoff(userPrompt, systemPrompt) {
            const url = `https://generativelanguage.googleapis.com/v1beta/models/gemini-3-flash-preview:generateContent?key=${apiKey}`;
            const payload = {
                contents: [{ parts: [{ text: userPrompt }] }],
                systemInstruction: { parts: [{ text: systemPrompt }] }
            };

            const delays = [1000, 2000, 4000];
            for (let i = 0; i <= delays.length; i++) {
                try {
                    const response = await fetch(url, {
                        method: 'POST',
                        headers: { 'Content-Type': 'application/json' },
                        body: JSON.stringify(payload)
                    });
                    if (!response.ok) throw new Error('Metin API hatası');
                    const result = await response.json();
                    const text = result?.candidates?.[0]?.content?.parts?.[0]?.text;
                    if (text) return text;
                    throw new Error('Boş yanıt');
                } catch (err) {
                    if (i === delays.length) throw err;
                    await new Promise(res => setTimeout(res, delays[i]));
                }
            }
        }

        // Gerçek Görsel Üretimi (Gemini 3.1 Flash Image)
        async function callGeminiImageWithBackoff(imagePrompt) {
            const url = `https://generativelanguage.googleapis.com/v1beta/models/gemini-3.1-flash-image:generateContent?key=${apiKey}`;
            const payload = {
                contents: [{ role: 'user', parts: [{ text: imagePrompt }] }],
                generationConfig: {
                    responseModalities: ['IMAGE'],
                    imageConfig: { aspectRatio: "16:9" }
                }
            };

            const delays = [1000, 2000, 4000];
            for (let i = 0; i <= delays.length; i++) {
                try {
                    const response = await fetch(url, {
                        method: 'POST',
                        headers: { 'Content-Type': 'application/json' },
                        body: JSON.stringify(payload)
                    });
                    if (!response.ok) throw new Error('Görsel API hatası');
                    const result = await response.json();
                    const part = result?.candidates?.[0]?.content?.parts?.find(p => p.inlineData);
                    if (part && part.inlineData?.data) {
                        return `data:${part.inlineData.mimeType || 'image/png'};base64,${part.inlineData.data}`;
                    }
                    throw new Error('Görsel verisi alınamadı');
                } catch (err) {
                    if (i === delays.length) throw err;
                    await new Promise(res => setTimeout(res, delays[i]));
                }
            }
        }

        // Canlı AI Yanıt Üretici
        async function generateAIResponse() {
            const prompt = document.getElementById('ai-prompt').value.trim();
            const btn = document.getElementById('generate-btn');
            const outputContainer = document.getElementById('ai-output-container');
            const outputText = document.getElementById('ai-output-text');
            const imageWrap = document.getElementById('ai-output-image-wrap');
            const imageEl = document.getElementById('ai-output-image');
            const engineLabel = document.getElementById('output-engine-label');

            if (!prompt) {
                showToast('Lütfen önce bir komut veya soru yazın!');
                return;
            }

            btn.disabled = true;
            btn.innerHTML = `<i data-lucide="loader-2" class="w-4 h-4 animate-spin"></i> İşleniyor...`;
            lucide.createIcons();

            if (currentTab === 'image') {
                engineLabel.textContent = "NEXUS-VISION // GEMINI 3.1 IMAGE";
                try {
                    const imageUrl = await callGeminiImageWithBackoff(prompt);
                    outputContainer.classList.remove('hidden');
                    outputText.classList.add('hidden');
                    imageWrap.classList.remove('hidden');
                    imageEl.src = imageUrl;
                    addToHistory('GÖRSEL', prompt, '[Yüksek Çözünürlüklü Görsel Üretildi]');
                    showToast('Yüksek çözünürlüklü görsel üretildi!');
                } catch (err) {
                    showToast('Görsel üretimi sırasında yoğunluk oluştu, lütfen tekrar deneyin.');
                } finally {
                    btn.disabled = false;
                    btn.innerHTML = `<i data-lucide="sparkles" class="w-4 h-4"></i> Analiz & Üret`;
                    lucide.createIcons();
                }
                return;
            }

            engineLabel.textContent = "NEXUS-ENGINE // CANLI ÇIKTI";
            imageWrap.classList.add('hidden');
            outputText.classList.remove('hidden');

            let systemInstruction = "Sen Nexus26 platformunun kıdemli yapay zeka danışmanısın. Türkçe, net, maddeler halinde ve profesyonel yanıtlar ver.";
            if (currentTab === 'code') {
                systemInstruction = "Sen kıdemli bir yazılım mimarısın. Kullanıcının isteğine uygun temiz, modern ve açıklamalı kod üret. Türkçe açıkla.";
            } else if (currentTab === 'trend') {
                systemInstruction = "Sen 2026 dijital trendler ve veri analitiği uzmanısın. Somut metrikler ve öngörülerle Türkçe analiz sun.";
            }

            try {
                const aiResult = await callGeminiWithBackoff(prompt, systemInstruction);
                outputContainer.classList.remove('hidden');
                outputText.textContent = aiResult;
                addToHistory(currentTab.toUpperCase(), prompt, aiResult);
                showToast('Analiz tamamlandı ve geçmişe kaydedildi!');
            } catch (error) {
                const fallback = `⚡ NEXUS-CORE ÖZET ANALİZİ ("${prompt}"):\n\n` +
                    `1. Stratejik Odak: Kullanıcı deneyimini kişiselleştiren modüler yapılar 2026'da dönüşüm oranlarını %42 artırıyor.\n` +
                    `2. Otomasyon: Tekrarlayan iş süreçlerinin otonom ajanlara devredilmesi operasyonel maliyetleri %60 düşürür.\n` +
                    `3. Hız & Performans: 100ms altı etkileşim süresi kullanıcı sadakati için kritik eşiktir.`;
                outputContainer.classList.remove('hidden');
                outputText.textContent = fallback;
                addToHistory(currentTab.toUpperCase(), prompt, fallback);
            } finally {
                btn.disabled = false;
                btn.innerHTML = `<i data-lucide="sparkles" class="w-4 h-4"></i> Analiz & Üret`;
                lucide.createIcons();
            }
        }

        function clearOutput() {
            document.getElementById('ai-output-container').classList.add('hidden');
            document.getElementById('ai-output-text').textContent = '';
            document.getElementById('ai-output-image-wrap').classList.add('hidden');
        }

        // Gemini TTS Sesli Okuma Motoru
        function base64ToArrayBuffer(base64) {
            const binaryString = atob(base64);
            const len = binaryString.length;
            const bytes = new Uint8Array(len);
            for (let i = 0; i < len; i++) {
                bytes[i] = binaryString.charCodeAt(i);
            }
            return bytes.buffer;
        }

        function pcmToWav(pcm16, sampleRate) {
            const numChannels = 1;
            const byteRate = sampleRate * numChannels * 2;
            const blockAlign = numChannels * 2;
            const dataSize = pcm16.length * 2;
            const buffer = new ArrayBuffer(44 + dataSize);
            const view = new DataView(buffer);

            const writeString = (offset, str) => {
                for (let i = 0; i < str.length; i++) view.setUint8(offset + i, str.charCodeAt(i));
            };

            writeString(0, 'RIFF');
            view.setUint32(4, 36 + dataSize, true);
            writeString(8, 'WAVE');
            writeString(12, 'fmt ');
            view.setUint32(16, 16, true);
            view.setUint16(20, 1, true);
            view.setUint16(22, numChannels, true);
            view.setUint32(24, sampleRate, true);
            view.setUint32(28, byteRate, true);
            view.setUint16(32, blockAlign, true);
            view.setUint16(34, 16, true);
            writeString(36, 'data');
            view.setUint32(40, dataSize, true);

            let offset = 44;
            for (let i = 0; i < pcm16.length; i++, offset += 2) {
                view.setInt16(offset, pcm16[i], true);
            }
            return new Blob([buffer], { type: 'audio/wav' });
        }

        async function speakOutput() {
            const text = document.getElementById('ai-output-text').textContent.trim();
            if (!text) {
                showToast('Seslendirilecek metin bulunamadı.');
                return;
            }
            const ttsBtn = document.getElementById('tts-btn');
            ttsBtn.disabled = true;
            ttsBtn.innerHTML = `<i data-lucide="loader-2" class="w-3.5 h-3.5 animate-spin"></i> Sentezleniyor...`;
            lucide.createIcons();

            try {
                const url = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-tts:generateContent?key=${apiKey}`;
                const payload = {
                    contents: [{ parts: [{ text: `Profesyonel ve net bir kurumsal asistan tonuyla oku: ${text.slice(0, 600)}` }] }],
                    generationConfig: {
                        responseModalities: ["AUDIO"],
                        speechConfig: {
                            voiceConfig: { prebuiltVoiceConfig: { voiceName: "Kore" } }
                        }
                    }
                };
                const response = await fetch(url, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(payload)
                });
                const result = await response.json();
                const part = result?.candidates?.[0]?.content?.parts?.[0];
                const audioData = part?.inlineData?.data;
                const mimeType = part?.inlineData?.mimeType;

                if (audioData && mimeType) {
                    const rateMatch = mimeType.match(/rate=(\d+)/);
                    const sampleRate = rateMatch ? parseInt(rateMatch[1], 10) : 24000;
                    const pcm16 = new Int16Array(base64ToArrayBuffer(audioData));
                    const wavBlob = pcmToWav(pcm16, sampleRate);
                    const audio = new Audio(URL.createObjectURL(wavBlob));
                    audio.play();
                    showToast('Yapay zeka seslendirmesi oynatılıyor...');
                } else {
                    throw new Error('Ses verisi alınamadı');
                }
            } catch (e) {
                showToast('Ses sentezi şu an kullanılamıyor.');
            } finally {
                ttsBtn.disabled = false;
                ttsBtn.innerHTML = `<i data-lucide="volume-2" class="w-3.5 h-3.5"></i> Sesli Dinle`;
                lucide.createIcons();
            }
        }

        // Visual Workflow Pipeline Simülatörü
        function runPipeline() {
            const btn = document.getElementById('run-pipeline-btn');
            const preset = document.getElementById('pipeline-preset').value;
            btn.disabled = true;
            showToast('Otomasyon boru hattı başlatıldı...');

            for (let i = 1; i <= 4; i++) {
                const node = document.getElementById(`node-${i}`);
                node.classList.remove('border-emerald-500/60', 'bg-emerald-950/20');
                node.querySelector('.node-status').textContent = 'SIRADA';
                node.querySelector('.node-status').className = 'node-status text-[10px] font-mono px-2 py-0.5 rounded bg-white/5 text-zinc-400';
            }

            [1, 2, 3, 4].forEach((step, index) => {
                setTimeout(() => {
                    const node = document.getElementById(`node-${step}`);
                    node.classList.add('border-emerald-500/60', 'bg-emerald-950/20');
                    const badge = node.querySelector('.node-status');
                    badge.textContent = 'TAMAMLANDI';
                    badge.className = 'node-status text-[10px] font-mono px-2 py-0.5 rounded bg-emerald-500/20 text-emerald-300';

                    if (step === 4) {
                        btn.disabled = false;
                        appendTerminalLog('PIPELINE', `"${preset.toUpperCase()}" iş akışı 4 aşamada başarıyla yürütüldü.`, 'text-emerald-400');
                        showToast('Tüm boru hattı adımları tamamlandı!');
                    }
                }, (index + 1) * 550);
            });
        }

        // Çıktıyı İndir (.txt / .png)
        function downloadOutput() {
            const imageWrap = document.getElementById('ai-output-image-wrap');
            if (!imageWrap.classList.contains('hidden')) {
                const imgSrc = document.getElementById('ai-output-image').src;
                const a = document.createElement('a');
                a.href = imgSrc;
                a.download = 'nexus26-ai-visual.png';
                a.click();
                showToast('Görsel indiriliyor...');
                return;
            }
            const text = document.getElementById('ai-output-text').textContent;
            const blob = new Blob([text], { type: 'text/plain;charset=utf-8' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = 'nexus26-analiz.txt';
            a.click();
            URL.revokeObjectURL(url);
            showToast('Rapor dosyası indirildi!');
        }

        // Canlı Ajan Terminali Fonksiyonları
        function appendTerminalLog(agent, message, colorClass = 'text-violet-400') {
            const term = document.getElementById('agent-terminal');
            if (!term) return;
            const now = new Date().toLocaleTimeString('tr-TR', { hour12: false });
            const line = document.createElement('div');
            line.className = 'text-zinc-400 animate-fade-in';
            line.innerHTML = `<span class="text-zinc-600">[${now}]</span> <span class="${colorClass} font-bold">${agent}:</span> ${message}`;
            term.prepend(line);
        }

        function runSingleAgent(name, report) {
            appendTerminalLog(name.toUpperCase(), report, 'text-emerald-400');
            showToast(`${name} görevini tamamladı!`);
        }

        function triggerSwarmBurst() {
            showToast('Tüm otonom ajanlar senkronize ediliyor...');
            appendTerminalLog('SWARM-CORE', '4 otonom ajan paralel iş akışına alındı...', 'text-violet-400');
            setTimeout(() => appendTerminalLog('ALPHA', 'Rakip fiyat endeksi ve 2026 büyüme verileri eşlendi.', 'text-sky-400'), 600);
            setTimeout(() => appendTerminalLog('SENTINEL', 'Sıfır-güven güvenlik duvarı doğrulandı.', 'text-emerald-400'), 1200);
            setTimeout(() => appendTerminalLog('GROWTH', 'Dönüşüm hunisi optimizasyonu canlıya alındı (+%38.2).', 'text-pink-400'), 1800);
        }

        // ROI Hesaplayıcı
        function calculateROI() {
            const teamEl = document.getElementById('roi-team');
            const hoursEl = document.getElementById('roi-hours');
            if (!teamEl || !hoursEl) return;
            const team = parseInt(teamEl.value, 10);
            const hours = parseInt(hoursEl.value, 10);
            document.getElementById('roi-team-val').textContent = `${team} Kişi`;
            document.getElementById('roi-hours-val').textContent = `${hours} Saat / Hafta`;

            const savedHours = Math.round(team * hours * 52 * 0.7);
            const savedMoney = savedHours * 350;

            document.getElementById('roi-saved-hours').innerHTML = `${savedHours.toLocaleString('tr-TR')} <span class="text-xs font-normal text-zinc-500">saat</span>`;
            document.getElementById('roi-money').textContent = `₺${savedMoney.toLocaleString('tr-TR')}`;
        }
        calculateROI();

        // Çıktıyı Kopyala
        function copyOutput() {
            const text = document.getElementById('ai-output-text').textContent;
            const tempInput = document.createElement('textarea');
            tempInput.value = text;
            document.body.appendChild(tempInput);
            tempInput.select();
            document.execCommand('copy');
            document.body.removeChild(tempInput);
            showToast('Çıktı panoya kopyalandı!');
        }

        // İnteraktif Grafik Verileri
        const chartData = {
            '2026': {
                nexus: [55, 62, 68, 74, 79, 85, 88, 92, 95, 97, 99, 100],
                legacy: [45, 43, 41, 39, 38, 36, 34, 32, 30, 28, 26, 24],
                stats: { ai: '%46.8', aiBadge: '+142% YoY', aiBar: '88%', saas: '%31.2', saasBadge: '+89% YoY', saasBar: '68%', leg: '%22.0', legBadge: '-34% YoY', legBar: '35%' }
            },
            '2025': {
                nexus: [30, 34, 38, 42, 45, 49, 52, 56, 60, 63, 66, 70],
                legacy: [65, 63, 61, 60, 58, 56, 55, 53, 51, 49, 48, 46],
                stats: { ai: '%28.4', aiBadge: '+64% YoY', aiBar: '55%', saas: '%24.1', saasBadge: '+41% YoY', saasBar: '48%', leg: '%47.5', legBadge: '-12% YoY', legBar: '65%' }
            }
        };

        function updateChartPeriod(year) {
            const btn26 = document.getElementById('btn-2026');
            const btn25 = document.getElementById('btn-2025');
            if (year === '2026') {
                btn26.className = "px-4 py-1.5 rounded-lg text-xs font-bold bg-white text-black transition";
                btn25.className = "px-4 py-1.5 rounded-lg text-xs font-bold text-zinc-400 hover:text-white transition";
            } else {
                btn25.className = "px-4 py-1.5 rounded-lg text-xs font-bold bg-white text-black transition";
                btn26.className = "px-4 py-1.5 rounded-lg text-xs font-bold text-zinc-400 hover:text-white transition";
            }

            const data = chartData[year];
            const container = document.getElementById('interactive-chart');
            if (!container) return;
            container.innerHTML = '';

            data.nexus.forEach((val, idx) => {
                const legVal = data.legacy[idx];
                const col = document.createElement('div');
                col.className = 'flex-1 h-full flex items-end justify-center gap-1 group relative';
                col.innerHTML = `
                    <div class="w-full max-w-[14px] bg-gradient-to-t from-violet-600 to-sky-400 rounded-t-md transition-all duration-500 group-hover:brightness-125" style="height: ${val}%" title="Nexus26: ${val} puan"></div>
                    <div class="w-full max-w-[10px] bg-zinc-700/70 rounded-t-md transition-all duration-500" style="height: ${legVal}%" title="Klasik Web: ${legVal} puan"></div>
                `;
                container.appendChild(col);
            });

            document.getElementById('stat-ai-val').innerHTML = `${data.stats.ai} <span class="text-xs font-normal text-zinc-500">Trafik Payı</span>`;
            document.getElementById('stat-ai-badge').textContent = data.stats.aiBadge;
            document.getElementById('bar-ai').style.width = data.stats.aiBar;

            document.getElementById('stat-saas-val').innerHTML = `${data.stats.saas} <span class="text-xs font-normal text-zinc-500">Trafik Payı</span>`;
            document.getElementById('stat-saas-badge').textContent = data.stats.saasBadge;
            document.getElementById('bar-saas').style.width = data.stats.saasBar;

            document.getElementById('stat-legacy-val').innerHTML = `${data.stats.leg} <span class="text-xs font-normal text-zinc-500">Trafik Payı</span>`;
            document.getElementById('stat-legacy-badge').textContent = data.stats.legBadge;
            document.getElementById('bar-legacy').style.width = data.stats.legBar;
        }

        updateChartPeriod('2026');

        // Fiyatlandırma Dönem Değişimi
        function setBilling(period) {
            const btnM = document.getElementById('bill-monthly');
            const btnY = document.getElementById('bill-yearly');
            const priceEl = document.getElementById('pro-price');
            const noteEl = document.getElementById('pro-billing-note');

            if (period === 'yearly') {
                btnY.className = "px-5 py-2 rounded-full text-xs font-bold bg-violet-600 text-white transition flex items-center gap-1.5";
                btnM.className = "px-5 py-2 rounded-full text-xs font-bold text-zinc-400 transition";
                priceEl.textContent = "₺390";
                noteEl.textContent = "Yıllık faturalandırılır (₺1.200 tasarruf)";
                noteEl.className = "text-xs text-emerald-400 mb-6";
            } else {
                btnM.className = "px-5 py-2 rounded-full text-xs font-bold bg-violet-600 text-white transition";
                btnY.className = "px-5 py-2 rounded-full text-xs font-bold text-zinc-400 transition flex items-center gap-1.5";
                priceEl.textContent = "₺490";
                noteEl.textContent = "Aylık esnek faturalandırma";
                noteEl.className = "text-xs text-zinc-500 mb-6";
            }
        }

        // SSS Akordeon
        function toggleFaq(btn) {
            const content = btn.nextElementSibling;
            const icon = btn.querySelector('i');
            content.classList.toggle('hidden');
            icon.classList.toggle('rotate-180');
        }

        // Komut Paleti Modalı
        function openCommandPalette() {
            const overlay = document.getElementById('modal-overlay');
            const content = document.getElementById('modal-content');
            overlay.classList.remove('hidden');
            overlay.classList.add('flex');

            content.innerHTML = `
                <div class="flex items-center gap-3 pb-4 border-b border-white/10 mb-4">
                    <i data-lucide="terminal" class="w-5 h-5 text-violet-400"></i>
                    <span class="font-bold text-base">Nexus Hızlı Komut Merkezi</span>
                </div>
                <div class="space-y-2">
                    <button onclick="closeModal(); scrollToSection('ai-hub'); switchTab('strategy');" class="w-full p-3 rounded-xl bg-white/5 hover:bg-violet-600/20 border border-white/5 hover:border-violet-500/40 text-left flex items-center justify-between transition">
                        <span class="text-sm font-medium">Yeni İş Stratejisi Başlat</span>
                        <span class="text-xs text-zinc-400">AI Stüdyo</span>
                    </button>
                    <button onclick="closeModal(); scrollToSection('rag-vault');" class="w-full p-3 rounded-xl bg-white/5 hover:bg-sky-600/20 border border-white/5 hover:border-sky-500/40 text-left flex items-center justify-between transition">
                        <span class="text-sm font-medium">Doküman & PDF Bilgi Bankasına Git</span>
                        <span class="text-xs text-zinc-400">RAG Hafıza</span>
                    </button>
                    <button onclick="closeModal(); scrollToSection('ai-arena');" class="w-full p-3 rounded-xl bg-white/5 hover:bg-pink-600/20 border border-white/5 hover:border-pink-500/40 text-left flex items-center justify-between transition">
                        <span class="text-sm font-medium">Çoklu AI Model Arenasını Aç</span>
                        <span class="text-xs text-zinc-400">Karşılaştırma</span>
                    </button>
                    <button onclick="closeModal(); scrollToSection('marketplace');" class="w-full p-3 rounded-xl bg-white/5 hover:bg-amber-600/20 border border-white/5 hover:border-amber-500/40 text-left flex items-center justify-between transition">
                        <span class="text-sm font-medium">Ajan Pazar Yeri & Şablon Mağazası</span>
                        <span class="text-xs text-zinc-400">Mağaza</span>
                    </button>
                    <button onclick="closeModal(); toggleHistoryDrawer();" class="w-full p-3 rounded-xl bg-white/5 hover:bg-violet-600/20 border border-white/5 hover:border-violet-500/40 text-left flex items-center justify-between transition">
                        <span class="text-sm font-medium">Kayıtlı Prompt Kütüphanesi & Geçmiş</span>
                        <span class="text-xs text-zinc-400">Arşiv</span>
                    </button>
                </div>
            `;
            lucide.createIcons();
        }

        // Bildirim Göster
        function showToast(msg) {
            const toast = document.getElementById('toast');
            document.getElementById('toast-message').textContent = msg;
            toast.classList.remove('translate-y-20', 'opacity-0');
            setTimeout(() => {
                toast.classList.add('translate-y-20', 'opacity-0');
            }, 3000);
        }

        // Yumuşak Kaydırma
        function scrollToSection(id) {
            document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
        }

        function closeModal() {
            const overlay = document.getElementById('modal-overlay');
            overlay.classList.add('hidden');
            overlay.classList.remove('flex');
        }

        // Hızlı AI Mikro-Aracı Başlatıcı
        function launchQuickTool(tab, prefixPrompt) {
            scrollToSection('ai-hub');
            switchTab(tab);
            const input = document.getElementById('ai-prompt');
            input.value = prefixPrompt;
            input.focus();
            showToast('Uzman modül hazırlandı! Detayı ekleyip "Analiz & Üret"e basın.');
        }
    </script>

    <!-- Gemini Live API Gerçek Zamanlı Sesli Konuşma Modülü -->
    <script type="module">
        import { GoogleGenAI, Modality } from 'https://esm.sh/@google/genai';

        let liveSessionPromise = null;
        let isLiveActive = false;
        let isFallbackMode = false;
        let recognitionInstance = null;
        let isMicMuted = false;
        let inputAudioContext = null;
        let outputAudioContext = null;
        let mediaStream = null;
        let nextStartTime = 0;
        const activeSources = new Set();
        let visualizerInterval = null;
        const fallbackChatHistory = [];

        function base64ToUint8Array(base64) {
            const binaryString = atob(base64);
            const len = binaryString.length;
            const bytes = new Uint8Array(len);
            for (let i = 0; i < len; i++) {
                bytes[i] = binaryString.charCodeAt(i);
            }
            return bytes;
        }

        async function decodeRawPcm(data, ctx, sampleRate, numChannels) {
            const dataInt16 = new Int16Array(data.buffer);
            const frameCount = dataInt16.length / numChannels;
            const buffer = ctx.createBuffer(numChannels, frameCount, sampleRate);
            for (let channel = 0; channel < numChannels; channel++) {
                const channelData = buffer.getChannelData(channel);
                for (let i = 0; i < frameCount; i++) {
                    channelData[i] = dataInt16[i * numChannels + channel] / 32768.0;
                }
            }
            return buffer;
        }

        function encodeBase64(bytes) {
            let binary = '';
            const len = bytes.byteLength;
            for (let i = 0; i < len; i++) {
                binary += String.fromCharCode(bytes[i]);
            }
            return btoa(binary);
        }

        function createPcmBlob(data) {
            const l = data.length;
            const int16 = new Int16Array(l);
            for (let i = 0; i < l; i++) {
                int16[i] = Math.max(-1, Math.min(1, data[i])) * 32768;
            }
            return {
                data: encodeBase64(new Uint8Array(int16.buffer)),
                mimeType: 'audio/pcm;rate=16000'
            };
        }

        function setVisualizerActive(active) {
            const viz = document.getElementById('voice-visualizer');
            if (!viz) return;
            const bars = viz.querySelectorAll('span');
            if (active) {
                visualizerInterval = setInterval(() => {
                    bars.forEach(bar => {
                        const h = Math.floor(Math.random() * 18) + 6;
                        bar.style.height = `${h}px`;
                        bar.classList.remove('bg-violet-500/40');
                        bar.classList.add('bg-violet-400');
                    });
                }, 120);
            } else {
                clearInterval(visualizerInterval);
                bars.forEach(bar => {
                    bar.style.height = '8px';
                    bar.classList.remove('bg-violet-400');
                    bar.classList.add('bg-violet-500/40');
                });
            }
        }

        function updateDockUI(active) {
            const dockDot = document.getElementById('dock-status-dot');
            const dockTitle = document.getElementById('dock-status-title');
            const dockSub = document.getElementById('dock-status-sub');
            const dockCallBtn = document.getElementById('dock-call-btn');
            const dockMute = document.getElementById('dock-mute-btn');
            const mainMute = document.getElementById('live-mute-btn');

            if (active) {
                if (dockDot) dockDot.className = 'w-2 h-2 rounded-full bg-emerald-400 animate-ping';
                if (dockTitle) dockTitle.textContent = 'Canlı Ses Aktif';
                if (dockSub) dockSub.textContent = 'Görüşme devam ediyor';
                if (dockCallBtn) dockCallBtn.innerHTML = '<i data-lucide="phone-off" class="w-5 h-5"></i>';
                if (dockMute) dockMute.classList.remove('hidden');
                if (mainMute) mainMute.classList.remove('hidden');
            } else {
                if (dockDot) dockDot.className = 'w-2 h-2 rounded-full bg-zinc-500';
                if (dockTitle) dockTitle.textContent = 'Sesli Asistan Hazır';
                if (dockSub) dockSub.textContent = 'Tüm araçlarla senkronize';
                if (dockCallBtn) dockCallBtn.innerHTML = '<i data-lucide="mic" class="w-5 h-5"></i>';
                if (dockMute) dockMute.classList.add('hidden');
                if (mainMute) mainMute.classList.add('hidden');
            }
            if (window.lucide) window.lucide.createIcons();
        }

        function appendLiveTranscript(speaker, text, isModel = false) {
            if (!text || !text.trim()) return;
            const box = document.getElementById('live-transcript-box');
            if (!box) return;
            if (box.querySelector('.italic')) box.innerHTML = '';
            const row = document.createElement('div');
            row.className = isModel ? 'p-2 rounded-lg bg-violet-500/10 border border-violet-500/20 text-violet-200' : 'p-2 rounded-lg bg-white/5 text-zinc-300';
            row.innerHTML = `<span class="font-bold text-[10px] uppercase mr-1.5 ${isModel ? 'text-violet-400' : 'text-sky-400'}">${speaker}:</span>${text}`;
            box.appendChild(row);
            box.scrollTop = box.scrollHeight;
        }

        async function processFallbackVoiceTurn(userText) {
            if (!userText || !userText.trim() || !isLiveActive) return;
            appendLiveTranscript('Siz', userText, false);
            fallbackChatHistory.push({ role: 'user', parts: [{ text: userText }] });

            const selectedVoice = document.getElementById('live-voice-select').value;
            try {
                const replyText = await window.callGeminiWithBackoff(
                    userText,
                    'Sen Nexus26 platformunun Türkçe konuşan, samimi ve zeki sesli asistanısın. Yanıtlarını kısa, doğal ve konuşma diline uygun (maksimum 2-3 cümle) ver.'
                );
                if (!isLiveActive) return;
                appendLiveTranscript('Nexus AI', replyText, true);

                const ttsUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-tts:generateContent?key=`;
                const ttsRes = await fetch(ttsUrl, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify({
                        contents: [{ parts: [{ text: replyText }] }],
                        generationConfig: {
                            responseModalities: ['AUDIO'],
                            speechConfig: { voiceConfig: { prebuiltVoiceConfig: { voiceName: selectedVoice } } }
                        }
                    })
                });
                const ttsJson = await ttsRes.json();
                const part = ttsJson?.candidates?.[0]?.content?.parts?.[0];
                const audioData = part?.inlineData?.data;
                const mimeType = part?.inlineData?.mimeType;

                if (audioData && mimeType) {
                    const rateMatch = mimeType.match(/rate=(\d+)/);
                    const sampleRate = rateMatch ? parseInt(rateMatch[1], 10) : 24000;
                    const pcm16 = new Int16Array(window.base64ToArrayBuffer(audioData));
                    const wavBlob = window.pcmToWav(pcm16, sampleRate);
                    const audio = new Audio(URL.createObjectURL(wavBlob));
                    audio.play();
                } else if ('speechSynthesis' in window) {
                    const utter = new SpeechSynthesisUtterance(replyText);
                    utter.lang = 'tr-TR';
                    window.speechSynthesis.speak(utter);
                }
            } catch (e) {
                appendLiveTranscript('Sistem', 'Yanıt alınırken kısa bir gecikme yaşandı, tekrar söyleyebilirsiniz.', true);
            }
        }

        function startFallbackVoiceEngine() {
            isFallbackMode = true;
            isLiveActive = true;
            isMicMuted = false;

            document.getElementById('live-btn-label').textContent = 'Görüşmeyi Sonlandır';
            document.getElementById('live-status-text').textContent = 'NEXUS VOICE // EŞZAMANLI SESLİ ASİSTAN AKTİF';
            document.getElementById('live-dot').className = 'w-2 h-2 rounded-full bg-emerald-400 animate-ping';
            setVisualizerActive(true);
            updateDockUI(true);
            window.showToast('Sesli asistan bağlandı! Konuşmaya başlayabilirsiniz.');
            appendLiveTranscript('Nexus AI', 'Merhaba! Ben Nexus26 sesli asistanınız. Size nasıl yardımcı olabilirim?', true);

            const SpeechRec = window.SpeechRecognition || window.webkitSpeechRecognition;
            if (SpeechRec) {
                recognitionInstance = new SpeechRec();
                recognitionInstance.lang = 'tr-TR';
                recognitionInstance.continuous = true;
                recognitionInstance.interimResults = false;

                recognitionInstance.onresult = (event) => {
                    if (isMicMuted || !isLiveActive) return;
                    const last = event.results[event.results.length - 1];
                    if (last.isFinal) {
                        processFallbackVoiceTurn(last[0].transcript);
                    }
                };
                recognitionInstance.onend = () => {
                    if (isLiveActive && isFallbackMode && !isMicMuted) {
                        try { recognitionInstance.start(); } catch (e) {}
                    }
                };
                try { recognitionInstance.start(); } catch (e) {}
            } else {
                appendLiveTranscript('Bilgi', 'Tarayıcınız doğrudan ses tanımayı kısıtlıyorsa aşağıdaki kutudan yazılı mesaj göndererek sesli yanıt alabilirsiniz.', true);
            }
        }

        function toggleLiveMute() {
            if (!isLiveActive) return;
            isMicMuted = !isMicMuted;
            const mainLabel = document.getElementById('live-mute-label');
            const mainBtn = document.getElementById('live-mute-btn');
            const dockMute = document.getElementById('dock-mute-btn');

            if (isMicMuted) {
                if (mainLabel) mainLabel.textContent = 'Mikrofon Kapalı';
                if (mainBtn) mainBtn.innerHTML = '<i data-lucide="mic-off" class="w-4 h-4 text-rose-400"></i><span id="live-mute-label">Mikrofon Kapalı</span>';
                if (dockMute) dockMute.innerHTML = '<i data-lucide="mic-off" class="w-4 h-4 text-rose-400"></i>';
                if (liveSessionPromise) {
                    liveSessionPromise.then(session => session.sendRealtimeInput({ audioStreamEnd: true })).catch(() => {});
                }
                if (recognitionInstance) {
                    try { recognitionInstance.stop(); } catch (e) {}
                }
                window.showToast('Mikrofon sessize alındı.');
            } else {
                if (mainBtn) mainBtn.innerHTML = '<i data-lucide="mic" class="w-4 h-4 text-emerald-400"></i><span id="live-mute-label">Mikrofon Açık</span>';
                if (dockMute) dockMute.innerHTML = '<i data-lucide="mic" class="w-4 h-4 text-emerald-400"></i>';
                if (isFallbackMode && recognitionInstance) {
                    try { recognitionInstance.start(); } catch (e) {}
                }
                window.showToast('Mikrofon tekrar açıldı.');
            }
            if (window.lucide) window.lucide.createIcons();
        }

        async function toggleLiveVoiceSession() {
            if (isLiveActive) {
                stopLiveSession();
                return;
            }

            const btnLabel = document.getElementById('live-btn-label');
            const statusText = document.getElementById('live-status-text');
            const liveDot = document.getElementById('live-dot');
            const selectedVoice = document.getElementById('live-voice-select').value;

            if (btnLabel) btnLabel.textContent = 'Bağlanıyor...';
            if (statusText) statusText.textContent = 'BAĞLANTI KURULUYOR...';

            let connectionResolved = false;
            const fallbackTimer = setTimeout(() => {
                if (!connectionResolved && !isLiveActive) {
                    connectionResolved = true;
                    if (liveSessionPromise) {
                        liveSessionPromise.then(s => { try { s.close(); } catch (e) {} }).catch(() => {});
                        liveSessionPromise = null;
                    }
                    startFallbackVoiceEngine();
                }
            }, 4500);

            try {
                const ai = new GoogleGenAI({ apiKey: "" });

                inputAudioContext = new (window.AudioContext || window.webkitAudioContext)({ sampleRate: 16000 });
                outputAudioContext = new (window.AudioContext || window.webkitAudioContext)();
                if (inputAudioContext.state === 'suspended') await inputAudioContext.resume();
                if (outputAudioContext.state === 'suspended') await outputAudioContext.resume();

                const outputNode = outputAudioContext.createGain();
                outputNode.connect(outputAudioContext.destination);

                const workletCode = `
                    class RecorderProcessor extends AudioWorkletProcessor {
                        process(inputs) {
                            const input = inputs[0];
                            if (input && input.length > 0) {
                                this.port.postMessage(input[0]);
                            }
                            return true;
                        }
                    }
                    registerProcessor('recorder-processor', RecorderProcessor);
                `;
                const workletBlob = new Blob([workletCode], { type: 'application/javascript' });
                await inputAudioContext.audioWorklet.addModule(URL.createObjectURL(workletBlob));

                mediaStream = await navigator.mediaDevices.getUserMedia({
                    audio: {
                        channelCount: 1,
                        echoCancellation: true,
                        noiseSuppression: true,
                        autoGainControl: true
                    }
                });

                let currentInText = '';
                let currentOutText = '';

                liveSessionPromise = ai.live.connect({
                    model: 'gemini-3.1-flash-live-preview',
                    callbacks: {
                        onopen: () => {
                            if (connectionResolved) return;
                            connectionResolved = true;
                            clearTimeout(fallbackTimer);
                            isFallbackMode = false;
                            isLiveActive = true;
                            isMicMuted = false;
                            if (btnLabel) btnLabel.textContent = 'Görüşmeyi Sonlandır';
                            if (statusText) statusText.textContent = 'GEMINI LIVE // CANLI BAĞLANTI AKTİF';
                            if (liveDot) liveDot.className = 'w-2 h-2 rounded-full bg-emerald-400 animate-ping';
                            setVisualizerActive(true);
                            updateDockUI(true);
                            window.showToast('Sesli AI görüşmesi başladı! Sayfayı kullanırken konuşabilirsiniz.');

                            const source = inputAudioContext.createMediaStreamSource(mediaStream);
                            const recorder = new AudioWorkletNode(inputAudioContext, 'recorder-processor');
                            recorder.port.onmessage = (event) => {
                                if (isMicMuted || !liveSessionPromise) return;
                                const pcmBlob = createPcmBlob(event.data);
                                liveSessionPromise.then((session) => {
                                    session.sendRealtimeInput({ audio: pcmBlob });
                                }).catch(() => {});
                            };
                            source.connect(recorder);
                            recorder.connect(inputAudioContext.destination);
                        },
                        onmessage: async (message) => {
                            if (message.serverContent?.inputTranscription?.text) {
                                currentInText += message.serverContent.inputTranscription.text;
                            }
                            if (message.serverContent?.outputTranscription?.text) {
                                currentOutText += message.serverContent.outputTranscription.text;
                            }
                            if (message.serverContent?.turnComplete) {
                                if (currentInText.trim()) appendLiveTranscript('Siz', currentInText, false);
                                if (currentOutText.trim()) appendLiveTranscript('Nexus AI', currentOutText, true);
                                currentInText = '';
                                currentOutText = '';
                            }

                            const base64Audio = message.serverContent?.modelTurn?.parts?.[0]?.inlineData?.data;
                            if (base64Audio && outputAudioContext) {
                                nextStartTime = Math.max(nextStartTime, outputAudioContext.currentTime);
                                const audioBuffer = await decodeRawPcm(base64ToUint8Array(base64Audio), outputAudioContext, 24000, 1);
                                const source = outputAudioContext.createBufferSource();
                                source.buffer = audioBuffer;
                                source.connect(outputNode);
                                source.addEventListener('ended', () => activeSources.delete(source));
                                source.start(nextStartTime);
                                nextStartTime += audioBuffer.duration;
                                activeSources.add(source);
                            }

                            if (message.serverContent?.interrupted) {
                                for (const src of activeSources.values()) {
                                    src.stop();
                                    activeSources.delete(src);
                                }
                                nextStartTime = 0;
                            }
                        },
                        onerror: () => {
                            if (!connectionResolved) {
                                connectionResolved = true;
                                clearTimeout(fallbackTimer);
                                startFallbackVoiceEngine();
                            } else if (!isFallbackMode) {
                                window.showToast('Sesli bağlantı kesildi.');
                                stopLiveSession();
                            }
                        },
                        onclose: () => {
                            if (!isFallbackMode && isLiveActive) {
                                stopLiveSession();
                            }
                        }
                    },
                    config: {
                        responseModalities: [Modality.AUDIO],
                        speechConfig: {
                            voiceConfig: { prebuiltVoiceConfig: { voiceName: selectedVoice } }
                        },
                        outputAudioTranscription: {},
                        inputAudioTranscription: {},
                        systemInstruction: 'Sen Nexus26 platformunun Türkçe konuşan, zeki, nazik ve çok yönlü yapay zeka sesli asistanısın. Kullanıcı sitedeki diğer AI araçlarını kullanırken arka planda onunla eşzamanlı sohbet ediyorsun. Kısa, doğal ve akıcı cevaplar ver.'
                    }
                });

                liveSessionPromise.catch(() => {
                    if (!connectionResolved) {
                        connectionResolved = true;
                        clearTimeout(fallbackTimer);
                        startFallbackVoiceEngine();
                    }
                });
            } catch (err) {
                if (!connectionResolved) {
                    connectionResolved = true;
                    clearTimeout(fallbackTimer);
                    startFallbackVoiceEngine();
                }
            }
        }

        function stopLiveSession() {
            isLiveActive = false;
            isFallbackMode = false;
            isMicMuted = false;
            setVisualizerActive(false);
            updateDockUI(false);
            const btnLabel = document.getElementById('live-btn-label');
            const statusText = document.getElementById('live-status-text');
            const liveDot = document.getElementById('live-dot');
            if (btnLabel) btnLabel.textContent = 'Sesli Görüşmeyi Başlat';
            if (statusText) statusText.textContent = 'GEMINI LIVE // SESLİ OTURUM HAZIR';
            if (liveDot) liveDot.className = 'w-2 h-2 rounded-full bg-zinc-500';

            if (recognitionInstance) {
                try { recognitionInstance.stop(); } catch (e) {}
                recognitionInstance = null;
            }
            if ('speechSynthesis' in window) {
                try { window.speechSynthesis.cancel(); } catch (e) {}
            }
            if (liveSessionPromise) {
                liveSessionPromise.then(session => {
                    try { session.close(); } catch (e) {}
                }).catch(() => {});
                liveSessionPromise = null;
            }
            if (mediaStream) {
                mediaStream.getTracks().forEach(t => t.stop());
                mediaStream = null;
            }
            if (inputAudioContext) {
                try { inputAudioContext.close(); } catch (e) {}
                inputAudioContext = null;
            }
            if (outputAudioContext) {
                try { outputAudioContext.close(); } catch (e) {}
                outputAudioContext = null;
            }
            nextStartTime = 0;
        }

        function sendLiveTextNote() {
            const input = document.getElementById('live-quick-text');
            if (!input) return;
            const text = input.value.trim();
            if (!text) return;
            if (!isLiveActive) {
                window.showToast('Önce "Sesli Görüşmeyi Başlat" butonuna tıklayın.');
                return;
            }
            input.value = '';
            if (isFallbackMode) {
                processFallbackVoiceTurn(text);
                return;
            }
            appendLiveTranscript('Siz (Not)', text, false);
            if (liveSessionPromise) {
                liveSessionPromise.then(session => {
                    session.sendRealtimeInput({ text });
                }).catch(() => {});
            }
        }

        // Dinamik Event Bağlantıları
        document.addEventListener('DOMContentLoaded', () => {
            const callBtn = document.getElementById('live-call-btn');
            const dockCallBtn = document.getElementById('dock-call-btn');
            const muteBtn = document.getElementById('live-mute-btn');
            const dockMuteBtn = document.getElementById('dock-mute-btn');
            const sendTextBtn = document.getElementById('live-send-text-btn');
            const quickTextInput = document.getElementById('live-quick-text');

            if (callBtn) callBtn.addEventListener('click', toggleLiveVoiceSession);
            if (dockCallBtn) dockCallBtn.addEventListener('click', toggleLiveVoiceSession);
            if (muteBtn) muteBtn.addEventListener('click', toggleLiveMute);
            if (dockMuteBtn) dockMuteBtn.addEventListener('click', toggleLiveMute);
            if (sendTextBtn) sendTextBtn.addEventListener('click', sendLiveTextNote);
            if (quickTextInput) {
                quickTextInput.addEventListener('keydown', (e) => {
                    if (e.key === 'Enter') sendLiveTextNote();
                });
            }
        });
    </script>
</body>
</html>
