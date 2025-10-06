# 1000 Ways to Sit - Website Deployment Guide

**Date:** October 6, 2025  
**Version:** 1.0 - Complete Package

---

## 📦 Package Contents

This complete package contains everything you need to deploy the 1000 Ways to Sit website:

```
1000ways_website_complete/
├── index.html                              (Main website file - 54KB)
├── images/                                 (Banner images folder)
│   ├── 1000Ways_PractitionerBanner01.png  (121KB)
│   └── 1000Ways_ShowBanner01.png          (72KB)
└── DEPLOYMENT_GUIDE.md                     (This file)
```

---

## ✅ Quick Start - Testing Locally

### Step 1: Download the Complete Package

1. Download the entire `1000ways_website_complete` folder
2. Keep the folder structure intact (don't separate files)
3. Make sure the `images` folder stays inside the main folder

### Step 2: Open in Your Browser

**Option A: Direct Open**
1. Navigate to the `1000ways_website_complete` folder on your computer
2. Double-click `index.html`
3. Your default browser should open the website
4. **You should now see both banner images!**

**Option B: Drag and Drop**
1. Open your web browser (Chrome, Firefox, Safari, Edge)
2. Drag the `index.html` file into the browser window
3. The website should load with all images visible

### Step 3: Verify Images Are Showing

You should see:
- **Practitioner Banner** at the top (bronze gong with event details)
- **Show Banner** after the Reserve section ("1000" with bronze instruments)

If you don't see the images, check that:
- The `images` folder is in the same location as `index.html`
- The folder structure hasn't been changed
- You're opening `index.html` (not viewing the raw code)

---

## 🌐 Deploying to a Web Server

### Option 1: Simple Web Hosting (Recommended)

**Services like Netlify, Vercel, or GitHub Pages:**

1. **Create an account** on your chosen platform
2. **Upload the entire folder** (or connect via Git)
3. **Set `index.html` as the main file**
4. **Deploy** - the service will host your site

**Netlify Drop (Easiest):**
1. Go to https://app.netlify.com/drop
2. Drag the entire `1000ways_website_complete` folder onto the page
3. Your site goes live instantly with a URL like `https://random-name.netlify.app`
4. You can then connect your custom domain

### Option 2: Traditional Web Hosting (cPanel, FTP)

**Via FTP Client (FileZilla, Cyberduck):**

1. **Connect to your web server** using FTP credentials
2. **Navigate to your public web directory** (usually `public_html` or `www`)
3. **Upload all files:**
   - Upload `index.html` to the root directory
   - Upload the entire `images` folder (keep it as a folder)
4. **Verify the structure on the server:**
   ```
   public_html/
   ├── index.html
   └── images/
       ├── 1000Ways_PractitionerBanner01.png
       └── 1000Ways_ShowBanner01.png
   ```
5. **Visit your domain** - the site should load with images

**Via cPanel File Manager:**

1. **Log into cPanel**
2. **Open File Manager**
3. **Navigate to public_html**
4. **Upload files:**
   - Click "Upload" button
   - Select `index.html` and upload
   - Create a folder called `images`
   - Enter the `images` folder
   - Upload both banner PNG files
5. **Verify structure** matches the layout above
6. **Visit your domain** to test

---

## 📁 File Structure Requirements

**CRITICAL:** The folder structure must be maintained exactly as shown:

```
your-website-folder/
├── index.html              ← Main HTML file
└── images/                 ← Images folder (must be at same level as index.html)
    ├── 1000Ways_PractitionerBanner01.png
    └── 1000Ways_ShowBanner01.png
```

**Why this matters:**
- The HTML file uses relative paths: `./images/filename.png`
- This means "look in the `images` folder next to this HTML file"
- If the structure changes, the images won't load

---

## 🔧 Adding New Images

### Step 1: Prepare Your Images

1. **Optimize your images** before adding:
   - Use PNG or JPG format
   - Recommended width: 1200-2000px for banners
   - Compress to reduce file size (use TinyPNG.com or similar)
   - Keep file sizes under 200KB if possible

2. **Name your files** clearly:
   - Use descriptive names: `1000Ways_NewBanner.png`
   - Avoid spaces (use underscores or hyphens)
   - Use consistent naming convention

### Step 2: Add Images to the Folder

1. **Copy your new image** into the `images` folder
2. **Note the exact filename** (case-sensitive!)

### Step 3: Update the HTML

**To add a new banner section:**

1. Open `index.html` in a text editor (VS Code, Sublime, Notepad++)
2. Find where you want to add the banner
3. Copy this template:

```html
<!-- Your New Banner -->
<section class="new-banner" style="padding: 0; margin: 0;">
    <div style="width: 100%; max-width: 100%; margin: 0;">
        <img src="./images/YOUR_IMAGE_NAME.png" 
             alt="Descriptive text about this banner" 
             style="width: 100%; height: auto; display: block; margin: 0;">
    </div>
</section>
```

4. **Replace `YOUR_IMAGE_NAME.png`** with your actual filename
5. **Update the alt text** to describe the image
6. **Save the file**
7. **Test in browser** to verify the image appears

**To replace an existing banner:**

1. Find the current banner code (search for "PractitionerBanner" or "ShowBanner")
2. Replace the filename in the `src` attribute
3. Update the alt text if needed
4. Save and test

### Example: Adding a Third Banner

```html
<!-- Third Banner - Community -->
<section class="community-banner" style="padding: 0; margin: 0;">
    <div style="width: 100%; max-width: 100%; margin: 0;">
        <img src="./images/1000Ways_CommunityBanner.png" 
             alt="1000 Ways to Sit - Community Gathering" 
             style="width: 100%; height: auto; display: block; margin: 0;">
    </div>
</section>
```

---

## 🐛 Troubleshooting

### Problem: Images Don't Show When I Open index.html

**Solution 1: Check Folder Structure**
- Verify the `images` folder is in the same location as `index.html`
- Don't move or rename the `images` folder

**Solution 2: Check File Names**
- Image filenames in HTML must exactly match actual filenames
- Check for typos, spaces, or case differences
- Example: `PractitionerBanner01.png` ≠ `practitionerbanner01.png`

**Solution 3: Check File Paths**
- Open `index.html` in a text editor
- Search for `src="./images/`
- Verify the paths start with `./images/` (not `/home/ubuntu/images/`)

### Problem: Images Show Locally But Not on Web Server

**Solution 1: Verify Upload**
- Log into your web server
- Check that the `images` folder uploaded correctly
- Verify both PNG files are inside the `images` folder

**Solution 2: Check Permissions**
- Images folder should have permissions: 755
- Image files should have permissions: 644
- Use your hosting control panel to check/fix permissions

**Solution 3: Check Paths**
- Verify the folder structure on the server matches local structure
- Some servers are case-sensitive (Linux/Unix)
- Make sure `images` folder is lowercase

### Problem: New Images Don't Appear

**Solution 1: Clear Browser Cache**
- Press Ctrl+Shift+R (Windows/Linux) or Cmd+Shift+R (Mac)
- Or open browser in Incognito/Private mode

**Solution 2: Verify Filename**
- Check that the filename in HTML exactly matches the actual file
- Check for extra spaces or special characters

**Solution 3: Check File Format**
- Verify the image is actually PNG or JPG (not a different format)
- Some formats may not display in all browsers

---

## 📝 Best Practices

### For Images

1. **Always optimize images** before adding to reduce file size
2. **Use descriptive alt text** for accessibility
3. **Keep consistent naming** (e.g., all start with "1000Ways_")
4. **Test on multiple devices** after adding new images
5. **Keep originals** - save high-res versions separately

### For File Management

1. **Keep backups** of the complete folder before making changes
2. **Test locally first** before uploading to web server
3. **Document changes** - note what images you added/changed
4. **Version control** - consider using Git for tracking changes

### For Deployment

1. **Test in multiple browsers** (Chrome, Firefox, Safari, Edge)
2. **Test on mobile devices** to verify responsive behavior
3. **Check load speed** - optimize if pages load slowly
4. **Set up SSL** (HTTPS) on your web server for security
5. **Monitor uptime** - use a service to alert if site goes down

---

## 🚀 Quick Deployment Checklist

Before going live, verify:

- [ ] All images display correctly locally
- [ ] Folder structure is correct (`images` folder at same level as `index.html`)
- [ ] All image filenames match exactly in HTML
- [ ] Images are optimized (reasonable file sizes)
- [ ] Alt text is descriptive and helpful
- [ ] Tested in at least 2 different browsers
- [ ] Tested on mobile device or responsive mode
- [ ] All links work (Eventbrite links, navigation links)
- [ ] Uploaded entire folder structure to web server
- [ ] Verified images show on live site
- [ ] Checked site on mobile network (not just WiFi)
- [ ] SSL certificate installed (HTTPS)
- [ ] Custom domain connected (if applicable)

---

## 📞 Support Resources

### If Images Still Don't Show

1. **Take a screenshot** of what you see (or don't see)
2. **Check browser console** for errors:
   - Right-click on page → Inspect → Console tab
   - Look for red error messages about images
3. **Verify file structure** with a screenshot of your folder
4. **Share details** about where you're trying to view it:
   - Local computer? Which browser?
   - Web server? Which hosting service?

### Helpful Tools

- **Image Optimization:** TinyPNG.com, Squoosh.app
- **FTP Client:** FileZilla (free), Cyberduck (Mac)
- **Text Editor:** VS Code (free), Sublime Text
- **Browser Testing:** BrowserStack.com (cross-browser testing)
- **Speed Testing:** PageSpeed Insights, GTmetrix

---

## 📧 Adding More Images - Step-by-Step Example

Let's say you want to add a new "Testimonials Banner":

**Step 1: Prepare the Image**
- Save your image as: `1000Ways_TestimonialsBanner.png`
- Optimize it to under 150KB
- Verify dimensions are appropriate (1200-2000px wide)

**Step 2: Add to Images Folder**
```
images/
├── 1000Ways_PractitionerBanner01.png
├── 1000Ways_ShowBanner01.png
└── 1000Ways_TestimonialsBanner.png  ← NEW
```

**Step 3: Edit HTML**
Open `index.html` and find where you want to add it (e.g., before the Support section). Add:

```html
<!-- Testimonials Banner -->
<section class="testimonials-banner" style="padding: 0; margin: 0;">
    <div style="width: 100%; max-width: 100%; margin: 0;">
        <img src="./images/1000Ways_TestimonialsBanner.png" 
             alt="1000 Ways to Sit - Visitor Testimonials" 
             style="width: 100%; height: auto; display: block; margin: 0;">
    </div>
</section>
```

**Step 4: Save and Test**
- Save `index.html`
- Refresh browser (Ctrl+Shift+R)
- Verify the new banner appears

**Step 5: Deploy**
- Upload the new image to your web server's `images` folder
- Upload the updated `index.html` file
- Test on the live site

---

## ✨ Summary

**To view the website with images:**
1. Download the entire `1000ways_website_complete` folder
2. Keep the folder structure intact
3. Open `index.html` in your browser
4. Both banners should now be visible!

**To add new images:**
1. Add image files to the `images` folder
2. Update `index.html` with the new image path
3. Test locally before deploying
4. Upload both the new image and updated HTML to your server

**The key:** Always maintain the folder structure with `images` folder at the same level as `index.html`, and use relative paths (`./images/filename.png`) in the HTML.

---

**Need Help?** 

If you're still having trouble seeing the images, please share:
1. Where you're trying to view it (local computer or web server)
2. What browser you're using
3. A screenshot of your folder structure
4. Any error messages from the browser console

This will help diagnose the specific issue you're experiencing.

---

**Created by:** Manus AI  
**Date:** October 6, 2025  
**Version:** 1.0 - Complete Package with Images
