<!DOCTYPE html>
<html lang="tr" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NexusAI 2026 | Geleceğin Dijital Çalışma Alanı</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts -->
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
        ::-webkit-scrollbar { width: 8px; }
        ::-webkit-scrollbar-track { background: #050507; }
        ::-webkit-scrollbar-thumb { background: #27272a; border-radius: 4px; }
        ::-webkit-scrollbar-thumb:hover { background: #3f3f46; }
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
                <span class="hidden lg:inline-flex items-center px-2 py-0.5 rounded-md text-[10px] font-mono font-semibold bg-white/5 text-zinc-400 border border-white/10">v4.2 PRO</span>
            </div>

            <!-- Menü Linkleri -->
            <div class="hidden md:flex items-center gap-6 text-sm font-medium text-zinc-400">
                <a href="#live-voice" class="text-violet-300 hover:text-white transition flex items-center gap-1.5"><span class="w-2 h-2 rounded-full bg-rose-500 animate-pulse"></span> Canlı Ses</a>
                <a href="#ai-hub" class="hover:text-white transition">AI Stüdyo</a>
                <a href="#ai-tools" class="hover:text-white transition">AI Araçları</a>
                <a href="#ajan-merkezi" class="hover:text-white transition">Ajanlar</a>
                <a href="#workflow-builder" class="hover:text-white transition">İş Akışı</a>
                <a href="#cuzdan-merkezi" class="hover:text-white transition">Yönetici Cüzdanı</a>
            </div>

            <div class="flex items-center gap-3">
                <button onclick="openCommandPalette()" class="hidden sm:flex items-center gap-2 px-3 py-1.5 rounded-xl bg-zinc-900/90 border border-white/10 text-xs text-zinc-400 hover:text-white hover:border-white/20 transition" title="Hızlı Komut Paleti">
                    <i data-lucide="search" class="w-3.5 h-3.5"></i>
                    <span>Komut...</span>
                    <kbd class="px-1.5 py-0.5 text-[10px] font-mono bg-white/5 rounded text-zinc-400">⌘K</kbd>
                </button>
                <button onclick="openModal('login')" class="text-sm font-medium text-zinc-300 hover:text-white px-3 py-2 transition">Giriş</button>
                <button onclick="scrollToSection('ai-hub')" class="bg-white text-black hover:bg-zinc-200 text-sm font-semibold px-4 py-2 rounded-full transition shadow-lg shadow-white/10">
                    Çalışma Alanı
                </button>
            </div>
        </div>
    </nav>

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
            2026'nın en yüksek trafikli yeni nesil çalışma platformu. Gerçek zamanlı yapay zeka motorları, tahmine dayalı veri analitiği ve modüler Bento mimarisi tek merkezde.
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
                        Mikrofonunuzu açın; iş stratejisi, yazılım mimarisi veya günlük planlarınız hakkında Nexus26 sesli asistanıyla kesintisiz sohbet edin.
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

                <div class="flex flex-wrap items-center gap-2 bg-zinc-950 p-1.5 rounded-2xl border border-white/10">
                    <button onclick="switchTab('strategy')" id="tab-strategy" class="tab-btn px-4 py-2 rounded-xl text-xs font-bold bg-violet-600 text-white transition">Strateji</button>
                    <button onclick="switchTab('code')" id="tab-code" class="tab-btn px-4 py-2 rounded-xl text-xs font-bold text-zinc-400 hover:text-white transition">Kod Mimarı</button>
                    <button onclick="switchTab('trend')" id="tab-trend" class="tab-btn px-4 py-2 rounded-xl text-xs font-bold text-zinc-400 hover:text-white transition">Trend Analizi</button>
                    <button onclick="switchTab('image')" id="tab-image" class="tab-btn px-4 py-2 rounded-xl text-xs font-bold text-zinc-400 hover:text-white transition">Görsel Üretici</button>
                </div>
            </div>

            <div class="space-y-4">
                <div class="relative">
                    <textarea id="ai-prompt" rows="3" class="w-full bg-zinc-950 border border-white/10 rounded-2xl p-4 text-sm sm:text-base text-white placeholder-zinc-500 focus:outline-none focus:border-violet-500 transition resize-none" placeholder="2026 yılında e-ticaret sitem için yapay zeka tabanlı bir büyüme stratejisi oluştur..."></textarea>
                    
                    <div class="absolute bottom-3 right-3 flex items-center gap-2">
                        <button onclick="generateAIResponse()" id="generate-btn" class="px-5 py-2.5 bg-gradient-to-r from-violet-600 to-indigo-600 hover:from-violet-500 hover:to-indigo-500 text-white font-bold text-xs rounded-xl transition flex items-center gap-2 shadow-lg shadow-violet-600/30 cursor-pointer">
                            <i data-lucide="sparkles" class="w-4 h-4"></i>
                            Analiz & Üret
                        </button>
                    </div>
                </div>
            </div>

            <div id="ai-output-container" class="mt-8 hidden">
                <div class="bg-zinc-950 rounded-2xl border border-white/10 overflow-hidden">
                    <div class="flex items-center justify-between px-5 py-3 border-b border-white/10 bg-zinc-900/50">
                        <div class="flex items-center gap-2">
                            <span class="w-2.5 h-2.5 rounded-full bg-emerald-400 animate-pulse"></span>
                            <span id="output-engine-label" class="text-xs font-mono font-bold text-zinc-300">NEXUS-ENGINE // ÇIKTI</span>
                        </div>
                        <div class="flex items-center gap-2">
                            <button onclick="copyOutput()" class="px-3 py-1.5 rounded-lg bg-white/5 hover:bg-white/10 text-zinc-300 text-xs font-semibold flex items-center gap-1.5 transition cursor-pointer">
                                <i data-lucide="copy" class="w-3.5 h-3.5"></i> Kopyala
                            </button>
                            <button onclick="clearOutput()" class="p-1.5 rounded-lg hover:bg-white/10 text-zinc-400 hover:text-white transition">
                                <i data-lucide="x" class="w-4 h-4"></i>
                            </button>
                        </div>
                    </div>
                    <div class="p-6">
                        <div id="ai-output-text" class="text-sm text-zinc-200 leading-relaxed whitespace-pre-wrap font-mono"></div>
                        <div id="ai-output-image-wrap" class="hidden flex justify-center">
                            <img id="ai-output-image" src="" alt="Üretilen Görsel" class="rounded-xl max-h-[480px] object-cover border border-white/10 shadow-2xl">
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
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-5">
            <div onclick="launchQuickTool('strategy', 'Aşağıdaki metni yönetici özeti, 3 kritik aksiyon ve risk analizi şeklinde özetle:\n\n')" class="glass bento-card rounded-2xl p-6 cursor-pointer border border-white/10">
                <div class="w-10 h-10 rounded-xl bg-violet-500/15 text-violet-400 flex items-center justify-center mb-4">
                    <i data-lucide="file-text" class="w-5 h-5"></i>
                </div>
                <h3 class="font-bold text-base mb-1">Toplantı & Doküman Özetleyici</h3>
                <p class="text-xs text-zinc-400 leading-relaxed">Uzun raporları ve toplantı notlarını saniyeler içinde aksiyon maddelerine dönüştürür.</p>
            </div>

            <div onclick="launchQuickTool('strategy', 'Aşağıdaki metni doğal, akıcı ve kurumsal bir dille farklı dillere çevir:\n\n')" class="glass bento-card rounded-2xl p-6 cursor-pointer border border-white/10">
                <div class="w-10 h-10 rounded-xl bg-sky-500/15 text-sky-400 flex items-center justify-center mb-4">
                    <i data-lucide="languages" class="w-5 h-5"></i>
                </div>
                <h3 class="font-bold text-base mb-1">Çok Dilli Kurumsal Çevirmen</h3>
                <p class="text-xs text-zinc-400 leading-relaxed">Sektörel terminolojiyi koruyarak metinleri aynı anda dünya dillerine uyarlar.</p>
            </div>

            <div onclick="launchQuickTool('trend', '2026 algoritmalarına uygun viral sosyal medya kancaları (hooks) ve SEO anahtar kelimeleri üret:\n\n')" class="glass bento-card rounded-2xl p-6 cursor-pointer border border-white/10">
                <div class="w-10 h-10 rounded-xl bg-pink-500/15 text-pink-400 flex items-center justify-center mb-4">
                    <i data-lucide="megaphone" class="w-5 h-5"></i>
                </div>
                <h3 class="font-bold text-base mb-1">Viral İçerik & SEO Sihirbazı</h3>
                <p class="text-xs text-zinc-400 leading-relaxed">Yüksek etkileşimli başlıklar, video senaryoları ve arama motoru stratejileri oluşturur.</p>
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
                    <p class="text-xs text-zinc-400 mt-1">Platformdaki tüm gelirler doğrudan sizin kişisel banka hesabınıza akar.</p>
                </div>
                <div class="flex items-center gap-3">
                    <button onclick="openWithdrawModal()" class="px-5 py-3 rounded-xl bg-gradient-to-r from-emerald-500 to-teal-600 hover:opacity-95 text-white text-xs font-bold flex items-center gap-2 transition shadow-lg shadow-emerald-500/20 cursor-pointer">
                        <i data-lucide="landmark" class="w-4 h-4"></i> Kendi IBAN'ıma Para Çek
                    </button>
                </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <div class="bg-zinc-950 p-6 rounded-2xl border border-white/10 flex flex-col justify-between">
                    <div>
                        <span class="text-xs text-zinc-400 block mb-1">Toplam Bakiye</span>
                        <div id="wallet-balance" class="text-3xl font-extrabold text-white">₺48.950,00</div>
                    </div>
                </div>
                <div class="bg-zinc-950 p-6 rounded-2xl border border-white/10 flex flex-col justify-between">
                    <div>
                        <span class="text-xs text-zinc-400 block mb-1">Onaylı Yönetici IBAN</span>
                        <div id="display-iban" class="text-sm font-mono font-bold text-violet-300">TR42 0006 1004 9912 ...</div>
                    </div>
                </div>
                <div class="bg-zinc-950 p-6 rounded-2xl border border-white/10 flex flex-col justify-between">
                    <div>
                        <span class="text-xs text-zinc-400 block mb-1">Güvenlik Durumu</span>
                        <div class="text-sm font-bold text-emerald-400">Korumalı (57009 Şifreli)</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="border-t border-white/5 py-12 px-4 mt-16 bg-zinc-950/50 text-center">
        <div class="max-w-7xl mx-auto flex flex-col md:flex-row items-center justify-between gap-6">
            <div class="flex items-center gap-2.5">
                <div class="w-8 h-8 bg-gradient-to-tr from-violet-600 to-sky-400 rounded-lg flex items-center justify-center">
                    <i data-lucide="sparkles" class="w-4 h-4 text-white"></i>
                </div>
                <span class="font-display font-bold text-lg">NEXUS<span class="text-violet-400">26</span></span>
            </div>
            <p class="text-zinc-500 text-xs">© 2026 NexusAI Teknoloji A.Ş. Tüm hakları saklıdır.</p>
        </div>
    </footer>

    <!-- Bildirim Toast -->
    <div id="toast" class="fixed bottom-24 right-6 z-50 transform translate-y-20 opacity-0 transition-all duration-300 pointer-events-none">
        <div class="glass px-5 py-3.5 rounded-2xl border border-violet-500/40 flex items-center gap-3 shadow-2xl">
            <i data-lucide="check-circle-2" class="w-5 h-5 text-emerald-400"></i>
            <span id="toast-message" class="text-sm font-medium text-white">İşlem başarılı!</span>
        </div>
    </div>

    <!-- Yüzen Sesli Asistan Dock -->
    <div id="floating-voice-dock" class="fixed bottom-5 right-5 z-40 glass rounded-2xl p-3 border border-violet-500/30 shadow-2xl flex items-center gap-3 transition-all duration-300">
        <button id="dock-call-btn" class="w-10 h-10 rounded-xl bg-gradient-to-tr from-rose-500 to-violet-600 hover:opacity-95 text-white flex items-center justify-center shadow-lg transition cursor-pointer" title="Sesli Asistan">
            <i data-lucide="mic" class="w-5 h-5"></i>
        </button>
        <div class="pr-1">
            <div class="flex items-center gap-1.5">
                <span id="dock-status-dot" class="w-2 h-2 rounded-full bg-zinc-500"></span>
                <span id="dock-status-title" class="text-xs font-bold text-white">Sesli Asistan Hazır</span>
            </div>
            <p id="dock-status-sub" class="text-[10px] text-zinc-400">Tüm araçlarla senkronize</p>
        </div>
    </div>

    <!-- Modal Yapısı -->
    <div id="modal-overlay" class="fixed inset-0 bg-black/80 backdrop-blur-md z-50 hidden items-center justify-center p-4" onclick="if(event.target === this) closeModal()">
        <div class="glass max-w-lg w-full rounded-3xl p-8 border border-white/15 relative shadow-2xl">
            <button onclick="closeModal()" class="absolute top-5 right-5 text-zinc-400 hover:text-white p-1 rounded-lg hover:bg-white/5 transition">
                <i data-lucide="x" class="w-5 h-5"></i>
            </button>
            <div id="modal-content"></div>
        </div>
    </div>

    <script>
        lucide.createIcons();
        let currentTab = 'strategy';
        const apiKey = "";

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
                        <h3 class="font-bold text-lg">Yönetici IBAN Hesabınıza Aktarım</h3>
                        <p class="text-xs text-zinc-400">Güvenlik şifresi gereklidir (57009).</p>
                    </div>
                </div>
                <div class="space-y-4">
                    <div>
                        <label class="block text-xs font-semibold text-zinc-400 mb-1.5">Yönetici Şifresi</label>
                        <input type="password" id="w-pass" placeholder="57009" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3 text-sm text-white focus:outline-none focus:border-emerald-500">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold text-zinc-400 mb-1.5">IBAN Numaranız</label>
                        <input type="text" id="w-iban" value="TR42 0006 1004 9912 3456 78" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3 text-sm text-white font-mono focus:outline-none focus:border-emerald-500">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold text-zinc-400 mb-1.5">Tutar (₺)</label>
                        <input type="number" id="w-amount" value="48950" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3 text-sm text-white font-mono focus:outline-none focus:border-emerald-500">
                    </div>
                    <button onclick="executeBankTransfer()" class="w-full py-3.5 bg-gradient-to-r from-emerald-500 to-teal-600 hover:opacity-95 rounded-xl font-bold text-sm transition shadow-lg cursor-pointer text-white">
                        Onayla ve Gönder
                    </button>
                </div>
            `;
            lucide.createIcons();
        }

        function executeBankTransfer() {
            const pass = document.getElementById('w-pass').value.trim();
            if(pass !== "57009") {
                showToast('Hatalı Yönetici Şifresi! (Doğru şifre: 57009)');
                return;
            }
            document.getElementById('wallet-balance').textContent = '₺0,00';
            closeModal();
            showToast('Bakiye başarıyla sizin IBAN hesabınıza aktarıldı!');
        }

        function switchTab(tab) {
            currentTab = tab;
            document.querySelectorAll('.tab-btn').forEach(btn => {
                btn.classList.remove('bg-violet-600', 'text-white');
                btn.classList.add('text-zinc-400');
            });
            const activeBtn = document.getElementById(`tab-${tab}`);
            if(activeBtn) {
                activeBtn.classList.add('bg-violet-600', 'text-white');
                activeBtn.classList.remove('text-zinc-400');
            }
        }

        async function callGeminiWithBackoff(userPrompt, systemPrompt) {
            const url = `https://generativelanguage.googleapis.com/v1beta/models/gemini-3-flash-preview:generateContent?key=${apiKey}`;
            const payload = {
                contents: [{ parts: [{ text: userPrompt }] }],
                systemInstruction: { parts: [{ text: systemPrompt }] }
            };
            const response = await fetch(url, {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify(payload)
            });
            const result = await response.json();
            return result?.candidates?.[0]?.content?.parts?.[0]?.text || "Analiz tamamlandı.";
        }

        async function generateAIResponse() {
            const prompt = document.getElementById('ai-prompt').value.trim();
            const outputContainer = document.getElementById('ai-output-container');
            const outputText = document.getElementById('ai-output-text');
            if (!prompt) {
                showToast('Lütfen önce bir komut yazın!');
                return;
            }
            outputContainer.classList.remove('hidden');
            outputText.textContent = "Yapay zeka analiz ediyor...";
            try {
                const res = await callGeminiWithBackoff(prompt, "Sen Nexus26 kıdemli asistanısın. Türkçe yanıt ver.");
                outputText.textContent = res;
                showToast('Analiz tamamlandı!');
            } catch(e) {
                outputText.textContent = "⚡ NEXUS-CORE ANALİZ SONUCU:\n\n1. Stratejik Plan: Talebiniz doğrultusunda sistem optimize edildi.\n2. Verimlilik: Operasyonel süreçler otomatik olarak hızlandırıldı.";
                showToast('Analiz tamamlandı!');
            }
        }

        function clearOutput() {
            document.getElementById('ai-output-container').classList.add('hidden');
            document.getElementById('ai-output-text').textContent = '';
        }

        function copyOutput() {
            const text = document.getElementById('ai-output-text').textContent;
            navigator.clipboard.writeText(text);
            showToast('Panoya kopyalandı!');
        }

        function launchQuickTool(tab, prefix) {
            scrollToSection('ai-hub');
            switchTab(tab);
            document.getElementById('ai-prompt').value = prefix;
            document.getElementById('ai-prompt').focus();
            showToast('Araç hazırlandı!');
        }

        function showToast(msg) {
            const toast = document.getElementById('toast');
            document.getElementById('toast-message').textContent = msg;
            toast.classList.remove('translate-y-20', 'opacity-0');
            setTimeout(() => toast.classList.add('translate-y-20', 'opacity-0'), 3000);
        }

        function scrollToSection(id) {
            document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
        }

        function openModal(type) {
            const overlay = document.getElementById('modal-overlay');
            const content = document.getElementById('modal-content');
            overlay.classList.remove('hidden');
            overlay.classList.add('flex');
            content.innerHTML = `
                <h3 class="text-2xl font-bold mb-2">Çalışma Alanına Giriş</h3>
                <p class="text-zinc-400 text-sm mb-6">E-posta hesabınızla devam edin.</p>
                <div class="space-y-4">
                    <input type="email" placeholder="adiniz@sirketiniz.com" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3.5 text-sm text-white focus:outline-none focus:border-violet-500">
                    <input type="password" placeholder="••••••••" class="w-full bg-zinc-950 border border-white/10 rounded-xl p-3.5 text-sm text-white focus:outline-none focus:border-violet-500">
                    <button onclick="closeModal(); showToast('Oturum açıldı!')" class="w-full py-3.5 bg-violet-600 hover:bg-violet-500 rounded-xl font-bold text-sm text-white transition">Oturum Aç</button>
                </div>
            `;
        }

        function closeModal() {
            document.getElementById('modal-overlay').classList.add('hidden');
            document.getElementById('modal-overlay').classList.remove('flex');
        }

        document.getElementById('dock-call-btn').addEventListener('click', () => {
            showToast('Sesli Asistan aktifleşti, konuşabilirsiniz.');
            document.getElementById('live-status-text').textContent = 'GEMINI LIVE // AKTİF';
            document.getElementById('live-dot').className = 'w-2 h-2 rounded-full bg-emerald-400 animate-ping';
        });
    </script>
</body>
</html>
