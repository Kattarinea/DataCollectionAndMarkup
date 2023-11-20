# DataCollectionAndMarkup
В данном репозитории содержатся файлы собраных датасетов при помощи web-scraping (MyDataset - датасет ресторанов/кафе с сайта https://www.restoclub.ru для Питера и Екатеринбурга [698 записей]; MyDataset_afisha_novosib - датасет ресторанов/кафе с сайта  https://www.afisha.ru для Новосибирска [1972 записи]; MyDataset_afisha_spb - датасет ресторанов/кафе с сайта  https://www.afisha.ru для Питера [1992 записи]) и открытый датасет (датасет заведений общественного питания Москвы с GitHub - https://github.com/gantsel/Market_of_public_catering_establishments_in_Moscow [8406 записей]). 

После обработки данных/удаления дублей суммарно итоговый датасет стал содержать в себе 12835 записей. Он содержит в себе следующие колонки:
name — название заведения;
address — адрес заведения;
category — категория заведения, например «кафе», «пиццерия» или «кофейня»;
hours — информация о днях и часах работы;
rating — рейтинг заведения по оценкам пользователей в Яндекс Картах (высшая оценка — 5.0);
avg_bill — строка, которая хранит среднюю стоимость заказа в виде диапазона;
city — город, в котором расположено заведение;
chain — число, выраженное 0 или 1, которое показывает, является ли заведение сетевым;
middle_coffee_cup — число с оценкой одной чашки капучино;
avg_bill_from — значение цены ОТ, взятой из avg_bill;
avg_bill_to — значение цены ДО, взятой из avg_bill;
seats — количество посадочных мест.

Для датасетов, полученных методом web-scraping информации по полям middle_coffee_cup, seats найдено не было.
При проведении EDA было обнаружено 19 категорий заведений. На рисунке ниже видны эти категории и их количество. Наиболее популярными являются рестораны и кафе. Есть категория "Чайная", к которой относится всего лишь одно заведение. Наверное, его лучше добавить в категорию кафе, так как такого рода заведения не сильно отличаются. "Кулинарную студию" сложно отнести к какому-то другому классу, поэтому ее лучше трогать не будем. "Спортбар" и "Винотека", возможно, стоило бы отнести к категории "бар, паб", но есть ощущение, что у данных заведений немного другой формат.

![image](https://github.com/Kattarinea/DataCollectionAndMarkup/assets/65298723/6f283047-64b0-4581-96e9-38c1289d69d3)

Был проведен анализ на количество сетевых и несетевых мест. Как видно из графика, несетевых заведений больше в нашем датасете.

![image](https://github.com/Kattarinea/DataCollectionAndMarkup/assets/65298723/31176b65-c29b-4a8e-917b-002ae73c5fe5)

Сетевыми в основном являются кофейни, рестораны и кафе.

![image](https://github.com/Kattarinea/DataCollectionAndMarkup/assets/65298723/9a876fa6-3bb4-4585-acde-9f2e139c7898)

В процентном соотношении пекарен, фастфуда, кондитерских больше сетевых. Меньше сетевых в процентном соотношении баров, караоке и банкетных залов. Кулинарию не учитываем, как наиболее "сетевую", так как их в нашей выборке очень мало.

![image](https://github.com/Kattarinea/DataCollectionAndMarkup/assets/65298723/50fe7dcc-6962-4256-b6f8-1846cc6404e2)

Анализ рейтинга заведений показал, что кондитерские и караоке не имеют максимальных оценок. По среднему рейтингу данные заведения ниже остальных. Низкие оценки встречаются не очень редко. Больше всего они наблюдаются у кафе и ресторанов, что логично, их и в датасете больше.

![image](https://github.com/Kattarinea/DataCollectionAndMarkup/assets/65298723/78b0b140-ac5c-4be0-b112-aab8288343c0)

Анализ среднего чека ОТ показал, что наиболее дорогим заведением является Винотека, что неуидвительно. Для некоторых категорий у нас нет цены от, поэтому получили 0.

![image](https://github.com/Kattarinea/DataCollectionAndMarkup/assets/65298723/0df6da0e-106f-45b3-8fa8-28ac0f907b83)

При анализе среднего чека ДО, выяснили, что Винотека также самая дорогая, а кофейня самая дешевая.

![image](https://github.com/Kattarinea/DataCollectionAndMarkup/assets/65298723/fc4ab0c6-9937-4d8e-9eb5-9484c852bfc1)

Данный датасет может быть использован для решения задачи классификации - определение категории завдения, определение города, к которому относится заведение. Предсказание среднего чека заведения или его рейтинга.
