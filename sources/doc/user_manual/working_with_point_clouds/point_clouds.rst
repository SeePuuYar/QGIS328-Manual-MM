.. index:: Point cloud
.. _working_with_point_clouds:

*****************************************************************
Working with Point Clouds (Point Cloud များဖြင့် အလုပ်လုပ်ခြင်း)
*****************************************************************

.. only:: html

   .. contents::
      :local:

.. _point_clouds_introduction:

Point Cloud မိတ်ဆက် (Introduction to Point Clouds)
===================================================

**What is A Point Cloud? (Point Cloud ဆိုတာဘာလဲ)**

များစွာသော data အမှတ် တစ်ခုချင်းစီ (သန်းဂဏန်း၊ သန်းထောင်ဂဏန်း အထိရှိနိုင်) ဖြင့် ဖန်တီးထားသော သုံးဖက်မြင်ဓာတ်ပုံတစ်ခုကို point cloud ဟုခေါ်ပါသည်။ အမှတ်တစ်ခုချင်းစီသည် X၊ Y၊ Z တည်နေရာတန်ဖိုးများ ပါရှိပါသည်။ ဖမ်းယူလိုက်သည့် နည်းလမ်းပေါ်မူတည်ပြီး အရောင်တန်ဖိုး သို့မဟုတ် ပြင်းအား များကဲ့သို့ ဖမ်းယူမှုမှ ရရှိလာသည့် ထပ်ပေါင်းအချက်အလက်များလည်း ရှိပါသေးသည်။ ဥပမာ- ထိုအချက်အလက်များ အသုံးပြုပြီး point cloud များကို အရောင်အမျိုးမျိုးဖြင့် ပြသနိုင်ပါသည်။ QGIS တွင် နေရာတစ်ခု (သို့မဟုတ် တခြားတစ်နေရာ) ရဲ့ သုံးဖက်မြင်ပုံကို ဖန်တီးရန် point cloud ကိုအသုံးပြုနိုင်ပါသည်။ 

**Supported Formats (အသုံးပြုနိုင်သော format များ)**

Entwine Point Tile (EPT) နှင့် LAS/LAZ data format များကို QGIS တွင်အသုံးပြုနိုင်ပါသည်။ Point cloud များနှင့်အလုပ်လုပ်ရန် QGIS သည် data များကို EPT format အဖြစ်သိမ်းဆည်းပေးပါသည်။ EPT ဆိုသည်မှာ အသုံးများသော (common) folder ထဲတွင် သိမ်းဆည်းထားပေးသည့် file များစွာပါဝင်သော သိုလှောင်ခြင်း (storage) format တစ်မျိုးဖြစ်ပါသည်။ Data များကိုမြန်မြန်ဆန်ဆန် အသုံးပြုနိုင်ရန် EPT သည် indexing (ညွှန်ပြခြင်း) နည်းလမ်းကိုအသုံးပြုပါသည်။ EPT format အကြောင်းပိုမိုသိလိုလျှင် `entwine homepage <https://entwine.io/entwine-point-tile.html>` တွင်ဖတ်ရှုပါ။

Data သည် LAS သို့မဟုတ် LAZ format ဖြစ်နေလျှင် ပထမဆုံးအကြိမ် အသုံးပြုသောအခါ QGIS သည် EPT format အဖြစ်သို့ ပြောင်းလဲပေးပါလိမ့်မည်။ File ရဲ့အရွယ်အစားပေါ်မူတည်ပြီး ကြာချိန်ကွာခြားနိုင်ပါသည်။ ဤလုပ်ငန်းစဉ်တွင် folder ထဲ၌ subfolder တစ်ခုဖန်တီးပြီး အစီအစဉ် :file:`ept_` + :file:`name_LAS/LAZ_file` အရ LAS/LAZ file ကို subfolder ထဲတွင် ထားရှိပေးမည်ဖြစ်သည်။ ထိုသို့သော subfolder တစ်ခု ရှိနေပြီးသားဆိုလျှင် QGIS သည် EPT ကို ချက်ချင်းဆွဲထည့်ပေးပါသည် (အလုပ်လုပ်ချိန်သက်သာစေပါသည်)။

**သိထားသင့်သည်များ (Worth Knowing)**

QGIS တွင် point cloud များကို တည်းဖြတ်ပြင်ဆင်ရန် မရနိုင်သေးပါ။ Point cloud များကို ပြင်ဆင်လိုလျှင် အခမဲ့အသုံးပြုနိုင်သော point cloud processing tool တစ်ခုဖြစ်သော `CloudCompare <https://www.cloudcompare.org/>` ကို အသုံးပြုနိုင်ပါသည်။ Point cloud များကို တည်းဖြတ်ပြင်ရန်အတွက် `Point Data Abstraction Library <https://pdal.io/en/stable/>` (PDAL- GDAL နှင့် ဆင်တူသော) ကိုလည်း အသုံးပြုနိုင်ပါသည်။ (PDAL သည် command line ဖြင့်သာ လုပ်ဆောင်နိုင်ပါသည်)

အရေအတွက်များပြားသော Data point များကြောင့် QGIS ထဲတွင် point cloud များရဲ့ အချက်အလက်ဇယား (attribute table) ကို ဖွင့်ကြည့်ရန် မဖြစ်နိုင်ပါ။ သို့သော် |identify| :ref:`Identify tool <identify>` ဖြင့် point cloud ၏ attribute များအားလုံးကို ကြည့်ရှုနိုင်ရုံသာမက data point တစ်ခုချင်းစီ၏ attribute များကိုပါ ကြည့်ရှုနိုင်ပါသည်။

.. _`point_clouds_properties`:

Point Clouds Properties (Point cloud များ၏ ဂုဏ်သတ္တိများ)
==========================================================

Point cloud layer ရဲ့ :guilabel:`Layer Properties` dialog သည် layer အတွက် အထွေထွေ setting များနှင့် ၎င်းကို ပုံဖော်ပြသခြင်းများ လုပ်ဆောင်နိုင်ပါသည်။ Layer အကြောင်း သတင်းအချက်အလက်များလည်း ထောက်ပံ့ပေးပါသည်။

:guilabel:`Layer Properties` dialog ကို အသုံးပြုရန် - 

* :guilabel:`Layers` ထဲတွင် layer ကို double-click နှိပ်ပါ သို့မဟုတ် layer ပေါ်တွင် right-click နှိပ်ပြီး ပေါ်လာသော menu မှ :guilabel:`Properties...` ကိုရွေးပါ။
* Layer ကိုရွေးချယ်ထားပြီး :menuselection:`Layer --> Layer Properties...` menu ကိုသွားပါ။

Point cloud :guilabel:`Layer Properties` dialog သည် အောက်ပါ section များကိုထောက်ပံ့ပေးပါသည်-

.. list-table::

   * - |metadata| :ref:`Information (သတင်းအချက်အလက်) <point_clouds_information>`
     - |system| :ref:`Source (မူရင်း) <point_clouds_source>`
     - |symbology| :ref:`Symbology (သင်္ကေတဆိုင်ရာ) <point_clouds_symbology>`:sup:`[1]`
   * - |3d| :ref:`3D View (၃ ဘက်မြင် မြင်ကွင်း) <point_clouds_3d>`:sup:`[1]`
     - |rendering| :ref:`Rendering (ပုံဖော်ပြသခြင်း) <point_clouds_rendering>`
     - |elevationscale| :ref:`Elevation (မြေပြင်အမြင့်) <point_clouds_elevation>`:sup:`[1]`
   * - |editMetadata| :ref:`Metadata <point_clouds_metadata>`
     - |basicStatistics| :ref:`Statistics (စာရင်းအင်းကိန်းဂဏန်းများ) <point_clouds_statistics>`
     -

:sup:`[1]` :ref:`Layer styling panel <layer_styling_panel>` တွင်လည်း ရရှိပါသည်။


.. note:: Point cloud layer ၏ property အများစုကို properties dialog အောက်ခြေရှိ :guilabel:`Style` menu ကိုအသုံးပြုပြီး :file:`.qml` file အဖြစ်သိမ်းဆည်းနိုင်သလို :file:`.qml` file မှ ခေါ်ယူအသုံးပြုနိုင်ပါသည်။ အသေးစိတ်ကို :ref:`save_layer_property` တွင် ကြည့်ရှုနိုင်ပါသည်။


.. _point_clouds_information:

Information Properties (သတင်းအချက်အလက်ဆိုင်ရာ ဂုဏ်သတ္တိများ)
-------------------------------------------------------------

|metadata| :guilabel:`Information` tab သည် ဖတ်ရှုနိုင်ရုံသာဖြစ်ပြီး လက်ရှိလုပ်ဆောင်နေသော layer ၏ အကျဉ်းချုပ်သတင်းအချက်အလက်နှင့် metadata ကို မြန်မြန်ဆန်ဆန် သိရှိနိုင်ရန် အသုံးပြုနိုင်ပါသည်။ သိရှိနိုင်သော သတင်းအချက်အလက်များမှာ- 

* Project ထဲရှိအမည်၊ file ၏မူရင်းလမ်းကြောင်း၊ နောက်ဆုံးသိမ်းဆည်းခဲ့သော အချိန်နှင့် အရွယ်အစား၊ data ဖန်တီးသူ များကဲ့သို့ အခြေခံအချက်အလက်များ။
* Data ဖန်တီးခဲ့သူပေါ်မူတည်ပြီး အမှတ်များ၏ အရေအတွက် နှင့် အကျယ်အဝန်း (extent) ။
* Coordinate Reference System - နာမည်၊ ယူနစ်များ၊ နည်းလမ်း၊ တိကျမှု၊ အညွှန်း (ပုံသေ သို့မဟုတ် ပြောင်းလဲနိုင်သည် ကိုဆိုလိုသည်)
* Data ဖန်တီးသူ ထည့်သွင်းခဲ့သော metadata များ - ဖန်တီးခဲ့သောရက်စွဲ၊ version၊ data format၊ စကေး  X/Y/Z ၊ အစရှိသည်....။ 
* |editMetadata| :ref:`Metadata <point_clouds_metadata>` tab (တည်းဖြတ်ပြင်ဆင်နိုင်သောနေရာ) မှ ရွေးချယ်ခြင်း - ရယူသုံးစွဲခွင့်၊ အကျယ်အဝန်း၊ ချိတ်ဆက်မှုများ၊ ဆက်သွယ်ရန်အချက်အလက်များ၊ သမိုင်းကြောင်း၊.....

.. _figure_point_cloud_information:

.. figure:: img/point_cloud_information.png
   :align: center

   Point cloud သတင်းအချက်အလက်ဆိုင်ရာ tab


.. _point_clouds_source:

Source Properties (မူလရင်းမြစ်၏ ဂုဏ်သတ္တိများ)
-----------------------------------------------

|system| :guilabel:`Source` tab ထဲတွင် point cloud layer ၏ အခြေခံသတင်းအချက်အလက်များကို မြင်တွေ့နိုင်သလို တည်းဖြတ်ပြင်ဆင်နိုင်ပါသည် -

* :guilabel:`Settings` (အပြင်အဆင်) - Project ထဲတွင် layer ကို identify (ဖော်ညွှန်း) လုပ်ရာတွင် အသုံးပြုမည့် layer filename နှင့်မတူအောင် layer အမည်တစ်ခုကို သတ်မှတ်ခြင်း (Layers panel၊ expression (ခိုင်းစေချက်) များနှင့်၊ မြေပုံပြင်ဆင်ခြင်း ရည်ညွှန်းချက်ထဲတွင်)
* :guilabel:`Assigned Coordinate Reference System (CRS)` (သတ်မှတ်ထားသော CRS) - Drop-down စာရင်းမှ မကြာသေးမီက အသုံးပြုခဲ့သည့် CRS တစ်ခုကိုရွေးချယ်ခြင်း သို့မဟုတ် |setProjection| set Projection Select CRS ခလုတ် (:ref:`crs_selector` တွင် ကြည့်ရှုပါ) ကိုနှိပ်ပြီး layer အတွက်သတ်မှတ်ပေးထားသော :ref:`Coordinate Reference System <layer_crs>` ကိုပြောင်းလဲနိုင်ပါသည်။ Layer အတွက်အသုံးပြုထားသော CRS မှားနေမှသာ သို့မဟုတ် CRS မရှိသောအခါများမှသာ ဒီနည်းလမ်းကိုအသုံးပြုရပါမည်။

.. _figure_point_cloud_source:

.. figure:: img/point_cloud_source.png
   :align: center

   Point cloud မူလရင်းမြစ်များဆိုင်ရာ tab


.. _point_clouds_symbology:

Symbology Properties (သင်္ကေတဆိုင်ရာ ဂုဏ်သတ္တိများ)
----------------------------------------------------

Point cloud များပုံဖော်ပြသခြင်းအတွက် setting များကို |symbology| :guilabel:`Symbology` tab တွင် လုပ်ဆောင်ပါသည်။ အပေါ်ပိုင်းတွင် feature အမျိုးမျိုး ပုံဖော်ပြသပေးသည့်အရာ (renderer) များ၏ setting များကို တွေ့နိုင်ပါသည်။ အောက်ပိုင်းတွင် layer တစ်ခုလုံးအတွက် အထွေထွေ setting များကို ဆောင်ရွက်နိုင်ပြီး feature renderer များအတွက် အသုံးချနိုင်သော section များရှိပါသည်။

.. _point_clouds_rendering_types:

Feature Rendering types (Feature ပုံဖော်ပြသခြင်း အမျိုးအစားများ)
.................................................................

:guilabel:`Symbology` tab ၏ ထိပ်တွင်ရှိသော drop-down menu ကိုအသုံးပြုပြီး point cloud များ ပုံဖော်ပြသခြင်းအမျိုးမျိုးကို ရွေးချယ်အသုံးပြုနိုင်ပါသည်။ (:numref:`figure_point_cloud_symbology_overview` တွင်ကြည့်ရှုပါ)

* |pointCloudExtent| :guilabel:`Extent Only` - Data extent ၏ bounding box (စတုဂံပုံအကျယ်အဝန်းနယ်) ကိုသာ ပြသပေးပါသည်၊ data extent ကို ခြုံငုံကြည့်ရှုသောအခါ လွယ်ကူစေပါသည်။ :guilabel:`Symbol` :ref:`widget <symbol_widget_selector>` ဖြင့် box အတွက် property များ (အရောင်၊ လိုင်းစုတ်ချက် (stroke)၊ အလင်းပိတ်နှုန်း၊ layer အခွဲများ၊....) ကို စိတ်ကြိုက်ပြင်ဆင်နိုင်ပါသည်။
* |singlebandPseudocolor| :guilabel:`Attribute by Ramp` - Color gradient (ရောင်ပြေး) တစ်ခုပေါ်တွင် data ကို ရေးဆွဲပါသည်။ :ref:`point_cloud_ramp` တွင်ကြည့်ရှုပါ။
* |multibandColor| :guilabel:`RGB` - အနီ၊ အစိမ်း၊ အပြာ အရောင်တန်ဖိုးများကို အသုံးပြုပြီး data ကို ရေးဆွဲပါသည်။ :ref:`point_cloud_rgb` တွင်ကြည့်ရှုပါ။
* |paletted| :guilabel:`Classification` - အတန်းအစားအမျိုးမျိုး အတွက် အရောင်အမျိုးမျိုးကို အသုံးပြုပြီး data ကိုရေးဆွဲပါသည်။ :ref:`point_cloud_classification` တွင်ကြည့်ရှုပါ။

Point cloud တစ်ခုကို QGIS အတွင်းထည့်လိုက်သောအခါ အကောင်းဆုံး renderer ကို ရွေးချယ်ရန် အောက်ပါ နည်းလမ်းအတိုင်း လုပ်ဆောင်ပါသည်- 

* Dataset သည် အရောင်သတင်းအချက်အလက် (အနီ၊ အစိမ်း၊ အပြာ) များပါလျှင် RGB renderer ကိုအသုံးပြုမည်ဖြစ်သည်။
* ``အတန်းအစားခွဲထားသော Classification`` သတင်းအချက်အလက်များပါလျှင် classified renderer ကိုအသုံးပြုမည်ဖြစ်သည်။
* အထက်တွင်ဖော်ပြခဲ့သော သတင်းအချက်အလက် နှစ်မျိုးလုံးမပါခဲ့လျှင် အမြင့် Z အချက်အလက် (attribute) ပေါ် မူတည်သည့် rendering ကိုအသုံးပြုမည်ဖြစ်သည်။

Point cloud ရဲ့အချက်အလက်များကိုမသိလျှင် point cloud ထဲတွင် မည်သည့်အချက်အလက်များပါဝင်သလဲ နှင့် မည်သည့် အပိုင်းအခြားအတွင်း တန်ဖိုးများတည်ရှိသလဲ ဆိုသည်ကို ခြုံငုံကြည့်ရှုနိုင်ရန် |basicStatistics| :guilabel:`Statistics` :ref:`tab <point_clouds_statistics>` တွင် ဖော်ပြပေးပါသည်။

.. _figure_point_cloud_symbology_overview:

.. figure:: img/point_cloud_symbology_overview.png
   :align: center

   Point cloud သင်္ကေတဆိုင်ရာ tab


.. _point_cloud_ramp:

Attribute by Ramp Renderer (အရောင်စဉ်ဖြင့် ပုံဖော်ပြသပေးသည့်အရာ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

|singlebandPseudocolor| :guilabel:`Attribute by Ramp` ကိုအသုံးပြုပြီး color gradient (ရောင်ပြေး) တစ်ခုပေါ်တွင် ဂဏန်းတန်ဖိုးများဖြင့် data များကို ကြည့်ရှုနိုင်ပါသည်။ ဥပမာ- ထိုကဲ့သို့ ကိန်းဂဏန်းတန်ဖိုးများသည် ရှိနေပြီးသား ပြင်းအားအချက်အလက် သို့မဟုတ် အမြင့် Z တန်ဖိုး ဖြစ်နိုင်ပါသည်။ အနည်းဆုံးနှင့် အများဆုံးတန်ဖိုး တစ်ခုစီပေါ်မူတည်ပြီး အခြားတန်ဖိုးများကို ရောင်ပြေးတစ်ခုထဲတွင် အလိုလျောက်ဖြန့်ပြီးအသုံးပြုပါသည်။ ထင်ရှားသောတန်ဖိုးများနှင့် ၎င်းတန်ဖိုးများကို အရောင်တစ်ခုချင်းစီ သတ်မှတ်ခြင်းကို "အရောင်မြေပုံ (color map)" ဟုခေါ်ပြီး ဇယားထဲတွင် ကြည့်ရှုနိုင်ပါသည်။ အောက်ဖော်ပြပါ figure တွင် ဖော်ပြထားသည့်အတိုင်း setting နှင့်ပတ်သက်သော ရွေးချယ်စရာများစွာရှိပါသည်။

.. _figure_point_cloud_attribute_by_ramp:

.. figure:: img/point_cloud_attribute_by_ramp.png
   :align: center

   Point cloud သင်္ကေတဆိုင်ရာ tab- Attribute by Ramp

* :guilabel:`Min (အနည်းဆုံး)` နှင့် :guilabel:`Max (အများဆုံး)` သည် color map တွင် အသုံးပြုမည့် အပိုင်းအခြားကို သတ်မှတ်ပေးပါသည်။ ဘယ်ဘက်သည် :guilabel:`Min (အနည်းဆုံး)` တန်ဖိုးကို ကိုယ်စားပြုပြီး ညာဘက်သည် :guilabel:`Max (အများဆုံး)` ကိုကိုယ်စားပြုပါသည်။ ၎င်းတန်ဖိုးများကိုအခြေခံပြီး ကြားတန်ဖိုးများကို အလိုအလျှောက်တွက်ထုတ်ပေးပါသည်။ ပုံမှန်အားဖြင့် QGIS သည် ရွေးချယ်ထားသော အချက်အလက်များမှ အနည်းဆုံးနှင့် အများဆုံးတန်ဖိုးများကိုရှာဖွေပါသည်၊ သို့သော် ၎င်းတန်ဖိုးများကို ပြုပြင်ပြောင်းလဲနိုင်ပါသည်။ တန်ဖိုးများ ပြောင်းပြီးသည်နှင့် မူရင်းတန်ဖိုးကို ပြန်လိုအပ်လျှင် :guilabel:`Load` ခလုတ်ကို နှိပ်ပြီး လုပ်ဆောင်နိုင်ပါသည်။
* :guilabel:`Interpolation` (သိရှိပြီးသားအချက်အလက်ကိုအခြေခံ၍ မသိသေးသည့်အရာများအတွက် ဖြည့်သွင်းတွက်ချက်ခြင်း) သည် တန်ဖိုးများကို မည်သို့အရောင်သတ်မှတ်မည်ဆိုသည်ကို ဆုံးဖြတ်ပါသည်- 

  * :guilabel:`Discrete` (ပြတ်ကိန်း) (:guilabel:`Value` column ရဲ့ခေါင်းစည်းတွင် ``<=`` သင်္ကေတတစ်ခု ပေါ်နေမည်) - အသုံးပြုမည့်အရောင်ကို အနီးဆုံး color map မှ တူညီသော သို့မဟုတ် ပိုများသောတန်ဖိုးကိုအသုံးပြုပါသည်။ 
  * :guilabel:`Linear` (အစဉ်အတိုင်း) - အသုံးပြုမည့်အရောင်ကို color map မှ Pixel တန်ဖိုး၏ အထက် သို့မဟုတ် အောက်ရောက်နေသောတန်ဖိုးများမှ linear အတိုင်းတွက်ထုတ်ပါသည်။ Dataset တန်ဖိုးတစ်ခုချင်းစီသည် မတူညီသောအရောင်တစ်ခုစီရှိသည်ကို ဆိုလိုပါသည်။
  * :guilabel:`Exact` (:guilabel:`Value` column ၏ခေါင်းစည်းတွင် ``<=`` သင်္ကေတတစ်ခုပေါ်နေမည်) - Color map နှင့်တူညီသောတန်ဖိုးရှိသည့် pixel များကိုသာ အရောင်သတ်မှတ်မည်ဖြစ်ပြီး တခြား pixel များကို အရောင်ပြသမည်မဟုတ်ပါ။	
* Dataset တွင်အသုံးပြုမည့် color ramp (ရောင်စဉ်တန်း) ရွေးချယ်ရန်အတွက် :guilabel:`Color ramp` widget ကိုအသုံးပြုနိုင်ပါသည်။ :ref:`Color ramp widget <color_ramp_widget>` ဖြင့် အသစ်တစ်ခုကို ဖန်တီးနိုင်သလို လက်ရှိရွေးချယ်ထားသောအရာကို ပြုပြင်ခြင်း သို့မဟုတ် သိမ်းဆည်းခြင်း ပြုလုပ်နိုင်ပါသည်။
* :guilabel:`Label unit suffix` (အညွှန်းယူနစ် နောက်ဆက်စာလုံး) - ရည်ညွှန်းချက်ထဲရှိ တန်ဖိုး၏နောက်တွင် အညွှန်းတစ်ခုထည့်ပေါင်းပေးပြီး :guilabel:`Label precision` သည် ဖော်ပြပေးမည့် ဒဿမ အရေအတွက်ကိုထိန်းချုပ်ပါသည်။

Classification (အတန်းအစားခွဲခြားခြင်း) :guilabel:`Mode` သည် အတန်းအစားအလိုက် တန်ဖိုးများ မည်သို့ ခွဲဝေချထားမည်ကို သတ်မှတ်ပါသည်-

* :guilabel:`Continuous` (တစ်ဆက်တစပ်တည်း)- အတန်းအစားအရေအတွက်နှင့် အရောင်များကို color ramp stops (အရောင်အပိုင်းအခြားအဖြတ်) များမှ တွက်ထုတ်ပါသည်။ Color ramp ထဲရှိ stop များပြန့်နှံမှုအလိုက် ကန့်သတ်တန်ဖိုးများကို သတ်မှတ်ပါသည်။ (Stop များအကြောင်း ပိုမိုသိရှိလိုလျှင် :ref:`color-ramp` တွင်ကြည့်ရှုပါ)
* :guilabel:`Equal interval` (တူညီ ကြားအကွာ) - အတန်းအစား၏အရေအတွက်များကို မျဉ်း၏အဆုံးတွင် :guilabel:`Classes` field ဖြင့်သတ်မှတ်ပါသည်။ အတန်းအစားများအားလုံး တူညီသည့်ပမာဏရှိစေရန် ကန့်သတ်တန်ဖိုးများကို သတ်မှတ်ပါသည်။

အတန်းအစားများကို အလိုအလျှောက်ဆုံးဖြတ်ပြီး color map ဇယားတွင်ပြသပေးပါသည်။ သို့သော် ၎င်းအတန်းအစားများကို စိတ်ကြိုက်ပြင်ဆင်နိုင်ပါသည်- 

* ဇယားထဲရှိ :guilabel:`Value (တန်ဖိုး)` တစ်ခုကို double-click နှိပ်ပြီး အတန်းအစားတန်ဖိုးကို ပြင်ဆင်နိုင်ပါသည်။ 
* ထိုတန်ဖိုးအတွက် အသုံးပြုမည့် အရောင်တစ်ခုကိုရွေးချယ်နိုင်သည့် :ref:`color-selector` widget ကိုဖွင့်ရန် :guilabel:`Color` column ထဲတွင် double click နှိပ်ပါ။ 
* အတန်းအစား၏ အညွှန်းကို ပြင်ဆင်ရန် :guilabel:`Label` column ထဲတွင် double click နှိပ်ပါ။
* Color table ထဲရှိ ရွေးချယ်ထားသော row (အတန်း)များပေါ်တွင် right-click နှိပ်ခြင်းသည် ရွေးချယ်ထားသည့်အရာများကို :guilabel:`Change Color (အရောင်ပြောင်းရန်)` နှင့် :guilabel:`Change Opacity (အလင်းပိတ်နှုန်းပြောင်းရန်)` menu တစ်ခုကို ပြသမည်ဖြစ်သည်။ 


ဇယား၏အောက်တွင် :guilabel:`Classify` ကိုနှိပ်ကာ မူရင်းအတန်းအစားများအဖြစ်ပြန်လည်ရယူနိုင်ပြီး တန်ဖိုးများ စိတ်ကြိုက် |symbologyAdd| :sup:`Add` (ပေါင်းထည့်) နိုင်သလို ဇယားမှရွေးချယ်ထားသောတန်ဖိုးများကို |symbologyRemove| :sup:`Delete` (ဖျက်ပစ်) နိုင်ပါသည်။

စိတ်ကြိုက် color map တစ်ခုဖန်တီးခြင်းသည် အလွန်ရှုပ်ထွေးနိုင်သောကြောင့် ရှိနေပြီးသား color map ကို ခေါ်ယူအသုံးပြုနိုင်ရန် |fileOpen| :sup:`Load` ကို နှိပ်ခြင်း သို့မဟုတ် အခြား layer များအတွက် အသုံးပြုနိုင်ရန် |fileSaveAs| :sup:`Save` ကို နှိပ်ပြီး သိမ်းဆည်းထားခြင်း (:file:`txt` file တစ်ခုအဖြစ်) များ ပြုလုပ်နိုင်ပါသည်။

:guilabel:`Interpolation` အတွက် :guilabel:`Linear` ကိုရွေးချယ်ထားလျှင် အောက်ပါပြင်ဆင်သတ်မှတ်ခြင်းများလည်း လုပ်‌ဆောင်နိုင်ပါသည်- 

* |checkbox| :guilabel:`Clip out of range values` (အပိုင်းအခြား အပြင်ဘက်ရောက်နေသောတန်ဖိုးများကို ဖြတ်ထုတ်ခြင်း) - ပုံမှန်အားဖြင့် linear နည်းလမ်းသည် :guilabel:`Min (အနည်းဆုံး)` တန်ဖိုးအောက်ရောက်နေသော တန်ဖိုးများကို ပထမဆုံး အတန်းအစားအဖြစ် သတ်မှတ်ပေးပြီး :guilabel:`Max (အများဆုံး)` တန်ဖိုးထက်ကျော်နေသော တန်ဖိုးများကို အများဆုံးအဖြစ် အသီးသီးသတ်မှတ်ပါသည်။ ၎င်းတန်ဖိုးများကို ပုံဖော်မပြသလိုလျှင် ဤ setting ကို အမှန်ခြစ်ထားပါ။
* :guilabel:`Legend settings` (ရည်ညွှန်းချက်အပြင်အဆင်) သည် :guilabel:`Layers` panel နှင့် :ref:`layout legend <layout_legend_item>` ထဲတွင် ပြသရန်ဖြစ်သည်။ Raster ရည်ညွှန်းချက်စိတ်ကြိုက်ပြင်ဆင်ခြင်းနှင့် အတူတူပင်ဖြစ်သည်။ (အသေးစိတ်ကို :ref:`raster_legend_settings` တွင် ရှာဖွေပါ) 


.. _point_cloud_rgb:

RGB Renderer (RGB ဖြင့် ပုံဖော်ပြသသည့်အရာ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

|multibandColor| :guilabel:`RGB` renderer ဖြင့် point cloud မှ ရွေးချယ်ထားသော attribute သုံးမျိုးကို အနီ၊ အစိမ်း၊ အပြာ အစိတ်အပိုင်းများအဖြစ်အသုံးပြုပါသည်။ Attribute များကို လိုက်လျောညီထွေ အမည်ပေးထားပါက QGIS သည် ၎င်းတို့ကို အလိုအလျောက်ရွေးချယ်ပြီး band တစ်ခုချင်းစီအတွက် :guilabel:`Min (အနည်းဆုံး)` နှင့် :guilabel:`Max (အများဆုံး)` တန်ဖိုးများကို တွက်ထုတ်ပြီး လိုက်လျောညီထွေဖြစ်အောင် အရောင်သတ်မှတ်ပေးပါသည်။ သို့သော် တန်ဖိုးများကို စိတ်ကြိုက်ပြင်ဆင်လို့လည်း ရပါသည်။

:guilabel:`Contrast enhancement (အရောင်ကွဲပြားထင်ရှားမှု မြှင့်တင်ခြင်း)` နည်းလမ်းကိုလည်း အသုံးပြုနိုင်ပါသည် - :guilabel:`No Enhancement (ဘာမှမပြင်ခြင်း)`၊ :guilabel:`Stretch to MinMax (အနည်းဆုံး၊ အများဆုံးတန်ဖိုးများထိ ဆွဲဆန့်ခြင်း)`၊ :guilabel:`Stretch and Clip to MinMax (အနည်းဆုံး၊ အများဆုံးတန်ဖိုးများထိ ဆွဲဆန့်ပြီး အစွန်းထွက်များကိုဖယ်ထုတ်ခြင်း)` နှင့် :guilabel:`Clip to MinMax (အနည်းဆုံး၊ အများဆုံးတန်ဖိုးများကို ဖြတ်ယူခြင်း)`


.. note:: :guilabel:`Contrast enhancement` tool သည် ပြင်ဆင်ဖန်တီးနေဆဲ ဖြစ်ပါသည်။ ၎င်းကို အသုံးပြုရာတွင် ပြဿနာရှိပါက မူရင်း setting ဖြစ်သော :guilabel:`Stretch to MinMax` ကိုအသုံးပြုပါ။

.. _figure_point_cloud_rgb:

.. figure:: img/point_cloud_rgb.png
   :align: center

   Point cloud များကို RGB ဖြင့် ပုံဖော်ပြသသည့်အရာ


.. _point_cloud_classification:

Classification Renderer (အတန်းအစားခွဲခြားခြင်းအတွက် ပုံဖော်ပြသပေးသည့်အရာ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

|paletted| :guilabel:`Classification` rendering ထဲတွင် အချက်အလက်တစ်ခုချင်းအရ point cloud ကို အရောင်များခွဲခြားပြသပါသည်။ မည်သည့် အချက်အလက်မျိုးမဆို အသုံးပြုနိုင်ပါသည် (ကိန်းဂဏန်း၊ စာသား၊ စသဖြင့်)။ Point cloud data များထဲတွင် များသောအားဖြင့် ``Classification`` လို့ခေါ်သော field တစ်ခုပါဝင်ပါသည်။ ၎င်းတွင် Post-processing နည်းဖြင့် အလိုအလျောက်ဆုံးဖြတ်ထားသော အချက်အလက်များပါဝင်လေ့ရှိပါသည် (ဥပမာ- အပင်ဖုံးလွှမ်းမှုများအကြောင်း)။ :guilabel:`Attribute (အချက်အလက်ဇယား)` တွင် classification အတွက် အသုံးပြုမည့် field ကိုရွေးချယ်နိုင်ပါသည်။ ပုံမှန်အားဖြင့် QGIS သည် LAS specification ၏ သတ်မှတ်ချက်များကို အသုံးပြုပါသည်။ (`ASPRS home page <https://www.asprs.org/divisions-committees/lidar-division/laser-las-file-format-exchange-activities>`_ တွင် တင်ထားသော PDF ထဲရှိ 'ASPRS Standard Point Classes' ဇယားကိုကြည့်ရှုပါ။) သို့သော် data များသည် ဒီပုံဖော်ထားမှုကနေ သွေဖယ်သွားနိုင်ပါသည်။ သံသယရှိလျှင် သတ်မှတ်ချက်များကို ဖန်တီးခဲ့သောသူ သို့မဟုတ် အဖွဲ့အစည်းကို ဆက်သွယ်မေးမြန်းရန် လိုအပ်ပါသည်။

.. _figure_point_cloud_classification:

.. figure:: img/point_cloud_classification.png
   :align: center

   Point cloud အတန်းအစားခွဲခြားခြင်းအတွက် ပုံဖော်ပြသပေးသည့်အရာ

ဇယားထဲတွင် အသုံးပြုထားသော တန်ဖိုးများအားလုံးကို သက်ဆိုင်ရာအရောင်နှင့် ရည်ညွှန်းချက်ဖြင့် ပြသပါသည်။ Row တစ်ခုချင်းစီရဲ့အစတွင် |checkbox| check box တစ်ခုစီရှိပါသည်။ အမှန်ခြစ် ဖြုတ်ထားလျှင် ၎င်းတန်ဖိုးကို မြေပုံတွင်ဖော်ပြပေးမည်မဟုတ်ပါ။ ဇယားထဲတွင် double click နှိပ်ပြီး :guilabel:`Color (အရောင်)`၊ :guilabel:`Value (တန်ဖိုး)` နှင့် :guilabel:`Legend (ရည်ညွှန်းချက်)` များကိုပြင်ဆင်နိုင်ပါသည် (အရောင်အတွက် :ref:`color-selector` widget ပွင့်လာမည်ဖြစ်သည်)

ဇယား၏အောက်တွင် QGIS မှ ဖန်တီးထားသော မူရင်း class များကို ပြောင်းလဲနိုင်သော ခလုတ်များရှိပါသည်-

* :guilabel:`Classify` ခလုတ်ကိုအသုံးပြုပြီး data များကို အလိုလျောက် အတန်းအစားခွဲခြားနိင်ပါသည်။ Attribute ထဲတွင် ပါဝင်ပြီး ဇယားထဲတွင်မတွေ့ရသေးသော တန်ဖိုးများအားလုံးကို ပေါင်းထည့်မည်ဖြစ်သည်။
* |symbologyAdd| :sup:`Add` နှင့် |symbologyRemove| :sup:`Delete` ခလုတ်များကို အသုံးပြုပြီး တန်ဖိုးများ ထည့်ခြင်း နှင့် ဖယ်ထုတ်ခြင်း ကို စိတ်ကြိုက်ပြုလုပ်နိုင်ပါသည်။
* ဇယားထဲမှ တန်ဖိုးများအားလုံးကို ဖယ်ထုတ်လိုလျှင် :guilabel:`Delete All` ကိုနှိပ်ပါ။

.. hint::

   :guilabel:`Layers` panel ထဲတွင် layer ၏ class leaf entry ပေါ် right-click နှိပ်ပြီး သက်ဆိုင်ရာ feature များ၏ မြင်ရနိုင်စွမ်းကို အမြန်သတ်မှတ်ပြင်ဆင်နိုင်ပါသည်။

Point Symbol (အမှတ်သင်္ကေတ)
............................

:guilabel:`Point Symbol` ၏ အောက်တွင် ပြသမည့် data point တစ်ခုချင်းဆီ၏ အရွယ်အစားနှင့် ယူနစ် (ဥပမာ မီလီမီတာ၊ pixels၊ လက်မ) တို့ကိုသတ်မှတ်ပေးနိုင်ပါသည်။ အမှတ်များအတွက် style ကို :guilabel:`Circle (စက်ဝိုင်း)` သို့မဟုတ် :guilabel:`Square (စတုရန်း)` ကိုရွေးချယ်အသုံးပြုနိုင်ပါသည်။

Layer Rendering (Layer ပုံဖော်ပြသခြင်း)
........................................

:guilabel:`Layer Rendering` section ထဲတွင် layer အတွက် ပုံဖော်ပြသခြင်း လုပ်ဆောင်နိုင်ရန် အောက်ပါ ပြုပြင်မွမ်းမံခြင်းများလုပ်ဆောင်နိုင်ပါသည်- 

.. _point_cloud_draw_order:

* :guilabel:`Draw order` - 2D map canvas ပေါ်ရှိ point cloud ပုံဖော်ပြသခြင်း အစီအစဉ် (order) သည် ၎င်းတို့ရဲ့ အမြင့် Z တန်ဖိုးပေါ်မူတည်/မမူတည် ဆိုသည်ကို ထိန်းချုပ်နိင်ပါသည်။ အောက်ပါတို့ဖြင့် ပုံဖော်ပြသနိုင်သည်-

  * Layer ထဲတွင် point များကို သိမ်းဆည်းထားသော :guilabel:`Default (မူရင်း)` order (အစီအစဉ်) ဖြင့်၊
  * :guilabel:`Bottom to top (အောက်ခြေမှ ထိပ်သို့)` (အမြင့် Z တန်ဖိုး ပိုများသော point များသည် နိမ့်နေသည့် point များကို ဖုံးပစ်လိုက်ပြီး ortho photo အစစ်နှင့်တူအောင် ဖန်တီးပေးပါသည်)၊
  * သို့မဟုတ် :guilabel:`ထိပ်မှ အောက်ခြေသို့` ကိုအသုံးပြုလျှင် အောက်ခြေမှ မော့ကြည့်ရသည့်ပုံစံမျိုး မြင်ရမည်ဖြစ်ပါသည်။

.. _`point_clouds_symbology_maxerror`:

* :guilabel:`Maximum error (အများဆုံးအမှား)` - များသောအားဖြင့် point cloud များသည် ပြသရန် လိုအပ်သည့် point အရေအတွက်ထက် ပိုမိုပြီး ပါရှိပါသည်။ ယခုနည်းလမ်းကိုအသုံးပြုပြီး ဘယ်လောက်ထိ သိပ်သိပ်သည်းသည်း သို့မဟုတ် ခပ်ကျဲကျဲ ပြသမည်ဆိုသည်ကို သတ်မှတ်ပေးနိုင်ပါသည် (point များကြား အများဆုံးခွင့်ပြုသော နေရာလွတ် 'maximum allowed gap between points' အဖြစ်နားလည်ထားပါ)။ ဂဏန်းတန်ဖိုးကြီးကြီးတစ်ခု (ဥပမာ  5 mm) အဖြစ်သတ်မှတ်လျှင် point များကြားတွင် သိသာ၊ မြင်သာသော နေရာလွတ်များရှိနေမှာဖြစ်ပါသည်။ ဂဏန်းတန်ဖိုးသေးတာ (ဥပမာ 0.1 mm) ကိုအသုံးပြုလျှင် မလိုအပ်သည့် point များကိုပါ ပုံဖော်ပြသရာတွင်အသုံးပြုသောကြောင့် rendering ကို နှေးသွားစေပါသည် (အခြား ယူနစ်များကို ရွေးချယ်နိုင်ပါသည်)။

* :guilabel:`Opacity (အလင်းပိတ်နှုန်း)` - Map canvas ထဲရှိ အောက်တွင်ရှိနေသော layer ကို မြင်ရစေရန် ဒီ tool ကို အသုံးပြုနိုင်ပါသည်။ မိမိကြည့်လိုသော မြင်ရနိုင်မှု အတိုင်းအတာအထိ slider ကို ရွှေ့ကြည့်ပါ။ မြင်ရနိုင်စွမ်း ရာခိုင်နှုန်းအတိအကျ သတ်မှတ်ပေးလိုလျှင် slider ၏ဘေးရှိ menu တွင် သတ်မှတ်ပေးနိုင်ပါသည်။ 

* :guilabel:`Blending mode` (ရောစပ်ခြင်း) - ဒီ tool ကိုအသုံးပြုပြီး အထူး rendering effect များကိုလုပ်ဆောင်နိုင်ပါသည်။ အထက်နှင့်အောက် ထပ်နေသော layer များ၏ pixel များကို :ref:`blend-modes` တွင်ဖော်ပြထားသော setting များဖြင့် ရောစပ်လိုက်ပါသည်။

* :guilabel:`Eye dome lighting` - အနက် (အနိမ့်အမြင့်) rendering ပိုကောင်းစေရန်အတွက် map canvas တွင် အရိပ် effect များကို ဖန်တီးနိုင်ပါသည်။ :ref:`draw order <point_cloud_draw_order>` property ပေါ်မူတည်ပြီး rendering အရည်အသွေး ကွာခြားပါသည်။ :guilabel:`Default` draw order (ပုံမှန်ရေးဆွဲခြင်းအစီအစဉ်) သည် အကောင်းဆုံးမဟုတ်တောင်မှ အတန်အသင့်ကောင်းသော ရလာဒ်ကို ဖန်တီးပေးနိုင်ပါသည်။ အောက်ပါ parameter များကို ထိန်းချုပ်နိုင်ပါသည်-

  * :guilabel:`Strength` - အလင်းအမှောင်ကွဲပြားခြားနားမှုကို မြှင့်တင်ပေးခြင်းဖြင့် အနက် (အနိမ့်အမြင့်) အသွင်အပြင်ပိုကောင်းစေပါသည်။
  * :guilabel:`Distance` - အသုံးပြုသော piexel များ၏ ဗဟိုမှအကွာအဝေးကို ကိုယ်စားပြုပြီး edge (အစွန်း) ကို ပိုထူအောင်လုပ်ဆောင်ပေးပါသည်။


.. _point_clouds_3d:

3D View Properties (၃ ဖက်မြင် ဂုဏ်သတ္တိများ)
---------------------------------------------

|3d| :guilabel:`3D View` tab ထဲတွင် 3D map များထဲတွင် point cloud ကို rendering လုပ်ခြင်းအတွက် setting များကို လုပ်ဆောင်နိုင်ပါသည်။

3D Rendering modes (၃ ဖက်မြင် ပုံဖော်ပြသခြင်း နည်းလမ်းများ)
............................................................

Tab ၏ ထိပ်တွင်ရှိသာ drop down menu မှ အောက်ပါနည်းလမ်းများကိုရွေးချယ်အသုံးပြုနိုင်ပါသည်-  

* :guilabel:`No Rendering` - Data များကို ပြသပေးမည်မဟုတ်ပါ။
* :guilabel:`Follow 2D Symbology` - :ref:`2D တွင်အသုံးပြုထားသော symbology <point_clouds_rendering_types>` ဖြင့် 3D တွင် feature များ ပုံဖော်ပြခြင်းကို အလိုအလျှောက်လုပ်ဆောင်မည်ဖြစ်သည်။
* |singleColor| :guilabel:`Single Color` - မည့်သည့် attribute များကိုမှ ထည့်မစဉ်းစားပဲ point အားလုံးကို :ref:`အရောင် <color-selector>` တစ်မျိုးတည်းအဖြစ်ပြသပေးပါသည်။
* |singlebandPseudocolor| :guilabel:`Attribute by Ramp` - Color ramp တစ်ခုပေါ်တွင် ပေးထားသော attribute ကို interpolate ပြုလုပ်ပေးပြီး feature များကို ကိုက်ညီသောအရောင်များဖြင့် သတ်မှတ်ပေးပါသည်။ :ref:`point_cloud_ramp` တွင်ကြည့်ရှုပါ။
* |multibandColor| :guilabel:`RGB` - Feature များတွင်ပါသော attribute အမျိုးမျိုးကိုအသုံးပြုပြီး အနီ၊ အစိမ်း၊ အပြာရောင်တို့ကိုသတ်မှတ်ပါသည်။ :ref:`point_cloud_rgb` တွင်ကြည့်ရှုပါ။
* |paletted| :guilabel:`Classification` - Attribute တစ်မျိုးချင်းစီအလိုက် point များကိုအရောင်တစ်မျိုးစီ သတ်မှတ်ပေးပါသည်။ :ref:`point_cloud_classification` တွင်ကြည့်ရှုပါ။

.. _figure_point_cloud_3d_view:

.. figure:: img/point_cloud_3d_view.png
   :align: center

   Classification renderer ဖြင့် point cloud 3D view tab

3D Point Symbol (၃ ဖက်မြင် အမှတ်သင်္ကေတ)
.........................................

|3d| :guilabel:`3D View` tab ၏ အောက်ပိုင်းတွင် :guilabel:`Point Symbol` section ကိုတွေ့နိုင်ပါသည်။
ဤတွင် layer တစ်ခုလုံးအတွက် renderer များအားလုံးတွင်အတူတူဖြစ်သော အထွေထွေ setting များကို လုပ်ဆောင်နိုင်ပါသည်။ အောက်ဖော်ပြပါ ရွေးချယ်စရာများရှိပါသည်-

* :guilabel:`Point size` (Point အရွယ်အစား) - Data point တစ်ခုချင်းစီအတွက် ပြသပေးသော အရွယ်အစား (pixel အားဖြင့်) ကိုသတ်မှတ်ပေးနိုင်ပါသည်။
* :guilabel:`Maximum screen space error` - ဒီနည်းလမ်းကိုအသုံးပြုပြီး point cloud များကို (pixel အားဖြင့်) မည်မျှ သိပ်သိပ်သည်းသည်း သို့မဟုတ် ခပ်ကျဲကျဲ ပြသမည်ဆိုသည်ကို သတ်မှတ်နိုင်ပါသည်။ တန်ဖိုးကြီးကြီးတစ်ခု (ဥပမာ 10) အဖြစ်သတ်မှတ်လျှင် point များအကြားတွင် သိသာ၊ မြင်သာသည့် နေရာလွတ်များရှိနေမည်ဖြစ်ပါသည်၊ တန်ဖိုးအသေး (ဥပမာ 0) ကိုအသုံးပြုလျှင် မလိုအပ်သည့် point များကိုပါ ပုံဖော်ပြသရာတွင်အသုံးပြုသောကြောင့် rendering ကို နှေးသွားစေပါသည်(:guilabel:`Symbology` :ref:`Maximum error <point_clouds_symbology_maxerror>` တွင်အသေးစိတ်ကြည့်ရှုနိုင်ပါသည်။)
* :guilabel:`Point budget` - အချိန်အကြာကြီး rendering လုပ်ခြင်းကိုရှောင်ရှားရန်အတွက် rendering လုပ်ဆောင်မည့် အများဆုံး point အရေအတွက်ကိုသတ်မှတ်ပေးနိုင်ပါသည်။
* Triangulation တွက်ချက်ခြင်းနည်းလမ်းဖြင့် ရလာသော မျက်နှာပြင်အပြည့်တစ်ခုဖြင့် 3D view တွင် point cloud layer ကို render လုပ်ရန်အတွက် |checkbox| :guilabel:`Render as surface (Triangulate)` ကို အမှန်ခြစ်ထားပါ။ တွက်ချက်ထားသော triangle (တြိဂံများ) များ၏ dimension (ရှုထောင့်)ကို ထိန်းချုပ်နိုင်ပါသည်-

  * |checkbox| :guilabel:`Skip triangles longer than` (ကန့်သတ်တန်ဖိုးထက် ပိုရှည်နေသော တြိဂံများကို ကျော်ပစ်ခြင်း) ကို အမှန်ခြစ် ခြစ်ထားပြီး တြိဂံများ၏ အနားတစ်ဖက်အတွက် အရှည်ဆုံးအလျားကိုရေပြင်ညီအတိုင်းသတ်မှတ်ပါသည်။ 
  * |checkbox| :guilabel:`Skip triangles taller than` (ကန့်သတ်တန်ဖိုးထက် အထက်အောက်ပိုရှည်နေသော တြိဂံများကို ကျော်ပစ်ခြင်း) ကို အမှန်ခြစ် ခြစ်ထားပြီး တြိဂံများ၏ အနားတစ်ဖက်အတွက် အမြင့်ဆုံးအလျားကို ဒေါင်လိုက်အတိုင်းသတ်မှတ်ပါသည်။
* |checkbox| :guilabel:`Show bounding boxes` ကို အမှန်ခြစ် ခြစ်ထားလျှင် debugging (အမှားပြင်ခြင်း) အတွက်အထူးအသုံးဝင်ပြီး hierarchy ထဲရှိ node များ၏ bounding box (စတုဂံပုံအကျယ်အဝန်းနယ်) များကိုပြသပေးပါသည်။


.. _point_clouds_rendering:

Rendering Properties (ပုံဖော်ပြသခြင်းဆိုင်ရာ ဂုဏ်သတ္တိများ)
------------------------------------------------------------

:guilabel:`Scale dependent visibility` (စကေးပေါ်မူတည်သော မြင်ရနိုင်စွမ်း) အုပ်စုအောက်တွင် :guilabel:`Maximum (inclusive)` (အများဆုံး (သူ့အောက်ရှိတန်ဖိုးများပါဝင်)) နှင့် :guilabel:`Minimum (exclusive) (အနည်းဆုံး (သူ့အောက်ရှိတန်ဖိုးများ မပါဝင်))` စကေးများသတ်မှတ်ပေးနိုင်ပြီး မည်သည့် စကေးအပိုင်းအခြားအတွင်းတွင် feature များကို မြင်ရနိုင်မည်ဆိုသည်ကို သတ်မှတ်ပေးနိုင်ပါသည်။ |mapIdentification| :sup:`Set to current canvas scale` ခလုတ်ကိုနှိပ်ပြီး လက်ရှိမြေပုံစကေးကို မြင်ရနိုင်သည့်အပိုင်းအခြားနယ်နိမိတ် စကေးအဖြစ် သတ်မှတ်ပေးနိုင်ပါသည်။ :ref:`label_scaledepend` တွင် ပိုမိုလေ့လာပါ။ 
   
.. note::

   :guilabel:`Layers` panel ထဲမှ layer ပေါ်ကို right-click နှိပ်ပြီး ပေါ်လာသော menu မှ :guilabel:`Set Layer Scale Visibility` ကိုရွေးချယ်ပြီးလည်း စကေးပေါ်မူတည်သောမြင်နိုင်စွမ်းကိုသတ်မှတ်ပေးနိုင်ပါသည်။

.. _figure_point_cloud_rendering:

.. figure:: img/point_cloud_rendering.png
   :align: center

   Point cloud ပုံဖော်ပြသခြင်းဆိုင်ရာ tab


.. _point_clouds_elevation:

Elevation Properties (မြေပြင်အမြင့်ဆိုင်ရာ ဂုဏ်သတ္တိများ)
----------------------------------------------------------

|elevationscale| :guilabel:`Elevation` tab တွင် data များ၏ အမြင့် Z တန်ဖိုး အတွက် အမှားပြင်ဆင်ခြင်းများကို သတ်မှတ်နိုင်ပါသည်။ 3D မြေပုံများတွင် data ၏ elevation ကို ချိန်ညှိရန်နှင့် :ref:`profile tool charts <label_elevation_profile_view>` ထဲရှိ အသွင်အပြင်ကို ချိန်ညှိရန်အတွက် ၎င်းကိုလိုအပ်နိုင်ပါသည်။ အောက်ပါနည်းလမ်းများကို အသုံးပြုပြီးလုပ်ဆောင်နိုင်ပါသည်- 

* :guilabel:`Elevation` group အောက်တွင် - 

  * :guilabel:`Scale` တစ်ခုသတ်မှတ်နိုင်ပါသည် - ``10`` လို့သတ်မှတ်လျှင် အမြင့် Z တန်ဖိုး ``5`` ရှိသော point တစ်ခုကို အမြင့် ``50`` တွင်ပြသပေးမည်ဖြစ်ပါသည်။
  * အမြင့် Z-level ကို :guilabel:`offset` (အရွေ့) တစ်ခုလည်း ထည့်သွင်းပေးထားနိုင်ပါသည်။ Data source အမျိုးမျိုးကို ၎င်းတို့အမြင့်တွင် တစ်ခုနှင့်တစ်ခု ကိုက်ညီစေရန် အသုံးဝင်ပါသည်။ ပုံမှန်အားဖြင့် data ထဲတွင်ပါသော အနိမ့်ဆုံး အမြင့် Z တန်ဖိုးကို ဤတန်ဖိုးအဖြစ်အသုံးပြုပါသည်။ မျဉ်း၏အဆုံးတွင်ရှိသော |refresh| :sup:`Refresh` ခလုတ်ကိုနှိပ်ပြီး ဤတန်ဖိုးကို မူရင်းသို့ပြန်လည်ပြောင်းလဲနိုင်ပါသည်။
* :guilabel:`Profile Chart Accuracy` အောက်တွင် :guilabel:`Maximum error (အများဆုံးအမှား)` သည် elevation profile ထဲတွင် point များ မည်မျှ သိပ်သိပ်သည်းသည်း သို့မဟုတ် ခပ်ကျဲကျဲ render ပြုလုပ်မည်ဆိုသည်ကို ထိန်းချုပ်ပေးပါသည်။ တန်ဖိုးအကြီးများကို အသုံးပြုလျှင် point နည်းနည်းဖြင့် မြန်မြန်ဆန်ဆန် ဖန်တီးပေးပါသည်။
* :guilabel:`Profile Chart Appearance` အောက်တွင် point များ ပြသခြင်းကိုထိန်းချုပ်နိုင်ပါသည်- 

  * :guilabel:`Point size` - အသုံးပြုနိုင်သော ယူနစ်များ (မီလီမီတာ၊ မြေပုံယူနစ်၊ pixel စသည်) ဖြင့် render လုပ်မည့် point များ၏ အရွယ်အစား
  * :guilabel:`Style` - Point များကို :guilabel:`Circle (စက်ဝိုင်း)` သို့မဟုတ် :guilabel:`Square (စတုရန်း)` အဖြစ် render လုပ်ရန်
  * Profile view တွင် မြင်နိုင်သော point အားလုံးကို :guilabel:`Color (အရောင်)` တစ်မျိုးတည်းအဖြစ် အသုံးပြုရန် 
  * :ref:`2D symbology <point_clouds_symbology>` မှတဆင့် သတ်မှတ်ထားသော အရောင်များဖြင့် point များကို ပြသရန် |checkbox| :guilabel:`Respect layer's coloring` ကို အမှန်ခြစ် ခြစ်ထားပါ။
  * |unchecked| :guilabel:`Apply opacity by distance from curve effect` ကို အမှန်ခြစ် ဖြုတ်ထားလျှင် profile curve မှ ပိုဝေးကွာသော point များ၏ အလင်းပိတ်နှုန်း (opacity) ကို လျော့ချပေးပါသည်။

.. _figure_point_cloud_elevation:

.. figure:: img/point_cloud_elevation.png
   :align: center

   Point cloud မြေပြင်အမြင့်ဆိုင်ရာ tab


.. _point_clouds_metadata:

Metadata Properties
--------------------

|editMetadata| :guilabel:`Metadata` tab တွင် layer ၏ metadata report တစ်ခုကို ဖန်တီးနိုင်၊ တည်းဖြတ်ပြင်ဆင်နိုင်ပါသည်။ အသေးစိတ်ကို :ref:`metadatamenu` တွင်ကြည့်ရှုပါ။

.. _point_clouds_statistics:

Statistics Properties (စာရင်းအင်းဆိုင်ရာ ဂုဏ်သတ္တိများ)
--------------------------------------------------------

|basicStatistics| :guilabel:`Statistics` tab ထဲတွင် point cloud များ၏ attribute နှင့် ၎င်းတို့၏ပျံ့နှံ့မှုများ အတွက် အကျဉ်းချုပ်ကို ကြည့်ရှုနိုင်ပါသည်။

ထိပ်ပိုင်းတွင် :guilabel:`Attribute Statistics` section ကိုတွေ့ရပါလိမ့်မည်။ ထိုထဲတွင် Point cloud ထဲရှိ attribute အားလုံးကို စာရင်းလုပ်ထားပြီး :guilabel:`Minimum (အနည်းဆုံးတန်ဖိုး)`၊ :guilabel:`Maximum (အများဆုံးတန်ိဖုး)`၊ :guilabel:`Mean (ပျမ်းမျှကိန်း)`၊ :guilabel:`Standard Deviation (စံသွေဖည်ခြင်း)` များကဲ့သို့သော တခြား စာရင်းအင်းအချက်အလက်များလည်း ပါဝင်ပါသည်။

:guilabel:`Classification` attribute တစ်ခုပါရှိလျှင် အောက်ပိုင်းတွင် အခြားဇယားတစ်ခု ရှိပါမည်။ Attribute ဇယားထဲတွင်ပါဝင်သော တန်ဖိုးများအားလုံးကို ထိုထဲတွင် စာရင်းလုပ်ထားပြီး ၎င်းတို့၏ ပကတိ :guilabel:`Count (အရေအတွက်)` နှင့် ဆက်စပ် :guilabel:`%` တို့လည်း ပါဝင်ပါသည်။

.. _figure_point_cloud_statistics:

.. figure:: img/point_cloud_statistics.png
   :align: center

   Point cloud စာရင်းအင်းဆိုင်ရာ tab


.. _`virtual_point_cloud`:

Virtual point cloud
====================

ဧရိယာအကျယ်ကြီးများကို တိုင်းတာထားသော Lidar survey သည် point များ သန်းချီပါဝင်သော multi-terabye dataset များဖြစ်ပါသည်။ ထိုကဲ့သလို့ အရမ်းကြီးမားသော dataset များကို point cloud တစ်ခုတည်းအဖြစ် ကိုယ်စားပြုပြသရန်မှာ သိမ်းဆည်းရန်အခက်အခဲ၊ ရွှေ့ပြောင်းရန်အခက်အခဲ၊ ကြည့်ရှုရန်နှင့် ဆန်းစစ်ရန်အခက်အခဲများကြောင့် လက်တွေ့တွင်ခက်ခဲပါသည်။ ထို့ကြောင့် point cloud data များကို စတုရန်းပုံစံ အကွက် (square tile) (ဓာတ်ပုံ - ဥပမာ ``1km x 1km``) များအဖြစ် သိမ်းဆည်းပြီး tile တစ်ခုချင်းစီသည် စီမံကိုင်တွယ်ရ အဆင်ပြေစေသော file size များရှိပါသည် (ဥပမာ ချုံ့လိုက်သောအခါ ~200 MB သာရှိပါသည်)

Data များကို tiling လုပ်ခြင်းသည် data အရွယ်အစားပြဿနာများကို ဖြေရှင်းပေးသော်လည်း tile တစ်ခုတည်းအတွင်းမှာ အပြည့်အဝမဝင်ဆန့်သော ဧရိယာများကို အလုပ်လုပ်ဆောင်သောအခါနှင့် ကြည့်သောအခါများတွင် ပြဿနာများ ဖြစ်စေပါသည်။ အသုံးပြုသူများသည် tile များစွာကို ထည့်သွင်းစဉ်းစားရန် လုပ်ငန်းစဉ် (workflows) များကို ဖန်တီးထားရန် လိုအပ်ပြီး ရလာဒ်တွင် မလိုအပ်သော artefacts (အပြစ်အနာအဆာ) များမပါစေရန် tile များ၏အစွန်နားရှိ data များကို ကိုင်တွယ်သောအခါ အထူးဂရုစိုက်ရန် လိုအပ်ပါသည်။ အလားတူစွာပင် point cloud data များကို ကြည့်သောအခါ file အများကြီး ထည့်သွင်းပြီး အားလုံးကို symbology အတူတူထားလျှင် နှေးကွေးစေပါသည်။

အောက်တွင် ဖော်ပြထားသည်မှာ point cloud tile အများကြီးကို QGIS ထဲကို ထည့်ထားသော ဥပမာ ဖြစ်ပါသည်။ Tile တစ်ခုချင်းကို အနည်းဆုံး/အများဆုံး အမြင့်  Z တန်ဖိုးများပေါ် မူတည်ပြီး style လုပ်ထားခြင်းဖြစ်ပြီး tile များရဲ့ အစွန်များတွင် မြင်သာသည့် artefact (အပြစ်အနာအဆာ) များဖြစ်စေပါသည်။ Layer တစ်ခုချင်းစီအတွက် style ကို ခွဲခြားချိန်ညှိရန် လိုအပ်ပါသည်။

.. _figure_point_cloud_tiles:

.. figure:: img/point_cloud_individual_tiles.png
   :align: center

   အစွန်များတွင် artefact (အပြစ်အနာအဆာ) များပါနေသော point cloud tile တစ်ခုချင်းစီများ

GIS လောကတွင် အသုံးပြုသူအများစုသည် virtual raster များနှင့် ရင်းရင်းနှီးနှီးရှိကြပါသည်။ Virtual raster ဆိုသည်မှာ တကယ့် data များနှင့် တခြား raster ကို အကိုးအကားလုပ်ထားသော file တစ်ခုကိုဆိုလိုပါသည်။ ဒီနည်းလမ်းတွင် GIS software သည် file အများကြီးပါဝင်သော dataset တစ်ခုလုံးကို raster layer တစ်ခုတည်းအဖြစ် လုပ်ဆောင်ပါသည်။ ထို့ကြောင့် virtual file ထဲတွင် စာရင်းလုပ်ထားသော raster များအားလုံးကို ကြည့်ရှုခြင်းနှင့် ဆန်းစစ်ခြင်းများလုပ်ရန် ပိုမိုလွယ်ကူစေပါသည်။

GDAL မှ virtual raster သဘောတရားကို ယူသုံးခြင်း - **virtual point cloud (VPC)**  ဆိုသည်မှာ အခြား point cloud file များကို အကိုးအကားလုပ်ထားသော file format တစ်မျိုးဖြစ်ပါသည်။ Virtual point cloud များကို လုပ်ဆောင်နိုင်သော software များသည် tile dataset တစ်ခုလုံးကို data source တစ်ခုတည်းအဖြစ် လုပ်ဆောင်ပါသည်။

.. _figure_point_cloud_vpc:

.. figure:: img/point_cloud_vpc.png
   :align: center

   Virtual point cloud

Virtual point cloud ကို ကြည့်ရှုခြင်းနှင့် ပြင်ဆင်လုပ်ကိုင်ခြင်းသည် များစွာလွယ်ကူပါသည်။

.. only:: html

  .. _figure_point_cloud_vpc2d:

  .. figure:: img/point_cloud_vpc_2d.gif
     :align: center

     2D မျက်နှာပြင်ပေါ်ရှိ virtual point cloud ရလာဒ် - zoom ချဲ့ကြည့်သောအခါ အသေးစိတ်ကို ပြသပေးပါသည်


Virtual point cloud file ဆိုသည်မှာ :file:`.vpc` extension ဖြင့် ရိုးရှင်းသော JSON file တစ်ခုဖြစ်ပြီး အမှန်တကယ် data file (ဥပမာ :file:`.LAS`၊ :file:`.LAZ` သို့မဟုတ် :file:`.COPC` file) များကိုလုပ်ထားသော အကိုးအကားများ ပါဝင်ပြီး ထပ်ဆောင်း metadata များကို file များမှရယူပါသည်။ VPC file များကို လက်ဖြင့်ရေးနိုင်သော်လည်း အောက်တွင်ဖော်ပြထားသော အလိုအလျောက်လုပ်ဆောင်သော tool များအသုံးပြုရန် လေးလေးနက်နက် အကြံပြုပါသည် -

* Processing **Build virtual point cloud** algorithm

.. todo: Replace the above with URL to the alg when available


*  `PDAL wrench <https://github.com/PDAL/wrench>`_ tool ၏ ``build_vpc`` command

အသေးစိတ်များအတွက် အကောင်းဆုံး လက်တွေ့လေ့ကျင့်ခန်းများနှင့် ရွေးချယ်စရာ extension များပါသော (အကျဉ်းချုပ်ကဲ့သို့) `VPC specification <https://github.com/PDAL/wrench/blob/main/vpc-spec.md>`_ ကို ကိုးကားပါ။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |3d| image:: /static/common/3d.png
   :width: 1.5em
.. |basicStatistics| image:: /static/common/mAlgorithmBasicStatistics.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |editMetadata| image:: /static/common/editmetadata.png
   :width: 1.2em
.. |elevationscale| image:: /static/common/elevationscale.png
   :width: 1.5em
.. |fileOpen| image:: /static/common/mActionFileOpen.png
   :width: 1.5em
.. |fileSaveAs| image:: /static/common/mActionFileSaveAs.png
   :width: 1.5em
.. |identify| image:: /static/common/mActionIdentify.png
   :width: 1.5em
.. |mapIdentification| image:: /static/common/mActionMapIdentification.png
   :width: 1.5em
.. |metadata| image:: /static/common/metadata.png
   :width: 1.5em
.. |multibandColor| image:: /static/common/multibandColor.png
   :width: 1.5em
.. |paletted| image:: /static/common/paletted.png
   :width: 1.5em
.. |pointCloudExtent| image:: /static/common/pointCloudExtent.png
   :width: 1.5em
.. |refresh| image:: /static/common/mActionRefresh.png
   :width: 1.5em
.. |rendering| image:: /static/common/rendering.png
   :width: 1.5em
.. |setProjection| image:: /static/common/mActionSetProjection.png
   :width: 1.5em
.. |singleColor| image:: /static/common/singleColor.png
   :width: 1.5em
.. |singlebandPseudocolor| image:: /static/common/singlebandPseudocolor.png
   :width: 1.5em
.. |symbology| image:: /static/common/symbology.png
   :width: 2em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
.. |symbologyRemove| image:: /static/common/symbologyRemove.png
   :width: 1.5em
.. |system| image:: /static/common/system.png
   :width: 1.5em
.. |unchecked| image:: /static/common/unchecked.png
   :width: 1.3em
