# Ceres & District Community Trust Website

A static website built with Hugo and Decap CMS for the Ceres & District Community Trust charity.

## 🌟 Features

- **Easy Content Management**: Volunteers can edit content through a WordPress-like admin panel (no coding required)
- **Volunteer Signup Form**: With file upload for health & safety forms
- **Membership System**: Two tiers (£5 lifetime, £15 annual) with Stripe payment integration
- **Donation System**: One-time donations with Stripe integration
- **Projects Gallery**: Showcase community projects
- **News/Blog**: Keep the community updated
- **Mobile Responsive**: Works on all devices
- **Fast & Secure**: Static site - no database to hack or slow down

## 📁 What's Included

### Pages
- **Home**: Welcome page with mission statement and latest updates
- **About Us**: Committee information and organizational details
- **Projects**: Community project showcase
- **Volunteers**: Signup form with health & safety upload
- **Membership**: Two-tier membership with payment integration
- **Donors**: Donation page with recognition
- **News**: Blog for updates and announcements

### Forms (All connect to Google Sheets via Netlify Forms + Zapier)
1. **Volunteer Registration Form**
   - Full contact details
   - Emergency contact
   - Skills and interests
   - Health & safety form upload
   - Availability

2. **Membership Registration Form**
   - Personal details
   - Membership type selection
   - Payment reference tracking
   - Newsletter opt-in

## 🚀 Deployment Guide

### Prerequisites

You'll need free accounts on:
1. **GitHub** (https://github.com) - to store your code
2. **Netlify** (https://netlify.com) - to host your website
3. **Stripe** (https://stripe.com) - for payments (optional initially)

### Step 1: Upload to GitHub

1. **Create a GitHub account** if you don't have one
2. **Create a new repository**:
   - Go to https://github.com/new
   - Name it: `cdct-website`
   - Set to "Public"
   - Don't initialize with README
   - Click "Create repository"

3. **Upload the files**:
   
   **Option A: Using GitHub Desktop (Easiest)**
   - Download GitHub Desktop: https://desktop.github.com
   - File → Add Local Repository
   - Choose the `cdct-website` folder
   - Click "Publish repository"

   **Option B: Using Git Command Line**
   ```bash
   cd cdct-website
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/cdct-website.git
   git push -u origin main
   ```
   
   **Option C: Upload via Web Interface**
   - Go to your repository page on GitHub
   - Click "uploading an existing file"
   - Drag and drop all files from cdct-website folder
   - Commit the changes

### Step 2: Deploy to Netlify

1. **Sign up for Netlify** at https://netlify.com (use your GitHub account for easy linking)

2. **Create a new site**:
   - Click "Add new site" → "Import an existing project"
   - Choose "GitHub"
   - Authorize Netlify to access your repositories
   - Select the `cdct-website` repository

3. **Configure build settings**:
   - Build command: `hugo --gc --minify`
   - Publish directory: `public`
   - Click "Deploy site"

4. **Wait for deployment** (1-2 minutes)
   - Your site will be live at a URL like: `random-name-123456.netlify.app`

5. **Enable Netlify Identity** (for CMS login):
   - Go to Site Settings → Identity
   - Click "Enable Identity"
   - Under "Registration preferences" → Select "Invite only"
   - Under "External providers" → Add GitHub (optional)
   - Click "Enable Git Gateway"

6. **Invite yourself as a CMS user**:
   - Identity tab → "Invite users"
   - Enter your email
   - Check your email and accept the invitation
   - Set your password

### Step 3: Configure Forms (Connect to Google Sheets)

**Option A: Using Zapier (Recommended)**

1. Sign up for free Zapier account: https://zapier.com
2. Create a new Zap:
   - Trigger: Netlify (Form submission)
   - Action: Google Sheets (Create spreadsheet row)
3. Connect your Netlify and Google accounts
4. Map form fields to spreadsheet columns
5. Test and activate

**Option B: Using Formspree**

1. Sign up at https://formspree.io
2. Create a new form endpoint
3. In your forms, change `data-netlify="true"` to `action="https://formspree.io/f/YOUR-FORM-ID"`
4. Connect to Google Sheets in Formspree settings

**Option C: Using Google Forms**

For simplest setup, you can embed Google Forms instead:
1. Create forms in Google Forms
2. Get embed code
3. Replace the HTML forms in the content files with the embed code

### Step 4: Set Up Stripe Payments (Optional - Can Do Later)

1. **Create Stripe account**: https://stripe.com
2. **Create Payment Links**:
   - Go to Stripe Dashboard → Payment Links
   - Create link for "Lifetime Membership - £5"
   - Create link for "Annual Membership - £15"
   - Create links for donation amounts (£10, £25, £50, £100)
   - Create a custom amount link for donations

3. **Add Payment Links to Website**:
   - Open `/content/membership.md` in CMS
   - Replace placeholder URLs with your Stripe Payment Link URLs
   - Do the same for `/content/donors.md`

4. **Testing**:
   - Use Stripe test mode initially
   - Test with test card: 4242 4242 4242 4242

### Step 5: Custom Domain (Optional)

1. **Buy a domain** (£10-15/year):
   - Namecheap, Google Domains, Cloudflare, etc.
   - Suggestion: `cerestrust.org.uk` or similar

2. **Connect to Netlify**:
   - Netlify: Site Settings → Domain Management
   - Add custom domain
   - Follow DNS instructions (or use Netlify DNS)

## ✏️ How Volunteers Edit Content

1. **Go to**: `yoursite.com/admin/`
2. **Log in** with email/password (set up in Netlify Identity)
3. **Edit content**:
   - Click on "News", "Projects", or "Pages"
   - Click "New News" or "Edit"
   - Use the visual editor (like WordPress)
   - Click "Save" then "Publish"
4. **Changes go live** in 30-60 seconds automatically!

### What Volunteers Can Edit
- ✅ All page content (text, headings, lists)
- ✅ Create new news posts
- ✅ Add/edit projects
- ✅ Upload images
- ✅ Update committee member info
- ❌ Cannot break the site design
- ❌ Cannot access payment settings

## 🔧 Maintenance Tasks

### Regular (Volunteers)
- Add news posts
- Update project status
- Update committee member info
- Add photos to image galleries

### Occasional (Tech Admin)
- Update Stripe payment links
- Adjust form fields if needed
- Update membership prices in hugo.toml
- Review form submissions

### Annual
- Renew domain (if custom domain)
- Review and update donor recognition lists
- Archive old news/projects

## 📊 Form Data Management

All form submissions go to:
1. **Netlify Forms** (can download CSV)
2. **Google Sheets** (via Zapier/Formspree)
3. **Email notifications** (configure in Netlify)

### Accessing Form Data

**In Netlify:**
- Site Dashboard → Forms
- Click on form name to see submissions
- Export to CSV

**In Google Sheets:**
- Opens automatically with Zapier
- Create sheets for each form:
  - Volunteer signups
  - Membership registrations

## 🎨 Customization

### Change Colors

Edit `/assets/css/main.css`:
```css
:root {
  --primary-color: #8B6F47;    /* Change this */
  --accent-color: #6B8E23;     /* And this */
}
```

### Change Membership Prices

Edit `hugo.toml`:
```toml
[params]
  lifetimeMembership = 5.00    /* Change these */
  annualMembership = 15.00
```

### Add/Remove Pages

1. Go to `/content/`
2. Add new `.md` files
3. Add to menu in `hugo.toml`

## 🆘 Troubleshooting

### "Site not building"
- Check Netlify deploy logs
- Usually a typo in a content file
- Ensure all `.md` files have proper front matter (the `---` sections)

### "Can't log into CMS"
- Ensure Netlify Identity is enabled
- Check you've been invited as a user
- Clear browser cache

### "Forms not submitting"
- Check Netlify Forms tab for submissions
- Ensure form has `data-netlify="true"`
- Check spam folder for email notifications

### "Stripe payments not working"
- Verify you're using live keys (not test keys)
- Check payment link URLs are correct
- Ensure Stripe account is fully activated

## 💰 Costs

### Completely Free Tier
- **Hosting**: Free on Netlify (up to 100GB bandwidth)
- **Forms**: Free (100 submissions/month on Netlify)
- **CMS**: Free (Decap CMS is open source)
- **Git**: Free on GitHub
- **Total**: £0/month

### Optional Paid Features
- **Custom Domain**: £10-15/year
- **More Forms**: Zapier paid tier (~£20/month) if over 100 submissions
- **Stripe**: 2.9% + 30p per transaction (standard)
- **Email Service**: (Optional) £5-15/month for newsletters

### Recommended Starting Budget
- **Year 1**: £10-15 (domain only)
- **Ongoing**: £1-2/month average (domain + occasional form costs)

## 📚 Resources

- **Hugo Documentation**: https://gohugo.io/documentation/
- **Decap CMS**: https://decapcms.org/docs/intro/
- **Netlify**: https://docs.netlify.com/
- **Stripe Payment Links**: https://stripe.com/docs/payment-links
- **Netlify Forms**: https://docs.netlify.com/forms/setup/

## 🤝 Support

Need help? Contact:
- **Technical Issues**: Open an issue on GitHub
- **Content Questions**: Ask any committee member with CMS access
- **Stripe/Payment Issues**: Contact Stripe support

## 📄 License

This website is built for Ceres & District Community Trust. Content is © CDCT. 
The code structure can be reused for other community organizations.

---

## Quick Reference Commands

### If you need to edit locally (advanced users)

**Install Hugo**:
```bash
# Mac
brew install hugo

# Windows
choco install hugo-extended

# Linux
snap install hugo
```

**Preview locally**:
```bash
cd cdct-website
hugo server -D
# Visit http://localhost:1313
```

**Build for production**:
```bash
hugo --gc --minify
# Output in /public folder
```

---

**Website built with ❤️ for the Ceres & District Community Trust**
