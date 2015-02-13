
Объект предназначен для получения списка документов, отправленных из
выбранного ящика или пришедших в него.

###Свойства объекта
 Свойство | Тип значения | Доступ | Описание
 ----------------------- | -------------- | --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
 FromSendDate | Дата и время | Чтение/запись | Дата отправки или получения документа, начальная дата интервала
 ToSendDate | Дата и время | Чтение/запись | Дата отправки или получения документа, конечная дата интервала
 FromDocumentDate | Дата и время | Чтение/запись | Дата документа, начальная дата интервала
 ToDocumentDate | Дата и время | Чтение/запись | Дата документа, конечная дата интервала
 Category | Строка | Чтение/запись | Категория типов документов
 CounteragentId | Строка | Чтение/запись | идентификатор контрагента, в адрес которого были отправлены или от которого были получены документы
 DepartmentId | Строка | Чтение/запись | Идентификатор подразделения организации
 RequireOneSDocumentId | Булево | Чтение/запись | Признак того, что необходимо загружать идентификаторы 1С
 ExcludeSubdepartments | Булево | Чтение/запись | Признак того, что в выборку не нужно включать документы по подразделениям, которые являются дочерними по отношению к подразделению, идентификатор которого задан в параметре DepartmentId
 Top100 | Булево | Чтение/запись | Признак того, что нужно вернуть только первые сто документов

###Методы объекта
 Метод | Описание
 -------------------------------------------- | --------------------------------------------------------------------------------------------------
 [GetDocuments](GetDocuments) | Возвращает список документов в текущем ящике по заданному фильтру
 [GetDocumentsAsync](GetDocumentsAsync) | Инициирует асинхронную операцию получения списка документов в текущем ящике по заданному фильтру

Использовать параметры FromSendDate/ToSendDate и
FromDocumentDate/ToDocumentDate одновременно нельзя. Фильтрация
производится либо по дате документа, либо по дате его передачи через
Диадок.

Обязательный параметр \<FilterCategory\> задается строкой в формате
"ТИП\_ДОКУМЕНТА.ТИП\_ФИЛЬТРА". Первая часть строки задает тип документа
и может принимать одно из следующих значений:

-   Any – любой документ
-   Invoice – счет-фактура
-   InvoiceRevision – исправление счета-фактуры
-   InvoiceCorrection – корректировочный счет-фактура
-   InvoiceCorrectionRevision – исправление корректировочного
    счета-фактуры
-   AnyInvoiceDocumentType – любой вид счет-фактуры
-   Torg12 – неформализованная накладная ТОРГ-12
-   XmlTorg12 – накладная ТОРГ-12 в формате ФНС
-   AcceptanceCertificate – неформализованный акт о выполнении работ
-   XmlAcceptanceCertificate – акт о выполнении работ в формате ФНС
-   TrustConnectionRequest – запрос на инициацию канала обмена
    документами через Диадок
-   PriceListAgreement – протокол согласования цены
-   CertificateRegistry – реестр сертификатов
-   ReconciliationAct – акт сверки
-   Contract – договор
-   ProformaInvoice – счет на оплату
-   ServiceDetails – детализация

ТИП\_ФИЛЬТРА указывает дополнительную информацию для отбора документов
указанного типа. Набор возможных значений фильтра зависит от типа
выбираемого документа.

###Таблица возможных значений
<table>
    <title>Таблица возможных значений </title>
      <thead>
        <tr>
          <td>Тип_Документа</td>
          <td>Тип_Фильтра, описание</td>
        
        </tr>
      </thead>
      <tbody>
        <tr>
          <td colspan=2 align="center">
            <b>Отбор по статусу подписания документа</b>
          </td>
        </tr>
        <tr>
          <td rowspan=4>Все типы документов</td>
          <td>Inbound  
<br>Все входящие документы </td>
         
        </tr>
        <tr>
          <td>Outbound
<br>Все исходящие документы</td>
        </tr>
        <tr>
          <td>OutboundWaitingForSenderSignature<br>Исходящие документы, требующие подписания и отправки</td>
        </tr>
        <tr>
          <td>OutboundInvalidSenderSignature<br>Исходящие документы с невалидной подписью отправителя, требующие повторного подписания и отправки</td>
        </tr>

        <tr>
          <td rowspan=4>
          		<ul>
          			<li>Invoice</li>
          			<li>InvoiceRevision</li>
          			<li>InvoiceCorrection</li>
          			<li>InvoiceCorrectionRevision</li>
          			<li>AnyInvoiceDocumentType</li>
          		</ul>
          </td>
          <td>OutboundNotFinished<br>Исходящий, документооборот не завершен</td>
    
        </tr>
        <tr>
          <td>OutboundFinished<br>Исходящий, документооборот завершен</td>
        </tr>
        <tr>
          <td>InboundNotFinished<br>Входящий, документооборот не завершен</td>
        </tr>
        <tr>
          <td>InboundFinished<br>Входящий, документооборот завершен</td>
        </tr>


        <tr>
          <td rowspan=6>
            	<ul>
          			<li>Torg12</li>
          			<li>XmlTorg12</li>
          			<li>AcceptanceCertificate</li>
          			<li>XmlAcceptanceCertificate</li>
          			<li>Nonformalized</li>
          			<li>TrustConnectionRequest</li>
          			<li>PriceListAgreement</li>
          			<li>CertificateRegistry</li>
          			<li>ReconciliationAct</li>
          			<li>Contract</li>
          		</ul>
          </td>
          <td>OutboundWaitingForRecipientSignature <br>Исходящий документ в ожидании ответной подписи</td>
    
        </tr>
        <tr>
          <td>OutboundWithRecipientSignature <br>Исходящий документ с ответной подписью</td>
        </tr>
        <tr>
          <td>OutboundRecipientSignatureRequestRejected<br>Исходящий документ с отказом в ответной подписи</td>
        </tr>
        <tr>
          <td>InboundWaitingForRecipientSignature <br>Входящий документ в ожидании ответной подписин</td>
        </tr>
        <tr>
          <td>InboundWithRecipientSignature <br>Входящий документ с ответной подписью</td>
        </tr>
        <tr>
          <td>InboundRecipientSignatureRequestRejected  <br>Входящий документ с отказом в ответной подписи</td>
        </tr>

        <tr>
          <td rowspan=2>
            	<ul>
          			<li>Nonformalized</li>
          			<li>PriceListAgreement</li>
          			<li>CertificateRegistry</li>
          		</ul>
          </td>
          <td>OutboundNoRecipientSignatureRequest <br>Исходящий документ без запроса ответной подписи</td>
        </tr>
          <tr>
            <td>InboundNoRecipientSignatureRequest  <br>Вхдящий документ без запроса ответной подписи</td>
          </tr>
           <tr>
            <td colspan="3" align="center">
                <b>Отбор по статусу согласования документа</b>
          </td>
          </tr>
        <tr>
          <td rowspan=6>
           Все типы документов

          </td>
          <td>OutboundWaitingForResolution   <br>Исходящий документ, переданный на согласование или подписание</td>
        </tr>
        <tr>
          <td>OutboundApproved<br>Согласованный исходящий документ</td>
        </tr>
        <tr>
          <td>OutboundDisapproved<br>Исходящий документ с отказом в согласовании</td>
        </tr>
        <tr>
          <td>InboundWaitingForResolution  <br>Входящий документ, переданный на согласование или подписание</td>
        </tr>
        <tr>
          <td>InboundApproved<br>Согласованный входящий документ</td>
        </tr>
        <tr>
          <td>InboundDisapproved<br>Входящий документ с отказом в согласовании</td>
        </tr>

        <tr>
          <td colspan="3" align="center">
              <b>Отбор по статусу аннулирования документа</b>
          </td>
        </tr>
        
        <tr>
          <td rowspan="8" >
            Все типы документов
          </td>
          <td>OutboundRevocationIsRequestedByMe<br>Исходящий документ, по которому запрошено аннулирование у другой стороны</td>
        </tr>
        <tr>
          <td>OutboundRequestsMyRevocation<br>Исходящий документ, по которому другой стороной запрошено аннулирование</td>
        </tr>

        <tr>
          <td>OutboundRevocationAccepted<br>Исходящий аннулированный документ</td>
        </tr>
        <tr>
          <td>OutboundRevocationRejected<br>Исходящий документ, по которому получен отказ на запрос об аннулировании</td>
        </tr>
    
        <tr>
          <td>InboundRevocationIsRequestedByMe<br>Входящий документ, по которому запрошено аннулирование у другой стороны</td>
        </tr>
        <tr>
          <td>InboundRequestsMyRevocation<br>Входящий документ, по которому другой стороной запрошено аннулирование</td>
        </tr>

        <tr>
          <td>InboundRevocationAccepted<br>Входящий аннулированный документ</td>
        </tr>
        <tr>
          <td>InboundRevocationRejected<br>Входящий документ, по которому получен отказ на запрос об аннулировании</td>
        </tr>
      </tbody>
    </tgroup>
  </table>

Пример использования
Следующая процедура позволяет получить список всех входящих
формализованных торг-12, которые требуется подписать:

        Процедура ПолучитьСписокНеподписанныхТорг12(Organization)
            DocumentsTask = Organization.GetDocumentsTask();
            DocumentsTask.FromSendDate = НачалоГода(ТекущаяДата());
            DocumentsTask.ToSendDate = КонецГода(ТекущаяДата());
            DocumentsTask.Category = "XmlTorg12.InboundWaitingForRecipientSignature";

            DocumentList = DocumentsTask.GetDocuments();
            ц = 0;
            Пока ц < DocumentList.Count цикл
                Document = DocumentList.GetItem(ц);
                Сообщить("Не подписан торг-12 №"+Document.Number+" от "+Document.Date);
                ц = ц +1;
            КонецЦикла;
        КонецПроцедуры

      
