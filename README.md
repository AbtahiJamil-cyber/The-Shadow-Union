<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Shadow Union - মূল পোর্টাল</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary: #1a1a2e;
            --secondary: #16213e;
            --accent: #0f3460;
            --highlight: #e94560;
            --text: #ffffff;
            --success: #2ecc71;
            --warning: #f39c12;
            --card-bg: rgba(255, 255, 255, 0.05);
        }

        body {
            background: linear-gradient(135deg, var(--primary), #0c0c1a);
            color: var(--text);
            min-height: 100vh;
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* হেডার স্টাইল */
        header {
            text-align: center;
            padding: 40px 20px;
            background: rgba(22, 33, 62, 0.8);
            border-radius: 15px;
            margin-bottom: 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            position: relative;
            overflow: hidden;
        }

        header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, var(--highlight), var(--accent));
        }

        .logo {
            margin-bottom: 20px;
        }

        .logo h1 {
            font-size: 3rem;
            background: linear-gradient(45deg, var(--highlight), #ff7b9c);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 10px;
            text-shadow: 0 2px 10px rgba(233, 69, 96, 0.3);
        }

        .logo p {
            font-size: 1.2rem;
            opacity: 0.8;
            letter-spacing: 1px;
        }

        .tagline {
            font-size: 1.1rem;
            max-width: 600px;
            margin: 0 auto;
            padding: 15px;
            background: rgba(15, 52, 96, 0.3);
            border-radius: 10px;
            border-left: 4px solid var(--highlight);
        }

        /* মন্ত্রণালয় গ্রিড স্টাইল */
        .ministries-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 25px;
            margin-top: 30px;
        }

        .ministry-card {
            background: var(--card-bg);
            border-radius: 15px;
            padding: 25px;
            transition: all 0.3s ease;
            cursor: pointer;
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            overflow: hidden;
            display: flex;
            flex-direction: column;
            height: 100%;
        }

        .ministry-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, var(--accent), var(--highlight));
            transform: scaleX(0);
            transition: transform 0.3s ease;
        }

        .ministry-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.4);
            border-color: rgba(233, 69, 96, 0.3);
        }

        .ministry-card:hover::before {
            transform: scaleX(1);
        }

        .card-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: var(--highlight);
            text-align: center;
        }

        .card-title {
            font-size: 1.4rem;
            margin-bottom: 10px;
            color: var(--text);
            text-align: center;
        }

        .card-minister {
            background: rgba(15, 52, 96, 0.5);
            padding: 8px 15px;
            border-radius: 20px;
            font-size: 0.9rem;
            margin-top: auto;
            text-align: center;
            color: white;
        }

        .card-description {
            font-size: 0.95rem;
            opacity: 0.8;
            margin: 15px 0;
            flex-grow: 1;
        }

        .card-action {
            margin-top: 15px;
            text-align: center;
        }

        .open-tab-btn {
            background: linear-gradient(45deg, var(--accent), var(--highlight));
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 25px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .open-tab-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 15px rgba(233, 69, 96, 0.4);
        }

        /* কমিটি সেকশন */
        .committee-section {
            margin-top: 50px;
            text-align: center;
        }

        .committee-btn {
            background: linear-gradient(45deg, var(--highlight), #ff7b9c);
            color: white;
            border: none;
            padding: 15px 30px;
            border-radius: 30px;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            box-shadow: 0 5px 15px rgba(233, 69, 96, 0.3);
        }

        .committee-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(233, 69, 96, 0.4);
        }

        /* ফুটার */
        footer {
            text-align: center;
            margin-top: 50px;
            padding: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.9rem;
            opacity: 0.7;
        }

        /* রেসপন্সিভ */
        @media (max-width: 768px) {
            .ministries-grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
            
            .logo h1 {
                font-size: 2.2rem;
            }
        }

        @media (max-width: 480px) {
            .ministries-grid {
                grid-template-columns: 1fr;
            }
            
            .container {
                padding: 10px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo">
                <h1>The Shadow Union</h1>
                <p>Est. 2025 | অরাজনৈতিক দল</p>
            </div>
            <div class="tagline">
                একটি সুসংগঠিত ও উন্নত সমাজ গঠনের লক্ষ্যে অগ্রসরমান অরাজনৈতিক দল
            </div>
        </header>

        <main>
            <div class="ministries-grid">
                <!-- স্বরাষ্ট্র -->
                <div class="ministry-card" data-ministry="swarastra">
                    <div class="card-icon">🔐</div>
                    <h3 class="card-title">স্বরাষ্ট্র</h3>
                    <p class="card-description">দলের অভ্যন্তরীণ বিষয় ও নিরাপত্তা ব্যবস্থাপনা এই মন্ত্রণালয়ের আওতাধীন।</p>
                    <div class="card-minister">মন্ত্রী: আবতাহি বিন জামিল</div>
                    <div class="card-action">
                        <button class="open-tab-btn" onclick="openMinistryTab('swarastra')">
                            <i class="fas fa-external-link-alt"></i> খুলুন
                        </button>
                    </div>
                </div>

                <!-- পররাষ্ট্র -->
                <div class="ministry-card" data-ministry="pororastro">
                    <div class="card-icon">🌐</div>
                    <h3 class="card-title">পররাষ্ট্র</h3>
                    <p class="card-description">বাহ্যিক সম্পর্ক ও যোগাযোগ এই মন্ত্রণালয়ের আওতাধীন।</p>
                    <div class="card-minister">মন্ত্রী: আবতাহি বিন জামিল</div>
                    <div class="card-action">
                        <button class="open-tab-btn" onclick="openMinistryTab('pororastro')">
                            <i class="fas fa-external-link-alt"></i> খুলুন
                        </button>
                    </div>
                </div>

                <!-- পরিকল্পনা -->
                <div class="ministry-card" data-ministry="porikkolpona">
                    <div class="card-icon">📊</div>
                    <h3 class="card-title">পরিকল্পনা</h3>
                    <p class="card-description">দলের বিভিন্ন প্রকল্প ও কার্যক্রম পরিকল্পনা এই মন্ত্রণালয়ের আওতাধীন।</p>
                    <div class="card-minister">মন্ত্রী: আবতাহি বিন জামিল</div>
                    <div class="card-minister">উপমন্ত্রী: মুহতাসিম বখতিয়ার রাফাত, ইবতিশাম হক জিসান</div>
                    <div class="card-action">
                        <button class="open-tab-btn" onclick="openMinistryTab('porikkolpona')">
                            <i class="fas fa-external-link-alt"></i> খুলুন
                        </button>
                    </div>
                </div>

                <!-- প্রতিরক্ষা -->
                <div class="ministry-card" data-ministry="protirakkha">
                    <div class="card-icon">🛡️</div>
                    <h3 class="card-title">প্রতিরক্ষা</h3>
                    <p class="card-description">দলের নিরাপত্তা ও প্রতিরক্ষা ব্যবস্থা এই মন্ত্রণালয়ের আওতাধীন।</p>
                    <div class="card-minister">মন্ত্রী: আবতাহি বিন জামিল</div>
                    <div class="card-action">
                        <button class="open-tab-btn" onclick="openMinistryTab('protirakkha')">
                            <i class="fas fa-external-link-alt"></i> খুলুন
                        </button>
                    </div>
                </div>

                <!-- অর্থ -->
                <div class="ministry-card" data-ministry="ortho">
                    <div class="card-icon">💰</div>
                    <h3 class="card-title">অর্থ</h3>
                    <p class="card-description">দলের আর্থিক ব্যবস্থাপনা ও তহবিল এই মন্ত্রণালয়ের আওতাধীন।</p>
                    <div class="card-minister">মন্ত্রী: আবতাহি বিন জামিল</div>
                    <div class="card-action">
                        <button class="open-tab-btn" onclick="openMinistryTab('ortho')">
                            <i class="fas fa-external-link-alt"></i> খুলুন
                        </button>
                    </div>
                </div>

                <!-- গণসংযোগ -->
                <div class="ministry-card" data-ministry="gonosongjog">
                    <div class="card-icon">📢</div>
                    <h3 class="card-title">গণসংযোগ</h3>
                    <p class="card-description">দলের প্রচার ও জনসংযোগ কার্যক্রম এই মন্ত্রণালয়ের আওতাধীন।</p>
                    <div class="card-minister">মন্ত্রী: আবতাহি বিন জামিল</div>
                    <div class="card-action">
                        <button class="open-tab-btn" onclick="openMinistryTab('gonosongjog')">
                            <i class="fas fa-external-link-alt"></i> খুলুন
                        </button>
                    </div>
                </div>

                <!-- শিক্ষা -->
                <div class="ministry-card" data-ministry="shikkha">
                    <div class="card-icon">📚</div>
                    <h3 class="card-title">শিক্ষা</h3>
                    <p class="card-description">দলের শিক্ষা ও উন্নয়নমূলক কার্যক্রম এই মন্ত্রণালয়ের আওতাধীন।</p>
                    <div class="card-minister">মন্ত্রী: আবতাহি বিন জামিল</div>
                    <div class="card-action">
                        <button class="open-tab-btn" onclick="openMinistryTab('shikkha')">
                            <i class="fas fa-external-link-alt"></i> খুলুন
                        </button>
                    </div>
                </div>

                <!-- শিল্প -->
                <div class="ministry-card" data-ministry="shilpo">
                    <div class="card-icon">🏭</div>
                    <h3 class="card-title">শিল্প</h3>
                    <p class="card-description">দলের শিল্প ও উৎপাদন সংশ্লিষ্ট কার্যক্রম এই মন্ত্রণালয়ের আওতাধীন।</p>
                    <div class="card-minister">মন্ত্রী: আবতাহি বিন জামিল</div>
                    <div class="card-action">
                        <button class="open-tab-btn" onclick="openMinistryTab('shilpo')">
                            <i class="fas fa-external-link-alt"></i> খুলুন
                        </button>
                    </div>
                </div>

                <!-- ভূমি -->
                <div class="ministry-card" data-ministry="bumi">
                    <div class="card-icon">🏞️</div>
                    <h3 class="card-title">ভূমি</h3>
                    <p class="card-description">দলের ভূমি ও স্থান ব্যবস্থাপনা এই মন্ত্রণালয়ের আওতাধীন।</p>
                    <div class="card-minister">মন্ত্রী: আবতাহি বিন জামিল</div>
                    <div class="card-action">
                        <button class="open-tab-btn" onclick="openMinistryTab('bumi')">
                            <i class="fas fa-external-link-alt"></i> খুলুন
                        </button>
                    </div>
                </div>

                <!-- বিজ্ঞান ও প্রযুক্তি -->
                <div class="ministry-card" data-ministry="biggan">
                    <div class="card-icon">🔬</div>
                    <h3 class="card-title">বিজ্ঞান ও প্রযুক্তি</h3>
                    <p class="card-description">দলের প্রযুক্তিগত উন্নয়ন ও গবেষণা এই মন্ত্রণালয়ের আওতাধীন।</p>
                    <div class="card-minister">মন্ত্রী: আবতাহি বিন জামিল</div>
                    <div class="card-action">
                        <button class="open-tab-btn" onclick="openMinistryTab('biggan')">
                            <i class="fas fa-external-link-alt"></i> খুলুন
                        </button>
                    </div>
                </div>

                <!-- তথ্য, যোগাযোগ ও সাইবার -->
                <div class="ministry-card" data-ministry="totto">
                    <div class="card-icon">📡</div>
                    <h3 class="card-title">তথ্য, যোগাযোগ ও সাইবার</h3>
                    <p class="card-description">দলের তথ্য ব্যবস্থাপনা ও যোগাযোগ এই মন্ত্রণালয়ের আওতাধীন।</p>
                    <div class="card-minister">মন্ত্রী: আবতাহি বিন জামিল</div>
                    <div class="card-action">
                        <button class="open-tab-btn" onclick="openMinistryTab('totto')">
                            <i class="fas fa-external-link-alt"></i> খুলুন
                        </button>
                    </div>
                </div>

                <!-- স্বাস্থ্য -->
                <div class="ministry-card" data-ministry="swastho">
                    <div class="card-icon">🏥</div>
                    <h3 class="card-title">স্বাস্থ্য</h3>
                    <p class="card-description">দলের স্বাস্থ্য সংক্রান্ত কার্যক্রম এই মন্ত্রণালয়ের আওতাধীন।</p>
                    <div class="card-minister">মন্ত্রী: আবতাহি বিন জামিল</div>
                    <div class="card-action">
                        <button class="open-tab-btn" onclick="openMinistryTab('swastho')">
                            <i class="fas fa-external-link-alt"></i> খুলুন
                        </button>
                    </div>
                </div>

                <!-- ক্রীড়া -->
                <div class="ministry-card" data-ministry="krida">
                    <div class="card-icon">⚽</div>
                    <h3 class="card-title">ক্রীড়া</h3>
                    <p class="card-description">দলের ক্রীড়া ও বিনোদন সংশ্লিষ্ট কার্যক্রম এই মন্ত্রণালয়ের আওতাধীন।</p>
                    <div class="card-minister">মন্ত্রী: আবতাহি বিন জামিল</div>
                    <div class="card-action">
                        <button class="open-tab-btn" onclick="openMinistryTab('krida')">
                            <i class="fas fa-external-link-alt"></i> খুলুন
                        </button>
                    </div>
                </div>

                <!-- পরিবেশ -->
                <div class="ministry-card" data-ministry="poribesh">
                    <div class="card-icon">🌳</div>
                    <h3 class="card-title">পরিবেশ</h3>
                    <p class="card-description">দলের পরিবেশ সংক্রান্ত কার্যক্রম এই মন্ত্রণালয়ের আওতাধীন।</p>
                    <div class="card-minister">মন্ত্রী: আবতাহি বিন জামিল</div>
                    <div class="card-minister">উপমন্ত্রী: মুহতাসিম বখতিয়ার রাফাত</div>
                    <div class="card-action">
                        <button class="open-tab-btn" onclick="openMinistryTab('poribesh')">
                            <i class="fas fa-external-link-alt"></i> খুলুন
                        </button>
                    </div>
                </div>

                <!-- বাণিজ্য -->
                <div class="ministry-card" data-ministry="banijjo">
                    <div class="card-icon">📦</div>
                    <h3 class="card-title">বাণিজ্য</h3>
                    <p class="card-description">দলের বাণিজ্যিক কার্যক্রম এই মন্ত্রণালয়ের আওতাধীন।</p>
                    <div class="card-minister">মন্ত্রী: আবতাহি বিন জামিল</div>
                    <div class="card-action">
                        <button class="open-tab-btn" onclick="openMinistryTab('banijjo')">
                            <i class="fas fa-external-link-alt"></i> খুলুন
                        </button>
                    </div>
                </div>

                <!-- আইন ও বিচার -->
                <div class="ministry-card" data-ministry="ain">
                    <div class="card-icon">⚖️</div>
                    <h3 class="card-title">আইন ও বিচার</h3>
                    <p class="card-description">দলের আইনগত বিষয় ও ন্যায়বিচার এই মন্ত্রণালয়ের আওতাধীন।</p>
                    <div class="card-minister">মন্ত্রী: আবতাহি বিন জামিল</div>
                    <div class="card-action">
                        <button class="open-tab-btn" onclick="openMinistryTab('ain')">
                            <i class="fas fa-external-link-alt"></i> খুলুন
                        </button>
                    </div>
                </div>

                <!-- স্থানীয় ও নির্বাচন -->
                <div class="ministry-card" data-ministry="nirbachon">
                    <div class="card-icon">🗳️</div>
                    <h3 class="card-title">স্থানীয় ও নির্বাচন</h3>
                    <p class="card-description">দলের নির্বাচনী কার্যক্রম ও স্থানীয় বিষয় এই মন্ত্রণালয়ের আওতাধীন।</p>
                    <div class="card-minister">মন্ত্রী: মুহতাসিম বখতিয়ার রাফাত</div>
                    <div class="card-action">
                        <button class="open-tab-btn" onclick="openMinistryTab('nirbachon')">
                            <i class="fas fa-external-link-alt"></i> খুলুন
                        </button>
                    </div>
                </div>

                <!-- খাদ্য -->
                <div class="ministry-card" data-ministry="khaddo">
                    <div class="card-icon">🍚</div>
                    <h3 class="card-title">খাদ্য</h3>
                    <p class="card-description">দলের খাদ্য ব্যবস্থাপনা এই মন্ত্রণালয়ের আওতাধীন।</p>
                    <div class="card-minister">মন্ত্রী: ইবতিশাম হক জিসান</div>
                    <div class="card-action">
                        <button class="open-tab-btn" onclick="openMinistryTab('khaddo')">
                            <i class="fas fa-external-link-alt"></i> খুলুন
                        </button>
                    </div>
                </div>

                <!-- সমাজকল্যাণ -->
                <div class="ministry-card" data-ministry="shomaj">
                    <div class="card-icon">🤝</div>
                    <h3 class="card-title">সমাজকল্যাণ</h3>
                    <p class="card-description">দলের সমাজকল্যাণমূলক কার্যক্রম এই মন্ত্রণালয়ের আওতাধীন।</p>
                    <div class="card-minister">মন্ত্রী: ইবতিশাম হক জিসান</div>
                    <div class="card-minister">উপমন্ত্রী: মুহতাসিম বখতিয়ার রাফাত</div>
                    <div class="card-action">
                        <button class="open-tab-btn" onclick="openMinistryTab('shomaj')">
                            <i class="fas fa-external-link-alt"></i> খুলুন
                        </button>
                    </div>
                </div>
            </div>

            <div class="committee-section">
                <button class="committee-btn" onclick="openCommittee()">
                    <i class="fas fa-users"></i> কমিটি দেখুন
                </button>
            </div>
        </main>

        <footer>
            <p>© 2025 The Shadow Union. সকল অধিকার সংরক্ষিত।</p>
        </footer>
    </div>

    <script>
        // মন্ত্রণালয় ট্যাব ওপেন করার ফাংশন
        function openMinistryTab(ministry) {
            const ministryData = {
                'swarastra': {
                    title: 'স্বরাষ্ট্র মন্ত্রণালয়',
                    content: `
                        <div class="content-box">
                            <h3>স্বরাষ্ট্র মন্ত্রণালয়</h3>
                            <p>দলের অভ্যন্তরীণ বিষয় ও নিরাপত্তা ব্যবস্থাপনা এই মন্ত্রণালয়ের আওতাধীন।</p>
                            <div class="minister-name">মন্ত্রী: আবতাহি বিন জামিল</div>
                        </div>
                    `
                },
                'pororastro': {
                    title: 'পররাষ্ট্র মন্ত্রণালয়',
                    content: `
                        <div class="content-box">
                            <h3>পররাষ্ট্র মন্ত্রণালয়</h3>
                            <p>বাহ্যিক সম্পর্ক ও যোগাযোগ এই মন্ত্রণালয়ের আওতাধীন।</p>
                            <div class="minister-name">মন্ত্রী: আবতাহি বিন জামিল</div>
                            
                            <h4>আমাদের শত্রু:</h4>
                            <div class="enemy-list">
                                <div class="enemy-card">
                                    <h4>ইচ্ছে</h4>
                                    <p>নাম্বার: ০১৭০১৪৬৯০৫৯</p>
                                </div>
                                <div class="enemy-card">
                                    <h4>মিসবাহ</h4>
                                    <p>নাম্বার: ০১৭০১৪৬৯০৫৯</p>
                                </div>
                                <div class="enemy-card">
                                    <h4>জিল</h4>
                                    <p>ফেসবুক অ্যাকাউন্ট: mobarok hossain jill</p>
                                </div>
                            </div>
                        </div>
                    `
                },
                'ortho': {
                    title: 'অর্থ মন্ত্রণালয় - The Shadow Union Reserve Bank',
                    content: `
                        <div class="content-box">
                            <div class="bank-header">
                                <div class="bank-logo">
                                    <i>🏦</i>
                                    <h2>The Shadow Union Reserve Bank</h2>
                                </div>
                                <div class="total-balance">
                                    <h3>মোট ব্যালেন্স</h3>
                                    <p>৳ 100</p>
                                </div>
                            </div>
                            
                            <p>দলের আর্থিক ব্যবস্থাপনা ও তহবিল এই মন্ত্রণালয়ের আওতাধীন। The Shadow Union Reserve Bank এর মাধ্যমে সকল সদস্যের ব্যাংক অ্যাকাউন্ট ব্যবস্থাপনা করা হয়।</p>
                            <div class="minister-name">মন্ত্রী: আবতাহি বিন জামিল</div>
                            
                            <h3>সদস্য অ্যাকাউন্টসমূহ</h3>
                            <div class="accounts-grid">
                                <div class="account-card banker-card">
                                    <div class="account-header">
                                        <div class="account-name">ব্যাংকার</div>
                                        <div class="account-number">ACC: TSUB-001</div>
                                    </div>
                                    <div class="account-balance balance-positive">৳ 100</div>
                                </div>
                                <div class="account-card">
                                    <div class="account-header">
                                        <div class="account-name">আবতাহি বিন জামিল</div>
                                        <div class="account-number">ACC: TSUB-002</div>
                                    </div>
                                    <div class="account-balance balance-zero">৳ 0</div>
                                </div>
                                <div class="account-card">
                                    <div class="account-header">
                                        <div class="account-name">মুহতাসিম বখতিয়ার রাফাত</div>
                                        <div class="account-number">ACC: TSUB-003</div>
                                    </div>
                                    <div class="account-balance balance-zero">৳ 0</div>
                                </div>
                                <div class="account-card">
                                    <div class="account-header">
                                        <div class="account-name">ইবতিশাম হক জিসান</div>
                                        <div class="account-number">ACC: TSUB-004</div>
                                    </div>
                                    <div class="account-balance balance-zero">৳ 0</div>
                                </div>
                                <div class="account-card">
                                    <div class="account-header">
                                        <div class="account-name">আরিক হোসাইন</div>
                                        <div class="account-number">ACC: TSUB-005</div>
                                    </div>
                                    <div class="account-balance balance-zero">৳ 0</div>
                                </div>
                                <div class="account-card">
                                    <div class="account-header">
                                        <div class="account-name">আদনান হোসেন</div>
                                        <div class="account-number">ACC: TSUB-006</div>
                                    </div>
                                    <div class="account-balance balance-zero">৳ 0</div>
                                </div>
                            </div>
                        </div>
                    `
                }
        // কমিটি পেজ ওপেন করার ফাংশন
        function openCommittee() {
            const committeeContent = `
                <html>
                <head>
                    <title>The Shadow Union - কমিটি</title>
                    <style>
                        body {
                            font-family: Arial, sans-serif;
                            margin: 0;
                            padding: 20px;
                            background-color: #1a1a2e;
                            color: white;
                        }
                        .committee-container {
                            max-width: 800px;
                            margin: 0 auto;
                            background-color: #16213e;
                            padding: 20px;
                            border-radius: 10px;
                            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
                        }
                        h1 {
                            color: #e94560;
                            text-align: center;
                            margin-bottom: 30px;
                        }
                        .member-card {
                            background-color: rgba(255,255,255,0.05);
                            border-radius: 8px;
                            padding: 15px;
                            margin-bottom: 15px;
                            border-left: 4px solid #0f3460;
                        }
                        .member-card h3 {
                            color: #e94560;
                            margin-top: 0;
                        }
                        .highlight {
                            color: white;
                            font-weight: bold;
                        }
                    </style>
                </head>
                <body>
                    <div class="committee-container">
                        <h1>The Shadow Union - কমিটি</h1>
                        
                        <div class="member-card">
                            <h3>লিডার - আবতাহি বিন জামিল</h3>
                            <p><span class="highlight">নাম্বার:</span> ০১৭৭৪৯৮১৩১২</p>
                            <p><span class="highlight">ঠিকানা:</span> গোপাল্পুর, লালপুর, নাটোর</p>
                            <p><span class="highlight">মিডিয়া:</span> ফেসবুক: Mohammed Sabbir hossain, Instagram: dadajongi prisoner</p>
                        </div>
                        
                        <div class="member-card">
                            <h3>সিনিয়র লিডার - মুহতাসিম বখতিয়ার রাফাত</h3>
                            <p><span class="highlight">ঠিকানা:</span> ফরিদপুর, এবি ইউনিয়ন, লালপুর, নাটোর</p>
                            <p><span class="highlight">মিডিয়া:</span> ফেসবুক: muhtasim bakhtiar rafat</p>
                        </div>
                        
                        <div class="member-card">
                            <h3>সিনিয়র লিডার - ইবতিশাম হক জিসান</h3>
                            <p><span class="highlight">নাম্বার:</span> ০১৮১৮২১৫৯০৪</p>
                            <p><span class="highlight">ঠিকানা:</span> রুইগারি, ওয়ালিয়া ইউনিয়ন, লালপুর, নাটোর</p>
                            <p><span class="highlight">মিডিয়া:</span> ফেসবুক: md ibtisham haque jishan</p>
                        </div>
                        
                        <div class="member-card">
                            <h3>সদস্য - আরিক হোসাইন</h3>
                            <p><span class="highlight">ঠিকানা:</span> গোপালপুর, লালপুর, নাটোর</p>
                            <p><span class="highlight">মিডিয়া:</span> N/A</p>
                        </div>
                        
                        <div class="member-card">
                            <h3>সদস্য - আদনান হোসেন</h3>
                            <p><span class="highlight">ঠিকানা:</span> ফরিদপুর, এবি ইউনিয়ন, লালপুর, নাটোর</p>
                            <p><span class="highlight">মিডিয়া:</span> নেই</p>
                        </div>
                    </div>
                </body>
                </html>
            `;
            
            const committeeWindow = window.open('', '_blank');
            committeeWindow.document.write(committeeContent);
            committeeWindow.document.close();
        }
    </script>
</body>
</html>
