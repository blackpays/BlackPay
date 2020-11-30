# Документация по API онлайн кассы BlackPay.
В данной документации описаны все доступные методы/запросы для работы с кассой.

&nbsp;

## Получение баланса кассы

| Параметр |     Описание     |
|:--------:|------------------|
|public_key| Публичный ключ   |

`GET` Пример запроса:

```sh
https://api.blackpay.space/api.php/balance?public_key=qVFZRhNb08Mo8Q5N1WbC
```

`JSON` Ответ:
```json
{"balance":3,"error":false}
```

## Генерация ссылки для оплаты

| Параметр |     Описание     |
|:--------:|------------------|
|public_key| Публичный ключ   |
|  amount  | Сумма в рублях   |

`GET` Пример запроса:

```sh
https://api.blackpay.space/api.php/generate?public_key=qVFZRhNb08Mo8Q5N1WbC&amount=100
```

`JSON` Ответ:
```json
{"id":"aipoTpOTkS","url":"https:\/\/pay.blackpay.space\/?id=aipoTpOTkS","error":false}
```

## Получение статуса оплаты

| Параметр |     Описание     |
|:--------:|------------------|
|public_key| Публичный ключ   |
|    id    |   id платежа     |

`GET` Пример запроса:

```sh
https://api.blackpay.space/api.php/status?public_key=qVFZRhNb08Mo8Q5N1WbC&id=aipoTpOTkS
```

`JSON` Ответ:
```json
{"amount":"100","state":"WAITING","error":false}
```
#### ИЛИ
```json
{"amount":"100","state":"PAID","error":false}
```

***

### Возможные ошибки
|    Ошибка       |                      Описание                                          |
|:---------------:|------------------------------------------------------------------------|
| `error`: true   | Возникла ошибка при выполнении запроса, возможно не соблюдены условия. |
