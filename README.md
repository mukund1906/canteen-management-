# Canteen Connect

College canteen ke liye online food ordering website. Students class se order karte hain, owner ko live orders milte hain.

- Student login / register, menu (90+ items, student budget rates), cart, COD aur UPI payment
- Owner login, live orders, menu stock, photo upload, canteen khula/band, UPI ID
- Sirf HTML, CSS aur JavaScript. Koi server install nahi karna.

## Files

| File | Kaam |
| --- | --- |
| `index.html` | Poori website |
| `firebase-config.js` | Firebase ki settings (live orders ke liye) |
| `firestore.rules` | Firebase database ke rules |

## Part 1: GitHub Pages par site live karna

1. github.com par login karein, upar **+** dabayein, phir **New repository**.
2. Repository name likhein (jaise `canteen-connect`), **Public** chunein, **Create repository** dabayein.
3. **uploading an existing file** link dabayein, aur `index.html`, `firebase-config.js`, `firestore.rules`, `README.md` ko drag karke daal dein. Neeche **Commit changes** dabayein.
4. **Settings** > **Pages** kholein. **Source** mein **Deploy from a branch**, branch `main`, folder `/ (root)` chunein, **Save** dabayein.
5. 1-2 minute baad aapki site is link par chalegi:
   `https://AAPKA-USERNAME.github.io/canteen-connect/`

Is point par site "Demo mode" mein hai. Orders sirf usi phone ya browser mein save hote hain jisse order kiya. Sabke liye live karne ke liye Part 2 karein.

## Part 2: Firebase se orders sab devices par live karna

1. console.firebase.google.com par Google account se login karein. **Create a project** dabayein, naam likhein, Google Analytics band kar dein.
2. Left menu mein **Build** > **Firestore Database** > **Create database**. Location `asia-south1 (Mumbai)` chunein, **Production mode** mein start karein.
3. Firestore ke **Rules** tab mein jayein. Wahan ka sab kuch hata kar `firestore.rules` file ka poora text paste karein, phir **Publish** dabayein.
4. Upar **Project settings** (gear icon) > **Your apps** > **Web** (`</>`) dabayein. App ka naam likhein, **Register app** dabayein. Jo `firebaseConfig` dikhe, uski values copy karein.
5. GitHub repo mein `firebase-config.js` kholein, pencil icon dabayein, apni values bharein, aur **Commit changes** dabayein.
6. 1-2 minute baad site refresh karein. Upar ka "Demo mode" wala peela bar gayab ho jayega. Ab orders sab devices par live dikhenge.
7. **Turant** owner link kholein: apni site ke link ke aage `#owner` lagayein, jaise `https://AAPKA-USERNAME.github.io/canteen-connect/#owner`. Wahan owner ID aur password se owner account bana lein. Pehli baar jo bana leta hai wahi owner hota hai.

Owner ka tab students ko nahi dikhta. Owner hamesha isi `#owner` wale link se login karta hai (is link ko bookmark kar lein), aur login ke baad usse Owner tab dikhne lagta hai.

## Owner ke kaam

- **Orders:** naye order aate hi beep bajta hai. "Banana shuru karein", "Ready hai", "Mil gaya" dabate jayein. Payment aane par "Payment mila" dabayein.
- **Menu stock:** koi item khatam ho to "Available" ko "Khatam" kar dein. "Photo" se asli photo lagayein.
- **Settings:** canteen khula/band karein aur apni asli UPI ID daalein. Default `canteen@upi` sirf demo hai.

## Zaroori baatein

- **Security:** Ye college project ke level ki security hai. Database ke rules sab ko read/write dete hain, aur site ka code dekhne wala Firebase config nikal sakta hai. Asli canteen mein chalane ke liye Firebase Authentication aur strict rules lagane honge.
- **Owner password badalna:** Database rules account ko banne ke baad badalne nahi dete. Password badalna ho to Firebase console mein Firestore > `accounts` > `owner` document delete karein, aur site par naya owner account bana lein.
- **Online payment:** Asli payment gateway nahi hai. Student UPI se paisa bhejke UTR number daalta hai, aur owner use check karke "Payment mila" dabata hai.
- **Photos:** Photo apne aap chhoti ho kar database mein save hoti hai. 90 items ki photos lagane par bhi site tez rahegi.
- **Free limit:** Firebase ka free plan ek chhoti canteen ke liye kaafi hai.
