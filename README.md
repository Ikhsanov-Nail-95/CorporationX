# Моя работа
## Achievement Service - работа с достижениями
[Общий интерфейс](https://github.com/Ikhsanov-Nail-95/achievement_service/blob/main/src/main/java/faang/school/achievement/handler/EventHandler.java), [абстрактный класс](https://github.com/Ikhsanov-Nail-95/achievement_service/blob/main/src/main/java/faang/school/achievement/handler/AbstractEventHandler.java) для достижений определённого типа и [обработчик достижения](https://github.com/Ikhsanov-Nail-95/achievement_service/blob/main/src/main/java/faang/school/achievement/handler/AllLoveAchievementHandler.java) работают в совокупности и предполагают просто добавление новых достижений и обновление функционала
## Analytics Service

[Сервис](https://github.com/Ikhsanov-Nail-95/analytics_service/blob/main/src/main/java/faang/school/analytics/service/AnalyticsEventService.java) выполняет работу по сохранению аналитики в общем виде.

[Aбстрактный класс](https://github.com/Ikhsanov-Nail-95/analytics_service/blob/main/src/main/java/faang/school/analytics/listener/AbstractListener.java) для достижений определённого типа и [cлушатель](https://github.com/Ikhsanov-Nail-95/analytics_service/blob/main/src/main/java/faang/school/analytics/listener/FollowerEventListener.java) ивентов ловит событие и сохраняет сущность в БД.
