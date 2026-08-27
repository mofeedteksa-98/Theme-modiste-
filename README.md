# Modiste — ثيم سلة (Twilight)

تأسيس أولي لثيم Modiste (ملابس/أزياء) مبني على بنية Twilight الرسمية من توثيق شركاء سلة.

## اللي جاهز الآن
- `twilight.json` مع تعريف 4 مكونات رئيسية للصفحة الرئيسية
- `src/views/layouts/master.twig` مع كل الـ Template Hooks الرسمية (head:start/head/head:end, body:classes/body:start/body:end)
- Header + Footer
- الصفحة الرئيسية كاملة: Hero، تصنيفات، منتجات مختارة، اقتباس تحريري + شريط مزايا
- بطاقة منتج قابلة لإعادة الاستخدام
- CSS كامل بهوية Modiste (ivory / walnut / clay)
- ملفات ترجمة عربي/إنجليزي أساسية

## ⚠️ قبل ما ترفعينه — تحقق من هالنقاط محليًا
هذي أشياء بنيتها على أنماط شائعة وموثّقة جزئيًا، لكن الأسماء الدقيقة للمتغيرات تحتاج تأكيد من `theme-raed` (الثيم المصدري الرسمي) بعد ما تشغّلين `salla theme dev`:
1. **أسماء متغيرات المنتج** (`product.name`, `product.price`, `product.colors`...) في `product/card.twig`
2. **مسار الـ include** لبطاقة المنتج (`components/product/card.twig`) — لو ظهر خطأ "template not found" جربي المسار بدون `components/`
3. **متغيّر `categories`** في `home/categories.twig` — تأكدي من الاسم الفعلي المتوفر على الصفحة الرئيسية
4. **صيغة `{% component 'namespace.name' %}`** — مبنية على مبدأ "Component Hooks" الموثّق (`component:{path}.start/end`)، لكن تأكدي من الصيغة بالضبط أول تشغيل

## الخطوات التالية
1. سجّلي دخول بوابة الشركاء ← My Themes ← Create your first theme
2. اربطي حساب GitHub وارفعي هذا المجلد كـ repo جديد (أو استوردي عبر `twilight.json`)
3. ثبّتي Salla CLI شغّلي `salla theme dev` على متجر تجريبي لمعاينة حية وتصليح أي أخطاء أسماء متغيرات
4. أكملي الصفحات الناقصة: صفحة المنتج، قائمة المنتجات، السلة، صفحات العميل، المدونة — نبنيها تباعًا
5. جهّزي 4 لقطات شاشة (عربي + إنجليزي) ومتجر تجريبي بمحتوى حقيقي قبل الإرسال للمراجعة
6. السعر المقترح: 490 ريال (فوق الحد الأدنى الرسمي 250 ريال للثيمات العامة)

## البنية
```
twilight.json
src/
 ├─ assets/styles/style.css
 ├─ locales/ (ar.json, en.json)
 └─ views/
     ├─ layouts/master.twig
     ├─ components/
     │   ├─ header/header.twig
     │   ├─ footer/footer.twig
     │   ├─ home/ (hero, categories, products, editorial)
     │   └─ product/card.twig
     └─ pages/index.twig
```
