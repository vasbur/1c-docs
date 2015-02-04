Установить партнерство 
======================

 

Для установления партнерства между организациями А и Б в Диадоке,
организация А должна отправить, а организация Б принять запрос на
установление партнерства.

Для отправки, принятия или отклонения запроса, а также для разрыва
партнерских отношений используются методы объекта
[Counteragent](1S_Counteragent_Desc):

-   AcquireCounteragent
    – отправка запроса и подтверждение входящего запроса от контрагента.
                    //Находим контрагента по ИНН/КПП
                    CounteragentList = Organization.GetCounteragentListByInnKpp(ИНН, КПП);
                    Counteragent = CounteragentList.GetItem(0);
                    //Принимаем запрос или отправляем приглашение
                    Counteragent.AcquireCounteragent("Приглашаем к партнерству");

                    //Или если у нас имеется ID контрагента, получаем его по ID
                    Counteragent = Organization.GetCounteragentById(CounteragentId);
                    Counteragent.AcquireCounteragent("Приглашаем к партнерству");
                  

-   BreakWithCounteragent
    – отклонение запроса и разрыв существующего партнерства.
                    //Находим контрагента по ИНН/КПП
                    CounteragentList = Organization.GetCounteragentListByInnKpp(ИНН, КПП);
                    Counteragent = CounteragentList.GetItem(0);
                    //Отклоняем запрос или разрываем взаимоотношения
                    Counteragent.BreakWithCounteragent("Отказываем в партнерстве");

                    //Или если у нас имеется ID контрагента, получаем его по ID
                    Counteragent = Organization.GetCounteragentById(CounteragentId);
                    Counteragent.BreakWithCounteragent("Отказываем в партнерстве");
                  

Для получения списка контрагентов в зависимости от статуса партнерства
предназначен метод
[GetCounteragentListByStatus](1S_GetCounteragentListByStatus) объекта
[Organization](1S_Organization_Desc).

Для получения объекта [Counteragent](1S_Counteragent_Desc) по
идентификатору ящика организации используется метод
[GetCounteragentById](1S_GetCounteragentById) объекта
[Organization](1S_Organization_Desc).

Важно. Партнерство с контрагентом необходимо устанавливать для каждой
нашей организации.
