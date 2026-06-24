# 🏹 Hunterverse — Telegram Mini App

## مراحل راه‌اندازی (۱۵ دقیقه)

---

## ۱. آپلود روی GitHub Pages (رایگان)

1. برو به [github.com](https://github.com) و یه ریپو جدید بساز
2. فایل `index.html` رو آپلود کن
3. برو به **Settings → Pages → Source** رو روی `main` بذار
4. آدرس اپت میشه: `https://USERNAME.github.io/REPO_NAME`

---

## ۲. ثبت Mini App در BotFather

1. تو تلگرام برو پیش **@BotFather**
2. بنویس `/newapp`
3. بات مورد نظرت رو انتخاب کن
4. اسم اپ بده: مثلاً **Hunterverse**
5. لینک GitHub Pages رو بده
6. یه عکس ۶۴۰×۳۶۰ برای پیش‌نمایش بده

---

## ۳. اضافه کردن دکمه به بات

در کد بات (bot.py)، این رو اضافه کن:

```python
from aiogram.types import WebAppInfo, InlineKeyboardMarkup, InlineKeyboardButton

@router.message(Command("game"))
async def open_game(message: Message):
    kb = InlineKeyboardMarkup(inline_keyboard=[[
        InlineKeyboardButton(
            text="🏹 باز کردن بازی",
            web_app=WebAppInfo(url="https://USERNAME.github.io/REPO_NAME")
        )
    ]])
    await message.answer("بازی Hunterverse رو باز کن! 🎯", reply_markup=kb)
```

---

## ویژگی‌های مینی اپ

- 🌲 **شکار جنگل** — ۱۲ حیوان از معمولی تا افسانه‌ای
- 🌊 **ماهیگیری دریاچه** — ماهی، خرچنگ، نهنگ و...
- 🏹 **۸ سلاح** — از چوب ساده تا توپ افسانه‌ای
- 🎒 **انبار** — فروش آیتم‌ها
- 🌟 **ایونت چالش** — جوایز پله‌ای
- 🎁 **جایزه روزانه** — سیستم استریک ۷ روزه
- 🎰 **کازینو** — ۶ بازی با ضرایب مختلف
- 🏆 **لیدربورد** — رقابت با بقیه
