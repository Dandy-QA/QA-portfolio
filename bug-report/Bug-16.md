# BUG-16: Ошибка 404 (Not Found) при обновлении страницы каталога (inventory.html)

**Модуль:** Catalog / Routing
**Серьёзность:** Major
**Приоритет:** High
**Статус:** Open
**Дата:** 14.11.2026

**Окружение:** 
Браузер: Google Chrome 157.0.8103.79, Safari 26.5 (21624.2.5.11.4) ОС: macOS 26.5.1 (Tahoe)

**Шаги воспроизведения:**
1. Авторизоваться на сайте `www.saucedemo.com` под `standard_user`.
2. Открыть DevTools (F12) -> вкладка Network.
3. Находясь на странице каталога, нажать F5 (обновить страницу).

**Фактический результат:** 
Запрос `GET /inventory.html` завершается с ошибкой **404 Not Found**. В консоли (Console) появляются ошибки `Failed to load resource`. В ответе (Response) приходит стандартная страница ошибки хостинга (GitHub Pages), а не страница приложения. Пользователь теряет доступ к каталогу и вынужден заново авторизовываться.

**Ожидаемый результат:** 
Обновление страницы каталога должно возвращать статус `200 OK`. Сервер должен корректно обрабатывать роутинг SPA-приложения (Single Page Application) и возвращать главный файл `index.html` с последующей отрисовкой интерфейса через JavaScript без потери сессии.

**Доказательство:**
![Ошибка 404 в Network](https://github.com/Dandy-QA/QA-portfolio/blob/9438546d67e4ca21466f2ebc144e773749a11987/screenshots/Inventory%20404%20headers.png?raw=true)
![Просмотр вкладки Response](https://github.com/Dandy-QA/QA-portfolio/blob/d4aa9cfb15d0beb0b0a87b6a852812a4cb3484f3/screenshots/404%20Response.png?raw=true)
![Продолжение просмотра вкладки Response](https://github.com/Dandy-QA/QA-portfolio/blob/d4aa9cfb15d0beb0b0a87b6a852812a4cb3484f3/screenshots/Response%20continue.png?raw=true)
![Ошибки в консоли и поиск кнопки](https://github.com/Dandy-QA/QA-portfolio/blob/d4aa9cfb15d0beb0b0a87b6a852812a4cb3484f3/screenshots/Searching%20in%20console%20button.png?raw=true)
