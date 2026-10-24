# Yemen Maize Production Prediction

## 1. Project Overview

This project studies annual maize production in Yemen using historical
agricultural data from 1961 to 2024. It includes data preparation,
temporal feature engineering, model evaluation, and forecasts for 2025–2027.

Forecasts are model estimates, not observed production values.

## 2. Main Objectives

- Organize historical maize production data.
- Examine harvested area, yield, production, and rainfall.
- Evaluate forecasting methods using the project's saved evaluation results.
- Compare model forecasts with simple baseline forecasts.
- Document data quality and uncertainty.

## 3. Project Structure

- `01_Raw_Data/`: Copies of source datasets and source archives.
- `02_Processed_Data/`: Prepared annual data and temporal features.
- `03_Train_Test_Splits/`: Reserved for documented training and evaluation splits.
- `04_Trained_Models/`: Reserved for serialized, reusable trained models.
- `05_Evaluation_Results/`: Saved model evaluation and comparison tables.
- `06_Forecasts/`: Forecast tables, including 2025–2027 predictions.
- `07_Figures/`: Project charts and visualizations.
- `08_Final_Report/`: Reserved for the final research report.
- `09_Documentation/`: Notebook, README, and supporting documentation.

## 4. Main Notebook

`Yemen_Maize_Prediction_Final.ipynb`

The notebook is stored in this documentation directory. Its integrity
was checked against the source copy using SHA-256.

## 5. Data Sources and Quality

The project includes FAOSTAT-derived agricultural data and annual rainfall
data. Rainfall coverage begins in 1981, while the maize production series
covers 1961–2024.

FAOSTAT status flags must be considered when interpreting observations.
In particular, `X` indicates an unofficial figure. Missing rainfall values
and source differences should be documented and handled explicitly.

## 6. Evaluation and Forecasting

Evaluation tables and forecast outputs are stored separately from the
processed input data. Review the evaluation protocol and time periods
before comparing metrics. Forecast values for 2025–2027 are predictions,
not confirmed observations.

## 7. Reproducibility Notes

- Original source files are retained in their original locations.
- Files copied into this directory are project-organizing copies.
- `03_Train_Test_Splits/` and `04_Trained_Models/` are reserved folders;
  their presence does not mean saved splits or serialized models exist.
- Verify the notebook's input paths before running it in a new environment.
- Avoid using future information when evaluating historical forecasts.

## 8. Limitations

Historical data may contain unofficial figures, missing values, or
differences between source versions. Forecasts should therefore be
interpreted with uncertainty and should not be treated as guaranteed
future production.

## 9. Current Organization Status

The raw data, processed data, evaluation tables, forecast tables, figures,
and final notebook have been copied into the project structure. Some
optional summary files were not found at their expected source paths and
require a separate search before they can be included.

## Scientific Note: Temporal Split and Experiment Comparability

### Chronological training and test split

The working notebook documents a chronological holdout evaluation.
In the documented experiment, observations through 2014 were used
for training, while the years 2015–2019 were reserved for final
holdout testing. The expected test years were explicitly checked
in the notebook.

This split applies to that specific experiment and should not be
assumed to describe every experiment or evaluation stage in the project.

### Distinguishing experiments and their metrics

The project contains outputs from multiple experimental stages,
including different feature configurations, model settings, and
evaluation procedures. Therefore, metric files from different stages
must not be merged or interpreted as if they came from one identical
experiment.

Before comparing metrics, verify at least:
- the experiment or notebook stage;
- the target variable and feature configuration;
- the model and its hyperparameters;
- the training and evaluation periods;
- the evaluation protocol, including holdout or walk-forward testing;
- the metric definition and units.

Results should be compared directly only when these conditions are
sufficiently consistent. Otherwise, report them separately and explain
the differences in experimental design.

### Interpretation and limitations

The holdout results for 2015–2019 are a separate evaluation of the
documented model configurations, not evidence that all later
experiments share the same performance. Negative R² values in the
reported holdout results indicate that those configurations performed
worse than predicting the mean of the observed test targets under
the R² definition. They should be reported transparently and should
not be hidden or combined with metrics from other stages.

Forecasts for 2025–2027 are model-generated estimates, not observed
production values. They must be presented separately from historical
test metrics. Data-quality flags and uncertainty in recent source
records should also be considered when interpreting the forecasts.

For reproducibility, each reported metric should be linked to its
corresponding prediction file, evaluation file, and notebook stage.

---

## النسخة العربية

# مشروع التنبؤ بإنتاج الذرة في اليمن

## 1. نظرة عامة على المشروع

يهدف هذا المشروع إلى تحليل بيانات إنتاج الذرة السنوية في اليمن، ودراسة التغيرات التاريخية في الإنتاج، والاستفادة من الميزات الزمنية وبيانات الأمطار المتاحة لتقييم أساليب التنبؤ بالإنتاج.

تتضمن ملفات المشروع بيانات خام، وبيانات معالجة، ونتائج تقييم، وتوقعات للسنوات المستقبلية، ورسومًا توضيحية، ودفتر عمل يوثق التحليلات والنتائج.

## 2. هيكل مجلد التسليم

- `01_Raw_Data`: البيانات الخام ومصادر البيانات الأصلية المتاحة.
- `02_Processed_Data`: البيانات المعالجة والميزات المستخدمة في التحليل.
- `03_Train_Test_Splits`: مخصص لحفظ ملفات بيانات التدريب والاختبار المنفصلة.
- `04_Trained_Models`: مخصص لحفظ ملفات النماذج المدرّبة عند الحاجة إلى تسليمها.
- `05_Evaluation_Results`: نتائج تقييم النماذج والمقاييس والمقارنات.
- `06_Forecasts`: ملفات التوقعات المستقبلية ونتائج المقارنة بينها.
- `07_Figures`: الرسوم البيانية المستخدمة في تحليل البيانات وعرض النتائج.
- `08_Final_Report`: مخصص للتقرير النهائي للمشروع.
- `09_Documentation`: دفتر العمل وملفات التوثيق.

وجود مجلد في الهيكل لا يعني بالضرورة أنه يحتوي على ملفات. يجب التحقق من محتوياته قبل اعتبار جميع مكونات التسليم مكتملة.

## 3. البيانات

يتضمن المشروع بيانات إنتاج الذرة السنوية للفترة 1961–2024، وبيانات الأمطار للفترة 1981–2024.

ينبغي مراعاة اختلاف الفترات الزمنية بين مصادر البيانات، والتحقق من القيم المفقودة وأعلام جودة البيانات قبل تدريب النماذج أو تفسير النتائج.

## 4. التدريب والاختبار

يحتوي دفتر العمل على تجربة تستخدم بيانات السنوات حتى 2014 للتدريب، والسنوات 2015–2019 للاختبار النهائي.

هذا التقسيم يخص التجربة الموثقة تحديدًا، ولا ينبغي افتراض أن جميع مراحل المشروع تستخدم التقسيم نفسه. يجب الرجوع إلى كود كل مرحلة وميزاتها وإعدادات النموذج وفترة التقييم المرتبطة بها.

كما ينبغي حفظ ملفات التدريب والاختبار المنفصلة عند إعداد نسخة التسليم، إذا أمكن إعادة إنتاجها بدقة من مصدر البيانات والكود المعتمدين.

## 5. تقييم النماذج ومقارنة النتائج

يحتوي مجلد `05_Evaluation_Results` على ملفات المقاييس والتنبؤات الناتجة عن مراحل تجريبية مختلفة.

قبل مقارنة أي نتيجتين، يجب التأكد من تطابق أو توضيح ما يلي:

- مرحلة التجربة والغرض منها.
- البيانات والميزات المستخدمة.
- النموذج ومعاملاته.
- فترة التدريب وفترة الاختبار.
- طريقة التقييم وتعريف المقاييس.

لا يجوز دمج نتائج مراحل مختلفة أو تقديمها على أنها تجربة واحدة دون التحقق من قابلية المقارنة بينها.

تشير قيمة \(R^2\) السالبة إلى أن النموذج كان أسوأ من استخدام متوسط القيم الفعلية في فترة التقييم، وفقًا لتعريف هذا المقياس. لذلك يجب تفسير النتائج في سياقها، وعدم الاعتماد على مقياس واحد فقط.

## 6. التوقعات المستقبلية

تتضمن ملفات المشروع توقعات لإنتاج الذرة للأعوام 2025–2027.

هذه القيم هي **توقعات وليست مشاهدات فعلية**، ويجب عرضها بوصفها تقديرات تعتمد على البيانات والافتراضات والنماذج المستخدمة. ولا ينبغي تفسيرها على أنها نتائج مؤكدة.

## 7. جودة البيانات وحدود المشروع

تعتمد موثوقية التوقعات على جودة البيانات التاريخية، ومدى اكتمالها، وصحة الميزات المستخدمة، واستقرار الأنماط عبر الزمن.

يجب مراعاة أعلام جودة البيانات، والقيم المفقودة، واختلاف مصادر البيانات، وعدم اليقين المرتبط بالسنوات الحديثة عند تفسير النتائج.

## 8. دفتر العمل

يحتوي `Yemen_Maize_Prediction_Final.ipynb` على التحليلات والنتائج والرسوم المحفوظة المستخدمة في نسخة التسليم.

ينبغي التمييز بين دفتر يوثق نتائج سبق إنتاجها ودفتر يعيد تنفيذ خطوات التدريب والتقييم من البداية. وجود النتائج المحفوظة لا يعني بالضرورة أن النموذج المدرّب محفوظ كملف مستقل.

## 9. ملاحظة علمية حول التقسيم الزمني وقابلية مقارنة التجارب

يُوثق تقسيم زمني يستخدم البيانات حتى عام 2014 للتدريب والسنوات 2015–2019 للاختبار النهائي في تجربة محددة. ولا يعني ذلك أن كل ملفات النتائج في المشروع ناتجة عن هذا التقسيم نفسه.

قبل المقارنة بين نتائج الملفات المختلفة، يجب التحقق من المرحلة التجريبية، والميزات، والنموذج ومعاملاته، وفترات التدريب والاختبار، وطريقة التقييم وتعريف المقاييس.

ينبغي تفسير قيم \(R^2\) السالبة بوصفها مؤشرًا على أداء أضعف من خط أساس يعتمد على متوسط القيم الفعلية، وفقًا لتعريف المقياس. كما يجب التعامل مع توقعات 2025–2027 على أنها تقديرات مستقبلية لا مشاهدات فعلية، مع مراعاة أعلام جودة البيانات.

## 10. قائمة تحقق قبل التسليم

- التأكد من وجود ملفات البيانات المطلوبة وعدم كونها فارغة.
- التحقق من إمكانية قراءة ملفات CSV.
- التأكد من وجود دفتر العمل وملف README.
- التحقق من وجود ملفات المقاييس والتنبؤات في مجلداتها الصحيحة.
- توثيق المرحلة التجريبية والفترة الزمنية لكل نتيجة.
- حفظ ملفات التدريب والاختبار المنفصلة عند توافرها وإمكانية إعادة إنتاجها بصورة موثوقة.
- إعداد التقرير النهائي إذا كان مطلوبًا ضمن التسليم.
- عدم اعتبار المشروع جاهزًا بالكامل لمجرد نجاح الفحص الأساسي للملفات؛ إذ يلزم أيضًا مراجعة صحة النتائج واكتمال التوثيق.

---
