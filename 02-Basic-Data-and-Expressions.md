# 1 Основные Виды Данных и Выражения

Давайте подумаем о том, какими программами мы сами пользуемся каждый или почти
каждый день. Когда мы пытаемся что-то найти в интернете при помощи поисковиков
типа Google или Яндекс, мы пользуемся программой, которая _принимает_ от нас
поисковый запрос в виде текста и _производит_ поисковую выдачу в виде набора
ссылок на релевантные страницы каких-то сайтов. Когды мы листаем ленту VK, мы
пользуемся программой, которая получает список тех людей, групп и пабликов, на
которые мы подписаны, и производит последовательность постов, которые формируют
фид. Появление рекламных банеров на сайтах --- тоже результат работы программы.
Она потребляет информацию о тех сайтах, на которые вы заходили, о том, когда вы
это делали и где (из какого браузера, с какого IP-адреса), и на основе этого
производит для вас предложение, от которого, как она считает, вы отказаться не
в состоянии. Короче говоря, программы _получают_ и _производят_ информацию.

Информация  --- это термин достаточно абстрактный. Компьютеры получают и
производят то, что называется _данными_. Между ними есть тонкое, но важное
различие. "Наше местоположение" --- понятие достаточно размытое, сайт погоды же
пользуется довольно конкретным _представлением_ этой информации, такой как
название населённого пункта (Туринск, Свердловская обл., ...) или GPS
координатами (типа 58.052506 N, 63.691896 W). Но даже и для этой информации ---
GPS координаты --- есть несколько вариантов представления. Некоторые системы
могут представлять это так, как написано выше: 58.052506 N, 63.691896 W. Другие же
могут обходиться только числами (без букв): 58.052506, -63.691896, условившись о том,
что неотрицательные числа это N, а отрицательные это W. Вы даже можете обойтись
одним единственным числом, если воспользуетесь таким приёмом как «[Нумерация Гёделя](https://ru.wikipedia.org/wiki/%D0%9D%D1%83%D0%BC%D0%B5%D1%80%D0%B0%D1%86%D0%B8%D1%8F_%D0%93%D1%91%D0%B4%D0%B5%D0%BB%D1%8F)».

Таким образом, для того, чтобы писать программы, мы должны понимать, как
работать с конкретными данными. Мы начнём с самых базовых видов данных и
напишем с ними несколько простых программ. В дальнейшем наши программы будут
усложняться, и вместе с этим мы будем вынуждены научиться представлять всё
более и более интересную информацию.

Для того, чтобы писать программы, нам необходимы две вещи: _язык
программирования_, на котором мы будем писать программы, и некоторые
инструменты, с помощью которых мы будем эти программы исполнять. Эти
инструменты называются _средой программирования_ или _средой разработки_. Мы
будем использовать язык, который называется [Pyret](https://pyret.org/). Среда,
в которой мы будем писать и исполнять наши программы, располагается по адресу
`code.pyret.org`, сокращённо --- CPO. Открыв сайт, видим здесь две кнопки.
Чтобы начать программировать, нужно нажать `Open Editor`, т. е. открыть
редактор. Нажав кнопку `Sign In`, можно залогиниться под вашим Google аккаунтом
для того, чтобы вы могли сохранять ваши программы в виде файлов, которые
синхронизируются с Google диском. Нажимаем `Open Editor`. CPO состоит из двух
окон: левое окно называется окном определений, а правое --- окном
взаимодействий.  Знаки больше `>>>` здесь называются "приглашением",
приглашение обозначает то место, где мы сообщаем CPO, что мы хотим выполнить с
помощью Pyret.

## 1.1 Числа

Один из наиболее часто используемых видов данных в программах --- это числа.
Они могут представлять координаты местонахождения, как в примерах выше, возраст
какого-нибудь человека, размер изображения на экране, число результатов
поисковой выдачи, баланс вашего интернет-кошелька, температуру воздуха и т. д.

С числами можно совершать различные операции: сложение

```
>>> 5 + 7
```

вычитание

```
>>> 123 - 456
```

умножение

```
>>> 789 * 987
```

деление

```
>>> 343 / 565
```

Записи такого (и не только такого) вида мы называем _выражениями_ --- так же,
как и в алгебре.

_Указание: Попробуйте убрать пробелы из выражений выше и посмотрите, что
получится, если их исполнить._

Помимо 4 базовых операций: `+` `-` `*` `/` есть ещё множество других операций над
числами, для обозначения которых нет специальных символов. Вместо этого вы
можете записать их, используя синтаксис, знакомый вам из уроков математики, а
конкретно --- алгебры. Например, операция извлечения квадратного корня
называется `num-sqrt`, использовать вы её можете так:

```
>>> num-sqrt(4)
```

Если вы хотите воспользоваться операцией, которая треубет нескольких
параметров, то их следует разделять запятыми. Например, возведение числа `2` в
седьмую степень будет выглядеть вот так:

```
>>> num-expt(2, 7)
```

## 1.2 Выражения и Значения

Прежде чем продолжить, нам нужно несколько прояснить используемую терминологию.
_Значением_ называется результат вычисления _выражения_. Т. е. это то, что уже
нельзя вычислить. Например, `1234 * 5678` не является значением, потому что мы
ещё можем выполнить умножение, а вот `7006652` является значением, потому что
здесь больше нет никаких операций, которые следует выполнить.

Давайте рассмотрим ещё один пример выражений. Как вы знаете, на Луне сила
притяжения меньше, чем на Земле, и вес космонавта, находящегося на Луне, будет
меньше его собственного веса в тот момент, когда он находился на Земле. Если
быть точным, то его вес на Луне будет меньше в шесть раз, т. е. будет составлять одну
шестую от веса земного. Например, если космонавт весил на Земле 80 кг, то на
Луне его вес составит всего 13.(3) кг.

```
>>> 80 * 1/6
```

Почему я здесь привожу этот пример, и в чём его отличие от того, что я
показывал до этого? Здесь используются операции умножения и деления, примеры
использования которых были ранее.

На самом деле, различие есть. В предыдущем примере с делением выражение
выглядело вот так:

```
>>> 1 / 6
```

Мы уже выяснили, что арифметические операции должны отбиваться пробелами с двух
сторон. Так почему здесь, в примере с весом, этих пробелов не было? Почему
Pyret не выдал ошибку на такую запись? Причина заключается в том, что 

```
>>> 1/6
```

это не выражение, а значение, являющееся рациональным числом. Pyret позволяет
нам записывать рациональные числа как в виде десятичных дробей, так и в виде
обыкновенных с использованием того же символа, что и для записи операции
деления.

Таким образом,

```
>>> 1 / 6
```

--- это выражение, потому что у нас здесь есть операция деления, которую ещё
нужно выполнить, чтобы получить значение, а

```
>>> 1/6
```

--- это значение, здесь нет никаких операций, и вычислять поэтому ничего не
нужно.

## 1.3 Переменные для Именования Значений

Зачастую удобнее обращаться к данным не напрямую по значению, а посредством
имён.  Представьте себе, что вы вычислили вес какого-нибудь космонавта на Луне
из предыдущего примера, допустим, он был равен

```
>>> 80 * 1/6
```

13.(3), и использовали это число где-то в своей программе. Если через несколько
недель или, тем более, месяцев вам нужно будет прочитать код этой программы, то
вам, вероятно, потребуется приложить немалые усилия для того, чтобы вспомнить,
откуда это число взялось, и что оно вообще означает. Но если вместо этого числа
вы увидите `astronaut-moon-weight`, вам сразу всё станет ясно (если вы,
конечно, разумеете английский язык; в противном случае, ясно вам станет далеко
не всё и далеко не сразу). Pyret позволяет нам давать имена значениям:

```
>>> astronaut-moon-weight = 13.3
>>> astronaut-earth-weight = 80
```

После чего мы можем использовать их в выражениях:

```
>>> astronaut-earth-weight - astronaut-moon-weight
```

Больше того, мы можем именовать не только значения, но и выражения:

```
>>> weight-diff = astronaut-earth-weight - astronaut-moon-weight
```

Эти имена мы называем _переменными_; опять-таки, так же, как и в алгебре, а
словом _связывание_ будем называть соотнесение некоторого имени с некоторым
значением. В данном случае, имя `astronaut-earth-weight` _связано_ со значением
`80`.

## 1.4 Строки

Одними только числами ограничиться, наверное, невозможно, хотелось бы ещё иметь
хотя бы буквы. Для того, чтобы иметь возможность написать имя какого-нибудь
человека, адрес какого-нибудь сайта или текст сообщения в вашем любимом
мессенджере, в Pyret есть то, что называется _строками_. Строки представляют
собой последовательность печатных символов, заключенных в двойные кавычки.

```
>>> "Privyet, Vasya!"
>>> "что-то очень интересное (нет)"
```

Если вам хочется, вы можете использовать вместо двойных кавычек одинарные:

```
>>> 'Privyet, Vasya!'
>>> 'что-то очень интересное (нет)'
```

Если написать строку в двойных кавычках, содержащую двойные кавычки или строку
в одинарных, содержащую одинарные, то Pyret вас не поймёт:

```
>>> 'вот 'так''
```

Есть два способа разрешить эту проблему. Во-первых, можно заменить кавычки на
другие. Если строка содержалась в одинарных кавычках, то все одинарные кавычки
внутри строки можно заменить на двойные:

```
>>> 'вот "так"'
```

Либо сделать так, как подсказывает вам Pyret:

```
>>> "вот \"так\""
```

--- т. е. написать перед каждыми внутренними кавычками бекслеш и этим самым сказать
Pyret, чтобы он воспринимал эти кавычки не как маркер строки --- открывающий
или закрывающий ---, а как любой другой обычный символ, в данном случае ---
буква или пробел.

## 1.4.1 Многострочные Строки

Иногда бывает нужно иметь возможность написать текст, разбитый на несколько
строк, когда символов слишком много и всё написананое в одну строку выглядит
громоздко. Если попытаться сделать это так:

```
>>> 'перенести
>>>  строку'
```

то Pyret посчитает, что вы, возможно, не закончили запись строки `'перенести`,
и вам необходимо добавить недостающую кавычку. Однако, он также подскажет вам,
что нужно сделать, если вы хотите сделать многострочную строку. Для этого,
говорит он, вместо кавычки используйте тройные обратные кавычки. Этот символ
расположен на той же клавише, где и буква Ё.

```
>>> ```Съешь ещё этих мягких французских булок, 
>>> да выпей же чаю```
```

Pyret напечатал между словами `\n`, это так обозначается символ переноса строки.
Мы можем сделать то же самое, уже не пользуясь тройными обратными кавычками:

```
>>> "перенести\nстроку"
```

## 1.4.2 Операции на Строках

Со строками, как и с числами, можно тоже выполнять разные операции. Их можно
склеивать, для чего используется тот же символ, что и для сложения чисел:

```
>>> "кон" + "кат" + "енация"
```

Можно узнать длину строки, т. е. количество символов, из которых она состоит:

```
>>> str = "кон" + "кат" + "енация" 
>>> string-length(str)
```

Можно выбрать из строки некоторую подстроку:

```
>>> string-substring(str, 0, 6)
```

## 1.5 Булевы Значения

Чтобы удостовериться в том, что две строки

```
>>> ```перенести
      строку```

>>> "перенести\nстроку"
```

равны, нам нужно своими собственными глазами посмотреть на результат исполнения
двух этих выражений и увидеть в правом окне, что они в точности совпадают. Эту
задачу --- проверку равенства --- мы можем перепоручить Pyret.

В языке для ответов на вопрос о равенстве есть два значение: `true` и `false`.
Называются они _булевыми значениями_ в честь [Джорджа
Буля](https://ru.wikipedia.org/wiki/%D0%91%D1%83%D0%BB%D1%8C,_%D0%94%D0%B6%D0%BE%D1%80%D0%B4%D0%B6),
который считается одним из основателей математической логики.

Для проверки равенства двух значений используется двойной знак равенства:

```
>>> 1 == 1
  true
>>> 1 == 2
  false
```

## 1.5.1 Другие сравнения

Проверять можно не только равенства, но и другие отношения.

```
>>> 1 <= 2
  true
>>> 1 > 3
  false
```

Можно так же сравнивать и строки:

```
>>> "a" < "b"
  true
>>> "a" >= "b"
  false
>>> "раз" > "два"
  true
```

Для сравнения строк используется лексикографический порядок, где в качестве
алфавита используется ASCII.

Булевы значения так же поддаются сравнению:

```
>>> true == false
  false
>>> false == false
  true
>>> true > false
```

## 1.5.2 Другие булево-значные операции

Почти для каждого типа данных есть какие-то булево-значные операторы. Например,
для строк:

```
>>> s = 'qwerty'
>>> string-contains(s, 'QWE')
  false
>>> string-contains(s, 'qwe')
  true
```

## 1.5.3 Комбинируем булевы значения

Часто мы хотим принимать решения на основе не одного, а нескольких булевых
значений. Например, я пойду гулять, если, во-первых, на улице хорошая погода, а
во-вторых, у меня есть свободное время.

Для того, чтобы комбинировать такие условия, в Pyret есть три операции: `and`,
`or`, `not`.

Вот как их, например, мы можем использовать:

```
>>> (1 < 2) and (2 < 3)
  true
>>> (1 < 2) and (3 < 2)
  false
>>> (1 < 2) or (2 < 3)
  true
>>> (3 < 2) or (1 < 2)
  true
>>> not(1 < 2)
  false
```

## 1.5.4 Используем булевы значения

Из булевых значений мы умеем получать булевы значения при помощи трёх
логических операций. Для того, чтобы на основе значений `true` или `false` получать
какие-то другие данные, в Pyret есть так называемое _условное выражение_. Оно
имеет следующий вид:

```
  if <булево-ЗначноеВыражение>:
    <Выражение1>
  else:
    <Выражение2>
  end
```

Например:

```
  msu-founding = 1755
  spsu-founding = 1724
  if spsu-founding < msu-founding:
    "СПбГУ старше МГУ"
  else:
    "МГУ старше СПбГУ"
  end
```

Можно заметить, что в этой программе есть ошибка. Если бы годы основания МГУ и
СПбГУ совпали, то значением выражения `spsu-founding < msu-founding` было бы
`false`, потому что никакое число не меньше самого себя. Для того, чтобы учесть
этот случай, воспользуемся расширенной версий условного выражения:

```
  msu-founding = 1755
  spsu-founding = 1724
  if spsu-founding < msu-founding:
    "СПбГУ старше МГУ"
  else if spsu-founding == msu-founding:
    "СПбГУ и МГУ основаны в один и тот же год"
  else:
    "МГУ старше СПбГУ"
  end
```

## 1.6 Исполнение посредством упрощения выражений

Теперь давайте немного поговорим о том, как Pyret получает из выражений
значения. Этот процесс называется _исполнением_.

Первый шаг исполнения --- это замена всех имён на значения, которые с ними
связаны:

```
  if 1724 < 1755:
    "СПбГУ старше МГУ"
  else if 1724 == 1755:
    "СПбГУ и МГУ основаны в один и тот же год"
  else:
    "МГУ старше СПбГУ"
  end
```

Следующий шаг --- исполнение `if`-выражения:

```
  if true:
    "СПбГУ старше МГУ"
  else if 1724 == 1755:
    "СПбГУ и МГУ основаны в один и тот же год"
  else:
    "МГУ старше СПбГУ"
  end
```

Если значение этого выражения --- `true`, то всё конструкция `if-else
if-else-end` заменяется на

```
  "СПбГУ старше МГУ"
```

Если бы вычисленное значение `if`-выражения было равно `false`, то следующим
шагом Pyret вычислит значение `else if`-выражения:

```
  if false:
    "СПбГУ старше МГУ"
  else if false:
    "СПбГУ и МГУ основаны в один и тот же год"
  else:
    "МГУ старше СПбГУ"
  end
```

В случае `true` вся конструкция заменяется на соответствующее выражение. Но т.
к. значение опять равно `false`, мы переходим к последней части этой
конструкции и заменяем всё это на выражение `"МГУ старше СПбГУ"`, потому как
ветка `else` исполняется тогда и только тогда, когда не выполнилось ни одно
предшествующее условие.

## 1.7 Изображения

В Pyret, в отличие от многих других языков базовым типом данных, помимо чисел и
строк, являются ещё и картинки. Для того, чтобы начать ими пользоваться, нужно
попросить Pyret предоставить нам операции по работе с ними, написав:

```
  include image
```

После чего можно уже нарисовать какие-нибудь фигуры, например, красный круг и
белый треугольник:

```
  red-circ = circle(60, "solid", "red")
  white-rect = rectangle(300, 200, "solid", "white")
```

Мы можем некоторым образом комбинировать картинки так же, как мы комбинировали
числа, строки и булевы значения. Например, операция `overlay` поместит одно
изображение поверх другого:

```
  overlay(red-circ, white-rect)
```

чтобы получить флаг Японии.

Подобным же образом можно разместить одно изображение над другим:

```
  white-circ = circle(50, "solid", "white")
  above(white-circ, white-circ)
  above(white-circ, above(white-circ, white-circ))
```

Возвращаясь к японскому флагу, надо сказать, что числовые параметры выбраны
неслучайно. Существуют определённые правила, которым изображение флага должно
следовать. Например, ширина и высота должны быть обязательно в пропорции 3 к 2
(отсюда и наши числа --- 300 и 200), диаметр круга должен составлять 3/5 от
общей высоты флага. Если нам захочется нарисовать флаг побольше, нам будет
нужно с осторожностью менять параметры, чтобы соблюсти все эти правила! Вместо
этого мы можем завести переменную, назовём её `unit`, которая будет обозначать
"единицу" размера флага, и на основании этой перменной уже исполнять все
необходимые вычисления.

```
  include image
  
  unit = 50
  bg-width = unit * 3
  bg-height = unit * 2
  circ-radius = 1/2 * 3/5 * bg-height
  
  red-circ = circle(circ-radius, "solid", "red")
  white-rect = rectangle(bg-width, bg-height, "solid", "white")
  overlay(red-circ, white-rect)
```

Теперь нам намного проще вносить изменения в нашу программу, достаточно лишь
изменить значение переменной `unit`, и при каждом запуске программы все
необходимые параметры будут вычисляться автоматически. (Поменять `unit` сначала
на 50, потом на 200.) 

## 1.8 Приближённые числа

Перед тем как завершить обзор базовых типов данных, нужно ещё кое-что сказать
про числа. Числовые примеры, которые были продемонстрированы, были подобраны
специально так, чтобы не было видно то, как компьютеры на самом деле обращаются
с числами. Pyret по большей части это маскирует, но всё-таки не полностью.
Чтобы это увидеть, можно, например, посчитать квадратный корень из двух:

```
>>> num-sqrt(2)
```

Что мы здесь видим? Pyret нам хочет сказать, что результат вычисления не
является точным ответом на наш вопрос. Это очевидно, потому что корень из двух
не является рациональным числом и не может быть представлен в виде конечной
десятичной дроби. Для того, чтобы сообщить о том, что это лишь примерный ответ,
Pyret добавляет значок волны "~" перед числом. У этих приближённых чисел есть
одно замечательное свойство: всякий раз, когда в вычислении задействуют
приближённое число, результат всего вычисления становится приближённым числом.

```
>>> ~1 + 2
```

Иногда это выглядит довольно комично:

```
>>> num-sqrt(2) - num-sqrt(2)
```

Мы знаем, что если из какого-нибудь числа вычесть это самое число, то результат
всегда равен нулю, независимо от того, какое число мы выбираем. Но Pyret не
такой умный, как мы с вами, он таких тонкостей не знает, и поэтому нам говорит,
что если из корня из двух вычесть корень из двух, то получится не нуль, а
_примерно нуль_.

Давайте рассмотрим такое вычисление:

```
>>> num-sqrt(2)
>>> num-sqrt(2) + 1
```

Обратите внимание на цифры после точки. Было бы разумно предположить, что два
эти числа будут отличаться только первой цифрой, но во втором числе куда-то
подевалась последняя единица.

А если мы захотим получить исходное число, вычислив

```
 >>> (num-sqrt(2) + 1) - 1
```

то получим число, явно отличающееся от корня из двух `num-sqrt(2)`. Мы можем
спросить Pyret, два эти числа суть одно и то же число или всё же разные?

```
 >>> ((num-sqrt(2) + 1) - 1) - num-sqrt(2)
```

Здесь появляется ещё какая-то буква "e". Эта нотация используется для
обозначения экспоненты. Т. е. данное число можно представить примерно как 2.2 *
10^{-1}. Это число, конечно, очень маленькое, но всё же это не ноль, которого
мы ждали. Итак, что мы имеем: мы взяли корень из двух, прибавили к нему
единицу, затем вычли из получившейся суммы единицу, из этого вычли корень из
двух, и в результате получили число, которое не равно в точности нулю.

Поскольку приближённые числа такие хрупкие в обращении, Pyret сделает
предупреждение, если вы попытаетесь использовать с ними операцию равенства:

```
>>> 1 == ~1
```

Pyret не уверен: `~1` представляет собой некоторое значение, которое примерно
равно `1`, но может быть и в точности быть единицей, или же `~1`это что-то
близкое к единице, но единицей не являющееся (как в примере с корнем из двух
--- мы знаем, что в действительности результат равен в точности нулю). Pyret не
считает

```
>>> 1 == ~1
```

ни верным (`true`), ни ложным (`false`), а считает скорее ошибкой, о чём и
сообщает нам в правом окне. В дальнейшем мы узнаем, как сравнивать такие числа.
