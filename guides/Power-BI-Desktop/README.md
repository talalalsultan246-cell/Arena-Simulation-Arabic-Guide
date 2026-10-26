<div dir="rtl" align="right">

# دليل Power BI Desktop
**التثبيت، إنشاء لوحة معلومات، وحل المشكلات الأساسية**

إعداد: **Talal Alsultan** | تحديث: أكتوبر 2026

Power BI Desktop برنامج لإنشاء نماذج البيانات والتقارير التفاعلية. يمكن استخدامه لتحليل ملفات Excel وCSV وقواعد البيانات ثم بناء رسوم ومؤشرات أداء. **البرنامج المكتبي مجاني للتنزيل**؛ أما مشاركة التقارير في بعض خدمات Microsoft فقد تتطلب صلاحيات أو تراخيص إضافية.

## 1. روابط Microsoft الرسمية

- [صفحة تحميل Power BI Desktop](https://www.microsoft.com/en-us/download/details.aspx?id=58494)
- [Microsoft Learn — تعليمات التحميل والتثبيت](https://learn.microsoft.com/en-us/power-bi/fundamentals/desktop-get-the-desktop)
- [Power BI Desktop من Microsoft Store](https://aka.ms/pbidesktopstore)

> **مهم:** Power BI Desktop العادي يختلف عن **Power BI Desktop (Optimized for Report Server)**. إذا كنت ستنشر التقارير على خادم داخلي من نوع Power BI Report Server، فانتقل إلى [دليل الخادم](../Power-BI-Report-Server/README.md) لمعرفة النسخة المناسبة.

## 2. خطوات التثبيت

**الخيار الأول: Microsoft Store**

1. افتح رابط [Microsoft Store](https://aka.ms/pbidesktopstore).
2. اختر **Get / Install**، ثم افتح التطبيق بعد انتهاء التثبيت.
3. هذه الطريقة مناسبة عادة للتحديثات التلقائية عبر المتجر.

**الخيار الثاني: تنزيل ملف EXE**

1. افتح [مركز تنزيل Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=58494).
2. اضغط **Download** واختر مثبت **64-bit**.
3. افتح ملف `PBIDesktopSetup_x64.exe` من مجلد Downloads.
4. اتبع معالج التثبيت، ثم افتح Power BI Desktop.

**لماذا 64-bit؟** توضح Microsoft أن نسخة Power BI Desktop العادية 32-bit لم تعد مدعومة.

## 3. كيف أبدأ أول تقرير؟

1. جهز ملف Excel يحتوي على جدول واضح بعناوين الأعمدة، مثل `Region` و`Sales` و`Date`.
2. من Power BI اختر **Home → Get data → Excel workbook** وحدد الملف.
3. اختر الجدول من **Navigator**، ثم **Load**، أو **Transform Data** إذا احتجت تعديل الأعمدة في Power Query.
4. انتقل إلى **Report view**، واختر رسمًا بيانيًا مناسبًا، واسحب الحقول إليه.
5. أضف **Slicer** للمنطقة أو السنة عند الحاجة.
6. احفظ التقرير بصيغة `.pbix` بواسطة **File → Save**.

### مثال مقياس DAX

إذا كان لديك جدول اسمه `Sales` وحقل رقمي اسمه `Amount`، فيمكن إنشاء مقياس من **Modeling → New measure**:

```dax
Total Sales = SUM(Sales[Amount])
```

النتيجة ليست رقمًا ثابتًا؛ إنها مجموع القيم الموجودة في `Amount`، وتتغير بحسب المرشحات المستخدمة في التقرير.

## 4. أهم الأجزاء

| المكوّن | ماذا أفعل فيه؟ |
| :---: | :---: |
| Power Query | تنظيف البيانات وتغيير أنواع الأعمدة |
| Model view | إنشاء العلاقات بين الجداول |
| DAX Measures | حساب المؤشرات مثل الإجماليات والمتوسطات |
| Report view | إنشاء الرسوم والخرائط والجداول |
| Slicers | تصفية التقرير تفاعليًا |
| Publish | نشر التقرير إلى Power BI Service عند توفر الصلاحيات |

## 5. أخطاء تتكرر

| المشكلة | ما الذي أفحصه؟ |
| :---: | :---: |
| ملف Excel لا يظهر كاملًا | اسم الورقة أو الجدول، وأسماء الأعمدة |
| بعض الرسومات فارغة | نوع الأعمدة والعلاقات والمرشحات |
| رسالة Circular dependency | العلاقات أو معادلات DAX المعتمدة على نفسها |
| لا يتغير التقرير بعد تعديل Excel | نفّذ **Refresh** وتأكد من مسار الملف |
| لا أستطيع النشر | حساب Microsoft والصلاحيات وتراخيص مساحة العمل |
| ملف PBIX لا يعمل على Report Server | توافق إصدار Desktop مع إصدار الخادم |
| بطء التقرير | حجم البيانات ونموذج العلاقات والاستعلامات المعقدة |

## 6. تنبيه بخصوص البيانات الحساسة

عند مشاركة `.pbix` قد يكون النموذج مستوردًا ومتضمنًا للبيانات، لذا افحص الملف ومصدر البيانات والصلاحيات قبل نشره في مستودع عام. ولا تضع كلمات مرور أو عناوين خوادم داخل ملفات الأمثلة المنشورة.

## 7. المصادر

- [Microsoft Learn — Power BI Desktop](https://learn.microsoft.com/en-us/power-bi/fundamentals/desktop-get-the-desktop)
- [Microsoft Download Center — Power BI Desktop](https://www.microsoft.com/en-us/download/details.aspx?id=58494)

</div>