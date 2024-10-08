﻿.. index:: Digitizing, Topology, Geometry validity, Errors
   single: Plugins; Geometry checker


.. _geometry_checker:


Geometry Checker Plugin (ဂျီဩမေတြီစစ်ဆေးပေးသည့်အရာ Plugin)
===========================================================

Geometry Checker သည် Layer တစ်ခု၏ ဂျီဩမေတြီ မှန်ကန်မှုရှိ/မရှိ စစ်ဆေးနိုင်ပြီး ပြင်ဆင်ခြင်းကိုလုပ်ဆောင်နိုင်သည့် အသုံးဝင်သော ပင်မ plugin တစ်ခုဖြစ်ပါသည်။ ၎င်းကို :menuselection:`Vector` menu တွင်ဝင်ရောက်လုပ်ဆောင်နိုင်ပါသည် (|geometryChecker| :menuselection:`Check Geometries...`)။


Configuring the checks (စစ်ဆေးမှုများကို သတ်မှတ်ခြင်း)
-------------------------------------------------------

:guilabel:`Check Geometries` dialog သည် ပထမဆုံး tab (:guilabel:`Setup`) တွင် အမျိုးမျိုးသော setting များကို အုပ်စုအလိုက် ပြသထားပါသည်- 

* :guilabel:`Input vector layers` - စစ်ဆေးမည့် layer များကို ရွေးချယ်နိုင်သည်။ :guilabel:`Only selected features` (ရွေးချယ်ထားသော feature များသာလျှင်) checkbox သည် ရွေးချယ်ထားသော feature များ၏ ဂျီဩမေတြီများကို စစ်ဆေးခြင်းပြုလုပ်ရာတွင် ကန့်သတ်ရန် အသုံးပြုနိုင်ပါသည်။


* :guilabel:`Allowed geometry types` gives the chance to restrict the geometry
  type of the input layer(s) to:

* :guilabel:`Allowed geometry types` (ခွင့်ပြုထားသော ဂျီဩမေတြီ အမျိုးအစားများ) သည် ထည့်သွင်းလိုက်သော Layer (များ) ၏ ဂျီဩမေတြီအမျိုးအစားများကို ကန့်သတ်ပေးနိုင်ပါသည်- 

  * |checkbox| Point (အမှတ်)
  * |checkbox| Multipoint (အမှတ်များ)
  * |checkbox| Line (မျဉ်း)
  * |checkbox| Multiline (မျဉ်းများ)
  * |checkbox| Polygon (ဗဟုဂံ)
  * |checkbox| Multipolygon (ဗဟုဂံများ)

* :guilabel:`Geometry validity` သည် ဂျီဩမေတြီအမျိုးအစားပေါ်မူတည်၍ အောက်ပါတို့ကို ရွေးချယ်နိုင်ပါသည်- 
 
  * |checkbox| :guilabel:`Self intersections` (ကိုယ်တိုင် ဖြတ်ခြင်း)
  * |checkbox| :guilabel:`Duplicate nodes` (ဆုံမှတ်များ ပုံတူပွားခြင်း)
  * |checkbox| :guilabel:`Self contacts` (ကိုယ်တိုင် ထိစပ်ခြင်း)
  * |checkbox| :guilabel:`Polygon with less than 3 nodes` (ဆုံမှတ် (၃)ခုထက် နည်းသော polygon)

* :guilabel:`Geometry properties` သည် ဂျီဩမေတြီအမျိုးအစားပေါ်မူတည်၍ အောက်ပါ ရွေးချယ်စရာအမျိုးမျိုးကို လုပ်ဆောင်နိုင်ပါသည်- 

  * |checkbox| :guilabel:`Polygons and multipolygons may not contain any holes` (Polygon နှင့် multipolygon များတွင် အပေါက်များ မပါဝင်နိုင်ပါ)
  * |checkbox| :guilabel:`Multipart objects must consist of more than one part` (အစိတ်အပိုင်းများစွာပါဝင်သော အရာများတွင် တစ်ခုထက်ပိုသော အစိတ်အပိုင်းများပါဝင်ရမည်)
  * |checkbox| :guilabel:`Lines must not have dangles` (မျဉ်းများတွင် မျဉ်းပြတ်များ မပါဝင်ရ) 

* :guilabel:`Geometry conditions` သည် ဂျီဩမေတြီများကို ခိုင်လုံမှန်ကန်မှုရှိစေရန် အခြေအနေအချို့ကို ထည့်သွင်းနိုင်ပါသည်-

  * |checkbox| :guilabel:`Minimal segment length (map units)` |selectNumber| (အနည်းဆုံးမျဉ်းပိုင်းအလျား (မြေပုံယူနစ်ဖြင့်)) 
  * |checkbox| :guilabel:`Minimum angle between segment (deg)` |selectNumber| (မျဉ်းပိုင်းများကြားရှိ အငယ်ဆုံးထောင့် (ဒီဂရီ)) 
  * |checkbox| :guilabel:`Minimal polygon area (map units sqr.)` |selectNumber| (အနည်းဆုံး polygon ဧရိယာ (စတုရန်းမြေပုံယူနစ်)) 
  *  :guilabel:`Maximum thinness` |selectNumber| (အများဆုံးအထူ) နှင့် |checkbox| :guilabel:`Max. area  (map units sqr.)` |selectNumber| (အများဆုံးဧရိယာ) ရှိသည့် |checkbox| :guilabel:`No sliver polygons` (သေးငယ်သည့် polygon အပိုင်းအစများမပါဝင်စေခြင်း)

* :guilabel:`Topology checks` (ဆက်စပ်တည်ရှိမှုအရ ဖွဲ့စည်းပုံစစ်ဆေးမှုများ) သည် ဂျီဩမေတြီအမျိုးအစားပေါ်မူတည်၍ အောက်ပါရွေးချယ်မှုအမျိုးမျိုးကို လုပ်ဆောင်နိုင်ပါသည်- 

  * |checkbox| :guilabel:`Checks for duplicates` (ပုံတူများကိုစစ်ဆေးခြင်း)
  * |checkbox| :guilabel:`Checks for features within other features` (အခြား feature များအတွင်းရှိ feature များကို စစ်ဆေးခြင်း)
  * |checkbox| :guilabel:`Checks for overlaps smaller than` |selectNumber| (ရွေးချယ်ထားသော တန်ဖိုးထက်ငယ်သည့် ထပ်နေခြင်းများကို စစ်ဆေးခြင်း)
  * |checkbox| :guilabel:`Checks for gaps smaller than` |selectNumber| (ရွေးချယ်ထားသော တန်ဖိုးထက်ငယ်သည့် ကွက်လပ်များကို စစ်ဆေးခြင်း)
  * |checkbox| :guilabel:`Points must be covered by lines` (Point များကို line များဖြင့် ဖုံးအုပ်ရမည်)
  * |checkbox| :guilabel:`Points must properly lie inside a polygon` (Point များသည် polygon တစ်ခုအတွင်း သင့်လျော်စွာ တည်ရှိရမည်)
  * |checkbox| :guilabel:`Lines must not intersect any other lines` (Line များသည် အခြား line များနှင့် ဖြတ်သွားခြင်းမျိုးမရှိရပါ)
  * |checkbox| :guilabel:`Lines must not intersect with features of layer` |selectString| (Line များသည် Layer ၏ feature များကို မဖြတ်ရပါ) 
  * |checkbox| :guilabel:`Polygons must follow boundaries of layer` |selectString| (Polygon များသည် layer ၏ နယ်နိမိတ်များအတိုင်း ဖြစ်ရမည်) 

* :guilabel:`Tolerance` (လက်ခံနိုင်မှု) သည် စစ်ဆေးခြင်း၏ tolerance (လက်ခံနိုင်မှု) ကို မြေပုံယူနစ်ဖြင့် သတ်မှတ်နိုင်ပါသည်။ 
* :guilabel:`Output vector layer` (ရလဒ် vector layer) ဖြင့် အောက်ပါတို့ကို လုပ်ဆောင်နိုင်ပါသည်- 

  * |radioButtonOn| :guilabel:`Modify input layer` (ထည့်သွင်းလိုက်သော Layer ကို မွမ်းမံပြင်ဆင်ခြင်း)
  * |radioButtonOn| :guilabel:`Create new layers` (Layer အသစ်များဖန်တီးခြင်း)

သတ်မှတ်ချက်များကို စိတ်တိုင်းကျပြင်ဆင်ပြီးလျှင် :guilabel:`Run` (လုပ်ဆောင်ခြင်း) ခလုတ်ကို click နှိပ်နိုင်ပါပြီ။ 


.. _figure_geometry_checker:


.. figure:: img/check_geometries.png
   :align: center


   Geometry Checker Plugin


*Geometry Checker Plugin* သည် အောက်ပါ မှားယွင်းမှုများကို ရှာဖွေပေးနိုင်ပါသည်- 

* Self intersections- ကိုယ်တိုင်ထိဖြတ်မှုရှိသည့် polygon တစ်ခု
* Duplicate nodes- မျဉ်းပိုင်းတစ်ခုအတွင်း ပုံတူပွားထားသည့် ဆုံမှတ် (node) နှစ်ခု
* Holes- Polygon တစ်ခုအတွင်းရှိ အပေါက်
* Segment length- ကန့်သတ်ထားသော တန်ဖိုးအောက် နည်းနေသည့် မျဉ်းပိုင်းအလျား
* Minimum angle- ကန့်သတ်ထားသောတန်ဖိုးအောက် နည်းနေသည့် ထောင့်တစ်ခုရှိသည့် မျဉ်းပိုင်းနှစ်ခု
* Minimum area- ကန့်သတ်ထားသောတန်ဖိုးအောက် နည်းနေသည့် polygon ဧရိယာ
* Sliver polygon- ဤ error သည် ပတ်လည်အနားတန်ဖိုးများပြီး အလွန်သေးငယ်သော polygon (သေးငယ်သောဧရိယာဖြင့်) ကြောင့် ဖြစ်ပေါ်လာခြင်းဖြစ်သည်။ 
* Feature ပုံတူပွားများ
* Feature အတွင်းရှိ feature များ
* Overlaps- Polygon များထပ်နေခြင်း
* Gaps- Polygon များအကြားရှိ ကွက်လပ်များ

အောက်ဖော်ပြပါပုံသည် ဤ plugin ဖြင့် လုပ်ဆောင်ထားသော စစ်ဆေးမှုအမျိုးမျိုးကို ပြသထားပါသည်။ 
 
.. _figure_geometry_checker_options:


.. figure:: img/geometry_checker_scheme.png
   :align: center

   Plugin မှလုပ်ဆောင်နိုင်သော စစ်ဆေးမှုအချို့

Analysing the results (ရလာဒ်များကို ခွဲခြမ်းစိတ်ဖြာခြင်း)
----------------------------------------------------------

ရလာဒ်များသည် ဒုတိယ tab (:guilabel:`Result`) တွင်ပေါ်လာမည်ဖြစ်ပြီး error များကို ခြုံငုံကြည့်ရှုနိုင်သော Layer တစ်ခုအဖြစ် မြေပုံမြင်ကွင်းတွင် တွေ့မြင်ရမည်ဖြစ်ပါသည် (၎င်း၏အမည်တွင် default အနေဖြင့် အစ စကားလုံး :file:`checked_` ဟူ၍ ပါရှိပါသည်)။ ဇယားတစ်ခုတွင် :guilabel:`Geometry check result` ကို error တစ်ခုလျှင် row တစ်ခုအနေဖြင့် ဖော်ပြနေမည်ဖြစ်ပြီး column များတွင် Layer အမည်၊ ID၊ error အမျိုးအစား၊ error ၏ကိုဩဒိနိတ်များ၊ တန်ဖိုးတစ်ခု (error အမျိုးအစားပေါ်မူတည်၍) နှင့် နောက်ဆုံးအနေဖြင့် error ကို ဖြေရှင်းနိုင်မည့် ဖြေရှင်းနည်းကို ဖော်ပြသော ဖြေရှင်းနည်း column တို့ ပါဝင်ပါသည်။ အဆိုပါဇယား၏အောက်ခြေတွင် error များကို အမျိုးမျိုးသော ဖိုင်ပုံစံများအဖြစ်သို့ :guilabel:`Export` (ထုတ်ယူခြင်း) ကို ပြုလုပ်နိုင်ပါသည်။ Error အရေအတွက် စုစုပေါင်းနှင့် ပြင်ဆင်ပြီးအရေအတွက် စုစုပေါင်းတို့ကိုဖော်ပြသည့် ရေတွက်မှုတစ်ခုလည်းရှိပါသည်။

Error ၏ တည်နေရာကို သိရှိနိုင်ရန် ဇယား၏ row တစ်ခုကို ရွေးချယ်နိုင်ပါသည်။ ဤလုပ်ဆောင်ချက်ကို |radioButtonOn| :guilabel:`Error`(default) ၊ |radioButtonOff| :guilabel:`Feature` ၊ |radioButtonOff| :guilabel:`Don't move` နှင့် |checkbox| :guilabel:`Highlight selected features` တို့အကြား အခြားလုပ်ဆောင်ချက်တစ်ခုခုကို ရွေးချယ်၍ ပြောင်းလဲနိုင်ပါသည်။

ဇယား row ကို click နှိပ်လိုက်ပါက ချုံ့/ချဲ့ ကြည့်ရှုခြင်း လုပ်ဆောင်ချက်အောက်တွင် အောက်ပါတို့ကို လုပ်ဆောင်နိုင်ပါသည်-


* |fromSelectedFeature| :guilabel:`Show selected features in attribute table` (အချက်အလက်ဇယားတွင် ရွေးချယ်ပြီး feature များကို ပြသခြင်း)
* |success| :guilabel:`Fix selected errors using default resolution` (Default ဖြေရှင်းနည်းကိုအသုံးပြု၍ ရွေးချယ်ထားသော error များကို ပြင်ဆင်ခြင်း)
* |success| :guilabel:`Fix selected errors, prompt for resolution method` (ရွေးချယ်ထားသော error များကို ပြင်ဆင်ခြင်းနှင့် ဖြေရှင်းမည့်နည်းလမ်းအတွက် သတိပေးခြင်း) ဖြေရှင်းရမည့် နည်းလမ်းများကို အောက်ပါတို့ထဲမှ ရွေးချယ်ရန် window တစ်ခုကို တွေ့မြင်ရမည်ဖြစ်ပါသည်- 

  * Merge with neighboring polygon with longest shared edge (အရှည်လျားဆုံးထိစပ်နေသော edge များရှိသော အနီးအနားရှိ polygon နှင့် ပေါင်းစပ်ခြင်း)
  * Merge with neighboring polygon with largest area (ဧရိယာအကြီးဆုံးရှိသော အနီးအနားရှိ polygon နှင့်ပေါင်းစပ်ခြင်း)
  * Merge with neighboring polygon with identical attribute value, if any, or leave as is (အကယ်၍ရှိပါက ဇယားတန်ဖိုးတထပ်တည်းတူညီသည့် အနီးအနားရှိ polygon နှင့်ပေါင်းစပ်ခြင်း၊ သို့မဟုတ် မူရင်းအတိုင်းထားခြင်း)
  * Delete feature (feature ကိုဖျက်ခြင်း)
  * No action (မည်သည့်လုပ်ဆောင်ချက်မှ မလုပ်ဆောင်ခြင်း)

* |options| :guilabel:`Error resolution settings` သည် error အမျိုးအစားပေါ်မူတည်၍ သတ်မှတ်ထားသည့် default ဖြေရှင်းနည်းများကို ပြောင်းလဲနိုင်စေပါသည်။

.. tip:: **Error များစွာကို ပြင်ဆင်ခြင်း**

   ဇယားအတွင်းရှိ တစ်ခုထက်ပိုသော row များစွာကို *CTRL + click* ဖြင့် ရွေးချယ်ပြီး error များစွာကို ပြင်ဆင်နိုင်ပါသည်။ 

နောက်ဆုံးတွင် attribute တန်ဖိုးများဖြင့် feature များပေါင်းစပ်ရာတွင် အသုံးပြုမည့် attribute ကို ရွေးချယ်နိုင်မည်ဖြစ်ပါသည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.


.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |fromSelectedFeature| image:: /static/common/mActionFromSelectedFeature.png
   :width: 1em
.. |geometryChecker| image:: /static/common/geometrychecker.png
   :width: 1.5em
.. |options| image:: /static/common/mActionOptions.png
   :width: 1em
.. |radioButtonOff| image:: /static/common/radiobuttonoff.png
   :width: 1.5em
.. |radioButtonOn| image:: /static/common/radiobuttonon.png
   :width: 1.5em
.. |selectNumber| image:: /static/common/selectnumber.png
   :width: 2.8em
.. |selectString| image:: /static/common/selectstring.png
   :width: 2.5em
.. |success| image:: /static/common/mIconSuccess.png
   :width: 1em