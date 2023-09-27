Скоуп bean'а определяет его жизненный цикл и видимость. Установить скоуп можно с помощью аннотации @Scope, которую можно использовать как на классе так и на методе.
Типы скоупов:
- singleton
- prototype
- request
- session
- application
- websocket
Последние 4 типа только для веб-приложений.

Singleton

При создании bean'а с этим скоупом контейнер создает единственный экземпляр, при обращении к которому всегда будет возвращаться один и тот же объект и соответственно его изменения затронут все ссылки. Для использования скоупа применяются @Scope("singleton") или @Scope(ConfigurableBeanFactory.SCOPE_SINGLETON).

Prototype

При обращении к bean'у с таким скоупом каждый раз из контейнера будет возвращаться новый экземпляр. Для задания скоупа применяются @Scope("prototype") или @Scope(ConfigurableBeanFactory.SCOPE_PROTOTYPE).

Request

Создает экземпляр для каждого HTTP запроса. Определить скоуп можно с помощью @Scope(value = WebApplicationContext.SCOPE_REQUEST, proxyMode = ScopedProxyMode.TARGET_CLASS) или @RequestScope. Аттрибут proxyMode нужен так как во время создания web application context'а нет активных запросов.

Session 

Создает экземпляр для HTTP сессии. Определить скоуп можно с помощью @Scope(value = WebApplicationContext.SCOPE_SESSION, proxyMode = ScopedProxyMode.TARGET_CLASS) или @SessionScope.

Application

Cоздает экземпляр для жизненнго цикла ServletContext'а. Определить скоуп можно с помощью @Scope(value = WebApplicationContext.SCOPE_APPLICATION, proxyMode = ScopedProxyMode.TARGET_CLASS) или @ApplicationScope. Данный скоуп очень похож на singleton, но с одним очень важным отличием один и тот же bean може быть использован несколькими приложениями, использующими один ServletContext.

WebSocket

При первом обращении bean'ы с этим скоупом сохраняются в аттрибуты WebSocket сессии. Затем возвращается один и тот же экземпляр при каждом обращении к этому bean'у в течение сессии. Поведение также очень похоже на singleton, но ограничено WebSocket сессией. Определить скоуп можно с помощью @Scope(scopeName = "websocket", proxyMode = ScopedProxyMode.TARGET_CLASS).