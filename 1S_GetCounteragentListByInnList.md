GetCounteragentListByInnList 
============================

Метод объекта [Organization](1S_Organization_Desc)

Синтаксис
GetCounteragentListByInnList(\<InnList\>)

Параметры
-   \<InnList\> (Строка, обязательный) - список ИНН контрагентов,
    разделенные запятой

Возвращаемое значение
Объект [AsyncResult](1S_AsyncResult_Desc).

Описание
Инициирует асинхронную операция получения списка контрагентов по списку
ИНН. Результатом асинхронной операции является объект
Collection
- коллекция объектов типа
CounteragentItem
.
