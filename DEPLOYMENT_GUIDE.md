# دليل النشر على Netlify

## خطوات النشر على app.netlify.com

### 1. إعداد المشروع للنشر

المشروع جاهز الآن للنشر على Netlify. تم إجراء التعديلات التالية:

- ✅ تم إنشاء ملف `netlify.toml` مع إعدادات البناء والتوجيه
- ✅ تم إنشاء Netlify Functions للتعامل مع API
- ✅ تم تحديث HTML مع SEO tags مناسبة
- ✅ تم إزالة Replit-specific scripts
- ✅ تم إنشاء ملف `.env.example` للمتغيرات البيئية

### 2. خطوات النشر

1. **رفع الكود إلى GitHub (إختياري)**
   - أنشئ repository جديد على GitHub
   - ارفع كامل الكود إلى GitHub

2. **النشر على Netlify**
   - اذهب إلى [app.netlify.com](https://app.netlify.com)
   - اضغط على "New site from Git" أو "Add new site"
   - اختر GitHub repository (إذا استخدمت Git)
   - أو اسحب وأفلت مجلد المشروع مباشرة

3. **إعدادات Build**
   - Build command: `npm run build`
   - Publish directory: `dist/public`
   - سيتم تطبيق هذه الإعدادات تلقائياً من ملف `netlify.toml`

### 3. متغيرات البيئة (Environment Variables)

في لوحة تحكم Netlify:
1. اذهب إلى Site settings > Environment variables
2. أضف المتغيرات التالية (إختيارية):
   - `DISCORD_BOT_TOKEN`: لعرض صورة Discord الحقيقية
   - `DISCORD_AVATAR_HASH`: إذا كنت تعرف hash الصورة
   - `DATABASE_URL`: إذا كنت تستخدم قاعدة بيانات

### 4. اختبار الموقع

بعد النشر:
- سيكون موقعك متاح على رابط مثل: `https://your-site-name.netlify.app`
- API endpoints ستعمل على: `https://your-site-name.netlify.app/api/discord-avatar`

### 5. ملاحظات مهمة

- **Netlify Functions**: تم تحويل Express server إلى Netlify Functions
- **Static Site**: الموقع سيعمل كموقع ثابت مع API functions
- **Redirects**: تم إعداد redirects للتعامل مع SPA routing
- **Build Process**: سيتم بناء React app تلقائياً

### 6. استكشاف الأخطاء

إذا واجهت مشاكل:
1. تحقق من Build logs في Netlify dashboard
2. تأكد من أن `npm run build` يعمل محلياً
3. تحقق من Function logs في Netlify
4. تأكد من إعداد Environment variables بشكل صحيح

### 7. تحديثات مستقبلية

- لتحديث الموقع، قم بإعادة رفع الكود أو push إلى GitHub
- Netlify ستعيد بناء الموقع تلقائياً

## بديل: النشر المباشر

بدلاً من GitHub، يمكنك:
1. تشغيل `npm run build` محلياً
2. سحب وإفلات مجلد `dist/public` مباشرة إلى Netlify
3. سحب وإفلات مجلد `netlify/functions` للـ API functions

الموقع جاهز الآن للنشر! 🚀