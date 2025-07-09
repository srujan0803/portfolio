<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Roopesh N - Frontend Developer & Data Analyst</title>
    <style>
        /* Reset and Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-color: #00f5ff;
            --secondary-color: #ff6b6b;
            --accent-color: #4ecdc4;
            --bg-dark: #0a0a0a;
            --bg-card: #1a1a1a;
            --text-light: #ffffff;
            --text-gray: #b0b0b0;
            --gradient-primary: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            --gradient-secondary: linear-gradient(135deg, #00f5ff 0%, #4ecdc4 100%);
            --shadow-glow: 0 0 30px rgba(0, 245, 255, 0.3);
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            background: var(--bg-dark);
            color: var(--text-light);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Mobile Menu Toggle */
        .mobile-menu-toggle {
            display: none;
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 1001;
            background: var(--bg-card);
            border: 2px solid var(--primary-color);
            border-radius: 8px;
            padding: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .mobile-menu-toggle:hover {
            background: var(--primary-color);
            transform: scale(1.05);
        }

        .hamburger {
            width: 25px;
            height: 3px;
            background: var(--text-light);
            margin: 5px 0;
            transition: 0.3s;
        }

        .mobile-menu-toggle.active .hamburger:nth-child(1) {
            transform: rotate(-45deg) translate(-5px, 6px);
        }

        .mobile-menu-toggle.active .hamburger:nth-child(2) {
            opacity: 0;
        }

        .mobile-menu-toggle.active .hamburger:nth-child(3) {
            transform: rotate(45deg) translate(-5px, -6px);
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            background: rgba(10, 10, 10, 0.95);
            backdrop-filter: blur(20px);
            z-index: 1000;
            transition: all 0.3s ease;
            border-bottom: 1px solid rgba(0, 245, 255, 0.2);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        nav ul {
            list-style: none;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px 0;
        }

        nav ul li {
            margin: 0 25px;
        }

        nav ul li a {
            color: var(--text-light);
            text-decoration: none;
            font-weight: 500;
            position: relative;
            transition: all 0.3s ease;
            padding: 8px 16px;
            border-radius: 25px;
        }

        nav ul li a::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: var(--gradient-secondary);
            border-radius: 25px;
            opacity: 0;
            transition: opacity 0.3s ease;
            z-index: -1;
        }

        nav ul li a:hover::before,
        nav ul li a.active::before {
            opacity: 1;
        }

        nav ul li a:hover {
            color: var(--bg-dark);
            transform: translateY(-2px);
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            background: radial-gradient(circle at 30% 40%, rgba(0, 245, 255, 0.1) 0%, transparent 70%),
                        radial-gradient(circle at 70% 80%, rgba(78, 205, 196, 0.1) 0%, transparent 70%);
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000"><defs><pattern id="grid" width="50" height="50" patternUnits="userSpaceOnUse"><path d="M 50 0 L 0 0 0 50" fill="none" stroke="%23ffffff08" stroke-width="1"/></pattern></defs><rect width="100%" height="100%" fill="url(%23grid)"/></svg>');
            opacity: 0.3;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 800px;
            padding: 0 20px;
        }

        .hero-title {
            font-size: clamp(2.5rem, 8vw, 6rem);
            font-weight: 800;
            margin-bottom: 20px;
            background: var(--gradient-secondary);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: fadeInUp 1s ease-out;
        }

        .hero-subtitle {
            font-size: clamp(1.2rem, 4vw, 2rem);
            color: var(--text-gray);
            margin-bottom: 30px;
            animation: fadeInUp 1s ease-out 0.2s both;
        }

        .hero-description {
            font-size: clamp(1rem, 2vw, 1.3rem);
            max-width: 600px;
            margin: 0 auto 40px;
            line-height: 1.8;
            animation: fadeInUp 1s ease-out 0.4s both;
        }

        .cta-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
            animation: fadeInUp 1s ease-out 0.6s both;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            padding: 15px 30px;
            border: none;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            cursor: pointer;
            font-size: 1rem;
        }

        .btn-primary {
            background: var(--gradient-secondary);
            color: var(--bg-dark);
            box-shadow: var(--shadow-glow);
        }

        .btn-secondary {
            background: transparent;
            color: var(--text-light);
            border: 2px solid var(--primary-color);
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0, 245, 255, 0.5);
        }

        .btn-secondary:hover {
            background: var(--primary-color);
            color: var(--bg-dark);
        }

        /* Section Styles */
        .section {
            padding: 100px 0;
            position: relative;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .section-title {
            font-size: clamp(2rem, 5vw, 3.5rem);
            text-align: center;
            margin-bottom: 20px;
            position: relative;
            display: inline-block;
            width: 100%;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: var(--gradient-secondary);
            border-radius: 2px;
        }

        .section-subtitle {
            text-align: center;
            color: var(--text-gray);
            font-size: clamp(1rem, 2vw, 1.3rem);
            margin-bottom: 60px;
        }

        /* About Section */
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 60px;
            align-items: center;
        }

        .about-image {
            position: relative;
        }

        .profile-card {
            background: var(--bg-card);
            border-radius: 20px;
            padding: 40px;
            text-align: center;
            border: 1px solid rgba(0, 245, 255, 0.2);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .profile-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: var(--gradient-secondary);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .profile-card:hover::before {
            opacity: 0.1;
        }

        .profile-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-glow);
        }

        .profile-avatar {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: var(--gradient-secondary);
            margin: 0 auto 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            font-weight: bold;
            color: var(--bg-dark);
            position: relative;
            z-index: 1;
        }

        .profile-info {
            position: relative;
            z-index: 1;
        }

        .about-content {
            font-size: 1.1rem;
            line-height: 1.8;
        }

        .about-content p {
            margin-bottom: 20px;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 20px;
            margin-top: 40px;
        }

        .stat-item {
            text-align: center;
            padding: 20px;
            background: var(--bg-card);
            border-radius: 15px;
            border: 1px solid rgba(0, 245, 255, 0.2);
            transition: all 0.3s ease;
        }

        .stat-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 245, 255, 0.2);
        }

        .stat-number {
            font-size: 2rem;
            font-weight: bold;
            color: var(--primary-color);
        }

        .stat-label {
            color: var(--text-gray);
            font-size: 0.9rem;
        }

        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }

        .skill-card {
            background: var(--bg-card);
            border-radius: 20px;
            padding: 30px;
            border: 1px solid rgba(0, 245, 255, 0.2);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .skill-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: var(--gradient-secondary);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .skill-card:hover::before {
            opacity: 0.1;
        }

        .skill-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-glow);
        }

        .skill-icon {
            font-size: 3rem;
            margin-bottom: 20px;
            position: relative;
            z-index: 1;
        }

        .skill-title {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 15px;
            color: var(--primary-color);
            position: relative;
            z-index: 1;
        }

        .skill-description {
            color: var(--text-gray);
            line-height: 1.6;
            position: relative;
            z-index: 1;
        }

        .skill-level {
            margin-top: 20px;
            position: relative;
            z-index: 1;
        }

        .skill-bar {
            width: 100%;
            height: 8px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 4px;
            overflow: hidden;
            margin-top: 10px;
        }

        .skill-progress {
            height: 100%;
            background: var(--gradient-secondary);
            border-radius: 4px;
            transition: width 2s ease;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
        }

        .project-card {
            background: var(--bg-card);
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid rgba(0, 245, 255, 0.2);
            transition: all 0.3s ease;
            position: relative;
            group: hover;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-glow);
        }

        .project-image {
            height: 200px;
            background: var(--gradient-primary);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            color: white;
            position: relative;
            overflow: hidden;
        }

        .project-image::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.3);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .project-card:hover .project-image::before {
            opacity: 1;
        }

        .project-content {
            padding: 30px;
        }

        .project-title {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 15px;
            color: var(--primary-color);
        }

        .project-description {
            color: var(--text-gray);
            line-height: 1.6;
            margin-bottom: 20px;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 20px;
        }

        .tech-tag {
            background: rgba(0, 245, 255, 0.1);
            color: var(--primary-color);
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.9rem;
            border: 1px solid rgba(0, 245, 255, 0.3);
        }

        .project-links {
            display: flex;
            gap: 15px;
        }

        .project-link {
            color: var(--text-light);
            text-decoration: none;
            padding: 8px 20px;
            border: 1px solid var(--primary-color);
            border-radius: 20px;
            transition: all 0.3s ease;
        }

        .project-link:hover {
            background: var(--primary-color);
            color: var(--bg-dark);
        }

        /* Experience Section */
        .experience-timeline {
            position: relative;
            padding-left: 40px;
        }

        .experience-timeline::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            bottom: 0;
            width: 2px;
            background: var(--gradient-secondary);
        }

        .experience-item {
            position: relative;
            margin-bottom: 50px;
            background: var(--bg-card);
            padding: 30px;
            border-radius: 15px;
            border: 1px solid rgba(0, 245, 255, 0.2);
            transition: all 0.3s ease;
        }

        .experience-item::before {
            content: '';
            position: absolute;
            left: -49px;
            top: 30px;
            width: 16px;
            height: 16px;
            border-radius: 50%;
            background: var(--primary-color);
            box-shadow: 0 0 0 4px var(--bg-dark);
        }

        .experience-item:hover {
            transform: translateX(10px);
            box-shadow: var(--shadow-glow);
        }

        .experience-date {
            color: var(--primary-color);
            font-weight: 600;
            margin-bottom: 10px;
        }

        .experience-title {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: 5px;
        }

        .experience-company {
            color: var(--text-gray);
            margin-bottom: 15px;
        }

        .experience-description {
            line-height: 1.6;
        }

        /* Contact Section */
        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .contact-card {
            background: var(--bg-card);
            padding: 40px;
            border-radius: 20px;
            text-align: center;
            border: 1px solid rgba(0, 245, 255, 0.2);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .contact-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: var(--gradient-secondary);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .contact-card:hover::before {
            opacity: 0.1;
        }

        .contact-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-glow);
        }

        .contact-icon {
            font-size: 3rem;
            margin-bottom: 20px;
            color: var(--primary-color);
            position: relative;
            z-index: 1;
        }

        .contact-title {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: 15px;
            position: relative;
            z-index: 1;
        }

        .contact-info {
            color: var(--text-gray);
            position: relative;
            z-index: 1;
        }

        .contact-info a {
            color: var(--primary-color);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .contact-info a:hover {
            color: var(--text-light);
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .fade-in {
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.8s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .mobile-menu-toggle {
                display: block;
            }

            nav ul {
                display: none;
                position: absolute;
                top: 100%;
                left: 0;
                right: 0;
                background: var(--bg-card);
                flex-direction: column;
                padding: 20px;
                border-top: 1px solid rgba(0, 245, 255, 0.2);
            }

            nav ul.active {
                display: flex;
            }

            nav ul li {
                margin: 10px 0;
            }

            .about-grid {
                grid-template-columns: 1fr;
                gap: 40px;
                text-align: center;
            }

            .skills-grid {
                grid-template-columns: 1fr;
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }

            .experience-timeline {
                padding-left: 20px;
            }

            .experience-item {
                margin-left: 0;
            }

            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .cta-buttons {
                flex-direction: column;
                align-items: center;
            }

            .btn {
                width: 100%;
                max-width: 300px;
                justify-content: center;
            }
        }

        @media (max-width: 480px) {
            .container {
                padding: 0 15px;
            }

            .section {
                padding: 60px 0;
            }

            .profile-card {
                padding: 20px;
            }

            .skill-card,
            .project-card,
            .contact-card {
                padding: 20px;
            }

            .experience-item {
                padding: 20px;
            }

            .stats-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Scroll indicator */
        .scroll-indicator {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: rgba(0, 245, 255, 0.2);
            z-index: 1002;
        }

        .scroll-progress {
            height: 100%;
            background: var(--gradient-secondary);
            width: 0%;
            transition: width 0.3s ease;
        }
    </style>
</head>
<body>
    <div class="scroll-indicator">
        <div class="scroll-progress"></div>
    </div>

    <div class="mobile-menu-toggle" onclick="toggleMobileMenu()">
        <div class="hamburger"></div>
        <div class="hamburger"></div>
        <div class="hamburger"></div>
    </div>

    <nav>
        <div class="nav-container">
            <ul id="navMenu">
                <li><a href="#home" class="nav-link">Home</a></li>
                <li><a href="#about" class="nav-link">About</a></li>
                <li><a href="#skills" class="nav-link">Skills</a></li>
                <li><a href="#projects" class="nav-link">Projects</a></li>
                <li><a href="#experience" class="nav-link">Experience</a></li>
                <li><a href="#contact" class="nav-link">Contact</a></li>
            </ul>
        </div>
    </nav>

    <section id="home" class="hero">
        <div class="hero-content">
            <h1 class="hero-title">ROOPESH N</h1>
            <p class="hero-subtitle">Frontend Developer & Data Analyst</p>
            <p class="hero-description">
                Passionate about creating exceptional digital experiences and transforming data into actionable insights. 
                Specialized in modern web technologies and data analytics.
            </p>
            <div class="cta-buttons">
                <a href="#projects" class="btn btn-primary">View My Work</a>
                <a href="#contact" class="btn btn-secondary">Get In Touch</a>
            </div>
        </div>
    </section>

    <section id="about" class="section">
        <div class="container">
            <h2 class="section-title fade-in">About Me</h2>
            <p class="section-subtitle fade-in">Discover my journey in technology and innovation</p>
            
            <div class="about-grid">
                <div class="about-image fade-in">
                    <div class="profile-card">
                        <div class="profile-avatar">RN</div>
                        <div class="profile-info">
                            <h3>Roopesh N</h3>
                            <p>Frontend Developer & Data Analyst</p>
                            <p>📍 Anekkal, Bengaluru 560106</p>
                            <p>📧 sujanroopesh@gmail.com</p>
                            <p>📱 9742554890</p>
                        </div>
                    </div>
                </div>
                
                <div class="about-content fade-in">
                    <p>
                        I'm an aspiring UI/UX Designer and Frontend Developer with expertise in HTML, CSS, JavaScript, and Python. 
                        I excel in teamwork and collaboration, having developed user-centered digital solutions that enhanced user 
                        engagement by 20%.
                    </p>
                    
                    <p>
                        Currently pursuing a Bachelor of Computer Application from Bangalore University, I've built a strong foundation 
                        in programming, web development, data structures, and software engineering. My passion lies in creating 
                        innovative solutions that bridge the gap between design and functionality.
                    </p>
                    
                    <p>
                        Beyond academics, I've taken leadership roles including VP of Cyber Sprint, organized the successful tech 
                        event "Techkrithi", and work as a freelance Event Manager at Playo, coordinating various tech events and 
                        managing complex projects.
                    </p>
                    
                    <div class="stats-grid fade-in">
                        <div class="stat-item">
                            <div class="stat-number">20%</div>
                            <div class="stat-label">User Engagement</div>
                        </div>
                        <div class="stat-item">
                            <div class="stat-number">3+</div>
                            <div class="stat-label">Years Experience</div>
                        </div>
                        <div class="stat-item">
                            <div class="stat-number">10+</div>
                            <div class="stat-label">Projects</div>
                        </div>
                        <div class="stat-item">
                            <div class="stat-number">5+</div>
                            <div class="stat-label">Technologies</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="skills" class="section">
        <div class="container">
            <h2 class="section-title fade-in">Skills & Expertise</h2>
            <p class="section-subtitle fade-in">Technologies and tools I work with</p>
            
            <div class="skills-grid">
                <div class="skill-card fade-in">
                    <div class="skill-icon">🎨</div>
                    <h3 class="skill-title">UI/UX Design</h3>
                    <p class="skill-description">Creating intuitive and engaging user experiences with modern design principles</p>
                    <div class="skill-level">
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 90%"></div>
                        </div>
                    </div>
                </div>
                
                <div class="skill-card fade-in">
                    <div class="skill-icon">💻</div>
                    <h3 class="skill-title">Frontend Development</h3>
                    <p class="skill-description">Building responsive web applications with HTML, CSS, JavaScript, and modern frameworks</p>
                    <div class="skill-level">
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 85%"></div>
                        </div>
                    </div>
                </div>
                
                <div class="skill-card fade-in">
                    <div class="skill-icon">📊</div>
                    <h3 class="skill-title">Data Analysis</h3>
                    <p class="skill-description">Extracting insights from complex datasets using Python and advanced analytics</p>
                    <div class="skill-level">
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 80%"></div>
                        </div>
                    </div>
                </div>
                
                <div class="skill-card fade-in">
                    <div class="skill-icon">🐍</div>
                    <h3 class="skill-title">Python Programming</h3>
                    <p class="skill-description">Developing automation scripts and data processing applications</p>
                    <div class="skill-level">
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 88%"></div>
                        </div>
                    </div>
                </div>
                
                <div class="skill-card fade-in">
                    <div class="skill-icon">📈</div>
                    <h3 class="skill-title">Advanced Excel</h3>
                    <p class="skill-description">Advanced data manipulation, analysis, and visualization using Excel</p>
                    <div class="skill-level">
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 92%"></div>
                        </div>
                    </div>
                </div>
                
                <div class="skill-card fade-in">
                    <div class="skill-icon">🔧</div>
                    <h3 class="skill-title">Leadership & Teamwork</h3>
                    <p class="skill-description">Leading teams and collaborating effectively on complex projects</p>
                    <div class="skill-level">
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 95%"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="projects" class="section">
        <div class="container">
            <h2 class="section-title fade-in">Featured Projects</h2>
            <p class="section-subtitle fade-in">Some of my recent work and achievements</p>
            
            <div class="projects-grid">
                <div class="project-card fade-in">
                    <div class="project-image">🏟️</div>
                    <div class="project-content">
                        <h3 class="project-title">Kreeda Bookings</h3>
                        <p class="project-description">
                            A comprehensive sports facility booking platform with mobile-first design. 
                            Features include real-time availability, booking management, and user authentication.
                        </p>
                        <div class="project-tech">
                            <span class="tech-tag">HTML5</span>
                            <span class="tech-tag">CSS3</span>
                            <span class="tech-tag">JavaScript</span>
                            <span class="tech-tag">Bootstrap</span>
                            <span class="tech-tag">UI/UX</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">Live Demo</a>
                            <a href="#" class="project-link">GitHub</a>
                        </div>
                    </div>
                </div>
                
                <div class="project-card fade-in">
                    <div class="project-image">🎯</div>
                    <div class="project-content">
                        <h3 class="project-title">Techkrithi Event</h3>
                        <p class="project-description">
                            Successfully organized and managed a comprehensive tech event with 500+ participants. 
                            Coordinated workshops, competitions, and networking sessions.
                        </p>
                        <div class="project-tech">
                            <span class="tech-tag">Event Management</span>
                            <span class="tech-tag">Leadership</span>
                            <span class="tech-tag">Coordination</span>
                            <span class="tech-tag">Planning</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">Case Study</a>
                            <a href="#" class="project-link">Gallery</a>
                        </div>
                    </div>
                </div>
                
                <div class="project-card fade-in">
                    <div class="project-image">📊</div>
                    <div class="project-content">
                        <h3 class="project-title">Data Analytics Dashboard</h3>
                        <p class="project-description">
                            Interactive dashboard for data visualization and analysis using Python and Excel. 
                            Features automated reporting and real-time data processing.
                        </p>
                        <div class="project-tech">
                            <span class="tech-tag">Python</span>
                            <span class="tech-tag">Excel</span>
                            <span class="tech-tag">Data Viz</span>
                            <span class="tech-tag">Analytics</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">Demo</a>
                            <a href="#" class="project-link">Code</a>
                        </div>
                    </div>
                </div>
                
                <div class="project-card fade-in">
                    <div class="project-image">🌐</div>
                    <div class="project-content">
                        <h3 class="project-title">Modern Portfolio</h3>
                        <p class="project-description">
                            A fully responsive portfolio website with modern design principles, 
                            smooth animations, and optimized performance across all devices.
                        </p>
                        <div class="project-tech">
                            <span class="tech-tag">HTML5</span>
                            <span class="tech-tag">CSS3</span>
                            <span class="tech-tag">JavaScript</span>
                            <span class="tech-tag">Responsive</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">View Live</a>
                            <a href="#" class="project-link">Source</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="experience" class="section">
        <div class="container">
            <h2 class="section-title fade-in">Experience & Journey</h2>
            <p class="section-subtitle fade-in">My professional and academic milestones</p>
            
            <div class="experience-timeline">
                <div class="experience-item fade-in">
                    <div class="experience-date">2023 - Present</div>
                    <div class="experience-title">Event Manager (Freelancer)</div>
                    <div class="experience-company">Playo</div>
                    <div class="experience-description">
                        Working as a freelance Event Manager, coordinating and managing various tech events. 
                        Responsible for end-to-end event planning, vendor coordination, participant management, 
                        and ensuring successful event execution with 95% satisfaction rate.
                    </div>
                </div>
                
                <div class="experience-item fade-in">
                    <div class="experience-date">2024 - 2025</div>
                    <div class="experience-title">Vice President</div>
                    <div class="experience-company">Cyber Sprint - College Club</div>
                    <div class="experience-description">
                        Elected as VP of Cyber Sprint, leading cybersecurity and technology initiatives. 
                        Organized multiple workshops, managed club activities, and mentored 50+ junior members 
                        in cybersecurity practices and emerging technology trends.
                    </div>
                </div>
                
                <div class="experience-item fade-in">
                    <div class="experience-date">2023 - 2025</div>
                    <div class="experience-title">UI/UX Designer Intern</div>
                    <div class="experience-company">BGR Technologies</div>
                    <div class="experience-description">
                        Contributed to the development of Kreeda Bookings, a responsive web platform for sports venue bookings. 
                        Designed user-centric, interactive mobile-first features that enhanced user engagement by 20% 
                        and improved conversion rates.
                    </div>
                </div>
                
                <div class="experience-item fade-in">
                    <div class="experience-date">2022 - 2025</div>
                    <div class="experience-title">Bachelor of Computer Application</div>
                    <div class="experience-company">Bangalore University</div>
                    <div class="experience-description">
                        Pursuing BCA with strong foundation in programming, web development, data structures, 
                        and software engineering. Active participant in tech events, coding competitions, 
                        and hackathons with consistent top performance.
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="section">
        <div class="container">
            <h2 class="section-title fade-in">Get In Touch</h2>
            <p class="section-subtitle fade-in">Let's connect and build something amazing together</p>
            
            <div class="contact-grid">
                <div class="contact-card fade-in">
                    <div class="contact-icon">📧</div>
                    <h3 class="contact-title">Email</h3>
                    <div class="contact-info">
                        <a href="mailto:sujanroopesh@gmail.com">sujanroopesh@gmail.com</a>
                    </div>
                </div>
                
                <div class="contact-card fade-in">
                    <div class="contact-icon">📱</div>
                    <h3 class="contact-title">Phone</h3>
                    <div class="contact-info">
                        <a href="tel:+919742554890">+91 9742554890</a>
                    </div>
                </div>
                
                <div class="contact-card fade-in">
                    <div class="contact-icon">📍</div>
                    <h3 class="contact-title">Location</h3>
                    <div class="contact-info">
                        Anekal, Bengaluru<br>
                        Karnataka 560106
                    </div>
                </div>
                
                <div class="contact-card fade-in">
                    <div class="contact-icon">💼</div>
                    <h3 class="contact-title">LinkedIn</h3>
                    <div class="contact-info">
                        <a href="https://www.linkedin.com/in/roopesh-n-bba190254" target="_blank">Connect with me</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <script>
        // Mobile menu toggle
        function toggleMobileMenu() {
            const toggle = document.querySelector('.mobile-menu-toggle');
            const menu = document.getElementById('navMenu');
            
            toggle.classList.toggle('active');
            menu.classList.toggle('active');
        }

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const targetId = this.getAttribute('href');
                const targetSection = document.querySelector(targetId);
                
                if (targetSection) {
                    targetSection.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
                
                // Close mobile menu after clicking
                document.querySelector('.mobile-menu-toggle').classList.remove('active');
                document.getElementById('navMenu').classList.remove('active');
            });
        });

        // Scroll progress indicator
        window.addEventListener('scroll', () => {
            const scrollTop = window.pageYOffset;
            const docHeight = document.body.scrollHeight - window.innerHeight;
            const scrollPercent = (scrollTop / docHeight) * 100;
            
            document.querySelector('.scroll-progress').style.width = scrollPercent + '%';
        });

        // Active navigation highlighting
        window.addEventListener('scroll', () => {
            const sections = document.querySelectorAll('section');
            const navLinks = document.querySelectorAll('.nav-link');
            
            let current = '';
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                if (scrollY >= sectionTop - 200) {
                    current = section.getAttribute('id');
                }
            });
            
            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href') === '#' + current) {
                    link.classList.add('active');
                }
            });
        });

        // Intersection Observer for animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        // Observe all fade-in elements
        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });

        // Animate skill bars when visible
        const skillObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const progressBars = entry.target.querySelectorAll('.skill-progress');
                    progressBars.forEach(bar => {
                        const width = bar.style.width;
                        bar.style.width = '0%';
                        setTimeout(() => {
                            bar.style.width = width;
                        }, 300);
                    });
                }
            });
        }, { threshold: 0.5 });

        document.querySelectorAll('.skills-grid').forEach(el => {
            skillObserver.observe(el);
        });

        // Typing effect for hero title
        function typeWriter(element, text, speed = 100) {
            element.innerHTML = '';
            let i = 0;
            
            function type() {
                if (i < text.length) {
                    element.innerHTML += text.charAt(i);
                    i++;
                    setTimeout(type, speed);
                }
            }
            type();
        }

        // Initialize typing effect
        window.addEventListener('load', () => {
            const heroTitle = document.querySelector('.hero-title');
            setTimeout(() => {
                typeWriter(heroTitle, 'ROOPESH N', 120);
            }, 500);
        });

        // Parallax effect for hero background
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const hero = document.querySelector('.hero');
            const rate = scrolled * -0.5;
            
            if (hero) {
                hero.style.transform = `translateY(${rate}px)`;
            }
        });

        // Add hover effect to cards
        document.querySelectorAll('.skill-card, .project-card, .contact-card').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-10px) scale(1.02)';
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0) scale(1)';
            });
        });

        // Smooth reveal animation for timeline items
        const timelineObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animationDelay = `${entry.target.dataset.delay || 0}s`;
                    entry.target.classList.add('visible');
                }
            });
        }, { threshold: 0.3 });

        document.querySelectorAll('.experience-item').forEach((item, index) => {
            item.dataset.delay = index * 0.2;
            timelineObserver.observe(item);
        });

        // Add loading animation
        window.addEventListener('load', () => {
            document.body.classList.add('loaded');
        });

        // Prevent horizontal scroll on mobile
        document.addEventListener('touchmove', function(e) {
            if (e.touches.length > 1) {
                e.preventDefault();
            }
        });

        // Close mobile menu when clicking outside
        document.addEventListener('click', function(e) {
            const toggle = document.querySelector('.mobile-menu-toggle');
            const menu = document.getElementById('navMenu');
            
            if (!toggle.contains(e.target) && !menu.contains(e.target)) {
                toggle.classList.remove('active');
                menu.classList.remove('active');
            }
        });
    </script>
</body>
</html>
