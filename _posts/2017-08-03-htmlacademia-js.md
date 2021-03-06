---
layout: "post"
title: "HtmlAcademia - Базовый JavaScript"
date: "2017-08-03 23:17"
tags:
  - js
---
*document* - самый верх дерева ДОМ

# Три главных слова JS

**1**

## querySelector()

Метод для поиска элементов. Возвращает элемент из ДОМ-дерева, соответствующий CSS-селектору.(метод)

*document.querySelector(".user-block");*
-Поиск по документу элемента с классом .user-block

**Найдем ссылку вход:**
```
<html>
  <body>
    ----
    <a class="login" href="#">Вход</a>
    ----

    <script>
      var link = document.querySelector(".login");
    </script>

  </body>
</html>

```

**querySelectorAll**

Возвращает все элементы из ДОМ-дерева, соответствующие CSS-селектору document.querySelectorAll(".button");
вернет список всех элементов с классом button.

**Сообщение в браузере**

*console.log("Сообщение в консоли браузера");*

*2*

## addEventListener ##

Метод для отлова диких событий. Отлавливает событие элемента и выполняет переданную функцию

*link.addEventListener("clik", function(){});*<br>
*link* - элемент, у которого мы будем ловить событие.<br>
*addEventListener* - метод для отлова события<br>
*clik* - событие, которое мы хотим поймать ("клики")<br>
*function(){}* - фунция, которая будет выполняться каждый раз, когда мы ловим событие "клик".

**Какие события можно поймать**
```
Mouse events:
cleck,
dbclick,
keydown - нажатие клавиши,
keypress - удержание клавиши,
keyup - отпускание клавиши,
mouseover,
mouseout

Focus events:
blur,
focus,
focusin,
focusout,
change

Form events:
reset,
submit
```

**Посмотреть документацию, какие бывают "события":**
```
developer.mozilla.org/ru.docs/Web/Events
```
```
<html>
  <body>
    ----
    <a class="login" href="#">Вход</a>
    ----

    <script>
      var link = document.querySelector(".login");

      link.addEventListener("click", function(){
	console.log("Клик по ссылке вход");
	});
    </script>

  </body>
</html>
```

**Остановка действия по умолчанию:**

```
<html>
  <body>
    ----
    <a class="login" href="#">Вход</a>
    ----

    <script>
      var link = document.querySelector(".login");

      link.addEventListener("click", function(event){
	event.preventDefault();
	console.log("Клик по ссылке вход");
	});
    </script>

  </body>
</html>
```

*event* - здесь произвольная переменная в которую фунция передает информацию о событии.
*preventDefault();* - производит прерывание деиствия браузера "по умолчанию", которое он должен был сделать после клика. После этого выводится надпись в консоли "Клик по ссылке вход"

Теперь найдем на странице модальное окно "всплывающий поп-ап":
Оно находится в самом низу страницы и скрыто с помощью displey: none
Скрипт должен его найти и изменить его свойство displey для того чтобы попап стал видимым.
```
---
<div class=""modal-content>
  ---
</div>

<script>
  var popup = document.querySelector(".modal-content");
</script>
```

**3**

## classList ##

Набор методов для управления классами элементов

**Пример:**

*element.classList.add("modal-content-show");*

*element* - элемент, которому добавляем новый класс<br>
*classList* - свойство, содержащее в себе методы для работы с классами<br>
*add*  - добавить<br>
*add("modal-content-show")* - метод добавления класса<br>
*modal-content-show* - класс, который добавляется к элементу "element"<br>


**Что еще может делать classList:**

*element.classList.add();* Добавляет класс<br>
*element.classList.remove();* Удаляет класс<br>
*element.classList.toggle();* Переключает класс (если есть - удаляет, если нет - добавляет)<br>
*element.classList.contains();* Сообщает, есть ли такой класс у элемента<br>

**Покажем модальное окно:**

```
<style>
  .modal-content {
      display:none;
      }

  .modal-content-show {
      display: block;
     }
</style>
---
<div class=""modal-content>
  ---
</div>

<script>
  var popup = document.querySelector(".modal-content");
  popup.classList.add("modal-content-show");
</script>
```

**Соединяем скрипт полностью вместе:**

```
<script>
  var link = document.querySelector(".login");
  var popup = document.querySelector(".modal-content");

  link.addEventLister("clik", function(event){
    event.preventDefault();
    popup.classList.add("modal-content-show");

</script>
```

**А как закрыть модальное окно?**

```
<div class="modal-content">
  <button class="modal-content-close" type="button">Закрыть</button>
</div>

<script>

  var close = document.querySelector(".modal-content-close");

  close.addEventListener("click", function(event) {
    event.prevetDefault();
    popup.classList.remove("modal-content-show");
  });

</script>
```

**Окончательный вид скрипта:**

```
<script>
  var link = document.querySelector(".login");
  var popup = document.querySelector(".modal-content");
  var close = document.querySelector(".modal-content-close");

  link.addEventLister("clik", function(event){
    event.preventDefault();
    popup.classList.add("modal-content-show");
    });

  close.addEventListener("click", function(event) {
    event.prevetDefault();
    popup.classList.remove("modal-content-show");
  });

</script>
```
-------------------------------
```
Кнопка появления и скрытия модального окна:

https://codepen.io/nichitenco/pen/ZJBagw
```
```
Всплывающее окно для ввода логина:

https://codepen.io/nichitenco/pen/mMOwWe
```

**var login = popup.querySelector("[name=login]");**
Поиск внутри элемента с селектором "popap", найти внутри него элемент с именем
"login" и при присвоить его переменной по имени "login'.

**login.focus();**
когда элемент будет найден, на нем будет наведен фокус.


**console.log(password.value);**
value - свойство, которое позволяет узнать значение, которое в данный момент есть у переменной (в данном случае у password).

------------------------------

**if (!login.value) {...}**
if Оператор условия: если условие в скобках верное, то запускается код в фигурных скобках.
login value - Проверяем существование значения поля login
! - Знак ! переворачивает условие наоборот: значение отсутствует у поля login

--------------------------

Условие:
&& - логическое "и"
|| - логическое "или"

-----------------------

Условие:

**if (!login.value || !password.value) { ... }**

1.Оператор условия: если условие в скобках верное, то запускается код в фигурных скобках.
2. Значение отсутствует у поля login или у поля password (или у обоих сразу).

**localStorage - Хранение данных в браузере**

-------------------------------------

**localStorage.setItem("name", "keks");**

localStorage - Глобальный объект для работы с хранилищем.
setItem - Метод для создания новой записи в хранилище.
"name" - Ключ к записи
"keks" - Значение записи

----------------------------------
Какие есть методы у хранилища:

**localStorage.getItem();**
Получает значение ключа из хранилища

**localStorage.setItem();**
Создает новую запись в хранилище.

**localStorage.removeItev();**
Удаляет запись из хранилища

**localStorage.clear();**
Полностью очищает хранилище
-------------------------

else - иначе

**localStorage.setItev("login", login.value);** - сохранить в Локал Стораж то что
пользователь в ключе "логин" то что находится в текущем значении  login.value

--------------------

window - Глобальный объект, занимается окном, внутри которого находится DOM - дерево

**Закроем модальное окно по ESC:**
```
window.addEventListener("keydown", function(event) {
	if (event.keyCode === 27) {
	if (popap.classList.contains("modal-win-show")) {
	popap.classList.remove("modal-win-show);
	}
    }
});
```

Отслеживание нажатие клавиш в окне браузере
У "event" есть свойство "keyCode". В Этом свойстве находится индитификатор клавиши,
которая была нажата.
27 - идентификационный номер клавиши эскейп

**contains** - проверяет, есть ли этот класс у этого элемента. Событие которое говорит либо "да" либо "нет".

**keycod.es** - сайт который показывает нажимаемые клавиши

**submit** - событие отправки формы любым способом

-------------

**Анимация, плавно выкатываем форму на экране (CSS):**

@keyframes - описываем нашу анимацию
bounce - название нашей анимации (произвольное)

Анимация, потрясем форму:

https://codepen.io/nichitenco/pen/WEYxjK
