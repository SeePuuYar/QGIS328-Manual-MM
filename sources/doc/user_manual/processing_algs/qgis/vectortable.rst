Vector table (Vector ဆိုင်ရာ ဇယား)
===================================

.. only:: html

   .. contents::
      :local:
      :depth: 1


.. _qgisaddautoincrementalfield:

Add autoincremental field (အလိုအလျောက်တိုးလာသော field ပေါင်းထည့်ခြင်း)
-----------------------------------------------------------------------

Feature တစ်ခုချင်းစီအတွက် အစီအစဉ်တကျဖြစ်သောတန်ဖိုးတစ်ခုဖြင့် vector layer တစ်ခုထဲသို့ ဂဏန်းဆိုင်ရာ integer (ကိန်းပြည့်) field အသစ်တစ်ခု ပေါင်းထည့်ပေးပါသည်။။ 

အဆိုပါ field ကို layer ထဲရှိ feature များအတွက် unique ID တစ်ခုအဖြစ် အသုံးပြုနိုင်ပါသည်။ အချက်အလက် (attribute) အသစ်ကို input layer ထဲတွင် ပေါင်းထည့်မည်မဟုတ်ပဲ layer အသစ်တစ်ခု ပေါ်ထွက်လာမည်ဖြစ်သည်။

တိုးလာမည့်ကိန်းစဉ် အတွက် ကနဦးစတင်မည့်တန်ဖိုးကို သတ်မှတ်နိုင်ပါသည်။ အခြားနည်းအနေဖြင့် တိုးလာမည့်ကိန်းစဉ် ကို field များအုပ်စုဖွဲ့ခြင်းပေါ်တွင် အခြေခံနိုင်ပြီး feature များအတွက် sort order (မျိုးတူစုခြင်း အစီအစဉ်) ကိုလည်းသတ်မှတ်နိုင်ပါသည်။

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
   * - **Field name** **(Field အမည်)**
     - ``FIELD_NAME``
     - [string]

       Default: 'AUTO'
     - အလိုအလျောက်တိုးလာမည့် တန်ဖိုးများပါဝင်မည့် field ၏အမည်
   * - **Start values at** **(အစတန်ဖိုး)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``START``
     - [number]

       Default: 0
     - တိုးလာမည့်အရေအတွက်၏ ကနဦးဂဏန်းကို ရွေးချယ်ပါ
   * - **Modulus value** **(ပကတိတန်ဖိုး)**
       
       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``MODULUS``
     - [number]
       
       Default: 0
     - စိတ်ကြိုက် modulus တန်ဖိုးတစ်ခုကို သတ်မှတ်ခြင်းသည် Field တန်ဖိုးသည် modulus တန်ဖိုးသို့ရောက်သည့်အချိန်တိုင်း အရေအတွက်ကို ပြန်လည်စတင်မည် ဖြစ်သည်။ ``0`` ဆိုပါက ပြန်လည်စတင်မည် မဟုတ်ပါ။
   * - **Group values by** **(တန်ဖိုးများကို အုပ်စုဖွဲ့ခြင်း)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``GROUP_FIELDS``
     - [tablefield: any] [list]
     - အုပ်စုဖွဲ့မည့် field များကို ရွေးချယ်ပါ - layer တစ်ခုလုံးအတွက် ရေတွက်မှုတစ်ခုတည်းဖြင့် လုပ်ဆောင်ခြင်းအစား အဆိုပါ field များပေါင်းစပ်ခြင်းမှ ရရှိလာသော တန်ဖိုးတစ်ခုချင်းစီအတွက် သီးခြား ရေတွက်မှုတစ်ခုကို လုပ်ဆောင်မည်ဖြစ်သည်။
   * - **Sort expression** **(မျိုးတူစုခြင်း expression)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``SORT_EXPRESSION``
     - [expression]
     - အုပ်စု field များအပေါ်အခြေခံပြီး layer အတွင်းရှိ feature များကို sort (မျိုးတူစု) လုပ်ရန် Expression တစ်ခုကို အသုံးပြုပါ။
   * - **Sort ascending** **(မျိုးတူစုခြင်း ငယ်စဉ်ကြီးလိုက်)**
     - ``SORT_ASCENDING``
     - [boolean]

       Default: True
     - ``sort expression`` တစ်ခုကို သတ်မှတ်ထားသောအခါတွင် feature များတွင် တန်ဖိုးများသတ်မှတ်မည့် အစီအစဉ် (order) ကိုထိန်းချူပ်ရန် ဤ option ကို အသုံးပြုပါ။
   * - **Sort nulls first** **(Null များကို ဦးစွာ စီပါ)**
     - ``SORT_NULLS_FIRST``
     - [boolean]

       Default: False
     - ``sort expression`` တစ်ခုကို သတ်မှတ်ထားသောအခါတွင် *Null* တန်ဖိုးများကို ပထမဆုံး သို့မဟုတ် နောက်ဆုံး အဖြစ် ရေတွက်ခြင်းကို သတ်မှတ်ရန် ဤ option ကို အသုံးပြုပါ။
   * - **Incremented** **(တိုးလာပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - အလိုအလျောက်တိုးလာသော field ပါဝင်သည့် output vector layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်)
................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Incremented** **(တိုးလာပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - အလိုအလျောက်တိုးလာသော field ပါဝင်သည့် vector layer

Python code
...........

**Algorithm ID**: ``native:addautoincrementalfield``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisaddfieldtoattributestable:

Add field to attributes table (အချက်အလက်ဇယားထဲသို့ field ပေါင်းထည့်ခြင်း)
--------------------------------------------------------------------------

Vector layer တစ်ခုထဲသို့ field အသစ်တစ်ခု ပေါင်းထည့်ပေးပါသည်။

Attribute ၏ အမည်နှင့် ဝိသေသလက္ခဏာများကို parameter (သတ်မှတ်ချက်) များအဖြစ်သတ်မှတ်မည် ဖြစ်ပါသည်။

Attribute အသစ်ကို input layer ထဲတွင် ပေါင်းထည့်မည်မဟုတ်ပဲ layer အသစ်တစ်ခု ပေါ်ထွက်လာမည်ဖြစ်သည်။

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
   * - **Field name** **(Field အမည်)**
     - ``FIELD_NAME``
     - [string]
     - Field အသစ်၏ အမည်
   * - **Field type** **(Field အမျိုးအစား)**
     - ``FIELD_TYPE``
     - [enumeration]
       
       Default: 0
     - Field အသစ်၏ အမျိုးအစား။ အောက်ပါတို့ထဲမှ ရွေးချယ်နိုင်ပါသည်-
       
       * 0 --- Integer (ကိန်းပြည့်ဂဏန်း)
       * 1 --- Float (ဒဿမဂဏန်း)
       * 2 --- String (စာသား)
       
   * - **Field length** **(Field အရှည်)**
     - ``FIELD_LENGTH``
     - [number]
       
       Default: 10
     - Field ၏ အရှည်
   * - **Field precision** **(Field ၏တိကျမှု)**
     - ``FIELD_PRECISION``
     - [number]
       
       Default: 0
     - Field ၏ တိကျမှု ။ float field အမျိုးအစားများတွင် အသုံးဝင်ပါသည်။
   * - **Field alias** **(Field ၏ အမည်ပွား)**

       |332|

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``FIELD_ALIAS``
     - [string]
     - Field အတွက် အမည်ပွား (alias) အဖြစ်အသုံးပြုမည့် အမည်တစ်ခုကို သတ်မှတ်ပါ။ Format အမျိုးအစားများအားလုံးတွင် အသုံးမပြုနိုင်ပါ။
   * - **Field comment** **(Field မှတ်ချက်)**

       |332|

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``FIELD_COMMENT``
     - [string]
     - Field ကို ဖော်ပြသော မှတ်ချက်တစ်ခုကို သိမ်းဆည်းမည်ဖြစ်သည်။ Format အမျိုးအစားများအားလုံးတွင် အသုံးမပြုနိုင်ပါ။
   * - **Added** **(ပေါင်းထည့်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
       
       Default: ``[Create temporary layer]``
     - Output vector layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်)
................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Added** **(ပေါင်းထည့်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Field အသစ် ပေါင်းထည့်ထားသော vector layer

Python code
...........

**Algorithm ID**: ``native:addfieldtoattributestable``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisadduniquevalueindexfield:

Add unique value index field (ထူးခြားသိသာသော တန်ဖိုး အညွှန်းကိန်း field ပေါင်းထည့်ခြင်း)
-----------------------------------------------------------------------------------------

Vector layer တစ်ခုနှင့် attribute တစ်ခု ယူပြီး ဂဏန်းဆိုင်ရာ field အသစ်တစ်ခု ပေါင်းထည့်ပေးပါသည်။

အဆိုပါ field ထဲရှိ တန်ဖိုးများသည် သတ်မှတ်ထားသော attribute ထဲရှိ တန်ဖိုးများနှင့် သက်ဆိုင်နေမည် ဖြစ်ပါသည်။ ထို့ကြောင့် attribute တန်ဖိုးတူညီသည့် feature များသည် ဂဏန်းဆိုင်ရာ field အသစ်ထဲတွင် တန်ဖိုးများ တူညီနေပါလိမ့်မည်။

ထိုအချက်သည် သတ်မှတ်ထားသော attribute နှင့် ကိန်းဂဏန်းညီမျှမည်ဖြစ်ပြီး၊ တူညီသောအတန်းအစားများကို သတ်မှတ်မည်ဖြစ်သည်။

Attribute အသစ်ကို input layer ထဲတွင် ပေါင်းထည့်မည်မဟုတ်ပဲ layer အသစ်တစ်ခု ပေါ်ထွက်လာမည်ဖြစ်သည်။


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
   * - **Class field** **(အတန်းအစား field)**
     - ``FIELD``
     - [tablefield: any]
     - ဤ field တွင် တန်ဖိုးများတူညီသည့် feature များသည် တူညီသည့် အညွှန်းကိန်း (index) များရရှိမည် ဖြစ်သည်။
   * - **Output field name** **(ရလာဒ် field အမည်)**
     - ``FIELD_NAME``
     - [string]
       
       Default: 'NUM_FIELD'
     - အညွှန်းကိန်း (index) များပါရှိသည့် field အသစ်၏ အမည်
   * - **Layer with index field** **(Index field ပါဝင်သော layer)**
     - ``OUTPUT``
     - [vector: any]
       
       Default: ``[Create temporary layer]``
     - အညွှန်းကိန်း (index) များပါရှိသည့် ဂဏန်းဆိုင်ရာ field များပါဝင်သော vector layer ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**

   * - **Class summary** **(အတန်းအစား အကျဉ်းချုပ်)**
     - ``SUMMARY_OUTPUT``
     - [table]
       
       Default: ``[Skip output]``
     - သက်ဆိုင်ရာ unique တန်ဖိုးကို ဖော်ပြသော အတန်းအစား field ၏အကျဉ်းချုပ်ပါဝင်ရန် table (ဇယား) ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**

Outputs (ရလာဒ်)
................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Layer with index field** **(Index field ပါဝင်သော layer)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - အညွှန်းကိန်း (index) များပါဝင်သည့် ဂဏန်းဆိုင်ရာ field များပါဝင်သော vector layer ။
   * - **Class summary** **(အတန်းအစား အကျဉ်းချုပ်)**
     - ``SUMMARY_OUTPUT``
     - [table]
     - သက်ဆိုင်ရာ unique တန်ဖိုးကို ဖော်ပြသော အတန်းအစား field ၏အကျဉ်းချုပ်ပါဝင်သည့် table (ဇယား)။

Python code
...........

**Algorithm ID**: ``native:adduniquevalueindexfield``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisaddxyfieldstolayer:

Add X/Y fields to layer (Layer ထဲသို့ X/Y field များ ပေါင်းထည့်ခြင်း)
----------------------------------------------------------------------

Point layer တစ်ခုထဲသို့ X နှင့် Y (သို့မဟုတ် လတ္တီကျု/ လောင်ဂျီကျု) field များကို ပေါင်းထည့်ပေးပါသည်။ X/Y field များကို layer ထဲသို့ထည့်ရာတွင် မတူညီသော CRS တစ်ခုဖြင့် တွက်ချက်နိုင်ပါသည် (ဥပမာ- projected CRS တစ်ခုသုံးထားသော layer တစ်ခုအတွက် လတ္တီကျု/လောင်ဂျီကျု field များဖန်တီးခြင်း)။

|checkbox| သည် Point feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း <processing_inplace_edit>` ကို လုပ်ဆောင်နိုင်ပါသည်။

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
     - ထည့်သွင်းအသုံးပြုသော layer
   * - **Coordinate system** **(ကိုဩဒိနိတ်စနစ်)**
     - ``CRS``
     - [crs]
       
       Default: "EPSG:4326"
     - ထုတ်ထားသော x နှင့် y field များအတွက် အသုံးပြုရန် ကိုဩဒိနိတ်ရည်ညွှန်းစနစ် (CRS)
   * - **Field prefix** **(Field ၏ ရှေ့ဆက်စာလုံး)**
       
       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``PREFIX``
     - [string]
     - Input layer ထဲရှိ field များနှင့် အမည်တူနေမှုများကို ရှောင်ရှားရန် field အသစ်၏အမည်များတွင် ပေါင်းထည့်မည့် prefix (ရှေ့ဆက်စာလုံး)။
   * - **Added fields** **(ပေါင်းထည့်ထားသော field များ)**
     - ``OUTPUT``
     - [vector: point]

       Default: ``[Create temporary layer]``
     - Output layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်)
................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Added fields** **(ပေါင်းထည့်ထားသော field များ)**
     - ``OUTPUT``
     - [vector: point]
     - Output layer - input layer နှင့် တစ်ထပ်တည်းတူညီသော်လည်း output layer တွင် ``x`` နှင့် ``y`` field အသစ်နှစ်ခုပါဝင်မည်ဖြစ်သည်။

Python code
...........

**Algorithm ID**: ``native:addxyfieldstolayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisadvancedpythonfieldcalculator:

Advanced Python field calculator (အဆင့်မြင့် Python field ဂဏန်းတွက်စက်)
------------------------------------------------------------------------

Feature တစ်ခုချင်းစီတွင် expression တစ်ခုအသုံးပြုခြင်းမှ ရရှိလာသော တန်ဖိုးများပါဝင်သည့် အချက်အလက်အသစ်တစ်ခုကို vector layer တစ်ခုထဲသို့ ပေါင်းထည့်ပေးပါသည်။

Expression ကို Python function တစ်ခုအဖြစ် သတ်မှတ်ပါသည်။

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
   * - **Result field name** **(ရလာဒ် field အမည်)**
     - ``FIELD_NAME``
     - [string]
       
       Default: 'NewField'
     - Field အသစ်၏ အမည်
   * - **Field type**
     - ``FIELD_TYPE``
     - [enumeration]
       
       Default: 0
     - Field အသစ်အမျိုးအစား။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-
       
       * 0 --- Integer (ကိန်းပြည့်ဂဏန်း)
       * 1 --- Float (ဒဿမဂဏန်း)
       * 2 --- String (စာသား)
       
   * - **Field length** **(Field အရှည်)**
     - ``FIELD_LENGTH``
     - [number]
       
       Default: 10
     - Field ၏ အရှည်
   * - **Field precision** **(Field ၏တိကျမှု)**
     - ``FIELD_PRECISION``
     - [number]
       
       Default: 3
     - Field ၏ တိကျမှု။ Float field အမျိုးအစားများတွင် အသုံးဝင်ပါသည်။
   * - **Global expression**
       
       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``GLOBAL``
     - [string]
     - Calculator သည် input layer ၏ feature များအားလုံးကို ထပ်ခါထပ်ခါ စတင်ဆောင်ရွက်ခြင်း မပြုမီတွင် Global expression အခန်းတွင်ရှိသော ကုဒ်ကို တစ်ကြိမ်သာလျှင် အလုပ်လုပ်ဆောင်စေမည်ဖြစ်သည်။ ထို့ကြောင့် လိုအပ်သည့် module များ ထည့်သွင်းရန် သို့မဟုတ် နောက်ပိုင်းတွက်ချက်ခြင်းများတွင် အသုံးပြုမည့် variable များကို တွက်ချက်ရန် ဤအရာသည် မှန်ကန်သည့် နေရာတစ်ခုဖြစ်ပါသည်။
   * - **Formula**
     - ``FORMULA``
     - [string]
     - အကဲဖြတ်ရန် Python formula ။ ဥပမာ - ထည့်သွင်းထားသည့် polygon layer တစ်ခု၏ ဧရိယာကို တွက်ချက်ရန် အောက်ပါအတိုင်းထည့်သွင်းနိုင်သည်- ::
       
         value = $geom.area()
       
   * - **Calculated** **(တွက်ချက်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
       
       Default: ``[Create temporary layer]``
     - တွက်ချက်ထားသော field အသစ်ပါဝင်သည့် vector layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-
       
       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

Outputs (ရလာဒ်)
................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Calculated** **(တွက်ချက်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - တွက်ချက်ထားသော field အသစ်ပါဝင်သည့် vector layer

Python code
...........

**Algorithm ID**: ``qgis:advancedpythonfieldcalculator``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisdeletecolumn:

Drop field(s) (Field (များ) ကို ဖြုတ်ချန်ထားခြင်း)
---------------------------------------------------

Vector layer တစ်ခုယူပြီး ရွေးချယ်ထားသည့် column များမပါဝင်သည့် တူညီသော feature များရှိသော layer အသစ်တစ်ခုကို ထုတ်ပေးပါသည်။

.. seealso:: :ref:`qgisretainfields`

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
     - Field (များ) ကို ဖြုတ်ချန် (drop) ထားမည့် input vector layer
   * - **Fields to drop** **(ဖြုတ်ချန်မည့် field များ)**
     - ``COLUMN``
     - [tablefield: any] [list]
     - ဖြုတ်ချန် (drop) လုပ်ရန် field များ
   * - **Remaining fields** **(ကျန်ရှိနေသော field များ)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - ကျန်ရှိနေသော field များပါဝင်သည့် output vector layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်)
................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Remaining fields** **(ကျန်ရှိနေသော field များ)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ကျန်ရှိနေသော field များပါဝင်သည့် vector layer

Python code
...........

**Algorithm ID**: ``native:deletecolumn``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisexplodehstorefield:

Explode HStore Field (HStore Field ကို ခွဲထုတ်ခြင်း)
-----------------------------------------------------

Input layer ၏ မိတ္တူပွားတစ်ခု ဖန်တီးပေးပြီး HStore field ထဲရှိ unique key တိုင်းအတွက် field အသစ်တစ်ခုကို ပေါင်းထည့်ပေးပါသည်။

မျှော်မှန်းသော field စာရင်းသည် comma ဖြင့်ပိုင်းခြားထားသော စာရင်းတစ်ခုဖြစ်ပါသည်။ အဆိုပါ စာရင်းကို သတ်မှတ်ထားပြီးဖြစ်လျှင် ထို field များကိုသာလျှင် ပေါင်းထည့်သွားမည်ဖြစ်ပြီး HStore field သည် update ဖြစ်သွားမည်ဖြစ်သည်။ Default အားဖြင့် unique key များအားလုံးကို ပေါင်းထည့်မည်ဖြစ်သည်။

PostgreSQL `HStore <https://www.postgresql.org/docs/10/hstore.html>`_ သည် တစ်ခုသာပါသော key-value store တစ်ခုဖြစ်ပြီး PostgreSQL နှင့် GDAL (``other_tags`` field ပါသော `OSM file <https://gdal.org/drivers/vector/osm.html#other-tags-field>`_  တစ်ခုကို ဖတ်သောအခါ) ထဲတွင်အသုံးပြုပါသည်။


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
   * - **HStore field**
     - ``FIELD``
     - [tablefield: any]
     - ဖြုတ်ချန် (Drop) လုပ်ရန် field များ
   * - **Expected list of fields separated by a comma** **(Comma ဖြင့်ပိုင်းခြားထားသော မျှော်မှန်း field များစာရင်း)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``EXPECTED_FIELDS``
     - [string]

       Default: ''
     - ထုတ်ယူရန် field များ၏ Comma ဖြင့်ပိုင်းခြားထားသောစာရင်းကို။ အဆိုပါ key များကို ဖယ်ရှားခြင်းအားဖြင့် HStore field ကို update လုပ်မည် ဖြစ်သည်။

   * - **Exploded**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
       
       Default: ``[Create temporary layer]``
     - Output vector layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-
       
       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**


Outputs (ရလာဒ်)
................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Exploded**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output vector layer

Python code
...........

**Algorithm ID**: ``native:explodehstorefield``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**

.. _qgisextractbinary:

Extract binary field (Binary field ကို ထုတ်ယူခြင်း)
----------------------------------------------------

Binary field တစ်ခုမှ ပါဝင်သည့်အကြောင်းအရာများကို ထုတ်ယူပေးပါသည်။ ၎င်းတို့ကို သီးခြားဖိုင်များတွင် သိမ်းဆည်းမည်ဖြစ်သည်။ ဖိုင်အမည်များကို ရင်းမြစ်ဇယားထဲရှိ အချက်အလက်မှ ယူထားသော တန်ဖိုးများကိုအသုံးပြုခြင်း သို့မဟုတ် ပိုမိုရှုပ်ထွေးသော expression တစ်ခုအပေါ် အခြေခံ၍ ထုတ်ယူသတ်မှတ်နိုင်ပါသည်။

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
     - Binary ဒေတာပါဝင်သည့် input vector layer
   * - **Binary field**
     - ``FIELD``
     - [tablefield: any]
     - Binary ဒေတာပါဝင်သည့် field 
   * - **File name**
     - ``FILENAME``
     - [expression]
     - Output ဖိုင်တစ်ခုချင်းစီကို အမည်ပေးရန် Field သို့မဟုတ် expression အခြေခံသော စာသား
   * - **Destination folder** **(သိမ်းဆည်းမည့် folder)**
     - ``FOLDER``
     - [folder]

       Default: ``[Save to temporary folder]``
     - Output ဖိုင်များကို သိမ်းဆည်းရန် Folder ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **directory_output_types**
          :end-before: **end_directory_output_types**

Outputs (ရလာဒ်)
................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Folder**
     - ``FOLDER``
     - [folder]
     - Output ဖိုင်များပါဝင်သည့် folder

Python code
...........

**Algorithm ID**: ``native:extractbinary``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisfieldcalculator:

Field calculator (Field ဂဏန်းတွက်စက်)
--------------------------------------

Field calculator (:ref:`vector_expressions` တွင်ကြည့်ပါ) ကိုဖွင့်ပါ။ ပံ့ပိုးပေးထားသည့် expression များနှင့် function များကို အသုံးပြုနိုင်ပါသည်။

Expression ရလာဒ်များဖြင့် layer အသစ်တစ်ခုကို ဖန်တီးပါမည်။ 

:ref:`processing.modeler` ထဲတွင် field calculator ကို အသုံးပြုသောအခါ အလွန်အသုံးဝင်ပါသည်။

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
     - တွက်ချက်ရန် layer
   * - **Output field name** **(ရလာဒ် field ၏အမည်)**
     - ``FIELD_NAME``
     - [string]
     - ရလာဒ်များအတွက် field ၏အမည်
   * - **Output field type** **(ရလာဒ် field အမျိုးအစား)**
     - ``FIELD_TYPE``
     - [enumeration]
       
       Default: 0
     - Field အမျိုးအစား။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-
       
       * 0 --- Float (ဒဿမဂဏန်း)
       * 1 --- Integer (ကိန်းပြည့်ဂဏန်း)
       * 2 --- String (စာသား)
       * 3 --- Date (နေ့စွဲ)
       
   * - **Output field width** **(ရလာဒ် field အကျယ်)**
     - ``FIELD_LENGTH``
     - [number]
       
       Default: 10
     - ရလာဒ် field ၏ အရှည် (အနည်းဆုံး 0)
   * - **Field precision** **(Field ၏တိကျမှု)**
     - ``FIELD_PRECISION``
     - [number]
       
       Default: 3
     - ရလာဒ် field ၏ တိကျမှု (အနည်းဆုံး 0 ၊ အများဆုံး 15)
   * - **Create new field** **(Field အသစ်ဖန်တီးခြင်း)**
     - ``NEW_FIELD``
     - [boolean]
       
       Default: True
     - ရလာဒ် field သည် field အသစ်တစ်ခု ဖြစ်သင့်/မဖြစ်သင့် ဆုံးဖြတ်ပါသည်
   * - **Formula**
     - ``FORMULA``
     - [expression]
     - ရလာဒ်များ တွက်ချက်ရန်အတွက် အသုံးပြုမည့် formula
   * - **Output file**
     - ``OUTPUT``
     - [vector: any]
       
       Default: ``[Create temporary layer]``
     - Output layer ၏ သီးခြားသတ်မှတ်ချက်။

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်)
................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Calculated** **(တွက်ချက်ထားပြီးသော)**
     - ``OUTPUT``
     - [vector: any]
     - တွက်ချက်ထားသော နယ်ပယ်တန်ဖိုးများပါဝင်သော ရလဒ် layer

Python code
...........

**Algorithm ID**: ``native:fieldcalculator``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisrefactorfields:

Refactor fields (Field များ ပြန်လည်ပြုပြင်ခြင်း)
-------------------------------------------------

Vector layer တစ်ခုထဲရှိ attribute ဇယား၏ တည်ဆောက်ပုံကို ပြင်ဆင်ခြင်းများပြုလုပ်နိုင်ပါသည်။

Field mapping တစ်ခုကို အသုံးပြုခြင်းဖြင့် field များကို ၎င်းတို့၏ အမျိုးအစားနှင့် အမည်ထဲတွင် ပြင်ဆင်သတ်မှတ်နိုင်ပါသည်။ 

မူလ layer အား ပြင်ဆင်ပြောင်းလဲသွားမည် မဟုတ်ပါ။ Layer အသစ်တစ်ခု ထွက်ပေါ်လာမည်ဖြစ်ပြီး၊ ထိုထဲတွင် ထောက်ပံ့ပေးထားသည့် field mapping အရ ပြင်ဆင်ထားသော attribute ဇယားတစ်ခု ပါဝင်မည်ဖြစ်ပါသည်။

.. note:: Field များတွင် :ref:`constraints <constraints>` ဖြင့် template layer တစ်ခုအသုံးပြုသောအခါ သတင်းအချက်အလက်ကို နောက်ခံအရောင်နှင့် tooltip တစ်ခုဖြင့် widget ထဲတွင် ဖော်ပြပေးမည်ဖြစ်ပါသည်။ အဆိုပါသတင်းအချက်အလက်ကို configure ပြုလုပ်နေစဉ်အတွင်း အရိပ်အမြွက်အဖြစ် မှတ်ယူရမည်။ Output layer တစ်ခုတွင် အကန့်အသတ် (constraints) ကို ထည့်သွင်းမည်မဟုတ်ပဲ ၎င်းတို့ကို algorithm ဖြင့် စစ်ဆေးခြင်း သို့မဟုတ် တွန်းအားပေးခြင်း ပြုလုပ်မည် မဟုတ်ပါ။

Refactor fields algorithm သည် အောက်ပါတို့ကို လုပ်ဆောင်ခွင့်ပြုပေးမည်ဖြစ်သည်-

* Field ၏ အမည်နှင့် အမျိုးအစားများကို ပြောင်းလဲခြင်း
* Field များကို ပေါင်းထည့်ခြင်းနှင့် ဖယ်ရှားခြင်း
* Field များကို ပြန်လည်စီစဉ်ခြင်း
* Expression များအပေါ် အခြေခံ၍ field အသစ်များကို တွက်ချက်ခြင်း
* အခြား layer မှ field စာရင်းကို ထည့်သွင်းခြင်း

.. figure:: img/refactor_fields.png
  :align: center

  Refactor fields dialog

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
     - မွမ်းမံပြင်ဆင်ရန် layer
   * - **Fields mapping**
     - ``FIELDS_MAPPING``
     - [list]
     - အဓိပ္ပါယ်ဖွင့်ဆိုချက်များပါဝင်သော output field များ၏ စာရင်း။ ချိတ်တွဲထားသော ဇယားသည် ရင်းမြစ် layer ၏ field များအားလုံးကို စာရင်းပြုစုထားမည်ဖြစ်ပြီး ၎င်းတို့ကို ပြင်ဆင်တည်းဖြတ်ခြင်းများ ပြုလုပ်နိုင်ပါသည်-

       * Field အသစ်တစ်ခု ဖန်တီးရန် |newAttribute| ကို နှိပ်ပါ။
       * Field တစ်ခုကို ဖယ်ရှားရန် |deleteAttribute| ကို နှိပ်ပါ။
       * ရွေးချယ်ထားသည့် field အစီအစဉ်များကို ပြောင်းလဲရန် |arrowUp| နှင့် |arrowDown| ကို အသုံးပြုပါ။
       * မူလမြင်ကွင်းသို့ ပြန်သွားရန်အတွက် |clearText| ကို နှိပ်ပါ။
       * Field များစာရင်းထဲရှိ ရွေးချယ်မှုများကို ပြောင်းပြန်လှန်ရန် |invertSelection| ကို နှိပ်ပါ။

       ပြန်လည်အသုံးပြုလိုသည့် field တစ်ခုချင်းစီအတွက် အောက်ပါ ရွေးချယ်စရာ (option) များကို ဖြည့်ရန်လိုအပ်ပါသည်-

       :guilabel:`Source expression` (``expression``) [expression]
         Input layer မှ field သို့မဟုတ် expression။

       :guilabel:`Field name` (``name``) [string]
         Output layer ထဲရှိ field ၏ အမည်။ Default အားဖြင့် input field အမည်အတိုင်း ထားမည်ဖြစ်သည်။

       :guilabel:`Type` (``type``) [enumeration]
         Output field ၏ ဒေတာအမျိုးအစား။ ရရှိနိုင်သော အမျိုးအစားများသည် output layer ပံ့ပိုးပေးသူပေါ်တွင် မူတည်ပါသည်။

       :guilabel:`Length` (``length``) [number]
         Output field ၏ အလျား။

       :guilabel:`Precision` (``precision``) [number]
         Output field ၏ တိကျမှု။

       :guilabel:`Constraints` (``constraints``) [string]
         Template layer တစ်ခုအသုံးပြုသောအခါ template field တစ်ခုတွင် constraint (ကန့်သတ်ချက်) များ အသုံးချထားခြင်း ရှိ/မရှိကို ညွှန်ပြပေးမည်ဖြစ်သည်။ Cell ကွက်တွင် မောက်စ် cursor ကိုတင်ကြည့်လျှင် constraint များကို ပြသပေးမည်ဖြစ်သည်။

       :guilabel:`Field alias` (``field_alias``) [string] |332|
         Field အတွက် အမည်ပွား (alias) အဖြစ်အသုံးပြုရန် အမည်တစ်ခု သတ်မှတ်ပါ။ Format အမျိုးအစားအားလုံးကို အသုံးမပြုနိုင်ပါ။ အကယ်၍ အသုံးပြုနိုင်လျှင် ရှိနေပြီးသား အမည်ပွားများကို ပြသပေးမည်ဖြစ်ပြီး ၎င်းတို့ကို ဦးတည် (destination) layer သို့ ကော်ပီကူးမည် ဖြစ်ပါသည်။

       :guilabel:`Field comment` (``field_comment``) [string] |332|
        Field များကို ဖော်ပြသည့် မှတ်ချက်တစ်ခုကို သိမ်းဆည်းပါ။ Format အမျိုးအစားအားလုံးကို အသုံးမပြုနိုင်ပါ။ အကယ်၍ အသုံးပြုနိုင်လျှင် ရှိနေပြီးသား မှတ်ချက်များကို ပြသပေးမည်ဖြစ်ပြီး ၎င်းတို့ကို ဦးတည် (destination) layer သို့ ကော်ပီကူးမည် ဖြစ်ပါသည်။

       :guilabel:`Load fields from template layer`
         လက်ရှိ ပရောဂျက်မှ layer တစ်ခုကို template တစ်ခုအဖြစ် ရွေးချယ်ရန် ခွင့်ပြုပေးမည်ဖြစ်ပြီး (:guilabel:`Load fields` ဖြင့်) ထိုအရာ၏ field များနှင့် အဓိပ္ပါယ်ဖွင့်ဆိုချက်များပါဝင်သည့် အထက်ဖော်ပြပါ "Fields mapping" option များတွင် ဖြည့်ပေးမည်ဖြစ်သည်။
         

   * - **Refactored** **(ပြန်လည်ပြုပြင်ထားသော)**
     - ``OUTPUT``
     - [vector: any]

       Default: ``[Create temporary layer]``
     - Output layer ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**


Outputs (ရလာဒ်)
................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Refactored** **(ပြန်လည်ပြုပြင်ထားသော)**
     - ``OUTPUT``
     - [vector: any]
     - ပြန်လည်ပြုပြင်ထားသော field များပါဝင်သည့် output layer 

Python code
...........

**Algorithm ID**: ``native:refactorfields``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**

.. _qgisrenametablefield:

Rename field (Field ကို အမည်ပြောင်းခြင်း)
------------------------------------------

Vector layer တစ်ခုမှ လက်ရှိရှိနေသော field တစ်ခုကို အမည်ပြောင်းပေးပါသည်။

မူလ layer ကို ပြင်ဆင်ပြောင်းလဲမည် မဟုတ်ပါ။ အမည်ပြောင်းထားသော နယ်ပယ်များပါဝင်သည့် attribute ဇယားပါဝင်သော layer အသစ်တစ်ခု ထုတ်ပေးမည် ဖြစ်ပါသည်။

.. seealso:: :ref:`qgisrefactorfields`

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
   * - **Field to rename** **(အမည်ပြောင်းရန် field)**
     - ``FIELD``
     - [tablefield: any]
     - ပြောင်းလဲမည့် field
   * - **New field name** **(Field အမည်အသစ်)**
     - ``NEW_NAME``
     - [string]
     - Field အမည် အသစ်
   * - **Renamed** **(အမည်ပြောင်းထားပြီးသော)**
     - ``OUTPUT``
     - [vector: input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output layer ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**


Outputs (ရလာဒ်)
................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Renamed** **(အမည်ပြောင်းထားပြီးသော)**
     - ``OUTPUT``
     - [vector: input နှင့်အတူတူဖြစ်ပါသည်]
     - အမည်ပြောင်းလဲထားသည့် field ပါဝင်သည့် output layer 

Python code
...........

**Algorithm ID**: ``qgis:renametablefield``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**

.. _qgisretainfields:

Retain fields (Field များကို ဆက်လက်ထိန်းသိမ်းထားခြင်း)
-------------------------------------------------------

Vector layer အသစ်တစ်ခုယူပြီး ရွေးချယ်ထားသည့် field များသာ ဆက်လက်ထိန်းသိမ်းထားရှိသော layer အသစ်တစ်ခု ထုတ်ပေးပါသည်။ အခြား field များအားလုံးကို ဖြုတ်ချန် (drop) လိုက်မည် ဖြစ်သည်။

.. seealso:: :ref:`qgisdeletecolumn`


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
   * - **Fields to retain** **(ဆက်လက်ထိန်းသိမ်းထားရှိမည့် field များ)**
     - ``FIELDS``
     - [tablefield: any] [list]
     - Layer ထဲတွင် ဆက်လက်ထားရှိမည့် field များစာရင်း
   * - **Retained fields** **(ဆက်လက်ထိန်းသိမ်းထားရှိသော field များ)**
     - ``OUTPUT``
     - [vector: input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Output layer ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်)
................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Retained fields** **(ဆက်လက်ထိန်းသိမ်းထားရှိသော field များ)**
     - ``OUTPUT``
     - [vector: input နှင့်အတူတူဖြစ်ပါသည်]
     - ဆက်လက်ထိန်းသိမ်းထားသည့် field များပါဝင်သည့် output layer

Python code
...........

**Algorithm ID**: ``native:retainfields``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**

.. _qgistexttofloat:

Text to float (စာသားမှ ဒဿမဂဏန်းသို့)
-------------------------------------

Vector layer တစ်ခုထဲရှိ ပေးထားသည့် attribute တစ်ခု၏ အမျိုးအစားကို မွမ်းမံပြင်ဆင်ပေးပါသည်၊ ဂဏန်းဆိုင်ရာ (numeric) string များပါဝင်သည့် စာသား attribute တစ်ခုကို ဂဏန်းဆိုင်ရာ (numeric) attribute တစ်ခုအဖြစ်သို့ ပြောင်းလဲပေးခြင်းဖြစ်ပါသည် (ဥပမာ၊ '1' မှ ``1.0``)။

Algorithm သည် vector layer အသစ်တစ်ခုကို ဖန်တီးမည်ဖြစ်သောကြောင့် မူလ layer ကို မွမ်းမံပြင်ဆင်မည်မဟုတ်ပါ။

ပြောင်းလဲမှုသည် မဖြစ်နိုင်ပါက ရွေးချယ်ထားသည့် column တွင် ``NULL`` တန်ဖိုးများ ရှိနေပါလိမ့်မည်။

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
   * - **Text attribute to convert to float** **(Float သို့ပြောင်းလဲရန် စာသား attribute)**
     - ``FIELD``
     - [tablefield: string]
     - Float field တစ်ခုအဖြစ်သို့ပြောင်းလဲရန် input layer အတွက် စာသား (string) field
   * - **Float from text** **(စာသားမှ Float သို့)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create Temporary Layer]``
     - Output layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_append**
          :end-before: **end_layer_output_types_append**

Outputs (ရလာဒ်)
................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Float from text** **(စာသားမှ Float သို့)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - စာသား (string) field မှ float (ဒဿမဂဏန်း) field တစ်ခုသို့ ပြောင်းလဲထားသည်များပါဝင်သော output vector layer

Python code
...........

**Algorithm ID**: ``qgis:texttofloat``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**



.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |332| replace:: ``NEW in 3.32``
.. |arrowDown| image:: /static/common/mActionArrowDown.png
   :width: 1.5em
.. |arrowUp| image:: /static/common/mActionArrowUp.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |clearText| image:: /static/common/mIconClearText.png
   :width: 1.5em
.. |deleteAttribute| image:: /static/common/mActionDeleteAttribute.png
   :width: 1.5em
.. |invertSelection| image:: /static/common/mActionInvertSelection.png
   :width: 1.5em
.. |newAttribute| image:: /static/common/mActionNewAttribute.png
   :width: 1.5em
