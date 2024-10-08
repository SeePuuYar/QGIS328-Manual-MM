Mesh (အချိန်ဆိုင်ရာ နှင့်အခြားအစိတ်အပိုင်းများပါရှိသည့်ဖွဲ့စည်းပုံမရှိသောအကွက်)
================================================================================

.. only:: html

   .. contents::
      :local:
      :depth: 1


.. _qgismeshcontours:

Export contours (ကွန်တိုများထုတ်ယူခြင်း)
-----------------------------------------

Mesh scalar dataset တစ်ခုမှ vector layer တစ်ခုအနေဖြင့် ကွန်တိုများကိုဖန်တီးပေးပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input mesh layer** (**ထည့်သွင်းအသုံးပြုသော mesh layer**)
     - ``INPUT``
     - [mesh]
     - Data ထုတ်ယူမည့် mesh layer
   * - **Dataset groups** (**Dataset အုပ်စုများ**)
     - ``DATASET_GROUPS``
     - [layer] [list]
     - Dataset အုပ်စုများ	 
   * - **Dataset time** (**Dataset အချိန်**)
     - ``DATASET_TIME``
     - [datetime]
     - လုပ်ဆောင်မည့် အချိန်အပိုင်းအခြား

       * 0 --- Current canvas time (လက်ရှိ canvas အချိန်)
       * 1 --- Defined date/time (သတ်မှတ်ထားသော ရက်စွဲ/အချိန်)
       * 2 --- Dataset group time step (Dataset အုပ်စု အချိန်အဆင့်)
   * - **Increment between contour levels** (**ကွန်တို level နှစ်ခုအကြား တိုးလာမှု**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``INCREMENT``
     - [number]

       Default: *Not set*
     - ဖန်တီးထားသော level များ၏ ကြားအကွာအဝေး
   * - **Minimum contour level** (**အနည်းဆုံး ကွန်တို level**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``MINIMUM``
     - [number]

       Default: *Not set*
     - ကွန်တိုများ၏ အစ level တန်ဖိုးများ
   * - **Maximum contour level** (**အများဆုံး ကွန်တို level**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``MAXIMUM``
     - [number]

       Default: *Not set*
     - ကွန်တိုများ၏ အများဆုံးတန်ဖိုး၊ ဖန်တီးပေးသော တန်ဖိုးများသည် ၎င်းတန်ဖိုးထက်ပိုကြီးလိမ့်မည်မဟုတ်ပါ ဟု ဆိုလိုပါသည်။
   * - **List of contours level** (**ကွန်တို level များ၏စာရင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``CONTOUR_LEVEL_LIST``
     - [number]

       Default: *Not set*
     - လိုချင်သော ကွန်တို level များစာရင်း (commas ဖြင့်ပိုင်းခြားထားပါသည်)။ ဖြည့်ထားလျှင် တိုးလာမှု၊ အနည်းဆုံး နှင့် အများဆုံး field များကို ထည့်သွင်းစဉ်းစားမည် မဟုတ်ပါ။
   * - **Output coordinate system** (**Output ကိုဩဒိနိတ်စနစ်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``CRS_OUTPUT``
     - [crs]
     - Output တွင်သတ်မှတ်မည့် ကိုဩဒိနိတ်စနစ်
   * - **Exported contour lines** (**ထုတ်ယူထားသော ကွန်တို line များ**)
     - ``OUTPUT_LINES``
     - [vector: line]

       Default: ``[Create temporary layer] ([ယာယီ layer ဖန်တီးခြင်း])``
     - Mesh layer ၏ ကွန်တိုများကို ကိုယ်စားပြုသော output line layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

   * - **Exported contour polygons** (**ထုတ်ယူထားသော ကွန်တို polygon များ**)
     - ``OUTPUT_POLYGONS``
     - [vector: polygon]

       Default: ``[Create temporary layer] ([ယာယီ layer ဖန်တီးခြင်း])``
     - Mesh layer ၏ ကွန်တိုများကို ကိုယ်စားပြုသော output polygon layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် - 

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Exported contour lines** (**ထုတ်ယူထားသော ကွန်တို line များ**)
     - ``OUTPUT_LINES``
     - [vector: line]
     - Mesh layer ၏ ကွန်တိုများကို ကိုယ်စားပြုသော line layer
   * - **Exported contour polygons** (**ထုတ်ယူထားသော ကွန်တို polygon များ**)
     - ``OUTPUT_POLYGONS``
     - [vector: polygon]
     - Mesh layer ၏ ကွန်တိုများကို ကိုယ်စားပြုသော polygon layer	 


Python code
............

**Algorithm ID**: ``native:meshcontours``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgismeshexportcrosssection:

Export cross section dataset values on lines from mesh (Mesh မှ line များပေါ်တွင် cross section dataset တန်ဖိုးများကို ထုတ်ယူခြင်း)
------------------------------------------------------------------------------------------------------------------------------------

Vector layer တစ်ခုထဲတွင်ပါဝင်သော line များမှ mesh dataset တစ်ခု၏တန်ဖိုးများကို ဆွဲထုတ်ပေးပါသည်။

Line တစ်ခုချင်းစီ၏ မျဉ်းအဆစ် (vertex) များပေါ်ရှိ တန်ဖိုးများကိုဆွဲထုတ်ခြင်းအတွက် resolution အကွာအဝေး parameter တစ်ခုဖြင့် line တစ်ကြောင်းစီကို ခွဲခြားပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input mesh layer** (**ထည့်သွင်းအသုံးပြုသော mesh layer**)
     - ``INPUT``
     - [mesh]
     - Data ထုတ်ယူမည့် mesh layer
   * - **Dataset groups** (**Dataset အုပ်စုများ**)
     - ``DATASET_GROUPS``
     - [layer] [list]
     - Dataset အုပ်စုများ
   * - **Dataset time** (**Dataset အချိန်**)
     - ``DATASET_TIME``
     - [datetime]
     - လုပ်ဆောင်မည့် အချိန်အပိုင်းအခြား

       * 0 --- Current canvas time (လက်ရှိ canvas အချိန်)
       * 1 --- Defined date/time (သတ်မှတ်ထားသော ရက်စွဲ/အချိန်)
       * 2 --- Dataset group time step (Dataset အုပ်စု အချိန်အဆင့်)
   * - **Lines for data export** (**Data ထုတ်ခြင်းအတွက် line များ**)
     - ``INPUT_LINES``
     - [vector: line]
     - Dataset mesh မှ data များကိုဆွဲထုတ်မည့် line များ
   * - **Line segmentation resolution** (**Line အပိုင်းများ၏ ကြည်လင်ပြတ်သားမှု**)
     - ``RESOLUTION``
     - [number]

       Default: 10.0
     - Dataset mesh မှ data များကိုဆွဲထုတ်မည့် line များပေါ်ရှိ point နှစ်ခုအကြား အကွာအဝေး
   * - **Digits count for dataset value** (**Dataset တန်ဖိုးအတွက် ဂဏန်းများအရေအတွက်**)
     - ``DATASET_DIGITS``
     - [number]

       Default: 2
     - Dataset တန်ဖိုးများကို ဒသမနေရာထားရှိမည့် ဂဏန်းအရေအတွက်
   * - **Exported data CSV file** (**ထုတ်ယူထားသော Data CSV file**)
     - ``OUTPUT``
     - [file]

       Default: ``[Save to temporary file] ([ယာယီ file ထဲတွင်သိမ်းဆည်းပါ])``
     - Output file ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Exported data CSV file** (**ထုတ်ယူထားသော data CSV file**)
     - ``OUTPUT``
     - [file]
     -

Python code
............

**Algorithm ID**: ``native:meshexportcrosssection``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisexportmeshedges:

Export mesh edges (Mesh အနားသတ်များကိုထုတ်ယူခြင်း)
---------------------------------------------------

အချက်အလက်တန်ဖိုးများအဖြစ် edge များပေါ်ရှိ dataset တန်ဖိုးများဖြင့် mesh layer တစ်ခု၏ edge များကို line vector layer တစ်ခုအဖြစ် ထုတ်ယူပေးပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input mesh layer** (**ထည့်သွင်းအသုံးပြုသော mesh layer**)
     - ``INPUT``
     - [mesh]
     - Data ထုတ်ယူမည့် mesh layer
   * - **Dataset groups** (**Dataset အုပ်စုများ**)
     - ``DATASET_GROUPS``
     - [layer] [list]
     - Dataset အုပ်စုများ
   * - **Dataset time** (**Dataset အချိန်**)
     - ``DATASET_TIME``
     - [datetime]
     - လုပ်ဆောင်မည့် အချိန်အပိုင်းအခြား

       * 0 --- Current canvas time (လက်ရှိ canvas အချိန်)
       * 1 --- Defined date/time (သတ်မှတ်ထားသော ရက်စွဲ/အချိန်)
       * 2 --- Dataset group time step (Dataset အုပ်စု အချိန်အဆင့်)
   * - **Output coordinate system** (**Output ကိုဩဒိနိတ်စနစ်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``CRS_OUTPUT``
     - [crs]
     - Output တွင်သတ်မှတ်ရန် ကိုဩဒိနိတ်စနစ်
   * - **Export vector option** (**Vector ရွေးချယ်စရာများကိုထုတ်ယူခြင်း**)
     - ``VECTOR_OPTION``
     - [enumeration]
     - Vector တန်ဖိုး ထုတ်ယူခြင်း၏ ကိုဩဒိနိတ်အမျိုးအစား

       * 0 --- Cartesian (x,y)
       * 1 --- Polar (ပြင်းအားပမာဏ ၊ ဒီဂရီ)
       * 2 --- Cartesian နှင့် polar
   * - **Output vector layer**
     - ``OUTPUT``
     - [vector: line]

       Default: ``[Create temporary layer] ([ယာယီ layer ဖန်တီးခြင်း])``
     - Output file ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output vector layer**
     - ``OUTPUT``
     - [vector: line]
     - ဆက်စပ် dataset တန်ဖိုးများဖြင့် input mesh layer ၏ edge များပါဝင်သော output vector line layer

Python code
............

**Algorithm ID**: ``native:exportmeshedges``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisexportmeshfaces:

Export mesh faces (Mesh မျက်နှာပြင်များထုတ်ယူခြင်း)
----------------------------------------------------

အချက်အလက်တန်ဖိုးများအဖြစ် မျက်နှာပြင် (face) များပေါ်ရှိ dataset တန်ဖိုးများဖြင့် mesh layer တစ်ခု၏ မျက်နှာပြင်များကို polygon vector layer အဖြစ်ထုတ်ယူပေးပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input mesh layer** (**ထည့်သွင်းအသုံးပြုသော mesh layer**)
     - ``INPUT``
     - [mesh]
     - Data ထုတ်ယူမည့် mesh layer
   * - **Dataset groups** (**Dataset အုပ်စုများ**)
     - ``DATASET_GROUPS``
     - [layer] [list]
     - Dataset အုပ်စုများ
   * - **Dataset time** (**Dataset အချိန်**)
     - ``DATASET_TIME``
     - [datetime]
     - လုပ်ဆောင်မည့် အချိန်အပိုင်းအခြား

       * 0 --- Current canvas time (လက်ရှိ canvas အချိန်)
       * 1 --- Defined date/time (သတ်မှတ်ထားသော ရက်စွဲ/အချိန်)
       * 2 --- Dataset group time step (Dataset အုပ်စု အချိန်အဆင့်)
   * - **Output coordinate system** (**Output ကိုဩဒိနိတ်စနစ်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``CRS_OUTPUT``
     - [crs]
     - Output တွင်သတ်မှတ်ရန် ကိုဩဒိနိတ်စနစ်
   * - **Export vector option** (**Vector ရွေးချယ်စရာများကိုထုတ်ယူခြင်း**)
     - ``VECTOR_OPTION``
     - [enumeration]
     - Vector တန်ဖိုး ထုတ်ယူခြင်း၏ ကိုဩဒိနိတ်အမျိုးအစား

       * 0 --- Cartesian (x,y)
       * 1 --- Polar (ပြင်းအားပမာဏ ၊ ဒီဂရီ)
       * 2 --- Cartesian နှင့် polar
   * - **Output vector layer**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer] ([ယာယီ layer ဖန်တီးခြင်း])``
     - Output file ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output vector layer**
     - ``OUTPUT``
     - [vector: polygon]
     - ဆက်စပ် dataset တန်ဖိုးများဖြင့် input mesh layer ၏ မျက်နှာပြင်များပါဝင်သော output vector polygon layer

Python code
............

**Algorithm ID**: ``native:exportmeshfaces``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisexportmeshongrid:

Export mesh on grid (Grid ပေါ်တွင် mesh ကိုထုတ်ယူခြင်း)
--------------------------------------------------------

Mesh layer dataset တစ်ခု၏ တန်ဖိုးများကို grid ပြုလုပ်ထားသော point vector layer တစ်ခုသို့ ထုတ်ယူပေးပြီး ၎င်း point ပေါ်ရှိ dataset တန်ဖိုးများကို attribute တန်ဖိုးများအဖြစ်ထားရှိပေးပါသည်။

ထုထည် (သုံးဘက်မြင် ထပ်ထားသော dataset တန်ဖိုးများ) ပေါ်ရှိ data အတွက် :ref:`the mesh layer properties <mesh_stacked_averaging>` (Default သည် အဆင့်များစွာကို ပျမ်းမျှလုပ်သော နည်းလမ်း ဖြစ်သည်) ထဲတွင် သတ်မှတ်ထားသော နည်းလမ်းကိုအသုံးပြုပြီး မျက်နှာပြင်များပေါ်တွင် ထုတ်ယူထားသော dataset တန်ဖိုးများကို ပျမ်းမျှတွက်ပေးပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input mesh layer** (**ထည့်သွင်းအသုံးပြုသော mesh layer**)
     - ``INPUT``
     - [mesh]
     - Data ထုတ်ယူမည့် mesh layer
   * - **Dataset groups** (**Dataset အုပ်စုများ**)
     - ``DATASET_GROUPS``
     - [layer] [list]
     - Dataset အုပ်စုများ
   * - **Dataset time** (**Dataset အချိန်**)
     - ``DATASET_TIME``
     - [datetime]
     - လုပ်ဆောင်မည့် အချိန်အပိုင်းအခြား

       * 0 --- Current canvas time (လက်ရှိ canvas အချိန်)
       * 1 --- Defined date/time (သတ်မှတ်ထားသော ရက်စွဲ/အချိန်)
       * 2 --- Dataset group time step (Dataset အုပ်စု အချိန်အဆင့်)
   * - **Extent** (**နယ်ပယ်အကျယ်အဝန်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTENT``
     - [extent]
     - Data ကို လုပ်ဆောင်မည့် extent ကိုသတ်မှတ်ပါ။ အသုံးပြုနိုင်သော နည်းလမ်းများမှာ-

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Grid spacing** (**Grid အစိတ်အကျဲပမာဏ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``GRID_SPACING``
     - [number]

       Default: 10.0
     - အသုံးပြုမည့် နမူနာအမှတ်များအကြား အကျယ်
   * - **Output coordinate system** (**Output ကိုဩဒိနိတ်စနစ်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``CRS_OUTPUT``
     - [crs]
     - Output တွင်သတ်မှတ်ရန် ကိုဩဒိနိတ်စနစ်
   * - **Export vector option** (**Vector ရွေးချယ်စရာများကို ထုတ်ယူခြင်း**)
     - ``VECTOR_OPTION``
     - [enumeration]
     - Vector တန်ဖိုး ထုတ်ယူခြင်း၏ ကိုဩဒိနိတ်အမျိုးအစား

       * 0 --- Cartesian (x,y)
       * 1 --- Polar (ပြင်းအားပမာဏ ၊ ဒီဂရီ)
       * 2 --- Cartesian နှင့် polar
   * - **Output vector layer**
     - ``OUTPUT``
     - [vector: point]

       Default: ``[Create temporary layer] ([ယာယီ layer ဖန်တီးခြင်း])``
     - Output file ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output vector layer**
     - ``OUTPUT``
     - [vector: point]
     - ထပ်နေသော မျက်နှာပြင် မှတွက်ထုတ်ထားသော dataset တန်ဖိုးများဖြင့် output vector point layer

Python code
............

**Algorithm ID**: ``native:exportmeshongrid``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisexportmeshvertices:

Export mesh vertices (Mesh မျဉ်းအဆစ်များကိုထုတ်ယူခြင်း)
--------------------------------------------------------

Mesh layer တစ်ခု၏ မျဉ်းအဆစ် (vertex) များကို point vector layer တစ်ခုသို့ ထုတ်ယူပေးပြီး မျဉ်းအဆစ် (vertex) များပေါ်ရှိ dataset တန်ဖိုးများကို attribute တန်ဖိုးများအဖြစ်ထားရှိပေးပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input mesh layer** (**ထည့်သွင်းအသုံးပြုသော mesh layer**)
     - ``INPUT``
     - [mesh]
     - Data ထုတ်ယူမည့် mesh layer
   * - **Dataset groups** (**Dataset အုပ်စုများ**)
     - ``DATASET_GROUPS``
     - [layer] [list]
     - Dataset အုပ်စုများ
   * - **Dataset time** (**Dataset အချိန်**)
     - ``DATASET_TIME``
     - [datetime]
     - လုပ်ဆောင်မည့် အချိန်အပိုင်းအခြား

       * 0 --- Current canvas time (လက်ရှိ canvas အချိန်)
       * 1 --- Defined date/time (သတ်မှတ်ထားသော ရက်စွဲ/အချိန်)
       * 2 --- Dataset group time step (Dataset အုပ်စု အချိန်အဆင့်)
   * - **Output coordinate system**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``CRS_OUTPUT``
     - [crs]
     - Output တွင်သတ်မှတ်ရန် ကိုဩဒိနိတ်စနစ်
   * - **Export vector option** (**Vector ရွေးချယ်စရာများကို ထုတ်ယူခြင်း**)
     - ``VECTOR_OPTION``
     - [enumeration]
     - Vector တန်ဖိုး ထုတ်ယူခြင်း၏ ကိုဩဒိနိတ်အမျိုးအစား

       * 0 --- Cartesian (x,y)
       * 1 --- Polar (ပြင်းအားပမာဏ ၊ ဒီဂရီ)
       * 2 --- Cartesian နှင့် polar
   * - **Output vector layer**
     - ``OUTPUT``
     - [vector: point]

       Default: ``[Create temporary layer] ([ယာယီ layer ဖန်တီးခြင်း])``
     - Output file ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output vector layer**
     - ``OUTPUT``
     - [vector: point]
     - ဆက်စပ် dataset တန်ဖိုးများဖြင့် input mesh layer ၏ vertex များပါဝင်သော output vector point layer

Python code
............

**Algorithm ID**: ``native:exportmeshvertices``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgismeshexporttimeseries:

Export time series values from points of a mesh dataset (Mesh dataset တစ်ခု၏ point များမှ အချိန်ကိန်းစဉ်အချက်အလက် တန်ဖိုးများကို ထုတ်ယူခြင်း)
----------------------------------------------------------------------------------------------------------------------------------------------

Vector layer တစ်ခုထဲတွင် ပါဝင်သော point များမှ mesh dataset တစ်ခု၏ time series (အချိန်ကိန်းစဉ်အချက်အလက်) တန်ဖိုးများကိုဆွဲထုတ်ပေးပါသည်။


Time step (အချိန်အဆင့်) ကို ၎င်း၏မူရင်းတန်ဖိုး (0 နာရီ) တွင်ထားလျှင် အသုံးပြုသော time step သည် ဦးဆုံးရွေးချယ်ထားသော dataset အုပ်စု၏ ပထမဆုံး dataset နှစ်ခုထဲမှ တစ်ခုဖြစ်ပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input mesh layer** (**ထည့်သွင်းအသုံးပြုသော mesh layer**)
     - ``INPUT``
     - [mesh]
     - Data ဆွဲထုတ်ယူမည့် mesh layer
   * - **Dataset groups** (**Dataset အုပ်စုများ**)
     - ``DATASET_GROUPS``
     - [layer] [list]
     - Dataset အုပ်စုများ
   * - **Starting time**
     - ``STARTING_TIME``
     - [datetime]
     - လုပ်ဆောင်မည့် အချိန်အပိုင်းအခြား၏ အစ

       * 0 --- Current canvas time (လက်ရှိ canvas အချိန်)
       * 1 --- Defined date/time (သတ်မှတ်ထားသော ရက်စွဲ/အချိန်)
       * 2 --- Dataset group time step (Dataset အုပ်စု အချိန်အဆင့်)
   * - **Finishing time** (**ပြီးဆုံးသည့်အချိန်**)
     - ``FINISHING_TIME``
     - [datetime]
     - လုပ်ဆောင်မည့် အချိန်အပိုင်းအခြား၏အဆုံး

       * 0 --- Current canvas time (လက်ရှိ canvas အချိန်)
       * 1 --- Defined date/time (သတ်မှတ်ထားသော ရက်စွဲ/အချိန်)
       * 2 --- Dataset group time step (Dataset အုပ်စု အချိန်အဆင့်)
   * - **Time step (hours)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``TIME_STEP``
     - [number]

       Default: 0
     - ကပ်လျှက်ရှိသော အဆင့်နှစ်ခုကြားမှ အချိန်ကို ဆွဲထုတ်ပေးပါသည်။ ပထမဆုံးရွေးချယ်ထားသော dataset အုပ်စု၏ အချိန်အဆင့် ကိုအသုံးပြုရန် ``0`` အတိုင်းထားရှိပါ။
   * - **Points for data export** (**Data ထုတ်ယူခြင်းအတွက် point များ**)
     - ``INPUT_POINTS``
     - [vector: point]

     - Dataset mesh မှ data များဆွဲထုတ်မည့် point များပါဝင်သော vector layer
   * - **Digits count for coordinates** (**ကိုဩဒိနိတ်များအတွက် ဂဏန်းအရေအတွက်**)
     - ``COORDINATES_DIGITS``
     - [number]
     - ကိုဩဒိနိတ် တန်ဖိုးများကို ဒဿမနေရာထားရှိမည့် ဂဏန်းအရေအတွက်	 

       Default: 2
   * - **Digits count for dataset value**  (**Dataset တန်ဖိုးများအတွက် ဂဏန်းအရေအတွက်**)
     - ``DATASET_DIGITS``
     - [number]

       Default: 2
     - Dataset တန်ဖိုးများကို ဒဿမနေရာထားရှိမည့် ဂဏန်းအရေအတွက်
   * - **Exported data CSV file** (**ထုတ်ထားသော CSV file အမျိုးအစား data**)
     - ``OUTPUT``
     - [file]

       Default: ``[Save to temporary file]``
     - Output file ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Exported data CSV file** (**ထုတ်ယူထားသော data CSV file**)
     - ``OUTPUT``
     - [file]
     - ထပ်နေသော point feature များရှိ mesh dataset time series တန်ဖိုးများပါဝင်သော :file:`.CSV` file

Python code
............

**Algorithm ID**: ``native:meshexporttimeseries``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgismeshrasterize:

Rasterize mesh dataset (Mesh dataset ကို raster ပြောင်းလဲခြင်း)
----------------------------------------------------------------

Mesh dataset တစ်ခုမှ raster layer တစ်ခုဖန်တီးပေးပါသည်။

ထုထည် (သုံးဘက်မြင် ထပ်ထားသော dataset တန်ဖိုးများ) ပေါ်ရှိ data အတွက် :ref:`the mesh layer properties <mesh_stacked_averaging>` (Default သည် အဆင့်များစွာကို ပျမ်းမျှလုပ်သော နည်းလမ်း ဖြစ်သည်) ထဲတွင် သတ်မှတ်ထားသော နည်းလမ်းကိုအသုံးပြုပြီး မျက်နှာပြင်များပေါ်တွင် ထုတ်ယူထားသော dataset တန်ဖိုးများကို ပျမ်းမျှတွက်ပေးပါသည်။ 1D (၁ဘက်မြင်) mesh များအတွက် မလုပ်ဆောင်နိုင်ပါ။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input mesh layer** (**ထည့်သွင်းအသုံးပြုသော mesh layer**)
     - ``INPUT``
     - [mesh]
     - Data ထုတ်ယူမည့် mesh layer
   * - **Dataset groups** (**Dataset အုပ်စုများ**)
     - ``DATASET_GROUPS``
     - [layer] [list]
     - Dataset အုပ်စုများ	 
   * - **Dataset time** (**Dataset အချိန်**)
     - ``DATASET_TIME``
     - [datetime]

     - လုပ်ဆောင်မည့် အချိန်အပိုင်းအခြား

       * 0 --- Current canvas time (လက်ရှိ canvas အချိန်)
       * 1 --- Defined date/time (သတ်မှတ်ထားသော ရက်စွဲ/အချိန်)
       * 2 --- Dataset group time step (Dataset အုပ်စုအချိန် အဆင့်)
   * - **Extent** (**နယ်ပယ်အကျယ်အဝန်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTENT``
     - [extent]
     - Data ကိုလုပ်ဆောင်မည့် extent ကိုသတ်မှတ်ပါ။ အသုံးပြုနိုင်သော နည်းလမ်းများမှာ-

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Pixel size** (**Pixel အရွယ်အစား**)
     - ``PIXEL_SIZE``
     - [number]

       Default: 1.0
     - Output raster layer ၏ pixel အရွယ်အစား
   * - **Output coordinate system** (**Output ကိုဩဒိနိတ်စနစ်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``CRS_OUTPUT``
     - [crs]
     - Output တွင်သတ်မှတ်မည့် ကိုဩဒိနိတ်စနစ်
   * - **Output raster layer**
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file ထဲတွင်သိမ်းဆည်းပါ])``
     - Output file ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output raster layer**
     - ``OUTPUT``
     - [raster]
     - Mesh layer မှတွက်ထုတ်ထားသော dataset တန်ဖိုးများပါဝင်သော output raster layer

Python code
............

**Algorithm ID**: ``native:meshrasterize``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgistinmeshcreation:

TIN mesh creation (TIN mesh ဖန်တီးခြင်း)
-----------------------------------------

Vector layer များမှ TIN mesh layer တစ်ခုကိုဖန်တီးပေးပါသည်။ Delaunay triangulation ကိုအသုံးပြုပြီး TIN mesh ကိုဖန်တီးပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layers** (**ထည့်သွင်းအသုံးပြုသော layer များ**)
     - ``SOURCE_DATA``
     - [vector: any] [list]
     - Mesh layer ကိုဖန်တီးရန် ပေါင်းစည်းရမည့် vector layer များ
   * - **Vector layer**
     - GUI ONLY
     - [vector: any] [list]
     - Mesh layer ကိုဖန်တီးရန် ပေါင်းစည်းရမည့် vector layer များ ရွေးချယ်ပေးသည့်အရာ (selector)
   * - **Value on vertex** (**မျဉ်းအဆစ်ပေါ်ရှိတန်ဖိုး**)
     - GUI ONLY
     - [tablefield: any]
     - ရွေးချယ်ထားသော layer မှ အသုံးပြုမည့် field ရွေးချယ်ပေးသည့်အရာ။ မျဉ်းအဆစ်တစ်ခုချင်းစီတွင် ၎င်း၏မူရင်း feature ၏သက်ဆိုင်ရာတန်ဖိုးကို သတ်မှတ်ပေးပါသည်။
   * - **Use Z-coordinate for value on vertex** (**မျဉ်းအဆစ်ပေါ်ရှိ တန်ဖိုးအတွက် အမြင့် Z-coordinate ကိုအသုံးပြုခြင်း**)
     - GUI ONLY
     - [boolean]

       Default: False
     - အမှန် (TRUE) ကိုထားလျှင် vector layer point များ သို့မဟုတ် polygons/lines မျဉ်းအဆစ်များ၏ အမြင့် Z တန်ဖိုးများကို vertex mesh layer ၏ အမြင့် Z တန်ဖိုးကိုသတ်မှတ်ရန်အတွက် အသုံးပြုပါလိမ့်သည်။ Input layer များသည် သုံးဖက်မြင် (3D) များဖြစ်မှသာ အသုံးပြုနိုင်ပါသည်။
   * - **Output format**
     - ``MESH_FORMAT``
     - [enumeration]

       Default: 2DM
     - ဖန်တီးထားသော layer ၏ output format

       * 0 --- 2DM
       * 1 --- SELAFIN
       * 2 --- PLY
       * 3 --- Ugrid
   * - **Output coordinate system** (**Output ကိုဩဒိနိတ်စနစ်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``CRS_OUTPUT``
     - [crs]
     - Output တွင်သတ်မှတ်မည့် ကိုဩဒိနိတ်စနစ်
   * - **Output file**
     - ``OUTPUT_MESH``
     - [mesh]

       Default: ``[Save to temporary file] ([ယာယီ file ထဲတွင်သိမ်းဆည်းပါ])``
     - Output file ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output file**
     - ``OUTPUT_MESH``
     - [mesh]
     - Vector layer များမှ တွက်ထုတ်ထားသော dataset တန်ဖိုးများပါဝင်သော output mesh layer

Python code
............

**Algorithm ID**: ``native:tinmeshcreation``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**

