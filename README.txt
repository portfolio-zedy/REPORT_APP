LBD Daily Report Tool - mobile app (PWA)

Files: index.html, manifest.webmanifest, sw.js, icons/   (keep them together in one folder)

HOW TO PUT IT ON A PHONE
1. Upload this whole folder to any HTTPS web host (GitHub Pages, Netlify, Cloudflare Pages, Firebase Hosting, your own site).
2. Open the link on the phone.
   Android (Chrome): menu > Install app (or use "Install app on this device" in the tool's menu).
   iPhone/iPad (Safari): Share > Add to Home Screen.
3. It opens full screen with its own icon and keeps working offline.

APP LOCK
- Settings > App lock turns on fingerprint / face / phone screen lock (plus a backup PIN). It needs the https link.
- Lock settings stay on each device and are not part of Settings export.

SAVE CSV TO GOOGLE DRIVE
- Settings > Save the Zoom .csv to Google Drive. Choose when to save and (optionally) a Drive folder.
- One-time: paste the saveCsv_ script (shown in that card) into your engine Apps Script, add the 'saveCsv' case to doPost, then Deploy > New version and approve the Drive permission.
- Use 'Test the connection' to check it.

ADMIN ACCOUNTS, SIGN-UP AND APPROVALS
- Other admins create an account (name, email, phone, area, password) from the sign-in page; the central admin approves them under Requests > Sign-ups before they can enter.
- Registration details go to the engine workbook's 'Admin accounts' sheet (password stored only as a salted hash); every sign-in attempt is logged in 'Admin sign-in log'.
- Approved admins can view, search, export and REQUEST edits. The central admin approves or declines each request.
- One-time: add engine-requests.gs to the engine Apps Script, follow the lines at the top (in doPost, before the passcode check), deploy a new version.
- Requests > Admins has the invite link to send people, plus pause / new password / remove for each account.
- The central admin still uses the passcode in Settings. Practice mode: tap the 'Central admin' chip, or Settings > Preview the admin sign-in page (demo login admin@lbd.test / demo1234).

NOTES
- HTTPS is required for install + offline. Opening index.html straight from a file still works as a normal page.
- Settings and passcodes are stored on each device. Use Settings > Export / Import to move them.
- Releasing an update: replace the files and change VERSION in sw.js (for example lbd-v2).
- PDF exports are unchanged (they use the browser's Print / Save as PDF).
