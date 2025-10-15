
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Matéo BOURDIN - Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        :root {
            --primary: #3498db;
            --secondary: #2c3e50;
            --accent: #e74c3c;
            --light: #ecf0f1;
            --dark: #2c3e50;
            --text: #333;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--text);
            overflow-x: hidden;
        }
        
        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(44, 62, 80, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        
        nav ul {
            list-style: none;
            display: flex;
            justify-content: center;
            padding: 1rem 0;
        }
        
        nav li {
            margin: 0 2rem;
        }
        
        nav a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s ease;
            position: relative;
        }
        
        nav a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary);
            transition: width 0.3s ease;
        }
        
        nav a:hover::after {
            width: 100%;
        }
        
        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
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
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320"><path fill="%23ffffff" fill-opacity="0.1" d="M0,96L48,112C96,128,192,160,288,160C384,160,480,128,576,122.7C672,117,768,139,864,154.7C960,171,1056,181,1152,165.3C1248,149,1344,107,1392,85.3L1440,64L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"></path></svg>');
            animation: wave 15s ease-in-out infinite;
        }
        
        @keyframes wave {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }
        
        .hero-content {
            z-index: 1;
            animation: fadeInUp 1s ease;
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
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
        }
        
        .hero p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }
        
        .btn {
            display: inline-block;
            padding: 1rem 2.5rem;
            background: white;
            color: var(--secondary);
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(0,0,0,0.3);
        }
        
        /* Section générale */
        section {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: var(--secondary);
            position: relative;
        }
        
        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background: var(--primary);
            margin: 1rem auto;
            border-radius: 2px;
        }
        
        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 3rem;
            align-items: center;
        }
        
        .profile-img {
            width: 100%;
            max-width: 300px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            transition: transform 0.3s ease;
        }
        
        .profile-img:hover {
            transform: scale(1.05);
        }
        
        .about-text h3 {
            color: var(--primary);
            margin-bottom: 1rem;
            font-size: 1.8rem;
        }
        
        .about-text p {
            margin-bottom: 1rem;
            line-height: 1.8;
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
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
        }
        
        .skill-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.15);
        }
        
        .skill-card h3 {
            color: var(--primary);
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }
        
        .skill-list {
            list-style: none;
        }
        
        .skill-list li {
            padding: 0.5rem 0;
            border-bottom: 1px solid var(--light);
        }
        
        .skill-list li:last-child {
            border-bottom: none;
        }
        
        /* Projects Section */
        #projets {
            background: var(--light);
        }
        
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }
        
        .project-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
        }
        
        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }
        
        .project-img {
            width: 100%;
            height: 200px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: white;
        }
        
        .project-content {
            padding: 1.5rem;
        }
        
        .project-content h3 {
            color: var(--secondary);
            margin-bottom: 0.5rem;
        }
        
        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-top: 1rem;
        }
        
        .tag {
            background: var(--primary);
            color: white;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.85rem;
        }
        
        /* Contact Section */
        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
        }
        
        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }
        
        .contact-item {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1rem;
            background: var(--light);
            border-radius: 10px;
            transition: all 0.3s ease;
        }
        
        .contact-item:hover {
            background: var(--primary);
            color: white;
            transform: translateX(10px);
        }
        
        .contact-icon {
            font-size: 1.5rem;
        }
        
        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 2rem;
        }
        
        .social-link {
            width: 50px;
            height: 50px;
            background: var(--primary);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            text-decoration: none;
            font-size: 1.5rem;
            transition: all 0.3s ease;
        }
        
        .social-link:hover {
            background: var(--secondary);
            transform: scale(1.1);
        }
        
        /* Footer */
        footer {
            background: var(--secondary);
            color: white;
            text-align: center;
            padding: 2rem;
        }
        
        .download-cv {
            margin-top: 2rem;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .hero p {
                font-size: 1.2rem;
            }
            
            .about-content,
            .contact-content {
                grid-template-columns: 1fr;
            }
            
            nav ul {
                flex-direction: column;
                align-items: center;
            }
            
            nav li {
                margin: 0.5rem 0;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <ul>
            <li><a href="#accueil">Accueil</a></li>
            <li><a href="#apropos">À propos</a></li>
            <li><a href="#competences">Compétences</a></li>
            <li><a href="#projets">Projets</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>
    
    <!-- Hero Section -->
    <section id="accueil" class="hero">
        <div class="hero-content">
            <h1>Matéo BOURDIN</h1>
            <p>Étudiant en Informatique | Développeur Full-Stack</p>
            <a href="#contact" class="btn">Me contacter</a>
        </div>
    </section>
    
    <!-- About Section -->
    <section id="apropos">
        <h2 class="section-title">À propos de moi</h2>
        <div class="about-content">
            <div>
                <img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 300 300'%3E%3Crect fill='%233498db' width='300' height='300' rx='20'/%3E%3Ctext x='50%25' y='50%25' fill='white' font-size='80' text-anchor='middle' dominant-baseline='middle' font-family='Arial'%3EMB%3C/text%3E%3C/svg%3E" alt="Matéo BOURDIN" class="profile-img">
            </div>
            <div class="about-text">
                <h3>Passionné par le développement et l'innovation</h3>
                <p>Actuellement en deuxième année de BUT Informatique à l'IUT d'Annecy, je suis passionné par le développement d'applications et la conception d'interfaces utilisateur intuitives.</p>
                <p>Mon parcours m'a permis de développer des compétences solides en programmation orientée objet, en gestion de bases de données et en développement web. Je maîtrise plusieurs langages et frameworks, notamment Java, C#, Python, et je travaille actuellement sur des projets utilisant Laravel et PostgreSQL.</p>
                <p>Au-delà de l'informatique, je suis sportif de haut niveau en ski et sports équestres, ce qui m'a appris la rigueur, la persévérance et l'esprit d'équipe.</p>
            </div>
        </div>
    </section>
    
    <!-- Skills Section -->
    <section id="competences">
        <h2 class="section-title">Compétences</h2>
        <div class="skills-grid">
            <div class="skill-card">
                <h3>🖥️ Langages de Programmation</h3>
                <ul class="skill-list">
                    <li>Java (POO)</li>
                    <li>C# (avancé)</li>
                    <li>Python (avancé)</li>
                    <li>HTML, CSS, JavaScript</li>
                    <li>PHP</li>
                </ul>
            </div>
            <div class="skill-card">
                <h3>🗄️ Bases de Données & API</h3>
                <ul class="skill-list">
                    <li>PostgreSQL</li>
                    <li>Modélisation MCD/MLD</li>
                    <li>Requêtes SQL</li>
                    <li>REST API</li>
                    <li>Intégration d'API externes</li>
                </ul>
            </div>
            <div class="skill-card">
                <h3>🎨 Développement IHM</h3>
                <ul class="skill-list">
                    <li>WPF (MVVM/MVC)</li>
                    <li>Tkinter</li>
                    <li>UI/UX Design</li>
                    <li>Conception ergonomique</li>
                    <li>Notions Android</li>
                </ul>
            </div>
            <div class="skill-card">
                <h3>🛠️ Outils & Technologies</h3>
                <ul class="skill-list">
                    <li>Git / GitHub</li>
                    <li>Visual Studio, IntelliJ IDEA</li>
                    <li>Laravel Framework</li>
                    <li>Azure DevOps (Scrum)</li>
                    <li>Visual Paradigm (UML)</li>
                </ul>
            </div>
        </div>
    </section>
    
    <!-- Projects Section -->
    <section id="projets">
        <h2 class="section-title">Mes Projets</h2>
        <div class="projects-grid">
            <div class="project-card">
                <div class="project-img">🛒</div>
                <div class="project-content">
                    <h3>Site E-commerce CUBE France</h3>
                    <p><strong>En cours</strong> | Équipe de 4</p>
                    <p>Développement d'une plateforme e-commerce complète avec Laravel, PostgreSQL et Azure DevOps. Intégration de systèmes de paiement sécurisés (Stripe, PayPal), chatbot et conformité RGPD.</p>
                    <div class="project-tags">
                        <span class="tag">Laravel</span>
                        <span class="tag">PostgreSQL</span>
                        <span class="tag">Scrum</span>
                        <span class="tag">RGPD</span>
                    </div>
                </div>
            </div>
            
            <div class="project-card">
                <div class="project-img">🍷</div>
                <div class="project-content">
                    <h3>Gestion de Stock de Vin</h3>
                    <p><strong>Début 2025</strong> | Binôme</p>
                    <p>Application desktop de gestion avec architecture MVVM, diagrammes UML complets et API REST pour la communication client-serveur.</p>
                    <div class="project-tags">
                        <span class="tag">C#</span>
                        <span class="tag">WPF</span>
                        <span class="tag">PostgreSQL</span>
                        <span class="tag">REST API</span>
                    </div>
                </div>
            </div>
            
            <div class="project-card">
                <div class="project-img">🚀</div>
                <div class="project-content">
                    <h3>Jeu de Combat Spatial</h3>
                    <p><strong>Fin 2024</strong> | Équipe de 3</p>
                    <p>Jeu vidéo développé en C# avec programmation orientée objet, rendu graphique, gestion audio et développement collaboratif via Git.</p>
                    <div class="project-tags">
                        <span class="tag">C#</span>
                        <span class="tag">POO</span>
                        <span class="tag">Git</span>
                        <span class="tag">UI Design</span>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Contact Section -->
    <section id="contact">
        <h2 class="section-title">Me Contacter</h2>
        <div class="contact-content">
            <div class="contact-info">
                <div class="contact-item">
                    <span class="contact-icon">📧</span>
                    <div>
                        <strong>Email</strong><br>
                        mateo.bourdin@etu.univ-smb.fr
                    </div>
                </div>
                <div class="contact-item">
                    <span class="contact-icon">📱</span>
                    <div>
                        <strong>Téléphone</strong><br>
                        06 11 62 43 81
                    </div>
                </div>
                <div class="contact-item">
                    <span class="contact-icon">📍</span>
                    <div>
                        <strong>Localisation</strong><br>
                        Reignier-Esery, France
                    </div>
                </div>
                <div class="social-links">
                    <a href="https://www.linkedin.com/in/BOURDINMateo" target="_blank" class="social-link">in</a>
                    <a href="https://github.com/MateoLeVre" target="_blank" class="social-link">🐙</a>
                </div>
            </div>
            <div>
                <h3>Disponibilité</h3>
                <p style="margin-bottom: 1rem;">Je suis actuellement à la recherche d'un stage de 1 à 3 mois à partir d'avril 2025 dans le domaine du développement d'applications.</p>
                <p style="margin-bottom: 1rem;">N'hésitez pas à me contacter pour discuter d'opportunités de collaboration ou pour en savoir plus sur mes projets !</p>
                <div class="download-cv">
                    <a href="#" class="btn">Télécharger mon CV</a>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Footer -->
    <footer>
        <p>&copy; 2025 Matéo BOURDIN - Tous droits réservés</p>
        <p style="margin-top: 0.5rem; opacity: 0.8;">Étudiant en BUT Informatique | IUT Annecy</p>
    </footer>
    
    <script>
        // Smooth scrolling
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
        
        // Active nav link on scroll
        window.addEventListener('scroll', () => {
            let current = '';
            const sections = document.querySelectorAll('section');
            
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                if (pageYOffset >= (sectionTop - 100)) {
                    current = section.getAttribute('id');
                }
            });
            
            document.querySelectorAll('nav a').forEach(a => {
                a.classList.remove('active');
                if (a.getAttribute('href').substring(1) === current) {
                    a.classList.add('active');
                }
            });
        });
    </script>
</body>
</html>
