:orphan:

.. _algs_include:

*********************************************************
Algorithms Include
*********************************************************

.. only:: html

   .. contents::
      :local:
      :depth: 1


Python Code Sample
===================

.. The following section is used to load python code sample in algs help

.. **algorithm_code_section**

.. code-block:: python

    import processing
    processing.run("algorithm_id", {parameter_dictionary})

Processing Toolbox ထဲရှိ algorithm ပေါ်တွင် mouse ကိုတင်ထားလျှင် *algorithm id* ကိုပြသပေးပါသည်။ *parameter dictionary* သည် parameter နာမည်များနှင့် တန်ဖိုးများကို ပေးပါသည်။ Python console မှ algorithm များကို မည်သို့လုပ်ဆောင်ရမည် ဆိုသည့် အသေးစိတ်ကို သိရှိလိုလျှင် :ref:`processing_console` တွင်ကြည့်ပါ။

.. **end_algorithm_code_section**


Output Types
=============

.. The following describes the different options for algorithm outputs,
 with variants including the "skip output" and the "append" options
 
Directory
----------

.. **directory_output_types**

* ယာယီ လမ်းကြောင်းတစ်ခုတွင် သိမ်းဆည်းပါ
* လမ်းကြောင်းတွင်သိမ်းဆည်းပါ

.. **end_directory_output_types**


.. **directory_output_types_skip**

* Output ကိုကျော်ပစ်ခြင်း
* ယာယီ လမ်းကြောင်းတစ်ခုတွင် သိမ်းဆည်းပါ
* လမ်းကြောင်းတွင်သိမ်းဆည်းပါ

.. **end_directory_output_types_skip**

File
-----

.. **file_output_types**

* ယာယီ file တစ်ခုတွင် သိမ်းဆည်းပါ
* File တွင်သိမ်းဆည်းပါ

.. **end_file_output_types**


.. **file_output_types_skip**

* Output ကိုကျော်ပစ်ခြင်း
* ယာယီ file တစ်ခုတွင် သိမ်းဆည်းပါ
* File တွင်သိမ်းဆည်းပါ

.. **end_file_output_types_skip**

Layer
------

.. **layer_output_types**

* ယာယီ layer ဖန်တီးပါ (``TEMPORARY_OUTPUT``)
* File တွင်သိမ်းဆည်းပါ
* Geopackage တွင် သိမ်းဆည်းပါ
* Database ဇယားတွင် သိမ်းဆည်းပါ

File encoding ကိုလည်းဤနေရာတွင်ပြောင်းလဲနိုင်ပါသည်။

.. **end_layer_output_types**


.. **layer_output_types_append**

* ယာယီ layer ဖန်တီးပါ (``TEMPORARY_OUTPUT``)
* File တွင်သိမ်းဆည်းပါ
* Geopackage တွင် သိမ်းဆည်းပါ
* Database ဇယားတွင် သိမ်းဆည်းပါ
* Layer သို့ဆက်တွဲပေါင်းထည့်ပါ (append)

File encoding ကိုလည်းဤနေရာတွင်ပြောင်းလဲနိုင်ပါသည်။

.. **end_layer_output_types_append**


.. **layer_output_types_skip**


* Output ကိုကျော်ပစ်ပါ
* ယာယီ layer ဖန်တီးပါ (``TEMPORARY_OUTPUT``)
* File တွင်သိမ်းဆည်းပါ
* Geopackage တွင် သိမ်းဆည်းပါ
* Database ဇယားတွင် သိမ်းဆည်းပါ

File encoding ကိုလည်းဤနေရာတွင်ပြောင်းလဲနိုင်ပါသည်။

.. **end_layer_output_types_skip**


Extent Dropdown
================

.. The following refers to the extent selector widget in the algorithms GUI


.. **extent_options**

အသုံးပြုနိုင်သော နည်းလမ်းများမှာ -

* Layer မှ တွက်ချက်ခြင်း - လက်ရှိ project ထဲတွင်ထည့်သွင်းထားသော layer ၏ extent (နယ်ပယ်အကျယ်အဝန်း)ကိုအသုံးပြုပါသည်။
* Layout map မှ တွက်ချက်ခြင်း - အသုံးပြုနေသော project ထဲရှိ :ref:`layout map item <layout_map_item>` တစ်ခု၏ extent အသုံးပြုပါသည်။
* Bookmark မှ တွက်ချက်ခြင်း - မှတ်ထားသော :ref:`bookmark <sec_bookmarks>` တစ်ခု၏ extent ကိုအသုံးပြုပါသည်။
* မြေပုံ canvas extent ကိုအသုံးပြုခြင်း
* Canvas ပေါ်တွင်ရေးဆွဲခြင်း - တွက်ချက်လိုသည့် ဧရိယာကို ထောင့်မှန်စတုဂံပုံဆွဲခြင်း။
* ``x အနည်းဆုံး၊ x အများဆုံး၊ y အနည်းဆုံး၊  y အများဆုံး`` တို့အဖြစ် ကိုဩဒိနိတ်များကို ထည့်သွင်းခြင်း။

.. **end_extent_options**


Geometric predicates
=====================

.. The following section is included in vector selection algorithms such as
 qgisselectbylocation, qgisextractbylocation and vector general algorithms
 such as qgisjoinattributesbylocation and qgisjoinbylocationsummary
 
.. **geometric_predicates**

Geometric predicate ဆိုသည်မှာ feature တစ်ခုနှင့် အခြား feature တစ်ခု၏ တည်နေရာဆိုင်ရာဆက်နွယ်မှုကို ၎င်းတို့၏ ဂျီဩမေတြီများမည်သို့ မျှဝေနေရာယူနေသလဲဆိုသည်ကို နှိုင်းယှဉ်ခြင်းအားဖြင့် ဆုံးဖြတ်ရန်အသုံးပြုသော boolean (မှန်/မှား) function များကို ဆိုလိုပါသည်။

.. figure:: /docs/user_manual/processing_algs/img/selectbylocation.png
   :align: center

   Layer များအကြား တည်နေရာဆိုင်ရာဆက်နွယ်မှုကို ရှာဖွေခြင်း

အထက်ဖော်ပြပါပုံကိုအသုံးပြုပြီး လိမ္မော်ရောင် ထောင့်မှန်စတုဂံ feature များကို အစိမ်းရောင်စက်ဝိုင်းများနှင့် တည်နေရာအရ နှိုင်းယှဉ်ပြီး အစိမ်းရောင်စက်ဝိုင်းများကို ရှာဖွေပါသည်။ အသုံးပြုနိုင်သော geometric predicate များမှာ-

 
*Intersect (ထိဖြတ်ခြင်း)*
  ဂျီဩမေတြီ တစ်ခုသည် အခြား ဂျီဩမေတြီ တစ်ခုနှင့်ထိဖြတ်/မဖြတ်ကို စစ်ဆေးပေးပါသည်။ ထိဖြတ်နေလျှင် (နေရာအစိတ်အပိုင်းတစ်ခုကိုမျှဝေသုံးစွဲခြင်း - ထပ်နေခြင်း သို့မဟုတ် ထိနေခြင်း ကိုဆိုလိုပါသည်) 1 (အမှန်) တန်ဖိုးကို ထုတ်ပေးပြီး မဖြစ်လျှင် 0 တန်ဖိုးကိုထုတ်ပေးပါသည်။ အထက်ဖော်ပြပါ ဓာတ်ပုံတွင် စက်ဝိုင်း 1၊ 2 နှင့် 3 တို့ကိုထုတ်ပေးပါသည်။

*Contain (ပါဝင်ခြင်း)*
  b ၏အမှတ်များသည် a ၏အပြင်ဘက်တွင် မရှိလျှင်နှင့် မရှိမှသာ တန်ဖိုး 1 (အမှန်) ကိုထုတ်ပေးပြီး အနည်းဆုံး b ၏အတွင်းဘက်ကတစ်မှတ်သည် a ၏အတွင်းဘက်တွင် ရှိရပါမည်။ ပုံတွင် မည်သည့်စက်ဝိုင်းမှ ပြန်ထုတ်မပေးပါ သို့သော် ၎င်းသည် စက်ဝိုင်း 1 အပြည့်အဝပါဝင်သောကြောင့် အခြားနည်းဖြင့်ရှာဖွေလျှင် ထောင့်မှန်စတုဂံ ကိုပြန်ထုတ်ပေးပါမည်။ ယခုနည်းလမ်းလည်း *are within (အတွင်းတွင်ရှိခြင်း)* နှင့် ဆန့်ကျင်ဘက်ဖြစ်ပါသည်။

*Disjoint (အဆက်ဖြုတ်ခြင်း)*
  ဂျီဩမေတြီ များသည် မည်သည့်အစိတ်အပိုင်းမျှ နေရာချင်းမျှဝေမနေလျှင် (ထပ်မနေ၊ ထိမနေခြင်း ကိုဆိုလိုပါသည်) တန်ဖိုး 1 (အမှန်) ကို ထုတ်ပေးပါမည်။ စက်ဝိုင်း 4 ကိုသာ ပြန်ထုတ်ပေးမည်ဖြစ်သည်။

*Equal (ညီမျှခြင်း)*
  ဂျီဩမေတြီ များသည်လုံးဝ တစ်ပုံစံတည်း တူနေလျှင် သို့မဟုတ် တူနေမှသာ တန်ဖိုး 1 (အမှန်) ကိုထုတ်ပေးပါသည်။ စက်ဝိုင်းများကို ထုတ်မပေးပါ။
  
*Touch (ထိနေခြင်း)*
  ဂျီဩမေတြီ တစ်ခုသည် အခြားဂျီဩမေတြီ တစ်ခုနှင့် ထိ/မထိ စစ်ဆေးပေးပါသည်။ ဂျီဩမေတြီများသည် အနည်းဆုံး ဘုံ point တစ်ခုရှိနေပြီး ၎င်းတို့၏အတွင်းပိုင်းများသည် ထိဖြတ်မနေသောအခါ တန်ဖိုး 1 (အမှန်) ကိုထုတ်ပေးပါသည်။ စက်ဝိုင်း 3 ကိုသာ ပြန်ထုတ်ပေးပါသည်။

*Overlap (ထပ်နေခြင်း)*
  ဂျီဩမေတြီ သည် အခြား ဂျီဩမေတြီ တစ်ခုနှင့် ထပ်/မထပ် ကို စစ်ဆေးပေးပါသည်။ ဂျီဩမေတြီများသည် နေရာခြင်း မျှဝေနေပြီး အရွယ်အစားလည်း တူညီနေသော်လည်း တစ်ခုထဲတွင် အခြားတစ်ခုက လုံးဝဝင်ရောက်နေခြင်း မဟုတ်လျှင် တန်ဖိုး 1 (အမှန်) ကိုထုတ်ပေးပါသည်။ စက်ဝိုင်း 2 ကိုသာ ပြန်ထုတ်ပေးပါသည်။
  
*Are within (အတွင်းတွင်ရှိခြင်း)*
  ဂျီဩမေတြီ သည် အခြား ဂျီဩမေတြီ တစ်ခုအတွင်းတွင်ရှိ/မရှိ ကို စစ်ဆေးပေးပါသည်။ ဂျီဩမေတြီ a သည် geometry b ၏အတွင်းတွင် လုံးဝကျရောက်နေလျှင် တန်ဖိုး 1 (အမှန်) ကိုထုတ်ပေးပါသည်။ စက်ဝိုင်း 1 ကိုသာ ပြန်ထုတ်ပေးပါသည်။

*Cross (ကန့်လန့်ဖြတ်နေခြင်း)*
  အသုံးပြုထားသော ဂျီဩမေတြီ များသည် အားလုံးမဟုတ်တောင် အချို့သော အတွင်းပိုင်း ဘုံ point များရှိနေပြီး အမှန်တကယ် ကန့်လန့်ဖြတ်နေခြင်း သည် အမြင့်ဆုံး ဂျီဩမေတြီ ထက်နိမ့်သော dimension တစ်ခုတွင် ဖြစ်သောအခါ တန်ဖိုး 1 (အမှန်) ကိုထုတ်ပေးပါသည်။ ဥပမာ- polygon တစ်ခုကိုဖြတ်သော line တစ်ခုသည် line အဖြစ် ကန့်လန့်ဖြတ်ပါမည် (အမှန်)။ ကန့်လန့်ဖြတ်နေသော line နှစ်ခုသည် point အဖြစ် ဖြတ်ပါလိမ့်မည် (အမှန်)။ Polygon နှစ်ခုသည် polygon တစ်ခုအဖြစ် ဖြတ်ပါလိမ့်မည် (အမှား)။ ဓာတ်ပုံတွင် စက်ဝိုင်းများကို ပြန်ထုတ်မပေးပါ။

.. **end_geometric_predicates**


Algorithm များအတွက် မှတ်ချက် (Notes on algorithms)
===================================================

.. **warning_attributes**

.. warning:: **ဂျီဩမေတြီ မွမ်းမံပြင်ဆင်ထားခြင်းများသာ**

   ယခုလုပ်ဆောင်မှုသည် feature ဂျီဩမေတြီ များကိုသာ မွမ်းမံပြင်ဆင်ပေးပါသည်။ Overlay operation ဖြင့် feature များ၏ ဧရိယာ သို့မဟုတ် အလျား ကဲ့သို့သော property များကို ပြင်ဆင်သော်လည်း feature များ၏ အချက်အလက် တန်ဖိုးများကို **ပြင်ဆင်မည်မဟုတ်ပါ**။ ထိုကဲ့သို့သော property များကို အချက်အလက်များအဖြစ် သိမ်းဆည်းထားလျှင် ၎င်းအချက်အလက်များကို အသုံးပြုသူကပြင်ဆင်ပေးရပါမည်။

.. **end_warning_attributes**


Raster data types
==================

Without user input (native)
----------------------------

.. **native_raster_data_types**


.. The following section is included in raster based algorithms such as
 qgisrasterbooleanand, qgisrasterbooleanor, qgisreclassifybylayer, qgisreclassifybytable

* 0 --- Byte        (Eight bit unsigned integer (quint8))
* 1 --- Int16       (Sixteen bit signed integer (qint16))
* 2 --- UInt16      (Sixteen bit unsigned integer (quint16))
* 3 --- Int32       (Thirty two bit signed integer (qint32))
* 4 --- UInt32      (Thirty two bit unsigned integer (quint32))
* 5 --- Float32     (Thirty two bit floating point (float))
* 6 --- Float64     (Sixty four bit floating point (double))
* 7 --- CInt16      (Complex Int16)
* 8 --- CInt32      (Complex Int32)
* 9 --- CFloat32    (Complex Float32)
* 10 --- CFloat64   (Complex Float64)
* 11 --- Int8       (Eight bit signed integer (qint8))

အသုံးပြုနိုင်သော နည်းလမ်းများမှာ QGIS ထဲတွင်ပါသော GDAL version ပေါ်တွင်မူတည်ပါသည် (:menuselection:`Help --> About` menu တွင်ကြည့်ပါ)။

.. **end_native_raster_data_types**


Without user input
-------------------

.. **raster_data_types**

.. The following section is included in raster based algorithms such as
 gdalrasterize, gdalmerge, gdalretile, gdalgriddatametrics,
 gdalgridinversedistancenearestneighbor, gdalgridinversedistance, gdalgridlinear,
 gdalgridaverage, gdalgridnearestneighbor, gdalproximity, gdalrastercalculator
 

* 0 --- Byte        (Eight bit unsigned integer (quint8))
* 1 --- Int16       (Sixteen bit signed integer (qint16))
* 2 --- UInt16      (Sixteen bit unsigned integer (quint16))
* 3 --- UInt32      (Thirty two bit unsigned integer (quint32))
* 4 --- Int32       (Thirty two bit signed integer (qint32))
* 5 --- Float32     (Thirty two bit floating point (float))
* 6 --- Float64     (Sixty four bit floating point (double))
* 7 --- CInt16      (Complex Int16)
* 8 --- CInt32      (Complex Int32)
* 9 --- CFloat32    (Complex Float32)
* 10 --- CFloat64   (Complex Float64)
* 11 --- Int8       (Eight bit signed integer (qint8))

အသုံးပြုနိုင်သော နည်းလမ်းများမှာ QGIS ထဲတွင်ပါသော GDAL version ပေါ်တွင်မူတည်ပါသည် (:menuselection:`Help --> About` menu တွင်ကြည့်ပါ)။

.. **end_raster_data_types**


With user input
----------------

.. **raster_data_types_extended**

.. The following section is included in raster based algorithms such as
  gdalwarpreproject, gdalcliprasterbyextent, gdalcliprasterbymasklayer,
  gdalrearrange_bands, gdaltranslate
  
* 0 --- Use Input Layer Data Type (Input layer ၏ data အမျိုးအစားကိုအသုံးပြုပါ)
* 1 --- Byte        (Eight bit unsigned integer (quint8))
* 2 --- Int16       (Sixteen bit signed integer (qint16))
* 3 --- UInt16      (Sixteen bit unsigned integer (quint16))
* 4 --- UInt32      (Thirty two bit unsigned integer (quint32))
* 5 --- Int32       (Thirty two bit signed integer (qint32))
* 6 --- Float32     (Thirty two bit floating point (float))
* 7 --- Float64     (Sixty four bit floating point (double))
* 8 --- CInt16      (Complex Int16)
* 9 --- CInt32      (Complex Int32)
* 10 --- CFloat32   (Complex Float32)
* 11 --- CFloat64   (Complex Float64)
* 12 --- Int8       (Eight bit signed integer (qint8))

အသုံးပြုနိုင်သော နည်းလမ်းများမှာ QGIS ထဲတွင်ပါသော GDAL version ပေါ်တွင်မူတည်ပါသည် (:menuselection:`Help --> About` menu တွင်ကြည့်ပါ)။

.. **end_raster_data_types_extended**


