# TrendRadar

<div align="center" id="trendradar">

<a href="https://github.com/memarzade-dev/TrendRadar" title="TrendRadar">
  <img src="/_image/banner.jpg" alt="بنر TrendRadar" width="50%">
</a>

🚀 دستیار سریع‌ترین استقرار热点 در ۳۰ ثانیه — خداحافظی با اسکرول بی‌هدف، تمرکز روی اخبار مهم

[![ستاره‌های GitHub](https://img.shields.io/github/stars/memarzade-dev/TrendRadar?style=flat-square&logo=github&color=yellow)](https://github.com/memarzade-dev/TrendRadar/stargazers)
[![فورک‌های GitHub](https://img.shields.io/github/forks/memarzade-dev/TrendRadar?style=flat-square&logo=github&color=blue)](https://github.com/memarzade-dev/TrendRadar/network/members)
[![لایسنس](https://img.shields.io/badge/license-GPL--3.0-blue.svg?style=flat-square)](LICENSE)
[![نسخه](https://img.shields.io/badge/version-v3.0.5-blue.svg)](https://github.com/memarzade-dev/TrendRadar)
[![MCP](https://img.shields.io/badge/MCP-v1.0.1-green.svg)](https://github.com/memarzade-dev/TrendRadar)

</div>

> پروژه سبک و آسان برای استقرار.

## 📑 ناوبری سریع

<div align="center">

| [🎯 ویژگی‌های اصلی](#-ویژگیهای-اصلی) | [🚀 شروع سریع](#-شروع-سریع) | [🐳 استقرار Docker](#-استقرار-docker) | [🤖 تحلیل هوشمند AI](#-تحلیل-هوشمند-ai) |
|:---:|:---:|:---:|:---:|
| [📝 تغییرات](#-تغییرات) | [🔌 کلاینت MCP](#-کلاینت-mcp) | [❓ سوالات رایج](#سوالات-رایج) | [⭐ مرتبط با پروژه](#مرتبط-با-پروژه) |

</div>

## ✨ ویژگی‌های اصلی

### **تجمیع热点 از چند پلتفرم**

- Zhihu، Douyin، Bilibili، Wall Street Insights، Tieba، Baidu Hot Search، Caijing Hot، The Paper، Phoenix News، Toutiao، Weibo.

پیش‌فرض ۱۱ پلتفرم اصلی؛ امکان افزودن سفارشی.

### **استراتژی‌های هوشمند推送**

**سه حالت推送**:

| حالت | کاربران هدف | زمان‌بندی | محتوا | سناریوها |
|------|----------|----------|----------|----------|
| **خلاصه روزانه** `daily` | مدیران/کاربران عادی | ساعتی | تمام اخبار روز + بخش جدید | گزارش روزانه |
| **لیست فعلی** `current` | تولیدکنندگان محتوا | ساعتی | لیست فعلی + بخش جدید | ردیابی realtime |
| **نظارت افزایشی** `incremental` | سرمایه‌گذاران | فقط جدید | اخبار جدید | جلوگیری از تکرار |

کنترل پنجره زمانی推送 (اختیاری): محدود به ساعات خاص، فرکانس قابل تنظیم.

### **فیلترینگ دقیق محتوا**

کلمات کلیدی شخصی (مثل AI، BYD)؛ syntax: کلمات عادی، الزامی (+)، حذف (!). گروه‌بندی با خط خالی.

### **تحلیل روند hotspot**

ردیابی timeline، تغییرات热度، تشخیص جدید (🆕)، تحلیل پایداری، مقایسه پلتفرم‌ها.

### **الگوریتم hotspot شخصی**

وزن‌دهی: رتبه ۶۰%، فرکانس ۳۰%، کیفیت ۱۰%؛ قابل تنظیم.

### **پوشش چندکاناله**

Enterprise WeChat، Feishu، DingTalk، Telegram، Email، ntfy.

### **تحلیل هوشمند AI (جدید v3.0.0)**

بر اساس MCP؛ ۱۳ ابزار: پرس‌وجو conversational، روند، sentiment، جستجو مشابه. پشتیبانی از کلاینت‌های متعدد.

### **استقرار بدون دانش فنی**

فورک یک‌کلیدی GitHub؛ ۳۰ ثانیه برای Pages، ۱ دقیقه برای WeChat.

## 📝 تغییرات

### ۲۰۲۵/۱۱/۱۲ - v3.0.5

- رفع مشکل پورت SSL/TLS ایمیل.
- بهینه‌سازی پورت پیش‌فرض برای QQ/163/126.
- پشتیبانی متغیرهای محیطی Docker برای پوشش تنظیمات.

(برای تاریخچه کامل، به فایل CHANGELOG.md مراجعه کنید.)

## 🚀 شروع سریع

۱. **فورک پروژه** به حساب GitHub شما.

۲. **تنظیم Secrets GitHub** (انتخاب کانال‌ها: WeChat، Feishu، DingTalk، Telegram، Email، ntfy).

۳. **تنظیمات**: کلمات کلیدی در frequency_words.txt، حالت در config.yaml.

۴. **تست دستی**: در Actions، "Hot News Crawler" را اجرا کنید.

## 🐳 استقرار Docker

**روش سریع**:

```bash
mkdir -p config output
wget https://raw.githubusercontent.com/memarzade-dev/TrendRadar/master/config/config.yaml -P config/
wget https://raw.githubusercontent.com/memarzade-dev/TrendRadar/master/config/frequency_words.txt -P config/

docker run -d --name trend-radar \
  -v ./config:/app/config:ro \
  -v ./output:/app/output \
  -e [متغیرهای webhook و ایمیل] \
  wantcat/trendradar:latest
```

**با docker-compose**: دانلود فایل‌ها، pull و up -d.

## 🤖 تحلیل هوشمند AI

استقرار سریع با Cherry Studio (GUI).教程 در README-Cherry-Studio.md.

## 🔌 کلاینت MCP

پشتیبانی از Claude Desktop، Cursor، VSCode (Cline/Continue)، CLI. تنظیمات در details هر کلاینت.

## ☕ سوالات رایج

- **سرویس HTTP شروع نمی‌شود؟** پورت چک، وابستگی‌ها نصب، لاگ ببینید.
- **اتصال کلاینت به MCP؟** مسیر UV چک، فایروال، Inspector تست.
- **فراخوانی ابزار شکست؟** داده چک، پارامترها، config.

## 📄 لایسنس

GPL-3.0

---

<div align="center">

[🔝 بازگشت به بالا](#trendradar)

</div>
