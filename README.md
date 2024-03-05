# Balance parcer for avito
Парсер для Авито, который позволяет узнать остаток Баланса на счету, количество откликов на объявления и колличество оставшихся объявлений и записать всё в Excel, для дальнейшего анализа данных.
Инструмент может быть особо полезен для операторов Такси-агрегаторов, которые на ежедневной основе выкладывают объвления о работе.

## Содержание
- [Технологии](#технологии)
- [API links for AvitoBalanceParser](#api-links-for-avitobalanceparser)
- [Использование](#использование)
- [Удобство использования](#удобство-использования)

## Технологии
- [Python](https://www.python.org/)
- [auto-py-to-exe](https://pypi.org/project/auto-py-to-exe/)

## API links for AvitoBalanceParser
Ссылки на используемые функции в API
- [Get token](https://developers.avito.ru/api-catalog/auth/documentation#operation/getAccessToken)
- [Get advance](https://developers.avito.ru/api-catalog/cpa/documentation#operation/balanceInfoV2)
- [Get applies](https://developers.avito.ru/api-catalog/job/documentation#operation/applicationsGetByIds)
- [Get advertisements](https://developers.avito.ru/api-catalog/item/documentation#operation/getItemsInfo)

## Использование
- Заготовить файл, с колонками:
Номер Авито|Деньги|Отклики|Обьявления|clientId|clientSecret
![image](https://github.com/makSSMZ/avito-balance-parser/assets/47451880/a28eb959-e609-4a5c-8942-006fc684e5ed)

- Получить [API-Ключ](https://www.avito.ru/legal/pro_tools/public-api) (client_id и client_secret) и внести его в Excel файл, колонки clientId и clientSecret соотвественно.
- Указать необходимые настройки для Excel в файле config.ini:
```
[SETTINGS]
AvitoLink = https://api.avito.ru  - Ссылка на API Авито
ExcelPath = Test.xlsx - Путь к итоговому Excel файлу
AdvanceCellLetter = B - Буква колонки, куда неоходимо записать остаток Баланса
AppliesCellLetter = C - Буква колонки, куда неоходимо записать количество откликов на объявления
AdsCountCellLetter = D - Буква колонки, куда неоходимо записать колличество оставшихся объявлений
PageCount = 15 - Сколько парсить страниц для объявлений. (В АПИ авито есть гораничение на 100 выводимых объявлений на страницу. Соотвественно, указав 15 страниц, мы получим максимальное количество объявлени в 1500)
```
- Запустить скрипт __init__.py на выполнение

## Удобство использования
Выполнение без необходимости установки Python можно реализовать с помощью утилиты [auto-py-to-exe](https://pypi.org/project/auto-py-to-exe/) - способ использования хорошо описан в [статье](https://habr.com/ru/companies/vdsina/articles/557316/)
