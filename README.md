# Инструкция по работе с GitHub.

Данная инструкция создана для освоения базовых работ с GitHub. И состоит из слудующих пунктов:

* Что такое GitHub и чем он отличается от Git

* Создание аккаунта в GitHub.

* Основные концепции GitHub простыми словами

* Создание репозитория и загрузка файлов

* Просмотр файлов в репозитории

* Поиск и чтение репозиториев

* Создание веток

* Переключение веток и решение конфликтов

* Настройка описания репозитория

* Вместо end()

## Что такое GitHub и чем он отличается от Git
GitHub — это облачная платформа для хостинга IT-проектов и совместной разработки, под капотом которой находится популярная система контроля версий Git, а также полноценная социальная сеть для разработчиков. 

## Создание аккаунта в GitHub.

Для создания аккаунта:
* Перейдите на сайт [github.com](https://github.com);
* Зарегистрируйтесь и верифицируйте адрес электронной почты;
* Выберите тип аккаунта: публичный или приватный;
В публичном аккаунте репозитории видны всем, а в приватном — только тем участникам, которым вы сами открыли доступ.

[Ссылка на подробную инструкцию по созданию аккаунта GitHub](https://learn.microsoft.com/ru-ru/visualstudio/version-control/git-create-github-account?view=vs-2022)

## Основные концепции GitHub простыми словами
Новичков интерфейс GitHub может сбивать с толку: за годы с момента создания площадка обросла множеством инструментов, но главное остаётся неизменным.

Почти вся терминология наследуется у Git. Основные термины — репозиторий, ветка, коммит, форк. Выбор некоторых из этих названий может показаться не очень интуитивным (даже если вы владеете английским), но так уж сложилось.

Как заливать файлы, создавать репозитории и проводить другие операции, мы рассмотрим в следующем разделе, так что не пугайтесь упоминания разных действий в определениях терминов — всё покажем с картинками :)

Репозиторий
Это просто корневая папка с файлами и вложенными директориями вашей программы — и одновременно её страница на GitHub. Загрузить в репозиторий можно всё что угодно, но предполагается, что вы будете хранить в нём файлы с исходным кодом и какие-нибудь дополнительные материалы — допустим, необходимую для GUI или вёрстки графику (картинки, иконки и тому подобное).

Репозитории могут быть публичными и приватными, в них можно создавать другие папки и отслеживать изменения версий. Управлять своими репозиториями можно прямо через интерфейс сайта, командную строку, десктопное приложение GitHub или различные средства разработки (IDE), поддерживающие интеграцию с сервисом.



Ветка (branch)
В ветки группируются изменения и обновления — допустим, одна главная ветка (по умолчанию создаётся main) и одна beta. Ветки независимы друг от друга, но при желании их можно объединять (merge — слияние) — даже если между ними есть разница в коде.

Способы изменения репозитория: коммит, пуш, клон, форк
Внести в содержимое репозитория изменения можно напрямую или создав копию. Само внесение изменений называется «коммит» (от английского commit — совершить), у него есть временная метка и хеш-сумма.

Перенос изменений-коммитов из локального репозитория (на вашем ПК) на удалённый (remote repository, то есть в данном случае на GitHub) называется «пуш» (push) — от английского «толкать» (дословно — «проталкивать» изменения).

Скопировать репозиторий для внесения изменений в копию можно двумя основными способами:

клонировать (clone) — то есть просто скопировать на локальный компьютер или сервер;
или форкнуть (от английского fork — развилка) — сделать отдельную копию репозитория (обычно чужого) для продолжения разработки «по другому пути развилки».
Если вы форкнули чужой проект, чтобы предложить автору конкретные улучшения, нужно по готовности «запулить» их в исходный репозиторий — то есть сделав pull request (запрос на изменения).

Это 90% необходимых фактов. Более скучные подробности описаны в документации и разделе обучения GitHub, а также в руководстве по самому Git, ну а мы попробуем применить всё это на практике.

## Создание репозитория и загрузка файлов
Конечно, самый простой способ пользоваться GitHub — через сайт, поэтому начнём отсюда.

Самые типичные действия при работе с репозиторием — его создание и загрузка файлов, их мы уже рассматривали ранее. Легко убедиться, что обе задачи занимают не больше 30 секунд.

Очень кратко повторим выводы из нашего прошлого материала:

для создания репозитория нужно нажать на + в правом верхнем углу сайта, выбрать пункт New Repository, заполнить название и описание, проставить нужные галочки и щёлкнуть на Create Repository;
для загрузки файлов нужно зайти в нужный репозиторий, щёлкнуть на Add file и выбрать Upload files.
12



Шаг 1. Создание GitHub-репозитория в веб-версии_Скриншот: Skillbox Media_



Шаг 2. Страница создания GitHub-репозитория_Скриншот: Skillbox Media_

Но для обучения Тёмной стороне Силы работе с GitHub полезно потренироваться выполнять и другие необходимые в процессе разработки действия: клонирование/форк, объединение веток, просмотр и разрешение конфликтов и другие.

Давайте пошагово пройдём всё это вместе — сначала через сайт, а потом взглянем одним глазком на работу через GUI-клиенты и интерфейс командной строки (CLI).

## Просмотр файлов в репозитории

Выбор файлов в GitHub-репозитории для их просмотра_Скриншот: Skillbox Media_

Согласитесь, что в ряде случаев удобно не скачивать исходники, а просто бегло ознакомиться с ними. Для таких простых операций вовсе не нужен десктопный клиент: все файлы можно быстро открыть в веб-версии (и код, и те же картинки). Просто щёлкните по ним для просмотра!

12



На этой картинке — просмотр файла с кодом. Всё как полагается: есть нумерация строк и подсветка синтаксиса_Скриншот: Skillbox Media_



А здесь — просмотр картинки, которая нужна нам для GUI и потому также залита в репозиторий_Скриншот: Skillbox Media_

## Поиск и чтение репозиториев
Хотя сёрфинг по чужим репозиториям — залипательное времяпровождение, в первую очередь это один из способов нахождения полезных инструментов вам в помощь. Над многими функциями, которые вы хотели бы добавить в своё приложение, уже кто-то работал, остаётся только найти GitHub-репозитории таких проектов.

Как и в других случаях поиска, вы можете выйти на нужный репозиторий из поисковика или через внутренний поиск по GitHub.



Для примера: это официальный GitHub-репозиторий Android-приложения Telegram. Смотрим на детали: краткое описание — About (Telegram for Android source), две ветки (там master и dev), в мастере 462 коммита, 227 пул-реквестов, последний релиз шесть дней назад, лицензия GPL 2.0, 1,2 тысячи наблюдателей, 7,1 тысячи форков и целая 21 тысяча добавлений в закладки_Скриншот: Skillbox Media_

Важнее другое — на что обращать внимание. Пройдёмся по некоторым пунктам со скриншота выше.

Во-первых, самое очевидное — это описание на главной странице. Именно в нём находится ответ на ваш главный вопрос — что это и чем может вам помочь.

Если точнее, предусмотрено два описания репозиториев — краткое (один абзац справа вверху) и полное (по центру, под списком файлов).

Если репозиторий кажется полезным, дальше нужно понять, на каких условиях вы можете его использовать, что зависит от указанной автором лицензии.

После этого оцените, подходит ли вам частота обновлений, — это можно сделать в разделе Releases (ссылка прямо под кратким описанием). Конечно, это зависит от ситуации: где-то может пригодиться инструмент, который не обновлялся четыре года, но чаще всего нужна хотя бы минимальная поддержка — то есть обновления минимум раз в несколько месяцев.

Важно знать и где посмотреть количество и содержание коммитов — кликабельный счётчик находится над списком файлов справа.

Наконец, стоит взглянуть и на количество отметок, демонстрирующих популярность проекта среди сообщества, — отслеживаний, форков и звёздочек (это в каком-то смысле местные аналоги лайков и репостов).

Ещё чуть ниже справа — одна из самых интересных штук: анализ используемых в репозитории языков программирования. В репозитории со скриншота выше набор выглядит так.



Языки программирования, на которых написан код загруженных в репозиторий исходников Android-приложения Telegram_Скриншот: Skillbox Media_

Вообще, неплохо изучать репозитории известных приложений, которыми сами пользуетесь (как на скриншоте выше), и отмечать понравившиеся звёздочками. Это не только интересно — со временем GitHub изучит ваши предпочтения и станет предлагать в блоке Explore то, что вам может понравиться.



Пример: GitHub-репозиторий VK_Скриншот: Skillbox Media_

## Создание веток

Создаём альтернативную ветку №1 — koshka_Скриншот: Skillbox Media_

Создать новую ветку очень просто:

Жмём на большую зелёную кнопку New branch.
Вводим название новой ветки.
Выбираем исходную ветку для копирования (то есть main, так как пока других и нет).
Щёлкаем на Create branch.

## Переключение веток и решение конфликтов
В данном случае нужно сначала уточнить, что имеется в виду: если необходимо просто зайти в альтернативную ветку, это можно сделать в списке веток репозитория (нужная ссылка есть над списком файлов).

Создадим также альтернативную ветку №2 (sava) и посмотрим, как всё это выглядит в итоге.



Список веток репозитория: основная и две альтернативных_Скриншот: Skillbox Media_

Можно говорить и про переключение между ветками в другом смысле — когда изменения из альтернативной ветки сливают с главной веткой. Смотрите: у нас есть файл code.js, но его содержимое немного отличается:

в ветке main там JS-команда console.log («Дефолтная ветка») и картинка с великим маэстро современности Риком Эстли;
однако в ветке koshka тот же файл содержит команду console.log («Кошка!»);, а вместо Рика — смешной кот;
и всё совсем усложняется третьей веткой sava, где консольный вывод вида console.log («Сова!»); и используется картинка с совой (естественно, все перечисленные картинки во всех ветках называются одинаково — pic.jpg).
Получается, между ветками есть конфликт и просто слить любую из альтернативных веток с главной нельзя! Но для этого уже есть решение: GitHub предлагает нам сравнить конфликтующие ветки, и если мы захотим, то и запулить изменения в основную — то есть сделать тот самый pull request, о котором говорилось выше.



Так GitHub сообщает, что в некоторых ветках есть изменения_Скриншот: Skillbox Media_

Вот как выглядит сравнение веток (c koshka и sava соответственно).

12



Сравнение ветки main с веткой koshka_Скриншот: Skillbox Media_



Сравнение ветки main с веткой sava_Скриншот: Skillbox Media_

Допустим, мы решаем принять изменения из ветки sava и создаём pull request с небольшим комментарием.



Создание пул-реквеста для слияния изменений из ветки sava с веткой main_Скриншот: Skillbox Media_

Дальше он появляется в списке пул-реквестов репозитория, где мы определяем дальнейшую судьбу данного запроса на изменения.



В соответствующем разделе репозитория появился новый пул-реквест_Скриншот: Skillbox Media_

Пул-реквест можно окончательно принять, подтвердив слияние (merge) веток, или отклонить, закрыв запрос (Close pull request).

12



Шаг 1. Рассмотрение пул-реквеста_Скриншот: Skillbox Media_



Шаг 2. Рассмотрение пул-реквеста_Скриншот: Skillbox Media_

При этом главную ветку main можно защитить от изменений, включив соответствующие опции в настройках репозитория (что вам и будет предложено при создании новых веток).



GitHub предлагает защитить ветку от нежелательных изменений_Скриншот: Skillbox Media_

Чтобы поменять данный ряд параметров, зайдите в своём репозитории в раздел Settings -> Branches. Нужные настройки — в подразделе Branch protection rules (целых 10 галочек на выбор).

## Настройка описания репозитория
Основное описание вашего GitHub-проекта задаётся в файле Readme.md, который можно создать вместе с репозиторием или после. Расширение md — это просто сокращение от названия популярного языка упрощённой разметки контента — Markdown.

Содержимое файла Readme отображается на главной странице репозитория и отвечает на вопрос, что это за проект, чем он может быть полезен другим разработчикам и как им воспользоваться.

Чтобы оформить Readme со вкусом, можно воспользоваться руководством GitHub по markdown-разметке. Вот как будет выглядеть Readme нашего репозитория-примера после прокачки (первый и второй экран соответственно).

12



Настройка файла Readme GitHub-репозитория_Скриншот: Skillbox Media_



Настройка файла Readme GitHub-репозитория_Скриншот: Skillbox Media_

Обратите внимание: в оформлении можно использовать всё что угодно — заголовки разных уровней, выделение жирным/курсивом, изображения, эмодзи, ссылки и так далее.

Файл Readme может быть довольно длинным, но всё же для оформления большой документации GitHub рекомендует создать «Вики».

## Вместо end()
Всё не так сложно, как может показаться (говоря иносказательно, каждый разработчик в своей жизни сначала учится есть вилкой, а потом — форкать GitHub-репозитории).

GitHub пользуются все: это один из важных общих навыков вне зависимости от выбранного вами языка программирования и направления разработки. И, как и школьные уроки ОБЖ, тот же git clone когда-нибудь вас спасёт.

Поэтому важно начинать пользоваться GitHub как можно раньше — хотя бы даже для бэкапов учебного кода, и уже скоро это станет полезной привычкой.