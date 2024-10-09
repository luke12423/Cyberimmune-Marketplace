# <a name="Start"> Cyberimmune-Marketplace</a>

Состав команды:
- Никоаев Дмитрий - 3 курс ИВТ-22-22
- Трониин Артем - 3 курс ИВТ-22-22
- Зиборов Артем - 3 курс ИВТ-22-22
- Данилов Артур - 3 курс ИВТ-22-22
##
- [Cyberimmune-Marketplace](#Start)
   - [Постановка задачи](#Task)
   - [Модель угроз](#Threats)
   - [Модель нарушителя](#Intruder)
   - [Архитектура (до кибериммунизации)](#Architecture1)
##
## <a name="Task"> Постановка задачи</a>
Необходимо создать безопасную среду для пользования маркетплейсом. 
Обеспечить защиту личных данных пользователей. Обеспечить безопасность транзакций. 
Предотвратить мошенничество и кибератаки.
Создать надежное взаимодействие между покупателями и продавцами.
## <a name="Threats">Модель угроз</a>
![export](https://github.com/user-attachments/assets/02a122c2-70e7-416b-bd0f-ceb3b639c976)
## <a name="Intruder">Модель нарушителя</a>
![export (2)](https://github.com/user-attachments/assets/33a3c8c2-7659-4064-8955-39fcf3e04381)

## <a name="Purposes">Цели безопасности</a>
- Защита личной информации пользователей
- Борьба с мошенничеством и фальсификацией
- Обеспечение безопасности при доставке товаров
- Защита от финансовых рисков

## <a name="Architecture1">Архитектура (До кибериммунизации)</a>

![ZLNBRjD05DtFLuowzu87BBgmogSCYQ4MUKIs4ubTqqGy1A9G8O4GekeVk6dSf76S_CATF-BCpJ1EhAHOQbrxvfnxpdtCz2HEL9JqsosfeiQf42yQIJUIHtH5AyhrPvhXxuHIVKwP-JwIAfRzE8XaDshY-KZqG0yROKzr4j2-qWJGbJwZEQYfVaTpVS4arKzEBUbnXNI9s](https://github.com/user-attachments/assets/790ee9a7-23f3-4b99-bdc8-05700b2a28c1)

## <a name="Negative scenarios">Описание сценариев, при которых ЦБ нарушается</a>
### Сценарий №1
Злоумышленник может составить большой список email-адресов и пробовать перебирать их через форму «забыл пароль». Если почта, которую он ввел существует, сайт ответит, что «письмо с восстановлением пароля отправлено на почту». Если нет — «пользователь с таким email не существует». Таким образом, злоумышленник поймет, какие адреса верные и составит список пользователей, которые есть в системе. Дальше он сможет атаковать их фишинговыми рассылками или перебором паролей для их аккаунтов. 

![VP4_JlD04CNxFSKeN_qLiJiA5Cw1AAp4HIH8Liv2dTWIVsIXX0g9KnWh4SR6oHNUt8YtybOfq3GpdlTxiq-Uh5oIkVkxMsEkfcwPoGZlw73K0ZzQwZFx0tfMWtOaoKhiM9RPBCraR2p9-NHkauKZjaEjES4rfL-ez16DRWSa2aXqXhnHV4IBWwu5UtIw5PneyQIvbWCQ1pG](https://github.com/user-attachments/assets/5b78c7cc-7854-4a9f-b524-9c4a1f8f78a9)

### Сценарий №2
Злоумышленник может пробовать перебирать самые простые пароли для email-адресов, которые ему удалось собрать. Есть целые базы простых паролей, которые чаще всего используют люди, вроде QWERTY или 123456. Подбор происходит в автоматическом режиме и не требует усилий злоумышленника.

![ROynJaCn44JxFSKgr2diaY8Avq0KrhUBBq5YEOQQ10aXKNn4mm6uG1I8Y0WnLvYz4ID1GH6vySxEsvsTBceezVhgKkIig_EY8xnWZsPt-B97U-1_YmFV3fyZ3GlDJkSbfg9ECic-wtEOLM9FsDYAu2sj7rZRFNOs_2B-3_4Y4hhQtuIQg4fsuqdsfufdRD3mhlWctcnfAvPlQ1G](https://github.com/user-attachments/assets/049957fd-080e-4b74-99a3-d7b9a9576507)

### Сценарий №3
Злоумышленник может воспользоваться мноественным СМС-запросом. 
Если нет механизма защиты от множественных запросов, то злоумышленник может отправить запрос на СМС неограниченное количество раз.

![RT0zJiD040NWVaun2dKAsnr552x01H35ojx24YIhpK8TWyIFA09L6fhSm4HOCJ4iLtXp8oQ92uJGD5lCzzxkZcV1-71rUK5qaeUfvm6Mw13b5f_o90zwRl2bqs8xO3DZb_3K5zPpGavbcPVEJ8AoPwpbHk5SLpUevGwjB0uaxKdwXxpeSiGMZSmPx-XamLZX5Qi3otgM4PaybDS](https://github.com/user-attachments/assets/1bcf48d9-9906-41eb-8e2c-f79684fb3d21)

### Сценарий №4
Если количество попыток ввода кода подтверждения неограничено, злоумышленник может перебирать цифры до бесконечности, пока не подберет нужный.
Это делается автоматически и очень быстро, особенно для 4-значных кодов — это всего 10 000 комбинаций.

![LO-nJe0m54NtznKlE3l0w63mEun3GpkGA3IbEXjDr8H1DoV_WI0eek8ltFT7lWONSuVUDFVqf6KNJOYN5-T49rLi0sTunYSskSMNzFAWVSQtPi6QiUdOvzm6wmBdv9MigzgR9YhsX55k5BpMwJi6kSCYZpjI_245aQbYVMMYqqiYdn-U7WHdpuvzSSHuKTM6LtrXI4AvtzNIuuC](https://github.com/user-attachments/assets/a5105988-8c70-4c68-aaee-0760eadc3c39)

### Сценарий №5
Злоумышленник для начала проводит тестовую покупку и получает идентификатор своего заказа. Так, он понимает, как этот идентификатор формируется. Затем он отправляет запрос на получение данных о покупке, но уже с другим идентификатором и получает информацию о заказе другого пользователя. Условно его настоящий запрос выглядит так: /get_order?id=1111, где id — это номер заказа. Если его изменить: /get_order?id=1234, то можно получить чужой заказ. 

![RP71IiD048Rl-nH3lTh3nfuAIdqEyH2Q70BQBkdgkMcA2ee5Bu87VOLO3CQqJLzXvetyDol5GXEoCpkP__ycsS74XgczkRvIwdnenobr-9LNt4ZEQtcK1-GbRt1NN7Sed93HD4wZE2Mj39J9C37Xo4BsWiRFBlesCkDIfZ97uKSohmh-L85IuT0cjw6DKLJAwEwP2Vh47pBbXfT](https://github.com/user-attachments/assets/53b0f011-15f3-4d5d-96dd-71b3cfc21de8)

### Сценарий №6
Если пользователь залогинен в интернет-магазине со своего браузера, но продолжает серфить в интернете, заходить на разные сайты, то в какой-то момент он может зайти на сайт злоумышленника. На этом сайте может быть специальный Java Script-код, который незаметно для пользователя отправит в магазин запрос на добавление своего товара в корзину. Для магазина это выглядит так, будто пользователь сам добавляет товар. Многие люди забывают проверить корзину, кто-то просто невнимателен, поэтому просто заказывают ненужный товар, а плохие продавцы зарабатывают. 

![XPAzJiCm58LtFyLLMUdGT6EeoihA20nHaw4I95PgElS745AGa10xuWtI2AifIPDNk7uZpYLX085GXzhtvpldM1dFZ9-OwwjBfOud9awenozSS-aUU8l_d3EtOYlt7lapqWEAao1CQA0qzgQJgVOZWwLNpdZdLeIjacktvigbxXvdotly2dxdh2Lu7S7xGNZ2wAQFoRqekeMxOGl](https://github.com/user-attachments/assets/a5c33c5e-1be7-4c9b-8467-5703d6415705)

## Описание позитивных сценариев работы

### Сценарий №1
1. Авторизация пользователя
2. Выбор товара
3. Оформление заказа
4. Выбор типа доставки
5. Оплата заказа
6. Передача информации о заказе продавцу
7. Упаковка и отпраавка товара
8. Получение товара

### Сценарий №2
1. Авторизация пользователя
2. Открытие пользователем вредоносного сайта
3. Попытка запуска скрипта вредоносным сайтом
4. Невыполнение запроса маркетплейсом
5. Последующее ипользование маркеплейса

### Сценарий №3
1. Попытка множественного запроса кода подтверждения через СМС
2. Система увеличивает время между отправкой СМС
3. Злоумышленник не может нанести существенный ущерб







