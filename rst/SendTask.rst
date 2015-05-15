Объект предназначен для отправки сообщения на сервер Диадок.

Свойства
~~~~~~~~

-  Content (чтение/запись) - содержание документа
-  CounterAgentId (строка, чтение/запись) - идентификатор контрагента
-  FileName (строка, чтение/запись) - имя файла вложения
-  Comment (строка, чтение/запись) - комментарий
-  OneSDocumentId (строка, чтение/запись) - идентификатор 1С
-  OperationId (строка, чтение/запись) - уникальный идентификатор
   операции
-  CustomDocumentId (строка, чтение/запись) - внешний идентификатор
-  FromDepartmentId (строка, чтение/запись) - идентификатор
   подразделения отправителя
-  ToDepartmentId (строка, чтение/запись) - идентификатор подразделения
   получателя
-  DelaySend (булево, чтение/запись) признак того, что сообщение будет
   сохранено без отправки
-  InitialDocuments (объект
   `Collection <Collection>`__, чтение) - список идентификаторов
   документов, на которые должен
   ссылаться отправляемый документ
-  SubordinateDocuments (объект
   `Collection <Collection>`__, чтение) - список идентификаторов
   документов, которые должны
   ссылаться на отправляемый
-  IsInternal (булево, чтение/запись) - признак того, что сообщение
   является внутренним, то есть сообщением между подразделениями
   организации

Свойство \\ имеет один из следующих типов

-  `InvoiceContent <InvoiceContent>`__ - счет-фактура/исправление
   счет-фактуры
-  `InvoiceCorrectionContent <InvoiceCorrectionContent>`__ -
   корректировочный счет-фактура/исправление корректировочного
   счет-фактуры
-  `Torg12SellerContent <Torg12SellerContent>`__ - товарная накладная
   ТОРГ-12 титул продавца
-  `Torg12BuyerContent <Torg12BuyerContent>`__ - товарная накладная
   ТОРГ-12 титул покупателя
-  `AcceptanceCertificateSellerContent <AcceptanceCertificateSellerContent>`__
   - акт о выполнении работ/оказании услуг, титул исполнителя
-  `AcceptanceCertificateBuyerContent <AcceptanceCertificateBuyerContent>`__
   - акт о выполнении работ/оказании услуг, титул заказчика
-  `NonformilizedDocumentContent <NonformilizedDocumentContent>`__ -
   неформализованный документ/протокол согласования цены/реестр
   сертификатов/акт сверки/детализация
-  `Torg12Content <Torg12Content>`__ - товарная накладная ТОРГ-12 в
   неформализованном виде
-  `AcceptanceCertificateContent <AcceptanceCertificateContent>`__ - акт
   о выполнении работ в неформализованном виде
-  `ProformaInvoiceContent <ProformaInvoiceContent>`__ - счет на оплату
-  `ContractDocumentContent <ContractDocumentContent>`__ - договор

Методы
~~~~~~

-  `AddInitialDocument <AddInitialDocument>`__ - добавляет идентификатор
   документа в коллекцию "родительских" документов
-  `AddSubordinateDocument <AddSubordinateDocument>`__ - добавляет
   идентификатор документа в коллекцию подчиненных
   документов
-  `Send <Send%20(Document)>`__ - отправляет документ на сервер
-  `SendAsync <SendAsync>`__ - инициирует асинхронную отправку документа
-  `SaveContent <SaveContent%20(SendTask)>`__ - на основании содержания
   документа формирует файл документа и сохраняет его на диск
-  `ValidateContent <ValidateContent>`__ - проверяет содержание
   документа на корректность заполнения
-  [AddStructuredDataAttachment] (AddStructuredDataAttachment) -
   добавляет файл со структурированными данными в отправляемый документ
