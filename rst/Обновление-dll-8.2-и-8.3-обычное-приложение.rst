Скачайте последнюю версию внешней компоненты -
`AddInDiadocAPI.dll <https://github.com/skbkontur/DiadocSDK-1C/raw/master/v40/AddInDiadocAPI.dll>`__

#. Открыть внешнюю обработку в конфигураторе, и найти в макетах
   «ФайлКомпоненты».
   Заменить двоичные данные в макете, файлом новой dll.
   |LoadDll|
#. Найти и открыть в обработке форму «Модуль\_Логика\_Версия», найти
   функцию «ТребуемаяВерсияКомпонентыДиадок», и заменить текущую строку
   с версией на строку с новой версией внешней компоненты.
   |ChangeVersion82|
#. Версию dll можно посмотреть в свойствах самой dll.
   |GetVersionDll|
#. Перезапустить 1С, и запустить модуль заново. После чего новая
   компонента будет зарегистрирована в системе.

.. |LoadDll| image:: https://github.com/skbkontur/DiadocSDK-1C/blob/master/resources/LoadDll.png
.. |ChangeVersion82| image:: https://github.com/skbkontur/DiadocSDK-1C/blob/master/resources/ChangeVersion82.png
.. |GetVersionDll| image:: https://github.com/skbkontur/DiadocSDK-1C/blob/master/resources/GetVersionDll.png
