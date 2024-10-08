Raster Creation (Raster ဖန်တီးခြင်း) 
======================================

.. only:: html

   .. contents::
      :local:
      :depth: 1


.. _qgiscreateconstantrasterlayer:

Create constant raster layer (ပုံသေ raster layer ဖန်တီးခြင်း)
--------------------------------------------------------------

ပေးထားသည့် အကျယ်အဝန်းနယ် (extent) နှင့် သတ်မှတ်ထားသည့်တန်ဖိုးဖြင့် ဖြည့်ထားသော cell အရွယ်အစားအတွက် raster layer တစ်ခုကို ဖန်တီးပေးပါသည်။ 

ထို့အပြင် output data အမျိုးအစားတစ်ခုကို သတ်မှတ်ပေးနိုင်ပါသည်။ အကယ်၍ ရွေးချယ်ထားသော (selected) output raster data အမျိုးအစားဖြင့် ကိုယ်စားပြုဖော်ပြနိုင်ခြင်းမရှိသည့် တန်ဖိုးတစ်ခုကို ထည့်သွင်းထားပါက algorithm သည် ပျက်ပြယ်သွားမည်ဖြစ်ပါသည်။


Parameters (သတ်မှတ်ချက်များ)
.............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Desired extent** **(အလိုရှိသည့် အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [extent]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent) ကို သတ်မှတ်ပေးပါသည်။ ၎င်းသည် tile အရွယ်အစား အများအပြားအဖြစ် အတွင်းပိုင်း (internal) တွင် တိုးချဲ့ (extend) ပေးသွားမည်ဖြစ်ပါသည်။ ရရှိနိုင်သောနည်းလမ်းများမှာ-

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Target CRS** **(ဦးတည်သည့် CRS)**
     - ``TARGET_CRS``
     - [crs]

       Default: Project CRS
     - Output raster layer အတွက် ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (CRS)
   * - **Pixel size** **(Pixel အရွယ်အစား)**
     - ``PIXEL_SIZE``
     - [number]

       Default: 1.0
     - မြေပုံယူနစ်များဖြင့် Pixel အရွယ်အစား (X=Y) 
   * - **Constant value** **(ပုံသေတန်ဖိုး)**
     - ``NUMBER``
     - [number]

       Default: 1
     - Output raster layer အတွက် ပုံသေ pixel တန်ဖိုး 
   * - **Constant**
     - ``OUTPUT``
     - [raster]

       Default : ``[Save to temporary file]``
     - output raster ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Output raster data type** **(ရလာဒ် raster layer အမျိုးအစား)**
     - ``OUTPUT_TYPE``

       Default: 5
     - [enumeration]
     - Output raster file ၏ data အမျိုးအစားကို သတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာများမှာ-

       * 0 --- Byte
       * 1 --- Integer16
       * 2 --- Unsigned Integer16
       * 3 --- Integer32
       * 4 --- Unsigned Integer32
       * 5 --- Float32
       * 6 --- Float64

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Constant**
     - ``OUTPUT``
     - [raster]
     - အလိုရှိသည့် အကျယ်အဝန်းနယ် (extent) ကို လွှမ်းခြုံမှုရှိ‌ပြီး သတ်မှတ်ထားသော pixel အရွယ်အစားနှင့် တန်ဖိုးပါရှိသော Raster

Python code
............

**Algorithm ID**: ``native:createconstantrasterlayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiscreaterandombinomialrasterlayer:

Create random raster layer (binomial distribution) (ကျပန်း raster layer ဖန်တီးခြင်း (ဒွိစုံဖြစ်တန်စွမ်း ပြန့်နှံ့မှု))
-----------------------------------------------------------------------------------------------------------------------

ပေးထားသည့် အကျယ်အဝန်းနယ် (extent) နှင့် binomial အရ distribute (ပြန့်နှံ့) ဖြစ်နေသော ကျပန်းတန်ဖိုးများဖြင့် ဖြည့်ထားသော cell အရွယ်အစားအတွက် raster layer တစ်ခုကို ဖန်တီးပေးပါသည်။ 

Default အားဖြင့် တန်ဖိုးများကို N တန်ဖိုး 10 နှင့် ဖြစ်တန်စွမ်း (probability) 0.5 ပေးပြီး ရွေးချယ်မည်ဖြစ်ပါသည်။ ၎င်းကို N နှင့် ဖြစ်တန်စွမ်း (probability) အတွက် အဆင့်မြင့် parameter ကို အသုံးပြုပြီး အစားထိုးရေးသားနိုင်ပါသည်။ Raster data အမျိုးအစား ကို Integer အမျိုးအစားများ (Default အားဖြင့် Integer16) သို့ သတ်မှတ်ပါသည်။ Binomial distribution ကျပန်းတန်ဖိုးများကို အပေါင်းကိန်းပြည့် (positive integer) များအဖြစ် သတ်မှတ်ပါသည်။ Floating point raster (ဆဲလ်တစ်ခုချင်းစီ၏ တန်ဖိုးများကို ဒဿမကိန်းများဖြင့်သိမ်းဆည်းထားသော နံပါတ်များပါဝင်သည့် raster) တစ်ခုသည် ကိန်းပြည့်တန်ဖိုးအုပ်စုတစ်ခု (a cast of integer values) ကို floating point သို့ကိုယ်စားပြုဖော်ပြမည်ဖြစ်ပါသည်။

Parameters (သတ်မှတ်ချက်များ)
.............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Desired extent** **(အလိုရှိသည့် အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [extent]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent) ကို သတ်မှတ်ပေးပါသည်။ ၎င်းသည် tile အရွယ်အစား အများအပြားအဖြစ် အတွင်းပိုင်း (internal) တွင် တိုးချဲ့ (extend) ပေးသွားမည်ဖြစ်ပါသည်။ ရရှိနိုင်သောနည်းလမ်းများမှာ-

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Target CRS** **(ဦးတည်သည့် CRS)**
     - ``TARGET_CRS``
     - [crs]

       Default: Project CRS
     - Output raster layer အတွက် ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (CRS)
   * - **Pixel size** **(Pixel အရွယ်အစား)**
     - ``PIXEL_SIZE`` 
     - [number]

       Default: 1.0
     - မြေပုံယူနစ်များဖြင့် Pixel အရွယ်အစား (X=Y) 
   * - **Output raster**
     - ``OUTPUT``
     - [raster]

       Default : ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output raster data type** **(Output raster data အမျိုးအစား)**
     - ``OUTPUT_TYPE``

       Default: 5
     - [enumeration]
     - Output raster file ၏ data အမျိုးအစားကို သတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာများမှာ-

       * 0 --- Integer16
       * 1 --- Unsigned Integer16
       * 2 --- Integer32
       * 3 --- Unsigned Integer32
       * 4 --- Float32
       * 5 --- Float64
   * - **N**
     - ``N``
     - [number]

       Default: 10
     -
   * - **Probability** **(ဖြစ်တန်စွမ်း)**
     - ``PROBABILITY`` 
     - [number]

       Default: 0.5
     -

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
     - အလိုရှိသည့် အကျယ်အဝန်းနယ် (extent) ကို လွှမ်းခြုံမှုရှိ‌ပြီး ကျပန်းပျံ့နှံ့နေသည့်တန်ဖိုးများဖြင့် (randomly distributed values) ဖြည့်ထားသည့် cell များပါဝင်သော Raster

Python code
............

**Algorithm ID**: ``native:createrandombinomialrasterlayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiscreaterandomexponentialrasterlayer:

Create random raster layer (exponential distribution) (ကျပန်း raster layer ဖန်တီးခြင်း (ထပ်ကိန်း ပြန့်နှံ့မှု))
----------------------------------------------------------------------------------------------------------------

ပေးထားသည့် အကျယ်အဝန်းနယ် (extent) နှင့် exponential အရ distribute (ပြန့်နှံ) ဖြစ်နေသော ကျပန်းတန်ဖိုးဖြင့် ဖြည့်ထားသော cell အရွယ်အစားအတွက် raster layer တစ်ခုကို ဖန်တီးပေးပါသည်။ 

Default အားဖြင့် တန်ဖိုးများကို lambda 1.0 ပေးပြီး ရွေးချယ်မည်ဖြစ်ပါသည်။ ၎င်းကို lambda အတွက်  အဆင့်မြင့် parameter ကို အသုံးပြုပြီး အစားထိုးရေးသားနိုင်ပါသည်။ Exponential distribution ကျပန်းတန်ဖိုးများသည် floating point numbers (ဒဿမကိန်းများပါဝင်သည့် ကိန်းဂဏန်းများ) ဖြစ်သည့်အတွက် raster data အမျိုးအစားကို default အားဖြင့် Float32 သို့ သတ်မှတ်ပါသည်။


Parameters (သတ်မှတ်ချက်များ)
.............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Desired extent** **(အလိုရှိသည့် အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [extent]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent) ကို သတ်မှတ်ပေးပါသည်။ ၎င်းသည် tile အရွယ်အစား အများအပြားအဖြစ် အတွင်းပိုင်း (internal) တွင် တိုးချဲ့ (extend) ပေးသွားမည်ဖြစ်ပါသည်။ ရရှိနိုင်သောနည်းလမ်းများမှာ-

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Target CRS** **(ဦးတည်သည့် CRS)**
     - ``TARGET_CRS``
     - [crs]

       Default: Project CRS
     - Output raster layer အတွက် ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (CRS)
   * - **Pixel size** **(Pixel အရွယ်အစား)**
     - ``PIXEL_SIZE`` 
     - [number]

       Default: 1.0
     - မြေပုံယူနစ်များဖြင့် Pixel အရွယ်အစား (X=Y) 
   * - **Output raster**
     - ``OUTPUT``
     - [raster]

       Default : ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Output raster data type** **(Output raster data အမျိုးအစား)**
     - ``OUTPUT_TYPE``

       Default: 0
     - [enumeration]
     - Output raster file ၏ data အမျိုးအစားကို သတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာများမှာ-

       * 0 --- Float32
       * 1 --- Float64
   * - **Lambda**
     - ``LAMBDA``
     - [number]

       Default: 1.0
     -

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
     - အလိုရှိသည့် အကျယ်အဝန်းနယ် (extent)ကို လွှမ်းခြုံမှုရှိ‌ပြီး ကျပန်းပျံ့နှံ့နေသည့်တန်ဖိုးများဖြင့်(randomly distributed values) ဖြည့်ထားသည့် cell အရွယ်အစားပါဝင်သော Raster
     

Python code
............

**Algorithm ID**: ``native:createrandomexponentialrasterlayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiscreaterandomgammarasterlayer:

Create random raster layer (gamma distribution) (ကျပန်း raster layer ဖန်တီးခြင်း (gamma ပြန့်နှံ့မှု))
-------------------------------------------------------------------------------------------------------

ပေးထားသည့် အကျယ်အဝန်းနယ် (extent) နှင့် gamma ဖြင့် distribute (ပြန့်နှံ့) ဖြစ်နေသော ကျပန်းတန်ဖိုးများဖြင့် ဖြည့်ထားသော cell အရွယ်အစားအတွက် raster layer တစ်ခုကို ဖန်တီးပေးပါသည်။ 

Default အားဖြင့် တန်ဖိုးများကို alpha နှင့် beta တန်ဖိုး 1.0 ပေးပြီး ရွေးချယ်မည်ဖြစ်ပါသည်။ ၎င်းကို alpha နှင့် beta အတွက် အဆင့်မြင့် parameter ကို အသုံးပြုပြီး အစားထိုးရေးသားနိုင်ပါသည်။ Gamma distribution ကျပန်းတန်ဖိုးများသည် floating point numbers (ဒဿမကိန်းများပါဝင်သည့် ကိန်းဂဏန်းများ) ဖြစ်သည့်အတွက် raster data အမျိုးအစားကို default အားဖြင့် Float32 သို့ သတ်မှတ်ပါသည်။

Parameters (သတ်မှတ်ချက်များ)
.............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Desired extent** **(အလိုရှိသည့် အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [extent]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent) ကို သတ်မှတ်ပေးပါသည်။ ၎င်းသည် tile အရွယ်အစား အများအပြားအဖြစ် အတွင်းပိုင်း (internal) တွင် တိုးချဲ့ (extend) ပေးသွားမည်ဖြစ်ပါသည်။ ရရှိနိုင်သောနည်းလမ်းများမှာ-

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Target CRS** **(ဦးတည်သည့် CRS)**
     - ``TARGET_CRS``
     - [crs]

       Default: Project CRS
     - Output raster layer အတွက် ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (CRS)
   * - **Pixel size** **(Pixel အရွယ်အစား)**
     - ``PIXEL_SIZE`` 
     - [number]

       Default: 1.0
     - မြေပုံယူနစ်များဖြင့် Pixel အရွယ်အစား (X=Y) 
   * - **Output raster**
     - ``OUTPUT``
     - [raster]

       Default : ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Output raster data type** 
     - ``OUTPUT_TYPE``

       ပုံသေ: 0
     - [enumeration]
     - Output raster ဖိုင် ၏ data အမျိုးအစားကို သတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာများမှာ-

       * 0 --- Float32
       * 1 --- Float64
   * - **Alpha**
     - ``ALPHA``
     - [number]

       Default: 1.0
     -
   * - **Beta**
     - ``BETA``
     - [number]

       Default: 1.0
     -

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **output(အထွက်) raster** **(Output raster data အမျိုးအစား)**
     - ``OUTPUT``
     - [raster]
     - အလိုရှိသည့် အကျယ်အဝန်းနယ်(extent)ကို လွှမ်းခြုံမှုရှိ‌ပြီး ကျပန်းပျံ့နှံ့နေသည့်တန်ဖိုးများဖြင့်(randomly distributed values) ဖြည့်ထားသည့် ဆဲလ်အရွယ်အစားရှိသော Raster

Python code
............

**Algorithm ID**: ``native:createrandomgammarasterlayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiscreaterandomgeometricrasterlayer:

Create random raster layer (geometric distribution) (ကျပန်း raster layer ဖန်တီးခြင်း (ဂျီဩမေတြီနှင့်ဆိုင်သော ပြန့်နှံ့မှု))
----------------------------------------------------------------------------------------------------------------------------

ပေးထားသည့် အကျယ်အဝန်းနယ် (extent) နှင့် ဂျီဩမေတြီ အရ distribute (ပြန့်နှံ့) ဖြစ်နေသော ကျပန်းတန်ဖိုးများဖြင့် ဖြည့်ထားသော cell အရွယ်အစားအတွက် raster layer တစ်ခုကို ဖန်တီးပေးပါသည်။ 

Default အားဖြင့် တန်ဖိုးများကို ဖြစ်တန်စွမ်း (probability) 0.5 ပေးပြီး ရွေးချယ်မည်ဖြစ်ပါသည်။ ၎င်းကို သမတ်ကိန်းတန်ဖိုး (mean value) အတွက် အဆင့်မြင့် parameter ကို အသုံးပြုပြီး အစားထိုးရေးသားနိုင်ပါသည်။ Raster data အမျိုးအစားကို Integer အမျိုးအစားများ (default အားဖြင့် Integer16) သို့ သတ်မှတ်ပါသည်။ Geometric distribution ကျပန်းတန်ဖိုးများကို အပေါင်းကိန်းပြည့်များအဖြစ် သတ်မှတ်ပါသည်။ Floating point raster တစ်ခုသည် ကိန်းပြည့်တန်ဖိုးအုပ်စုတစ်ခု (a cast of integer values) ကို floating point သို့ ကိုယ်စားပြုဖော်ပြမည်ဖြစ်ပါသည်။

Parameters (သတ်မှတ်ချက်များ)
.............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Desired extent** **(အလိုရှိသည့် အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [extent]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent) ကို သတ်မှတ်ပေးပါသည်။ ၎င်းသည် tile အရွယ်အစား အများအပြားအဖြစ် အတွင်းပိုင်း (internal) တွင် တိုးချဲ့ (extend) ပေးသွားမည်ဖြစ်ပါသည်။ ရရှိနိုင်သောနည်းလမ်းများမှာ-

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Target CRS** **(ဦးတည်သည့် CRS)**
     - ``TARGET_CRS``
     - [crs]

       Default: Project CRS
     - Output raster layer အတွက် ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (CRS)
   * - **Pixel size** **(Pixel အရွယ်အစား)**
     - ``PIXEL_SIZE`` 
     - [number]

       Default: 1.0
     - မြေပုံယူနစ်များဖြင့် Pixel အရွယ်အစား (X=Y) 
   * - **Output raster**
     - ``OUTPUT``
     - [raster]

       Default : ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Output raster data type** **(Output raster data အမျိုးအစား)**
     - ``OUTPUT_TYPE`` 

       Default: 0
     - [enumeration]
     - Output raster file ၏ data အမျိုးအစားကို သတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာများမှာ-

       * 0 --- Integer16
       * 1 --- Unsigned Integer16
       * 2 --- Integer32
       * 3 --- Unsigned Integer32
       * 4 --- Float32
       * 5 --- Float64
   * - **Probability** **(ဖြစ်တန်စွမ်း)**
     - ``PROBABILITY``
     - [number]

       Default: 0.5
     -

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **output raster**
     - ``OUTPUT``
     - [raster]
     - အလိုရှိသည့် အကျယ်အဝန်းနယ် (extent) ကို လွှမ်းခြုံမှုရှိ‌ပြီး ကျပန်းပျံ့နှံ့နေသည့်တန်ဖိုးများဖြင့် (randomly distributed values) ဖြည့်ထားသည့် cell အရွယ်အစားပါဝင်သော Raster
  
Python code
............

**Algorithm ID**: ``native:createrandomgeometricrasterlayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiscreaterandomnegativebinomialrasterlayer:

Create random raster layer (negative binomial distribution) (ကျပန်း raster layer ဖန်တီးခြင်း (negative binomial distribution))
-------------------------------------------------------------------------------------------------------------------------------

ပေးထားသည့် အကျယ်အဝန်းနယ် (extent) နှင့် negative binomial အရ distribute (ပြန့်နှံ့) ဖြစ်သော ကျပန်းတန်ဖိုးများဖြင့် ဖြည့်ထားသော cell အရွယ်အစားအတွက် raster layer တစ်ခုကို ဖန်တီးပေးပါသည်။ 

Default အားဖြင့် ပြန့်နှံ့ခြင်းသတ်မှတ်ချက် k တန်ဖိုး 10.0 နှင့် ဖြစ်တန်စွမ်း (probability) 0.5 တစ်ခုကို ပေးပြီး ရွေးချယ်မည်ဖြစ်ပါသည်။ ၎င်းကို k နှင့် ဖြစ်တန်စွမ်း (probability) အတွက် အဆင့်မြင့် parameter ကို အသုံးပြုပြီး အစားထိုးရေးသားနိုင်ပါသည်။ Raster data အမျိုးအစားကို Integer အမျိုးအစားများ (ပုံသေအားဖြင့် Integer16) သို့ သတ်မှတ်ပါသည်။ Negative binomial distribution ကျပန်းတန်ဖိုးများကို အပေါင်းကိန်းပြည့်များအဖြစ် သတ်မှတ်ပါသည်။ Floating point raster တစ်ခုသည် ကိန်းပြည့်တန်ဖိုးအုပ်စုတစ်ခု (a cast of integer values) ကို floating point သို့ကိုယ်စားပြုဖော်ပြမည်ဖြစ်ပါသည်။


Parameters (သတ်မှတ်ချက်များ)
.............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Desired extent** **(အလိုရှိသည့် အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [extent]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent) ကို သတ်မှတ်ပေးပါသည်။ ၎င်းသည် tile အရွယ်အစား အများအပြားအဖြစ် အတွင်းပိုင်း (internal) တွင် တိုးချဲ့ (extend) ပေးသွားမည်ဖြစ်ပါသည်။ ရရှိနိုင်သောနည်းလမ်းများမှာ-

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Target CRS** **(ဦးတည်သည့် CRS)**
     - ``TARGET_CRS``
     - [crs]

       Default: Project CRS
     - Output raster layer အတွက် ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (CRS)
   * - **Pixel size** **(Pixel အရွယ်အစား)**
     - ``PIXEL_SIZE`` 
     - [number]

       Default: 1.0
     - မြေပုံယူနစ်များဖြင့် Pixel အရွယ်အစား (X=Y) 
   * - **Output raster**
     - ``OUTPUT``
     - [raster]

       Default : ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters
^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output raster data type** **(Output raster data အမျိုးအစား)**
     - ``OUTPUT_TYPE``

       Default: 0
     - [enumeration]
     - Output raster file ၏ data အမျိုးအစားကို သတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာများမှာ-

       * 0 --- Integer16
       * 1 --- Unsigned Integer16
       * 2 --- Integer32
       * 3 --- Unsigned Integer32
       * 4 --- Float32
       * 5 --- Float64
   * - **Distribution parameter k** **(ပြန့်နှံ့မှု parameter k)**
     - ``K_PARAMETER`` 
     - [number]

       Default: 10
     -
   * - **Probability** **(ဖြစ်တန်စွမ်း)**
     - ``PROBABILITY`` 
     - [number]

       Default: 0.5
     -

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
     - အလိုရှိသည့် အကျယ်အဝန်းနယ်ပယ်ကို လွှမ်းခြုံမှုရှိ‌ပြီး ကျပန်းပြန့်နှံ့နေသည့်တန်ဖိုးများဖြင့်(randomly distributed values) ဖြည့်ထားသည့် cell အရွယ်အစားပါဝင်သော Raster

Python code
............

**Algorithm ID**: ``native:createrandomnegativebinomialrasterlayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiscreaterandomnormalrasterlayer:

Create random raster layer (normal distribution) (ကျပန်း raster layer ဖန်တီးခြင်း (ပုံမှန်ပြန့်နှံ့ခြင်း))
-----------------------------------------------------------------------------------------------------------

ပေးထားသည့် အကျယ်အဝန်းနယ် (extent) နှင့် ပုံမှန်အရ distribute (ပြန့်နှံ့) ဖြစ်နေသော ကျပန်းတန်ဖိုးများဖြင့် ဖြည့်ထားသော cell အရွယ်အစားအတွက် raster layer တစ်ခုကို ဖန်တီးပေးပါသည်။ 

Default အားဖြင့် တန်ဖိုးများကို mean (သမတ်ကိန်း) 0.0 နှင့် standard deviation (စံတိမ်းချက်) 1.0 ပေးပြီး ရွေးချယ်မည်ဖြစ်ပါသည်။ ၎င်းကို mean (သမတ်ကိန်း) နှင့် standard deviation (စံတိမ်းချက်) အတွက် အဆင့်မြင့် parameter ကို အသုံးပြုပြီး အစားထိုးရေးသားနိုင်ပါသည်။ Normal distribution ကျပန်းတန်ဖိုးများသည် floating point numbers (ဒဿမကိန်းများပါဝင်သည့် ကိန်းဂဏန်းများ) များဖြစ်သည့်အတွက် raster data အမျိုးအစားကို default အားဖြင့် Float32 သို့ သတ်မှတ်ပါသည်။

Parameters (သတ်မှတ်ချက်များ)
.............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Desired extent** **(အလိုရှိသည့် အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [extent]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent) ကို သတ်မှတ်ပေးပါသည်။ ၎င်းသည် tile အရွယ်အစား အများအပြားအဖြစ် အတွင်းပိုင်း (internal) တွင် တိုးချဲ့ (extend) ပေးသွားမည်ဖြစ်ပါသည်။ ရရှိနိုင်သောနည်းလမ်းများမှာ-

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Target CRS** **(ဦးတည်သည့် CRS)**
     - ``TARGET_CRS``
     - [crs]

       Default: Project CRS
     - Output raster layer အတွက် ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (CRS)
   * - **Pixel size** **(Pixel အရွယ်အစား)**
     - ``PIXEL_SIZE`` 
     - [number]

       Default: 1.0
     - မြေပုံယူနစ်များဖြင့် Pixel အရွယ်အစား (X=Y) 
   * - **Output raster**
     - ``OUTPUT``
     - [raster]

       Default : ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Output raster data type** **(Output raster data အမျိုးအစား)**
     - ``OUTPUT_TYPE`` 

       Default: 0
     - [enumeration]
     - Output raster file ၏ data အမျိုးအစားကို သတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာများမှာ-

       * 0 --- Float32
       * 1 --- Float64
   * - **Mean of normal distribution** **(Normal distribution ၏ သမတ်ကိန်း)**
     - ``MEAN``
     - [number]

       Default: 0.0
     -
   * - **Standard deviation of normal distribution** **(Normal distribution ၏ စံတိမ်းချက်)**
     - ``STDDEV``
     - [number]

       Default: 1.0
     -

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
     - အလိုရှိသည့် အကျယ်အဝန်းနယ်ပယ်ကို လွှမ်းခြုံမှုရှိ‌ပြီး ကျပန်းပြန့်နှံ့နေသည့်တန်ဖိုးများဖြင့်(randomly distributed values) ဖြည့်ထားသည့် cell အရွယ်အစားပါဝင်သော Raster

Python code
............

**Algorithm ID**: ``native:createrandomnormalrasterlayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiscreaterandompoissonrasterlayer:

ကျပန်း raster layer ဖန်တီးခြင်း (poisson distribution)
-------------------------------------------------------

ပေးထားသည့် အကျယ်အဝန်းနယ် (extent) နှင့် poisson အရ distribute (ပြန့်နှံ့) ဖြစ်နေသော ကျပန်းတန်ဖိုးများဖြင့်ဖြည့်ထားသော cell အရွယ်အစားအတွက် raster layer တစ်ခုကို ဖန်တီးပေးပါသည်။ 

Default အားဖြင့် တန်ဖိုးများကို mean (သမတ်ကိန်း)  1.0 ပေးပြီး ရွေးချယ်မည်ဖြစ်ပါသည်။ ၎င်းကို mean value (သမတ်ကိန်းတန်ဖိုး) အတွက် အဆင့်မြင့် parameter ကို အသုံးပြုပြီး အစားထိုးရေးသားနိုင်ပါသည်။ Raster data အမျိုးအစားကို Integer (အပြည့်ကိန်း) အမျိုးအစားများသို့ (default အားဖြင့် Integer16) သတ်မှတ်ပါသည်။ Poisson distribution ကျပန်းတန်ဖိုးများသည် အပေါင်းကိန်းပြည့်များဖြစ်ပါသည်။ Floating point raster တစ်ခုသည် ကိန်းပြည့်တန်ဖိုးအုပ်စုတစ်ခု (a cast of integer values) ကို floating point သို့ ကိုယ်စားပြုဖော်ပြမည်ဖြစ်ပါသည်။

Parameters (သတ်မှတ်ချက်များ)
.............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^


.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Desired extent** **(အလိုရှိသည့် အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [extent]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent) ကို သတ်မှတ်ပေးပါသည်။ ၎င်းသည် tile အရွယ်အစား အများအပြားအဖြစ် အတွင်းပိုင်း (internal) တွင် တိုးချဲ့ (extend) ပေးသွားမည်ဖြစ်ပါသည်။ ရရှိနိုင်သောနည်းလမ်းများမှာ-

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Target CRS** **(ဦးတည်သည့် CRS)**
     - ``TARGET_CRS``
     - [crs]

       Default: Project CRS
     - Output raster layer အတွက် ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (CRS)
   * - **Pixel size** **(Pixel အရွယ်အစား)**
     - ``PIXEL_SIZE`` 
     - [number]

       Default: 1.0
     - မြေပုံယူနစ်များဖြင့် Pixel အရွယ်အစား (X=Y) 
   * - **Output raster**
     - ``OUTPUT``
     - [raster]

       Default : ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Output raster data type** **(Output raster data အမျိုးအစား)**
     - ``OUTPUT_TYPE``

       Default: 0
     - [enumeration]
     - Output raster file ၏ data အမျိုးအစားကို သတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာများမှာ-

       * 0 --- Integer16
       * 1 --- Unsigned Integer16
       * 2 --- Integer32
       * 3 --- Unsigned Integer32
       * 4 --- Float32
       * 5 --- Float64
   * - **Mean** **(သမတ်ကိန်း)**
     - ``MEAN``
     - [number]

       Default: 1.0
     -

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
     - အလိုရှိသည့် အကျယ်အဝန်းနယ်ပယ်ကို လွှမ်းခြုံမှုရှိ‌ပြီး ကျပန်းပြန့်နှံ့နေသည့်တန်ဖိုးများဖြင့်(randomly distributed values) ဖြည့်ထားသည့် cell အရွယ်အစားပါဝင်သော Raster

Python code
............

**Algorithm ID**: ``native:createrandompoissonrasterlayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiscreaterandomuniformrasterlayer:

Create random raster layer (uniform distribution) (ကျပန်း raster layer ဖန်တီးခြင်း (တစ်သမတ်တည်းရှိသော ပြန့်နှံ့မှု))
---------------------------------------------------------------------------------------------------------------------

ပေးထားသည့် အကျယ်အဝန်းနယ် (extent) နှင့် ကျပန်းတန်ဖိုးများဖြင့် ဖြည့်ထားသော cell အရွယ်အစားအတွက် raster layer တစ်ခုကို ဖန်တီးပေးပါသည်။ 

Default အားဖြင့် တန်ဖိုးများသည် သတ်မှတ်ထားသည့် output raster အမျိုးအစား၏ အနိမ့်ဆုံးနှင့် အမြင့်ဆုံးတန်ဖိုးအကြားတွင် ရှိပါသည်။ ၎င်းကို lower (အနိမ့်) နှင့် upper (အမြင့်) ကန့်သတ်တန်ဖိုး အတွက် အဆင့်မြင့် parameter ကို အသုံးပြုပြီး အစားထိုးရေးသားနိုင်ပါသည်။ အကယ်၍ bounds (ကန့်သတ်မှုများ) သည် တူညီသည့် တန်ဖိုးရှိပါက သို့မဟုတ် နှစ်မျိုးစလုံး သုည (default အားဖြင့်) ဖြစ်ပါက algorithm သည် ရွေးချယ်ထားသည့် raster data အမျိုးအစား၏ တန်ဖိုးအပြည့်အပိုင်းအခြားပမာဏ (full value range) ထဲတွင် ကျပန်းတန်ဖိုးများကို ဖန်တီးမည်ဖြစ်ပါသည်။ Output raster အမျိုးအစား၏ လက်ခံနိုင်သည့်အပိုင်းအခြားပမာဏ(acceptable range) အပြင်ဘက်ရှိ bounds များကို ရွေးချယ်ခြင်းသည် algorithm ကို ပျက်ပြယ်စေမည်ဖြစ်ပါသည်။

Parameters (သတ်မှတ်ချက်များ)
.............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^


.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Desired extent** **(အလိုရှိသည့် အကျယ်အဝန်းနယ်)**
     - ``EXTENT``
     - [extent]
     - Output raster layer ၏ တည်နေရာဆိုင်ရာအကျယ်အဝန်းနယ် (spatial extent) ကို သတ်မှတ်ပေးပါသည်။ ၎င်းသည် tile အရွယ်အစား အများအပြားအဖြစ် အတွင်းပိုင်း (internal) တွင် တိုးချဲ့ (extend) ပေးသွားမည်ဖြစ်ပါသည်။ ရရှိနိုင်သောနည်းလမ်းများမှာ-

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Target CRS** **(ဦးတည်သည့် CRS)**
     - ``TARGET_CRS``
     - [crs]

       Default: Project CRS
     - Output raster layer အတွက် ရည်ညွှန်းကိုဩဒိနိတ်စနစ် (CRS)
   * - **Pixel size** **(Pixel အရွယ်အစား)**
     - ``PIXEL_SIZE`` 
     - [number]

       Default: 1.0
     - မြေပုံယူနစ်များဖြင့် Pixel အရွယ်အစား (X=Y) 
   * - **Output raster**
     - ``OUTPUT``
     - [raster]

       Default : ``[Save to temporary file]``
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output raster data type** **(Output raster data အမျိုးအစား)**
     - ``OUTPUT_TYPE``

       Default: 5
     - [enumeration]
     - Output raster ဖိုင် ၏ data အမျိုးအစားကို သတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာများမှာ-

       * 0 --- Byte
       * 1 --- Integer16
       * 2 --- Unsigned Integer16
       * 3 --- Integer32
       * 4 --- Unsigned Integer32
       * 5 --- Float32
       * 6 --- Float64
   * - **Lower bound for random number range** **(ကျပန်းနံပါတ်အပိုင်းအခြားပမာဏအတွက် အနိမ့်ဆုံးတန်ဖိုး)**
     - ``LOWER_BOUND``
     - [number]

       Default: 0.0
     -
   * - **Upper bound for random number range** **(ကျပန်းနံပါတ်အပိုင်းအခြားပမာဏအတွက် အမြင့်ဆုံးတန်ဖိုး)**
     - ``UPPER_BOUND``
     - [number]

       Default: 0.0
     -

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
     - အလိုရှိသည့် အကျယ်အဝန်းနယ် (extent) ကို လွှမ်းခြုံမှုရှိ‌ပြီး ကျပန်းပြန့်နှံ့နေသည့်တန်ဖိုးများဖြင့် (randomly distributed values) ဖြည့်ထားသည့် cell အရွယ်အစားပါဝင်သော Raster

Python code
............

**Algorithm ID**: ``native:createrandomuniformrasterlayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**

