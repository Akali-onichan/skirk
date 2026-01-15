# ⚡ VS Code Deployment Guide - Super Fast!

## 🎯 EASIEST: Vercel Deployment (5 Minutes)

### Prerequisites
- [ ] VS Code installed
- [ ] GitHub account
- [ ] Discord webhook URL or bot token
- [ ] 5 minutes of time
- [ ] Build errors fixed ✅ (just completed for you!)

---

## 🚀 Step-by-Step Deployment

### Step 1: Open in VS Code

```bash
# Navigate to your project
cd /home/z/my-project

# Or open in VS Code
code .
```

### Step 2: Push to GitHub (with updated code!)

**I've already fixed the build issues for you:**
- ✅ Removed `output: "standalone"` from next.config.ts
- ✅ Simplified build script in package.json
- ✅ Added vercel.json for proper deployment

```bash
# Initialize git (if first time)
git init
git add .
git commit -m "Deploy Skirk Bot website - Fixed build config"

# Add GitHub remote (paste your repo URL)
git remote add origin https://github.com/YOUR_USERNAME/skirk-bot-website.git

# Push to GitHub
git branch -M main
git push -u origin main
```

**Option A: GitHub Integration (Recommended) - FIXED & WORKING!**

1. Go to [vercel.com/new](https://vercel.com/new)
2. Click "Continue with GitHub"
3. Authorize Vercel to access your repositories
4. Find and select `skirk-bot-website`
5. Click "Deploy"

**That's it! The build issues are fixed!** 🎉

Wait 1-2 minutes and your site is live!

**Option B: Manual Deploy**

1. Go to [vercel.com/dashboard](https://vercel.com/dashboard)
2. Click "Add New Project"
3. Select "Continue with GitHub"
4. Import your repository
5. Click "Deploy"

### Step 5: Add Discord Webhook (Crucial!)

1. After deployment, go to your Vercel project
2. Click "Settings" → "Environment Variables"
3. Add this:

**Key:** `DISCORD_WEBHOOK_URL`
**Value:** Your Discord webhook URL
**Environments:** ✅ Production ✅ Preview ✅ Development

Click "Save"

4. Go to "Deployments" → Click "⋯" → "Redeploy"

### Step 6: Test Contact Form!

1. Open your new site (Vercel will show the URL)
2. Scroll to "Contact" section
3. Fill out the form:
   - Name: Test User
   - Email: test@example.com
   - Message: This is a test message from my deployed site!
4. Click "Send Message"
5. Check your Discord channel

**You should receive a beautiful embed with the message!** ✅

---

## 🎨 Custom Domain (Optional)

### Add Your Domain in Vercel

1. Go to Vercel project → "Settings" → "Domains"
2. Click "Add"
3. Enter your domain (e.g., `skirkbot.com`)
4. Follow DNS instructions shown

### Update DNS at Your Domain Registrar

**If using Namecheap:**
- Type: CNAME
- Host: @
- Value: `cname.vercel-dns.com`

**If using GoDaddy:**
- Type: CNAME (Alias)
- Host: @
- Points to: `cname.vercel-dns.com`

---

## 🔧 VS Code Extensions (Recommended)

Install these for better development:

```bash
# Install in VS Code
1. ESLint
2. Prettier - Code formatter
3. Tailwind CSS IntelliSense
4. Auto Rename Tag
5. GitHub Pull Requests
```

---

## 📞 Common Issues & Quick Fixes

### Issue: git push fails with "Permission denied"

**Fix:**
```bash
# Check your git remote
git remote -v

# Update with correct URL
git remote set-url origin https://github.com/YOUR_USERNAME/skirk-bot-website.git

# Try again
git push
```

### Issue: Vercel build fails

**Fix:**
```bash
# Test build locally first
bun run build

# If errors, fix them before pushing
# Common issues:
# - Missing dependencies → bun install
# - TypeScript errors → Fix in code
```

### Issue: Contact form not working on Vercel

**Fix:**
1. Check environment variables are set in Vercel
2. Redeploy after adding variables
3. Check Vercel logs for errors
4. Test webhook URL manually in browser or Postman

---

## 🔄 Updating Your Site (Future Changes)

### Make Changes in VS Code

1. Edit files in VS Code
2. See live preview with:
   ```bash
   bun run dev
   ```

### Deploy Updates

```bash
# Commit changes
git add .
git commit -m "Update feature"

# Push to GitHub
git push

# Vercel automatically detects and deploys!
```

That's it - no manual deployment needed!

---

## 📱 Share Your Site

### Your URLs

- **Vercel URL:** Provided after deployment
- **Custom Domain:** If you added one

### Where to Share

- Discord server ✅
- Top.gg bot page ✅
- Social media ✅
- GitHub README ✅

---

## 🎉 Success Checklist

After deployment, verify:

- [ ] Site loads without errors
- [ ] All sections display correctly
- [ ] Contact form works (check Discord!)
- [ ] Theme toggle works
- [ ] Mobile looks good
- [ ] Links go to right places
- [ ] Images load properly
- [ ] No console errors
- [ ] SEO meta tags are correct

---

## 💡 Pro Tips

### Tip 1: Use GitHub Branches

```bash
# Create a branch for new features
git checkout -b new-feature

# Work on it
# When done, commit and push
git push origin new-feature

# Go to GitHub and create Pull Request
# Vercel will deploy preview of PR automatically!
```

### Tip 2: Keep Dependencies Updated

```bash
# Check for updates
bun outdated

# Update specific package
bun update package-name

# Update all packages
bun update
```

### Tip 3: Monitor Performance

Vercel provides:
- **Analytics** - Track visitors
- **Logs** - See errors
- **Speed** - Monitor load times

Check these regularly!

---

## 📞 Need Help?

### Documentation Links

- [Vercel Docs](https://vercel.com/docs)
- [Next.js Docs](https://nextjs.org/docs)
- [GitHub Guides](https://guides.github.com/)
- [DISCORD_SETUP.md](./DISCORD_SETUP.md) - Discord integration guide

### Support

- Check [Vercel Status](https://www.vercel-status.com)
- Join our [Discord](https://discord.gg/ApE66m9FVu)

---

## 🎯 Quick Reference

### Commands You'll Use

```bash
# Development
bun run dev              # Start dev server

# Build
bun run build           # Build for production

# Lint
bun run lint            # Check code quality

# Git
git add .               # Stage changes
git commit -m "msg"     # Commit changes
git push                # Push to GitHub
```

### Environment Variables

```bash
# In Vercel Settings → Environment Variables:
DISCORD_WEBHOOK_URL=your_webhook_url_here
```

---

**That's everything you need!** 🚀

Deploy in 5 minutes with Vercel, test the contact form, and share your beautiful Skirk Bot website with the world! ✨
