# The-Shadow-Union
<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Shadow Union - প্রতিষ্ঠাকাল ২০২৫</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary: #1a2a6c;
            --secondary: #2a3a7c;
            --accent: #ffcc00;
            --light: #f5f5f5;
            --dark: #333;
        }
        
        body {
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.6;
            display: flex;
            min-height: 100vh;
        }
        
        .container {
            display: flex;
            width: 100%;
        }
        
        /* Sidebar Styles */
        .sidebar {
            width: 300px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            height: 100vh;
            position: sticky;
            top: 0;
            overflow-y: auto;
            box-shadow: 3px 0 10px rgba(0, 0, 0, 0.2);
        }
        
        .logo-area {
            padding: 25px 20px;
            text-align: center;
            border-bottom: 2px solid rgba(255, 255, 255, 0.1);
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            margin-bottom: 5px;
            color: var(--accent);
        }
        
        .tagline {
            font-size: 0.9rem;
            opacity: 0.9;
        }
        
        .menu {
            padding: 20px 0;
        }
        
        .menu-section {
            margin-bottom: 10px;
        }
        
        .menu-title {
            padding: 10px 20px;
            font-size: 0.9rem;
            text-transform: uppercase;
            color: var(--accent);
            font-weight: bold;
            letter-spacing: 1px;
        }
        
        .menu-items {
            list-style: none;
        }
        
        .menu-item {
            padding: 12px 20px;
            border-left: 4px solid transparent;
            transition: all 0.3s;
            cursor: pointer;
            display: flex;
            align-items: center;
        }
        
        .menu-item:hover {
            background-color: rgba(255, 255, 255, 0.1);
            border-left-color: var(--accent);
        }
        
        .menu-item.active {
            background-color: rgba(255, 255, 255, 0.15);
            border-left-color: var(--accent);
        }
        
        .menu-item i {
            margin-right: 10px;
            width: 20px;
            text-align: center;
        }
        
        .committee-link {
            background-color: rgba(255, 204, 0, 0.2);
            border-left: 4px solid var(--accent);
            margin: 10px 20px;
            padding: 12px 15px;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
        
        .committee-link:hover {
            background-color: rgba(255, 204, 0, 0.3);
            transform: translateX(5px);
        }
        
        .committee-link i {
            color: var(--accent);
        }
        
        /* Main Content Styles */
        .main-content {
            flex: 1;
            padding: 30px;
            overflow-y: auto;
        }
        
        .page-header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 25px 30px;
            border-radius: 10px;
            margin-bottom: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .page-title {
            font-size: 2rem;
            margin-bottom: 10px;
        }
        
        .page-subtitle {
            font-size: 1.1rem;
            opacity: 0.9;
        }
        
        .content-card {
            background-color: white;
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            margin-bottom: 30px;
        }
        
        .card-title {
            font-size: 1.5rem;
            color: var(--primary);
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid var(--accent);
            display: inline-block;
        }
        
        .minister-info {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
            padding: 15px;
            background-color: rgba(26, 42, 108, 0.05);
            border-radius: 8px;
        }
        
        .minister-avatar {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background-color: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 2rem;
            margin-right: 20px;
        }
        
        .minister-details h3 {
            color: var(--primary);
            margin-bottom: 5px;
        }
        
        .minister-details p {
            color: #666;
        }
        
        .responsibilities {
            margin-top: 25px;
        }
        
        .responsibilities h4 {
            color: var(--primary);
            margin-bottom: 15px;
        }
        
        .responsibilities ul {
            list-style-type: none;
        }
        
        .responsibilities li {
            padding: 8px 0;
            border-bottom: 1px solid #eee;
            display: flex;
            align-items: center;
        }
        
        .responsibilities li:before {
            content: "•";
            color: var(--accent);
            font-weight: bold;
            margin-right: 10px;
        }
        
        .hidden {
            display: none;
        }
        
        /* Committee Page Styles */
        .committee-page {
            background-color: white;
            padding: 40px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .committee-header {
            text-align: center;
            margin-bottom: 40px;
        }
        
        .committee-title {
            color: var(--primary);
            font-size: 2.2rem;
            margin-bottom: 10px;
        }
        
        .committee-subtitle {
            color: #666;
            font-size: 1.1rem;
        }
        
        .members-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 25px;
        }
        
        .member-card {
            background: linear-gradient(135deg, #f8f9fa, #e9ecef);
            border-radius: 10px;
            padding: 25px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s;
        }
        
        .member-card:hover {
            transform: translateY(-5px);
        }
        
        .member-avatar {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background-color: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.8rem;
            margin: 0 auto 15px;
        }
        
        .member-name {
            font-size: 1.2rem;
            color: var(--primary);
            margin-bottom: 5px;
        }
        
        .member-position {
            color: var(--accent);
            font-weight: bold;
            margin-bottom: 10px;
        }
        
        .member-bio {
            color: #666;
            font-size: 0.9rem;
        }
        
        .leader-card {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
        }
        
        .leader-card .member-name,
        .leader-card .member-bio {
            color: white;
        }
        
        .leader-card .member-position {
            color: var(--accent);
        }
        
        /* Mobile Responsive */
        @media (max-width: 992px) {
            .container {
                flex-direction: column;
            }
            
            .sidebar {
                width: 100%;
                height: auto;
                position: relative;
            }
            
            .menu-items {
                display: flex;
                flex-wrap: wrap;
            }
            
            .menu-item {
                flex: 1 0 50%;
            }
            
            .main-content {
                padding: 20px;
            }
        }
        
        @media (max-width: 576px) {
            .menu-item {
                flex: 1 0 100%;
            }
            
            .members-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Sidebar -->
        <div class="sidebar">
            <div class="logo-area">
                <div class="logo">The Shadow Union</div>
                <div class="tagline">প্রতিষ্ঠাকাল ২০২৫</div>
            </div>
            
            <div class="menu">
                <div class="committee-link" onclick="openCommitteePage()">
                    <span><i class="fas fa-users"></i> কমিটি</span>
                    <i class="fas fa-external-link-alt"></i>
                </div>
                
                <div class="menu-section">
                    <div class="menu-title">মন্ত্রণালয়সমূহ</div>
                    <ul class="menu-items">
                        <li class="menu-item active" data-ministry="home">
                            <i class="fas fa-home"></i> হোম
                        </li>
                        <li class="menu-item" data-ministry="swarastra">
                            <i class="fas fa-landmark"></i> স্বরাষ্ট্র
                        </li>
                        <li class="menu-item" data-ministry="pororastra">
                            <i class="fas fa-globe-asia"></i> পররাষ্ট্র
                        </li>
                        <li class="menu-item" data-ministry="porikalpana">
                            <i class="fas fa-chart-line"></i> পরিকল্পনা
                        </li>
                        <li class="menu-item" data-ministry="protirodha">
                            <i class="fas fa-shield-alt"></i> প্রতিরক্ষা
                        </li>
                        <li class="menu-item" data-ministry="bhasa">
                            <i class="fas fa-language"></i> ভাষা
                        </li>
                        <li class="menu-item" data-ministry="ortho">
                            <i class="fas fa-money-bill-wave"></i> অর্থ
                        </li>
                        <li class="menu-item" data-ministry="gongsongjog">
                            <i class="fas fa-bullhorn"></i> গণসংযোগ
                        </li>
                        <li class="menu-item" data-ministry="shikkha">
                            <i class="fas fa-graduation-cap"></i> শিক্ষা
                        </li>
                        <li class="menu-item" data-ministry="shilpo">
                            <i class="fas fa-industry"></i> শিল্প
                        </li>
                        <li class="menu-item" data-ministry="shomajkallyan">
                            <i class="fas fa-hands-helping"></i> সমাজকল্যাণ
                        </li>
                        <li class="menu-item" data-ministry="bhumi">
                            <i class="fas fa-mountain"></i> ভূমি
                        </li>
                        <li class="menu-item" data-ministry="biggan">
                            <i class="fas fa-flask"></i> বিজ্ঞান ও প্রযুক্তি
                        </li>
                        <li class="menu-item" data-ministry="totho">
                            <i class="fas fa-network-wired"></i> তথ্য, যোগাযোগ ও সাইবার
                        </li>
                        <li class="menu-item" data-ministry="shastho">
                            <i class="fas fa-heartbeat"></i> স্বাস্থ্য
                        </li>
                        <li class="menu-item" data-ministry="krida">
                            <i class="fas fa-running"></i> ক্রীড়া
                        </li>
                        <li class="menu-item" data-ministry="poribesh">
                            <i class="fas fa-leaf"></i> পরিবেশ
                        </li>
                        <li class="menu-item" data-ministry="banijjo">
                            <i class="fas fa-shopping-cart"></i> বাণিজ্য
                        </li>
                        <li class="menu-item" data-ministry="ain">
                            <i class="fas fa-gavel"></i> আইন ও বিচার
                        </li>
                        <li class="menu-item" data-ministry="nirbachon">
                            <i class="fas fa-vote-yea"></i> স্থানীয় ও নির্বাচন
                        </li>
                        <li class="menu-item" data-ministry="khaddo">
                            <i class="fas fa-utensils"></i> খাদ্য
                        </li>
                    </ul>
                </div>
            </div>
        </div>
        
        <!-- Main Content -->
        <div class="main-content">
            <!-- Home Page -->
            <div id="home" class="content-page">
                <div class="page-header">
                    <h1 class="page-title">The Shadow Union</h1>
                    <p class="page-subtitle">প্রতিষ্ঠাকাল ২০২৫ - একটি নতুন দিগন্তের সূচনা</p>
                </div>
                
                <div class="content-card">
                    <h2 class="card-title">দলের পরিচিতি</h2>
                    <p>The Shadow Union একটি অগ্রসরমান রাজনৈতিক দল, যার লক্ষ্য দেশ ও জনগণের সার্বিক উন্নয়ন। আমাদের মূলমন্ত্র হলো - "জনগণের সেবাই সর্বোচ্চ সেবা"। আমরা বিশ্বাস করি সুশাসন, স্বচ্ছতা ও জবাবদিহিতার মাধ্যমে একটি উন্নত ও সমৃদ্ধ বাংলাদেশ গড়ে তোলা সম্ভব।</p>
                    
                    <div class="responsibilities">
                        <h4>আমাদের লক্ষ্যসমূহ:</h4>
                        <ul>
                            <li>সকল নাগরিকের জন্য মৌলিক চাহিদা নিশ্চিতকরণ</li>
                            <li>দারিদ্র্যমুক্ত ও সুখী সমাজ গঠন</li>
                            <li>শিক্ষা ও স্বাস্থ্য ব্যবস্থার আধুনিকায়ন</li>
                            <li>ডিজিটাল বাংলাদেশের সম্প্রসারণ</li>
                            <li>নারী ও শিশু উন্নয়ন</li>
                            <li>পরিবেশবান্ধব উন্নয়ন নিশ্চিতকরণ</li>
                        </ul>
                    </div>
                </div>
                
                <div class="content-card">
                    <h2 class="card-title">মন্ত্রিসভা</h2>
                    <p>দলের কার্যক্রম সুষ্ঠুভাবে পরিচালনার জন্য ২০টি মন্ত্রণালয় গঠন করা হয়েছে। প্রতিটি মন্ত্রণালয়ের দায়িত্বে রয়েছেন দক্ষ ও অভিজ্ঞ মন্ত্রীবৃন্দ।</p>
                    
                    <div class="minister-info">
                        <div class="minister-avatar">
                            <i class="fas fa-user"></i>
                        </div>
                        <div class="minister-details">
                            <h3>আবতাহি বিন জামিল</h3>
                            <p>প্রধান মন্ত্রী ও ১৬টি মন্ত্রণালয়ের দায়িত্বে</p>
                        </div>
                    </div>
                    
                    <div class="minister-info">
                        <div class="minister-avatar">
                            <i class="fas fa-user"></i>
                        </div>
                        <div class="minister-details">
                            <h3>মুহতাসিম বাখতিয়ার রাফাত</h3>
                            <p>স্থানীয় ও নির্বাচন মন্ত্রী এবং ৪টি মন্ত্রণালয়ের উপমন্ত্রী</p>
                        </div>
                    </div>
                    
                    <div class="minister-info">
                        <div class="minister-avatar">
                            <i class="fas fa-user"></i>
                        </div>
                        <div class="minister-details">
                            <h3>ইবতিশাম হক জিসান</h3>
                            <p>খাদ্য ও সমাজকল্যাণ মন্ত্রী এবং পরিকল্পনা উপমন্ত্রী</p>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Ministry Detail Pages (Initially Hidden) -->
            <div id="swarastra" class="content-page hidden">
                <div class="page-header">
                    <h1 class="page-title">স্বরাষ্ট্র মন্ত্রণালয়</h1>
                    <p class="page-subtitle">দেশের অভ্যন্তরীণ নিরাপত্তা ও শৃঙ্খলা রক্ষায় নিবেদিত</p>
                </div>
                
                <div class="content-card">
                    <h2 class="card-title">মন্ত্রী: আবতাহি বিন জামিল</h2>
                    
                    <div class="responsibilities">
                        <h4>দায়িত্বসমূহ:</h4>
                        <ul>
                            <li>দেশের অভ্যন্তরীণ নিরাপত্তা নিশ্চিতকরণ</li>
                            <li>আইন-শৃঙ্খলা রক্ষায় পদক্ষেপ গ্রহণ</li>
                            <li>পুলিশ ও অন্যান্য নিরাপত্তা বাহিনীর তত্ত্বাবধান</li>
                            <li>জনসাধারণের নিরাপত্তা নিশ্চিতকরণ</li>
                            <li>সীমান্ত নিরাপত্তা ব্যবস্থা জোরদারকরণ</li>
                        </ul>
                    </div>
                </div>
            </div>
            
            <!-- Other ministry pages would follow similar structure -->
            <!-- For brevity, I'm showing only one example -->
            
            <div id="porikalpana" class="content-page hidden">
                <div class="page-header">
                    <h1 class="page-title">পরিকল্পনা মন্ত্রণালয়</h1>
                    <p class="page-subtitle">দেশের উন্নয়ন পরিকল্পনা ও বাস্তবায়ন</p>
                </div>
                
                <div class="content-card">
                    <h2 class="card-title">মন্ত্রী: আবতাহি বিন জামিল</h2>
                    <h3 class="card-title">উপমন্ত্রী: ইবতিশাম হক জিসান</h3>
                    
                    <div class="responsibilities">
                        <h4>দায়িত্বসমূহ:</h4>
                        <ul>
                            <li>জাতীয় উন্নয়ন পরিকল্পনা প্রণয়ন</li>
                            <li>বিভিন্ন প্রকল্পের মূল্যায়ন ও অনুমোদন</li>
                            <li>অর্থনৈতিক নীতি প্রণয়নে সহায়তা</li>
                            <li>উন্নয়ন সহযোগী সংস্থার সাথে সমন্বয়</li>
                            <li>উন্নয়ন প্রকল্পের মনিটরিং ও মূল্যায়ন</li>
                        </ul>
                    </div>
                </div>
            </div>
            
            <div id="nirbachon" class="content-page hidden">
                <div class="page-header">
                    <h1 class="page-title">স্থানীয় ও নির্বাচন মন্ত্রণালয়</h1>
                    <p class="page-subtitle">স্থানীয় সরকার ও নির্বাচন ব্যবস্থাপনা</p>
                </div>
                
                <div class="content-card">
                    <h2 class="card-title">মন্ত্রী: মুহতাসিম বাখতিয়ার রাফাত</h2>
                    
                    <div class="responsibilities">
                        <h4>দায়িত্বসমূহ:</h4>
                        <ul>
                            <li>স্থানীয় সরকার প্রতিষ্ঠানসমূহের তত্ত্বাবধান</li>
                            <li>নির্বাচনী ব্যবস্থা সংস্কার</li>
                            <li>নির্বাচন কমিশনের সাথে সমন্বয়</li>
                            <li>স্থানীয় পর্যায়ে উন্নয়ন প্রকল্প বাস্তবায়ন</li>
                            <li>জনপ্রতিনিধিদের প্রশিক্ষণ ও উন্নয়ন</li>
                        </ul>
                    </div>
                </div>
            </div>
            
            <div id="khaddo" class="content-page hidden">
                <div class="page-header">
                    <h1 class="page-title">খাদ্য মন্ত্রণালয়</h1>
                    <p class="page-subtitle">দেশের খাদ্য নিরাপত্তা নিশ্চিতকরণ</p>
                </div>
                
                <div class="content-card">
                    <h2 class="card-title">মন্ত্রী: ইবতিশাম হক জিসান</h2>
                    
                    <div class="responsibilities">
                        <h4>দায়িত্বসমূহ:</h4>
                        <ul>
                            <li>খাদ্য উৎপাদন ও সরবরাহ নিশ্চিতকরণ</li>
                            <li>খাদ্য গুদাম ব্যবস্থাপনা</li>
                            <li>খাদ্য মূল্য স্থিতিশীল রাখা</li>
                            <li>খাদ্য নিরাপত্তা নীতি প্রণয়ন</li>
                            <li>দুর্যোগকালীন খাদ্য ব্যবস্থাপনা</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Ministry navigation
        document.querySelectorAll('.menu-item').forEach(item => {
            item.addEventListener('click', function() {
                // Remove active class from all items
                document.querySelectorAll('.menu-item').forEach(i => {
                    i.classList.remove('active');
                });
                
                // Add active class to clicked item
                this.classList.add('active');
                
                // Hide all content pages
                document.querySelectorAll('.content-page').forEach(page => {
                    page.classList.add('hidden');
                });
                
                // Show selected content page
                const ministry = this.getAttribute('data-ministry');
                document.getElementById(ministry).classList.remove('hidden');
            });
        });
        
        // Committee page function
        function openCommitteePage() {
            const committeePage = `
                <!DOCTYPE html>
                <html lang="bn">
                <head>
                    <meta charset="UTF-8">
                    <meta name="viewport" content="width=device-width, initial-scale=1.0">
                    <title>The Shadow Union - কমিটি</title>
                    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
                    <style>
                        body {
                            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
                            background: linear-gradient(135deg, #1a2a6c, #2a3a7c);
                            color: white;
                            margin: 0;
                            padding: 0;
                            min-height: 100vh;
                        }
                        
                        .committee-container {
                            max-width: 1200px;
                            margin: 0 auto;
                            padding: 40px 20px;
                        }
                        
                        .committee-header {
                            text-align: center;
                            margin-bottom: 50px;
                        }
                        
                        .committee-title {
                            font-size: 2.5rem;
                            margin-bottom: 10px;
                            color: #ffcc00;
                        }
                        
                        .committee-subtitle {
                            font-size: 1.2rem;
                            opacity: 0.9;
                        }
                        
                        .members-grid {
                            display: grid;
                            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
                            gap: 30px;
                        }
                        
                        .member-card {
                            background: rgba(255, 255, 255, 0.1);
                            border-radius: 15px;
                            padding: 30px;
                            text-align: center;
                            backdrop-filter: blur(10px);
                            border: 1px solid rgba(255, 255, 255, 0.2);
                            transition: transform 0.3s;
                        }
                        
                        .member-card:hover {
                            transform: translateY(-10px);
                        }
                        
                        .member-avatar {
                            width: 100px;
                            height: 100px;
                            border-radius: 50%;
                            background: rgba(255, 204, 0, 0.2);
                            display: flex;
                            align-items: center;
                            justify-content: center;
                            margin: 0 auto 20px;
                            font-size: 2.5rem;
                            color: #ffcc00;
                        }
                        
                        .member-name {
                            font-size: 1.4rem;
                            margin-bottom: 10px;
                        }
                        
                        .member-position {
                            color: #ffcc00;
                            font-weight: bold;
                            margin-bottom: 15px;
                            font-size: 1.1rem;
                        }
                        
                        .member-bio {
                            opacity: 0.8;
                            line-height: 1.6;
                        }
                        
                        .leader-card {
                            background: rgba(255, 204, 0, 0.15);
                            border: 1px solid rgba(255, 204, 0, 0.3);
                        }
                        
                        .back-btn {
                            display: inline-block;
                            margin-top: 40px;
                            padding: 12px 30px;
                            background: #ffcc00;
                            color: #1a2a6c;
                            text-decoration: none;
                            border-radius: 5px;
                            font-weight: bold;
                            transition: background 0.3s;
                        }
                        
                        .back-btn:hover {
                            background: #e6b800;
                        }
                    </style>
                </head>
                <body>
                    <div class="committee-container">
                        <div class="committee-header">
                            <h1 class="committee-title">The Shadow Union কমিটি</h1>
                            <p class="committee-subtitle">দলের নেতৃত্ব ও পরিচালনা কমিটি</p>
                        </div>
                        
                        <div class="members-grid">
                            <div class="member-card leader-card">
                                <div class="member-avatar">
                                    <i class="fas fa-crown"></i>
                                </div>
                                <h2 class="member-name">আবতাহি বিন জামিল</h2>
                                <div class="member-position">লিডার</div>
                                <p class="member-bio">দলের প্রধান নেতা ও সর্বোচ্চ নীতিনির্ধারক। ১৬টি মন্ত্রণালয়ের দায়িত্বে রয়েছেন।</p>
                            </div>
                            
                            <div class="member-card leader-card">
                                <div class="member-avatar">
                                    <i class="fas fa-star"></i>
                                </div>
                                <h2 class="member-name">মুহতাসিম বখতিয়ার রাফাত</h2>
                                <div class="member-position">সিনিয়র লিডার</div>
                                <p class="member-bio">স্থানীয় ও নির্বাচন মন্ত্রী এবং ৪টি মন্ত্রণালয়ের উপমন্ত্রী। দলের অন্যতম প্রধান নীতিনির্ধারক।</p>
                            </div>
                            
                            <div class="member-card leader-card">
                                <div class="member-avatar">
                                    <i class="fas fa-star"></i>
                                </div>
                                <h2 class="member-name">ইবতিশাম হক জিসান</h2>
                                <div class="member-position">সিনিয়র লিডার</div>
                                <p class="member-bio">খাদ্য ও সমাজকল্যাণ মন্ত্রী এবং পরিকল্পনা উপমন্ত্রী। দলের অন্যতম প্রধান নীতিনির্ধারক।</p>
                            </div>
                            
                            <div class="member-card">
                                <div class="member-avatar">
                                    <i class="fas fa-user"></i>
                                </div>
                                <h2 class="member-name">অরিক হোসাইন</h2>
                                <div class="member-position">সদস্য</div>
                                <p class="member-bio">দলের গুরুত্বপূর্ণ সদস্য ও বিভিন্ন কমিটিতে সক্রিয় ভূমিকা পালন করছেন।</p>
                            </div>
                            
                            <div class="member-card">
                                <div class="member-avatar">
                                    <i class="fas fa-user"></i>
                                </div>
                                <h2 class="member-name">আদনান হোসেন</h2>
                                <div class="member-position">সদস্য</div>
                                <p class="member-bio">দলের গুরুত্বপূর্ণ সদস্য ও বিভিন্ন কমিটিতে সক্রিয় ভূমিকা পালন করছেন।</p>
                            </div>
                        </div>
                        
                        <div style="text-align: center;">
                            <a href="#" onclick="window.close()" class="back-btn">প্রধান পেজে ফিরে যান</a>
                        </div>
                    </div>
                </body>
                </html>
            `;
            
            const newWindow = window.open('', '_blank');
            newWindow.document.write(committeePage);
            newWindow.document.close();
        }
    </script>
</body>
</html>
