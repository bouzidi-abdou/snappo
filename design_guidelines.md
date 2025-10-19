# Snappo Design Guidelines - تطبيق المراسلة الفورية

## Design Approach
**Reference-Based:** Inspired by Telegram's clean interface and WhatsApp's simplicity, adapted for Arabic (RTL) with Snappo's distinctive purple identity.

---

## Core Design Elements

### A. Color Palette

**Dark Mode (Primary):**
- Primary: `270 79% 53%` (البنفسجي #7E30E1)
- Primary Light: `270 71% 66%` (للتدرج #9C58F1)
- Background Dark: `0 0% 10%` (خلفية رئيسية #1a1a1a)
- Background Light: `0 0% 17%` (بطاقات/جانبي #2c2c2c)
- Surface: `0 0% 20%` (حقول الإدخال #333)
- Text Primary: `0 0% 95%` (نص رئيسي #f1f1f1)
- Text Secondary: `0 0% 70%` (نص ثانوي)
- Border: `0 0% 25%` (حدود خفيفة)
- Success: `142 71% 45%` (رسائل مستلمة)
- Online: `142 76% 36%` (حالة متصل)

### B. Typography

**Font Family:** 'Montserrat' من Google Fonts
- العناوين الرئيسية: 600-700 weight
- العناوين الفرعية: 500-600 weight
- النصوص العادية: 400 weight
- التلميحات: 300 weight

**Sizes:**
- h1: 24px (العناوين الكبيرة)
- h2: 20px (أسماء المحادثات)
- Body: 13-14px (الرسائل والنصوص)
- Small: 11-12px (الوقت والتلميحات)

### C. Layout System

**Spacing:** استخدام وحدات Tailwind: 2, 3, 4, 6, 8, 12, 16
- Padding القياسي: p-4, p-6
- Margins بين العناصر: mb-2, mb-4
- فواصل الأقسام: py-8, py-12

**Structure:**
- عرض كامل مع max-w-screen-2xl
- الشريط الجانبي: 320px-380px
- منطقة المحادثة: flex-1
- ارتفاع كامل: h-screen

### D. Component Library

**1. Login/Register Panel** (مقدم من المستخدم):
- Container: 768px max-width, border-radius 30px
- Forms: حقول إدخال بزوايا 8px
- Buttons: uppercase, padding 10px 45px
- Social icons: 40x40px دائرية
- Animation: slide transition 0.6s
- شعار Snappo: 150px width

**2. Sidebar (قائمة المحادثات)**:
- خلفية: Background Light
- عنوان: اسم المستخدم + صورة + حالة الاتصال
- شريط بحث: بخلفية Surface مع أيقونة بحث
- قائمة المحادثات:
  - كل محادثة: صورة + اسم + آخر رسالة + وقت
  - ارتفاع 72px
  - hover: خلفية أفتح قليلاً
  - محادثة نشطة: border-right بالبنفسجي 3px
  - رسائل غير مقروءة: badge دائري بنفسجي

**3. Chat Area (منطقة المحادثة)**:
- Header:
  - صورة المحادثة + الاسم + حالة الاتصال
  - أيقونات: بحث، قائمة options
  - خلفية: Background Light، border-bottom
  
- Messages Container:
  - خلفية: Background Dark
  - رسائل المستخدم: Background بنفسجي، محاذاة يمين
  - رسائل الآخرين: Background Surface، محاذاة يسار
  - كل رسالة: padding 8px 12px، border-radius 12px
  - الوقت: نص صغير تحت الرسالة
  - فقاعات متتالية: تقليل المسافة بينها
  
- Input Area:
  - خلفية: Background Light
  - حقل النص: flex-1، Background Surface
  - أيقونات: إرفاق ملفات، emoji، إرسال صوتي
  - زر الإرسال: دائري بنفسجي مع أيقونة

**4. Contact List Modal**:
- overlay مظلل
- modal: 600px max-width
- قائمة جهات الاتصال مع صور دائرية
- زر "بدء محادثة" لكل جهة

**5. User Status Indicators**:
- نقطة خضراء صغيرة (8px) = متصل
- نص رمادي = آخر ظهور
- "يكتب..." = نص بنفسجي مع animation

### E. Animations

**Minimal & Purposeful:**
- Login panel: slide 0.6s ease-in-out (موجود)
- Message send: fade-in 0.2s
- Typing indicator: pulsing dots
- Sidebar hover: background transition 0.15s
- لا animations زائدة أو مشتتة

---

## RTL Considerations

- اتجاه النص: right-to-left
- محاذاة Form inputs: text-align-right
- الشريط الجانبي: على اليمين
- منطقة المحادثة: على اليسار
- رسائل المستخدم: من اليمين
- رسائل الآخرين: من اليسار
- أيقونات: عكس مواضعها حسب الاتجاه

---

## Images

**Logo:**
- استخدام snappo-logo.png المقدم
- مواضع: شاشة تسجيل الدخول (150px)، Sidebar header (40px)

**User Avatars:**
- دائرية بالكامل
- أحجام: 40px (sidebar)، 48px (chat header)، 32px (messages)
- استخدام placeholders ملونة بالأحرف الأولى للأسماء

**No Hero Images:** هذا تطبيق utility، ليس صفحة landing

---

## Accessibility & UX

- تباين عالي بين النصوص والخلفيات
- أحجام touch targets لا تقل عن 44px
- keyboard navigation كامل
- screen reader labels واضحة
- focus states واضحة بحدود بنفسجية