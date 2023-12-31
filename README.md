#  <p align="center"> Домашнее задание к занятию «4.2. Заключительная лекция» </p>
### <p align="right"> Выполнил Долгов Давид  <br> QA - 53 </p>
<br>
<br>
<br>

# <p align="center"> План на автоматизацию </p>
___Для начала думаю стоит описать задачу и полный путь того, что происходит, когда юзер совершает запись на курс Тестировщик ПО.___ 
<br><br>
     Заходим на сайт <a href="https://netology.ru/">Нетологии</a>. Выбираем из каталога курс "Тестировщик ПО". После ознакомления со страницей заполняем данные (имя и номер телефона). Ожидаем звонка.
<br>
<br>

___Что происходит на самом деле?___
<br><br>
    Результатом нижеописанного позитивного сценария является сохранение информации в БД. После этого запрос с собранной информацией переходит в задачи сотрудников, которые совершают звонок. 
<br>
<br>
    
___Учитывая всё вышесказанное, уже можно составить план на распределение времени и ресурсов для проверки сценариев для автоматизированного тестирования.___
<br>
<br>

_Итак, приступим._ 

## <p align="center"> 1. Перечень автоматизируемых сценариев. </p>
<br>

___По сути, начало у каждого сценария всегда одинаковое. Нам нужно зайти на сайт и прокликать до заполнения формы или ввести через поиск и дойти до заполнения формы.___ 

_Поэтому будут расписаны несколько условий, которые выполняются до начала каждого теста._ 

1. __Первый вариант__
   - Заходим на сайт [Нетологии](https://netology.ru/).
   - Кликаем на меню   ![Каталог курсов](%D0%BA%D0%B0%D1%82%D0%B0%D0%BB%D0%BE%D0%B3%20%D0%BA%D1%83%D1%80%D1%81%D0%BE%D0%B2.png)
   - Выбираем ![Все курсы](%D0%B2%D1%81%D0%B5%20%D0%BA%D1%83%D1%80%D1%81%D1%8B.png)
   -  Среди списка находим ссылку ![Тестировщик ПО](%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D1%89%D0%B8%D0%BA%20%D0%9F%D0%9E.png)  и переходим по ней.
   - В конце страницы находим форму заполнения на запись. 
  ![Запись](%D0%97%D0%B0%D0%BF%D0%B8%D1%81%D1%8C.png) 

1. __Второй вариант__
   - Заходим на сайт [Нетологии](https://netology.ru/). 
   - Кликаем на меню   ![Каталог курсов](%D0%BA%D0%B0%D1%82%D0%B0%D0%BB%D0%BE%D0%B3%20%D0%BA%D1%83%D1%80%D1%81%D0%BE%D0%B2.png)
   - Выбираем ![Программирование](%D0%9F%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5.png)
   - Среди списка находим ссылку ![Тестировщик ПО](%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D1%89%D0%B8%D0%BA%20%D0%9F%D0%9E.png) и переходим по ней.
   - В конце страницы находим форму заполнения на запись. 
  ![Запись](%D0%97%D0%B0%D0%BF%D0%B8%D1%81%D1%8C.png) 

1. __Третий вариант__
   - Заходим на сайт [Нетологии](https://netology.ru/). 
   - Кликаем на меню   ![МенюПрог](%D0%9C%D0%B5%D0%BD%D1%8E%D0%9F%D1%80%D0%BE%D0%B3.png)
   - Находим ссылку ![Тестировщик ПО](%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D1%89%D0%B8%D0%BA%20%D0%9F%D0%9E.png) и переходим по ней.
   - В конце страницы находим форму заполнения на запись. 
  ![Запись](%D0%97%D0%B0%D0%BF%D0%B8%D1%81%D1%8C.png) 

_Далее будут прописаны сценарии тестов, начиная с заполнения формы._

1. Позитивный сценарий, где вводятся валидные данные ( поле ввода "имя" - Давид; поле ввода "телефон" - +7 987 654 32 21 ). Нажимаем на кнопку "Записаться". Проверям запись данных в БД. Проверяем создание запроса во внутреннем сервисе для менеджеров компании Нетология.
2. Негативный сценарий, где вводятся невалидные данные (000йцуqwe123) в поле для ввода "имя", и при нажатии на кнопку "Записаться" поле окрашивается в красное и просят ввести нужную информацию. При этом номер вводится в верном формате ( +7 900 987 65 43 ) 
3. Негативный сценарий, где вводятся невалидные данные (йцукывсампи) в поле для ввода "телефон", и при нажатии на кнопку "Записаться" поле окрашивается в красное и просят ввести нужную информацию. При этом имя вводится в валидном варианте ( Давид )
4. Негативный сценарий, где поле ввода "Имя" пустое, а поле ввода "телефон" записаано верно ( +7 900 987 65 43 ). Форму нельзя отправить пока не заполнится поле ввода "Имя".
5. Негативный сценарий, где поле ввода "Телефон" пустое, а поле ввода "Имя" записаано верно ( Давид ). Форму нельзя отправить пока не заполнится поле ввода "Телефон".
6. Ряд негативных сценариев по количеству символов:
   - 1 символ, кириллица
   - 100 симоволов, кириллица
 и ввода спец. символов в поля ввода:
     - ввод символов (!"№;%:?*()-_1234567890~`@#$^&* )
     - ввод символов на латинице ( qwerty ) 
<br>

___Данные можнно ввести правильно, но это не значит, что они будут корректными. Для проверки номера телефона можно добавить проверку номера путём ввода смс-кода. Имя можно уточнить уже во время разговора во время звонка от менеджера.___ 
<br>

_Для проверки данного списка сценариев нам понадобится ряд инструментов:_

## <p align="center"> 2. Перечень используемых инструментов с обоснованием выбора. </p>
<br>

1. <b>IntelliJ IDEA</b> - Конечно же, нам нужна сама среда разработки, где будет прописан код для автотестов.
2. <b>Gradle</b> - Хороший фреймворк для работы и создания проекта. 
3. <b>JUnit</b> - Удобная библиотека методов и аннотаций для написания автотестов.
4. <b>Selenide</b> - Библиотека, позволяющая работать с элементами web-страниц для кода автотестов, а также помогает собирать информацию для отчётов.
5. <b>Mockito</b> - Традиционный подход для создания «заглушек», конкретных реализаций интерфейса, подходящих для сценариев с введением кода из смс для проверки номера телефона.
6. <b>Docker</b> - Данный инструмент нам нужен для поднятия базы данных, а также чтобы иметь возможность проверить, как ведёт себя сайт Нетологии на разных устройствах и операционных системах.
7. <b>DBeaver</b> - Инструмент, позволяющий комфортно работать с БД, а также с разными элементами самой БД. 
8. <b>Github</b> - Среда для сохранения прогресса работы над проектом. И, конечно, сам <b>Git</b> для работы с файлами проекта. 
9. <b>Allure с интеграцией с CI</b> - Отчётность о выполненной работе. CI показывает работоспособность тестов. Allure выдаёт информацию о самой работе каждого теста. Тем самым мы сможем выявить проблемные места в тестах.
 
<br>

___Безусловно, для каждого пункта можно найти и альтернативный вариант. Всё обсуждаемо в пользу лучшего и быстрого выполнения задачи.___
<br>

_Для корректной работы и получения всей информации нужны некоторые допуски_
## <p align="center"> 3. Перечень необходимых разрешений, данных и доступов. </p>
<br>

1. В первую очередь, при выполнении автоматизированного тестирования сайта, необходимо получить разрешение у владельца сайта на выполнение таких работ.
2. Естественно, нужен доступ к БД для проверки корректной записи информации;
3. Джарник, где описана работа создания запроса для менеджеров компании;
4. Если весь этот проект будет проходить на тестовом стенде, то и доступ к тестовому стенду и тестовым сервисам. 
   
   _Даже после получения всех доступов и всей информации имеются риски при автоматизации._

## <p align="center"> 4. Перечень и описание возможных рисков при автоматизации. </p>
<br>

1. Основным риском при автоматизировании этой задачи является <b>время</b> на работу с тестами и последующая проверка при нововведениях.
2. Сроки работы могу увеличиться из-за сложности привязки к локаторам html-объектов. Ведь, неявные приявзки не гарантируют уникальноть и долгую работоспособность автотестов.
3. Гораздо дешевле и быстрее выполнить поставленную задачу мануальному тестировщику, так как данный сервис не нуждается в постоянной доработке или исправлениях. Он прост и статичен.
4. Если всю работу будет выполнять один квалифицированный специалист. Есть вероятность зависимости от него, от его действий, решений и возможностей. (Если он резко уволится всё заного нужно будет делать другому спецу, ну или просто тратить время на понимание проделанной работы)  

_Однако продолжим выполнять поставленную задачу. Чтобы работать с инструментами, описанными выше, нужны специалисты нижеописанных форматов_
## <p align="center"> 5. Перечень необходимых специалистов для автоматизации. </p>
<br>

___Для выполнения поставлненной задачи достаточно и одного QA Инженера. Требуются только некоторые компетенции.___
<br>
_Далее будут перечисленны требования к специалисту._

1. <b>Автотестирование Java</b> - Умение писать автотесты и знать базовые методы и библиотеки для работы с автотестами.
2. <b>Мануальное тестирование</b> - Перед началом создания автотестов, всё это будет проделано руками и с помощью кейсов от ручного тестирования будут создаваться автосценарии. 
3. <b>Настройка окружения</b> - Требуется знание, как работает та или иная операционная система или сет программ для корректной и хорошей проверки на разных устройствах и браузерах.
4. <b>SQL запросы</b> - Создание SQL-запросов в базу данных и возможность предоставить правильную "схему" для корректной проверки данных.
5. <b>GIt</b> - Знающий работу Git-a, который сможет правильно настроить все файлы проекта для последующей работы с ними в интеграции всего сервиса Нетологии.
6. <b>Yml настройка</b> - Настройка корректной работы файлов описания для хорошей проверки и самой работы проекта автотестов. 
<br>
<br>

_Ну и обязательно нужно оценить, сколько по времени займёт выполение всего плана_
## <p align="center"> 6. Интервальная оценка с учётом рисков в часах. </p>
<br>
<p align="center">Для быстрой и хорошей работы нужна достаточно мощная среда разработки. Речь идёт о самом компьютере, на котором всё будет подниматься и разрабатываться.<br>
Учитывая вышеописанные инструменты и методы, немало времени уйдет на поднятие самого SUT, а также работу с Docker-загрузками и правильными настройками окружения в нём.</p> <br>

Примерная оценка этапов:

1. Написание автотестов и создание всех вышеописанных сценариев ~ от 4 до 10 часов;
2. Поднятие всех SUT и настройка окружений в Docker ~ от 2 до 6 часов;  
3. Создание и изучение полных отчётов, документации как артефактов после проверки ~ от 3 до 6 часов (зависит от требований к степени подробности в информации). 
<br>

### <p align="center"> Итого, мы получаем на всю работу примерный интервал времени от 9 до 22 часов работы по данному разработанному плану.</p>
<br>

___В данном плане не рассматривались юзабилити-тесты и привлечение для них дизайнеров, психологов и специалистов аналитики. Всё, конечно, зависит от бюджета и времени. Данная стратегия разработана только для автотестов (возможно, с небольшим вмешательсвом мануального тестирования).___ 
