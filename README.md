<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title id="pageTitle">Günlük Yaşam Dil Pratiği v1.1</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f4f7f6;
            margin: 0;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            box-sizing: border-box;
        }
        .card {
            background: white;
            padding: 25px;
            border-radius: 16px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.08);
            width: 100%;
            max-width: 520px;
            box-sizing: border-box;
            position: relative;
            padding-bottom: 75px;
        }
        .screen {
            display: none;
        }
        .screen.active {
            display: block;
        }
        .top-info-bar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 12px;
        }
        .lang-flags-container {
            display: flex;
            gap: 10px;
        }
        .streak-badge {
            background: #fff7ed;
            border: 1px solid #ffedd5;
            color: #c2410c;
            padding: 4px 10px;
            border-radius: 20px;
            font-size: 13px;
            font-weight: bold;
            display: flex;
            align-items: center;
            gap: 4px;
        }
        .flag-btn {
            background: transparent;
            border: 2px solid #cbd5e1;
            border-radius: 8px;
            padding: 4px 10px;
            font-size: 18px;
            cursor: pointer;
            transition: all 0.2s ease;
        }
        .flag-btn:hover {
            border-color: #007bff;
            background-color: #f8fafc;
        }
        .flag-btn.active-flag {
            border-color: #007bff;
            background-color: #e2e8f0;
        }
        .top-bar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }
        .lives {
            font-size: 18px;
            font-weight: bold;
            color: #e74c3c;
        }
        .back-btn {
            background: #f1f5f9;
            border: 1px solid #cbd5e1;
            padding: 8px 14px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 13px;
            font-weight: 600;
            color: #475569;
        }
        select {
            padding: 14px;
            font-size: 16px;
            border-radius: 8px;
            border: 2px solid #cbd5e1;
            width: 100%;
            cursor: pointer;
            background-color: #f8fafc;
            color: #1e293b;
            margin-bottom: 15px;
            box-sizing: border-box;
        }
        h1 {
            color: #2c3e50;
            font-size: 22px;
            text-align: center;
            margin-top: 5px;
            margin-bottom: 10px;
        }
        p.desc {
            color: #666;
            font-size: 14px;
            text-align: center;
            margin-bottom: 25px;
            line-height: 1.5;
        }
        .start-btn {
            background-color: #007bff;
            color: white;
            border: none;
            padding: 16px;
            font-size: 17px;
            font-weight: bold;
            border-radius: 8px;
            cursor: pointer;
            width: 100%;
            text-align: center;
            display: block;
            margin-bottom: 10px;
        }
        .errors-btn {
            background-color: #6c757d;
            color: white;
            border: none;
            padding: 14px;
            font-size: 16px;
            font-weight: bold;
            border-radius: 8px;
            cursor: pointer;
            width: 100%;
            text-align: center;
            display: block;
            margin-bottom: 10px;
        }
        .shop-btn {
            background-color: #8b5cf6;
            color: white;
            border: none;
            padding: 14px;
            font-size: 16px;
            font-weight: bold;
            border-radius: 8px;
            cursor: pointer;
            width: 100%;
            text-align: center;
            display: block;
        }
        .refill-box {
            background-color: #fff3cd;
            border: 1px solid #ffeeba;
            color: #856404;
            padding: 15px;
            border-radius: 8px;
            text-align: center;
            margin-top: 20px;
            display: none;
        }
        .refill-btn {
            background-color: #ffc107;
            color: #212529;
            border: none;
            padding: 10px 15px;
            font-size: 14px;
            font-weight: bold;
            border-radius: 6px;
            cursor: pointer;
            margin-top: 10px;
        }
        .quiz-container {
            margin-top: 15px;
        }
        .question-title {
            font-weight: bold;
            color: #2c3e50;
            font-size: 15px;
            margin-bottom: 15px;
            background: #f8f9fa;
            padding: 14px;
            border-radius: 8px;
            border-left: 4px solid #007bff;
            line-height: 1.4;
        }
        .options-list {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        .option-btn {
            background-color: #fff;
            border: 1px solid #cbd5e1;
            padding: 14px 15px;
            text-align: left;
            border-radius: 8px;
            font-size: 15px;
            color: #334155;
            cursor: pointer;
        }
        .option-btn.correct {
            background-color: #d4edda !important;
            border-color: #c3e6cb !important;
            color: #155724;
            font-weight: 600;
        }
        .option-btn.wrong {
            background-color: #f8d7da !important;
            border-color: #f5c6cb !important;
            color: #721c24;
            font-weight: 600;
        }
        .feedback-msg {
            text-align: center;
            font-weight: bold;
            font-size: 14px;
            margin-top: 15px;
            min-height: 20px;
        }
        .score-box {
            text-align: center;
            font-size: 18px;
            font-weight: bold;
            color: #28a745;
            margin-top: 20px;
        }
        .next-btn {
            margin-top: 15px;
            background-color: #007bff;
            color: white;
            border: none;
            padding: 14px 20px;
            font-size: 16px;
            font-weight: 600;
            border-radius: 8px;
            cursor: pointer;
            width: 100%;
            display: none;
        }
        .error-item {
            background: #f8fafc;
            border: 1px solid #e2e8f0;
            padding: 12px;
            border-radius: 8px;
            margin-bottom: 12px;
        }
        .error-q {
            font-weight: bold;
            color: #1e293b;
            font-size: 14px;
            margin-bottom: 6px;
        }
        .error-ans {
            color: #155724;
            font-size: 13px;
            background: #d4edda;
            padding: 6px 10px;
            border-radius: 6px;
        }
        /* Sol alttaki 8 köşeli mavi yıldızlı tıklanabilir buton */
        .sparkle-widget-btn {
            position: absolute;
            bottom: 15px;
            left: 15px;
            background: #eff6ff;
            border: 2px solid #3b82f6;
            border-radius: 10px;
            padding: 6px 12px;
            display: flex;
            align-items: center;
            gap: 6px;
            font-size: 13px;
            font-weight: bold;
            color: #1e40af;
            cursor: pointer;
            box-shadow: 0 4px 6px rgba(0,0,0,0.05);
            transition: all 0.2s ease;
        }
        .sparkle-widget-btn:hover {
            background-color: #dbeafe;
            border-color: #2563eb;
        }
        .eight-point-star {
            font-size: 18px;
            line-height: 1;
        }
    </style>
</head>
<body>

    <div class="card">
        <!-- ANA EKRAN -->
        <div id="homeScreen" class="screen active">
            <div class="top-info-bar">
                <div class="lang-flags-container">
                    <button type="button" id="trFlagBtn" class="flag-btn active-flag" onclick="setAppLanguage('tr')" title="Türkçe">🇹🇷</button>
                    <button type="button" id="enFlagBtn" class="flag-btn" onclick="setAppLanguage('en')" title="English">🇬🇧</button>
                </div>
                <div id="streakBadge" class="streak-badge">🔥 0 Gün</div>
            </div>

            <h1 id="mainTitle">🌍 Günlük Yaşam Dil Pratiği</h1>
            <p id="mainDesc" class="desc">Yetkinlik temelli yaklaşım ve günlük hayatta karşılaşılabilecek senaryolara dayalı dinamik testi çözmeye başla!</p>
            
            <select id="languageSelector">
                <option value="en">English (İngilizce)</option>
                <option value="es">Español (İspanyolca)</option>
                <option value="de">Deutsch (Almanca)</option>
                <option value="fr">Français (Fransızca)</option>
                <option value="it">Italiano (İtalyanca)</option>
                <option value="ru">Русский (Rusça)</option>
                <option value="ko">한국어 (Korece)</option>
                <option value="ja">日本語 (Japonca)</option>
            </select>

            <button type="button" id="startQuizBtnText" class="start-btn" onclick="startQuiz()">Derse / Teste Başla</button>
            <button type="button" id="errorsBtnText" class="errors-btn" onclick="openErrorsScreen()">❌ Hatalarım</button>
            <button type="button" id="shopBtnText" class="shop-btn" onclick="openShopScreen()">📚 Mağaza & Ödüller</button>

            <div id="refillBox" class="refill-box">
                <p id="refillMsgTitle" style="margin: 0 0 5px 0; font-weight: bold;">Canın bittiği için yeni oyuna başlayamazsın!</p>
                <button type="button" id="refillBtnText" class="refill-btn" onclick="startLifeLessons()">3 Can Dersi Yap (Canları Yenile)</button>
            </div>
            
            <!-- Sol alttaki 8 köşeli mavi yıldızlı tıklanabilir market butonu -->
            <button type="button" class="sparkle-widget-btn" onclick="openShopScreen()" title="Mağazaya Git">
                <span class="eight-point-star">✴️</span>
                <span id="sparkleCountText">0 Kıvılcım</span>
            </button>
        </div>

        <!-- TEST EKRANI -->
        <div id="quizScreen" class="screen">
            <div class="top-bar">
                <button type="button" id="backMenuBtn" class="back-btn" onclick="goHome()">⬅ Menü</button>
                <div id="livesDisplay" class="lives">❤️❤️❤️</div>
            </div>

            <h1 id="heading">Test</h1>
            <p id="description" class="desc">Aşağıdaki günlük yaşam senaryosuna uygun ifadeyi seçiniz.</p>

            <div id="quizContainer" class="quiz-container"></div>
            <div id="feedbackMsg" class="feedback-msg"></div>
            
            <button type="button" id="nextBtn" class="next-btn" onclick="nextQuestion()">Sonraki Soru</button>
            <div id="scoreBox" class="score-box"></div>
        </div>

        <!-- HATALAR EKRANI -->
        <div id="errorsScreen" class="screen">
            <div class="top-bar">
                <button type="button" id="errorBackBtn" class="back-btn" onclick="goHome()">⬅ Menü</button>
            </div>
            <h1 id="errorHeaderTitle" style="color: #e74c3c;">❌ Yanlış Yapılan Sorular</h1>
            <p id="errorHeaderDesc" class="desc">Testler sırasında yanlış yaptığın soruların doğru yanıtları:</p>
            
            <div id="errorsContainer" style="max-height: 350px; overflow-y: auto;"></div>
        </div>

        <!-- MAĞAZA EKRANI -->
        <div id="shopScreen" class="screen">
            <div class="top-bar">
                <button type="button" id="shopBackBtn" class="back-btn" onclick="goHome()">⬅ Menü</button>
            </div>
            <h1 id="shopHeading" style="color: #8b5cf6;">📚 Mağaza & Ödüller</h1>
            <p id="shopDesc" class="desc">7 günlük serileri tamamlayarak **10 Kitap** kazanabilir, **20 Kitap** ile **Seri Kıvılcımı** satın alabilirsin!</p>
            
            <div style="background: #f8fafc; border: 1px solid #e2e8f0; padding: 15px; border-radius: 8px; margin-bottom: 15px; text-align: center;">
                <p style="margin: 0 0 8px 0; font-weight: bold; color: #334155;" id="myBooksText">Sahip Olunan Kitaplar: 0 📖</p>
                <p style="margin: 0; font-size: 13px; color: #64748b;" id="streakProgressText">7 Günlük Seri İlerlemesi: 0/7 Gün</p>
            </div>

            <button type="button" id="buySparkleBtn" class="start-btn" style="background-color: #8b5cf6;" onclick="buySparkle()">20 Kitap Karşılığı Seri Kıvılcımı Satın Al ✴️</button>
            <div id="shopFeedback" class="feedback-msg"></div>
        </div>

        <!-- CAN DERSİ EKRANI -->
        <div id="lifeLessonScreen" class="screen">
            <h1 style="color: #d97706;" id="lessonHeading">💡 Can Dersi (1/3)</h1>
            <p id="lessonDescText" class="desc">3 canını tamamen geri kazanmak için sırayla 3 pekiştirme sorusunu doğru yanıtla!</p>

            <div class="quiz-container">
                <div class="question-title" id="lessonTitle">Günlük Yaşam Pratiği: ...</div>
                <div class="options-list" id="lessonOptions"></div>
            </div>
            <div id="lessonFeedback" class="feedback-msg"></div>
        </div>
    </div>

    <script>
        // Veri Saklama ve Seri Kontrolü (Meta AI Önerisiyle Kıvılcım Koruma Entegre Edildi)
        let userStreak = parseInt(localStorage.getItem("userStreak")) || 0;
        let lastQuizDate = localStorage.getItem("lastQuizDate") || "";
        let userBooks = parseInt(localStorage.getItem("userBooks")) || 0;
        let userSparkles = parseInt(localStorage.getItem("userSparkles")) || 0;
        let streakClaimedToday = localStorage.getItem("streakClaimedToday") === "true";

        function checkStreakOnLoad() {
            const todayStr = new Date().toDateString();
            if (lastQuizDate && lastQuizDate !== todayStr) {
                const yesterday = new Date();
                yesterday.setDate(yesterday.getDate() - 1);
                if (lastQuizDate !== yesterday.toDateString()) {
                    // Seri Kıvılcımı Kontrolü (Seriyi Kurtarma)
                    if (userSparkles > 0) {
                        userSparkles--;
                        localStorage.setItem("userSparkles", userSparkles);
                        alert("1 gün girmedin ama Seri Kıvılcımı seni kurtardı! 🔥✴️");
                        userStreak++; // Seri devam eder
                    } else {
                        userStreak = 0; // Kıvılcım yoksa seri maalesef sıfırlanır
                    }
                    streakClaimedToday = false;
                    localStorage.setItem("userStreak", userStreak);
                    localStorage.setItem("streakClaimedToday", "false");
                }
            }
        }
        checkStreakOnLoad();

        const uiTexts = {
            tr: {
                pageTitle: "Günlük Yaşam Dil Pratiği",
                mainTitle: "🌍 Günlük Yaşam Dil Pratiği",
                mainDesc: "Yetkinlik temelli yaklaşım ve günlük hayatta karşılaşılabilecek senaryolara dayalı dinamik testi çözmeye başla!",
                startBtn: "Derse / Teste Başla",
                errorsBtn: "❌ Hatalarım",
                shopBtn: "📚 Mağaza & Ödüller",
                refillMsg: "Canın bittiği için yeni oyuna başlayamazsın!",
                refillBtn: "3 Can Dersi Yap (Canları Yenile)",
                backMenu: "⬅ Menü",
                quizDefaultDesc: "Aşağıdaki günlük yaşam senaryosuna uygun ifadeyi seçiniz.",
                nextBtn: "Sonraki Soru",
                errorHeaderTitle: "❌ Yanlış Yapılan Sorular",
                errorHeaderDesc: "Testler sırasında yanlış yaptığın soruların doğru yanıtları:",
                noErrors: "Henüz kaydedilmiş bir hatan yok. Harika gidiyorsun!",
                correctAnswerText: "Doğru Cevap",
                lessonDesc: "3 canını tamamen geri kazanmak için sırayla 3 pekiştirme sorusunu doğru yanıtla!",
                lessonPrefix: "💡 Can Dersi",
                correctMsg: "Harika, doğru cevap!",
                wrongFirstMsg: "Yanlış! İstersen tekrar deneyelim.",
                wrongSecondMsg: "Üzgünüm, 1 canın gitti!",
                outOfLivesMsg: "Canın bitti! Ana menüye dönülüyor...",
                gameOver: "Tebrikler! Test bitti. Puanın:",
                blockedPlayAlert: "Canın bittiği için şu an oynayamazsın! Lütfen '3 Can Dersi Yap' butonuna basarak dersleri tamamla.",
                questionLabel: "Soru",
                shopHeading: "📚 Mağaza & Ödüller",
                shopDesc: "7 günlük serileri tamamlayarak **10 Kitap** kazanabilir, **20 Kitap** ile **Seri Kıvılcımı** satın alabilirsin!",
                buySparkleBtnText: "20 Kitap Karşılığı Seri Kıvılcımı Satın Al ✴️",
                streakBadgeText: (s) => `🔥 ${s} Gün`,
                sparkleText: (sp) => `${sp} Kıvılcım`,
                booksText: (b) => `Sahip Olunan Kitaplar: ${b} 📖`,
                streakProgress: (s) => `7 Günlük Seri İlerlemesi: ${s % 7}/7 Gün`,
                streakRewardMsg: "🎉 Tebrikler! 7 günlük seriyi tamamladın ve 10 Kitap ödülü kazandın!",
                notEnoughBooks: "Yeterli kitabın yok! Seri Kıvılcımı almak için 20 kitaba ihtiyacın var.",
                boughtSuccess: "Başarıyla 1 Seri Kıvılcımı satın aldın! ✴️",
                quizTitles: {
                    en: "English - Daily Life Scenarios",
                    es: "Español - Daily Life Scenarios",
                    de: "Deutsch - Daily Life Scenarios",
                    fr: "Français - Daily Life Scenarios",
                    it: "Italiano - Daily Life Scenarios",
                    ru: "Русский - Daily Life Scenarios",
                    ko: "한국어 - Daily Life Scenarios",
                    ja: "日本語 - Daily Life Scenarios"
                }
            },
            en: {
                pageTitle: "Daily Life Language Practice",
                mainTitle: "🌍 Daily Life Language Practice",
                mainDesc: "Start solving the dynamic test based on a competency-based approach and real-life scenarios!",
                startBtn: "Start Lesson / Quiz",
                errorsBtn: "❌ My Mistakes",
                shopBtn: "📚 Shop & Rewards",
                refillMsg: "You cannot start a new game because you are out of lives!",
                refillBtn: "Take 3 Life Lessons (Refill Lives)",
                backMenu: "⬅ Menu",
                quizDefaultDesc: "Choose the appropriate expression for the daily life scenario below.",
                nextBtn: "Next Question",
                errorHeaderTitle: "❌ Incorrectly Answered Questions",
                errorHeaderDesc: "Correct answers to the questions you got wrong during tests:",
                noErrors: "You have no saved mistakes yet. You're doing great!",
                correctAnswerText: "Correct Answer",
                lessonDesc: "Answer 3 reinforcement questions correctly in a row to fully recover your 3 lives!",
                lessonPrefix: "💡 Life Lesson",
                correctMsg: "Great, correct answer!",
                wrongFirstMsg: "Incorrect! Let's try again if you want.",
                wrongSecondMsg: "Sorry, you lost 1 life!",
                outOfLivesMsg: "Out of lives! Returning to the main menu...",
                gameOver: "Congratulations! Quiz finished. Your score:",
                blockedPlayAlert: "You cannot play right now because you are out of lives! Please click 'Take 3 Life Lessons' to complete the lessons.",
                questionLabel: "Question",
                shopHeading: "📚 Shop & Rewards",
                shopDesc: "Complete 7-day streaks to earn **10 Books**, and use **20 Books** to buy a **Streak Sparkle**!",
                buySparkleBtnText: "Buy Streak Sparkle for 20 Books ✴️",
                streakBadgeText: (s) => `🔥 ${s} Days`,
                sparkleText: (sp) => `${sp} Sparkles`,
                booksText: (b) => `Owned Books: ${b} 📖`,
                streakProgress: (s) => `7-Day Streak Progress: ${s % 7}/7 Days`,
                streakRewardMsg: "🎉 Congratulations! You completed a 7-day streak and earned 10 Books reward!",
                notEnoughBooks: "You don't have enough books! You need 20 books to buy a Streak Sparkle.",
                boughtSuccess: "Successfully bought 1 Streak Sparkle! ✴️",
                quizTitles: {
                    en: "English - Daily Life Scenarios",
                    es: "Spanish - Daily Life Scenarios",
                    de: "German - Daily Life Scenarios",
                    fr: "French - Daily Life Scenarios",
                    it: "Italian - Daily Life Scenarios",
                    ru: "Russian - Daily Life Scenarios",
                    ko: "Korean - Daily Life Scenarios",
                    ja: "Japanese - Daily Life Scenarios"
                }
            }
        };

        let appLang = "tr";

        function setAppLanguage(lang) {
            appLang = lang;
            const t = uiTexts[lang];

            if (lang === 'tr') {
                document.getElementById("trFlagBtn").classList.add("active-flag");
                document.getElementById("enFlagBtn").classList.remove("active-flag");
            } else {
                document.getElementById("enFlagBtn").classList.add("active-flag");
                document.getElementById("trFlagBtn").classList.remove("active-flag");
            }

            document.getElementById("pageTitle").innerText = t.pageTitle;
            document.getElementById("mainTitle").innerText = t.mainTitle;
            document.getElementById("mainDesc").innerText = t.mainDesc;
            document.getElementById("startQuizBtnText").innerText = t.startBtn;
            document.getElementById("errorsBtnText").innerText = t.errorsBtn;
            document.getElementById("shopBtnText").innerText = t.shopBtn;
            document.getElementById("refillMsgTitle").innerText = t.refillMsg;
            document.getElementById("refillBtnText").innerText = t.refillBtn;
            document.getElementById("backMenu").innerText = t.backMenu;
            document.getElementById("errorBackBtn").innerText = t.backMenu;
            document.getElementById("shopBackBtn").innerText = t.backMenu;
            document.getElementById("description").innerText = t.quizDefaultDesc;
            document.getElementById("nextBtn").innerText = t.nextBtn;
            document.getElementById("errorHeaderTitle").innerText = t.errorHeaderTitle;
            document.getElementById("errorHeaderDesc").innerText = t.errorHeaderDesc;
            document.getElementById("shopHeading").innerText = t.shopHeading;
            document.getElementById("shopDesc").innerHTML = t.shopDesc;
            document.getElementById("buySparkleBtn").innerText = t.buySparkleBtnText;

            updateHomeWidgets();

            const currentSelectedLang = document.getElementById("languageSelector").value;
            if (document.getElementById("quizScreen").classList.contains("active")) {
                document.getElementById("heading").innerText = rawQuizData[currentSelectedLang].heading[appLang];
            }
        }

        function updateHomeWidgets() {
            const t = uiTexts[appLang];
            document.getElementById("streakBadge").innerText = t.streakBadgeText(userStreak);
            document.getElementById("sparkleCountText").innerText = t.sparkleText(userSparkles);
        }

        const rawQuizData = {
            en: {
                heading: { tr: "English - Günlük Yaşam Senaryoları", en: "English - Daily Life Scenarios" },
                questions: [
                    { 
                        q: { tr: "Yabancı bir şehirde metro istasyonunu arıyorsunuz ve yoldan geçen birine sormanız gerekiyor. Ne dersiniz?", en: "You are looking for a subway station in a foreign city and need to ask a passerby. What do you say?" }, 
                        options: ["Where is the nearest subway station?", "What time is it?", "How much is this book?", "I am hungry."], correct: 0 
                    },
                    { 
                        q: { tr: "Bir kafede garson masanıza geldi ve siparişinizi vermenizi bekliyor. Kahve istediğinizi nasıl belirtirsiniz?", en: "A waiter came to your table at a café and is waiting for your order. How do you specify that you want coffee?" }, 
                        options: ["I want to pay the bill.", "Can I have a cup of coffee, please?", "Where is the restroom?", "Open the window."], correct: 1 
                    },
                    { 
                        q: { tr: "Mağazada beğendiğiniz bir tişörtün fiyatını öğrenmek istiyorsunuz. Kasiyere ne sormalısınız?", en: "You want to know the price of a t-shirt you liked in a store. What should you ask the cashier?" }, 
                        options: ["Do you speak English?", "How much does this t-shirt cost?", "What is your name?", "Where are you from?"], correct: 1 
                    },
                    { 
                        q: { tr: "Havaalanında pasaport kontrolünde görevli sizden pasaportunuzu istiyor. Bu durumu anlatan en doğru ifade hangisidir?", en: "At the airport passport control, the officer asks for your passport. Which is the most accurate expression describing this?" }, 
                        options: ["Show me your ticket.", "Here is my passport.", "I lost my luggage.", "The plane is delayed."], correct: 1 
                    },
                    { 
                        q: { tr: "Arkadaşınız size harika bir haber verdi ve çok mutlu oldunuz. Ona karşılık olarak ne söylersiniz?", en: "Your friend gave you wonderful news and you became very happy. What do you say in response?" }, 
                        options: ["I am very sorry.", "That's wonderful news!", "I don't know.", "See you tomorrow."], correct: 1 
                    },
                    { 
                        q: { tr: "Otele giriş yapıyorsunuz ve resepsiyonist odanızın anahtarını veriyor. Ona teşekkür etmek için ne dersiniz?", en: "You are checking into a hotel and the receptionist is giving you your room key. What do you say to thank them?" }, 
                        options: ["Goodbye", "Thank you, have a nice day.", "Excuse me", "Nice to meet you too."], correct: 1 
                    },
                    { 
                        q: { tr: "Market alışverişi yaparken aradığınız sütün nerede olduğunu bulamadınız. Görevliye nasıl sormalısınız?", en: "While shopping at the supermarket, you couldn't find where the milk you are looking for is. How should you ask the staff?" }, 
                        options: ["Where can I find the milk?", "Do you like milk?", "Is the market open?", "Can I help you?"], correct: 0 
                    },
                    { 
                        q: { tr: "Yolda yürürken yanlışlıkla birinin ayağına bastınız. Karşı taraftan hemen nasıl özür dilersiniz?", en: "While walking on the street, you accidentally stepped on someone's foot. How do you immediately apologize to the other person?" }, 
                        options: ["Thank you very much.", "I'm sorry / Excuse me.", "You are welcome.", "Good afternoon."], correct: 1 
                    },
                    { 
                        q: { tr: "Restoranda yemeğinizi yediniz ve hesabı istiyorsunuz. Garsona ne demelisiniz?", en: "You had your meal at a restaurant and want the bill. What should you tell the waiter?" }, 
                        options: ["The bill, please.", "More water, please.", "The food is cold.", "Where is the chef?"], correct: 0 
                    },
                    { 
                        q: { tr: "Toplantıya geç kaldınız ve içeri girerken özür dilemeniz gerekiyor. Ne dersiniz?", en: "You are late for the meeting and need to apologize while entering. What do you say?" }, 
                        options: ["Sorry I am late.", "See you later.", "Have a nice day.", "Good morning."], correct: 0 
                    }
                ]
            },
            es: {
                heading: { tr: "Español - Günlük Yaşam Senaryoları", en: "Spanish - Daily Life Scenarios" },
                questions: [
                    { 
                        q: { tr: "Şehir merkezinde metro istasyonunu arıyorsunuz. İspanyolca nasıl sorarsınız?", en: "You are looking for the subway station in the city center. How do you ask in Spanish?" }, 
                        options: ["¿Dónde está la estación de metro más cercana?", "¿Qué hora es?", "¿Cuánto cuesta?", "Tengo hambre."], correct: 0 
                    },
                    { 
                        q: { tr: "Bir kafede kahve sipariş etmek istiyorsunuz. Garsona ne söylersiniz?", en: "You want to order coffee in a café. What do you say to the waiter?" }, 
                        options: ["Quiero pagar.", "Un café, por favor.", "¿Dónde está el baño?", "Abra la ventana."], correct: 1 
                    }
                ]
            },
            de: {
                heading: { tr: "Deutsch - Günlük Yaşam Senaryoları", en: "German - Daily Life Scenarios" },
                questions: [
                    { 
                        q: { tr: "Trenden indiniz ve metro istasyonunu arıyorsunuz:", en: "You got off the train and are looking for the metro station:" }, 
                        options: ["Wo ist die nächste U-Bahn-Station?", "Wie spät ist es?", "Was kostet das?", "Ich habe Hunger."], correct: 0 
                    }
                ]
            },
            fr: {
                heading: { tr: "Français - Günlük Yaşam Senaryoları", en: "French - Daily Life Scenarios" },
                questions: [
                    { 
                        q: { tr: "Şehirde metro istasyonunu sormak istiyorsunuz:", en: "You want to ask for the metro station in the city:" }, 
                        options: ["Où est la station de métro la plus proche ?", "Quelle heure est-il ?", "C'est combien ?", "J'ai faim."], correct: 0 
                    }
                ]
            },
            it: {
                heading: { tr: "Italiano - Günlük Yaşam Senaryoları", en: "Italian - Daily Life Scenarios" },
                questions: [
                    { 
                        q: { tr: "Roma'da metro istasyonunu arıyorsunuz. İtalyanca nasıl sorarsınız?", en: "You are looking for the metro station in Rome. How do you ask in Italian?" }, 
                        options: ["Dov'è la stazione della metropolitana più vicina?", "Che ora è?", "Quanto costa?", "Ho fame."], correct: 0 
                    }
                ]
            },
            ru: {
                heading: { tr: "Русский - Günlük Yaşam Senaryoları", en: "Russian - Daily Life Scenarios" },
                questions: [
                    { 
                        q: { tr: "В незнакомом городе вы ищете станцию метро. Как спросить прохожего?", en: "In an unfamiliar city, you are looking for a metro station. How do you ask a passerby?" }, 
                        options: ["Где ближайшая станция метро?", "Сколько времени?", "Сколько это стоит?", "Я хочу есть."], correct: 0 
                    }
                ]
            },
            ko: {
                heading: { tr: "한국어 - Günlük Yaşam Senaryoları", en: "Korean - Daily Life Scenarios" },
                questions: [
                    { 
                        q: { tr: "지하철역을 찾고 있습니다. 길에서 물어볼 때 어떻게 말하나요?", en: "You are looking for a subway station. How do you ask on the street?" }, 
                        options: ["가장 가까운 지하철역이 어디에 있나요?", "지금 몇 시예요?", "이것은 얼마예요?", "배고파요."], correct: 0 
                    }
                ]
            },
            ja: {
                heading: { tr: "日本語 - Günlük Yaşam Senaryoları", en: "Japanese - Daily Life Scenarios" },
                questions: [
                    { 
                        q: { tr: "見知らぬ街で地下鉄の駅を探しています。道行く人にどう尋ねますか？", en: "You are looking for a subway station in an unfamiliar town. How do you ask a passerby?" }, 
                        options: ["一番近い地下鉄の駅はどこですか？", "何時ですか？", "これはいくらですか？", "お腹が空きました。"], correct: 0 
                    }
                ]
            }
        };

        const lifeLessonPool = [
            {
                q: { tr: "Günlük Yaşam Pratiği: Sabah insanları selamlamak için hangisi kullanılır?", en: "Daily Life Practice: Which one is used to greet people in the morning?" },
                options: ["Good night", "Good morning", "Goodbye"],
                correct: 1
            },
            {
                q: { tr: "Günlük Yaşam Pratiği: Birine teşekkür ederken hangisini söylersiniz?", en: "Daily Life Practice: Which one do you say when thanking someone?" },
                options: ["Thank you", "I am sorry", "Excuse me"],
                correct: 0
            },
            {
                q: { tr: "Günlük Yaşam Pratiği: Ayrılırken veya veda ederken hangisi söylenir?", en: "Daily Life Practice: Which one is said when leaving or saying goodbye?" },
                options: ["Hello", "Good morning", "Goodbye"],
                correct: 2
            }
        ];

        let currentLang = "en";
        let activeQuestions = [];
        let currentIndex = 0;
        let score = 0;
        let lives = 3;
        let wrongAttemptsOnCurrentQuestion = 0;
        let userErrors = [];
        let currentLesson = null;
        let currentLessonStep = 1;

        function shuffleArray(array) {
            let arr = [...array];
            for (let i = arr.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [arr[i], arr[j]] = [arr[j], arr[i]];
            }
            return arr;
        }

        function updateLivesDisplay() {
            let hearts = "";
            for (let i = 0; i < lives; i++) {
                hearts += "❤️";
            }
            document.getElementById("livesDisplay").innerText = hearts;
        }

        function updateMenuState() {
            const refillBox = document.getElementById("refillBox");
            if (lives <= 0) {
                refillBox.style.display = "block";
            } else {
                refillBox.style.display = "none";
            }
            updateHomeWidgets();
        }

        function handleStreakAfterCompletion() {
            const todayStr = new Date().toDateString();
            if (lastQuizDate !== todayStr) {
                if (!streakClaimedToday) {
                    userStreak++;
                    // Her 7 günde bir 10 kitap ver
                    if (userStreak > 0 && userStreak % 7 === 0) {
                        userBooks += 10;
                        alert(uiTexts[appLang].streakRewardMsg);
                    }
                    streakClaimedToday = true;
                }
                lastQuizDate = todayStr;
                localStorage.setItem("userStreak", userStreak);
                localStorage.setItem("lastQuizDate", lastQuizDate);
                localStorage.setItem("userBooks", userBooks);
                localStorage.setItem("streakClaimedToday", streakClaimedToday);
            }
        }

        function startQuiz() {
            if (lives <= 0) {
                alert(uiTexts[appLang].blockedPlayAlert);
                return;
            }

            currentLang = document.getElementById("languageSelector").value;
            currentIndex = 0;
            score = 0;
            wrongAttemptsOnCurrentQuestion = 0;

            const allPool = rawQuizData[currentLang].questions;
            const shuffledPool = shuffleArray(allPool);
            const selectedPool = shuffledPool.slice(0, 10);

            activeQuestions = selectedPool.map(item => {
                let indexedOptions = item.options.map((opt, idx) => ({ text: opt, isCorrect: idx === item.correct }));
                let shuffledOptions = shuffleArray(indexedOptions);
                let newCorrectIndex = shuffledOptions.findIndex(o => o.isCorrect);

                return {
                    q: item.q,
                    options: shuffledOptions.map(o => o.text),
                    correct: newCorrectIndex
                };
            });

            document.getElementById("heading").innerText = rawQuizData[currentLang].heading[appLang];
            document.getElementById("scoreBox").innerText = "";
            document.getElementById("nextBtn").style.display = "none";
            updateLivesDisplay();

            document.querySelectorAll(".screen").forEach(s => s.classList.remove("active"));
            document.getElementById("quizScreen").classList.add("active");

            loadQuestion();
        }

        function goHome() {
            document.querySelectorAll(".screen").forEach(s => s.classList.remove("active"));
            document.getElementById("homeScreen").classList.add("active");
            updateMenuState();
        }

        function openErrorsScreen() {
            document.querySelectorAll(".screen").forEach(s => s.classList.remove("active"));
            document.getElementById("errorsScreen").classList.add("active");

            const t = uiTexts[appLang];
            const container = document.getElementById("errorsContainer");
            if (userErrors.length === 0) {
                container.innerHTML = `<p style="text-align: center; color: #666; font-style: italic;">${t.noErrors}</p>`;
            } else {
                container.innerHTML = userErrors.map(err => `
                    <div class="error-item">
                        <div class="error-q">❓ ${err.question[appLang]}</div>
                        <div class="error-ans">✅ ${t.correctAnswerText}: ${err.correctAnswer}</div>
                    </div>
                `).join('');
            }
        }

        function openShopScreen() {
            document.querySelectorAll(".screen").forEach(s => s.classList.remove("active"));
            document.getElementById("shopScreen").classList.add("active");
            
            const t = uiTexts[appLang];
            document.getElementById("myBooksText").innerText = t.booksText(userBooks);
            document.getElementById("streakProgressText").innerText = t.streakProgress(userStreak);
            document.getElementById("shopFeedback").innerText = "";
        }

        function buySparkle() {
            const t = uiTexts[appLang];
            const feedback = document.getElementById("shopFeedback");

            if (userBooks >= 20) {
                userBooks -= 20;
                userSparkles++;
                localStorage.setItem("userBooks", userBooks);
                localStorage.setItem("userSparkles", userSparkles);

                document.getElementById("myBooksText").innerText = t.booksText(userBooks);
                document.getElementById("streakProgressText").innerText = t.streakProgress(userStreak);
                updateHomeWidgets();

                feedback.style.color = "#28a745";
                feedback.innerText = t.boughtSuccess;
            } else {
                feedback.style.color = "#e74c3c";
                feedback.innerText = t.notEnoughBooks;
            }
        }

        function startLifeLessons() {
            currentLessonStep = 1;
            loadNextLessonStep();
        }

        function loadNextLessonStep() {
            document.querySelectorAll(".screen").forEach(s => s.classList.remove("active"));
            document.getElementById("lifeLessonScreen").classList.add("active");
            
            const t = uiTexts[appLang];
            document.getElementById("lessonHeading").innerText = `${t.lessonPrefix} (${currentLessonStep}/3)`;
            document.getElementById("lessonDescText").innerText = t.lessonDesc;
            document.getElementById("lessonFeedback").innerText = "";

            const randomIndex = Math.floor(Math.random() * lifeLessonPool.length);
            const originalLesson = lifeLessonPool[randomIndex];

            let indexedOptions = originalLesson.options.map((opt, idx) => ({ text: opt, isCorrect: idx === originalLesson.correct }));
            let shuffledOptions = shuffleArray(indexedOptions);
            let newCorrectIndex = shuffledOptions.findIndex(o => o.isCorrect);

            currentLesson = {
                q: originalLesson.q,
                options: shuffledOptions.map(o => o.text),
                correct: newCorrectIndex
            };

            document.getElementById("lessonTitle").innerText = currentLesson.q[appLang];
            
            const optionsContainer = document.getElementById("lessonOptions");
            optionsContainer.innerHTML = currentLesson.options.map((opt, idx) => `
                <button type="button" class="option-btn" onclick="checkLessonAnswer(${idx})">${opt}</button>
            `).join('');
        }

        function checkLessonAnswer(selectedIndex) {
            const btns = document.querySelectorAll("#lessonOptions .option-btn");
            const feedback = document.getElementById("lessonFeedback");
            const correctIndex = currentLesson.correct;

            btns.forEach(b => b.disabled = true);

            if (selectedIndex === correctIndex) {
                btns[selectedIndex].classList.add("correct");
                feedback.style.color = "#28a745";

                if (currentLessonStep < 3) {
                    feedback.innerText = appLang === 'tr' ? `Doğru! ${currentLessonStep}. ders tamamlandı. Sonraki derse geçiliyor...` : `Correct! Lesson ${currentLessonStep} completed. Moving to next lesson...`;
                    currentLessonStep++;
                    setTimeout(loadNextLessonStep, 1800);
                } else {
                    feedback.innerText = appLang === 'tr' ? "Tebrikler! 3 dersi de başarıyla tamamladın ve 3 can kazandın!" : "Congratulations! You successfully completed all 3 lessons and earned 3 lives!";
                    lives = 3;
                    setTimeout(goHome, 2000);
                }
            } else {
                btns[selectedIndex].classList.add("wrong");
                btns[correctIndex].classList.add("correct");
                feedback.style.color = "#e74c3c";
                feedback.innerText = appLang === 'tr' ? "Yanlış cevap! Bu ders adımı baştan denenecek..." : "Wrong answer! This lesson step will be retried...";
                setTimeout(loadNextLessonStep, 2200);
            }
        }

        function loadQuestion() {
            wrongAttemptsOnCurrentQuestion = 0;
            document.getElementById("feedbackMsg").innerText = "";
            document.getElementById("nextBtn").style.display = "none";

            const data = activeQuestions[currentIndex];
            const container = document.getElementById("quizContainer");
            const t = uiTexts[appLang];
            const qPrefix = t.questionLabel;

            container.innerHTML = `
                <div class="question-title">${qPrefix} ${currentIndex + 1}/${activeQuestions.length}: ${data.q[appLang]}</div>
                <div class="options-list">
                    ${data.options.map((opt, index) => `
                        <button type="button" class="option-btn" onclick="checkAnswer(${index})">${opt}</button>
                    `).join('')}
                </div>
            `;
        }

        function checkAnswer(selectedOptionIndex) {
            const data = activeQuestions[currentIndex];
            const buttons = document.querySelectorAll(".option-btn");
            const feedbackMsg = document.getElementById("feedbackMsg");
            const t = uiTexts[appLang];

            if (selectedOptionIndex === data.correct) {
                buttons[selectedOptionIndex].classList.add("correct");
                buttons.forEach(btn => btn.disabled = true);
                feedbackMsg.style.color = "#28a745";
                feedbackMsg.innerText = t.correctMsg;
                score++;
                checkGameFlow();
            } else {
                wrongAttemptsOnCurrentQuestion++;

                if (wrongAttemptsOnCurrentQuestion === 1) {
                    buttons[selectedOptionIndex].classList.add("wrong");
                    buttons[selectedOptionIndex].disabled = true;
                    feedbackMsg.style.color = "#e67e22";
                    feedbackMsg.innerText = t.wrongFirstMsg;
                } else {
                    buttons[selectedOptionIndex].classList.add("wrong");
                    buttons[data.correct].classList.add("correct");
                    buttons.forEach(btn => btn.disabled = true);
                    
                    if (!userErrors.some(e => e.question.tr === data.q.tr)) {
                        userErrors.push({
                            question: data.q,
                            correctAnswer: data.options[data.correct]
                        });
                    }

                    lives--;
                    updateLivesDisplay();

                    feedbackMsg.style.color = "#e74c3c";
                    if (lives > 0) {
                        feedbackMsg.innerText = t.wrongSecondMsg;
                        checkGameFlow();
                    } else {
                        feedbackMsg.innerText = t.outOfLivesMsg;
                        setTimeout(goHome, 2000); 
                    }
                }
            }
        }

        function checkGameFlow() {
            const totalQuestions = activeQuestions.length;
            const t = uiTexts[appLang];
            if (currentIndex < totalQuestions - 1) {
                document.getElementById("nextBtn").style.display = "block";
            } else {
                handleStreakAfterCompletion();
                document.getElementById("scoreBox").innerText = `${t.gameOver} ${score} / ${totalQuestions}`;
                setTimeout(goHome, 3000);
            }
        }

        function nextQuestion() {
            currentIndex++;
            loadQuestion();
        }

        updateMenuState();
    </script>

</body>
</html>
