﻿**************************************************************
QGIS Configuration (QGIS ပြင်ဆင်သတ်မှတ်ခြင်း/အခင်းအကျင်း)
**************************************************************


.. only:: html


   .. contents::
      :local:
      :depth: 2

QGIS ကို သတ်မှတ်ချက်များစွာဖြင့် ပြင်ဆင်သတ်မှတ်နိုင်ပါသည်။ :menuselection:`Settings` menu တွင် အောက်ပါတို့ကို ဆောင်ရွက်ရန် ကိရိယာအမျိုးမျိုးကို ပံ့ပိုးပေးထားပါသည်-

* |styleManager| :guilabel:`Style Manager...` (Style စီမံခန့်ခွဲသည့်အရာ) သည်  :ref:`သင်္ကေတများ ၊ style များနှင့် ရောင်စဉ်တန်းများ <vector_style_manager>` ကို ဖန်တီးခြင်းနှင့် စီမံခန့်ခွဲခြင်းများ ဆောင်ရွက်နိုင်သည်။
* |customProjection| :guilabel:`Custom Projections...` (စိတ်ကြိုက်အရိပ်ချစနစ်ဖန်တီးခြင်း) သည် မိမိကိုယ်ပိုင် :ref:`coordinate reference systems (ရည်ညွှန်းကိုဩဒိနိတ်စနစ်များ) <sec_custom_projections>` ကို ဖန်တီးနိုင်သည်။
* |keyboardShortcuts| :guilabel:`Keyboard Shortcuts...` (ကီးဘုတ်ဖြတ်လမ်းနည်းများ) သည် ကိုယ်ပိုင် :ref:`keyboard shortcuts <shortcuts>` များကို ဖန်တီးနိုင်ပါသည်။ QGIS အပိုင်းတစ်ခုစီတွင် ၎င်း shortcuts များကို :ref:`project properties <project_properties>` မှ အစားထိုးပြင်ဆင်နိုင်သည်။ (:menuselection:`Project` menu အောက်တွင် ‌ဆောင်ရွက်နိုင်ပါသည်။)
* |interfaceCustomization| :guilabel:`Interface Customization...` (မျက်နှာပြင်အပြင်အဆင်) သည် မိမိ အလိုမရှိသော dialog များ သို့မဟုတ် ကိရိယာများကို ဖျောက်ထားနိုင်ပြီး  :ref:`application interface (အက်ပလီ‌ကေးရှင်းမျက်နှာပြင်) <sec_customization>` ကို ပြင်ဆင်သတ်မှတ်နိုင်သည်။
* |options| :guilabel:`Options...` သည် ဆော့ဝဲလ်များ၏ မတူညီသော နေရာအမျိုးမျိုးတွင် အသုံးချနိုင်ရန် :ref:`options (ရွေးချယ်စရာများ) <gui_options>` များကို သတ်မှတ်နိုင်သည်။ ဤ ဦးစားပေးရွေးချယ်မှုများကို အသုံးပြုနေသော :ref:`User profile (အသုံးပြုသူပရိုဖိုင်) <user_profiles>` setting များတွင် သိမ်းဆည်းထားမည်ဖြစ်ပြီး ၎င်း profile ဖြင့် project အသစ်ဖွင့်လိုက်သောအခါတိုင်းတွင် ထိုရွေးချယ်မှုများကို ပုံသေအသုံးပြုသွားမည် ဖြစ်သည်။ 


.. index:: Options, Configuration
.. _gui_options:

Options (ရွေးချယ်စရာများ)
==========================

QGIS အတွက် အချို့အခြေခံရွေးချယ်စရာများကို :guilabel:`Options` dialog ကို အသုံးပြု၍ ရွေးချယ်နိုင်သည်။ :menuselection:`Settings -->` |options| :menuselection:`Options` ကို ရွေးချယ်ပါ။ မိမိလိုအပ်ချက်ပေါ်မူတည်၍ ရွေးချယ်စရာများကို မွမ်းမံပြင်ဆင်နိုင်ပြီး အချို့သော ပြောင်းလဲမှုများသည် စတင်အသုံးမပြုခင် QGIS ကို ပြန်လည်စတင်ခြင်း (Restart) ပြုလုပ်ရန် လိုအပ်ပါသည်။

ရွေးချယ်စရာများကို စိတ်ကြိုက်ပြင်ဆင်သတ်မှတ်နိုင်သည့် tab များကို အောက်တွင်ဖော်ပြထားပါသည်။

.. note:: **Plugin များသည် Options dialog များအတွင်း ၎င်းတို့၏ setting များကို ထည့်သွင်းထားနိုင်ပါသည်။**

 အောက်တွင် အဓိက setting များကိုသာ ဖော်ပြထားပြီး  ၎င်းတို့၏ကိုယ်ပိုင်ရွေးချယ်စရာများကို စံရွေးချယ်စရာ dialog အဖြစ် လုပ်ဆောင်သော :ref:`installed plugins (ထည့်သွင်းထားသည့်  plugin များ) <plugins>` များဖြင့် ထို setting စာရင်းကို ထပ်မံတိုးချဲ့နိုင်သည်။ ထိုသို့ပြုလုပ်ခြင်းဖြင့် plugin တစ်ခုစီတွင် ၎င်းတို့အတွက်သာဖြစ်သော အပို menu item များဖြင့် ကိုယ်ပိုင်အပြင်အဆင် dialog (config dialog) ရှိခြင်းကို ရှောင်ရှားနိုင်သည်။


 .. Todo: Would be nice to link in the future to a place in the PyQGIS Cookbook
   showing the code to use to implement plugin options in standard dialog


.. _general_options:


General Settings (အထွေထွေ setting များ)
----------------------------------------


.. _figure_general_settings:


.. figure:: img/options_general.png
   :align: center

   အထွေထွေ setting များ

.. index:: Overwrite language
.. _locale_options:


**Override System Locale (စက်၏မူရင်းအပြင်အဆင်ကို အစားထိုးပြင်ဆင်ခြင်း)**

ပုံမှန်အားဖြင့် QGIS သည် ဘာသာစကားသတ်မှတ်ရန်နှင့် ကိန်းဂဏန်းတန်ဖိုးများ ကိုင်တွယ်လုပ်ဆောင်ရန်မှာ မိမိ အသုံးပြုသော ကွန်ပျူတာစနစ်၏ အပြင်အဆင်ပေါ်တွင် မူတည်နေပါသည်။ ဤအုပ်စုကို ဖွင့်လိုက်ခြင်းဖြင့် လုပ်ဆောင်မှုများကို စိတ်ကြိုက်ပြင်ဆင်နိုင်ပါသည်။

* အသုံးပြုသူဘက်မှ မြင်ရမည့် မျက်နှာပြင်ပုံစံ (GUI) တွင် အသုံးပြုရန်အတွက် :guilabel:`User interface translation` မှ ဘာသာစကားကို ရွေးချယ်ပါ။
* မည်သည့် ရက်စွဲနှင့် ကိန်းဂဏန်းတန်ဖိုးများကို ထည့်သွင်းပြီး ပုံဖော်ပြသမည်ကို :guilabel:`Locale (number, date and currency formats)` (ကိန်းဂဏန်း၊ ရက်စွဲ နှင့် ငွေကြေးပုံစံများ) ထဲတွင် စနစ်ကိုရွေးချယ်ပါ။
* |checkbox| :guilabel:`Show group (thousand) separator` (အုပ်စု (ထောင်ပြည့်ကိန်း)ခွဲခြားပေးသည့်အရာကို ပြသပါ)

ရွေးချယ်ထားသော setting များနှင့် ၎င်းတို့ကို မည်သို့အဓိပ္ပါယ်ကောက်ယူရမည်ဆိုသည့် အကျဉ်းချုပ် ကို ဘောင်၏အောက်ခြေတွင် ဖော်ပြထားပါသည်။


**Application (အသုံးချမှု)**

* Dialogs ထဲတွင် widget များ ပုံသဏ္ဍာန်နှင့် နေရာချထားမှုများအတွက် :guilabel:`Style (QGIS ကို ပြန်လည်စတင်ရန်လိုအပ်ပါသည်)` ကို ရွေးချယ်ပါ။ ဖြစ်နိုင်သောတန်ဖိုးများသည် မိမိ၏ ကွန်ပျူတာစနစ်ပေါ်တွင် မူတည်ပါသည်။ 
* :guilabel:`UI theme (QGIS ကို ပြန်လည်စတင်ရန်လိုအပ်ပါသည်)` |selectString| တွင် theme(ပုံစံ) ကို ရွေးချယ်သတ်မှတ်ပါ။ ၎င်းပုံစံသည် 'default' (ပုံမှန်) ၊ 'Night Mapping' (အလင်းမှိန်မြေပုံပုံစံ) သို့မဟုတ် 'Blend of Gray' (မီးခိုးရောင်ရောစပ်မှုပုံစံ) ဟူ၍ ရှိနေနိုင်ပါသည်။ 
* :guilabel:`Icon size` |selectString| တွင် Icon အရွယ်အစားကို ရွေးချယ်သတ်မှတ်ပါ။ 
* :guilabel:`Font` (စာလုံးပုံစံ) နှင့် ၎င်း၏ :guilabel:`Size` (အရွယ်အစား) ကို သတ်မှတ်ပါ။ Font သည် |radioButtonOn| :guilabel:`Qt default` (စက်တွင် ပုံသေထည့်သွင်းထားသည့်စာလုံးပုံစံ) သို့မဟုတ် အသုံးပြုသူမှ သတ်မှတ်ပေးသည့် font ဖြစ်နိုင်ပါသည်။ 
* :guilabel:`Timeout for timed messages or dialogs` (အချိန်ဖြင့်သတ်မှတ်ထားသောစာတို သို့မဟုတ် dialog များ အတွက် ကုန်ဆုံးချိန်)ကို ပြောင်းလဲပါ။ 
* |unchecked| :guilabel:`Hide splash screen at startup` (QGIS စတင်ချိန်ပေါ်လာသောမျက်နှာပြင်အား ဖျောက်ထားခြင်း) တွင် အမှန်ခြစ်ဖြုတ်ပါ။ 
* |checkbox| :guilabel:`Show QGIS news feed on welcome page` (ကြိုဆိုစာမျက်နှာတွင် QGIS သတင်းများကိုပြသခြင်း) ကို အမှန်ခြစ်ပြုလုပ်ခြင်းဖြင့် ကြိုဆိုသည့်စာမျက်နှာတွင် စနစ်တကျစီစဉ်ထားသည့် QGIS နှင့်ပတ်သက်သည့်သတင်းအချက်အလက်များကို မြင်သာစေရန် ဖော်ပြနေမည်ဖြစ်သည်။ (ထိုစာမျက်နှာတွင် အသုံးပြုသူ/ရေးဆွဲသူ (Developer) များ၏ အစည်းအဝေးပြုလုပ်မည့်ရက်များ၊ အနှစ်ချုပ်၊ လူထုစစ်တမ်းများ၊ ထုတ်ပြန်ကြေငြာချက်များ၊ အကြံပြုချက်များ စသည်တို့ပါဝင်ပါသည်။)
* |checkbox| :guilabel:`Check QGIS version at startup` (စတင်ချိန်တွင် QGIS version ကို စစ်ဆေးမည်) ကို အမှန်ခြစ်ပြုလုပ်ထားလျှင် QGIS version အသစ်ထွက်ပါက သတိပေးအကြောင်းကြားမည်ဖြစ်ပါသည်။ 
* |unchecked| :guilabel:`Use native color chooser dialogs` (မူရင်းအရောင်ရွေးချယ်သည့် dialogs ကိုအသုံးပြုမည်) ကို အမှန်ခြစ်ဖြုတ်ပါ။ (:ref:`color-selector` တွင် ကြည့်နိုင်ပါသည်။) 


.. _projectfiles_options:


**Project files (ပရောဂျက်ဖိုင်များ)**

* :guilabel:`Open project on launch` ကိုနှိပ်၍ QGIS စဖွင့်ချိန်တွင် ပရောဂျက်ကိုဖွင့်ပါ။

  * 'Welcome Page' (default) သည် သတင်းများ၊ project template (ပရောဂျက်နမူနာပုံစံ) များနှင့် :ref:`user profile (အသုံးပြုသူပရိုဖိုင်) <user_profiles>` ၏ မကြာသေးမီက အသုံးပြုခဲ့ပြီးသော project များကို (thumbnail များဖြင့်) ပြသပေးနိုင်ပါသည်။ ပုံမှန်အားဖြင့် မည်သည့် project ကိုမှ ဖွင့်ပေးမည်မဟုတ်ပါ။
  * 'New' (အသစ်) သည် default template ပေါ်မူတည်၍ project အသစ်ကို ဖွင့်ပေးပါသည်။
  * 'Most recent' သည် နောက်ဆုံးအသုံးပြုပြီးသိမ်းဆည်းထားခဲ့သော project ကို ပြန်လည်ဖွင့်ပေးပါသည်။ 
  * 'Specific' ဖြင့် သီးသန့် project တစ်ခုကို ဖွင့်နိုင်ပါသည်။ ပုံမှန်အားဖြင့် အသုံးပြုမည့် Project သတ်မှတ်ရန် :guilabel:`...` button ကို အသုံးပြုပါ။ 

* |checkbox| :guilabel:`Create new project from default project` (Default project မှ project အသစ်ကို ဖန်တီးပါ) ကို အမှန်ခြစ်ပြုလုပ်ပါ။ :guilabel:`Set current project as default` (လက်ရှိ project ကို default အနေဖြင့်သတ်မှတ်ပါ) သို့မဟုတ် :guilabel:`Reset default` (Default ကို ပြန်လည်သတ်မှတ်ပါ) ကို click နှိပ်နိုင်ပါသည်။ မိမိ၏ဖိုင်များအတွင်း ရှာဖွေ၍ အသုံးပြုသူသတ်မှတ်ထားသည့် project template များကို ရှာဖွေနိုင်မည့်လမ်းကြောင်းတစ်ခုကို သတ်မှတ်ပေးနိုင်ပါသည်။ ၎င်းကို :menuselection:`Project --> New From Template` တွင် ပေါင်းထည့်သွားမည်ဖြစ်ပါသည်။ |checkbox| :guilabel:`Create new project from default project` ကို ဦးစွာ အမှန်ခြစ်ခြစ်ထားလျှင် project templates folder ထဲတွင် project တစ်ခုကို သိမ်းဆည်းမည် ဖြစ်ပါသည်။ 
* |checkbox| :guilabel:`Prompt to save project and data source changes when required` (လိုအပ်ပါက ပရောဂျက်သိမ်းဆည်းခြင်းနှင့် ဒေတာအရင်းအမြစ်ပြောင်းလဲခြင်းတို့အတွက် သတိပေးချက်) ကို အမှန်ခြစ်ပြုလုပ်ထားခြင်းအားဖြင့် မိမိပြုလုပ်ထားသည့် ပြောင်းလဲမှုများကို ဆုံးရှုံးခြင်းမှ ကာကွယ်နိုင်မည်ဖြစ်သည်။
* |checkbox| :guilabel:`Prompt for confirmation when a layer is to be removed` (Layer တစ်ခုကို ဖယ်ရှားတော့မည်ဆိုလျှင် အတည်ပြုချက်တောင်းခံသည့် သတိပေးချက်) ကို အမှန်ခြစ်ပြုလုပ်နိုင်သည်။
* |checkbox| :guilabel:`Warn when opening a project file saved with an older version of QGIS` (QGIS version အဟောင်းဖြင့် သိမ်းဆည်းထားသည့် project ဖိုင်ကို ဖွင့်ရာတွင် သတိပေးခြင်း) QGIS version အဟောင်းဖြင့် ဖန်တီးထားသည့် project ဖိုင်များကို ဖွင့်နိုင်သော်လည်း project ကို တစ်ကြိမ်သိမ်းဆည်းပြီးသည်နှင့် ထို project ဖိုင်ကို QGIS version အဟောင်းဖြင့် ပြန်ဖွင့်ကြည့်သောအခါ ထို version အဟောင်းတွင် အချို့ features များမရရှိနိုင်သဖြင့် ဖွင့်နိုင်မည်မဟုတ်ပေ။
* :guilabel:`Enable macros` |selectString| (Macros များကိုဖွင့်ခြင်း) ဤ option ကို project များတွင် လုပ်ဆောင်ချက်တစ်ခုကို ဆောင်ရွက်ရန်ရေးသားထားသော macros များကို ကိုင်တွယ်အသုံးပြုနိုင်ရန် ဖန်တီးထားပါသည်။ ၎င်းတွင် 'Never'(ဘယ်တော့မှ မဖွင့်ပါ၊) ၊ 'Ask' (မေးမြန်းပါ)၊ 'For this session only' (ဤအပိုင်းအတွက်သာ) နှင့် 'Always (not recommended)' (အမြဲတမ်းဖွင့်ပါ (အကြံမပြုပါ)) တို့ကို ရွေးချယ်အသုံးပြုနိုင်ပါသည်။ 
* :guilabel:`Default paths` (မူလလမ်းကြောင်းများ) သည် project အသစ်များတွင် အသုံးပြုထားသည့် ဖိုင်များနှင့် layer များ၏ လမ်းကြောင်းများကို 'Absolute (ပကတိ)' သို့မဟုတ် 'Relative' (Project file နှင့်ဆက်နွယ်သော) အဖြစ် သိမ်းဆည်းခြင်းကို သတ်မှတ်ပေးပါသည်။ ဤ setting ကို project အဆင့်တွင် အစားထိုးရေးသားပြင်ဆင်နိုင်သည်။
* :guilabel:`Default project file format` (ပုံသေ project ဖိုင်အမျိုးအစား)

  * |radioButtonOn| :guilabel:`QGZ Archive file format, embeds auxiliary data` (အကူဒေတာများ ပါဝင်သည့် QGZ Archive ဖိုင်အမျိုးအစား) (:ref:`auxiliary data (အကူဒေတာ) <vector_auxiliary_storage>` တွင် ‌‌‌ကြည့်ရှုပါ)
  * |radioButtonOff| :guilabel:`QGS Project saved in a clear text, does not embed auxiliary data` (အကူဒေတာများမပါသော စာသားသီးသန့်ဖြင့် သိမ်းဆည်းထားသော QGS project) သည် အကူဒေတာ (auxiliary data) များကို project ဖိုင်နှင့်အတူ :file:`.qgd` ဖိုင်ပုံစံဖြင့် သီးခြားသိမ်းဆည်းထားခြင်းဖြစ်သည်။ 


.. index:: Environment variables
.. _`env_options`:

System Settings (စနစ် setting များ)
------------------------------------

.. _svg_paths:


**SVG လမ်းကြောင်းများ**


:guilabel:`Path(s) to search for Scalable Vector Graphic (SVG) Symbols` (အချိုးအစားချိန်ညှိနိုင်သည့် vector SVG သင်္ကေတများကိုရှာဖွေရန် လမ်းကြောင်း/များ) ကိုထည့်သွင်းခြင်း သို့မဟုတ် ဖယ်ရှားခြင်းတို့ ပြုလုပ်နိုင်ပါသည်။ ဤ SVG ဖိုင်များသည် feature များကို အညွှန်းတပ်ရာတွင်လည်းကောင်း သင်္ကေတများဖြင့် ဖော်ပြရာတွင်လည်းကောင်း မြေပုံဖွဲ့စည်းမှုကို အလှဆင်ရာတွင်လည်းကောင်း အသုံးပြုနိုင်ပါသည်။

QGIS လမ်းကြောင်းတစ်ခုထဲရှိ svg file များကို ရည်ညွှန်းကိုးကားနိုင်ရန် နည်းလမ်းအမျိုးမျိုးအတွက် :ref:`embedded_file_selector` ကိုဖတ်ရှုနိုင်ပါသည်။


**Plugin လမ်းကြောင်းများ**

:guilabel:`Path(s) to search for additional C++ plugin libraries` (C++ plugin library အပိုများကိုရှာဖွေရန် လမ်းကြောင်း(များ)) ကိုထည့်သွင်းအသုံးပြုခြင်း (သို့မဟုတ်) ဖယ်ရှားခြင်းတို့ကိုပြုလုပ်နိုင်ပါသည်။


.. _doc_config_path:

**မှတ်တမ်းမှတ်ရာများ လမ်းကြောင်းများ**

QGIS အကူအညီကိုအသုံးပြုနိုင်ရန် :guilabel:`Documentation Path(s)` (မှတ်တမ်းမှတ်ရာများ လမ်းကြောင်း(များ)) ကိုထည့်သွင်းခြင်း သို့မဟုတ် ဖယ်ရှားခြင်းတို့ကို ပြုလုပ်နိုင်ပါသည်။ ပုံမှန်အားဖြင့် အသုံးပြုနေသည့် ဗားရှင်းနှင့်သက်ဆိုင်သည့် တရားဝင်အသုံးပြုသူလမ်းညွှန်နှင့် ချိတ်ဆက်ထားသည့် link တစ်ခုကို ထည့်သွင်းထားသည်။ သို့ရာတွင် အခြား link များကိုလည်း ပေါင်းထည့်နိုင်ပြီး အဆိုပါ link များအား အပေါ်မှ အောက်သို့ ဦးစားပေးအစဉ်အတိုင်း ထည့်သွင်းနိုင်သည်။ Dialog ထဲရှိ :guilabel:`Help` button ကိုနှိပ်လိုက်သည့်အချိန်တိုင်းတွင် အပေါ်ဆုံးတွင် ရှိသော link ကို စစ်ဆေးပြီးနောက် သက်ဆိုင်သည့် စာမျက်နှာကို မတွေ့ရှိပါက နောက်ထပ် link များကို အဆင့်ဆင့်ထပ်မံစမ်းသပ်နိုင်ပါသည်။

.. note::
  မှတ်တမ်းမှတ်ရာများကို ကာလရှည်ထုတ်ဝေဖြန့်ချိခြင်း (Long Term Releases(LTR)) များအတွက်သာ version အလိုက်ထုတ်ဝေ၍ ဘာသာပြန်ဆိုထားခြင်းဖြစ်သည်။ ဆိုလိုသည်မှာ အကယ်၍ ပုံမှန်ထုတ်ဝေသည့် version (ဥပမာ- QGIS 3.0) ကို အသုံးပြုနေလျှင် အကူအညီ button သည် နောက်ထပ် LTR လမ်းညွှန်ဖြစ်သော (ဥပမာ- 3.4 LTR) စာမျက်နှာပေါ်လာမည်ဖြစ်သည်။ ၎င်း manual တွင် အသစ်ထွက်ရှိလာမည့် (3.2 နှင့် 3.4) တို့တွင် ပါဝင်လာနိုင်သော feature များ၏ ဖော်ပြချက်များပါရှိပါသည်။ အကယ်၍ မည်သည့် LTR မှတ်တမ်းကိုမျှ မရရှိလျှင် အသစ်ထွက်ရှိသည့် version များမှ feature များနှင့်အတူ *testing(အစမ်း)* မှတ်တမ်းများကို အသုံးပြုမည်ဖြစ်သည်။


**Setting များ**

Setting များသည် အကယ်၍ :ref:`customization <sec_customization>` (စိတ်ကြိုက်ပြင်ဆင်ခြင်း) ပြုလုပ်လျှင် :guilabel:`Reset user interface to default settings  (QGIS ကို ပြန်လည်စတင်ရန်လိုအပ်ပါသည်)` (အသုံးပြုသူဖက်မှ မြင်ရသည့်မျက်နှာပြင်ကို default setting များကိုပြန်ပြောင်းခြင်း) ကို လုပ်ဆောင်ရန် အကူအညီဖြစ်စေပါသည်။


**Environment (ပတ်ဝန်းကျင်)**


.. _figure_environment_variables:
.. figure:: img/options_system.png
   :align: center

   System environment variable များ

System ထဲရှိ environment variable များကို **Environment** group များထဲတွင် ကြည့်ရှုနိုင်ပြီး ပြင်ဆင်သတ်မှတ်ခြင်းများပြုလုပ်နိုင်ပါသည်။ ၎င်းသည် GUI application တစ်ခုမှ အသုံးပြုသူ၏ shell environment (command များ ရေးသားသည့်နေရာ) ကို မဖြစ်မနေလက်ဆင့်ကမ်းလုပ်ဆောင်ရန်မလိုအပ်သော Mac ကဲ့သို့ platform များအတွက် အလွန်အသုံးဝင်ပါသည်။ ၎င်းတို့သည် SAGA၊ GRASS စသော Processing toolbox မှ
ထိန်းချုပ်ထားသော ပြင်ပ tool အစုများအတွက် environment variable များကို ကြည့်ရှုခြင်းနှင့် setting များအတွက်လည်း အလွန်အသုံးဝင်ပြီး အရင်းအမြစ်ကုဒ် ၏ သီးသန့်အပိုင်းများအတွက် အမှားရှာဖွေခြင်းတို့ကို ပြုလုပ်ရာတွင် အလွန်အသုံးဝင်ပါသည်။


|checkbox| :guilabel:`Use custom variables (restart required - include separators)` (စိတ်ကြိုက် variables များကို အသုံးပြုခြင်း (separator များပါရှိပါက QGIS ပြန်လည်စတင်ရန် လိုအပ်သည်)) ကိုအမှန်ခြစ်ခြစ်၍ environment Variable များကို |symbologyAdd| :sup:`Add` (ပေါင်းထည့်ခြင်း) နှင့် |symbologyRemove| :sup:`Remove` (ဖယ်ရှားခြင်း) တို့ကိုပြုလုပ်နိုင်ပါသည်။ Item အသစ်တစ်ခုချင်းစီအတွက် :guilabel:`Variable` အမည်၊ ၎င်း၏ :guilabel:`Value` (တန်ဖိုး) နှင့် :guilabel:`Apply` (အသုံးပြုခြင်း) နည်းလမ်းများကို အောက်ဖော်ပြပါများအတိုင်း ပြင်ဆင်သတ်မှတ်နိုင်ပါသည်-

* :guilabel:`Overwrite` (အစားထိုးရေးသားပြင်ဆင်ခြင်း) သည် variable ၏ မူလရှိပြီးသားတန်ဖိုးကို အစားထိုးထည့်သွင်းခြင်းဖြစ်သည်။

* :guilabel:`If undefined` (အကယ်၍ မသတ်မှတ်ထားလျှင်) သည် OS သို့မဟုတ် application level များကဲ့သို့သော မြင့်မားသည့် အဆင့်များတွင် သတ်မှတ်ထားခြင်းမရှိသေးလျှင် ၎င်းတန်ဖိုးကို variable အတွက်အသုံးပြုပါသည်။

* :guilabel:`Unset` (မသတ်မှတ်ခြင်း) သည် environment မှ variable ကို ဖယ်ရှားခြင်းဖြစ်သည်။ (:guilabel:`Value` (တန်ဖိုး) parameter ကို အသုံးမပြုတော့ပေ)

* :guilabel:`Prepend` (မူလတည်းက သတ်မှတ်ထားခြင်း) သည် variable ၏ မူလရှိပြီးသားတန်ဖိုးတွင် တန်ဖိုးကို ကြိုတင်ထည့်သွင်းထားခြင်းဖြစ်သည်။

* :guilabel:`Append` (variable ၏တန်ဖိုးအဆုံးတွင် ချိတ်တွဲပေါင်းထည့်ခြင်း) သည် variable ၏ မူလရှိပြီးသားတန်ဖိုးတွင် တန်ဖိုးကို ချိတ်တွဲပေါင်းထည့်ခြင်းဖြစ်သည်။

* :guilabel:`Skip` (ကျော်သွားခြင်း) သည် ယခုအသုံးမပြုသော်လည်း နောက်ပိုင်းတွင်ကိုးကား၍ အသုံးပြုနိုင်ရန် item ကိုစာရင်းထဲတွင် ဆက်လက်ထားရှိခြင်းဖြစ်သည်။ 

သတ်မှတ်ပြီးဖြစ်သော variable များကို :guilabel:`Current environment variables` (လက်ရှိ environment variable များ) တွင် ဖော်ပြထားပြီး |checkbox| :guilabel:`Show only QGIS-specific variables` (QGIS ၏သီးသန့် variable များကိုသာ ပြသခြင်း) ကို စတင်ခြင်းဖြင့် ၎င်းတို့ကို စစ်ထုတ်နိုင်ပါသည်။


User Profiles Settings (အသုံးပြုသူပရိုဖိုင် setting များ)
----------------------------------------------------------

.. note:: အသုံးပြုသူပရိုဖိုင်များကို စီမံခန့်ခွဲနိုင်ရန်အတွက် အချက်အလက်များကို သီးသန့်ထည့်သွင်းထားသည့် :ref:`user_profiles` အခန်းတွင် ဖတ်ရှုနိုင်ပါသည်။


.. index:: CRS, On-the-fly reprojection
.. _crs_options:

CRS and Transforms Settings (ရည်ညွှန်းကိုဩဒိနိတ်စနစ်နှင့် အသွင်ပြောင်းလဲခြင်း setting များ)
--------------------------------------------------------------------------------------------

.. note:: 
  
  QGIS သည် Layer ၏ အရိပ်ချစနစ်ကို မည်သို့ကိုင်တွယ်သည်ကို ပိုမိုသိရှိလိုလျှင် သီးသန့်ထည့်သွင်းထားသည့် :ref:`label_projections` အခန်းတွင် ဖတ်ရှုနိုင်ပါသည်။


CRS Handling (ရည်ညွှန်းကိုဩဒိနိတ်စနစ်များကို ကိုင်တွယ်အသုံးပြုခြင်း)
.....................................................................

|crs| :guilabel:`CRS Handling` (ရည်ညွှန်းကိုဩဒိနိတ်စနစ်(CRS)များကို ကိုင်တွယ်အသုံးပြုခြင်း) tab တွင် Layer သို့မဟုတ် project အသစ်တစ်ခုအတွက် မည်သည့် CRS အသုံးပြုမည်ကို သတ်မှတ်နိုင်သည်။

.. _figure_crs_options:


.. figure:: img/options_crs.png
   :align: center

   CRS Setting များ

**Project များအတွက် CRS**

Project အသစ်၏ CRS စနစ်ကို အလိုအလျောက်သတ်မှတ်ရန် ရွေးချယ်စရာတစ်ခုရှိပါသည်-

* |radioButtonOn|:guilabel:`Use CRS from first layer added` (ပထမဦးဆုံးထည့်သွင်းသည့် Layer ၏ CRS ကို အသုံးပြုခြင်း) သည် project ၏ CRS စနစ်ကို ကနဦး ထည့်သွင်းအသုံးပြုလိုက်သော Layer ၏ CRS စနစ်အတိုင်း သတ်မှတ်သွားမည်ဖြစ်ပါသည်။
* |radioButtonOff|:guilabel:`Use a default CRS` (Default CRS တစ်ခုကို အသုံးပြုခြင်း) သည် ကြိုတင်ရွေးချယ် သတ်မှတ်ထားသော CRS တစ်ခုကို default အနေဖြင့် project အသစ်တွင် အသုံးပြုသွားမည်ဖြစ်ပြီး project ထဲသို့ Layer များ ထည့်သွင်းသောအခါတွင်လည်း မပြောင်းလဲပဲ ရှိနေမည်ဖြစ်သည်။


ထိုရွေးချယ်မှုကို QGIS ၏ ဆက်လက်ဆောင်ရွက်မည့်အပိုင်းများတွင် အသုံးပြုရန် သိမ်းဆည်းထားပါလိမ့်မည်။
Project ၏ ရည်ညွှန်းကိုဩဒိနိတ်စနစ်ကို :menuselection:`Project --> Properties... --> CRS` tab တွင် အစားထိုးပြင်ဆင်ပြောင်းလဲနိုင်နေဦးမည်ဖြစ်ပါသည်။


**Layer များအတွက် ရည်ညွှန်းကိုဩဒိနိတ်စနစ်**

:guilabel:`Default CRS for layers` (Layer များအတွက် default CRS သတ်မှတ်ခြင်း) သည် Layer တစ်ခုကို စတင်ဖန်တီးလိုက်သောအခါ အသုံးပြုမည့် default CRS တစ်ခုကို ‌ရွေးချယ်ခြင်းဖြစ်သည်။

Layer တစ်ခုကို စတင်ဖန်တီးလိုက်သောအခါ သို့မဟုတ် CRS သတ်မှတ်ထားခြင်းမရှိသော Layer တစ်ခုကို ထည့်သွင်းအသုံးပြုလိုက်သောအခါ ဆောင်ရွက်မည့် လုပ်ဆောင်ချက်များ‌ကိုလည်း သတ်မှတ်ပေးနိုင်ပါသည်။


* |radioButtonOn| :guilabel:`Leave as unknown CRS (take no action)` (အမည်မသိ CRS အဖြစ်ထားရှိပါ (မည်သည့်လုပ်ဆောင်ချက်ကိုမျှ ဆောင်ရွက်ခြင်းမရှိ))
* |radioButtonOff| :guilabel:`Prompt for CRS` (CRS အတွက် သတိပေးပါ)
* |radioButtonOff| :guilabel:`Use project CRS` (Project ၏ CRS အတိုင်း အသုံးပြုပါ)
* |radioButtonOff| :guilabel:`Use default layer CRS` (Defautl layer CRS ကိုအသုံးပြုပါ)


.. _crs_inaccuracies:


**တိကျမှု သတိပေးချက်များ**


.. A small intro either on accuracy differences between CRS/datum,
   or static vs dynamic CRS would be nice here.
   Or if you want, you can expand a lot in the working_with_projection.rst file.


   Also if anyone knows a link to "datum ensemble" concept?


:guilabel:`Only show CRS accuracy warnings for inaccuracies which exceed` (သတ်မှတ်အကွာအဝေးကို ကျော်လွန်သော မတိကျမှုများအတွက် CRS တိကျမှုသတိပေးချက်များကိုသာ ဖော်ပြခြင်း)- Data အစုတစ်ခုကို မွမ်းမံပြင်ဆင်ခြင်း သို့မဟုတ် အတိအကျဖန်တီးပြီး တိကျမှုနည်းသော ရည်ညွှန်းမျက်နှာပြင် (datum) ပေါ် အခြေခံထားသည့် CRS တစ်ခုကို ရွေးချယ်အသုံးပြုလိုက်သောအခါ တွေ့ရပါသည်။ ပုံသေအားဖြင့် တိကျမှုနည်းသည့် မည်သည့် CRS ကိုမဆို ``အမြဲပြသ`` နေမည်ဖြစ်သည်။ သို့သော် QGIS version သည် အနိမ့်ဆုံး `PROJ 8.0 <https://proj.org/index.html>`_ ကို အသုံးပြုရန် လိုအပ်သည်။


|unchecked| :guilabel:`Show CRS accuracy warning for layers in project legend` (Project ရည်ညွှန်းချက်ထဲရှိ Layer များအတွက် CRS တိကျမှုကိုပြသခြင်း) ကို အမှန်ခြစ်ပြုလုပ်ထားလျှင် တိကျမှုပြဿနာရှိသော CRS တစ်ခုရှိသည့် မည်သည့် layer တွင်မဆို (ဆိုလိုသည်မှာ ကိုဩဒိနိတ်စနစ်မရှိသော ပြောင်းလဲနေသည့် CRS သို့မဟုတ် အသုံးပြုသူကန့်သတ်ထားသော တိကျမှုထက်ကျော်လွန်သည့် မတိကျသောရည်ညွှန်းမျက်နှာပြင်ကိုအခြေခံထားသော CRS) ၎င်းသည် တိကျမှုနည်းသည့် Layer ဖြစ်ကြောင်းကို ဖော်ပြသည့် |indicatorLowAccuracy| သတိပေးချက် icon :guilabel:`Layers` panel ထဲတွင် ရှိလိမ့်မည်ဖြစ်သည်။

၎င်းကို မီတာ/မီတာခွဲအဆင့်မျှရှိသော မတိကျမှုများသည် အလွန်အဖိုးအခကြီးနိုင်သည့် သို့မဟုတ် အန္တရာယ်များနိုင်သည့် နယ်ပယ်များဖြစ်သော အင်ဂျင်နီယာပညာရပ်များ၊ ဆောက်လုပ်ရေးဆိုင်ရာ အချက်အလက်မော်ဒယ်တည်ဆောက်ခြင်းများ (BIM)၊ ပစ္စည်းဥစ္စာစီမံခန့်ခွဲမှုနှင့် အခြားနယ်ပယ်များအတွက် ရည်ရွယ်၍ ရေးဆွဲခဲ့ခြင်းဖြစ်သည်။

|unchecked| :guilabel:`Planimetric measurements` (ရေပြင်ညီတိုင်းတာမှုများ) သည် အသစ်ဖန်တီးလိုက်သော project များအတွက် :ref:`planimetric measurements <measurements_ellipsoid>` property အတွက် default ကိုသတ်မှတ်ပေးသည်။


.. index:: CRS, Datum transformation, Reprojection
.. _transformations_options:


Coordinate Transforms (ကိုဩဒိနိတ် ကူးပြောင်းခြင်းများ)
.......................................................

|transformation| :guilabel:`Coordinate Transforms` (ကိုဩဒိနိတ် ကူးပြောင်းခြင်း) tab သည် project တစ်ခုထဲသို့ Layer ကိုထည့်သွင်းအသုံးပြုခြင်း သို့မဟုတ် Layer တစ်ခု၏ အရိပ်ချစနစ်ပြောင်းလဲသတ်မှတ်ခြင်း‌ဆောင်ရွက်ရာတွင် ကိုဩဒိနိတ် ကူးပြောင်းခြင်းများနှင့် လုပ်ငန်းများကို ဆောင်ရွက်ရန် ကူညီပေးပါသည်။


.. _figure_transfo_options:


.. figure:: img/options_transformations.png
   :align: center


   ကူးပြောင်းခြင်းဆိုင်ရာ setting များ


**Default Datum Transformations** (**Default မူတည်မျက်နှာပြင် ကူးပြောင်းခြင်း**)

Laye များကို အခြား CRS သို့ အရိပ်ချစနစ်ပြောင်းလဲသင့်/မသင့်ကို ဤတွင် ကိုင်တွယ်ထိန်းချုပ်နိုင်ပါသည်-

* QGIS ၏ default ကူးပြောင်းခြင်း setting များကို အသုံးပြုခြင်းဖြင့် လုပ်ငန်းစဉ်များကို အလိုအလျောက် လုပ်ဆောင်ခြင်း၊
* အောက်ဖော်ပြပါတို့ကဲ့သို့သော စိတ်ကြိုက် ဦးစားပေးရွေးချယ်မှုများဖြင့် လုပ်ဆောင်ခြင်း-

  * |checkbox| :guilabel:`Ask for datum transformation if several are available` (ကူးပြောင်းမှုများစွာရရှိနိုင်ပါက မူတည်မျက်နှာပြင် ကူးပြောင်းခြင်းအတွက်မေးမြန်းပါ) ကို အမှန်ခြစ်ခြင်း။
  * Default အဖြစ်အသုံးပြုရန် ကြိုတင်သတ်မှတ်ထားသော မူတည်မျက်နှာပြင်ကူးပြောင်းခြင်းများ စာရင်း။ အသေးစိတ်အချက်အလက်များအတွက် :ref:`datum_transformation` (မူတည်မျက်နှာပြင်ကူးပြောင်းခြင်း) တွင်ကြည့်နိုင်ပါသည်။

အသစ်ဖန်တီးထားသော မည်သည့် project တွင်မဆို  |symbologyAdd| :sup:`Add` (ပေါင်းထည့်ခြင်း)၊ |symbologyRemove| :sup:`Remove` (ဖယ်ရှားခြင်း) သို့မဟုတ် |toggleEditing| :sup:`Edit` transformation (ကူးပြောင်းခြင်းကို တည်းဖြတ်ပြင်ဆင်ခြင်း) များ ဆောင်ရွက်နိုင်ပါသည်။


User Defined CRS (အသုံးပြုသူမှ သတ်မှတ်သော ရည်ညွှန်းကိုဩဒိနိတ်စနစ်)
...................................................................

|customProjection| :guilabel:`User Defined CRS` (အသုံးပြုသူမှ သတ်မှတ်သော ရည်ညွှန်းကိုဩဒိနိတ်စနစ်) tab သည် WKT သို့မဟုတ် Proj string format နှင့် လိုက်လျောညီထွေဖြစ်စေသော စိတ်ကြိုက် CRS တစ်ခု သတ်မှတ်ရန် ကူညီပေးနိုင်ပါသည်။


.. _figure_defined_crs:


.. figure:: img/options_defined_crs.png
   :align: center


   အသုံးပြုသူမှ သတ်မှတ်သော ရည်ညွှန်းကိုဩဒိနိတ်စနစ်


:guilabel:`Name` (အမည်) တစ်ခုသတ်မှတ်၍ |symbologyAdd| :sup:`Add new CRS` (CRS အသစ်ထည့်ခြင်း) ကို ဆောင်ရွက်နိုင်ပြီး ရှိနေပြီးသား CRS တစ်ခုကိုဖျက်လိုလျှင်  |symbologyRemove| :sup:`Remove CRS` (CRS ဖယ်ရှားခြင်း) ကိုအသုံးပြု၍ လုပ်ဆောင်နိုင်သည်။


**Definition** (**အဓိပ္ပါယ်သတ်မှတ်ချက်**)

* :guilabel:`Format`

   * WKT (အသုံးပြုရန်အကြံပြုပါသည်)
   * Proj String (Legacy - အသုံးမပြုရန် အကြံမပြုပါ)

* :guilabel:`Parameters`

   * |editCopy| သည် ရှိနေပြီးသား CRS တစ်ခုမှ parameter များ ကူးယူရာတွင်အသုံးပြုပါသည်။
   * :guilabel:`Validate` (အတည်ပြုခြင်း) သည် expression (ခိုင်းစေချက်) သည် မှန်ကန်ကြောင်း စစ်ဆေးရာတွင်အသုံးပြုပါသည်။


**Test** (**စမ်းသပ်မှု**)

မိမိဖန်တီးထားသော CRS အဓိပ္ပါယ်သတ်မှတ်ချက်များကို လတ္တီကျုနှင့် လောင်ဂျီကျု များဖြင့် စမ်းသပ်နိုင်ပါသည်။ အဓိပ္ပါယ်သတ်မှတ်ချက်သည် မှန်ကန်တိကျမှုရှိ/မရှိ ထိန်းချုပ်ရန်  သိပြီးဖြစ်သော ကိုဩဒိနိတ်တစ်ခုကို အသုံးပြုပါ။


.. _datasources_options:


Data Sources settings (Data ရင်းမြစ် setting များ)
---------------------------------------------------

.. _figure_data_sources_settings:


.. figure:: img/options_data_sources.png
   :align: center


   Data ရင်းမြစ် setting များ


**Feature attributes and table** (**Feature အချက်အလက်များနှင့် ဇယား**)

* |checkbox| :guilabel:`Open attribute table as docked window` (Attribute ဇယားကို window တစ်ခုဖြင့် ဖွင့်မည်)
* :guilabel:`Copy features as` (feature ကို … အဖြစ် ကူးယူခြင်း) 'Plain text, no geometry' (စာသား၊ geometry မပါ)၊ 'Plain text, WKT geometry' (စာသား၊ WKT geometry များ) သို့မဟုတ် အခြား application များတွင် feature များကို paste (ကူးချ) လုပ်သောအခါ 'GeoJSON' အဖြစ် ကူးယူနိုင်ပါသည်။ 
* :guilabel:`Attribute table behavior` |selectString| (Attribute ဇယား လုပ်ဆောင်ပုံ) သည် attribute ဇယားကို ဖွင့်လျှင် စစ်ထုတ်မှုများကို သတ်မှတ်ပေးပါသည်။ ဖြစ်နိုင်ခြေ ၃ မျိုးရှိပါသည်- 'Show all features (feature အားလုံးပြသခြင်း)'၊ 'Show selected features (ရွေးချယ်ထားသည့် feature များသာ ပြသခြင်း)' နှင့်  'Show features visible on map (မြေပုံပေါ်တွင် မြင်ရသည့် feature များသာ ပြသခြင်း)' တို့ဖြစ်ပါသည်။ 
* :guilabel:`Default view` (Default မြင်ကွင်း) သည် attribute ဇယားကို ဖွင့်လိုက်သည့်အခါတိုင်းတွင် မြင်ကွင်း mode ကို သတ်မှတ်ပေးပါသည်။ 'Remember last view (နောက်ဆုံး မြင်ကွင်းအား မှတ်သားခြင်း)'၊ 'Table view (ဇယားမြင်ကွင်း)' သို့မဟုတ် 'Form view (Form မြင်ကွင်း)' ဟူ၍ သတ်မှတ်ပေးနိုင်ပါသည်။ 
* :guilabel:`Attribute table row cache` |selectNumber| (Attribute ဇယား row မှတ်တမ်း) သည် နောက်ဆုံးထည့်သွင်းခဲ့သော N attribute row (N ကြိမ်မြောက် ဇယားတန်း) များကို သိမ်းဆည်းထားနိုင်သောကြောင့် attribute ဇယား၏ လုပ်ဆောင်ချက်များကို ပိုမိုလျင်မြန်စွာလုပ်ဆောင်နိုင်စေပါသည်။ Attribute ဇယားကို ပိတ်လိုက်သည့်အခါ မှတ်တမ်းများကိုလည်း ဖျက်ပစ်မည်ဖြစ်ပါသည်။ 
* :guilabel:`Representation for NULL values` (Null တန်ဖိုးများအတွက် ကိုယ်စားပြုဖော်ပြခြင်း) ဤနေရာတွင် Null တန်ဖိုးပါဝင်သည့် data field များအတွက် တန်ဖိုးတစ်ခုကို သတ်မှတ်ပေးနိုင်ပါသည်။ 


.. _tip_table_filtering:

.. tip:: **Data များစွာ ပါဝင်သည့် attribute ဇယားဖွင့်ရာတွင် ပိုမိုမြန်ဆန်စေခြင်း**

 Data သိမ်းဆည်းမှု (records) များစွာရှိနေသော layer များနှင့် လုပ်ဆောင်သောအခါ dialog သည် layer ရှိ row များအားလုံးကို တောင်းဆိုသောကြောင့် attribute ဇယားကိုဖွင့်ရာတွင် နှောင့်နှေးကြန့်ကြာနိုင်သည်။  :guilabel:`Attribute table behavior` setting ထဲရှိ **Show features visible on map (မြေပုံပေါ်တွင် လက်ရှိမြင်တွေ့ရသည့် feature များသာဖော်ပြခြင်း)** ကို ဖွင့်ထားပါက ဇယားကို ဖွင့်လိုက်သည့်အခါ လက်ရှိအသုံးပြုနေသော မြေပုံမျက်နှာပြင်ရှိ feature များကိုသာလျှင် ဖော်ပြပေးမည်ဖြစ်သဖြင့် ပိုမိုမြန်ဆန်သွားမည်ဖြစ်သည်။ 


Attribute ဇယားရှိ data သည် ဖွင့်ထားသည့် မြေပုံမျက်နှာပြင်အကျယ်အဝန်း (canvas extent) နှင့် ချိတ်ဆက်နေမည်ဖြစ်ပြီး ထိုကဲ့သို့သော ဇယားတစ်ခုအတွင်း **Show All Features** (Feature အားလုံးပြသခြင်း) ကို ရွေးချယ်ခြင်းသည် ဇယားထဲရှိ feature အသစ်များကို ဖော်ပြမည်မဟုတ်ပေ။ သို့သော်လည်း မြေပုံမျက်နှာပြင်အကျယ်အဝန်းကို ပြောင်းလဲခြင်းပြီး attribute ဇယားရှိ **Show Features Visible On Map** (မြေပုံပေါ်တွင် မြင်နိုင်သော Feature များကိုသာ ပြသခြင်း) option ကိုရွေးချယ်ကာ ဖော်ပြလိုသည့် feature များကို ပြင်ဆင်သတ်မှတ်ပေးနိုင်မည်ဖြစ်သည်။ 


**Data source handling** (**Data ရင်းမြစ်ကို ကိုင်တွယ်အသုံးပြုခြင်း**)

* :guilabel:`Scan for valid items in the browser dock` |selectString| (Brower တွင် ဆီလျော်မှုရှိသော item များကို scan ဖတ်ခြင်း) တွင် 'Check extension (ဖိုင် extension ကိုစစ်ဆေးခြင်း)' နှင့် 'Check file contents (ဖိုင်အကြောင်းအရာစစ်ဆေးခြင်း)' တို့ကို ရွေးချယ်နိုင်ပါသည်။ 
* :guilabel:`Scan for contents of compressed files (.zip) in browser dock` |selectString| (Brower တွင် ဖိုင်အရွယ်အစားချုံ့ထားသော ဖိုင်များ (.zip) ကို scan ဖတ်ခြင်း) သည် ထိုဖိုင်များကို query လုပ်သောအခါ brower panel အောက်ခြေရှိ widget အချက်အလက်များ မည်မျှအသေးစိတ်ကျမည်ကို သတ်မှတ်ပေးပါသည်။ ဖြစ်နိုင်သော option များမှာ 'No (မဖတ်ပါ)'၊ 'Basic scan (အခြေခံမျှသာ scan ဖတ်ခြင်း)' နှင့် 'Full scan(အပြည့်အဝ scan ဖတ်ခြင်း)' တို့ဖြစ်ပါသည်။
* :guilabel:`Prompt for sublayers when opening` (ဖွင့်သောအခါ layer အခွဲများအတွက် အချက်ပေးခြင်း) - အချို့သော raster များသည် GDAL တွင် subdataset (Data အစုခွဲ) များ ဟုခေါ်သော sublayer (Layer အခွဲ) များကို ပံ့ပိုးပေးပါသည်။ ဥပမာတစ်ခုမှာ netCDF file ဖြစ်သည်-- netCDF variable များစွာရှိနေလျှင် GDAL သည် variable တိုင်းကို subdataset တစ်ခုအဖြစ် မြင်မည်ဖြစ်ပါသည်။ ဤရွေးချယ်မှုသည် Sublayer များရှိသည့် file တစ်ခုကိုဖွင့်လိုက်သည့်အခါ sublayer များကို မည်သို့ကိုင်တွယ်မည်ကို ထိန်းချုပ်ပေးနိုင်ပါသည်။ အောက်တွင်ဖော်ပြထားသော ရွေးချယ်မှုများကို ပြုလုပ်နိုင်ပါသည်- 

  * 'Always' - အမြဲတမ်းအချက်ပေးမေးမြန်းပါမည် (Sublayer များရှိနေပြီးသားဖြစ်လျှင်)
  * 'If needed' - Layer တွင် band (လှိုင်းအလွှာ) များမရှိနေဘဲ sublayer များရှိနေလျှင် အချက်ပေးမေးမြန်းပါမည်
  * 'Never' - ဘယ်တော့မှအချက်ပေးမေးမြန်းမည်မဟုတ်ပဲ မည်သည့်အရာကိုမှ ထည့်သွင်းအသုံးပြုမည်မဟုတ်ပေ။
  * 'Load all' - ဘယ်တော့မှအချက်ပေးမေးမြန်းမည်မဟုတ်ပဲ sublayer များအားလုံးကို ထည့်သွင်းအသုံးပြုမည်ဖြစ်သည်။


* |checkbox| :guilabel:`Automatically refresh directories in browser dock when their contents change` (ပါဝင်သည့်အကြောင်းအရာများ ပြောင်းလဲလျှင် သိမ်းဆည်းရာ လမ်းကြောင်းကို အလိုအလျောက် refresh လုပ်ပေးခြင်း) ကို အမှန်ခြစ်ပြုလုပ်ခြင်းသည် default အနေဖြင့် :guilabel:`Browser` panel ရှိ လမ်းကြောင်းများကို စောင့်ကြည့်ခြင်းအား ရှောင်ရှားနိုင်ပါသည်။ (ဥပမာ- ကွန်ယက်စောင့်ဆိုင်းရမှုကြောင့်ဖြစ်သော နှောင့်နှေးနိုင်ခြေကို ရှောင်ရှားရန်)


**Localized data paths** (**ကွန်ပျူတာထဲရှိ Data လမ်းကြောင်းများ)**

ဖိုင်ကို အခြေခံသော မည်သည့် data ရင်းမြစ်အတွက်မဆို ကွန်ပျူတာထဲရှိသိမ်းဆည်းရာလမ်းကြောင်းများကို အသုံးပြုနိုင်ပါသည်။ ၎င်းတို့သည် data ရင်းမြစ် တည်နေရာကို ဆွဲထုတ်နိုင်ရန် အသုံးပြုသည့် လမ်းကြောင်းများ၏ စာရင်းတစ်ခု ဖြစ်ပါသည်။ ဥပမာ- :file:`C:\\my_maps` ကို လမ်းကြောင်းများစာရင်းထဲတွင် ထည့်ထားလျှင် :file:`C:\\my_maps\\my_country\\ortho.tif` ရှိသည့် layer တစ်ခုကို :file:`localized:my_country\\ortho.tif` ကိုအသုံးပြု၍ project ထဲတွင် data ရင်းမြစ်အဖြစ် သိမ်းဆည်းမည်ဖြစ်ပါသည်။ 

ဖိုင်လမ်းကြောင်းများကို ဦးစားပေးအစဉ်အလိုက် စာရင်းလုပ်ထားမည်ဖြစ်ပြီး တစ်နည်းအားဖြင့် QGIS သည် ပထမလမ်းကြောင်းရှိဖိုင်ကို ပထမဦးဆုံးရှာဖွေ၍ ထို့နောက်မှသာ ဒုတိယတစ်ခုကို ရှာဖွေမည်ဖြစ်ပါသည်။ 


**Hidden browser paths** (**ကွယ်ဝှက်ထားသော Browser လမ်းကြောင်းများ**)

ဤ widget သည် :ref:`Browser panel <browser_panel>` မှ ကွက်ဝှက်ထားလိုသည့် folder များအားလုံးကို စာရင်းပြုစုထားခြင်းဖြစ်သည်။ ထို စာရင်းမှ folder တစ်ခုကို ဖယ်ရှားလိုက်ပါက ထို folder ကို :guilabel:`Browser` panel တွင် တွေ့ရှိရမည်ဖြစ်သည်။ 


.. _gdal_options:


GDAL Setting များ
..................

`GDAL <https://gdal.org>`_ သည် vector နှင့် raster format ပေါင်းမြောက်များစွာကို ပံ့ပိုးပေးသည့် geospatial data (မြေပုံသတင်းအချက်အလက် data) အတွက် data များကို ကူးပြောင်းလဲလှယ်နိုင်သည့် library တစ်ခုဖြစ်ပါသည်။ ၎င်းတွင် ထို format များဖြင့် data ဖတ်ရန်နှင့် (တခါတရံတွင်) ရေးသားရန် driver များရှိပါသည်။ :guilabel:`GDAL` tab တွင် raster နှင့် vector format များအတွက် ၎င်းတို့၏လုပ်ဆောင်နိုင်စွမ်းများနှင့်အတူ driver များရှိပါသည်။ 


**GDAL raster နှင့် vector driver များ**

:guilabel:`Raster Drivers` နှင့် :guilabel:`Vector Drivers` tab များသည် အချို့သော ကိစ္စရပ်များတွင် GDAL driver တစ်ခုထက်ပို၍ ရနိုင်သောကြောင့် ဖိုင်များကို ဖတ်ရန် သို့မဟုတ် ရေးသားရန်အတွက် မည်သည့် GDAL driver များကို အသုံးပြုမည်ကို သတ်မှတ်နိုင်ပါသည်။ 


.. _figure_gdal_settings:
.. figure:: img/options_gdal.png
   :align: center


   GDAL Setting များ - Raster driver များ

.. tip:: 
  ဖတ်ခြင်းနှင့်ရေးခြင်းကို ဆောင်ရွက်နိုင်သည့် (``rw+(v)``) raster driver တစ်ခုကို click နှစ်ချက်နှိပ်လိုက်လျှင် စိတ်ကြိုက်ပြင်ဆင်ခြင်းအတွက် :ref:`Edit Create options (ဖန်တီးတည်းဖြတ်ရန်ရွေးချယ်စရာများ) <gdal_createoptions>` dialog ကို ပွင့်လာစေမည်ဖြစ်သည်။


**Raster driver options** (**Raster driver ရွေးချယ်စရာများ**)

ဤ frame သည် ဖတ်ရှုရေးသားနိုင်သည့် raster driver များ၏ လုပ်ဆောင်ချက်များကို စိတ်ကြိုက်ပြုလုပ်ရန် နည်းလမ်းများ ပံ့ပိုးပေးပါသည်- 


.. _gdal_createoptions:

* :guilabel:`Edit create options` (ဖန်တီးတည်းဖြတ်ရန် ‌ရွေးချယ်စရာများ) သည် ဖိုင်ပုံစံကူးပြောင်းခြင်း၏ မတူညီသော profile များကို တည်းဖြတ်ပြင်ဆင်ခြင်း သို့မဟုတ် ထပ်ပေါင်းထည့်ခြင်းတို့ကို လုပ်ဆောင်နိုင်ပါသည်။ ဆိုလိုသည်မှာ raster file များထုတ်သည့်အခါ အသုံးပြုရန် ကြိုတင်သတ်မှတ်ပေါင်းစပ်ထားသည့် parameter များ (ချုံ့နိုင်သည့် အမျိုးအစားနှင့် အဆင့်၊ block အရွယ်အစား၊ ခြုံငုံသုံးသပ်ချက်၊ အရောင်ပြောင်းပေးနိုင်သည့်အရာများ၊ alpha စသည်တို့) ကို ပြင်ဆင်တည်းဖြတ်ရန်နှင့် ထပ်ပေါင်းထည့်ရန် :guilabel:`Edit create options` ကို အသုံးပြုနိုင်ခြင်းဖြစ်သည်။ ထို parameter များသည် driver ပေါ်တွင် မူတည်နေပါသည်။ 


  .. _figure_gdal_create_settings:


  .. figure:: img/gdalCreateOptions.png
     :align: center

     Create options profile နမူနာ (GeoTiff ဖိုင်အတွက်)

Dialog ၏ အပေါ်ပိုင်းတွင် ယခုလက်ရှိ အသုံးပြုနေသော profile (များ) ကို စာရင်းပြုစုထားပြီး အသစ်များထပ်ထည့်ခြင်းနှင့် ဖယ်ရှားခြင်းတို့ကို ပြုလုပ်နိုင်ပါသည်။ Profile များကို ပြောင်းလဲပြီးလျှင်လည်း profile ကို ၎င်း၏ default parameter များ အဖြစ်သို့ ပြန်လည် သတ်မှတ်နိုင်ပါသည်။ အချို့သော driver (ဥပမာ-GeoTiff) များတွင် အသုံးပြုနိုင်သည့် နမူနာ profile အချို့ရှိပါသည်။

  Dialog ၏ အောက်ခြေတွင်- 

  * |symbologyAdd| ခလုတ်သည် parameter အမည်နှင့် တန်ဖိုးကို ဖြည့်ရန်အတွက် row (အတန်း) များကို ပေါင်းထည့်နိုင်ပါသည်။ 
  * |symbologyRemove| ခလုတ်သည် ရွေးချယ်ထားသည့် parameter ကို ဖျက်ပစ်နိုင်ပါသည်။ 
  * :guilabel:`Validate` ခလုတ်ကို click နှိပ်ခြင်းဖြင့် ပေးထားသည့် format အတွက် ထည့်သွင်းထားသော creation option များ ဆီလျော်မှုရှိ/မရှိ စစ်ဆေးနိုင်ပါသည်။ 
  * :guilabel:`Help` ခလုတ်သည် အသုံးပြုမည့် parameter များကို ရှာဖွေရန် သို့မဟုတ် `GDAL raster drivers documentation <https://gdal.org/drivers/raster/index.html>`_ (GDAL raster drivers မှတ်တမ်းမှတ်ရာ)` များကို ကိုးကားရန် အသုံးပြုနိုင်ပါသည်။ 


.. _gdal_pyramidsoptions:

* :guilabel:`Edit Pyramids Options` (Pyramid များဆိုင်ရာ ရွေးချယ်စရာများကို တည်းဖြတ်ပြင်ဆင်ခြင်း) 


  .. _figure_gdal_pyramids_settings:


  .. figure:: img/gdalPyramidsOptions.png
     :align: center


     Pyramid များ profile ၏ နမူနာ


.. index:: Rendering
.. _rendering_options:


Rendering Settings (ပုံဖော်ပြသခြင်း setting များ)
--------------------------------------------------

|rendering| :guilabel:`Rendering` (ပုံဖော်ပြသခြင်း) tab သည် မြေပုံ canvas ထဲတွင် layer ပုံဖော်ပြသခြင်းများကို ထိန်းချုပ်ကိုင်တွယ်ရန်အတွက် setting များကို ပံ့ပိုးပေးပါသည်။ 


.. _figure_rendering_menu:


.. figure:: img/options_rendering.png
   :align: center


   ပုံဖော်ပြသခြင်း setting များ

**Rendering Behavior** (**ပုံဖော်ပြသခြင်း လုပ်ဆောင်ပုံ**)

* |checkbox| :guilabel:`By default new layers added to the map should be displayed` (မြေပုံထဲသို့ထည့်သွင်းသော layer အသစ်များကို default အနေဖြင့်ပြသသင့်သည်) ကို အမှန်ခြစ်ဖြုတ်ခြင်းဖြင့် layer များစွာကို ထည့်သွင်းသည့်အခါ မြေပုံ canvas တွင် layer တစ်ခုချင်းစီကို ပုံဖော်ပြသနေခြင်းနှင့် လုပ်ငန်းစဉ်ကိုနှေးကွေးစေခြင်းမှ ရှောင်ရှားပေးနိုင်ပါသည်။ 
* :guilabel:`Maximum cores to use for map rendering` (မြေပုံ ပုံဖော်ပြသခြင်းအတွက် အသုံးပြုရန် အများဆုံး core များ) ကို သတ်မှတ်နိုင်သည်။
* မြေပုံ canvas သည် နောက်ကွယ်၌ သီးခြား image တစ်ခုပေါ်တွင် :guilabel:`Map update interval` (မြေပုံ update လုပ်ပေးသည့်ကြားကာလ) (default - 250 မီလီစက္ကန့်) တစ်ခုစီ၌ ပုံဖော်ပြသပြီး ထို (off-screen) နောက်ကွယ် image မှ အကြောင်းအရာများကို မြင်နိုင်သောမျက်နှာပြင်ပေါ်ပြသရာတွင် အသုံးပြုမည်ဖြစ်သည်။ သို့သော်လည်း ပုံဖော်ပြသခြင်းသည် ထိုကြာချိန်ထက် စောလျင်စွာပြီးစီးနေပါက ၎င်းကို ချက်ချင်းပြသပေးပါလိမ့်မည်။
* :guilabel:`Magnification level` (ပုံရိပ်ချဲ့သည့်အဆင့်) (:ref:`magnifier (မှန်ဘီလူး) <magnifier>` တွင် ကြည့်နိုင်ပါသည်။)


**Rendering Quality** (**ပုံဖော်ပြသမှုအရည်အသွေး**)

* |checkbox| :guilabel:`Make lines appear less jagged at the expense of some drawing performance` (ပုံဆွဲခြင်းစွမ်းရည်အချို့ကြောင့် မျဉ်းများကို မညီညာသောအစွန်းထွက်များဖြစ်ပေါ်မှုကို နည်းစေသည့် လုပ်ဆောင်ခြင်း) ကို အမှန်ခြစ် ပြုလုပ်ပါ။ 


Vector rendering settings (Vector ပုံဖော်ပြသမှု setting များ)
..............................................................

|polygonLayer| :guilabel:`Vector` tab တွင် vector layer များ ပုံဖော်ပြသခြင်းအတွက် သီးသန့် setting များ ပါဝင်ပါသည်။


.. _figure_rendering_vector:


.. figure:: img/options_rendering_vector.png
   :align: center


   Vector ပုံဖော်ပြသမှု setting များ
   

.. _global_simplification:

* |checkbox| :guilabel:`Enable Feature Simplification by Default for Newly Added Layers` (Default အနေဖြင့် အသစ် ထည့်သွင်းသော Layer များအတွက် Feature များကို ရိုးရှင်းအောင်လုပ်ခြင်း) ကို အမှန်ခြစ်ပြုလုပ်ခြင်းဖြင့် feature များ၏ ဂျီဩမေတြီကို ရိုးရှင်းအောင် ပြုလုပ်ပေး (ပိုနည်းသောမျဉ်းအဆစ်များ) ပြီး ရလဒ်အနေဖြင့် ၎င်းတို့ကို လျင်မြန်စွာ ပြသနိုင်မည် ဖြစ်ပါသည်။ ဤသို့ပြုလုပ်ခြင်းသည် (rendering inconsistencies) ပုံဖော်ပြသခြင်းကွဲလွဲမှုများ ဖြစ်စေနိုင်သည်ကို သတိပြုရန်လိုအပ်ပါသည်။ ရရှိနိုင်သော setting များမှာ-

  * :guilabel:`Simplification threshold` (ရိုးရှင်းမှု သတ်မှတ်ချက်) (တန်ဖိုးမြင့်လေ ပိုမိုရိုးရှင်းလေဖြစ်သည်) 
  * :guilabel:`Simplification algorithm` - ဤ option သည် feature များကို ရိုးရှင်းအောင် လုပ်ဆောင်ရာတွင်နှင့် ဂျီဩမေတြီများကို ပုံဖော်ပြသရာတွင် ပိုမိုမြန်ဆန်စွာဆောင်ရွက်စေပါသည်။ ၎င်းသည် ‌ဒေတာပံ့ပိုးသူ (data providers) များထံမှ ရရှိသည့် ဂျီဩမေတြီများကို ပြောင်းလဲသွားစေခြင်းမရှိပေ။ feature များ၏ ဂျီဩမေတြီကိုအသုံးပြုသည့် expression များအသုံးပြုသောအခါ (ဥပမာ- ဧရိယာတွက်ချက်ခြင်း) ထိုတွက်ချက်မှုများကို ရိုးရှင်းအောင် ပြင်ဆင်ထားသည့် ဂျီဩမေတြီတွင် မဟုတ်ဘဲ မူလဂျီဩမေတြီတွင်သာ ပြုလုပ်ရန် အရေးကြီးပါသည်။ ဤရည်ရွယ်ချက်အတွက် QGIS သည် algorithms သုံးခုအား ပံ့ပိုးထားပါသည်။ ၎င်းတို့မှာ 'Distance' (သတ်မှတ်ထားသည့်အကွာအဝေးနှင့်နီးသော အမှတ်များကိုဖျက်ခြင်း (default)၊ 'SnapToGrid' (ဂရစ်ကွက်များသို့ ဆွဲကပ်ခြင်း) နှင့် 'Visvalingam'  (အရေးမကြီးသော အမှတ်များကိုဖျက်ခြင်း) တို့ဖြစ်ကြပါသည်။
  * |unchecked| :guilabel:`Simplify on provider side if possible` (ဖြစ်နိုင်ပါက ပံ့ပိုးသူဘက်တွင် ရိုးရှင်းအောင် ပြုလုပ်ခြင်း) သည် ဂျီဩမေတြီများကို ပံ့ပိုးသူ (PostGIS ၊ Oracle...စသည်) ဘက်မှ ရိုးရှင်းအောင် ပြုလုပ်ခြင်းဖြစ်သည်။ အသုံးပြုသူဘက်မှ ရိုးရှင်းအောင် ပြုလုပ်ခြင်းနှင့်ကွာခြားချက်မှာ ၎င်းသည် ဂျီဩမေတြီကို အခြေခံထားသည့် တွက်ချက်မှုများကို သက်ရောက်စေမည်ဖြစ်သည်။ 
  * :guilabel:`Maximum scale at which the layer should be simplified (1:1 always simplifies)` (Layer ကို ရိုးရှင်းစေရန် ပြုလုပ်ရာတွင် ထားသင့်သည့် အမြင့်ဆုံးအချိုး (1:1 ဖြင့် အမြဲပြုလုပ်ခြင်း))


  .. note:: 
    Global setting အပြင် မည်သည့်သီးသန့် layer အတွက်မဆို ၎င်း၏ :menuselection:`Layer properties --> Rendering` menu မှတဆင့် feature များရိုးရှင်းအောင်ပြုလုပ်ခြင်းအတွက် သတ်မှတ်ပေးနိုင်ပါသည်။ 


* :guilabel:`Curve Segmentation` (မျဉ်းကွေးအပိုင်းများစိတ်ဖြာခြင်း)

  * :guilabel:`Segmentation tolerance` (အပိုင်းများစိတ်ဖြာခြင်းဆိုင်ရာ လက်ခံနိုင်မှု) - ဤ setting သည် စက်ဝန်းပိုင်းများပုံဖော်ပြသခြင်းနည်းလမ်းကို ထိန်းချုပ်ထားပါသည်။ အကြီးဆုံးထောင့်(ကပ်လျက်မျဉ်းဆစ်နှစ်ခုနှင့်မျဉ်းကွေးဗဟိုကြား ထောင့်ဒီဂရီ) သို့မဟုတ် အများဆုံးကွာခြားချက် (မျဉ်းဆစ်နှစ်ခု၏အပိုင်းနှင့် မျဉ်းကွေးကြား မြေပုံယူနစ်ဖြင့်တိုင်းတာထားသည့် အကွာအဝေး)သည်် **ပို၍ငယ်လေလေ**  ပုံဖော်ပြသရာတွင်အသုံးပြုမည့် မျဉ်းအပိုင်း (segment) များသည် **ပို၍ဖြောင့်တန်းလေလေ** ဖြစ်သည်။
  * :guilabel:`Tolerance type` (လက်ခံနိုင်မှုအမျိုးအစား) - ခန့်မှန်းခြေနှင့်မျဉ်းကွေးကြားရှိ *Maximum angle (အများဆုံးထောင့်)* သို့မဟုတ် *Maximum difference (အများဆုံးကွာခြားချက်)* ဖြစ်နိုင်ပါသည်။ 


Raster rendering settings (Raster ပုံဖော်ပြသခြင်း setting များ)
................................................................

|raster| :guilabel:`Raster` tab တွင် raster layer များကို ပုံဖော်ပြသရန်အတွက် သီးသန့် setting များ ပါဝင်ပါသည်။ 


.. _figure_rendering_raster:


.. figure:: img/options_rendering_raster.png
   :align: center


   Raster ပုံဖော်ပြသခြင်း setting များ

:guilabel:`Bands and Resampling` (လှိုင်းအလွှာများနှင့် ကြည်လင်ပြတ်သားမှုကို ပြောင်းလဲခြင်း) အောက်တွင်-

* :guilabel:`RGB band selection` (RGB လှိုင်းအလွှာရွေးချယ်ခြင်း) ဖြင့် အနီရောင်၊ အစိမ်းရောင်နှင့် အပြာရောင်‌ band (လှိုင်းအလွှာ) များအတွက် နံပါတ်များကို သတ်မှတ်နိုင်ပါသည်။
* :guilabel:`Zoomed in resampling` (Zoom ချဲ့ကြည့်လျှင် ကြည်လင်ပြတ်သားမှုပြောင်းလဲခြင်း) နှင့် :guilabel:`Zoomed out resampling` (Zoom ချုံ့ကြည့်လျှင် ကြည်လင်ပြတ်သားမှုပြောင်းလဲခြင်း) နည်းလမ်းများကို သတ်မှတ်နိုင်ပါသည်။ :guilabel:`Zoomed in resampling` အတွက် 'Nearest Neighbour'(အနီးစပ်ဆုံးနေရာ)၊ 'Bilinear'(အနီးဆုံးတန်ဖိုးလေးခု) နှင့် 'Cubic' (ကုဗသဏ္ဍာန်) ဟူ၍ ရွေးချယ်နိုင်သည့် နည်းလမ်းသုံးခုရှိပါသည်။ :guilabel:`Zoomed out resampling` အတွက် 'Nearest Neighbour' (အနီးစပ်ဆုံးနေရာ)နှင့် 'Average' (ပျမ်းမျှ) ဟူ၍ ရွေးချယ်နိုင်ပါသည်။ :guilabel:`Oversampling` တန်ဖိုးကိုလည်း သတ်မှတ်ပေးနိုင်ပါသည် (တန်ဖိုးများမှာ 0.0 နှင့် 99.99 ကြားဖြစ်ပြီး - တန်ဖိုးကြီးလျှင် QGIS အတွက် အလုပ်ပိုပိစေမည်ဖြစ်သည် - default တန်ဖိုးမှာ 2.0 ဖြစ်သည်)။
* |checkbox| :guilabel:`Early resampling` (ကြည်လင်ပြတ်သားမှုပြောင်းလဲခြင်းကို စောလျင်စွာဆောင်ရွက်ခြင်း) သည် အရင်းအမြစ်၏ resolution (ကြည်လင်ပြတ်သားမှု) ကို သိပြီးဖြစ်သော ပံ့ပိုးသူအဆင့် (provider level) ရှိ raster ပုံဖော်ပြသခြင်းကို တွက်ချက်ပေးနိုင်ပြီး QGIS ၏ စိတ်ကြိုက် style ပြင်ဆင်ခြင်းများအသုံးပြုခြင်းဖြင့် ပိုမိုကောင်းမွန်သော zoom ချဲ့ ပုံဖော်ပြသခြင်းကို ရရှိစေပါသည်။ :ref:`Interpretation method <interpretation>` (ဖြည့်သွင်းတွက်ထုတ်ပေးခြင်းနည်းလမ်း) တစ်ခုကို အသုံးပြု၍ထည့်သွင်းထားသည့် tile raster များအတွက် ပို၍လွယ်ကူစေပါသည်။ ထိုရွေးချယ်မှုကို layer အဆင့် (:guilabel:`Symbology` properties) တွင်လည်း သတ်မှတ်ပေးနိုင်ပါသည်။ 

:guilabel:`Contrast Enhancement` (အရောင်ကွဲပြားထင်ရှားမှုမြှင့်တင်ခြင်း) option များကို :guilabel:`Single band gray` ၊ :guilabel:`Multi band color (byte/band)` သို့မဟုတ် :guilabel:`Multi band color (>byte/band)` များတွင် အသုံးပြုနိုင်ပါသည်။ တစ်ခုချင်းစီအတွက် အောက်ပါအတိုင်း သတ်မှတ်နိုင်သည်-

* အသုံးပြုမည့် :guilabel:`Algorithm` တွင် 'No stretch' (ဖြန့်ထုတ်ခြင်းမရှိ)၊ 'Stretch to MinMax' (အနည်းဆုံးနှင့်အများဆုံးတန်ဖိုးများပေါ်မူတည်ပြီး ဖြန့်ထုတ်ခြင်း)၊ 'Stretch and Clip to MinMax' (ဖြန့်ထုတ်ပြီးနောက် အနည်းဆုံးနှင့်အများဆုံးတန်ဖိုးများကိုဖြတ်ထုတ်ခြင်း) သို့မဟုတ် 'Clip to MinMax'(အနည်းဆုံးအများဆုံးတန်ဖိုးများကိုဖြတ်ထုတ်ခြင်း) ဟူ၍ တန်ဖိုးများကို သတ်မှတ်နိုင်ပါသည်။ 
* အသုံးပြုမည့် :guilabel:`Limits (minimum/maximum)` (ကန့်သတ်ချက်)(အနည်းဆုံး/အများဆုံး) တွင် 'Cumulative pixel count cut' (တိုးလာသော pixel အရေအတွက် အဖြတ်)၊ 'Minimum/Maximum' (အနည်းဆုံး/အများဆုံး)၊ 'Mean +/- standard deviation' (ပျမ်းမျှကိန်း +/- စံသွေဖယ်ကိန်း) ကဲ့သို့ တန်ဖိုးများရှိနိုင်ပါသည်။

:guilabel:`Contrast Enhancement` (အရောင်ကွဲပြားထင်ရှားမှုမြှင့်တင်ခြင်း) option များတွင် အောက်ပါတို့လည်း ပါဝင်ပါသည်-
* :guilabel:`Cumulative pixel count cut limits` (တိုးလာသော pixel အရေအတွက် အဖြတ် ကန့်သတ်ချက်များ)
* :guilabel:`Standard deviation multiplier` (စံသွေဖယ်ကိန်းမြှောက်ကိန်း)


.. _canvas_legend_options:

Canvas and Legend Settings (မြေပုံမျက်နှာပြင်နှင့် ရည်ညွှန်းချက် setting များ)
-------------------------------------------------------------------------------

.. _figure_canvas_legend:


.. figure:: img/options_canvas_legend.png
   :align: center


   မြေပုံမျက်နှာပြင်နှင့် ရည်ညွှန်းချက် setting များ

ဤဂုဏ်ရည်အချက်များတွင် အောက်ပါတို့ကို သတ်မှတ်နိုင်ပါသည်- 

* **Default map appearance (Default မြေပုံအသွင်အပြင်) (Project ၏ property များဖြင့် အစားထိုးပြင်ဆင်ရေးသားခြင်း)** တွင် :guilabel:`Selection color` (အ‌ရောင်ရွေးချယ်ခြင်း) နှင့် :guilabel:`Background color` (နောက်ခံအရောင်) ဟူ၍ နှစ်မျိုးပါဝင်ပါသည်။

* **Layer ရည်ညွှန်းချက်** ဖြင့် အပြန်အလှန်လုပ်ဆောင်ခြင်း-

  * :guilabel:`Double click action in legend` |selectString| (ရည်ညွှန်းချက်တွင် click နှစ်ချက်နှိပ်၍ ဆောင်ရွက်ခြင်း)။ 'Open layer properties' (Layer property များဖွင့်ခြင်း)၊ 'Open attribute table' (attribute ဇယားဖွင့်ခြင်း) သို့မဟုတ် 'Open layer styling dock' (Layer style ပြင်ဆင်ရန်ဖွင့်ခြင်း) များကို double-click နှိပ်၍ ပြုလုပ်နိုင်ပါသည်။ 
  * |unchecked| :guilabel:`Show feature count for newly added layers` (အသစ်ထည့်သွင်းသော Layer များ၏ feature အရေအတွက်ဖော်ပြခြင်း) - :guilabel:`Layers` panel ထဲရှိ Layer အမည်ဘေးတွင် feature များ၏ အရေအတွက်ကို ဖော်ပြနေမည်ဖြစ်ပါသည်။ အတန်းအစားများ၏ feature အရေအတွက် ရှိပါကလည်း ဖော်ပြနေမည်ဖြစ်ပါသည်။ ၎င်း၏ feature အရေအတွက်ပြသခြင်းကို အဖွင့်/အပိတ်ပြုလုပ်ရန် Layer ပေါ်တွင် right-click နှိပ်၍ လုပ်ဆောင်နိုင်သည်။
  * |unchecked| :guilabel:`Display classification attribute names` (အမျိုးအစားခွဲခြားထားသည့် attribute အမည်များဖော်ပြခြင်း) ကိုအမှန်ခြစ်၍ Layers panel ထဲတွင် ဖော်ပြနိုင်သည်၊ ဥပမာ- categorized (အမျိုးအစားအလိုက်ပုံဖော်ပြသသော) သို့မဟုတ် rule-based renderer (စည်းမျဉ်းအခြေခံ ပုံဖော်ပြသသောအရာ) တစ်ခုအသုံးပြုထားသောအခါ။ (နောက်ထပ်အချက်အလက်များအတွက် :ref:`vector_style_menu` တွင် ဝင်ရောက်ကြည့်ရှုနိုင်ပါသည်) 
  * :guilabel:`WMS getLegendGraphic Resolution`
  * :guilabel:`Layers` panel တွင် ပြသမည့် သင်္ကေတအရွယ်အစားကိုထိန်းချုပ်ရန် :guilabel:`Minimum` (အသေးဆုံး) နှင့် :guilabel:`Maximum legend symbol size` (အကြီးဆုံးရည်ညွှန်းချက်သင်္ကေတအရွယ်အစား)
* Layer များ :ref:`map tips (မြေပုံအကြံပြုချက်များ) <maptips>` ပြသမှု၏ မီလီစက္ကန့်ဖြင့် :guilabel:`Delay` (ကြန့်ကြာချိန်)
* QGIS သည် |checkbox| :guilabel:`Respect screen DPI` (မျက်နှာပြင်၏ DPI (Dots per inch)) ကို ထည့်သွင်းစဉ်းစားသင့်/မသင့်။ ၎င်းကို အမှန်ခြစ်ပြုလုပ်ထားပါက QGIS သည် မော်နီတာ၏ DPI ပေါ်မူတည်၍ မြေပုံမျက်နှာပြင်ကို တိကျသည့်စကေးဖြင့် ဖော်ပြမည်ဖြစ်သည်။ အရွယ်အစားတိကျစွာသတ်မှတ်ထားသည့် သင်္ကေတများကိုလည်း ၎င်းစကေးအတိုင်း တိကျစွာပုံဖော်ပြသမည်ဖြစ်သည်။ ဥပမာ- ၁၀ မီလီမီတာအရွယ်အစားရှိသော သင်္ကေတသည် မျက်နှာပြင်တွင်လည်း ၁၀ မီလီမီတာဖြင့် ပြသနေပေလိမ့်မည်။ သို့သော်လည်း မြေပုံမျက်နှာပြင်ရှိ အညွှန်းစာလုံးအရွယ်အစားသည် QGIS ၏ UI သို့မဟုတ် အခြားသော application များတွင်မူ ကွဲပြားနေပေလိမ့်မည်။ အကယ်၍ ဤ setting ကို ပိတ်ထားမည်ဆိုပါက QGIS သည် system ၏ အခြားသော application များနှင့် ကိုက်ညီမည့် operating system (ကွန်ပျူတာလုပ်ဆောင်သည့်စနစ်) ၏ DPI အတိုင်းသာ အသုံးပြုသွားမည်ဖြစ်ပါသည်။ သို့ရာတွင် မြေပုံမျက်နှာပြင်စကေးနှင့် သင်္ကေတများ၏အရွယ်အစားသည် မျက်နှာပြင်ပေါ်တွင် တိကျမှုရှိလိမ့်မည်မဟုတ်ပေ။ အထူးသဖြင့် DPI မြင့်သောမျက်နှာပြင်များတွင် သင်္ကေတများသည် အလွန်သေးငယ်သယောင်ဖြစ်နေမည်ဖြစ်သည်။


  အကောင်းဆုံးအတွေ့အကြုံကိုရရှိစေရန် အကြံပြုရသော် မော်နီတာများစွာ သို့မဟုတ် မတူညီသောမော်နီတာအမျိုးမျိုးကို အသုံးပြု၍ အမြင်အရ အရည်အသွေးကောင်းသည့် မြေပုံများကို ပြင်ဆင်လိုသည့်အခါ |checkbox| :guilabel:`Respect screen DPI` ကို ဖွင့်ထားရန် အကြံပြုပါသည်။ |checkbox| :guilabel:`Respect screen DPI` ကို ပိတ်ထားခြင်းသည် စာလုံးအရွယ်အစားများကို အခြား application များနှင့် ကိုက်ညီစေနိုင်သောကြောင့် ကွန်ပျူတာဖန်သားပြင်ပေါ်တွင်သာ အသုံးပြုရန် ရည်ရွယ်သည့် မြေပုံများရေးဆွဲခြင်းအတွက် ပိုမိုသင့်တော်သော ရလာဒ်များကို ထုတ်ပေးပါလိမ့်မည်။

.. note:: 
  :guilabel:`Respect screen DPI` setting သည် Layout များကို ပုံဖော်ပြသရာတွင် သက်ဆိုင်မှုမရှိပေ။ ၎င်းသည် ရည်ရွယ်သည့် output device အတွက် သတ်မှတ်ထားသည့် DPI အတိုင်းသာ ဆောင်ရွက်သွားမည်ဖြစ်သည်။ ထို့အပြင် ဤ setting သည် ကွန်ပျူတာ OS မှပေးပို့သော screen (မျက်နှာပြင်) DPI ကိုအသုံးပြုသောကြောင့် ပြသခြင်းအားလုံးအတွက် တိကျမှုမရှိနိုင်သည်ကို သတိပြုပါ။


.. index:: Map tools
.. _maptools_options:


Map tools Settings (မြေပုံကိရိယာတန်ဆာပလာ setting များ)
-------------------------------------------------------

.. _figure_map_tools_settings:


.. figure:: img/options_map_tools.png
   :align: center


   မြေပုံကိရိယာတန်ဆာပလာ setting များ

ဤ tab တွင် :ref:`Identify tool <identify>` ၏လုပ်ဆောင်ပုံနှင့်သက်ဆိုင်သည့် ရွေးချယ်စရာအချို့ရှိပါသည်။

* :guilabel:`Search radius for identifying features and displaying map tips` (feature များဖော်ထုတ်ခြင်းနှင့် မြေပုံအကြံပြုချက်များ ပြသခြင်းတို့အတွက် ရှာဖွေမှုအချင်းဝက်) သည် လက်ခံနိုင်မှုအကွာအဝေး တစ်ခုဖြစ်ပြီး ထိုအကွာအဝေးအတွင်း click နှိပ်နေသမျှ identify tool သည် ရလာဒ်များကို ဖော်ပြနေမည်ဖြစ်ပါသည်။ 
* :guilabel:`Highlight color` (ထင်ရှားအောင်ပြသည့်အရောင်) သည် identify ပြုလုပ်ထားသည့် feature ကို မည်သည့်အရောင်ဖြင့် highlight (ထင်ရှားအောင်ပြသ) ပြုလုပ်သင့်သည်ကို ရွေးချယ်နိုင်စေပါသည်။ 
* :guilabel:`Buffer` (ကြားခံ) သည် identify highlight ပြုလုပ်ထားသည့်အနားသတ်မျဉ်းမှ ပုံဖော်ပြသခြင်းလုပ်ဆောင်မည့် ကြားခံအကွာအဝေးကို ဆုံးဖြတ်ပေးပါသည်။ 
* :guilabel:`Minimum width` (အနည်းဆုံးအထူ) သည် highlight ပြုလုပ်ထားသည့် အရာ၏ အနားသတ်မျဉ်းအထူကို သတ်မှတ်ပေးသည်။ 


**Measure tool** (**တိုင်းတာခြင်းကိရိယာ**)

* တိုင်းတာခြင်းကိရိယာများအတွက် :guilabel:`Rubberband color` (ရာဘာမျဉ်းအရောင်) ကို သတ်မှတ်ပါ။
* :guilabel:`Decimal places` (ဒဿမကိန်းအရေအတွက်) ကို သတ်မှတ်ပါ။
* |checkbox| :guilabel:`Keep base unit` ကို အမှန်ခြစ်ပြုလုပ်ခြင်းဖြင့် တန်ဖိုးကြီးကိန်းဂဏန်းများအဖြစ်သို့ အလိုအလျောက်ပြောင်းလဲခြင်းကို ကာကွယ်နိုင်သည်။ (ဥပမာ-မီတာမှ ကီလိုမီတာ)
* :guilabel:`Preferred distance units` (နှစ်သက်သည့်အကွာအဝေးယူနစ်) - ရွေးချယ်စရာများမှာ  'Meters' (မီတာ)၊ 'Kilometers' (ကီလိုမီတာ)၊ 'Feet' (ပေ)၊ 'Yards' (ကိုက်)၊ 'Miles' (မိုင်)၊ 'Nautical Miles' (ရေမိုင်)၊ 'Centimeters' (စင်တီမီတာ)၊ 'Millimeters' (မီလီမီတာ)၊ 'Degrees' (ဒီဂရီ) သို့မဟုတ် 'Map Units' (မြေပုံယူနစ်) တို့ဖြစ်ပါသည်။
* :guilabel:`Preferred area units` (နှစ်သက်သည့်ဧရိယာယူနစ်) - ရွေးချယ်စရာများမှာ 'Square meters' (စတုရန်းမီတာ)၊ 'Square kilometers' (စတုရန်းကီလိုမီတာ)၊ 'Square feet' (စတုရန်းပေ)၊ 'Square yards' (စတုရန်းကိုက်)၊ 'Square miles' (စတုရန်းမိုင်)၊ 'Hectares' (ဟက်တာ)၊ 'Acres' (ဧက)၊ 'Square nautical miles' (စတုရန်းရေမိုင်)၊ 'Square centimeters' (စတုရန်းစင်တီမီတာ)၊ 'Square millimeters' (စတုရန်းမီလီမီတာ)၊ 'Square degrees' (စတုရန်းဒီဂရီ) သို့မဟုတ် 'Map Units' (မြေပုံယူနစ်) တို့ဖြစ်ပါသည်။
* :guilabel:`Preferred angle units` (နှစ်သက်သည့်ထောင့်ယူနစ်) - ရွေးချယ်စရာများမှာ  'Degrees' (ဒီဂရီ)၊ 'Radians' (ရေဒီယမ်)၊ 'Gon/gradians' (ဂွန်/ဂရာဒီယမ်)၊ 'Minutes of arc' (မိနစ်)၊ 'Seconds of arc' (စက္ကန့်)၊ 'Turns/revolutions' (အလှည့်)၊ milliradians (မီလီရေဒီယမ်) (SI အဓိပ္ပါယ်သတ်မှတ်ချက်) သို့မဟုတ် mil(မီလ်)(နေတိုးအဖွဲ့/စစ်တပ်သုံး အဓိပ္ပါယ်သတ်မှတ်ချက်) ဟူ၍ ဖြစ်ပါသည်။ 


**Coordinate and Bearing Display** (**ကိုဩဒိနိတ်နှင့် ရပ်ညွှန်းဖော်ပြချက်**)

ဤအပိုင်းတွင် :guilabel:`Configure` (ပြင်ဆင်သတ်မှတ်ရန်) နည်းလမ်းများကို ဖော်ပြထားပါသည်-

* :guilabel:`Default coordinate format for new projects` (Project အသစ်များအတွက် default ကိုဩဒိနိတ်ပုံစံ)သည် QGIS အခြေအနေပြဘားရှိ :guilabel:`Coordinates` (ကိုဩဒိနိတ်များ) box နှင့် |identify| :sup:`Identify features` tool ၏ ရလာဒ်များ၏ :guilabel:`Derived` (ဆင့်ပွား) ကဏ္ဍတွင် ဖော်ပြထားသည့်အတိုင်းဖြစ်သည်။ 
* :guilabel:`Default bearing format for new projects` (Project အသစ်များအတွက် default ရပ်ညွှန်းပုံစံ) သည် မြေပုံမျက်နှာပြင်၏လားရာအတွက် နှင့် |measureBearing| :sup:`Measure bearing` (ရပ်ညွှန်းတိုင်းတာခြင်း) tool မှရလာဒ်အတွက် အခြေအနေပြဘားတွင် ဖော်ပြထားသည့်အတိုင်းဖြစ်သည်။

ဤရွေးချယ်မှုများကို :ref:`project level (ပရောဂျက်အဆင့်) <coordinate_and_bearing>` တွင် အစားထိုးပြင်ဆင်သတ်မှတ်နိုင်ပါသည်။ 


**Panning and zooming** (**မြေပုံရွှေ့ကြည့်ခြင်းနှင့် ချုံ့/ချဲ့ကြည့်ခြင်း**)

* ချုံ့/ချဲ့ကြည့်နိုင်သည့် tool များ သို့မဟုတ် မောက်စ်ဘီးအတွက် :guilabel:`Zoom factor` (ချုံ့/ချဲ့ကြည့်နိုင်သည့်ပမာဏ) တစ်ခုကိုသတ်မှတ်နိုင်ပါသည်။ 


.. _predefinedscales:


**Predefined scales** (**ကြိုတင်သတ်မှတ်ထားသည့် စကေးများ**)

ဤနေရာတွင် စကေးနှင့်ဆက်စပ်သော drop-down widget များဖြစ်သည့် အခြေအနေပြဘားရှိ :guilabel:`Scale` (စကေး)၊ မြင်နိုင်သည့်စကေးရွေးချယ်ပေးသည့်အရာ သို့မဟုတ် နှစ်ဖက်မြင်မြေပုံမြင်ကွင်း (2D map view) setting များတွင် default အားဖြင့် ပြသမည့် ကြိုတင်သတ်မှတ်ထားသည့်စကေးများစာရင်းတစ်ခုကို တွေ့နိုင်ပါသည်။ |symbologyAdd| (ထပ်ထည့်ခြင်း) နှင့် |symbologyRemove| (ဖယ်ရှားခြင်း) ခလုတ်တို့ကို နှိပ်၍ မိမိကိုယ်ပိုင်စကေးများကို ထည့်ခြင်း၊ ဖျက်ခြင်းတို့ကို ပြုလုပ်နိုင်ပါသည်။ စကေးများကို ``.XML`` ဖိုင်အမျိုးအစားဖြင့် ထည့်သွင်းခြင်း သို့မဟုတ် ထုတ်ယူခြင်းတို့ကိုလည်း ဆောင်ရွက်နိုင်ပါသည်။ ထို့အပြင် မိမိပြုလုပ်ထားသော ပြောင်းလဲမှုများကို ပယ်ဖျက်နိုင်ပြီး မူလကြိုတင်သတ်မှတ်ထားသည့် စာရင်းသို့ ပြန်လည်ပြောင်းလဲနိုင်ပါသည်။

Project property များ dialog မှလည်း widget များထဲရှိ အားလုံးအတွက်အသုံးပြုနိုင်သည့် (global) စကေးများကို အစားထိုးပြင်ဆင်၍ ကိုယ်ပိုင်စကေးများစာရင်းကို သတ်မှတ်နိုင်ပါသည်။ 


.. index:: Digitizing configuration
.. _digitizing_options:


Digitizing settings (ဒီဂျစ်တယ်ပုံစံသို့ပြောင်းလဲခြင်း/မြေပုံအချက်အလက်ရေးဆွဲခြင်း setting များ)
...............................................................................................

.. _figure_digitizing_settings:

.. figure:: img/options_digitizing.png
   :align: center

   Digitizing setting များ


ဤ tab တွင် :ref:`editing vector layer (vector layer ပြင်ဆင်တည်းဖြတ်ခြင်း) <editingvector>` (attribute များနှင့် ဂျီဩမေတြီ) ပြုလုပ်ရာတွင် အထွေထွေ setting များကို သတ်မှတ်နိုင်ပါသည်။ 


**Feature creation** (**Feature ဖန်တီးခြင်း**)

* |checkbox| :guilabel:`Suppress attribute form pop-up after feature creation` (Feature ကို ဖန်တီးပြီးနောက် attribute form ပေါ်လာခြင်းကို ဖုံးဖိထားခြင်း) - Layer property များ dialog တစ်ခုချင်းစီတွင် ဤရွေးချယ်မှုကို အစားထိုးလုပ်ဆောင်နိုင်သည်။
* |checkbox| :guilabel:`Reuse last entered attribute values` (နောက်ဆုံးထည့်သွင်းခဲ့သည့်အချက်အလက်တန်ဖိုးများကိုပြန်လည်အသုံးပြုခြင်း) - Attribute တိုင်းတွင်နောက်ဆုံးအသုံးပြုခဲ့သည့်တန်ဖိုးကို မှတ်ထားပြီး digitize ပြုလုပ်မည့် နောက်ထပ် feature အသစ်အတွက် default အနေဖြင့် အသုံးပြုနိုင်ပါသည်။ ၎င်းသည် Layer တစ်ခုချင်းစီအတွက် အလုပ်ဖြစ်ပါသည်။ ထို့အပြင် ဤလုပ်ဆောင်ချက်ကို field တစ်ခုချင်းပေါ်မူတည်၍ ထိန်းချုပ်နိုင်ပါသည်။ (:ref:`configure_field` တွင် ကြည့်ရှုနိုင်ပါသည်)။
* :guilabel:`Validate geometries` (ဂျီဩမေတြီများအတည်ပြုခြင်း) - အဆစ် (node) များစွာရှိနေသည့် ရှုပ်ထွေးသော line များနှင့် polygon များကို တည်းဖြတ်ခြင်းသည် ပုံဖော်ပြသရာတွင် အလွန်ကြန့်ကြာစေပါသည်။ အဘယ်ကြောင့်ဆိုသော် QGIS ရှိ မူရင်းအတည်ပြုခြင်းလုပ်ငန်းစဉ်များသည် အချိန်များစွာ ကြာမြင့်သောကြောင့် ဖြစ်ပါသည်။ ပုံဖော်ရာတွင် ပိုမိုမြန်ဆန်စေရန် GEOS ဂျီဩမေတြီအတည်ပြုခြင်း (GEOS 3.3 မှစတင်သည်) ကို ရွေးချယ်ခြင်း သို့မဟုတ် ပိတ်ထားခြင်းကိုလုပ်ဆောင်နိုင်မည်ဖြစ်သည်။ GEOS ဂျီဩမေတြီအတည်ပြုခြင်းသည် ပို၍မြန်ဆန်သော်လည်း ဆိုးကျိုးအနေဖြင့် ပထမဆုံးတွေ့ရှိသည့် ဂျီဩမေတြီပြဿနာကိုသာလျှင် ဖော်ပြမည်ဖြစ်သည်။ 

ရွေးချယ်မှုအပေါ်မူတည်၍ ဂျီဩမေတြီအမှားများကို အစီရင်ခံမှုများသည် အမျိုးမျိုးကွဲပြားနိုင်ပါသည်။ (:ref:`typesofgeomerrors` (ဂျီဩမေတြီအမှားဖော်ပြချက်စာတိုအမျိုးအစားများနှင့်၎င်းတို့၏အဓိပ္ပါယ်များ) တွင် ကြည့်ရှုနိုင်ပါသည်။)
* သုံးဖက်မြင် feature (3D feature) အသစ်များကို ဖန်တီးသည့်အခါ အသုံးပြုမည့် :guilabel:`Default Z value` (မူရင်း Z တန်ဖိုး)။


**Rubberband**

* Rubberband :guilabel:`Line width` (မျဉ်းအထူ) ၊ :guilabel:`Line color` (မျဉ်းအရောင်) နှင့် :guilabel:`Fill color` (ဖြည့်ရမည့်အရောင်) ကို သတ်မှတ်နိုင်သည်။ 
* :guilabel:`Don't update rubberband during vertex editing` (မျဉ်းအဆစ်များကို တည်းဖြတ်ပြင်ဆင်နေစဉ် rubberband ကို update မပြုလုပ်ပါနှင့်) 


**Snapping** (**ဆွဲကပ်ခြင်း**)

* |checkbox| :guilabel:`Enable snapping by default` (Default အနေဖြင့် ဆွဲကပ်ခြင်းကို အသုံးပြုနိုင်စေခြင်း) ကို အမှန်ခြစ်ပြုလုပ်ပါက project တစ်ခုကို ဖွင့်လိုက်သည့်အခါ snapping ကို အသုံးပြုနိုင်အောင်ဖွင့်ပေး (activate) မည်ဖြစ်သည်။ 
* :guilabel:`Default snap mode`  |selectString| (Default ဆွဲကပ်နည်းလမ်း) ကိုသတ်မှတ်နိုင်သည်။ ('Vertex' (မျဉ်းဆစ်) ၊ 'Segment' (မျဉ်းပိုင်း) ၊ 'Centroid' (အလယ်ဗဟို) ၊ 'Middle of segments'(မျဉ်းပိုင်းများ၏အလယ်) ၊ Line endpoints' (မျဉ်းကြောင်းဆုံးမှတ်) ၊ 'Area' (ဧရိယာ))
* :guilabel:`Default snapping tolerance` (Default ဆွဲကပ်ခြင်း လက်ခံနိုင်မှု) ကို မြေပုံယူနစ် သို့မဟုတ် pixel များဖြင့် သတ်မှတ်နိုင်သည်။
* :guilabel:`Search radius for vertex edits` (မျဉ်းအဆစ်ကို ပြင်ဆင်တည်းဖြတ်ရန်အတွက် ရှာဖွေမှုအချင်းဝက်) ကို မြေပုံယူနစ် သို့မဟုတ် pixel များဖြင့် သတ်မှတ်နိုင်သည်။
* :guilabel:`Display main dialog as (restart required)` (အဓိက dialog ကို...အနေဖြင့် ပြသခြင်း (ပြန်လည်စတင်ရန် လိုအပ်သည်)) - အဆင့်မြင့် ဆွဲကပ်ခြင်း dialog (Advanced Snapping dialog) ကို 'Dialog' သို့မဟုတ် 'Dock' အနေဖြင့် ပြသမည်/မပြသမည်ကို သတ်မှတ်ပေးနိုင်ပါသည်။ 
* :guilabel:`Snapping marker color` (ဆွဲကပ်အမှတ်အသား၏ အရောင်)
* |checkbox| :guilabel:`Show snapping tooltips` (ဆွဲကပ်ခြင်း tool အကြံပြုချက်များပြသခြင်း) - ဆွဲကပ်မည့် feature ပါဝင်သော layer အမည်ကို ဖော်ပြနေမည်ဖြစ်သည်။ Feature များစွာ ထပ်နေသည့်အခါမျိုးတွင် အသုံးဝင်ပါသည်။
* |checkbox| :guilabel:`Enable snapping on invisible features (not shown on the map canvas)` (မမြင်နိုင်သည့် feature များတွင် ဆွဲကပ်ခြင်း (မြေပုံမျက်နှာပြင်ပေါ်တွင် ပြသထားခြင်းမရှိသော))


**Vertex markers** (**မျဉ်းအဆစ် အမှတ်အသားများ**)

* |checkbox| :guilabel:`Show markers only for selected features` (ရွေးချယ်ထားသည့် feature များအတွက် သာလျှင် marker များကိုပြသခြင်း)
* မျဉ်းအဆစ်၏ :guilabel:`Marker style` |selectString| ကိုသတ်မှတ်ပါ ('Cross (ကြက်ခြေခတ်)' (default) ၊ 'Semi transparent circle' (တစ်ပိုင်းတစ်စဖောက်ထွင်းမြင်ရသည့်စက်ဝိုင်း) သို့မဟုတ် 'None' (မည်သည်မှမဟုတ်))
* မျဉ်းအဆစ်၏ :guilabel:`Marker size (in millimeter)` (marker အရွယ်အစား (မီလီမီတာဖြင့်)) ကိုသတ်မှတ်ပါ။


**Curve offset tool** (**မျဉ်းကွေးအရွေ့ tool**)

အောက်ဖော်ပြပါ ရွေးချယ်စရာ ၃ မျိုးသည် :ref:`sec_advanced_edit` ထဲရှိ |offsetCurve| :sup:`Offset Curve` (မျဉ်းကွေးအရွေ့) tool ကို ရည်ညွှန်းပါသည်။ အမျိုးမျိုးသော setting များဖြင့် line offset (လိုင်းအရွေ့) ၏ပုံသဏ္ဍာန်ကို ပြောင်းလဲနိုင်ပါသည်။ ဤရွေးချယ်မှုများသည် GEOS 3.3 မှ စတင်အသုံးပြုနိုင်မည်ဖြစ်သည်။

* :guilabel:`Join style` (ဆက်သည့်စတိုင်လ်) - 'Round' (စောင်းလုံး)၊ 'Miter' (စောင်းတိ) သို့မဟုတ်  'Bevel' (စောင်းသတ်)
* :guilabel:`Quadrant segments` (စက်ဝိုင်း၏လေးပုံတစ်ပုံ မျဉ်းပိုင်းများ)
* :guilabel:`Miter limit` (Miter ကန့်သတ်ချက်) 


**Tracing** (**လမ်းကြောင်းအတိုင်းလိုက်ခြင်း**)

|checkbox| :guilabel:`Convert tracing to curve` (လမ်းကြောင်းအတိုင်းလိုက်ခြင်းကို မျဉ်းကွေးအဖြစ်ပြောင်းလဲခြင်း) ကိုသုံး၍ digitize ပြုလုပ်စဉ်တွင် မျဉ်းကွေးအပိုင်းများကို ဖန်တီးနိုင်ပါသည်။ သို့သော် ဒေတာပံ့ပိုးသူမှ ထို feature ကိုပံ့ပိုးပေးရန် လိုအပ်ပါသည်။


.. index:: 3D
.. _3d_options:


3D settings (သုံးဖက်မြင် setting များ)
---------------------------------------

.. _figure_3d_options:

.. figure:: img/options_3d.png
   :align: center

   သုံးဖက်မြင် setting များ

|3d| :guilabel:`3D` menu တွင် မည်သည့် :guilabel:`3D Map view` (သုံးဖက်မြင်မြေပုံမြင်ကွင်း) အတွက်မဆို အသုံးပြုမည့် default setting အချို့ကို ပြင်ဆင်သတ်မှတ်နိုင်ပါသည်။ ၎င်းတို့သည် :guilabel:`Default Camera Settings` (ပုံမှန်ကင်မရာ setting များ) ကို ကိုးကားနိုင်ပါသည်-

* :guilabel:`Projection type` (အရိပ်ချစနစ်အမျိုးအစား) သည် သုံးဖက်မြင်မြင်ကွင်းကို အောက်ပါမြင်ကွင်းတစ်ခုဖြင့် ကြည့်ရှုစေနိုင်ပါသည်-

  * :guilabel:`Perspective projection` (ရှု‌ထောင့်ဆိုင်ရာ အရိပ်ချခြင်း) (default) - ပြိုင်မျဉ်းများကို အကွာအဝေးတစ်ခုတွင် တွေ့ဆုံစေပြီး အရာဝတ္ထုများသည် ကင်မရာမှ အကွာအဝေး ဝေးကွာလေလေ အရွယ်အစားကျုံ့သွားလေလေ တွေ့ရမည် ဖြစ်သည်။ 
  * သို့မဟုတ် :guilabel:`Orthogonal projection` (ထောင့်မှန် အရိပ်ချခြင်း) - ပြိုင်မျဉ်းများကို အပြိုင်သဏ္ဍာန်ဖြင့် တွေ့မြင်ရပြီး အရာဝတ္ထုများသည်လည်း အကွာအဝေးနှင့်သက်ဆိုင်မှုမရှိဘဲ တူညီသောအရွယ်အစားအတိုင်းသာ တွေ့ရမည်ဖြစ်သည်။ 
* ကင်မရာ၏ :guilabel:`Field of view` (မြင်ကွင်း) - ရှုထောင့်ဆိုင်ရာအရိပ်ချခြင်း နှင့်သာ သက်ဆိုင်ပြီး ၎င်းသည် လက်ရှိဒေါင်လိုက်မြင်ကွင်းကို ဒီဂရီဖြင့် သတ်မှတ်ခြင်းဖြစ်သည်။ ၎င်းသည် ကင်မရာမှ မြင်နိုင်သော မြင်ကွင်းပမာဏကို ဆုံးဖြတ်ပေးပြီး ပုံမှန်အားဖြင့် တန်ဖိုးသည် 45\° ဖြစ်ပါသည်။ 
* :guilabel:`Navigation mode` (ညွှန်ပြခြင်းနည်းလမ်း) - သုံးဖက်မြင်မြင်ကွင်းဖြင့် အပြန်အလှန်ဆောင်ရွက်နိုင်သည့် နည်းလမ်းအမျိုးမျိုးကို ပံ့ပိုးပေးပါသည်။ ရရှိနိုင်သည့် နည်းလမ်းများမှာ- 

  * :guilabel:`Terrain based` (မြေမျက်နှာသွင်ပြင်ကို အခြေခံထားသော) - မြင်ကွင်းကို ညွှန်ပြနေသည့်အတိုင်း ကင်မရာသည် မြေမျက်နှာသွင်ပြင်ပေါ်ရှိ ပုံသေတည်နေရာတစ်ခု၏ ပတ်လည်တဝိုက်ကို ပြသမည်ဖြစ်ပါသည်။ 
  * :guilabel:`Walk mode (first person)` (လမ်းလျှောက်နည်းလမ်း) (ပထမလူ)

  ရွေးချယ်ထားသည့် နည်းလမ်းပေါ်မူတည်၍ :ref:`navigation commands <3d_navigation>` (ညွှန်ပြသည့် စေခိုင်းချက်များ) သည် ကွဲပြားမှုရှိပါသည်။ 
* :guilabel:`Movement speed` (ရွေ့လျားနှုန်း)
* :guilabel:`Invert vertical axis` (ဒေါင်လိုက်ဝင်ရိုးပြောင်းပြန်ပြောင်းလဲခြင်း) - ဒေါင်လိုက်ဝင်ရိုးရွေ့လျားမှုများ ၎င်းတို့၏ ပုံမှန်အနေအထားမှ ပြောင်းပြန်လှည့်သင့်/မသင့်ကို ထိန်းချုပ်ပေးခြင်းဖြစ်သည်။ :guilabel:`Walk mode` (လမ်းလျှောက်နည်းလမ်း) ဖြင့် ပြုလုပ်သောရွေ့လျားမှုများတွင်သာ သက်ရောက်မှုရှိမည်ဖြစ်ပြီး ၎င်းကို အောက်ပါအတိုင်း သတ်မှတ်နိုင်ပါသည်- 

  * :guilabel:`Never` (မပြောင်းလဲပါ)
  * :guilabel:`Only when dragging` (ဖိဆွဲမှသာပြောင်းလဲခြင်း) - ကင်မရာလှည့်ထောင့်ကို click နှိပ်၍ဖိဆွဲမှသာ ဒေါင်လိုက်ရွေ့လျားမှုကို ပြောင်းပြန်ဖြစ်စေပါသည်။
  * :guilabel:`Always` (အမြဲတမ်း) - ကင်မရာရွေ့လျားမှုကို :kbd:`~` ကီးကိုနှိပ်၍ ပိတ်ထားသောအခါတွင်ဖြစ်စေ၊ click နှိပ်၍ ဖိဆွဲသောအခါတွင်ဖြစ်စေ ရွေ့လျားမှုကို ပြောင်းပြန်ဖြစ်စေမည်ဖြစ်ပါသည်။ 


.. index:: Colors
.. _colors_options:


Colors settings (အရောင် setting များ)
--------------------------------------

.. _figure_colors_options:

.. figure:: img/options_colors.png
   :align: center

   အရောင် setting များ

ဤ menu တွင် :ref:`color selector widget (အရောင်ရွေးချယ်ပေးသည့် widget) <color_widget>` ကို အသုံးပြု၍ QGIS တွင် အသုံးပြုခဲ့သည့် အရောင်များကို ဖန်တီးခြင်းနှင့် မွမ်းမံပြင်ဆင်ခြင်းများ ပြုလုပ်နိုင်ပါသည်။ အောက်ပါတို့မှ ရွေးချယ်နိုင်ပါသည်-

* :guilabel:`Recent colors` (မကြာသေးမီက အသုံးပြုခဲ့သည့်အရောင်များ) သည် မကြာသေးမီက အသုံးပြုခဲ့သည့် အရောင်များကို ဖော်ပြနေမည်ဖြစ်ပါသည်။ 
* :guilabel:`Standard colors` (စံအရောင်များ) သည် အရောင်များ၏ default palette ကို ဖော်ပြခြင်းဖြစ်သည်။
* :guilabel:`Project colors` (Project အရောင်များ) သည် လက်ရှိ project တွင် အသုံးပြုမည့် အရောင်များအစုတစ်ခုဖြစ်သည်။ (:ref:`default_styles_properties` တွင် အသေးစိတ်လေ့လာနိုင်ပါသည်။)
* :guilabel:`New layer colors` (Layer အသစ်အရောင်များ) သည် Layer အသစ်များကို QGIS ထဲသို့ထည့်သွင်းသည့်အခါ default အနေဖြင့် အသုံးပြုမည့်အရောင်များအစုတစ်ခုဖြစ်သည်။
* သို့မဟုတ် palette combobox ဘေးရှိ :guilabel:`...` ခလုတ်ကို အသုံးပြု၍ စိတ်ကြိုက်အရောင်ကွက် (များ)ကို ဖန်တီးခြင်း သို့မဟုတ် ထည့်သွင်းခြင်းများ ပြုလုပ်နိုင်ပါသည်။ 

ပုံမှန်အားဖြင့် :guilabel:`Recent colors` (မကြာသေးမီက အသုံးပြုခဲ့သည့်အရောင်များ)၊ :guilabel:`Standard colors` (စံအရောင်များ)နှင့် :guilabel:`Project colors` (Project အရောင်များ) များကို အရောင်ရွေးချယ်ရန်စာရင်းထဲတွင် ပါဝင်အောင်ထည့်သွင်းထားခြင်းဖြစ်ပြီး ဖယ်ရှားရန်မဖြစ်နိုင်ပေ။ :guilabel:`Show in Color Buttons` (အရောင်ခလုတ်များထဲတွင်ပြသခြင်း) ‌ရွေးချယ်မှုကိုသုံး၍ မိမိစိတ်ကြိုက်အရောင်များကို widget ထဲတွင် ထပ်မံထည့်သွင်းနိုင်သည်။ 

မည်သည့် palette အတွက်ဖြစ်စေ ဘောင်၏ဘေးရှိ tool များကို အသုံးပြု၍ အရောင်များစာရင်းကို စီမံခန့်ခွဲနိုင်သည်၊ ဆိုလိုသည်မှာ- 

* အရောင်ကို |symbologyAdd| :guilabel:`Add` (ပေါင်းထည့်ခြင်း) သို့မဟုတ် |symbologyRemove| :guilabel:`Remove` (ဖယ်ရှားခြင်း)
* အရောင်ကို |editCopy| :guilabel:`Copy` (ကူးယူခြင်း) သို့မဟုတ် |editPaste| :guilabel:`Paste` (ကူးချခြင်း)
* :file:`.gpl` ဖိုင်အမျိုးအစားများမှ/သို့ အရောင်များကို |fileOpen| :guilabel:`Import` (ထည့်သွင်းခြင်း) သို့မဟုတ် |fileSave| :guilabel:`Export` (ထုတ်ယူခြင်း) 

:ref:`Color Selector (အရောင်ရွေးချယ်ခြင်း) <color-selector>` dialog တွင် အရောင်ကို ပြုပြင်ပြောင်းလဲရန် သို့မဟုတ် အစားထိုးရန် စာရင်းထဲရှိအရောင်ကို ကလစ်နှစ်ချက်နှိပ်ပါ။ :guilabel:`Label` (အညွှန်း) column ကို  ကလစ်နှစ်ချက်နှိပ်၍လည်း အမည်ပြောင်းလဲနိုင်ပါသည်။ 


.. index:: Fonts
.. _fonts_options:


Fonts Settings (စာလုံး‌ဖောင့် setting များ)
--------------------------------------------

.. _figure_fonts_options:


.. figure:: img/options_fonts.png
   :align: center

   စာလုံး‌ဖောင့် setting များ


:guilabel:`Fonts` (စာလုံးဖောင့်) tab တွင် project များအတွင်း အသုံးပြုထားသော စာလုံးများကို စီမံခန့်ခွဲနိုင်ပါသည်- 

* :guilabel:`Font Replacements` (စာလုံးဖောင့်အစားထိုးမှုများ) - Project များ သို့မဟုတ် style များကို ထည့်သွင်းသောအခါ အသုံးချမည့် အလိုအလျောက် font အစားထိုးမှုများစာရင်းတစ်ခုကို ထုတ်ပေးပြီး မတူညီသော ကွန်ပျူတာ OS များတွင်အသုံးပြုရာ၌ project များနှင့် style များအတွက် ပိုမိုကောင်းမွန်သောအထောက်အကူများ ရရှိစေပါသည် (ဥပမာ- "Arial" ကို "Helvetica" ဖြင့်အစားထိုးခြင်း)
* :guilabel:`User Fonts` (အသုံးပြုသူ၏စာလုံးဖောင့်) - :ref:`user profile (အသုံးပြုသူပရိုဖိုင်) <user_profiles>` ၏ :file:`fonts` folder အခွဲတွင် TTF သို့မဟုတ် OTF ဖောင့်များကို သိမ်းဆည်းရန် ခွင့်ပြုထားပါသည်။ ထိုစာလုံးဖောင့်များကို QGIS အား စတင်ဖွင့်လိုက်သည့်အချိန်တွင် အလိုအလျောက် ထည့်သွင်းပေးနိုင်မည်ဖြစ်ပါသည်။ ၎င်းသည် လုပ်ငန်းသုံးနယ်ပယ်များတွင် မကြာခဏပိတ်ပင်ထားခံရသော OS အဆင့်တွင် စာလုံးဖောင့်များကို သီးသန့်ထည့်သွင်းရန်မလိုဘဲ font များကိုအသုံးပြုနိုင်သည့် နည်းလမ်းဖြစ်ပါသည်။ Panel တွင် ထည့်သွင်းထားသည့် အသုံးပြုသူစာလုံး font များအားလုံးကို စာရင်းပြုစုဖော်ပြထားပြီး ယခင်ထည့်သွင်းထားသည့် စာလုံး‌‌‌ font များကို စီမံခန့်ခွဲခြင်း (ဆိုလိုသည်မှာ ဖယ်ရှားခြင်း) တို့ကိုလည်း ဆောင်ရွက်နိုင်သည်။

  |checkbox| :guilabel:`Automatically download missing, freely-licensed fonts` (မပါဝင်သည့် လိုင်စင်အခမဲ့စာလုံး font များကို အလိုအလျောက်ဒေါင်းလုတ်ရယူခြင်း) ကို အမှန်ခြစ် ခြစ်၍အသုံးပြုနိုင်ပါသည်။ ဥပမာဆိုရသော် project သို့မဟုတ် style တစ်ခုကို ဖွင့်လိုက်သောအခါ၊ သို့မဟုတ် လက်ရှိတွင် မရှိသေးသော စာလုံး font များကို ကိုးကားအသုံးပြုထားသည့် vector tile layer ကိုဖွင့်ရန် ကြိုးစားကြည့်သောအခါ URL မှတဆင့် ဒေါင်းလုတ်ရယူမည့် လိုင်စင်အခမဲ့ရရှိသော စာလုံး font များစာရင်းသည် ထိုစာလုံးဖောင့်များကို အသုံးပြုသူပရိုဖိုင် စာလုံး font လမ်းကြောင်းသို့ အလိုအလျောက်ဒေါင်းလုတ်ရယူနိုင်ခြင်းရှိ/မရှိကို ဆုံးဖြတ်ပေးနိုင်ပါသည် (စာလုံး font လိုင်စင် အသိပေးချက်နှင့်အတူ)။


.. _layout_options:


Layouts settings (မြေပုံအပြင်အဆင် setting များ)
------------------------------------------------


.. _figure_layouts_settings:


.. figure:: img/options_layouts.png
   :align: center


   မြေပုံပြင်ဆင်ခြင်း setting များ


**Composition defaults** (**ဖွဲ့စည်းမှုဆိုင်ရာ default များ**)

:ref:`Print layout (မြေပုံထုတ်အပြင်အဆင်)  <label_printlayout>` အတွင်း အသုံးပြုသော :guilabel:`Default font` (မူရင်းစာလုံးဖောင့်) ကို သတ်မှတ်နိုင်ပါသည်။


**Grid appearance** (**Grid အသွင်အပြင်**)

* :guilabel:`Grid style` (Grid စတိုင်လ်) သတ်မှတ်ပါ။ (၎င်းတို့တွင် 'Solid' (အပြည့်)၊ 'Dots'(အစက်များ) နှင့် 'Crosses' (ကြက်ခြေခတ်များ) တို့ပါဝင်သည်။)
* :guilabel:`Grid color` (Grid အရောင်) ကိုသတ်မှတ်ပါ။


**Grid and guide defaults** (**Grid နှင့် guide default များ**)

* :guilabel:`Grid spacing` (Grid အကျယ်) ကိုသတ်မှတ်ပါ။
* X နှင့် Y အတွက် :guilabel:`Grid offset` (Grid အရွေ့) ကိုသတ်မှတ်ပါ။
* :guilabel:`Snap tolerance` (ဆွဲကပ်ခြင်း လက်ခံနိုင်မှု) ကိုသတ်မှတ်ပါ။


**Layout Paths** (**Layout လမ်းကြောင်းများ**)

* :guilabel:`Path(s) to search for extra print templates` (ပုံထုတ်နမူနာအပိုများကို ရှာဖွေရန်လမ်းကြောင်းများ) ကို သတ်မှတ်ပါ - Layout အသစ်တစ်ခုကိုဖန်တီးနေစဉ် Layout နမူနာများပါဝင်သည့် folder စာရင်းတစ်ခုဖြစ်ပါသည်။

.. index:: Variables
.. _variables_options:


Variables settings (ကိန်းရှင် setting များ)
--------------------------------------------

:guilabel:`Variables` tab တွင် global-level တွင် ရရှိနိုင်သော variable များအားလုံးကို စာရင်းပြုစုထားရှိပါသည်။

၎င်းတွင် အသုံးပြုသူများအနေဖြင့် global-level variable များကို စီမံခန့်ခွဲနိုင်စေပါသည်။ |symbologyAdd| (ထည့်သွင်းခြင်း) ခလုတ်ကိုနှိပ်၍ global-level variable အသစ်တစ်ခုကို ထည့်သွင်းအသုံးပြုနိုင်ပါသည်။ ထိုကဲ့သို့ပင် စာရင်းအတွင်းမှ global-level variable တစ်ခုကို ရွေးချယ်၍ |symbologyRemove| (ဖယ်ရှားခြင်း) ခလုတ်ကို click နှိပ်ပြီး ဖယ်ရှားနိုင်ပါသည်။


:ref:`general_tools_variables` အခန်းတွင် variable များအကြောင်းကို ထပ်မံလေ့လာနိုင်ပါသည်။


.. _figure_variables_settings:


.. figure:: img/options_variables_global.png
   :align: center


   Variables setting များ


.. index:: Authentication
.. _authentication_options:


Authentication settings (စစ်မှန်ကြောင်းအသိအမှတ်ပြုခြင်း setting များ)
----------------------------------------------------------------------

:guilabel:`Authentication` tab တွင် authentication ပြင်ဆင်သတ်မှတ်ခြင်းများကို သတ်မှတ်နိုင်ပြီး PKI certificate (PKI အသိအမှတ်ပြုလက်မှတ်များ) ကိုလည်း စီမံခန့်ခွဲနိုင်ပါသည်။ အသေးစိတ်သိရှိလိုသည်များအတွက် :ref:`authentication_index` တွင်ကြည့်ပါ။

Authentication များကိုစီမံခန့်ခွဲနိုင်ရန် ဘောင်ဘေးနားရှိ tool များစာရင်းကို အသုံးပြုနိုင်ပါသည်။ ၎င်းတို့မှာ-

* |symbologyAdd| :sup:`Add new authentication configuration` (Authentication ပြင်ဆင်သတ်မှတ်ခြင်းအသစ် ထည့်သွင်းခြင်း)
* |symbologyRemove| :sup:`Remove selected authentication configuration` (ရွေးချယ်ထားသော authentication ပြင်ဆင်သတ်မှတ်ခြင်းကို ဖယ်ရှားခြင်း)
* |symbologyEdit| :sup:`Edit selected authentication configuration` (ရွေးချယ်ထားသော authentication ပြင်ဆင်သတ်မှတ်ခြင်းကို တည်းဖြတ်ပြင်ဆင်ခြင်း) 


.. _figure_authentication_settings:


.. figure:: ../auth_system/img/auth-editor-configs2.png
   :align: center


   စစ်မှန်ကြောင်းအသိအမှတ်ပြုခြင်း setting များ


.. index:: Proxy, Network
.. _network_options:


Network settings (ကွန်ယက်ဆိုင်ရာ setting များ)
-----------------------------------------------

**General** (**အထွေထွေ**)

* :guilabel:`Timeout for network requests (ms)` (ကွန်ယက်တောင်းဆိုမှုများအတွက်ကုန်ဆုံးချိန်) (မီလီစက္ကန့်) သတ်မှတ်ပါ။ Default သည် 60000 ဖြစ်ပါသည်။
* :guilabel:`Default expiration period for WMS Capabilities (hours)` (WMS စွမ်းဆောင်ရည်များအတွက် default ကုန်ဆုံးချိန်)(နာရီ) ကို သတ်မှတ်ပါ။ Default သည် 24 ဖြစ်ပါသည်။
* :guilabel:`Default expiration period for WMS-C/WMTS tiles (hours)` (WMS-C/WMTS tile များအတွက် default ကုန်ဆုံးချိန်)(နာရီ) ကို သတ်မှတ်ပါ။ Default သည် 24 ဖြစ်ပါသည်။
* :guilabel:`Max retry in case of tile or feature request errors` (Tile သို့မဟုတ် feature တောင်းဆိုမှုမှားယွင်းခြင်းများအတွက် အများဆုံး ပြန်လည်ကြိုးစားနိုင်မှုအရေအတွက်) ကို သတ်မှတ်ပါ။
* :guilabel:`User-Agent` (အသုံးပြုသူ-ကိုယ်စားလှယ်) ကိုသတ်မှတ်ပါ။


.. _figure_network_tab:


.. figure:: img/options_network.png
   :align: center

   Network (ကွန်ယက်) နှင့် proxy (ကြားခံ) setting များ


**Cache settings** (**ယာယီသိမ်းဆည်းမှု setting များ**)

ယာယီသိမ်းဆည်းမှု (cache) အတွက် :guilabel:`Directory` (ဖိုင်သိမ်းဆည်းရာလမ်းကြောင်း) နှင့် :guilabel:`Size` (အရွယ်အစား) ကိုလည်း သတ်မှတ်နိုင်ပါသည်။ :guilabel:`automatically clear the connection authentication cache on SSL errors (recommended)` (SSL မှားယွင်းမှုများအပေါ် ချိတ်ဆက်မှုမှန်ကန်ကြောင်းယာယီသိမ်းဆည်းမှုများကို အလိုအလျောက်ရှင်းလင်းခြင်း)(အကြံပြုပါသည်) အတွက် tool များကိုလည်း ထောက်ပံ့ပေးထားပါသည်။


**Proxy for web access** (**ဝက်ဘ်အသုံးပြုခွင့်အတွက် ကြားခံ**)

* |checkbox| :guilabel:`Use proxy for web access` (ဝက်ဘ်အသုံးပြုခွင့်အတွက် ကြားခံသုံးခြင်း)
* မိမိလိုအပ်ချက်ပေါ်မူတည်၍ :guilabel:`Proxy type` |selectString| (ကြားခံအမျိုးအစား) ကိုသတ်မှတ်ပြီး 'Host' (လက်ခံ) နှင့် 'Port' (ဝင်ပေါက်) ကိုလည်း သတ်မှတ်နိုင်ပါသည်။ ရရှိနိုင်သော ကြားခံအမျိုးအစားများမှာ-

  * :menuselection:`Default Proxy` (ပုံသေကြားခံ) - စနစ်၏ကြားခံပေါ်မူတည်၍ ဆုံးဖြတ်ပါသည်။
  * :menuselection:`Socks5Proxy` (Sock5 ကြားခံ) - ချိတ်ဆက်မှုအမျိုးမျိုးအတွက် ယေဘုယျ အမျိုးအစားဖြစ်ပြီး TCP ၊ UDP ၊ ဝင်‌ပေါက်နှင့်ချိတ်ဆက်ခြင်း (အဝင်ချိတ်ဆက်မှုများ) နှင့် authentication များကိုလည်း ပံ့ပိုးပေးထားပါသည်။ 
  * :menuselection:`HttpProxy` (Http ကြားခံ) - "CONNECT" (ချိတ်ဆက်သည်) command ကိုအသုံးပြု၍ ဆောင်ရွက်ခြင်းနိုင်ပြီး အထွက် TCP ချိတ်ဆက်မှုများကိုသာ နှင့် authentication ကို ပံ့ပိုးပေးပါသည်။
  * :menuselection:`HttpCachingProxy` (Httpယာယီကြားခံ) - သာမန် HTTP command များကို အသုံးပြု၍ ဆောင်ရွက်နိုင်ပြီး HTTP တောင်းဆိုမှုများအတွက်သာ အသုံးပြုနိုင်ပါသည်။
  * :menuselection:`FtpCachingProxy` (Ftpယာယီကြားခံ) - FTP ကြားခံတစ်ခုကို အသုံးပြု၍ ဆောင်ရွက်နိုင်ပြီး FTP တောင်းဆိုမှုများအတွက်သာ အသုံးပြုနိုင်ပါသည်။

ကြားခံ၏ အထောက်အထားများ (Credentials) များကို :ref:`authentication widget <authentication>` ကိုအသုံးပြု၍ သတ်မှတ်ထားပါသည်။

URL အချို့ဖယ်ထားခြင်းကို ကြားခံ setting အောက်ရှိ text box (စာရိုက်နိုင်သည့်နေရာ) ထဲတွင် ထည့်သွင်းနိုင်ပါသည် (:numref:`Figure_Network_Tab` တွင်ကြည့်ပါ)။ အသုံးပြုလိုသော URL သည် text box ထဲတွင် စာရင်းပြုလုပ်ထားသော string တစ်ခုနှင့် စထားလျှင် မည်သည့် ကြားခံကိုမျှ အသုံးပြုမည်မဟုတ်ပေ။

မတူညီသော ကြားခံ setting အမျိုးမျိုးနှင့် ပတ်သက်၍ အသေးစိတ်အချက်အလက်များကို သိရှိလိုလျှင် https://doc.qt.io/archives/qt-5.9/qnetworkproxy.html#ProxyType-enum ထဲရှိ QT library မှတ်တမ်းမှတ်ရာ၏ လက်စွဲတွင် လေ့လာနိုင်သည်။

.. tip:: **ကြားခံများကို အသုံးပြုခြင်း**

   ကြားခံ (proxy) များအသုံးပြုခြင်းသည် တစ်ခါတစ်ရံတွင် ခက်ခဲနိုင်ပါသည်။ အကယ်၍ မိမိကိစ္စတွင် အထက်ပါကြားခံအမျိုးအစားများကို သုံး၍ အောင်မြင်နိုင်မှုရှိ/မရှိကို စစ်ဆေးရန် 'trial and Error' (စမ်းသပ်ခြင်းနှင့် မှားယွင်းမှု) ကို အသုံးပြုပြီး ဆက်လက်လုပ်ဆောင်ရာတွင် အသုံးဝင်ပါသည်။


.. index:: GPS
.. _gps_options:


GPS settings (GPS setting များ)
--------------------------------

GPS Visualisation Options (GPS ပုံဖော်ခြင်းဆိုင်ရာ ရွေးချယ်စရာများ)
....................................................................


.. figure:: img/options_gps.png
   :align: center

   GPS setting များ

ဤ dialog တွင် :ref:`QGIS သို့ချိတ်ဆက်သောအခါ (connected to QGIS) <sec_gpstracking>` ပြသမည့် GPS ကိရိယာများကို ပြင်ဆင်သတ်မှတ်နိုင်ပါသည်။ 

* :guilabel:`GPS location marker` သည် လက်ရှိ GPS တည်နေရာအတွက် အသုံးပြုသော သင်္ကေတအမှတ်အသားများကိုင်တွယ်ခြင်းကို လုပ်ဆောင်နိုင်သည်။
* :guilabel:`Rotate to match GPS bearing` သည် သင်္ကေတအမှတ်အသားများကို GPS လားရာနှင့် ကိုက်ညီစေရန် ဦးတည်ရာ လှည့်ပြောင်းသင့်/မသင့် ပြုလုပ်နိုင်ပါသည်။


.. _defining_new_device:

GPSBabel 
..........

`GPSBabel <https://www.gpsbabel.org/>`_ သည် Garmin သို့မဟုတ် Magellan ကဲ့သို့သော လူသိများထင်ရှားသည့် လက်ကိုင် GPS စက်များ နှင့် Google Earth သို့မဟုတ် Basecamp ကဲ့သို့သော မြေပုံဆိုင်ရာ ပရိုဂရမ်များ တစ်ခုနှင့် တစ်ခုအကြား waypoints (တည်နေရာအမှတ်) များ၊  tracks (ခြေရာခံလမ်းကြောင်း)များ နှင့် routes (ညွှန်ပြလမ်းကြောင်း) များကို ပြောင်းလဲပေးပါသည်။ ၎င်းတွင် လက်ကိုင် GPS စက်အမျိုးအစားများနှင့် ပရိုဂရမ်များစွာကို ပံ့ပိုးပေးထားပါသည်။ QGIS သည် လက်ကိုင် GPS စက်များ နှင့် အပြန်အလှန်ချိတ်ဆက်ဆောင်ရွက်နိုင်ရန် နှင့် :ref:`manipulate their data (၎င်းတို့၏ဒေတာများကိုင်တွယ်ခြင်း) <gps_algorithms>` လုပ်ဆောင်ရန် GPSBabel ပေါ်တွင် မူတည်နေပါသည်။ 

#. ပထမဦးစွာ :guilabel:`Path to GPSBabel` (GPSBabelသို့ လမ်းကြောင်း) binaries ကို သတ်မှတ်ရပါမည်။
#. ထို့နောက် မိမိ GPS စက်အမျိုးအစားကို ထည့်သွင်းပါ။ |symbologyAdd| :sup:`Add new device` ခလုတ်ကို နှိပ်၍ စက်ပစ္စည်းစာရင်းထဲသို့ ထည့်သွင်းခြင်း သို့မဟုတ် |symbologyRemove| :sup:`Remove device` ခလုတ်ကို နှိပ်၍ စာရင်းမှ ပယ်ဖျက်ခြင်းတို့ကို လုပ်‌ဆောင်နိုင်သည်။ 
#. GPS စက်အမျိုးအစားတစ်ခုစီအတွက် -

   * :guilabel:`Device name` (စက်ကိရိယာအမည်) သတ်မှတ်ပေးပါ။
   * QGIS နှင့်ချိတ်ဆက်ဆောင်ရွက်ရာတွင် QGIS မှ အသုံးပြုမည့် :guilabel:`Commands` (ညွှန်ကြားချက်) အမျိုးမျိုးကို အောက်ပါအတိုင်း ပြင်ဆင်သတ်မှတ်နိုင်ပါသည်- 

     * :guilabel:`Waypoint download` (တည်နေရာအမှတ်ဒေါင်းလုတ်ရယူခြင်း) ကို အသုံးပြု၍ GPS စက်မှ Waypoint များကို ရယူခြင်း
     * :guilabel:`Waypoint upload` (တည်နေရာအမှတ်ထည့်သွင်းခြင်း) ကို အသုံးပြု၍ GPS စက်ထဲတွင် Waypoint များ ထည့်သွင်းခြင်း
     * :guilabel:`Route download` (ညွန်ပြလမ်းကြောင်းကိုဒေါင်းလုတ်ရယူခြင်း) ကို အသုံးပြု၍ GPS စက်မှ Route များကို ရယူခြင်း
     * :guilabel:`Route upload` (ညွှန်ပြလမ်းကြောင်းထည့်သွင်းခြင်း) ကို အသုံးပြု၍ GPS စက်သို့ Route များ ထည့်သွင်းခြင်း
     * :guilabel:`Track download` (ခြေရာခံလမ်းကြောင်းကိုဒေါင်းလုတ်ရယူခြင်း) ကို အသုံးပြု၍ GPS စက်မှ Track များ ရယူခြင်း
     * :guilabel:`Track upload` (ခြေရာခံလမ်းကြောင်းထည့်သွင်းခြင်း) ကို အသုံးပြု၍ GPS စက်သို့ Track များ ထည့်သွင်းခြင်း

     Command များသည် များသောအားဖြင့် GPSBabel command များဖြစ်နေလျှင် GPX ဖိုင်တစ်ခုကို ဖန်တီးနိုင်သော အခြား command line program တစ်ခုခုကိုလည်း အသုံးပြုနိုင်ပါသည်။ အဆိုပါ command များကို လုပ်ဆောင်သောအခါ QGIS သည် ``%type``၊ ``%in``နှင့် ``%out`` အဓိကစကားလုံးများကို အစားထိုးလုပ်ဆောင်မည် ဖြစ်ပါသည်။ 

     ဥပမာတစ်ခုအနေဖြင့် စက်အမျိုးအစားတစ်ခုကို download command ``gpsbabel %type -i garmin -o gpx %in %out`` ဖြင့် ဖန်တီးပြီးနောက် waypoint များကို ဝင်ပေါက် ``/dev/ttyS0`` မှ ``output.gpx`` ဖိုင်သို့ ဒေါင်းလုတ်ပြုလုပ်ရန် အသုံးပြုမည်ဆိုပါက QGIS သည် အဓိကစကားလုံးများကို အစားထိုးပြီး ``gpsbabel -w -i garmin -o gpx /dev/ttyS0 output.gpx`` ဟူသည့် command ကို လုပ်ဆောင်သွားမည် ဖြစ်ပါသည်။ 

     မိမိအသုံးပြုသော ကိစ္စရပ်အတွက် သီးခြားဖြစ်နေနိုင်သည့် command line ရွေးချယ်မှုများအတွက် GPSBabel     အသုံးပြုနည်းလမ်းညွှန်ကို ဖတ်ရှုနိုင်ပါသည်။ 

စက်အမျိုးအစားအသစ်တစ်ခုကို ဖန်တီးပြီးသည်နှင့်တပြိုင်နက် GPS ဒေါင်းလုတ်ရယူခြင်းနှင့် ထည့်သွင်းခြင်း algorithm များ လုပ်ဆောင်ရန်အတွက် စက်အမျိုးအစားစာရင်းတွင် ပေါ်လာမည်ဖြစ်ပါသည်။ 


.. figure:: img/options_gpsbabel.png
   :align: center

   GPS Babel setting များ


.. index:: Search widget, Locator
.. _locator_options:


Locator settings (တည်နေရာပြ setting များ)
------------------------------------------

|search| :guilabel:`Locator` tab တွင် QGIS အတွင်း ရှာဖွေမှုများ လုပ်ဆောင်ရာတွင် ကူညီပေးမည့်  အခြေအနေပြဘားပေါ်ရှိ ရှာဖွေမှုလွယ်ကူလျင်မြန်စေသော widget ဖြစ်သည့် :ref:`Locator bar (တည်နေရာပြဘား) <locator_bar>` ကို ပြင်ဆင်သတ်မှတ်နိုင်ပါသည်။ 

၎င်းသည် အချို့သော default စစ်ထုတ်ရှာဖွေမှုများ (အစ စာလုံးများဖြင့်) ကို အသုံးပြုနိုင်ရန် ပံ့ပိုးပေးထားပါသည်-

.. _figure_locator_settings:


.. figure:: img/options_locator.png
   :align: center

   တည်နေရာပြ setting များ


* :guilabel:`Project Layers` (``l``): - :guilabel:`Layers` panel ထဲရှိ Layer တစ်ခုကိုရှာဖွေရန် နှင့် ရွေးချယ်ရန် လုပ်ဆောင်နိုင်ပါသည်။ 
* :guilabel:`Project Layouts` (``pl``) - Print layout တစ်ခုကို ရှာဖွေ၍ ဖွင့်ရန် လုပ်ဆောင်နိုင်ပါသည်။ 
* Actions (လုပ်ဆောင်ချက်များ) (``.``) - QGIS လုပ်ဆောင်ချက်တစ်ခုကို ရှာဖွေ၍ စေခိုင်းလုပ်ဆောင်ပေးပါသည်။ ထိုလုပ်ဆောင်ချက်များသည် QGIS တွင်ပါဝင်သော Panel တစ်ခုကိုဖွင့်ခြင်းကဲ့သို့ မည်သည့် tool သို့မဟုတ် menu မဆို ဖြစ်နိုင်ပါသည်။ 
* :guilabel:`Active Layer Features (လက်ရှိ Layer feature များ)` (``f``) - လက်ရှိအသုံးပြုနေသော Layer မှ field တစ်ခုခုရှိ ကိုက်ညီသည့် attribute များကို ရှာဖွေပေးပြီး ရွေးချယ်ထားသော feature ကို zoom ဆွဲယူကြည့်ရှုနိုင်ပါသည်။ အများဆုံးရလာဒ်အရေအတွက်ကို သတ်မှတ်ရန် |settings| ကိုနှိပ်ပါ။
* :guilabel:`Features in All Layers` (Layer များအားလုံးရှိ feature များ) (``af``) - :ref:`Searchable layers (ရှာဖွေနိုင်သော Layer များ) <project_layer_capabilities>` တစ်ခုစီ၏ :ref:`display name (ပြသနေသည့်အမည်) <maptips>` ရှိ ကိုက်ညီသည့် attribute များကို ရှာဖွေပေးပြီး ရွေးချယ်ထားသော feature ကို zoom ဆွဲယူကြည့်ရှုနိုင်ပါသည်။ အများဆုံးရလာဒ်အရေအတွက်နှင့် layer တစ်ခုစီအလိုက် အများဆုံးရလာဒ်အရေအတွက်များကို သတ်မှတ်ရန် |settings| ကိုနှိပ်ပါ။
* :guilabel:`Calculator` (``=``) - QGIS expression တိုင်းကို ဆန်းစစ်အကဲဖြတ်ရန် အသုံးပြုနိုင်ပြီး အကယ်၍ expression သည် မှန်ကန်ပါက ရလာဒ်များကို ကလစ်ဘုတ်တွင် ကူးယူနိုင်ပါသည်။ 
* :guilabel:`Spatial Bookmarks` (တည်နေရာအမှတ်အသားများ) (``b``) - တည်နေရာအမှတ်အသား extent ကို ရှာဖွေပြီး zoom ဆွဲယူကြည့်ရှုနိုင်ပါသည်။ 
* :guilabel:`Settings` (``set``) - Project နှင့် application တစ်ခုလုံးဆိုင်ရာ property dialog များကို ရှာဖွေပြီး ဖွင့်ပေးနိုင်ပါသည်။ 
*  :guilabel:`Go to Coordinate` (ကိုဩဒိနိတ်သို့သွားခြင်း) (``go``) - Comma သို့မဟုတ် space ဖြင့် ပိုင်းခြားထားသော x နှင့် y ကိုဩဒိနိတ်များ သို့မဟုတ် formatted URL (ဥပမာ OpenStreetMap ၊ Leaflet ၊ OpenLayer ၊ Google Maps ၊ ...) ဖြင့် သတ်မှတ်သော တည်နေရာသို့ မြေပုံမျက်နှာပြင်ကို ရွှေ့ပေးပါသည်။ ကိုဩဒိနိတ်သည် WGS 84 (``epsg:4326``) သို့မဟုတ် မြေပုံမျက်နှာပြင်၏ CRS အတိုင်းဖြစ်ရန် လိုအပ်ပါသည်။
* :guilabel:`Nominatim Geocoder` (``>``) - OpenStreetMap Foundation ၏ geocoding (တည်နေရာများကို ကုဒ်စနစ်ဖြင့်သတ်မှတ်ခြင်း) ဝန်ဆောင်မှုဖြစ်သော `Nominatim <https://nominatim.org>`_ အသုံးပြု၍ geocode ပြုလုပ်ပေးပါသည်။ 
* Processing Algorithms (``a``) - Processing algorithm dialog (လုပ်ငန်းလုပ်ဆောင်ခြင်း algorithm dialog) ကို ရှာဖွေပြီး ဖွင့်ပေးနိုင်ပါသည်။ 
* :guilabel:`Edit Selected Features` (ရွေးချယ်ထားသော feature များကို တည်းဖြတ်ပြင်ဆင်ခြင်း) (``ef``) - လက်ရှိ အသုံးပြုနေသော Layer တွင် ကိုက်ညီသော :ref:`modify-in-place (နေရာတွင် မွမ်းမံပြင်ဆင်ခြင်း)  <processing_inplace_edit>` Processing algorithm ကို လျင်မြန်စွာ ဝင်ရောက်လုပ်ဆောင်နိုင်စေပါသည်။


အဆိုပါ dialog တွင် အောက်ပါတို့ကို လုပ်ဆောင်နိုင်ပါသည်-

* :guilabel:`Prefix` (အစစာလုံးဖြင့်) စစ်ထုတ်ခြင်းကို စိတ်ကြိုက်ပြင်ဆင်နိုင်ပါသည်၊ စစ်ထုတ်မှု (filter) လုပ်ဆောင်ရန် အဓိကစာလုံးကို ဆိုလိုပါသည်။
* စစ်ထုတ်မှုကို :guilabel:`Enabled` (ဖွင့်ထား) ခြင်းရှိ/မရှိ သတ်မှတ်ပါ - ဖွင့်ထားလျှင် စစ်ထုတ်မှု (filter) ကို ရှာဖွေများတွင် အသုံးပြုနိုင်မည်ဖြစ်ပြီး တည်နေရာပြဘား menu ပေါ်တွင် shortcut (ဖြတ်လမ်း) တစ်ခုအနေဖြင့် တွေ့မြင်ရမည်ဖြစ်ပါသည်။ 

* စစ်ထုတ်မှု (filter) ကို :guilabel:`Default` အနေဖြင့် ထား/မထား သတ်မှတ်ပါ - သတ်မှတ်ထားသောအခါ filter (စစ်ထုတ်မှု) တစ်ခုကိုမသုံးထားသောကြောင့် ရှာဖွေမှုတစ်ခုသည် default filter (စစ်ထုတ်မှု) အမျိုးအစားများမှသာလျှင် ရလာဒ်များကို ထုတ်ပေးမည်ဖြစ်သည်။
* အချို့သော စစ်ထုတ်မှုများသည် ရှာဖွေမှုတစ်ခု၏ ရလာဒ်အရေအတွက်ကို သတ်မှတ်နိုင်သည့်နည်းလမ်းကို ပံ့ပိုးပေးပါသည်။ 

Default တည်နေရာစစ်ထုတ်မှု (default locator filter) များကို plugin များဖြင့် တိုးချဲ့အသုံးပြုနိုင်ပါသည်။ ဥပမာ- OSM nominatim ရှာဖွေမှုများ၊ database တိုက်ရိုက်ရှာဖွေမှုများ၊ Layer catalog ရှာဖွေမှုများ၊ စသည်…


Acceleration settings (အရှိန်မြှင့်တင်ခြင်း setting များ)
----------------------------------------------------------

OpenCL အရှိန်မြှင့်တင်ခြင်း setting များ။


.. _figure_acceleration_settings:

.. figure:: img/options_acceleration.png
   :align: center

   အရှိန်မြှင့်တင်ခြင်း setting များ

ကွန်ပျူတာ၏ hardware နှင့် software ပေါ်မူတည်၍ OpenCL acceleration (OpenCL အရှိန်မြှင့်တင်ခြင်း) ကို ဖွင့်နိုင်ရန်အတွက် ထပ်ဆောင်း library များကို ထည့်သွင်းရန် လိုအပ်နိုင်ပါသည်။ 


IDE settings (IDE setting များ)
--------------------------------

.. _code_editor_options:


Code Editor settings (ကုဒ်တည်းဖြတ်ပြင်ဆင်ပေးသည့်အရာ setting များ)
..................................................................

|codeEditor| :guilabel:`Code Editor` tab ထဲတွင် code editor widget များ၏ အသွင်အပြင်နှင့် လုပ်ဆောင်ပုံများ (Python interactive console နှင့် editor ၊ expression widget နှင့် လုပ်ဆောင်ချက် editor စသည်) ကို ကိုင်တွယ်ထိန်းချုပ်နိုင်ပါသည်။ 


.. _figure_code_editor_settings:


.. figure:: img/options_codeeditor.png
   :align: center

   Code Editor setting များ

Dialog ၏ထိပ်ရှိ widget တစ်ခုတွင် လက်ရှိ setting များ၏ အကြိုကြည့်ရှုမှု (preview) ကို coding ဘာသာစကား (Python ၊ QGIS expression ၊ HTML ၊ SQL ၊ JavaScript) အမျိုးမျိုးဖြင့် တိုက်ရိုက်ကြည့်ရှုနိုင်ပါသည်။ Setting များကို ချိန်ညှိရာတွင် အဆင်ပြေစေသောနည်းလမ်းဖြစ်ပါသည်။

* Default :guilabel:`Font` (စာလုံးဖောင့်) family နှင့် :guilabel:`Size` (အရွယ်အစား) တို့ကို မွမ်းမံပြင်ဆင်ရန် :guilabel:`Override Code Editor Font` (Code Editor Font ကိုအစားထိုးပြင်ဆင်ခြင်း) ကို အမှန်ခြစ်ပါ။

* :guilabel:`Colors` အုပ်စုအောက်တွင် အောက်ပါတို့ကို ပြုလုပ်နိုင်သည်-

  * :guilabel:`Color scheme` (အရောင်အစီအစဉ်) တစ်ခုကို ရွေးချယ်ပါ - ၎င်းတွင် ကြိုတင်သတ်မှတ်ထားသည့် setting များမှာ ``Default`` (မူရင်း) ၊ ``Solarized Dark`` (အမှောင်) နှင့် ``Solarized Light`` (အလင်း) တို့ဖြစ်သည်။ အရောင်တစ်ခုကို မွမ်းမံပြင်ဆင်နေသမျှ ``Custom`` (စိတ်ကြိုက်) scheme တစ်ခုပွင့်နေမည်ဖြစ်ပြီး မနှစ်သက်ပါက ကြိုတင်သတ်မှတ်ထားသည့် scheme တစ်ခုကိုရွေးချယ်၍ နဂိုအနေအထားအတိုင်း ပြန်လည်ပြောင်းလဲနိုင်ပါသည်။ 
  * Code ရေးသားခြင်းထဲတွင် element တစ်ခုချင်းစီ၏ :ref:`color (အရောင်) <color_widget>` ကို ပြောင်းလဲနိုင်ပါသည်။ ဥပမာ- မှတ်ချက်များ၊ ကိုးကားချက်များ၊ လုပ်ဆောင်ချက်များ၊ နောက်ခံ..အစရှိသည်တို့ဖြစ်သည်။


.. _console_options:


Python Console settings (Python Console setting များ)
......................................................

|runConsole| :guilabel:`Python Console` setting များသည် Python တည်းဖြတ်မှုများ (:ref:`interactive console <interactive_console>`:ref:`code editor <console_editor>` ၊ :ref:`project macros <project_macros>` ၊ :ref:`custom expressions <function_editor>` ၊ ..) ၏ လုပ်ဆောင်ပုံကိုထိန်းချုပ်ရန်နှင့် စီမံဆောင်ရွက်နိုင်ရန်ကူညီပေးပါသည်။ ၎င်းကို |options| :sup:`Options...` ခလုတ်မှလည်း ဝင်ရောက်နိုင်သည်။

* :guilabel:`Python console` toolbar
* :guilabel:`Python console` widget ၏ ရွေးချယ်နိုင်သည့် menu
* code editor ၏ ရွေးချယ်နိုင်သည့် menu


.. _figure_python_console_settings:


.. figure:: img/options_pythonconsole.png
   :align: center

   Python Console setting များ

အောက်ပါတို့ကိုလည်း သတ်မှတ်နိုင်ပါသည်-

* :guilabel:`Autocompletion` (အလိုအလျောက်ပြီးစီးခြင်း) - Code ပြီးမြောက်ခြင်းကို လုပ်ဆောင်ပေးပါသည်။ လက်ရှိမှတ်တမ်းမှဖြစ်စေ၊ ထည့်သွင်းထားသော API ဖိုင်များမှဖြစ်စေ သို့မဟုတ် နှစ်ခုစလုံးမှဖြစ်စေ အလိုအလျောက်ပြီးစီးခြင်းကို ရရှိနိုင်ပါသည်။

  * :guilabel:`Autocompletion threshold` (အလိုအလျောက်ပြီးစီးသည့် သတ်မှတ်ချက်) - အလိုအလျောက်ပြီးစီးခြင်းစာရင်းကို (အက္ခရာများဖြင့်) ပြသရန်အတွက် threshold ကိုသတ်မှတ်သည်။

* :guilabel:`Typing` (စာရေးသားခြင်း) ‌အောက်တွင်

  * :guilabel:`Automatic parentheses insertion` (ကွင်းစကွင်းပိတ်များကို အလိုအလျောက်ထည့်သွင်းခြင်း) - ကွင်းပိတ်များကို အလိုအလျောက်ပိတ်ပေးပါသည်။
  * |checkbox| :guilabel:`Automatic insertion of the 'import' string on 'from xxx'` (အခြားနေရာမှ import string များကို အလိုအလျောက်ထည့်သွင်းခြင်း) - Import များကို သတ်မှတ်သည့်အခါ 'Import' ထည့်သွင်းခြင်းကို လုပ်ဆောင်ပေးပါသည်။

* :guilabel:`Run and Debug` (လုပ်ဆောင်ခြင်းနှင့် မှားယွင်းမှုများကိုရှာဖွေခြင်း) အောက်တွင်

  * |unchecked| :guilabel:`Enable Object Inspector (switching between tabs may be slow)` (အရာဝတ္ထုစစ်ဆေးသည့်အရာကိုဖွင့်ခြင်း (tab များအကြား ကူးပြောင်းခြင်းကို နှောင့်နှေးကြန့်ကြာနိုင်ပါသည်))
  * |unchecked| :guilabel:`Auto-save script before running` (မလုပ်ဆောင်ခင် script များအလိုအလျောက်သိမ်းဆည်းခြင်း) - Script များကို စေခိုင်းလုပ်ဆောင် (execute) ပါက အလိုအလျောက်သိမ်းဆည်းပေးပါသည်။ ဤလုပ်ဆောင်ချက်သည် script များကို ယာယီဖိုင် (ယာယီဖိုင်လမ်းကြောင်းစနစ်တွင်) တစ်ခုအနေဖြင့် သိမ်းဆည်းပြီး လုပ်ဆောင် (running) ပြီးပါက အလိုအလျောက်ဖျက်သွားမည်ဖြစ်သည်။
 
:guilabel:`APIs` များအတွက် အောက်ပါတို့ကို သတ်မှတ်နိုင်ပါသည်-

* :guilabel:`Using preloaded APIs file` (ကြိုတင်ထည့်သွင်းထားသော API ဖိုင်များအသုံးပြုခြင်း) - ကြိုတင်ထည့်သွင်းထားသော API ဖိုင်များကို အသုံးပြု/မပြုကို ရွေးချယ်နိုင်ပါသည်။ အကယ်၍ ၎င်းကိုအမှန်ခြစ်မပြုလုပ်ထားပါက API ဖိုင်များကို ပေါင်းထည့်နိုင်ပြီး ပြင်ဆင်ထားသော API ဖိုင်များကို အသုံးပြုလိုပါကလည်း ရွေးချယ်နိုင်ပါသည် (နောက် option တွင် ကြည့်ပါ)။
* |unchecked| :guilabel:`Using prepared APIs file` (ပြင်ဆင်ထားသော API ဖိုင်များအသုံးပြုခြင်း) - အမှန်ခြစ်ပြုလုပ်ထားပါက ရွေးချယ်ထားသော ``*.pap`` ဖိုင်ကို code ပြီးစီးရန်အတွက် အသုံးပြုမည်ဖြစ်သည်။ ပြင်ဆင်ထားသော API ဖိုင်တစ်ခုကို ဖန်တီးရန် အနည်းဆုံး ``*.api`` ဖိုင်တစ်ဖိုင်ကိုထည့်သွင်းရမည်ဖြစ်ပြီး  :guilabel:`Compile APIs...` (API များစုစည်းခြင်း) ခလုတ်ကိုနှိပ်၍ ၎င်းကို compile (စုစည်း) လုပ်ရပါမည်။

:guilabel:`GitHub access token` (GitHub ဝင်ရောက်ခွင့်တိုကင်) အောက်တွင် ကိုယ်ပိုင်တိုကင်တစ်ခုကိုဖန်တီးနိုင်ပြီး Python code editor အတွင်းတွင် code snippets (ပြန်လည်အသုံးပြုနိုင်သော ကုဒ်များ) ကို မျှဝေနိုင်ပါသည်။ အသေးစိတ်အချက်အလက်များကို `GitHub authentication <https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token>`_  တွင်လေ့လာနိုင်ပါသည်။


Processing settings (လုပ်ဆောင်မှုဆိုင်ရာ setting များ)
-------------------------------------------------------

|processingAlgorithm| :guilabel:`Processing` (လုပ်ဆောင်မှု) tab သည် QGIS Processing framework (QGIS လုပ်ငန်းစဉ်) တွင် အသုံးပြုသည့် data ပံ့ပိုးသူများနှင့် ကိရိယာများဆိုင်ရာ ယေဘုယျ setting များကို ပံ့ပိုးပေးထားပါသည်။ :ref:`label_processing` တွင် ထပ်မံလေ့လာနိုင်ပါသည်။


.. comment for writers:


.. _figure_processing_settings:


.. figure:: img/options_processing.png
   :align: center


   လုပ်ဆောင်မှုဆိုင်ရာ setting များ

.. _optionsadvanced:


Advanced settings (အဆင့်မြင့် setting များ)
--------------------------------------------

.. _figure_advanced_settings:


.. figure:: img/options_advanced.png
   :align: center


   အဆင့်မြင့် setting များ

QGIS နှင့်သက်ဆိုင်သော setting အားလုံး (UI ၊ ကိရိယာများ၊ ဒေတာပံ့ပိုးသူများ ၊ Processing Configurations (လုပ်ဆောင်ခြင်းဆိုင်ရာအပြင်အဆင်များ)၊ မူရင်းတန်ဖိုးများ၊ ဖိုင်လမ်းကြောင်းများ၊ plugins ရွေးချယ်စရာများ၊ expression များနှင့် ဂျီဩမေတြီစစ်ဆေးမှုများ…..) များကို လက်ရှိ :ref:`user profile (အသုံးပြုသူပရိုဖိုင်) <user_profiles>` အောက်တွင် :file:`QGIS/QGIS3.ini` ဖိုင်အနေဖြင့်သိမ်းဆည်းထားပါသည်။ ဤဖိုင်ကို အခြားထည့်သွင်းမှုများတွင် ကူးယူခြင်းဖြင့် အပြင်အဆင်သတ်မှတ်မှုများကို မျှဝေနိုင်ပါသည်။

QGIS အတွင်းမှ :guilabel:`Advanced` tab တွင် ထိုသို့သော setting များကို :guilabel:`Advanced Settings Editor` မှတဆင့် စီမံခန့်ခွဲနိုင်ပါသည်။ ဂရုတစိုက်လုပ်ကိုင်ရန်ဆုံးဖြတ်ပြီးပါက ရှိနေပြီးသား setting များအားလုံး စုဖွဲ့ထားသော widget ပေါ်လာမည်ဖြစ်ပြီး ၎င်းတို့၏တန်ဖိုးများကို တည်းဖြတ်ပြင်ဆင်နိုင်မည်ဖြစ်သည်။ Setting တစ်ခုပေါ် သို့မဟုတ် အုပ်စုတစ်ခုပေါ်တွင် right-click နှိပ်ပြီး ၎င်းကို ဖျက်ပစ်နိုင်ပါသည် (setting တစ်ခု သို့မဟုတ် အုပ်စုတစ်ခုကို ပေါင်းထည့်ရန် :file:`QGIS3.ini` file ကို တည်းဖြတ်ပြင်ဆင်ရမည်ဖြစ်ပါသည်)။ လုပ်ဆောင်ထားသော ပြောင်းလဲမှုများကို :file:`QGIS3.ini` file ထဲတွင် အလိုအလျောက်သိမ်းဆည်းပေးမည်ဖြစ်သည်။

.. warning:: **အဆင့်မြင့် setting များ tab ကို သေချာစွာမကြည့်ရှုပဲ အသုံးပြုခြင်းကိုရှောင်ကြဉ်ပါ**

   ပြောင်းလဲမှုများကို အလိုအလျောက်သိမ်းဆည်းလုပ်ဆောင်ပေးခြင်းကြောင့် ဤ dialog ရှိ setting များကို မွမ်းမံပြင်ဆင်ရာတွင် ဂရုပြုပါ။ သေချာစွာမသိပဲ ပြောင်းလဲမှုများပြုလုပ်ခြင်းသည် QGIS ထည့်သွင်းခြင်းကို နည်းလမ်းအမျိုးမျိုးဖြင့် ပျက်စီးစေပါသည်။


.. index:: User profile
.. _user_profiles:

Working with User Profiles (အသုံးပြုသူပရိုဖိုင်များနှင့်အလုပ်လုပ်ခြင်း)
========================================================================

The concept (အယူအဆ) 
---------------------

:menuselection:`Settings --> User Profiles` menu တွင် အသုံးပြုသူပရိုဖိုင်ကို သတ်မှတ်ရန်နှင့် ဝင်ရောက်ရန် လုပ်ဆောင်ချက်များကို ပံ့ပိုးပေးထားပါသည်။ အသုံးပြုသူပရိုဖိုင်တစ်ခုသည် တစ်စုတစ်စည်းတည်းဖြစ်သော application ပြင်ဆင်သတ်မှတ်မှုတစ်ခုဖြစ်ပြီး folder တစ်ခုထဲတွင် သိမ်းဆည်နိုင်မည်ဖြစ်ပါသည်-

* :ref:`Global setting များ <gui_options>` အားလုံးတွင် နေရာဒေသများ၊ အရိပ်ချခြင်းများ၊ စစ်မှန်ကြောင်းအသိအမှတ်ပြခြင်း setting များ၊ အရောင် palette များနှင့် ဖြတ်လမ်းနည်းများ အားလုံးပါဝင်ပါသည်။ 
* GUI ပြင်ဆင်သတ်မှတ်မှုများနှင့် :ref:`customization (စိတ်ကြိုက်ပြင်ဆင်မှုများ) <sec_customization>` 
* Grid ဖိုင်များနှင့် မူတည်မျက်နှာပြင် (datum) ပြောင်းလဲခြင်းအတွက် ထည့်သွင်းထားသော အခြား proj အကူဖိုင်များ
* ထည့်သွင်းထားသည့် :ref:`plugin <plugins>` များနှင့် ၎င်းတို့၏ ပြင်ဆင်သတ်မှတ်မှုများ
* Project နမူနာပုံစံများနှင့် ကြိုတင်ကြည့်ရှုနိုင်သည့်ပုံများနှင့်အတူ သိမ်းဆည်းထားသည့် project မှတ်တမ်း
* :ref:`processing settings (လုပ်ဆောင်မှုဆိုင်ရာ setting များ) <label_processing>` ၊ မှတ်တမ်းများ၊ script များ၊ model များ။ 

ပုံမှန်အားဖြင့် QGIS ထည့်သွင်းခြင်းတွင် ``default`` ဟု အမည်ပေးထားသော အသုံးပြုသူပရိုဖိုင်တစ်ခုပါဝင်ပါသည်။ သို့ရာတွင် အသုံးပြုသူပရိုဖိုင်များကို အလိုရှိသလောက် ဖန်တီးနိုင်ပါသည်- 

#. :guilabel:`New profile...` (ပရိုဖိုင်အသစ်) ကိုနှိပ်ပါ။ 
#. ပရိုဖိုင်အမည်တစ်ခုပေးရန် အသိပေးမည်ဖြစ်ပြီး :file:`~/<UserProfiles>/` အောက်တွင် အမည်တူ folder တစ်ခုဖန်တီးပါမည်-

   * ``~`` သည် **HOME** လမ်းကြောင်းကို ကိုယ်စားပြုပြီး |win| Windows တွင် :file:`C:\\Users\\<username>` ကဲ့သို့ဖြစ်ပါသည်။ 
   * ``<UserProfiles>`` သည် အောက်တွင် ဖော်ပြထားသည့် အဓိကပရိုဖိုင်များ folder ကို ကိုယ်စားပြုပါသည်၊ ဆိုလိုသည်မှာ-

     * |nix| :file:`.local/share/QGIS/QGIS3/profiles/`
     * |win| :file:`%AppData%\\Roaming\\QGIS\\QGIS3\\profiles\\`
     * |osx| :file:`Library/Application Support/QGIS/QGIS3/profiles/`


    QGIS တွင် အသုံးပြုသူပရိုဖိုင် folder ကို :guilabel:`Open Active Profile Folder` (လက်ရှိပရိုဖိုင် folder ကိုဖွင့်ခြင်း) ကို အသုံးပြု၍ ဖွင့်နိုင်ပါသည်။

#. QGIS ကို ရှင်းလင်းသည့် ပြင်ဆင်သတ်မှတ်မှုပုံစံတစ်ခုဖြင့် အသစ်စတင်မည်ဖြစ်သည်။ ထို့နောက် စိတ်ကြိုက် ပြင်ဆင်သတ်မှတ်မှုများကို သတ်မှတ်နိုင်ပါသည်။

QGIS ထည့်သွင်းရာတွင် ပရိုဖိုင်တစ်ခုထက်ပို၍ ရှိနေမည်ဆိုလျှင် လက်ရှိအသုံးပြုနေသည့်ပရိုဖိုင်၏အမည်ကို application ခေါင်းစဉ်ဘားတွင် လေးထောင့်ပုံကွင်းစကွင်းပိတ် ([...]) အတွင်း ဖော်ပြမည်ဖြစ်သည်။

အသုံးပြုသူပရိုဖိုင်တစ်ခုချင်းစီတွင် သီးခြား setting များ၊ plugin များနှင့် မှတ်တမ်းများပါဝင်နေသောကြောင့် မတူညီသော အလုပ်လုပ်ပုံအမျိုးမျိုး၊ သရုပ်ပြမှုများ (demos)၊ စက်တစ်ခုတည်းတွင် မတူညီသောအသုံးပြုသူများ သို့မဟုတ် setting များစမ်းသပ်ခြင်းတို့အတွက် အသုံးဝင်ပါသည်။ :menuselection:`Settings --> User Profiles` menu တွင် အသုံးပြုသူပရိုဖိုင်ကို ရွေးချယ်၍ တစ်ခုမှ အခြားတစ်ခုသို့ ပြောင်းလဲနိုင်ပါသည်။ :ref:`command line (ညွှန်ကြားချက်များ) <label_commandline>` မှ သီးခြားအသုံးပြုသူပရိုဖိုင်တစ်ခုဖြင့်လည်း QGIS ကို လုပ်ဆောင်နိုင်ပါသည်။ 


.. tip:: **ချွတ်ယွင်းချက်ရှိနေမှုကို စစ်ဆေးရန်အတွက် အသုံးပြုသူပရိုဖိုင်အသစ်တွင် QGIS ကို လုပ်ဆောင်ပါ**

 QGIS တွင် အချို့သောလုပ်ဆောင်ချက်များကို ဆိုးဆိုးရွားရွားကြုံတွေ့ရပါက အသုံးပြုသူပရိုဖိုင်အသစ်တစ်ခုကိုဖန်တီး၍ commands (ညွှန်ကြားချက်များ) ကို နောက်တစ်ကြိမ် လုပ်ဆောင်ပါ။ တခါတရံတွင် ချွတ်ယွင်းချက်များသည် လက်ရှိအသုံးပြုသူပရိုဖိုင်၏ အကြွင်းအကျန်များနှင့် ဆက်စပ်နေတတ်ပြီး QGIS တွင် ပရိုဖိုင်အသစ်တစ်ခုကို စတင်လိုက်ခြင်းဖြင့် ၎င်းတို့ကို ပြင်ဆင်ပြီးဖြစ်သွားစေပါသည်။


.. _user_profile_setting:


Setting user profile (အသုံးပြုသူပရိုဖိုင်သတ်မှတ်ခြင်း)
-------------------------------------------------------

ပုံမှန်အားဖြင့် QGIS သည် နောက်ဆုံးပိတ်ထားခဲ့သည့် session ၏ ပရိုဖိုင်နှင့်အတူ session အသစ်တစ်ခု ဖွင့်ပေးပါသည်။  ၎င်းကို အခြား setting များအကြား :menuselection:`Settings -->` |options| :menuselection:`Options -->` |user| :menuselection:`User Profiles` tab တွင် စိတ်ကြိုက်ပြင်ဆင်နိုင်ပါသည်-


.. _figure_userprofiles_settings:


.. figure:: img/options_userprofiles.png
   :align: center

   အသုံးပြုသူပရိုဖိုင် setting များ

* :guilabel:`Startup profile` (စတင်မည့်ပရိုဖိုင်) - QGIS session တစ်ခုကို စတင်ဖွင့်လိုက်သည့်အခါ အသုံးပြုမည့် အသုံးပြုသူပရိုဖိုင်ကို ဖော်ညွှန်းခြင်းဖြစ်သည်။ ၎င်းသည် အောက်ပါတို့ဖြစ်နိုင်ပါသည်-

  * :guilabel:`Use last closed profile` (နောက်ဆုံးပိတ်ခဲ့သည့်ပရိုဖိုင်ကိုအသုံးပြုခြင်း) 
  * :guilabel:`Always use profile` (ပရိုဖိုင်ကိုအမြဲအသုံးပြုခြင်း) ရွေးချယ်ရန်စာရင်း (drop-down) မှ ရွေးချယ်နိုင်သည့် သီးခြားအသုံးပြုသူပရိုဖိုင်
  * :guilabel:`Choose profile at start up` (စတင်အသုံးပြုရန်ပရိုဖိုင်ရွေးချယ်ခြင်း) - ရရှိနိုင်သည့်အသုံးပြုသူပရိုဖိုင်များကို စာရင်းပြုစုထားသည့် :guilabel:`User Profile Selector` (အသုံးပြုသူပရိုဖိုင်ရွေးချယ်ပေးသည့်အရာ)ကို ပွင့်စေပါသည်။ Entry တစ်ခုကို ကလစ်နှစ်ချက်နှိပ်ပါ သို့မဟုတ် ပရိုဖိုင်တစ်ခုကိုရွေးချယ်ပြီး ထိုပရိုဖိုင်ကို စတင်အသုံးပြုနိုင်ရန် :guilabel:`OK` ကိုနှိပ်ပါ။ စာရင်းထဲသို့ |symbologyAdd| :guilabel:`Add new profile` (ပရိုဖိုင်အသစ်တစ်ခုထည့်ခြင်း) ကို ပြုလုပ်နိုင်ပြီး ၎င်းပရိုဖိုင်အသစ်သည် ဖွင့်ထားသည့် session ဖြင့် အလိုအလျောက်လုပ်ဆောင်သွားမည်ဖြစ်သည်။

* :guilabel:`Profile display` (ပရိုဖိုင်ပြသခြင်း) အောက်တွင် အောက်ပါတို့ကိုသတ်မှတ်နိုင်ပါသည်- 

  * :guilabel:`User Profile Selector` (အသုံးပြုသူပရိုဖိုင်ရွေးချယ်ပေးသည့်အရာ) dialog မှ ပရိုဖိုင်အသစ်တစ်ခုကို ရွေးချယ်ရာတွင် အသုံးပြုမည့် icon အရွယ်အစား
  * :menuselection:`Settings --> User profiles` menu သို့မဟုတ် :guilabel:`User Profile Selector` dialog ရှိ လက်ရှိပရိုဖိုင်ဘေးတွင် ပြသရန် သီးခြား icon တစ်ခု။ စိတ်ကြိုက်ပြင်ဆင်ချက်များကို ဖယ်ရှားရန် |refresh| :sup:`Reset profile icon` ကိုနှိပ်ပါ။ 

.. index:: Project properties
   single: Project; Properties
   single: Settings; Project


.. _project_properties:


Project Properties (Project ဂုဏ်သတ္တိများ)
===========================================

:menuselection:`Project --> Project Properties` အောက်ရှိ project အတွက် properties window (ဂုဏ်ရည်အချက်များ window) တွင် project သီးသန့်ရွေးချယ်စရာများကို သတ်မှတ်နိုင်ပါသည်။ Project သီးသန့်ရွေးချယ်စရာများသည် အထက်တွင်ဖော်ပြခဲ့သည့် :guilabel:`Options` (ရွေးချယ်စရာများ) dialog ရှိ ၎င်းတို့နှင့်တူညီသည့်အရာများကို အစားထိုးလုပ်ဆောင်သွားမည်ဖြစ်သည်။

General Properties (အထွေထွေ ဂုဏ်သတ္တိများ)
-------------------------------------------

|general| :guilabel:`General` tab ရှိ :guilabel:`General settings` (အထွေထွေ setting) များတွင် အောက်ပါတို့ကို လုပ်ဆောင်နိုင်ပါသည်- 

* Project ဖိုင်၏တည်နေရာကိုကြည့်နိုင်ပါသည်။
* Project Home အတွက် folder ကိုသတ်မှတ်နိုင်ပါသည် (:guilabel:`Browser` panel ၏ :guilabel:`Project home` item ထဲတွင် ရရှိနိုင်ပါသည်)။ ထိုလမ်းကြောင်းသည် project ဖိုင် folder နှင့်ဆက်နွယ်မှုရှိ (relative) နိုင်သကဲ့သို့ ပကတိ (absolute) လည်းဖြစ်နိုင်ပါသည်။ Project Home ကို data များသိမ်းဆည်းရန်နှင့် project အတွက် အသုံးဝင်သော အခြားအကြောင်းအရာများကို သိမ်းဆည်းရန် အသုံးပြုနိုင်ပါသည်။ Dataset နှင့် project ဖိုင်များကို တစ်နေရာတည်းတွင် သိမ်းဆည်းမထားသည့်အခါမျိုးတွင်လည်း အဆင်ပြေစေပါသည်။ အကယ်၍ ထည့်သွင်းမထားလျှင် :guilabel:`Project home` သည် project ဖိုင် folder တွင် ပုံသေရောက်ရှိနေပေလိမ့်မည်။
* Project ဖိုင်လမ်းကြောင်းဘေးတွင် project ကို ခေါင်းစဉ်တစ်ခုပေးနိုင်ပါသည်။
* ရွေးချယ်ထားသည့် feature များအတွက် အသုံးပြုမည့် အရောင်ကို ရွေးချယ်နိုင်ပါသည်။
* မြေပုံ canvas အတွက် အသုံးပြုနိုင်မည့် နောက်ခံအရောင်ကို ရွေးချယ်နိုင်ပါသည်။
* Project ထဲရှိ Layer လမ်းကြောင်းများကို ပကတိ (absolute) အတိုင်းဖြစ်စေ သို့မဟုတ် project ဖိုင်တည်နေရာနှင့် ဆက်နွယ် (relative) ၍ဖြစ်စေ သိမ်းဆည်းရန် သတ်မှတ်နိုင်သည်။ Project ကို မတူညီသောပလက်ဖောင်းများရှိ ကွန်ပျူတာများမှ ဝင်ရောက်အသုံးပြုလျှင် သို့မဟုတ် Layer နှင့် project ဖိုင် နှစ်မျိုးစလုံးကို နေရာရွှေ့ခြင်း သို့မဟုတ် မျှဝေခြင်းများ လုပ်ဆောင်နိုင်သောအခါ relative path (ဆက်နွယ်သည့်လမ်းကြောင်း) ကို အသုံးပြုနိုင်သည်။
* Project ကို မြေပုံအကွက် (map tile) များဖြင့် ပုံဖော်ပြသသည့်အခါတွင် artifacts (အပြစ်အနာအဆာ) များကို ရှောင်ရှားရန် ရွေးချယ်နိုင်သည်။ ဤရွေးချယ်မှုကို အမှန်ခြစ်ပြုလုပ်ပါက လုပ်ဆောင်မှု အရည်အသွေးကျဆင်းစေနိုင်သည်ကို သတိပြုပါ။
* :guilabel:`Remember attribute tables windows and docks between sessions` (Session များအကြား အချက်အလက်ဇယား window များနှင့် dock များကို မှတ်သားခြင်း) - ၎င်းကို project တစ်ခုအတွက် အမှန်ခြစ်ပြုလုပ်ထားပါက ဖွင့်ထားသည့် မည်သည့် attribute ဇယားကိုမဆို project ထဲတွင် သိမ်းဆည်းမည်ဖြစ်ပြီး project ကို ဖွင့်လိုက်သည်နှင့် ၎င်းတို့ကို ချက်ချင်း ပြန်ပွင့်စေမည်ဖြစ်သည်။ ၎င်းသည် မိမိလိုအပ်ချက်အရ attribute ဇယား ပြင်ဆင်သတ်မှတ်မှုများ၏ သီးခြားအစုတစ်ခုဖြင့် project တစ်ခုကို တည်ဆောက်ထားသည့်အခါတွင် ထို attribute ဇယားများကို ပြန်လည်တည်ဆောက်ရန် ခက်ခဲသောကြောင့် အလုပ်ပိုတွင်စေပါသည်။

.. _measurements_ellipsoid:

GIS တွင် ဧရိယာနှင့်အကွာအဝေးတွက်ချက်ခြင်းသည် အသုံးများသောလိုအပ်ချက်တစ်ခုဖြစ်သည်။ သို့သော်လည်း ဤတန်ဖိုးများသည် လက်ရှိသုံးနေသော မြေပုံအရိပ်ချခြင်း (projection) setting များနှင့် အမှန်တကယ်ဆက်စပ်နေပါသည်။ :guilabel:`Measurements` (တိုင်းတာမှုများ) ဘောင်တွင် ဤ parameter များကို ကိုင်တွယ်နိုင်ပြီး အောက်ပါတို့ကို ရွေးချယ်၍ အသုံးပြုနိုင်ပါသည်- 

* :guilabel:`Ellipsoid` (ဘဲဥပုံစက်လုံး) - အကွာအဝေးနှင့်ဧရိယာတွက်ချက်ခြင်းများသည် :guilabel:`Ellipsoid` (ဘဲဥပုံစက်လုံး) တွင် အလုံးစုံအခြေခံထားပါသည်။ ၎င်းသည်အောက်ပါတို့ဖြစ်နိုင်ပါသည်-

  * **None/Planimetric (မည်သည်မျှမဟုတ်/ပြင်ညီ)** - ရရှိလာသည့်တန်ဖိုးများသည် cartesian အတိုင်းအတာများ ဖြစ်သည်။ :menuselection:`Settings -->` |options| :menuselection:`Options -->` |crs| :menuselection:`CRS Handling` menu မှတဆင့် ဤရွေးချယ်မှုကို project အသစ်များအတွက် default အနေဖြင့် သတ်မှတ်နိုင်ပါသည်။ 
  * **Custom (စိတ်ကြိုက်)** တစ်ခု - semi-major ဝင်ရိုးနှင့် semi-minor ဝင်ရိုးတို့၏တန်ဖိုးများကို သတ်မှတ်ရန် လိုအပ်ပါသည်။ 
  * သို့မဟုတ် ကြိုတင်သတ်မှတ်ထားသည့်စာရင်းမှ ရှိပြီးသားတစ်ခု (Clarke 1866 ၊ Clarke 1880 IGN ၊ New International 1967 ၊ WGS 84...)

* အလျားနှင့် ပတ်လည်အနားများတိုင်းတာရန်အတွက် :guilabel:`units for distance measurements` (အကွာအဝေးတိုင်းတာခြင်းအတွက် ယူနစ်များ) နှင့် :guilabel:`units for area measurements` (ဧရိယာ တိုင်းတာခြင်းအတွက် ယူနစ်များ)။ ဤ setting များသည် QGIS တွင် သတ်မှတ်ထားသည့်ယူနစ်များအတိုင်း default ဖြစ်သော်လည်း လက်ရှိအသုံးပြုနေသော project အတွက် အစားထိုးပြင်ဆင်အသုံးပြုနိုင်သည်။ ၎င်းတို့ကို အောက်ပါတို့တွင် အသုံးပြုပါသည်-

  * Attribute ဇယား field update ဘား
  * Field calculator တွက်ချက်ခြင်းများ
  * Identify tool မှ ရရှိလာသော အလျား၊ ပတ်လည်အနားနှင့် ဧရိယာတန်ဖိုးများ
  * တိုင်းတာသည့် dialog တွင်ဖော်ပြနေသည့် default ယူနစ်


.. _coordinate_and_bearing:

:guilabel:`Coordinate and Bearing display` (ကိုဩဒိနိတ်နှင့်လားရာပြသခြင်း) တွင် အောက်ပါတို့၏ ပြသမည့်ပုံစံကို စိတ်ကြိုက်သတ်မှတ်နိုင်ပါသည်- 

* QGIS အခြေအနေပြဘားရှိ :guilabel:`Coordinates` (ကိုဩဒိနိတ်များ) box နှင့် |identify| :sup:`Identify features` tool ရလာဒ်များ၏ :guilabel:`Derived` (ရရှိလာသော) အပိုင်းတွင် ဖော်ပြထားသည့် ကိုဩဒိနိတ်များ
* မြေပုံ canvas ရွှေ့ခြင်းလားရာအတွက် အခြေအနေပြဘားတွင် ပြသထားသည့် လားရာတန်ဖိုးနှင့် |measureBearing| :sup:`Measure bearing` (လားရာတိုင်းတာခြင်း) tool ဖြင့်တိုင်းတာသည့် တန်ဖိုး

ရရှိနိုင်သည့် parameter များမှာ- 

* အောက်ပါတို့မှ တစ်ခုမဟုတ်တစ်ခု အသုံးပြု၍ :guilabel:`Display coordinates (ကိုဩဒိနိတ်ပြသခြင်း)` -

  * Project ၏ CRS ကို အခြေခံထားသည့် ``Map Units`` (မြေပုံယူနစ်များ) 
  * ``Map Geographic (degrees)`` - ပထဝီဝင်ဆိုင်ရာ (geographic) အမျိုးအစားဖြစ်လျှင် project ၏ CRS ကိုအခြေခံပြီး ထိုသို့မဟုတ်ပါက ၎င်းနှင့် ဆက်စပ်သော ပထဝီဝင်ဆိုင်ရာ CRS ကို အသုံးပြုပါသည်။ ဤအချက်သည် ဥပမာအားဖြင့်- ကမ္ဘာမြေမဟုတ်သည့် (နေ၊ လ၊ ဂြိုလ် စသည်တို့) အရာများအတွက် အထောက်အကူဖြစ်စေမည်ဖြစ်ပါသည်။ 
  * သို့မဟုတ် ``Custom Projection Units`` (စိတ်ကြိုက် မြေပုံအရိပ်ချခြင်းယူနစ်များ) - ကိုဩဒိနိတ်ပြသမှုအတွက် အသုံးပြုလိုသော မည်သည့် CRS တွင်မဆို မူတည်စေမည် ဖြစ်ပါသည်။ 
 
* :guilabel:`Coordinate CRS` (ကိုဩဒိနိတ် CRS) ရွေးချယ်ခြင်းတွင် ဖော်ပြလိုသည့် နည်းလမ်းပေါ်မူတည်၍ အသုံးပြုမည့် CRS ကို ကြည့်ရှုခြင်း သို့မဟုတ် သတ်မှတ်ခြင်းတို့ကို ပြုလုပ်နိုင်ပါသည်။ 
* :guilabel:`Coordinate format` (ကိုဩဒိနိတ်ပုံစံ) - ``Decimal Degrees`` (ဒဿမ ဒီဂရီ)၊ 
  ``Degrees, Minutes`` (ဒီဂရီ၊ မိနစ်) သို့မဟုတ် ``Degrees, Minutes, Seconds`` (ဒီဂရီ၊ မိနစ်၊ စက္ကန့်) များအနေဖြင့် သတ်မှတ်နိုင်ပါသည်။ ထို့အပြင် ၎င်းတို့ကို အောက်ပါအတိုင်း ဖော်ပြသင့်/မသင့်ကိုလည်း သတ်မှတ်ပေးနိုင်သည်-

   * |unchecked| :guilabel:`Show directional suffix` (ဦးတည်ရာလမ်းကြောင်းနောက်ဆက်စာလုံးပြသခြင်း)
   * |unchecked| :guilabel:`Show leading zeros for minutes and seconds` (မိနစ်နှင့် စက္ကန့်များအတွက် ရှေ့တွင်ရှိသော သုညများ ပြသခြင်း) 
   * |unchecked| :guilabel:`Show leading zeros for degrees` (ဒီဂရီများအတွက် ရှေ့တွင်ရှိသော သုညများပြသခြင်း)
   * |unchecked| :guilabel:`Show trailing zeros` (နောက်တွဲ သုညများ ပြသခြင်း) 

* :guilabel:`Coordinate precision` (ကိုဩဒိနိတ်တန်ဖိုးတိကျမှု) - ဒဿမကိန်းအရေအတွက်ကို အလိုအလျောက် သတ်မှတ်နိုင်ပေးပါသည် (CRS ၏ အမျိုးအစားမှရယူထားခြင်းဖြစ်သည်) သို့မဟုတ် ကိုယ်တိုင် သတ်မှတ်နိုင်ပါသည်။ 
* :guilabel:`Coordinate order` (ကိုဩဒိနိတ်အစဉ်) - CRS ၏ မူလအစဉ်လိုက်အတိုင်း  (``Default``) အနေဖြင့် ကိုဩဒိနိတ်များကို ရွေးချယ်ပြသပါသည်။ သို့မဟုတ် ``Easting, Northing (Longitude, Latitude)`` သို့မဟုတ် ``Northing, Easting (Latitude, Longitude)`` အစဉ်လိုက်ကိုလည်း ပြောင်းလဲရွေးချယ်နိုင်ပါသည်။
* :guilabel:`Bearing format` (လားရာပုံစံ) တွင် အသုံးပြုနိုင်သည့်တန်ဖိုးမှာ ``E/W နောက်ဆက်စာလုံးဖြင့် 0 မှ 180°`` ၊ ``-180 မှ +180°`` သို့မဟုတ် ``0 မှ 360°`` ဖြစ်သည်။ :guilabel:`Decimal places` (ဒဿမနေရာ) အရေအတွက်ကို သတ်မှတ်နိုင်သကဲ့သို့ :guilabel:`Show trailing zeros` (နောက်တွဲ သုညများပြသခြင်း) လုပ်/မလုပ်ကိုလည်း သတ်မှတ်နိုင်သည်။ 


.. _figure_general_tab:


.. figure:: img/project_general.png
   :align: center

   Project Properties dialog ၏ အထွေထွေ tab


.. _project_metadata:


Metadata Properties (Metadata ဂုဏ်သတ္တိများ)
---------------------------------------------

|editMetadata| :guilabel:`Metadata` tab တွင် အသုံးပြုသူ၊ ဖန်တီးပြုလုပ်သောရက်စွဲ၊ ဘာသာစကား၊ အကျဉ်းချုပ်များ၊ အမျိုးအစားများ၊ အဓိကစကားလုံးများ၊ ဆက်သွယ်ရန်အသေးစိတ်အချက်များ၊ link များနှင့် မှတ်တမ်းများ ပါဝင်သော အသေးစိတ် metadata များကို သတ်မှတ်ပေးနိုင်ပါသည်။ သီးခြား သတ်မှတ်ထားသော field များ မဖြစ်မနေဖြည့်သွင်းရန် ပြုလုပ်ထားခြင်း မရှိသော်လည်း အဆိုပါ ဖြည့်သွင်းထားသော field များကို စစ်ဆေးနိုင်သည့် အတည်ပြုလုပ်ဆောင်မှုတစ်ခုလည်း ရှိပါသည်။ အသေးစိတ် အချက်အလက်များကို သိရှိလိုပါက :ref:`vector layer metadata properties (vector layer ၏ metadata ဂုဏ်သတ္တိများ) <vectormetadatamenu>` တွင် ကြည့်ရှုနိုင်ပါသည်။


View Settings (မြင်ကွင်းဆိုင်ရာ setting များ)
----------------------------------------------

.. _figure_viewsettings_tab:

.. figure:: img/project_viewsettings.png
   :align: center

   Project Properties dialog ၏ မြင်ကွင်းဆိုင်ရာ setting tab

|overlay| :guilabel:`View Settings` tab တွင် project ၏ မြေပုံမျက်နှာပြင်ကို ကိုင်တွယ်ထိန်းချုပ်ရန် နည်းလမ်းများရှိပြီး အောက်ဖော်ပြပါဆောင်ရွက်မှုများကို လုပ်ဆောင်နိုင်ပါသည်-

* :guilabel:`Project predefined scales (Project ၏ ကြိုတင်သတ်မှတ်ထားသော စကေးများ)` ကို သတ်မှတ်ခြင်း - Global :ref:`predefined scales (ကြိုတင်သတ်မှတ်ထားသည့်စကေးများ) <predefinedscales>` ကို အစားထိုးဆောင်ရွက်မည့် စကေးနှင့်ပတ်သက်သော drop-down widget များတွင် ပြသမည့် စကေးများစာရင်းကို သတ်မှတ်ခြင်းဖြစ်သည်။ စကေးနှင့်ပတ်သက်သော drop-down widget များမှာ အခြေအနေပြဘားရှိ :guilabel:`Scale` (စကေး)၊ မြင်နိုင်သည့်စကေးရွေးချယ်ပေးသည့်အရာ သို့မဟုတ် အဓိကမဟုတ်သော (secondary) နှစ်ဖက်မြင်မြေပုံမြင်ကွင်း setting တို့ဖြစ်ပါသည်။


.. _project_full_extent:

* :guilabel:`Set Project full Extent` (Project ၏ extent အပြည့်သတ်မှတ်ခြင်း) - မြေပုံမြင်ကွင်းအပြည့် (|zoomFullExtent|) ကိုချဲ့၍ကြည့်သောအခါ Layer များအားလုံး၏ extent အစား ဤသတ်မှတ်ထားသော extent ကို အသုံးပြုမည်ဖြစ်ပါသည်။ ၎င်းသည် project တွင် ဝက်ဘ် Layer များ၊ နိုင်ငံအဆင့် Layer များနှင့် ကမ္ဘာအဆင့် Layer များ ပါဝင်နေပြီး အမှန်တကယ်စိတ်ဝင်စားသော ဧရိယာသည် သေးငယ်သော ဧရိယာဖြစ်နေသောအခါ အလွန်အသုံးဝင်ပါသည်။ Project ၏ extent အပြည့် ကိုဩဒိနိတ်များကို :ref:`extent selector (နယ်ပယ်အကျယ်အဝန်းရွေးချယ်ပေးသည့်အရာ) <extent_selector>` widget ဖြင့် သတ်မှတ်နိုင်ပါသည်။
 
CRS Properties (ရည်ညွှန်းကိုဩဒိနိတ်စနစ်ဆိုင်ရာ ဂုဏ်သတ္တိများ)
--------------------------------------------------------------

.. note:: QGIS သည် project ၏ မြေပုံအရိပ်ချစနစ် (projection) များကို ကိုင်တွယ်လုပ်ဆောင်ပုံနှင့်ပတ်သက်၍ ပိုမိုသိရှိနိုင်ရန် :ref:`label_projections` တွင် ပါရှိသော ၎င်းနှင့်သက်ဆိုင်သည့်အပိုင်းတွင် ဖတ်ရှုနိုင်ပါသည်။

|crs| :guilabel:`CRS` tab တွင် လက်ရှိဆောင်ရွက်နေသော project တွင် ရည်ညွှန်းကိုဩဒိနိတ်စနစ်ကို သတ်မှတ်ပေးနိုင်ပါသည်။ ၎င်းသည် အောက်ပါအတိုင်း ဖြစ်နိုင်ပါသည်-

* |checkbox| :guilabel:`No CRS (or unknown/non-Earth projection)` (CRS မရှိ (သို့မဟုတ် မသိသော/ ကမ္ဘာမြေနှင့် မသက်ဆိုင်သော အရိပ်ချစနစ်)) - Layer များကို ၎င်းတို့၏ မူရင်းကိုဩဒိနိတ်များပေါ်အခြေခံ၍ ရေးဆွဲမည်ဖြစ်သည်။  
* သို့မဟုတ် ရှိနေပြီးသား ရည်ညွှန်းကိုဩဒိနိတ်စနစ်တစ်ခု - *geographic* (ပထဝီဝင်ဆိုင်ရာ) ၊ *projected* (အရိပ်ချထားသော) သို့မဟုတ် *user-defined* (အသုံးပြုသူမှသတ်မှတ်ထားသော) ကိုဩဒိနိတ်စနစ်များဖြစ်နိုင်ပါသည်။ Project ထဲသို့ ထည့်သွင်းလိုက်သော Layer များကို ၎င်းတို့မူရင်း CRS ကိုထည့်သွင်းမစဉ်းစားဘဲ ဤ CRS သို့ ချက်ချင်း အစားထိုးပြောင်းလဲပေးသွားမည်ဖြစ်ပါသည်။


Transformations Properties (အသွင်ပြောင်းလဲမှုဆိုင်ရာ ဂုဏ်သတ္တိများ)
--------------------------------------------------------------------

|transformation| :guilabel:`Transformations` tab သည် လက်ရှိ project တွင် အသုံးပြုရန် မူတည်မျက်နှာပြင်ကူးပြောင်းခြင်း (datum transformation) ဦးစားပေးဆောင်ရွက်မှုများကို ပြင်ဆင်သတ်မှတ်ခြင်းဖြင့် Layer များ၏ အရိပ်ချစနစ်ပြောင်းလဲခြင်း setting များကို ကိုင်တွယ်ထိန်းချုပ်နိုင်ရန် ကူညီပေးပါသည်။ ခါတိုင်းလိုပင် ၎င်းတို့သည် သက်ဆိုင်ရာ မည်သည့် global setting များကိုမဆို အစားထိုးပြင်ဆင်မည်ဖြစ်ပါသည်။ အသေးစိတ်သိရှိလိုပါက :ref:`datum_transformation` တွင်ကြည့်ရှုနိုင်ပါသည်။ 


.. _default_styles_properties:

Styles Properties (Style များဆိုင်ရာ ဂုဏ်သတ္တိများ)
----------------------------------------------------

|symbology| :guilabel:`Styles` tab အောက်တွင် အခြားစက်များအကြား project ကို လုံခြုံစိတ်ချစွာ မျှဝေသုံးစွဲနိုင်သော project နှင့်သက်ဆိုင်သည့် သင်္ကေတများနှင့် အရောင်များကို သတ်မှတ်ပြင်ဆင်နိုင်ပါသည်။

:guilabel:`Default Symbols` (Default သင်္ကေတများ) အုပ်စုသည် project အတွင်း သတ်မှတ်ထားသော :file:`.qml` style ဖိုင်တစ်ခုမရှိလျှင် Layer အသစ်များ မည်သို့ရေးဆွဲမည်ကို ကိုင်တွယ်ဆောင်ရွက်နိုင်ပါသည်။ Layer ၏ geometry အမျိုးအစားပေါ်မူတည်၍ :guilabel:`Marker` (အမှတ်အသား)၊ :guilabel:`Fill` (ဖြည့်ခြင်း)၊ :guilabel:`Line` (မျဉ်း) များကို သတ်မှတ်နိုင်သကဲ့သို့ default :guilabel:`Color Ramp` (ရောင်စဉ်တန်း) နှင့်  :guilabel:`Text Format` (စာသားပုံစံများ) (ဥပမာ- အညွှန်းတပ်ခြင်းကို ဖွင့်ထားလျှင်) များကိုလည်း သတ်မှတ်နိုင်ပါသည်။ ၎င်းတို့ထဲမှ မည်သည့် item ကိုမဆို သက်ဆိုင်ရာ drop-down widget မှ :guilabel:`Clear` (ပယ်ဖျက်ခြင်း) ကိုအသုံးပြု၍ reset (မူလအနေအထားသို့ပြန်ပြောင်း) ပြုလုပ်နိုင်ပါသည်။

:guilabel:`Options` (ရွေးချယ်စရာများ) အုပ်စုတွင် အောက်ဖော်ပြပါလုပ်ဆောင်မှုများ ဆောင်ရွက်နိုင်ပါသည်-

* Layer အသစ်များတွင် default :guilabel:`Opacity` (အလင်းပိတ်နှုန်း) တစ်ခုကို သတ်မှတ်ပါ။ 
* |checkbox| :guilabel:`Assign random colors to symbols (သင်္ကေတများကို ကျပန်းအရောင်ထည့်သွင်းခြင်း)` သည် သင်္ကေတများ၏ အဖြည့်အရောင်များကို မွမ်းမံခြင်းဖြစ်ပြီး Layer များအားလုံးအတွက် အရောင်တူများဖြင့် ပုံဖော်ပြသခြင်းကို ရှောင်ရှားစေပါသည်။


.. _figure_default_styles:


.. figure:: img/project_styles.png
   :align: center

   Style များ tab

.. _project_colors:

လက်ရှိလုပ်ဆောင်နေသော project အတွက် သီးခြားအရောင်ကို သတ်မှတ်ထားနိုင်သော ထပ်ဆောင်း ကဏ္ဍတစ်ခုလည်း ပါဝင်ပါသည်။ :ref:`Global colors <colors_options>` ကဲ့သို့ပင် အောက်ဖော်ပြပါ လုပ်ဆောင်မှုများ ဆောင်ရွက်နိုင်ပါသည်- 

* အရောင်ကို |symbologyAdd| :guilabel:`Add` (ပေါင်းထည့်ခြင်း) သို့မဟုတ် |symbologyRemove| :guilabel:`Remove` ဖယ်ရှားခြင်း
* အရောင်ကို |editCopy| :guilabel:`Copy` (ကူးယူခြင်းး) သို့မဟုတ် |editPaste| :guilabel:`Paste` (ကူးချခြင်း)
* :file:`.gpl` ဖိုင်မှ/သို့ အရောင်အစုများကို |fileOpen| :guilabel:`Import` (ထည့်သွင်းခြင်း) သို့မဟုတ် |fileSave| :guilabel:`Export` (ထုတ်ယူခြင်း)

:ref:`Color Selector (အရောင်ရွေးချယ်ပေးသည့်အရာ) <color-selector>` dialog ထဲတွင် အရောင်ပြောင်းလဲရန် သို့မဟုတ်  အစားထိုးရန် စာရင်းထဲရှိ အရောင်တစ်ခုကို Double-click ပြုလုပ်ပါ။ :guilabel:`Label` (အညွှန်း) column တွင် Double-click ပြုလုပ်၍လည်း ၎င်းကိုအမည်ပြောင်းလဲနိုင်ပါသည်။

ထိုအရောင်များကို :guilabel:`Project colors` (Project အရောင်များ) အဖြစ်သတ်မှတ်ပြီး :ref:`color widgets  <color-selector>` ၏ အစိတ်ပိုင်းတစ်ခုအဖြစ် စာရင်းပြုစုထားပါသည်။

.. tip:: **အရောင် widget များကို လျင်မြန်စွာသတ်မှတ်ရန်နှင့် update ပြုလုပ်ရန် project အရောင်များကို အသုံးပြုပါ**

  Project အရောင်များကို ၎င်းတို့၏ အညွှန်း အသုံးပြု၍ ကိုးကားနိုင်ပြီး အသုံးပြုထားသောအရောင် widget များသည် ၎င်းတို့နှင့် တွဲဆက်လျက်ရှိနေမည်ဖြစ်ပါသည်။ ဆိုလိုသည်မှာ များစွာသော property များအတွက် တူညီသောအရောင်များ အကြိမ်ကြိမ်သတ်မှတ်ခြင်းကို ပြုလုပ်စေမည့်အစား၊ နှင့် ဝန်ထုတ်ဝန်ပိုးဖြစ်စေသော update ပြုလုပ်ခြင်းကို ရှောင်ရှားနိုင်ရန် အောက်ပါတို့ကို လုပ်ဆောင်နိုင်ပါသည်- 

  #. အရောင်တစ်ခုကို project အရောင်အဖြစ် သတ်မှတ်ပါ
  #. သတ်မှတ်လိုသော အရောင် property ဘေးရှိ :ref:`data defined override widget (Data ဖြင့်သတ်မှတ်ထားသော အစားထိုးပြင်ဆင်ခြင်း widget) <data_defined>` ကို နှိပ်ပါ။
  #. :guilabel:`Color` (အရောင်) menu ပေါ်တွင် မောက်စ်ကိုတင်ထား၍ project အရောင်ကိုရွေးချယ်ပါ။ ထို့နောက် Property ကို expression ``project_color('color_label')`` ဖြင့် သတ်မှတ်မည်ဖြစ်ပြီး အရောင် widget သည် ထိုအရောင်ကို ထင်ဟပ်ပြသမည်ဖြစ်ပါသည်။
  #. အဆင့်(၂) နှင့် (၃)ကို လိုအပ်သလို ထပ်ခါထပ်ခါဆောင်ရွက်ပါ။
  #. Project အရောင်ကို တစ်ကြိမ်သာ update ပြုလုပ်ပါ။ ပြောင်းလဲမှုသည် ၎င်းကို အသုံးပြုထားသော နေရာတိုင်းတွင် လိုက်လံပြောင်းလဲနေမည်ဖြစ်သည်။

.. _project_data_source_properties:

Data Sources Properties (Data အရင်းအမြစ်ဆိုင်ရာ ဂုဏ်သတ္တိများ)
---------------------------------------------------------------

|openTable| :guilabel:`Data Sources` tab ထဲတွင် အောက်ပါတို့ကို လုပ်ဆောင်နိုင်ပါသည်- 

* :guilabel:`Transaction mode` (လွှဲပြောင်းခြင်းနည်းလမ်း) - Data provider (ဒေတာပံ့ပိုးသူ) ထံသို့  ပြင်ဆင်တည်းဖြတ်မှုများ ပေးပို့မည့်နည်းလမ်းကို သတ်မှတ်ပေးပါသည်။ 

  * :guilabel:`Local Edit Buffer` - Layer များ ပြင်ဆင်တည်းဖြတ်ခြင်း mode ကို အဖွင့်အပိတ်လုပ်သောအခါ သို့မဟုတ် :guilabel:`Save edits` (ပြင်ဆင်တည်းဖြတ်မှုများသိမ်းဆည်းခြင်း) ကို နှိပ်သောအခါ ပြင်ဆင်ဆည်းဖြတ်မှုများကို ကွန်ပျူတာအတွင်း၌ပင် ကြားခံပြုလုပ်ပြီး ဒေတာပံ့ပိုးသူထံပေးပို့ပါသည်။
  * :guilabel:`Automatic Transaction Groups` - Postgres နှင့် geopackage database များကဲ့သို့သော ပံ့ပိုးထားသော data အရင်းအမြစ်များတွင် တူညီသော database များမှအစပြုသော ဇယားများအားလုံး၏ ပြင်ဆင်တည်းဖြတ်မှုအခြေအနေကို တပြိုင်နက်တည်း (synchronize) လုပ်ဆောင်ပြီး ဆာဗာဘက်ခြမ်းလွှဲပြောင်းမှု (server side transaction) တစ်ခုတွင် စေခိုင်းလုပ်ဆောင်ပါသည်။ ထိုနည်းတူစွာ ပြင်ဆင်တည်းဖြတ်ပြောင်းလဲမှုများကို ကွန်ပျူတာအတွင်း၌ကြားခံပြုလုပ်မည့်အစား ၎င်းတို့ကို Layer ပြင်ဆင်တည်းဖြတ်ခြင်း mode အဖွင့်အပိတ်လုပ်သောအခါ သို့မဟုတ် :guilabel:`Save edits` ကိုနှိပ်သောအခါ လွှဲပြောင်းရရှိသည့် database ထဲရှိ transaction (လွှဲပြောင်းမှု) တစ်ခုဆီသို့ တိုက်ရိုက် ပေးပို့ပါသည်။ 
  * :guilabel:`Buffered Transaction Groups` - မည်သည့် provider ထံမှ ရရှိသည်ကို ထည့်သွင်း စဉ်းစားခြင်းမပြုဘဲ ပြင်ဆင်တည်းဖြတ်နိုင်သော layer များ အားလုံးကို တပြိုင်နက်တည်း အဖွင့်အပိတ်ပြုလုပ်ပြီး ပြင်ဆင်တည်းဖြတ်မှုအားလုံး ကို local edit buffer တွင် သိမ်းဆည်းမည်ဖြစ်ပါသည်။ ပြောင်းလဲမှုများကို သိမ်းဆည်းခြင်းသည် layer အားလုံးအပေါ်၌ transaction (လွှဲပြောင်းမှု) တစ်ခုအတွင်းမှာပင် (ပံ့ပိုးသူတစ်ဦးစီအလိုက်) လုပ်ဆောင်မည်ဖြစ်ပါသည်။

  Project အတွင်း ပြင်ဆင်တည်းဖြတ်မှုပြုလုပ်နေသည့် layer မရှိမှသာလျှင် ဤရွေးချယ်မှုကို ပြောင်းလဲနိုင်မည် ဖြစ်ကြောင်း မှတ်သားထားပါ။ 

* |unchecked| :guilabel:`Evaluate default values on provider side` (ပံ့ပိုးသူဘက်မှ default ပါရှိလာသော တန်ဖိုးများကို အကဲဖြတ်ခြင်း) - အမှန်ခြစ်ပါက PostgreSQL ဇယားတစ်ခုတွင် feature အသစ်များ ထည့်သွင်းသည့်အခါ   default တန်ဖိုးအကန့်အသတ်များ ပါဝင်နေသည့် field များကို အကဲဖြတ်မည်ဖြစ်ပြီး ဖွင့်လာသော form ပုံစံတွင် တွေ့မြင်ရမည်ဖြစ်ကာ လွှဲပြောင်းမှုအခိုက်အတန့် (commit moment) ၌ တွေ့မြင်ရမည်မဟုတ်ပါ။ ဆိုလိုသည်မှာ ``nextval('serial')`` ကဲ့သို့ expression အစား :guilabel:`Add Feature` form ထဲရှိ field သည် မျှော်မှန်းတန်ဖိုးကို ပြသလိမ့်မည်ဖြစ်ပါသည် (ဥပမာ- ``25``)။ 
* |unchecked| :guilabel:`Remember editable layer status between sessions` (Session များအကြား ပြင်ဆင်တည်းဖြတ်နိုင်သော Layer အခြေအနေကို မှတ်သားခြင်း) - Project တစ်ခုအတွင်းရှိ ပြင်ဆင်တည်းဖြတ်နိုင်သော Layer များအားလုံးကို project သိမ်းဆည်းစဉ်ကကဲ့သို့ မှတ်သားမည်ဖြစ်ပြီး project ကို ပြန်ဖွင့်သည့်အခါတိုင်းတွင် ထို Layer များကို ချက်ချင်း တည်းဖြတ်ပြင်ဆင်နိုင်စေရန် ပြုလုပ်ပေးမည်ဖြစ်ပါသည်။ 


.. _project_layer_capabilities:

* :guilabel:`Layers Capabilities` (Layer စွမ်းဆောင်ရည်များ) ကို ပြင်ဆင်သတ်မှတ်ပါ။ ဆိုလိုသည်မှာ-

  * မည်သည့် layer များကို ``identifiable`` (ဖော်ထုတ်ပြသနိုင်သော) ပြုလုပ်နိုင်မည်ကို သတ်မှတ်ပါ (သို့မဟုတ် သတ်မှတ်ခြင်းကို ပိတ်ပါ)၊ ဆိုလိုသည်မှာ အဆိုပါ layer များသည် :ref:`identify tool <identify>` ကို တုံ့ပြန်မည်ဖြစ်ပါသည်။ Default အားဖြင့် layer များကို query ပြုလုပ်နိုင်အောင် သတ်မှတ်ထားပါသည်။ 
  * Layer တစ်ခုကို ``read-only`` အဖြစ် ပေါ်လာသင့်/မသင့် သတ်မှတ်ပါ၊ ဆိုလိုသည်မှာ layer တစ်ခုကို data ပံ့ပိုးသူဘက်မှ လုပ်ဆောင်နိုင်စွမ်းများ မပါဝင်ဘဲ အသုံးပြုသူမှ ပြင်ဆင်တည်းဖြတ်နိုင်မည် မဟုတ်ပါ။ ၎င်းသည် အားနည်းသောကာကွယ်နည်းဖြစ်သော်လည်း file အခြေခံသော layer များနှင့်အလုပ်လုပ်ဆောင်သောအခါ နောက်ဆုံးအသုံးပြုသူမှ data များကို မွမ်းမံပြင်ဆင်ခြင်းမှ လျင်မြန်လွယ်ကူစွာ ကာကွယ်ပေးစေနိုင်ပါသည်။
  * မည်သည့် layer များသည် ``searchable`` (ရှာဖွေနိုင်သော) ဖြစ်/မဖြစ်ကို သတ်မှတ်ပါ၊ ဆိုလိုသည်မှာ အဆိုပါ layer များကို :ref:`locator widget (တည်နေရာပြ widget) <locator_options>` ဖြင့် query ပြုလုပ်နိုင်မည်ဖြစ်ပါသည်။ Default အားဖြင့် Layer များကို ရှာဖွေနိုင်အောင် သတ်မှတ်ထားပါသည်။
  * မည်သည့် layer များကို ``required`` (လိုအပ်သော) အဖြစ်ထားမည်ကို သတ်မှတ်ပါ။ စာရင်းထဲရှိ အမှန်ခြစ်ထားသော  layer များကို project မှ အမှတ်တမဲ့ ဖယ်ရှားမိခြင်းမှ ကာကွယ်ထားမည်ဖြစ်ပါသည်။ 
  * မည်သည့် layer များကို ``private`` (သီးသန့်) အဖြစ်ထားမည်ကို သတ်မှတ်ပါ၊ ဆိုလိုသည်မှာ အဆိုပါ layer များကို :guilabel:`Layers` panel မှ ဖျောက်ထားပေးမည်ဖြစ်ပါသည်။ ဤသတ်မှတ်ချက်သည် project တွင် လိုအပ်သော်လည်း ရည်ညွှန်းချက် ဖွဲ့စည်းပုံ (legend tree) နှင့် အခြားသော layer ရွေးချယ်မှု tool များတွင် ရှုပ်ထွေးမနေစေလိုသော (basemap၊ ချိတ်ဆက်ခြင်း၊ တန်ဖိုးဆက်စပ်မှုများအတွက် ရှာဖွေမှုများ၊ ဖြစ်နိုင်ချေရှိဆုံး spatial layer များကဲ့သို့သော) အပို layer များ အတွက် ရည်ရွယ်ပါသည်။ အကယ်၍ မြင်နိုင်စေရန် သတ်မှတ်လိုက်လျှင် အဆိုပါ layer များကို မြေပုံ canvas ပေါ်တွင် ပြသနေမည်ဖြစ်ပြီး print layout ရည်ညွှန်းချက်တွင် ပုံဖော်ပြသနေမည် ဖြစ်ပါသည်။ လုပ်ဆောင်မှု တစ်ခုခုဆောင်ရွက်လိုသောအခါ ၎င်း layer များကို ယာယီ ဖွင့်ထားနိုင်ရန် :guilabel:`Layers` panel အပေါ်ဘက် toolbar ရှိ |filterMap| :menuselection:`Filter legend --> Show private layers (သီးသန့် Layer များကိုပြသခြင်း)` option ကို အသုံးပြုပါ။ 

  :guilabel:`Layers Capabilities (Layer များ၏စွမ်းဆောင်ရည်များ)` ဇယားသည် အောက်ဖော်ပြပါတို့ကို လုပ်ဆောင်နိုင်ရန် အဆင်ပြေစေသော tool များကို ပံ့ပိုးပေးပါသည်- 

  * ဇယားအကွက်ငယ်များစွာကို ရွေးချယ်၍ ၎င်းတို့၏ အမှန်ခြစ်အခြေအနေများ ပြောင်းလဲရန် :guilabel:`Toggle Selection` (ရွေးချယ်ထားသည်များကို အဖွင့်အပိတ်ပြုလုပ်ခြင်း) ကို နှိပ်ပါ၊ 
  * တည်နေရာနှင့် မသက်ဆိုင်သော layer များကို layer များစာရင်းမှ စစ်ထုတ် (filter) ရန် |unchecked| :guilabel:`Show spatial layers only` (တည်နေရာနှင့်သက်ဆိုင်သော Layer များကိုသာပြသခြင်း) ကို အသုံးပြုပါ၊
  * |search| :guilabel:`Filter layers…` (Layer များကို စစ်ထုတ်ခြင်း) ကိုအသုံးပြု၍ ပြင်ဆင်သတ်မှတ်လိုသော သီးခြား layer ကို လျင်မြန်စွာ ရှာဖွေပါ။ 

* :guilabel:`Advanced Settings` အုပ်စုအောက်တွင် |unchecked| :guilabel:`Trust project when data source has no metadata` (Data အရင်းအမြစ်တွင် metadata မပါရှိသောအခါ project ကို ယုံကြည်ပါ) ကို ရွေးချယ်နိုင်ပါသည် - Data စစ်ဆေးမှုများကိုကျော်ပစ်၍ project ထည့်သွင်းခြင်းကို မြန်ဆန်စေရန်ဖြစ်သည်။ ကြီးမားသော database များ ကြည့်ရှုခြင်း သို့မဟုတ် ရုပ်လုံးဖော်ကြည့်ရှုခြင်းများပါဝင်သော QGIS Server သို့မဟုတ် project များတွင် အသုံးဝင်ပါသည်။ Layer များ၏ extent ကို (Data အရင်းအမြစ်များအစား) QGIS project ဖိုင်မှ ဖတ်ရှုလိမ့်မည်ဖြစ်ပြီး PostgreSQL ပံ့ပိုးသူ အသုံးပြုသောအခါ ကြည့်ရှုခြင်းများနှင့် ရုပ်လုံးဖော်ကြည့်ရှုခြင်းများအတွက် primary key သီးသန့်ဖြစ်မှုကို စစ်ဆေးလိမ့်မည် မဟုတ်ပါ။

.. _figure_datasources_tab:

.. figure:: img/project_datasources.png
   :align: center

   Data အရင်းအမြစ်များ tab

.. _project_relations:


Relations Properties (ဆက်နွယ်မှုဆိုင်ရာ ဂုဏ်သတ္တိများ)
-------------------------------------------------------

1:n (တစ်ခုနှင့် n အရေအတွက်) ဆက်နွယ်မှုနှင့် ရုပ်သွင်ပြောင်းလဲခြင်း ဆက်နွယ်မှုများကို သတ်မှတ်ပေးနိုင်ရန် |relations| :guilabel:`Relations` (ဆက်နွယ်မှုများ) tab ကို အသုံးပြုပါသည်။ ထိုဆက်နွယ်မှုများကို project property များ dialog တွင် သတ်မှတ်ပါသည်။ Layer တစ်ခုအတွက် ဆက်နွယ်မှုများ တည်ရှိပြီးသည်နှင့် form view ထဲရှိ အသုံးပြုသူမှမြင်ရသောမျက်နှာပြင် (user interface) အသစ်တစ်ခု (ဥပမာ- feature တစ်ခုကို identify ပြုလုပ်သောအခါနှင့် ၎င်း၏ပုံစံကို ဖွင့်သောအခါ) သည် ဆက်နွယ်သော တည်ရှိမှုများကို စာရင်းပြုစုထားမည်ဖြစ်ပါသည်။ ၎င်းသည် ဥပမာ- ပိုက်လိုင်း၏ အလျား သို့မဟုတ် လမ်းပိုင်းတစ်ခု၏ အလျားကို စစ်ဆေးခြင်းမှတ်တမ်းကို ဖော်ပြရန် အားကောင်းသော နည်းလမ်းတစ်ခုဖြစ်ပါသည်။ 1:n ဆက်နွယ်မှုအကြောင်းကို :ref:`vector_relations` ကဏ္ဍတွင် ပိုမိုလေ့လာနိုင်ပါသည်။ 


.. _figure_relations_tab:

.. figure:: img/project_relations.png
   :align: center

   ဆက်နွယ်မှုများ tab


Variables Properties (ကိန်းရှင်များဆိုင်ရာ ဂုဏ်သတ္တိများ)
----------------------------------------------------------

|expression| :guilabel:`Variables` (ကိန်းရှင်များ) tab သည် project အဆင့်တွင်ရရှိနိုင်သော (global အဆင့် variable များအပါအဝင်) variable များအားလုံးကို စာရင်းပြုစုထားပါသည်။ ထို့အပြင် ၎င်းသည် project အဆင့် variable များအားလုံးကို အသုံးပြုသူမှ စီမံခန့်ခွဲနိုင်စေပါသည်။ စိတ်ကြိုက် project အဆင့် variable အသစ် တစ်ခု ထည့်သွင်းရန် |symbologyAdd| ကို နှိပ်ပါ။ ထိုနည်းတူစွာ စာရင်းထဲမှ စိတ်ကြိုက် project အဆင့် variable တစ်ခုကို ရွေးချယ်ပြီး ၎င်းကိုဖယ်ရှားရန် |symbologyRemove| ကို နှိပ်ပါ။ Variable များ အသုံးပြုမှုနှင့် ပတ်သက်၍ အချက်အလက်များ ပိုမို သိရှိလိုပါက General Tools :ref:`general_tools_variables` ကဏ္ဍတွင် လေ့လာနိုင်ပါသည်။
 
.. _project_macros:


Macros Properties (Macro များဆိုင်ရာ ဂုဏ်သတ္တိများ)
----------------------------------------------------

|action| :guilabel:`Macros` tab ကိုအသုံးပြုခြင်းဖြင့် project များအတွက် Python macro များကို တည်းဖြတ်ပြင်ဆင်နိုင်ပါသည်။ လတ်တလောအသုံးပြုနိုင်သည့် macro များမှာ ``openProject()`` (ပရောဂျက်ဖွင့်ခြင်း)၊ ``saveProject()`` (ပရောဂျက်သိမ်းဆည်းခြင်း) နှင့် ``closeProject()`` (ပရောဂျက်ပိတ်ခြင်း) တို့ဖြစ်ပါသည်။

.. _figure_macro_tab:

.. figure:: img/macro.png
   :align: center

   Macro setting များ

QGIS Server Properties (QGIS ဆာဗာဆိုင်ရာ ဂုဏ်သတ္တိများ)
--------------------------------------------------------

|overlay| :guilabel:`QGIS Server` (QGIS ဆာဗာ) tab သည် မိမိ၏ project အား အွန်လိုင်းတွင် ဖြန့်ဝေရန် ပြင်ဆင်သတ်မှတ်နိုင်စေပါသည်။ ဤနေရာတွင် QGIS server WMS နှင့် WFS ၏လုပ်ဆောင်နိုင်စွမ်းများ၊ extent နှင့် CRS ကန့်သတ်ချက်များအကြောင်း အချက်အလက်များကို သတ်မှတ်ပေးနိုင်ပါသည်။ အချက်အလက်များပိုမိုသိရှိလိုပါက :ref:`Creatingwmsfromproject` (Project ကို ပြင်ဆင်သတ်မှတ်ခြင်း) ကဏ္ဍနှင့် နောက်ဆက်တွဲကဏ္ဍတွင် လေ့လာနိုင်ပါသည်။


.. _figure_qgis_server_tab:

.. figure:: img/project_qgis_server.png
   :align: center

   QGIS Server setting များ

.. index:: Temporal; Project time range
.. _project_temporal:


Temporal Properties (အချိန်ကာလဆိုင်ရာ ဂုဏ်သတ္တိများ)
-----------------------------------------------------

:guilabel:`Start date` (စတင်ရက်) နှင့် :guilabel:`End date` (ပြီးဆုံးရက်) ကို မိမိကိုယ်တိုင် ထည့်သွင်းခြင်းဖြင့်သော်လည်းကောင်း (သို့မဟုတ်) လက်ရှိ project ရှိ အချိန်ကာလဆိုင်ရာ layer များမှ တွက်ချက်ခြင်းဖြင့်လည်းကောင်း မိမိ project ၏ အချိန်ကာလအပိုင်းအခြား သတ်မှတ်ရာတွင် |temporal| :guilabel:`Temporal` (အချိန်ကာလဆိုင်ရာ) tab ကို အသုံးပြုပါသည်။ မြေပုံ canvas :ref:`temporal navigation (အချိန်ကာလညွှန်ပြခြင်း) <maptimecontrol>` ကို စီမံဆောင်ရွက်ရန် project time range (အချိန်အပိုင်းအခြား) ကို :guilabel:`Temporal controller panel` (အချိန်ကာလများကို ထိန်းချုပ်သည့် Panel) ထဲတွင်အသုံးပြုနိုင်ပါသည်။

.. _figure_temporal_tab:

.. figure:: img/project_temporal.png
   :align: center

   Project Temporal (အချိန်ကာလဆိုင်ရာ) tab


.. index:: Terrain; Elevation
.. _project_terrain:

Terrain Properties (မြေမျက်နှာသွင်ပြင်အနေအထားဆိုင်ရာ ဂုဏ်သတ္တိများ)
--------------------------------------------------------------------

|layoutItem3DMap| :guilabel:`Terrain` tab တွင် မြေမျက်နှာသွင်ပြင်အနေအထား (terrain) နှင့် ပင်လယ်ရေမျက်နှာပြင်အထက်အမြင့်ပေ (elevation) တို့အတွက် default setting များကို ပြင်ဆင်သတ်မှတ်နိုင်ပါသည်။ Project ထဲတွင် :ref:`3d map(သုံးဖက်မြင်မြေပုံ) <label_3dmapview>` အသစ်တစ်ခုကို ဖန်တီးသည့်အခါ မြေပုံသည် project အတွက်သတ်မှတ်ထားသော terrain setting များကို default အနေဖြင့် အသုံးပြုမည်ဖြစ်ပါသည်။ Project ၏ အမြင့် (elevation) နှင့်ပတ်သက်သော setting များကို Profile tool ဖြင့်လည်း လုပ်ဆောင်နိုင်မည်ဖြစ်သည်။


.. todo: Add link to the profile tool when available

.. _figure_terrain_tab:

.. figure:: img/project_terrain.png
   :align: center

   Project Terrain (မြေမျက်နှာသွင်ပြင်အနေအထား) tab

Terrain နှင့် elevation ရွေးချယ်စရာများကို အောက်ပါတို့အတွက် ရရှိနိုင်ပါသည်-

* :guilabel:`Terrain height (မြေမျက်နှာသွင်ပြင်အနေအထားအမြင့်)` setting ဖြင့် :guilabel:`Flat terrain` (မြေပြန့်)
* :guilabel:`DEM (Raster Layer)` - :guilabel:`Raster layer` ၊ လှိုင်းအလွှာ (band) တန်ဖိုးများအတွက် အသုံးပြုမည့် :guilabel:`Vertical scale` (ဒေါင်လိုက်စကေး) factor နှင့် ဒေါင်လိုက် :guilabel:`Offset` (အရွေ့) များကို သတ်မှတ်ရန် setting များပါဝင်သည်။
* :guilabel:`Mesh` - :guilabel:`Mesh layer` ၊ မျဉ်းအဆစ် (vertex) Z တန်ဖိုးများအတွက် အသုံးပြုမည့် :guilabel:`Vertical scale` (ဒေါင်လိုက်စကေး) factor နှင့် ဒေါင်လိုက် :guilabel:`Offset` (အ‌ရွေ့) များကို သတ်မှတ်ရန် setting များပါဝင်သည်။

ဤ setting များကို 3D မြေပုံ :ref:`configuration dialog (ပြင်ဆင်သတ်မှတ်ခြင်း dialog) <scene_configuration>` မှ အစားထိုးပြင်ဆင်နိုင်ပါသည်။


.. index:: Sensors; Readings
.. _project_sensors:


Sensors Properties (အာရုံခံကိရိယာများဆိုင်ရာ ဂုဏ်သတ္တိများ)
------------------------------------------------------------

Sensors (အာရုံခံကိရိယာများ) ကို ပြင်ဆင်သတ်မှတ်ရန်နှင့် ၎င်းတို့၏ ချိတ်ဆက်မှုအခြေအနေများကို အဖွင့်အပိတ်ပြုလုပ်ရန် |sensor| :guilabel:`Sensors` (အာရုံခံကိရိယာများ) tab ကို အသုံးပြုပါသည်။ ၎င်းကိုဖွင့်ထားလျှင် sensor များသည် data များကို နောက်ကွယ်မှာပင် သူ့အလိုလို စုဆောင်းသွားမည်ဖြစ်ပြီး နောက်ဆုံးရ data များကို expression များနှင့် python script များအဖြစ် ရရှိစေမည်ဖြစ်ပါသည်။ 


.. _figure_sensors_tab:

.. figure:: img/project_sensors.png
   :align: center


   Project Sensor များဆိုင်ရာ tab

Sensor အသစ်တစ်ခု ထည့်သွင်းရန် |symbologyAdd| ခလုတ်ကို နှိပ်ပါ။ Setting များ panel အခွဲတစ်ခု ပွင့်လာမည်ဖြစ်ပြီး အောက်ပါတို့ကို ပြင်ဆင်သတ်မှတ်နိုင်ပါသည်- 

* :guilabel:`Sensor name` (Sensor အမည်) - Expression များနှင့် python script များတွင် sensor တန်ဖိုးများကိုထုတ်ယူရန် အသုံးပြုနိုင်သည်၊
* :guilabel:`Sensor type` (Sensor အမျိုးအစား) - TCP ၊ UDP ၊ serial port ၊ စသည်တို့နှင့်
* ထပ်ဆောင်း အမျိုးအစားအလိုက်သီးသန့်ဖြစ်သော (type-specific) အသေးစိတ်အချက်အလက်များ (ဥပမာ- host name နှင့် port)

.. _figure_sensors_configuration:

.. figure:: img/project_sensors_configuration.png
   :align: center

   Sensor setting များပါဝင်သည့် panel အခွဲ

Sensor တစ်ခုကို သတ်မှတ်ပြင်ဆင်ပြီးပါက sensor ကိုချိတ်ဆက်ရန် |start| :sup:`Start` ခလုတ်ကို အသုံးပြုနိုင်ပါသည်။ တစ်ကြိမ် လုပ်ဆောင်ပြီးလျှင် နောက်ဆုံး စုဆောင်းခဲ့သော data ကို sensor ဇယား၏ :guilabel:`Last value (နောက်ဆုံးတန်ဖိုး)` column တွင် ပြသမည်ဖြစ်ပါသည်။ 


.. index:: Customization
.. _sec_customization:

Customization (စိတ်ကြိုက်ပြင်ဆင်ခြင်း)
=======================================

:guilabel:`Customization` dialog တွင် QGIS user interface ထဲရှိ element အားလုံးနီးပါးကို ဖွင့်ထားခြင်း/ပိတ်ထားခြင်း လုပ်ဆောင်နိုင်ပါသည်။ လိုအပ်သော icon များ၊ menu များ သို့မဟုတ် panel များသာ ပါဝင်သည့် ပေါ့ပါးသော QGIS version ဖြင့် နောက်ဆုံးအသုံးပြုသူများသို့ ပံ့ပိုးပေးချင်သည့်အခါ ဤအရာသည် အလွန်အသုံးဝင်ပါသည်။

.. note::
   ပြောင်းလဲမှုများကို အသုံးမချမီတွင် QGIS ကို ပြန်လည်စတင်ရန် (restart) လိုအပ်ပါသည်။ 

.. _figure_customization:

.. figure:: img/customization.png
   :align: center

   Customization (စိတ်ကြိုက်ပြင်ဆင်ခြင်း) dialog


|checkbox| :guilabel:`Enable customization` ကို အမှန်ခြစ်ခြင်းသည် QGIS ကို စိတ်ကြိုက်ပြင်ဆင်ရန်အတွက် ပထမဆုံးအဆင့်ဖြစ်ပါသည်။ ဤကဲ့သို့ အမှန်ခြစ်လိုက်ခြင်းဖြင့် toolbar နှင့် widget panel ရှိ box များကို အမှန်ခြစ်ဖြုတ်ခြင်းများ ပြုလုပ်နိုင်ပြီး အချို့သော GUI item များကို ပိတ်ထားနိုင်ပါသည်။

ပြင်ဆင်သတ်မှတ်နိုင်သော အရာများမှာ-

* **Menu** တစ်ခု သို့မဟုတ် :ref:`label_menubar` မှ ၎င်းတို့ထဲရှိ အချို့ menu အခွဲများ
* **Panel** တစ်ခုလုံး (:ref:`sec_panels_and_toolbars` တွင် ကြည့်ရှုပါ)
* :ref:`label_statusbar` (အခြေအနေပြဘား) ထဲတွင်ဖော်ပြထားသော **Status bar** သို့မဟုတ် ၎င်းတို့ထဲမှ အချို့ item များ
* **Toolbar** တစ်ခု - ဘားတစ်ခုလုံး သို့မဟုတ် ၎င်း၏ icon များအချို့
* သို့မဟုတ် QGIS ထဲရှိ မည်သည့် dialog မဆိုမှ **widget** တစ်ခုခု - label (အညွှန်း)၊ button (ခလုတ်)၊ combobox(ပေါင်းစပ် box)......

|select| :sup:`Switch to catching widgets in main application` (အဓိက application တွင် widget များကို ချိတ်တွဲခြင်းသို့ ပြောင်းခြင်း) ဖြင့် QGIS interface ပေါ်တွင် ဖျောက်ထားလိုသော Item တစ်ခုကို နှိပ်နိုင်ပြီး QGIS သည် Customization dialog တွင် သက်ဆိုင်ရာ entry ကို အလိုအလျောက်အမှန်ခြစ်ဖြုတ်မည်ဖြစ်ပါသည်။ :guilabel:`Search` (ရှာဖွေခြင်း) box ကို အသုံးပြု၍လည်း item များ၏ အမည် သို့မဟုတ် အညွှန်းများကို ရိုက်ထည့်၍ ရှာဖွေနိုင်သည်။

Configuration ကို သတ်မှတ်ပြီးသည်နှင့် ပြောင်းလဲမှုများကို အတည်ပြုရန် :guilabel:`Apply` သို့မဟုတ် :guilabel:`OK` ကိုနှိပ်ပါ။ ထို configuration ကို နောက်တစ်ကြိမ် QGIS စတင်သည့်အခါတွင် default အဖြစ်အသုံးပြုသွားမည်ဖြစ်ပါသည်။

မွမ်းမံပြင်ဆင်ခြင်းများကို |fileSave| :sup:`Save To File` ခလုတ်ကို အသုံးပြု၍လည်း ``.ini`` ဖိုင်တစ်ခုထဲတွင် သိမ်းဆည်းနိုင်ပါသည်။ ၎င်းသည် အသုံးပြုသူများစွာအကြားတွင် အသုံးများသော QGIS interface တစ်ခုကိုမျှဝေရန် အသုံးဝင်သော နည်းလမ်းဖြစ်ပါသည်။ အသုံးပြုမည့်ကွန်ပျူတာမှ |fileOpen| :sup:`Load from File` (ဖိုင်များမှထည့်သွင်းခြင်း) ကို နှိပ်၍ ``.ini`` file ကိုထည့်သွင်းနိုင်သည်။ :ref:`Command line tools  <custom_commandline>` ကိုလည်း လုပ်ဆောင်နိုင်ပြီး မတူညီသော အသုံးပြုမှုများအတွက်လည်း setup အမျိုးမျိုးကို သိမ်းဆည်းနိုင်ပါသည်။

.. _tip_restoring_configuration:

.. tip:: **ကြိုတင်သတ်မှတ်ထားသော QGIS ကိုအလွယ်တကူ ပြန်လည်ရယူခြင်း**

   ကနဦး QGIS GUI ပြင်ဆင်သတ်မှတ်ခြင်းများကို အောက်ပါနည်းလမ်းများထဲမှ တစ်ခုဖြင့် ပြန်လည်ရယူနိုင်ပါသည်-

   * Customization dialog ရှိ |checkbox| :guilabel:`Enable customization` option ကို အမှန်ခြစ်ဖြုတ်ခြင်း သို့မဟုတ် |selectAllTree| :sup:`Check All` (အားလုံးကို အမှန်ခြစ်ခြင်း) ခလုတ်ကို နှိပ်ပါ။
   * :menuselection:`Settings --> Options` menu ၊ :guilabel:`System` tab အောက်ရှိ **Settings** ဘောင်ထဲမှ :guilabel:`Reset` ခလုတ်ကို နှိပ်ပါ။
   * Command prompt တစ်ခုတွင် ``qgis --nocustomization`` ဟူသော command line ဖြင့် QGIS ကို ဖွင့်ပါ။
   * :menuselection:`Settings --> Options` menu အောက်ရှိ :guilabel:`Advanced` tab မှ  :menuselection:`UI --> Customization --> Enabled` variable ၏တန်ဖိုးကို ``false`` အဖြစ်သတ်မှတ်ခြင်း  (:ref:`warning (သတိပေးချက်) <optionsadvanced>` တွင်ကြည့်ရှုနိုင်ပါသည်။)

   အခြေအနေအများစုတွင် ပြောင်းလဲမှုများကို အသုံးချရန်အတွက် QGIS ကို ပြန်လည်စတင်ရန်လိုအပ်ပါသည်။


.. index:: Keyboard shortcuts
.. _shortcuts:


Keyboard shortcuts (ကီးဘုတ်ဖြတ်လမ်းနည်းများ) 
==============================================

QGIS သည် လုပ်ငန်းဆောင်တာများစွာအတွက် default ကီးဘုတ်ဖြတ်လမ်းနည်း (keyboard shortcut) များကို ပံ့ပိုးထားပြီး ၎င်းတို့ကို :ref:`label_menubar` တွင် တွေ့နိုင်ပါသည်။ ထို့အပြင် :menuselection:`Settings -->` |keyboardShortcuts| :menuselection:`Keyboard Shortcuts...` တွင်လည်း default ကီးဘုတ်ဖြတ်လမ်းနည်းများကို ပြောင်းလဲနိုင်ပြီး QGIS feature များတွင် ကီးဘုတ်ဖြတ်လမ်းနည်းအသစ်များ ထပ်ထည့်၍လည်း အသုံးပြုနိုင်ပါသည်။ 


.. _figure_shortcuts:


.. figure:: img/shortcuts.png
   :align: center

   ဖြတ်လမ်းနည်း ရွေးချယ်စရာများ သတ်မှတ်ခြင်း 


Configuration သည် အလွန်ရိုးရှင်းပါသည်။ သီးသန့်လုပ်ဆောင်ချက်တစ်ခုကို ရှာဖွေရန် dialog ၏ အပေါ်ရှိ search box ကို အသုံးပြုပြီး စာရင်းထဲတွင် ၎င်းကိုရွေးချယ်၍ အောက်ပါတို့တွင် clik နှိပ်ပါ- 

* :guilabel:`Change` (ပြောင်းလဲခြင်း) ကိုနှိပ်၍ ဖြတ်လမ်းနည်း (shortcut) အသစ်အဖြစ် သတ်မှတ်လိုသည့် ပေါင်းစပ်မှုအသစ်ကို နှိပ်ပါ
* :guilabel:`Set None` (မည်သည့်အရာမှ မသတ်မှတ်ပါ) ဖြင့် သတ်မှတ်ထားသည့် မည်သည့်ဖြတ်လမ်းနည်း (shortcut) ကိုမဆို ပယ်ဖျက်နိုင်သည်
* သို့မဟုတ် ဖြတ်လမ်းနည်း (shortcut) ကို မူလအတိုင်း ပုံမှန်တန်ဖိုး ပြန်လည်ရယူလိုပါက :guilabel:`Set Default` ကို နှိပ်ပါ။ 

ပြင်ဆင်လိုသည့် အခြားသော tool များအတွက်လည်း အထက်တွင်ဖော်ပြထားသည့်အတိုင်း လုပ်ဆောင်နိုင်ပါသည်။ Configuration ကို လုပ်ဆောင်ပြီးနှင့် ပြောင်းလဲမှုများကို အသုံးချရန် :guilabel:`Close` ကိုနှိပ်ပါ။ ပြောင်းလဲမှုများကို အသုံးပြုသူဖြတ်လမ်းနည်း (User shortcut) များသာ ပါဝင်သော သို့မဟုတ် ဖြတ်လမ်းနည်း (shortcut) အားလုံးပါဝင်သော :file:`.XML` ဖိုင်တစ်ခုအဖြစ်လည်းကောင်း၊ ဖြတ်လမ်းနည်း (shortcut) အားလုံးပါဝင်သော :file:`.PDF` ဖိုင်တစ်ခုအဖြစ်လည်းကောင်း တစ်ခုမဟုတ်တစ်ခုဖြင့် :guilabel:`Save` (သိမ်းဆည်း) နိုင်သည်။ ထို့နောက် ၎င်းတို့ကို အခြား QGIS ထည့်သွင်းခြင်းတွင် :guilabel:`Load` (ထည့်သွင်း) ပြုလုပ်နိုင်ပါသည်။ 


.. index:: Command line options
.. _`label_commandline`:


Running QGIS with advanced settings (အဆင့်မြင့် setting များဖြင့် QGIS ကိုလုပ်ဆောင်ခြင်း)
==========================================================================================

Command line နှင့် environment variable (ကိန်းရှင်) များ
---------------------------------------------------------

မိမိ OS ပေါ်ရှိ application တစ်ခုခုကဲ့သို့ပင် :ref:`launching QGIS (QGIS စတင်ခြင်း) <label_startingqgis>` ကိုဆောင်ရွက်နိုင်သည်ကို သိရှိပြီးဖြစ်ပါသည်။ QGIS သည် ပိုမိုအဆင့်မြင့်သောအသုံးချမှုများအတွက် command line option များကို ပံ့ပိုးပေးထားပါသည် (အချို့အခြေအနေများတွင် command line option အစား environment variable တစ်ခုကို အသုံးပြုနိုင်ပါသည်)။ ရွေးချယ်မှုများစာရင်းတစ်ခုကိုရယူရန် command line ပေါ်တွင် ``qgis --help`` ကိုနှိပ်ပါက အောက်ပါတို့ကို ရရှိနိုင်ပါသည်- ::

  QGIS is a user friendly Open Source Geographic Information System.
  Usage: /usr/bin/qgis.bin [OPTION] [FILE]
    OPTION:
          [-v, --version]     display version information and exit
          [-s, --snapshot filename]   emit snapshot of loaded datasets to given file
          [-w, --width width] width of snapshot to emit
          [-h, --height height]       height of snapshot to emit
          [-l, --lang language]       use language for interface text (changes existing override)
          [-p, --project projectfile] load the given QGIS project
          [-e, --extent xmin,ymin,xmax,ymax]  set initial map extent
          [-n, --nologo]      hide splash screen
          [-V, --noversioncheck]      don't check for new version of QGIS at startup
          [-P, --noplugins]   don't restore plugins on startup
          [-B, --skipbadlayers]     don't prompt for missing layers
          [-C, --nocustomization]     don't apply GUI customization
          [-z, --customizationfile path]      use the given ini file as GUI customization
          [-g, --globalsettingsfile path]     use the given ini file as Global Settings (defaults)
          [-a, --authdbdirectory path] use the given directory for authentication database
          [-f, --code path]   run the given python file on load
          [-d, --defaultui]   start by resetting user ui settings to default
          [--hide-browser]        hide the browser widget
          [--dxf-export filename.dxf]     emit dxf output of loaded datasets to given file
          [--dxf-extent xmin,ymin,xmax,ymax]      set extent to export to dxf
          [--dxf-symbology-mode none|symbollayer|feature] symbology mode for dxf output
          [--dxf-scale-denom scale]       scale for dxf output
          [--dxf-encoding encoding]       encoding to use for dxf output
          [--dxf-map-theme maptheme]      map theme to use for dxf output
          [--take-screenshots output_path]        take screen shots for the user documentation
          [--screenshots-categories categories]   specify the categories of screenshot to be used (see QgsAppScreenShots::Categories).
          [--profile name]        load a named profile from the user's profiles folder.
          [-S, --profiles-path path]  path to store user profile folders. Will create profiles inside a {path}\profiles folder
          [--version-migration]   force the settings migration from older version if found
          [--openclprogramfolder]         path to the folder containing the sources for OpenCL programs.
          [--help]                this text
          [--]            treat all following arguments as FILEs


    FILE:
      Files specified on the command line can include rasters,
      vectors, and QGIS project files (.qgs and .qgz):
       1. Rasters - supported formats include GeoTiff, DEM
          and others supported by GDAL
       2. Vectors - supported formats include ESRI Shapefiles
          and others supported by OGR and PostgreSQL layers using
          the PostGIS extension

.. tip::
        **Command line argument များအသုံးပြုခြင်း ဥပမာ**
           Command Line တွင် တစ်ခု (သို့) တစ်ခုထက်ပိုသော data ဖိုင်များကို သတ်မှတ်ခြင်းဖြင့် QGIS ကို စတင်နိုင်ပါသည်။ ဥပမာအားဖြင့် မိမိသည် :file:`qgis_sample_data` ဖိုင်လမ်းကြောင်းတွင် ရောက်ရှိနေမည်ဆိုပါက ``qgis ./raster/landcover.img ./gml/lakes.gml`` ဟူသော command ကို အသုံးပြုခြင်းဖြင့် QGIS စတင်သည့်အခါ ထည့်သွင်းရန် သတ်မှတ်ထားသည့် vector layer တစ်ခုနှင့် raster ဖိုင်တစ်ခုဖြင့် QGIS ကို စတင်နိုင်မည်ဖြစ်ပါသည်။


``--version``
..............

ဤရွေးချယ်မှုသည် QGIS version နှင့်သက်ဆိုင်သည့်အချက်အလက်များကို ရရှိစေပါသည်။

``--snapshot``
...............

ဤရွေးချယ်မှုသည် လက်ရှိမြင်ကွင်းကို PNG format ဖြင့် လျှပ်တပြက်ပုံရိပ်ဖမ်းယူချက် (snapshot) တစ်ခုဖန်တီးနိုင်စေပါသည်။ Project များစွာရှိနေပြီး data များမှ snapshot များ ဖန်တီးလိုသည့်အခါ သို့မဟုတ် update ပြုလုပ်ထားသော data များဖြင့် တူညီသော project ၏ snapshot များ ဖန်တီးလိုသည့်အခါတွင် ၎င်းသည် အသုံးဝင်ပါသည်။  

လက်ရှိတွင် 800x600 pixels ဖြင့် PNG ဖိုင်တစ်ခုကို ထုတ်ပေးပါသည်။ ``--width`` (အကျယ်) နှင့်  ``--height`` (အမြင့်)များအသုံးပြု၍ အရွယ်အစားကို ချိန်ညှိနိုင်ပြီး ဖိုင်အမည်ကို ``--snapshot`` နောက်တွင် ထည့်ပေးနိုင်သည်။ ဥပမာအားဖြင့်- ::

  qgis --snapshot my_image.png --width 1000 --height 600 --project my_project.qgs

``--width``
............

ဤရွေးချယ်မှုသည် ထွက်ပေါ်လာမည့် snapshot ၏ ပုံအကျယ်ကို ရရှိစေမည်ဖြစ်ပါသည် (``--snapshot`` ဖြင့် အသုံးပြုပါ)။ 

``--height``
.............

ဤရွေးချယ်မှုသည် ထွက်ပေါ်လာမည့် snapshot ၏ ပုံအမြင့် ကို ရရှိစေသည် (``--snapshot`` ဖြင့် အသုံးပြုပါ)။ 

``--lang`` 
............

နေရာဒေသပေါ်မူတည်၍ QGIS သည် ဒေသနှင့်အညီဖြစ်စေခြင်းကို မှန်ကန်စွာ ရွေးချယ်နိုင်ပြီး ဘာသာစကားကို ပြောင်းလဲလိုပါက ဘာသာစကားကုဒ်ကို သတ်မှတ်ပေးနိုင်ပါသည်။ ဥပမာအားဖြင့် ``qgis --lang it`` သည် အီတလီဘာသာစကားဖြင့် QGIS ကို စတင်လိမ့်မည်။

``--project``
..............

ရှိပြီးသား project ဖိုင်တစ်ခုဖြင့် QGIS ကိုဖွင့်နိုင်ပါသည်။ Command line option ``--project`` နောက်တွင် project အမည် ထည့်သွင်းပါက QGIS သည် ထည့်သွင်းအသုံးပြုထားသော project ဖိုင်ထဲရှိ layer များအားလုံးနှင့်အတူ ပွင့်လာမည်ဖြစ်ပါသည်။ 

``--extent``
.............

သီးသန့်မြေပုံမြင်ကွင်းအကျယ်တစ်ခု (map extent) ဖြင့်စတင်ရန် ဤရွေးချယ်မှုကိုအသုံးပြုပါ။ အောက်ပါအစဉ်လိုက်အတိုင်း ကော်မာ (comma) ဖြင့်ပိုင်းခြား၍ extent ၏ bounding box (စတုဂံပုံမြင်ကွင်းအကျယ်) ကို ထည့်သွင်းရန် လိုအပ်မည်ဖြစ်ပါသည်- ::

  --extent xmin,ymin,xmax,ymax

ဤရွေးချယ်မှုသည် သီးခြားပရောဂျက်တစ်ခုကို လိုအပ်သည့် extent အတိုင်း ဖွင့်ရန် ``--project`` option နှင့် တွဲဖက်အသုံးပြုသောအခါ ပိုမိုအဓိပ္ပါယ်ရှိမည်ဖြစ်ပါသည်။

``--nologo``
.............

ဤရွေးချယ်မှုသည် QGIS ကိုစတင်သောအခါ splash screen (စတင်ချိန်တွင် တွေ့ရသည့် အမှတ်တံဆိပ် ပြသသော မျက်နှာပြင်) ကို ဖျောက်ပေးမည်ဖြစ်ပါသည်။

``--noversioncheck``
.....................

စတင်အသုံးပြုချိန်တွင် QGIS ၏ version အသစ်ရှာဖွေမှုအား ကျော်ပစ်မည်ဖြစ်ပါသည်။

``--noplugins``
................

Plugin များဖြင့် QGIS ကိုဖွင့်ချိန်တွင် ပြဿနာများကြုံတွေ့ရလျှင် ဤရွေးချယ်မှုဖြင့် စတင်ချိန်တွင် plugin များထည့်သွင်းခြင်းအား ရှောင်ရှားနိုင်ပါသည်။ နောက်ပိုင်းတွင် Plugins Manager မှ ၎င်းတို့ကို ပြန်လည်ရယူနိုင်ပါသည်။

``--nocustomization``
......................

ဤရွေးချယ်မှုကို အသုံးပြုခြင်းအားဖြင့် စတင်ချိန်တွင် ရှိနေပြီးသော :ref:`GUI customization (GUI စိတ်ကြိုက် ပြင်ဆင်ခြင်းများ) <sec_customization>` ကို အသုံးပြုလိမ့်မည်မဟုတ်ပါ။ ဆိုလိုသည်မှာ QGIS စတင်ဖွင့်လိုက်သောအခါ ဖျောက်ထားသောခလုတ်များ၊ menu item များ၊ toolbar များနှင့်အစရှိသည်တို့ကို မြင်တွေ့ရမည်ဖြစ်ပါသည်။ ဤအရာသည် အမြဲတမ်းအဖြစ် ပြောင်းလဲသွားသည်မဟုတ်ပါ။ QGIS ကို ဤရွေးချယ်မှုမပါဘဲ စတင်လိုက်လျှင် စိတ်ကြိုက်ပြင်ဆင်မှုများကို ပြန်လည်အသုံးပြုနိုင်ပါသည်။ ဤရွေးချယ်မှု သည် customization (စိတ်ကြိုက်ပြင်ဆင်မှု) ဖြင့် ဖယ်ရှားထားသော tool များကို ယာယီအသုံးပြုခွင့်ရစေရန် အသုံးဝင်ပါသည်။

.. _skipbadlayers:


``--skipbadlayers`` 
.....................

ဤရွေးချယ်မှုကို အသုံးပြုခြင်းဖြင့် QGIS စတင်ချိန်တွင် :guilabel:`Handle Unavailable Layers` (အသုံးမပြုနိုင်သော layer များကို ကိုင်တွယ်ခြင်း) dialog ပေါ်ပေါက်လာခြင်းကို ရှောင်ရှားနိုင်ပါသည်။ မပါရှိသော (missing) layer များကို မရရှိသည့် (unavailable) အတိုင်းထား၍ project ဖိုင်ကို ထည့်သွင်းမည်ဖြစ်ပါသည်။ အသေးစိတ်သိရှိလိုပါက :ref:`handle_broken_paths` ခေါင်းစဉ်တွင် ကြည့်ရှုနိုင်ပါသည်။


.. _custom_commandline:

``--customizationfile``
........................

ဤရွေးချယ်မှုကို အသုံးပြု၍ စတင်ချိန်တွင် အသုံးပြုမည်ဖြစ်သော UI customization ဖိုင်တစ်ခုကို သတ်မှတ်ထားနိုင်ပါသည်။

``--globalsettingsfile``
.........................

ညီမျှသော environment variable သည် ``QGIS_GLOBAL_SETTINGS_FILE`` ဖြစ်ပါသည်။

ဤရွေးချယ်မှုကိုအသုံးပြု၍ Default Setting များဟုလည်း ခေါ်ဆိုသော Global Setting များဖိုင် (``.ini``) တစ်ခုအတွက် လမ်းကြောင်းကို သီးခြားသတ်မှတ်နိုင်ပါသည်။ သီးခြားဖိုင်ထဲရှိ Setting များသည် မူလ default setting ဖိုင်များကို အစားထိုးမည် ဖြစ်သော်လည်း user profiles' settings (အသုံးပြုသူပရိုဖိုင်များ၏ setting) ကို အပေါ်ဆုံးတွင် သတ်မှတ် ထားလိမ့်မည်ဖြစ်ပါသည်။

QGIS သည် အောက်ဖော်ပြပါအစဉ်လိုက်အတိုင်း default global setting များကို ရှာဖွေပြီးနောက် ပထမဆုံးတွေ့ရှိသော ဖိုင်ကိုသာ အသုံးပြုလိမ့်မည်ဖြစ်သည်-

* commandline parameter ဖြင့် သီးခြားသတ်မှတ်ထားသော လမ်းကြောင်း
* Environment variable ဖြင့်သတ်မှတ်ထားသော လမ်းကြောင်း
* AppDataLocation folder သည် အမြဲအသုံးပြုနေသော application data များကို သိမ်းဆည်းထားသော နေရာဖြစ်ပါသည်။ ၎င်းကို အသုံးပြုသူ (user) သို့မဟုတ် system administrator (စနစ်ကို စီမံခန့်ခွဲသူ) မှ စီမံဆောင်ရွက်ပြီး ထည့်သွင်းသူ(installer) များမှ စီမံခန့်ခွဲမည်မဟုတ်ပါ။ ထို့အပြင် commandline parameter များ ဖြတ်ကျော်ခြင်း သို့မဟုတ် settings environment variable ကဲ့သို့သော ထပ်ဆောင်း setup တစ်ခုခုကိုလည်း လိုအပ်မည်မဟုတ်ပါ။ OS အမျိုးအစားပေါ်မူတည်၍ အောက်ပါဖိုင်များအတိုင်း ‌ဖြစ်နိုင်ပါသည်။-

  * |nix| :file:`$HOME/.local/share/QGIS/QGIS3/`
  * |win| :file:`C:\\Users\\<username>\\%AppData%\\Roaming\\QGIS\\QGIS3\\`
  * |osx| :file:`$HOME/Library/Application Support/QGIS/QGIS3/`

* Installation directory (ထည့်သွင်းသည့် လမ်းကြောင်း) - ဆိုလိုသည်မှာ :file:`your_QGIS_package_path/resources/qgis_global_settings.ini` ဖြစ်ပါသည်။ 

လက်ရှိတွင် setting များကို ရေးသားရန် သီးခြားဖိုင်တစ်ခုမရှိသောကြောင့် မူရင်းရှိနေပြီးသော setting ဖိုင်တစ်ခုကို ကူးယူဖန်တီး၍ အမည်ပြောင်းလဲခြင်းနှင့် လိုအပ်သလိုပြင်ဆင်မှုများပြုလုပ်နိုင်ပါသည်။

ကွန်ယက် (Network) တွင် မျှဝေထားသော folder သို့သွားရောက်နိုင်သော :file:`qgis_global_setting.ini` ဖိုင်လမ်းကြောင်းကို သတ်မှတ်ခြင်းသည် global setting များကို ပြောင်းလဲရန် system administrator အားခွင့်ပြုပေးပြီး ဖိုင်တစ်ခုတည်းတွင် တည်းဖြတ်ပြင်ဆင်ခြင်းဖြင့် စက်များစွာတွင် default အနေဖြင့် ဖြစ်စေပါသည်။


``--authdbdirectory``
......................

ဤရွေးချယ်မှုသည် ``--globalsettingsfile`` နှင့် ဆင်တူသော်လည်း ၎င်းသည် authentication database များကို သိမ်းဆည်းပြီးထည့်သွင်းအသုံးပြုနိုင်သည့် ဖိုင်လမ်းကြောင်းကို သတ်မှတ်ပေးပါသည်။


``--code``
...........

QGIS ကို စတင်ပြီးနောက် ပေးထားသော python ဖိုင်တစ်ခုကို တိုက်ရိုက်လုပ်ဆောင်ရန် ဤရွေးချယ်မှုကို အသုံးပြုနိုင်ပါသည်။ 

ဥပမာ- အောက်ပါအကြောင်းအရာများ ပါဝင်သည့် :file:`load_alaska.py` ဟု အမည်ပေးထားသော python ဖိုင်တစ်ခု ရှိမည်ဆိုပါက- 


.. code-block:: python


   from qgis.utils import iface
   raster_file = "/home/gisadmin/Documents/qgis_sample_data/raster/landcover.img"
   layer_name = "Alaska"
   iface.addRasterLayer(raster_file, layer_name)


:file:`load_alaska.py` ဖိုင်တည်ရှိသော လမ်းကြောင်းတွင် ရောက်ရှိနေမည်ဆိုပါက အောက်ပါ command ကိုအသုံးပြု၍ :file:`landcover.img` raster ဖိုင်ကို 'Alaska' ဟုအမည်ပေးပြီး ထည့်သွင်းကာ QGIS ကို စတင်နိုင်ပါသည်-::

  qgis --code load_alaska.py


``--defaultui``
................

ဤရွေးချယ်မှုသည် ထည့်သွင်းစဉ်တွင် အသုံးပြုသူဘက်မှ မြင်ရသည့်မျက်နှာပြင် (UI) ကို default setting များအတိုင်း **permanently resets** (အမြဲတမ်းအနေဖြင့် နဂိုအတိုင်းပြန်လည်သတ်မှတ်ခြင်း) ပြုလုပ်ပေးပါသည်။ ၎င်းသည် panel များနှင့် toolbar များ မြင်ရနိုင်မှု၊ နေရာအနေအထားနှင့် အရွယ်အစားတို့ကိုလည်း မူရင်းအတိုင်း ပြန်လည်ထားသိုမည်ဖြစ်ပါသည်။ ၎င်းတို့ကို ထပ်မံမပြောင်းလဲမချင်း နောက်ပိုင်းကဏ္ဍများတွင်လည်း default UI setting များအတိုင်း ဆက်လက်အသုံးပြုသွားမည်ဖြစ်သည်။

ဤရွေးချယ်မှုသည် :ref:`GUI customization (GUI စိတ်ကြိုက်ပြင်ဆင်မှု) <sec_customization>` အပေါ် သက်ရောက်မှုရှိမည်မဟုတ်ကြောင်း သတိပြုပါ။ ``--defaultui`` ကို အသုံးပြုထားသည့်တိုင် GUI စိတ်ကြိုက်ပြင်ဆင်မှု ဖြင့် ဖျောက်ထားသော item များကို ဆက်လက်ဖျောက်ထားမည်ဖြစ်သည်။ ``--nocustomization`` option တွင်လည်း ကြည့်ရှုပါ။ 

``--hide-browser``
...................

ဤရွေးချယ်မှုသည် ထည့်သွင်းစဉ်တွင် UI မှ :guilabel:`Browser` panel ကို ဖျောက်ထားမည်ဖြစ်သည်။ ဤ panel ကို toolbar များပေါ်ရှိ နေရာလွတ်တစ်ခုတွင် right-click နှိပ်၍ လည်းကောင်း သို့မဟုတ် :menuselection:`View --> Panels` ကို အသုံးပြု၍လည်းကောင်း ဖွင့်နိုင်ပါသည် (|kde| Linux KDE တွင် :menuselection:`Settings --> Panels` ကို အသုံးပြုရပါမည်)။

ထို Panel ကို ပြန်မဖွင့်မချင်း Browser panel သည် နောက်ပိုင်းကဏ္ဍများတွင် ဆက်လက်ပျောက်နေမည်ဖြစ်သည်။ 


``--dxf-*``
............

ဤရွေးချယ်မှုကို QGIS project တစ်ခုအား DXF ဖိုင်တစ်ခုအဖြစ်သို့ export ထုတ်ယူရာတွင် အသုံးပြုနိုင်ပါသည်။ လုပ်ဆောင်နိုင်သော ရွေးချယ်စရာများမှာ အောက်ပါအတိုင်းဖြစ်သည်- 

* *--dxf-export* - Layer များကို export ထုတ်ယူမည့် DXF ဖိုင်၏ ဖိုင်အမည်၊
* *--dxf-extent* - နောက်ဆုံး DXF ဖိုင်၏ extent ဖြစ်သည်၊
* *--dxf-symbology-mode* - DXF ဖိုင်၏သင်္ကေတပြုခြင်းဆိုင်ရာနည်းလမ်းကိုသတ်မှတ်နိုင်ပြီး တန်ဖိုးအမျိုးမျိုးကိုလည်း အသုံးပြုနိုင်ပါသည်။ ၎င်းတို့မှာ ``none`` (သင်္ကေတမသတ်မှတ်ပါ)၊ ``symbollayer`` (Layer သင်္ကေတ)၊ ``feature`` (featue သင်္ကေတ) တို့ဖြစ်သည်၊ 
* *--dxf-scale-denom* - DXF ၏ သင်္ကေတဆိုင်ရာ စကေးသတ်မှတ်ချက်ဖြစ်သည်၊
* *--dxf-encoding* - DXF ဖိုင်ကို encode ပြုလုပ်ခြင်းဖြစ်သည်၊
* *--dxf-map-theme* - Layer tree configuration (Layer ဖွဲ့စည်းပုံပြင်ဆင်သတ်မှတ်ခြင်း) မှ :ref:`map theme <map_themes>` (မြေပုံအကြောင်းအရာ) တစ်ခုကို ရွေးချယ်ခြင်းဖြစ်သည်။


``--take-screenshots``
.......................

အသုံးပြုသူမှ မှတ်တမ်းမှတ်ရာ ရရှိနိုင်ရန် မျက်နှာပြင်ပုံရိပ်ဖမ်းယူမှု (screenshot) ပြုလုပ်နိုင်သည်။ မှတ်တမ်းမှတ်ရာ၏ မည်သည့် အမျိုးအစား/ကဏ္ဍ screenshot များ ဖန်တီးသင့်သည်ကို filter (စစ်ထုတ်) လုပ်ရန် ``--screenshots-categories`` နှင့် တွဲ၍ အသုံးပြုနိုင်ပါသည် (QgsAppScreenShots::Categories တွင် ဆက်လက်ကြည့်ရှုနိုင်သည်)။

``--profile``
..............

အသုံးပြုသူ၏ ပရိုဖိုင် folder မှ သီးသန့် ပရိုဖိုင်တစ်ခုကို အသုံးပြု၍ QGIS ကိုထည့်သွင်းနိုင်ပါသည်။ ဤရွေးချယ်မှုသည် :ref:`user profile startup setting (အသုံးပြုသူ၏ ပရိုဖိုင် စတင်ခြင်း setting)<user_profile_setting>` ထက် ပို၍ဦးစားပေးဖြစ်သည်။


.. _profiles-path_option:


``--profiles-path``
....................

ဤရွေးချယ်မှုဖြင့် ပရိုဖိုင်များ (အသုံးပြုသူ setting များ) ကို သိမ်းဆည်းခြင်းနှင့် ထည့်သွင်းခြင်းတို့အတွက် လမ်းကြောင်း တစ်ခုကို ရွေးချယ်နိုင်ပါသည်။ ၎င်းသည် setting များ၊ ထည့်သွင်းထားသော plugin များ၊ processing model များနှင့် script များ အစရှိသည်တို့ပါဝင်သည့် ပရိုဖိုင်များကို ``{path}\profiles`` folder တစ်ခုအတွင်းတွင် ဖန်တီးပေးပါသည်။

ဥပမာအားဖြင့် ဤရွေးချယ်မှုသည် plugin များနှင့် setting များအားလုံးကို flash drive တစ်ခုထဲတွင် သယ်ဆောင်နိုင်ပြီး ဖိုင်မျှဝေခြင်းဝန်ဆောင်မှုကို အသုံးပြု၍ မတူညီသောကွန်ပျူတာများကြားတွင် setting များကိုမျှဝေနိုင်ပါသည်။

ညီမျှသော environment variable သည် ``QGIS_CUSTOM_CONFIG_PATH`` ဖြစ်သည်။

``--version-migration``
........................

အကယ်၍ version အဟောင်းတစ်ခုမှ setting များ (*ဥပမာ*- QGIS 2.18 မှ ``.qgis2`` folder) ကို တွေ့မည်ဆိုပါက ဤရွေးချယ်မှုသည် ၎င်းတို့ကို default QGIS ပရိုဖိုင်သို့ထည့်သွင်းသွားမည် ဖြစ်ပါသည်။


``--openclprogramfolder``
..........................

ဤရွေးချယ်မှုကို အသုံးပြုခြင်းဖြင့် သင်၏ OpenCL programs အတွက် အခြားလမ်းကြောင်းတစ်ခုကို သတ်မှတ်နိုင်ပါသည်။ ၎င်းသည် ရှိပြီးသား version များကို အစားထိုးရန်မလိုဘဲ developer များအတွက် ပရိုဂရမ်တစ်ခု၏ version အသစ်များကို စမ်းသပ်ရာတွင် အသုံးဝင်ပါသည်။

ညီမျှသော environment variable သည် ``QGIS_OPENCL_PROGRAM_FOLDER`` ဖြစ်ပါသည်။

.. _deploying_organization:

Deploying QGIS within an organization (အဖွဲ့အစည်းတစ်ခုအတွင်း QGIS ကို ဖြန့်ကျက်နေရာချခြင်း)
--------------------------------------------------------------------------------------------

အဖွဲ့အစည်းတစ်ခုအတွင်း QGIS ကို စိတ်ကြိုက် configuration ဖိုင်တစ်ခုဖြင့် ဖြန့်ကျက်ထားရန် လိုအပ်ပါက ပထမဦးစွာ မိမိ၏ :file:`your_QGIS_package_path/resources/qgis_global_settings.ini` ထဲတွင်ရှိသော default setting ၏ အကြောင်းအရာများကို မိတ္တူကူးထည့်ရန် လိုအပ်ပါသည်။ ဤဖိုင်တွင် ``[]`` နှင့် စတင်၍ သတ်မှတ်ထားသည့် default အပိုင်းအချို့ ပါရှိပြီးဖြစ်ပါသည်။ ဤ default တန်ဖိုးများကို ထိန်းသိမ်းထားပြီး ဖိုင်၏အောက်ခြေတွင် ကိုယ်ပိုင် အပိုင်း (section) များကို ထပ်၍ပေါင်းထည့်ထားရန် အကြံပြုပါသည်။ ဖိုင်တစ်ခုထဲတွင် အပိုင်းတစ်ခုကို ပုံတူပွားမည်ဆိုပါက QGIS သည် အထက်မှအောက်တွင် နောက်ဆုံးအပိုင်းကိုယူမည်ဖြစ်ပါသည်။

QGIS version စစ်ဆေးခြင်းကိုပိတ်ရန် ``allowVersionCheck=false`` ကို ပြောင်းလဲနိုင်ပါသည်။

အသစ်တစ်ခုကို စတင် ထည့်သွင်းပြီးနောက် migration window (အကူးအပြောင်း မျက်နှာပြင်) ကို မပြသစေလိုပါက အောက်ဖော်ပြပါအပိုင်းများကို လုပ်ဆောင်ရန် လိုအပ်ပါသည်-


.. code-block:: ini


    [migration]
    fileVersion=2
    settings=true


Global scope (အများသုံးနယ်ပယ်) တွင် စိတ်ကြိုက် variable တစ်ခုကို ထည့်သွင်းလိုပါက-

.. code-block:: ini


   [variables]
   organisation="Your organization"


Setting များ ``INI`` ဖိုင်၏ ဖြစ်နိုင်ခြေများကို ရှာဖွေတွေ့ရှိရန် QGIS Desktop တွင် အလိုရှိသော config ကို သတ်မှတ်ပြီး စာသားတည်းဖြတ်သည့်အရာ (text editor) တစ်ခုကိုအသုံးပြု၍ မိမိပရိုဖိုင်ထဲရှိ ``INI`` ဖိုင်ထဲတွင် ၎င်းကို ရှာဖွေရန် အကြံပြုပါသည်။ WMS/WMTS၊ PostGIS ချိတ်ဆက်မှုများ၊ proxy setting များ၊ မြေပုံအကြံပြုချက်များကဲ့သို့သော ``INI`` ဖိုင်ကို အသုံးပြု၍ setting အများအပြားကို သတ်မှတ်နိုင်ပါသည်။

နောက်ဆုံးအနေဖြင့် environment variable ``QGIS_GLOBAL_SETTINGS_FILE`` ကို မိမိပြင်ဆင်ထားသည့်ဖိုင်လမ်းကြောင်းတွင် သတ်မှတ်ပေးရန်လိုအပ်ပါသည်။

ထို့အပြင် Python macro များ၊ အရောင်ကွက်များ၊ layout နမူနာများ၊ project နမူနာများ ကဲ့သို့သော ဖိုင်များကိုလည်း QGIS system directory (QGIS စနစ်တည်နေရာလမ်းကြောင်း) တွင်လည်းကောင်း သို့မဟုတ် QGIS user profile (QGIS အသုံးပြုသူ ပရိုဖိုင်) တွင်လည်းကောင်း ဖြန့်ကျက်နေရာချထားနိုင်ပါသည်။ 

* Layout နမူနာများကို :file:`composer_templates` လမ်းကြောင်းတွင် ဖြန့်ကျက်နေရာချထားရပါမည်။
* Project နမူနာများကို :file:`project_templates` လမ်းကြောင်းတွင် ဖြန့်ကျက်နေရာချထားရပါမည်။
* စိတ်ကြိုက် Python macro များကို  :file:`python` လမ်းကြောင်းတွင် ဖြန့်ကျက်နေရာချထားရပါမည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script. If you need to create a new substitution manually, please add it also to the substitutions.txt file in the source folder.


.. |3d| image:: /static/common/3d.png
   :width: 1.5em
.. |action| image:: /static/common/action.png
   :width: 2em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |codeEditor| image:: /static/common/mIconCodeEditor.png
   :width: 1.5em
.. |crs| image:: /static/common/CRS.png
   :width: 1.5em
.. |customProjection| image:: /static/common/mActionCustomProjection.png
   :width: 1.5em
.. |editCopy| image:: /static/common/mActionEditCopy.png
   :width: 1.5em
.. |editMetadata| image:: /static/common/editmetadata.png
   :width: 1.2em
.. |editPaste| image:: /static/common/mActionEditPaste.png
   :width: 1.5em
.. |expression| image:: /static/common/mIconExpression.png
   :width: 1.5em
.. |fileOpen| image:: /static/common/mActionFileOpen.png
   :width: 1.5em
.. |fileSave| image:: /static/common/mActionFileSave.png
   :width: 1.5em
.. |filterMap| image:: /static/common/mActionFilterMap.png
   :width: 1.5em
.. |general| image:: /static/common/general.png
   :width: 1.5em
.. |identify| image:: /static/common/mActionIdentify.png
   :width: 1.5em
.. |indicatorLowAccuracy| image:: /static/common/mIndicatorLowAccuracy.png
   :width: 1.5em
.. |interfaceCustomization| image:: /static/common/mActionInterfaceCustomization.png
   :width: 1.5em
.. |kde| image:: /static/common/kde.png
   :width: 1.5em
.. |keyboardShortcuts| image:: /static/common/mActionKeyboardShortcuts.png
   :width: 1.5em
.. |layoutItem3DMap| image:: /static/common/mLayoutItem3DMap.png
   :width: 1.5em
.. |measureBearing| image:: /static/common/mActionMeasureBearing.png
   :width: 1.5em
.. |nix| image:: /static/common/nix.png
   :width: 1em
.. |offsetCurve| image:: /static/common/mActionOffsetCurve.png
   :width: 1.5em
.. |openTable| image:: /static/common/mActionOpenTable.png
   :width: 1.5em
.. |options| image:: /static/common/mActionOptions.png
   :width: 1em
.. |osx| image:: /static/common/osx.png
   :width: 1em
.. |overlay| image:: /static/common/overlay.png
   :width: 1.5em
.. |polygonLayer| image:: /static/common/mIconPolygonLayer.png
   :width: 1.5em
.. |processingAlgorithm| image:: /static/common/processingAlgorithm.png
   :width: 1.5em
.. |radioButtonOff| image:: /static/common/radiobuttonoff.png
   :width: 1.5em
.. |radioButtonOn| image:: /static/common/radiobuttonon.png
   :width: 1.5em
.. |raster| image:: /static/common/mIconRaster.png
   :width: 1.5em
.. |refresh| image:: /static/common/mActionRefresh.png
   :width: 1.5em
.. |relations| image:: /static/common/relations.png
   :width: 1.5em
.. |rendering| image:: /static/common/rendering.png
   :width: 1.5em
.. |runConsole| image:: /static/common/iconRunConsole.png
   :width: 1.5em
.. |search| image:: /static/common/search.png
   :width: 1.5em
.. |select| image:: /static/common/mActionSelect.png
   :width: 1.5em
.. |selectAllTree| image:: /static/common/mActionSelectAllTree.png
   :width: 1.5em
.. |selectNumber| image:: /static/common/selectnumber.png
   :width: 2.8em
.. |selectString| image:: /static/common/selectstring.png
   :width: 2.5em
.. |sensor| image:: /static/common/sensor.png
   :width: 1.5em
.. |settings| image:: /static/common/settings.png
   :width: 1.5em
.. |start| image:: /static/common/mActionStart.png
   :width: 1.5em
.. |styleManager| image:: /static/common/mActionStyleManager.png
   :width: 1.5em
.. |symbology| image:: /static/common/symbology.png
   :width: 2em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
.. |symbologyEdit| image:: /static/common/symbologyEdit.png
   :width: 1.5em
.. |symbologyRemove| image:: /static/common/symbologyRemove.png
   :width: 1.5em
.. |temporal| image:: /static/common/temporal.png
   :width: 1.5em
.. |toggleEditing| image:: /static/common/mActionToggleEditing.png
   :width: 1.5em
.. |transformation| image:: /static/common/transformation.png
   :width: 1.5em
.. |unchecked| image:: /static/common/unchecked.png
   :width: 1.3em
.. |user| image:: /static/common/user.png
   :width: 1.5em
.. |win| image:: /static/common/win.png
   :width: 1em
.. |zoomFullExtent| image:: /static/common/mActionZoomFullExtent.png
   :width: 1.5em