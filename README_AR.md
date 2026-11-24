# خياطتي — الدفعة 1 (المراحل 1–2)

## التشغيل لأول مرة
```bash
cd khayyati
flutter create --org com.khayyati --project-name khayyati --platforms android .
rm -f test/widget_test.dart          # ملف اختبار تلقائي لا يناسب المشروع
flutter pub get
dart run build_runner build --delete-conflicting-outputs
flutter test
flutter run
```
> إن ظهر تعارض إصدارات في `pub get` فاترك `flutter pub upgrade --major-versions` يحدّد الإصدارات المتوافقة مع Flutter عندك.

## خط Cairo (يعمل بدون إنترنت)
ضع `Cairo-Regular.ttf` و`Cairo-Bold.ttf` في `assets/fonts/` ثم أزل التعليق عن قسم `fonts` في `pubspec.yaml`.

## ما تم في هذه الدفعة
- هيكل المشروع (Riverpod + GoRouter + Drift + Material 3 + RTL عربي + وضع ليلي).
- قاعدة بيانات SQLite بالـ18 جدولاً المطلوبة مع العلاقات والمفاتيح الأجنبية، واستراتيجية ترحيل جاهزة، وإنشاء المحلين تلقائياً.
- إعداد المدير عند أول تشغيل، تسجيل الدخول، تجزئة كلمات المرور PBKDF2-SHA256 مع Salt.
- إدارة العاملين (إضافة/تفعيل/تعطيل + صلاحيات أساسية)، تعديل بيانات المحل، تغيير كلمة المرور، المظهر.
- سجل عمليات (Audit Log) يعمل لعمليات الدخول والمستخدمين والمحل.
- اختبارات: التجزئة، المصادقة، المفاتيح الأجنبية.

## المتبقي
الزبائن والمقاسات والطلبات ← الدفعات والديون والمصروفات والمخزون ← الفواتير والتنبيهات والتقارير والنسخ الاحتياطي ← APK.
