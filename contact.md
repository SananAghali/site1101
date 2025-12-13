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

