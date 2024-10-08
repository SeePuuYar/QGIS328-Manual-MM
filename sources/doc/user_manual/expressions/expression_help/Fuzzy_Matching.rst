:orphan:

.. DO NOT EDIT THIS FILE DIRECTLY. It is generated automatically by
   populate_expressions_list.py in the scripts folder.
   Changes should be made in the function help files
   in the resources/function_help/json/ folder in the
   qgis/QGIS repository.

.. _expression_function_Fuzzy_Matching_hamming_distance:

hamming_distance
.................

String နှစ်ခုအကြားရှိ Hamming (သက်ဆိုင်ရာသင်္ကေတများ ကွဲပြားသွားသည့် နေရာအရေအတွက်) အကွာအဝေးကို ပြန်ထုတ်ပေးပါသည်။ ထည့်သွင်းလိုက်သည့် string များအတွင်း character များ မတူညီသည့် သက်ဆိုင်ရာ နေရာများ၌ရှိသော character များအရေအတွက် ဖြစ်ပါသည်။ ထည့်သွင်းလိုက်သည့် string များသည် တူညီသော စာလုံးအရေအတွက်ရှိရမည်ဖြစ်ပြီး နှိုင်းယှဉ်ရာတွင် case-sensitive (စာလုံးအကြီးအသေးဂရုပြု) ဖြစ်ပါသည်။

.. list-table::
   :widths: 15 85

   * - Syntax (ဝါကျဖွဲ့ပုံ)
     - hamming_distance(string1, string2)
   * - Argument များ
     - * **string1** - string တစ်ခု
       * **string2** - string တစ်ခု
   * - ဥပမာများ
     - * ``hamming_distance('abc','xec')`` → 2
       * ``hamming_distance('abc','ABc')`` → 2
       * ``hamming_distance(upper('abc'),upper('ABC'))`` → 0
       * ``hamming_distance('abc','abcd')`` → NULL


.. end_hamming_distance_section

.. _expression_function_Fuzzy_Matching_levenshtein:

levenshtein
............

String နှစ်ခုအကြား Levenshtein edit အကွာအဝေးကို ပြန်ထုတ်ပေးပါသည်။ ၎င်းသည် string တစ်ခုမှ အခြား string တစ်ခုသို့ ပြောင်းလဲရန်လိုအပ်သော အနည်းဆုံး character ပြင်ဆင်မှုများ (ထပ်ထည့်ခြင်း၊ ဖျက်ပစ်ခြင်းများနှင့် အစားထိုးခြင်းများ) အရေအတွက်ဖြစ်ပါသည်။

Levenshtein အကွာအဝေး သည် string နှစ်ခုအကြား ဆင်တူညီမှု (similarity) ကို တိုင်းတာခြင်းဖြစ်သည်။ အကွာအဝေးနည်းလေလေ string များသည် ပိုမိုဆင်တူလေဖြစ်ပြီး အကွာအဝေးများလေလေ string များပိုမို ကွဲပြားလေ ဖြစ်ပါသည်။ အကွာအဝေး သည် case-sensitive (စာလုံးအကြီးအသေးဂရုပြု) ဖြစ်ပါသည်။

.. list-table::
   :widths: 15 85

   * - Syntax (ဝါကျဖွဲ့ပုံ)
     - levenshtein(string1, string2)
   * - Argument များ
     - * **string1** - string တစ်ခု
       * **string2** - string တစ်ခု
   * - ဥပမာများ
     - * ``levenshtein('kittens','mitten')`` → 2
       * ``levenshtein('Kitten','kitten')`` → 1
       * ``levenshtein(upper('Kitten'),upper('kitten'))`` → 0


.. end_levenshtein_section

.. _expression_function_Fuzzy_Matching_longest_common_substring:

longest_common_substring
.........................

Sting နှစ်ခုအကြား အရှည်ဆုံးဘုံဖြစ်သော string အခွဲ (substring) ကို ပြန်ထုတ်ပေးပါသည်။ ဤ string အခွဲသည် အရှည်ဆုံး string ဖြစ်ပြီး ထည့်သွင်းထားသည့် string နှစ်ခု၏ string အခွဲတစ်ခုဖြစ်ပါသည်။ ဥပမာအားဖြင့် "ABABC" နှင့် "BABCA" ၏ အရှည်ဆုံးဘုံဖြစ်သော string အခွဲမှာ "BABC" ဖြစ်ပါသည်။ String အခွဲသည် case-sensitive (စာလုံးအကြီးအသေးဂရုပြု) ဖြစ်ပါသည်။

.. list-table::
   :widths: 15 85

   * - Syntax (ဝါကျဖွဲ့ပုံ)
     - longest_common_substring(string1, string2)
   * - Argument များ
     - * **string1** - string တစ်ခု
       * **string2** - string တစ်ခု
   * - ဥပမာများ
     - * ``longest_common_substring('ABABC','BABCA')`` → 'BABC'
       * ``longest_common_substring('abcDeF','abcdef')`` → 'abc'
       * ``longest_common_substring(upper('abcDeF'),upper('abcdex'))`` → 'ABCDE'


.. end_longest_common_substring_section

.. _expression_function_Fuzzy_Matching_soundex:

soundex
........

String တစ်ခု၏ Soundex ကိုယ်စားပြုမှုကို ပြန်ထုတ်ပေးပါသည်။ Soundex ဆိုသည်မှာ phonetic (အသံထွက်နှင့်ဆိုင်သော) ကိုက်ညီမှု algorithm တစ်ခုဖြစ်ပါသည်၊ ထို့ကြောင့် အသံထွက်ဆင်တူသော string များကို တူညီသော Soundex ကုဒ် ဖြင့် ကိုယ်စားပြုဖော်ပြသင့်ပါသည်။

.. list-table::
   :widths: 15 85

   * - Syntax (ဝါကျဖွဲ့ပုံ)
     - soundex(string)
   * - Argument များ
     - * **string** - string တစ်ခု
   * - ဥပမာများ
     - * ``soundex('robert')`` → 'R163'
       * ``soundex('rupert')`` → 'R163'
       * ``soundex('rubin')`` → 'R150'


.. end_soundex_section

