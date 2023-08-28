.gitignore файл применяется в тех случаях, когда необходимо настроить, какими файлами или частями проекта мы не хотим делиться (файлы логгирования, временные файлы, скрытые файлы и тд.)
Правила для файла .gitignire:
- пустые строки - игнорируются
- начинающиеся с # - комментарии (игнорируются)
- name - имена файлов, папок и папок и файлов в name папке (/name.log, /name/file.txt, /lib/name.log)
- name/ - окончание на '/' указывает, что паттерн действует на папку name (/name/file.txt, /name/log/name.log), не будет действовать на /name.log
- /name.file - все файлы с именем name (/name.file, /lib/name.file)
- lib/name.file - определяет файлы в определенной папке, всегда являющейся корневой, даже если не начинается с '/' (/lib/name.file), не будет действовать на name.file, /test/lib/name.file
- \*\*/lib/name.file определяет файлы внутри папки lib, которая не обязательно является корневой (/lib/name.file, /test/lib/name.file)
- \*\*name - все папки name и файлы и папки в папке name (/name/log.file, /lib/name/log.file, name/lib/log.file)
- /lib/\*\*/name - все папки name и все файлы и папк внутри них внутри папки lib (/lib/name/log.file, /lib/test/name/log.file, /lib/test/ver1/name/log.file), не будет действовать с /name/log.file
- \*.file - все файлы с расширением .file (/name.file, lib/name.file)
- \*name/ - все папки заканчивающиеся на name (/lastname/log.file, /firstname/log.file)
- name?.file - файл с именем начинающимся на name и последним любым символом (/names/file, name1.file), не будет действовать на /names1.file
- name\[a-z].file - файл с именем начинающимся на name и последний символ в диапазоне a-z (/namea.file, /nameb.file), не будет действовать на /name1.file
- name\[abc].file - файл с именем начинающимся на name и последний символ a, b или c (/namea.file, /nameb.file), не будет действовать на /names.file
- name\[!abc].file - файл с именем начинающимся на name и последний символ не a, b или c (/names.file, /namex.file), не будет действовать на /namea.file
- name/
  !name/secret.log - '!' определяет отрицание или исключение, все файлы и папки в любой папке name, кроме name/secret.log (/name/file.txt, /name/log/name.log)
- \*.file
  !filename.file - все файлы с расширением .file, кроме name.file (/log.file, /name.file)

Useful materials

https://www.w3schools.com/git/git_ignore.asp