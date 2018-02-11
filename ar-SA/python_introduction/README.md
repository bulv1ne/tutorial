# مقدمة إلى بايثون

> هذا القسم يستند على دورة تعليمية من فتيات الجزر المهووسات (https://github.com/ggcarrots/django-carrots).

دعنا نكتب بعض التعليمات البرمجية!

## موجه بايثون

> للقراء في المنزل: تم تغطية هذا الجزء في فيديو [ أساسيات بايثون: عدد صحيح، سلاسل، قوائم، متغيرات وأخطاء ](https://www.youtube.com/watch?v=MO63L4s-20U).

لبدء العمل ببايثون، نحتاج إلى فتح *سطر الأوامر* على جهاز الكمبيوتر. يجب عليك ان تعرف كيف تفعل ذالك - لقد تعلمته في [مقدمة لسطر الأوامر](../intro_to_command_line/README.md).

عندما تكون مستعدا، اتبع الإرشادات أدناه.

نريد فتح وحدة تحكم بيثون، لذلك اكتب في `python` على ويندوز أو `python3` على نظام التشغيل ماك / لينوكس واضغط على `enter`.

{% filename %}command-line{% endfilename %}

    $ python3
    Python 3.6.1 (...)
    Type "help", "copyright", "credits" or "license" for more information.
    >>>
    

## أمر بايثون الأول الخاص بك!

بعد تشغيل الطلب في بايثون ، تغير الطلب إلى `>>>`. وهذا يعني بالنسبة لنا الآن انه يمكننا استخدام الأوامر في لغة بايثون فقط. ليس عليك الكتابة في `>>>` بايثون سيقوم بذالك.

إذا كنت ترغب في إنهاء وحدة تحكم بايثون ، فقط اكتب `exit()` أو استخدام الاختصار `Ctrl + Z` ل Windows و `Ctrl + D` ماك/لينكس. فإنك لن ترى `>>>`أبدا.

في الوقت الحالي، نحن لا نريد الخروج من وحدة تحكم بايثون. نريد أن نتعلم المزيد. دعونا نبدأ بكتابة بعض الرياضيات، مثل `2 + 3` و `enter`.

{% filename %}command-line{% endfilename %}

```python
>>> 2 + 3
5
```

لطيف! انظر كيف برز الجواب؟ بيثون يعرف الرياضيات! يمكنك محاولة الأوامر الأخرى مثل:

- `4 * 5`
- `5 - 1`
- `40 / 2`

لإجراء حساب ، قل 2 إلى القوة 3، نكتب: {% filename %}command-line{% endfilename %}

```python
>>> 2 ** 3
8
```

استمتع لبعض الوقت مع هذا ، وعد إلى هنا 

كما ترون، بايثون هي الة حاسبة عضيمة. إذا كنت تتساءل ماذا يمكنك أن تفعل…

## سلسلة

ماذا عن اسمك؟ اكتب الاسم الأول في علامات اقتباس مثل هذا:

{% filename %}command-line{% endfilename %}

```python
>>> "Ola"
'Ola'
```

لقد أنشأت الآن السلسلة الأولى! هو تسلسل أحرف يمكن معالجتها بواسطة جهاز الكمبيوتر. يجب ان تبدأ السلسلة وتنتهي بنفس الحرف. قد يكون هذا واحد(`'`)) أو الضعف (`"`)) اقتباس (لا فرق!) الإقتباس يقول لبايثون انه هناك سلسلة.

السلاسل يمكن أن تكون مربوطة معا. جرب هذا:

{% filename %}command-line{% endfilename %}

```python
>>> "Hi there " + "Ola"
'Hi there Ola'
```

يمكنك أيضا ضرب السلاسل مع عدد:

{% filename %}command-line{% endfilename %}

```python
>>> "Ola" * 3
'OlaOlaOla'
```

إذا كنت بحاجة إلى وضع علامة اقتباس أحادية داخل السلسلة الخاصة بك, لديك طريقتين للقيام بذلك.

استخدام علامات الاقتباس المزدوجة:

{% filename %}command-line{% endfilename %}

```python
>>> "Runnin' down the hill"
"Runnin' down the hill"
```

أو الهروب من الفاصلة بخط مائل (`` \):

{% filename %}command-line{% endfilename %}

```python
>>> 'Runnin\' down the hill'
"Runnin' down the hill"
```

لطيف، هاه؟ لرؤية اسمك بالأحرف الكبيرة، اكتب:

{% filename %}command-line{% endfilename %}

```python
>>> "Ola".upper()
'OLA'
```

لقد استخدمت `upper` **method** للتو في السلسلة الخاصة بك! وهناك طريقة (مثل `upper()`) عبارة عن سلسلة من التعليمات التي يجب على بايثون تنفيذها على كائن معين (`"Ola"`) بمجرد استدعائه.

إذا كنت تريد أن تعرف عدد الحروف الواردة في اسمك، هناك **function** لذلك أيضا!

{% filename %}command-line{% endfilename %}

```python
>>> len("Ola")
3
```

أتساءل لماذا في بعض الأحيان أستدعي الدالات بواسطة `.` في نهاية سلسلة (مثل `"Ola".upper()`)، وفي بعض الأحيان يمكنك استدعاء دالة أولاً ووضع السلسلة في الأقواس؟ حسنا، في بعض الحالات، تنتمي المهام إلى أشياء، مثل `upper()`, ، والتي لا يمكن تنفيذها إلا على السلاسل. في هذه الحالة نسمي المهام ب **method**. مرات اخرى، المهام لا تنتمي إلى أي شيء محدد، ويمكن استخدامها على أنواع مختلفة من الكائنات، مثل `len()`. لهذا نحن نعطي `"Ola"` اعدادات الى المهمة `len`.

### مُلخّص

طيب، يكفينا سلآسل ، حتى الأن لقد تعلمت:

- **the prompt** كتابة الأوامر (كودات) في موجه اوامر بايثون يعطينا اجابات في بايثون
- **numbers and strings** - في بايثون تستخدم الأرقام للرياضيات والسلاسل للكائنات النصية
- **operators** مثل `+` و `*`, تجمع بين القيم لتنتج واحدة جديدة
- **functions** مثل `upper()` و `len()` تنفذ إجراأت على الكائنات.

هذه هي الأساسيات لكل لغة برمجة تتعلمها. أنت مستعد لشيء أكثر صعوبة؟ ونحن نراهن على ذالك!

## أخطاء

دعنا نجرب شيئا جديداً. يمكن أن نحصل على طول عدد بنفس الطريقة التي يمكن أن نجد بها طول اسمنا؟ اكتب في `len(304023)` واضغط `enter`:

{% filename %}command-line{% endfilename %}

```python
>>> len(304023)
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
TypeError: object of type 'int' has no len()
```

حصلنا على الخطأ الأول! ويقول أن الكائنات من نوع "إنت" (الأعداد الصحيحة، أرقام كاملة) ليس لها طول. فماذا يمكننا أن نفعل الآن؟ ربما يمكننا كتابة رقمنا كسلسلة؟ سلاسل لها طول، أليس كذلك؟

{% filename %}command-line{% endfilename %}

```python
>>> len(str(304023))
6
```

لقد كان مجديًا! قمنا باستخدام الدالة `str` داخل الدالة `len`. `str ()` تحويل كل شيء إلى سلاسل.

- الدالة `str` تحول الأشياء إلى **strings</1 ></li> 
    
    - الدالة `int` تحول الأشياء إلى **integers**</ul> 
    
    > هام: علينا تحويل الأرقام إلى نص، ولكن لا يمكن بالضرورة تحويل النص إلى أرقام – ماذا ستكون `int('hello')` على أي حال؟
    
    ## المتغيرات
    
    مفهوم هام في البرمجة وهو المتغيرات. المتغير ليس أكثر من اسم لشيء يمكن استخدامه في وقت لاحق. يستخدم المبرمجون هذه المتغيرات لتخزين البيانات، وجعل التعليمات البرمجية الخاصة بهم أكثر قابلية للقراءة، لذالك هم ليسو بحاجة لتدكر كل شيء.
    
    لنفرض أننا نريد إنشاء متغير جديد يسمى `name`:
    
    {% filename %}command-line{% endfilename %}
    
    ```python
>>> name = "Ola"
```

اكتب اسم يساوي Ola.

كما لاحظت، فإن البرنامج لم يعد أي شيء كما فعل من قبل. فكيف نعرف أن المتغير موجود بالفعل؟ ما عليك سوى إدخال `name` واضغط على `enter`:

{% filename %}command-line{% endfilename %}

```python
>>> name
'Ola'
```

يآآاي! المتغير الأول الخاص بك! :) يمكنك دائماً تغيير ما يشير إليه:

{% filename %}command-line{% endfilename %}

```python
>>> name = "Sonja"
>>> name
'Sonja'
```

يمكنك استخدامه في وظائف ايضا:

{% filename %}command-line{% endfilename %}

```python
>>> len(name)
5
```

رائع، أليس كذلك؟ بالطبع، المتغيرات يمكن أن تكون أي شيء أرقام أيضا! جرب هذا:

{% filename %}command-line{% endfilename %}

```python
>>> a = 4
>>> b = 6
>>> a * b
24
```

ولكن ماذا لو استخدمنا اسم خاطئ؟ هل يمكنك تخمين ما يمكن أن يحدث؟ دعونا نحاول!

{% filename %}command-line{% endfilename %}

```python
>>> city = "Tokyo"
>>> ctiy
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'ctiy' is not defined
```

خطأ! كما ترون، بيثون لديه أنواع مختلفة من الأخطاء ويسمى هذا **NameError**. سيعطيك بايثون هذا الخطأ إذا حاولت استخدام متغير لم يتم تعريفه حتى الآن. إذا واجهت هذا الخطأ في وقت لاحق، تحقق من التعليمات البرمجية الخاصة بك لمعرفة إذا كنت أخطأت في أي أسماء.

العب بهذه التعليمات لبعض الوقت، وانضر ما يمكن ان تفعله!

## وظيفة الطباعة

جرب هذا:

{% filename %}command-line{% endfilename %}

```python
>>> name = 'Maria'
>>> name
'Maria'
>>> print(name)
Maria
```

عندما تكتب `name`, فقط، يستجيب مترجم بايثون مع*representation* المتغير 'نيم'، وهو الحرف M-a-r-i-a، المحاط بعلامات اقتباس مفردة، ''. عندما تقول `print(name)`, بايثون ستقوم ب "طباعة" محتويات المتغير إلى الشاشة، دون علامات الاقتباس، وهو أكثرإتقانا.

وكما سنرى لاحقاً، `print()` مفيد أيضا عندما نريد طباعة الأشياء من داخل المهام، أو عندما نريد طباعة الأشياء في أسطر متعددة.

## القوائم

بجانب السلاسل والأعداد الصحيحة، بايثون لديه كل الأنواع المختلفة من الكائنات. الآن نحن بصدد إدخال واحد يسمى **list**. القوائم هي بالضبط ما تعتقد: الكائنات التي هي قوائم لكائنات الأخرى. :)

امضي قدما وأنشئ قائمة:

{% filename %}command-line{% endfilename %}

```python
>>> []
[]
```

نعم، هذه القائمة فارغة. ليست مفيدة جدا، أليس كذلك؟ دعونا ننشئ قائمة من أرقام اليانصيب. نحن لا نريد أن نكرر ذالك طوال الوقت، لذلك سنضعها في متغير أيضا:

{% filename %}command-line{% endfilename %}

```python
>>> lottery = [3, 42, 12, 19, 30, 59]
```

حسنا، لدينا قائمة! ماذا يمكننا أن نفعل حيال ذلك؟ دعونا نرى كم عدد اليانصيب هناك في القائمة. هل لديك أي فكرة عن أي وظيفة يجب عليك استخدامها لذلك؟ أنت تعرف هذا بالفعل!

{% filename %}command-line{% endfilename %}

```python
>>> len(lottery)
6
```

نعم! `len()` يمكن أن تعطيك عددا من الكائنات في قائمة. مفيد، أليس كذلك؟ ربما سنقوم بترتيبها الآن:

{% filename %}command-line{% endfilename %}

```python
>>> lottery.sort()
```

هذا لا يعيد أي شيء، انها مجرد تغييرات للترتيب الذي يظهر الأرقام في القائمة. دعونا نطبعه مرة أخرى ونرى ما يحدث:

{% filename %}command-line{% endfilename %}

```python
>>> print(lottery)
[3, 12, 19, 30, 42, 59]
```

كما ترون، يتم فرز الأرقام في القائمة الخاصة بك الآن من أدنى إلى أعلى القيمة. مبروك!

ربما نريد عكس هذا الترتيب؟ دعونا نفعل ذلك!

{% filename %}command-line{% endfilename %}

```python
>>> lottery.reverse()
>>> print(lottery)
[59, 42, 30, 19, 12, 3]
```

إذا كنت ترغب في إضافة أي شيء إلى القائمة الخاصة بك، يمكنك القيام بذلك عن طريق كتابة هذا الأمر:

{% filename %}command-line{% endfilename %}

```python
>>> lottery.append(199)
>>> print(lottery)
[59, 42, 30, 19, 12, 3, 199]
```

إذا كنت ترغب في إظهار الرقم الأول فقط، يمكنك القيام بذلك باستخدام **indexes**. الفهرس هو العدد الذي يقول أين يحدث عنصر في قائمة. المبرمجين يفضلون بدء العد من 0، وبالتالي فإن الكائن الأول في قائمتك هو في مؤشر 0، والكائن القادم هو في 1، وما إلى ذلك. جرب هذا:

{% filename %}command-line{% endfilename %}

```python
>>> print(lottery[0])
59
>>> print(lottery[1])
42
```

كما ترون، يمكنك الوصول إلى كائنات مختلفة في القائمة الخاصة بك باستخدام الاسم في قائمة الفهرس للكائن داخل أقواس معقوفة.

لحذف شيء من القائمة الخاصة بك سوف تحتاج إلى استخدام **indexes** كما تعلمنا أعلاه وأسلوب `pop()`. دعونا احد الأمثلة ونعزز ما تعلمناه سابقا. سنقوم بحذف الرقم الأول من قائمتنا.

{% filename %}command-line{% endfilename %}

```python
>>> print(lottery)
[59, 42, 30, 19, 12, 3, 199]
>>> print(lottery[0])
59
>>> lottery.pop(0)
59
>>> print(lottery)
[42, 30, 19, 12, 3, 199]
```

انه يعمل كالحصان!

للمتعة الإضافية، حاول بعض الفهارس الأخرى: 6، 7، 1000،-1 أو-6-1000. انظر إذا كان يمكنك التنبؤ بالنتيجة قبل محاولة الأمر. منطقي؟

يمكن أن تجد قائمة بجميع الأساليب القائمة المتوفرة في هذا الفصل من وثائق بايثون: https://docs.python.org/3/tutorial/datastructures.html

## القواميس

> للقراء في المنزل: هذا الفصل تم التكلم عنه في [Python Basics: Dictionaries](https://www.youtube.com/watch?v=ZX1CVvZLE6c).

القاموس مماثل للقائمة، ولكن يمكنك الوصول إلى القيم عن طريق البحث عن المفتاح بدلا من الفهرس الرقمي. المفتاح يمكن أن يكون أي سلسلة أو رقم. تعريف جملة لبنآء قاموس فارغ:

{% filename %}command-line{% endfilename %}

```python
>>> {}
{}
```

هذا يدل على أنك قمت بإنشاء قاموس فارغ للتو. يآآاي!

والآن، حاول كتابة الأمر التالي (محاولة استبدال المعلومات الخاصة بك، ايضا):

{% filename %}command-line{% endfilename %}

```python
>>> participant = {'name': 'Ola', 'country': 'Poland', 'favorite_numbers': [7, 42, 92]}
```

مع هذا الأمر، الذي أنشأته للتو متغير يسمى `participant` مع ثثلاثة أزواج القيمة الرئيسية:

- المفتاح `name` يشير إلى قيمة`'Ola'`(كائن `string`)،
- `country` يشير إلى `'Poland'` (`string` أخرى)،
- ويشير `favorite_numbers` إلى `[7، 42، 92]` (`list` بثلاثة أرقام).

يمكنك التحقق من محتوى المفاتيح الفردية مع بناء الجملة التالي:

{% filename %}command-line{% endfilename %}

```python
>>> print(participant['name'])
Ola
```

انظر، انها مماثلة للقائمة. ولكن لا تحتاج إلى تذكر الفهرس - فقط الاسم.

ماذا يحدث إذا طلبنا من بايثون قيمة مفتاح غير موجود؟ هل يمكنك التخمين؟ دعونا نحاول ونرى!

{% filename %}command-line{% endfilename %}

```python
>>> participant['age']
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'age'
```

انضر، خطأ آخر! هذا **KeyError**. بايثون مفيد ويخبرك بأن مفتاح `'age'` غير موجود في هذا القاموس.

متى يجب استخدام قاموس أو قائمة؟ حسنا، هذه نقطة جيدة للتفكير. فقط فكر في حل قبل النظر في الجواب في السطر التالي.

- هل تحتاج فقط إلى تسلسل أمر من العناصر؟ انتقل إلى القائمة.
- هل تحتاج إلى ربط القيم مع مفاتيح، حتى تتمكن من البحث عنها بكفاءة (عن طريق مفتاح) في وقت لاحق؟ إستخدم المعجم.

القواميس، مثل القوائم، و *mutable*، بمعنى أنه يمكن تغييرها بعد إنشائها. يمكنك إضافة أزواج مفتاح – القيمة الجديدة إلى قاموس بعد إنشائه، هكذا:

{% filename %}command-line{% endfilename %}

```python
>>> participant['favorite_language'] = 'Python'
```

مثل القوائم، باستخدام طريقة `len()` على القواميس ترجع عدد أزواج القيمة الرئيسية في القاموس. إمضي قدما واكتب هذا الأمر:

{% filename %}command-line{% endfilename %}

```python
>>> len(participant)
4
```

آمل أن يكون هذا منطقيا حتى الآن. :) هل انت على استعداد لمتعة أكثر مع القواميس؟ قراءة لبعض الأشياء المدهشة.

يمكنك استخدام الأسلوب `pop()` لحدف عنصر من القاموس. لنفترض أنك تريد حذف المدخل المقابل للمفتاح `'favorite_numbers'`, ، اكتب فقط الأمر التالي:

{% filename %}command-line{% endfilename %}

```python
>>> participant.pop('favorite_numbers')
[7, 42, 92]
>>> participant
{'country': 'Poland', 'favorite_language': 'Python', 'name': 'Ola'}
```

كما ترون من المخرج، تم حذف زوج مفتاح القيمة المقابلة لمفتاح 'favorite_numbers'.

فضلا عن ذلك، يمكنك أيضا تغيير قيمة مرتبطة بمفتاح تم إنشاؤه مسبقاً في القاموس. اكتب هذا الأمر:

{% filename %}command-line{% endfilename %}

```python
>>> participant['country'] = 'Germany'
>>> participant
{'country': 'Germany', 'favorite_language': 'Python', 'name': 'Ola'}
```

كما ترون، تم تغيير قيمة المفتاح `'country'` من `'Poland'` إلى `'Germany'`. :) مثير؟ مرحى! لقد تعلمت للتو شيء آخر مدهش.

### الملخص

مدهش! أنت تعرف الكثير عن البرمجة الآن. لقد تعلمت في هذا الجزء الأخير حول:

- **أخطاء** – يمكنك الآن معرفة كيفية قراءة وفهم الأخطاء التي تظهر إذا كان بايثون لم يفهم امر اعطيته له
- **المتغيرات** –أسماء الكائنات التي تسمح لك بتكويد أكثر سهولة وجعل التعليمات البرمجية الخاصة بك أكثر قابلية للقراءة
- **قوائم** – قوائم الكائنات المخزنة في ترتيب معين
- **قواميس** – الكائنات المخزنة كقيمة مفتاح-أزواج

متحمس للجزء القادم؟ :)

## مقارنة الأشياء

> للقراء في المنزل: هذا الفصل تم التكلم عنه في فيديو [Python Basics: Dictionaries](https://www.youtube.com/watch?v=7bzxqIKYgf4).

جزء كبير من البرمجة ينطوي على مقارنة الأشياء. ما هو أسهل شيء للمقارنة؟ أرقام، بالطبع. دعونا نرى كيف يعمل:

{% filename %}command-line{% endfilename %}

```python
>>> 5 > 2
True
>>> 3 < 1
False
>>> 5 > 2 * 2
True
>>> 1 == 1
True
>>> 5 != 2
True
```

أعطينا بايثون بعض الأرقام للمقارنة. كما ترون،بايثون لا يمكنها مقارنة الأرقام فقط، ولكن يمكنها أيضا مقارنة نتائج الأسلوب. لطيف، هاه؟

هل تتساءل لماذا وضعنا اثنين من العلامات المتساوية `==` بجانب بعضها البعض للمقارنة إذا كانت الأرقام متساوية؟ ونحن نستخدم `=` واحد لتعيين القيم للمتغيرات. دائماً، تحتاج **دائماً** إلى وضع اثنين من--= = ``--إذا كنت ترغب في معرفة ما إذا كانت الأمور مساوية لبعضها البعض. يمكننا أن نقول أيضا أن الأمور غير متساوية مع بعضها البعض. لذالك نستخدم هذه الرموز `!=` كما هو مبين في المثال أعلاه.

أعطي بايثون مهمتان اخرتان:

{% filename %}command-line{% endfilename %}

```python
>>> 6 >= 12 / 2
True
>>> 3 <= 2
False
```

لقد شهدنا `>` و `<`، ولكن ما فعله `> =` و `< =` يعني؟ اقرأهم بهذه الطريقة:

- `x_>` y يعني: x أكبر من y
- `x_<` y يعني: x أقل من y
- x `<=` y يعني: x أقل من أو يساوي y
- x `> =` يعني y: x أكبر من أو يساوي y

رائع! تريد القيام بذالك مرة اخرى؟ جرب هذا:

{% filename %}command-line{% endfilename %}

```python
>>> 6 > 2 and 2 < 3
True
>>> 3 > 2 and 2 < 1
False
>>> 3 > 2 or 2 < 1
True
```

يمكنك أن تعطي بايثون العديد من الأرقام للمقارنة كما تريد، وسوف تعطيك الجواب! ذكية جدا، أليس كذلك؟

- **و**-إذا قمت باستخدام عامل التشغيل `and`، كل المقارنات يجب أن تكون صحيحة في النظام لكي يكون الأمر كله صحيح
- **أو** – إذا كنت تستخدم عامل التشغيل `or`، واحد فقط من المقارنات يجب أن يكون صحيحاً في النظام لكي يكون الأمر كله صحيح

هل سمعت عبارة "مقارنة التفاح بالبرتقال"؟ دعونا نحاول ما يعادل بايثون:

{% filename %}command-line{% endfilename %}

```python
>>> 1 > 'django'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: '>' not supported between instances of 'int' and 'str'
```

هنا ترى أنه كما هو الحال في التعبير، بايثون غير قادرة على مقارنة عدد(`int`) وسلسلة (`str`). بدلاً من ذلك، فإنه يظهر **TypeError** ويقول لنا لا يمكن مقارنة هذين النوعين معا.

## Boolean

وبالمناسبة، لقد تعلمت للتو نوع جديد من الكائنات في بايثون. تسمى **Boolean**.

هناك اثنين فقط من كائنات Boolean :

- صحيح
- خطأ

لتفهم بايثون ذالك ، تحتاج الى كتابتها دائما ك "صحيح" (الحرف الأول كبير، مع بقية الحروف صغيرة). **true, TRUE,، وtRUE لن تنجح – الوحيدة التي ستنجح هي True.** (نفس الأمر ينطبق على 'False' كذلك، بطبيعة الحال.)

يمكن أن تكون Booleans متغيرات، أيضا! انظر هنا:

{% filename %}command-line{% endfilename %}

```python
>>> a = True
>>> a
True
```

يمكنك أيضا القيام بذلك بهذه الطريقة:

{% filename %}command-line{% endfilename %}

```python
>>> a = 2 > 5
>>> a
False
```

تدرب واستمتع مع Booleans قبل محاولة تشغيل الأوامر التالية:

- `True and True`
- `False and True`
- `True or 1 == 1`
- `1 != 2`

مبروك! Booleans واحدة من أروع ملامح البرمجة، وانت تعلمت للتو كيفية استخدامها!

# احفظه!

> للقراء في المنزل: هذا الفصل تم التكلم عنه في فيديو [Python Basics: Saving files and "If" statement](https://www.youtube.com/watch?v=dOAg6QVAxyk).

حتى الآن كنا نكتب كل ما لدينا من تعليمات بايثون في المترجم، مما يحدنا من إدخال سطر واحد من التعليمات البرمجية في وقت واحد. يتم حفظ البرامج العادية في الملفات ويتم تنفيذها من قبل لغتنا البرمجية **interpreter** أو **compiler**. حتى الآن كنا نقوم بتشغيل برامجنا سطر واحد في كل مرة في بايثون **interpreter**. سنحتاج إلى أكثر من سطر واحد من التعليمات البرمجية للمهام القليلة التالية، لذلك سنحتاج بسرعة إلى:

- قم بإنهاء مترجم بايثون
- فتح محرر التعليمات البرمجية لدينا الاختيار
- حفظ بعض التعليمات البرمجية في ملف بايثون جديد
- تشغيله!

للخروج من مترجم بايثون كنا نستعمل، ببساطة اكتب دالة `exit()`

{% filename %}command-line{% endfilename %}

```python
>>> exit()
$
```

سيؤدي ذلك إلى إعادة توجيهك إلى موجه الأوامر.

في وقت سابق، اخترنا محرر رموز من قسم [code editor](../code_editor/README.md). سنحتاج إلى فتح المحرر الآن وكتابة بعض الأكواد في ملف جديد:

{% filename %}editor{% endfilename %}

```python
print('Hello, Django girls!')
```

ومن الواضح أنك مطور بايثون محنك جداً الآن، لذا لا تتردد في كتابة بعض التعليمات البرمجية التي تعلمتها اليوم.

الآن نحن بحاجة إلى حفظ الملف وإعطائه اسماً وصفياً. دعونا نسمي الملف **python_intro.py** وحفظه إلى سطح المكتب الخاص بك. يمكننا تسمية الملف أي شيء نريده، ولكن الجزء المهم هنا هو التأكد من انتهاء الملف ب **.py**. ويقول امتداد **.py** لنظام التشغيل أن هذا **Python executable file</0 وبايثون يمكن ان يشغله.</p> 

> يجب أن تلاحظ واحدة من أروع شيء عن المحررين الأكواد: الألوان! في وحدة تحكم بايثون، كان كل شيء بنفس اللون. الآن يجب أن ترى أن الدالة `print` هي لون مختلف عن السلسلة. وهذا ما يسمى "syntax highlighting"، وهي ميزة مفيدة حقاً عند الترميز. سيعطيك لون الأشياء تلميحات مثل السلاسل غير المغلقة أو الأخطاء المطبعية في اسم الكلمة الرئيسية (مثل `def` في إحدى الدالات، والتي سنراها أدناه). وهذا أحد الأسباب التي تجعلنا نستخدم محرر تعليمات برمجية. :)

مع الملف المحفوظ، حان الوقت لتشغيله! استخدم المهارات التي كنت قد تعلمت في قسم سطر الأوامر، استخدام التيرمينال **change directories** إلى سطح المكتب.

<!--sec data-title="Change directory: OS X" data-id="python_OSX"
data-collapse=true ces-->

على نظام التشغيل ماك، سيبدو الأمر على هذا النحو:

{% filename %}command-line{% endfilename %}

    $ cd ~/Desktop
    

<!--endsec-->

<!--sec data-title="Change directory: Linux" data-id="python_linux"
data-collapse=true ces-->

في لينكس، فإنه سيكون مثل هذا (كلمة "سطح المكتب" قد تترجم إلى اللغة المحلية الخاصة بك):

{% filename %}command-line{% endfilename %}

    $ cd ~/Desktop
    

<!--endsec-->

<!--sec data-title="Change directory: Windows Command Prompt" data-id="python_windows" data-collapse=true ces-->

في موجه أوامر Windows، فإنه سيكون مثل هذا:

{% filename %}command-line{% endfilename %}

    > cd %HomePath%\Desktop
    

<!--endsec-->

<!--sec data-title="Change directory: Windows Powershell" data-id="python_windowsPSH" data-collapse=true ces-->

وفي Windows Powershell، فإنه سيكون مثل هذا:

{% filename %}command-line{% endfilename %}

    > cd $Home\Desktop
    

<!--endsec-->

إذا واجهتك مشكلة، فقط اطلب المساعدة.

الآن استخدم بايثون لتنفيذ التعليمات البرمجية في ملف مثل هذا:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hello, Django girls!
    

ملاحظة: في يندوز 'python3' غير معروف كأمر. بدلاً من ذلك، استخدم 'python' لتنفيذ الملف:

{% filename %}command-line{% endfilename %}

```python
> python python_intro.py
```

حسنا ، لقد شغلت للتو برنامجك الأول في بايثون والذي كان محفوضا في ملف ، هذا احساس رائع؟

يمكنك الآن الانتقال إلى أداة أساسية في البرمجة:

## If … elif … else

يجب تنفيذ الكثير من الأشياء في التعليمات البرمجية فقط عند استيفاء شروط معينة. وهذا هو السبب في أن بايثون لديها ما يسمى **if statements**.

استبدال التعليمات البرمجية في ملف **python_intro.py** بهذا:

{% filename %}python_intro.py{% endfilename %}

```python
if 3 > 2:
```

إذا كان لنا أن نحفض ونشغل هذا، كنا لنرى خطأ مثل هذا:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    File "python_intro.py", line 2
             ^
    SyntaxError: unexpected EOF while parsing
    

بيثون يتوقع منا إعطاءه مزيد من التعليمات ليتم تنفيذها إذا كان الشرط `3 > 2` يتحول إلى أن يكون صحيحاً (أو `True` لهذه المسألة). دعونا نحاول جعل بايثون تطبع "بايثون تطبع!". استبدال التعليمات البرمجية في ملف **python_intro.py** بهذا:

{% filename %}python_intro.py{% endfilename %}

```python
if 3 > 2:
    print('It works!')
```

لاحظ كيف قمنا بفصل السطر التالي من التعليمات البرمجية ب 4 مسافات؟ نحن بحاجة إلى القيام بذلك حتى يعرف بايثون ما هي التعليمات البرمجية التي يجب عليه تشغيلها ، إذا كانت النتيجة صحيحة. يمكنك وضع مسافة واحدة لكن اغلب مبرمجي بايثون يستخدمون 4 مسافات ، لجعل الأمور اكثر اناقة. علامة تبويب `واحدة` ستعتبر أيضا 4 مسافات.

احفضها وشغلها مرة اخرى:

{% filename %}command-line{% endfilename %}

```python
$ python3 python_intro.py
It works!
```

ملاحظة: تذكر أن 'python3' في Windows، لا يعتبر كأمر. من الآن فصاعدا، غير 'python3' ب 'python' لتشغيل الملف.

### ماذا إذا كان الشرط غير صحيح؟

في الأمثلة السابقة، تم تنفيذ التعليمات البرمجية فقط عندما كانت الظروف حقيقية. ولكن بايثون تحتوى ايضا على `elif` و `else`:

{% filename %}python_intro.py{% endfilename %}

```python
if 5 > 2:
    print('5 is indeed greater than 2')
else:
    print('5 is not greater than 2')
```

عند تشغيل هذا سيتم طباعته:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    5 is indeed greater than 2
    

إذا كان عدد 2 أكبر من 5، فسيتم تنفيذ الأمر الثاني. دعونا نرى كيف يعمل `elif`:

{% filename %}python_intro.py{% endfilename %}

```python
name = 'Sonja'
if name == 'Ola':
    print('Hey Ola!')
elif name == 'Sonja':
    print('Hey Sonja!')
else:
    print('Hey anonymous!')
```

وتنفذ:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hey Sonja!
    

اترى ما حدث هناك؟ `elif` يسمح لك بإضافة الشروط الإضافية التي يتم تشغيلها في حالة فشل الشروط السابقة.

يمكنك إضافة العديد من بيانات `elif` كما تريد بعد العبارة الأولى `if` الخاص بك. على سبيل المثال:

{% filename %}python_intro.py{% endfilename %}

```python
volume = 57
if volume < 20:
    print("It's kinda quiet.")
elif 20 <= volume < 40:
    print("It's nice for background music")
elif 40 <= volume < 60:
    print("Perfect, I can hear all the details")
elif 60 <= volume < 80:
    print("Nice for parties")
elif 80 <= volume < 100:
    print("A bit loud!")
else:
    print("My ears are hurting! :(")
```

بايثون يمر من خلال كل اختبار في تسلسل ويطبع:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Perfect, I can hear all the details
    

## التعليقات

التعليقات هي سطور تبدأ ب `#`. يمكنك كتابة ما تريد بعد `#` وسيتجاهل بايثون ذلك. يمكن للتعليقات ان تجعل تعليماتك البرمجية سهلة ليفهمها الأخرين.

دعونا نرى كيف يبدو ذالك:

{% filename %}python_intro.py{% endfilename %}

```python
# Change the volume if it's too loud or too quiet
if volume < 20 or volume > 80:
    volume = 50
    print("That's better!")
```

لا تحتاج إلى كتابة تعليق لكل سطر من التعليمات البرمجية، ولكنها مفيدة لشرح سبب قيام الشفرة بعمل شيء ما، أو تقديم ملخص عندما تفعل شيئا معقدا.

### الملخص

لقد تعلمت في التدريبات القليلة الماضية حول:

- **مقارنة الأشياء** – في بايثون يمكنك مقارنة الأشياء باستخدام `>`، `> =`, `= =`، `< =`، `<` و `and` مشغلي `or`
- **Boolean** نوع من العناصر التي لا يمكن أن تحتوي إلا على قيمتين: `True` أو `False`
- **حفظ الملفات** – تخزين التعليمات البرمجية في ملفات حيث يمكنك تنفيذ برامج أكبر.
- **if … elif … else** – البيانات التي تسمح لك بتنفيذ التعليمات البرمجية فقط عند استيفاء شروط معينة.
- **التعليقات**-الأسطر التي لن تشغلها بايثون والتي تمكنك من توثيق التعليمات البرمجية الخاصة بك

حان الوقت للجزء الأخير من هذا الفصل!

## الدالات الخاصة بك!

> للقراء في المنزل: هذا الفصل تم التكلم عنه في فيديو [Python Basics: Functions](https://www.youtube.com/watch?v=5owr-6suOl0).

اتذكر الوضائف مثل `len()` التي يمكنك تنفيدها في بايثون؟ حسنا، الأخبار جيدة--سوف تتعلم كيفية كتابة الدالات الخاصة بك الآن!

الدالة هي سلسلة من التعليمات التي يجب على بيثون تنفيذها. تبدأ كل وظيفة في بيثون بالكلمة الرئيسية `def`، وتعطى اسما، ويمكن أن تحتوي على بعض المعلمات. دعونا نعطيها انطلاقة. استبدال التعليمات البرمجية في ملف **python_intro.py** بهذا:

{% filename %}python_intro.py{% endfilename %}

```python
def hi():
    print('Hi there!')
    print('How are you?')

hi()
```

حسنا، الدالة الأولى جاهزة!

قد تتساءل لماذا نحن قد كتبنا اسم الدالة في الجزء السفلي من الملف. هذا لأن بايثون يقرأ الملف وينفذه من أعلى إلى أسفل. لذالك لكي نستخدم وضيفتنا ، يجب ان نعيد كتابته في الجزء السفلي.

لنختبر و نرى ماذا يحدث:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hi there!
    How are you؟
    

ملاحظة: إذا كان لا يعمل، لا داعي للذعر! المخارج سوف تساعدك على معرفة السبب:

- إذا حصلت على `NameError`، فهذا يعني أنك كتبت شيئا خاطئا، لذا يجب عليك التحقق من أنك استخدمت نفس الاسم عند إنشاء الدالة باستخدام `def hi():` وعند الاتصال به `hi()`.
- إذا حصلت على `IndentationError`، تحقق من أن كلا من خطوط <`print` لها نفس المسافة البيضاء في بداية السطر: بايثون يريد أن تكون كل شفرة داخل الدالة محاذية بدقة.
- إذا لم يكن هناك أي إخراج على الإطلاق، تحقق من أن آخر `hi()` *isn't* مسنن - إذا كان كذلك، فسيصبح هذا السطر جزءا من الوظيفة أيضا، ولن يتم تشغيله ابدا.

دعونا نبني أول وظيفة لدينا مع المعلمات. سنستخدم المثال السابق - الدالة التي تقول "مرحبا" للشخص الذي يديرها - مع اسم:

{% filename %}python_intro.py{% endfilename %}

```python
def hi(name):
```

كما ترون، أعطينا الآن وظيفتنا معلمة قمنا بتسميتها `name`:

{% filename %}python_intro.py{% endfilename %}

```python
def hi(name):
    if name == 'Ola':
        print('Hi Ola!')
    elif name == 'Sonja':
        print('Hi Sonja!')
    else:
        print('Hi anonymous!')

hi()
```

تذكر: يتم وضع الدالة `print` على مسافة فاصلة ضمن المسافات `if`. وذلك لأن الدالة تعمل عندما يتم استيفاء الشرط. دعونا نرى كيف تعمل الآن:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Traceback (most recent call last):
    File "python_intro.py", line 10, in <module>
      hi()
    TypeError: hi() missing 1 required positional argument: 'name'
    

عفوا، خطأ. لحسن الحظ، بايثون يعطينا رسالة إعلام خطأ مفيدة جداً. يخبرنا أن الدالة `hi()`(التي حددناها) تحتوي على وسيطة واحدة مطلوبة (تسمى `name`) ونسينا أن نمررها عند استدعاء الدالة. دعونا نصلحه في الجزء السفلي من الملف:

{% filename %}python_intro.py{% endfilename %}

```python
hi("Ola")
```

وشغله مرة أخرى:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hi Ola!
    

وإذا قمنا بتغيير الاسم؟

{% filename %}python_intro.py{% endfilename %}

```python
hi("Sonja")
```

وتشغيله:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hi Sonja!
    

والآن، ما رأيك سوف يحدث إذا قمت بكتابة اسم آخر هناك؟ (لا Ola أو Sonja). جرب وانظر إذا كنت على حق. يجب طباعة هذا:

{% filename %}command-line{% endfilename %}

    Hi anonymous!
    

يبدو رائعا أليس كذالك؟ بهذه الطريقة ليس عليك تكرار نفسك في كل مرة تريد تغيير اسم الشخص الذي من المفترض أن تقوم الوضيفة بتحيته. وهذا هو بالضبط لماذا نحن بحاجة إلى وظائف--لا تريد ابدأ تكرار التعليمات البرمجية الخاصة بك!

دعونا نفعل شيئا أكثر ذكاء - هناك أسماء أكثر من اثنين، وكتابة شرط لكل منهم سيكون صعبا، أليس كذلك؟

{% filename %}python_intro.py{% endfilename %}

```python
def hi(name):
    print('Hi ' + name + '!')

hi("Rachel")
```

دعونا نستدعي التعليمات البرمجية الآن:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hi Rachel!
    

مبروك ! لقد تعلمت للتو كيف تكتب الوضائف

## الحلقات

> للقراء في المنزل: هذا الفصل تم التكلم عنه في فيديو [Python Basics: For Loop](https://www.youtube.com/watch?v=aEA6Rc86HF0).

هذا هو الجزء الأخير . كان ذلك سريعا، أليس كذلك؟ :)

المبرمجين لا يحبون تكرار أنفسهم. البرمجة هي جعل كل شيء يعمل أوتوماتيكيا، لذلك نحن لا نريد تحية كل شخص باسمه يدويا، أليس كذلك؟ هنا حيث تأتي الحلقات في متناول اليدين.

لا تزال تذكر القوائم؟ دعونا ننشئ قائمة من الفتيات:

{% filename %}python_intro.py{% endfilename %}

```python
girls = ['Rachel', 'Monica', 'Phoebe', 'Ola', 'You']
```

نحن نريد أن نحيي كل منهم باسمه. لدينا وظيفة `hi` للقيام بذلك، لذلك دعونا نستخدمها في حلقة:

{% filename %}python_intro.py{% endfilename %}

```python
for name in girls:
```

الـ ```ﻷجل``` بيان يتصرف مثل ```if``` بيان؛ الكود أدناه كل من هذه تحتاج إلى أن تكون المسافة البادئة بأربع مسافات.

هنا التعليمات البرمجية الكاملة التي سوف تكون في الملف:

{% filename %}python_intro.py{% endfilename %}

```python
def hi(name):
    print('Hi ' + name + '!')

girls = ['Rachel', 'Monica', 'Phoebe', 'Ola', 'You']
for name in girls:
    hi(name)
    print('Next girl')
```

وعند تشغيله:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hi Rachel!
    Next girl
    Hi Monica!
    Next girl
    Hi Phoebe!
    Next girl
    Hi Ola!
    Next girl
    Hi You!
    Next girl
    

كما ترون، سيتم تكرار كل ما تضعه داخل بيان `for` مع مسافة بادئة لكل عنصر من القائمة `girls`.

يمكنك أيضا استخدام `` بالأرقام باستخدام الدالة `range`:

{% filename %}python_intro.py{% endfilename %}

```python
for i in range(1, 6):
    print(i)
```

والتي ستطبع:

{% filename %}command-line{% endfilename %}

    1
    2
    3
    4
    5
    

`range` هو دالة تقوم بإنشاء قائمة أرقام متتالية واحداً تلو الآخر (هذه الأرقام هي التي تقدمها لك كمعلمات).

لاحظ أن ثاني هذين الرقمين غير مدرجين في القائمة التي يتم إخراجها بواسطة بايثون (بمعنى `range(1, 6)` من 1 إلى 5، ولكن لا يشمل الرقم 6). وهذا لأن "range" نصف مفتوح، ونعني بذلك أنه يتضمن القيمة الأولى، ولكنها ليست الأخيرة.

## الملخص

هذا كل شيء. **You totally rock!** كان هذا فصل صعب، لذلك يجب أن تشعر بالفخر من نفسك. لما وصلت اليه حتى الأن!

لدروس بايثون الرسمية والكاملة زر https://docs.python.org/3/tutorial/. هذا سوف يعطيك دراسة أكثر شمولا وكاملة للغة. في صحتك:)

قد ترغب في القيام بإيجاز شيء آخر - تمتد، تتجول قليلا، إراحة عينيك - قبل الذهاب إلى الفصل التالي. :)

![كاب كيك](images/cupcake.png)