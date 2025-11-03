# VelocityDev Ventures - Subdomain Setup Guide

## Overview

You now have two distinct brands under one umbrella:
- **velocitydev.ai** → Fee-for-service for established businesses
- **ventures.velocitydev.ai** → Equity partnerships for startups

This separation is professional, clear, and easy to manage.

---

## File Structure

```
velocitydev.ai/
├── index.html (main fee-for-service site)

ventures.velocitydev.ai/
├── index.html (equity partnerships site - use ventures.html)
```

---

## Cloudflare Pages Setup (Both Sites)

### Site 1: Main VelocityDev (velocitydev.ai)

**Already created if you followed previous guide**

1. **Cloudflare Dashboard** → Workers & Pages → Your existing project
2. **Custom Domains** → Make sure `velocitydev.ai` is connected
3. That's it - your main site is done!

---

### Site 2: VelocityDev Ventures (ventures.velocitydev.ai)

#### Option A: Separate Cloudflare Project (Recommended)

**Why:** Cleaner separation, independent deployments

1. **Create New Project:**
   - Cloudflare Dashboard → Workers & Pages → Create Application
   - Choose "Pages" → "Upload assets"
   - Project name: `velocitydev-ventures`

2. **Upload Ventures Site:**
   - Take your `ventures.html` file
   - Rename it to `index.html` (important!)
   - Upload this file
   - Click "Deploy site"

3. **Add Custom Domain:**
   - In the new project → Custom domains
   - Click "Set up a custom domain"
   - Enter: `ventures.velocitydev.ai`
   - Cloudflare will automatically create the CNAME record
   - Click "Activate domain"

4. **Done!** 
   - Main site: https://velocitydev.ai
   - Ventures site: https://ventures.velocitydev.ai
   - Both have free SSL, both on global CDN

#### Option B: Single Project with Multiple Domains

**Why:** Simpler if you want everything in one place

1. **In your existing project:**
   - Create a folder structure (requires GitHub approach)
   - Not ideal for simple static sites

**Recommendation:** Use Option A (separate projects). Much cleaner.

---

## Email Setup

You need two email addresses:

### 1. hello@velocitydev.ai (Main business)
### 2. ventures@velocitydev.ai (Equity partnerships)

### Cloudflare Email Routing (Free & Easy)

1. **Cloudflare Dashboard** → Email → Email Routing
2. **Enable Email Routing** for velocitydev.ai domain
3. **Create Two Routes:**

   **Route 1:**
   - Destination: `hello@velocitydev.ai`
   - Forward to: Your personal email (e.g., yourname@gmail.com)
   - Action: Deliver

   **Route 2:**
   - Destination: `ventures@velocitydev.ai`
   - Forward to: Your personal email (same or different)
   - Action: Deliver

4. **Send From Custom Address:**
   - In Gmail → Settings → Accounts → "Send mail as"
   - Add both `hello@velocitydev.ai` and `ventures@velocitydev.ai`
   - You can reply from either address

**Result:** All emails go to your personal inbox, but you can reply as either brand.

---

## Pre-Launch Checklist

### Main Site (velocitydev.ai)
- [ ] Update LinkedIn URL (appears 2x in index.html)
- [ ] Confirm email address (hello@velocitydev.ai)
- [ ] Test all links work
- [ ] Test responsive design on mobile

### Ventures Site (ventures.velocitydev.ai)
- [ ] Rename `ventures.html` to `index.html` before upload
- [ ] Ventures email forwarding is working
- [ ] Test application email (send test to ventures@velocitydev.ai)
- [ ] All links to main site work correctly
- [ ] Test responsive design on mobile

### Cross-Site Links
- [ ] Main site links to ventures.velocitydev.ai ✓ (already added)
- [ ] Ventures site links back to velocitydev.ai ✓ (already added)

---

## Deployment Steps (Complete Process)

### Step 1: Deploy Main Site (if not done already)

```
1. Cloudflare Dashboard → Workers & Pages → Create
2. Upload assets → Name: velocitydev
3. Upload index.html (the main site)
4. Deploy site
5. Add custom domain: velocitydev.ai
6. Done!
```

### Step 2: Deploy Ventures Site

```
1. Take ventures.html and rename to index.html
2. Cloudflare Dashboard → Workers & Pages → Create (new project)
3. Upload assets → Name: velocitydev-ventures  
4. Upload index.html (ventures site)
5. Deploy site
6. Add custom domain: ventures.velocitydev.ai
7. Done!
```

### Step 3: Set Up Email Routing

```
1. Cloudflare Dashboard → Email → Email Routing
2. Enable for velocitydev.ai
3. Add route: hello@velocitydev.ai → your email
4. Add route: ventures@velocitydev.ai → your email
5. Done!
```

### Step 4: Test Everything

```
1. Visit https://velocitydev.ai → Should load main site
2. Visit https://ventures.velocitydev.ai → Should load ventures site
3. Click link on main site to ventures → Should work
4. Click link on ventures site to main → Should work
5. Send test email to hello@velocitydev.ai → Should receive
6. Send test email to ventures@velocitydev.ai → Should receive
7. Test both sites on mobile
```

---

## DNS Records (What Cloudflare Creates Automatically)

When you add custom domains, Cloudflare creates:

```
velocitydev.ai
CNAME @ velocitydev.pages.dev (main site)

ventures.velocitydev.ai
CNAME ventures velocitydev-ventures.pages.dev (ventures site)
```

You don't need to create these manually - Cloudflare does it when you add the custom domains!

---

## Updating Your Sites Later

### Main Site Updates:
1. Edit your local `index.html` file
2. Cloudflare Dashboard → velocitydev project
3. "Create new deployment"
4. Upload updated file
5. Live in ~30 seconds

### Ventures Site Updates:
1. Edit your local `ventures.html` file
2. Rename to `index.html`
3. Cloudflare Dashboard → velocitydev-ventures project
4. "Create new deployment"
5. Upload updated file
6. Live in ~30 seconds

---

## Analytics (Optional)

### Add Google Analytics to Track Traffic

**For Main Site:**
1. Get Google Analytics tracking code
2. Add before `</head>` in index.html:
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

**For Ventures Site:**
1. Use same or different Analytics property
2. Add same code before `</head>` in ventures.html

**Result:** You can track which site gets more traffic, where visitors come from, etc.

---

## Marketing Your Two Brands

### Main Site (velocitydev.ai)
**Promote on:**
- LinkedIn (primary profile)
- Direct outreach to SMBs
- Business networking groups
- Google Ads (optional)

**Messaging:**
"Fast, affordable custom software for established businesses"

### Ventures Site (ventures.velocitydev.ai)
**Promote on:**
- Startup communities (Indie Hackers, Y Combinator)
- Founder-focused LinkedIn posts
- Startup accelerators
- Reddit (r/startups, r/entrepreneur)

**Messaging:**
"Your technical co-founder alternative - equity partnerships for ambitious founders"

---

## Brand Consistency

### Visual Separation
**Main Site:** Blue gradient (corporate, professional)
**Ventures Site:** Purple/pink gradient (startup energy, ambitious)

### Tone Separation
**Main Site:** Professional, proven, reliable
**Ventures Site:** Bold, aligned, startup-speak

### Email Signatures

**For Main Business (hello@velocitydev.ai):**
```
[Your Name]
Founder | VelocityDev.ai
AI-Accelerated Software Development

velocitydev.ai
hello@velocitydev.ai
LinkedIn: [your profile]
```

**For Ventures (ventures@velocitydev.ai):**
```
[Your Name]
VelocityDev Ventures
Equity Partnerships for Ambitious Founders

ventures.velocitydev.ai
ventures@velocitydev.ai
LinkedIn: [your profile]
```

---

## Cost Breakdown

**Total cost to run both sites:**

| Item | Cost |
|------|------|
| Domain (velocitydev.ai) | Already purchased |
| Cloudflare Pages (Main) | **FREE** |
| Cloudflare Pages (Ventures) | **FREE** |
| Email Routing (Both addresses) | **FREE** |
| SSL Certificates (Both sites) | **FREE** (auto) |
| Global CDN (Both sites) | **FREE** |
| **Total Monthly Cost** | **$0** |

Only ongoing cost is your domain renewal (~$15-30/year depending on registrar).

---

## Timeline to Launch

- **Hour 1:** Deploy main site (if not done)
- **Hour 1:** Deploy ventures site
- **Hour 1:** Set up email routing
- **Hour 2:** Test everything works
- **Total:** Both sites live in ~2 hours

---

## Next Steps

1. ✅ Deploy velocitydev.ai (main site)
2. ✅ Deploy ventures.velocitydev.ai (ventures site)
3. ✅ Set up email routing (both addresses)
4. ✅ Update LinkedIn with main site link
5. ✅ Test everything works
6. ✅ Announce launch on LinkedIn (main site first)
7. ✅ Week 2-3: Announce ventures (separate post, gauge interest)

---

## Support

**Cloudflare Docs:**
- Pages: https://developers.cloudflare.com/pages/
- Email Routing: https://developers.cloudflare.com/email-routing/
- DNS: https://developers.cloudflare.com/dns/

**Community:**
- Cloudflare Community: https://community.cloudflare.com/
- Cloudflare Discord: Active support community

---

**You're all set!** Two professional brands, zero hosting costs, maximum flexibility. 🚀
