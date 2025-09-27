# Shop Documentation

A documentation site for shop policies, terms, and conditions, deployed automatically using GitHub Pages.

## 📋 Contents

- [Terms & Conditions](Terms%20&%20Condition.html) - Loyalty program terms and conditions
- [Deployment Guide](DEPLOYMENT.md) - How to deploy and manage the site

## 🚀 Quick Start

This site is automatically deployed to GitHub Pages. No setup required!

**Live Site:** [View Documentation](https://your-username.github.io/your-repository-name)

## 🛠️ Local Development

To run the site locally:

```bash
# Using Python (recommended)
python -m http.server 8000

# Using Node.js
npx http-server

# Using PHP
php -S localhost:8000
```

Then open `http://localhost:8000` in your browser.

## 📁 Project Structure

```
├── .github/workflows/     # GitHub Actions workflows
│   ├── deploy.yml         # Main deployment workflow
│   ├── static-analysis.yml # HTML validation
│   └── security-scan.yml  # Security scanning
├── Terms & Condition.html # Terms and conditions page
├── index.html            # Main landing page
├── _config.yml          # Jekyll configuration
├── _redirects           # URL redirects
├── .htaccess           # Apache configuration
├── DEPLOYMENT.md       # Deployment documentation
└── README.md           # This file
```

## 🔧 Configuration

### GitHub Pages Settings

1. Go to repository **Settings** → **Pages**
2. Set **Source** to **GitHub Actions**
3. The site will deploy automatically on push to main branch

### Custom Domain

To use a custom domain:

1. Add your domain to the `cname` field in `.github/workflows/deploy.yml`
2. Create a `CNAME` file with your domain name
3. Configure DNS with your domain provider

## 🔒 Security Features

- **Automated Security Scanning:** Weekly vulnerability checks
- **Secret Detection:** Prevents accidental secret commits
- **HTML Validation:** Ensures all HTML is valid
- **Link Checking:** Verifies all links work

## 📊 Monitoring

- **Deployment Status:** Check the Actions tab
- **Security Issues:** View in Security tab
- **Performance:** Monitor GitHub Pages analytics

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test locally
5. Submit a pull request

## 📝 License

This documentation is for internal use only.

## 🆘 Support

- **Deployment Issues:** Check [DEPLOYMENT.md](DEPLOYMENT.md)
- **GitHub Actions:** [GitHub Actions Documentation](https://docs.github.com/en/actions)
- **GitHub Pages:** [GitHub Pages Documentation](https://docs.github.com/en/pages)

---

*Automatically deployed with GitHub Actions* 🚀
