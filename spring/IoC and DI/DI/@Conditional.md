Conditional аннотации могут применяться на классы помеченные @Configuration, @Component, @Service, @Controller, @Repository, на методы с аннотацией @Bean и классы с аннотацией @Configuration и определять условия создания bean'а.

- @ConditionalOnProperty(prefix = "", name = "", havingValue = "", matchIfMissing = false) - bean будет создаваться если в property файле есть аттрибут, который определяется "prefix" и "name" и содержит значение из "havingValue". "matchIfMissing" определяет выполняется ли условия в случае отсутствия поля в property файле, по умолчанию - false.
- @ConditionalOnExpression(value = "SpEL expression") - bean будет создаваться в случае, если выражение возвращает "true".
- @ConditionalOnBean(value = Type.class) - создает bean при наличии в контексте экземпляра bean'а типа Type.
- @ConditionalOnMissingBean(value = "classpath") - создает bean если в classpath нет объекта указанного типа.
- @ConditionalOnClass(value = Type.class/name = "classpath") - создает bean если в classpath есть объект указанного типа.
- @ConditionalOnMissingClass(value = "classpath") - создает bean если в classpath нет объекта указанного типа.
- @ConditionalOnJava() - проверяет указаную версию Java и при совпадении с версией, на которой запускается приложение, создает bean.
- @ConditionalOnWarDeployment - создает bean в случае war packaging, но не будет работать с встроенным сервером, например Spring Boot Tomcat.

Для создания собственного condition'а нужно создать новый класс, реализовать интерфейс "Condition" и переопределить метод matches, результат выполнения которого определяет создание bean'а
![[@Conditional creating custom condition.png]]
Для применения нужно добавить класс в параметр аннотации
![[@Conditional custom condition usage.png]]

При комбинации condition'ов можно создавать or/and обединения. Для использования and достаточно просто добавить 2 аннотации на метод или класс. При создании or потребуется создать класс, наследующий "AnyNestedCondition", создать конструктор и добавить пустые статические классы с аннотацими @Conditional. Также существуют "AllNestedCondition" и "NoneNestedCondition".
![[Creating custom condition OR.png]]

Можно создать и свою аннотацию без параметров
![[@ConditionalOn annotation.png]]