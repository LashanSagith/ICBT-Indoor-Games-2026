# ICBT Staff Indoor Games 2026 — Event Manager

A single-page event management system for the ICBT Staff Indoor Games 2026.
It uses Firebase Firestore so brackets and scores can be shared across devices.

## Included

- `index.html` — complete web application
- `firestore.rules` — Firestore security rules
- `.github/workflows/pages.yml` — automatic GitHub Pages deployment
- `.nojekyll` — GitHub Pages compatibility
- `.gitignore` — basic repository cleanup

## Deploy to GitHub Pages

### 1. Create a GitHub repository

Create a new repository, for example:

`icbt-indoor-games-2026`

Then upload all files and folders from this package.

### 2. Push the files

If using Git locally:

```bash
git init
git add .
git commit -m "Initial ICBT Indoor Games 2026 release"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
git push -u origin main
```

### 3. Enable GitHub Pages

Open the repository:

**Settings → Pages → Build and deployment**

Select **GitHub Actions** as the source.

The included workflow will deploy the site automatically whenever you push to `main`.

Your site will normally be available at:

`https://YOUR_USERNAME.github.io/YOUR_REPOSITORY/`

## Firebase

The application already contains a Firebase web configuration in `index.html`.

Before using the application with real data, make sure the Firebase project exists and that Firestore is enabled.

Open Firebase Console and apply the rules from:

`firestore.rules`

The application stores game data under:

`draws/{gameId}`

## Access code

The current application access code is:

`ICBT2026`

To change it, edit the `ACCESS_CODE` constant inside `index.html`.

## Important security note

The current login screen is an application-level access-code gate, not Firebase Authentication. The Firestore rules intentionally allow reads/writes to the `draws` collection because the app does not use Firebase Auth.

Therefore, do not treat the access code as strong authentication. If this system will contain sensitive information, Firebase Authentication and user-based Firestore rules should be added.

## Local testing

Because Firebase is used, it is better to test through a local web server rather than opening `index.html` directly with `file://`.

For example, with Python installed:

```bash
python -m http.server 8000
```

Then open:

`http://localhost:8000`

## Current games

The application includes the configured Indoor Games draw/score screens for:

- Pool
- Caram
- Omi
- Table Tennis
- Chess
- Dart
- and the other games configured inside `index.html`

© 2026 ICBT. All Rights Reserved.
