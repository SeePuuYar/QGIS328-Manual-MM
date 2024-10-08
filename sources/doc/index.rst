************************************************************
QGIS |version| အတွက် မှတ်တမ်းပြုစုခြင်း (Documentation)
************************************************************

.. only:: testing

  .. attention::  QGIS documentation စမ်းသပ်ဗားရှင်းကို ဖတ်ရှုနေရခြင်းဖြစ်ပြီး software ထဲတွင် နောက်ဆုံးပြောင်းလဲမှုများကို ဦးတည်သည့် ဆောင်ရွက်ဆဲအလုပ်တစ်ခုဖြစ်ပါသည်။ QGIS |CURRENT| Long Term Release နှင့်ကိုက်ညီမှုမရှိသော feature များကို မှတ်တမ်းပြုလုပ်ပါသည်။

.. only:: not testing

  .. hint:: |version| Long Term Release ထက် ပိုအသစ်ဖြစ်သော ဗားရှင်းကို ရှာဖွေနေပါသလား။ `testing docs <https://docs.qgis.org/testing/en/>`_ တွင် ကြည့်ရှုပါ။

.. note:: QGIS documentation သည် ဘာသာစကားအမျိုးမျိုးနှင့် ဗားရှင်းအမျိုးမျိုးတို့ဖြင့် ရရှိနိုင်ပါသည်။ ရရှိနိုင်သောစာရင်းကို ကြည့်ရှုရန် ဘေးဘက်ဘား အောက်ခြေ၌ရှိသော :guilabel:`QGIS Documentation` menu ကို ဖြန့်ကြည့်နိုင်ပါသည်။

.. only:: i18n

  .. note:: ဤ documentation သည် `Transifex <https://explore.transifex.com/qgis/qgis-documentation>`_ တွင် community member (အသိုင်းအဝိုင်းအဖွဲ့ဝင်) များမှ မူလ English ဗားရှင်းကို ဘာသာပြန်ဆိုထားခြင်းဖြစ်ပါသည်။

    ဘာသာပြန်ဆိုမှု ပြီးစီးမှုအဆင့်ပေါ်မူတည်၍ English အနေဖြင့်သာ ကျန်ရှိနေသေးသော စာပိုဒ်များ သို့မဟုတ် စာမျက်နှာများအလိုက် တွေ့ရနိုင်ပါသည်။ သင့်အနေဖြင့် Transifex ပေါ်တွင် ဘာသာပြန်ဆိုမှုအသစ်များဆောင်ရွက်ပေးခြင်း သို့မဟုတ် ဘာသာပြန်ဆိုပြီးသားများကို ပြန်လည်သုံးသပ်ပေးခြင်းများ လုပ်ဆောင်ခြင်းဖြင့် community ကို အကူအညီပေးနိုင်ပါသည်။

    လောလောဆယ်တွင် ကန့်သတ်ထားသော ဘာသာပြန်ဆိုမှုများကို Long Term ဖြန့်ချိမှုများအတွက်သာ ရရှိနိုင်မည်ဖြစ်သော်လည်း QGIS အသုံးပြုခြင်းကိုလေ့လာရန် သင့်တော်ပါသည်။ 

အခမဲ့ open source ဖြစ်ပြီး community (အသိုင်းအဝိုင်း) မှ ဝိုင်းဝန်းဖော်ဆောင်ထားသော GIS software ဖြစ်သည့် `QGIS <https://qgis.org>`_ ၏ တရားဝင် documentation မှ ကြိုဆိုပါသည်။ ဤ documentation ကို အခုမှ စတင်အသုံးပြုသူဖြစ်ပါက အောက်နှင့် ဘေးဘက် ဘားတွင်ရှိသော အကြောင်းအရာဇယားမှတဆင့် သင်စိတ်ဝင်စားရာခေါင်းစဉ်သို့ အလွယ်တကူ ဝင်ရောက်ဖတ်ရှုနိုင်ပါသည်။ ဘယ်ဘက်အပေါ်ထောင့်ရှိ search ကိုအသုံးပြု၍လည်း ရှာဖွေနိုင်ပါသည်။

.. todo: Actually, it could be nice to refactor the first chapters of the docs
 (preamble, foreword, features, conventions) to minimize repetition and have
 an introductory chapter for the whole documentation, not within User manual.
 Also we can consider adding an overview of how the docs is structured and what
 people should expect to find in each document (inspired by
 https://docs.godotengine.org/en/stable/about/introduction.html#doc-about-intro).


Online documentation အပြင် offline ဖတ်ရှုနိုင်ရန်အတွက်လည်း documentation ပါ အချက်အလက်များကို ဒေါင်းလုတ်ပြုလုပ်နိုင်ပါသည်။ ဘေးဘက်ဘား အောက်ခြေရှိ :guilabel:`QGIS Documentation` menu မှတဆင့် အောက်ပါတို့အနေဖြင့် ရရှိနိုင်ပါသည်-

* Software အတွင်းမှ :ref:`path များအနေဖြင့် အသုံးပြုနိုင်ပြီး <doc_config_path>` ပြန်လည်ထုတ်ယူနိုင်သော zip ပြုလုပ်ထားသည့် HTML ဖိုင်များ
* PDF ဖိုင်များ


.. note:: QGIS သည် ပံ့ပိုးကူညီသူအသိုင်းအဝိုင်းမှ ဖော်ဆောင်ထားသော open source project တစ်ခုဖြစ်ပါသည်။ မှတ်တမ်းပြုစုသည့်အဖွဲ့သည် သင်၏ feedback (တုံ့ပြန်ချက်) များကို အမြဲတမ်းအသုံးပြုပြီး tutorial များနှင့် အသွင်အပြင်ဖော်ပြချက်များကို တိုးတက်ကောင်းမွန်အောင် ကူညီဆောင်ရွက်ပေးပါသည်။ သင့်အနေဖြင့် တစ်စုံတစ်ခုကို နည်းမလည်ပါက သို့မဟုတ် documentation ထဲတွင် သင်ရှာဖွေလိုသောအရာကို မတွေ့ရှိရပါက အောက်ဖော်ပြပါများမှတဆင့် ကျွန်ုပ်တို့ထံသို့ အသိပေးအကြောင်းကြားနိုင်ပါသည်-

    * `GitHub repository <https://github.com/qgis/QGIS-Documentation/>`_ တွင် ဖြစ်ပွားသည့်ပြဿနာ သို့မဟုတ် တောင်းဆိုမှုကို တင်သွင်းနိုင်ပါသည်၊
    * သင့်ဘာသာစကားအဖြစ်သို့ `documentation ကို ဘာသာပြန်ဆိုနိုင်ရန်
      <https://qgis.org/en/site/getinvolved/translate.html>`_ ကူညီပေးနိုင်ပါသည်၊
    * `qgis-community-team <https://lists.osgeo.org/mailman/listinfo/qgis-community-team>`_ mailing-list ၊ IRC ပေါ်ရှိ `#qgis <http://webchat.freenode.net/?channels=#qgis>`_ channel သို့မဟုတ် `#qgis:matrix.org <http://matrix.to/#/#qgis:matrix.org>`_ room တစ်ခုမဟုတ်တစ်ခုမှတဆင့် ကျွန်ုပ်တို့ထဲသို့ ပြောဆိုအကြောင်းကြားနိုင်ပါသည်။


အောက်ဖော်ပြပါ document များထဲမှ တစ်ခုကို ကြည့်ပါ။

.. toctree::
   :maxdepth: 2
   :caption: အသုံးပြုသူများအတွက်

   QGIS Desktop User Guide/Manual (QGIS Testing) <user_manual/index>
   QGIS Server Guide/Manual (QGIS Testing) <server_manual/index>
   Training Manual <training_manual/index>
   A Gentle Introduction to GIS <gentle_gis_introduction/index>

.. toctree::
   :maxdepth: 2
   :caption: ရေးသားသူများအတွက်

   Documentation Guidelines <documentation_guidelines/index>

.. toctree::
   :maxdepth: 2
   :caption: Developer များအတွက်

   PyQGIS Cookbook (QGIS Testing) <pyqgis_developer_cookbook/index>
   Developers Guide <developers_guide/index>

* :ref:`genindex`


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |CURRENT| replace:: 3.28
