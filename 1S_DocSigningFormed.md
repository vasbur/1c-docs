Подписание и отправка заранее сформированного документа 
=======================================================

 

Для отправки заранее сформированного документа необходимо использовать
метод [CreateSendTaskFromFile](1S_CreateSendTaskFromFile) объекта
[Organization](1S_Organization_Desc). В качестве параметров при вызове
метода необходимо путь до файла, в котором находится отправляемый
документ, а также тип отправляемого документа. Данный метод возвращает
объект [SendTask](1S_SendTask_Desc), устанавливая свойства которого
можно задать различные параметры отправки документа.

Например, следующая процедура позволяет отправить контрагенту счет на
оплату:

            Процедура ОтправитьСчетНаОплату()

              SendTask = Organization.CreateSendTaskFromFile(ПутьКФайлу, "ProformaInvoiceContent");
              SendTask.CounterаgentId   = CounteragentId;
              SendTask.Content.Date     = ДатаДокумента;
              SendTask.Content.Number   = НомерДокумента;
              SendTask.Content.Total    = СуммаДокумента;
              SendTask.Content.Vat      = СуммаНДСДокумента;
              SendTask.Send();

            КонецПроцедуры
          
