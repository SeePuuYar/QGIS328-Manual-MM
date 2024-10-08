The Shape Items (ပုံသဏ္ဍာန် Item များ)
=======================================

.. only:: html

   .. contents::
      :local:

QGIS တွင် print layout (ပုံထုတ်အပြင်အဆင်) ပေါ်၌ ပုံမှန် သို့မဟုတ် ပိုမိုရှုပ်ထွေးသော ပုံသဏ္ဍာန်များရေးဆွဲရန် ကိရိယာများကို ပံ့ပိုးပေးထားပါသည်။

.. note::
   အခြား print layout item များနှင့်မတူသည့်အချက်မှာ ပုံသဏ္ဍာန်ဘောင်၏ စတိုင် သို့မဟုတ် နောက်ခံအရောင်ကို ပြောင်းလဲ၍မရခြင်းဖြစ်သည် (Default အားဖြင့် transparent ဟုသတ်မှတ်ထားသည်)။ 


.. index:: 
   single: Layout item; Basic shape
.. _layout_basic_shape_item:

The Regular Shape Item (ပုံမှန် ပုံသဏ္ဍာန် Item)
-------------------------------------------------

:guilabel:`Shape` item သည် တြိဂံ၊ ထောင့်မှန်စတုဂံနှင့် ဘဲဥပုံသဏ္ဍာန်များ...ကဲ့သို့သော ပုံမှန် ပုံသဏ္ဍာန်များဖြင့် မြေပုံအားအလှဆင်နိုင်မည့် tool တစ်ခုဖြစ်သည်။ သီးသန့် tool များဖြစ်သော |addBasicRectangle| :sup:`Add Rectangle` ၊ |addBasicCircle| :sup:`Add Ellipse` နှင့် |addBasicTriangle| :sup:`Add Triangle` တို့ကိုရယူအသုံးပြုနိုင်သည့် |addBasicShape| :sup:`Add Shape` tool မှတစ်ဆင့် ပုံမှန် ပုံသဏ္ဍာန်တစ်ခုကိုထည့်သွင်းနိုင်သည်။ သင့်တော်သော tool ကိုရွေးချယ်ပြီးသည်နှင့် :ref:`item များဖန်တီးခြင်းဆိုင်ရာ ညွှန်ကြားချက်များ <create_layout_item>` ကိုလိုက်နာ၍ item ကိုရေးဆွဲနိုင်ပြီဖြစ်သည်။ အခြား layout item များကဲ့သို့ပင် ပုံမှန် ပုံသဏ္ဍာန်တစ်ခုအား :ref:`interact_layout_item` တွင်ပြသထားသည့်နည်းလမ်းအတိုင်း ကိုင်တွယ်နိုင်မည်ဖြစ်သည်။

.. note::  အခြေခံပုံသဏ္ဍာန်တစ်ခုကို click နှိပ်၍ drag ဆွဲခြင်းနည်းလမ်းအသုံးပြု၍ ဆွဲသည့်အခါ :kbd:`Shift` ခလုတ်ကိုဖိထားခြင်းဖြင့် ပြည့်စုံသေသပ်သောစတုရန်း၊ စက်ဝိုင်း သို့မဟုတ် တြိဂံတစ်ခုဖန်တီးနိုင်မည်ဖြစ်သည်။ 

Default ပါဝင်သည့် ပုံသဏ္ဍာန် ကို ၎င်း၏ :guilabel:`Item Properties` panel အားအသုံးပြု၍ စိတ်ကြိုက်ပြင်ဆင်နိုင်သည်။ :ref:`item များ၏ဘုံဂုဏ်သတ္တိများ <item_common_properties>` အပြင် ဤ feature တွင်အောက်ပါလုပ်ဆောင်ချက်များပါရှိသည် (:numref:`figure_layout_basic_shape` ကိုကြည့်ပါ)-

.. _figure_layout_basic_shape:

.. figure:: img/shape_properties.png
   :align: center

   ပုံသဏ္ဍာန် Item ဂုဏ်သတ္တိများ Panel

ပေးထားသော frame အတွင်းတွင် :guilabel:`Main properties` အုပ်စုဖြင့် ပုံသဏ္ဍာန်၏အမျိုးအစား  (**ဘဲဥပုံသဏ္ဍာန်** ၊ **ထောင့်မှန်စတုဂံ** သို့မဟုတ် **တြိဂံ**) ကိုကြည့်ရှုနိုင်၍ ပြောင်းလဲနိုင်သည်။
 
အဆင့်မြင့် :ref:`သင်္ကေတ <symbol-selector>` နှင့် :ref:`အရောင် <color-selector>` ရွေးချယ်ပေးသည့်အရာ widget...တို့အားအသုံးပြု၍ ပုံသဏ္ဍာန်၏ style အားသတ်မှတ်နိုင်သည်

ထောင့်မှန်စတုဂံပုံသဏ္ဍာန်အတွက် ထောင့်စွန်းများကိုလုံးရန် :guilabel:`Corner radius` ၏တန်ဖိုးကို အမျိုးမျိုးသော ယူနစ်များဖြင့် သတ်မှတ်နိုင်သည်။ 


.. index::
   single: Layout item; Node-based shape
.. _layout_node_based_shape_item:

The Node-Based Shape Items (အဆစ်များကိုအခြေခံသည့် ပုံသဏ္ဍာန် Item များ)
------------------------------------------------------------------------

|addBasicShape| :guilabel:`Add Shape` tool ဖြင့် ရိုးရှင်း၍ ကြိုတင်သတ်မှတ်ထားသောသမားရိုးကျ ဂျီဩမေတြီ ပုံသဏ္ဍာန်များ ဖန်တီးနိုင်မည်ဖြစ်ပြီး |addNodesShape| :guilabel:`Add Node Item` tool ဖြင့် ပို၍အဆင့်မြင့်သော ဂျီဩမေတြီ item များကို စိတ်ကြိုက်ဖန်တီးနိုင်မည်ဖြစ်သည်။

Polyline များ သို့မဟုတ် polygon များအတွက် အလိုရှိသလောက် မျဉ်းများ သို့မဟုတ် အနားများကို ရေးဆွဲနိုင်ပြီး |editNodesShape| :guilabel:`Edit Nodes Item` အားအသုံးပြု၍ item များ၏ vertex (မျဉ်းအဆစ်) များကို မည်သည့်အရာကိုမျှမမှီခိုဘဲ တိုက်ရိုက်ကိုင်တွယ်နိုင်မည်ဖြစ်သည်။ :ref:`interact_layout_item` တွင်ဖော်ပြထားသည့်အတိုင်း ပုံသဏ္ဍာန် အား ကိုင်တွယ်နိုင်မည်ဖြစ်သည်။
 
အဆစ်များကိုအခြေခံသည့် ပုံသဏ္ဍာန်တစ်ခုကိုထည့်သွင်းရန်-

#. |addNodesShape| :sup:`Add Node Item` သင်္ကေတပေါ်တွင် Click နှိပ်ပါ။
#. |addPolygon| :sup:`Add Polygon` tool ကိုဖြစ်စေ |addPolyline| :sup:`Add Polyline` tool ကိုဖြစ်စေရွေးချယ်ပါ။ 
#. Item တွင် အဆစ်များထည့်ရန်အတွက် left click များဆက်တိုက်နှိပ်သွားပါ။ Segment (မျဉ်းပိုင်း) တစ်ခုဆွဲနေချိန်တွင် :kbd:`Shift` ခလုတ်ကို ဖိထားပါက 45\ |degrees| ၏ ဆတိုးဖြစ်သော ဦးတည်ရာများအတိုင်း ကန့်သတ်ရွေ့လျားမည်ဖြစ်သည်။
#. လုပ်ဆောင်ပြီးသောအခါ right-click နှိပ်၍ ပုံသဏ္ဍာန်ကို အပြီးသတ်ပါ။

:guilabel:`Item Properties` panel ထဲတွင် ပုံသဏ္ဍာန်၏အသွင်အပြင်အားစိတ်ကြိုက်ပြင်ဆင်နိုင်သည်။ 

.. _figure_layout_nodes_shape:

.. figure:: img/shape_nodes_properties.png
   :align: center

   Polygon အဆစ်ပုံသဏ္ဍာန် Item ဂုဏ်သတ္တိများ Panel

:guilabel:`Main properties` ထဲတွင် အဆင့်မြင့် :ref:`သင်္ကေတ <symbol-selector>` နှင့် :ref:`အရောင် <color-selector>` ရွေးချယ်ပေးသည့်အရာ widget... အားအသုံးပြု၍ ပုံသဏ္ဍာန်၏ style အားသတ်မှတ်နိုင်သည်။

Polyline အဆစ် item များအတွက် :guilabel:`Line markers` (လိုင်းအမှတ်အသား) များအားစိတ်ကြိုက်ပြင်ဆင်နိုင်သည်၊ ဆိုလိုသည်မှာ- 

* ရွေးချယ်စရာများဖြင့် အစ နှင့်/သို့မဟုတ် အဆုံး အမှတ်အသားများထည့်သွင်းရန်-

  * :guilabel:`None` - ရိုးရှင်းသော polyline တစ်ခုကိုဆွဲပေးသည်။
  * :guilabel:`Arrow` - စိတ်ကြိုက်ပြင်ဆင်နိုင်မည့် ပုံမှန် တြိဂံပုံ မြှားခေါင်းတစ်ခုကိုထည့်သွင်းပေးသည်။
  * :guilabel:`SVG` အမှတ်အသား - :file:`SVG` file တစ်ခုအား item ၏မြှားခေါင်းတစ်ခုအဖြစ်အသုံးပြုပေးသည်။

* မြှားခေါင်းကိုစိတ်ကြိုက်ပြင်ဆင်ရန်- 

  * :guilabel:`Arrow stroke color` - မြှားခေါင်း၏အပြင်အနားသတ်အ‌ရောင်ကိုသတ်မှတ်ပေးသည်။
  * :guilabel:`Arrow fill color` - မြှားခေါင်း၏အတွင်းဖြည့်ထားသည့်အရောင်ကိုသတ်မှတ်ပေးသည်။
  * :guilabel:`Arrow stroke width` - မြှားခေါင်း၏အပြင်အနားသတ်အထူကိုသတ်မှတ်ပေးသည်။
  * :guilabel:`Arrow head width` - မြှားခေါင်း၏အရွယ်အစားကိုသတ်မှတ်ပေးသည်။

SVG ပုံများသည် မျဉ်းများ၏ ဦးတည်ရာအတိုင်းလိုက်၍ အလိုအလျောက် လှည့်နိုင်သည်။ QGIS တွင်ကြိုတင်သတ်မှတ်ထားသော SVG ပုံများ၏ Stroke (အပြင်အနားသတ်) အရောင် နှင့် Fill (အဖြည့်) အရောင်များကို သက်ဆိုင်ရာရွေးချယ်စရာများကိုအသုံးပြု၍ ပြောင်းလဲနိုင်သည်။ SVG ကို စိတ်ကြိုက်ပြင်ဆင်ရာတွင် ဤ :ref:`ညွှန်ကြားချက် <parameterized_svg>` ကိုလိုက်နာရန်လိုအပ်နိုင်သည်။


.. _figure_layout_arrow:

.. figure:: img/arrow_properties.png
   :align: center

   Polyline အဆစ်ပုံသဏ္ဍာန် Item ဂုဏ်သတ္တိများ Panel

.. index:: 
   single: Layout item; Arrow
.. _layout_arrow_item:

The Arrow Item (မြှား Item)
............................

|addArrow| :sup:`Add Arrow` tool သည် default အားဖြင့် မြှားပါဝင်သော polyline တစ်ခုကိုဖန်တီးရန် ဖြတ်လမ်းတစ်ခုဖြစ်သောကြောင့် ၎င်း၏ ဂုဏ်သတ္တိများနှင့် အလုပ်လုပ်ပုံမှာ :ref:`polyline node item <layout_node_based_shape_item>` နှင့်တူညီသည်။

အမှန်တွင် ရိုးရှင်းသော မြှားတစ်ခုကို ထည့်ရန် မြှား item ကိုအသုံးပြုနိုင်သည်၊ ဥပမာအားဖြင့် မတူညီသော print layout item နှစ်ခုကြားရှိ ဆက်နွယ်မှုကိုညွှန်ပြလိုသည့်အခါဖြစ်သည်။ သို့သော်လည်း မြောက်အရပ်ပြမြှားတစ်ခုကို ဖန်တီးရာတွင် မြေပုံ item တစ်ခုနှင့် sync လုပ်နိုင်ပြီး ၎င်းမြေပုံ item အတိုင်း အလိုအလျောက်လှည့်ပေးနိုင်သော :file:`.SVG` format ဖြင့် မြောက်အရပ်ပြမြှားသို့ :ref:`image item <layout_picture_item>` သည်ဝင်ရောက်ခွင့်ပေးသောကြောင့် ၎င်း image item အား ဦးစွာ စဉ်းစားသင့်ပါသည်။

Editing a node item geometry (အဆစ် item ဂျီဩမေတြီတစ်ခုအားတည်းဖြတ်ခြင်း)
........................................................................

|editNodesShape| :sup:`Edit Nodes Item` ဖြင့် အဆစ်အခြေခံသည့်ပုံသဏ္ဍာန်များကို တည်းဖြတ်ရန် သီးသန့် tool တစ်ခုကို ပံ့ပိုးပေးထားသည်။ ဤ mode အတွင်းတွင် အဆစ်တစ်ခုပေါ်တွင် click နှိပ်ခြင်းဖြင့် ၎င်းကိုရွေးချယ်နိုင်သည် (ရွေးချယ်ထားသော အဆစ်ပေါ်တွင် အမှတ်အသားတစ်ခုအားပြသပေးသည်)။ ရွေးချယ်ထားသော အဆစ်တစ်ခုအား drag ဆွဲခြင်းဖြင့်ဖြစ်စေ ကီးဘုဒ်မှ မြှားခလုတ်များ အသုံးပြုခြင်းဖြင့်ဖြစ်စေ ရွှေ့နိုင်သည်။ ထို့အပြင် ဤ mode တွင် ရှိပြီးသားပုံသဏ္ဍာန်တစ်ခုသို့ အဆစ်များထည့်သွင်းနိုင်သည်- မျဉ်းပိုင်းတစ်ခုပေါ်တွင် click နှစ်ချက်နှိပ်ပါက click နှိပ်သောနေရာတွင် အဆစ်တစ်ခုထည့်ပြီးသားဖြစ်သွားမည်။ နောက်ဆုံးတွင် :kbd:`Del` ခလုတ်အားနှိပ်၍ လက်ရှိရွေးချယ်ထားသောအဆစ်အားဖယ်ရှားနိုင်မည်ဖြစ်သည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

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
.. |addNodesShape| image:: /static/common/mActionAddNodesShape.png
   :width: 1.5em
.. |addPolygon| image:: /static/common/mActionAddPolygon.png
   :width: 1.5em
.. |addPolyline| image:: /static/common/mActionAddPolyline.png
   :width: 1.5em
.. |degrees| unicode:: 0x00B0
   :ltrim:
.. |editNodesShape| image:: /static/common/mActionEditNodesShape.png
   :width: 1.5em
