Приоритет поиска зависимости:
- by Name
- by Type
- by Qualifier

Field Injection

1) Match by Name
	![[@Resource field injection by Name.png]]
	При внедрении зависимости по имени параметр "name" должен совпадать с именем bean'а, в противном случае будет NoSuchBeanDefinitionException.
	![[@Resourse bean determination for name.png]]

2) Match by Type
	Для внедрения по типу достаточно удалить аттрибут "name" из @Resourse.

3) Match by Qualifier
	При использовании неских bean'ов одного типа может возникнуть проблема с выбором подходящего для внедрения и будет выброшен NoUniqueBeanDefinitionException.
	![[@Resourse bean determination for qualifier.png]]
	Решить это поможет добавление аннотации @Qualifier. Она используется для определения необходимого bean'а среди bean'ов одного типа. Также эту ситуацию можно было решить параметром "name" в аннотации @Resourse.
	![[@Resourse field injection by qualifier.png]]

Setter Injection

1) Match by Name
	При внедрении по имени необходимо также добавить аттрибут "name" в @Resourse.
	![[@Resourse setter injection by Name.png]]

2) Match by Type
	Для внедрения по типу нужно аналогично убрать аттрибут "name" из аннотации.

3) Match by Qualifier
	Аналогично внедрению по полю можно добавить аннотацию @Qualifier для избегания NonUniqueBeanDefinitionException при наличии нескольких bean'ов одного типа.

Constructor Injection
 @Resourse не поддерживает внедрение с помощью конструктора