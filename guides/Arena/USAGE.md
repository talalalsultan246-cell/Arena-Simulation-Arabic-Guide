<div dir="rtl" align="right">

# دليل استخدام Arena Simulation

**إعداد:** Talal bin Ibrahim Alsultan  
**آخر تحديث:** 27 أكتوبر 2026  
**الإصدار المستهدف:** Arena 17 بواجهة الشريط الحديث **Home · Animate · Draw · Run · View · Tools**.  

> هذا **دليل استخدام** مستقل عن [دليل تحميل وتثبيت Arena](https://github.com/talalalsultan246-cell/Arena-Simulation-Arabic-Guide/blob/main/guides/Arena/README.md).

في محاضرة يوم الأحد **25 أكتوبر 2026**، استعرض **الأستاذ الدكتور محمود الشربيني** واجهات Arena الأساسية وبعض طرق إنشاء نموذج أولي. يربط هذا الدليل بين واجهة **Arena Professional Edition 17** وبين **Call Center Problem = مسألة مركز الاتصالات** الواردة في **Chapter 2: Simulation Examples = الفصل الثاني: أمثلة المحاكاة**. اعتمدت المصطلحات الإنجليزية الأصلية، وأرفقت معناها العربي لتكون سهلة القراءة أثناء تطبيق المثال.

<a id="arena-use-glossary"></a>
## المصطلحات العلمية — English = العربية

هذه المصطلحات مستخدمة في شرائح المقرر وفي إعدادات **Arena**. احتفظ بالاسم الإنجليزي عند إدخال البيانات إلى البرنامج.

| English Term | المعنى باللغة العربية |
|---|---|
| **Call Center** | مركز الاتصالات |
| **Simulation** | المحاكاة |
| **Discrete-Event Simulation** | محاكاة الأحداث المنفصلة |
| **Simulation Model** | نموذج المحاكاة |
| **Caller** | المتصل |
| **Entity** | الكيان الذي يتحرك داخل النموذج |
| **Server** | موظف تقديم الخدمة |
| **Resource** | المورد المستخدم لتقديم الخدمة |
| **Interarrival Time** | الزمن بين وصول مكالمتين متتاليتين |
| **Arrival Time** | وقت وصول المكالمة |
| **Service Time** | وقت الخدمة |
| **Service Start Time** | وقت بدء الخدمة |
| **Service Completion Time** | وقت انتهاء الخدمة |
| **Waiting Time / Caller Delay** | وقت انتظار المتصل |
| **Queue** | طابور الانتظار |
| **Time in System = الوقت داخل النظام** | الوقت الذي تقضيه المكالمة داخل النظام |
| **Service Time Distribution** | التوزيع الاحتمالي لوقت الخدمة |
| **Interarrival Time Distribution** | التوزيع الاحتمالي للزمن بين الوصولات |
| **Probability** | الاحتمال |
| **Cumulative Probability** | الاحتمال التراكمي |
| **Random Number** | رقم عشوائي |
| **Pseudo-Random Number** | رقم شبه عشوائي |
| **Random Variate** | قيمة عشوائية من توزيع احتمالي محدد |
| **Random-Number Generation** | توليد الأرقام العشوائية |
| **Random-Variate Generation** | توليد القيم العشوائية من التوزيعات الاحتمالية |
| **Uniformity** | خاصية التوزيع المنتظم |
| **Independence** | خاصية الاستقلال |
| **CDF: Cumulative Distribution Function** | دالة التوزيع التراكمي |
| **Inverse-Transform Technique** | طريقة التحويل العكسي |
| **Linear Congruential Method (LCM)** | الطريقة التوافقية الخطية |
| **DISC: Discrete Probability Distribution** | تعبير التوزيع الاحتمالي المتقطع في Arena |
| **Create** | إنشاء كيان جديد أو إدخال مكالمة |
| **Process** | تنفيذ عملية الخدمة |
| **Dispose** | إنهاء مسار الكيان وخروجه من النموذج |
| **Seize** | حجز المورد |
| **Delay** | زمن العملية أو تأخيرها |
| **Release** | تحرير المورد |
| **Capacity** | الطاقة الاستيعابية للمورد |
| **Utilization** | نسبة انشغال المورد |
| **Replication** | تكرار تجربة المحاكاة |
| **Replication Length** | مدة تكرار المحاكاة |
| **Simulation Time** | الزمن داخل نموذج المحاكاة |
| **Performance Measures** | مقاييس الأداء |
| **Model Verification** | التحقق من صحة تنفيذ النموذج |
| **Simulation Reports** | تقارير نتائج المحاكاة |

**مثال من المادة (Chapter 2 — Simulation Examples, Slide 1.3):** يوضح جدول **Call Center Problem** مصطلحي **Service Time = وقت الخدمة** و**Interarrival Time = الزمن بين وصول المكالمات**. وتظل الأسماء الإنجليزية كما هي داخل **Arena**.

---

## المحتويات

1. [المصطلحات العلمية English / العربية](#arena-use-glossary)
2. [الصورة العامة ومكونات النافذة](#arena-use-01)
3. [File — فتح وحفظ النموذج](#arena-use-02)
4. [Home — بناء النموذج](#arena-use-03)
5. [Animate — مشاهدة الكيانات](#arena-use-04)
6. [Draw — الرسم](#arena-use-05)
7. [Run — تشغيل المحاكاة](#arena-use-06)
8. [View — طريقة العرض](#arena-use-07)
9. [Tools — أدوات التحليل](#arena-use-08)
10. [Project Bar / Discrete Processing](#arena-use-10)
11. [Call Center: الشرائح والتوزيعات والقوانين](#arena-use-12)
12. [التطبيق خطوة بخطوة](#arena-use-13)
13. [قراءة النتائج](#arena-use-14)
14. [اختصارات مهمة](#arena-use-shortcuts)
15. [المراجع والصور](#arena-use-15)

---

<a id="arena-use-01"></a>
## 1. النافذة الرئيسية: أين أجد الأدوات؟

<div align="center">
<img src="images/01_Home_Arena17.jpg" width="96%" alt="لقطة أصلية توضح الصفحة الرئيسية Home ومساحة بناء النموذج في Arena 17"/>
</div>

**مصدر الصورة:** لقطة أصلية من واجهة **Arena 17 – Training & Evaluation Mode (Student)** على جهاز الطالب، مع ترقيم مواضع الأدوات.

| الموضع | وظيفته |
|---|---|
| **الأعلى: Home/Animate/Draw/Run/View/Tools** | اختيار الأدوات |
| **اليسار: Project Bar = لوحة المشروع** | **Modules = وحدات بناء النموذج** |
| **الوسط: Model Window = نافذة النموذج** | مساحة بناء **Simulation Model = نموذج المحاكاة** |
| **الأسفل: Spreadsheet View = عرض الجداول** | خصائص **Resources = الموارد** و**Modules = الوحدات** |
| **اليمين: Animate Bar** عند ظهوره | عناصر الحركة والمراقبة |
| **أسفل النافذة: Command/Status** | الرسائل وحالة التشغيل |

**قاعدة:** نضع الوحدات في **Model Window** ثم نوصلها بأداة **Connect**. قرب الوحدات من بعضها لا يعني اتصالها.

---

<a id="arena-use-02"></a>
## 2. File — إنشاء النموذج وحفظه

**File → New → Blank Model** لإنشاء ملف جديد، و**Open** لفتح السابق، و**Save / Save As** لحفظه. اسم مقترح: `Call_Center_Aly_Bander.doe`.

---

<a id="arena-use-03"></a>
## 3. Home — بناء النموذج

<div align="center"><img src="images/01_Home_Arena17.jpg" alt="Home: (1) شريط الأدوات، (2) Project Bar، (3) مساحة النموذج، (4) جدول الخصائص، (5) Animate Bar، (6) Connect" width="96%"/></div>

**الصورة الأصلية:** Home: (1) شريط الأدوات، (2) Project Bar، (3) مساحة النموذج، (4) جدول الخصائص، (5) Animate Bar، (6) Connect.

**ما الذي تبحث عنه في صورة Home؟**

- **Attach/Detach:** إظهار اللوحات داخل Project Bar.
- **Select/Zoom/Pan:** التحديد والتكبير والتنقل.
- **Connect:** ربط وحدات النموذج بمسار فعلي.
- **Auto-Connect:** وصل تلقائي عند سحب الوحدة إذا كان الخيار مفعلًا.
- **Check Model / Expression Builder / Manuals:** فحص النموذج والتعبيرات وفتح الأدلة إذا كانت هذه الأوامر ظاهرة.

**جرب:** اسحب `Create` ثم `Process` ثم `Dispose`، واستخدم `Connect` لربطها من اليسار إلى اليمين.

---

<a id="arena-use-04"></a>
## 4. Animate — الحركة أثناء التشغيل

<div align="center"><img src="images/02_Animate_Arena17.jpg" alt="Animate: متابعة الحركة والعدادات وحالة الموارد" width="96%"/></div>

**الصورة الأصلية:** Animate: متابعة الحركة والعدادات وحالة الموارد.

تُستخدم أدوات **Animate = التحريك** لعرض **Entities = الكيانات**، و**Servers = موظفي الخدمة**، و**Queues = طوابير الانتظار** خلال المحاكاة. في **Call Center**، تمثل المكالمة **Entity = كيان**، ويمثل **Aly / Bander** كلا منهما **Server / Resource = موظف خدمة / مورد**.

**ملاحظة:** تساعد **Animation = الحركة** في **Model Verification = التحقق من صحة تنفيذ النموذج**. أما **Average Caller Delay = متوسط وقت انتظار المتصل** فيُستخرج من **Simulation Reports = تقارير المحاكاة**.

---

<a id="arena-use-05"></a>
## 5. Draw — إضافة الرسم والعناوين

<div align="center"><img src="images/03_Draw_Arena17.jpg" alt="Draw: كتابة النصوص ورسم الأشكال التوضيحية" width="96%"/></div>

**الصورة الأصلية:** Draw: كتابة النصوص ورسم الأشكال التوضيحية.

استخدم **Text** لعنوان النموذج، و**Line / Rectangle / Ellipse** لتوضيح الأقسام. **Draw Line ليس Connect**؛ الأول للرسم، والثاني لمسار الكيانات الفعلي.

---

<a id="arena-use-06"></a>
## 6. Run — تشغيل المحاكاة

<div align="center"><img src="images/04_Run_Arena17.jpg" alt="Run: تشغيل النموذج، والتحقق منه، وتحديد فترة المحاكاة" width="96%"/></div>

**الصورة الأصلية:** Run: تشغيل النموذج، والتحقق منه، وتحديد فترة المحاكاة.

1. افتح **Run → Check Model**.
2. افتح **Run → Setup**.
3. حدد وحدات الزمن و**Replication Length** و**Number of Replications**.
4. اضغط **Go**، ثم راجع **Reports**.

**انتبه:** **Replication Length = مدة تكرار المحاكاة** بقيمة `480 Minutes` تمثل ثماني ساعات من **Simulation Time = الزمن المحاكى**، بينما مثال الشريحة 1.5 يتناول **100 Callers = 100 متصل**. يجب توحيد شروط التشغيل قبل مقارنة النتائج.

---

<a id="arena-use-07"></a>
## 7. View — التحكم في العرض

<div align="center"><img src="images/05_View_Arena17.jpg" alt="View: التكبير والتصغير وإظهار اللوحات" width="96%"/></div>

**الصورة الأصلية:** View: التكبير والتصغير وإظهار اللوحات.

**Zoom / Fit / Pan** لتغيير حجم واتجاه رؤية النموذج؛ ويمكن إظهار أو إخفاء مناطق الواجهة وفق إعدادات النسخة. إذا اختفى **Spreadsheet View** فتأكد من الفاصل السفلي القابل للسحب.

---

<a id="arena-use-08"></a>
## 8. Tools — التحليل والمساعدة

<div align="center"><img src="images/06_Tools_Arena17.jpg" alt="Tools: التحليل والإعدادات والأدوات المساعدة" width="96%"/></div>

**الصورة الأصلية:** Tools: التحليل والإعدادات والأدوات المساعدة.

توجد أدوات مثل **Input Analyzer** لملاءمة توزيعات البيانات، وأدوات مقارنة المخرجات و**OptQuest** بحسب الترخيص. لا تفترض أن كل إضافة موجودة لدى المستخدم.

للحصول على الدليل المثبت مع النسخة، راجع **Arena Product Manuals** من واجهة البرنامج أو **Arena Help**.

---

<a id="arena-use-10"></a>
## 9. Project Bar → Discrete Processing

<div align="center"><img src="images/07_Discrete_Processing_Arena17.jpg" alt="Discrete Processing: Create, Process, Dispose modules used in the Call Center simulation" width="96%"/></div>

**الصورة الأصلية:** **Discrete Processing = معالجة الأحداث المنفصلة**، وتشمل **Create = إنشاء المتصل**، **Process = تنفيذ الخدمة**، **Dispose = خروج المتصل** في **Call Center**.

| Module (الوحدة) | Function in Call Center (الوظيفة في النموذج) |
|---|---|
| **Create = إنشاء كيان** | توليد **Callers = المتصلين** |
| **Assign = تعيين قيمة** | إضافة **Attribute = خاصية** للمتصل |
| **Process = تنفيذ الخدمة** | معالجة **Service Time = وقت الخدمة** وإدارة **Resource = المورد** و**Queue = طابور الانتظار** عند ضبطها |
| **Seize = حجز المورد** | حجز **Server = موظف الخدمة** المتاح |
| **Delay = زمن العملية** | تمثيل وقت تنفيذ الخدمة |
| **Release = تحرير المورد** | إتاحة الموظف لمتصل آخر |
| **Dispose = خروج الكيان** | انتهاء المكالمة وخروجها من النموذج |

**الفرق:** `Process: Seize Delay Release` يجمع حجز الموظف ثم خدمته ثم تحريره. أما `Delay` وحدها فلا تمثل تلقائيًا انتظار الموظف المشغول.

---

<a id="arena-use-12"></a>
## 10. مثال من المادة — Chapter 2: Simulation Examples, Slide 1.2 — Call Center Problem

**مصدر المثال:** **Chapter 2 — Simulation Examples, Slide 1.2**، بعنوان **Example 2: Call Center Problem = مسألة مركز الاتصالات**. وتوجد توزيعات **Interarrival Time = الزمن بين الوصولات** و**Service Time = وقت الخدمة** في **Slide 1.3**، وقوانين المحاكاة في **Slide 1.4**. **Aly** هو **Server = موظف خدمة** الأكثر خبرة، ويقدم الخدمة أسرع من **Bander** وفق المثال.

| الفصل | الشريحة المطبوعة | ما الذي نأخذه؟ |
|---|---|---|
| **Chapter 2** | **1.2** | شرح الموظفين وثلاث سياسات للتوجيه |
| Chapter 2 | **1.3** | جدول احتمالات الوصول والخدمة |
| Chapter 2 | **1.4** | طريقة حساب الوصول والانتظار والخدمة |
| Chapter 2 | **1.5** | نتائج مثال المحاضرة لعدد 100 مكالمة |
| Chapter 2 | **1.6** | بعض إحصاءات الانتظار |
| Chapter 2 | **1.7** | سياسات بديلة: Bander أولًا، أو اختيار عشوائي |
| Chapter 2 | **1.8** | خوارزمية **Bander أولًا**، وليس التوزيع العشوائي |
| **Chapter 6 — Random-Number Generation** | **6.7** | الانتظام والاستقلال، `R ~ U(0,1)` |
| Chapter 6 | **6.16–6.18** | **Linear Congruential Method** |
| **Chapter 7 — Random-Variate Generation** | **7.7** | **Inverse-Transform Technique** |
| Chapter 7 | **7.8–7.10** | أمثلة توليد زمن أُسي للتوضيح النظري، **وليست** توزيعات الكول سنتر |

### مثال من المادة — Chapter 2, Slide 1.3: Probability Distributions = التوزيعات الاحتمالية

| Variable (المتغير) | Time in Minutes (الوقت بالدقائق) | Probability (الاحتمال) | Cumulative Probability (الاحتمال التراكمي) |
|---|---|---|---|
| **Interarrival Time = الزمن بين وصول المكالمات** | 1، 2، 3، 4 | .25، .40، .20، .15 | .25، .65، .85، 1.00 |
| **Aly Service Time = وقت خدمة Aly** | 2، 3، 4، 5 | .30، .28، .25، .17 | .30، .58، .83، 1.00 |
| **Bander Service Time = وقت خدمة Bander** | 3، 4، 5، 6 | .35، .25، .20، .20 | .35، .60، .80، 1.00 |

**Arena DISC Expressions = تعبيرات التوزيع الاحتمالي المتقطع**، والمشتقة من جدول الاحتمالات في الشريحة 1.3:

**Interarrival Time**
```text
DISC(0.25,1, 0.65,2, 0.85,3, 1.00,4)
```
**Aly Service Time**
```text
DISC(0.30,2, 0.58,3, 0.83,4, 1.00,5)
```
**Bander Service Time**
```text
DISC(0.35,3, 0.60,4, 0.80,5, 1.00,6)
```

لا تستبدل هذه التوزيعات بـ `EXPO(6)` أو `TRIA(2,4,6)` إذا كان الهدف تنفيذ مثال المحاضرة نفسه؛ كانت تلك قيمًا افتراضية لمثال مختلف.

### قوانين المثال من المادة — Chapter 2, Slide 1.4; Chapter 6, Slides 6.16–6.17; Chapter 7, Slide 7.7

**Chapter 6, Slides 6.16–6.17: Pseudo-Random Number Generation = توليد الأرقام شبه العشوائية**

```text
X(i+1) = (a × X(i) + c) mod m
R(i) = X(i) / m
```

حيث `a` معامل الضرب، `c` الزيادة، `m` المقياس، و`X(0)` البذرة. المعادلة للتفسير العلمي؛ **لا تُعد إعدادًا يثبت أن Arena يستخدم المعاملات الموضحة في المحاضرة**.

**Chapter 7, Slide 7.7: Inverse-Transform Technique = طريقة التحويل العكسي**

```text
X = F⁻¹(R)
For discrete X: choose the smallest x with F(x) ≥ R
```

**مثال:** إذا كان `R = 0.69` فإن زمن ما بين الوصولات **3 دقائق**، وزمن خدمة Aly **4 دقائق**، وخدمة Bander **5 دقائق**، لأن القيمة تقع داخل المجالات التراكمية المقابلة.

**Chapter 2, Slide 1.4: Call Center Equations = معادلات نموذج الاتصالات**

```text
Arrival(k) = Arrival(k−1) + Interarrival(k)
Waiting(k) = ServiceStart(k) − Arrival(k)
Finish(k) = ServiceStart(k) + ServiceTime(k)
TimeInSystem(k) = Finish(k) − Arrival(k)
AverageWaiting = Sum(Waiting(k)) / N
```

### Call Center Scenarios = سيناريوهات توزيع المكالمات

| Scenario (السيناريو) | Routing Rule (قاعدة توزيع المكالمات) |
|---|---|
| **Scenario 1: Aly First = أولوية Aly** | عند توافر الاثنين، تكون الأولوية لـ Aly |
| **Scenario 2: Bander First = أولوية Bander** | عند توافر الاثنين، تكون الأولوية لـ Bander |
| **Scenario 3: Random = التوزيع العشوائي** | اختيار متاح عشوائيًا؛ في التطبيق المتساوي **50% Aly / 50% Bander** عند توافر الاثنين |

**تنبيه:** طلبت الشريحة 1.7 قاعدة الاختيار العشوائي. أما افتراض تساوي الاحتمال **50/50** فهو تحديد تنفيذي للسيناريو الثالث؛ لا تُنسب له نتائج رقمية من الشريحة 1.5 لأن نتائجها تخص تجربة أخرى. وإذا كان أحد الموظفين فقط متاحًا تُعطى المكالمة له، وإذا كان الاثنان مشغولين تدخل في الطابور.

---

<a id="arena-use-13"></a>
## 11. Call Center Model in Arena = تطبيق نموذج Call Center

### Step 1 — Create = إنشاء المكالمات
- **File → New → Blank Model**.
- **Project Bar → Discrete Processing → Create**.
- الاسم: `Caller Arrivals`، ونوع الكيان: `Caller`.
- **Time Between Arrivals → Type: Expression**، ثم أدخل:
```text
DISC(0.25,1, 0.65,2, 0.85,3, 1.00,4)
```
- **Units: Minutes**؛ **Entities per Arrival: 1**.

### Step 2 — Resource Definition = تعريف الموارد
- من بيانات الموارد **Resource** أنشئ `Aly` و`Bander`، مع **Capacity = 1** لكل موظف.
- من **Set** أنشئ `SupportTeam` يضم `Aly` و`Bander`، إذا كانت هذه الوحدة في قالب البيانات الملحق.

### Step 3 — Process = تنفيذ الخدمة
- أضف `Process` باسم `Handle Call`.
- **Action = Seize Delay Release**.
- اختر موردًا من المجموعة `SupportTeam`، مع **Selection Rule = Random** بين الموارد المتاحة عند توافر الخيار في إصدارك.
- احفظ هوية الموظف المختار في **Attribute** لتطبيق توزيع زمن الخدمة الخاص به؛ راجع **Expression Builder** لاختبار التعبير الشرطي وربطه بفهرس المورد الذي تُرجعه نسختك.

> **حد التحقق:** لم يُنفذ النموذج فعليًا داخل نسخة Arena على جهاز الطالب في هذه المحادثة؛ لذلك اختيار العضو العشوائي وحفظ فهرسه وتخصيص توزيعين مختلفين هما **خطوات إعداد تحتاج اختبارًا**، ولا أدعي أنها ملف نموذج `.doe` جاهز أو مخرجات فعلية. لا تنشئ طابورين مستقلين للمكالمات دون التصريح بتغيير سياسة الانتظار الأصلية.

### Step 4 — Dispose & Connect = إخراج الكيان وربط الوحدات
أضف `Dispose` باسم `Call Completed`، ثم صِل:

```text
Create: Caller Arrivals  →  Process: Handle Call  →  Dispose: Call Completed
```

### Step 5 — Run = تشغيل المحاكاة
- **Run → Check Model** للتحقق من التعابير والوصلات والموارد.
- **Run → Setup** لضبط الزمن والتكرارات.
- **Go** للتشغيل، ثم قراءة تقارير الأداء.
- لتكرار **100 مكالمة** كما في الشريحة 1.5 يجب التحكم في عدد الواصلين ومصير المكالمات الموجودة في النظام عند التوقف، وليس الاكتفاء بفترة ثابتة عشوائية.

---

<a id="arena-use-14"></a>
## 12. Simulation Results = نتائج المحاكاة

| Performance Measure (مقياس الأداء) | Definition (المعنى) |
|---|---|
| **Average Waiting Time = متوسط وقت الانتظار** | متوسط انتظار المتصل |
| **Number Waiting = عدد المنتظرين** | عدد المكالمات في الطابور |
| **Time in System** | الزمن من الوصول حتى الانتهاء |
| **Utilization — Aly = نسبة انشغال Aly** | نسبة انشغال Aly |
| **Utilization — Bander = نسبة انشغال Bander** | نسبة انشغال Bander |
| **Number Out = عدد المغادرين** | عدد المكالمات التي غادرت النظام |

للمقارنة العلمية بين السيناريوهات الثلاثة ثبّت توزيعات الوصول والخدمة ووحدات الزمن وشروط انتهاء التشغيل وعدد التكرارات، ثم قارن المتوسطات وعدم اليقين، لا التشغيل المنفرد فقط.

---

<a id="arena-use-shortcuts"></a>
## 13. اختصارات ومسارات سريعة

| الأمر | استخدامه |
|---|---|
| **Ctrl + S** | حفظ النموذج |
| **File → New** | إنشاء نموذج |
| **Home → Connect** | ربط الوحدات |
| **Run → Check Model** | التحقق قبل التشغيل |
| **Run → Setup** | إعداد التشغيل |
| **Run → Go** | بدء المحاكاة |
| **Arena Product Manuals / Help** | أدلة البرنامج المثبتة |

> يختلف موضع بعض الأوامر والاختصارات بين إعدادات الإصدارات. اعتمد اسم الأمر الظاهر عندك إذا اختلف مكانه.

---

<a id="arena-use-15"></a>
## 14. المراجع والصور

**مواد المقرر المقدمة من الطالب:**
- محمود الشربيني، *Chapter 2 — Simulation Examples*, Example 2: Call Center Problem، الشرائح المطبوعة **1.2–1.8**. ملف: `Ch02_Call_Center_Scenarios_Highlighted.pptx`، مواد مقرر غير منشورة.
- *Chapter 6 — Random-Number Generation*، خاصة الشرائح **6.7** و**6.16–6.18**. ملف: `06 Random-Number Generation simulation Mah Final(4).pptx`.
- *Chapter 7 — Random-Variate Generation*، خاصة الشرائح **7.7–7.10**. ملف: `07 Random-Variate Generation Mah Final [Autosaved](2).pptx`.

**مصادر البرنامج والصورة الحديثة:**
- [Rockwell Automation — صفحة تنزيل Arena Professional Edition](https://www.rockwellautomation.com/en-us/products/software/arena-simulation/buying-options/download.html).
- [Rockwell Automation — خيارات Arena Professional Edition وDemo/Academic](https://www.rockwellautomation.com/en-us/products/software/arena-simulation/buying-options.html).
- صور واجهة Arena 17 الأصلية التي أرسلها الطالب، محفوظة في مجلد `guides/Arena/images` بالمستودع.

**ملاحظة الصور:** جميع اللقطات السبع أصلية من جهاز الطالب، وقد رُفعت كملفات صور فعلية داخل المستودع، ووُضعت كل لقطة في القسم الذي يشرحها.

</div>
