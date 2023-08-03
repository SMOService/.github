# ПОДКЛЮЧЕНИЕ API

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
