<div dir="rtl" align="right">

# **دليل IBM SPSS Statistics**

**إعداد:** Talal bin Ibrahim Alsultan  
**آخر تحديث:** 27 أكتوبر 2026

إذا كانت لديك بيانات لاستبانة أو مشروع جامعي وتحتاج إلى تحليلها، فإن **IBM SPSS Statistics** يساعدك في تجهيز البيانات وإجراء التحليلات الإحصائية وقراءة نتائجها. في هذا الدليل سنمر بثلاث مراحل واضحة: **تحميل البرنامج وتفعيله، التعرف على واجهاته واستخداماته، ثم تطبيق مثال واحد على الانحدار الخطي البسيط**.

</div>

<div align="center">
<img src="images/spss-guide-banner.svg" alt="ملخص المراحل الأساسية لدليل SPSS" width="95%"/>
</div>

<div dir="rtl" align="right">

> **دليل عملي لتنزيل SPSS وتثبيته، والتعرّف على قوائمه واستخداماته، وتنفيذ مثال واحد على الانحدار الخطي.**

<a name="spss-toc"></a>
## المحتويات

1. [تحميل SPSS وتثبيته وتفعيله](#spss-section-01)
   - [تنزيل النسخة المناسبة](#spss-section-01-01)
   - [تنشيط النسخة بطريقة نظامية](#spss-section-01-02)
   - [ماذا عن الروابط غير الرسمية؟](#spss-section-01-03)
2. [التعرف على الواجهة ومجالات الاستخدام](#spss-section-02)
   - [النوافذ الأساسية](#spss-section-02-01)
   - [ما الذي يمكن استخدام SPSS فيه؟](#spss-section-02-02)
   - [قراءة نتائج الانحدار والسلاسل الزمنية](#spss-section-02-03)
   - [كيف أفهم الجداول بعد تشغيل Regression؟](#spss-section-02-04)
3. [مثال تطبيقي واحد — Simple Linear Regression](#spss-section-03)
   - [قراءة مخرجات المثال: Model Summary وANOVA وCoefficients وDurbin–Watson](#spss-example-output)
   - [الخطوات داخل البرنامج](#spss-section-03-01)
4. [أسئلة متكررة عند الاستخدام](#spss-section-04)
5. [المصادر الرسمية وروابط الاستخدام](#spss-section-05)

---
<a name="spss-section-01"></a>
## 1. تحميل SPSS وتثبيته وتفعيله

<a name="spss-section-01-01"></a>
### 1. تنزيل النسخة المناسبة

1. ابدأ من [IBM SPSS Statistics — الصفحة الرسمية](https://www.ibm.com/products/spss-statistics).
2. حدد نوع الاستخدام: **تجربة رسمية** أو **اشتراك** أو **ترخيص الجامعة**. إذا حصلت على SPSS من جامعتك فالتزم بالإصدار وطريقة التفعيل اللذين توفرهما.
3. سجّل الدخول باستخدام **IBMid** عند الطلب، ثم نزّل المثبّت المناسب لنظامك.
4. شغّل ملف التثبيت الرسمي، واتبع التعليمات ثم افتح البرنامج.
5. أكمل التفعيل بالطريقة المطابقة لرخصتك، ثم تأكد من ظهور محرر البيانات **Data Editor**.

يمكنك مراجعة [صفحة موارد SPSS](https://www.ibm.com/products/spss-statistics/resources) و[توثيق IBM الرسمي](https://www.ibm.com/docs/en/spss-statistics) إذا اختلفت الواجهة أو تفاصيل التثبيت.

<div align="center">
<img src="images/01-download-ibm.svg" alt="رسم إرشادي لخطوات تنزيل SPSS" width="87%"/>
</div>

<small>هذه صورة إرشادية وليست لقطة شاشة فعلية. لواجهة التنزيل الحقيقية والمحدثة استخدم رابط IBM الرسمي أعلاه؛ فقد تتغير الشاشة من إصدار إلى آخر.</small>

<a name="spss-section-01-02"></a>
### 2. تنشيط النسخة بطريقة نظامية

| نوع الترخيص | طريقة التشغيل |
| :--- | :--- |
| **Subscription / Trial** | تسجيل الدخول بحساب **IBMid** المرتبط بالاشتراك أو التجربة |
| **Authorized User License** | استخدام **License Authorization Wizard** مع **Authorization Code** الرسمي |
| **Concurrent / Network License** | تطبيق تعليمات جهة الترخيص أو الجامعة للوصول إلى خادم التراخيص |

قد تصل إلى المعالج من **File → Manage License → Launch License Wizard** بحسب الإصدار. لا يعني وجود مفتاح متداول في موقع خارجي أنه يحوّل البرنامج إلى نسخة أصلية.

<a name="spss-section-01-03"></a>
### 3. ماذا عن الروابط غير الرسمية؟

قد يصادف القارئ [صفحة SPSS في Traidsoft](https://apps.traidsoft.net/download-ibm-spss-statistics/)، وهي **ليست مصدرًا رسميًا تابعًا لـ IBM**، ولا تُعد بديلًا للتحميل والترخيص النظاميين. تعرض الصفحة أداة تنشيط غير رسمية؛ لذلك لا أوصي باستخدامها أو بتعطيل أدوات الحماية.

<div align="center">
<img src="images/third-party-disclaimer.svg" alt="إخلاء مسؤولية بشأن مصادر SPSS غير الرسمية" width="90%"/>
</div>

<small><em>إخلاء مسؤولية: الرابط الخارجي غير تابع لشركة IBM، ولا يمكن ضمان سلامة الملفات أو صحة حقوق توزيعها. افحص الملفات قبل التشغيل ولا تعطل أنظمة الحماية. فحص الفيروسات لا يمنح البرنامج ترخيصًا رسميًا.</em></small>

<a name="spss-section-02"></a>
## 2. التعرف على الواجهة ومجالات الاستخدام

<a name="spss-section-02-01"></a>
### 4. النوافذ الأساسية

أول ما يفتح البرنامج عادةً ستتعامل مع **Data View** و**Variable View**، وبعد تشغيل أي تحليل ستظهر نافذة **Output Viewer**.

<div align="center">
<img src="https://s3.amazonaws.com/libapps/accounts/2515/images/spss_creating-variables_insert-variables-2.png" alt="لقطة حقيقية لواجهة SPSS Data View من مكتبة Kent State University" width="82%"/>
</div>

<small>صورة فعلية من [مكتبة جامعة Kent State](https://libguides.library.kent.edu/SPSS/CreateData). في حال تغيّر رابط الصورة، تتوفر صورة إرشادية في [ملفات الدليل](images/02-data-view.svg).</small>

**Data View:** أدخل البيانات هنا؛ كل صف يمثل سجلًا أو حالة، وكل عمود يمثل متغيرًا. تأكد من وضع الأرقام في الأعمدة الرقمية وعدم إضافة العناوين على أنها سجلات.



<div align="center">
<img src="https://sscc.wisc.edu/sscc/pubs/spss/classintro/screenshots/spss_students1/SPSS07VariableView.jpg" alt="لقطة حقيقية من SPSS Variable View - University of Wisconsin" width="82%"/>
</div>

<small>صورة فعلية من [University of Wisconsin](https://sscc.wisc.edu/sscc/pubs/spss/classintro/spss_students1.html). نسخة احتياطية إرشادية في [ملفات الدليل](images/03-variable-view.svg).</small>

**Variable View:** حدد اسم المتغير **Name**، ونوعه **Type**، ووصفه **Label**، ومستوى قياسه **Measure**، والقيم المفقودة **Missing**. اختيار نوع المتغير الصحيح خطوة مهمة قبل أي تحليل.



| الجزء | ماذا تستخدمه لأجله؟ |
| :--- | :--- |
| **Data View** | قراءة البيانات وإدخال الحالات |
| **Variable View** | تعريف المتغيرات ومستوى القياس |
| **Analyze** | اختيار الاختبار أو النموذج الإحصائي |
| **Graphs** | الرسوم البيانية والتوزيعات |
| **Transform** | إنشاء متغيرات وحساب قيم جديدة |
| **Output Viewer** | قراءة الجداول والرسوم التي أنتجها التحليل |
| **Syntax Editor** | حفظ أوامر التحليل وإعادة تنفيذها بصورة قابلة للتكرار |

<a name="spss-section-02-02"></a>
### 5. ما الذي يمكن استخدام SPSS فيه؟

- **Descriptive Statistics:** المتوسط الحسابي والانحراف المعياري والتكرارات وتلخيص البيانات.
- **Correlation:** دراسة اتجاه الارتباط وقوته بين المتغيرات المناسبة.
- **Simple Linear Regression:** دراسة علاقة متغير مستقل واحد بمتغير تابع واحد، وتكوين معادلة تنبؤ.
- **Multiple Linear Regression:** استخدام عدة متغيرات مستقلة لتفسير أو التنبؤ بالمتغير التابع.
- **One-Way ANOVA:** مقارنة متوسطات مجموعات وتفسير اختبار `F` والمقارنات اللاحقة عند الحاجة.
- **Binary Logistic Regression:** نمذجة ناتج ثنائي، مثل نجاح/فشل أو نعم/لا، عندما يناسب نوع البيانات والنموذج.
- **Time Series / Forecasting:** دراسة الاتجاهات الزمنية وتقدير نماذج ملائمة للسلاسل الزمنية.
- **ACF / Autocorrelation:** فحص الارتباط الذاتي عبر الفجوات الزمنية.
- **Residual Diagnostics:** فحص بواقي الانحدار ومخططاتها وتقييم افتراضات النماذج.
- **Graphs and Tables:** الرسوم البيانية وجداول النتائج الإحصائية.

<a name="spss-section-02-03"></a>
### قراءة نتائج الانحدار والسلاسل الزمنية

عند تطبيق **Regression** في SPSS ستظهر جداول مثل **Model Summary** و**ANOVA** و**Coefficients**، ويمكن عرض **Histogram** و**Normal P–P Plot** و**Scatterplot** لفحص البواقي. أما عند تحليل البيانات الزمنية، فقد تحتاج إلى **ACF** و**Time Series Modeler** و**Sequence Plot** حسب الهدف من التحليل.

هذه أدوات يمكن استخدامها في البرنامج، ولا يلزم تنفيذها كلها في مشروع واحد. اختر الإجراء المناسب للسؤال وطبيعة البيانات، ثم فسّر النتيجة بناءً على الافتراضات الإحصائية.

<a name="spss-section-02-04"></a>
### 6. كيف أفهم الجداول بعد تشغيل Regression؟

| اسم الجدول | ماذا تقرأ فيه؟ |
| :--- | :--- |
| **Model Summary** | `R Square` و`Adjusted R Square` عند ملاءمتهما |
| **ANOVA** | قيمة `F` و`Sig.` للدلالة الإحصائية الإجمالية لنموذج الانحدار |
| **Coefficients** | المعاملات `B` وصيغة معادلة الانحدار وقيم `t` و`Sig.` |
| **Residual Plots** | فحص طبيعة الأخطاء والتوزيع والقيم غير المعتادة |

**ملاحظة مهمة:** جدول **ANOVA** الذي يظهر في تقرير الانحدار يختبر دلالة نموذج الانحدار ككل؛ وهو يختلف في الغرض المباشر عن **One-Way ANOVA** الذي تُقارن فيه متوسطات مجموعات.

<a name="spss-section-03"></a>
## 3. مثال تطبيقي واحد — Simple Linear Regression

سأستخدم مثالًا تعليميًا من خمس حالات افتراضية لتوضيح كيفية دراسة العلاقة بين **ساعات الدراسة** و**درجة الاختبار**، ثم قراءة معادلة الانحدار.

| StudyHours (X) | ExamScore (Y) |
| :---: | :---: |
| 1 | 2 |
| 2 | 3 |
| 3 | 5 |
| 4 | 4 |
| 5 | 7 |

<a name="spss-section-03-01"></a>
### الخطوات داخل البرنامج

1. من **Variable View** أنشئ متغيرين رقميين بمستوى قياس **Scale**: `StudyHours` و`ExamScore`.
2. أدخل الجدول السابق في **Data View**.
3. افتح **Analyze → Regression → Linear**.
4. ضع `ExamScore` في **Dependent**، وضع `StudyHours` في **Independent(s)**.
5. من **Statistics** يمكنك تحديد **Estimates** و**Model fit**، ثم اضغط **Continue → OK**.
6. اقرأ نتائج **Model Summary** و**ANOVA** و**Coefficients**، وقارنها بالحساب المتوقع أدناه.

<div align="center">
<img src="https://higherlogicdownload.s3.amazonaws.com/IMWUC/UploadedImages/whOqiC1CTyvBUXPTjC0W_Clip_614-L.jpeg" alt="لقطة حقيقية لنافذة الانحدار الخطي في IBM SPSS Statistics" width="82%"/>
</div>

<small>لقطة فعلية من [IBM Community](https://community.ibm.com/community/user/discussion/ibm-spss-26-are-all-prediction-models-available-in-spss) توضح موقع المتغير التابع والمتغيرات المستقلة. قد تختلف النافذة بحسب الإصدار؛ يوجد [رسم توضيحي احتياطي](images/04-linear-regression.svg).</small>

</div>

```text
Simple Linear Regression

Y = b0 + b1 X + error

Estimated equation:
ExamScore = 0.90 + 1.10 × StudyHours

R Square ≈ 0.818
```

<div dir="rtl" align="right">

**قراءة النتيجة:** في البيانات التعليمية الخمس، تزداد الدرجة المتوقعة بمقدار **1.10** تقريبًا مقابل كل ساعة إضافية من الدراسة وفق النموذج الخطي. ويقارب `R Square` نسبة **81.8%** من تباين درجات المثال. لا تستخدم هذه العينة الصغيرة للاستنتاج بشأن أداء طلاب حقيقيين أو لإثبات علاقة سببية.

إذا أردت تكرار المثال بسرعة في SPSS يمكنك وضع الأمر التالي داخل **Syntax Editor** وتشغيله:

</div>

```spss
DATA LIST FREE / StudyHours ExamScore.
BEGIN DATA
1 2
2 3
3 5
4 4
5 7
END DATA.
EXECUTE.

REGRESSION
  /STATISTICS COEFF R ANOVA
  /DEPENDENT ExamScore
  /METHOD=ENTER StudyHours
  /RESIDUALS.
```

<div dir="rtl" align="right">

<a name="spss-example-output"></a>
### قراءة مخرجات المثال خطوة بخطوة (Output Viewer)

بعد الضغط على **OK** ستظهر النتائج في نافذة **SPSS Output Viewer**. ابدأ بجدول **Model Summary**، ثم **ANOVA**، ثم **Coefficients**. ولعرض **Durbin–Watson** ورسوم البواقي، افتح **Statistics** و**Plots** في نافذة Linear Regression، أو استخدم أمر Syntax الموضح أعلاه.

**صورة فعلية لنافذة Output Viewer تحتوي على جداول الانحدار:**

<div align="center">
<img src="https://stats.idre.ucla.edu/wp-content/uploads/2016/08/introreg_l1_25.png" alt="واجهة SPSS Output Viewer وجداول Model Summary وANOVA الفعلية — UCLA" width="88%"/>
</div>

<small>مصدر الصورة: [UCLA Statistical Consulting — Regression with SPSS](https://stats.oarc.ucla.edu/spss/seminars/introduction-to-regression-with-spss/introreg-lesson1/). **القيم في الصورة من المثال التعليمي الخاص بالمصدر، وليست قيم بيانات ساعات الدراسة الموجودة هنا.**</small>

#### 1. Model Summary — ماذا تعني جودة النموذج؟

<div align="center">
<img src="https://scales.arabpsychology.com/wp-content/uploads/2024/06/linear-regression-summary-table-in-spss-1024x962.png" alt="جداول SPSS Model Summary وANOVA وCoefficients في شاشة واحدة — مثال مستقل" width="86%"/>
</div>

<small>لقطة حقيقية لنتائج SPSS: [مصدر الصورة وشرح المخرجات](https://scales.arabpsychology.com/stats/what-is-the-summary-of-linear-regression-analysis-in-spss/). القيم المصورة تخص بيانات أخرى.</small>

**القيم المحسوبة من بيانات المثال الموجود في هذا الدليل:**

| Model | R | R Square | Adjusted R Square | Std. Error of the Estimate | Durbin–Watson |
| :---: | ---: | ---: | ---: | ---: | ---: |
| 1 | 0.904 | 0.818 | 0.757 | 0.949 | 3.274 |

- **R Square = 0.818:** النموذج يفسر نحو **81.8%** من التباين في درجات المثال الافتراضي.
- **Adjusted R Square = 0.757:** معامل تحديد معدل يأخذ عدد المتغيرات وحجم العينة في الاعتبار.
- **Std. Error = 0.949:** مقياس تقريبي لحجم أخطاء التقدير على مقياس المتغير التابع.
- **Durbin–Watson = 3.274:** يقيس نمط الارتباط الذاتي المتتابع في البواقي؛ الرقم المرتفع بالنسبة إلى 2 قد يشير إلى ارتباط ذاتي سالب عندما يكون لترتيب الحالات معنى. **لأن المثال يحتوي على خمس حالات افتراضية فقط، فلا يصح الاعتماد على هذه القيمة للحكم على وجود ارتباط ذاتي فعلي أو تعميم النتيجة.**

#### 2. ANOVA — هل نموذج الانحدار ككل دال إحصائيًا؟

| Source | Sum of Squares | df | Mean Square | F | Sig. |
| :--- | ---: | ---: | ---: | ---: | ---: |
| Regression | 12.100 | 1 | 12.100 | 13.444 | 0.035 |
| Residual | 2.700 | 3 | 0.900 | | |
| Total | 14.800 | 4 | | | |

**طريقة القراءة:** هنا **F = 13.444** و**Sig. = 0.035**؛ وبما أن 0.035 أصغر من 0.05، فالانحدار دال إحصائيًا في **العينة التعليمية الصغيرة** عند هذا المستوى، مع ضرورة الانتباه إلى الافتراضات وعدم تعميم النتيجة.

#### 3. Coefficients — كيف نكوّن المعادلة؟

| Predictor | B | Std. Error | Beta | t | Sig. |
| :--- | ---: | ---: | ---: | ---: | ---: |
| (Constant) | 0.900 | 0.995 | — | 0.905 | 0.432 |
| StudyHours | 1.100 | 0.300 | 0.904 | 3.667 | 0.035 |

من عمود **Unstandardized Coefficients (B)** نأخذ قيمة الثابت **0.900** ومعامل ساعات الدراسة **1.100**، فتكون المعادلة:

`ExamScore = 0.900 + (1.100 × StudyHours)`

إذا كانت ساعات الدراسة **4** فإن الدرجة المتوقعة **5.3** وفق النموذج التدريبي.

**صورة فعلية إضافية لنتائج الانحدار المتعدد، يظهر فيها عمود Durbin–Watson:**

<div align="center">
<img src="https://resdata.com.vn/public/upload/images/4_%20Ph%C3%A2n%20t%C3%ADch%20m%C3%B4%20h%C3%ACnh%20h%E1%BB%93i%20quy%20tuy%E1%BA%BFn%20t%C3%ADnh%20trong%20SPSS%20resdata.png" alt="صورة SPSS تحتوي على Model Summary وANOVA وCoefficients وDurbin-Watson في دراسة تعليمية مختلفة" width="86%"/>
</div>

<small>مصدر الصورة: [شرح لقراءة جداول الانحدار في SPSS](https://resdata.com.vn/bai-viet/148/phan-tich-va-doc-ket-qua-mo-hinh-hoi-quy-tuyen-tinh-boi-trong-spss-cap-nhat-2024). **هذا مثال آخر متعدد المتغيرات**؛ لا تستخدم قيم الصورة بدل نتائج المثال المحسوبة أعلاه.</small>

#### 4. Durbin–Watson والرسوم التشخيصية

لفحص البواقي داخل البرنامج افتح **Analyze → Regression → Linear → Statistics** واختر **Durbin–Watson**، ثم افتح **Plots** واختر Histogram وNormal probability plot، ويمكن رسم **ZRESID** مقابل **ZPRED** عند الحاجة.

<div align="center">
<img src="https://www.restore.ac.uk/srme/www/fac/soc/wie/research-new/srme/modules/mod3/14/spss_regression_stats_and_plots_setup.jpg" alt="لقطات فعلية لنوافذ SPSS Statistics وPlots وفيها Durbin-Watson وHistogram وNormal Probability Plot" width="86%"/>
</div>

<small>مصدر الصورة: [University of Warwick — Model Diagnostics](https://www.restore.ac.uk/srme/www/fac/soc/wie/research-new/srme/modules/mod3/14/index.html). تبيّن الصورة أماكن الخيارات داخل واجهة SPSS.</small>

<div align="center">
<img src="https://journals.sagepub.com/cms/10.1177/25152459251408046/asset/193031b9-0bd2-425b-8ddd-b8a13aa76460/assets/images/large/10.1177_25152459251408046-fig1.jpg" alt="صور فعلية لمخرجات فحص بواقي الانحدار: Normal P-P Plot وScatterplots" width="86%"/>
</div>

<small>مصدر الصورة: [منشور علمي في SAGE](https://journals.sagepub.com/doi/full/10.1177/25152459251408046). يوضح رسوم التشخيص في تحليل آخر؛ **ليست هذه الرسوم ناتجة عن بيانات المثال الصغير**.</small>

**كيف تقرأ الرسوم؟** في **Histogram** تراجع الشكل العام لتوزيع البواقي، وفي **Normal P–P Plot** تلاحظ مدى اقتراب النقاط من الخط القطري، أما **Residual Scatterplot** فتبحث فيه عن الأنماط أو تغير التشتت. لا يكفي أي رسم بمفرده لإثبات صحة النموذج.

للمزيد: [IBM — Linear Regression Statistics](https://www.ibm.com/docs/en/spss-statistics/30.0.0?topic=regression-linear-statistics) و[IBM — RESIDUALS Command](https://www.ibm.com/docs/en/spss-statistics/32.0.0?topic=regression-residuals-subcommand-command).

<a name="spss-section-04"></a>
## 4. أسئلة متكررة عند الاستخدام

| المشكلة | ماذا تفعل؟ |
| :--- | :--- |
| لا يعمل ترخيص البرنامج | تحقق من نوع الترخيص واستخدم معالج التفعيل الرسمي أو الدعم الجامعي |
| لا يمكنك الضغط على **OK** | تأكد من وضع المتغيرات في المربعات الصحيحة |
| النتائج لا تظهر | افتح نافذة **Output Viewer** |
| المتغير لا يظهر في الاختبارات | افحص **Type** و**Measure** في Variable View |
| تختلف معادلة الانحدار | راجع إدخال البيانات والمتغير التابع والمستقل والقيم المفقودة |
| نتائج `ANOVA` مربكة | حدد هل تقرأ **ANOVA داخل الانحدار** أم تحليل مقارنة المتوسطات |

<a name="spss-section-05"></a>
## 5. المصادر الرسمية وروابط الاستخدام

- [IBM — SPSS Statistics](https://www.ibm.com/products/spss-statistics)
- [IBM — Documentation](https://www.ibm.com/docs/en/spss-statistics)
- [IBM — SPSS Statistics Resources](https://www.ibm.com/products/spss-statistics/resources)
- [IBM — Variable View](https://www.ibm.com/docs/en/spss-statistics/31.0.0?topic=editor-variable-view)
- [IBM — One-Way ANOVA](https://www.ibm.com/docs/en/spss-statistics/30.0.0?topic=features-one-way-anova)

[العودة إلى مركز أدلة البرامج](../../README.md)

---

### إعداد الدليل

**Talal bin Ibrahim Alsultan**  
*Applied Information System • Data Science • Decision Sciences*  
King Saud University

</div>