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
      - [Негативные сценарии](#NegativeScenarios)
      - [Позитивные сценарии](#PositiveScenarios)
   - [Архитектура (после кибериммунизации)](#Architecture2)
      - [Решение](#Decision)
   - [Использованная литература](#Sources)
##
## <a name="Task"> Постановка задачи</a>
Необходимо создать безопасную среду для пользования маркетплейсом,
обеспечить защиту личных данных пользователей, безопасность транзакций. 
Предотвратить мошенничество. Создать надежное взаимодействие между покупателями и продавцами.

## <a name="Threats">Модель угроз</a>

| Угрозы | Последствия |
| ------ | ----------- |
| Несанкционированный доступ к личным данным | Злоумышленники могут получить доступ к адресу, телефону, платёжным данным и деталям заказа. |
| Фишинговые атаки | Мошенники создают фальшивые электронные письма или веб-сайты, имитируя маркетплейсы, чтобы выманить конфиденциальные данные у покупателей |
| Утечки данных | Недостаточная защита баз данных магазина или слабая кибербезопасность на стороне продавца могут привести к утечке личной информации покупателя |
| Мошенничество при онлайн-оплате | Поддельные или вредоносные платёжные страницы могут использоваться для кражи платёжных данных или осуществления незаконных транзакций |
| Недостаточная безопасность в процессе доставки | Риск вмешательства или кражи во время транспортировки заказов, особенно при использовании служб доставки |
| Вредоносные программы | Использование уязвимых или небезопасных приложений или программ может привести к инфицированию устройства покупателя вредоносным ПО |


## <a name="Intruder">Модель нарушителя</a>
| Вид нарушителя | Тип нарушителя по ФСТЭК | Тип нарушителя по ФСБ | Возможные последствия |
| -------------- | ----------------------- | --------------------- | --------------------- |
| Клиенты | Внешний | Н1 | Могут нанести ущерб намеренно или по не знанию |
| Конкурирующие организации | Внешний | Н4 | Несанкционированное получение и раскрытие конфиденциальной информации |
| Студенты | Внешний | Н1 | Непреднамеренные, неосторожные или неквалифицированные действия. Физическое уничтожение данных или оборудование. Раксрытие полученной информации.|
| Лица, распространяющие вирусы/вредоносные программы, другие лица, осуществляющие НСД | Внешний | Н5 | Обладают достаточными знаниями в области осуществления НСД к ресурсам ИС |
| Временный сотрудник | Внутренний | Н3 | Неосторожные или неквалифицированные действия. Продажа конфиденциальной информации с целью получения материальной выгоды |
| Программист, ТО | Внутренний | Н4 | Внедрение дополнительных функциональных возможностей в программное обеспечение или программно-технические средства на этапе разработки. Непреднамеренные, неосторожные или неквалифицированные действия. |
| Недобросовестные партнеры, хакеры | Внешний | Н5 | Способны умышленно дезорганизовать работу, вывести системы из строя, разгласить и исказить конфиденциальные информации за счет НСД к информации и утечки по ТКУИ |

## <a name="Purposes">Цели и Предположения безопасности</a>
### Цели безопасности:  
1. Защита личной информации пользователей
2. Борьба с мошенничеством и фальсификацией
3. Защита от финансовых рисков  

### Предположения безопасности  
1. Веб-приложение имеет защиту от Ddos-атак

## <a name="Architecture1">Архитектура (До кибериммунизации)</a>

![ZLNBRjD05DtFLuowzu87BBgmogSCYQ4MUKIs4ubTqqGy1A9G8O4GekeVk6dSf76S_CATF-BCpJ1EhAHOQbrxvfnxpdtCz2HEL9JqsosfeiQf42yQIJUIHtH5AyhrPvhXxuHIVKwP-JwIAfRzE8XaDshY-KZqG0yROKzr4j2-qWJGbJwZEQYfVaTpVS4arKzEBUbnXNI9s](https://github.com/user-attachments/assets/790ee9a7-23f3-4b99-bdc8-05700b2a28c1)

![diagram-export-22 10 2024-19_31_44](https://github.com/user-attachments/assets/551f956f-2377-4eb8-a38e-3aec57c412d2)






## <a name="NegativeScenarios">Описание сценариев, при которых ЦБ нарушается</a>
### Сценарий №1
Злоумышленник может составить большой список email-адресов и пробовать перебирать их через форму «забыл пароль». Если почта, которую он ввел существует, сайт ответит, что «письмо с восстановлением пароля отправлено на почту». Если нет — «пользователь с таким email не существует». Таким образом, злоумышленник поймет, какие адреса верные и составит список пользователей, которые есть в системе. Дальше он сможет атаковать их фишинговыми рассылками или перебором паролей для их аккаунтов. [(CWE-1390: Weak Authentication)](https://cwe.mitre.org/data/definitions/1390.html)

![VP4_JlD04CNxFSKeN_qLiJiA5Cw1AAp4HIH8Liv2dTWIVsIXX0g9KnWh4SR6oHNUt8YtybOfq3GpdlTxiq-Uh5oIkVkxMsEkfcwPoGZlw73K0ZzQwZFx0tfMWtOaoKhiM9RPBCraR2p9-NHkauKZjaEjES4rfL-ez16DRWSa2aXqXhnHV4IBWwu5UtIw5PneyQIvbWCQ1pG](https://github.com/user-attachments/assets/5b78c7cc-7854-4a9f-b524-9c4a1f8f78a9)

### Сценарий №2
Злоумышленник может пробовать перебирать самые простые пароли для email-адресов, которые ему удалось собрать. Есть целые базы простых паролей, которые чаще всего используют люди, вроде QWERTY или 123456. Подбор происходит в автоматическом режиме и не требует усилий злоумышленника. [CWE-521: Weak Password Requirements](https://cwe.mitre.org/data/definitions/521.html)

![ROynJaCn44JxFSKgr2diaY8Avq0KrhUBBq5YEOQQ10aXKNn4mm6uG1I8Y0WnLvYz4ID1GH6vySxEsvsTBceezVhgKkIig_EY8xnWZsPt-B97U-1_YmFV3fyZ3GlDJkSbfg9ECic-wtEOLM9FsDYAu2sj7rZRFNOs_2B-3_4Y4hhQtuIQg4fsuqdsfufdRD3mhlWctcnfAvPlQ1G](https://github.com/user-attachments/assets/049957fd-080e-4b74-99a3-d7b9a9576507)

### Сценарий №3
Злоумышленник выясняет номер телефона жертвы для авторизации в веб-приложении.
Отправляет запрос на авторизацию через код из СМС. Пользуясь уязвимостью SS7, перехватывает сообщение и вводит код, как будто получил его на телефон жертвы.

![fPBDIiD058NtynINkWxuin2w2FK1N6KfBeOcOA4_9PcwS5KhgA2Wksv4wHk4OcnfDNs5Sz_8Cw4gmPqIc9ovoVVbvZAjpDdKZNfTSzHsWrGQU469jTvZmViSkKvG-7r3R2QZB4bbaCPSzxw1ATOezGhlUgUtp0K-U2sngf2Bxk2Bs9MTD8dDa1_ij3j3stVIY8wZGAyzenCTLqJ](https://github.com/user-attachments/assets/9f71555c-9174-427c-ac1b-c7869fcd74d1)


### Сценарий №4
Злоумышленник использует уязвимость SQL-инъекции для получения данных из таблиц базы данных. Для этого используется ключевое слово UNION, которое позволяет выполнить дополнительный запрос SELECT и добавить его результаты к исходному запросу. Приложение выполняет следующий запрос, содержащий пользовательский ввод "Gifts":  
SELECT name, description FROM products WHERE category = 'Gifts'  
Злоумышленник добавляет в запрос:  
' UNION SELECT username, password FROM users--.  
И получает список со всеми именами пользователя и пароли.  
[CWE-20: Improper Input Validation](https://cwe.mitre.org/data/definitions/20.html)

![DP3DIiD0483l-nH3BxsOY7eBDDQOg0T5g8BdDLbb8Sqkkzk3dbJmf1UVGFG9Gh4ebRQlCFj6dOJaD3CmtpS_O-kuSRDfoOvofmmCy1FN-E_VyPVY76l_Wekc7W2ty5WgKAOG1lQO9axcKlFAzHGkW90vfJzO0sue-VFFk6oAxqxtX7MhqgeKdMkVfTpnMsu5YJwmfj44a09NkF9](https://github.com/user-attachments/assets/7d891fa7-d820-4a28-ab8a-281fbc654652)

![bLBDQjj04BxlKmpkmPTAfUtDODTrfVv0QuFRqaFTmrRQ5e4jYTqrfJd52OP0Siafnv0yWGWHKMHRUONPDygiP3r0M916iz_FwDiTAisbNYxcx6sW4maTlC0DLkOOj-RKd52TuuvMWMK7k8A3UGA938M4b_1CYf2bH8-2AEMn9l8bLfO2U4EhmblC01-eACmAI_jnZHNjPEOGire](https://github.com/user-attachments/assets/63fbad59-18ee-4ffd-b5b0-bdd45d4fb15a)




### Сценарий №5
Злоумышленник для начала проводит тестовую покупку и получает идентификатор своего заказа. Так, он понимает, как этот идентификатор формируется. Затем он отправляет запрос на получение данных о покупке, но уже с другим идентификатором и получает информацию о заказе другого пользователя. Условно его настоящий запрос выглядит так: /get_order?id=1111, где id — это номер заказа. Если его изменить: /get_order?id=1234, то можно получить чужой заказ. [CWE-425: Direct Request ('Forced Browsing')](https://cwe.mitre.org/data/definitions/425.html)

![RP71IiD048Rl-nH3lTh3nfuAIdqEyH2Q70BQBkdgkMcA2ee5Bu87VOLO3CQqJLzXvetyDol5GXEoCpkP__ycsS74XgczkRvIwdnenobr-9LNt4ZEQtcK1-GbRt1NN7Sed93HD4wZE2Mj39J9C37Xo4BsWiRFBlesCkDIfZ97uKSohmh-L85IuT0cjw6DKLJAwEwP2Vh47pBbXfT](https://github.com/user-attachments/assets/53b0f011-15f3-4d5d-96dd-71b3cfc21de8)

### Сценарий №6
Если пользователь залогинен в интернет-магазине со своего браузера, но продолжает серфить в интернете, заходить на разные сайты, то в какой-то момент он может зайти на сайт злоумышленника. На этом сайте может быть специальный Java Script-код, который незаметно для пользователя отправит в магазин запрос на добавление своего товара в корзину. Для магазина это выглядит так, будто пользователь сам добавляет товар. Многие люди забывают проверить корзину, кто-то просто невнимателен, поэтому просто заказывают ненужный товар, а плохие продавцы зарабатывают. [CWE-79: Improper Neutralization of Input During Web Page Generation ('Cross-site Scripting')](https://cwe.mitre.org/data/definitions/79.html)

![ZP8_Jy9W4CRtzrDSS9N1FvC3mTNLKHrgsw4HMb8A9avGn6WmSJ5nCJ5-WzhO00BbAznz8v-3qXWZYI6Xxxrtp_ExkxRUZgmmwZGRvjYEWf0g_COvp-IHntYcd4ZCcSOLijhKQRiX1Q63_ptJWj2plPRbHv2zSy9JYGcw6USouBcCv1xdZ1VuJVYBavN7JICeBFP_MRo2raDT1kP](https://github.com/user-attachments/assets/87dd1694-fa97-4862-a3de-44667fb43b25)




## <a name="PositiveScenarios">Описание позитивных сценариев работы</a>

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
1. Попытка перехвата кода подтверждения из СМС
2. Если текущий IP-адрес отличается от IP-адреса при прошлой авторизации, потребуется дополнительна аутентификция через почту
3. Злоумышленник не получает доступ к аккаунту жертвы

## <a name="Architecture2">Архитектура (после кибериммунизации)</a>

![nLNRRjD047tVhrZrtHBt2mzM-HIJM63HDf7Z59Mdk8ae2AG2GW8XHDG_S4FSk6bY_yBi7t5ckzauTXkP9nxYQDVdd9qvCplUxKLU6FNtzuHuteeweToXCULqfJxH3FyJIjGnfRpUaLvFzdj-A3jX6y-xeWjcq0gwta44sY_0fsh8K4ddu32_03-c9UKgXawcDNf-gny6qT4jEfz](https://github.com/user-attachments/assets/6debdfbc-eaef-420f-9bbd-6e27d88c3dd4)

![diagram-export-22 10 2024-19_24_52](https://github.com/user-attachments/assets/b6752ff6-0d5e-455c-beb7-4e1b72653b32)








## <a name="Decision">Решение</a>

### Описание действий для предотвращения нарушения ЦБ1
Использование общих слов при восстановлении пароля "Если такая почта существует, будет отправлен код восстановления". 
Усиление парольной политики, не разрешать людям ставить пароли в виде последовательности букв и цифр.
Ввести ограничение попыток ввода кода восстановления до 3-х раз, а также увеличить длину кода до 6 символов.
Проверять номер заказа и пользователя, сделавшего заказ, при показе информации о заказе.

![pLH1Rn9T5Ds_N_72-gF9fwwwQEh_S3C2YIGK6XWqSGK3iMreh9eOZOas_eDX1ALJ6Fx2lV_8SzxZDKD3IPTc5Zo6S-uzzzp3E-x5KJVkdxICULwBErrRaIzoAuMEPAaJFSTvBYiy2yahDkhPjwsExNJhZQvzOav1RTQQfr4x1k-3P9g0EG3sZwJwJXPwvJXHFtxr0EaZu8NaCjU](https://github.com/user-attachments/assets/5a804c77-4bf6-447b-83b3-b1db014b2dc4)

### Описание действий для предотвращения нарушения ЦБ2
Для защиты нужно внедрить CSRF-токен и установить атрибуты Same-Site, Secure, HTTPOnly для Cookies.

![dP6_JiCm4CRtUmghUmTWOq3bKKpY8L9fgiG5YIbD6P3AnCB6dpT88goMDd5VuVn6VBQCg1WOKAJuShhlTz_dJ4ej2xsudXBHPQBpGepubItltIDlS7RSk9gD_nu9MOf5gGgH5odU9pI7D4kokPnfoDwvuKzN2-ZsRDsAUxTs3wWD3tYslECcCEwcUKIS_a8yOROTOtJmIrtbxjc](https://github.com/user-attachments/assets/a6d47428-0748-40d3-8aa5-4049951f93ed)

### Описание действий для предотвращения нарушения ЦБ3
Чтобы избежать рисков, связанных с уязвимостью SS7, рекомендуется использовать современные меры безопасности, в частности двухфакторную авторизацию.

![fPBBIiD068NtUOgXhWDU5a8NeJw0gop5nT04BFHIagaBLxK5AoWgRjo8qZS8mTZIslGLplz6dWcn4dKXIc7wTvhloycPD6AZ8pFej9s3fkb5gePdv5ZADMRyJf7829dzNLCwLeCuZ5Gl2hZkR807B97B66zo9PUSCwpucMDH86VjtWUnhRQYC73wl66hsUhhhb4r_z1tvS8oCf9](https://github.com/user-attachments/assets/dc031bb6-7153-477c-a036-bdfc7cc6ffdc)


# <a name="Sources">Использованная литература</a>
- [Common Weakness Enumeratiion](https://cwe.mitre.org/index.html)  
- [OWASP Top-Ten](https://owasp.org/www-project-top-ten/)  
- [БДУ ФСТЭК](https://bdu.fstec.ru/vul)  
- [Федеральный закон от 29 июля 2018 г. № 250-ФЗ "О внесении изменений в Закон Российской Федерации "О защите прав потребителей"](https://base.garant.ru/72001334/)  
- [Федеральный закон от 28 декабря 2009 г. № 381-ФЗ "Об основах государственного регулирования торговой деятельности в Российской Федерации"](https://base.garant.ru/12171992/)  
- [Закон РФ от 7 февраля 1992 г. № 2300-I "О защите прав потребителей"](https://base.garant.ru/10106035/)  
- [МЕТОДИЧЕСКИЕ РЕКОМЕНДАЦИИ
по разработке нормативных правовых актов, определяющих угрозы
безопасности персональных данных, актуальные при обработке
персональных данных в информационных системах персональных
данных, эксплуатируемых при осуществлении соответствующих видов
деятельности](http://www.fsb.ru/files/PDF/Metodicheskie_recomendacii.pdf)  
- [Методический документ. Методика оценки угроз безопасности информации (утв. ФСТЭК России 05.02.2021)](https://sudact.ru/law/metodicheskii-dokument-metodika-otsenki-ugroz-bezopasnosti-informatsii/)  
- [Хабр: Какие задачи решают IAM системы?](https://habr.com/ru/articles/221159/)  
- [Хабр: Всё о файлах cookie и их безопасности](https://habr.com/ru/articles/710578/)  
- [SkillFactory: XSS](https://blog.skillfactory.ru/glossary/xss/)  
- [Security Vision: Атаки на веб-системы по методологии OWASP Top 10](https://www.securityvision.ru/blog/ataki-na-veb-sistemy-po-metodologii-owasp-top-10/)  
- [GeekForGeeks: How to Prevent Broken Access Control?](https://www.geeksforgeeks.org/how-to-prevent-broken-access-control/)  
- [Хабр: Все, что нужно знать про «Broken access control](https://habr.com/ru/articles/654769/)  
- [SkillBox: OWASP Top 10: самые распространённые уязвимости веб-приложений](https://skillbox.ru/media/code/owasp-top-10-samye-rasprostranyennye-uyazvimosti-vebprilozheniy/)  
- [Хабр: SQL-инъекции](https://habr.com/ru/articles/725134/)  


