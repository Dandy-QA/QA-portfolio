# Тестирование API (Postman)

В данном разделе представлены результаты тестирования REST API на тренажере `reqres.in`. Были проверены основные CRUD-операции (Create, Read, Update, Delete).

**Окружение:** Postman, тренажер `reqres.in`.

## 🛠 Реализованные запросы:

### 1. GET — Получение списка пользователей
*   **Метод:** `GET`
*   **URL:** `https://reqres.in/api/users?page=2`
*   **Ожидаемый результат:** Статус `200 OK`, получение JSON-списка пользователей.
*   **Фактический результат:** Запрос выполнен успешно. Получен статус `200 OK`. В теле ответа пришел JSON с массивом данных (id, email, first_name, last_name, avatar).

**Доказательство (Скриншот):**
![GET запрос](https://github.com/Dandy-QA/QA-portfolio/blob/a2932615d81d7daba2c99c9be615458ee16bab75/API/Screenshots/GET.png?raw=true)

---

### 2. POST — Создание нового пользователя
*   **Метод:** `POST`
*   **URL:** `https://reqres.in/api/users`
*   **Body (JSON):** 
    ```json
    {
        "name": "Ivan",
        "job": "QA Engineer"
    }
    ```
*   **Ожидаемый результат:** Статус `201 Created`, создание записи в системе и присвоение `id`.
*   **Фактический результат:** Запрос выполнен успешно. Получен статус `201 Created`. В ответе пришли данные пользователя с присвоенным `id`: "594" и датой создания (`createdAt`).

**Доказательство (Скриншот):**
![POST запрос](https://github.com/Dandy-QA/QA-portfolio/blob/8c0555523e0f9ee1b5cc31b4aef9690983b7fa05/API/Screenshots/POST.png?raw=true)

---

### 3. PUT — Полное обновление данных пользователя
*   **Метод:** `PUT`
*   **URL:** `https://reqres.in/api/users/2`
*   **Body (JSON):** 
    ```json
    {
        "name": "Ivan Updated",
        "job": "Senior QA"
    }
    ```
*   **Ожидаемый результат:** Статус `200 OK`, полное обновление данных пользователя.
*   **Фактический результат:** Запрос выполнен успешно. Получен статус `200 OK`. Сервер вернул обновленные данные (`Ivan Updated`, `Senior QA`) и время обновления (`updatedAt`).

**Доказательство (Скриншот):**
![PUT запрос](https://github.com/Dandy-QA/QA-portfolio/blob/7aea67861a16af36ad100e073436b87b20ea0f36/API/Screenshots/PUT.png?raw=true)

---

### 4. PATCH — Частичное обновление данных
*   **Метод:** `PATCH`
*   **URL:** `https://reqres.in/api/users/2`
*   **Body (JSON):** 
    ```json
    {
        "job": "Lead QA"
    }
    ```
*   **Ожидаемый результат:** Статус `200 OK`, обновление только переданного поля (job).
*   **Фактический результат:** Запрос выполнен успешно. Получен статус `200 OK`. Сервер вернул только измененное поле (`job`: "Lead QA") и время обновления.

**Доказательство (Скриншот):**
![PATCH запрос](https://github.com/Dandy-QA/QA-portfolio/blob/23f76be3377723da17902261d8ac86e1dd14f161/API/Screenshots/PATCH.png?raw=true)

---

### 5. DELETE — Удаление пользователя
*   **Метод:** `DELETE`
*   **URL:** `https://reqres.in/api/users/2`
*   **Ожидаемый результат:** Статус `204 No Content`, успешное удаление записи (тело ответа пустое).
*   **Фактический результат:** Запрос выполнен успешно. Получен статус `204 No Content`. Запись удалена.

**Доказательство (Скриншот):**
![DELETE запрос](https://github.com/Dandy-QA/QA-portfolio/blob/847a9477da4ad5d476a4f7dc941145a337ca651d/API/Screenshots/DELETE.png?raw=true)

---

## 📁 Коллекция Postman
Файл с экспортированной коллекцией запросов (`.json`) находится в папке `postman/` в корне репозитория. Вы можете импортировать его в Postman, чтобы проверить запросы самостоятельно.
