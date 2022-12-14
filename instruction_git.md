# **Инструкция по использованию системы контроля версий Git** #

## Что такое Git?

![Эмблема Гит](git.jpg) 

Программа Git (произносится "гит") - это распределенная система управления версиями. Проект был создан Линусом Торвальдсом для управления разработкой ядра Linux, первая версия выпущена 7 апреля 2005 года. На сегодняшний день его поддерживает Джунио Хамано.

## Инициализация репозитория

Чтобы инициализировать (создать) новый репозиторий нужно ввести команду:

    git init 

## Проверка состояния репозитория

Чтобы проверить состояние репозитория нужно ввести команду:

    git status

 ## Добавление изменений в индекс

   Чтобы добавить изменения в индекс для следующего коммита, нужно ввести команду:

    git add <filename> 

Где вместо < filename > пишется полное имя файла, в котором были произведены изменения.

## Фиксация изменений

Чтобы зафиксировать изменения (добавленные ранее к отслеживанию) необходимо использовать команду:

    git commit

В этом случае откроется окно для ввода краткого сообщения о создаваемом коммите.

Чтобы ввести краткое сообщение в процессе создания коммите необходимо использовать эту же команду с дополнительной опцией:

    git commit -m "message"

## Автоматическая индексация каждого отслеживаемого файла

    git commit -a

## Автоматическая индексация каждого отслеживаемого файла в коммите и добавление комментария к коммиту

    git commit -am "message"

## Просмотр истории коммитов

Чтобы посмотреть историю изменений (коммитов) используется команда:

    git log

Для отображения лога в кратком виде (один коммит - одна строка) используется та же команда с опцией:

    git log --oneline

Для отображения всех коммитов (вне зависимости от того, на какой из них мы сейчас переключены) используется команда:

    git log --all

Данные опции можно комбинировать:

    git log --oneline --all

## Просмотр различий между коммитами

Для просмотра различий между разными версиями репозитория, используется команда:

    git diff <hash1> <hash2>

При этом если ввести команду

    git diff

без параметро, то будет показана разницп между текущим состоянием репозитория и последним закоммиченным.

## Для переключения между коммитами

Чтобы переключиться на другую (ранее сохраненную) версию репозитория, используется команда:

    git checkout /<hash>

где hash - это идентификатор коммита, показываемый в логе.

## Ветвление

Ветки в гит нужны для того, чтобы программисты могли вести совместную работу над проектом и не мешать друг другу при этом.


### Создание новой ветки

Чтобы создать новую ветку нужно выполнить команду:

    git branch <new_branch_name>

### Переход между ветками

Чтобы перейти на другую ветку нужно выполнить команду:

    git checkout <new_branch_name>

### Слияние

Чтобы влить изменения из одной ветки в другую нужно выполнить команду, находясь в ветке master:

    git merge <new_branch_name>

#### Конфликты слияние

Если при слиянии в двух версиях файла одна и та же строка напечатана по разному, то может произойти конфликт слияния. Тогда получается, что Git не может сам решить какое из изменений нужно применить и он предлагает вручную решить эту ситуацию: оставить первоначальный вариант, выбрать вариант из ветки, которую сливаем, совместить изменения или сравнить версии.

## Удаленные репозитории

Удаленные репозитории - это очень полезная штука!!!
