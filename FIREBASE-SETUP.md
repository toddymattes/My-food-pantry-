# Shared family pantry setup

This app version uses Firebase Authentication and Cloud Firestore. Each family member has their own login; both see and update the same live inventory.

## 1. Create Firebase project
1. Visit https://console.firebase.google.com/ and create a project.
2. Project settings → General → Your apps → Add app → Web. Register it and copy the web config.
3. Authentication → Sign-in method → enable Email/Password.
4. Firestore Database → Create database.

## 2. Publish secure database rules
In Firestore → Rules, replace the rules with the contents of `firestore.rules` in this package, then Publish. Only authenticated users with a matching `pantryMembers` record can read or change pantry data.

## 3. Create family accounts
1. Open the GitHub Pages app and use Create account with your email and a strong password.
2. Have your family member open the same app and create their own account.
3. Firebase Console → Authentication → Users. Copy each account's User UID.

## 4. Authorize only those two accounts
In Firestore → Data, create collection `pantryMembers`. Create one document for each UID, using the exact UID as Document ID. Add a field `active` (boolean) = `true`. Only add the two family accounts you trust. Do not share passwords.

## 5. Connect GitHub Pages app
1. In your GitHub repository, open `index.html` and choose Edit (pencil).
2. Find `const firebaseConfig = {...}` near the start of the script.
3. Replace every `PASTE_...` placeholder with the exact values from your Firebase web app config. Keep quotes and commas.
4. Commit the change to `main`, then reload your GitHub Pages website and sign in.

## 6. Move existing pantry counts
Your current inventory remains in the original browser's local storage; it is not automatically copied. Keep the old app available and add each existing food and its current quantity once in the new shared app.

## Important
- Firebase config is intended to be present in a client app; Firestore rules provide access control.
- Never share passwords. Each family member uses their own account.
- Anyone listed in `pantryMembers` can fully read and change all pantry items.
- This package is a template until you create Firebase and paste the config.
