# Paradise Park Wizard – APK & portable EXE

Δομή:

- `mobile/www/index.html` → η mobile έκδοση (γίνεται Android APK με Capacitor)
- `desktop/index.html` → η desktop έκδοση (γίνεται portable EXE για Windows 10/11 με Electron)
- `.github/workflows/android.yml` και `windows.yml` → αυτόματο build στο GitHub

## Βήματα

1. Φτιάξτε νέο repository στο GitHub και ανεβάστε **όλο** αυτό το περιεχόμενο (συμπεριλαμβανομένου του φακέλου `.github`) στο branch `main`.
2. Πηγαίνετε στην καρτέλα **Actions**. Τα δύο workflows τρέχουν αυτόματα σε κάθε push (ή χειροκίνητα με «Run workflow»).
3. Όταν τελειώσουν (3–8 λεπτά), ανοίξτε το run και κατεβάστε από το **Artifacts**:
   - `Paradise-Park-Wizard-apk` → `app-debug.apk`
   - `Paradise-Park-Wizard-portable-exe` → `Paradise-Park-Wizard-portable.exe`

## Σημειώσεις

- Το APK είναι *debug-signed*: εγκαθίσταται κανονικά σε Android (επιτρέψτε «εγκατάσταση από άγνωστες πηγές»). Για Google Play χρειάζεται release build με δικό σας keystore.
- Το EXE είναι portable: δεν χρειάζεται εγκατάσταση, τρέχει με διπλό κλικ. Τα δεδομένα αποθηκεύονται τοπικά στο προφίλ του χρήστη των Windows. Το Windows SmartScreen μπορεί να δείξει προειδοποίηση επειδή το αρχείο δεν είναι υπογεγραμμένο («Περισσότερες πληροφορίες → Εκτέλεση ούτως ή άλλως»).
- Στο Android WebView η «Αποθήκευση αρχείου», το Excel και το κατέβασμα αρχείων μέσω συνδέσμου μπορεί να μην λειτουργούν. Η αποθήκευση γίνεται κανονικά στον ίδιο χώρο της εφαρμογής (αποθηκευμένα προγράμματα) και η αποστολή σε Viber/αντιγραφή δουλεύει.
- Για να ενημερώσετε την εφαρμογή, αντικαταστήστε τα `index.html` και κάντε push.
