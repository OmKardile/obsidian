obsidian://open?vault=Obsidian%20Vault&file=capacitor  

## How to Compile to APK using Capacitor

  

To convert this web application into a native Android APK, you can use [Capacitor](https://capacitorjs.com/).

  

### Prerequisites

1. Node.js installed

2. Android Studio installed (for compiling the APK)

3. Java Development Kit (JDK) installed

  

### Steps

  

1. **Install Capacitor CLI and Core:**

   ```bash

   npm install @capacitor/core

   npm install @capacitor/cli --save-dev

   ```

  

2. **Initialize Capacitor in the project:**

   

   npx cap init

   

  

3. **Install the Android platform:**

   ```bash

   npm install @capacitor/android

   npx cap add android

   ```

  

4. **Build the web app:**

   ```bash

   npm run build

   ```

  

5. **Sync the built web assets to the Android project:**

   ```bash

   npx cap sync android

   ```

  

6. **Open Android Studio to build the APK:**

   ```bash

   npx cap open android

   ```

   Once Android Studio opens:

   - Wait for Gradle to sync.

   - Go to `Build` > `Build Bundle(s) / APK(s)` > `Build APK(s)`.

   - Once the build is complete, you will see a popup in the bottom right corner with a link to "locate" the generated APK file.

  

### Notes

- All data is stored locally on the device using `localStorage`. If the user uninstalls the app or clears app data, their records will be lost. Consider adding an export/import feature in the future to backup data.

- The app is fully offline and requires no backend server.