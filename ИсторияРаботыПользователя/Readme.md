# История работы пользователей

Отчет для просмотра истории работы пользователей (СКД, просмотр для любого пользователя).

Материалы по другим темам Вы можете найти на сайте [ypermitin.github.io](https://ypermitin.github.io/), а новости по проектам или новым материалам в [Telegram-канале](https://t.me/TinyDevVault).

## Состав

* [media](media) - медиафайлы для документации данной разработки.
* [src](src) - файлы исходного кода.

## Назначение и возможности

Отчет для просмотра истории работы пользователей, доступной в платформе 1С. В историю работы автоматически попадают события интерактивного добавления или изменения объектов информационной базы (документов, элементов справочника и пр.), а также открытие форм списков, обработок и так далее. Также, в некоторых случаях события в историю работы могут быть добавлены программно. Все это работает только для управляемого интерфейса.

![Форма отчета](./media/1%2C%20%D0%A4%D0%BE%D1%80%D0%BC%D0%B0%20%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0.png)

Штатно эту историю можно просматривать в предназначенном для этого окне и только для текущего пользователя. То есть посмотреть историю работы различных пользователей штатными средствами платформы 1С не получится. Но есть другой путь, а именно - этот отчет.

Основными возможностями инструмента являются:

* Просмотр истории работы текущего пользователя (аналогично штатному функционалу платформы 1С). Доступно как для файлового, так и для клиент-серверного режима работы.
* Просмотр истории работы ВСЕХ пользователей с возможностью фильтрации по конкретным пользователям информационной базой. Доступно только для клиент-серверного режима работы, т.к. требует настройки соединения с базой данных (SQL Server / PostgreSQL).
* Реализована эффективная фильтрация по пользователям информационной базы.
* Переход по навигационным ссылкам из отчета и ссылкам на объекты информационной базы.
* Гибкие отборы по ссылке на объект, дате действия, пользователя, содержанию строки навигационной ссылки и др.
* Гибкие настройки подключения к базе данных. Может быть полезным, если нужна доменная аутентификация с клиентской машины и при этом со стороны сервера 1С доступа к СУБД нет. Или если нужно задействовать отчет в окружении Linux, где ADO недоступен, но можно подключиться к базе PostgreSQL с клиентской машины Windows.

## Требования

Требования для работы отчета:

* Платформа 1С версии 8.3.5 и выше.
* Режим работы не имеет значения (клиент-серверный или файловая база. SQL Server / PostgreSQL). Полные возможности отчета доступны только в клиент-серверном режиме работы.
* Только управляемые формы.

## Принцип работы

Работа отчета простая:

1. Получаем историю работы пользователей:
    * Для файловой базы история работы формируется средствами платформы 1С, поэтому для чтения доступна только история текущего пользователя.
    * Для клиент-серверного режима, если настроено соединение с базой данных (SQL Server / PostgreSQL) получение данных выполняется напрямую из таблицы "_UsersWorkHistory". Это позволяет смотреть историю работы всех пользователей информационной базы.
2. Данные подготавливаем для отчета, определяя ссылку на объекты базы данных и сопоставляя события с пользователями информационной базы.

Также отчет может дать пример переопределения поведения стандартных полей отчета СКД в части событий элементов (начало выбора, обработка выбора и др.).