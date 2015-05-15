Скачайте zip архив, содержащий файл компоненты -
`AddInDiadocApi.zip <https://github.com/skbkontur/DiadocSDK-1C/raw/master/v40/AddInDiadocApi.zip>`__

#. Открыть внешнюю обработку через конфигуратор, в списке макетов найти
   «ФайлКомпоненты\_%ВашаВерсияКомпоненты%» Заменить в макете двоичные
   данные новым архивом.
   |LoadZip|
#. В названии макета вместо текущих цифр версии вставить новую версию
   внешней компоненты. Вместо «.» использовать разделитель «\_».
   Например если версия 4.1.0.3 название макета должно быть
   «ФайлКомпоненты\_4\_1\_0\_3».
   |ModelVersion|
#. Найти и открыть форму в обработке с названием
   «Модуль\_Логика\_Версия», далее найти функцию
   «ТребуемаяВерсияКомпонентыДиадок», и заменить текущую строку с
   версией на строку с новой версией внешней компоненты.
   |GetVersionDll83|
#. Версию dll можно посмотреть в свойствах самой dll.
   |GetVersionDll|
#. Перезапустить 1С, и запустить модуль заново. После чего новая
   компонента будет зарегистрирована в системе.

.. |LoadZip| image:: https://github.com/skbkontur/DiadocSDK-1C/blob/master/resources/LoadZip.png
.. |ModelVersion| image:: https://github.com/skbkontur/DiadocSDK-1C/blob/master/resources/ModelVersion.png
.. |GetVersionDll83| image:: https://github.com/skbkontur/DiadocSDK-1C/blob/master/resources/GetVersionDll83.png
.. |GetVersionDll| image:: https://github.com/skbkontur/DiadocSDK-1C/raw/master/resources/GetVersionDll.png
