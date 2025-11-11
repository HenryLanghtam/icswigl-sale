# ICSWIGL - Accessibility Scaling App for Android

<img src="app/src/main/ic_launcher-playstore.png" alt="ICSWIGL Icon" width="100"/>

## 🌟 Overview

**ICSWIGL** (Icon & Content Scaling WIGL) is a powerful Android accessibility application designed to help users with vision impairments adjust text and UI scaling across their device. The app provides both system-wide and standalone scaling modes, multilingual support (English, Russian, Romanian), and innovative voice control features.

### Key Features

✅ **Smart Scaling System**
- 11 precise scaling levels (-5 to +5)
- Medical-grade scaling based on vision standards (20/200 to 20/6)
- Smooth transitions with scientifically calibrated factors (50% to 180%)
- Real-time preview of text scaling

✅ **Dual Operating Modes**
- **System Mode**: Apply scaling system-wide across all apps
- **Standalone Mode**: Apply scaling only in the built-in browser (no system permissions required)

✅ **Multilingual Support**
- English, Russian, and Romanian languages
- Runtime localization with seamless language switching
- All UI elements fully translated

✅ **Voice Control**
- Hands-free operation with voice commands
- Find phone feature with flashlight and vibration
- Support for commands in all 3 languages

✅ **Built-in Browser**
- WebView-based browser with adjustable scaling
- Persistent zoom levels per website
- Optimized for accessibility

✅ **User-Friendly Interface**
- Material Design 3 components
- High-contrast color schemes
- Large, easy-to-tap buttons
- Keyboard-friendly IME handling

---

## 📱 Technical Specifications

### Platform
- **Target Android Version**: API 35 (Android 15)
- **Minimum SDK**: API 24 (Android 7.0)
- **Language**: Kotlin
- **Architecture**: MVVM with helper utilities

### Technologies Used
- **UI Framework**: Jetpack Compose + Material Design 3
- **Localization**: AppCompat Locales with runtime string provider
- **Voice Recognition**: Android Speech Recognizer
- **WebView**: Custom WebView with zoom persistence
- **Storage**: SharedPreferences for settings
- **Permissions**: 
  - `WRITE_SETTINGS` (for system-wide scaling)
  - `RECORD_AUDIO` + `CAMERA` (for voice control)
  - `POST_NOTIFICATIONS` (for voice service)

### Project Structure
```
app/src/main/java/com/example/icswigl/
├── MainActivity.kt              # Main UI and scaling controls
├── LanguageSelectionActivity.kt # Language picker
├── LicenseActivity.kt           # EULA acceptance
├── LauncherActivity.kt          # Smart routing logic
├── ReaderActivity.kt            # Built-in browser
├── VoiceCommandService.kt       # Voice recognition service
├── UiStrings.kt                 # Runtime localization provider
├── ScaleTable.kt                # Medical-grade scaling logic
├── DirectScalingHelper.kt       # System settings manipulation
├── StandaloneModeHelper.kt      # Standalone mode logic
├── LanguageManager.kt           # Language switching
└── [Other helpers]
```

---

## 🚀 Getting Started

### Prerequisites
- Android Studio Hedgehog or later
- JDK 17+
- Android SDK 35
- Gradle 8.7+

### Build Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/ICSWIGL.git
   cd ICSWIGL
   ```

2. **Open in Android Studio**
   - Open Android Studio
   - Select "Open an Existing Project"
   - Navigate to the cloned directory

3. **Build the project**
   ```bash
   ./gradlew assembleDebug
   ```

4. **Install on device**
   ```bash
   adb install app/build/outputs/apk/debug/app-debug.apk
   ```

### Configuration

No additional configuration required! The app works out-of-the-box with default settings.

---

## 📖 User Guide

### First Launch
1. **Select Language**: Choose English, Russian, or Romanian
2. **Accept License**: Review and accept the EULA
3. **Main Screen**: Access all scaling and accessibility features

### Scaling Modes

#### System Mode (Default)
- Requires `WRITE_SETTINGS` permission
- Applies scaling globally across all apps
- Persistent across reboots

#### Standalone Mode
- Works without system permissions
- Scaling applies only in the built-in browser
- Perfect for quick testing

### Voice Commands

Activate voice control and use:
- **"hello wigl"** - Activate command mode
- **"wigl"** or **"wigl wigl"** - Find phone (flashlight + vibration)
- **"hello wigl choose plus three"** - Increase scaling by +3
- **"hello wigl reset"** - Reset to 100%

---

## 🎯 Market Potential

### Target Audience
- **Visually Impaired Users**: 285+ million people worldwide
- **Elderly Users**: Growing smartphone adoption among 60+ age group
- **Accessibility-Focused Organizations**: Schools, healthcare, government

### Competitive Advantages
1. **Medical-Grade Scaling**: Based on Snellen vision chart standards
2. **Multilingual**: Supports major languages (easily extendable)
3. **Voice Control**: Unique hands-free operation
4. **No Root Required**: Works on stock Android devices
5. **Dual Modes**: Flexibility for different permission scenarios

### Monetization Opportunities
- **Freemium Model**: Basic features free, premium features paid
- **Enterprise Licensing**: Bulk licenses for organizations
- **White-Label**: Rebrand for healthcare/education sectors
- **In-App Purchases**: Additional languages, themes, voice packs
- **Ads**: Optional ad-supported free tier

### Growth Potential
- **Localization**: Add 10+ more languages (Spanish, German, French, etc.)
- **AI Features**: Smart scaling based on user behavior
- **Cloud Sync**: Settings sync across devices
- **Accessibility Suite**: Expand to color blindness, hearing assistance
- **Wearable Integration**: Control from smartwatch

---

## 📊 Metrics

### Current State
- **Lines of Code**: ~5,000
- **Supported Languages**: 3 (EN, RU, RO)
- **Scaling Levels**: 11 precise levels
- **Voice Commands**: 15+ commands
- **Target Users**: 285M+ visually impaired people globally

### Development Stats
- **Development Time**: 3 months
- **Updates**: Regular feature additions
- **Bug Reports**: Active bug fixing and improvements
- **Code Quality**: Production-ready, well-documented

---

## 🔧 Customization

### Adding New Languages

1. Add translations to `UiStrings.kt`:
```kotlin
private val esStrings = UiStrings(
    appName = "ICSWIGL",
    selectLanguage = "Seleccionar idioma",
    // ... add all fields
)
```

2. Update `get()` method:
```kotlin
fun get(languageCode: String): UiStrings {
    return when (languageCode) {
        "ru" -> ruStrings
        "ro" -> roStrings
        "es" -> esStrings // Spanish
        else -> enStrings
    }
}
```

### Customizing Scaling Levels

Edit `ScaleTable.kt`:
```kotlin
fun indexToFactor(index: Int): Float {
    return when (index) {
        -5 -> 0.5f  // Modify these values
        // ...
    }
}
```

---

## 🛡️ License

This project is licensed under a custom EULA included in the app. Review `LicenseActivity.kt` for details.

### Key Terms
- App provided "as-is"
- No analytics or tracking
- Data stays on device
- Requires user acceptance before use

---

## 🤝 Support & Contact

For support, feature requests, or business inquiries:
- **Email**: your-email@example.com
- **GitHub Issues**: [Report a bug](https://github.com/yourusername/ICSWIGL/issues)

---

## 💰 For Sale on Flippa

This fully functional Android app is available for purchase on Flippa!

### What You Get
✅ Complete source code (Kotlin + XML)
✅ All assets and resources
✅ Technical documentation
✅ Build/deployment instructions
✅ Multilingual support (3 languages)
✅ Voice control system
✅ Medical-grade scaling algorithm
✅ Transfer of all rights

### Potential Revenue Streams
1. Google Play Store listing (free with ads or premium)
2. Enterprise/B2B licensing
3. White-label solutions for healthcare
4. In-app purchases for additional features
5. Subscription model for cloud features

### Why Buy This App?
- **Proven Technology**: Fully functional and tested
- **Niche Market**: Underserved accessibility sector
- **Global Reach**: Multilingual from day one
- **Extensible**: Easy to add features and monetize
- **Low Maintenance**: Stable codebase, minimal dependencies

---

## 📸 Screenshots

*[Screenshots will be added to the landing page]*

---

## 🏆 Awards & Recognition

- Medical-grade scaling algorithm
- Innovative voice control for accessibility
- Multilingual support for global reach

---

**Built with ❤️ for accessibility**

