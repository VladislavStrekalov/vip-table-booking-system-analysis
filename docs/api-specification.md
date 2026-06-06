# API Specification

## Общая информация

Базовый URL:

```http
/api/v1
```

Формат обмена данными:

```text
JSON
```

---

# Получить список VIP-столиков

## Request

```http
GET /api/v1/tables
```

## Response

```json
[
  {
    "id": "1",
    "tableNumber": 1
  },
  {
    "id": "2",
    "tableNumber": 2
  }
]
```

---

# Получить доступные VIP-столики

## Request

```http
GET /api/v1/tables/available?date=2025-08-01
```

## Query Parameters

| Параметр | Тип | Обязательный |
|-----------|------|------|
| date | string | Да |

## Response

```json
[
  {
    "id": "1",
    "tableNumber": 1
  }
]
```

---

# Создать бронирование

## Request

```http
POST /api/v1/reservations
```

## Request Body

```json
{
  "customerId": "123",
  "tableId": "1",
  "reservationDate": "2025-08-01",
  "startTime": "19:00"
}
```

## Response

```json
{
  "reservationId": "456",
  "status": "CREATED"
}
```

---

# Подтвердить бронирование

## Request

```http
PATCH /api/v1/reservations/{id}/confirm
```

## Path Parameters

| Параметр | Тип |
|-----------|------|
| id | UUID |

## Response

```json
{
  "reservationId": "456",
  "status": "CONFIRMED"
}
```

---

# Отменить бронирование

## Request

```http
PATCH /api/v1/reservations/{id}/cancel
```

## Response

```json
{
  "reservationId": "456",
  "status": "CANCELLED"
}
```
