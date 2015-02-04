GetCounteragentListByInnKpp 
===========================

Метод объекта [Organization](1S_Organization_Desc)

Синтаксис
GetCounteragentListByInnKpp(\<Inn\>, \<Kpp\>)

Параметры
-   \<Inn\> (строка, обязательный) - ИНН контрагента
-   \<Kpp\> (строка, необязательный) - КПП контрагента

Возвращаемое значение
Коллекция [Collection](1S_Collection_Desc) объектов
[Counteragent](1S_Counteragent_Desc).

Описание
Возвращает список контрагентов, у которых ИНН и КПП совпадают с
заданными.

Если КПП не задан, то поиск осуществляется только по ИНН.
