# 📊 Google Sheets Integration Guide - CDCT Forms

## Overview

This guide shows you how to automatically send form submissions from your website to Google Sheets, making it easy to track volunteers and members.

**Time needed**: 20-30 minutes  
**Cost**: Free (with Zapier free tier: 100 submissions/month)  
**Result**: Automatic spreadsheet updates when forms are submitted

---

## What You'll Create

Two Google Sheets that automatically fill when someone submits:
1. **Volunteer Signups** - Tracks volunteer registrations
2. **Membership Signups** - Tracks new members

---

## Method 1: Using Zapier (Recommended)

Zapier is the easiest way to connect Netlify Forms to Google Sheets.

### Step 1: Create Your Google Sheets (5 minutes)

#### 1.1 Volunteer Signup Sheet

1. Go to https://sheets.google.com
2. Click "Blank" to create new sheet
3. Name it: "CDCT Volunteer Signups"
4. Add these column headers in row 1:

| A | B | C | D | E | F | G | H | I | J |
|---|---|---|---|---|---|---|---|---|---|
| Date | Full Name | Email | Phone | Address | Emergency Contact | Emergency Phone | Interests | Skills | Availability |

#### 1.2 Membership Signup Sheet

1. Create another new sheet
2. Name it: "CDCT Membership Signups"
3. Add these column headers:

| A | B | C | D | E | F | G |
|---|---|---|---|---|---|---|
| Date | Membership Type | Full Name | Email | Phone | Address | Payment Reference |

### Step 2: Sign Up for Zapier (5 minutes)

1. Go to https://zapier.com/sign-up
2. Sign up with Google account (easiest)
3. Choose the free plan
4. Verify your email

### Step 3: Create Volunteer Form Zap (10 minutes)

#### 3.1 Start New Zap

1. Click "Create" → "Zaps"
2. Click "Create Zap"

#### 3.2 Set Up Trigger (When form is submitted)

1. **Choose App**: Search for "Netlify"
2. **Trigger Event**: "New Form Submission"
3. Click "Continue"
4. **Connect Account**: 
   - Click "Sign in to Netlify"
   - Log in with your Netlify account
   - Authorize Zapier
5. **Choose Options**:
   - **Site**: Select your CDCT site
   - **Form**: Select "volunteer-signup"
6. **Test Trigger**:
   - Click "Test trigger"
   - If no data appears, submit test form first
   - Should show your form fields
7. Click "Continue"

#### 3.3 Set Up Action (Add to Sheet)

1. **Choose App**: Search for "Google Sheets"
2. **Action Event**: "Create Spreadsheet Row"
3. Click "Continue"
4. **Connect Account**:
   - Sign in to Google
   - Allow Zapier access
5. **Set Up Action**:
   - **Drive**: My Drive
   - **Spreadsheet**: "CDCT Volunteer Signups"
   - **Worksheet**: Sheet1
6. **Match Fields** (click each field and select from dropdown):
   - Date: *Custom* → Today's date
   - Full Name: → full-name
   - Email: → email
   - Phone: → phone
   - Address: → address
   - Emergency Contact: → emergency-contact
   - Emergency Phone: → emergency-phone
   - Interests: → interests
   - Skills: → skills
   - Availability: → availability

7. **Test Action**: Click "Test action"
8. Check your Google Sheet - should see test data!
9. Name your Zap: "CDCT Volunteer Form → Sheet"
10. Click "Publish"

✅ **Done!** Volunteer submissions now go to Google Sheets automatically!

### Step 4: Create Membership Form Zap (10 minutes)

Repeat the same process:

1. Create new Zap
2. **Trigger**: Netlify → New Form Submission
   - Site: Your CDCT site
   - Form: "membership-signup"
3. **Action**: Google Sheets → Create Spreadsheet Row
   - Spreadsheet: "CDCT Membership Signups"
   - Match fields:
     - Date → Today's date
     - Membership Type → membership-type
     - Full Name → full-name
     - Email → email
     - Phone → phone
     - Address → address
     - Payment Reference → payment-reference
4. Test and Publish

✅ **Done!** Both forms now auto-fill spreadsheets!

---

## Method 2: Using Formspree (Alternative)

If you prefer Formspree over Zapier:

### Step 1: Sign Up for Formspree

1. Go to https://formspree.io
2. Sign up (free tier: 50 submissions/month)
3. Verify email

### Step 2: Create Forms

1. Click "New Form"
2. Name: "CDCT Volunteer Signup"
3. Copy the form endpoint URL

### Step 3: Update Website Forms

In your content files, change the form action:

**Before:**
```html
<form name="volunteer-signup" method="POST" data-netlify="true">
```

**After:**
```html
<form name="volunteer-signup" method="POST" action="https://formspree.io/f/YOUR_FORM_ID">
```

### Step 4: Connect to Google Sheets

1. In Formspree dashboard
2. Click your form
3. Go to Integrations
4. Click "Google Sheets"
5. Connect your Google account
6. Select your spreadsheet
7. Map fields

---

## Method 3: Using Native Netlify (No Third Party)

Simplest but most manual:

### View Submissions in Netlify

1. Netlify Dashboard
2. Click "Forms" tab
3. See all submissions
4. Click "Export to CSV" monthly
5. Import CSV to Google Sheets

**Pros**: Free, simple, no third party  
**Cons**: Manual work, not real-time

---

## Testing Your Setup

### Test Volunteer Form

1. Go to your website's volunteer page
2. Fill out the form with test data
3. Submit
4. Check Google Sheet - should appear in ~30 seconds
5. Check email - should get Netlify notification

### Test Membership Form

Same process for membership page.

### Troubleshooting Tests

**Form submits but nothing in Google Sheets:**
- Check Zapier task history for errors
- Verify Sheet name matches exactly
- Check field mappings in Zapier
- Try "Test action" again in Zapier

**Zapier says "No data":**
- Submit a real form first (not just test)
- Then refresh Zapier trigger test
- Should now see form fields

---

## Organizing Your Data

### Volunteer Sheet Tips

**Add these extra columns:**
- Column K: Status (Active/Inactive)
- Column L: Projects Joined
- Column M: Hours Volunteered
- Column N: Notes

**Use Data Validation:**
1. Click column K header
2. Data → Data validation
3. Criteria: List of items
4. Add: Active, Inactive, Pending
5. Now you can dropdown!

### Membership Sheet Tips

**Add columns:**
- Column H: Membership Status (Active/Expired)
- Column I: Start Date
- Column J: Expiry Date (for annual)
- Column K: Payment Confirmed (Yes/No)
- Column L: Welcome Pack Sent (Yes/No)

**Automatic calculations:**
In column J (Expiry Date):
```
=IF(B2="annual", DATE(YEAR(A2)+1, MONTH(A2), DAY(A2)), "Lifetime")
```
*Auto-calculates expiry for annual members*

---

## Monthly Workflow

### For Volunteer Coordinator:

1. **Review new signups** in Google Sheet
2. **Email welcome message** to new volunteers
3. **Mark status** as Active
4. **Match to projects** in Column L
5. **Update hours** as they volunteer

### For Membership Secretary:

1. **Cross-reference** with Stripe payments
2. **Confirm payment** in Column K
3. **Send welcome pack** (mark in Column L)
4. **Set reminder** for annual renewal

### For Treasurer:

1. **Download** Netlify form data monthly (backup)
2. **Export** from Stripe
3. **Reconcile** payments with registrations
4. **Update** accounting records

---

## Email Notifications

### Netlify Form Notifications

1. Netlify Dashboard → Forms
2. Click "Form notifications"
3. Add email addresses for notifications
4. Choose which forms to notify about

### Zapier Email Alerts

Add a second action to your Zap:

1. Edit existing Zap
2. Click "+" to add step
3. Choose "Email by Zapier"
4. Action: Send Outbound Email
5. To: Your email
6. Subject: "New CDCT Volunteer Signup"
7. Body: Include form fields
8. Test and Update Zap

---

## Data Management

### Regular Cleanup

**Monthly:**
- Remove test submissions
- Fix typos in names/emails
- Flag incomplete submissions
- Archive old inactive volunteers

**Quarterly:**
- Review membership expirations
- Send renewal reminders (annual members)
- Update volunteer availability
- Export backup to Google Drive folder

### Privacy & GDPR

**You must:**
- ✅ Have privacy policy on website
- ✅ Get consent to store data (form checkbox)
- ✅ Only keep data as long as needed
- ✅ Delete on request
- ✅ Keep data secure (Google account password)

**Google Sheets settings:**
1. Share → Restricted (only specific people)
2. Give committee members "Edit" access
3. Give view-only access sparingly
4. Never share publicly

---

## Backup Strategy

### Automatic Backups

**Option 1: Google Drive versions**
- Google Sheets auto-saves versions
- File → Version history → See version history
- Can restore any past version

**Option 2: Monthly exports**
- File → Download → Excel
- Save to secure folder
- Name: "CDCT-Volunteers-Oct2025.xlsx"

**Option 3: Google Sheets backup add-on**
- Extensions → Add-ons → Get add-ons
- Search "Backup" or "Export"
- Many free options for auto-export

---

## Advanced: Using Google Forms Instead

Prefer Google Forms' simplicity?

### Switch to Google Forms

1. Create form in Google Forms
2. Auto-connects to Google Sheets
3. Get embed code
4. Replace HTML forms in your website

**Pros:**
- ✅ Native Sheets integration
- ✅ Easier for non-technical people
- ✅ Better spam protection
- ✅ Free forever

**Cons:**
- ❌ Less control over design
- ❌ Doesn't match site theme
- ❌ Opens in separate tab

### How to Embed Google Form

1. Create form in Google Forms
2. Click Send → < > (embed icon)
3. Copy the iframe code
4. In your website .md file:
```html
<iframe src="https://docs.google.com/forms/d/e/YOUR_FORM_ID/viewform?embedded=true" width="100%" height="1200" frameborder="0">Loading…</iframe>
```

---

## Reporting & Analytics

### Create Dashboard

In Google Sheets, create a "Dashboard" tab:

**Volunteer metrics:**
- Total volunteers: `=COUNTA(Sheet1!B:B)-1`
- Active volunteers: `=COUNTIF(Sheet1!K:K,"Active")`
- By area of interest: Pivot table

**Membership metrics:**
- Total members: `=COUNTA(Sheet1!C:C)-1`
- Lifetime vs Annual: `=COUNTIF(Sheet1!B:B,"lifetime")`
- This year's new members: Date formula

### Create Charts

1. Select data range
2. Insert → Chart
3. Chart type: Column, pie, line
4. Customize colors to match CDCT theme

---

## Troubleshooting

### "Zapier isn't running"

- Check task history in Zapier
- Free tier: 100 tasks/month limit
- Tasks reset monthly
- Upgrade if needed (£20/month for unlimited)

### "Form data looks wrong in Sheet"

- Check field mapping in Zapier
- Edit Zap → Review "Customize" section
- May need to re-map if form changed
- Test action again

### "Getting duplicate entries"

- Zapier sometimes sends twice
- Filter duplicates:
  - Data → Remove duplicates
  - Select email column
  - Keep first occurrence

### "Health & safety uploads?"

File uploads from Netlify Forms:
1. Can't go directly to Sheets
2. Stored in Netlify Dashboard
3. Download manually from Forms tab
4. Store in Google Drive folder
5. Add Drive link to Sheet

---

## Limits & Costs

### Zapier Free Tier
- **100 tasks/month** (each form submission = 1 task)
- **15 minute** update interval
- **Single-step** Zaps

If you exceed 100/month:
- Upgrade to Starter: ~£20/month
- Get 750 tasks/month
- Multi-step Zaps
- Faster updates

### Formspree Free Tier
- **50 submissions/month**
- Email notifications
- Spam filtering
- $10/month for 1000 submissions

### Google Sheets Limits
- **5 million cells** per sheet (plenty!)
- **40,000 new rows** per day
- **200 sheets** per spreadsheet
- All FREE

---

## Quick Reference

### Setup Checklist

- [ ] Create Google Sheets
- [ ] Add column headers
- [ ] Sign up for Zapier
- [ ] Create Volunteer Form Zap
- [ ] Create Membership Form Zap
- [ ] Test both forms
- [ ] Set up email notifications
- [ ] Share sheets with committee
- [ ] Set up monthly backup
- [ ] Add to privacy policy

### Monthly Tasks

- [ ] Review new submissions
- [ ] Cross-check with Stripe
- [ ] Send welcome messages
- [ ] Update statuses
- [ ] Export backup
- [ ] Clean up test data

### Key Links

- Zapier: https://zapier.com
- Formspree: https://formspree.io
- Google Sheets: https://sheets.google.com
- Netlify Forms docs: https://docs.netlify.com/forms/setup/

---

**Your forms are now connected! Data flows automatically from website → Google Sheets. 📊**

*Last updated: October 2025*
