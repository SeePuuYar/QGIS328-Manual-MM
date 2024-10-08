﻿.... Purpose: This chapter aims to describe generic tools that can be used even
.. if the user is in another chapter.

.. _general_tools:

********************************************
General Tools (ယေဘုယျ tool များ) 
********************************************

.. only:: html

   .. contents::
          :local:
          :depth: 2


.. _`context_help`:


Context help (မာတိကာအကူအညီ)
============================

.. index::
   single: Context help

QGIS တွင် မိမိလုပ်ဆောင်လိုသော သီးသန့်အကြောင်းအရာတစ်ခုနှင့်ပတ်သက်၍ ပိုမိုသိရှိလိုလျှင် :guilabel:`Help` မှတဆင့် အသုံးပြုသူလမ်းညွှန် (User Manual) ရှိ သက်ဆိုင်ရာစာမျက်နှာတွင် ရှာဖွေနိုင်ပါသည်။ Third-party plugin (QGIS ပြင်ပရှိ plugin) များသည် သက်ဆိုင်ရာဝက်ဘ်ဆိုက်စာမျက်နှာသို့ ရောက်ရှိစေရန် လမ်းညွှန်ပေးပါသည်။

.. index:: Panels

Panels (Panel များ)
====================

ပုံမှန်အားဖြင့် QGIS တွင် လုပ်ငန်းဆောင်တာများ လုပ်ဆောင်နိုင်ရန်အတွက် panels များစွာ ပါရှိရာ ၎င်းတို့အနက် အချို့ panel များကို အောက်တွင် ဖော်ပြထားပြီး အခြား panel များကို ဤအသုံးပြုသူလမ်းညွှန်၏ အခြားနေရာအသီးသီးတွင် ရှာဖွေတွေ့ရှိနိုင်ပါမည်။ QGIS မှ မူလပံ့ပိုးပေးထားသည့် panel များစာရင်းကို  :menuselection:`View --> Panels -->` menu မှတဆင့်ရရှိနိုင်ပြီး :ref:`panels_tools` တွင် ဖော်ပြထားပါသည်။

.. index:: Panels; Layers
.. _`label_legend`:

Layers Panel (Layer များဖော်ပြသည့် panel)
------------------------------------------

.. index::
   single: Legend

:guilabel:`Layers` panel တွင် Project အတွင်း အသုံးပြုနေသော Layer အားလုံးကို တစ်စုတစ်စည်းတည်း တွေ့မြင်နိုင်သောကြောင့် ``map legend`` (မြေပုံရည်ညွှန်းချက်) ဟုလည်း ခေါ်သည်။ ထို Layer panel တွင် မိမိလုပ်ဆောင်နေသော Project တစ်ခုအတွင်း layer များ မြင်ရနိုင်မှုနှင့် မြေပုံ ပုံဖော်ခြင်းများကို စီမံခန့်ခွဲနိုင်ပါသည်။ :kbd:`Ctrl+1` ကို နှိပ်၍ panel ကို ဖော်ပြခြင်း သို့မဟုတ် ဖျောက်ထားခြင်း ပြုလုပ်နိုင်ပါသည်။ 

:guilabel:`Layers` panel ၏ ထိပ်တွင်ရှိသော toolbar တွင် အောက်ပါတို့ကို လုပ်ဆောင်နိုင်ပါသည်- 


* |symbology| :sup:`Open the layer styling dock (F7)` သည် :ref:`Layer Styling (Layer ပုံစံပြင်ဆင်ခြင်း) <layer_styling_panel>` panel ကို အဖွင့်/အပိတ် ပြုလုပ်နိုင်ပါသည်။ 
* |addGroup| :sup:`Add new group` (အုပ်စုအသစ်ဖွဲ့ခြင်း) ၏အသုံးပြုပုံကို :ref:`group_layers_interact` တွင် ကြည့်ရှုပါ။
* |showPresets| :sup:`Manage Map Themes` (မြေပုံအကြောင်းအရာကိုစီမံခန့်ခွဲခြင်း) ကိုအသုံးပြု၍ layer များ၏ မြင်ရနိုင်မှုကို ချိန်ညှိနိုင်သကဲ့သို့ :ref:`map themes (မြေပုံအကြောင်းအရာ) <map_themes>` အမျိုးမျိုးဖြင့် layer များကို စီမံဆောင်ရွက်နိုင်သည်။
* |filterMap| ကို အသုံးပြု၍ Legend tree (ရည်ညွှန်းချက်ဖွဲ့စည်းပုံ) တွင် ထည့်သွင်းဖော်ပြလိုသော Layer များကို စစ်ထုတ်နိုင်သည်-

  * :guilabel:`Filter Legend by Map Content` (မြေပုံအကြောင်းအရာဖြင့် ရည်ညွှန်းချက်ကို စစ်ထုတ်ခြင်း) -  လက်ရှိမြေပုံမျက်နှာပြင်တွင် မြင်ရနိုင်ပြီး မြေပုံမျက်နှာပြင်အတွင်း ဖြတ်နေသော feature များရှိသည့် layer များကိုသာ layer panel ထဲတွင် ၎င်းတို့၏ style ဖြင့် ပုံဖော်ပြသမည်ဖြစ်သည်။ ထိုသို့မဟုတ်ပါက Layer တွင် ယေဘုယျအမည်ဖြစ်သော Null သင်္ကေတသာ ပေါ်နေမည်ဖြစ်သည်။ Layer ၏ symbology ကို အခြေခံ၍ မည်သည့် layer များမှ မည်သို့သော feature အမျိုးအစားများသည် မိမိစိတ်ဝင်စားသော ဧရိယာကို လွှမ်းခြုံသည်ကို အလွယ်တကူခွဲခြားသိနိုင်ပါသည်။ 
  * :guilabel:`Show Private Layers` (သီးသန့် Layer များကို ပြသခြင်း) သည် Project setting တွင် ပြုပြင်မွမ်းမံခြင်းမပြုလုပ်ပဲ :guilabel:`Layers` panel ထဲတွင် :ref:`private layers <project_layer_capabilities>` (သီးသန့် Layer) များကို ပြသရန်နှင့် အပြန်အလှန်ဆောင်ရွက်ရန် အဆင်ပြေစေသော ဖြတ်လမ်းနည်းတစ်ခုဖြစ်ပါသည်။
* |expressionFilter| :sup:`Filter Legend by Expression` (ခိုင်းစေချက်ဖြင့်စစ်ထုတ်ခြင်း) - အခြေအနေနှင့်ကိုက်ညီမှုမရှိသည့် feature များ၏ style များကို ရွေးချယ်ထားသော layer tree မှ ဖယ်ရှားရန် |expressionFilter| :sup:`Filter Legend by Expression` မှတဆင့် expression (ခိုင်းစေချက်) ရေး၍ လုပ်ဆောင်နိုင်သည်။ ၎င်းကို အခြား Layer ၏ ဧရိယာ/feature အတွင်းရှိ မိမိဖော်ပြလိုသော feature ကို မြင်သာစေရန်အတွက်လည်း အသုံးပြုနိုင်သည်။ အောက်သို့ ဆွဲချနိုင်သောစာရင်း (Drop-down list) မှ လက်ရှိအသုံးပြုထားသော expression ကို တည်းဖြတ်ပြင်ဆင်ခြင်း၊ ဖျက်ခြင်း ပြုလုပ်နိုင်သည်။
* Layer panel အတွင်းရှိ Layer များနှင့် Layer အုပ်စုများကို အကျယ်ဖြန့်ကြည့်ရန် |expandTree| :sup:`Expand All` ကို အသုံးပြုနိုင်သည် သို့မဟုတ် ပြန်စုစည်းရန် |collapseTree| :sup:`Collapse All` ကို အသုံးပြုနိုင်သည်။
* လက်ရှိရွေးချယ်ထားသော Layer/Group များအား ပယ်ဖျက်လိုပါက |removeLayer| :sup:`Remove Layer/Group` ကို အသုံးပြု၍ ဖယ်ရှားနိုင်သည်။ 

.. _figure_layer_toolbar:

.. figure:: img/layer_toolbar.png
   :align: center 

   Layer panel ရှိ layer toolbar

.. note::
   Layer panel တွင် အသုံးပြုသော tool များသည် မြေပုံထုတ်ရန်ပြင်ဆင်သည့်နေရာ (print layouts) ထဲရှိ မြေပုံနှင့် ရည်ညွှန်းချက်များကို ပြင်ဆင်ရာတွင်လည်း အသုံးပြုနိုင်သည်။


.. index:: Map themes
.. _map_themes:

Configuring map themes (မြေပုံ၏အကြောင်းအရာများကို ပြင်ဆင်သတ်မှတ်ခြင်း)
.......................................................................

|showPresets| :sup:`Manage Map Themes` (မြေပုံအကြောင်းအရာများကို စီမံခန့်ခွဲခြင်း) ၏ drop-down ခလုတ်တွင် :guilabel:`Layers` Panel ထဲရှိ Layer များ၏ မြင်ရနိုင်မှု (visibility) ကို ကိုင်တွယ်နိုင်ရန်အတွက် ဖြတ်လမ်းနည်းများ ပါရှိပါသည်။

* |showAllLayers| :guilabel:`Show All Layers` (Layer အားလုံးပြသခြင်း)
* |hideAllLayers| :guilabel:`Hide All Layers` (Layer အားလုံးဖုံးကွယ်ထားခြင်း)
* |showSelectedLayers| :guilabel:`Show Selected Layers` (ရွေးချယ်ထားသည့် Layer များကို ပြသခြင်း)
* |hideSelectedLayers| :guilabel:`Hide Selected Layers` (ရွေးချယ်ထားသည့် Layer များကို ဖုံးကွယ်ထားခြင်း)
* |toggleSelectedLayers| :guilabel:`Toggle Selected Layers` (ရွေးချယ်ထားသည့် Layer များကို အဖွင့်အပိတ်ပြုလုပ်ခြင်း) - ပထမဦးဆုံးရွေးချယ်ထားသော Layer ၏ visibility (မြင်ရနိုင်မှု) ကို ပြောင်းလဲ၍ ထိုမြင်နိုင်သည့်ပုံစံအတိုင်း အခြား ရွေးချယ်ထားသော Layer များတွင် အသုံးပြုနိုင်ပြီး ဖြတ်လမ်းနည်းအနေဖြင့် :kbd:`Space` ကို အသုံးပြုနိုင်သည်။
* :guilabel:`Toggle Selected Layers Independently` (ရွေးချယ်ထားသည့် Layer များကို သီးသန့်အဖွင့်အပိတ်ပြုလုပ်ခြင်း) - ဤ tool ကို ရွေးချယ်ထားသော Layer တစ်ခုချင်းစီ၏ မြင်နိုင်သည့်ပုံစံကိုပြောင်းလဲရာတွင် အသုံးပြုနိုင်သည်။
* |hideDeselectedLayers| :guilabel:`Hide Deselected Layers` (ရွေးချယ်မှုမပြုလုပ်ထားသည့် Layer များကို ဖုံးကွယ်ထားခြင်း)

Layer ၏ မြင်ရနိုင်မှုကို ရိုးရှင်းစွာထိန်းချုပ်ခြင်းအပြင် |showPresets| :sup:`Manage Map Themes` menu သည် ရည်ညွှန်းချက်ရှိ **Map Themes** (မြေပုံအကြောင်းအရာ)များကို ပြင်ဆင်နိုင်ပြီး map theme တစ်ခုမှ တစ်ခုသို့ ပြောင်းလဲရန် ကူညီပေးပါသည်။ Map theme ဆိုသည်မှာ အောက်တွင် ဖော်ပြထားသော မှတ်တမ်းများပါဝင်သည့် လက်ရှိအသုံးပြုနေသော မြေပုံရည်ညွှန်းချက်၏ ပုံရိပ်(snapshot) တစ်ခုဖြစ်ပါသည်-

* :guilabel:`Layers` panel ထဲတွင် မြင်နိုင်စေရန် သတ်မှတ်ထားသော Layer များ
* **နှင့်** မြင်နိုင်သည့် Layer တစ်ခုချင်းစီအတွက်-

  * Layer တွင်အသုံးပြုထားသည့် :ref:`style <save_layer_property>` ၏ အကိုးအကား
  * :guilabel:`Layers panel` တွင် အမှန်ခြစ်ပြုလုပ်ထားသည့် Layer ရှိ style ၏မြင်နိုင်သော အတန်းအစားများဖြစ်သည်။ ၎င်းကို သင်္ကေတတစ်ခုအတွက် ပုံဖော်ပြသခြင်းမျိုးမဟုတ်ဘဲ :ref:`symbologies (သင်္ကေတဆိုင်ရာများ) <vector_style_menu>` တွင် အသုံးပြုသွားမည်ဖြစ်သည်။
  * မြေပုံတွင်ပါဝင်သည့် Layer နှင့် Layer အုပ်စုများ၏ အကျယ်ဖြန့်/စုစည်း ထားသည့် အခြေအနေ

Map theme တစ်ခု ဖန်တီးနိုင်ရန် -

#. မိမိဖော်ပြချင်သည့် Layer တစ်ခုကိုအမှန်ခြစ်ပါ။ 
#. ပုံမှန်အသုံးပြုနေကျအတိုင်း Layer properties (Layer ၏ဂုဏ်သတ္တိများ)(သင်္ကေတ၊ ရုပ်ပုံများ၊ အညွှန်းများ စသည်ဖြင့်) ကို ပြင်ဆင်သတ်မှတ်ပါ။
#. Project အောက်ခြေရှိ :menuselection:`Style -->` menu ကို အကျယ်ဖြန့်၍ :ref:`project အတွင်းထည့်သွင်းထားသော style အသစ်တစ်ခု <manage_custom_style>` အဖြစ် setting တွင် သိမ်းဆည်းရန် :guilabel:`Add...` ကို နှိပ်ပါ။ 

   .. note:: Map theme တစ်ခုသည် project ၏ properties အသေးစိတ်အချက်အလက်များကို မှတ်သားထားမည်မဟုတ်ပါ။ Style နာမည်အတွက် အကိုးအကားတစ်ခုကိုသာလျှင် သိမ်းထားမည်ဖြစ်ပြီး ထို style ကို အသုံးပြုနေစဉ် Layer ကို သင်္ကေတ၊ အရောင်စသဖြင့် ပြောင်းလဲမှုများပြုလုပ်တိုင်း (ဥပမာ- symbology ဆိုင်ရာပုံဖော်ပြသခြင်းကို ပြောင်းလဲခြင်း) အချက်အလက်အသစ်များနှင့်အတူ map theme တွင် သိမ်းဆည်းသွားမည်ဖြစ်သည်။

#. အခြား Layer များအတွက်လည်း ယခုပြုလုပ်ခဲ့သည့်အဆင့်များအတိုင်း လိုအပ်သလို ထပ်မံလုပ်ဆောင်ပါ။
#. လိုအပ်ပါက :guilabel:`Layers` panel ရှိ မြင်ရနိုင်သော Layer များနှင့် Layer အုပ်စုများကို အကျယ်ဖြန့်ခြင်း သို့မဟုတ် ပြန်လည်စုစည်းခြင်းများကို လုပ်ဆောင်ပါ။
#. Panel ထိပ်ရှိ |showPresets| :sup:`Manage Map Themes` ကိုနှိပ်၍ :guilabel:`Add Theme...` သို့ ဝင်ပါ။
#. Map theme ၏ အမည်ကို ရေးသား၍ :guilabel:`OK` ကို နှိပ်ပါ။

|showPresets| ၏ drop-down menu အောက်ခြေတွင် theme အသစ်ကို တွေ့မြင်ရမည် ဖြစ်သည်။

မြေပုံရည်ညွှန်းချက်ထဲရှိ လက်ရှိပေါင်းစပ်မှုများသည် အထက်တွင်သတ်မှတ်ထားသည့်အတိုင်း ရှိပြီးသား map theme အကြောင်းအရာများ တစ်ခုခုနှင့်ကိုက်ညီမှုမရှိလျှင် map theme အသစ်တစ်ခုကို ဖန်တီးရန် :guilabel:`Add Theme...` နှိပ်၍ သော်လည်းကောင်း၊ :menuselection:`Replace Theme -->` ကိုနှိပ်၍သော်လည်းကောင်း update ပြုလုပ်နိုင်ပြီး map themes များကို မိမိလိုအပ်သလောက် ဖန်တီးနိုင်ပါသည်။ ထို့အပြင် လက်ရှိအသုံးပြုနေသော map theme ကို အမည်ပြောင်းလိုလျှင် :guilabel:`Rename Current Theme...` မှတဆင့် ပြောင်းနိုင်ပြီး map theme အား ဖျက်လိုပါက :guilabel:`Remove Current Theme` ကိုသုံး၍ ဖယ်ရှားနိုင်ပါသည်။

Map themes များသည် မတူညီသော ကြိုတင်ပြင်ဆင်သတ်မှတ်ထားသည့် ပေါင်းစပ်မှုများအကြား မြန်ဆန်စွာ ပြောင်းလဲပေးနိုင်ပါသည်- စာရင်းထဲရှိ map theme တစ်ခုကို ရွေးချယ်ခြင်းဖြင့် ၎င်း၏ ပေါင်းစပ်မှုကို ပြန်လည်ရယူနိုင်ပါသည်။ ပြင်ဆင်သတ်မှတ်ထားပြီးသော Map themes များအားလုံးကို ပုံထုတ်ရန်ပြင်ဆင်သည့်အနေအထား (print layout) တွင်လည်း အသုံးပြုနိုင်သောကြောင့် လက်ရှိ မြေပုံ canvas ပုံဖော်ပြသခြင်းကို မမှီခိုပဲ သီးသန့်မြေပုံအကြောင်းအရာများပေါ်အခြေခံပြီး မတူညီသော မြေပုံ item များကို ဖန်တီးနိုင်ပါသည်။ (:ref:`Map item layers <layout_layers>` တွင် ကြည့်ရှုပါ)

Overview of the context menu of the Layers panel (Layer panel ရှိ context menu ကိုခြုံငုံလေ့လာခြင်း)
.....................................................................................................

Toolbar ၏ အောက်ခြေရှိ Layers panel ၏ အဓိကအပိုင်းသည် project အတွင်း ထည့်သွင်းထားသော Layer အားလုံးကို တစ်ခုချင်း သို့မဟုတ် အုပ်စုလိုက်ပြုလုပ်၍ ဖော်ပြထားသော frame ဖြစ်သည်။ :ref:`scale-based visibility <label_scaledepend>` (စကေးပေါ်မူတည်သော မြင်ရနိုင်မှု) ကို မသတ်မှတ်ထားလျှင် checked box (အမှန်ခြစ်ပြုလုပ်နိုင်သောလေးထောင့်ကွက်) တစ်ခုဘေးတွင်ပါရှိသော Layer တစ်ခုသည် မြေပုံမျက်နှာပြင်အကျယ်အဝန်းနှင့်ထပ်နေသော ၎င်း layer ၏ အကြောင်းအရာများကို ပြသပေးမည်ဖြစ်သည်။ Layer တစ်ခုကို ရည်ညွှန်းချက်ထဲတွင် အထက် သို့‌မဟုတ် အောက်သို့ ဖိဆွဲ၍ ရွေ့ကာ Z-ordering ကို ပြောင်းလဲနိုင်ပါသည်။ Z-ordering ဆိုသည်မှာ ရည်ညွှန်းချက်၏ ထိပ်ပိုင်းနှင့် ပိုနီးသော layer များကို အပေါ်ဆုံးမှထား၍ အစဉ်လိုက်စီသွားခြင်းဖြစ်ပါသည်။ Layer တစ်ခု သို့မဟုတ် Layer များအစု တစ်ခုကိုလည်း များစွာသော QGIS instances များကိုဖြတ်၍ ဖိဆွဲနိုင်ပါသည်။

.. note:: 
   Z-ordering ကို :ref:`Layer Order (Layer အစဉ်) <layer_order>` panel မှတဆင့် အထက်အောက်အစီအစဉ်ကို ရွှေ့ပြောင်းနိုင်သည်။ 


Panel ထဲတွင်ရွေးချယ်ထားသော item ပေါ်မူတည်၍ ထို item အား right-click နှိပ်ခြင်းအားဖြင့် ဆောင်ရွက်နိုင်သည့် လုပ်ဆောင်ချက်အမျိုးမျိုးကို အောက်ပါအတိုင်း ပြသနေမည်ဖြစ်သည်။


.. table updated with https://tableconvert.com/excel-to-restructuredtext

.. list-table:: :guilabel:`Layers` panel item များမှ Contextual menu များ
   :header-rows: 1
   :widths: 75 15 15 15 15 15
   :class: longtable

   * - Option (ရွေးချယ်စရာ)
     - Group
     - Vector Layer
     - Raster Layer
     - Mesh Layer
     - Point Cloud Layer
   * - |zoomToLayer| :guilabel:`Zoom to Layer(s)/Group` (Layer များ/အုပ်စု သို့ zoom ချဲ့ခြင်း)
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - |zoomToLayer| :guilabel:`Zoom to Selection` (ရွေးချယ်ထားသည်များသို့ zoom ချဲ့ခြင်း)
     - 
     - |checkbox|
     -
     -
     -
   * - |inOverview| :guilabel:`Show in Overview` (Overview ထဲတွင် ပြသခြင်း)
     - 
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Show Feature Count` (Feature အရေအတွက်ကို ပြသခြင်း)
     - 
     - |checkbox|
     -
     -
     -
   * - |labelingSingle| :guilabel:`Show Label` (အညွှန်းကို ပြသခြင်း)
     -
     - |checkbox|
     -
     -
     -
   * - :guilabel:`Copy Layer/Group` (Layer/အုပ်စု ကို ကူးယူခြင်း)
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Rename Layer/Group` (Layer/အုပ်စု ကို အမည်ပြောင်းခြင်း)
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - |zoomActual| :guilabel:`Zoom to Native Resolution (100%)` (မူရင်း ကြည်လင်ပြတ်သားမှု (100%) သို့ zoom ချဲ့ခြင်း)
     -
     -
     - |checkbox|
     -
     -
   * - :guilabel:`Stretch Using Current Extent` (လက်ရှိ extent ကိုအသုံးပြု၍ ဆန့်ကားခြင်း)
     -
     -
     - |checkbox|
     -
     -
   * - |dbManager| :guilabel:`Update SQL Layer...` (SQL Layer ကို update လုပ်ခြင်း)
     -
     - |checkbox|
     -
     -
     -
   * - |addVirtualLayer| :guilabel:`Edit Virtual Layer...` (Virtual Layer ကို တည်းဖြတ်ပြင်ဆင်ခြင်း)
     -
     - |checkbox|
     -
     -
     -
   * - |addGroup| :guilabel:`Add Group` (အုပ်စုပေါင်းထည့်ခြင်း)
     - |checkbox|
     -
     -
     -
     -
   * - |duplicateLayer| :guilabel:`Duplicate Layer` (Layer ကို ပုံတူပွားခြင်း)
     -
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - |removeLayer| :guilabel:`Remove Layer/Group...` (Layer/အုပ်စု ကိုဖယ်ရှားခြင်း)
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Move Out of Group` (အုပ်စု၏အပြင်သို့ရွှေ့ခြင်း)
     - 
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Move to Top` (အပေါ်သို့ရွှေ့ခြင်း)
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Move to Bottom` (အောက်သို့ရွှေ့ခြင်း)
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Check and all its Parents` (၎င်း၏ Parent များအားလုံးကို အမှန်ခြစ်ခြင်း)
     -
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Group Selected` (ရွေးချယ်ထားသည်များကို အုပ်စုဖွဲ့ခြင်း)
     -
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - |openTable| :guilabel:`Open Attribute Table` (အချက်အလက်ဇယားကို ဖွင့်ခြင်း)
     -
     - |checkbox|
     -
     -
     -
   * - |toggleEditing| :guilabel:`Toggle Editing` (Editing ကို အဖွင့်အပိတ်လုပ်ခြင်း)
     -
     - |checkbox|
     -
     - |checkbox|
     -
   * - |allEdits| :menuselection:`Current Edits -->` (လက်ရှိ ပြင်ဆင်တည်းဖြတ်မှုများ)
     -
     - |checkbox|
     -
     - |checkbox|
     -
   * - :guilabel:`Filter...` (စစ်ထုတ်ခြင်း)
     -
     - |checkbox|
     - |checkbox|
     -
     - |checkbox|
   * - :guilabel:`Change Data Source...` (Data ရင်းမြစ်ကို ပြောင်းလဲခြင်း)
     -
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Repair Data Source...` (Data ရင်းမြစ်ကို ပြုပြင်ခြင်း)
     -
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :menuselection:`Actions on selections -->` (ပြင်ဆင်တည်းဖြတ်ခြင်း mode တွင်)
     -
     - |checkbox|
     -
     -
     -
   * - :menuselection:`--> Duplicate Feature` (Feature ကိုပုံတူပွားခြင်း)
     -
     - |checkbox|
     -
     -
     -
   * - :menuselection:`--> Duplicate Feature and Digitize` (Feature ကိုပုံတူပွားပြီး digitize လုပ်ခြင်း)
     -
     - |checkbox|
     -
     -
     -
   * - :guilabel:`Set Layer Scale Visibility...` (Layer စကေး မြင်ရနိုင်မှုကို သတ်မှတ်ခြင်း)
     -
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Zoom to Visible Scale` (မြင်ရနိုင်သော စကေးသို့ zoom ချဲ့ခြင်း)
     -
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :menuselection:`Layer CRS -->` (Layer ၏ CRS)
     -
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :menuselection:`--> Set Project CRS from Layer` (Project CRS ကို Layer မှ သတ်မှတ်ခြင်း)
     -
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :menuselection:`--> Set to..` (လတ်တလောအသုံးပြုခဲ့သော CRS များ)
     -
     -
     -
     - |checkbox|
     - |checkbox|
   * - :menuselection:`--> Set Layer CRS...` (Layer CRS ကိုသတ်မှတ်ခြင်း)
     -
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :menuselection:`Set Group CRS...` (အုပ်စု CRS ကိုသတ်မှတ်ခြင်း)
     - |checkbox|
     -
     -
     -
     -
   * - :guilabel:`Set Group WMS Data...` (အုပ်စု WMS Data ကိုသတ်မှတ်ခြင်း)
     - |checkbox|
     -
     -
     -
     -
   * - |unchecked| :guilabel:`Mutually Exclusive Group` (အပြန်အလှန်ဖြစ်စွာ မပါဝင်သော အုပ်စု)
     - |checkbox|
     -
     -
     -
     -
   * - :guilabel:`Check and all its children (Ctrl-click)`
     - |checkbox|
     -
     -
     -
     -
   * - :guilabel:`Uncheck and all its children (Ctrl-click)`
     - |checkbox|
     -
     -
     -
     -
   * - :guilabel:`Make Permanent` (အမြဲတမ်းအဖြစ် ပြုလုပ်ခြင်း)
     -
     - |checkbox|
     -
     -
     -
   * - :menuselection:`Export -->` (ထုတ်ယူခြင်း)
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :menuselection:`--> Save As...` (...အနေဖြင့် သိမ်းဆည်းခြင်း)
     -
     -
     - |checkbox|
     -
     -
   * - :menuselection:`--> Save Features As...` (Feature များကို.... အနေဖြင့် သိမ်းဆည်းခြင်း)
     -
     - |checkbox|
     -
     -
     -
   * - :menuselection:`--> Save Selected Features As...` (ရွေးချယ်ထားသော Feature များကို.... အနေဖြင့် သိမ်းဆည်းခြင်း)
     -
     - |checkbox|
     -
     -
     -
   * - :menuselection:`--> Save As Layer Definition File...` (Layer Definition ဖိုင်အနေဖြင့် သိမ်းဆည်းခြင်း)
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :menuselection:`--> Save As QGIS Layer Style File...` (QGIS Layer style ဖိုင်အနေဖြင့် သိမ်းဆည်းခြင်း)
     -
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :menuselection:`Styles -->`
     -
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :menuselection:`--> Copy Style` (Style ကို ကူးယူခြင်း)       
     -
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :menuselection:`--> Paste Style` (ကူးယူထားသော Style ကို နေရာချခြင်း)
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :menuselection:`--> Add...` (ပေါင်းထည့်ခြင်း)
     -
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :menuselection:`--> Rename Current...` (လက်ရှိအရာကို အမည်ပြောင်းခြင်း)
     -
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :menuselection:`--> Edit symbol...` (သင်္ကေတကို တည်းဖြတ်ပြင်ဆင်ခြင်း)
     -
     - |checkbox|
     -
     -
     -
   * - :menuselection:`--> Copy Symbol` (သင်္ကေတကို ကူးယူခြင်း)
     -
     - |checkbox|
     -
     -
     -
   * - :menuselection:`--> Paste Symbol` (ကူးယူထားသော သင်္ကေတကို နေရာချခြင်း)
     -
     - |checkbox|
     -
     -
     -
   * - :guilabel:`Add Layer Notes...` (Layer မှတ်စုများ ပေါင်းထည့်ခြင်း)
     -
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Edit Layer Notes...` (Layer မှတ်စုများကို တည်းဖြတ်ပြင်ဆင်ခြင်း)
     -
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Remove Layer Notes` (Layer မှတ်စုများကို ဖယ်ရှားခြင်း)
     -
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Properties...` (ဂုဏ်သတ္တိများ)
     -
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|    

GRASS vector layer များအတွက် |toggleEditing| :sup:`Toggle editing` (‌တည်းဖြတ်ပြင်ဆင်ခြင်းကို အဖွင့်အပိတ်လုပ်ခြင်း) ကို အသုံးပြုနိုင်မည်မဟုတ်ပေ။ ထို Layer များကို တည်းဖြတ်ပြင်ဆင်ခြင်းနှင့် ပတ်သက်သည့် အချက်အလက်များသိရှိလိုပါက :ref:`grass_digitizing` အပိုင်းတွင် အသေးစိတ်ကြည့်ရှုနိုင်ပါသည်။ 


.. index:: Group, Layer
.. _group_layers_interact:


Interact with groups and layers (Group များနှင့် layer များဖြင့် အပြန်အလှန်ဆက်သွယ်လုပ်ဆောင်ခြင်း)
..................................................................................................
 
Legend (ရည်ညွှန်းချက်) window ထဲရှိ Layer များကို အောက်တွင်ဖော်ပြထားသော နည်းလမ်းအမျိုးမျိုးဖြင့် အုပ်စုများ အဖြစ်သို့ စီစဉ်ဖွဲ့စည်းနိုင်ပါသည်-

#. အုပ်စုအသစ်တစ်ခု ထည့်ရန် |folder| icon ကို နှိပ်ပါ။ ထို့နောက် အုပ်စုအတွက်အမည်ပေး၍ :kbd:`Enter` ကိုနှိပ်ပါ။ ထို့နောက် ရှိပြီးသား Layer ကို ဖိဆွဲ၍ အုပ်စုထဲသို့ ထည့်ပါ။ 
#. တစ်ခုထက်ပိုသော Layer များကို ရွေးချယ်၍ |folder| ကို နှိပ်လျှင် ရွေးချယ်ထားသော Layer များသည် အုပ်စုအသစ်တစ်ခုအဖြစ် အလိုအလျောက် ဖွဲ့စည်းသွားမည်ဖြစ်သည်။ 
#. Layer အချို့ကို ရွေးချယ်၍ legend window တွင် right-click နှိပ်ပြီး :guilabel:`Group Selected` ကို ရွေးချယ်ပါက ရွေးချယ်ထားသော Layer များသည် အုပ်စုအသစ်တစ်ခုထဲသို့ အလိုအလျောက် ရောက်ရှိသွားမည်ဖြစ်သည်။

Layer တစ်ခုကို အုပ်စုတစ်ခုမှ ပြန်ထုတ်လိုလျှင် Layer ကို ဖိဆွဲ၍ ထုတ်နိုင်ပါသည် သို့မဟုတ် Layer အား right-click နှိပ်၍ :guilabel:`Move Out of Group`  (အုပ်စုမှဖယ်ထုတ်ခြင်း) ကို ရွေးချယ်နိုင်သည်။ ထိုအခါ Layer သည် အုပ်စုမှ ထွက်၍ အုပ်စု၏ အပေါ်ဘက်တွင် ရောက်ရှိနေမည်ဖြစ်သည်။ ထို့အပြင် အခြားအုပ်စုများထဲသို့ အုပ်စုများကိုလည်း ထပ်မံစုစည်းနိုင်သည်။ Layer တစ်ခုသည် အုပ်စုများ စုစည်းထားသော အုပ်စု (nested group) အတွင်းရှိနေလျှင် :guilabel:`Move Out of Group` ကို အသုံးပြုလိုက်ပါက ထို Layer သည် nested group အားလုံး၏ ထိပ်တွင် ရောက်ရှိနေပါလိမ့်မည်။

အုပ်စုတစ်ခု သို့မဟုတ် Layer တစ်ခုကို Layer panel ၏ ထိပ်သို့ ရွှေ့ပြောင်းလိုလျှင် ထိပ်ပိုင်းသို့ ဖိဆွဲ၍ဖြစ်စေ :guilabel:`Move to Top` (ထိပ်ဆုံးသို့ ရွှေ့ခြင်း) ကို အသုံးပြု၍ဖြစ်စေ လုပ်ဆောင်နိုင်သည်။ Nested group တစ်ခုထဲရှိ Layer တစ်ခုကို အဆိုပါနည်းလမ်းအတိုင်း ရွှေ့ပြောင်းပါက ထို Layer သည် လက်ရှိရှိနေသော nested group ၏ ထိပ်ဆုံးသို့ ရောက်ရှိသွားမည်ဖြစ်သည်။ ထို့အပြင်  :guilabel:`Move to Bottom` (အောက်သို့ရွှေ့ခြင်း) option သည် :guilabel:`Move to Top` သဘောတရားနည်းတူ layer နှင့် အုပ်စုများကို အောက်သို့ ရွှေ့ပြောင်းရန် ဖြစ်ပါသည်။ 

အုပ်စု၏ checkbox (အမှန်ခြစ်ပြုလုပ်နိုင်သော လေးထောင့်ကွက်) ကို click တစ်ချက်နှိပ်ရုံဖြင့် အုပ်စုတွင်ရှိသော Layer များကို ပြသရန် သို့မဟုတ် ဖျောက်ထားရန် လုပ်ဆောင်နိုင်သည်။ နောက်တစ်နည်းအားဖြင့် :kbd:`Ctrl` နှိပ်၍လည်း အုပ်စုနှင့်အုပ်စုခွဲများရှိ Layer များအားလုံးကို  အဖွင့်အပိတ်ပြုလုပ်နိုင်သည်။

အမှန်ခြစ်ထားသော layer ပေါ်တွင် :kbd:`Ctrl` - click နှိပ်လျှင် layer နှင့်၎င်း၏ parent layer များအားလုံးတွင် အမှန်ခြစ်ဖျောက်သွားမည်ဖြစ်ပြီး အမှန်ခြစ်မခြစ်ထားသော layer ပေါ်တွင် :kbd:`Ctrl` - click နှိပ်လျှင် layer နှင့်၎င်း၏ parent layer များအားလုံးကို အမှန်ခြစ်ခြစ်ပေးမည်ဖြစ်သည်။

**Mutually Exclusive Group** option သည် မြင်ရနိုင်သော layer တစ်ခုတည်းသာရှိသော အုပ်စုတစ်ခုကို တစ်ချိန်တည်းတွင်ဖန်တီးနိုင်သည်။ အုပ်စုထဲရှိ Layer တစ်ခုကို မြင်နိုင်အောင် သတ်မှတ်လိုက်တိုင်း အခြား Layer များကို မြင်ရနိုင်တော့မည်မဟုတ်ပါ။

တစ်ခုထက်ပိုသော Layer သို့မဟုတ် အုပ်စုများကို :kbd:`Ctrl` key နှိပ်၍ ရွေးချယ်နိုင်ပြီး အုပ်စု အသစ်တစ်ခုထဲသို့ တပြိုင်နက်တည်း ရွေ့ပြောင်းနိုင်သည်။

တစ်ခုထက်ပိုသော Layer သို့မဟုတ် အုပ်စုများကို တပြိုင်နက်တည်း ဖျက်လိုပါက :kbd:`Ctrl` key ကို နှိပ်၍ရွေးချယ်ပြီး :kbd:`Ctrl+D` ကိုနှိပ်ကာ ရွေးချယ်ထားသည့် Layer များအားလုံးကို layer များစာရင်းမှ ဖယ်ရှားနိုင်သည်။


More information on layers and groups using indicator icon (ညွှန်ပြ icon များကို အသုံးပြု၍ Layer များနှင့် အုပ်စုများ၏ အချက်အလက်များ ပိုမိုသိရှိစေခြင်း)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

အချို့အခြေအနေများတွင် :guilabel:`Layers` panel ထဲရှိ Layer သို့မဟုတ် အုပ်စုတို့၏ဘေးရှိ icon များသည် ထို Layer နှင့်အုပ်စုများနှင့်ပတ်သက်သည့် အချက်အလက်များကို ပိုမိုသိရှိစေရန် အသုံးပြုနိုင်သည်။
ထိုအရာများမှာ အောက်ပါအတိုင်းဖြစ်သည်-


* |toggleEditing| သည် Layer မှာ ပြင်ဆင်တည်းဖြတ်မှု mode တွင် ရှိနေကြောင်းညွှန်ပြပြီး ထို Layer ရှိ data များကို ပြင်ဆင်မွမ်းမံနိုင်ပါသည်။
* |editableEdits| သည် ပြင်ဆင်တည်းဖြတ်နေသော Layer တွင် သိမ်းဆည်းမှုမပြုလုပ်ရသေးသော ပြောင်းလဲမှုများ ရှိနေကြောင်း ပြသသည်။
* |indicatorFilter| သည် Layer တွင် အသုံးပြုထားသော :ref:`filter <vector_query_builder>` (စစ်ထုတ်မှု) ကို ညွှန်ပြပြီး ထို icon ပေါ်တွင် mouse ကိုတင်ကြည့်ပါက စစ်ထုတ်ထားသည့် Expression (ခိုင်းစေချက်) ကိုကြည့်နိုင်ပြီး  Query (အချက်အလက်များရှာဖွေခြင်း) ကို update ပြုလုပ်ရန် click နှစ်ချက်နှိပ်ပါ။
* |indicatorNonRemovable| သည် Project အတွင်း :ref:`required (လိုအပ်သော) <project_layer_capabilities>`  layer များကို ဖော်ပြပြီး ထို layer များကို ရွေ့ပြောင်း၍မရနိုင်ပါ။
* |indicatorEmbedded| သည် :ref:`embedded group or layer <nesting_projects>` (ထည့်သွင်းထားသော အုပ်စု သို့မဟုတ် layer) တစ်ခုနှင့် ၎င်းတို့၏ မူလ project ဖိုင်လမ်းကြောင်းကို ဖော်ပြသည်။
* |indicatorBadLayer| သည် Project တစ်ခုကိုဖွင့်လိုက်သောအခါ data အရင်းအမြစ် မရှိသည့် Layer ကို ဖော်ပြသည် (:ref:`handle_broken_paths` တွင် ကြည့်ရှုပါ)။ အရင်းအမြစ်လမ်းကြောင်းကို update လုပ်ရန် ထို icon ကို click နှိပ်ပါ သို့မဟုတ် layer ၏ Context menu မှ :guilabel:`Repair Data Source...` ကိုရွေးချယ်၍ အရင်းအမြစ်လမ်းကြောင်းကို ပြန်လည်ပြင်ဆင်နိုင်သည်။
* |indicatorMemory| သည် Project အတွင်း အသုံးပြုနေသော Layer သည် :ref:`temporary scratch layer <vector_new_scratch_layer>` (စက်၏မှတ်ဉာဏ်တွင် သိမ်းဆည်းခြင်းမဟုတ်ဘဲ Project အတွင်းသာ သိမ်းဆည်းသည့် Layer) ဖြစ်ကြောင်း သတိပေးဖော်ပြနေသည်။ ထို Layer များသည် Project အတွင်း ယာယီဖန်တီးထားသော Layer များဖြစ်သည့်အတွက် QGIS အား ပိတ်လိုက်ပါက အဆိုပါ Layer များ ဆုံးရှုံးသွားနိုင်ပြီး ထိုသို့မဖြစ်စေရန် သိမ်းဆည်းလိုပါက icon အား နှိပ်၍ QGIS မှ ပံ့ပိုးပေးထားသည့် GDAL vector format တစ်ခုခုဖြင့် သိမ်းဆည်းထားနိုင်သည်။
* |indicatorOffline| သည် :ref:`offline editing mode (အင်တာနက်မလိုသော ပြင်ဆင်တည်းဖြတ်ခြင်း mode)
  <offlinedit>` တွင် အသုံးပြုထားသော layer ကိုဖော်ပြသည်။
* |indicatorNoCRS| သည် Layer တွင် ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (CRS) မပါရှိကြောင်း သို့မဟုတ် သတ်မှတ်ထားသော ကိုဩဒိနိတ်စနစ်မဟုတ်ကြောင်း ပြသသည်။
* |indicatorLowAccuracy| သည် ပင်ကိုသဘောအရ တိကျမှု နည်းပါးသော CRS တစ်ခုဖြင့် သိမ်းဆည်းထားသော ကိုဩဒိနိတ်များပါဝင်သည့် layer များအတွက် ဖြစ်သည်။ (:ref:`corresponding setting <crs_inaccuracies>` တွင် ဖွင့်ပေးထားရန် လိုအပ်ပါသည်။)
* |indicatorTemporal| သည် မြေပုံမျက်နှာပြင်တွင် animation (လှုပ်ရှားပုံရိပ်) ပြုလုပ်နေသော အချိန်နှင့်ပတ်သက်သော Layer များကို ဖော်ပြပါသည်။
* |indicatorNotes| သည် Layer တွင် ၎င်းနှင့်ပတ်သက်သည့် :ref:`notes (မှတ်စု) <layer_notes>` များ ပါရှိကြောင်း ပြသသည်။
* လက်ရှိမြေပုံမျက်နှာပြင်စကေးသည် layer ၏ မြင်ရနိုင်မှု စကေးအပိုင်းအခြားပြင်ပသို့ ရောက်ရှိနေပါက မီးခိုးရောင်စာလုံး အမည်ဖြင့် ပြသမည် ဖြစ်သည် (:menuselection:`Rendering` (ပုံဖော်ပြသခြင်း) properties တွင် သတ်မှတ်ထားသည့်အတိုင်း)။ Layer ၏ အနီးစပ်ဆုံး မြင်ရနိုင်မှုစကေး အတိုင်းအတာအထိ မြေပုံကို zoom ပြုလုပ်ရန် context menu ထဲရှိ :guilabel:`Zoom to Visible Scale` (မြင်ရနိုင်သောစကေးသို့ချုံ့/ချဲ့ကြည့်ခြင်း) ကို ရွေးချယ်ပါ။


.. _render_as_group:


Control layers rendering through grouping (Layer များပုံဖော်ပြသခြင်းကို အုပ်စုဖွဲ့ခြင်းဖြင့် ထိန်းချုပ်ခြင်း)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

အုပ်စုများသည် Project အတွင်းရှိ Layer များကို ဖွဲ့စည်းတည်ဆောက်ထားခြင်းဖြစ်ပြီး ၎င်းတို့သည် မြေပုံ rendering (ပုံဖော်ပြသခြင်း) ပြုလုပ်စဉ်တွင် ၎င်းတို့အတွင်းပါဝင်သော layer များ ပုံဖော်ပြသခြင်းကို ဝတ္ထုတစ်ခုတည်းအနေဖြင့် သက်ရောက်မည်ဖြစ်သည်။ 

အုပ်စုတစ်ခုကို ရွေးချယ်ပြီးချိန်တိုင်းတွင် ထိုသို့သော rendering အတွက် လုပ်ဆောင်နိုင်သောရွေးချယ်စရာများကို :guilabel:`Layer Styling` (Layer style ပြင်ဆင်နိုင်သော) panel တွင် ရရှိနိုင်ပါသည်။ |symbology| :sup:`Symbology` tab အောက်ရှိ |checkbox| :guilabel:`Render Layers as a Group` (Layer များကို အုပ်စုတစ်ခုအနေဖြင့် ပုံဖော်ပြသမည်) ကို အမှန်ခြစ်ခြစ်ထားခြင်းသည် layer ခွဲငယ်တစ်ခုချင်းစီအစား layer အားလုံး၏ အသွင်အပြင်ကို တစ်ခုတည်းအနေဖြင့် ပုံဖော်ပြသရန် ရွေးချယ်စရာများရရှိစေပါသည်။ 

* :guilabel:`Opacity` (အလင်းပိတ်နှုန်း) - Group အတွင်းရှိ အခြား Layer ခွဲငယ်များမှ ဖုံးကွယ်ခြင်းခံထားရသော layer ခွဲငယ်များ၏ feature များသည် ဖုံးကွယ်ခံနေရမည်ဖြစ်သည်။ Opacity (အလင်းပိတ်နှုန်း) ကို အုပ်စုတစ်ခုလုံးအတွက်သာ အသုံးပြုသွားမည်ဖြစ်သည်။ 


 .. _figure_group_opacity:


  .. figure:: img/group_opacity.png
     :align: center

     Layer များပေါ်တွင် opacity သတ်မှတ်ခြင်း vs အုပ်စုတစ်ခုပေါ်တွင် opacity သတ်မှတ်ခြင်း 

     ဘယ်ဘက်ရှိပုံတွင် Opacity (အလင်းပိတ်နှုန်း) ၅၀% ဖြင့် ပုံဖော်ပြသထားသော Layer နှစ်ခုကို ပြသထားသည်။ (ပုံတွင် ပြထားသည့်အတိုင်း အပေါ်ရှိအနီရောင် feature မှ ၅၀% ဖုံးကာထားသော်လည်း အောက်တွင်ရှိ‌သော feature ကို မြင်နိုင်သည်။) ဒုတိယပုံတွင် အုပ်စုတစ်ခုအား opacity setting သတ်မှတ်ထားခြင်း၏ ရလာဒ်ကို ပြသထားပါသည်။ (အောက်တွင်ရှိသော အပြာရောင် Layer ခွဲငယ်၏အစိတ်အပိုင်းများကို အပေါ်ရှိ အနီရောင် Layer မှ Layer နှစ်ခုထပ်နေသောနေရာတွင် လုံးဝဖုံးကာထားသည်ကို တွေ့နိုင်သည်။ Opacity (အလင်းပိတ်နှုန်း) ၅၀% ဖြင့် ပုံဖော်ပြသထားသော ရလာဒ်ဖြစ်သည်။)

* :guilabel:`Blend modes` (ရောစပ်ခြင်းနည်းလမ်းများ) - Opacity (အလင်းပိတ်နှုန်း) ကဲ့သို့ပင် အုပ်စုတစ်ခုလုံးအတွက် :ref:`blend mode <blend-modes>` ပြုလုပ်ခြင်းသည် Layer ခွဲငယ်များ၏ features များကို တစ်ခုတည်းဖြစ်အောင် ပေါင်းစည်းသွားစေပြီး အောက်တွင်ရှိသော Layer ကို အပေါ် Layer မှ ဖုံးကာနေမည်ဖြစ်သည်။ ထို့နောက် ပေါင်းထားသည့် အုပ်စုနှင့် အဆိုပါအုပ်စုအောက်ရှိ အခြား Layer များကို Blend (ရောစပ်ခြင်း) ပြုလုပ်၍ ပုံဖော်ပြသပေးပါသည်။

  * Layer ခွဲငယ်များကို ပေါင်းစည်းခြင်းမပြုလုပ်မီ Blend mode သတ်မှတ်ပေးသောအခါ ထိုအုပ်စုအတွင်းရှိ Layer ခွဲငယ်များကိုသာ သက်ရောက်မှုရှိမည်ဖြစ်ပြီး အုပ်စုတစ်ခုလုံးအောက်ရှိ အခြားသော Layer များကို သက်ရောက်စေမည်မဟုတ်ပါ။ 

  * အုပ်စုများ၏ :guilabel:`Symbology` tab ထဲတွင် ၎င်းတို့အတွင်းရှိ Layer ခွဲငယ်များအတွက် အချို့ :ref:`blending modes <blending_clipping>` ရွေးချယ်စရာများ ရရှိနိုင်ပြီး ပုံဖော်ပြသနေစဉ်အတွင်း အခြား layer ခွဲငယ်များအပေါ်တွင် style "clipping" (ဖြတ်ထုတ်သော) လုပ်ငန်းစဉ်များ ဆောင်ရွက်ပေးပါသည်။  ဥပမာအားဖြင့် Layer တစ်ခု၏ အကြောင်းအရာ ပုံဖော်ပြသခြင်းကို ဒုတိယ "mask" (ဖုံးအုပ်) Layer ၏ အကြောင်းအရာဖြင့် clip (ဖြတ်ထုတ်) ပြုလုပ်နိုင်သည်။

* :guilabel:`Layer effects` - Layer ခွဲငယ်များကို ပေါင်းစည်းကာ ပုံဖော်ပြသခြင်းတွင်သာ :ref:`effects <draw_effects>` များကို အသုံးပြုပါသည်။ ဥပမာ- အုပ်စုတစ်ခုကို drop shadow (အရိပ်ကျ) effect ပြုလုပ်ထားပါက အဆိုပါ အုပ်စုအတွင်းရှိ ဖုံးကာခံထားရသည့် Layer ခွဲငယ်များကို တွေ့မြင်နိုင်မည်မဟုတ်ပါ။ 

အုပ်စုတစ်ခုကို :guilabel:`Render layers as a group` (Layer များကိုအုပ်စုတစ်ခုအနေဖြင့် ပုံဖော်ပြသ) ဟု သတ်မှတ်ပြီးပါက :guilabel:`Layer Order` (Layer အစီအစဉ်) panel list တွင် အုပ်စုအနေဖြင့်သာ တွေ့မြင်နိုင်မည်ဖြစ်ပါသည်။ Layer ခွဲငယ်များ၏ စီစဉ်မှုသည် အုပ်စု layer ၏ နေရာချထားမှုဖြင့် ဆုံးဖြတ်ခြင်းဖြစ်သောကြောင့် အဆိုပါအုပ်စုအတွင်းရှိ Layer ခွဲငယ်များကို Layer အစီအစဉ် (order) တွင် တွေ့မြင်နိုင်မည်မဟုတ်ပါ။


.. index:: Style


.. _editing_style_layer:


Editing layer style (Layer style များကို ပြင်ဆင်တည်းဖြတ်ခြင်း)
...............................................................
 
:guilabel:`Layers` panel သို့ဝင်ရောက်၍ Layer style များကို လွယ်ကူလျင်မြန်စွာ ပြောင်းလဲရန် ဖြတ်လမ်းနည်း (shortcuts) များကို အသုံးပြုနိုင်သည်။ 

Layer တစ်ခုကို Right-click နှိပ်ပြီး :menuselection:`Styles -->` ကိုရွေးချယ်ပြီးနောက် အောက်ပါတို့ကို ပြုလုပ်နိုင်ပါသည်-

* Layer များအတွက် လက်ရှိအသုံးပြုနိုင်သော Layer စတိုင်လ်များကို ပိုမိုသိရှိရန်  :ref:`styles <manage_custom_style>` တွင် ကြည့်နိုင်သည်။ အကယ်၍ Layer အတွက် style များစွာ သတ်မှတ်ထားလျှင် မိမိပြောင်းလဲလိုသော style ကို တစ်ခုမှတစ်ခုသို့ ပြောင်းလဲရွေးချယ်နိုင်မည်ဖြစ်ပြီး ရွေးချယ်လိုက်သော style သည် မြေပုံမျက်နှာပြင်ပေါ်တွင် လိုက်လံပြောင်းလဲဖော်ပြနေမည်ဖြစ်ပါသည်။ 
* လက်ရှိရွေးချယ်ထားသော style ၏ တစ်စိတ်တစ်ပိုင်းကို ဖြစ်စေ အားလုံးကိုဖြစ်စေ ကူးယူပြီးနောက် အခြား Layer တစ်ခုတွင် ထည့်၍ အသုံးပြုနိုင်ပါသည်။
* :guilabel:`Rename current...` style ကို အသုံးပြု၍ လက်ရှိအသုံးပြုနေသော style ၏ အမည်ကို ပြောင်းလဲသတ်မှတ်နိုင်ပါသည်။ 
* :guilabel:`Add` ကို အသုံးပြု၍ style အသစ်တစ်ခု ထပ်မံထည့်သွင်းနိုင်ပါသည်။ (အမှန်တကယ်မှာမူ ၎င်းသည် လက်ရှိ style ၏ မိတ္တူပုံစံ တစ်ခုဖြစ်ပါသည်။)
* သို့မဟုတ် :guilabel:`Remove current` ကို အသုံးပြု၍ လက်ရှိ style ကို ဖယ်ရှားနိုင်သည်။ (သို့သော် စတိုင်လ်များစွာရှိနေသည့်အခါတွင်သာ ဖယ်ရှားနိုင်မည်ဖြစ်သည်။)

  .. tip:: **Layer style တစ်ခုကို လျင်မြန်စွာ မျှဝေအသုံးပြုနိုင်ရန်**

        Context menu ထဲမှ Layer တစ်ခု၏ style ကို ကူးယူ၍ အုပ်စုတစ်ခု သို့မဟုတ် Layer များရွေးချယ်ထားမှုတစ်ခုထဲသို့ paste (ကူးချသည်) ပြုလုပ်လိုက်သောအခါ အဆိုပါ အုပ်စု သို့မဟုတ် Layer အားလုံးသည် အမျိုးအစားတူညီပါက (ဥပမာ- vector ၊ raster ၊ mesh ၊ point cloud ၊.....) ကူးယူလာသော style သည် Layer အားလုံးတွင် အသုံးပြုသွားမည်ဖြစ်ပါသည်။ Vector layer များအတွက်မူ  point ၊ line သို့မဟုတ် polygon စသော geometry type များ တူညီနေပါက ကူးယူလာသော style သည် Layer အားလုံးတွင် အသုံးပြုသွားမည်ဖြစ်ပါမည်။  


Layer အတွင်းပါဝင်သော feature များပေါ်မူတည်၍ သင်္ကေတများကို သတ်မှတ်ရာတွင် (ဥပမာ- vector layer များအတွက်  :ref:`categorized (အမျိုးအစားအလိုက် ဖော်ပြခြင်း) <categorized_renderer>` ၊ :ref:`graduated (အဆင့်အလိုက် ဖော်ပြခြင်း) <graduated_renderer>` သို့မဟုတ် :ref:`rule-based (စည်းမျဉ်းသတ်မှတ်ချက်များကိုအခြေခံ၍ဖော်ပြခြင်း) <rule_based_rendering>` ၊ သို့မဟုတ် point cloud များအတွက် :ref:`classification (point cloud ပေါ်မူတည်၍ ခွဲခြားဖော်ပြခြင်း) <point_cloud_classification>`) :guilabel:`Layers` panels ထဲရှိ class entry ကို right-click နှိပ်ခြင်းဖြင့် class များနှင့် ၎င်းတို့၏ feature များ၏ မြင်ရနိုင်မှုကို ပြင်ဆင်သတ်မှတ်နိုင်ပြီး ရွေးချယ်၍ entry တစ်ခုချင်းစီကို အမှန်ခြစ်ခြင်း/အမှန်ခြစ်ဖြုတ်ခြင်းပြုလုပ်၍ ကြည့်ရခြင်းမှလည်း ရှောင်ရှားနိုင်သည်-


* |toggleAllLayers| :guilabel:`Toggle Items` ကိုအသုံးပြု၍ item များကို တစ်ဖက်ပိတ်/ဖွင့်လုပ်၍ ကြည့်နိုင်သည်။
* |showAllLayers| :guilabel:`Show All Items` ကိုအသုံးပြု၍ item များအားလုံးကို ပြသနိုင်သည်။
* |hideAllLayers| :guilabel:`Hide All Items` ကိုအသုံးပြု၍ item များအားလုံးကို ဖျောက်ထားနိုင်သည်။


Vector layer များတွင် class ၏ context menu သည် အောက်ပါတို့ကို လုပ်ဆောင်နိုင်စေပါသည်- 

* |selectAll| :guilabel:`Select features`- ကို အသုံးပြု၍ class နှင့် ကိုက်ညီသည့် Layer ထဲရှိ feature အားလုံးကို ရွေးချယ်နိုင်သည်။ 
* |openTable| :guilabel:`Show in attribute table`- ကို အသုံးပြု၍ class နှင့် ကိုက်ညီသည့် feature များကိုသာ စစ်ထုတ်၍ ဖော်ပြသည့် attribute table (အချက်အလက်ဇယား)ကို ဖွင့်နိုင်ပါသည်။ 
* **Color Wheel (ရောင်စုံဘီး)** ကိုအသုံးပြု၍ :ref:`symbol color (သင်္ကေတအရောင်)<color-selector>` ကို အရောင်ရွေးချယ်၍ ပြင်ဆင်နိုင်ပြီး အရောင်ရွေးချယ်ရာတွင် ပိုမိုအဆင်ပြေစေရန်အတွက် ရောင်စုံဘီး၏ အောက်ခြေတွင် မကြာသေးမီက အသုံးပြုခဲ့သော အရောင်များကို ရွေးချယ်၍လည်း ပြန်လည်အသုံးပြုနိုင်ပါသည်။ 
* :guilabel:`Edit Symbol...` ကို နှိပ်ပါက :ref:`Symbol Selector <symbol-selector>` dialog ပွင့်လာပြီး feature များ၏ သင်္ကေတများ (သင်္ကေတ၊ အရွယ်အစား၊ အရောင် စသည်) ကို ပြောင်းလဲနိုင်သည်။
* :guilabel:`Copy Symbol` ကို အသုံးပြု၍ သင်္ကေတများကို ကူးယူနိုင်ပါသည်။ 
* :guilabel:`Paste Symbol` ကို အသုံးပြု၍ သင်္ကေတများကို ကူးချနိုင်ပါသည်။ 


.. tip:: Class တစ်ခုကို နှစ်ချက်နှိပ်ခြင်းဖြင့်လည်း :guilabel:`Symbol Selector` dialog (သင်္ကေတရွေးချယ်နိုင်သည့် dialog) ကို ပွင့်လာစေမည်ဖြစ်သည်။ 


.. index::
   single: Layer properties
   single: Panels; Style
.. _layer_styling_panel:


Layer Styling Panel (Layer style ပြုလုပ်နိုင်သော Panel)
--------------------------------------------------------

:guilabel:`Layer Styling` panel (:kbd:`Ctrl+3` ဖြင့်လည်း ဖွင့်နိုင်သည်) သည် :guilabel:`Layer Properties` dialog ၏ လုပ်ဆောင်ချက်အချို့ကို ပြုလုပ်နိုင်သော ဖြတ်လမ်းနည်းတစ်ခုဖြစ်ပါသည်။ ၎င်းတွင် Layer တစ်ခု၏ ပုံဖော်ပြသခြင်းနှင့် သဘောသဘာဝကို သတ်မှတ်ခြင်းအပြင် :guilabel:`Layer Properties` ကို ဖွင့်ရန်မလိုဘဲ ၎င်းတို့၏ effect များပုံဖော်ကြည့်ရှုနိုင်ပါသည်။ 

Layer Styling Panel သည် Layer properties dialog ကို ဖွင့်စရာမလိုသည့်အပြင် style နှင့် ပတ်သက်သော (အရောင်ရွေးချယ်မှု၊ effect property များ ၊ ပြင်ဆင်တည်းဖြတ်မှု၊ အညွှန်းအစားထိုးခြင်း စသော) လုပ်ဆောင်ချက်များကို  dialog များစွာ ဖွင့်ရန်မလိုဘဲ တစ်နေရာတည်းတွင် လုပ်ဆောင်နိုင်သည်။ ဥပမာ-  Layer style panel ထဲရှိ color button (အရောင်ရွေးချယ်ရာနေရာ) ကို နှိပ်ခြင်းဖြင့် သီးသန့် dialog ပွင့်မလာစေဘဲ ၎င်း layer style panel ထဲတွင်သာ အရောင်ရွေးချယ်မှုပြုလုပ်နိုင်သော dialog ကို ပွင့်လာစေမည် ဖြစ်သည်။ 

Layer panel ထဲရှိ လက်ရှိ Layer များကို ပြသသော drop-down list မှ item တစ်ခုကို ရွေးချယ်ပြီး- 

* အသက်ဝင်နေသော item ပေါ်မူတည်၍ အောက်ပါတို့ကို သတ်မှတ်နိုင်ပါသည်-

  * :guilabel:`Symbology` ကို အသုံးပြု၍ အုပ်စုများအတွက် Symbol (သင်္ကေတ) ကိုရွေးချယ်နိုင်ပါသည်။  (:ref:`render_as_group` တွင် ကြည့်ရှုနိုင်ပါသည်။)
  * Raster layer အတွက် |symbology| :guilabel:`Symbology` (သင်္ကေတဆိုင်ရာများ)၊ |transparency| :guilabel:`Transparency` (အလင်းဖောက်နှုန်း)၊ |rasterHistogram| :guilabel:`Histogram` (ကြိမ်နှုန်းပြဂရပ်) ဆိုင်ရာ ဂုဏ်သတ္တိများ။ ထိုရွေးချယ်စရာများသည် :ref:`raster_properties_dialog` ထဲတွင် ပါရှိသော ရွေးချယ်စရာများနှင့် အတူတူပင် ဖြစ်သည်။ 
  * Vector layer အတွက် |symbology| :guilabel:`Symbology`၊ |labelingSingle| :guilabel:`Labels`(အညွှန်း)၊ |labelmask| :guilabel:`Mask` (အဖုံးအကာ) နှင့် |3d| :guilabel:`3D View` (သုံးဖက်မြင်ကွင်း) ဆိုင်ရာ ဂုဏ်သတ္တိများ။ ထိုရွေးချယ်စရာများသည် :ref:`vector_properties_dialog` ထဲတွင် ပါရှိသော ရွေးချယ်စရာများနှင့် အတူတူပင် ဖြစ်ပြီး third-party plugins များမှ မိတ်ဆက်ပံ့ပိုးပေးထားသည့် စိတ်ကြိုက်ပြင်ဆင်နိုင်သော ဂုဏ်သတ္တိများဖြင့် တိုးချဲ့အသုံးပြုနိုင်ပါသည်။
  * Mesh layer အတွက် |symbology| :guilabel:`Symbology` နှင့် |3d| :guilabel:`3D View` ဆိုင်ရာ ဂုဏ်သတ္တိများ။ ထိုရွေးချယ်စရာများသည် :ref:`label_meshproperties` ထဲတွင် ပါရှိသော ရွေးချယ်စရာများနှင့် အတူတူပင် ဖြစ်ပါသည်။
  * Point cloud layer အတွက် |symbology| :guilabel:`Symbology`၊ |3d| :guilabel:`3D View` နှင့် |elevationscale| :guilabel:`Elevation` (အမြင့်) ဆိုင်ရာ ဂုဏ်သတ္တိများ။ ထိုရွေးချယ်စရာများသည် :ref:`point_clouds_properties` တွင် ပါရှိသော ရွေးချယ်စရာများနှင့် အတူတူပင် ဖြစ်ပါသည်။

* |stylePreset| :guilabel:`Style Manager` ရှိ ဆက်စပ် style များကို စီမံခန့်ခွဲနိုင်သည်။ (အသေးစိတ်အချက်အလက်များကို :ref:`manage_custom_style` တွင် ကြည့်ရှုနိုင်ပါသည်။)
* လက်ရှိလုပ်ဆောင်နေသော project အတွင်းရှိ Layer style တွင် လုပ်ဆောင်ခဲ့သော ပြောင်းလဲမှုများကို |history| :guilabel:`History` (မှတ်တမ်း) တွင် ကြည့်ရှုနိုင်သည်။ ထို့ကြောင့် မှတ်တမ်းထဲတွင် ရွေးချယ်ပြီး :guilabel:`Apply` နှိပ်ခြင်းဖြင့် မည်သည့်အခြေအနေကိုမဆို ပြန်ခေါ်ခြင်း သို့မဟုတ် ပယ်ဖျက်ခြင်းများလုပ်ဆောင်နိုင်သည်။

ဤ panel ၏ နောက်ထပ်အသုံးဝင်သောလုပ်ဆောင်ချက်တစ်ခုမှာ |checkbox| :guilabel:`Live update` checkbox (လက်ရှိလုပ်ဆောင်ချက်အတိုင်း အချိန်နှင့်တပြေးညီလိုက်လံပြောင်းလဲခြင်း)ဖြစ်သည်။ မြေပုံမျက်နှာပြင်ပေါ်တွင် ပြုလုပ်သော ပြောင်းလဲလုပ်ဆောင်ချက်များအတိုင်း လိုက်လံပြောင်းလဲစေရန် |checkbox| :guilabel:`Live update` checkbox တွင် အမှန်ခြစ်ပြုလုပ်ခြင်းအားဖြင့် :guilabel:`Apply` ကို နှိပ်ရန် မလိုဘဲ  ဆောင်ရွက်နိုင်သည်။


.. _figure_layer_styling:


.. figure:: img/layer_styling.png
        :align: center


        Layer styling panel မှ layer ၏ သင်္ကေတကို သတ်မှတ်ခြင်း


.. index:: Layers; Order
.. _layer_order:


Layer Order Panel (Layer အစီအစဉ်ပြ Panel)
------------------------------------------

ပုံမှန်အားဖြင့် QGIS မြေပုံမျက်နှာပေါ်တွင် ပြသထားသော layer များသည် :guilabel:`Layers` panel ထဲတွင်ရှိသော အစဉ်လိုက်အတိုင်း ပြသနေခြင်းဖြစ်ပါသည်။ ဆိုလိုသည်မှာ Panel ထဲရှိ အပေါ်တွင်ရှိသော Layer သည် မြေပုံမြင်ကွင်းတွင်လည်း အပေါ်ဘက်တွင်ရှိနေမည်ဖြစ်သည်။ 

:guilabel:`Layer Order` (Layer အစီအစဉ်ပြ Panel) panel ကို :menuselection:`View --> Panels -->` menu သို့ဝင်ရောက်၍ သို့မဟုတ် :kbd:`Ctrl+9` နှိပ်၍ ဖွင့်နိုင်ပြီး ၎င်း Panel တွင် Layer အစဉ် (Drawing order) ကို Layers panel ထဲရှိ Layer အစဉ်လိုက်နှင့် သက်ဆိုင်မှုမရှိစေဘဲ သတ်မှတ်နိုင်ပါသည်။ Layer များစာရင်းအောက်ရှိ |checkbox| :guilabel:`Control rendering order` ကို အမှန်ခြစ်ပြုလုပ်၍ Panel ထဲရှိ Layer များကို မိမိလိုချင်သည့်အစဉ်အတိုင်း ပြန်လည်စုစည်းနိုင်ပြီး အဆိုပါ Layer အစဉ်အတိုင်း မြေပုံမျက်နှာပြင်ပေါ်တွင် ပြသနေမည်ဖြစ်သည်။ ဥပမာအားဖြင့် :numref:`figure_layer_order` တွင် Layers panel ထဲရှိ သက်ဆိုင်ရာ Layer များ၏ နေရာချထားမှုအတိုင်းအစဉ်လိုက်တွေ့မြင်ရမည့်အစား ``alaska`` polygon ပေါ်တွင် ``airports`` features များကို တွေ့မြင်ရမည်ဖြစ်သည်။ 

|checkbox| :guilabel:`Control rendering order` ကို အမှန်ခြစ်ဖြုတ်ခြင်းအားဖြင့် Layer အစဉ်ကို မူရင်းအတိုင်း ပြန်လည် ပြောင်းလဲနိုင်သည်။ 


.. _figure_layer_order:


.. figure:: img/layer_order.png
        :align: center


        Legend နှင့်သက်ဆိုင်မှုမရှိဘဲ Layer အစဉ်များကို သတ်မှတ်ခြင်း


.. index::
   single: Map; Overview
   single: Panels; Overview
.. _`overview_panels`:


Overview Panel (ခြုံငုံကြည့်ရှုခြင်းဆိုင်ရာ Panel)
---------------------------------------------------

:guilabel:`Overview` panel ကို :kbd:`Ctrl+8` ဖြင့် ဖွင့်နိုင်ပြီး ၎င်း panel သည် Layer များ၏ မြင်ကွင်းအပြည့်အစုံကို မြေပုံပေါ်တွင် မြင်နိုင်ရန် ကူညီပေးပါသည်။ ခြုံငုံကြည့်ရှုနိုင်သောမြေပုံ (overview map) ကို အသုံးပြုနေသော :menuselection:`Layer` ၏ option မှဖြစ်စေ၊ Layer ၏ Context menu မှဖြစ်စေ :guilabel:`Show in Overview` ကို နှိပ်၍ ကြည့်နိုင်သည်။ မြင်ကွင်းထဲရှိ အနီရောင်စတုဂံလေးသည် လက်ရှိအသုံးပြုနေသော မြေပုံမျက်နှာပြင်၏ဧရိယာကို ဖော်ပြပြီး မြေပုံဧရိယာတစ်ခုလုံး၏ မည်သည့်အပိုင်းကို  အသုံးပြုနေသည်ကို လွယ်ကူစွာ သိရှိနိုင်အောင် ကူညီပေးပါသည်။ Overview frame ထဲရှိ အနီရောင်စတုဂံလေးအား ဖိဆွဲ၍ရွှေ့ကြည့်လျှင် မြေပုံမျက်နှာပြင်မြင်ကွင်းသည်လည်း အလိုအလျောက် ရွေ့သွားမည် ဖြစ်သည်။

Map overview တွင် ပါဝင်သော Layer များကို အညွှန်းများ သတ်မှတ်ထားသော်လည်း ခြုံငုံကြည့်ရှုသောမြေပုံမြင်ကွင်းတွင် ယင်းအညွှန်းများကို ပုံဖော်ပြသမည်မဟုတ်ကြောင်း သတိပြုပါ။


.. index::
   single: Log messages
   single: Panels; Log messages


.. _`log_message_panel`:


Log Messages Panel (လုပ်ဆောင်ချက်မှတ်တမ်း အကြောင်းကြားချက်များဆိုင်ရာ Panel)
-----------------------------------------------------------------------------

Project တွင် အချို့သောလုပ်ဆောင်ချက်များ ဆောင်ရွက်သောအခါ |messageLog| :guilabel:`Log Messages Panel` ရှိ tab များတွင်ဖော်ပြနေသော အကြောင်းကြားချက်များအတိုင်း ခြေရာခံ၍ ဆောင်ရွက်နိုင်ပါသည်။ ၎င်း Panel ကို Project ၏ အောက်ခြေ status bar ၏ ညာဖက်အစွန်ဆုံး icon ကို အသုံးပြု၍ ဖွင့်နိုင်ပါသည်။


.. index:: Undo, Redo
   single: Panels; Undo
   single: Panels; Redo


.. _`undo_redo_panel`:


Undo/Redo Panel (ပြောင်းလဲမှုအား မလုပ်ဆောင်တော့ခြင်း/ပြန်လည်လုပ်ဆောင်စေခြင်း ဆောင်ရွက်နိုင်သည့် Panel)
-------------------------------------------------------------------------------------------------------

:guilabel:`Undo/Redo` (:kbd:`Ctrl+5`) panel သည် ပြင်ဆင်တည်းဖြတ်မှုပြုလုပ်နေသော Layer တစ်ခုချင်းစီအတွက် လုပ်ဆောင်ခဲ့သော လုပ်ငန်းအဆင့်ဆင့်အား ဖော်ပြထားပြီး ယင်းလုပ်ငန်းအဆင့်ဆင့်မှ အချို့လုပ်ဆောင်မှုများအား ရွေးချယ်၍ ပယ်ဖျက်ခြင်းကို ဆောင်ရွက်နိုင်ပါသည်။ :ref:`Undo and Redo edits (ပြောင်းလဲမှုအားမလုပ်ဆောင်တော့ခြင်းနှင့် ပြန်လည်လုပ်ဆောင်ခြင်း ပြင်ဆင်ခြင်းများ) <undoredo_edits>` တွင် အသေးစိတ်ဖော်ပြထားပါသည်။


.. index::
   single: Panels; Statistic
   single: Statistic


.. _`statistical_summary`:


Statistical Summary Panel (စာရင်းအင်းအချက်အလက်ဆိုင်ရာ အနှစ်ချုပ် Panel)
------------------------------------------------------------------------

:guilabel:`Statistics` panel ကို ဖြတ်လမ်းနည်းအနေဖြင့် :kbd:`Ctrl+6` ကိုသုံး၍ ဖွင့်နိုင်ပြီး Project တွင်အသုံးပြုနေသော vector layer တိုင်း၏ အချက်အလက်များကို အနှစ်ချုပ်ဖော်ပြပေးပါသည်။ ထို့ပြင် ဤ Panel မှ အောက်ဖော်ပြပါများကို ရွေးချယ်နိုင်ပါသည်-

* စာရင်းအင်းအချက်အလက်တွက်ချက်လိုသော Vector layer ကို Panel ၏ထိပ်ပိုင်းတွင်တည်ရှိသော drop-down menu မှ ရွေးချယ်၍သော်လည်းကောင်း၊ Statistics drop-down list အောက်ခြေမှ :guilabel:`Follow selected layer` ကို သုံး၍ :guilabel:`Layers` panel တွင် လက်ရှိအသုံးပြုနေသော layer အား ရွေးချယ်၍သော်လည်းကောင်း တွက်ချက်နိုင်ပါသည်။
* အသုံးပြုမည့် Field သို့မဟုတ် |expression| :ref:`expression <vector_expressions>` ကိုရွေးချယ်နိုင်သည်- layer တစ်ခုချင်းစီအတွက် နောက်ဆုံးထည့်သွင်းထားသော entry အား မှတ်သားထားပြီး Layer ပြန်လည်ရွေးချယ်မှုပေါ်မူတည်၍ အလိုအလျောက်တွက်ချက်သွားမည်ဖြစ်သည်။
* Dialog ၏ ညာဘက်အောက်ခြေရှိ drop-down ခလုတ်ကိုအသုံးပြု၍ field တစ်ခုချင်းစီ၌ တွက်ချက်လိုသည့် စာရင်းအင်းအချက်အလက်များကို ရွေးချယ်နိုင်သည်။ Field ၏ (Expression ၏ တန်ဖိုးများ) အမျိုးအစားပေါ်မူတည်၍ ရရှိနိုင်သော စာရင်းအင်းအချက်အလက်များမှာ အောက်ပါအတိုင်းဖြစ်ပါသည်-


.. list-table:: Filed အမျိုးအစားတစ်ခုချင်းအလိုက် တွက်ချက်နိုင်သော စာရင်းအင်းအချက်အလက်များ
   :header-rows: 1
   :widths: 30 15 15 15 15
   :class: longtable

   * - Statistics (စာရင်းအင်းအချက်အလက်များ)
     - String
     - Integer
     - Float
     - Date
   * - Count (အရေအတွက်)
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - Count Distinct Value (ထင်ရှားသောတန်ဖိုးအရေအတွက်)
     - |checkbox|
     -
     -
     - |checkbox|
   * - Count Missing value (ပျောက်နေသည့်တန်ဖိုးအရေအတွက်)
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - Sum (ပေါင်းလဒ်)
     -
     - |checkbox|
     - |checkbox|
     -
   * - Mean (ပျမ်းမျှ)
     -
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - Standard Deviation (စံတိမ်းချက်)
     -
     - |checkbox|
     - |checkbox|
     -
   * - Standard Deviation on Sample (နမူနာများ၏ စံတိမ်းချက်)
     -
     - |checkbox|
     - |checkbox|
     -
   * - Minimal value (အနည်းဆုံးတန်ဖိုး)
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - Maximal value (အများဆုံးတန်ဖိုး)
     - |checkbox|
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - Range (အပိုင်းအခြား)
     -
     - |checkbox|
     - |checkbox|
     - |checkbox|   
   * - Minority (အနည်းစု)
     - |checkbox|
     - |checkbox|
     - |checkbox|
     -
   * - Majority (အများစု)
     - |checkbox|
     - |checkbox|
     - |checkbox|
     -
   * - Variety (အမျိုးအစားကွဲပြားမှု)
     -
     - |checkbox|
     - |checkbox|
     -
   * - First Quartile (ဒေတာတစ်ခု၏ ပထမလေးပုံတစ်ပုံ/၂၅ ရာခိုင်နှုန်း)
     -
     - |checkbox|
     - |checkbox|
     -
   * - Third Quartile (ဒေတာတစ်ခု၏ တတိယလေးပုံတစ်ပုံ/၇၅ ရာခိုင်နှုန်း)
     -
     - |checkbox|
     - |checkbox|
     -
   * - Inter Quartile Range (ဒေတာ၏အလယ်တစ်ဝက်တွင် ပြန့်နှံ့မှု)
     -
     - |checkbox|
     - |checkbox|
     -
   * - Minimum Length (အနည်းဆုံးအလျား)
     - |checkbox|
     - 
     -
     -        
   * - Maximum Length (အများဆုံးအလျား)
     - |checkbox|
     - 
     -
     -
   * - Mean Length (ပျမ်းမျှအလျား)
     - |checkbox|
     - 
     -
     -


စာရင်းအင်းအချက်အလက်ဆိုင်ရာ အနှစ်ချုပ်သည် အောက်ပါတို့ကို ဆောင်ရွက်နိုင်ပါသည်-

* စာရင်းအင်းဆိုင်ရာဒေတာများကို Layer တစ်ခုလုံးအတွက် တွက်ချက်နိုင်သည် သို့မဟုတ် |checkbox| :guilabel:`Selected features only` (ရွေးချယ်ထားသည့် feature များအတွက်သာ) ကို အမှန်ခြစ်ပြုလုပ်၍ Layer အတွင်းရှိ ရွေးချယ်ထားသည့် feature များအတွက်လည်း တွက်ချက်နိုင်သည်။
* |editCopy| သည် တွက်ချက်ထားသော ဒေတာများကို clipboard သို့ ကူးယူပြီး အခြား application တွင် ဇယားတစ်ခုအဖြစ် ကူးချ၍ အသုံးပြုနိုင်သည်။
* ရှိနေသည့် data အရင်းအမြစ်များ ပြောင်းလဲမှုပြုလုပ်သည့်အခါတိုင်း |refresh| button ကိုအသုံးပြု၍ ပြန်လည်တွက်ချက်နိုင်သည်။ (ဥပမာ- Layer ၏ feature/ field တစ်ခုခုကို ဖယ်ရှားခြင်း သို့မဟုတ် အသစ်ထပ်ထည့်ခြင်း၊ attribute ကို မွမ်းမံပြင်ဆင်ခြင်း)

.. _figure_statistical_summary:


.. figure:: img/statistical_summary.png
    :align: center


    Field တစ်ခုတွင်ရှိသော စာရင်းအင်းအချက်အလက်များကို ပြသခြင်း


.. index:: Debugging/Development Tools Panel
.. _debug_dev_tools:


Debugging/Development Tools Panel (အမှားရှာခြင်း/တိုးတက်ကောင်းမွန်စေခြင်းဆိုင်ရာ tool များ panel)
--------------------------------------------------------------------------------------------------

:guilabel:`Debugging/Development Tools` panel ကို ဖြတ်လမ်းနည်းအနေဖြင့် :kbd:`F12` သုံး၍ ဖွင့်နိုင်ပြီး  QGIS အတွင်းရှိ အမှားများရှာဖွေပြုပြင်ခြင်းနှင့် ဖြေရှင်းခြင်းလုပ်ဆောင်မှုများအတွက် တစ်စုတစ်စည်းတည်း စုစည်းပေးထားသော နေရာတစ်ခုဖြစ်ပါသည်။ ၎င်း Panel တွင် အသုံးပြုနိုင်သော tool များကို အောက်ပါ tab များအောက်တွင် စုစည်းထားပါသည်-

* |networkAndProxy| :guilabel:`Network Logger` (ကွန်ယက်ဆိုင်ရာမှတ်တမ်းပြုလုပ်ပေးသည့်အရာ)
* |dbManager| :guilabel:`Query Logger` (Query ဆိုင်ရာ မှတ်တမ်းပြုလုပ်ပေးသည့်အရာ)
* |stopwatch| :guilabel:`Profiler`


.. note:: Plugin ရေးဆွဲသူများသည် ၎င်းတို့၏ Plugin များကို အမှားရှာဖွေ၍ ပိုမိုကောင်းမွန်အောင် ပြင်ဆင်ခြင်းတို့အတွက် စိတ်ကြိုက်ပြင်ဆင်ထားသော tab များဖြင့် Panel ကို ချဲ့ထွင် အသုံးပြုနိုင်ပါသည်။ ၎င်းကို :meth:`registerDevToolWidgetFactory <qgis.gui.QgisInterface.registerDevToolWidgetFactory>` နည်းလမ်းကို အသုံးပြု၍ ဆောင်ရွက်နိုင်သည်။


Network Logger (ကွန်ယက်ဆိုင်ရာမှတ်တမ်းပြုလုပ်ပေးသည့်အရာ)
.........................................................

|networkAndProxy| :guilabel:`Network Logger` tab သည် ကွန်ယက်တောင်းဆိုမှုများကို မှတ်တမ်းပြုစုဖော်ပြသောနေရာဖြစ်သည်။ ၎င်းတွင် cache အခြေအနေများ၊ ကုန်ဆုံးချိန် (timeout)များ၊ SSL ပြင်ဆင်သတ်မှတ်ခြင်းအမှားများ၊ အမှားများ၊ ခေါင်းစဉ်များ၊ ပြင်ဆင်ရန်တောင်းဆိုမှုများနှင့် အကြောင်းပြန်ကြားမှုအခြေအနေများ အစရှိသည့် အသုံးဝင်သော အသေးစိတ်အချက်အလက်များပါဝင်သည်။

၎င်း၏ အပေါ်ပိုင်းရှိ toolbar မှ တစ်ဆင့် အောက်ဖော်ပြပါလုပ်ငန်းများ ဆောင်ရွက်နိုင်ပါသည်-

* |record| :guilabel:`Record Log` သည် မှတ်တမ်းယူခြင်း (logging) ကို စတင်ရန် သို့မဟုတ် ရပ်တန့်ရန် အသုံးပြုနိုင်သည်။
* |deleteSelected| :guilabel:`Clear Log` သည် မှတ်တမ်းအား ရှင်းလင်းရန် အသုံးပြုနိုင်သည်။
* |fileSave| :guilabel:`Save Log...` ကိုနှိပ်လျှင် မှတ်တမ်းများကို လျှို့ဝှက်အနေဖြင့် ထားရှိသင့်ကြောင်း သတိပေးချက်အကြီးစားတစ်ခုကို ဦးစွာ ပြသမည်ဖြစ်ပြီး ထို့နောက်တွင် မှတ်တမ်းများကို သိမ်းဆည်းခွင့်ပြုမည်ဖြစ်ပါသည်။
* |options| :guilabel:`Settings` ၏ drop-down menu အားနှိပ်၍  :guilabel:`Show Successful Requests` (အောင်မြင်သောတောင်းဆိုမှုများကို ဖော်ပြခြင်း)၊ :guilabel:`Show Timeouts` (ကုန်ဆုံးချိန်များကို ဖော်ပြခြင်း)နှင့် :guilabel:`Show Replies Served from Cache` (Cache များမှ ပြန်ကြားချက်များကို ပြသခြင်း) တို့အားရွေးချယ်နိုင်ပါသည်။
* |unchecked| :guilabel:`Disable cache` သည် တောင်းဆိုမှုတိုင်းအား ဆောင်ရွက်နိုင်ရန်အတွက် cache များအား ပိတ်ထားပါလိမ့်မည်။
* |search| :guilabel:`Filter requests` သည် URL string subsets သို့မဟုတ် တောင်းဆိုမှုများအခြေအနေအပေါ် မူတည်၍ စစ်ထုတ်နိုင်သည်။


တောင်းဆိုမှုတစ်ခုအပေါ် right click နှိပ်၍ အောက်ပါတို့ကိုဆောင်ရွက်နိုင်သည်-

* :guilabel:`Open URL` သည် URL အား ပုံမှန် browser ဖြင့်ဖွင့်ရာတွင် အသုံးပြုပါသည်။
* :guilabel:`Copy URL` ဖြင့် URL အား ကူးယူနိုင်သည်။
* :guilabel:`Copy As cURL` သည် ထို URL အား terminal တွင် အသုံးပြုရန် ကူးယူနိုင်သည်။
* :guilabel:`Copy as JSON` သည် ဖွဲ့စည်းမှုတန်ဖိုးများအား clipboard ထဲသို့ json string များအဖြစ် ကူးယူနိုင်ပြီး bug report(အမှားအစီရင်ခံစာ) များထဲတွင် လွယ်ကူစွာကူးထည့်ခြင်း သို့မဟုတ် အဝေးမှကူညီမှု (remote assistance) ပြုလုပ်ခြင်းအတွက် အသုံးပြုပါသည်။


.. figure:: img/network_logger.png
   :align: center

   GET တောင်းဆိုမှုအတွက် Network logger ၏ ရလာဒ်


Query Logger (Query ဆိုင်ရာ မှတ်တမ်းပြုလုပ်ပေးသည့်အရာ)
.......................................................

|dbManager| :guilabel:`Query Logger` သည် QGIS မှ တိုင်းတာထားသော လုပ်ဆောင်မှုကြာချိန် (execution time)နှင့်အတူ data provider မှ ပေးပို့သော SQL commands များနှင့် API နှင့် backend database ဆက်သွယ်မှုများကို မှတ်တမ်းပြုလုပ်နိုင်သော နေရာတစ်ခုဖြစ်ပါသည် (ဆိုလိုသည်မှာ command များကို ပေးပို့သော client ထဲတွင်ဖြစ်သည်)။ ၎င်းသည် QGIS algorithm သို့မဟုတ် plugin တစ်ခု၏တိုးတက်မှု သို့မဟုတ် အမှားရှာဖွေပြင်ဆင်နေစဉ် layer တစ်ခု၏ လုပ်ဆောင်မှုများကို စစ်ဆေးရာတွင် အသုံးဝင်ပါသည်။

၎င်း၏ အပေါ်ပိုင်းရှိ toolbar မှ တစ်ဆင့် အောက်ဖော်ပြပါလုပ်ငန်းများ ဆောင်ရွက်နိုင်ပါသည်-

* |record| :guilabel:`Record Log` သည် မှတ်တမ်းယူခြင်း (logging) ကို စတင်ရန် သို့မဟုတ် ရပ်တန့်ရန် အသုံးပြုနိုင်သည်။
* |deleteSelected| :guilabel:`Clear Log` သည် မှတ်တမ်းအား ရှင်းလင်းရန် အသုံးပြုနိုင်သည်။
* |fileSave| :guilabel:`Save Log...` ကိုနှိပ်လျှင် မှတ်တမ်းများကို လျှို့ဝှက်အနေဖြင့် ထားရှိသင့်ကြောင်း သတိပေးချက်အကြီးစားတစ်ခုကို ဦးစွာ ပြသမည်ဖြစ်ပြီး ထို့နောက်တွင် မှတ်တမ်းများကို သိမ်းဆည်းခွင့်ပြုမည်ဖြစ်ပါသည်။
* |search| :guilabel:`Filter queries` သည် query string subsets သို့မဟုတ် Provider အမျိုးအစား၊ စတင်သည့်အချိန်၊ initiator(စတင်သူ) ကဲ့သို့ အသေးစိတ်အချက်အလက်များ အပေါ်တွင် မူတည်၍ query များကို စစ်ထုတ်ပေးနိုင်ပါသည်။

တင်ပြ/ဝင်ရောက်လာသော query တစ်ခုပေါ်တွင် right click နှိပ်၍ အောက်ပါတို့ကို ဆောင်ရွက်နိုင်ပါသည်-

* :guilabel:`Copy SQL` - database ပေါ်တွင် QGIS မှ ခေါ်ထားသော SQL command ကို ကူးယူနိုင်ပါသည်။
* :guilabel:`Copy as JSON` သည် ဖွဲ့စည်းမှုတန်ဖိုးများအား clipboard ထဲသို့ json string များအဖြစ် ကူးယူနိုင်ပြီး bug report(အမှားအစီရင်ခံစာ) များထဲတွင် လွယ်ကူစွာကူးထည့်ခြင်း သို့မဟုတ် အဝေးမှကူညီမှု (remote assistance) ပြုလုပ်ခြင်းအတွက် အသုံးပြုပါသည်။


.. figure:: img/query_logger.png
   :align: center


   Query Logger ၏ ရလဒ်


Profiler
.........

|stopwatch| :guilabel:`Profiler` tab သည် အသုံးပြုသူက တောင်းဆိုထားသော လုပ်ဆောင်ချက်များတွင် ပါဝင်သည့် operation(လုပ်ဆောင်ချက်) တစ်ခုချင်းစီအတွက် ကြာချိန်ကို ဖော်ပြပေးပါသည်။ ပါဝင်သည့်အကြောင်းအရာပေါ်မူတည်၍ ထို operation များသည် ဖတ်ရှုခြင်း၊ menu ၊ မြေပုံမျက်နှာပြင်၊ သုံးဖက်မြင် မြေပုံဖန်တီးခြင်း၊ map layers ကိုးကားချက်များကို ပြင်ဆင်ခြင်းနှင့် တည်နေရာအမှတ်အသား (bookmark) နှင့် Layout (မြေပုံထုတ်ရန်အသင့်ပြင်အနေအထား)များ ထည့်သွင်းခြင်း စသည်တို့ဆိုင်ရာ setting များဖြစ်နိုင်ပါသည်။ ဤ tool သည် operation တစ်ခုချင်းစီ၏ လုပ်ဆောင်ချိန်နှေးကွေးမှုကို ဖြစ်စေသည့်အကြောင်းအရင်းများကို ဆန်းစစ်ရာတွင် အသုံးဝင်ပါသည်။


:guilabel:`Categories` ၏ drop-down menu မှ မူလပံ့ပိုးပေးထားသည့် လုပ်ဆောင်ချက်များအား ရွေးချယ်နိုင်သည်-

* QGIS :guilabel:`Startup` (QGIS စတင်ချိန်)
* :guilabel:`Project Load` (Project ထည့်သွင်းချိန်)


.. figure:: img/profiler.png
   :align: center

   QGIS စတင်ချိန်အတွက် Profiler

.. index:: Nesting projects, Embed layers and groups
.. _nesting_projects:


Embedding layers from external projects (ပြင်ပ project များမှ layer များကို ထည့်သွင်းခြင်း)
============================================================================================

တစ်ခါတစ်ရံတွင် အခြား project များမှ တူညီသော style ဖြင့် အချို့ layer များကို သိမ်းဆည်းလိုလျှင် ထို layer များအတွက် :ref:`default style (ပုံသေ style) <store_style>` တစ်ခုကို ဖန်တီးနိုင်သည် သို့မဟုတ် ၎င်းတို့ကို အခြား project မှ ထည့်သွင်းနိုင်ပါသည်။ ထိုသို့ပြုလုပ်ခြင်းအားဖြင့် အချိန်နှင့် အင်အားကို သက်သာစေနိုင်သည်။

ရှိပြီးသား project တစ်ခုမှ Layer များနှင့် အုပ်စုများကိုထည့်သွင်းခြင်းအားဖြင့် style များကို ပြင်ဆင်ရာတွင် ‌အောက်ပါအကျိုးကျေးဇူးများကို ရရှိနိုင်သည်-

* Layer အမျိုးအစားအားလုံး  (vector သို့မဟုတ် raster ၊ စက်ထဲတွင်ရှိသော Layer သို့မဟုတ် အွန်လိုင်းမှ Layer...) ကို ထည့်သွင်းနိုင်ပါသည်။ 
* အုပ်စုနှင့် Layer များကို ထည့်သွင်းခြင်းအားဖြင့် မတူညီသော project များတွင် "နောက်ခံ (background)" layer များကို တူညီသောဖွဲ့စည်းပုံဖြင့် ထားရှိနိုင်သည်။
* ထည့်သွင်းထားသော Layer များကို ပြင်ဆင်တည်းဖြတ်နေချိန်တွင် Project အားလုံးတွင် တသမတ်တည်းဖြစ်နေစေရန်အတွက် ၎င်းတို့၏ ဂုဏ်သတ္တိများဖြစ်သည့် သင်္ကေတဆိုင်ရာများ၊ အညွှန်းများ၊ ပုံစံများ၊ မူရင်းတန်ဖိုး (default values) နှင့် လုပ်ဆောင်ချက်(actions) တို့ကို ပြင်ဆင်ပြောင်းလဲ၍ မရပါ။ 
* မူရင်း project တွင် item များကို ပြင်ဆင်ပြောင်းလဲမှုများ ပြုလုပ်ပါက ၎င်းတို့ကို အသုံးပြုထားသည့် အခြား project အားလုံးတွင်လည်း အလိုအလျောက် ပြောင်းလဲသွားမည်ဖြစ်သည်။

အခြား project ဖိုင်များမှ အကြောင်းအရာများကို မိမိ project တွင် ထည့်လိုလျှင် :menuselection:`Layer --> Embed Layers and Groups` (Layer များနှင့် အုပ်စုများကို ထည့်သွင်းခြင်း) ကိုရွေးချယ်၍ ပြုလုပ်နိုင်ပါသည်- 

#. Project ကို ရှာဖွေရန်အတွက်  :guilabel:`...` button ကို နှိပ်ပါက Project နှင့်အတူ ၎င်းတွင် ပါဝင်သည့်အကြောင်းအရာများကို တွေ့မြင်နိုင်မည် ဖြစ်သည်။ (:numref:`figure_embed_dialog` တွင်ကြည့်ရှုနိုင်ပါသည်)
#. :kbd:`Ctrl` ( သို့မဟုတ် |osx| :kbd:`Cmd`) ကိုဖိထားပီး မိမိဆွဲထုတ်လိုသော Layer နှင့် အုပ်စုများကို နှိပ်ပါ။ 
#. :guilabel:`OK` ကိုနှိပ်ပါ။ 

ရွေးချယ်လိုက်သော Layer နှင့် အုပ်စုများသည် :guilabel:`Layers` panel တွင် ပေါ်လာမည်ဖြစ်ပြီး မြေပုံမျက်နှာပြင်တွင်လည်း မြင်တွေ့နိုင်မည်ဖြစ်သည်။ |indicatorEmbedded| icon သည် ထည့်သွင်းလိုက်သည့် Layer ၏အမည် ဘေးတွင် ပေါ်လာမည်ဖြစ်ပြီး ၎င်းပေါ်တွင် မောက်စ်ကိုတင်ကြည့်ပါက မူလ project ဖိုင်လမ်းကြောင်းကို ဖော်ပြပေးပါလိမ့်မည်။

.. _figure_embed_dialog:


.. figure:: img/embed_dialog.png
   :align: center

   Layer နှင့်အုပ်စုများကို ထည့်သွင်းရန် ရွေးချယ်ခြင်း


အခြား Layer များနည်းတူ ထည့်သွင်းလိုက်သော Layer အား project မှ ဖယ်ရှားလိုလျှင် ထို Layer ပေါ်တွင် right-click နှိပ်၍  |removeLayer| :sup:`Remove` ကိုနှိပ်၍ ဖယ်ရှားနိုင်သည်။ 

.. tip:: **ထည့်သွင်းလိုက်သော Layer တစ်ခု၏ ပုံဖော်ပြသခြင်းကိုပြောင်းလဲခြင်း**

 မူလ Project ရှိ Layer အား ပြင်ဆင်မှု မပြုလုပ်ဘဲ ထည့်သွင်းလိုက်သော Layer ၏ ပုံဖော်ပြသခြင်းကို ပြင်ဆင်ရန် မဖြစ်နိုင်ပါ။ သို့သော်လည်း ထို Layer ပေါ်တွင် right-click နှင့် :guilabel:`Duplicate`` ကို နှိပ်ပြီး ပုံစံတူ Layer တစ်ခုကို ပွားယူနိုင်သည်။ ထိုပုံတူပွားလိုက်သည့် Layer သည် မူလ Project နှင့် သက်ဆိုင်မှုမရှိတော့ပဲ မူလ Project တွင် ဖန်တီးထားသည့် Layer အတိုင်း ပြည့်စုံစွာပါဝင်နေပေလိမ့်မည်။ ထို့နောက် ထည့်သွင်းထားသည့် မူရင်း Layer အား စိတ်ချလက်ချ ဖယ်ရှားနိုင်ပြီဖြစ်သည်။


Interacting with features (Feature များနှင့် အပြန်အလှန်ဆောင်ရွက်ခြင်း)
=======================================================================

.. index::
   see: Select; Selection tools
   single: Selection tools; Select all
   single: Selection tools; Invert selection
   single: Selection tools; Select by expression
   single: Selection tools; Select by form
   single: Selection tools; Select by polygon
   single: Selection tools; Select by freehand
   single: Selection tools; Select by rectangle
   single: Selection tools; Select by radius
   pair: Select; Deselect


.. _`sec_selection`:

Selecting features (Feature များရွေးချယ်ခြင်း)
-----------------------------------------------

QGIS သည် မြေပုံမျက်နှာပြင်တွင် feature များကို ရွေးချယ်ရန် tool များစွာကို ပံ့ပိုးပေးထားသည်။ Selection tool များကို :menuselection:`Edit --> Select` menu ထဲတွင် သို့မဟုတ် :guilabel:`Selection Toolbar` ထဲတွင် ရရှိနိုင်ပါသည်။


.. note::
   Selection tools (ရွေးချယ်ခြင်းပြုလုပ်သည့်ကိရိယာများ) များသည် Project တွင် လက်ရှိလုပ်ဆောင်လျက်ရှိသော Layer တွင်သာ အသုံးပြုနိုင်သည်။


Selecting manually on the map canvas (မြေပုံမျက်နှာပြင်ပေါ်တွင် ကိုယ်တိုင်ရွေးချယ်ခြင်း)
.........................................................................................

မောက်စ်ကိုအသုံးပြု၍ feature တစ်ခု သို့မဟုတ် တစ်ခုထက်ပို၍ ရွေးချယ်ရန် အောက်တွင်ဖော်ပြထားသော tool များကို အသုံးပြုနိုင်ပါသည်-

* |selectRectangle| :sup:`Select Features by area or single click` (ဧရိယာဖြင့် feature များကိုရွေးချယ်ခြင်း သို့မဟုတ် click တစ်ချက်နှိပ်၍ ရွေးချယ်ခြင်း)
* |selectPolygon| :sup:`Select Features by Polygon` (Polygon ဖြင့် feature များကိုရွေးချယ်ခြင်း )
* |selectFreehand| :sup:`Select Features by Freehand` (လက်ဖြင့် စိတ်ကြိုက်ရေးဆွဲ၍ feature များကိုရွေးချယ်ခြင်း)
* |selectRadius| :sup:`Select Features by Radius` (အချင်းဝက်ဖြင့် feature များကို ရွေးချယ်ခြင်း)

.. note:: |selectPolygon| :sup:`Select Features by Polygon` (Polygon ဖြင့် feature များကိုရွေးချယ်ခြင်း ) အပြင် အခြား selection tool များသည် မြေပုံမျက်နှာပြင်ရှိ feature များကို click တစ်ချက်နှိပ်ရုံဖြင့် ရွေးချယ်နိုင်သည်။

.. note:: |selectPolygon| :sup:`Select Features by Polygon` tool သည် မည်သည့် Layer မှမဆို လက်ရှိအသုံးပြုနေသော Layer ထဲရှိ ထပ်နေသော features များကို ရွေးချယ်ရန် ရှိပြီးသား Polygon feature တစ်ခုကို အသုံးပြုနိုင်သည်။ Polygon ကို right-click နှိပ်၍ click နှိပ်ထားသော point ပါဝင်သည့် polygon များအားလုံးစာရင်းကို ပြသသော context menu မှ၎င်းကို ရွေးချယ်ပါ။ လက်ရှိအသုံးပြုနေသော layer မှ ထပ်နေသော feature များအားလုံးကို ရွေးချယ်ပြီးဖြစ်နေပါလိမ့်မည်။

.. tip:: နောက်ဆုံးပြုလုပ်ထားသော ရွေးချယ်မှုကို :menuselection:`Edit --> Select --> Reselect Features` မှတဆင့် ပြန်ခေါ်နိုင်သဖြင့် ရွေးချယ်မှုပြုလုပ်နေစဉ် မတော်တဆအခြားတစ်နေရာရာအား နှိပ်မိသဖြင့် select ပြုလုပ်ထားသည်များ ပျောက်သွားသောအခါမျိုးတွင် ဤ tool သည် အလွန်အသုံးဝင်သည်။

|selectRectangle| :guilabel:`Select Feature(s)` tool ကို အသုံးပြု၍ ရွေးချယ်ပါက :kbd:`Shift` သို့မဟုတ် :kbd:`Ctrl` ကို နှိပ်ထားခြင်းဖြင့် feature တစ်ခုကို ရွေးချယ်ခြင်း သို့မဟုတ် ရွေးချယ်မှုပယ်ဖျက်ခြင်းကို ဆောင်ရွက်နိုင်သည်။ (လက်ရှိရွေးချယ်မှုထဲသို့ ထပ်ပေါင်းထည့်ခြင်း သို့မဟုတ် ရွေးချယ်မှုထဲမှ ဖယ်ရှားခြင်းများဆောင်ရွက်နိုင်သည်။)

အခြား tool များအတွက်လည်း အောက်ဖော်ပြပါများကို ဖိနှိပ်ထားခြင်းဖြင့် မတူညီသောအပြုအမူများကို လုပ်ဆောင်နိုင်ပါသည်-

* :kbd:`Shift`- လက်ရှိပြုလုပ်ထားသောရွေးချယ်မှုထဲသို့ feature များကို ထပ်ပေါင်းထည့်ရာတွင် သုံးသည်။
* :kbd:`Ctrl`- လက်ရှိပြုလုပ်ထားသောရွေးချယ်မှုမှ feature များကို ဖယ်ထုတ်ရာတွင် သုံးသည်။
* :kbd:`Ctrl+Shift`- လက်ရှိပြုလုပ်ထားသောရွေးချယ်မှုနှင့် ထပ်နေသော feature များကို သိလိုလျှင် သုံးသည်။ ဆိုလိုသည်မှာ လက်ရှိရွေးချယ်မှုနှင့် ထပ်နေသော feature များကိုသာ ဖော်ပြမည်ဖြစ်သည်။
* :kbd:`Alt`- ရွေးချယ်မှုပြုလုပ်သည့် ဧရိယာအတွင်း လုံးဝကျရောက်သော feature များကိုသာ ရွေးချယ်ပေးသည်။ :kbd:`Shift` သို့မဟုတ် :kbd:`Ctrl` ကီးများဖြင့် တွဲသုံးပါက လက်ရှိပြုလုပ်ထားသောရွေးချယ်မှုထဲသို့ feature အသစ်များ ထပ်ပေါင်းထည့်ခြင်း သို့မဟုတ် လက်ရှိပြုလုပ်ထားသောရွေးချယ်မှုထဲမှ feature များဖယ်ရှားခြင်းကို ပြုလုပ်နိုင်သည်။


.. _automatic_selection:

Automatic selection (အလိုအလျောက်ရွေးချယ်ခြင်း)
...............................................

အခြား selection tool များသည် :ref:`Attribute table <sec_attribute_table>` တွင် ပြုလုပ်နိုင်သော tool များဖြစ်ပြီး feature ၏ attribute (အချက်အလက်) သို့မဟုတ် ၎င်း၏ရွေးချယ်ထားမှုအခြေအနေ ပေါ်မူတည်၍ ရွေးချယ်မှုပြုလုပ်နိုင်သည်။ (အချက်အလက်ဇယား (attribute table) နှင့် မြေပုံမျက်နှာပြင်သည် တူညီသော အချက်အလက်များကိုသာ ဖော်ပြသည့်အတွက် အချက်အလက်ဇယားရှိ feature တစ်ခုကိုရွေးချယ်လိုက်လျှင် မြေပုံမျက်နှာပြင်ပေါ်တွင်လည်း ရွေးချယ်ပြီးသား ဖြစ်နေပါလိမ့်မည်)- 

* |expressionSelect| :sup:`Select By Expression...` (Expression (ခိုင်းစေချက်) ဖြင့် ရွေးချယ်ခြင်း) သည် expression dialog(ခိုင်းစေချက်ရေးသားနိုင်သည့် dialog) ကို အသုံးပြုပြီး feature များကို ရွေးချယ်နိုင်သည်။ 
* |formSelect| :sup:`Select Features By Value...` (တန်ဖိုးအလိုက် feature များကို ရွေးချယ်ခြင်း) သို့မဟုတ် :kbd:`F3` ကိုနှိပ်၍ feature များကို ၎င်းတို့၏တန်ဖိုး အလိုက် ရွေးချယ်နိုင်သည်။
* |deselectAll| :sup:`Deselect Features from All Layers` (Layer အားလုံးမှ feature များကိုရွေးချယ်မှုမှ ပယ်ဖျက်ခြင်း) သို့မဟုတ် :kbd:`Ctrl+Alt+A` ကို နှိပ်၍ Layer အားလုံးတွင် ရွေးချယ်ထားသည့် feature များကို ရွေးချယ်မှုမှ ပယ်ဖျက်နိုင်သည်။
* |deselectActiveLayer| :sup:`Deselect Features from the Current Active Layer` (လက်ရှိအသုံးပြုနေသော Layer မှ feature များကို ရွေးချယ်မှုမှပယ်ဖျက်ခြင်း) သို့မဟုတ် :kbd:`Ctrl+Shift+A` ကိုနှိပ်၍ လက်ရှိအသုံးပြုနေသော Layer မှ ရွေးချယ်ထားသည့် feature များကို ရွေးချယ်မှုမှ ပယ်ဖျက်နိုင်သည်။
* |selectAll| :sup:`Select All Features` (Feature များအားလုံးကို‌ရွေးချယ်ခြင်း) သို့မဟုတ် :kbd:`Ctrl+A` ကို နှိပ်၍ လက်ရှိအသုံးပြုနေသော Layer ရှိ feature အားလုံးကို ရွေးချယ်နိုင်သည်။
* |invertSelection| :sup:`Invert Feature Selection` (ရွေးချယ်ထားသည့် feature များကို ပြောင်းပြန်ရွေးချယ်ခြင်း) သည် လက်ရှိအသုံးပြုနေသော Layer ရှိ ရွေးချယ်ထားသည့် feature များမဟုတ်သည့် feature များကိုပြောင်းလဲရွေးချယ်ရန် အသုံးပြုနိုင်သည်။
* |selectLocation| :sup:`Select by Location` (တည်နေရာဖြင့် ရွေးချယ်ခြင်း) သည် အခြား feature များနှင့် တည်နေရာဆက်စပ်မှုပေါ်မူတည်၍ feature များကို ရွေးချယ်ရာတွင် အသုံးပြုသည်။ (တူညီသော Layer သို့မဟုတ် အခြား Layer တစ်ခုတွင် - :ref:`qgisselectbylocation` တွင် ကြည့်ရှုနိုင်ပါသည်။)
* |selectDistance| :sup:`Select within distance` (အကွာအဝေးတစ်ခုအတွင်း ရွေးချယ်ခြင်း) သည် ရည်ညွှန်းလိုသော feature မှ သတ်မှတ်ထားသည့် အများဆုံးအကွာအဝေးအတွင်းရှိ feature များကို ရွေးချယ်ရန် အသုံးပြုနိင်ပါသည်။ (:ref:`qgisselectwithindistance` တွင် ကြည့်ရှုနိုင်ပါသည်။)

ဥပမာအားဖြင့် QGIS sample data ၏ :file:`regions.shp` မှ 'Borough' ဖြစ်သည့် ဒေသများကို ရှာဖွေလိုလျှင် အောက်ဖော်ပြပါ အဆင့်များအတိုင်း လုပ်ဆောင်နိုင်သည်-

#. |expressionSelect| :sup:`Select features using an Expression` (expression ဖြင့် feature များကိုရွေးချယ်ခြင်း) icon ကို အသုံးပြုပါ။
#. :guilabel:`Fields and Values` အုပ်စုကို အကျယ်ဖြန့်ကြည့်ပါ။
#. Query ပြုလုပ်လိုသော field ("TYPE_2")  ကို click နှစ်ချက်နှိပ်ပါ။ 
#. ညာဘက်တွင် ပေါ်လာသည့် Panel ထဲတွင် :guilabel:`All Unique` ကို နှိပ်ပါ။ 
#. List ထဲမှ 'Borough' ကို double-click နှိပ်၍ :guilabel:`Expression` editor field ထဲတွင် အောက်ပါ query ကို ရိုက်ထည့်ပါ- ::

    "TYPE_2"  =  'Borough'

#. :guilabel:`Select Features` (Feature များရွေးချယ်ပါ) ကိုနှိပ်ပါ။ 

အသုံးပြုခဲ့ပြီးသော ရွေးချယ်မှုတစ်ခုကို ပြန်လည်အသုံးပြုရန် expression builder dialog ရှိ  :menuselection:`Function list --> Recent (Selection)` ကို အသုံးပြုနိုင်သည်။ Expression builder dialog သည် နောက်ဆုံးအသုံးပြုခဲ့ပြီးသော expressions ပေါင်း (၂၀) ကို မှတ်သားထားမည်ဖြစ်သည်။ နောက်ထပ်အချက်အလက်များနှင့်ဥပမာများကို ပိုမိုသိရှိလိုပါက :ref:`vector_expressions` တွင် ထပ်မံလေ့လာနိုင်ပါသည်။ 


.. tip:: **ရွေးချယ်မှုအား ဖိုင်အသစ်တစ်ခုအဖြစ်သိမ်းဆည်းခြင်း**

   အသုံးပြုသူများသည် ရွေးချယ်မှုပြုလုပ်ထားသည့် feature များကို **New Temporary Scratch Layer** (ယာယီအကြမ်း layer) အဖြစ် သိမ်းဆည်နိုင်သလို :menuselection:`Edit --> Copy Features`(Feature များကို ကူးယူခြင်း) နှင့် :menuselection:`Edit --> Paste Features as` (Feature များကို ကူးချခြင်း) တို့ကိုသုံး၍ **New Vector Layer** အဖြစ် မိမိလိုချင်သည့်ပုံစံဖြင့် သိမ်းဆည်းထားနိုင်ပါသည်။ 


.. index::
   single: Selection tools; Select by value


.. _select_by_value:


Select Features By Value (တန်ဖိုးအလိုက် feature များကို ရွေးချယ်ခြင်း)
.......................................................................

ဤ Selection tool ကို နှိပ်လိုက်ပါက Layer ၏ feature form ပွင့်လာပြီး field တစ်ခုချင်းစီအတွက် ရှာဖွေမည့် တန်ဖိုး၊ စာလုံးအကြီးအသေးကိုဂရုပြုသော ရှာဖွေမှု (case-sensitive) အသုံးပြု/မပြု နှင့် Operators (=, >, <,...) များအသုံးပြု/မပြု တို့ကို ရွေးချယ်နိုင်သည်။ ထို့အပြင် ဤ tool သည် ရှိပြီးသား တန်ဖိုးများကိုလည်း search box (ရှာဖွေမှု) တွင် အလိုအလျောက်ဖြည့်ပေးနိုင်သည်။


.. _figure_filter_form:


.. figure:: img/select_by_value.png
   :align: center

   Form dialog ဖြင့် feature များကို စစ်ထုတ်ခြင်း/ရွေးချယ်ခြင်း


Field တစ်ခုချင်းစီတွင် ပုံစံအမျိုးမျိုးဖြင့် ရှာဖွေနိုင်ရန် drop-down list တစ်ခုစီရှိသည်- 


.. list-table:: ဒေတာအမျိုးအစားတစ်ခုစီအလိုက် အသုံးပြုနိုင်သည့် Query opeartor များ
   :header-rows: 1
   :widths: 40 15 15 15
   :class: longtable

   * - Field ရှာဖွေမှုရွေးချယ်စရာ
     - String
     - Numeric
     - Date
   * - ရှာဖွေမှုမှ :guilabel:`Exclude Field` (Field ကို ဖယ်ထားခြင်း)
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Equal to (=)` (ညီမျှသော)
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Not equal to (≠)` (မညီမျှသော)
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Greater than (>)` (..ထက်ကြီးသော)
     -
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Less than (<)` (..ထက်ငယ်သော)
     -
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Greater than or equal to (≥)` (..နှင့်ညီသော သို့မဟုတ် ၎င်းထက်ကြီးသော)
     -
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Less than or equal to (≤)` (..နှင့်ညီသော သို့မဟုတ် ၎င်းထက်ငယ်သော)
     -
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Between (inclusive)` (နှစ်ခုကြားထဲရှိသော (၎င်းအပါအဝင်))
     -
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Not between (inclusive)` (နှစ်ခုကြားထဲမရှိသော (၎င်းအပါအဝင်))
     -
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Contains` (အထဲတွင် ပါဝင်သော)
     - |checkbox|
     -
     -
   * - :guilabel:`Does not contain` (အထဲတွင် မပါဝင်သော)
     - |checkbox|
     -
     -
   * - :guilabel:`Is missing (null)` (ပျောက်နေသော (null))
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Is not missing (not null)` (မပျောက်နေသော (null မဟုတ်သော))
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Starts with` (..ဖြင့် စတင်သော)
     - |checkbox|
     -
     -
   * - :guilabel:`Ends with`  (..ဖြင့် အဆုံးသတ်သော)
     - |checkbox|
     -
     -


String (စာသား) များကိုနှိုင်းယှဉ်ရန် |checkbox|:guilabel:`Case sensitive` (စာလုံးအကြီးအသေးကိုဂရုပြုခြင်း) ကိုအသုံးပြု၍လည်း ရှာဖွေနိုင်သည်။

ရှာဖွေနိုင်သည့် ရွေးချယ်စရာအမျိုးမျိုးကို ရွေးချယ်သတ်မှတ်ပြီးနောက် ကိုက်ညီသည့် feature များကို ရွေးချယ်ရန် :guilabel:`Select features` ကို နှိပ်ပါ။ ၎င်းတွင် အောက်ဖော်ပြပါ drop-down ရွေးချယ်စရာများကိုတွေ့မြင်နိုင်သည်- 

* :guilabel:`Select features` (Feature များရွေးချယ်ခြင်း)
* :guilabel:`Add to current selection` (လက်ရှိရွေးချယ်မှုတွင် ထပ်ပေါင်းထည့်ခြင်း)
* :guilabel:`Remove from current selection` (လက်ရှိရွေးချယ်မှုမှ ဖယ်ရှားခြင်း)
* :guilabel:`Filter current selection` (လက်ရှိရွေးချယ်မှုကို စစ်ထုတ်ခြင်း)

:guilabel:`Reset form` (မူလပုံစံအဖြစ်ပြန်လည်ပြောင်းခြင်း) ခလုတ်ကို အသုံးပြု၍ ရှာဖွေခြင်းဆိုင်ရာ ရွေးချယ်စရာအားလုံးကို ဖယ်ရှားနိုင်သည်။ 

ရှာဖွေလိုသည့်အခြေအနေများကို သတ်မှတ်ပြီးနောက် အောက်ပါတို့ကိုလည်း လုပ်ဆောင်နိုင်ပါသည်-

* :guilabel:`Zoom to features` (feature များကို zoom ဆွဲကြည့်ခြင်း) သည် feature ကို ကြိုတင်ရွေးချယ်ရန်မလိုဘဲ မြေပုံမျက်နှာပြင်တွင် feature များကို zoom ဆွဲကြည့်နိုင်သည်။

* :guilabel:`Flash features` (Feature များကို လျှပ်တပြက်ပြသခြင်း) သည် ကိုက်ညီသည့် feature များကို highlight(အရောင်ဖြင့်ထင်ရှားအောင်ပြသခြင်း) ပြုလုပ်ပေးပြီး Identify tool သို့မဟုတ် Selection ပြုလုပ်စရာမလိုဘဲ feature တစ်ခုကို အလွယ်တကူ ဖော်ပြပေးနိုင်သည့် နည်းလမ်းတစ်ခုဖြစ်ပါသည်။ သို့သော် flash feature သည် လက်ရှိအသုံးပြုနေသော မြေပုံမျက်နှာပြင်၏ extent (ပမာဏ) ကို ပြောင်းလဲနိုင်ခြင်း မရှိသည့်အတွက် အကယ်၍ feature သည် မြေပုံမျက်နှာပြင်၏ ဧရိယာပြင်ပတွင် ရောက်နေပါက မြင်နိုင်မည်မဟုတ်ပေ။


.. index::
   single: Identify features
.. _`identify`:

Identifying Features (Feature များကို ဖော်ထုတ်ပြသခြင်း)
--------------------------------------------------------

Identify tool သည် မြေပုံမျက်နှာပြင်တွင် ဖော်ပြထားသည့် feature များနှင့် ပတ်သက်သည့် အချက်အလက်များကို Pop-up window ဖြင့် ဖော်ထုတ်ပြသပါသည်။ Feature များကို ဖော်ထုတ်ပြသရန် အောက်ပါနည်းလမ်းများကို အသုံးပြုနိုင်သည်-

* :menuselection:`View --> Identify Features`
* :kbd:`Ctrl+Shift+I` (သို့မဟုတ် |osx| :kbd:`Cmd+Shift+I`)
* Attributes toolbar ပေါ်ရှိ |identify| :sup:`Identify Features` icon


Using the Identify Features tool (Identify Features tool ကို အသုံးပြုခြင်း)
............................................................................

QGIS တွင် |identify| :sup:`Identify Features` tool ကိုသုံး၍ feature များကို ဖော်ထုတ်ပြသရန် နည်းလမ်းများစွာ ရှိပါသည်-

* **left click** သည် :guilabel:`Identify Results` (ဖော်ထုတ်ပြသခြင်းရလာဒ်) panel ထဲတွင်သတ်မှတ်ထားသော :ref:`selection mode (ရွေးချယ်ခြင်းနည်းလမ်း) <identify_mode>` နှင့် :ref:`selection mask (ရွေးချယ်ခြင်းအဖုံးအကာ) <identify_selection>` များအရ feature များကို ဖော်ထုတ်ပြသပေးပါသည်။
* :guilabel:`Identify Results` Panel ထဲတွင်သတ်မှတ်ထားသော :ref:`selection mode <identify_mode>` အတိုင်း :guilabel:`Identify Feature(s)` ကိုသုံး၍ **right click** နှိပ်ခြင်းဖြင့် မြေပုံမျက်နှာပြင်ရှိ မြင်နိုင်သော layer များအားလုံးမှ ထိကပ်နေသော feature များအားလုံးကို ရယူပေးပါသည်။ Feature များကို ပိုမိုတိကျစွာ ဖော်ထုတ်ပြသနိုင်ရန် သို့မဟုတ် ၎င်းတို့ပေါ်တွင် ဆက်လက်လုပ်ဆောင်နိုင်မည့် လုပ်ဆောင်ချက်ကို ရွေးချယ်နိုင်မည့် context menu တစ်ခု ပွင့်လာမည်ဖြစ်သည်။
* :guilabel:`Identify Results` Panel ထဲတွင်သတ်မှတ်ထားသော :ref:`selection mode <identify_mode>` အတိုင်း  :guilabel:`Identify Features by Polygon` (Polygon ဖြင့် feature ဖော်ထုတ်ပြသခြင်း) ကိုသုံး၍ **right click** နှိပ်ခြင်းဖြင့် :guilabel:`Identify Results` panel ထဲတွင်သတ်မှတ်ထားသော :ref:`selection mask <identify_selection>` အရ ရွေးချယ်ထားသည့် ရှိပြီးသား Polygon နှင့်ထပ်နေသော feature များကို ဖော်ထုတ်ပြသပေးမည်ဖြစ်သည်။

.. tip:: **Identify Features tool ကိုသုံး၍ Layer များကို စစ်ထုတ်ကြည့်ရှုခြင်း**

    :menuselection:`Project --> Properties...--> Data Sources` ရှိ :guilabel:`Layer Capabilities` (Layer ၏လုပ်ဆောင်နိုင်စွမ်းများ) အောက်တွင် Layer နှင့်ကပ်လျက်တွင်ရှိသော :guilabel:`Identifiable` column တွင် အမှန်ခြစ်ဖြုတ်ခြင်းဖြင့် **လက်ရှိအသုံးပြုနေသော Layer** မှအပ အခြား Layer များတွင် |identify| :sup:`Identify Features` tool ကို အသုံးပြုသောအခါ စစ်ထုတ်ကြည့်ရှုခြင်းမရှိစေရန် ဆောင်ရွက်ပေးသည်။ ၎င်းသည် မိမိစိတ်ဝင်စားသော Layer မှ features များကိုသာ ထုတ်ပေးရန် လွယ်ကူသော နည်းလမ်းဖြစ်သည်။

Feature (များ) ပေါ်တွင် click နှိပ်လိုက်လျှင် :guilabel:`Identify Results` (ဖော်ထုတ်ပြသခြင်းရလာဒ်) dialog တွင် click ပြုလုပ်ထားသော feature နှင့်သက်ဆိုင်သည့် အချက်အလက်များကို ဖော်ပြပေးပါလိမ့်မည်။ ပုံမှန်မြင်တွေ့ရသည့် ပုံစံမှာ ဖွဲ့စည်းမှုပုံစံ (tree view) ဖြစ်ပြီး ပထမဦးဆုံး item သည် Layer ၏ အမည်ဖြစ်ပြီး ‌အောက်ရှိအခွဲများသည် ၎င်းနှင့်ပတ်သက်သည့်အချက်အလက်များဖြစ်သည်။ Feature တစ်ခုချင်းစီကို တန်ဖိုးနှင့်အတူ Field ၏အမည်ဖြင့် ဖော်ပြနေမည်ဖြစ်ပြီး ထို field သည် :menuselection:`Layer Properties --> Display` တွင် သတ်မှတ်ထားသည့်အတိုင်း ဖြစ်သည်။ Feature နှင့်ပတ်သက်သည့် အခြားသော အချက်အလက်များကို အောက်တွင် ဆက်လက်ကြည့်ရှုနိုင်သည်။


Feature information (Feature နှင့်ပတ်သက်သည့်အချက်အလက်များ)
...........................................................

Identify Results dialog တွင် လိုချင်သည့် field များကို ပြသရန် စိတ်ကြိုက်ပြင်ဆင်နိုင်သော်လည်း ပုံမှန်အားဖြင့်မူ အောက်ဖော်ပြပါ အချက်အလက်များကို ပြသမည်ဖြစ်သည်- 

.. index:: Actions

* Feature :ref:`display name (အမည်ဖော်ပြခြင်း) <maptips>`

* **Actions** - Identify feature window တွင် လုပ်ဆောင်ချက်များကို ထပ်ထည့်နိုင်သည်။ လုပ်ဆောင်ချက်အညွှန်း (Action label)ပေါ်တွင် click နှိပ်ခြင်းအားဖြင့် အဆိုပါလုပ်‌ဆောင်ချက်ကို ဆောင်ရွက်နိုင်သည်။ ပုံမှန်အားဖြင့် ပြင်ဆင်တည်းဖြတ်ရန်အတွက် ``View feature form`` ဟု ခေါ်သော လုပ်ဆောင်ချက်တစ်ခုကိုသာလျှင် ပြုလုပ်နိုင်သော်လည်း Layer's properties dialog (Layer ဂုဏ်သတ္တိများ dialog) တွင် နောက်ထပ်လုပ်ဆောင်ချက်များကို ထပ်မံသတ်မှတ်နိုင်ပါသည်။ ( :ref:`actions_menu` တွင် ကြည့်ရှုနိုင်ပါသည်။)

* **Derived** - ဤအချက်အလက်ကို အခြားအချက်အလက်များမှ တွက်ယူ သို့မဟုတ် ထုတ်ယူရရှိထားပြီး ၎င်းတွင်အောက်ပါတို့ ပါဝင်ပါသည်-

  * Feature ၏ ဂျီဩမေတြီနှင့်သက်ဆိုင်သည့် ယေဘုယျအချက်အလက်များ-

     * ဂျီဩမေတြီ အမျိုးအစားပေါ်မူတည်၍ Layer ၏ CRS ယူနစ်ဖြင့် အလျား၊ ပတ်လည်အနား သို့မဟုတ် ဧရိယာများ၏ cartesian (ပြင်ညီ)အတိုင်းအတာများနှင့် 3D line vector များအတွက် cartesian (ပြင်ညီ) လိုင်းအလျားများ 
     * ဂျီဩမေတြီ အမျိုးအစားပေါ်မူတည်၍ project properties dialog (Project ဂုဏ်သတ္တိများ dialog) ရှိ :guilabel:`Measurements` (အတိုင်းအတာများ) အတွက် ellipsoid (ဘဲဥပုံစက်လုံး) ကို သတ်မှတ်ထားလိုက်လျှင် သတ်မှတ်ထားသည့် ယူနစ်များအသုံးပြုထားသည့် အလျား၊ ပတ်လည်အနား သို့မဟုတ် ဧရိယာများ၏ ellipsoidal တန်ဖိုးများ
     * Feature ထဲရှိ ဂျီဩမေတြီ အစိတ်အပိုင်းအရေအတွက်နှင့် click ပြုလုပ်ထားသည့် အစိတ်အပိုင်းများ၏ အရေအတွက် 
     * Feature ထဲရှိ မျဥ်းအဆစ် (vertix) များအရေအတွက်
  * ကိုဩဒိနိတ်အချက်အလက်များ။ Project properties :guilabel:`Coordinates display` (ကိုဩဒိနိတ်ပြသခြင်း) setting ကိုအသုံးပြု၍-

     * Click နှိပ်ထားသော point ၏ ``X`` နှင့်  ``Y`` ကိုဩဒိနိတ်တန်ဖိုးများ
     * Click နှိပ်ထားသော point နှင့် အနီးဆုံးမျဉ်းဆစ်အရေအတွက်
     * အနီးဆုံးမျဉ်းဆစ်၏ ``X`` နှင့်  ``Y`` ကိုဩဒိနိတ်တန်ဖိုးများ (အကယ်၍ ရရှိနိုင်ပါက  ``Z``/``M`` တန်ဖိုးများ)
     * ကွေးနေသော အပိုင်းတစ်ခု ပေါ်သို့ click နှိပ်လိုက်လျှင် ထိုအပိုင်း၏ အချင်းဝက်ကိုပါ ဖော်ပြထားမည်ဖြစ်သည်။

* **Data attributes** သည် Click ပြုလုပ်ထားသော feature ၏ attribute field (အချက်အလက်ဇယား) များနှင့် value များ၏စာရင်းဖြစ်သည်။

* အကယ်၍ :ref:`relation (ချိတ်ဆက်မှု) <vector_relations>` တစ်ခုကို သတ်မှတ်ထားလျှင် ထို feature ခွဲငယ်နှင့် သက်ဆိုင်သည့် အချက်အလက်များ-

  * ချိတ်ဆက်မှု၏အမည်
  * အကိုးအကား field ထဲရှိ entry (ဥပမာ- ချိတ်ဆက်ထားသည့် feature ခွဲငယ်၏ အမည်)
  * **Actions** သည် Layer's properties dialog ထဲတွင် သတ်မှတ်ထားသော လုပ်ဆောင်ချက်များကိုစာရင်းပြုစုထားပြီး ( :ref:`actions_menu` တွင် ကြည့်ရှုနိုင်သည်။) ပုံသေသတ်မှတ်ထားသော လုပ်ဆောင်ချက်မှာ ``View feature form`` ဖြစ်သည်။ 
  * **Data attributes** (ဒေတာအချက်အလက်) သည် ချိတ်ဆက်ထားသည့် feature ခွဲငယ်နှင့် သက်ဆိုင်သည့် attributes field နှင့် တန်ဖိုးများကို စာရင်းပြုလုပ်ထားခြင်းဖြစ်သည်။


.. note::  Feature ၏ attribute ရှိ လင့်ခ်များကို :guilabel:`Identify Results` panel တွင် click ပြုလုပ်နိုင်ပြီး မိမိ၏ မူရင်း browser တွင် ပွင့်လာမည်ဖြစ်ပါသည်။


.. _figure_identify:


.. figure:: img/identify_features.png
   :align: center


   ဖော်ထုတ်ပြသခြင်းရလာဒ် dialog

The Identify Results dialog (ဖော်ထုတ်ပြသခြင်းရလာဒ် dialog)
...........................................................

Window ၏ အပေါ်ပိုင်း၌ အောက်ပါ tool များကို တွေ့နိုင်ပါသည်- 

* လက်ရှိ Identify ပြုလုပ်ထားသည့် feature များ၏ form ကို |formView| :sup:`Open Form` ဖြင့် ဖွင့်နိုင်ပါသည်။ 
* |expandTree| :sup:`Expand tree` ဖြင့် ဖွဲ့စည်းပုံကို အကျယ်ဖြန့်ကြည့်နိုင်သည်။
* |collapseTree| :sup:`Collapse tree` ဖြင့် ဖွဲ့စည်းပုံကို ပြန်စုစည်းနိုင်သည်။
* |expandNewTree| :sup:`Expand New Results by Default` ဖြင့် နောက်ထပ် identify ပြုလုပ်မည့် feature ၏ အချက်အလက်များကို စုစည်းထားမည် သို့မဟုတ် အကျယ်ဖြန့်ထားမည် ကို သတ်မှတ်ထားနိုင်သည်။
* |deselectAll| :sup:`Clear Results` ဖြင့် identify ပြုလုပ်ထားသောရလာဒ်များကို ပယ်ဖျက်နိုင်သည်။
* |editCopy| :sup:`Copy selected feature to clipboard` ဖြင့် ရွေးချယ်ထားသည့် feature များကို clipboard တွင် ကူးယူနိုင်သည်။
* |filePrint| :sup:`Print selected HTML response` ဖြင့် ရွေးချယ်ထားသည့် feature ၏ HTML response ကို  print ထုတ်နိုင်ပါသည်။

.. _identify_selection:


* Identify ပြုလုပ်ရန်အတွက် feature များကို ဆွဲထုတ်ယူရန် အသုံးပြုနိုင်သည့် ရွေးချယ်ခြင်းနည်းလမ်းများ- 

  * |identifyByRectangle| :sup:`Identify Features by area or single click` ဖြင့် feature ကို ဧရိယာ သို့မဟုတ် click တစ်ချက်နှိပ်ခြင်းဖြင့် identify ပြုလုပ်နိုင်သည်။
  * |identifyByPolygon| :sup:`Identify Features by Polygon` ဖြင့် feature များကို Polygon ဖြင့် identify ပြုလုပ်နိုင်သည်။
  * |identifyByFreehand| :sup:`Identify Features by Freehand` ဖြင့် feature များကို လက်ဖြင့်စိတ်ကြိုက်ဝိုက်၍ identify ပြုလုပ်နိုင်သည်။
  * |identifyByRadius| :sup:`Identify Features by Radius` ဖြင့် feature များကို အချင်းဝက်တန်ဖိုးဖြင့် စက်ဝိုင်းသဏ္ဍာန်ဝိုက်၍ identify ပြုလုပ်နိုင်သည်။


  .. note::
         |identifyByPolygon| :sup:`Identify Features by Polygon` ကိုအသုံးပြုသောအခါ ရှိပြီးသားမည်သည့် polygon ကိုမဆို right-click နှိပ်၍ အခြား layer ရှိ ထပ်နေသော feature များကို identify ပြုလုပ်နိုင်သည်။


.. _identify_mode:

Window ၏ အောက်တွင် :guilabel:`Mode` နှင့် :guilabel:`View` combo boxes များကို တွေ့မြင်နိုင်ပြီး :guilabel:`Mode` သည် မည်သည့် Layer များ၏ feature များကို identify ပြုလုပ်သင့်သည်ဆိုသည်ကို သတ်မှတ်ပေးပါသည်- 

* **Current layer** သည် ရွေးချယ်ထားသော Layer များ၏ feature များကိုသာလျှင် identify ပြုလုပ်မည်ဖြစ်သည်။ အုပ်စုတစ်ခုကို ရွေးချယ်လျှင် ၎င်းအုပ်စုအတွင်းရှိ မြင်နိုင်သော Layer များမှ feature များကို identify ပြုလုပ်မည်ဖြစ်သည်။ အကယ်၍ ရွေးချယ်မှုမပြုလုပ်ထားလျှင် လက်ရှိအသုံးပြုနေသော Layer ကိုသာလျှင် identify ပြုလုပ်မည်ဖြစ်သည်။ 
* **Top down, stop at first** သည် အပေါ်ဆုံးတွင်ရှိသည့် မြင်နိုင်သော Layer မှ feature များကိုသာလျှင် identify ပြုလုပ်မည်ဖြစ်သည်။
* **Top down** သည် မြင်နိုင်သော Layer များမှ feature အားလုံးကို ပြုလုပ်နိုင်ပြီး Panel ထဲတွင် ရလာဒ်များကို ဖော်ပြမည်ဖြစ်သည်။ 
* **Layer selection** သည် feature များကို identify ပြုလုပ်မည့် layer ကို ရွေးချယ်နိုင်သော context menu ကိုပွင့်လာစေပြီး ၎င်းသည် right-click နှိပ်ခြင်းနှင့် ဆင်တူပါသည်။ ရွေးချယ်ထားသည့် feature များကိုသာလျှင် result panel တွင် ပြသပေးမည်ဖြစ်သည်။

:guilabel:`View` (မြင်ကွင်း) ကို **Tree (ဖွဲ့စည်းပုံ)**၊ **Table (ဇယား)** သို့မဟုတ် **Graph (ဂရပ်)** ပုံစံဖြင့် သတ်မှတ်နိုင်ပြီး 'Table'(ဇယား) နှင့် 'Graph'(ဂရပ်) မှာမူ raster layer များအတွက်သာ သတ်မှတ်နိုင်ပါသည်။ 

Identify tool ကို |options|:sup:`Identify Settings` အောက်တွင်တွေ့ရသည့် |checkbox|:guilabel:`Auto open form for single feature results` (feature ရလာဒ်တစ်ခုချင်းအတွက် ပုံစံကိုအလိုအလျောက်ဖွင့်ခြင်း) ကို အမှန်ခြစ်ခြစ်၍လည်း အသုံးပြုနိုင်ပြီး အကယ်၍ အမှန်ခြစ်ပြုလုပ်ထားပါက feature တစ်ခုကို identify သတ်မှတ်သည့်အကြိမ်တိုင်းတွင် ၎င်း feature ၏ attribute (အချက်အလက်) ကို ဖော်ပြသည့် ပုံစံ (form) တစ်ခု ပေါ်လာမည်ဖြစ်သည်။ ဤနည်းလမ်းသည် feature ၏  attribute များကို လျင်မြန်စွာ ပြင်ဆင်တည်းဖြတ်ရာတွင် အသုံးဝင်သော နည်းလမ်းတစ်ခုဖြစ်ပါသည်။

အခြားသောလုပ်ဆောင်ချက်များကို Identify ပြုလုပ်ထားသည့် item ၏ context menu တွင် တွေ့မြင်နိုင်သည်။ ဥပမာအားဖြင့် context menu မှ အောက်ဖော်ပြပါ လုပ်ဆောင်ချက်တို့ကို ဆောင်ရွက်နိုင်သည်-

* Feature form ကိုကြည့်ရှုခြင်း
* Feature ကို zoom ချဲ့ကြည့်ခြင်း
* Feature များ၏ ဂျီဩမေတြီ နှင့် attribute များ အားလုံးကို ကူးယူခြင်း
* Feature ရွေးချယ်ခြင်းကို အဖွင့်အပိတ်လုပ်ခြင်း၊ identify ပြုလုပ်ထားသည့် feature ကို ရွေးချယ်မှု (selection) သို့ ပေါင်းထည့်ခြင်းး
* Click ပြုလုပ်ထားသော attribute value (အချက်အလက်တန်ဖိုး)ကိုသာ ကူးယူခြင်း
* Feature ၏ attribute များကို ကူးယူခြင်း
* Attribute တန်ဖိုးများဖြင့် feature များကိုရွေးချယ်ခြင်း - ရွေးချယ်ထားသော attribute နှင့် ကိုက်ညီသည့် Layer ထဲရှိ feature အားလုံးကို ရွေးချယ်ခြင်း
* ရလာဒ်များကို ရှင်းလင်းခြင်း - Window ထဲမှ ရလာဒ်များကို ဖယ်ရှားခြင်း
* Highlight (အရောင်ဖြင့်ထင်ရှားအောင်ပြသထားသည်များ) များကို ရှင်းလင်းခြင်း - မြေပုံပေါ်ရှိ highlight ပြုလုပ်ထားသော feature များကို ဖယ်ရှားခြင်း
* အားလုံးကို Highlight ပြုလုပ်ခြင်း
* Layer ကို Highlight ပြုလုပ်ခြင်း
* Layer ကို အသက်သွင်းခြင်း - Layer တစ်ခုကို စတင်လုပ်ဆောင်စေရန် ရွေးချယ်ခြင်း
* Layer ၏ ဂုဏ်သတ္တိများ - Layer ၏ ဂုဏ်သတ္တိများ window ကို ဖွင့်ခြင်း
* အားလုံးကို အကျယ်ဖြန့်ခြင်း
* အားလုံးကို စုစည်းထားခြင်း


.. index:: Save properties, Save style, QML, SLD
.. _save_layer_property:


Save and Share Layer Properties (Layer Properties များကို သိမ်းဆည်းခြင်းနှင့် မျှဝေခြင်း)
==========================================================================================

.. _manage_custom_style:


Managing Custom Styles (စိတ်ကြိုက် style များ စီမံခန့်ခွဲခြင်း)
----------------------------------------------------------------

မြေပုံမျက်နှာပြင်တွင် vector layer တစ်ခုကို ထည့်သွင်းလိုက်သောအခါ QGIS သည် အဆိုပါ vector layer ၏ feature ကို ကျပန်းသင်္ကေတ/အရောင်များဖြင့် ပုံဖော်ပြသပါလိမ့်မည်။ သို့သော်လည်း :menuselection:`Project --> Properties... --> Default styles` ထဲတွင် အသစ်ထည့်သွင်းသော Layer ၏ ဂျီဩမေတြီ အမျိုးအစားအလိုက် အသုံးပြုမည့် ပုံသေသင်္ကေတ (default symbol) တစ်ခုကို သတ်မှတ်ပေးနိုင်ပါသည်။ 


.. any idea on how it works for raster?

များသောအားဖြင့် Layer များတွင် အလိုအလျောက် သို့မဟုတ် ကိုယ်တိုင်ရွေးချယ်အသုံးချစေမည့် ပိုမိုရှုပ်ထွေးပြီး စိတ်ကြိုက်ပြင်ဆင်ထားသော style များရှိနိုင်ပါသည်။ ၎င်းကို Layer Properties dialog အောက်ခြေရှိ
:menuselection:`Style` menu ကိုအသုံးပြု၍ လုပ်ဆောင်နိုင်ပါသည်။ ဤ menu တွင် style များ အသစ်ဖန်တီးခြင်း၊ ထည့်သွင်းခြင်း နှင့် စီမံခန့်ခွဲခြင်းများကို လုပ်ဆောင်နိုင်ပါသည်။

Vector layer များအတွက် (သင်္ကေတများ၊ အညွှန်း၊ field များ၊ form definition၊ လုပ်ဆောင်ချက်များနှင့် ရုပ်ပုံများပါဝင်သော) layer နှင့်အပြန်အလှန်ဆောင်ရွက်ရန် သို့မဟုတ် ပုံဖော်ပြသရန်အတွက် layer properties dialog ထဲတွင် သတ်မှတ်ထားသောမည်သည့်အချက်အလက်ကိုမဆို Style တစ်ခုတွင် သိမ်းဆည်းထားပါသည်။ Raster ဖိုင်များအတွက်မူ pixel (Band (ရောင်စဉ်) သို့မဟုတ် အရောင်ပုံဖော်ပြသခြင်းများ၊ ဖောက်ထွင်းမြင်နိုင်မှု၊ ပိရမစ်များနှင့် histogram များ စသည့်) သတင်းအချက်အလက်များကို သိမ်းဆည်းထားပါသည်။

.. _figure_manage_style:


.. figure:: img/style_combobox.png
   :align: center

   Vector layer style combo box ရှိ ရွေးချယ်စရာများ

ပုံမှန်အားဖြင့် ထည့်သွင်းထားသည့် Layer တွင် အသုံးပြုထားသော style ကို ``default`` ဟုအမည်ပေးပါသည်။ အကယ်၍ ထည့်သွင်းလိုက်သော Layer အတွက် သင့်လျော်သော စံ ပုံဖော်ပြသမှုရရှိသည်နှင့် |selectString| :menuselection:`Style` combo box ကို click နှိပ်ပြီး အောက်ပါတို့ကိုရွေးချယ်၍ သိမ်းဆည်းနိုင်ပါသည်- 


* **Rename Current** ကို အသုံးပြု၍ လက်ရှိပြင်ဆင်ထားသော style ကို အမည်ပြောင်းလဲနိုင်သည်။
* **Add** - လက်ရှိရွေးချယ်စရာ များကိုအသုံးပြု၍ style အသစ်တစ်ခု ဖန်တီးနိုင်ပြီး ပုံမှန်အားဖြင့် ၎င်းကို QGIS project ဖိုင်တွင် သိမ်းဆည်းထားမည်ဖြစ်သည်။ Style ကို အခြားဖိုင်တစ်ခု သို့မဟုတ် database တစ်ခုတွင် သိမ်းဆည်းရန် အောက်တွင် ကြည့်ရှုနိုင်ပါသည်။ 
* **Remove** ကို Layer တစ်ခုအတွက် သတ်မှတ်ထားသော style များစွာ ရှိနေပါက မလိုအပ်သော style ကို ဖျက်ရာတွင် အသုံးပြုနိုင်သည်။

Style drop-down list ၏အောက်ခြေတွင် Layer အတွက် လက်ရှိအသုံးပြုထားသော style ကို အမှန်ခြစ်ပုံစံဖြင့် မြင်တွေ့နိုင်ပါသည်။  

Layer properties dialog တွင် အတည်ပြုမှုများပြုလုပ်သည့်အခါတိုင်းတွင် လက်ရှိအသုံးပြုနေသော style သည် မိမိပြောင်းလဲထားသည့်အတိုင်း လိုက်၍ ပြောင်းလဲနေမည်ဖြစ်သည်။ 

Layer တစ်ခုအတွက် style များစွာ စိတ်ကြိုက်ဖန်တီးနိုင်သော်လည်း တစ်ကြိမ်တွင် style တစ်ခုကိုသာ အသုံးပြုနိုင်မည်ဖြစ်သည်။ :ref:`Map Themes <map_themes>` နှင့်ပေါင်းစပ်အသုံးပြုပါက မြေပုံရည်ညွှန်းချက်တွင် Layer များကို ထပ်မံကူးယူရန်/ ပွားရန် မလိုဘဲ ရှုပ်ထွေးသော project များအား ကိုင်တွယ်ရာတွင် ထိရောက်၍ လွယ်ကူမြန်ဆန်စွာ ဆောင်ရွက်နိုင်စေပါသည်။ 

.. note::
  Layer properties အား ပြောင်းလဲမှုပြုလုပ်သည့်အခါတိုင်း လက်ရှိအသုံးပြုနေသော style တွင် ပြောင်းလဲမှုများကို သိမ်းဆည်းထားမည်ဖြစ်ရာ :ref:`map theme <map_themes>` တွင် အသုံးပြုနေသော style ကို မှားယွင်း၍ပြောင်းလဲခြင်းများမဖြစ်စေရန် မှန်ကန်သော style တွင်သာ ပြင်ဆင်တည်းဖြတ်စေရန် သတိပြုရမည်ဖြစ်သည်။ 

.. tip:: **Layer context menu မှ style များကို စီမံခန့်ခွဲခြင်း**

   :guilabel:`Layers` panel ထဲရှိ Layer ကို Right-click နှိပ်၍ style များကို ကူးယူခြင်း၊ ပေါင်းထည့်ခြင်းနှင့် အမည်ပြောင်းလဲခြင်းများ ပြုလုပ်နိုင်ပါသည်။ 


.. _store_style:


Storing Styles in a File or a Database (ဖိုင်တစ်ခု သို့မဟုတ် Database တစ်ခုထဲတွင် style များကို သိမ်းဆည်းခြင်း)
----------------------------------------------------------------------------------------------------------------

:guilabel:`Style` combo box တွင် ဖန်တီးထားသော style များကို ပုံမှန်အားဖြင့် project ထဲတွင် သိမ်းဆည်းထားပြီး Layer တစ်ခုမှ တစ်ခုသို့ ကူးယူခြင်းများကို လုပ်ဆောင်နိုင်ပါသည်။ အခြား project တွင် ထည့်သွင်းအသုံးပြုနိုင်ရန်အလို့ငှာ project ပြင်ပတွင်လည်း သိမ်းဆည်းထားနိုင်သည်။ 

Save as text file (စာသားဖိုင် (text file) အဖြစ် သိမ်းဆည်းခြင်း)
................................................................

|selectString| :menuselection:`Style --> Save Style` ကို နှိပ်၍ style တစ်ခုကို- 

* QGIS layer style ဖိုင်ဖြစ်သော `.qml` ဖိုင်ပုံစံအဖြစ်လည်းကောင်း
* Vector layer များအတွက်သာ အသုံးပြုနိုင်သော `.sld` ဖိုင်ပုံစံအဖြစ်လည်းကောင်း သိမ်းဆည်းနိုင်ပါသည်။ 

:file:`.shp` ၊ :file:`.tab` ကဲ့သို့သော file-based (ဖိုင်အခြေခံ) ပုံစံအမျိုးအစား layer များတွင် အသုံးပြုသောအခါ  :guilabel:`Save as Default` (ပုံသေအတိုင်းသိမ်းဆည်းခြင်း) သည် layer အတွက် :file:`.qml` file (တူညီသော အမည်ဖြင့်) ထုတ်ပေးမည်ဖြစ်သည်။ SLD ဖိုင်အမျိုးအစားများကို single symbol ၊ categorized ၊ graduated or rule-based ကဲ့သို့သော မည်သည့် ပုံဖော်ပြသပေးသည့်အရာ (renderer) အမျိုးအစားများမှမဆို ပြောင်းလဲထုတ်ယူနိုင်သော်လည်း SLD ဖိုင်တစ်ခုကို ထည့်သွင်းရာတွင် single symbol သို့မဟုတ် rule-based တစ်မျိုးမျိုးအဖြစ်သာ ထည့်သွင်းနိုင်မည်ဖြစ်သည်။ ဆိုလိုသည်မှာ categorized နှင့် graduated renderer များကို rule-based renderer အဖြစ်သို့ ပြောင်းလဲရမည်ဖြစ်သည်။ အကယ်၍ ထို renderer များကို မပြောင်းလဲဘဲ မူရင်းပုံစံအတိုင်း ထိန်းသိမ်းထားလိုပါက QML ဖိုင်အမျိုးအစားကို အသုံးပြုရပါမည်။ သို့သော် style များကို rule-based အဖြစ်သို့ လွယ်ကူစွာ ပြောင်းလဲထုတ်ယူခြင်းသည် တခါတရံ အလွန်အဆင်ပြေစေနိုင်ပါသည်။


Save in database (Database တွင် သိမ်းဆည်းခြင်း)
................................................

Layer ၏ ဒေတာအရင်းအမြစ်သည် datasource provider ဖြစ်လျှင် Vector layer style များကို database တစ်ခုထဲတွင် သိမ်းဆည်းနိုင်ပါသည်။ အသုံးပြုနိုင်သည့် format များမှာ PostGIS၊ GeoPackage၊ SpatiaLite၊ MS SQL Server နှင့် Oracle တို့ဖြစ်ပါသည်။ Layer style ကို database ထဲတွင် :file:`layer_styles` ဟု ခေါ်သော ဇယားတစ်ခုအတွင်း၌ သိမ်းဆည်းထားပါသည်။ Style များကို database တွင် သိမ်းဆည်းရန် :menuselection:`Save Style... --> Save in database` ကိုနှိပ်ပါ။ ထို့နောက် style အမည်ပေး၍ ဖော်ပြချက် (description) တွင်လည်း style နှင့်ပတ်သက်သည့် ဖော်ပြချက်ကို ရေးပြီး အကယ်၍ ရရှိနိုင်ပါက :file:`.ui` file ကို ထည့်ပါ။ ပြီးလျှင် ထို style ကို မူရင်း style (default style) အဖြစ် အသုံးပြုရန် အမှန်ခြစ်ပါ။

Database တွင် ဇယားတစ်ခုတည်း၌ style များစွာကို သိမ်းဆည်းနိုင်ပါသည်။ သို့သော် ဇယားတစ်ခုတွင် မူရင်း style တစ်ခုသာလျှင် ရှိမည်ဖြစ်သည်။ Style များကို Layer database သို့မဟုတ် :ref:`user profile <user_profiles>` လမ်းကြောင်းရှိ SQLite database ဖြစ်သော `qgis.db` ဖိုင်ထဲတွင် သိမ်းဆည်းနိုင်ပါသည်။

.. _figure_save_style_database:


.. figure:: img/save_style_database.png
   :align: center

   Database dialog တွင် style ကိုသိမ်းဆည်းခြင်း

.. tip:: **Database များအကြား style ဖိုင်များမျှဝေခြင်း**

 Database တွင် style များကို သိမ်းဆည်းရာတွင် Layer သည် ထို database မှရရှိသော Layer ဖြစ်မှသာလျှင် သိမ်းဆည်းနိုင်မည်ဖြစ်သည်။ ထို့အပြင် database များကို ရောစပ် အသုံးပြု၍ မရပါ။ (ဥပမာ- Oracle တွင်ရှိသော Layer နှင့် MS SQL server တွင်ရှိသော style တို့သည် database မတူညီသောကြောင့် ရောစပ်၍ အသုံးမပြုနိုင်ပါ။) အကယ်၍ database များအကြား style ကို ဝေမျှအသုံးပြုလိုပါက plain text ဖိုင်ကို အသုံးပြုနိုင်ပါသည်။
 
.. note:: PostgreSQL database backup မှ :file:`layer_styles` ဇယားကို ပြန်လည်ရယူ (restore) ရာတွင် အခက်အခဲများ တွေ့ကြုံရပါက ဖြေရှင်းနိုင်ရန် :ref:`layer_style_backup` တွင် သွားရောက်လေ့လာနိုင်ပါသည်။


Load style (Style ထည့်သွင်းအသုံးပြုခြင်း)
..........................................

Layer တစ်ခုအတွက် မူရင်း style ကိုသတ်မှတ်ထားပြီးဖြစ်ပါက အဆိုပါ Layer ကို QGIS တွင် ထည့်သွင်းကြည့်လျှင် သတ်မှတ်ထားပြီးသော မူရင်း style ကိုပါ တွေ့မြင်ရမည်ဖြစ်ပါသည်။ :menuselection:`Style --> Restore Default` သို့ဝင်ရောက်၍လည်း မူရင်း style ကို ရှာဖွေပြီး လက်ရှိဖော်ပြနေသော style ကို အစားထိုးပြောင်းလဲနိုင်သည်။ 

:menuselection:`Style --> Load Style` သည် သိမ်းဆည်းထားသည့် မည်သည့် style ကိုမဆို Layer အတွင်းသို့ ထည့်သွင်းနိုင်ရန် ကူညီပေးနိုင်သည်။ Text ဖိုင်ဖြစ်သော style ဖိုင်များ :file:`.sld` သို့မဟုတ်  :file:`.qml` အမျိုးအစားများကို မည်သည့် Layer တွင်မဆို အသုံးပြုနိုင်သော်လည်း database တစ်ခုထဲတွင် သိမ်းဆည်းထားသော style များကိုမူ တူညီသော database မှ Layer ဖြစ်မှသာ သို့မဟုတ် style ကို QGIS local database ထဲတွင် သိမ်းဆည်းထားသောအခါမှသာ ထည့်သွင်းအသုံးပြုနိုင်မည်ဖြစ်ပါသည်။ 

:guilabel:`Database Styles Manager` dialog သည် database ထဲရှိ Layer နှင့် ဆက်စပ်လျက်ရှိသည့် style များစာရင်းနှင့် ၎င်းထဲတွင် သိမ်းဆည်းထားသော အခြား style များအားလုံးကို အမည်၊ ဖော်ပြချက်များနှင့်တွဲ၍ ပြသပေးမည် ဖြစ်သည်။ 

.. tip:: **Project တစ်ခုအတွင်း Layer style တစ်ခုကို လျှင်မြန်စွာ မျှဝေခြင်း**
  
   Project တစ်ခုအတွင်း ဖိုင် သို့မဟုတ် database style ကို ထည့်သွင်းခြင်းမပြုလုပ်ဘဲ Layer style များကို မျှဝေနိုင်ပါသည်။ :guilabel:`Layers Panel` ထဲရှိ Layer ပေါ်တွင် right-click နှိပ်ပြီး :guilabel:`Styles` combo box မှ Layer တစ်ခု၏ style ကို ကူးယူ၍ ရွေးချယ်ထားသော Layer များ သို့မဟုတ် Layer အုပ်စုတစ်ခုတွင် ကူးချလိုက်လျှင် style သည် မူလ layer အတိုင်း အမျိုးအစားတူညီသော (vector နှင့် raster) layer များအားလုံးတွင် အသုံးပြုသွားမည်ဖြစ်ပြီး vector layer များအတွက်မူ တူညီသော ဂျီဩမေတြီအမျိုးအစား (point ၊ line သို့မဟုတ် polygon) အတိုင်း ရှိနေမည်ဖြစ်သည်။ 


.. index:: Layer Definition File, qlr file
.. _layer_definition_file:


Layer definition file (Layer အဓိပ္ပါယ်ဖွင့်ဆိုချက်ဖိုင်)
---------------------------------------------------------

Layer Definition များကို လက်ရှိအသုံးပြုနေသော Layer များ၏ context menu ထဲရှိ :menuselection:`Export --> Save As Layer Definition File...` ကိုအသုံးပြု၍ ``Layer Definition File`` (:file:`.qlr`) အဖြစ် သိမ်းဆည်းနိုင်ပါသည်။ ``Layer Definition File`` ဖြစ်သော `.qlr` ဖိုင်ထဲတွင် Layer ၏ မူရင်းဒေတာအရင်းအမြစ်နှင့်ပတ်သက်သည့် အကိုးအကားများနှင့် ၎င်း၏ style များပါဝင်သည်။ :file:`.qlr` ဖိုင်များကို Browser Panel တွင် တွေ့မြင်နိုင်ပြီး Layers Panel သို့ Layer များကို (သိမ်းဆည်းထားသော style များနှင့်အတူ) ထည့်သွင်းရန် အသုံးပြုနိုင်ပါသည်။ ထို့အပြင် system file manager မှ :file:`.qlr` ဖိုင်များကို မြေပုံမျက်နှာပြင်ပေါ်သို့ တိုက်ရိုက်ဖိဆွဲယူ၍လည်း ထည့်သွင်းနိုင်သည်။


Documenting your data (Data များကို မှတ်တမ်းတင်ခြင်း)
======================================================

QGIS သည် Layer များထဲတွင်ရှိသော data များကို ပြသခြင်းနှင့် သင်္ကေတဖြင့်ဖော်ပြခြင်းတို့အပြင် အောက်ပါ data များကိုလည်း ဖြည့်စွက်ထည့်သွင်းနိုင်ရန် ပံ့ပိုးပေးထားပါသည်-


* **metadata** သည် ဒေတာအစု (dataset) များကို ရှာဖွေသိရှိနိုင်ရန်နှင့် မည်သို့ရယူအသုံးပြုရမည်ကို ကူညီပေးနိုင်သော အချက်အလက်ဖြစ်သည့်အပြင် ၎င်းတို့သည် data အရင်းအမြစ်များ၏ ဂုဏ်သတ္တိများဖြစ်ပြီး ၎င်းတို့ကို QGIS project ပြင်ပတွင်လည်း အသုံးပြုနိုင်သည်။ 
* **notes** သည် လက်ရှိ project ထဲရှိ Layer နှင့်သက်ဆိုင်သော ညွှန်ကြားချက်များနှင့် မှတ်ချက်များကို မှတ်သားနိုင်ရန် ကူညီပေးသည်။


.. index:: Metadata, Metadata editor, Keyword
.. _metadatamenu:

Metadata
---------

Layer properties dialog ထဲရှိ |editMetadata| :guilabel:`Metadata` tab သည် Layer နှင့်ပတ်သက်သည့် metadata report (အစီရင်ခံစာ) များကို ဖန်တီးနိုင်ရန်နှင့် ပြင်ဆင်ရန် အသုံးပြုနိုင်ပါသည်။ 

ထည့်သွင်းရန်အချက်အလက်များမှာ အောက်ပါအတိုင်းဖြစ်သည်-

* Data :guilabel:`Identification` (ဒေတာအမျိုးအမည်သတ်မှတ်ခြင်း) - dataset ၏ အခြေခံအချက်အလက် (မူရင်းဒေတာ(parent)၊ identifier (အမျိုးအမည်သတ်မှတ်သည့်အရာ)၊ title (ခေါင်းစဉ်)၊ abstract (အကျဉ်းချုပ်)၊ language (ဘာသာစကား)...) 
* Data နှင့်သက်ဆိုင်သည့် :guilabel:`Categories` (အမျိုးအစားများ)။ **ISO** categories အပြင် စိတ်ကြိုက်ဖန်တီးထားသော category များကိုလည်း ထည့်သွင်းနိုင်သည်။
* :guilabel:`Keywords` (အဓိကစကားလုံးများ) ကို ဝေါဟာရအပေါ် အခြေခံထားသည့် စံသတ်မှတ်ချက်အတိုင်း data များနှင့် သက်ဆိုင်ရာ သဘောတရားများကို ရယူရန် အသုံးပြုနိုင်ပါသည်။ 
* Dataset ကို ရယူသုံးစွဲနိုင်သည့် :guilabel:`Access` (လိုင်စင်၊ အခွင့်အရေး၊ အခကြေးငွေနှင့် ကန့်သတ်ချက်)
* Dataset ၏ :guilabel:`Extent` (နယ်နိမိတ်အတိုင်းအတာပမာဏ)- တည်နေရာနှင့်သက်ဆိုင်သော (spatial) (CRS ၊ မြေပုံ extent ၊ အမြင့်) extent သို့မဟုတ် အချိန်နှင့်သက်ဆိုင်သော (temporal) extent
* Dataset ၏ မူရင်းပိုင်ရှင် (များ) ဆက်သွယ်နိုင်ရန် :guilabel:`Contact` (အဆက်အသွယ်)
* ကူညီဖြည့်စွက်ပေးသည့် အရင်းအမြစ်များနှင့် ဆက်စပ်အချက်အလက်များသို့ ညွှန်းပေးမည့် :guilabel:`Links` (လင့်ခ်များ)
* Dataset ၏ :guilabel:`History` (မှတ်တမ်း)

:guilabel:`Validation` tab တွင် ဖြည့်သွင်းထားသောအချက်အလက်များ၏ အကျဉ်းချုပ်ကို သိရှိနိုင်ပြီး ၎င်းနှင့်သက်ဆိုင်သော ဖြစ်ပေါ်လာနိုင်သည့် ပြဿနာများကို သိရှိစေရန် ဖော်ပြပါသည်။ ထိုပြဿနာများကို ဖြေရှင်းခြင်းနှင့် မဖြေရှင်းလိုပါက လျစ်လျူရှုခြင်းတို့ကိုလည်း ပြုလုပ်နိုင်ပါသည်။ 

Metadata များကို Project အတွင်းတွင် default အနေဖြင့် သိမ်းဆည်းမည်ဖြစ်ပြီး :guilabel:`Metadata` drop-down တွင် Metadata ကို :file:`.qmd` file မှ ထည့်သွင်းအသုံးပြုခြင်း/သိမ်းဆည်းခြင်း နှင့် "Default" location တွင် ထည့်သွင်းအသုံးပြုခြင်း/သိမ်းဆည်းခြင်းများ ပြုလုပ်နိုင်သည်။ 

.. _figure_metadata_save_options:


.. figure:: img/metadata_save_options.png
   :align: center


   Metadata အား ထည့်သွင်း/သိမ်းဆည်းရန် ရွေးချယ်စရာများ

:guilabel:`Save as Default` နှင့် :guilabel:`Restore Default` တို့ဖြင့် ခေါ်ယူအသုံးပြုနိုင်သော "Default" location သည် data အရင်းအမြစ်နှင့် ၎င်း၏ အပြင်အဆင် (configuration) ပေါ်မူတည်၍ ပြောင်းလဲနိုင်ပါသည်-


.. _`savemetadatatodb`:

* PostgreSQL data အရင်းအမြစ်များအတွက် configuration option ဖြစ်သော :guilabel:`Allow saving/loading QGIS layer metadata in the database` (Database တွင် QGIS Layer ၏ metadata များကို သိမ်းဆည်းခြင်း/ထည့်သွင်းခြင်းတို့ကို ခွင့်ပြုခြင်း) တွင် အမှန်ခြစ်ပြုလုပ်ထားပါက database ထဲရှိ ဇယားတစ်ခုအတွင်းတွင် metadata များကို သိမ်းဆည်းထားမည်ဖြစ်သည်။

* GeoPackage data အရင်းအမြစ်များအတွက်မူ :guilabel:`Save as Default` အတိုင်း သိမ်းဆည်းပါက metadata များကို GeoPackage ၏ အတွင်းပိုင်း metadata ဇယားတွင် အမြဲသိမ်းဆည်းထားမည်ဖြစ်သည်။ 

  Metadata များကို PostgreSQL သို့မဟုတ် GeoPackage ၏ အတွင်းပိုင်းဇယားများတွင် သိမ်းဆည်းထားသောအခါ အဆိုပါ metadata များကို :ref:`layer metadata search panel <layer_metadata_search_panel>` ထဲနှင့် browser ထဲတွင် ရှာဖွေခြင်းနှင့် စစ်ထုတ်ခြင်းများကို ပြုလုပ်နိုင်ပါသည်။

* Data အရင်းအမြစ်များပေါ် အခြေခံထားသည့် အခြားဖိုင်အားလုံးအတွက်မူ metadata များကို :guilabel:`Save as Default` အတိုင်း သိမ်းဆည်းပါက :file:`.qmd` ဖိုင်ပုံစံဖြင့် သိမ်းဆည်းသွားမည်ဖြစ်သည်။

* အခြားအခြေအနေများအတွက်မူ Metadata များကို :guilabel:`Save as Default` ဖြင့် သိမ်းဆည်းပါက ကွန်ပျူတာရှိ :file:`.sqlite` database တွင် သိမ်းဆည်းသွားမည်ဖြစ်သည်။


.. _layer_notes:

Layer notes (Layer မှတ်စုများ)
-------------------------------

Layer မှတ်စုများသည် လက်ရှိအသုံးပြုနေသော project အတွင်းရှိ Layer နှင့်ပတ်သက်သော အကြောင်းအရာများကို မှတ်တမ်းတင်ရာတွင် အသုံးပြုပါသည်။ ၎င်းတို့တွင် Project ကို အသုံးပြုသူများအတွက် အရေးကြီးသည့်အရာများဖြစ်သော လုပ်ဆောင်ရန်များ၊ လမ်းညွှန်ချက်များနှင့် သတိပေးချက်များ စသည်တို့ကို သိမ်းဆည်းပေးထားပါသည်။

:guilabel:`Layers` panel ထဲရှိ Layer ၏ context menu မှ :guilabel:`Add layer notes...` (Layer မှတ်စုထည့်သွင်းခြင်း) ကို ရွေးချယ်ပြီးနောက် ပွင့်လာသော dialog တွင် လိုအပ်သည့်အချက်အလက်များကို ဖြည့်သွင်းနိုင်ပါသည်။ 


.. _figure_layer_notes:

.. figure:: img/layer_notes.png
   :align: center

   Layer တစ်ခုတွင် မှတ်စုများထည့်သွင်းခြင်း

:guilabel:`Add layer notes` (Layer မှတ်စုထည့်သွင်းခြင်း) dialog သည် အောက်ပါတို့လုပ်ဆောင်ရန်အတွက် tool အပြည့်အစုံဖြင့် html ကိုအခြေခံထားသည့် စာကြောင်းများစွာထည့်သွင်းနိုင်သည့် text box တစ်ခုဖြစ်သည်-

* စာသားများကို လိုအပ်သလိုပြင်ဆင်ခြင်း - ဖြတ်ခြင်း၊ ကူးယူခြင်း၊ ကူးချခြင်း၊ လုပ်ဆောင်ချက်ကိုပယ်ဖျက်ခြင်း၊ ပြန်လည်လုပ်ဆောင်ခြင်း
* အကြောင်းအရာတွင် ပါဝင်သော စကားလုံးများအားလုံး သို့မဟုတ် အစိတ်အပိုင်းများတွင်အသုံးပြုမည့် character formatting (ပုံစံသတ်မှတ်ခြင်း) - စာလုံးအရွယ်အစားနှင့် အရောင်၊ အရောင်ထင်းအောင်လုပ်ခြင်း (bold)၊ စာလုံးစောင်းဖြင့်ရေးသားခြင်း (italic)၊ စာသားအောက်တွင်မျဉ်းသားခြင်း၊ စာသားကိုဖြတ်၍မျဉ်းသားခြင်း၊ နောက်ခံအရောင်ထည့်ခြင်း၊ URL ကို highlight ပြုလုပ်ခြင်း
* စာပိုဒ်များကို ပုံစံချခြင်း - အချက်များ (bullet) နှင့် နံပါတ်စဉ် စာရင်းများ၊ နေရာချန်ခြင်း (indentation)၊ ကြိုတင်သတ်မှတ်ထားသည့် ခေါင်းစဉ်များထည့်ခြင်း (predefined headings)
* ဖိုင်များကို ဖိဆွဲ၍လည်း ထည့်သွင်းခြင်း
* HTML code ဖြင့် ပြင်ဆင်တည်းဖြတ်ခြင်း

Toolbar ၏ ညာဘက်ရှိ :guilabel:`...` drop-down မှ- 
* :guilabel:`Remove all formatting` (Format အားလုံးကို ဖယ်ရှားခြင်း) 
* :guilabel:`Remove character formatting` (Character format များဖယ်ရှားခြင်း)
* :guilabel:`Clear all content` (အကြောင်းအရာအားလုံးဖယ်ရှားခြင်း) တို့ကို ပြုလုပ်နိုင်ပါသည်။ 

:guilabel:`Layers` panel ထဲတွင် မှတ်စုတစ်ခုဖြင့် Layer တစ်ခုကို |indicatorNotes| icon ဖြင့်သတ်မှတ်ပေးထားပြီး ထို icon ပေါ်တွင် mouse ကို တင်ထားလိုက်ပါက မှတ်စုကို ပြသပေးမည်ဖြစ်သည်။ အဆိုပါမှတ်စုကိုပြင်ဆင်ရန် |indicatorNotes| icon ကို click ပြုလုပ်နိုင်ပါသည်။ ထို့အပြင် Layer အား right-click နှိပ်၍ :guilabel:`Edit layer note...` (Layerမှတ်စုကို ပြင်ဆင်တည်းဖြတ်ခြင်း) သို့မဟုတ် :guilabel:`Remove layer note` (Layer မှတ်စုကိုဖယ်ရှားခြင်း) ကိုလည်း ပြုလုပ်နိုင်ပါသည်။ 

.. note:: မှတ်စုများသည် :ref:`layer style <store_style>` ၏ အစိတ်အပိုင်းများဖြစ်ပြီး :file:`.qml` သို့မဟုတ် :file:`.qlr` ဖိုင်တွင် သိမ်းဆည်းထားနိုင်ပါသည်။ ၎င်းတို့ကို Layer style ကူးယူစဉ်တွင် Layer တစ်ခုမှ အခြားတစ်ခုသို့ ကူးပြောင်းနိုင်သည်။


.. index:: Variables, Expressions
.. _`general_tools_variables`:


Storing values in Variables (Variables (ကိန်းရှင်) များတွင် တန်ဖိုးများကို သိမ်းဆည်းခြင်း)
===========================================================================================

QGIS တွင် ထပ်ကာတလဲလဲပြန်လည်အသုံးပြုနေရသည့် တန်ဖိုးများ (ဥပမာ- Project ခေါင်းစဉ်၊ အသုံးပြုသူ၏ နာမည်အပြည့်အစုံ) သိမ်းဆည်းရန် variable များကို အသုံးပြုနိုင်ပါသည်။ Variable များကို ကမ္ဘာအဆင့်၊ project အဆင့် ၊ Layer အဆင့်၊ processing modeler level (လုပ်ငန်းမော်ဒယ်အဆင့်)၊ layout level (ပုံထုတ်ရန်ပြင်ဆင်သည့်အဆင့်) နှင့် layout item’s level(ပုံထုတ်ရန်ပြင်ဆင်သည့် item အဆင့်) များတွင် သတ်မှတ်နိုင်ပါသည်။ CSS cascading ၏စည်းမျဉ်းများအတိုင်း variable များကို အစားထိုးရေးသားနိုင်သည်။ ဥပမာအားဖြင့် Global level variable များကို နာမည်တူသည့် Project level variable များဖြင့် အစားထိုးရေးသားနိုင်သည်။ Variable နာမည်၏ ရှေ့တွင် ``@`` စကားလုံးကို အသုံးပြု၍ expression သို့မဟုတ် text strings များကို တည်ဆောက်ရန်အတွက် variable များကို အသုံးပြုနိုင်ပါသည်။ ဥပမာအားဖြင့် Print layout (ပုံထုတ်ရန် ပြင်ဆင်သည့်အနေအထား) တွင် အောက်ပါအကြောင်းအရာဖြင့် အညွှန်း(label) တစ်ခုဖန်တီးလျှင်-::

  This map was made using QGIS [% @qgis_version %]. The project file for this
  map is: [% @project_path %]


အောက်ဖော်ပြပါအတိုင်း အညွှန်းကို ပုံဖော်ပြသမည်ဖြစ်သည်-::

  This map was made using QGIS 3.4.4-Madeira. The project file for this map is:
  /gis/qgis-user-conference-2019.qgs

:ref:`preset read-only variables (ကြိုတင်သတ်မှတ်ထားသည့် ဖတ်ခွင့်သာရှိသော variable များ) <expression_variables>` များအပြင် အထက်တွင် ဖော်ပြခဲ့သည့် မည်သည့် level များအတွက်မဆို ကိုယ်ပိုင်စိတ်ကြိုက် variable များကိုသတ်မှတ်နိုင်ပါသည်။ အောက်ပါတို့ကိုစီမံခန့်ခွဲနိုင်ပါသည်-

* :menuselection:`Settings --> Options` menu ထဲမှ **global variables** 
* :guilabel:`Project Properties` dialog မှ **project variables** (:ref:`project_properties` တွင် ကြည့်ရှုနိုင်သည်)
* :guilabel:`Layer Properties` dialog မှ **vector layer variables** (:ref:`vector_properties_dialog` တွင် ကြည့်ရှုနိုင်သည်) 
* :guilabel:`Model Designer` dialog မှ **modeler variables** (:ref:`processing.modeler` တွင် ကြည့်ရှုနိုင်သည်)
* Print layout ရှိ :guilabel:`Layout` panel မှ **layout variables** (:ref:`layout_panel` တွင် ကြည့်ရှုနိုင်သည်)
* Print layout ရှိ :guilabel:`Item Properties` panel မှ **layout item variables** (:ref:`layout_item_options` တွင် ကြည့်ရှုနိုင်သည်)

ပြင်ဆင်တည်းဖြတ်နိုင်သော variable များနှင့် ကွဲပြားမှုရှိစေရန် read-only variable (ဖတ်ခွင့်သာရှိသည့် variable) များ၏ အမည်နှင့် တန်ဖိုးများကို စာလုံးအစောင်းဖြင့် ဖော်ပြထားပါသည်။ တနည်းအားဖြင့် ပိုမိုအဆင့်မြင့်သော variable (higher level variables) များကို အဆင့်နိမ့်သော variable (lower level variables) များဖြင့် အစားထိုးရေးသားထားလျှင် higher level variable များကို စာသားကိုဖြတ်၍မျဉ်းသား (strikethrough) ကာ ဖော်ပြသည်ကို တွေ့ရသည်။


.. _figure_variables_dialog:


.. figure:: img/project_variables.png
   :align: center

   Project အဆင့်တွင် variable များကို ပြင်ဆင်သည့်အရာ

.. note:: 
   
   Variable များအကြောင်းနှင့် အခြားသော ဥပမာများကို Nyall Dawson ၏ `Exploring variables in QGIS 2.12, အပိုင်း ၁
   <https://nyalldawson.net/2015/12/exploring-variables-in-qgis-2-12-part-1/>`_ ၊
   `အပိုင်း ၂ <https://nyalldawson.net/2015/12/exploring-variables-in-qgis-pt-2-project-management/>`_
   နှင့် `အပိုင်း ၃ <https://nyalldawson.net/2015/12/exploring-variables-in-qgis-pt-3-layer-level-variables/>`_ blog များတွင် ဆက်လက်လေ့လာနိုင်ပါသည်။
   
.. _authentication:


Authentication (အစစ်အမှန်ဖြစ်အောင်လုပ်ခြင်း)
=============================================

QGIS တွင် authentication credentials (အစစ်အမှန်ဖြစ်ကြောင်း အထောက်အထားများ)ကို လုံခြုံစိတ်ချစွာ သိမ်းဆည်း/ရယူပေးနိုင်စွမ်းရှိပါသည်။ အသုံးပြုသူများသည် credentials များကို portable database (ရွေ့ပြောင်းသယ်ယူနိုင်သော database) တွင် လုံခြုံစွာ သိမ်းဆည်းထားနိုင်ပြီး server သို့မဟုတ် database ချိတ်ဆက်မှုများတွင်လည်း အသုံးပြုနိုင်သည့်အပြင်
project သို့မဟုတ် setting ဖိုင်များတွင် ID tokens အနေဖြင့် စိတ်ချစွာ ကိုးကားယူခြင်းများ ပြုလုပ်နိုင်ပါသည်။ နောက်ထပ်သိရှိလိုသည့် အကြောင်းအရာများအတွက် :ref:`authentication_index` တွင် သွားရောက်ကြည့်ရှုနိုင်ပါသည်။ 

Authentication system နှင့် ၎င်း၏ portable database ကို စတင်အသုံးပြုရာတွင် ခိုင်ခံ့လုံခြုံသည့်စကားဝှက် (Master password)တစ်ခု သတ်မှတ်ထားရန် လိုအပ်မည်ဖြစ်သည်။ 


.. _common_widgets:


Common widgets (အသုံးများသော widget များ)
==========================================

QGIS တွင် မကြာခဏအသုံးပြုရမည့် ရွေးချယ်စရာ (options) အချို့ရှိရာ အသုံးပြုရာတွင် လွယ်ကူအဆင်ပြေစေရန် QGIS သည် အောက်တွင်ဖော်ပြထားသော အထူး widget များကို ပံ့ပိုးပေးထားပါသည်။


.. index:: Colors
.. _color-selector:

Color Selector (အရောင်ရွေးချယ်ပေးသည့်အရာ)
------------------------------------------

The color dialog (အရောင် dialog)
.................................

အရောင်တစ်ခုကိုရွေးချယ်ရန် |selectColor| icon ကိုနှိပ်လိုက်သည့်အခါတိုင်း :guilabel:`Select Color` dialog ပွင့်လာမည်ဖြစ်သည်။ အဆိုပါ dialog ရှိ အသွင်အပြင်များသည် :menuselection:`Settings --> Options... --> General` မှ :guilabel:`Use native color chooser dialogs` (မူရင်းအရောင်ရွေးချယ်ပေးသည့် dialog များအသုံးပြုမည်) parameter checkbox ၏ အခြေအနေပေါ်မူတည်၍ ဖော်ပြမည်ဖြစ်သည်။ အဆိုပါ checkbox ကို အမှန်ခြစ်ပြုလုပ်ပါက color dialog သည် QGIS ကိုအသုံးပြုနေသည့် OS ၏ မူရင်းအရောင်အတိုင်း အသုံးပြုသွားမည်ဖြစ်ပြီး အမှန်ခြစ်ဖြုတ်ထားပါက QGIS custom color chooser (QGIS တွင်စိတ်ကြိုက်အရောင်ရွေးချယ်နိုင်မည့်နေရာ) ကိုအသုံးပြုမည်ဖြစ်သည်။

Custom color chooser တွင် အရောင်များရွေးချယ်နိုင်ရန်အတွက် |colorBox| :sup:`Color ramp` (ရောင်စဉ်တန်း)၊ |colorWheel| :sup:`Color wheel` (အရောင်ဘီး) ၊ |colorSwatches| :sup:`Color swatches` (အရောင်ကွက်) နှင့် |colorPicker| :sup:`Color picker` (အရောင်ရယူပေးသည့်အရာ) ဟူ၍ tab ၄ ခုရှိပြီး အဆိုပါ tab များအနက် ပထမ tab ၂ခုတွင် အရောင်ပေါင်းစပ်မှု အားလုံးကိုတွေ့ရှိနိုင်ပြီး မိမိလိုအပ်သလို အရောင်ရွေးချယ်နိုင်သည်။

.. figure:: img/color_selector_ramp.png
   :align: center


   အရောင်ရွေးချယ်နိုင်သည့် ရောင်စဉ်တန်း tab


|colorSwatches| :sup:`Color swatches` (အရောင်ကွက်) tab တွင် color palette (အရောင်ချပ်) များစာရင်းမှ ရွေးချယ်နိုင်ပါသည် (အသေးစိတ်ကို :ref:`colors_options` တွင် ကြည့်ရှု့နိုင်ပါသည်။) :guilabel:`Recent colors` (မကြာသေးမီက အသုံးပြုခဲ့သည့်အရောင်) palette ကို frame ၏ အောက်ခြေတွင်ရှိသော |symbologyAdd| :sup:`Add current color` (လက်ရှိအရောင်ထည့်သွင်းခြင်း) နှင့် |symbologyRemove| :sup:`Remove selected color`  (ရွေးချယ်ထားသည့်အရောင်ဖယ်ရှားခြင်း) ခလုတ်များဖြင့် ပြုပြင်မွမ်းမံနိုင်သည်။

Palette combo box ဘေးတွင်ရှိသော :guilabel:`...` button တွင် အောက်ဖော်ပြပါများကို ဆောင်ရွက်နိုင်ပါသည်-

* အရောင်များအား ကူးယူခြင်း၊ ကူးချခြင်း၊ ထည့်သွင်းခြင်း သို့မဟုတ် ထုတ်ယူခြင်း၊ 
* Color palette များကို ဖန်တီးခြင်း၊ ထည့်သွင်းခြင်း သို့မဟုတ် ဖယ်ရှားခြင်း
* Color selector widget တွင် စိတ်ကြိုက်ပြင်ဆင်ထားသော palette တစ်ခုကို :guilabel:`Show in Color Buttons` ဖြင့် ထည့်သွင်းခြင်း (:numref:`figure_color_selector` တွင် ကြည့်ရှုနိုင်ပါသည်)


.. _figure_color_selector_swatches:


.. figure:: img/color_selector_recent_colors.png
   :align: center

   အရောင်ရွေးချယ်နိုင်သည့် ရောင်စုံကွက် tab

.. index:: Color picker

နောက်တစ်နည်းအနေဖြင့် |colorPicker| :sup:`Color picker` (အရောင်ရယူပေးသည့်အရာ) ကို အသုံးပြုနိုင်ပါသည်။ ၎င်းသည် QGIS UI (QGIS မျက်နှာပြင်) ၏ မည်သည့်နေရာ၌မဆို mouse cursor အောက်ရှိ အရောင်ကို နမူနာအနေဖြင့် ရွေးချယ်နိုင်ပါသည်။ သို့မဟုတ် အခြား application များမှပင် ရယူနိုင်ပါသည် - ၎င်း tab ဖွင့်ထားချိန်တွင် space bar ကိုနှိပ်ကာ အသုံးပြုလိုသည့် အရောင်ပေါ်သို့ mouse ကိုရွှေ့ပြီးနောက် click နှိပ်ပါ သို့မဟုတ် space bar ကို နောက်တစ်ကြိမ်ထပ်နှိပ်ပါ။ :guilabel:`Sample Color` ခလုတ် ကိုနှိပ်၍လည်း color picker ကို အသုံးပြုနိုင်သည်။

မည်သည့်နည်းလမ်းကိုပင် အသုံးပြုသည်ဖြစ်စေ ရွေးချယ်ထားသောအရောင်ကို ``HSV`` တန်ဖိုးများ (အရောင်အဆင်း (Hue)၊ အရောင်အနုအရင့် (Saturation)၊ တန်ဖိုး) နှင့် ``RGB`` တန်ဖိုးများ (အနီရောင်၊ အစိမ်းရောင်၊ အပြာရောင်) အတွက် color slider (အရောင်တန်ဖိုးအတိုးအလျှော့လုပ်ပေးသည့်အရာ) များဖြင့် ဖော်ပြမည်ဖြစ်ပြီး :guilabel:`HTML notation` (HTML သင်္ကေတ) တွင်လည်း အရောင်သတ်မှတ်ရွေးချယ်နိုင်သည်။

အရောင်တစ်ခုအား ပြင်ဆင်ပြောင်းလဲရန် color parameters slider များပေါ်ရှိ နေရာတစ်ခုခု သို့မဟုတ် color wheel သို့မဟုတ် ramp ပေါ်တွင် click နှိပ်၍ လွယ်ကူစွာပြောင်းလဲနိုင်ပါသည်။ Parameter များကိုလည်း ၎င်းနှင့် သက်ဆိုင်သည့် slider ပေါ်သို့ mouse ဘီးအား လှည့်၍ သို့မဟုတ် ဘေးတွင်ရှိသော spinbox ကို အသုံးပြု၍ လိုအပ်သလို ချိန်ညှိနိုင်သည့်အပြင် HTML notation ထဲတွင် စာရိုက်၍လည်း ပြောင်းလဲနိုင်သည်။ နောက်ဆုံးအနေဖြင့် :guilabel:`Opacity` slider ဖြင့် transparency (ဖောက်ထွင်းမြင်နိုင်မှု) အဆင့်ကို သတ်မှတ်နိုင်သည်။ 

Dialog တွင် ယခင်အသုံးပြုထားသော :guilabel:`Old` color (အရောင်ဟောင်း) နှင့် လက်ရှိရွေးချယ်ထားသည့် :guilabel:`Current` (လက်ရှိအရောင်) အရောင်နှစ်ခုကို နှိုင်းယှဉ်ပြသထားပါသည်။ ဖိဆွဲ၍ထည့်ခြင်း သို့မဟုတ် |atlasNext| :sup:`Add color to swatch` ခလုတ်ကိုနှိပ်ခြင်းအားဖြင့် ထိုအရောင်များကို လွယ်ကူစွာအသုံးပြုနိုင်ရန် သိမ်းဆည်းထားနိုင်ပါသည်။
 
.. _quick_color_modification:

.. tip:: **အရောင်အား လျင်မြန်စွာမွမ်းမံပြောင်းလဲခြင်း**


  Color selector widget ကို အခြားတစ်ခုပေါ်သို့ဖိဆွဲချ၍ ၎င်း၏အရောင်များကို အခြားတစ်ခုတွင်အသုံးပြုနိုင်ပါသည်။


.. _color_widget:


The color drop-down shortcut (အရောင် Drop-down ဖြတ်လမ်းနည်း)
.............................................................

|selectColor| ၏ ညာဘက်ရှိ drop-down arrow အားနှိပ်ပါက အရောင်အလွယ်တကူရွေးချယ်နိုင်ရန် widget တစ်ခု ပေါ်လာပါမည်။ ၎င်းတွင် အောက်ဖော်ပြပါတို့ကို သုံးစွဲနိုင်ပါသည်-

* အရောင်ရွေးချယ်နိုင်ရန် Color wheel တစ်ခု
* အရောင်၏ အလင်းပိတ်နှုန်းကိုပြောင်းလဲနိုင်ရန် alpha slider တစ်ခု
* :guilabel:`Show in Color Buttons` တွင် ယခင်ကသတ်မှတ်ထားသော color palette များ
* လက်ရှိအသုံးပြုနေသော အရောင်အား ကူးယူ၍ အခြား widget တစ်ခုတွင် နေရာချထားခြင်း
* ကွန်ပျူတာမြင်ကွင်း၏ နေရာတစ်ခုခုမှ အရောင်ရွေးချယ်ခြင်း
* Color selector dialog မှ အရောင်ရွေးချယ်ခြင်း
* Widget တစ်ခုမှ အခြားတစ်ခုသို့ အရောင်အား ဖိဆွဲချ၍ လွယ်ကူလျင်မြန်စွာပြောင်းလဲခြင်း တို့ဖြစ်သည်။

.. tip:: Color selector widget ပေါ်တွင် mouse ဘီးအား လှိမ့်၍ သက်ဆိုင်ရာအရောင်၏ အလင်းပိတ်နှုန်း (opacity) အား လျင်မြန်စွာ ပြုပြင်မွမ်းမံနိုင်ပါသည်။


.. note:: 
   Color widget အား data-defined override properties (Data ဖြင့်သတ်မှတ်ထားသော အစားထိုးရေးသားခြင်းဆိုင်ရာ ဂုဏ်သတ္တိများ) ကိုသုံး၍ :ref:`project color <project_colors>` တစ်ခုတွင်သတ်မှတ်ထားလျှင် အရောင်ပြောင်းလဲခြင်းအတွက် အထက်ဖော်ပြပါ လုပ်ဆောင်ချက်များကို အသုံးပြု၍ မရပါ။ အသုံးပြုနိုင်ရန် :guilabel:`Unlink color` (အရောင်ချိတ်ဆက်မှုပယ်ဖျက်ခြင်း) သို့မဟုတ် သတ်မှတ်ချက် (definition) ကို :guilabel:`Clear` (ရှင်းလင်းခြင်း) တို့ကို ဦးစွာပြုလုပ်ရန် လိုအပ်ပါသည်။

.. _figure_color_selector:

.. figure:: img/quick_color_selector.png
   :align: center

   အရောင်ကိုလျင်မြန်စွာရွေးချယ်ပေးသည့် menu


.. _color_ramp_widget:


The color ramp drop-down shortcut (ရောင်စဉ်တန်း Drop-down ဖြတ်လမ်းနည်း)
........................................................................

Color ramp များသည် တစ်ခု သို့မဟုတ် တစ်ခုထက်ပိုသော feature များတွင် အရောင်အစုများ အသုံးပြုရာတွင်အသုံးဝင်သည့် နည်းလမ်းတစ်ခုဖြစ်ပါသည်။ အဆိုပါလုပ်ဆောင်မှုကို :ref:`color-ramp` အခန်းတွင် ဖော်ပြထားပါသည်။ အရောင်များအတွက်အသုံးပြုမည်ဆိုပါက |selectColorRamp| color ramp ခလုတ်ကိုနှိပ်လိုက်လျှင် သက်ဆိုင်ရာ color ramp type dialog(ရောင်စဉ်တန်းအမျိုးအစား dialog) ပွင့်လာမည်ဖြစ်ပြီး ၎င်းတွင် အရောင်တို့၏ ဂုဏ်သတ္တိများကို ပြောင်းလဲနိုင်ပါသည်။

.. _figure_colorBrewer_ramp:

.. figure:: img/color_ramp_brewer.png
   :align: center

   Colorbreser ramp တစ်ခုအားစိတ်ကြိုက်ပြင်ဆင်ခြင်း

ခလုတ်၏ ညာဘက်တွင်ရှိသော colorbrewer ramp သည် color ramp အမျိုးမျိုးနှင့် အောက်ပါရွေးချယ်စရာများကို လျှင်မြန်စွာ အသုံးပြုနိုင်ရန် ဆောင်ရွက်ပေးပါသည်- 


* :guilabel:`Invert Color Ramp` (ရောင်စဉ်တန်းကို ပြောင်းပြန်အသုံးပြုခြင်း)
* :guilabel:`Clear Current Ramp` ကို widget တွင် အသုံးပြုထားသော မည်သည့် color ramp ကိုမဆို ဖယ်ရှားရာတွင် အသုံးပြုသည်။ (အချို့သောအကြောင်းအရာများတွင်သာ အသုံးပြုနိုင်ပါသည်။)
* |unchecked| :guilabel:`Random Colors` (ကျပန်းအရောင်) - အချို့အကြောင်းအရာများတွင်သာ
  အသုံးပြုနိုင်သည် (ဥပမာ- Layer သင်္ကေတတစ်ခုအတွက် color ramp တစ်ခုအား အသုံးပြုထားသောအချိန်)၊ ၎င်းကို အမှန်ခြစ်ပြုလုပ်ခြင်းဖြင့် ကျပန်းအရောင်တစ်ခုခုကို အသုံးပြုစေပါသည်။ လက်ရှိအရောင်ကို စိတ်ကျေနပ်မှုမရှိပါက ကျပန်း color ramp အသစ်တစ်ခု ထုတ်ပေးရန် :guilabel:`Shuffle random colors` (ကျပန်းအ‌ရောင်များကို ကျပန်းရွေးချယ်ခြင်း) ကိုလည်း လုပ်ဆောင်နိုင်ပါသည်။
* :guilabel:`Style Manager` (Style စီမံခန့်ခွဲသည့်အရာ) dialog တွင် **Favorites (နှစ်သက်ရာများ)** အဖြစ် မှတ်သားထားသည့် ``gradient`` သို့မဟုတ် ``catalog: cpt-city`` color ramp များကိုလည်း ကြိုတင်ကြည့်ရှုနိုင်သည်။
* :guilabel:`All Color Ramps` သည် ကိုက်ညီသော color ramps database ကို ဝင်ရောက်အသုံးပြုနိုင်ပါသည်။
* :guilabel:`Create New Color Ramp...` (ရောင်စဉ်တန်းအသစ်ဖန်တီးခြင်း) ကို သုံး၍ လက်ရှိအသုံးပြုနေသော widget တွင် အသုံးပြုနိုင်သော color ramp အသစ်တစ်ခုကိုဖန်တီးနိုင်ပါသည်။ (သို့သော် ထို color ramp သည် library တွင် သိမ်းဆည်းထားခြင်းမရှိပါက အခြားနေရာများတွင် အသုံးပြုနိုင်မည်မဟုတ်ကြောင်း မှတ်သားထားသင့်ပါသည်။)
* :guilabel:`Edit Color Ramp...` (ရောင်စဉ်တန်းကိုပြင်ဆင်တည်းဖြတ်ခြင်း) သည် color ramp ခလုတ်တစ်ခုလုံးအား click ပြုလုပ်ခြင်းနှင့် အတူတူပင်ဖြစ်ပါသည်။
* :guilabel:`Save Color Ramp...` (ရောင်စဉ်တန်းအားသိမ်းဆည်းခြင်း) သည် လက်ရှိအသုံးပြုနေသော color ramp အား စိတ်ကြိုက်ပြင်ဆင်ချက်များနှင့်အတူ style library တွင် သိမ်းဆည်းရန် အသုံးပြုနိုင်သည်။

.. _figure_color_ramp_widget:


.. figure:: img/quick_colorramp_selector.png
   :align: center

   ရောင်စဉ်တန်းများအား လျှင်မြန်စွာရွေးချယ်နိုင်သည့် widget


.. index:: Symbol
.. _symbol_widget_selector:


Symbol Widget (သင်္ကေတ Widget)
-------------------------------

:guilabel:`Symbol` selector widget သည် feature တစ်ခု၏ symbol properties (သင်္ကေတဂုဏ်သတ္တိ) များကို သတ်မှတ်ရန် အသုံးပြုနိုင်သည့် လွယ်ကူသောဖြတ်လမ်းနည်းတစ်ခုဖြစ်ပါသည်။ Drop-down arrow ကို click ပြုလုပ်လျှင် :ref:`color drop-down widget <color_widget>` ၏ feature များနှင့်အတူ အောက်ပါရွေးချယ်စရာများကို တွေ့နိုင်ပါသည်- 

* :guilabel:`Configure Symbol...` (သင်္ကေတပြင်ဆင်သတ်မှတ်ခြင်း) သည် symbol selector widget ကို ဖွင့်သည်နှင့်အတူတူပင် ဖြစ်ပြီး :ref:`symbol parameters <edit_symbol>` များကို သတ်မှတ်ရန် dialog တစ်ခုပေါ်လာမည်ဖြစ်သည်။
* :guilabel:`Copy Symbol` သည် လက်ရှိအသုံးပြုနေသော item မှ သင်္ကေတအား ကူးယူရန် အသုံးပြုနိုင်သည်။
* :guilabel:`Paste Symbol` သည် လက်ရှိအသုံးပြုနေသော item သို့ သင်္ကေတအား ကူးချရန်ဖြစ်ပြီး Configuration (ပြင်ဆင်သတ်မှတ်ခြင်း)ကို ပိုမိုလျှင်မြန်စေပါသည်။
* :guilabel:`Clear Current Symbol` သည် widget တွင် အသုံးပြုထားသော သင်္ကေတကို ပယ်ဖျက်ရန် အသုံးပြုနိုင်ပါသည် (၎င်းကို အကြောင်းအရာအချို့တွင်သာ အသုံးပြုနိုင်ပါသည်)

.. tip:: အမှတ် (marker) သို့မဟုတ် မျဉ်း (line) symbol widget ပေါ်တွင် mouse ဘီးအားလှိမ့်၍ သင်္ကေတအရွယ်အစားကို ပြုပြင်မွမ်းမံနိုင်ပါသည်။


.. index:: Embedded file
.. _embedded_file_selector:

Remote or embedded file selector (အဝေးမှဖိုင် သို့မဟုတ် ထည့်သွင်းထားသည့် ဖိုင်ရွေးချယ်ပေးသည့်အရာ)
--------------------------------------------------------------------------------------------------

File selector widget နှင့်အတူ :guilabel:`...` ခလုတ်သည် အောက်တွင် ဖော်ပြထားသည့် ဖိုင်အမျိုးအစားကို အသုံးပြုသည့်အချိန်များတွင်သာ drop-down arrow တစ်ခုကိုပြသမည်ဖြစ်သည်-

* သင်္ကေတ သို့မဟုတ် အညွှန်းထဲရှိ SVG ဖိုင်တစ်ခုကို အသုံးပြုခြင်း
* သင်္ကေတ၊ အညွှန်းများ၊ အသွင်အပြင် (textures) နှင့် အလှဆင်မှု (Decorations) များ ပြင်ဆင်ရန် raster image တစ်ခုအား အသုံးပြုခြင်း 

ထို drop-down arrow အားနှိပ်ခြင်းဖြင့် အောက်ပါတို့ကို လုပ်‌ဆောင်နိုင်သည်-

* စက်ထဲရှိ ဖိုင်လမ်းကြောင်းအတွင်းမှ ဖိုင်ကို ထည့်သွင်းအသုံးပြုခြင်း- ဖိုင်သည် ဖိုင်လမ်းကြောင်းတွင် တည်ရှိရမည်ဖြစ်ပြီး QGIS သည်လည်း သက်ဆိုင်သည့် image ကို ပြသရန် ဖိုင်လမ်းကြောင်းကို ဆုံးဖြတ်ရန် လိုအပ်သည်။
* Remote URL မှ ဖိုင်အား ထည့်သွင်းအသုံးပြုခြင်း- အထက်တွင်ဖော်ပြထားသကဲ့သို့ပင် image အား remote အရင်းအမြစ်မှ အောင်မြင်စွာရယူပြီးမှသာ ထည့်သွင်းအသုံးပြုနိုင်မည်ဖြစ်သည်။
* ဖိုင်အား item အတွင်းသို့ထည့်သွင်းခြင်း- ဖိုင်အား လက်ရှိအသုံးပြုနေသော project၊ style database သို့မဟုတ် print layout ပုံစံများအတွင်း ထည့်သွင်းထားမည်ဖြစ်သည်။ ထိုဖိုင်ကို item ၏ အစိတ်အပိုင်းတစ်ခုအဖြစ် အမြဲပုံဖော်ပြသမည်ဖြစ်သည်။ ထိုသို့ထည့်သွင်းထားခြင်းသည် QGIS အသုံးပြုခြင်းနှင့် အသုံးပြုသူများကြားတွင် လွယ်ကူစွာ မျှဝေအသုံးပြုနိုင်သော စိတ်ကြိုက်ပြုလုပ်ထားသည့် သင်္ကေတများပါဝင်သော project အားဖန်တီးရန် လွယ်ကူသောနည်းလမ်းဖြစ်သည်။
* ထည့်သွင်းထားသော file အား widget မှ ထုတ်ယူ၍ စက်ထဲတွင် သိမ်းဆည်းထားနိုင်ပါသည်။


.. index:: Rendering; Scale dependent visibility
.. _label_scaledepend:

Visibility Scale Selector (မြင်ရနိုင်သောစကေး ရွေးချယ်ပေးသည့်အရာ)
-----------------------------------------------------------------

Visibility scale selector တွင် မြေပုံမျက်နှာပြင်ရှိ element တစ်ခုကို မည်သည့်စကေးတွင် မြင်ရနိုင်မည်ကို ထိန်းချုပ်နိုင်သည့် ရွေးချယ်စရာများပါရှိပါသည်။ သတ်မှတ်ထားသည့် စကေးအပိုင်းအခြားထက်ကျော်လွန်ပါက မည်သည့် element ကိုမျှ မြင်နိုင်မည် မဟုတ်ပေ။ ဤလုပ်ဆောင်မှုကို layer များ၊ အညွှန်းများ သို့မဟုတ် ရုပ်ပုံများတွင် ၎င်းတို့၏ :guilabel:`Rendering` properties tab အားအသုံးပြု၍ဆောင်ရွက်နိုင်ပါသည်။

#. |checkbox| :guilabel:`Scale dependent visibility` (စကေးပေါ်မူတည်သည့် မြင်ရနိုင်မှု) box ကို အမှန်ခြစ်ပါ။
#. :guilabel:`Minimum (exclusive)` box တွင် :ref:`predefined scales (ကြိုတင်သတ်မှတ်ထားသည့်စကေး) <predefinedscales>` ကိုရွေးချယ်ခြင်း သို့မဟုတ် တန်ဖိုးအား ရိုက်ထည့်ခြင်းဖြင့် လိုချင်သော အများဆုံးချုံ့ကြည့်နိုင်သည့်စကေးကို ဖြည့်သွင်းပါ။
#. :guilabel:`Maximum (inclusive)` box တွင်လည်း လိုချင်သောအများဆုံးချဲ့ကြည့်နိုင်သော စကေးကို ဖြည့်သွင်းပါ။

   စကေး box များ၏ ဘေးနားတွင်ရှိသော |mapIdentification| :sup:`Set to current canvas scale` (လက်ရှိမြေပုံမျက်နှာပြင်စကေးအတိုင်းသတ်မှတ်ခြင်း) ခလုတ်သည် မြင်နိုင်သောအပိုင်းအခြားပမာဏကို လက်ရှိအသုံးပြုနေသော မြေပုံမျက်နှာပြင်အတိုင်း သတ်မှတ်မည်ဖြစ်ပြီး အဆိုပါ ခလုတ်ဘေးရှိ မြှားကို နှိပ်လိုက်လျှင် Layout ပြင်ဆင်ထားသော မြေပုံများ၏ စကေးများကို ရရှိနိုင်ပြီး box တွင် ဖြည့်သွင်းရန် ၎င်းတို့ကို ပြန်လည်အသုံးပြုနိုင်သည်။

.. _figure_visibilityscaleselector_widget:

.. figure:: img/visibilityscale_selector.png
   :align: center

   မြင်ရနိုင်သောစကေး ရွေးချယ်ပေးသည့်အရာ widget


.. index:: Extent selection
.. _extent_selector:


Spatial Extent Selector (တည်နေရာ အကျယ်အဝန်းအတိုင်းအတာရွေးချယ်ပေးသည့်အရာ)
-------------------------------------------------------------------------

:guilabel:`Extent` selector widget သည် Layer တစ်ခုပေါ်တွင်သတ်မှတ်မည့် spatial extent တစ်ခုကို ရွေးချယ်လိုသည့်အခါတွင် ဖြစ်စေ သို့မဟုတ် layer ပေါ်တွင်ဆောင်ရွက်မည့် လုပ်ဆောင်ချက်များကို ကန့်သတ်လိုသည့်အခါတွင်ဖြစ်စေ အလွယ်တကူ အသုံးပြုနိုင်သောဖြတ်လမ်းနည်းတစ်ခုဖြစ်ပါသည်။ အကြောင်းအရာပေါ်မူတည်၍ အောက်ဖော်ပြပါများအကြား ရွေးချယ်မှုများ ပြုလုပ်နိုင်ပါသည်-

* :guilabel:`Current Layer Extent` (လက်ရှိ Layer extent)- ဥပမာ- Layer တစ်ခုအားထုတ်ယူလိုသည့်အချိန်တွင် အသုံးပြုပါသည်။
* :menuselection:`Calculate from Layer -->` (Layer မှ တွက်ချက်ခြင်း) - လက်ရှိလုပ်ဆောင်နေသော project တွင် ထည့်သွင်းအသုံးပြုထားသော Layer တစ်ခု၏ extent အတိုင်း တွက်ချက်ရာတွင် အသုံးပြုသည်။
* လက်ရှိဆောင်ရွက်နေသောမြေပုံမျက်နှာပြင်အတိုင်း အသုံးပြုရန် :guilabel:`Map Canvas Extent` ကိုအသုံးပြုနိုင်သည်။
* :guilabel:`Draw on Canvas` (မြေပုံမျက်နှာပြင်တွင် ရေးဆွဲခြင်း) - ထောင့်မှန်စတုဂံတစ်ခုကို ရေးဆွဲပြီး ၎င်း၏ကိုဩဒိနိတ်များကို အသုံးပြုမည်ဖြစ်သည်။
* :guilabel:`Calculate from Bookmark` (တည်နေရာအမှတ်အသားမှတွက်ချက်ခြင်း) - သိမ်းဆည်းထားသော  :ref:`bookmark(တည်နေရာအမှတ်အသား) <sec_bookmarks>` ၏ extent အတိုင်း အသုံးပြုပါသည်။
* :guilabel:`Calculate from Layout Map` (Layout မြေပုံမှ တွက်ချက်ခြင်း) - :ref:`Layout map <layout_map_item>` တစ်ခု၏ extent ကို အသုံးပြုပါသည်။
* ကိုဩဒိနိတ်များကို ``xmin ၊ xmax ၊ ymin ၊ ymax`` အဖြစ် ထည့်သွင်းခြင်း သို့မဟုတ် ပြင်ဆင်ခြင်းကို ပြုလုပ်နိုင်သည်။

.. _figure_extentselector_widget:

.. figure:: img/extent_selector.png
   :align: center


   အကျယ်အဝန်းအတိုင်းအတာရွေးချယ်ပေးသည့်အရာ widget


.. index:: Font selection; Text format
.. _font_selector:

Font Selector (စာလုံးဖောင့် ရွေးချယ်ပေးသည့်အရာ)
------------------------------------------------

:guilabel:`Font` selector widget သည် စာဖြင့်ဖော်ပြထားသော (feature အညွှန်းများ၊ အလှဆင်ခြင်းအညွှန်းများ၊ မြေပုံရည်ညွှန်းချက်စာသား စသော)  အချက်အလက်များအတွက် font properties (စာလုံးဖောင့် ဂုဏ်သတ္တိ) များကို သတ်မှတ်လိုသောအခါတွင် အသုံးပြုနိုင်သည့် လွယ်ကူသော ဖြတ်လမ်းနည်းတစ်ခုဖြစ်ပါသည်။ Drop-down arrow ကို click နှိပ်ခြင်းအားဖြင့် အောက်ဖော်ပြပါ ရွေးချယ်စရာများအားလုံး သို့မဟုတ် အချို့ကို တွေ့ရှိနိုင်ပါသည်-


.. _figure_fontselector_widget:


.. figure:: img/fontselector_widget.png
   :align: center

   စာလုံးဖောင့် ရွေးချယ်ပေးသည့်အရာ drop-down menu

* :guilabel:`Clear Current Text Format` (လက်ရှိစာသားပုံစံကို ရှင်းလင်းခြင်း) သည် widget တွင် အသုံးပြုထားသော စာသားပုံစံကို ဖယ်ရှားရန်အသုံးပြုပါသည်။ (အချို့သော အကြောင်းအရာများတွင်သာ အသုံးပြုနိုင်ပါသည်)
* :guilabel:`Font Size` (စာလုံးအရွယ်အစား) ကို သက်ဆိုင်သည့်ယူနစ်ဖြင့် ရွေးချယ်နိုင်သည်။
* :menuselection:`Recent Fonts -->` (လတ်တလောအသုံးပြုထားသည့် စာလုံးဖောင့်များ) menu သည် လက်ရှိအသုံးပြုထားသော စာလုံးဖောင့်ကို (ထိပ်ဆုံးတွင်) ဖော်ပြထားသည်။
* :guilabel:`Configure Format...` (Format ပြင်ဆင်သတ်မှတ်ခြင်း) သည် font selector widget (စာလုံးဖောင့် ရွေးချယ်ပေးသည့်အရာ widget) ကို ဖွင့်ခြင်းနှင့်အတူတူပင်ဖြစ်သည်။ ၎င်းသည် :ref:`Text format <text_format>` dialog ကို ပွင့်သွားစေပြီး စကားလုံးများ၏ အရောင်၊ အလင်းပိတ်နှုန်း၊ မျက်နှာမူရာ၊ HTML notation ၊ buffer ၊ နောက်ခံ၊ အရိပ်ကျမှု (shadow) စသည်တို့ကိုပြင်ဆင်နိုင်ရန် အဆင့်မြင့်သည့် ပုံစံသတ်မှတ်ခြင်းဆိုင်ရာရွေးချယ်စရာများ (advanced formatting options) များရရှိနိုင်ပါသည်။
* :guilabel:`Copy Format` သည် စကားလုံးများ၏ format ကို ကူးယူနိုင်သည်။
* :guilabel:`Paste Format` သည် ကူးယူထားသော format ကို စကားလုံးများတွင်သုံးရန်ဖြစ်ပြီး configuration ကို ပိုမိုလျင်မြန်စေပါသည်။
* :ref:`Color widget <color_widget>` ကို လျှင်မြန်သော အရောင်သတ်မှတ်မှုအတွက်အသုံးပြုပါသည်။

.. tip:: Font selector widget ပေါ်တွင် mouse ဘီးကို လှိမ့်၍ စာလုံးအရွယ်အစားကို လျင်မြန်စွာ ပြုပြင်မွမ်းမံနိုင်ပါသည်။


.. index:: Unit selection; Map scale
.. _unit_selector:

Unit Selector (ယူနစ်များ ရွေးချယ်ပေးသည့်အရာ)
---------------------------------------------

QGIS တွင်ရှိသော item (အညွှန်း၊ သင်္ကေတ၊ Layout တွင်ပါဝင်သည့်အရာများ စသည်) များ၏ အရွယ်အစားဂုဏ်သတ္တိများသည် Layer တစ်ခု သို့မဟုတ် project တစ်ခု၏ ယူနစ်များနှင့် ဆက်စပ်မှုမရှိပါ။ :guilabel:`Unit` selector ၏ drop-down menu တွင်  မိမိလိုချင်သည့် rendering အတိုင်း (မျက်နှာပြင်ကြည်လင်ပြတ်သားမှု (screen resolution)၊ စာရွက်အရွယ်အစားနှင့် terrain (မျက်နှာပြင်အနေအထား) တို့ပေါ်မူတည်၍) ၎င်းတို့၏ တန်ဖိုးများကို ပြောင်းလဲနိုင်ပါသည်။ အသုံးပြုနိုင်သော ယူနစ်များမှာ-

* :guilabel:`Millimeters` (မီလီမီတာ)
* :guilabel:`Points` (ပွိုင့်)
* :guilabel:`Pixels`
* :guilabel:`Inches` (လက်မ)
* :guilabel:`Percentage` (ရာခိုင်နှုန်း) - အချို့ ဂုဏ်သတ္တိများကို အခြားတစ်ခု၏ ရာခိုင်နှုန်းအဖြစ် သတ်မှတ်ပေးနိုင်ပါသည်။ ဥပမာအားဖြင့် buffer/အရိပ် အရွယ်အစားများ တသမတ်တည်း ရှိမည့်အစား စာသားအရွယ်အစားပြောင်းလဲသည့်အတိုင်း buffer အရွယ်အစား၊ အရိပ်အချင်းဝက် စသည့် အပိုင်းများကို စကေးကိုက်ပြောင်းလဲပေးနိုင်သော စာသား format များဖန်တီးရာတွင် အသုံးဝင်ပါသည်။ ထို့ကြောင့် စာလုံးအရွယ်အစားပြောင်းလဲသည့်အခါတိုင်း ထိုအရာများ၏ အရွယ်အစားကို တစ်ခုချင်းလိုက်ချိန်ညှိပေးရန် မလိုအပ်တော့ပေ။ 
* :guilabel:`Meters at Scale` (စကေးရှိမီတာ) - ၎င်းသည် မြေပုံမျက်နှာပြင်ရှိ နောက်ခံမြေပုံယူနစ်များကို ထည့်သွင်းစဉ်းစားခြင်းမပြုပဲ အရွယ်အစားကို မီတာဖြင့်သတ်မှတ်ပေးပါသည် (ဥပမာအားဖြင့် နောက်ခံမြေပုံယူနစ်သည် လက်မ၊ ပေ၊ ဒီဂရီ တစ်ခုခုဖြစ်သော်လည်း မီတာဖြင့်သာ တိုင်းတာဖော်ပြပါသည်)။ Project တွင် အသုံးပြုထားသော ဘဲဥပုံစက်လုံး setting (ellipsoid setting) နှင့် မြေပုံ extent ၏ အလယ်ဗဟိုရှိ မီတာဖြင့်အကွာအဝေး၏ အရိပ်ချခြင်းပေါ်မူတည်၍ မီတာဖြင့်အရွယ်အစားကို တွက်ချက်ပေးပါသည်။ Projected coordinate system ရှိသော မြေပုံများအတွက် projected ယူနစ်များကို အသုံးပြု၍ တွက်ချက်ပေးပါသည်။ လတ္တီတွဒ်၊ လောင်ဂျီတွဒ် ဖြင့် ဖော်ပြသော Geographic coordinate system ရှိသော မြေပုံများအတွက်မူ မြေပုံ၏ ဒေါင်လိုက်စကေးအတွက် ellipsoidal တွက်ချက်မှုများကို အသုံးပြု၍ မီတာဖြင့်အရွယ်အစားကို အနီးစပ်ဆုံးခန့်မှန်းတွက်ချက်ပေးပါသည်။
* :guilabel:`Map Units` (မြေပုံယူနစ်) - အရွယ်အစားကို မြေပုံမြင်ကွင်း၏စကေးအတိုင်း စကေးကိုက်ဖော်ပြပါသည်။ ၎င်း၏တန်ဖိုးများသည် ကြီးလွန်းခြင်း သို့မဟုတ် ငယ်လွန်းခြင်းဖြစ်တတ်သောကြောင့် entry ဘေးရှိ |options| ကိုသုံး၍  အောက်ပါတို့အပေါ်အခြေခံ၍ တန်ဖိုးအပိုင်းအခြားအရွယ်အစားကိုကန့်သတ်ထားနိုင်ပါသည်-

  * :guilabel:`Minimum scale` (အနည်းဆုံးစကေး)နှင့် :guilabel:`Maximum scale` (အများဆုံးစကေး) - သတ်မှတ်ထားသော စကေးကန့်သတ်ချက်များကို မရောက်မချင်း တန်ဖိုးကို မြေပုံမြင်ကွင်း၏စကေးပေါ်မူတည်၍ စကေးကိုက်ပြုလုပ်ပေးပါသည်။ စကေးကန့်သတ်ချက်အပိုင်းအခြားကိုကျော်လွန်သွားပါက အနီးဆုံးစကေးကန့်သတ်ချက်ရှိ တန်ဖိုးကို ထားရှိမည်ဖြစ်သည်။
  * ``mm`` ဖြင့် :guilabel:`Minimum size` (အနည်းဆုံးအရွယ်အစား) နှင့် :guilabel:`Maximum size` (အများဆုံးအရွယ်အစား) - သတ်မှတ်ထားသော ကန့်သတ်ချက်များကို မရောက်မချင်း တန်ဖိုးကို မြေပုံမြင်ကွင်း၏စကေးပေါ်မူတည်၍ စကေးကိုက်ပြုလုပ်ပေးပါသည်။ ပမာဏထက်ကျော်လွန်နေပါက ကန့်သတ်ထားသည့်အရွယ်အစားကိုသာ ထားရှိမည်ဖြစ်သည်။

  .. _figure_adjust_scaling_units:


  .. figure:: img/adjust_scaling.png
     :align: center


     စကေးအပိုင်းအခြားချိန်ညှိခြင်း dialog

.. index:: Number format; Map scale bar
.. _number_formatting:


Number Formatting (ကိန်းဂဏန်း format ပြင်ဆင်ခြင်း)
---------------------------------------------------

Numeric formatters (ကိန်းဂဏန်း format ပြင်ဆင်ပေးသည့်အရာ) သည် ဖော်ပြပေးမည့် ကိန်းဂဏန်းတန်ဖိုးများ၏ format များကို အမျိုးမျိုးသော formatting နည်းများကိုအသုံးပြု၍ ပြင်ဆင်နိုင်ပါသည် (ဥပမာအားဖြင့် scientific notation (သိပ္ပံပညာရပ်ဆိုင်ရာ သင်္ကေတများ)၊ ငွေကြေးတန်ဖိုးများ၊ ရာခိုင်နှုန်းတန်ဖိုးများ စသဖြင့်)။ ၎င်း၏အသုံးပြုမှုတစ်ခုမှာ layout scale bar (Layout ရှိ စကေးဘား) သို့မဟုတ် fixed table (ပုံသေသတ်မှတ်ထားသောဇယား)တွင် စာသားများကို format ပြင်ဆင်သတ်မှတ်ခြင်း ဖြစ်သည်။

.. _figure_number_formatting:

.. figure:: img/number_formatting.png
   :align: center

   ကိန်းဂဏန်းတန်ဖိုးများကို format ပြင်ဆင်ခြင်း

Format အမျိုးအစားအမျိုးမျိုး ရရှိနိုင်ပြီး အများစုအတွက် အောက်ပါ ကိန်းဂဏန်းဆိုင်ရာရွေးချယ်စရာများအားလုံး သို့မဟုတ် တစိတ်တပိုင်းကို သတ်မှတ်နိုင်ပါသည်-

* |checkbox| :guilabel:`Show thousands separator` (ထောင်ပြည့်ကိန်းများ ခွဲခြားသည့်အရာအား ဖော်ပြခြင်း)
* |unchecked| :guilabel:`Show plus sign` (အပေါင်းလက္ခဏာအားဖော်ပြခြင်း)
* |unchecked| :guilabel:`Show trailing zeros` (နောက်လိုက် သုညများကိုဖော်ပြခြင်း)

သို့သော် ၎င်းတို့တွင်လည်း စိတ်ကြိုက်ပြင်ဆင်နိုင်သော setting များရှိပါသည်။ ပါဝင်သည့် အမျိုးအစားများမှာ-

* :guilabel:`General` သည် default အမျိုးအစားဖြစ်သည်- setting မပါရှိပဲ မူရင်း widget တွင် သတ်မှတ်ထားသည့်အတိုင်း တန်ဖိုးများကို ဖော်ပြပေးပါသည် သို့မဟုတ် global settting အတိုင်းသာ တန်ဖိုးများကို ဖော်ပြပါသည်။

* :guilabel:`Number` (ကိန်းဂဏန်း)

  * တန်ဖိုးများကို သတ်မှတ်ထားသော :guilabel:`Decimal places` (ဒဿမနေရာ) အရေအတွက်အတိုင်း သို့မဟုတ် ၎င်းတို့၏ :guilabel:`Significant figures` (ထင်ရှားသောပုံပန်းသဏ္ဍာန်) အတိုင်း :guilabel:`Round` (ပြောင်းလဲ) ပြုလုပ်ပေးနိုင်ပါသည်။
  * :guilabel:`Thousands separator` (ထောင်ပြည့်ကိန်းများ ခွဲခြားသည့်အရာ) နှင့် :guilabel:`Decimal separator` (ဒဿမကိန်းများခွဲခြားပေးသည့်အရာ) တို့ကိုလည်း စိတ်ကြိုက်ပြင်ဆင်နိုင်သည်။
* :guilabel:`Bearing` (လားရာ) တစ်ခု၏ text representation (စာသားဖော်ပြချက်) အတွက် အောက်ပါတို့ကို အသုံးပြုနိုင်သည်-

  * :guilabel:`Format` - ဖြစ်နိုင်ချေရှိသော တန်ဖိုးအပိုင်းအခြားများမှာ  ``E/W suffix (နောက်တွဲစကားလုံး)နှင့်အတူ 0 မှ 180°အတွင်း`` ၊ ``-180 မှ +180° အတွင်း`` နှင့် ``0 မှ 360° အတွင်း`` တို့ဖြစ်သည်။
  * :guilabel:`Decimal places` (ဒဿမကိန်းနေရာ) အရေအတွက်
* :guilabel:`Currency` သည် ငွေကြေးတန်ဖိုးတစ်ခုခု၏ text representation ကို ဖော်ပြရာတွင် အသုံးပြုနိုင်သည်။

  * :guilabel:`Prefix` (ရှေ့ဆက်စကားလုံး)
  * :guilabel:`Suffix` (နောက်တွဲစကားလုံး)
  * :guilabel:`Decimal places` (ဒဿမကိန်းနေရာ) အရေအတွက်
* :guilabel:`Fraction` သည် ဒဿမကိန်းတစ်ခုကို အပိုင်းကိန်းဖြင့်ဖော်ပြခြင်းဖြစ်သည်။ (ဥပမာ- *0.5* ဟု ဖော်ပြရမည့်အစား *1/2* ဟု ဖော်ပြခြင်းဖြစ်သည်)

  * |unchecked| :guilabel:`Use unicode super/subscript` ကို အမှန်ခြစ်ပြုလုပ်၍ ½ ကို :sup:`1/2` ဟု ပြောင်းလဲဖော်ပြနိုင်သည်။
  * |unchecked| :guilabel:`Use dedicated Unicode characters` (ထည့်သွင်းထားသည့် ယူနီကုဒ်သင်္ကေတများကိုအသုံးပြုခြင်း)
  * :guilabel:`Thousands separator` ကို စိတ်ကြိုက်သတ်မှတ်နိုင်သည်။
* :guilabel:`Percentage` သည် အောက်ဖော်ပြပါ setting များဖြင့် တန်ဖိုးများကို ``%`` ဖြင့် ဖော်ပြပါသည်-

  * number of :guilabel:`Decimal places` (ဒဿမကိန်းနေရာ) အရေအတွက်
  * :guilabel:`Scaling` သည် အမှန်တကယ်တန်ဖိုးများကို ရာခိုင်နှုန်းဖြင့် သတ်မှတ်ပြီးဖြစ်ပါက ၎င်းအတိုင်းပင် ထားရှိပြီး အကယ်၍ အပိုင်းကိန်းများဖြစ်နေပါက ရာခိုင်နှုန်းအဖြစ် ပြောင်းလဲဖော်ပြရာတွင် သုံးနိုင်သည်။
* ``2.56e+03`` ပုံစံဖြင့် :guilabel:`Scientific` notation (သိပ္ပံပညာရပ်ဆိုင်ရာသင်္ကေတ) များကို ဖော်ပြနိုင်သည်။ ၎င်းတွင်  :guilabel:`Decimal places` (ဒဿမကိန်းနေရာ) အရေအတွက်များကိုလည်း သတ်မှတ်နိုင်ပါသည်။

Setting များ၏ live preview (အကြိုတိုက်ရိုက်ကြည့်ရှုခြင်း) ကို :guilabel:`Sample` (နမူနာ) အခန်းအောက်တွင် ဖော်ပြထားပါသည်။

.. index::
   single: Rendering effects; Blending modes
.. _blend-modes:


Blending Modes (ရောစပ်ခြင်းနည်းလမ်းများ)
-----------------------------------------

QGIS တွင် ဒီဇိုင်းရေးဆွဲခြင်းနှင့်သက်ဆိုင်သည့် ပရိုဂရမ်များ (Graphics Program) များတွင် သိကောင်းသိနိုင်ပြီးဖြစ်သော tool များနှင့် အထူးပုံဖော်ပြသခြင်းဆိုင်ရာ ပြုလုပ်ချက်များ (rendering effects) ပြုလုပ်နိုင်ရန် ရွေးချယ်စရာအမျိုးမျိုးပါရှိပါသည်။ Blending modes (ရောစပ်ခြင်းနည်းလမ်းများ) ကို Layer နှင့် feature များတွင်သာမက print layout item များတွင်လည်း အသုံးပြုနိုင်ပါသည်-

* :guilabel:`Normal` သည် စံ ရောစပ်ခြင်းနည်းလမ်းဖြစ်ပြီး အပေါ်တွင်ရှိသော pixel ၏ alpha channel ကို ၎င်း၏အောက်တွင်ရှိသော pixel နှင့် ရောစပ်ခြင်းဖြစ်သည်။ သို့သော် အရောင်များမှာမူ ရောမသွားပေ။
* :guilabel:`Lighten` သည် အရှေ့တွင်ရှိသော (foreground) နှင့် အနောက်တွင်ရှိသော (background) pixel များမှ အစိတ်အပိုင်းတစ်ခုစီ၏ အမြင့်ဆုံးတန်ဖိုးများကို ရွေးချယ်ပေးပါသည်။ ရရှိလာသော ရလာဒ်များသည် ခပ်ကြမ်းကြမ်းဖြစ်တတ်သည်ကို သတိပြုရမည်။
* :guilabel:`Screen` သည် အရောင်ရင့်သော pixel များကိုအသုံးမပြုဘဲ အရောင်ဖျော့သော pixels များကိုသာ ရွေးချယ်၍ ရောစပ်ခြင်းဖြစ်သည်။ ဤနည်းလမ်းသည် item တစ်ခု၏ texture ကို အခြား item တစ်ခုနှင့်ပေါင်းစပ်ကြည့်လိုသောအချိန်တွင် အသုံးအဝင်ဆုံးဖြစ်ပါသည်။ (ဥပမာ - အခြား Layer တစ်ခု၏အသွင်အပြင်ကိုကြည့်ရန် hillshade ကိုအသုံးပြုခြင်း)
* :guilabel:`Dodge` သည် အပေါ်တွင်ရှိသော pixel၏ အလင်းတောက်ပမှုပေါ် အခြေခံပြီး အောက်တွင်ရှိသော pixels များကို တောက်ပ၍ စိုနေစေခြင်းဖြစ်သည်။ အပေါ်ရှိ pixel များ အရောင်တောက်လေ အောက်တွင်ရှိသော pixel များမှာ ပိုမိုအရောင်တောက်ပစေပြီး စိုလေဖြစ်သည်။ ဤနည်းလမ်းသည် အပေါ်ရှိ pixel များ အရောင်ဖျော့‌နေသောအခါမျိုးတွင် အသုံးပြုနိုင်သည်။ သို့မဟုတ်ပါက ရရှိလာသော အရောင်သည် အလွန်ရင့်နေပါလိမ့်မည်။
* :guilabel:`Addition` သည် item တစ်ခု၏ pixel တန်ဖိုးများကို အခြား item တစ်ခုသို့ ပေါင်းထည့်ခြင်းဖြစ်သည်။ အကယ်၍ တန်ဖိုးများသည်သည် အများဆုံးပမာဏ (RGB တွင်) ထက် ကျော်နေပါက အဖြူရောင်ကိုသာ မြင်ရမည်ဖြစ်သည်။ ဤနည်းလမ်းသည် feature များကို highlight လုပ်၍ ကြည့်ရှုလိုသည့်အချိန်မျိုးတွင် အလွန်အသုံးဝင်သည်။
* :guilabel:`Darken` သည် foreground pixel များနှင့် background pixel များနှစ်ခုလုံးရှိ အရောင်တန်ဖိုး အနည်းဆုံးရှိသော အပိုင်းများကိုသာဖော်ပြခြင်းဖြစ်သည်။ Lighten ကဲ့သို့ပင် ရရှိလာသော အရောင်သည် ခပ်ကြမ်းကြမ်းဖြစ်နေပေလိမ့်မည်။
* :guilabel:`Multiply` သည် အပေါ်တွင်ရှိသော item ၏ pixel တန်ဖိုးများနှင့် အောက်တွင်ရှိသော item တို့ရှိ သက်ဆိုင်သည့် pixel တန်ဖိုးများကို မြှောက်၍ ဖော်ပြခြင်းဖြစ်ရာ ရရှိလာသော အရောင်သည် အရောင်ပိုရင့်သွားပေလိမ့်မည်။
* :guilabel:`Burn` သည် အပေါ်တွင်ရှိသော item ရှိ အရောင်ရင့်သော pixel များသည် အောက်တွင်ရှိသော item များကို ပို၍ အရောင်ရင့်စေပါသည်။ ၎င်းကို အသုံးပြု၍ အောက်တွင်ရှိသော layer များကို ပိုမိုပေါ်လွင်စေပါသည်။
* :guilabel:`Overlay` သည် Multiply နှင့် screen blending mode နှစ်ခုကို ရောစပ်ထားခြင်းဖြစ်သည်။ အရောင်ဖျော့သော အပိုင်းသည် ပိုမိုအရောင်ဖျော့သွားပြီး အရောင်ရင့်သည့်နေရာများကိုလည်း ပိုမိုရင့်‌သွားစေပါသည်။
* :guilabel:`Soft light` Overlay နှင့်သဘောတရားချင်းတူညီသော်လည်း Multiply နှင့် screen blending mode နှစ်ခုကို ပေါင်းစပ်ထားသည့်အစား burn နှင့် dodge blending mode နှစ်ခုကို ရောနှောထားခြင်းဖြစ်သည်။ ၎င်းသည် image ပေါ်ရှိ အရောင်ဖျော့သောနေရာအား ပိုမိုတောက်ပစေပါသည်။
* :guilabel:`Hard light` သည် overlay mode နှင့်အလွန်ဆင်တူပြီး image ပေါ်တွင် အလင်းပြင်းပြင်းပုံရိပ်တစ်ခုချပေးပါသည်။
* :guilabel:`Difference` သည် အောက်တွင်ရှိသော pixel မှ အပေါ်တွင်ရှိသော pixel ကို နှုတ်ခြင်းဖြင့်ဖြစ်စေ အပေါ်တွင်ရှိသော pixel မှ အောက်တွင်ရှိသော pixel ကိုနှုတ်ခြင်းဖြင့်ဖြစ်စေ ခြားနားခြင်းသည် အမြဲတမ်းအပေါင်းတန်ဖိုးရအောင် ဆောင်ရွက်ခြင်းဖြစ်သည်။ အနက်ရောင်ဖြင့် ရောစပ်ခြင်းသည် မည်သည့်ပြောင်းလဲမှုကိုမျှ ရရှိမည်မဟုတ်ပေ။ အဘယ့်ကြောင့်ဆိုသော် အရောင်များအားလုံးဖြင့် ခြားနားခြင်းသည် သုညဖြစ်သောကြောင့် ဖြစ်သည်။
* :guilabel:`Subtract` သည် item တစ်ခုမှ pixel တန်ဖိုးများကို အခြား item တစ်ခု pixel တန်ဖိုးများမှ နှုတ်ခြင်းဖြစ်ပြီး ခြားနားခြင်းတန်ဖိုးသည် အနှုတ်တန်ဖိုးဖြစ်ပါက အနက်ရောင်သာလျှင် ဖော်ပြမည်ဖြစ်သည်။

.. _figure_blend_modes:

.. figure:: img/blending_modes.png
   :align: center

   လိမ္မော်ရောင်ရှိသော feature တစ်ခုပေါ်တွင် အစိမ်းရောင် feature တစ်ခုကို အသုံးပြုထားသည့် blending mode ဥပမာများ

   အထက်မှ အောက်၊ ဝဲမှ ယာသို့ - Normal -- Lighten ၊ Screen ၊ Dodge ၊ Addition -- Difference ၊ Subtract -- Darken ၊ Multiply ၊ Burn -- Overlay ၊ Soft light ၊ Hard light


.. _blending_clipping:


Layer တစ်ခုသည် :ref:`renders layers as a group (အုပ်စုတစ်ခုအနေဖြင့် rendering ပြုလုပ်ထားသော) <render_as_group>` အုပ်စုတစ်ခု၏ တစိတ်တပိုင်းဖြစ်နေသောအခါ ၎င်းကို rendering ပြုလုပ်ရန်အတွက် ထပ်ဆောင်း blending mode များလည်း ရှိပါသည်။ ၎င်းတွင် Layer တစ်ခုကို ဒုတိယ "mask" layer ဖြင့် ဖြတ်တောက် (clip) ၍ ပုံဖော်ပြသနိုင်သော နည်းလမ်းများကို ပံ့ပိုးပေးထားပါသည်။
* :guilabel:`Masked By Below` (အောက်တွင်ရှိသော pixel များဖြင့် ဖုံးအုပ်ခြင်း) - ထွက်လာသော ရလာဒ်သည် အပေါ်တွင်ရှိသော pixel ဖြစ်ပြီး ၎င်း၏ opacity (အလင်းပိတ်နှုန်း) ကို အောက်တွင်ရှိသော pixel ၏ opacity (အလင်းပိတ်နှုန်း) ဖြင့် လျှော့ချထားခြင်းဖြစ်သည်။
* :guilabel:`Mask Below` (အောက်တွင်ရှိသော pixel ကို ဖုံးအုပ်ခြင်း) - ထွက်လာသော ရလာဒ်သည် အောက်တွင်ရှိသော pixel ဖြစ်ပြီး ၎င်း၏ opacity (အလင်းပိတ်နှုန်း) ကို အပေါ်တွင်ရှိသော pixel ၏ opacity (အလင်းပိတ်နှုန်း) လျှော့ချထားခြင်းဖြစ်သည်။
* :guilabel:`Inverse Masked By Below` (‌အောက်တွင်ရှိသော pixel ဖြင့် ဖုံးအုပ်ခြင်းကို ဆန့်ကျင်ဘက်သို့ပြောင်းလဲခြင်း) - ရရှိလာသောရလာဒ်သည် အပေါ်တွင်ရှိသော pixel ဖြစ်ပြီး ၎င်း၏ opacity (အလင်းပိတ်နှုန်း) ကို အောက်တွင်ရှိသော pixel ၏ opacity (အလင်းပိတ်နှုန်း) ပြောင်းပြန်တန်ဖိုးဖြင့် လျှော့ချထားခြင်းဖြစ်သည်။
* :guilabel:`Inverse Mask Below` (အောက်တွင်ရှိသော pixel အား ဖုံးအုပ်ခြင်းကို ဆန့်ကျင်ဘက်သို့ပြောင်းလဲခြင်း) - ရလာဒ်သည် အောက်တွင်ရှိသော pixel ဖြစ်ပြီး ၎င်း၏ opacity (အလင်းပိတ်နှုန်း) ကို အပေါ်တွင်ရှိသော pixel ၏ pacity (အလင်းပိတ်နှုန်း) ပြောင်းပြန်တန်ဖိုးဖြင့် လျှော့ချထားခြင်းဖြစ်သည်။
* :guilabel:`Paint Inside Below` သည် အပေါ်တွင်ရှိသော pixel ကို အောက်တွင်ရှိသော pixel ၏ အထက်တွင် ရောစပ်ထားခြင်းဖြစ်ပြီး  အပေါ်တွင်ရှိသော pixel ၏ opacity (အလင်းပိတ်နှုန်း) ကို အောက်တွင်ရှိသော pixel ၏ opacity (အလင်းပိတ်နှုန်း) ဖြင့် လျှော့ချထားပါသည်။
* :guilabel:`Paint Below Inside` - အောက်တွင်ရှိသော pixel ကို အပေါ်တွင်ရှိသော pixel ၏ အထက်တွင် ရောစပ်ထားခြင်းဖြစ်ပြီး အောက်တွင်ရှိသော pixel ၏ opacity (အလင်းပိတ်နှုန်း) ကို အပေါ်တွင်ရှိသော pixel ၏ opacity (အလင်းပိတ်နှုန်း) ဖြင့် လျှော့ချထားပါသည်။


.. _figure_blend_clipping_modes:


.. figure:: img/blending_clipping.png
   :align: center

   အုပ်စုတစ်ခုရှိ အပေါ်တွင်ရှိသော အစိမ်းရောင် Layer တွင် အသုံးပြုထားသည့် blend clipping mode ဥပမာများ 


   **A**: Mask Below **B**: Masked By Below **C**: Paint Below Inside **D**: Inverse Mask Below **E**: Inverse Masked By Below **F**: Paint Inside Below


.. index:: Data-defined override
.. _data_defined:


Data defined override setup (Data ဖြင့်သတ်မှတ်ထားသော အစားထိုးလုပ်ဆောင်ခြင်းဆိုင်ရာ setup)
------------------------------------------------------------------------------------------

Vector layer properties dialog သို့မဟုတ် Print layout ရှိ settings ထဲမှ ရွေးချယ်စရာများ၏ ဘေးတွင် |dataDefine| :sup:`Data defined override` icon ကို တွေ့ရမည်ဖြစ်သည်။ Layer attribute များ သို့မဟုတ် item setting များ၊ ကြိုတင်ပြင်ဆင်ထားသော သို့မဟုတ် စိတ်ကြိုက်ပြင်ဆင်ထားသောလုပ်ဆောင်ချက်များနှင့် :ref:`variables (ကိန်းရှင်) <general_tools_variables>` များပေါ်တွင်အခြေခံထားသည့် :ref:`expressions (ခိုင်းစေချက်များ) <vector_expressions>` ကိုအသုံးပြုခြင်းသည် parameters များအတွက် ပြောင်းလဲနေသည့်တန်ဖိုးများကို သတ်မှတ်ပေးစေနိုင်ပါသည်။ ဤ tool ကို အသုံးပြုပါက ၎င်းတို့၏ ပုံမှန်တန်ဖိုးများကို ထည့်သွင်းမစဉ်းစားတော့ဘဲ widget မှ ရရှိလာသည့် တန်ဖိုးများကို parameter များတွင် အသုံးပြုမည်ဖြစ်ပါသည်။


The data defined override widget (Data ဖြင့်သတ်မှတ်ထားသော အစားထိုးလုပ်ဆောင်ခြင်းဆိုင်ရာ widget)
................................................................................................

|dataDefine| :sup:`Data defined override` icon ကိုနှိပ်လိုက်လျှင် အောက်တွင်ဖော်ပြထားသော ထည့်သွင်းစရာများကို ပြသမည်ဖြစ်ပါသည်- 

* :guilabel:`Description...` (ဖော်ပြချက်) သည် ‌option ကိုဖွင့်ထားပါက သင့်လျော်သော input အမျိုးအစားနှင့် ၎င်း၏ လက်ရှိအဓိပ္ပာယ်ဖွင့်ဆိုချက်ကို ဖော်ပြပေးပါမည်။ Widget ပေါ်တွင် mouse ကိုတင်ထားပါက အဆိုပါအချက်အလက်များကို ဖော်ပြပေးမည်ဖြစ်ပါသည်။
* :guilabel:`Store data in the project` (Project အတွင်း ဒေတာသိမ်းဆည်းခြင်း) သည် :ref:`vector_auxiliary_storage` mechanism ကိုအသုံးပြု၍ property များကို သိမ်းဆည်းရန် လုပ်ဆောင်နိုင်သော နေရာတစ်ခုဖြစ်ပါသည်။ 
* :guilabel:`Field type` (Field အမျိုးအစား) သည် ဆီလျော်သည့် input အမျိုးအစားနှင့် ကိုက်ညီသည့် field ကို layer မှရွေးချယ်နိုင်ရန် အသုံးပြုရမည့် entry ဖြစ်သည်။
* :guilabel:`Color` (အရောင်) သည် Widget ကို color property နှင့် ချိတ်ဆက်‌လိုက်သောအခါ လက်ရှိအသုံးပြုနေသော :ref:`project's colors <project_colors>` scheme ၏ အစိတ်အပိုင်းတစ်ခုအဖြစ် အရောင်များကို ရွေးချယ်နိုင်မည်ဖြစ်သည်။
* :guilabel:`Variable` (ကိန်းရှင်) သည် အသုံးပြုသူမှ သတ်မှတ်ထားသော :ref:`variables (ကိန်းရှင်များ) <general_tools_variables>` ကို ဝင်ရောက်ရယူနိုင်မည့် menu ဖြစ်သည်။ 
* :guilabel:`Edit...` ခလုတ်သည် :guilabel:`Expression String Builder` dialog အသုံးပြု၍ expression များကို ဖန်တီးရန် သို့မဟုတ် ပြင်ဆင်ရန်ဖြစ်သည်။ Expresssion ထဲတွင်ထည့်သွင်းမှု မှန်ကန်စေရန် ရရှိနိုင်သည့်ရလာဒ်ကို dialog အတွင်းတွင် ဖော်ပြပေးနေလိမ့်မည်။
* :guilabel:`Paste` နှင့် :guilabel:`Copy` ခလုတ်များကို အသုံးပြု၍ ကူးယူ/ချခြင်းများ ပြုလုပ်နိုင်သည်။
* :guilabel:`Clear` ခလုတ်သည် setup များကို ဖယ်ရှားရန် အသုံးပြုနိုင်ပါသည်။ 
* ကိန်းဂဏန်းနှင့်အရောင်များ၏ ဂုဏ်သတ္တိများအတွက် feature data တစ်ခုသည် ဂုဏ်သတ္တိတွင် မည်သို့အသုံးပြုမည်ကို ချိန်ညှိရန် :guilabel:`Assistant...` ကို အသုံးပြုနိုင်ပါသည်။ (အသေးစိတ်အချက်အလက်များကို  :ref:`အောက်တွင် <data_defined_assistant>` တွင် ဆက်လက်ကြည့်ရှုနိုင်ပါသည်) 


.. tip:: **Data override ကို ဖွင့်ရန် သို့မဟုတ် ပိတ်ရန် right-click ကို အသုံးပြုပါ။**

 Data-defined override option ကို မှန်ကန်စွာထည့်သွင်းနိုင်ပါက icon သည် အဝါရောင် |dataDefineOn| သို့မဟုတ် |dataDefineExpressionOn| ဖြင့် ပြသမည်ဖြစ်ပြီး မှားယွင်းစွာ ထည့်သွင်းထားလျှင် icon သည် အနီရောင် |dataDefineError| သို့မဟုတ် |dataDefineExpressionError| ဖြင့် ပြသနေပေလိမ့်မည်။

 Widget ပေါ်တွင် right-click နှိပ်ခြင်းဖြင့် |dataDefine| :sup:`Data-defined override` ခလုတ်ကို အဖွင့်အပိတ် ပြုလုပ်နိုင်ပါသည်။ 


.. _data_defined_assistant:


Using the data-defined assistant interface (Data-defined အကူအညီ interface ကိုအသုံးပြုခြင်း)
............................................................................................

|dataDefine| :sup:`Data-defined override` ခလုတ်သည် အရွယ်အစား၊ လှည့်ထောင့် (rotation)၊ အလင်းပိတ်နှုန်း သို့မဟုတ် အရောင်ကဲ့သို့သော ဂုဏ်သတ္တိတစ်ခုခုနှင့်ဆက်နွယ်နေမည်ဆိုပါက feature တစ်ခုချင်းစီအတွက် parameter များတွင် data များကို မည်သို့အသုံးချမည်ကို ပြောင်းလဲပေးနိုင်ရန် :guilabel:`Assistant...` ကို အသုံးပြုနိုင်သည်။ ထို Assistant တွင် အောက်ဖော်ပြပါတို့ကို လုပ်ဆောင်နိုင်သည်-

* :guilabel:`Input` (ထည့်သွင်းမည့်) data ကိုသတ်မှတ်ပါ။ ဆိုလိုသည်မှာ-

  * :guilabel:`Source` (အရင်းအမြစ်) သည် field တစ်ခု သို့မဟုတ် |expression| :ref:`expression <vector_expressions>` တစ်ခုကို သုံး၍ ကိုယ်စားပြုမည့်အချက်အလက်များ
  * ကိုယ်စားပြုမည့် တန်ဖိုးအပိုင်းအခြား - ထိုတန်ဖိုးများကို ကိုယ်တိုင်ထည့်သွင်းပေးသည် သို့မဟုတ် :guilabel:`Source` expression မှ ရရှိလာသည့် အနည်းဆုံးနှင့်အများဆုံး တန်ဖိုးများကို |refresh| :sup:`Fetch value range from layer` ကိုသုံး၍ အလိုအလျောက် ဖြည့်သွင်းပေးစေနိုင်သည်။
* |unchecked| :guilabel:`Apply transform curve` (မျဉ်းကွေးအဖြစ်ပုံစံပြောင်းလဲခြင်း) - ရလာဒ်တန်ဖိုးများကို ပုံသေအနေဖြင့် ထည့်သွင်းသည့် input feature များတွင် (setting အတွက် အောက်တွင်ကြည့်နိုင်ပါသည်) linear scale (မျဉ်းဖြောင့်စကေး) အတိုင်း အသုံးပြုသွားမည်ဖြစ်သည်။ ဤ logic ကို အစားထိုးလုပ်ဆောင်ရန် |unchecked| :guilabel:`Apply transform curve` ကို အမှန်ခြစ်ခြစ်၍ break points များပေါင်းထည့်ရန် graphic တွင် click နှိပ်ပြီး ထို့နောက် စိတ်ကြိုက်ဖြန့်ကျက်မှုတစ်ခု ပြုလုပ်ရန် point များကို ဖိဆွဲထည့်ပါ။
* :guilabel:`Output` တန်ဖိုးများကိုသတ်မှတ်ပါ။ သတ်မှတ်ရန်ရွေးချယ်စရာများသည် parameter များအလိုက် ပြောင်းလဲနေမည်ဖြစ်သည်။ ယေဘုယျအားဖြင့် အောက်ပါအတိုင်းသတ်မှတ်နိုင်သည်-

  * အရောင် setting တစ်ခုအတွက် :ref:`color ramp (ရောင်စဉ်တန်း) <color-ramp>` ကို တန်ဖိုးများအတွက် အသုံးပြုပြီး Null တန်ဖိုးများအတွက် အရောင်တစ်ခုတည်းကိုသာ အသုံးပြုမည်ဖြစ်သည်။
  * အခြား setting များအတွက်မူ အနိမ့်ဆုံးနှင့် အမြင့်ဆုံးတန်ဖိုးများကို ရွေးချယ်ထားသည့် ဂုဏ်သတ္တိများတွင် အသုံးပြုနိုင်ပြီး အရွယ်အစား၊ ထောင့်၊ အလင်းပိတ်နှုန်း ကဲ့သို့သော တန်ဖိုးများကို လျစ်လျူရှုထားသော သို့မဟုတ် NULL source features များအတွက် အသုံးပြုပါသည်။  
  * အရွယ်အစားဂုဏ်သတ္တိများအတွက် **Flannery** ၊ **Exponential** ၊ **Surface** ၊ **Radius** သို့မဟုတ် **Linear** ဖြင့် ဖော်ပြနိုင်သည့် :guilabel:`Scale method` ကို အသုံးပြုပါသည်။ 
  * :guilabel:`Scale method` သည် exponential (အက္ခရာထပ်ကိန်းများ) အမျိုးအစားဖြစ်နေသည့်အခါတွင်လည်းကောင်း သို့မဟုတ် အလင်းပိတ်နှုန်းကို ပြင်ဆင်သည့်အခါတွင်လည်းကောင်း data ကို scaling လုပ်ရန်အတွက် :guilabel:`Exponent` ကို အသုံးပြုနိုင်ပါသည်။ 

ဂုဏ်သတ္တိများနှင့် ကိုက်ညီသောအခါ dialog ၏ ညာဘက်တွင် value scaling (စကေးချိန်ညှိထားသည့်တန်ဖိုး) ကို ကိုင်တွယ်နိုင်ရန် live-update ကို ကြိုတင်ကြည့်ရှုနိုင်ပါသည်။ 


.. _figure_symbology_size_assistant:


.. figure:: img/varying_size_assistant.png
   :align: center

   Passenger field တန်ဖိုးပေါ်မူတည်၍ feature အရွယ်အစားကို စကေးချိန်ညှိခြင်း


အထက်ဖော်ပြပါ အရွယ်အစားပြောင်းလဲနိုင်သည့် assistant ထဲတွင်ဖော်ပြထားသော တန်ဖိုးများကို 'Data-defined override' ဖြင့် အောက်ပါအတိုင်း ပြင်ဆင်သတ်မှတ်နိုင်ပါသည်-::

 coalesce(scale_exp("passengers", 9, 2000, 1, 10, 0.57), 0)


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.


.. |3d| image:: /static/common/3d.png
   :width: 1.5em
.. |addGroup| image:: /static/common/mActionAddGroup.png
   :width: 1.5em
.. |addVirtualLayer| image:: /static/common/mActionAddVirtualLayer.png
   :width: 1.5em
.. |allEdits| image:: /static/common/mActionAllEdits.png
   :width: 1.5em
.. |atlasNext| image:: /static/common/mActionAtlasNext.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |collapseTree| image:: /static/common/mActionCollapseTree.png
   :width: 1.5em
.. |colorBox| image:: /static/common/mIconColorBox.png
   :width: 1.5em
.. |colorPicker| image:: /static/common/mIconColorPicker.png
   :width: 1.5em
.. |colorSwatches| image:: /static/common/mIconColorSwatches.png
   :width: 1.5em
.. |colorWheel| image:: /static/common/mIconColorWheel.png
   :width: 1.5em
.. |dataDefine| image:: /static/common/mIconDataDefine.png
   :width: 1.5em
.. |dataDefineError| image:: /static/common/mIconDataDefineError.png
   :width: 1.5em
.. |dataDefineExpressionError| image:: /static/common/mIconDataDefineExpressionError.png
   :width: 1.5em
.. |dataDefineExpressionOn| image:: /static/common/mIconDataDefineExpressionOn.png
   :width: 1.5em
.. |dataDefineOn| image:: /static/common/mIconDataDefineOn.png
   :width: 1.5em
.. |dbManager| image:: /static/common/dbmanager.png
   :width: 1.5em
.. |deleteSelected| image:: /static/common/mActionDeleteSelected.png
   :width: 1.5em
.. |deselectActiveLayer| image:: /static/common/mActionDeselectActiveLayer.png
   :width: 1.5em
.. |deselectAll| image:: /static/common/mActionDeselectAll.png
   :width: 1.5em
.. |duplicateLayer| image:: /static/common/mActionDuplicateLayer.png
   :width: 1.5em
.. |editCopy| image:: /static/common/mActionEditCopy.png
   :width: 1.5em
.. |editMetadata| image:: /static/common/editmetadata.png
   :width: 1.2em
.. |editableEdits| image:: /static/common/mIconEditableEdits.png
   :width: 1em
.. |elevationscale| image:: /static/common/elevationscale.png
   :width: 1.5em
.. |expandNewTree| image:: /static/common/mActionExpandNewTree.png
   :width: 1.5em
.. |expandTree| image:: /static/common/mActionExpandTree.png
   :width: 1.5em
.. |expression| image:: /static/common/mIconExpression.png
   :width: 1.5em
.. |expressionFilter| image:: /static/common/mIconExpressionFilter.png
   :width: 1.5em
.. |expressionSelect| image:: /static/common/mIconExpressionSelect.png
   :width: 1.5em
.. |filePrint| image:: /static/common/mActionFilePrint.png
   :width: 1.5em
.. |fileSave| image:: /static/common/mActionFileSave.png
   :width: 1.5em
.. |filterMap| image:: /static/common/mActionFilterMap.png
   :width: 1.5em
.. |folder| image:: /static/common/mActionFolder.png
   :width: 1.5em
.. |formSelect| image:: /static/common/mIconFormSelect.png
   :width: 1.5em
.. |formView| image:: /static/common/mActionFormView.png
   :width: 1.2em
.. |hideAllLayers| image:: /static/common/mActionHideAllLayers.png
   :width: 1.5em
.. |hideDeselectedLayers| image:: /static/common/mActionHideDeselectedLayers.png
   :width: 1.5em
.. |hideSelectedLayers| image:: /static/common/mActionHideSelectedLayers.png
   :width: 1.5em
.. |history| image:: /static/common/mActionHistory.png
   :width: 1.5em
.. |identify| image:: /static/common/mActionIdentify.png
   :width: 1.5em
.. |identifyByFreehand| image:: /static/common/mActionIdentifyByFreehand.png
   :width: 1.5em
.. |identifyByPolygon| image:: /static/common/mActionIdentifyByPolygon.png
   :width: 1.5em
.. |identifyByRadius| image:: /static/common/mActionIdentifyByRadius.png
   :width: 1.5em
.. |identifyByRectangle| image:: /static/common/mActionIdentifyByRectangle.png
   :width: 1.5em
.. |inOverview| image:: /static/common/mActionInOverview.png
   :width: 1.5em
.. |indicatorBadLayer| image:: /static/common/mIndicatorBadLayer.png
   :width: 1.5em
.. |indicatorEmbedded| image:: /static/common/mIndicatorEmbedded.png
   :width: 1.5em
.. |indicatorFilter| image:: /static/common/mIndicatorFilter.png
   :width: 1.5em
.. |indicatorLowAccuracy| image:: /static/common/mIndicatorLowAccuracy.png
   :width: 1.5em
.. |indicatorMemory| image:: /static/common/mIndicatorMemory.png
   :width: 1.5em
.. |indicatorNoCRS| image:: /static/common/mIndicatorNoCRS.png
   :width: 1.5em
.. |indicatorNonRemovable| image:: /static/common/mIndicatorNonRemovable.png
   :width: 1.5em
.. |indicatorNotes| image:: /static/common/mIndicatorNotes.png
   :width: 1.5em
.. |indicatorOffline| image:: /static/common/mIndicatorOffline.png
   :width: 1.5em
.. |indicatorTemporal| image:: /static/common/mIndicatorTemporal.png
   :width: 1.5em
.. |invertSelection| image:: /static/common/mActionInvertSelection.png
   :width: 1.5em
.. |labelingSingle| image:: /static/common/labelingSingle.png
   :width: 1.5em
.. |labelmask| image:: /static/common/labelmask.png
   :width: 1.5em
.. |mapIdentification| image:: /static/common/mActionMapIdentification.png
   :width: 1.5em
.. |messageLog| image:: /static/common/mMessageLog.png
   :width: 1.5em
.. |networkAndProxy| image:: /static/common/network_and_proxy.png
   :width: 1.5em
.. |openTable| image:: /static/common/mActionOpenTable.png
   :width: 1.5em
.. |options| image:: /static/common/mActionOptions.png
   :width: 1em
.. |osx| image:: /static/common/osx.png
   :width: 1em
.. |rasterHistogram| image:: /static/common/rasterHistogram.png
   :width: 1.5em
.. |record| image:: /static/common/mActionRecord.png
   :width: 1.5em
.. |refresh| image:: /static/common/mActionRefresh.png
   :width: 1.5em
.. |removeLayer| image:: /static/common/mActionRemoveLayer.png
   :width: 1.5em
.. |search| image:: /static/common/search.png
   :width: 1.5em
.. |selectAll| image:: /static/common/mActionSelectAll.png
   :width: 1.5em
.. |selectColor| image:: /static/common/selectcolor.png
.. |selectColorRamp| image:: /static/common/selectcolorramp.png
.. |selectDistance| image:: /static/common/mAlgorithmSelectDistance.png
   :width: 1.5em
.. |selectFreehand| image:: /static/common/mActionSelectFreehand.png
   :width: 1.5em
.. |selectLocation| image:: /static/common/mAlgorithmSelectLocation.png
   :width: 1.5em
.. |selectPolygon| image:: /static/common/mActionSelectPolygon.png
   :width: 1.5em
.. |selectRadius| image:: /static/common/mActionSelectRadius.png
   :width: 1.5em
.. |selectRectangle| image:: /static/common/mActionSelectRectangle.png
   :width: 1.5em
.. |selectString| image:: /static/common/selectstring.png
   :width: 2.5em
.. |showAllLayers| image:: /static/common/mActionShowAllLayers.png
   :width: 1.5em
.. |showPresets| image:: /static/common/mActionShowPresets.png
   :width: 1.5em
.. |showSelectedLayers| image:: /static/common/mActionShowSelectedLayers.png
   :width: 1.5em
.. |stopwatch| image:: /static/common/mIconStopwatch.png
   :width: 1.5em
.. |stylePreset| image:: /static/common/stylepreset.png
   :width: 1.5em
.. |symbology| image:: /static/common/symbology.png
   :width: 2em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
.. |symbologyRemove| image:: /static/common/symbologyRemove.png
   :width: 1.5em
.. |toggleAllLayers| image:: /static/common/mActionToggleAllLayers.png
   :width: 1.5em
.. |toggleEditing| image:: /static/common/mActionToggleEditing.png
   :width: 1.5em
.. |toggleSelectedLayers| image:: /static/common/mActionToggleSelectedLayers.png
   :width: 1.5em
.. |transparency| image:: /static/common/transparency.png
   :width: 1.5em
.. |unchecked| image:: /static/common/unchecked.png
   :width: 1.3em
.. |zoomActual| image:: /static/common/mActionZoomActual.png
   :width: 1.5em
.. |zoomToLayer| image:: /static/common/mActionZoomToLayer.png
  :width: 1.5em