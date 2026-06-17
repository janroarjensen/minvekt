# Min Vektreise Cloud – GitHub/Firebase-pakke

Dette er en ferdig startpakke for GitHub + Firebase Hosting + Firebase Authentication + Firestore.

## Filer
- `index.html` – appen
- `styles.css` – design
- `app.js` – logikk (Firebase Auth + Firestore + UI)
- `firebase-config.js` – legg inn dine Firebase-nøkler
- `firebase-config.example.js` – eksempelmal
- `firebase.json` – oppsett for Firebase Hosting
- `firestore.rules` – sikkerhetsregler per bruker
- `.github/workflows/firebase-hosting.yml` – GitHub Action for deploy til Firebase Hosting

## Datamodell
Data lagres per bruker i Firestore her:

/users/{uid}/app/main

## Oppsett
1. Opprett Firebase-prosjekt
2. Registrer en Web App og lim inn verdier i `firebase-config.js`
3. Aktiver Authentication -> Email/Password
4. Opprett Firestore og deploy reglene
5. Legg filene i GitHub-repo
6. Deploy med Firebase CLI **eller** GitHub Actions

## Firebase CLI
```bash
npm install -g firebase-tools
firebase login
firebase init hosting
firebase deploy
```

## GitHub Action
Legg inn repository secret:
- `FIREBASE_SERVICE_ACCOUNT`

Og bytt `YOUR_FIREBASE_PROJECT_ID` i workflow-filen.

## Tips
- Hvis du vil teste layout uten Firebase, kan appen kjøres i demo-modus lokalt.
- For GitHub Pages må du fortsatt sette opp Firebase Authentication/Firestore i Firebase Console.
