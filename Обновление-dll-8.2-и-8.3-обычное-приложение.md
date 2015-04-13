Скачайте последнюю версию внешней компоненты - [AddInDiadocAPI.dll](https://github.com/skbkontur/DiadocSDK-1C/raw/master/v40/AddInDiadocAPI.dll)

1. Открыть внешнюю обработку в конфигураторе, и найти в макетах «ФайлКомпоненты».
Заменить двоичные данные в макете, файлом новой dll.
![LoadDll](https://github.com/skbkontur/DiadocSDK-1C/blob/master/resources/LoadDll.png)
2. Найти и открыть в обработке форму «Модуль_Логика_Версия», найти функцию «ТребуемаяВерсияКомпонентыДиадок», и заменить текущую строку с версией на строку с новой версией внешней компоненты.
![ChangeVersion82](https://github.com/skbkontur/DiadocSDK-1C/blob/master/resources/ChangeVersion82.png)
3. Версию dll можно посмотреть в свойствах самой dll.
![GetVersionDll](https://github.com/skbkontur/DiadocSDK-1C/blob/master/resources/GetVersionDll.png)
4. Перезапустить 1С, и запустить модуль заново. После чего новая компонента будет зарегистрирована в системе.