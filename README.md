# סוכות בצפון

רשימה משותפת וחיה לסופ״ש סוכות של חמש משפחות בוילה בצפון — תכנון ארוחות,
רשימת קניות נגזרת, ציוד ורשימות אישיות לכל משפחה.

**האתר:** https://shovalbatel.github.io/sukkot-tzafon/

## איך זה עובד

- `index.html` — כל האפליקציה (HTML, CSS, JS). בלי תלויות מלבד Firebase והפונטים.
- `seed.js` — הרשימה ההתחלתית (148 פריטים). נטענת אוטומטית בפעם הראשונה שהאתר נפתח.
- `config.js` — פרטי החיבור למסד הנתונים המשותף.

בלי חיבור למסד, האתר עובד ושומר במכשיר של הגולש בלבד (localStorage).
עם חיבור, כל מי שפותח את הקישור רואה ומעדכן את אותה רשימה בזמן אמת — בלי שום חשבון.

## חיבור המסד המשותף

1. https://console.firebase.google.com → **Add project** (בלי Analytics).
2. בתפריט: **Build → Realtime Database → Create Database** → אזור אירופה → **Start in test mode**.
3. **Rules** → להחליף ב:
   ```json
   { "rules": { ".read": true, ".write": true } }
   ```
4. **Project settings → General → Your apps → Web (`</>`)** → להעתיק את אובייקט `firebaseConfig`
   ולהדביק אותו ב-`config.js` במקום ערכי ה-`PASTE_`.
5. `git commit && git push` — GitHub Pages מתעדכן תוך דקה.

הרשימה פתוחה לכתיבה לכל מי שיש לו את הקישור. זו רשימת קניות משפחתית — אין בה מידע רגיש.
