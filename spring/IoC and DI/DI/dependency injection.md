Для внедрения зависимостей используются несколько аннотаций с разными принципами работы:
- [[@Resourse]] (Java annotation)
- [[@Inject]] (Java annotation)
- [[@Autowired]] (Spring annotation)

При использовании этих аннотаций нет необходимости самому напрямую создавать объекты.

Внедрение с помощью конструктора является более приоритетным:
- удобное тестировани, так как в противном случае для инициализации полей придется использовать рефлексию.
- null safety
- вписывается в парадигму ООП

Решить проблему неоднозначности зависимостей может помочь аннотация [[@Primary]].

Для упорядочивания bean'ов применяется [[@Order]].
