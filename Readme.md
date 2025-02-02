# Инструкция по работе с Git и удалёнными репозиториями

## Что такое git?
**Git** - это наиболее популярная реализация распределённой системы контроля версий. Самая популярная реализация **Git** - это [GitHub](https://github.com/)

## Подготовка репозитория
Для создания репозитория используется команда *git init*. Для этого необходимо в терминале перейти в пустую папку, где в будущем будет репозиторий. Затем в терминале с папкой написать команду *git init*.

## Создание коммитов

### Добавление файла к коммиту
Для добавления файла к будущему коммиту используется команда *git add*. Для этого в терминале с папкой-репозиторием необходимо написать *git add <название файла>*.

### Создание коммита
Для создания коммита используется команда *git commit*. Для этого в терминале с папкой репозиторием необходимо написать *git commit -m <сообщение к коммиту>*. Сообщение к коммиту писать ***ОБЯЗАТЕЛЬНО!!!***.

## Журнал изменений
Для просмотра журнала изменений используется команда *git log*. Для этого в терминале с папкой-репозиторием необходимо написать *git log*.

## Перемещение между коммитами
Для перемещения на предидущие коммиты используется команда *git checkout*. Для этого необходимо в журнале изменений, как показано в предыдущей части, найти необходимый коммит и его номер. После чего в терминале с папкой-репозиторием написать команду *git checkout <номер коммита>*. После применения этой команды Вы попадёте в состояние **Detached head**, в котором никакие изменения фиксироваться не будут. Для возврата в обычное состояние необходимо написать команду *git checkout master*.

## Ветки в Git
### Создание веток в Git
Для создания новой ветки используется команда *git branch*. Для этого в терминале с папкой-репозиторием необходимо написать *git branch <название ветки>*

### Просмотр списка веток
Для просмотра списка веток используется комнада *git branch*. Для этого в терминале с папкой-репозиторием необходимо написать команду *git branch*. Зелёным цветом с символом **звёздочка** будет выделена текущая ветка

### Переключение между ветками
Для перехода на другую ветку используется команда *git checkout*. Для этого в терминале с папкой-репозиторием пишем команду *git checkout <название ветки*. Для перехода на ветку ветка должна быть ***создана***!!!

## Слияние веток и разрешение конфликтов

### Слияние веток 
Основная цель создание дополнительных веток – проработать отдельный элемент проекта автономно, а затем присоединить еe к проекту. В большинстве случаев ветки, в конечном итоге, объединяются с веткой master. 
Для слияния текущей ветки с какой-либо другой используется команда *git merge <название ветки>*. Обратите внимание: Ветка сольется в ветку, где вы находитесь. *ВАЖНО* перед объединением веток перейти в нужную ветку.

### Разрешение конфликтов
При слиянии может возникнуть ситуация, когда фрагмент в каком-либо файле проекта в различных ветках отредактирован по-разному. Такая ситуация называется конфликт. В случае возникновения конфликтов git заносит в создаваемый при объединении  файл, содержащий текст обоих версий. Начало конфликтного фрагмента помечается строкой, начинающиеся с символов <<<<<<< и содержащей имя первой ветки, а заканчивается строкой, начинающиеся с символов >>>>>>> и содержащей имя вливаемой ветки. Версии из каждой ветки разделяются строкой с символами =======. 
При возникновении конфликта пользователю рекомендуется в ручном режиме его устранить: 
1. удалить неактуальную информацию;
2. оставить актуальную информацию.

### Удаление веток
Для удаления ветки используется команда *git -d branch*. Для этого в терминале с папкой-репозиторием необходимо написать *git branch -d <название ветки>* Для удаления ветки ветка должна быть ***создана***!!!

## Работа с удаленными репозиториями
Современные проекты во многих случаях выполняются командой разработчиков. Для поддерживание согласованного состояния репозиториев команды обычно используется сервер, который хранить центральный репозиторий. Создание репозитория на серверах, таких как [GitHub](https://github.com/), производится в web-интерфейсе. Такой интерфейс содержит в себе инструкцию, достаточную для того, чтобы работать с репозиторием.

### Перенос репозитория в локальную папку
Для создания копии репозитория на компьютере пользователя используется команда: *git clone Путь на репозиторий*. Дальше можно работать в локальном режиме.

### Актуализация локального репозитория из удаленного 
Перед тем, как создавать новый функционал и новую ветку, стоит обновить master на вашем устройстве. Для этого нужно находиться в этой ветке и выполнить следующую команду: 
1. Переключаемся в master *git checkout master*
2. Подтягиваем изменения из репозитория GitHub *git pull origin master*

### Актуализация удаленного репозитория из локального
После внесения изменений в локальном репозитории необходимо передать их в удаленный репозиторий. Для этого в терминале с папкой-репозиторием необходимо написать *git push <origin> <master>* 

### Работа с удаленным репозиторием без доступа на изменение к удаленному репозиторию через *GitHub*

#### Создание копии репозитория с полными правами
Для совместной работы со сторонним удаленным репозиторием необходимо перенести его в репозиторий на своем аккаунте (с полным доступом) через web-интерфейс при помощи кнопки *Fork*. Это будет полная копия удаленного репозитория и включает ссылку на удаленный репозиторий родителя.

#### Отправка запроса на внесение изменений в исходный репозиторий 
Чтобы предложить внести сделанные вами изменения владельцу удаленного репозитория необходимо через web-интерфейс необходимо создать *Pull request*. Для этого:
1. Нажимаем кнопку  *Pull request*;
2. Нажимаем кнопку  *New Pull request*;
3. Далее выбираем в какой репозиторий предлагаем внести изменения;
4. Далее выбираем в какую ветку предлагаем внести изменения;
5. Далее выбираем из какого репозитория хотим передать изменения;
6. Далее выбираем из какой ветки хотим передать изменения;
7. Обязательно пишем сопроводительный комментарий для владельца удаленного репозитория;
8. Нажимаем *Create Pull request*.