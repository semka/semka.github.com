---
title:     О подсветке синтаксиса
author:    Semyon Novikov
published: 2012-06-14 08:05:23YEKT
---

7-8 июля я впитывал мудрость на семинаре <a href="http://brainwashing.pro/ios-dev">Brainwashing iOS</a> от волшебных <a href="http://evilmartians.ru/">Злых Марсиан</a> и совершенно неожиданно встретил там Льва Валкина. Познакомились лично, было очень-очень приятно. Он даже сделал вид, что понял кто я такой, когда я с ним заговорил, за что нижайший поклон :)
(К слову хочется еще раз сказать спасибо марсианам и ребятам из AnyVoid и Zeptolab за отличные выходные проведенные с пользой)

За обедом выяснилось, что у Льва весьма, гм, своеобразный стиль работы с компьютером. Я могу сейчас наврать, но если что он может сам меня поправить. Тезисно самое интересное лично для меня:

* Он использует vi для редактирования почти всего
* Он не использует подсветку синтаксиса

## Редактор

Насколько я понял решение Льва использовать vi обусловлено тем, что он стандартен, есть везде и предлагает вполне разумное соотношение сложность/возможности. Когда-то давно случилась <strike>травма</strike> профдеформация связанная с работой на технике Sun с хардкорными юниксами и все такое. Бывает.

Я и сам пользовался vim&#39;ом довольно долго перед тем как перейти на emacs, с которым я провел шесть незабываемых лет. Но за последний год у меня случилось два редакторных кризиса результатом которых стало то, что я больше не емаксер и перешел на Sublime Text 2. Претензия к емаксу одна: мне надоело конфигурировать редактор. Когда папка с конфигами стала больше походить на небольшой репозиторий с каким-то софтом я задумался. Ведь даже при таком объеме кастомизации все равно что-нибудь не работает или отваливается время от времени.


Sublime Text 2 в этом вопросе выглядел почти панацеей, его не надо конфигурировать, он просто работает. Так что я остановился именно на нем. Ну до позапрошлой субботы.&nbsp;Сейчас есть желание перейти на что-то вечное, типа того же vi или emacs, но использовать самый необходимый минимум конфигурации. Во-первых это бесплатно, во-вторых оно снимает проблемы с конфигурацией. Есть резонное возражение, мол настрой один раз как надо и используй всю жизнь. Не работает. Каждый год выходит что-то новенькое, новые версии библиотек, el-get, потом пэкэджи, потом ломают nXhtml, потом чинят и снова ломают. А ты раз в месяц чинишь свой конфиг воскресным днем, чтобы поработать в понедельник.

Собственно в 2006 году я бросил vim по <strike>религиозной</strike> совершенно дурацкой причине: emacs написан на лиспе. Я тогда думал, что это очень круто. О, идиот и не догадывался, <i>что</i> это за лисп. Теперь я попробую вернуться. Во-первых я его немного знаю, во-вторых он есть везде.

## Подсветка синтаксиса

А вот с подсветкой синтаксиса у меня давние личные счеты. Я уже ставил подобный эксперимент два года назад, но тогда я поставил просто неконтрастную тему в которой было всего два цвета: черный и тёмно-серый на белом фоне. И вот зачем я это делал: подсветка синтаксиса играет примерно ту же роль, что и форматирование текста, помогает быстро видеть сущности.

Но как и со всем хорошим с ним нельзя перебарщивать, после некоторого времени работы с раскрашенным текстом качество понимания начинает падать за счет снижения внимательности. Программист моментально принимает решение о некотором фрагменте кода на основании его цвета и выводы далеко не всегда получаются правильными.
Мне на глаза попалось <a href="http://www.unicog.org/publications/ReadingDegradedWordsDorsalVentral_Neuroimage2008.pdf">исследование</a> показывающее, что отдел мозга &laquo;которым человек учится читать&raquo; продолжает работать и во взрослом состоянии, но активизируется только тогда, когда читать трудно. В то же время качество осознания текста ощутимо повышается когда эта система работает.
Короче говоря тексты, которые сложно читать усваиваются лучше. Вот такой парадокс, впрочем довольно легко разрешимый: уровень внимания должен быть выше когда текст тяжело читать, кроме того увеличивается &laquo;цена ошибки&raquo; чтения. Мозг понимает, что если он сейчас прочитает этот текст неправильно, то нужно будет его <i>перечитывать.</i>

Таким образом вполне вероятно, что если код трудно читать, то он будет прочтен внимательнее (конечно при условии, что код в любом случае нужно прочитать). Я специально не написал &laquo;лучше&raquo;, рука не поднялась. Есть два очевидных способа &laquo;испортить&raquo; код чтобы лучше его понимать:

* Сломать форматирование
* Отключить подсветку синтаксиса

Первый вариант это настоящий фашизм. Хотя я думаю даже Гитлер бы так не поступил, это слишком подло. Дело в том, что проблемы с вниманием лично у меня, а не у всех людей читающих мой код. Я уверен, что нормальные люди способны внимательно читать код с подсветкой синтаксиса и самым клевым форматированием на свете. Это только я не могу.

Примерно этим же я руководствовался два года назад делая неконтрастную тему. Но практика показала, что даже минимальное цветовое различение сущностей в коде работает <i>точно так же</i> как и полная подсветка, разве что со стороны выглядит загадочно и круто.

Я, кстати, не знаю почему Лев её не включает, сомневаюсь, что у него проблемы с вниманием :) Кроме того, теперь у меня везде одинаковая цветовая схема &mdash; никакой. Это так приятно.