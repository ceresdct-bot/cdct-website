# 💳 Stripe Setup Guide - CDCT Payments

## Overview

This guide shows you how to set up Stripe to accept membership payments and donations for your charity.

**Time needed**: 30-45 minutes  
**Cost**: Free to set up, 2.9% + 30p per transaction  
**What you'll create**: Payment links for memberships and donations

---

## Prerequisites

- ✅ Website deployed to Netlify
- ✅ UK bank account (for receiving funds)
- ✅ Charity details and registration number
- ✅ Government-issued ID for verification

---

## Step 1: Create Stripe Account (15 minutes)

### 1.1 Sign Up

1. Go to https://stripe.com/gb
2. Click "Start now" or "Sign up"
3. Enter your email and create password
4. Verify your email address

### 1.2 Choose Account Type

- Select: **Business account**
- Business type: **Non-profit / Charity**
- Legal business name: **Ceres & District Community Trust**

### 1.3 Provide Business Information

Required details:
- Charity registration number
- Business address: Ceres, Fife, Scotland
- Website: `yoursite.netlify.app`
- Phone number
- Your role: Treasurer / Committee Member

### 1.4 Bank Account Details

- Sort code
- Account number
- Account holder name (must match charity name)

**Important**: Funds will be deposited to this account within 2-7 business days.

### 1.5 Verify Your Identity

Upload a photo of:
- Passport, or
- Driving license, or
- National identity card

*This is required by UK financial regulations.*

### 1.6 Activate Your Account

- Review and submit all information
- Stripe may ask for additional documentation
- Activation typically takes 1-2 business days

---

## Step 2: Create Payment Links (15 minutes)

Payment Links are the easiest way to accept payments. Customers click the link and Stripe hosts the payment page.

### 2.1 Lifetime Membership - £5

1. In Stripe Dashboard, click **"Payment links"** (left sidebar)
2. Click **"+ New"** (top right)
3. Configure:
   - **Type**: One-time payment
   - **Name**: Lifetime Membership
   - **Price**: £5.00 GBP
   - **Description**: "Lifetime membership of Ceres & District Community Trust"
4. **Customer information**: Collect email address (required)
5. Optional settings:
   - ✅ Enable "Collect customer billing address" (for records)
   - ✅ Enable "Collect customer phone number" (optional)
6. Click **"Create link"**
7. **Copy the URL** - you'll need this!

**Your link will look like**: `https://buy.stripe.com/test_xxxxx`

### 2.2 Annual Membership - £15

Repeat the above process:
- **Name**: Annual Membership
- **Price**: £15.00 GBP
- **Description**: "Annual membership of Ceres & District Community Trust (renewable yearly)"
- Copy the URL

### 2.3 Donation Links

Create these preset amounts:

**£10 Donation:**
- One-time payment
- £10.00 GBP
- Description: "Donation to Ceres & District Community Trust"

**£25 Donation:**
- Same as above, £25.00

**£50 Donation:**
- Same as above, £50.00

**£100 Donation:**
- Same as above, £100.00

**Custom Amount Donation:**
- One-time payment
- **Price**: Toggle to "Customer chooses price"
- Minimum: £1.00
- Suggested: £25.00
- Description: "Support the Ceres & District Community Trust"

---

## Step 3: Add Links to Website (10 minutes)

Now you need to add your Stripe payment links to your website.

### 3.1 Update Membership Page

1. Go to `yoursite.com/admin/`
2. Click **"Pages"** → **"Membership Page"**
3. Find the JavaScript section at the bottom (search for `function handleLifetimePayment`)
4. Replace the placeholder URLs:

**Before:**
```javascript
const stripeLifetimeURL = 'https://buy.stripe.com/YOUR_LIFETIME_LINK';
```

**After** (use your actual Stripe link):
```javascript
const stripeLifetimeURL = 'https://buy.stripe.com/test_1234abcd5678';
```

5. Do the same for `stripeAnnualURL`
6. Remove or comment out the alert messages about "Stripe integration pending"
7. Uncomment the line: `window.open(stripeLifetimeURL, '_blank');`

**Your finished code should look like:**
```javascript
function handleLifetimePayment() {
  const stripeLifetimeURL = 'https://buy.stripe.com/test_YOUR_REAL_LINK';
  window.open(stripeLifetimeURL, '_blank');
}

function handleAnnualPayment() {
  const stripeAnnualURL = 'https://buy.stripe.com/test_YOUR_REAL_LINK';
  window.open(stripeAnnualURL, '_blank');
}
```

8. Click **"Save"** and **"Publish"**

### 3.2 Update Donors Page

Repeat the same process for the Donors page:

1. **"Pages"** → **"Donors Page"**
2. Find the `handleDonation` function
3. Replace with:

```javascript
function handleDonation(amount) {
  const donationLinks = {
    10: 'https://buy.stripe.com/YOUR_10_LINK',
    25: 'https://buy.stripe.com/YOUR_25_LINK',
    50: 'https://buy.stripe.com/YOUR_50_LINK',
    100: 'https://buy.stripe.com/YOUR_100_LINK',
    custom: 'https://buy.stripe.com/YOUR_CUSTOM_LINK'
  };
  
  const link = donationLinks[amount] || donationLinks.custom;
  window.open(link, '_blank');
}

function handleCustomDonation() {
  handleDonation('custom');
}
```

4. **Save** and **Publish**

---

## Step 4: Test Everything (5 minutes)

### 4.1 Use Test Mode First

Stripe has a test mode - use this before going live!

**Test card details:**
- Card: 4242 4242 4242 4242
- Expiry: Any future date
- CVC: Any 3 digits
- Postcode: Any valid UK postcode

### 4.2 Test Each Payment Link

1. Go to your website
2. Click each membership/donation button
3. Complete test payment
4. Check Stripe Dashboard → Payments to see the test transaction

### 4.3 Switch to Live Mode

Once testing complete:
1. In Stripe Dashboard, toggle from "Test mode" to "Live mode" (top right)
2. Create the SAME payment links in live mode
3. Update your website with the LIVE links (they look different from test links)
4. Remove "test_" from URLs

---

## Step 5: Set Up Confirmations (5 minutes)

### 5.1 Email Receipts

Stripe automatically sends email receipts to customers. You can customize these:

1. Stripe Dashboard → **Settings** → **Emails**
2. **Successful payments**: Already enabled
3. Optional: Customize the email template with your logo

### 5.2 Success Pages

After payment, customers see a Stripe success page. You can customize:

1. In each Payment Link settings
2. **After payment**: Choose "Show success page"
3. Add custom message: "Thank you for supporting CDCT! We'll be in touch soon."
4. Optional: Add your logo

---

## Understanding Stripe Fees

### Transaction Fees

**UK cards**: 1.5% + 20p per transaction  
**European cards**: 2.5% + 20p  
**International cards**: 2.9% + 20p

### Examples:

| Amount | You Receive | Stripe Fee |
|--------|-------------|------------|
| £5.00 (lifetime) | £4.73 | £0.27 |
| £15.00 (annual) | £14.57 | £0.43 |
| £10.00 (donation) | £9.73 | £0.27 |
| £50.00 (donation) | £49.05 | £0.95 |

### Payout Schedule

- **Default**: Every 2 days (after initial 7-day waiting period)
- **Can change to**: Daily, weekly, or monthly
- **Bank holidays**: May delay payouts by 1-2 days

---

## Managing Payments

### View Transactions

1. Stripe Dashboard → **Payments**
2. See all successful payments
3. Click any payment for full details
4. Export to CSV for accounting

### Refunds

If needed to refund:
1. Find the payment in Dashboard
2. Click **"Refund"**
3. Full or partial refund
4. Money returned to customer in 5-10 days

### Failed Payments

If a payment fails:
- Customer sees error immediately
- Stripe emails you about the failure
- Common reasons: Insufficient funds, incorrect card details
- Customer can retry payment

---

## Matching Payments to Registrations

When someone pays for membership:

1. **They complete payment on Stripe**
   - Stripe captures their email
   - Sends them a receipt

2. **They return to your site**
   - Fill out membership form
   - Include payment reference (transaction ID)

3. **You match them up**
   - Check Stripe Dashboard for payments
   - Match emails/transaction IDs to form submissions
   - Add to membership records

**Tip**: Set up a simple spreadsheet:
- Column A: Name from form
- Column B: Email
- Column C: Amount paid
- Column D: Stripe transaction ID
- Column E: Date
- Column F: Membership type

---

## Security & Compliance

### PCI Compliance

✅ **You're automatically compliant!**
- Stripe hosts the payment page
- Card details never touch your website
- Stripe is PCI DSS Level 1 certified (highest level)

### GDPR

Stripe is GDPR compliant. Best practices:
- Add Stripe to your privacy policy
- Mention that payment data is processed by Stripe
- Keep payment records only as long as needed

### Charity Commission

For your charity records:
- Download monthly CSV exports from Stripe
- Keep with your financial records
- Include in annual accounts
- Show gross income (before Stripe fees)

---

## Advanced: Recurring Donations (Optional)

Want monthly recurring donations?

1. Create a **Subscription** payment link (not one-time)
2. Set billing interval: Monthly
3. Amount: e.g., £5/month
4. Add to your Donors page

Benefits:
- Predictable income
- Automatic each month
- Donors can cancel anytime

---

## Troubleshooting

### "Payment link not working"

- ✅ Did you activate your Stripe account?
- ✅ Are you in live mode (not test mode)?
- ✅ Did you copy the full URL correctly?
- ✅ Try the link in incognito window

### "Customer says payment failed"

- Check Stripe Dashboard for failed payment
- Common issues:
  - Card declined by bank
  - Insufficient funds
  - Incorrect card details
- Ask customer to try different card or payment method

### "Haven't received payout"

- First payout takes 7-10 days (regulatory requirement)
- Subsequent payouts: 2-7 days
- Check Stripe Dashboard → Payouts for status
- Verify bank details are correct

### "Can't find transaction"

- Search by amount, email, or date in Stripe
- Check both test and live mode
- Customer may have started but not completed payment

---

## Monthly Tasks

### Things to Do Each Month:

1. **Download payment report**
   - Stripe Dashboard → Payments → Export
   - Save to your records

2. **Reconcile with registrations**
   - Match Stripe payments to membership forms
   - Follow up on payments without forms

3. **Send thank you emails**
   - For new members and donors
   - Personal touch builds community

4. **Update donor recognition**
   - Add new donors to website (with permission)
   - Update totals and statistics

---

## Getting Help

### Stripe Support

- **Email**: Help available in Dashboard
- **Chat**: Click "?" in bottom right of Dashboard
- **Phone**: +44 20 7084 5555 (UK)
- **Docs**: https://stripe.com/docs

### Common Resources

- Payment Links guide: https://stripe.com/docs/payment-links
- Dashboard tutorial: Built into Stripe Dashboard
- Charity-specific help: Available from Stripe support

---

## Checklist: Going Live

Before accepting real payments:

- [ ] Stripe account fully activated
- [ ] Bank account verified
- [ ] Created all payment links in LIVE mode
- [ ] Updated website with live links
- [ ] Tested each payment type
- [ ] Set up email receipts
- [ ] Added Stripe to privacy policy
- [ ] Informed committee about payment process
- [ ] Set up monthly reconciliation process
- [ ] Tested refund process (optional)

---

## Quick Reference

### Payment Links Needed:

1. Lifetime Membership - £5
2. Annual Membership - £15
3. Donation - £10
4. Donation - £25
5. Donation - £50
6. Donation - £100
7. Donation - Custom amount

### Where to Add Links:

- Membership page: Links 1 & 2
- Donors page: Links 3-7

### Monthly Tasks:

- Download payment report
- Match to registrations
- Thank donors
- Update website

---

**You're all set! Your charity can now accept secure online payments. 💳**

*Last updated: October 2025*
