# SEO Validation & Testing Checklist
**Website:** Small Group Soccer Training
**Date:** March 15, 2026
**Status:** Post-SEO Optimization

---

## Pre-Deployment Checklist

Run these tests BEFORE pushing to production:

### 1. Local Testing (Port 3091)
- [ ] Site loads correctly at http://localhost:3091
- [ ] All navigation links work
- [ ] Contact form displays properly
- [ ] Blog pages load without errors
- [ ] Images display correctly
- [ ] Mobile menu toggles properly
- [ ] FAQ accordions expand/collapse

---

## Post-Deployment Validation

Run these tests AFTER deploying to production (smallgroupsoccer.com):

---

## Google Tools

### 1. Google Rich Results Test
**URL:** https://search.google.com/test/rich-results
**Test URL:** https://smallgroupsoccer.com

**What to Check:**
- [ ] LocalBusiness schema validates ✅
- [ ] Person schema validates ✅
- [ ] VideoObject schema validates ✅
- [ ] FAQPage schema validates ✅
- [ ] No errors or warnings

**Expected Results:**
```
✅ Page is eligible for rich results
- LocalBusiness
- Person
- VideoObject
- FAQPage (4 questions)
```

**If errors appear:**
- Check JSON-LD syntax (commas, brackets, quotes)
- Verify URLs are absolute (https://...)
- Confirm email format is correct

---

### 2. Google Mobile-Friendly Test
**URL:** https://search.google.com/test/mobile-friendly
**Test URL:** https://smallgroupsoccer.com

**What to Check:**
- [ ] Page is mobile-friendly ✅
- [ ] Text is readable without zooming
- [ ] Content fits screen width
- [ ] Touch targets are appropriately sized
- [ ] No horizontal scrolling

**Expected Result:**
```
✅ Page is mobile-friendly
```

---

### 3. Google PageSpeed Insights
**URL:** https://pagespeed.web.dev
**Test URL:** https://smallgroupsoccer.com

**Target Scores:**
- [ ] Mobile Performance: 70+ (80+ ideal)
- [ ] Desktop Performance: 85+ (90+ ideal)
- [ ] Mobile Accessibility: 95+
- [ ] Desktop Accessibility: 95+
- [ ] Mobile Best Practices: 90+
- [ ] Desktop Best Practices: 90+
- [ ] Mobile SEO: 95+
- [ ] Desktop SEO: 95+

**Core Web Vitals (Must Pass):**
- [ ] LCP (Largest Contentful Paint): < 2.5s
- [ ] INP (Interaction to Next Paint): < 200ms
- [ ] CLS (Cumulative Layout Shift): < 0.1

**Known Issues (Acceptable):**
- Using Tailwind CDN will flag as "Reduce unused CSS" - This is acceptable for now
- Font Awesome CDN may show as render-blocking - Can be optimized later

---

### 4. Google Search Console Setup
**URL:** https://search.google.com/search-console

**Initial Setup:**
1. [ ] Add property: `https://smallgroupsoccer.com`
2. [ ] Verify ownership (DNS, HTML file, or meta tag method)
3. [ ] Submit sitemap: `https://smallgroupsoccer.com/sitemap.xml`
4. [ ] Request indexing for homepage
5. [ ] Request indexing for key blog articles

**Monitor Weekly:**
- [ ] Coverage report (indexed pages)
- [ ] Performance report (clicks, impressions, CTR)
- [ ] Mobile usability errors
- [ ] Core Web Vitals status

**Expected Timeline:**
- **Day 1-3:** Property verified, sitemap submitted
- **Week 1:** 2-3 pages indexed
- **Week 2-4:** All 8 pages indexed, impressions start showing
- **Month 2-3:** Clicks from organic search increase

---

## Schema Validation Tools

### 5. Schema.org Validator
**URL:** https://validator.schema.org
**Test Method:** Paste URL or paste schema JSON directly

**What to Check:**
- [ ] No syntax errors
- [ ] All required properties present
- [ ] Dates in correct format (YYYY-MM-DD)
- [ ] URLs are absolute (https://...)
- [ ] Email addresses valid

**Test Each Schema Type:**
```json
LocalBusiness ✅
Person ✅
VideoObject ✅
FAQPage ✅
BlogPosting (blog articles) ✅
```

---

### 6. Google Structured Data Testing Tool (Legacy)
**URL:** https://search.google.com/structured-data/testing-tool

**Note:** This tool is deprecated but still useful for detailed validation

**What to Check:**
- [ ] All schemas recognized
- [ ] Preview shows correct data
- [ ] No warnings about missing recommended fields

---

## Social Media Validation

### 7. Facebook Sharing Debugger
**URL:** https://developers.facebook.com/tools/debug/
**Test URL:** https://smallgroupsoccer.com

**What to Check:**
- [ ] Title displays correctly
- [ ] Description shows properly
- [ ] Image displays (Coach Marcus photo)
- [ ] No warnings or errors
- [ ] Preview looks professional

**Expected Preview:**
```
Title: Youth Soccer Training for 11 Year Old Boys - Raleigh NC
Description: Small group soccer training for 11 year old boys in Raleigh and Wake County NC
Image: Coach Marcus photo (1200x630px)
```

**Click "Scrape Again"** if image doesn't show (Facebook caches aggressively)

---

### 8. Twitter Card Validator
**URL:** https://cards-dev.twitter.com/validator
**Test URL:** https://smallgroupsoccer.com

**What to Check:**
- [ ] Card preview displays
- [ ] summary_large_image card type recognized
- [ ] Title, description, image all present
- [ ] Image displays correctly

**Note:** You may need to be logged into Twitter Developer account

---

### 9. LinkedIn Post Inspector
**URL:** https://www.linkedin.com/post-inspector/
**Test URL:** https://smallgroupsoccer.com

**What to Check:**
- [ ] Title displays
- [ ] Description shows
- [ ] Image renders
- [ ] No errors reported

**Click "Inspect"** button to test

---

## Meta Tags Validation

### 10. Meta Tags Checker
**URL:** https://metatags.io
**Test URL:** https://smallgroupsoccer.com

**What to Check:**
- [ ] Title tag: 50-60 characters
- [ ] Meta description: 150-160 characters
- [ ] Canonical URL present
- [ ] Robots meta tag correct
- [ ] Open Graph tags complete
- [ ] Twitter Card tags complete

**Visual Preview Test:**
- [ ] Google search preview looks good
- [ ] Facebook preview looks good
- [ ] Twitter preview looks good

---

## Robots.txt & Sitemap Validation

### 11. Robots.txt Tester
**URL:** https://smallgroupsoccer.com/robots.txt

**Manual Check:**
- [ ] File loads without errors
- [ ] Sitemap URL is correct
- [ ] All AI crawlers allowed (GPTBot, ClaudeBot, etc.)
- [ ] No accidental Disallow: / blocking everything

**Expected Content:**
```
User-agent: *
Allow: /
Sitemap: https://smallgroupsoccer.com/sitemap.xml
```

**Test in Google Search Console:**
1. Go to Search Console → Settings → robots.txt
2. Check that robots.txt is accessible
3. Test specific URLs with the tester tool

---

### 12. XML Sitemap Validator
**URL:** https://www.xml-sitemaps.com/validate-xml-sitemap.html
**Test:** `https://smallgroupsoccer.com/sitemap.xml`

**What to Check:**
- [ ] Sitemap is valid XML
- [ ] All URLs are absolute (https://...)
- [ ] No 404 errors on listed pages
- [ ] Lastmod dates are recent
- [ ] Priority values are appropriate (0.3-1.0)

**Manual Check:**
- [ ] Homepage listed (priority 1.0)
- [ ] Blog articles listed (priority 0.7-0.8)
- [ ] Legal pages listed (priority 0.3)
- [ ] llms.txt listed (priority 0.5)

**Expected URLs (8 total):**
1. / (homepage)
2. /blog.html
3. /blog/5-essential-soccer-drills-for-11-year-old-boys.html
4. /blog/benefits-of-small-group-soccer-training.html
5. /blog/getting-started-with-our-platform.html
6. /privacy.html
7. /terms.html
8. /llms.txt

---

## AI Search Optimization (GEO)

### 13. llms.txt Validation
**URL:** https://smallgroupsoccer.com/llms.txt

**Manual Check:**
- [ ] File loads without errors
- [ ] Plain text format (not HTML)
- [ ] Business info clearly presented
- [ ] Coach bio included
- [ ] Services listed
- [ ] Contact information correct
- [ ] No broken Markdown formatting

**Test with AI:**
- [ ] Ask ChatGPT: "What do you know about Small Group Soccer Training in Raleigh?"
- [ ] Ask Perplexity: "Find information about Coach Marcus soccer training"
- [ ] Check if llms.txt data is being used in responses (may take 2-4 weeks for AI indexing)

---

### 14. AI Crawler Accessibility
**Check robots.txt allows these crawlers:**
- [ ] GPTBot (ChatGPT)
- [ ] ClaudeBot (Anthropic)
- [ ] PerplexityBot (Perplexity)
- [ ] Google-Extended (Bard/Gemini)
- [ ] CCBot (Common Crawl)

**Expected:** All allowed with `Allow: /`

---

## Accessibility Testing

### 15. WAVE Web Accessibility Evaluation
**URL:** https://wave.webaim.org
**Test URL:** https://smallgroupsoccer.com

**Target:**
- [ ] 0 Errors
- [ ] < 5 Warnings (alerts are okay)
- [ ] No contrast errors
- [ ] All images have alt text
- [ ] Form labels present

---

### 16. axe DevTools (Browser Extension)
**Install:** Chrome/Firefox extension "axe DevTools"

**Run on Homepage:**
- [ ] 0 Critical issues
- [ ] 0 Serious issues
- [ ] < 3 Moderate issues
- [ ] Minor issues acceptable

**Common Issues (Acceptable):**
- Tailwind CDN warnings
- Font Awesome icon contrast (decorative only)

---

## Performance Monitoring

### 17. GTmetrix
**URL:** https://gtmetrix.com
**Test URL:** https://smallgroupsoccer.com

**Target Scores:**
- [ ] Performance: B or higher
- [ ] Structure: A or B
- [ ] Fully Loaded Time: < 3.0s
- [ ] Total Page Size: < 2MB

**Key Metrics:**
- [ ] Time to First Byte (TTFB): < 600ms
- [ ] First Contentful Paint: < 1.8s
- [ ] Speed Index: < 3.4s

---

### 18. WebPageTest
**URL:** https://www.webpagetest.org
**Test:** https://smallgroupsoccer.com (from Raleigh, NC location if available)

**Test Settings:**
- Location: Dulles, VA (closest to Raleigh)
- Browser: Chrome
- Connection: Cable

**Target:**
- [ ] Load Time: < 3s
- [ ] Time to First Byte: < 500ms
- [ ] Start Render: < 1.5s

---

## Contact Form Testing

### 19. Formspree Setup & Testing
**URL:** https://formspree.io

**Setup Steps:**
- [ ] Create Formspree account with marcus@smallgroupsoccer.com
- [ ] Verify email address
- [ ] Get form endpoint URL
- [ ] Update index.html form action (line 387)

**Test Form Submission:**
1. [ ] Fill out contact form on site
2. [ ] Submit form
3. [ ] Verify "Thank you" message or redirect
4. [ ] Check email arrives at marcus@smallgroupsoccer.com
5. [ ] Verify form data is complete (name, email, phone, message)

**Expected Behavior:**
- Form submits successfully
- Email notification received within 1-2 minutes
- No errors in browser console

---

## Link Validation

### 20. Dead Link Checker
**URL:** https://www.deadlinkchecker.com
**Test URL:** https://smallgroupsoccer.com

**What to Check:**
- [ ] All internal links work (no 404s)
- [ ] All external links work
- [ ] Email links formatted correctly (mailto:)
- [ ] Phone links work on mobile (tel:)
- [ ] YouTube embed loads

**Common Issues to Fix:**
- Broken blog article links
- Incorrect relative/absolute paths
- Missing pages in navigation

---

### 21. W3C HTML Validator
**URL:** https://validator.w3.org
**Test URL:** https://smallgroupsoccer.com

**Target:**
- [ ] 0 Errors
- [ ] Warnings acceptable (Tailwind CSS CDN warnings are normal)

**Common Warnings (Ignore These):**
- "Consider adding a 'lang' attribute" (already have `lang="en"`)
- "Consider using the 'h1' element as a top-level heading only" (our structure is correct)
- Tailwind CSS unknown property warnings

---

## Security & Best Practices

### 22. SSL Certificate Check
**URL:** https://www.sslshopper.com/ssl-checker.html
**Test:** https://smallgroupsoccer.com

**What to Check:**
- [ ] SSL certificate valid
- [ ] No mixed content warnings (all resources HTTPS)
- [ ] Certificate not expired
- [ ] Grade A SSL rating

**Browser Check:**
- [ ] Green padlock shows in browser address bar
- [ ] No "Not Secure" warnings

---

### 23. Security Headers Check
**URL:** https://securityheaders.com
**Test URL:** https://smallgroupsoccer.com

**Target Grade:** B or higher

**Acceptable for Static Site:**
- May not have all headers (Content-Security-Policy, etc.)
- Static HTML sites don't need advanced security headers

---

## Local SEO Testing

### 24. Google Business Profile (Optional)
If you create a Google Business Profile:

**What to Check:**
- [ ] Business name matches website
- [ ] Address matches (if physical location)
- [ ] Phone matches
- [ ] Website URL correct
- [ ] Categories: Soccer Club, Sports Club, Youth Organization
- [ ] Business description includes "11 year old boys" and "Raleigh"

---

## Ongoing Monitoring (Weekly/Monthly)

### Weekly Checks:
- [ ] Google Search Console - New indexed pages, errors
- [ ] Google Analytics - Traffic trends, top pages
- [ ] Google Business Profile - Reviews, questions (if set up)

### Monthly Checks:
- [ ] PageSpeed Insights - Performance regression
- [ ] Broken link checker - New 404s
- [ ] Competitor analysis - How do you rank vs competitors
- [ ] Keyword rankings - Track "soccer training 11 year old boys Raleigh NC"

---

## SEO Ranking Tracking

### 25. Google Search Manual Check
**Search these terms monthly:**

1. "soccer training 11 year old boys raleigh nc"
   - Target: Page 1 (top 10) by Month 3

2. "youth soccer training raleigh"
   - Target: Page 1-2 (top 20) by Month 3

3. "private soccer coach raleigh nc"
   - Target: Page 2 (top 20) by Month 3

4. "small group soccer training wake county"
   - Target: Page 1 (top 10) by Month 2

**Track Position Weekly:**
- Month 1: Probably not ranking yet (building authority)
- Month 2: Page 3-5 for some keywords
- Month 3: Page 1-2 for target keywords
- Month 4-6: Page 1, top 5 for primary keywords

---

### 26. Free Rank Tracking Tools
**Tool:** https://www.serprobot.com/rank-tracker

**Track these keywords:**
- soccer training 11 year old boys raleigh nc
- youth soccer training raleigh
- private soccer coach raleigh
- small group soccer training wake county

**Location:** Raleigh, NC

**Frequency:** Weekly

---

## Summary Checklist

### Must-Do Immediately (Day 1):
- [ ] Google Rich Results Test
- [ ] robots.txt accessible
- [ ] sitemap.xml valid
- [ ] Contact form working
- [ ] SSL certificate valid
- [ ] All pages load without errors

### Week 1 Post-Launch:
- [ ] Google Search Console setup & sitemap submitted
- [ ] Google Analytics tracking verified
- [ ] Social media previews tested
- [ ] PageSpeed Insights baseline recorded
- [ ] Initial keyword position tracking started

### Month 1 Review:
- [ ] First pages indexed in Google
- [ ] Rich snippets appearing in search (check GSC)
- [ ] Traffic baseline established
- [ ] Conversion tracking confirmed

---

## Expected SEO Timeline

| Month | Milestone |
|-------|-----------|
| **Month 1** | - Schema indexed<br>- 5-8 pages indexed<br>- 50-100 visitors/month<br>- Traffic mostly direct (people you tell) |
| **Month 2** | - Blog articles ranking<br>- Rich snippets showing<br>- 150-300 visitors/month<br>- 30-40% from organic search |
| **Month 3** | - Page 1 for target keywords<br>- AI citations appearing<br>- 400-600 visitors/month<br>- 50-60% from organic search<br>- 5-10 contact form submissions |

---

## Questions or Issues?

**Schema errors:**
- https://developers.google.com/search/docs/advanced/structured-data

**Google Search Console help:**
- https://support.google.com/webmasters

**PageSpeed optimization:**
- https://developers.google.com/speed/docs/insights/v5/about

---

**Last Updated:** March 15, 2026
**Next Review:** April 15, 2026
