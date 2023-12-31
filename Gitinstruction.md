![logotip](gitim.png) 

# Работа с Git

## 1. Проверка наличия установки Git
В терминале выполнить команду `git --version` 
Если Git установлен появиться сообщение с информацией о версии программы, иначе будет сообщение об ошибке.

## 2. Установка Git
Загружаем последнюю версию Git с [сайта](https://git-scm.com/downloads).
Устанавливаем с настройками по умолчанию.

## 3. Настройка Git
При первом использовании Git необходимо представиться.
Для этого нужно ввести в терминале 2 команды:
```
git config --global user.name «Ваше имя английскими буквами»
git config --global user.email ваша почта@example.com
```
Далее что бы Git начал отслеживать всё, что мы будем делать в своей папке его нужно инициализировать Git, запустив специальную команду 
```
Git init
```
Чтобы проверить, что Git думает о нашей папке и её содержимом, а также
статус происходящего
пишеться команда
```
Git status
```
Т.к. ни каких фиксаций мы еще не делали, то Git выдаст нам, что мы находимся в ветке master, и никаких
commit нет (commit — это фиксация).

## 4. Создание и изменение нового файла
В нашей папке создаем файл, напишем в нём какой-нибудь текст и добавляем к нему расширение (расширение может быть любое, например .md, .txt, .doc)
Сохраняем нажав Ctrl+s или Cmd+s,
если работаете на Mac. Теперь попросим Git указать текущий статус. Он говорит нам создать
файлы. Чтобы Git начал отслеживать изменения в этих файлах, их надо добавить.
В терминале для этого есть подсказки, где
говорится, что мы можем использовать команду `git add` (add — «добавить») и указать какие-то
файлы, чтобы включить их в фиксацию.

Изменим наш файл. Напишем в нём какой-нибудь текст. Наш файл видоизменился.
Напишем `git add`. Далее ещё раз смотрим на статус. Снова строка hello world стала зелёной. То
есть у нас есть какой-то изменённый файл, который теперь можем сохранить. Пишем `git
commit` и указываем новое сообщение, например, «Добавили новую строку». Нажимаем Enter
— появилось некоторое сохранение.

## 5. Создаём журнал изменений
Теперь у нас есть несколько сохранений. Появилась возможность
переходить от одной версии файлов к другой, что нам и хочется от системы контроля версий. Но сначала посмотрим, какие версии существуют. Для этого используется специальная
команда `git log`. Log — это просто журнал изменений, каких-то событий, которые у нас
хранятся.

Набираем `git log` и видим немного странный вывод, к которому вы скоро привыкнете. Главное,
что у нас есть некоторые фиксации (сохранения) — первое сохранение и второе сохранение.
К каждому сохранению прикреплены текстовые комментарии, которые мы оставили. И уже
можно понять следующее:
* первое сохранение относится к добавлению новой строки;
* второе сохранение относится к созданию нового файла.

## 6. Переход к предыдуще версии файла
Сейчас мы находимся на первом сохранении. Но если хотим перейти к предыдущей версии
файла, воспользуемся для этого указанным commit. Это очень непонятное сочетание букв и
цифр, по которым можем перейти. Чтобы перейти к какой-то версии, сохранению, надо
вызвать команду `git checkout`.

После команды `git — пробел — checkout — пробел` укажем, какое сохранение надо загрузить.
Можем указать либо название целиком, либо первые четыре символа, что и позволяет Git.
Первых четырёх символов достаточно, чтобы понять, какое сохранение надо запустить.
Скопируем их и после `git checkout` укажем именно этот набор символов. Далее нажимаем на
Enter — исчезла строка, которую мы писали. То есть версия файла вернулась к сохранённым.

Теперь можем вернуться к версии, которая нас интересовала, посмотреть на сохранение и
выбрать, например, то, что было выше, затем снова вызвать `git checkout` и ввести символы.
Видим, что случилась магия. Мы перешли к новой версии. У нас опять появилась строка,
которую писали.

## 7. Возврат в актуальную версию
Cейчас, чтобы всё работало и ничего не сломалось, требуется вернуться в актуальное состояние. Для этого надо не просто указать необходимый commit, а что-то иное. Мы сами напишем `git checkout
master`. Master — это название ветки, в которой работаем

## 8. Игнорирование файлов
Для того чтобы исключить из отслеживания в репозитории определенные файлы или папки необходимо создать там файл ***.gitignore*** и записать в него их названия или шаблоны, соответствующие таким файлам или папкам.

## 9. Создание веток Git
По умолчанию имя основной ветке в Git - **master**

Создать ветку можно командой 

```
git branch <имя новой ветки>
```
Список веток в репозитории можно посмотреть с помощью команды `git branch`.
Текущая ветка будет отмечена звездочкой **\* master**

Есть еще один способ добавить ветку и срузу на нее перейти, для этого используется команда `git checkout -b <Название ветки>`
## 10. Слияние веток и разрешение конфликтов.

Для слияние веток используется команда `git merge <название ветки которую нужно слить>`
. При этом мы должны находиться в той ветке в которую нужно сливать.

При слиянии веток может произойти конфлик, когда в разных ветках одни и теже строчки содержат разные данные. Git не поймёт, какую версию необходимо использовать. Этот конфликт нужно разрешить выбрав текущую версию, версию которая пришла с другой ветки или оба варинта. 

## 11. Удаление веток.
Отработанные и слитые ветки которые нам уже не нужны лучше удалять. Для этого используется команда `git branch -d <название ветки>`. Нельзя удалить ветку в которой вы находитесь.

Чтобы удалить не нужную (лишнюю), но еще не слитую ветку, можно сделать это принудительно с помощью команды `git branch -D <название ветки>`. В Git команды начинающиеся с заглавных букв означает какое-то принудительное действие.  
## 12. Работа с удаленными репозиториями
1. В первую очередь нужно создать аккаунт на сервисе с которым будете работать удаленно. В нашем случае это **GitHub**. Соответственно авторизироваться и начать работу.

Затем нужно создать удаленный репозиторий. С помощью кнопки `+` `creat new..` создаем `new repository`.
Также создаем локальный репозитори на своем устройстве. Далее нужно связать удаленный репозиторий с локальным. Чтобы добавить удаленный репозиторий к проекту используется команда:
```
git remote add <имя репозитория> <url-адрес репозитория в сети>
```
Далее идет команда для того чтобы переименовать ветку в main, если она такой не является.  
```
git branch -M main
```
И команда чтобы отправить изменения локального репозитория на удаленный.
```
git push -u origin main
```
После этих действий если вы еще не авторизованы вас попросят это сделать.

2. Теперь когда все сделано верно, можно вносить изменения (корректировать) в данных репозиториях и сохранять. Используя команды:

 Для получения и слияния изменений из удаленного репозитория используется команда `git pull`

Отправить изменения локального репозитория в удаленный `git push` 

Также чтобы посмотреть список удаленных репозиториев есть команда `git remote`
## 13. Pull request
Это инструмент, который позволит другим людям предлагать
изменения в какой-либо проект. `Pull
request` — это запрос на вливание данных в какой-то репозиторий.

Как сделать pull request:

1. В своём аккаунте на GitHub создать копию интересующего репозитория с помощью кнопки "Fork".
2. С помощью команды `git clone <url-адрес репозитория в сети>` делаем локальную копию версии репозитория на своем устройстве.
3. Создаем новую ветку `(git branch)` и в `ней` вносим свои изменения.
4. Сохраняем эти изменения и коммиты к ним. `(git add и git commit)`
5. Отправляем эту версию на собственный аккаунт.`(git push)`
6. В окне на GitHub появляется возможность отправить `pull request`.