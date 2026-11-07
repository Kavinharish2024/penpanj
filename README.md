# Penpanj App

Sign in with Google, pick your player, see ratings, salary rankings and past matches.
`notetokavin@gmail.com` is the admin: create/edit/delete players, generate teams, log matches.
Everyone else is read-only. (Enforced by `firestore.rules`, not just the UI.)

## One-time setup (about 10 minutes, free)
1. Go to https://console.firebase.google.com and **Add project**.
2. **Build > Authentication > Get started > Sign-in method > Google > Enable.**
3. **Build > Firestore Database > Create database** (production mode, any region).
4. In Firestore open the **Rules** tab, paste the contents of `firestore.rules`, **Publish**.
5. **Project settings (gear) > Your apps > Web (</>)**, register an app, and copy the config into `firebase-config.js`.
6. Push these files to a GitHub repo, then **Settings > Pages > Deploy from branch (main, root)**.
7. Firebase **Authentication > Settings > Authorized domains > Add domain**: `YOUR-USERNAME.github.io`.

Open `https://YOUR-USERNAME.github.io/REPO-NAME/` and sign in as notetokavin@gmail.com.

## Moving your existing players
In the old claude.ai version: Dashboard > Backup / restore > copy the text.
In this app (as admin): Dashboard > Backup / restore > paste > Restore from box.

## Notes
- Friends just open the link and sign in with any Google account. They pick their player on first login.
- To test locally run `python3 -m http.server` in this folder (Google sign-in needs http, not file://); add `localhost` to authorized domains.
- Salaries and clubs update automatically when the admin logs a match with ratings out of 10.
