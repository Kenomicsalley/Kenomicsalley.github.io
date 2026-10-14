FASTEST FINGER - APP FILES (phone-friendly guide)
=================================================

WHAT IS IN THIS FOLDER
  index.html .............. the game (same game, plus app settings)
  manifest.webmanifest .... tells Android the app's name, icon and colours
  sw.js ................... lets the game work offline
  icon-192.png, icon-512.png, icon-maskable-512.png, favicon.png ... app icons made from your logo
  privacy.html ............ simple privacy policy (needed later for Google Play)
  assetlinks.template.json  example of the file you will add in Step 7

You do NOT need Railway. GitHub alone is enough (free hosting with HTTPS).

PART 1 - PUT THE GAME ONLINE WITH GITHUB PAGES
 1. Open github.com in your phone browser and sign in. If buttons look tiny, open the browser menu
    and tick "Desktop site".
 2. Create a new PUBLIC repository named exactly:   YOURUSERNAME.github.io
    (use your real GitHub username; no spaces; all lower case)
 3. In the repository tap "Add file" > "Upload files". Select ALL the files from this folder
    (index.html, manifest.webmanifest, sw.js, privacy.html and the 4 png files). Tap "Commit changes".
 4. Tap "Add file" > "Create new file". Name it   .nojekyll   (with the dot at the start).
    Type one blank space as the content, then commit. (This makes the .well-known folder work later.)
 5. Go to Settings > Pages. Under "Build and deployment" choose "Deploy from a branch",
    branch "main", folder "/ (root)". Save.
 6. Wait 1 to 3 minutes. Open  https://YOURUSERNAME.github.io  on your phone. The game should load.
    Test it: open the game once, turn on airplane mode, reload. It should still work.

PART 2 - MAKE THE APK WITH PWABUILDER
 7. Open  pwabuilder.com  (use "Desktop site" if needed). Paste  https://YOURUSERNAME.github.io  and tap Start.
 8. When the report shows, choose "Package for stores", then Android.
    Settings to use:
      Package ID ........ com.kenomicsalley.fastestfinger
      App name .......... Fastest Finger
      Launcher name ..... Fastest Finger
      App version ....... 1.0.0   (version code 1)
      Signing key ....... Create new
    Then tap Generate / Download. You receive a ZIP file.
 9. IMPORTANT: keep that ZIP safe (email it to yourself and save it to Google Drive).
    It contains your signing key and its password. You need the SAME key for every future update.
    If you lose it you cannot update the app.
10. Unzip it with your phone's file manager. Inside you should find a signed APK and an AAB file
    (the AAB is the one Google Play wants later), plus a file called assetlinks.json
    and signing-key-info.txt.

PART 3 - REMOVE THE ADDRESS BAR (so it looks like a real app)
11. Open assetlinks.json from the ZIP and copy ALL its text.
12. In your GitHub repository tap "Add file" > "Create new file". In the name box type exactly:
        .well-known/assetlinks.json
    (typing the slash creates the folder). Paste the text. Commit.
13. Check it opens at  https://YOURUSERNAME.github.io/.well-known/assetlinks.json

PART 4 - INSTALL AND TEST THE APK
14. Tap the .apk file. If Android asks, allow "Install unknown apps" for your file manager or browser.
15. Open Fastest Finger from your home screen. No address bar means everything is set up correctly.
    If you still see a bar, wait a few minutes, then close and reopen the app (Android checks the link
    file when the app starts).
16. You can send the same APK to other people on WhatsApp or Google Drive.

UPDATING THE GAME LATER
 - Upload the new index.html to GitHub (Add file > Upload files, same name replaces it).
 - In sw.js change  fastest-finger-v1  to  fastest-finger-v2  (and v3 next time) so phones fetch the update.
 - You do NOT need a new APK for game changes, because the app shows your website.

LATER, FOR GOOGLE PLAY (optional)
 - Upload the .aab file, not the APK.
 - Privacy policy address to give Google:  https://YOURUSERNAME.github.io/privacy.html
 - After the first upload, Play Console > Setup > App integrity > App signing shows a second fingerprint.
   Add it to assetlinks.json (see assetlinks.template.json) so the address bar stays hidden.
 - New personal developer accounts must run a closed test with at least 12 testers for 14 days before
   production. A company/organization account is exempt.
 - Please read the privacy.html text and change anything that is not true for your app. It is a basic
   draft and not legal advice.
