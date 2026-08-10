<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>English Learning Hub</title>
    <style>
        /* ───────── RESET & BASE ───────── */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #f4f7fb;
            color: #1a2a3a;
            line-height: 1.6;
            padding: 20px;
        }
        a {
            color: #2a7de1;
            text-decoration: none;
        }
        a:hover {
            text-decoration: underline;
        }

        /* ───────── LAYOUT ───────── */
        .app-container {
            max-width: 1100px;
            margin: 0 auto;
            background: #fff;
            border-radius: 24px;
            box-shadow: 0 12px 40px rgba(0, 0, 0, 0.08);
            padding: 24px 28px 40px;
            min-height: 90vh;
        }

        /* ───────── HEADER ───────── */
        .app-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            border-bottom: 2px solid #eef2f6;
            padding-bottom: 16px;
            margin-bottom: 24px;
        }
        .app-header h1 {
            font-size: 26px;
            font-weight: 700;
            color: #0b1e2e;
            letter-spacing: -0.3px;
        }
        .app-header h1 span {
            color: #2a7de1;
        }
        .header-stats {
            font-size: 15px;
            background: #eef4fa;
            padding: 6px 18px;
            border-radius: 40px;
            color: #1a3a5a;
        }
        .header-stats strong {
            color: #2a7de1;
        }

        /* ───────── NAV ───────── */
        .main-nav {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 28px;
            border-bottom: 1px solid #e8edf3;
            padding-bottom: 14px;
        }
        .main-nav button {
            background: transparent;
            border: none;
            padding: 8px 20px;
            border-radius: 40px;
            font-size: 14px;
            font-weight: 600;
            color: #4a5a6a;
            cursor: pointer;
            transition: all 0.2s;
        }
        .main-nav button:hover {
            background: #eef4fa;
            color: #1a2a3a;
        }
        .main-nav button.active {
            background: #2a7de1;
            color: #fff;
            box-shadow: 0 4px 12px rgba(42, 125, 225, 0.25);
        }

        /* ───────── PAGES ───────── */
        .page {
            display: none;
            animation: fadeUp 0.3s ease;
        }
        .page.active {
            display: block;
        }
        @keyframes fadeUp {
            0% {
                opacity: 0;
                transform: translateY(12px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* ───────── CARDS / GRID ───────── */
        .grid-2 {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
        }
        .grid-3 {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 16px;
        }
        .card {
            background: #f9fbfd;
            border-radius: 16px;
            padding: 20px 22px;
            border: 1px solid #e8edf3;
            transition: transform 0.15s, box-shadow 0.15s;
        }
        .card:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.04);
        }
        .card h3 {
            font-size: 18px;
            margin-bottom: 6px;
        }
        .card p {
            color: #4a5a6a;
            font-size: 14px;
        }
        .card .badge {
            display: inline-block;
            background: #dce6f0;
            padding: 2px 14px;
            border-radius: 40px;
            font-size: 12px;
            font-weight: 600;
            color: #1a3a5a;
            margin-top: 8px;
        }
        .card .badge.done {
            background: #c8e6d9;
            color: #0f6b3a;
        }

        /* ───────── BUTTONS ───────── */
        .btn {
            display: inline-block;
            background: #2a7de1;
            color: #fff;
            border: none;
            padding: 8px 24px;
            border-radius: 40px;
            font-weight: 600;
            font-size: 14px;
            cursor: pointer;
            transition: background 0.2s;
        }
        .btn:hover {
            background: #1b5fb0;
        }
        .btn-outline {
            background: transparent;
            color: #2a7de1;
            border: 2px solid #2a7de1;
        }
        .btn-outline:hover {
            background: #2a7de1;
            color: #fff;
        }
        .btn-sm {
            padding: 4px 16px;
            font-size: 13px;
        }
        .btn-success {
            background: #1f9a6e;
        }
        .btn-success:hover {
            background: #157a56;
        }
        .btn-danger {
            background: #d14c4c;
        }
        .btn-danger:hover {
            background: #b33a3a;
        }

        /* ───────── PROGRESS BAR ───────── */
        .progress-bar {
            width: 100%;
            height: 8px;
            background: #e8edf3;
            border-radius: 40px;
            overflow: hidden;
            margin: 10px 0 6px;
        }
        .progress-bar .fill {
            height: 100%;
            background: #2a7de1;
            border-radius: 40px;
            transition: width 0.3s;
        }
        .progress-label {
            display: flex;
            justify-content: space-between;
            font-size: 13px;
            color: #4a5a6a;
        }

        /* ───────── VOCABULARY ───────── */
        .word-card {
            background: #f9fbfd;
            border-radius: 16px;
            padding: 24px;
            border: 1px solid #e8edf3;
            text-align: center;
            margin-bottom: 16px;
        }
        .word-card .word {
            font-size: 32px;
            font-weight: 700;
        }
        .word-card .meaning {
            font-size: 20px;
            color: #2a7de1;
            margin: 8px 0 4px;
        }
        .word-card .example {
            font-style: italic;
            color: #4a5a6a;
            font-size: 15px;
        }
        .word-card .bn {
            font-size: 18px;
            color: #1a5a3a;
        }

        /* ───────── GRAMMAR ───────── */
        .grammar-explain {
            background: #f0f6fe;
            border-radius: 12px;
            padding: 16px 20px;
            margin: 12px 0;
            border-left: 4px solid #2a7de1;
        }
        .grammar-explain .bn {
            color: #1a5a3a;
            margin-top: 6px;
            font-size: 15px;
        }

        /* ───────── READING ───────── */
        .passage {
            background: #f9fbfd;
            border-radius: 16px;
            padding: 20px 24px;
            border: 1px solid #e8edf3;
            font-size: 16px;
            line-height: 1.8;
            margin-bottom: 16px;
        }
        .passage .clickable {
            color: #2a7de1;
            cursor: pointer;
            font-weight: 600;
            border-bottom: 2px dotted #2a7de1;
            transition: background 0.15s;
        }
        .passage .clickable:hover {
            background: #e0ecfe;
        }
        .word-tooltip {
            background: #1a2a3a;
            color: #fff;
            padding: 6px 14px;
            border-radius: 8px;
            font-size: 14px;
            position: fixed;
            pointer-events: none;
            z-index: 999;
            max-width: 260px;
            box-shadow: 0 8px 24px rgba(0, 0, 0, 0.2);
        }

        /* ───────── LISTENING ───────── */
        .audio-controls {
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
            align-items: center;
            margin: 12px 0;
        }
        .audio-controls button {
            background: #eef4fa;
            border: none;
            padding: 8px 20px;
            border-radius: 40px;
            font-weight: 600;
            cursor: pointer;
            transition: background 0.2s;
        }
        .audio-controls button:hover {
            background: #dce6f0;
        }
        .audio-controls button.playing {
            background: #2a7de1;
            color: #fff;
        }

        /* ───────── SPEAKING ───────── */
        .speaking-prompt {
            font-size: 22px;
            font-weight: 600;
            text-align: center;
            padding: 20px;
            background: #f0f6fe;
            border-radius: 16px;
            margin-bottom: 16px;
        }
        .speaking-result {
            background: #eef4fa;
            border-radius: 12px;
            padding: 12px 18px;
            min-height: 48px;
            margin: 10px 0;
            font-size: 16px;
            color: #1a2a3a;
        }
        .speaking-result .highlight {
            color: #2a7de1;
            font-weight: 600;
        }

        /* ───────── QUIZ / EXERCISE ───────── */
        .quiz-option {
            display: block;
            width: 100%;
            text-align: left;
            background: #f9fbfd;
            border: 2px solid #e8edf3;
            border-radius: 12px;
            padding: 12px 18px;
            margin: 6px 0;
            cursor: pointer;
            transition: all 0.15s;
            font-size: 15px;
        }
        .quiz-option:hover {
            background: #eef4fa;
            border-color: #b0c8e0;
        }
        .quiz-option.correct {
            background: #c8e6d9;
            border-color: #1f9a6e;
        }
        .quiz-option.wrong {
            background: #f8d6d6;
            border-color: #d14c4c;
        }
        .quiz-option.disabled {
            cursor: default;
            opacity: 0.8;
        }

        /* ───────── WRITING ───────── */
        .writing-prompt-box {
            background: #f0f6fe;
            border-radius: 16px;
            padding: 18px 22px;
            border-left: 4px solid #2a7de1;
            margin-bottom: 16px;
        }
        .writing-prompt-box h4 {
            font-size: 18px;
            margin-bottom: 4px;
        }
        .writing-prompt-box .tip {
            font-size: 14px;
            color: #4a5a6a;
        }

        /* ───────── DICTATION ───────── */
        .dictation-input {
            width: 100%;
            padding: 12px 18px;
            border-radius: 12px;
            border: 2px solid #e8edf3;
            font-size: 16px;
            font-family: inherit;
            transition: border 0.2s;
            resize: vertical;
            min-height: 60px;
        }
        .dictation-input:focus {
            border-color: #2a7de1;
            outline: none;
        }

        /* ───────── RESPONSIVE ───────── */
        @media (max-width: 640px) {
            .app-container {
                padding: 16px;
            }
            .app-header {
                flex-direction: column;
                align-items: flex-start;
                gap: 8px;
            }
            .main-nav button {
                padding: 6px 14px;
                font-size: 13px;
            }
            .grid-2 {
                grid-template-columns: 1fr;
            }
            .grid-3 {
                grid-template-columns: 1fr 1fr;
            }
        }

        /* ───────── UTILITY ───────── */
        .mt-8 {
            margin-top: 8px;
        }
        .mt-12 {
            margin-top: 12px;
        }
        .mt-16 {
            margin-top: 16px;
        }
        .mb-12 {
            margin-bottom: 12px;
        }
        .mb-16 {
            margin-bottom: 16px;
        }
        .text-center {
            text-align: center;
        }
        .text-muted {
            color: #4a5a6a;
            font-size: 14px;
        }
        .flex-between {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 8px;
        }
        .gap-8 {
            gap: 8px;
        }
        .hidden {
            display: none !important;
        }
        .status-msg {
            padding: 10px 16px;
            border-radius: 12px;
            margin: 8px 0;
        }
        .status-msg.success {
            background: #c8e6d9;
            color: #0f6b3a;
        }
        .status-msg.error {
            background: #f8d6d6;
            color: #8a2e2e;
        }
        .status-msg.info {
            background: #dce6f0;
            color: #1a3a5a;
        }
    </style>
</head>
<body>

    <div class="app-container" id="app">
        <!-- ─── HEADER ─── -->
        <header class="app-header">
            <h1>📘 English <span>Learning Hub</span></h1>
            <div class="header-stats">
                ⭐ Overall: <strong id="overallProgress">0%</strong>
            </div>
        </header>

        <!-- ─── NAV ─── -->
        <nav class="main-nav" id="mainNav">
            <button class="active" data-page="dashboard">🏠 Dashboard</button>
            <button data-page="vocabulary">📚 Vocabulary</button>
            <button data-page="grammar">📖 Grammar</button>
            <button data-page="reading">📄 Reading</button>
            <button data-page="writing">✍️ Writing</button>
            <button data-page="listening">🎧 Listening</button>
            <button data-page="speaking">🎤 Speaking</button>
        </nav>

        <!-- ─── PAGES ─── -->
        <!-- DASHBOARD -->
        <section class="page active" id="page-dashboard">
            <h2>🏠 Dashboard</h2>
            <p class="text-muted mb-16">Track your progress across all learning paths.</p>

            <div class="grid-2" id="dashboardCards">
                <!-- populated by JS -->
            </div>

            <div class="card mt-16">
                <h3>📊 Overall Progress</h3>
                <div class="progress-bar">
                    <div class="fill" id="overallFill" style="width:0%"></div>
                </div>
                <div class="progress-label">
                    <span>Total mastered</span>
                    <span id="overallLabel">0 / 0</span>
                </div>
                <p class="text-muted mt-8">💡 All progress is saved automatically in your browser.</p>
            </div>
        </section>

        <!-- VOCABULARY -->
        <section class="page" id="page-vocabulary">
            <h2>📚 Vocabulary</h2>
            <div class="flex-between mb-12">
                <span class="text-muted">Learn words by category.</span>
                <div>
                    <button class="btn btn-sm btn-outline" id="vocabReset">Reset Progress</button>
                </div>
            </div>

            <div class="grid-3 mb-16" id="vocabCategories">
                <!-- populated by JS -->
            </div>

            <div id="vocabWordArea">
                <!-- word card + quiz -->
            </div>
        </section>

        <!-- GRAMMAR -->
        <section class="page" id="page-grammar">
            <h2>📖 Grammar</h2>
            <p class="text-muted mb-12">Topics by difficulty with explanations in English &amp; Bangla.</p>

            <div class="grid-3 mb-16" id="grammarTopics">
                <!-- populated by JS -->
            </div>

            <div id="grammarDetailArea">
                <!-- detail + exercise -->
            </div>
        </section>

        <!-- READING -->
        <section class="page" id="page-reading">
            <h2>📄 Reading</h2>
            <p class="text-muted mb-12">Read passages and click any word to see its Bangla meaning.</p>

            <div class="grid-2 mb-16" id="readingPassages">
                <!-- populated by JS -->
            </div>

            <div id="readingDetailArea">
                <!-- passage + questions -->
            </div>
        </section>

        <!-- WRITING -->
        <section class="page" id="page-writing">
            <h2>✍️ Writing</h2>
            <p class="text-muted mb-12">Guided prompts with sentence-building tips.</p>

            <div id="writingArea">
                <!-- populated by JS -->
            </div>
        </section>

        <!-- LISTENING -->
        <section class="page" id="page-listening">
            <h2>🎧 Listening</h2>
            <p class="text-muted mb-12">Listen to passages (browser TTS) and answer questions.</p>

            <div id="listeningArea">
                <!-- populated by JS -->
            </div>
        </section>

        <!-- SPEAKING -->
        <section class="page" id="page-speaking">
            <h2>🎤 Speaking</h2>
            <p class="text-muted mb-12">Repeat phrases and get feedback via speech recognition.</p>
            <div class="status-msg info" id="speakingStatus">
                🎙️ Click "Start Speaking" and allow microphone access when prompted.
            </div>

            <div id="speakingArea">
                <!-- populated by JS -->
            </div>
        </section>
    </div>

    <script>
        // ═══════════════════════════════════════════════════════════════
        //  DATA
        // ═══════════════════════════════════════════════════════════════

        const VOCAB_DATA = {
            categories: ['Food', 'Animals', 'Everyday', 'Emotions', 'Actions'],
            words: {
                Food: [
                    { en: 'Apple', bn: 'আপেল', example: 'I eat an apple every day.' },
                    { en: 'Bread', bn: 'রুটি', example: 'She bought fresh bread.' },
                    { en: 'Rice', bn: 'ভাত', example: 'Rice is a staple food.' },
                    { en: 'Milk', bn: 'দুধ', example: 'The child drinks milk.' },
                ],
                Animals: [
                    { en: 'Cat', bn: 'বিড়াল', example: 'The cat is sleeping.' },
                    { en: 'Dog', bn: 'কুকুর', example: 'Dogs are loyal animals.' },
                    { en: 'Bird', bn: 'পাখি', example: 'The bird sings beautifully.' },
                    { en: 'Fish', bn: 'মাছ', example: 'Fish live in water.' },
                ],
                Everyday: [
                    { en: 'Book', bn: 'বই', example: 'I read a book every night.' },
                    { en: 'House', bn: 'বাড়ি', example: 'Our house is big.' },
                    { en: 'Water', bn: 'পানি', example: 'Drink plenty of water.' },
                    { en: 'Light', bn: 'আলো', example: 'The sun gives light.' },
                ],
                Emotions: [
                    { en: 'Happy', bn: 'খুশি', example: 'She feels happy today.' },
                    { en: 'Sad', bn: 'দুঃখী', example: 'He was sad after the news.' },
                    { en: 'Angry', bn: 'রাগী', example: 'The teacher looked angry.' },
                    { en: 'Excited', bn: 'উত্তেজিত', example: 'They are excited for the trip.' },
                ],
                Actions: [
                    { en: 'Run', bn: 'দৌড়ানো', example: 'I run every morning.' },
                    { en: 'Eat', bn: 'খাওয়া', example: 'We eat together.' },
                    { en: 'Read', bn: 'পড়া', example: 'She reads a lot.' },
                    { en: 'Write', bn: 'লেখা', example: 'He writes stories.' },
                ],
            }
        };

        const GRAMMAR_DATA = [{
            id: 'articles',
            title: 'Articles',
            difficulty: 'Beginner',
            explanation_en: 'Articles (a, an, the) are used before nouns. "A" and "an" are indefinite; "the" is definite. Use "a" before consonant sounds, "an" before vowel sounds.',
            explanation_bn: 'আর্টিকেল (a, an, the) বিশেষ্যের আগে বসে। "A" এবং "an" অনির্দিষ্ট; "the" নির্দিষ্ট। "a" ব্যবহার করা হয় ব্যঞ্জনধ্বনির আগে, "an" স্বরধ্বনির আগে।',
            exercises: [
                { q: 'I saw ___ elephant.', options: ['a', 'an', 'the'], answer: 1 },
                { q: '___ sun rises in the east.', options: ['A', 'An', 'The'], answer: 2 },
                { q: 'She has ___ cat.', options: ['a', 'an', 'the'], answer: 0 },
            ]
        }, {
            id: 'present-simple',
            title: 'Present Simple',
            difficulty: 'Beginner',
            explanation_en: 'Present simple describes habits, facts, and routines. Use the base form for I/you/we/they, and add -s for he/she/it.',
            explanation_bn: 'Present simple অভ্যাস, সত্য এবং রুটিন বর্ণনা করে। I/you/we/they-এর জন্য base form ব্যবহার করুন, he/she/it-এর জন্য -s যোগ করুন।',
            exercises: [
                { q: 'She ___ to school every day.', options: ['go', 'goes', 'going'], answer: 1 },
                { q: 'We ___ coffee in the morning.', options: ['drink', 'drinks', 'drinking'], answer: 0 },
                { q: 'He ___ English very well.', options: ['speak', 'speaks', 'speaking'], answer: 1 },
            ]
        }, {
            id: 'past-simple',
            title: 'Past Simple',
            difficulty: 'Beginner',
            explanation_en: 'Past simple describes completed actions in the past. Regular verbs add -ed; irregular verbs have special forms.',
            explanation_bn: 'Past simple অতীতে সম্পন্ন কাজ বর্ণনা করে। নিয়মিত ক্রিয়ার সাথে -ed যোগ হয়; অনিয়মিত ক্রিয়ার বিশেষ রূপ আছে।',
            exercises: [
                { q: 'She ___ a letter yesterday.', options: ['write', 'wrote', 'written'], answer: 1 },
                { q: 'We ___ to the park last Sunday.', options: ['go', 'went', 'gone'], answer: 1 },
                { q: 'He ___ his homework.', options: ['finish', 'finished', 'finishing'], answer: 1 },
            ]
        }, {
            id: 'future-simple',
            title: 'Future Simple',
            difficulty: 'Beginner',
            explanation_en: 'Future simple (will) describes predictions, promises, and spontaneous decisions.',
            explanation_bn: 'Future simple (will) ভবিষ্যদ্বাণী, প্রতিশ্রুতি এবং স্বতঃস্ফূর্ত সিদ্ধান্ত বর্ণনা করে।',
            exercises: [
                { q: 'I ___ you tomorrow.', options: ['call', 'will call', 'called'], answer: 1 },
                { q: 'It ___ rain later.', options: ['will', 'is', 'does'], answer: 0 },
                { q: 'We ___ to the beach.', options: ['go', 'will go', 'went'], answer: 1 },
            ]
        }, {
            id: 'present-continuous',
            title: 'Present Continuous',
            difficulty: 'Intermediate',
            explanation_en: 'Present continuous describes actions happening right now or around now. Form: am/is/are + verb-ing.',
            explanation_bn: 'Present continuous এখন বা এখনকার সময়ে ঘটছে এমন কাজ বর্ণনা করে। রূপ: am/is/are + verb-ing।',
            exercises: [
                { q: 'She ___ a book right now.', options: ['read', 'reads', 'is reading'], answer: 2 },
                { q: 'They ___ for the bus.', options: ['wait', 'are waiting', 'waits'], answer: 1 },
                { q: 'He ___ dinner at the moment.', options: ['cook', 'is cooking', 'cooks'], answer: 1 },
            ]
        }, {
            id: 'present-perfect',
            title: 'Present Perfect',
            difficulty: 'Intermediate',
            explanation_en: 'Present perfect connects past and present. Form: have/has + past participle. Used for experiences, changes, and unfinished time.',
            explanation_bn: 'Present perfect অতীত ও বর্তমানকে সংযুক্ত করে। রূপ: have/has + past participle। অভিজ্ঞতা, পরিবর্তন এবং অসমাপ্ত সময়ের জন্য ব্যবহৃত হয়।',
            exercises: [
                { q: 'I ___ to London twice.', options: ['have been', 'went', 'go'], answer: 0 },
                { q: 'She ___ her homework already.', options: ['finish', 'has finished', 'finished'], answer: 1 },
                { q: 'We ___ each other for years.', options: ['know', 'have known', 'knew'], answer: 1 },
            ]
        }, {
            id: 'modals',
            title: 'Modals (can, must, should)',
            difficulty: 'Intermediate',
            explanation_en: 'Modals express ability, obligation, or advice. Can = ability, must = obligation, should = advice.',
            explanation_bn: 'Modals সামর্থ্য, বাধ্যবাধকতা বা পরামর্শ প্রকাশ করে। Can = সামর্থ্য, must = বাধ্যবাধকতা, should = পরামর্শ।',
            exercises: [
                { q: 'You ___ stop at the red light.', options: ['can', 'must', 'should'], answer: 1 },
                { q: 'I ___ swim very well.', options: ['can', 'must', 'should'], answer: 0 },
                { q: 'You ___ drink more water.', options: ['can', 'must', 'should'], answer: 2 },
            ]
        }, {
            id: 'passive-voice',
            title: 'Passive Voice',
            difficulty: 'Advanced',
            explanation_en: 'Passive voice focuses on the action, not the doer. Form: be + past participle. Used when the doer is unknown or unimportant.',
            explanation_bn: 'Passive voice কাজের উপর গুরুত্ব দেয়, কর্তার উপর নয়। রূপ: be + past participle। যখন কর্তা অজানা বা গুরুত্বহীন তখন ব্যবহৃত হয়।',
            exercises: [
                { q: 'The letter ___ by the postman.', options: ['delivered', 'was delivered', 'is deliver'], answer: 1 },
                { q: 'The cake ___ by my sister.', options: ['made', 'was made', 'is make'], answer: 1 },
                { q: 'The report ___ tomorrow.', options: ['will complete', 'will be completed', 'is completing'], answer: 1 },
            ]
        }, {
            id: 'conditionals',
            title: 'Conditionals',
            difficulty: 'Advanced',
            explanation_en: 'Conditionals express "if... then" situations. Type 1 (real): if + present, will + base. Type 2 (unreal): if + past, would + base.',
            explanation_bn: 'Conditionals "যদি... তাহলে" পরিস্থিতি প্রকাশ করে। Type 1 (বাস্তব): if + present, will + base। Type 2 (অবাস্তব): if + past, would + base।',
            exercises: [
                { q: 'If it rains, I ___ stay home.', options: ['will', 'would', 'can'], answer: 0 },
                { q: 'If I ___ you, I would say sorry.', options: ['am', 'were', 'was'], answer: 1 },
                { q: 'If she ___ early, we will catch the train.', options: ['leave', 'leaves', 'left'], answer: 1 },
            ]
        }, ];

        const READING_DATA = [{
            id: 'passage1',
            title: 'The Morning Walk',
            text: 'Every morning, Sarah wakes up at 6 AM. She puts on her shoes and goes for a walk in the park. The park is full of trees and flowers. She loves to hear the birds singing. After the walk, she feels fresh and ready for the day. Many people in the neighborhood also walk in the morning. They greet each other with a smile. Sarah thinks that a morning walk is the best way to start the day.',
            words: {
                'wakes': 'জাগে',
                'puts': 'পরিধান করে',
                'shoes': 'জুতো',
                'park': 'পার্ক',
                'trees': 'গাছ',
                'flowers': 'ফুল',
                'birds': 'পাখি',
                'singing': 'গান গাওয়া',
                'fresh': 'সতেজ',
                'neighborhood': 'পাড়া',
                'greet': 'অভিবাদন জানায়',
                'smile': 'হাসি',
            },
            questions: [
                { q: 'What time does Sarah wake up?', options: ['5 AM', '6 AM', '7 AM'], answer: 1 },
                { q: 'Where does she go for a walk?', options: ['The beach', 'The park', 'The mall'], answer: 1 },
                { q: 'What does she hear in the park?', options: ['Cars', 'Birds singing', 'Children playing'], answer: 1 },
            ]
        }, {
            id: 'passage2',
            title: 'The Helpful Neighbor',
            text: 'Mr. Johnson is a kind man. He lives in a small house on Oak Street. Every Saturday, he helps his neighbors. He mows the lawn for Mrs. Green. He fixes the fence for Mr. Brown. He even teaches the children how to plant flowers. The neighbors love Mr. Johnson. They often bring him cookies and cakes. He says, "Helping others makes me happy." The whole street is like a big family.',
            words: {
                'kind': 'দয়ালু',
                'neighbors': 'প্রতিবেশী',
                'mows': 'কাটে',
                'lawn': 'লন',
                'fixes': 'মেরামত করে',
                'fence': 'বেড়া',
                'teaches': 'শেখায়',
                'plant': 'রোপণ করা',
                'cookies': 'কুকিজ',
                'whole': 'সমস্ত',
                'street': 'রাস্তা',
            },
            questions: [
                { q: 'What does Mr. Johnson do for Mrs. Green?', options: ['Mows the lawn', 'Fixes the fence', 'Teaches children'],
                    answer: 0 },
                { q: 'What do the neighbors bring him?', options: ['Flowers', 'Cookies and cakes', 'Books'], answer: 1 },
                { q: 'What does Mr. Johnson say?', options: ['Helping others makes me happy', 'I like money',
                        'Working is hard'
                    ], answer: 0 },
            ]
        }, {
            id: 'passage3',
            title: 'The Lost Key',
            text: 'Alice lost her house key yesterday. She looked everywhere. She checked her bag, her pockets, and the kitchen table. The key was not there. She felt worried. Then she remembered that she had taken off her jacket when she came home. She ran to the closet and found the key in her jacket pocket. She was very relieved. She said, "I should always check my pockets first!"',
            words: {
                'lost': 'হারিয়েছে',
                'key': 'চাবি',
                'checked': 'পরীক্ষা করেছে',
                'bag': 'ব্যাগ',
                'pockets': 'পকেট',
                'worried': 'চিন্তিত',
                'remembered': 'মনে করেছে',
                'jacket': 'জ্যাকেট',
                'closet': 'আলমারি',
                'relieved': 'স্বস্তি পেয়েছে',
            },
            questions: [
                { q: 'What did Alice lose?', options: ['Her phone', 'Her house key', 'Her wallet'], answer: 1 },
                { q: 'Where did she find the key?', options: ['In her bag', 'In her jacket pocket', 'On the table'],
                    answer: 1 },
                { q: 'How did she feel after finding the key?', options: ['Worried', 'Angry', 'Relieved'], answer: 2 },
            ]
        }, ];

        const WRITING_DATA = [{
            id: 'prompt1',
            title: 'Describe Your Morning',
            prompt: 'Write a paragraph about your morning routine. What do you do from the time you wake up until you leave home?',
            tips: [
                'Use present simple tense for habits.',
                'Use time words like "first", "then", "after that".',
                'Include at least 5 sentences.',
            ]
        }, {
            id: 'prompt2',
            title: 'Your Favorite Place',
            prompt: 'Describe your favorite place in your town or city. Why do you like it? What can you do there?',
            tips: [
                'Use adjectives to describe the place (beautiful, quiet, busy).',
                'Use prepositions of place (near, next to, across from).',
                'Give reasons for your choice.',
            ]
        }, {
            id: 'prompt3',
            title: 'A Memorable Event',
            prompt: 'Write about a memorable event from your life. What happened? Where were you? How did you feel?',
            tips: [
                'Use past simple and past continuous.',
                'Describe your feelings (happy, excited, nervous).',
                'Include details about the people and place.',
            ]
        }, ];

        const LISTENING_DATA = [{
            id: 'listen1',
            title: 'The Weekend Trip',
            text: 'Last weekend, my family and I went to the beach. The weather was sunny and warm. We swam in the ocean and built a sandcastle. In the evening, we watched the sunset. It was a beautiful day. We ate seafood at a small restaurant. Everyone had a wonderful time.',
            questions: [
                { q: 'Where did they go last weekend?', options: ['The mountains', 'The beach', 'The lake'],
                answer: 1 },
                { q: 'What did they build?', options: ['A sandcastle', 'A tent', 'A fire'], answer: 0 },
                { q: 'What did they eat?', options: ['Pizza', 'Seafood', 'Burgers'], answer: 1 },
            ],
            dictation: 'Last weekend, my family and I went to the beach.'
        }, {
            id: 'listen2',
            title: 'The Library',
            text: 'The public library is a quiet place where people can read and study. There are thousands of books on many topics. You can borrow books for free. The library also has computers and a children\'s section. Many students go there to do homework. The librarian is very helpful and friendly.',
            questions: [
                { q: 'What can you do at the library?', options: ['Read and study', 'Watch movies', 'Play games'],
                    answer: 0 },
                { q: 'What does the library have for children?', options: ['A playground', 'A children\'s section',
                        'A cafe'
                    ], answer: 1 },
                { q: 'Who is helpful at the library?', options: ['The guard', 'The librarian', 'The cleaner'],
                answer: 1 },
            ],
            dictation: 'The public library is a quiet place where people can read and study.'
        }, {
            id: 'listen3',
            title: 'Healthy Habits',
            text: 'Eating healthy food and exercising regularly are important for a good life. You should eat fruits and vegetables every day. Drinking enough water is also essential. It is good to walk or run for at least 30 minutes each day. Getting enough sleep helps your body and mind rest. These habits can make you feel strong and happy.',
            questions: [
                { q: 'What should you eat every day?', options: ['Fast food', 'Fruits and vegetables', 'Sweets'],
                    answer: 1 },
                { q: 'How long should you walk or run each day?', options: ['10 minutes', '30 minutes', '1 hour'],
                    answer: 1 },
                { q: 'What helps your body and mind rest?', options: ['Exercise', 'Sleep', 'Food'], answer: 1 },
            ],
            dictation: 'Eating healthy food and exercising regularly are important for a good life.'
        }, ];

        const SPEAKING_DATA = [
            { phrase: 'Good morning, how are you today?', hint: 'Say this to greet someone.' },
            { phrase: 'I would like to order a coffee, please.', hint: 'Use this at a café.' },
            { phrase: 'Could you please help me find the station?', hint: 'Ask for directions.' },
            { phrase: 'I really enjoyed the movie last night.', hint: 'Talk about entertainment.' },
            { phrase: 'What do you like to do on weekends?', hint: 'Ask about hobbies.' },
        ];

        // ═══════════════════════════════════════════════════════════════
        //  STATE
        // ═══════════════════════════════════════════════════════════════

        const state = {
            // progress: { vocabulary: { category: [wordIndex, ...] }, grammar: [topicId], reading: [passageId], writing: [
            //     promptId], listening: [listenId], speaking: [phraseIndex] }
            progress: loadProgress(),

            // current selections
            vocabCategory: null,
            vocabWordIndex: 0,
            grammarTopicId: null,
            readingPassageId: null,
            writingPromptId: null,
            listeningId: null,
            speakingIndex: 0,

            // quiz states
            vocabQuizAnswered: false,
            grammarQuizAnswered: false,
            readingQuizAnswered: false,
            listeningQuizAnswered: false,
            dictationAttempted: false,

            // speaking
            speakingListening: false,
            speakingResult: '',
        };

        function defaultProgress() {
            return {
                vocabulary: {}, // { category: [wordIndex, ...] }
                grammar: [],
                reading: [],
                writing: [],
                listening: [],
                speaking: [],
            };
        }

        function loadProgress() {
            try {
                const raw = localStorage.getItem('elhub_progress');
                if (raw) {
                    const p = JSON.parse(raw);
                    // ensure all keys exist
                    const def = defaultProgress();
                    for (const k of Object.keys(def)) {
                        if (!(k in p)) p[k] = def[k];
                    }
                    return p;
                }
            } catch (_) { /* ignore */ }
            return defaultProgress();
        }

        function saveProgress() {
            try {
                localStorage.setItem('elhub_progress', JSON.stringify(state.progress));
            } catch (_) { /* ignore */ }
            updateUI();
        }

        // ─── helpers ───
        function isWordLearned(category, idx) {
            const arr = state.progress.vocabulary[category] || [];
            return arr.includes(idx);
        }

        function markWordLearned(category, idx) {
            if (!state.progress.vocabulary[category]) state.progress.vocabulary[category] = [];
            if (!state.progress.vocabulary[category].includes(idx)) {
                state.progress.vocabulary[category].push(idx);
                saveProgress();
            }
        }

        function isGrammarDone(id) {
            return state.progress.grammar.includes(id);
        }

        function markGrammarDone(id) {
            if (!state.progress.grammar.includes(id)) {
                state.progress.grammar.push(id);
                saveProgress();
            }
        }

        function isReadingDone(id) {
            return state.progress.reading.includes(id);
        }

        function markReadingDone(id) {
            if (!state.progress.reading.includes(id)) {
                state.progress.reading.push(id);
                saveProgress();
            }
        }

        function isWritingDone(id) {
            return state.progress.writing.includes(id);
        }

        function markWritingDone(id) {
            if (!state.progress.writing.includes(id)) {
                state.progress.writing.push(id);
                saveProgress();
            }
        }

        function isListeningDone(id) {
            return state.progress.listening.includes(id);
        }

        function markListeningDone(id) {
            if (!state.progress.listening.includes(id)) {
                state.progress.listening.push(id);
                saveProgress();
            }
        }

        function isSpeakingDone(idx) {
            return state.progress.speaking.includes(idx);
        }

        function markSpeakingDone(idx) {
            if (!state.progress.speaking.includes(idx)) {
                state.progress.speaking.push(idx);
                saveProgress();
            }
        }

        function getOverallProgress() {
            const total = getTotalItems();
            const done = getDoneItems();
            return total === 0 ? 0 : Math.round((done / total) * 100);
        }

        function getTotalItems() {
            let count = 0;
            for (const cat of VOCAB_DATA.categories) {
                count += VOCAB_DATA.words[cat].length;
            }
            count += GRAMMAR_DATA.length;
            count += READING_DATA.length;
            count += WRITING_DATA.length;
            count += LISTENING_DATA.length;
            count += SPEAKING_DATA.length;
            return count;
        }

        function getDoneItems() {
            let count = 0;
            for (const cat of VOCAB_DATA.categories) {
                const arr = state.progress.vocabulary[cat] || [];
                count += arr.length;
            }
            count += state.progress.grammar.length;
            count += state.progress.reading.length;
            count += state.progress.writing.length;
            count += state.progress.listening.length;
            count += state.progress.speaking.length;
            return count;
        }

        // ═══════════════════════════════════════════════════════════════
        //  ROUTING / NAV
        // ═══════════════════════════════════════════════════════════════

        let currentPage = 'dashboard';

        function navigateTo(pageId) {
            // hide all pages
            document.querySelectorAll('.page').forEach(el => el.classList.remove('active'));
            // show target
            const target = document.getElementById('page-' + pageId);
            if (target) target.classList.add('active');
            // nav buttons
            document.querySelectorAll('.main-nav button').forEach(btn => {
                btn.classList.toggle('active', btn.dataset.page === pageId);
            });
            currentPage = pageId;
            // render the page
            renderPage(pageId);
        }

        document.getElementById('mainNav').addEventListener('click', (e) => {
            const btn = e.target.closest('button');
            if (btn && btn.dataset.page) {
                navigateTo(btn.dataset.page);
            }
        });

        // ═══════════════════════════════════════════════════════════════
        //  RENDER FUNCTIONS
        // ═══════════════════════════════════════════════════════════════

        function renderPage(pageId) {
            switch (pageId) {
                case 'dashboard':
                    renderDashboard();
                    break;
                case 'vocabulary':
                    renderVocabulary();
                    break;
                case 'grammar':
                    renderGrammar();
                    break;
                case 'reading':
                    renderReading();
                    break;
                case 'writing':
                    renderWriting();
                    break;
                case 'listening':
                    renderListening();
                    break;
                case 'speaking':
                    renderSpeaking();
                    break;
            }
            updateUI();
        }

        function updateUI() {
            const pct = getOverallProgress();
            document.getElementById('overallProgress').textContent = pct + '%';
            const fill = document.getElementById('overallFill');
            if (fill) fill.style.width = pct + '%';
            const label = document.getElementById('overallLabel');
            if (label) label.textContent = getDoneItems() + ' / ' + getTotalItems();
        }

        // ─── DASHBOARD ───
        function renderDashboard() {
            const container = document.getElementById('dashboardCards');
            const paths = [
                { id: 'vocabulary', label: '📚 Vocabulary', total: getVocabTotal(), done: getVocabDone() },
                { id: 'grammar', label: '📖 Grammar', total: GRAMMAR_DATA.length, done: state.progress.grammar.length },
                { id: 'reading', label: '📄 Reading', total: READING_DATA.length, done: state.progress.reading.length },
                { id: 'writing', label: '✍️ Writing', total: WRITING_DATA.length, done: state.progress.writing.length },
                { id: 'listening', label: '🎧 Listening', total: LISTENING_DATA.length, done: state.progress.listening
                        .length },
                { id: 'speaking', label: '🎤 Speaking', total: SPEAKING_DATA.length, done: state.progress.speaking.length },
            ];
            container.innerHTML = paths.map(p => {
                const pct = p.total === 0 ? 0 : Math.round((p.done / p.total) * 100);
                return `
              <div class="card">
                <div class="flex-between">
                  <h3>${p.label}</h3>
                  <span class="badge ${p.done === p.total && p.total > 0 ? 'done' : ''}">${p.done}/${p.total}</span>
                </div>
                <div class="progress-bar"><div class="fill" style="width:${pct}%"></div></div>
                <div class="progress-label"><span>${pct}%</span><span>${p.done === p.total && p.total > 0 ? '✅ Complete' : 'In progress'}</span></div>
              </div>
            `;
            }).join('');
        }

        function getVocabTotal() {
            let n = 0;
            for (const cat of VOCAB_DATA.categories) n += VOCAB_DATA.words[cat].length;
            return n;
        }

        function getVocabDone() {
            let n = 0;
            for (const cat of VOCAB_DATA.categories) {
                n += (state.progress.vocabulary[cat] || []).length;
            }
            return n;
        }

        // ─── VOCABULARY ───
        function renderVocabulary() {
            const catContainer = document.getElementById('vocabCategories');
            catContainer.innerHTML = VOCAB_DATA.categories.map(cat => {
                const words = VOCAB_DATA.words[cat] || [];
                const done = (state.progress.vocabulary[cat] || []).length;
                const total = words.length;
                const pct = total === 0 ? 0 : Math.round((done / total) * 100);
                return `
              <div class="card" data-category="${cat}" style="cursor:pointer">
                <h3>${cat}</h3>
                <div class="progress-bar"><div class="fill" style="width:${pct}%"></div></div>
                <div class="progress-label"><span>${done}/${total}</span><span>${pct}%</span></div>
              </div>
            `;
            }).join('');

            // click on category
            catContainer.querySelectorAll('.card').forEach(el => {
                el.addEventListener('click', () => {
                    const cat = el.dataset.category;
                    state.vocabCategory = cat;
                    state.vocabWordIndex = 0;
                    state.vocabQuizAnswered = false;
                    renderVocabWords(cat);
                });
            });

            // if no category selected, pick first
            if (!state.vocabCategory || !VOCAB_DATA.categories.includes(state.vocabCategory)) {
                state.vocabCategory = VOCAB_DATA.categories[0];
                state.vocabWordIndex = 0;
                state.vocabQuizAnswered = false;
            }
            renderVocabWords(state.vocabCategory);
        }

        function renderVocabWords(category) {
            const area = document.getElementById('vocabWordArea');
            const words = VOCAB_DATA.words[category] || [];
            if (words.length === 0) {
                area.innerHTML = '<p>No words in this category.</p>';
                return;
            }
            const idx = state.vocabWordIndex;
            const word = words[idx];
            if (!word) {
                // reset to 0
                state.vocabWordIndex = 0;
                renderVocabWords(category);
                return;
            }
            const learned = isWordLearned(category, idx);
            const total = words.length;
            const done = (state.progress.vocabulary[category] || []).length;

            let quizHtml = '';
            const qAnswered = state.vocabQuizAnswered;
            if (!qAnswered) {
                // generate a quiz: pick 4 options including the correct bn meaning
                const allMeanings = [...new Set(VOCAB_DATA.categories.flatMap(c => VOCAB_DATA.words[c].map(w => w.bn)))];
                const correct = word.bn;
                let options = [correct];
                const others = allMeanings.filter(m => m !== correct);
                // shuffle and pick up to 3 others
                const shuffled = others.sort(() => Math.random() - 0.5);
                for (let i = 0; i < Math.min(3, shuffled.length); i++) {
                    options.push(shuffled[i]);
                }
                options = options.sort(() => Math.random() - 0.5);
                quizHtml = `
              <div class="card mt-12">
                <p><strong>What is the Bangla meaning of "${word.en}"?</strong></p>
                ${options.map((opt, i) => `
                  <button class="quiz-option" data-opt="${opt}" data-correct="${correct}">${opt}</button>
                `).join('')}
              </div>
            `;
            } else {
                // show result
                const correct = word.bn;
                const msg = learned ? '✅ You got it right!' : '❌ Try again next time!';
                quizHtml = `
              <div class="card mt-12">
                <p><strong>Meaning of "${word.en}":</strong> <span style="color:#2a7de1;font-weight:600">${correct}</span></p>
                <p class="text-muted">${msg}</p>
                ${!learned ? `<button class="btn btn-sm btn-success mt-8" id="vocabMarkLearned">✅ Mark as Learned</button>` : ''}
                <button class="btn btn-sm btn-outline mt-8" id="vocabNextWord">Next Word →</button>
              </div>
            `;
            }

            area.innerHTML = `
            <div class="flex-between mb-8">
              <span class="text-muted">${category} — ${idx+1}/${total} (${done} learned)</span>
              <span class="badge ${learned ? 'done' : ''}">${learned ? '✅ Learned' : '📖 In progress'}</span>
            </div>
            <div class="word-card">
              <div class="word">${word.en}</div>
              <div class="meaning">${word.bn}</div>
              <div class="example">"${word.example}"</div>
            </div>
            ${quizHtml}
          `;

            // event listeners for quiz options
            if (!qAnswered) {
                area.querySelectorAll('.quiz-option').forEach(btn => {
                    btn.addEventListener('click', (e) => {
                        if (state.vocabQuizAnswered) return;
                        const chosen = btn.dataset.opt;
                        const correct = btn.dataset.correct;
                        const isCorrect = chosen === correct;
                        // disable all
                        area.querySelectorAll('.quiz-option').forEach(b => b.classList.add('disabled'));
                        if (isCorrect) {
                            btn.classList.add('correct');
                            markWordLearned(category, idx);
                        } else {
                            btn.classList.add('wrong');
                            // highlight correct
                            area.querySelectorAll('.quiz-option').forEach(b => {
                                if (b.dataset.opt === correct) b.classList.add('correct');
                            });
                        }
                        state.vocabQuizAnswered = true;
                        // re-render after short delay
                        setTimeout(() => renderVocabWords(category), 800);
                    });
                });
            } else {
                const markBtn = document.getElementById('vocabMarkLearned');
                if (markBtn) {
                    markBtn.addEventListener('click', () => {
                        markWordLearned(category, idx);
                        renderVocabWords(category);
                    });
                }
                const nextBtn = document.getElementById('vocabNextWord');
                if (nextBtn) {
                    nextBtn.addEventListener('click', () => {
                        state.vocabWordIndex = (idx + 1) % total;
                        state.vocabQuizAnswered = false;
                        renderVocabWords(category);
                    });
                }
            }
        }

        // vocab reset
        document.getElementById('vocabReset').addEventListener('click', () => {
            if (confirm('Reset all vocabulary progress?')) {
                state.progress.vocabulary = {};
                saveProgress();
                renderVocabulary();
            }
        });

        // ─── GRAMMAR ───
        function renderGrammar() {
            const container = document.getElementById('grammarTopics');
            container.innerHTML = GRAMMAR_DATA.map(topic => {
                const done = isGrammarDone(topic.id);
                return `
              <div class="card" data-grammar-id="${topic.id}" style="cursor:pointer">
                <div class="flex-between">
                  <h3>${topic.title}</h3>
                  <span class="badge ${done ? 'done' : ''}">${done ? '✅ Done' : topic.difficulty}</span>
                </div>
                <p class="text-muted">${topic.difficulty}</p>
              </div>
            `;
            }).join('');

            container.querySelectorAll('.card').forEach(el => {
                el.addEventListener('click', () => {
                    state.grammarTopicId = el.dataset.grammarId;
                    state.grammarQuizAnswered = false;
                    renderGrammarDetail(state.grammarTopicId);
                });
            });

            if (!state.grammarTopicId || !GRAMMAR_DATA.find(t => t.id === state.grammarTopicId)) {
                state.grammarTopicId = GRAMMAR_DATA[0].id;
                state.grammarQuizAnswered = false;
            }
            renderGrammarDetail(state.grammarTopicId);
        }

        function renderGrammarDetail(topicId) {
            const topic = GRAMMAR_DATA.find(t => t.id === topicId);
            if (!topic) return;
            const area = document.getElementById('grammarDetailArea');
            const done = isGrammarDone(topicId);
            let exerciseHtml = '';
            const qAnswered = state.grammarQuizAnswered;

            if (topic.exercises && topic.exercises.length > 0) {
                if (!qAnswered) {
                    exerciseHtml = topic.exercises.map((ex, i) => `
                <div class="card mt-8" data-ex="${i}">
                  <p><strong>${i+1}. ${ex.q}</strong></p>
                  ${ex.options.map((opt, oi) => `
                    <button class="quiz-option" data-ex="${i}" data-opt="${oi}" data-answer="${ex.answer}">${opt}</button>
                  `).join('')}
                </div>
              `).join('');
                } else {
                    // show results
                    exerciseHtml = topic.exercises.map((ex, i) => {
                        const allCorrect = true; // we'll just show answers
                        return `
                  <div class="card mt-8">
                    <p><strong>${i+1}. ${ex.q}</strong></p>
                    <p>✅ Correct answer: <strong>${ex.options[ex.answer]}</strong></p>
                  </div>
                `;
                    }).join('');
                    exerciseHtml += `
                <button class="btn btn-sm btn-outline mt-8" id="grammarResetQuiz">🔄 Try Again</button>
                ${!done ? `<button class="btn btn-sm btn-success mt-8" id="grammarMarkDone">✅ Mark as Complete</button>` : ''}
              `;
                }
            }

            area.innerHTML = `
            <div class="card">
              <div class="flex-between">
                <h3>${topic.title}</h3>
                <span class="badge ${done ? 'done' : ''}">${done ? '✅ Complete' : topic.difficulty}</span>
              </div>
              <div class="grammar-explain">
                <p>${topic.explanation_en}</p>
                <div class="bn">🇧🇩 ${topic.explanation_bn}</div>
              </div>
            </div>
            <h4 class="mt-12">📝 Practice Exercises</h4>
            ${exerciseHtml || '<p class="text-muted">No exercises available.</p>'}
          `;

            // quiz listeners
            if (!qAnswered) {
                area.querySelectorAll('.quiz-option').forEach(btn => {
                    btn.addEventListener('click', (e) => {
                        if (state.grammarQuizAnswered) return;
                        const exIdx = parseInt(btn.dataset.ex);
                        const chosen = parseInt(btn.dataset.opt);
                        const correct = parseInt(btn.dataset.answer);
                        const isCorrect = chosen === correct;
                        // disable all options for this exercise
                        const parent = btn.closest('[data-ex]');
                        parent.querySelectorAll('.quiz-option').forEach(b => b.classList.add('disabled'));
                        if (isCorrect) {
                            btn.classList.add('correct');
                        } else {
                            btn.classList.add('wrong');
                            parent.querySelectorAll('.quiz-option').forEach(b => {
                                if (parseInt(b.dataset.opt) === correct) b.classList.add('correct');
                            });
                        }
                        // check if all answered
                        const allEx = area.querySelectorAll('[data-ex]');
                        let allDone = true;
                        allEx.forEach(el => {
                            const opts = el.querySelectorAll('.quiz-option');
                            if (opts.length === 0) allDone = false;
                            else {
                                let hasDisabled = false;
                                opts.forEach(o => { if (o.classList.contains('disabled')) hasDisabled = true; });
                                if (!hasDisabled) allDone = false;
                            }
                        });
                        if (allDone) {
                            state.grammarQuizAnswered = true;
                            setTimeout(() => renderGrammarDetail(topicId), 600);
                        }
                    });
                });
            } else {
                const resetBtn = document.getElementById('grammarResetQuiz');
                if (resetBtn) {
                    resetBtn.addEventListener('click', () => {
                        state.grammarQuizAnswered = false;
                        renderGrammarDetail(topicId);
                    });
                }
                const markBtn = document.getElementById('grammarMarkDone');
                if (markBtn) {
                    markBtn.addEventListener('click', () => {
                        markGrammarDone(topicId);
                        renderGrammarDetail(topicId);
                    });
                }
            }
        }

        // ─── READING ───
        function renderReading() {
            const container = document.getElementById('readingPassages');
            container.innerHTML = READING_DATA.map(p => {
                const done = isReadingDone(p.id);
                return `
              <div class="card" data-reading-id="${p.id}" style="cursor:pointer">
                <div class="flex-between">
                  <h3>${p.title}</h3>
                  <span class="badge ${done ? 'done' : ''}">${done ? '✅ Done' : '📖 Read'}</span>
                </div>
              </div>
            `;
            }).join('');

            container.querySelectorAll('.card').forEach(el => {
                el.addEventListener('click', () => {
                    state.readingPassageId = el.dataset.readingId;
                    state.readingQuizAnswered = false;
                    renderReadingDetail(state.readingPassageId);
                });
            });

            if (!state.readingPassageId || !READING_DATA.find(p => p.id === state.readingPassageId)) {
                state.readingPassageId = READING_DATA[0].id;
                state.readingQuizAnswered = false;
            }
            renderReadingDetail(state.readingPassageId);
        }

        function renderReadingDetail(passageId) {
            const passage = READING_DATA.find(p => p.id === passageId);
            if (!passage) return;
            const area = document.getElementById('readingDetailArea');
            const done = isReadingDone(passageId);

            // build passage with clickable words
            let textHtml = passage.text;
            for (const [word, meaning] of Object.entries(passage.words)) {
                const regex = new RegExp(`\\b${word}\\b`, 'g');
                textHtml = textHtml.replace(regex, `<span class="clickable" data-word="${word}" data-meaning="${meaning}">${word}</span>`);
            }

            let questionsHtml = '';
            const qAnswered = state.readingQuizAnswered;

            if (passage.questions && passage.questions.length > 0) {
                if (!qAnswered) {
                    questionsHtml = passage.questions.map((q, i) => `
                <div class="card mt-8" data-rq="${i}">
                  <p><strong>${i+1}. ${q.q}</strong></p>
                  ${q.options.map((opt, oi) => `
                    <button class="quiz-option" data-rq="${i}" data-opt="${oi}" data-answer="${q.answer}">${opt}</button>
                  `).join('')}
                </div>
              `).join('');
                } else {
                    questionsHtml = passage.questions.map((q, i) => `
                <div class="card mt-8">
                  <p><strong>${i+1}. ${q.q}</strong></p>
                  <p>✅ Correct answer: <strong>${q.options[q.answer]}</strong></p>
                </div>
              `).join('');
                    questionsHtml += `
                <button class="btn btn-sm btn-outline mt-8" id="readingResetQuiz">🔄 Try Again</button>
                ${!done ? `<button class="btn btn-sm btn-success mt-8" id="readingMarkDone">✅ Mark as Complete</button>` : ''}
              `;
                }
            }

            area.innerHTML = `
            <div class="flex-between mb-8">
              <h3>${passage.title}</h3>
              <span class="badge ${done ? 'done' : ''}">${done ? '✅ Done' : '📖 Reading'}</span>
            </div>
            <div class="passage" id="passageText">${textHtml}</div>
            <p class="text-muted">💡 Click any <span class="clickable">highlighted word</span> to see its Bangla meaning.</p>
            <h4 class="mt-12">📝 Comprehension Questions</h4>
            ${questionsHtml || '<p class="text-muted">No questions available.</p>'}
          `;

            // clickable words tooltip
            area.querySelectorAll('.clickable').forEach(el => {
                el.addEventListener('click', (e) => {
                    const meaning = el.dataset.meaning;
                    const word = el.dataset.word;
                    showTooltip(e, `${word} → 🇧🇩 ${meaning}`);
                });
                el.addEventListener('mouseleave', hideTooltip);
            });

            // quiz listeners
            if (!qAnswered) {
                area.querySelectorAll('.quiz-option').forEach(btn => {
                    btn.addEventListener('click', (e) => {
                        if (state.readingQuizAnswered) return;
                        const rq = parseInt(btn.dataset.rq);
                        const chosen = parseInt(btn.dataset.opt);
                        const correct = parseInt(btn.dataset.answer);
                        const isCorrect = chosen === correct;
                        const parent = btn.closest('[data-rq]');
                        parent.querySelectorAll('.quiz-option').forEach(b => b.classList.add('disabled'));
                        if (isCorrect) {
                            btn.classList.add('correct');
                        } else {
                            btn.classList.add('wrong');
                            parent.querySelectorAll('.quiz-option').forEach(b => {
                                if (parseInt(b.dataset.opt) === correct) b.classList.add('correct');
                            });
                        }
                        const allRq = area.querySelectorAll('[data-rq]');
                        let allDone = true;
                        allRq.forEach(el => {
                            const opts = el.querySelectorAll('.quiz-option');
                            let hasDisabled = false;
                            opts.forEach(o => { if (o.classList.contains('disabled')) hasDisabled = true; });
                            if (!hasDisabled) allDone = false;
                        });
                        if (allDone) {
                            state.readingQuizAnswered = true;
                            setTimeout(() => renderReadingDetail(passageId), 600);
                        }
                    });
                });
            } else {
                const resetBtn = document.getElementById('readingResetQuiz');
                if (resetBtn) {
                    resetBtn.addEventListener('click', () => {
                        state.readingQuizAnswered = false;
                        renderReadingDetail(passageId);
                    });
                }
                const markBtn = document.getElementById('readingMarkDone');
                if (markBtn) {
                    markBtn.addEventListener('click', () => {
                        markReadingDone(passageId);
                        renderReadingDetail(passageId);
                    });
                }
            }
        }

        // Tooltip
        let tooltipEl = null;

        function showTooltip(e, text) {
            hideTooltip();
            tooltipEl = document.createElement('div');
            tooltipEl.className = 'word-tooltip';
            tooltipEl.textContent = text;
            document.body.appendChild(tooltipEl);
            const rect = e.target.getBoundingClientRect();
            tooltipEl.style.left = (rect.left + rect.width / 2 - tooltipEl.offsetWidth / 2) + 'px';
            tooltipEl.style.top = (rect.bottom + 8) + 'px';
        }

        function hideTooltip() {
            if (tooltipEl) {
                tooltipEl.remove();
                tooltipEl = null;
            }
        }

        // ─── WRITING ───
        function renderWriting() {
            const area = document.getElementById('writingArea');
            const prompts = WRITING_DATA;

            if (!state.writingPromptId || !prompts.find(p => p.id === state.writingPromptId)) {
                state.writingPromptId = prompts[0].id;
            }

            const current = prompts.find(p => p.id === state.writingPromptId);
            const done = isWritingDone(current.id);
            const idx = prompts.indexOf(current);

            area.innerHTML = `
            <div class="grid-3 mb-16">
              ${prompts.map((p, i) => `
                <div class="card" data-writing-id="${p.id}" style="cursor:pointer">
                  <div class="flex-between">
                    <h3>${p.title}</h3>
                    <span class="badge ${isWritingDone(p.id) ? 'done' : ''}">${isWritingDone(p.id) ? '✅' : i+1}</span>
                  </div>
                </div>
              `).join('')}
            </div>
            <div class="card">
              <div class="flex-between">
                <h3>${current.title}</h3>
                <span class="badge ${done ? 'done' : ''}">${done ? '✅ Complete' : '✍️ Prompt'}</span>
              </div>
              <div class="writing-prompt-box">
                <h4>📝 Write about:</h4>
                <p>${current.prompt}</p>
              </div>
              <div class="card">
                <h4>💡 Tips</h4>
                <ul style="padding-left:20px;color:#4a5a6a;">
                  ${current.tips.map(t => `<li>${t}</li>`).join('')}
                </ul>
              </div>
              <div class="mt-12">
                <textarea class="dictation-input" id="writingTextarea" rows="6" placeholder="Write your response here..."></textarea>
              </div>
              <div class="flex-between mt-8">
                <div>
                  <button class="btn btn-sm btn-outline" id="writingPrev">◀ Previous</button>
                  <button class="btn btn-sm btn-outline" id="writingNext">Next ▶</button>
                </div>
                ${!done ? `<button class="btn btn-sm btn-success" id="writingMarkDone">✅ Mark as Complete</button>` : ''}
              </div>
            </div>
          `;

            // navigation
            document.getElementById('writingPrev').addEventListener('click', () => {
                const i = prompts.findIndex(p => p.id === state.writingPromptId);
                const next = (i - 1 + prompts.length) % prompts.length;
                state.writingPromptId = prompts[next].id;
                renderWriting();
            });
            document.getElementById('writingNext').addEventListener('click', () => {
                const i = prompts.findIndex(p => p.id === state.writingPromptId);
                const next = (i + 1) % prompts.length;
                state.writingPromptId = prompts[next].id;
                renderWriting();
            });

            const markBtn = document.getElementById('writingMarkDone');
            if (markBtn) {
                markBtn.addEventListener('click', () => {
                    markWritingDone(current.id);
                    renderWriting();
                });
            }

            // click on cards
            area.querySelectorAll('[data-writing-id]').forEach(el => {
                el.addEventListener('click', () => {
                    state.writingPromptId = el.dataset.writingId;
                    renderWriting();
                });
            });
        }

        // ─── LISTENING ───
        function renderListening() {
            const area = document.getElementById('listeningArea');
            const items = LISTENING_DATA;

            if (!state.listeningId || !items.find(p => p.id === state.listeningId)) {
                state.listeningId = items[0].id;
                state.listeningQuizAnswered = false;
                state.dictationAttempted = false;
            }

            const current = items.find(p => p.id === state.listeningId);
            const done = isListeningDone(current.id);
            const idx = items.indexOf(current);

            let questionsHtml = '';
            const qAnswered = state.listeningQuizAnswered;

            if (current.questions && current.questions.length > 0) {
                if (!qAnswered) {
                    questionsHtml = current.questions.map((q, i) => `
                <div class="card mt-8" data-lq="${i}">
                  <p><strong>${i+1}. ${q.q}</strong></p>
                  ${q.options.map((opt, oi) => `
                    <button class="quiz-option" data-lq="${i}" data-opt="${oi}" data-answer="${q.answer}">${opt}</button>
                  `).join('')}
                </div>
              `).join('');
                } else {
                    questionsHtml = current.questions.map((q, i) => `
                <div class="card mt-8">
                  <p><strong>${i+1}. ${q.q}</strong></p>
                  <p>✅ Correct answer: <strong>${q.options[q.answer]}</strong></p>
                </div>
              `).join('');
                    questionsHtml += `
                <button class="btn btn-sm btn-outline mt-8" id="listeningResetQuiz">🔄 Try Again</button>
                ${!done ? `<button class="btn btn-sm btn-success mt-8" id="listeningMarkDone">✅ Mark as Complete</button>` : ''}
              `;
                }
            }

            // dictation
            let dictationHtml = '';
            const dictAttempted = state.dictationAttempted;
            if (current.dictation) {
                if (!dictAttempted) {
                    dictationHtml = `
                <div class="card mt-12">
                  <h4>📝 Dictation</h4>
                  <p class="text-muted">Listen to the audio and type what you hear.</p>
                  <textarea class="dictation-input" id="dictationInput" rows="3" placeholder="Type what you heard..."></textarea>
                  <button class="btn btn-sm btn-outline mt-8" id="dictationSubmit">Submit</button>
                </div>
              `;
                } else {
                    const correct = current.dictation;
                    const userText = state.dictationUserText || '';
                    const isCorrect = userText.trim().toLowerCase() === correct.trim().toLowerCase();
                    dictationHtml = `
                <div class="card mt-12">
                  <h4>📝 Dictation</h4>
                  <p><strong>Your answer:</strong> "${userText}"</p>
                  <p><strong>Correct:</strong> "${correct}"</p>
                  <p class="${isCorrect ? 'status-msg success' : 'status-msg error'}">${isCorrect ? '✅ Perfect! You got it right!' : '❌ Not quite. Try again!'}</p>
                  <button class="btn btn-sm btn-outline mt-8" id="dictationRetry">🔄 Try Again</button>
                </div>
              `;
                }
            }

            area.innerHTML = `
            <div class="flex-between mb-12">
              <div>
                <span class="text-muted">${idx+1} / ${items.length}</span>
              </div>
              <div>
                <button class="btn btn-sm btn-outline" id="listeningPrev">◀ Previous</button>
                <button class="btn btn-sm btn-outline" id="listeningNext">Next ▶</button>
              </div>
            </div>
            <div class="card">
              <div class="flex-between">
                <h3>${current.title}</h3>
                <span class="badge ${done ? 'done' : ''}">${done ? '✅ Done' : '🎧 Listen'}</span>
              </div>
              <div class="audio-controls">
                <button id="listenPlayBtn">▶️ Play</button>
                <button id="listenStopBtn" class="hidden">⏹ Stop</button>
                <span class="text-muted" id="listenStatus">Ready</span>
              </div>
              <div class="card mt-8" style="background:#f0f6fe;">
                <p style="font-style:italic;color:#1a3a5a;">"${current.text}"</p>
              </div>
            </div>
            <h4 class="mt-12">📝 Comprehension Questions</h4>
            ${questionsHtml || '<p class="text-muted">No questions available.</p>'}
            ${dictationHtml}
          `;

            // audio controls
            let utterance = null;
            const playBtn = document.getElementById('listenPlayBtn');
            const stopBtn = document.getElementById('listenStopBtn');
            const statusEl = document.getElementById('listenStatus');

            if (playBtn) {
                playBtn.addEventListener('click', () => {
                    if (window.speechSynthesis.speaking) {
                        window.speechSynthesis.cancel();
                    }
                    utterance = new SpeechSynthesisUtterance(current.text);
                    utterance.lang = 'en-US';
                    utterance.rate = 0.9;
                    utterance.onstart = () => {
                        statusEl.textContent = '🔊 Playing...';
                        playBtn.classList.add('hidden');
                        stopBtn.classList.remove('hidden');
                    };
                    utterance.onend = () => {
                        statusEl.textContent = '✅ Done';
                        playBtn.classList.remove('hidden');
                        stopBtn.classList.add('hidden');
                    };
                    window.speechSynthesis.speak(utterance);
                });
            }
            if (stopBtn) {
                stopBtn.addEventListener('click', () => {
                    if (window.speechSynthesis.speaking) {
                        window.speechSynthesis.cancel();
                    }
                    statusEl.textContent = '⏹ Stopped';
                    playBtn.classList.remove('hidden');
                    stopBtn.classList.add('hidden');
                });
            }

            // quiz listeners
            if (!qAnswered) {
                area.querySelectorAll('.quiz-option').forEach(btn => {
                    btn.addEventListener('click', (e) => {
                        if (state.listeningQuizAnswered) return;
                        const lq = parseInt(btn.dataset.lq);
                        const chosen = parseInt(btn.dataset.opt);
                        const correct = parseInt(btn.dataset.answer);
                        const isCorrect = chosen === correct;
                        const parent = btn.closest('[data-lq]');
                        parent.querySelectorAll('.quiz-option').forEach(b => b.classList.add('disabled'));
                        if (isCorrect) {
                            btn.classList.add('correct');
                        } else {
                            btn.classList.add('wrong');
                            parent.querySelectorAll('.quiz-option').forEach(b => {
                                if (parseInt(b.dataset.opt) === correct) b.classList.add('correct');
                            });
                        }
                        const allLq = area.querySelectorAll('[data-lq]');
                        let allDone = true;
                        allLq.forEach(el => {
                            const opts = el.querySelectorAll('.quiz-option');
                            let hasDisabled = false;
                            opts.forEach(o => { if (o.classList.contains('disabled')) hasDisabled = true; });
                            if (!hasDisabled) allDone = false;
                        });
                        if (allDone) {
                            state.listeningQuizAnswered = true;
                            setTimeout(() => renderListening(), 600);
                        }
                    });
                });
            } else {
                const resetBtn = document.getElementById('listeningResetQuiz');
                if (resetBtn) {
                    resetBtn.addEventListener('click', () => {
                        state.listeningQuizAnswered = false;
                        renderListening();
                    });
                }
                const markBtn = document.getElementById('listeningMarkDone');
                if (markBtn) {
                    markBtn.addEventListener('click', () => {
                        markListeningDone(current.id);
                        renderListening();
                    });
                }
            }

            // dictation
            const dictSubmit = document.getElementById('dictationSubmit');
            if (dictSubmit) {
                dictSubmit.addEventListener('click', () => {
                    const input = document.getElementById('dictationInput');
                    state.dictationUserText = input.value.trim();
                    state.dictationAttempted = true;
                    renderListening();
                });
            }
            const dictRetry = document.getElementById('dictationRetry');
            if (dictRetry) {
                dictRetry.addEventListener('click', () => {
                    state.dictationAttempted = false;
                    state.dictationUserText = '';
                    renderListening();
                });
            }

            // navigation
            const prevBtn = document.getElementById('listeningPrev');
            const nextBtn = document.getElementById('listeningNext');
            if (prevBtn) {
                prevBtn.addEventListener('click', () => {
                    const i = items.findIndex(p => p.id === state.listeningId);
                    const next = (i - 1 + items.length) % items.length;
                    state.listeningId = items[next].id;
                    state.listeningQuizAnswered = false;
                    state.dictationAttempted = false;
                    state.dictationUserText = '';
                    renderListening();
                });
            }
            if (nextBtn) {
                nextBtn.addEventListener('click', () => {
                    const i = items.findIndex(p => p.id === state.listeningId);
                    const next = (i + 1) % items.length;
                    state.listeningId = items[next].id;
                    state.listeningQuizAnswered = false;
                    state.dictationAttempted = false;
                    state.dictationUserText = '';
                    renderListening();
                });
            }
        }

        // ─── SPEAKING ───
        function renderSpeaking() {
            const area = document.getElementById('speakingArea');
            const phrases = SPEAKING_DATA;

            if (state.speakingIndex >= phrases.length) state.speakingIndex = 0;
            const current = phrases[state.speakingIndex];
            const done = isSpeakingDone(state.speakingIndex);

            const recognition = window.SpeechRecognition || window.webkitSpeechRecognition;
            const hasRecognition = !!recognition;

            area.innerHTML = `
            <div class="flex-between mb-12">
              <span class="text-muted">${state.speakingIndex+1} / ${phrases.length}</span>
              <div>
                <button class="btn btn-sm btn-outline" id="speakingPrev">◀ Previous</button>
                <button class="btn btn-sm btn-outline" id="speakingNext">Next ▶</button>
              </div>
            </div>
            <div class="card">
              <div class="flex-between">
                <h3>🎤 Repeat the phrase</h3>
                <span class="badge ${done ? 'done' : ''}">${done ? '✅ Done' : '🎙️ Practice'}</span>
              </div>
              <div class="speaking-prompt">"${current.phrase}"</div>
              <p class="text-muted text-center">💡 ${current.hint}</p>

              <div class="text-center mt-12">
                ${hasRecognition ? `
                  <button class="btn" id="speakingStartBtn">🎙️ Start Speaking</button>
                  <button class="btn btn-danger hidden" id="speakingStopBtn">⏹ Stop</button>
                ` : `
                  <p class="status-msg error">❌ Speech recognition is not supported in this browser. Please use Chrome or Edge.</p>
                `}
              </div>

              <div class="speaking-result" id="speakingResult">
                <span class="text-muted">Your speech will appear here...</span>
              </div>

              <div id="speakingFeedback" class="mt-8"></div>

              ${!done && hasRecognition ? `
                <div class="text-center mt-8">
                  <button class="btn btn-sm btn-success" id="speakingMarkDone">✅ Mark as Practiced</button>
                </div>
              ` : ''}
              ${done ? `<p class="text-center text-muted">✅ You've practiced this phrase!</p>` : ''}
            </div>
          `;

            if (!hasRecognition) return;

            let recognitionInstance = null;
            let isListening = false;

            const startBtn = document.getElementById('speakingStartBtn');
            const stopBtn = document.getElementById('speakingStopBtn');
            const resultEl = document.getElementById('speakingResult');
            const feedbackEl = document.getElementById('speakingFeedback');

            function startListening() {
                try {
                    recognitionInstance = new recognition();
                    recognitionInstance.lang = 'en-US';
                    recognitionInstance.interimResults = true;
                    recognitionInstance.continuous = false;

                    recognitionInstance.onresult = (event) => {
                        let final = '';
                        for (let i = event.resultIndex; i < event.results.length; i++) {
                            if (event.results[i].isFinal) {
                                final += event.results[i][0].transcript;
                            }
                        }
                        if (final) {
                            resultEl.innerHTML = `🗣️ You said: <span class="highlight">"${final}"</span>`;
                            // compare with phrase
                            const target = current.phrase.toLowerCase().replace(/[.,!?]/g, '').trim();
                            const spoken = final.toLowerCase().replace(/[.,!?]/g, '').trim();
                            const wordsTarget = target.split(/\s+/);
                            const wordsSpoken = spoken.split(/\s+/);
                            let matched = 0;
                            for (const w of wordsTarget) {
                                if (wordsSpoken.includes(w)) matched++;
                            }
                            const accuracy = Math.round((matched / wordsTarget.length) * 100);
                            if (accuracy >= 70) {
                                feedbackEl.innerHTML = `
                    <div class="status-msg success">🎉 Great! You got ${accuracy}% match. Well done!</div>
                  `;
                                if (!done) {
                                    markSpeakingDone(state.speakingIndex);
                                    // re-render after a moment
                                    setTimeout(() => renderSpeaking(), 1000);
                                }
                            } else if (accuracy >= 40) {
                                feedbackEl.innerHTML = `
                    <div class="status-msg info">👍 Not bad! ${accuracy}% match. Try to say it more clearly.</div>
                  `;
                            } else {
                                feedbackEl.innerHTML = `
                    <div class="status-msg error">🤔 Hmm, only ${accuracy}% match. Listen carefully and try again.</div>
                  `;
                            }
                            stopListening();
                        } else {
                            resultEl.innerHTML = '👂 Listening... speak now.';
                        }
                    };

                    recognitionInstance.onerror = (event) => {
                        if (event.error === 'not-allowed') {
                            resultEl.innerHTML = '❌ Microphone access denied. Please allow microphone access.';
                        } else if (event.error === 'no-speech') {
                            resultEl.innerHTML = '🔇 No speech detected. Try again.';
                        } else {
                            resultEl.innerHTML = `⚠️ Error: ${event.error}`;
                        }
                        stopListening();
                    };

                    recognitionInstance.onend = () => {
                        stopListening();
                    };

                    recognitionInstance.start();
                    isListening = true;
                    startBtn.classList.add('hidden');
                    stopBtn.classList.remove('hidden');
                    resultEl.innerHTML = '👂 Listening... speak now.';
                    document.getElementById('speakingStatus').textContent = '🎙️ Listening... speak clearly.';
                } catch (err) {
                    resultEl.innerHTML = '❌ Error starting recognition: ' + err.message;
                    stopListening();
                }
            }

            function stopListening() {
                if (recognitionInstance) {
                    try { recognitionInstance.stop(); } catch (_) {}
                    recognitionInstance = null;
                }
                isListening = false;
                startBtn.classList.remove('hidden');
                stopBtn.classList.add('hidden');
                document.getElementById('speakingStatus').textContent = '🎙️ Click "Start Speaking" to practice.';
            }

            if (startBtn) {
                startBtn.addEventListener('click', startListening);
            }
            if (stopBtn) {
                stopBtn.addEventListener('click', stopListening);
            }

            // mark done
            const markBtn = document.getElementById('speakingMarkDone');
            if (markBtn) {
                markBtn.addEventListener('click', () => {
                    markSpeakingDone(state.speakingIndex);
                    renderSpeaking();
                });
            }

            // navigation
            const prevBtn = document.getElementById('speakingPrev');
            const nextBtn = document.getElementById('speakingNext');
            if (prevBtn) {
                prevBtn.addEventListener('click', () => {
                    if (isListening) stopListening();
                    state.speakingIndex = (state.speakingIndex - 1 + phrases.length) % phrases.length;
                    renderSpeaking();
                });
            }
            if (nextBtn) {
                nextBtn.addEventListener('click', () => {
                    if (isListening) stopListening();
                    state.speakingIndex = (state.speakingIndex + 1) % phrases.length;
                    renderSpeaking();
                });
            }
        }

        // ═══════════════════════════════════════════════════════════════
        //  INIT
        // ═══════════════════════════════════════════════════════════════

        // ensure progress integrity
        for (const cat of VOCAB_DATA.categories) {
            if (!state.progress.vocabulary[cat]) state.progress.vocabulary[cat] = [];
        }
        saveProgress();

        // render initial page
        renderPage('dashboard');

        // handle tooltip reposition on scroll
        window.addEventListener('scroll', () => {
            if (tooltipEl) hideTooltip();
        });

        console.log('📘 English Learning Hub loaded!');
        console.log('💡 All progress saved in localStorage.');
        console.log('🎧 Listening uses browser TTS; 🎤 Speaking uses Web Speech API.');
    </script>

</body>
</html>
