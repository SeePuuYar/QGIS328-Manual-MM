.. _sec_processing_intro:

Introduction (မိတ်ဆက်)
=======================

ဒီအခန်းတွင် QGIS processing framework (လုပ်ငန်းစဉ်မူဘောင်) ၊ ပထဝီဆိုင်ရာ လေ့လာဆန်းစစ်ခြင်းများကို ပိုမိုထိရောက် လွယ်ကူစေပြီး QGIS မှ မူရင်းနှင့် third-party (တတိယပါတီ) algorithm များကိုခေါ်ယူအသုံးပြုနိုင်သော geoprocessing environment တစ်ခုကိုမိတ်ဆက်ပေးပါမည်။

:ref:`Core plugin <core_plugins>` (ပင်မ plugin) တစ်ခုအဖြစ် processing ကိုမူရင်းအဖြစ် ထည့်သွင်းထားပါသည် သို့သော် ဖွင့်ပေးရန် လိုအပ်ပါသည်-

#. :menuselection:`Plugins --> Manage and install plugins...` ကိုသွားပါ
#. ဘယ်ဘက်တွင်ရှိသော :guilabel:`Installed` tab ကိုနှိပ်ပါ။
#. |processingAlgorithm| :guilabel:`Processing` entry ၏ဘေးတွင်ရှိသော box ကိုအမှန်ခြစ် ခြစ်ပါ။
#. Dialog ကိုပိတ်ပါ။

   အထက်မှာရှိသော menu bar တွင် :menuselection:`Processing` menu တစ်ခုပေါ်နေပါလိမ့်မည်။ ဤ framework ၏ အဓိကအစိတ်အပိုင်းများကို ၎င်း menu တွင် တွေ့ရှိနိင်မည်ဖြစ်ပါသည်။
   
အောက်ပါ section များတွင် ဤ framework ၏ graphical element (ရုပ်ပြဆိုင်ရာ) များကို မည်သို့အသုံးပြုရမည်ဆိုသည်နှင့် တစ်ခုချင်းဆီကို သုံးသပ်ပြပါမည်။

Framework GUI (Graphical user interface) ထဲတွင် ရည်ရွယ်ချက်အမျိုးမျိုးအတွက် algorithm များကို အသုံးပြုနိုင်သော အခြေခံ element လေးမျိုးရှိပါသည်။ မည်သည့် tool ကိုရွေးချယ်မည်ဆိုတာသည် လုပ်ဆောင်မည့် ဆန်းစစ်ခြင်းအမျိုးအစား၊ အသုံးပြုသူနှင့် project များအပေါ်တွင်မူတည်ပါသည်။ ၎င်းတို့အားလုံး (toolbox သို့မဟုတ် algorithm စေခိုင်းလုပ်ဆောင်သော dialog မှ ခေါ်ယူအသုံးပြုသော အစုအဖွဲ့လိုက် (batch) processing လုပ်သော interface မှလွဲ၍) ကို :menuselection:`Processing` menu item မှသွားရောက်အသုံးပြုနိုင်ပါသည်။(ထည့်သွင်းမှုများကိုပိုမိုတွေ့ရပါမည် - ကျန်သောအရာများကို algorithm များ စေခိုင်းလုပ်ဆောင် ရန်အတွက် အသုံးပြုမည်မဟုတ်ပါ၊ ဒီအခန်း၏နောက်ပိုင်းတွင်ရှင်းပြသွားပါမည်)

* :guilabel:`Toolbox` - GUI ၏အဓိက element ဖြစ်ပြီး algorithm တစ်ခုတည်းကို စေခိုင်းလုပ်ဆောင်ရာတွင် သို့မဟုတ် ၎င်း algorithm ပေါ်မူတည်ပြီး batch အလိုက်လုပ်ဆောင်ခြင်းတစ်ခုအတွက် အသုံးပြုပါသည်။ 

.. _figure_toolbox_dialog:

.. figure:: img/toolbox.png
   :align: center

   Processing Toolbox

* :guilabel:`Model Designer` - Subprocess (လုပ်ငန်းစဉ်အခွဲ) များစွာပါဝင်သော တစ်ခုတည်းသော process ကိုဖန်တီးသည့် workflow တစ်ခုကို သတ်မှတ်ရန် modeler ကိုအသုံးပြုပြီး များစွာသော algorithm များကို ပေါင်းစပ်နိုင်ပါသည်။


.. _figure_model_dialog:

.. figure:: img/models.png
   :align: center

   Processing Modeler

* :guilabel:`History` စီမံခန့်ခွဲသည့်အရာ - ဖော်ပြခဲ့ပြီးဖြစ်သော မည်သည့် element ကိုမဆိုအသုံးပြုပြီး လုပ်ဆောင်သော လုပ်ဆောင်ချက်များအားလုံးကို မှတ်တမ်း file ထဲတွင်သိမ်းဆည်းထားပြီး မှတ်တမ်း စီမံခန့်ခွဲသည့်အရာကိုအသုံးပြုပြီး နောက်မှလွယ်ကူစွာ ပြန်လည်ထုတ်ယူနိုင်ပါသည်။

.. _figure_history_dialog:

.. figure:: img/history.png
   :align: center

   Processing မှတ်တမ်း

* :guilabel:`Batch Processing` interface - ဤ interface တွင် batch အလိုက် process များကိုစေခိုင်းလုပ်ဆောင်ခြင်းနှင့် များစွာသော dataset များတွင် တစ်ခုတည်းသော algorithm ကို စေခိုင်းလုပ်ဆောင်ခြင်းကို အလိုအလျှောက်လုပ်စေခြင်းတို့ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။


.. _figure_batchprocess_dialog:

.. figure:: img/batch_processing.png
   :align: center

   Batch Processing interface

အောက်ပါ section များတွင် ၎င်း element များကို တစ်ခုချင်းစီ အသေးစိတ် သုံးသပ်ပြပါမည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |processingAlgorithm| image:: /static/common/processingAlgorithm.png
   :width: 1.5em
