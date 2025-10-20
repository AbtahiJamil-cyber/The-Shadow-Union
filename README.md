<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Shadow Union</title>
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
            background: var(--primary);
            color: var(--text);
            min-height: 100vh;
            line-height: 1.5;
            font-size: 14px;
            overflow-x: hidden;
        }

        .container {
            width: 100%;
            padding: 15px;
        }

        /* হেডার স্টাইল */
        header {
            text-align: center;
            padding: 25px 15px;
            background: var(--secondary);
            border-radius: 12px;
            margin-bottom: 20px;
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

        .logo h1 {
            font-size: 1.8rem;
            background: linear-gradient(45deg, var(--highlight), #ff7b9c);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 8px;
        }

        .logo p {
            font-size: 0.9rem;
            opacity: 0.8;
        }

        .tagline {
            font-size: 0.9rem;
            padding: 12px;
            background: rgba(15, 52, 96, 0.3);
            border-radius: 8px;
            border-left: 3px solid var(--highlight);
            margin-top: 10px;
        }

        /* মোবাইল নেভিগেশন */
        .mobile-nav {
            position: fixed;
            bottom: 0;
            left: 0;
            right: 0;
            background: var(--secondary);
            display: flex;
            justify-content: space-around;
            padding: 10px 0;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            z-index: 1000;
        }

        .nav-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            color: var(--text);
            text-decoration: none;
            font-size: 0.7rem;
            padding: 5px;
            opacity: 0.7;
            transition: all 0.3s ease;
        }

        .nav-item.active {
            opacity: 1;
            color: var(--highlight);
        }

        .nav-icon {
            font-size: 1.2rem;
            margin-bottom: 3px;
        }

        /* মন্ত্রণালয় গ্রিড স্টাইল */
        .ministries-section {
            margin-bottom: 80px; /* মোবাইল নেভের জন্য স্পেস */
        }

        .section-title {
            font-size: 1.3rem;
            color: var(--highlight);
            margin: 20px 0 15px 0;
            padding-bottom: 8px;
            border-bottom: 2px solid var(--accent);
        }

        .ministries-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 12px;
            margin-top: 15px;
        }

        .ministry-card {
            background: var(--card-bg);
            border-radius: 12px;
            padding: 15px;
            transition: all 0.3s ease;
            cursor: pointer;
            border: 1px solid rgba(255, 255, 255, 0.1);
            text-align: center;
            min-height: 140px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .ministry-card:active {
            transform: scale(0.98);
            background: rgba(233, 69, 96, 0.1);
        }

        .card-icon {
            font-size: 1.8rem;
            margin-bottom: 8px;
            color: var(--highlight);
        }

        .card-title {
            font-size: 0.9rem;
            margin-bottom: 5px;
            color: var(--text);
            font-weight: 600;
        }

        .card-minister {
            background: rgba(15, 52, 96, 0.5);
            padding: 4px 8px;
            border-radius: 15px;
            font-size: 0.7rem;
            color: white;
            margin-top: 5px;
        }

        /* কমিটি সেকশন */
        .committee-section {
            margin: 25px 0;
            text-align: center;
        }

        .committee-btn {
            background: linear-gradient(45deg, var(--highlight), #ff7b9c);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 25px;
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            width: 100%;
            justify-content: center;
        }

        .committee-btn:active {
            transform: scale(0.95);
        }

        /* মডাল স্টাইল */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            z-index: 2000;
            overflow-y: auto;
        }

        .modal-content {
            background: var(--secondary);
            margin: 20px;
            border-radius: 15px;
            padding: 20px;
            position: relative;
            animation: modalSlideIn 0.3s ease;
        }

        @keyframes modalSlideIn {
            from {
                transform: translateY(50px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .close-btn {
            position: absolute;
            top: 15px;
            right: 15px;
            background: var(--highlight);
            color: white;
            border: none;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            font-size: 1rem;
        }

        .modal-header {
            text-align: center;
            margin-bottom: 20px;
            padding-right: 40px;
        }

        .modal-header h2 {
            color: var(--highlight);
            font-size: 1.4rem;
            margin-bottom: 5px;
        }

        /* কন্টেন্ট বক্স */
        .content-box {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            padding: 15px;
            margin-bottom: 15px;
        }

        .content-box h3 {
            color: var(--highlight);
            margin-bottom: 10px;
            font-size: 1.1rem;
        }

        .minister-name {
            background: rgba(15, 52, 96, 0.5);
            padding: 8px 12px;
            border-radius: 20px;
            font-size: 0.8rem;
            margin: 8px 0;
            display: inline-block;
        }

        /* অ্যাকাউন্ট গ্রিড */
        .accounts-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 12px;
            margin-top: 15px;
        }

        .account-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 8px;
            padding: 12px;
            border-left: 4px solid var(--accent);
        }

        .banker-card {
            background: rgba(15, 52, 96, 0.3);
            border-left: 4px solid var(--highlight);
        }

        .account-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
        }

        .account-name {
            font-weight: bold;
            font-size: 0.9rem;
        }

        .account-number {
            font-size: 0.7rem;
            opacity: 0.7;
        }

        .account-balance {
            font-size: 1.3rem;
            font-weight: bold;
            text-align: center;
            padding: 8px;
            border-radius: 5px;
            background: rgba(0, 0, 0, 0.2);
            margin: 8px 0;
        }

        .balance-zero {
            color: var(--warning);
        }

        .balance-positive {
            color: var(--success);
        }

        /* বাটন স্টাইল */
        .btn-group {
            display: flex;
            gap: 10px;
            margin: 15px 0;
            flex-direction: column;
        }

        .btn {
            padding: 12px 20px;
            border: none;
            border-radius: 8px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            text-align: center;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .btn:active {
            transform: scale(0.95);
        }

        .btn-primary {
            background: linear-gradient(45deg, var(--accent), var(--highlight));
            color: white;
        }

        .btn-warning {
            background: linear-gradient(45deg, #f39c12, #e74c3c);
            color: white;
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.1);
            color: white;
        }

        /* ট্যাব স্টাইল */
        .tab-container {
            margin: 20px 0;
        }

        .tab-buttons {
            display: flex;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 8px;
            padding: 5px;
            margin-bottom: 15px;
        }

        .tab-btn {
            flex: 1;
            padding: 10px;
            text-align: center;
            background: transparent;
            border: none;
            color: var(--text);
            cursor: pointer;
            border-radius: 6px;
            transition: all 0.3s ease;
        }

        .tab-btn.active {
            background: var(--highlight);
            color: white;
        }

        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: block;
        }

        /* ফুটার */
        footer {
            text-align: center;
            margin: 30px 0 80px 0;
            padding: 15px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.8rem;
            opacity: 0.7;
        }

        /* লোডিং স্পিনার */
        .loading {
            text-align: center;
            padding: 20px;
        }

        .spinner {
            width: 30px;
            height: 30px;
            border: 3px solid rgba(255, 255, 255, 0.3);
            border-top: 3px solid var(--highlight);
            border-radius: 50%;
            animation: spin 1s linear infinite;
            margin: 0 auto 10px;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* স্ক্রলবার স্টাইল */
        ::-webkit-scrollbar {
            width: 5px;
        }

        ::-webkit-scrollbar-track {
            background: var(--secondary);
        }

        ::-webkit-scrollbar-thumb {
            background: var(--highlight);
            border-radius: 10px;
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
                একটি সুসংগঠিত ও উন্নত সমাজ গঠনের লক্ষ্যে
            </div>
        </header>

        <main>
            <!-- মন্ত্রণালয় সেকশন -->
            <section class="ministries-section">
                <h2 class="section-title">মন্ত্রণালয়সমূহ</h2>
                <div class="ministries-grid" id="ministriesGrid">
                    <!-- মন্ত্রণালয় কার্ডগুলো জাভাস্ক্রিপ্ট দ্বারা লোড হবে -->
                </div>
            </section>

            <!-- কমিটি সেকশন -->
            <section class="committee-section">
                <button class="committee-btn" onclick="openCommittee()">
                    <i class="fas fa-users"></i> কমিটি দেখুন
                </button>
            </section>
        </main>

        <footer>
            <p>© 2025 The Shadow Union. সকল অধিকার সংরক্ষিত।</p>
        </footer>
    </div>

    <!-- মোবাইল নেভিগেশন -->
    <nav class="mobile-nav">
        <a class="nav-item active" onclick="showSection('ministries')">
            <i class="fas fa-landmark nav-icon"></i>
            <span>মন্ত্রণালয়</span>
        </a>
        <a class="nav-item" onclick="openCommittee()">
            <i class="fas fa-users nav-icon"></i>
            <span>কমিটি</span>
        </a>
        <a class="nav-item" onclick="showSection('about')">
            <i class="fas fa-info-circle nav-icon"></i>
            <span>আমাদের সম্পর্কে</span>
        </a>
    </nav>

    <!-- মন্ত্রণালয় মডাল -->
    <div id="ministryModal" class="modal">
        <div class="modal-content">
            <button class="close-btn" onclick="closeModal('ministryModal')">
                <i class="fas fa-times"></i>
            </button>
            <div class="modal-header">
                <h2 id="modalTitle">মন্ত্রণালয়ের নাম</h2>
                <p>The Shadow Union</p>
            </div>
            <div id="modalContent">
                <!-- কন্টেন্ট এখানে লোড হবে -->
            </div>
        </div>
    </div>

    <!-- কমিটি মডাল -->
    <div id="committeeModal" class="modal">
        <div class="modal-content">
            <button class="close-btn" onclick="closeModal('committeeModal')">
                <i class="fas fa-times"></i>
            </button>
            <div class="modal-header">
                <h2>কমিটি</h2>
                <p>The Shadow Union</p>
            </div>
            <div id="committeeContent">
                <!-- কমিটি কন্টেন্ট এখানে লোড হবে -->
            </div>
        </div>
    </div>

    <script>
        // মন্ত্রণালয় ডেটা
        const ministriesData = [
            {
                id: 'swarastra',
                icon: '🔐',
                title: 'স্বরাষ্ট্র',
                description: 'দলের অভ্যন্তরীণ বিষয় ও নিরাপত্তা ব্যবস্থাপনা',
                minister: 'আবতাহি বিন জামিল'
            },
            {
                id: 'pororastro',
                icon: '🌐',
                title: 'পররাষ্ট্র',
                description: 'বাহ্যিক সম্পর্ক ও যোগাযোগ',
                minister: 'আবতাহি বিন জামিল'
            },
            {
                id: 'porikkolpona',
                icon: '📊',
                title: 'পরিকল্পনা',
                description: 'দলের বিভিন্ন প্রকল্প ও কার্যক্রম পরিকল্পনা',
                minister: 'আবতাহি বিন জামিল',
                deputy: 'মুহতাসিম বখতিয়ার রাফাত, ইবতিশাম হক জিসান'
            },
            {
                id: 'protirakkha',
                icon: '🛡️',
                title: 'প্রতিরক্ষা',
                description: 'দলের নিরাপত্তা ও প্রতিরক্ষা ব্যবস্থা',
                minister: 'আবতাহি বিন জামিল'
            },
            {
                id: 'ortho',
                icon: '💰',
                title: 'অর্থ',
                description: 'দলের আর্থিক ব্যবস্থাপনা ও তহবিল',
                minister: 'আবতাহি বিন জামিল'
            },
            {
                id: 'vasa',
                icon: '🗣️',
                title: 'ভাষা',
                description: 'দলের ভাষা ও সংস্কৃতি সংশ্লিষ্ট কার্যক্রম',
                minister: 'আবতাহি বিন জামিল'
            },
            {
                id: 'totto',
                icon: '📡',
                title: 'তথ্য, যোগাযোগ ও সাইবার',
                description: 'দলের তথ্য ব্যবস্থাপনা ও যোগাযোগ',
                minister: 'আবতাহি বিন জামিল'
            }
        ];

        // মন্ত্রণালয় কার্ড লোড করা
        function loadMinistryCards() {
            const grid = document.getElementById('ministriesGrid');
            grid.innerHTML = '';

            ministriesData.forEach(ministry => {
                const card = document.createElement('div');
                card.className = 'ministry-card';
                card.onclick = () => openMinistryModal(ministry.id);
                
                card.innerHTML = `
                    <div class="card-icon">${ministry.icon}</div>
                    <div class="card-title">${ministry.title}</div>
                    <div class="card-minister">${ministry.minister}</div>
                `;
                
                grid.appendChild(card);
            });
        }

        // মন্ত্রণালয় মডাল ওপেন করা
        function openMinistryModal(ministryId) {
            const ministry = ministriesData.find(m => m.id === ministryId);
            if (!ministry) return;

            document.getElementById('modalTitle').textContent = ministry.title;
            document.getElementById('modalContent').innerHTML = getMinistryContent(ministry);
            document.getElementById('ministryModal').style.display = 'block';
        }

        // মন্ত্রণালয় কন্টেন্ট জেনারেট করা
        function getMinistryContent(ministry) {
            let content = `
                <div class="content-box">
                    <h3>${ministry.title} মন্ত্রণালয়</h3>
                    <p>${ministry.description}</p>
                    <div class="minister-name">মন্ত্রী: ${ministry.minister}</div>
                    ${ministry.deputy ? `<div class="minister-name">উপমন্ত্রী: ${ministry.deputy}</div>` : ''}
                </div>
            `;

            // বিশেষ কন্টেন্ট যোগ করা
            if (ministry.id === 'ortho') {
                content += getOrthoContent();
            } else if (ministry.id === 'totto') {
                content += getTottoContent();
            } else if (ministry.id === 'pororastro') {
                content += getPororastroContent();
            }

            content += `
                <div class="btn-group">
                    <button class="btn btn-secondary" onclick="closeModal('ministryModal')">
                        <i class="fas fa-arrow-left"></i> বন্ধ করুন
                    </button>
                </div>
            `;

            return content;
        }

        // অর্থ মন্ত্রণালয় কন্টেন্ট
        function getOrthoContent() {
            return `
                <div class="content-box">
                    <h3>The Shadow Union Reserve Bank</h3>
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
                    </div>
                    <button class="btn btn-warning" onclick="resetAllBalances()" style="margin-top: 15px; width: 100%;">
                        <i class="fas fa-sync-alt"></i> সকলের ব্যালেন্স ০ টাকা করুন
                    </button>
                </div>
            `;
        }

        // তথ্য মন্ত্রণালয় কন্টেন্ট
        function getTottoContent() {
            return `
                <div class="content-box">
                    <h4>দলের অফিসিয়াল অ্যাকাউন্টসমূহ:</h4>
                    <div class="accounts-grid">
                        <div class="account-card">
                            <div class="account-header">
                                <div class="account-name">জিমেইল ১</div>
                            </div>
                            <div class="account-details">
                                <p><strong>ইমেইল:</strong> theshadowunion123@gmail.com</p>
                                <p><strong>পাসওয়ার্ড:</strong> TSU2025@#1234</p>
                            </div>
                        </div>
                        <div class="account-card">
                            <div class="account-header">
                                <div class="account-name">ফেসবুক</div>
                            </div>
                            <div class="account-details">
                                <p><strong>অ্যাকাউন্ট:</strong> mohammed sabbir hossain</p>
                                <p><strong>পাসওয়ার্ড:</strong> TSU2025@#1234</p>
                            </div>
                        </div>
                        <div class="account-card">
                            <div class="account-header">
                                <div class="account-name">ইনস্টাগ্রাম</div>
                            </div>
                            <div class="account-details">
                                <p><strong>অ্যাকাউন্ট:</strong> dadajongiprisoner</p>
                                <p><strong>পাসওয়ার্ড:</strong> amipuronpasa040912</p>
                            </div>
                        </div>
                    </div>
                </div>
            `;
        }

        // পররাষ্ট্র মন্ত্রণালয় কন্টেন্ট
        function getPororastroContent() {
            return `
                <div class="content-box">
                    <h4>আমাদের শত্রু:</h4>
                    <div class="accounts-grid">
                        <div class="account-card" style="border-left-color: #e74c3c;">
                            <div class="account-header">
                                <div class="account-name">ইচ্ছে</div>
                            </div>
                            <div class="account-details">
                                <p><strong>নাম্বার:</strong> ০১৭০১৪৬৯০৫৯</p>
                            </div>
                        </div>
                        <div class="account-card" style="border-left-color: #e74c3c;">
                            <div class="account-header">
                                <div class="account-name">মিসবাহ</div>
                            </div>
                            <div class="account-details">
                                <p><strong>নাম্বার:</strong> ০১৩২২৩২৭৩৩৫</p>
                            </div>
                        </div>
                        <div class="account-card" style="border-left-color: #e74c3c;">
                            <div class="account-header">
                                <div class="account-name">জিল</div>
                            </div>
                            <div class="account-details">
                                <p><strong>ফেসবুক:</strong> mobarok hossain jill</p>
                            </div>
                        </div>
                    </div>
                </div>
            `;
        }

        // কমিটি মডাল ওপেন করা
        function openCommittee() {
            document.getElementById('committeeContent').innerHTML = `
                <div class="content-box">
                    <div class="member-card">
                        <h3>লিডার - আবতাহি বিন জামিল</h3>
                        <p><strong>নাম্বার:</strong> ০১৭৭৪৯৮১৩১২</p>
                        <p><strong>ঠিকানা:</strong> গোপাল্পুর, লালপুর, নাটোর</p>
                        <p><strong>মিডিয়া:</strong> ফেসবুক: Mohammed Sabbir hossain</p>
                    </div>
                    
                    <div class="member-card">
                        <h3>সিনিয়র লিডার - মুহতাসিম বখতিয়ার রাফাত</h3>
                        <p><strong>ঠিকানা:</strong> ফরিদপুর, এবি ইউনিয়ন, লালপুর, নাটোর</p>
                        <p><strong>মিডিয়া:</strong> ফেসবুক: muhtasim bakhtiar rafat</p>
                    </div>
                    
                    <div class="member-card">
                        <h3>সিনিয়র লিডার - ইবতিশাম হক জিসান</h3>
                        <p><strong>নাম্বার:</strong> ০১৮১৮২১৫৯০৪</p>
                        <p><strong>ঠিকানা:</strong> রুইগারি, ওয়ালিয়া ইউনিয়ন, লালপুর, নাটোর</p>
                        <p><strong>মিডিয়া:</strong> ফেসবুক: md ibtisham haque jishan</p>
                    </div>
                    
                    <div class="btn-group">
                        <button class="btn btn-secondary" onclick="closeModal('committeeModal')">
                            <i class="fas fa-arrow-left"></i> বন্ধ করুন
                        </button>
                    </div>
                </div>
            `;
            document.getElementById('committeeModal').style.display = 'block';
        }

        // মডাল বন্ধ করা
        function closeModal(modalId) {
            document.getElementById(modalId).style.display = 'none';
        }

        // ব্যালেন্স রিসেট করা
        function resetAllBalances() {
            const balanceElements = document.querySelectorAll('.account-balance');
            balanceElements.forEach(element => {
                if (!element.closest('.banker-card')) {
                    element.textContent = '৳ 0';
                    element.className = 'account-balance balance-zero';
                }
            });
            alert('সকল সদস্যের ব্যালেন্স ০ টাকা করা হয়েছে!');
        }

        // সেকশন দেখানো
        function showSection(section) {
            // নেভিগেশন আপডেট
            document.querySelectorAll('.nav-item').forEach(item => {
                item.classList.remove('active');
            });
            event.currentTarget.classList.add('active');
            
            // এখানে বিভিন্ন সেকশন হ্যান্ডেল করা যাবে
        }

        // মডালের বাইরে ক্লিক করলে বন্ধ করা
        window.onclick = function(event) {
            const modals = document.querySelectorAll('.modal');
            modals.forEach(modal => {
                if (event.target === modal) {
                    modal.style.display = 'none';
                }
            });
        }

        // পেজ লোড হওয়ার পর কার্ড লোড করা
        document.addEventListener('DOMContentLoaded', function() {
            loadMinistryCards();
            
            // টাচ ইভেন্ট অপ্টিমাইজেশন
            document.addEventListener('touchstart', function() {}, {passive: true});
        });

        // সোয়াইপ জেসচার সাপোর্ট
        let touchStartX = 0;
        let touchEndX = 0;

        document.addEventListener('touchstart', e => {
            touchStartX = e.changedTouches[0].screenX;
        });

        document.addEventListener('touchend', e => {
            touchEndX = e.changedTouches[0].screenX;
            handleSwipe();
        });

        function handleSwipe() {
            const diff = touchStartX - touchEndX;
            if (Math.abs(diff) > 50) { // minimum swipe distance
                if (diff > 0) {
                    // Right swipe - could be used for navigation
                } else {
                    // Left swipe - could be used for navigation
                }
            }
        }
    </script>
</body>
</html>
