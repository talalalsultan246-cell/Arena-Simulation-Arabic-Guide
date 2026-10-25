# دليل تثبيت وتشخيص Arena Simulation بالعربية

> **آخر مراجعة للمصادر: 25 أكتوبر 2026**  
> دليل مستقل باللغة العربية، موجّه لطلاب المحاكاة ومستخدمي **Arena 17** والإصدارات الأخرى. يعتمد على تعليمات الشركة المصنّعة ومراجع Microsoft، ولا يُعدّ وثيقة رسمية من Rockwell Automation.

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

---

## 1. قبل البدء

الغرض من هذا الدليل **التحقق أولًا، ثم تنزيل وتثبيت الناقص فقط**. إذا كان Arena يفتح ولكن أدوات Create وProcess وDispose أو القوائم تظهر باللون الرمادي (Disabled)، **لا تبدأ بإلغاء تثبيته**؛ فالمشكلة قد تكون في عدم فتح نموذج أو وضع التشغيل أو الترخيص أو مكوّنات النظام.

- احفظ نسخًا احتياطية من نماذجك (`.doe` وأي ملفات مشروع مرتبطة بها).
- استخدم روابط Microsoft وRockwell الرسمية؛ لا تشغّل ملفات `.exe` مجهولة المصدر من مستودعات خارجية.
- افتح نافذة الأوامر عبر **Start > CMD > Run as administrator** عند الحاجة إلى الصلاحيات، لكن أوامر القراءة أدناه لا تحتاج غالبًا إلى تشغيل المدير.
- أوامر `cmd` توضع في Command Prompt، وأوامر `powershell` توضع في Windows PowerShell. يمكن أيضًا تنفيذ الأمر البديل المحدد من نافذة CMD.
- وجود حزمة مثبتة **لا يثبت وحده** أنها سبب العطل أو أن إصدارها مناسب لكل نسخة Arena.
- افحص معمارية برنامج Arena نفسه (`x86` أو `x64`)، فهي ليست بالضرورة مطابقة لمعمارية Office أو Windows.

### روابط التنزيل الرسمية المختصرة

| البرنامج | المصدر الرسمي | متى أحتاجه؟ |
|---|---|---|
| Arena Simulation | [Rockwell Automation: تنزيل Arena](https://www.rockwellautomation.com/en-us/products/software/arena-simulation/buying-options/download.html) | تنزيل البرنامج أو إعادة تثبيته بعد التشخيص |
| .NET Framework 4.8.1 Runtime | [Microsoft: .NET Framework 4.8.1](https://dotnet.microsoft.com/en-us/download/dotnet-framework/net481) | إذا تطلّبه Arena وكانت النسخة المثبتة أقدم وكانت 4.8.1 متوافقة مع Windows |
| Visual C++ Redistributable x64 | [Microsoft: تنزيل مباشر x64](https://aka.ms/vc14/vc_redist.x64.exe) | للتطبيقات ذات معمارية 64-bit التي تحتاج مكتبات v14 |
| Visual C++ Redistributable x86 | [Microsoft: تنزيل مباشر x86](https://aka.ms/vc14/vc_redist.x86.exe) | للتطبيقات ذات معمارية 32-bit التي تحتاج مكتبات v14، حتى على Windows 64-bit |
| Visual C++ الإصدارات القديمة | [Microsoft: جميع الإصدارات المدعومة والقديمة](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist) | عند إثبات احتياج إصدار أقدم محدد |
| SQL Server Compact 4.0 SP1 | [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=30709) | **اختياري** فقط عند ثبوت الحاجة |
| Microsoft Office | [Microsoft 365](https://www.microsoft.com/microsoft-365) | إذا كانت ميزات تقارير Excel مطلوبة ولم يكن Office موجودًا |

> **تنبيه دقة:** تعرض [صفحة متطلبات Rockwell الرسمية](https://www.rockwellautomation.com/en-us/products/software/arena-simulation/support/system-requirements.html) بيانات لإصدار **16.20.02**. لا يُفترض تلقائيًا أن تفاصيل الصفحة تنطبق بالكامل على **Arena 17**. راجع ملف المتطلبات المرفق مع نسختك إذا اختلفت الأرقام.

## 2. الحد الأدنى للمواصفات

بحسب صفحة Rockwell المتاحة لإصدار 16.20.02:

| العنصر | الحد الأدنى في صفحة Rockwell | الموصى به |
|---|---|---|
| RAM | 8 GB | 16 GB |
| مساحة القرص الحرة | 2 GB | 4 GB |
| المعالج | Intel ثنائي النواة، 3 GHz | بحسب تعقيد النموذج |
| نظام التشغيل | Windows 10 / 11 Pro أو Enterprise بحسب قائمة دعم Rockwell | نظام تدعمه النسخة المستهدفة |
| Microsoft Office | يُستخدم لعرض تقارير إحصاءات Excel | تحقق من التوافق |
| صلاحيات التثبيت | صلاحيات Administrator | مطلوبة للتثبيت |

**لا تعتمد رقم 4GB RAM الموجود في الدليل القديم كحد أدنى موثّق حاليًا من Rockwell.** ولا تَعُدّ الدعم الرسمي لنظام Windows أو Arena 17 مؤكدًا إلا بعد مراجعة وثائق نسختك.

## 3. فحص Windows والذاكرة والمساحة

### معرفة إصدار Windows

افتح CMD:

```cmd
winver
```

أو:

```cmd
ver
```

لمعلومات أوسع: اضغط `Win + R`، واكتب `msinfo32`. ستجد `OS Name` و`System Type` و`Installed Physical Memory`.

### قياس الذاكرة RAM بواسطة CMD

```cmd
powershell -NoProfile -Command "Get-CimInstance Win32_ComputerSystem | Select-Object @{N='RAM_GB';E={[math]::Round($_.TotalPhysicalMemory/1GB,2)}}"
```

### قياس المساحة الحرة على القرص C:

```cmd
powershell -NoProfile -Command "Get-PSDrive C | Select-Object Name,@{N='Free_GB';E={[math]::Round($_.Free/1GB,2)}}"
```

**التفسير:** إذا أظهر الحاسوب 8GB RAM ومساحة كافية، فهذا اجتياز أولي للمواصفات المذكورة، لكنه لا يثبت صلاحية الترخيص أو التوافق الكامل لإصدار Arena 17.

## 4. فحص وتثبيت .NET Framework

### الأمر الأول (CMD)

```cmd
reg query "HKLM\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full" /v Release
```

### الأمر البديل (PowerShell)

```powershell
(Get-ItemProperty 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full').Release
```

### تفسير أشهر قيم Release

| القيمة | نسخة .NET Framework |
|---|---|
| 528040 أو 528049 أو 528372 أو 528449 | 4.8 (تختلف قيمة التسجيل بحسب Windows) |
| 533320 أو 533325 أو 533509 | 4.8.1 |

توجد قيم أخرى بحسب إصدار Windows. الرقم **528040 أو أعلى** يدل عادة على وجود .NET Framework 4.8 أو إصدار أحدث ضمن سلسلة 4.x. المرجع: [Microsoft: كيفية التعرف إلى الإصدارات المثبتة](https://learn.microsoft.com/en-us/dotnet/framework/install/how-to-determine-which-versions-are-installed).

**عند الحاجة للتثبيت:**

1. ادخل [صفحة Microsoft الرسمية لـ .NET Framework 4.8.1](https://dotnet.microsoft.com/en-us/download/dotnet-framework/net481).
2. اختر **Runtime** لتشغيل البرامج؛ ليس **Developer Pack**.
3. تأكد من توافق النسخة مع Windows عندك.
4. نفّذ مثبت Microsoft الرسمي وأعد تشغيل الجهاز **إذا طُلب منك ذلك**.
5. كرّر أمر قراءة `Release` للتحقق.

لا تثبّت .NET 4.8.1 إذا كان Windows يحتوي عليه بالفعل.

## 5. فحص جميع إصدارات Microsoft Visual C++

هذه أكثر خطوة احتاجت إلى تحديث في المستودع المرجعي.

### الطريقة الأولى: أمر المستودع القديم باستخدام WMIC

```cmd
wmic product where "name like '%%Visual C++%%'" get name,version
```

**مهم:** هذه الصيغة من دليل GitHub الأصلي، وهي **قديمة وغير موصى بها**؛ وقد تفشل برسالة `'wmic' is not recognized` على Windows 11 الحديث. أعلنت Microsoft إزالة أداة WMIC من Windows 11 المدعوم في 2026. كذلك فحص `Win32_Product` قد يكون بطيئًا ويُسبّب عمليات فحص اتساق لحزم MSI، ولا يضمن إظهار جميع الحزم.

**إذا لم يعمل الأمر الأول، انتقل مباشرةً إلى الطريقة الثانية؛ لا تحتاج إلى إعادة تثبيت WMIC.**

### الطريقة الثانية: أمر بديل يعمل داخل CMD ويُظهر الأسماء والإصدارات

انسخ **السطر كاملًا** في نافذة CMD:

```cmd
powershell -NoProfile -Command "Get-ItemProperty 'HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall\*','HKLM:\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\*' -ErrorAction SilentlyContinue | Where-Object { $_.DisplayName -like '*Microsoft Visual C++*' } | Sort-Object DisplayName,DisplayVersion | Select-Object DisplayName,DisplayVersion | Format-Table -AutoSize"
```

**هذا هو البديل الموصى به في الدليل.** يقرأ بيانات البرامج المسجلة في مساري Uninstall ذوي المعماريتين. سيعرض عمودين:

- `DisplayName`: اسم الحزمة، وغالبًا يظهر فيه x86 أو x64.
- `DisplayVersion`: رقم الإصدار المثبت.

ملاحظة: قد توجد حزم غير مسجلة في هذه المفاتيح، لذا لا يُعدّ الأمر فحصًا جنائيًا شاملًا لكل ملف DLL في النظام.

### الطريقة الثالثة: تنفيذ الأمر مباشرة داخل PowerShell

إذا أردت استخدام PowerShell بدل CMD:

```powershell
Get-ItemProperty 'HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall\*','HKLM:\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\*' -ErrorAction SilentlyContinue |
  Where-Object { $_.DisplayName -like '*Microsoft Visual C++*' } |
  Sort-Object DisplayName, DisplayVersion |
  Select-Object DisplayName, DisplayVersion |
  Format-Table -AutoSize
```

### الطريقة الرابعة: واجهة Windows

`Settings > Apps > Installed apps` ثم ابحث عن `Microsoft Visual C++`. تظهر النتائج حسب البرامج المسجلة في النظام.

### تنزيل حزم Microsoft عند الحاجة فقط

1. راجع معمارية **Arena** المطلوبة: x86 أو x64.
2. افتح [صفحة Microsoft للإصدارات المدعومة](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist).
3. للحزم الحديثة المتوافقة مع v14: [x86](https://aka.ms/vc14/vc_redist.x86.exe) أو [x64](https://aka.ms/vc14/vc_redist.x64.exe).
4. إذا ظهرت نافذة **Install / Repair / Uninstall** وكانت الحزمة نفسها مثبتة، جرّب **Repair** عندما توجد أدلة على فسادها، بدل حذفها عشوائيًا.
5. لا تحذف حزم 2008/2010/2012/2013 لمجرد أنها قديمة؛ قد تستخدمها برامج أخرى، وهي تُثبّت جنبًا إلى جنب مع الحزم الأحدث.
6. أعد تشغيل Windows إذا طلب المثبت، ثم افحص الإصدارات مجددًا.

**تنبيه:** تثبيت نسخة x64 وحدها لا يغطي جميع تطبيقات x86. وفي المقابل، ليس كل برنامج Arena بحاجة إلى جميع إصدارات Visual C++ المذكورة.

مراجع: [Microsoft VC++ downloads](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist) | [Microsoft WMIC removal](https://support.microsoft.com/en-us/servicing/os/windows/docs/2025/09/windows-management-instrumentation-command-line-wmic-removal-from-windows).

## 6. فحص SQL Server Compact 4.0

ورد هذا المكوّن في الدليل الأصلي، **لكن لم يثبت أنه متطلب لازم لجميع تثبيتات Arena 17**.

### فحص مسار السجل الأساسي باستخدام CMD

```cmd
reg query "HKLM\SOFTWARE\Microsoft\Microsoft SQL Server Compact Edition\v4.0" /v Version
```

### فحص مسار السجل الثاني عند استخدام Windows 64-bit

```cmd
reg query "HKLM\SOFTWARE\WOW6432Node\Microsoft\Microsoft SQL Server Compact Edition\v4.0" /v Version
```

إذا ظهرت `ERROR: The system was unable to find the specified registry key or value.`، فالمعنى أن المفتاح غير موجود في **المسار المحدد**؛ وليس بالضرورة أن المكوّن غير موجود بأي صورة.

### عند إثبات الحاجة إليه

1. افتح [صفحة SQL Server Compact 4.0 SP1 على Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=30709).
2. اختر `SSCERuntime_x86-ENU.exe` أو `SSCERuntime_x64-ENU.exe` وفق المتطلب الفعلي.
3. شغّل المثبت الرسمي وتحقق من النتائج.
4. **تحذير أمني:** انتهى دعم SQL Server Compact 4.0 الممتد في **14 يوليو 2021**؛ لا توصي هذه الصفحة بتثبيته افتراضيًا على جهاز حديث. راجع [سجل دورة الحياة الرسمي](https://learn.microsoft.com/en-us/lifecycle/products/microsoft-sql-server-compact-40).

## 7. فحص Office

افتح **Excel > File > Account > About Excel** وتحقق من المعمارية والإصدار.

يمكن فحص نظام Click-to-Run عبر CMD:

```cmd
reg query "HKLM\SOFTWARE\Microsoft\Office\ClickToRun\Configuration" /v Platform
```

القيمتان المحتملتان: `x86` و`x64`. إذا لم يظهر المفتاح، قد يكون Office مثبتًا بطريقة أخرى؛ هذا الأمر وحده لا يكفي للحكم.

**تصحيح مهم للدليل الأصلي:** Office **ليس ملزمًا بأن يكون 64-bit في جميع تثبيتات Arena**. راجع متطلبات Rockwell والإصدار المستهدف. لا تُزِل Office أو تغيّر معماريته دون سبب محدد.

## 8. تحميل Arena وتثبيته رسميًا

### أ. التحميل من الشركة المصنّعة

1. افتح [صفحة تحميل Arena من Rockwell Automation](https://www.rockwellautomation.com/en-us/products/software/arena-simulation/buying-options/download.html).
2. سجّل الدخول أو أنشئ حساب Rockwell وفق التعليمات الظاهرة.
3. أكمل بيانات الجامعة أو جهة العمل عند الطلب.
4. استخدم زر **Download** أو بوابة [Product Compatibility and Download Center](https://compatibility.rockwellautomation.com/) وابحث عن Arena.
5. تأكد من **رقم الإصدار المراد تثبيته** قبل التنزيل. لا تُفترض إتاحة إصدار 17 في رابط التحميل لمجرد امتلاكه على جهاز آخر.
6. شغّل Download Manager إذا تطلّب تنزيل الملفات ذلك؛ قد تُحفظ في `C:\RA` بحسب إرشادات Rockwell.
7. انتظر اكتمال التنزيل محليًا وتحقق من المجلد.

### ب. تثبيت الملفات

1. افتح مجلد التنزيل (غالبًا `C:\RA`).
2. **استخرج ملفات الأرشيف بالكامل** إلى مجلد فعلي. لا تشغّل المثبت من داخل ZIP.
3. افتح المجلد `MediaImage`.
4. انقر بزر الفأرة الأيمن على `AutoRun.exe` ثم **Run as administrator**.
5. اختر **Install Arena** واتبع الشاشة ووافق على شروط الترخيص الرسمية.
6. اختر مكان التثبيت إذا طلبه البرنامج.
7. **أدخل الترخيص الخاص بك أو خيار نسخة الطالب حسب تعليمات Rockwell**؛ لا تستخدم أرقامًا غير مرخصة.
8. عند الانتهاء، أعد تشغيل الجهاز **إذا طلب التثبيت ذلك**.

> تختلف تفاصيل المثبت حسب النسخة. لا تستخدم ملفات EXE المجهولة الموجودة في مستودعات GitHub باعتبارها بديلًا عن ملفات Arena الرسمية.

### ج. ترخيص الطالب والترخيص المؤسسي

- **Student**: توضح [Rockwell FAQ](https://www.rockwellautomation.com/en-us/products/software/arena-simulation/support/frequently-asked-questions.html) أن كلمة `STUDENT` يمكن إدخالها عندما يطلب مثبت نسخة الطالب رقمًا تسلسليًا، مع تطبيق حدود النموذج الأكاديمي وفق النسخة.
- **ترخيص الجامعة أو الشركة**: استخدم بيانات الترخيص التي منحتها الجهة. قد يلزم **FactoryTalk Activation Manager** مع تراخيص المؤسسات. راجع التعليمات المتاحة داخل مثبت Arena.
- ظهور واجهة Arena وحده ليس دليلًا على أن الترخيص نشط.

## 9. فحص الترخيص وتشغيل نموذج تجريبي

بعد التثبيت:

1. افتح Arena.
2. افتح `File > New` أو استخدم `Ctrl + N` لإنشاء نموذج جديد.
3. تحقق من ظهور لوحة **Basic Process**. طريقة إظهار اللوحة قد تختلف باختلاف نسخة Arena؛ استخدم خيار Attach/Template Panel من قوائم Arena إذا كان متاحًا.
4. ضع **Create** ثم **Process** ثم **Dispose** على مساحة النموذج.
5. صِل الوحدات في اتجاه تدفق الكيانات.
6. افتح إعدادات Process واضبط نشاطًا بسيطًا. تحقّق من صحة مداخل الوحدات ثم احفظ النموذج.
7. جرّب أمر **Run / Go** وفق واجهة نسختك.
8. إذا اشتغلت المحاكاة دون أخطاء، فهذا اختبار عملي أولي على أن الوظائف الأساسية تعمل.

إذا كانت أدوات النمذجة رمادية اللون، انتقل للخطوة التالية.

## 10. حل مشكلة الأدوات والقوائم غير المفعلة

اتبع هذا التسلسل **دون حذف Arena في البداية**:

| الحالة | الإجراء الأول |
|---|---|
| الصفحة فارغة أو الأدوات رمادية | افتح نموذجًا جديدًا `File > New` |
| البرنامج في وضع تشغيل محاكاة | أوقف/أنهِ التشغيل ثم أعد محاولة التحرير |
| لوحة Basic Process لا تظهر | افحص عرض لوحات القوالب وإرفاق Basic Process |
| البرنامج يعمل لكن بعض الوظائف محجوبة | افحص فئة الترخيص وحالة FactoryTalk Activation عند استخدامه |
| رسائل عن DLL أو Runtime | افحص نسخة Visual C++ المناسبة عبر الطريقة الثانية |
| رسالة عن .NET | افحص `Release` ثم ثبّت Runtime المطلوب فقط |
| خلل في تقارير Excel | افحص Office وتوافقه |
| تثبيت غير مكتمل أو رسائل Installer | جرّب Repair إن كان متاحًا، ثم إعادة التثبيت رسميًا بعد حفظ المشاريع |
| مشكلة مستمرة خاصة بـ Arena 17 | تحقق من متطلبات الإصدار الفرعية واطلب إرشادات Rockwell مع نص رسالة الخطأ |

### ماذا تُرسل إلى الدعم عند استمرار المشكلة؟

- رقم Arena الدقيق كما يظهر في About.
- إصدار Windows ورقم البناء ومعمارية التطبيق.
- هل يتم فتح `File > New` بنجاح؟
- صورة الشاشة الكاملة للأدوات المعطلة.
- نص رسالة الخطأ (إن ظهرت).
- قائمة Visual C++ الصادرة من أمر PowerShell البديل (الأسماء والإصدارات فقط).

**الخصوصية:** لا تنشر رقم الترخيص أو معلومات حسابك أو لقطات تحتوي على بيانات شخصية في Issue عام.

## 11. الأسئلة الشائعة والمراجع

### لماذا أمر WMIC لا يعمل؟

لأنه أداة قديمة أزالتها Microsoft من إصدارات Windows 11 المدعومة في 2026. استخدم أمر PowerShell من CMD في القسم الخامس. لا تحتاج إلى إعادة تثبيت WMIC.

### هل يجب تثبيت جميع الإصدارات القديمة من Visual C++؟

لا. ثبّت الحزم التي تتطلبها نسخة Arena أو التي يحددها سجل الخطأ. إصدارات x86 وx64 مختلفة، ولا يصح حذف الحزم القديمة دون سبب.

### هل برنامج Office 64-bit ضروري؟

لا يوجد أساس لتعميم هذا الشرط على جميع إصدارات Arena. اقرأ متطلبات النسخة لديك.

### هل تثبيت SQL Server Compact 4.0 آمن وضروري؟

هو منتج انتهى دعمه؛ لا تنصّبه إلا عند إثبات الحاجة ومع فهم المخاطر.

### هل هذه وثيقة رسمية لإصدار Arena 17؟

لا. هو **دليل عربي مستقل** يلخّص خطوات فحص Windows وتثبيت البرنامج الرسمي. بعض متطلبات Rockwell المنشورة تشير إلى 16.20.02، لذلك يجب التحقق من وثائق Arena 17 إذا كان هذا الإصدار هو المطلوب.

### المصادر (روابط مباشرة)

1. [Rockwell Automation — تنزيل Arena](https://www.rockwellautomation.com/en-us/products/software/arena-simulation/buying-options/download.html)
2. [Rockwell Automation — متطلبات النظام وخطوات التثبيت](https://www.rockwellautomation.com/en-us/products/software/arena-simulation/support/system-requirements.html)
3. [Rockwell Automation — الأسئلة الشائعة والتراخيص](https://www.rockwellautomation.com/en-us/products/software/arena-simulation/support/frequently-asked-questions.html)
4. [Microsoft — إصدارات Visual C++ Redistributable](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist)
5. [Microsoft — إزالة WMIC من Windows](https://support.microsoft.com/en-us/servicing/os/windows/docs/2025/09/windows-management-instrumentation-command-line-wmic-removal-from-windows)
6. [Microsoft — فحص إصدارات .NET Framework](https://learn.microsoft.com/en-us/dotnet/framework/install/how-to-determine-which-versions-are-installed)
7. [Microsoft — .NET Framework 4.8.1 Runtime](https://dotnet.microsoft.com/en-us/download/dotnet-framework/net481)
8. [Microsoft — SQL Server Compact 4.0 SP1](https://www.microsoft.com/en-us/download/details.aspx?id=30709)
9. [Microsoft — دورة حياة SQL Server Compact 4.0](https://learn.microsoft.com/en-us/lifecycle/products/microsoft-sql-server-compact-40)

### أصل الفكرة

استُلهم نطاق الفحص الأولي من مستودع [M02lsayed/Arena](https://github.com/M02lsayed/Arena/blob/main/README.md)، لكن **هذه صياغة عربية مستقلة** أُعيدت كتابتها مع روابط رسمية وملاحظات تصحيحية. المستودع المرجعي تابع لطرف ثالث وليس موردًا رسميًا من Rockwell Automation.

---

**ملاحظة المسؤولية:** الأوامر هنا للفحص، ولا تعدّل سجل Windows أو تزيل البرامج. تثبيت أي مكوّن قرار منفصل بعد مطابقة المتطلبات والمصدر الرسمي.