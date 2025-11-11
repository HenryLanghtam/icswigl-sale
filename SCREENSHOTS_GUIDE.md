# Screenshot Guide for Google Play Store

## 📸 Required Screenshots

Google Play requires **minimum 2 screenshots**, recommended **8 screenshots** for best presentation.

### Screenshot Specifications
- **Phone**: 16:9 aspect ratio, minimum 320px, maximum 3840px
- **Tablet**: 16:9 or 16:10, same size requirements
- **Recommended Size**: 1080×1920 (phone), 1920×1080 or 2560×1600 (tablet)
- **Format**: PNG or JPEG, 24-bit RGB, no alpha channel

---

## 🎯 Recommended Screenshots (in order)

### 1. Main Screen - English (Primary Language)
**What to show**:
- App title at top
- Scaling preview with "Aa Bb 123"
- All main buttons visible
- Current scale indicator

**How to capture**:
1. Open app, select English
2. Set scale to 0 (100%)
3. Take screenshot: `adb shell screencap -p /sdcard/screenshot1.png`
4. Pull: `adb pull /sdcard/screenshot1.png screenshots/`

**Caption**: "Clean, intuitive interface with medical-grade text scaling"

---

### 2. Scaling Preview - Large Text
**What to show**:
- Preview text at +3 or +4 level
- Visible size difference

**How**:
1. Tap "+ Increase"
2. Select "+3"
3. Take screenshot

**Caption**: "11 precision scaling levels for different vision needs"

---

### 3. Voice Control Interface
**What to show**:
- Voice control section
- "Turn on voice control" button (or if enabled, show "Turn off")
- Voice commands help button

**How**:
1. Scroll to voice control section
2. Take screenshot

**Caption**: "Hands-free control with 15+ voice commands in 3 languages"

---

### 4. Built-in Browser
**What to show**:
- Browser section
- URL input field
- A website loaded with scaled text (optional: open https://point.md)

**How**:
1. Enter a URL
2. Tap "Open"
3. Take screenshot in ReaderActivity

**Caption**: "Accessible browser with persistent zoom and site-specific settings"

---

### 5. Language Selection
**What to show**:
- Three language buttons
- English, Romanian, Russian flags/text

**How**:
1. From MainActivity, press back button until LanguageSelectionActivity
2. Or reinstall app
3. Take screenshot on language screen

**Caption**: "Multilingual support: English, Russian, Romanian (easy to add more)"

---

### 6. Standalone Mode
**What to show**:
- Standalone mode section
- Toggle button
- Description text

**How**:
1. Scroll to standalone mode card
2. Take screenshot

**Caption**: "Dual modes: system-wide scaling or browser-only (no permissions required)"

---

### 7. System Settings Section
**What to show**:
- Icon size section
- Display settings buttons

**How**:
1. Scroll to system settings / icon size section
2. Take screenshot

**Caption**: "Comprehensive accessibility controls including system icon sizing"

---

### 8. License/Welcome Screen
**What to show**:
- License agreement screen with Agree/Disagree buttons

**How**:
1. Reinstall app
2. Select language
3. Take screenshot on license screen

**Caption**: "User-friendly onboarding with clear privacy policy"

---

## 🎨 Professional Screenshot Enhancement

### Option 1: Use Android Studio Layout Inspector
- Better quality than device screenshots
- Can remove status bar clutter
- Clean, professional look

### Option 2: Screenshot Framing Tools

Free tools:
- **Screely** (https://www.screely.com/) - Add device frames
- **MockUPhone** (https://mockuphone.com/) - Device mockups
- **Smartmockups** (https://smartmockups.com/) - Professional frames

### Option 3: Add Captions/Annotations

Use **Canva** (free):
1. Upload screenshot
2. Add text overlays highlighting features
3. Add arrows pointing to key UI elements
4. Export as PNG

---

## 🖼️ Feature Graphic

**Required for Google Play**: 1024×500px banner

### Design Tips:
1. Use app icon on left
2. App name + tagline in center/right
3. Key benefit or feature callout
4. Brand colors (purple gradient from app)

### Tools:
- **Canva**: Use "Google Play Feature Graphic" template
- **Figma**: Professional design tool (free tier)
- **Photoshop**: If you have it

### Example Text:
```
ICSWIGL
Medical-Grade Text Scaling for Android
Voice Control • 3 Languages • Accessibility First
```

---

## 📱 Promo Video (Optional but Recommended)

### Script (30-60 seconds):

1. **Opening (5s)**: Show app icon + name
2. **Problem (10s)**: "Millions struggle to read small text on their phones"
3. **Solution (15s)**: Show scaling feature in action
4. **Features (20s)**: Quick cuts of voice control, languages, browser
5. **Call to Action (10s)**: "Download ICSWIGL today - See clearly, live better"

### Tools:
- **Screen Recording**: Built-in Android screen recorder
- **Editing**: DaVinci Resolve (free), iMovie, or CapCut
- **Music**: YouTube Audio Library (free, copyright-safe)

### Recording Steps:
```bash
# Start recording
adb shell screenrecord /sdcard/demo.mp4

# Use app for 30-60 seconds

# Stop recording (Ctrl+C)
# Pull video
adb pull /sdcard/demo.mp4
```

---

## 📋 Screenshot Checklist

- [ ] 8 phone screenshots (1080×1920)
- [ ] 2-4 tablet screenshots (optional)
- [ ] Feature graphic (1024×500)
- [ ] App icon (512×512 for store listing)
- [ ] Promo video (optional, 30-60s)
- [ ] All screenshots show English language
- [ ] No personal information visible
- [ ] No offensive content
- [ ] High quality (no pixelation)
- [ ] Consistent UI state (no debug info)

---

## 🎯 Quick Capture Script

Save this as `capture-screenshots.sh`:

```bash
#!/bin/bash

# Create screenshots directory
mkdir -p screenshots

echo "Make sure app is open in English language!"
sleep 3

# Capture screenshots
for i in {1..8}; do
    echo "Prepare screen $i and press Enter..."
    read
    adb shell screencap -p /sdcard/screenshot$i.png
    adb pull /sdcard/screenshot$i.png screenshots/
    echo "Screenshot $i saved!"
done

echo "All screenshots captured in screenshots/ folder"
```

Run: `bash capture-screenshots.sh`

---

## 🎨 Screenshot Post-Processing

### Use This Workflow:
1. **Capture** raw screenshots (steps above)
2. **Frame** screenshots in device mockup (MockUPhone)
3. **Annotate** key features (Canva or Figma)
4. **Optimize** file size (TinyPNG.com)
5. **Upload** to Google Play Console

### Example Annotations:
- Arrow → "11 Precision Levels"
- Highlight → "Voice Control"
- Text Box → "Medical-Grade Scaling"

---

## 💡 Pro Tips

1. **Use Real Content**: Don't use "Lorem ipsum" - shows professionalism
2. **Highlight Key Features**: Use arrows, circles, text overlays
3. **Show Value**: Each screenshot should answer "Why should I download?"
4. **Consistent Branding**: Same style across all screenshots
5. **Tell a Story**: Order screenshots to show user journey
6. **Multilingual Bonus**: Include 1-2 screenshots in other languages (shows global appeal)

---

## 🚀 Quick Start (For Busy Buyers)

Don't have time for perfect screenshots? Here's the minimum:

1. **Screenshot 1**: Main screen (English, scale at 0)
2. **Screenshot 2**: Scaling preview (scale at +3, show larger text)
3. **Feature Graphic**: Use Canva template, add app name + icon

**Time needed**: 15-20 minutes

**Good enough for**: Initial launch, can improve later

---

## 📤 Where to Upload

- **Google Play Console**: In app listing, under "Store Listing" → "Graphics"
- **Flippa Listing**: Upload to image gallery
- **Landing Page**: Use in `docs/index.html` (replace placeholders)
- **Marketing**: Social media, app review sites, press releases

---

**Need help?** Screenshots are included in the support period - just ask!

