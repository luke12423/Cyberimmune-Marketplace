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








