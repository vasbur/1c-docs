
Объект предназначен для отправки сообщения на сервер Диадок.

###Свойства

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
    [Collection](Collection), чтение) - список идентификаторов документов, на которые должен
    ссылаться отправляемый документ
-   SubordinateDocuments (объект
    [Collection](Collection), чтение) - список идентификаторов документов, которые должны
    ссылаться на отправляемый
-   IsInternal (булево, чтение/запись) - признак того, что сообщение
    является внутренним, то есть сообщением между подразделениями
    организации

Свойство \<Content\> имеет один из следующих типов

-  [InvoiceContent](InvoiceContent)  - счет-фактура/исправление счет-фактуры
-  [InvoiceCorrectionContent](InvoiceCorrectionContent) - корректировочный счет-фактура/исправление корректировочного счет-фактуры
-  [Torg12SellerContent](Torg12SellerContent) - товарная накладная ТОРГ-12 титул продавца
-  [Torg12BuyerContent](Torg12BuyerContent) - товарная накладная ТОРГ-12 титул покупателя
-  [AcceptanceCertificateSellerContent](AcceptanceCertificateSellerContent) - акт о выполнении работ/оказании услуг, титул исполнителя
-  [AcceptanceCertificateBuyerContent](AcceptanceCertificateBuyerContent) - акт о выполнении работ/оказании услуг, титул заказчика
-  [NonformilizedDocumentContent](NonformilizedDocumentContent) - неформализованный документ/протокол согласования цены/реестр сертификатов/акт сверки/детализация
-   [Torg12Content](Torg12Content) - товарная накладная ТОРГ-12 в неформализованном виде
-   [AcceptanceCertificateContent](AcceptanceCertificateContent) - акт о выполнении работ в неформализованном виде
-   [ProformaInvoiceContent](ProformaInvoiceContent) - счет на оплату
-   [ContractDocumentContent](ContractDocumentContent) - договор

###Методы

-   [AddInitialDocument](AddInitialDocument) - добавляет идентификатор документа в коллекцию "родительских"    документов
-   [AddSubordinateDocument](AddSubordinateDocument) - добавляет идентификатор документа в коллекцию подчиненных
    документов
-   [Send](Send (Document)) - отправляет документ на сервер
-   [SendAsync](SendAsync) - инициирует асинхронную отправку документа
-   [SaveContent](SaveContent (SendTask)) - на основании содержания документа формирует файл документа и  сохраняет его на диск
-   [ValidateContent](ValidateContent) - проверяет содержание документа на корректность заполнения
-   [AddStructuredDataAttachment] (AddStructuredDataAttachment) - добавляет файл со структурированными данными в отправляемый документ

