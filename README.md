# Что такое Git и зачем он нужен? #
Git - это консольная утилита, для отслеживания и ведения истории изменения файлов, в вашем проекте. Чаще всего его используют для кода, но можно и для других файлов. Например, для картинок - полезно для дизайнеров.  

С помощью Git-a вы можете откатить свой проект до более старой версии, сравнивать, анализировать или сливать свои изменения в репозиторий. 

Репозиторием называют хранилище вашего кода и историю его изменений. Git работает локально и все ваши репозитории хранятся в определенных папках на жестком диске.  

Так же ваши репозитории можно хранить и в интернете. Обычно для этого используют три сервиса:

* GitHub
* Bitbucket
* GitLab   

Каждая точка сохранения вашего проекта носит название коммит (commit). У каждого commit-a есть hash (уникальный id) и комментарий. Из таких commit-ов собирается ветка. Ветка - это история изменений. У каждой ветки есть свое название. Репозиторий может содержать в себе несколько веток, которые создаются из других веток или вливаются в них.

# Как работает
Если посмотреть на картинку, то становиться чуть проще с пониманием. Каждый кружок, это commit. Стрелочки показывают направление, из какого commit сделан следующий. Например C3 сделан из С2 и т. д. Все эти commit находятся в ветке под названием main. Это основная ветка, чаще всего ее называют master . Прямоугольник main* показывает в каком commit мы сейчас находимся, проще говоря указатель.   
![v](g1.jpg)
В итоге получается очень простой граф, состоящий из одной ветки (main) и четырех commit. Все это может превратиться в более сложный граф, состоящий из нескольких веток, которые сливаются в одну.
![v](photo_5382061035613176177_x.jpg)

# Шпаргалка по основным командам
>git add     

Команда git add добавляет содержимое рабочей директории в индекс (staging area) для последующего коммита. По умолчанию git commit использует лишь этот индекс, так что вы можете использовать git add для сборки слепка вашего следующего коммита.

>git status  

Команда git status показывает состояния файлов в рабочей директории и индексе: какие файлы изменены, но не добавлены в индекс; какие ожидают коммита в индексе. Вдобавок к этому выводятся подсказки о том, как изменить состояние файлов.

>git diff

Команда git diff используется для вычисления разницы между любыми двумя Git деревьями. Это может быть разница между вашей рабочей директорией и индексом (собственно git diff), разница между индексом и последним коммитом (git diff --staged), или между любыми двумя коммитами (git diff master branchB).

>git difftool

Команда git difftool просто запускает внешнюю утилиту сравнения для показа различий в двух деревьях, на случай если вы хотите использовать что-либо отличное от встроенного просмотрщика git diff.

>git commit

Команда git commit берёт все данные, добавленные в индекс с помощью git add, и сохраняет их слепок во внутренней базе данных, а затем сдвигает указатель текущей ветки на этот слепок.

>git reset

Команда git reset, как можно догадаться из названия, используется в основном для отмены изменений. Она изменяет указатель HEAD и, опционально, состояние индекса. Также эта команда может изменить файлы в рабочей директории при использовании параметра --hard, что может привести к потере наработок при неправильном использовании, так что убедитесь в серьёзности своих намерений прежде чем использовать его.

# Шпаргалка по ветвлению и слиянию

>git branch

Команда git branch — это своего рода “менеджер веток”. Она умеет перечислять ваши ветки, создавать новые, удалять и переименовывать их.

>git checkout

Команда git checkout используется для переключения веток и выгрузки их содержимого в рабочую директорию.

>git merge

Команда git merge используется для слияния одной или нескольких веток в текущую. Затем она устанавливает указатель текущей ветки на результирующий коммит.

>git mergetool

Команда git mergetool просто вызывает внешнюю программу слияний, в случае если у вас возникли проблемы слияния.

>git log

Команда git log используется для просмотра истории коммитов, начиная с самого свежего и уходя к истокам проекта. По умолчанию, она показывает лишь историю текущей ветки, но может быть настроена на вывод истории других, даже нескольких сразу, веток. Также её можно использовать для просмотра различий между ветками на уровне коммитов.

# *Кратко о главном* 
> ✦ git init – инициализация локального репозитория  
 ✦ git status – получить информацию от git о его текущем состоянии  
 ✦ git add – добавить файл или файлы к следующему коммиту  
 ✦ git commit -m “message” – создание коммита.  
 ✦ git log – вывод на экран истории всех коммитов с их хеш-кодами  
 ✦ git checkout – переход от одного коммита к другому  
 ✦ git checkout master – вернуться к актуальному состоянию и продолжить работу  
 ✦ git diff – увидеть разницу между текущим файлом и закоммиченным файлом  
 ✦ git branch – посмотреть список веток в репозитории  
 ✦ git branch <название ветки> – создать новую ветку  
 ✦ git checkout <название ветки> – переход к другой ветке    
 ✦ git branch -d <название ветки> – удалить ветку  
 ✦ git clone <url-адрес репозитория> – клонирование внешнего репозитория на локальный ПК  
 ✦ git pull – получение изменений и слияние с локальной версией  
 ✦ git push – отправляет локальную версию репозитория на внешний
