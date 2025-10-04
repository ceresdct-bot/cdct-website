---
title: "Support Our Work"
---

## Thank You to Our Donors

The Ceres & District Community Trust relies on the generosity of donors to fund our projects and activities. Every donation, large or small, makes a real difference in our community.

---

## Ways to Donate

### One-Time Donation

Support a specific project or our general operating fund with a one-time gift.

<div style="text-align: center; margin: 2rem 0;">
  <button class="btn btn-primary" onclick="handleDonation(10)">Donate £10</button>
  <button class="btn btn-primary" onclick="handleDonation(25)">Donate £25</button>
  <button class="btn btn-primary" onclick="handleDonation(50)">Donate £50</button>
  <button class="btn btn-primary" onclick="handleDonation(100)">Donate £100</button>
  <button class="btn btn-primary" onclick="handleCustomDonation()">Custom Amount</button>
</div>

### Other Ways to Give

- **Bank Transfer**: Contact us for account details
- **Cheque**: Made payable to "Ceres & District Community Trust"
- **In Person**: Hand to any committee member
- **Fundraising Events**: Join us at our various events throughout the year

---

## Where Your Money Goes

Your donations support:

<div class="grid grid-3">
  <div class="card">
    <h3>🌳 Community Projects</h3>
    <p>Direct funding for improvements to public spaces, heritage sites, and community facilities.</p>
  </div>
  <div class="card">
    <h3>📅 Events & Activities</h3>
    <p>Bringing the community together through events, workshops, and celebrations.</p>
  </div>
  <div class="card">
    <h3>🛠️ Operating Costs</h3>
    <p>Insurance, administration, and essential costs that keep the Trust running effectively.</p>
  </div>
</div>

---

## Recognition

We'd love to thank you publicly (unless you prefer to remain anonymous). Donors are recognized:

- On this website (with permission)
- In our annual report
- At our AGM
- In project signage for major contributions

---

## Our Supporters

**Major Donors (£500+)**
- [Name/Organization]
- [Name/Organization]

**Project Sponsors (£100-499)**
- [Name/Organization]
- [Name/Organization]
- [Name/Organization]

**Community Supporters (Under £100)**

Thank you to the many individuals who contribute to make our work possible. Your names could be listed here with your permission!

---

## Gift Aid

If you're a UK taxpayer, we can claim Gift Aid on your donation at no extra cost to you. This adds 25p for every £1 you donate! Let us know when you donate if you'd like us to claim Gift Aid.

---

## Corporate Sponsorship

Is your business interested in supporting community projects? We offer corporate sponsorship opportunities with recognition at events and in our communications. Contact us to discuss how your company can give back to the local community.

---

## Contact Us

For questions about donations or to discuss a larger gift:

**Email**: info@cdct.org.uk  
**Phone**: [Your number]

**Thank you for your support!**

<script>
  // Stripe donation handling
  
  function handleDonation(amount) {
    alert(`You will be redirected to Stripe to complete your £${amount} donation. Thank you for your generosity!`);
    
    // For now, show instructions. Replace with actual Stripe links:
    if (confirm('Stripe integration pending. Would you like instructions to set this up?')) {
      alert('To set up Stripe donations:\n\n1. Log into your Stripe account\n2. Create Payment Links for preset amounts (£10, £25, £50, £100)\n3. Create a Payment Link that allows custom amounts\n4. Replace the URLs in this page\n\nFor now, please contact us directly to arrange your donation.');
    }
    
    // When Stripe is set up, use something like:
    // const stripeURL = `https://buy.stripe.com/YOUR_LINK_${amount}`;
    // window.open(stripeURL, '_blank');
  }
  
  function handleCustomDonation() {
    const amount = prompt('Enter your donation amount (£):');
    if (amount && !isNaN(amount) && parseFloat(amount) > 0) {
      handleDonation(amount);
    } else if (amount !== null) {
      alert('Please enter a valid amount.');
    }
  }
</script>
