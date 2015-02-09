﻿Как подписать входящий документ 
===============================

 

Входящие электронные документы, который требуют ответной подписи, можно
обработать несколькими способами

1.  Подписать документ

    -   Для формализованных документов требуется сначала сформировать
        т.н. титул покупателя
        [Torg12BuyerContent](1S_Torg12BuyerContent_Desc) или
        [AcceptanceCertificateBuyerContent](1S_AcceptanceCertificateBuyerContent_Desc),
        и создать задание методом
        [CreateReplySendTask](1S_CreateReplySendTask2)

        Пример кода, формирующий задание на подписание торг-12:

                            ReplySendTask=  Document.CreateReplySendTask();

                            ReplySendTask.Content.ShipmentReceiptDate = ТекущаяДата();

                            ReplySendTask.Content.Signer.IsSoleProprietor = Ложь;
                            ReplySendTask.Content.Signer.Surname = "Иванов";
                            ReplySendTask.Content.Signer.FirstName = "Иван";
                            ReplySendTask.Content.Signer.Patronymic = "Иванович";
                            ReplySendTask.Content.Signer.JobTitle = "Директор";
                            ReplySendTask.Content.Signer.INN = "123456789";
                            ReplySendTask.Content.Signer.SoleProprietorRegistrationCertificate = "";

                            ReplySendTask.Send();
                          

    -   Неформализованные документы подписываются методом Accept
        ([Accept объекта NonformalizedTorg12](1S_Accept), [Accept
        объекта Nonformalized](#1S_Accept11) и т.д.)

        Пример:

                            Document.Accept();
                          

2.  Отказать в подписи

    Для всех типов документов применятся метод Reject ([Reject объекта
    NonformalizedTorg12](#1S_Reject), [Reject объекта
    XmlTorg12](#1S_Reject2) и т.д.), где параметром можно передать свой
    комментарий отказа в подписи

    Пример:

                    СвойКомментарийКОтказу = "Не удовлетворяет условиям договора";
                    Document.Reject(СвойКомментарийКОтказу);
                  

