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

