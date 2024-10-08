Vector geometry (Vector ဂျီဩမေတြီ)
===================================

.. only:: html

   .. contents::
      :local:
      :depth: 1
      :class: toc-columns


.. _qgisexportaddgeometrycolumns:

Add geometry attributes (ဂျီဩမေတြီ အချက်အလက်များ ထည့်ခြင်း)
------------------------------------------------------------

Vector layer တစ်ခုအတွင်းမှ feature များ၏ ဂျီဩမေတြီ ဂုဏ်သတ္တိများကိုတွက်ချက်ပြီး ၎င်းတို့ကို output layer ထဲတွင်ပါဝင်အောင်လုပ်ပေးပါသည်။

၎င်းသည် input layer တွင်ပါဝင်သော အကြောင်းအရာများနှင့်တူသည့် vector layer အသစ်တစ်ခုကိုဖန်တီးပေးပါသည်။ သို့သော် ထပ်ပေါင်းအချက်အလက်များနှင့် ရွေးချယ်ထားသော CRS တစ်ခုပေါ်မူတည်ပြီး ဂျီဩမေတြီဆိုင်ရာ တိုင်းတာမှုများ ပါဝင်လာပါသည်။

ဇယားတွင်ထည့်ပေါင်းမည့်အချက်အလက်များသည် ဂျီဩမေတြီ အမျိုးအစားနှင့် input layer ၏ အရွယ်အစား (အကျယ်) ပေါ်မူတည်ပါသည် -

* **point** layer များအတွက် - X (``xcoord``) ၊ Y (``ycoord``) ၊ Z (``zcoord``) ကိုဩဒိနိတ်များနှင့် (``mvalue``) အတွက် M တန်ဖိုး။
* **line** layer များအတွက် - ``length`` (အလျား) နှင့် LineString နှင့် CompoundCurve ဂျီဩမေတြီ အမျိုးအစားအတွက် feature ``sinuosity`` နှင့် အဖြောင့်အကွာအဝေး (``straightdis``)
* **polygon** layer များအတွက် - ``perimeter`` (ပတ်လည်အနား) နှင့် ``area`` (ဧရိယာ)

**Default menu** - :menuselection:`Vector --> Geometry Tools`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Calculate using** **(အသုံးပြုပြီး တွက်ချက်ခြင်း)**
     - ``CALC_METHOD``
     - [enumeration]

       Default: 0
     - ဂျီဩမေတြီ ဂုဏ်သတ္တိများအတွက် အသုံးပြုမည့် တွက်ချက်မှု parameter များ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       * 0 --- Layer CRS
       * 1 --- Project CRS
       * 2 --- Ellipsoidal

   * - **Added geom info** **(ထည့်သွင်းထားသော geom သတင်းအချက်အလက်များ)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output (ဂျီဩမေတြီ ပါသော input မိတ္တူ) layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**


Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Added geom info** (**ထည့်သွင်းထားသော geom သတင်းအချက်အလက်များ**)
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ဂျီဩမေတြီ field များ ထပ်ဖြည့်ထားသော input vector layer ၏ မိတ္တူ

Python code
............

**Algorithm ID**: ``qgis:exportaddgeometrycolumns``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisaffinetransform:

Affine transform (ပုံမပျက်အသွင်ပြောင်းခြင်း)
---------------------------------------------

Layer ဂျီဩမေတြီ များတွင် ပုံမပျက်အသွင်ပြောင်းခြင်း ကိုအသုံးပြုပါသည်။ ပုံမပျက်အသွင်ပြောင်းခြင်းတွင် နေရာရွှေ့ပြောင်းခြင်း (translation) ၊ စကေးကိုက်ချိန်ညှိခြင်း (scaling) နှင့် လှည့်ခြင်း (rotation) တို့ ပါဝင်နိုင်ပါသည်။ လုပ်ဆောင်မှုများကို ယခုအစီအစဉ်အတိုင်း လုပ်ဆောင်ပါသည် - စကေးကိုက်ချိန်ညှိခြင်း၊ လှည့်ခြင်း နှင့် နေရာရွှေ့ပြောင်းခြင်း။

အမြင့် Z နှင့် အကွာအဝေး M တန်ဖိုးများ (ပါခဲ့လျှင်) ကို နေရာရွှေ့ပြောင်းပြီး စကေးကိုက်ချိန်ညှိနိုင်ပါသည်။

.. figure:: img/affinetransform.png
   :align: center

   ပုံမပျက်အသွင်ပြောင်းခြင်း (နေရာရွှေ့ပြောင်းခြင်း) မလုပ်ခင် (ဘယ်ဘက်) နှင့် လုပ်ဆောင်ပြီး (ညာဘက်) Vector point layer (အစိမ်းရောင်အစက်များ) 

|checkbox| သည် point၊ line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာမှာတင် မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgistranslategeometry` 

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Translation (x-axis)** **(နေရာရွှေ့ပြောင်းခြင်း (x ဝင်ရိုး))**
     - ``DELTA_X``
     - [number |dataDefine|]

       Default: 0
     - X ဝင်ရိုးပေါ်တွင်အသုံးပြုရန် နေရာအရွှေ့။
   * - **Translation (y-axis)** **(နေရာရွှေ့ပြောင်းခြင်း (y ဝင်ရိုး))**
     - ``DELTA_Y``
     - [number |dataDefine|]

       Default: 0
     - Y ဝင်ရိုးပေါ်တွင်အသုံးပြုရန် နေရာအရွှေ့။
   * - **Translation (z-axis)** **(နေရာရွှေ့ပြောင်းခြင်း (z ဝင်ရိုး))**
     - ``DELTA_Z``
     - [number |dataDefine|]

       Default: 0
     - Z ဝင်ရိုးပေါ်တွင်အသုံးပြုရန် နေရာအရွှေ့။	 
   * - **Translation (m-values)** **နေရာရွှေ့ပြောင်းခြင်း (m တန်ဖိုးများ))**
     - ``DELTA_M``
     - [number |dataDefine|]

       Default: 0
     - M တန်ဖိုးများပေါ်တွင် အသုံးပြုမည့် offset (အရွေ့)။
   * - **Scale factor (x-axis)** **(စကေး factor (x ဝင်ရိုး))**
     - ``SCALE_X``
     - [number |dataDefine|]

       Default: 1
     - X ဝင်ရိုးပေါ်တွင်အသုံးပြုမည့် scaling တန်ဖိုး (ချဲ့ခြင်း သို့မဟုတ် ကျုံ့ခြင်း)။
   * - **Scale factor (y-axis)** **(စကေး factor (y ဝင်ရိုး))**
     - ``SCALE_Y``
     - [number |dataDefine|]

       Default: 1
     - Y ဝင်ရိုးပေါ်တွင်အသုံးပြုမည့် scaling တန်ဖိုး (ချဲ့ခြင်း သို့မဟုတ် ကျုံ့ခြင်း)။
   * - **Scale factor (z-axis)** **(စကေး factor (z ဝင်ရိုး))**
     - ``SCALE_Z``
     - [number |dataDefine|]

       Default: 1
     - Z ဝင်ရိုးပေါ်တွင်အသုံးပြုမည့် scaling တန်ဖိုး (ချဲ့ခြင်း သို့မဟုတ် ကျုံ့ခြင်း)။
   * - **Scale factor (m-values)** **(စကေး factor (m တန်ဖိုးများ))**
     - ``SCALE_M``
     - [number |dataDefine|]

       Default: 1
     - M တန်ဖိုးများပေါ်တွင်အသုံးပြုမည့် scaling တန်ဖိုး (ချဲ့ခြင်း သို့မဟုတ် ကျုံ့ခြင်း)။
   * - **Rotation around z-axis (degrees counter-clockwise)** **(Z ဝင်ရိုးပတ်လည် အလှည့် (ဒီဂရီဖြင့် နာရီလက်တံပြောင်းပြန်))**
     - ``ROTATION_Z``
     - [number |dataDefine|]

       Default: 0
     - ဒီဂရီဖြင့် လှည့်ထောင့်။	 
   * - **Transformed** **(အသွင်ပြောင်းထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**
   
Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Transformed** **(အသွင်ပြောင်းထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - အသွင်ပြောင်းထားပြီးသော output vector layer

Python code
............

**Algorithm ID**: ``native:affinetransform``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisaggregate:

Aggregate (စုပေါင်းခြင်း)
--------------------------

Vector သို့မဟုတ် ဇယား layer တစ်ခုကိုယူပြီး ``group by`` expression တစ်ခုဖြင့် feature များကို aggregate (စုပေါင်း) ခြင်းဖြင့် layer အသစ်တစ်ခုကို ဖန်တီးပေးပါသည်။

``group by`` expression မှ ထုတ်ပေးသော တန်ဖိုးတူ feature များကို အုပ်စုတစ်စုတည်း အဖြစ်စုပေါင်းပေးပါသည်။

``group by`` parameter ထဲတွင် ကိန်းသေတစ်ခုကိုအသုံးပြုပြီး ရင်းမြစ် feature အားလုံးကို အုပ်စုတစ်ခုတည်းအဖြစ် ပေါင်းစည်းနိုင်ပါသည်။ ဥပမာ- NULL။

Arrary function ကိုအသုံးပြုပြီး field များစွာဖြင့် feature များကိုအုပ်စုဖွဲ့ခြင်းကိုလည်း ပြုလုပ်နိုင်ပါသည်။ ဥပမာ- Array("Field1"၊ "Field2")

အုပ်စုတစ်ခုချင်းစီအတွက် ဂျီဩမေတြီများ (ရှိလျှင်) ကို အပိုင်းများစွာပါဝင်သော (multipart) ဂျီဩမေတြီ တစ်ခုအဖြစ် ပေါင်းစည်းနိုင်ပါသည်။ အသုံးပြုထားသော ပေါင်းစည်းမှု သတ်မှတ်ချက်တစ်ခုချင်းစီပေါ် မူတည်ပြီး output အချက်အလက်များကို တွက်ချက်ပါသည်။

ယခု algorithm သည် QGIS Expression engine ၏ default :ref:`aggregates function <aggregates_function>` များကို အသုံးပြုနိုင်အောင် လုပ်ဆောင်ပေးပါသည်။

.. seealso:: :ref:`qgiscollect` ၊ :ref:`qgisdissolve`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Group by expression** **(Expression ဖြင့် အုပ်စုဖွဲ့ခြင်း)**
     - ``GROUP_BY``
     - [tablefield: any]

       Default: 'NULL'
     - အုပ်စုဖွဲ့မည့် field ကိုရွေးချယ်ပါ။ *NULL* ဖြစ်နေလျှင် feature အားလုံးကိုအုပ်စုဖွဲ့ပါလိမ့်မည်။
   * - **Aggregates** **(စုပေါင်းခြင်း)**
     - ``AGGREGATES``
     - [list]
     - Output layer field အဓိပ္ပါယ်သတ်မှတ်ချက်များ၏ စာရင်း။ Field အဓိပ္ပါယ်သတ်မှတ်ချက်တစ်ခု၏ ဥပမာ-

       *{'aggregate': 'sum', 'delimiter': ',', 'input': ' $area',
       'length': 10, 'name': 'totarea', 'precision': 0, 'type': 6}*

       Default အားဖြင့် စာရင်းတွင် input layer ၏ field များအားလုံးပါဝင်ပါသည်။ GUI ထဲတွင် ၎င်း field များနှင့် ၎င်းတို့၏ အဓိပ္ပါယ်သတ်မှတ်ချက်များကို ပြင်ဆင်နိုင်ပြီး အောက်ပါတို့ကိုလည်း လုပ်ဆောင်နိင်ပါသည် - 

       * Field အသစ်ခုပေါင်းထည့်ရန် |newAttribute| ခလုတ်ကိုနှိပ်ပါ။
       * ရွေးချယ်ထားသော field ကိုဖျက်ရန် |deleteAttribute| ကိုနှိပ်ပါ။
       * Field များ၏ အထက်အောက် အစီအစဉ်ကို ပြောင်းလဲရန် |arrowUp| နှင့် |arrowDown| ကိုအသုံးပြုပါ။
       * မူရင်းအတိုင်း ပြန်ပြောင်းရန် (input layer ၏ field များ) |clearText| ကိုနှိပ်ပါ။

       သတင်းအချက်အလက်ရယူလိုသော field တစ်ခုချင်းစီအတွက် အောက်ပါတို့ကိုသတ်မှတ်ပေးရန် လိုအပ်ပါသည် -

       ``Input expression`` [expression] (``input``)
         Input layer မှ field သို့မဟုတ် expresssion

       ``Aggregate function`` [enumeration] (``aggregate``)
         စုပေါင်းတန်ဖိုးကို ပြန်ထုတ်ပေးရန်အတွက် input expression တွင်အသုံးပြုမည့် :ref:`Function <aggregates_function>`

         Default- *concatenate* (စာသား data အမျိုးအစားအတွက်)၊ *sum* (ကိန်းဂဏန်း data အမျိုးအစားအတွက်)

       ``Delimiter`` [string] (``delimiter``)
         စုပေါင်းတန်ဖိုးများကို ခွဲခြားထားရန် စာသား။ ဥပမာ- concatenation အသုံးပြုခြင်းတွင်။

         Default- *,*
 
       ``Output field name`` [string] (``name``)
         Output layer ထဲရှိ စုပေါင်းထားသော field ၏အမည်။ Default အားဖြင့် input field အမည်ကိုသာ ဆက်သုံးပါသည်။
 
       ``Type`` [enumeration] (``type``)
         Output field ၏ data အမျိုးအစား။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -	   

         * 1 --- Boolean (မှန်/မှား)
         * 2 --- Integer (ကိန်းပြည့်)
         * 4 --- Integer64 (ကိန်းပြည့် 64)
         * 6 --- Double (ဒဿမကိန်း)
         * 10 --- String (စာသား)
         * 14 --- Date (ရက်စွဲ)
         * 16 --- DateTime (ရက်စွဲအချိန်)
 
       ``Length`` [number] (``length``)
         Output field ၏ အလျား (ထည့်သွင်းနိုင်သောစာလုံးအရေအတွက်)	   
 
       ``Precision`` [number] (``precision``)
         Output field ၏ တိကျမှု (ဒဿမကိန်းအရေအတွက်)	   

   * - **Load fields from layer** **(Layer မှ ထည့်သွင်းအသုံးပြုသော field များ)**
     - GUI ထဲတွင်သာ
     - [vector: any]
     - အခြား layer မှ field များကို ခေါ်ယူထည့်သွင်းနိုင်ပြီး ၎င်းတို့ကို စုပေါင်းခြင်း အတွက်အသုံးပြုနိုင်ပါသည်။
   * - **Aggregated** **(စုပေါင်းထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - စုပေါင်းထားသော output layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Aggregated** **(စုပေါင်းထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - စုပေါင်းထားပြီးသောတန်ဖိုးများပါဝင်သော ဂျီဩမေတြီ များစွာရှိသော (Multigeometry) vector layer

Python code
............

**Algorithm ID**: ``native:aggregate``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisboundary:

Boundary (နယ်နိမိတ်)
---------------------

Input ဂျီဩမေတြီ များ၏ ပေါင်းစပ်နယ်နိမိတ်၏ အပိတ်ကိုပြန်ထုတ်ပေးပါသည် (ဥပမာ- ဂျီဩမေတြီ ၏ Topology ဆိုင်ရာနယ်နိမိတ်)

Polygon နှင့် line layer များအတွက်သာ။

**Polygon ဂျီဩမေတြီများ** အတွက် နယ်နိမိတ် တွင် polygon အဝန်းအဝိုင်းဖြစ်စေသော line များအားလုံးပါဝင်ပါသည်။

.. figure:: img/boundary_polygon.png
   :align: center

   ရင်းမြစ် polygon layer ၏ နယ်နိမိတ်များ (အနက်ရောင် dash line)

**Line ဂျီဩမေတြီများ** အတွက် နယ်နိမိတ်များသည် ၎င်းတို့၏အဆုံးသတ် point များဖြစ်ပါသည်။

.. figure:: img/boundary_lines.png
   :align: center

   Line များအတွက် boundary layer (အနီရောင် point များ)။ အဝါရောင်များသည် ရွေးချယ်ထားသော feature တစ်ခုဖြစ်ပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line, polygon]
     - ထည့်သွင်းအသုံးပြုသော line သို့မဟုတ် polygon vector layer
   * - **Boundary** **(နယ်နိမိတ်)**
     - ``OUTPUT``
     - [vector: point, line]

       Default: ``[Create temporary layer]``
     - Output (boundary) layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Boundary** **(နယ်နိမိတ်)**
     - ``OUTPUT``
     - [vector: point, line]
     - Input layer မှ နယ်နိမိတ်များ (line အတွက် point၊ နှင့် polygon အတွက် line)

Python code
............

**Algorithm ID**: ``native:boundary``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisboundingboxes:

Bounding boxes (စတုဂံပုံ အကျယ်အဝန်းနယ် box များ)
-------------------------------------------------

Input layer တစ်ခုထဲရှိ feature တစ်ခုချင်းစီ၏ bounding box (envelope) ကိုတွက်ချက်ပေးပါသည်။ Polygon နှင့် line ဂျီဩမေတြီ များကိုလုပ်ဆောင်နိုင်ပါသည်။

.. figure:: img/bounding_box.png
   :align: center

   အနက်ရောင် line များသည် Polygon feature တစ်ခုချင်းစီ၏ bounding box များကို ကိုယ်စားပြုပါသည်

|checkbox| သည် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgisminimumboundinggeometry`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line, polygon]
     - ထည့်သွင်းအသုံးပြုသော line သို့မဟုတ် polygon vector layer
   * - **Bounds** **(ဘောင်များ)**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output (bounding box) layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Bounds**
     - ``OUTPUT``
     - [vector: polygon]
     - Input layer ၏ bounding box များ

Python code
............

**Algorithm ID**: ``native:boundingboxes``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisbuffer:

Buffer (ကြားခံဇုံ)
-------------------

ပုံသေအကွာအဝေးတစ်ခု သို့မဟုတ် data ဖြင့်သတ်မှတ်ထားသောအကွာအဝေးတစ်ခုကိုအသုံးပြုပြီး input layer ထဲရှိ feature များအားလုံးအတွက် buffer ဧရိယာတစ်ခုကို ဖန်တီးပေးပါသည်။

Polygon input layer များအတွက် အနှုတ်တန်ဖိုး အကွာအဝေးကိုအသုံးပြုနိုင်ပါသည်။ ထိုသို့အသုံးပြုလျှင် buffer အတွင်းဘက်တွင် ဖြစ်ပေါ်ပြီး ပိုသေးသော polygon တစ်ခုရလာပါမည်။

.. figure:: img/buffer.png
   :align: center

   အပေါင်းတန်ဖိုးဖြင့် point ၊ line ၊ polygon တို့၏ buffer (အဝါရောင်) နှင့် အနှုတ်တန်ဖိုးဖြင့် buffer လုပ်ထားသော polygon

|checkbox| သည် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

**Default menu**- :menuselection:`Vector --> Geoprocessing Tools`

.. seealso:: :ref:`qgisvariabledistancebuffer` ၊
   :ref:`qgismultiringconstantbuffer` ၊ :ref:`qgisbufferbym`

Parameters (Parameter များ)
............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Distance** **(အကွာအဝေး)**
     - ``DISTANCE``
     - [number |dataDefine|]

       Default: 10.0
     - Feature တစ်ခုချင်းစီ၏ နယ်နိမိတ်မှ buffer အကွာအဝေး။ အချင်းဝက်ကိုတွက်ထုတ်မည့် field တစ်ခုကိုရွေးချယ်ရန် ညာဘက်ရှိ Data Defined (Data ဖြင့်သတ်မှတ်သော) ခလုတ်ကိုအသုံးပြုနိုင်ပါသည်။ ဤနည်းလမ်းကိုအသုံးပြုပြီး feature တစ်ခုချင်းစီအတွက် အချင်းဝက်အမျိုမျိုးကို ရရှိနိုင်ပါသည် (:ref:`qgisvariabledistancebuffer` ကိုကြည့်ပါ)။
   * - **Segments** **(အမှတ်နှစ်ခုကြားကမျဉ်းပိုင်းများ)**
     - ``SEGMENTS``
     - [number]

       Default: 5
     - လုံးဝန်းသော offset များကိုဖန်တီးသောအခါ စက်ဝိုင်းလေးပုံတစ်ပုံ ကိုခန့်မှန်းရန်အတွက် အသုံးပြုသော line segment အရေအတွက်ကို ထိန်းချုပ်ပေးပါသည်။
   * - **End cap style** **(အဆုံးသတ် ထိပ်အဖုံး style)**
     - ``END_CAP_STYLE``
     - [enumeration]

       Default: 0
     - Buffer ထဲတွင် မျဉ်းအဆုံးသတ်များကို မည်သို့ဖြစ်စေမည်ဆိုသည်ကို ထိန်းချုပ်ပေးပါသည်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       * 0 --- Round (လုံးဝန်းသော)
       * 1 --- Flat (ပြားသော)
       * 2 --- Square (လေးထောင့်ဆန်သော)

       .. figure:: img/buffer_cap_style.png
          :align: center
          :width: 100%

          လုံးဝန်းသော၊ ပြားသော၊ လေးထောင့်ဆန်သော အဆုံးသတ် style များ
   * - **Join style** **(အဆက် style)**
     - ``JOIN_STYLE``
     - [enumeration]

       Default: 0
     - Line တစ်ခု၏ ထောင့်များကို offset ဖန်တီးသောအခါ လုံးဝန်းသော (round)၊ စောင်းတိ (miter) သို့မဟုတ် စောင်းသတ် (bevel) နည်းလမ်းများကို အသုံးပြု/မပြုကို သတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာ နည်းလမ်းများမှာ -

       * 0 --- Round (လုံးဝန်းသော)
       * 1 --- Miter (စောင်းတိ)
       * 2 --- Bevel (စောင်းသတ်)

       .. figure:: img/buffer_join_style.png
          :align: center
          :width: 100%

          လုံးဝန်းသော (round)၊ စောင်းတိ (miter) နှင့် စောင်းသတ် (bevel) အဆက် style များ
   * - **Miter limit** **(Miter ကန့်သတ်ချက်)**
     - ``MITER_LIMIT``
     - [number]

       Default: 2.0
     - Offset အကွာအဝေး၏ factor တစ်ခုအဖြစ် (miter အဆက် style တွင်သာ အသုံးပြုနိုင်ပါသည်) miter ဆက်နည်းကို ဖန်တီးသောအခါ အသုံးပြုမည့် offset ဂျီဩမေတြီ မှ အများဆုံးအကွာအဝေးကို သတ်မှတ်ပေးပါသည်။ အနည်းဆုံး- 1.0
              
       .. figure:: img/buffer_miter_limit.png
          :align: center
          :width: 100%
         
          ကန့်သတ်မှု 2 ဖြင့် 10m buffer တစ်ခုနှင့် ကန့်သတ်မှု 1 ဖြင့် 10m buffer တစ်ခု
   * - **Dissolve result** **(ပေါင်းစည်းထားသော ရလာဒ်)**
     - ``DISSOLVE``
     - [boolean]

       Default: False
     - နောက်ဆုံးရလာဒ် buffer ကို ပေါင်းစည်းပေးပါသည်။ ``True`` (အမှန်ခြစ်ထားလျှင်) ဖြစ်လျှင် ထပ်နေသော buffer များကို အစိတ်အပိုင်းများစွာပါဝင်သော (multipart) feature တစ်ခုအဖြစ် ပေါင်းစည်းပေးပါမည်။

       .. figure:: img/buffer_dissolve.png
          :align: center
          :width: 100%

          ပုံမှန် (အပိုင်းသုံးပိုင်းဖြစ်နေသော တစ်ခုချင်းကွဲနေသော feature များ -ဘယ်ဘက်)၊ ပေါင်းစည်းထားသော (အပိုင်းနှစ်ခုပါဝင်သော အစိတ်အပိုင်းများစွာပါဝင်သော feature -ညာဘက်)
   * - **Buffered** **(Buffer ပြုလုပ်ထားသော)**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output (buffer) layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Keep disjoint features separate** **(အဆက်ဖြုတ်ထားသော feature များကို သီးခြားခွဲထားခြင်း)**
     - ``SEPARATE_DISJOINT``
     - [boolean]

       Default: False
     - ``True`` (အမှန်ခြစ်ထားလျှင်) ကိုထားပြီး ပေါင်းစည်းခြင်းကို ရွေးချယ်ထားလျှင် ထပ်မနေသော သို့မဟုတ် ထိမနေသော feature များကို သီးခြား (ကွဲနေသော) feature များအဖြစ် ထုတ်ပေးပါမည်(အစိတ်အပိုင်းများစွာပါသော feature တစ်ခု၏ အပိုင်းများအစား ထုတ်ပေးပါသည်)။

       .. figure:: img/buffer_disjoint.png
          :align: center

          အစိတ်အပိုင်းတစ်ခုစီဖြစ်နေသော feature နှစ်ခုကို ရပါသည်

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Buffered** **(Buffer ပြုလုပ်ထားသော)**
     - ``OUTPUT``
     - [vector: polygon]
     - Output (buffer) polygon layer

Python code
............

**Algorithm ID**: ``native:buffer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiscentroids:

Centroids (အလယ်ဗဟိုမှတ်များ)
-----------------------------

Input layer ၏ ဂျီဩမေတြီများ၏ ဗဟိုမှတ်များကို ကိုယ်စားပြုသော အမှတ်များပါဝင်သော point layer အသစ်တစ်ခုကိုဖန်တီးပေးပါသည်။

ဗဟိုမှတ်သည် feature ၏ (အစိတ်အပိုင်းအားလုံး၏) ဘုံဗဟိုမှတ် ကိုကိုယ်စားပြုသော အမှတ်တစ်ခုဖြစ်ပါသည်။ ထို့ကြောင့် ၎င်းသည် feature နယ်နိမိတ်များ၏ အပြင်ဘက်တွင်လည်း ရှိနေနိုင်ပါသည်။ သို့သော် feature ၏ အစိတ်အပိုင်းတစ်ခုချင်းစီပေါ်မှ အမှတ်တစ်ခုလည်း ဖြစ်နိုင်ပါသည်။

Output layer ထဲရှိ အမှတ်များ၏ အချက်အလက်များသည် မူရင်း feature များနှင့် အတူတူပင် ဖြစ်ပါသည်။

.. figure:: img/centroids.png
   :align: center

   အနီရောင်ကြယ်များသည် input layer ၏ feature များ၏ ဗဟိုမှတ်များ ဖြစ်ပါသည်။

|checkbox| သည် point feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

**Default menu**- :menuselection:`Vector --> Geometry Tools`

.. seealso:: :ref:`qgispointonsurface`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Create centroid for each part** **(အစိတ်အပိုင်း တစ်ခုချင်းစီအတွက် ဗဟိုမှတ်ကိုဖန်တီးခြင်း)**
     - ``ALL_PARTS``
     - [boolean |dataDefine|]
       Default: False
     - True ကိုထားလျှင် (အမှန်ခြစ်ထားလျှင်) ဂျီဩမေတြီ၏ အစိတ်အပိုင်းတစ်ခုချင်းစီအတွက် ဗဟိုမှတ်တစ်ခုကို ဖန်တီးပေးပါမည်။
   * - **Centroids** **(ဗဟိုမှတ်များ)**
     - ``OUTPUT``
     - [vector: point]

       Default: ``[Create temporary layer]``
     - Output (centroid) layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Centroids** **(အလယ်ဗဟိုမှတ်များ)**
     - ``OUTPUT``
     - [vector: point]
     - Output point vector layer (အလယ်ဗဟိုမှတ်များ)

Python code
............

**Algorithm ID**: ``native:centroids``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgischeckvalidity:

Check validity (ဆီလျော်မှုကို စစ်ဆေးခြင်း)
-------------------------------------------

Vector layer တစ်ခု၏ ဂျီဩမေတြီများကို အမှားကင်းရှင်းပြီး ဆီလျော်မှုရှိ/မရှိ ကို စစ်ဆေးပေးပါသည်။ 

ဂျီဩမေတြီများကို အုပ်စု သုံးမျိုးခွဲခြားထားပြီး (အမှားကင်းရှင်းပြီး ဆီလျော်သော၊ အမှားမကင်းပဲ ဆီလျော်မှုမရှိသော နှင့် အမှား) အုပ်စုတစ်ခုချင်းစီအတွက် ၎င်း၏ feature များပါဝင်သော vector layer တစ်ခုကို ဖန်တီးပေးပါသည်-

* **Valid output (အမှားကင်းရှင်းပြီးဆီလျော်သော ရလာဒ်)** layer တွင် ဆီလျော်မှုရှိသော feature များသာပါဝင်ပါသည် (Topology ဆိုင်ရာ အမှားများမပါဝင်ပဲ)။
* **Invalid output (အမှားမကင်းပဲ ဆီလျော်မှုမရှိသော ရလာဒ်)** layer တွင် algorithm မှတွေ့ရှိသော အမှားမကင်းပဲ ဆီလျော်မှုမရှိသော feature များအားလုံးပါဝင်ပါသည်။
* **Error output (အမှား ရလာဒ်)** layer သည် အမှားမကင်းပဲ ဆီလျော်မှုမရှိသော feature များ မည်သည့်နေရာတွင် တွေ့ရှိသည်ကို ညွှန်ပြသော point layer တစ်ခုဖြစ်ပါသည်။

ဖန်တီးထားသော layer များ၏ attribute ဇယားတွင် အခြားသတင်းအချက်အလက်များ ပါဝင်ပါသည် (**အမှား** layer အတွက် "အသိပေးစာတို" ၊ **အမှားမကင်းပဲ ဆီလျော်မှုမရှိသော** layer အတွက် "FID" နှင့် "_errors" နှင့် **အမှားကင်းရှင်းပြီးဆီလျော်သော** layer အတွက် "FID" တစ်ခုတည်းသာ)-

ဖန်တီးထားသော vector layer တစ်ခုချင်းစီ၏ attribute ဇယား တွင် အခြားသတင်းအချက်အလက်များ ပါဝင်ပါသည် (တွေ့ရှိသော အမှားအရေအတွက်နှင့် အမှားအမျိုးအစားများ)-

.. figure:: img/check_validity.png
   :align: center

   ဘယ်ဘက်- input layer ၊ ညာဘက် - အမှားကင်းရှင်းပြီးဆီလျော်သော layer (အစိမ်း)၊ အမှားမကင်းပဲ ဆီလျော်မှုမရှိသော layer (လိမ္မော်ရောင်)

**Default menu**- :menuselection:`Vector --> Geometry Tools`

.. seealso:: :ref:`qgisfixgeometries` နှင့် ပင်မ plugin
   :ref:`geometry_checker`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT_LAYER``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Method** **(နည်းလမ်း)**
     - ``METHOD``
     - [enumeration]

       Default: 2
     - ဆီလျော်မှုကို စစ်ဆေးရာတွင်အသုံးပြုမည့် နည်းလမ်း။ ရွေးချယ်စရာ နည်းလမ်းများမှာ -

       * 0: Digitizing setting များတွင် ရွေးချယ်ထားသော တစ်ခု
       * 1: QGIS
       * 2: GEOS
   * - **Ignore ring self intersection** **(ကွင်းများ အချင်းချင်းထိဖြတ်နေခြင်းကို လျှစ်လျှူရှုခြင်း)**
     - ``IGNORE_RING_SELF_INTERSECTION``
     - [boolean]

       Default: False
     - ဆီလျော်မှုကို စစ်ဆေးသောအခါ ကွင်းများ အချင်းချင်းထိဖြတ်နေခြင်း ကို လျစ်လျူရှုပေးပါသည်။
   * -  **Valid output** **(အမှားကင်းရှင်းပြီးဆီလျော်သော ရလာဒ်)**
     - ``VALID_OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - ရင်းမြစ် layer ၏ အမှားကင်းရှင်းပြီးဆီလျော်သော feature များ၏ မိတ္တူတစ်ခုပါဝင်ရန် vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**

   * - **Invalid output** **(အမှားမကင်းပဲ ဆီလျော်မှုမရှိသော ရလာဒ်)**
     - ``INVALID_OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - တွေ့ရှိရသော အမှားများ၏ အကျဉ်းချုပ်ကို စာရင်းလုပ်ထားသည့် ``_errors`` field ဖြင့် ရင်းမြစ် layer ၏ အမှားမကင်းပဲ ဆီလျော်မှုမရှိသော feature များ၏ မိတ္တူပါဝင်သော vector layer။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**

   * - **Error output** **(အမှား ရလာဒ်)**
     - ``ERROR_OUTPUT``
     - [vector: point]

       Default: ``[Create temporary layer]``
     - တွေ့ရှိရသော အမှားများကိုဖော်ပြသော ``message`` field ဖြင့် အမှားတည်နေရာအတိအကျကို ဖော်ပြသော point layer။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည်- 

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**


Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Count of errors** **(အမှားအရေအတွက်)**
     - ``ERROR_COUNT``
     - [number]

     - အမှားများဖြစ်စေသော ဂျီဩမေတြီ အရေအတွက်
   * - **Error output** (**အမှား ရလာဒ်**)
     - ``ERROR_OUTPUT``
     - [vector: point]
     - တွေ့ရှိရသော အမှားများကိုဖော်ပြသော ``message`` field ဖြင့် အမှားတည်နေရာအတိအကျကို ဖော်ပြသော point layer။
   * - **Count of invalid features** **(အမှားမကင်းပဲ ဆီလျော်မှုမရှိသော feature အရေအတွက်)**
     - ``INVALID_COUNT``
     - [number]

     - အမှားမကင်း၍သုံးရန်မသင့်တော်သော geometry အရေအတွက်။
   * - **Invalid output** **(အမှားမကင်းပဲ ဆီလျော်မှုမရှိသော output)**
     - ``INVALID_OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

     - တွေ့ရှိရသော အမှားများ၏ အကျဉ်းချုပ်ကို စာရင်းလုပ်ထားသည့် ``_errors`` field ဖြင့် ရင်းမြစ် layer ၏ အမှားမကင်းပဲ ဆီလျော်မှုမရှိသော feature များ၏ မိတ္တူပါဝင်သော vector layer။
   * -  **Count of valid features** **(အမှားကင်းစင်ပြီးဆီလျော်သော feature အရေအတွက်)**
     - ``VALID_COUNT``
     - [number]

     - အမှားကင်းစင်ပြီးဆီလျော်သော ဂျီဩမေတြီများ အရေအတွက်
   * -  **Valid output** **(အမှားကင်းစင်ပြီးဆီလျော်သော ရလာဒ်)**
     - ``VALID_OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

     - ရင်းမြစ် layer ၏ အမှားကင်းစင်ပြီးဆီလျော်သော feature များ၏ မိတ္တူတစ်ခုပါဝင်သော vector layer။ 

Python code
............

**Algorithm ID**: ``qgis:checkvalidity``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**

.. index:: GEOS, QGIS
.. _typesofgeomerrors:

Types of error messages and their meanings (အမှားသတိပေးစာတိုအမျိုးအစားများနှင့် ၎င်းတို့၏အဓိပ္ပါယ်များ)
........................................................................................................

.. list-table:: GEOS နည်းလမ်းကိုအသုံးပြုလျှင် အောက်ပါ အမှားသတိပေးစာတိုများကို တွေ့ရနိုင်ပါသည်-
   :widths: 30 30 40
   :header-rows: 1
   :class: longtable

   * - အမှားသတိပေးစာတို
     - ရှင်းပြချက်
     - ဥပမာ

   * - Repeated point (ထပ်ခါတလဲလဲဖြစ်သော point)
     - Vertex (မျဉ်းအဆစ်) ကို ထပ်ခါထပ်ခါ လုပ်မိလျှင် ယခု အမှားဖြစ်စေပါသည်။
     - .. figure:: img/geos_rep_point.png
          :align: center

   * - Ring self-intersection (ကွင်း အချင်းချင်းထိဖြတ်ခြင်း)
     - ဂျီဩမေတြီ တစ်ခုသည် ၎င်းတို့အချင်းချင်းထိနေပြီး ကွင်းတစ်ခုကို ထုတ်ပေးသောအခါ ယခု အမှားဖြစ်စေပါသည်။
     - .. figure:: img/geos_ring_inter.png
          :align: center

   * - Self-intersection (အချင်းချင်း ထိဖြတ်နေခြင်း)
     - ဂျီဩမေတြီ တစ်ခုသည် ၎င်းတို့အချင်းချင်းထိနေသောအခါ ယခု အမှားဖြစ်စေပါသည်။
     - .. figure:: img/geos_self_inter.png
          :align: center

   * - Topology validation error (Topology ဆီလျော်မှု အမှား)
     -
     -

   * - Hole lies outside shell (Shell ၏အပြင်ဘက်တွင်ရှိနေသော အပေါက်)
     -
     -

   * - Holes are nested (အပေါက်များ ထပ်နေ/ရှုပ်ထွေးနေခြင်း)
     -
     -

   * - Interior is disconnected (အတွင်းပိုင်းတွင် ချိတ်ဆက်မှု ပြတ်တောက်နေခြင်း)
     -
     -

   * - Nested shells (ထပ်နေ/ရှုပ်ထွေးနေသော shell များ)
     - Polygon ဂျီဩမေတြီ တစ်ခုသည် အခြား polygon ဂျီဩမေတြီ တစ်ခုပေါ်တွင် ထပ်နေသောအခါ ယခု အမှားဖြစ်စေပါသည်။
     - .. figure:: img/geos_nest_shell.png
          :align: center

   * - Duplicate rings (ကွင်းများ ပွားနေခြင်း)
     - Polygon ဂျီဩမေတြီ တစ်ခု၏ ကွင်းနှစ်ခုသည် (အတွင်းပိုင်း သို့မဟုတ် အပြင်ပိုင်း) တစ်ထပ်တည်း ဖြစ်နေသောအခါ ယခု အမှားဖြစ်စေပါသည်။

     - .. figure:: img/geos_dupl_rings.png
          :align: center

   * - Too few points in geometry component (ဂျီဩမေတြီ အစိတ်အပိုင်းတွင် point အရမ်းနည်းနေခြင်း)
     -
     -

   * - Invalid coordinate (အမှားမကင်းပဲ ဆီလျော်မှုမရှိသော ကိုဩဒိနိတ်)
     - Point ဂျီဩမေတြီ တစ်ခုအတွက် ဂျီဩမေတြီ သည် သင့်တော်သော ကိုဩဒိနိတ် အတွဲ မပါရှိသောအခါ ယခု အမှားဖြစ်စေပါသည်။ ကိုဩဒိနိတ် အတွဲတွင် လတ္တီကျုတန်ဖိုးတစ်ခုနှင့် လောင်ဂျီကျုတန်ဖိုးတစ်ခုသည် အစီအစဉ်အတိုင်း ရှိမနေခြင်းဖြစ်ပါသည်။
     -

   * - Ring is not closed (ကွင်းသည် ပိတ်မနေခြင်း)
     -
     -


.. list-table:: QGIS နည်းလမ်းကို အသုံးပြုလျှင် အောက်ပါအမှားကို ဖြစ်စေနိုင်ပါသည်-
   :widths: 50 50 50
   :header-rows: 1
   :class: longtable

   * - အမှားသတိပေးစာတို
     - ရှင်းပြချက်
     - ဥပမာ

   * - Segment %1 of ring %2 of polygon %3 intersects segment %4
       of ring %5 of polygon %6 at %7
     -
     -

   * - Ring %1 with less than four points
     -
     -

   * - Ring %1 not closed
     -
     -

   * - Line %1 with less than two points
     -
     -

   * - Line %1 contains %n duplicate node(s) at %2
     - Line တစ်ခုပေါ်ရှိ တစ်ဆက်တစ်ဆက်တည်းဖြစ်နေသော point များသည် တူညီသော ကိုဩဒိနိတ်များ ရှိနေလျှင် ယခု အမှားဖြစ်စေပါသည်။
     - .. figure:: img/geos_rep_point.png
          :align: center

   * - Segments %1 and %2 of line %3 intersect at %4
     - Line တစ်ခုသည် ၎င်းအချင်းချင်း ထိဖြတ်နေလျှင် (line ၏ မျဉ်းပိုင်း နှစ်ခုသည် တစ်ခုကိုတစ်ခု ထိဖြတ်နေခြင်း) ယခု အမှားဖြစ်စေပါသည်။
     - .. figure:: img/qgis_seg_line_int.png
          :align: center

   * - Ring self-intersection (အချင်းအချင်း ထိဖြတ်နေသော ကွင်း)
     - Polygon ဂျီဩမေတြီ တစ်ခု၏ အပြင်ပိုင်း သို့မဟုတ် အတွင်းပိုင်း (ကျွန်း) ကွင်း/နယ်နိမိတ်သည် ၎င်းအချင်းချင်း ထိဖြတ်နေသောအခါ ယခု အမှားဖြစ်စေပါသည်။
     - .. figure:: img/geos_ring_inter.png
          :align: center

   * - Ring %1 of polygon %2 not in exterior ring
     -
     -

   * - Polygon %1 lies inside polygon %2
     - Polygon များစွာပါသော ဂျီဩမေတြီ တစ်ခု၏ အစိတ်အပိုင်းတစ်ခုသည် polygon များစွာပါဝင်သော ဂျီဩမေတြီ တစ်ခု၏ အပေါက်ထဲတွင် ရှိနေသောအခါ ယခု အမှားဖြစ်စေပါသည်။
     - .. figure:: img/qgis_poliinside_.png
          :align: center


.. _qgiscollect:

Collect geometries (ဂျီဩမေတြီ များစုစည်းခြင်း)
-----------------------------------------------

Vector layer တစ်ခုကိုယူပြီး ၎င်း၏ ဂျီဩမေတြီများကို အစိတ်အပိုင်းများစွာပါဝင်သော (multipart) ဂျီဩမေတြီများ အသစ်ထဲသို့ စုစည်းပေးပါသည်။

အတန်းအစားတူညီသော ဂျီဩမေတြီများကိုသာစုဆောင်းရန် တစ်ခု သို့မဟုတ် တစ်ခုထက်ပိုသော attribute များကို သတ်မှတ်နိုင်ပါသည် (သတ်မှတ်ထားသော attribute အတွက် တူညီသည့် တန်ဖိုး ရှိသော)။ တစ်နည်းအားဖြင့် ဂျီဩမေတြီ များအားလုံးကို စုဆောင်းနိုင်ပါသည်။

Output ဂျီဩမေတြီ များအားလုံးကို အစိတ်အပိုင်းတစ်ခုတည်းပါသော (single part) ဂျီဩမေတြီ ဖြစ်နေစေကာမူ ဂျီဩမေတြီ များစွာအဖြစ်သို့ ပြောင်းလဲပေးပါမည်။ ယခု algorithm သည် ထပ်နေသာ ဂျီဩမေတြီ များကိုပေါင်းစည်းမပေးပါ၊ ဂျီဩမေတြီ အစိတ်အပိုင်းတစ်ခုချင်းစီ၏ ပုံစံကို မပြောင်းလဲစေပဲ ၎င်းတို့ကို အတူတကွ စုစည်းပေးပါမည်။

အခြားနည်းလမ်းများအတွက် 'Promote to multipart' သို့မဟုတ် 'Aggregate' algorithm များကို ကြည့်ပါ။

**Default menu**- :menuselection:`Vector --> Geometry Tools`

.. seealso:: :ref:`qgisaggregate` ၊ :ref:`qgispromotetomulti` ၊
   :ref:`qgisdissolve`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Unique ID fields** **(ထင်ရှားသော ID field များ)**
     - ``FIELD``
     - [tablefield: any] [list]
     - ဂျီဩမေတြီ များကိုစုဆောင်းရန် တစ်ခု သို့မဟုတ် တစ်ခုထက်ပိုသော attribute များကိုရွေးချယ်ပါ။
   * - **Collected** **(စုစည်းထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - စုဆောင်းထားသော ဂျီဩမေတြီများပါဝင်သော vector layer

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Collected** **(စုစည်းထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - စုစည်းထားပြီးသော ဂျီဩမေတြီများအတွက် output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**


Python code
............

**Algorithm ID**: ``native:collect``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisconcavehull:

Concave hull (alpha shapes) (အတွင်းဘက်သို့ ခွက်ဝင်နေသော ကိုယ်ထည် (alpha ပုံသဏ္ဍာန်များ))
-----------------------------------------------------------------------------------------

Input point layer တစ်ခုထဲရှိ feature များ၏ concave hull ကိုတွက်ချက်ပေးပါသည်။

.. figure:: img/concave_hull_threshold.png
    :align: center

    Threshold အမျိုးမျိုး (0.3၊ 0.6၊ 0.9) ဖြင့် concave hull များ


.. seealso:: :ref:`qgisconvexhull` ၊ :ref:`qgisknearestconcavehull`

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
   * - **Input point layer** **(ထည့်သွင်းအသုံးပြုသော point layer)**
     - ``INPUT``
     - [vector: point]
     - ထည့်သွင်းအသုံးပြုသော point vector layer
   * - **Threshold** **(သတ်မှတ်အဆင့်)**
     - ``ALPHA``
     - [number]

       Default: 0.3
     - 0 (အများဆုံး concave hull) မှ 1 (convex hull) သို့ နံပါတ်
   * - **Allow holes** **(အပေါက်များခွင့်ပြုခြင်း)**
     - ``HOLES``
     - [boolean]

       Default: True
     - နောက်ဆုံး concave hull ထဲတွင် အပေါက်များ ခွင့်ပြု/မပြု ကို ရွေးချယ်ပေးပါသည်။
   * - **Split multipart geometry into singlepart geometries** **(အပိုင်းများစွာပါဝင်သော ဂျီဩမေတြီကို အပိုင်းတစ်ခုတည်းပါဝင်သော ဂျီဩမေတြီ များအဖြစ် ခွဲထုတ်ခြင်း)**
     - ``NO_MULTIGEOMETRY``
     - [boolean]

       Default: True
     - အပိုင်းများစွာပါဝင်သော (multipart) ဂျီဩမေတြီများအစား အပိုင်းတစ်ခုပဲပါဝင်သော (singlepart) ဂျီဩမေတြီ များကိုရယူလိုလျှင် အမှန်ခြစ်ထားပါ။
   * - **Concave hull** **(ခွက်နေသောကိုယ်ထည်)**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Concave hull**
     - ``OUTPUT``
     - [vector: polygon]
     - Output vector layer

Python code
............

**Algorithm ID**: ``qgis:concavehull``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisknearestconcavehull:

Concave hull (k-nearest neighbor)
----------------------------------

Point အစုများမှ concave hull polygon ကိုဖန်တီးပေးပါသည်။ Input layer သည် line သို့မဟုတ် polygon layer တစ်ခုဖြစ်နေလျှင် vertex (မျဉ်းအဆစ်များ) ကိုအသုံးပြုပါမည်။

Output polygon ၏ ခွက်ဝင်မှု (concaveness) ပမာဏကို ဆုံးဖြတ်ရန် ထည့်သွင်းစဉ်းစားသော အနီးအနားရှိအရာများ (neighbor) အရေအတွက်။ အရေအတွက် အနည်းငယ် အသုံးပြုလျှင် point များအတိုင်း အလွန်နီးကပ်စွာ လိုက်သော concave hull (ခွက်နေသောကိုယ်ထည်) တစ်ခုကိုရရှိစေပြီး အရေအတွက် များများ အသုံးပြုလျင် ပိုပြီးပြေပြစ်သော polygon တစ်ခုကို ရရှိမည်ဖြစ်ပါသည်။ အနည်းဆုံး neighbor point အရေအတွက်မှာ 3 ဖြစ်ပါသည်။ Point နှင့်အရေအတွက်တူသော သို့မဟုတ် ပိုကြီးသော အရေအတွက်ကို အသုံးပြုလျှင် convex hull (ခုံးနေသောကိုယ်ထည်) တစ်ခုကိုရရှိစေမည်ဖြစ်ပါသည်။

Field တစ်ခုကိုရွေးချယ်ထားလျှင် algorithm သည် ၎င်း field ထဲရှိ unique ဖြစ်သောတန်ဖိုးများကိုအသုံးပြု၍ input layer ထဲရှိ feature များကိုအုပ်စုဖွဲ့ပေးပြီး output layer ထဲတွင် အုပ်စုတစ်ခုချင်းစီအတွက် သီးသန့် polygon များကို ထုတ်ပေးမည်ဖြစ်ပါသည်။

.. seealso:: :ref:`qgisconcavehull`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Number of neighboring points to consider (a lower number is more concave, a higher number is smoother)** **(ထည့်သွင်းစဉ်းစားမည့် အနီးအနား point အရေအတွက် (အရေအတွက်နည်းလျှင် ပိုခွက်ပြီး၊ အရေအတွက်များလျှင် ပိုပြေပြစ်ပါသည်))**
     - ``KNEIGHBORS``
     - [number]

       Default: 3
     - Output polygon ၏ ခွက်ဝင်မှု (concaveness) ပမာဏကို ဆုံးဖြတ်ပေးပါသည်။ အရေအတွက် အနည်းငယ်ကို အသုံးပြုလျှင် point များအတိုင်း အလွန်နီးကပ်စွာ လိုက်သော concave hull (ခွက်နေသောကိုယ်ထည်) တစ်ခုကိုရရှိစေပြီး အရေအတွက်များများ အသုံးပြုလျှင် convex hull (ခုံးနေသောကိုယ်ထည်) ကဲ့သို့သော polygon တစ်ခုကို ရရှိမည်ဖြစ်ပါသည် (Point နှင့်အရေအတွက်တူသော သို့မဟုတ် ပိုကြီးသော အရေအတွက်ကို အသုံးပြုလျှင် convex hull (ခုံးနေသောကိုယ်ထည်) တစ်ခုကိုရရှိစေမည်ဖြစ်ပါသည်)။ အနည်းဆုံး point အရေအတွက်မှာ 3 ဖြစ်ပါသည်။
   * - **Field**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``FIELD``
     - [tablefield: any]

       Default: None
     - သတ်မှတ်ထားလျှင် field ထဲရှိ မတူသော (unique) တန်ဖိုးတစ်ခုချင်းစီအတွက် concave hull polygon တစ်ခုကိုဖန်တီးပေးမည် ဖြစ်ပါသည် (သတ်မှတ်ထားသောတန်ဖိုးကိုအသုံးပြုပြီး feature များကိုရွေးချယ်ခြင်းအားဖြင့်)
   * - **Concave hull**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Concave hull**
     - ``OUTPUT``
     - [vector: polygon]
     - Output vector layer

Python code
............

**Algorithm ID**: ``qgis:knearestconcavehull``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisconvertgeometrytype:

Convert geometry type (ဂျီဩမေတြီ အမျိုးအစားကို ပြောင်းလဲခြင်း)
---------------------------------------------------------------

ရှိနေပြီးသား layer တစ်ခုကိုအခြေခံပြီး ဂျီဩမေတြီ အမျိုးအစားမတူသော layer အသစ်တစ်ခုဖန်တီးပေးပါသည်။

Output layer ၏ attribute ဇယားသည် input layer ၏ attribute ဇယားနှင့် အတူတူပင် ဖြစ်ပါသည်။

လိုချင်သော ပြောင်းလဲမှုအားလုံးကို လုပ်ဆောင်လို့မရနိုင်ပါ။ ဥပမာ- line layer တစ်ခုကို point layer တစ်ခုအဖြစ်ပြောင်းလဲနိုင်ပါသည်၊ သို့သော် point layer တစ်ခုကို line layer တစ်ခုအဖြစ် မပြောင်းလဲနိုင်ပါ။

.. seealso:: :ref:`qgispolygonize` ၊ :ref:`qgislinestopolygons` ၊ :ref:`qgispolygonstolines` ၊
   :ref:`qgispointstopath`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **New geometry type** **(ဂျီဩမေတြီ အမျိုးအစား အသစ်)**
     - ``TYPE``
     - [enumeration]

       Default: 0
     - Output feature များတွင်အသုံးပြုမည့် ဂျီဩမေတြီ အမျိုးအစား။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည်-

       * 0 --- Centroids (အလယ်ဗဟိုမှတ်များ)
       * 1 --- Nodes (ဆုံမှတ်များ)
       * 2 --- Linestrings (Linestring များ)
       * 3 --- Multilinestrings (များစွာသော linestring များ)
       * 4 --- Polygons (Polygon များ)

   * - **Converted** **(ပြောင်းလဲထားပြီးသော)**
     - ``OUTPUT``
     - [vector: any]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Converted** **(ပြောင်းလဲထားပြီးသော)**
     - ``OUTPUT``
     - [vector: any]
     - Output vector layer - အမျိုးအစားသည် parameter များပေါ်တွင် မူတည်ပါသည်

Python code
............

**Algorithm ID**: ``qgis:convertgeometrytype``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisconverttocurves:

Convert to curved geometries (ကွေးနေသော ဂျီဩမေတြီ များအဖြစ် ပြောင်းလဲခြင်း)
----------------------------------------------------------------------------

ဂျီဩမေတြီ တစ်ခုကို ကွေးနေသော ဂျီဩမေတြီအဖြစ်သို့ ပြောင်းလဲပေးပါသည်။

ကွေးနေပြီးသား ဂျီဩမေတြီ များကို ပုံစံအပြောင်းအလဲမရှိစေဘဲ ရယူပါမည်။

|checkbox| သည် line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line or polygon]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Maximum distance tolerance** **(အများဆုံးအကွာအဝေး လက်ခံနိုင်စွမ်း)**
     - ``DISTANCE``
     - [number]

       Default: 0.000001
     - Vertex (မျဉ်းအဆစ်) များ၏မူလတည်နေရာနှင့် ကွေးနေသော ဂျီဩမေတြီများပေါ်တွင်ကျရောက်နေသော vertex များအကြား ခွင့်ပြုပေးသော အများဆုံးအကွာအဝေး
   * - **Maximum angle tolerance** **(အများဆုံးထောင့်အကျယ် လက်ခံနိုင်စွမ်း)**
     - ``ANGLE``
     - [number]

       Default: 0.000001
     - ရည်မှန်းထားသော မျဉ်းခုံးပေါ်တွင် point များကို အကွာအဝေးညီ နေရာချထားလျှင် မျဉ်းခုံးကို အစားထိုးခြင်းအတွက် မျဉ်းပိုင်း (segment) များကို သင့်တော်သည်ဟု ယူဆပါသည်။ ပုံမှန် point နေရာချခြင်းကို စမ်းသပ်သောအခါ ယခု parameter သည် အကြီးဆုံး ထောင့်သွေဖယ်ခြင်း (ဒီဂရီဖြင့်) ကိုခွင့်ပြုပေးပါသည်။ 0 နှင့် 45\° ကြား။
   * - **Curves** **(မျဉ်းကွေးများ)**
     - ``OUTPUT``
     - [vector: compoundcurve or curvepolygon]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Curves** **(မျဉ်းကွေးများ)**
     - ``OUTPUT``
     - [vector: compoundcurve or curvepolygon]
     - ကွေးနေသော ဂျီဩမေတြီများဖြင့် output vector layer

Python code
............

**Algorithm ID**: ``native:converttocurves``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisconvexhull:

Convex hull (ခုံးနေသော ကိုယ်ထည်)
---------------------------------

Input layer ထဲရှိ feature တစ်ခုချင်းစီအတွက် convex hull ကိုတွက်ချက်ပေးပါသည်။

Layer တစ်ခုလုံး သို့မဟုတ် feature အုပ်စုကို ခြုံလွှမ်းသော convex hull တွက်ချက်ခြင်းအတွက် 'Minimum bounding geometry' algorithm ကို ကြည့်ပါ။

.. figure:: img/convex_hull.png
   :align: center

   အနက်ရောင် line များသည် layer feature တစ်ခုချင်းစီအတွက် convex hull ကို သရုပ်ခွဲပြပါသည်

|checkbox| သည် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

**Default menu**- :menuselection:`Vector --> Geoprocessing Tools`

.. seealso:: :ref:`qgisminimumboundinggeometry` ၊
   :ref:`qgisconcavehull`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Convex hull**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -
 
       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Convex hull**
     - ``OUTPUT``
     - [vector: polygon]
     - Output (convex hull) vector layer

Python code
............

**Algorithm ID**: ``native:convexhull``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisextenttolayer:

Create layer from extent (နယ်ပယ်အကျယ်အဝန်းမှ layer ဖန်တီးခြင်း)
----------------------------------------------------------------

Input layer ၏ extent (နယ်ပယ်အကျယ်အဝန်း)နှင့် ကိုက်ညီသော ဂျီဩမေတြီဖြင့် feature တစ်ခုတည်းပါဝင်သော vector layer အသစ်တစ်ခုကို ဖန်တီးပေးပါသည်။

Layer ထည့်ရန် လိုအပ်သော algorithm များတွင်အသုံးပြုနိုင်သော layer တစ်ခုအဖြစ်သို့ extent အရှိအတိုင်း (``xmin`` ၊ ``xmax`` ၊ ``ymin`` ၊ ``ymax`` format) ကို ပြောင်းလဲရန် model များတွင် ယခုနည်းလမ်းကို အသုံးပြုနိုင်ပါသည်။

.. seealso:: :ref:`qgispointtolayer`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Extent (xmin, xmax, ymin, ymax)**
     - ``INPUT``
     - [extent]
     - ထည့်သွင်းအသုံးပြုသော နယ်ပယ်အကျယ်အဝန်း

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Extent** **(နယ်ပယ်အကျယ်အဝန်း)**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Extent** (**နယ်ပယ်အကျယ်အဝန်း**)
     - ``OUTPUT``
     - [vector: polygon]
     - Output (extent) vector layer

Python code
............

**Algorithm ID**: ``native:extenttolayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgispointtolayer:

Create layer from point (Point မှ layer ဖန်တီးခြင်း)
-----------------------------------------------------

Point parameter တစ်ခုနှင့် ကိုက်ညီသော ဂျီဩမေတြီဖြင့် feature တစ်ခုတည်းပါဝင်သော vector layer အသစ်တစ်ခုကို ဖန်တီးပေးပါသည်။ Layer ထည့်ရန် လိုအပ်သော algorithm များအတွက် point တစ်ခုကို point layer တစ်ခုအဖြစ်ဖန်တီးရန် model များတွင် ယခုနည်းလမ်းကို အသုံးပြုနိုင်ပါသည်။

.. seealso:: :ref:`qgisextenttolayer`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Point**
     - ``INPUT``
     - [coordinates]
     - CRS အချက်အလက်များပါဝင်သော input point (ဥပမာ- ``397254,6214446 [EPSG:32632]``)

       CRS မရှိလျှင် project ၏ CRS ကိုအသုံးပြုပါလိမ့်မည်။
     
       မြေပုံ canvas ပေါ်တွင် click ထောက်ပေးခြင်းဖြင့် point ကိုတိတိကျကျသတ်မှတ်နိုင်ပါသည်။
   * - **Point**
     - ``OUTPUT``
     - [vector: point]

       Default: ``[Create temporary layer]``
     - Output layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Point**
     - ``OUTPUT``
     - [vector: point]
     - Input point ပါဝင်သော output point vector layer

Python code
............

**Algorithm ID**: ``native:pointtolayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiswedgebuffers:

Create wedge buffers (သပ်ပုံစံ buffer များ ဖန်တီးခြင်း)
--------------------------------------------------------

Input point များမှ သပ်ပုံစံ buffer များကို ဖန်တီးပေးပါသည်။

.. figure:: img/wedge_buffers.png
   :align: center

   သပ်ပုံစံ buffer များ

ယခု algorithm မှထွက်လာသော မူရင်း output သည် ကွေးနေသော polygon ဂျီဩမေတြီများဖြစ်ပါသည်၊ သို့သော် output format ပေါ်မူတည်ပြီး ၎င်းတို့ကို polygon များဖြစ်အောင် အလိုအလျောက် အပိုင်းများပိုင်းပစ်နိုင်ပါသည်။

.. seealso:: :ref:`qgisbuffer` ၊ :ref:`qgisbufferbym` ၊
   :ref:`qgistaperedbuffer`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: point]
     - ထည့်သွင်းအသုံးပြုသော point vector layer
   * - **Azimuth (degrees from North)** (**Azimuth (ဒီဂရီဖြင့် မြောက်ဘက်မှ စတင်တိုင်းတာပါသည် - မြောက်အရပ်သည် 0 ဒီဂရီဖြစ်ပါသည်)**)
     - ``AZIMUTH``
     - [number |dataDefine|]

       Default: 0.0
     - Wedge (သပ်ပုံစံ) ၏အလယ်တန်ဖိုးအဖြစ် ထောင့် (ဒီဂရီဖြင့်)
   * - **Wedge width (in degrees)** **(Wedge အကျယ် (ဒီဂရီဖြင့်))**
     - ``WIDTH``
     - [number |dataDefine|]

       Default: 45.0
     - Buffer ၏ အကျယ် (ဒီဂရီဖြင့်)။ Azimuth လားရာ၏ တစ်ဖက်တစ်ချက်စီတွင် wedge သည် ထောင့်အကျယ်၏ တစ်ဝက်အထိ ချဲ့ကားပေးပါလိမ့်မည်။

       .. figure:: img/wedge_buffers_azimuth_width.png
         :align: center

         Wedge buffer ၏ Azimuth နှင့် အကျယ်တန်ဖိုးများ

   * - **Outer radius** **(အပြင်ဘက် အချင်းဝက်များ)**
     - ``OUTER_RADIUS``
     - [number |dataDefine|]

       Default: 1.0
     - Wedge ၏ အပြင်ဘက် *အရွယ်အစား* (အလျား) - အရွယ်အစားဆိုသည်မှာ မူရင်း point မှ wedge ပုံစံ၏ အစွန်းဘက်သို့အကွာအဝေးကို ဆိုလိုပါသည်။
   * - **Inner radius** **(အတွင်းဘက် အချင်းဝက်များ)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``INNER_RADIUS``
     - [number |dataDefine|]

       Default: 0.0
     - အတွင်းဘက် အချင်းဝက်တန်ဖိုး။ 0 ဖြစ်လျှင် wedge သည် မူရင်း point မှစတင်ပါမည်။
   * - **Buffers** **(ကြားခံဇုံများ)**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Buffers** **(ကြားခံဇုံများ)**
     - ``OUTPUT``
     - [vector: polygon]
     - Output (wedge buffer) vector layer	 

Python code
............

**Algorithm ID**: ``native:wedgebuffers``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisdelaunaytriangulation:

Delaunay triangulation (Delaunay တြိဂံဖွဲ့ခြင်း)
-------------------------------------------------

Input point layer နှင့်သက်ဆိုင်သော Delaunay triangulation ဖြင့် polygon layer တစ်ခုဖန်တီးပေးပါသည်။

.. figure:: img/delaunay.png
   :align: center

   Point များပေါ်တွင် Delaunay တြိဂံဖွဲ့ခြင်း

**Default menu**- :menuselection:`Vector --> Geometry Tools`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: point]
     - ထည့်သွင်းအသုံးပြုသော point vector layer
   * - **Delaunay triangulation**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Delaunay triangulation**
     - ``OUTPUT``
     - [vector: polygon]
     - Output (Delaunay triangulation) vector layer

Python code
............

**Algorithm ID**: ``qgis:delaunaytriangulation``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisdeleteholes:

Delete holes (အပေါက်များကို ဖျက်ပစ်ခြင်း)
------------------------------------------

Polygon layer တစ်ခုကိုယူပြီး polygon များထဲမှ အပေါက်များကိုဖယ်ရှားပေးပါသည်။ အပေါက်များပါနေသော polygon များကို ၎င်းတို့၏အပြင်ဘက်ကွင်းများသာပါသော polygon များဖြင့်အစားထိုးခြင်းဖြင့် vector layer အသစ်တစ်ခုကို ဖန်တီးပါသည်။ အချက်အလက်များကို မွမ်းမံပြင်ဆင်ခြင်း ပြုလုပ်မည်မဟုတ်ပါ။

အသေးဆုံး ဧရိယာ parameter ကိုအသုံးပြုခြင်းသည် သတ်မှတ်ထားသော ဧရိယာထက် ပိုငယ်သော အပေါက်များကိုသာ ဖယ်ရှားပေးပါသည်။ ၎င်း parameter ကို ``0.0`` တွင်ထားလျှင် ရှိသမျှ အပေါက်များအားလုံးကို ဖယ်ရှားပေးပါသည်။

.. figure:: img/delete_holes.png
   :align: center

   မဖျက်ခင်နှင့် ဖျက်ပြီးနောက်

|checkbox| သည် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: polygon]
     - ထည့်သွင်းအသုံးပြုသော polygon vector layer
   * - **Remove holes with area less than** (**သတ်မှတ်ထားသော ဧရိယာထက် ပိုငယ်သော အပေါက်များကို ဖယ်ရှားခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``MIN_AREA``
     - [number |dataDefine|]

       Default: 0.0
     - သတ်မှတ်ထားသော ဧရိယာထက် ပိုငယ်သော အပေါက်များကိုသာ ဖျက်ပေးပါသည်။ တန်ဖိုးကို ``0.0`` တွင်ထားလျှင် ရှိသမျှ အပေါက်များ **အားလုံး** ကို ဖျက်ပေးပါသည်။

   * - **Cleaned** **(ရှင်းလင်းထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Cleaned** **(ရှင်းလင်းထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output (ရှင်းလင်းထားပြီးသော) vector layer	 

Python code
............

**Algorithm ID**: ``native:deleteholes``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisdensifygeometries:

Densify by count (အရေအတွက်အားဖြင့် သိပ်သည်းအောင်ပြုလုပ်ခြင်း)
--------------------------------------------------------------

Polygon သို့မဟုတ် line layer တစ်ခုကိုယူပြီး မူရင်း vertex အရေအတွက်ထက် ပိုများသော vertex များကိုဖန်တီးပြီး polyon သို့မဟုတ် line layer အသစ်တစ်ခုကိုဖန်တီးပေးပါသည်။

ဂျီဩမေတြီများတွင် အမြင့် Z သို့မဟုတ် M တန်ဖိုးများပါလျှင် ၎င်းတန်ဖိုးများကို ထပ်ပေါင်းထည့်ထားသော vertex များ၌ အဖြောင့်အတိုင်း ဖြည့်စွက်တွက်ချက် (interpolate) ပေးပါမည်။

မျဉ်းပိုင်း (segment) တစ်ခုစီတွင် ပေါင်းထည့်မည့် vertex များအရေအတွက်ကို input parameter တစ်ခုအဖြစ် သတ်မှတ်ပါသည်။

.. figure:: img/densify_geometry.png
   :align: center

   အနီရောင် point များသည် densify မလုပ်မီနှင့် လုပ်ပြီးနောက် vertex များကို ပြသပါသည်

|checkbox| သည် line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

**Default menu**- :menuselection:`Vector --> Geometry Tools`

.. seealso:: :ref:`qgisdensifygeometriesgivenaninterval`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line, polygon]
     - ထည့်သွင်းအသုံးပြုသော line သို့မဟုတ် polygon vector layer 
   * - **Vertices to add** **(ပေါင်းထည့်ရန် vertex များ)**
     - ``VERTICES``
     - [number]

       Default: 1
     - မျဉ်းပိုင်းတစ်ခုစီတွင် ပေါင်းထည့်ရမည့် vertex အရေအတွက်
   * - **Densified** **(သိပ်သည်းအောင်ပြုလုပ်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Densified** **(သိပ်သည်းအောင်ပြုလုပ်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output (သိပ်သည်းအောင်ပြုလုပ်ထားပြီးသော) vector layer

Python code
............

**Algorithm ID**: ``native:densifygeometries``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisdensifygeometriesgivenaninterval:

Densify by interval (ကြားအကွာအဝေးဖြင့် သိပ်သည်းအောင်ပြုလုပ်ခြင်း)
------------------------------------------------------------------

Polygon သို့မဟုတ် line layer တစ်ခုကိုယူပြီး မူလ vertex အရေအတွက်ထက် ပိုများသော ဂျီဩမေတြီများရှိသည့် polyon သို့မဟုတ် line layer အသစ်တစ်ခုကိုဖန်တီးပေးပါသည်။

Vertex နှစ်ခုကြားရှိ အများဆုံးအကွာအဝေးသည် သတ်မှတ်ထားသော အကွာအဝေးကို မကျော်လွန်စေရန် မျဉ်းပိုင်းတစ်ခုချင်းစီတွင် အကွာအဝေးညီသော vertex များကို ပေါင်းထည့်ပေးခြင်းဖြင့် ဂျီဩမေတြီ များကို သိပ်သည်းအောင်လုပ်ဆောင်ပေးပါသည်။

ဂျီဩမေတြီများတွင် အမြင့် Z သို့မဟုတ် M တန်ဖိုးများပါလျှင် ၎င်းတန်ဖိုးများကို ထပ်ပေါင်းထည့်ထားသော vertex များ၌ အဖြောင့်အတိုင်း ဖြည့်စွက်တွက်ချက် (interpolate) ပေးပါမည်။

**ဥပမာ**

အကွာအဝေးကို 3 အဖြစ်သတ်မှတ်လျှင် မျဉ်းပိုင်းပေါ်တွင် vertex အပို သုံးခုလိုအပ်ပြီး ၎င်းတို့ကို 2.5 တွင်ထားလျှင် မျဉ်းပိုင်းပေါ်တွင် ညီညီညာညာနေရချထားပေးမည် ဖြစ်သောကြောင့် မျဉ်းပိုင်း ``[0 0] -> [10 0]`` ကို ``[0 0] -> [2.5 0] -> [5 0] -> [7.5 0] -> [10 0]`` သို့ပြောင်းပေးမည် ဖြစ်ပါသည်။

.. figure:: img/densify_geometry_interval.png
   :align: center

   ဂျီဩမေတြီများကို သတ်မှတ်ထားသော ကြားအကွာအဝေးဖြင့် သိပ်သည်းအောင်ပြုလုပ်ခြင်း

|checkbox| သည် line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgisdensifygeometries`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line, polygon]
     - ထည့်သွင်းအသုံးပြုသော line သို့မဟုတ် polygon vector layer
   * - **Interval between vertices to add** **(Vertex များပေါင်းထည့်ရန် ကြားအကွာအဝေး)**
     - ``INTERVAL``
     - [number |dataDefine|]

       Default: 1.0
     - ကပ်လျှက်ရှိသော vertex နှစ်ခုကြား အများဆုံးအကွာအဝေး
   * - **Densified**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Densified** **(သိပ်သည်းအောင်ပြုလုပ်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output (densified) vector layer

Python code
............

**Algorithm ID**: ``native:densifygeometriesgivenaninterval``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisdissolve:

Dissolve (ပေါင်းစည်းခြင်း)
---------------------------

Vector layer တစ်ခုကိုယူပြီး ၎င်း၏ feature များကို feature အသစ်များအဖြစ် ပေါင်းစည်းပေးပါသည်။ အမျိုးအစားတူသောအုပ်စု (attribute တွင် တူညီသောတန်ဖိုးရှိနေသည့်အရာများ) တွင် ပါဝင်သော feature များကို ပေါင်းစည်းရန် တစ်ခု သို့မဟုတ် တစ်ခုထက်ပိုသော attribute များကို သတ်မှတ်ပေးနိုင်ပါသည်။ တစ်နည်းအားဖြင့် feature များအားလုံးကိုလည်း feature တစ်ခုတည်းအဖြစ် ပေါင်းစည်းနိုင်ပါသည်။

Output ဂျီဩမေတြီအားလုံးကို ဂျီဩမေတြီ များစွာအဖြစ် ပြောင်းလဲပစ်ပါမည်။ Input သည် polygon layer ဖြစ်နေလျှင် ပေါင်းစည်းထားပြီးသော (dissolved) ကပ်လျှက် polygon များ၏ ဘုံနယ်နိမိတ်များကို ဖျက်ပစ်ပါမည်။ "Keep disjoint features separate (အချိတ်အဆက်မရှိနေသော feature များကို သီးခြားအဖြစ်ထားခြင်း)" setting ကိုအသုံးပြုလျှင် ထပ်မနေသော သို့မဟုတ် ထိမနေသော feature များကို သီးခြားအနေဖြင့် ထုတ်ပေးမည်ဖြစ်ပါသည် (အပိုင်းများစွာပါဝင်သော feature တစ်ခုတည်း၏ အစိတ်အပိုင်းများ အစား)။

ရရှိလာသော attribute ဇယားတွင် input layer နှင့်တူညီသော field များရှိပါမည်။ Output layer field များ၏ တန်ဖိုးများသည် process လုပ်ဆောင်မည့် ပထမ input feature ၏ field များဖြစ်ပါသည်။


.. figure:: img/dissolve.png
   :align: center

   Dissolving a layer into a single multipart feature (Layer တစ်ခုကို အပိုင်းများစွာပါဝင်သော feature တစ်ခုအဖြစ် ပေါင်းစည်းခြင်း)

**Default menu**- :menuselection:`Vector --> Geoprocessing Tools`

.. seealso:: :ref:`qgisaggregate` ၊ :ref:`qgiscollect`

Parameters (Parameter များ)
............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - Input vector layer
   * - **Dissolve field(s)** **(ပေါင်းစည်းမည့် field (များ))**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``FIELD``
     - [tablefield: any] [list]

       Default: []
     - ရွေးချယ်ထားသော field (များ) အတွက် တူညီသောတန်ဖိုးရှိသည့် feature များကို feature တစ်ခုဖြင့် အစားထိုးမည်ဖြစ်ပြီး ၎င်းတို့၏ ဂျီဩမေတြီများကိုပေါင်းပစ်ပါမည်။
   
       Field ကိုရွေးချယ်မထားလျှင် feature များအားလုံးကိုပေါင်းစည်းပစ်ပြီး feature တစ်ခုတည်း (အပိုင်းများစွာပါဝင်သော) အဖြစ် ထုတ်ပေးမည်ဖြစ်ပါသည်။

       .. figure:: img/dissolve_field.png
          :align: center

          Polygon layer ကို ဘုံ attribute အရ ပေါင်းစည်းခြင်း (အစိတ်အပိုင်းများစွာပါဝင်သော feature နှစ်ခု)

   * - **Dissolved** **(ပေါင်းစည်းထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Keep disjoint features separate** **(အချိတ်အဆက်မရှိနေသော feature များကို သီးခြားအဖြစ်ထားခြင်း)**
     - ``SEPARATE_DISJOINT``
     - [boolean]

       Default: False
     - ပေါင်းစည်းထားသော feature များ၏ အစိတ်အပိုင်းများကို သီးခြား feature များအဖြစ် ထုတ်ပေးပါသည် (အစိတ်အပိုင်းများစွာပါဝင်သော feature တစ်ခု၏ အစိတ်အပိုင်းများ အစား)။

       .. figure:: img/dissolve_disjoint.png
          :align: center

          မူရင်း (ဘယ်ဘက်)၊ အားလုံးပေါင်းစည်းထားသော (ထင်ရှားသော feature ၃ ခု - ညာဘက်)

       .. figure:: img/dissolve_disjoint_field.png
          :align: center

          မူရင်း (ဘယ်ဘက်)၊ field အရပေါင်းစည်းထားသော (ထင်ရှားသော feature ၅ ခု - ညာဘက်))

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Dissolved** **(ပေါင်းစည်းထားသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ပေါင်းစည်းထားသော ဂျီဩမေတြီများပါဝင်သည့် output vector layer

Python code
............

**Algorithm ID**: ``native:dissolve``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgissetzfromraster:

Drape (set Z value from raster) (Drape (Raster မှ အမြင့် Z တန်ဖိုးကိုသတ်မှတ်ခြင်း))
------------------------------------------------------------------------------------

Feature ဂျီဩမေတြီ ထဲရှိ ထပ်နေသော vertex များအားလုံးအတွက် အမြင့်တန်ဖိုး Z ကိုသတ်မှတ်ရန် raster layer တစ်ခုအတွင်းရှိ band (လှိုင်းအလွှာ) တစ်ခုမှ နမူနာတန်ဖိုးများကို အသုံးပြုပါသည်။ Raster တန်ဖိုးများကို ကြိုတင်ချိန်ကိုက်ထားသောပမာဏဖြင့် စကေးသတ်မှတ်နိုင်ပါသည်။

Layer ထဲတွင် အမြင့် Z တန်ဖိုးရှိနေပြီးသားဆိုလျှင် ၎င်းတို့ကို တန်ဖိုးအသစ်တစ်ခုဖြင့် အစားထိုးပစ်ပါမည်။ အမြင့် Z တန်ဖိုးမရှိလျှင် အမြင့်တန်ဖိုးပါလာစေရန် ဂျီဩမေတြီကို အဆင့်မြှင့်ပေးပါလိမ့်မည်။

|checkbox| သည် Z တန်ဖိုးပါဝင်သော point၊ line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgissetmfromraster` ၊ :ref:`qgissetzvalue`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Raster layer**
     - ``RASTER``
     - [raster]
     - အမြင့်တန်ဖိုးများပါသော raster layer
   * - **Band number** (**Band နံပါတ်**)
     - ``BAND``
     - [raster band]

       Default: 1
     - အမြင့် Z တန်ဖိုးများ ရယူမည့် raster band
   * - **Value for nodata or non-intersecting vertices** **(Nodata အတွက် သို့မဟုတ် ထိဖြစ်ခြင်းမရှိသော vertex များအတွက် တန်ဖိုး)**
     - ``NODATA``
     - [number |dataDefine|]

       Default: 0
     - Vertex သည် raster တစ်ခု၏ ဆီလျော်မှုရှိသော pixel တစ်ခုကို မထိဖြတ်လျှင် အသုံးပြုမည့် တန်ဖိုး
   * - **Scale factor** **(စကေး factor)**
     - ``SCALE``
     - [number |dataDefine|]

       Default: 1.0
     - Scaling တန်ဖိုး - band တန်ဖိုးများကို ယခု ဂဏန်းဖြင့် မြှောက်မည်ဖြစ်ပါသည်။
   * - **Offset** **(အရွေ့)**
     - ``OFFSET``
     - [number |dataDefine|]

       Default: 0.0
     - အရွေ့တန်ဖိုး - "Scale factor" ကိုအသုံးပြုပြီးနောက် ၎င်းကိုသင်္ချာနည်းအရ band တန်ဖိုးများဆီကို ပေါင်းထည့်ပါသည်။
   * - **Updated** **(နောက်ဆုံးအခြေအနေဖြစ်အောင်လုပ်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ (raster layer မှ အမြင့် Z တန်ဖိုးများဖြင့်)။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Updated** **(နောက်ဆုံးအခြေအနေဖြစ်အောင်လုပ်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Raster layer မှ အမြင့် Z တန်ဖိုးများပါဝင်သော output vector layer

Python code
............

**Algorithm ID**: ``native:setzfromraster``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisdropmzvalues:

Drop M/Z values (M/Z တန်ဖိုးများကို ဖယ်ခြင်း)
----------------------------------------------

Input ဂျီဩမေတြီ မှ M (အတိုင်းအတာ) သို့မဟုတ် Z (အမြင့်) တန်ဖိုးများကို ဖယ်ရှားပေးပါသည်။

.. seealso:: :ref:`qgissetmvalue` ၊ :ref:`qgissetzvalue`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - M သို့မဟုတ် Z တန်ဖိုးများပါသော input vector layer
   * - **Drop M Values**  **(M တန်ဖိုးများ ဖယ်ခြင်း)**
     - ``DROP_M_VALUES``
     - [boolean]

       Default: False
     - ဂျီဩမေတြီများမှ M တန်ဖိုးများကိုဖယ်ရှားပေးပါသည်။
   * - **Drop Z Values** **(Z တန်ဖိုးများ ဖယ်ခြင်း)**
     - ``DROP_Z_VALUES``
     - [boolean]

       Default: False
     - ဂျီဩမေတြီများမှ Z တန်ဖိုးများကိုဖယ်ရှားပေးပါသည်။
   * - **Z/M Dropped** **(Z/M တန်ဖိုးများ ဖယ်ရှားထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Z/M Dropped** **(Z/M တန်ဖိုးများ ဖယ်ရှားထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

     - Output vector layer (ဂျီဩမေတြီများမှ M နှင့်/သို့မဟုတ် Z တန်ဖိုးများကို ဖယ်ရှားထားခြင်းမှလွဲ၍ input layer နှင့် ထပ်တူဖြစ်ပါသည်)။

Python code
............

**Algorithm ID**: ``native:dropmzvalues``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiseliminateselectedpolygons:

Eliminate selected polygons (ရွေးချယ်ထားသော polygon များကို ဖယ်ရှားခြင်း)
--------------------------------------------------------------------------

Input layer ၏ရွေးချယ်ထားသော polygon များကို ကပ်လျှက်ရှိသော polygon များ၏ ဘုံနယ်နိမိတ်များကို ဖျက်ပစ်ပြီး ၎င်း polygon များဖြင့်ပေါင်းစပ်ပေးပါသည်။ ကပ်လျှက်ရှိသော polygon သည် အကြီးဆုံး သို့မဟုတ် အသေးဆုံး ဧရိယာရှိသောတစ်ခုဖြစ်နိုင်ပါသည် သို့မဟုတ် ဖယ်ရှားပစ်ရမည့် polygon နှင့် အကြီးဆုံးဘုံနယ်နိမိတ်ကို မျှသုံးနေသော တစ်ခုဖြစ်နိုင်ပါသည်။

ဖယ်ရှားခြင်းကို သာမန်အားဖြင့် polygon အစအန အသေးများကိုဖယ်ရှားရန်အတွက် အသုံးပြုပါသည်။ Input များ၏နယ်နိမိတ်များသည် တူသယောင်ယောင် ရှိသော်လည်း တစ်ထပ်တည်းကျမနေသော polygon များ ထိဖြတ်ခြင်းကြောင့် ဖြစ်ပေါ်လာသည့် polygon သေးသေးလေးများ ဖယ်ရှားခြင်းကို ဆိုလိုပါသည်။

**Default menu**- :menuselection:`Vector --> Geoprocessing Tools`

.. seealso:: :ref:`qgisfixgeometries`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: polygon]
     - ထည့်သွင်းအသုံးပြုသော polygon vector layer
   * - **Merge selection with the neighboring polygon with the** **(ရွေးချယ်ထားသော polygon ကိုအနီးအနားမှ polygon များနှင့်ပေါင်းစပ်ခြင်း)**
     - ``MODE``
     - [enumeration]

       Default: None
     - ရွေးချယ်ထားသော polygon များကို ဖယ်ရှားရန် အသုံးပြုသော parameter ကိုရွေးချယ်ပါ -

       * 0 --- Largest Area (အကြီးဆုံး ဧရိယာ)
       * 1 --- Smallest Area (အသေးဆုံး ဧရိယာ)
       * 2 --- Largest Common Boundary (အကြီးဆုံး ဘုံနယ်နိမိတ်)

   * - **Eliminated** **(ဖယ်ရှားထားပြီးသော)**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Eliminated** **(ဖယ်ရှားထားပြီးသော)**
     - ``OUTPUT``
     - [vector: polygon]
     - Output polygon vector layer

Python code
............

**Algorithm ID**: ``qgis:eliminateselectedpolygons``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisexplodelines:

Explode lines (Line များကို အပိုင်းပိုင်း ခွဲထုတ်ခြင်း)
--------------------------------------------------------

Line layer တစ်ခုကိုယူပြီး line layer အသစ်တစ်ခုကိုဖန်တီးပေးပါသည်။ ၎င်း layer အသစ်တွင် line layer တစ်ခုချင်းစီအား မူရင်း line ထဲရှိ မျဉ်းပိုင်းများကို ကိုယ်စားပြုသော line များဖြင့် အစားထိုးထားပါသည်။

ရရှိလာသော layer ၏ line တစ်ခုချင်းစီသည် အစမှတ်နှင့် အဆုံးမှတ်သာပါဝင်ပြီး ကြားထဲတွင် ကြားမှတ်မရှိတော့ပါ။


.. figure:: img/explode_lines.png
   :align: center

   မူရင်း line layer နှင့် အပိုင်းပိုင်းခွဲထုတ်ထားသော line layer

|checkbox| သည် line feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgissubdivide` ၊ :ref:`qgislinesubstring`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line]
     - ထည့်သွင်းအသုံးပြုသော line vector layer
   * - **Exploded** **(အပိုင်းပိုင်း ခွဲထုတ်ထားပြီးသော)**
     - ``OUTPUT``
     - [vector: line]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Exploded** **(အပိုင်းပိုင်း ခွဲထုတ်ထားပြီးသော)**
     - ``OUTPUT``
     - [vector: line]
     - Input layer ၏ မျဉ်းပိုင်းတစ်ခုချင်းစီကို ကိုယ်စားပြုသော feature များပါဝင်သည့် output line vector layer။

Python code
............

**Algorithm ID**: ``native:explodelines``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisextendlines:

Extend lines (Line များကို ဆန့်ထုတ်ခြင်း)
------------------------------------------

Line ၏အစနှင့် အဆုံးတွင် သတ်မှတ်ထားသော ပမာဏတစ်ခုဖြင့် line ဂျီဩမေတြီ ကိုဆန့်ထုတ်ပေးပါသည်။

Line ထဲရှိ ပထမဆုံးနှင့် နောက်ဆုံး မျဉ်းပိုင်း၏ လှည့်ထားသောဦးတည်ရာအရပ် အတိုင်း line များကိုဆန့်ထုတ်ခြင်း။

.. figure:: img/extend_lines.png
   :align: center

   အနီရောင် dash များသည် မူရင်း layer ၏ အစပိုင်းနှင့် နောက်ဆုံးဆန့်ထုတ်ထားသော နေရာများကို ပြသပါသည်

|checkbox| သည် line feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgislinesubstring`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line]
     - ထည့်သွင်းအသုံးပြုသော line vector layer
   * - **Start distance** **(အစ အကွာအဝေး)**
     - ``START_DISTANCE``
     - [number |dataDefine|]
     - Line ၏ပထမ မျဉ်းပိုင်း (အစမှတ်) ကိုဆန့်ထုတ်မည့် အကွာအဝေး။
   * - **End distance** (**အဆုံးသတ် အကွာအဝေး**)
     - ``END_DISTANCE``
     - [number |dataDefine|]
     - Line ၏နောက်ဆုံး မျဉ်းပိုင်း (အဆုံးမှတ်) ကိုဆန့်ထုတ်မည့် အကွာအဝေး။
   * - **Extended** **(ဆန့်ထုတ်ထားပြီးသော)**
     - ``OUTPUT``
     - [vector: line]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Extended** **(ဆန့်ထုတ်ထားပြီးသော)**
     - ``OUTPUT``
     - [vector: line]
     - Output (ဆန့်ထုတ်ထားသော) line vector layer

Python code
............

**Algorithm ID**: ``native:extendlines``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisextractmvalues:

Extract M values (M တန်ဖိုးများ ဆွဲထုတ်ခြင်း)
----------------------------------------------

ဂျီဩမေတြီများမှ M တန်ဖိုးများကို feature အချက်အလက်များထဲသို့ ဆွဲထုတ်ပေးပါသည်။

Default အားဖြင့် feature တစ်ခုချင်းစီ၏ ပထမ vertex မှ M တန်ဖိုးကိုသာ ဆွဲထုတ်ပါသည်၊ သို့သော် algorithm သည် ဂျီဩမေတြီများအားလုံး၏ M တန်ဖိုးများပေါ်တွင် စာရင်းအင်းကိန်းဂဏန်းများ (ပေါင်းလဒ်၊ ပျမ်းမျှကိန်း၊ အနည်းဆုံး နှင့် အများဆုံး) ကိုတွက်ချက်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgisextractzvalues` ၊ :ref:`qgissetmvalue` ၊ :ref:`qgisdropmzvalues`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Summaries to calculate** **(တွက်ချက်ရန် အကျဉ်းချုပ်များ)**
     - ``SUMMARIES``
     - [enumeration]

       Default: [0]
     - ဂျီဩမေတြီတစ်ခု၏ M တန်ဖိုးများ၏ စာရင်းအင်းကိန်းဂဏန်းများ။ အောက်ပါတို့ထဲမှ တစ်ခု သို့မဟုတ် တစ်ခုထက်ပိုနိုင်ပါသည် -

       * 0 --- First (ပထမကိန်း)
       * 1 --- Last (နောက်ဆုံးကိန်း)
       * 2 --- Count (အရေအတွက်)
       * 3 --- Sum (ပေါင်းလာဒ်)
       * 4 --- Mean (ပျမ်းမျှကိန်း)
       * 5 --- Median (ကြားကိန်း)
       * 6 --- St.dev (pop) (စံသွေဖယ်မှု)
       * 7 --- Minimum (အနည်းဆုံး)
       * 8 --- Maximum (အများဆုံး)
       * 9 --- Range (အပိုင်းအခြား)
       * 10 --- Minority (အနည်းစုဖြစ်သော)
       * 11 --- Majority (အများစုဖြစ်သော)
       * 12 --- Variety (အမျိုးစုံလင်မှု)
       * 13 --- Q1
       * 14 --- Q3
       * 15 --- IQR

   * - **Output column prefix** **(Output column ရှေ့ဆက် စကားလုံး)**
     - ``COLUMN_PREFIX``
     - [string]

       Default: 'm\_'
     - Output (M) column အတွက် ရှေ့ဆက်စကားလုံး
   * - **Extracted** **(ဆွဲထုတ်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Extracted** **(ဆွဲထုတ်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output vector layer (M တန်ဖိုးများဖြင့်)

Python code
............

**Algorithm ID**: ``native:extractmvalues``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisextractspecificvertices:

Extract specific vertices (သီးခြားသတ်မှတ်ထားသော vertex များကို ဆွဲထုတ်ခြင်း)
-----------------------------------------------------------------------------

Vector layer တစ်ခုကိုယူပြီး input ဂျီဩမေတြီ များထဲမှ သတ်မှတ်ထားသော vertex များကို ကိုယ်စားပြုသော point များပါဝင်သော point layer တစ်ခုကို ဖန်တီးပေးပါသည်။

ဥပမာ- ဂျီဩမေတြီထဲမှ ပထမဆုံးနှင့် နောက်ဆုံး vertex များကိုဆွဲထုတ်ရန် ယခု algorithm ကိုအသုံးပြုနိုင်ပါသည်။ Point တစ်ခုချင်းစီနှင့် ဆက်စပ်သော attribute များသည် vertex ပါသော feature နှင့်ဆက်စပ်နေသည့် attribute များနှင့် အတူတူပင် ဖြစ်ပါသည်။ 

Vertex index (အညွှန်းကိန်း) များ parameter သည် ဆွဲထုတ်မည့် vertex များ၏ index များကိုသတ်မှတ်ရန် comma separated string (ကော်မာဖြင့် ပိုင်းခြားထားသော စာသား) ကိုလက်ခံပါသည်။ ပထမဆုံး vertex သည် index 0၊ ဒုတိယ vertex သည် index 1 စသဖြင့် ဖြစ်ပါသည်။ ဂျီဩမေတြီ၏အဆုံးတွင် vertex များကိုရှာရန်အတွက် အနှုတ်တန်ဖိုး index များကိုလည်း အသုံးပြုနိုင်ပါသည်။ ဥပမာ index -1 သည် နောက်ဆုံး vertex ကို ကိုယ်စားပြုပြီး -2 သည် ဒုတိယနောက်ဆုံး vertex ကို ကိုယ်စားပြုပါသည်။

သတ်မှတ်ထားသော vertex တည်နေရာ (ဥပမာ 0၊ -1၊ စသဖြင့်)၊ မူရင်း vertex index ၊ vertex ၏ အစိတ်အပိုင်း နှင့် အစိတ်အပိုင်းထဲမှ ၎င်း index (polygon အတွက် ၎င်း၏ကွင်းများအပါအဝင်)၊ မူရင်း ဂျီဩမေတြီ တစ်လျှောက်မှ အကွာအဝေး နှင့် မူရင်းဂျီဩမေတြီအတွက် vertex ၏ ညီမျှစွာနှစ်ပိုင်းခွဲထားသောထောင့် (bisector angle) များကို ဖော်ပြသော ထပ်ဆောင်း field များကို vertex များသို့ပေါင်းထည့်ပေးပါသည်။

|checkbox| သည် point feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgisextractvertices` ၊ :ref:`qgisfilterverticesbym` ၊
   :ref:`qgisfilterverticesbyz`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Vertex indices** **(Vertex index များ)**
     - ``VERTICES``
     - [string]

       Default: '0'
     - ဆွဲထုတ်မည့် vertex များ၏ index များ၏ comma-separated string (ကော်မာဖြင့် ပိုင်းခြားထားသော စာသား)
   * - **Vertices** **(မျဉ်းအဆစ်များ)**
     - ``OUTPUT``
     - [vector: point]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Vertices** **(မျဉ်းအဆစ်များ)**
     - ``OUTPUT``
     - [vector: point]
     - Input layer ဂျီဩမေတြီများမှ သီးခြားသတ်မှတ်ထားသော vertex များပါဝင်သော output (point) vector layer။

Python code
............

**Algorithm ID**: ``native:extractspecificvertices``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisextractvertices:

Extract vertices (Vertex များကို ဆွဲထုတ်ခြင်း)
-----------------------------------------------

Input ဂျီဩမေတြီထဲရှိ vertex များကို ကိုယ်စားပြုသော point များပါဝင်သော point layer တစ်ခုကို ဖန်တီးပေးပါသည်။ 

Point တစ်ခုချင်းစီနှင့် ဆက်စပ်သော attribute များသည် vertex ပါသော feature နှင့်ဆက်စပ်နေသည့် attribute များနှင့် အတူတူပင် ဖြစ်ပါသည်။ 

Vertex index (0 မှစတင်ပါသည်)၊ vertex ၏ အစိတ်အပိုင်း နှင့် အစိတ်အပိုင်းထဲမှ ၎င်း index (polygon အတွက် ၎င်း၏ကွင်းများအပါအဝင်)၊ မူရင်းဂျီဩမေတြီ တစ်လျှောက်မှ အကွာအဝေး နှင့် မူရင်းဂျီဩမေတြီ အတွက် vertex ၏ ညီမျှစွာနှစ်ပိုင်းခွဲထားသောထောင့် (bisector angle) များကို ဖော်ပြသော ထပ်ဆောင်း field များကို vertex များထဲသို့ ပေါင်းထည့်ပေးပါသည်။

.. figure:: img/extract_nodes.png
   :align: center

   Line နှင့် polygon layer အတွက် ဆွဲထုတ်ထားသော vertex များ

|checkbox| သည် point feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

**Default menu**- :menuselection:`Vector --> Geometry Tools`

.. seealso:: :ref:`qgisextractspecificvertices` ၊
   :ref:`qgisfilterverticesbym` ၊ :ref:`qgisfilterverticesbyz`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Vertices** **(မျဉ်းအဆစ်များ)**
     - ``OUTPUT``
     - [vector: point]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Vertices**
     - ``OUTPUT``
     - [vector: point]
     - Input layer ဂျီဩမေတြီမှ vertex များပါဝင်သော output (point) vector layer 

Python code
............

**Algorithm ID**: ``native:extractvertices``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisextractzvalues:

Extract Z values (အမြင့် Z တန်ဖိုးများကို ဆွဲထုတ်ခြင်း)
--------------------------------------------------------

ဂျီဩမေတြီများမှ အမြင့် Z တန်ဖိုးများကို feature attribute များဆီသို့ ဆွဲထုတ်ပေးပါသည်။

Default အားဖြင့် feature တစ်ခုချင်းစီ၏ ပထမ vertex မှ Z တန်ဖိုးကိုသာ ဆွဲထုတ်ပေးပါသည်၊ သို့သော် algorithm သည် ဂျီဩမေတြီများအားလုံး၏ Z တန်ဖိုးများတွင် စာရင်းအင်းကိန်းဂဏန်း (ပေါင်းလဒ်၊ ပျမ်းမျှကိန်း၊ အနည်းဆုံး နှင့် အများဆုံး) ကိုတွက်ချက်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgisextractmvalues` ၊ :ref:`qgissetzvalue` ၊
   :ref:`qgisdropmzvalues`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Summaries to calculate** **(တွက်ချက်ရန် အကျဉ်းချုပ်များ)**
     - ``SUMMARIES``
     - [enumeration]

       Default: [0]
     - ဂျီဩမေတြီတစ်ခု၏ အမြင့် Z တန်ဖိုးများ၏ စာရင်းအင်းကိန်းဂဏန်းများ။ အောက်ပါတို့ထဲမှ တစ်ခု သို့မဟုတ် တစ်ခုထက်ပိုနိုင်ပါသည် -

       * 0 --- First (ပထမကိန်း)
       * 1 --- Last (နောက်ဆုံးကိန်း)
       * 2 --- Count (အရေအတွက်)
       * 3 --- Sum (ပေါင်းလဒ်)
       * 4 --- Mean (ပျမ်းမျှကိန်း)
       * 5 --- Median (ကြားကိန်း)
       * 6 --- St.dev (pop) (စံသွေဖယ်မှု)
       * 7 --- Minimum (အနည်းဆုံး)
       * 8 --- Maximum (အများဆုံး)
       * 9 --- Range (အပိုင်းအခြား)
       * 10 --- Minority (အနည်းစုဖြစ်သော)
       * 11 --- Majority (အများစုဖြစ်သော)
       * 12 --- Variety (အမျိုးစုံလင်မှု)
       * 13 --- Q1
       * 14 --- Q3
       * 15 --- IQR   

   * - **Output column prefix**  **(Output column ရှေ့ဆက်စကားလုံး)**
     - ``COLUMN_PREFIX``
     - [string]

       Default: 'z\_'
     - Output (z) column အတွက် ရှေ့ဆက်စကားလုံး
   * - **Extracted** **(ဆွဲထုတ်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -
 
       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Extracted** **(ဆွဲထုတ်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output vector layer (အမြင့် Z တန်ဖိုးများဖြင့်)

Python code
............

**Algorithm ID**: ``native:extractzvalues``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisfilterverticesbym:

Filter vertices by M value (Vertex များကို M တန်ဖိုးဖြင့် စစ်ထုတ်ခြင်း)
------------------------------------------------------------------------

Vertex များကို ၎င်းတို့၏ M တန်ဖိုးပေါ်အခြေခံပြီး စစ်ထုတ် (filter) ပေးပြီး၊ သတ်မှတ်ထားသော အနည်းဆုံးတန်ဖိုးထက် ပိုကြီးသော သို့မဟုတ် တူညီသော M တန်ဖိုးရှိသည့် သို့မဟုတ် အများဆုံးတန်ဖိုးထက်ပိုငယ်သော သို့မဟုတ် တူညီသော M တန်ဖိုးရှိသည့် vertex များသာပါဝင်သော ဂျီဩမေတြီများကို ပြန်ထုတ်ပေးပါသည်။ 

အနည်းဆုံးတန်ဖိုးကို သတ်မှတ်မထားလျှင် အများဆုံးတန်ဖိုးဖြင့်သာ စစ်ဆေးမည်ဖြစ်ပြီး အလားတူပင် အများဆုံးတန်ဖိုးကိုသတ်မှတ်မထားလျှင် အနည်းဆုံးတန်ဖိုးဖြင့်သာ စစ်ဆေးမည်ဖြစ်ပါသည်။

.. figure:: img/filter_zm.png
   :align: center

   အနီရောင် line သည် M တန်ဖိုး 10 နှင့် 10 အောက်ရှိသော vertex များသာပါသည့် အနက်ရောင် line ကို ကိုယ်စားပြုပါသည်။
   
|checkbox| သည် line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. note:: Input ဂျီဩမေတြီ attribute များနှင့် အသုံးပြုထားသော စစ်ထုတ်မှု (filter) များအပေါ် မူတည်ပြီး ယခု algorithm ဖြင့်ဖန်တီးထားသော ရရှိလာသည့် ဂျီဩမေတြီများသည် ဆက်လက်အသုံးပြုရန် ရချင်မှ ရပါလိမ့်မည်။

.. seealso:: :ref:`qgisfilterverticesbyz` ၊ :ref:`qgisextractvertices` ၊
 :ref:`qgisextractspecificvertices`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line, polygon]
     - Vertex များဖယ်ထုတ်မည့် ထည့်သွင်းအသုံးပြုသော line သို့မဟုတ် polygon vector layer
   * - **Minimum** **(အနည်းဆုံး)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``MIN``
     - [number |dataDefine|]

       Default: *Not set*
     - ခွင့်ပြုထားသော အနည်းဆုံး M တန်ဖိုးများ
   * - **Maximum** **(အများဆုံး)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``MAX``
     - [number |dataDefine|]

       Default: *Not set*
     - ခွင့်ပြုထားသော အများဆုံး M တန်ဖိုးများ
   * - **Filtered** **(စစ်ထုတ်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Filtered** (**စစ်ထုတ်ထားပြီးသော**)
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - စစ်ထုတ်ထားပြီးသော vertex များသာပါဝင်သော feature များ၏ output vector layer

Python code
............

**Algorithm ID**: ``native:filterverticesbym``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisfilterverticesbyz:

Filter vertices by Z value (Vertex များကို အမြင့် Z တန်ဖိုးဖြင့် စစ်ထုတ်ခြင်း)
-------------------------------------------------------------------------------

Vertex များကို ၎င်းတို့၏ အမြင့် Z တန်ဖိုးပေါ်အခြေခံပြီး စစ်ထုတ် (filter) ပြီး၊ သတ်မှတ်ထားသော အနည်းဆုံးတန်ဖိုးထက် ပိုကြီးသော သို့မဟုတ် တူညီသော အမြင့် Z တန်ဖိုးရှိသော သို့မဟုတ် အများဆုံးတန်ဖိုးထက်ပိုငယ်သော သို့မဟုတ် တူညီသော အမြင့် Z တန်ဖိုးရှိသော vertex များကိုသာ ပြန်ထုတ်ပေးပါသည်။ 

အနည်းဆုံးတန်ဖိုးကို သတ်မှတ်မထားလျှင် အများဆုံးတန်ဖိုးဖြင့်သာ စစ်ဆေးမည်ဖြစ်ပြီး အလားတူပင် အများဆုံးတန်ဖိုးကိုသတ်မှတ်မထားလျှင် အနည်းဆုံးတန်ဖိုးဖြင့်သာ စစ်ဆေးမည်ဖြစ်ပါသည်။

.. figure:: img/filter_zm.png
   :align: center

   အနီရောင် line သည် Z တန်ဖိုး 10 နှင့် 10 အောက်ရှိသော vertex များသာ ပါဝင်သည့် အနက်ရောင် line ကို ကိုယ်စားပြုပါသည်။

|checkbox| သည် Z တန်ဖိုးရှိသော line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. note:: Input ဂျီဩမေတြီ attribute များနှင့် အသုံးပြုထားသော စစ်ထုတ်မှု (filter) များအပေါ် မူတည်ပြီး ယခု algorithm ဖြင့်ဖန်တီးထားသော ရရှိလာသည့် ဂျီဩမေတြီများကို ဆက်လက်အသုံးပြုရန် ရချင်မှ ရပါလိမ့်မည်။ အသုံးပြုနိုင်စေရန်အတွက် :ref:`qgisfixgeometries` algorithm ကိုအသုံးပြုရန်လိုအပ်ပါသည်။

.. seealso:: :ref:`qgisfilterverticesbym` ၊ :ref:`qgisextractvertices` ၊
 :ref:`qgisextractspecificvertices`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line, polygon]
     - Vertex များဖယ်ထုတ်မည့် ထည့်သွင်းအသုံးပြုသော line သို့မဟုတ် polygon vector layer
 
   * - **Minimum** **(အနည်းဆုံး)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``MIN``
     - [number |dataDefine|]

       Default: *Not set*
     - ခွင့်ပြုထားသော အနည်းဆုံး Z တန်ဖိုးများ
   * - **Maximum** **(အများဆုံး)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``MAX``
     - [number |dataDefine|]

       Default: *Not set*
     - ခွင့်ပြုထားသော အများဆုံး Z တန်ဖိုးများ
   * - **Filtered** (**စစ်ထုတ်ထားပြီးသော**)
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Filtered** **(စစ်ထုတ်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

     - စစ်ထုတ်ထားပြီးသော vertex များသာပါဝင်သော feature များ၏ output vector layer

Python code
............

**Algorithm ID**: ``native:filterverticesbyz``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisfixgeometries:

Fix geometries (ဂျီဩမေတြီများကိုပြင်ဆင်ခြင်း)
----------------------------------------------

မည်သည့် Input vertex များကိုမှ မဆုံးရှုံးစေပဲ ဆီလျော်မှုမရှိသော ဂျီဩမေတြီတစ်ခုကို ဆီလျော်ပြီးအသုံးပြုနိုင်အောင် လုပ်ဆောင်ပေးပါသည်။ ဆီလျော်မှုရှိပြီးသား ဂျီဩမေတြီများကို အခြား ပြင်ဆင်ခြင်းများ မပြုလုပ်တော့ပဲ ပြန်ထုတ်ပေးပါသည်။ ဂျီဩမေတြီများစွာပါဝင်သော  (multi-geometry) layer ကို အမြဲတမ်းပြန်ထုတ်ပေးပါသည်။

|checkbox| သည် M တန်ဖိုးပါရှိသော point၊ line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. note:: Output တွင် M တန်ဖိုးများ မပါတော့ပါ။

.. seealso:: :ref:`qgischeckvalidity`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Repair method** **(ပြင်ဆင်သောနည်းလမ်း)**
     - ``METHOD``
     - [enumeration]

       Default: 1
     - ဂျီဩမေတြီများပြင်ဆင်ရန်နည်းလမ်းများ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       * 0 --- ``Linework`` - ကွင်းများအားလုံးကို node (အဆစ်) များပါသော line များအစုတစ်ခုအဖြစ် ပေါင်းလိုက်ပြီး ၎င်း line မှ ဆီလျော်မှုရှိသော polygon များကိုဆွဲထုတ်ပေးပါသည်။
       * 1 --- ``Structure`` - ပထမဆုံးအနေဖြင့် ကွင်းများအားလုံးကို ဆီလျော်မှုရှိအောင် လုပ်ဆောင်ပြီး shells (ကိုယ်ထည်များ) ကိုပေါင်းပါသည်၊ ထို့နောက် ဆီလျော်မှုရှိသော ရလာဒ်ကို ဖန်တီးရန် ၎င်း shell များမှ အပေါက်များကို ဖယ်ထုတ်ပါသည်။ အပေါက်များနှင့် shell များကို မှန်မှန်ကန်ကန် အမျိုးအစား ခွဲထားသည်ဟု ယူဆပါသည်။ GEOS 3.10 သို့မဟုတ် ၎င်းအထက် ပါဝင်သော QGIS version လိုအပ်ပါသည် (:menuselection:`Help --> About` menu တွင်စစ်ဆေးပါ)။
   * - **Fixed geometries** **(ပြင်ဆင်ထားပြီးသောဂျီဩမေတြီများ)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Fixed geometries** **(ပြင်ဆင်ထားပြီးသောဂျီဩမေတြီများ)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

     - ပြင်ဆင်ထားသော ဂျီဩမေတြီများပါဝင်သော output vector layer

Python code
............

**Algorithm ID**: ``native:fixgeometries``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisforcerhr:

Force right-hand-rule (Right-hand-rule ကိုတွန်းအားပေးလုပ်ဆောင်ခြင်း)
---------------------------------------------------------------------

Polygon တစ်ခုဖြင့် နယ်နိမိတ်သတ်မှတ်ထားသော ဧရိယာသည် နယ်နိမိတ်၏ ညာဘက်တွင် ရှိသော Right-Hand-Rule ကိုလိုက်နာရန် polygon ဂျီဩမေတြီ များကိုတွန်းအားပေးလုပ်ဆောင်ပါသည်။ အပြင်ဘက်ကွင်းသည် နာရီလက်တံလားရာအတိုင်း လှည့်ပတ်ပြီး အတွင်းဘက်ကွင်းများသည် နာရီလက်တံပြောင်းပြန်လားရာ အတိုင်း လှည့်ပတ်ပါသည်။

|checkbox| သည် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: polygon]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Reoriented** **(ဦးတည်ရာအရပ်ကို ပြန်လှည့်ထားသော)**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Reoriented** (**ဦးတည်ရာအရပ် ကို ပြန်လှည့်ထားသော**)
     - ``OUTPUT``
     - [vector: polygon]
     - ဦးတည်ရာအရပ် ကို ပြန်လှည့်ထားသော ဂျီဩမေတြီများပါဝင်သော output vector layer

Python code
............

**Algorithm ID**: ``native:forcerhr``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisantimeridiansplit:

Geodesic line split at antimeridian (Meridian မျဉ်း၏ ဆန့်ကျင်ဘက်အရပ်တွင် ပိုင်းခြားထားသော geodesic line)
---------------------------------------------------------------------------------------------------------

Antimeridian (±180 ဒီဂရီ လောင်ဂျီကျူ) တွင် line ဖြတ်သောအခါတိုင်း line တစ်ခုကို အပိုင်းများစွာပါဝင်သော geodesic မျဉ်းပိုင်းများအဖြစ် ပိုင်းပစ်ပေးပါသည်။

အချို့သော အရိပ်ချစနစ် (projection) များတွင် antimeridian တွင်ပိုင်းခြားထားခြင်းသည် line များကို ကြည့်ရှုရာတွင်ပိုမိုလွယ်ကူစေပါသည်။ ပြန်ထုတ်ပေးသော ဂျီဩမေတြီသည် အမြဲတမ်း အစိတ်အပိုင်းများစွာပါဝင်သော (multi-part) ဂျီဩမေတြီဖြစ်ပါသည်။

Input ဂျီဩမေတြီထဲရှိ line မျဉ်းပိုင်းများသည် antimeridian ကိုဖြတ်သောအခါတိုင်း ၎င်းမျဉ်းပိုင်း၏ တစ်ဖက်တစ်ချက်စီတွင် point များကိုဆက်ပေးသော geodesic line ကိုအသုံးပြုပြီး ဆုံးဖြတ်သော ပိုင်းဖြတ်ပေးသည့်လတ္တီကျု (breakpoint latitude) ဖြင့် ၎င်းတို့ကို မျဉ်းပိုင်းနှစ်ခုအဖြစ် ပိုင်းပစ်ပါသည်။ ထို breakpoint ကိုတွက်ချက်သောအခါ လက်ရှိ project ၏ ellipsoid (ဘဲဥပုံစက်လုံး) setting ကိုအသုံးပြုမည်ဖြစ်သည်။

Input ဂျီဩမေတြီသည် M သို့မဟုတ် Z တန်ဖိုးများပါလျှင် ၎င်းတို့ကို antimeridian တွင် ဖန်တီးထားသော vertex အသစ်များအတွက် အဖြောင့်အတိုင်း ဖြည့်စွက်တွက်ချက် (interpolate) ပေးပါလိမ့်မည်။

|checkbox| သည် line feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line]
     - ထည့်သွင်းအသုံးပြုသော line vector layer
   * - **Split** **(ပိုင်းဖြတ်ခြင်း)**
     - ``OUTPUT``
     - [vector: line]

       Default: ``[Create temporary layer]``
     - Output line vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် - 

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Split** **(ပိုင်းဖြတ်ခြင်း)**
     - ``OUTPUT``
     - [vector: line]
     - Antimeridian တွင်ပိုင်းဖြတ်သော output line vector layer

Python code
............

**Algorithm ID**: ``native:antimeridiansplit``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisgeometrybyexpression:

Geometry by expression (Expression အားဖြင့် ဂျီဩမေတြီ)
-------------------------------------------------------

QGIS expression တစ်ခုကိုအသုံးပြုပြီး input feature များအတွက် ရှိနေပြီးသား (သို့မဟုတ် ဂျီဩမေတြီ အသစ်များ ဖန်တီးပေးပါသည်) ဂျီဩမေတြီများကို update (သတင်းအချက်အလက်အသစ်ကို ရယူခြင်း) ပြုလုပ်ပေးပါသည်။ 

QGIS expression engine ၏ လိုက်လျှောညီထွေမှုများကို အသုံးပြုပြီး output feature များအတွက် ဂျီဩမေတြီများကို ပြုပြင်နိုင်/ဖန်တီးနိုင်သော အဆင့်မြင့်သည့် ဂျီဩမေတြီပြုပြင်ခြင်းများကို လုပ်ဆောင်နိုင်ပါသည်။

QGIS expression function အကူအညီအတွက် :ref:`expression builder <vector_expressions>` ရှိ မူရင်းအတိုင်းပါသော အကူအညီ ကိုကြည့်ပါ။

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Output geometry type** **(Output ဂျီဩမေတြီအမျိုးအစား)**
     - ``OUTPUT_GEOMETRY``
     - [enumeration]

       Default: 0
     - Output ဂျီဩမေတြီသည် expression ပေါ်တွင် များစွာမူတည်ပါသည် - ဥပမာ buffer တစ်ခုဖန်တီးလျှင် ဂျီဩမေတြီအမျိုးအစားသည် polygon ဖြစ်ရပါမည်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       * 0 --- Polygon
       * 1 --- Line
       * 2 --- Point

   * - **Output geometry has z values** **(Output ဂျီဩမေတြီတွင် အမြင့် Z တန်ဖိုးများ ပါရှိခြင်း)**
     - ``WITH_Z``
     - [boolean]

       Default: False
     - Output ဂျီဩမေတြီသည် အမြင့် Z တန်ဖိုး ပါသင့်/မသင့် ရွေးချယ်ပေးပါသည်။
   * - **Output geometry has m values** **(Output ဂျီဩမေတြီတွင် M တန်ဖိုးများ ပါရှိခြင်း)**
     - ``WITH_M``
     - [boolean]

       Default: False
     - Output ဂျီဩမေတြီသည် M တန်ဖိုး ပါသင့်/မသင့် ရွေးချယ်ပေးပါသည်။
   * - **Geometry expression**
     - ``EXPRESSION``
     - [expression]

       Default: '$geometry'
     - အသုံးပြုလိုသော ဂျီဩမေတြီ expression ကိုထည့်ပါ။ Expression Dialog ကိုဖွင့်ရန် ခလုတ်ကိုအသုံးပြုနိုင်ပါသည်။ Dialog တွင် အကူအညီနှင့် လမ်းညွှန်များအပါအဝင် သက်ဆိုင်သော expression များအားလုံးကို စာရင်းပြုစုပေးထားပါသည်။
   * - **Modified geometry** **(ပြုပြင်ထားသော ဂျီဩမေတြီ)**
     - ``OUTPUT``
     - [vector: any]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Modified geometry** **(ပြုပြင်မွမ်းမံထားသော ဂျီဩမေတြီ)**
     - ``OUTPUT``
     - [vector: any]
     - Output vector layer

Python code
............

**Algorithm ID**: ``native:geometrybyexpression``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisinterpolatepoint:

Interpolate point on line (Line ပေါ်တွင် point ကို ဖြည့်စွက်တွက်ထုတ်ခြင်း)
---------------------------------------------------------------------------

Line သို့မဟုတ် ကောက်နေသော ဂျီဩမေတြီများတစ်လျှောက်တွင် သတ်မှတ်ထားသောအကွာအဝေး၌ ဖြည့်စွက်တွက်ထုတ်ပေးထားသော point ဂျီဩမေတြီ တစ်ခုကို ဖန်တီးပေးပါသည်။

Z နှင့် M တန်ဖိုးများကို ရှိနေပြီးသားတန်ဖိုးများမှ အဖြောင့်တိုင်း ဖြည့်စွက်တွက်ထုတ် (interpolate) ပေးပါသည်။

အစိတ်အပိုင်းများစွာပါဝင်သော ဂျီဩမေတြီတစ်ခုဖြစ်လျှင် substring ကိုတွက်ချက်သောအခါ ပထမဆုံး အပိုင်းကိုသာ ထည့်သွင်းစဉ်းစားမည်ဖြစ်သည်။

သတ်မှတ်ထားသော အကွာအဝေးသည် input feature ၏အလျားထက် ပိုရှည်နေလျှင် ရရှိလာသော feature တွင် null ဂျီဩမေတြီ တစ်ခုရှိနေပါမည်။

.. figure:: img/interpolated_point.png
   :align: center

   Line ၏အစ 500m တွင် interpolate လုပ်ထားသော point

.. seealso:: :ref:`qgispointsalonglines`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line, polygon]
     - ထည့်သွင်းအသုံးပြုသော line သို့မဟုတ် polygon vector layer
   * - **Distance** **(အကွာအဝေး)**
     - ``DISTANCE``
     - [number |dataDefine|]

       Default: 0.0
     - Line ၏အစမှ အကွာအဝေး
   * - **Interpolated points** **(ဖြည့်စွက်တွက်ထုတ်ထားသော point များ)**
     - ``OUTPUT``
     - [vector: point]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Interpolated points** **(ဖြည့်စွက်တွက်ထုတ်ထားသော point များ)**
     - ``OUTPUT``
     - [vector: point]
     - Line သို့မဟုတ် polygon နယ်နိမိတ်တစ်လျှောက် သတ်မှတ်ထားသော အကွာအဝေးတွင်ရှိသော feature များပါဝင်သော output point vector layer

Python code
............

**Algorithm ID**: ``native:interpolatepoint``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiskeepnbiggestparts:

Keep N biggest parts (N အကြီးဆုံး အစိတ်အပိုင်းများကို ဆက်လက်ထားရှိခြင်း)
-------------------------------------------------------------------------

Polygon များ သို့မဟုတ် multipolygon များပါဝင်သော layer တစ်ခုကိုယူပြီး multipolygon feature တစ်ခုချင်းစီ၏ *n* အကြီးဆုံး polygon များကိုသာ ထိန်းသိမ်းထားပေးသော layer အသစ်တစ်ခုကို ပြန်ထုတ်ပေးပါသည်။ Feature တစ်ခုသည် *n* သို့မဟုတ် ပိုနည်းသော အစိတ်အပိုင်းများ ရှိလျှင် feature ကို မိတ္တူပွား ပေးပါလိမ့်မည်။

.. figure:: img/n_biggest.png
   :align: center
   
   ဘယ်ဘက်အပေါ်မှ နာရီလက်တံအတိုင်း - မူရင်း အစိတ်အပိုင်းများစွာပါဝင်သော feature ၊ တစ် ၊ နှစ် နှင့် သုံးအကြီးဆုံးအစိတ်အပိုင်းများကို ဆက်လက်ထားရှိပေးထားခြင်း

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Polygons** **(Polygon များ)**
     - ``INPUT``
     - [vector: polygon]
     - ထည့်သွင်းအသုံးပြုသော polygon vector layer
   * - **Parts to keep** (**ဆက်လက်ထားရှိရမည့် အစိတ်အပိုင်းများ**)
     - ``PARTS``
     - [number]

       Default: 1
     - ဆက်လက်ထားရှိရမည့် အစိတ်အပိုင်းများ အရေအတွက်။ 1 ဖြစ်လျှင် feature ၏အကြီးဆုံး အစိတ်အပိုင်းကိုသာ ဆက်လက်ထားရှိပေးထားပါမည်။
   * - **Parts** **(အစိတ်အပိုင်းများ)**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output polygon vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Parts** **(အစိတ်အပိုင်းများ)**
     - ``OUTPUT``
     - [vector: polygon]
     - Feature တစ်ခုချင်းစီ၏ N အကြီးဆုံးအစိတ်အပိုင်းများပါဝင်သော output polygon vector layer

Python code
............

**Algorithm ID**: ``qgis:keepnbiggestparts``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgislinesubstring:

Line substring (Line ၏ အပိုင်းအစ)
----------------------------------

သတ်မှတ်ထားသော အစ နှင့်အဆုံးသတ် အကွာအဝေးများ (line ၏အစမှ တိုင်းတာပါသည်) ကြားတွင်ကျရောက်သော line (သို့မဟုတ် မျဉ်းကွေး) တစ်ခု၏ တစ်စိတ်တစ်ပိုင်းကို ပြန်ထုတ်ပေးပါသည်။

Z နှင့် M တန်ဖိုးများကို ရှိနေပြီးသားတန်ဖိုးများမှ အဖြောင့်တိုင်း ဖြည့်စွက်တွက်ထုတ် (interpolate) ပေးပါသည်။

အစိတ်အပိုင်းများစွာပါဝင်သော ဂျီဩမေတြီတစ်ခုဖြစ်လျှင် substring ကိုတွက်ချက်သောအခါ ပထမဆုံး အပိုင်းကိုသာ ထည့်သွင်းစဉ်းစားမည်ဖြစ်သည်။


.. figure:: img/substring.png
   :align: center

   အစအကွာအဝေးကို 0 မီတာ နှင့် အဆုံး အကွာအဝေးကို 250 မီတာများတွင် သတ်မှတ်ထားသော substring line

|checkbox| သည် line feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgisextendlines`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line]
     - ထည့်သွင်းအသုံးပြုသော line vector layer
   * - **Start distance** **(အစ အကွာအဝေး)**
     - ``START_DISTANCE``
     - [number |dataDefine|]
     - Ouput feature ၏ အစမှတ်သို့ input line တစ်လျှောက် အကွာအဝေး
   * - **End distance** **(အဆုံး အကွာအဝေး)**
     - ``END_DISTANCE``
     - [number |dataDefine|]
     - Ouput feature ၏အဆုံးမှတ်သို့ input line တစ်လျှောက် အကွာအဝေး
   * - **Substring**
     - ``OUTPUT``
     - [vector: line]

       Default: ``[Create temporary layer]``
     - Output line vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Substring**
     - ``OUTPUT``
     - [vector: line]
     - Output line vector layer

Python code
............

**Algorithm ID**: ``native:linesubstring``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgislinestopolygons:

Lines to polygons (Line များမှ polygon များသို့)
-------------------------------------------------

Input line layer တစ်ခုမှ line များကို polygon ကွင်းများအဖြစ်အသုံးပြုသော polygon layer တစ်ခုကိုဖန်တီးပေးပါသည်။

Output layer ၏ attribute ဇယားသည် input layer ၏ attribute ဇယား နှင့်အတူတူပင် ဖြစ်ပါသည်။

**Default menu**- :menuselection:`Vector --> Geometry Tools`

.. seealso:: :ref:`qgispolygonstolines` ၊ :ref:`qgispolygonize` ၊ :ref:`qgisconvertgeometrytype`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line]
     - ထည့်သွင်းအသုံးပြုသော line vector layer
   * - **Polygons**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output polygon vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Polygons**
     - ``OUTPUT``
     - [vector: polygon]
     - Output polygon vector layer

Python code
............

**Algorithm ID**: ``qgis:linestopolygons``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgismergelines:

Merge lines (Line များကိုပေါင်းခြင်း)
--------------------------------------

အစိတ်အပိုင်းများစွာပါဝင်သော LineString ဂျီဩမေတြီများ၏ ချိတ်ဆက်နေသောအစိတ်အပိုင်းများအားလုံးကို တစ်ခုတည်းပါသော LineString ဂျီဩမေတြီများအဖြစ် ဆက်ပေးပါသည်။

Input MultiLineString ဂျီဩမေတြီများထဲရှိ အစိတ်အပိုင်းများသည် ချိတ်ဆက်မနေလျှင် ရလာဒ်သည် ပေါင်းစည်းနိုင်သော သို့မဟုတ် ချိတ်ဆက်မနေသော line အစိတ်အပိုင်းများပါဝင်သော MultiLineString တစ်ခုဖြစ်နေပါမည်။

|checkbox| သည် line feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line]
     - ထည့်သွင်းအသုံးပြုသော line vector layer
   * - **Merged** **(ပေါင်းစည်းထားပြီးသော)**
     - ``OUTPUT``
     - [vector: line]

       Default: ``[Create temporary layer]``
     - Output line vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Merged** **(ပေါင်းစည်းထားပြီးသော)**
     - ``OUTPUT``
     - [vector: line]
     - Output (ပေါင်းစည်းထားပြီးသော) line vector layer

Python code
............

**Algorithm ID**: ``native:mergelines``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisminimumboundinggeometry:

Minimum bounding geometry (အနည်းဆုံး ဘောင်ခတ်ထားသော ဂျီဩမေတြီ)
---------------------------------------------------------------

Input layer တစ်ခုမှ feature များကို ဝိုင်းကာထားသော ဂျီဩမေတြီများကိုဖန်တီးပေးပါသည်။ Feature များကို field တစ်ခုဖြင့် အုပ်စုဖွဲ့နိုင်ပါသည်။ ထို့နောက် output layer တွင် ကိုက်ညီသောတန်ဖိုးများနှင့် feature များ၏ ဂျီဩမေတြီများကို ခြုံလွှမ်းသော ဂျီဩမေတြီ (MBB) တစ်ခုဖြင့် အုပ်စုတန်ဖိုးတစ်ခုစီတွင် feature တစ်ခုပါဝင်လိမ့်မည်။

အောက်ပါ ဘောင်ခတ်ထားသော ဂျီဩမေတြီ အမျိုးအစားများကို အသုံးပြုနိုင်ပါသည် -

* bounding box (envelope) (ဘောင်ခတ်ထားသော box (စာအိတ်ပုံစံ))
* oriented rectangle (အရပ်မျက်နှာလှည့်ထားသော ထောင့်မှန်စတုဂံ)
* circle (စက်ဝိုင်း)
* convex hull (ခုံးနေသော polygon)

.. figure:: img/minimum_bounding.png
    :align: center

    အပေါ်ဘယ်ဘက်မှ နာရီလက်တံအတိုင်း - စာအိတ်ပုံစံ၊ အရပ်မျက်နှာလှည့်ထားသော ထောင့်မှန်စတုဂံ၊ စက်ဝိုင်း၊ convex hull

.. seealso:: :ref:`qgisminimumenclosingcircle`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Field**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``FIELD``
     - [tablefield: any]
     - Feature များကို field တစ်ခုဖြင့်အုပ်စုဖွဲ့နိုင်ပါသည်။ သတ်မှတ်ထားလျှင် output layer သည် ကိုက်ညီသောတန်ဖိုးများနှင့် feature များကိုသာ ခြုံလွှမ်းသော အနည်းဆုံး ဂျီဩမေတြီ တစ်ခုဖြင့် အုပ်စုဖွဲ့ထားသောတန်ဖိုးတစ်ခုတွင် feature တစ်ခုပါဝင်စေမည်ဖြစ်ပါသည်။
   * - **Geometry type** (**ဂျီဩမေတြီ အမျိုးအစား**)
     - ``TYPE``
     - [enumeration]

       Default: 0
     - ဘောင်ခတ်ထားသော ဂျီဩမေတြီ အမျိုးအစားများ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       * 0 --- Envelope (Bounding Box) (စာအိတ်ပုံစံ (ဘောင်ခတ်ထားသော box))
       * 1 --- Minimum Oriented Rectangle (အနည်းဆုံးလှည့်ထားသော ထောင့်မှန်စတုဂံ)
       * 2 --- Minimum Enclosing Circle (အနည်းဆုံး ဘောင်ခတ်ထားသော စက်ဝိုင်း)
       * 3 --- Convex Hull (ခုံးနေသော polygon)

   * - **Bounding geometry** **(ဘောင်ခတ်ထားသော ဂျီဩမေတြီ)**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output polygon vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Bounding geometry** **(ဘောင်ခတ်ထားသော ဂျီဩမေတြီ)**
     - ``OUTPUT``
     - [vector: polygon]
     - Output (ဘောင်ခတ်ထားသော) polygon vector layer

Python code
............

**Algorithm ID**: ``qgis:minimumboundinggeometry``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisminimumenclosingcircle:

Minimum enclosing circles (အနည်းဆုံး ဘောင်ခတ်ထားသော စက်ဝိုင်းများ)
-------------------------------------------------------------------

Input layer ထဲရှိ feature များ၏ အနည်းဆုံး ဘောင်ခတ်ထားသော စက်ဝိုင်းများကို ဖန်တီးပေးပါသည်။

.. figure:: img/minimum_enclosing_circles.png
   :align: center

   Feature တစ်ခုချင်းစီအတွက် ဘောင်ခတ်ထားသော စက်ဝိုင်းများ

|checkbox| သည် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgisminimumboundinggeometry`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Number of segments in circles** **(စက်ဝိုင်းများထဲရှိ မျဉ်းပိုင်းများ အရေအတွက်)**
     - ``SEGMENTS``
     - [number]

       Default: 72
     - စက်ဝိုင်းတစ်ခုကို ခန့်မှန်းဖန်တီးရန် အသုံးပြုသော မျဉ်းပိုင်းများအရေအတွက်။ အနည်းဆုံး 8 ဖြစ်ပြီး အများဆုံး မှာ 100000 ဖြစ်ပါသည်။
   * - **Minimum enclosing circles** **(အနည်းဆုံး ဘောင်ခတ်ထားသော စက်ဝိုင်းများ)**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output polygon vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Minimum enclosing circles** **(အနည်းဆုံး ဘောင်ခတ်ထားသော စက်ဝိုင်းများ)**
     - ``OUTPUT``
     - [vector: polygon]
     - Output polygon vector layer

Python code
............

**Algorithm ID**: ``native:minimumenclosingcircle``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgismultiringconstantbuffer:

Multi-ring buffer (constant distance) (ကွင်းများစွာ ပါဝင်သော buffer (ပုံသေအကွာအဝေး))
-------------------------------------------------------------------------------------

ပုံသေ သို့မဟုတ် ပြောင်းလဲနေသော အကွာအဝေးနှင့် ကွင်းအရေအတွက်ကိုအသုံးပြုပြီး input layer ၏ feature များအတွက် ကွင်းများစွာ ပါဝင်သော (multi-ring) buffer (*donut*) များဖန်တီးပေးပါသည်။

.. figure:: img/multiringbuffer.png
   :align: center

   Line ၊ point နှင့် polygon layer တစ်ခုအတွက် ကွင်းများစွာ ပါဝင်သော buffer

|checkbox| သည် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgisbuffer` ၊
   :ref:`qgisvariabledistancebuffer` ၊
   :ref:`qgisrectanglesovalsdiamonds` ၊
   :ref:`qgissinglesidedbuffer`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Number of rings** **(ကွင်းအရေအတွက်)**
     - ``RINGS``
     - [number |dataDefine|]

       Default: 1
     - ကွင်းအရေအတွက်။ Unique ဖြစ်သောတန်ဖိုးတစ်ခု ဖြစ်နိုင်ပါသည် (feature အားလုံးအတွက် တူညီသော ကွင်းအရေအတွက်) သို့မဟုတ် feature data မှ ရယူနိုင်ပါသည် (ကွင်းအရေအတွက်သည် feature တန်ဖိုးများပေါ်တွင် မူတည်ပါသည်)။
   * - **Distance between rings** **(ကွင်းများအကြားအကွာအဝေး)**
     - ``DISTANCE``
     - [number |dataDefine|]

       Default: 1.0
     - ကွင်းများအကြားအကွာအဝေး။ Unique ဖြစ်သောတန်ဖိုးတစ်ခု ဖြစ်နိုင်ပါသည် (feature အားလုံးအတွက် တူညီသော ကွင်းအရေအတွက်) သို့မဟုတ် feature data မှ ရယူနိုင်ပါသည် (ကွင်းအရေအတွက်သည် feature တန်ဖိုးများပေါ်တွင် မူတည်ပါသည်)။
   * - **Multi-ring buffer (constant distance)** **(ကွင်းများစွာပါဝင်သော buffer (ပုံသေအကွာအဝေး))**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output polygon vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Multi-ring buffer (constant distance)** **(ကွင်းများစွာပါဝင်သော buffer (ပုံသေအကွာအဝေး))**
     - ``OUTPUT``
     - [vector: polygon]
     - Output polygon vector layer

Python code
............

**Algorithm ID**: ``native:multiringconstantbuffer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgismultiparttosingleparts:

Multipart to singleparts (အစိတ်အပိုင်းများစွာ မှ အစိတ်အပိုင်းတစ်ခုစီ သို့)
---------------------------------------------------------------------------

Layer ထဲမှ အစိတ်အပိုင်းများစွာပါဝင်သော (multipart) feature များကို အစိတ်အပိုင်းတစ်ခုစီဖြစ်သော (singlepart) feature များအဖြစ်သို့ ခွဲထုတ်ပေးပါသည်။

Output layer ၏ attribute များသည် မူရင်း layer ၏ attribute များနှင့် အတူတူဖြစ်ပါသည်။ သို့သော် တစ်ခုစီဖြစ်သော feature များအဖြစ် ခွဲထုတ်ထားပါသည်။

.. figure:: img/multipart.png
   :align: center

   ဘယ်ဘက် - အစိတ်အပိုင်းများစွာပါဝင်သော မူရင်း layer နှင့် ညာဘက် - အစိတ်အပိုင်းတစ်ခုစီဖြစ်သော output ရလာဒ်

|checkbox| သည် point၊ line နှင့် polygon feature များ၏ :ref:`features in-place modification ( နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

**Default menu**- :menuselection:`Vector --> Geometry Tools`

.. seealso:: :ref:`qgiscollect` ၊ :ref:`qgispromotetomulti`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Single parts** **(တစ်ခုစီဖြစ်သော အစိတ်အပိုင်းများ)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output polygon vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Single parts** **(တစ်ခုစီဖြစ်သော အစိတ်အပိုင်းများ)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output vector layer

Python code
............

**Algorithm ID**: ``native:multiparttosingleparts``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisoffsetline:

Offset lines (အရွေ့ line များ)
-------------------------------

သတ်မှတ်ထားသောအကွာအဝေးဖြင့် line များကို နေရာရွှေ့ပေးပါသည်။ အပေါင်းတန်ဖိုး အကွာအဝေးများသည် line များကို ဘယ်ဘက်သို့ ရွှေ့ပေးမည်ဖြစ်ပြီး အနှုတ်တန်ဖိုး အကွာအဝေးများသည် line များကို ညာဘက်သို့ ရွှေ့ပေးမည် ဖြစ်ပါသည်။

.. figure:: img/offset_lines.png
   :align: center

   အပြာရောင်သည် မူရင်း layer ဖြစ်ပြီး အနီရောင်သည် offset layer ဖြစ်ပါသည်

|checkbox| သည် line feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgisarrayoffsetlines` ၊ :ref:`qgistranslategeometry`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line]
     - ထည့်သွင်းအသုံးပြုသော line vector layer
   * - **Distance** **(အကွာအဝေး)**
     - ``DISTANCE``
     - [number |dataDefine|]

       Default: 10.0
     - Offset (အရွေ့) အကွာအဝေး။ အချင်းဝက်ကိုတွက်ထုတ်မည့် field ကိုရွေးချယ်ရန် ညာဘက်တွင်ရှိသော Data Defined ခလုတ်ကိုအသုံးပြုနိုင်ပါသည်။ ၎င်းနည်းလမ်းဖြင့် feature တစ်ခုချင်းစီအတွက် အချင်းဝက်အမျိုးမျိုးကိုရရှိနိုင်မည် ဖြစ်ပါသည် (:ref:`qgisvariabledistancebuffer` တွင်ကြည့်ပါ)။
   * - **Segments** **(မျဉ်းပိုင်းများ)**
     - ``SEGMENTS``
     - [number]

       Default: 8
     - လုံးဝန်းသော offset များကိုဖန်တီးသောအခါ စက်ဝိုင်းလေးပုံတစ်ပုံကို ခန့်မှန်းရန် အသုံးပြုမည့် line မျဉ်းပိုင်းများအရေအတွက်ကို ထိန်းချုပ်ပါသည်။
   * - **Join style** **(အဆက် style)**
     - ``JOIN_STYLE``
     - [enumeration]

       Default: 0
     - Line တစ်ခု၏ ထောင့်များတွင် offset ဖန်တီးသောအခါ round (စောင်းလုံး) ၊ miter (စောင်းတိ) သို့မဟုတ် beveled (စောင်းသတ်) အဆက်ပုံစံကို အသုံးပြုသင့်သည်ကို သတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာနည်းလမ်းများမှာ -

       * 0 --- Round (စောင်းလုံး)
       * 1 --- Miter (စောင်းတိ)
       * 2 --- Bevel (စောင်းသတ်)

       .. figure:: img/buffer_join_style.png
          :align: center
          :width: 100%

          Round ၊ miter နှင့် bevel အဆက် style များ
   * - **Miter limit** **(Miter ကန့်သတ်ချက်)**
     - ``MITER_LIMIT``
     - [number]

       Default: 2.0
     - Offset အကွာအဝေး၏ factor တစ်ခုအဖြစ် miter အဆက် တစ်ခုကိုဖန်တီးသောအခါ အသုံးပြုမည့် offset ဂျီဩမေတြီ မှ အများအဆုံးအကွာအဝေးကို သတ်မှတ်ပါသည် (miter အဆက် style များတွင်သာ အသုံးပြုနိုင်ပါသည်)။ အနည်းဆုံး - 1.0	 

       .. figure:: img/buffer_miter_limit.png
          :align: center
          :width: 100%
         
          ကန့်သတ်ချက် 2 ဖြင့် 10m buffer နှင့် ကန့်သတ်ချက် 1 ဖြင့် 10m buffer
   * - **Offset** **(အရွေ့)**
     - ``OUTPUT``
     - [vector: line]

       Default: ``[Create temporary layer]``
     - Output (offset) layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Offset**
     - ``OUTPUT``
     - [vector: line]
     - Output (offset) line layer

Python code
............

**Algorithm ID**: ``native:offsetline``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisorientedminimumboundingbox:

Oriented minimum bounding box (ဦးတည်ရာအရပ် လှည့်ထားသော အနည်းဆုံး ဘောင်ခတ်ထားသော box)
-------------------------------------------------------------------------------------

Input layer ထဲရှိ feature တစ်ခုချင်းစီအတွက် အနည်းဆုံးဧရိယာ လှည့်ထားသော ထောင့်မှန်စတုဂံ ကိုတွက်ချက်ပေးပါသည်။

.. figure:: img/oriented_minimum_bounding_box.png
   :align: center

   ဦးတည်ရာအရပ် လှည့်ထားသော အနည်းဆုံး ဘောင်ခတ်ထားသော box

|checkbox| သည် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgisminimumboundinggeometry`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Bounding boxes** **(ဘောင်ခတ်ထားသော box များ)**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output polygon vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Bounding boxes** **(ဘောင်ခတ်ထားသော box များ)**
     - ``OUTPUT``
     - [vector: polygon]
     - Output polygon vector layer

Python code
............

**Algorithm ID**: ``native:orientedminimumboundingbox``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisorthogonalize:

Orthogonalize
--------------

Input line သို့မဟုတ် polygon layer ၏ ဂျီဩမေတြီများကို ထောင့်မှန် ဖြစ်အောင်ပြုလုပ်ပေးပါသည်။ ဤလုပ်ငန်းစဉ်သည် ဂျီဩမေတြီထဲရှိ ထောင့်တိုင်းကို ထောင့်မှန်တစ်ခု သို့မဟုတ် မျဉ်းဖြောင့်တစ်ခုဖြစ်အောင် ပြုလုပ်ရန် ဂျီဩမေတြီများထဲရှိ vertex များကိုရွှေ့ပေးခြင်းဖြစ်ပါသည်။

.. figure:: img/orthogonize.png
   :align: center

   အပြာရောင်ဖြင့် မူရင်း layer နှင့် အနီရောင်ဖြင့် orthogonal ပြောင်းထားသော ရလာဒ်

|checkbox| သည် line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line, polygon]
     - ထည့်သွင်းအသုံးပြုသော line သို့မဟုတ် polygon vector layer
   * - **Maximum angle tolerance (degrees)** **(အများဆုံး လက်ခံနိုင်သော ထောင့် (ဒီဂရီ))**
     - ``ANGLE_TOLERANCE``
     - [number]

       Default: 15
     - Vertex တစ်ခုကို ချိန်ညှိရန်အတွက် ၎င်း vertex တစ်ခုအတွက် ရှိနိုင်မည့် ထောင့်မှန်တစ်ခု သို့မဟုတ် မျဉ်းဖြောင့်တစ်ခု မှ အများဆုံး သွေဖယ်မှု ကို သတ်မှတ်ပါသည်။ လက်ခံနိုင်စွမ်း (tolerance) နည်းခြင်းသည် ထောင့်မှန်များနှင့်နီးကပ်နေပြီးသော vertex များကိုသာ ချိန်ညှိမည်ဖြစ်ပြီး လက်ခံနိုင်စွမ်း (tolerance) များခြင်းသည် ထောင့်မှန်များမှ ပိုဝေးဝေးထိ သွေဖယ်နေသော vertex များကိုလည်း ချိန်ညှိပေးမည် ဖြစ်ပါသည်။
   * - **Maximum algorithm iterations** **(အများဆုံး algorithm ထပ်ခါထပ်ခါလုပ်ဆောင်ခြင်းများ)**
     - ``MAX_ITERATIONS``
     - [number]

       Default: 1000
     - ထပ်ခါထပ်ခါလုပ်ဆောင်ခြင်း၏ အများဆုံးအရေအတွက်အတွက် ကိန်းဂဏန်းအကြီးကြီးကို အသုံးပြုလျှင် processing အချိန်ပိုကြာစေပြီး ပို၍ orthogonal ဖြစ်သော ဂျီဩမေတြီတစ်ခုကို ဖန်တီးပေးပါမည်။
   * - **Orthogonalized**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output polygon vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Orthogonalized**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ချိန်ညှိထားသော ထောင့်များပါဝင်သော output polygon vector layer။

Python code
............

**Algorithm ID**: ``native:orthogonalize``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgispointonsurface:

Point on Surface (မျက်နှာပြင်ပေါ်ရှိ အမှတ်)
--------------------------------------------

Input layer ၏ feature တစ်ခုချင်းစီအတွက် feature ဂျီဩမေတြီ၏ မျက်နှာပြင်ပေါ်တွင် ကျရောက်သည်မှာသေချာသော point တစ်ခုကို ပြန်ထုတ်ပေးပါသည်။

|checkbox| သည် point feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgiscentroids`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Create point on surface for each part** **(အစိတ်အပိုင်းတစ်ခုချင်းစီအတွက် မျက်နှာပြင်ပေါ်တွင် point ဖန်တီးခြင်း)**
     - ``ANGLE_TOLERANCE``
     - [boolean |dataDefine|]
     - အမှန်ခြစ်ထားလျှင် ဂျီဩမေတြီ၏အစိတ်အပိုင်းတစ်ခုချင်းစီအတွက် point တစ်ခုကိုဖန်တီးပေးပါမည်။
   * - **Point**
     - ``OUTPUT``
     - [vector: point]

       Default: ``[Create temporary layer]``
     - Output point vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Point**
     - ``OUTPUT``
     - [vector: point]
     - Output point vector layer

Python code
............

**Algorithm ID**: ``native:pointonsurface``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgispointsalonglines:

Points along geometry (ဂျီဩမေတြီ တစ်လျှောက်ရှိ point များ)
-----------------------------------------------------------

Line သို့မဟုတ် polygon ဂျီဩမေတြီများတစ်လျှောက်တွင် အကွာအဝေးတူသော point များဖန်တီးပေးပါသည်။ ဖန်တီးထားသော point များသည် ဂျီဩမေတြီ တစ်လျှောက်အကွာအဝေးနှင့် point နေရာရှိ line ၏ထောင့်အတွက် အချက်အလက်အသစ်များ ပါဝင်လာပါမည်။

ဂျီဩမေတြီ ၏အစနှင့် အဆုံးတို့မှ မည်သည့်အကွာအဝေးတွင် point များကိုဖန်တီးသင့်သည်ကို ထိန်းချုပ်ပေးသော အစနှင့် အဆုံး offset (အရွေ့) တစ်ခုကို သတ်မှတ်ပေးနိုင်ပါသည်။

.. figure:: img/points_along_line.png
   :align: center

   မူရင်း line layer တစ်လျှောက် ဖန်တီးထားသော point များ

.. seealso:: :ref:`qgisinterpolatepoint`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line, polygon]
     - ထည့်သွင်းအသုံးပြုသော line သို့မဟုတ် polygon vector layer
   * - **Distance** **(အကွာအဝေး)**
     - ``DISTANCE``
     - [number |dataDefine|]

       Default: 1.0
     - Line တစ်လျှောက် ကပ်လျှက်ရှိသော point နှစ်ခုများအကြား အကွာအဝေး
   * - **Start offset** **(အစ offset)**
     - ``START_OFFSET``
     - [number |dataDefine|]

       Default: 0.0
     - ပထမ point ၏တည်နေရာကို ကိုယ်စားပြုသော input line ၏အစမှ အကွာအဝေး။
   * - **End offset** **(အဆုံး offset)**
     - ``END_OFFSET``
     - [number |dataDefine|]

       Default: 0.0
     - Point feature ကို ကျော်လွန်ပြီး မဖန်တီးသင့်သော တည်နေရာကို ကိုယ်စားပြုသော input line ၏အဆုံးမှ အကွာအဝေး။
   * - **Interpolated points** **(ဖြည့်စွက်တွက်ထုတ်ထားသော point များ)**
     - ``OUTPUT``
     - [vector: point]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Interpolated points** **(ဖြည့်စွက်တွက်ထုတ်ထားသော point များ)**
     - ``OUTPUT``
     - [vector: point]
     - Input layer ၏ line သို့မဟုတ် polygon နယ်နိမိတ်များတစ်လျှောက်တွင် နေရာချထားသော feature များပါဝင်သော point vector layer။

Python code
............

**Algorithm ID**: ``native:pointsalonglines``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgispointsdisplacement:

Points displacement (Point များအရွေ့)
--------------------------------------

Proximity (အနီးအဝေး) အကွာအဝေးတစ်ခုကိုသတ်မှတ်ပေးပြီး အနီးအနားမှ point feature များကိုဖော်ထုတ်ပြီး စက်ဝိုင်းတစ်ခုအတွင်းတွင် ၎င်း point များကို ဗဟိုမှဖြာထွက်သည့်ပုံစံ (radially) ဖြင့် ဖြန့်ကျက်နေရာချပေးပါသည်။ ထပ်နေသော feature များကို ဖြန့်ကျက်နေရာချရန်အတွက် အသုံးဝင်သော နည်းလမ်းတစ်ခုဖြစ်ပါသည်။

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: point]
     - ထည့်သွင်းအသုံးပြုသော point vector layer
   * - **Minimum distance to other points** **(အခြား point များသို့ အနည်းဆုံးအကွာအဝေး)**
     - ``PROXIMITY``
     - [number]

       Default: 1.0
     - တန်ဖိုးအောက်တွင်ရှိလျှင် point feature များကို နီးစပ်သည်ဟု ယူဆမည့် အကွာအဝေး။ နီးကပ်နေသော feature များကို အတူတကွ ဖြန့်ကျက်နေရချပေးမည်ဖြစ်သည်။
   * - **Displacement distance** **(နေရာအရွှေ့ အကွာအဝေး)**
     - ``DISTANCE``
     - [number]

       Default: 1.0
     - နီးကပ်သော feature များကို နေရာချထားမည့် စက်ဝိုင်း၏ အချင်းဝက်။
   * - **Horizontal distribution for two point case** **(Point နှစ်ခုအတွက် ရေပြင်ညီ ဖြန့်ကျက်နေရာချခြင်း)**
     - ``HORIZONTAL``
     - [boolean]

       Default: False
     - Point နှစ်ခုသည်သာ နီးကပ်သည်ဟု သတ်မှတ်သောအခါ ၎င်း point နှစ်ခုကို ဒေါင်လိုက်အစား ရေပြင်ညီအတိုင်း စက်ဝိုင်းပေါ်တွင် တန်းညီအောင်စီ (align) ပေးမည်ဖြစ်ပါသည်။

   * - **Displaced** **(နေရာရွှေ့ထားပြီးသော)**
     - ``OUTPUT``
     - [vector: point]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Displaced** **(နေရာရွှေ့ထားပြီးသော)**
     - ``OUTPUT``
     - [vector: point]
     - Output point vector layer

Python code
............

**Algorithm ID**: ``qgis:pointsdisplacement``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgispoleofinaccessibility:

Pole of inaccessibility (မရောက်နိုင်သော ဝင်ရိုးအမှတ်)
------------------------------------------------------

Polygon layer တစ်ခုအတွက် မရောက်နိုင်သော ဝင်ရိုးအမှတ် (pole of inaccessibility) ကိုတွက်ချက်ပေးပါသည်။ ၎င်းသည် မျက်နှာပြင်၏ နယ်နိမိတ်မှ အဝေးဆုံးအတွင်းပိုင်း point ဖြစ်ပါသည်။

ယခု algorithm သည် သတ်မှတ်ထားသော tolerance (လက်ခံနိုင်စွမ်း) အတွင်းတွင် မရောက်နိုင်သော ဝင်ရိုးအမှတ် အမှန်ကို ရှာရန်အတွက် ထပ်ခါထပ်ခါ လုပ်ဆောင်သော 'polylabel' algorithm (Vladimir Agafonkin, 2016) ကို အသုံးပြုပါသည်။ ပိုမိုတိကျသော tolerance (နည်းသောတန်ဖိုး) အသုံးပြုပါက ထပ်ခါထပ်ခါလုပ်ဆောင်မှု အကြိမ်ပိုများပြီး တွက်ချက်ချိန် ပိုကြာမည်ဖြစ်ပါသည်။

တွက်ချက်ထားသော ဝင်ရိုးအမှတ်မှ polygon နယ်နိမိတ် သို့အကွာအဝေးကို output layer ထဲတွင် attribute အသစ်တစ်ခုအဖြစ် သိမ်းဆည်းပါမည်။

.. figure:: img/pole_inaccessibility.png
   :align: center

   Pole of inaccessibility (မရောက်နိုင်သော ဝင်ရိုးအမှတ်)

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: polygon]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Tolerance** **(လက်ခံနိုင်စွမ်း)**
     - ``TOLERANCE``
     - [number]

       Default: 1.0
     - တွက်ချက်မှုအတွက် လက်ခံနိုင်စွမ်းကိုသတ်မှတ်ပါ
   * - **Point**
     - ``OUTPUT``
     - [vector: point]

       Default: ``[Create temporary layer]``
     - Output polygon vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Point**
     - ``OUTPUT``
     - [vector: point]
     - Output point vector layer

Python code
............

**Algorithm ID**: ``native:poleofinaccessibility``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgispolygonize:

Polygonize (Polygon ဖန်တီးခြင်း)
---------------------------------

**Closed (အပိတ်ဖြစ်သော)** feature များ၏ line layer တစ်ခုမှ ဖန်တီးထားသော feature နယ်နိမိတ်များရှိသည့် polygon layer တစ်ခုကိုဖန်တီးပေးပါသည်။

.. figure:: img/polygonize.png
   :align: center

   အပိတ်ဖြစ်သော line များမှ ဖန်တီးထားသော အဝါရောင် polygon များ

 
.. note:: Line layer ကို polygon တစ်ခုအဖြစ်ပြောင်းလဲရန် ၎င်း line layer သည် အပိတ်ပုံစံ (အစမှတ်သည် အဆုံးမှတ်ကို ပြန်ဆက်နေခြင်းကို ဆိုလိုပါသည်) ဖြစ်နေရပါမည်။

.. seealso:: :ref:`qgispolygonstolines` ၊ :ref:`qgislinestopolygons` ၊ :ref:`qgisconvertgeometrytype`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line]
     - ထည့်သွင်းအသုံးပြုသော line vector layer
   * - **Keep fields from the input layer** **(Input layer မှ field များကို ဆက်အသုံးပြုခြင်း)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``KEEP_FIELDS``
     - [boolean]

       Default: False
     - Input layer ၏ field များ (ဇယားဖွဲ့စည်းပုံကိုသာ၊ တန်ဖိုးများမပါ) ကို ဆက်လက်အသုံးပြုရန် အမှန်ခြစ်ထားပါ။
   * - **Polygons from lines** **(Line များမှ ရလာသော polygon များ)**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output polygon vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Polygons from lines** **(Line များမှ ရလာသော polygon များ)**
     - ``OUTPUT``
     - [vector: polygon]
     - Line များမှ ရလာသော output polygon vector layer

Python code
............

**Algorithm ID**: ``native:polygonize``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgispolygonstolines:

Polygons to lines (Polygon များမှ line များသို့)
-------------------------------------------------

Polygon layer တစ်ခုကိုယူပြီး input layer ထဲရှိ polygon များ၏ နယ်နိမိတ်များကိုကိုယ်စားပြုသော line များပါဝင်သော line layer တစ်ခုအဖြစ်ဖန်တီးပေးပါသည်။

Output layer ၏ attribute ဇယားသည် input layer ၏ attribute ဇယား နှင့်အတူတူပင် ဖြစ်ပါသည်။

.. figure:: img/polygon_to_lines.png
   :align: center

   အနက်ရောင် line များသည် algorithm ၏ရလာဒ်ဖြစ်ပါသည်

**Default menu**- :menuselection:`Vector --> Geometry Tools`

.. seealso:: :ref:`qgislinestopolygons` ၊ :ref:`qgispolygonize` ၊ :ref:`qgisconvertgeometrytype`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: polygon]
     - ထည့်သွင်းအသုံးပြုသော polygon vector layer
   * - **Lines** **(Line များ)**
     - ``OUTPUT``
     - [vector: line]

       Default: ``[Create temporary layer]``
     - Output line vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Lines** **(Line များ)**
     - ``OUTPUT``
     - [vector: line]
     - Polygon များမှ ဖန်တီးထားသော output line vector layer

Python code
............

**Algorithm ID**: ``native:polygonstolines``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisprojectpointcartesian:

Project points (Cartesian) (Point များကို Cartesian နည်းဖြင့် အရိပ်ချခြင်း)
----------------------------------------------------------------------------

သတ်မှတ်ပေးထားသော အကွာအဝေးတစ်ခုနှင့် ဦးတည်ရာအရပ် (azimuth) တို့ဖြင့် point ဂျီဩမေတြီများကို project (အရိပ်ချ) ပြုလုပ်ပေးပါသည်။

|checkbox| သည် point feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: point]
     - ထည့်သွင်းအသုံးပြုသော point vector layer
   * - **Bearing (degrees from North)** **(ဦးတည်ရာအရပ် (မြောက်အရပ်မှ စတိုင်းတာသော ဒီဂရီ))**
     - ``BEARING``
     - [number |dataDefine|]

       Default: 0.0
     - မြောက်အရပ်မှ စတင်သော နာရီလက်တံအတိုင်းလှည့်သော ထောင့်၊ ဒီဂရီ ယူနစ်ဖြင့် တိုင်းတာသည်
   * - **Distance** **(အကွာအဝေး)**
     - ``DISTANCE``
     - [number |dataDefine|]

       Default: 1.0
     - Offset ဂျီဩမေတြီ များသို့အကွာအဝေး၊ layer ယူနစ်ဖြင့်တိုင်းတာသည်
   * - **Projected** **(ဖန်တီးထားသော)**
     - ``OUTPUT``
     - [vector: point]

       Default: ``[Create temporary layer]``
     - Output point vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Projected**
     - ``OUTPUT``
     - [vector: point]
     - Output (projected) point vector layer 

Python code
............

**Algorithm ID**: ``native:projectpointcartesian``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgispromotetomulti:

Promote to multipart (အစိတ်အပိုင်းများစွာအဖြစ် ပြောင်းလဲခြင်း)
---------------------------------------------------------------

အစိတ်အပိုင်းတစ်ခုတည်းရှိသော ဂျီဩမေတြီများ ပါဝင်သော vector layer ကို ယူပြီး အစိတ်အပိုင်းများစွာရှိသော ဂျီဩမေတြီများပါဝင်သော vector layer တစ်ခုကိုဖန်တီးပေးပါသည်။

အစိတ်အပိုင်းများစွာရှိသော feature များဖြစ်နေပြီးသား input feature များကို ဘာမှ မပြောင်းမလဲပဲ အရင်အတိုင်းပဲ ဆက်ရှိနေပါမည်။

ယခု algorithm ကို အစိတ်အပိုင်းများစွာရှိရန်လိုအပ်သော data provider များနှင့် လိုက်လျောညီထွေဖြစ်စေရန် ဂျီဩမေတြီများကို အစိတ်အပိုင်းများစွာရှိသော အမျိုးအစားအဖြစ် ပြောင်းလဲရာတွင် အသုံးပြုနိုင်ပါသည်။

|checkbox| သည် point၊ line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgisaggregate` ၊ :ref:`qgiscollect`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Multiparts** **(အစိတ်အပိုင်းများစွာပါဝင်သော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output အစိတ်အပိုင်းများစွာပါဝင်သော vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Multiparts** **(အစိတ်အပိုင်းများစွာပါဝင်သော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - အစိတ်အပိုင်းများစွာပါဝင်သော output vector layer

Python code
............

**Algorithm ID**: ``native:promotetomulti``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisrectanglesovalsdiamonds:

Rectangles, ovals, diamonds (ထောင့်မှန်စတုဂံများ၊ ဘဲဥပုံများ နှင့် စိန်ပုံစံများ)
----------------------------------------------------------------------------------

Input point layer ၏ feature တစ်ခုချင်းစီအတွက် ထောင့်မှန်စတုဂံ၊ ဘဲဥပုံ သို့မဟုတ် စိန်ပုံစံ တစ်ခုခုဖြင့် buffer ဧရိယာတစ်ခုကို ဖန်တီးပေးပါသည်။

Feature အားလုံးအတွက် ပုံသဏ္ဍာန် parameter များကို field တစ်ခု သို့မဟုတ် expression တစ်ခုကိုအသုံးပြုပြီး ပြင်ဆင်နိုင်ပါသည်။

.. figure:: img/rectangles_ovals_diamond_variable.png
   :align: center

   အမျိုးမျိုးသော parameter များဖြင့် အမျိုးမျိုးသော buffer ပုံသဏ္ဍာန်များ

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: point]
     - ထည့်သွင်းအသုံးပြုသော point vector layer
   * - **Buffer shape** **(Buffer ပုံသဏ္ဍာန်)**
     - ``SHAPE``
     - [enumeration]
     - အသုံးပြုမည့် ပုံသဏ္ဍာန်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       * 0 --- Rectangles (ထောင့်မှန်စတုဂံများ)
       * 1 --- Ovals (ဘဲဥပုံများ)
       * 2 --- Diamonds (စိန်ပုံစံများ)

   * - **Width** **(အကျယ်များ)**
     - ``WIDTH``
     - [number |dataDefine|]

       Default: 1.0
     - Buffer ပုံသဏ္ဍာန်၏ အကျယ်
   * - **Height** **(အမြင့်)**
     - ``HEIGHT``
     - [number |dataDefine|]

       Default: 1.0
     - Buffer ပုံသဏ္ဍာန်၏ အမြင့်
   * - **Rotation** **(အလှည့်)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``ROTATION``
     - [number |dataDefine|]

       Default: None
     - Buffer ပုံသဏ္ဍာန်၏ အလှည့်
   * - **Number of segments** **(မျဉ်းပိုင်းများအရေအတွက်)**
     - ``SEGMENTS``
     - [number]

       Default: 36
     - စက်ဝိုင်းအပြည့်တစ်ခုအတွက် (*ဘဲဥပုံစံ*) မျဉ်းပိုင်းများအရေအတွက်
   * - **Output**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output**
     - ``OUTPUT``
     - [vector: polygon]
     - ကြားခံဇုံ ပုံစံများဖြင့် output vector layer

Python code
............

**Algorithm ID**: ``native:rectanglesovalsdiamonds``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisremoveduplicatevertices:

Remove duplicate vertices (ပုံတူပွားဖြစ်နေသော vertex များကို ဖယ်ရှားခြင်း)
---------------------------------------------------------------------------

ဂျီဩမေတြီ ကိုအရည်အသွေးမကျသွားစေဘဲ feature များမှ ပုံတူပွားဖြစ်နေသော vertex များကို ဖယ်ရှားပေးပါသည်။

Vertex များသည် တစ်ထပ်တည်း ဖြစ်နေသလားကို ဆုံးဖြတ်သောအခါ ကိုဩဒိနိတ်များအတွက် လက်ခံနိုင်စွမ်း (tolerance) ကို tolerance parameter ဖြင့်သတ်မှတ်ပေးပါသည်။

Default အားဖြင့် အပွားဖြစ်နေသော vertex များကို ရှာဖွေသောအခါ အမြင့်တန်ဖိုးများကိုထည့်သွင်းမစဉ်းစားပါ။ ဥပမာ- vertex နှစ်ခုသည် X နှင့် Y ကိုဩဒိနိတ်များ တူနေပြီး အမြင့် Z တန်ဖိုးမတူလျှင် ပုံတူပွားဖြစ်နေသည်ဟု ယူဆပြီး vertex တစ်ခုကို ဖယ်ပစ်ပေးပါမည်။ :guilabel:`Use Z Value` parameter ကိုအမှန်ခြစ်ထားလျှင် အမြင့်တန်ဖိုးများကိုလည်း ထည့်သွင်းစဉ်းစားပြီး X နှင့် Y တန်ဖိုးများတူနေပြီး အမြင့် Z တန်ဖိုးမတူလျှင် ၎င်း vertex များကို ဆက်လက်ထိန်းထားပါမည် (မဖျက်ပစ်ပါ)။

|checkbox| သည် point၊ line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. note:: အစိတ်အပိုင်းများစွာပါဝင်သော (multipart) ဂျီဩမေတြီတစ်ခု၏ အစိတ်အပိုင်းအမျိုးမျိုးကြားတွင် ပုံတူပွားဖြစ်နေသော vertex များကို မစစ်ဆေးပါ။ ဥပမာ- ထပ်နေသော point များဖြင့် point များစွာပါဝင်သော ဂျီဩမေတြီတစ်ခုကို ယခုနည်းလမ်းဖြင့် ပြောင်းလဲမပေးပါ။

.. seealso:: :ref:`qgisextractvertices` ၊
   :ref:`qgisextractspecificvertices` ၊
   :ref:`qgisdeleteduplicategeometries`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Tolerance** **(လက်ခံနိုင်စွမ်း)**
     - ``TOLERANCE``
     - [number |dataDefine|]

       Default: 0.000001
     - သတ်မှတ်ထားသော အကွာအဝေးထက် ပိုနီးနေသော vertex များကို ပုံတူပွားများအဖြစ် ယူဆပါသည်။
   * - **Use Z value** **(အမြင့်တန်ဖိုးကို အသုံးပြုခြင်း)**
     - ``USE_Z_VALUE``
     - [boolean |dataDefine|]

       Default: False
     - :guilabel:`Use Z Value` parameter ကိုအသုံးပြုလျှင် အမြင့်တန်ဖိုးများကိုလည်း ထည့်သွင်းစဉ်းစားပြီး X နှင့် Y တန်ဖိုးတူနေသော်လည်း အမြင့် Z တန်ဖိုးမတူလျှင် ၎င်း vertex များကို ဆက်လက်ထိန်းထားပါမည် (ဖျက်မပစ်ပါ)။
   * - **Cleaned** **(ရှင်းလင်းထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Cleaned** **(ရှင်းလင်းထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output vector layer (ပုံတူပွားဖြစ်နေသော vertex များမပါဝင်ပဲ)

Python code
............

**Algorithm ID**: ``native:removeduplicatevertices``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisremovenullgeometries:

Remove null geometries (Null ဂျီဩမေတြီများကိုဖယ်ရှားခြင်း)
-----------------------------------------------------------

Vector layer တစ်ခုမှ ဂျီဩမေတြီတစ်ခုမှ မရှိသော မည်သည့် feature များကိုမဆို ဖယ်ရှားပေးပါသည်။ အခြား feature များအားလုံးကို မပြောင်းလဲပဲ မိတ္တူပွားယူပါလိမ့်မည်။

Null ဂျီဩမေတြီ များပါသော feature များကို သီးခြား layer တစ်ခုအဖြစ် သိမ်းဆည်းနိုင်ပါသည်။

:guilabel:`Also remove empty geometries` ကို အမှန်ခြစ်ထားလျှင် ယခု algorithm သည် ကိုဩဒိနိတ်များမရှိသော ဂျီဩမေတြီများပါဝင်သော feature များကို ဖယ်ရှားပေးပါမည်၊ ဥပမာ- ဂျီဩမေတြီ အလွတ်များ။ ထိုကဲ့သို့အခါမျိုးတွင် null output သည် null ဂျီဩမေတြီနှင့် ဂျီဩမေတြီအလွတ်များအပါအဝင် ယခုနည်းလမ်းကို လုပ်ဆောင်ပါမည်။


.. seealso:: :ref:`qgisdeleteduplicategeometries`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer (NULL ဂျီဩမေတြီများမပါသော)
   * - **Also remove empty geometries** **(ဂျီဩမေတြီအလွတ်များကိုလည်း ဖယ်ရှားခြင်း)**
     - ``REMOVE_EMPTY``
     - [boolean]

     - 
   * - **Non null geometries** **(Null ဂျီဩမေတြီ များမဟုတ်သော)**
     - ``OUTPUT``

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Null မဟုတ်သော (ဗလာဖြစ်မနေသော) ဂျီဩမေတြီများအတွက် output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**

   * - **Null geometries** **(Null ဂျီဩမေတြီများ)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``NULL_OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Skip output]``
     - Null (နှင့် အလွတ်ဖြစ်နေသော) ဂျီဩမေတြီများအတွက် output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Null geometries** **(Null ဂျီဩမေတြီများ)**
     - ``NULL_OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output vector layer (Null အတွက်နှင့်၊ ရွေးချယ်ထားလျှင် ဂျီဩမေတြီအလွတ်များ)
   * - **Non null geometries** **(Null မဟုတ်သော ဂျီဩမေတြီများ)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

     - Output vector layer (Null မပါဝင်သော နှင့်၊ ရွေးချယ်ထားလျှင် ဂျီဩမေတြီအလွတ်များ)

Python code
............

**Algorithm ID**: ``native:removenullgeometries``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisreverselinedirection:

Reverse line direction (line ဦးတည်ရာကို ပြောင်းပြန်လှည့်ခြင်း)
---------------------------------------------------------------

Line layer တစ်ခု၏ ဦးတည်ရာကို ပြောင်းပြန်လှန်ပေးပါသည်။

.. figure:: img/reverse_line.png
   :align: center

   ဦးတည်ရာ ပြောင်းပြန်မလှန်မီ နှင့် လှန်ပြီးနောက်

|checkbox| သည် line feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line]
     - ထည့်သွင်းအသုံးပြုသော line vector layer
   * - **Reversed** **(ပြောင်းပြန်လှည့်ထားသော)**
     - ``OUTPUT``
     - [vector: line]

       Default: ``[Create temporary layer]``
     - Output line vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Reversed** **(ပြောင်းပြန်လှည့်ထားသော)**
     - ``OUTPUT``
     - [vector: line]
     - Output line vector layer (ပြောင်းပြန်လှည့်ထားသော line များဖြင့်)

Python code
............

**Algorithm ID**: ``native:reverselinedirection``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisrotatefeatures:

Rotate (လှည့်ခြင်း)
--------------------

နာရီလက်တံအတိုင်း သတ်မှတ်ထားသော ထောင့်တစ်ခုဖြင့် feature ဂျီဩမေတြီများကို လှည့်ပေးပါသည်။ Feature တစ်ခုချင်းစီ၏ အလယ်ဗဟိုအမှတ် ပတ်ပတ်လည်တွင် လှည့်ပါသည် သို့မဟုတ် တမူထူးခြားသော ကြိုတင်သတ်မှတ်ထားသည့် point ပတ်ပတ်လည်တွင်လည်း လှည့်နိုင်ပါသည်။

|checkbox| သည် point၊ line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgistranslategeometry` ၊ :ref:`qgisswapxy`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Rotation (degrees clockwise)** **(အလှည့် (ဒီဂရီဖြင့် နာရီလက်တံအတိုင်း))**
     - ``ANGLE``
     - [number |dataDefine|]

       Default: 0.0
     - ဒီဂရီဖြင့် လှည့်ထောင့်
   * - **Rotation anchor point (x, y)** **(လှည့်ခြင်းအတွက် အခြေပြု point (x ၊ y))**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``ANCHOR``
     - [point]

       Default: None
     - Feature များကိုပတ်ပတ်လည် လှည့်ရန် အသုံးပြုသော point ၏ X ၊ Y ကိုဩဒိနိတ်။ သတ်မှတ်မထားလျှင် လှည့်ပတ်မှုသည် feature တစ်ခုချင်းစီ၏ အလယ်ဗဟိုအမှတ်တွင် လုပ်ဆောင်ပါမည်။
   * - **Rotated** **(လှည့်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer (လှည့်ထားသော ဂျီဩမေတြီများဖြင့်) ကိုသတ်မှတ်ပါ။ အောက်တို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Rotated** **(လှည့်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - လှည့်ထားသော ဂျီဩမေတြီများပါဝင်သော output vector layer

Python code
............

**Algorithm ID**: ``native:rotatefeatures``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisroundness:

Roundness (လုံးဝန်းမှု)
------------------------

Feature တစ်ခုချင်းစီ၏ လုံးဝန်းမှု ကိုတွက်ချက်ပြီး ၎င်းကို field အသစ်ထဲတွင် သိမ်းဆည်းပေးပါသည်။ Input vector layer တွင် polygon များပါဝင်ရပါမည်။

Polygon တစ်ခု၏လုံးဝန်းမှုကို 4π × polygon area / perimeter² အနေဖြင့်သတ်မှတ်ပါသည်။ လုံးဝန်းမှုတန်ဖိုးသည် 0 နှင့် 1 ကြားတွင် ရှိပါသည်။ အတိအကျစက်ဝိုင်းပုံစံ လုံးဝန်းနေသော polygon သည် လုံးဝန်းမှုတန်ဖိုး 1 ရှိပြီး လုံးဝပြားနေသော polygon သည် လုံးဝန်းမှုတန်ဖိုး 0 ရှိပါသည်။

.. note:: Algorithm သည် အစိတ်အပိုင်းများစွာပါဝင်သော (multipart) polygon feature များအတွက် Null တန်ဖိုးကိုပြန်ထုတ်ပေးပါသည်။

|checkbox| သည် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: polygon]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Roundness** **(လုံးဝန်းမှု)**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output vector layer (လုံးဝန်းမှု field ဖြင့်) ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Rotated** **(လှည့်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Field တစ်ခုထဲတွင် လုံးဝန်းမှုတန်ဖိုးပါဝင်သော output vector layer

Python code
............

**Algorithm ID**: ``native:roundness``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgissegmentizebymaxangle:

Segmentize by maximum angle (အကြီးဆုံးထောင့်ဖြင့် မျဉ်းပိုင်းများဖန်တီးခြင်း)
------------------------------------------------------------------------------

ကွေးနေသော အပိုင်းများကို မျဉ်းဖြောင့်အပိုင်းများအဖြစ် ပြောင်းပေးခြင်းဖြင့် ဂျီဩမေတြီ တစ်ခုကို မျဉ်းပိုင်းများဖန်တီးပေးပါသည်။

ဖြောင့်နေသော ဂျီဩမေတြီပေါ်ရှိ vertex နှစ်ခုအကြား အများဆုံးခွင့်ပြုထားသော အချင်းဝက်ထောင့်ကို သတ်မှတ်ပေးခြင်းဖြင့် မျဉ်းပိုင်းများဖန်တီးခြင်းကို လုပ်ဆောင်ပါသည် (ဥပမာ- ဖြောင့်နေသော ဂျီဩမေတြီပေါ်တွင် မူရင်း စက်ဝန်းပြတ် (arc) ဗဟိုမှ ကပ်လျှက်ရှိသော output vertex များသို့ ဖန်တီးထားသော စက်ဝန်းပြတ် (arc)ထောင့်)။ ကွေးမနေသော ဂျီဩမေတြီများကို မပြောင်းလဲပဲ အရှိအတိုင်း ဆက်လက်ထိန်းထားပါမည်။

.. seealso:: :ref:`qgissegmentizebymaxdistance` ၊
   :ref:`qgissimplifygeometries` ၊ :ref:`qgissmoothgeometry`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line, polygon]
     - ထည့်သွင်းအသုံးပြုသော line သို့မဟုတ် polygon vector layer
   * - **Maximum angle between vertices (degrees)** **(Vertex များအကြား အများဆုံးထောင့် (ဒီဂရီ))**
     - ``ANGLE``
     - [number |dataDefine|]

       Default: 5.0
     - ဖြောင့်နေသော ဂျီဩမေတြီပေါ်ရှိ vertex နှစ်ခုအကြား ခွင့်ပြုသောအများဆုံး အချင်းဝက်ထောင့်
   * - **Segmentized** **(မျဉ်းပိုင်းများဖန်တီးထားသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``

     - Output vector layer (မျဉ်းပိုင်းများပြောင်းထားသော ဂျီဩမေတြီများဖြင့်) ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Segmentized** **(မျဉ်းပိုင်းများပြောင်းထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - မျဉ်းပိုင်းများပြောင်းထားပြီးသော ဂျီဩမေတြီများပါဝင်သော output vector layer

Python code
............

**Algorithm ID**: ``native:segmentizebymaxangle``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgissegmentizebymaxdistance:

Segmentize by maximum distance (အများဆုံးအကွာအဝေးဖြင့် မျဉ်းပိုင်းများဖန်တီးခြင်း)
-----------------------------------------------------------------------------------

ကွေးနေသော အပိုင်းများကို မျဉ်းဖြောင့်အပိုင်းများအဖြစ် ပြောင်းပေးခြင်းဖြင့် ဂျီဩမေတြီတစ်ခုကို မျဉ်းပိုင်းများဖန်တီးပေးပါသည်။

မူရင်းမျဉ်းကွေးနှင့် မျဉ်းပိုင်းများပြောင်းထားသော ကိုယ်စားပြုမှုကြားရှိ အများဆုံးခွင့်ပြုထားသော offset (အရွေ့) အကွာအဝေးကို သတ်မှတ်ပေးခြင်းဖြင့် မျဉ်းပိုင်းများဖန်တီးခြင်းကို လုပ်ဆောင်ပါသည်။ ကွေးမနေသော ဂျီဩမေတြီများကို မပြောင်းလဲပဲ အရှိအတိုင်းဆက်လက်ထိန်းထားပါမည်။

.. seealso:: :ref:`qgissegmentizebymaxangle` ၊
   :ref:`qgissimplifygeometries` ၊ :ref:`qgissmoothgeometry`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line, polygon]
     - ထည့်သွင်းအသုံးပြုသော line သို့မဟုတ် polygon vector layer
   * - **Maximum offset distance** **(အများဆုံး offset အကွာအဝေး)**
     - ``DISTANCE``
     - [number |dataDefine|]

       Default: 1.0
     - မူရင်းမျဉ်းကွေးနှင့် မျဉ်းပိုင်းများပြောင်းထားသော ကိုယ်စားပြုမှုကြားရှိ အများဆုံးခွင့်ပြုထားသော Layer ယူနစ်ဖြင့် offset အကွာအဝေး။
   * - **Segmentized** **(မျဉ်းပိုင်းများပြောင်းထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer (မျဉ်းပိုင်းများပြောင်းထားသော ဂျီဩမေတြီများဖြင့်) ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Segmentized** **(မျဉ်းပိုင်းများပြောင်းထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - မျဉ်းပိုင်းများပြောင်းထားပြီးသော ဂျီဩမေတြီများပါဝင်သည့် output vector layer

Python code
............

**Algorithm ID**: ``native:segmentizebymaxdistance``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgissetmvalue:

Set M value (M တန်ဖိုးကို သတ်မှတ်ခြင်း)
----------------------------------------

Layer တစ်ခုအတွင်းရှိ ဂျီဩမေတြီများအတွက် M တန်ဖိုးကိုသတ်မှတ်ပေးပါသည်။

Layer ထဲတွင် M တန်ဖိုးရှိနေပြီးသား ဖြစ်နေလျှင် ၎င်းတန်ဖိုးများကို တန်ဖိုးအသစ်များဖြင့် အစားထိုးပြင်ဆင်ပါမည်။ M တန်ဖိုးမရှိသေးလျှင်၊ M တန်ဖိုးနှင့် ဂျီဩမေတြီများအားလုံးအတွက် ကနဦး M တန်ဖိုးအဖြစ်အသုံးပြုသော သတ်မှတ်တန်ဖိုးများ ပါဝင်လာစေရန် ဂျီဩမေတြီကိုအဆင့်မြှင့်ပေးပါလိမ့်မည်။
    
|checkbox| သည် M တန်ဖိုးရှိသော point၊ line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. tip:: ပေါင်းထည့်ထားသော M တန်ဖိုးကို စစ်ဆေးရန် |identify|:sup:`Identify Features` ခလုတ်ကို အသုံးပြုပါ- ရလာဒ်များကို :guilabel:`Identify Results` dialog တွင် ကြည့်နိုင်ပါသည်။

.. seealso:: :ref:`qgissetmfromraster` ၊ :ref:`qgissetzvalue` ၊
   :ref:`qgisdropmzvalues`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **M Value** **(M တန်ဖိုး)**
     - ``M_VALUE``
     - [number |dataDefine|]

       Default: 0.0
     - Feature ဂျီဩမေတြီများကို သတ်မှတ်ပေးမည့် M တန်ဖိုး
   * - **M Added** **(M တန်ဖိုး ပေါင်းထည့်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **M Added** **(M တန်ဖိုး ပေါင်းထည့်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output vector layer (ဂျီဩမေတြီများသို့ သတ်မှတ်ထားသော M တန်ဖိုးများဖြင့်)

Python code
............

**Algorithm ID**: ``native:setmvalue``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgissetmfromraster:

Set M value from raster (Raster မှ M တန်ဖိုး သတ်မှတ်ခြင်း)
-----------------------------------------------------------

Feture ဂျီဩမေတြီထဲတွင် ထပ်နေသော vertex တိုင်းအတွက် M တန်ဖိုးကို သတ်မှတ်ရန် raster layer တစ်ခုအတွင်းရှိ band တစ်ခုမှ နမူနာတန်ဖိုးများကို အသုံးပြုပါသည်။ Raster တန်ဖိုးများကို ကြိုတင်သတ်မှတ်ထားသောပမာဏတစ်ခုဖြင့် စကေးချိန်ကိုက်နိုင်ပါသည်။

Layer ထဲတွင် M တန်ဖိုးရှိနေပြီးသားဆိုလျှင် ၎င်းတို့ကို တန်ဖိုးအသစ်တစ်ခုဖြင့် အစားထိုးလုပ်ဆောင်ပါမည်။ M တန်ဖိုးမရှိလျှင်၊ M တန်ဖိုးပါလာစေရန် ဂျီဩမေတြီကို အဆင့်မြှင့် လုပ်ဆောင်ပါမည်။

|checkbox| သည် M တန်ဖိုးရှိသော point၊ line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgissetzfromraster` ၊ :ref:`qgissetmvalue`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Raster layer**
     - ``RASTER``
     - [raster]
     - M တန်ဖိုးများဖြင့် raster layer
   * - **Band number** **(Band နံပါတ်)**
     - ``BAND``
     - [raster band]

       Default: 1
     - M တန်ဖိုးများ ရယူမည့် raster band
   * - **Value for nodata or non-intersecting vertices** **(Nodata သို့မဟုတ် ထိဖြတ်မနေသော vertex များအတွက် တန်ဖိုး)**
     - ``NODATA``
     - [number |dataDefine|]

       Default: 0.0
     - Vertex များသည် raster ၏ကောင်းမွန်စွာအသုံးပြုနိုင်သော pixel တစ်ခုကို မထိဖြတ်လျှင် အသုံးပြုမည့် တန်ဖိုး
   * - **Scale factor** **(စကေး factor)**
     - ``SCALE``
     - [number |dataDefine|]

       Default: 1.0
     - Scaling တန်ဖိုး - band တန်ဖိုးများကို ယခုတန်ဖိုးဖြင့် မြှောက်ပေးမည် ဖြစ်ပါသည်။
   * - **Offset** **(အရွေ့)**
     - ``OFFSET``
     - [number |dataDefine|]

       Default: 0.0
     - Offset တန်ဖိုး - "Scale factor" ကိုအသုံးပြုပြီးနောက် ၎င်း offset တန်ဖိုးကို သင်္ချာနည်းအရ band တန်ဖိုးများဆီကို ပေါင်းထည့်ပါသည်။
   * - **Updated** **(အသစ်ပြောင်းလဲထားသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer (update ပြုလုပ်ထားသော M တန်ဖိုးများဖြင့်) ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Updated**  **(အသစ်ပြောင်းလဲထားသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output vector layer (update ပြုလုပ်ထားသော M တန်ဖိုးများဖြင့်)

Python code
............

**Algorithm ID**: ``native:setmfromraster``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgissetzvalue:

Set Z value (Z တန်ဖိုးကို သတ်မှတ်ခြင်း)
----------------------------------------

Layer တစ်ခုအတွင်းရှိ ဂျီဩမေတြီများအတွက် အမြင့် Z တန်ဖိုးကိုသတ်မှတ်ပေးပါသည်။

Layer ထဲတွင် အမြင့် Z တန်ဖိုးရှိနေပြီးသား ဖြစ်နေလျှင် ၎င်းတန်ဖိုးများကို တန်ဖိုးအသစ်များဖြင့် အစားထိုးပြင်ဆင်ပါမည်။ အမြင့် Z တန်ဖိုးမရှိသေးလျှင် အမြင့် Z တန်ဖိုးနှင့် ဂျီဩမေတြီများအားလုံးအတွက် ကနဦး အမြင့် Z တန်ဖိုးအဖြစ်အသုံးပြုသော သတ်မှတ်တန်ဖိုးများ ပါဝင်လာစေရန် ဂျီဩမေတြီကို အဆင့်မြှင့်ပေးပါမည်။
 
|checkbox| သည် အမြင့် Z တန်ဖိုးပါရှိသည့် point၊ line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. tip:: ပေါင်းထည့်ထားသော အမြင့် Z တန်ဖိုးကို စစ်ဆေးရန် |identify|:sup:`Identify Features` ခလုတ်ကို အသုံးပြုပါ၊ ရလာဒ်များကို :guilabel:`Identify Results` dialog တွင် ကြည့်နိုင်ပါသည်။

.. seealso:: :ref:`qgissetzfromraster` ၊ :ref:`qgissetmvalue` ၊
   :ref:`qgisdropmzvalues`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Z Value** **(အမြင့်တန်ဖိုး)**
     - ``Z_VALUE``
     - [number |dataDefine|]

       Default: 0.0
     - Feature ဂျီဩမေတြီတွင် သတ်မှတ်ပေးမည့် အမြင့် Z တန်ဖိုး
   * - **Z Added** **(အမြင့် Z တန်ဖိုး ပေါင်းထည့်ထားသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Z Added** **(အမြင့် Z တန်ဖိုး ပေါင်းထည့်ထားသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output vector layer (သတ်မှတ်ထားသော အမြင့် Z တန်ဖိုးများဖြင့်)

Python code
............

**Algorithm ID**: ``native:setzvalue``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**

.. _qgissimplifygeometries:

Simplify (Vertex များကိုလျှော့ချပြီး ရိုးရှင်းအောင်ပြုလုပ်ခြင်း)
-----------------------------------------------------------------

Line သို့မဟုတ် polygon layer တစ်ခုထဲရှိ ဂျီဩမေတြီများကို ရိုးရှင်းအောင်ပြုလုပ်ပေးပါသည်။ Input layer ထဲရှိ feature များအတိုင်း တူညီသော feature များပါဝင်သော layer အသစ်တစ်ခုကို ဖန်တီးပေးပါသည်၊ သို့သော် ဂျီဩမေတြီများတွင် vertex အရေအတွက် နည်းသွားမည်ဖြစ်ပါသည်။

ယခု algorithm တွင် အကွာအဝေးကို အခြေခံသော ("Douglas-Peucker" algorithm)၊ ဧရိယာကိုအခြေခံသော ("Visvalingam" algorithm) နှင့် grid သို့ ဂျီဩမေတြီများဆွဲကပ်ခြင်းတို့ ပါဝင်သော ရိုးရှင်းအောင်ပြုလုပ်ခြင်းဆိုင်ရာ နည်းလမ်းများကို ရွေးချယ်နိုင်ပါသည်။

.. figure:: img/simplify_geometries.png
   :align: center

   ဘယ်ဘက်အပေါ်မှ နာရီလက်တံအတိုင်း - မူရင်း layer နှင့် simplification လက်ခံနိုင်စွမ်းများ တိုးလာခြင်း

|checkbox| သည် line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

**Default menu**- :menuselection:`Vector --> Geometry Tools`

.. seealso:: :ref:`qgissmoothgeometry` ၊ :ref:`qgisdensifygeometries` ၊
 :ref:`qgisdensifygeometriesgivenaninterval`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line, polygon]
     - ထည့်သွင်းအသုံးပြုသော line သို့မဟုတ် polygon vector layer
   * - **Simplification method** **(ရိုးရှင်းအောင်ပြုလုပ်ခြင်း နည်းလမ်းများ)**
     - ``METHOD``
     - [enumeration]

       Default: 0
     - ရိုးရှင်းအောင်ပြုလုပ်ခြင်း နည်းလမ်း။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       * 0 --- Distance (Douglas-Peucker) (အကွာအဝေး (Douglas-Peucker))
       * 1 --- Snap to grid (Grid ကိုဆွဲကပ်ခြင်း)
       * 2 --- Area (Visvalingam) (ဧရိယာ (Visvalingam))

   * - **Tolerance** **(လက်ခံနိုင်စွမ်း)**
     - ``TOLERANCE``
     - [number |dataDefine|]


       Default: 1.0
     - လက်ခံနိုင်စွမ်း သတ်မှတ်ချက် (layer ယူနစ်များဖြင့်) - ဆုံမှတ်နှစ်ခုကြား အကွာအဝေးသည် လက်ခံနိုင်စွမ်းတန်ဖိုးထက် ပိုငယ်နေလျှင် မျဉ်းပိုင်းကို ရိုးရှင်းအောင်ပြုလုပ်ပြီး vertex များကို ဖယ်ရှားပစ်ပါမည်။
   * - **Simplified** **(ရိုးရှင်းအောင်ပြုလုပ်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer (ရိုးရှင်းအောင်ပြုလုပ်ထားပြီးသော) ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် - 

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Simplified** **(ရိုးရှင်းအောင်ပြုလုပ်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output (ရိုးရှင်းအောင်ပြုလုပ်ထားပြီးသော) vector layer

Python code
............

**Algorithm ID**: ``native:simplifygeometries``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgissinglesidedbuffer:

Single sided buffer (တစ်ဖက်တည်း ရှိသော ကြားခံဇုံ)
--------------------------------------------------

သတ်မှတ်ထားသော အကွာအဝေးတစ်ခုဖြင့် Line ၏ တစ်ဖက်တည်းတွင်သာ buffer တစ်ခု ဖန်တီးပေးပါသည်။

Buffer သည် အမြဲတမ်း polygon layer အဖြစ် ရရှိပါမည်။

.. figure:: img/single_side_buffer.png
   :align: center

   တူညီသော Vector line layer တစ်ခုတည်းပေါ်ရှိ ဘယ်ဘက်နှင့် ညာဘက် buffer

.. seealso:: :ref:`qgisbuffer`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line]
     - ထည့်သွင်းအသုံးပြုသော line vector layer
   * - **Distance** **(အကွာအဝေး)**
     - ``DISTANCE``
     - [number]

       Default: 10.0
     - Buffer အကွာအဝေး။
   * - **Side** (**ဘက် (ဘယ်/ညာ)**)
     - ``SIDE``
     - [enumeration]
  
       Default: 0
     - မည်သည့်ဘက်ခြမ်းတွင် buffer ကို ဖန်တီးမည်ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် - 

       * 0 -- Left (ဘယ်)
       * 1 -- Right (ညာ)

   * - **Segments** **(မျဉ်းပိုင်းများ)**
     - ``SEGMENTS``
     - [number]

       Default: 8
     - လုံးဝန်းသော offset များကိုဖန်တီးသောအခါ စက်ဝိုင်းလေးပုံတစ်ပုံ ကိုခန့်မှန်းရန်အတွက် အသုံးပြုသော line segment များအရေအတွက်ကို ထိန်းချုပ်ပါသည်။
   * - **Join style** **(အဆက် style)**
     - ``JOIN_STYLE``
     - [enumeration]

       Default: 0
     - Line တစ်ခုတွင် ထောင့်များကို offset ဖန်တီးသောအခါ round (လုံးဝန်းသော)၊ miter (စောင်းတိ) သို့မဟုတ် bevel (စောင်းသတ်) မည်သည့်နည်းလမ်းဖြင့် ဆက်မည်ကို သတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာ နည်းလမ်းများမှာ-

       * 0 --- Round (လုံးဝန်းသော)
       * 1 --- Miter (စောင်းတိ)
       * 2 --- Bevel (စောင်းသတ်)
  
       .. figure:: img/buffer_join_style.png
          :align: center
          :width: 100%

          Round ၊ miter နှင့် bevel အဆက် style များ
   * - **Miter limit** **(Miter ကန့်သတ်ချက်)**
     - ``MITER_LIMIT``
     - [number]

       Default: 2.0
     - Offset အကွာအဝေး၏ factor တစ်ခုအဖြစ် (miter အဆက် style တွင်သာ အသုံးပြုနိုင်ပါသည်) miter နည်းဖြင့် အဆက် တစ်ခုကို ဖန်တီးသောအခါ အသုံးပြုမည့် offset ဂျီဩမေတြီ မှ အများဆုံးအကွာအဝေးကို သတ်မှတ်ပေးပါသည်။ အနည်းဆုံး- 1.0
                     
       .. figure:: img/buffer_miter_limit.png
          :align: center
          :width: 100%
         
          ကန့်သတ်ချက် 2 ဖြင့် 10 မီတာ buffer တစ်ခုနှင့် ကန့်သတ်ချက် 1 ဖြင့် 10 မီတာ buffer တစ်ခု
   * - **Buffer** **(ကြားခံဇုံ)**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output (buffer) layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Buffer** **(ကြားခံဇုံ)**
     - ``OUTPUT``
     - [vector: polygon]
     - Output (buffer) polygon layer

Python code
............

**Algorithm ID**: ``native:singlesidedbuffer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgissmoothgeometry:

Smooth (ချောမွေ့စေခြင်း)
-------------------------

Feature ဂျီဩမေတြီများတွင် **vertex များနှင့် ထောင့်များ** ထပ်ပေါင်းထည့်ခြင်းဖြင့် line သို့မဟုတ် polygon layer တစ်ခုရှိ ဂျီဩမေတြီများကို ချောမွေ့အောင် လုပ်ဆောင်ပေးပါသည်။

ဂျီဩမေတြီ တစ်ခုချင်းစီကို ချောမွေ့စေရန် ထပ်ခါထပ်ခါလုပ်ဆောင်ခြင်းများ (iterations) အကြိမ်ရေမည်မျှလုပ်ဆောင်မည်ကို iterations parameter ကဆုံးဖြတ်ပေးပါသည်။ Iteration များလေလေ ဂျီဩမေတြီ များထဲမှ vertex များပိုများပြီး ပိုမိုချောမွေ့သော ဂျီဩမေတြီများကိုရရှိစေမည် ဖြစ်ပါသည်။ 

.. figure:: img/smooth_geometry_1.png
    :align: center

    Iteration ပိုများလေလေ ဂျီဩမေတြီများ ပိုမိုချောမွေ့လေလေဖြစ်ပါသည်

ချောမွေ့အောင်လုပ်ထားသော ဂျီဩမေတြီများသည် မူရင်း ဂျီဩမေတြီများကို မည်မျှ "" လိုက်ပေးသည်ကို  Offset parameter မှထိန်းချုပ်ပေးပါသည်။ ဂဏန်းတန်ဖိုးသေးလျှင် ပိုစိတ်စိတ်လုပ်ပေးပြီး ဂဏန်းကြီးလျှင် ခပ်ကျဲကျဲလုပ်ပေးပါသည်။

.. figure:: img/smooth_geometry_2.png
    :align: center

    အပြာ - input layer။ Offset 0.25 သည် အနီရောင် line ကိုဖြစ်စေပြီး offset 0.50 သည် အစိမ်းရောင် line ကိုဖြစ်စေပါသည်။

ဆုံမှတ်များကို ထောင့်အကျယ်ကြီးများဖြင့် ချောမွေ့စေခြင်းမဖြစ်စေရန် အကြီးဆုံးထောင့် parameter ကိုအသုံးပြုနိုင်ပါသည်။ မျဉ်းပိုင်းများ၏ ထောင့်များသည် ယခုတန်ဖိုးထက် ပိုကြီးနေလျှင် ချောမွေ့စေခြင်းကို လုပ်ဆောင်ပေးမည်မဟုတ်ပါ။ ဥပမာ- အကြီးဆုံးထောင့်ကို 90 ဒီဂရီနှင့် အောက်ကိုထားလျှင် ဂျီဩမေတြီထဲတွင် ထောင့်မှန်များကို ချောမွေ့အောင် လုပ်ဆောင်ပေးမည်မဟုတ်ပါ။

|checkbox| သည် line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgissimplifygeometries` ၊
   :ref:`qgisdensifygeometries` ၊
   :ref:`qgisdensifygeometriesgivenaninterval`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line, polygon]
     - ထည့်သွင်းအသုံးပြုသော line သို့မဟုတ် polygon vector layer
   * - **Iterations** **(ထပ်ခါထပ်ခါလုပ်ဆောင်ခြင်းများ)**
     - ``ITERATIONS``
     - [number |dataDefine|]

       Default: 1
     - Iteration အရေအတွက်ကို တိုးပေးလျှင် ပိုမိုချောမွေ့သော ဂျီဩမေတြီများကို ရရှိပါမည် (vertex များပိုပါလာခြင်း)။
   * - **Offset** **(အရွေ့)**
     - ``OFFSET``
     - [number |dataDefine|]

       Default: 0.25
     - တန်ဖိုးများကို မြှင့်တင်ခြင်းသည် ချောမွေ့သော line များ/ နယ်နိမိတ်များကို input line များ/ နယ်နိမိတ်များ မှ ပိုဝေးရာဆီသို့ *ရွှေ့* ပေးပါမည်။
   * - **Maximum node angle to smooth** **(ချောမွေ့စေရန် အကြီးဆုံး ဆုံမှတ် ထောင့်)**
     - ``MAX_ANGLE``
     - [number |dataDefine|]

       Default: 180.0
     - ယခုတန်ဖိုးထက်ပိုနည်းသော ဆုံမှတ်တိုင်းကို ချောမွေ့အောင် လုပ်ဆောင်ပေးပါမည်
   * - **Smoothed** **(ချောမွေ့အောင်လုပ်ဆောင်ထားသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output (ချောမွေ့အောင်လုပ်ဆောင်ထားသော) layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Smoothed** **(ချောမွေ့အောင်လုပ်ဆောင်ထားသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output (ချောမွေ့အောင်လုပ်ဆောင်ထားသော) vector layer

Python code
............

**Algorithm ID**: ``native:smoothgeometry``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgissnapgeometries:

Snap geometries to layer (ဂျီဩမေတြီများကို layer သို့ဆွဲကပ်ခြင်း)
------------------------------------------------------------------

Layer တစ်ခုထဲမှ ဂျီဩမေတြီများကို အခြား layer မှ ဂျီဩမေတြီများသို့ သို့မဟုတ် တူညီသော layer မှ ဂျီဩမေတြီ များသို့ ဆွဲကပ်ပေးပါသည်။

Matching (ယှဉ်တွဲခြင်း) သည် လက်ခံနိုင်စွမ်း (tolerance) အကွာအဝေးပေါ်တွင် အခြေခံပြီး ဂျီဩမေတြီများသည် အကိုးအကား ဂျီဩမေတြီများနှင့် ကိုက်ညီစေရန် vertex များကို အသစ်ထည့်ခြင်း သို့မဟုတ် ရှိနေသော vertex များ ဖယ်ရှားခြင်းများကို လိုအပ်သလို လုပ်ဆောင်ပါသည်။

|checkbox| သည် point၊ line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgissnappointstogrid`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Reference layer** **(အကိုးအကား layer)**
     - ``REFERENCE_LAYER``
     - [vector: any]
     - ဆွဲကပ်မည့် vector layer
   * - **Tolerance** **(လက်ခံနိုင်စွမ်း)**
     - ``TOLERANCE``
     - [number]


       Default: 10.0
     - Input vertex များသည် အကိုးအကား layer ဂျီဩမေတြီ များသို့ မဆွဲကပ်မီ ၎င်းတို့သည် မည်မျှနီးနီးကပ်ကပ်ရှိရန် လိုအပ်မည်ကို ထိန်းချုပ်ပေးပါသည်။
   * - **Behavior** **(အပြုအမူ)**
     - ``BEHAVIOR``
     - [enumeration]

       Default: 0
     - Snapping (ဆွဲကပ်ခြင်း) ကို ရှိနေပြီးသား ဆုံမှတ်တစ်ခုသို့ သို့မဟုတ် မျဉ်းပိုင်းတစ်ခုသို့ (vertex သို့ ရွှေ့ရမည့် အနီးဆုံး point) လုပ်ဆောင်နိုင်ပါသည်။ အသုံးပြုနိုင်သော ဆွဲကပ်ခြင်း နည်းလမ်းများမှာ - 
 
       * 0 --- တန်းညှိ (align) ထားသော ဆုံမှတ်များကိုဦးစားပေးပြီး လိုအပ်သောနေရာများတွင် vertex အပိုများထည့်ခြင်း
    
         မျဉ်းပိုင်းတစ်ခုသည် ဆုံမှတ်တစ်ခုနှင့်ပိုနီးနေလျှင်တောင်မှ ဆုံမှတ်များသို့ ဆွဲကပ်ခြင်းကို ဦးစားပေးပါသည်။ ခွင့်ပြုနိုင်သော လက်ခံနိုင်စွမ်း အတွင်းရှိသောအခါ ဂျီဩမေတြီများသည် တစ်ခုနောက်ကိုတစ်ခု အတိအကျလိုက်သွားစေရန် ဆုံမှတ်အသစ်များကို ထည့်ပေးပါမည်။

       * 1 --- အနီးဆုံးအမှတ်ကို ဦးစားပေးပြီး လိုအပ်သောနေရာတွင် vertex အပိုများထည့်ခြင်း
   
         ဆုံမှတ်ပဲဖြစ်စေ မျဉ်းပိုင်းပဲဖြစ်စေ အနီးဆုံးအမှတ်ကို ဆွဲကပ်ပေးပါသည်။ ခွင့်ပြုနိုင်သော လက်ခံနိုင်စွမ်း အတွင်းရှိသောအခါ ဂျီဩမေတြီများသည် တစ်ခုနောက်ကိုတစ်ခု အတိအကျလိုက်သွားစေရန် ဆုံမှတ်အသစ်များကို ထည့်ပေးပါမည်။

       * 2 --- တန်းညှိ (align) ထားသော ဆုံမှတ်များကိုဦးစားပေးပြီး vertex အသစ်များ မထည့်ခြင်း
   
         မျဉ်းပိုင်းတစ်ခုသည် ဆုံမှတ်တစ်ခုနှင့်ပိုနီးနေလျှင်တောင်မှ ဆုံမှတ်များကို ဆွဲကပ်ခြင်းကို ဦးစားပေးပါသည်။ ဆုံမှတ်အသစ်များကို ထပ်ထည့်ပေးမည်မဟုတ်ပါ။

       * 3 --- အနီးဆုံးအမှတ်ကို ဦးစားပေးပြီး vertex အသစ်များ မထည့်ခြင်း
   
         ဆုံမှတ်ပဲဖြစ်စေ မျဉ်းပိုင်းပဲဖြစ်စေ အနီးဆုံးအမှတ်ကို ဆွဲကပ်ပေးပါသည်။ ဆုံမှတ်အသစ်များကို ထပ်ထည့်ပေးမည်မဟုတ်ပါ။

       * 4 --- အဆုံးမှတ်များကိုသာရွှေ့ပြီး တန်းညှိ (align) ထားသော ဆုံမှတ်များကိုဦးစားပေးခြင်း
   
         Line များ၏ အစမှတ်/အဆုံးမှတ်များကိုသာ ဆွဲကပ်ပေးပါသည် (point feature များကိုလည်းဆွဲကပ်မည်ဖြစ်ပါသည်၊ polygon feature များကို ပြင်ဆင်မည်မဟုတ်ပါ)။ ဆုံမှတ်များကို ဦးစားပေးဆွဲကပ်ပါမည်။

       * 5 --- အဆုံးမှတ်များကိုသာရွှေ့ပြီး အနီးဆုံးအမှတ်ကို ဦးစားပေးခြင်း
   
         Line များ၏ အစမှတ်/အဆုံးမှတ်များကိုသာ ဆွဲကပ်ခြင်း (point feature များကိုလည်းဆွဲကပ်မည်ဖြစ်ပါသည်၊ polygon feature များကို ပြင်ဆင်မည်မဟုတ်ပါ)။ အနီးဆုံးအမှတ်ကို ဆွဲကပ်ပါမည်။

       * 6 --- အဆုံးမှတ်များကို အဆုံးမှတ်များသို့သာ ဆွဲကပ်ခြင်း

         Line များ၏ အစမှတ်/အဆုံးမှတ်များကို တခြား line များ၏ အစမှတ်/အဆုံးမှတ်များကိုသာ ဆွဲကပ်ပေးပါသည်။   
   
       * 7 --- နေရာအသေချထားသော ဆုံမှတ်များကို ဆွဲကပ်ခြင်း (layer တစ်ခုတည်းအတွက်သာ)	   

   * - **Snapped geometry** **(ဆွဲကပ်ထားသော ဂျီဩမေတြီ)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output (ဆွဲကပ်ထားသော) layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Snapped geometry** **(ဆွဲကပ်ထားသော ဂျီဩမေတြီ)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output (ဆွဲကပ်ထားသော) vector layer

Python code
............

**Algorithm ID**: ``native:snapgeometries``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgissnappointstogrid:

Snap points to grid (Point များကို grid သို့ဆွဲကပ်ခြင်း)
---------------------------------------------------------

Point များ သို့မဟုတ် vertex များအားလုံးကို grid တစ်ခု၏အနီးဆုံး point ကို ဆွဲကပ်စေရန် vector layer ထဲရှိ ဂျီဩမေတြီများ၏ ကိုဩဒိနိတ်များကို ပြင်ဆင်ပေးပါသည်။

ဆွဲကပ်ထားသော ဂျီဩမေတြီကိုမတွက်ချက်နိုင်လျှင် (သို့မဟုတ် လုံးဝပျက်စီးနေလျှင်) feature ၏ ဂျီဩမေတြီ ကိုရှင်းလင်းပစ်ပါမည်။

ဆွဲကပ်ခြင်းကို X၊ Y၊ Z သို့မဟုတ် M ဝင်ရိုးများပေါ်တွင် လုပ်‌ဆောင်နိုင်ပါသည်။ မည်သည့် ဝင်ရိုးအတွက်မဆို grid အစိတ်အကျဲ (spacing) 0 သည် ၎င်းဝင်ရိုးအတွက် ဆွဲကပ်ခြင်းကို ပိတ်ပစ်ပါလိမ့်မည်။

|checkbox| သည် point၊ line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. note:: အချို့ ထောင့်နေရာများတွင် grid သို့ ဆွဲကပ်ခြင်းသည် အမှားပါဝင်ပြီးဆီလျော်မှုမရှိသော ဂျီဩမေတြီတစ်ခုကို ထုတ်ပေးနိုင်ပါသည်။ 

.. seealso:: :ref:`qgissnapgeometries`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **X Grid Spacing** **(X Grid အစိတ်အကျဲ)**
     - ``HSPACING``
     - [number |dataDefine|]

       Default: 1.0
     - X ဝင်ရိုးပေါ်ရှိ grid spacing
   * - **Y Grid Spacing** **(Y Grid အစိတ်အကျဲ)**
     - ``VSPACING``
     - [number |dataDefine|]

       Default: 1.0
     - Y ဝင်ရိုးပေါ်ရှိ grid spacing	 
   * - **Z Grid Spacing** **(Z Grid အစိတ်အကျဲ)**
     - ``ZSPACING``
     - [number |dataDefine|]

       Default: 0.0
     - Z ဝင်ရိုးပေါ်ရှိ grid spacing	 
   * - **M Grid Spacing** **(M Grid အစိတ်အကျဲ)**
     - ``MSPACING``
     - [number |dataDefine|]

       Default: 0.0
     - M ဝင်ရိုးပေါ်ရှိ grid spacing
   * - **Snapped** **(ဆွဲကပ်ထားသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output (ဆွဲကပ်ထားသော) layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Snapped** **(ဆွဲကပ်ထားသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

     - Output (ဆွဲကပ်ထားသော) vector layer 

Python code
............

**Algorithm ID**: ``native:snappointstogrid``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgissplitlinesbylength:

Split lines by maximum length (အရှည်ဆုံးအလျားဖြင့် line များကိုခွဲထုတ်ခြင်း)
-----------------------------------------------------------------------------

Line (သို့မဟုတ် မျဉ်းကွေး) တစ်ခုကိုယူပြီး feature တစ်ခုချင်းစီကို အစိတ်အပိုင်းများစွာအဖြစ် ပိုင်းခြားပေးပြီး အစိတ်အပိုင်းတစ်ခုချင်းစီသည် သတ်မှတ်ထားသော အရှည်ဆုံးအလျားတစ်ခုဖြစ်သည်။ Line substring အသစ်များ၏ အစနှင့် အဆုံးရှိ Z နှင့် M တန်ဖိုးများကို ရှိနေပြီးသားတန်ဖိုးများမှ အဖြောင့်အတိုင်း interpolate (ဖြည့်စွက်တွက်ထုတ်) ပြုလုပ်ပေးပါသည်။

|checkbox| သည် line feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line]
     - ထည့်သွင်းအသုံးပြုသော line vector layer
   * - **Maximum line length** **(အရှည်ဆုံး line အလျား)**
     - ``LENGTH``
     - [number |dataDefine|]

       Default: 10.0
     - Output ထဲရှိ line တစ်ခု၏ အရှည်ဆုံးအလျား
   * - **Split** **(ခွဲထုတ်ထားသော)**
     - ``OUTPUT``
     - [vector: line]

       Default: ``[Create temporary layer]``
     - Output line vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်

   * - **Split** **(ခွဲထုတ်ထားသော)**
     - ``OUTPUT``
     - [vector: line]
     - Line vector layer အသစ် - Feature ဂျီဩမေတြီများ၏အလျားသည် LENGTH parameter ထဲတွင် သတ်မှတ်ထားသော အလျားထက် ပိုတိုသည် သို့ အလျားနှင့်တူညီပါသည်။

Python code
............

**Algorithm ID**: ``native:splitlinesbylength``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgissubdivide:

Subdivide (ထပ်ဆင့်ပိုင်းခြားခြင်း) 
------------------------------------

ဂျီဩမေတြီ ကို ထပ်ဆင့်ပိုင်းခြားပေးပါသည်။ ပြန်လည်ထုတ်ပေးသော ဂျီဩမေတြီသည် မူရင်း ဂျီဩမေတြီမှ ထပ်ဆင့်ပိုင်းခြားထားသော အပိုင်းများပါဝင်သော စုစည်းမှုတစ်ခုဖြစ်နေပါလိမ့်မည်။ သတ်မှတ်ထားသောအများဆုံး ဆုံမှတ်အရေအတွက်ထက် ပိုသော ဆုံမှတ်များရှိသည့် အပိုင်းများရှိမည်မဟုတ်ပါ။

ရှုပ်ထွေးနေသော ဂျီဩမေတြီကို ရှုပ်ထွေးမှုနည်းသော အစိတ်အပိုင်းများအဖြစ် ပိုင်းခြားရာတွင် အသုံးဝင်ပြီး တည်နေရာအရ ညွှန်းပေးရန်လွယ်ကူသလို တည်နေရာနှင့်သက်ဆိုင်သော လုပ်ငန်းဆောင်တာများကို မြန်ဆန်စွာ လုပ်ဆောင်နိုင်စေပါသည်။ ကွေးညွတ်နေသော ဂျီဩမေတြီများကို ထပ်ဆင့်ပိုင်းခြားခြင်းမပြုလုပ်မီတွင် မျဉ်းပိုင်းများအဖြစ်ပြုလုပ်ပေးမည်ဖြစ်သည်။

.. figure:: img/subdivide.png
   :align: center

   ဘယ်ဘက်သည် input layer၊ အလယ်တွင် အများဆုံး ဆုံမှတ်တန်ဖိုး 100 ဖြစ်ပြီး ညာဘက်တွင် အများဆုံး တန်ဖိုး 200 ဖြစ်ပါသည်

|checkbox| သည် point၊ line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. note:: ဂျီဩမေတြီတစ်ခုကို ထပ်ဆင့်ပိုင်းခြားခြင်းသည် ဆီလျော်မှုမရှိသော ဂျီဩမေတြီ အစိတ်အပိုင်းများနှင့် အချင်းချင်းပြန်ထိဖြတ်နေသော အစိတ်အပိုင်းများ ပါလာနိုင်ပါသည်။   

.. seealso:: :ref:`qgisexplodelines` ၊ :ref:`qgislinesubstring`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်

   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Maximum nodes in parts** **(အစိတ်အပိုင်းများရှိ အများဆုံး ဆုံမှတ်များ)**
     - ``MAX_NODES``
     - [number |dataDefine|]

       Default: 256
     - ဂျီဩမေတြီ အစိတ်အပိုင်းအသစ်တစ်ခုစီတွင် ရှိခွင့်ပြုသော အများဆုံး ဆုံမှတ်အရေအတွက်။ ဂဏန်းတန်ဖိုးပိုမြင့်လေလေ *Sub-parts (အစိတ်အပိုင်းအခွဲများ)* ပိုနည်းလေလေ ဖြစ်ပါသည်။
   * - **Subdivided** **(ထပ်ဆင့်ပိုင်းခြားထားသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output (ထပ်ဆင့်ပိုင်းခြားထားသော) vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်

   * - **Subdivided** **(ထပ်ဆင့်ပိုင်းခြားထားသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output vector layer

Python code
............

**Algorithm ID**: ``native:subdivide``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisswapxy:

Swap X and Y coordinates (X နှင့် Y ကိုဩဒိနိတ်များကို နေရာဖလှယ်ခြင်း)
----------------------------------------------------------------------

Input ဂျီဩမေတြီများတွင် X နှင့် Y ကိုဩဒိနိတ်တန်ဖိုးများကို နေရာဖလှယ်ပေးပါသည်။

လတ္တီကျုနှင့် လောင်ဂျီကျုတန်ဖိုးများ နေရာချင်းမှားထည့်ထားခဲ့မိသော ဂျီဩမေတြီများကို ပြန်လည်ပြင်ဆင်ရန်အတွက် အသုံးပြုနိုင်ပါသည်။

|checkbox| သည် point၊ line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgistranslategeometry` ၊ :ref:`qgisrotatefeatures`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်

   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Swapped** **(နေရာချင်းဖလှယ်ထားသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်

   * - **Swapped** **(နေရာချင်းဖလှယ်ထားသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output (နေရာချင်းဖလှယ်ထားသော) vector layer

Python code
............

**Algorithm ID**: ``native:swapxy``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgistaperedbuffer:

Tapered buffers (အဖျားရှူးသွားသော ကြားခံဇုံများ)
-------------------------------------------------

သတ်မှတ်ထားသော အစနှင့် အဆုံး buffer အချင်းမျဉ်းတန်ဖိုးများကိုအသုံးပြုပြီး line ဂျီဩမေတြီများတစ်လျှောက်တွင် အဖျားရှူးသွားသော buffer ကိုဖန်တီးပေးပါသည်။

.. figure:: img/tapered_buffer.png
   :align: center

   အဖျားရှူးသွားသော buffer ဥပမာ

.. seealso:: :ref:`qgisbufferbym` ၊ :ref:`qgisbuffer` ၊
   :ref:`qgiswedgebuffers`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line]
     - ထည့်သွင်းအသုံးပြုသော line vector layer
   * - **Start width** **(အစအကျယ်)**
     - ``START_WIDTH``
     - [number |dataDefine|]

       Default: 0.0
     - Line feature ၏ အစမှတ်တွင် အသုံးပြုသော buffer ၏ အချင်းဝက်ကို ကိုယ်စားပြုပါသည်။
   * - **End width** **(အဆုံးအကျယ်)**
     - ``END_WIDTH``
     - [number |dataDefine|]

       Default: 0.0
     - Line feature ၏ အဆုံးမှတ်တွင် အသုံးပြုသော buffer ၏ အချင်းဝက်ကို ကိုယ်စားပြုပါသည်။
   * - **Segments** **(မျဉ်းပိုင်းများ)**
     - ``SEGMENTS``
     - [number |dataDefine|]

       Default: 16
     - လုံးဝန်းသော offset များကိုဖန်တီးသောအခါ စက်ဝိုင်းလေးပုံတစ်ပုံ ကိုခန့်မှန်းရန်အတွက် အသုံးပြုသော line segment များအရေအတွက်ကို ထိန်းချုပ်ပါသည်။
   * - **Buffered** **(Buffer ပြုလုပ်ထားသော)**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output (Buffer ပြုလုပ်ထားသော) layer။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Buffered** **(Buffer ပြုလုပ်ထားသော)**
     - ``OUTPUT``
     - [vector: polygon]
     - Output (Buffer ပြုလုပ်ထားသော) polygon layer

Python code
............

**Algorithm ID**: ``native:taperedbuffer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgistessellate:

Tessellate (အကွက်များဖန်တီးခြင်း)
----------------------------------

ဂျီဩမေတြီများကို တြိဂံပုံစံအပိုင်းများအဖြစ် ပိုင်းခြားပြီး polygon ဂျီဩမေတြီ layer တစ်ခုကို အကွက်များ ဖန်တီးပေးပါသည်။

Output layer တွင် input feature တစ်ခုချင်းစီအတွက် multipolygon ဂျီဩမေတြီများ ပါဝင်ပြီး multipolygon တစ်ခုချင်းစီတွင် များစွာသော တြိဂံ polygon များစွာပါဝင်ပါသည်။

.. figure:: img/tessellated.png
   :align: center

   အကွက်များဖန်တီးထားသော polygon (ညာဘက်)

|checkbox| သည် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: polygon]
     - ထည့်သွင်းအသုံးပြုသော polygon vector layer
   * - **Tesselated** **(အကွက်များဖန်တီးထားသော)**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Tesselated** **(အကွက်များဖန်တီးထားသော)**
     - ``OUTPUT``
     - [vector: polygon]
     - Polygon များစွာပါဝင်သော output layer

Python code
............

**Algorithm ID**: ``3d:tessellate``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgistransect:

Transect
---------

Linestring (များစွာ) အတွက် vertex များပေါ်တွင် transect များကို ဖန်တီးပေးပါသည်။

Transect ဆိုသည်မှာ ထောင့်တစ်ခုမှ (default အားဖြင့် ထောင့်မှန်) input polyline သို့ (vertex များတွင်) လှည့်ထားသော line တစ်ခုဖြစ်ပါသည်။

Feature (များ) မှ field (များ) ကို အောက်ပါ field အသစ်များဖြင့် transect ထဲတွင် ပြန်ထုတ်ပေးပါသည် -

* TR_FID: မူရင်း feature ၏ ID
* TR_ID: Transect ၏ ID။ Transect တစ်ခုချင်းစီသည် မတူညီသော ID တစ်ခုစီ ရှိပါသည်
* TR_SEGMENT: Linestring ၏ မျဉ်းပိုင်း၏ ID
* TR_ANGLE: Vertex တွင် မူရင်း line မှ ဒီဂရီဖြင့်ထောင့်
* TR_LENGTH: ပြန်ထုတ်ပေးသော transect ၏ စုစုပေါင်းအလျား
* TR_ORIENT: Transect ၏ ဘေးဘက် (line ၏ ဘယ်ဘက် သို့မဟုတ် ညာဘက်၊ သို့မဟုတ် နှစ်ဖက်လုံး))

.. figure:: img/transect.png
   :align: center

   အနီရောင် dash line များသည် input line layer ၏ transect ကိုကိုယ်စားပြုပါသည်

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line]
     - ထည့်သွင်းအသုံးပြုသော line vector layer
   * - **Length of the transect** **(Transect ၏ အလျား)**
     - ``LENGTH``
     - [number |dataDefine|]

       Default: 5.0
     - Transect ၏ မြေပုံ ယူနစ်ဖြင့် အလျား
   * - **Angle in degrees from the original line at the vertices** **(Vertex များ၌ မူရင်း line မှ ဒီဂရီဖြင့်ထောင့်)**
     - ``ANGLE``
     - [number |dataDefine|]

       Default: 90.0
     - Transect ၏ထောင့်ကို ပြောင်းလဲခြင်း
   * - **Side to create the transect** **(Transect ကိုဖန်တီးရန် ဘေးဘက်)**
     - ``SIDE``
     - [enumeration]
     - Transect ၏ ဘေးဘက် ကိုရွေးချယ်ခြင်း။ အသုံးပြုနိုင်သော နည်းလမ်းများမှာ -

       * 0 --- Left (ဘယ်)
       * 1 --- Right (ညာ)
       * 2 --- Both (နှစ်ဖက်စလုံး)

   * - **Transect**
     - ``OUTPUT``
     - [vector: line]

       Default: ``[Create temporary layer]``
     - Output line layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Transect**
     - ``OUTPUT``
     - [vector: line]
     - Output line layer

Python code
............

**Algorithm ID**: ``native:transect``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgistranslategeometry:

Translate (နေရာရွှေ့ခြင်း)
---------------------------

ကြိုတင်သတ်မှတ်ထားသည့် X နှင့် Y နေရာအရွေ့တန်ဖိုးဖြင့် layer တစ်ခုအတွင်းမှ ဂျီဩမေတြီများကို ရွှေ့ပေးပါသည်။

ဂျီဩမေတြီထဲတွင်ကိုယ်စားပြုသော Z တန်ဖိုးနှင့် M တန်ဖိုးများကိုလည်း ရွှေ့နိုင်ပါသည်။

.. figure:: img/translate_geometry.png
   :align: center

   Dash line များသည် input layer ၏နေရာရွှေ့ထားသော ဂျီဩမေတြီကိုကိုယ်စားပြုပါသည် 

|checkbox| သည် point၊ line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်ပေးနိုင်ပါသည်။

.. seealso:: :ref:`qgisarraytranslatedfeatures` ၊
   :ref:`qgisoffsetline` ၊ :ref:`qgisrotatefeatures` ၊ :ref:`qgisswapxy`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Offset distance (x-axis)** **(Offset အကွာအဝေး (x ဝင်ရိုး))**
     - ``DELTA_X``
     - [number |dataDefine|]

       Default: 0.0
     - X ဝင်ရိုးပေါ်တွင် လုပ်ဆောင်မည့် အရွှေ့
   * - **Offset distance (y-axis)** **(Offset အကွာအဝေး (y ဝင်ရိုး))**
     - ``DELTA_Y``
     - [number |dataDefine|]

       Default: 0.0
     - Y ဝင်ရိုးပေါ်တွင် လုပ်ဆောင်မည့် အရွှေ့ 
   * - **Offset distance (z-axis)** **(Offset အကွာအဝေး (Z ဝင်ရိုး))**
     - ``DELTA_Z``
     - [number |dataDefine|]

       Default: 0.0
     - Z ဝင်ရိုးပေါ်တွင် လုပ်ဆောင်မည့် အရွှေ့ 
   * - **Offset distance (m values)** **(Offset အကွာအဝေး (M တန်ဖိုးများ))**
     - ``DELTA_M``
     - [number |dataDefine|]

       Default: 0.0
     - M ဝင်ရိုးပေါ်တွင် လုပ်ဆောင်မည့် အရွှေ့ 
   * - **Translated** **(နေရာရွှေ့ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့မှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Translated** **(နေရာရွှေ့ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output vector layer

Python code
............

**Algorithm ID**: ``native:translategeometry``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisbufferbym:

Variable width buffer (by M value)  (အကျယ်ပြောင်းလဲနိုင်သော ကြားခံဇုံ (M တန်ဖိုးဖြင့်))
----------------------------------------------------------------------------------------

Vertex တစ်ခုချင်းစီတွင် buffer ၏ အချင်းမျဉ်းအဖြစ် line ဂျီဩမေတြီများ၏ M တန်ဖိုးကို အသုံးပြုပြီး line များတစ်လျှောက်တွင် အကျယ်ပြောင်းလဲနိုင်သော buffer များကို ဖန်တီးပေးပါသည်။

.. figure:: img/variable_buffer_m.png
   :align: center

   ပြောင်းလဲနိုင်သော buffer ဥပမာ

.. seealso:: :ref:`qgistaperedbuffer` ၊ :ref:`qgisbuffer` ၊
   :ref:`qgissetmvalue` ၊ :ref:`qgisvariabledistancebuffer`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line]
     - ထည့်သွင်းအသုံးပြုသော line vector layer
   * - **Segments** **(မျဉ်းပိုင်းများ)**
     - ``SEGMENTS``
     - [number |dataDefine|]

       Default: 16
     - စက်ဝိုင်းလေးပုံတစ်ပုံချင်းစီအတွက် buffer မျဉ်းပိုင်းများအရေအတွက်။ ၎င်းသည် unique ဖြစ်သောတန်ဖိုးတစ်ခု ဖြစ်နိုင်သလို (feature များအားလုံးအတွက် တူညီသောတန်ဖိုး) သို့မဟုတ် ၎င်းကို feature data မှလည်း ရယူနိုင်ပါသည် (တန်ဖိုးသည် feature attribute များပေါ်တွင် မူတည်နိုင်ပါသည်)
   * - **Buffered** **(ကြားခံဇုံလုပ်ထားသော)**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output (buffer) layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့မှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Buffered** **(ကြားခံဇုံလုပ်ထားသော)**
     - ``OUTPUT``
     - [vector: polygon]
     - ပြောင်းလဲနိုင်သော buffer polygon layer

Python code
............

**Algorithm ID**: ``native:bufferbym``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisvoronoipolygons:

Voronoi polygons (Voronoi polygon များ)
----------------------------------------

Point layer တစ်ခုကိုယူပြီး ၎င်းအမှတ်များနှင့် သက်ဆိုင်သော Voronoi polygons (Thiessen polygon များ ဟုလည်းခေါ်သော) များပါဝင်သော polygon layer တစ်ခုကိုဖန်တီးပေးပါသည်။

Voronoi polygon တစ်ခုထဲတွင်ပါဝင်သော တည်နေရာတိုင်းသည် အခြား point များထက် ၎င်းနှင့်သက်ဆိုင်သော point နှင့် ပိုမိုနီးကပ်ပါသည်။

.. figure:: img/voronoi.png
   :align: center

   Voronoi polygon များ

**Default menu**- :menuselection:`Vector --> Geometry Tools`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: point]
     - ထည့်သွင်းအသုံးပြုသော point vector layer
   * - **Buffer region (% of extent)** **(Buffer နယ်ပယ် (extent ၏ရာခိုင်နှုန်း))**
     - ``BUFFER``
     - [number]

       Default: 0.0
     - Output layer ၏ extent သည် input layer ၏ extent ထက် ယခု ပမာဏလောက် ပိုကြီးပါလိမ့်မည်။
   * - **Voronoi polygons** **(Voronoi polygon များ)**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output layer (Voronoi polygon များပါဝင်သော) ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Voronoi polygons**
     - ``OUTPUT``
     - [vector: polygon]
     - Input point vector layer ၏ Voronoi polygon များ

Python code
............

**Algorithm ID**: ``qgis:voronoipolygons``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |arrowDown| image:: /static/common/mActionArrowDown.png
   :width: 1.5em
.. |arrowUp| image:: /static/common/mActionArrowUp.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |clearText| image:: /static/common/mIconClearText.png
   :width: 1.5em
.. |dataDefine| image:: /static/common/mIconDataDefine.png
   :width: 1.5em
.. |deleteAttribute| image:: /static/common/mActionDeleteAttribute.png
   :width: 1.5em
.. |identify| image:: /static/common/mActionIdentify.png
   :width: 1.5em
.. |newAttribute| image:: /static/common/mActionNewAttribute.png
   :width: 1.5em
