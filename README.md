# blinadiJSON
Конвектор из JS объекта в html. Часть проекта blinadi. Имеет простой синтаксис. 
##Установка
```bash
    $ npm i blinadijson
```
##Синтаксис
BlinadiJSON имеет простой синтаксис js объекта.
```js
{
    tag: "h1",
    attrs:{id:"HelloNode"},
    content:"Hello, World!"
}
```
* tag - тег элемента. По умолчанию div
* attrs - атрибуты элемента
* content - содержимое объекта. Если объект или массив объектов, то они будут обработаны.
 

#####Вот пример:

``` js
({
    content: [
        {
            tag: "h1",
            content: "Состав группы Nirvana."
        },
        {
            tag: "ul",
            content: "Курт Кобейн,Крист Новоселич,Дэйв Грол".split(',').map(function (el) {
                return {
                    elem: "li",
                    content: el
                }
            })
}]
}) 

```
##API

``` js
blinadiJSON = function (object, callback);

```
* object - Путь до файла.
* callback -  function(html)
 
## Зачем?
Такой формат нужен для создания переопределяемых блоков. Я планирую в дальнейшем написать сборщик проектов в котором будут переопределяемые сущности и такой стиль написания кода будет удобно переопределять. Задача создать очень простой аналог BEM.
##TODO:
* Обучить систему названиям тегов, которые не закрываются
* Написать нормальный readme.
