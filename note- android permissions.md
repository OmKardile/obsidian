Good idea. Let's keep it simple.

# 1. Change App Logo (Adaptive Icon)

### Method (Recommended)

Open **Android Studio**

```
android/
```

Then:

```
File
→ New
→ Image Asset
```

Configure:

```
Asset Type:
Launcher Icons (Adaptive and Legacy)

Foreground:
Your PNG logo

Background:
Choose a solid color
(or transparent if your logo already has padding)

Name:
ic_launcher
```

Android Studio will automatically generate:

```
mipmap-mdpi
mipmap-hdpi
mipmap-xhdpi
mipmap-xxhdpi
mipmap-xxxhdpi

ic_launcher.png
ic_launcher_round.png
```

No manual editing required.

---

# 2. Change App Name

Edit:

```
android/app/src/main/res/values/strings.xml
```

```xml
<resources>
    <string name="app_name">Dear Abantika</string>
    <string name="title_activity_main">Dear Abantika</string>
</resources>
```

---

# 3. Permissions

Add these inside **manifest** but **outside `<application>`**.

```xml
<!-- Internet -->
<uses-permission android:name="android.permission.INTERNET"/>

<!-- Notifications (Android 13+) -->
<uses-permission android:name="android.permission.POST_NOTIFICATIONS"/>

<!-- Vibrate -->
<uses-permission android:name="android.permission.VIBRATE"/>

<!-- Wake device for reminders -->
<uses-permission android:name="android.permission.WAKE_LOCK"/>

<!-- Exact alarms -->
<uses-permission android:name="android.permission.SCHEDULE_EXACT_ALARM"/>

<!-- Restore reminders after reboot -->
<uses-permission android:name="android.permission.RECEIVE_BOOT_COMPLETED"/>
```

Your `<manifest>` should become:

```xml
<manifest ...>

    <uses-permission android:name="android.permission.INTERNET"/>
    <uses-permission android:name="android.permission.POST_NOTIFICATIONS"/>
    <uses-permission android:name="android.permission.VIBRATE"/>
    <uses-permission android:name="android.permission.WAKE_LOCK"/>
    <uses-permission android:name="android.permission.SCHEDULE_EXACT_ALARM"/>
    <uses-permission android:name="android.permission.RECEIVE_BOOT_COMPLETED"/>

    <application>
        ...
    </application>

</manifest>
```

---

# 4. Add Application Properties

Inside `<application>` add these:

```xml
android:allowBackup="true"
android:fullBackupContent="true"
android:hardwareAccelerated="true"
android:usesCleartextTraffic="false"
android:supportsRtl="true"
```

Result:

```xml
<application
    android:allowBackup="true"
    android:fullBackupContent="true"
    android:hardwareAccelerated="true"
    android:usesCleartextTraffic="false"
    android:icon="@mipmap/ic_launcher"
    android:roundIcon="@mipmap/ic_launcher_round"
    android:label="@string/app_name"
    android:supportsRtl="true"
    android:theme="@style/AppTheme">
```

---

# 5. App Version

Edit:

```
android/app/build.gradle
```

or

```
android/app/build.gradle.kts
```

Set:

```
versionCode 1
versionName "1.0.0"
```

---

## I would **not** add these yet

❌ Camera  
❌ Microphone  
❌ Storage (`READ_MEDIA_*`)  
❌ Contacts  
❌ Location  
❌ Calendar  
❌ Bluetooth

Only request permissions when you actually implement a feature that needs them. This keeps the app more privacy-friendly and avoids unnecessary permission prompts.

---

## Next

Once the logo is in place and the app builds again, the next Android enhancement I'd recommend is implementing **native local notifications** for hydration, brushing, skincare, medicine, and reminders, so they continue to work even when the app isn't open.