Snapshots

Важным отличем Git от других СКВ является подход к работе с данными. Другие системы хранят информацию ввиде набора файлов и изменений, сделанных в каждом файле, по времени. Git же работает по другому принципу и сохраняет набор снимков файловой системы. То есть при каждом коммите система запоминает как выглядит каждый файл и сохраняет ссылку на этот снимок. Если файлы не изменены, то Git не запоминает эти файлы вновь, а лишь создает ссылку на предыдущую версию файла, который уже сохранен.

Local operations

Для большинства операций в Git достаточно локальных файлов и ресурсов. Примером служит история проекта, для ее отображения система считывает данные из локальной базы данных. Также в случае нахождения оффлайн можно без каких-либо проблем создавать коммиты в локальную копию, а при появлении соединения синхронизировать с сервером.

Integrity

В Git для всего вычисляется хеш-сумма и только потом происходит сохранение. В последствии обращение к сохраненным объектам происходит по этой хеш-сумме. Хеш сумма вычисляется с помощью алгоритма SHA-1

Three states

В Git есть 3 основных состояния, в которых могут находится файлы:
- modified
- staged
- commited
Это приводит к трем основным секциям проекта Git:
- working directory - снимок одной версии проекта, файлы извлекаются из базы данных в каталоге Git и помещаются на диск, чтобы их можно было использовать или редактировать.
- staging area - файл, который обычно находится в каталоге Git, в нем содержится информация, которая попадет в следующий коммит.
- git directory - место, где Git хранит метаданные и базу объектов проекта. Это именно та часть, которая копируется при клонировании проекта.
Процесс работы с Git:
- изменение файлов
- добавление в staging area файлов, которые должны попасть в следующий коммит.
- делается коммит, который использует файлы из staging area.
Так как работа в командах предполагает параллельное внесение изменений используются различные [[branching strategy]]

Git terminology

Branch (ветвь) - это именованный указатель на коммит. При создании нового коммита указатель перемещается на него. Создать ветвь можно на основе существующией. Ветка master является веткой по умолчанию и создается в локальном репозитории при клонировании.
Commit - фиксация изменений в Git репозитории.  
HEAD - символическая ссылка, указывающая на текущую ветку.
Index - синоним staged area.
Repository - хранилище, содержащее историю, различные версии, ветви и теги.
Tag - указатель на коммит, который уникально определяет версию Git репозитория. Ветви и теги являются указателями, но разница заключается в том, что ветвь перемещается при создании нового коммита, а тег всегда указывает на один и тот же коммит.
URL - определяет расположение репозитория. Есть fetchurl для получения новых данных из другого репозитория и pushurl для добавления данных в другой репозиторий.
Для работы с Git необходимо знать основные [[git operations]]
Для настройки файлов, которые будут попадать в коммиты и как следствие в удаленный репозиторий создается [[gitignore]]

Useful materials

https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F

