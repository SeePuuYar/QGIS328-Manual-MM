﻿.. index:: Plugins; Offline editing
.. _`offlinedit`:


Offline Editing Plugin (အင်တာနက်မလိုအပ်သော ပြင်ဆင်တည်းဖြတ်ခြင်း Plugin)
========================================================================

ကွင်းဆင်း၍ ဒေတာကောက်ယူသည့်အခါ ကွန်ပျူတာ သို့မဟုတ် ဆဲလ်ဖုန်းများနှင့်အလုပ်လုပ်ရာတွင် အင်တာနက်မရရှိခြင်းသည် ဖြစ်ရိုးဖြစ်စဉ်အခြေအနေတစ်ခုဖြစ်ပါသည်။ အင်တာနက်ပြန်လည်ရရှိသည့်အချိန်တွင် ပြောင်းလဲမှုများကို မူရင်းဒေတာအရင်းအမြစ် (ဥပမာ- PostGIS database) ဖြင့် ပြန်လည်လုပ်ဆောင်ရန် လိုအပ်မည်ဖြစ်ပါသည်။ အကယ်၍ တူညီသည့် dataset များကို လူအများမှ တစ်ပြိုင်တည်း အလုပ်လုပ်သည့်အခါတွင် တူညီသည့် feature များကို မပြောင်းလဲသည့်တိုင် ပြင်ဆင်တည်းဖြတ်မှုများကို တစ်ခုစီလိုက်လံပေါင်းစပ်ရန် ခက်ခဲပါသည်။ 

|offlineEditingCopy| :sup:`Offline Editing` plugin သည် ဒေတာအရင်းအမြစ်၏ အကြောင်းအရာများကို  SpatiaLite သို့မဟုတ် GeoPackage data သို့ ကူးယူခြင်းနှင့် offline ပြင်ဆင်တည်းဖြတ်မှုများကို သီးသန့်ဇယားတွင် သိမ်းဆည်းပေးထားခြင်းဖြင့် synchronisation ကိုအလိုအလျောက်လုပ်ဆောင်ပေးပါသည်။ အင်တာနက်ပြန်လည်ရရှိပါက offline ပြင်ဆင်တည်းဖြတ်မှုများကို မူရင်း dataset တွင် အသုံးချနိုင်မည်ဖြစ်သည်။

Plugin ကို အသုံးပြုရန်- 

#. Vector Layer အချို့ပါရှိသော project တစ်ခုကို ဖွင့်ပါ (ဥပမာ- Esri Shapefile ၊ PostGIS
   သို့မဟုတ် WFS-T datasource တို့မှ)
#. ထို plugin ကို ဖွင့်ထားပြီးပြီဟု ယူဆပါ ( :ref:`core_and_external_plugins` ကို ကြည့်ပါ) ထို့နောက် :menuselection:`Database --> Offline Editing -->`  |offlineEditingCopy|:guilabel:`Convert to offline project` သို့ ဝင်ရောက်ပါ။ ထိုအခါ သင်္ကေတများကို ပြင်ဆင်နိုင်သည့် dialog ပွင့်လာမည်ဖြစ်သည်။
#. :guilabel:`Storage type` (သိမ်းဆည်းမည့်အမျိုးအစား) ကို ရွေးချယ်ပါ။ ၎င်းသည် :guilabel:`GeoPackage` သို့မဟုတ် :guilabel:`SpatiaLite` database အမျိုးအစားဖြစ်နိုင်ပါသည်။
#. :guilabel:`Browse` ခလုတ်ကို :guilabel:`Offline data` ကို သိမ်းဆည်းမည့် database ၏ တည်နေရာကို ပြသရန် အသုံးပြုပါ။ ၎င်းသည် ရှိပြီးသားဖိုင်တစ်ခု သို့မဟုတ် အသစ်ဖန်တီးရမည့်တစ်ခု ဖြစ်နိုင်ပါသည်။ 
#. :guilabel:`Select remote layers` အပိုင်းတွင် သိမ်းဆည်းလိုသည့် Layer များကို အမှန်ခြစ်ပါ။ Layer တွင်ပါဝင်သည့်အကြောင်းအရာများကို database ဇယားတွင် သိမ်းဆည်းထားမည်ဖြစ်ပါသည်။ 

   .. note:: 
     ရည်ရွယ်ထားသည့် database ပုံစံများတွင် ကိုယ်ပိုင် list (စာရင်း) ပံ့ပိုးမှုမရှိသည့်အတွက် offline တည်းဖြတ်ပြင်ဆင်ခြင်း plugin သည် {string ၊ number} (စာသား၊ နံပါတ်) list ၏ field များကို ကော်မာများ (commas) ဖြင့် ခွဲခြားထားသည့် စာသား field များအဖြစ် ပြောင်းလဲပေးပါသည်။ ၎င်းသည် အင်တာနက်မရှိချိန်တွင် ထို field များကို ကြည့်ရှုခြင်းနှင့် တည်းဖြတ်ပြင်ဆင်ခြင်းကို ဆောင်ရွက်နိုင်မည်ဖြစ်သည်။  

     အကယ်၍ မူရင်း Layer နှင့် offline layer နှစ်ခုလုံးရှိ field များကို ကိုင်တွယ်လိုလျှင် :ref:`try() <expression_function_Conditionals_try>` နှင့် :ref:`array <array_functions>` expression function များအတိုင်း ဆောင်ရွက်နိုင်သည်။ ဥပမာအနေဖြင့်-
     ::

      try(array_contains("field",1),array_contains(string_to_array("field"),1))

#. |checkbox| :guilabel:`Only synchronize selected features if a selection is present` (ရွေးချယ်မှုပြုလုပ်ထားလျှင် ရွေးချယ်ထားသော feature များကိုသာ လုပ်ဆောင်စေခြင်း) ကို အမှန်ခြစ်ပြုလုပ်ခြင်းသည် အစုခွဲ (subset) တစ်ခုတွင်သာ သိမ်းဆည်းပြီး လုပ်ဆောင်နိုင်မည်ဖြစ်သည်။ ၎င်းသည် ကြီးမားသော layer များအတွက် အလွန်အဖိုးတန်ပါသည်။   
#. Project ကို သိမ်းဆည်း၍ ကွင်းဆင်းရာတွင် ယူဆောင်သွားပါ။ 
#. Layer များကို အင်တာနက်မရှိလျှင်လည်း တည်းဖြတ်ပြင်ဆင်နိုင်ပြီဖြစ်သည်။ 
#. အင်တာနက်ချိတ်ဆက်မှု တဖန်ရရှိပါက  :menuselection:`Database --> Offline Editing -->` |offlineEditingSync| :guilabel:`Synchronize` ကိုအသုံးပြု၍ ပြောင်းလဲပြင်ဆင်မှုများကို ထည့်သွင်းပါ။ 

.. note:: အင်တာနက်မရရှိသည့်အချိန်တွင် အသုံးပြုထားသည့် Layer များကို :guilabel:`Layers` panel တွင်  |indicatorOffline| icon ဖြင့် အမှတ်အသားပြုထားမည်ဖြစ်ပါသည်။ 

.. _figure_offline_editing:


.. figure:: img/create_offline_project.png
   :align: center

   Offline project တစ်ခု ဖန်တီးခြင်း 


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.


.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |indicatorOffline| image:: /static/common/mIndicatorOffline.png
   :width: 1.5em
.. |offlineEditingCopy| image:: /static/common/offline_editing_copy.png
   :width: 1.5em
.. |offlineEditingSync| image:: /static/common/offline_editing_sync.png
   :width: 1.5em