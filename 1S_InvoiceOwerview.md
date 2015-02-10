Регламентный документооборот по электронным счетам-фактурам 
===========================================================

Для удобства работы объект [Organization](Организация)
содержит механизм автоматизированного формирования и отправки всех
технологических документов, которые требует [регламент документооборота
ЭСФ](#InvoiceDocflow). Этот механизм инкапсулирован в объекте
[ReceiptGenerationProcess](1S_ReceiptGenerationProcess_desc).

Объект [ReceiptGenerationProcess](1S_ReceiptGenerationProcess_desc)
имеет методы Start, Stop, предназначенные для запуска и остановки
процесса, соответственно. Процесс формирования технологических
документов работает в фоновом потоке и не вносит задержек в работу
интерфейса. Пример:

        ReceiptGenerationProcess = Organization.GetReceiptGenerationProcess();
        ReceiptGenerationProcess.Start();
      
