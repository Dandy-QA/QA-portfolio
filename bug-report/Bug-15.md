# BUG-15: Ошибка Fetch failed при отправке логов в backtrace.io при неверном пароле

**Модуль:** Login / Backend (Logging)
**Серьёзность:** Minor
**Приоритет:** Low
**Статус:** Open
**Дата:** 14.11.2026

**Окружение:** 
Браузер: Google Chrome,Safari ОС: macOS.

**Шаги воспроизведения:**
1. Открыть `www.saucedemo.com`.
2. Открыть DevTools (F12) -> вкладка Network (включить `Preserve log`).
3. Ввести логин `standard_user` и неверный пароль (например, `12345`).
4. Нажать кнопку "Login".
5. Перейти на вкладку Console.

**Фактический результат:** 
При неудачной попытке входа уходит POST-запрос на сторонний сервис `https://submit.backtrace.io/...`, который завершается со статусом `(canceled)` и не имеет ответа от сервера. В консоли браузера появляется красная ошибка `Fetch failed loading: POST`.
*(Примечание: Сам вход блокируется корректно, пароль на сервер не уходит).*

**Ожидаемый результат:** 
Система сбора логов (логирования) должна работать корректно (возвращать статус `200 OK` или `202 Accepted`) и не выдавать критических ошибок в консоль браузера при штатной проверке неверного пароля. Отказоустойчивость системы логирования не должна влиять на чистоту консоли.

**Доказательство:**
![Headers JSON is failed](https://github.com/Dandy-QA/QA-portfolio/blob/41c1fbfa6046ceb647261bec25a60652c42eab9a/screenshots/Headers%20in%20wrong%20password.png?raw=true)
![Запрос в Network](https://github.com/Dandy-QA/QA-portfolio/blob/7c36683f24db0bc841ecd0d7eff2e0fe345e4c80/screenshots/Empty%20response%20with%20wrong%20pass.png?raw=true)
![Ошибка Fetch failed в консоли](https://github.com/Dandy-QA/QA-portfolio/blob/1fac2fe1653cf7899101a7c07f1acee7d495162a/screenshots/Console%20in%20wrong%20pass.png?raw=true)
