# Начало работы с API

Это руководство поможет вам начать работу с API "Пример API для работы с пользователями" для создания, получения, обновления и удаления пользователей.

К концу этого руководства вы сможете:

* Получать списки пользователей и информацию о конкретных пользователях.
* Создавать новых пользователей.
* Обновлять и удалять существующие учетные записи пользователей.

## Предварительные требования

Прежде чем начать, убедитесь, что вы:

* Знакомы с концепциями REST API.
* Имеете установленные или настроенные следующие инструменты:
  * Инструмент для выполнения HTTP-запросов (например, cURL или Postman).
  * Текстовый редактор или интегрированную среду разработки (IDE).

## Аутентификация

Для выполнения запросов к API "Пример API для работы с пользователями" требуется аутентификация. Чтобы получить доступ к API, выполните следующие шаги:

1.  Зарегистрируйтесь на учебный курс по документированию API.
2.  Модератор курса создаст вашу учётную запись и пришлёт API-ключ вам по электронной почте.
3.  Включите ваш API-ключ `Token` в заголовок `header` каждого запроса.

## Базовый URL

Базовый URL для всех запросов к API:

```text
https://api.documentat.io/api/prod
https://api.documentat.io/api/dev
```

## Выполнение вашего первого запроса к API

Этот раздел демонстрирует, как выполнить ваш первый запрос к API "Пример API для работы с пользователями".
Чтобы выполнить ваш первый запрос к API:

1.  Выберите конечную точку API. Список конечных точек см. в документе "Справочник API".
2.  Используйте cURL или Postman для выполнения запроса.

### Запрос

Ниже приведен пример запроса GET, который получает список всех пользователей с конечной точки `users` с использованием cURL:

```bash
curl -X GET "https://api.documentat.io/api/prod/users?limit=2" \
     -H "Token: ВАШ_API_КЛЮЧ"
```

### Ответ

Ниже приведен пример JSON-ответа от API:

```bash
[
  {
    "id": 123,
    "username": "g_chabukiani1",
    "email": "g-chabukiani@example.com",
    "firstName": "Гиа",
    "lastName": "Чабукиани",
    "address": {
      "country": "Грузия",
      "city": "Тбилиси",
      "street": "Цотне Дадиани",
      "house": "34"
    },
    "age": 32,
    "isEmployee": true,
    "accountStatus": "active"
  },
  {
    "id": 124,
    "username": "test_user_2",
    "email": "test2@example.com",
    "firstName": "Имя",
    "lastName": "Фамилия",
    "address": {
      "country": "Грузия",
      "city": "Тбилиси",
      "street": "Джавская",
      "house": "10"
    },
    "age": 28,
    "isEmployee": false,
    "accountStatus": "inactive"
  }
]
```