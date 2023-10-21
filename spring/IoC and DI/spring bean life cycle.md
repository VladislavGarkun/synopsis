Жизненный цикла Spring bean'а включает в себя стадии создания и уничтожения объектов.
Создание Spring Bean'а:
1) Если объект содержит поля, то вначале происходит их инициализация
2) Статический блок инициализации, он применяется для выполнения кода, который должен выполниться 1 раз при иницализации класса загрузчиком классов.
3) Нестатический блок(-и) инициализации. Будут выполняться при каждом создании объекта, при наличии нескольких будут вызываться в порядке объявления. Блок способен генерировать исключения, если они объявлены в throws всех конструкторов.
4) Java Constructor
5) Метод setBeanName(String beanName), при реализации интерфейса BeanNameAware. В методе можно получить доступ к имени bean'а, которое задается:
	- @Bean(name = "beanName")
	- @Component(value = "beanName") и производных аннотациях, по умолчанию использует имя класса в camelCase.
	- При использовании xml-конфигурации параметр "id" в теге "bean"
6) Метод setClassLoader(ClassLoader classLoader), при реализации интерфейса BeanClassLoaderAware. Он позволяет получить доступ к ClassLoader'у, используемому BeanFactory для загрузки bean'ов.
7) Метод setApplicationContext(ApplicationContext applicationContext), при реализации интерфейса ApplicationContextAware. Он позволяет получить доступ к контексту.
8) Метод postProcessBeforeInitialization(Object bean, String beanName). Для использования необходимо создать кастомный BeanPostProcessor и переопределить его. Кастомный BeanPostProcessor будет работать для каждого создаваемого bean'а.
9) Метод с аннотацией @PostConstruct. init method используемый при работе с аннотациями.
10) Метод afterPropertiesSet() при реализации интерфейса InitializingBean. Метод использовался в Spring 2, до появления аннотаций.
11) Еще один вариант задания init метода это задание его в аннотации @Bean(initMethod = "initMethod") или в теге "bean" при использовании xml конфигурации.
12) Метод postProcessAfterInitialization(Object bean, String beanName). Для использования необходимо создать кастомный BeanPostProcessor и переопределить его. Кастомный BeanPostProcessor будет работать для каждого создаваемого bean'а.

Уничтожение Spring bean'а:
1) Метод с аннотацией @PreDestroy. destroy method используемый при работе с аннотациями.
2) Destroy method, задаваемый в аннотации @Bean(destroyMethod = "destroyMethod").
3) Метод destroy(), при реализации интерфейса DisposableBean. 
4) Затем по такой же схеме происходит уничтожение полей.