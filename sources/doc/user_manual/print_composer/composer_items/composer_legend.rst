.. index:: Legend item, Map legend
.. _layout_legend_item:

The Legend Item (မြေပုံရည်ညွှန်းချက် Item)
===========================================

.. only:: html

   .. contents::
      :local:


:guilabel:`Legend` item သည် မြေပုံပေါ်တွင်အသုံးပြုထားသော သင်္ကေတများ၏ အဓိပ္ပာယ်ကိုရှင်းပြသော လေးထောင့်ကွက်တစ်ခု သို့မဟုတ် ဇယားတစ်ခုဖြစ်သည်။ ထို့နောက် legend တစ်ခုကို မြေပုံ item တစ်ခုနှင့် ချိတ်ဆက်ထားမည်ဖြစ်သည်။ :ref:`Item များဖန်တီးခြင်းဆိုင်ရာညွှန်ကြားချက်များ <create_layout_item>` ကိုလိုက်နာ၍ |addLegend| :guilabel:`Add Legend` tool ဖြင့် ရည်ညွှန်းချက် တစ်ခုကိုထည့်သွင်းနိုင်ပြီး ၎င်းကို :ref:`interact_layout_item` ထဲတွင်ဖော်ပြထားသည့်နည်းလမ်းအတိုင်း ကိုင်တွယ်နိုင်မည်ဖြစ်သည်။

Default အားဖြင့် ရရှိနိုင်သော layer အားလုံးကို legend item တွင်ပြသနေမည်ဖြစ်သော်လည်း ၎င်း၏ :guilabel:`Item Properties` panel အားအသုံးပြု၍ ပြသလိုသည့်အရာကိုရွေးချယ်နိုင်သည်။ ဤ feature တွင် :ref:`item များ၏ဘုံ ဂုဏ်သတ္တိများ <item_common_properties>` အပြင်  အောက်ပါလုပ်ဆောင်ချက်များပါရှိသည် (:numref:`figure_layout_legend` ကိုကြည့်ပါ)-


.. showing all layers is a bug (https://issues.qgis.org/issues/13575) but given
   that it's the behavior for a long moment now, let's document it...

.. _figure_layout_legend:

.. figure:: img/legend_properties.png
   :align: center

   ရည်ညွှန်းချက် Item ဂုဏ်သတ္တိများ Panel

Main properties (အဓိကဂုဏ်သတ္တိများ)
------------------------------------

ရည်ညွှန်းချက်အတွက် :guilabel:`Item Properties` panel ၏ :guilabel:`Main properties` အုပ်စုတွင် အောက်ပါလုပ်ဆောင်ချက်များပါဝင်သည် (:numref:`figure_layout_legend_ppt` ကိုကြည့်ပါ )-


.. _figure_layout_legend_ppt:

.. figure:: img/legend_mainproperties.png
   :align: center

   ရည်ညွှန်းချက်၏ အဓိကဂုဏ်သတ္တိများ အုပ်စု

အဓိကဂုဏ်သတ္တိများထဲတွင်-

* မြေပုံရည်ညွှန်းချက်များ၏ :guilabel:`Title` (ခေါင်းစဉ်) ကိုပြောင်းလဲနိုင်သည်။ :ref:`Data-defined override <data_defined>` (Data ဖြင့်သတ်မှတ်ပြီး အစားထိုးလုပ်ဆောင်ခြင်း) setting အားအသုံးပြု၍ ၎င်းကို dynamic (ပြောင်းလဲနိုင်) ဖြစ်အောင်လုပ်ထားနိုင်သည်။ ဥပမာ- atlas တစ်ခုအားဖန်တီးနေချိန်တွင် ထိုသို့ပြုလုပ်ခြင်းသည် အသုံးဝင်ပါသည်။
* လက်ရှိ မြေပုံရည်ညွှန်းချက်မှ ရည်ညွှန်းမည့် :guilabel:`Map` item ကိုရွေးချယ်နိုင်သည်။ Default အားဖြင့် မြေပုံရည်ညွှန်းချက်အား တင်ဆွဲထားသောမြေပုံကိုရွေးချယ်ခြင်းဖြစ်သည်။ မည်သည့်မြေပုံကိုမျှရွေးချယ်မထားလျှင် :ref:`reference map <reference_map>` (ရည်ညွှန်းမြေပုံ) ကိုရယူသုံးစွဲမည်ဖြစ်သည်။
  
  .. note:: Link ချိတ်ဆက်ထားသော မြေပုံ item ၏ :ref:`Variables (ကိန်းရှင်များ) <expression_variables>` (@map_id၊ @map_scale၊ @map_extent...) ကို ရည်ညွှန်းချက်၏ data-defined ဂုဏ်သတ္တိများမှလည်းဝင်ရောက်နိုင်သည်။
   
* သတ်မှတ်ထားသောစာလုံးတွင် မြေပုံရည်ညွှန်းချက်၏စာသားအား wrap (ခြုံငုံ၍မြင်ရနိုင်စေရန် စာကြောင်းများစွာဖြင့်ပြသ) ပြုလုပ်နိုင်သည် - စာလုံးပေါ်လာသည့်အချိန်တိုင်း ၎င်းကို စာကြောင်းအခွဲတစ်ခုဖြင့် အစားထိုးမည်ဖြစ်သည်။
* မြေပုံရည်ညွှန်းချက်ထဲတွင် သင်္ကေတများနှင့်စာသားနေရာချမှုများအား သတ်မှတ်နိုင်ပါသည် - :guilabel:`Arrangement `သည် :guilabel:`Symbols on left` (ဘယ်ဘက်တွင် သင်္ကေတများထားပါ) သို့မဟုတ် :guilabel:`Symbols on right` (ညာဘက်တွင် သင်္ကေတများထားပါ) ဖြစ်နိုင်သည်။ Default တန်ဖိုးသည် အသုံးပြုနေသည့် locale (မူရင်းဒေသ) ပေါ်တွင်မူတည်သည် (ညာမှဘယ်သို့ အခြေခံသော သို့မဟုတ် ဘယ်မှညာသို့ အခြေခံသော)
* မြေပုံရည်ညွှန်းချက်တွင် ပါဝင်သောအကြောင်းအရာများ ဆံ့စေရန် ၎င်း၏ အရွယ်အစားကို အလိုအလျောက်ပြောင်းလဲချိန်ညှိစေလိုပါက |checkbox| :guilabel:`Resize to fit contents` အား အမှန်ခြစ်ပေး၍ အသုံးပြုနိုင်ပါသည်။ အမှန်ခြစ်မပေးခဲ့ပါက မြေပုံရည်ညွှန်းချက်သည် ဘယ်တော့မှ အရွယ်အစားကိုလိုက်ပြောင်းပေးမည်မဟုတ်ဘဲ ၎င်းအစား အသုံးပြုသူမှသတ်မှတ်ခဲ့သော အရွယ်အစားတွင်သာ ရှိနေမည်ဖြစ်သည်။ သတ်မှတ်ထားသော အရွယ်အစားတွင် မဆံ့သမျှအကြောင်းအရာမှန်သမျှကို ဖြတ်ထုတ်လိုက်မည်ဖြစ်သည်။
  

Legend items (မြေပုံရည်ညွှန်းချက်တွင်ပါဝင်သော item များ)
---------------------------------------------------------

ရည်ညွှန်းချက်အတွက် :guilabel:`Item Properties` panel မှ :guilabel:`Legend items` အုပ်စုတ္ငင် အောက်ပါလုပ်ဆောင်ချက်များပါရှိသည် (:numref:`figure_layout_legend_items` ကိုကြည့်ပါ)-

.. _figure_layout_legend_items:

.. figure:: img/legend_items.png
   :align: center

   ရည်ညွှန်းချက် Item များအုပ်စု

* |checkbox| :guilabel:`Auto update` ကိုအမှန်ခြစ်ထားပါက ရည်ညွှန်းချက်ကို အလိုအလျောက် update လုပ်ပေးမည်ဖြစ်သည်။ :guilabel:`Auto update` ကိုအမှန်ခြစ်ဖြုတ်ထားပါက ရည်ညွှန်းချက်ထဲရှိ အရာများကို ပိုမိုထိန်းချုပ်နိုင်စေမည်ဖြစ်ပါသည်။ ရည်ညွှန်းချက် item များစာရင်းအောက်ရှိ icon များအားလုံးသည် အသက်ဝင်လာမည်ဖြစ်သည်။
* ရည်ညွှန်းချက် item များ (Legend items) window တွင် ရည်ညွှန်းချက် item များအားလုံးကို စာရင်းပြုစုထားပြီး item order (အစဉ်) များပြောင်းလဲခြင်း၊ layer များကိုအုပ်စုဖွဲ့ခြင်း ၊ စာရင်းထဲရှိ item များအားဖယ်ရှားခြင်းနှင့်ပြန်လည်ရယူခြင်း၊ layer အမည်များနှင့် သင်္ကေတပုံသဏ္ဍာန်အားပြင်ဆင်ခြင်းနှင့် filter (စစ်ထုတ်မှု) တစ်ခုထည့်သွင်းခြင်းတို့ကိုလုပ်ဆောင်နိုင်သည်။

  * Item order (အစဉ်) ကို  |arrowUp| နှင့် |arrowDown| ခလုတ်များကိုအသုံးပြုခြင်းဖြင့်ဖြစ်စေ 'drag-and-drop' လုပ်ဆောင်ချက်ဖြင့်ဖြစ်စေ ပြောင်းလဲနိုင်သည်။ WMS legend graphic များအတွက် order ကိုပြောင်းလဲ၍ရမည်မဟုတ်ပါ။
  * ရည်ညွှန်းချက်အုပ်စုတစ်ခုကိုထည့်သွင်းရန် |addGroup| ခလုတ်ကိုနှိပ်ပါ။
  * Layer များထည့်ရန် |symbologyAdd| ခလုတ်ကိုအသုံးပြု၍ အုပ်စုများ၊ layer များ သို့မဟုတ်  သင်္ကေတအတန်းအစားများကို ဖယ်ရှားရန် |symbologyRemove| ခလုတ်ကိုအသုံးပြုပါ။
  * |symbologyEdit| ခလုတ်ကိုအသုံးပြု၍ layer ၊ အုပ်စုအမည် သို့မဟုတ် ခေါင်းစဉ်ကို ပြင်ဆင်တည်းဖြတ်နိုင်သည်။ ရည်ညွှန်းချက် item ကို ဦးစွာရွေးချယ်ရန်လိုအပ်သည်။ Item ပေါ်တွင် click နှစ်ချက်နှိပ်ခြင်းဖြင့်လည်း ၎င်းကိုအမည်ပြန်ပေးရန် စာသားအကွက် (text box) တစ်ခုပေါ်လာမည်ဖြစ်သည်။
  * |expression| ခလုတ်ဖြင့် expression များကိုအသုံးပြု၍ရွေးချယ်ထားသော layer ၏ သင်္ကေတအညွှန်း တစ်ခုစီကိုစိတ်ကြိုက်ပြင်ဆင်နိုင်သည် (:ref:`legend_items_data_defined` ကိုကြည့်ပါ)
  * |sum| ခလုတ်သည် vector layer အတန်းအစားတစ်ခုစီအတွက် feature count တစ်ခုကိုထည့်သွင်းပေးသည်။ 
  * |expressionFilter| :sup:`Filter legend by expression` ဖြင့် layer တစ်ခု၏ရည်ညွှန်းချက် item များထဲမှပြသလိုသောတစ်ခုကိုစစ်ထုတ်နိုင်သည်။ ဆိုလိုသည်မှာ မတူညီသော ရည်ညွှန်းချက်များစွာရှိသည့် layer တစ်ခု (ဥပမာ- rule-based သို့မဟုတ် categorized symbology) တွင် boolean expression အားအသုံးပြု၍ အခြေအနေနှင့်မကိုက်ညီသော feature များကို ရည်ညွှန်းချက်ဖွဲ့စည်းပုံမှ ဖယ်ရှားနိုင်သည်။ သတိပြုရန်မှာ ဖယ်ရှားလိုက်သော ထို feature များသည် layout map item ထဲတွင် ဆက်လက်တည်ရှိနေမည်ဖြစ်သည်။

  ရည်ညွှန်းချက် item ၏ မူရင်းအလုပ်လုပ်ပုံသည် :guilabel:`Layers` panel ဖွဲ့စည်းပုံအတိုင်း တူညီသော အုပ်စုများ၊ layer များနှင့် သင်္ကေတအတန်းအစားများကိုပြသခြင်းတို့ပါဝင်သော်လည်း item တစ်ခုခုပေါ်တွင် right-click နှိပ်ခြင်းဖြင့် layer ၏အမည်ကို ဖျောက်ခြင်း သို့မဟုတ် အုပ်စု သို့မဟုတ် အုပ်စုခွဲ အဖြစ် ဖွဲ့စည်းခြင်းတို့ကိုလုပ်ဆောင်နိုင်သည်။ Layer တစ်ခုသို့ ပြောင်းလဲမှုအချို့လုပ်မိပါက မြေပုံရည်ညွှန်းချက် menu မှ :guilabel:`Reset to defaults` ကိုရွေးချယ်၍ မူလအခြေအနေသို့ပြန်လည်ရောက်ရှိအောင်လုပ်နိုင်သည်။


   QGIS main window ထဲတွင်သင်္ကေတပုံစံအားပြောင်းလဲပြီးပါက :guilabel:`Update All` ပေါ်တွင် click နှိပ်၍ print layout တစ်ခုထဲရှိ ရည်ညွှန်းချက်ထဲတွင်ပြောင်းလဲထားသမျှကို update လုပ်နိုင်သည်။
  
  
* :guilabel:`Only show items inside linked maps` ကိုအမှန်ခြစ်ထားပါက ချိတ်ဆက်ထားသောမြေပုံထဲတွင် မြင်ရသည့် item များကိုသာ ရည်ညွှန်းချက်ထဲတွင် စာရင်းလုပ်၍ဖော်ပြမည်ဖြစ်သည်။ မြေပုံမှာတစ်ခုထက်ပို၍ ရှိနေလျှင် :guilabel:`...` ပေါ်တွင် click နှိပ်၍ layout မှ အခြားမြေပုံများကိုရွေးချယ်နိုင်သည်။ |checkbox| :guilabel:`Auto-update` ကိုအမှန်ခြစ်ထားချိန်တွင်လည်း ဤ tool အားအသုံးပြု၍ရနေမည်။ 
* Polygon feature များနှင့် atlas တစ်ခုကိုဖန်တီးနေချိန်တွင် လက်ရှိ atlas feature နှင့်ကိုက်ညီသော ရည်ညွှန်းချက် item များကိုသာပြသစေရန် စစ်ထုတ်နိုင်သည်။ ထိုသို့ပြုလုပ်ရန် |checkbox| :guilabel:`Only show items inside current atlas feature` option အားအမှန်ခြစ်ပါ။
  
.. _legend_items_data_defined:

Data-define the legend labels (Data ဖြင့်သတ်မှတ်ထားသော ရည်ညွှန်းချက်အညွှန်းများ)
.................................................................................

|expression| ကိုသုံး၍ ပေးထားသော layer ၏ သင်္ကေတအညွှန်းတစ်ခုစီအတွက် :ref:`expressions <vector_expressions>` များထည့်သွင်းနိုင်သည်။ Variable အသစ်များ (``@symbol_label`` ၊ ``@symbol_id`` နှင့် ``@symbol_count``) ဖြင့် ရည်ညွှန်းချက်ထဲတွင် အပြန်အလှန်ဆောင်ရွက်နိုင်မည်ဖြစ်သည်။


ဥပမာအားဖြင့်  ``type`` field ဖြင့် အမျိုးအစားခွဲထားသော ``regions`` အမည်ရှိ layer တစ်ခုရှိပါက ရည်ညွှန်းချက်ထဲတွင် အတန်းအစားတစ်ခုစီတွင် ၎င်းတို့ရှိ feature အရေအတွက် နှင့်စုစုပေါင်းဧရိယာတို့ကိုပူးတွဲဖော်ပြထားနိုင်သည်။ ဥပမာ- ``Borough (3) - 850ha`` အတွက်-

#. မြေပုံရည်ညွှန်းချက်ဖွဲ့စည်းပုံထဲရှိ layer entry ကိုရွေးချယ်ပါ
#. |expression| ခလုတ်ကိုနှိပ်၍ :guilabel:`Expression String Builder` dialog ကိုဖွင့်ပါ
#. အောက်ပါ expression ကိုရိုက်ထည့်ပါ (*သင်္ကေတအညွှန်းများကိုတည်းဖြတ်ပြင်ဆင်ခြင်းမပြုရသေးဟုယူဆမည်*)-

::

    format( '%1 (%2) - %3ha',
            @symbol_label,
            @symbol_count,
            round( aggregate(@layer, 'sum', $area, filter:= "type"=@symbol_label)/10000 )
          )

#. :guilabel:`OK` ကိုနှိပ်ပါ


Customizing legend items (ရည်ညွှန်းချက် item များအားစိတ်ကြိုက်ပြင်ဆင်ခြင်း)
............................................................................

.. _figure_layout_legend_item_properties:

.. figure:: img/legend_item_properties.png
   :align: center

:guilabel:`Legend Items Properties` ထဲတွင် ရည်ညွှန်းချက် item များကိုတစ်ခုချင်းစီ စိတ်ကြိုက်ပြင်ဆင်နိုင်သည်။ သို့သော် စိတ်ကြိုက်ပြင်ဆင်ခြင်းအား |checkbox| :guilabel:`Auto update` တွင် အမှန်ခြစ်ဖြုတ်ထားမှသာ ပြုလုပ်နိုင်မည်။

Item တစ်ခုပေါ်တွင် Double-click နှိပ်ခြင်း သို့မဟုတ် |symbologyEdit| :sup:`Edit selected item properties` အားနှိပ်ခြင်းဖြင့် နောက်ထပ် စိတ်ကြိုက်ပြင်ဆင်ခြင်းများပြုလုပ်နိုင်သည်။

:guilabel:`Label (အညွှန်း)`

Item အမျိုးအစားအားလုံးအတွက် အညွှန်းမှစာသား ပြင်ဆင်ပြောင်းလဲလိုလျှင် စာရိုက်ထည့်ခြင်း သို့မဟုတ် |expression| :guilabel:`Insert or Edit an Expression` အားအသုံးပြု၍ expression များထည့်သွင်းခြင်းဖြင့် ပြုလုပ်နိုင်သည်။ [% expression %] သင်္ကေတအားအသုံးပြု၍ Expression များကို item ၏ အညွှန်းထဲရှိ မည်သည့်နေရာ၌ မဆို တိုက်ရိုက်ထည့်သွင်းနိုင်သည်။ 

:guilabel:`Columns (ဇယားတိုင်များ)`

ရည်ညွှန်းချက် Item ဂုဏ်သတ္တိတွင် သီးခြားအရာတစ်ခု သို့မဟုတ် layer တစ်ခုရှိ သင်္ကေတများအားလုံးပြီးမှ ဇယားတိုင်ကိုခွဲထုတ်စေခြင်းဖြင့် ၎င်း၏ အလုပ်လုပ်ပုံကိုထိန်းချုပ်နိုင်သည်။ ဤ widget တွင် layer တစ်ခုချင်းစီအလိုက် layer တစ်ခုနှင့် ၎င်း၏ child (အခွဲ) ကို အလိုအလျောက်ခွဲထုတ်ခြင်းကိုခွင့်ပြုရန် သို့မဟုတ် ပိတ်ဆို့ရန်ရွေးချယ်ခွင့်ရှိသည်။  

:guilabel:`Patch (အကွက်)`

သင်္ကေတတစ်ခုပါဝင်သော item များအတွက် ရည်ညွှန်းချက် Item ဂုဏ်သတ္တိဖြင့် သင်္ကေတတစ်ခုတွင်ရှိနိုင်သည့် အများဆုံး အမြင့်နှင့် အကျယ် ကိုသတ်မှတ်နိုင်သည်။ 

Vector သင်္ကေတများအတွက် သင်္ကေတကို စိတ်ကြိုက် ပုံသဏ္ဍာန်တစ်ခုပြုလုပ်၍သတ်မှတ်ထားနိုင်သည်။ အများအားဖြင့်ပုံသဏ္ဍာန်များကို ရိုးရိုးပြန့် (simple plane) တစ်ခုထဲရှိ ဂျီဩမေတြီကို ကိုယ်စားပြုရန် expression တစ်ခုဖြင့်သတ်မှတ်သည်။ သို့သော် ထိုသင်္ကေတများကို style manager ထဲတွင် သိမ်းထားနိုင်ပြီး နောက်မှ import (ထည့်သွင်း) လုပ်နိုင်မည်ဖြစ်သည်။ ဂျီဩမေတြီအမျိုးအစားတစ်ခုစီအတွက် default သင်္ကေတကို style manager မှတစ်ဆင့် ထိန်းချုပ်နိုင်သည်။

:guilabel:`Custom Symbol (စိတ်ကြိုက်သင်္ကေတ)`

Vector သင်္ကေတများအတွက် သင်္ကေတတစ်ခုကို စိတ်ကြိုက်ပြင်ဆင်သတ်မှတ်နိုင်သည်။ သင်္ကေတတစ်ခုကို စိတ်ကြိုက်ပြင်ဆင်ခြင်းသည် သီးသန့်သင်္ကေတတစ်ခုကို ပုံဖော်ပြသရန်၊ မြေပုံရည်ညွှန်းချက်ထဲတွင် ၎င်းကိုမြင်သာစေရန် သို့မဟုတ် ၎င်း၏သင်္ကေတ အကြိုကြည့်ရှုခြင်း (preview) မှ မှီခိုမှုကင်းသော သင်္ကေတတစ်ခုရရှိရန် အသုံးဝင်နိုင်ပါသည်။ စိတ်ကြိုက်ပြင်ဆင်ထားသောသင်္ကေတသည် မြေပုံရည်ညွှန်းချက်သင်္ကေတကို အစားထိုးသွားမည်ဖြစ်သော်လည်း သတ်မှတ်ထားသည့် သင်္ကေတ :guilabel:`Patch` ကိုဆက်လက်အသုံးပြုမည်ဖြစ်သည်။


Fonts and text formatting (စာလုံးဖောင့်များနှင့် စာသားပုံစံပြင်ဆင်ခြင်း)
-------------------------------------------------------------------------

မြေပုံရည်ညွှန်းချက်အတွက် :guilabel:`Item Properties` panel ၏ :guilabel:`Fonts and text formatting` အုပ်စုတွင် အောက်ပါလုပ်ဆောင်ချက်များပါဝင်သည်-


.. _figure_layout_legend_fonts:

.. figure:: img/legend_fonts.png
   :align: center

   ရည်ညွှန်းချက် စာလုံးဖောင့်များဆိုင်ရာ ဂုဏ်သတ္တိများ

* :ref:`Font selector <font_selector>` (စာလုံးဖောင့်ရွေးချယ်ပေးသည့်အရာ) widget အားအသုံးပြု၍ :ref:`text formatting <text_format>` ၏ လုပ်ဆောင်နိုင်စွမ်းများ (စာလုံးဖောင့် အစိတ်အကျဲ၊ ရောနှောထားသော HTML format ပြင်ဆင်ခြင်း၊ အရောင်ထည့်ခြင်း၊ ရောစပ်ခြင်း၊ နောက်ခံ၊ စာလုံး buffer၊ အရိပ် ...) ကို ထည့်ပေးခြင်းဖြင့် ရည်ညွှန်းချက် item ထဲတွင် ရည်ညွှန်းချက်ခေါင်းစဉ်၊ အုပ်စု၊ အုပ်စုခွဲ၊ နှင့် item (feature) များ၏ စာလုံးဖောင့်များအားပြောင်းလဲနိုင်သည်။
   
* ဤ level များထဲမှတစ်ခုစီအတွက် စာသား :guilabel:`Alignment` (တန်းညှိခြင်း) အား သတ်မှတ်နိုင်သည်- ၎င်းသည် :guilabel:`Left` (ဘယ်မှညာ အခြေခံသည့် locale များအတွက် default)၊ :guilabel:`Center` သို့မဟုတ် :guilabel:`Right` (ညာမှဘယ် အခြေခံသည့် locale များအတွက် default) ဖြစ်နိုင်သည်။
  

Columns (ဇယားတိုင်များ)
------------------------

မြေပုံရည်ညွှန်းချက်အတွက် :guilabel:`Item Properties` panel ၏ :guilabel:`Columns` အုပ်စုအောက်တွင် ရည်ညွှန်းချက် item များကို များစွာသော column များဖြင့် စီစဉ်နိုင်သည်-

* :guilabel:`Count` |selectNumber| field ထဲတွင် column များ၏အရေအတွက်ကို သတ်မှတ်ပါ။ ထိုတန်ဖိုးကို dynamic (ပြောင်းလဲနိုင်သော) လုပ်ထားနိုင်သည်၊ ဥပမာအားဖြင့် atlas feature များ၊ မြေပုံရည်ညွှန်းချက်အကြောင်းအရာများ၊ frame အရွယ်အစား...
* |checkbox| :guilabel:`Equal column widths` သည် မြေပုံရည်ညွှန်းချက် column များကို မည်သို့ ချိန်ညှိသင့်သည်ကို သတ်မှတ်ပေးသည်။
* |checkbox| :guilabel:`Split layers` ဖြင့် column များအကြားတွင် categorized layer legend (အမျိုးအစားခွဲခြားထားသည့် layer ရည်ညွှန်းချက်) တစ်ခု သို့မဟုတ် graduated layer legend (အဆင့်များအလိုက်ခွဲခြားထားသည့် layer ရည်ညွှန်းချက်) တစ်ခုအား ပိုင်းခြားပေးစေပါသည်။
  

.. _figure_layout_legend_columns:

.. figure:: img/legend_columns.png
   :align: center

   ရည်ညွှန်းချက် column setting များ


Symbol (သင်္ကေတ)
-----------------

မြေပုံရည်ညွှန်းချက်အတွက် :guilabel:`Item Properties` panel ၏ :guilabel:`Symbol` အုပ်စုဖြင့် မြေပုံရည်ညွှန်းချက်ရှိ အညွှန်းများ၏ဘေးတွင်ပြသသော သင်္ကေတများ၏ အရွယ်အစားကို ပြင်ဆင်သတ်မှတ်နိုင်သည်။ ၎င်းအုပ်စုတွင် -

* :guilabel:`Symbol width` (သင်္ကေတအကျယ်) နှင့် :guilabel:`Symbol height` (သင်္ကေတအမြင့်) ကိုသတ်မှတ်ထားနိုင်သည်။
* အမှတ်အသားများ၏ :guilabel:`Min symbol size` (အနည်းဆုံးသင်္ကေတအရွယ်အစား) နှင့် :guilabel:`Max symbol size` (အများဆုံးသင်္ကေတအရွယ်အစား) ကို သတ်မှတ်နိုင်ပါသည်- ``0.00mm`` သည် မည်သည့်တန်ဖိုးကိုမျှသတ်မှတ်မထားဟုဆိုလိုခြင်းဖြစ်သည်။
* |checkbox| :guilabel:`Draw stroke for raster symbols`- Raster layer ၏ band (လှိုင်းအလွှာ) အရောင်ကို ကိုယ်စားပြုသည့် သင်္ကေတတွင် outline တစ်ခုထည့်ပေးသည်။ :guilabel:`Stroke color` (အနားသတ်လိုင်းအရောင်) နှင့် :guilabel:`Tickness` (အထူ) နှစ်ခုလုံးကိုသတ်မှတ်နိုင်သည်။

.. _figure_layout_legend_symbol:

.. figure:: img/legend_symbol.png
   :align: center

   ရည်ညွှန်းချက်သင်္ကေတများပြင်ဆင်သတ်မှတ်ခြင်း


WMS LegendGraphic
------------------

ရည်ညွှန်းချက် :guilabel:`Item Properties` panel ၏ :guilabel:`WMS LegendGraphic` အပိုင်းတွင် အောက်ပါလုပ်ဆောင်ချက်များပါရှိသည် (:numref:`figure_layout_legend_wms` ကိုကြည့်ပါ)-

.. _figure_layout_legend_wms:

.. figure:: img/legend_wms.png
   :align: center

   WMS LegendGraphic

WMS layer တစ်ခုကိုထည့်သွင်းပြီး မြေပုံရည်ညွှန်းချက် item တစ်ခုအားထည့်လိုက်သောအခါ WMS မြေပုံရည်ညွှန်းချက်တစ်ခုရရှိရန် WMS server ဆီသို့ တောင်းဆိုမှု တစ်ခုပို့မည်ဖြစ်သည်။ WMS server တွင် GetLegendGraphic လုပ်ဆောင်နိုင်စွမ်း ရှိမှသာ ဤ မြေပုံရည်ညွှန်းချက် အားပြသမည်ဖြစ်သည်။ WMS မြေပုံရည်ညွှန်းချက် အကြောင်းအရာများအား raster ပုံရိပ်တစ်ခုအဖြစ်ပြသလိမ့်မည်ဖြစ်သည်။

WMS မြေပုံရည်ညွှန်းချက် raster ပုံရိပ်၏ :guilabel:`Legend width` (ရည်ညွှန်းချက်အကျယ်) နှင့်  :guilabel:`Legend height` (ရည်ညွှန်းချက်အမြင့်) ကိုချိန်ညှိနိုင်စေရန်အတွက် :guilabel:`WMS LegendGraphic` ကိုအသုံးပြုသည်။


Spacing (စာလုံးအကွာအဝေး)
-------------------------


.. _figure_layout_legend_spacing:

.. figure:: img/legend_spacing.png
   :align: center

:guilabel:`Spacing` အပိုင်းဖြင့် ရည်ညွှန်းချက်အတွင်းရှိ စာလုံးအကွာအဝေး ကိုစိတ်ကြိုက်ပြင်ဆင်နိုင်သည်။ စာလုံးအကွာအဝေးသည် ရည်ညွှန်းချက်အတွင်းရှိ အရာများအား အုပ်စုဖွဲ့ခြင်းနှင့် ၎င်းတို့အကြား ချိတ်ဆက်နေမှုကို ပြသရန်လွန်စွာအသုံးဝင်သည်။

ဤ dialog ဖြင့် ခေါင်းစဉ်တစ်ဝိုက်နှင့် ခေါင်းစဉ် မတိုင်မီ၊ အုပ်စုများ၊ အုပ်စုခွဲများ၊ သင်္ကေတများ၊ အညွှန်းများ၊ လေးထောင့်ကွက်များ၊ တိုင်များနှင့်မျဉ်းများ :guilabel:`Spacing` အား စိတ်ကြိုက်ပြင်ဆင်နိုင်သည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |addGroup| image:: /static/common/mActionAddGroup.png
   :width: 1.5em
.. |addLegend| image:: /static/common/mActionAddLegend.png
   :width: 1.5em
.. |arrowDown| image:: /static/common/mActionArrowDown.png
   :width: 1.5em
.. |arrowUp| image:: /static/common/mActionArrowUp.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |expression| image:: /static/common/mIconExpression.png
   :width: 1.5em
.. |expressionFilter| image:: /static/common/mIconExpressionFilter.png
   :width: 1.5em
.. |selectNumber| image:: /static/common/selectnumber.png
   :width: 2.8em
.. |sum| image:: /static/common/mActionSum.png
   :width: 1.2em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
.. |symbologyEdit| image:: /static/common/symbologyEdit.png
   :width: 1.5em
.. |symbologyRemove| image:: /static/common/symbologyRemove.png
   :width: 1.5em
