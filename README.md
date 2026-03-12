# 🎓 لوحة طالب العلاج الوظيفي

> تحكّم كامل بالداشبورد عبر تعديل ملف `config.json` فقط — بدون لمس الكود!

---

## 🚀 خطوات الرفع على GitHub Pages (مرة واحدة فقط)

### 1. إنشاء Repository
1. افتح [github.com](https://github.com) وسجّل دخول
2. اضغط **New repository** (الزر الأخضر)
3. اسم الـ repo: `ot-dashboard` (أو أي اسم تريده)
4. اختر **Public** ✅
5. اضغط **Create repository**

### 2. رفع الملفات
ارفع هذه الملفات الثلاثة على الـ repo:
```
📁 ot-dashboard/
├── index.html      ← (OT.html مُعاد تسميته)
├── config.json     ← ملف الإعدادات
└── README.md       ← هذا الملف
```

**طريقة الرفع:**
- اضغط **Add file** ← **Upload files**
- اسحب الملفات أو اختَرها
- اضغط **Commit changes**

### 3. تفعيل GitHub Pages
1. اذهب إلى **Settings** في الـ repo
2. من القائمة الجانبية: **Pages**
3. تحت **Source** اختر: **Deploy from a branch**
4. اختر Branch: **main** ← Folder: **/ (root)**
5. اضغط **Save**
6. انتظر دقيقة، ستظهر رسالة: *"Your site is live at..."*

### 4. تحديث الرابط في HTML
افتح `index.html` وابحث عن هذا السطر:
```javascript
const CONFIG_URL = 'https://raw.githubusercontent.com/USERNAME/REPO/refs/heads/main/config.json';
```
غيّر `USERNAME` باسم حسابك و`REPO` باسم الـ repo.

---

## ✏️ كيف تتحكم بالداشبورد؟

### افتح `config.json` وعدّل ما تريد:

---

### 📱 تغيير أرقام الواتساب
```json
"whatsappContacts": [
  { "name": "مجموعة السنة الأولى",  "number": "96279XXXXXXX" },
  { "name": "مجموعة السنة الثانية", "number": "96278XXXXXXX" }
]
```
> ⚠️ الرقم يبدأ بـ `962` (كود الأردن) بدون `0` في البداية
> مثال: `0791234567` ← يصبح `962791234567`

---

### 🔔 إضافة إشعار جديد
```json
"announcements": [
  {
    "id": "notif_005",
    "title": "عنوان الإشعار",
    "body":  "تفاصيل الإشعار هنا",
    "priority": "high",
    "date": "2025-05-01",
    "active": true
  }
]
```

| الأولوية | الوصف | اللون |
|----------|-------|-------|
| `"high"` | عاجل 🔴 — يظهر في الشريط المتحرك | أحمر |
| `"med"`  | متوسط 🟡 | برتقالي |
| `"low"`  | عادي 🟢 | أخضر |

> لإخفاء إشعار بدون حذفه: غيّر `"active": true` إلى `"active": false`

---

### 👨‍🏫 تغيير بيانات الدكاترة
```json
"doctors": [
  {
    "name":   "د. محمد أحمد",
    "rank":   "رئيس القسم",
    "email":  "m.ahmed@just.edu.jo",
    "isHead": true
  }
]
```

---

### 🏫 تغيير اسم الجامعة ورسالة الترحيب
```json
"site": {
  "university":   "جامعة العلوم والتكنولوجيا الأردنية",
  "welcomeText":  "أهلاً طالب العلاج الوظيفي 👋"
}
```

---

### 💬 تغيير الاقتباسات اليومية
```json
"quotes": [
  "اقتباس أول ✨",
  "اقتباس ثاني 💚",
  "اقتباس ثالث 🌟"
]
```

---

### 👁️ إخفاء/إظهار أقسام الداشبورد
```json
"features": {
  "showCalendar":    true,
  "showGPA":         true,
  "showAssignments": true,
  "showProgress":    true,
  "showSchedule":    true,
  "showEmails":      true
}
```
> غيّر `true` إلى `false` لإخفاء أي قسم

---

## 🔄 كيف تحدّث الإعدادات؟

1. افتح `config.json` في GitHub (اضغط على الملف ← ✏️ Edit)
2. عدّل ما تريد
3. اضغط **Commit changes**
4. **انتهى!** التغييرات تظهر فوراً عند تحديث الصفحة ⚡

---

## ⚡ نصائح مهمة

- ✅ تأكد أن الـ JSON صحيح (يمكنك التحقق على [jsonlint.com](https://jsonlint.com))
- ✅ الداشبورد يعمل حتى لو فشل تحميل `config.json` (يستخدم البيانات المدمجة)
- ✅ التغييرات تظهر خلال ثوانٍ بعد الحفظ
- ⚠️ لا تحذف أي مفتاح من الـ JSON، فقط غيّر القيم
