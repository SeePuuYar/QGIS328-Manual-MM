.. index:: Expressions

.. _vector_expressions:

*******************************
Expressions (စေခိုင်းချက်များ)
*******************************

.. only:: html

   .. contents::
      :local:
      :depth: 2

Layer data နှင့် ကြိုတင်တည်ဆောက်ထားသော သို့မဟုတ် အသုံးပြုသူသတ်မှတ်ထားသော function (လုပ်ဆောင်ချက်) များအပေါ်အခြေခံ၍ **Expressions** သည် ဂျီသြမေတြီစတိုင်၊ အညွှန်း၏ အကြောင်းအရာ သို့မဟုတ် အနေအထား၊ diagram အတွက် တန်ဖိုး၊ ပုံထုတ်အပြင်အဆင်တစ်ခု၏ အမြင့်၊ feature အချို့ကို ရွေးချယ်ရန်နှင့် virtual field ဖန်တီးရန်...စသည်တို့အတွက် attribute value (အချက်အလက်ပြဇယားတန်ဖိုး)၊ ဂျီသြမေတြီ နှင့် variable (ကိန်းရှင်) များကို ကိုင်တွယ်ရန် လုပ်ဆောင်ပေးနိုင်သောနည်းလမ်းတစ်ခုဖြစ်ပါသည်။

.. note:: Expression ရေးသားခြင်းအတွက် နဂိုပါရှိသော (default) function များနှင့် variable များစာရင်းကို :ref:`functions_list` တွင် အသေးစိတ်အချက်အလက်များနှင့် ဥပမာများဖြင့် တွေ့ရှိနိုင်ပါသည်။ 
  
.. _expression_builder:

The Expression string builder (Expression စာသား တည်ဆောက်ပေးသည့်အရာ)
====================================================================

Expression များတည်ဆောက်ရန် main dialog (ပင်မ ဒိုင်ယာလော့ခ်) ဖြစ်သော :guilabel:`Expression string builder (Expression စာသား တည်ဆောက်ပေးသည့်အရာ)` ကို QGIS ၏ အစိတ်အပိုင်းများစွာတွင် ရရှိနိုင်ပြီး၊ အထူးသဖြင့် အောက်ပါတို့ကိုလုပ်ဆောင်သောအခါတွင် ရရှိနိုင်ပါသည်-

* |expression| ခလုတ်ကို နှိပ်ခြင်း၊
* |expressionSelect|:sup:`Select By Expression...` tool ဖြင့် :ref:`features များရွေးချယ်ခြင်း <sec_selection>`၊
* ဥပမာ- |calculateField| :sup:`Field calculator` tool ဖြင့် :ref:`attribute များ ပြင်ဆင်တည်းဖြတ်ခြင်း <calculate_fields_values>`၊
* |dataDefine| :sup:`Data defined override` tool (:ref:`data_defined` ကို ကြည့်ပါ) ဖြင့် သင်္ကေတ၊ အညွှန်း သို့မဟုတ် layout item parameter များကို ကိုင်တွယ်ခြင်း၊
* :ref:`Geometry generator <geometry_generator_symbol>` သင်္ကေတ layer တစ်ခု တည်ဆောက်ခြင်း၊
* အချို့ :ref:`geoprocessing <label_processing>` များလုပ်ဆောင်ခြင်း။

Expression builder dialog တွင် အောက်ပါတို့ကို ပြုလုပ်နိုင်ပါသည်-

* :ref:`Expression tab <functions_list>` သည် ကြိုတင်သတ်မှတ်ထားသော function များစာရင်းကြောင့် အသုံးပြုရမည့် expression ကို ရေးသားရန်နှင့် စစ်ဆေးရန် ကူညီပေးသည်။
* :ref:`Function Editor tab <function_editor>` တွင် မိမိစိတ်ကြိုက် function များကို ဖန်တီးခြင်းဖြင့် function စာရင်းကို တိုးချဲ့နိုင်သည်။

The Interface (အသွင်အပြင်အနေအထား)
----------------------------------

:guilabel:`Expression` tab သည် function များ၊ layer field များနှင့် တန်ဖိုးများကို အသုံးပြု၍ expression များရေးသားရန် main interface (ပင်မ အသွင်အပြင်) ကို အသုံးပြုနိုင်သည်။ ၎င်းတွင် အောက်ပါ widget (အထားအသိုနေရာပုံစံ) များ ပါဝင်ပါသည်-

.. _figure_expression_tab:

.. figure:: img/function_list.png
   :align: center
   :width: 100%

   Expression tab

* Expression များ စာရိုက်ခြင်း သို့မဟုတ် ကူးထည့်ခြင်းအတွက် Expression များ တည်းဖြတ်ဧရိယာ။ Expression ရေးသားခြင်းကို မြန်ဆန်စေရန်အတွက် အလိုအလျောက်ဖြည့်စွက်မှု (Autocompletion) ကို ရရှိမည်ဖြစ်သည်-

  * ထည့်သွင်းထားသော စာသားများနှင့် သက်ဆိုင်သော variable များ၊ funcion အမည်များနှင့် field အမည်များကို အောက်တွင်ဖော်ပြထားသည်-  :kbd:`Up (အ‌ပေါ်)` နှင့် :kbd:`Down (အောက်)` မြှားများကို အသုံးပြုပြီး item များကို ရှာဖွေကြည့်ရှုပြီး Expression တွင် ထည့်သွင်းရန် :kbd:`Tab` ကို နှိပ်ပါ သို့မဟုတ် လိုချင်သည့် item ကို click နှိပ်ပါ။
  * ၎င်းတို့ကို ဖြည့်သွင်းစဉ်တွင် funcion parameter များကို ပြထားပါသည်။

  QGIS သည် အောက်ပါတို့ကို အသုံးပြုပြီး expression မှန်ကန်မှုကို စစ်ဆေးပေးပြီး error (အမှား)များအားလုံးကိုလည်း သိသာထင်ရှာစွာ ပြပေးပါသည်-

  * *Underline (အောက်ခံမျဥ်း)* - မသိရှိရသော function များ၊ မှားယွင်းသော သို့မဟုတ် ဆီလျော်မှုမရှိသော argument များအတွက်ဖြစ်သည်၊
  * *Marker (အမှတ်အသား)* - တည်နေရာတစ်ခုတည်းရှိ အခြား error တိုင်း (ဥပမာ- ကွင်းစကွင်းပိတ်များ (parenthesis) ကျန်ခဲ့ခြင်း၊ မမျှော်လင့်ထားသော စာလုံးများ) အတွက်ဖြစ်သည်။

  .. tip:: **Expression ကို မှတ်ချက် (comment) များဖြင့် မှတ်တမ်းတင်ပါ**

    ရှုပ်ထွေးသော expression ကို အသုံးပြုသောအခါ multiline comment (စာကြောင်းအများအပြားပါသောမှတ်ချက်) သို့မဟုတ် inline comment (စာကြောင်းအတွင်းထည့်သွင်းသော မှတ်ချက်) များအဖြစ် စာသားထည့်သွင်းပြီး လုပ်ဆောင်ခြင်းသည် ကောင်းသောအလေ့အကျင့်ဖြစ်သည်။ 

    ::

      /*
      Labels each region with its highest (in altitude) airport(s)
      and altitude, eg 'AMBLER : 264m' for the 'Northwest Artic' region
      */
      with_variable(
        'airport_alti', -- stores the highest altitude of the region
        aggregate(
          'airports',
          'max',
          "ELEV", -- the field containing the altitude
          -- and limit the airports to the region they are within
          filter := within( $geometry, geometry( @parent ) )
        ),
          aggregate( -- finds airports at the same altitude in the region
            'airports',
            'concatenate',
            "NAME",
            filter := within( $geometry, geometry( @parent ) )
              and "ELEV" = @airport_alti
          )
          || ' : ' || @airport_alti || 'm'
          -- using || allows regions without airports to be skipped
      )

* Expression editor အပေါ်ရှိ tool များကိုအသုံးပြု၍-

  * |fileNew|:sup:`Clear the expression editor` (Expression editor ကို ရှင်းလင်းခြင်း)၊
  * :ref:`User expressions (အသုံးပြုသူ expression များ) <user_expressions_functions>` ကို ဖန်တီးပြီး စီမံခန့်ခွဲနိုင်သည်။

* Expression editor အောက်တွင် အောက်ပါတို့ကို တွေ့မြင်ရမည်ဖြစ်သည်-

  * Expression တည်ဆောက်ရာတွင် အသုံးပြုနိုင်သော အခြေခံ operator များအစု
  * Data သတ်မှတ်ထားသော feature properties (ဂုဏ်သတ္တိများ) ရှိနေသောအခါ မျှော်လင့်ထားသော ရလာဒ် (output) ၏  format ညွှန်ပြချက်တစ်ခု
  * Default အားဖြင့် layer ၏ပထမဆုံး feature ပေါ်တွင် အကဲဖြတ်သော expression ၏ တိုက်ရိုက် :guilabel:`Output preview (ရလာဒ် အကြိုကြည့်ရှုမှု)` တစ်ခု (စာလုံး ၆၀ အလုံးထိ)။ စာလုံး 60 ထက်ကျော်လွန်သော output preview စာသားကိုကြည့်ရှုရန် စာသားပေါ်တွင် cursor ကိုတင်ထားခြင်းဖြင့် output preview တစ်ခုလုံးပါရှိသော tooltip pop-up ကိုပြသပေးနိုင်မည်ဖြစ်သည်။ Output preview စာသားကို clipboard ပေါ်သို့ ကော်ပီကူးရန် output preview  စာသားပေါ်တွင် click နှိပ်ပြီး |editCopy| :guilabel:`Copy Expression Value (Expression တန်ဖိုးကို ကော်ပီကူးခြင်း)` ကို ရွေးချယ်ပါ။
    
    :guilabel:`Feature` combobox ကို အသုံးပြု၍ layer ၏ အခြား feature များကို အကဲဖြတ်နိုင်ပါသည်။ (တန်ဖိုးများကို layer ၏ :ref:`display name (ပြသသောအမည်) <maptips>` property မှ ရယူပါသည်)။

    Error ရှိပါက ၎င်းကိုညွှန်ပြပြီး ပံ့ပိုးပေးထားသည့် hyperlink ဖြင့် အသေးစိတ်အချက်အလက်များကို ဝင်ရောက်ကြည့်ရှုနိုင်ပါသည်။ 

* Function ရွေးချယ်ပေးသည့်အရာသည် အုပ်စုအလိုက် ဖွဲ့စည်းထားသော function များ၊ variable များ၊ field များစာရင်းကို ပြသပေးသည်။ စာရင်းကို စစ်ထုတ် (filter) ရန်နှင့် သီးခြား function သို့မဟုတ် field တစ်ခုကို အမြန်ရှာဖွေရန် search box တွင် လုပ်ဆောင်နိုင်သည်။ Item တစ်ခုကို click နှစ်ချက်နှိပ်ခြင်းဖြင့် ၎င်းကို expression editor ထဲသို့ ပေါင်းထည့်ပေးသွားမည်ဖြစ်သည်။
* Help panel သည် function ရွေးချယ်ပေးသည့်အရာထဲတွင် ရွေးချယ်ထားသည့် item တစ်ခုချင်းစီအတွက် အကူအညီကို ပြသပေးပါသည်။

  .. tip::

   Expression တစ်ခုထဲရှိ function အမည်တစ်ခုပေါ်တွင် cursor တင်ပြီး :kbd:`Ctrl+Click` ကိုနှိပ်ခြင်းသည် dialog ထဲတွင် ၎င်းအတွက် အကူအညီကို အလိုအလျှောက်ပြသပေးမည်ဖြစ်သည်။

  Function ရွေးချယ်ပေးသည့်အရာ ထဲတွင် field တစ်ခုကိုရွေးချယ်ထားသောအခါ ပြသသော field ၏တန်ဖိုးများ widget သည် feature attribute များကို ရယူရာတွင် အောက်ပါတို့ကိုလုပ်ဆောင်ပေးနိုင်ပါသည်-

  * သီးခြား field တန်ဖိုးတစ်ခုကို ရှာဖွေခြင်း
  * :guilabel:`All Unique` (ထင်ရှားသည်များအားလုံး) သို့မဟုတ် :guilabel:`10 Samples` (နမူနာ ၁၀ ခု) တန်ဖိုးများ၏ စာရင်းကို ပြသခြင်း။ Right-click မှလည်း ရရှိနိုင်ပါသည်။

    Field ကို အခြား layer သို့မဟုတ် တန်ဖိုးအစုတစ်ခုဖြင့် map ပြုလုပ်သောအခါ၊ ဆိုလိုသည်မှာ :ref:`field widget <edit_widgets>` သည် *RelationReference (ဆက်စပ်ရည်ညွှန်းချက်)* ၊ *ValueRelation (တန်ဖိုးဆက်စပ်ချက်)* သို့မဟုတ် *ValueMap (တန်ဖိုးမြေပုံ)* အမျိုးအစားများဖြစ်လျှင် map ပြုလုပ်ထားသော field ၏ တန်ဖိုးအားလုံးကို စာရင်းပြုလုပ်နိုင်သည် (ရည်ညွှန်း layer ၊ ဇယား သို့မဟုတ် စာရင်းမှ) ။ ထို့အပြင် လက်ရှိ field ထဲတွင် အသုံးပြုသော တန်ဖိုးများကိုသာ ပြသရန် |checkbox| :guilabel:`Only show values in use` ကို အမှန်ခြစ်ပြီး စာရင်းကို စစ်ထုတ် (filter) နိုင်ပါသည်။
  

  Widget ရှိ field တန်ဖိုးကို click နှစ်ချက်နှိပ်ခြင်းဖြင့် ၎င်းကို expression editor သို့ ပေါင်းထည့်ပေးမည်ဖြစ်သည်။

  .. tip::

   Function များအကူအညီ သို့မဟုတ် field တန်ဖိုးများကိုပြသသည့် ညာဘက်ရှိ panel ကို dialog ထဲတွင် ဖျောက်ထားနိုင်သည်။ ၎င်းကို ပြန်လည်ရရှိရန် :guilabel:`Show Values (တန်ဖိုးများကို ပြသခြင်း)` သို့မဟုတ် :guilabel:`Show Help (အကူအညီကို ပြသခြင်း)` ခလုတ်ကို နှိပ်ပါ။


Writing an expression (Expression တစ်ခု ရေးသားခြင်း)
-----------------------------------------------------

QGIS expression များကို feature များ ရွေးချယ်ရန် သို့မဟုတ် တန်ဖိုးများ သတ်မှတ်ရန်အတွက် အသုံးပြုကြသည်။ QGIS တွင် Expression တစ်ခု ရေးသားခြင်းသည် အောက်ပါ စည်းကမ်းအချို့ကို လိုက်နာပါသည်-

#. **Dialog သည် context (အကြောင်းအရာ)ကို သတ်မှတ်သည်** - သင်သည် SQL ကို အသုံးပြုနေကျဖြစ်လျှင် *select features from layer where condition* သို့မဟုတ် *update layer set field = new_value where condition* အမျိုးအစား၏ query (တန်ဖိုးများ၊ ဇယားများကို စစ်ထုတ်ခြင်း) များကို သိကောင်းသိပါလိမ့်မည်။ QGIS Expression တစ်ခုသည်လည်း ဤအချက်အလက်အားလုံးကို လိုအပ်သော်လည်း expression builder dialog ကိုဖွင့်ရန် အသုံးပြုသည့် tool သည် ၎င်းတို့ထဲမှ အစိတ်အပိုင်းများကို ပံ့ပိုးပေးထားပါသည်။ ဥပမာအားဖြင့် field (``height```) တစ်ခုဖြင့် layer (``buildings``) တစ်ခုကို ပေးထားပြီး-

   * |expressionSelect|:sup:`Select by expression` tool ကို နှိပ်ခြင်းဖြင့် "အဆောက်အဦများမှ feature များကို ရွေးချယ်" နိုင်သည်။  **Condition** သည် expression text widget တွင် ထည့်သွင်းပေးရန် လိုအပ်သည့် အချက်အလက်မျှသာ ဖြစ်သည်။ ဥပမာ- အမြင့် ၂၀ ထက် မြင့်သည့် အဆောက်အဦများကို ရွေးချယ်ရန် ``"height" > 20`` ကို ရိုက်ထည့်ပါ။
   * ဤရွေးချယ်မှုဖြင့် |calculateField| :sup:`Field calculator` ခလုတ်ကို နှိပ်ပြီး :guilabel:`Update existing field (ရှိပြီသား field ကို update ပြုလုပ်ခြင်း)` အဖြစ် "အမြင့်" ကို ရွေးချယ်ပါ။ "update buildings set height = ??? where height > 20" command ပေးပြီးသား ဖြစ်သွားပါလိမ့်မည်။ ဤကိစ္စတွင် ပံ့ပိုးပေးရမည့် ကျန်သည့် bit များသည် **တန်ဖိုးအသစ်** ဖြစ်သည်။ ဥပမာ- ယခင်ရွေးချယ်ထားသော အဆောက်အဦများ၏ အမြင့်ကို သတ်မှတ်ရန် expression editor textbox တွင် ``50`` ကို ရိုက်ထည့်ပါ။  

#. **Quotes များကို ဂရုပြုပါ** - Single quotes (' ') သည် စာသားဆိုလိုရင်း (literal) တစ်ခုပြန်ထုတ်ပေးသည်၊ ထို့ကြောင့် single quotes ကြားရှိ စာသား (``'145'``) ကို string (စာသား) အဖြစ် မှတ်ယူပါသည်။ Double quotes (" ") သည် ထိုစာသား၏ တန်ဖိုးကိုပေးမည်ဖြစ်သောကြောင့် ၎င်းတို့ကို field များ အတွက် အသုံးပြုပါ (``"myfield"``) ။ Field များကို quotes မပါပဲ အသုံးပြုနိုင်ပါသည် (``myfield``) ။ Number (အရေအတွက်) များအတွက် quote မရှိပါ (``3.16``)။

   .. note:: Function များသည် ပုံမှန်အားဖြင့် field အမည်အတွက် argument အနေဖြင့် string တစ်ခုကိုယူပါသည်။
      လုပ်ဆောင်ပါ-
      ::

        attribute( @atlas_feature, 'height' ) -- လက်ရှိ atlas feature ၏ "height" attribute တွင် သိမ်းဆည်းထားသော တန်ဖိုးကို ပြန်ထုတ်ပေးသည်။

      မလုပ်ဆောင်ပါနှင့်-
      ::

        attribute( @atlas_feature, "height" ) -- "height" (ဥပမာ- 100) ဟု အမည်ပေးထားသော attribute ၏တန်ဖိုးကို ရယူပြီး atlas feature တန်ဖိုးကို ပြန်ပေးရန်အတွက် ထိုတန်ဖိုးကို field တစ်ခုအဖြစ် အသုံးပြုပါသည်။ Field အမည် "100" ဆိုသည်မှာ ရှိမနေသောကြောင့် မှားကောင်းမှားနိုင်ပါသည်။

.. index:: Named parameters
   single: Expressions; Named parameters
   single: Functions; Named parameters

.. tip:: **Expression ဖတ်ခြင်းကို လွယ်ကူစေရန် အမည်ပေးထားသော parameter များကို အသုံးပြုပါ**

  အချို့သော function များတွင် parameter များစွာ သတ်မှတ်ရန်လိုအပ်ပါသည်။ Expression engine သည် အမည်ပေးထားသော parameter များ အသုံးပြုရန် ထောက်ပံ့ပေးပါသည်။ ဆိုလိုသည်မှာ ``clamp( 1, 2, 9)`` ဟု cryptic (ဖုံးကွယ်ထားသော) expression ကို ရေးမည့်အစား ``clamp( min:=1, value:=2, max:=9)`` ကို အသုံးပြုနိုင်သည်။ ဤအရာသည် argument ကို ပြောင်းလဲစေနိုင်ပါသည်၊ ဥပမာ ``clamp( value:=2, max:=9, min:=1)``။ အမည်ပေးထားသော parameter များကို အသုံးပြုခြင်းသည် expression function တစ်ခုအတွက် argument များသည် မည်သည့်အရာကို ရည်ညွှန်းသည်ကို ရှင်းလင်းစေပြီး ၎င်းသည် နောက်ပိုင်းတွင် expression တစ်ခုကို အဓိပ္ပာယ်ပြန်ဆိုသည့်အခါ အထောက်အကူဖြစ်စေသည်။

Some use cases of expressions (Expression များ အသုံးပြုမှုအချို့)
------------------------------------------------------------------

* Field Calculator မှ ရှိပြီးသား "total_pop"  နှင့် "area_km2" field များကို အသုံးပြုပြီး "pop_density" field တစ်ခုကို တွက်ချက်ခြင်း-
  ::

    "total_pop" / "area_km2"

* ၎င်းတို့၏ဧရိယာပေါ် အခြေခံ၍ feature များကို အညွှန်းတပ်ခြင်း သို့မဟုတ် အမျိုးအစားခွဲခြင်း-
  ::

    CASE WHEN $area > 10 000 THEN 'Larger' ELSE 'Smaller' END

* "pop_density" တန်ဖိုးအရ အမျိုးအစားများဖြင့် "density_level" field ကို update ပြုလုပ်ခြင်း-
  ::

    CASE WHEN "pop_density" < 50 THEN 'Low population density'
         WHEN "pop_density" >= 50 and "pop_density" < 150 THEN 'Medium population density'
         WHEN "pop_density" >= 150 THEN 'High population density'
    END

* ပျှမ်းမျှ အိမ်စျေးနှုန်းသည် တစ်စတုရန်းမီတာလျှင် ယူရို (၁၀၀၀၀)ထက် ငယ်သည် သို့မဟုတ် ကြီးသည်ပေါ်မူတည်၍ feature များအားလုံးကို အမျိုးအစားခွဲခြားခြင်း style ကို အသုံးပြုပါ-
  ::

    "price_m2" > 10000

* "Select By Expression..." tool ကို အသုံးပြု၍ “High population density” ဖြစ်ပြီး ပျမ်းမျှအိမ်စျေးနှုန်းသည် တစ်စတုရန်းမီတာလျှင် ယူရို (၁၀၀၀၀) ထက် ပိုမြင့်သော ဧရိယာများကို ကိုယ်စားပြုသည့် feature အားလုံးကို ရွေးချယ်ပါ-
  ::

    "density_level" = 'High population density' and "price_m2" > 10000

မြေပုံပေါ်တွင် မည်သည့် feature များကို အညွှန်းတပ်မည် သို့မဟုတ် ပြသမည်ကို သတ်မှတ်ရာတွင်လည်း ယခင်အသုံးပြုခဲ့သော Expression ကို အသုံးပြုနိုင်သည်။

* Geometry generator ကိုအသုံးပြု၍ layer အတွက် မတူညီသောသင်္ကေတ (အမျိုးအစား) တစ်ခုကိုဖန်တီးပါ-
  ::

    point_on_surface( $geometry )

* ပေးထားသော point feature တစ်ခု၏ ဂျီသြမေတြီ ပတ်လည်တွင် မျဉ်းပိတ်တစ်ကြောင်း (closed line) ကို ဖန်တီးပါ  (``make_line`` ကိုအသုံးပြု၍)-
  ::

    make_line(
      -- using an array of points placed around the original
      array_foreach(
        -- list of angles for placing the projected points (every 90°)
        array:=generate_series( 0, 360, 90 ),
        -- translate the point 20 units in the given direction (angle)
        expression:=project( $geometry, distance:=20, azimuth:=radians( @element ) )
      )
    )

* Print layout (ပုံထုတ်အပြင်အဆင်) အညွှန်းတစ်ခုတွင် layout "Map 1" item အတွင်းရှိ "airports" feature များ၏ အမည်ကို ပြသပါ-
  ::
   
   with_variable( 'extent',
                  map_get( item_variables( 'Map 1' ), 'map_extent' ),
                  aggregate( 'airports', 'concatenate', "NAME",
                             intersects( $geometry, @extent ), ' ,'
                           )
                )

.. index:: User expression
.. _user_expressions_functions:

Saving Expressions (Expression များကို သိမ်းဆည်းခြင်း)
-------------------------------------------------------

Expression editor frame အပေါ်မှ |fileSave| :sup:`Add current expression to user expressions` (လက်ရှိ expression ကို အသုံးပြုသူ expression များထဲသို့ပေါင်းထည့်ခြင်း) ခလုတ်ကို အသုံးပြု၍ အမြန်ဝင်ရောက်လိုသော အရေးကြီးသည့် expression များကို သိမ်းဆည်းနိုင်သည်။ ဤအရာများကို အလယ် panel ရှိ **User expressions (အသုံးပြုသူ expression များ)** အုပ်စုမှ ရရှိနိုင်သည်။ ၄င်းတို့ကို :ref:`user profile (အသုံးပြုသူ ပရိုဖိုင်) <user_profiles>` (:file:`<userprofile>/QGIS/QGIS3.ini` file) အောက်တွင် သိမ်းဆည်းထားပြီး လက်ရှိအသုံးပြုသူပရိုဖိုင်၏ project အားလုံးအတွင်းရှိ expression dialog များအားလုံးထဲတွင် ရရှိနိုင်ပါသည်။

အသုံးပြုသူ expression များကို စီမံခန့်ခွဲနိုင်ရန် Expression editor frame အထက်တွင် tool များရှိပါသည်-

* |fileSave|:sup:`Add the current expression to user expressions` (လက်ရှိ expression ကို အသုံးပြုသူ expression များထဲသို့ပေါင်းထည့်ခြင်း) - User profile ထဲတွင် expression ကို သိမ်းဆည်းသိုလှောင်နိုင်သည်။ လွယ်ကူစွာ သတ်မှတ်ဖော်ပြနိုင်ရန်အတွက် အညွှန်းတစ်ခုနှင့် စာသားတစ်ခုကို ထည့်သွင်းနိုင်သည်။
* |symbologyEdit| :sup:`Edit selected expression from user expressions` (အသုံးပြုသူ expression များမှ ရွေးချယ်ထားသော expression ကို တည်းဖြတ်ခြင်း)၊ ၄င်းတို့၏ အကူအညီနှင့် အညွှန်း များကိုလည်း ပြင်ဆင်တည်းဖြတ်နိုင်သည်။
* |deleteSelected| :sup:`Remove selected expression from user expressions` (အသုံးပြုသူ expression များမှ ရွေးချယ်ထားသော expression ကို ဖယ်ရှားခြင်း)
* |sharingImport| :sup:`Import user expressions` (အသုံးပြုသူ expression များထည့်သွင်းခြင်း) သည် expression များကို ``.json`` file တစ်ခုမှ active ဖြစ်နေသော user profile folder ထဲသို့ ထည့်သွင်းခြင်း
* |sharingExport| :sup:`Export user expressions` (အသုံးပြုသူ expression များ ထုတ်ယူခြင်း) သည် expression များကို ``.json`` file တစ်ခုအဖြစ် ထုတ်ယူပြီး user profile :file:`QGIS3.ini` file ထဲရှိ အသုံးပြုသူ expression များအားလုံးကို မျှဝေပေးမည်ဖြစ်သည်။


.. index:: Custom functions
.. _function_editor:

Function Editor (Function ပြင်ဆင်တည်းဖြတ်သည့်အရာ)
==================================================

:guilabel:`Function Editor` tab တွင် Python language ဖြင့် ကိုယ်ပိုင် function များ ရေးသားနိုင်သည်။ ၎င်းသည် ကြိုတင်သတ်မှတ်ထားသော function များမရှိသေးသည့် သီးခြားလိုအပ်ချက်များကို ဖြေရှင်းရန် အသုံးဝင်ပြီး အဆင်ပြေသောနည်းလမ်းတစ်ခုဖြစ်ပါသည်။

.. _figure_expression_function:

.. figure:: img/function_editor.png
   :align: center

   Function Editor tab

Function အသစ်တစ်ခုဖန်တီးရန်-

#. |symbologyAdd| :sup:`New File` ခလုတ်ကို နှိပ်ပါ။
#. ပေါ်လာသော form ထဲတွင်အသုံးပြုမည့် အမည်တစ်ခုကို ရိုက်ထည့်ပြီး :guilabel:`OK` ကို နှိပ်ပါ။

   ပေးထားသော အမည်တစ်ခုဖြင့် item အသစ်တစ်ခုကို :guilabel:`Function Editor` tab ၏ ဘယ်ဘက် panel တွင် ထည့်သွင်းပေးထားမည်ဖြစ်သည်၊ ၄င်းသည် QGIS template file ကို အခြေခံထားသည့် Python :file:`.py` file တစ်ခုဖြစ်ပြီး active ဖြစ်နေသော :ref:`user profile <user_profiles>` directory အောက်တွင်ရှိသည့် :file:`/python/expressions` folder ထဲတွင် ၎င်းကိုသိမ်းဆည်းသိုလှောင်ထားပါသည်။
#. ညာဘက် panel သည် file ၏ အကြောင်းအရာကို ပြသပါသည်၊ python script template တစ်ခုဖြစ်သည်။ လိုအပ်သလို code နှင့် ၎င်း၏အကူအညီဆိုင်ရာ ကို update ပြုလုပ်ပါ။
#. |start| :guilabel:`Save and Load Functions` ခလုတ်ကို နှိပ်ပါ။ ရေးခဲ့သော function ကို :guilabel:`Expression` tab ရှိ function များ tree (Function များဖွဲ့စည်းပုံ) ထဲတွင် ပေါင်းထည့်မည်ဖြစ်သည်၊ default အားဖြင့် ``Custom`` အုပ်စုအောက်တွင်ဖြစ်ပါသည်။
#. Function အသစ်ကို ကောင်းမွန်စွာ အသုံးပြုနိုင်ပါသည်။
#. Function ကို ပိုမိုကောင်းမွန်အောင်လုပ်ဆောင်ရန်လိုအပ်ပါက :guilabel:`Function Editor` tab ကိုဖွင့်ပါ။ ပြောင်းလဲမှုများကို လုပ်ဆောင်ပြီး file တွင် ၄င်းတို့ကို အသုံးပြုနိုင်စေရန် |start| :guilabel:`Save and Load Functions` ခလုတ်ကို ထပ်မံနှိပ်ပါ။ ၎င်းတို့ကို Expression tab တိုင်းတွင်လည်း အသုံးပြုနိုင်မည်ဖြစ်သည်။

စိတ်ကြိုက် Python function များကို user profile လမ်းညွှန်အောက်တွင် သိမ်းဆည်းထားပါသည်။ ဆိုလိုသည်မှာ QGIS စတင်မှုတိုင်းတွင် လက်ရှိ user profile ဖြင့် သတ်မှတ်ထားသည့် function များအားလုံးကို အလိုအလျောက် ထည့်သွင်းပေးမည်ဖြစ်သည်။ Function အသစ်များကို :file:`/python/expressions` folder ထဲတွင်သာ သိမ်းဆည်းထားပြီး project file တွင် သိမ်းဆည်းမထားသည်ကို သတိပြုပါ။ စိတ်ကြိုက် function များထဲမှ တစ်ခုခုကိုအသုံးပြုထားသည့် project တစ်ခုခုကို မျှဝေပါက :file:`/python/expressions` folder ထဲရှိ :file:`.py` file ကိုလည်းမျှဝေရန် လိုအပ်ပါသည်။

စိတ်ကြိုက် function တစ်ခုကို ဖျက်ရန်-

#. :guilabel:`Function Editor` tab ကို ဖွင့်ပါ။
#. စာရင်းရှိ function ကို ရွေးပါ။
#. |symbologyRemove| :sup:`Remove selected function` ကို နှိပ်ပါ။ Function ကို စာရင်းမှ ဖယ်ရှားပစ်မည်ဖြစ်ပြီး သက်ဆိုင်ရာ ``.py`` file ကိုလည်း user profile folder မှ ဖယ်ရှားပစ်မည်ဖြစ်သည်။

**ဥပမာ**

အောက်ပါဥပမာသည် တန်ဖိုးနှစ်ခုဖြင့် လုပ်ဆောင်မည့် ကိုယ်ပိုင် ``my_sum`` function ကို ဖန်တီးသည့် အတိုချုပ်ဥပမာတစ်ခုဖြစ်ပါသည်-
 
.. code-block:: python

   from qgis.core import *
   from qgis.gui import *

   @qgsfunction(args='auto', group='Custom')
   def my_sum(value1, value2, feature, parent):
       """
       Calculates the sum of the two parameters value1 and value2.
       <h2>Example usage:</h2>
       <ul>
         <li>my_sum(5, 8) -> 13</li>
         <li>my_sum("field1", "field2") -> 42</li>
       </ul>
       """
       return value1 + value2


``@qgsfunction`` decorator သည် အောက်ပါ argument များကို လက်ခံပါသည်-

* ``args`` - Argument များအ‌ရေအတွက်။ ``args='auto'`` argument ကို အသုံးပြုသည့်အခါ Python (အနုတ် 2 - ``feature`` နှင့် ``parent (မူလ)``) ထဲတွင် function ကိုသတ်မှတ်ထားသော argument များအရေအတွက်ဖြင့် လိုအပ်သော function argument များအရေအတွက်ကို တွက်ချက်ပါမည်။ ``args = -1`` ဖြင့်ဆိုလျှင် မည်သည့် argument အရေအတွက်ကိုမဆို လက်ခံပါသည်။
* ``group`` argument သည် Expression dialog ထဲတွင် function ကို စာရင်းပြုစုသင့်သည့် အုပ်စုကို ညွှန်ပြပါသည်။
* ``usesgeometry=True`` ကို expression သည် feature ဂျီသြမေတြီသို့ ဝင်ရောက်ခွင့် လိုအပ်လျှင် အသုံးပြုပါသည်။ Default အားဖြင့် :const:`False` ဖြစ်ပါသည်။
* ``handlesnull=True`` ကို expression သည် NULL တန်ဖိုးများအတွက် စိတ်ကြိုက်ကိုင်တွယ်ရာတွင် အသုံးပြုသည်။ :const:`False` (default) ဖြစ်လျှင် မည်သည့် parameter တစ်ခုမဆိုသည် NULL ဖြစ်သည်နှင့် ရလာဒ်သည် အမြဲတမ်း NULL ဖြစ်ပါလိမ့်မည်။
* ``referenced_columns=[list]`` - Function အတွက် လိုအပ်သော attribute အမည်များ၏ Array တစ်ခု။ Default သည် ``[QgsFeatureRequest.ALL_ATTRIBUTES]`` ဖြစ်သည်။

Function ကိုယ်တိုင်သည် အောက်ပါ argument များကို ခွင့်ပြုပါသည်-

* အောက်ပါ argument များမတိုင်မီတွင် သတ်မှတ်ထားသော function သို့ ဖြတ်ကျော်လိုသည့် မည်သည့် ကိန်းဂဏန်းနှင့် parameter အမျိုးအစားများမဆို။
* ``feature`` - လက်ရှိ feature
* ``parent`` - :class:`QgsExpression <qgis.core.QgsExpression>` object
* ``context`` - နောက်ဆုံးအနေအထားတွင် ``context`` ဟုခေါ်သည့် argument တစ်ခုရှိလျှင် ဤ variable တွင် expression variable များကဲ့သို့ အမျိုးမျိုးသော ထပ်လောင်းသတင်းအချက်အလက်များကို ဝင်ရောက်ကြည့်ရှုခွင့်ပေးသည့် :class:`QgsExpressionContext <qgis.core.QgsExpressionContext>` object တစ်ခု ပါဝင်ပါသည်။ ဥပမာ- ``context.variable( 'layer_id' )``

ထို့နောက် အထက်တွင် ဖော်ပြထားသည့် ဥပမာ function ကို expression များတွင် အသုံးပြုနိုင်ပါသည်-

.. _figure_expression_custom_function:

.. figure:: img/customFunction.png
   :align: center

   Expression tab သို့ ပေါင်းထည့်ထားသော Custom Function


Python code ဖန်တီးခြင်းနှင့် ပတ်သက်သော နောက်ထပ်သတင်းအချက်အလက်များကို :ref:`PyQGIS-Developer-Cookbook` တွင် ရရှိနိုင်ပါသည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |calculateField| image:: /static/common/mActionCalculateField.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |dataDefine| image:: /static/common/mIconDataDefine.png
   :width: 1.5em
.. |deleteSelected| image:: /static/common/mActionDeleteSelected.png
   :width: 1.5em
.. |editCopy| image:: /static/common/mActionEditCopy.png
   :width: 1.5em
.. |expression| image:: /static/common/mIconExpression.png
   :width: 1.5em
.. |expressionSelect| image:: /static/common/mIconExpressionSelect.png
   :width: 1.5em
.. |fileNew| image:: /static/common/mActionFileNew.png
   :width: 1.5em
.. |fileSave| image:: /static/common/mActionFileSave.png
   :width: 1.5em
.. |sharingExport| image:: /static/common/mActionSharingExport.png
   :width: 1.5em
.. |sharingImport| image:: /static/common/mActionSharingImport.png
   :width: 1.5em
.. |start| image:: /static/common/mActionStart.png
   :width: 1.5em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
.. |symbologyEdit| image:: /static/common/symbologyEdit.png
   :width: 1.5em
.. |symbologyRemove| image:: /static/common/symbologyRemove.png
   :width: 1.5em
