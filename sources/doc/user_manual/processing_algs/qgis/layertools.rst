Layer tools (Layer ဆိုင်ရာ ကိရိယာတန်ဆာပလာများ)
===============================================

.. only:: html

   .. contents::
      :local:
      :depth: 1


.. _qgisexportlayersinformation:

Export layer(s) information (Layer များ၏ သတင်းအချက်အလက်များကို ထုတ်ယူခြင်း)
----------------------------------------------------------------------------

ရွေးချယ်ထားသော layer များ၏နယ်ပယ်အကျယ်အဝန်း (extent) နှင့် သက်ဆိုင်သော feature များပါဝင်သော polygon layer တစ်ခုကိုဖန်တီးပေးပါသည်။

ထပ်ဆောင်း layer ၏အသေးစိတ်အချက်အလက်များ (CRS၊ provider နာမည်၊ file လမ်းကြောင်း၊ layer နာမည်၊ subset စစ်ထုတ်ပေးမှု၊ အနှစ်ချုပ် နှင့် အချက်အလက်များ) ကို feature တစ်ခုချင်းစီတွင် attribute များအဖြစ် ပူးတွဲထားပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layers** (**ထည့်သွင်းအသုံးပြုသော layer များ**)
     - ``LAYERS``
     - [vector: any] [list]
     - သတင်းအချက်အလက်များကို ရယူရန် input vector layer များ
   * - **Output** (**ရလာဒ်များ**)
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer] ([ယာယီ layer ဖန်တီးပါ])``
     - သတင်းအချက်အလက်များပါသော output layer ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Output**
     - ``OUTPUT``
     - [vector: polygon]
     - Input layer များ၏ extent ကိုပြသသော polygon vector layer နှင့် attribute များထဲရှိ ဆက်စပ်သတင်းအချက်အလက်များ

Python code
............

**Algorithm ID**: ``native:exportlayersinformation``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisexporttospreadsheet:

Export to spreadsheet (spreadsheet သို့ထုတ်ယူခြင်း)
----------------------------------------------------

ရွေးချယ်ထားသော vector layer များ၏ attribute များကို spreadsheet document တစ်ခုအဖြစ်ထုတ်ယူပေး သို့မဟုတ် ရှိနေပြီးသား spreadsheet တစ်ခုထဲသို့ sheet အသစ်များအဖြစ် ဆက်တွဲပေါင်းထည့်ပေးပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layers** (**ထည့်သွင်းအသုံးပြုသော layer များ**)
     - ``LAYERS``
     - [vector: any] [list]
     - Input vector layer များ။ Output spreadsheet တွင် layer တစ်ခုချင်းစီအတွက် ၎င်း layer ၏ attribute များပါဝင်သော sheed တစ်ခုပါဝင်ပါလိမ့်မည်။
   * - **Use field aliases as column headings** (**Field အမည်ပို များကို column ခေါင်းစဉ်များအဖြစ် အသုံးပြုခြင်း**)
     - ``USE_ALIAS``
     - [boolean]

       Default: False
     - Attribute ဇယားမှ field alias (အမည်ပို) များကို spreadsheet အတွက် အသုံးပြုခြင်း။
   * - **Export formatted values instead of raw values** (**Raw တန်ဖိုးများအစား format ချထားသော တန်ဖိုးများကို ထုတ်ယူခြင်း**)
     - ``FORMATTED_VALUES``
     - [boolean]

       Default: False
     - ``True`` ဖြစ်လျှင် format ချထားပြီး လူများဖတ်ရှုနိုင်သော (ဥပမာ- :ref:`တန်ဖိုးမြေပုံ သို့မဟုတ် တန်ဖိုးချိတ်ဆက်မှု <edit_widgets>` တစ်ခုမှ) တန်ဖိုးများကို spreadsheet ထဲသို့ ထုတ်ပေးပါသည်။
   * - **Overwrite existing spreadsheet** (**ရှိနေပြီးသား spreadsheet ကိုအစားထိုးရေးသားခြင်း**)
     - ``OVERWRITE``
     - [boolean]

       Default: True
     - သတ်မှတ်ထားသော spreadsheet ရှိနေပြီသားဖြစ်ပြီး ယခု setting ကို ``True`` အဖြစ်ထားလျှင် ရှိနေပြီးသား spreadsheet ကိုအစားထိုးရေးသားပါမည်။ ``False`` အဖြစ်ထားပြီး spreadsheet သည် ရှိနေပြီးသားဖြစ်လျှင် layer များကို sheet အသစ်များအဖြစ် ဆက်တွဲပေါင်းထည့်ပါမည်။

   * - **Destination spreadsheet** (**spreadsheet တည်နေရာ**)
     - ``OUTPUT``
     - [file]

       Default: ``[Save to temporary file] ([ယာယီ file ထဲတွင်သိမ်းဆည်းပါ])``
     - Layer တိုင်းအတွက် sheet တစ်ခုပါဝင်သော output spreadsheet ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည်-

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
   * - **Destination spreadsheet** (**spreadsheet တည်နေရာ**)
     - ``OUTPUT``
     - [file]
     - Layer တိုင်းအတွက် sheet တစ်ခုပါဝင်သော spreadsheet
   * - **Layers within spreadsheet** (**spreadsheet အတွင်းရှိ layer များ**)
     - ``OUTPUT_LAYERS``
     - [list]
     - Spreadsheet ထဲသို့ ပေါင်းထည့်ထားသော sheet များစာရင်း

Python code
............

**Algorithm ID**: ``native:exporttospreadsheet``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgispolygonfromlayerextent:

Extract layer extent (Layer ၏ နယ်ပယ်အကျယ်အဝန်းကို ဆွဲထုတ်ခြင်း)
----------------------------------------------------------------

Input feature များအားလုံးကို ခြုံလွှမ်းနိုင်သော အသေးဆုံး bounding box (စတုဂံပုံနယ်ပယ်အကျယ်အဝန်း)  (တောင်-မြောက် မျက်နှာမူရာဖြင့် ထောင့်မှန်စတုဂံ) တစ်ခုဖြင့် vector layer တစ်ခုကို ဖန်တီးပေးပါသည်။

Output layer တွင် input layer တစ်ခုလုံးအတွက် bounding box (စတုဂံပုံနယ်ပယ်အကျယ်အဝန်း) တစ်ခု ပါဝင်ပါသည်။

.. figure:: img/extract_layer_extent.png
   :align: center

   Source layer ၏ bounding box ကိုအနီရောင်ဖြင့်ဖော်ပြထားပါသည်

**Default menu** - :menuselection:`Vector --> Research Tools`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Layer**
     - ``INPUT``
     - [layer]
     - ထည့်သွင်းအသုံးပြုသော layer
   * - **Extent** (**နယ်ပယ်အကျယ်အဝန်း**)
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer] ([ယာယီ layer ဖန်တီးပါ])``
     - Output extent အတွက် polygon vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   *  - **Extent** (**နယ်ပယ်အကျယ်အဝန်း**)
      - ``OUTPUT``
      - [vector: polygon]
      - Extent ဖြင့် output (polygon) vector layer (အသေးဆုံး bounding box)

Python code
............

**Algorithm ID**: ``qgis:polygonfromlayerextent``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**
