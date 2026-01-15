# Skirk Bot Website - Deployment Guide

## 🚀 Quick Deployment Options

### 1. Vercel (Recommended - Easiest)

**Why Vercel?**
- Created by the Next.js team
- Zero configuration needed
- Automatic HTTPS
- Free tier available
- Perfect for Next.js apps
- Automatic previews on every push

**Steps:**

1. **Push to GitHub**
   ```bash
   # Initialize git if not already
   git init
   git add .
   git commit -m "Initial commit"

   # Add remote (replace with your repo)
   git remote add origin https://github.com/YOUR_USERNAME/skirk-bot-website.git

   # Push
   git branch -M main
   git push -u origin main
   ```

2. **Deploy to Vercel**

   a. Go to [vercel.com](https://vercel.com)
   b. Sign up or log in with GitHub
   c. Click "Add New Project"
   d. Import your GitHub repository
   e. Click "Deploy"

   That's it! Vercel handles everything automatically!

3. **Add Environment Variables**

   a. Go to your Vercel project → Settings → Environment Variables
   b. Add these variables:

   ```
   DISCORD_WEBHOOK_URL=https://discord.com/api/webhooks/YOUR_ID/YOUR_TOKEN
   # OR
   DISCORD_BOT_TOKEN=your_bot_token
   DISCORD_CHANNEL_ID=your_channel_id
   ```

4. **Get Your URL**

   - Your site will be at: `https://your-project-name.vercel.app`
   - You can add custom domain in project settings

---

### 2. Netlify

**Steps:**

1. **Build the Project**
   ```bash
   bun install
   bun run build
   ```

2. **Deploy via Netlify**

   a. Go to [netlify.com](https://netlify.com)
   b. Sign up or log in
   c. Click "Add new site"
   d. Choose "Deploy manually"
   e. Drag and drop the `.next` folder (or select it)

3. **Add Environment Variables**

   - Site Settings → Build & deploy → Environment
   - Add Discord variables

4. **Add Custom Domain** (optional)

---

### 3. GitHub Pages

**Steps:**

1. **Update `package.json`**

   Add this to your scripts:
   ```json
   {
     "scripts": {
       "export": "next build && next export"
     }
   }
   ```

2. **Build and Export**
   ```bash
   bun run export
   ```

3. **Push to GitHub**

   - Push the `out` folder to your repository
   - Enable GitHub Pages in repo settings

**Note:** This approach doesn't support all Next.js features (API routes won't work).

---

### 4. Railway

**Steps:**

1. **Install Railway CLI**
   ```bash
   npm install -g @railway/cli
   ```

2. **Login and Deploy**
   ```bash
   railway login
   railway deploy
   ```

3. **Add Environment Variables**

   - Railway dashboard → Variables
   - Add Discord variables

---

### 5. Render

**Steps:**

1. **Create Account**

   - Go to [render.com](https://render.com)
   - Sign up

2. **Create New Web Service**

   - Click "New +"
   - Choose "Web Service"
   - Connect your GitHub repository
   - Select Next.js as framework

3. **Add Environment Variables**

   - Build & Deploy → Environment
   - Add Discord variables

---

## 🔧 Pre-Deployment Checklist

### Must-Have Before Deploying

- [ ] **Environment Variables Set**
  - [ ] DISCORD_WEBHOOK_URL or DISCORD_BOT_TOKEN + DISCORD_CHANNEL_ID
  - [ ] Test contact form locally first

- [ ] **Git Repository Ready**
  - [ ] All changes committed
  - [ ] `.gitignore` includes:
    - `node_modules`
    - `.env`
    - `.next`
    - `dist`
    - `.env.local`

- [ ] **Production Build Tested**
  ```bash
  bun run build
  ```
  - [ ] No errors
  - [ ] Build succeeds

- [ ] **Domain Configured** (optional)
  - [ ] Custom domain purchased
  - [ ] DNS settings ready

---

## 📋 Environment Variables Reference

Add these in your hosting platform's environment settings:

### For Contact Form (Choose ONE method):

**Method 1: Webhook (Recommended)**
```bash
DISCORD_WEBHOOK_URL=https://discord.com/api/webhooks/1234567890/AbCdEfGhIjKlMnOpQrStUvWxYz
```

**Method 2: Bot Token**
```bash
DISCORD_BOT_TOKEN=MTIyMzQ1NjM.XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
DISCORD_CHANNEL_ID=1234567890123456789
```

### Optional Variables:
```bash
NODE_ENV=production
```

---

## 🎯 Vercel Deployment (Step-by-Step with Screenshots)

### Step 1: Prepare Your Code

```bash
# Make sure you're in the project directory
cd /path/to/my-project

# Install dependencies (if not already)
bun install

# Test build locally
bun run build
```

### Step 2: Initialize Git (if not already)

```bash
git init
git add .
git commit -m "Initial commit - Skirk Bot website"
```

### Step 3: Create GitHub Repository

1. Go to [github.com](https://github.com) and sign in
2. Click the "+" icon → "New repository"
3. Name it: `skirk-bot-website` (or your preferred name)
4. Make it "Public" or "Private"
5. Click "Create repository"

### Step 4: Push to GitHub

```bash
# Add your GitHub repository as remote
git remote add origin https://github.com/YOUR_USERNAME/skirk-bot-website.git

# Push code
git branch -M main
git push -u origin main
```

### Step 5: Deploy to Vercel

1. Go to [vercel.com](https://vercel.com)
2. Click "Sign Up" (use GitHub for easiest auth)
3. Click "Add New Project"
4. You'll see your GitHub repositories
5. Find and click on `skirk-bot-website`
6. Click "Deploy"

Vercel will:
- Build your project
- Run all tests
- Deploy to edge network
- Give you a URL like: `https://skirk-bot-website.vercel.app`

### Step 6: Add Environment Variables

1. Go to your Vercel project
2. Click "Settings" tab
3. Click "Environment Variables"
4. Add these (one by one):

**Key 1:**
- Name: `DISCORD_WEBHOOK_URL`
- Value: `https://discord.com/api/webhooks/YOUR_ID/YOUR_TOKEN`
- Environments: Production, Preview, Development

Click "Save"

**OR Key 2 & 3:**
- Name: `DISCORD_BOT_TOKEN`
- Value: `your_bot_token`
- Environments: Production, Preview, Development

Click "Save"

- Name: `DISCORD_CHANNEL_ID`
- Value: `your_channel_id`
- Environments: Production, Preview, Development

Click "Save"

### Step 7: Redeploy

After adding environment variables:
1. Go to "Deployments" tab
2. Click the three dots (⋯) on latest deployment
3. Click "Redeploy"

### Step 8: Test Your Live Site

1. Open your Vercel URL
2. Test all sections:
   - [ ] Hero loads
   - [ ] Showcase with phone/laptop
   - [ ] Features cards
   - [ ] Commands section
   - [ ] Reactions with GIFs
   - [ ] Premium pricing
   - [ ] **Contact form** - submit a test message
   - [ ] Check Discord for the message!
   - [ ] Policy section
   - [ ] Footer links work
3. Test mobile responsive view

---

## 🌐 Custom Domain Setup (Vercel)

### Option 1: Use Vercel Domain

1. Project Settings → Domains
2. Click "Add" next to "Production Domain"
3. Enter: `skirkbot.your-domain.com`
4. Follow DNS instructions provided

### Option 2: Bring Your Own Domain

1. Buy a domain (Namecheap, GoDaddy, etc.)
2. Go to Vercel → Domains → Add
3. Enter your domain
4. Update DNS records at your domain registrar:
   ```
   Type: CNAME
   Name: @
   Value: cname.vercel-dns.com
   ```

---

## 🔒 Security Checklist

### Before Production Deployment

- [ ] **Remove Sensitive Data from Code**
  - [ ] No hardcoded API keys
  - [ ] No hardcoded Discord tokens
  - [ ] `.env` not committed to git

- [ ] **Enable HTTPS**
  - Vercel: Automatic ✅
  - Other platforms: Check SSL settings

- [ ] **Set Rate Limiting**
  - Consider rate-limiting contact form
  - Vercel has built-in protection

- [ ] **Monitor Analytics**
  - Set up Vercel Analytics (free)
  - Track page views and errors

---

## 📊 Monitoring Your Deployment

### Vercel Dashboard

After deployment:

1. Go to your project on Vercel
2. Check tabs:
   - **Overview**: See recent deployments
   - **Analytics**: Page views, visitors
   - **Logs**: Error logs and performance
   - **Settings**: Environment variables, domains

### Common Issues & Fixes

**Issue: Contact form not sending**
- Check environment variables are set correctly
- Test Discord webhook URL in Postman
- Check Vercel logs for errors

**Issue: Images not loading**
- Check image URLs are HTTPS
- Verify images are not broken
- Check CORS settings

**Issue: Build fails**
- Check package.json dependencies
- Verify all imports are correct
- Check for syntax errors in code

---

## 🔄 CI/CD with Vercel (Automatic Deployments)

### Setup Automatic Deployments

With Vercel connected to GitHub:

- Every `git push` triggers new build
- Builds are tested automatically
- Successful builds deploy automatically
- Preview deployments for every pull request

### How It Works

```bash
# Make changes locally
git add .
git commit -m "Add new feature"
git push

# Vercel automatically:
# 1. Detects push
# 2. Starts build
# 3. Runs tests
# 4. Deploys if successful
# 5. Sends you the URL
```

---

## 💰 Pricing Comparison

| Platform | Free Tier | Build Time | Custom Domain | Best For |
|----------|-----------|-------------|---------------|----------|
| **Vercel** | 100GB/mo | ~1 min | Free | Next.js apps ⭐ |
| **Netlify** | 100GB/mo | ~2 min | Free | Static sites |
| **Railway** | 500hrs/mo | ~2 min | Paid | Small apps |
| **Render** | 750hrs/mo | ~3 min | Free | Full-stack apps |
| **GitHub Pages** | 1GB total | N/A | Free | Static sites only |

---

## 📞 Deployment Troubleshooting

### Build Failures

**Error: "Module not found"**
```bash
# Clear cache and reinstall
rm -rf node_modules
bun install
```

**Error: "TypeScript errors"**
```bash
# Fix TypeScript errors and rebuild
bun run build
```

### Runtime Errors

**Error: "API 404"**
- Verify API files are in `/src/app/api/`
- Check file names are `route.ts`
- Ensure correct import paths

**Error: "Discord webhook fails"**
- Test webhook URL manually
- Check webhook exists in Discord
- Verify bot has permissions

---

## 🎉 Post-Deployment Checklist

After your site is live:

- [ ] Test all navigation links
- [ ] Test contact form (check Discord!)
- [ ] Test mobile responsiveness
- [ ] Test in multiple browsers (Chrome, Firefox, Safari)
- [ ] Check page load speed
- [ ] Set up analytics (optional)
- [ ] Add custom domain (optional)
- [ ] Share with your community!
- [ ] Update social links if changed

---

## 📱 Testing Checklist

### Desktop
- [ ] Chrome/Edge
- [ ] Firefox
- [ ] Safari

### Mobile
- [ ] iOS Safari
- [ ] Android Chrome
- [ ] Mobile responsive view

### Features
- [ ] Contact form submits
- [ ] Discord message received
- [ ] Theme toggle works
- [ ] Back to top button
- [ ] Smooth scrolling
- [ ] All animations play

---

## 📞 Getting Help

### Vercel Support
- [Vercel Dashboard](https://vercel.com/dashboard)
- [Documentation](https://vercel.com/docs)
- [Status Page](https://www.vercel-status.com)

### Community Resources
- [Next.js Docs](https://nextjs.org/docs)
- [Vercel Examples](https://vercel.com/templates)
- [Discord Community](https://discord.gg/ApE66m9FVu)

---

## 🚀 Quick Start Command Summary

```bash
# Complete deployment to Vercel in 4 commands:

# 1. Install and build
bun install && bun run build

# 2. Commit changes
git add . && git commit -m "Deploy Skirk Bot website"

# 3. Push to GitHub
git push

# 4. Go to vercel.com and click "Deploy"
```

That's it! Your Skirk Bot website will be live in minutes! 🎉
