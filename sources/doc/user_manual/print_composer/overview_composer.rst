.. _overview_layout:

********************************************************************
Overview of the Print Layout (ပုံထုတ်အပြင်အဆင်ဆိုင်ရာ ခြုံငုံသုံးသပ်ချက်)
********************************************************************

.. only:: html

   .. contents::
      :local:

Print layout (ပုံထုတ်အပြင်အဆင်) သည် မြေပုံအချောသပ်ပြင်ဆင်ခြင်းနှင့် print ပြုလုပ်ခြင်း လုပ်နိုင်စွမ်းများစွာကို ရရှိစေပါသည်။ QGIS မြေပုံ canvas (မြင်ကွင်း)၊ စာသားအညွှန်းများ၊ ဓာတ်ပုံများ၊ ရည်ညွှန်းချက်များ၊ စကေးပြဘားများ၊ အခြေခံပုံသဏ္ဍာန်များ၊ မြှားများ၊ အချက်အလက်ဇယားများ နှင့် HTML ဘောင်များကဲ့သို့သော element များကို ထည့်သွင်းနိုင်ပါသည်။ Element တစ်ခုချင်းစီကို အရွယ်အစားချိန်ညှိခြင်း၊ အုပ်စုဖွဲ့ခြင်း၊ တန်းညီအောင်ညှိခြင်း၊ နေရာချထားခြင်းနှင့် လှည့်ခြင်းကို ပြုလုပ်နိုင်ပြီး layout ဖန်တီးရန်အတွက် ၎င်းတို့၏ properties (ဂုဏ်သတ္တိများ) ကို ချိန်ညှိပေးနိုင်ပါသည်။ Layout ကို print ပြုလုပ်နိုင်သလို ဓာတ်ပုံ format များ၊ PostScript ၊ PDF သို့မဟုတ် SVG များသို့ export ပြုလုပ်နိုင်ပါသည်။

.. index:: Layout template, Map template

Sample Session for beginners (စတင်အသုံးပြုသူများအတွက် နမူနာကဏ္ဍ)
=================================================================

Print layout နှင့်စတင်အလုပ်မလုပ်မီတွင် QGIS မြေပုံ canvas ထဲသို့ raster သို့မဟုတ် vector layer အချို့ထည့်သွင်းထားရန်လိုအပ်ပြီး မိမိ၏လိုအပ်ချက်နှင့်အညီ ၎င်းတို့၏ property များကို လိုက်လျောညီထွေလုပ်ဆောင်ရန်လိုအပ်ပါသည်။ အရာအားလုံးကို စိတ်တိုင်းကျ ပုံဖော်ပြသခြင်းနှင့် သင်္ကေတထည့်သွင်းခြင်းများပြုလုပ်ပြီးလျှင် :guilabel:`Project` toolbar ထဲရှိ |newLayout| :sup:`New Print Layout` icon ကိုနှိပ်ပါ သို့မဟုတ် :menuselection:`Project -->` |newLayout| :menuselection:`New Print Layout` ကို ရွေးချယ်ပါ။ Layout အသစ်အတွက် ခေါင်းစဉ်တစ်ခုကို ရွေးချယ်ပေးရန် မေးမြန်းပါလိမ့်မည်။

မြေပုံတစ်ခုကို မည်သို့ဖန်တီးရမည်ကို သရုပ်ဖော်ပြသရန် ဖော်ပြပါ ညွှန်းကြားချက်များအတိုင်း လုပ်ဆောင်ပါ။

#. ဘယ်ဘက်ခြမ်းရှိ |addMap| :sup:`Add map` toolbar ကို ရွေးပြီး မောက်စ်၏ ဘယ်ဘက်ခလုတ်ကို ဖိနှိပ်ထားပြီး canvas ပေါ်တွင် ထောင့်မှန်စတုဂံ (rectangle) တစ်ခုဆွဲပါ။ QGIS မြေပုံမြင်ကွင်းသည် ဆွဲထားသော ထောင့်မှန်စတုဂံအထဲတွင် ပေါ်လာမည်ဖြစ်သည်။
#. |scaleBar| :sup:`Add scalebar` toolbar ခလုတ်ကို ရွေးချယ်ပြီး print layout canvas ပေါ်တွင် မောက်စ်၏ ဘယ်ဘက်ခလုတ်ဖြင့် click လုပ်ပါ။ Canvas ထဲတွင် စကေးဘား တစ်ခုကို ထည့်သွင်းပေးမည်ဖြစ်သည်။
#. |addLegend| :sup:`Add legend` toolbar ခလုတ်ကိုရွေးချယ်ပြီး မောက်စ်၏ ဘယ်ဘက်ခလုတ်ကို ဖိနှိပ်ထားပြီး canvas ပေါ်တွင် ထောင့်မှန်စတုဂံတစ်ခုကို ဆွဲပါ။ ဆွဲထားသော ထောင့်မှန်စတုဂံအထဲတွင် legend (ရည်ညွှန်းချက်) ကို ရေးဆွဲထည့်သွင်းပေးမည်ဖြစ်သည်။
#. Canvas ပေါ်ရှိ မြေပုံကို ရွေးချယ်ရန် |select| :sup:`Select/Move item` icon ကိုနှိပ်ပြီး မြေပုံကိုအနည်းငယ်ရွေ့ကြည့်ပါ။
#. မြေပုံ item ကို ရွေးချယ်ထားနေဆဲဖြစ်လျှင် မြေပုံ item ၏အရွယ်အစားကိုလည်း ပြောင်းလဲပေးနိုင်ပါသည်။ အရွယ်အစားကို ပြောင်းလဲရန် မောက်စ်၏ ဘယ်ဘက်ခလုတ်ကို ဖိနှိပ်ထားပြီး မြေပုံ item ၏ ထောင့်လေးထောင့်ထဲမှ အဖြူရောင်ထောင့်မှန်စတုဂံအသေးလေးတစ်ခုကို click နှိပ်ကာ နေရာအသစ်တစ်ခုသို့ ဖိဆွဲ၍ရွှေ့ပါ။ 
#. ဘယ်ဘက်အောက်ခြေရှိ :guilabel:`Item Properties` panel ကို click နှိပ်ပြီး orientation (မျက်နှာမူရာ) အတွက် setting ကို ရှာဖွေပါ။ :guilabel:`Map orientation` (မြေပုံမျက်နှာမူရာ) setting ၏တန်ဖိုးကို '15.00\ |degrees| ' သို့ပြောင်းလဲပါ။ မြေပုံ item ၏ orientation ပြောင်းလဲသွားသည်ကို တွေ့ရမည်ဖြစ်သည်။
#. Print layout ကို print ပြုလုပ်နိုင်သလို :menuselection:`Layout` menu ထဲရှိ export ထုတ်ယူခြင်း tool များဖြင့် ဓာတ်ပုံ format များ၊ PDF သို့မဟုတ် SVG file များသို့ export ထုတ်ယူနိုင်ပါသည်။
#. နောက်ဆုံးတွင် |fileSave| :sup:`Save Project` ခလုတ်ကိုနှိပ်ပြီး project file အတွင်းရှိ ပြင်ဆင်ထားသော print layout ကို သိမ်းဆည်းနိုင်ပါသည်။


Print layout ထဲတွင် element များစွာကို ထည့်သွင်းနိုင်ပါသည်။ တစ်ခုထက်ပိုသောစာမျက်နှာများပေါ်တွင် print layout canvas ထဲရှိ မြေပုံမြင်ကွင်း သို့မဟုတ် ရည်ညွှန်းချက် သို့မဟုတ် စကေးဘား များကို တစ်ခုထက်ပိုပြီး ထည့်သွင်းနိုင်ပါသည်။ Element တစ်ခုချင်းစီတွင် ကိုယ်ပိုင် property များရှိပြီး မြေပုံအတွက်မူ ၎င်း၏ကိုယ်ပိုင် နယ်ပယ်အကျယ်အဝန်း (extent) ရှိပါသည်။ :kbd:`Delete` သို့မဟုတ် :kbd:`Backspace` key ဖြင့် layout canvas မှ မည်သည့် element ကိုမဆို ဖယ်ရှားနိုင်ပါသည်။

.. index:: Layout manager
.. _layout_manager:

The Layout Manager (Layout စီမံခန့်ခွဲသည့်အရာ)
===============================================

:guilabel:`Layout Manager` သည် project ထဲရှိ print layout များကို စီမံခန့်ခွဲသည့် အဓိက window ဖြစ်ပါသည်။ ၎င်းတွင် project ထဲရှိ ရှိနေပြီးသား print layout များနှင့် report (အစီရင်ခံစာ) များကို ခြုံငုံကြည့်ရှုနိုင်ပြီး အောက်ပါတို့ကို လုပ်ဆောင်နိုင်ရန် tool များပါရှိပါသည်-

* Layout တစ်ခုကို ရှာဖွေခြင်း၊
* Print layout အသစ် သို့မဟုတ် အစီရင်ခံစာအသစ်ကို အသစ်မှစတင်ခြင်း၊ နမူနာ (template) မှရယူခြင်း သို့မဟုတ် ရှိနေပြီးသားတစ်ခုမှ ပုံတူပွားခြင်းဖြင့် ပေါင်းထည့်ခြင်း၊
* ၎င်းတို့ထဲမှတစ်ခုခုကို အမည်ပြန်ပေးခြင်း သို့မဟုတ် ဖျက်ပစ်ခြင်း၊
* ၎င်းတို့ကို project ထဲတွင် ဖွင့်ခြင်း။

Layout manager dialog ကိုဖွင့်ရန်-

* QGIS အဓိက dialog မှ :menuselection:`Project --> Layout Manager...` menu ကိုရွေးချယ်ပါ သို့မဟုတ် :guilabel:`Project Toolbar` ထဲရှိ |layoutManager| :sup:`Layout Manager` ခလုတ်ကို နှိပ်ပါ၊
* Print layout တစ်ခု သို့မဟုတ် အစီရင်ခံစာ dialog မှ :menuselection:`Layout --> Layout Manager...` menu ကိုရွေးချယ်ပါ သို့မဟုတ် :guilabel:`Layout Toolbar` ထဲရှိ |layoutManager| :sup:`Layout Manager` ခလုတ်ကို နှိပ်ပါ။

.. _figure_layout_manager:

.. figure:: img/print_composer_manager.png
   :align: center

   Print Layout စီမံခန့်ခွဲသည့်အရာ

Layout manager ၏အပေါ်ဘက်အပိုင်းတွင် project ထဲရှိအသုံးပြုနိုင်သော print layout များ သို့မဟုတ် အစီရင်ခံစာများကို အောက်ပါတို့ကိုလုပ်ဆောင်ရန် tool များဖြင့် စာရင်းပြုစုပေးထားပါသည်-

* ရွေးချယ်ထားမှုကိုပြသပါ - များစွာသော အစီရင်ခံစာများ နှင့်/သို့မဟုတ် print layout (များ) ကိုရွေးချယ်နိုင်ပြီး click တစ်ချက်နှိပ်ကာ ဖွင့်နိုင်ပါသည်။ အမည်တစ်ခုပေါ်တွင် click နှစ်ချက်နှိပ်ပြီးလည်း ဖွင့်နိုင်ပါသည်၊
* ရွေးချယ်ထားသော print layout သို့မဟုတ် အစီရင်ခံစာကို ပုံတူပွားပါ (item တစ်ခုကို ရွေးချယ်ထားမှာသာ ရရှိနိုင်ပါမည်) - ရွေးချယ်ထားသောတစ်ခုကို template (နမူနာ) အနေဖြင့်အသုံးပြုပြီး dialog အသစ်တစ်ခုကို ဖန်တီးပေးပါသည်။ Layout အသစ်အတွက် ခေါင်းစဉ်အသစ်တစ်ခုကို ရွေးချယ်ရန် မေးမြန်းပါလိမ့်မည်၊
* အစီရင်ခံစာ သို့မဟုတ် layout ကို အမည်ပြန်ပေးပါ (item တစ်ခုကို ရွေးချယ်ထားမှာသာ ရရှိနိုင်ပါမည်) - Layout အတွက် ခေါင်းစဉ်အသစ်တစ်ခုကို ရွေးချယ်ရန် မေးမြန်းပါလိမ့်မည်၊
* Layout ကိုဖယ်ရှားပါ - ရွေးချယ်ထားသော print layout (များ) ကို project မှ ဖယ်ရှားပေးပါလိမ့်မည်။

အောက်ဘက်အပိုင်းတွင် print layout အသစ်များ သို့မဟုတ် အစီရင်ခံစာအသစ်များကို အသစ်တစ်ခု သို့မဟုတ် template (နမူနာ) တစ်ခုမှ ဖန်တီးနိုင်ပါသည်။ ပုံမှန်အားဖြင့် QGIS သည် template များကို အသုံးပြုသူ profile နှင့် application template လမ်းကြောင်းများထဲတွင် ရှာဖွေမည်ဖြစ်သလို (Frame ၏အောက်ခြေရှိ ခလုတ်နှစ်ခုဖြင့် အသုံးပြုနိုင်သည်) :menuselection:`Settings --> Options --> Layouts` ထဲရှိ :guilabel:`Path(s) to search for extra print templates` (အပို print template များကိုရှာဖွေရန် လမ်းကြောင်းများ) အနေဖြင့် သတ်မှတ်ထားသော မည်သည့် folder ထဲတွင်မဆို ရှာဖွေမည်ဖြစ်ပါသည်။ ရှာဖွေတွေ့ရှိသော template များကို combobox ထဲတွင် စာရင်းပြုစုထားမည်ဖြစ်သည်။ Item တစ်ခုကို ရွေးချယ်ပြီး :guilabel:`Create` ခလုတ်ကိုနှိပ်ကာ အစီရင်ခံစာအသစ်တစ်ခု သို့မဟုတ် print layout အသစ်တစ်ခုကို ဖန်တီးနိုင်ပါသည်။

စိတ်ကြိုက် folder တစ်ခုမှ layout template များကိုလည်း အသုံးပြုနိုင်ပါသည်။ ထိုသို့လုပ်ရန်အတွက် template များ drop-down (ရွေးချယ်နိုင်သော) စာရင်းထဲတွင် *specific (သီးသန့်)* ကိုရွေးချယ်ပြီး template ရှိရာနေရာသို့သွားရောက်ကာ :guilabel:`Create` ကိုနှိပ်ပါ။    

.. tip:: **Browser panel မှ template ကိုအခြေခံသော print layout များ ဖန်တီးခြင်း**

  File browser တစ်ခုခုမှ print layout template :file:`.qpt` file တစ်ခုကို မြေပုံ canvas ပေါ်သို့ Drag-and-drop (ဖိဆွဲပြီးထည့်) လုပ်ပါ သို့မဟုတ် :ref:`Browser panel <browser_panel>` ထဲရှိ ၎င်း file ကို click နှစ်ချက်နှိပ်ပြီး template မှ print layout အသစ်တစ်ခုကို ဖန်တီးပါ။

.. Todo: Add a link to User profile section when it's ready

.. _print_composer_menus:

Menus, tools and panels of the print layout (Print layout ၏ menu များ၊ tool များနှင့် panel များ)
==================================================================================================

Print layout ကိုဖွင့်လိုက်သောအခါ စာရွက်စာမျက်နှာအလွတ် canvas တစ်ခုပေါ်လာမည်ဖြစ်သည်။ Print layout item များ- QGIS မြေပုံ canvas ၊ စာသားအညွှန်း၊ ဓာတ်ပုံများ၊ ရည်ညွှန်းချက်များ၊ စကေးဘားများ၊ အခြေခံပုံသဏ္ဍာန်များ၊ မြှားများ၊ အချက်အလက်ဇယားများနှင့် HTML ဘောင်များကို ထည့်သွင်းရန်အတွက် canvas ၏ဘယ်ဘက်ခြမ်းတွင် ခလုတ်များကိုတွေ့ရမည်ဖြစ်သည်။ ဤ toolbar ထဲတွင် ညွှန်ပြပေးရန်၊ ဧရိယာတစ်ခုပေါ်တွင် အကျယ်ချဲ့ကြည့်ရန် နှင့် layout ပေါ်ရှိ မြင်ကွင်းကိုရွှေ့ရန် ခလုတ်များပါဝင်သကဲ့သို့ layout item တစ်ခုခုကို ရွေးချယ်ရန်နှင့် မြေပုံ item ၏အကြောင်းအရာများကို နေရာရွှေ့ရန် ခလုတ်များလည်းပါဝင်ပါသည်။


:numref:`figure_layout_overview` သည် element များမထည့်သွင်းမီ print layout ၏ နဂိုမူလ မြင်ကွင်းကို ပြသပေးပါသည်။

.. _figure_layout_overview:

.. figure:: img/print_composer_blank.png
   :align: center
   :width: 100%

   Print Layout


Canvas ၏ဘေး ညာဘက်ခြမ်းတွင် panel အစုနှစ်ခုကို တွေ့ရပါမည်။ အပေါ်ဘက် panel အစုတွင် :guilabel:`Items` panel နှင့် :guilabel:`Undo History` panel ရှိပြီး အောက်ဘက် panel အစုတွင် :guilabel:`Layout` ၊ :guilabel:`Item properties` နှင့် :guilabel:`Atlas generation` panel များကိုတွေ့ရမည်ဖြစ်သည်။

* :guilabel:`Items` panel တွင် canvas ထဲသို့ ထည့်သွင်းသော print layout item များအားလုံး၏စာရင်းရှိမည်ဖြစ်ပြီး ၎င်းတို့နှင့် အပြန်အလှန်လုပ်ဆောင်နိုင်မည့် နည်းလမ်းများပါရှိပါသည် (ပိုမိုသိရှိလိုသည်များအတွက် :ref:`layout_items_panel` တွင် ကြည့်ရှုပါ)။
* :guilabel:`Undo History` panel သည် layout တွင်ပြုလုပ်ထားသော ပြောင်းလဲမှုများအားလုံး၏မှတ်တမ်းကို ပြသပေးပါသည်။ မောက်စ် click တစ်ချက်နှိပ်ရုံဖြင့် layout အဆင့်များကို အခြေအနေတစ်ခုသို့ undo (လုပ်ဆောင်မှုကိုပယ်ဖျက်ခြင်း) နှင့် redo (ပယ်ဖျက်ထားသောလုပ်ဆောင်မှုကိုပြန်လည်လုပ်ဆောင်ခြင်း) ပြုလုပ်ပေးနိုင်ပါသည်။
* :guilabel:`Layout` panel သည် layout ကို export ထုတ်ယူရာတွင် သို့မဟုတ် layout အတွင်းအလုပ်လုပ်ဆောင်ရာတွင် အသုံးပြုသည့် ယေဘုယျ parameter များကို သတ်မှတ်ပေးနိုင်ပါသည်။
* :guilabel:`Item Properties` panel သည် ရွေးချယ်ထားသော item ၏ property ကို ပြသပေးပါသည်။ Canvas ပေါ်ရှိ item တစ်ခု (ဥပမာ- ရည်ညွှန်းချက်၊ စကေးဘား သို့မဟုတ် အညွှန်း) ကို ရွေးချယ်ရန် |select| :sup:`Select/Move item` icon ကို click နှိပ်ပါ။ ထို့နောက် :guilabel:`Item Properties` panel ကိုနှိပ်ပြီး ရွေးချယ်ထားသော item အတွက် setting များကို စိတ်ကြိုက်ပြင်ဆင်ပါ (Item တစ်ခုချင်းစီ၏ setting များ၏ အသေးစိတ်အချက်အလက်အတွက် :ref:`layout_items` တွင်ကြည့်ရှုပါ)
* :guilabel:`Atlas` panel သည် လက်ရှိ layout အတွက် atlas (မြေပုံစီးရီး) တစ်ခုကိုဖန်တီးပေးနိုင်ပြီး ၎င်း၏ parameter များကို အသုံးပြုခွင့်ပေးပါသည် (Altal ဖန်တီးခြင်းဆိုင်ရာအသုံးချမှုများ၏ အသေးစိတ်အချက်အလက်အတွက် :ref:`atlas_generation` တွင် ကြည့်ရှုပါ)


Print layout window ၏ အောက်ခြေဘက်အပိုင်းတွင် အခြေအနေပြဘား (status bar) တစ်ခုကိုတွေ့နိုင်ပြီး ထိုဘားတွင် မောက်စ်၏တည်နေရာ၊ လက်ရှိစာမျက်နှာနံပါတ်၊ zoom level သတ်မှတ်ရန် combo box တစ်ခု၊ ရွေးချယ်ထားသော item အရေအတွက်နှင့် altas ဖန်တီးခြင်းများအတွက် feature များအရေအတွက်တို့ကို ပြသပေးပါသည်။

Print layout window ၏ အပေါ်ဘက်အပိုင်းတွင် menu များနှင့် အခြား toolbar များကို တွေ့နိုင်ပါသည်။ Print layout tool များအားလုံးကို menu ထဲတွင် ရရှိနိုင်ပြီး toolbar တစ်ခုထဲတွင် icon များအနေဖြင့် ရရှိနိုင်မည်ဖြစ်သည်။

Toolbar များနှင့် panel များကို အဖွင့်အပိတ်ပြုလုပ်နိုင်ပြီး ထိုသို့ပြုလုပ်ရန် မည်သည့် toolbar တစ်ခုပေါ်တွင် ညာဘက်မောက်စ် click ကိုအသုံးပြု၍ဖြစ်စေ :menuselection:`View --> Toolbars -->` သို့မဟုတ် :menuselection:`View --> Panels -->` မှဖြစ်စေ ပြုလုပ်နိုင်ပါသည်။

.. index::
   single: Print layout; Tools

.. _layout_tools:

Menus and Tools (Menu များနှင့် tool များ)
-------------------------------------------

Layout menu (အပြင်အဆင် menu)
.............................

:menuselection:`Layout` တွင် layout ကိုစီမံခန့်ခွဲရန် လုပ်ဆောင်ချက်များရှိပါသည်-

* Print layout window မှ project file ကို တိုက်ရိုက်သိမ်းဆည်းခြင်း။
* |newLayout| :guilabel:`New Layout...` ကိုအသုံးပြုပြီး အလွတ် print layout အသစ်တစ်ခုကို ဖန်တီးခြင်း။
* |duplicateLayout| :guilabel:`Duplicate Layout...` (Layout ကို ပုံတူပွားခြင်း) - လက်ရှိ layout တစ်ခုကို ပုံတူပွားခြင်းဖြင့် print layout အသစ်တစ်ခုကို ဖန်တီးခြင်း။
* |deleteSelected| :guilabel:`Delete Layout...` ကိုအသုံးပြုပြီး လက်ရှိ layout ကို ဖယ်ရှားခြင်း။
* |layoutManager| :guilabel:`Layout Manager...` ကို ဖွင့်ခြင်း။
* :menuselection:`Layouts -->` - ရှိနေပြီးသား print layout တစ်ခုကို ဖွင့်ခြင်း။

Layout ကိုပြင်ဆင်ပြီးသည်နှင့် |fileSaveAs| :guilabel:`Save as Template` နှင့် |fileOpen| :guilabel:`Add Items from Template` icon များအသုံးပြုပြီး print layout တစ်ခု၏ လက်ရှိအခြေအနေကို :file:`.qpt` template file တစ်ခုအဖြစ်သိမ်းဆည်းနိုင်ပြီး အခြား print layout များတွင် သိမ်းဆည်းထားသော layout ၏ item များကို ထည့်သွင်းအသုံးပြုနိုင်ပါသည်။

အစီရင်ခံစာများ သို့မဟုတ် စာတမ်းများထဲတွင်ထည့်သွင်းနိုင်သည့် QGIS ဖြင့်ထုတ်လုပ်ထားသော မြေမျက်နှာသွင်ပြင်ဆိုင်ရာအချက်အလက်များကို အခြားသူများနှင့်မျှဝေရန်အတွက် :menuselection:`Layout` menu ထဲတွင် နည်းလမ်းများလည်း ရှိပါသည်။ ၎င်းတို့မှာ |saveMapAsImage| :guilabel:`Export as Image...` (ဓာတ်ပုံအနေဖြင့် export ထုတ်ခြင်း)၊ |saveAsPDF| :guilabel:`Export as PDF...` (PDF အနေဖြင့် export ထုတ်ခြင်း)၊ |saveAsSVG| :guilabel:`Export as SVG...` (SVG အနေဖြင့် export ထုတ်ခြင်း) နှင့် |filePrint| :guilabel:`Print...` (Print ပြုလုပ်ခြင်း) တို့ဖြစ်ကြပါသည်။

အောက်ဖော်ပြပါစာရင်းသည် အချက်အလက်အချို့ပါဝင်သော menu ထဲရှိ အသုံးပြုနိုင်သည့် tool များစာရင်းတစ်ခုဖြစ်ပါသည်။

================================================= ========================== ========================== =====================================
 Tool                                              Shortcut                   Toolbar                    Reference
================================================= ========================== ========================== =====================================
 |fileSave| :guilabel:`Save Project`               :kbd:`Ctrl+S`              :guilabel:`Layout`         :ref:`sec_projects`
 |newLayout| :guilabel:`New Layout`                :kbd:`Ctrl+N`              :guilabel:`Layout`         :ref:`layout_manager`
 |duplicateLayout| :guilabel:`Duplicate Layout`                               :guilabel:`Layout`         :ref:`layout_manager`
 |deleteSelected| :guilabel:`Delete Layout`
 |layoutManager| :guilabel:`Layout Manager...`                                :guilabel:`Layout`         :ref:`layout_manager`
 :menuselection:`Layouts -->`
 :guilabel:`Layout Properties...`                                                                        :ref:`layout_panel`
 :guilabel:`Rename Layout...`
 |newPage| :guilabel:`Add Pages...`                                           :guilabel:`Layout`         :ref:`page_properties`
 |fileOpen| :guilabel:`Add Items from Template`                               :guilabel:`Layout`         :ref:`create_layout_item`
 |fileSaveAs| :guilabel:`Save as Template...`                                 :guilabel:`Layout`         :ref:`layout_manager`
 |saveMapAsImage| :guilabel:`Export as Image...`                              :guilabel:`Layout`         :ref:`export_layout_image`
 |saveAsSVG| :guilabel:`Export as SVG...`                                     :guilabel:`Layout`         :ref:`export_layout_svg`
 |saveAsPDF| :guilabel:`Export as PDF...`                                     :guilabel:`Layout`         :ref:`export_layout_pdf`
 :guilabel:`Page Setup...`                         :kbd:`Ctrl+Shift+P`
 |filePrint| :guilabel:`Print...`                  :kbd:`Ctrl+P`              :guilabel:`Layout`         :ref:`create-output`
 :guilabel:`Close`                                 :kbd:`Ctrl+Q`
================================================= ========================== ========================== =====================================

Edit menu (တည်းဖြတ်ပြင်ဆင်ခြင်း menu)
......................................

:menuselection:`Edit` menu တွင် print layout item များကို ကိုင်တွယ်ရန် tool များပါရှိပါသည်။ Layout ထဲရှိ item များအတွက် ရွေးချယ်ခြင်းဆိုင်ရာ tool များ၊ Copy/Cut/Paste (ကူးယူ/ရွှေ့ပြောင်း/နေရာချ) နှင့် undo/redo (:ref:`layout_undo_panel` တွင်ကြည့်ရှုပါ) လုပ်ဆောင်နိုင်စွမ်းများကဲ့သို့ အသုံးများသော လုပ်ဆောင်ချက်များ ပါဝင်ပါသည်။

Paste (နေရာချ) လုပ်ဆောင်ချက်ကိုအသုံးပြုသောအခါ လက်ရှိ မောက်စ်တည်နေရာအတိုင်း element များကို paste လုပ်မည်ဖြစ်သည်။ :menuselection:`Edit --> Paste in Place` လုပ်ဆောင်ချက်ကိုအသုံးပြု၍ဖြစ်စေ :kbd:`Ctrl+Shift+V` ကိုနှိပ်၍ဖြစ်စေ နဂိုစာမျက်နှာပေါ်တွင်ရှိခဲ့သည့်တည်နေရာအတိုင်း လက်ရှိစာမျက်နှာပေါ်တွင် item များကို paste လုပ်ပေးမည်ဖြစ်သည်။ ၎င်းသည် စာမျက်နှာတစ်ခုမှတစ်ခုသို့ item များကူးယူပြောင်းရွှေ့ရာတွင် နေရာအတူတူဖြစ်စေပါသည်။

အောက်ဖော်ပြပါစာရင်းသည် အချက်အလက်အချို့ပါဝင်သော menu ထဲရှိ အသုံးပြုနိုင်သည့် tool များစာရင်းတစ်ခုဖြစ်ပါသည်။

.. csv-table:: အသုံးပြုနိုင်သော Tool များ
   :header: "Tool", "Shortcut", "Toolbar", "Reference"
   :widths: 30, 17, 10, 33

   "|undo| :guilabel:`Undo (last change)`", ":kbd:`Ctrl+Z`", ":guilabel:`Layout`", ":ref:`layout_undo_panel`"
   "|redo| :guilabel:`Redo (last reverted change)`", ":kbd:`Ctrl+Y`", ":guilabel:`Layout`", ":ref:`layout_undo_panel`"
   "|deleteSelected| :guilabel:`Delete`", ":kbd:`Del`"
   "|editCut| :guilabel:`Cut`", ":kbd:`Ctrl+X`"
   "|editCopy| :guilabel:`Copy`", ":kbd:`Ctrl+C`"
   "|editPaste| :guilabel:`Paste`", ":kbd:`Ctrl+V`"
   ":guilabel:`Paste in place`", ":kbd:`Ctrl+Shift+V`"
   "|selectAll| :guilabel:`Select All`", ":kbd:`Ctrl+A`"
   "|deselectAll| :guilabel:`Deselect all`", ":kbd:`Ctrl+Shift+A`"
   "|invertSelection| :guilabel:`Invert Selection`"
   ":guilabel:`Select Next Item Below`", ":kbd:`Ctrl+Alt+[`"
   ":guilabel:`Select Next Item above`", ":kbd:`Ctrl+Alt+]`"
   "|pan| :guilabel:`Pan Layout`", ":kbd:`P`", ":guilabel:`Toolbox`"
   "|zoomToArea| :guilabel:`Zoom`", ":kbd:`Z`", ":guilabel:`Toolbox`"
   "|select| :guilabel:`Select/Move Item`", ":kbd:`V`", ":guilabel:`Toolbox`", ":ref:`interact_layout_item`"
   "|moveItemContent| :guilabel:`Move Content`", ":kbd:`C`", ":guilabel:`Toolbox`", ":ref:`layout_map_item`"
   "|editNodesShape| :guilabel:`Edit Nodes Item`", "", ":guilabel:`Toolbox`", ":ref:`layout_node_based_shape_item`"



View menu (မြင်ကွင်းဆိုင်ရာ menu)
..................................

:menuselection:`View` menu တွင် ညွှန်ပြခြင်းဆိုင်ရာ tool များပါရှိပြီး print layout ၏ ယေဘုယျအပြုအမူကို ပြင်ဆင်သတ်မှတ်ပေးနိုင်ပါသည်။ အသုံးများသော zoom ပြုလုပ်သည့် tool များအပြင် အောက်ပါတို့ကိုလည်း လုပ်ဆောင်နိုင်ပါသည်-

* |refresh| :sup:`Refresh view` (မြင်ကွင်းသည် တသမတ်တည်းမရှိသည့်အခြေအနေတစ်ခုတွင်ရှိလျှင်)။
* Item များကို ရွှေ့ခြင်း သို့မဟုတ် ဖန်တီးခြင်းများလုပ်သောအခါ ၎င်း item များနှင့်ဆွဲကပ်ပေးနိုင်ရန် :ref:`grid <grid_guides>` (အကွက်) တစ်ခုဖွင့်ပေးပါ။ Grid များဆိုင်ရာ setting ကို :menuselection:`Settings --> Layout Options...` သို့မဟုတ် :ref:`Layout Panel <layout_panel>` ထဲတွင် လုပ်ဆောင်နိုင်ပါသည်။
* Item များကို ရွှေ့ခြင်း သို့မဟုတ် ဖန်တီးခြင်းများလုပ်သောအခါ ၎င်း item များနှင့်ဆွဲကပ်ပေးနိုင်ရန် :ref:`guides <grid_guides>` (ဒေါင်လိုက် သို့မဟုတ် ရေပြင်ညီမျဉ်း) များကို ဖွင့်ပေးပါ။ Guide များသည် အနီရောင်မျဉ်းများဖြစ်ပြီး ruler (layout ၏ အထက် သို့မဟုတ် ဘယ်ဘက်တွင်ရှိသော) ထဲတွင် click နှိပ်ခြင်းဖြင့် ဖန်တီးနိုင်ပါသည်။ ၎င်းတို့ကို လိုချင်သောနေရာများသို့ ဖိဆွဲရွှေ့ပြောင်းပေးနိုင်ပါသည်။ 
* :guilabel:`Smart Guides` (ပိုကောင်းသော guide များ) - Item တစ်ခုကို ရွှေ့ပြောင်း သို့မဟုတ် သဏ္ဍာန်ပြောင်းလဲလိုက်တိုင်း အလိုအလျှောက်ပြောင်းလဲကာ ဆွဲကပ်နိုင်ရန် အခြား layout item များကို guide များအနေဖြင့် အသုံးပြုပါသည်။
* :guilabel:`Clear Guides` (Guide များကို ရှင်းလင်းခြင်း) - လက်ရှိအသုံးပြုနေသော guide များအားလုံးကို ဖယ်ရှားပေးပါသည်။
* :guilabel:`Show Bounding box` (စတုဂံပုံစံနယ်ပယ်အကျယ်အဝန်းကိုပြသခြင်း) - ရွေးချယ်မှုကို ကောင်းမွန်စွာ ဖော်ထုတ်ပြသနိုင်ရန် item များ၏ပတ်လည်တွင် bounding box ကို ပြသပေးပါသည်။
* :guilabel:`Show Rules` - Layout ၏ပတ်လည်တွင် rule (စည်းမျဉ်း) များကို ပြသပေးပါသည်။
* :guilabel:`Show Pages` (စာမျက်နှာများကိုပြသပါ) သို့မဟုတ် ဖောက်ထွင်းမြင်ရစေရန် စာမျက်နှာများကို သတ်မှတ်ပါ။ ရံဖန်ရံခါ layout ကို non-print (print မပြုလုပ်မည့်) layout များကိုဖန်တီးရန်အသုံးပြုပါသည်၊ ဥပမာ- presentation များ သို့မဟုတ် အခြားမှတ်တမ်းများတွင် ထည့်သွင်းခြင်း။ ထိုသို့သောအခါမျိုးတွင် လုံးဝဖောက်ထွင်းမြင်ရသော နောက်ခံတစ်ခုကိုအသုံးပြုပြီး export ထုတ်ခြင်းသည် အဆင်ပြေစေပါသည်။ ၎င်းကို အခြား editing (တည်းဖြတ်ခြင်း) package များတွင် "infinite canvas" အဖြစ် တစ်ခါတရံ ရည်ညွှန်းပါသည်။

Print layout ထဲတွင် zoom level ကို မောက်စ်ဘီးလုံး သို့မဟုတ် status bar ထဲရှိ slider နှင့် combo box ကိုအသုံးပြုပြီး ပြောင်းလဲနိုင်ပါသည်။ Layout ဧရိယာထဲတွင် အလုပ်လုပ်နေစဉ် pan (မြင်ကွင်းရွှေ့နိုင်သည့်) mode သို့ ပြောင်းလဲလိုလျှင် :kbd:`Spacebar` သို့မဟုတ် မောက်စ်ဘီးလုံးကို ဖိထားနိုင်ပါသည်။ :kbd:`Ctrl+Spacebar` ကိုနှိပ်ပြီး Zoom In (zoom ချဲ့) mode သို့ ယာယီပြောင်းထားနိုင်ပြီး :kbd:`Ctrl+Alt+Spacebar` ဖြင့် Zoom Out (zoom ချုံ့) mode သို့ ယာယီပြောင်းထားနိုင်ပါသည်။

Panel များနှင့် toolbar များကို :menuselection:`View -->` menu မှ အသုံးပြုနိုင်အောင်ဖွင့်ပေးနိုင်ပါသည်။ Panel များနှင့် toolbar များဖွဲ့စည်းထားရှိမှုအရပြောင်းလဲနိုင်သော နေရာပိုမိုကျယ်လာစေရန် |checkbox| :menuselection:`View --> Toggle Panel Visibility` ကို အမှန်ခြစ်ခြစ်နိုင်သလို :kbd:`Ctrl+Tab` ကိုလည်းနှိပ်နိုင်ပါသည်- အမှန်ခြစ်ဖျောက်ထားသောအခါ panel များအားလုံးကို ဖျောက်ထားပေးမည်ဖြစ်ပြီး အရင်ကမြင်ရအောင်ဖွင့်ထားသော panel များကိုသာ ပြန်လည်ဖော်ပြပေးမည်ဖြစ်သည်။

:kbd:`F11` သို့မဟုတ် :menuselection:`View -->` |checkbox| :guilabel:`Toggle Full Screen` ကိုအသုံးပြုပြီး လုပ်ဆောင်ရန် နေရာပိုမိုရရှိစေရန် မြင်ကွင်းမျက်နှာပြင်အပြည့် (full screen) mode ကိုလည်း ပြောင်းလဲပေးနိုင်ပါသည်။


================================================= ========================== ========================== =====================================
 Tool                                              Shortcut                   Toolbar                    Reference
================================================= ========================== ========================== =====================================
 |refresh| :guilabel:`Refresh`                     :kbd:`F5`                  :guilabel:`Navigation`
 :menuselection:`Preview -->`
 |zoomIn| :guilabel:`Zoom In`                      :kbd:`Ctrl++`              :guilabel:`Navigation`
 |zoomOut| :guilabel:`Zoom Out`                    :kbd:`Ctrl+-`              :guilabel:`Navigation`
 |zoomActual| :guilabel:`Zoom to 100%`             :kbd:`Ctrl+1`              :guilabel:`Navigation`
 |zoomFullExtent| :guilabel:`Zoom Full`            :kbd:`Ctrl+0`              :guilabel:`Navigation`
 :guilabel:`Zoom to Width`
 |vectorGrid| :guilabel:`Show Grid`                :kbd:`Ctrl+'`                                         :ref:`grid_guides`
 |unchecked| :guilabel:`Snap to Grid`              :kbd:`Ctrl+Shift+'`                                   :ref:`grid_guides`
 |checkbox| :guilabel:`Show Guides`                :kbd:`Ctrl+;`                                         :ref:`grid_guides`
 |checkbox| :guilabel:`Snap to Guides`             :kbd:`Ctrl+Shift+;`                                   :ref:`grid_guides`
 |checkbox| :guilabel:`Smart Guides`               :kbd:`Ctrl+Alt+;`
 :guilabel:`Manage Guides...`                      \                          \                          :ref:`layout_guides_panel`
 :guilabel:`Clear Guides`                          \                          \                          :ref:`layout_guides_panel`
 |checkbox| :guilabel:`Show Rulers`                :kbd:`Ctrl+R`
 |checkbox| :guilabel:`Show Bounding Boxes`        :kbd:`Ctrl+Shift+B`
 |checkbox| :guilabel:`Show Pages`
 :menuselection:`Toolbars -->`                      \                         \                          :ref:`sec_panels_and_toolbars`
 :menuselection:`Panels -->`                        \                         \                          :ref:`sec_panels_and_toolbars`
 |unchecked| :guilabel:`Toggle Full Screen`        :kbd:`F11`                 \                          :ref:`view_menu`
 |unchecked| :guilabel:`Toggle Panel Visibility`   :kbd:`Ctrl+Tab`            \                          :ref:`view_menu`
================================================= ========================== ========================== =====================================

Items menu (Item များဆိုင်ရာ menu)
...................................

:menuselection:`Items` သည် layout ထဲရှိ item များ၏တည်နေရာနှင့် ၎င်းတို့အကြား ဆက်နွယ်မှုများကို ပြင်ဆင်သတ်မှတ်ရာတွင် အကူအညီပေးပါသည် (:ref:`interact_layout_item` တွင်ကြည့်ရှုပါ)။


================================================= ========================== ========================== ==========================
 Tool                                              Shortcut                   Toolbar                    Reference
================================================= ========================== ========================== ==========================
 |groupItems| :guilabel:`Group`                    :kbd:`Ctrl+G`              :guilabel:`Actions`        :ref:`group_items`
 |ungroupItems| :guilabel:`Ungroup`                :kbd:`Ctrl+Shift+G`        :guilabel:`Actions`        :ref:`group_items`
 |raiseItems| :guilabel:`Raise`                    :kbd:`Ctrl+]`              :guilabel:`Actions`        :ref:`align_items`
 |lowerItems| :guilabel:`Lower`                    :kbd:`Ctrl+[`              :guilabel:`Actions`        :ref:`align_items`
 |moveItemsToTop| :guilabel:`Bring to Front`       :kbd:`Ctrl+Shift+]`        :guilabel:`Actions`        :ref:`align_items`
 |moveItemsToBottom| :guilabel:`Send to Back`      :kbd:`Ctrl+Shift+[`        :guilabel:`Actions`        :ref:`align_items`
 |locked| :guilabel:`Lock Selected Items`          :kbd:`Ctrl+L`              :guilabel:`Actions`        :ref:`lock_items`
 |unlocked| :guilabel:`Unlock All`                 :kbd:`Ctrl+Shift+L`        :guilabel:`Actions`        :ref:`lock_items`
 :menuselection:`Align Items -->`                                             :guilabel:`Actions`        :ref:`align_items`
 :menuselection:`Distribute Items -->`                                        :guilabel:`Actions`        :ref:`move_resize`
 :menuselection:`Resize -->`                                                  :guilabel:`Actions`        :ref:`move_resize`
================================================= ========================== ========================== ==========================

Add Item menu (Item ပေါင်းထည့်ခြင်း menu)
..........................................

Layout item များကို ဖန်တီးရန် tool များ ရှိပါသည်။ ၎င်းတို့တစ်ခုချင်းစီအကြောင်းကို :ref:`layout_items` အခန်းတွင် အသေးစိတ်ဖော်ပြထားပါသည်။

========================================================= ======================== =====================================
 Tool                                                      Toolbar                    Reference
========================================================= ======================== =====================================
 |addMap| :guilabel:`Add Map`                              :guilabel:`Toolbox`        :ref:`layout_map_item`
 |add3DMap| :guilabel:`Add 3D Map`                         :guilabel:`Toolbox`        :ref:`layout_map3d_item`
 |addImage| :guilabel:`Add Picture`                        :guilabel:`Toolbox`        :ref:`layout_picture_item`
 |label| :guilabel:`Add Label`                             :guilabel:`Toolbox`        :ref:`layout_label_item`
 :menuselection:`Add Dynamic Text -->`                                                :ref:`The Label Item <layout_label_main_properties>`
 |addLegend| :guilabel:`Add Legend`                        :guilabel:`Toolbox`        :ref:`layout_legend_item`
 |scaleBar| :guilabel:`Add Scale Bar`                      :guilabel:`Toolbox`        :ref:`layout_scalebar_item`
 |northArrow| :guilabel:`Add North Arrow`                  :guilabel:`Toolbox`        :ref:`layout_northarrow_item`
 |addBasicShape| :menuselection:`Add Shape -->`            :guilabel:`Toolbox`        :ref:`layout_basic_shape_item`
 |addBasicRectangle| :menuselection:`--> Add Rectangle`    :guilabel:`Toolbox`        :ref:`layout_basic_shape_item`
 |addBasicCircle| :menuselection:`--> Add Ellipse`         :guilabel:`Toolbox`        :ref:`layout_basic_shape_item`
 |addBasicTriangle| :menuselection:`--> Add Triangle`      :guilabel:`Toolbox`        :ref:`layout_basic_shape_item`
 |addMarker| :guilabel:`Add Marker`                        :guilabel:`Toolbox`        :ref:`layout_marker_item`
 |addArrow| :guilabel:`Add Arrow`                          :guilabel:`Toolbox`        :ref:`layout_arrow_item`
 |addNodesShape| :menuselection:`Add Node Item -->`        :guilabel:`Toolbox`        :ref:`layout_node_based_shape_item`
 |addPolygon| :menuselection:`--> Add Polygon`             :guilabel:`Toolbox`        :ref:`layout_node_based_shape_item`
 |addPolyline| :menuselection:`--> Add Polyline`           :guilabel:`Toolbox`        :ref:`layout_node_based_shape_item`
 |addHtml| :guilabel:`Add HTML`                            :guilabel:`Toolbox`        :ref:`layout_html_item`
 |addTable| :guilabel:`Add Attribute Table`                :guilabel:`Toolbox`        :ref:`layout_attribute_table_item`
 |addManualTable| :guilabel:`Add Fixed Table`              :guilabel:`Toolbox`        :ref:`layout_fixed_table_item`
 |elevationProfile| :guilabel:`Add Elevation Profile`      :guilabel:`Toolbox`        :ref:`layout_elevation_profile_item`
========================================================= ======================== =====================================


Atlas menu (မြေပုံစီးရီးဆိုင်ရာ menu)
......................................

======================================================== ========================== ========================== =====================================
 Tool                                                     Shortcut                   Toolbar                    Reference
======================================================== ========================== ========================== =====================================
 |atlas| :guilabel:`Preview Atlas`                        :kbd:`Ctrl+ALt+/`          :guilabel:`Atlas`          :ref:`atlas_preview`
 |atlasFirst| :guilabel:`First Feature`                   :kbd:`Ctrl+<`              :guilabel:`Atlas`          :ref:`atlas_preview`
 |atlasPrev| :guilabel:`Previous Feature`                 :kbd:`Ctrl+,`              :guilabel:`Atlas`          :ref:`atlas_preview`
 |atlasNext| :guilabel:`Next Feature`                     :kbd:`Ctrl+.`              :guilabel:`Atlas`          :ref:`atlas_preview`
 |atlasLast| :guilabel:`Last feature`                     :kbd:`Ctrl+>`              :guilabel:`Atlas`          :ref:`atlas_preview`
 |filePrint| :guilabel:`Print Atlas...`                                              :guilabel:`Atlas`          :ref:`atlas_preview`
 |saveMapAsImage| :guilabel:`Export Atlas as Images...`                              :guilabel:`Atlas`          :ref:`atlas_preview`
 |saveAsSVG| :guilabel:`Export Atlas as SVG...`                                      :guilabel:`Atlas`          :ref:`atlas_preview`
 |saveAsPDF| :guilabel:`Export Atlas as PDF...`                                      :guilabel:`Atlas`          :ref:`atlas_preview`
 |atlasSettings| :guilabel:`Atlas Settings`                                          :guilabel:`Atlas`          :ref:`atlas_generation`
======================================================== ========================== ========================== =====================================


Settings Menu (Setting များဆိုင်ရာ menu)
.........................................

:menuselection:`Settings --> Layout Options...` menu သည် QGIS အဓိက canvas ၏ :menuselection:`Settings --> Options --> Layouts` menu သို့ရောက်မည့် shortcut (ဖြတ်လမ်းနည်း) တစ်ခုဖြစ်သည်။ ဤတွင် မည်သည့် print layout အသစ်တွင်မဆို default (မူရင်း) အဖြစ်အသုံးပြုမည့် အချို့ရွေးချယ်စရာများကို သတ်မှတ်ပေးနိုင်ပါသည်-

* :guilabel:`Layout defaults` သည် အသုံးပြုမည့် default စာလုံးဖောင့်ကို သတ်မှတ်ပေးစေနိုင်ပါသည်၊
* :guilabel:`Grid appearance` ဖြင့် grid style နှင့် အရောင်ကို သတ်မှတ်ပေးနိုင်ပါသည်။ Grid အမျိုးအစား သုံးမျိုးရှိပါသည် - **Dots (အစက်များ)** ၊ **Solid (အပြည့်)** လိုင်းများ နှင့် **Crosses (ကြက်ခြေခတ်များ)** ဖြစ်ပါသည်။
* :guilabel:`Grid and guide defaults` သည် grid ၏ spacing (အကျယ်)၊ offset (အရွေ့) နှင့် tolerance (လက်သင့်ခံနိုင်မှု) များကို သတ်မှတ်ပေးပါသည် (အသေးစိတ်ကို :ref:`grid_guides` တွင် ကြည့်ရှုပါ)၊
* :guilabel:`Layout Paths` - Print template များကိုရှာဖွေရန် စိတ်ကြိုက်လမ်းကြောင်းများစာရင်းကို စီမံခန့်ခွဲရန်ဖြစ်ပါသည်။ :menuselection:`Settings --> Keyboard Shortcuts...` menu သည် print layout မျက်နှာပြင်ထဲတွင် :ref:`shortcuts manager <shortcuts>` များကို အသုံးပြုခွင့်ပေးပါသည်။

Contextual menus (ဆက်စပ်အကြောင်းအရာဆိုင်ရာ menu များ)
......................................................

Print layout dialog ထဲရှိ မည်သည့်နေရာတွင် right-click နှိပ်သည်ပေါ်မူတည်၍ အမျိုးမျိုးသောအသွင်အပြင်များပါဝင်သော contextual menu တစ်ခုပွင့်လာမည်ဖြစ်သည်-

* Menu bar သို့မဟုတ် toolbar တစ်ခုခုပေါ်တွင် right-click နှိပ်ပါက layout panel များနှင့် toolbar များစာရင်း ပေါ်လာမည်ဖြစ်ပြီး ၎င်းတို့ကို အဖွင့်အပိတ်ပြုလုပ်နိုင်ပါသည်။

* Ruler (ပေတံ) ပေါ်တွင် right-click နှိပ်ပါက |checkbox| :guilabel:`Show Guides` (Guide များကိုပြသခြင်း) ၊ |checkbox| :guilabel:`Snap to Guides` (Guide များသို့ ဆွဲကပ်ခြင်း)၊ :guilabel:`Manage Guides...` (Guide များကို စီမံခန့်ခွဲခြင်း) - :ref:`Guides panel <layout_guides_panel>` ပွင့်လာပါမည်၊ သို့မဟုတ် :guilabel:`Clear Guides` (Guide များကို ရှင်းလင်းခြင်း) များပြုလုပ်နိုင်ပါသည်။ Ruler (ပေတံ) များကိုလည်း ဖျောက်ထားနိုင်ပါသည်။

* Print layout canvas ထဲတွင် right-click နှိပ်ပြီး-

  * လက်တလောပြောင်းလဲမှုများကို :guilabel:`Undo` နှင့် :guilabel:`Redo` ပြုလုပ်နိုင်သလို ကူးယူထားသော မည်သည့် item ကိုမဆို :guilabel:`Paste` ပြုလုပ်နိုင်ပါသည် (မည်သည့် item ကိုမျှ ရွေးချယ်ထားခြင်းမရှိမှသာ အသုံးပြုနိုင်ပါမည်)

  * စာမျက်နှာတစ်ခုပေါ်တွင် click နှိပ်လျှင် လက်ရှိ စာမျက်နှာ၏ :ref:`Page
    Properties <page_properties>` panel ကို အသုံးပြုနိုင်သလို :guilabel:`Remove Page` (စာမျက်နှာကိုဖယ်ရှား) လည်းပြုလုပ်နိုင်ပါသည်။
  * ရွေးချယ်ထားသော item တစ်ခုပေါ်တွင် click နှိပ်ပြီးလျှင် ၎င်း item ကို ရွှေ့ခြင်း သို့မဟုတ် ကူးယူခြင်း ပြုလုပ်နိုင်သည့်အပြင် :ref:`Item Properties <layout_item_options>` panel ကိုလည်း ဖွင့်နိုင်ပါသည်။
  * Item တစ်ခုထက်ပို၍ ရွေးချယ်ထားလျှင် ၎င်း item များကို အုပ်စုဖွဲ့ခြင်း (group) နှင့်/သို့မဟုတ် ရွေးချယ်ထားမှုထဲတွင် အနည်းဆုံး အုပ်စုတစ်ခုရှိနေပြီးသားဖြစ်လျှင် ၎င်းအုပ်စုကို ပြန်ခွဲထုတ်ခြင်း (ungroup) ပြုလုပ်နိုင်ပါသည်။  
* Text (စာသား) box တစ်ခုအတွင်း သို့မဟုတ် မည်သည့် layout panel ၏ spinbox widget အတွင်း right-click ပြုလုပ်ခြင်းသည် ၎င်း၏အကြောင်းအရာကို ကိုင်တွယ်နိုင်ရန် edit (တည်းဖြတ်ခြင်း) ရွေးချယ်စရာများကို ရရှိနိုင်ပါသည်။  


.. _layout_panel:

The Layout Panel (Layout ဆိုင်ရာ panel)
----------------------------------------

:guilabel:`Layout` panel ထဲတွင် print layout ၏ ယေဘုယျ setting များကို သတ်မှတ်ပေးနိုင်ပါသည်။

.. _figure_composition:

.. figure:: img/composition_settings.png
   :align: center

   Print Layout ထဲရှိ Layout setting များ

.. _reference_map:

General settings (အထွေထွေ setting များ)
........................................

Print layout တစ်ခုထဲတွင် တစ်ခုထက်ပိုသော မြေပုံ item များကို အသုံးပြုနိုင်ပါသည်။ :guilabel:`Reference map` သည် layout ၏ မာစတာမြေပုံ အဖြစ်အသုံးပြုမည့် မြေပုံ item ကိုကိုယ်စားပြုပါသည်။ Layout ထဲတွင် မြေပုံ item တစ်ခုရှိနေသမျှ ၎င်းကို သတ်မှတ်ထားမည်ဖြစ်သည်။ Layout သည် ထို reference မြေပုံကို ၎င်းတို့၏ property များတစ်ခုခုထဲနှင့် ယူနစ်များ သို့မဟုတ် စကေး ကိုတွက်ချက်ပေးသော variable များထဲတွင် အသုံးပြုမည်ဖြစ်သည်။ ၎င်းတွင် print layout ကို georeference ပြုလုပ်ထားသော format အဖြစ် export ထုတ်ယူခြင်းပါဝင်ပါသည်။

ထို့အပြင် စကေးဘား၊ ရည်ညွှန်းချက် သို့မဟုတ် မြောက်အရပ်ပြမြှား များကဲ့သို့ layout item အသစ်များတွင် ၎င်းတို့ကိုရေးဆွဲထားသော မြေပုံ item နှင့်ချိတ်ဆက်နေသော default setting များ (မျက်နှာမူရာ၊ ပြသသော layer များ၊ စကေး၊....) ပါရှိပြီး ထပ်နေသော မြေပုံမရှိလျှင် reference မြေပုံကိုသာ အားထားမည်ဖြစ်သည်။

.. _grid_guides:

Guides and Grid (Guide များနှင့် Grid)
.......................................

အချို့ item များကို တိကျစွာနေရာချထားနိုင်ရန် စာရွက်ပေါ်တွင် reference အမှတ်အသား (mark) အချို့ကို ထားရှိနိုင်ပါသည်။ ထိုအမှတ်အသားများသည် အောက်ပါတို့ဖြစ်နိုင်ပါသည်-

* အလိုရှိရာနေရာတွင် ထားရှိသော ရိုးရိုး ရေပြင်ညီ သို့မဟုတ် ဒေါင်လိုက် မျဉ်းများ (**Guides** ဟုခေါ်ပါသည်) (Guide များဖန်တီးခြင်းအတွက် :ref:`layout_guides_panel` တွင်ကြည့်ရှုပါ)   
* သို့မဟုတ် ပုံမှန် **Grid** - Layout ပေါ်တွင် ထပ်ထားသော ရေပြင်ညီနှင့် ဒေါင်လိုက်မျဉ်းများ ကွန်ယက်တစ်ခု 

:guilabel:`Grid spacing` (Grid အကျယ်) သို့မဟုတ် :guilabel:`Grid offset` (Grid အရွေ့) ကဲ့သို့ setting များကို ဤအုပ်စုထဲတွင် ချိန်ညှိပေးနိုင်ပြီး item များအတွက် အသုံးပြုမည့် :guilabel:`Snap tolerance` (ဆွဲကပ်ခြင်းအတွက် လက်သင့်ခံနိုင်မှု) ကိုလည်း ချိန်ညှိပေးနိုင်ပါသည်။ Tolerance (လက်သင့်ခံနိုင်မှု) ဆိုသည်မှာ item တစ်ခုကို ရွှေ့နေစဉ်၊ အရွယ်အစားပြောင်းနေစဉ် သို့မဟုတ် ဖန်တီးနေစဉ်တွင် grid တစ်ခု သို့မဟုတ် guide တစ်ခုသို့ မောက်စ်၏မြှားမှ ဆွဲကပ်မည့် အများဆုံးအကွာအဝေးဖြစ်ပါသည်။ 

Grid သို့မဟုတ် guide များကို ပြသမည်/မပြသမည်ကို :menuselection:`View` menu ထဲတွင် သတ်မှတ်ပါသည်။ ၎င်းတို့ကို layout item များသို့ ဆွဲကပ်ရာ၌ အသုံးပြု/မပြုကိုလည်း ဆုံးဖြတ်ပေးနိုင်ပါသည်။ Grid မျဉ်းတစ်ခုနှင့် guide မျဉ်းတစ်ခု နှစ်ခုစလုံးသည် point တစ်ခု၏ tolerance (လက်သင့်ခံနိုင်မှု) အတွင်း ရှိနေသောအခါ guide များကို အမြဲတမ်း ဦးစားပေးမည်ဖြစ်သည်- အဘယ်ကြောင့်ဆိုသော ၎င်းတို့ကို ကိုယ်တိုင်သတ်မှတ်ပေးထားသောကြောင့်ဖြစ်သည် (ထို့ကြောင့် ၎င်းတို့ကို အလိုချင်ဆုံး ဆွဲကပ်မည့်တည်နေရာ၌ အတိအလင်းထားရှိပြီး ယေဘုယျ grid ကိုကျော်၍ ရွေးချယ်သင့်သည်ဟု ယူဆရပါမည်)။

.. note::
  :menuselection:`Settings --> Layout Options` menu ထဲတွင် အထက်တွင်ဖော်ပြထားသော grid နှင့် guide parameter များကိုလည်း သတ်မှတ်ပေးနိုင်ပါသည်။ သို့သော် ထို ရွေးချယ်စရာများသည် print layout အသစ်များတွင် default များအနေဖြင့်သာ အသုံးပြုမည်ဖြစ်သည်။

.. _layout_export_settings:

Export settings (Export ထုတ်ယူခြင်း setting များ)
..................................................

:guilabel:`Export resolution` ထဲတွင် export ထုတ်ယူမည့် မြေပုံများအားလုံးအတွက် အသုံးပြုမည့် resolution (ကြည်လင်ပြတ်သားမှု) တစ်ခုကို သတ်မှတ်ပေးနိုင်ပါသည်။ မြေပုံတစ်ခုကို export တစ်ကြိမ်ပြုလုပ်တိုင်း ထို setting ကို အစားထိုးပြင်ဆင်ပေးနိုင်ပါသည်။

အချို့အဆင့်မြင့် ပုံဖော်ပြသခြင်းဆိုင်ရာ ရွေးချယ်စရာများ (:ref:`blending mode (ရောစပ်ခြင်းနည်းလမ်း) <blend-modes>`,
:ref:`effects (အထူးပြုလုပ်ချက်များ) <draw_effects>`...) ကြောင့် မှန်ကန်စွာ export ထုတ်ယူနိုင်ရန် layout item တစ်ခုကို raster သို့ပြောင်းလဲပေးရန် လိုကောင်းလိုနိုင်ပါသည်။ QGIS သည် အခြား item အားလုံးကိုပြောင်းလဲပေးရန်မလိုပဲ ထို item တစ်ခုကို သီးသန့် raster ပြောင်းလဲပေးပါလိမ့်မည်။ ထိုသို့လုပ်ဆောင်ခြင်းသည်  ရရှိနိုင်သလောက် item များကို vector များအနေဖြင့် ဆက်လက်ထားရှိပေးရန် PostScript သို့မဟုတ် PDF အဖြစ် print ပြုလုပ်ခြင်း သို့မဟုတ် သိမ်းဆည်းပေးခြင်း ပြုလုပ်ပေးပါသည်၊ ဥပမာ- layer opacity (အလင်းပိတ်နှုန်း) ပါရှိသော မြေပုံ item တစ်ခုသည် အညွှန်းများ၊ စကေးဘားများ၊ အစရှိသည်တို့ကို raster အဖြစ် တွန်းအားပေးပြောင်းလဲခြင်း လုပ်ဆောင်မည်မဟုတ်ပါ။ သို့သော် အောက်ပါတို့ကို လုပ်ဆောင်နိုင်ပါသည်-

* |checkbox| :guilabel:`Print as raster` box ကို အမှန်ခြစ်ခြစ်ပြီး item များအားလုံးကို raster အဖြစ်ပြောင်းလဲရန် တွန်းအားပေးလုပ်ဆောင်ခြင်း။
* သို့မဟုတ် ဆန့်ကျင်ဘက်ရွေးချယ်စရာကို အသုံးပြုခြင်း၊ ဆိုလိုသည်မှာ :guilabel:`Always export as vectors` (Vector များအနေဖြင့် အမြဲတမ်း export ထုတ်ယူခြင်း)၊ ကိုက်ညီမှုရှိသော format တစ်ခုသို့ export ထုတ်ယူသောအခါ item များအားလုံးကို vector များအနေဖြင့် export ထုတ်ယူရန် တွန်းအားပေးခြင်းဖြစ်သည်။ အချို့ကိစ္စများတွင် ထွက်လာသောရလာဒ်သည် layout တွင်မြင်ရသည်နှင့် ကွဲပြားမှုများ ဖြစ်စေနိုင်ပါသည်။  

:file:`.TIF` ၊ :file:`.PDF` ဖြစ်လျှင် print layout တစ်ခုကို export ထုတ်ယူခြင်းသည် default အနေဖြင့် georeference ဖြစ်သော file တစ်ခုထဲတွင်ရလာဒ် ထုတ်ပေးမည်ဖြစ်သည် (:guilabel:`General settings` အုပ်စုထဲရှိ :guilabel:`Reference map` item ပေါ်တွင် မူတည်ပါသည်)။ အခြား format များအတွက်မူ georeference ဖြစ်သော ရလာဒ်ကိုရရှိရန် |checkbox| :guilabel:`Save world file` ကိုအမှန်ခြစ်ခြစ်ပြီး world file တစ်ခုကို ဖန်တီးပေးရန်လိုအပ်ပါသည်။ Export ထုတ်ယူထားသော မြေပုံ(များ)၏ ဘေးတွင် world file ကိုဖန်တီးမည်ဖြစ်ပြီး ၎င်းတွင် ကိုးကားမြေပုံ item ပါဝင်သည့် ရလာဒ်စာမျက်နှာ၏အမည်ပါရှိကာ အလွယ်တကူ georeference ပြုလုပ်နိုင်ရန် အချက်အလက်များ ပါဝင်ပါသည်။

Resize layout to content (Layout ကို ပါဝင်အကြောင်းအရာအတိုင်း အရွယ်အစားပြင်ဆင်ခြင်း)
....................................................................................

ဤအုပ်စုထဲရှိ :guilabel:`Resize page` tool ကိုအသုံးပြုပြီး print layout ၏လက်ရှိအကြောင်းအရာများကို လွမ်းခြုံသော extent (နယ်ပယ်အကျယ်အဝန်း) ရှိသည့် unique ဖြစ်သောစာမျက်နှာတစ်ခုကို ဖန်တီးနိုင်ပါသည် (ဖြတ်တောက်ထားသော အတိုင်းအတာတဝိုက် ရွေးချယ်နိုင်သော :guilabel:`margins` အချို့ဖြင့်)

ဤအရာသည် :ref:`crop to content <crop_to_content>` (ပါဝင်အကြောင်းအရာအတိုင်း ဖြတ်တောက်ခြင်း) option နှင့်ကွဲပြားပါသည်။ :ref:`Crop to content <crop_to_content>` option တွင် ရှိနေပြီးသား စာမျက်နှာများအားလုံးအစားထိုးပြီး စစ်မှန်ပြီး unique ဖြစ်သော စာမျက်နှာတစ်ခုပေါ်တွင် item များအားလုံးကို နေရာချထားမည်ဖြစ်သည်။

Variables (ကိန်းရှင်များ)
..........................

:guilabel:`Variables` တွင် layout အဆင့် (Global နှင့် project ၏ variable များအားလုံးပါဝင်သော) တွင် အသုံးပြုနိုင်သော variable များအားလုံးကို စာရင်းပြုစုပေးထားပါသည်။

Layout အဆင့် variable များကို စီမံခန့်ခွဲနိုင်မည်ဖြစ်ပါသည်။ စိတ်ကြိုက် layout အဆင့် variable တစ်ခုကို ပေါင်းထည့်ရန် |symbologyAdd| ခလုတ်ကို နှိပ်ပါ။ အလားတူပင် စာရင်းမှ စိတ်ကြိုက် layout အဆင့် variable တစ်ခုကိုရွေးချယ်ပြီး |symbologyRemove| ခလုတ်ကိုနှိပ်ကာ ၎င်းကို ဖယ်ရှားနိုင်ပါသည်။

Variable များအသုံးချမှုကို ပိုမိုသိရှိလိုပါက :ref:`General Tools <general_tools_variables>` ကဏ္ဍတွင် ကြည့်ရှုပါ။

.. _figure_composition_variables:

.. figure:: img/composition_variables.png
   :align: center

   Print layout ထဲရှိ Variables Editor

.. index:: Layout pages, Page properties
.. _page_properties:

Working with the page properties (စာမျက်နှာဆိုင်ရာဂုဏ်သတ္တိများနှင့် အလုပ်လုပ်ခြင်း)
-------------------------------------------------------------------------------------

Layout တစ်ခုကို စာမျက်နှာများစွာဖြင့် ဖွဲ့စည်းနိုင်ပါသည်။ ဥပမာအားဖြင့် ပထမစာမျက်နှာသည် မြေပုံ canvas တစ်ခုကို ပြသနိုင်ပြီး ဒုတိယစာမျက်နှာသည် layer တစ်ခုနှင့်ဆက်စပ်သော attribute ဇယားကို ပြသနိုင်ပါသည်။ တတိယစာမျက်နှာသည် မိမိအဖွဲ့အစည်း၏ website နှင့် link လုပ်ထားသော HTML frame တစ်ခုကို ပြသနိုင်ပါသည်။ သို့မဟုတ် စာမျက်နှာတစ်ခုစီတွင် item အမျိုးအစားများစွာကို ပေါင်းထည့်နိုင်ပါသည်။


Adding a new page (စာမျက်နှာအသစ်တစ်ခုပေါင်းထည့်ခြင်း)
......................................................

ထို့အပြင် စာမျက်နှာများ၏ အရွယ်အစားအမျိုးမျိုး နှင့်/သို့မဟုတ် ဦးတည်ရာအမျိုးမျိုး အသုံးပြုပြီး layout တစ်ခုကို ပြုလုပ်နိုင်ပါသည်။ စာမျက်နှာတစ်ခုကို ပေါင်းထည့်ရန် :menuselection:`Layout` menu သို့မဟုတ် :guilabel:`Layout Toolbar` မှ |newPage| :guilabel:`Add Pages...` tool ကိုရွေးချယ်ပါ။ :guilabel:`Insert Pages` dialog ပွင့်လာမည်ဖြစ်ပြီး အောက်ပါတို့ကို ဖြည့်သွင်းရန် မေးမြန်းပါလိမ့်မည်-

* ထည့်သွင်းမည့် စာမျက်နှာအရေအတွက်၊
* စာမျက်နှာ(များ)၏ ထားရှိမည့်နေရာ - ပေးထားသောစာမျက်နှာတစ်ခု မတိုင်မီ သို့မဟုတ် နောက်၊ သို့မဟုတ် print layout ၏ အဆုံး၌
* :guilabel:`Page size` (စာမျက်နှာအရွယ်အစား) - သက်ဆိုင်ရာ :guilabel:`Orientation` (ဦးတည်ရာ) (Portrait သို့မဟုတ် Landscape) ဖြင့် ကြိုတင်သတ်မှတ်ပေးထားသော format စာမျက်နှာတစ်ခုထဲမှ ဖြစ်နိုင်ပြီး (``A4`` ၊ ``B0`` ၊ ``Legal`` ၊ ``Letter`` ၊ ``ANSI A`` ၊ ``Arch A`` နှင့် ၎င်းတို့၏ ဆင့်ပွားများအပြင် ``1920x1080`` သို့မဟုတ် ``1024x768`` ကဲ့သို့သော resolution အမျိုးအစားတစ်ခု)

  စာမျက်နှာအရွယ်အစားသည် ``custom`` (စိတ်ကြိုက်) format တစ်ခုလည်းဖြစ်နိုင်ပါသည်၊ ထိုသို့လုပ်ဆောင်ရန် ၎င်း၏ :guilabel:`Width`(အကျယ်) နှင့် :guilabel:`Height` (အမြင့်) ကို ထည့်သွင်းပေးရန်လိုအပ်မည်ဖြစ်ပြီး (လိုအပ်လျှင် အရွယ်အစားအချိုးကို lock ပြုလုပ်ခြင်းဖြင့်) ``mm`` ၊ ``cm`` ၊ ``px`` ၊ ``pt`` ၊ ``in`` ၊ ``ft`` အစရှိသည့် အသုံးပြုမည့်ယူနစ်ကို ရွေးချယ်ပေးရပါမည်။ ယူနစ်တစ်ခုမှ အခြားတစ်ခုသို့ ကူးပြောင်းသောအခါ ထည့်သွင်းထားသော တန်ဖိုးများကို အလိုအလျောက် ပြောင်းလဲပေးမည်ဖြစ်ပါသည်။


.. _figure_layout_new_page:

.. figure:: img/insert_page.png
   :align: center

   Print layout ထဲတွင် စာမျက်နှာအသစ်တစ်ခုဖန်တီးခြင်း

Updating page properties (စာမျက်နှာဆိုင်ရာဂုဏ်သတ္တိများကို နောက်ဆုံးအခြေအနေ၌ထားရှိခြင်း)
.........................................................................................

မည်သည့် စာမျက်နှာကိုမဆို Page :guilabel:`Item Properties` panel မှတဆင့် နောက်ပိုင်းမှ ပြင်ဆင်သတ်မှတ်ခြင်းများ လုပ်ဆောင်နိုင်ပါသည်။ စာမျက်နှာတစ်ခု၏ property သို့ရောက်ရှိရန် စာမျက်နှာ၏ လွတ်နေသောအပိုင်းတွင် left-click နှိပ်ပါ သို့မဟုတ် စာမျက်နှာတစ်ခုပေါ်တွင် right-click နှိပ်ပြီး :guilabel:`Page Properties...` ကိုရွေးချယ်ပါ။ အောက်ဖော်ပြပါ setting များဖြင့် :guilabel:`Item Properties` panel ပွင့်လာမည်ဖြစ်သည်-

* အထက်တွင်ဖော်ပြထားခဲ့သော :guilabel:`Page size` frame ။ Data ဖြင့်သတ်မှတ်သော အစားထိုးပြင်ဆင်ခြင်း option များ (:ref:`atlas_data_defined_override` တွင်ကြည့်ရှုပါ) အသုံးပြုပြီး property တစ်ခုချင်းစီကို မွမ်းမံပြင်ဆင်နိုင်ပါသည်၊
* |unchecked| :guilabel:`Exclude page from exports` သည် လက်ရှိစာမျက်နှာကို :ref:`layout output
  <create-output>` ထဲတွင် ထည့်သွင်း/မသွင်းကို ဆုံးဖြတ်ပေးပါသည်။  
* အသုံးပြုလိုသော :ref:`အရောင် <color-selector>` သို့မဟုတ် :ref:`သင်္ကေတ <symbol-selector>` ကိုအသုံးပြုပြီး လက်ရှိစာမျက်နှာ၏ :guilabel:`Background` (နောက်ခံ)။  

.. _figure_layout_page:

.. figure:: img/page_properties.png
   :align: center

   စာမျက်နှာဆိုင်ရာဂုဏ်သတ္တိများ dialog

.. index:: Guides, Smart guides
.. _layout_guides_panel:

The Guides Panel (Guide များဆိုင်ရာ Panel)
-------------------------------------------

Guide များသည် layout စာမျက်နှာပေါ်တွင် ထားရှိနိုင်သော ဒေါင်လိုက် သို့မဟုတ် ရေပြင်ညီမျဉ်း အကိုးအကားများဖြစ်ပြီး item များကိုဖန်တီးခြင်း၊ ရွှေ့ခြင်း သို့မဟုတ် အရွယ်အစားပြင်ဆင်ခြင်းများလုပ်ဆောင်သောအခါ ၎င်း item များကို နေရာချထားရာတွင် အထောက်အကူပေးပါသည်။ Guide များကို အသုံးပြုနိုင်စေရန် :menuselection:`View --> Show Guides` နှင့် :menuselection:`View --> Snap to Guides` option များကို အမှန်ခြစ်ခြစ်ထားရန် လိုအပ်ပါသည်။ Guide တစ်ခုကို ဖန်တီးရန် မတူညီသော နည်းလမ်း ၂ မျိုးရှိပါသည်-

* :menuselection:`View --> Show Rulers` option ကိုသတ်မှတ်ထားလျှင် ruler (ပေတံ) တစ်ခုကို ဖိဆွဲပြီး စာမျက်နှာဧရိယာအတွင်း အလိုရှိသောနေရာတွင် မောက်စ်ခလုတ်ကို လွှတ်လိုက်ပါ။  
* ပိုမိုတိကျလိုလျှင် :menuselection:`View --> Toolbox -->` မှ :guilabel:`Guides` panel ကိုအသုံးပြုပါ သို့မဟုတ် စာမျက်နှာ၏ contextual menu မှ :guilabel:`Manage guides for page...` ကိုရွေးချယ်ပါ။

.. _figure_layout_guides_panel:

.. figure:: img/guides_panel.png
   :align: center

   Guide များ panel

:guilabel:`Guides` panel တွင် သီးသန့်နေရာများ၌ ဆွဲကပ်မျဉ်းများကို ဖန်တီးနိုင်ပါသည်-

#. Guide များပေါင်းထည့်လိုသော :guilabel:`Page` ကိုရွေးချယ်ပါ
#. |symbologyAdd| :sup:`Add new guide` ခလုတ်ကိုနှိပ်ပြီး ရေပြင်ညီ သို့မဟုတ် ဒေါင်လိုက်မျဉ်း၏ ကိုဩဒိနိတ်များကို ထည့်သွင်းပါ။ မူလအစ သည် ဘယ်ဘက်အပေါ်ထောင့်၌ ဖြစ်ပါသည်။ ယူနစ်အမျိုးမျိုးကို အသုံးပြုနိုင်ပါသည်။

   Panel တွင် ကိုဩဒိနိတ်များကို ဆွဲထုတ်ရန် ရှိနေပြီးသား guide များ၏တည်နေရာကို ချိန်ညှိပေးနိုင်ပါသည်- click နှစ်ချက်နှိပ်၍ တန်ဖိုးကို အစားထိုးပါ။
#. :guilabel:`Guides` panel သည် လက်ရှိစာမျက်နှာအတွက် item များကိုသာ စာရင်းလုပ်ပေးပါသည်။ လက်ရှိစာမျက်နှာထဲတွင်သာ guide များကို ဖန်တီးခြင်း သို့မဟုတ် ဖယ်ရှားခြင်း လုပ်ဆောင်နိုင်ပေးပါသည်။ သို့သော် လက်ရှိစာမျက်နှာ၏ guide ပြင်ဆင်သတ်မှတ်ထားမှုကို layout ထဲရှိ အခြားစာမျက်နှာများတွင် ပုံတူပွားရန်အတွက် :guilabel:`Apply to All Pages` ခလုတ်ကို အသုံးပြုနိုင်ပါသည်။  
#. Guide တစ်ခုကို ဖျက်ရန်အတွက် ၎င်းကို ရွေးချယ်ပြီး |symbologyRemove| :sup:`Remove selected guide` ခလုတ်ကိုနှိပ်ပါ။ လက်ရှိစာမျက်နှာထဲရှိ guide များအားလုံးကို ဖယ်ရှားရန် :guilabel:`Clear All Guides` ကိုအသုံးပြုပါ။   

.. tip:: **ရှိနေပြီးသား layout item များသို့ ဆွဲကပ်ခြင်း**

  Guide များနှင့် grid များအပြင် item များကို ရွှေ့ခြင်း၊ အရွယ်အစားပြင်ဆင်ခြင်း သို့မဟုတ် အသစ်ဖန်တီးခြင်းများလုပ်ဆောင်သောအခါ ရှိနေပြီးသား item များကို snapping reference (ဆွဲကပ်အကိုးအကား) အဖြစ်အသုံးပြုနိုင်ပါသည်- ၎င်းတို့ကို **smart guides** ဟုခေါ်ဆိုပြီး ထိုသို့လုပ်ဆောင်ရန် :menuselection:`View --> Smart Guides` option ကိုအမှန်ခြစ်ခြစ်ထားရန် လိုအပ်ပါသည်။ မောက်စ်၏မြှား သည် item တစ်ခု၏နယ်နိမိတ်နှင့် နီးကပ်လာသည့်အချိန်တိုင်း snapping cross (ဆွဲကပ်ခြင်း ကြက်ခြေခတ်) တစ်ခုပေါ်လာမည်ဖြစ်သည်။

.. _layout_items_panel:

The Items Panel (Item များ Panel)
----------------------------------

:guilabel:`Items` panel တွင် item များရွေးချယ်ခြင်းနှင့် item များ၏မြင်ရနိုင်မှုကို စီမံခန့်ခွဲရန် option အချို့ ပါရှိပါသည်။ Print layout canvas ထဲသို့ ပေါင်းထည့်ထားသော item များအားလုံး (:ref:`item များအုပ်စု <group_items>` များအပါအဝင်) ကို စာရင်းတစ်ခုထဲတွင် ပြသမည်ဖြစ်ပြီး item တစ်ခုကို ရွေးချယ်လိုက်ခြင်းသည် စာရင်းထဲရှိ သက်ဆိုင်ရာ row ကို ရွေးချယ်ပေးမည်ဖြစ်သကဲ့သို့ row တစ်ခုကို ရွေးချယ်လိုက်ပါက သက်ဆိုင်ရာ item ကို print layout canvas ထဲတွင် ရွေးချယ်ပေးမည်ဖြစ်သည်။ ထို့ကြောင့် ဤနည်းလမ်းသည် အခြား item တစ်ခု၏နောက်ကွယ်တွင်ရှိနေသော item တစ်ခုကို ရွေးချယ်ရာတွင် အဆင်ပြေစေပါသည်။ ရွေးချယ်ခံထားရသော row တစ်ခုကို bold (စာလုံးအထင်း) ဖြင့် ပြသပေးပါသည်။ 

ရွေးချယ်ထားသော မည်သည့် item အတွက်မဆို အောက်ပါတို့ကို လုပ်ဆောင်နိုင်ပါသည်-

* |showAllLayers| Item ကို မြင်ရအောင် ပြုလုပ်ခြင်း သို့မဟုတ် ဖျောက်ထားခြင်း၊
* |locked| Item ၏ နေရာကို lock လုပ်ထားခြင်း သို့မဟုတ် unlock မလုပ်ထားခြင်း၊
* Item ၏ Z တည်နေရာကို စဉ်ခြင်း။ Click နှိပ်ပြီး ဖိဆွဲကာ စာရင်းထဲရှိ item တစ်ခုချင်းစီကို အထက်အောက် ရွှေ့နိုင်ပါသည်။ စာရင်းထဲရှိ အပေါ်ဆုံး item ကို print layout canvas ထဲတွင် အရှေ့ဆုံးသို့ ပို့ဆောင်ပေးမည်ဖြစ်သည်။
* စာသားကို click နှစ်ချက်နှိပ်ခြင်းဖြင့် item ID ကိုပြောင်းလဲခြင်း။
* Item တစ်ခုပေါ်တွင် right-click နှိပ်ပြီး ၎င်းကို ကူးယူခြင်း သို့မဟုတ် ဖျက်ပစ်ခြင်း သို့မဟုတ် ၎င်း၏ :ref:`properties panel <layout_item_options>` ကို ဖွင့်ခြင်း။

Item တစ်ခုအတွက် မှန်ကန်သောနေရာကို ရှာတွေ့သည်နှင့် |locked| column ထဲရှိ box ကို အမှန်ခြစ်ခြစ်ကာ lock လုပ်ထားနိုင်ပါသည်။ Lock လုပ်ထားသော item များကို canvas ပေါ်တွင် ရွေးချယ်၍မရပါ။ Lock လုပ်ထားသော item များကို unlock ပြုလုပ်ရန် :menuselection:`Items` panel ထဲတွင် item ကို ရွေးချယ်ပြီး box တွင် အမှန်ခြစ်ဖြုတ်ပါ သို့မဟုတ် toolbar ပေါ်ရှိ icon များကို အသုံးပြုနိုင်ပါသည်။

.. index:: Revert layout actions
.. _layout_undo_panel:

The Undo History Panel: Revert and Restore actions (လုပ်ဆောင်မှုကိုပယ်ဖျက်ခြင်း မှတ်တမ်း Panel- လုပ်ဆောင်ချက်များကို နောက်ပြန်ဆုတ်ခြင်းနှင့် မူလအနေအထားသို့ပြန်ရောက်စေခြင်း)
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Layout လုပ်ငန်းစဉ်အတွင်း လုပ်ဆောင်ထားသောပြောင်းလဲမှုများကို နောက်ပြန်ဆုတ်ခြင်း (revert) နှင့် မူလအနေအထားသို့ပြန်ရောက်စေခြင်း (restore) များ လုပ်ဆောင်နိုင်ပါသည်။ ၎င်းကို :guilabel:`Edit` menu ၊ :guilabel:`Layout` toolbar သို့မဟုတ် print layout ဧရိယာထဲတွင် right-click နှိပ်တိုင်း ပေါ်လာသော contextual menu ထဲတွင်ရရှိနိုင်သော revert နှင့် restore tool များဖြင့် လုပ်ဆောင်နိုင်ပါသည်-

* |undo| :sup:`Revert last change` (နောက်ဆုံးပြောင်းလဲမှုကို နောက်ပြန်ဆုတ်ခြင်း)
* |redo| :sup:`Restore last change` (နောက်ဆုံးပြောင်းလဲမှုကို မူလအနေအထားသို့ပြန်ရောက်စေခြင်း)

၎င်းကို :guilabel:`Undo history` panel အတွင်း မောက်စ် click နှိပ်ပြီးလည်း လုပ်ဆောင်နိုင်ပါသည် (:numref:`figure_layout` တွင်ကြည့်ရှုပါ)။ History (မှတ်တမ်း) panel တွင် print layout အတွင်း ပြုလုပ်ခဲ့ပြီးသော နောက်ဆုံးလုပ်ဆောင်ချက်များ စာရင်းရှိပါသည်။ နောက်ပြန်ဆုတ်လိုသော လုပ်ဆောင်ချက်အမှတ်နေရာကိုသာ ရွေးချယ်လိုက်ပါ။ လုပ်ဆောင်ချက်အသစ်ကို ပြုလုပ်လိုက်သည်နှင့် ရွေးချယ်ထားသောလုပ်ဆောင်ချက်နောက်ပိုင်း လုပ်ဆောင်ချက်များအားလုံးကို ဖယ်ရှားပစ်မည်ဖြစ်သည်။


.. _figure_layout:

.. figure:: img/command_hist.png
   :align: center

   Print Layout ထဲရှိ Undo History

.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |add3DMap| image:: /static/common/mActionAdd3DMap.png
   :width: 1.5em
.. |addArrow| image:: /static/common/mActionAddArrow.png
   :width: 1.5em
.. |addBasicCircle| image:: /static/common/mActionAddBasicCircle.png
   :width: 1.5em
.. |addBasicRectangle| image:: /static/common/mActionAddBasicRectangle.png
   :width: 1.5em
.. |addBasicShape| image:: /static/common/mActionAddBasicShape.png
   :width: 1.5em
.. |addBasicTriangle| image:: /static/common/mActionAddBasicTriangle.png
   :width: 1.5em
.. |addHtml| image:: /static/common/mActionAddHtml.png
   :width: 1.5em
.. |addImage| image:: /static/common/mActionAddImage.png
   :width: 1.5em
.. |addLegend| image:: /static/common/mActionAddLegend.png
   :width: 1.5em
.. |addManualTable| image:: /static/common/mActionAddManualTable.png
   :width: 1.5em
.. |addMap| image:: /static/common/mActionAddMap.png
   :width: 1.5em
.. |addMarker| image:: /static/common/mActionAddMarker.png
   :width: 1.5em
.. |addNodesShape| image:: /static/common/mActionAddNodesShape.png
   :width: 1.5em
.. |addPolygon| image:: /static/common/mActionAddPolygon.png
   :width: 1.5em
.. |addPolyline| image:: /static/common/mActionAddPolyline.png
   :width: 1.5em
.. |addTable| image:: /static/common/mActionAddTable.png
   :width: 1.5em
.. |atlas| image:: /static/common/mIconAtlas.png
   :width: 1.5em
.. |atlasFirst| image:: /static/common/mActionAtlasFirst.png
   :width: 1.5em
.. |atlasLast| image:: /static/common/mActionAtlasLast.png
   :width: 1.5em
.. |atlasNext| image:: /static/common/mActionAtlasNext.png
   :width: 1.5em
.. |atlasPrev| image:: /static/common/mActionAtlasPrev.png
   :width: 1.5em
.. |atlasSettings| image:: /static/common/mActionAtlasSettings.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |degrees| unicode:: 0x00B0
   :ltrim:
.. |deleteSelected| image:: /static/common/mActionDeleteSelected.png
   :width: 1.5em
.. |deselectAll| image:: /static/common/mActionDeselectAll.png
   :width: 1.5em
.. |duplicateLayout| image:: /static/common/mActionDuplicateLayout.png
   :width: 1.5em
.. |editCopy| image:: /static/common/mActionEditCopy.png
   :width: 1.5em
.. |editCut| image:: /static/common/mActionEditCut.png
   :width: 1.5em
.. |editNodesShape| image:: /static/common/mActionEditNodesShape.png
   :width: 1.5em
.. |editPaste| image:: /static/common/mActionEditPaste.png
   :width: 1.5em
.. |elevationProfile| image:: /static/common/mActionElevationProfile.png
   :width: 1.5em
.. |fileOpen| image:: /static/common/mActionFileOpen.png
   :width: 1.5em
.. |filePrint| image:: /static/common/mActionFilePrint.png
   :width: 1.5em
.. |fileSave| image:: /static/common/mActionFileSave.png
   :width: 1.5em
.. |fileSaveAs| image:: /static/common/mActionFileSaveAs.png
   :width: 1.5em
.. |groupItems| image:: /static/common/mActionGroupItems.png
   :width: 1.5em
.. |invertSelection| image:: /static/common/mActionInvertSelection.png
   :width: 1.5em
.. |label| image:: /static/common/mActionLabel.png
   :width: 1.5em
.. |layoutManager| image:: /static/common/mActionLayoutManager.png
   :width: 1.5em
.. |locked| image:: /static/common/locked.png
   :width: 1.5em
.. |lowerItems| image:: /static/common/mActionLowerItems.png
   :width: 1.5em
.. |moveItemContent| image:: /static/common/mActionMoveItemContent.png
   :width: 1.5em
.. |moveItemsToBottom| image:: /static/common/mActionMoveItemsToBottom.png
   :width: 1.5em
.. |moveItemsToTop| image:: /static/common/mActionMoveItemsToTop.png
   :width: 1.5em
.. |newLayout| image:: /static/common/mActionNewLayout.png
   :width: 1.5em
.. |newPage| image:: /static/common/mActionNewPage.png
   :width: 1.5em
.. |northArrow| image:: /static/common/north_arrow.png
   :width: 1.5em
.. |pan| image:: /static/common/mActionPan.png
   :width: 1.5em
.. |raiseItems| image:: /static/common/mActionRaiseItems.png
   :width: 1.5em
.. |redo| image:: /static/common/mActionRedo.png
   :width: 1.5em
.. |refresh| image:: /static/common/mActionRefresh.png
   :width: 1.5em
.. |saveAsPDF| image:: /static/common/mActionSaveAsPDF.png
   :width: 1.5em
.. |saveAsSVG| image:: /static/common/mActionSaveAsSVG.png
   :width: 1.5em
.. |saveMapAsImage| image:: /static/common/mActionSaveMapAsImage.png
   :width: 1.5em
.. |scaleBar| image:: /static/common/mActionScaleBar.png
   :width: 1.5em
.. |select| image:: /static/common/mActionSelect.png
   :width: 1.5em
.. |selectAll| image:: /static/common/mActionSelectAll.png
   :width: 1.5em
.. |showAllLayers| image:: /static/common/mActionShowAllLayers.png
   :width: 1.5em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
.. |symbologyRemove| image:: /static/common/symbologyRemove.png
   :width: 1.5em
.. |unchecked| image:: /static/common/unchecked.png
   :width: 1.3em
.. |undo| image:: /static/common/mActionUndo.png
   :width: 1.5em
.. |ungroupItems| image:: /static/common/mActionUngroupItems.png
   :width: 1.5em
.. |unlocked| image:: /static/common/unlocked.png
   :width: 1.5em
.. |vectorGrid| image:: /static/common/vector_grid.png
   :width: 1.5em
.. |zoomActual| image:: /static/common/mActionZoomActual.png
   :width: 1.5em
.. |zoomFullExtent| image:: /static/common/mActionZoomFullExtent.png
   :width: 1.5em
.. |zoomIn| image:: /static/common/mActionZoomIn.png
   :width: 1.5em
.. |zoomOut| image:: /static/common/mActionZoomOut.png
   :width: 1.5em
.. |zoomToArea| image:: /static/common/mActionZoomToArea.png
   :width: 1.5em
