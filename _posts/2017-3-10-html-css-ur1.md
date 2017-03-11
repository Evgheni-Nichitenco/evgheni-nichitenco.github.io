---
layout: post
title: HTML CSS. Уровень 1
---
Конспект прохождения уроков "Специалист", которые вел Сергей Алмазов.

* Магия Emmet:

```
div>span.mytext{Текст внутри span}

ul>li*4>a*3

.wrapper>header+main+footer

a.button{ссылка}*3

ul.menu>li.menu-element*4>a.menu-link

header+nav+main+footer

ul.menu>li.menu-element*4>a.menu-link{Ссылка}

.parent>a.child{Ссылка}
```
------------

**rectangle** - прямоугольник  
**round**     - круг  
**triangle**  - треугольник  
**solid**     - сплошная линия  
**wrapper**   - обертка  
**charset**   - кодировка

------------

* Прозрачность

```
rgba(255, 255, 255, 0.8)
a - альфаканал
0 - абсолютно прозрачный объект
1 - абсолютно непрозрачный объект
```

* Первые 6 строчек, которые надо писать в любом КСС файле. Сброс стилей:

```
    * {
    margin: 0;
    padding: 0;
    border: 0;
    font-size: 0;
    }

```

-------------

Параметр **auto** может быть только у margin-right и margin-left (не у top и bottom).

-------------

**ctrl+ /**   - закомментирование в Visual Studio Code

------------

### Видео 01-1
------------
* Гиперссылка
```
<a href="adres">Eto ssilka</a>
```

* Внутренние гиперссылки

    ```
    <a href="#anchor">Это внутренняя ссылка</a>

    Якорь:
    <a name="ancor"></a>
    Слово 'ancor' произвольное!
    ```

    ```
../ Подняться на один уровень выше
../../ Подняться на два уровня выше
```

* Прикрепление файла со стилями

```
<link rel="stylesheet" href="styles.css"
```

* Псевдоклассы и псевдоэлементы

```
.prazdnik:hover {
	color:red;
}

.prazdnik:active {
	color:blu;

}
```

```
aside:after {
	content: "Контент"
}              присоединение контента после содержимого тега с классом aside

aside:before {
	content: "Контент"
]		присоедниение контента до содержимого тег с классом aside
```

* Псевдоэлементы: "after", "before", свойство "content":

    ```

    https://codepen.io/nichitenco/pen/zrWBjd

    ```

* Свойства шрифтов:

```
font-family    Семейство шрифтов

font-style     Курсив

font-variant   Капитель

font-weight    Жирность

font-size      Размер шрифта
```

* Картинка в качестве фона

```
body {
	background-image: url("kartinka.jpg");
	background-repeat: no-repeat;			убираем мозаику (чтобы картинка не повторялась)
	background-attachment: fixed;	 фиксируем картинку (снимаем прокрутку картинки)
  background-size: cover; 	растягиваем на весь фон
}

```
Внутренний отступ увеличивает размер блока: размер + паддинг:

```
padding: 20px
```

Скругление углов:

```
border-radius: 10px
```

Центрирование блока по горизонтали:

```
margin: 60 auto
```

Paint - хорошая программа чтобы быстро посмотреть палитру и выбрать ргб значения цвета.


```
background-color: rgb (160, 63, 182);
		  rgba (160, 63, 182, 0.5)
```

Прозрачность (альфа-канал) задается значениями от 0 до 1.


При использовании псевдоэлемента :hover можно изменяющемуся классу назначить
время на плавное изменение Вписать в класса элемента:

```
transition: 2s backgroud
```


* Изучение работы со шрифтами, бэкграундом, контейнером, псевдоклассами

    ```
    https://codepen.io/nichitenco/pen/wMmzPo
    ```
------------------

* Списки, CSS свойства для списков
    ```
    https://codepen.io/nichitenco/pen/obdgJr
    ```

* Объединение ячеек, заголовки ячеек

    ```
    https://codepen.io/nichitenco/pen/MKGQqL
    ```

* Табличная верстка

    ```
    https://codepen.io/nichitenco/pen/gPzwPN
    ```


* Формы и их дополнительные атрибуты

    ```
    https://codepen.io/nichitenco/pen/rxvvyG
    ```

* Бэкграунд, отступы внутренние и внешние, закругление углов

    ```
    https://codepen.io/nichitenco/pen/mVLybo
    ```

* Работа с Koala

```
    Перетаскиваем папку с файлом CSS в программу Коала.
    Щелкаем в программе "Обновить". Должен появиться файл styles.min.css
    Переименовать файл styles.css -> styles.css
    Нажать "обновить" в Коале
    Щелкаем по файлу styles.scss в Koala. Ставим галочку Avtocompile
    Работаем постоянно в файле styles.scss
    В процессе работы Коала самостоятельно будет компилировать его в styles.css и указывать на ошибки
    Файл styles.min.css  сжатый код CSS
```

* HTML5 тэги

```
    <header> Шапка сайта

    <nav> Блок для главного меню

    <aside> Боковая панель

    <main> Основной блок содержимого

    <footer> Подвал сайта

    <article> Статья

    <section> Секция сайта

```
