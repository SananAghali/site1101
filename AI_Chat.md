# Jekyll portfolio website for SITE 1101
_Exported on 12/13/2025 at 11:47:14 GMT+4 from Cursor (2.1.49)_

---

**User**

You are working inside my Cursor editor.



I am a beginner and I do NOT want to write code myself.



Create a full Jekyll portfolio website 

compatible with GitHub Pages for SITE 1101.



IMPORTANT RULES:

- Tell me EXACTLY which file to create

- Give FULL code for each file

- Do not give snippets

- Use Jekyll (_config.yml, _layouts, _includes)

- Make it responsive

- Include Home, About, Projects, Contact pages

- Navbar and Footer

- GitHub and Codecademy icons

- Link to the website GitHub repository



Start now and go step by step.



---

**Cursor**


Creating a Jekyll portfolio site for GitHub Pages. Checking the current directory structure, then building it step by step.



Creating the Jekyll portfolio site. Starting with the configuration file.


```yaml
# Site Settings
title: SITE 1101 Portfolio
description: A professional portfolio website built with Jekyll
author: Your Name
email: your.email@example.com
url: https://yourusername.github.io
baseurl: "" # leave empty if using custom domain, or "/repository-name" if using project pages

# Build Settings
theme: minima
plugins:
  - jekyll-feed
  - jekyll-seo-tag

# Navigation
navigation:
  - title: Home
    url: /
  - title: About
    url: /about
  - title: Projects
    url: /projects
  - title: Contact
    url: /contact

# Social Links
github_username: yourusername
codecademy_username: yourusername

# Exclude from processing
exclude:
  - Gemfile
  - Gemfile.lock
  - node_modules
  - vendor/bundle/
  - vendor/cache/
  - vendor/gems/
  - vendor/ruby/

```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{% if page.title %}{{ page.title }} | {% endif %}{{ site.title }}</title>
    <meta name="description" content="{% if page.description %}{{ page.description }}{% else %}{{ site.description }}{% endif %}">
    <link rel="stylesheet" href="{{ '/assets/css/style.css' | relative_url }}">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body>
    {% include navbar.html %}
    
    <main>
        {{ content }}
    </main>
    
    {% include footer.html %}
</body>
</html>

```

```html
<nav class="navbar">
    <div class="container">
        <div class="nav-brand">
            <a href="{{ '/' | relative_url }}">{{ site.title }}</a>
        </div>
        <button class="nav-toggle" aria-label="Toggle navigation">
            <span></span>
            <span></span>
            <span></span>
        </button>
        <ul class="nav-menu">
            <li><a href="{{ '/' | relative_url }}" class="nav-link">Home</a></li>
            <li><a href="{{ '/about' | relative_url }}" class="nav-link">About</a></li>
            <li><a href="{{ '/projects' | relative_url }}" class="nav-link">Projects</a></li>
            <li><a href="{{ '/contact' | relative_url }}" class="nav-link">Contact</a></li>
        </ul>
    </div>
</nav>

<script>
    document.addEventListener('DOMContentLoaded', function() {
        const navToggle = document.querySelector('.nav-toggle');
        const navMenu = document.querySelector('.nav-menu');
        
        if (navToggle) {
            navToggle.addEventListener('click', function() {
                navMenu.classList.toggle('active');
                navToggle.classList.toggle('active');
            });
        }
        
        // Close menu when clicking on a link
        const navLinks = document.querySelectorAll('.nav-link');
        navLinks.forEach(link => {
            link.addEventListener('click', function() {
                navMenu.classList.remove('active');
                navToggle.classList.remove('active');
            });
        });
    });
</script>

```

```html
<footer class="footer">
    <div class="container">
        <div class="footer-content">
            <div class="footer-section">
                <h3>{{ site.title }}</h3>
                <p>{{ site.description }}</p>
            </div>
            <div class="footer-section">
                <h3>Quick Links</h3>
                <ul>
                    <li><a href="{{ '/' | relative_url }}">Home</a></li>
                    <li><a href="{{ '/about' | relative_url }}">About</a></li>
                    <li><a href="{{ '/projects' | relative_url }}">Projects</a></li>
                    <li><a href="{{ '/contact' | relative_url }}">Contact</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h3>Connect</h3>
                <div class="social-links">
                    <a href="https://github.com/{{ site.github_username }}" target="_blank" rel="noopener noreferrer" aria-label="GitHub">
                        <i class="fab fa-github"></i>
                    </a>
                    <a href="https://www.codecademy.com/profiles/{{ site.codecademy_username }}" target="_blank" rel="noopener noreferrer" aria-label="Codecademy">
                        <i class="fas fa-code"></i>
                    </a>
                </div>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; {{ 'now' | date: "%Y" }} {{ site.title }}. All rights reserved.</p>
            <p>
                <a href="https://github.com/{{ site.github_username }}/{{ site.github_username }}.github.io" target="_blank" rel="noopener noreferrer">
                    View Source on GitHub <i class="fab fa-github"></i>
                </a>
            </p>
        </div>
    </div>
</footer>

```

```html
---
layout: default
title: Home
description: Welcome to SITE 1101 Portfolio
---

<section class="hero">
    <div class="container">
        <div class="hero-content">
            <h1 class="hero-title">Welcome to SITE 1101</h1>
            <p class="hero-subtitle">A Modern Portfolio Website</p>
            <p class="hero-description">Showcasing projects, skills, and achievements</p>
            <div class="hero-buttons">
                <a href="{{ '/about' | relative_url }}" class="btn btn-primary">Learn More</a>
                <a href="{{ '/projects' | relative_url }}" class="btn btn-secondary">View Projects</a>
            </div>
        </div>
    </div>
</section>

<section class="features">
    <div class="container">
        <h2 class="section-title">What I Do</h2>
        <div class="features-grid">
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-code"></i>
                </div>
                <h3>Web Development</h3>
                <p>Building responsive and modern web applications using the latest technologies.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-palette"></i>
                </div>
                <h3>Design</h3>
                <p>Creating beautiful and user-friendly interfaces that provide great user experiences.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-mobile-alt"></i>
                </div>
                <h3>Responsive Design</h3>
                <p>Ensuring websites work perfectly on all devices, from mobile to desktop.</p>
            </div>
        </div>
    </div>
</section>

<section class="cta">
    <div class="container">
        <h2>Ready to Work Together?</h2>
        <p>Let's create something amazing together!</p>
        <a href="{{ '/contact' | relative_url }}" class="btn btn-primary">Get In Touch</a>
    </div>
</section>

```

```markdown
---
layout: default
title: About
description: Learn more about me and my journey
---

<div class="page-header">
    <div class="container">
        <h1>About Me</h1>
        <p class="page-subtitle">Get to know more about my background and interests</p>
    </div>
</div>

<section class="about-content">
    <div class="container">
        <div class="about-grid">
            <div class="about-text">
                <h2>Hello, I'm a Developer</h2>
                <p>
                    Welcome to my portfolio! I'm passionate about creating beautiful, functional, 
                    and user-friendly websites. I enjoy learning new technologies and applying them 
                    to solve real-world problems.
                </p>
                <p>
                    My journey in web development started with curiosity and has evolved into a 
                    passion for creating digital experiences that make a difference. I believe 
                    in writing clean, maintainable code and following best practices.
                </p>
                <h3>Skills & Technologies</h3>
                <div class="skills-list">
                    <span class="skill-tag">HTML</span>
                    <span class="skill-tag">CSS</span>
                    <span class="skill-tag">JavaScript</span>
                    <span class="skill-tag">Jekyll</span>
                    <span class="skill-tag">Git</span>
                    <span class="skill-tag">GitHub Pages</span>
                    <span class="skill-tag">Responsive Design</span>
                </div>
            </div>
            <div class="about-image">
                <div class="image-placeholder">
                    <i class="fas fa-user"></i>
                    <p>Your Photo Here</p>
                </div>
            </div>
        </div>
    </div>
</section>

<section class="education">
    <div class="container">
        <h2>Education & Learning</h2>
        <div class="education-list">
            <div class="education-item">
                <div class="education-icon">
                    <i class="fas fa-graduation-cap"></i>
                </div>
                <div class="education-content">
                    <h3>Continuous Learning</h3>
                    <p>Always learning new technologies and improving my skills through online courses and practice.</p>
                </div>
            </div>
            <div class="education-item">
                <div class="education-icon">
                    <i class="fas fa-code"></i>
                </div>
                <div class="education-content">
                    <h3>Codecademy</h3>
                    <p>Building skills through hands-on projects and interactive learning.</p>
                </div>
            </div>
        </div>
    </div>
</section>

```

```markdown
---
layout: default
title: Projects
description: Check out my latest projects and work
---

<div class="page-header">
    <div class="container">
        <h1>My Projects</h1>
        <p class="page-subtitle">A collection of projects I've worked on</p>
    </div>
</div>

<section class="projects-content">
    <div class="container">
        <div class="projects-grid">
            <div class="project-card">
                <div class="project-image">
                    <div class="image-placeholder">
                        <i class="fas fa-laptop-code"></i>
                    </div>
                </div>
                <div class="project-content">
                    <h3>Project One</h3>
                    <p>A description of your first project. Explain what it does, what technologies you used, and what you learned from it.</p>
                    <div class="project-tags">
                        <span class="tag">HTML</span>
                        <span class="tag">CSS</span>
                        <span class="tag">JavaScript</span>
                    </div>
                    <div class="project-links">
                        <a href="#" class="project-link" target="_blank" rel="noopener noreferrer">
                            <i class="fas fa-external-link-alt"></i> Live Demo
                        </a>
                        <a href="#" class="project-link" target="_blank" rel="noopener noreferrer">
                            <i class="fab fa-github"></i> Source Code
                        </a>
                    </div>
                </div>
            </div>

            <div class="project-card">
                <div class="project-image">
                    <div class="image-placeholder">
                        <i class="fas fa-mobile-alt"></i>
                    </div>
                </div>
                <div class="project-content">
                    <h3>Project Two</h3>
                    <p>A description of your second project. Explain what it does, what technologies you used, and what you learned from it.</p>
                    <div class="project-tags">
                        <span class="tag">Jekyll</span>
                        <span class="tag">GitHub Pages</span>
                        <span class="tag">Responsive</span>
                    </div>
                    <div class="project-links">
                        <a href="#" class="project-link" target="_blank" rel="noopener noreferrer">
                            <i class="fas fa-external-link-alt"></i> Live Demo
                        </a>
                        <a href="#" class="project-link" target="_blank" rel="noopener noreferrer">
                            <i class="fab fa-github"></i> Source Code
                        </a>
                    </div>
                </div>
            </div>

            <div class="project-card">
                <div class="project-image">
                    <div class="image-placeholder">
                        <i class="fas fa-globe"></i>
                    </div>
                </div>
                <div class="project-content">
                    <h3>Project Three</h3>
                    <p>A description of your third project. Explain what it does, what technologies you used, and what you learned from it.</p>
                    <div class="project-tags">
                        <span class="tag">Web Design</span>
                        <span class="tag">UI/UX</span>
                        <span class="tag">CSS</span>
                    </div>
                    <div class="project-links">
                        <a href="#" class="project-link" target="_blank" rel="noopener noreferrer">
                            <i class="fas fa-external-link-alt"></i> Live Demo
                        </a>
                        <a href="#" class="project-link" target="_blank" rel="noopener noreferrer">
                            <i class="fab fa-github"></i> Source Code
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

<section class="github-section">
    <div class="container">
        <div class="github-cta">
            <h2>Want to see more?</h2>
            <p>Check out my GitHub profile for more projects and contributions!</p>
            <a href="https://github.com/{{ site.github_username }}" class="btn btn-primary" target="_blank" rel="noopener noreferrer">
                <i class="fab fa-github"></i> Visit My GitHub
            </a>
        </div>
    </div>
</section>

```

```markdown
---
layout: default
title: Contact
description: Get in touch with me
---

<div class="page-header">
    <div class="container">
        <h1>Get In Touch</h1>
        <p class="page-subtitle">I'd love to hear from you. Send me a message!</p>
    </div>
</div>

<section class="contact-content">
    <div class="container">
        <div class="contact-grid">
            <div class="contact-info">
                <h2>Contact Information</h2>
                <p>Feel free to reach out through any of these channels:</p>
                
                <div class="contact-item">
                    <div class="contact-icon">
                        <i class="fas fa-envelope"></i>
                    </div>
                    <div class="contact-details">
                        <h3>Email</h3>
                        <p><a href="mailto:{{ site.email }}">{{ site.email }}</a></p>
                    </div>
                </div>

                <div class="contact-item">
                    <div class="contact-icon">
                        <i class="fab fa-github"></i>
                    </div>
                    <div class="contact-details">
                        <h3>GitHub</h3>
                        <p><a href="https://github.com/{{ site.github_username }}" target="_blank" rel="noopener noreferrer">github.com/{{ site.github_username }}</a></p>
                    </div>
                </div>

                <div class="contact-item">
                    <div class="contact-icon">
                        <i class="fas fa-code"></i>
                    </div>
                    <div class="contact-details">
                        <h3>Codecademy</h3>
                        <p><a href="https://www.codecademy.com/profiles/{{ site.codecademy_username }}" target="_blank" rel="noopener noreferrer">codecademy.com/profiles/{{ site.codecademy_username }}</a></p>
                    </div>
                </div>

                <div class="social-contact">
                    <h3>Follow Me</h3>
                    <div class="social-links">
                        <a href="https://github.com/{{ site.github_username }}" target="_blank" rel="noopener noreferrer" aria-label="GitHub">
                            <i class="fab fa-github"></i>
                        </a>
                        <a href="https://www.codecademy.com/profiles/{{ site.codecademy_username }}" target="_blank" rel="noopener noreferrer" aria-label="Codecademy">
                            <i class="fas fa-code"></i>
                        </a>
                    </div>
                </div>
            </div>

            <div class="contact-form-section">
                <h2>Send a Message</h2>
                <form class="contact-form" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
                    <div class="form-group">
                        <label for="name">Name</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="subject">Subject</label>
                        <input type="text" id="subject" name="subject" required>
                    </div>
                    <div class="form-group">
                        <label for="message">Message</label>
                        <textarea id="message" name="message" rows="6" required></textarea>
                    </div>
                    <button type="submit" class="btn btn-primary">Send Message</button>
                </form>
                <p class="form-note">
                    <small>Note: To enable the contact form, you'll need to set up a service like Formspree or use GitHub Issues. 
                    For now, you can use the email link above or remove this form section.</small>
                </p>
            </div>
        </div>
    </div>
</section>

```

```css
/* Reset and Base Styles */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

:root {
    --primary-color: #2563eb;
    --secondary-color: #1e40af;
    --text-color: #1f2937;
    --text-light: #6b7280;
    --bg-color: #ffffff;
    --bg-light: #f9fafb;
    --border-color: #e5e7eb;
    --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
    --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
}

body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
    line-height: 1.6;
    color: var(--text-color);
    background-color: var(--bg-color);
}

.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
}

/* Navigation */
.navbar {
    background-color: var(--bg-color);
    box-shadow: var(--shadow);
    position: sticky;
    top: 0;
    z-index: 1000;
}

.navbar .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 20px;
}

.nav-brand a {
    font-size: 1.5rem;
    font-weight: bold;
    color: var(--primary-color);
    text-decoration: none;
    transition: color 0.3s;
}

.nav-brand a:hover {
    color: var(--secondary-color);
}

.nav-menu {
    display: flex;
    list-style: none;
    gap: 2rem;
}

.nav-link {
    color: var(--text-color);
    text-decoration: none;
    font-weight: 500;
    transition: color 0.3s;
    position: relative;
}

.nav-link:hover {
    color: var(--primary-color);
}

.nav-link::after {
    content: '';
    position: absolute;
    bottom: -5px;
    left: 0;
    width: 0;
    height: 2px;
    background-color: var(--primary-color);
    transition: width 0.3s;
}

.nav-link:hover::after {
    width: 100%;
}

.nav-toggle {
    display: none;
    flex-direction: column;
    background: none;
    border: none;
    cursor: pointer;
    padding: 5px;
}

.nav-toggle span {
    width: 25px;
    height: 3px;
    background-color: var(--text-color);
    margin: 3px 0;
    transition: 0.3s;
}

/* Hero Section */
.hero {
    background: linear-gradient(135deg, var(--primary-color) 0%, var(--secondary-color) 100%);
    color: white;
    padding: 100px 0;
    text-align: center;
}

.hero-content {
    max-width: 800px;
    margin: 0 auto;
}

.hero-title {
    font-size: 3.5rem;
    margin-bottom: 1rem;
    animation: fadeInUp 0.8s;
}

.hero-subtitle {
    font-size: 1.5rem;
    margin-bottom: 1rem;
    opacity: 0.9;
    animation: fadeInUp 0.8s 0.2s both;
}

.hero-description {
    font-size: 1.1rem;
    margin-bottom: 2rem;
    opacity: 0.8;
    animation: fadeInUp 0.8s 0.4s both;
}

.hero-buttons {
    display: flex;
    gap: 1rem;
    justify-content: center;
    flex-wrap: wrap;
    animation: fadeInUp 0.8s 0.6s both;
}

/* Buttons */
.btn {
    display: inline-block;
    padding: 12px 30px;
    text-decoration: none;
    border-radius: 5px;
    font-weight: 600;
    transition: all 0.3s;
    border: 2px solid transparent;
}

.btn-primary {
    background-color: white;
    color: var(--primary-color);
}

.btn-primary:hover {
    background-color: var(--bg-light);
    transform: translateY(-2px);
    box-shadow: var(--shadow-lg);
}

.btn-secondary {
    background-color: transparent;
    color: white;
    border: 2px solid white;
}

.btn-secondary:hover {
    background-color: white;
    color: var(--primary-color);
}

/* Features Section */
.features {
    padding: 80px 0;
    background-color: var(--bg-light);
}

.section-title {
    text-align: center;
    font-size: 2.5rem;
    margin-bottom: 3rem;
    color: var(--text-color);
}

.features-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
}

.feature-card {
    background: white;
    padding: 2rem;
    border-radius: 10px;
    text-align: center;
    box-shadow: var(--shadow);
    transition: transform 0.3s, box-shadow 0.3s;
}

.feature-card:hover {
    transform: translateY(-5px);
    box-shadow: var(--shadow-lg);
}

.feature-icon {
    font-size: 3rem;
    color: var(--primary-color);
    margin-bottom: 1rem;
}

.feature-card h3 {
    font-size: 1.5rem;
    margin-bottom: 1rem;
    color: var(--text-color);
}

.feature-card p {
    color: var(--text-light);
}

/* CTA Section */
.cta {
    padding: 80px 0;
    text-align: center;
    background: linear-gradient(135deg, var(--primary-color) 0%, var(--secondary-color) 100%);
    color: white;
}

.cta h2 {
    font-size: 2.5rem;
    margin-bottom: 1rem;
}

.cta p {
    font-size: 1.2rem;
    margin-bottom: 2rem;
    opacity: 0.9;
}

/* Page Header */
.page-header {
    background: linear-gradient(135deg, var(--primary-color) 0%, var(--secondary-color) 100%);
    color: white;
    padding: 60px 0;
    text-align: center;
}

.page-header h1 {
    font-size: 3rem;
    margin-bottom: 1rem;
}

.page-subtitle {
    font-size: 1.2rem;
    opacity: 0.9;
}

/* About Page */
.about-content {
    padding: 60px 0;
}

.about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 3rem;
    align-items: center;
}

.about-text h2 {
    font-size: 2rem;
    margin-bottom: 1rem;
    color: var(--text-color);
}

.about-text p {
    margin-bottom: 1.5rem;
    color: var(--text-light);
    line-height: 1.8;
}

.about-text h3 {
    font-size: 1.5rem;
    margin: 2rem 0 1rem;
    color: var(--text-color);
}

.skills-list {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
}

.skill-tag {
    background-color: var(--primary-color);
    color: white;
    padding: 0.5rem 1rem;
    border-radius: 20px;
    font-size: 0.9rem;
    font-weight: 500;
}

.image-placeholder {
    background-color: var(--bg-light);
    border: 2px dashed var(--border-color);
    border-radius: 10px;
    padding: 60px 20px;
    text-align: center;
    color: var(--text-light);
}

.image-placeholder i {
    font-size: 4rem;
    margin-bottom: 1rem;
    color: var(--primary-color);
}

/* Education Section */
.education {
    padding: 60px 0;
    background-color: var(--bg-light);
}

.education h2 {
    text-align: center;
    font-size: 2.5rem;
    margin-bottom: 3rem;
    color: var(--text-color);
}

.education-list {
    max-width: 800px;
    margin: 0 auto;
}

.education-item {
    display: flex;
    gap: 2rem;
    background: white;
    padding: 2rem;
    border-radius: 10px;
    margin-bottom: 1.5rem;
    box-shadow: var(--shadow);
}

.education-icon {
    font-size: 2.5rem;
    color: var(--primary-color);
}

.education-content h3 {
    font-size: 1.5rem;
    margin-bottom: 0.5rem;
    color: var(--text-color);
}

.education-content p {
    color: var(--text-light);
}

/* Projects Page */
.projects-content {
    padding: 60px 0;
}

.projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    gap: 2rem;
}

.project-card {
    background: white;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: var(--shadow);
    transition: transform 0.3s, box-shadow 0.3s;
}

.project-card:hover {
    transform: translateY(-5px);
    box-shadow: var(--shadow-lg);
}

.project-image {
    height: 200px;
    background: linear-gradient(135deg, var(--primary-color) 0%, var(--secondary-color) 100%);
    display: flex;
    align-items: center;
    justify-content: center;
}

.project-image .image-placeholder {
    background: transparent;
    border: none;
    color: white;
}

.project-image .image-placeholder i {
    color: white;
    font-size: 4rem;
}

.project-content {
    padding: 1.5rem;
}

.project-content h3 {
    font-size: 1.5rem;
    margin-bottom: 1rem;
    color: var(--text-color);
}

.project-content p {
    color: var(--text-light);
    margin-bottom: 1rem;
    line-height: 1.6;
}

.project-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin-bottom: 1rem;
}

.tag {
    background-color: var(--bg-light);
    color: var(--text-color);
    padding: 0.3rem 0.8rem;
    border-radius: 15px;
    font-size: 0.85rem;
    border: 1px solid var(--border-color);
}

.project-links {
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
}

.project-link {
    color: var(--primary-color);
    text-decoration: none;
    font-weight: 500;
    transition: color 0.3s;
    display: flex;
    align-items: center;
    gap: 0.5rem;
}

.project-link:hover {
    color: var(--secondary-color);
}

.github-section {
    padding: 60px 0;
    background-color: var(--bg-light);
}

.github-cta {
    text-align: center;
    max-width: 600px;
    margin: 0 auto;
}

.github-cta h2 {
    font-size: 2rem;
    margin-bottom: 1rem;
    color: var(--text-color);
}

.github-cta p {
    color: var(--text-light);
    margin-bottom: 2rem;
    font-size: 1.1rem;
}

/* Contact Page */
.contact-content {
    padding: 60px 0;
}

.contact-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 3rem;
}

.contact-info h2 {
    font-size: 2rem;
    margin-bottom: 1rem;
    color: var(--text-color);
}

.contact-info > p {
    color: var(--text-light);
    margin-bottom: 2rem;
}

.contact-item {
    display: flex;
    gap: 1.5rem;
    margin-bottom: 2rem;
}

.contact-icon {
    font-size: 2rem;
    color: var(--primary-color);
    width: 50px;
    text-align: center;
}

.contact-details h3 {
    font-size: 1.2rem;
    margin-bottom: 0.5rem;
    color: var(--text-color);
}

.contact-details p {
    color: var(--text-light);
}

.contact-details a {
    color: var(--primary-color);
    text-decoration: none;
    transition: color 0.3s;
}

.contact-details a:hover {
    color: var(--secondary-color);
    text-decoration: underline;
}

.social-contact {
    margin-top: 2rem;
}

.social-contact h3 {
    font-size: 1.2rem;
    margin-bottom: 1rem;
    color: var(--text-color);
}

.social-links {
    display: flex;
    gap: 1rem;
}

.social-links a {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 50px;
    height: 50px;
    background-color: var(--primary-color);
    color: white;
    border-radius: 50%;
    text-decoration: none;
    font-size: 1.5rem;
    transition: all 0.3s;
}

.social-links a:hover {
    background-color: var(--secondary-color);
    transform: translateY(-3px);
    box-shadow: var(--shadow);
}

.contact-form-section h2 {
    font-size: 2rem;
    margin-bottom: 1.5rem;
    color: var(--text-color);
}

.contact-form {
    background: var(--bg-light);
    padding: 2rem;
    border-radius: 10px;
}

.form-group {
    margin-bottom: 1.5rem;
}

.form-group label {
    display: block;
    margin-bottom: 0.5rem;
    font-weight: 500;
    color: var(--text-color);
}

.form-group input,
.form-group textarea {
    width: 100%;
    padding: 0.75rem;
    border: 1px solid var(--border-color);
    border-radius: 5px;
    font-family: inherit;
    font-size: 1rem;
    transition: border-color 0.3s;
}

.form-group input:focus,
.form-group textarea:focus {
    outline: none;
    border-color: var(--primary-color);
}

.form-note {
    margin-top: 1rem;
    color: var(--text-light);
    font-size: 0.9rem;
}

/* Footer */
.footer {
    background-color: var(--text-color);
    color: white;
    padding: 60px 0 20px;
    margin-top: 60px;
}

.footer-content {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 2rem;
    margin-bottom: 2rem;
}

.footer-section h3 {
    font-size: 1.2rem;
    margin-bottom: 1rem;
}

.footer-section p {
    opacity: 0.8;
    line-height: 1.6;
}

.footer-section ul {
    list-style: none;
}

.footer-section ul li {
    margin-bottom: 0.5rem;
}

.footer-section ul li a {
    color: white;
    text-decoration: none;
    opacity: 0.8;
    transition: opacity 0.3s;
}

.footer-section ul li a:hover {
    opacity: 1;
}

.footer-bottom {
    text-align: center;
    padding-top: 2rem;
    border-top: 1px solid rgba(255, 255, 255, 0.1);
}

.footer-bottom p {
    margin-bottom: 0.5rem;
    opacity: 0.8;
}

.footer-bottom a {
    color: white;
    text-decoration: none;
    opacity: 0.8;
    transition: opacity 0.3s;
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
}

.footer-bottom a:hover {
    opacity: 1;
}

/* Animations */
@keyframes fadeInUp {
    from {
        opacity: 0;
        transform: translateY(20px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

/* Responsive Design */
@media (max-width: 768px) {
    .nav-menu {
        position: fixed;
        left: -100%;
        top: 70px;
        flex-direction: column;
        background-color: var(--bg-color);
        width: 100%;
        text-align: center;
        transition: 0.3s;
        box-shadow: var(--shadow);
        padding: 2rem 0;
    }

    .nav-menu.active {
        left: 0;
    }

    .nav-toggle {
        display: flex;
    }

    .nav-toggle.active span:nth-child(1) {
        transform: rotate(-45deg) translate(-5px, 6px);
    }

    .nav-toggle.active span:nth-child(2) {
        opacity: 0;
    }

    .nav-toggle.active span:nth-child(3) {
        transform: rotate(45deg) translate(-5px, -6px);
    }

    .hero-title {
        font-size: 2.5rem;
    }

    .hero-subtitle {
        font-size: 1.2rem;
    }

    .section-title {
        font-size: 2rem;
    }

    .features-grid {
        grid-template-columns: 1fr;
    }

    .about-grid {
        grid-template-columns: 1fr;
    }

    .projects-grid {
        grid-template-columns: 1fr;
    }

    .contact-grid {
        grid-template-columns: 1fr;
    }

    .page-header h1 {
        font-size: 2rem;
    }

    .footer-content {
        grid-template-columns: 1fr;
        text-align: center;
    }
}

@media (max-width: 480px) {
    .hero-title {
        font-size: 2rem;
    }

    .hero-buttons {
        flex-direction: column;
        align-items: stretch;
    }

    .btn {
        text-align: center;
    }
}

```

```markdown
# SITE 1101 Portfolio

A modern, responsive portfolio website built with Jekyll and compatible with GitHub Pages.

## Features

- 🎨 Modern and responsive design
- 📱 Mobile-friendly navigation
- 🚀 Fast and lightweight
- 🔗 Social media integration (GitHub, Codecademy)
- 📄 Multiple pages (Home, About, Projects, Contact)
- 🎯 SEO optimized

## Setup Instructions

### 1. Update Configuration

Edit `_config.yml` and update the following:

```yaml
title: SITE 1101 Portfolio
author: Your Name
email: your.email@example.com
url: https://yourusername.github.io
github_username: yourusername
codecademy_username: yourusername
```

### 2. Customize Content

- **Home Page**: Edit `index.html` to customize the hero section and features
- **About Page**: Edit `about.md` to add your information and skills
- **Projects Page**: Edit `projects.md` to showcase your projects
- **Contact Page**: Edit `contact.md` to update contact information

### 3. Deploy to GitHub Pages

#### Option A: Using GitHub Pages (Automatic)

1. Create a new repository on GitHub named `yourusername.github.io` (replace `yourusername` with your GitHub username)
2. Push all files to the repository
3. Go to Settings > Pages
4. Select the main branch as the source
5. Your site will be live at `https://yourusername.github.io`

#### Option B: Using a Project Repository

1. Create a repository with any name
2. Push all files to the repository
3. Go to Settings > Pages
4. Select the main branch as the source
5. Update `_config.yml`:
   ```yaml
   baseurl: "/repository-name"
   url: "https://yourusername.github.io"
   ```
6. Your site will be live at `https://yourusername.github.io/repository-name`

### 4. Local Development (Optional)

To test locally before deploying:

1. Install Ruby and Jekyll:
   ```bash
   gem install bundler jekyll
   ```

2. Install dependencies:
   ```bash
   bundle install
   ```

3. Run the development server:
   ```bash
   bundle exec jekyll serve
   ```

4. Open `http://localhost:4000` in your browser

## File Structure

```
site1101/
├── _config.yml          # Jekyll configuration
├── _layouts/
│   └── default.html     # Main layout template
├── _includes/
│   ├── navbar.html      # Navigation bar
│   └── footer.html      # Footer with social links
├── assets/
│   └── css/
│       └── style.css    # Main stylesheet
├── index.html           # Home page
├── about.md             # About page
├── projects.md          # Projects page
├── contact.md           # Contact page
└── README.md            # This file
```

## Customization

### Colors

Edit the CSS variables in `assets/css/style.css`:

```css
:root {
    --primary-color: #2563eb;
    --secondary-color: #1e40af;
    /* ... */
}
```

### Contact Form

The contact form uses Formspree as an example. To enable it:

1. Sign up at [Formspree.io](https://formspree.io)
2. Create a new form
3. Replace `YOUR_FORM_ID` in `contact.md` with your form ID

Alternatively, you can:
- Use GitHub Issues API
- Use another form service
- Remove the form and keep only contact information

## License

This project is open source and available for personal and commercial use.

## Support

For issues or questions, please open an issue on the GitHub repository.

---

Built with ❤️ using Jekyll and GitHub Pages

```

```ignore
_site/
.sass-cache/
.jekyll-cache/
.jekyll-metadata
vendor/
.bundle/
Gemfile.lock
node_modules/

```

```ruby
source "https://rubygems.org"

gem "jekyll", "~> 4.3"
gem "minima", "~> 2.5"
gem "jekyll-feed", "~> 0.12"
gem "jekyll-seo-tag", "~> 2.8"

platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

gem "wdm", "~> 0.1.1", :platforms => [:mingw, :x64_mingw, :mswin]

```


Created a Jekyll portfolio site for GitHub Pages. Files created:

## Files created

### 1. **`_config.yml`** — Jekyll configuration
   - Site settings, navigation, social links (GitHub, Codecademy)

### 2. **`_layouts/default.html`** — Main layout template
   - Wraps all pages with navbar and footer

### 3. **`_includes/navbar.html`** — Navigation bar
   - Responsive menu with mobile toggle

### 4. **`_includes/footer.html`** — Footer
   - GitHub and Codecademy icons, link to repository

### 5. **`index.html`** — Home page
   - Hero section, features, call-to-action

### 6. **`about.md`** — About page
   - Bio, skills, education

### 7. **`projects.md`** — Projects page
   - Project cards with tags and links

### 8. **`contact.md`** — Contact page
   - Contact info, social links, contact form template

### 9. **`assets/css/style.css`** — Stylesheet
   - Responsive design, animations, mobile-friendly

### 10. **`README.md`** — Setup instructions
    - Deployment guide and customization tips

### 11. **`.gitignore`** — Git ignore file
    - Excludes Jekyll build files

### 12. **`Gemfile`** — Ruby dependencies
    - Required Jekyll gems

## Next steps

1. Update `_config.yml`:
   - Replace `yourusername` with your GitHub username
   - Update email and other personal info

2. Deploy to GitHub:
   - Create a repository named `yourusername.github.io`
   - Push all files
   - Enable GitHub Pages in Settings

3. Customize content:
   - Edit the pages with your information
   - Add your projects to `projects.md`
   - Update the contact form if needed

The site is responsive, includes all requested pages, and has GitHub and Codecademy icons in the footer. The footer also links to your GitHub repository.

All files are ready. Update the configuration and deploy to GitHub Pages.

