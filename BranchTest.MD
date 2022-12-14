
# Инструкция по Markdown и GIT

## MarkDown
Это язык разметки (форматирования) для веб.   
* Чтобы две последовательные строки не склеивались в одну стороку при отображении, нужно дважды нажать перевод строки в конце предыдущей строки.   
Но так будет выглядеть не очень красиво в текстовом редакторе.  
Поэтому проще и более читабельно ставить два пробела в конце каждой строки, как у меня здесь.  
Когда мы используем, например, список, не нужно ставить дополнительные разделители строк, так как каждый элемент списка и так начинается с новой строки.
* Список выделяется звёздочков в начале строки, тогда в отображении каждый пункт будет отмечен точкой
> Можно использовать цитаты. Цитаты в отображении будут выделены специальным разделителем, а на языке markdown нужно поставить символ >  
* Заголовки выделяются решеткой. Чем больше решеток подряд Вы поставите, тем мельче будет заголовок. Смотри выше. Первый заголовок - одна решетка, второй заголовок - две. После решетки обязательно поставить пробел, иначе ничего не получится.
* В квадратных скобках напишите имя ссылки, а дальше в круглых укажите путь к ней. Будет выглядеть так: [Здесь нужная ссылка](https://learn.microsoft.com/ru-ru/contribute/markdown-reference)
* Сложнее всего вставить картинку, это делается вот так: ![Это образец картинки (Тест команды log)](TestLog.jpg)
* *Можно что-то выделить курсивом*, для этого текст нужно заключить в звёздочки.  
* Можно так же отделить блок один от другого. Тогда надо поставить три звездочки, как ниже.
***
## GIT
Git - это программа, которая позволит Вам отслеживать версии ваших файлов.
* Чтобы начать пользоваться Git, установите его отсюда: [Установить](https://git-scm.com/downloads)
А дальше в командной строке введите нужную команду (предварительно не забудьте перейти в нужный каталог)
* Git –version – получить версию программы
* Git –init  - инициализировать работу контролера версий (создать репозиторий)
* Git status – проверить статус версий
* Git add <название файла> -  добавить объект, который версионируем
* Git commit -m “добавили комментарий о добавлении комментария”
* Git log  - отобразит список версий
* Git checkout <номер версии (или первые четыре символа)>  - переход к версии
* Git checkout master – возврат к актуальной версии
* Git diff – показывает изменения
* git branch -d <имя версии> - удаляет версию
* Git config --global user.name "My Name" - ввести своё имя, настроить Git
* git config --global user.email myEmail@example.com - добавим e-mail в настройки
* Создадим новую ветку  
git branch test_branch


**Второй урок мы тестируем ветвление**
* Сначала настроим git:  
git config --global user.name "My Name"
git config --global user.email myEmail@example.com
* Чтобы посмотреть установились ли нужные настройки наберём:  
git config --list
* Инициируем новый репозиторий  
git init  
* Добавляем файл в логирование  
git add BranchTest.MD
* Теперь всё сохраним  
git commit -m "Первая версия"
* Теперь что-то исправим в файле и попробуем сохранить
У меня ничего не получилось. Git пишет, что нет изменений подготовленных к фиксации. Вот поэтому мы не используем его в своей работе
В общем пришлось снова сделать add, потом снова выполнить commit и только после этого получилось сохранить версию. 
* Теперь пора сделать ветвление. Создадим новую ветку
git branch test_branch
* И сделаем новую ветку текущей  
git checkout test_branch
* После этого мне снова приходится добавлять файл, иначе мой git ничего не видит. Ну ОК, добавим
git add BranchTest.MD
* И сделаем commit
git commit -m "Изменения в новой ветке"
* А теперь перейдем к основной ветке  
git checkout master  
Теперь если мы делаем 
git log
то не видем ничего, что делалось в новой ветке
Здесь становится страшно, потому что все исправления вдруг исчезают. Поэтому вернемся к новой ветки и всё скопируем.
git checkout test_branch
* Создаем ещё одну ветку
git branch test_branch_any
* После этого мне снова приходится добавлять файл, иначе мой git ничего не видит. 
git add BranchTest.MD
* И сделаем commit
git commit -m "Расширили список команд в первоначальной инструкции"
* Вернёмся в первое ветвление и дополним инструкцию 
git branch test_branch
* Объединение версий
git merdge test_branch
* Удалим ненужную версию
git branch -d test_branch
* Добавим картинки: 
![Это картинка команд](Screenshot_1.jpg)
Добавим ещё немного текста

* В итоге мы пробуем создать и разрешить конфликт. 
![В конце картинка конфликта. Я выбрала оба](%D0%A2%D0%B5%D1%81%D1%82%20%D0%BA%D0%BE%D0%BD%D1%84%D0%BB%D0%B8%D0%BA%D1%82%D0%B0.jpg)
