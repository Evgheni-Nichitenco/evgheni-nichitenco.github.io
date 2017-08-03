---
layout: "post"
title: "HtmlAcademia - Базовый JavaScript"
date: "2017-08-03 23:17"
tags:
  - js
---
*document* - самый верх дерева ДОМ

**Три главных слова JS**

*1*

**querySelector()**

Возвращает элемент из ДОМ-дерева, соответствующий CSS-селектору.(метод)

*document.querySelector(".user-block");* - Поиск по документу элемента с классом .user-block

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

**addEventListener**

Отлавливает событие элемента и выполняет переданную функцию

*link.addEventListener("clik", function(){});*<br>
*link* - элемент, у которого мы будем ловить событие.<br>
*addEventListener* - метод для отлова события<br>
*clik* - событие, которое мы хотим поймать ("клики")<br>
*function(){}* - фунция, которая будет выполняться каждый раз, когда мы ловим событие "клик".

Посмотреть документацию, какие бывают "события":
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

**classList**  - набор методов для управления классами элементов

Пример:<br>
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
