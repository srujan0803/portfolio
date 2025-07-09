<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Roopesh N - Frontend Developer & Data Analyst</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        /* Mobile-first Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            padding: 10px 0;
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: #667eea;
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 20px;
        }

        .nav-menu a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s ease;
            padding: 5px 10px;
            border-radius: 5px;
        }

        .nav-menu a:hover {
            background: rgba(102, 126, 234, 0.1);
            color: #667eea;
        }

        .hamburger {
            display: none;
            flex-direction: column;
            cursor: pointer;
            padding: 5px;
        }

        .hamburger span {
            width: 25px;
            height: 3px;
            background: #333;
            margin: 3px 0;
            transition: 0.3s;
        }

        /* Hero Section - Mobile Optimized */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            padding: 80px 20px 40px;
        }

        .hero-content {
            max-width: 600px;
            animation: fadeInUp 1s ease-out;
        }

        .hero h1 {
            font-size: clamp(2rem, 8vw, 4rem);
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .hero p {
            font-size: clamp(1rem, 4vw, 1.5rem);
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .btn {
            display: inline-block;
            padding: 15px 30px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            font-size: 1rem;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.3);
        }

        /* Section Styles - Mobile Optimized */
        .section {
            padding: 60px 0;
            background: white;
        }

        .section:nth-child(even) {
            background: #f8f9fa;
        }

        .section h2 {
            text-align: center;
            font-size: clamp(1.8rem, 5vw, 2.5rem);
            margin-bottom: 2rem;
            color: #333;
            position: relative;
            padding-bottom: 15px;
        }

        .section h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 3px;
            background: linear-gradient(45deg, #667eea, #764ba2);
        }

        /* About Section - Mobile Optimized */
        .about-content {
            display: flex;
            flex-direction: column;
            gap: 2rem;
            align-items: center;
        }

        .profile-card {
            background: white;
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            text-align: center;
            transition: transform 0.3s ease;
            width: 100%;
            max-width: 400px;
        }

        .profile-card:hover {
            transform: translateY(-5px);
        }

        .profile-avatar {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            margin: 0 auto 1rem;
            overflow: hidden;
            border: 4px solid;
            border-image: linear-gradient(45deg, #667eea, #764ba2) 1;
        }

        .profile-avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
            text-align: left;
            max-width: 800px;
        }

        .about-text p {
            margin-bottom: 1.5rem;
        }

        /* Skills Section - Mobile Grid */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .skill-card {
            background: white;
            padding: 1.5rem;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            text-align: center;
            transition: all 0.3s ease;
        }

        .skill-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .skill-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .skill-card h3 {
            margin-bottom: 0.5rem;
            font-size: 1.2rem;
        }

        .skill-card p {
            font-size: 0.9rem;
            color: #666;
        }

        /* Projects Section - Mobile Optimized */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .project-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }

        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .project-header {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            padding: 1.5rem;
            text-align: center;
        }

        .project-header h3 {
            margin-bottom: 0.5rem;
            font-size: 1.3rem;
        }

        .project-content {
            padding: 1.5rem;
        }

        .project-content p {
            margin-bottom: 1rem;
            font-size: 0.95rem;
            line-height: 1.6;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
        }

        .tech-tag {
            background: #e9ecef;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            color: #495057;
        }

        /* Experience Section - Mobile Timeline */
        .experience-timeline {
            position: relative;
            padding-left: 1.5rem;
            margin-top: 2rem;
        }

        .experience-timeline::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            bottom: 0;
            width: 2px;
            background: linear-gradient(45deg, #667eea, #764ba2);
        }

        .experience-item {
            position: relative;
            margin-bottom: 2rem;
            background: white;
            padding: 1.5rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            margin-left: 1rem;
        }

        .experience-item::before {
            content: '';
            position: absolute;
            left: -1.5rem;
            top: 1.5rem;
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: #667eea;
        }

        .experience-date {
            color: #667eea;
            font-weight: bold;
            margin-bottom: 0.5rem;
            font-size: 0.9rem;
        }

        .experience-title {
            font-size: 1.2rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
        }

        .experience-company {
            color: #666;
            margin-bottom: 1rem;
            font-style: italic;
        }

        .experience-item p {
            font-size: 0.95rem;
            line-height: 1.6;
        }

        /* Contact Section - Mobile Grid */
        .contact-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .contact-item {
            background: white;
            padding: 1.5rem;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            text-align: center;
            transition: transform 0.3s ease;
        }

        .contact-item:hover {
            transform: translateY(-5px);
        }

        .contact-icon {
            font-size: 2rem;
            margin-bottom: 1rem;
        }

        .contact-item h3 {
            margin-bottom: 0.5rem;
            font-size: 1.1rem;
        }

        .contact-item p {
            font-size: 0.9rem;
            color: #666;
            word-break: break-all;
        }

        /* Mobile Responsive Styles */
        @media (max-width: 768px) {
            .nav-menu {
                position: fixed;
                left: -100%;
                top: 70px;
                flex-direction: column;
                background-color: rgba(255, 255, 255, 0.98);
                width: 100%;
                text-align: center;
                transition: 0.3s;
                box-shadow: 0 10px 27px rgba(0, 0, 0, 0.05);
                padding: 20px 0;
            }

            .nav-menu.active {
                left: 0;
            }

            .nav-menu li {
                margin: 15px 0;
            }

            .nav-menu a {
                padding: 10px 20px;
                display: block;
            }

            .hamburger {
                display: flex;
            }

            .hamburger.active span:nth-child(2) {
                opacity: 0;
            }

            .hamburger.active span:nth-child(1) {
                transform: translateY(8px) rotate(45deg);
            }

            .hamburger.active span:nth-child(3) {
                transform: translateY(-8px) rotate(-45deg);
            }

            .hero {
                padding: 100px 20px 40px;
            }

            .section {
                padding: 40px 0;
            }

            .about-content {
                gap: 1.5rem;
            }

            .skills-grid {
                grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
                gap: 1rem;
            }

            .projects-grid {
                grid-template-columns: 1fr;
                gap: 1.5rem;
            }

            .experience-timeline {
                padding-left: 1rem;
            }

            .experience-item {
                margin-left: 0.5rem;
                padding: 1rem;
            }

            .contact-info {
                grid-template-columns: 1fr;
                gap: 1rem;
            }

            .profile-avatar {
                width: 100px;
                height: 100px;
            }
        }

        @media (max-width: 480px) {
            .container {
                padding: 0 10px;
            }

            .nav-container {
                padding: 0 15px;
            }

            .hero {
                padding: 80px 15px 30px;
            }

            .section {
                padding: 30px 0;
            }

            .btn {
                padding: 12px 24px;
                font-size: 0.9rem;
            }

            .skill-card, .project-card, .contact-item {
                padding: 1rem;
            }

            .experience-item {
                padding: 1rem;
            }

            .about-text {
                font-size: 1rem;
            }
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

        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Touch-friendly buttons */
        @media (hover: none) {
            .btn:hover {
                transform: none;
            }
            
            .skill-card:hover,
            .project-card:hover,
            .contact-item:hover,
            .profile-card:hover {
                transform: none;
            }
        }
    </style>
</head>
<body>
    <nav>
        <div class="nav-container">
            <div class="logo">Roopesh N</div>
            <ul class="nav-menu">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#experience">Experience</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="hamburger">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <section id="home" class="hero">
        <div class="hero-content">
            <h1>ROOPESH N</h1>
            <p>Aspiring Frontend Developer | Data Analyst</p>
            <a href="#about" class="btn">Explore My Journey</a>
        </div>
    </section>

    <section id="about" class="section">
        <div class="container">
            <h2>About Me</h2>
            <div class="about-content">
                <div class="profile-card fade-in">
                    <div class="profile-avatar">
                        <img id="profileImage" src="" alt="Roopesh N" />
                    </div>
                    <h3>Roopesh N</h3>
                    <p>Frontend Developer & Data Analyst</p>
                    <p>📍 Anekkal, Bengaluru 560106</p>
                    <p>📧 sujanroopesh@gmail.com</p>
                    <p>📱 9742554890</p>
                </div>
                <div class="about-text fade-in">
                    <p>Aspiring UI/UX Designer, adept in HTML, CSS, and JavaScript, who excels in teamwork and collaboration. Developed user-centered digital solutions, enhancing user engagement by 20%. A fast learner with strong problem-solving skills, committed to delivering innovative designs and effective solutions.</p>
                    
                    <p>Currently pursuing Bachelor of Computer Application from Bangalore University, I have developed a strong foundation in programming, web development, data structures, and software engineering. I'm skilled in problem-solving, UI/UX design, and emerging technologies.</p>
                    
                    <p>Beyond academics, I've taken on leadership roles including serving as VP of Cyber Sprint in college, organizing the successful tech event "Techkrithi", and working as a freelance Event Manager at Playo, where I coordinate and manage various tech events.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="skills" class="section">
        <div class="container">
            <h2>Skills & Technologies</h2>
            <div class="skills-grid">
                <div class="skill-card fade-in">
                    <div class="skill-icon">🎨</div>
                    <h3>UI/UX Design</h3>
                    <p>Creating user-centered designs with focus on usability and aesthetics</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">📊</div>
                    <h3>Data Analysis</h3>
                    <p>Analyzing data patterns and creating insights for better decision making</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">🐍</div>
                    <h3>Python</h3>
                    <p>Programming and automation with Python for various applications</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">🔧</div>
                    <h3>Teamwork</h3>
                    <p>Excellent collaboration skills with proven leadership experience</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">📈</div>
                    <h3>Advanced Excel</h3>
                    <p>Data manipulation and analysis using advanced Excel functions</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">🧠</div>
                    <h3>Problem Solving</h3>
                    <p>Strong analytical thinking and creative problem-solving approach</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">💻</div>
                    <h3>JavaScript</h3>
                    <p>Interactive web development and frontend functionality</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">🌐</div>
                    <h3>Git/GitHub</h3>
                    <p>Version control and collaborative development workflows</p>
                </div>
            </div>
        </div>
    </section>

    <section id="projects" class="section">
        <div class="container">
            <h2>Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card fade-in">
                    <div class="project-header">
                        <h3>Kreeda Bookings</h3>
                        <p>Sports Facility Booking Platform</p>
                    </div>
                    <div class="project-content">
                        <p>As a UI/UX Designer intern at BGR Technologies, I contributed to the development of Kreeda Bookings, a responsive web platform for booking sports venues. I designed user-centric, interactive mobile-first features such as booking management, facility browsing, and user authentication.</p>
                        <div class="project-tech">
                            <span class="tech-tag">HTML</span>
                            <span class="tech-tag">CSS</span>
                            <span class="tech-tag">JavaScript</span>
                            <span class="tech-tag">Bootstrap</span>
                            <span class="tech-tag">UI/UX Design</span>
                        </div>
                    </div>
                </div>
                <div class="project-card fade-in">
                    <div class="project-header">
                        <h3>Techkrithi Event</h3>
                        <p>Tech Event Organization</p>
                    </div>
                    <div class="project-content">
                        <p>Successfully organized and managed "Techkrithi", a comprehensive tech event at college. Led a team of volunteers, coordinated with speakers, managed logistics, and ensured smooth execution of multiple technical workshops and competitions.</p>
                        <div class="project-tech">
                            <span class="tech-tag">Event Management</span>
                            <span class="tech-tag">Leadership</span>
                            <span class="tech-tag">Team Coordination</span>
                            <span class="tech-tag">Project Management</span>
                        </div>
                    </div>
                </div>
                <div class="project-card fade-in">
                    <div class="project-header">
                        <h3>Data Analysis Projects</h3>
                        <p>Python & Excel Analytics</p>
                    </div>
                    <div class="project-content">
                        <p>Developed various data analysis projects using Python and Advanced Excel, focusing on extracting meaningful insights from complex datasets. Created interactive dashboards and automated reporting systems.</p>
                        <div class="project-tech">
                            <span class="tech-tag">Python</span>
                            <span class="tech-tag">Excel</span>
                            <span class="tech-tag">Data Visualization</span>
                            <span class="tech-tag">Statistical Analysis</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="experience" class="section">
        <div class="container">
            <h2>Experience & Leadership</h2>
            <div class="experience-timeline">
                <div class="experience-item fade-in">
                    <div class="experience-date">2023-Present</div>
                    <div class="experience-title">Event Manager (Freelancer)</div>
                    <div class="experience-company">Playo</div>
                    <p>Working as a freelance Event Manager, coordinating and managing various tech events. Responsible for event planning, vendor coordination, participant management, and ensuring successful event execution.</p>
                </div>
                <div class="experience-item fade-in">
                    <div class="experience-date">2024-2025</div>
                    <div class="experience-title">Vice President</div>
                    <div class="experience-company">Cyber Sprint - College Club</div>
                    <p>Elected as VP of Cyber Sprint, leading cybersecurity and technology initiatives. Organized workshops, managed club activities, and mentored junior members in cybersecurity practices and technology trends.</p>
                </div>
                <div class="experience-item fade-in">
                    <div class="experience-date">2024-2025</div>
                    <div class="experience-title">UI/UX Designer Intern</div>
                    <div class="experience-company">BGR Technologies</div>
                    <p>Contributed to the development of Kreeda Bookings, a responsive web platform for booking sports venues. Designed user-centric, interactive mobile-first features and enhanced user engagement by 20%.</p>
                </div>
                <div class="experience-item fade-in">
                    <div class="experience-date">2022-2025</div>
                    <div class="experience-title">Student</div>
                    <div class="experience-company">Bangalore University - BCA</div>
                    <p>Pursuing Bachelor of Computer Application with strong foundation in programming, web development, data structures, and software engineering. Active participant in tech events and coding competitions.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="section">
        <div class="container">
            <h2>Let's Connect</h2>
            <div class="contact-info">
                <div class="contact-item fade-in">
                    <div class="contact-icon">📧</div>
                    <h3>Email</h3>
                    <p>sujanroopesh@gmail.com</p>
                </div>
                <div class="contact-item fade-in">
                    <div class="contact-icon">📱</div>
                    <h3>Phone</h3>
                    <p>9742554890</p>
                </div>
                <div class="contact-item fade-in">
                    <div class="contact-icon">📍</div>
                    <h3>Location</h3>
                    <p>Anekal, Bengaluru 560106</p>
                </div>
                <div class="contact-item fade-in">
                    <div class="contact-icon">💼</div>
                    <h3>LinkedIn</h3>
                    <p>linkedin.com/in/roopesh-n-bba902547</p>
                </div>
            </div>
        </div>
    </section>

    <script>
        // Mobile menu toggle
        const hamburger = document.querySelector('.hamburger');
        const navMenu = document.querySelector('.nav-menu');

        hamburger.addEventListener('click', () => {
            hamburger.classList.toggle('active');
            navMenu.classList.toggle('active');
        });

        // Close menu when clicking on a link
        document.querySelectorAll('.nav-menu a').forEach(link => {
            link.addEventListener('click', () => {
                hamburger.classList.remove('active');
                navMenu.classList.remove('active');
            });
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Fade in animation on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });

        // Load profile image
        async function loadProfileImage() {
            try {
                const imageData = await window.fs.readFile('image.png');
                const blob = new Blob([imageData], { type: 'image/png' });
                const imageUrl = URL.createObjectURL(blob);
                document.getElementById('profileImage').src = imageUrl;
            } catch (error) {
                console.log('Image not found, using fallback');
                // Fallback to initials if image can't be loaded
                const profileAvatar = document.querySelector('.profile-avatar');
                profileAvatar.innerHTML = '<div style="display: flex; align-items: center; justify-content: center; width: 100%; height: 100%; background: linear-gradient(45deg, #667eea, #764ba2); font-size: 2rem; color: white; font-weight: bold; border-radius: 50%;">RN</div>';
            }
        }

        // Initialize when page loads
        window.addEventListener('load', function() {
            loadProfileImage();
        });

        // Add touch event handling for better mobile interaction
        if ('ontouchstart' in window) {
            document.addEventListener('touchstart', function() {}, true);
        }
    </script>
</body>
</html>
