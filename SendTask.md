﻿
Объект предназначен для отправки сообщения на сервер Диадок.

Свойства

-   Content (чтение/запись) - содержание документа
-   CounterAgentId (строка, чтение/запись) - идентификатор контрагента
-   FileName (строка, чтение/запись) - имя файла вложения
-   Comment (строка, чтение/запись) - комментарий
-   OneSDocumentId (строка, чтение/запись) - идентификатор 1С
-   OperationId (строка, чтение/запись) - уникальный идентификатор
    операции
-   CustomDocumentId (строка, чтение/запись) - внешний идентификатор
-   FromDepartmentId (строка, чтение/запись) - идентификатор
    подразделения отправителя
-   ToDepartmentId (строка, чтение/запись) - идентификатор подразделения
    получателя
-   DelaySend (булево, чтение/запись) признак того, что сообщение будет
    сохранено без отправки
-   InitialDocuments (объект
    Collection
    , чтение) - список идентификаторов документов, на которые должен
    ссылаться отправляемый документ
-   SubordinateDocuments (объект
    Collection
    , чтение) - список идентификаторов документов, которые должны
    ссылаться на отправляемый
-   IsInternal (булево, чтение/запись) - признак того, что сообщение
    является внутренним, то есть сообщением между подразделениями
    организации

Свойство \<Content\> имеет один из следующих типов

-   InvoiceContent
    - счет-фактура/исправление счета-фактуры
-   InvoiceCorrectionContent
    - корректировочный счет-фактура/исправление корректировочного
    счета-фактуры
-   Torg12SellerContent
    - товарная накладная ТОРГ-12 титул продавца
-   Torg12BuyerContent
    - товарная накладная ТОРГ-12 титул покупателя
-   AcceptanceCertificateSellerContent
    - акт о выполнении работ/оказании услуг титул исполнителя
-   AcceptanceCertificateBuyerContent
    - акт о выполнении работ/оказании услуг титул заказчика
-   NonformilizedDocumentContent
    - неформализованный документ/протокол согласования цены/реестр
    сертификатов/акт сверки/детализация
-   Torg12Content
    - товарная накладная ТОРГ-12 в неформализованном виде
-   AcceptanceCertificateContent
    - акт о выполнении работ в неформализованном виде
-   ProformaInvoiceContent
    - счет на оплату
-   ContractDocumentContent
    - договор

Методы

-   AddInitialDocument
    - добавляет идентификатор документа в коллекцию "родительских"
    документов
-   AddSubordinateDocument
    - добавляет идентификатор документа в коллекцию подчиненных
    документов
-   Send
    - отправляет документ на сервер
-   SendAsync
    - инициирует асинхронную отправку документа
-   SaveContent
    - на основании содержания документа формирует файл документа и
    сохраняет его на диск
-   ValidateContent
    - проверяет содержание документа на корректность заполнения
-   AddStructuredDataAttachment
    - добавляет файл со структурированными данными в отправляемый
    документ
