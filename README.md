
```html
<!DOCTYPE html>
<html lang="ar" dir="rtl" class="dark scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>عبد الفتاح - البوابة الإسلامية الشاملة</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts: Amiri & Cairo -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Amiri:ital,wght@0,400;0,700;1,400&family=Cairo:wght@300;400;600;700;800&display=swap" rel="stylesheet">
    
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        emeraldDeep: '#081c15',
                        emeraldBase: '#0d2818',
                        emeraldPanel: '#143829',
                        emeraldHover: '#1b4a37',
                        goldAccent: '#d4af37',
                        goldLight: '#f4c430',
                        goldMuted: '#aa8c2c',
                    },
                    fontFamily: {
                        amiri: ['Amiri', 'serif'],
                        cairo: ['Cairo', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <style>
        body {
            font-family: 'Cairo', sans-serif;
            background-color: #081c15;
            color: #e2e8f0;
            background-image: radial-gradient(circle at 50% 0%, #143829 0%, #081c15 75%);
            background-attachment: fixed;
        }

        /* Subtle Islamic Geometric Pattern Overlay */
        .pattern-overlay {
            background-image: radial-gradient(rgba(212, 175, 55, 0.05) 1px, transparent 0);
            background-size: 24px 24px;
        }

        .gold-glow {
            box-shadow: 0 0 25px -5px rgba(212, 175, 55, 0.25);
        }

        .gold-border-glow {
            border-color: rgba(212, 175, 55, 0.4);
            box-shadow: inset 0 0 15px rgba(212, 175, 55, 0.1);
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #081c15;
        }
        ::-webkit-scrollbar-thumb {
            background: #143829;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #d4af37;
        }

        /* Compass needle rotate animation smooth transition */
        #compassNeedle {
            transition: transform 0.8s cubic-bezier(0.4, 0, 0.2, 1);
        }
    </style>
</head>
<body class="pattern-overlay min-h-screen flex flex-col justify-between selection:bg-goldAccent selection:text-emeraldDeep">

    <!-- Top Announcement / Bismillah Banner -->
    <div class="bg-gradient-to-r from-emeraldBase via-emeraldPanel to-emeraldBase border-b border-goldAccent/20 py-2 text-center text-goldAccent font-amiri text-lg tracking-wide shadow-md">
        بسم الله الرحمن الرحيم
    </div>

    <!-- Header & Navigation -->
    <header class="sticky top-0 z-50 backdrop-blur-md bg-emeraldDeep/85 border-b border-goldAccent/20 shadow-lg">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20">
                <!-- Brand Title -->
                <div class="flex items-center space-x-3 space-x-reverse">
                    <div class="w-11 h-11 rounded-full bg-gradient-to-tr from-goldMuted via-goldAccent to-goldLight flex items-center justify-center text-emeraldDeep font-amiri text-2xl font-bold shadow-md shadow-goldAccent/20">
                        ع
                    </div>
                    <div>
                        <a href="#" class="font-amiri text-2xl sm:text-3xl font-bold text-goldAccent tracking-tight block">
                            عبد الفتاح
                        </a>
                        <span class="text-xs text-emerald-300/60 font-light block">البوابة الإسلامية الشاملة</span>
                    </div>
                </div>

                <!-- Desktop Navigation Links -->
                <nav class="hidden md:flex space-x-1 lg:space-x-2 space-x-reverse font-medium text-sm">
                    <a href="#hero" class="px-3 py-2 rounded-lg text-goldAccent bg-emeraldPanel/60 border border-goldAccent/30 transition-all">الرئيسية</a>
                    <a href="#prayer-times" class="px-3 py-2 rounded-lg text-slate-300 hover:text-goldAccent hover:bg-emeraldPanel/40 transition-all">أوقات الصلاة</a>
                    <a href="#quran" class="px-3 py-2 rounded-lg text-slate-300 hover:text-goldAccent hover:bg-emeraldPanel/40 transition-all">القرآن الكريم</a>
                    <a href="#adhkar" class="px-3 py-2 rounded-lg text-slate-300 hover:text-goldAccent hover:bg-emeraldPanel/40 transition-all">الأذكار والسبحة</a>
                    <a href="#tools" class="px-3 py-2 rounded-lg text-slate-300 hover:text-goldAccent hover:bg-emeraldPanel/40 transition-all">القبلة والتقويم</a>
                </nav>

                <!-- Action Button & Mobile Menu Toggle -->
                <div class="flex items-center space-x-3 space-x-reverse">
                    <button onclick="scrollToAdhkar()" class="hidden sm:inline-flex items-center gap-2 bg-gradient-to-r from-goldAccent to-goldLight text-emeraldDeep font-bold px-4 py-2 rounded-xl shadow-lg hover:brightness-110 transition-all">
                        <i class="fa-solid fa-hands-praying"></i>
                        <span>السبحة الإلكترونية</span>
                    </button>
                    <!-- Mobile Menu Button -->
                    <button id="mobileMenuBtn" class="md:hidden p-2 rounded-lg text-slate-300 hover:text-goldAccent focus:outline-none">
                        <i class="fa-solid fa-bars text-2xl"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Navigation Menu -->
        <div id="mobileMenu" class="hidden md:hidden bg-emeraldPanel/95 border-b border-goldAccent/20 px-4 pt-2 pb-4 space-y-2 text-right">
            <a href="#hero" class="block px-3 py-2 rounded-md text-goldAccent font-semibold bg-emeraldDeep/50">الرئيسية</a>
            <a href="#prayer-times" class="block px-3 py-2 rounded-md text-slate-300 hover:text-goldAccent hover:bg-emeraldDeep/30">أوقات الصلاة</a>
            <a href="#quran" class="block px-3 py-2 rounded-md text-slate-300 hover:text-goldAccent hover:bg-emeraldDeep/30">القرآن الكريم</a>
            <a href="#adhkar" class="block px-3 py-2 rounded-md text-slate-300 hover:text-goldAccent hover:bg-emeraldDeep/30">الأذكار والسبحة</a>
            <a href="#tools" class="block px-3 py-2 rounded-md text-slate-300 hover:text-goldAccent hover:bg-emeraldDeep/30">القبلة والتقويم</a>
        </div>
    </header>

    <!-- Main Content Container -->
    <main class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8 space-y-12">

        <!-- 1. Hero Section & Daily Ayah -->
        <section id="hero" class="relative rounded-3xl bg-gradient-to-br from-emeraldPanel via-emeraldBase to-emeraldDeep border border-goldAccent/30 p-6 sm:p-10 gold-glow overflow-hidden">
            <!-- Background Decorative Ornament -->
            <div class="absolute -left-10 -bottom-10 opacity-10 text-goldAccent pointer-events-none">
                <i class="fa-solid fa-kaaba text-[220px]"></i>
            </div>
            
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-center relative z-10">
                <!-- Hero Left / Daily Ayah Card -->
                <div class="lg:col-span-8 space-y-6">
                    <div class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-goldAccent/10 border border-goldAccent/30 text-goldAccent text-xs font-semibold">
                        <i class="fa-solid fa-star text-xs"></i>
                        <span>آية اليوم المباركة</span>
                    </div>

                    <div class="space-y-4">
                        <p id="ayahText" class="font-amiri text-2xl sm:text-3xl md:text-4xl text-slate-100 leading-relaxed font-bold">
                            " اللَّهُ لَا إِلَٰهَ إِلَّا هُوَ الْحَيُّ الْقَيُّومُ ۚ لَا تَأْخُذُهُ سِنَةٌ وَلَا نَوْمٌ "
                        </p>
                        <p id="ayahRef" class="text-goldAccent/90 font-medium text-sm sm:text-base">
                            — سورة البقرة [الآية 255 - آية الكرسي]
                        </p>
                    </div>

                    <!-- Audio Player & Actions for Ayah -->
                    <div class="flex flex-wrap items-center gap-4 pt-2">
                        <button id="playAyahBtn" onclick="toggleAyahAudio()" class="flex items-center gap-2 bg-goldAccent hover:bg-goldLight text-emeraldDeep font-bold px-5 py-2.5 rounded-xl shadow-md transition-all">
                            <i id="playAyahIcon" class="fa-solid fa-play"></i>
                            <span id="playAyahText">استماع للآية</span>
                        </button>
                        <button onclick="copyAyahText()" class="flex items-center gap-2 bg-emeraldPanel/80 hover:bg-emeraldHover border border-goldAccent/30 text-slate-200 px-4 py-2.5 rounded-xl transition-all">
                            <i class="fa-regular fa-copy text-goldAccent"></i>
                            <span>نسخ الآية</span>
                        </button>
                        <button onclick="changeAyah()" class="flex items-center gap-2 bg-emeraldPanel/80 hover:bg-emeraldHover border border-goldAccent/30 text-slate-200 px-4 py-2.5 rounded-xl transition-all">
                            <i class="fa-solid fa-rotate text-goldAccent"></i>
                            <span>آية أخرى</span>
                        </button>
                    </div>
                </div>

                <!-- Hero Right / Quick Actions Box -->
                <div class="lg:col-span-4 bg-emeraldDeep/80 rounded-2xl p-6 border border-goldAccent/20 space-y-4 shadow-inner">
                    <h3 class="text-goldAccent font-bold text-lg border-b border-goldAccent/20 pb-2 flex items-center gap-2">
                        <i class="fa-solid fa-compass"></i>
                        <span>الوصول السريع</span>
                    </h3>
                    <div class="grid grid-cols-2 gap-3">
                        <a href="#prayer-times" class="flex flex-col items-center justify-center p-4 rounded-xl bg-emeraldPanel/60 hover:bg-emeraldHover border border-goldAccent/20 text-center transition-all group">
                            <i class="fa-solid fa-clock text-2xl text-goldAccent group-hover:scale-110 transition-transform mb-2"></i>
                            <span class="text-xs font-semibold">مواقيت الصلاة</span>
                        </a>
                        <a href="#quran" class="flex flex-col items-center justify-center p-4 rounded-xl bg-emeraldPanel/60 hover:bg-emeraldHover border border-goldAccent/20 text-center transition-all group">
                            <i class="fa-solid fa-quran text-2xl text-goldAccent group-hover:scale-110 transition-transform mb-2"></i>
                            <span class="text-xs font-semibold">القرآن الكريم</span>
                        </a>
                        <a href="#adhkar" class="flex flex-col items-center justify-center p-4 rounded-xl bg-emeraldPanel/60 hover:bg-emeraldHover border border-goldAccent/20 text-center transition-all group">
                            <i class="fa-solid fa-hands-praying text-2xl text-goldAccent group-hover:scale-110 transition-transform mb-2"></i>
                            <span class="text-xs font-semibold">الأذكار اليومية</span>
                        </a>
                        <a href="#tools" class="flex flex-col items-center justify-center p-4 rounded-xl bg-emeraldPanel/60 hover:bg-emeraldHover border border-goldAccent/20 text-center transition-all group">
                            <i class="fa-solid fa-location-arrow text-2xl text-goldAccent group-hover:scale-110 transition-transform mb-2"></i>
                            <span class="text-xs font-semibold">اتجاه القبلة</span>
                        </a>
                    </div>
                </div>
            </div>
        </section>

        <!-- 2. Interactive Prayer Times Widget -->
        <section id="prayer-times" class="space-y-6">
            <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 border-b border-goldAccent/20 pb-4">
                <div>
                    <h2 class="text-2xl sm:text-3xl font-amiri font-bold text-goldAccent flex items-center gap-2">
                        <i class="fa-solid fa-mosque"></i>
                        <span>أوقات الصلاة اليومية</span>
                    </h2>
                    <p class="text-slate-400 text-sm mt-1">المواعيد بدقة حسَب التوقيت المحلي لمدينتك</p>
                </div>
                <!-- City Selector & Current Live Clock -->
                <div class="flex items-center gap-3">
                    <div class="bg-emeraldPanel border border-goldAccent/30 px-4 py-2 rounded-xl text-xs sm:text-sm text-goldAccent flex items-center gap-2">
                        <i class="fa-solid fa-location-dot"></i>
                        <select id="citySelect" onchange="updatePrayerCity()" class="bg-transparent font-bold focus:outline-none cursor-pointer text-slate-200">
                            <option value="makkah" class="bg-emeraldDeep">مكة المكرمة</option>
                            <option value="cairo" class="bg-emeraldDeep" selected>القاهرة</option>
                            <option value="riyadh" class="bg-emeraldDeep">الرياض</option>
                            <option value="dubai" class="bg-emeraldDeep">دبي</option>
                            <option value="amman" class="bg-emeraldDeep">عَمّان</option>
                        </select>
                    </div>
                    <div class="bg-emeraldPanel border border-goldAccent/30 px-4 py-2 rounded-xl text-xs sm:text-sm font-mono text-goldAccent flex items-center gap-2">
                        <i class="fa-regular fa-clock"></i>
                        <span id="liveClock">00:00:00</span>
                    </div>
                </div>
            </div>

            <!-- Countdown Banner -->
            <div class="bg-gradient-to-r from-emeraldPanel via-emeraldHover to-emeraldPanel border border-goldAccent/40 rounded-2xl p-4 text-center flex flex-col sm:flex-row items-center justify-between gap-3 shadow-md">
                <div class="flex items-center gap-3">
                    <div class="w-10 h-10 rounded-full bg-goldAccent/20 flex items-center justify-center text-goldAccent text-lg">
                        <i class="fa-solid fa-hourglass-half"></i>
                    </div>
                    <div class="text-right">
                        <span class="text-xs text-slate-400">الصلاة القادمة:</span>
                        <h4 id="nextPrayerName" class="font-bold text-goldAccent text-base">العصر</h4>
                    </div>
                </div>
                <div class="flex items-center gap-2">
                    <span class="text-xs text-slate-300">متبقي على الأذان:</span>
                    <span id="countdownTimer" class="font-mono text-xl font-bold text-goldLight tracking-wider bg-emeraldDeep/80 px-3 py-1 rounded-lg border border-goldAccent/20">02:14:35</span>
                </div>
            </div>

            <!-- Prayer Cards Grid -->
            <div class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-6 gap-4" id="prayerCardsGrid">
                <!-- Fajr -->
                <div data-prayer="fajr" class="prayer-card bg-emeraldPanel/50 border border-goldAccent/20 rounded-2xl p-4 text-center space-y-2 transition-all hover:border-goldAccent">
                    <i class="fa-solid fa-sun-plant-wilt text-2xl text-slate-400"></i>
                    <h4 class="font-bold text-slate-200">الفجر</h4>
                    <p class="font-mono text-xl font-bold text-goldAccent">04:32 AM</p>
                </div>
                <!-- Sunrise -->
                <div data-prayer="sunrise" class="prayer-card bg-emeraldPanel/50 border border-goldAccent/20 rounded-2xl p-4 text-center space-y-2 transition-all hover:border-goldAccent">
                    <i class="fa-solid fa-sun text-2xl text-slate-400"></i>
                    <h4 class="font-bold text-slate-200">الشروق</h4>
                    <p class="font-mono text-xl font-bold text-slate-300">06:01 AM</p>
                </div>
                <!-- Dhuhr -->
                <div data-prayer="dhuhr" class="prayer-card bg-emeraldPanel/50 border border-goldAccent/20 rounded-2xl p-4 text-center space-y-2 transition-all hover:border-goldAccent">
                    <i class="fa-solid fa-sun text-2xl text-goldAccent"></i>
                    <h4 class="font-bold text-slate-200">الظهر</h4>
                    <p class="font-mono text-xl font-bold text-goldAccent">12:15 PM</p>
                </div>
                <!-- Asr (Active Highlight Example) -->
                <div data-prayer="asr" class="prayer-card bg-emeraldPanel border-2 border-goldAccent rounded-2xl p-4 text-center space-y-2 transition-all gold-glow relative">
                    <span class="absolute -top-3 left-1/2 transform -translate-x-1/2 bg-goldAccent text-emeraldDeep text-[10px] font-bold px-2 py-0.5 rounded-full">القادمة</span>
                    <i class="fa-solid fa-cloud-sun text-2xl text-goldAccent"></i>
                    <h4 class="font-bold text-goldAccent">العصر</h4>
                    <p class="font-mono text-xl font-bold text-goldLight">03:30 PM</p>
                </div>
                <!-- Maghrib -->
                <div data-prayer="maghrib" class="prayer-card bg-emeraldPanel/50 border border-goldAccent/20 rounded-2xl p-4 text-center space-y-2 transition-all hover:border-goldAccent">
                    <i class="fa-solid fa-moon text-2xl text-slate-400"></i>
                    <h4 class="font-bold text-slate-200">المغرب</h4>
                    <p class="font-mono text-xl font-bold text-goldAccent">06:28 PM</p>
                </div>
                <!-- Isha -->
                <div data-prayer="isha" class="prayer-card bg-emeraldPanel/50 border border-goldAccent/20 rounded-2xl p-4 text-center space-y-2 transition-all hover:border-goldAccent">
                    <i class="fa-regular fa-moon text-2xl text-slate-400"></i>
                    <h4 class="font-bold text-slate-200">العشاء</h4>
                    <p class="font-mono text-xl font-bold text-goldAccent">07:58 PM</p>
                </div>
            </div>
        </section>

        <!-- 3. Holy Quran & Audio Player Preview Section -->
        <section id="quran" class="space-y-6">
            <div class="border-b border-goldAccent/20 pb-4">
                <h2 class="text-2xl sm:text-3xl font-amiri font-bold text-goldAccent flex items-center gap-2">
                    <i class="fa-solid fa-quran"></i>
                    <span>القرآن الكريم والتلاوات</span>
                </h2>
                <p class="text-slate-400 text-sm mt-1">اختر السورة للاستماع بقارئك المفضل</p>
            </div>

            <!-- Surah Audio Player Card -->
            <div class="bg-gradient-to-r from-emeraldPanel to-emeraldDeep border border-goldAccent/30 rounded-2xl p-6 shadow-xl space-y-6">
                <!-- Player Header / Currently Playing Info -->
                <div class="flex flex-col md:flex-row items-center justify-between gap-4">
                    <div class="flex items-center gap-4">
                        <div class="w-14 h-14 rounded-2xl bg-goldAccent/20 border border-goldAccent/40 flex items-center justify-center text-goldAccent text-2xl">
                            <i class="fa-solid fa-book-open text-goldAccent"></i>
                        </div>
                        <div>
                            <h3 id="currentSurahTitle" class="font-amiri text-2xl font-bold text-goldAccent">سورة الفاتحة</h3>
                            <p id="currentReciter" class="text-xs text-slate-400">القارئ: الشيخ مشاري العفاسي</p>
                        </div>
                    </div>
                    <!-- Audio Bar Controls -->
                    <div class="w-full md:w-1/2 space-y-2">
                        <div class="flex items-center justify-between text-xs font-mono text-slate-400">
                            <span id="audioCurrentTime">00:00</span>
                            <span id="audioDuration">01:45</span>
                        </div>
                        <input id="audioSeekBar" type="range" min="0" max="100" value="0" class="w-full h-1.5 bg-emeraldDeep rounded-lg appearance-none cursor-pointer accent-goldAccent">
                        <div class="flex items-center justify-center gap-6 pt-2">
                            <button onclick="prevSurah()" class="text-slate-400 hover:text-goldAccent transition-colors text-xl">
                                <i class="fa-solid fa-backward-step"></i>
                            </button>
                            <button id="mainPlayBtn" onclick="toggleAudio()" class="w-12 h-12 rounded-full bg-goldAccent hover:bg-goldLight text-emeraldDeep flex items-center justify-center text-xl font-bold shadow-lg transition-all">
                                <i id="mainPlayIcon" class="fa-solid fa-play"></i>
                            </button>
                            <button onclick="nextSurah()" class="text-slate-400 hover:text-goldAccent transition-colors text-xl">
                                <i class="fa-solid fa-forward-step"></i>
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Surahs Cards Grid -->
                <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 gap-4 pt-4 border-t border-goldAccent/10">
                    <!-- Surah 1 -->
                    <div onclick="selectSurah('سورة الفاتحة', 'الشيخ مشاري العفاسي', '01:45')" class="surah-card p-4 rounded-xl bg-emeraldDeep/80 border border-goldAccent/20 hover:border-goldAccent cursor-pointer transition-all flex items-center justify-between group">
                        <div class="flex items-center gap-3">
                            <span class="w-8 h-8 rounded-lg bg-emeraldPanel text-goldAccent text-xs font-bold flex items-center justify-center border border-goldAccent/20">١</span>
                            <div>
                                <h4 class="font-bold text-slate-200 group-hover:text-goldAccent transition-colors">الفاتحة</h4>
                                <span class="text-[11px] text-slate-400">مكية - ٧ آيات</span>
                            </div>
                        </div>
                        <i class="fa-regular fa-circle-play text-goldAccent/60 group-hover:text-goldAccent text-xl transition-colors"></i>
                    </div>

                    <!-- Surah 2 -->
                    <div onclick="selectSurah('سورة يس', 'الشيخ عبد الباسط عبد الصمد', '22:10')" class="surah-card p-4 rounded-xl bg-emeraldDeep/80 border border-goldAccent/20 hover:border-goldAccent cursor-pointer transition-all flex items-center justify-between group">
                        <div class="flex items-center gap-3">
                            <span class="w-8 h-8 rounded-lg bg-emeraldPanel text-goldAccent text-xs font-bold flex items-center justify-center border border-goldAccent/20">٣٦</span>
                            <div>
                                <h4 class="font-bold text-slate-200 group-hover:text-goldAccent transition-colors">يس</h4>
                                <span class="text-[11px] text-slate-400">مكية - ٨٣ آية</span>
                            </div>
                        </div>
                        <i class="fa-regular fa-circle-play text-goldAccent/60 group-hover:text-goldAccent text-xl transition-colors"></i>
                    </div>

                    <!-- Surah 3 -->
                    <div onclick="selectSurah('سورة الكهف', 'الشيخ ماهر المعيقلي', '35:40')" class="surah-card p-4 rounded-xl bg-emeraldDeep/80 border border-goldAccent/20 hover:border-goldAccent cursor-pointer transition-all flex items-center justify-between group">
                        <div class="flex items-center gap-3">
                            <span class="w-8 h-8 rounded-lg bg-emeraldPanel text-goldAccent text-xs font-bold flex items-center justify-center border border-goldAccent/20">١٨</span>
                            <div>
                                <h4 class="font-bold text-slate-200 group-hover:text-goldAccent transition-colors">الكهف</h4>
                                <span class="text-[11px] text-slate-400">مكية - ١١٠ آية</span>
                            </div>
                        </div>
                        <i class="fa-regular fa-circle-play text-goldAccent/60 group-hover:text-goldAccent text-xl transition-colors"></i>
                    </div>

                    <!-- Surah 4 -->
                    <div onclick="selectSurah('سورة الملك', 'الشيخ سعد الغامدي', '08:15')" class="surah-card p-4 rounded-xl bg-emeraldDeep/80 border border-goldAccent/20 hover:border-goldAccent cursor-pointer transition-all flex items-center justify-between group">
                        <div class="flex items-center gap-3">
                            <span class="w-8 h-8 rounded-lg bg-emeraldPanel text-goldAccent text-xs font-bold flex items-center justify-center border border-goldAccent/20">٦٧</span>
                            <div>
                                <h4 class="font-bold text-slate-200 group-hover:text-goldAccent transition-colors">الملك</h4>
                                <span class="text-[11px] text-slate-400">مكية - ٣٠ آية</span>
                            </div>
                        </div>
                        <i class="fa-regular fa-circle-play text-goldAccent/60 group-hover:text-goldAccent text-xl transition-colors"></i>
                    </div>
                </div>
            </div>
        </section>

        <!-- 4. Interactive Daily Adhkar & Digital Tasbeeh Counter Widget -->
        <section id="adhkar" class="grid grid-cols-1 lg:grid-cols-12 gap-8">
            
            <!-- Digital Tasbeeh Counter Component (5 cols) -->
            <div class="lg:col-span-5 bg-gradient-to-b from-emeraldPanel to-emeraldDeep border border-goldAccent/30 rounded-3xl p-6 sm:p-8 flex flex-col items-center justify-between shadow-2xl relative gold-border-glow">
                <div class="w-full flex items-center justify-between border-b border-goldAccent/20 pb-3">
                    <h3 class="font-amiri text-xl font-bold text-goldAccent flex items-center gap-2">
                        <i class="fa-solid fa-hands-praying"></i>
                        <span>السبحة الإلكترونية</span>
                    </h3>
                    <button onclick="resetTasbeeh()" class="text-xs text-red-400 hover:text-red-300 flex items-center gap-1 border border-red-500/30 px-2 py-1 rounded-lg">
                        <i class="fa-solid fa-rotate-right"></i>
                        <span>تصفير</span>
                    </button>
                </div>

                <!-- Dhikr Category Selector -->
                <div class="my-4 w-full text-center">
                    <select id="dhikrSelect" onchange="changeDhikr()" class="w-full bg-emeraldDeep border border-goldAccent/30 rounded-xl px-4 py-2 text-goldAccent font-bold text-center text-sm focus:outline-none">
                        <option value="سبحان الله">سبحان الله</option>
                        <option value="الحمد لله">الحمد لله</option>
                        <option value="لا إله إلا الله">لا إله إلا الله</option>
                        <option value="الله أكبر">الله أكبر</option>
                        <option value="أستغفر الله واتوب إليه">أستغفر الله وأتوب إليه</option>
                        <option value="اللهم صل وسلم على نبينا محمد">الصلاة على النبي ﷺ</option>
                    </select>
                </div>

                <!-- Counter Digital Screen -->
                <div class="my-6 w-full bg-emeraldDeep/95 border-2 border-goldAccent/40 rounded-2xl p-6 text-center space-y-2 shadow-inner">
                    <span id="dhikrDisplay" class="font-amiri text-2xl font-bold text-goldLight block">سبحان الله</span>
                    <div id="tasbeehCount" class="font-mono text-5xl sm:text-6xl font-extrabold text-goldAccent tracking-widest my-2">0</div>
                    <span class="text-xs text-slate-400 block">اضغط على الزر الكبير للتسبيح</span>
                </div>

                <!-- Main Tap Button -->
                <button id="tasbeehBtn" onclick="incrementTasbeeh()" class="w-32 h-32 rounded-full bg-gradient-to-tr from-goldMuted via-goldAccent to-goldLight text-emeraldDeep text-2xl font-bold shadow-2xl flex items-center justify-center transform active:scale-95 transition-all cursor-pointer border-4 border-emeraldDeep hover:brightness-110">
                    <span class="text-base font-bold">تسبيح</span>
                </button>
            </div>

            <!-- Rotating Daily Adhkar Cards (7 cols) -->
            <div class="lg:col-span-7 space-y-6">
                <div class="border-b border-goldAccent/20 pb-4 flex items-center justify-between">
                    <div>
                        <h2 class="text-2xl font-amiri font-bold text-goldAccent flex items-center gap-2">
                            <i class="fa-solid fa-book-bookmark"></i>
                            <span>أذكار اليوم والليلة</span>
                        </h2>
                        <p class="text-slate-400 text-sm mt-1">حصن المسلم من أذكار الصباح والمساء</p>
                    </div>
                    <!-- Adhkar Tab Controls -->
                    <div class="flex gap-2 bg-emeraldDeep p-1 rounded-xl border border-goldAccent/20 text-xs">
                        <button id="morningTab" onclick="switchAdhkarTab('morning')" class="px-3 py-1.5 rounded-lg font-bold bg-goldAccent text-emeraldDeep transition-all">الصباح</button>
                        <button id="eveningTab" onclick="switchAdhkarTab('evening')" class="px-3 py-1.5 rounded-lg font-bold text-slate-300 hover:text-goldAccent transition-all">المساء</button>
                    </div>
                </div>

                <!-- Morning Adhkar Cards Container -->
                <div id="adhkarContainer" class="space-y-4 max-h-[380px] overflow-y-auto pr-2">
                    <!-- Morning Dhikr 1 -->
                    <div class="bg-emeraldPanel/60 border border-goldAccent/20 rounded-2xl p-5 space-y-3">
                        <p class="font-amiri text-lg text-slate-100 leading-relaxed font-semibold">
                            "أصبحنا وأصبح الملك لله، والحمد لله، لا إله إلا الله وحده لا شريك له، له الملك وله الحمد وهو على كل شيء قدير."
                        </p>
                        <div class="flex items-center justify-between text-xs text-goldAccent border-t border-goldAccent/10 pt-2">
                            <span>التكرار: مرة واحدة</span>
                            <button onclick="copyText(this)" class="hover:text-goldLight transition-colors flex items-center gap-1">
                                <i class="fa-regular fa-copy"></i>
                                <span>نسخ</span>
                            </button>
                        </div>
                    </div>

                    <!-- Morning Dhikr 2 -->
                    <div class="bg-emeraldPanel/60 border border-goldAccent/20 rounded-2xl p-5 space-y-3">
                        <p class="font-amiri text-lg text-slate-100 leading-relaxed font-semibold">
                            "رضيت بالله رباً، وبالإسلام ديناً، وبمحمد صلى الله عليه وسلم نبياً ورسولاً."
                        </p>
                        <div class="flex items-center justify-between text-xs text-goldAccent border-t border-goldAccent/10 pt-2">
                            <span>التكرار: 3 مرات</span>
                            <button onclick="copyText(this)" class="hover:text-goldLight transition-colors flex items-center gap-1">
                                <i class="fa-regular fa-copy"></i>
                                <span>نسخ</span>
                            </button>
                        </div>
                    </div>

                    <!-- Morning Dhikr 3 -->
                    <div class="bg-emeraldPanel/60 border border-goldAccent/20 rounded-2xl p-5 space-y-3">
                        <p class="font-amiri text-lg text-slate-100 leading-relaxed font-semibold">
                            "اللهم بك أصبحنا، وبك أمسينا، وبك نحيا، وبك نموت، وإليك النشور."
                        </p>
                        <div class="flex items-center justify-between text-xs text-goldAccent border-t border-goldAccent/10 pt-2">
                            <span>التكرار: مرة واحدة</span>
                            <button onclick="copyText(this)" class="hover:text-goldLight transition-colors flex items-center gap-1">
                                <i class="fa-regular fa-copy"></i>
                                <span>نسخ</span>
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 5. Qibla Finder & Hijri Calendar Display Section -->
        <section id="tools" class="grid grid-cols-1 md:grid-cols-2 gap-8">
            
            <!-- Qibla Finder Interactive Widget -->
            <div class="bg-gradient-to-br from-emeraldPanel to-emeraldDeep border border-goldAccent/30 rounded-3xl p-6 space-y-6">
                <div class="border-b border-goldAccent/20 pb-3 flex items-center justify-between">
                    <h3 class="font-amiri text-xl font-bold text-goldAccent flex items-center gap-2">
                        <i class="fa-solid fa-compass"></i>
                        <span>بوصلة اتجاه القبلة</span>
                    </h3>
                    <span class="text-xs bg-goldAccent/10 text-goldAccent border border-goldAccent/30 px-2.5 py-1 rounded-full">محاكاة تفاعلية</span>
                </div>

                <!-- Compass Graphic -->
                <div class="relative w-48 h-48 sm:w-56 sm:h-56 mx-auto rounded-full bg-emeraldDeep border-4 border-goldAccent/40 flex items-center justify-center shadow-xl">
                    <!-- Degrees Markers -->
                    <span class="absolute top-2 text-xs font-mono text-goldAccent">N (0°)</span>
                    <span class="absolute bottom-2 text-xs font-mono text-slate-400">S (180°)</span>
                    <span class="absolute right-2 text-xs font-mono text-slate-400">E (90°)</span>
                    <span class="absolute left-2 text-xs font-mono text-slate-400">W (270°)</span>

                    <!-- Kaaba Icon Indicator at Qibla Angle -->
                    <div class="absolute top-6 left-12 text-goldAccent text-lg">
                        <i class="fa-solid fa-kaaba"></i>
                    </div>

                    <!-- Rotating Compass Needle -->
                    <div id="compassNeedle" class="w-full h-full relative flex items-center justify-center transform rotate-45">
                        <div class="w-1.5 h-24 bg-gradient-to-t from-red-500 to-goldAccent rounded-full shadow-lg"></div>
                        <div class="w-4 h-4 bg-goldAccent rounded-full border-2 border-emeraldDeep absolute"></div>
                    </div>
                </div>

                <div class="text-center space-y-2">
                    <p class="text-sm text-slate-300">اتجاه القبلة بالنسبة لموقعك الحالي: <span class="text-goldAccent font-bold">135° SE</span></p>
                    <button onclick="rotateCompass()" class="bg-emeraldPanel hover:bg-emeraldHover border border-goldAccent/30 text-goldAccent text-xs font-bold px-4 py-2 rounded-xl transition-all inline-flex items-center gap-2">
                        <i class="fa-solid fa-rotate-right"></i>
                        <span>تحديث الاتجاه</span>
                    </button>
                </div>
            </div>

            <!-- Hijri & Gregorian Calendar Widget -->
            <div class="bg-gradient-to-br from-emeraldPanel to-emeraldDeep border border-goldAccent/30 rounded-3xl p-6 space-y-6">
                <div class="border-b border-goldAccent/20 pb-3 flex items-center justify-between">
                    <h3 class="font-amiri text-xl font-bold text-goldAccent flex items-center gap-2">
                        <i class="fa-solid fa-calendar-days"></i>
                        <span>التقويم الهجري والميلادي</span>
                    </h3>
                    <span id="hijriMonthBadge" class="text-xs bg-goldAccent/10 text-goldAccent border border-goldAccent/30 px-2.5 py-1 rounded-full">جمادى الأولى</span>
                </div>

                <!-- Calendar Display Card -->
                <div class="bg-emeraldDeep/80 rounded-2xl p-6 border border-goldAccent/20 text-center space-y-4">
                    <!-- Hijri Date Big -->
                    <div class="space-y-1">
                        <span class="text-xs text-slate-400">التاريخ الهجري اليوم</span>
                        <h4 id="hijriFullDate" class="font-amiri text-3xl font-bold text-goldAccent">
                            15 جمادى الأولى 1448 هـ
                        </h4>
                    </div>
                    <hr class="border-goldAccent/10">
                    <!-- Gregorian Date -->
                    <div class="space-y-1">
                        <span class="text-xs text-slate-400">التاريخ الميلادي المقابل</span>
                        <p id="gregorianFullDate" class="font-semibold text-slate-200 text-lg">
                            6 نوفمبر 2026 م
                        </p>
                    </div>
                </div>

                <!-- Islamic Occasion Highlight Banner -->
                <div class="bg-emeraldPanel/80 border border-goldAccent/20 rounded-2xl p-4 flex items-center gap-3">
                    <div class="w-10 h-10 rounded-xl bg-goldAccent/20 text-goldAccent flex items-center justify-center text-xl flex-shrink-0">
                        <i class="fa-solid fa-moon"></i>
                    </div>
                    <div class="text-xs space-y-0.5">
                        <span class="text-goldAccent font-bold">المناسبة القادمة:</span>
                        <p class="text-slate-300">شهر رمضان المبارك (متبقي حوالي 4 أشهر)</p>
                    </div>
                </div>
            </div>

        </section>

    </main>

    <!-- Footer -->
    <footer class="bg-emeraldDeep border-t border-goldAccent/20 mt-16 py-8 text-center text-slate-400 text-sm space-y-4">
        <div class="max-w-7xl mx-auto px-4 flex flex-col sm:flex-row items-center justify-between gap-4">
            <!-- Brand & Info -->
            <div class="flex items-center space-x-2 space-x-reverse">
                <span class="font-amiri text-xl font-bold text-goldAccent">عبد الفتاح</span>
                <span class="text-xs text-slate-500">| البوابة الإسلامية</span>
            </div>

            <!-- Islamic Quote -->
            <p class="font-amiri text-goldAccent/80 text-base">
                "وَاذْكُر رَّبَّكَ كَثِيرًا وَسَبِّحْ بِالْعَشِيِّ وَالْإِبْكَارِ"
            </p>

            <!-- Copyright -->
            <div class="text-xs text-slate-500">
                جميع الحقوق محفوظة &copy; 2026 موقع عبد الفتاح الإسلامي
            </div>
        </div>
    </footer>

    <!-- JavaScript Logic -->
    <script>
        // --- 1. Mobile Menu Toggle ---
        const mobileMenuBtn = document.getElementById('mobileMenuBtn');
        const mobileMenu = document.getElementById('mobileMenu');

        mobileMenuBtn.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
        });

        // --- 2. Dynamic Live Clock ---
        function updateClock() {
            const now = new Date();
            const hours = String(now.getHours()).padStart(2, '0');
            const minutes = String(now.getMinutes()).padStart(2, '0');
            const seconds = String(now.getSeconds()).padStart(2, '0');
            document.getElementById('liveClock').textContent = `${hours}:${minutes}:${seconds}`;
        }
        setInterval(updateClock, 1000);
        updateClock();

        // --- 3. Digital Tasbeeh Counter Logic ---
        let count = 0;
        const countDisplay = document.getElementById('tasbeehCount');
        const dhikrSelect = document.getElementById('dhikrSelect');
        const dhikrDisplay = document.getElementById('dhikrDisplay');

        function incrementTasbeeh() {
            count++;
            countDisplay.textContent = count;
            // Visual bounce feedback
            countDisplay.classList.add('scale-110');
            setTimeout(() => countDisplay.classList.remove('scale-110'), 150);
        }

        function resetTasbeeh() {
            count = 0;
            countDisplay.textContent = '0';
        }

        function changeDhikr() {
            dhikrDisplay.textContent = dhikrSelect.value;
            resetTasbeeh();
        }

        function scrollToAdhkar() {
            document.getElementById('adhkar').scrollIntoView({ behavior: 'smooth' });
        }

        // --- 4. Quran Ayah Rotation & Copy ---
        const ayahs = [
            { text: '" اللَّهُ لَا إِلَٰهَ إِلَّا هُوَ الْحَيُّ الْقَيُّومُ ۚ لَا تَأْخُذُهُ سِنَةٌ وَلَا نَوْمٌ "', ref: '— سورة البقرة [الآية 255 - آية الكرسي]' },
            { text: '" إِنَّ مَعَ الْعُسْرِ يُسْرًا "', ref: '— سورة الشرح [الآية 6]' },
            { text: '" وَرَبُّكَ فَكَبِّرْ "', ref: '— سورة المدثر [الآية 3]' },
            { text: '" أَلَا بِذِكْرِ اللَّهِ تَطْمَئِنُّ الْقُلُوبُ "', ref: '— سورة الرعد [الآية 28]' }
        ];
        let currentAyahIdx = 0;

        function changeAyah() {
            currentAyahIdx = (currentAyahIdx + 1) % ayahs.length;
            document.getElementById('ayahText').textContent = ayahs[currentAyahIdx].text;
            document.getElementById('ayahRef').textContent = ayahs[currentAyahIdx].ref;
        }

        function copyAyahText() {
            const textToCopy = `${document.getElementById('ayahText').textContent} ${document.getElementById('ayahRef').textContent}`;
            navigator.clipboard.writeText(textToCopy);
            alert('تم نسخ الآية الكريمة بنجاح!');
        }

        // Ayah audio toggle simulation
        let isAyahPlaying = false;
        function toggleAyahAudio() {
            isAyahPlaying = !isAyahPlaying;
            const icon = document.getElementById('playAyahIcon');
            const text = document.getElementById('playAyahText');
            if(isAyahPlaying) {
                icon.className = 'fa-solid fa-pause';
                text.textContent = 'إيقاف الاستماع';
            } else {
                icon.className = 'fa-solid fa-play';
                text.textContent = 'استماع للآية';
            }
        }

        // --- 5. Quran Audio Surah Player Simulation ---
        let isPlaying = false;
        function toggleAudio() {
            isPlaying = !isPlaying;
            const icon = document.getElementById('mainPlayIcon');
            if(isPlaying) {
                icon.className = 'fa-solid fa-pause';
            } else {
                icon.className = 'fa-solid fa-play';
            }
        }

        function selectSurah(name, reciter, duration) {
            document.getElementById('currentSurahTitle').textContent = name;
            document.getElementById('currentReciter').textContent = `القارئ: ${reciter}`;
            document.getElementById('audioDuration').textContent = duration;
            document.getElementById('audioCurrentTime').textContent = '00:00';
            document.getElementById('audioSeekBar').value = 0;
            isPlaying = false;
            toggleAudio();
        }

        function nextSurah() {
            selectSurah('سورة يس', 'الشيخ عبد الباسط عبد الصمد', '22:10');
        }

        function prevSurah() {
            selectSurah('سورة الفاتحة', 'الشيخ مشاري العفاسي', '01:45');
        }

        // --- 6. Morning / Evening Adhkar Tab Switcher ---
        const morningAdhkar = [
            { text: '"أصبحنا وأصبح الملك لله، والحمد لله، لا إله إلا الله وحده لا شريك له، له الملك وله الحمد وهو على كل شيء قدير."', count: 'مرة واحدة' },
            { text: '"رضيت بالله رباً، وبالإسلام ديناً، وبمحمد صلى الله عليه وسلم نبياً ورسولاً."', count: '3 مرات' },
            { text: '"اللهم بك أصبحنا، وبك أمسينا، وبك نحيا، وبك نموت، وإليك النشور."', count: 'مرة واحدة' }
        ];

        const eveningAdhkar = [
            { text: '"أمسينَا وأمسَى الملكُ لله والحمدُ لله، لا إلهَ إلاّ اللهُ وحدَهُ لا شَريكَ لهُ، لهُ المُلْكُ ولهُ الحَمْدُ، وهُوَ على كُلّ شَيءٍ قديرٌ."', count: 'مرة واحدة' },
            { text: '"اللّهُمَّ بِكَ أَمْسَيْنَا وَبِكَ أَصْبَحْنَا وَبِكَ نَحْيَا وَبِكَ نَمُوتُ وَإِلَيْكَ الْمَصِيرُ."', count: 'مرة واحدة' },
            { text: '"أعوذ بكلمات الله التامات من شر ما خلق."', count: '3 مرات' }
        ];

        function switchAdhkarTab(type) {
            const container = document.getElementById('adhkarContainer');
            const morningBtn = document.getElementById('morningTab');
            const eveningBtn = document.getElementById('eveningTab');

            if(type === 'morning') {
                morningBtn.className = 'px-3 py-1.5 rounded-lg font-bold bg-goldAccent text-emeraldDeep transition-all';
                eveningBtn.className = 'px-3 py-1.5 rounded-lg font-bold text-slate-300 hover:text-goldAccent transition-all';
                renderAdhkar(morningAdhkar);
            } else {
                eveningBtn.className = 'px-3 py-1.5 rounded-lg font-bold bg-goldAccent text-emeraldDeep transition-all';
                morningBtn.className = 'px-3 py-1.5 rounded-lg font-bold text-slate-300 hover:text-goldAccent transition-all';
                renderAdhkar(eveningAdhkar);
            }
        }

        function renderAdhkar(list) {
            const container = document.getElementById('adhkarContainer');
            container.innerHTML = list.map(item => `
                <div class="bg-emeraldPanel/60 border border-goldAccent/20 rounded-2xl p-5 space-y-3">
                    <p class="font-amiri text-lg text-slate-100 leading-relaxed font-semibold">${item.text}</p>
                    <div class="flex items-center justify-between text-xs text-goldAccent border-t border-goldAccent/10 pt-2">
                        <span>التكرار: ${item.count}</span>
                        <button onclick="copyText(this)" class="hover:text-goldLight transition-colors flex items-center gap-1">
                            <i class="fa-regular fa-copy"></i>
                            <span>نسخ</span>
                        </button>
                    </div>
                </div>
            `).join('');
        }

        function copyText(btn) {
            const card = btn.closest('div').parentElement;
            const text = card.querySelector('p').textContent;
            navigator.clipboard.writeText(text);
            alert('تم نسخ الذكر بنجاح!');
        }

        // --- 7. Qibla Needle Rotation simulation ---
        let currentRotation = 45;
        function rotateCompass() {
            currentRotation += 90;
            document.getElementById('compassNeedle').style.transform = `rotate(${currentRotation}deg)`;
        }

        // --- 8. City Prayer Times Switcher Simulation ---
        const cityPrayerTimes = {
            cairo: { fajr: '04:32 AM', sunrise: '06:01 AM', dhuhr: '12:15 PM', asr: '03:30 PM', maghrib: '06:28 PM', isha: '07:58 PM' },
            makkah: { fajr: '05:02 AM', sunrise: '06:22 AM', dhuhr: '12:24 PM', asr: '03:45 PM', maghrib: '06:25 PM', isha: '07:55 PM' },
            riyadh: { fajr: '04:40 AM', sunrise: '06:00 AM', dhuhr: '11:50 AM', asr: '03:12 PM', maghrib: '05:40 PM', isha: '07:10 PM' },
            dubai: { fajr: '05:10 AM', sunrise: '06:30 AM', dhuhr: '12:20 PM', asr: '03:40 PM', maghrib: '06:10 PM', isha: '07:40 PM' },
            amman: { fajr: '04:45 AM', sunrise: '06:12 AM', dhuhr: '12:18 PM', asr: '03:25 PM', maghrib: '06:22 PM', isha: '07:52 PM' }
        };

        function updatePrayerCity() {
            const selectedCity = document.getElementById('citySelect').value;
            const times = cityPrayerTimes[selectedCity];
            
            const grid = document.getElementById('prayerCardsGrid');
            const cards = grid.querySelectorAll('.prayer-card');
            
            cards[0].querySelector('p').textContent = times.fajr;
            cards[1].querySelector('p').textContent = times.sunrise;
            cards[2].querySelector('p').textContent = times.dhuhr;
            cards[3].querySelector('p').textContent = times.asr;
            cards[4].querySelector('p').textContent = times.maghrib;
            cards[5].querySelector('p').textContent = times.isha;
        }
    </script>
</body>
</html>
```
