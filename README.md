# 🦷 Dental Clinic OS

نظام إدارة عيادة الأسنان — PWA كامل مرتبط بـ Google Sheets

## الملفات

```
dental-clinic/
├── index.html      ← التطبيق الكامل
├── manifest.json   ← PWA manifest
├── sw.js           ← Service Worker (offline support)
└── dental_Code.gs  ← Google Apps Script (Backend)
```

## خطوات الإعداد

### 1. Google Apps Script

1. افتح الـ Google Sheet
2. **Extensions → Apps Script**
3. احذف كل شيء والصق محتوى `dental_Code.gs`
4. شغّل `SETUP_BuildSheets()` مرة واحدة
5. **Deploy → New Deployment**
   - Type: Web App
   - Execute as: **Me**
   - Who has access: **Anyone**
6. انسخ رابط الـ `/exec`

### 2. GitHub + Vercel

1. ارفع الملفات الثلاثة (`index.html`, `manifest.json`, `sw.js`) على GitHub
2. اربط الـ repo بـ [vercel.com](https://vercel.com)
3. Vercel ينشر تلقائياً على `dental-clinic.vercel.app`

### 3. ربط التطبيق بالشيت

1. افتح `dental-clinic.vercel.app`
2. اذهب لـ **المزيد ← الإعدادات**
3. الصق رابط Apps Script
4. اضغط **حفظ الرابط**

## الاستخدام

- **السكرتير**: يفتح الرابط من الجهاز بالعيادة — يدخل البيانات
- **الطبيب**: يفتح نفس الرابط من الأيفون — يشوف كل شيء لحظياً
- **بدون إنترنت**: التطبيق يشتغل offline ويزامن لما يرجع الاتصال

## الميزات

- ✅ إضافة مراجعين مع حساب تلقائي لحصة الطبيب
- ✅ بحث المرضى القدامى
- ✅ نسبة حصة الطبيب قابلة للتعديل (مو بالضرورة 50/50)
- ✅ مواعيد مع تذكير
- ✅ أرشيف كامل قابل للبحث
- ✅ جرد شهري تفصيلي
- ✅ تصدير CSV يُفتح بـ Excel
- ✅ يُثبَّت كتطبيق على الأيفون والأندرويد
