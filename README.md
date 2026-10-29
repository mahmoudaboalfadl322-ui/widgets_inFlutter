# دليل الـ Widgets الشامل لتطبيق Daily Water Tracker 💧📱

تم إعداد هذا المستند كمرجع منظم وشامل لشرح جميع الـ **Widgets** المذكورة في تكليف المشروع (صفحات 9 و 10 و 11 من ملف التكليف)، مع توضيح وظيفة كل منها، ومكان استخدامها في الكود، وأمثلة عملية، والأسئلة المتوقعة في المناقشة الشفوية.

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
| 8 | `Expanded` | أساسي | ملء المساحة المتبقية داخل Row أو Column بالتساوي |
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

---

## 🔍 الشرح التفصيلي لكل Widget مع أمثلة الكود

---

### 1. `MaterialApp`
* **وظيفته**: هو الـ Widget الجذري (Root Widget) لتطبيقات Flutter، يقوم بتهيئة التصميم (Material Design)، وتحديد شاشة البداية (`home`)، وضبط الثيم العام وتوجيه الصفحات.
* **مكان استخدامه في مشروعنا**: في ملف `lib/main.dart` داخل دالة البناء في كلاس `MyApp`.
* **مثال من الكود**:
```dart
return MaterialApp(
  debugShowCheckedModeBanner: false,
  title: 'Water Tracker',
  theme: ThemeData.dark().copyWith(
    scaffoldBackgroundColor: kBgColor,
  ),
  home: const InputScreen(),
);
```

---

### 2. `Scaffold`
* **وظيفته**: يوفر الهيكل التخطيطي القياسي لأي صفحة (يحتوي على مساحات مخصصة لـ `appBar`، و `body`، و `bottomNavigationBar`، وخلفية الصفحة `backgroundColor`).
* **مكان استخدامه في مشروعنا**: كعنصر رئيسي في شاشتي التطبيق: `InputScreen` و `ResultScreen`.
* **مثال من الكود**:
```dart
return Scaffold(
  backgroundColor: kBgColor,
  appBar: AppBar(...),
  body: SafeArea(...),
);
```

---

### 3. `AppBar`
* **وظيفته**: الشريط العلوي الثابت في أعلى الشاشة، يعرض عنوان الصفحة، وزر الرجوع، وأيقونات مساعدة.
* **مكان استخدامه في مشروعنا**: في أعلى شاشة الإدخال (`Water Tracker`) مع أيقونة الماء، وفي أعلى شاشة النتيجة (`Your Daily Water Intake`).
* **مثال من الكود**:
```dart
appBar: AppBar(
  backgroundColor: kBgColor,
  title: const Row(
    mainAxisSize: MainAxisSize.min,
    children: [
      Icon(Icons.water_drop, color: kAccentColor),
      SizedBox(width: 8),
      Text('Water Tracker'),
    ],
  ),
  centerTitle: true,
)
```

---

### 4. `SafeArea`
* **وظيفته**: يحمي محتوى التطبيق من التداخل مع حواف الهواتف الحديثة، مثل نوتش الكاميرا العلوية (Notch) أو شريط التنقل السفلي الخاص بنظام التشغيل.
* **مكان استخدامه في مشروعنا**: يغلف محتوى الـ `body` في كل من الشاشة الأولى وشاشة النتيجة.
* **مثال من الكود**:
```dart
body: SafeArea(
  child: Column(...),
)
```

---

### 5. `Container`
* **وظيفته**: صندوق رسم وتنسيق متعدد المهام، يُستخدم لإعطاء خلفية ملونة، وحواف دائرية (`borderRadius`)، وحدود (`border`)، ومسافات داخلية (`padding`) وخارجية (`margin`).
* **مكان استخدامه في مشروعنا**: بطاقات الجنس، بطاقة الـ Slider، بطاقة النتيجة الكبيرة، وحاوية إخلاء المسؤولية.
* **مثال من الكود**:
```dart
Container(
  margin: const EdgeInsets.all(4.0),
  padding: const EdgeInsets.symmetric(vertical: 20.0),
  decoration: BoxDecoration(
    color: isSelected ? kActiveCardColor : kInactiveCardColor,
    borderRadius: BorderRadius.circular(12.0),
    border: isSelected ? Border.all(color: kAccentColor, width: 2.0) : null,
  ),
  child: Column(...),
)
```

---

### 6. `Column`
* **وظيفته**: ترتيب مجموعة من العناصر رأسياً (فوق بعضها البعض من الأعلى إلى الأسفل).
* **مكان استخدامه في مشروعنا**: في الشاشة الرئيسية لترتيب (بطاقات الجنس ⬅️ الـ Slider ⬅️ بطاقات الوزن/العمر ⬅️ زر الحساب).
* **مثال من الكود**:
```dart
Column(
  children: [
    Row(...),       // بطاقات الجنس
    Container(...), // شريط النشاط
    Row(...),       // الوزن والعمر
  ],
)
```

---

### 7. `Row`
* **وظيفته**: ترتيب مجموعة من العناصر أفقياً (جنباً إلى جنب من اليسار إلى اليمين).
* **مكان استخدامه في مشروعنا**: لوضع بطاقتي `Male` و `Female` بجانب بعضهما، وبطاقتي `Weight` و `Age`، وأزرار (+) و (-).
* **مثال من الكود**:
```dart
Row(
  children: [
    GenderCard(label: 'MALE', ...),
    GenderCard(label: 'FEMALE', ...),
  ],
)
```

---

### 8. `Expanded`
* **وظيفته**: يجبر العنصر الداخلي على التمدد ليأخذ كل المساحة المتاحة في الـ `Row` أو `Column`. وإذا وضعنا اثنين `Expanded` في `Row` فسيتقاسمان العرض بنسبة 50% لكل منهما بالضبط.
* **مكان استخدامه في مشروعنا**: داخل كلاس `GenderCard` وكلاس `CounterCard` لضمان أن تأخذ البطاقات نصف عرض الشاشة بالتساوي مهما اختلف حجم الهاتف.
* **مثال من الكود**:
```dart
return Expanded(
  child: GestureDetector(...),
);
```

---

### 9. `Flexible`
* **وظيفته**: يشبه `Expanded` لكنه يعطي العنصر مرونة للتمدد بدون إلزامه بملء المساحة كلها إن لم يكن محتواها بحاجة لها (يسمح للعنصر بأخذ حجمه الطبيعي بحد أقصى المساحة المتاحة).
* **فائدته**: حماية النصوص الطويلة أو العناصر المرنة من كسر حدود الشاشة.

---

### 10. `Padding`
* **وظيفته**: إضافة مسافة بيضاء داخلية فارغة تفصل بين إطار العنصر ومحتواه الداخلي.
* **مكان استخدامه في مشروعنا**: حول أرقام الـ Slider (`0 h` و `8 h`)، وداخل شاشة النتيجة، وحول عناصر ملخص المدخلات.
* **مثال من الكود**:
```dart
Padding(
  padding: const EdgeInsets.symmetric(horizontal: 16.0),
  child: Row(
    mainAxisAlignment: MainAxisAlignment.spaceBetween,
    children: [Text('0 h'), Text('8 h')],
  ),
)
```

---

### 11. `SizedBox`
* **وظيفته**: إنشاء صندوق بأبعاد ثابتة محددة (`height` و `width`)، ويُستخدم كأبسط وأفضل طريقة لوضع فواصل ومسافات فارغة بين العناصر.
* **مكان استخدامه في مشروعنا**: لعمل فراغ رأسي بين البطاقات (`SizedBox(height: 12)`) أو أفقي بين الأزرار (`SizedBox(width: 8)`).
* **مثال من الكود**:
```dart
const SizedBox(height: 12);
```

---

### 12. `Text`
* **وظيفته**: عرض النصوص على الشاشة وتحديد مواصفاتها عبر خاصية `style: TextStyle(...)` مثل الحجم واللون والسمك ومحاذاة النص `textAlign`.
* **مكان استخدامه في مشروعنا**: في كل مكان لعرض العناوين والأرقام، مثل `'3.56 L / Day'` ونصوص التوجيه.
* **مثال من الكود**:
```dart
Text(
  '${litres.toStringAsFixed(2)} L / Day',
  style: const TextStyle(
    fontSize: 38,
    fontWeight: FontWeight.bold,
    color: Colors.white,
  ),
)
```

---

### 13. `Icon`
* **وظيفته**: رسم أيقونة متجهية (Vector Icon) جاهزة من مكتبة فلاتر مع إمكانية تعديل حجمها ولونها بسهولة.
* **مكان استخدامه في مشروعنا**: قطرة الماء `Icons.water_drop`، وأيقونات الجنس `Icons.male` و `Icons.female`، وعلامات الزيادة والنقصان `Icons.add` و `Icons.remove`.
* **مثال من الكود**:
```dart
Icon(
  Icons.water_drop,
  size: 48,
  color: kAccentColor,
)
```

---

### 14. `Card`
* **وظيفته**: ويدجت جاهز من Material Design يقدم بطاقة بخلفية ملونة مع حواف وظلال افتراضية (Elevation).
* **علاقته بـ Container**: يعتبر بديلاً سريعاً لـ `Container`، ولكن تم تفضيل `Container` في مشروعنا لإعطاء تحكم كامل ودقيق في ألوان الحدود النشطة (`Border.all`) والظلال.

---

### 15. `Slider`
* **وظيفته**: شريط تمرير تفاعلي يسمح للمستخدم باختيار رقم بسلاسة بين حد أدنى (`min`) وحد أقصى (`max`).
* **مكان استخدامه في مشروعنا**: لتحديد ساعات النشاط الرياضي اليومية من 0 إلى 8 ساعات مع تقسيمها إلى 8 خطوات (`divisions: 8`).
* **مثال من الكود**:
```dart
Slider(
  value: activityHours,
  min: 0,
  max: 8,
  divisions: 8,
  onChanged: (val) {
    setState(() {
      activityHours = val;
    });
  },
)
```

---

### 16. `SliderTheme`
* **وظيفته**: غلاف مخصص يسمح بتعديل ألوان وأحجام كل تفاصيل الـ `Slider` (مثل مقبض السحب `thumbColor`، والمسار النشط `activeTrackColor`، والوهج الشفاف عند اللمس `overlayColor`).
* **مكان استخدامه في مشروعنا**: لإعطاء مقبض الـ Slider والمسار اللون السمائي المشع (`#00E5FF`).
* **مثال من الكود**:
```dart
SliderTheme(
  data: SliderTheme.of(context).copyWith(
    activeTrackColor: kAccentColor,
    inactiveTrackColor: Colors.white24,
    thumbColor: kAccentColor,
    overlayColor: const Color(0x3300E5FF),
    trackHeight: 4.0,
  ),
  child: Slider(...),
)
```

---

### 17. `GestureDetector`
* **وظيفته**: يتعرف على حركات وإيماءات اللمس من المستخدم (مثل النقرة الواحدة `onTap`، والنقرة المزدوجة `onDoubleTap`، والضغط المطول `onLongPress`) على أي عنصر ليس زراً في الأصل.
* **مكان استخدامه في مشروعنا**: حول بطاقتي `MALE` و `FEMALE` لتحويلهما إلى بطاقات تفاعلية يتم اختيارها عند الضغط.
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
* **وظيفته**: يشبه `GestureDetector` تماماً في التقاط الضغط `onTap`، ولكنه يضيف تأثير موجة مائية مرئية (Ripple / Splash Effect) عند لمس العنصر.
* **ملاحظة**: يمكن استبدال `GestureDetector` به بسهولة لإعطاء تفاعل ملموس إضافي.

---

### 19. `ElevatedButton`
* **وظيفته**: الزر الأساسي المرتفع في Material Design، له خلفية ملونة وتأثير ظل وشكل مخصص.
* **مكان استخدامه في مشروعنا**: الزر العريض في أسفل الشاشتين: زر `Calculate Water Intake` وزر `Re-calculate`.
* **مثال من الكود**:
```dart
ElevatedButton(
  style: ElevatedButton.styleFrom(
    backgroundColor: kAccentColor,
    shape: RoundedRectangleBorder(
      borderRadius: BorderRadius.circular(12),
    ),
  ),
  onPressed: onTap,
  child: Text(title, style: ...),
)
```

---

### 20. `IconButton / RawMaterialButton`
* **وظيفته**: زر يحتوي على أيقونة. استُخدم `RawMaterialButton` تحديداً لأنه يتيح صنع زر دائري الشكل بالكامل بحجم دقيق وثابت دون التقيد بهيكل الزر المستطيل.
* **مكان استخدامه في مشروعنا**: أزرار الزيادة والنقصان (+) و (-) داخل بطاقتي الوزن والعمر في `counter_card.dart`.
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
* **وظيفته**: يقوم بمحاذاة العنصر التابع له ليقع بالضبط في منتصف المساحة المتاحة رأسياً وأفقياً.
* **مكان استخدامه في مشروعنا**: لتوسيط النصوص والأيقونات داخل البطاقات وشريط العنوان.

---

### 22. `SingleChildScrollView`
* **وظيفته**: يحول المحتوى الرأسي أو الأفقي إلى قائمة قابلة للتمرير (Scrollable).
* **أهميته القصوى في التقييم**: هذا الـ Widget هو الحامي الأول من ظهور خطأ الشاشة الشهير **(RenderFlex overflowed)** أو الخطوط الصفراء والسوداء عند تشغيل التطبيق على هواتف ذات شاشات صغيرة أو عند تدوير الشاشة.
* **مكان استخدامه في مشروعنا**: يغلف الـ `Column` الرئيسي في الشاشة الأولى وشاشة النتيجة.
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
  - `Navigator.push()`: إضافة شاشة جديدة فوق الشاشة الحالية مع تمرير البيانات إليها.
  - `Navigator.pop()`: إزالة الشاشة الحالية والعودة للشاشة السابقة.
* **مكان استخدامه في مشروعنا**:
  - `Navigator.push`: عند الضغط على زر الحساب للانتقال من `InputScreen` إلى `ResultScreen`.
  - `Navigator.pop`: عند الضغط على زر `Re-calculate` للعودة للشاشة الأولى.
* **مثال من الكود**:
```dart
// الانتقال وتمرير البيانات:
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (context) => ResultScreen(
      litres: litres,
      weight: weight,
      age: age,
      activityHours: activityHours,
      gender: selectedGender == 'male' ? 'Male' : 'Female',
    ),
  ),
);

// العودة للشاشة السابقة:
Navigator.pop(context);
```

---

### 24. `StatelessWidget`
* **وظيفته**: ويدجت "عديم الحالة"، يُبنى مرة واحدة فقط ولا يحتوي على أي متغيرات قابلة للتغيير بعد إنشائه. يتميز بأنه سريع جداً وخفيف في استهلاك الذاكرة.
* **مكان استخدامه في مشروعنا**:
  - `ResultScreen`: لأنها تستقبل البيانات الجاهزة فقط وتعرضها دون تعديل.
  - `GenderCard`، `CounterCard`، `BottomButton`: لأنها مجرد قوالب تصميمية تستقبل دوال وقيم جاهزة من الشاشة الأم.

---

### 25. `StatefulWidget`
* **وظيفته**: ويدجت "ذو حالة"، يحتوي على بيانات قابلة للتغيير والتحديث أثناء استخدام التطبيق، ويعتمد على استدعاء دالة `setState()` لإعلام Flutter بضرورة إعادة بناء الواجهة (`rebuild`) لعكس التغيير الجديد على الشاشة فوراً.
* **مكان استخدامه في مشروعنا**: شاشة الإدخال `InputScreen` (لأن المستخدم يغير باستمرار: اختيار الجنس، ساعات النشاط عبر الـ Slider، وقيم العداد للوزن والعمر).
* **مثال من الكود**:
```dart
setState(() {
  weight++;
});
```

---

### 26. `ThemeData`
* **وظيفته**: تعريف وإعداد المظهر اللوني والخطوط الافتراضية للتطبيق بأكمله من مكان واحد، مما يضمن اتساق التصميم وسهولة تغييره.
* **مكان استخدامه في مشروعنا**: داخل `MaterialApp` لتفعيل الوضع الليلي `ThemeData.dark()` وضبط لون الخلفية الداكنة `#0A0E21`.
* **مثال من الكود**:
```dart
theme: ThemeData.dark().copyWith(
  scaffoldBackgroundColor: kBgColor,
)
```

---

## 🎯 أهم الأسئلة المحتملة في المناقشة الشفوية وكيفية الإجابة عليها:

1. **س: ما الفرق بين `StatefulWidget` و `StatelessWidget`؟ ولماذا اخترت كلاً منهما؟**
   * **الإجابة**: الـ `StatelessWidget` ويدجت ثابت لا تتغير حالته بعد بنائه واستخدمته في `ResultScreen` والبطاقات لأنها تستقبل قيم ثابتة فقط للعرض. بينما `StatefulWidget` يمتلك حالة داخلية تتغير مع الوقت باستخدام `setState()`، واستخدمته في `InputScreen` لأن المستخدم يعدل المدخلات (الوزن، العمر، السلايدر، الجنس) والواجهة تحتاج للتحديث مع كل ضغطة.

2. **س: كيف حميت التطبيق من مشكلة الـ `RenderFlex overflow`؟**
   * **الإجابة**: باستخدام `SingleChildScrollView` حول الـ `Column` الرئيسي ليتيح للمستخدم التمرير عند صغر حجم الشاشة، واستخدام `Expanded` داخل الـ `Rows` لتوزيع المساحات بالتساوي وبنسب مرنة بدلاً من استخدام أبعاد ثابتة كبيرة.

3. **س: كيف تم تمرير البيانات بين الشاشة الأولى وشاشة النتيجة؟**
   * **الإجابة**: عن طريق الـ `Constructor` الخاص بـ `ResultScreen` أثناء استدعاء دالة `Navigator.push(context, MaterialPageRoute(...))`.

4. **س: كيف عاد زر `Re-calculate` للشاشة الأولى مع الحفاظ على مدخلات المستخدم؟**
   * **الإجابة**: استدعينا `Navigator.pop(context)`، والتي تقوم بحذف شاشة النتيجة من المكدس (Stack) والعودة للشاشة السابقة التي لا تزال محتفظة بحالتها ومتغيراتها الأصلية في الذاكرة.


---

# 🧠 شرح الـ Controller والـ Provider في Flutter

---

## 1️⃣ ما هو الـ Controller في Flutter؟

### الفكرة ببساطة:
الـ **Controller** (المتحكم) هو كائن (Object) أو كلاس مستقل مسؤول عن **فصل منطق البيانات (Business Logic) عن واجهة المستخدم (UI)**، والتحكم في سلوك ويدجت معينة أو حالة الشاشة.

بدلاً من أن نكتب المتغيرات والحسابات داخل كلاس الشاشة (`StatefulWidget`)، ننقلها داخل **Controller**.

---

### أنواع الـ Controllers في Flutter:

#### أ) Controllers مدمجة جاهزة داخل فلاتر (Built-in Controllers):
1. **`TextEditingController`**: للتحكم في حقول الإدخال النصية (`TextField`) وقراءة ما يكتبه المستخدم أو مسحه.
2. **`ScrollController`**: للتحكم في القوائم المنسدلة والتمرير والنزول لأسفل القائمة برمجياً.
3. **`PageController`**: للتحكم في التنقل بين الصفحات في `PageView`.
4. **`AnimationController`**: للتحكم في بدء وإيقاف وتكرار الحركات والأنيميشن.

#### ب) Controller مخصص لإدارة الحالة (Custom State Controller):
كلاس نكتبه بأنفسنا لتخزين بيانات التطبيق ودوال التعديل عليها، مثل إنشاء كلاس `WaterController` بدلاً من كتابة كل شيء داخل الشاشة.

---

## 2️⃣ ما هو الـ Provider في Flutter؟

### الفكرة ببساطة:
الـ **Provider** هو أشهر مكتبة لإدارة الحالة (**State Management**) في Flutter، وهو مدعوم وموصى به رسمياً من فريق فلاتر و Google.

### ما المشكلة التي يحلها Provider؟
في التطبيقات العادية بدون Provider:
* إذا أردت تمرير بيانات من الشاشة الأولى للشاشة الثالثة، ستضطر لتمريرها يدوياً عبر كل الشاشات والـ Widgets الوسيطة (**Prop Drilling**).
* عند استدعاء `setState()` يتم إعادة بناء (Rebuild) الشاشة بأكملها بكل أزرارها وبطاقاتها حتى لو تغير رقم واحد فقط.

**حل الـ Provider:**
يعمل مثل **"خزان مياه مركزي"** في أعلى شجرة التطبيق (Widget Tree). أي Widget في أي مكان بالتطبيق تستطيع سحب البيانات منه مباشرة أو الاستماع للتغييرات بدون إعادة بناء الشاشة كلها!

---

## 3️⃣ المفاهيم الأساسية الثلاثة في Provider:

| المفهوم | الوظيفة | التشبيه |
|:---|:---|:---|
| **`ChangeNotifier`** | كلاس يحتوي على البيانات والدوال، ويطلق تنبيهاً عند أي تعديل عبر `notifyListeners()` | **محطة الراديو** (تبث الأخبار عند حدوث جديد) |
| **`ChangeNotifierProvider`** | ويدجت يوضع في مكان عالي بالشجرة ليجعل الـ Controller متاحاً للجميع | **برج الإرسال** (يوصل الإشارة للمستمعين) |
| **`Consumer` أو `context.watch()`** | ويدجت يستمع للبيانات ويعيد رسم نفسه فقط عندما تتغير | **جهاز الراديو** (يستقبل التحديث ويغير الصوت) |

---

## 4️⃣ مثال عملي: تحويل تطبيق Water Tracker إلى Controller + Provider

### الخطوة 1: إنشاء الـ Controller كـ `ChangeNotifier`:
```dart
import 'package:flutter/material.dart';

class WaterController extends ChangeNotifier {
  // البيانات (State)
  String? selectedGender;
  double activityHours = 1.0;
  int weight = 60;
  int age = 20;

  // دوال تعديل البيانات
  void setGender(String gender) {
    selectedGender = gender;
    notifyListeners(); // إعلام الواجهة بحدوث تغيير لتحديث نفسها
  }

  void setActivity(double hours) {
    activityHours = hours;
    notifyListeners();
  }

  void incrementWeight() {
    if (weight < 200) {
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

  // دالة الحساب
  double get totalLitres {
    int baseMl = weight * 35;
    int activityMl = (activityHours * 250).round();
    return (baseMl + activityMl) / 1000;
  }
}
```

---

### الخطوة 2: توفير الـ Controller للتطبيق عبر `ChangeNotifierProvider` في `main.dart`:
```dart
void main() {
  runApp(
    ChangeNotifierProvider(
      create: (context) => WaterController(),
      child: const MyApp(),
    ),
  );
}
```

---

### الخطوة 3: استهلاك البيانات في الواجهة بكل سهولة:

#### الطريقة الأولى (باستخدام `Consumer`):
يعيد بناء هذا الجزء فقط من الشاشة دون لمس باقي الصفحة:
```dart
Consumer<WaterController>(
  builder: (context, controller, child) {
    return Text(
      '${controller.weight} kg',
      style: const TextStyle(fontSize: 36),
    );
  },
)
```

#### الطريقة الثانية (باستخدام `context.read` و `context.watch`):
* **`context.watch<WaterController>()`**: للقراءة والاستماع (تحديث الواجهة عند التغيير).
* **`context.read<WaterController>()`**: لتنفيذ دالة بدون الاستماع (مثالي للأزرار):
```dart
// في زر الزيادة (+):
RawMaterialButton(
  onPressed: () {
    context.read<WaterController>().incrementWeight();
  },
  child: const Icon(Icons.add),
);
```

---

## 5️⃣ مقارنة سريعة: `setState` مقابل `Provider + Controller`

| وجه المقارنة | `setState()` | `Provider + Controller` |
|:---|:---|:---|
| **مكان البيانات والمنطق** | مدمج داخل كلاس الـ Widget (`UI`) | مفصول تماماً في كلاس `Controller` مستقل |
| **إعادة بناء الواجهة (Rebuild)** | تعيد بناء الـ Widget بالكامل | تعيد بناء الـ Widget المستمع فقط بدقة |
| **مشاركة البيانات بين الشاشات** | صعبة وتتطلب تمرير يدوي في الـ Constructor | سهلة جداً والبيانات متاحة في أي شاشة |
| **إمكانية اختبار الكود (Testing)** | صعبة لاختلاط المنطق بالواجهة | سهلة جداً لأن الـ Controller كلاس Dart خالص |
| **المناسبة للمشاريع** | المشاريع الصغيرة والبسيطة | المشاريع المتوسطة والكبيرة والاحترافية |
