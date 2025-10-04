---
title: "Membership"
---

## Become a Member

Membership of the Ceres & District Community Trust supports our work and gives you a voice in shaping our community's future. Members receive updates on our projects, are invited to our Annual General Meeting, and can stand for election to the committee.

---

## Membership Options

<div class="pricing-container">
  <div class="pricing-card">
    <h3>Lifetime Membership</h3>
    <div class="price">£5</div>
    <p class="price-period">One-time payment</p>
    <ul style="text-align: left; margin: 1.5rem 0;">
      <li>Full voting rights</li>
      <li>AGM invitation & voting</li>
      <li>Regular newsletters</li>
      <li>Project updates</li>
      <li>Certificate of membership</li>
      <li><strong>Valid for life</strong></li>
    </ul>
    <button class="btn btn-primary" onclick="handleLifetimePayment()">Join - £5 Lifetime</button>
  </div>
  
  <div class="pricing-card featured">
    <h3>Annual Membership</h3>
    <div class="price">£15</div>
    <p class="price-period">Per year</p>
    <ul style="text-align: left; margin: 1.5rem 0;">
      <li>Full voting rights</li>
      <li>AGM invitation & voting</li>
      <li>Regular newsletters</li>
      <li>Project updates</li>
      <li>Priority event booking</li>
      <li>Renewable annually</li>
    </ul>
    <button class="btn btn-primary" onclick="handleAnnualPayment()">Join - £15/Year</button>
  </div>
</div>

---

## After Payment

Once you've completed payment, please fill out the membership form below so we can register your details and send you a welcome pack.

---

## Membership Registration Form

<form name="membership-signup" method="POST" data-netlify="true">
  <input type="hidden" name="form-name" value="membership-signup" />
  
  <div class="form-group">
    <label for="membership-type">Membership Type *</label>
    <select id="membership-type" name="membership-type" required>
      <option value="">-- Select --</option>
      <option value="lifetime">Lifetime Membership (£5)</option>
      <option value="annual">Annual Membership (£15)</option>
    </select>
  </div>
  
  <div class="form-group">
    <label for="full-name">Full Name *</label>
    <input type="text" id="full-name" name="full-name" required />
  </div>
  
  <div class="form-group">
    <label for="email">Email Address *</label>
    <input type="email" id="email" name="email" required />
  </div>
  
  <div class="form-group">
    <label for="phone">Phone Number</label>
    <input type="tel" id="phone" name="phone" />
  </div>
  
  <div class="form-group">
    <label for="address">Full Address *</label>
    <textarea id="address" name="address" placeholder="Street, Town, Postcode" required></textarea>
  </div>
  
  <div class="form-group">
    <label for="payment-reference">Payment Reference/Transaction ID</label>
    <input type="text" id="payment-reference" name="payment-reference" placeholder="If you've already paid via Stripe" />
    <small class="form-help">This helps us match your payment to your registration</small>
  </div>
  
  <div class="form-group">
    <label>
      <input type="checkbox" name="newsletter" value="yes" checked />
      I would like to receive the CDCT newsletter and updates
    </label>
  </div>
  
  <div class="form-group">
    <label>
      <input type="checkbox" name="data-consent" value="yes" required />
      I consent to CDCT storing my information for membership purposes *
    </label>
  </div>
  
  <div class="form-group">
    <button type="submit" class="btn btn-primary">Complete Membership Registration</button>
  </div>
</form>

---

## Payment Methods

We accept payment via:
- **Stripe** (card payments - click buttons above)
- **Bank Transfer**: Contact us for details
- **Cash/Cheque**: Hand to any committee member

---

## Membership Benefits

As a member, you'll:
- Have a say in the Trust's direction and activities
- Vote at our Annual General Meeting
- Be eligible to stand for the committee
- Receive regular updates on projects and events
- Know you're supporting your local community

---

## Questions About Membership?

Contact us at info@cdct.org.uk or speak to any committee member.

<script>
  // Stripe payment handling
  // Note: Replace these with your actual Stripe Payment Link URLs after setup
  
  function handleLifetimePayment() {
    // Replace with your Stripe Payment Link for £5 lifetime membership
    const stripeLifetimeURL = 'https://buy.stripe.com/YOUR_LIFETIME_LINK';
    
    alert('You will be redirected to Stripe to complete your £5 lifetime membership payment. After payment, please return here to complete the registration form.');
    
    // For now, show instructions. Replace with actual Stripe link:
    if (confirm('Stripe integration pending. Would you like instructions to set this up?')) {
      alert('To set up Stripe:\n\n1. Create a Stripe account\n2. Create a Payment Link for £5 (lifetime)\n3. Create a Payment Link for £15 (annual)\n4. Replace the URLs in this page\n\nFor now, please complete the form below and we\'ll send you payment details.');
    }
    
    // Uncomment when Stripe is set up:
    // window.open(stripeLifetimeURL, '_blank');
  }
  
  function handleAnnualPayment() {
    // Replace with your Stripe Payment Link for £15 annual membership
    const stripeAnnualURL = 'https://buy.stripe.com/YOUR_ANNUAL_LINK';
    
    alert('You will be redirected to Stripe to complete your £15 annual membership payment. After payment, please return here to complete the registration form.');
    
    // For now, show instructions. Replace with actual Stripe link:
    if (confirm('Stripe integration pending. Would you like instructions to set this up?')) {
      alert('To set up Stripe:\n\n1. Create a Stripe account\n2. Create a Payment Link for £5 (lifetime)\n3. Create a Payment Link for £15 (annual)\n4. Replace the URLs in this page\n\nFor now, please complete the form below and we\'ll send you payment details.');
    }
    
    // Uncomment when Stripe is set up:
    // window.open(stripeAnnualURL, '_blank');
  }
</script>
