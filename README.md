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
    Row(...),       // بطاقات الجنس
    Container(...), // بطاقة شريط الطول
    Row(...),       // بطاقات الوزن والعمر
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
* **وظيفته**: يجبر العنصر الداخلي على التمدد ليأخذ كل المساحة المتاحة بالتساوي داخل `Row` أو `Column`.
* **مكان استخدامه**: وضع بطاقتي الجنس وبطاقتي الوزن والعمر ليأخذ كل منهما 50% من عرض الشاشة مهما اختلف حجم الهاتف.
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
```dart
// الانتقال لشاشة النتيجة:
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

// العودة للشاشة السابقة:
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
    notifyListeners(); // إعلام الويدجتس المستمعة بالتحديث
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

  // حساب مؤشر كتلة الجسم (BMI = weight / (height/100)^2)
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
```dart
// 1. تسجيل الـ Provider في أعلى شجرة التطبيق (main.dart):
ChangeNotifierProvider(
  create: (context) => BmiController(),
  child: const MyApp(),
)

// 2. قراءة القيمة في الشاشة (تحديث هذا الجزء فقط):
Consumer<BmiController>(
  builder: (context, controller, child) {
    return Text('${controller.weight} kg');
  },
)

// 3. استدعاء الدالة عند الضغط على زر (+):
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
