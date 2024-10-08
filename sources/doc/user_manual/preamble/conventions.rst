.. _label_conventions:

****************************************
Conventions (အသုံးအနှုန်းများ)
****************************************

.. only:: html

   .. contents::
      :local:

ဤအခန်း၌ လမ်းညွှန်စာအုပ်တစ်ခုလုံးတွင်အသုံးပြုသွားမည့် တစ်သမတ်တည်းပုံစံတွေကို ဖော်ပြထားပါသည်။

GUI Conventions (Graphical User Interface အသုံးအနှုန်းများ)
------------------------------------------------------------

GUI convention style များကို Graphical User Interface ၏ပုံစံအတိုင်း တူညီစေရန်တုပ၍ပြုလုပ်ထားခြင်းဖြစ်ပါသည်။
ယေဘူယျအားဖြင့် style တစ်ခုသည် mouse pointer တင်မထားသောအခြေအနေ (non-hover appearance) အား ထင်ဟပ်စေမည်ဖြစ်ပါသည်။
ထို့ကြောင့်အသုံးပြုသူတစ်ဦးအနေဖြင့် စာအုပ်ထဲတွင်ပါဝင်သော လမ်းညွှန်ချက်နှင့် ဆင်တူသည့် အရာများကို Graphical User Interface တွင်ရှာဖွေခြင်းဖြင့်တွေ့ရှိနိုင်မည်ဖြစ်ပါသည်။

* Menu Options- :menuselection:`Layer --> Add a Raster Layer` သို့မဟုတ်
  :menuselection:`Settings --> Toolbars --> Digitizing`
* Tool- |addRasterLayer| :sup:`Add a Raster Layer`
* Button- :guilabel:`Save as Default`
* Dialog Box Title- :guilabel:`Layer Properties`
* Tab- :guilabel:`General`
* Checkbox- |checkbox| :guilabel:`Render`
* Radio Button- |radioButtonOn| :guilabel:`Postgis SRID`
  |radioButtonOff| :guilabel:`EPSG ID`
* နံပါတ်တစ်ခုကိုရွေးရန်- |selectNumber|
* စာသားတစ်ခုကိုရွေးရန်- |selectString|
* ဖိုင်တစ်ခုကိုရှာဖွေရန်- :guilabel:`...`
* အရောင်တစ်ခုကိုရွေးရန်- |selectColor|
* Slider- |slider|
* စာသားထည့်သွင်းရန်- |inputText|

.. * Toolbox : \toolboxtwo{nviz}{nviz - Open 3D-View in NVIZ}

အရိပ်ပုံစံ ပြခြင်းသည် click နှိပ်နိုင်သည့် GUI ၏ အစိတ်အပိုင်းတစ်ခုကို ညွှန်ပြပါသည်။

Text or Keyboard Conventions (စာသား သို့မဟုတ် ကီးဘုတ်လက်ကွက်ဆိုင်ရာ အသုံးအနှုန်းများ)
--------------------------------------------------------------------------------------

ဤလမ်းညွှန်တွင် အတန်းအစားများ (classes) နှင့် နည်းလမ်းများ (methods) ကဲ့သို့ အမျိုးမျိုးသော ထည့်သွင်းခြင်းများကိုညွှန်ပြရန်  
စာသား၊ ကီးဘုတ် command များနှင့် ကုဒ်ရေးသားခြင်းတို့နှင့်ဆက်နွယ်သည့် စတိုင်များ ထည့်သွင်းထားပါသည်။
သို့သော်လည်း ထိုစတိုင်များသည် QGIS အတွင်းရှိ စာသားများ သို့မဟုတ် ကုဒ်ရေးသားခြင်းများ၏ အမှန်တကယ်အသွင်အပြင်နှင့်တော့မသက်ဆိုင်ပါ။

.. Use for all urls. Otherwise, it is not clickable in the document.

* Hyperlinks (Web link များဖြင့်ချိတ်ဆက်ထားမှုများ)- https://qgis.org
* ကီးဘုတ်လက်ကွက် ပေါင်းစပ်ခြင်းများ- :kbd:`Ctrl+B` ကိုနှိပ်ပါ ၊ ဆိုလိုသည်မှာ Ctrl
  key ကိုဖိထားပြီး B key ကိုနှိပ်ပါ။
* ဖိုင်တစ်ခု၏အမည်- :file:`lakes.shp`
* အတန်းအစား(class)တစ်ခု၏အမည်- **NewLayer**
* နည်းလမ်း(method)- *classFactory*
* Server- *myhost.de*
* User text- ``qgis --help``

.. * Single Keystroke: press \keystroke{p}
.. * Name of a Field: \fieldname{NAMES}
.. * SQL Table: \sqltable{example needed here}

ကုဒ် စာကြောင်းများကို ပုံသေသတ်မှတ်ထားသောစာလုံးအကျယ်ဖြင့် ညွှန်ပြပါသည်-

::

    PROJCS["NAD_1927_Albers",
      GEOGCS["GCS_North_American_1927",

Platform-specific instructions (သုံးစွဲသည့် Operating System အလိုက်ညွှန်ကြားချက်များ)
--------------------------------------------------------------------------------------

GUI sequences များနှင့် စာသားပမာဏအနည်းငယ်ကို inline စတိုင်ဖြင့်တစ်သမတ်တည်း format ကျအောင်ပြုလုပ်ထားပါမည်- QGIS ကို ပိတ်ရန်အတွက် 
|nix| |win| :menuselection:`File` |osx| :menuselection:`QGIS --> Quit to close QGIS` ကိုနှိပ်ပါ။
Linux ၊ Unix နှင့် Windowsplatforms များတွင် File menu ကိုအရင်နှိပ်ရပါမည်။ ပြီးမှထွက်ရပါမည်။
MacOS platforms များတွင် QGIS menu ကိုအရင်ဆုံးကလစ်နှိပ်ပြီးမှ ထွက်ရပါမည်။ 

ပမာဏများသည့်စာများကို စာရင်းတစ်ခုအနေနှင့် format လုပ်ထားနိုင်ပါသည်-

* |nix| Do this (ဒီအရာကိုလုပ်ပါ)
* |win| Do that (ထိုအရာကိုလုပ်ပါ)
* |osx| Or do that (သို့မဟုတ် ထိုအရာကိုလုပ်ပါ)

သို့မဟုတ် စာပိုဒ်များအနေဖြင့်-

|nix| |osx| ဒီအရာ နှင့် ဒီအရာ နှင့် ဒီအရာ ကိုလုပ်ပါ။ ထို့နောက် ဒီအရာ နှင့် ဒီအရာ နှင့် ဒီအရာ၊ ပြီးလျှင် ဒီအရာ နှင့် ဒီအရာ နှင့် ဒီအရာ၊ ထပ်ပြီးလျှင် ဒီအရာ နှင့် ဒီအရာ နှင့် ဒီအရာ ကို လုပ်ပါ။

|win| ထိုအရာကိုလုပ်ပါ။ ထို့နောက် ထိုအရာ နှင့် ထိုအရာနှင့် ထိုအရာ ကိုလုပ်ပါ၊ ပြီးလျှင် ထိုအရာ နှင့် ထိုအရာ နှင့် ထိုအရာ၊ ထို့နောက် ထိုအရာ နှင့် ထိုအရာ နှင့် ထိုအရာ၊ ပြီးလျှင် ထိုအရာ နှင့် ထိုအရာ ကိုလုပ်ပါ။

အသုံးပြုသူလမ်းညွှန်စာအုပ်တစ်ခုလုံးမှာပါသည့် screenshot များကို ပလက်ဖောင်းအမျိုးမျိုးပေါ်တွင် ဖန်တီးခဲ့ပါသည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |addRasterLayer| image:: /static/common/mActionAddRasterLayer.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |inputText| image:: /static/common/inputtext.png
.. |nix| image:: /static/common/nix.png
   :width: 1em
.. |osx| image:: /static/common/osx.png
   :width: 1em
.. |radioButtonOff| image:: /static/common/radiobuttonoff.png
   :width: 1.5em
.. |radioButtonOn| image:: /static/common/radiobuttonon.png
   :width: 1.5em
.. |selectColor| image:: /static/common/selectcolor.png
.. |selectNumber| image:: /static/common/selectnumber.png
   :width: 2.8em
.. |selectString| image:: /static/common/selectstring.png
   :width: 2.5em
.. |slider| image:: /static/common/slider.png
.. |win| image:: /static/common/win.png
   :width: 1em
