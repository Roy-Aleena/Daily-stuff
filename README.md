# Daily stuff – your offline app with sync

Works with no internet. When you're online, it syncs between your phone and laptop by itself
through your own free Firebase project. No Claude needed.

## 1. Create the Firebase project (5 min, free)
1. Go to **console.firebase.google.com** and sign in with Google → **Create a project** → name it `daily-stuff` → you can turn Google Analytics off → Create.
2. Click the **</>** (Web) icon → app nickname `daily-stuff` → **Register app** (skip Firebase Hosting).
   Firebase shows a `firebaseConfig = { … }` block. Keep that page open.

## 2. Turn on sign-in
**Security → Authentication → Get started → Sign-in method** → turn on **Google** (and Email/Password if you want a backup).
Then **Authentication → Settings → Authorized domains → Add domain** → `<your-username>.github.io`.

## 3. Create the database
1. **Build → Firestore Database → Create database** → pick a location near you (e.g. `us-east1`) → **Start in production mode** → Create.
2. Open the **Rules** tab, replace everything with the contents of `firestore.rules` from this folder, and click **Publish**.
   (This makes sure only you, signed in, can read or write your data.)

## 4. Paste your config
Open `firebase-config.js` and replace the placeholder values with the ones from step 1.2
(apiKey, authDomain, projectId, storageBucket, messagingSenderId, appId). Save.

## 5. Put it online (GitHub Pages, free)
1. github.com → **New repository** → e.g. `daily-stuff` → Public → Create.
2. **uploading an existing file** → drag in **everything in this folder** → Commit.
3. **Settings → Pages** → Branch `main`, `/ (root)` → Save. About a minute later it's live at
   `https://<username>.github.io/daily-stuff/`.

## 6. Install + sign in on each device
- **iPhone:** Safari → open the link → Share → **Add to Home Screen**.
- **Android:** Chrome → ⋮ → **Install app**.
- **Laptop:** Chrome/Edge → install icon in the address bar.
- Open the app → **Dashboard → Sync** → **Create account** (first device) or **Sign in** (other devices) with the same email and password.

## 7. Bring over your current data
1. In your Claude version: **Dashboard → Download backup**.
2. In the new app (signed in): **Dashboard → Restore from file**. It uploads to sync, and your other devices pull it in.

## How sync works
- Every change saves on the device instantly, online or not.
- When you're online, changes upload within a second and your other devices update live.
- Offline edits upload automatically once you reconnect. The Sync card shows ✅ Synced, ⏳ Syncing… or 📴 Offline.
- If you edit the same day on two devices while both are offline, the last one to reconnect wins for that day.
- Firebase's free plan is far more than one person needs.

## Optional: lock it to just you
After creating your account: **Authentication → Settings → User actions →** turn off **Enable create (sign-up)**,
if your console shows that option. Nobody else can make an account on your app then.

## Updating the app later
Change `index.html`, bump `VERSION` in `sw.js` (v1 → v2), and upload both to the same repo.
Your devices pick it up the next time you open the app.
