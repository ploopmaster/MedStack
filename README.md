# MedStack

A colourful medical-student resource website with:
- Google sign-in
- Public resource library
- Search + category filters
- Upload PDFs, Word files, PowerPoint, Excel, text files and images
- Firebase Storage for files
- Firestore for resource metadata
- Responsive desktop/mobile design

## 1. Create Firebase project
1. Open https://console.firebase.google.com/
2. Create a project named `MedStack`.
3. Add a Web App.
4. Copy its Firebase configuration.
5. In `index.html`, replace the `YOUR_*` values in `firebaseConfig`.

## 2. Enable Google login
Firebase Console → Authentication → Sign-in method → Google → Enable.
Add your deployed domain under Authentication → Settings → Authorized domains.

## 3. Enable Firestore
Create a Firestore database. Start in production mode, then deploy the included `firestore.rules`.

## 4. Enable Storage
Create/enable Firebase Storage, then deploy the included `storage.rules`.

## 5. Run locally
Because Firebase modules are loaded by the browser, serve the folder from a local web server rather than opening index.html with file://.

Example:
- VS Code: install Live Server and open `index.html`.
- Or run `python -m http.server 5500` in this folder and visit http://localhost:5500

## 6. Deploy
You can deploy the folder with Firebase Hosting, Netlify, Vercel, GitHub Pages (with appropriate configuration), or another static host.

### Firebase CLI example
npm install -g firebase-tools
firebase login
firebase init hosting
firebase deploy

## Important production notes
- The included rules let anyone read uploaded resources. This is intentional for a public resource library.
- Only authenticated users can upload.
- Users can modify/delete only their own Firestore resource records.
- Storage write access is limited to each user's own upload directory.
- For a real public platform, add moderation/reporting, file-type validation, malware scanning, rate limits, abuse controls, pagination, and an admin role before launch.
- Only upload material you have permission to distribute. Avoid hosting copyrighted textbooks or other protected content without permission.
