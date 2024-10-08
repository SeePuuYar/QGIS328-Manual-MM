.. index:: Layout; Map item
.. _layout_map_item:

The Map Item (မြေပုံ Item)
===========================

.. only:: html

   .. contents::
      :local:


မြေပုံ item သည် မြေပုံ canvas တွင် ဖန်တီးခဲ့သောမြေပုံကိုပြသပေးသည့် ပင်မ frame ဖြစ်သည်။ :ref:`Item များဖန်တီးခြင်းဆိုင်ရာညွှန်ကြားချက်များ <create_layout_item>` ကိုလိုက်နာ၍ :ref:`interact_layout_item` တွင် ဖော်ပြထားသည့်နည်းလမ်းအတိုင်းကိုင်တွယ်နိုင်မည့် မြေပုံ item အသစ်တစ်ခုထည့်သွင်းရန် |addMap| :guilabel:`Add Map` tool ကိုအသုံးပြုပါ။

Default အားဖြင့် မြေပုံ item အသစ်တစ်ခုသည် :ref:`မြေပုံ canvas <label_mapview>` ၏ extent (နယ်ပယ်အကျယ်အဝန်း) နှင့် မြင်နိုင်သော layer များပါဝင်သော မြေပုံ canvas ၏ လက်ရှိ အခြေအနေကို ပြသပေးသည်။ ၎င်းကို :guilabel:`Item Properties` panel မှတစ်ဆင့် စိတ်ကြိုက်ပြင်ဆင်နိုင်သည်။ ဤ feature တွင် :ref:`item များ၏ဘုံဂုဏ်သတ္တိများ <item_common_properties>` အပြင် အောက်ပါလုပ်ဆောင်ချက်များပါရှိသည်-

.. _figure_layout_map:

.. figure:: img/map_mainproperties.png
   :align: center

   မြေပုံ Item ဂုဏ်သတ္တိများ Panel


The Toolbar (ကိရိယာတန်ဆာပလာများပါဝင်သော ဘား)
---------------------------------------------

မြေပုံ၏ :guilabel:`Item Properties` panel တွင် အောက်ပါလုပ်ဆောင်ချက်များပါရှိသော toolbar တစ်ခုထည့်သွင်းထားသည်- 

* |refresh| :sup:`Update map preview` (မြေပုံ အကြိုကြည့်ရှုခြင်းအား update ပြုလုပ်ပါ)
* |setToCanvasExtent| :sup:`Set map canvas to match main canvas extent` (အဓိက canvas extent နှင့်ကိုက်ညီစေရန် မြေပုံ canvas ကို သတ်မှတ်ပါ)
* |viewExtentInCanvas| :sup:`View current map extent in main canvas` (အဓိက canvas ထဲတွင် လက်ရှိ မြေပုံ extent အား ကြည့်ရှုပါ)
* |setToCanvasScale| :sup:`Set map scale to match main canvas scale` (အဓိက canvas စကေးနှင့်ကိုက်ညီစေရန် မြေပုံစကေးကို သတ်မှတ်ပါ)
* |viewScaleInCanvas| :sup:`Set main canvas to match current map scale` (လက်ရှိမြေပုံစကေးနှင့်ကိုက်ညီစေရန် အဓိက canvas ကိုသတ်မှတ်ပါ)
* |showBookmarks| :sup:`Bookmarks` - ရှိပြီးသား spatial bookmark တစ်ခုနှင့် ကိုက်ညီမှုရှိစေရန် မြေပုံ item extent ကို သတ်မှတ်ပါ။
* |moveItemContent| :sup:`Interactively edit map extent` - မြေပုံ item အတွင်းတွင် ရွှေ့၍ မြင်ကွင်းချုံ့ခြင်း/ချဲ့ခြင်းများကို အပြန်အလှန်လုပ်ဆောင်ပေးပါသည်။
* |labelingSingle| :sup:`Labeling settings` - Layout မြေပုံ item extent ထဲတွင် feature အညွှန်း၏ လုပ်ဆောင်ချက်များ (နေရာချထားမှု၊ မြင်နိုင်မှု...) ကို ကိုင်တွယ်နိုင်သည် -
  

  * :guilabel:`Margin from map edges` (မြေပုံအစွန်းများမှ margin) တစ်ခုအားသတ်မှတ်ပါ၊ အညွှန်းများကိုဖော်ပြခြင်းမပြုမည့် မြေပုံ item ၏ကန့်သတ်ချက်များမှ data ဖြင့်သတ်မှတ်ပေးနိုင်သောအကွာအဝေးတစ်ခု။
  * |unchecked| :guilabel:`Allow truncated labels on edges of map` - မြေပုံ item ၏ ခွင့်ပြုသော extent ထက်ကျော်လွန်၍ မြေပုံ၏ပြင်ပသို့တစ်စိတ်တစ်ပိုင်းကျရောက်နေသော အညွှန်းများ အားပြသခြင်းပြု/မပြု ထိန်းချုပ်ပေးပါသည်။ အမှန်ခြစ်ပေးခဲ့လျှင် ဤ အညွှန်းများကိုဖော်ပြပေးမည်ဖြစ်သည် (မြင်နိုင်သောနေရာအတွင်းတွင် အပြည့်အဝနေရာချထားရန် မဖြစ်နိုင်သောအခါ)။ အမှန်ခြစ်ဖြုတ်ထားခဲ့လျှင် တစ်စိတ်တစ်ပိုင်းသာမြင်ရသော အညွှန်းများကို ပြသမည်မဟုတ်ပါ၊ 
  * :guilabel:`Label blocking items`- အခြား layout item များ (စကေးဘားများ၊ မြောက်အရပ်ပြမြှားများ၊ ထည့်သွင်းထားသောမြေပုံများ ၊ အစရှိသဖြင့်) အား **လက်ရှိရွေးချယ်ထားသော** မြေပုံ item ထဲရှိ အညွှန်းများအတွက် ပိတ်ကွယ်နေသောအရာများ (blocker) အဖြစ် မှတ်ယူစေမည်ဖြစ်သည်။ ဤနည်းဖြင့် မည်သည့်မြေပုံအညွှန်းများကိုမဆို ၎င်းအရာများအောက်သို့ ရောက်မသွားစေရန်ကာကွယ်ပေးသည် - အညွှန်းတပ်သည့်စနစ်သည် သင့်တော်သည့်နေရာတွင် အဆိုပါအညွှန်းများအားနေရာချပေးခြင်း ဖြစ်စေနိုင်သလို ၎င်းတို့အားလုံးကို ပယ်ပစ်ခြင်းလည်း ဖြစ်စေနိုင်ပါသည်။
    
   
    :guilabel:`Margin from map edges` တစ်ခုကို သတ်မှတ်ထားပါက အမှန်ခြစ်ထားသော layout item များမှ သတ်မှတ်ထားသောအကွာအဝေးထက်ပိုနီးသော နေရာတွင် မြေပုံအညွှန်းများကို နေရာချထားမည်မဟုတ်ပါ။
    
  * :guilabel:`Show unplaced labels` - Layout မြေပုံထဲတွင်ပျောက်ဆုံးနေသော အညွှန်းများ (ဥပမာ- အခြားမြေပုံအညွှန်းများနှင့် ရောနှောနေခြင်းကြောင့် သို့မဟုတ်  အညွှန်းတပ်ရန်လုံလောက်သောနေရာမရှိခြင်းကြောင့်) ကို :ref:`predefined color <automated_placement>` (ကြိုတင်သတ်မှတ်ထားသောအရောင်) ဖြင့် ထင်ရှားအောင်ပြသ (highlight) ခြင်းဖြင့် ရှာဖွေရန်အသုံးပြုနိုင်မည်ဖြစ်သည်။
     
* |clip| :sup:`Clipping settings` - မြေပုံ item အား atlas feature ၊ ပုံသဏ္ဍာန် (shape) နှင့် polygon item များဖြင့် တိဖြတ် (clip) စေနိုင်ပါသည်-

  * |checkbox| :guilabel:`Clip to atlas feature` - လက်ရှိ :ref:`atlas feature <atlas_generation>` ဖြင့် layout မြေပုံ item အား အလိုအလျောက် တိဖြတ် (clip) ပေးမည်ဖြစ်ပါသည်။
    
    ရရှိနိုင်သည့်မြေပုံ တိဖြတ်ခြင်းနည်းလမ်းများမှာ-

    * :guilabel:`Clip During Render Only` - Painter အခြေခံသော တိဖြတ်ခြင်း (clip) တစ်ခုကိုအသုံးပြုသည့်အတွက် atlas feature အပြင်ဘက်ရှိ vector feature များ၏အပိုင်းများကို မြင်ရမည်မဟုတ်ပါ။       
    * :guilabel:`Clip Feature Before Render` - Feature ကို ပုံဖော်ပြသခြင်းမပြုမီ တိဖြတ်ခြင်း (clip) ပြုလုပ်ပေးပါသည်။ ထို့ကြောင့် atlas feature ၏ပြင်ပတွင်တစ်စိတ်တစ်ပိုင်းကျရောက်နေသော feature များ၏နယ်နိမိတ်များကို atlas feature ၏နယ်နိမိတ်ပေါ်တွင် မြင်နေရဦးမည်ဖြစ်သည်။ 
    * :guilabel:`Render Intersecting Features Unchanged` - လက်ရှိ atlas feature နှင့်ထိဖြတ်နေသည့် feature အားလုံး၏ ဂျီဩမေတြီကို တိဖြတ်ခြင်းမပြုဘဲ feature များအားလုံးကို ပုံဖော်ပြသပေးမည်ဖြစ်သည်။

    |checkbox| :guilabel:`Force labels inside atlas feature` တွင်အမှန်ခြစ်ပေးထားနိုင်သည်။ Atlas feature ဖြင့် |radioButtonOff| :guilabel:`Clip all layers` (layer အားလုံးအားတိဖြတ်ခြင်း) မလုပ်လိုလျှင် |radioButtonOn| :guilabel:`Clip selected layers` (ရွေးချယ်ထားသော layer များအား တိဖြတ်ခြင်း) ကိုအသုံးပြုနိုင်သည်။
  * |checkbox| :guilabel:`Clip to item` - Print layout မှ :ref:`shape <layout_basic_shape_item>` တစ်ခု သို့မဟုတ် :ref:`polygon
    <layout_node_based_shape_item>` item ကိုအသုံးပြု၍ မြေပုံ item ၏ပုံသဏ္ဍာန်ကိုပြောင်းလဲနိုင်သည်။ ဤရွေးချယ်မှုကိုအသုံးပြုထားသောအခါ combobox ထဲတွင် ရွေးချယ်ထားသော ပုံသဏ္ဍာန်အတိုင်း မြေပုံကိုအလိုအလျောက် တိဖြတ်သွားမည်ဖြစ်သည်။ တစ်ဖန် အထက်တွင်ဖော်ပြခဲ့သော တိဖြတ်ခြင်းနည်းလမ်းများကိုအသုံးပြုနိုင်ပြီး အညွှန်းများကို တိဖြတ်ထားသော ပုံသဏ္ဍာန်အတွင်းတွင်သာ ပြသစေနိုင်ပါသည်။
    
    .. _figure_layout_mapclipitem:

    .. figure:: img/map_cliptoitem.*
       :align: center

       Layout မြေပုံ item တစ်ခုအား ပုံသဏ္ဍာန်များဖြင့် တိဖြတ်ခြင်း

.. _`layout_main_properties`:

Main properties (အဓိကဂုဏ်သတ္တိများ)
------------------------------------

မြေပုံ၏ :guilabel:`Item Properties` panel မှ :guilabel:`Main properties` အုပ်စု (:numref:`figure_layout_map` ကိုကြည့်ပါ) တွင်ရရှိနိုင်သော ရွေးချယ်စရာများမှာ -

* မြေပုံ canvas ထဲရှိ မြင်ကွင်းတွင် အပြောင်းအလဲများပြုလုပ်လိုက်လျှင် မြေပုံအား update ပြုလုပ်၍ ပုံဖော်ပြသရန် :guilabel:`Update Preview` ခလုတ်ကို အသုံးပြုပါ။ အများအားဖြင့်  အပြောင်းအလဲများကို မြေပုံပေါ်တွင် အလိုအလျောက် update ပြုလုပ်ပေးသည်ကိုသတိပြုပါ။ 
* မြေပုံ item ၏စကေးကို ကိုယ်တိုင်သတ်မှတ်ရန် :guilabel:`Scale` ၊
* မြေပုံ item အကြောင်းအရာများကို ဒီဂရီဖြင့် နာရီလက်တံအတိုင်း လှည့်ပေးသည့် :guilabel:`Map rotation` (မြေပုံအလှည့်)။ မြေပုံ canvas အား လှည့်သည့်အတိုင်း တုပထားခြင်းဖြစ်သည်။
* မြေပုံ item အကြောင်းအရာကိုပြသရန် မည်သည့် :ref:`CRS <crs_selector>` ကိုမဆိုရွေးချယ်နိုင်သည့် :guilabel:`CRS`။ ၎င်းသည် default အားဖြင့် ``Use project CRS`` ဖြစ်သည်။
* ပင်မမြေပုံ canvas တွင် နေရာချထားသော :ref:`annotations (မှတ်စာများ) <sec_annotations>` များကို print layout ထဲတွင်ပြသပေးသည့် |checkbox| :guilabel:`Draw map canvas items` ။ 

.. _`layout_layers`:

Layers (Layer များ)
--------------------

Default အားဖြင့် မြေပုံ item ၏အသွင်အပြင်သည် မြေပုံ canvas ပေါ်တွင်မြင်ရသည်နှင့် ချိန်သားကိုက်ထားခြင်းဖြစ်သည်။ ဆိုလိုသည်မှာ :guilabel:`Layers Panel` ထဲတွင် layer များ၏မြင်နိုင်မှုအားပြောင်းလဲခြင်း သို့မဟုတ် ၎င်းတို့၏ style များကိုပြင်ဆင်ပြောင်းလဲလိုက်ခြင်းဖြင့် မြေပုံ item ပေါ်တွင်အလိုအလျောက်ပြောင်းလဲပြီးသားဖြစ်သွားပါမည်။ အခြား item များကဲ့သို့ပင် စကေးအမျိုးမျိုးနှင့် အမျိုးမျိုးသော ဧရိယာများ၊ layer များပေါင်းစပ်ခြင်း အစရှိသည့် မြောက်များစွာသော မြေပုံ item များကို print layout တစ်ခုထဲသို့ ထည့်သွင်းလိုပါက synchronization (ချိန်သားကိုက်ခြင်း) ကိုရပ်တန့်ထားရန်လိုအပ်ပါသည်။ ထိုသို့ပြုလုပ်နိုင်ရန်  :guilabel:`Layers` ဂုဏ်သတ္တိများအုပ်စုကိုသုံးနိုင်သည် (:numref:`figure_layout_map_layers` ကိုကြည့်ပါ)။

.. _figure_layout_map_layers:

.. figure:: img/map_layers.png
   :align: center

   မြေပုံ Layer များ အုပ်စု

မြေပုံ item အား ရှိပြီးသား :ref:`map theme (မြေပုံအပြင်အဆင်) <map_themes>` တစ်ခုအတိုင်း ထားရှိလိုပါက |checkbox| :guilabel:`Follow map theme` ကိုအမှန်ခြစ်၍ drop-down စာရင်းမှလိုချင်သည့် မြေပုံအပြင်အဆင် ကိုရွေးချယ်နိုင်သည်။ ပင်မ QGIS window ရှိ အပြင်အဆင်တွင် ပြုလုပ်လိုက်သော ပြောင်းလဲမှုမှန်သမျှ (အပြင်အဆင်အား အစားထိုးသည့်လုပ်ဆောင်ချက်အားအသုံးပြုခြင်း)သည် မြေပုံ item တွင် အလိုအလျောက် သက်ရောက်မည်ဖြစ်သည်။ Map theme တစ်ခုအားရွေးချယ်လိုက်သောအခါ :guilabel:`Follow map theme` သည် layer များ၏ style များ (သင်္ကေတများ၊ အညွှန်းများ၊ ရုပ်ပုံကားချပ်များ) ကိုပါ update လုပ်လိုက်မည်ဖြစ်သောကြောင့် :guilabel:`Lock styles for layers` option သည် ပိတ်သွားမည်ဖြစ်သည်။

လက်ရှိမြေပုံ canvas ပေါ်တွင်မြင်ရသည့်အတိုင်း မြေပုံ item တစ်ခုတွင်ပြသထားသည့် layer များကို lock ပြုလုပ်ရန် |checkbox| :guilabel:`Lock layers` ကိုအမှန်ခြစ်ပေးပါ။ ဤ option အားဖွင့်ထားသောအခါ QGIS ၏ ပင်မ window တွင်ရှိသော layer ၏ မြင်ရနိုင်မှုအပေါ် ပြောင်းလဲမှုမှန်သမျှသည် layout မြေပုံ item အားသက်ရောက်မှုရှိမည်မဟုတ်ပါ။ သို့သော် lock ပြုလုပ်ထားသည့် layer များ၏ style နှင့် အညွှန်းများ QGIS ၏ပင်မ window အတိုင်း update လုပ်နေဆဲဖြစ်မည်။ ထိုသို့ မဖြစ်စေရန် :guilabel:`Lock styles for layers` ကိုအသုံးပြုနိုင်ပါသည်။

လက်ရှိမြေပုံ canvas ကို အသုံးပြုခြင်းအစား ရှိပြီးသား မြေပုံအပြင်အဆင်တစ်ခု၏ layer များဖြင့် မြေပုံ item ၏ layer များကို lock ပြုလုပ်နိုင်ပါသည်- |showPresets| :sup:`Set layer list from a map theme` drop-down ခလုတ်မှ မြေပုံအပြင်အဆင်တစ်ခုကိုရွေးချယ်ပြီး |checkbox| :guilabel:`Lock layers` ကိုအမှန်ခြစ်ပါ။ အခြားမြေပုံအပြင်အဆင်တစ်ခုကိုမရွေးချယ်မီ သို့မဟုတ် |checkbox| :guilabel:`Lock layers` option တွင် အမှန်ခြစ်မဖြုတ်မီအထိ မြေပုံအပြင်အဆင်ထဲတွင် မြင်တွေ့ရနိုင်သော layer အစုလိုက်ကို မြေပုံ item အတွက် အသုံးပြုသွားမည်ဖြစ်သည်။ ထို့နောက် :guilabel:`Navigation` toolbar မှ |refresh| :sup:`Refresh view` ခလုတ်ကိုသုံး၍ဖြစ်စေ အပေါ်တွင်တွေ့ရသော :guilabel:`Update Preview` ခလုတ်ကိုသုံး၍ဖြစ်စေ မြင်ကွင်းအား update လုပ်ရန် လိုအပ်ပါသည်။  
  
:guilabel:`Follow map theme` option နှင့်မတူညီသည့်အချက်မှာ :guilabel:`Lock layers` option ကိုဖွင့်ထားပြီး မြေပုံအပြင်အဆင်တစ်ခုတွင် သတ်မှတ်လျှင် QGIS ၏ပင်မ window ထဲတွင် မြေပုံအပြင်အဆင်သည် update ဖြစ်သွားသည့်တိုင် (အပြင်အဆင်အား အစားထိုးသည့်လုပ်ဆောင်ချက်အားအသုံးပြုခြင်း) မြေပုံ item ထဲမှ layer များကို update လုပ်မည်မဟုတ်ကြောင်းသတိပြုရမည်ဖြစ်သည်။

Option ၏ဘေးရှိ |dataDefine| သင်္ကေတအားအသုံးပြုခြင်းဖြင့် မြေပုံ item ထဲရှိ lock ပြုလုပ်ထားသော layer များကို :ref:`data-defined <data_defined>` (Data ဖြင့်သတ်မှတ်) လုပ်ထားနိုင်သည်။ အသုံးပြုသောအခါ ၎င်းသည် drop-down စာရင်းတွင် သတ်မှတ်ထားသော ရွေးချယ်မှုကို အစားထိုးလုပ်ဆောင်သွားမည်ဖြစ်သည်။ Layer များ၏စာရင်းကို ``|`` သင်္ကေတများဖြင့်ပိုင်းခြားပေးထားရန်လိုအပ်သည်။ အောက်ပါဥပမာသည် ``layer 1`` နှင့် ``layer 2`` များကိုသာအသုံးပြုစေရန် မြေပုံ item အား lock ပြုလုပ်ခြင်းကို ပြသထားပါသည်-
::

  concat ('layer 1', '|', 'layer 2')


Extents (နယ်ပယ်အကျယ်အဝန်းများ)
-------------------------------

မြေပုံ item ဂုဏ်သတ္တိများ panel ၏ :guilabel:`Extents` အုပ်စုတွင် အောက်ပါလုပ်ဆောင်ချက်များပါဝင်ပါသည် (:numref:`figure_layout_map_extents` ကိုကြည့်ပါ)-

.. _figure_layout_map_extents:

.. figure:: img/map_extents.png
   :align: center

   မြေပုံနယ်ပယ်အကျယ်အဝန်းများအုပ်စု

**Extents** ဧရိယာသည် မြေပုံ item ထဲတွင်ပြသထားသောဧရိယာ၏ ``X`` နှင့် ``Y`` ကိုဩဒိနိတ်များကိုပြသပေးသည်။ အဆိုပါ ကိုဩဒိနိတ်တန်ဖိုးများ တစ်ခုချင်းစီကို အစားထိုး၍ ပြသထားသည့် မြေပုံ canvas ပေါ်မှ ဧရိယာ နှင့်/သို့မဟုတ် မြေပုံ item ၏အရွယ်အစားကို ပြုပြင်ပြောင်းလဲနိုင်သည်။ Extent အား မြေပုံ item panel ၏ထိပ်တွင်ရှိသော အောက်ပါ tool များကိုအသုံးပြုခြင်းဖြင့်လည်း ပြုပြင်ပြောင်းလဲနိုင်သည်-

* |setToCanvasExtent| :sup:`Set map canvas to match main canvas extent` (အဓိက canvas extent နှင့်ကိုက်ညီစေရန် မြေပုံ canvas ကို သတ်မှတ်ပါ)
* |setToCanvasScale| :sup:`Set map scale to match main canvas scale` (အဓိက canvas စကေးနှင့်ကိုက်ညီစေရန် မြေပုံစကေးကို သတ်မှတ်ပါ)

|moveItemContent| :sup:`Move item content` tool အားအသုံးပြုခြင်းဖြင့် မြေပုံ item တစ်ခုအား ပြောင်းလဲနိုင်သည်- မြေပုံ item အတွင်း click နှိပ်၍ ဖိဆွဲကာ ရွှေ့ခြင်းဖြင့် စကေးကိုမပြောင်းလဲစေပဲ ၎င်း၏လက်ရှိမြင်ကွင်းကိုပြောင်းလဲနိုင်သည်။ |moveItemContent| tool အားဖွင့်ထားပြီး မောက်စ်ဘီးလုံး ဖြင့် မြင်ကွင်းချုံ့ခြင်း သို့မဟုတ် ချဲ့ခြင်းပြုလုပ်ကာ ပြထားသောမြေပုံ၏ စကေးကို ပြောင်းလဲနိုင်သည်။ :kbd:`Ctrl` ခလုတ်ဖြင့် တွဲ၍လုပ်ဆောင်သောအခါ ချောမွေ့သော မြင်ကွင်းချုံ့ချဲ့မှုကို ရရှိနိုင်သည်။

.. index:: Temporal, Print layout
.. _mapitem_temporalrange:

Temporal range (အချိန်နှင့်သက်ဆိုင်သော အပိုင်းအခြားများ)
---------------------------------------------------------

မြေပုံ item ဂုဏ်သတ္တိများ panel ၏ :guilabel:`Temporal range` အုပ်စုတွင်  အချိန်အပိုင်းအခြားပေါ်မူတည်၍ မြေပုံ item ထဲရှိ layer များအားပုံဖော်ပြသခြင်းကို ထိန်းချုပ်နိုင်သော option များရှိပါသည်။ :guilabel:`Start` (စချိန်) နှင့် :guilabel:`End` (ဆုံးချိန်) ရက်စွဲများဖြင့် သတ်မှတ်ထားသောအချိန်အပိုင်းအခြားအတွင်း ကျရောက်သော  အချိန်ဆိုင်ရာဂုဏ်သတ္တိများရှိသည့် layer များကိုသာ မြေပုံ item ထဲတွင်ပြသမည်ဖြစ်သည်။
   
သက်ဆိုင်ရာ ဒေတာသတ်မှတ်ထားသော widget များဖြင့် အချိန်အပိုင်းအခြားကို dynamic (ပြောင်းလဲနေ) ဖြစ်နေစေရန် လုပ်ဆောင်နိုင်ပြီး အချိန်နှင့်သက်ဆိုင်သော :ref:`atlases (မြေပုံစီးရီး) <atlas_generation>` များကို ရလာဒ် ထုတ်ပေးနိုင်ပါသည်၊ ဥပမာ- တည်နေရာဆိုင်ရာအကျယ်အဝန်းကို ပုံသေသတ်မှတ်ထားပြီး ပါဝင်သောအကြောင်းအရာများသည် အချိန်အပေါ်မူတည်၍ ပြောင်းလဲနေသည့် automated (အလိုအလျောက်ဖြစ်သော) မြေပုံများ။ ဥပမာအားဖြင့်- အချိန်အပိုင်းအခြားများကို ကိုယ်စားပြုသော အစနှင့် အဆုံး အတွဲလိုက် field များနှင့် row အရေအတွက်များပါဝင်သော csv file တစ်ခုအား coverage layer အဖြစ် အသုံးပြုခြင်းသည် မြေပုံ item ဂုဏ်သတ္တိများရှိ Temporal range (အချိန်အပိုင်းအခြား) နှင့် control by atlas (atlas မှထိန်းချုပ်ခြင်း) နှစ်ခုစလုံးကို ပွင့်စေပြီး atlas export ပြုလုပ်နိုင်မည်ဖြစ်သည်။

.. index:: Atlas
.. _controlled_atlas:

Controlled by atlas (Atlas မှထိန်းချုပ်ထားသော)
-----------------------------------------------

Print layout ထဲတွင် :ref:`atlas <atlas_generation>` တစ်ခုကိုဖွင့်ထားမှသာ |checkbox| :guilabel:`Controlled by atlas` အုပ်စုဂုဏ်သတ္တိများအား အသုံးပြုနိုင်မည်ဖြစ်သည်။ မြေပုံ item ကို altas ဖြင့် ထိန်းချုပ်လိုက်လျှင် ဤ option ကို အမှန်ခြစ်ပါ။ Coverage layer တွင် ထပ်ခါထပ်ခါပြုလုပ် (iterate) သောအခါ မြေပုံ item extent သည် အောက်ပါတို့ပေါ်မူတည်၍ atlas feature သို့ ရွေ့သွား/မြင်ကျယ်ချဲ့သွားမည်ဖြစ်သည်-

* |radioButtonOn| :guilabel:`Margin around features` - Feature ကို အကောင်းဆုံး စကေး၌ မြင်ကွင်းချဲ့ခြင်းပြုလုပ်ပေးပြီး မြေပုံ item အကျယ် သို့မဟုတ် အမြင့်၏ ရာခိုင်နှုန်းတစ်ခုကို ကိုယ်စားပြုသော အနားသတ် (margin) တစ်ခုကို feature တစ်ခုချင်းစီ၏ပတ်လည်တွင် ထားရှိပေးမည်ဖြစ်သည်။ အနားသတ် သည် feature အားလုံးအတွက်တူညီနိုင်သကဲ့သို့ :ref:`variable သတ်မှတ်ထား <data_defined>` သည်လည်းဖြစ်နိုင်သည်၊ ဥပမာ- မြေပုံစကေးပေါ်တွင်မူတည်နေခြင်းမျိုးဖြစ်သည်။
* |radioButtonOff| :guilabel:`Predefined scale (best fit)` - Atlas feature နှင့်အကောင်းဆုံးကိုက်ညီသည့် project ၏ :ref:`ကြိုတင်သတ်မှတ်ထားသော စကေး <predefinedscales>` ၌ feature ကို မြင်ကွင်းချဲ့ခြင်းပြုလုပ်ပေးမည်ဖြစ်သည်။
* |radioButtonOff| :guilabel:`Fixed scale`- မြေပုံ item ၏ စကေးကိုမပြောင်းလဲစေပဲ atlas feature များကို တစ်ခုမှအခြားတစ်ခုသို့ ကူးပြောင်းသွားစေသည်။ ၎င်းသည် အရွယ်အစားတူညီသော feature များနှင့်အလုပ်လုပ်လျှင်ဖြစ်စေ (ဥပမာ- gridတစ်ခု) သို့မဟုတ် atlas feature များအကြားတွင် အရွယ်အစားကွာခြားချက်အား ထင်ရှားစေလိုလျှင်ဖြစ်စေ အသုံးဝင်သည်။

.. index:: Grids, Map grid

Grids (အကွက်များ)
------------------

Grid များကိုအသုံးပြု၍ မြေပုံပေါ်တွင် ၎င်း၏ extent သို့မဟုတ် ကိုဩဒိနိတ်များနှင့်ပတ်သက်သော အချက်အလက်များကို မြေပုံ item ၏ projection ဖြင့်ဖြစ်စေ အခြားမတူညီသည့် projection ဖြင့်ဖြစ်စေ ထည့်သွင်းနိုင်သည်။ :guilabel:`Grids` အုပ်စုဖြင့် မြေပုံ item တစ်ခုထဲသို့မြောက်များစွာသော grid များထည့်သွင်းနိုင်သည်။

* |symbologyAdd| နှင့် |symbologyRemove| ခလုတ်များဖြင့် ရွေးချယ်ထားသော grid တစ်ခုကို ထည့်သွင်းခြင်း သို့မဟုတ် ဖယ်ရှားခြင်းပြုလုပ်နိုင်သည်။
* |arrowUp| နှင့်|arrowDown| ခလုတ်များဖြင့် စာရင်းထဲရှိ grid တစ်ခုကို အပေါ် အောက် ရွှေ့နိုင်သည်၊ ထို့ကြောင့် မြေပုံပေါ်တွင် grid တစ်ခုအား အခြား တစ်ခု၏ အပေါ် သို့မဟုတ် အောက်သို့ရွှေ့နိုင်ပါသည်။ 

ထည့်သွင်းလိုက်သော grid ပေါ်တွင် click နှစ်ချက်နှိပ်၍ ၎င်းအား အမည်ပြန်ပေးနိုင်သည်။

.. _Figure_layout_map_grid:

.. figure:: img/map_grids.png
   :align: center

   မြေပုံ Grid များ Dialog

Grid တစ်ခုကိုပြောင်းလဲရန်အတွက် ၎င်းအားရွေး၍ :guilabel:`Modify Grid...` ခလုတ်ကိုနှိပ်ပြီး :guilabel:`Map Grid Properties` panel အားဖွင့်ကာ ၎င်း၏ပြင်ဆင်သတ်မှတ်ခြင်းဆိုင်ရာ option များသို့ ဝင်ရောက်ပါ။ 
 
Grid Appearance (Grid များ၏အသွင်အပြင်)
.......................................

မြေပုံ item ပေါ်တွင် grid ပေါ်လာစေရန် :guilabel:`Map Grid Properties` panel ထဲမှ |checkbox|:guilabel:`Grid enabled` ကိုအမှန်ခြစ်ပါ။

Grid များ၏ အမျိုးအစားအနေဖြင့် အောက်ပါတို့ကို သုံးရန်သတ်မှတ်နိုင်သည်-

* *Solid* - Grid ဘောင်တစ်လျှောက် မျဉ်းတစ်ကြောင်းကိုပြပေးသည်။ :guilabel:`Line style` အား :ref:`အရောင် <color-selector>` နှင့် :ref:`သင်္ကေတ <symbol-selector>` ရွေးချယ်ပေးသည့်အရာ  widget များသုံး၍ စိတ်ကြိုက်ပြင်ဆင်နိုင်သည်၊
* *Cross* - Grid လိုင်းများဆုံသည့်နေရာများတွင် :guilabel:`Line style` နှင့် :guilabel:`Cross width` သတ်မှတ်နိုင်သည့် segment (မျဉ်းပိုင်း) တစ်ခုကိုပြပေးသည်၊
* *Markers*- Grid လိုင်းများဆုံသည့်နေရာများတွင် စိတ်ကြိုက်ပြင်ဆင်နိုင်သော အမှတ်အသားသင်္ကေတများကိုသာ ပြပေးသည်၊
* သို့မဟုတ် *Frame နှင့် annotation များသာ*။

Grid အမျိုးအစားအပြင် အောက်ပါတို့ကိုသတ်မှတ်နိုင်ပါသည်-

* Grid ၏ :guilabel:`CRS`။ ၎င်းအားမပြောင်းလျှင် မြေပုံ၏ CRS (Coordinate Reference System)အတိုင်းသတ်မှတ်မည်ဖြစ်သည်။ :guilabel:`Change` ခလုတ် ဖြင့် အခြားမတူညီသည့် CRS ကိုသတ်မှတ်နိုင်သည်။ အခြားတစ်ခုကို သတ်မှတ်ပြီးနောက် default သို့ပြန်လည်ပြောင်းလဲလိုပါက CRS ရွေးချယ်ခြင်း dialog ထဲရှိ :guilabel:`Predefined Coordinate Reference Systems` အောက်မှ အုပ်စုခေါင်းစီး တစ်ခုခုကိုရွေးလိုက်ခြင်းဖြင့် ပြုလုပ်နိုင်သည်။ (ဥပမာ- **Geographic Coordinate System**) 
  
* Grid အကိုးအကား များအတွက် သုံးရန် :guilabel:`Interval` (ကြားအကွာအဝေး) အမျိုးအစား။ ရရှိနိုင်သောရွေးချယ်စရာများမှာ ``မြေပုံယူနစ်`` ၊ ``အံကိုက်ဖြစ်သော Segment အကျယ်`` ၊ ``မီလီမီတာ`` သို့မဟုတ် ``စင်တီမီတာ`` တို့ဖြစ်ပါသည်-

  * ``Fit Segment Width`` ကိုရွေးချယ်ခြင်းသည် မြေပုံ extent အပေါ်အခြေခံ၍ grid interval ကို အလိုအလျောက်ဆုံးဖြတ်ပေးမည်ဖြစ်ပြီး သေသပ်လှပသော interval ရရှိစေမည်ဖြစ်သည်။ ရွေးချယ်သောအခါ ``Minimum`` နှင့် ``Maximum`` interval များကိုသတ်မှတ်နိုင်သည်။
  * အခြားရွေးချယ်စရာများမှာ ကပ်လျက် grid အကိုးအကား နှစ်ခုကြားအကွာအဝေးအား ``X`` နှင့် ``Y`` ဦးတည်ရာများဖြင့် သတ်မှတ်နိုင်သည်။
    
* ``X`` နှင့်/သို့မဟုတ် ``Y`` ဦးတည်ရာဖြင့် မြေပုံ item အစွန်းများမှ :guilabel:`Offset` (အရွေ့)
* ကိုက်ညီမှုရှိသည့်အခါ အသုံးပြုနိုင်မည့် grid ၏ :guilabel:`Blend mode` (ရောစပ်ခြင်းနည်းလမ်း) (:ref:`blend-modes` ကိုကြည့်ပါ) 

.. _Figure_layout_map_grid_draw:

.. figure:: img/map_grid_appearance.png
   :align: center

   Grid အသွင်အပြင် Dialog

Grid Frame (Grid ဘောင်)
........................

မြေပုံထည့်သွင်းထားရှိမည့် ဘောင်အတွက် style သတ်မှတ်ရန် ရွေးချယ်စရာအမျိုးမျိုးရှိပြီး အောက်ပါတို့ကိုအသုံးပြုနိုင်ပါသည်- ``No Frame`` ၊ ``Zebra`` ၊ ``Zebra (nautical)``၊ ``Interior ticks`` ၊ ``Exterior ticks``၊ ``Interior and Exterior ticks``၊ ``Line border`` နှင့် ``Line border (nautical)``။

ထို့အပြင်အချို့နေရာများတွင် :guilabel:`Frame size (ဘောင်အရွယ်အစား)` ၊ :guilabel:`Frame margin (ဘောင်အနားသတ်)` တစ်ခု၊ သက်ဆိုင်ရာအရောင်ဖြင့် :guilabel:`Frame line thickness (ဘောင်လိုင်းအထူ)` နှင့် :guilabel:`Frame fill colors (ဘောင်အဖြည့်အရောင်)` တို့ကိုပါသတ်မှတ်နိုင်ပါမည်။

လှည့်ထားသော မြေပုံများ သို့မဟုတ် projection ပြောင်းထားသော grid များနှင့် အလုပ်လုပ်သည့်အခါ အပိုင်းခွဲရာ၌ ``Latitude/Y only`` နှင့် ``Longitude/X only`` တန်ဖိုးများကို အသုံးပြုခြင်းဖြင့် တစ်ဘက်စီတွင် လတ္တီကျု/Y နှင့် လောင်ဂျီကျု/X ကိုဩဒိနိတ်များ ရောနှောပြသခြင်းကို ရှောင်ရှားနိုင်သည်။ Grid frame ၏ တစ်ဖက်တစ်ချက်စီတွင် မြင်နိုင်စေရန် သို့မဟုတ် မမြင်နိုင်စေရန် ကိုလည်း ရွေးချယ်သတ်မှတ်နိုင်ပါသည်။

.. _Figure_layout_map_frame:

.. figure:: img/map_grid_frame.png
   :align: center

   Grid ဘောင် Dialog

Coordinates (ကိုဩဒိနိတ်များ)
.............................

|checkbox| :guilabel:`Draw coordinates` တွင်အမှန်ခြစ်ခြင်းဖြင့် မြေပုံဘောင်တွင် ကိုဩဒိနိတ်များ ထည့်သွင်းနိုင်သည်။ မှတ်စာ (annotation) ကိန်းဂဏန်း format များကို ရွေးချယ်နိုင်ပါသည်၊ ရွေးချယ်စရာများမှာ ဒဿမကိန်းများမှဒီဂရီများအထိ၊ မိနစ်များနှငိ့စက္ကန့်များ၊ နောက်ဆက်တွဲများပါ/မပါ၊ တန်းညီ/မညီ နှင့် Expression dialog အားအသုံးပြု၍ စိတ်ကြိုက် format တစ်ခု စသည်တို့ဖြစ်ကြပါသည်။
   
ဖော်ပြလိုသည့်မှတ်စာများကိုရွေးချယ်နိုင်သည်။ ရွေးချယ်စရာများမှာ- အားလုံးကိုပြရန်၊  လတ္တီကျုများသာပြရန်၊ လောင်ဂျီကျု များသာပြရန် သို့မဟုတ် မည်သည့်အရာမျှမပြရန်တို့ဖြစ်သည်။ ၎င်းသည် မြေပုံကိုလှည့်ထားသောအခါတွင် အသုံးဝင်မည်ဖြစ်သည်။ မြေပုံဘောင်၏ အတွင်းတွင်ဖြစ်စေ အပြင်တွင်ဖြစ်စေ မှတ်စာများကိုထားရှိနိုင်သည်။ မှတ်စာများ၏ဦးတည်ရာအား အလျားလိုက်ဖြစ်စေ၊ ဒေါင်လိုက် ငယ်စဉ်ကြီးလိုက်ဖြစ်စေ၊ ဒေါင်လိုက် ကြီးစဉ်ငယ်လိုက် ဖြစ်စေ သတ်မှတ်နိုင်သည်။

နောက်ဆုံးအနေနှင့် မှတ်စာတွင် အသုံးပြုမည့် စာလုံးဖောင့်၊ စာလုံးဖောင့်အရောင်၊ မြေပုံဘောင်မှအကွာအဝေးနှင့် ရေးဆွဲထားသော ကိုဩဒိနိတ်များအတွက် ဂဏန်းတိကျမှုများကိုပါ သတ်မှတ်နိုင်မည်ဖြစ်သည်။

.. _figure_layout_map_coord:

.. figure:: img/map_grid_draw_coordinates.png
   :align: center

   Grid Draw ကိုဩဒိနိတ်များ dialog


.. index:: Location map, Map overview

Overviews (ခြုံငုံပြသမှုများ)
------------------------------

တစ်ခါတစ်ရံတွင် print layout ထဲ၌ မြေပုံများတစ်ခုထက်မကရှိနေနိုင်ပြီး မြေပုံ item တစ်ခု၏လေ့လာမှုဧရိယာ (study area) ကို အခြားမြေပုံ item တစ်ခုပေါ်တွင် တည်နေရာပြသလိုသည့်အခါများရှိတတ်ပါသည်။ ၎င်းသည် ဒုတိယမြေပုံပေါ်တွင်ပြသထားသော ပိုကြီးမားသည့်ပထဝီဝင်အနေအထားနှင့် ဆက်နွယ်သော ဧရိယာကို မြေပုံကြည့်ရှုသူများ ဖော်ထုတ်နိုင်စေရန် အဆင်ပြေသည့် ဥပမာတစ်ခုဖြစ်ပါသည်။

မြေပုံ panel ၏ :guilabel:`Overviews` အုပ်စုဖြင့် မတူညီသော မြေပုံ extent နှစ်ခုကြားတွင် ချိတ်ဆက်မှုတစ်ခုဖန်တီးနိုင်ပြီး ၎င်းတွင်အောက်ပါလုပ်ဆောင်ချက်များပါဝင်သည်- 

.. _figure_layout_map_overview:

.. figure:: img/map_overview.png
   :align: center

   မြေပုံ ခြုံငုံပြသမှုများ အုပ်စု

Overview တစ်ခုအားဖန်တီးရန် အခြားမြေပုံ item တစ်ခု၏ extent ကိုတင်၍ ပြသလိုသည့် မြေပုံ item ကိုရွေးချယ်၍ :guilabel:`Item Properties` panel ထဲရှိ :guilabel:`Overviews` ကိုအကျယ်ဖြန့်ပါ။ ထို့နောက် |symbologyAdd| ခလုတ်ကိုနှိပ်၍ Overview တစ်ခုကိုထည့်သွင်းပါ။

ပထမဆုံးအနေနှင့် ဤ overview အား 'Overview 1' ဟုအမည်ပေးထားပါမည် (:numref:`Figure_layout_map_overview` ကိုကြည့်ပါ)။ ၎င်းအား-

* Click နှစ်ချက်နှိပ်၍ အမည်ပြန်ပေးနိုင်သည်။
* |symbologyAdd| နှင့် |symbologyRemove| ခလုတ်များဖြင့် overview များထည့်နိုင်သကဲ့သို့ ဖယ်ရှားနိုင်သည်။
* |arrowUp| နှင့် |arrowDown| ခလုတ်များဖြင့် စာရင်းထဲတွင် overview အား မြေပုံ item ထဲရှိ အခြား overview များ၏ အထက် သို့မဟုတ် အောက်တွင် ထားခြင်းဖြင့် အပေါ်အောက်ရွှေ့နိုင်သည်။ (တူညီသော :ref:`stack position <overview_stack_position>` တွင်ရှိနေသောအခါ)

ထို့နောက် စာရင်းထဲရှိ overview item အားရွေးချယ်၍ ရွေးချယ်ထားသော မြေပုံ frame ပေါ်တွင် overview ရေးဆွဲရန် :guilabel:`Draw "<name_overview>" overview` ကိုအမှန်ခြစ်ပါ။ ၎င်းကိုအောက်ပါတို့ဖြင့် စိတ်ကြိုက်ပြင်ဆင်နိုင်သည်-

* :guilabel:`Map frame` သည် လက်ရှိ မြေပုံ item ပေါ်တွင်ပြသမည့် extent ပါရှိသော မြေပုံ item ကိုရွေးချယ်ပေးသည်။
* :guilabel:`Frame Style` သည် overview frame ကိုပုံဖော်ပြသရန် :ref:`သင်္ကေတဂုဏ်သတ္တိများ <symbol-selector>` ကို အသုံးပြုပါသည်။
* :guilabel:`Blending mode` သည် အမျိုးမျိုးသော transparency (အလင်းဖောက်နှုန်း) ရောစပ်မှုနည်းလမ်းများကို သတ်မှတ်စေနိုင်ပါသည်။
* |checkbox| :guilabel:`Invert overview` အမှန်ခြစ်ပေးထားသောအခါ မြေပုံ extent ၏ပတ်လည်တွင် mask (အဖုံးအကာ) တစ်ခုဖန်တီးပေးမည်ဖြစ်ပြီး- အကိုးအကားပြုထားသော မြေပုံ extent များကို ရှင်းလင်းစွာ ပြသပေးမည်ဖြစ်သည်။ မြေပုံ၏ကျန်ရှိသောအပိုင်းများကို ဘောင်တွင်ဖြည့်ထားသောအရောင်ဖြင့် ရောစပ်၍ ပြသပေးမည်ဖြစ်သည် (အဖြည့်အရောင် တစ်ခုကို သုံးထားလျှင်)
* |checkbox| :guilabel:`Center on overview` သည် overview frame အားမြေပုံ၏အလယ်ဗဟိုတွင်ရှိနေစေရန် မြေပုံပါအကြောင်းအရာများကို ချိန်ညှိပေးသည်။
  overview မြောက်များစွာရှိစေကာမူ မြေပုံ၏အလယ်ဗဟိုတွင်  overviewတစ်ခုကိုသာလျှင်တင်ထားနိုင်မည်ဖြစ်သည်။

.. _`overview_stack_position`:

* :guilabel:`Position` ဖြင့် မြေပုံ item ၏ layer အစုအထပ်ထဲတွင် overview အားထားရှိမည့်နေရာကို အတိအကျသတ်မှတ်နိုင်သည်။ ဥပမာ- အခြားနောက်ခံ layer များအပေါ်တွင် ရေးဆွဲရသော လမ်းများကဲ့သို့ အချို့ feature layer များအောက်တွင် overview extent အား ရေးဆွဲစေခြင်းဖြစ်ပါသည်။ ရရှိနိုင်သောရွေးချယ်စရာများမှာ-

  * :guilabel:`Below map` (မြေပုံအောက်တွင်)
  * :guilabel:`Below map layer` နှင့် :guilabel:`Above map layer` - Overview frame အား layer တစ်ခု၏ ဂျီဩမေတြီများအောက်နှင့်အပေါ်တ္ငင်အသီးသီးထားရှိပေးသည်။ Layer အား:guilabel:`Stacking layer` option ထဲတွင် ရွေးချယ်ခြင်းဖြစ်သည်။
  * :guilabel:`Below map labels`- မြေပုံ item ထဲတွင်အညွှန်းများအား feature ဂျီဩမေတြီများ၏အပေါ်တွင်အမြဲသတ်မှတ်ထားရှိပါက overview frame ကိုဂျီဩမေတြီအားလုံး၏အပေါ်နှင့် အညွှန်းများ၏အောက်တွင် ထားရှိပေးသည်။
  * :guilabel:`Above map labels` - Overview frame ကိုမြေပုံ item ထဲရှိ ဂျီဩမေတြီများ နှင့် အညွှန်းများအားလုံး၏အပေါ်တွင်ထားရှိပေးသည်။



.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |addMap| image:: /static/common/mActionAddMap.png
   :width: 1.5em
.. |arrowDown| image:: /static/common/mActionArrowDown.png
   :width: 1.5em
.. |arrowUp| image:: /static/common/mActionArrowUp.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |clip| image:: /static/common/mAlgorithmClip.png
   :width: 1.5em
.. |dataDefine| image:: /static/common/mIconDataDefine.png
   :width: 1.5em
.. |labelingSingle| image:: /static/common/labelingSingle.png
   :width: 1.5em
.. |moveItemContent| image:: /static/common/mActionMoveItemContent.png
   :width: 1.5em
.. |radioButtonOff| image:: /static/common/radiobuttonoff.png
   :width: 1.5em
.. |radioButtonOn| image:: /static/common/radiobuttonon.png
   :width: 1.5em
.. |refresh| image:: /static/common/mActionRefresh.png
   :width: 1.5em
.. |setToCanvasExtent| image:: /static/common/mActionSetToCanvasExtent.png
   :width: 1.5em
.. |setToCanvasScale| image:: /static/common/mActionSetToCanvasScale.png
   :width: 1.5em
.. |showBookmarks| image:: /static/common/mActionShowBookmarks.png
   :width: 1.5em
.. |showPresets| image:: /static/common/mActionShowPresets.png
   :width: 1.5em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
.. |symbologyRemove| image:: /static/common/symbologyRemove.png
   :width: 1.5em
.. |unchecked| image:: /static/common/unchecked.png
   :width: 1.3em
.. |viewExtentInCanvas| image:: /static/common/mActionViewExtentInCanvas.png
   :width: 1.5em
.. |viewScaleInCanvas| image:: /static/common/mActionViewScaleInCanvas.png
   :width: 1.5em
