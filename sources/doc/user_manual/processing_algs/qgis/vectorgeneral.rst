Vector general (Vector ဆိုင်ရာ အထွေထွေ)
========================================

.. only:: html

   .. contents::
      :local:
      :depth: 1
      :class: toc-columns


.. _qgisassignprojection:

Assign projection (မြေပုံအရိပ်ချစနစ် သတ်မှတ်ခြင်း)
---------------------------------------------------

Vector layer တစ်ခုတွင် projection (မြေပုံအရိပ်ချစနစ်) အသစ်တစ်ခုအား သတ်မှတ်ထည့်သွင်းပေးပါသည်။

Input layer တစ်ခုနှင့် အတိအကျတူသည့် feature များနှင့်ဂျီဩမေတြီများရှိသည့် layer အသစ်တစ်ခုကိုဖန်တီးပေးပါသည်။ သို့သော် CRS အသစ်တစ်ခုကိုအသုံးပြုမည်ဖြစ်သည်။ ဂျီဩမေတြီများကို projection တစ်ခုမှတစ်ခုသို့ပြောင်းလဲခြင်း (reprojection) **မဟုတ်** ဘဲ မတူညီသော  CRS တစ်ခုကိုသာထည့်သွင်းလိုက်ခြင်းဖြစ်သည်။

ဤ algorithm အား မမှန်ကန်သော projection သတ်မှတ်ထားမိသည့် layer များကိုပြင်ဆင်ရန် အသုံးပြုနိုင်ပါသည်။

ဤ algorithm သည် Attribute များကို ပြောင်းလဲပြင်ဆင်မည်မဟုတ်ပါ။

.. seealso:: :ref:`qgisdefinecurrentprojection` ၊
   :ref:`qgisfindprojection` ၊ :ref:`qgisreprojectlayer`

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
     - CRS မှားယွင်းနေသော သို့မဟုတ် CRS မပါရှိသော vector layer 
   * - **Assigned CRS** **(သတ်မှတ်ပေးမည့် CRS)**
     - ``CRS``
     - [crs]
       
       Default: ``EPSG:4326 - WGS84``
     - Vector layer တွင်သတ်မှတ်အသုံးပြုရမည့် CRS အသစ်ကိုရွေးချယ်ပါ
   * - **Assigned CRS** **(CRS သတ်မှတ်ထားပြီးသော)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer အားသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Assigned CRS** **(CRS သတ်မှတ်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - သတ်မှတ်ထည့်သွင်းထားသည့် projection ဖြင့် vector layer

Python code
............

**Algorithm ID**: ``native:assignprojection``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisbatchnominatimgeocoder:

Batch Nominatim geocoder (အစုလိုက် Nominatim geocode ပြုလုပ်ပေးသည့်အရာ)
------------------------------------------------------------------------

String (စာသား) field ပါရှိသော input layer တစ်ခုအတွက် Nominatim service ကို အသုံးပြု၍ အစုလိုက် geocoding(လိပ်စာများနှင့် နေရာအမည်များအား ပထဝီဝင်ဆိုင်ရာ ကိုဩဒိနိတ်များအဖြစ်ပြောင်းလဲခြင်း) ကိုလုပ်ဆောင်ပေးပါသည်။ Output layer တွင် ကိုဩဒိနိတ်ဖြင့် ပြောင်းလဲဖော်ပြထားသော တည်နေရာအပြင် ၎င်း တည်နေရာနှင့်ဆက်စပ်နေသည့် attribute အချို့ ကိုကိုယ်စားပြုသည့် point ဂျီဩမေတြီတစ်ခု ပါဝင်ပါလိမ့်မည်။

|checkbox| တွင် အမှန်ခြစ်ပေးခြင်းဖြင့် point feature များအတွက် :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကိုအသုံးပြုနိုင်ပါသည်။

.. note:: ဤ algorithm သည် OpenStreetMap ဖောင်ဒေးရှင်းမှ ပံ့ပိုးသော Nominatim geocoding ဝန်ဆောင်မှု၏ `အသုံးပြုမှု မူဝါဒ <https://operations.osmfoundation.org/policies/nominatim/>`_ ကို လိုက်နာပါသည်။
 
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
     - Feature များကို geocode ပြုလုပ်ရမည့် vector layer
   * - **Address field** **(လိပ်စာဖော်ပြထားသော field)**
     - ``FIELD``
     - [tablefield: string]
     - Geocode ပြုလုပ်ရန် လိပ်စာများပါဝင်သော Field
   * - **Geocoded** **(Geocode ပြုလုပ်ထားသော)**
     - ``OUTPUT``
     - [vector: point]

       Default: ``[Create temporary layer]``
     - Geocode ပြုလုပ်ထားပြီးသော လိပ်စာ များသာပါဝင်သော output layer အား သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Geocoded** **(Geocode ပြုလုပ်ထားသော)**
     - ``OUTPUT``
     - [vector: point]
     - Geocode ပြုလုပ်ထားသော လိပ်စာများနှင့်သက်ဆိုင်သော point feature များပါဝင်သည့် vector layer

Python code
............

**Algorithm ID**: ``native:batchnominatimgeocoder``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgislayertobookmarks:

Convert layer to spatial bookmarks (Layer ကို တည်နေရာဆိုင်ရာ bookmark များအဖြစ်ပြောင်းခြင်း)
---------------------------------------------------------------------------------------------

Layer တစ်ခုတွင်ပါဝင်သည့် feature များ၏ extent နှင့် သက်ဆိုင်သော spatial (တည်နေရာဆိုင်ရာ) bookmark များကိုဖန်တီးပေးပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input Layer** **(ထည့်သွင်းအသုံးပြုသော Layer)**
     - ``INPUT``
     - [vector: line, polygon]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Bookmark destination** **(Bookmark ထားရှိမည့် နေရာ)**
     - ``DESTINATION``
     - [enumeration]
       
       Default: 0
     - Bookmark များအတွက် ထားရှိမည့်နေရာကိုရွေးချယ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-
       
       * 0 --- Project bookmarks
       * 1 --- User bookmarks
   * - **Name field** **(အမည် field)**
     - ``NAME_EXPRESSION``
     - [expression]
     - ထွက်ရှိလာသော bookmark များအား အမည်ပေးမည့် Field သို့မဟုတ် expression  
   * - **Group field** **(အုပ်စု field)**
     - ``GROUP_EXPRESSION``
     - [expression]
     - ထွက်ရှိလာသော bookmark များအား အုပ်စုများဖန်တီးပေးမည့် Field သို့မဟုတ် expression 
       

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Count of bookmarks added** **(ထည့်သွင်းထားသော bookmark များအရေအတွက်)**
     - ``COUNT``
     - [number]
     - 

Python code
............

**Algorithm ID**: ``native:layertobookmarks``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisbookmarkstolayer:

Convert spatial bookmarks to layer (တည်နေရာဆိုင်ရာ bookmark များကို layerအဖြစ် ပြောင်းလဲခြင်း)
-----------------------------------------------------------------------------------------------

သိမ်းဆည်းထားသော တည်နေရာဆိုင်ရာ (spatial) bookmark များအတွက် polygon feature များပါဝင်သည့် layer အသစ်တစ်ခုကိုဖန်တီးပေးပါသည်။ Export ထုတ်ရာ၌ လက်ရှိ project နှင့်သက်ဆိုင်သော bookmark များကိုသာ၊ အသုံးပြုသူ bookmark များအားလုံး သို့မဟုတ် နှစ်ခုစလုံးနှင့် သက်ဆိုင်သော bookmark များကို စစ်ထုတ်နိုင်သည်။


Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Bookmark source** **(Bookmark ရင်းမြစ်)**
     - ``SOURCE``
     - [enumeration] [list]
       
       Default: [0,1]
     - Bookmark များ၏ ရင်းမြစ်(များ) ကိုရွေးချယ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခု သို့မဟုတ် တစ်ခုထက်ပို၍ အသုံးပြုနိုင်သည်-
       
       * 0 --- Project bookmarks
       * 1 --- User bookmarks
   * - **Output CRS** **(ရလာဒ်တွင်အသုံးပြုမည့် CRS)**
     - ``CRS``
     - [crs]
       
       Default: ``EPSG:4326 - WGS 84``
     - Output layer ၏ CRS 
   * - **Output** **(ရလာဒ်)**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output layer အားသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Output** **(ရလာဒ်)**
     - ``OUTPUT``
     - [vector: polygon]
     - Bookmark များပါဝင်သည့် output vector layer

Python code
............

**Algorithm ID**: ``native:bookmarkstolayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiscreateattributeindex:

Create attribute index (Attribute အညွှန်းကိန်း ဖန်တီးခြင်း)
------------------------------------------------------------

Attribute ဇယားမှ field တစ်ခုတွင် အချက်အလက်များရှာဖွေရာ၌ ပိုမိုမြန်ဆန်စေရန် အညွှန်းကိန်း (index) တစ်ခုကိုဖန်တီးပေးပါသည်။ Index ဖန်တီးခြင်းသည် layer ၏ data ထောက်ပံ့ပေးသူ နှင့်  field အမျိုးအစား နှစ်ခုလုံးပေါ်တွင်မူတည်ပါသည်။

မည်သည့် output ကိုမျှဖန်တီးမည်မဟုတ်ဘဲ index အား layer ထဲတွင်ပင်သိမ်းဆည်းထားပေးမည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input Layer** **(ထည့်သွင်းအသုံးပြုသော Layer)**
     - ``INPUT``
     - [vector: any]
     - Attribute index တစ်ခုအား ဖန်တီးမည့် vector layer ကိုရွေးချယ်ပါ။ 
   * - **Attribute to index** **(Index ဖန်တီးရမည့် Attribute)**
     - ``FIELD``
     - [tablefield: any]
     - Vector layer မှ Field 

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Indexed layer** **(အညွှန်းကိန်း ဖန်တီးထားသော layer)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - သတ်မှတ်ထားသော field တစ်ခုအတွက် index တစ်ခုပါရှိသည့် input vector layer ၏ မိတ္တူတစ်ခု 
       

Python code
............

**Algorithm ID**: ``native:createattributeindex``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiscreatespatialindex:

Create spatial index (တည်နေရာဆိုင်ရာ အညွှန်းကိန်း ဖန်တီးခြင်း)
---------------------------------------------------------------

Layer တစ်ခုထဲရှိ feature များ၏ spatial တည်နေရာအပေါ်အခြေခံ၍ ၎င်းတို့ကို လျင်မြန်စွာရှာဖွေနိုင်ရန်အတွက် index တစ်ခုကို ဖန်တီးပေးပါသည်။ တည်နေရာဆိုင်ရာ index ဖန်တီးခြင်းသည် layer ၏ data ပံ့ပိုးပေးသူပေါ်တွင် မူတည်ပါသည်။

Output layer အသစ်များကို ဖန်တီးမည်မဟုတ်ပါ။

**Default menu**- :menuselection:`Vector --> Data Management Tools`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input Layer** **(ထည့်သွင်းအသုံးပြုသော Layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Indexed layer** **(အညွှန်းကိန်း ပြုလုပ်ထားသော layer)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - တည်နေရာဆိုင်ရာ index တစ်ခုပါရှိသော input vector layer ၏ မိတ္တူတစ်ခု

Python code
............

**Algorithm ID**: ``native:createspatialindex``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisdefinecurrentprojection:

Define Shapefile projection (Shapefile projection အားသတ်မှတ်ခြင်း)
-------------------------------------------------------------------

ရှိနေပြီးသား Shapefile format dataset တစ်ခု၏ CRS (projection) ကို သတ်မှတ်ထားသော CRS အတိုင်း ဖြစ်အောင် သတ်မှတ်ပေးပါသည်။ Shapefile format dataset တစ်ခုတွင် ``prj`` file သည် ပျောက်နေပြီး အသုံးပြုရမည့် မှန်ကန်သည့် projection အားသိလျှင် ဤ algorithm သည် လွန်စွာအသုံးဝင်ပါသည်။

:ref:`qgisassignprojection` algorithm နှင့်မတူညီသောအချက်မှာ layer အသစ်တစ်ခုကို ထပ်မံဖန်တီးမည်မဟုတ်ဘဲ လက်ရှိ layer ကိုသာ မွမ်းမံပြင်ဆင်မည်ဖြစ်သည်။

.. note:: Shapefile dataset များအတွက် သတ်မှတ်ထားသော CRS နှင့်ကိုက်ညီမှုရှိစေရန် ``.prj`` နှင့်  ``.qpj`` ဖိုင်များအား အစားထိုးလုပ်ဆောင်မည်ဖြစ်သည်- သို့မဟုတ် ထိုဖိုင်များ ပျောက်ဆုံးနေပါက အသစ်ဖန်တီးမည်ဖြစ်သည်။

**Default menu**- :menuselection:`Vector --> Data Management Tools`

.. seealso:: :ref:`qgisassignprojection` ၊ :ref:`qgisfindprojection` ၊
 :ref:`qgisreprojectlayer`

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
     - Projection အချက်အလက်များ ပျောက်နေသည့် vector layer 
   * - **CRS**
     - ``CRS``
     - [crs]
     - Vector layer တွင် သတ်မှတ်အသုံးပြုမည့် CRS ကိုရွေးချယ်ပါ။ 

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - 
     - ``INPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - သတ်မှတ်ထားသော projection ပါရှိသည့် input vector layer

Python code
............

**Algorithm ID**: ``qgis:definecurrentprojection``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisdeleteduplicategeometries:

Delete duplicate geometries (ပုံတူဖြစ်နေသော ဂျီဩမေတြီများကို ဖျက်ပေးခြင်း)
---------------------------------------------------------------------------

ပုံတူဖြစ်နေသော ဂျီဩမေတြီများကို ရှာဖွေ၍ ဖယ်ရှားပေးပါသည်။

Attribute များကိုစစ်ဆေးမည်မဟုတ်သောကြောင့် feature နှစ်ခုတွင် ထပ်တူညီသည့် ဂျီဩမေတြီများ ရှိသော်လည်း မတူညီသည့် attribute များရှိပါက ၎င်းတို့ထဲမှတစ်ခုကိုသာလျှင် ရလာဒ် layer ထဲတွင် ထည့်သွင်းမည်ဖြစ်သည်။


.. seealso:: :ref:`qgisdropgeometries` ၊
   :ref:`qgisremovenullgeometries` ၊
   :ref:`qgisremoveduplicatesbyattribute`

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
     - ရှင်းလင်းလိုသည့် ပုံတူဖြစ်နေသော ဂျီဩမေတြီများ ပါဝင်နေသည့် layer 
   * - **Cleaned** **(ရှင်းလင်းထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Count of discarded duplicate records** **(ဖျက်ထားသော ပုံတူဖြစ်နေသော မှတ်တမ်းများ၏ အရေအတွက်)**
     - ``DUPLICATE_COUNT``
     - [number]
     - ဖျက်ထားသော ပုံတူဖြစ်နေသော မှတ်တမ်းများ၏ အရေအတွက်
   * - **Cleaned** **(ရှင်းလင်းထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ပုံတူဖြစ်နေသော ဂျီဩမေတြီများ မပါရှိသည့် output layer  
   * - **Count of retained records** **(ဆက်လက်ထားရှိသည့် မှတ်တမ်းများအရေအတွက်)**
     - ``RETAINED_COUNT``
     - [number]
     - သီးခြားကွဲပြား (unique) နေသော မှတ်တမ်းများအရေအတွက် 

Python code
............

**Algorithm ID**: ``native:deleteduplicategeometries``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisremoveduplicatesbyattribute:

Delete duplicates by attribute (Attribute အရ ပုံတူဖြစ်နေသောအရာများကို ဖျက်ပေးခြင်း)
------------------------------------------------------------------------------------

သတ်မှတ်ထားသော field / field များကိုသာ ထည့်သွင်းစဉ်းစား၍ ပုံတူဖြစ်နေသော row များကိုဖျက်ပေးပါသည်။ ပထမဆုံး ကိုက်ညီသော row သာကျန်ရှိမည်ဖြစ်ပြီး ပုံတူဖြစ်နေသောအရာများကို ဖျက်ပစ်မည်ဖြစ်သည်။

Optional အနေဖြင့် ထို ပုံတူဖြစ်နေသော မှတ်တမ်းများအား လေ့လာဆန်းစစ်ခြင်းပြုလုပ်နိုင်ရန်အတွက် သီးခြား output ဖိုင်တစ်ခုထဲတွင် သိမ်းဆည်းထားနိုင်ပါသည်။

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
     - ထည့်သွင်းအသုံးပြုသော layer
   * - **Fields to match duplicates by** **(ပုံတူဖြစ်နေသောအရာများကို ရှာဖွေရန် အသုံးပြုသည့် Field များ)**
     - ``FIELDS``
     - [tablefield: any] [list]
     - ပုံတူဖြစ်နေသောအရာများကို သတ်မှတ်ဖော်ပြပေးသော Field များ ။ ထို Field များအားလုံးအတွက် ထပ်တူညီသောတန်ဖိုးများရှိသည့် feature များကို ပုံတူဖြစ်နေသောအရာများအဖြစ် သတ်မှတ်မည်ဖြစ်သည်။
   * - **Filtered (no duplicates)** **(စစ်ထုတ်ထားသော (ပုံတူဖြစ်နေသောအရာများမပါဝင်သော))**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - သီးခြားကွဲပြားသော feature များပါဝင်သော output layer အားသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

   * - **Filtered (duplicates)** **(စစ်ထုတ်ထားသော (ပုံတူဖြစ်နေသောအရာများပါဝင်နေသော))**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``DUPLICATES``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Skip output]``
     - ပုံတူဖြစ်နေသောအရာများသာပါဝင်သည့် output layer အားသတ်မှတ်ပါ။
       အောက်ပါတို့မှ တစ်ခုဖြင့်-

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
   * - **Filtered (duplicates)** **(စစ်ထုတ်ထားသော (ပုံတူဖြစ်နေသောအရာများပါဝင်နေသော))**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``DUPLICATES``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     
       Default: ``[Skip output]``
     - ဖယ်ရှားထားသော feature များပါဝင်သည့် vector layer ။ မသတ်မှတ်ထားပါက ဖန်တီးပေးမည်မလုပ်ပါ (``[Skip output]`` အဖြစ်သာ ကျန်ရှိနေမည်)
   * - **Count of discarded duplicate records** **(ဖျက်လိုက်သော ပုံတူဖြစ်နေသည့်အရာများ ၏အရေအတွက်)**
     - ``DUPLICATE_COUNT``
     - [number]
     - ဖျက်လိုက်သော ပုံတူဖြစ်နေသောအရာများ၏ အရေအတွက်
   * - **Filtered (no duplicates)** **(စစ်ထုတ်ထားသော (ပုံတူဖြစ်နေသောအရာများမပါဝင်သော))**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - သီးခြား ကွဲပြားသည့် feature များပါဝင်သော vector layer 
   * - **Count of retained records** **(ဆက်လက်ထားရှိသော မှတ်တမ်းများအရေအတွက်)**
     - ``RETAINED_COUNT``
     - [number]
     - သီးခြား ကွဲပြားသည့်မှတ်တမ်းများ၏ အရေအတွက်

Python code
............

**Algorithm ID**: ``native:removeduplicatesbyattribute``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisdetectvectorchanges:

Detect dataset changes (Dataset အပြောင်းအလဲများကို ရှာဖွေဖော်ထုတ်ခြင်း)
------------------------------------------------------------------------

Vector layer နှစ်ခုကို နှိုင်းယှဉ်ပေး၍ ၎င်းတို့ကြားတွင် မည်သည့် feature များသည် မပြောင်းလဲပဲရှိနေသည်၊ ပေါင်းထည့်ထားသည် သို့မဟုတ် ဖျက်ပစ်ထားသည် တို့ကို ဆုံးဖြတ်ပေးသည်။ Dataset တူညီပြီး မတူကွဲပြားသော ပုံစံနှစ်မျိုးအား နှိုင်းယှဉ်ရန် ၎င်းကို ဖန်တီးထားခြင်းဖြစ်သည်။ 

.. figure:: img/detect_change.png
  :align: center

  Dataset ပြောင်းလဲသွားမှုအား ရှာဖွေဖော်ထုတ်ခြင်း ဥပမာ

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
   * - **Original layer** **(မူရင်း layer)**
     - ``ORIGINAL``
     - [vector: any]
     - မူရင်းပုံစံ အဖြစ် သတ်မှတ်စဉ်းစားသည့် vector layer 
   * - **Revised layer** **(စိစစ်ပြင်ဆင်ထားသော layer)** 
     - ``REVISED``
     - [vector: any]
     - စိစစ်ပြင်ဆင်ထားသော သို့မဟုတ် ပြုပြင်ပြောင်းလဲထားသော layer
   * - **Attributes to consider for match** **(ကိုက်ညီမှုရှိမရှိ ရှာဖွေကြည့်ရှုရမည့် Attribute များ)**
   
       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``COMPARE_ATTRIBUTES``
     - [tablefield: any] [list]
     - ကိုက်ညီမှုရှိမရှိ ရှာဖွေကြည့်ရှုရမည့် Attribute များ။ Default အားဖြင့် attribute များအားလုံးကို နှိုင်းယှဉ်ပေးမည်ဖြစ်သည်။
   * - **Geometry comparison behavior** **(ဂျီဩမေတြီ ကို နှိုင်းယှဉ်စစ်ဆေးသည့်ပုံစံ)**
   
       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``MATCH_TYPE``
     - [enumeration]
       
       Default: 1
     - နှိုင်းယှဉ်စစ်ဆေးမည့် စံ (criteria) အားသတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာများမှာ-

       * 0 --- Exact Match- ဂျီဩမေတြီများ၏ အစီအစဉ်နှင့် vertex များအရေအတွက် ပါဝင်ပါသည်
       * 1 --- Tolerant Match (Topological Equality)- ဂျီဩမေတြီများကို တူညီသည်ဟုယူဆသည်။

   * - **Unchanged features** **(ပြောင်းလဲခြင်းမရှိသော feature များ)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``UNCHANGED``
     - [vector: Original layer နှင့်အတူတူဖြစ်ပါသည်]
     - ပြောင်းလဲခြင်းမရှိသော feature များပါရှိသည့် output vector layer အားသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**

   * - **Added features** **(ပေါင်းထည့်ထားသော feature များ)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``ADDED``
     - [vector: Original layer နှင့်အတူတူဖြစ်ပါသည်]
     - ပေါင်းထည့်ထားသော feature များပါရှိသည့် output vector layer အားသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**

   * - **Deleted features** **(ဖျက်ထားသော feature များ)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``DELETED``
     - [vector: Original layer နှင့်အတူတူဖြစ်ပါသည်]
     - ဖျက်ထားပြီးသော feature များ ပါရှိသည့် output vector layer အားသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Unchanged features** **(ပြောင်းလဲခြင်းမရှိသော feature များ)**
     - ``UNCHANGED``
     - [vector: Original layer နှင့်အတူတူဖြစ်ပါသည်]
     - ပြောင်းလဲခြင်းမရှိသော feature များပါဝင်သည့် vector layer 
   * - **Added features** **(ပေါင်းထည့်ထားသော feature များ)**
     - ``ADDED``
     - [vector: Original layer နှင့်အတူတူဖြစ်ပါသည်]
     - ပေါင်းထည့်ထားသော feature များ ပါဝင်သည့် vector layer 
   * - **Deleted features** **(ဖျက်ထားသော feature များ)**
     - ``DELETED``
     - [vector: Original layer နှင့်အတူတူဖြစ်ပါသည်]
     - ဖျက်ထားသော featureများ ပါဝင်သည့် vector layer  
   * - **Count of unchanged features** **(ပြောင်းလဲခြင်းမရှိသော feature များ၏အရေအတွက်)**
     - ``UNCHANGED_COUNT``
     - [number]
     - ပြောင်းလဲခြင်းမရှိသော feature များ၏အရေအတွက်
   * - **Count of features added in revised layer** **(စိစစ်ပြင်ဆင်ထားသော layer တွင် ထည့်သွင်းထားသော feature များ၏အရေအတွက်)**
     - ``ADDED_COUNT``
     - [number]
     - စိစစ်ပြင်ဆင်ထားသော layer တွင် ထည့်သွင်းထားသော feature များ၏အရေအတွက်
   * - **Count of features deleted from original layer** **(မူရင်း layer မှဖျက်ထားပြီးသော feature များ၏အရေအတွက်)**
     - ``DELETED_COUNT``
     - [number]
     - မူရင်း layer မှ ဖျက်ထားပြီးသော feature များ၏အရေအတွက်

Python code
............

**Algorithm ID**: ``native:detectvectorchanges``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisdropgeometries:

Drop geometries (ဂျီဩမေတြီများဖယ်ရှားခြင်း)
--------------------------------------------

Input layer ၏ attribute ဇယားအတွက် ရိုးရှင်းသော *ဂျီဩမေတြီဆိုင်ရာအချက်အလက်မပါရှိသည့်* မိတ္တူတစ်ခုအားဖန်တီးပေးပါသည်။ မူရင်း layer ၏ Attribute ဇယားကို ဆက်လက်ထားရှိပေးမည်ဖြစ်သည်။

ဖိုင်ကို စက်အတွင်းရှိ folder တစ်ခုထဲတွင်သိမ်းဆည်းလျှင် ရလာဒ် အတွက် ဖိုင် format အမျိုးအစားများစွာရွေးချယ်နိုင်ပါသည်။ 

|checkbox| အားအမှန်ခြစ်ပေးခြင်းဖြင့် point ၊ line နှင့် polygon feature များအတွက် :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကိုအသုံးပြုနိုင်မည်ဖြစ်သည်။

.. seealso:: :ref:`qgisdeleteduplicategeometries` ၊
   :ref:`qgisremovenullgeometries`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **ထည့်သွင်းအသုံးပြုသော layer**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Dropped geometries** **(ဂျီဩမေတြီများ ဖယ်ရှားထားပြီးသော)**
     - ``OUTPUT``
     - [table]
     - ဂျီဩမေတြီမပါရှိသည့် output layer အားသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Dropped geometries** **(ဂျီဩမေတြီများ ဖယ်ရှားထားပြီးသော)**
     - ``OUTPUT``
     - [table]
     - ဂျီဩမေတြီမပါရှိသည့် output layer ။ မူရင်း attribute ဇယား၏ မိတ္တူတစ်ခု ။

Python code
............

**Algorithm ID**: ``native:dropgeometries``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisexecutesql:

Execute SQL (SQL အား စေခိုင်းလုပ်ဆောင်ခြင်း)
---------------------------------------------

ရင်းမြစ် layer ပေါ်တွင် ``SQL`` syntax ကိုအသုံးပြု၍ ရိုးရှင်းသော သို့မဟုတ် ရှုပ်ထွေးသော query (database တစ်ခုမှအချက်အလက်များထုတ်ယူရန် တောင်းခံခြင်း) ကို လုပ်ဆောင်ပေးပါသည်။

Input datasource များကို ``input1`` ၊ ``input2``... ``inputN`` အစရှိသည်တို့ဖြင့် အမျိုးအစားသတ်မှတ်ပြီး ရိုးရှင်းသော query တစ်ခုသည် ``SELECT * FROM input1`` ကဲ့သို့ဖြစ်ပါလိမ့်မည်။ 

ရိုးရှင်းသော query တစ်ခုအပြင် expression များ သို့မဟုတ် variable (ကိန်းရှင်) များကို ``SQL query`` parameter ထဲတွင် ထည့်သွင်းနိုင်ပါသည်။ အကယ်၍ ဤ algorithm အား Processing model တစ်ခုအတွင်း လုပ်ဆောင်ပြီး query ၏ parameter တစ်ခုအနေဖြင့် model input တစ်ခုကို အသုံးပြုလိုလျှင် အထူးသဖြင့်အသုံးဝင်မည်ဖြစ်သည်။ ဥပမာအားဖြင့် query တစ်ခုသည် ``SELECT * FROM [% @table %]`` ဖြစ်ပြီး ``@table`` သည် model input ကိုသတ်မှတ်ပေးသည့် variable ဖြစ်ပါသည်။ 

Query မှရရှိလာသော ရလာဒ် အား layer အသစ်တစ်ခုအဖြစ် ပေါင်းထည့်ပေးမည်ဖြစ်သည်။

.. seealso:: :ref:`qgisspatialiteexecutesql` ၊
   :ref:`qgispostgisexecutesql`

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
   * - **Additional input datasources (called input1, .., inputN in the query)** **(ထပ်ဆောင်း input datasource များ (Query ထဲတွင် input1၊ ..၊ inputN ဟုခေါ်သည်))**
     - ``INPUT_DATASOURCES``
     - [vector: any] [list]
     - Query ပြုလုပ်ရန် layer များ၏စာရင်း။ SQL editor ထဲတွင် ထို layer များအား ၎င်းတို့၏ နာမည် **အရင်း** ဖြင့် သို့မဟုတ် ရွေးချယ်ထားသော layer အရေအတွက်ပေါ်မူတည်၍ **input1** ၊ **input2** ၊ **inputN** စသည့် အမည်များဖြင့် ရည်ညွှန်းပေးနိုင်သည်။
   * - **SQL query**
     - ``INPUT_QUERY``
     - [string]
     - SQL query စာသားအားရိုက်ထည့်ပါ၊ ဥပမာအားဖြင့် ``SELECT * FROM input1``
   * - **Unique identifier field** **(Unique ဖြစ်သော ခွဲခြားသတ်မှတ်ပေးမည့် field)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``INPUT_UID_FIELD``
     - [string]
     - သီးခြားကွဲပြားသည့် ID ဖြင့် column အားသတ်မှတ်ပါ။
   * - **Geometry field** **(ဂျီဩမေတြီ field)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``INPUT_GEOMETRY_FIELD``
     - [string]
     - ဂျီဩမေတြီ field အားသတ်မှတ်ပါ
   * - **Geometry type** **(ဂျီဩမေတြီ အမျိုးအစား)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``INPUT_GEOMETRY_TYPE``
     - [enumeration]

       Default: 0
     - ရလာဒ်အတွက် ဂျီဩမေတြီကို ရွေးချယ်ပါ။ Default အားဖြင့် algorithm သည် အလိုအလျောက် ရှာဖွေဖော်ထုတ်ပေးမည်ဖြစ်သည်။ အောက်ပါတို့မှတစ်ခုဖြင့်-

       * 0 --- Autodetect (အလိုအလျောက်ရှာဖွေဖော်ထုတ်မည်)
       * 1 --- No geometry (ဂျီဩမေတြီ ပါရှိမည်မဟုတ်ပါ)
       * 2 --- Point
       * 3 --- LineString
       * 4 --- Polygon
       * 5 --- MultiPoint
       * 6 --- MultiLineString
       * 7 --- MultiPolygon

   * - **CRS**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``INPUT_GEOMETRY_CRS``
     - [crs]
     - Output layer တွင် သတ်မှတ်အသုံးပြုမည့် CRS 
   * - **SQL Output** **(SQL ရလာဒ်)**
     - ``OUTPUT``
     - [vector: any]

       Default: ``[Create temporary layer]``
     - Query ဖြင့် ဖန်တီးထားသော output layer အားသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **SQL Output** **(SQL ရလာဒ်)**
     - ``OUTPUT``
     - [vector: any]
     - Query ဖြင့် ဖန်တီးထားသော vector layer

Python code
............

**Algorithm ID**: ``qgis:executesql``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisdxfexport:

Export layers to DXF (Layer များကို DXF ဖိုင်အဖြစ် Export ထုတ်ပေးခြင်း)
------------------------------------------------------------------------

Layer များကို DXF file အဖြစ်သို့ Export ထုတ်ပေးပါသည်။ Layer တစ်ခုစီအတွက် field တစ်ခုကို ရွေးချယ်နိုင်ပြီး ၎င်း field မှ တန်ဖိုးများကို အသုံးပြု၍ DXF output ထဲရှိ ထုတ်ယူထားသော ဦးတည်ရာ layer များထဲမှ feature များကို အပိုင်းများအဖြစ် ပိုင်းခြားပေးပါသည်။


.. seealso:: :ref:`create_dxf_files`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layers** **(ထည့်သွင်းအသုံးပြုသော layer များ)** 
     - ``LAYERS``
     - [vector: any] [list]
     - Export ပြုလုပ်မည့် input vector layer များ 
   * - **Symbology mode** **(သင်္ကေတဆိုင်ရာ ပုံစံ)**
     - ``SYMBOLOGY_MODE``
     - [enumeration]

       Default: 0
     - Output layer များတွင် အသုံးပြုမည့် သင်္ကေတအမျိုးအစားကို အောက်ပါတို့မှရွေးချယ်နိုင်မည်-
       
       * 0 --- No Symbology (သင်္ကေတမထည့်သွင်းခြင်း)
       * 1 --- Feature Symbology (Feature အပေါ် အခြေခံသည့် သင်္ကေတပုံစံ)
       * 2 --- Symbol Layer Symbology (သင်္ကေတ Layer အပေါ် အခြေခံသည့် သင်္ကေတပုံစံ)
       
   * - **Symbology scale** **(သင်္ကေတများအတွက် စကေး)**
     - ``SYMBOLOGY_SCALE``
     - [scale]

       Default: 1:1 000 000
     - Data export လုပ်ရာတွင် သုံးသော Default စကေး
   * - **Encoding**
     - ``ENCODING``
     - [enumeration]
     - Layer များတွင် အသုံးပြုမည့် encoding
   * - **CRS**
     - ``CRS``
     - [crs]
     - Output layer အတွက် CRS အားရွေးချယ်ပါ။
   * - **Use layer title as name** **(Layer ၏ ခေါင်းစဉ်ကို အမည်အဖြစ်အသုံးပြုခြင်း)**
     - ``USE_LAYER_TITLE``
     - [boolean]

       Default: False
     - Output layer အား layer ၏ အမည်အစား layer ခေါင်းစဉ်ဖြင့် အမည်ပေးခြင်း (QGISတွင် သတ်မှတ်ထားသည့်အတိုင်း) 
   * - **Force 2D** **(နှစ်ဘက်မြင်ပုံစံကို တွန်းအားပေးလုပ်ဆောင်ခြင်း)**
     - ``FORCE_2D``
     - [boolean]

       Default: False
     -
   * - **Export labels as MTEXT elements** **(အညွှန်းများကို  MTEXT element များအဖြစ် Export ထုတ်ပေးခြင်း)**
     - ``MTEXT``
     - [boolean]

       Default: False
     - အညွှန်းများကို MTEXT သို့မဟုတ် TEXT element များအဖြစ် Export ထုတ်ပေးပါသည်
   * - **DXF**
     - ``OUTPUT``
     - [file]

       Default: ``[Save to temporary file]``
     - Output DXF file အတွက် သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **DXF**
     - ``OUTPUT``
     - [file]
     - Input layer များပါရှိသည့် :file:`.DXF` file 

Python code
............

**Algorithm ID**: ``native:dxfexport``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgissaveselectedfeatures:

Extract selected features (ရွေးချယ်ထားသော feature များကို ထုတ်ယူခြင်း)
-----------------------------------------------------------------------

ရွေးချယ်ထားသော feature များကို layer အသစ်တစ်ခုအဖြစ် သိမ်းဆည်းပေးပါသည်။

.. note:: အကယ်၍ ရွေးချယ်လိုက်သော layer တွင် feature များရွေးချယ်ထားခြင်းမရှိပါက  အသစ်ဖန်တီးလိုက်သော layer သည် ဗလာ (empty) ဖြစ်နေပါမည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input Layer** **(ထည့်သွင်းအသုံးပြုသော Layer)**
     - ``INPUT``
     - [vector: any]
     - သိမ်းဆည်းရန် ရွေးချယ်မှုလုပ်ဆောင်ရမည့် Layer 
   * - **Selected features** **(ရွေးချယ်ထားသော feature များ)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - ရွေးချယ်ထားသော feature များအတွက် vector layer အားသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Selected features** **(ရွေးချယ်ထားသော feature များ)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ရွေးချယ်ထားသော feature များသာပါဝင်သည့် vector layer 
       သို့မဟုတ် မည်သည်ကိုမျှမရွေးချယ်ထားပါက feature မပါရှိသော vector layer

Python code
............

**Algorithm ID**: ``native:saveselectedfeatures``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisshpencodinginfo:

Extract Shapefile encoding (Shapefile encoding ကို ထုတ်ယူခြင်း)
----------------------------------------------------------------

Shapefile တစ်ခုအတွင်း ထည့်သွင်းထားသော attribute encoding အချက်အလက်ကို ထုတ်ယူပေးပါသည်။ Optional :file:`.cpg` file တစ်ခုမှ သတ်မှတ်ထားသော encoding နှင့် :file:`.dbf` LDID header block ထဲတွင်ရှိသော မည်သည့် encoding အသေးစိတ်အချက်အလက်များမဆို ထည့်သွင်းစဉ်းစားမည်ဖြစ်သည်။
 

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
   * - **Input Layer** **(ထည့်သွင်းအသုံးပြုသော Layer)**
     - ``INPUT``
     - [vector: any]
     - Encoding အချက်အလက်များကိုထုတ်ယူမည့် ESRI Shapefile (:file:`.SHP`) Layer 

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Shapefile encoding**
     - ``ENCODING``
     - [string]
     - Input file ထဲတွင် သတ်မှတ်ထားသော encoding အချက်အလက်များ
   * - **CPG encoding**
     - ``CPG_ENCODING``
     - [string]
     - မည်သည့် :file:`.CPG` file ထဲတွင်မဆို သတ်မှတ်ထားသော encoding အချက်အလက်များ
   * - **LDID encoding**
     - ``LDID_ENCODING``
     - [string]
     - :file:`.dbf` LDID header block ထဲတွင် encoding အချက်အလက်များ

Python code
............

**Algorithm ID**: ``native:shpencodinginfo``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisfindprojection:

Find projection (Projection အားရှာဖွေခြင်း)
--------------------------------------------

Layer တစ်ခုတွင် ၎င်း၏ projection ကိုမသိပါက သင့်လျော်သော ကိုသြဒိနိတ်ရည်ညွှန်းစနစ် (CRS) များပါဝင်သည့် ဇကာတင်စာရင်းတစ်ခုအား ဖန်တီးမည်ဖြစ်သည်။  

Layer မှလွှမ်းခြုံရန် မျှော်မှန်းထားသောဧရိယာကို ဦးတည်ရာ (target) ဧရိယာ parameter မှတဆင့် သတ်မှတ်ပေးရပါမည်။ ဤ target ဧရိယာအတွက် အသုံးပြုမည့် ကိုသြဒိနိတ်ရည်ညွှန်းစနစ် သည် QGIS မှ သိရှိသည့်အရာ ဖြစ်ရပါမည်။

ဤ algorithm သည် သိရှိထားပြီးသည့် CRS တိုင်းတွင် layer ၏ extent ကို စစ်ဆေးပြီးနောက် layer သည် ဤ projection ထဲတွင်ဖြစ်ခဲ့လျှင် target ဧရိယာနှင့်နီးစပ်သော projection များကို စာရင်းပြုစုခြင်းအားဖြင့် လုပ်ဆောင်ပါသည်။ 

.. seealso:: :ref:`qgisassignprojection` ၊
   :ref:`qgisdefinecurrentprojection` ၊ :ref:`qgisreprojectlayer`

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
   * - **Input Layer** **(ထည့်သွင်းအသုံးပြုသော Layer)**
     - ``INPUT``
     - [vector: any]
     - Projection မသိရှိသော Layer
   * - **Target area for layer (xmin, xmax, ymin, ymax)** **(Layer အတွက် ဦးတည် ဧရိယာ (xmin၊ xmax၊ ymin၊ ymax))**
     - ``TARGET_AREA``
     - [extent]
     - Layer မှ လွှမ်းခြုံထားသော ဧရိယာ။

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **CRS candidates** **(ရွေးချယ်စရာ CRS များ)**
     - ``OUTPUT``
     - [table]

       Default: ``[Create temporary layer]``
     - Coordinate Reference System (CRS) အကြံပြုချက်များ (EPSG codes) အတွက် ဇယား(ဂျီဩမေတြီမပါရှိသော layer) အားသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **CRS candidates** **(ရွေးချယ်စရာ CRS များ)**
     - ``OUTPUT``
     - [table]
     - ပေးထားသော စံနှုန်းများနှင့် ကိုက်ညီသော CRS (EPSG codes) အားလုံးပါဝင်သည့် ဇယားတစ်ခု။ 

Python code
............

**Algorithm ID**: ``qgis:findprojection``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisflattenrelationships:

Flatten relationship (ဆက်နွယ်မှုကို ပြေပြစ်စေခြင်း)
----------------------------------------------------

Vector layer တစ်ခုအတွက် :ref:`relationship (ဆက်နွယ်မှု) <vector_relations>` တစ်ခုအား ပြေပြစ်ချောမွေ့စေပြီး ဆက်စပ်နေသော child (အခွဲ) feature တစ်ခုလျှင် parent (မူရင်း) feature တစ်ခု ပါဝင်သော layer တစ်ခုတည်းအဖြစ် export ထုတ်ပေးပါသည်။ ဤ ပင်မ (master) feature တွင် ဆက်စပ်နေသည့် feature များအတွက် attribute များ အားလုံးပါဝင်ပါသည်။ ဥပမာအားဖြင့် CSV သို့ export ထုတ်နိုင်သော ဇယားတစ်ခုအဖြစ် ဆက်နွယ်မှုကို ရရှိစေမည်ဖြစ်သည်။

.. figure:: img/flatten_relationship.png
  :align: center
  :width: 100%

  ဆက်နွယ်နေသော အခွဲများပါဝင်သည် region တစ်ခု၏ပုံစံ (ဘယ်) - ဆက်နွယ်နေသော အခွဲ တစ်ခုစီအတွက် ချိတ်ဆက်ထားသော attribute များပါရှိသည့် အပွား region feature တစ်ခု (ညာ)

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
   * - **Input Layer** **(ထည့်သွင်းအသုံးပြုသော Layer)**
     - ``INPUT``
     - [vector: any]
     - ပြေပြစ်ချောမွေ့စေရန် ပြုလုပ်သင့်သည့် ဆက်နွယ်မှု ပါရှိသော layer
   * - **Flattened Layer** **(ပြေပြစ်ချောမွေ့အောင်ပြုလုပ်ထားသော Layer)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output layer (ပြေပြစ်ချောမွေ့အောင်ပြုလုပ်ထားသော) အားသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Flattened Layer** **(ပြေပြစ်ချောမွေ့အောင်ပြုလုပ်ထားသော Layer)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ဆက်နွယ်နေသော feature များအတွက် attribute များအားလုံးပါဝင်သည့် master (ပင်မ)feature များပါရှိသော layer တစ်ခု 
      

Python code
............

**Algorithm ID**: ``native:flattenrelationships``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**
  

.. _qgisjoinattributestable:

Join attributes by field value (Field တန်ဖိုးဖြင့် attribute များကို ချိတ်ဆက်ခြင်း)
------------------------------------------------------------------------------------

Input vector layer တစ်ခုကိုယူပြီး ၎င်း၏ attribute ဇယားထဲတွင် ထပ်ဆောင်း attribute များဖြင့် ထပ်တိုးထားသော vector layer အသစ်တစ်ခုကို ဖန်တီးပေးပါသည်။

ထပ်ဆောင်း attribute များနှင့် ၎င်းတို့၏တန်ဖိုးများကို ဒုတိယ vector layer တစ်ခုမှရယူမည်ဖြစ်သည်။ ၎င်း layer တစ်ခုစီမှ attribute တစ်ခုကိုရွေးချယ်၍ ချိတ်ဆက်မူစံနှုန်း (join criteria) ကို သတ်မှတ်ပါသည်။ 

.. seealso:: :ref:`qgisjoinbynearest` ၊
   :ref:`qgisjoinattributesbylocation`

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
   * - **Input Layer** **(ထည့်သွင်းအသုံးပြုသော Layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer ။ Output layer တွင် ဤ layer မှ feature များ အပြင် ဒုတိယ layer မှကိုက်ညီသော feature များ၏ attribute များလည်း ပါဝင်ပါလိမ့်သည်။
   * - **Table field** **(ဇယား field)**
     - ``FIELD``
     - [tablefield: any]
     - ချိတ်ဆက်ရာတွင် အသုံးပြုမည့် ရင်းမြစ် layer ၏ Field 
   * - **Input layer 2** **(ထည့်သွင်းအသုံးပြုသော ဒုတိယ layer)**
     - ``INPUT_2``
     - [vector: any]
     - ချိတ်ဆက်ရန် attribute ဇယားပါရှိသော Layer 
   * - **Table field 2** **(ဒုတိယ ဇယား field)**
     - ``FIELD_2``
     - [tablefield: any]
     - ချိတ်ဆက်ရာတွင် အသုံးပြုမည့် ဒုတိယ (join) layer ၏ Field ။ ထို field ၏အမျိုးအစားသည် input ဇယား field အမျိုးအစားနှင့် တူညီရမည် (သို့မဟုတ် ကိုက်ညီမှုရှိရမည်)
   * - **Layer 2 fields to copy** **(မိတ္တူကူးယူရမည့် ဒုတိယ Layer field များ)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``FIELDS_TO_COPY``
     - [tablefield: any] [list]
     - ပေါင်းထည့်လိုသော သီးခြား field များကို ရွေးချယ်ပါ။ Default အားဖြင့် field များအားလုံးကို ပေါင်းထည့်မည်ဖြစ်သည်။
   * - **Join type** **(ချိတ်ဆက်မှု အမျိုးအစား)**
     - ``METHOD``
     - [enumeration]

       Default: 1
     - နောက်ဆုံး ချိတ်ဆက်ထားသော layer ၏ အမျိုးအစား။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       * 0 --- ကိုက်ညီမှုရှိသည့် feature တစ်ခုစီအတွက် သီးခြား feature တစ်ခုဖန်တီးပါ။
	 (one-to-many)
       * 1 --- ပထမဆုံး ကိုက်ညီမှုရှိသည့် feature မှ attribute များကိုသာရယူပါ။
	 (one-to-one)

   * - **Discard records which could not be joined** **(ချိတ်ဆက်ခြင်းမပြုနိုင်သည့် မှတ်တမ်းများကိုဖျက်ပစ်ခြင်း)**
     - ``DISCARD_NONMATCHING``
     - [boolean]

       Default: True
     - ချိတ်ဆက်ခြင်းမပြုနိုင်သည့် feature များကို ဆက်လက်မထားရှိလိုပါက အမှန်ခြစ်ပေးထားပါ။
       
   * - **Joined field prefix** **(ချိတ်ဆက်ထားသော field အတွက် ရှေ့ဆက်စာလုံး)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``PREFIX``
     - [string]
     - ချိတ်ဆက်ထားပြီးသော field များကို အလွယ်တကူ ခွဲခြားနိုင်ရန်နှင့် field အမည်များတူနေခြင်းကို ရှောင်ရှားနိုင်ရန်အတွက် ၎င်းတို့တွင် prefix (ရှေ့ဆက်စာလုံး) တစ်ခုပေါင်းထည့်ပါ။
   * - **Joined layer** **(ချိတ်ဆက်ထားပြီးသော layer)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - ချိတ်ဆက်ခြင်းအတွက် output vector layer အားသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**

   * - **Unjoinable features from first layer** **(ပထမ layer မှ ချိတ်ဆက်ခြင်းမပြုနိုင်သော feature များ)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``NON_MATCHING``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Skip output]``
     - ပထမ layer မှ ပေါင်းစပ်ခြင်းမပြုနိုင်သော feature များအတွက် output vector layer အားသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Number of joined features from input table** **(Input ဇယားမှ ချိတ်ဆက်ထားပြီးသော feature များအရေအတွက်)**
     - ``JOINED_COUNT``
     - [number]
     - 
   * - **Unjoinable features from first layer** **(ပထမ layer မှ ချိတ်ဆက်ခြင်းမပြုနိုင်သော feature များ)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``NON_MATCHING``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - မကိုက်ညီသည့် feature များပါဝင်သော vector layer 
   * - **Joined layer** **(ချိတ်ဆက်ထားပြီးသော layer)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ချိတ်ဆက်မှုမှ ပေါင်းထည့်ထားသော attribute များပါဝင်သည့် output vector layer
   * - **Number of unjoinable features from input table** **(Input ဇယားမှ ချိတ်ဆက်ခြင်းမပြုနိုင်သော feature များအရေအတွက်)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``UNJOINABLE_COUNT``
     - [number]
     - 

Python code
............

**Algorithm ID**: ``native:joinattributestable``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisjoinattributesbylocation:

Join attributes by location (တည်နေရာအရ attribute များကို ချိတ်ဆက်ခြင်း)
------------------------------------------------------------------------

Input vector layer တစ်ခုကိုယူပြီး ၎င်း၏ attribute ဇယားထဲတွင် ထပ်ဆောင်း attribute များဖြင့် ထပ်တိုးထားသော vector layer အသစ်တစ်ခုကို ဖန်တီးပေးပါသည်။

ထပ်ဆောင်း attribute များနှင့် ၎င်းတို့၏တန်ဖိုးများကို ဒုတိယ vector layer တစ်ခုမှရယူမည်ဖြစ်သည်။ ပထမ layer မှ feature တစ်ခုချင်းစီသို့ ပေါင်းထည့်သော ဒုတိယ layer မှ တန်ဖိုးများကို ရွေးချယ်ရန် တည်နေရာဆိုင်ရာစံနှုန်း (spatial criteria) ကိုအသုံးပြုပါသည်။


**Default menu**- :menuselection:`Vector --> Data Management Tools`

.. seealso:: :ref:`qgisjoinbynearest` ၊
   :ref:`qgisjoinattributestable` ၊ :ref:`qgisjoinbylocationsummary`

Exploring spatial relations (တည်နေရာဆိုင်ရာ ဆက်နွယ်မှုများကို ရှာဖွေဖော်ထုတ်ခြင်း)
...................................................................................

.. include:: ../algs_include.rst
   :start-after: **geometric_predicates**
   :end-before: **end_geometric_predicates**

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
   * - **Join to features in**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer ။ Output layer တွင် ဤ layer မှ feature များ အပြင် ဒုတိယ layer မှကိုက်ညီသော feature များ၏ attribute များလည်း ပါဝင်ပါလိမ့်သည်။
   * - **Where the features**
     - ``PREDICATE``
     - [enumeration] [list]

       Default: [0]
     - ရင်းမြစ် feature နှင့် ဦးတည်ရာ feature တို့အကြား ပေါင်းစပ်နိုင်စေရန်အတွက် ရှိသင့်သည့် တည်နေရာဆိုင်ရာဆက်နွယ်မှု (spatial relation) အမျိုးအစား ။ အောက်ပါရွေးချယ်စရာများထဲမှ တစ်ခု သို့မဟုတ် တစ်ခုထက်ပို၍ ရွေးချယ်နိုင်သည်- 
        
       * 0 --- intersect (တစ်ခုနှင့်တစ်ခု ထိဖြတ်နေခြင်း)
       * 1 --- contain (တစ်ခုတွင် တစ်ခုက ပါဝင်ခြင်း)
       * 2 --- equal (တစ်ခုနှင့်တစ်ခု တူညီခြင်း)
       * 3 --- touch (တစ်ခုနှင့်တစ်ခု ထိနေခြင်း)
       * 4 --- overlap (တစ်ခုနှင့်တစ်ခု ထပ်နေခြင်း)
       * 5 --- are within (တစ်ခုမှာ အခြားတစ်ခုထဲတွင်ရှိနေခြင်း)
       * 6 --- cross (တစ်ခုနှင့်တစ်ခု ဖြတ်သွားခြင်း)

       အကယ်၍ အခြေအနေ တစ်ရပ်ထက်ပို၍ ရွေးချယ်ထားလျှင် အနည်းဆုံးတော့ ၎င်းတို့ထဲမှတစ်ခုသည် 
       feature တစ်ခုအားထုတ်ယူရန် အခြေအနေနှင့်ကိုက်ညီမှုရှိရမည် (OR operation)။
   * - **By comparing to**
     - ``JOIN``
     - [vector: any]
     - ချိတ်ဆက်မှု layer ။ ဤ vector layer မှ feature များသည် တည်နေရာဆိုင်ရာဆက်နွယ်မှုနှင့် ကိုက်ညီပါက ၎င်းတို့၏ attribute များကို ရင်းမြစ်  layer attribute ဇယားသို့ **ပေါင်းထည့်** မည်ဖြစ်သည်။      
   * - **Fields to add (leave empty to use all fields)** **(ပေါင်းထည့်မည့် Field များ (field များအားလုံးကိုအသုံးပြုရန် empty ထားရှိပါ))**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``JOIN_FIELDS``
     - [tablefield: any] [list]
     - ချိတ်ဆက်မှု layer မှ ပေါင်းထည့်လိုသော သီးသန့် field များကိုရွေးချယ်ပါ။ Default အားဖြင့်field များအားလုံးကို ပေါင်းထည့်မည်ဖြစ်သည်။ 
   * - **Join type** **(ချိတ်ဆက်မှု အမျိုးအစား)**
     - ``METHOD``
     - [enumeration]
     - နောက်ဆုံး ချိတ်ဆက်ထားပြီးသော layer ၏ အမျိုးအစား။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       * 0 --- ကိုက်ညီမှုရှိသည့် feature တစ်ခုစီအတွက်သီးခြားဖြစ်သော feature တစ်ခု ဖန်တီးပါ (one-to-many)
       * 1 --- ပထမဆုံး ကိုက်ညီမှုရှိသော feature ၏ attribute များကိုသာ ရယူအသုံးပြုပါ။ (one-to-one)
       * 2 --- အများဆုံးထပ်နေသော feature ၏ attribute များကိုသာ ရယူအသုံးပြုပါ။ (one-to-one)

   * - **Discard records which could not be joined** **(ချိတ်ဆက်ခြင်းမပြုနိုင်သည့် မှတ်တမ်းများကိုဖျက်ခြင်း)**
     - ``DISCARD_NONMATCHING``
     - [boolean]
     
       Default: False
     - ချိတ်ဆက်ခြင်းမပြုနိုင်သော input layer ၏ feature များကို output မှ ဖယ်ရှားပေးပါသည်။ 
   * - **Joined field prefix** **(ချိတ်ဆက်ထားသော field ရှေ့ဆက်စာလုံး)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``PREFIX``
     - [string]
     - ချိတ်ဆက်ထားသော field များကို အလွယ်တကူ ခွဲခြားသတ်မှတ်နိုင်ရန်နှင့် field အမည်များ တူနေခြင်းကိုရှောင်ရှားရန်အတွက် ၎င်း field များရှေ့တွင် prefix (ရှေ့ဆက်စာလုံး) တစ်ခုထည့်သွင်းပါ။  
   * - **Joined layer** **(ချိတ်ဆက်ထားသော layer)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - ချိတ်ဆက်မှုအတွက် output vector layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**

   * - **Unjoinable features from first layer** **(ပထမ layer မှ ချိတ်ဆက်ခြင်းမပြုနိုင်သော feature များ)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``NON_MATCHING``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Skip output]``
     - ပထမ layerမှ ချိတ်ဆက်ခြင်းမပြုနိုင်သော feature များအတွက် output vector layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Number of joined features from input table** **(Input ဇယားမှ ချိတ်ဆက်ထားပြီးသော feature များ၏အရေအတွက်)**
     - ``JOINED_COUNT``
     - [number]
     - 
   * - **Unjoinable features from first layer** **(ပထမ layer မှ ချိတ်ဆက်ခြင်းမပြုနိုင်သော feature များ)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``NON_MATCHING``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ကိုက်ညီမှုမရှိသော feature များ ပါဝင်သည့် vector layer
   * - **Joined layer** **(ချိတ်ဆက်ထားသော layer)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ချိတ်ဆက်မှုမှ ပေါင်းထည့်ထားသော attribute များပါဝင်သည့် output vector layer 

Python code
............

**Algorithm ID**: ``native:joinattributesbylocation``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisjoinbylocationsummary:

Join attributes by location (summary) (တည်နေရာအားဖြင့် attribute များကိုချိတ်ဆက်ခြင်း (အကျဉ်းချုပ်))
-----------------------------------------------------------------------------------------------------

Input vector layer တစ်ခုကိုယူပြီး ၎င်း၏ attribute ဇယားထဲတွင် ထပ်ဆောင်း attribute များဖြင့် ထပ်တိုးထားသော vector layer အသစ်တစ်ခုကို ဖန်တီးပေးပါသည်။

ထပ်ဆောင်း attribute များနှင့် ၎င်းတို့၏တန်ဖိုးများကို ဒုတိယ vector layer တစ်ခုမှရယူမည်ဖြစ်သည်။ ပထမ layer မှ feature တစ်ခုချင်းစီသို့ ပေါင်းထည့်သော ဒုတိယ layer မှ တန်ဖိုးများကို ရွေးချယ်ရန် တည်နေရာဆိုင်ရာစံနှုန်း (spatial criteria) ကိုအသုံးပြုပါသည်။

ဤ algorithm သည် ဒုတိယ layer ထဲရှိ ကိုက်ညီမှုရှိသော feature များမှတန်ဖိုးများအတွက် ကိန်းဂဏန်း အချက်အလက်ဆိုင်ရာ အကျဉ်းချုပ် ကိုတွက်ချက်ပေးပါသည် (ဥပမာအားဖြင့်  အများဆုံးတန်ဖိုး၊ ပျမ်းမျှတန်ဖိုး အစရှိသည်)။


.. seealso:: :ref:`qgisjoinattributesbylocation`

Exploring spatial relations (တည်နေရာဆိုင်ရာ ဆက်နွယ်မှုများကို ရှာဖွေဖော်ထုတ်ခြင်း)
...................................................................................

.. include:: ../algs_include.rst
   :start-after: **geometric_predicates**
   :end-before: **end_geometric_predicates**

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
   * - **Join to features in**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer ။ Output layer တွင် ဤ layer မှ feature များ အပြင် ဒုတိယ layer မှကိုက်ညီသော feature များ၏ attribute များလည်း ပါဝင်ပါလိမ့်သည်။
   * - **Where the features**
     - ``PREDICATE``
     - [enumeration] [list]

       Default: [0]
     - ရင်းမြစ် feature နှင့် ဦးတည်ရာ feature တို့အကြား ပေါင်းစပ်နိုင်စေရန်အတွက် ရှိသင့်သည့် တည်နေရာဆိုင်ရာဆက်နွယ်မှု (spatial relation) အမျိုးအစား ။ အောက်ပါရွေးချယ်စရာများထဲမှ တစ်ခု သို့မဟုတ် တစ်ခုထက်ပို၍ ရွေးချယ်နိုင်သည်- 
        
       * 0 --- intersect (တစ်ခုနှင့်တစ်ခု ထိဖြတ်နေခြင်း)
       * 1 --- contain (တစ်ခုတွင် တစ်ခုက ပါဝင်ခြင်း)
       * 2 --- equal (တစ်ခုနှင့်တစ်ခု တူညီခြင်း)
       * 3 --- touch (တစ်ခုနှင့်တစ်ခု ထိနေခြင်း)
       * 4 --- overlap (တစ်ခုနှင့်တစ်ခု ထပ်နေခြင်း)
       * 5 --- are within (တစ်ခုမှာ အခြားတစ်ခုထဲတွင်ရှိနေခြင်း)
       * 6 --- cross (တစ်ခုနှင့်တစ်ခု ဖြတ်သွားခြင်း)

       အကယ်၍ အခြေအနေ တစ်ရပ်ထက်ပို၍ ရွေးချယ်ထားလျှင် အနည်းဆုံးတော့ ၎င်းတို့ထဲမှတစ်ခုသည် 
       feature တစ်ခုအားထုတ်ယူရန် အခြေအနေနှင့်ကိုက်ညီမှုရှိရမည် (OR operation)။
   * - **By comparing to**
     - ``JOIN``
     - [vector: any]
     - ချိတ်ဆက်မှု layer ။ ဤ vector layer မှ feature များသည် တည်နေရာဆိုင်ရာဆက်နွယ်မှုနှင့် ကိုက်ညီပါက ၎င်းတို့၏ attribute များကို ရင်းမြစ် layer attribute ဇယားသို့ **ပေါင်းထည့်** မည်ဖြစ်သည်။ 
   * - **Fields to summarize (leave empty to use all fields)** **(အကျဉ်းချုပ်ပြုလုပ်ရန် Field များ (field များအားလုံးကိုအသုံးပြုရန်အတွက် empty ထားပါ))**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``JOIN_FIELDS``
     - [tablefield: any] [list]
     - ချိတ်ဆက်မှု layer မှ ပေါင်းထည့်လိုသော သီးသန့် field များကိုရွေးချယ်ပါ။ Default အားဖြင့်field များအားလုံးကို ပေါင်းထည့်မည်ဖြစ်သည်။ 
   * - **Summaries to calculate (leave empty to use all fields)** **(တွက်ချက်ရမည့် အကျဉ်းချုပ်များ (field များအားလုံးကိုအသုံးပြုရန်အတွက် empty ထားပါ))**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``SUMMARIES``
     - [enumeration] [list]

       Default: []
     - Input feature တစ်ခုချင်းစီအတွက် ၎င်းတို့နှင့်ကိုက်ညီမှုရှိသော feature များ၏ ချိတ်ဆက်ထားသည့် field များပေါ်တွင် ကိန်းဂဏန်းအချက်အလက်များကိုတွက်ချက်မည်ဖြစ်သည်။ အောက်ပါရွေးချယ်စရာများထဲမှ တစ်ခု သို့မဟုတ် တစ်ခုထက်ပို၍ ရွေးချယ်နိုင်သည်- 

       * 0 --- count (အရေအတွက်)
       * 1 --- unique (ကွဲပြားခြားနားသည့် တန်ဖိုး)
       * 2 --- min (အငယ်ဆုံး တန်ဖိုး)
       * 3 --- max (အကြီးဆုံး တန်ဖိုး)
       * 4 --- range (အပိုင်းအခြား)
       * 5 --- sum (စုစုပေါင်း)
       * 6 --- mean (ပျမ်းမျှတန်ဖိုး)
       * 7 --- median (တစ်ဝက်ကိန်းတန်ဖိုး)
       * 8 --- stddev (စံတိမ်းချက်)
       * 9 --- minority (အနည်းစု)
       * 10 --- majority (အများစု)
       * 11 --- q1 (ဒေတာတစ်ခု၏ ပထမလေးပုံတစ်ပုံ/၂၅ ရာခိုင်နှုန်း)
       * 12 --- q3 (ဒေတာတစ်ခု၏ တတိယလေးပုံတစ်ပုံ/၇၅ ရာခိုင်နှုန်း)
       * 13 --- iqr (ဒေတာ၏အလယ်တစ်ဝက်တွင် ပြန့်နှံ့မှု)
       * 14 --- empty (ဗလာဖြစ်နေသော)
       * 15 --- filled (အချက်အလက်များနှင့် တန်ဖိုးများ ဖြည့်ထားသော)
       * 16 --- min_length (အငယ်ဆုံးအလျား)
       * 17 --- max_length (အကြီးဆုံးအလျား)
       * 18 --- mean_length (ပျမ်းမျှအလျား)

   * - **Discard records which could not be joined** **(ချိတ်ဆက်၍မရသော မှတ်တမ်းများကို ဖျက်ခြင်း)**
     - ``DISCARD_NONMATCHING``
     - [boolean]
     
       Default: False
     - ချိတ်ဆက်၍မရသော input layer ၏ feature များကို output မှ ဖယ်ရှားပါ။
   * - **Joined layer** **(ချိတ်ဆက်ထားသော layer)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - ချိတ်ဆက်မှုအတွက် output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Joined layer** **(ချိတ်ဆက်ထားသော layer)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ချိတ်ဆက်မှုမှ ရရှိလာသော အကျဉ်းချုပ် attribute များပါရှိသော output vector layer 

Python code
............

**Algorithm ID**: ``qgis:joinbylocationsummary``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisjoinbynearest:

Join attributes by nearest (အနီးစပ်ဆုံးဖြင့် attribute များကိုချိတ်ဆက်ခြင်း)
-----------------------------------------------------------------------------

Input vector layer တစ်ခုမှ ၎င်း၏ attribute ဇယားထဲတွင် ထပ်ဆောင်း field များ ထည့်သွင်းထားသော vector layer အသစ်တစ်ခုကို ဖန်တီးပေးပါသည်။ ထပ်ဆောင်း attributeများ နှင့် ၎င်းတို့၏တန်ဖိုးများကို ဒုတိယ vector layer မှရယူမည်ဖြစ်သည်။ Layer တစ်ခုချင်းစီမှ အနီးဆုံးသော feature များကိုရှာဖွေ၍ ချိတ်ဆက်ပေးခြင်းဖြစ်သည်။

Default အားဖြင့် အနီးစပ်ဆုံး feature ကိုသာသွား၍ ချိတ်ဆက်စေသော်လည်း k-nearest neighboring (K အရေအတွက် အနီးစပ်ဆုံးအနီးအနား) feature များနှင့်လည်း ချိတ်ဆက်နိုင်သည်။

အကယ်၍ အများဆုံးအကွာအဝေးတစ်ခုကိုသတ်မှတ်ထားပါက ထိုအကွာအဝေးထက်ပို၍ နီးကပ်သည့် feature များသာ ကိုက်ညီမည်ဖြစ်သည်။ 
 
.. seealso:: :ref:`qgisnearestneighbouranalysis` ၊
   :ref:`qgisjoinattributestable` ၊
   :ref:`qgisjoinattributesbylocation` ၊ :ref:`qgisdistancematrix`

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
     - ထည့်သွင်းအသုံးပြုသော layer
   * - **Input layer 2** **(ထည့်သွင်းအသုံးပြုသော ဒုတိယ layer)**
     - ``INPUT_2``
     - [vector: any]
     - ချိတ်ဆက်မည့် layer
   * - **Layer 2 fields to copy (leave empty to copy all fields)** **(မိတ္တူကူးယူရမည့် Layer 2 field များ (field အားလုံးကို မိတ္တူကူးယူရန် empty ထားပါ))**
     - ``FIELDS_TO_COPY``
     - [fields]
     - မိတ္တူကူးယူရမည့် Join layer field များ (အကယ်၍ ဗလာဖြစ်နေလျှင် field အားလုံးအား မိတ္တူကူးယူမည်ဖြစ်သည်)
   * - **Discard records which could not be joined** **(ချိတ်ဆက်ခြင်းမပြုနိုင်သည့် မှတ်တမ်းများကို ဖျက်ခြင်း)**
     - ``DISCARD_NONMATCHING``
     - [boolean]
     
       Default: False
     - ချိတ်ဆက်ခြင်းမပြုနိုင်သည့် input layer မှတ်တမ်းများကို output မှ ဖယ်ရှားမည်ဖြစ်သည်။
   * - **Joined field prefix** **(ချိတ်ဆက်ထားသော field၏ ရှေ့ဆက်စာလုံး)**
     - ``PREFIX``
     - [string]
     - ချိတ်ဆက်ထားသော field ၏ prefix (ရှေ့ဆက်စာလုံး)
   * - **Maximum nearest neighbors** **(အများဆုံးဖြစ်သည့် အနီးစပ်ဆုံး အနီးအနားများ)**
     - ``NEIGHBORS``
     - [number]
     
       Default: 1
     - အနီးစပ်ဆုံး အနီးအနားများ၏ အများဆုံးအရေအတွက်
   * - **Maximum distance** **(အများဆုံး အကွာအဝေး)**
     - ``MAX_DISTANCE``
     - [number]
     - အများဆုံး ရှာဖွေအကွာအဝေး
   * - **Joined layer** **(ချိတ်ဆက်ပြီးသော layer)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - ချိတ်ဆက်ပြီးသော feature များပါရှိသည့် vector layer ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**

   * - **Unjoinable features from first layer** **(ပထမ layer မှ ချိတ်ဆက်ခြင်းမပြုနိုင်သော feature များ)**
     - ``NON_MATCHING``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Skip output]``
     - ချိတ်ဆက်ခြင်းမပြုနိုင်သော feature များပါဝင်သည့် vector layer အားသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Joined layer** **(ချိတ်ဆက်ပြီးသော layer)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ရရှိလာသော ချိတ်ဆက်ပြီးသည့် layer
   * - **Unjoinable features from first layer** **(ပထမ layer မှ ချိတ်ဆက်ခြင်းမပြုနိုင်သည့် feature များ)**
     - ``NON_MATCHING``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Join Layer ရှိ မည်သည့် feature များနှင့်မျှ မချိတ်ဆက်နိုင်သော ပထမ Layer မှ feature များပါဝင်သည့် Layer
   * - **Number of joined features from input table** **(Input ဇယားမှ ချိတ်ဆက်ပြီးသော feature များ၏အရေအတွက်)**
     - ``JOINED_COUNT``
     - [number]
     - Input ဇယားမှ ချိတ်ဆက်ထားပြီးသော feature များ၏အရေအတွက်
   * - **Number of unjoinable features from input table** **(Input ဇယားမှ ချိတ်ဆက်ခြင်းမပြုနိုင်သော feature များ၏အရေအတွက်)**
     - ``UNJOINABLE_COUNT``
     - [number]
     - Input ဇယားမှ ချိတ်ဆက်ခြင်းမပြုနိုင်သော feature များ၏အရေအတွက်

Python code
............

**Algorithm ID**: ``native:joinbynearest``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgismergevectorlayers:

Merge vector layers (Vector layer များကိုပေါင်းခြင်း)
------------------------------------------------------

**တူညီသော ဂျီဩမေတြီ** အမျိုးအစားရှိသည့် မြောက်များစွာသော vector layer များကို တစ်ခုတည်းအဖြစ် ပေါင်းစပ်ပေးသည်။

ရရှိလာသော layer ၏ attribute ဇယားတွင် input layer များအားလုံးမှ field များ ပါဝင်မည်ဖြစ်သည်။ အကယ်၍ အမည်တူပြီး အမျိုးအစားမတူညီသော field များပါဝင်နေပါက export ထုတ်ထားသော field ကို string type (စာသားပုံစံ) field တစ်ခုအဖြစ်သို့ အလိုအလျောက်ပြောင်းလဲသွားမည်ဖြစ်သည်။ မူလ layer အမည် နှင့် အချက်အလက်အရင်းအမြစ်များ သိမ်းဆည်းထားသည့် field အသစ်များကိုလည်း ပေါင်းထည့်သွားမည်ဖြစ်သည်။

အကယ်၍ မည်သည့် input layer တွင်မဆို Z သို့မဟုတ် M တန်ဖိုးများပါဝင်ပါက output layer တွင်လည်း ထိုတန်ဖိုးများပါဝင်မည်ဖြစ်သည်။ အလားတူစွာ အကယ်၍ input layer များထဲမှတစ်ခုသည် multi-part(အစိတ်အပိုင်းများစွာပါရှိနေခြင်း) ဖြစ်လျှင် ရရှိလာသော layer သည်လည်း multi-part layer တစ်ခုဖြစ်လိမ့်မည်။
 
ထို့အပြင် ပေါင်းစပ်လိုက်သော layer အတွက် ဦးတည်အသုံးပြုမည့် coordinate reference system (CRS)ကို သတ်မှတ်နိုင်သည်။ အကယ်၍ မသတ်မှတ်ထားပါက CRS အား ပထမဆုံး input layer အတိုင်းအသုံးပြုမည်ဖြစ်သည်။ ၎င်း CRS နှင့်ကိုက်ညီမှုရှိစေရန် layer အားလုံးအား projection တစ်ခုမှတစ်ခုသို့ ပြောင်းလဲပေးမည်ဖြစ်သည်။

.. figure:: img/merge_vector_layers.png
   :align: center

**Default menu**- :menuselection:`Vector --> Data Management Tools`

.. seealso:: :ref:`qgissplitvectorlayer`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input Layers** **(ထည့်သွင်းအသုံးပြုသော Layer များ)**
     - ``LAYERS``
     - [vector: any] [list]
     - တစ်ခုတည်းသော layer အဖြစ် ပေါင်းစပ်ရမည့် layerများ ။ Layer များတွင် တူညီသော ဂျီဩမေတြီအမျိုးအစား ရှိရမည်။
   * - **Destination CRS** **(ဦးတည်အသုံးပြုမည့် CRS)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``CRS``
     - [crs]
     - Output layer အတွက် CRS ကိုရွေးချယ်ပါ။ မသတ်မှတ်ထားလျှင် ပထမဆုံး input layer ၏ CRS ကိုအသုံးပြုမည်။
   * - **Merged** **(ပေါင်းစပ်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Merged** **(ပေါင်းစပ်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Input layer များမှ feature များအားလုံးနှင့် attribute များအားလုံး ပါဝင်သော output vector layer 
       

Python code
............

**Algorithm ID**: ``native:mergevectorlayers``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisorderbyexpression:

Order by expression (Expression ဖြင့် အထားအသိုစီစဉ်ခြင်း)
----------------------------------------------------------

Expression တစ်ခုအပေါ် အခြေခံ၍ vector layer တစ်ခုကို sort (စဉ်) လုပ်ပေးပါသည်- expression တစ်ခုပေါ် အခြေခံ၍ feature index ကိုပြောင်းလဲပေးမည်ဖြစ်သည်။

သတိပြုရမည်မှာ ၎င်းသည် အချို့ provider များနှင့် မျှော်လင့်ထားသလို အလုပ်ဖြစ်နိုင်မည်မဟုတ်ဘဲ order (အစီအစဉ်) သည်လည်းအချိန်တိုင်း တသမတ်တည်း ရှိနေမည်မဟုတ်ပါ။


Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input Layer** **(ထည့်သွင်းအသုံးပြုသော Layer)**
     - ``INPUT``
     - [vector: any]
     - Sort (စဉ်) လုပ်ရမည့် ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Expression** **(စေခိုင်းချက်)**
     - ``EXPRESSION``
     - [expression]
     - Sorting အတွက် အသုံးပြုရမည့် Expression 
   * - **Sort ascending** **(ငယ်စဉ်ကြီးလိုက်စဉ်ခြင်း)**
     - ``ASCENDING``
     - [boolean]
       
       Default: True
     - အကယ်၍ အမှန်ခြစ်ပေးထားပါက vector layer တန်ဖိုးများကို ငယ်ရာမှ ကြီးရာသို့ စဉ်ပေးမည်ဖြစ်သည်။
   * - **Sort nulls first** **(Null တန်ဖိုးများကို ဦးစွာစဉ်ခြင်း)**
     - ``NULLS_FIRST``
     - [boolean]
       
       Default: False
     - အကယ်၍ အမှန်ခြစ်ပေးထားပါက Null တန်ဖိုးများကို ဦးစွာ စဉ်ပေးမည်ဖြစ်သည်။
   * - **Ordered** **(စီစဉ်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Ordered** **(စီစဉ်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output (စဉ်ထားသော) vector layer

Python code
............

**Algorithm ID**: ``native:orderbyexpression``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisrepairshapefile:

Repair Shapefile (Shapefile အား ပြန်လည်ပြုပြင်ခြင်း)
-----------------------------------------------------

SHX file အား (ပြန်လည်) ဖန်တီးခြင်းဖြင့် ပျက်စီးနေသော ESRI Shapefile dataset တစ်ခုအား ပြန်လည်ပြုပြင်ပေးပါသည်။  

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input Shapefile** **(ထည့်သွင်းအသုံးပြုသော Shapefile)**
     - ``INPUT``
     - [file]
     - ပျောက်ဆုံးနေသော သို့မဟုတ် ပျက်စီးနေသော SHX file တစ်ခုရှိသည့် ESRI Shapefile dataset ရှိရာ ဖိုင်လမ်းကြောင်း အပြည့်အစုံ
       

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Repaired layer** **(ပြန်လည်ပြုပြင်ထားသော layer)**
     - ``OUTPUT``
     - [vector: any]
     - ပြန်လည်ပြုပြင်ထားသော SHX file ပါဝင်သည့် input vector layer

Python code
............

**Algorithm ID**: ``native:repairshapefile``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisreprojectlayer:

Reproject layer (Layer ကို projection တစ်ခုမှတစ်ခုသို့ပြောင်းလဲခြင်း)
----------------------------------------------------------------------

Vector layer တစ်ခုကို အခြားမတူညီသော CRS (Coordinate Reference System) သို့ projection ပြောင်းလဲပေးပါသည်။ Reprojection လုပ်ထားသော layer တွင် input layer ကဲ့သို့ပင် တူညီသော feature များနှင့် attribute များရှိပါလိမ့်မည်။

|checkbox| တွင်အမှတ်ခြစ်ပေးထားခြင်းဖြင့် point ၊ line နှင့် polygon feature များအတွက် :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ရွေးချယ်ခွင့်ကိုအသုံးပြုနိုင်သည်။
 
.. seealso:: :ref:`qgisassignprojection` ၊
   :ref:`qgisdefinecurrentprojection` ၊ :ref:`qgisfindprojection`

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
   * - **Input Layer** **(ထည့်သွင်းအသုံးပြုသော Layer)**
     - ``INPUT``
     - [vector: any]
     - Reproject ပြုလုပ်မည့် input vector layer 
   * - **Target CRS** **(ဦးတည်အသုံးပြုမည့် CRS)**
     - ``TARGET_CRS``
     - [crs]

       Default: ``EPSG:4326 - WGS 84``
     - ဦးတည်အသုံးပြုမည့် ရည်ညွှန်းကိုဩဒိနိတ်စနစ်
   * - **Convert curved geometries to straight segments** **(မျဉ်းကွေးဂျီဩမေတြီများအား မျဉ်းပိုင်းအဖြောင့်များအဖြစ်ပြောင်းလဲခြင်း)**

       |332|

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``CONVERT_CURVED_GEOMETRIES``
     - [boolean]

       Default: False
     - အမှန်ခြစ်ထားပါက မျဉ်းကွေးဂျီဩမေတြီများသည် လုပ်ငန်းစဉ်အတွင်းတွင်  မျဉ်းပိုင်းအဖြောင့်များအဖြစ်ပြောင်းလဲသွားမည်ဖြစ်ပြီး ဖြစ်နိုင်ချေရှိသော ပုံပျက်တွန့်လိမ်သွားသည့် ပြဿနာများကို ရှောင်ရှားနိုင်မည်ဖြစ်သည်။
   * - **Reprojected** **(Projection ပြောင်းထားသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Coordinate Operation** **(ကိုသြဒိနိတ် လုပ်ဆောင်မှု)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``OPERATION``
     - [string]
     - လက်ရှိ project ၏ အသွင်ပြောင်းလဲခြင်း (transformation) setting များကို အမြဲတမ်းအသုံးပြုနေမည့်အစား သီးသန့် reprojection လုပ်ငန်းစဉ်တစ်ခုအတွက် အသုံးပြုမည့် သီးသန့်လုပ်ဆောင်မှု။ ၎င်းသည် သီးခြား layer တစ်ခုကို reprojection ပြုလုပ်ပြီး ထိုပြောင်းလဲခြင်းအပေါ်တွင် အသေးစိတ် ချိန်ညှိထိန်းချုပ်ရန်လိုအပ်ပါက အသုံးဝင်ပါသည်။ proj version >= 6 (6နှင့်အထက်) ဖြစ်ရန်လိုအပ်သည်။

       ပိုမိုသိရှိလိုပါက :ref:`datum_transformation` တွင်ဖတ်ရှုပါ။

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Reprojected** **(Projection ပြောင်းထားသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output (Projection ပြောင်းထားသော) vector layer

Python code
............

**Algorithm ID**: ``native:reprojectlayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgissavefeatures:

Save vector features to file (Vector feature များကို File အဖြစ်သိမ်းခြင်း)
---------------------------------------------------------------------------

Vector feature များကို သတ်မှတ်ထားသော file dataset ထဲတွင် သိမ်းဆည်းပေးပါသည်။ 

Dataset format များကို အသုံးပြုနိုင်သည့် layer များအတွက် layer အမည်အတွက် parameter တစ်ခုကိုအသုံးပြုခြင်းဖြင့် စိတ်ကြိုက်စာသားတစ်ခုကိုသတ်မှတ်နိုင်သည်။ GDAL မှသတ်မှတ်ထားသော dataset များနှင့် layer ရွေးချယ်စရာများကိုလည်း သတ်မှတ်ပေးနိုင်ပါသည်။ ပိုမိုသိရှိလိုသည့်အချက်အလက်များအတွက် အွန်လိုင်းမှ `GDAL documentation <https://gdal.org/drivers/vector/index.html>`_  တွင်ဖတ်ရှုနိုင်ပါသည်။
 

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
   * - **Vector features** **(Vector feature များ)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Saved features** **(သိမ်းဆည်းထားသော feature များ)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Save to temporary file]``
     - Feature များကိုသိမ်းဆည်းမည့် file ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Layer name** **(Layer အမည်)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``LAYER_NAME``
     - [string]
     - Output layer အတွက် အသုံးပြုမည့် အမည်
   * - **GDAL dataset options**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``DATASOURCE_OPTIONS``
     - [string]
     - Output format ၏ GDAL dataset ဖန်တီးခြင်း ရွေးချယ်စရာများ။ Semicolon (;) များဖြင့် ရွေးချယ်စရာတစ်ခုချင်းစီအား ခွဲခြားထားပါသည်။ 
   * - **GDAL layer options**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``LAYER_OPTIONS``
     - [string]
     - Output format ၏ GDAL layer ဖန်တီးခြင်း ရွေးချယ်စရာများ။ Semicolon (;) များဖြင့် ရွေးချယ်စရာတစ်ခုချင်းစီအား ခွဲခြားထားပါသည်။  

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Saved features** **(သိမ်းဆည်းထားသော feature များ)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - သိမ်းဆည်းထားသော feature များပါရှိသည့် vector layer 
   * - **File name and path** **(File အမည် နှင့် လမ်းကြောင်း)**
     - ``FILE_PATH``
     - [string]
     - Output file အမည်နှင့်လမ်းကြောင်း
   * - **Layer name** **(Layer အမည်)**
     - ``LAYER_NAME``
     - [string]
     - Layer ၏အမည်

Python code
............

**Algorithm ID**: ``native:savefeatures``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgissetlayerencoding:

Set layer encoding (Layer encoding ကိုသတ်မှတ်ခြင်း)
----------------------------------------------------

Layer တစ်ခု၏ attribute များကို ဖတ်ရှုရန်အတွက် အသုံးပြုမည့် encoding ကို သတ်မှတ်ပေးပါသည်။ Layer အား အပြီးတိုင်ပြောင်းလဲခြင်းမဟုတ်ဘဲ လက်ရှိ session အတွင်းတွင် layer ကိုမည်သို့ ဖတ်ရှုမည် ဆိုသည်ကိုသာ အကျိုးသက်ရောက်စေမည်ဖြစ်သည်။

.. note:: Encoding ပြောင်းလဲခြင်းကို အချို့ vector layer data ရင်းမြစ်များတွင်သာ အသုံးပြုနိုင်မည်ဖြစ်သည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Saved features** **(သိမ်းဆည်းထားသော feature များ)**
     - ``INPUT``
     - [vector: any]
     - Encoding အားသတ်မှတ်မည့် vector layer
   * - **Encoding**
     - ``ENCODING``
     - [string]
     - လက်ရှိ QGIS session ထဲ၌ layer တွင် သတ်မှတ်ပေးမည့် စာသား encoding

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output layer**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - သတ်မှတ်ထားသော encoding ပါဝင်သည့် input vector layer

Python code
............

**Algorithm ID**: ``native:setlayerencoding``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgissplitfeaturesbycharacter:

Split features by character (စာလုံးသင်္ကေတများအလိုက် feature များကို ပိုင်းခြားခြင်း)
--------------------------------------------------------------------------------------

သတ်မှတ်ထားသော စာလုံးသင်္ကေတတစ်ခုတွင် field တစ်ခု၏တန်ဖိုးကို ပိုင်းခြားခြင်းဖြင့် Feature များကို output feature များစွာအဖြစ်သို့ ပိုင်းခြားပေးမည်ဖြစ်သည်။ ဥပမာအားဖြင့် layer တစ်ခုတွင် feature များပါရှိပြီး ၎င်း feature များသည် field တစ်ခုထဲ၌ comma ဖြင့်ခွဲခြားထားသော တန်ဖိုးများစွာပါဝင်နေလျှင် ဤ algorithm အားအသုံးပြု၍ ၎င်းတန်ဖိုးများအား များစွာသော output feature များအဖြစ် ပိုင်းခြားနိုင်သည်။ Output ထဲတွင် ဂျီဩမေတြီများနှင့် အခြား attribute များသည်မပြောင်းလဲပဲ ကျန်ရှိနေမည်ဖြစ်သည်။ နောက်ထပ်ရွေးချယ်စရာအနေနှင့် Feature များကိုခွဲရာတွင် ပြောင်းလွယ်ပြင်လွယ်ဖြစ်စေရန်အတွက် separator string သည် ပုံမှန် expression တစ်ခုဖြစ်နိုင်ပါသည်။

|checkbox| တွင်အမှန်ခြစ်ပေးခြင်းဖြင့် point ၊ line နှင့် polygon feature များအတွက် :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း <processing_inplace_edit>` ကိုရွေးချယ်နိုင်သည်။

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
   * - **Input Layer** **(ထည့်သွင်းအသုံးပြုသော Layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Split using values in the field** **(Field ထဲရှိ တန်ဖိုးများကိုအသုံးပြု၍ ပိုင်းခြားခြင်း)**
     - ``FIELD``
     - [tablefield: any]
     - ပိုင်းခြားခြင်းအတွက် အသုံးပြုမည့် Field 
   * - **Split value using character** **(စာလုံးသင်္ကေတများအသုံးပြု၍ တန်ဖိုးများကို ပိုင်းခြားခြင်း)**
     - ``CHAR``
     - [string]
     - ပိုင်းခြားခြင်းအတွက် အသုံးပြုမည့် စာလုံးသင်္ကေတများ 
   * - **Use regular expression separator** **(Regular expression separator အားအသုံးပြုခြင်း)**
     - ``REGEX``
     - [boolean]
       
       Default: False
     - 
   * - **Split** **(ပိုင်းခြားထားသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
       
       Default: ``Create temporary layer``
     - Output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Split** **(ပိုင်းခြားထားသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output vector layer

Python code
............

**Algorithm ID**: ``native:splitfeaturesbycharacter``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgissplitvectorlayer:

Split vector layer (Vector layer များကို ပိုင်းခြားခြင်း)
----------------------------------------------------------

Input layer တစ်ခုနှင့် attribute တစ်ခုပေါ်တွင်အခြေခံ၍ vector များအစုအဝေးတစ်ခုကို output folder ထဲတွင်ဖန်တီးပေးပါသည်။ အလိုရှိသော field ထဲရှိ unique တန်ဖိုးများ တွေ့ရှိရသလောက်အရေအတွက်အတိုင်း output folder ထဲတွင် layer များပါဝင်ပါလိမ့်မည်။

ထွက်ရှိလာသော file များ၏အရေအတွက်သည် သတ်မှတ်ထားသော attribute အတွက် ကွဲပြားသော တန်ဖိုးများ၏အရေအတွက်နှင့် တူညီမည်ဖြစ်သည်။ 

၎င်းသည် *merging* လုပ်ငန်းစဉ်နှင့် ဆန့်ကျင်ဘက်ဖြစ်သည်။

**Default menu**- :menuselection:`Vector --> Data Management Tools`

.. seealso:: :ref:`qgismergevectorlayers`

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
   * - **Input Layer** **(ထည့်သွင်းအသုံးပြုသော Layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Unique ID field**
     - ``FIELD``
     - [tablefield: any]
     - ပိုင်းခြားခြင်းအတွက် အသုံးပြုမည့် Field 
   * - **Output directory** **(ရလာဒ်များ သိမ်းဆည်းရာ ဖိုင်လမ်းကြောင်း)**
     - ``OUTPUT``
     - [folder]
       
       Default: ``[Save to temporary folder]``
     - Output layer များအတွက် ဖိုင်လမ်းကြောင်းသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **directory_output_types**
          :end-before: **end_directory_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output file type** **(ရလာဒ်ဖိုင်အမျိုးအစား)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``FILE_TYPE``
     - [enumeration]

       Default:  Dialog window ထဲရှိ ``gpkg``
     - Output file များ၏ extension ကို ရွေးချယ်ပါ။ အကယ်၍ မရွေးချယ်ထားလျှင် သို့မဟုတ် ကိုက်ညီမှုမရှိလျှင် output file များအား "Default output vector layer extension" Processing setting ထဲတွင်သတ်မှတ်ထားသော format အတိုင်း အသုံးပြုမည်ဖြစ်သည်။
       
Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output directory** **(ရလာဒ်များ သိမ်းဆည်းရာ ဖိုင်လမ်းကြောင်း)**
     - ``OUTPUT``
     - [folder]
     - Output layer များအတွက် ဖိုင်လမ်းကြောင်း
   * - **Output layers**
     - ``OUTPUT_LAYERS``
     - [input နှင့်အတူတူဖြစ်ပါသည်] [list]
     - ပိုင်းခြားခြင်းမှရရှိလာသော output vector layer များ

Python code
............

**Algorithm ID**: ``native:splitvectorlayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgistruncatetable:

Truncate table (ဇယားထဲမှ အချက်အလက်များအား ရှင်းလင်းခြင်း)
----------------------------------------------------------

Layer တစ်ခုအား ၎င်းအတွင်းရှိ feature အားလုံးကိုဖျက်ခြင်းဖြင့် ရှင်းလင်းပေးပါသည်။

.. warning:: ဤ algorithm အသုံးပြုပါက layer အား ၎င်းနေရာတွင်ပင် ပြင်ဆင်ပြောင်းလဲလိုက်မည်ဖြစ်ပြီး ဖျက်လိုက်သော feature များကို ပြန်လည်ရယူနိုင်မည်မဟုတ်ပါ။
   
Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input Layer** **(ထည့်သွင်းအသုံးပြုသော Layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Truncated layer** **(ရှင်းလင်းထားသော layer)**
     - ``OUTPUT``
     - [folder]
     - ရှင်းလင်းထားသော (ဗလာဖြစ်နေသည့်) layer

Python code
............

**Algorithm ID**: ``native:truncatetable``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |332| replace:: ``NEW in 3.32``
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
