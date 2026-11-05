# Essencare

Aplikasi kesehatan harian (PWA): olahraga, diet, siklus haid, pup & pee. Login dan penyimpanan memakai Firebase (Authentication + Cloud Firestore). Dihosting di GitHub Pages.

## Setup Firebase
1. Authentication > Sign-in method > aktifkan **Email/Password**.
2. Firestore Database > Rules > ganti dengan:

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /users/{uid}/{document=**} {
      allow read, write: if request.auth != null && request.auth.uid == uid;
    }
  }
}
```

## Deploy
Upload semua isi folder ini ke repository GitHub, lalu aktifkan Settings > Pages (branch main, folder root).

## Revisi
Untuk update tampilan atau fitur, cukup timpa `index.html`.
