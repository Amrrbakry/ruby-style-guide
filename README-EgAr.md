# مقدمة

> وجود مثل أعلي مهم <br>
> -- أليكس ج. ميرفي / روبوكب


شئ كان دايما بيضايقني ك روبي ديفيلوبر&mdash;مطورين البايثون عندهم مرجع عظيم لطريقة كتابة الكود
([راجع ستايل البايثون](https://www.python.org/dev/peps/pep-0008/)) و احنا مش عندنا واحد رسمي زيه يوثق طريقة الكتابة بالروبي و افضل التطبيقات.
 و انا مؤمن جدا ان دا حاجة مهمة , و ايضا مؤمن ان مجتمع عظيم زي بتاع الروبي لازم يكون قادر يطلع ستايل زي ده.

المرجع او الدليل دا ابتدا ك مرجع داخلي خاص لشركتنا دليل البرمجة بالروبي (اتكتب عشانك بجد).
في لحظة كدا قررت ان اللي انا بعمله دا ممكن ناس كتيرة من مجتمع الروبي تهتم بيه عامة , و ان العالم في احتياج اقل  ل توجيه داخلي اخر لشركة .
بس بكل تأكيد العالم هيستنفع من اللي هنقدر نسجله و نتوصل ايه من تطبيقات و ممارسات تسهل كتابة لغة الروبي

من ساعة ما بدأت الدليلل دا و انا بيجيلي رد فعل من اعضاء مجتمع الروبي من جميع انحاء العالم.
الفضل ل كل الاقتراحات و الدعم! مع بعض هنقدر نعمل مصدر مفيد لكل مطزر بلغة الروبي.

علي فكرة لو انت شغال رايلز برضه ممكن تحتاج تبص بصة علي [دليل أسلوب الروبي اون رايلز][rails-style-guide].


# دليل أسلوب كتابة الروبي

الدليل دا بيقترح عليك افضل التطبيقات عشان مبرمج الروبي الحقيقي يقدر يكتب حاجة مبرمج روبي حقيقي تاني يقدر يعدل عليها
دليل بيعكس الاستخدام بتاعه في العالم الحقيقي , في حين ان الدليل المتمسك بالمثالية بيترفض من الناس ,
 و هو المفروض يساعد علي التخلص من المشاكل نهائيا بغض النظر هو كويس اد ايه .


الدليل دا متقسم ل اجزاء ليها علاقة ببعض . و انا حاولت اضيف المنطق علي القواعد (لو حاجة منها اهملت ف انا حاطط افتراض انها واضحة)

انا مجبتش القواعد دي من عندي, هم غالبا مستندين علي حياتي المهنية ك مهندس برمجيات محترف و الاقتراحات و الاراء من اعضاء مجتمع الروبي  و مصادر محترمة ل برمجة الروبي
 مثل :-
["Programming Ruby"][pickaxe] و
["The Ruby Programming Language"][trpl].

في بعض النواحي مبتلاقيش توافق واضح للاراء في مجتمع الروبي بالنسبة لاسلوب معين (زي طريقة تعريف السترينج, المسافات اللي جوا الهاش, مكان النقطة في تسلسل الدوال, الخ .. )
في الحالات اللي زي دي يتم التعريف بجميع الانماط المشهورة و يسيبك براحتك تطبق اللي تحبه .


الدليل دا بيتطور علي طول مع الوقت ,عشان عرف جديد بيتحط او واحد قديم يتشال عشان تغير بيحصل في لغة الروبي نفسها

كتير من المشاريع عندهم دليل كتابة كود خاص بيهم (غالبا بيكون مشتق من الدليل دا).
في حالة وجود اي خلاف فان الاولوية تكون للدليل دا.

ممكن تعمل نسخة من الدليل PDF او HTML باستخدام  [Pandoc][].

و دا يقدر يحلل الكود بتاعك , بناء علي الدليل دا [RuboCop][] .


الترجمات المتاحة للدليل دا موجودة بالغات دي :-


* [الانجليزية](https://github.com/bbatsov/ruby-style-guide/blob/master/README.md)
* [الصينية المبسطة](https://github.com/JuanitoFatas/ruby-style-guide/blob/master/README-zhCN.md)
* [الصينية التقليدية](https://github.com/JuanitoFatas/ruby-style-guide/blob/master/README-zhTW.md)
* [الفرنسية](https://github.com/gauthier-delacroix/ruby-style-guide/blob/master/README-frFR.md)
* [اليابانية](https://github.com/fortissimo1997/ruby-style-guide/blob/japanese/README.ja.md)
* [الكورية](https://github.com/dalzony/ruby-style-guide/blob/master/README-koKR.md)
* [البرتغالية](https://github.com/rubensmabueno/ruby-style-guide/blob/master/README-PT-BR.md)
* [الروسية](https://github.com/arbox/ruby-style-guide/blob/master/README-ruRU.md)
* [الاسبانية](https://github.com/alemohamad/ruby-style-guide/blob/master/README-esLA.md)
* [الفيتنامية](https://github.com/CQBinh/ruby-style-guide/blob/master/README-viVN.md)

## المحتويات



* [نموذج السورس كود](#source-code-layout)
* [تركيب الجملة](#syntax)
* [التسمية](#naming)
* [التعليقات](#comments)
  * [التعليقات التوضيحية للتعليقات](#comment-annotations)
  * [التعليقات السحرية](#magic-comments)
* [الفئات و الوحدات](#classes--modules)
* [الاستثنائات](#exceptions)
* [المجموعات](#collections)
* [الارقام](#numbers)
* [strings](#strings)
* [الوقت و التاريخ](#date--time)
* [التعبيرات العادية](#regular-expressions)
* [حرف النسبة المئوية](#percent-literals)
* [ميتابروجرامينج](#metaprogramming)
* [متفرقات](#misc)
* [ادوات](#tools)

## نموذج السورس كود
تقريبا كل واحد شايف ان كل الستيلات معفنة و متتقريش معادا بتاعهم , شيل كدا "بتاعهم" . تقريبا كدا هم صح
> تقريبا كل واحد شايف ان كل الستيلات معفنة و متتقريش
> معادا بتاعهم , شيل كدا "بتاعهم"
> تقريبا كدا هم صح... <br>
> -- جيري كوفين

* <a name="utf-8"></a>
  استخدم `UTF-8` لل انكودين بتاع فايل الكود بتاعك.
<sup>[[link](#utf-8)]</sup>

* <a name="spaces-indentation"></a>
  استخدم **مسافتين** لكل مستوي ف كودك (زي السوفت تاب) مستخدمش هارد تاب
<sup>[[link](#spaces-indentation)]</sup>

  ```ruby
  # سئ - اربع مسافات
  def some_method
      do_something
  end

  # جيد
  def some_method
    do_something
  end
  ```

* <a name="crlf"></a>
  استخدم ستايل اليونكس في نهاية السطور. (\*BSD/Solaris/Linux/macOS مستخدمين نظم التشغيل دول عنهم بشكل افتراضي , الويندوز يوزر بس هو اللي محتاج ياخد باله.)
<sup>[[link](#crlf)]</sup>

  * لو انت بتستخدم ال جيت ف ممكن تكون محتاج تحط
    تعريف لحماية مشروعك من نهاية السطور في نظام الويندوز:

    ```bash
    $ git config --global core.autocrlf true
    ```

* <a name="no-semicolon"></a>
  متسدخدمش `;` عشان تفرق بين الستاتمينت  و للتانية
 استخدم ستاتمينت واحدة في السطر
<sup>[[link](#no-semicolon)]</sup>

  ```ruby
  # سئ
  puts 'foobar'; # فاصلة منقوطة ملهاش لازمة

  puts 'foo'; puts 'bar' # اتنين اكسبريشن في سطر واحد

  # جيد
  puts 'foobar'

  puts 'foo'
  puts 'bar'

  puts 'foo', 'bar' # دا وضع خاص بس
  ```

* <a name="single-line-classes"></a>
  يفضل تعريف الكلاس اللي منغير محتوي في سطر واحد.
<sup>[[link](#single-line-classes)]</sup>

  ```ruby
  # سئ
  class FooError < StandardError
  end

  # شغال
  class FooError < StandardError; end

  # جيد
  FooError = Class.new(StandardError)
  ```

* <a name="no-single-line-methods"></a>
بلاش تكتب دالة في سطر واحد, مع انها مشهورة عامة
في شوية خوصيات في السينتاكس بتاعها بتخلي استخدامها غير مرغوب فيه
علي اي حال مينفعش يبقي في اكتر من اكسبرشن ف سطر واحد في الدالة بتاعتك
<sup>[[link](#no-single-line-methods)]</sup>

  ```ruby
  # سئ
  def too_much; something; something_else; end

  # شغال - لاحظ ان اول ; ضرورية
  def no_braces_method; body end

  # شغال - لاحظ ان تاني ;  اختيارية
  def no_braces_method; body; end

  # شغال - بس منغير ;  بتبقي صعب تقراه
  def some_method() body end

  # جيد
  def some_method
    body
  end
  ```

  استثناء وحيد للقاعدة و هي الدالة الفاضية

  ```ruby
  # جيد
  def no_op; end
  ```

* <a name="spaces-operators"></a>
استخدم المسافات جوالين ال فواصل و النقطتان و الفواصل المنقوطة
ممكن يكون المسافات (او غالبا) ملهاش علاقة بمترجم الروبي .
بس الهدف الاساسي منه كتابة كود سهل القراية
<sup>[[link](#spaces-operators)]</sup>

  ```ruby
  sum = 1 + 2
  a, b = 1, 2
  class FooError < StandardError; end
  ```

  في بعض الاستثنائات منها علامة الأس:

  ```ruby
  # سئ
  e = M * c ** 2

  # جيد
  e = M * c**2
  ```

  استثناء اخر عشان الجذر:

  ```ruby
  # سئ
  o_scale = 1 / 48r

  # جيد
  o_scale = 1/48r
  ```

* <a name="spaces-braces"></a>
  مفيش مسافات بعد `(`, `[` او بعد `]`, `)`.
  Use spaces around `{` and before `}`.
<sup>[[link](#spaces-braces)]</sup>

  ```ruby
  # سئ
  some( arg ).other
  [ 1, 2, 3 ].each{|e| puts e}

  # جيد
  some(arg).other
  [1, 2, 3].each { |e| puts e }
  ```

  `{` و `}` محتاجين بعض التوضيح خاصة اننا بنستخدمه للهاش و البلوك و السترينج

  في الهاش الطريقتين يعتبروا مقبولين.
  بس الطريقة الاولي اوضح شوية  (و اكتر شعبية و استخداما في مجتمع الروبي عامة).
  انما الطريقة التانية ميزيتها انها بتعمل فرق مرئي لشكل الهاش و البلوك .
ايا يكن الطريقة اللي هتخترها استخدمها باتساق.

  ```ruby
  # جيد - مسافة بعد { و قبل  }
  { one: 1, two: 2 }

  # جيد - مفيش مسافة قبل  { و بعد }
  {one: 1, two: 2}
  ```

  مع استخدامها جوا السترينج, متسيبش مسافة فاضية من جوا .

  ```ruby
  # سئ
  "From: #{ user.first_name }, #{ user.last_name }"

  # جيد
  "From: #{user.first_name}, #{user.last_name}"
  ```

* <a name="no-space-bang"></a>
  متسيبش مسافة بعد `!`.
<sup>[[link](#no-space-bang)]</sup>

  ```ruby
  # سئ
  ! something

  # جيد
  !something
  ```

* <a name="no-space-inside-range-literals"></a>
  مفيش مسافات جوا تعريف الراينج.
<sup>[[link](#no-space-inside-range-literals)]</sup>

    ```ruby
    # سئ
    1 .. 3
    'a' ... 'z'

    # جيد
    1..3
    'a'...'z'
    ```

* <a name="indent-when-to-case"></a>
  خلي  `when` و `case`. الاتتنين علي نفس المستوي دا اللي موجود في كتابين
  "The Ruby Programming Language" و "Programming Ruby".
<sup>[[link](#indent-when-to-case)]</sup>

  ```ruby
  # سئ
  case
    when song.name == 'Misty'
      puts 'Not again!'
    when song.duration > 120
      puts 'Too long!'
    when Time.now.hour > 21
      puts "It's too late"
    else
      song.play
  end

  # جيد
  case
  when song.name == 'Misty'
    puts 'Not again!'
  when song.duration > 120
    puts 'Too long!'
  when Time.now.hour > 21
    puts "It's too late"
  else
    song.play
  end
  ```

* <a name="indent-conditional-assignment"></a>
  لما تيجي تحط ناتج الكونداشن بتاعك في متغير ,
  حافظ عليهم بحيث يكونوا في نفس البرانش.
<sup>[[link](#indent-conditional-assignment)]</sup>

  ```ruby
  # سئ - معقد شوية
  kind = case year
  when 1850..1889 then 'Blues'
  when 1890..1909 then 'Ragtime'
  when 1910..1929 then 'New Orleans Jazz'
  when 1930..1939 then 'Swing'
  when 1940..1950 then 'Bebop'
  else 'Jazz'
  end

  result = if some_cond
    calc_something
  else
    calc_something_else
  end

  # جيد - واضح اووي ايه اللي بيحصل
  kind = case year
         when 1850..1889 then 'Blues'
         when 1890..1909 then 'Ragtime'
         when 1910..1929 then 'New Orleans Jazz'
         when 1930..1939 then 'Swing'
         when 1940..1950 then 'Bebop'
         else 'Jazz'
         end

  result = if some_cond
             calc_something
           else
             calc_something_else
           end

  # جيد (اكثر كفاءة في الشكل)
  kind =
    case year
    when 1850..1889 then 'Blues'
    when 1890..1909 then 'Ragtime'
    when 1910..1929 then 'New Orleans Jazz'
    when 1930..1939 then 'Swing'
    when 1940..1950 then 'Bebop'
    else 'Jazz'
    end

  result =
    if some_cond
      calc_something
    else
      calc_something_else
    end
  ```

* <a name="empty-lines-between-methods"></a>
  Use empty lines between method definitions and also to break up methods
  into logical paragraphs internally.
<sup>[[link](#empty-lines-between-methods)]</sup>

  ```ruby
  def some_method
    data = initialize(options)

    data.manipulate!

    data.result
  end

  def some_method
    result
  end
  ```

* <a name="two-or-more-empty-lines"></a>
  متحطش كذا سطر فاضي ورا بعض.
<sup>[[link](#two-or-more-empty-lines)]</sup>

  ```ruby
  # سئ - فيها سطرين فاضيين.
  some_method


  some_method

  # جيد
  some_method

  some_method
  ```

* <a name="empty-lines-around-access-modifier"></a>
  حط سطر فاضي بعد الاكسيس موديفاير.
<sup>[[link](#empty-lines-around-access-modifier)]</sup>

  ```ruby
  # bad
  class Foo
    attr_reader :foo
    def foo
      # do something...
    end
  end

  # good
  class Foo
    attr_reader :foo

    def foo
      # do something...
    end
  end
  ```

* <a name="empty-lines-around-bodies"></a>
  متحطش سطور فاضية حوالين الدوال و الكلاسيس و الموديول .
<sup>[[link](#empty-lines-around-bodies)]</sup>

  ```ruby
  # سئ
  class Foo

    def foo

      begin

        do_something do

          something

        end

      rescue

        something

      end

    end

  end

  # جيد
  class Foo
    def foo
      begin
        do_something do
          something
        end
      rescue
        something
      end
    end
  end
  ```

* <a name="no-trailing-params-comma"></a>
  لما تيجي تستخدم دالة متحطش اخر فاصلة ,خاصة لما يكون الباراميتيرز بتوعها مش علي خطوط منفصلة
<sup>[[link](#no-trailing-params-comma)]</sup>

  ```ruby
  # سئ - اسهل ل تحريك/اضافة/ازالة باراميتير, بس برضه مش احسن حاجة
  some_method(
    size,
    count,
    color,
  )

  # سئ
  some_method(size, count, color, )

  # جيد
  some_method(size, count, color)
  ```

* <a name="spaces-around-equals"></a>
  حط مسافات حوالين  علامة `=` لما تيجي تحط قيمة افتراضية للبراميتيرز :
<sup>[[link](#spaces-around-equals)]</sup>

  ```ruby
  # سئ
  def some_method(arg1=:default, arg2=nil, arg3=[])
    # do something...
  end

  # جيد
  def some_method(arg1 = :default, arg2 = nil, arg3 = [])
    # do something...
  end
  ```

  في حين ان بعض الكتب بتقترح الطريقة الاولي, التاني احسن في الاستخدام (تقدر تقول كدا مقري اكتر).

* <a name="no-trailing-backslash"></a>
  متكملش في سطر جديد لو انت مش محتاج كدا  `\`
  عمليا متكملش في سطر جديد الا لو محتاج كدا في سترانج مثلا
<sup>[[link](#no-trailing-backslash)]</sup>

  ```ruby
  # سئ
  result = 1 - \
           2

  # جيد (بس شكلها وحش زي الزفت)
  result = 1 \
           - 2

  long_string = 'First part of the long string' \
                ' and second part of the long string'
  ```

* <a name="consistent-multi-line-chains"></a>
    عشان تنسق تسلسل الدوال متعدد السطور. There are two popular
    في طريقتين مشهورين في مجتمع الروبي, و الاتنين يعتبروا كويسين&mdash;قدام `.` (الاختيار أ) و تابعة `.` (الاختيار ب).
<sup>[[link](#consistent-multi-line-chains)]</sup>

  * **(الاختيار أ)**
    لما تيجي تستخدم التسلسل في سطر جديد سيب ال`.` في السطر التاني.

    ```ruby
    # سئ - محتاج تراجع السطر الاول عشان تفهم السطر التاني.
    one.two.three.
      four

    # جيد - انت فاهم كويس ايه اللي بيحصل في السطر التاني.
    one.two.three
      .four
    ```

  * **(الاختيار  ب)** لما تيجي تستخدم التسلسل في سطر جديد سيب ال`.` في السطر الاول عشان يبقي فاهم ان في تكملة تحت.

    ```ruby
    # سئ - انت محتاج توصل للسطر التاني عشان تفهم ان لسة التسلسل مخلصش .
    one.two.three
      .four

    # جيد - واضحة اووي من السطر الاول ان لسة في تكملة .
    one.two.three.
      four
    ```

  هتلاقي مناقشة هنا فيها المزايا بتاعت الطريقتين
  [here](https://github.com/bbatsov/ruby-style-guide/pull/176).

* <a name="no-double-indent"></a>
    حاذي علي بارامتر الدالة لو هياخدوا اكتر من سطر.
 لما تيجي تحاذيهم و ميبقوش مناسبين عشان كول السطر ,
 حط واحد بس ف كل سطر و مقبول برضه لو بعد اول واحد
<sup>[[link](#no-double-indent)]</sup>

  ```ruby
  # نقطة البداية (السطر طويل اوي)
  def send_mail(source)
    Mailer.deliver(to: 'bob@example.com', from: 'us@example.com', subject: 'Important message', body: source.text)
  end

  # سئ (مزدوج المسافة)
  def send_mail(source)
    Mailer.deliver(
        to: 'bob@example.com',
        from: 'us@example.com',
        subject: 'Important message',
        body: source.text)
  end

  # جيد
  def send_mail(source)
    Mailer.deliver(to: 'bob@example.com',
                   from: 'us@example.com',
                   subject: 'Important message',
                   body: source.text)
  end

  # جيد - (مسافة عادية)
  def send_mail(source)
    Mailer.deliver(
      to: 'bob@example.com',
      from: 'us@example.com',
      subject: 'Important message',
      body: source.text
    )
  end
  ```

* <a name="align-multiline-arrays"></a>
  حاذي عناصر الاراي اللي بتاخد اكتر من سطر .
<sup>[[link](#align-multiline-arrays)]</sup>

  ```ruby
  # سئ - مسافة البداية
  menu_item = ['Spam', 'Spam', 'Spam', 'Spam', 'Spam', 'Spam', 'Spam', 'Spam',
    'Baked beans', 'Spam', 'Spam', 'Spam', 'Spam', 'Spam']

  # جيد
  menu_item = [
    'Spam', 'Spam', 'Spam', 'Spam', 'Spam', 'Spam', 'Spam', 'Spam',
    'Baked beans', 'Spam', 'Spam', 'Spam', 'Spam', 'Spam'
  ]

  # جيد
  menu_item =
    ['Spam', 'Spam', 'Spam', 'Spam', 'Spam', 'Spam', 'Spam', 'Spam',
     'Baked beans', 'Spam', 'Spam', 'Spam', 'Spam', 'Spam']
  ```

* <a name="underscores-in-numerics"></a>
  حط اندرسكور ل الارقام الكبيرة عشان نعرف نقراها.
<sup>[[link](#underscores-in-numerics)]</sup>

  ```ruby
  # سئ - في كام صفر موجود ؟
  num = 1000000

  # جيد - كدا مخك يقدر يفهمها
  num = 1_000_000
  ```

* <a name="numeric-literal-prefixes"></a>
بيفضل تخلي الحروف سمول لما تستخدم الحروف الرقمية.

  `0o` ل الاوكتل , `0x` لل الهيكساديسيمل  و `0b` لل بيناري.
  متستخدمش ال  `0d` في او الدسيمال .
<sup>[[link](#numeric-literal-prefixes)]</sup>

  ```ruby
  # سئ
  num = 01234
  num = 0O1234
  num = 0X12AB
  num = 0B10101
  num = 0D1234
  num = 0d1234

  # جيد - اسهل عشان تفصل الارقام من البداية
  num = 0o1234
  num = 0x12AB
  num = 0b10101
  num = 1234
  ```

* <a name="rdoc-conventions"></a>
 استخدم [Rdoc][rdoc] و طريقيتها في شرح او توثيق ال API.
متسيبش سطر فاضي بين ال كومنت بلوك و ال `def`.
<sup>[[link](#rdoc-conventions)]</sup>

* <a name="80-character-limits"></a>
اخرك في السطر 80 رمز
<sup>[[link](#80-character-limits)]</sup>

* <a name="no-trailing-whitespace"></a>
  تجنب المسافات الزيادة اللي ملهاش لازمة
<sup>[[link](#no-trailing-whitespace)]</sup>

* <a name="newline-eof"></a>
  في نهاية كل صفحة حط سطر فاضي.
<sup>[[link](#newline-eof)]</sup>

* <a name="no-block-comments"></a>
متستخدمش البلوك كومنت.
مبتتسبقش بمسافة و مش سهل تتفهم زي الكومنتات العادية.
<sup>[[link](#no-block-comments)]</sup>

  ```ruby
  # سئ
  =begin
  comment line
  another comment line
  =end

  # جيد
  # comment line
  # another comment line
  ```

## تركيب الجملة

* <a name="double-colons"></a>
استخدم `::` ك مرجع للثوابت (زي الكلاسيس و الموديل)
 و برضه (زي `Array()` او `Nokogiri::HTML()`).
متستخدمش `::` لل الدوال العادية .
<sup>[[link](#double-colons)]</sup>

  ```ruby
  # سئ
  SomeClass::some_method
  some_object::some_method

  # جيد
  SomeClass.some_method
  some_object.some_method
  SomeModule::SomeClass::SOME_CONST
  SomeModule::SomeClass()
  ```

* <a name="method-parens"></a>
استخدم `def` ب اقواس لما تكون بتاخد براميتيرز.
و شيلهم لو هي مش بتاخد حاجة.
<sup>[[link](#method-parens)]</sup>

   ```ruby
   # سئ
   def some_method()
     # اللي جوا اتشال
   end

   # جيد
   def some_method
     # اللي جوا اتشال
   end

   # سئ
   def some_method_with_parameters param1, param2
     # اللي جوا اتشال
   end

   # جيد
   def some_method_with_parameters(param1, param2)
     # اللي جوا اتشال
   end
   ```

* <a name="method-invocation-parens"></a>
استخدم الاقواس حوالين الارجيومنت الدوال المستعاه
 خاصة لو اول ارجيومنت بيبدا ب قوس مفتوح `)`,
  زي هنا `f((3 + 2) + 1)`.
<sup>[[link](#method-invocation-parens)]</sup>

  ```ruby
  # سئ
  x = Math.sin y
  # جيد
  x = Math.sin(y)

  # سئ
  array.delete e
  # جيد
  array.delete(e)

  # سئ
  temperance = Person.new 'Temperance', 30
  # جيد
  temperance = Person.new('Temperance', 30)
  ```

  دايما شيل الاقواس في الحالات دي

  * دالة مش بتاخد ارجيومنت:

    ```ruby
    # سئ
    Kernel.exit!()
    2.even?()
    fork()
    'test'.upcase()

    # جيد
    Kernel.exit!
    2.even?
    fork
    'test'.upcase
    ```

  * دوال هم جزي من DSL الداخلي  (زي ال, Rake, Rails, RSpec):

    ```ruby
    # سئ
    validates(:name, presence: true)
    # جيد
    validates :name, presence: true
    ```

  * الدوال الي ليها صفة "الكلمة" في الروبي:

    ```ruby
    class Person
      # سئ
      attr_reader(:name, :age)
      # جيد
      attr_reader :name, :age

      # شلنا باقي الكلاس
    end
    ```

  ممكن نشيل الاقواس ل

  * الدوال الي ليها صفة "الكلمة" في الروبي, بس تكون مش معبرة:

    ```Ruby
    # جيد
    puts(temperance.age)
    system('ls')
    # برضه جيد
    puts temperance.age
    system 'ls'
    ```
* <a name="optional-arguments"></a>
    عرف الارجيومنت الاختيارية في النهاية.
  الروبي عندها شويه نتايج غير متوقعة لما تيجي تنادي دوال
 و يكون عندها ارجيومنت اختيارية في النص.
<sup>[[link](#optional-arguments)]</sup>

  ```ruby
  # سئ
  def some_method(a = 1, b = 2, c, d)
    puts "#{a}, #{b}, #{c}, #{d}"
  end

  some_method('w', 'x') # => '1, 2, w, x'
  some_method('w', 'x', 'y') # => 'w, 2, x, y'
  some_method('w', 'x', 'y', 'z') # => 'w, x, y, z'

  # جيد
  def some_method(c, d, a = 1, b = 2)
    puts "#{a}, #{b}, #{c}, #{d}"
  end

  some_method('w', 'x') # => '1, 2, w, x'
  some_method('w', 'x', 'y') # => 'y, 2, w, x'
  some_method('w', 'x', 'y', 'z') # => 'y, z, w, x'
  ```

* <a name="parallel-assignment"></a>
   تحجنب التعريف المتوازي للمتغيرات.
  هو بيبقي مسموح في حالة القيمة راجعة من دالة .
 استخدمه مع علامة النجمة , او تبديل قيم المتغيرات
 من الاخر هو صعب يتقري مش زي اما تعرف كل حاجة لوحدها
<sup>[[link](#parallel-assignment)]</sup>

  ```ruby
  # سئ
  a, b, c, d = 'foo', 'bar', 'baz', 'foobar'

  # جيد
  a = 'foo'
  b = 'bar'
  c = 'baz'
  d = 'foobar'

  # جيد - استبدال قيم المتغيرات
  # استبدال قيم المتغيرات حالة خاصة , عشان هتسمحلك
  # انك تغير القيم بتاعت كل متغير.
  a = 'foo'
  b = 'bar'

  a, b = b, a
  puts a # => 'bar'
  puts b # => 'foo'

  # جيد - اللي الدالة بترجعه
  def multi_return
    [1, 2]
  end

  first, second = multi_return

  # جيد - بيستخدم علامة النجمة
  first, *list = [1, 2, 3, 4] # first => 1, list => [2, 3, 4]

  hello_array = *'Hello' # => ["Hello"]

  a = *(1..3) # => [1, 2, 3]
  ```

* <a name="trailing-underscore-variables"></a>
   تجنب استخدام اسامي  الاندرسكور في المتغيرات خلال ال التعريف الموازي .
  التسمية المتغيرات بالاندرس سكور بيبقي مفضل عشان السياق اللي بتوفره .
 هي بتبقي مهمة لما بيكون في متغير من سبلات و متعرف علي شمال التعريف.
 المتغير من نوع سبلات مش بيكون اندر سكور
<sup>[[link]](#trailing-underscore-variables)</sup>

  ```ruby
  # سئ
  foo = 'one,two,three,four,five'
  # تعريف عديم النفع بيقول معلمات مش مهمة
  first, second, _ = foo.split(',')
  first, _, _ = foo.split(',')
  first, *_ = foo.split(',')


  # جيد
  foo = 'one,two,three,four,five'
  # لاندر سكور مهم عشان يوضحلك انك محتاجهم كلهم
  # معادا اخر واحد اللي هو اندرسكور
  *beginning, _ = foo.split(',')
  *beginning, something, _ = foo.split(',')

  a, = foo.split(',')
  a, b, = foo.split(',')
  # تعريف غير مهم ل متغير غير مستخدم , بس التعريف دا
  # بيوفر معلومات مهمة.
  first, _second = foo.split(',')
  first, _second, = foo.split(',')
  first, *_ending = foo.split(',')
  ```

* <a name="no-for-loops"></a>
   مستخدمش `for` لحد ما تعرف السبب بالظبط .
  اغلب الوقت حاجات كتير المفروض تستخدمها بدلها .
 `for` اتعملت علي طراز ال `each`
  (كدا انت بتعمل مستوي جديد غير مباشر), الفكرة كلها ان ال `for`
  مبتعملش سكوب جديد, بمعني الفاريبال اللي هتعملها جوه هتتشاف برا عادي.
<sup>[[link](#no-for-loops)]</sup>

  ```ruby
  arr = [1, 2, 3]

  # سئ
  for elem in arr do
    puts elem
  end

  # لاحظ هنا elem  بيستخدموها برا اللوب عادي .
  elem # => 3

  # جيد
  arr.each { |elem| puts elem }

  # هنا بقي متقدرش تستخدم elem برا البلوك
  elem # => NameError: undefined local variable or method `elem'
  ```

* <a name="no-then"></a>
  متستخدمش `then` لبلوك متعددة السطور`if`/`unless`.
<sup>[[link](#no-then)]</sup>

  ```ruby
  # سئ
  if some_condition then
    # اللي هنا اتشال
  end

  # جيد
  if some_condition
    # اللي هنا اتشال
  end
  ```

* <a name="same-line-condition"></a>
  حط دايما الشرط بتاع `if`/`unless` علي نفس السطر.
 في حالات تعدد سطور الكوندشن
<sup>[[link](#same-line-condition)]</sup>

  ```ruby
  # سئ
  if
    some_condition
    do_something
    do_something_else
  end

  # جيد
  if some_condition
    do_something
    do_something_else
  end
  ```

* <a name="ternary-operator"></a>
  بيفضل استخدام علامات ال (`:?`)  عن `if/then/else/end`.
 عشان هي اكتر انتشارا و واضحة اكتر .
<sup>[[link](#ternary-operator)]</sup>

  ```ruby
  # سئ
  result = if some_condition then something else something_else end

  # جيد
  result = some_condition ? something : something_else
  ```

* <a name="no-nested-ternary"></a>
 متكتبش اكتر من واحدة في نفس السطر .
 فيما معناه مينفعش تكتب واحدة و جواها واحدة تانية .
 في الحالة دي بيفضل تعملها ب `if/else` .
<sup>[[link](#no-nested-ternary)]</sup>

  ```ruby
  # سئ
  some_condition ? (nested_condition ? nested_something : nested_something_else) : something_else

  # جيد
  if some_condition
    nested_condition ? nested_something : nested_something_else
  else
    something_else
  end
  ```

* <a name="no-semicolon-ifs"></a>
 متعملش `if x; ...`.
 استخدم بدالهم علامة الترناري.
<sup>[[link](#no-semicolon-ifs)]</sup>

  ```ruby
  # سئ
  result = if some_condition; something else something_else end

  # جيد
  result = some_condition ? something : something_else
  ```

* <a name="use-if-case-returns"></a>
 استفيد من ان `if` و `case` بيرجعوا الناتج .
<sup>[[link](#use-if-case-returns)]</sup>

  ```ruby
  # سئ
  if condition
    result = x
  else
    result = y
  end

  # جيد
  result =
    if condition
      x
    else
      y
    end
  ```

* <a name="one-line-cases"></a>
استخدم `when x then ...` في حالات السطر الواحد .
عشان الطريقة المختلفة بتاعت `when x:...` اتشالت من الروبي نسخة 1.9 .
<sup>[[link](#one-line-cases)]</sup>

* <a name="no-when-semicolons"></a>
  متستخدمش `when x; ...`. بص علي القاعدة اللي فاتت .
<sup>[[link](#no-when-semicolons)]</sup>

* <a name="bang-not-not"></a>
استخدم `!` بدل `not` .
<sup>[[link](#bang-not-not)]</sup>

  ```ruby
  # سئ - عشان اولوية الاقواس.
  x = (not something)

  # جيد
  x = !something
  ```

* <a name="no-bang-bang"></a>
  تجنب استخدام `!!`.
<sup>[[link](#no-bang-bang)]</sup>
  `!!` بتحول القيمة ل بوليان, بس انت مش محتاج الكلام دا في الكوندشن.
  لو عاوز تتاكد من ان قيمتها `nil` استخدم `nil?`
  ```ruby
  # سئ
  x = 'test'
  # طريقة تاكيد غير واضحة
  if !!x
    # اللي هنا اتشال
  end

  # جيد
  x = 'test'
  if x
    # اللي هنا اتشال
  end
  ```

* <a name="no-and-or-or"></a>
  علامتين ال `and` و `or` محظور استخدامهم .
  هي بتضيف قابلية بسيطة علي قرايه اسهل بس بتبقي سبب لوجود اخطاء برمجية .
 في البوليان اكسبريشنز دايما يفضل تستخدم  `&&` و `||` بدلهم .
 استخدام `if` و `unless`; `&&` و `||` مقبولين برضه بس مش واضحين اووي .
<sup>[[link](#no-and-or-or)]</sup>

  ```ruby
  # سئ
  # boolean expression
  ok = got_needed_arguments and arguments_are_valid

  # control flow
  document.save or fail(RuntimeError, "Failed to save document!")

  # جيد
  # boolean expression
  ok = got_needed_arguments && arguments_are_valid

  # control flow
  fail(RuntimeError, "Failed to save document!") unless document.save

  # تمام
  # control flow
  document.save || fail(RuntimeError, "Failed to save document!")
  ```

* <a name="no-multiline-ternary"></a>
  تجنب استخدام اكتر من سطر مع `?:` (the ternary operator); استخدم `if`/`unless` بدالهم .
<sup>[[link](#no-multiline-ternary)]</sup>

* <a name="if-as-a-modifier"></a>
بيفضل استخدام `if`/`unless` لما تكون هتعملها في سطر واحد .
برضه حل تاني مختلف انك تستخدم `&&`/`||`.
<sup>[[link](#if-as-a-modifier)]</sup>

  ```ruby
  # سئ
  if some_condition
    do_something
  end

  # جيد
  do_something if some_condition

  # حل تاني كويس
  some_condition && do_something
  ```

* <a name="no-multiline-if-modifiers"></a>
  ابعد عن استخدام `if`/`unless` في اخر البلوك اللي بيتكون من اكتر من سطر .
<sup>[[link](#no-multiline-if-modifiers)]</sup>

  ```ruby
  # سئ
  10.times do
    # multi-line body omitted
  end if some_condition

  # جيد
  if some_condition
    10.times do
      # multi-line body omitted
    end
  end
  ```

* <a name="no-nested-modifiers"></a>
  بلاش تعمل `if`/`unless`/`while`/`until` جوا بعض .
  يفضل `&&`/`||` لو هينفع يعني .
<sup>[[link](#no-nested-modifiers)]</sup>

  ```ruby
  # سئ
  do_something if other_condition if some_condition

  # جيد
  do_something if some_condition && other_condition
  ```

* <a name="unless-for-negatives"></a>
استخدم `unless` احسن من `if` لو بتتاكد من الحالة غلط .
<sup>[[link](#unless-for-negatives)]</sup>

  ```ruby
  # سئ
  do_something if !some_condition

  # سئ
  do_something if not some_condition

  # جيد
  do_something unless some_condition

  # حالة تانية كويسة
  some_condition || do_something
  ```

* <a name="no-else-with-unless"></a>
متستخدمش `unless` مع `else`.
اكتبها من اول و جديد وحط الحالة الايجابية الاول .
<sup>[[link](#no-else-with-unless)]</sup>

  ```ruby
  # سئ
  unless success?
    puts 'failure'
  else
    puts 'success'
  end

  # جيد
  if success?
    puts 'success'
  else
    puts 'failure'
  end
  ```

* <a name="no-parens-around-condition"></a>
  متستخدمش الاقواس حوالين الكونديشن
<sup>[[link](#no-parens-around-condition)]</sup>

  ```ruby
  # سئ
  if (x > 10)
    # اللي هنا اتشال
  end

  # جيد
  if x > 10
    # اللي هنا اتشال
  end
  ```
خد بالك ان في استثناء للقاعدة دي, اللي هي
[safe assignment in condition](#safe-assignment-in-condition).
* <a name="no-multiline-while-do"></a>
  متستخدمش `while/until condition do` لاكتر من سطر استخدم `while/until`.
<sup>[[link](#no-multiline-while-do)]</sup>

  ```ruby
  # سئ
  while x > 5 do
    # اللي هنا اتشال
  end

  until x > 5 do
    # اللي هنا اتشال
  end

  # جيد
  while x > 5
    # اللي هنا اتشال
  end

  until x > 5
    # اللي هنا اتشال
  end
  ```

* <a name="while-as-a-modifier"></a>
  يفضل استخدام  `while/until` في حالة هتكتبها ف سطر واحد .
<sup>[[link](#while-as-a-modifier)]</sup>

  ```ruby
  # سئ
  while some_condition
    do_something
  end

  # جيد
  do_something while some_condition
  ```

* <a name="until-for-negatives"></a>
  يفضل `until` عن `while` في الحالات السلبية
<sup>[[link](#until-for-negatives)]</sup>

  ```ruby
  # سئ
  do_something while !some_condition

  # جيد
  do_something until some_condition
  ```

* <a name="infinite-loop"></a>
 لما تكون عاوز تعمل لوب لا نهائي استخدم `Kernel#loop` بدل `while/until` .
<sup>[[link](#infinite-loop)]</sup>

    ```ruby
    # سئ
    while true
      do_something
    end

    until false
      do_something
    end

    # جيد
    loop do
      do_something
    end
    ```

* <a name="loop-with-break"></a>
  استخدم `Kernel#loop` مع ال `break`بدل من `begin/end/until` او  `begin/end/while`
  في حالة ال post-loop
<sup>[[link](#loop-with-break)]</sup>

  ```ruby
  # سئ
  begin
    puts val
    val += 1
  end while val < 0

  # جيد
  loop do
    puts val
    val += 1
    break unless val < 0
  end
  ```

* <a name="no-braces-opts-hash"></a>
  شيل الاقواس الخارجيه اللي حوالين الهاش .
<sup>[[link](#no-braces-opts-hash)]</sup>

  ```ruby
  # سئ
  user.set({ name: 'John', age: 45, permissions: { read: true } })

  # جيد
  user.set(name: 'John', age: 45, permissions: { read: true })
  ```

* <a name="no-dsl-decorating"></a>
شيل الاقواس الخارجية للدوال الجزء من DSL .
<sup>[[link](#no-dsl-decorating)]</sup>

  ```ruby
  class Person < ActiveRecord::Base
    # سئ
    validates(:name, { presence: true, length: { within: 1..10 } })

    # جيد
    validates :name, presence: true, length: { within: 1..10 }
  end
  ```

* <a name="single-action-blocks"></a>
  استخدم اختصار ال Proc في حالة الدوال اللي بتعمل عملية واحدة.
<sup>[[link](#single-action-blocks)]</sup>

  ```ruby
  # سئ
  names.map { |name| name.upcase }

  # جيد
  names.map(&:upcase)
  ```

* <a name="single-line-blocks"></a>
  يفضل استخدام `{...}` عن `do...end` في حالة البلوك اللي بيتكون من سطر.
  تجنب استخدام `{...}` في حالة البلوك بيتكون من اكتر من سطر (تسلسل السطور دايما وحش).
 دايما استخدم  `do...end` لل control flow و تعريف الدوال (زي اللي في Rakefiles و DSL )
  ابعد عن `do...end` في التسلسل .
<sup>[[link](#single-line-blocks)]</sup>

  ```ruby
  names = %w[Bozhidar Steve Sarah]

  # سئ
  names.each do |name|
    puts name
  end

  # جيد
  names.each { |name| puts name }

  # سئ
  names.select do |name|
    name.start_with?('S')
  end.map { |name| name.upcase }

  # جيد
  names.select { |name| name.start_with?('S') }.map(&:upcase)
  ```
  في ناس هتجادل و تقول ان استخدام الاقواس دي {...} شكلها احسن,
 بس المفروض يسألوا نفسهم - هل الكود دا فعلا ينفع يتقري , و محتوي الدالة ممكن تخرجه بسهوله ؟

* <a name="block-argument"></a>
  حط في اعتبارك استخدام البلوك ك ارجيومنت بدل ما تضطر تبعت بلوك من جوا.
 خد بالك ان دا بيأثر علي الاداء , عشان البلوك بيتحول ل بروك.
<sup>[[link](#block-argument)]</sup>

  ```ruby
  require 'tempfile'

  # سئ
  def with_tmp_dir
    Dir.mktmpdir do |tmp_dir|
      Dir.chdir(tmp_dir) { |dir| yield dir }  # block just passes arguments
    end
  end

  # جيد
  def with_tmp_dir(&block)
    Dir.mktmpdir do |tmp_dir|
      Dir.chdir(tmp_dir, &block)
    end
  end

  with_tmp_dir do |dir|
    puts "dir is accessible as a parameter and pwd is set: #{dir}"
  end
  ```

* <a name="no-explicit-return"></a>
  متحطش `return` لما ميبقاش ليها لازمة.
<sup>[[link](#no-explicit-return)]</sup>

  ```ruby
  # سئ
  def some_method(some_arr)
    return some_arr.size
  end

  # جيد
  def some_method(some_arr)
    some_arr.size
  end
  ```

* <a name="no-self-unless-required"></a>
  متستخدمش `self` لما ميبقاش ليها لازمة
 (هي مهمة بس لما بتستخدم  self write accessor, او تعيد كتابة علامة, تسميه دالة باسم متاخد اصلا)
<sup>[[link](#no-self-unless-required)]</sup>

  ```ruby
  # سئ
  def ready?
    if self.last_reviewed_at > self.last_updated_at
      self.worker.update(self.content, self.options)
      self.status = :in_progress
    end
    self.status == :verified
  end

  # جيد
  def ready?
    if last_reviewed_at > last_updated_at
      worker.update(content, options)
      self.status = :in_progress
    end
    status == :verified
  end
  ```

* <a name="no-shadowing"></a>
و نتيجة لكدا, بطل تضلل الدوال بتاعتك بالمتغيرا طالما يعني الاتنين واحد .
<sup>[[link](#no-shadowing)]</sup>

  ```ruby
  class Foo
    attr_accessor :options

    # تمام
    def initialize(options)
      self.options = options
      # both options and self.options are equivalent here
    end

    # سئ
    def do_something(options = {})
      unless options[:when] == :later
        output(self.options[:message])
      end
    end

    # جيد
    def do_something(params = {})
      unless params[:when] == :later
        output(options[:message])
      end
    end
  end
  ```

* <a name="safe-assignment-in-condition"></a>
  متستخدمش القيمة اللي راجعة من `=` (علامة اليساوي) في الكونديشنز طالما مش محطوطين بين اقواس.
و دي حاجة مشهورة جا عند مبرمجين الروبي و شاعات بيحبوا يسموها *safe assignment in condition*
<sup>[[link](#safe-assignment-in-condition)]</sup>

  ```ruby
  # سئ
  if v = array.grep(/foo/)
    do_something(v)
    # شوية كود
  end

  # جيد (MRI هيقولك انها غلط بس روبوكب هيشتغل عادي قشطة)
  if (v = array.grep(/foo/))
    do_something(v)
    # شوية كود
  end

  # جيد
  v = array.grep(/foo/)
  if v
    do_something(v)
    # some code
  end
  ```

* <a name="self-assignment"></a>
استخدم الاختصارات لما تيجي تخلي المتغير يزود علي نفسه لما يكون ينفع.
<sup>[[link](#self-assignment)]</sup>

  ```ruby
  # سئ
  x = x + y
  x = x * y
  x = x**y
  x = x / y
  x = x || y
  x = x && y

  # جيد
  x += y
  x *= y
  x **= y
  x /= y
  x ||= y
  x &&= y
  ```

* <a name="double-pipe-for-uninit"></a>
  استخدم `||=` لما تعرف المتغير بقيمة اذا كان مش متعرف .
<sup>[[link](#double-pipe-for-uninit)]</sup>

  ```ruby
  # سئ
  name = name ? name : 'Bozhidar'

  # سئ
  name = 'Bozhidar' unless name

  # جيد حطلها القيمة دي 'Bozhidar' لو كانت هي ب nil  او false
  name ||= 'Bozhidar'
  ```

* <a name="no-double-pipes-for-bools"></a>
  متستخدمش ال `||=` لما تيجي تعرف boolean .
 (حط في اعتبارك اللي ممكن يحصل لو القيمة اللي موجودة ب `false`)
<sup>[[link](#no-double-pipes-for-bools)]</sup>

  ```ruby
  # سئ - القيمة هتبقي ب true  حتي لو متعرفة قبل كدا ب false.
  enabled ||= true

  # جيد
  enabled = true if enabled.nil?
  ```

* <a name="double-amper-preprocess"></a>
  استخدم `&&=` مع المتغيرات اللي ممكن او مش ممكن تكون موجودة.
 استخدام `&&=` هيغير قيمة المتغير في حالة انه فعلا موجود بس, بيوفر عليك انك تتاكد من وجوده ب `if`.
<sup>[[link](#double-amper-preprocess)]</sup>

  ```ruby
  # سئ
  if something
    something = something.downcase
  end

  # سئ
  something = something ? something.downcase : nil

  # تمام
  something = something.downcase if something

  # جيد
  something = something && something.downcase

  # احسن
  something &&= something.downcase
  ```

* <a name="no-case-equality"></a>
  تجنب استخدام `===` (case equality operator).
  من اسمها كدا باين معناها انها بترجع ل تعبير ال `case`
و بعيدا عن كدا هي بتخلي كودك يلغبط .
<sup>[[link](#no-case-equality)]</sup>

  ```ruby
  # سئ
  Array === something
  (1..100) === 7
  /something/ === some_string

  # جيد
  something.is_a?(Array)
  (1..100).include?(7)
  some_string =~ /something/
  ```

* <a name="eql"></a>
   متستخدمش `eql?` لما ينفع تستخدم `==` .
  عملية المقارنة اللي بتحصل بالعلامة دي `eql?` الاحتياج لاستخدامها نادر عمليا .
<sup>[[link](#eql)]</sup>

  ```ruby
  # سئ - eql? هتعمل نفس الي == بتعمله مع السترينج
  'ruby'.eql? some_str

  # جيد
  'ruby' == some_str
  1.0.eql? x # eql? استخدامها هنا اكتر منطقية لو حابب تفرق بين الاعداد الصحيحة و العشرية
  ```

* <a name="no-cryptic-perlisms"></a>
  تجنب استخدام المتغيات اللي علي طراز لغة بيرل (زي `$:`, `$;`, و هكذا ).
  هم مخفيين جدا دا غير ان استخدامهم محدش بيحبذه طالما مش في one-liner scripts .
 استخدم حاجة الني ادمين يفهموها و تكون موجوده في مكتبة ال `English` .
<sup>[[link](#no-cryptic-perlisms)]</sup>

  ```ruby
  # سئ
  $:.unshift File.dirname(__FILE__)

  # جيد
  require 'English'
  $LOAD_PATH.unshift File.dirname(__FILE__)
  ```

* <a name="parens-no-spaces"></a>
  متسيبش مسافة فاضية ما بين اسم الدالة و الاقواس .
<sup>[[link](#parens-no-spaces)]</sup>

  ```ruby
  # سئ
  f (3 + 2) + 1

  # جيد
  f(3 + 2) + 1
  ```

* <a name="always-warn-at-runtime"></a>
  دايما لما تيجي تشغل كود روبي ابعتله `-w` عشان يحذرك لو نسيت حاجة من اللي قلناهم فوق !
<sup>[[link](#always-warn-at-runtime)]</sup>

* <a name="no-nested-methods"></a>
  متحطش دالة جوا دالة, استخدم lambda بدالها .
 تعريف دالتين في مكان واحد بينتج عنه دوال عندهم نفس السكوب .
 غير كدا كمان "الدوال اللي جوا بعض" هيتم تعريفهم من جديد في كل مرة الدالة تتعرف فيه .
<sup>[[link](#no-nested-methods)]</sup>

  ```ruby
  # سئ
  def foo(x)
    def bar(y)
      # اللي هنا اتشال
    end

    bar(x)
  end

  # جيد - بتعمل زيها زي اللي فاتت بس مبيحصلش تعريف جديد للدوال كل مرة .
  def bar(y)
    # اللي هنا اتشال 
  end

  def foo(x)
    bar(x)
  end

  # برضه جيد
  def foo(x)
    bar = ->(y) { ... }
    bar.call(x)
  end
  ```

* <a name="lambda-multi-line"></a>
  لو هتكتب ال lambda في سطر واحد استخدم السنتاكس الجديد بتاعها.
 و لو اكتر من سطر يبقي استخدم بتاع ال  `lambda` اللي بياخد كذا سطر .
<sup>[[link](#lambda-multi-line)]</sup>

  ```ruby
  # سئ
  l = lambda { |a, b| a + b }
  l.call(1, 2)

  # هو صح, بس متعملش الهبل دا .
  l = ->(a, b) do
    tmp = a * 7
    tmp * b / 50
  end

  # جيد
  l = ->(a, b) { a + b }
  l.call(1, 2)

  l = lambda do |a, b|
    tmp = a * 7
    tmp * b / 50
  end
  ```

* <a name="stabby-lambda-with-args"></a>
متشيلش الاقواس بتاعت البراميتر لما تيجي تعمل stabby lambda معاها براميتير.
<sup>[[link](#stabby-lambda-with-args)]</sup>

  ```ruby
  # سئ
  l = ->x, y { something(x, y) }

  # جيد
  l = ->(x, y) { something(x, y) }
  ```

* <a name="stabby-lambda-no-args"></a>
شيل الاقواس لما تيجي تعمل stabby lambda منغير براميتير.
<sup>[[link](#stabby-lambda-no-args)]</sup>

  ```ruby
  # سئ
  l = ->() { something }

  # جيد
  l = -> { something }
  ```

* <a name="proc"></a>
  يفصل `proc` عن `Proc.new`.
<sup>[[link](#proc)]</sup>

  ```ruby
  # سئ
  p = Proc.new { |n| puts n }

  # جيد
  p = proc { |n| puts n }
  ```

* <a name="proc-call"></a>
  بيفضل `proc.call()` عن `proc[]` او `proc.()` في الحالتين lambdas و procs.
<sup>[[link](#proc-call)]</sup>

  ```ruby
  # سئ - كانك بتستخدم Enumeration.
  l = ->(v) { puts v }
  l[1]

  # also bad - uncommon syntax
  l = ->(v) { puts v }
  l.(1)

  # جيد
  l = ->(v) { puts v }
  l.call(1)
  ```

* <a name="underscore-unused-vars"></a>
  حط `_` قبل اي اسم متغير او براميتر مش هتستخدمهم.
  ممكن برضه تستخدم `_` بس (بس برضه هي مش معبرة اوي).
 الطريقة دي بيفهمها محلل الروبي و ادوات تانية زي روبوكب
 و مش هيطلعلك تحذر لعدم استخدام المتغير المعرف .
<sup>[[link](#underscore-unused-vars)]</sup>

  ```ruby
  # سئ
  result = hash.map { |k, v| v + 1 }

  def something(x)
    unused_var, used_var = something_else(x)
    # شوية كود
  end

  # جيد
  result = hash.map { |_k, v| v + 1 }

  def something(x)
    _unused_var, used_var = something_else(x)
    # some code
  end

  # جيد
  result = hash.map { |_, v| v + 1 }

  def something(x)
    _, used_var = something_else(x)
    # some code
  end
  ```

* <a name="global-stdout"></a>
  استخدم `$stdout/$stderr/$stdin` بدل من `STDOUT/STDERR/STDIN`.
  عشان `STDOUT/STDERR/STDIN` ثوابت تمبتتغيش .
 في حين ان انت ممكن تغير قيميتهم (ممكن عاوز تغير مسار حاجة) ساعتها هيجيلك نحذير من محول الروبي .
<sup>[[link](#global-stdout)]</sup>

* <a name="warn"></a>
  استخدم  `warn` بدلا من  `$stderr.puts`.
  بغض النظر انها بتقول المختصر المفيد . 
  بس `warn` بتسمحلك انك تمنع التحذيرات لو عاوز . 
 (عن طريق ان تجط مستوي التحذير ل 0 عن طريق `-W0`).
<sup>[[link](#warn)]</sup>

* <a name="sprintf"></a>
  يفضل استخدام `sprintf` و اللي زيها `format` عن انك تستخدم `String#%`
<sup>[[link](#sprintf)]</sup>

  ```ruby
  # سئ
  '%d %d' % [20, 10]
  # => '20 10'

  # جيد
  sprintf('%d %d', 20, 10)
  # => '20 10'

  # جيد
  sprintf('%<first>d %<second>d', first: 20, second: 10)
  # => '20 10'

  format('%d %d', 20, 10)
  # => '20 10'

  # جيد
  format('%<first>d %<second>d', first: 20, second: 10)
  # => '20 10'
  ```

* <a name="named-format-tokens"></a>
  لما تيجي تستخد الاسامي في ال format string tokens . 
 يفضل `%<name>s` عن `%{name}` عشان يحدد معلومات نوع المتغير .
<sup>[[link]](#named-format-tokens)</sup>

  ```ruby
  # سئ
  format('Hello, %{name}', name: 'John')

  # جيد
  format('Hello, %<name>s', name: 'John')
  ```

* <a name="array-join"></a>
  يفضل استخدام `Array#join` عن اللي ممكن تخدعك شوية `Array#*` لما تيجي تبعتلها سترنج .
<sup>[[link](#array-join)]</sup>

  ```ruby
  # سئ
  %w[one two three] * ', '
  # => 'one, two, three'

  # جيد
  %w[one two three].join(', ')
  # => 'one, two, three'
  ```

* <a name="array-coercion"></a>
  Use `Array()` instead of explicit `Array` check or `[*var]`, when dealing
  with a variable you want to treat as an Array, but you're not certain it's an
  array.
<sup>[[link](#array-coercion)]</sup>

  ```ruby
  # سئ
  paths = [paths] unless paths.is_a? Array
  paths.each { |path| do_something(path) }

  # سئ (دايما هعمل array جديد)
  [*paths].each { |path| do_something(path) }

  # جيد (و مقري اكتر شوية)
  Array(paths).each { |path| do_something(path) }
  ```

* <a name="ranges-or-between"></a>
  استخدم ranges او `Comparable#between?` بدل ما تعمل علامات مقارنة منطقية تبقي معقدة طالما ممكن تعملها .
<sup>[[link](#ranges-or-between)]</sup>

  ```ruby
  # سئ
  do_something if x >= 1000 && x <= 2000

  # جيد
  do_something if (1000..2000).include?(x)

  # جيد
  do_something if x.between?(1000, 2000)
  ```

* <a name="predicate-methods"></a>
  يفضل استخدام الدوال الجاهزة اللي زي `==`.
 مقارنات الارقام كويسة برضه.
<sup>[[link](#predicate-methods)]</sup>

  ```ruby
  # سئ
  if x % 2 == 0
  end

  if x % 2 == 1
  end

  if x == nil
  end

  # جيد
  if x.even?
  end

  if x.odd?
  end

  if x.nil?
  end

  if x.zero?
  end

  if x == 0
  end
  ```

* <a name="no-non-nil-checks"></a>
  اتاكد من ان القيمة `nil` بشكل مباشر .
 طالما مش بتتعامل مع قيمة boolean .
<sup>[[link](#no-non-nil-checks)]</sup>

    ```ruby
    # سئ
    do_something if !something.nil?
    do_something if something != nil

    # جيد
    do_something if something

    # جيد - لانه بيتعامل مع boolean
    def value_set?
      !@some_boolean.nil?
    end
    ```

* <a name="no-BEGIN-blocks"></a>
  تجنب استخدام  `BEGIN` في البلوك .
<sup>[[link](#no-BEGIN-blocks)]</sup>

* <a name="no-END-blocks"></a>
  متسخدمش `END` . استخدم بدالها `Kernel#at_exit` .
<sup>[[link](#no-END-blocks)]</sup>

  ```ruby
  # سئ
  END { puts 'Goodbye!' }

  # جيد
  at_exit { puts 'Goodbye!' }
  ```

* <a name="no-flip-flops"></a>
  تجنب استخدام flip-flops.
<sup>[[link](#no-flip-flops)]</sup>

* <a name="no-nested-conditionals"></a>
 تجنب استخدام كوندشن جوا بعض .
<sup>[[link](#no-nested-conditionals)]</sup>
 يفضل guard clause لما يكون متاح ليك تتاكد من عدم صحة البيانات .
 دي حاجة بتبقي موجودة ف الاول خالص بس بترجع الناتج في اقرب وقت ممكن .

  ```ruby
  # سئ
  def compute_thing(thing)
    if thing[:foo]
      update_with_bar(thing[:foo])
      if thing[:foo][:bar]
        partial_compute(thing)
      else
        re_compute(thing)
      end
    end
  end

  # جيد
  def compute_thing(thing)
    return unless thing[:foo]
    update_with_bar(thing[:foo])
    return re_compute(thing) unless thing[:foo][:bar]
    partial_compute(thing)
  end
  ```

  بيفضل استخدام `next` بدل من الكوندشن جوا.

  ```ruby
  # سئ
  [0, 1, 2, 3].each do |item|
    if item > 1
      puts item
    end
  end

  # جيد
  [0, 1, 2, 3].each do |item|
    next unless item > 1
    puts item
  end
  ```

* <a name="map-find-select-reduce-size"></a>
  بيفضل  `map` عن `collect`, `find` عن `detect`, `select` عن `find_all`,
 `reduce` عن `inject` و `size` عن `length`. دا مش متطلب صعب;
  لو استخدام الحاجات الشبيهة بتحسب طريقة قراية الكود, في يحالة دي قشطة استخدمها.
  الدوال دي اتاخدت من smalltalk و مش موجودة في لغات البرمجة التانيه.
 السبب في استخدام `select` للتشجيع عنها عن `find_all` تمام زيها زي `reject` 
و اسمها كمان معبر عن نفسه اووي.
<sup>[[link](#map-find-select-reduce-size)]</sup>

* <a name="count-vs-size"></a>
  متسخدمش `count` كبديل ل `size`.
 في حالة `Enumerable` objects تكون غير ال Array عشان في الحالة دي هيلف حوالين المجموعة كلها عشان يقولك الحجم .
<sup>[[link](#count-vs-size)]</sup>

  ```ruby
  # سئ
  some_hash.count

  # جيد
  some_hash.size
  ```

* <a name="flat-map"></a>
  استخدم `flat_map` بدل من `map` + `flatten`. 
 الكلام دا مش لل Array اللي عمقة اكتر من 2 
 زي دا مثلا `users.first.songs == ['a', ['b','c']]`,
 استخدم `map + flatten` بدل من  `flat_map`.
 `flat_map` بتسطح الاراي لعمق 1
 بس `flatten` بتسطحه بكل الطرق .
<sup>[[link](#flat-map)]</sup>

  ```ruby
  # سئ
  all_songs = users.map(&:songs).flatten.uniq

  # جيد
  all_songs = users.flat_map(&:songs).uniq
  ```

* <a name="reverse-each"></a>
 يفضل `reverse_each` عن  `reverse.each`
 عشان بعض ال classes اللي بتضم `include Enumerable` هتوفر تطبيق فعال ليها.
 حتي في السواء الحالات لما مبتكنش بتدعم التطبيق دا, التطبيق الهام بتاعها اللي متاخد من `Enumerable`
 هيعمل نفس اللي بيعمله `reverse.each`.
<sup>[[link](#reverse-each)]</sup>

  ```ruby
  # سئ
  array.reverse.each { ... }

  # جيد
  array.reverse_each { ... }
  ```

## Naming

> الحاجات الوحيدة الصعبة في البرمجة هي  cache invalidation و
> تسمية الاشياء. <br>
> -- Phil Karlton

* <a name="english-identifiers"></a>
  الاسامي لازم تكون بالانجليزي .
<sup>[[link](#english-identifiers)]</sup>

  ```ruby
  # سئ - اسامي لا تدعم الاسكي كود
  заплата = 1_000

  # سئ - كلمة بلغارية مكتوبة بحروف لاتينية
  zaplata = 1_000

  # جيد
  salary = 1_000
  ```

* <a name="snake-case-symbols-methods-vars"></a>
  استخدم  `snake_case` للرموز , و المتغيرات و الدوال.
<sup>[[link](#snake-case-symbols-methods-vars)]</sup>

  ```ruby
  # سئ
  :'some symbol'
  :SomeSymbol
  :someSymbol

  someVar = 5
  var_10  = 10

  def someMethod
    # some code
  end

  def SomeMethod
    # some code
  end

  # جيد
  :some_symbol

  some_var = 5
  var10    = 10

  def some_method
    # some code
  end
  ```

* <a name="snake-case-symbols-methods-vars-with-numbers"></a>
  متفصلش الارقام عن الحروف في الرموز و الممتغيرات و الدوال .
<sup>[[link](#snake-case-symbols-methods-vars-with-numbers)]</sup>

  ```ruby
  # سئ
  :some_sym_1

  some_var_1 = 1

  def some_method_1
    # شوية كود هنا 
  end

  # جيد
  :some_sym1

  some_var1 = 1

  def some_method1
    # شوية كود هنا 
  end
  ```


* <a name="camelcase-classes"></a>
  استخدم  `CamelCase` في حالات  classes و modules.
  (خلي الاختصارات زي دي   HTTP, RFC, XML كبيرة زي ما هي .)
<sup>[[link](#camelcase-classes)]</sup>

  ```ruby
  # سئ
  class Someclass
    # شوية كود هنا
  end

  class Some_Class
    # شوية كود هنا
  end

  class SomeXml
    # شوية كود هنا 
  end

  class XmlSomething
    # some code
  end

  # جيد
  class SomeClass
    # شوية كود هنا 
  end

  class SomeXML
    # شوية كود هنا
  end

  class XMLSomething
    # شوية كود هنا 
  end
  ```

* <a name="snake-case-files"></a>
  استخدم `snake_case`في يتسمية الملفات, زي `hello_world.rb`.
<sup>[[link](#snake-case-files)]</sup>

* <a name="snake-case-dirs"></a>
  استخدم `snake_case` لتسميه المجلدات زي 
  `lib/hello_world/hello_world.rb`.
<sup>[[link](#snake-case-dirs)]</sup>

* <a name="one-class-per-file"></a>
  احرص انك يكو عندك class/module وحيد جوا ملف الكود الواحد .
  سمي الملف زيه زي اسم ال class/module 
  بس الفرق حول الاسم من CamelCase ل snake_case.
<sup>[[link](#one-class-per-file)]</sup>

* <a name="screaming-snake-case"></a>
  استخدم `SCREAMING_SNAKE_CASE` لجميع الثوابت التانية .
<sup>[[link](#screaming-snake-case)]</sup>

  ```ruby
  # سئ
  SomeConst = 5

  # جيد
  SOME_CONST = 5
  ```

* <a name="bool-methods-qmark"></a>
  اسامي الدوال التأكيد ( اللي بترجع قيمة boolean) المفروض تنتهي بعلامة استفهام.
  مثال علي كدا (زي `Array#empty?`) .
 الدوال بقي اللي مش بترجع القيم دي مش المفروض تخلص بعلامة استفهام.
<sup>[[link](#bool-methods-qmark)]</sup>

* <a name="bool-methods-prefix"></a>
  تجنب بدء الدوال التأكيديه بالافعال المساعدة  اللي زي `is`,`does`, او `can`.
 الكلمات دي تعتبر زيادة و ملهاش لازمة بالنسبة للاسلوي اللي اساس لغة الروبي كاتب بيه
 دوال ال boolean, اللي هي مثلا زي `empty?` و `include?`.
<sup>[[link](#bool-methods-prefix)]</sup>

  ```ruby
  # سئ
  class Person
    def is_tall?
      true
    end

    def can_play_basketball?
      false
    end

    def does_like_candy?
      true
    end
  end

  # جيد
  class Person
    def tall?
      true
    end

    def basketball_player?
      false
    end

    def likes_candy?
      true
    end
  end
  ```

* <a name="dangerous-method-bang"></a>
  اسامي الدوال *الخطيرة* (الدوال اللي بتعدل `self` او ال arguments),
 `exit!` (مبترجعش القيمة النهائية زي ما `exit` بتعمل و هكذا )
 المفروض تنتهي بعلامة تعجب لو في نسخة امنة من الدالة دي .
<sup>[[link](#dangerous-method-bang)]</sup>

  ```ruby
  # شئ مفيش نسخة تانيه 'امنة' منها 
  class Person
    def update!
    end
  end

  # جيد
  class Person
    def update
    end
  end

  # جيد
  class Person
    def update!
    end

    def update
    end
  end
  ```

* <a name="safe-because-unsafe"></a>
  عرف الدوال اللي منغي علامة استفهام (الامنة)
  من نفس الناحية او الطريقة اللي مكتوب بيها اللي بعلامة تعجب (الخطرة)
 لو ممكن يعني .
<sup>[[link](#safe-because-unsafe)]</sup>

  ```ruby
  class Array
    def flatten_once!
      res = []

      each do |e|
        [*e].each { |f| res << f }
      end

      replace(res)
    end

    def flatten_once
      dup.flatten_once!
    end
  end
  ```

* <a name="other-arg"></a>
  لما تيجي تعرف علامات ال binary سمي البرامتر `other`
 (`<<` و `[]` دول حالات خاصة للحالة دي, خاصة ان دول ليهم دلالات مختلفة).
<sup>[[link](#other-arg)]</sup>

  ```ruby
  def +(other)
    # body omitted
  end
  ```

## التعليقات

> الكود الجيد بيرجع للشرح الكويس بتاعه . لما تيجي تحط تعليق,
> أسال نفسك , "ازاي اقدر احسن الحتة دي من الكود 
> عشان متكنش محتاجة تعليق يوضحها" حسن كودك و بعدين اشرحه 
> مدا هيكون اوضح كتير. <br>
> -- Steve McConnell

* <a name="no-comments"></a>
  خلي الكود بتاعك بيشح نفسه و انت مش هتحتاج تقرأ الكلام اللي جاي كله , بجد!
<sup>[[link](#no-comments)]</sup>

* <a name="english-comments"></a>
  Write comments in English.
<sup>[[link](#english-comments)]</sup>

* <a name="hash-space"></a>
  استخدم مسافة واحد فاضية ما بين الرمز دا  `#` و الكلام اللي بعده اللي مكتوب في الكومنت.
<sup>[[link](#hash-space)]</sup>

* <a name="english-syntax"></a>
  التعليقات اللي اكتر من كلمة بتكبر الحروف الاولي منها و بتستخدم علامات الترقيم.
 استخدم  [مسافة واحدة](https://en.wikipedia.org/wiki/Sentence_spacing.
<sup>[[link](#english-syntax)]</sup>

* <a name="no-superfluous-comments"></a>
  بلاش التعليقات اللي ملهاش لازمة.
<sup>[[link](#no-superfluous-comments)]</sup>

  ```ruby
  # سئ
  counter += 1 # Increments counter by one.
  ```

* <a name="comment-upkeep"></a>
  حدث التعليقات اول بأول, لان التعليقات القديمة اسواء من عدمه بكتيير.
<sup>[[link](#comment-upkeep)]</sup>

> الكود الحلو زي النكتة الحلوة: مش محتاج تشرحها <br>
> &mdash; المبرمج القديم  maxim, خلال [Russ Olsen](http://eloquentruby.com/blog/2011/03/07/good-code-and-good-jokes/)

* <a name="refactor-dont-comment"></a>
  تجنب كتابة تعليقات تشرح الكود الوحش .
 عدل الكود بتاعك عشان يشرح نفسه .
. ("Do or do not&mdash;there is no try." Yoda)
<sup>[[link](#refactor-dont-comment)]</sup>

### التعليقات التوضيحية للتعليقات

* <a name="annotate-above"></a>
  التعليقات التوضيحيه عادة بتكتب في سطر فوق بالظبط الكود اللي عاوز يتوضح.
<sup>[[link](#annotate-above)]</sup>

* <a name="annotate-keywords"></a>
  الكلمات اللي بتميزها لازم يجي بعدها نقطتين فوق بعض و مسافة,
 و بعدها الملاحظة اللي بتفسر المشكلة.
<sup>[[link](#annotate-keywords)]</sup>

* <a name="indent-annotations"></a>
  لو المشكلة محتاجة اكتر من سطر عشان تتشرح , اشرحها في السطور اللي بعدها و سيب 3 مسافات بعد  `#` 
(مسافة واحدة كدا كدا بتبقي محطوطه, الاتنين التانين معناهم التكملة).
<sup>[[link](#indent-annotations)]</sup>

  ```ruby
  def bar
    # FIXME: This has crashed occasionally since v3.2.1. It may
    #   be related to the BarBazUtil upgrade.
    baz(:quux)
  end
  ```

* <a name="rare-eol-annotations"></a>
  في الحالات اللي بتكون الحالة واضحة اووي و اي توضيح هيعتبر اعادة, 
  التعليقات التوضيحية بتتساب اخر السطر منغير تفسير .
 الموضوع دا استثناء و مش قاعدة.
<sup>[[link](#rare-eol-annotations)]</sup>

  ```ruby
  def bar
    sleep 100 # OPTIMIZE
  end
  ```

* <a name="todo"></a>
  استخدم `TODO` عشان تسيب ملاحظة علي خاصية او ميزة  متعملوش 
  و المفروض يتعملوا بعدين.
<sup>[[link](#todo)]</sup>

* <a name="fixme"></a>
  استخدم `FIXME` ك ملاحظة ل كود بايظ محتاج يتصلح .
<sup>[[link](#fixme)]</sup>

* <a name="optimize"></a>
  استخدم `OPTIMIZE` ك ملاحظة لل بطء او عدم فاعلية الكود,
 اللي مكن يعمل مشاكل ف الاداء بعدين.
<sup>[[link](#optimize)]</sup>

* <a name="hack"></a>
  استخدم `HACK` ك ملاحظة ل حاجة اتكروتت و المفروض تتظبط .
<sup>[[link](#hack)]</sup>

* <a name="review"></a>
  استخدم `REVIEW` ك ملاحظة ل حاجة محتاجة تأكيد انها كدا بتعمل المطلوب.
 علي سبيل المثال: `REVIEW: Are we sure this is how the client does X currently?`
<sup>[[link](#review)]</sup>

* <a name="document-annotations"></a>
  استخدم كلمات مختلفة للتعليقات التوضيحية لو شايف انها كدا هتوضح اكتر, 
 بس اتاكد انك شارحها في مكان وي ال `README` بتاع المشروهع او حاجة زيه .
<sup>[[link](#document-annotations)]</sup>

### التعليقات السحرية

* <a name="magic-comments-first"></a>
  حط ال التعليقات السحرية فوق كل الاكواد و الشرح.
 هي بس بتتحط لو انت محتاجهم في ملف الكود بتاعك 
<sup>[[link](#magic-comments-first)]</sup>

  ```ruby
  # جيد
  # frozen_string_literal: true
  # Some documentation about Person
  class Person
  end

  # سئ
  # Some documentation about Person
  # frozen_string_literal: true
  class Person
  end
  ```

  ```ruby
  # جيد
  #!/usr/bin/env ruby
  # frozen_string_literal: true
  App.parse(ARGV)

  # سئ
  # frozen_string_literal: true
  #!/usr/bin/env ruby
  App.parse(ARGV)
  ```

* <a name="one-magic-comment-per-line"></a>
  استخدم تعليق سحري وحيد ف كل سطر لو محتاج اكتر من واحد.
<sup>[[link](#one-magic-comment-per-line)]</sup>

  ```ruby
  # جيد
  # frozen_string_literal: true
  # encoding: ascii-8bit

  # سئ
  # -*- frozen_string_literal: true; encoding: ascii-8bit -*-
  ```

* <a name="separate-magic-comments-from-code"></a>
  فرق ما بين التعليقات السحرية و الاخري ب سطر واحد فاضي .
<sup>[[link](#separate-magic-comments-from-code)]</sup>

  ```ruby
  # جيد
  # frozen_string_literal: true

  # Some documentation for Person
  class Person
    # شوية كود هنا
  end

  # سئ
  # frozen_string_literal: true
  # Some documentation for Person
  class Person
    # Some code
  end
  ```

## الفئات و الوحدات

* <a name="consistent-classes"></a>
  استخدم شكل متناسق لما تيجي تعرف ال class .
<sup>[[link](#consistent-classes)]</sup>

  ```ruby
  class Person
    # extend و include بيبقوا الاول 
    extend SomeModule
    include AnotherModule

    # inner classes
    CustomError = Class.new(StandardError)

    # و بعد كدا الثوابت
    SOME_CONSTANT = 20

    # بعد كدا بنحط العناصر
    attr_reader :name

    # بعد كدا بتحط اي  macro لو موجود 
    validates :name

    # و بعدهم بقي يجي دور ال public class methods
    def self.some_method
    end

    # الدالة ةالتعريفية بتكون ما بين ال class methods و ال instance methods
    def initialize
    end

    # بيجي بعدها public instance methods
    def some_method
    end

    #  الوال protected و private بيتجمعوا قبل كلمة end
    protected

    def some_protected_method
    end

    private

    def some_private_method
    end
  end
  ```

* <a name="mixin-grouping"></a>
  قسم اكتر من mixins في اكتر من سطر .
<sup>[[link](#mixin-grouping)]</sup>

  ```ruby
  # سئ
  class Person
    include Foo, Bar
  end

  # جيد
  class Person
    # اكتر من mixins انفصلوا في سطور مختفلة
    include Foo
    include Bar
  end
  ```

* <a name="file-classes"></a>
  تجنب تحط classes بتتكون من اكتر من سطر جوا classes تانية.
 حطه جوا بعض في كل واحدة في الملف بتاعها و خلي اسم الفايل نفس اسم الكلاس اللي جوا.
<sup>[[link](#file-classes)]</sup>

  ```ruby
  # سئ

  # foo.rb
  class Foo
    class Bar
      # 30 دالة جوا 
    end

    class Car
      # 20 دالة جوا
    end

    # 30 دالة جوا
  end

  # good

  # foo.rb
  class Foo
    # 30 دالة جوا
  end

  # foo/bar.rb
  class Foo
    class Bar
      # 30 دالة جوا
    end
  end

  # foo/car.rb
  class Foo
    class Car
      # 20 دالة جوا
    end
  end
  ```

* <a name="namespace-definition"></a>
  عرف (و اعد فتح) namespaced classes و modules عن طريق ال explicit nesting.
 عن طريق استخدام علامة ال scope resolution هيؤدي ل استدعاء مفاجي لل ثوابت طبقا ل الروبي [lexical scoping](https://cirw.in/blog/constant-lookup.html),
 و اللي بتعتمد علي طريقة تعريف جوا عض في لحظة التعريف.
  <sup>[[link](#namespace-definition)]</sup>

  ```Ruby
  module Utilities
    class Queue
    end
  end

  # سئ
  class Utilities::Store
    Module.nesting # => [Utilities::Store]

    def initialize
      # بيرجع ل اعلي مستوي عشان ال ::Queue class
      # مش في التسلسل الداخلي لل Utilities 
      @queue = Queue.new
    end
  end

  # جيد
  module Utilities
    class WaitingList
      Module.nesting # => [Utilities::WaitingList, Utilities]

      def initialize
        @queue = Queue.new # بترجع ل  Utilities::Queue
      end
    end
  end
  ```

* <a name="modules-vs-classes"></a>
   بيفضل انه يكون modules عن classes لما بتكون عبارة عن دوال بس.
  بنستخددم ال classes بس لما بيكون في سبب منطقي اننا نعمل نسخة منها.
<sup>[[link](#modules-vs-classes)]</sup>

  ```ruby
  # سئ
  class SomeClass
    def self.some_method
      # اللي هنا اتشال
    end

    def self.some_other_method
      # اللي هنا اتشال 
    end
  end

  # جيد
  module SomeModule
    module_function

    def some_method
      # اللي هنا اتشال
    end

    def some_other_method
      # اللي هنا اتشال
    end
  end
  ```

* <a name="module-function"></a>
  يفضل استخدام `module_function` عن `extend self` لما تحب تحول 
 نسخة الدوال بتاعت ال module ب دوال بتاعت class.
<sup>[[link](#module-function)]</sup>

  ```ruby
  # سئ
  module Utilities
    extend self

    def parse_something(string)
      # شوية حاجات هنا 
    end

    def other_utility_method(number, string)
      # شوية حاجات هنا
    end
  end

  # جيد
  module Utilities
    module_function

    def parse_something(string)
      # شوية حاجات هنا
    end

    def other_utility_method(number, string)
      # شوية حاجات هنا
    end
  end
  ```

* <a name="liskov"></a>
  لما تيجي تصمم التسلسل الهرمي للكلاس اتاكد انها بتتبع  [Liskov
  Substitution
  Principle](https://en.wikipedia.org/wiki/Liskov_substitution_principle).
<sup>[[link](#liskov)]</sup>

* <a name="solid-design"></a>
  حاول تخلي الكلاس بتاعتك زي دي 
  [SOLID](https://en.wikipedia.org/wiki/SOLID_\(object-oriented_design\)) as
  علي اد ما تقدر.
<sup>[[link](#solid-design)]</sup>

* <a name="define-to-s"></a>
  دايما خالي عندك دالة ال `to_s` متعرفة في الكلاسس بتوعك اللي بعبروا عن ال domain objects.
<sup>[[link](#define-to-s)]</sup>

  ```ruby
  class Person
    attr_reader :first_name, :last_name

    def initialize(first_name, last_name)
      @first_name = first_name
      @last_name = last_name
    end

    def to_s
      "#{@first_name} #{@last_name}"
    end
  end
  ```

* <a name="attr_family"></a>
 استخدم `attr` و الحاجات اللي زيه عشان تعرف trivial accessors او mutators
<sup>[[link](#attr_family)]</sup>

  ```ruby
  # سئ
  class Person
    def initialize(first_name, last_name)
      @first_name = first_name
      @last_name = last_name
    end

    def first_name
      @first_name
    end

    def last_name
      @last_name
    end
  end

  # جيد
  class Person
    attr_reader :first_name, :last_name

    def initialize(first_name, last_name)
      @first_name = first_name
      @last_name = last_name
    end
  end
  ```

* <a name="accessor_mutator_method_names"></a>
  في حالة استخدام accessors and mutators, تجنب اسامي الدوال اللي بتبداء ب `get_` و `set_`.
  دا طريقة الروبي لتعريف الاسامي بتعتهم يا بتتب اسمه لو عاوز تاخد القيمة.
 يا بتحط اسمه و بعده علامة يساوي لو هتديله قيمه كدهو `attr_name=`.
<sup>[[link](#accessor_mutator_method_names)]</sup>

  ```ruby
  # سئ
  class Person
    def get_name
      "#{@first_name} #{@last_name}"
    end

    def set_name(name)
      @first_name, @last_name = name.split(' ')
    end
  end

  # جيد
  class Person
    def name
      "#{@first_name} #{@last_name}"
    end

    def name=(name)
      @first_name, @last_name = name.split(' ')
    end
  end
  ```

* <a name="attr"></a>
  تجنب استخدام ال `attr`, استخدم بدالها `attr_reader` و `attr_accessor`
<sup>[[link](#attr)]</sup>

  ```ruby
  # سئ - بتعرف عنصر واحد (اساسا اهملت من بعد نسخة روبي 1.9)
  attr :something, true
  attr :one, :two, :three # behaves as attr_reader

  # جيد
  attr_accessor :something
  attr_reader :one, :two, :three
  ```

* <a name="struct-new"></a>
  حط في اعتبارك استخدام `Struct.new`,
 هي هتعرفلك trivial accessors و constructor و comparison operators.
<sup>[[link](#struct-new)]</sup>

  ```ruby
  # جيد
  class Person
    attr_accessor :first_name, :last_name

    def initialize(first_name, last_name)
      @first_name = first_name
      @last_name = last_name
    end
  end

  # احسن
  Person = Struct.new(:first_name, :last_name) do
  end
  ```

* <a name="no-extend-struct-new"></a>
  متمددش حاجة انت عرفتها بال `Struct.new`.
 لانه حاجة ملهاش لازمة و هتجيبلك شوية اخطاء لو الملف اتطلب في اكتر من وقت.
<sup>[[link](#no-extend-struct-new)]</sup>

  ```ruby
  # سئ
  class Person < Struct.new(:first_name, :last_name)
  end

  # جيد
  Person = Struct.new(:first_name, :last_name)
  ```

* <a name="factory-methods"></a>
  حط في اعتبارك تعريف دوال تعريفيه زيادة .
 عشان تسمحلك تعرف نسخ تانيه من الكلاس بشكل اكتر منطقية .
<sup>[[link](#factory-methods)]</sup>

  ```ruby
  class Person
    def self.create(options_hash)
      # اللي هنا اتشال
    end
  end
  ```

* <a name="duck-typing"></a>
  بيفضل  [duck-typing](https://en.wikipedia.org/wiki/Duck_typing) عن
  الوراثة.
<sup>[[link](#duck-typing)]</sup>

  ```ruby
  # سئ
  class Animal
    # abstract method
    def speak
    end
  end

  # extend superclass
  class Duck < Animal
    def speak
      puts 'Quack! Quack'
    end
  end

  # extend superclass
  class Dog < Animal
    def speak
      puts 'Bau! Bau!'
    end
  end

  # جيد
  class Duck
    def speak
      puts 'Quack! Quack'
    end
  end

  class Dog
    def speak
      puts 'Bau! Bau!'
    end
  end
  ```

* <a name="no-class-vars"></a>
 تجنب استخدام متغيرات الكلاس (`@@`) عشان التداخل اللي بيحصل في الوراثة.
<sup>[[link](#no-class-vars)]</sup>

  ```ruby
  class Parent
    @@class_var = 'parent'

    def self.print_class_var
      puts @@class_var
    end
  end

  class Child < Parent
    @@class_var = 'child'
  end

  Parent.print_class_var # => will print 'child'
  ```
  زي ما انت شايف كل ال classes في الترتيب بتاعم بيتشاركوا في واحد class variable.
 دايما بيفضل استخدام ال Class instance variables عن ال class variables.

* <a name="visibility"></a>
  عرف المستوي المناسب للدوال (`private`, `protected`) شبه بعض في الاستخدام .
  متسيبش كل حاجة `public` (تقدر تقول هو دا اساسا الوضع الافتراضي).
 علي اي حال احنا بنكتب *روبي* دلوقتي, مش *بايثون*.
<sup>[[link](#visibility)]</sup>

* <a name="indent-public-private-protected"></a>
  المسافة اللي في الاول بتاعت الدوال دي `public`و `protected`و `private` مهمة زيها زي التعريف .
 سيب سطر فاضي قبل الدوال دي قبلها و بعدها .
 عشان توضح ان دا الستوي بتاع كل الدوال اللي تحتها .
<sup>[[link](#indent-public-private-protected)]</sup>

  ```ruby
  class SomeClass
    def public_method
      # شوية كود هنا 
    end

    private

    def private_method
      # شوية كود هنا 
    end

    def another_private_method
      # شوية كود هنا
    end
  end
  ```

* <a name="def-self-class-methods"></a>
  استخدم `def self.method` عشان تعرف ال class methods.
 دا بيخلي الكون احسن لو عاوز تحسنه لان اسم الكلاس مش بيتكرر .
<sup>[[link](#def-self-class-methods)]</sup>

  ```ruby
  class TestClass
    # سئ
    def TestClass.some_method
      # body omitted
    end

    # جيد
    def self.some_other_method
      # body omitted
    end

    # ممكن جدا و بتبقي كويسة
    # لما تكون مضطر تعرف اكتر من دالة.
    class << self
      def first_method
        # اللي هنا اتشال
      end

      def second_method_etc
        # اللي هنا اتشال
      end
    end
  end
  ```

* <a name="alias-method-lexically"></a>
  يفضل `alias` عند  استعارة الدوال في حال ال lexical class scope
 حيث ان اخذ قرار ل `self` في حالة زي دي يعتبر برضه lexical,
 و  ف حين ان التواصل بتاعها اوضح للمستخدم و برضه مش هيحصل تغير لل aliase 
في الوقت اللي الكود شغال فيه او عن طريق اي subclass الا لو اتعمل بشكل مباشر.

<sup>[[link](#alias-method-lexically)]</sup>

  ```ruby
  class Westerner
    def first_name
      @names.first
    end

    alias given_name first_name
  end
  ```
  و زي ما `alias` شبهة, و هي كلمة مستخدمة 
 بيفضل انك تستخدمها كدا `alias foo bar`
 مش كدا `alias :foo :bar`.

  برضه خليك عارف ازاي الروبي بتتعامل مع ال aliases  و ال inheritance:
  ال alias بيرجع للدالة اللي اتعرفت وقت ما هو بص عليها .
 مبتتغير بعد كدا لوحدها.

  ```ruby
  class Fugitive < Westerner
    def first_name
      'Nobody'
    end
  end
  ```
  
   في المثال دا, `Fugitive#given_name` هيفضل يستخدم الدالة الاصلية من دي `Westerner#first_name`,
   مش دي `Fugitive#first_name`.
  عشان تعيد كتابة التصرف بتاع `Fugitive#given_name`, انت لازم تعرفها من جديد في ال derived class .

  ```ruby
  class Fugitive < Westerner
    def first_name
      'Nobody'
    end

    alias given_name first_name
  end
  ```

* <a name="alias-method"></a>
  دايما استخدم `alias_method` لما تعمل aliasing من دوال ال modules او classes او singleton classes
 في وقت تشغيل الكود.
 حيث ان تصرف ال `alias` هيعمل حاجة غير متوقعه في الحالات دي.
<sup>[[link](#alias-method)]</sup>

  ```ruby
  module Mononymous
    def self.included(other)
      other.class_eval { alias_method :full_name, :given_name }
    end
  end

  class Sting < Westerner
    include Mononymous
  end
  ```

* <a name="class-and-self"></a>
  لما دوال ال class (او module) يستخدموا دوال تانيين, 
شيل `self` من البداية او اسمها متبوع ب `.` لما تيجي تستخدم زيها من مكان تاني.
 دا حاجة معتادة في ال "service classes" او في الحاجات اللي زيها 
المبدا دا بيقلل الاعادة في ال classes.
  <sup>[[link](#class-and-self)]</sup>

  ```ruby
  class TestClass

    # سئ - هتتعب لما تيجي تغير اسم او تشيل الدالة
    def self.call(param1, param2)
      TestClass.new(param1).call(param2)
    end

    # سئ - اطول من الازم.
    def self.call(param1, param2)
      self.new(param1).call(param2)
    end

    # جيد
    def self.call(param1, param2)
      new(param1).call(param2)
    end

    # ...دوال تانية...
  end
  ```

## الاستثنائات

* <a name="prefer-raise-over-fail"></a>
  بيفضل `raise` عن `fail` في الاستثنائات
  <sup>[[link](#prefer-raise-over-fail)]</sup>

  ```ruby
  # سئ
  fail SomeException, 'message'

  # جيد
  raise SomeException, 'message'
  ```

* <a name="no-explicit-runtimeerror"></a>
  متحددش نوع الاستثناء `RuntimeError` و تبعته مع نسخة ال `raise`.
<sup>[[link](#no-explicit-runtimeerror)]</sup>

  ```ruby
  # سئ
  raise RuntimeError, 'message'

  # جيد - المفرد بيعتبر RuntimeError منغير ما تكتبه .
  raise 'message'
  ```

* <a name="exception-class-messages"></a>
  بيفضل فصل الاستثناء و الرسالة بتاعته منفصلين لما تستخدم `raise`,
 بدل ما تعمل نسخة منه .
<sup>[[link](#exception-class-messages)]</sup>

  ```ruby
  # سئ
  raise SomeException.new('message')
  # خد بالك مفيش طريقة تعرف تعمل بيها كدا `raise SomeException.new('message'), backtrace`.

  # جيد
  raise SomeException, 'message'
  # شغاله برضه مع `raise SomeException, 'message', backtrace`.
  ```

* <a name="no-return-ensure"></a>
   متسخدمش return مع بلوك ال `ensure`.
   لو انت استخدمت return جوا دالة ف بلوك ال `ensure`,  الاولويه هتكون ليها عن اي استثناء,
  و الدالة هترجع قيمة كأن مكنش في اي استثناء . الاستثناء ببساطة كانه محصلش.
<sup>[[link](#no-return-ensure)]</sup>

  ```ruby
  # سئ
  def foo
    raise
  ensure
    return 'very bad idea'
  end
  ```

* <a name="begin-implicit"></a>
  Use *implicit begin blocks* where possible.
<sup>[[link](#begin-implicit)]</sup>

  ```ruby
  # سئ
  def foo
    begin
      # الكود اللي شغال هنا
    rescue
      # الكود اللي بتعامل مع الاخطاء
    end
  end

  # جيد
  def foo
    # الكود اللي شغال هنا
  rescue
    # الكود اللي بتعامل مع الاخطاء
  end
  ```

* <a name="contingency-methods"></a>
  خفف انتشار بلوكات `begin` عن طريق استخدام *contingency methods*
 
  Mitigate the proliferation of `begin` blocks by using *contingency methods*
  (مصطلح اللي عمله واحد اسمه Avdi Grimm).
<sup>[[link](#contingency-methods)]</sup>

  ```ruby
  # سئ
  begin
    something_that_might_fail
  rescue IOError
    # handle IOError
  end

  begin
    something_else_that_might_fail
  rescue IOError
    # handle IOError
  end

  # جيد
  def with_io_error_handling
     yield
  rescue IOError
    # handle IOError
  end

  with_io_error_handling { something_that_might_fail }

  with_io_error_handling { something_else_that_might_fail }
  ```

* <a name="dont-hide-exceptions"></a>
  متمنعش استخدام الاستثنائات.
<sup>[[link](#dont-hide-exceptions)]</sup>

  ```ruby
  # سئ
  begin
    # الاستثنائات بتتحط هنا
  rescue SomeError
    # ال rescue هنا بقي ملهوش لازمة
  end

  # سئ
  do_something rescue nil
  ```

* <a name="no-rescue-modifiers"></a>
  تجنب استخدام `rescue` في شكلة الجديد.
<sup>[[link](#no-rescue-modifiers)]</sup>

  ```ruby
  # سئ - دي بتمسك الاستثنائات اللي زي StandardError و اللي زيها.
  read_file rescue handle_error($!)

  # جيد - دي بتمسك الاستثنائات فقط اللي زي Errno::ENOENT و اللي زيها.
  def foo
    read_file
  rescue Errno::ENOENT => ex
    handle_error(ex)
  end
  ```

* <a name="no-exceptional-flows"></a>
  متستخدمش الاستثنائات مع ال flow of control.
<sup>[[link](#no-exceptional-flows)]</sup>

  ```ruby
  # سئ
  begin
    n / d
  rescue ZeroDivisionError
    puts 'Cannot divide by 0!'
  end

  # جيد
  if d.zero?
    puts 'Cannot divide by 0!'
  else
    n / d
  end
  ```

* <a name="no-blind-rescues"></a>
   تجنب استخدام الكلاس دي `Exception`.
  عشان دي هتؤدي انها تقفل البرنامج لانها بتستخدم `exit`.
 بيتطلب منك انك تنفهي العمليه ب `kill -9`.
<sup>[[link](#no-blind-rescues)]</sup>

  ```ruby
  # سئ
  begin
    # calls to exit and kill signals will be caught (except kill -9)
    exit
  rescue Exception
    puts "you didn't really want to exit, right?"
    # التعامل مع الاستثناء
  end

  # جيد
  begin
    # تعامل اعمي مع الاستثنائات بيندرج تحت StandardError.
    # و معظم المبرمجين مبتعتبروش استثناء.
  rescue => e
    # التعامل مع الاستثناء
  end

  # برضه جيد
  begin
    # الاستثناء بيبقي هنا
  rescue StandardError => e
    # التعامل مع الاستثناء
  end
  ```

* <a name="exception-ordering"></a>
 حط استثناءات محدده أعلى سلسلة ال exceptions ، وإلا مش هتتنفذ.
<sup>[[link](#exception-ordering)]</sup>

  ```ruby
  # سئ
  begin
    # شوية كود هنا
  rescue StandardError => e
    # التعامل هنا
  rescue IOError => e
    # دي عمرها ما هتشتغل
  end

  # جيد
  begin
    # شوية كود هنا
  rescue IOError => e
    # طريقة تعامل 
  rescue StandardError => e
    # طريقة تعامل
  end
  ```

* <a name="release-resources"></a>
  الحاجات اللي الكود بتاعك معتمد عليها و بتيجي من برا حطها جوا `ensure` بلوك.
<sup>[[link](#release-resources)]</sup>

  ```ruby
  f = File.open('testfile')
  begin
    # .. process
  rescue
    # .. handle error
  ensure
    f.close if f
  end
  ```

* <a name="auto-release-resources"></a>
   طالما ممكن تستخدم دوال بتنضف بعد ما بتخلص لوحدها و بتتقفل لوحدها استخدمها.
<sup>[[link](#auto-release-resources)]</sup>

  ```ruby
  # سئ - انت محتاج تقفل الكود بنفسك
  f = File.open('testfile')
  # some action on the file
  f.close

  # جيد - الملف بيتقل لوحده بعد ما تخلص.
  File.open('testfile') do |f|
    # some action on the file
  end
  ```

* <a name="standard-exceptions"></a>
  بيفضل انك تستخدم استثناء من اللي موجودين ف ال standard library
 بدل ما تعمل واحد جديد من الاول.
<sup>[[link](#standard-exceptions)]</sup>

## المجموعات

* <a name="literal-array-hash"></a>
  بيفضل صنع ال array و hash بالعلامات اللي بترمز ليهم ( دا طالما 
 انت مش عاوز تبعتلهم بارمتر هيساعد في صنعهم, بس كدا).
<sup>[[link](#literal-array-hash)]</sup>

  ```ruby
  # سئ
  arr = Array.new
  hash = Hash.new

  # جيد
  arr = []
  arr = Array.new(10)
  hash = {}
  hash = Hash.new(0)
  ```

* <a name="percent-w"></a>
 بيفضل استخدام `%w` لما تيجي تعرف array متكون من كلمات ( الكلمات الي منغير فواصل 
من جوا مع عدم وجود اي رموز مميزة). طبق القاعدة دي مع ال array اللي بعنصرين او اكتر.
<sup>[[link](#percent-w)]</sup>

  ```ruby
  # سئ
  STATES = ['draft', 'open', 'closed']

  # جيد
  STATES = %w[draft open closed]
  ```

* <a name="percent-i"></a>ط
  بيفضل استخدام `%i` لما تيجي تعرف array بيتكون من symbols 
 (و انت مش محتاج تصلح في نسخة الروبي 1.9).
 طبق القاعدة دي علي ال arrays اللي بتتكون من عنصر.
<sup>[[link](#percent-i)]</sup>

  ```ruby
  # سئ
  STATES = [:draft, :open, :closed]

  # جيد
  STATES = %i[draft open closed]
  ```

* <a name="no-trailing-array-commas"></a>
  تجنب انك تحط اخر فاصلة ف ال `Array` او `Hash`,
 خاصة لما يكون متعرف في اكتر من سطر .
<sup>[[link](#no-trailing-array-commas)]</sup>

  ```ruby
  # سئ - اسهل في انك تشيل/تحط/تحرك عنصر بس برضه مش مفضلة. 
  VALUES = [
             1001,
             2020,
             3333,
           ]

  # سئ
  VALUES = [1001, 2020, 3333, ]

  # جيد
  VALUES = [1001, 2020, 3333]
  ```

* <a name="no-gappy-arrays"></a>
  
  تجنب تسيب مسافات كبيرة جوا فاضية ف ال array.
<sup>[[link](#no-gappy-arrays)]</sup>

  ```ruby
  arr = []
  arr[100] = 1 # دلوقتي بقي عندك array كبير من حاجات فاضية
  ```

* <a name="first-and-last"></a>
  لما تيجي تتعامل مع اول و اخر عنصر في ال array بفضل استخدام `first` او `last`
 عن استخدام `[0]` او `[-1]`.
<sup>[[link](#first-and-last)]</sup>

* <a name="set-vs-array"></a>
  استخدم ال `Set` بدلا من ال `Array` لما تكون بتتعامل مع عناصر فريدة مبتتكررش.
 ال `Set` مبنية بحيث انها تشيل مجموعات مش مترتبة بس برضه مش متكررة.
 دا عبارة عن نوع هجين من ال `Array` في علاماته و ال `Hash` في سرعته .
<sup>[[link](#set-vs-array)]</sup>

* <a name="symbols-as-keys"></a>
  بيفضل استخدام ال symbols بدل ال strings ك hash keys.
<sup>[[link](#symbols-as-keys)]</sup>

  ```ruby
  # سئ
  hash = { 'one' => 1, 'two' => 2, 'three' => 3 }

  # جيد
  hash = { one: 1, two: 2, three: 3 }
  ```

* <a name="no-mutable-keys"></a>
 تجنب استخدام mutable objects ك hash keys.
<sup>[[link](#no-mutable-keys)]</sup>

* <a name="hash-literals"></a>
  استخدم طريقة نسخة الروبي 1.9 لما تيجي تعرف hash و يكون ال keys بتاعته symbols.
<sup>[[link](#hash-literals)]</sup>

  ```ruby
  # سئ
  hash = { :one => 1, :two => 2, :three => 3 }

  # جيد
  hash = { one: 1, two: 2, three: 3 }
  ```

* <a name="no-mixed-hash-syntaces"></a>
  متنوعش في الروبي 1.9 لما تيجي تعرف ال hash بين الطريقة العادية و ال hash rockets
 في نفس ال hash لما يكون عندك keys مش symbols و محتاجين hash rockets عشان يتعرفوا .
<sup>[[link](#no-mixed-hash-syntaces)]</sup>

  ```ruby
  # سئ
  { a: 1, 'b' => 2 }

  # جيد
  { :a => 1, 'b' => 2 }
  ```

* <a name="hash-key"></a>
 استخدم `Hash#key?`بدلا من `Hash#has_key?` و استخدم `Hash#value?` بدلا من `Hash#has_value?`..
<sup>[[link](#hash-key)]</sup>

  ```ruby
  # سئ
  hash.has_key?(:test)
  hash.has_value?(value)

  # جيد
  hash.key?(:test)
  hash.value?(value)
  ```

* <a name="hash-each"></a>
  استخدم `Hash#each_key` بدلا من `Hash#keys.each` و `Hash#each_value` بدلا من `Hash#values.each`.
<sup>[[link](#hash-each)]</sup>

  ```ruby
  # سئ
  hash.keys.each { |k| p k }
  hash.values.each { |v| p v }
  hash.each { |k, _v| p k }
  hash.each { |_k, v| p v }

  # جيد
  hash.each_key { |k| p k }
  hash.each_value { |v| p v }
  ```

* <a name="hash-fetch"></a>
  استخدم `Hash#fetch` لما تتعامل مع hash keys المفﻻوض تتعرض.
<sup>[[link](#hash-fetch)]</sup>

  ```ruby
  heroes = { batman: 'Bruce Wayne', superman: 'Clark Kent' }
  # سئ - لو في غلط مش هيبان
  heroes[:batman] # => 'Bruce Wayne'
  heroes[:supermann] # => nil

  # جيد -  fetch هتعمل KeyError ما متلاقي ال key.
  heroes.fetch(:supermann)
  ```

* <a name="hash-fetch-defaults"></a>
  حط قيمة افتراضيه لل hash keys عن طريق `Hash#fetch` بدل ما تستخدم علامة منطقية .
<sup>[[link](#hash-fetch-defaults)]</sup>

  ```ruby
  batman = { name: 'Bruce Wayne', is_evil: false }

  # سئ - لو احنا استخدمنا علامة ال || مع ال false مش هيجيلنا الناتج اللي متوقعينه.
  batman[:is_evil] || true # => true

  # جيد - هتشتغل صح مع القيمة ال false.
  batman.fetch(:is_evil, true) # => false
  ```

* <a name="use-hash-blocks"></a>
  يفضل استخدام البلوك  بدل من القيمة الافتراضيه في `Hash#fetch`
 لو الكود بتاعك اللي عدلته ممكن يكون مهم او مؤثر .
  <sup>[[link](#use-hash-blocks)]</sup>

  ```ruby
  batman = { name: 'Bruce Wayne' } 
  #  سئ - لو استخدمنا القيمة الافتراضية
  #  ممكن جدا تبظء البرنامج لو اتعملت كذا مرة .
  batman.fetch(:powers, obtain_batman_powers) # obtain_batman_powers استخدام مكلف

  # good - blocks are lazy evaluated, so only triggered in case of KeyError exception
  batman.fetch(:powers) { obtain_batman_powers }
  ```

* <a name="hash-values-at"></a>
  استخدم `Hash#values_at` لما تحب ترجع مجموعة من القيم المتتالية.
<sup>[[link](#hash-values-at)]</sup>

  ```ruby
  # سئ
  email = data['email']
  username = data['nickname']

  # جيد
  email, username = data.values_at('email', 'nickname')
  ```

* <a name="ordered-hashes"></a>
  اعتمد علي الحقيقة اللي عملتها روبي نسخة 1.9 ان ال hash مترتب.
<sup>[[link](#ordered-hashes)]</sup>

* <a name="no-modifying-collections"></a>
  متعدلش في مجموعة و انت بتلف عليها.
<sup>[[link](#no-modifying-collections)]</sup>

* <a name="accessing-elements-directly"></a>
  لما تيجي تستعمل عنصر من عناصر المجموعة, تجنب انك تستخدم دي `[n]`.
  لما بتسخدم حاجة بديلة من دا بيحميك من انك تنادي `[]` عل `nil`.
<sup>[[link](#accessing-elements-directly)]</sup>

  ```ruby
  # سئ
  Regexp.last_match[1]

  # جيد
  Regexp.last_match(1)
  ```

* <a name="provide-alternate-accessor-to-collections"></a>
  لما تيجي نوفر accessor ل للمجوعة, احمي المستخدم من انه يناديها علي  `nil`
 قبل ما يبدا يتعامل مع العنصر بتاع المجموعة.
<sup>[[link](#provide-alternate-accessor-to-collections)]</sup>

  ```ruby
  # سئ
  def awesome_things
    @awesome_things
  end

  # جيد
  def awesome_things(index = nil)
    if index && @awesome_things
      @awesome_things[index]
    else
      @awesome_things
    end
  end
  ```
## الارقام

* <a name="integer-type-checking"></a>
  استخدم `Integer` لو عاوز تتاكد من انه رقم صحيح او لا.
 عشان `Fixnum` تعتبر platform-dependent و التاكد من خلالها
 هيرجع قيم مختلفة في حالات الاجهزة نوعها 32-bit و 64-bit
<sup>[[link](#integer-type-checking)]</sup>

  ```ruby
  timestamp = Time.now.to_i

  # سئ
  timestamp.is_a? Fixnum
  timestamp.is_a? Bignum

  # جيد
  timestamp.is_a? Integer
  ```

  * <a name="random-numbers"></a>
  بيفضل استخدام ال ranges لو كنت عاوز تطلع رقم عشوائي
  بدل ما تستخدم فارق الاعداد الصحيحة, عشان هتبقي اوضح
 تخيل اللي ال الزهر بيعمله.
  <sup>[[link](#random-numbers)]</sup>

    ```ruby
    # سئ
    rand(6) + 1

    # جيد
    rand(1..6)
    ```

## Strings

* <a name="string-interpolation"></a>
  بيفضل انك تستخدم string interpolation و string formatting بدل من string concatenation:
<sup>[[link](#string-interpolation)]</sup>

  ```ruby
  # سئ
  email_with_name = user.name + ' <' + user.email + '>'

  # جيد
  email_with_name = "#{user.name} <#{user.email}>"

  # جيد
  email_with_name = format('%s <%s>', user.name, user.email)
  ```

* <a name="consistent-string-literals"></a>
  اعتمد علي نوع واحد لم تيجي تعرف ال string بالنسبة لل quoting style.
 هو في اتنين مشهورين في مجتمع الروبي, و الاتنين بنعتبرهم كويسين 
  و هو single quotes (الاختيار أ) و التاني double quotes (الاختيار ب).
<sup>[[link](#consistent-string-literals)]</sup>
 
  * **(الاختيار أ )** بيفضل ال single-quoted لما مبتكنش محتاج تعمل string interpolation
    او الرموز الخاصة زي `\t`, `\n`, `'`, 
    وهكذا.

    ```ruby
    # سئ
    name = "Bozhidar"

    # جيد
    name = 'Bozhidar'
    ```

  * **(الاختيار ب)** يفضل ال double-quotes طالما ال string بتاعك
   مفيهوش `"` او اي رموز مميزة عاوز تظهرها علي اصلها.

    ```ruby
    # سئ
    name = 'Bozhidar'

    # جيد
    name = "Bozhidar"
    ```

  طريقةالتعامل مع ال string في الدليل دا بتفضل الاختيار الاول.

* <a name="no-character-literals"></a>
   متستخدمش طريقة تعريف الحروف دي `?x`.
 من ساعة روبي 1.9 و هي مستغني عنها
 بس `?x` هتتحول ك `'x'` (عبارة عن string متعرف ب حرف واحد جواه).
<sup>[[link](#no-character-literals)]</sup>

  ```ruby
  # سئ
  char = ?c

  # جيد
  char = 'c'
  ```

* <a name="curlies-interpolate"></a>
  متسيبش `{}` دي حوالين ال instance و global variables 
 عشان يتعمله interpolated جوا string.
<sup>[[link](#curlies-interpolate)]</sup>

  ```ruby
  class Person
    attr_reader :first_name, :last_name

    def initialize(first_name, last_name)
      @first_name = first_name
      @last_name = last_name
    end

    # سئ - صح, بس مش واضحة
    def to_s
      "#@first_name #@last_name"
    end

    # جيد
    def to_s
      "#{@first_name} #{@last_name}"
    end
  end

  $global = 0
  # سئ
  puts "$global = #$global"

  # جيد
  puts "$global = #{$global}"
  ```

* <a name="no-to-s"></a>
  متستخدمش Object#to_s` علي ال interpolated objects.
 هي بتتعمل لوحدها كدا.
<sup>[[link](#no-to-s)]</sup>

  ```ruby
  # سئ
  message = "This is the #{result.to_s}."

  # جيد
  message = "This is the #{result}."
  ```

* <a name="concat-strings"></a>
  تجنب استخدام `String#+` لما تكون محتاج تكون داتا كبيرة.
  في حين انك ممكن تستخدم `String#<<` للوصل بينهم في مكان 
 هي دايما اسرع من `String#+` اللي بتخليك كل مرة تصنع string object جداد.
<sup>[[link](#concat-strings)]</sup>

  ```ruby
  # سئ
  html = ''
  html += '<h1>Page title</h1>'

  paragraphs.each do |paragraph|
    html += "<p>#{paragraph}</p>"
  end

  # جيد و اسرع
  html = ''
  html << '<h1>Page title</h1>'

  paragraphs.each do |paragraph|
    html << "<p>#{paragraph}</p>"
  end
  ```

* <a name="dont-abuse-gsub"></a>
  متستخدمش `String#gsub` في الحالات اللي ممكن تستخدم فيهاحاجات تانية اسرغ و متخصصه اكتر.
<sup>[[link](#dont-abuse-gsub)]</sup>

    ```ruby
    url = 'http://example.com'
    str = 'lisp-case-rules'

    # سئ
    url.gsub('http://', 'https://')
    str.gsub('-', '_')

    # جيد
    url.sub('http://', 'https://')
    str.tr('-', '_')
    ```

* <a name="heredocs"></a>
   لما تيجي تستخدم heredocs لل strings اللي بتاخد اكتر من سطر,
   حط في اعتبارك انها بتحافظ علي المسافة الزيادة.
  دا تطبيق كويس عشان تبطل تحط مسافات ملهاش لازمة.
<sup>[[link](#heredocs)]</sup>

  ```ruby
  code = <<-END.gsub(/^\s+\|/, '')
    |def test
    |  some_method
    |  other_method
    |end
  END
  # => "def test\n  some_method\n  other_method\nend\n"
  ```

* <a name="squiggly-heredocs"></a>
  استخدم طريقة الروبي 2.3 لل squiggly heredocs بشكل الطف ل strings اللي تاخد كذا سطر 
<sup>[[link](#squiggly-heredocs)]</sup>

  ```ruby
  # سئ - بيستخدم Powerpack String#strip_margin
  code = <<-RUBY.strip_margin('|')
    |def test
    |  some_method
    |  other_method
    |end
  RUBY

  # برضه سئ
  code = <<-RUBY
  def test
    some_method
    other_method
  end
  RUBY

  # جيد
  code = <<~RUBY
    def test
      some_method
      other_method
    end
  RUBY
  ```

* <a name="heredoc-delimiters"></a>
  استخدم محددات تكون معبرة في ال heredocs .
 محددتات تكون بتضيف معلومات قيمة عن المحتوي بتاع ال heredocs,
 و ك حاجة حلوة تانية بعد محررات النصوص تقدر تسيب علامة علي الكود اللي خلال ال heredocs
 لو هو مستخدم المحددات صح .
<sup>[[link](#heredoc-delimiters)]</sup>

  ```ruby
  # سئ
  code = <<~END
    def foo
      bar
    end
  END

  # جيد
  code = <<~RUBY
    def foo
      bar
    end
  RUBY

  # good
  code = <<~SUMMARY
    An imposing black structure provides a connection between the past and
    the future in this enigmatic adaptation of a short story by revered
    sci-fi author Arthur C. Clarke.
  SUMMARY
  ```

## الوقت و التاريخ

* <a name="time-now"></a>
  بيفضل `Time.now` عن `Time.new` لما تكون عاوز تاخد الوقت الحالي للنظام.
<sup>[[link](#time-now)]</sup>

* <a name="no-datetime"></a>
  متسخدمش `DateTime` الا لو كنت عاوز تاخد التقويم التاريخي معاك -- و لو عملت كدا 
 حدد بصراحة ال `start` ارجيومنت عشان توضح بالظبط انت عاوز ايه .
<sup>[[link](#no-datetime)]</sup>

  ```ruby
  # سئ - استخدم DateTime للوقت بتاع دلوقتي 
  DateTime.now

  # جيد - استخدم Time للوقت دلوقتي 
  Time.now

  # سئ - استخدم DateTime للتوقيتات العصرية
  DateTime.iso8601('2016-06-29')

  # جيد - استخدم Date للتوقيتات العصرية 
  Date.iso8601('2016-06-29')
  # جيد - استخدم DateTime و معاها start argument للتاريخ القديم.
  DateTime.iso8601('1751-04-23', Date::ENGLAND)
  ```

## التعبيرات العادية

> بعض الناس, لما بتواجهم مشكلة بيفكر,
> "انا عارف, انا هستخدم التعبيرات العادية" دلوقتي بقي عنده مشكلتين.<br>
> -- Jamie Zawinski

* <a name="no-regexp-for-plaintext"></a>
  متستخدمش التعبيرات العادية لو بتدور علي string في نص عادي: `string['text']`
<sup>[[link](#no-regexp-for-plaintext)]</sup>

* <a name="regexp-string-index"></a>
  لتكوين بسيط انت ممكن تستخدم regexp مباشرة خلال string index.
<sup>[[link](#regexp-string-index)]</sup>

  ```ruby
  match = string[/regexp/]             # هات المحتوي اللي بيساوي ال regexp
  first_group = string[/text(grp)/, 1] # هات امحتي من المجموعة الي ماسكها
  string[/text (grp)/, 1] = 'replace'  # string => 'text replace'
  ```

* <a name="non-capturing-regexp"></a>
  استخدم مجموعات ال non-capturing لما متكونش هتستخدم ناتج ال captured.
<sup>[[link](#non-capturing-regexp)]</sup>

  ```ruby
  # سئ
  /(first|second)/

  # جيد
  /(?:first|second)/
  ```

* <a name="no-perl-regexp-last-matchers"></a>
  متستخدمش متغيرات ال cryptic Perl-legacy للدلالة علي اخر مجموعة بتطابق ال regexp (`$1`, `$2`, وهكذا).
 استخدم `Regexp.last_match(n)` بدلها.
<sup>[[link](#no-perl-regexp-last-matchers)]</sup>

  ```ruby
  /(regexp)/ =~ string
  ...

  # سئ
  process $1

  # جيد
  process Regexp.last_match(1)
  ```

* <a name="no-numbered-regexes"></a>
  تجنب استخدام المجموعات المرقمة عشان بيبقي صعب متابعة محتواها.
 ممكن تسمي مجموعات متسمية احسن منها .
<sup>[[link](#no-numbered-regexes)]</sup>

  ```ruby
  # سئ
  /(regexp)/ =~ string
  # some code
  process Regexp.last_match(1)

  # جيد
  /(?<meaningful_var>regexp)/ =~ string
  # some code
  process meaningful_var
  ```

* <a name="limit-escapes"></a>
  ال Character classes عندهم بس قليل من الحروف اللي المفروض تهتم بيهم:
هم `^`, `-`, `\`, `]`, يبقي متتجنبش  `.` او الاقواس في `[]`.
<sup>[[link](#limit-escapes)]</sup>

* <a name="caret-and-dollar-regexp"></a>
  خد بالك من `^` و `$` عشان هم بيعبروا عن بداية/نهاية السطر . مش بتاعت ال string.
 لو عاوز تطتبق ال string كله استخدم `\A` و `\z` (متخليش  `\Z` اللي هي بتساوي `/\n?\z/`).
<sup>[[link](#caret-and-dollar-regexp)]</sup>

  ```ruby
  string = "some injection\nusername"
  string[/^username$/]   # متطابقة
  string[/\Ausername\z/] # لا تطابق
  ```

* <a name="comment-regexes"></a>
  استخدم `x` في علامات ال regexps المعقدة .
 دا هيخليك تعرف تقري كويس و تقدر تحط شوية تعليقات مفيدة.
 بس خد بالك المسافات مبتتحسبش.ً
<sup>[[link](#comment-regexes)]</sup>

  ```ruby
  regexp = /
    start         # some text
    \s            # white space char
    (group)       # first group
    (?:alt1|alt2) # some alternation
    end
  /x
  ```

* <a name="gsub-blocks"></a>
  للتبديل المعقد `sub`/`gsub` ممكن تستخدم مع بلوك او هاش.
<sup>[[link](#gsub-blocks)]</sup>

  ```ruby
  words = 'foo bar'
  words.sub(/f/, 'f' => 'F') # => 'Foo bar'
  words.gsub(/\w+/) { |word| word.capitalize } # => 'Foo Bar'
  ```

## حرف النسبة المئوية

* <a name="percent-q-shorthand"></a>
  استخدم `%()` (دي اختصار ل `%Q`) اللي بتشتغل علي ال لسطر واحد single-line
 اليي بتبقي محتاجة حاجتين interpolation و انك تحط double-quotes .
 في حالة تعدد السطور بيفضل ال heredocs.
<sup>[[link](#percent-q-shorthand)]</sup>

  ```ruby
  # سئ (مفيش اي حاجة لل interpolation)
  %(<div class="text">Some text</div>)
  # should be '<div class="text">Some text</div>'

  # سئ (مفي double-quotes)
  %(This is #{quality} style)
  # المفروض تبقي  "This is #{quality} style"

  # سئ (متعدد السطور)
  %(<div>\n<span class="big">#{exclamation}</span>\n</div>)
  # المفروض تبقي heredoc.

  # جيد (محتاجة  interpolation, عندها quotes,سطر واحد )
  %(<tr><td class="name">#{name}</td>)
  ```

* <a name="percent-q"></a>
  تجنب %() او اللي زيها بالظبط %q() طالما مش عندك الاتنيد دول `'` و `"` جوا ال string.
 علامات ال string العادية اسهل للقراية و دايما مفضلة طالما مش عندك رموز كتيرة عاوز تبطل مفعولها
<sup>[[link](#percent-q)]</sup>

  ```ruby
  # سئ
  name = %q(Bruce Wayne)
  time = %q(8 o'clock)
  question = %q("What did you say?")

  # جيد
  name = 'Bruce Wayne'
  time = "8 o'clock"
  question = '"What did you say?"'
  quote = %q(<p class='quote'>"What did you say?"</p>)
  ```

* <a name="percent-r"></a>
 استخدم `%r` فقط في التعبيرات العادية اللي بتساوي *علي الاقل* واحد من دا '/' .
<sup>[[link](#percent-r)]</sup>

  ```ruby
  # سئ
  %r{\s+}

  # جيد
  %r{^/(.*)$}
  %r{^/blog/2011/(.*)$}
  ```

* <a name="percent-x"></a>
  تجنب استخدام `%x` طالما مش هتبعت معاها امر معين 
(و هي حاجة مستبعدة ل حد ما).
<sup>[[link](#percent-x)]</sup>

  ```ruby
  # سئ
  date = %x(date)

  # جيد
  date = `date`
  echo = %x(echo `date`)
  ```

* <a name="percent-s"></a>
   تجنب استخدام `%s`.
  يبدو ان المجتمع قرر `:"some string"` الطريقة المفضلة عشان تعمل symbol
 مع وجود مسافات فاضية جواها .
<sup>[[link](#percent-s)]</sup>

* <a name="percent-literal-braces"></a> 
  استخدم الاقواس الانسب للعلامة المئوية.
  <sup>[[link](#percent-literal-braces)]</sup>
  - `()` لتعريف ال string (`%q`, `%Q`).
  - `[]` لتعريف ال array (`%w`, `%i`, `%W`, `%I`) دا غير انها بتشتغل مع علامة الاراي العادية.
  - `{}` ل اعريف ال regexp (`%r`) لما بيكون الاقواس موجودة جوا التعبير .
  و لهاذا السبب الحرف الاقل شيوعا مع ال `{` هو دايما افضل delimiter في حالة ال `%r`.
  - `()`لجميع العلامات التانية  (زي `%s`, `%x`)

  ```ruby
  # سئ
  %q{"Test's king!", John said.}

  # جيد
  %q("Test's king!", John said.)

  # سئ
  %w(one two three)
  %i(one two three)

  # جيد
  %w[one two three]
  %i[one two three]

  # سئ
  %r((\w+)-(\d+))
  %r{\w{1,2}\d{2,5}}

  # جيد
  %r{(\w+)-(\d+)}
  %r|\w{1,2}\d{2,5}|
  ```

## ميتابروجرامينج

* <a name="no-needless-metaprogramming"></a>
  تجنب ال  metaprogramming اللي ملهاش لازمة.
<sup>[[link](#no-needless-metaprogramming)]</sup>

* <a name="no-monkey-patching"></a>
  متلعبش في المكتبات الاساسية في اللغة لما تيجي تعمل حاجة جديدة.
  (متعملش زي ال monkey-patch معاهم.)
<sup>[[link](#no-monkey-patching)]</sup>

* <a name="block-class-eval"></a>
  البلوك اللي بتعمل من `class_eval` بيفضل ل ال string-interpolated .
<sup>[[link](#block-class-eval)]</sup>
 
  - لما تيجي تستخدم نموذج ال string-interpolated, دايما وفر `__FILE__` و `__LINE__` 
  , عشان اقواسك يبقوا اكتر منطقية:

    ```ruby
    class_eval 'def use_relative_model_naming?; true; end', __FILE__, __LINE__
    ```

  - `define_method` بيفضل ل  `class_eval{ def ... }`

* <a name="eval-comment-docs"></a>
  لما تيجي تستخدم `class_eval` (او اي `eval` تاني ) و معاه string interpolation,
 حط معاه بلوك من التعليقات يوضح المظهر بتاع ال interpolated (مثال متاخد من كود الرايلز)
<sup>[[link](#eval-comment-docs)]</sup>

  ```ruby
  # من activesupport/lib/active_support/core_ext/string/output_safety.rb
  UNSAFE_STRING_METHODS.each do |unsafe_method|
    if 'String'.respond_to?(unsafe_method)
      class_eval <<-EOT, __FILE__, __LINE__ + 1
        def #{unsafe_method}(*params, &block)       # def capitalize(*params, &block)
          to_str.#{unsafe_method}(*params, &block)  #   to_str.capitalize(*params, &block)
        end                                       # end

        def #{unsafe_method}!(*params)              # def capitalize!(*params)
          @dirty = true                           #   @dirty = true
          super                                   #   super
        end                                       # end
      EOT
    end
  end
  ```

* <a name="no-method-missing"></a>
  تجنب استخدام ال `method_missing` في ال ميتابروجرايمنج عشان ال backtraces بيبقي فوضوي,
  التصرف مبيبقي مرصود ف ال `#methods` و الخطاء في كتابة اسم دالة هيشغله بهدوء, زي `nukes.launch_state = false`. 
  اعتبر استخدام delegation, proxy, او `define_method` كبديل.
  لو لازمك يعني استخدام `method_missing`:
<sup>[[link](#no-method-missing)]</sup>

  - خليك متأكد ان [و برضه معرف `respond_to_missing?`](http://blog.marc-andre.ca/2010/11/methodmissing-politely.html)
  - اسمك الدوال اللي بدايتها محددة جدا, زي  `find_by_*` -- خلي كودك مؤكد قدر المستطاع.
  - كلم `super` في اخر سطر عندك
  - خلي التاكيد علي , الدوال غير سحرية:

    ```ruby
    # سئ
    def method_missing?(meth, *params, &block)
      if /^find_by_(?<prop>.*)/ =~ meth
        # ... lots of code to do a find_by
      else
        super
      end
    end

    # جيد
    def method_missing?(meth, *params, &block)
      if /^find_by_(?<prop>.*)/ =~ meth
        find_by(prop, *params, &block)
      else
        super
      end
    end

    # افضل الموجودين, علي الرغم , من انك ه define_method مع كل attribute هتلاقيه متعرف
    ```

* <a name="prefer-public-send"></a>
  بيفضل `public_send` عن `send` عشان متتلغبتش مع ال `private`/`protected` المتاحة .
<sup>[[link](#prefer-public-send)]</sup>

  ```ruby
  # احنا عندنا منظومة من ال ActiveModel و اللي بتضمن concern Activatable
  module Activatable
    extend ActiveSupport::Concern

    included do
      before_create :create_token
    end

    private

    def reset_token
      # شوية كود هنا
    end

    def create_token
      # شوية كود هنا
    end

    def activate!
      # شوية كود هنا
    end
  end

  class Organization < ActiveRecord::Base
    include Activatable
  end

  linux_organization = Organization.find(...)
  # سئ - بيخض علي الخصوصيات
  linux_organization.send(:reset_token)
  # جيد - هيرجع استثناء
  linux_organization.public_send(:reset_token)
  ```

* <a name="prefer-__send__"></a>
بيفضل `__send__` عن `send` لانها ممكن تلغبط مع دالة موجودة اصلا.
<sup>[[link](#prefer-__send__)]</sup>

  ```ruby
  require 'socket'

  u1 = UDPSocket.new
  u1.bind('127.0.0.1', 4913)
  u2 = UDPSocket.new
  u2.connect('127.0.0.1', 4913)
  # مش هتبعت حالة للعنصر اللي مفروض يستلم.
  # في المقابل هتبعتها عن طريق ال UDP socket.
  u2.send :sleep, 0
  #كدا فعلا هتبعت للعنصر اللي مفروض يستلم.
  u2.__send__ ...
  ```

## متفرقات

* <a name="always-warn"></a>
  اكتب `ruby -w` لكود أمن.
<sup>[[link](#always-warn)]</sup>

* <a name="no-optional-hash-params"></a>
  تجنب ال hashes ك باراميتر اختيارية. الدالة بتاعتك بتعمل حاجات كتير؟
 (معرف ال Object استثناء للقاعدة دي).
<sup>[[link](#no-optional-hash-params)]</sup>

* <a name="short-methods"></a>
   تجنب الدوال اللي حجمها اطول من 10 سطور, لو عاوز تبقي مثالي اوي المفروض تبقي اصغر من 10 سطور.
  السطور الفاضية مش بتساهم في موضوع السطور دا.
<sup>[[link](#short-methods)]</sup>

* <a name="too-many-params"></a>
  تجنب ال  parameter lists اطول من تلاتة او اربعة براميتر.
<sup>[[link](#too-many-params)]</sup>

* <a name="private-global-methods"></a>
  لو انت فعلا محتاج دالة "global"و حطهم ف ال kenral  و اعملهم private.
<sup>[[link](#private-global-methods)]</sup>

* <a name="instance-vars"></a>
  استخدم متغيرات ال module نوع instance بدال ما تستخدم ال global variables.
<sup>[[link](#instance-vars)]</sup>

  ```ruby
  # سئ
  $foo_bar = 1

  # جيد
  module Foo
    class << self
      attr_accessor :bar
    end
  end

  Foo.bar = 1
  ```

* <a name="optionparser"></a>
  استخدم `OptionParser` ل تحليل الاوامر الاختيارية  المعقدة و `ruby -s` لل الاوامر التافهة.
<sup>[[link](#optionparser)]</sup>

* <a name="functional-code"></a>
  اكت كود بطريقة وظيفية و تجنب ال mutation لما تكون اكثر منطقية.
<sup>[[link](#functional-code)]</sup>

* <a name="no-param-mutations"></a>
  متعملش mutate parameters طالما دا هدف الدالة .
<sup>[[link](#no-param-mutations)]</sup>

* <a name="three-is-the-number-thou-shalt-count"></a>
  تجنب اكتر من تلت مستوايات من البلوك جوا بعض.
<sup>[[link](#three-is-the-number-thou-shalt-count)]</sup>

* <a name="be-consistent"></a>
  
  خلي ثابت علي مبداك. في عالم مثالي , خليك ثابت علي الدليل دا.
<sup>[[link](#be-consistent)]</sup>

* <a name="common-sense"></a>
  استخدم المنطق.
<sup>[[link](#common-sense)]</sup>

## الادوات

في شوية ادوات تساعد تفحص كود الروبي بتاعك اوتوماتيك كدا بدل الدليل دا.

### روبوكب
[RuboCop][] هو بيفحص ل شكل كود الروبي و المرجع بتاعه الدليل دا.
روبوكب شامل جزء مش قليل من الدليل دا,
بيدعم الاتنين MRI 1.9 و MRI 2.0 و عنده قابليه للدمج كويس مع Emacs.

### RubyMine

[RubyMine](http://www.jetbrains.com/ruby/) دا محلل الكود بتاعه
[جزئيا بيعتمد](http://confluence.jetbrains.com/display/RUBYDEV/RubyMine+Inspections)
علي الدليل دا.

# المشاركة

الدليل دا لسة شغالين عليه; بعض القواعد ناقصها امثلة,
و بعض القواعد معندهاش امثلة تفصله بشكل واضح و كافي.
لتحسين القواعد دي بطريقة عظيمة (و طريقة سهلة) لمساعدة مجتمع الروبي!
في الوقت الحالي المشاكل دي (نتمني) تتصلح انت بس حطهم في بالك دلوقتي.
مفيش حاجة في الدليل دا مكتوبة علي حتة حجر, دي رغبتي في الشغل مع كل من الناس المهتمة بوجود طريقة لكتابة الروبي 
عشان كدا احنا نقدر نعمل دليل هيعود بالنفع علي كل مجتمع الروبي.

خد راحتك خالص انك تبلغ بمشكلة او تضيف تغيير في تحسينات. و شكرا مقدما علي تعبك دا
انت بره تقدر تساعد في البروجكت (و روبوكب) بالفلوس عن طريق [Gratipay](https://gratipay.com/~bbatsov/).
[![Support via Gratipay](https://cdn.rawgit.com/gratipay/gratipay-badge/2.3.0/dist/gratipay.png)](https://gratipay.com/~bbatsov/)


## ازاي تشارك؟

بمنتهي السهولة, اتبع الخطوات دي [contribution guidelines](https://github.com/HassanTC/ruby-style-guide/blob/master/CONTRIBUTING.md).

# الرخصة

![Creative Commons License](http://i.creativecommons.org/l/by/3.0/88x31.png)
العمل دا بينطبق عليه الرخصة دي [Creative Commons Attribution 3.0 Unported License](http://creativecommons.org/licenses/by/3.0/deed.en_US)

# انشر الكلمة

الدليل اللي موجود بسبب ال مجتمع قيمته قليلة لمجتمع ميعرفش عن وجوده.
اكتب عنه ف تويتر، انشره لزمايلك و صحابك.
كل كومنت و اقتراح و رايي بيخلي الدليل احسن 
واحنا عايزين احسن دليل ممكن، مش كدا؟ 
علي وضعك,<br>
[Bozhidar](https://twitter.com/bbatsov)

[PEP-8]: https://www.python.org/dev/peps/pep-0008/
[rails-style-guide]: https://github.com/bbatsov/rails-style-guide
[pickaxe]: https://pragprog.com/book/ruby4/programming-ruby-1-9-2-0
[trpl]: http://www.amazon.com/Ruby-Programming-Language-David-Flanagan/dp/0596516177
[Pandoc]: http://pandoc.org/
[RuboCop]: https://github.com/bbatsov/rubocop
[rdoc]: http://rdoc.sourceforge.net/doc/
