# دليل الـ Widgets الشامل لتطبيقات Flutter 📱✨
### مع تطبيق عملي ونماذج برمجية على تطبيق (BMI & Health Tracker)

تم إعداد هذا المستند كمرجع شامل ومنظم لجميع الـ **Widgets** والمفاهيم الأساسية في Flutter، مدعوماً بأمثلة عملية من تطبيق صحي تفاعلي (BMI & Fitness Tracker) لحساب مؤشر كتلة الجسم، مع شرح الـ **Provider & Controller** و **قواعد البيانات (Databases)**.

---

## 📑 فهرس الـ Widgets

| # | الـ Widget | التصنيف | الوظيفة الأساسية |
|:---:|:---|:---:|:---|
| 1 | `MaterialApp` | أساسي | تهيئة التطبيق وتحديد الشاشة الرئيسية والثيم العام |
| 2 | `Scaffold` | أساسي | الهيكل البنائي للشاشة (الخلفية، الشريط العلوي، المحتوى) |
| 3 | `AppBar` | أساسي | شريط العنوان العلوي في الشاشة |
| 4 | `SafeArea` | حسب الحاجة | حماية الواجهة من النتوءات (Notch) والحواف السفلية |
| 5 | `Container` | أساسي | صندوق متعدد الاستخدامات للتلوين والحواف والحدود والمسافات |
| 6 | `Column` | أساسي | ترتيب العناصر بشكل عمودي (رأسي) فوق بعضها |
| 7 | `Row` | أساسي | ترتيب العناصر بشكل أفقي جنباً إلى جنب |
| 8 | `Expanded` | أساسي | أخذ المساحة المتبقية داخل Row أو Column بنسبة الـ flex (والافتراضي بالتساوي) |
| 9 | `Flexible` | حسب الحاجة | إعطاء العنصر مرونة في المساحة دون إجباره على ملئها |
| 10 | `Padding` | أساسي | إضافة مسافات وفراغات داخلية حول المحتوى |
| 11 | `SizedBox` | أساسي | وضع فراغ ثابت بين العناصر أو إعطاء حجم محدد |
| 12 | `Text` | أساسي | عرض النصوص وتنسيق الخط والحجم واللون |
| 13 | `Icon` | أساسي | عرض أيقونة جاهزة من مكتبة Icons |
| 14 | `Card` | حسب الحاجة | بطاقة جاهزة بظلال وحواف دائرية (بديل لـ Container) |
| 15 | `Slider` | أساسي | شريط سحب لاختيار رقم ضمن نطاق محدد |
| 16 | `SliderTheme` | حسب الحاجة | تخصيص مظهر وألوان ومقبض شريط الـ Slider |
| 17 | `GestureDetector` | أساسي | التقاط ضغطات اللمس (onTap) على أي عنصر |
| 18 | `InkWell` | حسب الحاجة | التقاط اللمس مع تأثير موجي سلس (Ripple Effect) |
| 19 | `ElevatedButton` | أساسي | زر بارز ومرتفع للعمليات الأساسية |
| 20 | `IconButton / RawMaterialButton` | أساسي | أزرار تحتوي على أيقونات دائرية للتحكم بالقيم |
| 21 | `Center` | أساسي | توسيط العنصر في منتصف المساحة المتاحة |
| 22 | `SingleChildScrollView` | حسب الحاجة | إضافة إمكانية التمرير (Scroll) لمنع خطأ الـ Overflow |
| 23 | `Navigator (push / pop)` | أساسي | نظام التنقل بين الشاشات وتمرير البيانات والعودة |
| 24 | `StatelessWidget` | أساسي | ويدجت ثابت لا تتغير بياناته بعد البناء |
| 25 | `StatefulWidget` | أساسي | ويدجت تفاعلي يحتوي على حالة وبيانات تتغير عبر `setState()` |
| 26 | `ThemeData` | حسب الحاجة | توحيد الألوان والمظهر العام في كامل التطبيق |
| 27 | `TextField` / `TextFormField` | أساسي | حقل إدخال نصوص أو أرقام من المستخدم مع خيارات التنسيق والتحقق |
| 28 | `ListView` / `ListView.builder` | أساسي | عرض قوائم عناصر قابلة للتمرير بكفاءة عالية في الذاكرة |
| 29 | `GridView` / `GridView.builder` | أساسي | عرض شبكة من العناصر في صفوف وأعمدة |
| 30 | `ListTile` | أساسي | ويدجت جاهز ومثالي لصفوف القوائم (أيقونة، عنوان، وصف، سهم) |
| 31 | `Divider` | أساسي | خط أفقي رفيع يفصل بين العناصر |
| 32 | `Image` (`asset` / `network`) | أساسي | عرض الصور من مجلد المشروع المحلي أو عبر روابط الإنترنت |
| 33 | `CircleAvatar` | أساسي | دائرة مخصصة لصور البروفايل أو الحروف الشخصية |
| 34 | `Stack` & `Positioned` | أساسي | ترتيب ووضع العناصر فوق بعضها كطبقات ثلاثية الأبعاد |
| 35 | `Wrap` (ومقارنتها بـ `SingleChildScrollView`) | حسب الحاجة | ترتيب العناصر مع الانتقال التلقائي لسطر جديد عند امتلاء المساحة |
| 36 | `FloatingActionButton` (FAB) | أساسي | الزر الدائري العائم فوق المحتوى في زاوية الشاشة |
| 37 | `SnackBar` & `ScaffoldMessenger` | أساسي | شريط رسائل التنبيه المنبثق من أسفل الشاشة لثوانٍ |
| 38 | `AlertDialog` & `showDialog` | أساسي | نافذة حوار منبثقة في منتصف الشاشة تطلب تأكيد المستخدم |
| 39 | `Switch` | أساسي | زر تبديل تشغيل/إيقاف (On / Off) مثل تفعيل الوضع الليلي |
| 40 | `Checkbox` | أساسي | مربع اختيار علامة صح للموافقة على الشروط أو إتمام مهام |
| 41 | `DropdownButton` / `DropdownButtonFormField` | أساسي | قائمة منسدلة لاختيار عنصر واحد من بين عدة خيارات |
| 42 | `Form` & `GlobalKey<FormState>` | أساسي | حاوية تجميع وإدارة حقول الإدخال والتحقق من صحتها دفعة واحدة |

---

## 🔍 الشرح التفصيلي لكل Widget مع أمثلة الكود (تطبيق BMI & Health Tracker)

---

### 1. `MaterialApp`
* **وظيفته**: هو الـ Widget الجذري (Root Widget) لتطبيقات Flutter، يقوم بتهيئة التصميم (Material Design)، وتحديد شاشة البداية (`home`)، وضبط الثيم العام وتوجيه الصفحات.
* **مكان استخدامه**: في ملف `main.dart` لتشغيل التطبيق وتعيين الشاشة الأولى.
* **مثال من الكود**:
```dart
return MaterialApp(
  debugShowCheckedModeBanner: false,
  title: 'BMI Tracker',
  theme: ThemeData.dark().copyWith(
    scaffoldBackgroundColor: const Color(0xFF0A0E21),
    primaryColor: const Color(0xFF00E5FF),
  ),
  home: const InputScreen(),
);
```

---

### 2. `Scaffold`
* **وظيفته**: يوفر الهيكل التخطيطي الأساسي لأي صفحة (يحتوي على مساحات مخصصة لـ `appBar`، و `body`، و `bottomNavigationBar`، وخلفية الصفحة `backgroundColor`).
* **مكان استخدامه**: الهيكل الرئيسي لشاشة الإدخال وشاشة عرض النتيجة.
* **مثال من الكود**:
```dart
return Scaffold(
  backgroundColor: const Color(0xFF0A0E21),
  appBar: AppBar(...),
  body: SafeArea(...),
);
```

---

### 3. `AppBar`
* **وظيفته**: الشريط العلوي الثابت في أعلى الشاشة، يعرض عنوان الصفحة، وزر الرجوع، وأيقونات مساعدة.
* **مكان استخدامه**: لعرض عنوان التطبيق `BMI CALCULATOR` وزر الرجوع في شاشة النتيجة.
* **مثال من الكود**:
```dart
appBar: AppBar(
  backgroundColor: const Color(0xFF0A0E21),
  title: const Row(
    mainAxisSize: MainAxisSize.min,
    children: [
      Icon(Icons.monitor_weight_outlined, color: Color(0xFF00E5FF)),
      SizedBox(width: 8),
      Text('BMI CALCULATOR'),
    ],
  ),
  centerTitle: true,
)
```

---

### 4. `SafeArea`
* **وظيفته**: يحمي محتوى التطبيق من التداخل مع حواف الهواتف الحديثة، مثل نوتش الكاميرا العلوية (Notch) أو شريط التنقل السفلي الخاص بنظام التشغيل.
* **مكان استخدامه**: يغلف محتوى الـ `body` في كل شاشات التطبيق لضمان ظهور كل العناصر داخل المساحة الآمنة.
* **مثال من الكود**:
```dart
body: SafeArea(
  child: Column(...),
)
```

---

### 5. `Container`
* **وظيفته**: صندوق رسم وتنسيق متعدد المهام، يُستخدم لإعطاء خلفية ملونة، وحواف دائرية (`borderRadius`)، وحدود (`border`)، ومسافات داخلية (`padding`) وخارجية (`margin`).
* **مكان استخدامه**: في بطاقات اختيار الجنس، وبطاقة الطول، وبطاقة النتيجة الكبيرة.
* **مثال من الكود**:
```dart
Container(
  margin: const EdgeInsets.all(4.0),
  padding: const EdgeInsets.symmetric(vertical: 20.0),
  decoration: BoxDecoration(
    color: isSelected ? const Color(0xFF1D1E33) : const Color(0xFF111328),
    borderRadius: BorderRadius.circular(12.0),
    border: isSelected ? Border.all(color: const Color(0xFF00E5FF), width: 2.0) : null,
  ),
  child: Column(...),
)
```

---

### 6. `Column`
* **وظيفته**: ترتيب مجموعة من العناصر رأسياً (فوق بعضها البعض من الأعلى إلى الأسفل).
* **مكان استخدامه**: لترتيب أقسام الشاشة الرئيسية (بطاقات الجنس ⬅️ شريط الطول ⬅️ بطاقات الوزن والعمر ⬅️ زر الحساب).
* **مثال من الكود**:
```dart
Column(
  children: [
    Row(...),       // Gender cards
    Container(...), // Height slider card
    Row(...),       // Weight & age cards
  ],
)
```

---

### 7. `Row`
* **وظيفته**: ترتيب مجموعة من العناصر أفقياً (جنباً إلى جنب من اليسار إلى اليمين).
* **مكان استخدامه**: لوضع بطاقتي `Male` و `Female` بجانب بعضهما، وبطاقتي `Weight` و `Age`، وأزرار (+) و (-).
* **مثال من الكود**:
```dart
Row(
  children: [
    GenderCard(label: 'MALE', icon: Icons.male),
    GenderCard(label: 'FEMALE', icon: Icons.female),
  ],
)
```

---

### 8. `Expanded`
* **وظيفته**: يجبر العنصر الداخلي على التمدد ليأخذ المساحة المتبقية داخل `Row` أو `Column` بنسبة معامل الـ `flex` (وقيمته الافتراضية `1`، فإذا كانت كل العناصر تحمله تتوزع المساحة المتبقية بالتساوي).
* **مكان استخدامه**: وضع بطاقتي الجنس وبطاقتي الوزن والعمر ليأخذ كل منهما 50% من عرض الشاشة مهما اختلف حجم الهاتف (لأن كلاهما يحمل القيمة الافتراضية `flex: 1`).
* **مثال من الكود**:
```dart
return Expanded(
  child: GestureDetector(...),
);
```

---

### 9. `Flexible`
* **وظيفته**: يمنح العنصر مرونة في التمدد دون إجباره على ملء المساحة بالكامل، مما يمنع انكسار النصوص الطويلة أو العناصر المرنة داخل الصفوف.

---

### 10. `Padding`
* **وظيفته**: إضافة مسافة داخلية فارغة تفصل بين إطار العنصر ومحتواه الداخلي.
* **مكان استخدامه**: حول النصوص التوجيهية في شاشة النتيجة، وحول أرقام البداية والنهاية في شريط الـ Slider.
* **مثال من الكود**:
```dart
Padding(
  padding: const EdgeInsets.symmetric(horizontal: 16.0),
  child: Row(
    mainAxisAlignment: MainAxisAlignment.spaceBetween,
    children: [Text('120 cm'), Text('220 cm')],
  ),
)
```

---

### 11. `SizedBox`
* **وظيفته**: إنشاء صندوق بأبعاد ثابتة محددة (`height` و `width`)، ويُستخدم كأبسط وأفضل طريقة لعمل فواصل ومسافات فارغة بين العناصر.
* **مكان استخدامه**: لعمل مسافة رأسية بين البطاقات (`SizedBox(height: 12)`).
* **مثال من الكود**:
```dart
const SizedBox(height: 12);
```

---

### 12. `Text`
* **وظيفته**: عرض النصوص على الشاشة وتحديد خصائص الخط عبر خاصية `style: TextStyle(...)`.
* **مكان استخدامه**: لعرض قيمة المؤشر مثل `'22.4'`, ورسالة التقييم `'NORMAL WEIGHT'`.
* **مثال من الكود**:
```dart
Text(
  bmiResult.toStringAsFixed(1),
  style: const TextStyle(
    fontSize: 54,
    fontWeight: FontWeight.bold,
    color: Colors.white,
  ),
)
```

---

### 13. `Icon`
* **وظيفته**: رسم أيقونة جاهزة من مكتبة فلاتر مع سهولة تعديل حجمها ولونها.
* **مكان استخدامه**: أيقونات `Icons.male` و `Icons.female`، وأيقونات الزيادة والنقصان `Icons.add` و `Icons.remove`.
* **مثال من الكود**:
```dart
Icon(
  Icons.favorite_rounded,
  size: 48,
  color: Color(0xFF00E5FF),
)
```

---

### 14. `Card`
* **وظيفته**: ويدجت جاهز يقدم بطاقة ذات حواف دائرية وظلال مسبقة (بديل سريع لـ `Container`).

---

### 15. `Slider`
* **وظيفته**: شريط سحب تفاعلي لاختيار قيمة محددة بين حد أدنى (`min`) وحد أقصى (`max`).
* **مكان استخدامه**: لاختيار الطول بالسنتيمتر من 120 cm إلى 220 cm.
* **مثال من الكود**:
```dart
Slider(
  value: height.toDouble(),
  min: 120.0,
  max: 220.0,
  onChanged: (double newValue) {
    setState(() {
      height = newValue.round();
    });
  },
)
```

---

### 16. `SliderTheme`
* **وظيفته**: غلاف مخصص لتعديل شكل وألوان ومقبض شريط الـ `Slider`.
* **مكان استخدامه**: لجعل مقبض السحب والمسار النشط باللون السماوي المشع (`#00E5FF`).
* **مثال من الكود**:
```dart
SliderTheme(
  data: SliderTheme.of(context).copyWith(
    activeTrackColor: const Color(0xFF00E5FF),
    thumbColor: const Color(0xFF00E5FF),
    overlayColor: const Color(0x3300E5FF),
    trackHeight: 4.0,
  ),
  child: Slider(...),
)
```

---

### 17. `GestureDetector`
* **وظيفته**: التقاط حركات وإيماءات اللمس من المستخدم (مثل النقرة الواحدة `onTap`) على أي عنصر ليس زراً في الأصل.
* **مكان استخدامه**: حول بطاقتي `MALE` و `FEMALE` لاختيار إحداهما عند الضغط.
* **مثال من الكود**:
```dart
GestureDetector(
  onTap: () {
    setState(() {
      selectedGender = 'male';
    });
  },
  child: Container(...),
)
```

---

### 18. `InkWell`
* **وظيفته**: يشبه `GestureDetector` في التقاط النقرات، ولكنه يضيف تأثيراً موجياً متحركاً (Ripple Effect) عند لمس البطاقة.

---

### 19. `ElevatedButton`
* **وظيفته**: زر بارز ومرتفع للعمليات الأساسية.
* **مكان استخدامه**: الزر العريض أسفل الشاشات: `CALCULATE BMI` وزر `RE-CALCULATE`.
* **مثال من الكود**:
```dart
ElevatedButton(
  style: ElevatedButton.styleFrom(
    backgroundColor: const Color(0xFF00E5FF),
    shape: RoundedRectangleBorder(
      borderRadius: BorderRadius.circular(12),
    ),
  ),
  onPressed: onCalculate,
  child: const Text('CALCULATE BMI'),
)
```

---

### 20. `IconButton / RawMaterialButton`
* **وظيفته**: زر يحتوي على أيقونة. استُخدم `RawMaterialButton` لإنشاء أزرار دائرية مخصصة بحجم دقيق وثابت.
* **مكان استخدامه**: أزرار (+) و (-) لتعديل الوزن والعمر.
* **مثال من الكود**:
```dart
RawMaterialButton(
  onPressed: onIncrement,
  elevation: 0,
  constraints: const BoxConstraints.tightFor(width: 44, height: 44),
  shape: const CircleBorder(),
  fillColor: const Color(0xFF4C4F5E),
  child: const Icon(Icons.add, color: Colors.white, size: 22),
)
```

---

### 21. `Center`
* **وظيفته**: محاذاة العنصر ليقع بالضبط في منتصف المساحة المتاحة رأسياً وأفقياً.
* **مكان استخدامه**: لتوسيط النصوص والأرقام داخل البطاقات.

---

### 22. `SingleChildScrollView`
* **وظيفته**: يتيح تمرير المحتوى (Scroll) رأسياً أو أفقياً لمنع ظهور خطأ المساحة الشهير **(RenderFlex overflow)** على الهواتف الصغيرة أو عند تدوير الشاشة.
* **مكان استخدامه**: يغلف الـ `Column` الرئيسي في شاشات التطبيق.
* **مثال من الكود**:
```dart
SingleChildScrollView(
  padding: const EdgeInsets.symmetric(horizontal: 16.0, vertical: 8.0),
  child: Column(...),
)
```

---

### 23. `Navigator (push / pop)`
* **وظيفته**: نظام إدارة الشاشات والملاحة في Flutter الذي يعمل بنظام المكدس (Stack):
  - `Navigator.push()`: فتح شاشة جديدة فوق الشاشة الحالية وتمرير البيانات إليها.
  - `Navigator.pop()`: إغلاق الشاشة الحالية والرجوع للشاشة السابقة.
* **مكان استخدامه**:
  - `push`: الانتقال من شاشة الإدخال إلى شاشة النتيجة مع تمرير قيمة الـ BMI.
  - `pop`: عند الضغط على زر `RE-CALCULATE` للعودة للشاشة الأولى.
* **مثال من الكود**:

الانتقال لشاشة النتيجة:
```dart
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (context) => ResultScreen(
      bmi: bmiResult,
      resultText: 'NORMAL',
      interpretation: 'You have a healthy body weight. Keep it up!',
    ),
  ),
);
```

العودة للشاشة السابقة:
```dart
Navigator.pop(context);
```

---

### 24. `StatelessWidget`
* **وظيفته**: ويدجت "عديم الحالة"، يُبنى مرة واحدة ولا تتغير بياناته داخلياً بعد إنشائه. يتميز بأنه سريع جداً وخفيف في استهلاك الذاكرة.
* **مكان استخدامه**: في شاشة عرض النتيجة `ResultScreen` والبطاقات المساعدة، لأنها فقط تعرض بيانات مرسلة إليها.

---

### 25. `StatefulWidget`
* **وظيفته**: ويدجت "ذو حالة"، يحتوي على متغيرات تتغير أثناء استخدام التطبيق، وتُحدث الواجهة باستدعاء دالة `setState()`.
* **مكان استخدامه**: في شاشة الإدخال `InputScreen` (تعديل الطول بالسلايدر، والوزن، والعمر، واختيار الجنس).
* **مثال من الكود**:
```dart
setState(() {
  weight++;
});
```

---

### 26. `ThemeData`
* **وظيفته**: توحيد المظهر اللوني والخطوط في كامل التطبيق من مكان واحد في `main.dart`.
* **مثال من الكود**:
```dart
theme: ThemeData.dark().copyWith(
  scaffoldBackgroundColor: const Color(0xFF0A0E21),
)
```

---

### 27. `TextField` & `TextFormField`
* **وظيفته**: عنصر إدخال النصوص والأرقام والبيانات من المستخدم عبر لوحة المفاتيح التفاعلية.
* **الفرق بينهما**:
  - **`TextField`**: حقل إدخال نصوص مباشر وسريع للمهام العادية.
  - **`TextFormField`**: نسخة متطورة ترتبط بـ `Form`، وتدعم خاصية التحقق من صحة المدخلات (`validator`) لإظهار رسالة خطأ تلقائية باللون الأحمر إذا كان الإدخال فارغاً أو غير صحيح.
* **أهم الخصائص (Key Properties)**:
  - `controller`: ربط الحقل بـ `TextEditingController` لقراءة ما كتبه المستخدم أو مسحه برمجياً.
  - `keyboardType`: تحديد نوع لوحة المفاتيح (`TextInputType.number` للأرقام، أو `TextInputType.emailAddress` للبريد، أو `TextInputType.text`).
  - `obscureText: true`: إخفاء الأحرف بنجوم (تُستخدم لحقول كلمات المرور Password).
  - `decoration: InputDecoration(...)`: لتنسيق شكل الحقل بالكامل:
    - `hintText`: النص التوضيحي الباهت داخل الحقل (Placeholder).
    - `labelText`: عنوان الحقل الذي يرتفع للأعلى عند الكتابة.
    - `prefixIcon`: أيقونة تظهر في بداية الحقل من الداخل.
    - `suffixIcon`: أيقونة في نهاية الحقل (مثل زر إظهار/إخفاء كلمة المرور).
    - `border`, `enabledBorder`, `focusedBorder`: تخصيص شكل ولون الحدود عند التركيز أو الابتعاد.
    - `filled` و `fillColor`: تلوين خلفية الحقل.
  - `onChanged`: دالة تلتقط كل حرف يكتبه المستخدم لحظياً.
* **مثال عملي من الكود (حقل إدخال وزن أو اسم مخصص بتصميم داكن وإطار سمائي)**:
```dart
TextField(
  controller: weightInputController,
  keyboardType: TextInputType.number,
  style: const TextStyle(color: Colors.white, fontSize: 18),
  decoration: InputDecoration(
    filled: true,
    fillColor: const Color(0xFF1D1E33),
    labelText: 'Enter Weight (kg)',
    labelStyle: const TextStyle(color: Color(0xFFB0BEC5)),
    hintText: 'e.g. 70',
    hintStyle: const TextStyle(color: Colors.white38),
    prefixIcon: const Icon(Icons.fitness_center, color: Color(0xFF00E5FF)),
    border: OutlineInputBorder(
      borderRadius: BorderRadius.circular(12),
      borderSide: BorderSide.none,
    ),
    focusedBorder: OutlineInputBorder(
      borderRadius: BorderRadius.circular(12),
      borderSide: const BorderSide(color: Color(0xFF00E5FF), width: 2),
    ),
  ),
  onChanged: (value) {
    print('User typed: $value');
  },
)
```

---

### 28. `ListView` & `ListView.builder`
* **وظيفته**: أشهر وأهم ويدجت لعرض قوائم العناصر القابلة للتمرير (Scrollable Lists).
* **الفرق بينهما**:
  - `ListView(children: [...])`: يقوم بتحميل كل العناصر دفعة واحدة في الذاكرة (مناسب للقوائم الصغيرة الثابتة مثل صفحة الإعدادات).
  - `ListView.builder`: يبني العناصر عند الحاجة فقط أثناء التمرير (**Lazy Loading**)، وهو الأفضل للأداء مع القوائم الطويلة أو اللانهائية القادمة من الـ API أو قاعدة البيانات.
* **مثال كود**:
```dart
ListView.builder(
  itemCount: historyList.length,
  itemBuilder: (context, index) {
    return ListTile(
      title: Text('Record #${index + 1}'),
      subtitle: Text('Score: ${historyList[index]}'),
    );
  },
)
```

---

### 29. `GridView` & `GridView.builder`
* **وظيفته**: عرض العناصر في شبكة منظمة من صفوف وأعمدة قابلة للتمرير (Grid).
* **مكان استخدامه**: معارض الصور، شبكات المنتجات في المتاجر، لوحة الأزرار في الآلة الحاسبة.
* **مثال كود**:
```dart
GridView.builder(
  gridDelegate: const SliverGridDelegateWithFixedCrossAxisCount(
    crossAxisCount: 2, // 2 columns
    crossAxisSpacing: 10,
    mainAxisSpacing: 10,
  ),
  itemCount: 6,
  itemBuilder: (context, index) => Container(color: const Color(0xFF1D1E33)),
)
```

---

### 30. `ListTile`
* **وظيفته**: ويدجت جاهز مصمم خصيصاً كصف نموذجي في القوائم وفقاً لـ Material Design، يوزع العناصر تلقائياً بمسافات قياسية:
  - `leading`: أيقونة أو صورة في البداية.
  - `title`: العنوان الرئيسي.
  - `subtitle`: سطر وصف توضيحي فرعي.
  - `trailing`: أيقونة في النهاية (مثل سهم `>` أو زر مفتاح).
  - `onTap`: للضغط على الصف بالكامل.
* **مثال كود**:
```dart
ListTile(
  leading: const Icon(Icons.history, color: Color(0xFF00E5FF)),
  title: const Text('Previous BMI Result', style: TextStyle(color: Colors.white)),
  subtitle: const Text('22.4 - Normal', style: TextStyle(color: Colors.grey)),
  trailing: const Icon(Icons.arrow_forward_ios, size: 16),
  onTap: () {},
)
```

---

### 31. `Divider`
* **وظيفته**: رسم خط أفقي رفيع وأنيق يفصل بين العناصر أو الأقسام في القوائم والبطاقات.
* **أهم خصائصه**: `thickness` (سُمك الخط)، و `color` (لون الخط)، و `height` (المسافة الرأسية الإجمالية حوله).
* **مثال كود**:
```dart
const Divider(color: Colors.white24, thickness: 1, height: 20);
```

---

### 32. `Image` (`Image.asset` & `Image.network`)
* **وظيفته**: عرض الصور الثابتة والمتحركة (PNG, JPG, WebP, GIF) في التطبيق.
* **النوعان الأساسيان**:
  - `Image.asset('assets/images/logo.png')`: لتحميل الصور المخزنة داخل مجلدات المشروع محلياً (بعد تعريفها في `pubspec.yaml`).
  - `Image.network('https://example.com/photo.jpg')`: لتحميل وعرض الصور مباشرة عبر رابط إنترنت مع إمكانية إضافة `loadingBuilder`.
* **مثال كود**:
```dart
Image.network(
  'https://images.unsplash.com/photo-1517838277536-f5f99be501cd',
  height: 120,
  fit: BoxFit.cover,
)
```

---

### 33. `CircleAvatar`
* **وظيفته**: ويدجت دائري الشكل مخصص لعرض صور الملف الشخصي (Profile Avatars) أو الأيقونات أو الأحرف الأولى من اسم المستخدم.
* **أهم خصائصه**: `radius` (نصف قطر الدائرة)، و `backgroundImage` (صورة الخلفية)، و `backgroundColor`.
* **مثال كود**:
```dart
const CircleAvatar(
  radius: 35,
  backgroundColor: Color(0xFF00E5FF),
  child: Icon(Icons.person, size: 40, color: Color(0xFF0A0E21)),
)
```

---

### 34. `Stack` & `Positioned`
* **وظيفته**: ترتيب وتركيب العناصر **فوق بعضها البعض كطبقات ثلاثية الأبعاد (Z-axis)** بدلاً من جانب بعضها.
* **`Positioned`**: ويدجت يُستخدم حصرياً داخل الـ `Stack` لتثبيت العنصر في مكان محدد بدقة (`top`, `bottom`, `left`, `right`).
* **أشهر استخداماته**: وضع علامة تنبيه حمراء صغيرة فوق أيقونة الجرس، أو كتابة نص فوق صورة خلفية.
* **مثال كود**:
```dart
Stack(
  children: [
    Container(width: 100, height: 100, color: Colors.blueGrey),
    const Positioned(
      top: 8,
      right: 8,
      child: CircleAvatar(radius: 6, backgroundColor: Colors.red),
    ),
  ],
)
```

---

### 35. `Wrap` (ومقارنتها بـ `SingleChildScrollView` مع `Column`)
* **سؤال المناقشة الشهير**: ما الفرق بين `Row` و `Wrap` و `SingleChildScrollView`؟
  1. **الـ `Row`**: يرص العناصر أفقياً في سطر واحد؛ إذا زاد عددها عن عرض الشاشة يحدث خطأ **(Overflow)** فوراً!
  2. **الـ `Wrap`**: الحل الذكي للـ `Row`؛ يرص العناصر أفقياً، وبمجرد أن تمتلئ الشاشة **ينزل تلقائياً للسطر التالي** (مثل الكلمات أو الـ Chips والوسوم).
  3. **`SingleChildScrollView` مع `Column`**: الحل الذكي للـ `Column`؛ عندما تزيد العناصر رأسياً عن طول الشاشة، يمنع الـ Overflow ويحول الصفحة إلى **قائمة قابلة للتمرير الرأسي (Scrollable)**.
* **مثال كود للـ Wrap**:
```dart
Wrap(
  spacing: 8.0, // Horizontal spacing
  runSpacing: 4.0, // Vertical spacing
  children: [
    Chip(label: Text('Fitness')),
    Chip(label: Text('Cardio')),
    Chip(label: Text('Hydration')),
    Chip(label: Text('Nutrition')),
  ],
)
```

---

### 36. `FloatingActionButton` (FAB)
* **وظيفته**: الزر الدائري البارز والعائم الذي يطفو في زاوية الشاشة فوق كل المحتويات، ويوضع داخل خاصية `floatingActionButton` في كلاس `Scaffold`.
* **مثال كود**:
```dart
Scaffold(
  floatingActionButton: FloatingActionButton(
    backgroundColor: const Color(0xFF00E5FF),
    onPressed: () {},
    child: const Icon(Icons.add, color: Color(0xFF0A0E21)),
  ),
)
```

---

### 37. `SnackBar` & `ScaffoldMessenger`
* **وظيفته**: شريط تنبيه خفيف يظهر من أسفل الشاشة لعدة ثوانٍ لإعلام المستخدم بنجاح عملية أو بوجود خطأ دون مقاطعة استخدامه للتطبيق.
* **مثال كود**:
```dart
ScaffoldMessenger.of(context).showSnackBar(
  const SnackBar(
    content: Text('Please fill all required fields!'),
    backgroundColor: Colors.redAccent,
    duration: Duration(seconds: 2),
  ),
);
```

---

### 38. `AlertDialog` & `showDialog`
* **وظيفته**: نافذة حوارية منبثقة تظهر في منتصف الشاشة مع تعتيم الخلفية، تطلب تأكيداً أو قراراً من المستخدم وتمنعه من التفاعل حتى يجيب.
* **مثال كود**:
```dart
showDialog(
  context: context,
  builder: (context) => AlertDialog(
    title: const Text('Reset Data?'),
    content: const Text('Are you sure you want to reset all inputs?'),
    actions: [
      TextButton(onPressed: () => Navigator.pop(context), child: const Text('Cancel')),
      ElevatedButton(onPressed: () => Navigator.pop(context), child: const Text('Reset')),
    ],
  ),
);
```

---

### 39. `Switch`
* **وظيفته**: زر تبديل ثنائي الحالة (تشغيل / إيقاف - On/Off).
* **أشهر استخداماته**: تفعيل الوضع الداكن (Dark Mode) أو تشغيل التنبيهات.
* **مثال كود**:
```dart
Switch(
  value: isDarkMode,
  activeColor: const Color(0xFF00E5FF),
  onChanged: (bool newValue) {
    setState(() {
      isDarkMode = newValue;
    });
  },
)
```

---

### 40. `Checkbox`
* **وظيفته**: مربع اختيار يضع علامة صح (`true / false`) عند النقر عليه.
* **أشهر استخداماته**: الموافقة على الشروط والأحكام، أو تتبع قائمة المهام المنجزة (Todo List).
* **مثال كود**:
```dart
Checkbox(
  value: isAgreed,
  activeColor: const Color(0xFF00E5FF),
  onChanged: (bool? newValue) {
    setState(() {
      isAgreed = newValue ?? false;
    });
  },
)
```

---

### 41. `DropdownButton` & `DropdownButtonFormField`
* **وظيفته**: قائمة منسدلة أنيقة تتيح للمستخدم اختيار عنصر واحد من بين قائمة من الخيارات دون أخذ مساحة كبيرة على الشاشة (مثل اختيار الدولة، أو فئة النشاط).
* **مثال كود**:
```dart
DropdownButton<String>(
  value: selectedCity,
  items: ['Cairo', 'Alexandria', 'Giza'].map((city) {
    return DropdownMenuItem(value: city, child: Text(city));
  }).toList(),
  onChanged: (newCity) {
    setState(() => selectedCity = newCity!);
  },
)
```

---

### 42. `Form` & `GlobalKey<FormState>`
* **وظيفته**: الحاوية الذكية التي تجمع كل حقول `TextFormField` في صفحة التسجيل، وتسمح بفحص صحة كل الحقول دفعة واحدة بنقرة زر واحدة عبر `formKey.currentState!.validate()`.
* **مثال كود**:
```dart
final _formKey = GlobalKey<FormState>();

Form(
  key: _formKey,
  child: Column(
    children: [
      TextFormField(
        validator: (value) => value!.isEmpty ? 'Field required' : null,
      ),
      ElevatedButton(
        onPressed: () {
          if (_formKey.currentState!.validate()) {
            print('All inputs are valid!');
          }
        },
        child: const Text('Submit'),
      ),
    ],
  ),
)
```

---

# 🧠 شرح الـ Controller والـ Provider في Flutter

---

## 1️⃣ ما هو الـ Controller؟
الـ **Controller** هو كلاس مستقل مسؤوليته **فصل منطق البيانات والعمليات الحسابية عن واجهة المستخدم (UI)**.
بدلاً من أن نكتب المتغيرات والحسابات داخل كود الشاشة، ننقلها داخل Controller مستقل (مثل `BmiController`).

---

## 2️⃣ ما هو الـ Provider؟
الـ **Provider** هو أشهر مكتبة لإدارة الحالة (**State Management**) في Flutter.
* يحل مشكلة تمرير البيانات يدوياً بين الشاشات المتعددة (**Prop Drilling**).
* يحل مشكلة إعادة بناء الشاشة كلها عند كل تغيير عبر `setState()`، حيث يقوم بتحديث الويدجت المستمع فقط.

---

## 3️⃣ مثال عملي: كود `BmiController` مع `ChangeNotifier`:

```dart
import 'package:flutter/material.dart';

class BmiController extends ChangeNotifier {
  String? selectedGender;
  int height = 170;
  int weight = 65;
  int age = 22;

  void setGender(String gender) {
    selectedGender = gender;
    notifyListeners(); // Notify listening widgets
  }

  void setHeight(int newHeight) {
    height = newHeight;
    notifyListeners();
  }

  void incrementWeight() {
    if (weight < 250) {
      weight++;
      notifyListeners();
    }
  }

  void decrementWeight() {
    if (weight > 30) {
      weight--;
      notifyListeners();
    }
  }

  // BMI calculation: weight / (height/100)^2
  double get bmi {
    double heightInMeters = height / 100.0;
    return weight / (heightInMeters * heightInMeters);
  }

  String get resultText {
    if (bmi >= 25) return 'OVERWEIGHT';
    if (bmi > 18.5) return 'NORMAL';
    return 'UNDERWEIGHT';
  }
}
```

### استخدام الـ Provider في الواجهة:

1. تسجيل الـ Provider في أعلى شجرة التطبيق (`main.dart`):
```dart
ChangeNotifierProvider(
  create: (context) => BmiController(),
  child: const MyApp(),
)
```

2. قراءة القيمة في الشاشة (تحديث هذا الجزء فقط):
```dart
Consumer<BmiController>(
  builder: (context, controller, child) {
    return Text('${controller.weight} kg');
  },
)
```

3. استدعاء الدالة عند الضغط على زر (+):
```dart
RawMaterialButton(
  onPressed: () {
    context.read<BmiController>().incrementWeight();
  },
  child: const Icon(Icons.add),
)
```

---

# 💾 دليل قواعد البيانات في Flutter (Databases Guide)

---

## 1️⃣ قواعد البيانات المحلية (Local Databases - أوفلاين)
تعمل مباشرة على هاتف المستخدم بدون إنترنت:

### أ) `SharedPreferences` (Key-Value)
* **استخدامها**: لتخزين قيم بسيطة مثل إعدادات المستخدم (الوضع الليلي Dark Mode، اختيار وحدة الطول cm أو inch، توكن الدخول).
```dart
final prefs = await SharedPreferences.getInstance();
await prefs.setInt('last_height', 175);
int? lastHeight = prefs.getInt('last_height');
```

### ب) `Hive` (NoSQL فائقة السرعة)
* **استخدامها**: تخزين كائنات وسجلات بدون أكواد SQL، وتعتمد على نظام الصناديق (`Boxes`).
```dart
var box = await Hive.openBox('fitnessBox');
box.put('today_bmi', 22.4);
double savedBmi = box.get('today_bmi', defaultValue: 0.0);
```

### ج) `sqflite` (قواعد بيانات علائقية SQL كاملة)
* **استخدامها**: للتطبيقات التي تحتوي على جداول وتقارير وسجلات متعددة.
```dart
Database db = await openDatabase('fitness.db');
await db.execute('''
  CREATE TABLE history (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    bmi REAL,
    date TEXT
  )
''');
```

---

## 2️⃣ قواعد البيانات السحابية (Cloud Databases - أونلاين)
* **`Firebase Cloud Firestore`**: قاعدة بيانات NoSQL سحابية من Google، ميزتها الكبرى هي المزامنة اللحظية (Realtime Sync) لبيانات المستخدم بين عدة أجهزة فوراً.
* **`Supabase`**: بديل مجاني ومفتوح المصدر مبني على قاعدة بيانات علائقية قوية (**PostgreSQL**).


---

# 🛠️ الدليل العملي: طريقة كتابة الـ Widgets من الصفر إلى الاحتراف (من البداية للنهاية)

---

## 💡 أولاً: ما هي الـ Widget وكيف يفهمها Flutter؟

في Flutter: **"كل شيء عبارة عن Widget" (Everything is a Widget)**.
الشاشة، الزر، النص، المسافة، اللون، وحتى طريقة ترتيب العناصر داخل الصفحة كلها Widgets.

عند كتابة أي Widget، يمر الكود بـ 3 طبقات داخل محرك Flutter:
1. **Widget Tree**: كود التنسيق الذي تكتبه أنت (Blueprint / المخطط الهندسي).
2. **Element Tree**: الهيكل الذي يربط التنسيق بحالة الشاشة في الذاكرة.
3. **RenderObject Tree**: المحرك الرسومي الفعلي الذي يرسم البكسلات والألوان على شاشة الهاتف.

---

## 2️⃣ طريقة كتابة `StatelessWidget` خطوة بخطوة

يُستخدم عندما تكون الواجهة **ثابتة** ولا تحتوي على متغيرات تتغير قيمتها أثناء بقاء المستخدم في الشاشة (مثل بطاقة لعرض معلومات، زر مخصص، شريط عنوان).

### الهيكل القياسي لكتابة StatelessWidget:

```dart
// 1. Import Material library
import 'package:flutter/material.dart';

// 2. Class definition extending StatelessWidget
class CustomCard extends StatelessWidget {
  
  // 3. Immutable properties (must be final)
  final String title;
  final IconData icon;
  final VoidCallback onTap;

  // 4. Constructor using super.key for optimization
  const CustomCard({
    super.key,
    required this.title,
    required this.icon,
    required this.onTap,
  });

  // 5. Build method rendering the widget tree
  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: onTap,
      child: Container(
        padding: const EdgeInsets.all(16.0),
        decoration: BoxDecoration(
          color: const Color(0xFF1D1E33),
          borderRadius: BorderRadius.circular(12.0),
        ),
        child: Column(
          mainAxisSize: MainAxisSize.min,
          children: [
            Icon(icon, size: 40, color: const Color(0xFF00E5FF)),
            const SizedBox(height: 8),
            Text(
              title,
              style: const TextStyle(fontSize: 16, color: Colors.white),
            ),
          ],
        ),
      ),
    );
  }
}
```

### عناصر الكود الأساسية:
1. **`super.key`**: معرف فريد يساعد Flutter في التمييز بين الويدجتس وتحسين سرعة إعادة الرسم.
2. **`final`**: لأن الويدجت غير قابلة للتغيير (Immutable)، وكل مدخلاتها يجب أن تكون ثابتة بعد الإنشاء.
3. **`BuildContext context`**: خريطة توضح موقع هذا الويدجت بالضبط داخل شجرة التطبيق (Widget Tree).

---

## 3️⃣ طريقة كتابة `StatefulWidget` ودورة حياتها الكاملة (Lifecycle)

يُستخدم عندما تحتوي الشاشة على **بيانات متغيرة وتفاعلية** (مثل عداد، تبديل ألوان، حقل كتابة، شريط سحب).

يتكون الـ `StatefulWidget` دائماً من **كلاسين اثنين**:
1. الكلاس الأول (الـ Widget): يستقبل الإعدادات الثابتة ويُنشئ الحالة.
2. الكلاس الثاني (الـ State): يحتوي على المتغيرات ودورة الحياة ودالة `setState()`.

---

### الكود الكامل مع دورة الحياة (Lifecycle):

```dart
import 'package:flutter/material.dart';

// Class 1: Widget configuration
class CounterPage extends StatefulWidget {
  final String screenTitle;

  const CounterPage({super.key, required this.screenTitle});

  @override
  State<CounterPage> createState() => _CounterPageState();
}

// Class 2: State management & UI
class _CounterPageState extends State<CounterPage> {
  // 1. Mutable state variables
  int _counter = 0;
  late TextEditingController _textController;

  // 2. initState: called once when screen is first created
  @override
  void initState() {
    super.initState();
    _textController = TextEditingController();
  }

  // 3. didChangeDependencies: called after initState or when Theme/Provider changes
  @override
  void didChangeDependencies() {
    super.didChangeDependencies();
  }

  // 4. Method to update state and trigger rebuild
  void _increment() {
    setState(() {
      _counter++;
    });
  }

  // 5. build: renders UI whenever setState is called
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(widget.screenTitle),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            const Text('Current Value:', style: TextStyle(fontSize: 18)),
            Text(
              '$_counter',
              style: const TextStyle(fontSize: 48, fontWeight: FontWeight.bold),
            ),
            const SizedBox(height: 16),
            ElevatedButton(
              onPressed: _increment,
              child: const Text('Increment (+)'),
            ),
          ],
        ),
      ),
    );
  }

  // 6. dispose: called when screen is closed to free resources
  @override
  void dispose() {
    _textController.dispose();
    super.dispose();
  }
}
```

---

## 🔄 مراحل دورة حياة الـ StatefulWidget (Lifecycle Summary):

```text
[Screen Created]
       |
       v
1. createState()           --> Creates State object in memory
       |
       v
2. initState()             --> One-time setup & variables
       |
       v
3. didChangeDependencies() --> InheritedWidget & Theme bind
       |
       v
4. build()                 --> Renders widget tree to screen
       |
       v
   [setState() Called]     --> Re-runs build() on interaction
       |
       v
5. deactivate()            --> Widget removed temporarily
       |
       v
6. dispose()               --> Permanent disposal & memory cleanup
```

* **تفاصيل المراحل بالتسلسل**:
  1. `createState()`: إنشاء كائن الحالة (`State`) في الذاكرة عند استدعاء الويدجت.
  2. `initState()`: تهيئة المتغيرات والاشتراكات (`TextEditingController`, Listeners) لمرة واحدة فقط.
  3. `didChangeDependencies()`: تُستدعى بعد `initState` مباشرة، أو عند تغير حالة عامة (مثل الثيم أو الـ Provider).
  4. `build()`: المسؤولة عن رسم وتلوين شجرة الويدجتس وعرضها للمستخدم.
  * `setState()`: عند حدوث أي تفاعل، يتم استدعاؤها لإخبار فلاتر بإعادة تشغيل `build()` فقط لتحديث القيمة في الواجهة.
  5. `deactivate()`: عند نقل الويدجت أو إزالتها مؤقتاً من شجرة العناصر.
  6. `dispose()`: الإغلاق النهائي للشاشة وتفريغ الذاكرة ومسح الـ Controllers لمنع تسريب الذاكرة (Memory Leak).

---

## 4️⃣ كيف تصنع Custom Reusable Widget (ويدجت مخصصة قابلة لإعادة الاستخدام)؟

بدلاً من تكرار كود التصميم 5 مرات، نستخرجه في ملف مستقل بطريقة برمجية احترافية:

### الخطوات الذهبية لصنع أي Custom Widget:
1. **حدد الجزء المكرر**: (مثلاً بطاقة لها خلفية وإطار وأيقونة ونص).
2. **حدد ما هو متغير وما هو ثابت**:
   - الثابت: لون الخلفية، الحواف الدائرية، الظل.
   - المتغير: النص، الأيقونة، ماذا يحدث عند الضغط (`onTap`).
3. **أنشئ كلاس StatelessWidget جديد** واجعله يطلب هذه المتغيرات عبر الـ `Constructor`.
4. **استخدم الـ Widget في شاشتك الرئيسية بسهولة**:

```dart
Row(
  children: [
    CustomCard(
      title: 'Profile',
      icon: Icons.person,
      onTap: () => print('Profile clicked'),
    ),
    CustomCard(
      title: 'Settings',
      icon: Icons.settings,
      onTap: () => print('Settings clicked'),
    ),
  ],
)
```

---

## 📐 قاعدة القيود والأبعاد في فلاتر (قاعدة الـ Constraints):

> **"Constraints go down, sizes go up, parent sets position"**

تعتمد شجرة الواجهة في فلاتر على هذه القاعدة الذهبية لتحديد حجم وموضع أي ويدجت في 3 خطوات بسيطة:

1. **الأب يرسل للابن حدود (Constraints go down)**:
   - الـ Parent يحدد للـ Child الحدود المتاحة له (الحد الأدنى والأقصى للطول والعرض: min/max width & height).
2. **الابن يختار حجمه ويرجعه للأب (Sizes go up)**:
   - الـ Child يقرر حجمه بناءً على تلك الحدود المسموحة، ويرجع الحجم المطلوب للـ Parent.
3. **الأب يحدد مكان الابن (Parent sets position)**:
   - الـ Parent يضع الـ Child في المكان المناسب على الشاشة وفقاً للتنسيق ومحاذاة الشاشة.

---

### ⚠️ أشهر خطأ ينتج بسبب القيود (Unbounded Height Error):

* **المشكلة**:
  محاولة وضع ويدجت تتمدد بلا نهاية مثل `Expanded` أو `ListView` داخل ويدجت تعطي أبناءها حرية تمدد لا نهائية رأسياً مثل `Column` أو `SingleChildScrollView`.
  - الأب يعطي قيوداً غير محدودة الارتفاع (`unbounded height`).
  - والابن يحاول التمدد لملء كل المساحة، فيحدث خطأ الانهيار الشهير:
  `Vertical viewport was given unbounded height` أو `RenderFlex children have non-zero flex but incoming height constraints are unbounded`.

* **الحل**:
  - إذا كان `ListView` داخل `Column`: نقوم بتغليفه داخل `Expanded` ليأخذ المساحة المتبقية فقط، أو نحدد حجمه باستخدام `shrinkWrap: true` مع `physics: const NeverScrollableScrollPhysics()`.
  - إذا كان داخل `SingleChildScrollView`: لا نستخدم `Expanded` داخله نهائياً؛ لأن التمرير بطبيعته غير محدود الارتفاع.

```dart
// Correct: Wrap ListView in Expanded inside Column
Column(
  children: [
    const Text('Header'),
    Expanded(
      child: ListView.builder(
        itemCount: 20,
        itemBuilder: (context, index) => ListTile(
          title: Text('Item $index'),
        ),
      ),
    ),
  ],
)
```

---

## ⚡ أفضل الممارسات عند كتابة الـ Widgets (Best Practices):

1. **استخدم `const` دائماً**:
   - استخدام `const` مع الويدجتس الثابتة يجعل Flutter يعيد استخدام نفس الـ Widget في الذاكرة بدلاً من بنائها من جديد عند كل إعادة رسم (Rebuild)، مما يقلل شغل إعادة البناء ويحسّن الأداء، لكنها لا تضمن معدل فريمات معين.
2. **قسّم الواجهة لويدجتس صغيرة (Small Widgets)**:
   - بدلاً من كتابة ملف شاشة به 600 سطر، قسّمه إلى عدة ويدجتس صغيرة منفصلة.
3. **لا تضع عمليات ثقيلة داخل دالة `build()`**:
   - دالة `build()` تتكرر باستمرار؛ لا تضع فيها استدعاء API أو قراءة من قاعدة بيانات، بل ضع ذلك في `initState()` أو داخل `Controller`.
4. **تفريغ الموارد دائماً في `dispose()`**:
   - أي `TextEditingController` أو `AnimationController` أو `StreamSubscription` يجب إغلاقه بـ `.dispose()` لحماية الهاتف من استهلاك الذاكرة العشوائية (RAM).
