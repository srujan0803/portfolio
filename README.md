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
            padding: 0 20px;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            transition: all 0.3s ease;
        }

        nav.scrolled {
            box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
        }

        nav ul {
            list-style: none;
            display: flex;
            justify-content: center;
            padding: 1rem 0;
        }

        nav ul li {
            margin: 0 1.5rem;
        }

        nav ul li a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s ease;
            position: relative;
        }

        nav ul li a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: #667eea;
            transition: width 0.3s ease;
        }

        nav ul li a:hover::after {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
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
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000"><polygon fill="%23ffffff10" points="0,0 1000,300 1000,1000 0,700"/></svg>');
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .hero-content {
            position: relative;
            z-index: 2;
            animation: fadeInUp 1s ease-out;
        }

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

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .hero p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.3);
        }

        /* Section Styles */
        .section {
            padding: 80px 0;
            background: white;
        }

        .section:nth-child(even) {
            background: #f8f9fa;
        }

        .section h2 {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #333;
            position: relative;
        }

        .section h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 3px;
            background: linear-gradient(45deg, #667eea, #764ba2);
        }

        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 3rem;
            align-items: center;
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
        }

        .profile-card {
            background: white;
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            text-align: center;
            transition: transform 0.3s ease;
        }

        .profile-card:hover {
            transform: translateY(-10px);
        }

        .profile-avatar {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: linear-gradient(45deg, #667eea, #764ba2);
            margin: 0 auto 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: white;
            font-weight: bold;
        }

        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .skill-card {
            background: white;
            padding: 2rem;
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
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: linear-gradient(45deg, #667eea, #764ba2);
            margin: 0 auto 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: white;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
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

        .project-content {
            padding: 1.5rem;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-top: 1rem;
        }

        .tech-tag {
            background: #e9ecef;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.9rem;
            color: #495057;
        }

        /* Experience Section */
        .experience-timeline {
            position: relative;
            padding-left: 2rem;
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
        }

        .experience-title {
            font-size: 1.2rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
        }

        .experience-company {
            color: #666;
            margin-bottom: 1rem;
        }

        /* Contact Section */
        .contact-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            text-align: center;
        }

        .contact-item {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
        }

        .contact-item:hover {
            transform: translateY(-5px);
        }

        .contact-icon {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: linear-gradient(45deg, #667eea, #764ba2);
            margin: 0 auto 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: white;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1.2rem;
            }

            .about-content {
                grid-template-columns: 1fr;
                text-align: center;
            }

            nav ul {
                flex-wrap: wrap;
            }

            nav ul li {
                margin: 0.5rem;
            }
        }

        /* Scroll animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Particles background */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: rgba(255, 255, 255, 0.5);
            border-radius: 50%;
            animation: float-particle 8s infinite linear;
        }

        @keyframes float-particle {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(-100px) rotate(360deg);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <div class="particles" id="particles"></div>

    <nav id="navbar">
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#skills">Skills</a></li>
            <li><a href="#projects">Projects</a></li>
            <li><a href="#experience">Experience</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
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
                    <div class="profile-avatar">RN</div>
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
                    <div class="experience-date">2023-2025</div>
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
                    <p>Anekal, Bengaluru 562106</p>
                </div>
                <div class="contact-item fade-in">
                    <div class="contact-icon">💼</div>
                    <h3>LinkedIn</h3>
                    <p><a href="https://www.linkedin.com/in/roopesh-n-bba190254?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=ios_app"></a></p>
                </div>
            </div>
        </div>
    </section>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Navbar scroll effect
        window.addEventListener('scroll', function() {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
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

        // Particle animation
        function createParticle() {
            const particle = document.createElement('div');
            particle.classList.add('particle');
            particle.style.left = Math.random() * 100 + '%';
            particle.style.animationDelay = Math.random() * 8 + 's';
            particle.style.animationDuration = (Math.random() * 3 + 5) + 's';
            document.getElementById('particles').appendChild(particle);

            setTimeout(() => {
                particle.remove();
            }, 8000);
        }

        // Create particles periodically
        setInterval(createParticle, 300);

        // Create initial particles
        for (let i = 0; i < 50; i++) {
            setTimeout(createParticle, i * 100);
        }

        // Add typing effect to hero text
        function typeWriter(element, text, speed = 100) {
            let i = 0;
            element.innerHTML = '';
            function type() {
                if (i < text.length) {
                    element.innerHTML += text.charAt(i);
                    i++;
                    setTimeout(type, speed);
                }
            }
            type();
        }

        // Initialize typing effect when page loads
        window.addEventListener('load', function() {
            const heroTitle = document.querySelector('.hero h1');
            const heroSubtitle = document.querySelector('.hero p');
            
            setTimeout(() => {
                typeWriter(heroTitle, 'ROOPESH N', 150);
            }, 500);
            
            setTimeout(() => {
                typeWriter(heroSubtitle, 'Aspiring Frontend Developer | Data Analyst', 80);
            }, 2000);
        });
    </script>
</body>
</html>
