﻿
Объект предназначен для работы с содержанием документов «счет-фактура» и
«исправление счет-фактуры».

###Свойства объекта
 Свойство | Тип значения | Доступ | Ограничения | Описание
 ----------------------- | --------------------------------------------------------------------------------------- | --------------- | ----------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------
 Date | Дата | Чтение/запись | Обязательно для заполнения | Дата счет-фактуры
 Number | Строка | Чтение/запись | Обязательно для заполнения, длина не более 256 символов | Номер счет-фактуры
 InvoiceRevisionDate | Дата | Чтение/запись | --- | Дата исправленния счет-фактуры (обязательно при формировании InvoiceRevision)
 InvoiceRevisionNumber | Строка | Чтение/запись | Длина не более 3 символов | Номер исправления счет-фактуры (обязательно при формировании InvoiceRevision)
 Currency | Строка | Чтение/запись | Обязательно для заполнения. Числовая строка длиной 3 символа. Код должен содержаться в общероссийском классификаторе валют. | Код валюты
 Seller | объект [OrganizationInfo](OrganizationInfo) | Чтение | Обязательно для заполнения | Данные продавца
 Buyer | объект [OrganizationInfo](OrganizationInfo) | Чтение | Обязательно для заполнения | Данные покупателя
 Shipper | объект [ShipperOrConsigneeInfo](ShipperOrConsigneeInfo) | Чтение | --- | Данные грузоотправителя
 Consignee | объект [ShipperOrConsigneeInfo](ShipperOrConsigneeInfo) | Чтение | --- | Данные грузополучателя
 Signer | объект [Signer](Signer) | Чтение | Обязательно для заполнения | Данные подписанта документа
 Totals | [InvoiceTotals](Итоги InvoiceTotals) | Чтение | --- | Общие итоги по документу
 Type | Строка | Чтение | --- | Тип документа
 Items | [Коллекция](Collection) объектов [InvoiceItem](InvoiceItem (Invoice))           Ч | тение          О | бязательно для заполнения                                                                                                    Т | абличная часть счет-фактуры
 PaymentDocuments | [Коллекция](Collection) объектов [PaymentDocument](PaymentDocument)   Ч | тение          - | --                                                                                                                           С | писок платежно-расчетных документов
 AdditionalInfo | Строка | Чтение/запись | --- | Дополнительные сведения

###Методы объекта
 Метод | Описание
 ---------------------------------------------- | ---------------------------------------------------
 [AddItem](AddItem (InvoiceContent)) | Добавляет строку в табличную часть счет-фактуры
 [AddPaymentDocument](AddPaymentDocument (InvoiceContent)) | Добавляет сведения о платежно-расчетном документе

