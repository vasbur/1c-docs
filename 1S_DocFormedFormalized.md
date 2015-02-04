Формирование и отправка формализованного документа 
==================================================

 

В случае, когда необходимо отправить документ в формате ФНС, учетная
система, как правило, не умеет формировать документы требуемого формата.
В компоненте реализован механизм, позволяющий переложить "заботу" о
формировании xml-файла на внешнюю компоненту. От учетной системы, в этом
случае, требуется только предоставить исходные данные, необходимые для
формирования файла

Чтобы сформировать и отправить документ нужно:

-   Вызвать метод
    CreateSendTask
    объекта
    Organization
    , в качестве параметра указав тип формируемого документа
-   Получив в результате вызова метода объект
    SendTask
    , заполнить параметры отправки документа
-   заполнить информацию о документе, заполнив структуру, которая
    содержится в SendTask.Content
-   отправить документ

Пример формирования и отправки счет-фактуры

            Процедура ОтправитьЭлектронныйCчетФактуру(Organization, CounteragentId)

              SendTask = Organization.CreateSendTask("InvoiceContent");
              SendTask.CounterаgentId   = CounteragentId;

              InvoiceContent = SendTask.Content;
              InvoiceContent.Date        = '20130101';
              InvoiceContent.Number      = "1";
              InvoiceContent.Currency    = "643";

              InvoiceContent.Seller.Name = "ООО Продавец";
              InvoiceContent.Seller.Inn  = "2012500001";
              InvoiceContent.Seller.Kpp  = "111111111";
              InvoiceContent.Seller.Address.RegionCode = "66";

              InvoiceContent.Buyer.Name  = "ООО Покупатель";
              InvoiceContent.Buyer.Inn   = "2012600006";
              InvoiceContent.Buyer.Kpp   = "222222222 ID   ";
              InvoiceContent.Buyer.Address.RegionCode = "66";

              Item = InvoiceContent.AddItem();
              Item.Product               = "Товар";
              Item.UnitCode              = "166";
              Item.Quantity              = 10;
              Item.Price                 = 100;
              Item.TotalWithVatExcluded  = 1000;
              Item.TaxRate               = "18";
              Item.Vat                   = 180;
              Item.Total                 = 1180;

              SendTask.Send();

            КонецПроцедуры
          
