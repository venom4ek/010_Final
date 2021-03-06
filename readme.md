![img](img/top.png)
# План автоматизации тестирования сервиса "Накопилка"

## Перечень автоматизируемых сценариев

#### В каждом тесте, до заполнения формы будут выполняться повторяющиеся действия, которые необходимо вынести в <br>отдельный этап. Назовем его goToAnketa(данный этап должен содержать в себе список действий для перехода к анкете):
---
> Вариант 1  
> 
> переход на сайт https://alfabank.ru  
> переход в раздел частным клиентам -> вклады -> Накопилка  
> ![img](img/go-to-nakopilka.png)  
> нажатие кнопки "Заполнить заявку" под описанием сервиса Накопительный счет "Накопилка"  
> ![img](img/klick-to-zayavka.png)  

---

<details>
  <summary>Другие варианты перехода на страницу анкеты:</summary>

<details>
<summary>Вариант 2</summary>
переход на сайт https://alfabank.ru

переход в раздел частным клиентам -> вклады  
![img](img/go-to-nakopilka2.1.png)

переход в раздел "Сервисы для накоплений"  
![img](img/go-to-nakopilka2.2.1.png)

переход в раздел "Архивные счета и депозиты"  
![img](img/go-to-nakopilka2.3.1.png)

переход к сервису Накопилка  
![img](img/go-to-nakopilka2.4.1.png)

нажатие кнопки "Заполнить заявку" под описанием сервиса Накопительный счет "Накопилка"  
![img](img/klick-to-zayavka.png)
</details>

<details>
<summary>Вариант 3</summary>
переход на сайт https://alfabank.ru

переход в раздел частным клиентам -> вклады  
![img](img/go-to-nakopilka2.1.png)

переход в раздел "Сервисы для накоплений"  
![img](img/go-to-nakopilka2.2.2.png)

переход в раздел "Архивные счета и депозиты"  
![img](img/go-to-nakopilka2.3.2.png)

переход к сервису Накопилка  
![img](img/go-to-nakopilka2.4.1.png)

нажатие кнопки "Заполнить заявку" под описанием сервиса Накопительный счет "Накопилка"  
![img](img/klick-to-zayavka.png)
</details>

<details>
  <summary>Вариант 4</summary>
переход на сайт https://alfabank.ru

переход в раздел частным клиентам -> вклады  
![img](img/go-to-nakopilka2.1.png)

переход в раздел "Сервисы для накоплений"  
![img](img/go-to-nakopilka2.2.1.png)

переход в раздел "Архивные счета и депозиты"  
![img](img/go-to-nakopilka2.3.1.png)

переход к сервису Накопилка  
![img](img/go-to-nakopilka2.4.2.png)

нажатие кнопки "Заполнить заявку" под описанием сервиса Накопительный счет "Накопилка"  
![img](img/klick-to-zayavka.png)
</details>

<details>
<summary>Вариант 5</summary>
переход на сайт https://alfabank.ru

переход в раздел частным клиентам -> вклады  
![img](img/go-to-nakopilka2.1.png)

переход в раздел "Сервисы для накоплений"  
![img](img/go-to-nakopilka2.2.2.png)

переход в раздел "Архивные счета и депозиты"  
![img](img/go-to-nakopilka2.3.2.png)

переход к сервису Накопилка  
![img](img/go-to-nakopilka2.4.2.png)

нажатие кнопки "Заполнить заявку" под описанием сервиса Накопительный счет "Накопилка"  
![img](img/klick-to-zayavka.png)
</details>

</details>

---

#### После открытия анкеты необходимо провести ряд тестов на позитивные и негативные сценарии формы.

##### Позитивные сценарии  
(т.к. требований к полям у нас нету, мы будем использовать в плане условные, рекомендуемые требования к полям)

- заполнить поле "ИМЯ" (используем валидные имена, двойные имена через тире, а так же валидное имя через букву Ё)
    - Анна
    - Иван
    - Дмитрий
    - Пётр
    - Анна-Мария
    - Вера-Ника
    - Иван-Павел  
    
  ![img](img/name.png)

- заполнить поле "мобильный телефон" (при вводе телефона автоматически проставляется +7. Необходимо ввести 10 цифр после 8(восьмерки). Данный формат был выявлен путем изучения формы)
    - 9123451122
    - 9871236545  
    
  ![img](img/phone.png)

- отметить галочкой поле "Я согласен(а) на обработку персональных данных"  
![img](img/agree.png)

- нажать кнопку "Мы перезвоним"  
![img](img/button-send.png)

- получаем сообщение:  
![img](img/answer.png)

##### Негативные сценарии

при проверке поля "ИМЯ" на негативные сценарии, поле "мобильный телефон" должно быть заполнено валидными данными, поле об обработке персданных должно быть отмечено галочкой.
- пустое поле (система не должна разрешать отправлять форму с пустым полем)
- использование цифр в поле (не допускать имспользовать при заполнении поля цифры)
- одна буква в поле (поле должно иметь как минимум две буквы)
- спецсимволы типа !"№;%:? и т.д. (не доспускать использование спец символов)
- повторяющийся набор букв (не допускать в поле содержание часто повторяющихся букв, к примеру "ппппппппппкккккккрррр")

при проверке поля "мобильный телефон" на негативные сценарии, поле "имя" должно быть заполнено валидными данными, поле об обработке перс данных должно быть отмечено галочкой.
- ввод более 10 цифр (запрет ввода более 10 цифр телефона)
- ввод менее 10 цифр (запрет отправлять форму при введенном номере телефона, где цифр менее 10 посе +7(8))
- ввод букв (запрет на ввод букв)
- ввод спецсимволов (запрет на использование спецсимовлов типа !"№;%: и т.д.)
- пустое поле (запретить отправлять форму, если поле пустое)

проверка поля "Я согласен(а) на обработку персональных данных"
при проверке данного поля, все предыдущие поля "ИМЯ" и "мобильный телефон" должны быть заполнены валидными данными
- оставить поле пустым, не ставить галочку. 

##### при соответствующей проверке на негативные сценарии должны получать соответствующие сообщения об ошибке. так же, рекомендуется, когда поле "Я согласен(а) на обработку персональных данных" остается не отмеченным, при попытке нажать кнопку "Мы перезвоним" подсвечивать тест об обработке персональных данных красным цветом.
---

## Перечень используемых инструментов с обоснованием выбора
### IntelliJ IDEA
Несмотря на то, что IntelliJ IDEA — в первую очередь IDE для Java, она понимает и предоставляет интеллектуальную помощь при написании кода на SQL, JPQL, HTML, JavaScript и многих других языках и позволяет редактировать код, написанный не на Java, внутри строковых литералов Java-кода.

### Java 11
Java — едва ли не единственный язык, на свежих версиях которого можно запускать код, написанный 25 лет назад. Разработчики языка очень серьезно относятся к обратной совместимости, поэтому многие организации выбирают Java в качестве основной технологии, зная, что старый код будет запускаться на JVM еще долгие годы.
Сам язык и решения, которые он предлагает, хорошо документированы и поддерживаются вендорами и некоммерческими организациями, а также отдельными пользователями.

### Gradle
Альтернатива Maven, но:
  - скрипты сборки на Gradle на много короче и удобнее в написании
  - Gradle быстрее maven
  - Gradle был создан для расширяемых многопроектных сборок, и поддерживает инкрементальные сборки, определяя, какие компоненты дерева сборки не изменились и какие задачи, зависимые от этих частей, не требуют перезапуска.
  - в Gradle собраны лучшие качества от Maven и Ant
  - Gradle легко масштабируется
### JUnit 5
  - На сегодняшний день это самая популярная платформа автоматизированного тестирования в мире Java. Как JUnit, так и TestNG поставляются вместе с IntelliJ IDEA: предполагается, что для любого нового Java-проекта необходим фреймворк тестирования. Вполне вероятно, что современные тестовые фреймворки для самых разных языков основаны на идеях, впервые реализованных в JUnit. Культура автоматизированного тестирования, принятая в Java-сообществе, во многом обязана именно этой библиотеке.
  - В виду популярности данной платформы, много поддерживаемых модулей и документации.
### Selenide
  - это обёртка вокруг Selenium WebDriver, позволяющая быстро и просто его использовать при написании тестов, сосредоточившись на логике, а не суете с браузером.
### Lombok
  - библиотека, с помощью которой мы можем сократить количество шаблонного кода, который нужно писать на Java.
### JavaFaker (на усмотрение)
  - библиотека, которую можно использовать для создания широкого спектра реально выглядящих данных.
  - это хороший модуль, но я бы неписал свой список данных, что бы быть уверенным в минимизации рисков при вводе валидных данных.


## Перечень необходимых разрешений/данных/доступов от банка
- Необходимо от Альфа Банк получить разрешение на проведение тестов и их автоматизацию в письменной форме.
- Необходимо уточнение данных по сервису, а точнее требований к полям в анкете:
    1. что можно вводить в поле "ИМЯ"? 
        - Только имя, или полные ФИО, или имя отчество.
        - допустимо ли использование тире "-"
        - минимальное количество букв в поле
        - максимальное количество букв в поле
        - использование транслита
    2. какой формат ввода в поле "мобильный телефон"?
        - только российские номера?
        - ввод с или без 8(восьмерки)?

## Перечень и описание возможных рисков при автоматизации
- Так как тестирование и его автоматизация будет проводиться на продакшне, могут возникнуть риски нагрузки на сервис
- Изменнеие элементов в коде может повлиять на работу автотестов и в конечном счете их придется править/чинить.
- Увеличение времени на тестирование и его стоимость. (Автоматизация тетов имеется смысл, только если проверка модуля будет необходима с какой-то периодичностью.)

## Перечень необходимых специалистов для автоматизации
Для написания автотестов на данный модуль потребуется 1 специалист QA

## Интервальная оценка с учётом рисков (в часах)
Для выполнения автоматизации тестирования, с учетом рисков, потребуется от 4 до 8 рабочих часов, в зависимости от квалификации специалиста QA.