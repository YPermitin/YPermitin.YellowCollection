# Обозреватель криптографии

Отчет для просмотра доступных провайдеров и сертификатов криптографии на сервере и клиенте.

Материалы по другим темам Вы можете найти на сайте [ypermitin.github.io](https://ypermitin.github.io/), а новости по проектам или новым материалам в [Telegram-канале](https://t.me/TinyDevVault).

## Состав

* [media](media) - медиафайлы для документации данной разработки.
* [src](src) - файлы исходного кода.

## Назначение и возможности

Платформа 1С имеет ряд возможностей для работы с криптографией, которые базируются на асимметричном шифровании (то есть на использовании пары ключей – открытого и закрытого). С помощью этих механизмов становится возможно использовать шифрование данных, создание электронной подписи и др.

Хоть сама платформа 1С и не имеет встроенных алгоритмов криптографии, но с помощью сторонних провайдеров позволяет решить большинство связанных с ними задач.

Отчет был создан для упрощенного доступа к списку доступных к использованию провайдеров криптографии и их настроек, а также просмотра и контроля установленных сертификатов криптографии (срок действия, проверка установки, получение отпечатков и серийных номеров и др.).

![1. Основная форма отчета](./media/1.%20%D0%9E%D1%81%D0%BD%D0%BE%D0%B2%D0%BD%D0%B0%D1%8F%20%D1%84%D0%BE%D1%80%D0%BC%D0%B0%20%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0.png)

Отчет не сделает за Вас настройки программ криптографии, сертификатов и других параметров. Он лишь инструмент для проверки результатов настройки или получения доп. информации о провайдерах и сертификатов криптографии, доступных для платформы 1С на стороне сервера приложений или клиентской части.

Основные возможности отчета:

* Просмотр установленных провайдеров криптографии на клиенте и сервере.
* Просмотр установленных сертификатов криптографии на клиенте и сервере.
* Контроль срока действия сертификатов.
* Получение дополнительной информации о сертификатах, такой как серийный номер, отпечаток и произвольные атрибуты.
* Поддержка подсистемы "Варианты отчетов" из БСП.
* Далее Вы найдете основные варианты отчета и их описание.

## Требования

Обработка тестировалась на платформе 8.3.12 и выше.

## Варианты отчета

Отчет имеет в своем составе несколько предопределенных вариантов отчета с разной детализацией.

### Доступные провайдеры криптографии

Как было сказано выше, платформа 1С не имеет собственной реализации алгоритмов криптографии. Чаще всего используются продукты [КриптоПро](https://www.cryptopro.ru/) и [ViPNet](https://infotecs.ru/product/).

С помощью этого варианта отчета можно посмотреть список доступных провайдеров на сервере / клиенте, их тип, а также основные алгоритмы подписи, хеширования и шифрования.

![2. Доступные провайдеры криптографии](./media/2.%20%D0%94%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B%D0%B5%20%D0%BF%D1%80%D0%BE%D0%B2%D0%B0%D0%B9%D0%B4%D0%B5%D1%80%D1%8B%20%D0%BA%D1%80%D0%B8%D0%BF%D1%82%D0%BE%D0%B3%D1%80%D0%B0%D1%84%D0%B8%D0%B8.png)

Обратите внимание на первую строку отчета. При настройке этого провайдера в 1С:Библиотека электронных документов (или в конфигурациях, где она встроена) задаются такие же настройки, как и в отчете.

![3. Доступные провайдеры криптографии (настройки)](./media/3.%20%D0%94%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B%D0%B5%20%D0%BF%D1%80%D0%BE%D0%B2%D0%B0%D0%B9%D0%B4%D0%B5%D1%80%D1%8B%20%D0%BA%D1%80%D0%B8%D0%BF%D1%82%D0%BE%D0%B3%D1%80%D0%B0%D1%84%D0%B8%D0%B8%20(%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8).png)

Таким образом, с помощью отчета можно узнать какие провайдеры установлены, с какими настройками их использовать, а после перенести эти настройки при необходимости в приложение.

### Сертификаты криптографии

Для получения списка сертификатов и их параметров используется вариант "Сертификаты криптографии". С его помощью можно получить список сертификатов, сроки их действия, назначение, а также параметры издателя и субъекта.

![4. Сертификаты криптографии](./media/4.%20%D0%A1%D0%B5%D1%80%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D1%8B%20%D0%BA%D1%80%D0%B8%D0%BF%D1%82%D0%BE%D0%B3%D1%80%D0%B0%D1%84%D0%B8%D0%B8.png)

В 1С:Библиотека электронных документов также возможно посмотреть параметры сертификата, который был добавлен и настроен. Параметры схожи.

![5. Сертификаты криптографии (параметры)](./media/5.%20%D0%A1%D0%B5%D1%80%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D1%8B%20%D0%BA%D1%80%D0%B8%D0%BF%D1%82%D0%BE%D0%B3%D1%80%D0%B0%D1%84%D0%B8%D0%B8%20(%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B).png)

Поможет с проверкой какие сертификаты установлены и какие из них платформа 1С может использовать.

### Сертификаты криптографии (расширенный)

Вариант дополняет данными предыдущую версию. Можно увидеть отпечаток, серийный номер и открытый ключ сертификата в виде Base64 или двоичных данных.

![6. Сертификаты криптографии (расширенный)](./media/6.%20%D0%A1%D0%B5%D1%80%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D1%8B%20%D0%BA%D1%80%D0%B8%D0%BF%D1%82%D0%BE%D0%B3%D1%80%D0%B0%D1%84%D0%B8%D0%B8%20(%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D1%8B%D0%B9).png)

Эта информация может пригодиться при разработке или настройке использования сертификатов. Хардкодом эти параметры можно использовать так.

```
// Настройки менеджера криптографии по данным отчета
МенеджерКриптографии = Новый МенеджерКриптографии("Crypto-Pro GOST R 34.10-2001 Cryptographic Service Provider","",75);
МенеджерКриптографии.АлгоритмПодписи = "GOST R 34.10-2001";
МенеджерКриптографии.АлгоритмХеширования = "GOST R 34.11-94";
МенеджерКриптографии.АлгоритмШифрования = "GOST 28147-89";
МенеджерКриптографии.ВключениеСертификатовВПодпись = РежимВключенияСертификатовКриптографии.ВключатьСертификатСубъекта;	
ХранилищеСертификатов = МенеджерКриптографии.ПолучитьХранилищеСертификатов();

// Поиск по значению отпечатка из отчета. 
// Также доступен поиск по серийному номеру и субъекту
СертификатПодписи = ХранилищеСертификатов.НайтиПоОтпечатку(Base64Значение("9a0LzBrVbNFQclschmwwrZLvIbA="));

ПодписанныеДанные = МенеджерКриптографии.Подписать(ПутьКФайлуДляПодписи, СертификатПодписи);
```

Но все же рекомендую все выносить в настройки.

### Сертификаты с истекающим сроком действия

Вариант дополняет данными предыдущую версию. Можно увидеть отпечаток, серийный номер и открытый ключ сертификата в виде Base64 или двоичных данных.

![7. Сертификаты с истекающим сроком действия](./media/7.%20%D0%A1%D0%B5%D1%80%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D1%8B%20%D1%81%20%D0%B8%D1%81%D1%82%D0%B5%D0%BA%D0%B0%D1%8E%D1%89%D0%B8%D0%BC%20%D1%81%D1%80%D0%BE%D0%BA%D0%BE%D0%BC%20%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F.png)

Можно добавить рассылку этого варианта раз в неделю с помощью подсистемы БСП "Рассылка отчетов", чтобы держать актуальные сертификаты на сервере.

## Без заключения

Криптография, криптография, криптография!

Следите за своей безопасностью. Недействительные сертификаты - это не про нас!