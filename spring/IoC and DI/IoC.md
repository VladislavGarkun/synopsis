Inversion of Control (IoC) - принцип разработки ПО при котором управление объектами или частами приложения передается контейнеру/контексту ([[application context]]) или фреймворку.
Dependency Injection (DI) - паттерн который используется для реализации IoC.

Классический подход

![[classic approach.png]]

Минусы:
- Класс PersonService напрямую зависит от PersonDAO
- Невозможно тестировать PersonService отдельно от PersonDAO
- Жизненный цикл классов связан напрямую
- Невозможно изменить PersonDAO на другую реализацию

Service Locator

![[Service Locator.png]]

Плюсы:
- PersonService не зависит от PersonDAO
- Возможно тестировать PersonService отдельно от PersonDAO
- PersonDAO возможно заменить на другую реализацию
Минусы:
- PersonService зависит от ServiceLocator'a

IoC Container

![[IoC Container.png]]

Плюсы:
- Контейнер создает необходимые объекты и управляет жизненным циклом
- PersonService не зависит от PersonDAO
- PersonService легко тестировать отдельно от PersonDAO
- PersonDAO можно заменить на другую реализацию