@startuml
actor "Злоумышленник" as Hacker
participant "Внешний API" as API
participant "IDS" as IDS

Hacker -> API: Поддельный запрос с измененным ID рецепта
API -> IDS: Анализ аномального запроса
IDS --> API: Блокировка (признак SQL-инъекции)
API --> Hacker: Ошибка 403 Forbidden
IDS -> Admin: Отправка лога атаки
@enduml
