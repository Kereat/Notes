## Генерация ssh ключа
Для генерации ключа необходимо использовать утилиту ssh-keygen:<br>
<code>ssh-keygen -t rsa -b 4096</code><br>
В результате генерации ssh ключа будет создана папка .ssh, в котором будет находиться два ключа: приватный <code>id_rsa</code> и публичный <code>id_rsa.pub</code>. Публичный ключ необходимо скопировать и добавить в git (Settings -> SSH and GPG keys -> New SSH key).<br>
Дополнительная литература:
- <a href="https://www.ssh.com/ssh/keygen/">Инструкция по генерации ключей</a>
- <a href="https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-on-ubuntu-1604">Ещё одна инструкция по генерации ключей</a>
- <a href="https://hackernoon.com/asymmetric-encryption-explained-using-chocolate-boxes-5a329ea6813e">Асимметричное шифрование на шоколадках</a>
- <a href="https://www.coursera.org/learn/internet-history/lecture/lY9Uw/security-public-private-key-secure-sockets">Объяснение асимметричного шифрования</a>

## Настройка контактной информации
Перед первым коммитом необходимо добавить контактную информацию о себе, почту и имя, с помощью следующих команд:<br>
<code>git config --global user.email "your@mail"</code><br>
<code>git config --global user.name "Your Name"</code>

## Команды git
### Клонирование репозитория
Команда позволяет клонировать репозиторий, находящийся по ссылке my_link:<br>
<code>git clone my_link</code><br>
Например, для клонирования данного репозитория с помощью ssh (процесс генерирования ssh ключа описан выше) необходимо выполнить следующую команду:<br>
<code>git clone git@github.com:Kereat/Notes.git</code>

### Статус репозитория
Для просмотра статуса репозитория используется следующая команда:<br>
<code>git status</code><br>
Статус репозитория позволяет определить, какие файлы не добавлены для последующего коммита (выделены красным), а какие добавлены (выледелены зеленым).

### Добавление измененных файлов для коммита
Для добавления файла file_name для коммита, необходимо выполнить следующую команду:<br>
<code>git add file_name</code><br>
Чтобы добавить все файлы для коммита, необходимо указать точку вместо название файла:<br>
<code>git add .</code>

### Коммит файлов
Для коммита файлов (тех, которые добавлены для коммита и выделены зеленым при выполнении команды <code>git status</code>) необходимо выполнить следующую команду:<br>
<code>git commit</code><br>
При коммите добавляется редактор, где требуется внести описание коммита. Чтобы ввести описание коммита прямо в терминале, необходимо воспользоваться модификатором -m и передать описание, взятое в кавычки:<br>
<code>git commit -m "description"</code>

### История коммитов
Просмотреть историю всех коммитов можно выполнив следующую команду:<br>
<code>git log</code>

### Просмотр, создание и удаление веток
Для просмотра всех веток (в том числе текущей, которая выделена зеленым) необходимо выполнить следующую команду:<br>
<code>git branch</code><br>
Для создания новой ветки my_branch, необходимо выполнить следующую команду:<br>
<code>git branch my_branch</code><br>
Для удаления ветки надо добавить опцию -d. Если ветка не была запушена, но её всё равно требуется удалить, необходимо использовать -D вместо -d:<br>
<code>git branch -d</code> 

### Перемещение между ветками
Для перехода в другую ветку my_branch необходимо выполнить следующую команду:<br>
<code>git checkout my_branch</code><br>
Результат выполнения этой команды можно отследить, выполнив команду <code>git branch</code> (будет подсвечиваться зеленым другая ветка).

### Отслеживание изменений между ветками
Отследить изменения файлов между двумя ветками можно с помощью команды git diff, где указываются сравниваемые ветки (например master и my_branch):<br>
<code> git diff master my_branch</code>

### Обновление репозитория
Если репозиторий в git был изменен, а локальный при этом нет, можно подтянуть все эти изменения выполнив следующую команду:<br>
<code>git pull</code>

### Слияние веток
Чтобы смерджить текущую ветку с другой (например, с веткой мастер), необходимо выполнить следующую команду:<br>
<code>git merge master</code>

### Внесение изменений
Для внесения изменений в репозитории, необходимо создать merge request для слияния изменений в новой ветке my_branch с веткой origin. Для этого неоьходимо выполнить следующую команду:<br>
<code>git push origin my_branch</code> Обновление единого репозитория

## Полезные ссылки
- <a href="https://git-scm.com/book/ru/v2">Учебник по git</a>
- <a href="https://githowto.com/ru">Интерактивный учебник</a>
- <a href="https://learngitbranching.js.org/?locale=ru_RU">Анимированное объяснение git</a>
- <a href="https://habr.com/ru/post/342116/">Краткий обзор работы с git</a>
- <a href="https://habr.com/ru/post/174467/">Краткий обзор работы с git 2</a>
- <a href="https://www.atlassian.com/git">Мануал от Atlassian</a>
