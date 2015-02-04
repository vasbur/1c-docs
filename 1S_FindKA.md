Найти контрагента 
=================

 

Найти контрагента в Диадоке возможно с помощью поиска по ИНН/КПП. С
помощью компоненты можно реализовать несколько способов поиска
контрагента.

-   Поиск по ИНН/КПП в синхронном режиме, для этого можно использовать
    метод
    GetCounteragentListByInnKpp
                    ЯщикиКонтрагентов = Новый Массив;

                    ИНН= СокрЛП(Контрагент.ИНН);
                    КПП= СокрЛП(Контрагент.КПП);

                    //Получаем список контрагентов с заданными ИНН/КПП
                    CounteragentList = Organization.GetCounteragentListByInnKpp(ИНН, КПП);
                    Для Ц = 0 по CounteragentList.count-1 Цикл
                      ЯщикиКонтрагентов.Добавить(CounteragentList.GetItem(Ц));
                    КонецЦикла;
                  

-   Поиск по списку ИНН, для получения результата в асинхронном режиме,
    можно воспользоваться методом
    GetCounteragentListByInnList
    объекта объекта
    Organization
                    //Получаем результат асинхронной операции по строке содержащей список ИНН
                    CounteragentList=   Organization.GetCounteragentListByInnList(СтрокаИНН);

                    Если CounteragentList.IsCompleted Тогда
                      РезультатЗапроса = CounteragentList.Result;
                      Item = РезультатЗапроса.GetItem(0);
                      Counteragent = Item.Counteragent;
                    КонецЕсли;

                  


