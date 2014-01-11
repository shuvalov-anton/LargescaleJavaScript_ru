<!-- ### Frequently Asked Questions -->

### Возможно ли обойтись без использования песочницы или фасада?

Хотя архитектура, которую я изложил здесь использует фасад для обеспечения
безопасности, вполне возможно достичь того же с помощью медиатора — сообщения
могут обрабатываться непосредственно ядром без использования фасада. Такая
упрощенная версия все равно будет обеспечивать необходимо низкий уровень
связывания кода, но при выборе этого варианта, нужно понимать, насколько вам
будет комфортно работать с модулями, которые взаимодействуют напрямую
с ядром(медиатором).

### В книге говорилось о том, что модули не должны иметь любых зависимостей, касается ли это библиотек (к примеру, jQuery)

Я специально вынес вопрос о зависимостях от других модулей сюда. Когда
некоторые разработчики выбирают подобную архитектуру, этот выбор подразумевает
определенную использование определенных абстракций от DOM-библиотек. К примеру,
вы можете использовать вспомогательную утилиту, которая будет возвращать нужные
вам DOM-элементы используя jQuery (или dojo). Таким образоб модули все еще могут
удобно работать с DOM, но уже будут это делать не напрямую, жестко используя
конкретную библиотеку. Существует достаточно много способов, как сделать
модули независимыми, но стоит понимать, что, в обсуждаемой нами архитектуре,
идеальные модули не должны иметь зависимостей.

Вы заметите, что иногда при таком подходе становится гораздо легче взять
законченный модуль из одного проекта и перенести его в другой проект с небольшими
дополнительными усилиями. Я должен прояснить, что я полностью согласен с тем, что
иногда намного лучше когда модули вместо определенной части своей функциональности
просто используют другие модули. Как бы то ни было, держите в голове то, что
такие модули, в некоторых случаях, могут потребовать гораздо больше усилий для
переноса в другой проект.

### Я хочу сегодня же начать использовать эту архитектуру. Есть ли какой-то шаблон от которого я бы мог оттолкнуться?

Я планирую написать бесплатный шаблон проекта для этой книги, когда появится
время, но сейчас, наверное, лучший выбор — [«Написание модульного JavaScript»][14] — 
платное учебное пособие написанное Эндрю Бэджис (разаблачу себя: деньги от этой
реферальной ссылки, как и любые другие, полученные от этой книги в пересмотр
материала перед тем, как я порекоммендую его другим)(???). Пособие Андре вклбчает
в себя скринкаст и код. Оно охватывает большую часть идей, которые мы обсуждали
в книге, но в нем используется вместо названия фасада «песочница», как у Николоса 
Закас. Здесь есть обсуждение о том, что работа с DOM-библиотеками в идеале должа
быть реализованна посредством абстстракции, как я и отвечал в предыдущем вопросе.
Эндрю делает ставку на некоторые интересные паттерны, обобщающие работу с 
селекторами DOM, таким образом, в крайнем случае замена библиотеки может быть
выполненна в нескольких коротких строках. Я не говорю, что это правильный или
лучший подход, но я поступаю.

<!-- A: I plan on releasing a free boilerplate pack for this post when time permits
, but at the moment, your best bet is probably the
'[Writing Modular JavaScript][14]' premium tutorial by Andrew Burgees (for
complete disclosure, this is a referral link as any credits received are re-
invested into reviewing material before I recommend it to others). Andrew's pack
includes a screencast and code and covers most of the main concepts outlined in 
this post but opts for calling the facade a 'sandbox', as per Zakas. There's 
some discussion regarding just how DOM library abstraction should be ideally 
implemented in such an architecture - similar to my answer for the second 
question, Andrew opts for some interesting patterns on generalizing query 
selectors so that at most, switching libraries is a change that can be made in a
few short lines. I'm not saying this is the right or best way to go about this, 
but it's an approach I personally also use. -->

### Возможно ли модулям взаимодействовать напрямую с ядром, если это необходимо?

Как заметил раньше Николас Закас, технически, нет никаких причин, мешающих
модулям напрямую обращаться к ядру, это лучше чем ничего. Если вы намерены
строго следовать этой архитектуре, выдолжны следовать ее правилам, либо
правилам более простой архитектуры, которая была описана в первом вопросе.

<!-- A: As Zakas has previously hinted, there's technically no reason why modules
shouldn't be able to access the core but this is more of a best practice than 
anything. If you want to strictly stick to this architecture you'll need to 
follow the rules defined or opt for a looser architecture as per the answer to 
the first question. -->


[14]: http://bit.ly/orGVOL