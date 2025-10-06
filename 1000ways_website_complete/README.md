# 1000 Ways to Sit - Complete Website Package

## 🎉 Quick Start

**To view the website with banner images:**

1. **Download this entire folder** (`1000ways_website_complete`)
2. **Keep the folder structure intact** - don't separate the files
3. **Double-click `index.html`** to open in your browser
4. **You should see both banner images!**

## 📁 What's Included

- `index.html` - Main website file
- `images/` - Folder containing banner images
  - `1000Ways_PractitionerBanner01.png` (top banner)
  - `1000Ways_ShowBanner01.png` (middle banner)
- `DEPLOYMENT_GUIDE.md` - Complete instructions for deployment and adding images
- `README.md` - This file

## ⚠️ Important

**The folder structure must stay exactly like this:**

```
1000ways_website_complete/
├── index.html
└── images/
    ├── 1000Ways_PractitionerBanner01.png
    └── 1000Ways_ShowBanner01.png
```

If you move or rename the `images` folder, the banners won't display!

## 🚀 To Deploy Online

See `DEPLOYMENT_GUIDE.md` for complete instructions on:
- Uploading to web hosting
- Using services like Netlify or Vercel
- Adding new images
- Troubleshooting

## 📧 Adding New Images

1. Add your image file to the `images/` folder
2. Open `index.html` in a text editor
3. Add this code where you want the image:

```html
<section class="your-banner" style="padding: 0; margin: 0;">
    <div style="width: 100%; max-width: 100%; margin: 0;">
        <img src="./images/YOUR_IMAGE_NAME.png" 
             alt="Description of your image" 
             style="width: 100%; height: auto; display: block; margin: 0;">
    </div>
</section>
```

4. Replace `YOUR_IMAGE_NAME.png` with your actual filename
5. Save and refresh your browser

## ✅ Verify It's Working

When you open `index.html`, you should see:

1. **Practitioner Banner** at the top - bronze gong with event details
2. **Show Banner** after the Reserve section - "1000" with bronze instruments

If you don't see these, check that the `images` folder is in the same location as `index.html`.

## 🐛 Troubleshooting

**Images don't show?**
- Make sure you downloaded the entire folder (not just the HTML file)
- Check that the `images` folder is next to `index.html`
- Try opening in a different browser
- See `DEPLOYMENT_GUIDE.md` for more solutions

## 📞 Need Help?

Read the complete `DEPLOYMENT_GUIDE.md` for detailed instructions and troubleshooting.

---

**Version:** 1.0  
**Date:** October 6, 2025  
**Status:** Production Ready
