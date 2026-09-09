<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title id="pageTitle">Günlük Yaşam Dil Pratiği v2.0</title>
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
            display: none;
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
        select, input[type="text"] {
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
        .friends-btn { background-color: #10b981; }

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
            margin-top: 5px;
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

            <h1 id="mainTitle">🌍 Günlük Yaşam Dil Pratiği</h1>
            
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
            <button type="button" id="friendsBtnText" class="menu-btn friends-btn" onclick="openFriendsScreen()">👥 Arkadaşlar & Ekle</button>

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

            <h1 id="heading" style="display: block;">🌍 Günlük Yaşam Dil Pratiği</h1>

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
            <h1 id="errorHeaderTitle" style="color: #e74c3c; display: block;">❌ Yanlış Yapılan Sorular</h1>
            <p id="errorHeaderDesc" style="color: #666; font-size: 14px; text-align: center; margin-bottom: 25px; line-height: 1.5; display: block;">Testler sırasında yanlış yaptığın çeldiricilere takıldığın soruların doğru yanıtları:</p>
            
            <div id="errorsContainer" style="max-height: 350px; overflow-y: auto;"></div>
        </div>

        <!-- MAĞAZA EKRANI -->
        <div id="shopScreen" class="screen">
            <div class="top-bar">
                <button type="button" id="shopBackBtn" class="back-btn" onclick="goHome()">⬅ Menü</button>
            </div>
            <h1 id="shopHeading" style="color: #8b5cf6; display: block;">📚 Mağaza & Ödüller</h1>
            <p id="shopDesc" style="color: #666; font-size: 14px; text-align: center; margin-bottom: 25px; line-height: 1.5; display: block;">7 günlük serileri tamamlayarak **10 Kitap** kazanabilir, **20 Kitap** ile **Seri Kıvılcımı** satın alabilirsin!</p>
            
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
            <h1 id="leagueHeading" style="color: #f59e0b; display: block;">💎 Elmas Lig Sıralaması</h1>
            <p id="leagueDesc" style="color: #666; font-size: 14px; text-align: center; margin-bottom: 25px; line-height: 1.5; display: block;">İlk 3'e girerek üst aşamaya yüksel, Final'de 1. olarak Prestij Rozeti kazan!</p>
            
            <div id="leagueContainer" style="max-height: 330px; overflow-y: auto;"></div>
        </div>

        <!-- ARKADAŞLAR EKRANI -->
        <div id="friendsScreen" class="screen">
            <div class="top-bar">
                <button type="button" id="friendsBackBtn" class="back-btn" onclick="goHome()">⬅ Menü</button>
            </div>
            
            <!-- İstediğin gibi AD DÜZENLE / EKLE başlığı ve butonu en üstte -->
            <div style="background: #f8fafc; border: 1px solid #e2e8f0; padding: 15px; border-radius: 10px; margin-bottom: 20px;">
                <p style="margin: 0 0 8px 0; font-weight: bold; color: #1e293b; font-size: 14px;" id="nicknameSectionTitle">AD DÜZENLE / EKLE</p>
                <input type="text" id="nicknameInput" placeholder="Takma adınızı girin..." style="margin-bottom: 10px;">
                <button type="button" id="saveNicknameBtn" class="menu-btn start-btn" style="padding: 10px; margin-bottom: 0;" onclick="saveNickname()">Takma Adı Kaydet</button>
            </div>

            <h1 id="friendsHeading" style="color: #10b981; display: block;">👥 Arkadaş Ekle & Listesi</h1>
            <p id="friendsDesc" style="color: #666; font-size: 14px; text-align: center; margin-bottom: 15px; line-height: 1.5; display: block;">Arkadaşının kullanıcı adını yazarak arkadaş olarak ekle:</p>

            <div style="display: flex; gap: 8px; margin-bottom: 15px;">
                <input type="text" id="friendUsernameInput" placeholder="Arkadaş kullanıcı adı..." style="margin-bottom: 0;">
                <button type="button" id="addFriendActionBtn" class="menu-btn start-btn" style="width: 120px; margin-bottom: 0; background-color: #10b981;" onclick="addFriend()">Ekle</button>
            </div>

            <div id="friendsContainer" style="max-height: 220px; overflow-y: auto;"></div>
        </div>

        <!-- ROZETLER EKRANI -->
        <div id="badgesScreen" class="screen">
            <div class="top-bar">
                <button type="button" id="badgesBackBtn" class="back-btn" onclick="goHome()">⬅ Menü</button>
            </div>
            <h1 id="badgesHeading" style="color: #f59e0b; display: block;">👑 Prestij Rozetlerim</h1>
            <p id="badgesDesc" style="color: #666; font-size: 14px; text-align: center; margin-bottom: 25px; line-height: 1.5; display: block;">Liglerde elde ettiğin başarılara göre açılan özel unvanlar ve rozetler:</p>
            
            <div id="badgesContainer" style="max-height: 330px; overflow-y: auto;"></div>
        </div>

        <!-- CAN DERSİ EKRANI -->
        <div id="lifeLessonScreen" class="screen">
            <h1 style="color: #d97706; display: block;" id="lessonHeading">💡 Can Dersi (1/3)</h1>
            <p id="lessonDescText" style="color: #666; font-size: 14px; text-align: center; margin-bottom: 25px; line-height: 1.5; display: block;">3 canını tamamen geri kazanmak için sırayla 3 pekiştirme sorusunu doğru yanıtla!</p>

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
        let leagueStage = localStorage.getItem("leagueStage") || "quarter";
        let lastLeagueReset = localStorage.getItem("lastLeagueReset") || "";

        let userNickname = localStorage.getItem("userNickname") || "Sen";
        let friendList = JSON.parse(localStorage.getItem("friendList")) || [];

        let badgeApprentice = localStorage.getItem("badgeApprentice") === "true";
        let badgeMaster = localStorage.getItem("badgeMaster") === "true";
        let badgePro = localStorage.getItem("badgePro") === "true";
        let badgePower = localStorage.getItem("badgePower") === "true";

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
                let rankingList = [...botScores, { name: userNickname, xp: userXP }];
                rankingList.sort((a, b) => b.xp - a.xp);
                let userRank = rankingList.findIndex(r => r.name === userNickname) + 1;

                if (leagueStage === "final" && userRank === 1) {
                    userBadges++;
                    if (!badgePower) {
                        badgePower = true;
                        localStorage.setItem("badgePower", "true");
                    }
                    leagueStage = "quarter"; 
                    alert(`👑 ELMAS GÜCÜ & ŞAMPİYON! 💎 Rozet +1 kazandın!\nElmas Finalleri 1.liği açıldı! Çeyrek Final'e döndün.`);
                } else if (userRank <= 3 && leagueStage !== "final") {
                    if (leagueStage === "quarter") {
                        leagueStage = "semi";
                        if (!badgeApprentice) {
                            badgeApprentice = true;
                            localStorage.setItem("badgeApprentice", "true");
                            alert(`🥉 Yeni Rozet Açıldı: Elmas Çırağı!`);
                        }
                        alert(`🚀 İlk 3! Elmas Yarı Final aşamasına yükseldin!`);
                    } else if (leagueStage === "semi") {
                        leagueStage = "final";
                        if (!badgeMaster) {
                            badgeMaster = true;
                            localStorage.setItem("badgeMaster", "true");
                            alert(`🥈 Yeni Rozet Açıldı: Elmas Ustası!`);
                        }
                        alert(`🚀 İlk 3! Elmas Final aşamasına yükseldin!`);
                    }
                } else if (leagueStage === "final" && userRank <= 3) {
                    if (!badgePro) {
                        badgePro = true;
                        localStorage.setItem("badgePro", "true");
                        alert(`🥇 Yeni Rozet Açıldı: Elmas Prosu!`);
                    }
                }
                
                if (userRank >= 8 && leagueStage !== "quarter") {
                    leagueStage = leagueStage === "final" ? "semi" : "quarter";
                    alert(`😭 Son 3... Bir alt lige düştün.`);
                }

                userXP = 0;
                localStorage.setItem("userXP", 0);
                localStorage.setItem("leagueStage", leagueStage);
                localStorage.setItem("userBadges", userBadges);
                lastLeagueReset = todayStr;
                localStorage.setItem("lastLeagueReset", todayStr);
                
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
                pageTitle: "Günlük Yaşam Dil Pratiği v2.0",
                mainTitle: "🌍 Günlük Yaşam Dil Pratiği",
                startBtn: "Derse / Teste Başla",
                errorsBtn: "❌ Hatalarım",
                shopBtn: "📚 Mağaza & Ödüller",
                friendsBtn: "👥 Arkadaşlar & Ekle",
                refillMsg: "Canın bittiği için yeni oyuna başlayamazsın!",
                refillBtn: "3 Can Dersi Yap (Canları Yenile)",
                backMenu: "⬅ Menü",
                nextBtn: "Sonraki Soru",
                errorHeaderTitle: "❌ Yanlış Yapılan Sorular",
                errorHeaderDesc: "Testler sırasında yanlış yaptığın çeldiricilere takıldığın soruların doğru yanıtları:",
                noErrors: "Henüz kaydedilmiş bir hatan yok. Harika gidiyorsun!",
                correctAnswerText: "Doğru Cevap",
                lessonDesc: "3 canını tamamen geri kazanmak için sırayla 3 pekiştirme sorusunu doğru yanıtla!",
                lessonPrefix: "💡 Can Dersi",
                correctMsg: "Tebrikler, doğru!",
                wrongFirstMsg: "Yanlış! Çok yaklaştın, tekrar dene.",
                wrongSecondMsg: "Üzgünüm, bu soruyu geçemedin",
                outOfLivesMsg: "Canın bitti! Ana menüye dönülüyor...",
                gameOver: "Tebrikler! Test bitti (+10 XP kazandın!). Puanın:",
                blockedPlayAlert: "Canın bittiği için şu an oynayamazsın! Lütfen can dersi yap.",
                shopHeading: "📚 Mağaza & Ödüller",
                shopDesc: "7 günlük serileri tamamlayarak **10 Kitap** kazanabilir, **20 Kitap** ile **Seri Kıvılcımı** satın alabilirsin!",
                buySparkleBtnText: "20 Kitap Karşılığı Seri Kıvılcımı Satın Al ✴️",
                streakBadgeText: (s) => `🔥 ${s} Gün`,
                sparkleText: (sp) => `${sp} Kıvılcım`,
                badgeText: (b) => `💎${b}`,
                booksText: (b) => `Sahip Olunan Kitaplar: ${b} 📖`,
                streakProgress: (s) => `7 Günlük Seri İlerlemesi: ${s % 7}/7 Gün`,
                streakRewardMsg: "🎉 Tebrikler! 7 günlük seriyi tamamladın ve 10 Kitap ödülü kazandın!",
                notEnoughBooks: "Yeterli kitabın yok! 20 kitaba ihtiyacın var.",
                boughtSuccess: "Başarıyla 1 Seri Kıvılcımı satın aldın! ✴️",
                leagueDesc: "İlk 3'e girerek üst aşamaya yüksel, Final'de 1. olarak Prestij Rozeti kazan!",
                friendsHeading: "👥 Arkadaş Ekle & Listesi",
                friendsDesc: "Arkadaşının kullanıcı adını yazarak arkadaş olarak ekle:",
                nicknameTitle: "AD DÜZENLE / EKLE",
                saveNicknameBtn: "Takma Adı Kaydet",
                addFriendBtn: "Ekle",
                noFriends: "Henüz arkadaş eklemedin."
            },
            en: {
                pageTitle: "Daily Life Language Practice v2.0",
                mainTitle: "🌍 Daily Life Language Practice",
                startBtn: "Start Lesson / Quiz",
                errorsBtn: "❌ My Mistakes",
                shopBtn: "📚 Shop & Rewards",
                friendsBtn: "👥 Friends & Add",
                refillMsg: "You cannot start a new game because you are out of lives!",
                refillBtn: "Take 3 Life Lessons (Refill Lives)",
                backMenu: "⬅ Menu",
                nextBtn: "Next Question",
                errorHeaderTitle: "❌ Incorrectly Answered Questions",
                errorHeaderDesc: "Correct answers to questions where you fell for distractors:",
                noErrors: "No saved mistakes yet. Great job!",
                correctAnswerText: "Correct Answer",
                lessonDesc: "Answer 3 reinforcement questions correctly in a row to recover 3 lives!",
                lessonPrefix: "💡 Life Lesson",
                correctMsg: "Congratulations, correct!",
                wrongFirstMsg: "Incorrect! You were close, try again.",
                wrongSecondMsg: "Sorry, you couldn't pass this question",
                outOfLivesMsg: "Out of lives! Returning to menu...",
                gameOver: "Congratulations! Test finished (+10 XP). Your score:",
                blockedPlayAlert: "Out of lives! Please complete life lessons.",
                shopHeading: "📚 Shop & Rewards",
                shopDesc: "Complete 7-day streaks to earn **10 Books**, use **20 Books** for a **Streak Sparkle**!",
                buySparkleBtnText: "Buy Streak Sparkle for 20 Books ✴️",
                streakBadgeText: (s) => `🔥 ${s} Days`,
                sparkleText: (sp) => `${sp} Sparkles`,
                badgeText: (b) => `💎${b}`,
                booksText: (b) => `Owned Books: ${b} 📖`,
                streakProgress: (s) => `7-Day Streak Progress: ${s % 7}/7 Days`,
                streakRewardMsg: "🎉 Congratulations! Streak completed, earned 10 Books!",
                notEnoughBooks: "Not enough books! You need 20 books.",
                boughtSuccess: "Successfully bought 1 Streak Sparkle! ✴️",
                leagueDesc: "Top 3 advance, finish #1 in Final for a Prestige Badge!",
                friendsHeading: "👥 Friends & List",
                friendsDesc: "Add friends by typing their username:",
                nicknameTitle: "EDIT / ADD NICKNAME",
                saveNicknameBtn: "Save Nickname",
                addFriendBtn: "Add",
                noFriends: "No friends added yet."
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
            document.getElementById("startQuizBtnText").innerText = t.startBtn;
            document.getElementById("errorsBtnText").innerText = t.errorsBtn;
            document.getElementById("shopBtnText").innerText = t.shopBtn;
            document.getElementById("leagueBtnText").innerText = t.leagueBtn;
            document.getElementById("friendsBtnText").innerText = t.friendsBtn;
            document.getElementById("refillMsgTitle").innerText = t.refillMsg;
            document.getElementById("refillBtnText").innerText = t.refillBtn;
            document.getElementById("backMenuBtn").innerText = t.backMenu;
            document.getElementById("errorBackBtn").innerText = t.backMenu;
            document.getElementById("shopBackBtn").innerText = t.backMenu;
            document.getElementById("leagueBackBtn").innerText = t.backMenu;
            document.getElementById("friendsBackBtn").innerText = t.backMenu;
            document.getElementById("badgesBackBtn").innerText = t.backMenu;
            document.getElementById("nextBtn").innerText = t.nextBtn;
            document.getElementById("errorHeaderTitle").innerText = t.errorHeaderTitle;
            document.getElementById("errorHeaderDesc").innerText = t.errorHeaderDesc;
            document.getElementById("shopHeading").innerText = t.shopHeading;
            document.getElementById("shopDesc").innerHTML = t.shopDesc;
            document.getElementById("buySparkleBtn").innerText = t.buySparkleBtnText;
            document.getElementById("leagueDesc").innerText = t.leagueDesc;
            
            document.getElementById("nicknameSectionTitle").innerText = t.nicknameTitle;
            document.getElementById("saveNicknameBtn").innerText = t.saveNicknameBtn;
            document.getElementById("friendsHeading").innerText = t.friendsHeading;
            document.getElementById("friendsDesc").innerText = t.friendsDesc;
            document.getElementById("addFriendActionBtn").innerText = t.addFriendBtn;

            updateHomeWidgets();
            updateLeagueButtonTitle();
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

        const poolTemplates = {
            tr: [
                { q: "[PLACE] konumunu kibarca nasıl sorarsınız?", options: ["Afedersiniz, [PLACE] nerede acaba?", "[PLACE] nerede?", "Hemen [PLACE] lazım.", "[PLACE] aç bana."], correct: 0 },
                { q: "Bir restoranda [FOOD] siparişi nasıl verilir?", options: ["[PLACE_OR_FOOD] alabilir miyim lütfen?", "Bana hemen [FOOD] ver.", "[FOOD] sevmiyorum.", "[FOOD] nerede?"], correct: 0 },
                { q: "Bir mağazada [ITEM] fiyatını nasıl sorarsınız?", options: ["[ITEM] fiyatı ne kadardır?", "[ITEM] bugün bedava mı?", "[ITEM] niye burada?", "[ITEM] giyebilir miyim?"], correct: 0 },
                { q: "Biri sana [THING] konusunda yardım ettiğinde ne dersin?", options: ["Yardımın için çok teşekkür ederim.", "Bir daha asla yardım etme.", "[THING] nerede?", "İyi günler."], correct: 0 },
                { q: "[EVENT] etkinliğine geç kaldığın için nasıl özür dilersin?", options: ["[EVENT] etkinliğine geç kaldığım için içtenlikle özür dilerim.", "[EVENT] niye bensiz başladı?", "[EVENT] nefret ederim.", "Herkese günaydın."], correct: 0 }
            ],
            en: [
                { q: "How do you politely ask for the location of [PLACE]?", options: ["Excuse me, could you tell me where [PLACE] is?", "Where is [PLACE]?", "I want [PLACE] now.", "Open [PLACE] for me."], correct: 0 },
                { q: "How do you order [FOOD] at a restaurant?", options: ["Can I have [FOOD], please?", "Give me [FOOD] immediately.", "Why don't you have [FOOD]?", "Is [FOOD] broken?"], correct: 0 },
                { q: "How do you ask the price of [ITEM] in a store?", options: ["How much does [ITEM] cost?", "Is [ITEM] free today?", "Why is [ITEM] here?", "Can I wear [ITEM]?"], correct: 0 },
                { q: "What do you say when someone helps you with [THING]?", options: ["Thank you so much for your help.", "Don't ever help me again.", "Where is [THING]?", "Goodbye now."], correct: 0 },
                { q: "How do you apologize for being late to [EVENT]?", options: ["I sincerely apologize for being late to [EVENT].", "Why did [EVENT] start without me?", "I hate [EVENT].", "Good morning everyone."], correct: 0 }
            ],
            es: [
                { q: "¿Cómo preguntas cortésmente por [PLACE] en la ciudad?", options: ["¿Podría decirme dónde está [PLACE]?", "¿Dónde está [PLACE]?", "Quiero [PLACE] ahora.", "Abre [PLACE]."], correct: 0 },
                { q: "¿Cómo pides [FOOD] en un restaurante?", options: ["¿Me podría traer [FOOD], por favor?", "Dame [FOOD] ya.", "No me gusta [FOOD].", "¿Dónde está [FOOD]?"], correct: 0 }
            ],
            de: [
                { q: "Wie fragt man höflich nach [PLACE]?", options: ["Könnten Sie mir sagen, wo [PLACE] ist?", "Wo ist [PLACE]?", "Ich will [PLACE].", "Gib mir [PLACE]."], correct: 0 }
            ],
            fr: [
                { q: "Comment demandez-vous poliment [PLACE] ?", options: ["Pourriez-vous m'indiquer où se trouve [PLACE] ?", "Où est [PLACE] ?", "Je veux [PLACE].", "Au revoir."], correct: 0 }
            ],
            it: [
                { q: "Come chiedi gentilmente [PLACE]?", options: ["Saprebbe dirmi dov'è [PLACE]?", "Dov'è [PLACE]?", "Voglio [PLACE].", "Ciao."], correct: 0 }
            ],
            ru: [
                { q: "Как вежливо спросить где находится [PLACE]?", options: ["Скажите, пожалуйста, где находится [PLACE]?", "Где [PLACE]?", "Я хочу [PLACE].", "Пока."], correct: 0 }
            ],
            ko: [
                { q: "[PLACE]의 곹을 정중하게 물어보는 방법은 무엇입니까?", options: ["[PLACE]가 어디에 있는지 알려주시겠어요?", "[PLACE]가 어디에요?", "[PLACE]를 주세요.", "안녕히 가세요."], correct: 0 }
            ],
            ja: [
                { q: "[PLACE]への行き方を丁寧に尋ねる表現は？", options: ["[PLACE]はどこにあるか教えていただけますか？", "[PLACE]はどこですか？", "[PLACE]をください。", "さようなら。"], correct: 0 }
            ]
        };

        const replacementTokens = {
            tr: {
                places: ["metro istasyonunun", "en yakın hastanenin", "merkezi bankanın", "havaalanı terminalinin", "müze çıkışının", "karakolun", "postanenin", "botanik bahçesinin"],
                foods: ["bir fincan espresso", "taze portakal suyu", "bir dilim çikolatalı kek", "ızgara tavuk sandviç", "vegan pizza", "sıcak yeşil çay"],
                items: ["bu deri ceketin", "şu dijital kameranın", "bu ahşap masanın", "kışlık montun", "koşu ayakkabısının"],
                things: ["ağır bavullarını", "bozuk projeksiyonu", "kayıp anahtarları bulma", "market poşetlerini taşıma"],
                events: ["sabah toplantısına", "uluslararası konferansa", "sanat atölyesine", "proje sunumuna"]
            },
            en: {
                places: ["the subway station", "the nearest hospital", "the central bank", "the airport terminal", "the museum exit", "the police station", "the post office", "the botanical garden"],
                foods: ["a cup of espresso", "fresh orange juice", "a slice of chocolate cake", "a grilled chicken sandwich", "vegan pizza", "hot green tea"],
                items: ["this leather jacket", "that digital camera", "this wooden table", "the winter coat", "the running shoes"],
                things: ["your heavy luggage", "the broken projector", "finding the lost keys", "carrying the grocery bags"],
                events: ["the morning meeting", "the international conference", "the art workshop", "the project presentation"]
            }
        };

        let usedQuestionSignatures = new Set();

        function generateUniqueQuestion(interfaceLang, quizLang) {
            const sourceKey = (interfaceLang === 'tr') ? 'tr' : quizLang;
            const templates = poolTemplates[sourceKey] || poolTemplates["en"];
            let templateIndex = Math.floor(Math.random() * templates.length);
            let template = templates[templateIndex];

            const tokenSet = replacementTokens[quizLang] || replacementTokens["en"];
            const trTokenSet = replacementTokens["tr"];

            let pIndex = Math.floor(Math.random() * tokenSet.places.length);
            let fIndex = Math.floor(Math.random() * tokenSet.foods.length);
            let iIndex = Math.floor(Math.random() * tokenSet.items.length);
            let thIndex = Math.floor(Math.random() * tokenSet.things.length);
            let evIndex = Math.floor(Math.random() * tokenSet.events.length);

            let qText = template.q
                .replace("[PLACE]", interfaceLang === 'tr' ? trTokenSet.places[pIndex] : tokenSet.places[pIndex])
                .replace("[FOOD]", interfaceLang === 'tr' ? trTokenSet.foods[fIndex] : tokenSet.foods[fIndex])
                .replace("[ITEM]", interfaceLang === 'tr' ? trTokenSet.items[iIndex] : tokenSet.items[iIndex])
                .replace("[THING]", interfaceLang === 'tr' ? trTokenSet.things[thIndex] : tokenSet.things[thIndex])
                .replace("[EVENT]", interfaceLang === 'tr' ? trTokenSet.events[evIndex] : tokenSet.events[evIndex]);
            
            if (usedQuestionSignatures.has(qText)) {
                return generateUniqueQuestion(interfaceLang, quizLang);
            }
            usedQuestionSignatures.add(qText);

            const targetTemplates = poolTemplates[quizLang] || poolTemplates["en"];
            let targetTemplate = targetTemplates[templateIndex] || targetTemplates[0];

            let opts = targetTemplate.options.map(opt => opt
                .replace("[PLACE]", tokenSet.places[pIndex])
                .replace("[FOOD]", tokenSet.foods[fIndex])
                .replace("[ITEM]", tokenSet.items[iIndex])
                .replace("[THING]", tokenSet.things[thIndex])
                .replace("[EVENT]", tokenSet.events[evIndex])
                .replace("[PLACE_OR_FOOD]", tokenSet.foods[fIndex])
            );
            
            let indexedOptions = opts.map((opt, idx) => ({ text: opt, isCorrect: idx === targetTemplate.correct }));
            let shuffledOptions = shuffleArray(indexedOptions);
            let newCorrectIndex = shuffledOptions.findIndex(o => o.isCorrect);

            return {
                questionText: qText,
                options: shuffledOptions.map(o => o.text),
                correct: newCorrectIndex
            };
        }

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
            
            usedQuestionSignatures.clear();

            activeQuestions = [];
            for (let i = 0; i < 10; i++) {
                activeQuestions.push(generateUniqueQuestion(appLang, currentLang));
            }

            document.getElementById("scoreBox").innerText = "";
            document.getElementById("nextBtn").style.display = "none";

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
                        <div class="error-q">❓ ${err.questionText}</div>
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

            let rankingList = [...botScores, { name: userNickname, xp: userXP, isUser: true }];
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

        function openFriendsScreen() {
            document.querySelectorAll(".screen").forEach(s => s.classList.remove("active"));
            document.getElementById("friendsScreen").classList.add("active");

            document.getElementById("nicknameInput").value = userNickname === "Sen" ? "" : userNickname;
            renderFriendsList();
        }

        function saveNickname() {
            const inputVal = document.getElementById("nicknameInput").value.trim();
            if (inputVal !== "") {
                userNickname = inputVal;
                localStorage.setItem("userNickname", userNickname);
                alert(appLang === 'tr' ? "Takma adınız başarıyla kaydedildi!" : "Nickname saved successfully!");
            } else {
                alert(appLang === 'tr' ? "Lütfen geçerli bir ad girin." : "Please enter a valid name.");
            }
        }

        function addFriend() {
            const friendInput = document.getElementById("friendUsernameInput");
            const friendName = friendInput.value.trim();
            const t = uiTexts[appLang];

            if (friendName !== "") {
                if (!friendList.includes(friendName)) {
                    friendList.push(friendName);
                    localStorage.setItem("friendList", JSON.stringify(friendList));
                    friendInput.value = "";
                    renderFriendsList();
                } else {
                    alert(appLang === 'tr' ? "Bu kişi zaten arkadaş listende!" : "This user is already in your friends list!");
                }
            }
        }

        function renderFriendsList() {
            const container = document.getElementById("friendsContainer");
            const t = uiTexts[appLang];

            if (friendList.length === 0) {
                container.innerHTML = `<p style="text-align: center; color: #666; font-style: italic; font-size: 13px;">${t.noFriends}</p>`;
            } else {
                container.innerHTML = friendList.map((friend, idx) => `
                    <div class="league-row">
                        <span>👤 ${friend}</span>
                        <button type="button" onclick="removeFriend(${idx})" style="background: #e74c3c; color: white; border: none; padding: 4px 8px; border-radius: 4px; cursor: pointer; font-size: 11px;">Sil</button>
                    </div>
                `).join('');
            }
        }

        function removeFriend(index) {
            friendList.splice(index, 1);
            localStorage.setItem("friendList", JSON.stringify(friendList));
            renderFriendsList();
        }

        function openBadgesScreen() {
            document.querySelectorAll(".screen").forEach(s => s.classList.remove("active"));
            document.getElementById("badgesScreen").classList.add("active");

            const container = document.getElementById("badgesContainer");
            const badgesList = [
                { title: "💎 Elmas Çırağı", desc: appLang === 'tr' ? "Elmas çeyrek finalinde ilk 3 içine girerek açılır." : "Top 3 in Quarter-Final.", unlocked: badgeApprentice, icon: "🥉" },
                { title: "👑 Elmas Ustası", desc: appLang === 'tr' ? "Yarı finallerde ilk 3'te bitirilince açılır." : "Top 3 in Semi-Finals.", unlocked: badgeMaster, icon: "🥈" },
                { title: "⚡ Elmas Prosu", desc: appLang === 'tr' ? "Elmas finallerinde ilk 3'te bitirilince açılır." : "Top 3 in Finals.", unlocked: badgePro, icon: "🥇" },
                { title: "🔥 Elmas Gücü", desc: appLang === 'tr' ? "Elmas finalleri 1. olarak bitirilince açılır." : "1st place in Finals.", unlocked: badgePower, icon: "💎" }
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
                    feedback.innerText = appLang === 'tr' ? `Doğru! ${currentLessonStep}. ders tamamlandı...` : `Correct! Lesson ${currentLessonStep} completed...`;
                    currentLessonStep++;
                    setTimeout(loadNextLessonStep, 1800);
                } else {
                    feedback.innerText = appLang === 'tr' ? "Tebrikler! 3 can kazandın!" : "Congratulations! Earned 3 lives!";
                    lives = 3;
                    setTimeout(goHome, 2000);
                }
            } else {
                btns[selectedIndex].classList.add("wrong");
                btns[correctIndex].classList.add("correct");
                feedback.style.color = "#e74c3c";
                feedback.innerText = appLang === 'tr' ? "Yanlış! Baştan deneniyor..." : "Wrong! Retrying...";
                setTimeout(loadNextLessonStep, 2200);
            }
        }

        function loadQuestion() {
            wrongAttemptsOnCurrentQuestion = 0;
            document.getElementById("feedbackMsg").innerText = "";
            document.getElementById("nextBtn").style.display = "none";

            const data = activeQuestions[currentIndex];
            const container = document.getElementById("quizContainer");

            container.innerHTML = `
                <div class="question-title">${data.questionText}</div>
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
                feedbackMsg.innerText = "Tebrikler, doğru!";
                score++;
                checkGameFlow(true);
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
                    
                    if (!userErrors.some(e => e.questionText === data.questionText)) {
                        userErrors.push({
                            questionText: data.questionText,
                            correctAnswer: data.options[data.correct]
                        });
                    }

                    lives--;

                    feedbackMsg.style.color = "#e74c3c";
                    if (lives > 0) {
                        feedbackMsg.innerText = t.wrongSecondMsg;
                        checkGameFlow(false);
                    } else {
                        feedbackMsg.innerText = t.outOfLivesMsg;
                        setTimeout(goHome, 2000); 
                    }
                }
            }
        }

        function checkGameFlow(isCorrectAnswer) {
            const totalQuestions = activeQuestions.length;
            const t = uiTexts[appLang];
            if (currentIndex < totalQuestions - 1) {
                document.getElementById("nextBtn").style.display = "block";
            } else {
                if (isCorrectAnswer) {
                    userXP += 10;
                    localStorage.setItem("userXP", userXP);
                    handleStreakAfterCompletion();
                }
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
