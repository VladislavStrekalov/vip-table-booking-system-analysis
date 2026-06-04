# Модель данных

## Сущность: Клиент

| Атрибут      | Тип    |
| ------------ | ------ |
| id           | UUID   |
| full_name    | String |
| phone_number | String |
| email        | String |


## Сущность: VIP-столик

| Атрибут      | Тип     |
| ------------ | ------- |
| id           | UUID    |
| table_number | Integer |
| capacity     | Integer |
| description  | String  |
| status       | String  |


## Сущность: Бронирование

| Атрибут          | Тип      |
| ---------------- | -------- |
| id               | UUID     |
| customer_id      | UUID     |
| table_id         | UUID     |
| reservation_date | Date     |
| start_time       | Time     |
| end_time         | Time     |
| status           | String   |
| created_at       | DateTime |


## Связи

Один клиент может иметь несколько бронирований.

Один VIP-столик может участвовать в нескольких бронированиях в разные временные интервалы.

Каждое бронирование связано с одним клиентом и одним VIP-столиком.

