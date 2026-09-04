# NexCode V11 — Files Only Upload Pack

هذه حزمة مخصصة للرفع من الهاتف: الملفات التي سترفعها إلى GitHub كلها ملفات في الجذر، ولا تحتاج لاختيار مجلدات من مدير الملفات. GitHub نفسه يدعم المجلدات، لكن هذه الطريقة أسهل على الهاتف.

## طريقة الاستخدام
1. أنشئ مستودع GitHub فارغ.
2. فك هذا الملف على الهاتف.
3. ارفع الملفات الموجودة داخله إلى المستودع.
4. في GitHub اختر **Add file → Create new file**، واكتب المسار `.github/workflows/android.yml`.
5. افتح `ANDROID_BUILD_WORKFLOW.yml` وانسخ محتواه إلى ملف الـ workflow ثم احفظه.
6. أضف Secret باسم `NEXCODE_API_URL` وضع فيه رابط Backend العام.
7. من **Actions → Android Build → Run workflow** شغّل البناء.

الـ workflow يفك حزم backend/app/docs/evaluation/store قبل البناء. بعد ذلك ينشئ مجلد Android ويشغل `flutter build apk` و`flutter build appbundle`. Flutter توثق بناء APK وAAB بهذه الأوامر.
