# 📁 Complete Website Package - File Index

## 🎉 Your CDCT Website Is Ready!

This folder contains everything you need for a complete, professional charity website.

---

## 📖 Start Here Documents (READ THESE FIRST!)

### 1. **START_HERE.md** ⭐ READ THIS FIRST
Complete overview of what you've got and what to do next. Start here!

### 2. **QUICK_START.md** 🚀
30-minute guide to get your site live today. Follow this step-by-step.

### 3. **README.md** 📚
Complete technical documentation with all the details.

---

## 📋 Setup Guides (Follow As Needed)

### 4. **STRIPE_SETUP.md** 💳
How to accept membership payments and donations (30-45 min)

### 5. **GOOGLE_SHEETS_SETUP.md** 📊
Connect forms to automatically fill spreadsheets (20-30 min)

### 6. **VOLUNTEER_GUIDE.md** 👥
Give this to volunteers who will edit the website content

---

## 🌐 Website Files

### Configuration Files

- **hugo.toml** - Main site configuration (name, prices, menu)
- **netlify.toml** - Deployment settings for Netlify
- **.gitignore** - Tells Git which files to ignore

### Design & Styling

- **assets/css/main.css** - All the styling (warm, earthy colors)

### Content Pages

All in `/content/` folder - these are what volunteers will edit:

- **_index.md** - Home page content
- **about.md** - Committee and about page
- **volunteers.md** - Volunteer signup with form
- **membership.md** - Membership page with Stripe buttons
- **donors.md** - Donation page with recognition
- **news/_index.md** - News section index
- **news/welcome-to-new-website.md** - Example news post
- **projects/_index.md** - Projects section index  
- **projects/village-green-restoration.md** - Example project

### HTML Templates

In `/layouts/` folder - these create the website structure:

- **_default/baseof.html** - Base template for all pages
- **_default/single.html** - Template for individual pages
- **_default/list.html** - Template for list pages (news, projects)
- **index.html** - Home page template with hero section
- **partials/header.html** - Site header with navigation
- **partials/footer.html** - Site footer

### CMS (Content Management)

In `/static/admin/` folder:

- **config.yml** - CMS configuration (what volunteers can edit)
- **index.html** - Admin login page (yoursite.com/admin/)

---

## 📊 File Count Summary

Total files: **27**

Breakdown:
- Documentation: 6 markdown guides
- Configuration: 3 files
- Content pages: 8 markdown files
- HTML templates: 6 files
- CSS: 1 stylesheet
- CMS: 2 files
- Git: 1 .gitignore

---

## 🎯 What Each File Does

### Core Files (Don't Delete These!)

| File | Purpose | Who Edits |
|------|---------|-----------|
| hugo.toml | Site settings, menu, prices | Tech admin |
| netlify.toml | How site deploys | Don't touch |
| assets/css/main.css | All styling | Tech admin (to change colors) |
| layouts/* | Page templates | Advanced only |
| static/admin/config.yml | CMS settings | Tech admin |

### Content Files (Volunteers Edit These!)

| File | Purpose | Edit Via |
|------|---------|----------|
| content/_index.md | Home page | CMS or direct |
| content/about.md | About/committee | CMS or direct |
| content/volunteers.md | Volunteer page | CMS or direct |
| content/membership.md | Membership | CMS or direct |
| content/donors.md | Donors page | CMS or direct |
| content/news/*.md | News posts | CMS - easy! |
| content/projects/*.md | Projects | CMS - easy! |

---

## 🗺️ Directory Structure

```
cdct-website/
│
├── Documentation (Read First!)
│   ├── START_HERE.md ⭐
│   ├── QUICK_START.md 🚀
│   ├── README.md
│   ├── STRIPE_SETUP.md
│   ├── GOOGLE_SHEETS_SETUP.md
│   └── VOLUNTEER_GUIDE.md
│
├── Configuration
│   ├── hugo.toml
│   ├── netlify.toml
│   └── .gitignore
│
├── assets/
│   └── css/
│       └── main.css (Warm, earthy styling)
│
├── content/ (Your pages!)
│   ├── _index.md (Home)
│   ├── about.md
│   ├── volunteers.md
│   ├── membership.md
│   ├── donors.md
│   ├── news/
│   │   ├── _index.md
│   │   └── welcome-to-new-website.md
│   └── projects/
│       ├── _index.md
│       └── village-green-restoration.md
│
├── layouts/ (HTML templates)
│   ├── _default/
│   │   ├── baseof.html
│   │   ├── single.html
│   │   └── list.html
│   ├── index.html
│   └── partials/
│       ├── header.html
│       └── footer.html
│
└── static/
    ├── admin/ (CMS)
    │   ├── config.yml
    │   └── index.html
    ├── images/ (Empty - add images here)
    └── js/ (Empty - for future use)
```

---

## 🎨 Customization Points

### Easy Changes (Anyone Can Do)

**Change site name/title:**
- Edit `hugo.toml` → change `title` line

**Update contact email:**
- Edit `hugo.toml` → change `email` under [params]

**Change membership prices:**
- Edit `hugo.toml` → change `lifetimeMembership` and `annualMembership`

**Update content:**
- Use the CMS at `yoursite.com/admin/` after deployment

### Design Changes (Need CSS Knowledge)

**Change colors:**
- Edit `assets/css/main.css`
- Look for `:root` section at top
- Change color codes (e.g., `--primary-color: #8B6F47;`)

**Current color scheme:**
- Primary: #8B6F47 (Warm brown)
- Accent: #6B8E23 (Olive green)
- Background: #FDFBF7 (Warm off-white)

### Advanced Changes (Need HTML/Hugo Knowledge)

**Change page layouts:**
- Edit files in `/layouts/` folder
- Requires understanding of Hugo templating

**Add new sections:**
- Create new .md files in `/content/`
- Update menu in `hugo.toml`

---

## ✅ Pre-Deployment Checklist

Before uploading to GitHub and deploying:

### Must Do:
- [ ] Read START_HERE.md
- [ ] Read QUICK_START.md
- [ ] Have GitHub account ready
- [ ] Have Netlify account ready

### Should Do:
- [ ] Update charity registration number (in about.md)
- [ ] Add real committee names (in about.md)  
- [ ] Update contact email (in hugo.toml)
- [ ] Delete or edit example project
- [ ] Delete or edit example news post

### Can Do Later:
- [ ] Set up Stripe (STRIPE_SETUP.md)
- [ ] Connect Google Sheets (GOOGLE_SHEETS_SETUP.md)
- [ ] Get custom domain
- [ ] Add photos

---

## 🚀 Deployment Path

**Follow this order:**

1. **Read START_HERE.md** (5 min)
2. **Follow QUICK_START.md** (30 min)
   - Upload to GitHub
   - Deploy to Netlify
   - Enable CMS login
3. **Test everything** (10 min)
   - Visit site
   - Try logging into /admin/
   - Submit test forms
4. **Then when ready:**
   - STRIPE_SETUP.md (for payments)
   - GOOGLE_SHEETS_SETUP.md (for forms)

---

## 📞 Support & Help

### If Stuck During Setup:

1. **Check the relevant guide** - detailed troubleshooting in each
2. **Look for error messages** - usually tell you what's wrong
3. **Try in incognito** - rules out browser cache issues
4. **Search the error** - Google + error message often helps

### Common Issues:

- "Can't log into CMS" → Did you enable Netlify Identity?
- "Site not building" → Check deploy logs in Netlify
- "Forms not working" → Takes one deploy to activate
- "Changes not showing" → Wait 60 seconds, hard refresh

### Resources:

- Hugo docs: https://gohugo.io/documentation/
- Netlify docs: https://docs.netlify.com/
- Decap CMS: https://decapcms.org/docs/
- Stripe: https://stripe.com/docs

---

## 💰 Cost Breakdown

### Completely Free (Recommended Start):
- Website hosting: FREE (Netlify)
- CMS: FREE (Decap CMS)
- Forms: FREE (100/month)
- Git hosting: FREE (GitHub)
- **Total: £0/month**

### With Custom Domain:
- Everything above: FREE
- Domain: £10-15/year
- **Total: ~£1/month**

### If Adding Premium Features:
- Stripe fees: 2.9% + 30p per transaction
- More forms: £20/month (if over 100)
- **Total: £1-25/month depending on usage**

---

## 🎊 What Makes This Special

### For Your Charity:
✅ Professional web presence  
✅ Accepts payments online  
✅ Volunteers can edit easily  
✅ Collects data automatically  
✅ Costs almost nothing  
✅ No technical maintenance  

### For Volunteers:
✅ Edit like WordPress  
✅ Can't break anything  
✅ Changes instant  
✅ No coding needed  
✅ Well documented  

### For You:
✅ Everything included  
✅ Step-by-step guides  
✅ Deploy in 30 minutes  
✅ Secure and fast  
✅ Scales with you  

---

## 📝 Final Notes

### This Package Includes:

- ✅ Complete working website
- ✅ All pages and features
- ✅ Forms ready to go
- ✅ Payment integration prepared
- ✅ CMS fully configured
- ✅ 6 comprehensive guides
- ✅ Example content
- ✅ Professional design

### You Just Need To:

1. Upload to GitHub (10 min)
2. Deploy to Netlify (10 min)
3. Enable CMS (10 min)
4. Customize content
5. Go live!

---

## 🌟 Ready to Launch!

**Next Action**: Open **START_HERE.md**

It will guide you through everything else.

Your community trust deserves a great website - you now have one! 🎉

---

**Built with care for Ceres & District Community Trust**  
*October 2025*

---

## Quick File Reference

| Need to... | Open this file... |
|------------|-------------------|
| Get started | START_HERE.md |
| Deploy site | QUICK_START.md |
| Set up payments | STRIPE_SETUP.md |
| Connect forms | GOOGLE_SHEETS_SETUP.md |
| Train volunteers | VOLUNTEER_GUIDE.md |
| Technical details | README.md |
| Change colors | assets/css/main.css |
| Edit content | Use CMS after deployment |
| Change prices | hugo.toml |
| Update menu | hugo.toml |

**Have everything you need? Let's get your charity online! 🚀**
