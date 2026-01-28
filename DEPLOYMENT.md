# GitHub Pages Deployment Guide

This guide explains how to deploy the Asgardeo Flutter SDK documentation to GitHub Pages.

## 🚀 Quick Deployment

### Option 1: Automatic Deployment (Recommended)

The repository includes a GitHub Actions workflow that automatically deploys the documentation when changes are pushed to the `docs/` folder.

1. **Push your code to GitHub:**

```bash
git add .
git commit -m "docs: add documentation site"
git push origin main
```

2. **Enable GitHub Pages:**
   - Go to your repository on GitHub
   - Click **Settings** → **Pages**
   - Under "Build and deployment":
     - Source: Select **"GitHub Actions"**
   - The workflow will automatically deploy on the next push

3. **Access your documentation:**
   - Your site will be available at: `https://yourusername.github.io/repository-name/`
   - Check the Actions tab to monitor deployment progress

### Option 2: Manual Deployment

If you prefer to deploy manually without GitHub Actions:

1. **Go to repository Settings:**
   - Click **Settings** → **Pages**

2. **Configure source:**
   - Source: Select **"Deploy from a branch"**
   - Branch: Select **"main"** (or your default branch)
   - Folder: Select **"/docs"**
   - Click **Save**

3. **Wait for deployment:**
   - GitHub will build and deploy your site
   - This may take a few minutes
   - You'll see a link to your live site once it's ready

## 🔧 Configuration

### Custom Domain (Optional)

To use a custom domain:

1. Add a `CNAME` file in the `docs/` folder:

```bash
echo "docs.yourdomain.com" > docs/CNAME
```

2. Configure DNS:
   - Add a CNAME record pointing to `yourusername.github.io`
   - Or add A records pointing to GitHub Pages IPs

3. Enable HTTPS:
   - In repository Settings → Pages
   - Check "Enforce HTTPS"

### Base URL Configuration

If your repository name is not the root of your domain, update the links in the HTML files:

```html
<!-- Change from: -->
<link rel="stylesheet" href="styles.css">

<!-- To: -->
<link rel="stylesheet" href="/repository-name/styles.css">
```

Or use relative URLs (already implemented):

```html
<link rel="stylesheet" href="styles.css">
```

## 📝 Updating Documentation

### Making Changes

1. **Edit HTML files locally:**

```bash
cd docs
# Edit files
```

2. **Test locally:**

```bash
# Using Python
python3 -m http.server 8000

# Or using Node.js
npx http-server

# Open http://localhost:8000
```

3. **Commit and push:**

```bash
git add docs/
git commit -m "docs: update documentation"
git push origin main
```

4. **Automatic deployment:**
   - The GitHub Action will automatically deploy your changes
   - Check the Actions tab to monitor progress

### Local Development

For local development with live reload:

```bash
# Install a live server
npm install -g live-server

# Run from docs directory
cd docs
live-server
```

## 🔍 Troubleshooting

### Site not updating

1. Check the Actions tab for deployment status
2. Verify the workflow completed successfully
3. Clear your browser cache (Cmd/Ctrl + Shift + R)
4. Wait a few minutes for CDN propagation

### 404 errors

1. Verify all file paths are correct
2. Check that files are in the `docs/` folder
3. Ensure file names match case-sensitively
4. Check that `index.html` exists in the root of `docs/`

### CSS/JS not loading

1. Verify file paths in HTML files
2. Use relative paths (e.g., `styles.css` not `/styles.css`)
3. Check browser console for 404 errors

### Workflow not running

1. Verify `.github/workflows/deploy-docs.yml` exists
2. Check that GitHub Actions are enabled in repository settings
3. Ensure you have push permissions to the repository

## 📊 Monitoring

### Deployment Status

Check deployment status:
- Go to **Actions** tab in your repository
- Click on the latest workflow run
- View logs for any errors

### Analytics (Optional)

Add Google Analytics to track visitors:

1. Get your GA tracking ID
2. Add to each HTML file before `</head>`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

## 🔐 Security

### HTTPS

Always enable HTTPS for your documentation site:
- Go to Settings → Pages
- Check "Enforce HTTPS"
- GitHub provides free SSL certificates

### Branch Protection

Protect your main branch:
- Go to Settings → Branches
- Add branch protection rule for `main`
- Require pull request reviews before merging

## 📚 Additional Resources

- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Custom Domain Guide](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)

## ✅ Checklist

Before deploying:

- [ ] All HTML files validated
- [ ] CSS loads correctly
- [ ] All internal links work
- [ ] Images load properly
- [ ] Mobile responsive design tested
- [ ] Browser compatibility checked
- [ ] 404 page exists
- [ ] README.md updated
- [ ] GitHub Actions workflow configured

## 🎉 Success!

Once deployed, your documentation will be live at:

```
https://yourusername.github.io/repository-name/
```

Share this URL in your README and package documentation!
