<div align="center">
  <img src="Preview.png" alt="PGClock Plus Preview" width="900">
</div>

<h1 align="center">PGClock Plus</h1>

<p align="center">
  ساده، زیبا و کامل — قالب صفحهٔ اشتراک برای Pasarguard
</p>

<p align="center">
  <a href="#نصب-خودکار">نصب خودکار</a> ·
  <a href="#نصب-دستی">نصب دستی</a> ·
  <a href="#تنظیمات-پنل">تنظیمات پنل</a> ·
  <a href="#نسخه‌های-دیگر">نسخه‌های دیگر</a>
</p>

---

## ویژگی‌ها

### سادگی
- رابط تمیز و بدون شلوغی — هر چیز جای درست خودش
- نصب با یک دستور، بدون build و بدون Node.js
- یک فایل HTML — بدون وابستگی به فریم‌ورک

### زیبایی
- طراحی تاریک مدرن با جزئیات ظریف
- انیمیشن‌های نرم و حس پریمیوم
- بهینه برای موبایل، تبلت و دسکتاپ

### امکانات
- اطلاعات اشتراک، هشدارها و نمودار مصرف حجم/زمان
- اپلیکیشن‌ها و اعلان‌ها مستقیم از پنل Pasarguard
- کپی لینک اشتراک، QR و دانلود WireGuard
- تشخیص سیست‌عامل و مرتب‌سازی هوشمند اپ‌ها

---

## نصب خودکار

روی سرور **Ubuntu** با Pasarguard نصب‌شده:

```bash
curl -fsSL https://raw.githubusercontent.com/Mrclocks/PGClockPlus/main/install.sh -o /tmp/pgclock-install.sh && sudo bash /tmp/pgclock-install.sh
```

یا:

```bash
wget -qO /tmp/pgclock-install.sh https://raw.githubusercontent.com/Mrclocks/PGClockPlus/main/install.sh && sudo bash /tmp/pgclock-install.sh
```

از طریق نصب‌کنندهٔ اصلی PGClock هم می‌توانید نصب کنید:

```bash
curl -fsSL https://raw.githubusercontent.com/Mrclocks/PGClock/main/install.sh -o /tmp/pgclock-install.sh && sudo bash /tmp/pgclock-install.sh
```

در منو گزینه **۳) PGClock Plus** را انتخاب کنید.

### اسکریپت چه کار می‌کند؟

1. منوی انتخاب نسخه (`Lite` / `PGClock` / `Plus` / `Pro`)
2. ذخیرهٔ `index.html` در:

```text
/var/lib/pasarguard/templates/subscription/index.html
```

3. به‌روزرسانی `/opt/pasarguard/.env`:

```env
CUSTOM_TEMPLATES_DIRECTORY="/var/lib/pasarguard/templates/"
SUBSCRIPTION_PAGE_TEMPLATE="subscription/index.html"
```

4. پرسیدن برای ریستارت Pasarguard (پیش‌فرض: بله)

> **پیش‌نیازها:** `wget`، `curl`، `python3`

---

## نصب دستی

### ۱. دانلود قالب

```bash
sudo mkdir -p /var/lib/pasarguard/templates/subscription/
sudo wget -N -O /var/lib/pasarguard/templates/subscription/index.html \
  https://raw.githubusercontent.com/Mrclocks/PGClockPlus/main/index.html
```

### ۲. تنظیم Pasarguard

```bash
sudo nano /opt/pasarguard/.env
```

اضافه یا به‌روز کنید:

```env
CUSTOM_TEMPLATES_DIRECTORY="/var/lib/pasarguard/templates/"
SUBSCRIPTION_PAGE_TEMPLATE="subscription/index.html"
```

### ۳. راه‌اندازی مجدد

```bash
sudo pasarguard restart
```

---

## تنظیمات پنل

1. پنل Pasarguard → **Settings → Subscription**
2. ویرایش **announcement** و **announcement link**
3. افزودن/ویرایش اپ‌ها در بخش apps

---

## نسخه‌های دیگر

- [PGClock Lite](https://github.com/Mrclocks/PGClockLite) — سبک‌تر و سریع‌تر
- [PGClock](https://github.com/Mrclocks/PGClock) — نسخهٔ استاندارد با استایل شیشه‌ای
- [PGClock Pro](https://github.com/Mrclocks/PGClockPRO) — برند، زیرعنوان و لوگوی سفارشی
