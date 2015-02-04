Создать контекст работы с организацией 
======================================

 

Все действия с документами: отправка, получение, подписание и т.д.
выполняются в контексте организации, к которой пользователь имеет права
доступа в системе Диадок. Для работы с контекстом организации
предназначен объект [Organization](1S_Organization_Desc). Он получается
через объект [DiadocConnection](1S_DiadocConnection_Desc). Получить
объект Organization можно одним из двух способов:

-   Получив объект [Organization](1S_Organization_Desc) по
    идентификатору. Пример:

                    OrganizationId = "8fd0af8abe934c7091b5ccd476ef1cb5@diadoc.ru";
                    ДиадокКонтекстОрганизации = ДиадокСоединение.GetOrganizationById(OrganizationId);
                  

-   Получив массив всех объектов [Organization](1S_Organization_Desc)
    всех доступных ящиков. Пример:

                      OrganizationList = ДиадокСоединение.GetOrganizationList();
                        Ц = 0;
                        Пока Ц < OrganizationList.Count() Цикл
                          Organization = OrganizationList.GetItem(ц);
                          Сообщить(Organization.Name);
                        Ц = Ц + 1;
                      КонецЦикла;
                    


