Сначала необходимо скачать zip архив содержащий файл компоненты и файл сопровождения - [AddInDiadocApi.zip](https://github.com/skbkontur/DiadocSDK-1C/blob/master/v40/AddInDiadocApi.zip)
1. Открыть внешнюю обработку через конфигуратор, в списке макетов найти «ФайлКомпоненты_%ВашаВерсияКомпоненты%» Заменить в макете  двоичные данные новым архивом.
![LoadZip](https://github.com/skbkontur/DiadocSDK-1C/blob/master/resources/LoadZip.png)
2. В названии макета вместо текущих цифр версии вставить новую версию внешней компоненты. Вместо «.» использовать разделитель «_». Например если версия 4.1.0.3 название макета должно быть «ФайлКомпоненты_4_1_0_3».
![ModelVersion](https://github.com/skbkontur/DiadocSDK-1C/blob/master/resources/ModelVersion.png)
3. Найти и открыть форму в обработке с названием «Модуль_Логика_Версия», далее найти функцию «ТребуемаяВерсияКомпонентыДиадок», и заменить текущую строку с версией на строку с новой версией внешней компоненты.
![GetVersionDll83](https://github.com/skbkontur/DiadocSDK-1C/blob/master/resources/GetVersionDll83.png)
4. Версию dll можно посмотреть в свойствах самой dll.
![GetVersionDll](https://github.com/skbkontur/DiadocSDK-1C/raw/master/resources/GetVersionDll.png)