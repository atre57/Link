<html lang="tr" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0, user-scalable=yes">
    <title<>NexusAI 2026 | Geleceğin Dijital Çalışma Alanı (Auto-Device Responsive)</title>
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

    <div class="fixed inset-0 grid-pattern pointer-events-none z-[-2]"></div>
    <div class="glow-bg top-[-150px] left-[-100px]"></div>
    <div class="glow-bg top-[35%] right-[-150px]" style="background: radial-gradient(circle, rgba(56, 189, 248, 0.1) 0%, rgba(0,0,0,0) 70%);"></div>

    <!-- Cihaz Algılama Çubuğu -->
    <div class="bg-zinc-950/90 border-b border-white/10 px-4 py-2 text-xs flex flex-wrap items-center justify-between gap-3 sticky top-0 z-50 backdrop-blur-md">
        <div class="flex items-center gap-2">
            <span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></span>
            <span id="detected-device-badge" class="font-mono text-zinc-300">Cihaz Algılanıyor...</span>
        </div>
        <div class="flex items-center gap-1.5 overflow-x-auto py-1">
            <span class="text-[11px] text-zinc-500 hidden sm:inline">Görünüm:</span>
            <button onclick="setDeviceView('auto')" id="mode-auto" class="px-2.5 py-1 rounded-lg bg-violet-600 text-white font-semibold transition cursor-pointer">Otomatik</button>
            <button onclick="setDeviceView('mobile')" id="mode-mobile" class="px-2.5 py-1 rounded-lg bg-white/5 hover:bg-white/10 text-zinc-300 transition cursor-pointer">Telefon</button>
            <button onclick="setDeviceView('tablet')" id="mode-tablet" class="px-2.5 py-1 rounded-lg bg-white/5 hover:bg-white/10 text-zinc-300 transition cursor-pointer">Tablet</button>
            <button onclick="setDeviceView('pc')" id="mode-pc" class="px-2.5 py-1 rounded-lg bg-white/5 hover:bg-white/10 text-zinc-300 transition cursor-pointer">Masaüstü</button>
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
            </div>

            <!-- Menü Sekmeleri -->
            <div class="hidden lg:flex items-center gap-4 text-xs font-medium text-zinc-400">
                <a href="#live-voice" class="text-violet-300 hover:text-white transition flex items-center gap-1.5"><span class="w-2 h-2 rounded-full bg-rose-500 animate-pulse"></span> Canlı Ses</a>
                <a href="#ai-hub" class="hover:text-white transition">AI Stüdyo</a>
                <a href="#rag-vault" class="hover:text-white transition">Bilgi Bankası</a>
                <a href="#ai-arena" class="hover:text-white transition">AI Arena</a>
                <a href="#marketplace" class="hover:text-white transition">Pazar Yeri</a>
                <a href="#affiliate-hub" class="hover:text-white transition">Ortaklık</a>
            </div>

            <div class="flex items-center gap-2">
                <button onclick="toggleHistoryDrawer()" class="px-2.5 py-2 rounded-xl bg-white/5 hover:bg-white/10 border border-white/10 text-zinc-300 text-xs font-semibold flex items-center gap-1.5 transition cursor-pointer" title="Geçmiş">
                    <i data-lucide="history" class="w-4 h-4 text-sky-400"></i>
                    <span class="hidden sm:inline">Geçmiş</span>
                    <span id="history-count" class="px-1.5 py-0.5 rounded-full bg-violet-600/30 text-violet-300 text-[10px] font-mono">0</span>
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

    <!-- Ana Konteyner -->
    <div id="device-wrapper" class="w-full transition-all duration-300">

        <!-- Geçmiş Çekmecesi -->
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
                <div id="favorite-prompts-list" class="space-y-2 max-h-48 overflow-y-auto pr-1"></div>
            </div>
            <div class="flex-1 p-4 overflow-y-auto">
                <div class="flex items-center justify-between mb-2.5">
                    <span class="text-[11px] font-bold uppercase tracking-wider text-sky-400">Son AI Stüdyo Çıktıları</span>
                    <button onclick="clearSessionHistory()" class="text-[11px] text-zinc-500 hover:text-rose-400 transition">Temizle</button>
                </div>
                <div id="session-history-list" class="space-y-2.5">
                    <p class="text-xs text-zinc-500 italic">Henüz üretim yapılmadı.</p>
                </div>
            </div>
        </div>

        <!-- Hero -->
        <header class="relative pt-16 pb-20 px-4 text-center max-w-5xl mx-auto">
            <div class="inline-flex items-center gap-2.5 px-3.5 py-1.5 rounded-full bg-white/[0.04] border border-white/10 text-xs font-medium text-violet-300 mb-7 shadow-inner">
                <span class="relative flex h-2 w-2">
                    <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-75"></span>
                    <span class="relative inline-flex rounded-full h-2 w-2 bg-emerald-500"></span>
                </span>
                <span>Otomatik Cihaz Uyumlu Ekran Mimarisi Aktif</span>
            </div>
            <h1 class="text-4xl sm:text-6xl md:text-7xl font-extrabold tracking-tight leading-[1.08] mb-6">
                Kurumsal Zekayı <span class="gradient-text">Otonom Hızla</span> Ölçeklendirin.
            </h1>
            <p class="text-zinc-400 text-sm sm:text-xl max-w-2xl mx-auto mb-10 leading-relaxed font-normal">
                Telefon, tablet ve masaüstü bilgisayarlarınız için kusursuz uyum sağlayan yeni nesil yapay zeka çalışma alanı. Tüm özellikler tamamen açık ve ücretsizdir.
            </p>
            <div class="flex flex-col sm:flex-row items-center justify-center gap-4">
                <button onclick="scrollToSection('live-voice')" class="w-full sm:w-auto px-8 py-4 bg-gradient-to-r from-violet-600 to-indigo-600 hover:from-violet-500 hover:to-indigo-500 text-white font-bold rounded-2xl transition flex items-center justify-center gap-2.5 shadow-xl shadow-violet-600/25 cursor-pointer">
                    <i data-lucide="mic" class="w-5 h-5"></i> Yapay Zeka ile Sesli Konuş
                </button>
                <button onclick="scrollToSection('ai-hub')" class="w-full sm:w-auto px-8 py-4 glass hover:bg-white/10 text-white font-semibold rounded-2xl transition flex items-center justify-center gap-2.5 cursor-pointer">
                    <i data-lucide="cpu" class="w-5 h-5 text-sky-400"></i> Canlı AI Stüdyoyu Aç
                </button>
            </div>
        </header>

        <!-- Canlı Sesli AI Konuşma Merkezi -->
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
                            Mikrofonunuzu açın; iş stratejisi veya günlük planlarınız hakkında sesli asistanımızla kesintisiz konuşun.
                        </p>
                        <div class="flex flex-wrap items-center justify-center lg:justify-start gap-3 pt-2">
                            <select id="live-voice-select" class="bg-zinc-950 border border-white/10 rounded-xl px-3.5 py-3 text-xs text-zinc-200 focus:outline-none focus:border-violet-500">
                                <option value="Zephyr">Ses: Zephyr (Parlak & Enerjik)</option>
                                <option value="Kore">Ses: Kore (Net & Kurumsal)</option>
                                <option value="Puck">Ses: Puck (Samimi & Dinamik)</option>
                            </select>
                            <button id="live-call-btn" class="px-6 py-3 rounded-xl bg-gradient-to-r from-rose-500 to-violet-600 hover:opacity-95 text-white font-bold text-sm flex items-center gap-2.5 transition shadow-lg shadow-rose-500/20 cursor-pointer">
                                <i data-lucide="phone-call" class="w-4 h-4"></i>
                                <span id="live-btn-label">Sesli Görüşmeyi Başlat</span>
                            </button>
                        </div>
                    </div>
                    <div class="w-full lg:w-[440px] bg-zinc-950/90 border border-white/10 rounded-2xl p-5 flex flex-col justify-between space-y-4">
                        <div class="flex items-center justify-between pb-3 border-b border-white/10">
                            <span class="text-xs font-mono text-zinc-400 flex items-center gap-2">
                                <i data-lucide="audio-waveform" class="w-4 h-4 text-violet-400"></i> CANLI TRANSKRİPT
                            </span>
                            <div id="voice-visualizer" class="flex items-center gap-1 h-5">
                                <span class="w-1 h-2 bg-violet-500/40 rounded-full transition-all duration-150"></span>
                                <span class="w-1 h-2 bg-violet-500/40 rounded-full transition-all duration-150"></span>
                                <span class="w-1 h-2 bg-violet-500/40 rounded-full transition-all duration-150"></span>
                            </div>
                        </div>
                        <div id="live-transcript-box" class="h-36 overflow-y-auto space-y-2 text-xs text-zinc-300 pr-1">
                            <p class="italic text-zinc-500">Görüşme başladığında konuşmalarınız burada canlı olarak akacaktır...</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- AI Stüdyo -->
        <section id="ai-hub" class="py-12 px-4 max-w-7xl mx-auto">
            <div class="glass rounded-3xl p-6 sm:p-10 border border-white/10 relative">
                <div class="flex flex-col lg:flex-row items-start lg:items-center justify-between gap-4 mb-8 pb-6 border-b border-white/10">
                    <div>
                        <span class="text-xs font-bold uppercase tracking-widest text-violet-400">NexusAI Multimodal Engine</span>
                        <h2 class="text-2xl sm:text-3xl font-extrabold mt-1">Canlı AI Stüdyosu</h2>
                    </div>
                    <div class="flex flex-wrap items-center gap-2 bg-zinc-950 p-1.5 rounded-2xl border border-white/10">
                        <button onclick="switchTab('strategy')" id="tab-strategy" class="tab-btn px-4 py-2 rounded-xl text-xs font-bold bg-violet-600 text-white transition cursor-pointer">Strateji</button>
                        <button onclick="switchTab('code')" id="tab-code" class="tab-btn px-4 py-2 rounded-xl text-xs font-bold text-zinc-400 hover:text-white transition cursor-pointer">Kod Mimarı</button>
                        <button onclick="switchTab('trend')" id="tab-trend" class="tab-btn px-4 py-2 rounded-xl text-xs font-bold text-zinc-400 hover:text-white transition cursor-pointer">Trend Analizi</button>
                        <button onclick="switchTab('image')" id="tab-image" class="tab-btn px-4 py-2 rounded-xl text-xs font-bold text-zinc-400 hover:text-white transition cursor-pointer">Görsel Üretici</button>
                    </div>
                </div>
                <div class="space-y-4">
                    <div class="relative">
                        <textarea id="ai-prompt" rows="3" class="w-full bg-zinc-950 border border-white/10 rounded-2xl p-4 text-sm sm:text-base text-white placeholder-zinc-500 focus:outline-none focus:border-violet-500 transition resize-none" placeholder="Yapay zeka için komut veya soru yazın..."></textarea>
                        <div class="absolute bottom-3 right-3 flex items-center gap-2">
                            <button onclick="saveCurrentPromptToFavorites()" class="px-3.5 py-2.5 bg-white/5 hover:bg-white/10 border border-white/10 text-zinc-300 font-semibold text-xs rounded-xl transition flex items-center gap-1.5 cursor-pointer">
                                <i data-lucide="bookmark-plus" class="w-4 h-4 text-amber-400"></i> Kaydet
                            </button>
                            <button onclick="generateAIResponse()" id="generate-btn" class="px-5 py-2.5 bg-gradient-to-r from-violet-600 to-indigo-600 hover:from-violet-500 hover:to-indigo-500 text-white font-bold text-xs rounded-xl transition flex items-center gap-2 shadow-lg shadow-violet-600/30 cursor-pointer">
                                <i data-lucide="sparkles" class="w-4 h-4"></i> Analiz & Üret
                            </button>
                        </div>
                    </div>
                </div>
                <div id="ai-output-container" class="mt-8 hidden">
                    <div class="bg-zinc-950 rounded-2xl border border-white/10 overflow-hidden">
                        <div class="flex items-center justify-between px-5 py-3 border-b border-white/10 bg-zinc-900/50">
                            <span class="text-xs font-mono font-bold text-zinc-300">NEXUS-ENGINE // ÇIKTI</span>
                            <div class="flex items-center gap-2">
                                <button onclick="copyOutput()" class="px-3 py-1.5 rounded-lg bg-white/5 hover:bg-white/10 text-zinc-300 text-xs font-semibold cursor-pointer">Kopyala</button>
                                <button onclick="downloadOutput()" class="px-3 py-1.5 rounded-lg bg-white/5 hover:bg-white/10 text-zinc-300 text-xs font-semibold cursor-pointer">İndir</button>
                                <button onclick="clearOutput()" class="p-1.5 rounded-lg hover:bg-white/10 text-zinc-400"><i data-lucide="x" class="w-4 h-4"></i></button>
                            </div>
                        </div>
                        <div class="p-6">
                            <div id="ai-output-text" class="text-sm text-zinc-200 leading-relaxed whitespace-pre-wrap font-mono"></div>
                            <div id="ai-output-image-wrap" class="hidden flex justify-center">
                                <img id="ai-output-image" src="" alt="Görsel" class="rounded-xl max-h-[480px] object-cover border border-white/10 shadow-2xl">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Doküman & PDF Bilgi Bankası (RAG) -->
        <section id="rag-vault" class="py-12 px-4 max-w-7xl mx-auto">
            <div class="glass rounded-3xl p-8 border border-sky-500/25">
                <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 mb-8 pb-6 border-b border-white/10">
                    <div>
                        <span class="text-xs font-bold uppercase tracking-widest text-sky-400">Kurumsal Hafıza (RAG)</span>
                        <h2 class="text-2xl sm:text-3xl font-extrabold mt-1">Doküman & PDF Bilgi Bankası</h2>
                    </div>
                </div>
                <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
                    <div class="space-y-4">
                        <label for="rag-file-input" class="block border-2 border-dashed border-sky-500/30 hover:border-sky-400 rounded-2xl p-6 text-center bg-zinc-950/70 cursor-pointer">
                            <div class="w-11 h-11 rounded-xl bg-sky-500/15 text-sky-400 flex items-center justify-center mx-auto mb-3">
                                <i data-lucide="file-up" class="w-6 h-6"></i>
                            </div>
                            <p class="text-sm font-bold text-white">Doküman Yükle</p>
                            <input type="file" id="rag-file-input" class="hidden" onchange="handleRagFileUpload(event)">
                        </label>
                        <div class="bg-zinc-950/80 border border-white/10 rounded-2xl p-4 space-y-2.5">
                            <span class="text-xs font-bold text-zinc-300">Yüklü Kaynaklar</span>
                            <div id="rag-files-list" class="space-y-2 max-h-48 overflow-y-auto pr-1"></div>
                        </div>
                    </div>
                    <div class="lg:col-span-2 bg-zinc-950/90 border border-white/10 rounded-2xl p-5 flex flex-col justify-between space-y-4">
                        <div id="rag-chat-box" class="h-56 overflow-y-auto space-y-3 text-xs pr-1">
                            <div class="p-3 rounded-xl bg-sky-500/10 text-sky-200">Bilgi bankasındaki dokümanlar hakkında soru sorabilirsiniz.</div>
                        </div>
                        <div class="flex items-center gap-2 pt-2 border-t border-white/10">
                            <input id="rag-question-input" type="text" placeholder="Belgelerde ara..." class="flex-1 bg-zinc-900 border border-white/10 rounded-xl px-4 py-3 text-xs text-white placeholder-zinc-500 focus:outline-none focus:border-sky-500" onkeydown="if(event.key==='Enter') askRagDocuments()">
                            <button onclick="askRagDocuments()" class="px-5 py-3 rounded-xl bg-gradient-to-r from-sky-500 to-indigo-600 text-white text-xs font-bold cursor-pointer">Sorgula</button>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- AI Model Arena -->
        <section id="ai-arena" class="py-12 px-4 max-w-7xl mx-auto">
            <div class="glass rounded-3xl p-8 border border-pink-500/25">
                <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 mb-8 pb-6 border-b border-white/10">
                    <div>
                        <span class="text-xs font-bold uppercase tracking-widest text-pink-400">Side-by-Side Karşılaştırma</span>
                        <h2 class="text-2xl sm:text-3xl font-extrabold mt-1">Çoklu AI Model Arenası</h2>
                    </div>
                </div>
                <div class="flex flex-col sm:flex-row gap-3 mb-6">
                    <input id="arena-prompt-input" type="text" placeholder="İki uzmanın yanıtlayacağı soruyu yazın..." class="flex-1 bg-zinc-950 border border-white/10 rounded-2xl px-4 py-3.5 text-sm text-white focus:outline-none focus:border-pink-500">
                    <button onclick="runModelArena()" class="px-6 py-3.5 rounded-2xl bg-gradient-to-r from-pink-600 to-violet-600 text-white font-bold text-xs cursor-pointer">Yarıştır</button>
                </div>
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
                    <div class="bg-zinc-950/90 border border-violet-500/25 rounded-2xl p-6">
                        <span class="font-bold text-sm text-violet-300 block mb-3">MODEL A // Yaratıcı Vizyoner</span>
                        <div id="arena-output-a" class="text-xs sm:text-sm text-zinc-300 leading-relaxed whitespace-pre-wrap min-h-[140px]">Bekleniyor...</div>
                    </div>
                    <div class="bg-zinc-950/90 border border-sky-500/25 rounded-2xl p-6">
                        <span class="font-bold text-sm text-sky-300 block mb-3">MODEL B // Veri & ROI Analisti</span>
                        <div id="arena-output-b" class="text-xs sm:text-sm text-zinc-300 leading-relaxed whitespace-pre-wrap min-h-[140px]">Bekleniyor...</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Pazar Yeri -->
        <section id="marketplace" class="py-12 px-4 max-w-7xl mx-auto">
            <div class="glass rounded-3xl p-8 border border-amber-500/25">
                <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 mb-8 pb-6 border-b border-white/10">
                    <div>
                        <span class="text-xs font-bold uppercase tracking-widest text-amber-400">Şablon Ekonomisi</span>
                        <h2 class="text-2xl sm:text-3xl font-extrabold mt-1">Ajan Pazar Yeri</h2>
                    </div>
                </div>
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-5">
                    <div class="bg-zinc-950/90 border border-white/10 rounded-2xl p-5 flex flex-col justify-between bento-card">
                        <div>
                            <div class="flex justify-between mb-3"><span class="text-[10px] font-mono text-emerald-300">E-TİCARET</span><span class="text-sm font-extrabold">Ücretsiz</span></div>
                            <h3 class="font-bold text-base mb-1.5">E-Ticaret SEO Botu</h3>
                        </div>
                        <button onclick="buyMarketplaceAgent('E-Ticaret SEO Botu', 0, 'SEO metni üret: ')" class="mt-5 w-full py-2.5 rounded-xl bg-amber-500/15 text-amber-300 text-xs font-bold cursor-pointer">Şablonu Aç</button>
                    </div>
                    <div class="bg-zinc-950/90 border border-white/10 rounded-2xl p-5 flex flex-col justify-between bento-card">
                        <div>
                            <div class="flex justify-between mb-3"><span class="text-[10px] font-mono text-violet-300">HUKUK</span><span class="text-sm font-extrabold">Ücretsiz</span></div>
                            <h3 class="font-bold text-base mb-1.5">Hukuk Sözleşme Denetçisi</h3>
                        </div>
                        <button onclick="buyMarketplaceAgent('Hukuk Sözleşme Denetçisi Pro', 0, 'Risk analizi: ')" class="mt-5 w-full py-2.5 rounded-xl bg-amber-500/15 text-amber-300 text-xs font-bold cursor-pointer">Şablonu Aç</button>
                    </div>
                </div>
            </div>
        </section>

        <!-- Ortaklık -->
        <section id="affiliate-hub" class="py-12 px-4 max-w-7xl mx-auto">
            <div class="glass rounded-3xl p-8 border border-emerald-500/25">
                <div class="grid grid-cols-1 lg:grid-cols-3 gap-8 items-center">
                    <div class="lg:col-span-2 space-y-4">
                        <span class="text-xs font-bold uppercase tracking-widest text-emerald-400">Topluluk & İş Birliği</span>
                        <h2 class="text-2xl sm:text-3xl font-extrabold">Referans (Affiliate) Sistemi</h2>
                        <p class="text-zinc-400 text-sm">Davet linkinizi paylaşarak arkadaşlarınızın da NexusAI platformuna kolayca katılmasını sağlayın.</p>
                        <div class="flex flex-col sm:flex-row gap-2">
                            <input id="affiliate-link-input" type="text" readonly value="https://nexus26.ai/?ref=VIP-2026" class="flex-1 bg-zinc-950 border border-white/10 rounded-xl px-4 py-3 text-xs font-mono text-emerald-300">
                            <button onclick="copyAffiliateLink()" class="px-5 py-3 rounded-xl bg-emerald-600 hover:bg-emerald-500 text-white text-xs font-bold cursor-pointer">Kopyala</button>
                        </div>
                    </div>
                    <div class="bg-zinc-950/90 border border-white/10 rounded-2xl p-6 space-y-4">
                        <span class="text-xs font-bold text-zinc-300">Ortaklık Özeti</span>
                        <div class="grid grid-cols-2 gap-3">
                            <div class="p-3.5 rounded-xl bg-white/[0.03]"><span class="text-[11px] text-zinc-400">Davetli</span><span class="text-2xl font-extrabold text-white">14</span></div>
                            <div class="p-3.5 rounded-xl bg-white/[0.03]"><span class="text-[11px] text-zinc-400">Aktivite</span><span class="text-2xl font-extrabold text-emerald-400">%100</span></div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Yönetici Cüzdanı -->
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
                        <div class="text-sm font-mono font-bold text-violet-300">TR42 0006 1004 9912 ...</div>
                    </div>
                </div>
            </div>
        </section>

        <footer class="border-t border-white/5 py-12 px-4 mt-16 bg-zinc-950/50 text-center">
            <p class="text-zinc-500 text-xs">© 2026 NexusAI Teknoloji A.Ş. Tüm hakları saklıdır.</p>
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
    <div id="floating-voice-dock" class="fixed bottom-5 right-5 z-40 glass rounded-2xl p-3 border border-violet-500/30 shadow-2xl flex items-center gap-3">
        <button id="dock-call-btn" class="w-10 h-10 rounded-xl bg-gradient-to-tr from-rose-500 to-violet-600 text-white flex items-center justify-center cursor-pointer">
            <i data-lucide="mic" class="w-5 h-5"></i>
        </button>
        <div>
            <div class="flex items-center gap-1.5"><span id="dock-status-dot" class="w-2 h-2 rounded-full bg-zinc-500"></span><span class="text-xs font-bold text-white">Sesli Asistan</span></div>
            <p class="text-[10px] text-zinc-400">Tüm cihazlarda aktif</p>
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
        const sessionHistory = [];
        const ragDocuments = [
            { name: "2026_Kurumsal_Finans.txt", size: "14 KB", content: "Q4 bütçe limiti 250.000 TL." }
        ];

        function detectDeviceAndApplyLayout() {
            const width = window.innerWidth;
            const badge = document.getElementById('detected-device-badge');
            if (width <= 640) {
                if (badge) badge.textContent = `Mobil Telefon Görünümü (${width}px)`;
            } else if (width > 640 && width <= 1024) {
                if (badge) badge.textContent = `Tablet Görünümü (${width}px)`;
            } else {
                if (badge) badge.textContent = `Masaüstü Görünümü (${width}px)`;
            }
        }
        window.addEventListener('resize', detectDeviceAndApplyLayout);
        window.addEventListener('DOMContentLoaded', detectDeviceAndApplyLayout);

        function setDeviceView(mode) {
            const badge = document.getElementById('detected-device-badge');
            if (mode === 'mobile') if (badge) badge.textContent = "Manuel: Telefon";
            else if (mode === 'tablet') if (badge) badge.textContent = "Manuel: Tablet";
            else if (mode === 'pc') if (badge) badge.textContent = "Manuel: Masaüstü";
            else detectDeviceAndApplyLayout();
            showToast(`Görünüm güncellendi: ${mode}`);
        }

        function toggleHistoryDrawer() {
            document.getElementById('history-drawer').classList.toggle('translate-x-full');
        }

        function handleRagFileUpload(event) {
            const file = event.target.files[0];
            if (!file) return;
            ragDocuments.unshift({ name: file.name, size: `${Math.round(file.size/1024)} KB`, content: "Yüklendi." });
            showToast(`"${file.name}" yüklendi!`);
        }

        async function askRagDocuments() {
            const q = document.getElementById('rag-question-input').value.trim();
            const box = document.getElementById('rag-chat-box');
            if (!q) return;
            document.getElementById('rag-question-input').value = '';
            box.innerHTML += `<div class="p-3 rounded-xl bg-white/5 text-zinc-200 ml-8">${q}</div>`;
            setTimeout(() => {
                box.innerHTML += `<div class="p-3 rounded-xl bg-sky-500/10 text-sky-200 mr-8">Doküman analizi: ${ragDocuments[0].content}</div>`;
                box.scrollTop = box.scrollHeight;
            }, 600);
        }

        async function runModelArena() {
            const prompt = document.getElementById('arena-prompt-input').value.trim();
            if (!prompt) { showToast('Soru yazın.'); return; }
            document.getElementById('arena-output-a').textContent = "Model A yanıtlıyor...";
            document.getElementById('arena-output-b').textContent = "Model B yanıtlıyor...";
            setTimeout(() => {
                document.getElementById('arena-output-a').textContent = `[Vizyoner]: "${prompt}" için en iyi büyüme modeli topluluk odaklı stratejidir.`;
                document.getElementById('arena-output-b').textContent = `[Analist]: "${prompt}" için bütçe verimliliği %28 oranında optimize edilebilir.`;
            }, 800);
        }

        function buyMarketplaceAgent(title, price, prompt) {
            scrollToSection('ai-hub');
            document.getElementById('ai-prompt').value = prompt;
            showToast(`"${title}" şablonu yüklendi!`);
        }

        function copyAffiliateLink() {
            navigator.clipboard.writeText(document.getElementById('affiliate-link-input').value);
            showToast('Bağlantı kopyalandı!');
        }

        function requestAdminPasswordForWithdraw() {
            const pass = prompt("Yönetici Şifresini Girin (Şifre: 57009):");
            if (pass === '57009') {
                const amount = prompt(`Çekilecek Tutar (Mevcut Bakiye: ₺${walletBalanceNumeric}):`, walletBalanceNumeric);
                if (amount && !isNaN(amount)) {
                    walletBalanceNumeric = Math.max(0, walletBalanceNumeric - Number(amount));
                    document.getElementById('wallet-balance').textContent = `₺${walletBalanceNumeric.toLocaleString('tr-TR', { minimumFractionDigits: 2 })}`;
                    showToast(`₺${Number(amount).toLocaleString('tr-TR')} hesaba aktarıldı!`);
                }
            } else if (pass !== null) {
                showToast('Hatalı şifre! (Doğru şifre: 57009)');
            }
        }

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

        function switchTab(t) { currentTab = t; showToast(`Mod: ${t}`); }
        function generateAIResponse() {
            const p = document.getElementById('ai-prompt').value;
            if(!p) { showToast('Komut yazın.'); return; }
            document.getElementById('ai-output-container').classList.remove('hidden');
            document.getElementById('ai-output-text').textContent = `[NEXUS-AI Yanıtı]: "${p}" talebiniz işlendi ve başarıyla optimize edildi.`;
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
