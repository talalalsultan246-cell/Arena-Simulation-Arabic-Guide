<div dir="rtl" align="right">

<h1><strong>دليل تثبيت واستخدام Power BI Desktop</strong></h1>

<p><strong>إعداد:</strong> Talal bin Ibrahim Alsultan &nbsp; | &nbsp; <strong>آخر تحديث:</strong> 26 أكتوبر 2026</p>

إذا كانت لديك بيانات في Excel أو CSV أو قاعدة بيانات، وتريد تحويلها إلى رسوم ومؤشرات تفاعلية، فابدأ ببرنامج **Power BI Desktop**. ستتعلم في هذا الدليل كيف تحمّله من Microsoft، وتثبّته، ثم تنشئ أول تقرير وتحفظه. وفي النهاية وضعت حلولًا للمشكلات التي قد تواجهك.

## 1. قبل أن تبدأ

Power BI Desktop برنامج مكتبي لتحليل البيانات وإعداد التقارير. تبدأ عادةً باستيراد البيانات، ثم تنظيفها في **Power Query**، وإنشاء العلاقات والحسابات عند الحاجة، وبعدها تصميم الرسوم البيانية والتفاعل معها.

**معلومة مهمة:** تنزيل Power BI Desktop واستخدامه محليًا مجاني، لكن نشر التقارير ومشاركتها عبر Power BI Service يخضعان للصلاحيات والتراخيص المناسبة. وإذا كان عملك على **Power BI Report Server** داخل جهة العمل، فهناك نسخة Desktop مخصصة له؛ ستجد شرحها في [دليل Power BI Report Server](../Power-BI-Report-Server/README.md).

## 2. تحميل البرنامج وتثبيته

<p align="center"><img src="https://cdn-dynmedia-1.microsoft.com/is/image/microsoftcorp/2.1-Product-Overview-800x471-PBD?fit=constrain&amp;hei=1188&amp;op_usm=1.5%2C0.65%2C15%2C0&amp;qlt=100&amp;resMode=sharp2&amp;wid=2000" alt="لقطة حقيقية من واجهة Power BI Desktop — المثال 1" width="92%"/></p>

*هذه لقطة شاشة لواجهة **Get Data** من [موقع Microsoft الرسمي](https://www.microsoft.com/en-us/power-platform/products/power-bi/desktop)، وتوضح اختيار مصدر البيانات.*

يمكنك تثبيت البرنامج بإحدى الطريقتين. اختر طريقة واحدة فقط:

### الطريقة الأولى: Microsoft Store

1. افتح [Power BI Desktop في Microsoft Store](https://aka.ms/pbidesktopstore).
2. اضغط **Get** أو **Install** بحسب ما يظهر لك.
3. بعد اكتمال التثبيت، ابحث عن **Power BI Desktop** في قائمة Start وافتحه.

هذه الطريقة مناسبة إذا كانت سياسة جهازك تسمح باستخدام Microsoft Store، وقد تساعدك في الحصول على تحديثات البرنامج من المتجر.

### الطريقة الثانية: ملف التثبيت من Microsoft

1. ادخل [صفحة التنزيل الرسمية](https://www.microsoft.com/en-us/download/details.aspx?id=58494).
2. اضغط **Download**، واختر الملف المناسب لنظام Windows ذي معمارية 64-bit.
3. شغّل الملف الذي نزلته، مثل `PBIDesktopSetup_x64.exe`، واتبع خطوات التثبيت.
4. افتح البرنامج من Start وتأكد من ظهور واجهة التقرير.

إذا كان لديك البرنامج أصلًا، فتحقق من نسخته قبل تثبيت إصدار جديد. إصدار 32-bit القديم من Power BI Desktop لم يعد مدعومًا.

## 3. إنشاء أول تقرير خطوة بخطوة

<p align="center"><img src="https://learn.microsoft.com/es-es/power-bi/fundamentals/media/desktop-getting-started/mergedcolumn.png" alt="لقطة حقيقية من واجهة Power BI Desktop — المثال 2" width="92%"/></p>

*الصورة الثانية من [Microsoft Learn](https://learn.microsoft.com/en-us/power-bi/fundamentals/desktop-getting-started)، وتعرض واجهة **Power Query Editor** الفعلية أثناء معالجة البيانات.*

للتجربة، جهّز ملف Excel بسيطًا يحتوي على أعمدة مثل `Region` و`Amount` و`Date`. ثم نفذ الخطوات التالية بالترتيب:

1. افتح Power BI Desktop، واختر **Home → Get Data → Excel Workbook**، ثم حدد ملف Excel.
2. من نافذة **Navigator** اختر الجدول الذي تريد تحليله.
3. إذا كانت الأعمدة تحتاج إلى تنظيف، اضغط **Transform Data**. ستنتقل إلى **Power Query** حيث تستطيع تغيير نوع البيانات، وحذف الصفوف غير المطلوبة، وتصحيح أسماء الأعمدة. بعد ذلك اضغط **Close & Apply**.
4. انتقل إلى **Report View**. اختر الرسم العمودي مثلًا، وضع `Region` في المحور و`Amount` في القيم.
5. أضف **Slicer** للسنة أو المنطقة حتى يستطيع قارئ التقرير تغيير نطاق البيانات بسهولة.
6. احفظ عملك من **File → Save**. امتداد الملف غالبًا `.pbix`.

بهذا تكون بنيت تقريرًا أوليًا: **استيراد البيانات ← تجهيزها ← تصميم الرسم ← إضافة الفلاتر ← حفظ التقرير**.

### تجربة مقياس DAX

إذا كان اسم الجدول `Sales` واسم عمود القيم `Amount`، اختر **Modeling → New Measure** ثم اكتب:

</div>

```dax
Total Sales = SUM(Sales[Amount])
```

<div dir="rtl" align="right">

يعيد هذا المقياس مجموع المبالغ في العمود. على سبيل المثال، إذا كان العمود يحتوي على 100 و150 فالناتج **250**. وعند استخدام الفلاتر قد تتغير القيمة بحسب السجلات المعروضة. هذه أرقام تدريبية لتجربة المعادلة فقط.

## 4. أين أجد الأدوات الأساسية؟

<p align="center"><img src="https://learn.microsoft.com/id-id/power-bi/create-reports/media/sample-tutorial-connect-to-the-samples/power-bi-samples-desktop.png" alt="لقطة حقيقية من واجهة Power BI Desktop — المثال 3" width="92%"/></p>

*تُظهر الصورة الثالثة مساحة **Report View** والرسوم والمرشحات من [Microsoft Learn](https://learn.microsoft.com/en-us/power-bi/create-reports/sample-tutorial-connect-to-the-samples).*

| الأداة | متى أستخدمها؟ |
| :---: | :---: |
| **Power Query** | عندما تحتاج لتنظيف البيانات أو دمج الملفات أو تعديل نوع العمود |
| **Model View** | عندما تعمل على أكثر من جدول وتحتاج إلى تحديد العلاقات |
| **DAX Measures** | عندما تريد حساب الإجمالي أو المتوسط أو أي مؤشر مشتق |
| **Report View** | عندما تبدأ تصميم الرسوم والجداول والبطاقات |
| **Slicers** | عندما تريد أن يحدد المستخدم سنة أو منطقة أو فئة معينة |
| **Publish** | عندما تريد نشر التقرير على الخدمة السحابية وتملك الصلاحيات اللازمة |

## 5. إذا واجهتك مشكلة

| المشكلة | جرب هذا أولًا |
| :---: | :---: |
| لا تظهر كل بيانات Excel | تأكد من اختيار الجدول الصحيح في Navigator، ومن وجود عناوين أعمدة واضحة |
| يظهر الرسم فارغًا | افحص نوع البيانات والعلاقات والفلاتر المطبّقة على الصفحة |
| التقرير لا يعكس آخر تعديل في Excel | اضغط **Refresh** وتأكد أن مسار المصدر لم يتغير |
| يظهر خطأ في DAX | تحقق من أسماء الجداول والأعمدة والأقواس |
| لا تستطيع مشاركة التقرير | راجع نوع حسابك وصلاحيات النشر والتراخيص |
| ملف PBIX لا يعمل في Report Server | افتحه بنسخة **Power BI Desktop for Report Server** المتوافقة مع الخادم |
| أصبح التقرير بطيئًا | ابدأ بمراجعة حجم البيانات والاستعلامات والعلاقات غير الضرورية |

## 6. قبل أن تشارك التقرير

إذا استخدمت وضع **Import** فقد يحتوي ملف `.pbix` نفسه على نسخة من البيانات. لذلك افحص محتواه وصلاحية نشر البيانات قبل مشاركته، ولا تضع كلمات المرور أو مسارات الخوادم الداخلية ضمن ملفات عامة.

## 7. المصادر الرسمية

- [Microsoft — تنزيل Power BI Desktop](https://www.microsoft.com/en-us/download/details.aspx?id=58494)
- [Microsoft Learn — دليل تثبيت Power BI Desktop](https://learn.microsoft.com/en-us/power-bi/fundamentals/desktop-get-the-desktop)

يمكنك الرجوع إلى [صفحة أدلة البرامج](../../README.md) لاختيار البرنامج التالي.

</div>