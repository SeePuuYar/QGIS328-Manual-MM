Raster analysis (Raster ဆန်းစစ်လေ့လာခြင်း)
===========================================

.. only:: html

   .. contents::
      :local:
      :depth: 1
      :class: toc_columns


.. _qgiscellstackpercentrankfromvalue:

Cell stack percent rank from value (တန်ဖိုးမှ cell အစုအထပ် ရာခိုင်နှုန်းအဆင့်)
-------------------------------------------------------------------------------

တစ်ခုတည်းသော ထည့်သွင်းတန်ဖိုး (single input value) အပေါ်တွင် အခြေခံထားသော raster များ အစုအထပ်တစ်ခု(stack of raster) တစ်ခု၏ cell အလိုက်ရာခိုင်နှုန်းအဆင့်တန်ဖိုး (cell-wise percentrank value) ကို တွက်ချက်ပြီး ၎င်းတို့ကို output raster တစ်ခုထဲသို့ ရေးသွင်းပါသည်။

Cell ၏ တည်နေရာတစ်ခုချင်းစီ၌ သတ်မှတ်ထားသောတန်ဖိုး (specified value) ကို တစ်ခုနှင့်တစ်ခုထပ်ထားသော အစုအထပ် (stack) ထဲရှိ သက်ဆိုင်ရာတန်ဖိုးများနှင့် input raster များမှ sort လုပ်ထားသော cell တန်ဖိုးများ အကြားတွင် အဆင့်သတ်မှတ်ပါသည်။ Stack value distribution (အစုအထပ်တန်ဖိုးပြန့်နှံ့ခြင်း) ၏ အပြင်ဘက်တွင်ရှိသော တန်ဖိုးများအတွက်မူ cell တန်ဖိုးများအကြားတွင် တန်ဖိုးကို အဆင့်မသတ်မှတ်နိုင်သောကြောင့် algorithm သည် NoData ကို ပြန်ထုတ်ပေးမည်ဖြစ်သည်။ 

Percentile တွက်ချက်ခြင်းအတွက် နည်းလမ်း နှစ်ခုရှိပါသည်-

* Inclusive linear interpolation (PERCENTRANK.INC)
* Exclusive linear interpolation (PERCENTRANK.EXC)

Linear interpolation နည်းလမ်းသည် မတူညီသော တန်ဖိုးများအတွက် သိသာထင်ရှား (unique) သည့် ရာခိုင်နှုန်းအဆင့်(percent rank) ကို ရရှိစေပါသည်။ Interpolation နည်းလမ်းနှစ်ခုစလုံးသည် Microsoft Excel သို့မဟုတ် `LibreOffice <https://help.libreoffice.org/latest/en-US/text/scalc/01/04060184.html?DbPAR=CALC#bm_id3148807>`_  မှ အကောင်အထည်ဖော်ဆောင်ရွက်ထားသော ၎င်းတို့၏ သက်ဆိုင်ရာနည်းလမ်းများကို လိုက်နာပါသည်။ 

Output raster ၏ အကျယ်အဝန်းနယ် (extent) နှင့် ကြည်လင်ပြတ်သားမှု (resolution) ကို reference (ရည်ညွှန်း) raster တစ်ခုဖြင့် သတ်မှတ်ပါသည်။ Reference (ရည်ညွှန်း) raster layer ၏ cell အရွယ်အစားနှင့်မကိုက်ညီသော input raster layer များအား nearest neighbor resampling ကို အသုံးပြုပြီး cell အရွယ်အစားပြောင်းလဲပေး (resample) မည်ဖြစ်ပါသည်။ အကယ်၍ "Ignore NoData values" ဆိုသည့် parameter ကို သတ်မှတ်ထားခြင်းမရှိပါက မည့်သည့် input layer များထဲမဆိုရှိ NoData တန်ဖိုးများသည် NoData cell output တစ်ခုထဲတွင် ရရှိလိမ့်မည်ဖြစ်ပါသည်။ Output raster data အမျိုးအစားသည် အမြဲတမ်း ``Float32`` ဖြစ်မည်ဖြစ်ပါသည်။

.. figure:: img/percentrankfromvalue.png
  :align: center

  ရာခိုင်နှုန်းအဆင့်သတ်မှတ်ချက်တန်ဖိုး = 1 ။ ``NoData`` cell များ (မီးခိုးရောင်) ကို လျစ်လျူရှုထားပါသည်။

.. seealso:: :ref:`qgiscellstackpercentile` ၊ :ref:`qgiscellstackpercentrankfromrasterlayer`


Parameters (သတ်မှတ်ချက်များ)
.............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 100 100 100 300
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layers** **(ထည့်သွင်းအသုံးပြုသော layer များ)**
     - ``INPUT`` 
     - [raster] [list] 
     - အကဲဖြတ်သတ်မှတ်ရန် (evaluate) Raster layer များ။ အကယ်၍ data raster stack (အစုအထပ်) တွင် multiband(လှိုင်းအလွှာများစွာပါဝင်သည့်) raster များကို အသုံးပြုထားပါက algorithm သည် raster များ၏ ပထမ band အပေါ်တွင် ခွဲခြမ်းစိတ်ဖြာမှု (analysis) ကို အမြဲတမ်း ဆောင်ရွက်မည်ဖြစ်ပါသည်။ 
   * - **Method** **(နည်းလမ်း)**
     - ``METHOD`` 
     - [enumeration]

       Default: 0
     - Percentile တွက်ချက်ခြင်းအတွက် နည်းလမ်း-

       * 0 --- Inclusive linear interpolation (PERCENTRANK.INC)
       * 1 --- Exclusive linear interpolation (PERCENTRANK.EXC)
   * - **Value** **(တန်ဖိုး)**
     - ``VALUE`` 
     - [number]

       Default : 10.0
     - တစ်ခုနှင့်တစ်ခုထပ်ထားသော အစုအထပ် (stack) ထဲရှိ သက်ဆိုင်ရာတန်ဖိုးများနှင့် input raster များမှ sort လုပ်ထားသော cell တန်ဖိုးများ အကြားတွင် အဆင့်သတ်မှတ်ရန်တန်ဖိုး 
   * - **Ignore NoData values** **(NoData တန်ဖိုးများကို လျစ်လျူရှုပါ)**
     - ``IGNORE_NODATA`` 
     - [boolean]

       Default: True
     - အကယ်၍ အမှန်ခြစ်ဖြုတ်ထားပါက input layer များထဲရှိ မည်သည့် NoData cell များမဆိုသည် output raster ထဲတွင် NoData cell တစ်ခုကို ဖြစ်ပေါ်စေမည်ဖြစ်ပါသည်။ 
   * - **Reference layer** **(ရည်ညွှန်း layer)**
     - ``REFERENCE_LAYER``
     - [raster]
     - Output layer ဖန်တီးခြင်းအတွက် reference (ရည်ညွှန်း) layer (အကျယ်အဝန်းနယ် (extent)၊ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (CRS) ၊ pixel အတိုင်းအတာများ (dimensions))
   * - **Output layer** **(ရလာဒ် layer)**
     - ``OUTPUT`` 
     - [input ကဲ့သို့အတူတူဖြစ်ပါသည်။]

       Default: ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 100 100 100 300
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **output no data value** **(Output NoData တန်ဖိုး)**
     - ``OUTPUT_NODATA_VALUE`` 
     - [number]

       Default: -9999.0
     - Output layer ထဲတွင် nodata အတွက် အသုံးပြုမည့် တန်ဖိုး

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 100 100 100 300

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output layer**
     - ``OUTPUT``
     - [raster]
     - ရလာဒ် (result) ပါဝင်သည့် output raster layer
   * - **CRS authority identifier**
     - ``CRS_AUTHID``
     - [string]
     - Output raster layer ၏ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (coordinate reference system)
   * - **Extent** **(အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [string]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent)
   * - **Width in pixels** **(Pixel ဖြင့် အကျယ်)**
     - ``WIDTH_IN_PIXELS``
     - [integer]
     - Output raster layer ထဲရှိ column (တိုင်) များအရေအတွက်
   * - **Height in pixels** **(Pixel ဖြင့် အမြင့်)**
     - ``HEIGHT_IN_PIXELS`` 
     - [integer]
     - Output raster layer ထဲရှိ row (တန်း) များအရေအတွက်
   * - **Total pixel count** **(Pixel အရေအတွက် စုစုပေါင်း)**
     - ``TOTAL_PIXEL_COUNT``
     - [integer]
     - Output raster layer ထဲရှိ pixel အရေအတွက် (count)

Python code
............

**Algorithm ID**: ``native:cellstackpercentrankfromvalue``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiscellstackpercentile:

Cell stack percentile (Cell အစုအထပ် ရာခိုင်နှုန်း)
---------------------------------------------------

Raster များအစုအထပ် (stack) တစ်ခု၏ cell အလိုက်ရာခိုင်နှုန်းအဆင့်တန်ဖိုး (cell-wise percentrank value) တန်ဖိုးကို တွက်ချက်ပြီး ရလာဒ်များ (results) ကို output raster တစ်ခုထဲသို့ ရေးသွင်းပေးပါသည်။ ရရှိလာမည့် percentile ကို percentile input value (ထည့်သွင်းထားသည့် percentile တန်ဖိုး) ဖြင့်ဆုံးဖြတ်ပါသည် (အပိုင်းအခြားပမာဏမှာ 0 နှင့် 1 အကြားဖြစ်ပါသည်)။ Cell တည်နေရာတစ်ခုချင်းစီ၌ သတ်မှတ်ထားသော percentile ကို တစ်ခုနှင့်တစ်ခုထပ်ထားသော အစုအထပ် (stack) ထဲရှိ သက်ဆိုင်ရာတန်ဖိုးများနှင့် input raster များမှ sort လုပ်ထားသော cell တန်ဖိုးများကို အသုံးပြုပြီး ရရှိပါသည်။

Percentile တွက်ချက်ခြင်းအတွက် နည်းလမ်း(၃)မျိုးရှိပါသည်-

* Nearest rank - သတ်မှတ်ထားသည့် percentile နှင့် အနီးဆုံးဖြစ်သည့် တန်ဖိုးကို ရရှိစေသည်။ 
* Inclusive linear interpolation (PERCENTRANK.INC)
* Exclusive linear interpolation (PERCENTRANK.EXC)

Linear interpolation နည်းလမ်းများသည် မတူညီသော percentile များအတွက် သိသာထင်ရှားသည့်တန်ဖိုးများ (unique values) ကို ရစေမည်ဖြစ်ပါသည်။ Interpolation နည်းလမ်းနှစ်မျိုးလုံးသည် `LibreOffice <https://help.libreoffice.org/latest/en-US/text/scalc/01/04060184.html?DbPAR=CALC#bm_id3148807>`_ သို့မဟုတ် Microsoft Excel မှ အကောင်အထည်ဖော်ဆောင်ရွက်ထားသော ၎င်းတို့၏ သက်ဆိုင်ရာနည်းလမ်းများကို လိုက်နာပါသည်။ 

Output raster ၏ အကျယ်အဝန်းနယ် (extent) နှင့် ကြည်လင်ပြတ်သားမှု (resolution) ကို reference (ရည်ညွှန်း) raster တစ်ခုဖြင့် သတ်မှတ်ပါသည်။ Reference (ရည်ညွှန်း) raster layer ၏ cell အရွယ်အစားနှင့်မကိုက်ညီသော input raster layer များအား nearest neighbor resampling ကို အသုံးပြုပြီး cell အရွယ်အစားပြောင်းလဲပေး (resample) မည်ဖြစ်ပါသည်။ အကယ်၍ "Ignore NoData values" ဆိုသည့် parameter ကို သတ်မှတ်ထားခြင်းမရှိပါက မည့်သည့် input layer များထဲမဆိုရှိ NoData တန်ဖိုးများသည် NoData cell output တစ်ခုထဲတွင် ရရှိလိမ့်မည်ဖြစ်ပါသည်။ Output raster data အမျိုးအစားသည် အမြဲတမ်း ``Float32`` ဖြစ်မည်ဖြစ်ပါသည်။


.. figure:: img/percentile.png
  :align: center

  Percentile = 0.25 ။ ``NoData`` cell (မီးခိုးရောင်) များကို လျစ်လျူရှုထားပါသည်။  

.. seealso:: :ref:`qgiscellstackpercentile` ၊ :ref:`qgiscellstackpercentrankfromrasterlayer`

Parameters (သတ်မှတ်ချက်များ)
.............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 100 100 100 300
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layers** **(ထည့်သွင်းအသုံးပြုသော layer များ)**
     - ``INPUT`` 
     - [raster] [list]
     - အကဲဖြတ်သတ်မှတ် (evaluate) ရန် Raster layer များ။ အကယ်၍ data raster stack တွင် multiband (band များစွာပါဝင်သည့်) raster များကို အသုံးပြုထားပါက algorithm သည် raster များ၏ ပထမ band ပေါ်တွင် ခွဲခြမ်းစိတ်ဖြာမှု (analysis) ကို အမြဲတမ်း ဆောင်ရွက်မည်ဖြစ်ပါသည်။ 
   * - **Method** **(နည်းလမ်း)**
     - ``METHOD`` 
     - [enumeration]

       Default: 0
     - Percentile တွက်ချက်ခြင်းအတွက် နည်းလမ်း-

       * 0 --- Nearest rank - သတ်မှတ်ထားသည့် percentile များနှင့် အနီးစပ်ဆုံးဖြစ်သည့် တန်ဖိုးကို ရရှိစေသည်။
       * 1 --- Inclusive linear interpolation (PERCENTILE.INC)
       * 2 --- Exclusive linear interpolation (PERCENTILE.EXC)
   * - **Percentile**
     - ``VALUE`` 
     - [number]

       Default: 0.25
     - တစ်ခုနှင့်တစ်ခုထပ်ထားသော အစုအထပ် (stack) ထဲရှိ သက်ဆိုင်ရာတန်ဖိုးများနှင့် input raster များမှ sort လုပ်ထားသော cell တန်ဖိုးများ အကြားတွင် အဆင့်သတ်မှတ်ရန်တန်ဖိုး။ 0 နှင့် 1 အကြားဖြစ်ပါသည်။
   * - **Ignore NoData values** **(NoData တန်ဖိုးများကို လျစ်လျူရှုပါ)**
     - ``IGNORE_NODATA`` 
     - [boolean]

       Default: True
     - အကယ်၍ အမှန်ခြစ်ဖြုတ်ထားပါက input layer များထဲရှိ မည်သည့် NoData cell များမဆိုသည် output raster ထဲတွင် NoData cell တစ်ခုကို ဖြစ်ပေါ်စေမည်ဖြစ်ပါသည်။ 
   * - **Reference layer** **(ရည်ညွှန်း layer)**
     - ``REFERENCE_LAYER``
     - [raster]
     - Output layer ဖန်တီးခြင်းအတွက် reference (ရည်ညွှန်း) layer (အကျယ်အဝန်းနယ် (extent)၊ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (CRS) ၊ pixel အတိုင်းအတာများ (dimensions))
   * - **Output layer** **(ရလာဒ် layer)**
     - ``OUTPUT`` 
     - [input ကဲ့သို့အတူတူဖြစ်ပါသည်။]

       Default: ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 50 50 50 100
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output no data value** 
     - ``OUTPUT_NODATA_VALUE``
     - [number] [ဂဏန်း]

       Default: -9999.0
     - Output layer ထဲတွင် nodata အတွက် အသုံးပြုမည့်တန်ဖိုး


Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 100 100 100 300

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output layer**
     - ``OUTPUT``
     - [raster]
     - ရလာဒ် (result) ပါဝင်သည့် output raster layer
   * - **CRS authority identifier**
     - ``CRS_AUTHID``
     - [string]
     - Output raster layer ၏ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (coordinate reference system)
   * - **Extent** **(အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [string]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent)
   * - **Width in pixels** **(Pixel ဖြင့် အကျယ်)**
     - ``WIDTH_IN_PIXELS``
     - [integer]
     - Output raster layer ထဲရှိ column (တိုင်) များအရေအတွက်
   * - **Height in pixels** **(Pixel ဖြင့် အမြင့်)**
     - ``HEIGHT_IN_PIXELS`` 
     - [integer]
     - Output raster layer ထဲရှိ row (တန်း) များအရေအတွက်
   * - **Total pixel count** **(Pixel အရေအတွက် စုစုပေါင်း)**
     - ``TOTAL_PIXEL_COUNT``
     - [integer]
     - Output raster layer ထဲရှိ pixel အရေအတွက် (count)

Python code
............

**Algorithm ID**: ``native:cellstackpercentile``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiscellstackpercentrankfromrasterlayer:

Cell stack percentrank from raster layer (Raster layer မှ cell အစုအထပ် ရာခိုင်နှုန်းအဆင့်)
-------------------------------------------------------------------------------------------

Input value raster တစ်ခုအပေါ်တွင် အခြေခံထားသော raster အစုအထပ်တစ်ခု (stack of raster) ၏ cell အလိုက်ရာခိုင်နှုန်းအဆင့်တန်ဖိုး (cell-wise percentrank value) ကို တွက်ချက်ပြီး ၎င်းတို့ကို output raster တစ်ခုထဲသို့ ရေးသွင်းသည်။

Cell ၏ တည်နေရာတစ်ခုချင်းစီ၌ value raster ၏ လက်ရှိတန်ဖိုးကို တစ်ခုနှင့်တစ်ခုထပ်ထားသော အစုအထပ် (stack) ထဲရှိ သက်ဆိုင်ရာတန်ဖိုးများနှင့် input raster များမှ sort လုပ်ထားသော cell တန်ဖိုးများ အကြားတွင် အဆင့်သတ်မှတ်ပါသည်။ Stack value distribution (အစုအထပ်တန်ဖိုးပြန့်နှံ့ခြင်း) ၏ အပြင်ဘက်တွင်ရှိသော တန်ဖိုးများအတွက်မူ cell တန်ဖိုးများအကြားတွင် တန်ဖိုးကို အဆင့်မသတ်မှတ်နိုင်သောကြောင့် algorithm သည် NoData ကို ပြန်ထုတ်ပေးမည်ဖြစ်သည်။ 

Percentile တွက်ချက်ခြင်းအတွက် နည်းလမ်း နှစ်ခုရှိပါသည်-

* Inclusive linear interpolation (PERCENTRANK.INC)
* Exclusive linear interpolation (PERCENTRANK.EXC)

Linear interpolation နည်းလမ်းသည် မတူညီသော တန်ဖိုးများအတွက် သိသာထင်ရှား (unique) သည့် ရာခိုင်နှုန်းအဆင့်(percent rank) ကို ရရှိစေပါသည်။ Interpolation နည်းလမ်းနှစ်ခုစလုံးသည် Microsoft Excel သို့မဟုတ် `LibreOffice <https://help.libreoffice.org/latest/en-US/text/scalc/01/04060184.html?DbPAR=CALC#bm_id3148807>`_  မှ အကောင်အထည်ဖော်ဆောင်ရွက်ထားသော ၎င်းတို့၏ သက်ဆိုင်ရာနည်းလမ်းများကို လိုက်နာပါသည်။ 

Output raster ၏ အကျယ်အဝန်းနယ် (extent) နှင့် ကြည်လင်ပြတ်သားမှု (resolution) ကို reference (ရည်ညွှန်း) raster တစ်ခုဖြင့် သတ်မှတ်ပါသည်။ Reference (ရည်ညွှန်း) raster layer ၏ cell အရွယ်အစားနှင့်မကိုက်ညီသော input raster layer များအား nearest neighbor resampling ကို အသုံးပြုပြီး cell အရွယ်အစားပြောင်းလဲပေး (resample) မည်ဖြစ်ပါသည်။ အကယ်၍ "Ignore NoData values" ဆိုသည့် parameter ကို သတ်မှတ်ထားခြင်းမရှိပါက မည့်သည့် input layer များထဲမဆိုရှိ NoData တန်ဖိုးများသည် NoData cell output တစ်ခုထဲတွင် ရရှိလိမ့်မည်ဖြစ်ပါသည်။ Output raster data အမျိုးအစားသည် အမြဲတမ်း ``Float32`` ဖြစ်မည်ဖြစ်ပါသည်။

.. figure:: img/percentrankfromrasterlayer.png
  :align: center

  Value raster layer cell များအား အဆင့်သတ်မှတ်ခြင်း။ ``NoData`` cell (မီးခိုးရောင်) များကို လျစ်လျူရှုပါသည်။

.. seealso:: :ref:`qgiscellstackpercentile` ၊ :ref:`qgiscellstackpercentrankfromvalue`


Parameters (သတ်မှတ်ချက်များ)
.............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 100 100 100 300
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layers** **(ထည့်သွင်းအသုံးပြုသော layer များ)**
     - ``INPUT`` 
     - [raster] [list]
     - အကဲဖြတ်သတ်မှတ် (evaluate) ရန် Raster layer များ။ အကယ်၍ data raster stack တွင် multiband (band များစွာပါဝင်သည့်) raster များကို အသုံးပြုထားပါက algorithm သည် raster များ၏ ပထမ band ပေါ်တွင် ခွဲခြမ်းစိတ်ဖြာမှု (analysis) ကို အမြဲတမ်း ဆောင်ရွက်မည်ဖြစ်ပါသည်။ 
   * - **Value raster layer**
     - ``INPUT_VALUE_RASTER``
     - [raster]
     - တစ်ခုနှင့်တစ်ခုထပ်ထားသော (overlaid) layer များအားလုံး၏ stack (အစုအထပ်) များအကြားတွင် တန်ဖိုးများကို အဆင့်သတ်မှတ်ရန် layer
   * - **Value raster band**
     - ``VALUE_RASTER_BAND``
     - [integer]

       Default: 1
     - နှိုင်းယှဉ်မည့် "value raster layer" ၏ band (လှိုင်းအလွှာ)
   * - **Method** **(နည်းလမ်း)**
     - ``METHOD`` 
     - [enumeration]

       Default: 0
     - Percentile တွက်ချက်ခြင်းအတွက် နည်းလမ်း-

       * 0 --- Inclusive linear interpolation (PERCENTRANK.INC)
       * 1 --- Exclusive linear interpolation (PERCENTRANK.EXC)
   * - **Ignore NoData values** **(NoData တန်ဖိုးများကို လျစ်လျူရှုပါ)**
     - ``IGNORE_NODATA`` 
     - [boolean]

       Default: True
     - အကယ်၍ အမှန်ခြစ်ဖြုတ်ထားပါက input layer များထဲရှိ မည်သည့် NoData cell များမဆိုသည် output raster ထဲတွင် NoData cell တစ်ခုကို ဖြစ်ပေါ်စေမည်ဖြစ်ပါသည်။ 
   * - **Reference layer** **(ရည်ညွှန်း layer)**
     - ``REFERENCE_LAYER``
     - [raster]
     - Output layer ဖန်တီးခြင်းအတွက် reference (ရည်ညွှန်း) layer (အကျယ်အဝန်းနယ် (extent)၊ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (CRS) ၊ pixel အတိုင်းအတာများ (dimensions))
   * - **Output layer** **(ရလာဒ် layer)**
     - ``OUTPUT`` 
     - [input ကဲ့သို့အတူတူဖြစ်ပါသည်။]

       Default: ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 50 50 50 100
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output no data value**
     - ``OUTPUT_NODATA_VALUE``
     - [number]

       Default: -9999.0
     - Output layer ထဲတွင် nodata အတွက် အသုံးပြုမည့်တန်ဖိုး

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 100 100 100 300

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output layer**
     - ``OUTPUT``
     - [raster]
     - ရလာဒ် (result) ပါဝင်သည့် output raster layer
   * - **CRS authority identifier**
     - ``CRS_AUTHID``
     - [string]
     - Output raster layer ၏ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (coordinate reference system)
   * - **Extent** **(အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [string]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent)
   * - **Width in pixels** **(Pixel ဖြင့် အကျယ်)**
     - ``WIDTH_IN_PIXELS``
     - [integer]
     - Output raster layer ထဲရှိ column (တိုင်) များအရေအတွက်
   * - **Height in pixels** **(Pixel ဖြင့် အမြင့်)**
     - ``HEIGHT_IN_PIXELS`` 
     - [integer]
     - Output raster layer ထဲရှိ row (တန်း) များအရေအတွက်
   * - **Total pixel count** **(Pixel အရေအတွက် စုစုပေါင်း)**
     - ``TOTAL_PIXEL_COUNT``
     - [integer]
     - Output raster layer ထဲရှိ pixel အရေအတွက် (count)

Python code
............

**Algorithm ID**: ``native:cellstackpercentrankfromrasterlayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiscellstatistics:

Cell statistics (Cell ဆိုင်ရာစာရင်းအင်းအချက်အလက်များ)
------------------------------------------------------

Input raster layer များအပေါ်အခြေခံပြီး cell တစ်ခုစီအလိုက်စာရင်းအင်းအချက်အလက်များ (per-cell statistics)ကို တွက်ချက်ပေးပြီး cell တစ်ခုချင်းစီအတွက် ရရှိလာသည့် စာရင်းအင်းအချက်အလက်များကို output raster တစ်ခုထဲသို့ ရေးသွင်းပါသည်။ Cell တည်နေရာတစ်ခုချင်းစီ၌ output တန်ဖိုးကို input raster များ၏ တစ်ခုနှင့်တစ်ခုထပ်ထားသော (overlaid) cell တန်ဖိုးများအားလုံး၏ function (လုပ်ဆောင်ချက်) တစ်ခုအဖြစ်သတ်မှတ်ပါသည်။

Default အားဖြင့် မည်သည့် input layers များမဆိုထဲရှိ NoData cell တစ်ခုသည် output raster ထဲတွင် NoData cell တစ်ခုကို ရရှိစေမည်ဖြစ်ပါသည်။ အကယ်၍ :guilabel:`Ignore NoData values` option ကို check (အမှန်ခြစ်) ပြုလုပ်ထားပါက စာရင်းအင်းဆိုင်ရာတွက်ချက်မှုတွင် NoData input များကို လျစ်လျူရှုထားမည်ဖြစ်သည်။ ၎င်းသည် cell များအားလုံး NoData ဖြစ်နေသည့် တည်နေရာများအတွက် NoData output(ရလာဒ်)ကို ရစေနိုင်မည်ဖြစ်သည်။

Output raster ဖန်တီးရာတွင် လက်ရှိရှိနေသည့် raster layer တစ်ခုကို reference (ရည်ညွှန်း) တစ်ခုအဖြစ် အသုံးပြုရန် :guilabel:`Reference layer` parameter မှ သတ်မှတ်ပေးပါသည်။ Output raster သည် ဤ layer ကဲ့သို့ပင် တူညီသည့် extent (အကျယ်အဝန်းနယ်)၊ CRS (ရည်ညွှန်းကိုဩဒိနိတ်စနစ်) နှင့် pixel dimensions(အတိုင်းအတာများ) ရှိမည်ဖြစ်ပါသည်။

**Calculation details** (တွက်ချက်မှုအသေးစိတ်)- Reference (ရည်ညွှန်း) raster layer ၏ cell အရွယ်အစားနှင့် မကိုက်ညီသော input raster layer များကို ``nearest neighbor resampling`` အသုံးပြုပြီး cell အရွယ်အစားပြောင်းလဲပေး (resample) မည်ဖြစ်သည်။ Output raster data အမျိုးအစားကို ``Mean`` (သမတ်ကိန်း) ၊ ``Standard deviation`` (စံတိမ်းချက်) နှင့် ``Variance`` (ကွဲလွဲချက်)(Data အမျိုးအစားသည် input float အမျိုးအစားပေါ်မူတည်ပြီး အမြဲတမ်း ``Float32`` သို့မဟုတ် ``Float64`` ဖြစ်ပါသည်) သို့မဟုတ် ``Count`` (အရေအတွက်) နှင့် ``Variety`` (မျိုးစုံမှု) (Data အမျိုးအစားသည် အမြဲ ``Int32`` ဖြစ်ပါသည်) function များကို အသုံးပြုသည့်အခါမှလွဲ၍ input dataset များတွင်ရှိသည့် အရှုပ်ထွေးဆုံး data အမျိုးအစား (most complex data type) အဖြစ်သို့ သတ်မှတ်မည်ဖြစ်ပါသည်။

- ``Count`` - Count statistic (စာရင်းအချက်အလက်) သည် လက်ရှိ cell တည်နေရာ၌ NoData တန်ဖိုးများမပါရှိသည့် cell အရေအတွက်များကို အမြဲတမ်း ရရှိစေမည်ဖြစ်ပါသည်။

- ``Median`` (တစ်ဝက်ကိန်း) - အကယ်၍ input layer အရေအတွက်သည် စုံကိန်းဖြစ်ပါက median (သမတ်ကိန်း) ကို အစဉ်လိုက်ထည့်သွင်းထားသော cell တန်ဖိုးများ (ordered cell input values) ၏ အလယ်တန်ဖိုးနှစ်ခု၏ arithmetic mean (တန်ဖိုးစုစုပေါင်းကို တည်ပြီး အရေအတွက်ဖြင့်စားသည့် ပျမ်းမျှတွက်ချက်မှု) အဖြစ်တွက်ချက်မည်ဖြစ်ပါသည်။

- ``Minority/Majority`` (အနည်းစု/အများစု) - အကယ်၍ သိသာထင်ရှားသည့် minority (အနည်းစု) သို့မဟုတ် majority(အများစု) ကို မတွေ့ရှိခဲ့ပါက ထည့်သွင်းထားသည့် cell တန်ဖိုးများ (input cell values) အားလုံးတူညီသည်မှလွဲ၍ ရလာဒ်သည် NoData ဖြစ်မည်ဖြစ်ပါသည်။


.. figure:: img/cell_statistics_all_stats.png
  :align: center

  စာရင်းအင်းဆိုင်ရာ function အားလုံး၏ဥပမာများ။ ``NoData`` cell (မီးခိုရောင်) များကို ထည့်သွင်းစဉ်းစားပါသည်။


Parameters (သတ်မှတ်ချက်များ)
.............................

Basic parameters (အခြေခံသတ်မှတ်ချက်များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 100 100 100 300

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layers** **(ထည့်သွင်းအသုံးပြုသော layer များ)**
     - ``INPUT``
     - [raster] [list]
     - Input raster layer များ 
   * - **Statistic** **(စာရင်းအင်းအချက်အလက်)**
     - ``STATISTIC``
     - [enumeration]

       Default : 0
     - ရရှိနိုင်သည့် စာရင်းအင်းအချက်အလက်များ။ ရွေးချယ်စရာများမှာ-

       * 0 --- Sum (ပေါင်းခြင်း)
       * 1 --- Count (ရေတွက်ခြင်း)
       * 2 --- Mean (သမတ်ကိန်း)
       * 3 --- Median (တစ်ဝက်ကိန်း)
       * 4 --- Standard deviation (စံတိမ်းချက်)
       * 5 --- Variance (ကွဲလွဲချက်)
       * 6 --- Minimum (အနည်းဆုံးတန်ဖိုး)
       * 7 --- Maximum (အများဆုံးတန်ဖိုး)
       * 8 --- Minority (အနည်းစုအဖြစ်ဆုံး တန်ဖိုး- least common value)
       * 9 --- Majority (အများစုအဖြစ်ဆုံး တန်ဖိုး- most common value)
       * 10 --- Range (အပိုင်းအခြားပမာဏ) (max - min) (အများဆုံး - အနည်းဆုံး)
       * 11 --- Variety (unique value count) (သိသာထင်ရှားသည့် တန်ဖိုးအရေအတွက်)
   * - **Ignore NoData values** **(NoData တန်ဖိုးများကို လျစ်လျူရှုပါ)**
     - ``IGNORE_NODATA``
     - [boolean]

       Default: True
     - Cell stack များအားလုံးအတွက်လည်း NoData occurrence (ဖြစ်ပွားမှု) ကို လျစ်လျူရှုပြီး စာရင်းအင်းအချက်အလက်များကို တွက်ချက်ပါသည်။ 
   * - **Reference layer** **(ရည်ညွှန်း layer)**
     - ``REFERENCE_LAYER``
     - [raster]
     - Output layer ဖန်တီးခြင်းအတွက် reference (ရည်ညွှန်း) layer (အကျယ်အဝန်းနယ် (extent)၊ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (CRS) ၊ pixel အတိုင်းအတာများ (dimensions))
   * - **Output layer** **(ရလာဒ် layer)**
     - ``OUTPUT`` 
     - [input ကဲ့သို့အတူတူဖြစ်ပါသည်။]

       Default: ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 50 50 50 100
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output no data value**
       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုအပ်ပါ)
     - ``OUTPUT_NO_DATA_VALUE``
     - [number]

       Default: -9999.0
     - Output layer ထဲတွင် nodata အတွက် အသုံးပြုမည့်တန်ဖိုး

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 100 100 100 300

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **CRS authority identifier**
     - ``CRS_AUTHID``
     - [string]
     - Output raster layer ၏ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (coordinate reference system)
   * - **Extent** **(အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [string]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent)
   * - **Height in pixels** **(Pixel ဖြင့် အမြင့်)**
     - ``HEIGHT_IN_PIXELS`` 
     - [integer]
     - Output raster layer ထဲရှိ row (တန်း) များအရေအတွက်     
   * - **Output layer**
     - ``OUTPUT``
     - [raster]
     - ရလာဒ် (result) ပါဝင်သည့် output raster layer
   * - **Total pixel count** **(Pixel အရေအတွက် စုစုပေါင်း)**
     - ``TOTAL_PIXEL_COUNT``
     - [integer]
     - Output raster layer ထဲရှိ pixel အရေအတွက် (count)     
   * - **Width in pixels** **(Pixel ဖြင့် အကျယ်)**
     - ``WIDTH_IN_PIXELS``
     - [integer]
     - Output raster layer ထဲရှိ column (တိုင်) များအရေအတွက်

Python code
............

**Algorithm ID**: ``native:cellstatistics``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisequaltofrequency:

Equal to frequency (ကြိမ်နှုန်းနှင့်အညီ)
-----------------------------------------

ထည့်သွင်းထားသည့် raster အစုအထပ်တစ်ခု (input stack of rasters) ၏ တန်ဖိုးများသည် value layer တစ်ခု၏ တန်ဖိုးနှင့်တူညီသော Frequency (ကြိမ်နှုန်း) (အကြိမ်အရေအတွက်) ကို cell တစ်ခုချင်းစီအလိုက် အကဲဖြတ်ပေးပါသည်။ Output raster ၏ အကျယ်အဝန်းနယ် (extent) နှင့် ကြည်လင်ပြတ်သားမှု (resolution) တို့ကို input raster layer ဖြင့် သတ်မှတ်ပြီး အမြဲတမ်း ``Int32`` အမျိုးအစားဖြစ်ပါသည်။

အကယ်၍ multiband raster (Band များစွာပါရှိသည့်) များကို data raster stack ထဲတွင် အသုံးပြုထားပါက algorithm သည် အမြဲတမ်း raster များ၏ ပထမ band အပေါ်တွင် ခွဲခြမ်းစိတ်ဖြာမှု (analysis)ကို ဆောင်ရွက်မည်ဖြစ်ပါသည် - ခွဲခြမ်းစိတ်ဖြာမှုတွင် အခြားသော band များကို အသုံးပြုရန်အတွက် GDAL ကို အသုံးပြုပါ။ Output NoData တန်ဖိုးကို ကိုယ်တိုင် သတ်မှတ်ပေးနိုင်ပါသည်။ 


.. figure:: img/equaltofrequency.png
  :align: center

  Output raster ထဲရှိ cell တစ်ခုချင်းစီအတွက် တန်ဖိုးသည် raster များ၏ စာရင်းထဲရှိ သက်ဆိုင်ရာ cell များသည် value raster များနှင့်အတူတူဖြစ်သည့် အကြိမ်အရေအတွက်ကို ကိုယ်စားပြုဖော်ပြပါသည်။ ``NoData`` cell (မီးခိုးရောင်) များကို ထည့်သွင်းစဉ်းစားပါသည်။

.. seealso:: :ref:`qgisgreaterthanfrequency` ၊ :ref:`qgislessthanfrequency`

.. **frequencyparams**
.. FYI, the next params description is shared with Greater/Less than frequency algorithms


Parameters (သတ်မှတ်ချက်များ)
.............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 100 100 100 300
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input value raster** **(ထည့်သွင်းအသုံးပြုသော value raster)** 
     - ``INPUT_VALUE_RASTER``
     - [raster]
     - Input value layer သည် sample layer များအတွက် reference (ရည်ညွှန်း) layer အဖြစ်ဆောင်ရွက်မည်ဖြစ်ပါသည်။ 
   * - **Value raster band** 
     - ``INPUT_VALUE_RASTER_BAND``
     - [raster band]

       Default: Raster layer ၏ ပထမ band
     - Sample အဖြစ် အသုံးပြုလိုသည့် band ကို ရွေးချယ်ပါ။ 
   * - **Input raster layers** **(ထည့်သွင်းအသုံးပြုသော raster layer များ)**
     - ``INPUT_RASTERS``
     - [raster] [list]
     - အကဲဖြတ်သတ်မှတ် (evaluate) ရန် Raster layer များ။ အကယ်၍ data raster stack တွင် multiband (band များစွာပါဝင်သည့်) raster များကို အသုံးပြုထားပါက algorithm သည် raster များ၏ ပထမ band ပေါ်တွင် ခွဲခြမ်းစိတ်ဖြာမှု (analysis) ကို အမြဲတမ်း ဆောင်ရွက်မည်ဖြစ်ပါသည်။ 
   * - **Ignore NoData values** **(NoData တန်ဖိုးများကို လျစ်လျူရှုပါ)**
     - ``IGNORE_NODATA`` 
     - [boolean]

       Default: False
     - အကယ်၍ အမှန်ခြစ်ဖြုတ်ထားပါက value raster သို့မဟုတ် data layer stack ထဲရှိ မည်သည့် NoData cell များမဆိုသည် output raster ထဲတွင် NoData cell တစ်ခုကို ဖြစ်ပေါ်စေမည်ဖြစ်ပါသည်။ 
   * - **Output layer** **(ရလာဒ် layer)**
     - ``OUTPUT`` 
     - [input ကဲ့သို့အတူတူဖြစ်ပါသည်။]

       Default: ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 50 50 50 100
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output no data value**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုအပ်ပါ)
     - ``OUTPUT_NO_DATA_VALUE``
     - [number]

       Default: -9999.0
     - Output layer ထဲရှိ nodata အတွက် အသုံးပြုမည့် တန်ဖိုး

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 100 100 100 300

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output layer**
     - ``OUTPUT``
     - [raster]
     - ရလာဒ် (result) ပါဝင်သည့် output raster layer
   * - **CRS authority identifier**
     - ``CRS_AUTHID``
     - [string]
     - Output raster layer ၏ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (coordinate reference system)
   * - **Extent** **(အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [string]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent)
   * - **Count of cells with equal value occurrences** **(တူညီသော တန်ဖိုးဖြစ်ပွားမှုရှိသည့် cell များအရေအတွက်)** 
     - ``FOUND_LOCATIONS_COUNT``
     - [number]
     -
   * - **Height in pixels** **(Pixel ဖြင့် အမြင့်)**
     - ``HEIGHT_IN_PIXELS`` 
     - [integer]
     - Output raster layer ထဲရှိ row (တန်း) များအရေအတွက်
   * - **Total pixel count** **(Pixel အရေအတွက် စုစုပေါင်း)**
     - ``TOTAL_PIXEL_COUNT``
     - [integer]
     - Output raster layer ထဲရှိ pixel အရေအတွက် (count)
   * - **Mean frequency at valid cell locations** **(ကိုက်ညီသော cell တည်နေရာများရှိ ပျမ်းမျှကြိမ်နှုန်း)** 
     - ``MEAN_FREQUENCY_PER_LOCATION`` 
     - [number]
     -
   * - **Count of value occurrences** **(တန်ဖိုးဖြစ်ပွားမှုအရေအတွက်)** 
     - ``OCCURRENCE_COUNT``
     - [number]
     -
   * - **Width in pixels** **(Pixel ဖြင့် အကျယ်)**
     - ``WIDTH_IN_PIXELS``
     - [integer]
     - Output raster layer ထဲရှိ column (တိုင်) များအရေအတွက်

.. **endfrequencyparams**


Python code
............

**Algorithm ID**: ``native:equaltofrequency``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisfuzzifyrastergaussianmembership:

Fuzzify raster (gaussian membership) 
--------------------------------------

Gaussian membership function တစ်ခုကို အသုံးပြုပြီး pixel တစ်ခုချင်းစီသို့ membership တန်ဖိုး တစ်ခုသတ်မှတ်ခြင်းဖြင့် input raster တစ်ခုကို fuzzified raster အဖြစ်သို့ ပြောင်းလဲပေးပါသည်။ Membership တန်ဖိုးသည် 0 မှ 1 အပိုင်းအခြားပမာဏအတွင်းဖြစ်ပါသည်။ Fuzzified raster (0 နှင့် 1 အကြားရှိ membership တန်ဖိုးသို့ ပြောင်းလဲထားသည့် raster) တွင် 0 ဟူသည့် တန်ဖိုးသည် သတ်မှတ်ထားသော fuzzy set ၏ membership မဟုတ်ဟု ဆိုလိုပြီး 1 ဟူသည့် တန်ဖိုးသည် full membership ကို ညွှန်းဆိုပါသည်။ Gaussian membership function ကို |gaussian_formula| အဖြစ် သတ်မှတ်ပါသည်။ *f1* သည် spread (Spread သည် fuzzy membership တန်ဖိုးများကို 1 မှ 0 သို့ မည်မျှလျှင်မြန်စွာ ကျဆင်းသွားသည်ကို ဆုံးဖြတ်သည်) ဖြစ်ပြီး *f2* သည် midpoint (အလယ်မှတ်) ဖြစ်ပါသည်။ 

.. figure:: img/gaussianimage.png
  :align: center

  Fuzzify raster ဥပမာ။ Input raster ရင်းမြစ် - Land Tirol -
  data.tirol.gv.at.

.. seealso:: :ref:`qgisfuzzifyrasterlargemembership` ၊ :ref:`qgisfuzzifyrasterlinearmembership` ၊ :ref:`qgisfuzzifyrasternearmembership` ၊ :ref:`qgisfuzzifyrasterpowermembership` ၊  :ref:`qgisfuzzifyrastersmallmembership`


Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 100 100 100 300
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input Raster** **(ထည့်သွင်းအသုံးပြုသော raster)**
     - ``INPUT``
     - [raster]
     - Input raster layer များ
   * - **Band number** **(Band နံပါတ်)**
     - ``BAND``
     - [raster band]

       Default: Raster layer ၏ ပထမ Band
     - Raster သည် multiband (Band များစွာ) ဖြစ်ပါက fuzzify ပြုလုပ်လိုသည့် band ကို ရွေးချယ်ပါ။ 
       
   * - **Function midpoint**
     - ``FUZZYMIDPOINT``
     - [number]

       Default: 10
     - Gaussian function ၏ Midpoint (အလယ်မှတ်)
   * - **Function spread**
     - ``FUZZYSPREAD``
     - [number]

       Default: 0.01
     - Gaussian function ၏ Spread
   * - **Fuzzified raster**
     - ``OUTPUT``
     - [input ကဲ့သို့အတူတူဖြစ်ပါသည်။]

       Default : ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက် (Specification) ။ အောက်ပါထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**


Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 100 100 100 300

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Fuzzified raster**
     - ``OUTPUT``
     - [input ကဲ့သို့အတူတူဖြစ်ပါသည်။]
     - ရလာဒ်ပါဝင်သော output raster layer
   * - **CRS authority identifier**
     - ``CRS_AUTHID``
     - [crs]
     - Output raster layer ၏ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (coordinate reference system)
   * - **Extent** **(အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [string]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent)
   * - **Width in pixels** **(Pixel ဖြင့် အလျား)**
     - ``WIDTH_IN_PIXELS``
     - [integer]
     - Output raster layer ထဲရှိ column (တိုင်) များအရေအတွက်
   * - **Height in pixels** **(Pixel ဖြင့် အမြင့်)**
     - ``HEIGHT_IN_PIXELS`` 
     - [integer]
     - Output raster layer ထဲရှိ row (တန်း) များအရေအတွက်
   * - **Total pixel count** **(Pixel အရေအတွက် စုစုပေါင်း)**
     - ``TOTAL_PIXEL_COUNT``
     - [integer]
     - Output raster layer ထဲရှိ pixel အရေအတွက် (count)


Python code
............

**Algorithm ID**: ``native:fuzzifyrastergaussianmembership``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisfuzzifyrasterlargemembership:

Fuzzify raster (large membership)
----------------------------------

Large membership function တစ်ခုကို အသုံးပြုပြီး pixel တစ်ခုချင်းစီသို့ membership တန်ဖိုးတစ်ခုသတ်မှတ်ခြင်းဖြင့် input raster တစ်ခုကို fuzzified raster အဖြစ်သို့ ပြောင်းလဲပေးပါသည်။ Membership တန်ဖိုးသည် 0 မှ 1 အပိုင်းအခြားပမာဏအတွင်းဖြစ်ပါသည်။ Fuzzified raster (0 နှင့် 1 အကြားရှိ membership တန်ဖိုးသို့ ပြောင်းလဲထားသည့် raster) တွင် 0 ဟူသည့် တန်ဖိုးသည် သတ်မှတ်ထားသော fuzzy set ၏ membership မဟုတ်ဟု ဆိုလိုပြီး 1 ဟူသည့် တန်ဖိုးသည် full membership ကို ညွှန်းဆိုပါသည်။ Large membership function ကို |fuzzy_large_formula| အဖြစ် သတ်မှတ်ပါသည်။ *f1* သည် spread (Spread သည် fuzzy membership တန်ဖိုးများကို 1 မှ 0 မှ မည်မျှလျင်မြန်စွာ ကျဆင်းသွားသည်ကို ဆုံးဖြတ်သည်) ဖြစ်ပြီး *f2* သည် midpoint(အလယ်မှတ်) ဖြစ်ပါသည်။ 

.. seealso:: :ref:`qgisfuzzifyrastergaussianmembership` ၊ :ref:`qgisfuzzifyrasterlinearmembership` ၊ :ref:`qgisfuzzifyrasternearmembership` ၊ :ref:`qgisfuzzifyrasterpowermembership` ၊ :ref:`qgisfuzzifyrastersmallmembership`

Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 100 100 100 300

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input Raster** **(ထည့်သွင်းအသုံးပြုသော raster)**
     - ``INPUT``
     - [raster]
     - Input raster layer များ
   * - **Band number** **(Band နံပါတ်)**
     - ``BAND``
     - [raster band]

       Default: Raster layer ၏ ပထမ Band
     - Raster သည် multiband (Band များစွာ) ဖြစ်ပါက fuzzify ပြုလုပ်လိုသည့် band ကို ရွေးချယ်ပါ။ 
   * - **Function midpoint**
     - ``FUZZYMIDPOINT``
     - [number]

       Default : 50
     - Large function ၏ Midpoint (အလယ်မှတ်)
   * - **Function spread**
     - ``FUZZYSPREAD``
     - [number]

       Default : 5
     - Large function ၏ Spread
   * - **Fuzzified raster**
     - ``OUTPUT``
     - [input ကဲ့သို့အတူတူဖြစ်ပါသည်။]

       Default : ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 100 100 100 300

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Fuzzified raster**
     - ``OUTPUT``
     - [input ကဲ့သို့အတူတူဖြစ်ပါသည်။]
     - ရလာဒ်ပါဝင်သော output raster layer
   * - **CRS authority identifier**
     - ``CRS_AUTHID``
     - [crs]
     - Output raster layer ၏ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (coordinate reference system)
   * - **Extent** **(အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [string]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent)
   * - **Width in pixels** **(Pixel ဖြင့် အကျယ်)**
     - ``WIDTH_IN_PIXELS``
     - [integer]
     - Output raster layer ထဲရှိ column (တိုင်) များအရေအတွက်
   * - **Height in pixels** **(Pixel ဖြင့် အမြင့်)**
     - ``HEIGHT_IN_PIXELS`` 
     - [integer]
     - Output raster layer ထဲရှိ row (တန်း) များအရေအတွက်
   * - **Total pixel count** **(Pixel အရေအတွက် စုစုပေါင်း)**
     - ``TOTAL_PIXEL_COUNT``
     - [integer]
     - Output raster layer ထဲရှိ pixel အရေအတွက် (count)

Python code
............

**Algorithm ID**: ``native:fuzzifyrasterlargemembership``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisfuzzifyrasterlinearmembership:

Fuzzify raster (linear membership)
-----------------------------------

Linear membership function တစ်ခုကို အသုံးပြုပြီး pixel တစ်ခုချင်းစီသို့ membership တန်ဖိုးတစ်ခုသတ်မှတ်ခြင်းဖြင့် input raster တစ်ခုကို fuzzified raster အဖြစ်သို့ ပြောင်းလဲပေးပါသည်။ Membership တန်ဖိုးသည် 0 မှ 1 အပိုင်းအခြားပမာဏအတွင်းဖြစ်ပါသည်။ Fuzzified raster (0 နှင့် 1 အကြားရှိ membership value သို့ ပြောင်းလဲထားသည့် raster) တွင် 0 ဟူသည့် တန်ဖိုးသည် သတ်မှတ်ထားသော fuzzy set ၏ membership မဟုတ်ဟု ဆိုလိုပြီး 1 ဟူသည့် တန်ဖိုးသည် full membership ကို ညွှန်းဆိုပါသည်။ Linear function ကို |fuzzy_linear_formula| အဖြစ် သတ်မှတ်ပါသည်။ *a* သည် low bound (ကန့်သတ်ချက်အနိမ့်) ဖြစ်ပြီး *b* သည် high bound (ကန့်သတ်ချက်အမြင့်) ဖြစ်ပါသည်။ ဤပုံသေနည်းသည် low နှင့် high bound များအကြားရှိ pixel တန်ဖိုးများအတွက် linear transformation တစ်ခုကို အသုံးပြုပြီး membership တန်ဖိုးများကို သတ်မှတ်ပါသည်။  Low bound အောက်ငယ်သော pixel တန်ဖိုးများကို 0 membership အဖြစ်သတ်မှတ်ပြီး high bound ထက်ကြီးသော pixel တန်ဖိုးများကို 1 membership အဖြစ်သတ်မှတ်ပါသည်။ 

.. seealso:: :ref:`qgisfuzzifyrastergaussianmembership` ၊
  :ref:`qgisfuzzifyrasterlargemembership` ၊
  :ref:`qgisfuzzifyrasternearmembership` ၊
  :ref:`qgisfuzzifyrasterpowermembership` ၊
  :ref:`qgisfuzzifyrastersmallmembership`


Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 100 100 100 300

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input raster** **(ထည့်သွင်းအသုံးပြုသော raster)**
     - ``INPUT``
     - [raster]
     - Input raster layer များ
   * - **Band number** **(Band နံပါတ်)**
     - ``BAND``
     - [raster band]

       Default: raster layer ၏ ပထမ Band
     - Raster သည် multiband (Band များစွာ) ဖြစ်ပါက fuzzify ပြုလုပ်လိုသည့် band ကို ရွေးချယ်ပါ။ 
   * - **Low fuzzy membership bound**
     - ``FUZZYLOWBOUND``
     - [number]

       Default: 0
     - Linear function ၏ Low bound
   * - **High fuzzy membership bound**
     - ``FUZZYHIGHBOUND``
     - [number]

       Default: 1
     - Linear function ၏ High bound
   * - **Fuzzified raster**
     - ``OUTPUT``
     - [input ကဲ့သို့အတူတူဖြစ်ပါသည်။]

       Default : ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက် (Specification) ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**


Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 100 100 100 300

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Fuzzified raster**
     - ``OUTPUT``
     - [input ကဲ့သို့အတူတူဖြစ်ပါသည်။]
     - ရလာဒ်ပါဝင်သော output raster layer
   * - **CRS authority identifier**
     - ``CRS_AUTHID``
     - [crs]
     - Output raster layer ၏ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (coordinate reference system)
   * - **Extent** **(အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [string]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent)
   * - **Width in pixels** **(Pixel ဖြင့် အကျယ်)**
     - ``WIDTH_IN_PIXELS``
     - [integer]
     - Output raster layer ထဲရှိ column (တိုင်) များအရေအတွက်
   * - **Height in pixels** **(Pixel ဖြင့် အမြင့်)**
     - ``HEIGHT_IN_PIXELS`` 
     - [integer]
     - Output raster layer ထဲရှိ row (တန်း) များအရေအတွက်
   * - **Total pixel count** **(Pixel အရေအတွက် စုစုပေါင်း)**
     - ``TOTAL_PIXEL_COUNT``
     - [integer]
     - Output raster layer ထဲရှိ pixel အရေအတွက် (count)


Python code
............

**Algorithm ID**: ``native:fuzzifyrasterlinearmembership``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisfuzzifyrasternearmembership:

Fuzzify raster (near membership)
---------------------------------

Near membership function တစ်ခုကို အသုံးပြုပြီး pixel တစ်ခုချင်းစီသို့ membership တန်ဖိုးတစ်ခုသတ်မှတ်ခြင်းဖြင့် input raster တစ်ခုကို fuzzified raster အဖြစ်သို့ ပြောင်းလဲပေးပါသည်။ Membership တန်ဖိုးသည် 0 မှ 1 အပိုင်းအခြားပမာဏအတွင်းဖြစ်ပါသည်။ Fuzzified raster (0 နှင့် 1 အကြားရှိ membership တန်ဖိုးသို့ ပြောင်းလဲထားသည့် raster) တွင် 0 ဟူသည့် တန်ဖိုးသည် သတ်မှတ်ထားသော fuzzy set ၏ membership မဟုတ်ဟု ဆိုလိုပြီး 1 ဟူသည့် တန်ဖိုးသည် full membership ကို ညွှန်းဆိုပါသည်။ Near membership function ကို |near_formula| အဖြစ် သတ်မှတ်ပါသည်။ *f1* သည် spread (Spread သည် fuzzy membership တန်ဖိုးများကို 1 မှ 0 မှ မည်မျှလျင်မြန်စွာ ကျဆင်းသွားသည်ကို ဆုံးဖြတ်သည်) ဖြစ်ပြီး *f2* သည် midpoint(အလယ်မှတ်) ဖြစ်ပါသည်။ 

.. seealso:: :ref:`qgisfuzzifyrastergaussianmembership` ၊
  :ref:`qgisfuzzifyrasterlargemembership` ၊
  :ref:`qgisfuzzifyrasterlinearmembership` ၊
  :ref:`qgisfuzzifyrasterpowermembership` ၊
  :ref:`qgisfuzzifyrastersmallmembership`


Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 100 100 100 300

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input Raster** **(ထည့်သွင်းအသုံးပြုသော raster)**
     - ``INPUT``
     - [raster]
     - Input raster layer များ
   * - **Band number** **(Band နံပါတ်)**
     - ``BAND``
     - [raster band]

       Default: Raster layer ၏ ပထမ Band
     - Raster သည် multiband (Band များစွာ) ဖြစ်ပါက fuzzify ပြုလုပ်လိုသည့် band ကို ရွေးချယ်ပါ။ 
   * - **Function midpoint**
     - ``FUZZYMIDPOINT``
     - [number]

       Default : 50
     - Near function ၏ Midpoint (အလယ်မှတ်)
   * - **Function spread**
     - ``FUZZYSPREAD``
     - [number]

       Default : 0.01
     - Near function ၏ Spread
   * - **Fuzzified raster**
     - ``OUTPUT``
     - [input ကဲ့သို့အတူတူဖြစ်ပါသည်။]

       Default : ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 100 100 100 300

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Fuzzified raster**
     - ``OUTPUT``
     - [input ကဲ့သို့အတူတူဖြစ်ပါသည်။]
     - ရလာဒ်ပါဝင်သော output raster layer
   * - **CRS authority identifier**
     - ``CRS_AUTHID``
     - [crs]
     - Output raster layer ၏ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (coordinate reference system)
   * - **Extent** **(အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [string]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent)
   * - **Width in pixels** **(Pixel ဖြင့် အကျယ်)**
     - ``WIDTH_IN_PIXELS``
     - [integer]
     - Output raster layer ထဲရှိ column (တိုင်) များအရေအတွက်
   * - **Height in pixels** **(Pixel ဖြင့် အမြင့်)**
     - ``HEIGHT_IN_PIXELS`` 
     - [integer]
     - Output raster layer ထဲရှိ row (တန်း) များအရေအတွက်
   * - **Total pixel count** **(Pixel အရေအတွက် စုစုပေါင်း)**
     - ``TOTAL_PIXEL_COUNT``
     - [integer]
     - Output raster layer ထဲရှိ pixel အရေအတွက် (count)

Python code
............

**Algorithm ID**: ``native:fuzzifyrasternearmembership``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisfuzzifyrasterpowermembership:

Fuzzify raster (power membership)
----------------------------------

Power membership function တစ်ခုကို အသုံးပြုပြီး pixel တစ်ခုချင်းစီသို့ membership တန်ဖိုးတစ်ခုသတ်မှတ်ခြင်းဖြင့် input raster တစ်ခုကို fuzzified raster အဖြစ်သို့ ပြောင်းလဲပေးပါသည်။ Membership တန်ဖိုးသည် 0 မှ 1 အပိုင်းအခြားပမာဏအတွင်းဖြစ်ပါသည်။ Fuzzified raster (0 နှင့် 1 အကြားရှိ membership တန်ဖိုးသို့ ပြောင်းလဲထားသည့် raster) တွင် 0 ဟူသည့် တန်ဖိုးသည် သတ်မှတ်ထားသော fuzzy set ၏ membership မဟုတ်ဟု ဆိုလိုပြီး 1 ဟူသည့် တန်ဖိုးသည် full membership ကို ညွှန်းဆိုပါသည်။ Power function ကို |power_formula| အဖြစ် သတ်မှတ်ပါသည်။ *a* သည် low bound (ကန့်သတ်ချက်အနိမ့်) ဖြစ်၍ *b* သည် high bound (ကန့်သတ်ချက်အမြင့်) ဖြစ်ပြီး *f1* သည် exponent (ထပ်ကိန်း) ဖြစ်ပါသည်။ ဤပုံသေနည်းသည် low နှင့် high bound များအကြားရှိ pixel တန်ဖိုးများအတွက် power transformation ကို အသုံးပြုပြီး membership တန်ဖိုးများကို သတ်မှတ်ပါသည်။ Low bound အောက်ငယ်သော pixel တန်ဖိုးများကို 0 membership အဖြစ်သတ်မှတ်ပြီး high bound ထက်ကြီးသော pixel တန်ဖိုးများကို 1 membership အဖြစ်သတ်မှတ်ပါသည်။ 

.. seealso:: :ref:`qgisfuzzifyrastergaussianmembership` ၊ :ref:`qgisfuzzifyrasterlargemembership` ၊
  :ref:`qgisfuzzifyrasterlinearmembership` ၊ :ref:`qgisfuzzifyrasternearmembership` ၊
  :ref:`qgisfuzzifyrastersmallmembership`


Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 100 100 100 200

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input Raster** **(ထည့်သွင်းအသုံးပြုသော raster)**
     - ``INPUT``
     - [raster]
     - Input raster layer များ
   * - **Band number** **(Band နံပါတ်)**
     - ``BAND``
     - [raster band]

       Default: Raster layer ၏ ပထမ Band
     - Raster သည် multiband (Band များစွာ) ဖြစ်ပါက fuzzify ပြုလုပ်လိုသည့် band ကို ရွေးချယ်ပါ။ 
   * - **Low fuzzy membership bound**
     - ``FUZZYLOWBOUND``
     - [number]

       Default: 0
     - Power function ၏ Low bound 
   * - **High fuzzy membership bound**
     - ``FUZZYHIGHBOUND``
     - [number]

       Default: 1
     - Power function ၏ High bound 
   * - **High fuzzy membership bound**
     - ``FUZZYEXPONENT``
     - [number]

       Default: 2
     - Power function ၏ Exponent (ထပ်ကိန်း-ကြီးမားသည့်ကိန်းဂဏန်းများကို ပါဝါများဖြင့်ဖော်ပြခြင်း)
   * - **Fuzzified raster**
     - ``OUTPUT``
     - [input ကဲ့သို့အတူတူဖြစ်ပါသည်။]

       Default : ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက် (Specification) ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Fuzzified raster**
     - ``OUTPUT``
     - [input ကဲ့သို့အတူတူဖြစ်ပါသည်။]
     - ရလာဒ်ပါဝင်သော output raster layer
   * - **CRS authority identifier**
     - ``CRS_AUTHID``
     - [crs]
     - Output raster layer ၏ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (coordinate reference system)
   * - **Extent** **(အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [string]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent)
   * - **Width in pixels** **(Pixel ဖြင့် အကျယ်)**
     - ``WIDTH_IN_PIXELS``
     - [integer]
     - Output raster layer ထဲရှိ column (တိုင်) များအရေအတွက်
   * - **Height in pixels** **(Pixel ဖြင့် အမြင့်)**
     - ``HEIGHT_IN_PIXELS`` 
     - [integer]
     - Output raster layer ထဲရှိ row (တန်း) များအရေအတွက်
   * - **Total pixel count** **(Pixel အရေအတွက် စုစုပေါင်း)**
     - ``TOTAL_PIXEL_COUNT``
     - [integer]
     - Output raster layer ထဲရှိ pixel အရေအတွက် (count)


Python code
............

**Algorithm ID**: ``native:fuzzifyrasterpowermembership``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisfuzzifyrastersmallmembership:

Fuzzify raster (small membership)
----------------------------------

Small membership function တစ်ခုကို အသုံးပြုပြီး pixel တစ်ခုချင်းစီသို့ membership တန်ဖိုးတစ်ခုသတ်မှတ်ခြင်းဖြင့် input raster တစ်ခုကို fuzzified raster အဖြစ်သို့ ပြောင်းလဲပေးပါသည်။ Membership တန်ဖိုးသည် 0 မှ 1 အပိုင်းအခြားပမာဏအတွင်းဖြစ်ပါသည်။ Fuzzified raster (0 နှင့် 1 အကြားရှိ membership တန်ဖိုးသို့ ပြောင်းလဲထားသည့် raster) တွင် 0 ဟူသည့် တန်ဖိုးသည် သတ်မှတ်ထားသော fuzzy set ၏ membership မဟုတ်ဟု ဆိုလိုပြီး 1 ဟူသည့် တန်ဖိုးသည် full membership ကို ညွှန်းဆိုပါသည်။ Small membership function ကို |small_formula| အဖြစ် သတ်မှတ်ပါသည်။ *f1* သည် spread (Spread သည် fuzzy membership တန်ဖိုးများကို 1 မှ 0 မှ မည်မျှလျင်မြန်စွာ ကျဆင်းသွားသည်ကို ဆုံးဖြတ်သည်) ဖြစ်ပြီး *f2* သည် midpoint(အလယ်မှတ်) ဖြစ်ပါသည်။ 

.. seealso:: :ref:`qgisfuzzifyrastergaussianmembership` ၊ :ref:`qgisfuzzifyrasterlargemembership` ၊ :ref:`qgisfuzzifyrasterlinearmembership` ၊ :ref:`qgisfuzzifyrasternearmembership` ၊ :ref:`qgisfuzzifyrasterpowermembership`


Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input Raster** **(ထည့်သွင်းအသုံးပြုသော raster)**
     - ``INPUT``
     - [raster]
     - Input raster layer များ
   * - **Band number** **(Band နံပါတ်)**
     - ``BAND``
     - [raster band]

       Default: Raster layer ၏ ပထမ Band
     - Raster သည် multiband (Band များစွာ) ဖြစ်ပါက fuzzify ပြုလုပ်လိုသည့် band ကို ရွေးချယ်ပါ။ 
   * - **Function midpoint**
     - ``FUZZYMIDPOINT``
     - [number]

       Default : 50
     - Small function ၏ Midpoint (အလယ်မှတ်)
   * - **Function spread**
     - ``FUZZYSPREAD``
     - [number]

       Default : 5
     - Small function ၏ Spread
   * - **Fuzzified raster**
     - ``OUTPUT``
     - [input ကဲ့သို့အတူတူဖြစ်ပါသည်။]

       Default : ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Fuzzified raster**
     - ``OUTPUT``
     - [input ကဲ့သို့အတူတူဖြစ်ပါသည်။]
     - ရလာဒ်ပါဝင်သော output raster layer
   * - **CRS authority identifier**
     - ``CRS_AUTHID``
     - [crs]
     - Output raster layer ၏ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (coordinate reference system)
   * - **Extent** **(အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [string]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent)
   * - **Width in pixels** **(Pixel ဖြင့် အကျယ်)**
     - ``WIDTH_IN_PIXELS``
     - [integer]
     - Output raster layer ထဲရှိ column (တိုင်) များအရေအတွက်
   * - **Height in pixels** **(Pixel ဖြင့် အမြင့်)**
     - ``HEIGHT_IN_PIXELS`` 
     - [integer]
     - Output raster layer ထဲရှိ row (တန်း) များအရေအတွက်
   * - **Total pixel count** **(Pixel အရေအတွက် စုစုပေါင်း)**
     - ``TOTAL_PIXEL_COUNT``
     - [integer]
     - Output raster layer ထဲရှိ pixel အရေအတွက် (count)

Python code
............

**Algorithm ID**: ``native:fuzzifyrastersmallmembership``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisgreaterthanfrequency:

Greater than frequency (ကြိမ်နှုန်းထက် ပိုကြီးသော)
---------------------------------------------------

ထည့်သွင်းထားသည့် raster အစုအထပ်တစ်ခု (input stack of rasters) ၏ တန်ဖိုးများသည် value layer တစ်ခု၏ တန်ဖိုးနှင့်တူညီသော Frequency (ကြိမ်နှုန်း) (အကြိမ်အရေအတွက်) ကို cell တစ်ခုချင်းစီအလိုက် အကဲဖြတ်ပေးပါသည်။ Output raster ၏ အကျယ်အဝန်းနယ် (extent) နှင့် ကြည်လင်ပြတ်သားမှု (resolution) တို့ကို input raster layer ဖြင့် သတ်မှတ်ပြီး အမြဲတမ်း ``Int32`` အမျိုးအစားဖြစ်ပါသည်။

အကယ်၍ multiband raster (Band များစွာပါရှိသည့်) များကို data raster stack ထဲတွင် အသုံးပြုထားပါက algorithm သည် အမြဲတမ်း raster များ၏ ပထမ band အပေါ်တွင် ခွဲခြမ်းစိတ်ဖြာမှု (analysis) ကို ဆောင်ရွက်မည်ဖြစ်ပါသည် - ခွဲခြမ်းစိတ်ဖြာမှုတွင် အခြားသော band များကို အသုံးပြုရန်အတွက် GDAL ကို အသုံးပြုပါ။ Output NoData တန်ဖိုးကို ကိုယ်တိုင် သတ်မှတ်ပေးနိုင်ပါသည်။ 

.. figure:: img/greaterthanfrequency.png
  :align: center

  Output raster ထဲရှိ cell တစ်ခုချင်းစီအတွက် တန်ဖိုးသည် raster များ၏ စာရင်းထဲရှိ သက်ဆိုင်ရာ cell များသည် value raster ထက်ကြီးသည့် အကြိမ်အရေအတွက်ကို ကိုယ်စားပြုဖော်ပြပါသည်။ ``NoData`` cell (မီးခိုးရောင်) များကို ထည့်သွင်းစဉ်းစားပါသည်။

.. seealso:: :ref:`qgisequaltofrequency` ၊ :ref:`qgislessthanfrequency`

.. The params description comes from the "Equal to frequency" algorithm

.. include:: ./rasteranalysis.rst
  :start-after: .. **frequencyparams**
  :end-before: .. **endfrequencyparams**

Python code
............

**Algorithm ID**: ``native:greaterthanfrequency``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgishighestpositioninrasterstack:

Highest position in raster stack (Raster stack (အစုအထပ်) ထဲရှိ အမြင့်ဆုံးနေရာ)
-------------------------------------------------------------------------------

ထည့်သွင်းထားသည့် raster များအစုအထပ်တစ်ခုထဲတွင် အမြင့်ဆုံးတန်ဖိုးရှိသော raster ၏ တည်နေရာကို cell-by-cell basis (cell တစ်ခုချင်းစီအလိုက်) ဖြင့် အကဲဖြတ်ပါသည်။ တည်နေရာရေတွက်မှုများ (Position counts) သည် 1 ဖြင့် စပြီး input raster များ၏ အရေအတွက် စုစုပေါင်းအထိ အပိုင်းအခြားပမာဏရှိပါသည်။ Input raster များ၏ order (အစဉ်) သည် algorithm အတွက် သက်ဆိုင်မှုရှိပါသည်။ အကယ်၍ raster အများအပြားသည် အမြင့်ဆုံးတန်ဖိုးများ ရှိနေပါက ပထမဆုံး raster ကို position value (တည်နေရာတန်ဖိုး) အတွက်အသုံးပြုမည်ဖြစ်ပါသည်။

Data raster stack ထဲတွင် multiband (Band များစွာပါဝင်သည့်) raster များကို အသုံးပြုထားပါက algorithm သည် raster များ၏ ပထမ band အပေါ်တွင် ခွဲခြမ်းစိတ်ဖြာမှုကို အမြဲတမ်း ဆောင်ရွက်မည်ဖြစ်ပါသည် - ခွဲခြမ်းစိတ်ဖြာမှုများတွင် အခြားသော band များကို အသုံးပြုရန် GDAL ကိုအသုံးပြုပါ။ Raster layer stack ထဲရှိ မည်သည့် NoData cell များမဆိုသည် "ignore NoData" parameter ကို အမှန်ခြစ်မပြုလုပ်ထားပါက output raster ထဲတွင် NoData cell တစ်ခုကို ရရှိစေလိမ့်မည်ဖြစ်ပါသည်။ Output NoData တန်ဖိုးကို ကိုယ်တိုင် သတ်မှတ်ပေးနိုင်ပါသည်။ Output raster များ၏ အကျယ်အဝန်းနယ် (extent) နှင့် ကြည်လင်ပြတ်သားမှု (resolution) ကို reference (ရည်ညွှန်း) raster layer တစ်ခုဖြင့် သတ်မှတ်နိုင်ပြီး အမြဲတမ်း ``Int32`` အမျိုးအစားဖြစ်ပါသည်။ 


.. figure:: img/highestposition.png
  :align: center

.. seealso:: :ref:`qgislowestpositioninrasterstack`

.. **positionparams**

Parameters (သတ်မှတ်ချက်များ)
.............................

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
   * - **Input raster layers** **(ထည့်သွင်းအသုံးပြုသော raster layer များ)**
     - ``INPUT_RASTERS``
     - [raster] [list]
     - နှိုင်းယှဉ်ရန် raster layer များ၏စာရင်း
   * - **Reference layer** **(ရည်ညွှန်း layer)**
     - ``REFERENCE_LAYER``
     - [raster]
     - Output layer ဖန်တီးခြင်းအတွက် reference (ရည်ညွှန်း) layer (အကျယ်အဝန်းနယ် (extent)၊ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (CRS) ၊ pixel အတိုင်းအတာများ (dimensions))     
   * - **Ignore NoData values** **(NoData တန်ဖိုးများကို လျစ်လျူရှုပါ)**
     - ``IGNORE_NODATA`` 
     - [boolean]

       Default: False
     - အကယ်၍ အမှန်ခြစ်ဖြုတ်ထားပါက input layer များထဲရှိ မည်သည့် NoData cell များမဆိုသည် output raster ထဲတွင် NoData cell တစ်ခုကို ဖြစ်ပေါ်စေမည်ဖြစ်ပါသည်။  
   * - **Output layer** **(ရလာဒ် layer)**
     - ``OUTPUT`` 
     - [input ကဲ့သို့အတူတူဖြစ်ပါသည်။]

       Default: ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output no data value** 
     - ``OUTPUT_NODATA_VALUE``
     - [number]

       Default: -9999.0
     - Output layer ထဲတွင် nodata အတွက် အသုံးပြုမည့် တန်ဖိုး

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
     - [raster]
     - ရလာဒ် (result) ပါဝင်သည့် output raster layer
   * - **CRS authority identifier**
     - ``CRS_AUTHID``
     - [string]
     - Output raster layer ၏ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (coordinate reference system)
   * - **Extent** **(အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [string]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent)
   * - **Width in pixels** **(Pixel ဖြင့် အကျယ်)**
     - ``WIDTH_IN_PIXELS``
     - [integer]
     - Output raster layer ထဲရှိ column (တိုင်) များအရေအတွက်
   * - **Height in pixels** **(Pixel ဖြင့် အမြင့်)**
     - ``HEIGHT_IN_PIXELS`` 
     - [integer]
     - Output raster layer ထဲရှိ row (တန်း) များအရေအတွက်
   * - **Total pixel count** **(Pixel အရေအတွက် စုစုပေါင်း)**
     - ``TOTAL_PIXEL_COUNT``
     - [integer]
     - Output raster layer ထဲရှိ pixel အရေအတွက် (count)

.. **endpositionparams**

Python code
............

**Algorithm ID**: ``native:highestpositioninrasterstack``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgislessthanfrequency:

Less than frequency (ကြိမ်နှုန်း ထက်ပိုနည်းသော)
------------------------------------------------

ထည့်သွင်းထားသည့် raster အစုအထပ်တစ်ခု (input stack of rasters) ၏ တန်ဖိုးများသည် value layer တစ်ခု၏ တန်ဖိုးထက်ငယ်သော Frequency (ကြိမ်နှုန်း) (အကြိမ်အရေအတွက်) ကို cell တစ်ခုချင်းစီအလိုက် အကဲဖြတ်ပေးပါသည်။ Output raster ၏ အကျယ်အဝန်းနယ် (extent) နှင့် ကြည်လင်ပြတ်သားမှု (resolution) တို့ကို input raster layer ဖြင့် သတ်မှတ်ပြီး အမြဲတမ်း ``Int32`` အမျိုးအစားဖြစ်ပါသည်။

အကယ်၍ multiband raster (Band များစွာပါရှိသည့်) များကို data raster stack ထဲတွင် အသုံးပြုထားပါက algorithm သည် အမြဲတမ်း raster များ၏ ပထမ band အပေါ်တွင် ခွဲခြမ်းစိတ်ဖြာမှု (analysis)ကို ဆောင်ရွက်မည်ဖြစ်ပါသည် - ခွဲခြမ်းစိတ်ဖြာမှုတွင် အခြားသော band များကို အသုံးပြုရန်အတွက် GDAL ကို အသုံးပြုပါ။ Output NoData တန်ဖိုးကို ကိုယ်တိုင် သတ်မှတ်ပေးနိုင်ပါသည်။ 

.. figure:: img/lessthanfrequency.png
  :align: center

  Output raster ထဲရှိ cell တစ်ခုချင်းစီအတွက် တန်ဖိုးသည် raster များ၏ စာရင်းထဲရှိ သက်ဆိုင်ရာ cell များသည် value raster များထက်ငယ်သည့် အကြိမ်အရေအတွက်ကို ကိုယ်စားပြုဖော်ပြပါသည်။ ``NoData`` cell (မီးခိုးရောင်) များကို ထည့်သွင်းစဉ်းစားပါသည်။

.. seealso:: :ref:`qgisequaltofrequency`, :ref:`qgisgreaterthanfrequency`

.. The params description comes from the "Equal to frequency" algorithm

.. include:: ./rasteranalysis.rst
  :start-after: .. **frequencyparams**
  :end-before: .. **endfrequencyparams**

Python code
............

**Algorithm ID**: ``native:lessthanfrequency``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgislowestpositioninrasterstack:

Lowest position in raster stack (Raster stack ထဲရှိ အနိမ့်ဆုံးနေရာ)
--------------------------------------------------------------------

ထည့်သွင်းထားသည့် raster များအစုအထပ်တစ်ခုထဲတွင် အနိမ့်ဆုံးတန်ဖိုးရှိသော raster ၏ တည်နေရာကို cell-by-cell basis (cell တစ်ခုချင်းစီအလိုက်) ဖြင့် အကဲဖြတ်ပါသည်။ တည်နေရာရေတွက်မှုများ (Position counts) သည် 1 ဖြင့် စပြီး input raster များ၏ အရေအတွက် စုစုပေါင်းအထိ အပိုင်းအခြားပမာဏရှိပါသည်။ Input raster များ၏ order (အစဉ်) သည် algorithm အတွက် သက်ဆိုင်မှုရှိပါသည်။ အကယ်၍ raster အများအပြားသည် အနိမ့်ဆုံးတန်ဖိုးများ ရှိနေပါက ပထမဆုံး raster ကို position value (တည်နေရာတန်ဖိုး) အတွက်အသုံးပြုမည်ဖြစ်ပါသည်။

Data raster stack ထဲတွင် multiband (Band များစွာပါဝင်သည့်) raster များကို အသုံးပြုထားပါက algorithm သည် raster များ၏ ပထမ band အပေါ်တွင် ခွဲခြမ်းစိတ်ဖြာမှုကို အမြဲတမ်း ဆောင်ရွက်မည်ဖြစ်ပါသည် - ခွဲခြမ်းစိတ်ဖြာမှုများတွင် အခြားသော band များကို အသုံးပြုရန် GDAL ကိုအသုံးပြုပါ။ Raster layer stack ထဲရှိ မည်သည့် NoData cell များမဆိုသည် "ignore NoData" parameter ကို အမှန်ခြစ်မပြုလုပ်ထားပါက output raster ထဲတွင် NoData cell တစ်ခုကို ရရှိစေလိမ့်မည်ဖြစ်ပါသည်။ Output NoData တန်ဖိုးကို ကိုယ်တိုင် သတ်မှတ်ပေးနိုင်ပါသည်။ Output raster များ၏ အကျယ်အဝန်းနယ် (extent) နှင့် ကြည်လင်ပြတ်သားမှု (resolution) ကို reference (ရည်ညွှန်း) raster layer တစ်ခုဖြင့် သတ်မှတ်နိုင်ပြီး အမြဲတမ်း ``Int32`` အမျိုးအစားဖြစ်ပါသည်။


.. figure:: img/lowestposition.png
  :align: center

.. seealso:: :ref:`qgishighestpositioninrasterstack`

.. The params description comes from the "Highest position" algorithm

.. include:: ./rasteranalysis.rst
  :start-after: .. **positionparams**
  :end-before: .. **endpositionparams**

Python code
............

**Algorithm ID**: ``native:lowestpositioninrasterstack``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisrasterbooleanand:

Raster boolean AND
-------------------

Input raster များအစုတစ်ခုအတွက် boolean ``AND`` ကိုတွက်ချက်ပေးပါသည်။ (Boolean အော်ပရေတာများသည် ရှာဖွေမှုတစ်ခုတွင် keyword များကို ပေါင်းစပ်ရန် သို့မဟုတ် ဖယ်ထုတ်ရန်အတွက် တွဲဖက်အဖြစ်အသုံးပြုသည့် ရိုးရှင်းသောစကားလုံးများ (AND၊ OR၊ NOT သို့မဟုတ် AND NOT) များဖြစ်သည်။) အကယ်၍ input raster များအားလုံးသည် pixel တစ်ခုအတွက် non-zero value (သုညနှင့်မညီသောကိန်းဂဏန်းတန်ဖိုး) တစ်ခုရှိပါက အဆိုပါ pixel ကို output raster ထဲတွင် ``1`` အဖြစ်သို့ သတ်မှတ်မည်ဖြစ်ပါသည်။ အကယ်၍ pixel အတွက် မည်သည့် input raster မဆိုသည် ``0`` တန်ဖိုးများရှိနေပါက ၎င်းကို output raster ထဲတွင် ``0`` အဖြစ်သို့ သတ်မှတ်မည်ဖြစ်ပါသည်။

Output raster ကို ဖန်တီးသည့်အခါတွင် ရည်ညွှန်း layer parameter သည် လက်ရှိရှိနေသည့် raster layer တစ်ခုကို reference တစ်ခုအဖြစ်အသုံးပြုနိုင်ရန် သတ်မှတ်ပေးပါသည်။ Output raster သည် ဤ layer ကဲ့သို့ပင် တူညီသည့် extent (အကျယ်အဝန်းနယ်)၊ CRS (ရည်ညွှန်းကိုဩဒိနိတ်စနစ်) နှင့် pixel dimensions (အတိုင်းအတာများ) ရှိမည်ဖြစ်ပါသည်။ 

Default အားဖြင့် မည်သည့် input layer များထဲမဆိုရှိ nodata pixel တစ်ခုသည် output raster ထဲတွင် nodata pixel တစ်ခုကို ရရှိစေမည်ဖြစ်ပါသည်။ အကယ်၍ :guilabel:`Treat nodata values as false` option ကို အမှန်ခြစ်ပြုလုပ်ထားပါက nodata input များကို input တန်ဖိုး ``0`` အဖြစ် ပြုမှုဆောင်ရွက်မည်ဖြစ်ပါသည်။

.. seealso:: :ref:`qgisrasterbooleanor`

Parameters (သတ်မှတ်ချက်များ)
.............................

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
   * - **Input layers** **(ထည့်သွင်းအသုံးပြုသော layer များ)**
     - ``INPUT``
     - [raster] [list]
     - Input raster layer များ၏စာရင်း
   * - **Reference layer** **(ရည်ညွှန်း layer)**
     - ``REF_LAYER``
     - [raster]
     - Output layer ဖန်တီးခြင်းအတွက် reference (ရည်ညွှန်း) layer (အကျယ်အဝန်းနယ် (extent)၊ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (CRS) ၊ pixel အတိုင်းအတာများ (dimensions))
   * - **Treat nodata values as false** **(Nodata တန်ဖိုးများကို false အဖြစ် ပြုမှုဆောင်ရွက်ပါ)**
     - ``NODATA_AS_FALSE``
     - [boolean]

       Default : False
     - လုပ်ဆောင်ချက် (operation) များကို ဆောင်ရွက်သည့်အခါတွင် input file များထဲရှိ nodata တန်ဖိုးများကို 0 အဖြစ် ပြုမှုဆောင်ရွက်ပါ။
   * - **Output layer**
     - ``OUTPUT``
     - [raster]

       Default : ``[Save to temporary file]``
     - ရလာဒ်ပါဝင်သော output raster ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**


Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output no data value** **(ရလာဒ် no data တန်ဖိုး)**
     - ``NO_DATA``
     - [number]

       Default: -9999.0
     - Output layer ထဲတွင် nodata အတွက် အသုံးပြုမည့် တန်ဖိုး
   * - **Output data type** **(ရလာဒ် data အမျိုးအစား)**
     - ``DATA_TYPE``
     - [enumeration]

       Default: 5
     - Output raster data အမျိုးအစား။ ရွေးချယ်စရာများမှာ-

       .. include:: ../algs_include.rst
          :start-after: **native_raster_data_types**
          :end-before: **end_native_raster_data_types**

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
   * - **Extent** **(အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [string]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent)
   * - **CRS authority identifier**
     - ``CRS_AUTHID``
     - [string]
     - Output raster layer ၏ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (coordinate reference system)
   * - **Width in pixels** **(Pixel ဖြင့် အကျယ်)**
     - ``WIDTH_IN_PIXELS``
     - [integer]
     - Output raster layer ထဲရှိ column (တိုင်) များအရေအတွက်
   * - **Height in pixels** **(Pixel ဖြင့် အမြင့်)**
     - ``HEIGHT_IN_PIXELS`` 
     - [integer]
     - Output raster layer ထဲရှိ row (တန်း) များအရေအတွက်
   * - **Total pixel count** **(Pixel အရေအတွက် စုစုပေါင်း)**
     - ``TOTAL_PIXEL_COUNT``
     - [integer]
     - Output raster layer ထဲရှိ pixel အရေအတွက် (count)
   * - **NODATA pixel count** **(Nodata pixel အရေအတွက်)**
     - ``NODATA_PIXEL_COUNT``
     - [integer]
     - Output raster layer ထဲရှိ nodata pixel များအရေအတွက်
   * - **True pixel count** **(True ဖြစ်သော Pixel အရေအတွက်)**
     - ``TRUE_PIXEL_COUNT``
     - [integer]
     - Output raster layer ထဲရှိ True ဖြစ်သော pixel အရေအတွက် (တန်ဖိုး = 1)
   * - **False pixel count** **(False ဖြစ်သော Pixel အရေအတွက်)** 
     - ``FALSE_PIXEL_COUNT``
     - [integer]
     - Output raster layer ထဲရှိ False ဖြစ်သော pixel အရေအတွက် (တန်ဖိုး = 0)       
   * - **Output layer**
     - ``OUTPUT``
     - [raster]
     - ရလာဒ် (result) ပါဝင်သည့် output raster layer
   

Python code
............

**Algorithm ID**: ``native:rasterbooleanand``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisrasterbooleanor:

Raster boolean OR
------------------

Input raster များအစုတစ်ခုအတွက် boolean ``OR`` ကိုတွက်ချက်ပေးပါသည်။ (Boolean အော်ပရေတာများသည် ရှာဖွေမှုတစ်ခုတွင် keyword များကို ပေါင်းစပ်ရန် သို့မဟုတ် ဖယ်ထုတ်ရန်အတွက် တွဲဖက်အဖြစ်အသုံးပြုသည့် ရိုးရှင်းသောစကားလုံးများ (AND၊ OR၊ NOT သို့မဟုတ် AND NOT) များဖြစ်သည်။) အကယ်၍ input raster များအားလုံးသည် pixel တစ်ခုအတွက် non-zero value (သုညနှင့်မညီသောကိန်းဂဏန်းတန်ဖိုး) တစ်ခုရှိပါက အဆိုပါ pixel ကို output raster ထဲတွင် ``0`` အဖြစ်သို့ သတ်မှတ်မည်ဖြစ်ပါသည်။ အကယ်၍ pixel အတွက် မည်သည့် input raster မဆိုသည် ``1`` တန်ဖိုးများရှိနေပါက ၎င်းကို output raster ထဲတွင် ``1`` အဖြစ်သို့ သတ်မှတ်မည်ဖြစ်ပါသည်။

Output raster ကို ဖန်တီးသည့်အခါတွင် ရည်ညွှန်း layer parameter သည် လက်ရှိရှိနေသည့် raster layer တစ်ခုကို reference တစ်ခုအဖြစ်အသုံးပြုနိုင်ရန် သတ်မှတ်ပေးပါသည်။ Output raster သည် ဤ layer ကဲ့သို့ပင် တူညီသည့် extent (အကျယ်အဝန်းနယ်)၊ CRS (ရည်ညွှန်းကိုဩဒိနိတ်စနစ်) နှင့် pixel dimensions (အတိုင်းအတာများ) ရှိမည်ဖြစ်ပါသည်။ 

Default အားဖြင့် မည်သည့် input layer များထဲမဆိုရှိ nodata pixel တစ်ခုသည် output raster ထဲတွင် nodata pixel တစ်ခုကို ရရှိစေမည်ဖြစ်ပါသည်။ အကယ်၍ :guilabel:`Treat nodata values as false` option ကို အမှန်ခြစ်ပြုလုပ်ထားပါက nodata input များကို input တန်ဖိုး ``0`` အဖြစ် ပြုမှုဆောင်ရွက်မည်ဖြစ်ပါသည်။

.. seealso:: :ref:`qgisrasterbooleanand`

Parameters (သတ်မှတ်ချက်များ)
.............................

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
   * - **Input layers** **(ထည့်သွင်းအသုံးပြုသော layer များ)**
     - ``INPUT``
     - [raster] [list]
     - Input raster layer များ၏စာရင်း
   * - **Reference layer** **(ရည်ညွှန်း layer)**
     - ``REF_LAYER``
     - [raster]
     - Output layer ဖန်တီးခြင်းအတွက် reference (ရည်ညွှန်း) layer (အကျယ်အဝန်းနယ် (extent)၊ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (CRS) ၊ pixel အတိုင်းအတာများ (dimensions))
   * - **Treat nodata values as false** **(Nodata တန်ဖိုးများကို false အဖြစ် ပြုမှုဆောင်ရွက်ပါ)**
     - ``NODATA_AS_FALSE``
     - [boolean]

       Default : False
     - လုပ်ဆောင်ချက် (operation) များကို ဆောင်ရွက်သည့်အခါတွင် input file များထဲရှိ nodata တန်ဖိုးများကို 0 အဖြစ် ပြုမှုဆောင်ရွက်ပါ။
   * - **Output layer**
     - ``OUTPUT``
     - [raster]

       Default : ``[Save to temporary file]``
     - ရလာဒ်ပါဝင်သော output raster ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output no data value** 
     - ``NO_DATA``
     - [number]

       Default: -9999.0
     - Output layer ထဲတွင် nodata အတွက် အသုံးပြုမည့် တန်ဖိုး
   * - **Output data type** 
     - ``DATA_TYPE``
     - [enumeration]

       Default: 5
     - Output raster data အမျိုးအစား။ ရွေးချယ်စရာများမှာ-

       .. include:: ../algs_include.rst
          :start-after: **native_raster_data_types**
          :end-before: **end_native_raster_data_types**

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
   * - **Extent** **(အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [string]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent)
   * - **CRS authority identifier**
     - ``CRS_AUTHID``
     - [string]
     - Output raster layer ၏ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (coordinate reference system)
   * - **Width in pixels** **(Pixel ဖြင့် အကျယ်)**
     - ``WIDTH_IN_PIXELS``
     - [integer]
     - Output raster layer ထဲရှိ column (တိုင်) များအရေအတွက်
   * - **Height in pixels** **(Pixel ဖြင့် အမြင့်)**
     - ``HEIGHT_IN_PIXELS`` 
     - [integer]
     - Output raster layer ထဲရှိ row (တန်း) များအရေအတွက်
   * - **Total pixel count** **(Pixel အရေအတွက် စုစုပေါင်း)**
     - ``TOTAL_PIXEL_COUNT``
     - [integer]
     - Output raster layer ထဲရှိ pixel အရေအတွက် (count)
   * - **NODATA pixel count** **(Nodata pixel အရေအတွက်)**
     - ``NODATA_PIXEL_COUNT``
     - [integer]
     - Output raster layer ထဲရှိ nodata pixel များအရေအတွက်
   * - **True pixel count** **(True ဖြစ်သော Pixel အရေအတွက်)**
     - ``TRUE_PIXEL_COUNT``
     - [integer]
     - Output raster layer ထဲရှိ True ဖြစ်သော pixel အရေအတွက် (တန်ဖိုး = 1)
   * - **False pixel count** **(False ဖြစ်သော Pixel အရေအတွက်)** 
     - ``FALSE_PIXEL_COUNT``
     - [integer]
     - Output raster layer ထဲရှိ False ဖြစ်သော pixel အရေအတွက် (တန်ဖိုး = 0)       
   * - **Output layer**
     - ``OUTPUT``
     - [raster]
     - ရလာဒ် (result) ပါဝင်သည့် output raster layer 

Python code
............

**Algorithm ID**: ``native:rasterbooleanor``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisrastercalculator:

Raster calculator (Raster ဂဏန်းတွက်စက်)
----------------------------------------

Raster layer များကို အသုံးပြုပြီး အက္ခရာသင်္ချာတွက်ချက်မှုများကို (algebraic operations) ကို ဆောင်ရွက်ပေးပါသည်။

ရရှိလာသည့် layer တွင် expression (ခိုင်းစေချက်) တစ်ခုအရ တွက်ချက်ပေးထားသော ၎င်း၏တန်ဖိုးများရှိမည်ဖြစ်ပါသည်။ Expression တွင် ကိန်းဂဏန်းတန်ဖိုးများ (numerical values)၊ operator များနှင့် လက်ရှိ project ထဲရှိ မည်သည့် layer မဆိုသို့ ရည်ညွှန်းချက်များ (references) ပါဝင်နိုင်ပါသည်။

.. note:: :ref:`processing_batch` ထဲတွင် သို့မဟုတ် :ref:`console` မှ calculator ကို အသုံးပြုသည့်အခါတွင် အသုံးပြုမည့်ဖိုင်များကို သတ်မှတ်ပေးရမည်ဖြစ်ပါသည်။ ဖိုင်၏ အခြေခံအမည် (ဖိုင်လမ်းကြောင်းအပြည့်အစုံမပါရှိဘဲ) ကို အသုံးပြုပြီး သက်ဆိုင်ရာ layer များကို ညွှန်းဆိုမည်ဖြစ်ပါသည်။ ဥပမာအားဖြင့်- ``path/to/my/rasterfile.tif`` ၌ရှိသော layer တစ်ခုကိုအသုံးပြုပါက အဆိုပါ layer ၏ ပထမ band ကို ``rasterfile.tif@1`` အဖြစ် ညွှန်းဆိုမည်ဖြစ်ပါသည်။ 

.. seealso:: :ref:`label_raster_calc`


Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Layers**
     -  GUI only
     -
     - ရည်ညွှန်းချက် (legend) ထဲတွင် ထည့်သွင်းထားသည့် raster layer များအားလုံး၏ စာရင်းကိုပြသသည်။ ၎င်းတို့အား expression box ကို ဖြည့်ရန် အသုံးပြုနိုင်ပါသည် (ထည့်သွင်းရန် ကလစ်နှစ်ချက်နှိပ်ပါ)။ Raster layer များကို ၎င်းတို့၏ အမည် နှင့် band နံပါတ် - ``layer_name@band_number`` ဖြင့် ညွှန်းဆိုပါသည်။ ဥပမာအားဖြင့် ``DEM`` ဟု အမည်တွင်သော layer တစ်ခုမှ ပထမဆုံး band ကို ``DEM@1`` အဖြစ် ညွှန်းဆိုပါသည်။
   * - **Operators**
     -  GUI only
     -
     - Expression box ကို ဖြည့်ရန် အသုံးပြုနိုင်သည့် calculator ကဲ့သို့ ခလုတ်အချို့ပါရှိသည်။
   * - **Expression**
     -  ``EXPRESSION``
     - [string]
     - Output raster layer ကို တွက်ချက်ရန် အသုံးပြုမည့် Expression။ ဤ box တွင် expression ကို တိုက်ရိုက်ထည့်သွင်းရန် ပံ့ပိုးပေးထားသည့် operator buttons (ခလုတ်များ) ကို အသုံးပြုနိုင်ပါသည်။
   * - **Predefined expressions** **(ကြိုတင်သတ်မှတ်ထားသည့် expression များ)** 
     - GUI only
     -
     - တွက်ချက်မှုများအတွက် ကြိုတင်သတ်မှတ်ထားသည့် ``NDVI`` expression ကို အသုံးပြုနိုင်သည် သို့မဟုတ်  expression အသစ်များကို သတ်မှတ်နိုင်ပါသည်။ :guilabel:`Add...` ခလုတ်သည် ကြိုတင်သတ်မှတ်ထားသည့် expression ကို ထည့်သွင်းပေးပါသည် (ထို့အပြင် parameter များ သတ်မှတ်ခြင်းကိုလည်း ခွင့်ပြုပါသည်)။ :guilabel:`Save...` ခလုတ်သည် expression အသစ်တစ်ခုအား သတ်မှတ်ခြင်းကို ခွင့်ပြုပါသည်။
   * - **Reference layer(s) (used for automated extent, cellsize, and CRS)** **ရည်ညွှန်း layer များ (အလိုအလျောက် အကျယ်အဝန်းနယ်၊ cell အရွယ်အစား နှင့် ရည်ညွှန်းကိုဩဒိနိတ်စနစ် တို့အတွက်အသုံးပြုပါသည်။)**   

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``LAYERS``
     - [raster] [list]
     - အကျယ်အဝန်းနယ်၊ cell အရွယ်အစား နှင့် ရည်ညွှန်းကိုဩဒိနိတ်စနစ်ကို ရယူအသုံးပြုမည့် layer (များ)။ ဤ box တွင် layer ကို ရွေးချယ်ခြင်းဖြင့် အခြားသော parameter များကို လက်ဖြင့် ဖြည့်သွင်းခြင်းကို ရှောင်ရှားနိုင်ပါသည်။ Raster layer များကို ၎င်းတို့၏ အမည်နှင့် band နံပါတ်များ ``layer_name@band_number`` ဖြင့် ညွှန်းဆိုပါသည်။ ဥပမာအားဖြင့် ``DEM`` ဟု အမည်တွင်သော layer မှ ပထမဆုံးရောင်စဉ်ကို ``DEM@1`` အဖြစ် ညွှန်းဆိုပါသည်။
   * - **Cell size (use 0 or empty to set it automatically)** **(ဆဲလ်အရွယ်အစား (၎င်းကို အလိုအလျောက်သတ်မှတ်ရန် 0 သို့မဟုတ် empty ကို အသုံးပြုပါ))**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``CELLSIZE``
     - [number]
     - Output raster layer ၏ cell အရွယ်အစား ။ အကယ်၍ cell အရွယ်အစား ကို မသတ်မှတ်ထားပါက ရွေးချယ်ထားသည့် (selected) reference (ရည်ညွှန်း) layer (များ) ၏ အနည်းဆုံး cell အရွယ်အစား ကို အသုံးပြုမည်ဖြစ်ပါသည်။ Cell အရွယ်အစားသည် X နှင့် Y ဝင်ရိုးများအတွက် အတူတူပင်ဖြစ်မည်ဖြစ်ပါသည်။
   * - **Output extent** **(ရလာဒ် အကျယ်အဝန်းနယ်)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``EXTENT``
     - [extent]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်း (spatial extent) ကို သတ်မှတ်ပါ။ အကယ်၍ အကျယ်အဝန်းနယ်ကို သတ်မှတ်ထားခြင်းမရှိပါက အနိမ့်ဆုံးအနေဖြင့် ရွေးချယ်ထားသည့် (selected) reference(ရည်ညွှန်း) layer များအားလုံးကို လွှမ်းခြုံနိုင်သည့် အကျယ်အဝန်းနယ်ကို အသုံးပြုမည်ဖြစ်ပါသည်။

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Output CRS** **(Output ၏ရည်ညွှန်းကိုဩဒိနိတ်စနစ်)** 

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``CRS``
     - [crs]
     - Output raster layer ၏ CRS ။ အကယ်၍ output ၏ CRS ကို မသတ်မှတ်ထားပါက ပထမဆုံး reference (ရည်ညွှန်း) layer ၏ CRS ကို အသုံးပြုမည်ဖြစ်ပါသည်။
   * - **Output**
     - ``OUTPUT``
     - [raster]

       Default : ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်- 

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
   * - **Output**
     - ``OUTPUT`` 
     - [raster]
     - တွက်ချက်ထားသည့် တန်ဖိုးများပါဝင်သည့် output raster file 

Python code
............

**Algorithm ID**: ``qgis:rastercalculator``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisrasterlayerproperties:

Raster layer properties (Raster layer ဂုဏ်သတ္တိများ)
-----------------------------------------------------

အကျယ်အဝန်းနယ်၊ pixel အရွယ်အစားနှင့် pixel များ၏ အတိုင်းအတာများ (မြေပုံ ယူနစ်များဖြင့်)၊ band နံပါတ်များ နှင့် nodata value များပါဝင်သော raster layer ၏ အခြေခံဂုဏ်သတ္တိများ (basic properties) ကို ရရှိစေမည်ဖြစ်ပါသည်။

ဤ algorithm ကို model တစ်ခုထဲတွင် အခြားသော algorithm သို့ input(အဝင်) တန်ဖိုးများအဖြစ် အသုံးပြုနိုင်ရေး ထိုအသုံးဝင်သည့် ဂုဏ်သတ္တိများကို ထုတ်နှုတ်ရန် (extracting) နည်းလမ်းတစ်ခုအဖြစ် အသုံးပြုရန် ရည်ရွယ်ပါသည်။ - ဥပမာ- လက်ရှိရှိပြီးသား raster တစ်ခု၏ pixel အရွယ်အစားများကို GDAL raster algorithm တစ်ခုသို့ လွှဲပြောင်းခြင်းကို ခွင့်ပြုရန်။


Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)** 
     - ``INPUT``
     - [raster]
     - Input raster layer
   * - **Band number** **(Band နံပါတ်)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``BAND``
     - [raster band]

       Default: Not set
     - သီးသန့်လှိုင်းအလွှာ (specific band) တစ်ခု၏ ဂုဏ်သတ္တိများကို ပြန်လည်ထုတ်ပေးရန်/မထုတ်ပေးရန်။ အကယ်၍ band တစ်ခုကို သီးသန့် သတ်မှတ်ထားပါက ရွေးချယ်မှုပြုလုပ်ထားသည့် band ၏ noData တန်ဖိုးကိုလည်း ပြန်လည်ရရှိစေမည်ဖြစ်ပါသည်။


Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Number of bands in raster** **(Raster ထဲရှိ band များအရေအတွက်)**
     - ``BAND_COUNT``
     - [number]
     - Raster ထဲရှိ band များအရေအတွက်
   * - **CRS authority identifier**
     - ``CRS_AUTHID``
     - [string]
     - Output raster layer ၏ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (coordinate reference system)
   * - **Extent** **(အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [string]
     - CRS ထဲရှိ raster layer အကျယ်အဝန်းနယ်
   * - **Band has a NoData value set** **(Band သည် NoData value set တစ်ခုရှိပါသည်)** 
     - ``HAS_NODATA_VALUE``
     - [boolean] 
     - ရွေးချယ်မှုပြုလုပ်ထားသည့် band ထဲရှိ NODATA pixel များအတွက် raster layer တွင် value set တစ်ခု ရှိ/မရှိကို ဖော်ပြပါသည်။
   * - **Height in pixels** **(Pixels ဖြင့် အမြင့်)**
     - ``HEIGHT_IN_PIXELS``
     - [integer]
     - Raster layer ထဲရှိ column (တိုင်) အရေအတွက်များ
   * - **Band NoData value** **(Band အတွက် NoData တန်ဖိုး)**
     - ``NODATA_VALUE``
     - [number]
     - ရွေးချယ်မှုပြုလုပ်ထားသည့် band ထဲရှိ NODATA pixel များ၏ တန်ဖိုး (အကယ်၍ သတ်မှတ်ထားပါက)
   * - **Pixel size (height) in map units** **(Pixel အရွယ်အစား(အမြင့်) မြေပုံယူနစ်များဖြင့်)** 
     - ``PIXEL_HEIGHT``
     - [integer]
     - မြေပုံယူနစ်များဖြင့် Pixel ၏ ဒေါင်လိုက်အရွယ်အစား (Vertical size) 
   * - **Pixel size (width) in map units** **(Pixel အရွယ်အစား(အကျယ်) မြေပုံယူနစ်များဖြင့်)**
     - ``PIXEL_WIDTH``
     - [integer]
     - မြေပုံယူနစ်များဖြင့် Pixel ၏ ရေပြင်ညီအရွယ်အစား (Horizontal size)
   * - **Width in pixels** **(Pixels ဖြင့် အကျယ်)**
     - ``WIDTH_IN_PIXELS``
     - [integer]
     - Raster layer ထဲရှိ row (တန်း) အရေအတွက်များ
   * - **Maximum x-coordinate** **(အမြင့်ဆုံး x-coordinate)**
     - ``X_MAX``
     - [number]
     -
   * - **Minimum x-coordinate** **(အနိမ့်ဆုံး x-coordinate)**
     - ``X_MIN``
     - [number]
     -
   * - **Maximum y-coordinate** **(အမြင့်ဆုံး y-coordinate)**
     - ``Y_MAX``
     - [number]
     -
   * - **Minimum y-coordinate** **(အနိမ့်ဆုံး y-coordinate)**
     - ``Y_MIN``
     - [number]
     -

Python code
............

**Algorithm ID**: ``native:rasterlayerproperties``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisrasterlayerstatistics:

Raster layer statistics (Raster layer ဆိုင်ရာ စာရင်းအင်းအချက်အလက်များ)
-----------------------------------------------------------------------

Raster layer ၏ band တစ်ခုထဲရှိ တန်ဖိုးများမှ အခြေခံစာရင်းအင်းအချက်အလက်များ (basic statistics) ကို တွက်ချက်ပေးပါသည်။ Output (ရလာဒ်) ကို :menuselection:`Processing --> Results viewer` menu ထဲတွင် ထည့်သွင်းပါသည်။


Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input Raster** **(ထည့်သွင်းအသုံးပြုသော raster)**
     - ``INPUT``
     - [raster]
     - Input raster layer
   * - **Band number** **(Band နံပါတ်)**
     - ``BAND``
     - [raster band]

       Default : Input layer ၏ ပထမ Band
     - Raster သည် multiband (Band များစွာ) ဖြစ်ပါက စာရင်းအင်းအချက်အလက်များရယူလိုသည့် band ကို ရွေးချယ်ပါ။ 
   * - **Statistics** **(စာရင်းအင်းအချက်အလက်များ)**
     - ``OUTPUT_HTML_FILE``
     - [html]

       Default : ``[Save to temporary file]``
     - Output file ၏ သီးသန့်သတ်မှတ်ချက် (Specification)-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types_skip**
          :end-before: **end_file_output_types_skip**


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
   * - **Maximum value** **(အမြင့်ဆုံးတန်ဖိုး)**
     - ``MAX``
     - [number]
     -
   * - **Mean value** **(သမတ်ကိန်းတန်ဖိုး)**
     - ``MEAN``
     - [number]
     -
   * - **Minimum value** **(အနိမ့်ဆုံးတန်ဖိုး)**
     - ``MIN``
     - [number]
     -
   * - **Statistics** **(စာရင်းအင်းအချက်အလက်များ)**
     - ``OUTPUT_HTML_FILE``
     - [html]
     - Output file တွင် အောက်ဖော်ပြပါ အချက်အလက်များပါဝင်ပါသည်-

       * Analyzed file (ခွဲခြမ်းစိတ်ဖြာမှုပြုလုပ်ထားသည့် file)- raster layer ၏ လမ်းကြောင်း (path)
       * Minimum value (အနိမ့်ဆုံးတန်ဖိုး) - raster ၏ အနိမ့်ဆုံးတန်ဖိုး
       * Maximum value (အမြင့်ဆုံးတန်ဖိုး) - raster ၏ အမြင့်ဆုံးတန်ဖိုး
       * Range (အပိုင်းအခြားပမာဏ) - အမြင့်ဆုံးတန်ဖိုး နှင့် အနိမ့်ဆုံးတန်ဖိုး အကြား ကွာခြားချက်          
       * Sum (ပေါင်းလဒ်) - တန်ဖိုးများ၏ စုစုပေါင်း ပေါင်းလဒ်     
       * Mean value (သမတ်ကိန်းတန်ဖိုး) - တန်ဖိုးများ၏ သမတ်ကိန်း တန်ဖိုး
       * Standard deviation (စံတိမ်းချက်) - တန်ဖိုးများ၏ စံတိမ်းချက်
       * Sum of the squares (နှစ်ထပ်ကိန်းများပေါင်းလဒ်) - ခြုံငုံထားသည့်သမတ်ကိန်း (overall mean) မှ စူးစမ်းလေ့လာမှု (observation) တစ်ခုချင်းစီ၏ squared differences (နှစ်ထပ်ကိန်း ကွာခြားချက်) များပေါင်းလဒ်

   * - **Range** **(အပိုင်းအခြားပမာဏ)**
     - ``RANGE``
     - [number]
     -
   * - **Standard deviation** **(စံတိမ်းချက်)**
     - ``STD_DEV``
     - [number]
     -
   * - **Sum** **(ပေါင်းလဒ်)**
     - ``SUM``
     - [number]
     -
   * - **Sum of the squares** **(နှစ်ထပ်ကိန်းများပေါင်းလဒ်)**
     - ``SUM_OF_SQUARES``
     - [number]
     -

Python code
............

**Algorithm ID**: ``native:rasterlayerstatistics``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisrasterlayeruniquevaluesreport:

Raster layer unique values report (Raster layer ၏ သိသာထင်ရှားသည့် တန်ဖိုးများ အစီရင်ခံစာ)
------------------------------------------------------------------------------------------

Raster layer တစ်ခုထဲရှိ သိသာထင်ရှားသည့်တန်ဖိုး (unique value) တစ်ခုချင်းစီ၏ အရေအတွက် (count) နှင့် ဧရိယာ(area) ကို ပြန်လည်ရရှိစေပါသည်။

Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input Raster** **(ထည့်သွင်းအသုံးပြုသော raster)**
     - ``INPUT``
     - [raster]
     - Input raster layer
   * - **Band number** **(Band နံပါတ်)**
     - ``BAND``
     - [raster band]

       Default : Input layer ၏ ပထမ Band
     - Raster သည် multiband (Band များစွာ) ဖြစ်ပါက စာရင်းအင်းအချက်အလက်များရယူလိုသည့် band ကို ရွေးချယ်ပါ။ 
   * - **Unique values report** **(သိသာထင်ရှားသည့် တန်ဖိုးများ အစီရင်ခံစာ )**
     - ``OUTPUT_HTML_FILE``
     - [file]

       Default : ``[Save to temporary file]``
     - ရရှိလာသည့် output file ၏ သီးသန့်သတ်မှတ်ချက် (Specification)-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types_skip**
          :end-before: **end_file_output_types_skip**

   * - **Unique values table** **(သိသာထင်ရှားသည့် တန်ဖိုးများ ဇယား)**
     - ``OUTPUT_TABLE``
     - [table]

       Default : ``[Skip output]``
     - Unique values table ၏ သီးသန့်သတ်မှတ်ချက် (Specification)-

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
   * - **CRS authority identifier**
     - ``CRS_AUTHID``
     - [string]
     - Output raster layer ၏ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (coordinate reference system)
   * - **Extent** **(အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [string]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent)
   * - **Height in pixels** **(Pixel ဖြင့် အမြင့်)**
     - ``HEIGHT_IN_PIXELS``
     - [integer] 
     - Output raster layer ၏ row (တန်း) အရေအတွက်များ
   * - **NODATA pixel count** **(NODATA pixel အရေအတွက်)**
     - ``NODATA_PIXEL_COUNT``
     - [number]
     - Output raster layer ထဲရှိ NODATA pixel အရေအတွက်
   * - **Total pixel count** **(Pixel အရေအတွက် စုစုပေါင်း)**
     - ``TOTAL_PIXEL_COUNT``
     - [integer] 
     - Output raster layer ထဲရှိ pixel အရေအတွက် 
   * - **Unique values report** **(သိသာထင်ရှားသည့် တန်ဖိုးများ အစီရင်ခံစာ)**
     - ``OUTPUT_HTML_FILE``
     - [html]
     - ရရှိလာသည့် HTML ဖိုင်တွင် အောက်ပါ အချက်အလက်များပါဝင်ပါသည်-

       * Analyzed file (ခွဲခြမ်းစိတ်ဖြာမှုပြုလုပ်ထားသည့် file) - raster layer ၏ လမ်းကြောင်း (path)
       * Extent (အကျယ်အဝန်းနယ်) - အကျယ်အဝန်းနယ်၏ xmin ၊ ymin ၊ xmax ၊ ymax ကိုဩဒိနိတ်များ
       * Projection (အရိပ်ချစနစ်) - Layer ၏ အရိပ်ချစနစ် (Projection) 
       * Width in pixels - Column အရေအတွက်နှင့် pixel အကျယ်အရွယ်အစား
       * Height in pixels - Row အရေအတွက်နှင့် pixel အမြင့်အရွယ်အစား       
       * စုစုပေါင်း pixel အရေအတွက် - pixel များအားလုံး၏ အရေအတွက်
       * NODATA pixel အရေအတွက် - NODATA တန်ဖိုးရှိသည့် pixel များအရေအတွက်
   * - **Unique values table** **(သိသာထင်ရှားသည့် တန်ဖိုးဇယား)**
     - ``OUTPUT_TABLE``
     - [table]
     - Column ၃ ခု ပါရှိသည့် ဇယားတစ်ခု-

       * *တန်ဖိုး (value)* - pixel တန်ဖိုး
       * *အရေအတွက် (count)* - အဆိုပါတန်ဖိုးရှိသည့် pixel များ အရေအတွက်
       * *m*\ :sup:`2` - အဆိုပါတန်ဖိုးရှိသည့် pixel များ၏ စတုရန်းမီတာဖြင့်စုစုပေါင်းဧရိယာ  

   * - **Width in pixels** **(Pixel ဖြင့် အကျယ်)**
     - ``WIDTH_IN_PIXELS``
     - [integer]
     - Output raster layer ထဲရှိ column အရေအတွက်များ

Python code
............

**Algorithm ID**: ``native:rasterlayeruniquevaluesreport``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisrasterlayerzonalstats:

Raster layer zonal statistics (Raster layer နယ်မြေအလိုက် စာရင်းအင်းတွက်ချက်မှုများ)
------------------------------------------------------------------------------------

Raster layer တစ်ခု၏ တန်ဖိုးများအတွက် စာရင်းအင်းအချက်အလက်များကို တွက်ချက်ပြီး အခြားသော raster layer ထဲရှိ သတ်မှတ်ထားသော zones (ဇုန်များ) ဖြင့် အမျိုးအစားခွဲခြားခြင်း (categorized) ပြုလုပ်ပေးပါသည်။

.. seealso:: :ref:`qgiszonalstatisticsfb`

Parameters (သတ်မှတ်ချက်များ)
.............................

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
   * - **Input Raster** **(ထည့်သွင်းအသုံးပြုသော raster)** 
     - ``INPUT``
     - [raster]
     - Input raster layer
   * - **Band number** **(Band နံပါတ်)**
     - ``BAND``
     - [raster band]

       Default : Input layer ၏ ပထမ Band
     - Raster သည် multiband (Band များစွာ) ဖြစ်ပါက စာရင်းအင်းအချက်အလက်များရယူလိုသည့် band ကို ရွေးချယ်ပါ။
   * - **Zones layer**
     - ``ZONES``
     - [raster]
     - ဇုန်များကို သတ်မှတ်သည့် Raster layer။ ဇုန်များကို တူညီသော pixel တန်ဖိုးရှိသည့် contiguous (ဆက်စပ်) pixel များဖြင့် သတ်မှတ်ပေးပါသည်။
   * - **Zones band number** 
     - ``ZONES_BAND``
     - [raster band]

       Default : Raster layer ၏ ပထမ Band
     - Raster သည် multiband (Band များစွာ) ဖြစ်ပါက ဇုန်ကို သတ်မှတ်သည့် band ကို ရွေးချယ်ပါ။
   * - **Statistics** **(စာရင်းအင်းအချက်အလက်များ)**
     - ``OUTPUT_TABLE``
     - [table]

       Default :  ``[Create temporary layer]``
     - Output report (ရရှိလာသည့် အစီရင်ခံစာ) ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Reference layer** **(ရည်ညွှန်း layer)**

       Optional (မဖြစ်မနေ လုပ်ဆောင်ရန်မလိုပါ)
     - ``REF_LAYER``
     - [enumeration]

       Default: 0
     - Output layer ထဲတွင် ဇုန်များကို ဆုံးဖြတ်သည့်အခါတွင် အကိုးအကား (reference) အဖြစ်အသုံးပြုမည့် centroids(အလယ်မှတ်) များကို တွက်ချက်ရန် အသုံးပြုသည့် Raster layer။ အောက်ပါထဲမှ တစ်ခုဖြစ်ပါသည်-

       * 0 --- Input layer - Source (ရင်းမြစ်) raster layer မှ pixel တစ်ခုစီ၏ centroids (အလယ်မှတ်) ရှိ zone raster layer တန်ဖိုးကို sampling ပြုလုပ်ခြင်းဖြင့် ဇုန်များကို ဆုံးဖြတ်ပါသည်။
       * 1 --- Zones layer - Zones raster layer မှ pixel တစ်ခုစီ၏ centroids (အလယ်မှတ်) ၌ input raster layer ကို sampling ပြုလုပ်မည်ဖြစ်သည်။


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
   * - **CRS authority identifier**
     - ``CRS_AUTHID``
     - [string] 
     - Output raster layer ၏ ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (coordinate reference system)
   * - **Extent** **(အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [string]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent)
   * - **Height in pixels** **(Pixel ဖြင့် အမြင့်)**
     - ``HEIGHT_IN_PIXELS`` 
     - [integer]
     - Output raster layer ထဲရှိ row (တန်း) များအရေအတွက်
   * - **NODATA pixel count** **(NODATA pixel အရေအတွက်)**
     - ``NODATA_PIXEL_COUNT``
     - [number]
     - Output raster layer ထဲရှိ NODATA pixel အရေအတွက်
   * - **Statistics** **(စာရင်းအင်းအချက်အလက်များ)**
     - ``OUTPUT_TABLE``
     - [table]
     - Output layer တွင် **ဇုန်တစ်ခုချင်းစီအတွက်** အောက်ဖော်ပြပါ အချက်အလက်များပါဝင်ပါသည်-

       * ဧရိယာ(Area) - ဇုန်ထဲရှိ စတုရန်း raster ယူနစ်များဖြင့် ဧရိယာ၊
       * ပေါင်းလဒ်(Sum) - ဇုန်ထဲရှိ pixel တန်ဖိုးများ၏ စုစုပေါင်း ပေါင်းလဒ်၊
       * အရေအတွက်(Count) - ဇုန်ရှိ pixel အရေအတွက်၊
       * အနည်းဆုံး(Min) - ဇုန်အတွင်းရှိ အနည်းဆုံး pixel တန်ဖိုး၊
       * အများဆုံး(Max) - ဇုန်အတွင်းရှိ အများဆုံး pixel တန်ဖိုး၊
       * သမတ်ကိန်း(Mean) - ဇုန်အတွင်းရှိ pixel တန်ဖိုးများ၏ သမတ်ကိန်း၊
   * - **Total pixel count** **(Pixel အရေအတွက် စုစုပေါင်း)**
     - ``TOTAL_PIXEL_COUNT``
     - [number]
     - Output raster layer ထဲရှိ pixel အရေအတွက် 
   * - **Width in pixels** **(Pixel ဖြင့် အကျယ်)**
     - ``WIDTH_IN_PIXELS``
     - [number]
     - Output raster layer ထဲရှိ column (တိုင်) များအရေအတွက်

Python code
............

**Algorithm ID**: ``native:rasterlayerzonalstats``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisrastersurfacevolume:

Raster surface volume (Raster မျက်နှာပြင် ထုထည်)
-------------------------------------------------

ပေးထားသည့် base (အခြေ) level တစ်ခုနှင့်ဆက်နွယ်သော raster မျက်နှာပြင် (surface) တစ်ခုအောက်ရှိ ထုထည်ပမာဏကို တွက်ချက်ပေးပါသည်။ ၎င်းသည် Digital Elevation Model (DEM) (မြေပြင်အမြင့်ပြ‌ဒေတာ) များအတွက် အဓိက အသုံးဝင်ပါသည်။

Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input Raster** **(ထည့်သွင်းအသုံးပြုသော raster)**
     - ``INPUT``
     - [raster]
     - Input raster၊ မျက်နှာပြင်တစ်ခုကို ကိုယ်စားပြုဖော်ပြသည်။
   * - **Band number** **(Band နံပါတ်)**
     - ``BAND``
     - [raster band]

       Default : Raster layer ၏ ပထမ Band
     - Raster သည် multiband (Band များစွာ) ဖြစ်ပါက မျက်နှာပြင် (surface)ကို သတ်မှတ်သည့် band ကို ရွေးချယ်ပါ။
   * - **Base level**
     - ``LEVEL``
     - [number]

       Default: 0.0
     - အခြေ (base) သို့မဟုတ် ရည်ညွှန်း (reference) တန်ဖိုး တစ်ခုကို သတ်မှတ်ပါ။ ဤ base ကို ``Method`` parameter (သတ်မှတ်ချက်) အလိုက် ထုထည်ကို တွက်ချက်ရာတွင် အသုံးပြုပါသည် (အောက်တွင် ကြည့်ရှုပါ။)
   * - **Method** **(နည်းလမ်း)**
     - ``METHOD`` 
     - [enumeration]

       Default: 0
     - ``Base level`` နှင့် raster pixel တန်ဖိုးအကြား ကွာခြားချက်ဖြင့် ထုထည်တွက်ချက်ရန် နည်းလမ်း (Method)ကို သတ်မှတ်ပါ။ ရွေးချယ်စရာများမှာ-

       * 0 --- Base Level အပေါ်ကိုသာ ရေတွက်သည် - Base Level အပေါ်ရှိ pixel များကိုသာ ထုထည် (volume) ထဲသို့ ထည့်သွင်းမည်ဖြစ်ပါသည်။
       * 1 --- Base Level အောက်ကိုသာ ရေတွက်သည် - Base Level အောက်ရှိ pixel များကိုသာ ထုထည် (volume) ထဲသို့ ထည့်သွင်းမည်ဖြစ်ပါသည်။  
       * 2 --- Base Level အောက်ရှိ ထုထည်ကို နှုတ်ယူ (Subtract) သည် - Base Level အပေါ်ရှိ pixel များကိုသာ ထုထည် (volume) ထဲသို့ ထည့်သွင်းမည်ဖြစ်ပါသည်။ Base Level အောက်ရှိ pixel များကို ထုထည်ထဲမှ နှုတ်ယူ(Subtract) မည်ဖြစ်ပါသည်။
       * 3 --- Base Level အောက်တွင် ထုထည် (volume) များကို ပေါင်းထည့်သည် - Pixel သည် base level ၏ အပေါ် သို့မဟုတ် အောက် မည်သည့်နေရာတွင်မဆို ရှိစေကာမူ ထုထည်ကို ပေါင်းထည့်ပါသည်။ ၎င်းသည် pixel တန်ဖိုး နှင့် base level အကြား ကွာခြားချက်၏ ပကတိတန်ဖိုးများ (absolute values) ပေါင်းလဒ်နှင့် တူညီပါသည်။

   * - **Surface volume report** **(မျက်နှာပြင်ထုထည်အစီရင်ခံစာ)**
     - ``OUTPUT_HTML_FILE``
     - [html]

       Default : ``[Save to temporary file]``
     - Output HTML report (ရရှိလာသည့် HTML အစီရင်ခံစာ) ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**

   * - **Surface volume table** **(မျက်နှာပြင်ထုထည်ဇယား)**
     - ``OUTPUT_TABLE``
     - [table]

       Default: ``[Skip output]``
     - ရရှိလာသည့် ဇယား၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Volume** **(ထုထည်)**
     - ``VOLUME``
     - [number]
     - တွက်ချက်ထားသည့် ထုထည်
   * - **Area** **(ဧရိယာ)**
     - ``AREA``
     - [number]
     - စတုရန်းမြေပုံအတိုင်းအတာများဖြင့် ဧရိယာ
   * - **Pixel_count** **(Pixel အရေအတွက်)**
     - ``PIXEL_COUNT``
     - [number]
     - ခွဲခြမ်းစိတ်ဖြာမှုပြုလုပ်ထားသည့် pixel စုစုပေါင်း အရေအတွက်
   * - **Surface volume report** **(မျက်နှာပြင်ထုထည်အစီရင်ခံစာ)**
     - ``OUTPUT_HTML_FILE``
     - [html]
     - HTML format ဖြင့် output အစီရင်ခံစာ (ထုထည်၊ ဧရိယာနှင့် pixel အရေအတွက် ပါဝင်သော) 
   * - **Surface volume table** **(မျက်နှာပြင်ထုထည်ဇယား)**
     - ``OUTPUT_TABLE`` 
     - [table]
     - Output ဇယား (ထုထည်၊ ဧရိယာနှင့် pixel အရေအတွက် ပါဝင်သော)

Python code
............

**Algorithm ID**: ``native:rastersurfacevolume``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisreclassifybylayer:

Reclassify by layer (Layer ဖြင့် အတန်းအစားပြန်လည်ခွဲခြားခြင်း)
---------------------------------------------------------------

Vector table (ဇယား) တစ်ခုထဲတွင် သတ်မှတ်ထားသည့် အပိုင်းအခြားပမာဏများအပေါ် အခြေခံ၍ class (အတန်းအစား) တန်ဖိုးအသစ်များကိုသတ်မှတ်ခြင်းဖြင့် raster band တစ်ခုကို reclassify ပြုလုပ်ပေးပါသည်။

Parameters (သတ်မှတ်ချက်များ)
.............................

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
   * - **Raster layer**
     - ``INPUT_RASTER``
     - [raster]
     - Reclassify ပြုလုပ်မည့် raster layer 
   * - **Band number** **(Band နံပါတ်)**
     - ``RASTER_BAND``
     - [raster band]

       Default : Raster layer ၏ ပထမ Band
     - Raster သည် multiband (Band များစွာ) ဖြစ်ပါက reclassify ပြုလုပ်လိုသည့် band ကို ရွေးချယ်ပါ။
   * - **Layer containing class breaks** **(Class အဖြတ် များပါဝင်သည့် Layer)** 
     - ``INPUT_TABLE`` 
     - [vector: any]
     - Classification (အတန်းအစားခွဲခြားခြင်း) အတွက် အသုံးပြုမည့် တန်ဖိုးများပါဝင်သော Vector layer
   * - **Minimum class value field** **(အနိမ့်ဆုံး အတန်းအစား တန်ဖိုး ပါဝင်သည့် field)**
     - ``MIN_FIELD``
     - [tablefield: numeric]
     - အတန်းအစား (class) အတွက် အပိုင်းအခြားပမာဏ ၏ အနိမ့်ဆုံးတန်ဖိုးရှိသည့် Field    
   * - **Maximum class value field** **(အမြင့်ဆုံး အတန်းအစား တန်ဖိုး ပါဝင်သည့် field)**
     - ``MAX_FIELD``
     - [tablefield: numeric]
     - အတန်းအစား (class) အတွက် အပိုင်းအခြားပမာဏ ၏ အမြင့်ဆုံးတန်ဖိုးရှိသည့် Field   
   * - **Output value field** 
     - ``VALUE_FIELD``
     - [tablefield: numeric]
     - အတန်းအစား (class) အတွင်းကျရောက်သည့် pixel များတွင် သတ်မှတ်မည့်တန်ဖိုးပါဝင်သည့် Field 
       (သက်ဆိုင်ရာ အနိမ့်ဆုံးနှင့် အမြင့်ဆုံးတန်ဖိုးများအကြား)
   * - **Reclassified raster** **(Reclassify ပြုလုပ်ထားသော raster)**
     - ``OUTPUT``
     - [raster]

       Default : ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output no data value**
     - ``NO_DATA``
     - [number]

       Default: -9999.0
     - No data တန်ဖိုးများတွင် အသုံးပြုမည့် တန်ဖိုး
   * - **Range boundaries** **(အပိုင်းအခြားပမာဏ နယ်နိမိတ်များ)**
     - ``RANGE_BOUNDARIES``
     - [enumeration]

       Default: 0
     - အတန်းအစား သို့မဟုတ် အမျိုးအစားခွဲခြားခြင်း (classification) အတွက် နှိုင်းယှဉ်သည့်စည်းမျဉ်းများ(comparison rules) ကို သတ်မှတ်သည်။ ရွေးချယ်စရာများမှာ-

       * 0 --- min < value <= max
       * 1 --- min <= value < max
       * 2 --- min <= value <= max
       * 3 --- min < value < max
   * - **Use no data when no range matches value** **(အပိုင်းအခြားပမာဏသည် တန်ဖိုးနှင့်မကိုက်ညီသည့်အခါတွင် no data ကိုအသုံးပြုပါ)** 
     - ``NODATA_FOR_MISSING``
     - [boolean]
       Default: False
     - မည်သည့် class (အတန်းအစား) မျိုးတွင်မျှ ကျရောက်မနေသည့် band တန်ဖိုးများတွင် no data တန်ဖိုးကို အသုံးချပါသည်။ အကယ်၍ False ဖြစ်ပါက မူရင်းတန်ဖိုးကို ထိန်းသိမ်းထားပေးမည်ဖြစ်ပါသည်။
   * - **Output data type** **(ရလာဒ် ဒေတာအမျိုးအစား)**
     - ``DATA_TYPE``
     - [enumeration]

       Default: 5
     - Output raster ဖိုင်၏ format ကို သတ်မှတ်ပါ။ ရွေးချယ်စရာများမှာ-

       .. include:: ../algs_include.rst
          :start-after: **native_raster_data_types**
          :end-before: **end_native_raster_data_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Reclassified raster** **(Reclassify ပြုလုပ်ထားသော raster)**
     - ``OUTPUT``
     - [raster]
     - Reclassify ပြုလုပ်ထားသော band တန်ဖိုးများပါဝင်သော output raster layer

Python code
............

**Algorithm ID**: ``native:reclassifybylayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisreclassifybytable:

Reclassify by table (ဇယားဖြင့် အတန်းအစားပြန်လည်ခွဲခြားခြင်း)
-------------------------------------------------------------

ပုံသေဇယား (fixed table) တစ်ခုထဲတွင် သတ်မှတ်ထားသည့် အပိုင်းအခြားပမာဏများအပေါ် အခြေခံ၍ class တန်ဖိုးအသစ်များကိုသတ်မှတ်ခြင်းဖြင့် raster band တစ်ခုကို  reclassify ပြုလုပ်ပေးပါသည်။


Parameters (သတ်မှတ်ချက်များ)
.............................

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
   * - **Raster layer**
     - ``INPUT_RASTER``
     - [raster]
     - Reclassify ပြုလုပ်မည့် raster layer
   * - **Band number** **(Band နံပါတ်)**
     - ``RASTER_BAND``
     - [raster band]

       Default: 1
     - တန်ဖိုးများ ပြန်လည်တွက်ချက်လိုသည့် Raster band
   * - **Reclassification table** **(Reclassify ပြုလုပ်မည့်ဇယား)**
     - ``TABLE``
     - [table]
     - အတန်းအစား(class) (``Minimum``(အနိမ့်ဆုံး) နှင့် ``Maximum``(အမြင့်ဆုံး)) တစ်ခုချင်းစီ၏ နယ်နိမိတ်များကိုသတ်မှတ်ရန်အတွက် တန်ဖိုးများနှင့် အတန်းအစား (class) အတွင်းကျရောက်သည့် band တန်ဖိုးများတွင် သတ်မှတ်မည့် ``Value`` အသစ် ဖြည့်သွင်းရန် ကော်လံ(၃)ခုပါ ဇယား တစ်ခု။
   * - **Reclassified raster** **(Reclassify ပြုလုပ်ထားသည့် raster)**
     - ``OUTPUT``
     - [raster]

       Default : ``[Save to temporary file]``
     - Output raster layer ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်- 

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**


Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output no data value** 
     - ``NO_DATA``
     - [number]

       Default : -9999.0
     - No data တန်ဖိုးများတွင် အသုံးပြုမည့် တန်ဖိုး။ 
   * - **Range boundaries** **(အပိုင်းအခြားပမာဏ နယ်နိမိတ်များ)**
     - ``RANGE_BOUNDARIES``
     - [enumeration]

       Default : 0
     - အတန်းအစား သို့မဟုတ် အမျိုးအစားခွဲခြားခြင်း (classification) အတွက် နှိုင်းယှဉ်သည့်စည်းမျဉ်းများ (comparison rules) ကို သတ်မှတ်သည်။ ရွေးချယ်စရာများမှာ-

       * 0 --- min < value <= max
       * 1 --- min <= value < max
       * 2 --- min <= value <= max
       * 3 --- min < value < max
   * - **Use no data when no range matches value** **(အပိုင်းအခြားပမာဏများသည် တန်ဖိုးများနှင့် ကိုက်ညီမှုမရှိသည့်အခါတွင် no data ကို အသုံးပြုပါ)**  
     - ``NODATA_FOR_MISSING``
     - [boolean]

       Default: False
     - မည်သည့် အတန်းအစား(class) များသို့ ကျရောက်ခြင်းမရှိနေသည့် band တန်ဖိုးများတွင် no data တန်ဖိုးကို အသုံးပြုပါမည်။ အကယ်၍ False ဖြစ်ပါက မူရင်းတန်ဖိုးကို ထိန်းသိမ်းထားမည်ဖြစ်ပါသည်။ 
   * - **Output data type** **(ရလာဒ် ဒေတာအမျိုးအစား)**
     - ``DATA_TYPE``
     - [enumeration]

       Default: 5
     - Output raster file ၏ format ကို သတ်မှတ်သည်။ ရွေးချယ်စရာများမှာ-

       .. include:: ../algs_include.rst
          :start-after: **native_raster_data_types**
          :end-before: **end_native_raster_data_types**


Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Reclassified raster** **(Reclassify ပြုလုပ်ထားသည့် raster)**
     - ``OUTPUT``
     - [raster]
     - Reclassify ပြုလုပ်ထားသည့် band တန်ဖိုးများပါဝင်သော output raster layer 

Python code
............

**Algorithm ID**: ``native:reclassifybytable``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisrescaleraster:

Rescale raster (Raster စကေးပြန်လည်ချိန်ညှိခြင်း)
-------------------------------------------------

Raster ၏ histogram (pixel တန်ဖိုးများ) ၏ ပုံသဏ္ဍာန် (ပျံ့နှံ့မှု) ကို ထိန်းသိမ်းထားရှိပြီး raster layer ကို တန်ဖိုးအပိုင်းအခြားပမာဏ အသစ်တစ်ခုသို့ စကေးပြန်လည်ချိန်ညှိပေးပါသည်။ Input တန်ဖိုးများကို source (ရင်းမြစ်) raster ၏ အနိမ့်ဆုံး နှင့် အမြင့်ဆုံး pixel တန်ဖိုးများမှ ဦးတည်သည့် (destination) အနိမ့်ဆုံး နှင့် အမြင့်ဆုံး pixel တန်ဖိုး အပိုင်းအခြားပမာဏများအထိ linear interpolation တစ်ခုကို အသုံးပြုပြီး ပုံဖော်ရေးဆွဲခြင်း (mapped) ပြုလုပ်ပါသည်။

Default အားဖြင့် algorithm သည် original (မူရင်း) NODATA တန်ဖိုးကို ထိန်းသိမ်းထားရှိပါသည်။ သို့သော် ၎င်းကို အစားထိုးရေးသားရန် (override) ရန် နည်းလမ်းတစ်ခုရှိပါသည်။ 

.. figure:: img/rescale_raster.png
  :align: center

  Raster layer တစ်ခု၏ တန်ဖိုးများကို [0 - 50] မှ [100 - 1000] သို့ စကေးပြန်လည်ချိန်ညှိခြင်း 


Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 30 20 20 30

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input Raster** **(ထည့်သွင်းအသုံးပြုသော raster)** 
     - ``INPUT``
     - [raster]
     - စကေးပြန်လည်ချိန်ညှိခြင်း (rescaling) အတွက် အသုံးပြုသည့် Raster layer 
   * - **Band number** **(Band နံပါတ်)**
     - ``BAND``
     - [raster band]

       Default : Input layer ၏ ပထမ Band
     - Raster သည် multiband (Band များစွာ) ဖြစ်ပါက band တစ်ခုကို ရွေးချယ်ပါ။
   * - **New minimum value** **(အနိမ့်ဆုံးတန်ဖိုးအသစ်)**
     - ``MINIMUM``
     - [number]

       Default value: 0.0
     - စကေးပြန်လည်ချိန်ညှိထားသည့် layer ထဲတွင်အသုံးပြုရန် အနိမ့်ဆုံး pixel တန်ဖိုး
   * - **New maximum value** **(အမြင့်ဆုံးတန်ဖိုးအသစ်)**
     - ``MAXIMUM``
     - [number]

       Default value: 255.0
     - စကေးပြန်လည်ချိန်ညှိထားသည့် layer ထဲတွင်အသုံးပြုရန် အမြင့်ဆုံး pixel တန်ဖိုး
   * - **New NODATA value** **(NODATA တန်ဖိုးအသစ်)**
   
       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``NODATA``
     - [number]
     
       Default value: Not set (သတ်မှတ်ထားခြင်းမရှိပါ)
     - NODATA pixel များတွင် သတ်မှတ်မည့်တန်ဖိုး။ အကယ်၍ သတ်မှတ်ထားခြင်းမရှိပါက original (မူရင်း) NODATA တန်ဖိုးများကို ထိန်းသိမ်းထားရှိမည်ဖြစ်ပါသည်။
   * - **Rescaled** **(စကေးပြန်လည်ချိန်ညှိထားပြီးသော)**
     - ``OUTPUT``
     - [raster]

       Default : ``[Save to temporary file]``
     - Output raster layer ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Rescaled** **(စကေးပြန်လည်ချိန်ညှိထားပြီးသော)** 
     - ``OUTPUT``
     - [raster]
     - စကေးပြန်လည်ချိန်ညှိထားသော band တန်ဖိုးများပါရှိသည့် output raster layer


Python code
............

**Algorithm ID**: ``native:rescaleraster``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisroundrastervalues:

Round raster (Raster ကို အနီးစပ်ဆုံးတန်ဖိုးယူခြင်း)
----------------------------------------------------

သတ်မှတ်ထားသည့် ဒဿမကိန်းအရေအတွက်အလိုက် raster dataset တစ်ခု၏ cell တန်ဖိုးများကို Round(အနီးစပ်ဆုံးတန်ဖိုးယူခြင်း) ပြုလုပ်ပေးပါသည်။

တနည်းအားဖြင့် အနှုတ်ဒဿမကိန်းနေရာတစ်ခုကို base n တစ်ခု၏ powers (ပါဝါများ) သို့ တန်ဖိုးများအား round(အနီးစပ်ဆုံးတန်ဖိုးယူခြင်း) ပြုလုပ်ရန် အသုံးပြုနိုင်ပါသည်။ ဥပမာ- Base n တန်ဖိုး 10 နှင့် ဒဿမနေရာ -1 ဖြင့် algorithm သည် cell တန်ဖိုးများကို 10 ၏ ဆတိုးကိန်း (multiples) သို့ round ပြုလုပ်ပေးပြီး၊ ဒဿမနေရာ -2 ဖြစ်လျှင် 100 ၏ ဆတိုးကိန်း (multiples) အစရှိသဖြင့် round ပြုလုပ်ပါသည်။ Arbitrary (စိတ်ကြိုက်ဖြစ်သော) base တန်ဖိုးများကို ရွေးချယ်နိုင်ပါသည်။ Algorithm သည် တူညီသည့် multiplicative principle (ပွားများခြင်းဆိုင်ရာ နိယာမ) ကို အသုံးချပါသည်။ Cell တန်ဖိုးများကို base n ၏ မြှောက်ကိန်း (multiples) များသို့ Rounding ပြုလုပ်ခြင်းကို raster layer များအား generalize (Generalize ပြုလုပ်ခြင်းဆိုသည်မှာ cell အသစ်များအတွက် တန်ဖိုးများကို ပြန်လည်တွက်ချက်ခြင်းနှင့် မတူညီသော၊ ပိုကြီးသော cell အရွယ်အစားသို့ ကူးပြောင်းခြင်းများပြုလုပ်ခြင်းကို ဆိုလိုပါသည်) ပြုလုပ်ရန်အတွက် အသုံးပြုနိုင်ပါသည်။

Algorithm သည် input raster ၏ data အမျိုးအစားအတိုင်း ထိန်းသိမ်းထားရှိပါသည်။ ထို့အတွက်ကြောင့် byte/integer raster များကို base n တစ်ခု၏ မြှောက်ကိန်း (multiples) များသို့သာ round ပြုလုပ်နိုင်မည်ဖြစ်ပါသည်။ သို့မဟုတ်ပါက သတိပေးချက်တစ်ခု ပေါ်လာမည်ဖြစ်ပြီး raster သည် byte/integer raster အဖြစ် ကော်ပီကူးယူခြင်းခံရမည်ဖြစ်ပါသည်။

.. figure:: img/round_raster.png
  :align: center

  Raster တစ်ခု၏ တန်ဖိုးများကို Round ပြုလုပ်ခြင်း


Parameters (သတ်မှတ်ချက်များ)
.............................

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
   * - **Input Raster** **(ထည့်သွင်းအသုံးပြုသော raster)** 
     - ``INPUT`` 
     - [raster]
     - လုပ်ဆောင်ရန် (process) raster
   * - **Band number** **(Band နံပါတ်)** 
     - ``BAND``
     - [number]

       Default: 1
     - Raster ၏ band
   * - **Rounding direction** **(Rounding ပြုလုပ်မည့် ဦးတည်ချက်)**
     - ``ROUNDING_DIRECTION``
     - [list]

       Default: 1
     - ရည်မှန်းထားသည့် round ပြုလုပ်ပြီးရရှိလာမည့်တန်ဖိုးကို မည်ကဲ့သို့ ရွေးချယ်မည်ကို သတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာများမှာ- 

       * 0 --- Round up (တိုးယူခြင်း)
       * 1 --- Round to nearest (အနီးစပ်ဆုံးယူခြင်း)
       * 2 --- Round down (လျော့ယူခြင်း)
   * - **Number of decimals places** **(ဒဿမနေရာများအရေအတွက်)**
     - ``DECIMAL_PLACES``
     - [number]

       Default: 2
     - Round ပြုလုပ်မည့် ဒသမနေရာအရေအတွက်။ Cell တန်ဖိုးများကို base n တစ်ခု၏ မြှောက်ကိန်း (multiple) သို့ round ပြုလုပ်ရန် အနုတ်တန်ဖိုးများကို အသုံးပြုပါ။ 
   * - **Output raster** 
     - ``OUTPUT``
     - [raster]

       Default : ``[Save to temporary file]``
     - Output file ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types** 
          :end-before: **end_file_output_types** 


Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Base n for rounding to multiples of n** **(n ၏ ဆတိုးကိန်းသို့ rounding ပြုလုပ်ခြင်းအတွက် Base n)** 
     - ``BASE_N``
     - [number]

       Default : 10
     - ``DECIMAL_PLACES`` (ဒဿမကိန်းနေရာများ) ဆိုသည့် parameter သည် အနုတ်ဖြစ်နေသည့်အခါတွင် raster တန်ဖိုးများကို Base n တန်ဖိုး၏ ဆတိုးကိန်း (multiples) သို့ round ပြုလုပ်မည်ဖြစ်ပါသည်။


Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output raster**
     - ``OUTPUT``
     - [raster]
     - ရွေးချယ်ထားသည့် band အတွက် round ပြုလုပ်ထားသည့် တန်ဖိုးများပါရှိသည့် output raster layer

Python code
............

**Algorithm ID**: ``native:roundrastervalues``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisrastersampling:

Sample raster values (Raster တန်ဖိုးများကို နမူနာယူခြင်း)
----------------------------------------------------------

အမှတ်တည်နေရာများ (point locations) ၌ raster တန်ဖိုးများကို ထုတ်နှုတ် (Extract) ပေးပါသည်။ အကယ်၍ raster layer သည် multiband (Band များစွာ) ဖြစ်ပါက band တစ်ခုချင်းစီကို နမူနာယူမည်ဖြစ်ပါသည်။

ရရှိလာသည့် layer ၏ အချက်အလက်ဇယား (attribute table) သည် raster layer band count (band အရေအတွက်) များအတိုင်း column အသစ်များပါရှိလိမ့်မည်ဖြစ်ပါသည်။

Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 30 20 20 30

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input Raster** **(ထည့်သွင်းအသုံးပြုသော layer)** 
     - ``INPUT`` 
     - [vector: point]
     - နမူနာကောက်ယူခြင်း (sampling) အတွက် အသုံးပြုမည့် Point vector layer 
   * - **Raster Layer**
     - ``RASTERCOPY``
     - [raster]
     - ပေးထားသည့် အမှတ်တည်နေရာ၌ နမူနာကောက်ယူရန် Raster layer
   * - **Output column prefix** **(ရလာဒ် column ၏ရှေ့ဆက်စာလုံး)**
     - ``COLUMN_PREFIX``
     - [string]

       Default : 'SAMPLE\_'
     - ပေါင်းထည့်ထားသည့် column များ၏ အမည်များအတွက် ရှေ့ဆက်စာလုံး (prefix)
   * - **Sampled** **(နမူနာယူထားပြီးသော)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``OUTPUT``
     - [vector: point]

       Default: ``[Create temporary layer]``
     - နမူနာကောက်ယူထားသည့် တန်ဖိုးများပါဝင်သော output layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Sampled** **(နမူနာယူထားပြီးသော)**
     - ``OUTPUT``
     - [vector: point]
     - နမူနာကောက်ယူထားသည့်တန်ဖိုးများပါဝင်သည့် output layer

Python code
............

**Algorithm ID**: ``native:rastersampling``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiszonalhistogram:

Zonal histogram (ဇုန်အလိုက်ပြသသော ဟစ်စတိုဂရမ်/ကြိမ်နှုန်းပြဂရပ်)
-----------------------------------------------------------------

Polygon feature များအတွင်းပါဝင်သော raster layer တစ်ခုမှ သိသာထင်ရှားသည့် (unique) တန်ဖိုးတစ်ခုချင်းစီ၏ အရေအတွက်ကို ကိုယ်စားပြုဖော်ပြသည့် field များ ဆက်တွဲပေါင်းထည့် (append) ပေးပါသည်။

Output layer attribute တွင်ပါရှိမည့် field အရေအတွက်သည် polygon (များ)နှင့် အပြန်အလှန်ဖြတ်သော raster layer ၏ သိသာထင်ရှားတန်ဖိုးများ (unique values) အတိုင်း ရှိပါလိမ့်မည်။ 

.. figure:: img/raster_histogram.png
  :align: center

  Raster layer histogram ဥပမာ


Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Raster layer**
     - ``INPUT_RASTER``
     - [raster]
     - Input raster layer
   * - **Band number** **(Band နံပါတ်)**
     - ``RASTER_BAND``
     - [raster band]

       Default: Input layer ၏ ပထမ Band
     - Raster သည် multiband (Band များစွာ) ဖြစ်ပါက band တစ်ခုကို ရွေးချယ်ပါ။ 
   * - **Vector layer containing zones** **(ဇုန်များပါဝင်သည့် Vector layer)**
     - ``INPUT_VECTOR``
     - [vector: polygon]
     - ဇုန်များသတ်မှတ်သည့် Vector polygon layer
   * - **Output column prefix** **(ရလာဒ် column ၏ရှေ့ဆက်စာလုံး)**
     - ``COLUMN_PREFIX``

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - [string]

       Default: 'HISTO\_'
     - Output column အမည်များအတွက် ရှေ့ဆက် (Prefix)
   * - **Output zones** **(ရလာဒ်ဇုန်များ)**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output vector polygon layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Output zones** **(ရလာဒ်ဇုန်များ)**
     - ``OUTPUT`` (ရလာဒ်)
     - [vector: polygon]
     - Output vector polygon layer


Python code
............

**Algorithm ID**: ``native:zonalhistogram``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiszonalstatisticsfb:

Zonal statistics (ဇုန်အလိုက် စာရင်းအင်းအချက်အလက်များ)
------------------------------------------------------

Overlapping (တစ်ခုနှင့်တစ်ခုထပ်နေသော) ဖြစ်နေသည့် polygon vector layer တစ်ခု၏ feature တစ်ခုချင်းစီအတွက် raster layer တစ်ခု၏ စာရင်းအင်းအချက်အလက်များ (statistics) ကို တွက်ချက်ပေးပါသည်။ 


Parameters (သတ်မှတ်ချက်များ)
......................... 

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
     - [vector: polygon]
     - ဇုန်များပါဝင်သည့် Vector polygon layer
   * - **Raster layer**
     - ``INPUT_RASTER``
     - [raster]
     - Input raster layer
   * - **Raster band**
     - ``RASTER_BAND``
     - [raster band]

       Default: Input layer ၏ ပထမ band
     - Raster သည် multiband (Band များစွာ) ဖြစ်ပါက စာရင်းအင်းတွက်ချက်မှုများအတွက် band တစ်ခုကို ရွေးချယ်ပါ။ 
   * - **Output column prefix** **(ရလာဒ် column ၏ရှေ့ဆက်စာလုံး)**
     - ``COLUMN_PREFIX``
     - [string] 
       Default: '_'
     - Output column အမည်များအတွက် ရှေ့ဆက် (Prefix)
   * - **Statistics to calculate** **(တွက်ချက်မှုများပြုလုပ်ရန် စာရင်းအင်းအချက်အလက်များ)**
     - ``STATISTICS``
     - [enumeration] [list]

       Default: [0,1,2]
     - Output အတွက် စာရင်းဆိုင်ရာတွက်ချက်မှုလုပ်ဆောင်သည့် (statistical) operator စာရင်း။ ရွေးချယ်စရာများမှာ-

       * 0 --- Count (အရေအတွက်)
       * 1 --- Sum (ပေါင်းလဒ်)
       * 2 --- Mean (သမတ်ကိန်း)
       * 3 --- Median (တစ်ဝက်ကိန်း)
       * 4 --- St. dev. (စံတိမ်းချက်)
       * 5 --- Minimum (အနည်းဆုံး)
       * 6 --- Maximum (အများဆုံး)
       * 7 --- Range (အပိုင်းအခြား)
       * 8 --- Minority (အနည်းစုဖြစ်သော)
       * 9 --- Majority (အများစုဖြစ်သော)
       * 10 --- Variety (မျိုးစုံမှု)
       * 11 --- Variance (ကွဲလွဲချက်)
   * - **Zonal Statistics**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer]``
     - Output vector polygon layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Zonal Statistics** 

     - ``OUTPUT``
     - [vector: polygon]
     - စာရင်းအင်းအချက်အလက်များထပ်မံထည့်သွင်းထားသည့် zone vector layer 

Python code
............

**Algorithm ID**: ``native:zonalstatisticsfb``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. |gaussian_formula| image:: img/fuzzy_gaussian_formula.png
   :height: 1.5em
.. |fuzzy_large_formula| image:: img/fuzzy_large_formula.png
   :height: 3.2em
.. |fuzzy_linear_formula| image:: img/fuzzy_linear_formula.png
   :height: 3.8em
.. |near_formula| image:: img/fuzzy_near_formula.png
   :height: 2.5em
.. |power_formula| image:: img/fuzzy_power_formula.png
   :height: 4.4em
.. |small_formula| image:: img/fuzzy_small_formula.png
   :height: 3.2em
