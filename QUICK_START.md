# 🚀 Quick Start Guide - CDCT Website

## Getting Your Site Live in 30 Minutes

Follow these simple steps to get your website online today!

### ⏱️ Phase 1: Upload to GitHub (10 minutes)

1. **Create GitHub Account**
   - Go to https://github.com/signup
   - Choose a username, enter email, create password
   - Verify your email

2. **Create New Repository**
   - Click the "+" in top right → "New repository"
   - Name: `cdct-website`
   - Description: "Ceres & District Community Trust website"
   - Keep it PUBLIC (required for free Netlify)
   - Click "Create repository"

3. **Upload Your Files**
   
   **Easiest Method - Web Upload:**
   - Download the cdct-website folder to your computer
   - On GitHub, click "uploading an existing file"
   - Drag ALL files from cdct-website folder into the upload box
   - Scroll down, click "Commit changes"
   - Done! ✅

### ⏱️ Phase 2: Deploy to Netlify (10 minutes)

1. **Sign Up for Netlify**
   - Go to https://app.netlify.com/signup
   - Click "Continue with GitHub" (easiest!)
   - Authorize Netlify

2. **Deploy Your Site**
   - Click "Add new site" → "Import an existing project"
   - Click "GitHub"
   - Find and click on `cdct-website`
   - Click "Deploy cdct-website"
   - Wait 1-2 minutes... ☕
   - Your site is LIVE! 🎉

3. **Get Your URL**
   - You'll see something like: `https://cheerful-moonlight-123456.netlify.app`
   - This is your website! Click it to visit

### ⏱️ Phase 3: Enable CMS Access (10 minutes)

1. **Enable Identity**
   - In Netlify, go to Site Settings (bottom left)
   - Click "Identity" in the menu
   - Click "Enable Identity"

2. **Configure Identity**
   - Scroll to "Registration preferences"
   - Select "Invite only" (important for security!)
   - Click "Save"

3. **Enable Git Gateway**
   - Still in Identity settings
   - Scroll to "Services"
   - Click "Enable Git Gateway"

4. **Invite Yourself**
   - Click "Identity" tab at the top
   - Click "Invite users"
   - Enter your email address
   - Check your email
   - Click the invite link
   - Set your password
   - Done! ✅

5. **Test CMS Access**
   - Go to: `yoursite.netlify.app/admin/`
   - Log in with your email and password
   - Try editing the Home page
   - Click Save → Publish
   - Wait 30 seconds
   - Refresh your homepage - see your changes! 🎉

---

## ✅ You're Done! What's Next?

### Immediate Tasks

1. **Update Site Content**
   - Log into `yoursite.com/admin/`
   - Update the About page with real committee members
   - Delete the example project
   - Edit the welcome news post

2. **Test the Forms**
   - Go to Volunteers page
   - Fill out and submit the form
   - Check Netlify Dashboard → Forms to see the submission

3. **Customize Your Site Name**
   - Netlify: Site Settings → Site details
   - Click "Change site name"
   - Choose something like: `ceres-community-trust`
   - Your site is now: `ceres-community-trust.netlify.app`

### Within First Week

1. **Set Up Google Sheets Connection**
   - Sign up for free Zapier: https://zapier.com
   - Create Zap: Netlify Forms → Google Sheets
   - See README.md for detailed instructions

2. **Invite Other Volunteers**
   - Netlify → Identity → Invite users
   - They can log into /admin/ to edit content
   - No coding knowledge needed!

3. **Add Real Content**
   - Upload committee photos
   - Add current projects
   - Write welcome news posts
   - Update contact information

### Within First Month

1. **Set Up Stripe** (if ready to accept payments)
   - Create Stripe account: https://stripe.com
   - Create payment links for memberships
   - Update membership.md with your Stripe URLs
   - See README.md for full Stripe guide

2. **Get a Custom Domain** (optional but recommended)
   - Buy domain: ~£10-15/year
   - Suggestions: `cerestrust.org.uk`, `cdct.org.uk`
   - Connect in Netlify: Site Settings → Domain Management

3. **Train Volunteers**
   - Show them /admin/ interface
   - Teach how to add news posts
   - Demonstrate image uploads
   - Practice editing existing pages

---

## 🆘 Common Issues & Solutions

### "I can't log into /admin/"
- ✅ Did you enable Netlify Identity? (See Phase 3, step 1)
- ✅ Did you accept the email invite and set a password?
- ✅ Try going directly to: `yoursite.netlify.app/admin/`
- ✅ Clear your browser cache and try again

### "My changes aren't showing"
- ✅ Did you click both "Save" AND "Publish" in the CMS?
- ✅ Wait 30-60 seconds for rebuild
- ✅ Hard refresh: Ctrl+Shift+R (Windows) or Cmd+Shift+R (Mac)

### "Forms aren't working"
- ✅ Netlify automatically detects forms on first deploy
- ✅ Check: Site Dashboard → Forms tab
- ✅ Submissions appear there even without Google Sheets connection

### "Site build failed"
- ✅ Check: Site Dashboard → Deploys → Click failed deploy
- ✅ Read the error message
- ✅ Usually a typo in a .md file
- ✅ Fix in /admin/ or GitHub, then redeploy

---

## 📞 Need Help?

1. **Read the full README.md** - has detailed instructions for everything
2. **Check Netlify Docs** - https://docs.netlify.com
3. **Hugo Documentation** - https://gohugo.io/documentation/
4. **Decap CMS Docs** - https://decapcms.org/docs/

---

## 🎉 Congratulations!

You now have a professional website that:
- ✅ Costs £0/month (or ~£1/month with domain)
- ✅ Volunteers can edit without coding
- ✅ Has forms that collect data
- ✅ Can accept payments (when you set up Stripe)
- ✅ Is fast, secure, and mobile-friendly
- ✅ Automatically saves all content to GitHub

**Your community trust is now online! 🌟**

---

**Next Step**: Open README.md for the complete guide including Stripe setup, form integration, and advanced customization!
