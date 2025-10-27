# المعمل الأول: إعداد وتأمين سويتش (Switch) أساسي

**المستوى:** Level 1 - Introduction to Networks
**الأدوات المستخدمة:** Cisco Packet Tracer

## 1. الهدف من المعمل (Objective)
الهدف هو بناء شبكة محلية (LAN) صغيرة جداً تتكون من سويتش واحد وجهاز كمبيوتر واحد. يتم تطبيق إعدادات الأمان الأساسية على السويتش، وضبط العناوين (IPs) لتمكين إدارة السويتش والاتصال به.

## 2. الخطوات التي تم تنفيذها (Steps)
1.  **بناء الشبكة:** إضافة سويتش (Cisco 2960) وجهاز كمبيوتر (PC) واحد إلى مساحة العمل.
2.  **التوصيل:** توصيل جهاز الكمبيوتر بمنفذ (FastEthernet) على السويتش باستخدام كابل (Copper Straight-Through).
3.  **تسمية السويتش:** تغيير الاسم الافتراضي إلى `sw-Jood`.
4.  **تأمين الوضع المميز:** ضبط كلمة سر مشفرة لـ (Privileged Mode) باستخدام الأمر `enable secret`.
5.  **تأمين الكونسول:** ضبط كلمة سر لخط الكونسول (`line console 0`) وتفعيل طلبها عند الدخول (`login`).
6.  **تأمين الاتصال عن بُعد:** ضبط كلمة سر لخطوط (`line vty 0 15`) وتفعيل طلبها (`login`).
7.  **تشفير كلمات السر:** تفعيل `service password-encryption` لإخفاء كلمات السر غير المشفرة في ملف الإعدادات.
8.  **ضبط الإدارة (SVI):** إعطاء السويتش عنوان IP (`192.168.1.1 255.255.255.0`) على واجهة `interface Vlan 1` وتفعيلها (`no shutdown`).
9.  **ضبط الجهاز (PC):** إعطاء جهاز الكمبيوتر عنوان IP ثابت (Static IP) يتوافق مع شبكة السويتش (مثل `192.168.1.10`).
10. **حفظ الإعدادات:** حفظ جميع الإعدادات الجارية (Running Config) إلى ذاكرة (NVRAM) باستخدام الأمر `copy running-config startup-config`.

## 3. التحقق من العمل (Verification)
تم استخدام الأمر `ping` من جهاز الكمبيوتر (PC) إلى عنوان IP الخاص بالسويتش (`192.168.1.1`).
* **النتيجة: (ناجح)**.

هذا يثبت أن جهاز الكمبيوتر والسويتش يمكنهما التواصل على نفس الشبكة، وأن إعدادات الإدارة صحيحة.

## 4. أوامر الإعدادات (Configuration Snippet)
هذا هو ناتج الأمر `show running-config` الذي يوضح الإعدادات المطبقة على السويتش.

```text
sw-Jood#show running-config
Building configuration...

Current configuration : 1213 bytes
!
version 15.0
no service timestamps log datetime msec
no service timestamps debug datetime msec
service password-encryption
!
hostname sw-Jood
!
enable secret 5 $1$mERr$yQRlRAfIGXJbu03q9DD/H.
!
!
!
!
!
!
spanning-tree mode pvst
spanning-tree extend system-id
!
interface FastEthernet0/1
!
... (Interfaces Fa0/2 - Fa0/24) ...
!
interface GigabitEthernet0/1
!
interface GigabitEthernet0/2
!
interface Vlan1
 ip address 192.168.1.1 255.255.255.0
!
!
!
!
line con 0
 password 7 0822455D0A1654454359
 login
!
line vty 0 4
 password 7 0822455D0A1654454359
 login
line vty 5 15
 login
!
!
!
!
end
