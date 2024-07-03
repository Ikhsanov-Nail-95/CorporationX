# Моя работа
## Achievement Service - работа с достижениями
[Общий интерфейс](https://github.com/Ikhsanov-Nail-95/achievement_service/blob/main/src/main/java/faang/school/achievement/handler/EventHandler.java), [абстрактный класс](https://github.com/Ikhsanov-Nail-95/achievement_service/blob/main/src/main/java/faang/school/achievement/handler/AbstractEventHandler.java) для достижений определённого типа и [обработчик достижения](https://github.com/Ikhsanov-Nail-95/achievement_service/blob/main/src/main/java/faang/school/achievement/handler/AllLoveAchievementHandler.java) работают в совокупности и предполагают просто добавление новых достижений и обновление функционала

## Analytics Service - сбор аналитики о работе сервисов и фичей 
[Сервис](https://github.com/Ikhsanov-Nail-95/analytics_service/blob/main/src/main/java/faang/school/analytics/service/AnalyticsEventService.java) выполняет работу по сохранению аналитики в общем виде.

[Абстрактный класс](https://github.com/Ikhsanov-Nail-95/analytics_service/blob/main/src/main/java/faang/school/analytics/listener/AbstractListener.java) для событий определённого типа и [слушатель](https://github.com/Ikhsanov-Nail-95/analytics_service/blob/main/src/main/java/faang/school/analytics/listener/FollowerEventListener.java) ивентов ловит событие и сохраняет сущность в БД.

## Notification Service - обработка и отправление нотификаций
[Общий интерфейс](https://github.com/Ikhsanov-Nail-95/notification_service/blob/main/src/main/java/faang/school/notificationservice/messages/MessageBuilder.java) для реализации определённого типа [Message Builder](https://github.com/Ikhsanov-Nail-95/notification_service/blob/main/src/main/java/faang/school/notificationservice/messages/LikeEventMessageBuilder.java) для построения корректного сообщения (в моём случае под мой тип нотификации), после чего выбирает предпочитаемый вид контакта пользователя и отправляет этим способом нотификацию.

[Общий интерфейс](https://github.com/Ikhsanov-Nail-95/notification_service/blob/main/src/main/java/faang/school/notificationservice/service/NotificationService.java) предоставляет основные методы для отправки нотификаций пользователю. Под каждый конкретный способ отправки (SMS, Email, Telegram...) создается реализация этого интерфейса.
В моем случае я реализовал [TelegramService](https://github.com/Ikhsanov-Nail-95/notification_service/blob/main/src/main/java/faang/school/notificationservice/service/telegram/TelegramService.java), который отвечает за отправку нотификаций пользователю в его Телеграм через нашего собственного Telegram-бота.

[Абстрактный класс](https://github.com/Ikhsanov-Nail-95/notification_service/blob/main/src/main/java/faang/school/notificationservice/service/telegram/command/Command.java) для реализации различных команд необходимых при взаимодействия с пользователем, например команда [StartCommand](https://github.com/Ikhsanov-Nail-95/notification_service/blob/main/src/main/java/faang/school/notificationservice/service/telegram/command/StartCommand.java).

Класс [CommandExecutor](https://github.com/Ikhsanov-Nail-95/notification_service/blob/main/src/main/java/faang/school/notificationservice/service/telegram/command/CommandExecutor.java) служит для выполнения команд (например, "/start", "/help"), которые могут взаимодействовать с пользователем через чат. Команды хранятся в словаре `commands`, где ключом является строка, обозначающая команду, а значением - объект класса `Command`. В методе `execute()` происходит поиск команды по переданному ключу, и если команда найдена, то вызывается метод `sendMessage()` объекта команды, который возвращает объект `SendMessage`. Если команда не найдена, то вызывается команда с ключом `/unknown`.
Таким образом, класс `CommandExecutor` обеспечивает гибкое и расширяемое выполнение команд, передаваемых в виде строк, и позволяет легко добавлять новые команды или изменять существующие.

## Post Service - публикация постов с возможностью писать под ними комментарии и ставить лайки
[Контроллер](https://github.com/Ikhsanov-Nail-95/post_service/blob/main/src/main/java/faang/school/postservice/controller/PostController.java) - документировал API с помощью библиотеки Swagger/OpenAPI. Каждая операция (создание поста, публикация поста и обновление поста) документирована с указанием её назначения, возможных ответов и валидации параметров. 

[Сервис](https://github.com/Ikhsanov-Nail-95/post_service/blob/main/src/main/java/faang/school/postservice/service/PostService.java) - выполняет все действия описанные в контроллере. Чистый и понятный код с соблюдением принципов SOLID и других передовых практик.

## Остальные сервисы
В них сделана не настолько уникальная работа, так что решаю не тратить ваше время на CRUD операции, хоть и с добавлением некоторой логики.
