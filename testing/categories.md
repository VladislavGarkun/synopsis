Для задания category нужно создать интерфейс который будет за нее отвечать и затем добавить аннотацию на метод/класс теста

Затем с помощью @IncludeCategory(Category.class) и @ExcludeCategory(Category.class) можно добавлять или исключать категорию в TestSuite.