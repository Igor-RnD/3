# Концепция безопасности системы "Робот-фармацевт"

## 1. Активы и риски
| Актив                | Угроза                                    | Уязвимость               | Последствие                 |
|----------------------|-------------------------------------------|--------------------------|-----------------------------|
| Рецептура            | Утечка данных                             | Слабый шифрование        | Утрата конкурентного преимущества |
| Персональные данные   | Несанкционированный доступ               | Отсутствие 2FA           | Штрафы, репутационные потери |
| Робот-фармацевт       | Физическая поломка                       | Нет резервного оборудования | Простой производства        |
| Процесс производства | Нарушение алгоритма смешивания           | Ошибка в ПО               | Причинение вреда здоровью   |

## 2. Цели безопасности
- **Конфиденциальность**: 
  - Шифрование рецептур на уровне базы данных (AES-256)
  - RBAC для доступа к системе
- **Целостность**: 
  - Цифровая подпись рецептов (ECDSA)
  - Контрольные суммы этапов производства
- **Доступность**: 
  - Резервирование оборудования
  - Мониторинг в режиме 24/7

## 3. Предположения безопасности
1. Физический доступ к роботу имеют только авторизованные сотрудники
2. Все обновления ПО проверяются на цифровую подпись
3. Резервные копии данных создаются ежечасно

## 4. Сценарий функционирования
![Сценарий функционирования](diagrams/Сценарий функционированния.png)
