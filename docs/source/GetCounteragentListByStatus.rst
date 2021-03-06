﻿GetCounteragentListByStatus
===========================

Метод объекта :doc:`Organization <Организация>`

**Синтаксис:**


GetCounteragentListByStatus(<Status>)

**Параметры**


-  <Status> (строка, необязательный) - статус отношений между
   контрагентами и организацией текущего ящика

Возможные значения параметра <Status>:

-  "IsMyCounteragent" – установлены партнерские отношения в Диадоке
-  "InvitesMe" – контрагент прислал запрос на установление отношения
   партнерства
-  "IsInvitedByMe" – в адрес контрагента был отправлен запрос на
   установление отношения партнерства
-  "Rejected" – отношение партнерства было разоварвано с той или иной
   стороны, либо запрос на установление отношения партнерства был
   отклонен той или иной стороной

**Возвращаемое значение**


Коллекция :doc:`Collection <Collection>` объектов
:doc:`Counteragent <Контрагент>`.

**Описание**


Если параметр <Status> не задан, тогда функция вернет список тех
контрагентов, с которыми партнерские отношения:

-  Существуют
-  Устанавливаются (отправлено либо получено приглашение)
-  Разорваны, но когда-либо были установлены

Если параметр <Status> задан, тогда функция вернет список контрагентов
по заданному статусу отношений.
