<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title id="pageTitle">Günlük Yaşam Dil Pratiği v1.6</title>
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
        .menu-btn {
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
            color: white;
        }
        .start-btn { background-color: #007bff; }
        .errors-btn { background-color: #6c757d; }
        .shop-btn { background-color: #8b5cf6; }
        .league-btn { background-color: #f59e0b; }

        .refill-box {
            background-color: #fff3cd;
            border: 1px solid #ffeeba;
            color: #856404;
            padding: 15px;
            border-radius: 8px;
            text-align: center;
            margin-top: 15px;
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
            transition: all 0.15s ease;
        }
        .option-btn:hover {
            background-color: #f1f5f9;
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
        .league-row {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: #f8fafc;
            border: 1px solid #e2e8f0;
            padding: 10px 14px;
            border-radius: 8px;
            margin-bottom: 8px;
            font-size: 14px;
            font-weight: 600;
            color: #334155;
        }
        .league-row.user-row {
            background: #fef3c7;
            border-color: #f59e0b;
            color: #92400e;
        }
        .badge-card {
            background: #f8fafc;
            border: 2px solid #e2e8f0;
            padding: 12px 15px;
            border-radius: 10px;
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 14px;
        }
        .badge-card.unlocked {
            background: #fffbeb;
            border-color: #f59e0b;
        }
        .badge-icon {
            font-size: 28px;
        }
        .badge-info h3 {
            margin: 0 0 4px 0;
            font-size: 15px;
            color: #1e293b;
        }
        .badge-info p {
            margin: 0;
            font-size: 12px;
            color: #64748b;
        }
        .badge-card.unlocked .badge-info h3 {
            color: #b45309;
        }
        .badge-card.unlocked .badge-info p {
            color: #78350f;
        }
        .bottom-widgets {
            position: absolute;
            bottom: 15px;
            left: 15px;
            right: 15px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .sparkle-widget-btn {
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
        .badge-widget {
            background: #fffbeb;
            border: 2px solid #f59e0b;
            border-radius: 10px;
            padding: 6px 12px;
            display: flex;
            align-items: center;
            gap: 6px;
            font-size: 13px;
            font-weight: bold;
            color: #b45309;
            cursor: pointer;
            box-shadow: 0 4px 6px rgba(0,0,0,0.05);
            transition: all 0.2s ease;
        }
        .badge-widget:hover {
            background-color: #fef3c7;
            border-color: #d97706;
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

            <h1 id="mainTitle">🌍 Günlük Yaşam Dil Pratiği v1.6</h1>
            <p id="mainDesc" class="desc">Günlük Elmas Ligleri, Prestij Sistemi ve Kademeli Rozetler!</p>
            
            <select id="languageSelector">
                <option value="en">English (İngilizce)</option>
                <option value="es">Español (İspanyolca)</option>
                <option value="de">Deutsch (Almanca)</option>
                <option value="fr">Français (Fransızca)</option>
                <option value="it">Italiano (İtalyanca)</option>
                <option value="ru">Русский (Русский)</option>
                <option value="ko">한국어 (Korece)</option>
                <option value="ja">日本語 (Japonca)</option>
            </select>

            <button type="button" id="startQuizBtnText" class="menu-btn start-btn" onclick="startQuiz()">Derse / Teste Başla</button>
            <button type="button" id="errorsBtnText" class="menu-btn errors-btn" onclick="openErrorsScreen()">❌ Hatalarım</button>
            <button type="button" id="shopBtnText" class="menu-btn shop-btn" onclick="openShopScreen()">📚 Mağaza & Ödüller</button>
            <button type="button" id="leagueBtnText" class="menu-btn league-btn" onclick="openLeagueScreen()">🏆 Lig & Sıralama</button>

            <div id="refillBox" class="refill-box">
                <p id="refillMsgTitle" style="margin: 0 0 5px 0; font-weight: bold;">Canın bittiği için yeni oyuna başlayamazsın!</p>
                <button type="button" id="refillBtnText" class="refill-btn" onclick="startLifeLessons()">3 Can Dersi Yap (Canları Yenile)</button>
            </div>
            
            <div class="bottom-widgets">
                <button type="button" class="sparkle-widget-btn" onclick="openShopScreen()" title="Mağazaya Git">
                    <span class="eight-point-star">✴️</span>
                    <span id="sparkleCountText">0 Kıvılcım</span>
                </button>
                <button type="button" class="badge-widget" onclick="openBadgesScreen()" title="Rozetlerimi Görüntüle">
                    <span>👑</span>
                    <span id="badgeCountText">💎0</span>
                </button>
            </div>
        </div>

        <!-- TEST EKRANI -->
        <div id="quizScreen" class="screen">
            <div class="top-bar">
                <button type="button" id="backMenuBtn" class="back-btn" onclick="goHome()">⬅ Menü</button>
                <div id="livesDisplay" class="lives">❤️❤️❤️</div>
            </div>

            <h1 id="heading">Test</h1>
            <p id="description" class="desc">Aşağıdaki günlük yaşam senaryosuna en uygun ve doğru ifadeyi seçiniz.</p>

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
            <p id="errorHeaderDesc" class="desc">Testler sırasında yanlış yaptığın çeldiricilere takıldığın soruların doğru yanıtları:</p>
            
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

            <button type="button" id="buySparkleBtn" class="menu-btn start-btn" style="background-color: #8b5cf6;" onclick="buySparkle()">20 Kitap Karşılığı Seri Kıvılcımı Satın Al ✴️</button>
            <div id="shopFeedback" class="feedback-msg"></div>
        </div>

        <!-- LİG EKRANI -->
        <div id="leagueScreen" class="screen">
            <div class="top-bar">
                <button type="button" id="leagueBackBtn" class="back-btn" onclick="goHome()">⬅ Menü</button>
            </div>
            <h1 id="leagueHeading" style="color: #f59e0b;">💎 Elmas Lig Sıralaması</h1>
            <p id="leagueDesc" class="desc">İlk 3'e girerek üst aşamaya yüksel, Final'de 1. olarak Prestij Rozeti kazan!</p>
            
            <div id="leagueContainer" style="max-height: 330px; overflow-y: auto;"></div>
        </div>

        <!-- ROZETLER EKRANI -->
        <div id="badgesScreen" class="screen">
            <div class="top-bar">
                <button type="button" id="badgesBackBtn" class="back-btn" onclick="goHome()">⬅ Menü</button>
            </div>
            <h1 id="badgesHeading" style="color: #f59e0b;">👑 Prestij Rozetlerim</h1>
            <p id="badgesDesc" class="desc">Liglerde elde ettiğin başarılara göre açılan özel unvanlar ve rozetler:</p>
            
            <div id="badgesContainer" style="max-height: 330px; overflow-y: auto;"></div>
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
        let userStreak = parseInt(localStorage.getItem("userStreak")) || 0;
        let lastQuizDate = localStorage.getItem("lastQuizDate") || "";
        let userBooks = parseInt(localStorage.getItem("userBooks")) || 0;
        let userSparkles = parseInt(localStorage.getItem("userSparkles")) || 0;
        let streakClaimedToday = localStorage.getItem("streakClaimedToday") === "true";
        let userXP = parseInt(localStorage.getItem("userXP")) || 0;
        let userBadges = parseInt(localStorage.getItem("userBadges")) || 0;
        let leagueStage = localStorage.getItem("leagueStage") || "quarter"; // "quarter", "semi", "final"
        let lastLeagueReset = localStorage.getItem("lastLeagueReset") || "";

        // Rozet Durumları (Kilitler)
        let badgeApprentice = localStorage.getItem("badgeApprentice") === "true"; // Elmas Çırağı
        let badgeMaster = localStorage.getItem("badgeMaster") === "true";         // Elmas Ustası
        let badgePro = localStorage.getItem("badgePro") === "true";               // Elmas Prosu
        let badgePower = localStorage.getItem("badgePower") === "true";           // Elmas Gücü

        // Bot Rakipler
        let botScores = JSON.parse(localStorage.getItem("botScores")) || [
            { name: "AlphaBot-01", xp: 140 },
            { name: "NeuralSynth-X", xp: 120 },
            { name: "LogicUnit-9", xp: 95 },
            { name: "QuantumBot-V2", xp: 80 },
            { name: "CyberCore-7", xp: 70 },
            { name: "DataNode-Alpha", xp: 55 },
            { name: "SyntaxError-Fix", xp: 40 },
            { name: "Protocol-Delta", xp: 30 },
            { name: "EchoBot-99", xp: 15 }
        ];

        function checkStreakOnLoad() {
            const todayStr = new Date().toDateString();
            if (lastQuizDate && lastQuizDate !== todayStr) {
                const yesterday = new Date();
                yesterday.setDate(yesterday.getDate() - 1);
                if (lastQuizDate !== yesterday.toDateString()) {
                    if (userSparkles > 0) {
                        userSparkles--;
                        localStorage.setItem("userSparkles", userSparkles);
                        alert("1 gün girmedin ama Seri Kıvılcımı seni kurtardı! 🔥✴️");
                        userStreak++;
                    } else {
                        userStreak = 0;
                    }
                    streakClaimedToday = false;
                    localStorage.setItem("userStreak", userStreak);
                    localStorage.setItem("streakClaimedToday", "false");
                }
            }
        }
        checkStreakOnLoad();

        function checkDailyLeagueReset() {
            const todayStr = new Date().toDateString();
            if (lastLeagueReset !== todayStr && lastLeagueReset !== "") {
                let rankingList = [...botScores, { name: "Sen", xp: userXP }];
                rankingList.sort((a, b) => b.xp - a.xp);
                let userRank = rankingList.findIndex(r => r.name === "Sen") + 1;

                let isChampion = false;

                // 1. ELMAS FİNALİ 1.LİĞİ -> ELMAS GÜCÜ & PRESTİJ (ÇEYREĞE DÖN)
                if (leagueStage === "final" && userRank === 1) {
                    userBadges++;
                    if (!badgePower) {
                        badgePower = true;
                        localStorage.setItem("badgePower", "true");
                    }
                    leagueStage = "quarter"; 
                    isChampion = true;
                    alert(`👑 ELMAS GÜCÜ & ŞAMPİYON! 💎 Rozet +1 kazandın!\nElmas Finalleri 1.liği rozeti açıldı! Çeyrek Final'e döndün.`);
                } 
                // 2. NORMAL YÜKSELME / DÜŞME VE AŞAMA ROZETLERİ
                else if (userRank <= 3 && leagueStage !== "final") {
                    if (leagueStage === "quarter") {
                        leagueStage = "semi";
                        if (!badgeApprentice) {
                            badgeApprentice = true;
                            localStorage.setItem("badgeApprentice", "true");
                            alert(`🥉 Yeni Rozet Açıldı: Elmas Çırağı! (Çeyrek Final İlk 3)`);
                        }
                        alert(`🚀 İlk 3! Elmas Yarı Final aşamasına yükseldin!`);
                    } else if (leagueStage === "semi") {
                        leagueStage = "final";
                        if (!badgeMaster) {
                            badgeMaster = true;
                            localStorage.setItem("badgeMaster", "true");
                            alert(`🥈 Yeni Rozet Açıldı: Elmas Ustası! (Yarı Final İlk 3)`);
                        }
                        alert(`🚀 İlk 3! Elmas Final aşamasına yükseldin!`);
                    }
                } 
                // 3. FİNAL İLK 3 KONTROLÜ -> ELMAS PROSU
                else if (leagueStage === "final" && userRank <= 3) {
                    if (!badgePro) {
                        badgePro = true;
                        localStorage.setItem("badgePro", "true");
                        alert(`🥇 Yeni Rozet Açıldı: Elmas Prosu! (Final İlk 3)`);
                    }
                }
                
                // DÜŞME KONTROLLERİ
                if (userRank >= 8 && leagueStage !== "quarter") {
                    leagueStage = leagueStage === "final" ? "semi" : "quarter";
                    alert(`😭 Son 3... Bir alt lige düştün.`);
                }

                if (!isChampion && leagueStage === "final" && userRank !== 1) {
                    alert(`Finali ${userRank}. bitirdin. Yarın tekrar dene!`);
                }

                // HERKESİ SIFIRLA
                userXP = 0;
                localStorage.setItem("userXP", 0);
                localStorage.setItem("leagueStage", leagueStage);
                localStorage.setItem("userBadges", userBadges);
                lastLeagueReset = todayStr;
                localStorage.setItem("lastLeagueReset", todayStr);
                
                // BOTLARA RANDOM XP KASDIR
                botScores.forEach(bot => bot.xp = Math.floor(Math.random() * 60) + 10);
                localStorage.setItem("botScores", JSON.stringify(botScores));
            } else if (!lastLeagueReset) {
                lastLeagueReset = todayStr;
                localStorage.setItem("lastLeagueReset", todayStr);
            }
        }
        checkDailyLeagueReset();

        const uiTexts = {
            tr: {
                pageTitle: "Günlük Yaşam Dil Pratiği v1.6",
                mainTitle: "🌍 Günlük Yaşam Dil Pratiği",
                mainDesc: "Günlük Elmas Ligleri, Prestij Sistemi ve Kademeli Rozetler!",
                startBtn: "Derse / Teste Başla",
                errorsBtn: "❌ Hatalarım",
                shopBtn: "📚 Mağaza & Ödüller",
                refillMsg: "Canın bittiği için yeni oyuna başlayamazsın!",
                refillBtn: "3 Can Dersi Yap (Canları Yenile)",
                backMenu: "⬅ Menü",
                quizDefaultDesc: "Aşağıdaki günlük yaşam senaryosuna en uygun ve doğru ifadeyi seçiniz.",
                nextBtn: "Sonraki Soru",
                errorHeaderTitle: "❌ Yanlış Yapılan Sorular",
                errorHeaderDesc: "Testler sırasında yanlış yaptığın çeldiricilere takıldığın soruların doğru yanıtları:",
                noErrors: "Henüz kaydedilmiş bir hatan yok. Harika gidiyorsun!",
                correctAnswerText: "Doğru Cevap",
                lessonDesc: "3 canını tamamen geri kazanmak için sırayla 3 pekiştirme sorusunu doğru yanıtla!",
                lessonPrefix: "💡 Can Dersi",
                correctMsg: "Harika, doğru çeldiriciyi aştın!",
                wrongFirstMsg: "Yanlış! Çok yaklaştın, tekrar dene.",
                wrongSecondMsg: "Üzgünüm, profesyonel çeldiriciye takıldın ve 1 canın gitti!",
                outOfLivesMsg: "Canın bitti! Ana menüye dönülüyor...",
                gameOver: "Tebrikler! Soru bankası testi bitti (+10 XP kazandın!). Puanın:",
                blockedPlayAlert: "Canın bittiği için şu an oynayamazsın! Lütfen '3 Can Dersi Yap' butonuna basarak canları yenile.",
                questionLabel: "Soru Bankası Soru No",
                shopHeading: "📚 Mağaza & Ödüller",
                shopDesc: "7 günlük serileri tamamlayarak **10 Kitap** kazanabilir, **20 Kitap** ile **Seri Kıvılcımı** satın alabilirsin!",
                buySparkleBtnText: "20 Kitap Karşılığı Seri Kıvılcımı Satın Al ✴️",
                streakBadgeText: (s) => `🔥 ${s} Gün`,
                sparkleText: (sp) => `${sp} Kıvılcım`,
                badgeText: (b) => `💎${b}`,
                booksText: (b) => `Sahip Olunan Kitaplar: ${b} 📖`,
                streakProgress: (s) => `7 Günlük Seri İlerlemesi: ${s % 7}/7 Gün`,
                streakRewardMsg: "🎉 Tebrikler! 7 günlük seriyi tamamladın ve 10 Kitap ödülü kazandın!",
                notEnoughBooks: "Yeterli kitabın yok! Seri Kıvılcımı almak için 20 kitaba ihtiyacın var.",
                boughtSuccess: "Başarıyla 1 Seri Kıvılcımı satın aldın! ✴️",
                leagueDesc: "İlk 3'e girerek üst aşamaya yüksel, Final'de 1. olarak Prestij Rozeti kazan!",
                myProfileName: "Sen"
            },
            en: {
                pageTitle: "Daily Life Language Practice v1.6",
                mainTitle: "🌍 Daily Life Language Practice",
                mainDesc: "Daily Diamond Leagues, Prestige System & Tiered Badges!",
                startBtn: "Start Lesson / Quiz",
                errorsBtn: "❌ My Mistakes",
                shopBtn: "📚 Shop & Rewards",
                refillMsg: "You cannot start a new game because you are out of lives!",
                refillBtn: "Take 3 Life Lessons (Refill Lives)",
                backMenu: "⬅ Menu",
                quizDefaultDesc: "Choose the most appropriate and accurate expression for the daily life scenario below.",
                nextBtn: "Next Question",
                errorHeaderTitle: "❌ Incorrectly Answered Questions",
                errorHeaderDesc: "Correct answers to the questions where you fell for the tricky distractors:",
                noErrors: "You have no saved mistakes yet. You're doing great!",
                correctAnswerText: "Correct Answer",
                lessonDesc: "Answer 3 reinforcement questions correctly in a row to fully recover your 3 lives!",
                lessonPrefix: "💡 Life Lesson",
                correctMsg: "Great, you beat the tricky distractor!",
                wrongFirstMsg: "Incorrect! You were close, try again.",
                wrongSecondMsg: "Sorry, you fell for the professional distractor and lost 1 life!",
                outOfLivesMsg: "Out of lives! Returning to the main menu...",
                gameOver: "Congratulations! Test finished (+10 XP earned!). Your score:",
                blockedPlayAlert: "You cannot play right now because you are out of lives! Please click 'Take 3 Life Lessons' to refill.",
                questionLabel: "Question Bank Item",
                shopHeading: "📚 Shop & Rewards",
                shopDesc: "Complete 7-day streaks to earn **10 Books**, and use **20 Books** to buy a **Streak Sparkle**!",
                buySparkleBtnText: "Buy Streak Sparkle for 20 Books ✴️",
                streakBadgeText: (s) => `🔥 ${s} Days`,
                sparkleText: (sp) => `${sp} Sparkles`,
                badgeText: (b) => `💎${b}`,
                booksText: (b) => `Owned Books: ${b} 📖`,
                streakProgress: (s) => `7-Day Streak Progress: ${s % 7}/7 Days`,
                streakRewardMsg: "🎉 Congratulations! You completed a 7-day streak and earned 10 Books reward!",
                notEnoughBooks: "You don't have enough books! You need 20 books to buy a Streak Sparkle.",
                boughtSuccess: "Successfully bought 1 Streak Sparkle! ✴️",
                leagueDesc: "Top 3 advance, finish #1 in Final to earn a Prestige Badge!",
                myProfileName: "You"
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
            document.getElementById("backMenuBtn").innerText = t.backMenu;
            document.getElementById("errorBackBtn").innerText = t.backMenu;
            document.getElementById("shopBackBtn").innerText = t.backMenu;
            document.getElementById("leagueBackBtn").innerText = t.backMenu;
            document.getElementById("badgesBackBtn").innerText = t.backMenu;
            document.getElementById("description").innerText = t.quizDefaultDesc;
            document.getElementById("nextBtn").innerText = t.nextBtn;
            document.getElementById("errorHeaderTitle").innerText = t.errorHeaderTitle;
            document.getElementById("errorHeaderDesc").innerText = t.errorHeaderDesc;
            document.getElementById("shopHeading").innerText = t.shopHeading;
            document.getElementById("shopDesc").innerHTML = t.shopDesc;
            document.getElementById("buySparkleBtn").innerText = t.buySparkleBtnText;
            document.getElementById("leagueDesc").innerText = t.leagueDesc;

            updateHomeWidgets();
            updateLeagueButtonTitle();

            const currentSelectedLang = document.getElementById("languageSelector").value;
            if (document.getElementById("quizScreen").classList.contains("active")) {
                document.getElementById("heading").innerText = rawQuizData[currentSelectedLang].heading[appLang];
            }
        }

        function getLeagueStageInfo() {
            if (leagueStage === "final") {
                return { name: appLang === 'tr' ? "💎 Elmas Final" : "💎 Diamond Final" };
            } else if (leagueStage === "semi") {
                return { name: appLang === 'tr' ? "💎 Elmas Yarı Final" : "💎 Diamond Semi-Final" };
            } else {
                return { name: appLang === 'tr' ? "💎 Elmas Çeyrek Final" : "💎 Diamond Quarter-Final" };
            }
        }

        function updateHomeWidgets() {
            const t = uiTexts[appLang];
            document.getElementById("streakBadge").innerText = t.streakBadgeText(userStreak);
            document.getElementById("sparkleCountText").innerText = t.sparkleText(userSparkles);
            document.getElementById("badgeCountText").innerText = t.badgeText(userBadges);
        }

        function updateLeagueButtonTitle() {
            const stage = getLeagueStageInfo();
            document.getElementById("leagueBtnText").innerText = `🏆 Lig & Sıralama (${stage.name})`;
        }

        const rawQuizData = {
            en: {
                heading: { tr: "English - Genişletilmiş Soru Bankası", en: "English - Expanded Question Bank" },
                questions: [
                    { 
                        q: { tr: "Yabancı bir şehirde metro istasyonunu arıyorsunuz ve yoldan geçen kibar birine adres sormanız gerekiyor. En doğal ve doğru hitap hangisidir?", en: "You are looking for a subway station in a foreign city and need to ask a polite stranger for directions. What is the most natural approach?" }, 
                        options: ["Excuse me, could you tell me where the nearest subway station is?", "Where is subway? Tell me now.", "I want to find subway station immediately.", "Do you know where the metro is closed?"], correct: 0 
                    },
                    { 
                        q: { tr: "Bir kafede garson masanıza gelip siparişinizi sordu. Hem kahve hem de hesap isteme ihtimalini ortadan kaldırıp net bir şekilde kahve sipariş etmek istiyorsunuz:", en: "A waiter came to your table and asked for your order. You want to clearly order coffee without causing any confusion:" }, 
                        options: ["Can I have a cup of black coffee, please?", "I want coffee and give me the bill too.", "Where is your coffee machine?", "Do you drink coffee here?"], correct: 0 
                    },
                    { 
                        q: { tr: "Mağazada beğendiğiniz kaliteli bir montun fiyatını ve indirimde olup olmadığını öğrenmek istiyorsunuz:", en: "You want to find out the price of a jacket you liked in a store and whether it is on sale:" }, 
                        options: ["Excuse me, how much does this jacket cost?", "Is this jacket expensive for me?", "Why is this jacket here?", "Can I wear this jacket outside?"], correct: 0 
                    },
                    { 
                        q: { tr: "Havaalanı pasaport kontrolünde görevli memur pasaportunuzla birlikte biniş kartınızı da talep ediyor. Ona doğru cevaben ne verirsiniz?", en: "At the airport passport control, the officer requests your boarding pass along with your passport. What do you hand over correctly?" }, 
                        options: ["Here is my passport and my boarding pass.", "I lost both my passport and my ticket.", "Show me your officer card first.", "My plane is already landing."], correct: 0 
                    },
                    { 
                        q: { tr: "Arkadaşınız uzun süren zorlu bir sınavı başarıyla geçtiğini söyledi. Onun bu büyük sevincini paylaşmak için ne dersiniz?", en: "Your friend said they successfully passed a difficult exam after a long time. What do you say to share their excitement?" }, 
                        options: ["That's fantastic news, huge congratulations!", "I am so sorry to hear that.", "Exams are always boring and long.", "See you next week at school."], correct: 0 
                    },
                    { 
                        q: { tr: "Otele giriş yapıyorsunuz, resepsiyonist oda kartınızı teslim ediyor ve size konforlu bir konaklama diliyor:", en: "You are checking into a hotel, the receptionist hands over your room card and wishes you a comfortable stay:" }, 
                        options: ["Thank you very much, have a wonderful day.", "Give me another room key immediately.", "Where is the exit door?", "Goodbye, I am leaving now."], correct: 0 
                    },
                    { 
                        q: { tr: "Süpermarketde laktozsuz süt arıyorsunuz ama reyonlarda bulamadınız. Görevliye en kibar nasıl danışırsınız?", en: "You are looking for lactose-free milk in the supermarket but couldn't find it on the shelves. How do you politely ask the staff?" }, 
                        options: ["Excuse me, do you know where I can find lactose-free milk?", "Bring me milk right now.", "Why don't you sell milk here?", "Is this milk expired?"], correct: 0 
                    },
                    { 
                        q: { tr: "Kalabalık bir caddede yürürken dalgınlıkla birinin telefonunu düşürmesine sebep oldunuz. Acil ve samimi özür:", en: "While walking on a crowded street, you absentmindedly caused someone to drop their phone. Urgent and sincere apology:" }, 
                        options: ["I am so terribly sorry, let me help you pick it up.", "Thank you for dropping your phone.", "Watch out for my steps next time.", "Good afternoon to you too."], correct: 0 
                    },
                    { 
                        q: { tr: "Şık bir restoranda akşam yemeğini bitirdiniz ve ödemeyi kredi kartıyla yapmak istediğinizi belirtmek istiyorsunuz:", en: "You finished dinner at an upscale restaurant and want to state that you wish to pay by credit card:" }, 
                        options: ["Could we have the bill, and can I pay by credit card?", "I don't have any money for this meal.", "Where is the kitchen staff?", "The food was completely raw."], correct: 0 
                    },
                    { 
                        q: { tr: "Önemli bir iş toplantısına toplu taşıma gecikmesi yüzünden 10 dakika geciktiniz. İçeri girerken yapacağınız en profesyonel açıklama:", en: "You are 10 minutes late for an important business meeting due to public transit delays. The most professional statement upon entering:" }, 
                        options: ["Please accept my apologies for being late due to traffic delays.", "I overslept because my alarm didn't ring at all.", "Why did you start the meeting without me?", "Have a great morning everyone."], correct: 0 
                    }
                ]
            },
            es: {
                heading: { tr: "Español - Genişletilmiş Soru Bankası", en: "Spanish - Expanded Question Bank" },
                questions: [
                    { 
                        q: { tr: "Şehir merkezinde en yakın metro istasyonunu arıyorsunuz. İspanyolca en doğru ifade:", en: "You are looking for the nearest subway station in the city center. Most accurate expression in Spanish:" }, 
                        options: ["¿Podría decirme dónde está la estación de metro más cercana?", "¿Dónde está el metro cerrado?", "Quiero comprar billetes de tren.", "Tengo mucha hambre ahora."], correct: 0 
                    }
                ]
            },
            de: {
                heading: { tr: "Deutsch - Genişletilmiş Soru Bankası", en: "German - Expanded Question Bank" },
                questions: [
                    { 
                        q: { tr: "Trenden indiniz ve en yakın metro istasyonunu Almanca sormak istiyorsunuz:", en: "You got off the train and want to ask for the nearest metro station in German:" }, 
                        options: ["Könnten Sie mir sagen, wo die nächste U-Bahn-Station ist?", "Wo ist der geschlossene Bahnhof?", "Ich möchte jetzt schlafen.", "Wie viel Uhr ist es genau?"], correct: 0 
                    }
                ]
            },
            fr: {
                heading: { tr: "Français - Genişletilmiş Soru Bankası", en: "French - Expanded Question Bank" },
                questions: [
                    { 
                        q: { tr: "Fransa'da en yakın metro istasyonunu sormak istiyorsunuz:", en: "You want to ask for the nearest metro station in France:" }, 
                        options: ["Excusez-moi, pourriez-vous m'indiquer la station de métro la plus proche ?", "Où est le train qui ne marche pas ?", "Je voudrais dormir ici.", "Quelle est la date d'aujourd'hui ?"], correct: 0 
                    }
                ]
            },
            it: {
                heading: { tr: "Italiano - Genişletilmiş Soru Bankası", en: "Italian - Expanded Question Bank" },
                questions: [
                    { 
                        q: { tr: "Roma'da metro istasyonunu İtalyanca kibarca sormak istiyorsunuz:", en: "You want to politely ask for the metro station in Rome in Italian:" }, 
                        options: ["Scusi, saprebbe dirmi dov'è la stazione della metropolitana più vicina?", "Dov'è il treno che non parte?", "Voglio mangiare una pizza adesso.", "Che tempo fa oggi a Roma?"], correct: 0 
                    }
                ]
            },
            ru: {
                heading: { tr: "Русский - Genişletilmiş Soru Bankası", en: "Russian - Expanded Question Bank" },
                questions: [
                    { 
                        q: { tr: "Rusya'da en yakın metro istasyonunu sormak istiyorsunuz:", en: "You want to ask for the nearest metro station in Russia:" }, 
                        options: ["Скажите, пожалуйста, где находится ближайшая станция метро?", "Где закрытый вокзал города?", "Я хочу купить билет на самолет.", "Который сейчас час?"], correct: 0 
                    }
                ]
            },
            ko: {
                heading: { tr: "한국어 - Genişletilmiş Soru Bankası", en: "Korean - Expanded Question Bank" },
                questions: [
                    { 
                        q: { tr: "한국에서 가장 가까운 지하철역을 정중하게 물어보고 싶습니다:", en: "You want to politely ask for the nearest subway station in Korea:" }, 
                        options: ["실례합니다, 가장 가까운 지하철역이 어디에 있는지 알려주시겠어요?", "지하철역이 왜 문을 닫았나요?", "지금 몇 시인지 아십니까?", "배가 고파서 음식을 먹고 싶어요."], correct: 0 
                    }
                ]
            },
            ja: {
                heading: { tr: "日本語 - Genişletilmiş Soru Bankası", en: "Japanese - Expanded Question Bank" },
                questions: [
                    { 
                        q: { tr: "日本で一番近い地下鉄の駅を丁寧に尋ねたい場合:", en: "When you want to politely ask for the nearest subway station in Japan:" }, 
                        options: ["すみません、一番近い地下鉄の駅はどこにあるか教えていただけますか？", "地下鉄の駅はどこで閉まりますか？", "今何時ですか、教えてください。", "お腹が空いたのでレストランに行きます。"], correct: 0 
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
            updateLeagueButtonTitle();
        }

        function handleStreakAfterCompletion() {
            const todayStr = new Date().toDateString();
            if (lastQuizDate !== todayStr) {
                if (!streakClaimedToday) {
                    userStreak++;
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
            updateHomeWidgets();
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

        function openLeagueScreen() {
            document.querySelectorAll(".screen").forEach(s => s.classList.remove("active"));
            document.getElementById("leagueScreen").classList.add("active");

            const t = uiTexts[appLang];
            const container = document.getElementById("leagueContainer");
            const stage = getLeagueStageInfo();

            document.getElementById("leagueHeading").innerText = `🏆 ${stage.name} Sıralaması`;

            let rankingList = [...botScores, { name: t.myProfileName, xp: userXP, isUser: true }];
            rankingList.sort((a, b) => b.xp - a.xp);

            container.innerHTML = rankingList.map((item, idx) => {
                let medal = idx === 0 ? "🥇" : idx === 1 ? "🥈" : idx === 2 ? "🥉" : `${idx + 1}.`;
                let rowClass = item.isUser ? "league-row user-row" : "league-row";
                return `
                    <div class="${rowClass}">
                        <span>${medal} ${item.name}</span>
                        <span>${item.xp} XP</span>
                    </div>
                `;
            }).join('');
        }

        function openBadgesScreen() {
            document.querySelectorAll(".screen").forEach(s => s.classList.remove("active"));
            document.getElementById("badgesScreen").classList.add("active");

            const container = document.getElementById("badgesContainer");

            const badgesList = [
                {
                    title: "💎 Elmas Çırağı",
                    desc: appLang === 'tr' ? "Elmas çeyrek finalinde ilk 3 içine girerek açılır." : "Unlocked by finishing in the top 3 of Diamond Quarter-Final.",
                    unlocked: badgeApprentice,
                    icon: "🥉"
                },
                {
                    title: "👑 Elmas Ustası",
                    desc: appLang === 'tr' ? "Yarı finallerde ilk 3'te bitirilince açılır." : "Unlocked by finishing in the top 3 of Semi-Finals.",
                    unlocked: badgeMaster,
                    icon: "🥈"
                },
                {
                    title: "⚡ Elmas Prosu",
                    desc: appLang === 'tr' ? "Elmas finallerinde ilk 3'te bitirilince açılır." : "Unlocked by finishing in the top 3 of Diamond Finals.",
                    unlocked: badgePro,
                    icon: "🥇"
                },
                {
                    title: "🔥 Elmas Gücü",
                    desc: appLang === 'tr' ? "Elmas finalleri 1. olarak bitirilince açılır." : "Unlocked by finishing 1st in Diamond Finals.",
                    unlocked: badgePower,
                    icon: "💎"
                }
            ];

            container.innerHTML = badgesList.map(b => {
                let cardClass = b.unlocked ? "badge-card unlocked" : "badge-card";
                let statusText = b.unlocked ? (appLang === 'tr' ? "Açıldı! ✔️" : "Unlocked! ✔️") : (appLang === 'tr' ? "Kilitli 🔒" : "Locked 🔒");
                return `
                    <div class="${cardClass}">
                        <div class="badge-icon">${b.icon}</div>
                        <div class="badge-info" style="flex-grow: 1;">
                            <h3>${b.title}</h3>
                            <p>${b.desc}</p>
                        </div>
                        <div style="font-size: 12px; font-weight: bold; color: ${b.unlocked ? '#b45309' : '#94a3b8'};">
                            ${statusText}
                        </div>
                    </div>
                `;
            }).join('');
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
                btns.forEach(b => b.disabled = true);
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
                userXP += 10;
                localStorage.setItem("userXP", userXP);

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
