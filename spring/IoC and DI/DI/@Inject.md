Приоритет поиска зависимости:
- by Type
- by Qualifier
- by Name

Field Injection

1) Match by Type
	![[@Inject field injection by Type.png]]
	Так внедрение по типу является наиболее приоритетным и будет происходить, даже при разных именах поля класса и bean'а.

2) Match by Qualifier
	При наличии нескольких bean'ов одного типа необходимо использовать @Qualifier для предотвращения NoUniqueBeanDefinitionException.
	![[@Inject field injection by Qualifier.png]]

3) Match by Name
	Для внедрения по имени используется аннотация @Named, в которую необходимо передать имя bean'а.
	![[@Inject field injection match by Name.png]]
	При неправильно указанном имени будет выбрашено NoSuchBeanDefinitionException.

Setter Injection

Применение внедрения с помощью setter'а аналогично с аннотацией @Resourse, но с приоритетом поиска для @Inject.