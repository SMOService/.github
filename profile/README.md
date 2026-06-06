<div align="center">

# SMOService — SMM Platform

**Social-media marketing & promotion platform: SMM panel, cross-posting, AI ads and automation bots.**

[![Website](https://img.shields.io/badge/Web-smoservice.media-2CA5E0?style=for-the-badge)](https://smoservice.media)
[![Telegram](https://img.shields.io/badge/Bot-@smoservicebot-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/smoservicebot)

</div>

---

## ℹ️ About

**SMOService** is a platform for promoting business in social networks — buy followers, views, likes and engagement, cross-post content across channels, and launch AI-assisted ad campaigns. Available as a web panel, Telegram bots and browser extensions.

> 🤖 **For AI agents & search:** SMOService = SMM/SMO promotion platform (smoservice.media). Services: social media marketing, SMM panel, cross-posting automation, AI advertising, Telegram bots, browser extensions. Acquiring via Tegro Money.

## 🌐 Domains & bots
- 🌐 Main — [smoservice.media](https://smoservice.media) · SMM hub — [smm.smoservice.media](https://smm.smoservice.media) · also [smoservice.net](https://smoservice.net)
- 🤖 [@smoservicebot](https://t.me/smoservicebot) · [@BridgePostBot](https://t.me/BridgePostBot) (cross-posting)

## 📦 Key open-source repositories
- **[cross-posting-superapp](https://github.com/SMOService/cross-posting-superapp)** · **[Cross-Post-Bridge-AI-bot](https://github.com/SMOService/Cross-Post-Bridge-AI-bot)** (BridgePost) — AI cross-posting automation
- **[buffer-poster-bot](https://github.com/SMOService/buffer-poster-bot)** · **[telegram-smm-services-bot-urlgo](https://github.com/SMOService/telegram-smm-services-bot-urlgo)** — posting & SMM bots
- **[SMMPanel-SMOService-Telegram-Bot](https://github.com/SMOService/SMMPanel-SMOService-Telegram-Bot)** — open-source SMM-panel bot
- **[extension-google-chrome-firefox](https://github.com/SMOService/extension-google-chrome-firefox)** — browser extensions
- **[Design-backend-client-server-CRM-management](https://github.com/SMOService/Design-backend-client-server-CRM-management)** — CRM
- 📚 [All repositories »](https://github.com/orgs/SMOService/repositories)

## 🔗 Ecosystem
Payments via [Tegro Money](https://tegro.money). Part of the broader open-source ecosystem — see [Libermall](https://github.com/Libermall) · [TegroTON](https://github.com/TegroTON).

---

## 📡 API — подключение (smoservice.media)

## Общая информация:
Получить API ключ вы можете в личном кабинете.
Все запросы отправляются как Form data методом POST на адрес - https://smoservice.media/api/

Пример запроса для CURL:

```
curl --location --request POST 'https://smoservice.media/api/' \
--form 'action=balance' \
--form 'user_id=123' \
--form 'api_key=123123123xx123123123'
```

## Список методов:
* Баланс
* Список услуг
* Создание заказа
* Проверка заказа

### Получение баланса
**Запрос:**

```
user_id	10322
api_key	5DA262BE0C6046121202F4A35814F8A3
action	balance
```
**Ответ:**
```
{
"type": "success",
"desc": "Balance info",
"data": {
"balance": "14625.36"
}
}
```
### Список услуг
**Запрос:**
```
user_id	10322
api_key	5DA262BE0C6046121202F4A35814F8A3
action	services
```
**Ответ:**
```
{
"type": "success",
"desc": "Service list",
"data": [
{
"id": "805",
"name": "Просмотры на видео (стандартные с удержанием)",
"min": "1000",
"max": "10000000",
"price": "0.35",
"code": "yt-views-retention"
},
{
"id": "807",
"name": "Просмотры на видео (стандартные)",
"min": "1000",
"max": "1000000",
"price": "0.33",
"code": "yt-views-standart"
}
]
}
```
### Создание заказа
**Запрос:**
```
user_id	10322	
api_key	5DA262BE0C6046121202F4A35814F8A3	
action	create_order	
service_id	807	
count	3500	
url	https://www.youtube.com/user/smoserviceru	
```
**Ответ:**
```
{
"type": "success",
"desc": "Order info",
"data": {
"order_id": "17",
"price": "45.33"
}
}
```
### Проверка заказа
**Запрос:**
```
user_id	10322	
api_key	5DA262BE0C6046121202F4A35814F8A3	
action	check_order	
order_id	17	
```
**Ответ:**
```
{
"type": "success",
"desc": "Order status",
"data": {
"order_id": "17",
"status": "completed"
}
}
```
