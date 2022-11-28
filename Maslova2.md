# Git Seminar. Comits

## Необходимый алгоритм работы с Git 
## 1. Шаг внесения изменений
   
**Внесите необходимую информацию**, используя возможности MD

## 2. Шаг сохранения изменений
   
 **Сохраните изменения**, используя горячие клавиши **Cntrl + S** либо **Cmnd + S**


## 3. Шаг Git add

 **Добавьте текущую версию сохранения к отслеживанию** с помощью команды **git add**
   
## 4.  Шаг Git commit

**Зафиксируйте уже сохраненные изменения** в журнал изменений с помощью команды **git commit** 

   Команда пишется так:

 *git commit -m"Комментарий коммита, наиболее четко отражающего суть изменений"*

## Визуальное представление терминала

Терминал в процессе выполнения 4х шагов может выглядеть так:

![Skreenshot](Снимок%20экрана%2002.png)

## Команды управления Git

* git status - покажет содержание проекта и проделанные действия
* git log - покажет журнал изменений
* git checkout master - вернёт к главной ветви
* git diff - покажет разницу между этим сохранением и предыдущим коммитом
* git branch name - переведёт на ветвь с именем name
* git checkout name - переместит на ветвь с именем name
* git merge name - сольёт настоящую ветвь с ветвью с именем name
* git branch -d name - создаст новую ветвь с именем name
* git log --graph - покажет графическое дерево ветвей
* git commit --amond -m"Новый комментарий" - исправит имя предыдущего коммита


## ВАЖНО
Переходя на checkout, **НЕЛЬЗЯ** вносить изменения!


Команда git commit --amond -m"Новый комментарий" 
работает **только на последний комментарий** к коммиту!


Merge нужно вызывать **ИЗ ВЕТВИ, на которую нужно влить** другую ветвь


## **Семинар 2** - Дз

- Описать виды разрешения конфликтов
- Сделать общий конспект
- Описать виды слияния 
- Описать новые команды
- Описать автокоммитинг

При этом: в процессе от 4х веток и слить их по каждому варианту слияния по паре раз

2 fast-forvard

2 "ort" strategy

2 conflicts

## Fast-Forward

FF - вариант слияния конфликта, когда одна ветвь опережает другую по информации. Слияние происходит автоматически. В терминале выходит такое сообщение, как на картинке ниже:

![seccessfullMerge](11.png)


Если выполнена команда "git add .", а не "git add name", то слияние ветвей произойдет автоматически с сообщением, как на картинке ниже: 

![nothingToCommit](12.png)
![conflictRezolved](13.png)

## Merge made by the "ort" strategy

Ort - слияние, когда добавление информации и коммиты есть на разных ветвях в разных блоках, и в слияянии ничто не вызывает противоречий.

Пока не получилось сделать, задам вопрос на семинаре

## Conflict

Вариант слияния, когда возникает противоречие в информации в одном и том же блоке и в разных ветвях. Тогда терминал предлагает решить самостоятельно, какую часть информации оставить. 

*Вариантов решения конфликта может быть несколько:*

- Assept Current Changes - принять вариант основной ветви (на которой стоишь)
- Assept Incoment Changes - принять вариант добавляемой ветви
- Assept Bouth Changes - принять информацию с обоих вариантов
- Compare Changes - спецокно с построчным разбором, что принять, а что удалить
- Разрешить в редакторе слияния - лучше пока не лезть
- Удалить ключевые слова вручную - приравнивается Assept Bouth Changes


## Новые команды

Новые команды в этом семинаре мы не проходили, но я заметила паттерны, которые опишу в разделе "Примечания"

Для создания конфликта я дописывааю эту строку в уже готовый раздел

## Автокоммитинг

Автокоммитинг возникает, когда происходит слияние 2х веток по варианту ort strategy. Больше пока не знаю))

## Примечания

1. Названия веток удобнее писать с маленьгой буквы, потом легче прописывать команды
2. В описание картинок [Внутри] должен быть непрерывный шрифт, иначе программа не работает
3. После разрешения конфликта ОБЯЗАТЕЛЬНО нужно сделать коммит, дабы не потерять слияние
4. При git checkout НЕЛЬЗЯ вность изменения, доступен только просмотр
  
  
# Семинар 3. Работа с удаленными репозиториями

## Работа с репо на Гитхабе, который принадлежит мне

Необходимо создать удаленный паблик репо на Гитхаб, а далее соединить его с локальным на компьютере. 

Для этого необходимо использовать команду: 

- *git remote add origin https: ...*
Она добавит в пару удаленный репозиторий, и далее с помощью команлы 
- *git push* можно будет добавлять изменения с локального репозитория в удаленный
- *git pull* зальёт изменения с удаленного репозитория в локальный, если вдруг удаленный опережает

## Работа с репо на Гитхабе, который не принадлежит мне

Чтобы работать с чужим репозиторием, он должен быть паблик, а вы должны знать ссылку

 1. Сделать Fork репозитория к себе на удаленный аккаунт (при желании можно переименовать, скачать либо ветку мастер, либо все ветки)
 2. В VSCode клонировать репозиторий своего Forka, для этого для него необходимо создать папку
 3. Можно добавлять и редактировать файлы, создавать побочные ветки
 4. Git push внесет эти изменения в удаленный fork 
 5. Слева вверху Pull requests запросит добавить изменения в репозиторий хозяина, необходимо описать изменения в окне и назвать отчет


Если изменения произведены не в в основной ветке, а в дополнительной, то нужно добавленную ветку сделать потоковой:

*git push --set upstream origin "BranchName"*

В форке после обновления страницы будет возможность выбрать ветку, а также сформировать запрос на pull gequest


*git checkout -b NewBranchName* одновременно и создает и переходит на новую ветку, удобно!