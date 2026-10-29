# TreatyBox Android App — source project

This is a simple Android app for TreatyBox. It includes:
- Menu and snack box prices: Budget ₹60, Standard ₹80, Special ₹100, Premium ₹120
- Breakfast, lunch/tiffin and catering inquiry sections
- Order inquiry form that prepares a message for WhatsApp
- Phone, email and service-area details

## Important limitations
- This project is source code, not a prebuilt APK.
- Orders are sent as a WhatsApp message for the customer to review and send. The app does not save orders in a database and does not process payments.
- Internet access is not needed to display the bundled menu; WhatsApp, email and phone actions need the relevant app/network.
- Please verify the menu, contact details, prices and business details before publishing.

## Build an installable APK using Android Studio
1. On a computer, install the latest stable Android Studio from https://developer.android.com/studio
2. Extract `TreatyBoxAndroid.zip`.
3. In Android Studio, choose **Open** and select the extracted `TreatyBoxAndroid` folder (the folder containing `settings.gradle`).
4. Allow Android Studio to download the Android Gradle plugin and SDK components if prompted. Use JDK 17 if asked.
5. If Android Studio asks to install Android SDK Platform 35, install it from **Tools → SDK Manager**.
6. Choose **Build → Build Bundle(s) / APK(s) → Build APK(s)**.
7. When the build finishes, click the notification's **locate** link. The debug APK is usually at:
   `app/build/outputs/apk/debug/app-debug.apk`
8. Transfer that APK to your Android phone. Open it and allow installation from that source if Android prompts you. Only install APKs you built or otherwise trust.

## Make it available to customers
- For a small private test, share the APK directly with trusted testers. Android may show a warning because it is not distributed through Google Play.
- For public distribution, create a signed release build in Android Studio (**Build → Generate Signed Bundle / APK**) and follow Google Play Console's current developer, testing and publishing requirements.
- A public website is often easier for school customers because they can open a link without installing an app. You can later publish the same menu and inquiry flow as a website.

## Branding and contact
- App name: TreatyBox
- Service area: Badlapur, Maharashtra
- Email: Treatyboxes@gmail.com
- Phone / WhatsApp: 7038485318
- Alternate phone: 7030386998
- Tagline: Treat with box, treat with love.

## Customising
- Edit `app/src/main/assets/index.html` to update the menu, styles, text or WhatsApp number.
- Update the `applicationId` in `app/build.gradle` before publishing under your own unique package ID if needed.


## Build the APK using only your Android phone (GitHub Actions)
This project includes `.github/workflows/android.yml`, which builds the debug APK on GitHub's cloud runner.

1. Download and extract the ZIP on your phone using your file manager or an archive app.
2. In your phone browser, sign in to https://github.com/ and create a **new repository** named `TreatyBoxAndroid`. For the simplest setup, make it public; do not upload passwords, private keys, customer data, or other secrets.
3. Open the repository and use **Add file → Upload files**. Upload the extracted project contents, including the hidden `.github` folder if the mobile browser/file picker allows it. Commit to the `main` branch.
4. Open the repository's **Actions** tab. Select **Build TreatyBox Android APK**, then tap **Run workflow** if it has not already started.
5. Open the completed workflow run. In **Artifacts**, download `TreatyBox-debug-APK`. Extract that artifact ZIP to get `app-debug.apk`.
6. Open the APK on your phone and follow Android's prompts to allow installation from that source.

Mobile GitHub upload interfaces can make uploading folders and hidden `.github` files difficult. If you cannot upload the workflow folder from your phone, create `.github/workflows/android.yml` directly in GitHub using **Add file → Create new file** and paste the contents from the project ZIP's workflow file. Then commit it to `main`.

This produces a **debug/test APK** for installation and testing, not a Play Store release. For public Google Play distribution, generate a properly signed release and follow the current Play Console requirements. Never share a signing key or its passwords.

