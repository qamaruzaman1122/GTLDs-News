<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GTLDs News - Trusted Global News Source</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* CSS Reset and Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-color: #BB1919;
            --secondary-color: #121212;
            --accent-color: #FFD300;
            --light-color: #F6F6F6;
            --dark-color: #121212;
            --text-color: #121212;
            --text-light: #4A4A4A;
            --white: #FFFFFF;
            --gray-light: #E5E5E5;
            --shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }

        body {
            font-family: 'Helvetica Neue', Arial, sans-serif;
            line-height: 1.5;
            color: var(--text-color);
            background-color: var(--white);
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        ul {
            list-style: none;
        }

        img {
            max-width: 100%;
            height: auto;
        }

        .container {
            width: 100%;
            max-width: 1280px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .btn {
            display: inline-block;
            padding: 10px 20px;
            background-color: var(--primary-color);
            color: var(--white);
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: var(--transition);
            font-weight: 600;
            font-size: 14px;
        }

        .btn:hover {
            background-color: #A01515;
        }

        .section-title {
            font-size: 1.5rem;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid var(--primary-color);
            display: inline-block;
            font-weight: 700;
        }

        /* Header Styles */
        header {
            background-color: var(--white);
            border-bottom: 1px solid var(--gray-light);
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }

        .logo {
            font-size: 2rem;
            font-weight: 700;
            color: var(--primary-color);
            display: flex;
            align-items: center;
        }

        .logo span {
            color: var(--secondary-color);
        }

        .logo-icon {
            margin-right: 10px;
            font-size: 1.8rem;
        }

        .header-actions {
            display: flex;
            align-items: center;
        }

        .search-bar {
            display: flex;
            margin-right: 20px;
        }

        .search-bar input {
            padding: 8px 15px;
            border: 1px solid var(--gray-light);
            border-radius: 4px 0 0 4px;
            outline: none;
            width: 200px;
            font-size: 14px;
        }

        .search-bar button {
            background-color: var(--primary-color);
            color: var(--white);
            border: none;
            padding: 8px 15px;
            border-radius: 0 4px 4px 0;
            cursor: pointer;
        }

        .hamburger {
            display: none;
            cursor: pointer;
            font-size: 1.5rem;
            color: var(--primary-color);
        }

        /* Main Navigation */
        .main-nav {
            background-color: var(--secondary-color);
            padding: 0;
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
        }

        .nav-menu {
            display: flex;
        }

        .nav-menu li {
            position: relative;
        }

        .nav-menu a {
            display: block;
            padding: 15px 20px;
            color: var(--white);
            font-weight: 500;
            transition: var(--transition);
            font-size: 15px;
        }

        .nav-menu a:hover {
            background-color: rgba(255, 255, 255, 0.1);
        }

        .nav-menu a.active {
            background-color: var(--primary-color);
        }

        /* Sidebar Navigation */
        .sidebar-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 2000;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
        }

        .sidebar-overlay.active {
            opacity: 1;
            visibility: visible;
        }

        .sidebar {
            position: fixed;
            top: 0;
            right: -350px;
            width: 320px;
            height: 100%;
            background-color: var(--white);
            z-index: 2001;
            transition: var(--transition);
            overflow-y: auto;
            box-shadow: -2px 0 10px rgba(0, 0, 0, 0.1);
        }

        .sidebar.active {
            right: 0;
        }

        .sidebar-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
            border-bottom: 1px solid var(--gray-light);
            background-color: var(--primary-color);
            color: var(--white);
        }

        .sidebar-close {
            background: none;
            border: none;
            color: var(--white);
            font-size: 1.5rem;
            cursor: pointer;
        }

        .sidebar-content {
            padding: 20px;
        }

        .sidebar-menu {
            margin-bottom: 30px;
        }

        .sidebar-menu h3 {
            font-size: 1.2rem;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 1px solid var(--gray-light);
            color: var(--primary-color);
        }

        .sidebar-menu ul li {
            margin-bottom: 10px;
        }

        .sidebar-menu ul li a {
            display: block;
            padding: 10px 0;
            color: var(--text-color);
            transition: var(--transition);
            border-bottom: 1px solid var(--gray-light);
        }

        .sidebar-menu ul li a:hover {
            color: var(--primary-color);
            padding-left: 5px;
        }

        /* Breaking News Ticker */
        .breaking-news {
            background-color: var(--primary-color);
            color: var(--white);
            padding: 10px 0;
            overflow: hidden;
        }

        .breaking-news-container {
            display: flex;
            align-items: center;
        }

        .breaking-label {
            background-color: var(--secondary-color);
            padding: 5px 15px;
            font-weight: bold;
            margin-right: 20px;
            white-space: nowrap;
            font-size: 14px;
        }

        .ticker {
            overflow: hidden;
            position: relative;
            flex-grow: 1;
        }

        .ticker-content {
            display: inline-block;
            white-space: nowrap;
            animation: ticker 30s linear infinite;
            font-size: 14px;
        }

        @keyframes ticker {
            0% { transform: translateX(100%); }
            100% { transform: translateX(-100%); }
        }

        /* Featured News Slider */
        .featured-slider {
            position: relative;
            height: 500px;
            overflow: hidden;
            margin-bottom: 40px;
            border-radius: 4px;
            box-shadow: var(--shadow);
        }

        .slide {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            opacity: 0;
            transition: opacity 0.8s ease;
            background-size: cover;
            background-position: center;
            display: flex;
            align-items: flex-end;
            padding: 40px;
        }

        .slide.active {
            opacity: 1;
        }

        .slide-content {
            background: rgba(0, 0, 0, 0.7);
            color: var(--white);
            padding: 20px;
            border-radius: 4px;
            max-width: 600px;
        }

        .slide-content .category {
            display: inline-block;
            background-color: var(--primary-color);
            color: var(--white);
            padding: 5px 10px;
            border-radius: 4px;
            font-size: 0.8rem;
            margin-bottom: 10px;
            font-weight: 600;
        }

        .slide-content h2 {
            font-size: 1.8rem;
            margin-bottom: 10px;
            line-height: 1.3;
        }

        .slide-content p {
            margin-bottom: 15px;
            opacity: 0.9;
            font-size: 1rem;
        }

        .slider-nav {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
        }

        .slider-dot {
            width: 12px;
            height: 12px;
            background-color: rgba(255, 255, 255, 0.5);
            border-radius: 50%;
            margin: 0 5px;
            cursor: pointer;
            transition: var(--transition);
        }

        .slider-dot.active {
            background-color: var(--white);
        }

        .slider-arrow {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background-color: rgba(0, 0, 0, 0.5);
            color: var(--white);
            width: 50px;
            height: 50px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            cursor: pointer;
            transition: var(--transition);
            font-size: 1.2rem;
        }

        .slider-arrow:hover {
            background-color: rgba(0, 0, 0, 0.8);
        }

        .slider-arrow.prev {
            left: 20px;
        }

        .slider-arrow.next {
            right: 20px;
        }

        /* Live Update Indicator */
        .live-indicator {
            display: inline-flex;
            align-items: center;
            background-color: var(--primary-color);
            color: var(--white);
            padding: 4px 10px;
            border-radius: 4px;
            font-size: 0.8rem;
            margin-left: 10px;
            font-weight: 600;
        }

        .live-indicator::before {
            content: '';
            width: 8px;
            height: 8px;
            background-color: var(--white);
            border-radius: 50%;
            margin-right: 5px;
            animation: pulse 1.5s infinite;
        }

        @keyframes pulse {
            0% { opacity: 1; }
            50% { opacity: 0.5; }
            100% { opacity: 1; }
        }

        /* Categories Section */
        .categories {
            padding: 40px 0;
            background-color: var(--light-color);
        }

        .category-filters {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            margin-bottom: 30px;
        }

        .category-filter {
            padding: 8px 20px;
            margin: 5px;
            background-color: var(--white);
            border-radius: 30px;
            cursor: pointer;
            transition: var(--transition);
            font-weight: 500;
            box-shadow: var(--shadow);
            font-size: 14px;
            border: 1px solid var(--gray-light);
        }

        .category-filter.active, .category-filter:hover {
            background-color: var(--primary-color);
            color: var(--white);
            border-color: var(--primary-color);
        }

        /* News Grid */
        .news-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }

        .news-card {
            background-color: var(--white);
            border-radius: 4px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            border: 1px solid var(--gray-light);
        }

        .news-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
        }

        .card-image {
            height: 200px;
            overflow: hidden;
            position: relative;
        }

        .card-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .news-card:hover .card-image img {
            transform: scale(1.05);
        }

        .card-content {
            padding: 20px;
        }

        .card-category {
            display: inline-block;
            background-color: var(--primary-color);
            color: var(--white);
            padding: 4px 10px;
            border-radius: 4px;
            font-size: 0.8rem;
            margin-bottom: 10px;
            font-weight: 600;
        }

        .card-title {
            font-size: 1.2rem;
            margin-bottom: 10px;
            line-height: 1.4;
            font-weight: 600;
        }

        .card-excerpt {
            color: var(--text-light);
            margin-bottom: 15px;
            font-size: 0.95rem;
            line-height: 1.5;
        }

        .card-meta {
            display: flex;
            justify-content: space-between;
            font-size: 0.85rem;
            color: var(--text-light);
            border-top: 1px solid #eee;
            padding-top: 15px;
        }

        /* About Us Section */
        .about-section {
            padding: 80px 0;
            background-color: var(--white);
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }

        .about-text h2 {
            font-size: 2.2rem;
            margin-bottom: 20px;
            color: var(--secondary-color);
        }

        .about-text p {
            margin-bottom: 20px;
            font-size: 1.1rem;
            line-height: 1.7;
            color: var(--text-light);
        }

        .about-stats {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            margin-top: 30px;
        }

        .stat {
            text-align: center;
            padding: 20px;
            background-color: var(--light-color);
            border-radius: 8px;
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--primary-color);
            display: block;
        }

        .stat-label {
            font-size: 1rem;
            color: var(--text-light);
        }

        .about-image {
            border-radius: 8px;
            overflow: hidden;
            box-shadow: var(--shadow);
        }

        /* Contact Section */
        .contact-section {
            padding: 80px 0;
            background-color: var(--light-color);
        }

        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
        }

        .contact-info h2 {
            font-size: 2.2rem;
            margin-bottom: 20px;
            color: var(--secondary-color);
        }

        .contact-info p {
            margin-bottom: 30px;
            font-size: 1.1rem;
            line-height: 1.7;
            color: var(--text-light);
        }

        .contact-details {
            margin-bottom: 30px;
        }

        .contact-item {
            display: flex;
            align-items: flex-start;
            margin-bottom: 20px;
        }

        .contact-icon {
            background-color: var(--primary-color);
            color: var(--white);
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 15px;
            flex-shrink: 0;
        }

        .contact-text h3 {
            font-size: 1.2rem;
            margin-bottom: 5px;
        }

        .contact-form {
            background-color: var(--white);
            padding: 30px;
            border-radius: 8px;
            box-shadow: var(--shadow);
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
        }

        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
            transition: var(--transition);
        }

        .form-control:focus {
            border-color: var(--primary-color);
            outline: none;
            box-shadow: 0 0 0 2px rgba(187, 25, 25, 0.2);
        }

        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }

        /* Loading Spinner */
        .loading {
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 40px;
        }

        .spinner {
            width: 40px;
            height: 40px;
            border: 4px solid rgba(0, 0, 0, 0.1);
            border-left-color: var(--primary-color);
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        /* Article Modal */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 2000;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
        }

        .modal-overlay.active {
            opacity: 1;
            visibility: visible;
        }

        .modal {
            background-color: var(--white);
            width: 90%;
            max-width: 800px;
            max-height: 90vh;
            border-radius: 8px;
            overflow-y: auto;
            position: relative;
            transform: translateY(20px);
            transition: var(--transition);
        }

        .modal-overlay.active .modal {
            transform: translateY(0);
        }

        .modal-close {
            position: absolute;
            top: 15px;
            right: 15px;
            background-color: rgba(0, 0, 0, 0.5);
            color: var(--white);
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            z-index: 10;
            transition: var(--transition);
        }

        .modal-close:hover {
            background-color: rgba(0, 0, 0, 0.8);
        }

        .modal-image {
            height: 300px;
            overflow: hidden;
        }

        .modal-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .modal-content {
            padding: 30px;
        }

        .modal-category {
            display: inline-block;
            background-color: var(--primary-color);
            color: var(--white);
            padding: 5px 10px;
            border-radius: 4px;
            font-size: 0.8rem;
            margin-bottom: 15px;
            font-weight: 600;
        }

        .modal-title {
            font-size: 1.8rem;
            margin-bottom: 15px;
            line-height: 1.4;
            font-weight: 700;
        }

        .modal-meta {
            display: flex;
            margin-bottom: 20px;
            color: var(--text-light);
            font-size: 0.9rem;
        }

        .modal-meta span {
            margin-right: 20px;
        }

        .modal-meta i {
            margin-right: 5px;
        }

        .modal-body {
            line-height: 1.7;
        }

        .modal-body p {
            margin-bottom: 15px;
        }

        /* Footer */
        footer {
            background-color: var(--secondary-color);
            color: var(--white);
            padding: 50px 0 20px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-column h3 {
            font-size: 1.3rem;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }

        .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 50px;
            height: 2px;
            background-color: var(--primary-color);
        }

        .footer-about p {
            margin-bottom: 20px;
            opacity: 0.8;
        }

        .footer-links li {
            margin-bottom: 10px;
        }

        .footer-links a {
            opacity: 0.8;
            transition: var(--transition);
        }

        .footer-links a:hover {
            opacity: 1;
            color: var(--primary-color);
            padding-left: 5px;
        }

        .footer-contact li {
            margin-bottom: 15px;
            display: flex;
            align-items: flex-start;
        }

        .footer-contact i {
            margin-right: 10px;
            color: var(--primary-color);
        }

        .social-links {
            display: flex;
            margin-top: 20px;
        }

        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            margin-right: 10px;
            transition: var(--transition);
        }

        .social-links a:hover {
            background-color: var(--primary-color);
            transform: translateY(-3px);
        }

        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.9rem;
            opacity: 0.7;
        }

        /* Responsive Styles */
        @media (max-width: 992px) {
            .featured-slider {
                height: 400px;
            }
            
            .slide-content h2 {
                font-size: 1.5rem;
            }
            
            .about-content,
            .contact-content {
                grid-template-columns: 1fr;
                gap: 40px;
            }
            
            .about-image {
                order: -1;
            }
        }

        @media (max-width: 768px) {
            .nav-menu {
                display: none;
            }
            
            .hamburger {
                display: block;
            }
            
            .search-bar {
                display: none;
            }
            
            .mobile-search {
                margin-top: 20px;
            }
            
            .mobile-search input {
                width: 100%;
            }
            
            .featured-slider {
                height: 350px;
            }
            
            .slide {
                padding: 20px;
            }
            
            .slide-content h2 {
                font-size: 1.3rem;
            }
            
            .slider-arrow {
                width: 40px;
                height: 40px;
                font-size: 1rem;
            }
            
            .about-stats {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 576px) {
            .featured-slider {
                height: 300px;
            }
            
            .slide-content h2 {
                font-size: 1.1rem;
            }
            
            .section-title {
                font-size: 1.5rem;
            }
            
            .modal-title {
                font-size: 1.4rem;
            }
            
            .about-text h2,
            .contact-info h2 {
                font-size: 1.8rem;
            }
            
            .sidebar {
                width: 280px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-container">
            <a href="#" class="logo">
                <i class="fas fa-globe-americas logo-icon"></i>
                GTLDs <span>News</span>
            </a>
            
            <div class="header-actions">
                <div class="search-bar">
                    <input type="text" id="search-input" placeholder="Search news...">
                    <button id="search-btn"><i class="fas fa-search"></i></button>
                </div>
                
                <div class="hamburger" id="hamburger">
                    <i class="fas fa-bars"></i>
                </div>
            </div>
        </div>
        
        <!-- Main Navigation -->
        <nav class="main-nav">
            <div class="container nav-container">
                <ul class="nav-menu">
                    <li><a href="#" class="active">Home</a></li>
                    <li><a href="#latest-news">Latest</a></li>
                    <li><a href="#categories">Categories</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#contact">Contact</a></li>
                    <li><a href="#">World</a></li>
                    <li><a href="#">Politics</a></li>
                    <li><a href="#">Business</a></li>
                    <li><a href="#">Technology</a></li>
                    <li><a href="#">Science</a></li>
                </ul>
            </div>
        </nav>
    </header>

    <!-- Sidebar Navigation -->
    <div class="sidebar-overlay" id="sidebar-overlay"></div>
    <div class="sidebar" id="sidebar">
        <div class="sidebar-header">
            <h3>Menu</h3>
            <button class="sidebar-close" id="sidebar-close">
                <i class="fas fa-times"></i>
            </button>
        </div>
        <div class="sidebar-content">
            <div class="sidebar-menu">
                <h3>Navigation</h3>
                <ul>
                    <li><a href="#">Home</a></li>
                    <li><a href="#latest-news">Latest News</a></li>
                    <li><a href="#categories">Categories</a></li>
                    <li><a href="#about">About Us</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </div>
            
            <div class="sidebar-menu">
                <h3>Categories</h3>
                <ul>
                    <li><a href="#">World</a></li>
                    <li><a href="#">Politics</a></li>
                    <li><a href="#">Business</a></li>
                    <li><a href="#">Technology</a></li>
                    <li><a href="#">Science</a></li>
                    <li><a href="#">Health</a></li>
                    <li><a href="#">Entertainment</a></li>
                    <li><a href="#">Sports</a></li>
                </ul>
            </div>
            
            <div class="sidebar-menu">
                <h3>Account</h3>
                <ul>
                    <li><a href="#">Sign In</a></li>
                    <li><a href="#">Register</a></li>
                    <li><a href="#">Newsletter</a></li>
                    <li><a href="#">Preferences</a></li>
                </ul>
            </div>
            
            <div class="mobile-search">
                <input type="text" id="mobile-search-input" placeholder="Search news...">
                <button id="mobile-search-btn" class="btn" style="width: 100%; margin-top: 10px;">Search</button>
            </div>
        </div>
    </div>

    <!-- Breaking News Ticker -->
    <section class="breaking-news">
        <div class="container breaking-news-container">
            <div class="breaking-label">BREAKING NEWS</div>
            <div class="ticker">
                <div class="ticker-content" id="breaking-news-ticker">
                    Loading latest headlines...
                </div>
            </div>
        </div>
    </section>

    <!-- Featured News Slider -->
    <section class="featured-slider" id="featured-slider">
        <div class="loading">
            <div class="spinner"></div>
        </div>
    </section>

    <!-- Categories Section -->
    <section class="categories" id="categories">
        <div class="container">
            <h2 class="section-title">Browse by Category <span class="live-indicator">LIVE</span></h2>
            <div class="category-filters" id="category-filters">
                <!-- Category filters will be dynamically generated by JavaScript -->
            </div>
        </div>
    </section>

    <!-- Latest News Section -->
    <section class="latest-news" id="latest-news">
        <div class="container">
            <h2 class="section-title">Latest News</h2>
            <div class="news-grid" id="news-grid">
                <div class="loading">
                    <div class="spinner"></div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Us Section -->
    <section class="about-section" id="about">
        <div class="container">
            <div class="about-content">
                <div class="about-text">
                    <h2>About GTLDs News</h2>
                    <p>GTLDs News is a premier digital news platform committed to delivering accurate, timely, and comprehensive news coverage from around the globe. Founded in 2010, we've grown to become one of the most trusted sources for breaking news, in-depth analysis, and diverse perspectives.</p>
                    <p>Our mission is to inform, educate, and empower our readers with factual reporting and insightful commentary. We believe in the power of journalism to foster understanding and drive positive change in society.</p>
                    <p>With correspondents in over 50 countries and partnerships with leading news agencies worldwide, we bring you the stories that matter most, when they matter most.</p>
                    
                    <div class="about-stats">
                        <div class="stat">
                            <span class="stat-number">500K+</span>
                            <span class="stat-label">Daily Readers</span>
                        </div>
                        <div class="stat">
                            <span class="stat-number">50+</span>
                            <span class="stat-label">Countries Covered</span>
                        </div>
                        <div class="stat">
                            <span class="stat-number">24/7</span>
                            <span class="stat-label">News Coverage</span>
                        </div>
                    </div>
                </div>
                <div class="about-image">
                    <img src="https://images.unsplash.com/photo-1583324113626-70df0f4deaab?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1438&q=80" alt="GTLDs News Team">
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact-section" id="contact">
        <div class="container">
            <div class="contact-content">
                <div class="contact-info">
                    <h2>Get In Touch</h2>
                    <p>We value your feedback, questions, and story tips. Reach out to us through any of the following channels, and our team will respond as quickly as possible.</p>
                    
                    <div class="contact-details">
                        <div class="contact-item">
                            <div class="contact-icon">
                                <i class="fas fa-map-marker-alt"></i>
                            </div>
                            <div class="contact-text">
                                <h3>Our Office</h3>
                                <p>123 Media Street, News District<br>New York, NY 10001, USA</p>
                            </div>
                        </div>
                        <div class="contact-item">
                            <div class="contact-icon">
                                <i class="fas fa-phone"></i>
                            </div>
                            <div class="contact-text">
                                <h3>Phone Number</h3>
                                <p>+1 (555) 123-4567</p>
                            </div>
                        </div>
                        <div class="contact-item">
                            <div class="contact-icon">
                                <i class="fas fa-envelope"></i>
                            </div>
                            <div class="contact-text">
                                <h3>Email Address</h3>
                                <p>info@gtldsnews.com</p>
                            </div>
                        </div>
                    </div>
                    
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#"><i class="fab fa-youtube"></i></a>
                    </div>
                </div>
                
                <div class="contact-form">
                    <h3>Send Us a Message</h3>
                    <form id="contactForm">
                        <div class="form-group">
                            <label for="name">Your Name</label>
                            <input type="text" id="name" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="email">Your Email</label>
                            <input type="email" id="email" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="subject">Subject</label>
                            <input type="text" id="subject" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="message">Your Message</label>
                            <textarea id="message" class="form-control" required></textarea>
                        </div>
                        <button type="submit" class="btn">Send Message</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Article Modal -->
    <div class="modal-overlay" id="modal-overlay">
        <div class="modal" id="modal">
            <div class="modal-close" id="modal-close">
                <i class="fas fa-times"></i>
            </div>
            <div class="modal-image" id="modal-image">
                <!-- Modal image will be dynamically generated by JavaScript -->
            </div>
            <div class="modal-content">
                <span class="modal-category" id="modal-category">Category</span>
                <h2 class="modal-title" id="modal-title">Article Title</h2>
                <div class="modal-meta" id="modal-meta">
                    <!-- Meta information will be dynamically generated by JavaScript -->
                </div>
                <div class="modal-body" id="modal-body">
                    <!-- Article content will be dynamically generated by JavaScript -->
                </div>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column footer-about">
                    <h3>About GTLDs News</h3>
                    <p>GTLDs News is your trusted source for the latest news, delivering accurate and timely information across various categories including technology, sports, politics, and entertainment.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                    </div>
                </div>
                
                <div class="footer-column">
                    <h3>Quick Links</h3>
                    <ul class="footer-links">
                        <li><a href="#">Home</a></li>
                        <li><a href="#categories">Categories</a></li>
                        <li><a href="#latest-news">Latest News</a></li>
                        <li><a href="#about">About Us</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Contact Us</h3>
                    <ul class="footer-contact">
                        <li>
                            <i class="fas fa-map-marker-alt"></i>
                            <span>123 News Street, Media City, MC 12345</span>
                        </li>
                        <li>
                            <i class="fas fa-phone"></i>
                            <span>+1 (555) 123-4567</span>
                        </li>
                        <li>
                            <i class="fas fa-envelope"></i>
                            <span>info@gtldsnews.com</span>
                        </li>
                    </ul>
                </div>
            </div>
            
            <div class="copyright">
                <p>&copy; 2023 GTLDs News. All rights reserved. | Last updated: <span id="last-updated">Loading...</span></p>
            </div>
        </div>
    </footer>

    <script>
        // News API Configuration
        const NEWS_API_CONFIG = {
            // Using NewsAPI with your provided API key
            apiKey: 'ea180fe5856d46f6a51e72f9146c5842',
            endpoint: 'https://newsapi.org/v2/top-headlines',
            country: 'us',
            pageSize: 20,
            
            // Fallback to Guardian API if NewsAPI fails
            guardianEndpoint: 'https://content.guardianapis.com/search',
            guardianApiKey: 'test', // The Guardian API has a public test key
        };

        // Initialize the application
        document.addEventListener('DOMContentLoaded', function() {
            // Load news from API
            loadNewsFromAPI();
            
            // Initialize search functionality
            initSearch();
            
            // Initialize mobile menu
            initMobileMenu();
            
            // Initialize sidebar
            initSidebar();
            
            // Initialize modal functionality
            initModal();
            
            // Initialize contact form
            initContactForm();
            
            // Set up auto-refresh every 5 minutes
            setInterval(loadNewsFromAPI, 5 * 60 * 1000);
            
            // Update last updated time
            updateLastUpdatedTime();
        });

        // Load News from API
        async function loadNewsFromAPI() {
            try {
                // Try NewsAPI first
                await loadNewsFromNewsAPI();
            } catch (error) {
                console.error('NewsAPI failed, trying Guardian API:', error);
                try {
                    // Fallback to Guardian API
                    await loadNewsFromGuardianAPI();
                } catch (guardianError) {
                    console.error('All APIs failed, using sample data:', guardianError);
                    // Final fallback to sample data
                    useSampleData();
                }
            }
        }

        // Load News from NewsAPI
        async function loadNewsFromNewsAPI() {
            const url = `${NEWS_API_CONFIG.endpoint}?country=${NEWS_API_CONFIG.country}&pageSize=${NEWS_API_CONFIG.pageSize}&apiKey=${NEWS_API_CONFIG.apiKey}`;
            
            const response = await fetch(url);
            if (!response.ok) {
                throw new Error(`NewsAPI error: ${response.status}`);
            }
            
            const data = await response.json();
            
            if (data.articles && data.articles.length > 0) {
                processNewsData(data.articles, 'newsapi');
            } else {
                throw new Error('No articles found');
            }
        }

        // Load News from Guardian API
        async function loadNewsFromGuardianAPI() {
            const url = `${NEWS_API_CONFIG.guardianEndpoint}?show-fields=thumbnail,trailText&page-size=${NEWS_API_CONFIG.pageSize}&api-key=${NEWS_API_CONFIG.guardianApiKey}`;
            
            const response = await fetch(url);
            if (!response.ok) {
                throw new Error(`Guardian API error: ${response.status}`);
            }
            
            const data = await response.json();
            
            if (data.response && data.response.results && data.response.results.length > 0) {
                processNewsData(data.response.results, 'guardian');
            } else {
                throw new Error('No articles found');
            }
        }

        // Process news data from different APIs
        function processNewsData(articles, source) {
            let processedNews = [];
            
            if (source === 'newsapi') {
                processedNews = articles.map((article, index) => {
                    // Extract category from source name or use general
                    const category = article.source ? article.source.name : 'General';
                    const shortCategory = getShortCategory(category);
                    
                    return {
                        id: index + 1,
                        title: article.title || 'No title available',
                        description: article.description || 'No description available',
                        content: article.content || 'Content not available. Please visit the source website for full article.',
                        image: article.urlToImage || getFallbackImage(shortCategory),
                        category: shortCategory,
                        author: article.author || 'Unknown Author',
                        date: article.publishedAt ? new Date(article.publishedAt).toISOString().split('T')[0] : getCurrentDate(),
                        source: 'NewsAPI',
                        url: article.url
                    };
                });
            } else if (source === 'guardian') {
                processedNews = articles.map((article, index) => {
                    const fields = article.fields || {};
                    const category = article.sectionName || 'General';
                    const shortCategory = getShortCategory(category);
                    
                    return {
                        id: index + 1,
                        title: article.webTitle || 'No title available',
                        description: fields.trailText || 'No description available',
                        content: 'Content not available. Please visit the Guardian website for full article.',
                        image: fields.thumbnail || getFallbackImage(shortCategory),
                        category: shortCategory,
                        author: 'The Guardian',
                        date: article.webPublicationDate ? new Date(article.webPublicationDate).toISOString().split('T')[0] : getCurrentDate(),
                        source: 'Guardian',
                        url: article.webUrl
                    };
                });
            }
            
            // Update the UI with the processed news
            updateNewsUI(processedNews);
        }

        // Use sample data as final fallback
        function useSampleData() {
            const sampleNews = [
                {
                    id: 1,
                    title: "Global Climate Summit Reaches Historic Agreement",
                    description: "World leaders have agreed on ambitious new targets to combat climate change at the latest international summit.",
                    content: "<p>In a landmark decision, representatives from over 190 countries have reached a comprehensive agreement to accelerate efforts against climate change. The new targets include reducing carbon emissions by 50% by 2030 and achieving net-zero by 2050.</p><p>The agreement comes after two weeks of intense negotiations, with developed nations committing $100 billion annually to help developing countries transition to renewable energy sources.</p><p>UN Secretary-General described the agreement as 'a turning point in our collective fight to preserve our planet for future generations.'</p>",
                    image: "https://images.unsplash.com/photo-1569163139394-de44cb54d521?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80",
                    category: "Politics",
                    author: "Environmental News Network",
                    date: getCurrentDate(),
                    source: "Sample Data"
                },
                {
                    id: 2,
                    title: "Tech Giant Unveils Revolutionary AI Assistant",
                    description: "The new AI system promises to transform how we interact with technology in daily life.",
                    content: "<p>Tech conglomerate InnovateCorp today unveiled 'Aura', its next-generation AI assistant that the company claims will revolutionize human-computer interaction. Unlike current voice assistants, Aura uses advanced contextual understanding to engage in more natural, flowing conversations.</p><p>'Aura represents a quantum leap in AI technology,' said Dr. Benjamin Carter, Chief Technology Officer at InnovateCorp. 'It doesn't just respond to commands; it understands context, remembers previous interactions, and can even anticipate user needs.'</p><p>The demonstration showed Aura managing complex tasks like planning a multi-day business trip, coordinating schedules between multiple people, and making restaurant reservations based on dietary preferences and past choices.</p>",
                    image: "https://images.unsplash.com/photo-1677442136019-21780ecad995?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80",
                    category: "Technology",
                    author: "Tech Insights",
                    date: getCurrentDate(),
                    source: "Sample Data"
                },
                {
                    id: 3,
                    title: "National Team Secures Championship Victory",
                    description: "In a stunning overtime finish, the national team claims the international championship title.",
                    content: "<p>In a stunning upset, the national team claimed victory in the International Championship with a last-minute goal in overtime. The final score was 3-2 after a hard-fought match that kept fans on the edge of their seats.</p><p>Captain Michael Torres scored the winning goal in the 119th minute, securing the country's first international trophy in over two decades. 'This is a dream come true for our team and our country,' Torres said in a post-match interview.</p><p>The victory parade is scheduled for tomorrow in the capital city, where thousands of fans are expected to celebrate the historic win.</p><p>Coach David Wilson praised his team's resilience: 'They never gave up, even when things looked difficult. This victory is a testament to their hard work and dedication.'</p>",
                    image: "https://images.unsplash.com/photo-1459865264687-595d652de67e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80",
                    category: "Sports",
                    author: "Sports Daily",
                    date: getCurrentDate(),
                    source: "Sample Data"
                },
                {
                    id: 4,
                    title: "Award-Winning Film Director Announces New Project",
                    description: "After recent festival success, the acclaimed director reveals plans for next cinematic venture.",
                    content: "<p>Acclaimed director Elena Martinez, fresh from her historic win at the International Film Festival, has announced her next project: an adaptation of the bestselling novel 'Echoes of Time'.</p><p>The film will explore themes of memory, identity, and intergenerational trauma through the story of three generations of women in a single family. Martinez described the project as 'deeply personal' and 'the most challenging work of my career.'</p><p>Production is scheduled to begin in the fall, with casting announcements expected in the coming weeks. The director confirmed that several A-list actors have expressed interest in the lead roles.</p><p>'Echoes of Time' is expected to premiere at next year's film festival circuit, with a wide theatrical release planned for the following season.</p>",
                    image: "https://images.unsplash.com/photo-1489599809505-f2d4cac55b73?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80",
                    category: "Entertainment",
                    author: "Cinema Today",
                    date: getCurrentDate(),
                    source: "Sample Data"
                }
            ];
            
            updateNewsUI(sampleNews);
        }

        // Update the UI with news data
        function updateNewsUI(newsData) {
            // Update breaking news ticker
            updateBreakingNewsTicker(newsData);
            
            // Initialize featured slider
            initFeaturedSlider(newsData);
            
            // Initialize category filters
            initCategoryFilters(newsData);
            
            // Render news grid
            renderNewsGrid(newsData);
            
            // Update last updated time
            updateLastUpdatedTime();
        }

        // Update breaking news ticker
        function updateBreakingNewsTicker(newsData) {
            const ticker = document.getElementById('breaking-news-ticker');
            const headlines = newsData.slice(0, 5).map(article => article.title);
            
            ticker.textContent = headlines.join(' • ');
        }

        // Featured Slider Functions
        function initFeaturedSlider(newsData) {
            const slider = document.getElementById('featured-slider');
            const featuredArticles = newsData.slice(0, 3); // Get first 3 articles for featured slider
            
            let slidesHTML = '';
            let dotsHTML = '';
            
            featuredArticles.forEach((article, index) => {
                const activeClass = index === 0 ? 'active' : '';
                
                slidesHTML += `
                    <div class="slide ${activeClass}" style="background-image: url('${article.image}')">
                        <div class="slide-content">
                            <span class="category">${article.category}</span>
                            <h2>${article.title}</h2>
                            <p>${article.description}</p>
                            <button class="btn read-more-btn" data-id="${article.id}">Read More</button>
                        </div>
                    </div>
                `;
                
                dotsHTML += `<div class="slider-dot ${activeClass}" data-index="${index}"></div>`;
            });
            
            slider.innerHTML = `
                ${slidesHTML}
                <div class="slider-arrow prev"><i class="fas fa-chevron-left"></i></div>
                <div class="slider-arrow next"><i class="fas fa-chevron-right"></i></div>
                <div class="slider-nav">
                    ${dotsHTML}
                </div>
            `;
            
            // Add event listeners for slider navigation
            const slides = document.querySelectorAll('.slide');
            const dots = document.querySelectorAll('.slider-dot');
            const prevArrow = document.querySelector('.slider-arrow.prev');
            const nextArrow = document.querySelector('.slider-arrow.next');
            let currentSlide = 0;
            
            function showSlide(index) {
                // Remove active class from all slides and dots
                slides.forEach(slide => slide.classList.remove('active'));
                dots.forEach(dot => dot.classList.remove('active'));
                
                // Add active class to current slide and dot
                slides[index].classList.add('active');
                dots[index].classList.add('active');
                currentSlide = index;
            }
            
            function nextSlide() {
                let nextIndex = (currentSlide + 1) % slides.length;
                showSlide(nextIndex);
            }
            
            function prevSlide() {
                let prevIndex = (currentSlide - 1 + slides.length) % slides.length;
                showSlide(prevIndex);
            }
            
            // Auto-advance slides
            let slideInterval = setInterval(nextSlide, 5000);
            
            // Pause auto-advance on hover
            slider.addEventListener('mouseenter', () => clearInterval(slideInterval));
            slider.addEventListener('mouseleave', () => slideInterval = setInterval(nextSlide, 5000));
            
            // Event listeners for manual navigation
            nextArrow.addEventListener('click', nextSlide);
            prevArrow.addEventListener('click', prevSlide);
            
            dots.forEach(dot => {
                dot.addEventListener('click', function() {
                    const index = parseInt(this.getAttribute('data-index'));
                    showSlide(index);
                });
            });
            
            // Read more buttons in slider
            document.querySelectorAll('.read-more-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const articleId = parseInt(this.getAttribute('data-id'));
                    openArticleModal(articleId, newsData);
                });
            });
        }

        // Category Filters Functions
        function initCategoryFilters(newsData) {
            const categoryFilters = document.getElementById('category-filters');
            
            // Get unique categories
            const categories = [...new Set(newsData.map(article => article.category))];
            
            // Add "All" category
            categories.unshift('All');
            
            let filtersHTML = '';
            
            categories.forEach(category => {
                const activeClass = category === 'All' ? 'active' : '';
                filtersHTML += `<div class="category-filter ${activeClass}" data-category="${category}">${category}</div>`;
            });
            
            categoryFilters.innerHTML = filtersHTML;
            
            // Add event listeners to category filters
            document.querySelectorAll('.category-filter').forEach(filter => {
                filter.addEventListener('click', function() {
                    // Remove active class from all filters
                    document.querySelectorAll('.category-filter').forEach(f => f.classList.remove('active'));
                    
                    // Add active class to clicked filter
                    this.classList.add('active');
                    
                    const category = this.getAttribute('data-category');
                    
                    if (category === 'All') {
                        renderNewsGrid(newsData);
                    } else {
                        const filteredNews = newsData.filter(article => article.category === category);
                        renderNewsGrid(filteredNews);
                    }
                });
            });
        }

        // News Grid Functions
        function renderNewsGrid(articles) {
            const newsGrid = document.getElementById('news-grid');
            
            if (articles.length === 0) {
                newsGrid.innerHTML = '<p class="no-results">No articles found matching your criteria.</p>';
                return;
            }
            
            let gridHTML = '';
            
            articles.forEach(article => {
                gridHTML += `
                    <div class="news-card" data-id="${article.id}">
                        <div class="card-image">
                            <img src="${article.image}" alt="${article.title}">
                        </div>
                        <div class="card-content">
                            <span class="card-category">${article.category}</span>
                            <h3 class="card-title">${article.title}</h3>
                            <p class="card-excerpt">${article.description}</p>
                            <div class="card-meta">
                                <span><i class="far fa-user"></i> ${article.author}</span>
                                <span><i class="far fa-calendar"></i> ${formatDate(article.date)}</span>
                            </div>
                        </div>
                    </div>
                `;
            });
            
            newsGrid.innerHTML = gridHTML;
            
            // Add event listeners to news cards
            document.querySelectorAll('.news-card').forEach(card => {
                card.addEventListener('click', function() {
                    const articleId = parseInt(this.getAttribute('data-id'));
                    openArticleModal(articleId, articles);
                });
            });
        }

        // Search Functionality
        function initSearch() {
            const searchInput = document.getElementById('search-input');
            const searchBtn = document.getElementById('search-btn');
            const mobileSearchInput = document.getElementById('mobile-search-input');
            const mobileSearchBtn = document.getElementById('mobile-search-btn');
            
            function performSearch() {
                const searchTerm = searchInput.value.trim().toLowerCase() || mobileSearchInput.value.trim().toLowerCase();
                
                if (searchTerm === '') {
                    // Reload all news if search is empty
                    loadNewsFromAPI();
                    return;
                }
                
                // This would need access to the current news data
                // For a real implementation, you would filter the current news array
                alert(`Search functionality would filter for: ${searchTerm}\n\nIn a full implementation, this would filter the current news articles.`);
            }
            
            searchBtn.addEventListener('click', performSearch);
            mobileSearchBtn.addEventListener('click', performSearch);
            
            searchInput.addEventListener('keyup', function(event) {
                if (event.key === 'Enter') {
                    performSearch();
                }
            });
            
            mobileSearchInput.addEventListener('keyup', function(event) {
                if (event.key === 'Enter') {
                    performSearch();
                }
            });
        }

        // Mobile Menu Functionality
        function initMobileMenu() {
            const hamburger = document.getElementById('hamburger');
            
            hamburger.addEventListener('click', function() {
                openSidebar();
            });
        }

        // Sidebar Functionality
        function initSidebar() {
            const sidebarOverlay = document.getElementById('sidebar-overlay');
            const sidebar = document.getElementById('sidebar');
            const sidebarClose = document.getElementById('sidebar-close');
            
            sidebarOverlay.addEventListener('click', closeSidebar);
            sidebarClose.addEventListener('click', closeSidebar);
            
            // Close sidebar with Escape key
            document.addEventListener('keydown', function(event) {
                if (event.key === 'Escape' && sidebar.classList.contains('active')) {
                    closeSidebar();
                }
            });
        }

        function openSidebar() {
            document.getElementById('sidebar-overlay').classList.add('active');
            document.getElementById('sidebar').classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        function closeSidebar() {
            document.getElementById('sidebar-overlay').classList.remove('active');
            document.getElementById('sidebar').classList.remove('active');
            document.body.style.overflow = '';
        }

        // Contact Form Functionality
        function initContactForm() {
            const contactForm = document.getElementById('contactForm');
            
            contactForm.addEventListener('submit', function(e) {
                e.preventDefault();
                
                // Get form values
                const name = document.getElementById('name').value;
                const email = document.getElementById('email').value;
                const subject = document.getElementById('subject').value;
                const message = document.getElementById('message').value;
                
                // In a real application, you would send this data to a server
                // For this demo, we'll just show a success message
                alert(`Thank you, ${name}! Your message has been sent successfully.\n\nWe'll get back to you at ${email} as soon as possible.`);
                
                // Reset the form
                contactForm.reset();
            });
        }

        // Modal Functions
        function initModal() {
            const modalOverlay = document.getElementById('modal-overlay');
            const modalClose = document.getElementById('modal-close');
            
            modalClose.addEventListener('click', closeModal);
            
            modalOverlay.addEventListener('click', function(event) {
                if (event.target === modalOverlay) {
                    closeModal();
                }
            });
            
            // Close modal with Escape key
            document.addEventListener('keydown', function(event) {
                if (event.key === 'Escape' && modalOverlay.classList.contains('active')) {
                    closeModal();
                }
            });
        }

        function openArticleModal(articleId, newsData) {
            const article = newsData.find(a => a.id === articleId);
            
            if (!article) return;
            
            // Update modal content
            document.getElementById('modal-image').innerHTML = `<img src="${article.image}" alt="${article.title}">`;
            document.getElementById('modal-category').textContent = article.category;
            document.getElementById('modal-title').textContent = article.title;
            document.getElementById('modal-meta').innerHTML = `
                <span><i class="far fa-user"></i> ${article.author}</span>
                <span><i class="far fa-calendar"></i> ${formatDate(article.date)}</span>
                <span><i class="fas fa-source"></i> ${article.source}</span>
            `;
            document.getElementById('modal-body').innerHTML = article.content;
            
            // Add source link if available
            if (article.url) {
                document.getElementById('modal-body').innerHTML += `
                    <p><a href="${article.url}" target="_blank" class="btn">Read Full Article at Source</a></p>
                `;
            }
            
            // Show modal
            document.getElementById('modal-overlay').classList.add('active');
            document.body.style.overflow = 'hidden'; // Prevent scrolling
        }

        function closeModal() {
            document.getElementById('modal-overlay').classList.remove('active');
            document.body.style.overflow = ''; // Restore scrolling
        }

        // Utility Functions
        function formatDate(dateString) {
            const options = { year: 'numeric', month: 'long', day: 'numeric' };
            return new Date(dateString).toLocaleDateString('en-US', options);
        }

        function getCurrentDate() {
            return new Date().toISOString().split('T')[0];
        }

        function updateLastUpdatedTime() {
            const now = new Date();
            const timeString = now.toLocaleTimeString('en-US', { 
                hour: '2-digit', 
                minute: '2-digit',
                second: '2-digit'
            });
            document.getElementById('last-updated').textContent = timeString;
        }

        function getShortCategory(category) {
            const categoryMap = {
                'technology': 'Technology',
                'sports': 'Sports',
                'politics': 'Politics',
                'entertainment': 'Entertainment',
                'business': 'Business',
                'health': 'Health',
                'science': 'Science',
                'general': 'General'
            };
            
            const lowerCategory = category.toLowerCase();
            for (const key in categoryMap) {
                if (lowerCategory.includes(key)) {
                    return categoryMap[key];
                }
            }
            
            return 'General';
        }

        function getFallbackImage(category) {
            const fallbackImages = {
                'Technology': 'https://images.unsplash.com/photo-1518709268805-4e9042af2176?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80',
                'Sports': 'https://images.unsplash.com/photo-1461896836934-ffe607ba8211?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80',
                'Politics': 'https://images.unsplash.com/photo-1529107386315-e1a2ed48a620?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80',
                'Entertainment': 'https://images.unsplash.com/photo-1489599809505-f2d4cac55b73?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80',
                'Business': 'https://images.unsplash.com/photo-1507679799987-c73779587ccf?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1471&q=80',
                'Health': 'https://images.unsplash.com/photo-1559757148-5c350d0d3c56?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80',
                'Science': 'https://images.unsplash.com/photo-1532094349884-543bc11b234d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80',
                'General': 'https://images.unsplash.com/photo-1585829365295-ab7cd400c167?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80'
            };
            
            return fallbackImages[category] || fallbackImages['General'];
        }
    </script>
</body>
</html>
