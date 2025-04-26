# nocone.github.io

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Name - Personal Site</title>
    <style>
        :root {
            --primary: #8b5cf6;
            --primary-dark: #7c3aed;
            --primary-light: #a78bfa;
            --dark: #121212;
            --dark-2: #1e1e1e;
            --dark-3: #2a2a2a;
            --light: #f9fafb;
            --gray: #9ca3af;
            --accent: #10b981;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
        }
        
        body {
            background-color: var(--dark);
            color: var(--light);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }
        
        header {
            padding: 1.5rem 0;
            background-color: rgba(0, 0, 0, 0.5);
            backdrop-filter: blur(10px);
            position: sticky;
            top: 0;
            z-index: 100;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 1rem;
        }
        
        .logo-img {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            object-fit: cover;
            border: 2px solid var(--primary);
        }
        
        .nav-links {
            display: flex;
            gap: 1.5rem;
        }
        
        .nav-links a {
            color: var(--light);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.2s;
            position: relative;
            padding: 0.5rem 0;
        }
        
        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: 0;
            left: 0;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            transition: width 0.3s ease;
        }
        
        .nav-links a:hover::after {
            width: 100%;
        }
        
        .nav-links a:hover {
            color: var(--primary-light);
        }
        
        .hero {
            padding: 8rem 0;
            text-align: center;
            background: linear-gradient(rgba(0,0,0,0.8), rgba(0,0,0,0.8)), url('/api/placeholder/1200/600') center/cover;
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, rgba(139, 92, 246, 0.3), rgba(16, 185, 129, 0.3));
            z-index: 1;
        }
        
        .hero-content {
            position: relative;
            z-index: 2;
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            background: linear-gradient(to right, var(--primary-light), var(--accent));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            display: inline-block;
        }
        
        .hero p {
            font-size: 1.25rem;
            max-width: 700px;
            margin: 0 auto;
            color: var(--light);
        }
        
        section {
            padding: 6rem 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            font-size: 2.5rem;
            background: linear-gradient(to right, var(--primary), var(--accent));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            display: inline-block;
            position: relative;
            left: 50%;
            transform: translateX(-50%);
        }
        
        .section-title::after {
            content: '';
            display: block;
            width: 60px;
            height: 4px;
            background: linear-gradient(to right, var(--primary), var(--accent));
            margin: 0.5rem auto 0;
            border-radius: 2px;
        }
        
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 3rem;
            align-items: center;
        }
        
        .profile-container {
            position: relative;
        }
        
        .profile-img {
            width: 100%;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            border: 3px solid var(--dark-3);
            position: relative;
            z-index: 2;
        }
        
        .profile-img::before {
            content: '';
            position: absolute;
            top: -10px;
            left: -10px;
            right: -10px;
            bottom: -10px;
            background: linear-gradient(45deg, var(--primary), var(--accent));
            z-index: -1;
            border-radius: 15px;
            filter: blur(15px);
            opacity: 0.6;
        }
        
        .profile-bg {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 15px;
            left: 15px;
            background: var(--primary);
            border-radius: 12px;
            z-index: 1;
        }
        
        .social-links {
            margin-top: 2rem;
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }
        
        .social-btn {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.75rem 1.25rem;
            background: linear-gradient(45deg, var(--dark-3), var(--dark-2));
            color: white;
            text-decoration: none;
            border-radius: 8px;
            transition: all 0.3s;
            border: 1px solid rgba(255, 255, 255, 0.1);
            font-weight: 500;
        }
        
        .social-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2), 0 0 0 2px var(--primary-light);
        }
        
        .social-btn i {
            font-size: 1.25rem;
            color: var(--primary-light);
        }
        
        .portfolio {
            background-color: var(--dark-2);
            position: relative;
            overflow: hidden;
        }
        
        .portfolio::before {
            content: '';
            position: absolute;
            width: 400px;
            height: 400px;
            border-radius: 50%;
            background: var(--primary);
            filter: blur(150px);
            opacity: 0.1;
            top: -100px;
            right: -100px;
        }
        
        .portfolio::after {
            content: '';
            position: absolute;
            width: 300px;
            height: 300px;
            border-radius: 50%;
            background: var(--accent);
            filter: blur(150px);
            opacity: 0.1;
            bottom: -100px;
            left: -100px;
        }
        
        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
            position: relative;
            z-index: 2;
        }
        
        .portfolio-item {
            border-radius: 12px;
            overflow: hidden;
            background: linear-gradient(145deg, var(--dark-3), var(--dark));
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            transition: transform 0.4s, box-shadow 0.4s;
            border: 1px solid rgba(255, 255, 255, 0.05);
            position: relative;
        }
        
        .portfolio-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3), 0 0 0 2px var(--primary-light);
        }
        
        .portfolio-img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
        }
        
        .portfolio-content {
            padding: 1.5rem;
        }
        
        .portfolio-content h3 {
            margin-bottom: 0.75rem;
            color: var(--light);
        }
        
        .portfolio-content p {
            color: var(--gray);
            margin-bottom: 1.5rem;
        }
        
        .portfolio-link {
            display: inline-block;
            color: var(--primary-light);
            font-weight: 500;
            text-decoration: none;
            position: relative;
        }
        
        .portfolio-link::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -2px;
            left: 0;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            transition: width 0.3s ease;
        }
        
        .portfolio-link:hover::after {
            width: 100%;
        }
        
        #contact {
            background: var(--dark);
            position: relative;
            overflow: hidden;
        }
        
        #contact::before {
            content: '';
            position: absolute;
            width: 500px;
            height: 500px;
            border-radius: 50%;
            background: var(--primary);
            filter: blur(200px);
            opacity: 0.05;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
        }
        
        footer {
            background-color: var(--dark-3);
            color: var(--light);
            padding: 2rem 0;
            text-align: center;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
        }
        
        .btn {
            display: inline-block;
            padding: 0.75rem 1.5rem;
            background: linear-gradient(45deg, var(--primary), var(--primary-dark));
            color: white;
            text-decoration: none;
            border-radius: 8px;
            font-weight: 500;
            transition: all 0.3s;
            border: none;
            box-shadow: 0 4px 15px rgba(124, 58, 237, 0.4);
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(124, 58, 237, 0.5);
        }
        
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 1rem;
            }
            
            .about-grid {
                grid-template-columns: 1fr;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .portfolio-grid {
                grid-template-columns: 1fr;
            }
            
            .social-links {
                justify-content: center;
            }
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body>
    <header>
        <div class="container header-content">
            <div class="logo">
                <img src="/api/placeholder/80/80" alt="Profile" class="logo-img">
                <h2>Your Name</h2>
            </div>
            <nav class="nav-links">
                <a href="#about">About</a>
                <a href="#portfolio">Portfolio</a>
                <a href="#contact">Contact</a>
            </nav>
        </div>
    </header>
    
    <section class="hero">
        <div class="container hero-content">
            <h1>Hey, I'm Your Name</h1>
            <p>Roblox Developer | Designer | Creator</p>
        </div>
    </section>
    
    <section id="about">
        <div class="container">
            <h2 class="section-title">About Me</h2>
            <div class="about-grid">
                <div class="profile-container">
                    <div class="profile-img">
                        <img src="/api/placeholder/400/400" alt="Your profile" width="100%">
                    </div>
                    <div class="profile-bg"></div>
                </div>
                <div class="about-content">
                    <p>Hi there! I'm a passionate developer who loves creating immersive experiences on Roblox and beyond. I specialize in game design, scripting, and building virtual worlds that people enjoy exploring.</p>
                    <p>When I'm not coding or designing, you can find me gaming, learning new technologies, or collaborating with other creators on exciting projects.</p>
                    
                    <div class="social-links">
                        <a href="https://github.com/yourusername" class="social-btn">
                            <i class="fab fa-github"></i> GitHub
                        </a>
                        <a href="https://www.roblox.com/users/yourid/profile" class="social-btn">
                            <i class="fas fa-gamepad"></i> Roblox
                        </a>
                        <a href="https://discord.gg/yourinvite" class="social-btn">
                            <i class="fab fa-discord"></i> Discord
                        </a>
                        <a href="https://twitter.com/yourusername" class="social-btn">
                            <i class="fab fa-twitter"></i> Twitter
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <section id="portfolio" class="portfolio">
        <div class="container">
            <h2 class="section-title">My Portfolio</h2>
            <div class="portfolio-grid">
                <!-- Portfolio Item 1 -->
                <div class="portfolio-item">
                    <img src="/api/placeholder/400/300" alt="Roblox Game 1" class="portfolio-img">
                    <div class="portfolio-content">
                        <h3>Awesome Roblox Game</h3>
                        <p>A fun adventure game with over 1M+ visits!</p>
                        <a href="#" class="portfolio-link">View Project →</a>
                    </div>
                </div>
                
                <!-- Portfolio Item 2 -->
                <div class="portfolio-item">
                    <img src="/api/placeholder/400/300" alt="Roblox Game 2" class="portfolio-img">
                    <div class="portfolio-content">
                        <h3>Cool Simulator</h3>
                        <p>A simulator game with unique mechanics and systems.</p>
                        <a href="#" class="portfolio-link">View Project →</a>
                    </div>
                </div>
                
                <!-- Portfolio Item 3 -->
                <div class="portfolio-item">
                    <img src="/api/placeholder/400/300" alt="UI Design" class="portfolio-img">
                    <div class="portfolio-content">
                        <h3>Modern UI Kit</h3>
                        <p>A collection of UI components for Roblox developers.</p>
                        <a href="#" class="portfolio-link">View Project →</a>
                    </div>
                </div>
                
                <!-- To add more portfolio items, simply copy and paste this structure -->
            </div>
        </div>
    </section>
    
    <section id="contact">
        <div class="container" style="text-align: center;">
            <h2 class="section-title">Get In Touch</h2>
            <p>Interested in working together or have any questions?</p>
            <p>Reach out to me on Discord or send me an email:</p>
            <p><strong>Email:</strong> your.email@example.com</p>
            <p><strong>Discord:</strong> YourUsername#0000</p>
            <div style="margin-top: 2rem;">
                <a href="mailto:your.email@example.com" class="btn">Send Email</a>
            </div>
        </div>
    </section>
    
    <footer>
        <div class="container">
            <p>© 2025 Your Name. All rights reserved.</p>
        </div>
    </footer>

    <script>
        // JavaScript for dynamic content loading or interactions can be added here
        // This is where you could add code to dynamically load portfolio items from a JSON file
        
        document.addEventListener('DOMContentLoaded', function() {
            // Example of how you could add smooth scrolling
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    document.querySelector(this.getAttribute('href')).scrollIntoView({
                        behavior: 'smooth'
                    });
                });
            });
            
            // Add parallax effect to hero section
            window.addEventListener('scroll', function() {
                const scrollPosition = window.pageYOffset;
                const hero = document.querySelector('.hero');
                if (hero) {
                    hero.style.backgroundPosition = `center ${scrollPosition * 0.5}px`;
                }
            });
        });
    </script>
</body>
</html>
