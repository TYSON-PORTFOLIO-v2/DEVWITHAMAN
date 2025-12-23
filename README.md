<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DevWithAman - Premium Game Development Package</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        :root {
            --primary: #6366f1;
            --primary-dark: #4f46e5;
            --secondary: #10b981;
            --accent: #f59e0b;
            --dark: #1e293b;
            --darker: #0f172a;
            --light: #f8fafc;
            --gray: #64748b;
            --success: #22c55e;
            --danger: #ef4444;
            --glass: rgba(255, 255, 255, 0.05);
            --glass-border: rgba(255, 255, 255, 0.1);
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #0f172a 0%, #1e293b 100%);
            color: var(--light);
            min-height: 100vh;
            overflow-x: hidden;
        }
        
        .background-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            overflow: hidden;
        }
        
        .particle {
            position: absolute;
            border-radius: 50%;
            background: radial-gradient(circle, var(--primary) 0%, transparent 70%);
            opacity: 0.1;
            animation: float 20s infinite linear;
        }
        
        @keyframes float {
            0% { transform: translateY(0) rotate(0deg); }
            100% { transform: translateY(-1000px) rotate(720deg); }
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
        }
        
        /* Header */
        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
            margin-bottom: 30px;
            border-bottom: 1px solid var(--glass-border);
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .logo-icon {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
        }
        
        .logo-text h1 {
            font-size: 28px;
            font-weight: 700;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .logo-text span {
            font-size: 14px;
            color: var(--gray);
        }
        
        .contact-links {
            display: flex;
            gap: 15px;
        }
        
        .social-btn {
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 12px 24px;
            background: var(--glass);
            border: 1px solid var(--glass-border);
            border-radius: 10px;
            color: var(--light);
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }
        
        .social-btn:hover {
            transform: translateY(-3px);
            background: var(--primary);
            border-color: var(--primary);
        }
        
        .social-btn.youtube {
            color: #ff0000;
        }
        
        .social-btn.telegram {
            color: #0088cc;
        }
        
        .social-btn.youtube:hover, .social-btn.telegram:hover {
            color: white;
        }
        
        /* Hero Section */
        .hero {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .hero-left {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }
        
        .hero-tag {
            display: inline-block;
            padding: 8px 20px;
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            border-radius: 50px;
            font-size: 14px;
            font-weight: 600;
            letter-spacing: 1px;
            width: fit-content;
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        
        .hero-title {
            font-size: 48px;
            font-weight: 800;
            line-height: 1.2;
        }
        
        .hero-title span {
            background: linear-gradient(to right, var(--secondary), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .hero-subtitle {
            font-size: 18px;
            color: var(--gray);
            line-height: 1.6;
        }
        
        .stats {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
        }
        
        .stat-card {
            background: var(--glass);
            border: 1px solid var(--glass-border);
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            backdrop-filter: blur(10px);
            transition: transform 0.3s ease;
        }
        
        .stat-card:hover {
            transform: translateY(-5px);
            border-color: var(--primary);
        }
        
        .stat-number {
            font-size: 32px;
            font-weight: 700;
            color: var(--secondary);
            margin-bottom: 5px;
        }
        
        .stat-label {
            font-size: 14px;
            color: var(--gray);
        }
        
        /* Package Cards */
        .package-section {
            margin-bottom: 50px;
        }
        
        .section-title {
            font-size: 32px;
            font-weight: 700;
            margin-bottom: 30px;
            text-align: center;
        }
        
        .packages {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 30px;
            margin-bottom: 40px;
        }
        
        @media (max-width: 1024px) {
            .packages {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        
        @media (max-width: 768px) {
            .packages {
                grid-template-columns: 1fr;
            }
        }
        
        .package-card {
            background: linear-gradient(145deg, var(--glass), rgba(30, 41, 59, 0.5));
            border: 1px solid var(--glass-border);
            border-radius: 20px;
            padding: 30px;
            position: relative;
            overflow: hidden;
            transition: all 0.4s ease;
            backdrop-filter: blur(10px);
        }
        
        .package-card:hover {
            transform: translateY(-10px);
            border-color: var(--primary);
            box-shadow: 0 20px 40px rgba(99, 102, 241, 0.2);
        }
        
        .package-card.premium {
            border: 2px solid var(--accent);
            transform: scale(1.05);
        }
        
        .package-card.premium:hover {
            transform: scale(1.05) translateY(-10px);
        }
        
        .package-badge {
            position: absolute;
            top: 20px;
            right: 20px;
            background: var(--accent);
            color: var(--darker);
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: 600;
        }
        
        .package-icon {
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            margin-bottom: 20px;
        }
        
        .package-title {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 15px;
        }
        
        .package-price {
            font-size: 42px;
            font-weight: 800;
            color: var(--secondary);
            margin-bottom: 20px;
        }
        
        .package-price span {
            font-size: 16px;
            color: var(--gray);
        }
        
        .features-list {
            list-style: none;
            margin-bottom: 25px;
        }
        
        .features-list li {
            padding: 8px 0;
            display: flex;
            align-items: center;
            gap: 10px;
            border-bottom: 1px solid var(--glass-border);
        }
        
        .features-list li:last-child {
            border-bottom: none;
        }
        
        .features-list i {
            color: var(--secondary);
        }
        
        /* Payment Gateway */
        .payment-gateway {
            background: linear-gradient(145deg, rgba(30, 41, 59, 0.8), rgba(15, 23, 42, 0.9));
            border-radius: 25px;
            padding: 40px;
            border: 1px solid var(--glass-border);
            backdrop-filter: blur(20px);
            margin-bottom: 50px;
        }
        
        .payment-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
        }
        
        .payment-title {
            font-size: 32px;
            font-weight: 700;
        }
        
        .payment-steps {
            display: flex;
            gap: 20px;
            margin-bottom: 40px;
        }
        
        .step {
            flex: 1;
            text-align: center;
            position: relative;
        }
        
        .step-number {
            width: 50px;
            height: 50px;
            background: var(--glass);
            border: 2px solid var(--primary);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            margin: 0 auto 15px;
            position: relative;
            z-index: 2;
        }
        
        .step.active .step-number {
            background: var(--primary);
        }
        
        .step-line {
            position: absolute;
            top: 25px;
            left: calc(50% + 25px);
            right: calc(-50% + 25px);
            height: 2px;
            background: var(--glass-border);
            z-index: 1;
        }
        
        .step.active .step-line {
            background: var(--primary);
        }
        
        .step:last-child .step-line {
            display: none;
        }
        
        .payment-grid {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 40px;
        }
        
        .payment-info {
            background: var(--glass);
            border-radius: 20px;
            padding: 30px;
            border: 1px solid var(--glass-border);
        }
        
        .order-summary {
            background: rgba(0, 0, 0, 0.2);
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 30px;
        }
        
        .summary-item {
            display: flex;
            justify-content: space-between;
            padding: 15px 0;
            border-bottom: 1px solid var(--glass-border);
        }
        
        .summary-item:last-child {
            border-bottom: none;
        }
        
        .summary-label {
            color: var(--gray);
        }
        
        .summary-value {
            font-weight: 600;
        }
        
        .total {
            font-size: 36px;
            font-weight: 800;
            color: var(--secondary);
        }
        
        .timer-container {
            background: linear-gradient(135deg, var(--primary-dark), var(--primary));
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            margin-bottom: 30px;
        }
        
        .timer-label {
            font-size: 14px;
            color: rgba(255, 255, 255, 0.8);
            margin-bottom: 10px;
        }
        
        .timer {
            font-size: 48px;
            font-weight: 800;
            font-family: monospace;
            letter-spacing: 5px;
        }
        
        .upi-container {
            background: var(--glass);
            border-radius: 15px;
            padding: 25px;
            text-align: center;
        }
        
        .upi-id {
            font-size: 28px;
            font-weight: 700;
            color: var(--secondary);
            margin: 20px 0;
            word-break: break-all;
            background: rgba(0, 0, 0, 0.2);
            padding: 15px;
            border-radius: 10px;
            border: 1px solid var(--glass-border);
        }
        
        .action-buttons {
            display: flex;
            gap: 15px;
            justify-content: center;
        }
        
        .btn {
            padding: 15px 30px;
            border-radius: 10px;
            border: none;
            font-weight: 600;
            font-size: 16px;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }
        
        .btn-primary {
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            color: white;
        }
        
        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(99, 102, 241, 0.3);
        }
        
        .btn-secondary {
            background: var(--glass);
            color: var(--light);
            border: 1px solid var(--glass-border);
        }
        
        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.1);
            transform: translateY(-3px);
        }
        
        .qr-section {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
        }
        
        .qr-code {
            width: 250px;
            height: 250px;
            background: white;
            border-radius: 15px;
            padding: 15px;
            margin-bottom: 20px;
        }
        
        .qr-instruction {
            text-align: center;
            color: var(--gray);
            font-size: 14px;
        }
        
        .upcoming-features {
            margin-top: 50px;
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }
        
        .feature-card {
            background: var(--glass);
            border: 1px solid var(--glass-border);
            border-radius: 15px;
            padding: 25px;
            transition: all 0.3s ease;
        }
        
        .feature-card:hover {
            border-color: var(--primary);
            transform: translateY(-5px);
        }
        
        .feature-icon {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            margin-bottom: 20px;
        }
        
        .feature-title {
            font-size: 18px;
            font-weight: 600;
            margin-bottom: 10px;
        }
        
        .feature-desc {
            color: var(--gray);
            font-size: 14px;
            line-height: 1.6;
        }
        
        /* Footer */
        .footer {
            text-align: center;
            padding: 40px 0;
            border-top: 1px solid var(--glass-border);
            color: var(--gray);
            font-size: 14px;
        }
        
        .footer-links {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-bottom: 20px;
        }
        
        .footer-links a {
            color: var(--gray);
            text-decoration: none;
            transition: color 0.3s ease;
        }
        
        .footer-links a:hover {
            color: var(--primary);
        }
        
        /* Responsive */
        @media (max-width: 1024px) {
            .hero {
                grid-template-columns: 1fr;
            }
            
            .payment-grid {
                grid-template-columns: 1fr;
            }
        }
        
        @media (max-width: 768px) {
            .header {
                flex-direction: column;
                gap: 20px;
            }
            
            .contact-links {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .hero-title {
                font-size: 36px;
            }
            
            .stats {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .payment-steps {
                flex-direction: column;
                gap: 30px;
            }
            
            .step-line {
                display: none;
            }
        }
        
        @media (max-width: 480px) {
            .stats {
                grid-template-columns: 1fr;
            }
            
            .action-buttons {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <!-- Background Animation -->
    <div class="background-animation" id="particles"></div>
    
    <div class="container">
        <!-- Header -->
        <header class="header">
            <div class="logo">
                <div class="logo-icon">
                    <i class="fas fa-code"></i>
                </div>
                <div class="logo-text">
                    <h1>DevWithAman</h1>
                    <span>Premium Game Development</span>
                </div>
            </div>
            
            <div class="contact-links">
                <a href="https://youtube.com/@devloperwithaman?si=rQ-VnW3eYdFs9_n1" target="_blank" class="social-btn youtube">
                    <i class="fab fa-youtube"></i> YouTube
                </a>
                <a href="https://t.me/pluginxpertcode" target="_blank" class="social-btn telegram">
                    <i class="fab fa-telegram"></i> Telegram
                </a>
            </div>
        </header>
        
        <!-- Hero Section -->
        <section class="hero">
            <div class="hero-left">
                <div class="hero-tag">
                    <i class="fas fa-bolt"></i> LIMITED TIME OFFER
                </div>
                <h1 class="hero-title">
                    Complete Game Development <span>Package</span> in 24 Hours
                </h1>
                <p class="hero-subtitle">
                    Get your game live with full setup including hosting, domain, admin panel, user panel, script, APK, website, and phpMyAdmin. Everything you need to start your gaming platform.
                </p>
                
                <div class="stats">
                    <div class="stat-card">
                        <div class="stat-number">24h</div>
                        <div class="stat-label">Delivery Time</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number">9+</div>
                        <div class="stat-label">Features Included</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number">100%</div>
                        <div class="stat-label">Client Satisfaction</div>
                    </div>
                </div>
            </div>
            
            <div class="hero-right">
                <div class="package-card premium">
                    <div class="package-badge">
                        <i class="fas fa-crown"></i> MOST POPULAR
                    </div>
                    <div class="package-icon">
                        <i class="fas fa-gamepad"></i>
                    </div>
                    <h3 class="package-title">Complete Game Package</h3>
                    <div class="package-price">₹10,000 <span>/one-time</span></div>
                    
                    <ul class="features-list">
                        <li><i class="fas fa-check-circle"></i> 1 Year Premium Hosting</li>
                        <li><i class="fas fa-check-circle"></i> 1 Year Domain (.com/.in)</li>
                        <li><i class="fas fa-check-circle"></i> Advanced Admin Panel</li>
                        <li><i class="fas fa-check-circle"></i> User Panel with Dashboard</li>
                        <li><i class="fas fa-check-circle"></i> Complete Game Script</li>
                        <li><i class="fas fa-check-circle"></i> Android APK (Signed)</li>
                        <li><i class="fas fa-check-circle"></i> Responsive Website</li>
                        <li><i class="fas fa-check-circle"></i> phpMyAdmin Access</li>
                        <li><i class="fas fa-check-circle"></i> 24/7 Technical Support</li>
                    </ul>
                    
                    <button class="btn btn-primary" style="width: 100%;" onclick="scrollToPayment()">
                        <i class="fas fa-shopping-cart"></i> Get This Package
                    </button>
                </div>
            </div>
        </section>
        
        <!-- Package Comparison -->
        <section class="package-section">
            <h2 class="section-title">Choose Your Perfect Package</h2>
            <div class="packages">
                <div class="package-card">
                    <div class="package-icon">
                        <i class="fas fa-mobile-alt"></i>
                    </div>
                    <h3 class="package-title">Basic Setup</h3>
                    <div class="package-price">₹5,000 <span>/one-time</span></div>
                    
                    <ul class="features-list">
                        <li><i class="fas fa-check"></i> 6 Months Hosting</li>
                        <li><i class="fas fa-check"></i> Basic Admin Panel</li>
                        <li><i class="fas fa-check"></i> User Panel</li>
                        <li><i class="fas fa-check"></i> Game Script</li>
                        <li><i class="fas fa-times" style="color: var(--danger);"></i> No APK</li>
                        <li><i class="fas fa-times" style="color: var(--danger);"></i> No Custom Domain</li>
                    </ul>
                    
                    <button class="btn btn-secondary" style="width: 100%;" onclick="selectPackage('basic')">
                        Select Basic
                    </button>
                </div>
                
                <div class="package-card premium">
                    <div class="package-badge">
                        <i class="fas fa-crown"></i> RECOMMENDED
                    </div>
                    <div class="package-icon">
                        <i class="fas fa-gamepad"></i>
                    </div>
                    <h3 class="package-title">Complete Package</h3>
                    <div class="package-price">₹10,000 <span>/one-time</span></div>
                    
                    <ul class="features-list">
                        <li><i class="fas fa-check-circle"></i> 1 Year Premium Hosting</li>
                        <li><i class="fas fa-check-circle"></i> 1 Year Domain (.com/.in)</li>
                        <li><i class="fas fa-check-circle"></i> Advanced Admin Panel</li>
                        <li><i class="fas fa-check-circle"></i> User Panel with Dashboard</li>
                        <li><i class="fas fa-check-circle"></i> Complete Game Script</li>
                        <li><i class="fas fa-check-circle"></i> Android APK (Signed)</li>
                        <li><i class="fas fa-check-circle"></i> Responsive Website</li>
                        <li><i class="fas fa-check-circle"></i> phpMyAdmin Access</li>
                    </ul>
                    
                    <button class="btn btn-primary" style="width: 100%;" onclick="selectPackage('complete')">
                        Select Complete
                    </button>
                </div>
                
                <div class="package-card">
                    <div class="package-icon">
                        <i class="fas fa-rocket"></i>
                    </div>
                    <h3 class="package-title">Enterprise</h3>
                    <div class="package-price">₹25,000 <span>/one-time</span></div>
                    
                    <ul class="features-list">
                        <li><i class="fas fa-check-circle"></i> 2 Years Enterprise Hosting</li>
                        <li><i class="fas fa-check-circle"></i> 2 Years Domain + SSL</li>
                        <li><i class="fas fa-check-circle"></i> Custom Admin Panel</li>
                        <li><i class="fas fa-check-circle"></i> Multi-User Management</li>
                        <li><i class="fas fa-check-circle"></i> Custom Game Script</li>
                        <li><i class="fas fa-check-circle"></i> Android + iOS Apps</li>
                        <li><i class="fas fa-check-circle"></i> Premium Website Design</li>
                        <li><i class="fas fa-check-circle"></i> Priority Support</li>
                    </ul>
                    
                    <button class="btn btn-secondary" style="width: 100%;" onclick="selectPackage('enterprise')">
                        Select Enterprise
                    </button>
                </div>
            </div>
        </section>
        
        <!-- Payment Gateway -->
        <section class="payment-gateway" id="paymentSection">
            <div class="payment-header">
                <h2 class="payment-title">Secure Payment Gateway</h2>
                <div class="timer-container">
                    <div class="timer-label">OFFER EXPIRES IN</div>
                    <div class="timer" id="countdownTimer">05:00</div>
                </div>
            </div>
            
            <div class="payment-steps">
                <div class="step active">
                    <div class="step-number">1</div>
                    <div class="step-line"></div>
                    <div class="step-label">Select Package</div>
                </div>
                <div class="step">
                    <div class="step-number">2</div>
                    <div class="step-line"></div>
                    <div class="step-label">Make Payment</div>
                </div>
                <div class="step">
                    <div class="step-number">3</div>
                    <div class="step-line"></div>
                    <div class="step-label">Start Development</div>
                </div>
                <div class="step">
                    <div class="step-number">4</div>
                    <div class="step-label">Get Delivery</div>
                </div>
            </div>
            
            <div class="payment-grid">
                <div class="payment-info">
                    <h3 style="font-size: 24px; margin-bottom: 20px; color: var(--primary);">
                        <i class="fas fa-shopping-cart"></i> Order Summary
                    </h3>
                    
                    <div class="order-summary">
                        <div class="summary-item">
                            <div class="summary-label">Selected Package</div>
                            <div class="summary-value" id="selectedPackage">Complete Game Package</div>
                        </div>
                        <div class="summary-item">
                            <div class="summary-label">Package Price</div>
                            <div class="summary-value">₹10,000.00</div>
                        </div>
                        <div class="summary-item">
                            <div class="summary-label">Setup Charges</div>
                            <div class="summary-value">₹0.00 (Included)</div>
                        </div>
                        <div class="summary-item">
                            <div class="summary-label">Advance Payment (40%)</div>
                            <div class="summary-value total" id="advanceAmount">₹4,000.00</div>
                        </div>
                    </div>
                    
                    <div style="margin: 30px 0; padding: 20px; background: rgba(0, 0, 0, 0.2); border-radius: 15px;">
                        <h4 style="margin-bottom: 15px; color: var(--accent);">
                            <i class="fas fa-credit-card"></i> Payment Schedule
                        </h4>
                        <div style="display: grid; grid-template-columns: repeat(3, 1fr); gap: 15px;">
                            <div style="text-align: center;">
                                <div style="font-size: 14px; color: var(--gray);">Step 1</div>
                                <div style="font-size: 18px; font-weight: 600; color: var(--secondary);">₹4,000</div>
                                <div style="font-size: 12px; color: var(--gray);">Advance Payment</div>
                            </div>
                            <div style="text-align: center;">
                                <div style="font-size: 14px; color: var(--gray);">Step 2</div>
                                <div style="font-size: 18px; font-weight: 600; color: var(--accent);">₹3,000</div>
                                <div style="font-size: 12px; color: var(--gray);">After Game Live</div>
                            </div>
                            <div style="text-align: center;">
                                <div style="font-size: 14px; color: var(--gray);">Step 3</div>
                                <div style="font-size: 18px; font-weight: 600; color: var(--primary);">₹3,000</div>
                                <div style="font-size: 12px; color: var(--gray);">On Delivery</div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="upi-container">
                        <div style="font-size: 16px; color: var(--gray); margin-bottom: 10px;">
                            <i class="fas fa-qrcode"></i> Send Advance Payment To
                        </div>
                        <div class="upi-id" id="displayUpiId">8092043236@ybl</div>
                        
                        <div class="action-buttons">
                            <button class="btn btn-primary" onclick="copyUpiId()">
                                <i class="fas fa-copy"></i> Copy UPI ID
                            </button>
                            <button class="btn btn-secondary" onclick="openAllUpiApps()">
                                <i class="fas fa-external-link-alt"></i> Open UPI App
                            </button>
                        </div>
                    </div>
                </div>
                
                <div class="qr-section">
                    <h3 style="font-size: 24px; margin-bottom: 20px; color: var(--primary);">
                        <i class="fas fa-qrcode"></i> Scan QR Code
                    </h3>
                    
                    <div class="qr-code" id="qrCode">
                        <!-- QR Code will be generated here -->
                        <canvas id="qrCanvas"></canvas>
                    </div>
                    
                    <div class="qr-instruction">
                        <p>Scan this QR code with any UPI app to make payment</p>
                        <p style="margin-top: 10px; font-size: 12px;">
                            After payment, share transaction ID on Telegram for instant confirmation
                        </p>
                    </div>
                    
                    <div style="margin-top: 30px;">
                        <h4 style="margin-bottom: 15px; color: var(--accent);">
                            <i class="fas fa-shield-alt"></i> Secure & Fast
                        </h4>
                        <div style="display: flex; flex-wrap: wrap; gap: 10px; justify-content: center;">
                            <div style="padding: 8px 15px; background: rgba(16, 185, 129, 0.1); border-radius: 8px; font-size: 12px;">
                                <i class="fas fa-lock"></i> 256-bit SSL
                            </div>
                            <div style="padding: 8px 15px; background: rgba(99, 102, 241, 0.1); border-radius: 8px; font-size: 12px;">
                                <i class="fas fa-bolt"></i> Instant Processing
                            </div>
                            <div style="padding: 8px 15px; background: rgba(239, 68, 68, 0.1); border-radius: 8px; font-size: 12px;">
                                <i class="fas fa-history"></i> 24h Delivery
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Additional Features -->
        <section class="upcoming-features">
            <h2 class="section-title">Advanced Features Included</h2>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-chart-line"></i>
                    </div>
                    <h4 class="feature-title">Analytics Dashboard</h4>
                    <p class="feature-desc">
                        Track user activity, revenue, and game performance with advanced analytics and reporting.
                    </p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-robot"></i>
                    </div>
                    <h4 class="feature-title">AI-Powered Support</h4>
                    <p class="feature-desc">
                        Intelligent chatbot for instant user support and automated issue resolution.
                    </p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-mobile-alt"></i>
                    </div>
                    <h4 class="feature-title">Responsive Design</h4>
                    <p class="feature-desc">
                        Fully responsive website and admin panel that works perfectly on all devices.
                    </p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-database"></i>
                    </div>
                    <h4 class="feature-title">Database Management</h4>
                    <p class="feature-desc">
                        Full phpMyAdmin access for complete control over your database and backups.
                    </p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-shield-alt"></i>
                    </div>
                    <h4 class="feature-title">Security Features</h4>
                    <p class="feature-desc">
                        Advanced security measures including SSL, firewalls, and regular security updates.
                    </p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-sync-alt"></i>
                    </div>
                    <h4 class="feature-title">Auto Updates</h4>
                    <p class="feature-desc">
                        Automatic updates for scripts, security patches, and feature enhancements.
                    </p>
                </div>
            </div>
        </section>
        
        <!-- Footer -->
        <footer class="footer">
            <div class="footer-links">
                <a href="https://youtube.com/@devloperwithaman" target="_blank">YouTube</a>
                <a href="https://t.me/pluginxpertcode" target="_blank">Telegram</a>
                <a href="#">Privacy Policy</a>
                <a href="#">Terms of Service</a>
                <a href="#">Support</a>
            </div>
            <p>© 2024 DevWithAman. All rights reserved. | Premium Game Development Services</p>
            <p style="margin-top: 10px; font-size: 12px; color: var(--gray);">
                Delivery Time: 24 Hours | Payment: 40% Advance, 30% After Game Live, 30% On Delivery
            </p>
        </footer>
    </div>

    <script>
        // Background particles
        function createParticles() {
            const container = document.getElementById('particles');
            const particleCount = 30;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                
                const size = Math.random() * 100 + 50;
                particle.style.width = `${size}px`;
                particle.style.height = `${size}px`;
                particle.style.left = `${Math.random() * 100}%`;
                particle.style.top = `${Math.random() * 100}%`;
                particle.style.animationDuration = `${Math.random() * 30 + 20}s`;
                particle.style.animationDelay = `${Math.random() * 5}s`;
                
                container.appendChild(particle);
            }
        }
        
        // Countdown timer
        let countdownMinutes = 5;
        let countdownSeconds = 0;
        let countdownInterval;
        
        function startCountdown() {
            const timerElement = document.getElementById('countdownTimer');
            
            countdownInterval = setInterval(() => {
                if (countdownSeconds === 0) {
                    if (countdownMinutes === 0) {
                        clearInterval(countdownInterval);
                        timerElement.style.color = 'var(--danger)';
                        showTimeUpModal();
                        return;
                    }
                    countdownMinutes--;
                    countdownSeconds = 59;
                } else {
                    countdownSeconds--;
                }
                
                // Update color when less than 1 minute
                if (countdownMinutes === 0 && countdownSeconds < 60) {
                    timerElement.style.color = 'var(--danger)';
                }
                
                const mins = countdownMinutes.toString().padStart(2, '0');
                const secs = countdownSeconds.toString().padStart(2, '0');
                timerElement.textContent = `${mins}:${secs}`;
            }, 1000);
        }
        
        // Package selection
        function selectPackage(type) {
            const packages = {
                'basic': {
                    name: 'Basic Setup Package',
                    price: 5000,
                    advance: 2000
                },
                'complete': {
                    name: 'Complete Game Package',
                    price: 10000,
                    advance: 4000
                },
                'enterprise': {
                    name: 'Enterprise Package',
                    price: 25000,
                    advance: 10000
                }
            };
            
            const selected = packages[type];
            document.getElementById('selectedPackage').textContent = selected.name;
            document.getElementById('advanceAmount').textContent = `₹${selected.advance.toLocaleString()}.00`;
            
            // Update QR code data
            updateQRCode(selected.advance, selected.name);
            
            // Scroll to payment section
            scrollToPayment();
        }
        
        // Generate QR Code
        function generateQRCode() {
            const canvas = document.getElementById('qrCanvas');
            const ctx = canvas.getContext('2d');
            
            // Set canvas size
            canvas.width = 220;
            canvas.height = 220;
            
            // QR Code data
            const upiId = '8092043236@ybl';
            const amount = 4000;
            const name = 'DevWithAman Game Development';
            const note = 'Advance payment for Complete Game Package';
            
            // Create UPI URL
            const upiUrl = `upi://pay?pa=${upiId}&pn=${encodeURIComponent(name)}&am=${amount}&cu=INR&tn=${encodeURIComponent(note)}`;
            
            // Simple QR code generation (in production, use a proper library)
            drawSimpleQR(ctx, upiUrl);
        }
        
        function drawSimpleQR(ctx, text) {
            // This is a simplified QR-like pattern for demo
            // In production, use a QR code library like qrcode.js
            ctx.fillStyle = '#ffffff';
            ctx.fillRect(0, 0, 220, 220);
            
            // Draw border
            ctx.strokeStyle = '#000000';
            ctx.lineWidth = 2;
            ctx.strokeRect(10, 10, 200, 200);
            
            // Draw patterns
            ctx.fillStyle = '#000000';
            
            // Position markers
            ctx.fillRect(20, 20, 40, 40);
            ctx.fillRect(20, 160, 40, 40);
            ctx.fillRect(160, 20, 40, 40);
            
            // Text
            ctx.font = '14px Arial';
            ctx.fillStyle = '#333333';
            ctx.textAlign = 'center';
            ctx.fillText('Scan to Pay ₹4,000', 110, 190);
            ctx.font = '10px Arial';
            ctx.fillText('8092043236@ybl', 110, 210);
        }
        
        function updateQRCode(amount, packageName) {
            // In a real implementation, regenerate QR with new amount
            const canvas = document.getElementById('qrCanvas');
            const ctx = canvas.getContext('2d');
            
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            
            // Redraw with new amount
            const upiId = '8092043236@ybl';
            const name = 'DevWithAman Game Development';
            const note = `Advance payment for ${packageName}`;
            
            drawSimpleQR(ctx, `upi://pay?pa=${upiId}&pn=${encodeURIComponent(name)}&am=${amount}&cu=INR&tn=${encodeURIComponent(note)}`);
            
            // Update amount text
            const qrText = canvas.parentElement.querySelector('p');
            if (qrText) {
                qrText.textContent = `Scan to Pay ₹${amount.toLocaleString()}`;
            }
        }
        
        // Copy UPI ID
        function copyUpiId() {
            const upiId = '8092043236@ybl';
            navigator.clipboard.writeText(upiId).then(() => {
                showNotification('UPI ID copied to clipboard!', 'success');
            }).catch(err => {
                // Fallback
                const textArea = document.createElement('textarea');
                textArea.value = upiId;
                document.body.appendChild(textArea);
                textArea.select();
                document.execCommand('copy');
                document.body.removeChild(textArea);
                showNotification('UPI ID copied to clipboard!', 'success');
            });
        }
        
        // Open UPI Apps
        function openAllUpiApps() {
            const upiId = '8092043236@ybl';
            const amount = document.getElementById('advanceAmount').textContent.replace(/[^0-9]/g, '');
            const packageName = document.getElementById('selectedPackage').textContent;
            
            // Create UPI URL
            const upiUrl = `upi://pay?pa=${upiId}&pn=DevWithAman%20Game%20Development&am=${amount}&cu=INR&tn=Advance%20Payment%20for%20${encodeURIComponent(packageName)}`;
            
            // Try to open UPI app
            window.location.href = upiUrl;
            
            // Fallback
            setTimeout(() => {
                if (!document.hidden) {
                    showNotification('Please select a UPI app manually or scan QR code', 'info');
                }
            }, 1000);
        }
        
        // Scroll to payment
        function scrollToPayment() {
            document.getElementById('paymentSection').scrollIntoView({
                behavior: 'smooth'
            });
        }
        
        // Show notification
        function showNotification(message, type) {
            // Create notification element
            const notification = document.createElement('div');
            notification.style.cssText = `
                position: fixed;
                top: 20px;
                right: 20px;
                padding: 15px 25px;
                background: ${type === 'success' ? 'var(--success)' : 'var(--primary)'};
                color: white;
                border-radius: 10px;
                z-index: 1000;
                animation: slideIn 0.3s ease;
                box-shadow: 0 5px 15px rgba(0,0,0,0.3);
            `;
            
            notification.innerHTML = `
                <i class="fas fa-${type === 'success' ? 'check-circle' : 'info-circle'}"></i>
                ${message}
            `;
            
            document.body.appendChild(notification);
            
            // Remove after 3 seconds
            setTimeout(() => {
                notification.style.animation = 'slideOut 0.3s ease';
                setTimeout(() => {
                    document.body.removeChild(notification);
                }, 300);
            }, 3000);
        }
        
        // Show time up modal
        function showTimeUpModal() {
            const modal = document.createElement('div');
            modal.style.cssText = `
                position: fixed;
                top: 0;
                left: 0;
                width: 100%;
                height: 100%;
                background: rgba(0, 0, 0, 0.9);
                display: flex;
                justify-content: center;
                align-items: center;
                z-index: 10000;
                animation: fadeIn 0.3s ease;
            `;
            
            modal.innerHTML = `
                <div style="background: linear-gradient(135deg, var(--darker), var(--dark)); 
                           padding: 40px; 
                           border-radius: 20px; 
                           text-align: center;
                           border: 2px solid var(--danger);
                           max-width: 500px;
                           width: 90%;">
                    <div style="font-size: 60px; color: var(--danger); margin-bottom: 20px;">
                        <i class="fas fa-clock"></i>
                    </div>
                    <h2 style="color: white; margin-bottom: 20px;">Time's Up!</h2>
                    <p style="color: var(--gray); margin-bottom: 30px;">
                        The special offer has expired. Contact us on Telegram for current pricing.
                    </p>
                    <div style="display: flex; gap: 15px; justify-content: center;">
                        <button onclick="window.open('https://t.me/pluginxpertcode', '_blank')" 
                                style="padding: 12px 30px; background: var(--primary); color: white; border: none; border-radius: 10px; cursor: pointer;">
                            <i class="fab fa-telegram"></i> Contact on Telegram
                        </button>
                        <button onclick="this.closest('div').style.display = 'none'" 
                                style="padding: 12px 30px; background: transparent; color: var(--gray); border: 1px solid var(--gray); border-radius: 10px; cursor: pointer;">
                            Close
                        </button>
                    </div>
                </div>
            `;
            
            document.body.appendChild(modal);
        }
        
        // Initialize
        document.addEventListener('DOMContentLoaded', () => {
            createParticles();
            startCountdown();
            generateQRCode();
            
            // Add CSS for animations
            const style = document.createElement('style');
            style.textContent = `
                @keyframes slideIn {
                    from { transform: translateX(100%); opacity: 0; }
                    to { transform: translateX(0); opacity: 1; }
                }
                @keyframes slideOut {
                    from { transform: translateX(0); opacity: 1; }
                    to { transform: translateX(100%); opacity: 0; }
                }
                @keyframes fadeIn {
                    from { opacity: 0; }
                    to { opacity: 1; }
                }
            `;
            document.head.appendChild(style);
        });
    </script>
</body>
</html>
