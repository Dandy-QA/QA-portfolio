# BUG-12: Поле Last Name не валидно для заполнения при оформлении товаров

**Модуль:** Checkout
**Серьёзность:** Critical
**Приоритет:** High
**Статус:** Open
**Дата:** 07.10.2026

**Окружение:** Google Chrome 150, Safari Browser, macOS Monterey, 2560x1600.

**Шаги воспроизведения:**
1. Открыть `https://www.saucedemo.com`
2. Ввести Username: `problem_user`
3. Ввести Password: `secret_sauce`
4. Нажать Login
5. Убедиться, что совершен успешный вход
6. Добавить товары в корзину
7. Перейти в раздел Checkout
8. Начать оформление заказа, ввести валидные данные пользователя (First Name, Last Name, ZIP/ Postal Code)

**Ожидаемый результат:** 
При оформлении заказа ввести свои данные (First Name, Last Name, ZIP/ Postal Code), все поля заполнятся без ошибок, далее нажать на кнопку Continue и заказ успешно обработается.

**Фактический результат:** 
При введении данных, поле Last Name не валидно для заполнения. Вместо него изменяются данные в поле First Name.

**Доказательство:**
![Баг с Last Name](https://github.com/Dandy-QA/QA-portfolio/blob/f638d6c3369b3a402768d54571915d0119d8cdf6/screenshots/Checkout%20Bug%20(Last%20Name%20not%20Valid).png?raw=true)
