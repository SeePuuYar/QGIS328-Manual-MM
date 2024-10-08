.. index:: Layout; Scale bar, Map scalebar
.. _layout_scalebar_item:

The Scale Bar Item (စကေးဘား Item)
==================================

.. only:: html

   .. contents::
      :local:

စကေးဘားများသည် မြေပုံပေါ်ရှိ feature များ၏အရွယ်အစားနှင့် feature များကြားအကွာအဝေး ကိုသရုပ်ဖော်ညွှန်ပြပေးသည်။ စကေးဘား တစ်ခုထည့်ရန် မြေပုံ item တစ်ခုလိုအပ်ပါသည်။ :ref:`Item များဖန်တီးခြင်းဆိုင်ရာညွှန်ကြားချက်များ <create_layout_item>` ကိုလိုက်နာပြီး |scaleBar| :guilabel:`Add Scale Bar` tool ကိုအသုံးပြု၍ :ref:`interact_layout_item` တွင်ဖော်ပြထားသည့် နည်းလမ်းအတိုင်းကိုင်တွယ်နိုင်မည့် စကေးဘားအသစ်တစ်ခုကိုထည့်နိုင်ပါသည်။ 

Default အားဖြင့် စကေးဘား အသစ်တစ်ခုသည် ၎င်းအားတင်ဆွဲထားသော မြေပုံ၏ စကေးကိုပြသခြင်းဖြစ်ပါသည်။ ၎င်းတွင် အောက်ခံမြေပုံမရှိခဲ့ပါက :ref:`reference map <reference_map>` (ရည်ညွှန်းမြေပုံ) ကိုရယူသုံးစွဲမည်ဖြစ်သည်။ ၎င်းကို :guilabel:`Item Properties` panel ထဲတွင်စိတ်ကြိုက်ပြင်ဆင်နိုင်ပါသည်။ ဤ feature တွင် :ref:`item များ၏ common ဂုဏ်သတ္တိများ <item_common_properties>` အပြင် အောက်ပါလုပ်ဆောင်ချက်များပါရှိသည် ( :numref:`figure_layout_scalebar` ကိုကြည့်ပါ)-

.. _figure_layout_scalebar:

.. figure:: img/scalebar_properties.png
   :align: center

   စကေးဘား Item ဂုဏ်သတ္တိများ Panel

Main properties (အဓိကဂုဏ်သတ္တိများ)
------------------------------------

စကေးဘား၏ :guilabel:`Item Properties` panel မှ :guilabel:`Main properties` အုပ်စုတွင် အောက်ပါလုပ်ဆောင်ချက်များပါဝင်သည် (:numref:`figure_layout_scalebar_ppt` ကိုကြည့်ပါ)-

.. _figure_layout_scalebar_ppt:

.. figure:: img/scalebar_mainproperties.png
   :align: center

   စကေးဘား အဓိကဂုဏ်သတ္တိများအုပ်စု

#. ပထမဦးစွာ စကေးဘား ထည့်သွင်းလိုသည့်မြေပုံကိုရွေးချယ်ပါ။ 
#. ထို့နောက် စကေးဘား၏ style ကိုရွေးချယ်ပါ။ ရရှိနိုင်သော style များမှာ-

   * အရောင်တစ်လှည့်စီသွားသောမျဉ်းကြောင်းအကွက် တစ်ခု သို့မဟုတ် နှစ်ခုပါဝင်သော **Single box** နှင့် **Double box** style များ
   * **Middle**၊ **Up** သို့မဟုတ် **Down** မျဉ်းအမှတ်အသားများ
   * စကေးဘားကို လှေကားထစ်ပုံစံမျဉ်းနှင့်သရုပ်ဖော်ပေးသည့် **Stepped line** style
   * အရောင်များတစ်လှည့်စီသွားသောအပိုင်းများနှင့် ထိုတစ်လှည့်စီသွားသောအပိုင်းများကို ဖြတ်ထားသည့်အလျားလိုက်မျဉ်းများပါဝင်သော အကွက်တစ်ခုကို ဆွဲပေးသည့်  **Hollow** style
   * စကေး၏အချိုးကိုပြသော **Numeric** (ဥပမာ- ``1:50000``)
#. ဂုဏ်သတ္တိများကိုသင့်တော်သလိုချိန်ညှိပါ။

Units (ယူနစ်များ)
------------------

စကေးဘားအတွက် :guilabel:`Item Properties` panel မှ :guilabel:`Units` အုပ်စုတ္ငင် ပြသလိုသည့်ယူနစ်များနှင့် အချို့စာသားပုံစံချမှုကိုသတ်မှတ်ရန် လုပ်ဆောင်ချက်များပါရှိသည် (:numref:`figure_layout_scalebar_units` ကိုကြည့်ပါ)-

.. _figure_layout_scalebar_units:

.. figure:: img/scalebar_units.png
   :align: center

   စကေးဘား ယူနစ်များ အုပ်စု

* :guilabel:`Scalebar units` ဖြင့် အသုံးပြုလိုသော ယူနစ်များကို ရွေးချယ်ပါ။ ရရှိနိုင်သော ရွေးချယ်စရာများစွာတွင်- **မြေပုံယူနစ်များ** (default ဖြစ်သည်)၊ **မီတာများ**၊ **ပေများ**၊ **မိုင်များ** သို့မဟုတ် **ရေမိုင်များ**... နှင့် အချို့ derivative (နောက်ဆက်တွဲဆင်းသက်လာသည့်အရာ) များပါဝင်သည်။ ယူနစ်များ ပြောင်းလဲခြင်းကို အလိုအလျောက် လုပ်ဆောင်နိုင်သည်။
* :guilabel:`Label unit multiplier` သည် label တပ်ထားသောယူနစ်တစ်ခုစီအတွက် စကေးဘားယူနစ် မည်မျှရှိသည်ကို သတ်မှတ်ပေးသည်။ ဥပမာအားဖြင့် စကေးဘားယူနစ်များကို "မီတာများ" ဖြင့် သတ်မှတ်ထားပါက 1000 ၏ဆတိုးကိန်းတစ်ခု ဖြစ်သောရလာဒ်အား စကေးဘား lable များတွင် "ကီလိုမီတာများ" ဖြင့်ပြသမည်ဖြစ်သည်။
* :guilabel:`Label for units` field သည် စကေးဘား၏ ယူနစ်များကိုဖော်ပြမည့်စာသားကို သတ်မှတ်ပေးသည်။ ဥပမာ- ``m`` သို့မဟုတ် ``km``။ အထက်တွင်ဖော်ပြခဲ့သည့် ဆတိုးကိန်းနှင့်ကိုက်ညီမှုရှိရပါမည်။
* :guilabel:`Number format` ဘေးမှ :guilabel:`Customize` ကိုနှိပ်၍ စကေးဘားထဲရှိ ဂဏန်းများအတွက် ထောင်ဂဏန်းပိုင်းခြားပေးသည့်အရာများ (thousand separators)၊ ဒဿမနေရာများ၊ သိပ္ပံဆိုင်ရာအမှတ်အသားများ အစရှိသည်တို့ပါဝင်သော format ဆိုင်ရာဂုဏ်သတ္တိများအားလုံးကို စီမံနိုင်သည်။ (နောက်ထပ် အသေးစိတ်အချက်အလက်များအတွက် :ref:`number_formatting` ကိုကြည့်ပါ)။ လက်ရှိ QGIS နယ်ပယ်၏ပြင်ပရှိ ပုဂ္ဂိုလ်များအတွက် မြေပုံများဖန်တီးရေးဆွဲရာတွင် သို့မဟုတ် locale default များနှင့် မတူညီသော style ကိုပြောင်းလဲအသုံးပြုလိုပါက လွန်စွာအသုံးဝင်မည်ဖြစ်သည် (ဥပမာ- locale default တွင် ထောင်ဂဏန်းပိုင်းခြားပေးသည့်အရာများ (thousand separators) ကို ဖျောက်ထားသောအခါ thousand separator များကိုပေါင်းထည့်ခြင်း)။
  
Segments (အပိုင်းများ)
-----------------------

စကေးဘားအတွက် :guilabel:`Item Properties` panel ရှိ :guilabel:`Segments` အုပ်စုတွင် အပိုင်းများနှင့် အပိုင်းခွဲများ၏ အရေအတွက်နှင့် အရွယ်အစားကို သတ်မှတ်ထားရှိနိုင်မည့် လုပ်ဆောင်ချက်များပါဝင်သည် (:numref:`figure_layout_scalebar_segments` ကိုကြည့်ပါ)-

.. _figure_layout_scalebar_segments:

.. figure:: img/scalebar_segments.png
   :align: center

   စကေးဘား အပိုင်းများ အုပ်စု

* စကေးဘားမှ ``0`` ၏ ဘယ်ဘက်နှင့်ညာဘက်များတွင် ရေးဆွဲမည့် :guilabel:`Segment` များ၏အရေအတွက်ကိုသတ်မှတ်နိုင်သည်-

  * :guilabel:`ဘယ်ဘက်` ရှိ သီးသန့်အပိုင်းတစ်ခု၏ အပိုင်းခွဲအရေအတွက်
  * :guilabel:`ညာဘက်` ရှိ အပိုင်းများအရေအတွက်
*  အပိုင်းတစ်ခု၏အကျယ် သို့မဟုတ် စကေးဘား၏ စုစုပေါင်းအလျားအတွက် အပိုင်းအခြားကိုသတ်မှတ်နိုင်သည်-
  
  * စကေးဘား ယူနစ်များထဲတွင် အပိုင်းတစ်ခုသည် မည်မျှရှည်မည်ကိုသတ်မှတ်နိုင်သည် (:guilabel:`Fixed width`)
  * သို့မဟုတ် စုစုပေါင်း စကေးဘား အရွယ်အစားအား :guilabel:`Fit segment width` option သုံး၍ ``mm`` နှင့် ကန့်သတ်ထားနိုင်သည်။ ဒုတိယတစ်ခုတွင် မြေပုံစကေးပြောင်းလဲသွားသည့်အချိန်တိုင်း  သတ်မှတ်ထားသောအပိုင်းအခြားအကြားတွင်ဝင်ဆံ့ရန် စကေးဘားကို အရွယ်အစား ပြန်လည်သတ်မှတ်ပေးမည်ဖြစ်သည် (ထို့နောက် ၎င်း၏ label သည်လည်း အသစ်ဖြစ်သွားမည်)။

* ဘား၏အမြင့်ကို သတ်မှတ်ရန် :guilabel:`Height` ကိုအသုံးပြုသည်။ 
* :guilabel:`Right segment subdivisions` ကို စကေးဘား၏ညာဘက်ရှိအပိုင်းများတွင် ရှိနိုင်သော အပိုင်းခွဲများအရေအတွက်ကိုသတ်မှတ်ရန် အသုံးပြုသည်။ (*Line Ticks Down* ၊ *Line Ticks Middle* နှင့် *Line Ticks Up* စကေးဘား style များအတွက်) 
* အပိုင်းခွဲ၏အမြင့်ကိုသတ်မှတ်ရန် :guilabel:`Subdivision height` ကိုအသုံးပြုသည်။


Display (ပြသမှု)
-----------------

စကေးဘားအတွက် :guilabel:`Item Properties` panel မှ :guilabel:`Display` အုပ်စုတွင်အောက်ပါလုပ်ဆောင်ချက်များပါဝင်သည်-

.. _figure_layout_scalebar_display:

.. figure:: img/scalebar_display.png
   :align: center

   စကေးဘား ပြသမှု အုပ်စု

စကေးဘားအား ၎င်း၏ frame ထဲတွင် မည်သို့ပြသလိုသည်ကို သတ်မှတ်နိုင်သည်-

* :guilabel:`Box margin` - စာသားနှင့် frame border များအကြားအကွာအဝေး
* :guilabel:`Label margin` - စာသားနှင့် စကေးဘား ကြား အကွာအဝေး
* :guilabel:`Vertical label placement` -  စကေးဘား အပိုင်း ၏ အထက် သို့ အောက်တွင် ၎င်းကိုထားရှိနိုင်သည်။
* :guilabel:`Horizontal label placement`- စကေးဘား အပိုင်း ၏ အစွန်း သို့ အလယ်ဗဟိုတွင် ထားရှိနိုင်သည်။
* *Single Box*၊ *Double Box* နှင့် *Hollow* style များအတွက် :ref:`အဖြည့် သင်္ကေတဂုဏ်သတ္တိများ <vector_fill_symbols>` (အရောင်၊ အလင်းပိတ်မှု၊ ပုံစံကွက်များ၊ effect များ...) ကိုအသုံးပြု၍ စကေးဘား၏ :guilabel:`Primary fill` နှင့် :guilabel:`Secondary fill` ကိုသတ်မှတ်ပေးသည်။
* *Numeric* style မှလွဲ၍အားလုံးအတွက် :ref:`လိုင်း သင်္ကေတဂုဏ်သတ္တိများ <vector_line_symbols>` (အရောင်၊ အထူ၊ ချိတ်ဆက်မှုပုံစံ၊ အဆုံးသတ်ပုံစံ၊ ပုံစံကွက်များ၊ effect များ...) ကိုအသုံးပြု၍ စကေးဘား၏ :guilabel:`Line style` ကိုသတ်မှတ်ပေးသည်။
* :guilabel:`Division style` နှင့် :guilabel:`Subdivision style` သည် *Line Ticks Up*၊ *Line Ticks Middle* နှင့် *Line Ticks Down* စကေးဘား style များရှိ အပိုင်းနှင့်အပိုင်းခွဲအသီးသီးအတွက် :ref:`လိုင်း သင်္ကေတဂုဏ်သတ္တိများ <vector_line_symbols>` (အရောင်၊ အထူ၊ ချိတ်ဆက်မှုပုံစံ၊ အဆုံးသတ်ပုံစံ၊ ပုံစံကွက်များ၊ effect များ...) ကိုအသုံးပြု၍ သတ်မှတ်ပေးသည်။
* :guilabel:`Alignment` သည် စာသားကို frame ၏ဘယ်ဘက်၊ အလယ်ဗဟို သို့မဟုတ် ညာဘက်တွင်ထားပေးသည် ( *Numeric* စကေးဘား style အတွက်သာ)။  
* :guilabel:`Font` ဖြင့် စကေးဘား label ၏ :ref:`ဂုဏ်သတ္တိများ <text_format>` (အရွယ်အစား၊ စာလုံးဖောင့်၊ အရောင်၊ စာလုံးများကြားအကွာအဝေး၊ အရိပ်၊ နောက်ခံ...)  ကိုသတ်မှတ်ပေးသည်။

စကေးဘား၏ သရုပ်ဖော်ပြသမှုဆိုင်ရာ ဂုဏ်သတ္တိအများစုသည် data ဖြင့်သတ်မှတ်ထားသော (data-defined) ဂုဏ်သတ္တိများရှိသော သင်္ကေတများပေါ်တွင် မှီခိုနေသည့်အတွက် data ဖြင့်သတ်မှတ်ထားသော စကေးဘားများကို ပုံဖော်ပြသရန်ဖြစ်နိုင်ပါသည်။

**ဥပမာ**- စကေး label များ၏ bold (စာလုံးအထင်း) ဂုဏ်သတ္တိတွင်အသုံးပြုထားသော အောက်ပါ code သည် ဂဏန်းများသည် 500 ၏ ဆတိုးကိန်းဖြစ်သောအခါ ထိုဂဏန်းများကို စာလုံးမည်းဖြင့် ပြသပေးမည်ဖြစ်သည်-


::

   -- returns True (or 1) if the value displayed on the bar
   -- is a multiple of 500

   @scale_value % 500 = 0


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |scaleBar| image:: /static/common/mActionScaleBar.png
   :width: 1.5em
