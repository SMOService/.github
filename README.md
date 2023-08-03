# Подключение API

## Общая информация
Получить API ключ вы можете в личном кабинете. Данный ключ является важным элементом, позволяющим осуществлять взаимодействие с нашим API. После получения ключа, вам будет доступна возможность отправлять запросы на наш сервер.

Все запросы отправляются как Form data методом POST на адрес - https://smoservice.media/api/

## Примеры и объяснения методов:

### Получение баланса
Позволяет получить информацию о балансе на вашем аккаунте.

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

### Получение списка услуг
Позволяет получить информацию о всех доступных услугах.

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
Позволяет создать заказ на определенную услугу.

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
Позволяет проверить статус заказа.

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

## Примеры использования с помощью curl:

```
curl --location --request POST 'https://smoservice.media/api/' \
--form 'action=balance' \
--form 'user_id=123' \
--form 'api_key=123123123xx123123123'
```

Этот пример показывает, как можно выполнить запрос для получения баланса на вашем аккаунте, используя консоль и утилиту curl. Важно, что вы должны заменить 'user_id' и 'api_key' на реальные значения, которые вы получили в своем личном кабинете.

Обратите внимание, что для других типов запросов вам необходимо будет добавить другие параметры в качестве form data (например, 'service_id' и 'url' для создания заказа).
