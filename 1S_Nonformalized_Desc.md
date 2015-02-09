Nonformalized 
=============

Данный объект предназначен для работы с документами в неформализованном
формате, и является производным объектом от
[Document](1S_Document_Desc).

###Свойства объекта
 Свойство | Тип значения | Доступ | Описание
 ---------- | -------------- | -------- | ------------------------------------
 Status | Строка | Чтение | Текущий статус документа в Диадоке

Значения свойства Status
-   UnknownNonformalizedDocumentStatus - неизвестное состояние документа
-   OutboundNoRecipientSignatureRequest - документ исходящий, без
    запроса ответной подписи
-   OutboundWaitingForRecipientSignature - документ исходящий, ответная
    подпись, либо отказ от ее формирования еще не получены
-   OutboundWithRecipientSignature - документ исходящий, ответная
    подпись получена
-   OutboundRecipientSignatureRequestRejected - документ исходящий,
    получен отказ от формирования ответной подписи
-   OutboundWaitingForSenderSignature - документ исходящий, документ не
    отправлен, поскольку не подписан отправителем
-   OutboundInvalidSenderSignature - документ исходящий, документ не
    отправлен, поскольку подпись отправителя не является корректной
-   InboundNoRecipientSignatureRequest - документ входящий, без запроса
    ответной подписи
-   InboundWaitingForRecipientSignature - документ входящий, ответная
    подпись, либо отказ от ее формирования еще не отправлены
-   InboundWithRecipientSignature - документ входящий, ответная подпись
    поставлена
-   InboundRecipientSignatureRequestRejected - документ входящий,
    отправлен отказ от формирования ответной подписи
-   InboundInvalidRecipientSignature - документ входящий,
    документооборот не завершен, поскольку подпись отправителя не
    является корректной
-   InternalNoRecipientSignatureRequest - документ внутренний, документ
    без запроса ответной подписи
-   InternalWaitingForRecipientSignature - документ внутренний, ответная
    подпись
-   InternalWithRecipientSignature - документ внутренний, ответная
    подпись поставлена
-   InternalRecipientSignatureRequestRejected - документ внутренний,
    отправлен отказ от формирования ответной подписи
-   InternalWaitingForSenderSignature - документ внутренний, документ не
    отправлен, поскольку не подписан отправителем
-   InternalInvalidSenderSignature - документ внутренний, документ не
    отправлен, поскольку подпись отправителя не является корректной
-   InternalInvalidRecipientSignature - документ внутренний,
    документооборот не завершен, поскольку подпись отправителя не
    является корректной

###Методы объекта
 Метод | Описание
 -------------------------------------------------- | ----------------------------------------------
 [GetRejectionComment](1S_GetRejectionComment11) | Возвращает комментарий к отказу в подписании
 [Accept](1S_Accept11) | Формирует подпись получателя документа
 [Reject](1S_Reject11) | Формирует отказ в подписании документа

