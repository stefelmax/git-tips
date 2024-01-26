# Шпаргалка по работе с GIT

## Работа с SSH ключами

### Проверка наличия SSH-ключа


Прежде чем генерировать SSH-ключи, убедитесь, что у вас их ещё нет. По умолчанию директория с SSH-ключами находится в домашней директории пользователя. 

```$ cd ~```  перешли в домашнюю директорию. Обычно SSH-ключи находятся в директории ```.ssh/```.
Проверить наличие этой директории и файлов в ней можно с помощью следующей команды.
```ls -la .ssh/```  вывели список созданных ключей 


Если есть файлы с похожими названиями, SSH-ключи уже создавались:
```id_dsa.pub;```
```id_ecdsa.pub;```
```id_ed25519.pub;```
```id_rsa.pub.```


### Инструкция по генерации SSH-ключа

Для генерации SSH-пары можно использовать программу ssh-keygen. Откройте терминал и введите следующую команду.
```$ ssh-keygen -t ed25519 -C``` "электронная почта, к которой привязан ваш аккаунт на GitHub" 
    Используйте электронную почту, к которой привязан ваш GitHub-аккаунт.
    Если вы видите сообщение об ошибке, то, скорее всего, ваша система не поддерживает алгоритм шифрования ed25519. Ничего страшного: используйте другой алгоритм.
```$ ssh-keygen -t rsa -b 4096 -C "электронная почта"```, к которой привязан ваш аккаунт на GitHub" 
    После ввода отобразится такое сообщение.
```> Generating public/private rsa key pair``` сгенерированы публичный и приватный ключи 

Укажите место хранения ключей. Простой вариант — сделать домашний каталог пользователя путём по умолчанию. Для этого нажмите Enter.
macOS
```> Enter a file in which to save the key (/Users/you/.ssh/id_rsa): [Press enter] ```


## Работа с командной строкой

Менять директории командой ```cd```;
выводить содержимое директорий с помощью ```ls```;
```pwd``` — проверить, где мы находимся;
просматривать содержимое вместе со скрытыми файлами и папками через ```ls -a```.


Команда ```touch``` создаёт файл, а команда ```mkdir``` — директорию.
С помощью флага -p можно создать целую структуру директорий одной командой: ```mkdir -p```.
Для копирования файлов используют команду ```cp```, для перемещения — ```mv```.


Вывести содержимое файла можно командой ```cat```.
Для удаления файла используют ```rm```, для удаления пустой директории — ```rmdir```, а для директории с файлами — ```rm -r```.

*Все команды удаления стирают данные безвозвратно — их нельзя будет восстановить из корзины!*


Для быстрой работы:

С помощью ```&&``` можно выполнить несколько команд сразу — одну за другой.
Команды, которые вы выполняете в консоли, попадают в историю. Вы можете перемещаться по этой истории при помощи стрелок ```↑↓```.
При нажатии на ```Tab``` консоль предложит несколько вариантов продолжения команды.
Символами ```/``` и ```~``` можно быстро перемещаться к корневой и домашней директориям.


## GIT основные команды

Сделать папку репозиторием — ```git init```

```
$ cd ~/dev/first-project # перешли в нужную папку

$ git init # создали репозиторий 
```

«Разгитить» папку, если что-то пошло не так, — ```rm -rf .git```


Проверить состояние репозитория — ```git status```


Команда ```git add``` позволяет подготовить файл к сохранению.

Команда ```git add --all``` подготовит к сохранению сразу все файлы.

С помощью ```git add .``` можно добавить в репозиторий текущую папку со всеми файлами.


Коммит можно сделать с помощью команды ```git commit```.
Ключ ```-m``` позволяет присвоить коммиту сообщение. Помните, что такие сообщения должны быть информативными: чётко описывать изменения.
В коммит попадает то, что было предварительно добавлено «в корзину», или «в кадр», перед коммитом.



Просмотреть историю коммитов — ```git log```




___
## Работа и оформление текста
### Заголовки


```
# H1 — заголовок первого уровня, самый большой
## H2 — заголовок второго уровня, поменьше
### H3
#### H4
##### H5
###### H6 — заголовок шестого уровня, самый маленький
```
___

#### Выделение текста
```
Чтобы выделить текст курсивом (*текст*), его заключают в звёздочки (астериски) или нижние подчёркивания.
Курсив — это *звёздочки* или _подчёркивания_. 
```

Чтобы выделить текст полужирным шрифтом (**текст**), его окружают двойными звёздочками или двойными нижними подчёркиваниями.

```
Полужирный шрифт — двойные **звёздочки** или двойные __подчёркивания__.
Можно совместить выделение **звёздочки и _подчёркивания_**.
```


Чтобы зачеркнуть текст (~~текст~~), его окружают двойными волнистыми линиями — тильдами.

```
~~Зачёркнутый текст.~~
``` 

___


#### Списки

Для оформления нумерованного списка достаточно поставить в начало строки цифры с точкой.
```
1. Первый пункт нумерованного списка.
2. Второй пункт.
```


Ненумерованный список создаётся звёздочкой с пробелом в начале строки либо дефисом с пробелом.
```
* первый пункт ненумерованного списка;
* второй пункт ненумерованного списка

- первый пункт ненумерованного списка;
- второй пункт ненумерованного списка
```
___

#### Ссылки
Чтобы сделать ссылкой часть текста, его заключают в квадратные скобки, а затем указывают нужный адрес в круглых скобках.

```
[Яндекс](https://www.yandex.ru) 
```

Также можно добавить ссылке тайтл (от англ title — «название», «заголовок»). Тайтл — это всплывающая подсказка, которая появляется при наведении мыши на ссылку. Тайтл нужно заключить в кавычки и указать внутри скобок после адреса.

```
[Яндекс](https://www.yandex.ru "Я Yandex!") 
```

___

#### Код

Чтобы оформить текст как код, нужно окружить его тройками косых кавычек — грависов. После первой тройки грависов указывают язык программирования, на котором написан код. В маркдауне есть поддержка синтаксиса почти всех популярных языков и инструментов.
```
    ```bash
    ls - la
    ```
    ```html
    <h1>А я просто текст</h1>
    ``` 
```