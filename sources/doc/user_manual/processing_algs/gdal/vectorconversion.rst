Vector conversion (Vector များကိုပြောင်းလဲခြင်း)
=================================================

.. only:: html

   .. contents::
      :local:
      :depth: 1


.. _gdalconvertformat:

Convert format (Format ပြောင်းလဲခြင်း)
---------------------------------------

OGR မှလုပ်ဆောင်ပေးနိုင်သော မည်သည့် vector layer ကိုမဆို အခြား OGR မှလုပ်ဆောင်ပေးနိုင်သော format အဖြစ်ပြောင်းလဲပေးပါသည်။

Algorithm ကို `ogr2ogr utility <https://gdal.org/programs/ogr2ogr.html>`_ မှ ရယူပါသည်။

Parameter များ
...............

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Convert all layers from dataset** (**Dataset မှ layer များအားလုံးကို ပြောင်းလဲခြင်း**)
     - ``CONVERT_ALL_LAYERS``
     - [boolean]

       Default: False
     - Dataset တစ်ခုလုံးကိုပြောင်းလဲပေးပါသည်။ ဤနည်းလမ်းအတွက် အသုံးပြုနိုင်သော format များမှာ :file:`GPKG` နှင့် :file:`GML` တို့ဖြစ်ကြပါသည်။
   * - **Converted** (**ပြောင်းလဲထားသော**)
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output vector layer ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် - 

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

       ``Save to File (File အဖြစ်သိမ်းဆည်းခြင်း)`` အတွက် output format ကိုသတ်မှတ်ပေးရပါမည်။ GDAL vector format များအားလုံး အလုပ်လုပ်ပါသည်။ ``Save to a Temporary File (ယာယီ file အဖြစ်သိမ်းဆည်းခြင်း)`` အတွက် QGIS ၏မူရင်း vector format ကိုအသုံးပြုပါသည်။

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးခြင်း နည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: '' (ထပ်ဆောင်း ရွေးချယ်စရာ မရှိပါ)
     - ထပ်ဆောင်း GDAL ဖန်တီးခြင်း နည်းလမ်းများ

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Converted** (**ပြောင်းလဲထားသော**)
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output vector layer

Python code
............

**Algorithm ID**: ``gdal:convertformat``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalrasterize_over:

Rasterize (overwrite with attribute)  (Raster ပြောင်းလဲခြင်း (attribute ဖြင့်အစားထိုးပြင်ဆင်ခြင်း))
----------------------------------------------------------------------------------------------------

Vector layer တစ်ခုမှ တန်ဖိုးများဖြင့် raster layer ကို အစားထိုးပြင်ဆင်ပါသည်။ ထပ်နေသော vector feature များ၏ attribute တန်ဖိုးများကိုအခြေခံပြီး တန်ဖိုးအသစ်များကို သတ်မှတ်ပါသည်။

Algorithm ကို `GDAL rasterize utility <https://gdal.org/programs/gdal_rasterize.html>`_ မှ ရယူပါသည်။

Parameter များ
...............

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
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Input raster layer** (**ထည့်သွင်းအသုံးပြုသော raster layer**)
     - ``INPUT_RASTER``
     - [raster]
     - ထည့်သွင်းအသုံးပြုသော raster layer
   * - **Field to use for a burn-in value** (**Burn-in တန်ဖိုးတစ်ခုအတွက် အသုံးပြုမည့် column**)

        Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``FIELD``
     - [tablefield: numeric]
     - Pixel တန်ဖိုးများကို သတ်မှတ်ရန် အသုံးပြုမည့် attribute column ကို သတ်မှတ်ပေးပါသည်။

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   *  - **Add burn in values to existing raster values** (**ရှိနေပြီးသား raster တန်ဖိုးများသို့ burn-in တန်ဖိုးများ ပေါင်းထည့်ခြင်း**)
      - ``ADD``
      - [boolean]

        Default: False
      - False ဖြစ်လျှင် ရွေးချယ်ထားသော field ၏တန်ဖိုးကို pixel များတွင် သတ်မှတ်ပေးပါမည်။ True ဖြစ်လျှင် ရွေးချယ်ထားသော field ၏တန်ဖိုးကို input raster layer ၏တန်ဖိုးတွင် ပေါင်းထည့်မည်ဖြစ်သည်။
   * - **Additional command-line parameters** (**ထပ်ဆောင်း command-line parameter များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTRA``
     - [string]

       Default: None
     - ထပ်ဆောင်း GDAL command line ရွေးချယ်စရာများကို ထည့်ပေါင်းခြင်း

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   *  - **Rasterized** (**Raster ပြောင်းလဲထားသော**)
      - ``OUTPUT``
      - [raster]
      - အစားထိုးပြင်ဆင်ထားသော input raster layer

Python code
............

**Algorithm ID**: ``gdal:rasterize_over``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalrasterize_over_fixed_value:

Rasterize (overwrite with fixed value) (Raster ပြောင်းလဲခြင်း (ပုံသေတန်ဖိုးဖြင့် အစားထိုးပြင်ဆင်ခြင်း))
--------------------------------------------------------------------------------------------------------

Raster layer ၏ အစိတ်အပိုင်းများကို ပုံသေတန်ဖိုးတစ်ခုဖြင့် အစားထိုးပြင်ဆင်ပါသည်။ အသုံးပြုထားသော (ထပ်နေသော) vector layer ပေါ်ကိုအခြေခံပြီး အစားထိုးပြင်ဆင်မည့် pixel များကိုရွေးချယ်ပါသည်။

Algorithm ကို `GDAL rasterize utility <https://gdal.org/programs/gdal_rasterize.html>`_ မှ ရယူပါသည်။

Parameter များ
...............

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
   *  - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
      - ``INPUT``
      - [vector: any]
      - ထည့်သွင်းအသုံးပြုသော vector layer
   *  - **Input raster layer** (**ထည့်သွင်းအသုံးပြုသော raster layer**)
      - ``INPUT_RASTER``
      - [raster]
      - ထည့်သွင်းအသုံးပြုသော raster layer
   *  - **A fixed value to burn** (**လုပ်ဆောင်ရန် ပုံသေတန်ဖိုးတစ်ခု**)
      - ``BURN``
      - [number]

        Default: 0.0
      - လုပ်ဆောင်ရန် တန်ဖိုး

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   *  - **Add burn in values to existing raster values** (**ရှိနေပြီးသား raster တန်ဖိုးများထဲသို့ burn-in တန်ဖိုးများပေါင်းထည့်ခြင်း**)
      - ``ADD``
      - [boolean]

        Default: False
      - False ဖြစ်လျှင် ပုံသေတန်ဖိုးများကို pixel များတွင်သတ်မှတ်ပါမည်။ True ဖြစ်လျှင် ပုံသေတန်ဖိုးကို input raster layer ၏တန်ဖိုးထဲသို့ ပေါင်းထည့်ပေးပါသည်။
   * - **Additional command-line parameters** (**ထပ်ဆောင်း command-line parameter များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTRA``
     - [string]

       Default: None
     - ထပ်ဆောင်း GDAL command line ရွေးချယ်စရာများကို ထည့်ပေါင်းခြင်း

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   *  - **Rasterized** (**Raster ပြောင်းလဲထားသော**)
      - ``OUTPUT``
      - [raster]
      - အစားထိုးပြင်ဆင်ထားသော input raster layer

Python code
............

**Algorithm ID**: ``gdal:rasterize_over_fixed_value``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalrasterize:

Rasterize (vector to raster) (Raster ပြောင်းလဲခြင်း (vector မှ raster သို့))
-----------------------------------------------------------------------------

Vector geometry (point များ၊ line များ နှင့် polygon များ) များကို raster ဓာတ်ပုံအဖြစ် ပြောင်းလဲပေးပါသည်။

Algorithm ကို `GDAL rasterize utility <https://gdal.org/programs/gdal_rasterize.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Conversion`

Parameter များ
...............

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
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Field to use for a burn-in value** (**Burn-in တန်ဖိုးတစ်ခုအတွက် အသုံးပြုမည့် column**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``FIELD``
     - [tablefield: numeric]
     - Pixel များအတွက် attribute များကိုရွေးချယ်သင့်သော attribute column ကိုသတ်မှတ်ပေးပါသည်
   * - **A fixed value to burn** (**လုပ်ဆောင်မည့် ပုံသေတန်ဖိုး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``BURN``
     - [number]

       Default: 0.0
     - Feature များအားလုံးအတွက် band တစ်ခုထဲတွင် လုပ်ဆောင်မည့် ပုံသေတန်ဖိုးတစ်ခု
   * - **Burn value extracted from the "Z" values of the feature** (**Feature ၏ အမြင့် Z တန်ဖိုးများမှ ဆွဲထုတ်ထားသော Burn တန်ဖိုး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``USE_Z``
     - [boolean]

       Default: False
     - Feature ၏ အမြင့်တန်ဖိုး Z များမှ burn တန်ဖိုးတစ်ခုကို ဆွဲထုတ်သင့်သည်ဟု ညွှန်ပြပေးပါသည်။ Point နှင့် line များဖြင့် အလုပ်လုပ်ပေးပါသည် (segment တစ်ခုချင်း တလျှောက်တွင် အဖြောင့် interpolation)။ Polygon များအတွက်မူ ၎င်းတို့သည် ပြားနေမှသာ ကောင်းကောင်းမွန်မွန် အလုပ်လုပ်ဆောင်ပါသည် (မျဉ်းအဆစ်အားလုံးအတွက် အမြင့်တန်ဖိုးတူရမည်ကို ဆိုလိုပါသည်)။
   * - **Output raster size units** (**Output raster အရွယ်အစား unit များ**)
     - ``UNITS``
     - [enumeration]

       Default: 0
     - Output raster အရွယ်အစား/resolution ကိုသတ်မှတ်ခြင်းအတွက် အသုံးပြုမည့် unit များ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       * 0 --- Pixel များ
       * 1 --- Georeferenced unit များ

   * - **Width/Horizontal resolution** (**အကျယ်/ရေပြင်ညီ resolution**)
     - ``WIDTH``
     - [number]

       Default: 0.0
     - Output raster ၏အကျယ် (အရွယ်အစား unit သည် "Pixels" ဖြစ်လျှင်) သို့မဟုတ် ရေပြင်ညီ resolution (အရွယ်အစား unit သည် "Georeferenced units" ဖြစ်လျှင်) ကိုသတ်မှတ်ပေးပါသည်။ အနည်းဆုံးတန်ဖိုး - 0.0။
   * - **Height/Vertical resolution** (**အမြင့်/ဒေါင်လိုက် resolution**)
     - ``HEIGHT``
     - [number]

       Default: 0.0
     - Output raster ၏ အမြင့် (အရွယ်အစား unit သည် "Pixels" ဖြစ်လျှင်) သို့မဟုတ် ဒေါင်လိုက် resolution (အရွယ်အစား uniy သည် "Georeferenced units" ဖြစ်လျှင်) ကိုသတ်မှတ်ပေးပါသည်။
   * - **Output extent** (**Output နယ်ပယ်အတိုင်းအတာအကျယ်အဝန်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTENT``
     - [extent]

     - Output raster layer ၏ extent ။ Extent ကို သတ်မှတ်မပေးထားလျှင် ရွေးချယ်ထားသော reference layer များကို ခြုံငုံသော အသေးဆုံး extent ကို အသုံးပြုပါမည်။

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Assign a specified nodata value to output bands** (**Output band များသို့ သီးခြား nodata တန်ဖိုးတစ်ခု သတ်မှတ်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``NODATA``
     - [number]

       Default: 0.0
     - Output band များသို့ သီးခြား nodata တန်ဖိုးတစ်ခု သတ်မှတ်ပေးပါသည်
   * - **Rasterized** (**Raster ပြောင်းလဲထားသော**)
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Output raster layer ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**
     
       ``Save to File (File အဖြစ်သိမ်းဆည်းခြင်း)`` အတွက် output format ကိုသတ်မှတ်ပေးရပါမည်။ GDAL vector format များအားလုံး အလုပ်လုပ်ပါသည်။ ``Save to a Temporary File (ယာယီ file အဖြစ်သိမ်းဆည်းခြင်း)`` အတွက် QGIS ၏မူရင်း vector format ကိုအသုံးပြုပါသည်။

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးမှုနည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: ''
     - Raster ဖန်တီးခြင်းကို ထိန်းချုပ်သော ဖန်တီးခြင်းနည်းလမ်းများကို ပိုမိုပေါင်းထည့်ရန် (အရောင်၊ block အရွယ်အစား၊ file ချုံ့ခြင်း)။ လွယ်ကူစေရန် ကြိုတင်သတ်မှတ်ထားသော profile များကိုအသုံးပြုနိုင်ပါသည် (:ref:`GDAL driver options section <gdal_createoptions>` တွင်ကြည့်ပါ)။ အစုလိုက်လုပ်ဆောင်ခြင်း (Batch process) နှင့် Model Designer - နည်းလမ်းများစွာကို pipe character (``|``) ဖြင့်ပိုင်းခြားထားပါသည်။
   
   * - **Output data type** (**Output data အမျိုးအစား**)
     - ``DATA_TYPE``
     - [enumeration]

       Default: 5
     - Output raster file ၏ format ကိုသတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာများမှာ-

       .. include:: ../algs_include.rst
          :start-after: **raster_data_types**
          :end-before: **end_raster_data_types**

   * - **Pre-initialize the output image with value** (**Output ဓာတ်ပုံကို တန်ဖိုးဖြင့် ကြိုတင် စတင်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``INIT``
     - [number]

     - ဤတန်ဖိုးဖြင့် output ဓာတ်ပုံ band များကို ကြိုတင်စတင်စေပါသည်။ Output file ထဲတွင် nodata တန်ဖိုးအဖြစ် မှတ်သားမပေးပါ။ Band များအားလုံးတွင် တန်ဖိုးအတူတူ အသုံးပြုပါသည်။
   * - **Invert rasterization** (**ပြောင်းပြန် raster ပြောင်းလဲခြင်း**)
     - ``INVERT``
     - [boolean]

       Default: False
     - ပုံသေ burn တန်ဖိုးတစ်ခု လုပ်ဆောင်ပါ သို့မဟုတ် အသုံးပြုထားသော polygon ထဲမှမဟုတ်သော ဓာတ်ပုံ၏ အစိတ်အပိုင်းများအားလုံးထဲသို့ ပထမ feature နှင့်ဆက်စပ်သော burn တန်ဖိုးကို လုပ်ဆောင်ပါ။
   * - **Additional command-line parameters** (**ထပ်ဆောင်း command-line parameter များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTRA``
     - [string]

       Default: None
     - ထပ်ဆောင်း GDAL command line ရွေးချယ်စရာများကို ထည့်ပေါင်းခြင်း

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Rasterized** (**Raster ပြောင်းလဲထားသော**)
     - ``OUTPUT``
     - [raster]
     - Output raster layer

Python code
............

**Algorithm ID**: ``gdal:rasterize``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**
