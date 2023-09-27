XML Configuration

При использовании XML конфигурации мы можем объявлять bean'ы в одном файле или разбивать на разные для структуризации. При использовании нескольких файлов их можно импортировать.

Для загрузки bean'ов из файла и инициализации необходимо передать имя файла в конструкторе одно из типов контекста (ClassPathXmlApplicationContext, FileSystemXmlApplicationContext, XmlWebApplicationContext).

Annotation Configuration

Появилось в Spring 2.5 и для добавления класса в контекст на него необходимо добавить одну из аннотаций:
- @Component
	- @Controller
		- @RestController
	- @Service
	- @Repository
	- @ControllerAdvice
		- @RestControllerAdvice

	Для поиска bean'ов на конфигурационный класс (проаннотированный @Configuration, подразумевает что класс содержит конфигурацию Spring bean'ов), обычно это Main, нужно добавить аннотацию @ComponentScan(basePackages = "...").

Java Configuration

Данный подход появился в Spring 3.0 и подразумевает описание bean'ов в конфигурационном классе. Конфигурационный класс содержит методы, проаннотированные @Bean, подразумевается, что метод создает Spring bean.

![[Java Configuration example.png]]

Для внедрения зависимостей используются различные аннотации [[dependency injection]]

При конфигурировании bean'ов стоит принимать во внимание [[bean scopes]].