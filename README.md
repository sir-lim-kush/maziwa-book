# Maziwa Book

Milk, maziwa lala and egg tray tracker with a wallet, profit, history and Excel reports.
Sign in with email and password. Data is kept online in Firebase so two phones stay in sync.

## Firestore rules (Firebase console > Firestore Database > Rules)

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if request.auth != null
        && request.auth.token.email in ['EMAIL_ONE@gmail.com', 'EMAIL_TWO@gmail.com'];
    }
  }
}
```

Also turn off sign-ups: Authentication > Settings > User actions > untick "Enable create (sign-up)".
