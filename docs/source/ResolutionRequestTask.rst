﻿ResolutionRequestTask
=====================

Объект предназначен для отправки запроса на согласование.

Свойства
--------

-  InitialDocumentId (строка, чтение) - идентификатор документа, для
   которого формируется запрос на согласование
-  ResolutionRequestType (строка, чтение/запись) - тип запроса на
   согласование
-  Comment (строка, чтение/запись) - комментарий к запросу согласования
-  TargetDepartmentId (строка, чтение/запись) - идентификатор
   подразделения, в которое направлен запрос
-  TargetUserId (строка, чтение/запись) - идентификатор пользователя,
   которому направлен запрос

Свойство ResolutionRequestType принимает одно из следующих значений:

-  ApprovementRequest - запрос на согласование документа
-  SignatureRequest - запрос на подпись документа

Методы
------

-  :doc:`Send <Send-(ResolutionRequestTask)>` - отправить запрос на
   согласование на сервер Диадок

.. toctree::
   :name: Auto
   :hidden:

   Send <Send-(ResolutionRequestTask)>
