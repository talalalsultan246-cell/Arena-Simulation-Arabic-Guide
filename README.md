<div align="center" dir="rtl">

# دليل تثبيت Arena Simulation 

</div>

<div align="center" dir="rtl">

> **آخر مراجعة للمصادر: 25 أكتوبر 2026**  
> دليل مستقل باللغة العربية، موجّه لطلاب المحاكاة ومستخدمي **Arena 17** والإصدارات الأخرى. يعتمد على تعليمات الشركة المصنّعة ومراجع Microsoft، ولا يُعدّ وثيقة رسمية من Rockwell Automation.

</div>

<div align="center" dir="rtl">

## الإصدار المستهدف: Arena 17

</div>

- يستهدف هذا الدليل **Arena 17**، وبالأخص التحديث **17.00.01**.
- يعرض [مركز تنزيل Rockwell الرسمي](https://compatibility.rockwellautomation.com/Pages/MultiProductFindDownloads.aspx?crumb=112&mode=3&refSoft=1&versions=65330) الإصدار **17.00.01** مع إصدارات سابقة.
- توصي [نشرة Rockwell الأمنية](https://www.rockwellautomation.com/en-us/trust-center/security-advisories.html) باستخدام **17.00.01** لمعالجة ثغرات في **17.00.00 وما قبله**. تحقق من رقم التصحيح قبل التحميل.
- يظهر في تسجيل الشاشة المرفق مسار الملفات `C:\RA\17.00.01.10_x64\17.00.01.10_x64\MediaImage`، بينما تحمل شاشة المثبت اسم **Arena 2026**. يشير ذلك إلى اختلاف الاسم التسويقي للمثبت عن رقم فرع البرنامج؛ لا تخلط بينهما.
- **تنبيه:** تظل صفحة متطلبات النظام العامة لدى Rockwell تعرض الإصدار **16.20.02**؛ راجع وثائق الإصدار 17 المطلوبة على مركز التنزيل عند وجود اختلاف.

<div align="center" dir="rtl">

## المحتويات
1. [قبل البدء](#1-قبل-البدء)
2. [الحد الأدنى للمواصفات](#2-الحد-الأدنى-للمواصفات)
3. [فحص Windows والذاكرة والمساحة](#3-فحص-windows-والذاكرة-والمساحة)
4. [فحص وتثبيت .NET Framework](#4-فحص-وتثبيت-net-framework)
5. [فحص جميع إصدارات Microsoft Visual C++](#5-فحص-جميع-إصدارات-microsoft-visual-c)
6. [فحص SQL Server Compact 4.0](#6-فحص-sql-server-compact-40)
7. [فحص Office](#7-فحص-office)
8. [تحميل Arena وتثبيته رسميًا](#8-تحميل-arena-وتثبيته-رسميًا)
9. [فحص الترخيص وتشغيل نموذج تجريبي](#9-فحص-الترخيص-وتشغيل-نموذج-تجريبي)
10. [حل مشكلة الأدوات والقوائم غير المفعّلة](#10-حل-مشكلة-الأدوات-والقوائم-غير-المفعلة)
11. [الأسئلة الشائعة والمراجع](#11-الأسئلة-الشائعة-والمراجع)

</div>

---

<div align="center" dir="rtl">

## 1. قبل البدء

</div>

<div align="center" dir="rtl">

الغرض من هذا الدليل **التحقق أولًا، ثم تنزيل وتثبيت الناقص فقط**. إذا كان Arena يفتح ولكن أدوات Create وProcess وDispose أو القوائم تظهر باللون الرمادي (Disabled)، **لا تبدأ بإلغاء تثبيته**؛ فالمشكلة قد تكون في عدم فتح نموذج أو وضع التشغيل أو الترخيص أو مكوّنات النظام.

</div>

- احفظ نسخًا احتياطية من نماذجك (`.doe` وأي ملفات مشروع مرتبطة بها).
- استخدم روابط Microsoft وRockwell الرسمية؛ لا تشغّل ملفات `.exe` مجهولة المصدر من مستودعات خارجية.
- افتح نافذة الأوامر عبر **Start > CMD > Run as administrator** عند الحاجة إلى الصلاحيات، لكن أوامر القراءة أدناه لا تحتاج غالبًا إلى تشغيل المدير.
- أوامر `cmd` توضع في Command Prompt، وأوامر `powershell` توضع في Windows PowerShell. يمكن أيضًا تنفيذ الأمر البديل المحدد من نافذة CMD.
- وجود حزمة مثبتة **لا يثبت وحده** أنها سبب العطل أو أن إصدارها مناسب لكل نسخة Arena.
- افحص معمارية برنامج Arena نفسه (`x86` أو `x64`)، فهي ليست بالضرورة مطابقة لمعمارية Office أو Windows.

<div align="center" dir="rtl">

### روابط التنزيل الرسمية المختصرة

</div>

<div align="center" dir="rtl">

> **الروابط الخارجية:** روابط التحميل والمراجع تنقلك مباشرةً إلى المواقع الرسمية المعنية. إذا أردت فتح الرابط في تبويب منفصل دون مغادرة هذا الدليل، استخدم **Ctrl + Click** على Windows أو **فتح في علامة تبويب جديدة** من قائمة المتصفح على الهاتف. لا يمكن فرض فتح تبويب جديد تلقائيًا داخل GitHub README.

</div>

| البرنامج | المصدر الرسمي | متى أحتاجه؟ |
| :---: | :---: | :---: |
| Arena Simulation | [Rockwell Automation: تنزيل Arena](https://www.rockwellautomation.com/en-us/products/software/arena-simulation/buying-options/download.html) | تنزيل البرنامج أو إعادة تثبيته بعد التشخيص |
| .NET Framework 4.8.1 Runtime | [Microsoft: .NET Framework 4.8.1](https://dotnet.microsoft.com/en-us/download/dotnet-framework/net481) | إذا تطلّبه Arena وكانت النسخة المثبتة أقدم وكانت 4.8.1 متوافقة مع Windows |
| Visual C++ Redistributable x64 | [Microsoft: تنزيل مباشر x64](https://aka.ms/vc14/vc_redist.x64.exe) | للتطبيقات ذات معمارية 64-bit التي تحتاج مكتبات v14 |
| Visual C++ Redistributable x86 | [Microsoft: تنزيل مباشر x86](https://aka.ms/vc14/vc_redist.x86.exe) | للتطبيقات ذات معمارية 32-bit التي تحتاج مكتبات v14، حتى على Windows 64-bit |
| Visual C++ الإصدارات القديمة | [Microsoft: جميع الإصدارات المدعومة والقديمة](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist) | عند إثبات احتياج إصدار أقدم محدد |
| SQL Server Compact 4.0 SP1 | [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=30709) | **اختياري** فقط عند ثبوت الحاجة |
| Microsoft Office | [Microsoft 365](https://www.microsoft.com/microsoft-365) | إذا كانت ميزات تقارير Excel مطلوبة ولم يكن Office موجودًا |

<div align="center" dir="rtl">

> **تنبيه دقة:** تعرض [صفحة متطلبات Rockwell الرسمية](https://www.rockwellautomation.com/en-us/products/software/arena-simulation/support/system-requirements.html) بيانات لإصدار **16.20.02**. لا يُفترض تلقائيًا أن تفاصيل الصفحة تنطبق بالكامل على **Arena 17**. راجع ملف المتطلبات المرفق مع نسختك إذا اختلفت الأرقام.

</div>

<div align="center" dir="rtl">

## 2. الحد الأدنى للمواصفات

</div>

<div align="center" dir="rtl">

بحسب صفحة Rockwell المتاحة لإصدار 16.20.02:

</div>

| العنصر | الحد الأدنى في صفحة Rockwell | الموصى به |
| :---: | :---: | :---: |
| RAM | 8 GB | 16 GB |
| مساحة القرص الحرة | 2 GB | 4 GB |
| المعالج | Intel ثنائي النواة، 3 GHz | بحسب تعقيد النموذج |
| نظام التشغيل | Windows 10 / 11 Pro أو Enterprise بحسب قائمة دعم Rockwell | نظام تدعمه النسخة المستهدفة |
| Microsoft Office | يُستخدم لعرض تقارير إحصاءات Excel | تحقق من التوافق |
| صلاحيات التثبيت | صلاحيات Administrator | مطلوبة للتثبيت |

<div align="center" dir="rtl">

**لا تعتمد رقم 4GB RAM الموجود في الدليل القديم كحد أدنى موثّق حاليًا من Rockwell.** ولا تَعُدّ الدعم الرسمي لنظام Windows أو Arena 17 مؤكدًا إلا بعد مراجعة وثائق نسختك.

</div>

<div align="center" dir="rtl">

## 3. فحص Windows والذاكرة والمساحة

</div>

<div align="center" dir="rtl">

### معرفة إصدار Windows

</div>

<div align="center" dir="rtl">

افتح CMD:

</div>

```cmd
winver
```

<div align="center" dir="rtl">

**Output (مثال توضيحي، وليس نتيجة جهازك):**

</div>

```text
[تفتح نافذة About Windows في واجهة النظام]
Windows 11
Version: 23H2 (مثال فقط)
```

<div align="center" dir="rtl">

**كيف تقرأ النتيجة؟** هذا الأمر يفتح نافذة رسومية؛ لا يطبع تقريرًا داخل CMD. الرقم المعروض على جهازك قد يختلف.

</div>

<div align="center" dir="rtl">

أو:

</div>

```cmd
ver
```

<div align="center" dir="rtl">

**Output (مثال توضيحي، وليس نتيجة جهازك):**

</div>

```text
Microsoft Windows [Version 10.0.22631.XXXX]
```

<div align="center" dir="rtl">

**كيف تقرأ النتيجة؟** يعرض إصدار نظام Windows في نافذة CMD؛ قيمة XXXX موضعية وليست نتيجة فعلية.

</div>

<div align="center" dir="rtl">

لمعلومات أوسع: اضغط `Win + R`، واكتب `msinfo32`. ستجد `OS Name` و`System Type` و`Installed Physical Memory`.

</div>

<div align="center" dir="rtl">

### قياس الذاكرة RAM بواسطة CMD

</div>

```cmd
powershell -NoProfile -Command "Get-CimInstance Win32_ComputerSystem | Select-Object @{N='RAM_GB';E={[math]::Round($_.TotalPhysicalMemory/1GB,2)}}"
```

<div align="center" dir="rtl">

**Output (مثال توضيحي، وليس نتيجة جهازك):**

</div>

```text
RAM_GB
------
 16.00
```

<div align="center" dir="rtl">

**كيف تقرأ النتيجة؟** 16.00 تعني سعة ذاكرة RAM قدرها 16 جيجابايت في هذا المثال فقط.

</div>

<div align="center" dir="rtl">

### قياس المساحة الحرة على القرص C:

</div>

```cmd
powershell -NoProfile -Command "Get-PSDrive C | Select-Object Name,@{N='Free_GB';E={[math]::Round($_.Free/1GB,2)}}"
```

<div align="center" dir="rtl">

**Output (مثال توضيحي، وليس نتيجة جهازك):**

</div>

```text
Name Free_GB
---- -------
C      125.50
```

<div align="center" dir="rtl">

**كيف تقرأ النتيجة؟** Free_GB هي المساحة الحرة المتبقية على محرك C، وليست المساحة الإجمالية.

</div>

<div align="center" dir="rtl">

**التفسير:** إذا أظهر الحاسوب 8GB RAM ومساحة كافية، فهذا اجتياز أولي للمواصفات المذكورة، لكنه لا يثبت صلاحية الترخيص أو التوافق الكامل لإصدار Arena 17.

</div>

<div align="center" dir="rtl">

## 4. فحص وتثبيت .NET Framework

</div>

<div align="center" dir="rtl">

### الأمر الأول (CMD)

</div>

```cmd
reg query "HKLM\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full" /v Release
```

<div align="center" dir="rtl">

**Output (مثال توضيحي، وليس نتيجة جهازك):**

</div>

```text
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full
    Release    REG_DWORD    0x80ea8
```

<div align="center" dir="rtl">

**كيف تقرأ النتيجة؟** القيمة السداسية 0x80ea8 تساوي 528040 بالنظام العشري، وتمثل .NET Framework 4.8 في إحدى بيئات Windows.

</div>

<div align="center" dir="rtl">

### الأمر البديل (PowerShell)

</div>

```powershell
(Get-ItemProperty 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full').Release
```

<div align="center" dir="rtl">

**Output (مثال توضيحي، وليس نتيجة جهازك):**

</div>

```text
528040
```

<div align="center" dir="rtl">

**كيف تقرأ النتيجة؟** يعرض PowerShell القيمة نفسها بالأرقام العشرية؛ 528040 قيمة نموذجية لـ .NET Framework 4.8.

</div>

<div align="center" dir="rtl">

### تفسير أشهر قيم Release

</div>

| القيمة | نسخة .NET Framework |
| :---: | :---: |
| 528040 أو 528049 أو 528372 أو 528449 | 4.8 (تختلف قيمة التسجيل بحسب Windows) |
| 533320 أو 533325 أو 533509 | 4.8.1 |

<div align="center" dir="rtl">

توجد قيم أخرى بحسب إصدار Windows. الرقم **528040 أو أعلى** يدل عادة على وجود .NET Framework 4.8 أو إصدار أحدث ضمن سلسلة 4.x. المرجع: [Microsoft: كيفية التعرف إلى الإصدارات المثبتة](https://learn.microsoft.com/en-us/dotnet/framework/install/how-to-determine-which-versions-are-installed).

</div>

<div align="center" dir="rtl">

**عند الحاجة للتثبيت:**

</div>

1. ادخل [صفحة Microsoft الرسمية لـ .NET Framework 4.8.1](https://dotnet.microsoft.com/en-us/download/dotnet-framework/net481).
2. اختر **Runtime** لتشغيل البرامج؛ ليس **Developer Pack**.
3. تأكد من توافق النسخة مع Windows عندك.
4. نفّذ مثبت Microsoft الرسمي وأعد تشغيل الجهاز **إذا طُلب منك ذلك**.
5. كرّر أمر قراءة `Release` للتحقق.

<div align="center" dir="rtl">

لا تثبّت .NET 4.8.1 إذا كان Windows يحتوي عليه بالفعل.

</div>

<div align="center" dir="rtl">

## 5. فحص جميع إصدارات Microsoft Visual C++

</div>

<div align="center" dir="rtl">

هذه أكثر خطوة احتاجت إلى تحديث في المستودع المرجعي.

</div>

<div align="center" dir="rtl">

### الطريقة الأولى: أمر المستودع القديم باستخدام WMIC

</div>

```cmd
wmic product where "name like '%%Visual C++%%'" get name,version
```

<div align="center" dir="rtl">

**Output (مثال توضيحي، وليس نتيجة جهازك):**

</div>

```text
'wmic' is not recognized as an internal or external command,
operable program or batch file.
```

<div align="center" dir="rtl">

**كيف تقرأ النتيجة؟** هذه رسالة فشل محتملة على Windows 11 الحديث؛ عند ظهورها استخدم الطريقة الثانية بدل إعادة تثبيت WMIC.

</div>

<div align="center" dir="rtl">

**مهم:** هذه الصيغة من دليل GitHub الأصلي، وهي **قديمة وغير موصى بها**؛ وقد تفشل برسالة `'wmic' is not recognized` على Windows 11 الحديث. أعلنت Microsoft إزالة أداة WMIC من Windows 11 المدعوم في 2026. كذلك فحص `Win32_Product` قد يكون بطيئًا ويُسبّب عمليات فحص اتساق لحزم MSI، ولا يضمن إظهار جميع الحزم.

</div>

<div align="center" dir="rtl">

**إذا لم يعمل الأمر الأول، انتقل مباشرةً إلى الطريقة الثانية؛ لا تحتاج إلى إعادة تثبيت WMIC.**

</div>

<div align="center" dir="rtl">

### الطريقة الثانية: أمر بديل يعمل داخل CMD ويُظهر الأسماء والإصدارات

</div>

<div align="center" dir="rtl">

انسخ **السطر كاملًا** في نافذة CMD:

</div>

```cmd
powershell -NoProfile -Command "Get-ItemProperty 'HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall\*','HKLM:\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\*' -ErrorAction SilentlyContinue | Where-Object { $_.DisplayName -like '*Microsoft Visual C++*' } | Sort-Object DisplayName,DisplayVersion | Select-Object DisplayName,DisplayVersion | Format-Table -AutoSize"
```

<div align="center" dir="rtl">

**Output (مثال توضيحي، وليس نتيجة جهازك):**

</div>

```text
DisplayName                                                  DisplayVersion
-----------                                                  --------------
Microsoft Visual C++ 2013 x86 Minimum Runtime                12.0.40664
Microsoft Visual C++ 2015-2022 Redistributable (x64)          14.40.33816
Microsoft Visual C++ 2015-2022 Redistributable (x86)          14.40.33816
```

<div align="center" dir="rtl">

**شرط التحقق المهم: التأكد من وجود Microsoft Visual C++ 2022**

بعد تنفيذ الأمر، ابحث في عمود `DisplayName` عن **Microsoft Visual C++ 2015–2022 Redistributable**، أو حزمة **Visual C++ v14 أحدث متوافقة مع Visual Studio 2022**. تأكد من المعمارية المناسبة: `(x64)` لبرامج 64-bit و`(x86)` لبرامج 32-bit. ويُفضّل فحص وجود النسختين على Windows بنظام 64-bit عند استخدام برامج مختلفة المعمارية.

**إذا لم تظهر حزمة متوافقة، راجع روابط Microsoft الرسمية:** [تحميل x64](https://aka.ms/vc14/vc_redist.x64.exe) | [تحميل x86](https://aka.ms/vc14/vc_redist.x86.exe).

**تنبيه:** قد يتغير اسم الحزمة في الإصدارات الأحدث؛ لا يُشترط ظهور لفظ `2022` حرفيًا إذا كانت حزمة **v14** المثبتة أحدث ومتوافقة. هذه **خطوة تحقق في الدليل** وليست إثباتًا بأن Arena 17 يشترط حزمة باسم 2022 تحديدًا.

</div>

<div align="center" dir="rtl">

**كيف تقرأ النتيجة؟** يعرض العمود الأول أسماء الحزم ومعماريتها، والثاني الإصدارات المثبتة. الصفوف هنا أمثلة وليست بيانات جهازك.

</div>

<div align="center" dir="rtl">

**هذا هو البديل الموصى به في الدليل.** يقرأ بيانات البرامج المسجلة في مساري Uninstall ذوي المعماريتين. سيعرض عمودين:

</div>

- `DisplayName`: اسم الحزمة، وغالبًا يظهر فيه x86 أو x64.
- `DisplayVersion`: رقم الإصدار المثبت.

<div align="center" dir="rtl">

ملاحظة: قد توجد حزم غير مسجلة في هذه المفاتيح، لذا لا يُعدّ الأمر فحصًا جنائيًا شاملًا لكل ملف DLL في النظام.

</div>

<div align="center" dir="rtl">

### الطريقة الثالثة: تنفيذ الأمر مباشرة داخل PowerShell

</div>

<div align="center" dir="rtl">

إذا أردت استخدام PowerShell بدل CMD:

</div>

```powershell
Get-ItemProperty 'HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall\*','HKLM:\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\*' -ErrorAction SilentlyContinue |
  Where-Object { $_.DisplayName -like '*Microsoft Visual C++*' } |
  Sort-Object DisplayName, DisplayVersion |
  Select-Object DisplayName, DisplayVersion |
  Format-Table -AutoSize
```

<div align="center" dir="rtl">

**Output (مثال توضيحي، وليس نتيجة جهازك):**

</div>

```text
DisplayName                                                  DisplayVersion
-----------                                                  --------------
Microsoft Visual C++ 2015-2022 Redistributable (x64)          14.40.33816
Microsoft Visual C++ 2015-2022 Redistributable (x86)          14.40.33816
```

<div align="center" dir="rtl">

**كيف تقرأ النتيجة؟** نفس المبدأ عند استخدام PowerShell مباشرة. قد تختلف القائمة والإصدارات، وقد تظهر صفوف إضافية.

</div>

<div align="center" dir="rtl">

### الطريقة الرابعة: واجهة Windows

</div>

<div align="center" dir="rtl">

`Settings > Apps > Installed apps` ثم ابحث عن `Microsoft Visual C++`. تظهر النتائج حسب البرامج المسجلة في النظام.

</div>

<div align="center" dir="rtl">

### تنزيل حزم Microsoft عند الحاجة فقط

</div>

1. راجع معمارية **Arena** المطلوبة: x86 أو x64.
2. افتح [صفحة Microsoft للإصدارات المدعومة](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist).
3. للحزم الحديثة المتوافقة مع v14: [x86](https://aka.ms/vc14/vc_redist.x86.exe) أو [x64](https://aka.ms/vc14/vc_redist.x64.exe).
4. إذا ظهرت نافذة **Install / Repair / Uninstall** وكانت الحزمة نفسها مثبتة، جرّب **Repair** عندما توجد أدلة على فسادها، بدل حذفها عشوائيًا.
5. لا تحذف حزم 2008/2010/2012/2013 لمجرد أنها قديمة؛ قد تستخدمها برامج أخرى، وهي تُثبّت جنبًا إلى جنب مع الحزم الأحدث.
6. أعد تشغيل Windows إذا طلب المثبت، ثم افحص الإصدارات مجددًا.

<div align="center" dir="rtl">

**تنبيه:** تثبيت نسخة x64 وحدها لا يغطي جميع تطبيقات x86. وفي المقابل، ليس كل برنامج Arena بحاجة إلى جميع إصدارات Visual C++ المذكورة.

</div>

<div align="center" dir="rtl">

مراجع: [Microsoft VC++ downloads](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist) | [Microsoft WMIC removal](https://support.microsoft.com/en-us/servicing/os/windows/docs/2025/09/windows-management-instrumentation-command-line-wmic-removal-from-windows).

</div>

<div align="center" dir="rtl">

## 6. فحص SQL Server Compact 4.0

</div>

<div align="center" dir="rtl">

ورد هذا المكوّن في الدليل الأصلي، **لكن لم يثبت أنه متطلب لازم لجميع تثبيتات Arena 17**.

</div>

<div align="center" dir="rtl">

### فحص مسار السجل الأساسي باستخدام CMD

</div>

```cmd
reg query "HKLM\SOFTWARE\Microsoft\Microsoft SQL Server Compact Edition\v4.0" /v Version
```

<div align="center" dir="rtl">

**Output (مثال توضيحي، وليس نتيجة جهازك):**

</div>

```text
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Compact Edition\v4.0
    Version    REG_SZ    4.0.8876.1
```

<div align="center" dir="rtl">

**كيف تقرأ النتيجة؟** هذه نتيجة افتراضية عند وجود مفتاح Version في هذا المسار. قد يعرض جهازك قيمة أخرى أو عدم وجود المفتاح.

</div>

<div align="center" dir="rtl">

### فحص مسار السجل الثاني عند استخدام Windows 64-bit

</div>

```cmd
reg query "HKLM\SOFTWARE\WOW6432Node\Microsoft\Microsoft SQL Server Compact Edition\v4.0" /v Version
```

<div align="center" dir="rtl">

**Output (مثال توضيحي، وليس نتيجة جهازك):**

</div>

```text
ERROR: The system was unable to find the specified registry key or value.
```

<div align="center" dir="rtl">

**كيف تقرأ النتيجة؟** مثال عند عدم العثور على المفتاح في مسار WOW6432Node تحديدًا؛ لا يثبت هذا غياب المكوّن كليًا.

</div>

<div align="center" dir="rtl">

إذا ظهرت `ERROR: The system was unable to find the specified registry key or value.`، فالمعنى أن المفتاح غير موجود في **المسار المحدد**؛ وليس بالضرورة أن المكوّن غير موجود بأي صورة.

</div>

<div align="center" dir="rtl">

### عند إثبات الحاجة إليه

</div>

1. افتح [صفحة SQL Server Compact 4.0 SP1 على Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=30709).
2. اختر `SSCERuntime_x86-ENU.exe` أو `SSCERuntime_x64-ENU.exe` وفق المتطلب الفعلي.
3. شغّل المثبت الرسمي وتحقق من النتائج.
4. **تحذير أمني:** انتهى دعم SQL Server Compact 4.0 الممتد في **14 يوليو 2021**؛ لا توصي هذه الصفحة بتثبيته افتراضيًا على جهاز حديث. راجع [سجل دورة الحياة الرسمي](https://learn.microsoft.com/en-us/lifecycle/products/microsoft-sql-server-compact-40).

<div align="center" dir="rtl">

## 7. فحص Office

</div>

<div align="center" dir="rtl">

افتح **Excel > File > Account > About Excel** وتحقق من المعمارية والإصدار.

</div>

<div align="center" dir="rtl">

يمكن فحص نظام Click-to-Run عبر CMD:

</div>

```cmd
reg query "HKLM\SOFTWARE\Microsoft\Office\ClickToRun\Configuration" /v Platform
```

<div align="center" dir="rtl">

**Output (مثال توضيحي، وليس نتيجة جهازك):**

</div>

```text
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\Configuration
    Platform    REG_SZ    x64
```

<div align="center" dir="rtl">

**كيف تقرأ النتيجة؟** x64 تعني أن إصدار Office Click-to-Run مسجّل بمعمارية 64-bit؛ أما x86 فيشير إلى 32-bit.

</div>

<div align="center" dir="rtl">

القيمتان المحتملتان: `x86` و`x64`. إذا لم يظهر المفتاح، قد يكون Office مثبتًا بطريقة أخرى؛ هذا الأمر وحده لا يكفي للحكم.

</div>

<div align="center" dir="rtl">

**تصحيح مهم للدليل الأصلي:** Office **ليس ملزمًا بأن يكون 64-bit في جميع تثبيتات Arena**. راجع متطلبات Rockwell والإصدار المستهدف. لا تُزِل Office أو تغيّر معماريته دون سبب محدد.

</div>

<div align="center" dir="rtl">

## 8. تحميل Arena وتثبيته رسميًا

</div>

## دليل التثبيت بالصور: Arena 17

<p align="center" dir="rtl"><strong>من تسجيل الحساب إلى تشغيل برنامج Arena Simulation</strong></p>

> 🔴 **شرطان قبل تنزيل Arena:** إكمال بيانات الملف الشخصي (**Complete Profile**) وإضافة موقع الجهة التعليمية (**Location**). إذا كنت من طلاب جامعة الملك سعود، اختر **King Saud University** واطلب إضافتها إلى حسابك عند الحاجة.

> 🔴 **مهم:** يفضّل استخدام متصفح **Microsoft Edge** والبريد الجامعي لتسهيل عملية التسجيل. لا يمثل ذلك شرطًا حصريًا أو إلزاميًا مثبتًا من Rockwell.

> **عن الصور:** هذه **رسومات إرشادية مبنية على الشاشات المرفقة**، وليست لقطات شاشة حرفية. الإطارات الحمراء تحدد الأزرار والحقول، وقد تتغير هيئة الصفحات مع التحديثات.

<p align="center">
<a href="https://compatibility.rockwellautomation.com/Pages/Downloads.aspx?c=118&amp;pid=50026"><img src="images/arena-download-banner.svg" alt="صفحة التنزيل الرسمية المباشرة" width="95%"/></a>
</p>

<p align="center"><strong><a href="https://compatibility.rockwellautomation.com/Pages/Downloads.aspx?c=118&amp;pid=50026">فتح صفحة تنزيل Arena 17 الرسمية مباشرة</a></strong></p>

> ⚠️ **التنزيل:** قد تتطلب الصفحة تسجيل الدخول. ولا تفترض أن ملف **Arena 17.00.01 Patch** يساوي مثبتًا كاملًا؛ تحقق من نوع الحزمة أولًا.

<h4 align="center" dir="rtl">01 | فتح قائمة الحساب</h4>

<p align="center" dir="rtl">افتح موقع Rockwell Automation باستخدام Microsoft Edge، ثم اختر <strong>Sign In</strong> أو <strong>Create an Account</strong> لإنشاء حساب جديد.</p>

<p align="center"><img src="images/steps/01-open-account.svg" alt="01 | فتح قائمة الحساب" width="95%"/></p>

<h4 align="center" dir="rtl">02 | تسجيل الدخول بالبريد الجامعي</h4>

<p align="center" dir="rtl">أدخل بريدك الجامعي ثم اضغط <strong>Continue</strong>. توصي Rockwell باستخدام البريد الجامعي لتسهيل التحقق، لكنه <strong>توصية وليس شرطًا مطلقًا</strong>.</p>

<p align="center"><img src="images/steps/02-university-email.svg" alt="02 | تسجيل الدخول بالبريد الجامعي" width="95%"/></p>

<h4 align="center" dir="rtl">03 | فتح My Account</h4>

<p align="center" dir="rtl">بعد تسجيل الدخول، افتح <strong>My Account</strong> ثم <strong>Account Profile Dashboard</strong>.</p>

<p align="center"><img src="images/steps/03-my-account.svg" alt="03 | فتح My Account" width="95%"/></p>

<h4 align="center" dir="rtl">04 | إكمال بيانات الحساب</h4>

<p align="center" dir="rtl">من <strong>Profile → Personal Information</strong>، أكمل بيانات الملف الشخصي واحفظها. هذا هو <strong>الشرط الأول</strong>.</p>

<p align="center"><img src="images/steps/04-complete-profile.svg" alt="04 | إكمال بيانات الحساب" width="95%"/></p>

<h4 align="center" dir="rtl">05 | إضافة الجهة التعليمية</h4>

<p align="center" dir="rtl">من <strong>Access → Locations</strong>، اختر <strong>King Saud University</strong> إذا كانت جامعتك، وقدّم <strong>Request Locations</strong> إذا لزم. تأكد من ظهور الاسم والحالة <strong>Approved</strong>. هذا هو <strong>الشرط الثاني</strong>.</p>

<p align="center"><img src="images/steps/05-approved-location.svg" alt="05 | إضافة الجهة التعليمية" width="95%"/></p>

<h4 align="center" dir="rtl">06 | البحث عن Arena</h4>

<p align="center" dir="rtl">ابحث عن <strong>Arena</strong> في موقع الشركة، أو استخدم رابط التحميل المباشر أعلاه.</p>

<p align="center"><img src="images/steps/06-arena-search.svg" alt="06 | البحث عن Arena" width="95%"/></p>

<h4 align="center" dir="rtl">07 | تحديد إصدار Arena 17.00.01</h4>

<p align="center" dir="rtl">حدد الإصدار الصحيح وملف التنزيل ثم <strong>Download Selections</strong>. ملف <strong>Patch</strong> قد يتطلب نسخة أساسية سابقة.</p>

<p align="center"><img src="images/steps/07-arena-17-download.svg" alt="07 | تحديد إصدار Arena 17.00.01" width="95%"/></p>

<h4 align="center" dir="rtl">08 | الموافقة على اتفاقية الترخيص</h4>

<p align="center" dir="rtl">اقرأ الاتفاقية ثم اختر <strong>Accept and Download</strong> إذا كنت موافقًا على شروطها.</p>

<p align="center"><img src="images/steps/08-accept-license.svg" alt="08 | الموافقة على اتفاقية الترخيص" width="95%"/></p>

<h4 align="center" dir="rtl">09 | حفظ مدير التنزيل</h4>

<p align="center" dir="rtl">اختر مكان الحفظ ثم اضغط <strong>Save</strong>، وشغّل مدير التنزيل الرسمي.</p>

<p align="center"><img src="images/steps/09-save-download.svg" alt="09 | حفظ مدير التنزيل" width="95%"/></p>

<h4 align="center" dir="rtl">10 | الوصول إلى C:\RA</h4>

<p align="center" dir="rtl">افتح <strong>C:\RA</strong> بعد اكتمال التنزيل، وافتح مجلد الإصدار المناسب. فك الضغط عن ZIP إذا كان الملف مضغوطًا.</p>

<p align="center"><img src="images/steps/10-drive-ra.svg" alt="10 | الوصول إلى C:\RA" width="95%"/></p>

<h4 align="center" dir="rtl">11 | فتح MediaImage</h4>

<p align="center" dir="rtl">افتح مجلد <strong>MediaImage</strong> داخل الملفات المستخرجة.</p>

<p align="center"><img src="images/steps/11-mediaimage.svg" alt="11 | فتح MediaImage" width="95%"/></p>

<h4 align="center" dir="rtl">12 | تشغيل autorun.exe</h4>

<p align="center" dir="rtl">اختر <strong>autorun</strong> من نوع <strong>Application</strong> وليس <strong>Setup Information</strong>، ثم <strong>Run as administrator</strong>.</p>

<p align="center"><img src="images/steps/12-autorun.svg" alt="12 | تشغيل autorun.exe" width="95%"/></p>

<h4 align="center" dir="rtl">13 | تثبيت Arena</h4>

<p align="center" dir="rtl">من نافذة <strong>Arena 2026</strong> اختر <strong>Install Arena</strong> واتبع التعليمات، ثم اختبر النموذج.</p>

<p align="center"><img src="images/steps/13-install-arena.svg" alt="13 | تثبيت Arena" width="95%"/></p>

> 🔴 **حماية البيانات:** لا تنشر البريد الجامعي الكامل أو رقم الترخيص أو رقم الهاتف أو معرف الحساب/المنشأة في صور مستودع عام.

**المصادر:** [Rockwell: شروط الحساب والتنزيل](https://www.rockwellautomation.com/en-us/products/software/arena-simulation/buying-options/download.html) | [فيديو الشرح المرجعي](https://youtu.be/apJPCLteJ0A?si=fJQ-PgGWp7WWCs_q).

### أ. التحميل من الشركة المصنّعة

1. افتح [صفحة تحميل Arena من Rockwell Automation](https://www.rockwellautomation.com/en-us/products/software/arena-simulation/buying-options/download.html).
2. سجّل الدخول أو أنشئ حساب Rockwell وفق التعليمات الظاهرة.
3. أكمل بيانات الجامعة أو جهة العمل عند الطلب.
4. استخدم زر **Download** أو بوابة [Product Compatibility and Download Center](https://compatibility.rockwellautomation.com/) وابحث عن Arena.
5. تأكد من **رقم الإصدار المراد تثبيته** قبل التنزيل. لا تُفترض إتاحة إصدار 17 في رابط التحميل لمجرد امتلاكه على جهاز آخر.
6. شغّل Download Manager إذا تطلّب تنزيل الملفات ذلك؛ قد تُحفظ في `C:\RA` بحسب إرشادات Rockwell.
7. انتظر اكتمال التنزيل محليًا وتحقق من المجلد.

<div align="center" dir="rtl">

### ب. تثبيت الملفات

</div>

1. افتح مجلد التنزيل (غالبًا `C:\RA`).
2. **استخرج ملفات الأرشيف بالكامل** إلى مجلد فعلي. لا تشغّل المثبت من داخل ZIP.
3. افتح المجلد `MediaImage`.
4. انقر بزر الفأرة الأيمن على `AutoRun.exe` ثم **Run as administrator**.
5. اختر **Install Arena** واتبع الشاشة ووافق على شروط الترخيص الرسمية.
6. اختر مكان التثبيت إذا طلبه البرنامج.
7. **أدخل الترخيص الخاص بك أو خيار نسخة الطالب حسب تعليمات Rockwell**؛ لا تستخدم أرقامًا غير مرخصة.
8. عند الانتهاء، أعد تشغيل الجهاز **إذا طلب التثبيت ذلك**.

<div align="center" dir="rtl">

> تختلف تفاصيل المثبت حسب النسخة. لا تستخدم ملفات EXE المجهولة الموجودة في مستودعات GitHub باعتبارها بديلًا عن ملفات Arena الرسمية.

</div>

<div align="center" dir="rtl">

### ج. ترخيص الطالب والترخيص المؤسسي

</div>

- **Student**: توضح [Rockwell FAQ](https://www.rockwellautomation.com/en-us/products/software/arena-simulation/support/frequently-asked-questions.html) أن كلمة `STUDENT` يمكن إدخالها عندما يطلب مثبت نسخة الطالب رقمًا تسلسليًا، مع تطبيق حدود النموذج الأكاديمي وفق النسخة.
- **ترخيص الجامعة أو الشركة**: استخدم بيانات الترخيص التي منحتها الجهة. قد يلزم **FactoryTalk Activation Manager** مع تراخيص المؤسسات. راجع التعليمات المتاحة داخل مثبت Arena.
- ظهور واجهة Arena وحده ليس دليلًا على أن الترخيص نشط.

<div align="center" dir="rtl">

## 9. فحص الترخيص وتشغيل نموذج تجريبي

</div>

<div align="center" dir="rtl">

بعد التثبيت:

</div>

1. افتح Arena.
2. افتح `File > New` أو استخدم `Ctrl + N` لإنشاء نموذج جديد.
3. تحقق من ظهور لوحة **Basic Process**. طريقة إظهار اللوحة قد تختلف باختلاف نسخة Arena؛ استخدم خيار Attach/Template Panel من قوائم Arena إذا كان متاحًا.
4. ضع **Create** ثم **Process** ثم **Dispose** على مساحة النموذج.
5. صِل الوحدات في اتجاه تدفق الكيانات.
6. افتح إعدادات Process واضبط نشاطًا بسيطًا. تحقّق من صحة مداخل الوحدات ثم احفظ النموذج.
7. جرّب أمر **Run / Go** وفق واجهة نسختك.
8. إذا اشتغلت المحاكاة دون أخطاء، فهذا اختبار عملي أولي على أن الوظائف الأساسية تعمل.

<div align="center" dir="rtl">

إذا كانت أدوات النمذجة رمادية اللون، انتقل للخطوة التالية.

</div>

<div align="center" dir="rtl">

## 10. حل مشكلة الأدوات والقوائم غير المفعلة

</div>

<div align="center" dir="rtl">

اتبع هذا التسلسل **دون حذف Arena في البداية**:

</div>

| الحالة | الإجراء الأول |
| :---: | :---: |
| الصفحة فارغة أو الأدوات رمادية | افتح نموذجًا جديدًا `File > New` |
| البرنامج في وضع تشغيل محاكاة | أوقف/أنهِ التشغيل ثم أعد محاولة التحرير |
| لوحة Basic Process لا تظهر | افحص عرض لوحات القوالب وإرفاق Basic Process |
| البرنامج يعمل لكن بعض الوظائف محجوبة | افحص فئة الترخيص وحالة FactoryTalk Activation عند استخدامه |
| رسائل عن DLL أو Runtime | افحص نسخة Visual C++ المناسبة عبر الطريقة الثانية |
| رسالة عن .NET | افحص `Release` ثم ثبّت Runtime المطلوب فقط |
| خلل في تقارير Excel | افحص Office وتوافقه |
| تثبيت غير مكتمل أو رسائل Installer | جرّب Repair إن كان متاحًا، ثم إعادة التثبيت رسميًا بعد حفظ المشاريع |
| مشكلة مستمرة خاصة بـ Arena 17 | تحقق من متطلبات الإصدار الفرعية واطلب إرشادات Rockwell مع نص رسالة الخطأ |

<div align="center" dir="rtl">

### ماذا تُرسل إلى الدعم عند استمرار المشكلة؟

</div>

- رقم Arena الدقيق كما يظهر في About.
- إصدار Windows ورقم البناء ومعمارية التطبيق.
- هل يتم فتح `File > New` بنجاح؟
- صورة الشاشة الكاملة للأدوات المعطلة.
- نص رسالة الخطأ (إن ظهرت).
- قائمة Visual C++ الصادرة من أمر PowerShell البديل (الأسماء والإصدارات فقط).

<div align="center" dir="rtl">

**الخصوصية:** لا تنشر رقم الترخيص أو معلومات حسابك أو لقطات تحتوي على بيانات شخصية في Issue عام.

</div>

<div align="center" dir="rtl">

## 11. الأسئلة الشائعة والمراجع

</div>

<div align="center" dir="rtl">

### لماذا أمر WMIC لا يعمل؟

</div>

<div align="center" dir="rtl">

لأنه أداة قديمة أزالتها Microsoft من إصدارات Windows 11 المدعومة في 2026. استخدم أمر PowerShell من CMD في القسم الخامس. لا تحتاج إلى إعادة تثبيت WMIC.

</div>

<div align="center" dir="rtl">

### هل يجب تثبيت جميع الإصدارات القديمة من Visual C++؟

</div>

<div align="center" dir="rtl">

لا. ثبّت الحزم التي تتطلبها نسخة Arena أو التي يحددها سجل الخطأ. إصدارات x86 وx64 مختلفة، ولا يصح حذف الحزم القديمة دون سبب.

</div>

<div align="center" dir="rtl">

### هل برنامج Office 64-bit ضروري؟

</div>

<div align="center" dir="rtl">

لا يوجد أساس لتعميم هذا الشرط على جميع إصدارات Arena. اقرأ متطلبات النسخة لديك.

</div>

<div align="center" dir="rtl">

### هل تثبيت SQL Server Compact 4.0 آمن وضروري؟

</div>

<div align="center" dir="rtl">

هو منتج انتهى دعمه؛ لا تنصّبه إلا عند إثبات الحاجة ومع فهم المخاطر.

</div>

<div align="center" dir="rtl">

### هل هذه وثيقة رسمية لإصدار Arena 17؟

</div>

<div align="center" dir="rtl">

لا. هو **دليل عربي مستقل** يلخّص خطوات فحص Windows وتثبيت البرنامج الرسمي. بعض متطلبات Rockwell المنشورة تشير إلى 16.20.02، لذلك يجب التحقق من وثائق Arena 17 إذا كان هذا الإصدار هو المطلوب.

</div>

<div align="center" dir="rtl">

### المصادر (روابط مباشرة)

</div>

1. [Rockwell Automation — تنزيل Arena](https://www.rockwellautomation.com/en-us/products/software/arena-simulation/buying-options/download.html)
2. [Rockwell Automation — متطلبات النظام وخطوات التثبيت](https://www.rockwellautomation.com/en-us/products/software/arena-simulation/support/system-requirements.html)
3. [Rockwell Automation — الأسئلة الشائعة والتراخيص](https://www.rockwellautomation.com/en-us/products/software/arena-simulation/support/frequently-asked-questions.html)
4. [Microsoft — إصدارات Visual C++ Redistributable](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist)
5. [Microsoft — إزالة WMIC من Windows](https://support.microsoft.com/en-us/servicing/os/windows/docs/2025/09/windows-management-instrumentation-command-line-wmic-removal-from-windows)
6. [Microsoft — فحص إصدارات .NET Framework](https://learn.microsoft.com/en-us/dotnet/framework/install/how-to-determine-which-versions-are-installed)
7. [Microsoft — .NET Framework 4.8.1 Runtime](https://dotnet.microsoft.com/en-us/download/dotnet-framework/net481)
8. [Microsoft — SQL Server Compact 4.0 SP1](https://www.microsoft.com/en-us/download/details.aspx?id=30709)
9. [Microsoft — دورة حياة SQL Server Compact 4.0](https://learn.microsoft.com/en-us/lifecycle/products/microsoft-sql-server-compact-40)

<div align="center" dir="rtl">

### أصل الفكرة

</div>

<div align="center" dir="rtl">

استُلهم نطاق الفحص الأولي من مستودع [M02lsayed/Arena](https://github.com/M02lsayed/Arena/blob/main/README.md)، لكن **هذه صياغة عربية مستقلة** أُعيدت كتابتها مع روابط رسمية وملاحظات تصحيحية. المستودع المرجعي تابع لطرف ثالث وليس موردًا رسميًا من Rockwell Automation.

</div>

---

<div align="center" dir="rtl">

**ملاحظة عن نواتج الأوامر:** كل قسم **Output** في هذا الدليل مثال تعليمي على الشكل المحتمل للنتيجة، ولا يعتمد على فحص تلقائي لجهاز القارئ. لا تنشر بيانات حساسة من سجل النظام أو الحساب عند طلب المساعدة.

</div>

<div align="center" dir="rtl">

**ملاحظة المسؤولية:** الأوامر هنا للفحص، ولا تعدّل سجل Windows أو تزيل البرامج. تثبيت أي مكوّن قرار منفصل بعد مطابقة المتطلبات والمصدر الرسمي.

</div>
