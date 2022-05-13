﻿# .NET API Банка

Простая реализация API банка на .NET 6, C#, Postgresql для проекта по предмету `Интеллектуальные мобильные приложения` в ВУЗе `РТУ МИРЭА` от студента: `Курамшина Анастасия Романовна`, группы: `БСБО-08-20`. 

## Основные функции банка
Банк позволяет создавать пользователей (клиентов) банка, счета для них в трех разных валютах (RUB, USD, EUR), осуществлять переводы между клиентами банка и просматривать историю переводов. При переводе между банковскими счетами разных клиентов берется комиссия в 2% от суммы перевода. При переводе средств между банковскими счетами одного пользователя комиссия не взымается. При переводе между банковскими счетами, имеющими различные типы валюыт, происходит конвертация валют с использованием [сервиса ЦБ](https://www.cbr-xml-daily.ru/daily_json.js)

## Использование
### Установка с использованием docker-compose
1. Открываем терминал или powershell
2. Клонируем данный репозиторий
3. Меняем текущую директиву на Minibank, используя команду:
    ```bash
    cd Minibank
    ```
4. Запускаем docker-compose, используя команду:
    ```bash
    docker-compose -f build/docker-compose.yml up
    ```
5. Чтобы использовать `Swagger` переходим по адресу: `http://localhost:2109`. Если нужно подключиться к базе, используйте следующие данные: </br>
**Адрес:** localhost </br>
**Порт:** 1602 </br>
**POSTGRES_USER:** minibank-postgres-user </br>
**POSTGRES_PASSWORD:** qwerty12345 </br>

6. Чтобы использовать API банка, сначала необходимо авторизоваться, используя swagger UI (зеленая кнопка `Authorize` в правом верхнем углу). Для авторизации используйте один из следующих пользователей: [демо-клиенты](https://demo.duendesoftware.com/). Например: client_id: m2m, client_secret: secret
