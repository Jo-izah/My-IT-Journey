## 🔧 Practical Project 2.2: Advanced Troubleshooting & Isolation

**Original Goal:** Hands-on disassembly and reassembly practice
on an old laptop — applying skills from ACNT 101: IT Essentials.

**What Actually Happened:** The project turned into a full
troubleshooting and isolation mission after the laptop failed
following reassembly.

---

## Why This Project Exists

I grabbed an old laptop for a simple disassembly practice.

What started as a hands-on hardware exercise turned into
a full troubleshooting session after three unexpected
failures appeared post-reassembly.

This is the story of what went wrong — and how I fixed it.

---

## 1. Smart Component Diagnosis & Verification

- **Discovering the Upgrade:** Unusual boot speed was diagnosed
  using system tools (Task Manager), confirming the original
  HDD had previously been upgraded to an **SSD**.

- **Hands-on Practice:** Opened the laptop to verify this
  finding and practice **reseating** the RAM and SSD.

**Components & Disassembly Stages:**


* **صورة الجهاز كامل**
![فك وتركيب](https://github.com/user-attachments/assets/1845fc58-d06d-4316-8499-6ac624425fcd)

* **صورة الهارد ديسك SSD:** ![SSD](https://github.com/user-attachments/assets/e686bd15-0fe6-443d-a588-2abf84017352)

* **صورة الرام في مكانها:** ![استكشاف الرام](https://github.com/user-attachments/assets/6c2be7d6-b403-44d1-9646-1e0c4c37b007)
* **صورة عملية فك الرام (التطبيق):** ![RAM](https://github.com/user-attachments/assets/975f6c2b-732f-48b5-b876-b83dfe798f3a)

* **المواصفات المؤكدة:**
    * **الهارد ديسك:** نوع **SATA** 2.5 إنش، **EZASHY 128GB SSD**.
    * **الرام:** نوع **DDR2 SDRAM**.

### 2. قصة التحول إلى التشخيص والعزل (The Breakdown & Fix)

| المشكلة (العرض) | الإجراء المتخذ | الدليل والحل المعتمد |
| :--- | :--- | :--- |
| **تعليق النظام وصوت الصفير** | **إعادة تثبيت (Reseating) الرام** ثم **العزل الكامل** وإزالة الرام A. | **النجاح:** تم حل مشكلة الصفير (Beep Code)، وتم إثبات أن **الرام A تالفة** وتسببت بالتعليق. |
| **الشاشة السوداء (التجمد)** | تطبيق إجراء **تفريغ الكهرباء الساكنة (Hard Reset)** لمدة 60 ثانية. | **النجاح:** حل مشكلة "الكهرباء الشبحية" (Ghost Power) وعودة ظهور شعار DELL. |
| **خطأ "الهارد ديسك غير موجود"** | محاولات إزالة وتركيب للـ SSD، ثم الدخول لـ **BIOS (F2)** و **الفحص الذاتي (F5)**. | **النتيجة:** تقرير الفحص أكد أن الـ SSD يسبب **تعارضاً دائماً** ولا يمكن للنظام قراءته، مما يثبت تلفه (غالباً بسبب ESD). |

### 3. الحصيلة النهائية والقرار المهني

* **الحصيلة:** تم تحديد 3 أعطال (RAM A، SSD، وكابل شاشة مرتخٍ).
* **دليل خطأ الكابل:** ![كابل شاشة مرتخ](https://github.com/user-attachments/assets/c5ac9d4b-9664-448f-b8c0-2952ae979b85)
* **القرار:** تم **عزل** القطع التالفة (الـ SSD والـ RAM A) وتأمين اللوحة الأم.
* **الدرس الأهم:** **يجب** تفريغ الكهرباء الساكنة قبل لمس أي مكونات (ESD Precaution).

#### **صورة الدليل الرسمي (تقرير الفحص)**

[]![تقرير الفحص](https://github.com/user-attachments/assets/4f0f2f57-1772-4f32-9c2b-09d019731985)


### 4. 🎮 توسيع مهارات التشخيص: المحاكاة والصيانة المتقدمة

لتعويض المخاطر المترتبة على استكمال مهام التركيب وتحسين الأداء على اللابتوب الفعلي (الذي تعرض لأعطال)، تم استخدام محاكي **PC Building Simulator** لتطبيق مهارات الدعم الفني المتقدمة التالية:

| المهمة المنجزة | المهارة المطبقة (Troubleshooting & Maintenance) | الدليل العملي |
| :--- | :--- | :--- |
| **إصلاح جهاز عميل جديد** | **Initial Diagnosis:** التعامل مع رسائل بريد العملاء ومهام فحص الأجهزة (مثل `First Job: virus scan`). | ![1000177991](https://github.com/user-attachments/assets/fa7d3573-a0d1-430f-b8b3-8895644523f3)() |
| **الصيانة وإزالة الفيروسات** | **Software Troubleshooting & Security:** استخدام أداة خارجية (USB Virus Scanner) لإزالة التهديدات وإعادة الجهاز للحالة الآمنة (Protected). | ![٢٠٢٥١١١٢_٠٢١٦٠٠](https://github.com/user-attachments/assets/6b6d8e43-09da-4f73-8c61-b544b576d0c5)|
| **تحسين الأداء (Overclocking)** | **Advanced BIOS/UEFI & Performance Tuning:** تعديل نسبة المعالج (CPU Ratio) والجهد (Voltage) في الـ BIOS لرفع السرعة. **الهدف:** إثبات التعامل مع إعدادات الأداء التي قد تسبب عدم استقرار النظام. | ![٢٠٢٥١١١٢_٠٢٢٢٣٣](https://github.com/user-attachments/assets/222c4d2d-5520-44a5-b810-20d67adaa171)![٢٠٢٥١١١٢_٠٢٣١٣٤](https://github.com/user-attachments/assets/65d67722-4cda-4186-a70d-076a581b7761)
 |
| **اختبار الإجهاد (Stress Test)** | **Stability Verification:** استخدام برنامج OCCT لضمان استقرار النظام على سرعته الجديدة وتحمل الضغط (Load) دون ارتفاع الحرارة (إثبات إتقان مهارة الاختبار بعد الصيانة). | ![٢٠٢٥١١١٢_٠٢٣٥٢٤](https://github.com/user-attachments/assets/5b5cda4c-f4c3-47cd-af25-194c7a14e9c7) |
![1000178005](https://github.com/user-attachments/assets/913d61cb-4f24-49b2-a2e1-137ac010ccba)

**الحصيلة:** تم إغلاق فجوة مهارات التركيب (Assembly)، وصيانة البرامج، والتحكم في الـ BIOS/UEFI، ليكتمل ملف **التشخيص المتقدم** بنجاح.
