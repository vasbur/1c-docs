GetDocumentEventList 
====================

Метод объекта [Organization](1S_Organization_Desc)

Синтаксис
GetDocumentEventList(\<EventId\>)

Параметры
-   \<EventId\> (cтрока, обязательный) идентификатор последнего
    полученного события.

Возвращаемое значение
Коллекция [Collection](1S_Collection_Desc) объектов
[DocumentEvent](1S_DocumentEvent_Desc).

Описание
Возвращает список событий, следующих за событием с идентификатором
EventId в хронологическом порядке. При этом само событие с
идентификатором EventId в этот список не включается.
