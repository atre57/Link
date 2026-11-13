<html lang="tr" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <!-- Cihaz Optimizasyonlu Viewport (iOS, Android, Tablet ve PC için otomatik ölçeklendirme) -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0, user-scalable=yes">
    <title>NexusAI 2026 | Geleceğin Dijital Çalışma Alanı (Auto-Device Responsive)</title>
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
            -webkit-tap-highlight-color: transparent;
        }
        h1, h2, h3, .font-display {
            font-family: 'Plus Jakarta Sans', sans-serif;
        }
        .glass {
            background: rgba(18, 18, 22, 0.78);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 255, 255, 0.08);
        }
        /* Fare takipli parıltı efekti */
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
        /* Cihaz Önizleme Modu İçin Çerçeve Sınıfları */
        .device-frame-iphone {
            max-width: 390px;
            margin: 0 auto;
            border: 12px solid #27272a;
            border-radius: 40px;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.9);
        }
        .device-frame-ipad {
            max-width: 768px;
            margin: 0 auto;
            border: 14px solid #27272a;
            border-radius: 32px;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.9);
        }
        .device-frame-android {
            max-width: 412px;
            margin: 0 auto;
            border: 10px solid #18181b;
            border-radius: 36px;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.9);
        }
        /* Özel Kaydırma Çubuğu */
        ::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #050507;
        }
        ::-webkit-scrollbar-thumb {
            background: #27272a;
            border-radius: 3px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #3f3f46;
        }
    </style>
</head>
<body id="main-body" class="selection:bg-violet-500/30 selection:text-violet-200 relative">

    <!-- Izgara Arka Plan ve Işık Efektleri -->
    <div class="fixed inset-0 grid-pattern pointer-events-none z-[-2]"></div>
    <div class="glow-bg top-[-150px] left-[-100px]"></div>
    <div class="glow-bg top-[35%] right-[-150px]" style="background: radial-gradient(circle, rgba(56, 189, 248, 0.1) 0%, rgba(0,0,0,0) 70%);"></div>

    <!-- Cihaz Algılama ve Otomatik Ekran Boyutlandırma Üst Çubuğu -->
    <div class="bg-zinc-950/90 border-b border-white/10 px-4 py-2 text-xs flex flex-wrap items-center justify-between gap-3 sticky top-0 z-50 backdrop-blur-md">
        <div class="flex items-center gap-2">
            <span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></span>
            <span id="detected-device-badge" class="font-mono text-zinc-300">Cihaz Algılanıyor...</span>
        </div>
        <div class="flex items-center gap-1.5 overflow-x-auto py-1">
            <span class="text-[11px] text-zinc-500 hidden sm:inline">Manuel Görünüm:</span>
            <button onclick="setDeviceView('auto')" id="mode-auto" class="px-2.5 py-1 rounded-lg bg-violet-600 text-white font-semibold transition cursor-pointer">Otomatik (Responsive)</button>
            <button onclick="setDeviceView('iphone')" id="mode-iphone" class="px-2.5 py-1 rounded-lg bg-white/5 hover:bg-white/10 text-zinc-300 transition cursor-pointer">iPhone</button>
            <button onclick="setDeviceView('android')" id="mode-android" class="px-2.5 py-1 rounded-lg bg-white/5 hover:bg-white/10 text-zinc-300 transition cursor-pointer">Android</button>
            <button onclick="setDeviceView('tablet')" id="mode-tablet" class="px-2.5 py-1 rounded-lg bg-white/5 hover:bg-white/10 text-zinc-300 transition cursor-pointer">Tablet / iPad</button>
            <button onclick="setDeviceView('pc')" id="mode-pc" class="px-2.5 py-1 rounded-lg bg-white/5 hover:bg-white/10 text-zinc-300 transition cursor-pointer">PC / Masaüstü</button>
        </div>
    </div>

    <!-- Navigasyon -->
    <nav class="sticky top-[41px] z-40 glass border-b border-white/5 px-4 py-3">
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
            <div class="hidden lg:flex items-center gap-4 text-xs font-medium text-zinc-400">
                <a href="#live-voice" class="text-violet-300 hover:text-white transition flex items-center gap-1.5"><span class="w-2 h-2 rounded-full bg-rose-500 animate-pulse"></span> Canlı Ses</a>
                <a href="#ai-hub" class="hover:text-white transition">AI Stüdyo</a>
                <a href="#rag-vault" class="hover:text-white transition">Bilgi Bankası</a>
                <a href="#ai-arena" class="hover:text-white transition">AI Arena</a>
                <a href="#marketplace" class="hover:text-white transition">Pazar Yeri</a>
                <a href="#affiliate-hub" class="hover:text-white transition">Ortaklık</a>
                <a href="#fiyatlandirma" class="hover:text-white transition">Planlar</a>
            </div>

            <div class="flex items-center gap-2">
                <button onclick="toggleHistoryDrawer()" class="px-2.5 py-2 rounded-xl bg-white/5 hover:bg-white/10 border border-white/10 text-zinc-300 text-xs font-semibold flex items-center gap-1.5 transition cursor-pointer" title="Kayıtlı Prompt & Oturum Geçmişi">
                    <i data-lucide="history" class="w-4 h-4 text-sky-400"></i>
                    <span class="hidden sm:inline">Geçmiş</span>
                    <span id="history-count" class="px-1.5 py-0.2 rounded-full bg-violet-600/30 text-violet-300 text-[10px] font-mono">0</span>
                </button>
                <button onclick="openCommandPalette()" class="hidden xl:flex items-center gap-2 px-3 py-1.5 rounded-xl bg-zinc-900/90 border border-white/10 text-xs text-zinc-400 hover:text-white hover:border-white/20 transition" title="Hızlı Komut Paleti">
                    <i data-lucide="search" class="w-3.5 h-3.5"></i>
                    <kbd class="px-1.5 py-0.5 text-[10px] font-mono bg-white/5 rounded text-zinc-400">⌘K</kbd>
                </button>
                <button onclick="toggleFloatingVoiceDock()" class="px-2.5 py-2 rounded-xl bg-violet-600/10 hover:bg-violet-600/20 border border-violet-500/30 text-violet-300 text-xs font-semibold flex items-center gap-1.5 transition cursor-pointer" title="Asistan Düğmesi">
                    <i data-lucide="mic" class="w-4 h-4 text-rose-400"></i> <span class="hidden sm:inline">Asistan</span>
                </button>
                <div id="nav-auth-area" class="flex items-center gap-2">
                    <button onclick="openModal('register')" class="text-xs font-medium text-zinc-300 hover:text-white px-2 py-2 transition cursor-pointer">Kayıt Ol</button>
                    <button onclick="openModal('login')" class="text-xs font-semibold text-violet-300 bg-violet-600/20 hover:bg-violet-600/30 border border-violet-500/30 px-3 py-2 rounded-xl transition cursor-pointer">Giriş Yap</button>
                </div>
            </div>
        </div>
    </nav>

    <!-- Ana Cihaz Çerçeveleyici Konteyner -->
    <div id="device-wrapper" class="w-full transition-all duration-300">

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
                <span>Otomatik Cihaz Ayarı: iOS, Android, Tablet & PC Uyumlu</span>
            </div>
            
            <h1 class="text-4xl sm:text-6xl md:text-7xl font-extrabold tracking-tight leading-[1.08] mb-6">
                Kurumsal Zekayı <span class="gradient-text">Otonom Hızla</span> Ölçeklendirin.
            </h1>
            
            <p class="text-zinc-400 text-sm sm:text-xl max-w-2xl mx-auto mb-10 leading-relaxed font-normal">
                2026'nın en yüksek trafikli yeni nesil çalışma platformu. Mobil, tablet ve masaüstü ekranlarınıza tam uyumlu akıllı arayüz mimarisi.
            </p>

            <div class="flex flex-col sm:flex-row items-center justify-center gap-4">
                <button onclick="scrollToSection('live-voice')" class="w-full sm:w-auto px-8 py-4 bg-gradient-to-r from-violet-600 to-indigo-600 hover:from-violet-500 hover:to-indigo-500 text-white font-bold rounded-2xl transition flex items-center justify-center gap-2.5 shadow-xl shadow-violet-600/25 cursor-pointer">
                    <i data-lucide="mic" class="w-5 h-5"></i>
                    Yapay Zeka ile Sesli Konuş
                </button>
                <button onclick="scrollToSection('ai-hub')" class="w-full sm:w-auto px-8 py-4 glass hover:bg-white/10 text-white font-semibold rounded-2xl transition flex items-center justify-center gap-2.5 cursor-pointer">
                    <i data-lucide="cpu" class="w-5 h-5 text-sky-400"></i>
                    Canlı AI Stüdyoyu Aç
                </button>
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
                            Telefonunuzdan, tabletinizden veya bilgisayarınızdan mikrofonu açın; tıpkı gerçek bir uzmanla konuşur gibi kesintisiz sohbet edin.
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
                        <button onclick="switchTab('strategy')" id="tab-strategy" class="tab-btn px-4 py-2 rounded-xl text-xs font-bold bg-violet-600 text-white transition cursor-pointer">Strateji</button>
                        <button onclick="switchTab('code')" id="tab-code" class="tab-btn px-4 py-2 rounded-xl text-xs font-bold text-zinc-400 hover:text-white transition cursor-pointer">Kod Mimarı</button>
                        <button onclick="switchTab('trend')" id="tab-trend" class="tab-btn px-4 py-2 rounded-xl text-xs font-bold text-zinc-400 hover:text-white transition cursor-pointer">Trend Analizi</button>
                        <button onclick="switchTab('image')" id="tab-image" class="tab-btn px-4 py-2 rounded-xl text-xs font-bold text-zinc-400 hover:text-white transition cursor-pointer">Görsel Üretici</button>
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

        <!-- DOKÜMAN & PDF BİLGİ BANKASI (RAG) -->
        <section id="rag-vault" class="py-12 px-4 max-w-7xl mx-auto">
            <div class="glass rounded-3xl p-8 border border-sky-500/25">
                <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 mb-8 pb-6 border-b border-white/10">
                    <div>
                        <span class="text-xs font-bold uppercase tracking-widest text-sky-400">Kurumsal Hafıza & Vektör İndeksleme (RAG)</span>
                        <h2 class="text-2xl sm:text-3xl font-extrabold mt-1">Doküman & PDF Bilgi Bankası</h2>
                        <p class="text-zinc-400 text-xs sm:text-sm mt-1">Şirket sözleşmelerinizi yükleyin; yapay zeka yalnızca sizin dokümanlarınızdan kaynak göstererek yanıt versin.</p>
                    </div>
                    <span id="rag-doc-count" class="px-3 py-1.5 rounded-xl bg-sky-500/10 border border-sky-500/20 text-sky-300 text-xs font-mono font-bold">2 Aktif Doküman</span>
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
                    <div class="space-y-4">
                        <label for="rag-file-input" class="block border-2 border-dashed border-sky-500/30 hover:border-sky-400 rounded-2xl p-6 text-center bg-zinc-950/70 hover:bg-sky-950/10 transition cursor-pointer">
                            <div class="w-11 h-11 rounded-xl bg-sky-500/15 text-sky-400 flex items-center justify-center mx-auto mb-3">
                                <i data-lucide="file-up" class="w-6 h-6"></i>
                            </div>
                            <p class="text-sm font-bold text-white">Doküman / TXT / MD / CSV Yükle</p>
                            <input type="file" id="rag-file-input" accept=".txt,.md,.csv,.json" class="hidden" onchange="handleRagFileUpload(event)">
                        </label>
                        <div class="bg-zinc-950/80 border border-white/10 rounded-2xl p-4 space-y-2.5">
                            <span class="text-xs font-bold text-zinc-300">İndekslenmiş Bilgi Kaynakları</span>
                            <div id="rag-files-list" class="space-y-2 max-h-48 overflow-y-auto pr-1"></div>
                        </div>
                    </div>

                    <div class="lg:col-span-2 bg-zinc-950/90 border border-white/10 rounded-2xl p-5 flex flex-col justify-between space-y-4">
                        <div class="flex items-center justify-between pb-3 border-b border-white/10">
                            <span class="text-xs font-mono text-sky-400 flex items-center gap-2">
                                <i data-lucide="database-zap" class="w-4 h-4"></i> KURUMSAL HAFIZA SORGULAMA MOTORU
                            </span>
                        </div>
                        <div id="rag-chat-box" class="h-56 overflow-y-auto space-y-3 text-xs pr-1">
                            <div class="p-3 rounded-xl bg-sky-500/10 border border-sky-500/20 text-sky-200">
                                <span class="font-bold text-sky-400 block mb-1">Bilgi Bankası Asistanı:</span>
                                Hafızada kayıtlı dokümanlar hakkında dilediğinizi sorabilirsiniz.
                            </div>
                        </div>
                        <div class="flex items-center gap-2 pt-2 border-t border-white/10">
                            <input id="rag-question-input" type="text" placeholder="Örn: Sözleşmedeki fesih süresi kaç gündür?" class="flex-1 bg-zinc-900 border border-white/10 rounded-xl px-4 py-3 text-xs text-white placeholder-zinc-500 focus:outline-none focus:border-sky-500" onkeydown="if(event.key==='Enter') askRagDocuments()">
                            <button onclick="askRagDocuments()" id="rag-ask-btn" class="px-5 py-3 rounded-xl bg-gradient-to-r from-sky-500 to-indigo-600 hover:opacity-95 text-white text-xs font-bold flex items-center gap-2 transition cursor-pointer">
                                Belgelerde Ara
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- ÇOKLU AI MODEL ARENASI -->
        <section id="ai-arena" class="py-12 px-4 max-w-7xl mx-auto">
            <div class="glass rounded-3xl p-8 border border-pink-500/25">
                <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 mb-8 pb-6 border-b border-white/10">
                    <div>
                        <span class="text-xs font-bold uppercase tracking-widest text-pink-400">Side-by-Side Karar Laboratuvarı</span>
                        <h2 class="text-2xl sm:text-3xl font-extrabold mt-1">Çoklu AI Model Karşılaştırma Arenası</h2>
                    </div>
                </div>
                <div class="flex flex-col sm:flex-row gap-3 mb-6">
                    <input id="arena-prompt-input" type="text" placeholder="Örn: Yeni çıkacak mobil uygulamamız için 30 günlük lansman planı öner..." class="flex-1 bg-zinc-950 border border-white/10 rounded-2xl px-4 py-3.5 text-sm text-white placeholder-zinc-500 focus:outline-none focus:border-pink-500">
                    <button onclick="runModelArena()" id="arena-run-btn" class="px-6 py-3.5 rounded-2xl bg-gradient-to-r from-pink-600 to-violet-600 hover:opacity-95 text-white font-bold text-xs flex items-center justify-center gap-2 transition cursor-pointer">
                        İki Uzmanı Yarıştır
                    </button>
                </div>
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
                    <div class="bg-zinc-950/90 border border-violet-500/25 rounded-2xl p-6 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between pb-3 mb-4 border-b border-white/10">
                                <span class="font-bold text-sm text-violet-300">MODEL A // Yaratıcı Vizyoner</span>
                            </div>
                            <div id="arena-output-a" class="text-xs sm:text-sm text-zinc-300 leading-relaxed whitespace-pre-wrap min-h-[140px]">Yanıt bekleniyor...</div>
                        </div>
                    </div>
                    <div class="bg-zinc-950/90 border border-sky-500/25 rounded-2xl p-6 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between pb-3 mb-4 border-b border-white/10">
                                <span class="font-bold text-sm text-sky-300">MODEL B // Veri & ROI Analisti</span>
                            </div>
                            <div id="arena-output-b" class="text-xs sm:text-sm text-zinc-300 leading-relaxed whitespace-pre-wrap min-h-[140px]">Yanıt bekleniyor...</div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- PAZAR YERİ & ORTAKLIK -->
        <section id="marketplace" class="py-12 px-4 max-w-7xl mx-auto">
            <div class="glass rounded-3xl p-8 border border-amber-500/25">
                <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 mb-8 pb-6 border-b border-white/10">
                    <div>
                        <span class="text-xs font-bold uppercase tracking-widest text-amber-400">Otonom Şablon Ekonomisi</span>
                        <h2 class="text-2xl sm:text-3xl font-extrabold mt-1">Ajan Pazar Yeri & Şablon Mağazası</h2>
                    </div>
                </div>
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-5">
                    <div class="bg-zinc-950/90 border border-white/10 rounded-2xl p-5 flex flex-col justify-between bento-card">
                        <div>
                            <div class="flex justify-between mb-3"><span class="text-[10px] font-mono text-emerald-300">E-TİCARET</span><span class="text-sm font-extrabold">₺450</span></div>
                            <h3 class="font-bold text-base mb-1.5">E-Ticaret SEO Botu</h3>
                            <p class="text-xs text-zinc-400">SEO uyumlu açıklamalar üretir.</p>
                        </div>
                        <button onclick="buyMarketplaceAgent('E-Ticaret SEO Botu', 450, 'SEO metni üret: ')" class="mt-5 w-full py-2.5 rounded-xl bg-amber-500/15 text-amber-300 text-xs font-bold cursor-pointer">Satın Al</button>
                    </div>
                    <div class="bg-zinc-950/90 border border-white/10 rounded-2xl p-5 flex flex-col justify-between bento-card">
                        <div>
                            <div class="flex justify-between mb-3"><span class="text-[10px] font-mono text-violet-300">HUKUK</span><span class="text-sm font-extrabold">₺790</span></div>
                            <h3 class="font-bold text-base mb-1.5">Hukuk Sözleşme Denetçisi</h3>
                            <p class="text-xs text-zinc-400">Riskli maddeleri tespit eder.</p>
                        </div>
                        <button onclick="buyMarketplaceAgent('Hukuk Sözleşme Denetçisi Pro', 790, 'Sözleşme risk analizi: ')" class="mt-5 w-full py-2.5 rounded-xl bg-amber-500/15 text-amber-300 text-xs font-bold cursor-pointer">Satın Al</button>
                    </div>
                </div>
            </div>
        </section>

        <!-- ORTAKLIK (AFFILIATE) -->
        <section id="affiliate-hub" class="py-12 px-4 max-w-7xl mx-auto">
            <div class="glass rounded-3xl p-8 border border-emerald-500/25">
                <div class="grid grid-cols-1 lg:grid-cols-3 gap-8 items-center">
                    <div class="lg:col-span-2 space-y-4">
                        <span class="text-xs font-bold uppercase tracking-widest text-emerald-400">Viral Büyüme & Gelir Ortaklığı</span>
                        <h2 class="text-2xl sm:text-3xl font-extrabold">Referans & Ortaklık (Affiliate) Sistemi</h2>
                        <p class="text-zinc-400 text-sm">Davet bağlantınızla Pro üyelik başlatan herkesten %30 ömür boyu komisyon kazanın.</p>
                        <div class="flex flex-col sm:flex-row gap-2">
                            <input id="affiliate-link-input" type="text" readonly value="https://nexus26.ai/?ref=NEXUS-VIP-2026" class="flex-1 bg-zinc-950 border border-white/10 rounded-xl px-4 py-3 text-xs font-mono text-emerald-300">
                            <button onclick="copyAffiliateLink()" class="px-5 py-3 rounded-xl bg-emerald-600 hover:bg-emerald-500 text-white text-xs font-bold cursor-pointer">Kopyala</button>
                        </div>
                    </div>
                    <div class="bg-zinc-950/90 border border-white/10 rounded-2xl p-6 space-y-4">
                        <span class="text-xs font-bold text-zinc-300">Ortaklık Özeti</span>
                        <div class="grid grid-cols-2 gap-3">
                            <div class="p-3.5 rounded-xl bg-white/[0.03]"><span class="text-[11px] text-zinc-400">Davetli</span><span id="aff-count" class="text-2xl font-extrabold text-white">14</span></div>
                            <div class="p-3.5 rounded-xl bg-white/[0.03]"><span class="text-[11px] text-zinc-400">Kazanç</span><span id="aff-earnings" class="text-2xl font-extrabold text-emerald-400">₺1.638</span></div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- FİYATLANDIRMA -->
        <section id="fiyatlandirma" class="py-20 px-4 max-w-6xl mx-auto">
            <div class="text-center mb-12">
                <span class="text-xs font-bold uppercase tracking-widest text-violet-400">Esnek Lisanslama</span>
                <h2 class="text-3xl sm:text-5xl font-extrabold mt-2 mb-4">Ekibinizle Birlikte Büyüyen Planlar</h2>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="glass bento-card rounded-3xl p-8 border border-white/5 flex flex-col justify-between">
                    <div>
                        <span class="text-xs font-bold uppercase tracking-widest text-zinc-500">Başlangıç</span>
                        <div class="text-4xl font-extrabold mt-3 mb-2">₺0 <span class="text-sm font-normal text-zinc-500">/ ay</span></div>
                    </div>
                    <button onclick="showToast('Ücretsiz başlangıç tanımlandı!')" class="w-full py-3.5 rounded-xl bg-white/5 hover:bg-white/10 border border-white/10 text-white font-semibold text-sm">Ücretsiz Başla</button>
                </div>
                <div class="glass bento-card rounded-3xl p-8 border-2 border-violet-500 relative flex flex-col justify-between shadow-2xl">
                    <div>
                        <span class="text-xs font-bold uppercase tracking-widest text-violet-400">Nexus Pro</span>
                        <div class="text-4xl font-extrabold mt-3 mb-2">₺390 <span class="text-sm font-normal text-zinc-500">/ ay</span></div>
                    </div>
                    <button onclick="openPaymentModal()" class="w-full py-3.5 rounded-xl bg-violet-600 hover:bg-violet-500 text-white font-bold text-sm cursor-pointer">Pro Satın Al</button>
                </div>
                <div class="glass bento-card rounded-3xl p-8 border border-white/5 flex flex-col justify-between">
                    <div>
                        <span class="text-xs font-bold uppercase tracking-widest text-zinc-500">Enterprise</span>
                        <div class="text-4xl font-extrabold mt-2 mb-1">Özel</div>
                    </div>
                    <button onclick="openModal('contact')" class="w-full py-3.5 rounded-xl bg-white/5 border border-white/10 text-white font-semibold text-sm">Satış Ekibi</button>
                </div>
            </div>
        </section>

        <!-- YÖNETİCİ CÜZDANI -->
        <section id="cuzdan-merkezi" class="py-12 px-4 max-w-6xl mx-auto">
            <div class="glass rounded-3xl p-8 border border-violet-500/20">
                <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 mb-8 pb-6 border-b border-white/10">
                    <div>
                        <span class="text-xs font-bold uppercase tracking-widest text-violet-400">Yalnızca Sistem Sahibine Özel</span>
                        <h2 class="text-2xl sm:text-3xl font-extrabold mt-1">Yönetici Cüzdanı & Kendi IBAN Hesabınız</h2>
                    </div>
                    <button onclick="requestAdminPasswordForWithdraw()" class="px-5 py-3 rounded-xl bg-gradient-to-r from-emerald-500 to-teal-600 text-white text-xs font-bold cursor-pointer">Kendi IBAN'ıma Para Çek</button>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                    <div class="bg-zinc-950 p-6 rounded-2xl border border-white/10">
                        <span class="text-xs text-zinc-400 block mb-1">Toplam Bakiye</span>
                        <div id="wallet-balance" class="text-3xl font-extrabold text-white">₺48.950,00</div>
                    </div>
                    <div class="bg-zinc-950 p-6 rounded-2xl border border-white/10">
                        <span class="text-xs text-zinc-400 block mb-1">Onaylı Yönetici IBAN</span>
                        <div id="display-iban" class="text-sm font-mono font-bold text-violet-300">TR42 0006 1004 9912 ...</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Footer -->
        <footer class="border-t border-white/5 py-12 px-4 mt-16 bg-zinc-950/50 text-center">
            <p class="text-zinc-500 text-xs">© 2026 NexusAI Teknoloji A.Ş. Tüm hakları saklıdır. iOS, Android, Tablet & PC Otomatik Uyumlu.</p>
        </footer>
    </div>

    <!-- Bildirim Toast -->
    <div id="toast" class="fixed bottom-24 right-6 z-50 transform translate-y-20 opacity-0 transition-all duration-300 pointer-events-none">
        <div class="glass px-5 py-3.5 rounded-2xl border border-violet-500/40 flex items-center gap-3 shadow-2xl">
            <i data-lucide="check-circle-2" class="w-5 h-5 text-emerald-400"></i>
            <span id="toast-message" class="text-sm font-medium text-white">İşlem başarılı!</span>
        </div>
    </div>

    <!-- Yüzen Sesli Asistan Dock -->
    <div id="floating-voice-dock" class="fixed bottom-5 right-5 z-40 glass rounded-2xl p-3 border border-violet-500/30 shadow-2xl flex items-center gap-3 transition-all duration-300">
        <button id="dock-call-btn" class="w-10 h-10 rounded-xl bg-gradient-to-tr from-rose-500 to-violet-600 text-white flex items-center justify-center cursor-pointer" title="Sesli Asistan">
            <i data-lucide="mic" class="w-5 h-5"></i>
        </button>
        <div>
            <div class="flex items-center gap-1.5"><span id="dock-status-dot" class="w-2 h-2 rounded-full bg-zinc-500"></span><span id="dock-status-title" class="text-xs font-bold text-white">Sesli Asistan</span></div>
            <p id="dock-status-sub" class="text-[10px] text-zinc-400">Tüm cihazlarda aktif</p>
        </div>
    </div>

    <!-- Modal Yapısı -->
    <div id="modal-overlay" class="fixed inset-0 bg-black/80 backdrop-blur-md z-50 hidden items-center justify-center p-4" onclick="if(event.target === this) closeModal()">
        <div class="glass max-w-lg w-full rounded-3xl p-8 border border-white/15 relative shadow-2xl">
            <button onclick="closeModal()" class="absolute top-5 right-5 text-zinc-400 hover:text-white"><i data-lucide="x" class="w-5 h-5"></i></button>
            <div id="modal-content"></div>
        </div>
    </div>

    <script>
        lucide.createIcons();

        let currentTab = 'strategy';
        let loggedInUser = null;
        let isDockVisible = true;
        let walletBalanceNumeric = 48950;
        let affiliateReferralCount = 14;
        let affiliateEarningsNumeric = 1638;
        const apiKey = "";
        const sessionHistory = [];
        const ragDocuments = [
            { name: "2026_Kurumsal_Finans.txt", size: "14 KB", content: "Q4 bütçe limiti 250.000 TL." },
            { name: "Hizmet_Sozlesmesi.txt", size: "22 KB", content: "Sözleşme süresi 12 ay, ihbar süresi 30 gün." }
        ];

        // --- CİHAZ OTOMATİK ALGILAMA VE ÖLÇEKLENDİRME MOTORU ---
        function detectDeviceAndApplyLayout() {
            const width = window.innerWidth;
            const userAgent = navigator.userAgent || navigator.vendor || window.opera;
            const badge = document.getElementById('detected-device-badge');
            const wrapper = document.getElementById('device-wrapper');

            // Önceki çerçeve sınıflarını temizle
            wrapper.classList.remove('device-frame-iphone', 'device-frame-ipad', 'device-frame-android');

            if (/android/i.test(userAgent) && width < 768) {
                if (badge) badge.textContent = `Android Mobil Cihaz Algılandı (${width}px)`;
            } else if (/iPad|iPhone|iPod/.test(userAgent) && !window.MSStream) {
                if (badge) badge.textContent = `iOS / Apple Cihaz Algılandı (${width}px)`;
            } else if (width <= 640) {
                if (badge) badge.textContent = `Mobil Telefon Görünümü (${width}px)`;
            } else if (width > 640 && width <= 1024) {
                if (badge) badge.textContent = `Tablet / iPad Görünümü (${width}px)`;
            } else {
                if (badge) badge.textContent = `PC / Masaüstü Görünümü (${width}px)`;
            }
        }

        window.addEventListener('resize', detectDeviceAndApplyLayout);
        window.addEventListener('DOMContentLoaded', detectDeviceAndApplyLayout);

        function setDeviceView(mode) {
            const wrapper = document.getElementById('device-wrapper');
            const badge = document.getElementById('detected-device-badge');
            
            // Buton aktiflik sınıfları
            ['auto', 'iphone', 'android', 'tablet', 'pc'].forEach(m => {
                const btn = document.getElementById(`mode-${m}`);
                if (btn) {
                    if (m === mode) {
                        btn.className = "px-2.5 py-1 rounded-lg bg-violet-600 text-white font-semibold transition cursor-pointer";
                    } else {
                        btn.className = "px-2.5 py-1 rounded-lg bg-white/5 hover:bg-white/10 text-zinc-300 transition cursor-pointer";
                    }
                }
            });

            wrapper.classList.remove('device-frame-iphone', 'device-frame-ipad', 'device-frame-android');

            if (mode === 'iphone') {
                wrapper.classList.add('device-frame-iphone');
                if (badge) badge.textContent = "Manuel Görünüm: iPhone (390px)";
            } else if (mode === 'android') {
                wrapper.classList.add('device-frame-android');
                if (badge) badge.textContent = "Manuel Görünüm: Android (412px)";
            } else if (mode === 'tablet') {
                wrapper.classList.add('device-frame-ipad');
                if (badge) badge.textContent = "Manuel Görünüm: Tablet / iPad (768px)";
            } else if (mode === 'pc') {
                if (badge) badge.textContent = "Manuel Görünüm: PC / Tam Ekran";
            } else {
                detectDeviceAndApplyLayout();
            }
            showToast(`Görünüm modu değiştirildi: ${mode.toUpperCase()}`);
        }

        // Cüzdan & Gelir Aktarım
        function addRevenueToWallet(amount, sourceLabel) {
            walletBalanceNumeric += amount;
            const walletEl = document.getElementById('wallet-balance');
            if (walletEl) walletEl.textContent = `₺${walletBalanceNumeric.toLocaleString('tr-TR', { minimumFractionDigits: 2 })}`;
            showToast(`+₺${amount} (${sourceLabel}) cüzdana eklendi.`);
        }

        // Geçmiş Çekmecesi
        function toggleHistoryDrawer() {
            document.getElementById('history-drawer').classList.toggle('translate-x-full');
        }

        // RAG Bilgi Bankası
        function renderRagFiles() {
            const list = document.getElementById('rag-files-list');
            if (!list) return;
            list.innerHTML = ragDocuments.map(doc => `
                <div class="p-2.5 rounded-xl bg-white/[0.03] border border-white/5 flex items-center justify-between text-xs">
                    <span class="text-zinc-200 truncate">${doc.name}</span>
                    <span class="text-[10px] text-zinc-500">${doc.size}</span>
                </div>
            `).join('');
        }
        renderRagFiles();

        function handleRagFileUpload(event) {
            const file = event.target.files[0];
            if (!file) return;
            ragDocuments.unshift({ name: file.name, size: `${Math.round(file.size/1024)} KB`, content: "Yüklendi." });
            renderRagFiles();
            showToast(`"${file.name}" yüklendi ve indekslendi!`);
        }

        async function askRagDocuments() {
            const input = document.getElementById('rag-question-input');
            const chatBox = document.getElementById('rag-chat-box');
            const q = input.value.trim();
            if (!q) return;
            input.value = '';
            chatBox.innerHTML += `<div class="p-3 rounded-xl bg-white/5 text-zinc-200 ml-8">${q}</div>`;
            setTimeout(() => {
                chatBox.innerHTML += `<div class="p-3 rounded-xl bg-sky-500/10 text-sky-200 mr-8">Yüklü dokümanlara göre: ${ragDocuments[0].content}</div>`;
                chatBox.scrollTop = chatBox.scrollHeight;
            }, 600);
        }

        // AI Model Arena
        async function runModelArena() {
            const prompt = document.getElementById('arena-prompt-input').value.trim();
            if (!prompt) { showToast('Lütfen soru yazın.'); return; }
            document.getElementById('arena-output-a').textContent = "Model A strateji üretiyor...";
            document.getElementById('arena-output-b').textContent = "Model B verileri analiz ediyor...";
            setTimeout(() => {
                document.getElementById('arena-output-a').textContent = `[Vizyoner]: "${prompt}" için en iyi marka konsepti topluluk odaklı viral büyümedir.`;
                document.getElementById('arena-output-b').textContent = `[Analist]: "${prompt}" için CAC maliyetini %24 düşürecek metrikler doğrulandı.`;
            }, 800);
        }

        // Pazar Yeri Satın Alma
        function buyMarketplaceAgent(title, price, prompt) {
            addRevenueToWallet(price, title);
            scrollToSection('ai-hub');
            document.getElementById('ai-prompt').value = prompt;
            showToast(`"${title}" satın alındı ve stüdyoda açıldı!`);
        }

        // Affiliate Kopyala
        function copyAffiliateLink() {
            navigator.clipboard.writeText(document.getElementById('affiliate-link-input').value);
            showToast('Davet linki panoya kopyalandı!');
        }

        // Ödeme Modalı
        function openPaymentModal() {
            openModal('contact');
            document.getElementById('modal-content').innerHTML = `
                <h3 class="text-xl font-bold mb-2">Nexus Pro Güvenli Ödeme</h3>
                <p class="text-xs text-zinc-400 mb-4">Kendi banka kartınızla 14 gün ücretsiz deneyin (₺390/ay).</p>
                <div class="space-y-3">
                    <input type="text" placeholder="Ad Soyad" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3 text-xs text-white">
                    <input type="text" placeholder="Kart Numarası (16 Hane)" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3 text-xs text-white font-mono">
                    <button onclick="addRevenueToWallet(390, 'Pro Abonelik'); closeModal(); showToast('Pro abonelik aktifleşti!')" class="w-full py-3 bg-violet-600 rounded-xl font-bold text-xs cursor-pointer">Güvenli Öde</button>
                </div>
            `;
        }

        // Yönetici IBAN Çekim
        function requestAdminPasswordForWithdraw() {
            const pass = prompt("Yönetici Şifresini Girin (Şifre: 57009):");
            if (pass === '57009') {
                const amount = prompt(`Çekilecek Tutar (Mevcut Bakiye: ₺${walletBalanceNumeric}):`, walletBalanceNumeric);
                if (amount && !isNaN(amount)) {
                    walletBalanceNumeric = Math.max(0, walletBalanceNumeric - Number(amount));
                    document.getElementById('wallet-balance').textContent = `₺${walletBalanceNumeric.toLocaleString('tr-TR', { minimumFractionDigits: 2 })}`;
                    showToast(`₺${Number(amount).toLocaleString('tr-TR')} kendi IBAN hesabınıza aktarıldı!`);
                }
            } else if (pass !== null) {
                showToast('Hatalı şifre! (Doğru şifre: 57009)');
            }
        }

        // Modal Yönetimi
        function openModal(type) {
            const overlay = document.getElementById('modal-overlay');
            const content = document.getElementById('modal-content');
            overlay.classList.remove('hidden');
            overlay.classList.add('flex');
            content.innerHTML = `
                <h3 class="text-2xl font-bold mb-2">${type === 'login' ? 'Giriş Yap' : 'Kayıt Ol'}</h3>
                <div class="space-y-3">
                    <input type="email" placeholder="E-posta" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3 text-xs text-white">
                    <input type="password" placeholder="Şifre" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3 text-xs text-white">
                    <button onclick="loggedInUser='kullanici@nexus26.ai'; closeModal(); updateUIAfterLogin(); showToast('Giriş yapıldı!')" class="w-full py-3 bg-violet-600 rounded-xl font-bold text-xs cursor-pointer">Devam Et</button>
                </div>
            `;
        }

        function updateUIAfterLogin() {
            if (!loggedInUser) return;
            document.getElementById('nav-auth-area').innerHTML = `
                <span class="text-xs text-emerald-400 font-semibold px-2">${loggedInUser}</span>
                <button onclick="loggedInUser=null; location.reload();" class="text-xs text-rose-400 px-2">Çıkış</button>
            `;
        }

        function closeModal() {
            document.getElementById('modal-overlay').classList.add('hidden');
            document.getElementById('modal-overlay').classList.remove('flex');
        }

        function scrollToSection(id) {
            document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
        }

        function showToast(msg) {
            const toast = document.getElementById('toast');
            document.getElementById('toast-message').textContent = msg;
            toast.classList.remove('translate-y-20', 'opacity-0');
            setTimeout(() => toast.classList.add('translate-y-20', 'opacity-0'), 3000);
        }

        function toggleFloatingVoiceDock() {
            isDockVisible = !isDockVisible;
            document.getElementById('floating-voice-dock').style.display = isDockVisible ? 'flex' : 'none';
        }

        function setPrompt(txt) { document.getElementById('ai-prompt').value = txt; }
        function switchTab(t) { currentTab = t; showToast(`Mod geçişi: ${t}`); }
        function generateAIResponse() {
            const p = document.getElementById('ai-prompt').value;
            if(!p) { showToast('Lütfen komut yazın.'); return; }
            document.getElementById('ai-output-container').classList.remove('hidden');
            document.getElementById('ai-output-text').textContent = `[NEXUS-AI Yanıtı]: "${p}" talebiniz doğrultusunda 2026 kurumsal verileriyle otonom olarak işlendi ve optimize edildi.`;
            showToast('Analiz tamamlandı!');
        }
        function copyOutput() {
            navigator.clipboard.writeText(document.getElementById('ai-output-text').textContent);
            showToast('Kopyalandı!');
        }
        function downloadOutput() {
            const blob = new Blob([document.getElementById('ai-output-text').textContent], {type: 'text/plain'});
            const a = document.createElement('a'); a.href = URL.createObjectURL(blob); a.download = 'nexus26.txt'; a.click();
            showToast('İndirildi!');
        }
        function clearOutput() { document.getElementById('ai-output-container').classList.add('hidden'); }
    </script>
</body>
</html>
