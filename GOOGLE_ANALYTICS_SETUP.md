# Google Analytics 4 (GA4) Setup Guide
**For: Small Group Soccer Training Website**
**Date: March 15, 2026**

---

## Why Google Analytics?

Google Analytics 4 (GA4) will help you track:
- How many people visit your site
- Which pages they view
- How they found you (Google search, social media, direct visits)
- Which blog articles drive the most traffic
- How many people click "Contact Us"
- Conversion tracking (form submissions)

This data helps you understand what's working and optimize your SEO strategy.

---

## Step 1: Create Google Analytics Account

### 1.1 Go to Google Analytics
Visit: https://analytics.google.com

### 1.2 Sign In
Use your Gmail account (create one if needed): `marcus@smallgroupsoccer.com`

### 1.3 Create Account
1. Click "Start measuring"
2. Account name: `Small Group Soccer Training`
3. Check all data-sharing settings (recommended)
4. Click "Next"

---

## Step 2: Set Up Property

### 2.1 Property Details
- **Property name:** `Small Group Soccer Training - Raleigh NC`
- **Reporting time zone:** `(GMT-05:00) Eastern Time`
- **Currency:** `United States Dollar (USD)`
- Click "Next"

### 2.2 Business Information
- **Industry category:** Sports & Recreation
- **Business size:** Small (1-10 employees)
- **How will you use Google Analytics:** Get baseline reports
- Click "Create"

### 2.3 Accept Terms
- Check "I accept the Google Analytics Terms of Service Agreement"
- Check "I accept the Measurement Controller-Controller Data Protection Terms"
- Click "I Accept"

---

## Step 3: Set Up Data Stream

### 3.1 Choose Platform
- Click "Web"

### 3.2 Configure Web Stream
- **Website URL:** `https://smallgroupsoccer.com`
- **Stream name:** `Small Group Soccer Training Website`
- **Enhanced measurement:** Leave ON (recommended)
  - This tracks: Page views, scrolls, outbound clicks, site search, video engagement, file downloads

### 3.3 Click "Create stream"

---

## Step 4: Add Tracking Code to Website

### 4.1 Get Your Measurement ID
After creating the data stream, you'll see:
```
Measurement ID: G-XXXXXXXXXX
```
Copy this ID (example: `G-ABC123XYZ`)

### 4.2 Add Google Tag to Your Website

**IMPORTANT:** Add this code to the `<head>` section of **every HTML page** on your site.

Insert this code right after the `<head>` tag in:
- `index.html`
- `blog.html`
- `privacy.html`
- `terms.html`
- All blog articles in `/blog/` folder

```html
<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-XXXXXXXXXX');
</script>
```

**Replace `G-XXXXXXXXXX` with your actual Measurement ID**

### 4.3 Example: Adding to index.html

Your `<head>` section should look like this:

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <!-- Google tag (gtag.js) -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
    <script>
      window.dataLayer = window.dataLayer || [];
      function gtag(){dataLayer.push(arguments);}
      gtag('js', new Date());
      gtag('config', 'G-XXXXXXXXXX');
    </script>

    <meta name="description" content="...">
    <!-- rest of head content -->
</head>
```

---

## Step 5: Set Up Event Tracking (Optional but Recommended)

Track specific user actions like clicking "Contact Us" button.

### 5.1 Track Contact Button Clicks

Find your "Contact Us" button in `index.html` (line ~267):

```html
<a href="#contact" class="btn-primary inline-block bg-blue-600...">
    Contact Us
</a>
```

Add `onclick` event:

```html
<a href="#contact"
   class="btn-primary inline-block bg-blue-600..."
   onclick="gtag('event', 'click', {'event_category': 'engagement', 'event_label': 'contact_button_click'});">
    Contact Us
</a>
```

### 5.2 Track Form Submissions

Add to your contact form (line ~387):

```html
<form class="space-y-5"
      action="https://formspree.io/f/marcus@smallgroupsoccer.com"
      method="POST"
      onsubmit="gtag('event', 'form_submit', {'event_category': 'lead_generation', 'event_label': 'contact_form'});">
```

### 5.3 Track Phone/Email Clicks

Track email link clicks:

```html
<a href="mailto:marcus@smallgroupsoccer.com"
   onclick="gtag('event', 'click', {'event_category': 'contact', 'event_label': 'email_click'});">
    marcus@smallgroupsoccer.com
</a>
```

---

## Step 6: Verify Installation

### 6.1 Real-Time Test
1. Go to Google Analytics: https://analytics.google.com
2. Navigate to: **Reports → Realtime → Overview**
3. Open your website in a new tab: https://smallgroupsoccer.com
4. Within 30 seconds, you should see "1 user" in the Realtime report

If you see yourself, tracking is working! ✅

### 6.2 Check All Pages
- Click through to different pages on your site
- Visit blog articles
- Make sure each page shows up in Realtime report

---

## Step 7: Configure Important Settings

### 7.1 Enable Demographics & Interests
1. Go to **Admin** (bottom left)
2. Under **Property** → **Data Settings** → **Data Collection**
3. Toggle ON: "Google signals data collection"
4. This enables demographics data (age, gender, interests)

### 7.2 Link Google Search Console (Recommended)
1. In Admin → **Property Settings** → **Product Links**
2. Click "Link" next to Search Console
3. Follow prompts to link (you'll set up Search Console next)

---

## Step 8: Set Up Conversions (Goals)

### 8.1 Create Contact Form Conversion
1. Go to **Admin** → **Events**
2. Click "Create event"
3. Event name: `contact_form_submission`
4. Mark as "Conversion"

This tracks how many people submit your contact form = leads generated!

### 8.2 Other Conversion Ideas
- Email link clicks
- Phone number clicks
- Blog article reads (time on page > 2 minutes)
- Video views

---

## Step 9: Important Reports to Monitor Weekly

### Report 1: Traffic Acquisition
**Where:** Reports → Acquisition → Traffic acquisition

Shows where visitors come from:
- Organic Search (Google)
- Direct (typing URL)
- Referral (other websites)
- Social (Facebook, Twitter, etc.)

**What to look for:** Increase in "Organic Search" after SEO improvements

---

### Report 2: Pages and Screens
**Where:** Reports → Engagement → Pages and screens

Shows which pages get the most views:
- Homepage
- Blog articles
- Contact page

**What to look for:** Blog articles driving traffic

---

### Report 3: Events
**Where:** Reports → Engagement → Events

Shows user actions:
- Form submissions
- Button clicks
- Video plays

**What to look for:** Contact form submissions (leads!)

---

### Report 4: Conversions
**Where:** Reports → Engagement → Conversions

Shows goal completions:
- Contact form submissions
- Email clicks
- Phone clicks

**What to look for:** Increasing conversion rate over time

---

## Step 10: Set Up Weekly Email Reports (Optional)

1. Open any report (e.g., Traffic Acquisition)
2. Click **Share** (top right)
3. **Schedule email**
4. Email frequency: Weekly
5. Day: Monday
6. Recipients: marcus@smallgroupsoccer.com
7. Click "Schedule"

---

## What Success Looks Like (Example Goals)

### Month 1 (March 2026)
- **Visitors:** 50-100/month
- **Top source:** Direct traffic (people you tell)
- **Goal:** Set baseline, verify tracking works

### Month 2-3 (April-May 2026)
- **Visitors:** 150-300/month (after SEO improvements)
- **Top source:** Organic search (Google)
- **Goal:** See 2-3x traffic increase from schema markup + blog content

### Month 4-6 (June-August 2026)
- **Visitors:** 400-600/month
- **Contact forms:** 10-15/month
- **Top pages:** Homepage, blog articles about youth soccer training
- **Goal:** Steady lead generation from organic search

---

## Troubleshooting

### Problem: No Data Showing in Realtime Report
**Solutions:**
1. Check Measurement ID is correct in tracking code
2. Make sure tracking code is in `<head>` section, not `<body>`
3. Check browser isn't blocking scripts (disable ad blockers)
4. Wait 24 hours—some reports take time to populate

### Problem: Tracking Code on Some Pages But Not Others
**Solution:**
- Add tracking code to ALL HTML files
- Use "View Page Source" in browser to verify code is present
- Check `/blog/` folder articles have tracking code

### Problem: Events Not Tracking
**Solution:**
- Check `onclick` attributes are correctly added
- Open browser console (F12) and check for JavaScript errors
- Test form submission and check Realtime Events report

---

## Next Steps After Setup

1. **Deploy tracking code** to all pages
2. **Verify installation** with Realtime report
3. **Wait 24-48 hours** for data to accumulate
4. **Check weekly reports** to track SEO progress
5. **Create custom dashboards** for quick glance at key metrics

---

## Resources

- **Google Analytics Help:** https://support.google.com/analytics
- **GA4 Learning Center:** https://skillshop.withgoogle.com/analytics
- **Event Tracking Guide:** https://support.google.com/analytics/answer/9267735

---

## Summary Checklist

- [ ] Create Google Analytics account
- [ ] Set up GA4 property
- [ ] Create web data stream
- [ ] Copy Measurement ID
- [ ] Add tracking code to all HTML pages
- [ ] Verify with Realtime report
- [ ] Enable Google Signals (demographics)
- [ ] Set up conversions (contact form)
- [ ] Link Google Search Console (next step)
- [ ] Schedule weekly email reports
- [ ] Monitor traffic weekly

---

**Questions?** Review this guide step-by-step. Most setup takes 15-20 minutes.

**Need help?** Google Analytics support: https://support.google.com/analytics/gethelp
