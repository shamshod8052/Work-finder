# 📦 Telegram Message Filter

Telegram xabarlarini avtomatik tarzda **filtrlash**, **nazorat qilish** va **jo'natish** uchun yaratilgan kichik, ammo kuchli loyiha.

> ⚡ **Telethon asosida yozilgan. Minimal konfiguratsiya. Tez ishga tushadi.**

---

## 🖼️ Demo (Skrinshotlar)

```
![Filter working example](images/example1.png)
![Console log](images/example2.png)
```

---

## 🚀 Texnologiyalar

* **Python 3.11**
* **Telethon == 1.41.0**
* **python-decouple == 3.8**

---

## 📥 O‘rnatish

Terminalda (CMD, PowerShell yoki bash) quyidagilarni bajarishingiz kerak:

```bash
git clone https://github.com/shamshod8052/Telegram-msg-filter
cd Telegram-msg-filter
```

### 🐍 Virtual environment yaratish

#### Windows:

```bash
python -m venv venv
venv\Scripts\activate
```

#### Linux / MacOS:

```bash
python -m venv venv
source venv/bin/activate
```

### 📦 Kutubxonalarni o‘rnatish

```bash
pip install -r requirements.txt
```

---

## 🔧 Environment Variables

Loyihani ishga tushirishdan oldin `.env` fayl yarating:

```
PHONE=""
API_ID=1
API_HASH=""
```

---

## ▶️ Ishga tushirish

```bash
python main.py
```

Agar birinchi marta kirayotgan bo‘lsangiz, Telegram tasdiqlash kodini kiritasiz — Telethon avtomatik sessiya yaratadi.

---

## 🧩 Asosiy foydalanish

* Telegram akkaunt a'zo bo'lgan chatlardagi xabarlarni matn bo‘yicha filtrlash va berilgan chatga yuborish
* Matnni filterdan foydalanib bloklash / ruxsat berish
* Faqat belgilangan so‘zlardan kelgan xabarlarni olish

## 📜 Filtrlash qoidalari (`channels.json`) namunasi
```json
[
  {
    "chat_id": "-1003072741896",
    "parts_of_texts": [
      ["python", "dasturchi"], ["bot"], ["django"],
    ],
    "not_parts_of_texts": [
      ["Нажмите кнопку, чтобы доказать, что вы не бот."],
      ["тебя заблокировали"],
      ["转U不烧TRX！0.8TRX搞定一笔能量?"]
    ]
  },
  {
    "chat_id": "-1002290340409",
    "parts_of_texts": [
      ["Php"], ["Yii2"], ["Laravel"]
    ],
    "not_parts_of_texts": []
  }
]
```

### 📝 Qoidalar izohi

* **chat_id**
  Filtrlashdan o'tgan xabarlar yuboriladigan chat'ning id'si

* **parts_of_texts**
  Xabar **shu so‘z yoki iborani o‘z ichiga olsa**, filtrga tushadi.
  Masalan ["python", "dasturchi"] deb berilsa list ichidagi 2 ta so'z ham matnda majburiy bo'lishi kerakligini anglatadi.

* **not_parts_of_texts**
  Agar matn ushbu iboralardan birini o‘z ichiga olsa — **xabar filtrlanmaydi**.
  Bu “blokirovka xabarlar”, “captcha matnlari” yoki “spam reklama”larni chiqarib tashlash uchun kerak.

---

## 📄 License

**MIT License**

```
Copyright (c) 2025 Shamshod
```
