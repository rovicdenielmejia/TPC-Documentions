# Deployment Guide

This document explains how to deploy and manage the documentation site using GitHub Pages and GitHub Actions.

## Overview

This repository is configured for automated deployment to GitHub Pages using GitHub Actions. The site will be automatically deployed whenever changes are pushed to the main branch.

## Deployment Methods

### 1. Automatic Deployment (Recommended)

The site is automatically deployed using GitHub Actions when:
- Code is pushed to the `main` or `master` branch
- A pull request is merged into the main branch

**No manual intervention required!**

### 2. Manual Deployment

If you need to manually trigger a deployment:

1. Go to the **Actions** tab in your GitHub repository
2. Select the **Deploy Documentation Site** workflow
3. Click **Run workflow**
4. Choose the branch and click **Run workflow**

## Configuration Files

### GitHub Actions Workflows

- `.github/workflows/deploy.yml` - Main deployment workflow
- `.github/workflows/static-analysis.yml` - HTML validation and link checking
- `.github/workflows/security-scan.yml` - Security scanning and vulnerability checks

### GitHub Pages Configuration

- `_config.yml` - Jekyll configuration for GitHub Pages
- `index.html` - Main landing page
- `_redirects` - URL redirects for better SEO
- `.htaccess` - Apache server configuration

## Setting Up GitHub Pages

### Initial Setup

1. **Enable GitHub Pages:**
   - Go to your repository settings
   - Navigate to **Pages** section
   - Under **Source**, select **GitHub Actions**

2. **Configure Repository Permissions:**
   - Go to **Settings** → **Actions** → **General**
   - Under **Workflow permissions**, select **Read and write permissions**
   - Check **Allow GitHub Actions to create and approve pull requests**

### Custom Domain (Optional)

If you want to use a custom domain:

1. Add your domain to the `cname` field in `.github/workflows/deploy.yml`
2. Create a `CNAME` file in the repository root with your domain name
3. Configure DNS settings with your domain provider

## Environment Variables

The following environment variables are used in the deployment:

- `GITHUB_TOKEN` - Automatically provided by GitHub Actions
- `NODE_VERSION` - Set to '18' in the workflow

## Monitoring Deployments

### Check Deployment Status

1. Go to the **Actions** tab in your repository
2. Look for the **Deploy Documentation Site** workflow
3. Click on a workflow run to see detailed logs

### Common Issues

1. **Build Failures:**
   - Check the Actions logs for specific error messages
   - Ensure all HTML files are valid
   - Verify that all referenced files exist

2. **Page Not Updating:**
   - Wait a few minutes for GitHub Pages to propagate changes
   - Clear your browser cache
   - Check if the deployment workflow completed successfully

3. **Permission Errors:**
   - Ensure the repository has the correct permissions
   - Check that GitHub Actions is enabled
   - Verify the workflow has write permissions

## Security

The deployment includes several security measures:

- **Automated Security Scanning:** Weekly vulnerability scans
- **Secret Detection:** Scans for accidentally committed secrets
- **HTML Validation:** Ensures all HTML files are valid
- **Link Checking:** Verifies all links are working

## Local Development

To test changes locally before deploying:

1. **Simple HTTP Server:**
   ```bash
   # Python 3
   python -m http.server 8000
   
   # Node.js
   npx http-server
   
   # PHP
   php -S localhost:8000
   ```

2. **Access the site:** Open `http://localhost:8000` in your browser

## Troubleshooting

### Deployment Not Working

1. Check the Actions tab for failed workflows
2. Verify repository permissions
3. Ensure the main branch is protected if needed
4. Check for syntax errors in workflow files

### Site Not Updating

1. Wait 5-10 minutes for GitHub Pages to update
2. Clear browser cache
3. Check if the deployment workflow completed
4. Verify the gh-pages branch was updated

### Custom Domain Issues

1. Verify DNS settings with your domain provider
2. Check that the CNAME file is correct
3. Ensure SSL certificate is properly configured
4. Wait up to 24 hours for DNS propagation

## Support

For issues with:
- **GitHub Actions:** Check the [GitHub Actions documentation](https://docs.github.com/en/actions)
- **GitHub Pages:** Check the [GitHub Pages documentation](https://docs.github.com/en/pages)
- **This repository:** Create an issue in this repository

## Contributing

When contributing to this documentation:

1. Create a feature branch
2. Make your changes
3. Test locally if possible
4. Create a pull request
5. The deployment will be triggered automatically when merged

---

*Last updated: [Current Date]*
