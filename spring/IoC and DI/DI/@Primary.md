Данная аннотация применяется для обозначения приоритетности bean'а при внедрении (использовании его по умолчанию).
![[@Primary example.png]]
В приведенном случае bean "tonyEmployee" будет внедряться по умолчанию. Аннотацию также можно ставить и на класс при использовании @Component.
При необходимости заинжектить "johnEmployee" необходимо добавить @Qualifier("johnEmployee") или использовать @Resourse(name = "johnEmployee").