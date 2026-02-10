# Colin McClusick AI Consulting Website

A professional, modern website for AI consulting services built with HTML, CSS, and JavaScript. Ready to deploy on GitHub Pages.

## 🚀 Quick Start - Deploy to GitHub Pages

### Step 1: Create a GitHub Account
1. Go to [github.com](https://github.com)
2. Click "Sign up" and create your free account

### Step 2: Create a New Repository
1. Click the "+" icon in the top right corner
2. Select "New repository"
3. Name it: `yourusername.github.io` (replace `yourusername` with your actual GitHub username)
4. Make sure it's set to **Public**
5. Click "Create repository"

### Step 3: Upload Your Website Files
1. On your new repository page, click "uploading an existing file"
2. Drag and drop ALL these files:
   - `index.html`
   - `about.html`
   - `services.html`
   - `contact.html`
   - `styles.css`
   - `script.js`
   - `README.md` (this file)
3. Scroll down and click "Commit changes"

### Step 4: Enable GitHub Pages
1. In your repository, click "Settings" (top right)
2. Click "Pages" in the left sidebar
3. Under "Source", select "Deploy from a branch"
4. Under "Branch", select "main" and "/ (root)"
5. Click "Save"

### Step 5: Access Your Website
- Your website will be live at: `https://yourusername.github.io`
- It may take 1-2 minutes to deploy the first time
- Refresh the Settings > Pages page to see the live URL

## 📝 Customization Checklist

### Replace Placeholder Image
The website currently has placeholder boxes where your professional photo should go. To add your photo:

1. Get a professional headshot (square format works best, at least 800x800px)
2. Name it `profile.jpg` or `profile.png`
3. Upload it to your GitHub repository
4. Update the image placeholders in:
   - `index.html` (line ~55)
   - `about.html` (line ~55)

Replace this code:
```html
<div class="profile-placeholder">
    <!-- SVG content -->
</div>
```

With:
```html
<img src="profile.jpg" alt="Colin McClusick" style="border-radius: 1rem; width: 100%; max-width: 400px;">
```

### Connect Your Calendar Tool (Optional)
To enable the "Schedule a Call" button to actually book appointments:

1. Sign up for a free calendar booking tool like:
   - [Calendly](https://calendly.com)
   - [Cal.com](https://cal.com)
   - [SavvyCal](https://savvycal.com)

2. Get your booking link from the service

3. In `contact.html`, find line ~134 and replace:
```html
<a href="#" class="calendar-link" id="calendarLink">View Calendar</a>
```

With:
```html
<a href="YOUR_CALENDLY_LINK" target="_blank" class="calendar-link">View Calendar</a>
```

4. In `script.js`, you can remove the calendar link event listener (lines ~115-123) since the link now works directly

### Set Up Form Submissions (Optional)
The contact form currently shows a success message but doesn't actually send emails. To make it functional:

**Option 1: Use Formspree (Easiest)**
1. Sign up at [formspree.io](https://formspree.io)
2. Create a new form and get your endpoint URL
3. In `contact.html`, update the form tag (around line ~45):
```html
<form class="contact-form" action="YOUR_FORMSPREE_URL" method="POST">
```

**Option 2: Use Netlify Forms**
1. Deploy to Netlify instead of GitHub Pages
2. Add `netlify` attribute to the form tag
3. Forms will automatically work

**Option 3: Custom Backend**
- Update the JavaScript in `script.js` (lines ~51-72) to send to your own server endpoint

### Update Content
Edit the HTML files to customize:
- Service descriptions
- Pricing (currently shows "Contact for custom pricing")
- Credentials and achievements
- Timeline dates and descriptions
- FAQ answers

## 🎨 Design Customization

### Change Colors
Edit `styles.css` (lines 8-21) to change the color scheme:

```css
:root {
    --primary-color: #2563eb;  /* Main blue - change this */
    --secondary-color: #06b6d4; /* Teal accent - change this */
    /* ... other colors */
}
```

### Modify Fonts
The website uses the Inter font from Google Fonts. To change:
1. Visit [Google Fonts](https://fonts.google.com)
2. Select your preferred font
3. Replace the font link in the `<head>` of each HTML file
4. Update `--font-primary` in `styles.css`

## 📱 Features Included

- ✅ Fully responsive (mobile, tablet, desktop)
- ✅ Modern, professional design
- ✅ Smooth animations and transitions
- ✅ Mobile-friendly navigation menu
- ✅ Contact form with validation
- ✅ Newsletter signup
- ✅ SEO-optimized structure
- ✅ Fast loading performance
- ✅ Accessible design

## 🔧 Technical Details

### Files Structure
```
├── index.html          # Homepage
├── about.html          # About page
├── services.html       # Services page
├── contact.html        # Contact page
├── styles.css          # All styling
├── script.js           # Interactive features
└── README.md           # This file
```

### Browser Support
- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers

### Performance
- No external dependencies except Google Fonts
- Lightweight (total size < 100KB)
- Fast loading on all devices

## 🎯 Next Steps After Launch

1. **Add Google Analytics** to track visitors
2. **Set up Google Search Console** for SEO
3. **Create blog content** (add a blog.html page)
4. **Add client testimonials** as you get them
5. **Create case studies** of successful projects
6. **Connect social media** profiles
7. **Set up email marketing** integration

## 💡 Tips for Success

- Keep your LinkedIn profile updated and linked
- Regularly update with new projects and achievements
- Consider adding a blog for SEO benefits
- Respond quickly to contact form submissions
- Test the website on multiple devices before sharing

## 🆘 Need Help?

If you run into issues:
1. Check GitHub Pages status: [githubstatus.com](https://www.githubstatus.com)
2. Review GitHub Pages docs: [pages.github.com](https://pages.github.com)
3. Make sure all files are in the root directory (not in folders)
4. Wait 5-10 minutes after uploading for changes to appear

## 📄 License

This website template is free to use and modify for your personal consulting business.

---

**Ready to launch your AI consulting business? Upload these files to GitHub and you'll be live in minutes! 🚀**