<div dir="rtl" align="right">

# دليل استخدام Arena Simulation

**إعداد:** Talal bin Ibrahim Alsultan  
**آخر تحديث:** 27 أكتوبر 2026  
**الإصدار المستهدف:** Arena Simulation 17.

> هذا **دليل استخدام** مستقل عن [دليل تحميل وتثبيت Arena](https://github.com/talalalsultan246-cell/Arena-Simulation-Arabic-Guide/blob/main/guides/Arena/README.md).

في محاضرة يوم الأحد **25 أكتوبر 2026**، استعرض **الأستاذ الدكتور محمود الشربيني مشكوراً** واجهات Arena الأساسية وبعض طرق إنشاء نموذج أولي. يربط هذا الدليل بين واجهة **Arena Simulation 17** وبين مثال **Call Center Problem = مسألة مركز الاتصالات** الوارد في **Chapter 2: Simulation Examples = الفصل الثاني: أمثلة المحاكاة**.


## المحتويات

1. [الواجهة الرئيسية](#arena-use-01)
2. [File](#arena-use-02)
3. [Home](#arena-use-03)
4. [Animate](#arena-use-04)
5. [Draw](#arena-use-05)
6. [Run](#arena-use-06)
7. [View](#arena-use-07)
8. [Tools](#arena-use-08)
9. [Discrete Processing](#arena-use-10)
10. [مصطلحات واجهة Arena](#arena-use-glossary)
11. [مثال Call Center من Chapter 2](#arena-use-12)
12. [تنفيذ المثال داخل Arena](#arena-use-13)
13. [تشغيل النموذج وقراءة النتائج](#arena-use-14)
14. [الأوامر السريعة](#arena-use-shortcuts)
15. [مصادر البرنامج](#arena-use-15)

---

<a id="arena-use-01"></a>
## 1. الواجهة الرئيسية — Home

<div align="center"><img src="images/01_Home_Arena17.jpg" width="96%" alt="Arena 17 Home interface with six red numbered areas"/></div>

**الأرقام في الصورة:**

<p dir="rtl" align="right"><strong>(1)</strong> <strong>Home = التبويب الرئيسي:</strong> أدوات تحرير نموذج المحاكاة والتحكم في عرضه وربط الوحدات.</p>
<p dir="rtl" align="right"><strong>(2)</strong> <strong>Project Bar = لوحة المشروع:</strong> تعرض مجموعات الوحدات التي تستخدم في إنشاء النموذج.</p>
<p dir="rtl" align="right"><strong>(3)</strong> <strong>Model Window = نافذة النموذج:</strong> المساحة البيضاء التي تسحب إليها الوحدات وترسم فيها تسلسل العمليات.</p>
<p dir="rtl" align="right"><strong>(4)</strong> <strong>Spreadsheet View = عرض الجداول:</strong> إدخال خصائص الوحدات والموارد ومراجعتها.</p>
<p dir="rtl" align="right"><strong>(5)</strong> <strong>Animate Bar = لوحة الحركة:</strong> تعرض عناصر الحركة مثل Queues وResources وEntity Pictures.</p>
<p dir="rtl" align="right"><strong>(6)</strong> <strong>Connect = توصيل الوحدات:</strong> ترسم مسار انتقال الكيان من وحدة إلى أخرى.</p>

---

<a id="arena-use-02"></a>
## 2. File — الملفات والحفظ

- **New = جديد:** إنشاء نموذج.
- **Open = فتح:** فتح نموذج محفوظ.
- **Save / Save As = حفظ / حفظ باسم:** حفظ نموذج Arena بامتداد .doe.

---

<a id="arena-use-03"></a>
## 3. Home — أدوات بناء النموذج

<div align="center"><img src="images/01_Home_Arena17.jpg" width="96%" alt="Arena 17 Home tab and red highlighted Connect button"/></div>

**الأرقام في الصورة:**

<p dir="rtl" align="right"><strong>(1)</strong> <strong>Home:</strong> التبويب الرئيسي.</p>
<p dir="rtl" align="right"><strong>(2)</strong> <strong>Project Bar:</strong> اختيار وحدات المحاكاة من اللوحة اليسرى.</p>
<p dir="rtl" align="right"><strong>(3)</strong> <strong>Model Window:</strong> سحب الوحدات إلى منطقة بناء النموذج.</p>
<p dir="rtl" align="right"><strong>(4)</strong> <strong>Spreadsheet View:</strong> تعديل البيانات والخصائص.</p>
<p dir="rtl" align="right"><strong>(5)</strong> <strong>Animate Bar:</strong> عرض عناصر الحركة.</p>
<p dir="rtl" align="right"><strong>(6)</strong> <strong>Connect:</strong> ربط مخرج الوحدة الأولى بمدخل الوحدة التالية.</p>

**مثال سريع:** اسحب Create ثم Process ثم Dispose إلى Model Window، واستخدم Connect لتوصيلها بالترتيب.

---

<a id="arena-use-04"></a>
## 4. Animate — عرض الحركة

<div align="center"><img src="images/02_Animate_Arena17.jpg" width="96%" alt="Arena 17 Animate tab with three numbered red highlights"/></div>

**الأرقام في الصورة:**

<p dir="rtl" align="right"><strong>(1)</strong> <strong>Animate:</strong> التبويب المخصص لعناصر عرض الحركة.</p>
<p dir="rtl" align="right"><strong>(2)</strong> <strong>Status / Waiting / Queue / Resource:</strong> مجموعات لعرض الحالة والطوابير والموارد أثناء المحاكاة.</p>
<p dir="rtl" align="right"><strong>(3)</strong> <strong>Animate Bar:</strong> القائمة اليمنى التي تجمع عناصر الحركة مثل Levels وQueues وResources.</p>

في نموذج Call Center يمكن إظهار حالة الموظفين وعدد المكالمات المنتظرة أثناء التشغيل.

---

<a id="arena-use-05"></a>
## 5. Draw — الرسم

<div align="center"><img src="images/03_Draw_Arena17.jpg" width="96%" alt="Arena 17 Draw tab with three numbered highlights"/></div>

**الأرقام في الصورة:**

<p dir="rtl" align="right"><strong>(1)</strong> <strong>Draw:</strong> تبويب رسم العناصر التوضيحية.</p>
<p dir="rtl" align="right"><strong>(2)</strong> <strong>Line / Fill / Text / Shapes:</strong> رسم الخطوط والأشكال وإضافة النصوص وتنسيقها.</p>
<p dir="rtl" align="right"><strong>(3)</strong> <strong>Model Window:</strong> المكان الذي تظهر فيه الرسوم إلى جانب وحدات النموذج.</p>

استخدم Text لإضافة عنوان Call Center أعلى الرسم. خطوط Draw للتوضيح؛ أما توصيل مسار المكالمات فيتم بواسطة Connect.

---

<a id="arena-use-06"></a>
## 6. Run — التشغيل

<div align="center"><img src="images/04_Run_Arena17.jpg" width="96%" alt="Arena 17 Run tab with three numbered highlights"/></div>

**الأرقام في الصورة:**

<p dir="rtl" align="right"><strong>(1)</strong> <strong>Run:</strong> تبويب تشغيل المحاكاة.</p>
<p dir="rtl" align="right"><strong>(2)</strong> <strong>Go / Pause / Stop / Check Model / Review Errors:</strong> بدء التشغيل والتحكم به وفحص الأخطاء.</p>
<p dir="rtl" align="right"><strong>(3)</strong> <strong>Debug / Visualization:</strong> أدوات متابعة المحاكاة والعناصر المتحركة.</p>

**Run → Setup** يفتح إعدادات التشغيل مثل Replication Length وNumber of Replications.

---

<a id="arena-use-07"></a>
## 7. View — العرض

<div align="center"><img src="images/05_View_Arena17.jpg" width="96%" alt="Arena 17 View tab with three numbered highlights"/></div>

**الأرقام في الصورة:**

<p dir="rtl" align="right"><strong>(1)</strong> <strong>View:</strong> تبويب إعدادات العرض.</p>
<p dir="rtl" align="right"><strong>(2)</strong> <strong>Zoom In / Zoom Out / Zoom Factor:</strong> تكبير نموذج المحاكاة وتصغيره.</p>
<p dir="rtl" align="right"><strong>(3)</strong> <strong>Views / Project Bar / Status Bar / Animate Bar:</strong> إظهار مناطق البرنامج وتنظيم طريقة العرض.</p>

---

<a id="arena-use-08"></a>
## 8. Tools — الأدوات

<div align="center"><img src="images/06_Tools_Arena17_no3.svg" width="96%" alt="Arena 17 Tools tab with two numbered highlights"/></div>

**الأرقام في الصورة:**

<p dir="rtl" align="right"><strong>(1)</strong> <strong>Tools:</strong> تبويب الأدوات المساعدة.</p>
<p dir="rtl" align="right"><strong>(2)</strong> <strong>Object Transfer to Arena:</strong> أداة ضمن مجموعة الربط والتكامل الموجودة يسار الشريط.</p>

من هذا التبويب يمكن الوصول إلى أدوات مثل Input Analyzer وModel Report حسب الأدوات الظاهرة في الشاشة.

---

<a id="arena-use-10"></a>
## 9. Discrete Processing — وحدات بناء النموذج

<div align="center"><img src="images/07_Discrete_Processing_Arena17.jpg" width="96%" alt="Arena 17 Discrete Processing module panel numbered 1 to 4"/></div>

**الأرقام في الصورة:**

<p dir="rtl" align="right"><strong>(1)</strong> <strong>Discrete Processing:</strong> اللوحة التي تضم وحدات مسار الكيانات.</p>
<p dir="rtl" align="right"><strong>(2)</strong> <strong>Create:</strong> إنشاء المكالمات أو الكيانات عند وصولها.</p>
<p dir="rtl" align="right"><strong>(3)</strong> <strong>Process:</strong> تنفيذ عملية الخدمة. يمكنها أن تحجز موردًا وتؤخر الكيان وتحرره حسب إعداد Action.</p>
<p dir="rtl" align="right"><strong>(4)</strong> <strong>Dispose:</strong> إنهاء مسار الكيان بعد اكتمال الخدمة.</p>

تحتوي اللوحة أيضًا على وحدات **Seize = حجز مورد**، **Delay = وقت الخدمة**، **Release = تحرير مورد**. سنستخدم هذه الوحدات في المثال لأن وقت خدمة Aly يختلف عن وقت خدمة Bander.

---

<a id="arena-use-glossary"></a>
## 10. مصطلحات واجهة Arena

| English | العربية |
|---|---|
| **Home** | التبويب الرئيسي |
| **Animate** | عرض الحركة |
| **Draw** | الرسم |
| **Run** | التشغيل |
| **View** | العرض |
| **Tools** | الأدوات |
| **Project Bar** | لوحة المشروع |
| **Model Window** | نافذة بناء النموذج |
| **Spreadsheet View** | عرض البيانات والخصائص |
| **Animate Bar** | لوحة الحركة |
| **Discrete Processing** | لوحة وحدات العمليات |
| **Create** | إنشاء كيان |
| **Seize** | حجز مورد |
| **Delay** | تنفيذ تأخير زمني |
| **Release** | تحرير مورد |
| **Process** | تنفيذ عملية |
| **Dispose** | إخراج الكيان من النموذج |
| **Resource** | مورد |
| **Set** | مجموعة موارد |
| **Save Attribute** | حفظ خاصية على الكيان |
| **Connect** | توصيل الوحدات |
| **Check Model** | فحص النموذج |
| **Setup** | إعدادات التشغيل |
| **Go** | بدء التشغيل |
| **Reports** | تقارير النتائج |

---

<a id="arena-use-12"></a>
## 11. مثال من المادة — Chapter 2: Simulation Examples, Slide 1.2

### Example 2: Call Center Problem

يستقبل **Call Center = مركز الاتصالات** المكالمات ويقدم الخدمة موظفان: **Aly** و**Bander**. الموظف Aly أسرع من Bander وفق بيانات المثال.

**المطلوب:** محاكاة وصول **100 Callers = 100 متصل**، وتوزيع المكالمات على الموظفين، ثم قياس **Waiting Time = وقت الانتظار** و**Time in System = الوقت داخل النظام** ونسبة انشغال الموظفين.

**مصدر البيانات:** **Chapter 2 — Slide 1.3**.

| البيانات | الوقت بالدقائق | الاحتمالات |
|---|---|---|
| **Interarrival Time = الزمن بين الوصولات** | 1، 2، 3، 4 | 0.25، 0.40، 0.20، 0.15 |
| **Aly Service Time = وقت خدمة Aly** | 2، 3، 4، 5 | 0.30، 0.28، 0.25، 0.17 |
| **Bander Service Time = وقت خدمة Bander** | 3، 4، 5، 6 | 0.35، 0.25، 0.20، 0.20 |

في **Slide 1.2** تبدأ الخدمة مع Aly إذا كان كلا الموظفين متاحًا، ثم تُدرس سياسات أخرى في **Slide 1.7**، منها **Bander First** و**Random Assignment**.

---

<a id="arena-use-13"></a>
## 12. التطبيق العملي: بناء Call Center في Arena

<text dir="ltr"></text>

### الخطوة 1 — New Model

1. افتح **Arena Simulation 17**.
2. اختر **File → New** لإنشاء نموذج فارغ.
3. افتح **File → Save As** واحفظه باسم **Call_Center_Aly_Bander.doe**.
4. من **Project Bar** افتح **Discrete Processing**.

### الخطوة 2 — Create: إنشاء المكالمات

اسحب **Create** إلى Model Window وانقر عليه مرتين.

| الحقل في Arena | القيمة |
|---|---|
| Name | Caller Arrivals |
| Entity Type | Caller |
| Time Between Arrivals — Type | Expression |
| Expression | DISC(0.25,1, 0.65,2, 0.85,3, 1.00,4) |
| Units | Minutes |
| Entities per Arrival | 1 |
| Max Arrivals | 100 |
| First Creation | 0 |

**Interarrival Time = الزمن بين وصول مكالمتين متتاليتين**. يستخدم تعبير DISC الاحتمالات التراكمية من **Chapter 2, Slide 1.3**.

### الخطوة 3 — Seize: حجز موظف متاح

اسحب **Seize** من لوحة Discrete Processing وضعه بعد Create.

أثناء إعداد وحدة Seize:

1. افتح بيانات **Resource** من لوحة **Data Definition**، وأدخل **Aly — Capacity = 1** ثم **Bander — Capacity = 1**.
2. من بيانات **Set** أنشئ مجموعة موارد باسم **SupportTeam**، وأضف إليها **Aly** أولًا ثم **Bander** ثانيًا.
3. انقر مرتين على **Seize** وسمِّها **Assign Available Agent**.
4. افتح قائمة **Resources → Add**، وحدد **Type = Set** و**Set Name = SupportTeam** و**Quantity = 1**.
5. اختر **Selection Rule = Preferred Order**، ثم أدخل **Save Attribute = aAgentIndex**.

هذا يطبّق سيناريو **Aly First = أولوية Aly**: إذا كان Aly متاحًا يختاره النظام، وإلا يختار Bander؛ وإذا كان الاثنان مشغولين تنتظر المكالمة في **Queue = طابور الانتظار** المتعلق بوحدة Seize. تستخدم **Save Attribute** لحفظ رقم الموظف الذي اختاره Arena من المجموعة. <https://www.manualsdir.com/manuals/580146/rockwell-automation-arena-basic-edition-users-guide.html?page=39>

### الخطوة 4 — Decide: تحديد من يقدم الخدمة

من **Project Bar → Decisions** اسحب **Decide** وضعه بعد Seize.

- **Name:** Which Agent?
- **Type:** 2-way by Condition
- **Condition:** aAgentIndex == 1

**True** يعني أن الموظف المختار هو **Aly**، و**False** يعني **Bander**. تأكد أن ترتيب أعضاء مجموعة SupportTeam هو Aly ثم Bander.

### الخطوة 5 — Delay: إدخال Service Time

ضع وحدتين من **Delay** بعد Decide، ثم اضبط:

**Delay الأولى — Aly Service**

| الحقل | القيمة |
|---|---|
| Name | Aly Service |
| Delay Type | Expression |
| Expression | DISC(0.30,2, 0.58,3, 0.83,4, 1.00,5) |
| Units | Minutes |

**Delay الثانية — Bander Service**

| الحقل | القيمة |
|---|---|
| Name | Bander Service |
| Delay Type | Expression |
| Expression | DISC(0.35,3, 0.60,4, 0.80,5, 1.00,6) |
| Units | Minutes |

**Service Time = وقت الخدمة.** تعبيرا DISC مأخوذان من توزيعي الخدمة في **Chapter 2, Slide 1.3**.

### الخطوة 6 — Release ثم Dispose

1. ضع وحدة **Release** بعد مساري Delay، وسمّها **Free Agent**.
2. في **Resources → Add** اختر **Type = Set**، ثم **Set Name = SupportTeam**.
3. اختر **Release Rule = Specific Member** و**Set Index = aAgentIndex** و**Quantity = 1**، حتى تحرر وحدة Release الموظف نفسه الذي حجزته وحدة Seize.
4. أضف **Dispose** باسم **Call Completed**.

### الخطوة 7 — Connect: توصيل النموذج

صِل الوحدات بالترتيب:

~~~text
Create: Caller Arrivals
          |
          v
Seize: Assign Available Agent
          |
          v
Decide: Which Agent?
      /           \
  True / Aly    False / Bander
     |              |
     v              v
Delay: Aly      Delay: Bander
 Service          Service
     \              /
      \            /
       v          v
       Release: Free Agent
                |
                v
       Dispose: Call Completed
~~~

تنتظر المكالمة داخل Seize إلى أن يتوافر موظف. بعد ذلك تنتقل إلى **Delay** الخاصة به، ثم يُحرّر الموظف وتغادر المكالمة.

### الخطوة 8 — مقارنة السيناريوهات

بعد حفظ النموذج وتشغيل **Aly First**:

- **Scenario 2 — Bander First:** غيّر ترتيب أعضاء SupportTeam إلى **Bander ثم Aly** مع إبقاء **Preferred Order**. حدّث شرط Decide حتى يتوافق كل مسار Delay مع الموظف الصحيح.
- **Scenario 3 — Random:** أبقِ ترتيب **Aly ثم Bander**، وغيّر **Selection Rule = Random** في Seize. إذا كان الموظفان متاحين يُختار أحدهما باحتمال متساوٍ، أما إذا كان أحدهما فقط متاحًا فتُسند المكالمة إليه.

احفظ كل سيناريو باسم مختلف للمقارنة.

---

<a id="arena-use-14"></a>
## 13. تشغيل المحاكاة وقراءة النتائج

### الخطوة 9 — Run: التشغيل

1. افتح **Run → Check Model** للتحقق من النموذج.
2. افتح **Run → Setup**.
3. اجعل **Base Time Units = Minutes**.
4. اختر **Replication Length = 1000 Minutes** و**Number of Replications = 1** للتجربة الأولى.
5. اضغط **Go** لبدء المحاكاة.
6. افتح **Reports** بعد الانتهاء.

**Max Arrivals = 100** يمنع إنشاء أكثر من 100 مكالمة؛ ومدة 1000 دقيقة تسمح في هذا المثال بزمن كافٍ لانتهاء المكالمات التي بدأت، في ضوء الحدود القصوى لأزمنة الوصول والخدمة الموجودة في الشريحة 1.3. عند المقارنة، استخدم مدة التشغيل نفسها لجميع السيناريوهات.

### الخطوة 10 — نتائج Arena

راجع في التقارير:

| Performance Measure = مقياس الأداء | القراءة المطلوبة |
|---|---|
| **Number In = عدد الداخلين** | يجب أن يكون 100 متصل |
| **Number Out = عدد الخارجين** | تحقق من اكتمال خدمة المتصلين المئة |
| **Average Waiting Time = متوسط وقت الانتظار** | معدل الانتظار قبل حجز الموظف |
| **Number Waiting = عدد المنتظرين** | عدد المكالمات في Queue |
| **Aly Utilization = نسبة انشغال Aly** | نسبة الوقت الذي كان فيه Aly مشغولًا |
| **Bander Utilization = نسبة انشغال Bander** | نسبة الوقت الذي كان فيه Bander مشغولًا |
| **Time in System = الوقت داخل النظام** | من وقت وصول المكالمة إلى مغادرتها |

**للمقارنة مع المحاضرة:** في جدول تجربة **Chapter 2, Slide 1.5**، بلغ مجموع **Caller Delay = وقت انتظار المتصلين** مقدار **211 دقيقة**، ومجموع **Time in System = الوقت داخل النظام** مقدار **564 دقيقة** لـ100 مكالمة؛ أي متوسطين **2.11 دقيقة** و**5.64 دقيقة** على التوالي. **هذه أرقام المثال الوارد في الشريحة، وليست نتائج تشغيل فعلي لهذا النموذج في Arena**. تختلف المخرجات عند اختلاف تسلسل الأرقام العشوائية أو سياسة توزيع المكالمات.

**معادلات الفصل الثاني — Slide 1.4:**

~~~text
Arrival Time(k) = Arrival Time(k−1) + Interarrival Time(k)
Waiting Time(k) = Service Start Time(k) − Arrival Time(k)
Service Completion Time(k) = Service Start Time(k) + Service Time(k)
Time in System(k) = Service Completion Time(k) − Arrival Time(k)
~~~

**صلة الفصلين السادس والسابع:** يوضح **Chapter 6 — Random-Number Generation** توليد الأرقام العشوائية، ويعرض **Chapter 7 — Random-Variate Generation** توليد القيم وفق توزيعاتها. في Arena ينفّذ **DISC** اختيار الوقت طبقًا للاحتمالات التراكمية في شريحة المثال.

---

<a id="arena-use-shortcuts"></a>
## 14. الأوامر السريعة

| الأمر | الوظيفة |
|---|---|
| File → New | نموذج جديد |
| Ctrl + S | حفظ النموذج |
| Home → Connect | توصيل الوحدات |
| Run → Check Model | فحص النموذج |
| Run → Setup | إعداد تشغيل المحاكاة |
| Run → Go | بدء المحاكاة |
| Reports | قراءة نتائج التشغيل |

---

<a id="arena-use-15"></a>
## 15. مصادر البرنامج

- [Rockwell Automation — تنزيل Arena](https://www.rockwellautomation.com/en-us/products/software/arena-simulation/buying-options/download.html)
- [Rockwell Automation — Arena Basic Edition User's Guide، إعداد Resource Set](https://www.manualsdir.com/manuals/580146/rockwell-automation-arena-basic-edition-users-guide.html?page=39)
- [Getting Started with Arena — وصف Seize وRelease وSelection Rule](https://studylib.net/doc/28102816/getting-started-with-arena)

</div>
