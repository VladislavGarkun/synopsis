Аннотация @Autowired предоставляет такой же функционал как и @Inject с той лишь разницей, что является аннотацией Spring'а.

Приоритет поиска зависимости:
- by Type
- by Qualifier
- by Name

Field Injection

1) Match by Type
	![[@Autowired field injection by Type.png]]

2) Match by Qualifier
	![[@Autowired field injection by Qualifier.png]]
	@Qualifier помогает избегать NoUniqueBeanDefinitionException при наличии нескольких bean'ов с типом FieldDependency.

3) Match by Name
	Для внедрения по имени необходимо использовать имя bean'а в качестве названия поля, что также позволит избежать NoUniqueBeanDefinitionException.

Setter Injection

Применение внедрения с помощью setter'а аналогично с аннотацией @Resourse, но с приоритетом поиска для @Inject.

Если при внедрении зависимости нет необходимого bean'а, то будет выбрашено NoSuchBeanDefinitionException. Решить это проблему можно добавлением параметра "required" в аннотацию @Autowired(required = false)