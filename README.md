[index.html](https://github.com/user-attachments/files/22687558/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hammad Khan Photography | Professional Portfolio</title>
    <style>
        /* Reset and Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary-color: #2c3e50;
            --accent-color: #e74c3c;
            --light-color: #ecf0f1;
            --dark-color: #2c3e50;
            --text-color: #333;
            --transition: all 0.3s ease;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            line-height: 1.6;
            color: var(--text-color);
            background-color: #f9f9f9;
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
            display: block;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            background-color: var(--accent-color);
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: var(--transition);
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-size: 0.9rem;
        }

        .btn:hover {
            background-color: #c0392b;
            transform: translateY(-3px);
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }

        .section-title h2 {
            font-size: 2.5rem;
            color: var(--primary-color);
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .section-title::after {
            content: '';
            position: absolute;
            width: 80px;
            height: 4px;
            background-color: var(--accent-color);
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
        }

        /* Header Styles */
        header {
            background-color: var(--primary-color);
            color: white;
            position: fixed;
            width: 100%;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.5rem 0;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            letter-spacing: 1px;
        }

        .logo span {
            color: var(--accent-color);
        }

        .nav-links {
            display: flex;
        }

        .nav-links li {
            margin-left: 2rem;
        }

        .nav-links a {
            font-weight: 500;
            transition: var(--transition);
            position: relative;
        }

        .nav-links a:hover {
            color: var(--accent-color);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            background-color: var(--accent-color);
            bottom: -5px;
            left: 0;
            transition: var(--transition);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .hamburger {
            display: none;
            cursor: pointer;
        }

        .hamburger span {
            display: block;
            width: 25px;
            height: 3px;
            background-color: white;
            margin: 5px 0;
            transition: var(--transition);
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), url('https://images.unsplash.com/photo-1506905925346-21bda4d32df4?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80') no-repeat center center/cover;
            color: white;
            display: flex;
            align-items: center;
            text-align: center;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            text-transform: uppercase;
            letter-spacing: 3px;
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        /* Portfolio Section */
        .portfolio {
            padding: 6rem 0;
            background-color: white;
        }

        .portfolio-filter {
            display: flex;
            justify-content: center;
            margin-bottom: 2rem;
            flex-wrap: wrap;
        }

        .filter-btn {
            padding: 8px 20px;
            margin: 0 5px 10px;
            background: none;
            border: 2px solid var(--primary-color);
            color: var(--primary-color);
            border-radius: 30px;
            cursor: pointer;
            transition: var(--transition);
            font-weight: 500;
        }

        .filter-btn.active, .filter-btn:hover {
            background-color: var(--primary-color);
            color: white;
        }

        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
        }

        .portfolio-item {
            position: relative;
            overflow: hidden;
            border-radius: 5px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            height: 250px;
        }

        .portfolio-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .portfolio-item:hover img {
            transform: scale(1.1);
        }

        .portfolio-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(44, 62, 80, 0.8);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: var(--transition);
            color: white;
            padding: 20px;
            text-align: center;
        }

        .portfolio-item:hover .portfolio-overlay {
            opacity: 1;
        }

        .portfolio-overlay h3 {
            font-size: 1.5rem;
            margin-bottom: 10px;
        }

        /* About Section */
        .about {
            padding: 6rem 0;
            background-color: #f5f5f5;
        }

        .about-content {
            display: flex;
            align-items: center;
            gap: 4rem;
        }

        .about-img {
            flex: 1;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }

        .about-text {
            flex: 1;
        }

        .about-text h2 {
            font-size: 2.2rem;
            margin-bottom: 1.5rem;
            color: var(--primary-color);
        }

        .about-text p {
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
        }

        .stats {
            display: flex;
            justify-content: space-between;
            margin-top: 2rem;
        }

        .stat {
            text-align: center;
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--accent-color);
            display: block;
        }

        .stat-text {
            font-size: 1rem;
            color: var(--dark-color);
        }

        /* Services Section */
        .services {
            padding: 6rem 0;
            background-color: white;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .service-card {
            background-color: white;
            border-radius: 8px;
            padding: 2rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: var(--transition);
            text-align: center;
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }

        .service-icon {
            font-size: 2.5rem;
            color: var(--accent-color);
            margin-bottom: 1.5rem;
        }

        .service-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--primary-color);
        }

        /* Contact Section */
        .contact {
            padding: 6rem 0;
            background-color: #f5f5f5;
        }

        .contact-content {
            display: flex;
            gap: 4rem;
        }

        .contact-info {
            flex: 1;
        }

        .contact-form {
            flex: 1;
        }

        .contact-item {
            display: flex;
            align-items: flex-start;
            margin-bottom: 2rem;
        }

        .contact-icon {
            font-size: 1.5rem;
            color: var(--accent-color);
            margin-right: 1rem;
            min-width: 30px;
        }

        .form-group {
            margin-bottom: 1.5rem;
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
            border-color: var(--accent-color);
            outline: none;
        }

        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }

        /* Footer */
        footer {
            background-color: var(--primary-color);
            color: white;
            padding: 3rem 0 1.5rem;
        }

        .footer-content {
            display: flex;
            justify-content: space-between;
            margin-bottom: 2rem;
        }

        .footer-logo {
            font-size: 1.8rem;
            font-weight: 700;
            margin-bottom: 1rem;
        }

        .footer-logo span {
            color: var(--accent-color);
        }

        .social-links {
            display: flex;
            gap: 1rem;
        }

        .social-link {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            transition: var(--transition);
        }

        .social-link:hover {
            background-color: var(--accent-color);
            transform: translateY(-5px);
        }

        .copyright {
            text-align: center;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.9rem;
        }

        /* Responsive Styles */
        @media (max-width: 992px) {
            .about-content, .contact-content {
                flex-direction: column;
            }
            
            .about-img, .about-text, .contact-info, .contact-form {
                width: 100%;
            }
        }

        @media (max-width: 768px) {
            .navbar {
                padding: 1rem 0;
            }

            .nav-links {
                position: fixed;
                top: 70px;
                left: -100%;
                width: 100%;
                flex-direction: column;
                background-color: var(--primary-color);
                text-align: center;
                transition: var(--transition);
                box-shadow: 0 10px 15px rgba(0, 0, 0, 0.1);
                padding: 2rem 0;
            }

            .nav-links.active {
                left: 0;
            }

            .nav-links li {
                margin: 1rem 0;
            }

            .hamburger {
                display: block;
            }

            .hamburger.active span:nth-child(1) {
                transform: rotate(45deg) translate(5px, 5px);
            }

            .hamburger.active span:nth-child(2) {
                opacity: 0;
            }

            .hamburger.active span:nth-child(3) {
                transform: rotate(-45deg) translate(7px, -6px);
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .section-title h2 {
                font-size: 2rem;
            }

            .stats {
                flex-direction: column;
                gap: 1.5rem;
            }
        }

        @media (max-width: 576px) {
            .hero h1 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .portfolio-grid {
                grid-template-columns: 1fr;
            }
            
            .footer-content {
                flex-direction: column;
                gap: 2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <nav class="navbar">
                <a href="#" class="logo">Hammad<span>Khan</span></a>
                <ul class="nav-links">
                    <li><a href="#home">Home</a></li>
                    <li><a href="#portfolio">Portfolio</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#services">Services</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
                <div class="hamburger">
                    <span></span>
                    <span></span>
                    <span></span>
                </div>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content">
                <h1>Hammad Khan Photography</h1>
                <p>Professional photography services specializing in portraits, events, and creative projects. Capturing your special moments with artistic vision.</p>
                <a href="#portfolio" class="btn">View My Work</a>
            </div>
        </div>
    </section>

    <!-- Portfolio Section -->
    <section class="portfolio" id="portfolio">
        <div class="container">
            <div class="section-title">
                <h2>My Portfolio</h2>
            </div>
            <div class="portfolio-filter">
                <button class="filter-btn active" data-filter="all">All</button>
                <button class="filter-btn" data-filter="portrait">Portraits</button>
                <button class="filter-btn" data-filter="wedding">Weddings</button>
                <button class="filter-btn" data-filter="nature">Nature</button>
                <button class="filter-btn" data-filter="urban">Urban</button>
            </div>
            <div class="portfolio-grid">
                <div class="portfolio-item" data-category="portrait">
                    <img src='https://i.postimg.cc/56kZqgxs/Whats-App-Image-2025-10-03-at-22-40-34-bed5e54b-Copy.jpg' border='0' alt='Whats-App-Image-2025-10-03-at-22-40-34-bed5e54b-Copy'/></a>">" alt="Portrait Photography">
                    <div class="portfolio-overlay">
                        <h3>Portrait Session</h3>
                        <p>Elegant portrait photography</p>
                    </div>
                </div>
                <div class="portfolio-item" data-category="wedding">
                    <img src="https://images.unsplash.com/photo-1511285560929-80b456fea0bc?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Wedding Photography">
                    <div class="portfolio-overlay">
                        <h3>Wedding Day</h3>
                        <p>Capturing precious moments</p>
                    </div>
                </div>
                <div class="portfolio-item" data-category="nature">
                    <img src="https://images.unsplash.com/photo-1501854140801-50d01698950b?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Nature Photography">
                    <div class="portfolio-overlay">
                        <h3>Nature's Beauty</h3>
                        <p>Landscape and nature shots</p>
                    </div>
                </div>
                <div class="portfolio-item" data-category="urban">
                    <img src="https://images.unsplash.com/photo-1477959858617-67f85cf4f1df?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Urban Photography">
                    <div class="portfolio-overlay">
                        <h3>City Life</h3>
                        <p>Urban and street photography</p>
                    </div>
                </div>
                <div class="portfolio-item" data-category="portrait">
                    <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Portrait Photography">
                    <div class="portfolio-overlay">
                        <h3>Creative Portraits</h3>
                        <p>Artistic portrait sessions</p>
                    </div>
                </div>
                <div class="portfolio-item" data-category="wedding">
                    <img src="https://images.unsplash.com/photo-1465495976277-4387d4b0e4a6?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Wedding Photography">
                    <div class="portfolio-overlay">
                        <h3>Wedding Details</h3>
                        <p>Special moments captured</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section class="about" id="about">
        <div class="container">
            <div class="section-title">
                <h2>About Me</h2>
            </div>
            <div class="about-content">
                <div class="about-img">
                    <img src="https://scontent.fisb2-1.fna.fbcdn.net/v/t39.30808-6/481206471_1122282789673974_5482133487557776107_n.jpg?stp=c0.169.1536.1536a_dst-jpg_s206x206_tt6&_nc_cat=104&ccb=1-7&_nc_sid=50ad20&_nc_eui2=AeEDoz6g3zTA9auoWgq8P-1s60MS1yWepMLrQxLXJZ6kwn_-xtCMJnDpWNqUGd3M7b_hiQqPsF8d1RrUujoIsIsm&_nc_ohc=OiZtVfQItIQQ7kNvwHCJ-yU&_nc_oc=AdkRh8bFM4mrrTn1A4Rf6GU3TEjUB1s0H_E6BfouNodcAhaXGsednI1KS2-3pRugQjAoViUH03LtTJjRQEalmtpl&_nc_zt=23&_nc_ht=scontent.fisb2-1.fna&_nc_gid=c0PuCCuiXkumIJSA8PvGYA&oh=00_AffefvIDUcuyjsJ5ZS5obSo50Tl8kC3UhJrV_22cTvmO1g&oe=68E5F84D"Hammad Khan - Photographer">
                </div>
                <div class="about-text">
                    <h2>Hi, I'm Hammad Bin Altaf</h2>
                    <p>With over 5 years of professional photography experience, I specialize in capturing authentic moments that tell unique stories. My approach combines technical expertise with a creative eye to produce images that are both beautiful and meaningful.</p>
                    <p>Based in Batkhela,Malakand, I've had the privilege of working with clients from various backgrounds, helping them preserve their most precious memories through my lens.</p>
                    <div class="stats">
                        <div class="stat">
                            <span class="stat-number">200+</span>
                            <span class="stat-text">Projects Completed</span>
                        </div>
                        <div class="stat">
                            <span class="stat-number">100+</span>
                            <span class="stat-text">Happy Clients</span>
                        </div>
                        <div class="stat">
                            <span class="stat-number">5+</span>
                            <span class="stat-text">Years Experience</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section class="services" id="services">
        <div class="container">
            <div class="section-title">
                <h2>My Services</h2>
            </div>
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-icon">📷</div>
                    <h3>Portrait Photography</h3>
                    <p>Professional portrait sessions for individuals, couples, and families. Create timeless memories with stunning portraits.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">💒</div>
                    <h3>Wedding Photography</h3>
                    <p>Capture your special day with beautiful, candid wedding photography that tells your unique love story.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">🏢</div>
                    <h3>Commercial Photography</h3>
                    <p>Professional product and commercial photography to enhance your brand and marketing materials.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact" id="contact">
        <div class="container">
            <div class="section-title">
                <h2>Get In Touch</h2>
            </div>
            <div class="contact-content">
                <div class="contact-info">
                    <h3>Contact Information</h3>
                    <div class="contact-item">
                        <div class="contact-icon">📍</div>
                        <div>
                            <h4>Address</h4>
                            <p>Batkhela,Malakand, Pakistan</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">📞</div>
                        <div>
                            <h4>Phone</h4>
                            <p>+92 3413095530</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">✉️</div>
                        <div>
                            <h4>Email</h4>
                            <p>hk3138125@gmail.com</p>
                        </div>
                    </div>
                </div>
                <div class="contact-form">
                    <form id="contactForm">
                        <div class="form-group">
                            <input type="text" class="form-control" placeholder="Your Name" required>
                        </div>
                        <div class="form-group">
                            <input type="email" class="form-control" placeholder="Your Email" required>
                        </div>
                        <div class="form-group">
                            <input type="text" class="form-control" placeholder="Subject">
                        </div>
                        <div class="form-group">
                            <textarea class="form-control" placeholder="Your Message" required></textarea>
                        </div>
                        <button type="submit" class="btn">Send Message</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div>
                    <div class="footer-logo">Hammad<span>Khan</span></div>
                    <p>Professional photography services for all your special moments.</p>
                </div>
                <div class="social-links">
                    <a href="#" class="social-link">FB</a>
                    <a href="#" class="social-link">IG</a>
                    <a href="#" class="social-link">TW</a>
                    <a href="#" class="social-link">PT</a>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2024 Hammad Khan Photography. All Rights Reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Mobile Navigation Toggle
        const hamburger = document.querySelector('.hamburger');
        const navLinks = document.querySelector('.nav-links');

        hamburger.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            hamburger.classList.toggle('active');
        });

        // Close mobile menu when clicking on a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
                hamburger.classList.remove('active');
            });
        });

        // Portfolio Filter
        const filterButtons = document.querySelectorAll('.filter-btn');
        const portfolioItems = document.querySelectorAll('.portfolio-item');

        filterButtons.forEach(button => {
            button.addEventListener('click', () => {
                // Remove active class from all buttons
                filterButtons.forEach(btn => btn.classList.remove('active'));
                // Add active class to clicked button
                button.classList.add('active');
                
                const filterValue = button.getAttribute('data-filter');
                
                portfolioItems.forEach(item => {
                    if (filterValue === 'all' || item.getAttribute('data-category') === filterValue) {
                        item.style.display = 'block';
                    } else {
                        item.style.display = 'none';
                    }
                });
            });
        });

        // Smooth Scrolling for Navigation Links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if(targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if(targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });

        // Form Submission
        const contactForm = document.getElementById('contactForm');
        contactForm.addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Thank you for your message, Hammad will get back to you soon!');
            this.reset();
        });

        // Header background on scroll
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.backgroundColor = 'rgba(44, 62, 80, 0.95)';
            } else {
                header.style.backgroundColor = 'var(--primary-color)';
            }
        });
    </script>
</body>
</html>
