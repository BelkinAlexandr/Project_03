# Проект №3 — Архитектура WEB. Тестирование клиент-серверных систем

Веб-приложения становятся всё более распространёнными и всё более сложными.
Они очень динамичны, непрерывно возрастает потоковый трафик. 
Как и во многих системах, основанных на взаимодействии между клиентом и сервером,
 дефекты и уязвимости веб-приложений обычно возникают из-за некорректной обработки запросов клиента. 
В рамках данного проекта вы с командой разберётесь в особенностях архитектуры веб-приложений
 и проведёте комплексное тестирование пользовательского интерфейса сайта https://online.sber.insure/store/propertyins/.

## Contents

1. [Chapter I](#chapter-i) \
    1.1. [Instructions](#instructions)
    1.2. [WEB Architecture](#web-archtecture)
    1.3. [Task 1](#task-web-architecture)
2. [Chapter II](#chapter-ii) \
    2.1. [HTTP](#http)
    2.2. [Task 2](#task-http)
3. [Chapter III](#chapter-iii) \
    3.1. [WEB Testing](#web-testing)
    3.2. [Task 3](#task-web-testing)
4. [Chapter IV](#chapter-iv) \
    4.1. [Dev Tools](#dev-tools)
    4.2. [Task 4](#task-dev-tools)
5. [Chapter V](#chapter-v) \
    5.1. [Firefox dev](#firefox-dev)
    5.2. [Task 5](#task-firefox-dev)


<h3 id="instructions" >Instructions</h3>

Это ваш первый групповой проект. Работайте как команда, у которой общие цели.
Распределяйте задачи, чтобы добиться максимальной эффективности.

*Все созданные файлы и скрины загружайте в папку src ветка develop.*  

*Данные на скриншотах должны быть читаемыми и должны покрывать смысл задания.*  

*Нумерация всех скриншотов начинается с 01. В случае, если содержимое занимает больше одной страницы и требуется сделать несколько скриншотов, добавляйте дополнительную нумерацию в конец названия файла: «…_01», «…_02» и так далее.*  

*Каждому участнику группы необходимо создать почту для использования в тестовых целях.*

<h2 id="chapter-i" >Chapter I</h2>

<h2 id="web-archtecture" >WEB Architecture</h2>

![WEB](misc/images/WEB.png)

Как работает системная архитектура для веб-приложений?
Базовая конфигурация веб-приложения: клиент, сервер, база данных.

Все приложения состоят из двух частей — клиентской (front-end) и серверной (back-end).
Интерфейс — это визуальная часть приложения.
Пользователи могут видеть интерфейс и взаимодействовать с ним.
Клиентский код реагирует на действия пользователей.
Серверная часть не видна пользователям, но она заставляет их запросы работать.
Она обрабатывает бизнес-логику и отвечает на HTTP-запросы.

Поэтому, когда вы вводите свои учётные данные в регистрационную форму, вы имеете дело с внешним интерфейсом, но как только вы нажимаете «ввод» и регистрируетесь — это серверная часть заставляет его работать.

При правильной работе клиентская и серверная стороны составляют архитектуру программного обеспечения веб-приложения.

**Базовые компоненты архитектуры веб-приложений**  

Веб-архитектура имеет компоненты пользовательского интерфейса и структурные компоненты.
Последние также делятся на клиентские и серверные.

__Компоненты пользовательского интерфейса__  

Компоненты пользовательского интерфейса — это все элементы интерфейса, такие как: журналы активности, информационные панели, уведомления, настройки и многое другое. Они являются частью макета интерфейса веб-приложения.

__Структурные компоненты__  

Структурные компоненты состоят из клиентской и серверной сторон.

Клиентский компонент разработан с помощью HTML, CSS или JavaScript.
Веб-браузеры запускают код и преобразуют его в интерфейс, поэтому нет необходимости в настройке операционной системы.

Что касается серверного компонента, он построен на Java, .NET, Node.js, Python и других языках программирования.
Сервер состоит из двух частей — логики приложения и базы данных.
Логика приложения — это центр управления веб-приложением.
База данных отвечает за хранение информации (например, ваших учётных данных).

__Уровни архитектуры веб-приложений__  

Существует четыре общих уровня веб-приложений:
- уровень представления (PL);  
- уровень обслуживания данных (DSL);
- уровень бизнес-логики (BLL);  
- уровень доступа к данным (DAL).  


<h3 id="task-web-archtecture" >Task 1</h3>

- Создайте файл «Web-architecture» и опишите в нём каждый из четырёх уровней веб-приложения;
- добавьте описание особенностей тестирования монолитных и микросервисных веб-приложений.

<h2 id="chapter-ii" >Chapter II</h2>
<h2 id="http" >HTTP — HyperText Transfer Protocol</h2>

Что такое HTTP?
В клиент-серверной модели клиенты и серверы обмениваются сообщениями по принципу «запрос — ответ»: клиент отправляет запрос, а сервер возвращает ответ.
Хранить трек из подобных сообщений сложнее, чем это звучит, поэтому клиент и сервер придерживаются общего языка и набора правил.
Этот «язык», или протокол, называется HTTP.
Протокол HTTP определяет синтаксис (формат и кодировку данных), семантику (значение, связанное с синтаксисом) и тайминг (скорость и последовательность).
Каждый HTTP-запрос и ответ, которыми обмениваются клиент и сервер, рассматривается как одна HTTP-транзакция.

С каждым годом этот протокол становится всё популярнее, и возможностей для его применения становится всё больше.

<h3 id="task-http" >Task 2</h3>

Создайте и заполните файл «HTTP»: 
- перечислите виды запросов HTTP-клиента (CRUD);
- укажите существующие ответы HTTP-сервера (успешные и неуспешные: 200, 500 и т. д.)


<h2 id="chapter-iii" >Chapter III</h2>
<h2 id="web-testing" >WEB Testing</h2>

Тестирование веб-приложений — это наблюдение за функционированием программы в искусственно созданных обстоятельствах, которое позволяет определить ее соответствие поставленным требованиям.


Задачи тестирования веб-приложений:

- нахождение ошибок в работе программы и эффективное их устранение;
- проверка электронных форм (и элементов) приложения на соответствие конкретным требованиям;
- проверка функционала на стороне клиента;
- обработка информации, которая станет основой для принятия последующих действий;
- оценка производительности и безопасности и т. д.

<h3 id="task-web-testing" >Task 3</h3>

- Создайте файл «WEB-Testing_checklist»;
- соберите в него основные виды тестирования веб-приложений (функциональные и нефункциональные) и их особенности (например Web-формы, кроссбраузерность, функциональное тестирование).

<h2 id="chapter-iv" >Chapter IV</h2>
<h2 id="dev-tools" >Dev Tools</h2>

Google Chrome — один из самых популярных браузеров.
Положение лидера делает тестирование в Chrome обязательным пунктом в чек-листе кроссбраузерного тестирования.
Инструменты разработчика (Dev Tools) — одна из функций браузера Chrome.
Эти инструменты стали важной частью ежедневной работы как разработчиков, так и тестировщиков. 

<h3 id="task-dev-tools" >Task 4</h3>

- Изучите основные панели в DevTools (elements, network, performance и проч.);
- сделайте тестовый набор в TestRail с названием «Chrome», добавьте туда функциональные и ui тесты (не менее 10 шт);
- проведите тестирование https://online.sber.insure/store/propertyins/ с помощью DevTools, отметьте статус прохождения тестов в TestRail;
- найдите все Content-Type любых пяти элементов тестируемого сайта, внесите данные в файл «Devtools_content»;
- выгрузите результаты запусков тестов из TestRail в файл «Results-devtools».



<h2 id="chapter-v" >Chapter V</h2>
<h3 id="firefox-dev">Firefox dev</h3>

Второй по популярности в мире браузер — Firefox.
В России на втором месте стоит Яндекс.браузер, но в нём нет такого мощного расширения, как Firebug.
Firefox dev ( бывший Firebug) — это многофункциональный плагин для браузера FireFox, который призван упростить процесс разработки и отладки веб-страниц.
Данное расширение позволяет в режиме реального времени инспектировать код страницы, выявлять в нём ошибки и тут же их исправлять.

<h3 id="task-firefox-dev" >Task 5</h3>

- Проведите тестирование сайта https://online.sber.insure/store/propertyins/ с помощью Firefox dev;
- сделайте отчёт по тестированию (найдите best practices и обсудите с командой, какой формат и наполнение лучше всего использовать для отчёта по данному тестированию);
- найдите значения для любых пяти элементов сайта https://online.sber.insure/store/propertyins/ (type, id, position, background), внесите их в файл «Elements»;
- отредактируйте styles или любой атрибут этих элементов (шрифт, цвет, расположение, прочее — на усмотрение команды);
- сделайте скрины этих элементов до и после редактирования, присвойте им названия: «01.before» — до; «02.after» — после;
- сделайте запись performance при прохождении одного из тест-кейсов, сохраните скриншот с названием «03.performance».

Пример результата performance: 

![WEB](misc/images/screen_21.png)

- обсудите в группе значения этих показателей;
- обсудите в группе отличия DevTools и Firefox dev, плюсы и минусы, выделите 10 пунктов — что самое полезное и обязательное в этих инструментах для целей тестирования. Все выводы внесите в файл «DevTools-Firefox»;
- сделайте страницу с инструкцией в Notion «Тестирование web-приложений с помощью DevTools и Firefox dev», сохраните скрины инструкции в папку «Notion»;
- загрузите файл «DevTools-Firefox», скрины измененных элементов, скрин результатов performance, скрин инструкции в Notion.

<h3>Double-check</h3>
Перед загрузкой выполненного проекта в репозиторий перепроверьте наличие всех необходимых файлов, которые требовалось создать во время выполнения проекта:

- файлы:
    - «Web-architecture»;
    - «HTTP»;
    - «WEB-Testing_checklist»;
    - «Devtools_content»;
    - «Results-devtools»;
    - «Elements»;
    - «DevTools-Firefox».
- скриншоты:
    - «01.before»;
    - «02.after»;
    - «03.performance».
- папка «Notion» со скриншотами инструкции.

>Пожалуйста, оставьте обратную связь по проекту в [форме обратной связи.](https://forms.gle/EYKHyx3pxRq6qqsS9)
