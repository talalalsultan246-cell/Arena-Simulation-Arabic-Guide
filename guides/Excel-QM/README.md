<div dir="rtl" align="right">

# دليل Excel QM وQM for Windows
**كيفية التحميل والتثبيت وأهم استخدامات بحوث العمليات**

إعداد: **Talal Alsultan** | تحديث: أكتوبر 2026

هنا فرق مهم قبل البدء: **Excel QM** إضافة (Add-in) تعمل داخل Microsoft Excel، بينما **POM-QM / QM for Windows** برنامج مستقل له واجهة خاصة. كلاهما يستخدم في مسائل الأساليب الكمية وإدارة العمليات، لكن خطوات تثبيتهما ليست واحدة.

## 1. الرابط المعتمد

- [صفحة Pearson الرسمية لموارد Quantitative Analysis for Management، الطبعة 13](https://media.pearsoncmg.com/ph/bp/bridgepages/bp_render_bridgepage/qam_13e/index.html)
- [Pearson — صفحة الكتاب والبرامج المساندة](https://www.pearson.com/en-us/subject-catalog/p/quantitative-analysis-for-management/P200000006031)

تحققت من صفحة Pearson: تظهر ضمن **Software Downloads** حزمة **Excel OM/QM for PCs, Version 5.3**، وحزمة Mac للإصدار نفسه، و**POM/QM for Windows, Version 4**. قد تختلف الحزمة المطلوبة إذا حدد الدكتور إصدارًا آخر.

## 2. تثبيت Excel QM على Windows

1. تأكد من وجود **Microsoft Excel Desktop** على الجهاز، وليس Excel داخل المتصفح فقط.
2. افتح [صفحة Pearson](https://media.pearsoncmg.com/ph/bp/bridgepages/bp_render_bridgepage/qam_13e/index.html).
3. انزل إلى **Software Downloads** واضغط **Excel OM/QM for PCs, Version 5.3**.
4. نزّل ملف التثبيت `.msi` من Pearson، ثم شغّله وأكمل الخطوات.
5. افتح Excel بعد التثبيت. ابحث عن تبويب **Excel QM** أو **Add-ins** وفق الإصدار وطريقة التشغيل.
6. إذا طلب Excel السماح بالماكرو، تحقق من مصدر الملف أولًا ولا تفعّل كافة وحدات الماكرو لكل الملفات؛ اسمح فقط للملف الموثوق من Pearson.
7. جرّب مسألة من قائمة البرنامج للتأكد من ظهور نموذج إدخال البيانات وورقة النتائج.

### إذا لم يظهر Excel QM

1. افتح **Excel → File → Options → Add-ins**.
2. أسفل النافذة اختر **Manage: Excel Add-ins → Go**.
3. إذا كانت الإضافة موجودة ضع علامة أمامها. أو اختر **Browse** وافتح ملف الإضافة `.xlam` أو `.xla` من موقع تثبيتها.
4. أغلق Excel بالكامل وافتحه مرة أخرى.
5. إذا ظهرت رسالة عن حظر الماكرو، راجع سياسة المؤسسة أو الجامعة؛ لا تُلغِ إعدادات الحماية العامة لمجرد تشغيل الإضافة.

## 3. تثبيت QM for Windows

1. من [صفحة Pearson نفسها](https://media.pearsoncmg.com/ph/bp/bridgepages/bp_render_bridgepage/qam_13e/index.html)، اختر **POM/QM for Windows, Version 4** إذا كان هذا ما يتطلبه المقرر.
2. نزّل الأرشيف الرسمي ثم استخرج الملفات (Extract All).
3. افتح مثبت البرنامج الموجود داخل الحزمة واتبع خطوات الإعداد.
4. شغّل البرنامج من قائمة Start، واختر نوع المسألة من القوائم المتاحة.
5. حدّد عدد المتغيرات أو الفترات وفق السؤال، وأدخل البيانات ثم اطلب الحل من البرنامج.
6. راجع الناتج رقميًا؛ اختيار النموذج الخاطئ يؤدي إلى نتيجة غير مرتبطة بالسؤال حتى إن اكتمل الحساب.

## 4. ما الذي يمكن حله؟

| الموضوع | مثال استخدام |
| :---: | :---: |
| Linear Programming | تعظيم الربح ضمن قيود الموارد |
| Forecasting | مقارنة المتوسط المتحرك والتنعيم الأسي |
| Inventory | تحليل كميات الطلب وتكاليف المخزون |
| Transportation | تقليل تكلفة توزيع الشحنات |
| Assignment | توزيع مهام على موارد |
| Waiting Lines | نماذج الطوابير الأساسية |

**تنبيه:** توفر كل وحدة ونطاقها يتحدد وفق البرنامج والإصدار الذي ثبته المستخدم؛ ليست كل الوحدات متطابقة بين Excel QM وQM for Windows.

## 5. تجربة بسيطة — Moving Average

إذا كانت البيانات للفترات الثلاث الأخيرة `100, 110, 120`، فإن توقع الفترة التالية باستخدام متوسط متحرك لثلاث فترات:

```text
Forecast = (100 + 110 + 120) / 3
Forecast = 110
```

في Excel تكتب:

```excel
=AVERAGE(B2:B4)
```

**الناتج المتوقع:**

```text
110
```

بهذه الطريقة تستطيع التأكد من إجابة البرنامج بمقارنة النتيجة مع الحساب اليدوي.

## 6. حلول المشكلات الشائعة

| المشكلة | ما الذي أفحصه؟ |
| :---: | :---: |
| لا يظهر تبويب Excel QM | إدارة الإضافات والماكرو ثم إعادة تشغيل Excel |
| يظهر خطأ Macro disabled | مصدر الملف وإعدادات Trust Center وسياسات الجهاز |
| لا يعمل المثبت على جهاز حديث | نسخة البرنامج ومتطلبات النظام وتوافق Microsoft Office |
| تظهر نتائج مختلفة | عدد الفترات أو المتغيرات وطريقة الإدخال والإعدادات |
| البرنامج يطلب ترخيصًا | استخدم رخصة Pearson أو الرخصة المرفقة بالمقرر |
| الروابط القديمة لا تعمل | ارجع لصفحة Pearson الحالية أو ملفات المقرر |

## 7. المصدر

- [Pearson — Excel OM/QM 5.3 وPOM/QM 4](https://media.pearsoncmg.com/ph/bp/bridgepages/bp_render_bridgepage/qam_13e/index.html)
- [Pearson — Quantitative Analysis for Management](https://www.pearson.com/en-us/subject-catalog/p/quantitative-analysis-for-management/P200000006031)

لا أضع روابط تنزيل من مواقع نسخ البرامج غير الموثوقة. عندما تتوفر صور من برنامجك الفعلي يمكن وضعها في هذا المجلد وتحديد أماكن الضغط بالمربعات الحمراء، بنفس أسلوب دليل Arena.

</div>