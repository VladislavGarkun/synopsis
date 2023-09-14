BeanFactory - корневой интерфейс для доступа к Spring контейнеру. Он предоставляет базовую функциональность для управления bean'ами.
ApplicationContext - наследник BeanFactory, который расширяет ее функциональность.
Важным отличием между ними является то, что BeanFactory загружает все bean'ы только при необходимости (lazy loading), ApplicationContext загружает все singleton bean'ы при запуске контекста.
Bean - это объект, который создается, собирается и управляется Spring контейнером/контекстом.

Типы контекстов:
- AnnotationConfigApplicationContext
	Содержит классы аннотированные @Configuration, @Component and etc.
- AnnotationConfigWebApplicationContext
	Можно использовать этот контекст при конфигурации Spring listener или Spring MVC
- XmlWebApplicationContext
	Используется при Xml конфигурации
- FileSystemXmlApplicationContext
	Используется для конфигурации с помощью файла из системы или по url
- ClassPathXmlApplicationContext
	Используется при загрузке Xml конфигурации из classpath'a

ApplicationContext поддерживает [[build-in events]]

Существуют несколько способов конфигурирования bean'ов [[bean configuration]]