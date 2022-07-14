# Examples-Postman
Здесь представленно описание тестирования проекта DummyAPI/ USER

## Описание проекта
https://dummyapi.io/ представляет собой сервис для тестирования API. Для выполнения запросов неоходимо app-id, который генерируется автоматически после регистрации на сайте. В качестве тестирования был взят объект **USER**

### USER

#### Get List
Возвращает список публикаций отсортированных по дате создания:
- доступны созданные query params
- доступны query params разбиения на страницы

**Response Body**

**List**
Структура данных для всех ответов, которые возвращают массив данных.
```js
{
data: Array(Model)
total: number(total items in DB)
page: number(current page)
limit: number(number of items on page)
}
```
Параметр *Limit* - Предельное значение должно находиться в диапазоне [5-50]. Значение по умолчанию: 20

Проведем проверку лимитов по нижнему диапозону граничных значений. 

*Limit=49*

![Скрин postman](https://github.com/TanyaGL11/Examples-Postman/blob/main/Limit49.png "CP")

*Limit=50*

![Скрин postman](https://github.com/TanyaGL11/Examples-Postman/blob/main/Limit50.png "CP")

*Limit=51*

![Скрин postman](https://github.com/TanyaGL11/Examples-Postman/blob/main/Limit51.png "CP")
Найдена фича - limit при любом вводимом значение более 50, значение остается равное 50.

