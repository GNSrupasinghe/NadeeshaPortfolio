<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nadeesha Rupasinghe - Software Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            color: #e0e0e0;
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f0f23 100%);
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Animated Background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f0f23 100%);
        }

        .floating-shapes {
            position: absolute;
            width: 100%;
            height: 100%;
        }

        .shape {
            position: absolute;
            opacity: 0.05;
            animation: float 6s ease-in-out infinite;
        }

        .shape:nth-child(1) {
            top: 10%;
            left: 10%;
            width: 80px;
            height: 80px;
            background: #00d4ff;
            border-radius: 50%;
            animation-delay: 0s;
        }

        .shape:nth-child(2) {
            top: 20%;
            right: 10%;
            width: 60px;
            height: 60px;
            background: #ff6b6b;
            transform: rotate(45deg);
            animation-delay: 1s;
        }

        .shape:nth-child(3) {
            bottom: 10%;
            left: 20%;
            width: 100px;
            height: 100px;
            background: #4ecdc4;
            clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
            animation-delay: 2s;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(10deg); }
        }

        /* Header */
        header {
            background: rgba(26, 26, 46, 0.9);
            backdrop-filter: blur(10px);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            transition: all 0.3s ease;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: #00d4ff;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: #e0e0e0;
            text-decoration: none;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: #00d4ff;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: #00d4ff;
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #e0e0e0;
            position: relative;
        }

        .hero-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
            width: 100%;
            max-width: 1200px;
        }

        .hero-content {
            text-align: left;
        }

        .hero-content h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            animation: slideInDown 1s ease-out;
            background: linear-gradient(135deg, #00d4ff, #ff6b6b);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            line-height: 1.2;
        }

        .hero-content .subtitle {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.9;
            animation: slideInUp 1s ease-out 0.3s both;
            color: #4ecdc4;
        }

        .hero-content p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            animation: fadeIn 1s ease-out 0.6s both;
            color: #b0b0b0;
            line-height: 1.6;
        }

        .hero-image {
            display: flex;
            justify-content: center;
            align-items: center;
            animation: slideInRight 1s ease-out 0.3s both;
        }

        .profile-image {
            width: 350px;
            height: 350px;
            border-radius: 50%;
            border: 4px solid #00d4ff;
            box-shadow: 0 0 30px rgba(0, 212, 255, 0.3);
            object-fit: cover;
            transition: all 0.3s ease;
            background: linear-gradient(135deg, #00d4ff, #4ecdc4);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 6rem;
            color: #1a1a2e;
        }

        .profile-image:hover {
            transform: scale(1.05);
            box-shadow: 0 0 40px rgba(0, 212, 255, 0.5);
        }

        .cta-buttons {
            display: flex;
            gap: 1rem;
            animation: fadeIn 1s ease-out 0.9s both;
        }

        .btn {
            padding: 12px 30px;
            border: none;
            border-radius: 50px;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
        }

        .btn-primary {
            background: linear-gradient(135deg, #00d4ff, #4ecdc4);
            color: #1a1a2e;
            font-weight: bold;
        }

        .btn-secondary {
            background: transparent;
            color: #e0e0e0;
            border: 2px solid #00d4ff;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 212, 255, 0.3);
        }

        .btn-secondary:hover {
            background: #00d4ff;
            color: #1a1a2e;
        }

        /* Sections */
        section {
            padding: 5rem 0;
            background: rgba(22, 33, 62, 0.8);
            margin: 2rem 0;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #e0e0e0;
            position: relative;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background: linear-gradient(135deg, #00d4ff, #4ecdc4);
            margin: 1rem auto;
            border-radius: 2px;
        }

        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .skill-card {
            background: linear-gradient(135deg, #2a2a4e 0%, #1e1e3f 100%);
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            color: #e0e0e0;
            transition: transform 0.3s ease;
            cursor: pointer;
            border: 1px solid rgba(0, 212, 255, 0.2);
        }

        .skill-card:hover {
            transform: translateY(-10px);
            border-color: #00d4ff;
            box-shadow: 0 15px 30px rgba(0, 212, 255, 0.2);
        }

        .skill-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .skill-card h3 {
            margin-bottom: 1rem;
            color: #00d4ff;
        }

        .skill-list {
            list-style: none;
        }

        .skill-list li {
            margin: 0.5rem 0;
            opacity: 0.9;
            color: #b0b0b0;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .project-card {
            background: rgba(26, 26, 46, 0.9);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            transition: transform 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0, 212, 255, 0.2);
            border-color: #00d4ff;
        }

        .project-image {
            height: 200px;
            background: linear-gradient(135deg, #00d4ff 0%, #4ecdc4 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: #1a1a2e;
        }

        .project-content {
            padding: 2rem;
        }

        .project-content h3 {
            margin-bottom: 1rem;
            color: #00d4ff;
        }

        .project-content p {
            color: #b0b0b0;
            margin-bottom: 1rem;
        }

        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin: 1rem 0;
        }

        .tech-tag {
            background: rgba(0, 212, 255, 0.2);
            color: #00d4ff;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            border: 1px solid rgba(0, 212, 255, 0.3);
        }

        /* Contact Section */
        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }

        .contact-info h3 {
            margin-bottom: 2rem;
            color: #00d4ff;
        }

        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 1rem;
            padding: 1rem;
            background: rgba(26, 26, 46, 0.8);
            border-radius: 10px;
            transition: background 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .contact-item:hover {
            background: rgba(42, 42, 78, 0.8);
            border-color: #00d4ff;
        }

        .contact-icon {
            font-size: 1.5rem;
            margin-right: 1rem;
            color: #00d4ff;
        }

        .contact-item a {
            color: #4ecdc4;
            text-decoration: none;
        }

        .contact-item a:hover {
            color: #00d4ff;
        }

        .contact-form {
            background: rgba(26, 26, 46, 0.8);
            padding: 2rem;
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .contact-form h3 {
            color: #00d4ff;
            margin-bottom: 1.5rem;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: #e0e0e0;
            font-weight: bold;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            border: 2px solid rgba(255, 255, 255, 0.2);
            border-radius: 10px;
            font-size: 1rem;
            transition: border-color 0.3s ease;
            background: rgba(42, 42, 78, 0.8);
            color: #e0e0e0;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #00d4ff;
            box-shadow: 0 0 10px rgba(0, 212, 255, 0.3);
        }

        .form-group input::placeholder,
        .form-group textarea::placeholder {
            color: #888;
        }

        /* Animations */
        @keyframes slideInDown {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes slideInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .hero-container {
                grid-template-columns: 1fr;
                gap: 2rem;
                text-align: center;
            }

            .hero-content {
                text-align: center;
            }

            .hero-content h1 {
                font-size: 2.5rem;
            }

            .profile-image {
                width: 250px;
                height: 250px;
                font-size: 4rem;
            }

            .nav-links {
                display: none;
            }

            .cta-buttons {
                flex-direction: column;
                align-items: center;
                justify-content: center;
            }

            .contact-content {
                grid-template-columns: 1fr;
            }

            .skills-grid,
            .projects-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Scroll animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.6s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Scrollbar styling */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: #1a1a2e;
        }

        ::-webkit-scrollbar-thumb {
            background: #00d4ff;
            border-radius: 4px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: #4ecdc4;
        }
    </style>
</head>
<body>
    <div class="bg-animation">
        <div class="floating-shapes">
            <div class="shape"></div>
            <div class="shape"></div>
            <div class="shape"></div>
        </div>
    </div>

    <header>
        <div class="container">
            <nav>
                <div class="logo">Nadeesha.dev</div>
                <ul class="nav-links">
                    <li><a href="#home">Home</a></li>
                    <li><a href="#skills">Skills</a></li>
                    <li><a href="#projects">Projects</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <section id="home" class="hero">
        <div class="container">
            <div class="hero-container">
                <div class="hero-content">
                    <h1>Nadeesha Rupasinghe</h1>
                    <div class="subtitle">Software Developer Intern</div>
                    <p>I am an enthusiastic undergraduate passionate about web development and innovation. I thrive in dynamic environments, love problem-solving, and seek opportunities to collaborate and make a meaningful impact through technology.</p>
                    <div class="cta-buttons">
                        <a href="#projects" class="btn btn-primary">View My Work</a>
                        <a href="#contact" class="btn btn-secondary">Get In Touch</a>
                    </div>
                </div>
                <div class="hero-image">
                    <img src="images/profile.png" alt="Nadeesha Rupasinghe" class="profile-image" 
                         onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                    
                    </div>
                </div>
            </div>
        </div>
    </section>

    <div class="container">
        <section id="skills" class="fade-in">
            <h2 class="section-title">Technical Skills</h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <div class="skill-icon">💻</div>
                    <h3>Programming</h3>
                    <ul class="skill-list">
                        <li>Java - Application Development</li>
                        <li>C - System Programming</li>
                        <li>JavaScript - Full Stack</li>
                        <li>PHP - Web Development</li>
                        <li>Python - Automation</li>
                    </ul>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">📱</div>
                    <h3>Mobile Development</h3>
                    <ul class="skill-list">
                        <li>React Native</li>
                        <li>Flutter</li>
                        <li>Android Development</li>
                        <li>Cross-Platform Apps</li>
                        <li>API Integration</li>
                    </ul>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">🌐</div>
                    <h3>Web Technologies</h3>
                    <ul class="skill-list">
                        <li>HTML5 & CSS3</li>
                        <li>Responsive Design</li>
                        <li>Frontend Development</li>
                        <li>UI/UX Implementation</li>
                        <li>Modern Web Standards</li>
                    </ul>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">🗄️</div>
                    <h3>Database & Tools</h3>
                    <ul class="skill-list">
                        <li>MySQL - Database Design</li>
                        <li>Firebase - Real-time DB</li>
                        <li>Git Version Control</li>
                        <li>Agile Methodologies</li>
                        <li>Testing (Manual & Selenium)</li>
                    </ul>
                </div>
            </div>
        </section>

        <section id="projects" class="fade-in">
            <h2 class="section-title">Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-image">🚗</div>
                    <div class="project-content">
                        <h3>Vehicle Management System</h3>
                        <p>Comprehensive tracking system with real-time GPS coordinates, developed during internship at District Secretariat Matale.</p>
                        <div class="tech-stack">
                            <span class="tech-tag">Java</span>
                            <span class="tech-tag">React Native</span>
                            <span class="tech-tag">MySQL</span>
                            <span class="tech-tag">GPS</span>
                            <span class="tech-tag">Android</span>
                        </div>
                        <p><strong>Key Features:</strong> Real-time tracking, database optimization, full-stack implementation</p>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">🔧</div>
                    <div class="project-content">
                        <h3>Vehicle Service Support App</h3>
                        <p>Data-driven mobile application connecting car owners with service centers using intelligent matching algorithms.</p>
                        <div class="tech-stack">
                            <span class="tech-tag">Flutter</span>
                            <span class="tech-tag">Firebase</span>
                            <span class="tech-tag">Google Maps API</span>
                            <span class="tech-tag">Figma</span>
                        </div>
                        <p><strong>Key Features:</strong> User authentication, real-time notifications, service matching, scheduling optimization</p>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">🛒</div>
                    <div class="project-content">
                        <h3>T-Store E-commerce Platform</h3>
                        <p>Collaborative e-commerce solution with focus on order processing functionality and user experience.</p>
                        <div class="tech-stack">
                            <span class="tech-tag">Web Technologies</span>
                            <span class="tech-tag">Database</span>
                            <span class="tech-tag">Order Processing</span>
                            <span class="tech-tag">Team Project</span>
                        </div>
                        <p><strong>Key Features:</strong> Order management, payment processing, inventory system</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="contact" class="fade-in">
            <h2 class="section-title">Let's Connect</h2>
            <div class="contact-content">
                <div class="contact-info">
                    <h3>Get In Touch</h3>
                    <div class="contact-item">
                        <div class="contact-icon">📧</div>
                        <div>
                            <strong>Email</strong><br>
                            nadeeshar48@gmail.com
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">📱</div>
                        <div>
                            <strong>Phone</strong><br>
                            +94 76 963 5208 
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">💼</div>
                        <div>
                            <strong>LinkedIn</strong><br>
                            <a href="https://lk.linkedin.com/in/nadeesha-rupasinghe-026898358" target="_blank">nadeesha-rupasinghe</a>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">💻</div>
                        <div>
                            <strong>GitHub</strong><br>
                            <a href="https://github.com/GNSrupasinghe" target="_blank">GNSrupasinghe</a>
                        </div>
                    </div>
                </div>
                <div class="contact-form">
                    <h3>Send a Message</h3>
                    <form>
                        <div class="form-group">
                            <label for="name">Name</label>
                            <input type="text" id="name" name="name" required>
                        </div>
                        <div class="form-group">
                            <label for="email">Email</label>
                            <input type="email" id="email" name="email" required>
                        </div>
                        <div class="form-group">
                            <label for="message">Message</label>
                            <textarea id="message" name="message" rows="5" required></textarea>
                        </div>
                        <button type="submit" class="btn btn-primary" style="width: 100%;">Send Message</button>
                    </form>
                </div>
            </div>
        </section>
    </div>

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

        // Scroll animations
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

        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });

        // Header background on scroll
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.background = 'rgba(26, 26, 46, 0.95)';
            } else {
                header.style.background = 'rgba(26, 26, 46, 0.9)';
            }
        });

        // Form submission
        document.querySelector('form').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Thank you for your message! I\'ll get back to you soon.');
            this.reset();
        });

        // Add interactive hover effects
        document.querySelectorAll('.skill-card, .project-card').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-10px) scale(1.02)';
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0) scale(1)';
            });
        });
    </script>
</body>
</html>
