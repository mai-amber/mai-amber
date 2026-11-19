# Voice clone · team board

Small two-stage site. First, one-time recurring availability poll. Once active participants submit and a 60-minute biweekly time is chosen, the poll disappears and the one-task-per-person board opens.

## Publish on GitHub Pages

1. Put `index.html`, `firebase-config.js` and `database.rules.json` together in a folder on a Pages-enabled repository.
2. In Firebase Console, create a project, create a web app and a **Realtime Database**, and enable **Authentication → Sign-in method → Anonymous**.
3. Paste the web app's `firebaseConfig` values (including `databaseURL`) into `firebase-config.js`.
4. Under Realtime Database → Rules, paste `database.rules.json` and publish the rules.
5. Enable **Settings → Pages** for the GitHub repository, with the branch containing these files. Open the published URL. Use **Copy invite link** to share the same private room.

Without Firebase configuration, the app works as a local-only preview. Local changes persist only in that browser and are **not shared**. A team-synced deployment requires Firebase; GitHub Pages alone cannot store shared updates.

## Team

Core roster: Amber, Rom, Basel, Reut, Doron. Roy and Omer are shown as invited, and can choose their name and join. The poll waits for the active roster only. The first milestone is a working shared demo; the four checklist items are manually checked. Task effort is suggested from keywords (1-5 workdays) and can be overridden, as can the due date. No user accounts are needed for the simple name selector.

## Privacy

The shared room identifier is random and sits in the URL fragment. Anyone with that link can edit project status. Do not store participant audio, private credentials or sensitive study data here. Anonymous Firebase authentication and an unguessable room URL are not equivalent to individual access controls. Restrict rules and add member authentication before storing confidential information.

## Run locally

```bash
python3 -m http.server 8000
```

Open `http://localhost:8000` in a browser. The site uses ES modules and must be served over HTTP(S), not opened as a `file://` URL.