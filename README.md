
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Yassine Idlhaj - Full Stack Developer</title>
    <meta name="description" content="Full-stack developer specializing in mobile and web apps using Laravel, Flutter, Angular, Next.js, and modern deployment solutions.">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            background: linear-gradient(135deg, #0f172a 0%, #581c87 50%, #0f172a 100%);
            color: white;
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        /* Animated background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .bg-circle {
            position: absolute;
            border-radius: 50%;
            filter: blur(60px);
            opacity: 0.2;
            animation: float 6s ease-in-out infinite;
        }

        .bg-circle:nth-child(1) {
            width: 300px;
            height: 300px;
            background: #8b5cf6;
            top: -150px;
            right: -150px;
            animation-delay: 0s;
        }

        .bg-circle:nth-child(2) {
            width: 250px;
            height: 250px;
            background: #06b6d4;
            bottom: -125px;
            left: -125px;
            animation-delay: 2s;
        }

        .bg-circle:nth-child(3) {
            width: 200px;
            height: 200px;
            background: #ec4899;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            animation-delay: 4s;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) scale(1); }
            50% { transform: translateY(-20px) scale(1.1); }
        }

        /* Header */
        header {
            text-align: center;
            padding: 4rem 0;
            opacity: 0;
            transform: translateY(30px);
            animation: fadeInUp 1s ease-out forwards;
        }

        .title {
            font-size: clamp(2.5rem, 8vw, 5rem);
            font-weight: 800;
            background: linear-gradient(45deg, #06b6d4, #8b5cf6, #ec4899);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 1rem;
            animation: pulse 2s ease-in-out infinite alternate;
        }

        .subtitle {
            font-size: clamp(1rem, 3vw, 1.5rem);
            color: #cbd5e1;
            max-width: 800px;
            margin: 0 auto 2rem;
        }

        .highlight {
            color: #06b6d4;
            font-weight: 600;
        }

        .highlight.purple {
            color: #8b5cf6;
        }

        .highlight.green {
            color: #10b981;
        }

        /* Tech Stack Grid */
        .section {
            margin: 4rem 0;
            opacity: 0;
            transform: translateY(30px);
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 700;
            text-align: center;
            margin-bottom: 3rem;
            background: linear-gradient(45deg, #06b6d4, #8b5cf6);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-bottom: 4rem;
        }

        .tech-card {
            background: rgba(30, 41, 59, 0.5);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(148, 163, 184, 0.2);
            border-radius: 1rem;
            padding: 2rem;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .tech-card:hover {
            transform: translateY(-10px) scale(1.02);
            border-color: #8b5cf6;
            box-shadow: 0 20px 40px rgba(139, 92, 246, 0.3);
        }

        .tech-header {
            display: flex;
            align-items: center;
            margin-bottom: 1.5rem;
        }

        .tech-icon {
            font-size: 2rem;
            margin-right: 1rem;
        }

        .tech-title {
            font-size: 1.5rem;
            font-weight: 700;
        }

        .tech-category {
            color: #94a3b8;
            font-size: 0.9rem;
            margin-bottom: 0.5rem;
        }

        .tech-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
        }

        .tech-tag {
            padding: 0.5rem 1rem;
            border-radius: 2rem;
            font-size: 0.8rem;
            font-weight: 500;
            color: white;
            transition: transform 0.2s ease;
        }

        .tech-tag:hover {
            transform: scale(1.1);
        }

        .tag-red { background: linear-gradient(45deg, #ef4444, #f97316); }
        .tag-green { background: linear-gradient(45deg, #10b981, #059669); }
        .tag-blue { background: linear-gradient(45deg, #3b82f6, #06b6d4); }
        .tag-purple { background: linear-gradient(45deg, #8b5cf6, #a855f7); }
        .tag-orange { background: linear-gradient(45deg, #f97316, #ea580c); }
        .tag-pink { background: linear-gradient(45deg, #ec4899, #be185d); }
        .tag-gray { background: linear-gradient(45deg, #6b7280, #4b5563); }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
        }

        .project-card {
            background: rgba(30, 41, 59, 0.5);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(148, 163, 184, 0.2);
            border-radius: 1rem;
            padding: 2rem;
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .project-card:hover {
            transform: translateY(-10px) scale(1.05);
            border-color: #06b6d4;
            box-shadow: 0 20px 40px rgba(6, 182, 212, 0.3);
        }

        .project-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            display: block;
            transition: transform 0.3s ease;
        }

        .project-card:hover .project-icon {
            transform: scale(1.2);
        }

        .project-title {
            font-size: 1.25rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            color: white;
        }

        .project-desc {
            color: #94a3b8;
            font-size: 0.9rem;
        }

        /* Contact Section */
        .contact {
            text-align: center;
            padding: 4rem 0;
        }

        .contact-text {
            font-size: 1.25rem;
            color: #cbd5e1;
            margin-bottom: 2rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
        }

        .social-link {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 60px;
            height: 60px;
            background: rgba(30, 41, 59, 0.5);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(148, 163, 184, 0.2);
            border-radius: 1rem;
            color: #94a3b8;
            text-decoration: none;
            font-size: 1.5rem;
            transition: all 0.3s ease;
        }

        .social-link:hover {
            transform: translateY(-10px) scale(1.1);
            color: white;
            box-shadow: 0 20px 40px rgba(139, 92, 246, 0.3);
        }

        .social-link.github:hover {
            border-color: #8b5cf6;
            box-shadow: 0 20px 40px rgba(139, 92, 246, 0.3);
        }

        .social-link.linkedin:hover {
            border-color: #06b6d4;
            box-shadow: 0 20px 40px rgba(6, 182, 212, 0.3);
        }

        .social-link.email:hover {
            border-color: #10b981;
            box-shadow: 0 20px 40px rgba(16, 185, 129, 0.3);
        }

        .quote {
            margin-top: 3rem;
            padding: 2rem;
            background: rgba(30, 41, 59, 0.3);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(148, 163, 184, 0.2);
            border-radius: 1rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            font-style: italic;
            color: #cbd5e1;
        }

        /* Animations */
        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            100% { transform: scale(1.02); }
        }

        .animate-on-scroll {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease-out;
        }

        .animate-on-scroll.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .container {
                padding: 0 1rem;
            }
            
            .tech-grid {
                grid-template-columns: 1fr;
            }
            
            .social-links {
                gap: 1rem;
            }
            
            .social-link {
                width: 50px;
                height: 50px;
                font-size: 1.25rem;
            }
        }
    </style>
</head>
<body>
    <div class="bg-animation">
        <div class="bg-circle"></div>
        <div class="bg-circle"></div>
        <div class="bg-circle"></div>
    </div>

    <div class="container">
        <header>
            <h1 class="title">👋 Hey, I'm YASSINE IDLHAJ</h1>
            <p class="subtitle">
                I'm a full-stack developer who builds <span class="highlight">mobile</span> and 
                <span class="highlight purple">web apps</span> using modern tools and frameworks.<br>
                Shipping code that runs <em class="highlight green">fast</em>, scales well, and actually solves problems is what I do.
            </p>
        </header>

        <section class="section animate-on-scroll">
            <h2 class="section-title">🛠️ Tech Stack</h2>
            <div class="tech-grid">
                <div class="tech-card">
                    <div class="tech-header">
                        <span class="tech-icon">💻</span>
                        <div>
                            <h3 class="tech-title" style="color: #06b6d4;">Web</h3>
                        </div>
                    </div>
                    <div class="tech-category">Backend:</div>
                    <div class="tech-tags">
                        <span class="tech-tag tag-red">Laravel</span>
                        <span class="tech-tag tag-green">Spring Boot</span>
                        <span class="tech-tag tag-green">Node.js</span>
                    </div>
                    <div class="tech-category" style="margin-top: 1rem;">Frontend:</div>
                    <div class="tech-tags">
                        <span class="tech-tag tag-red">Angular</span>
                        <span class="tech-tag tag-gray">Next.js</span>
                        <span class="tech-tag tag-blue">Tailwind</span>
                    </div>
                </div>

                <div class="tech-card">
                    <div class="tech-header">
                        <span class="tech-icon">📱</span>
                        <div>
                            <h3 class="tech-title" style="color: #10b981;">Mobile</h3>
                        </div>
                    </div>
                    <div class="tech-tags">
                        <span class="tech-tag tag-blue">Flutter</span>
                        <span class="tech-tag tag-purple">Kotlin</span>
                        <span class="tech-tag tag-orange">Java</span>
                    </div>
                </div>

                <div class="tech-card">
                    <div class="tech-header">
                        <span class="tech-icon">🗄️</span>
                        <div>
                            <h3 class="tech-title" style="color: #ec4899;">Databases</h3>
                        </div>
                    </div>
                    <div class="tech-tags">
                        <span class="tech-tag tag-blue">MySQL</span>
                        <span class="tech-tag tag-blue">PostgreSQL</span>
                        <span class="tech-tag tag-red">Oracle</span>
                        <span class="tech-tag tag-orange">Firestore</span>
                    </div>
                </div>

                <div class="tech-card">
                    <div class="tech-header">
                        <span class="tech-icon">🐧</span>
                        <div>
                            <h3 class="tech-title" style="color: #f97316;">DevOps</h3>
                        </div>
                    </div>
                    <p style="color: #cbd5e1; font-size: 0.9rem; margin-bottom: 1rem;">Fedora Linux power user</p>
                    <div class="tech-tags">
                        <span class="tech-tag tag-blue">Docker</span>
                        <span class="tech-tag tag-green">Nginx</span>
                        <span class="tech-tag tag-orange">Linux</span>
                        <span class="tech-tag tag-purple">VPS</span>
                    </div>
                </div>
            </div>
        </section>

        <section class="section animate-on-scroll">
            <h2 class="section-title">🚀 What I Build</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <span class="project-icon">🔐</span>
                    <h3 class="project-title">Authenticator Apps</h3>
                    <p class="project-desc">Secure authentication systems with OAuth2</p>
                </div>
                <div class="project-card">
                    <span class="project-icon">📱</span>
                    <h3 class="project-title">Flutter Mobile Apps</h3>
                    <p class="project-desc">Cross-platform mobile applications</p>
                </div>
                <div class="project-card">
                    <span class="project-icon">🧩</span>
                    <h3 class="project-title">REST APIs</h3>
                    <p class="project-desc">Scalable backend services and APIs</p>
                </div>
                <div class="project-card">
                    <span class="project-icon">🎯</span>
                    <h3 class="project-title">VPS Deployments</h3>
                    <p class="project-desc">Production-ready server configurations</p>
                </div>
            </div>
        </section>

        <section class="contact animate-on-scroll">
            <h2 class="section-title">📬 Let's Connect</h2>
            <p class="contact-text">
                I'm always down to collaborate or work on meaningful projects.
            </p>
            
            <div class="social-links">
                <a href="https://github.com/Kazan-2-magma" target="_blank" rel="noopener noreferrer" class="social-link github">
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                        <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                    </svg>
                </a>
                
                <a href="https://www.linkedin.com/in/yassine-idlhaj-9aaab119a/" target="_blank" rel="noopener noreferrer" class="social-link linkedin">
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                        <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
                    </svg>
                </a>
                
                <a href="mailto:your.email@example.com" class="social-link email">
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                        <path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636C.732 21.002 0 20.27 0 19.366V5.457c0-.887.711-1.636 1.636-1.636h.727L12 10.724l9.637-6.903h.727c.905 0 1.636.749 1.636 1.636z"/>
                    </svg>
                </a>
            </div>

            <div class="quote">
                <p>"Building tomorrow's solutions with today's technology"</p>
            </div>
        </section>
    </div>

    <script>
        // Smooth scroll animation observer
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

        // Observe all elements with animate-on-scroll class
        document.querySelectorAll('.animate-on-scroll').forEach(el => {
            observer.observe(el);
        });

        // Add click animations to cards
        document.querySelectorAll('.tech-card, .project-card').forEach(card => {
            card.addEventListener('click', () => {
                card.style.transform = 'scale(0.95)';
                setTimeout(() => {
                    card.style.transform = '';
                }, 150);
            });
        });

        // Parallax effect for background circles
        window.addEventListener('mousemove', (e) => {
            const circles = document.querySelectorAll('.bg-circle');
            const x = e.clientX / window.innerWidth;
            const y = e.clientY / window.innerHeight;

            circles.forEach((circle, index) => {
                const speed = (index + 1) * 0.5;
                const xPos = (x - 0.5) * speed * 50;
                const yPos = (y - 0.5) * speed * 50;
                
                circle.style.transform = `translate(${xPos}px, ${yPos}px)`;
            });
        });

        // Typing effect for title (optional enhancement)
        const title = document.querySelector('.title');
        const originalText = title.textContent;
        title.textContent = '';
        
        let i = 0;
        const typeWriter = () => {
            if (i < originalText.length) {
                title.textContent += originalText.charAt(i);
                i++;
                setTimeout(typeWriter, 100);
            }
        };
        
        // Start typing effect after a short delay
        setTimeout(typeWriter, 500);
    </script>
</body>
</html>
