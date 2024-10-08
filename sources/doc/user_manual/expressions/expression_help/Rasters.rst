:orphan:

.. DO NOT EDIT THIS FILE DIRECTLY. It is generated automatically by
   populate_expressions_list.py in the scripts folder.
   Changes should be made in the function help files
   in the resources/function_help/json/ folder in the
   qgis/QGIS repository.

.. _expression_function_Rasters_raster_attributes:

raster_attributes
..................

Field အမည်များကို key များအဖြစ် နှင့် raster attribute ဇယားတန်ဖိုးများကို ပေးထားသော raster တန်ဖိုးနှင့်ကိုက်ညီသော attribute ဇယားထည့်သွင်းထားမှုမှ တန်ဖိုးများအဖြစ် ပါဝင်သည့် map တစ်ခုကို ပြန်ထုတ်ပေးပါသည်။

.. list-table::
   :widths: 15 85

   * - Syntax (ဝါကျဖွဲ့ပုံ)
     - raster_attributes(layer, band, value)
   * - Argument များ
     - * **layer** - raster layer တစ်ခု၏ အမည် သို့မဟုတ် id
       * **band** - သက်ဆိုင်ရာ attribute ဇယားရှာဖွေမှုအတွက် band (လှိုင်းအလွှာ) နံပါတ်
       * **value** - raster တန်ဖိုး
   * - ဥပမာများ
     - * ``raster_attributes('vegetation', 1, raster_value('vegetation', 1, make_point(1,1)))`` → {'class': 'Vegetated', 'subclass': 'Trees'}


.. end_raster_attributes_section

.. _expression_function_Rasters_raster_statistic:

raster_statistic
.................

Raster layer တစ်ခုမှ စာရင်းအင်းအချက်အလက်များ (statistics) များကို ပြန်ထုတ်ပေးပါသည်။

.. list-table::
   :widths: 15 85

   * - Syntax (ဝါကျဖွဲ့ပုံ)
     - raster_statistic(layer, band, property)
   * - Argument များ
     - * **layer** - raster layer အမည် သို့မဟုတ် layer ID တစ်ခုကို ကိုယ်စားပြုသော string တစ်ခု
       * **band** - raster layer မှ band နံပါတ်ကို ကိုယ်စားပြုသော ကိန်းပြည့်၊ 1 မှ စတင်ပါသည်။
       * **property** - ပြန်ထုတ်ပေးမည့် ဂုဏ်သတ္တိ (property) နှင့်သက်ဆိုင်သော string တစ်ခု။ ဆီလျော်မှုရှိသော ရွေးချယ်စရာများမှာ-

         

         * min: အနည်းဆုံးတန်ဖိုး
         * max: အများဆုံးတန်ဖိုး
         * avg: ပျမ်းမျှတန်ဖိုး
         * stdev: တန်ဖိုးများ၏ စံတိမ်းချက်
         * range: တန်ဖိုးများ၏ အပိုင်းအခြား (အများဆုံး - အနည်းဆုံး)
         * sum: raster မှ တန်ဖိုးများအားလုံး၏ ပေါင်းလဒ်


   * - ဥပမာများ
     - * ``raster_statistic('lc',1,'avg')`` → 'lc' raster layer ၏ band 1 မှ ပျှမ်းမျှတန်ဖိုး
       * ``raster_statistic('ac2010',3,'min')`` → 'ac2010' raster layer ၏ band 3 မှ အနည်းဆုံးတန်ဖိုး


.. end_raster_statistic_section

.. _expression_function_Rasters_raster_value:

raster_value
.............

ပေးထားသော point ၌ တွေ့ရှိရသော raster တန်ဖိုးကို ပြန်ထုတ်ပေးပါသည်။

.. list-table::
   :widths: 15 85

   * - Syntax (ဝါကျဖွဲ့ပုံ)
     - raster_value(layer, band, point)
   * - Argument များ
     - * **layer** - raster layer တစ်ခု၏ အမည် သို့မဟုတ် id
       * **band** - တန်ဖိုးကို နမူနာယူမည့် band နံပါတ်
       * **point** - point ဂျီဩမေတြီ (အစိတ်အပိုင်းတစ်ခုထက်ပိုပါသော multipart ဂျီဩမေတြီများအတွက် NULL တန်ဖိုးတစ်ခုကို ပြန်ထုတ်ပေးပါလိမ့်မည်)
   * - ဥပမာများ
     - * ``raster_value('dem', 1, make_point(1,1))`` → 25


.. end_raster_value_section

