# TODO: Manual Intervention Required

This file contains tasks that require your manual intervention to complete the website deployment.

## 🔧 Configuration Tasks

### 1. Cloudflare Workers Deployment Setup
- [ ] **Create a Cloudflare account** (if you don't have one)
  - Visit: https://dash.cloudflare.com/sign-up
  
- [ ] **Install Wrangler CLI** (if not already installed)
  ```bash
  npm install -g wrangler
  ```

- [ ] **Authenticate with Cloudflare**
  ```bash
  wrangler login
  ```

- [ ] **Update wrangler.toml with your project details**
  - Edit the `name` field if you want a different project name
  - The current name is `personal-website`
  
- [ ] **Configure custom domain** (optional)
  - Uncomment and update the routes section in `wrangler.toml`
  - Add your domain name
  - Configure DNS settings in Cloudflare dashboard

- [ ] **Deploy to Cloudflare Pages**
  ```bash
  npm run build
  wrangler pages deploy dist
  ```

### 2. Content Updates

- [ ] **Update personal information** in `src/pages/index.astro`
  - Line 147: Replace `your.email@example.com` with your actual email address
  - Update LinkedIn and GitHub URLs if they're different
  - Review and customize the About Me section (lines 49-63)

- [ ] **Update GitHub username** in `src/components/GitHubRepos.astro`
  - Line 20: Change `JashandeepJustinBains` to your GitHub username
  - This will automatically fetch your public repositories

- [ ] **Add certifications** in `src/components/Certifications.astro`
  - Lines 3-25: Replace placeholder certification URLs with your actual Credly badge links
  - Update dates and certification details
  - Add or remove certifications as needed

- [ ] **Update homelab topology** in `src/components/NetworkTopology.astro`
  - Lines 191-329: Customize nodes to match your actual homelab infrastructure
  - Update server names, specs, and configurations
  - Modify edges (connections) to reflect your network topology
  - Line 526: Update GitHub homelab repository URL

### 3. Resume File

- [ ] **Add your resume PDF**
  - Place your resume file at: `public/resume.pdf`
  - Ensure the file is named exactly `resume.pdf` or update the link in `src/pages/index.astro` (line 122)

### 4. Favicon and Branding

- [ ] **Replace favicon**
  - Current: `public/favicon.svg`
  - Create or add your own favicon
  - Supports SVG, ICO, or PNG formats

### 5. Site Configuration

- [ ] **Update site URL** in `astro.config.mjs`
  - Line 6: Change `https://jashandeepjustinbains.github.io` to your domain
  - Line 7: Update or remove the `base` path if not using GitHub Pages
  - For Cloudflare Pages, you may want to remove the `base` property entirely

### 6. SEO and Metadata

- [ ] **Update structured data** in `src/pages/index.astro`
  - Lines 10-30: Update the JSON-LD schema with your information
  - Add your actual URLs, skills, and professional details

### 7. Environment Variables (Optional)

- [ ] **Add environment variables** if needed
  - Create `.env` file for local development
  - Add variables in Cloudflare dashboard for production
  - Update `wrangler.toml` [vars] section if needed

## 🎨 Design Customization (Optional)

### Color Scheme
- [ ] **Adjust colors** if needed in `src/styles/global.css`
  - Lines 13-25: Primary and secondary colors
  - The current scheme uses blue (#2563eb) as primary
  - Off-white (#fafafa) background with white (#ffffff) cards

### Typography
- [ ] **Change fonts** if desired in `src/styles/global.css`
  - Line 44: System font stack
  - Consider adding Google Fonts or custom fonts

### Spacing and Layout
- [ ] **Adjust spacing scale** if needed in `src/styles/global.css`
  - Lines 77-87: Spacing scale (4px increments)

## 📝 Testing

- [ ] **Test locally**
  ```bash
  npm run dev
  ```
  - Visit http://localhost:4321/personal-website (or without /personal-website if base is removed)

- [ ] **Test build**
  ```bash
  npm run build
  npm run preview
  ```

- [ ] **Test all links**
  - Certification badge links
  - GitHub profile link
  - LinkedIn profile link
  - Email link
  - Resume download link

- [ ] **Test responsive design**
  - Mobile devices
  - Tablets
  - Desktop screens

## 🚀 Deployment

### Option 1: Cloudflare Pages (Recommended)
```bash
# Build the site
npm run build

# Deploy with Wrangler
wrangler pages deploy dist
```

### Option 2: Cloudflare Pages with Git Integration
1. Push your code to GitHub
2. Go to Cloudflare Dashboard → Pages
3. Connect your GitHub repository
4. Set build command: `npm run build`
5. Set build output directory: `dist`
6. Deploy!

### Option 3: Keep GitHub Pages
If you prefer to keep using GitHub Pages instead:
1. Remove the Cloudflare adapter: `npm uninstall @astrojs/cloudflare`
2. Keep the current `astro.config.mjs` settings
3. Push to GitHub and enable GitHub Pages in repository settings

## 📊 Analytics (Optional)

- [ ] **Add analytics** if desired
  - Google Analytics
  - Cloudflare Web Analytics (free and privacy-friendly)
  - Plausible Analytics
  - Add tracking script to `src/layouts/BaseLayout.astro`

## 🔒 Security

- [ ] **Review security headers** in Cloudflare dashboard
  - Enable HTTPS
  - Set up security headers (CSP, HSTS, etc.)
  - Configure rate limiting if needed

## 📱 Social Media Integration

- [ ] **Add Open Graph images**
  - Create a social sharing image (1200x630px recommended)
  - Add to `public/` folder
  - Update meta tags in `src/layouts/BaseLayout.astro`

- [ ] **Update social media links**
  - Ensure all social profile URLs are correct
  - Add additional social profiles if desired

## ✅ Final Checklist

Before going live:
- [ ] All personal information is updated
- [ ] All links work correctly
- [ ] Resume file is uploaded
- [ ] Certifications are current
- [ ] GitHub repositories are displaying
- [ ] Site is responsive on all devices
- [ ] No console errors in browser
- [ ] DNS is configured (if using custom domain)
- [ ] SSL certificate is active
- [ ] Analytics are tracking (if implemented)

---

## 📚 Additional Resources

- **Astro Documentation**: https://docs.astro.build
- **Cloudflare Pages Docs**: https://developers.cloudflare.com/pages
- **Wrangler CLI Docs**: https://developers.cloudflare.com/workers/wrangler/
- **Cloudflare Web Analytics**: https://www.cloudflare.com/web-analytics/

## 🆘 Support

If you need help:
1. Check the Astro Discord: https://astro.build/chat
2. Cloudflare Community: https://community.cloudflare.com/
3. Review the README.md for basic setup instructions

---

**Last Updated**: 2025-01-20
