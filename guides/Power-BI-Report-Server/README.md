<div dir="rtl" align="right">

# دليل Power BI Report Server
**الفكرة العامة، تنزيل الخادم، نشر التقارير والتحديث المجدول**

إعداد: **Talal Alsultan** | تحديث: أكتوبر 2026

**Power BI Report Server (PBIRS)** خادم تقارير داخل مقر الجهة (On-premises). يستخدم لعرض ملفات Power BI والتقارير المقسمة إلى صفحات ومؤشرات الأداء من خلال بوابة داخلية، ويمكن تشغيله في بيئة لا تعتمد على نشر التقارير في خدمة Power BI السحابية.

**هذا دليل للإعداد التقني، وليس تعليمات لتنصيب خادم إنتاج دون تنسيق مع مسؤول الأنظمة.** تشغيل PBIRS يحتاج ترخيصًا ومتطلبات خادم وقاعدة بيانات وصلاحيات مناسبة.

## 1. الروابط الرسمية

- [Microsoft — تنزيل Power BI Report Server](https://learn.microsoft.com/en-us/power-bi/report-server/download-powerbi-report-server)
- [Microsoft — تنزيل Power BI Report Server (September 2026)](https://www.microsoft.com/en-us/download/details.aspx?id=105945)
- [Microsoft — خطوات تثبيت الخادم](https://learn.microsoft.com/en-us/power-bi/report-server/install-report-server)
- [Microsoft — تنزيل Desktop الخاص بالخادم](https://learn.microsoft.com/en-us/power-bi/report-server/install-powerbi-desktop)
- [Microsoft — إدارة التحديث المجدول](https://learn.microsoft.com/en-us/power-bi/report-server/configure-scheduled-refresh)

تعرض Microsoft حزمة **September 2026**، المنشورة في 1 أكتوبر 2026. قد تتغير الإصدارات لاحقًا؛ استخدم النسخة المناسبة للخادم الحالي.

## 2. الفرق بين Desktop وReport Server

| Power BI Desktop | Power BI Report Server |
| :---: | :---: |
| بناء البيانات والرسوم والنماذج | استضافة وعرض التقارير وإدارة الوصول |
| يعمل على جهاز المحلل | يعمل على خادم الجهة |
| يحفظ تقرير `.pbix` | يستقبل تقارير PBIX المتوافقة |
| لا يحتاج خادمًا لإنشاء تقرير محلي | يحتاج تثبيتًا وإعدادًا وقاعدة بيانات |

### مخطط مبسط للعمل

```mermaid
flowchart LR
    A["ملفات Excel أو قواعد بيانات"] --> B["Power BI Desktop for Report Server"]
    B --> C["PBIX"]
    C --> D["Power BI Report Server"]
    D --> E["بوابة داخلية للمستخدمين"]
    A -.-> F["Scheduled Refresh"]
    F --> D
```

## 3. تثبيت Power BI Report Server — لمسؤول الأنظمة

1. اقرأ [متطلبات الإصدار](https://learn.microsoft.com/en-us/power-bi/report-server/download-powerbi-report-server) وتأكد من توفر ترخيص مناسب وبيئة Windows مدعومة.
2. حدد SQL Server Database Engine الذي سيستضيف قاعدة بيانات Report Server.
3. نزّل `PowerBIReportServer.exe` من صفحة Microsoft الرسمية.
4. شغّل المثبت، ثم اختر **Install Power BI Report Server**، وحدد الإصدار/الترخيص الذي تملكه.
5. وافق على شروط الترخيص واختر مسار التثبيت.
6. بعد الانتهاء افتح **Report Server Configuration Manager**.
7. اضبط **Service Account**، واتصال قاعدة البيانات (**Database**)، و**Web Service URL** و**Web Portal URL**، وأي إعدادات اتصال وأمان مطلوبة.
8. احفظ مفاتيح التشفير بحسب إرشادات Microsoft واختبر فتح بوابة التقارير من الشبكة المصرح لها.

> لا يكفي تشغيل ملف التثبيت وحده؛ يجب إكمال الإعداد في Configuration Manager والتأكد من قاعدة البيانات والشبكة.

## 4. تنزيل النسخة المناسبة من Power BI Desktop

لإنشاء تقرير يعمل على PBIRS، **لا تعتمد تلقائيًا على Power BI Desktop العادي**:

1. افتح بوابة الخادم ثم اختر **Download → Power BI Desktop** إذا كانت هذه الميزة متاحة.
2. أو افتح [دليل Microsoft لتحميل نسخة Report Server](https://learn.microsoft.com/en-us/power-bi/report-server/install-powerbi-desktop).
3. حمّل النسخة المتوافقة مع إصدار خادمك؛ مثال: الإصدار المرافق لحزمة September 2026.
4. بعد التثبيت راجع اسم النسخة وتاريخها في شريط عنوان Power BI Desktop.
5. افتح تقرير PBIX باستخدام Desktop المناسب ثم انشره للخادم.

تسمح Microsoft بتثبيت نسختَي Desktop العادية وDesktop الخاصة بـ Report Server على الجهاز نفسه، لكن فتح ملف PBIX بالنقر المزدوج قد يعتمد على آخر نسخة ثبتّها.

## 5. نشر تقرير داخل الجهة

1. افتح **Power BI Desktop for Report Server**.
2. جهز البيانات والمرئيات واحفظ `.pbix`.
3. من **File → Save as** أو من بوابة الخادم ارفع التقرير حسب الخيارات المدعومة بإصدارك.
4. اختر مجلدًا في بوابة الخادم تملك صلاحية النشر فيه.
5. افتح التقرير من المتصفح وتأكد من وجود الرسوم والمرشحات.
6. اختبره بحساب قارئ للتأكد من أن الصلاحيات لا تزيد عن الحاجة.

## 6. التحديث المجدول Scheduled Refresh

للتقارير التي تستورد البيانات داخل PBIX، يمكن إعداد Refresh حسب مصادر البيانات المدعومة:

1. في بوابة التقارير، افتح قائمة التقرير واختر **Manage**.
2. انتقل إلى **Data Sources** واضبط بيانات اعتماد الاتصال المصرح بها.
3. افتح **Scheduled Refresh** ثم **New Scheduled Refresh Plan**.
4. اختر أوقات التحديث وراقب سجل نجاحه أو فشله.

**مشكلة شائعة:** إذا كان التقرير يستورد Excel من مسار على كمبيوتر المحلل مثل `C:\Users\...\Desktop\sales.xlsx`، قد لا يستطيع خادم PBIRS الوصول للملف، وبالتالي لن يعمل التحديث المجدول. استخدم مشاركة شبكية مسموحًا للخادم بالوصول إليها، مثل `\\fileserver\department\sales.xlsx`، مع صلاحيات القراءة المناسبة. <https://learn.microsoft.com/en-us/power-bi/report-server/scheduled-refresh>

## 7. أخطاء تتكرر

| المشكلة | الخطوة الأولى |
| :---: | :---: |
| تقرير PBIX لا يفتح | افحص توافق نسخة Desktop مع الخادم |
| لا أستطيع رؤية المجلد | تحقق من دور المستخدم وصلاحية Browser |
| زر رفع التقرير غير متاح | تحقق من صلاحيات النشر وإدارة المحتوى |
| Refresh يفشل | افحص مصدر البيانات ومساره وبيانات الاعتماد |
| البوابة لا تُفتح | راجع Web Portal URL والخدمة والجدار الناري |
| تقرير Excel لا يتحدث | تحقق من تحديث الملف الأصلي وجدولة تحديث البيانات |
| الأداء ضعيف | افحص الذاكرة وحجم النموذج والاستعلامات |

## 8. مراجع Microsoft

- [Get started with Power BI Report Server](https://learn.microsoft.com/en-us/power-bi/report-server/get-started)
- [Install Power BI Report Server](https://learn.microsoft.com/en-us/power-bi/report-server/install-report-server)
- [Power BI Report Server scheduled refresh](https://learn.microsoft.com/en-us/power-bi/report-server/scheduled-refresh)
- [Power BI Desktop optimized for Report Server](https://learn.microsoft.com/en-us/power-bi/report-server/install-powerbi-desktop)

</div>