# موقع تطبيق كشفيتي (Scout Manager Website)

الموقع التعريفي الرسمي لتطبيق **كشفيتي** — تطبيق إدارة الأنشطة والفعاليات الكشفية، مع صفحة تحميل مباشرة لنسخة APK.

## محتويات الموقع

| الملف | الوصف |
|---|---|
| `index.html` | الصفحة الرئيسية (الميزات + طريقة العمل) |
| `about.html` | عن التطبيق (القصة، الميزات، الخصوصية، معلومات تقنية) |
| `developer.html` | عن المطور + التواصل والدعم |
| `download.html` | صفحة تحميل APK مع خطوات التثبيت |
| `assets/scouts_logo.png` | شعار الكشافة الإسلامية الجزائرية |
| `style.css` | التنسيق (بألوان وخط التطبيق نفسه) |

## النشر على GitHub Pages

1. أنشئ مستودعاً جديداً على GitHub (مثال: `scout-manager-website`).
2. ارفع كل ملفات هذا المجلد إلى المستودع:
   ```powershell
   cd scout-manager-website
   git init
   git add .
   git commit -m "موقع تطبيق كشفيتي"
   git branch -M main
   git remote add origin https://github.com/boulalouahhamza/scout-manager-website.git
   git push -u origin main
   ```
3. من إعدادات المستودع: **Settings → Pages → Source: Deploy from a branch → Branch: main / (root)**.
4. سيكون الموقع متاحاً على:
   `https://boulalouahhamza.github.io/scout-manager-website/`

## تجديد ملف APK

ملف الـ APK يُستضاف على **GitHub Releases** (وليس داخل المستودع، لأن حد GitHub للملفات 100 MB):

1. انسخ الملف الجديد وأطلق إصداراً جديداً:
   ```powershell
   gh release create v1.0.1 "C:\Users\Hamza\My Projects\Flutter Apps\scout_manager\build\app\outputs\flutter-apk\app-release.apk" --title "كشفيتي v1.0.1" --notes "وصف التحديث"
   ```
   (الأحدث دائماً يظهر عبر رابط `releases/latest/download/app-release.apk` الموجود في صفحة التحميل)
2. حدّث رقم الإصدار في: `index.html` و `about.html` و `download.html` (في الترويسة السفلية ولوحة التحميل).
3. ارفع التغييرات إلى المستودع (`git add . && git commit -m "تحديث الإصدار" && git push`).

## ملاحظات

- الموقع ثابت (HTML/CSS فقط) ولا يحتاج أي أدوات بناء.
- ملف الـ APK تتم استضافته على **GitHub Releases** (يستبدل رابطه في `download.html` تلقائياً مع كل إصدار جديد عبر رابط `latest`).
- الخط Cairo ولوحة الألوان (أخضر كشفي `#1B7A43` + ذهبي `#C9A227`) مطابقة لتطبيق Flutter نفسه.
- روابط الأنماط والصور **نسبية**، لذا يعمل الموقع من أي مسار فرعي على GitHub Pages دون تعديل.
