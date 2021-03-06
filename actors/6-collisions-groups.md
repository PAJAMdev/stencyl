## Автоматические Столкновения

Поскольку Stencyl работает на [Box2D](docs/actors/physics), столкновения происходят автоматически, как будто каждый объект существует в “реальной жизни”. Для случаев по умолчанию, чтобы столкновения произошли, с вашей стороны не требуется никаких действий.

[![](http://static.stencyl.com/pedia2/ch3/ragdoll.png)](http://www.stencyl.com/game/play/10715)

## Группы

Однако, что, если вы хотите, чтобы происходили **только определенные столкновения**? Например, если какой-либо враг стреляет пулей, пуля должна столкнуться только с игроком, а не другими врагами.

![](http://static.stencyl.com/help/images/CollisionGroupsIllustration2.png)

Чтобы сделать это, вы должны настроить группы.

Группы - **произвольные наборы Актеров.** Группы обычно названы в честь определенных классов Актеров, таких как “Игроки” и “Враги”.

![](http://static.stencyl.com/pedia2/ch3/collisions/image09.png)

**Столкновения происходят между группами, которые настроены, чтобы сталкиваться друг с другом.** С другой стороны столкновения игнорируются между группами, которые не настроены, чтобы сталкиваться друг с другом.

### Как Настроить Группы
Вы можете установить Groups _(Группы)_ в диалоговом окне Settings _(Настройки)_. Нажмите кнопку **Settings**, чтобы открыть диалоговое окно.

![](http://static.stencyl.com/help/images/Settings-Button-New.png)

Затем, нажмите кнопку **Groups** *(Группы)* (показано ниже), и вы увидите диалоговое окно, которое показывает Collision Groups _(Группы Столкновений)_ в вашей игре, зеленую кнопку Create New _(Создать Новое)_, которая позволяет вам сделать новую Группу, и другие параметры.

![](http://static.stencyl.com/help/images/Settings-CollisionGroupsPic.png)

### Как Добавить Актера в Группу
Вы можете установить свойства столкновений Актера и определить группу, к которой он принадлежит, на странице Properties _(Свойтсва)_ Редактора Актера.

![](http://static.stencyl.com/help/images/Collisions_ActorProperties.png)

### Группы по Умолчанию

Каждая игра Stencyl начинает с набором Групп по умолчанию, которые помогают вам начинать.

У этих групп есть блокировка, рядом с ними (иконка с замком). Группы по умолчанию не могут быть отредактированы или удалены.

- Players _(Игроки)_
- Tiles _(Тайлы)_
- Doodads (Scenery) _(Декорации (Пейзаж))_
- Actors _(Актеры)_
- Regions _(Регионы)_

По умолчанию, Декорации и Регионы никогда не включают физические столкновения. Они могут быть полезными, если вы хотите быстро определить актера, как "не сталкивающийся".

## Shapes *(Формы)*

Как мы говорили в разделе о Анимации, Актеры могут принимать различные состояния Анимации. Для каждого состояния Анимации у Актера могут быть различные границы столкновений.

Например, если персонаж стоит, он может быть более высоким. Если он приседает, он может быть короче.

![](http://static.stencyl.com/pedia2/ch3/collisions/image02.png)

Stencyl поддерживает 3 вида форм границ столкновений: Boxes _(Квадраты)_, Circles _(Круги)_ и Polygons _(Многоугольники)_. (Для Многоугольников разрешены только выпуклые формы!)

![](http://static.stencyl.com/pedia2/ch3/collisions/image01.png)

Вы можете совмещать произвольное количество этих форм, чтобы сформировать более сложные.

![](http://static.stencyl.com/pedia2/ch3/collisions/image04.png)

<div class="note">
В этом примере мы сделали форму “L”, используя 2 квадрата.
</div>

## Sensors *(Датчики)*

Что делать, если вы хотите обнаружить столкновения, без столкновения форм на самом деле? Например, в Tower Defense игре, где башни стреляют по целям, которые находятся в диапазоне.

Вы бы использовали Датчики, чтобы это произошло. Sensors _(Датчики)_ - специальные виды форм (да/нет флаг на любой форме, если быть точным), с которыми Актер **физически не сталкивается** с другими Актерами, но **все еще фиксирует** столкновения.

![](http://static.stencyl.com/pedia2/ch3/collisions/image13.png)

Просто установите этот флажок в правом поле страницы Collision _(Столкновения)_ Актера, чтобы сделать определенную форму Датчиком.

## Обработка Столкновений

**Используйте События**, чтобы обработать столкновения. Под "Обработкой" мы имеем ввиду **отвечать на столкновения логикой.** Например, если Шаровая молния врежется в Марио, то Марио умрет.

Мы поддерживаем 6 видов Событий.

![](http://static.stencyl.com/pedia2/ch3/collisions/image11.png)

Независимо от того, какое Событие вы выберете, обычно будет появляться блок, подобный этому.

![](http://static.stencyl.com/pedia2/ch3/collisions/image06.png)

1st actor _(1-й актер)_ всегда относится к первому актеру в “предложении”. То же самое для 2nd actor _(2-й актер)_.

Для примера...

![](http://static.stencyl.com/pedia2/ch3/collisions/image15.png)

После того, как произойдет этот вид столкновения, 1-й актер будет относиться к Hero _(Герой)_, а 2-й актер будет относиться к Button _(Кнопка)_.

![](http://static.stencyl.com/pedia2/ch3/collisions/image16.png)

Просто в случае, если вы этого не знаете, вы можете перетащить блоки “1st actor” и “2nd actor” и использовать их в любом месте, в пределах этого события.

![](http://static.stencyl.com/pedia2/ch3/collisions/image17.png)

## Больше Обработки Столкновений

Любой вид столкновения, вы можете проверить на 3 дополнительных бита информации.

- С какой стороны произошло столкновение
- Какие группы были вовлечены
- Точки Столкновений (где произошли столкновения)

### Стороны Столкновения
Один момент, следите за тем, что **стороны столкновения основываются на прямоугольной, ограниченной формой** *квадрата*, границе столкновения, так что если вы использовали круг или многоугольник, обратите внимание на результаты.

![](http://static.stencyl.com/pedia2/ch3/collisions/image03.png)

<div class="note">
**Упражнение:** Прыжок на врага сверху один из распространенных случаев использования сторон столкновения. Что-то "растоптали", если на него попали сверху. Вы можете придумать другие случаи использования для сторон столкновения?
</div>

### Группы для Форм Столкновений

![](http://static.stencyl.com/pedia2/ch3/collisions/image12.png)

Что тут делает "форма столкновений”? Это происходит из-за возможности **переопределить группу Актера по умолчанию на основе формы**, так, чтобы определенная форма могла взять другую группу.

![](http://static.stencyl.com/pedia2/ch3/collisions/image10.png)

При работе с блоком “Collision Group for colliding shape” _(Группа Столкновений для формы границ столкновений)_, убедитесь, что **сравниваете группы напрямую**, а не текстовое имя Группы, это может привести к ошибкам и вылетам.

![](http://static.stencyl.com/pedia2/ch3/collisions/image00.png)  
*(Это правильный способ)*

![](http://static.stencyl.com/pedia2/ch3/collisions/image08.png)  
*(Это неправильный способ, не делайте так!)*

Вы можете найти все блоки “getter” _(получать)_ Группы и Типа в Actor > Properties _(Актер > Свойства)_.

![](http://static.stencyl.com/pedia2/ch3/collisions/image05.png)

### Точки Столкновений
Наконец, что не менее важно, вы можете точно зафиксировать, где произошло столкновение. Это применяется не очень часто, но это возможно в случае, если вы хотите создать любую дополнительную логику на основе расположения столкновения.

![](http://static.stencyl.com/pedia2/ch3/collisions/image07.png)

## Итог

- Благодаря физике столкновения происходят автоматически.
- Группы помогают вам фильтровать столкновения, определяя кто с кем сталкивается.
- Используйте датчики, чтобы фиксировать столкновения без "твердых" актеров.
