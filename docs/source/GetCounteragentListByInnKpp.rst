﻿GetCounteragentListByInnKpp
===========================

Метод объекта :doc:`Organization <Организация>`

**Синтаксис**


GetCounteragentListByInnKpp(<Inn>, <Kpp>)

**Параметры**


-  <Inn> (строка, обязательный) - ИНН контрагента
-  <Kpp> (строка, необязательный) - КПП контрагента

**Возвращаемое значение**


Коллекция :doc:`Collection <Collection>` объектов
:doc:`Counteragent <Контрагент>`.

**Описание**


Возвращает список контрагентов, у которых ИНН и КПП совпадают с
заданными.

Если КПП не задан, то поиск осуществляется только по ИНН.
