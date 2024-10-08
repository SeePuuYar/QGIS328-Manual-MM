Vector miscellaneous (Vector ဆိုင်ရာ သောင်းပြောင်းထွေလာ)
=========================================================

.. only:: html

   .. contents::
      :local:
      :depth: 1


.. _gdalbuildvirtualvector:

Build virtual vector (ပညတ်ချက်မဲ့ vector တည်ဆောက်ခြင်း)
--------------------------------------------------------

Vector layer များအစုပါဝင်သော virtual vector layer တစ်ခုကို ဖန်တီးပေးပါသည်။ လက်ရှိ project ထဲတွင် output vitual vector layer ကိုဖွင့်မည် မဟုတ်ပါ။

အခြား algorithm သည် layer များစွာလိုအပ်သော်လည်း layer များကိုသတ်မှတ်ထားသော ``vrt`` ကိုသာလက်ခံသော အခါမျိုးတွင် ယခု algorithm သည် အသုံးဝင်ပါသည်။

Parameter များ
...............

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input datasources** (**ထည့်သွင်းအသုံးပြုသော datasource များ**)
     - ``INPUT``
     - [vector: any] [list]
     - Virtual vector ကိုတည်ဆောက်ရန်အသုံးပြုလိုသော vector layer များကိုရွေးချယ်ပါ။
   * - **Create "unioned" VRT** (**"ပေါင်းစည်းထားသော" VRT ကို ဖန်တီးခြင်း**)
     - ``UNIONED``
     - [boolean]
       
       Default: False
     - ``vrt`` file တစ်ခုတည်းထဲတွင် vector များအားလုံးကိုပေါင်းစည်းချင်လျှင် အမှန်ခြစ်ထားပါ။
   * - **Virtual vector**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Duplicate (အပွား) များသာပါဝင်သော output layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲက တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Virtual vector**
     - ``OUTPUT``
     - [vector: any]
     - ရွေးချယ်ထားသော ရင်းမြစ်များမှ ဖန်တီးထားသော output virtual vector

Python code
............

**Algorithm ID**: ``gdal:buildvirtualvector``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalexecutesql:

Execute SQL (SQL ကိုစေခိုင်းလုပ်ဆောင်ခြင်း)
--------------------------------------------

ရင်းမြစ် layer ပေါ်တွင် SQL syntax အသုံးပြုပြီး ရိုးရှင်းသော သို့မဟုတ် အဆင့်မြင့်သော query (ရွေးချယ်စစ်ထုတ်ခြင်း) တစ်ခုကိုလုပ်ဆောင်ပေးပါသည်။ Query ၏ ရလာဒ်ကို layer အသစ်အဖြစ် ပေါင်းထည့်ပါမည်။

Algorithm ကို `GDAL ogr2ogr utility <https://gdal.org/programs/ogr2ogr.html>`_ မှ ရယူပါသည်။

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
     - OGR မှလုပ်ဆောင်ပေးနိုင်သော input vector layer
   * - **SQL expression**
     - ``SQL``
     - [string]

     - SQL query ကိုသတ်မှတ်ပေးပါသည်၊ ဥပမာ- ``SELECT * FROM my_table WHERE name is not null``

   * - **SQL dialect** (**SQL ဘာသာစကား**)
     - ``DIALECT``
     - [enumeration]

       Default: 0
     - အသုံးပြုမည့် SQL ဘာသာစကား။ အောက်ပါတို့ထဲက တစ်ခုခုဖြစ်ပါသည် -

       * 0 --- None
       * 1 --- OGR SQL
       * 2 --- SQLite
   * - **SQL result** (**SQL ရလာဒ်**)
     - ``OUTPUT``
     - [vector: any]

     - Output layer ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲက တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

   
       ``Save to File (File အဖြစ်သိမ်းဆည်းခြင်း)`` အတွက် output format ကိုသတ်မှတ်ပေးရပါမည်။ GDAL vector format များအားလုံး အလုပ်လုပ်ပါသည်။ ``Save to a Temporary File (ယာယီ file အဖြစ်သိမ်းဆည်းခြင်း)`` အတွက် မူရင်း output vector layer format ကိုအသုံးပြုပါသည်။

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

       Default: '' (အခြားထပ်ဆောင်းရွေးချယ်စရာ မရှိပါ)
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
   * - **SQL result** (**SQL ရလာဒ်**)
     - ``OUTPUT``
     - [vector: any]
     - Query ဖြင့်ဖန်တီးထားသော vector layer

Python code
............

**Algorithm ID**: ``gdal:executesql``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalimportvectorintopostgisdatabaseavailableconnections:

Export to PostgreSQL (available connections) (PostgreSQL သို့ထုတ်ခြင်း (ရရှိနိုင်သောချိတ်ဆက်မှုများ))
------------------------------------------------------------------------------------------------------

အသုံးပြုနိုင်သော ချိတ်ဆက်မှုတစ်ခုအခြေခံပေါ်တွင် PostgreSQL database တစ်ခုအတွင်းသို့ vector layer များထည့်သွင်းပေးပါသည်။ ချိတ်ဆက်မှုကို အသုံးမပြုမီ :ref:`သေသေချာချာသတ်မှတ်ရပါမည် <vector_create_stored_connection>`။ 'Save Username (အသုံးပြုသူနာမည်ကို သိမ်းထားခြင်း)' နှင့် 'Save Password (လျှို့ဝှက်နံပတ်ကိုသိမ်းထားခြင်း)' checkbox များကို အသုံးပြုထားသည်ကို သတိထားပါ။ ထို့နောက် algorithm ကိုအသုံးပြုနိုင်ပြီ ဖြစ်ပါသည်။

Algorithm ကို `GDAL ogr2ogr utility <https://gdal.org/programs/ogr2ogr.html>`_ မှ ရယူပါသည်။

Parameter များ
...............

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Database (connection name)** (**Database (ချိတ်ဆက်မှု နာမည်)**)
     - ``DATABASE``
     - [string]

     - ချိတ်ဆက်မည့် PostgreSQL database
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [vector: any]

     - Database သို့ထုတ်ရန် OGR မှလုပ်ဆောင်ပေးနိုင်သော vector layer
   * - **Shape encoding** (**Encoding ကိုပုံဖော်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SHAPE_ENCODING``
     - [string]

       Default: ''
     - Data အတွက်အသုံးချမည့် encoding ကိုသတ်မှတ်ပေးပါသည်
   * - **Output geometry type** (**Output ဂျီဩမေတြီ အမျိုးအစား**)
     - ``GTYPE``
     - [enumeration]

       Default: 0
     - Output ဂျီဩမေတြီ အမျိုးအစားကို သတ်မှတ်ပေးပါသည်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် - 

       * 0 ---
       * 1 --- NONE
       * 2 --- GEOMETRY
       * 3 --- POINT
       * 4 --- LINESTRING
       * 5 --- POLYGON
       * 6 --- GEOMETRYCOLLECTION
       * 7 --- MULTIPOINT
       * 8 --- MULTIPOLYGON
       * 9 --- MULTILINESTRING

   * - **Assign an output CRS** (**Output CRS တစ်ခုကိုသတ်မှတ်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``A_SRS``
     - [crs]

       Default: None
     - Database table ၏ output CRS ကိုသတ်မှတ်ပေးပါသည်။
   * - **Reproject to this CRS on output** (**Output အတွက် ယခု CRS သို့ projection ပြောင်းလဲပေးခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``T_SRS``
     - [crs]

       Default: None
     - Output အတွက် ယခု CRS သို့ projection ပြောင်းလဲပေး/အသွင်ပြောင်းပေးပါသည်။
   * - **Override source CRS** (**ရင်းမြစ် CRS ကိုအစားထိုးပြင်ဆင်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``S_SRS``
     - [crs]

       Default: None
     - Input layer CRS ကိုအစားထိုးပြင်ဆင်ပေးပါသည်။
   * - **Schema (schema name)** (**ပုံကြမ်း (ပုံကြမ်းအမည်)**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SCHEMA``
     - [string]

       Default: 'public'
     - Database ဇယားအတွက် schema ကိုသတ်မှတ်ပေးပါသည်။
   * - **Table to export to (leave blank to use layer name)** (**ထုတ်ရန် ဇယား (layer အမည်အတွက် အသုံးပြုရန် ဗလာထားခဲ့ပါ)**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``TABLE``
     - [string]

       Default: ''
     - Database ထဲသို့ထည့်သွင်းမည့် ဇယားအတွက် အမည်တစ်ခုကို သတ်မှတ်ပေးပါသည်။ Default အားဖြင့် ဇယားအမည်သည် input vector file ၏အမည်ဖြစ်ပါသည်။
   * - **Primary Key (new field)** (**မူလ Key (column အသစ်)**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``PK``
     - [string]

       Default: 'id'
     - Database ဇယား၏ မည်သည့် column သည် primary key ဖြစ်မည်ကို သတ်မှတ်ပေးပါသည်။
   * - **Primary Key (existing field, used if the above option is
       left empty)** (**မူလ Key (ရှိနေပြီးသား column၊ အထက်တွင်ဖော်ပြခဲ့သော option ကိုဗလာအဖြစ်ထားလျှင် အသုံးပြုပါ)**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``PRIMARY_KEY``
     - [tablefield: any]

       Default: None
     - ထုတ်ထားသည့် layer ထဲရှိ မည်သည့် column သည် Database ဇယား၏ primary key ဖြစ်မည်ကို သတ်မှတ်ပေးပါသည်။
   * - **Geometry column name** (**ဂျီဩမေတြီ column အမည်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``GEOCOLUMN``
     - [string]

       Default: 'geom'
     - Database ၏မည်သည့် column တွင် ဂျီဩမေတြီ သတင်းအချက်အလက်ရှိမည် ဆိုသည်ကို သတ်မှတ်ပေးပါသည်
   * - **Vector dimensions** (**Vector ရှုထောင့် များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``DIM``
     - [enumeration]

       Default: 0 (2D)
     - ထည့်သွင်းအသုံးပြုမည့် vector file တွင် နှစ်ဖက်မြင် သို့မဟုတ် သုံးဖက်မြင် data များရှိ/မရှိကို သတ်မှတ်ပေးပါသည်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် - 

       * 0 --- 2
       * 1 --- 3

   * - **Distance tolerance for simplification** (**ရိုးရှင်းအောင်ပြုလုပ်ခြင်းအတွက် အကွာအဝေးပမာဏ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SIMPLIFY``
     - [string]

       Default: ''
     - ထည့်သွင်းမည့် vector ဂျီဩမေတြီ များကိုအမှတ်များနည်းသွားပြီး feature ကိုရိုးရှင်းအောင်ပြုလုပ်ခြင်းအတွက် အကွာအဝေး ကိုသတ်မှတ်ပေးပါသည်။ မူရင်းအားဖြင့် ရိုးရှင်းအောင်ပြုလုပ်ခြင်း မရှိပါ။
   * - **Maximum distance between 2 nodes (densification)** (**ဆုံချက်နှစ်ခုအကြား အဝေးဆုံးအကွာအဝေး (အမှတ်များတိုးများလာပြီး သိပ်သည်းအောင် ပြုလုပ်ခြင်း)**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SEGMENTIZE``
     - [string]

       Default: ''
     - ဆုံချက်နှစ်ခုအကြား အဝေးဆုံးအကွာအဝေး။ ကြားထဲတွင် အမှတ်များဖန်တီးရန် အသုံးပြုပါသည်။ မူရင်းအားဖြင့် အမှတ်များတိုးများလာပြီးသိပ်သည်းအောင် ပြုလုပ်ခြင်း မရှိပါ။
   * - **Select features by extent (defined in input layer CRS)** (**Extent ဖြင့် feature များကိုရွေးချယ်ခြင်း (input layer CRS ထဲတွင်သတ်မှတ်ထားသော)**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SPAT``
     - [extent]

       Default: None
     - သတ်မှတ်ထားသော extent တစ်ခုမှ feature များကို ရွေးချယ်နိုင်ပြီး ၎င်းတို့သည် Output ဇယားထဲတွင်ရှိနေလိမ့်မည်ဖြစ်သည်။

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Clip the input layer using the above (rectangle) extent** (**အထက်တွင်ဖော်ပြခဲ့သော ထောင့်မှန်စတုဂံ extent ကို အသုံးပြုပြီး input layer ကိုဖြတ်ထုတ်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``CLIP``
     - [boolean]


       Default: False
     - ရှေ့တွင်သတ်မှတ်ခဲ့သော extent ဖြင့် input layer ကို ဖြတ်ထုတ်ပါမည်။
   * - **Select features using a SQL "WHERE" statement (Ex: column="value")** (**SQL "WHERE" statement ကိုအသုံးပြုပြီး feature များကိုရွေးချယ်ခြင်း (ဥပမာ- column="value")**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``WHERE``
     - [string]

       Default: ''
     - Input layer မှ မည်သည့် feature များကို ရွေးချယ်သင့်သည်ကို SQL "WHERE" statement တစ်ခုအသုံးပြုပြီး သတ်မှတ်ပေးပါသည်
   * - **Group N features per transaction (Default: 2000)** (**လုပ်ဆောင်မှုတစ်ခုချင်းအလိုက် အုပ်စုဖွဲ့မည့် feature အရေအတွက် (မူရင်း - 2000)**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``GT``
     - [string]

       Default: ''
     - လုပ်ဆောင်မှုများတွင် input feature များအား အုပ်စုဖွဲ့နိုင်ပြီး N သည်အရွယ်အစားကို သတ်မှတ်ပေးပါသည်။ မူရင်းအားဖြင့် N သည် လုပ်ဆောင်မှုအရွယ်အစားကို 20000 feature အထိ ကန့်သတ်ပါသည်။
   * - **Overwrite existing table** (**ရှိနေပြီးသား ဇယားကို အစားထိုးပြင်ဆင်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OVERWRITE``
     - [boolean]

       Default: True
     - Database ထဲတွင် နာမည်တူသော ဇယားတစ်ခုရှိနေပြီး ၎င်းနည်းလမ်းကို အမှန်အဖြစ်ထားလျှင် ဇယားကို အစားထိုးပြင်ဆင်ပါလိမ့်မည်။
   * - **Append to existing table** (**ရှိနေပြီးသား ဇယားတွင် နောက်ဆက်တွဲထည့်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``APPEND``
     - [boolean]


       Default: False 
     - အမှန်ခြစ်ထားလျှင်/True ဖြစ်နေလျှင် vector data ကို ရှိနေပြီးသားဇယားထဲသို့ နောက်ဆက်တွဲထည့်ပါလိမ့်မည်။ Input layer ထဲတွင် တွေ့ရသော column အသစ်များကို လျှစ်လျူရှုပါသည်။ သာမန်အားဖြင့် ဇယားအသစ်တစ်ခုကို ဖန်တီးပါလိမ့်မည်။
   * - **Append and add new fields to existing table** (**ရှိနေပြီးသားဇယားသို့ column အသစ်များ နောက်ဆက်တွဲထည့်ခြင်းနှင့် ပေါင်းထည့်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``ADDFIELDS``
     - [boolean]

       Default: False
     - ဖွင့်ထားလျှင် vector layer ကို ရှိနေပြီးသားဇယားသို့ နောက်ဆက်တွဲထည့်မည်ဖြစ်ပြီး ဇယားအသစ်ကိုဖန်တီးပေးမည် မဟုတ်ပါ။ Input layer တွင် တွေ့ရသော column အသစ်များကို ဇယားတွင်ပေါင်းထည့်ပေးပါသည်။ မူရင်းအားဖြင့် ဇယားအသစ်တစ်ခုကို ဖန်တီးပေးပါသည်။
   * - **Do not launder columns/table names** (**Column များ/ဇယား အမည်များကို သန့်စင်အောင်မလုပ်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``LAUNDER``
     - [boolean]


       Default: False
     - ယခုနည်းလမ်းကိုအသုံးပြုလျှင် မူရင်းလုပ်ဆောင်မှု (column အမည်များကို စာလုံးအသေးအဖြစ် ပြောင်းလဲခြင်း၊ space နှင့်အခြား အသုံးပြုလို့မရသော သင်္ကေတများကို ဖယ်ထုတ်ခြင်း) ကို လုပ်ဆောင်မည်မဟုတ်ပါ 
   * - **Do not create Spatial Index** (**တည်နေရာဆိုင်ရာအညွှန်းကိုမဖန်တီးခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``INDEX``
     - [boolean]

       Default: False
     - Output ဇယားအတွက် spatial index တစ်ခုကို ဖန်တီးပေးမည်မဟုတ်ပါ။ မူရင်းအားဖြင့် spatial index တစ်ခုကိုပေါင်းထည့်ပါသည်။
   * - **Continue after a failure, skipping the failed feature** (**မအောင်မြင်မှုဖြစ်ပြီးနောက် ဆက်လက်လုပ်ဆောင်ခြင်း၊ လုပ်ဆောင်မှုမအောင်မြင်သော feature များကိုကျော်ပစ်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SKIPFAILURES``
     - [boolean]

       Default: False
     - 
   * - **Promote to Multipart** (**အစိတ်အပိုင်းများစွာအဖြစ် မြှင့်တင်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``PROMOTETOMULTI``
     - [boolean]

       Default: True
     - Feature ဂျီဩမေတြီ အမျိုးအစားကို output ဇယားထဲတွင် အစိတ်အပိုင်းများစွာအဖြစ် လုပ်ဆောင်ပေးပါသည်
   * - **Keep width and precision of input attributes** (**Input attribute များ၏ အကျယ် (အလုံးအရေအတွက်) နှင့် တိကျမှု (ဒဿမကိန်းအရေအတွက်) ကို ထိန်းထားခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``PRECISION``
     - [boolean]

       Default: True
     - Column attribute များကို input data နှင့်ကိုက်ညီစေရန် မွမ်းမံပြင်ဆင်မှုကို ရှောင်ရှားခြင်း။
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးခြင်း နည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: '' (အခြားထပ်ဆောင်းရွေးချယ်စရာ မရှိပါ)
     - ထပ်ဆောင်း GDAL ဖန်တီးခြင်း နည်းလမ်းများ

Outputs (ရလာဒ်များ)
....................

ဤ Algorithm သည် output မရှိပါ။

Python code
............

**Algorithm ID**: ``gdal:importvectorintopostgisdatabaseavailableconnections``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalimportvectorintopostgisdatabasenewconnection:

Export to PostgreSQL (new connection) (PostgreSQL သို့ထုတ်ခြင်း (ချိတ်ဆက်မှုအသစ်))
-----------------------------------------------------------------------------------

PostGreSQL database တစ်ခုထဲသို့ vector layer များထည့်သွင်းပေးပါသည်။ PostGIS database သို့ချိတ်ဆက်မှုအသစ်တစ်ခု ဖန်တီးရပါမည်။

Algorithm ကို `GDAL ogr2ogr utility <https://gdal.org/programs/ogr2ogr.html>`_ မှ ရယူပါသည်။

Parameter များ
...............

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
     - Database သို့ထုတ်ရန် OGR မှလုပ်ဆောင်ပေးနိုင်သော vector layer
   * - **Shape encoding**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SHAPE_ENCODING``
     - [string]

       Default: ''
     - Data အတွက်အသုံးပြုရန် encoding ကိုသတ်မှတ်ပေးပါသည်။
   * - **Output geometry type** (**Output ဂျီဩမေတြီ အမျိုးအစား**)
     - ``GTYPE``
     - [enumeration]

       Default: 0
     - Output ဂျီဩမေတြီ အမျိုးအစားကို သတ်မှတ်ပေးပါသည်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       * 0 ---
       * 1 --- NONE
       * 2 --- GEOMETRY
       * 3 --- POINT
       * 4 --- LINESTRING
       * 5 --- POLYGON
       * 6 --- GEOMETRYCOLLECTION
       * 7 --- MULTIPOINT
       * 8 --- MULTIPOLYGON
       * 9 --- MULTILINESTRING

   * - **Assign an output CRS** (**Output CRS တစ်ခုသတ်မှတ်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``A_SRS``
     - [crs]

       Default: None
     - Database ဇယား၏ output CRS ကိုသတ်မှတ်ပေးပါသည်။
   * - **Reproject to this CRS on output** (**Output တွင် ယခု CRS သို့ projection ပြောင်းလဲခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``T_SRS``
     - [crs]

       Default: None
     - Output တွင် ယခု CRS သို့ projection ပြောင်းလဲပေး/အသွင်ပြောင်းပေးပါသည်။
   * - **Override source CRS** (**ရင်းမြစ် CRS ကိုအစားထိုးပြင်ဆင်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``S_SRS``
     - [crs]

       Default: None
     - Input layer CRS ကိုအစားထိုးပြင်ဆင်ခြင်း
   * - **Host**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``HOST``
     - [string]

       Default: 'localhost'
     - Database host ၏ အမည်
   * - **Port**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``PORT``
     - [string]

       Default: '5432'
     - PostgreSQL database server က လက်ခံသော port နံပတ်
   * - **Username** (**အသုံးပြုသူအမည်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``USER``
     - [string]

       Default: ''
     - Database ထဲသို့ဝင်ရောက်ရန် အသုံးပြုမည့် အသုံးပြုသူအမည်
   * - **Database name** (**Database အမည်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``DBNAME``
     - [string]

       Default: ''
     - Database အမည်
   * - **Password** (**လျှို့ဝှက်နံပါတ်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``PASSWORD``
     - [string]

       Default: ''
     - Database နှင့်ချိတ်ဆက်ရန် အသုံးပြုသူနာမည်နှင့် တွဲသုံးရမည့် လျှို့ဝှက်နံပါတ်
   * - **Schema (schema name)**  (**ပုံကြမ်း (ပုံကြမ်းအမည်)**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SCHEMA``
     - [string]

       Default: 'public' ('အများပြည်သူအသုံးပြုနိုင်ပါသည်')
     - Database ဇယားအတွက် schema ကိုသတ်မှတ်ပေးပါသည်
   * - **Table name, leave blank to use input name** (**ဇယားနာမည်၊ input နာမည်ကို အသုံးပြုရန် ဗလာထားပါ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``TABLE``
     - [string]

       Default: ''
     - Database ထဲသို့ထည့်သွင်းမည့် ဇယားအတွက် နာမည်သတ်မှတ်ပေးပါသည်။ မူရင်းအားဖြင့် ဇယားနာမည်သည် input vector file ၏နာမည်ဖြစ်ပါသည်။
   * - **Primary Key (new field)** (**မူလ Key (column အသစ်)**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``PK``
     - [string]

       Default: 'id'
     - မည်သည့် column သည် Database ဇယား၏ primary key ဖြစ်မည်ကို သတ်မှတ်ပေးပါသည်။
   * - **Primary Key (existing field, used if the above option is left empty)** (**Primary Key (ရှိနေပြီးသား column၊ အထက်တွင်ဖော်ပြခဲ့သော နည်းလမ်းကိုဗလာအဖြစ်ထားလျှင် အသုံးပြုပါ)**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``PRIMARY_KEY``
     - [tablefield: any]

       Default: None
     - ထုတ်ထားသည့် layer ထဲရှိ မည်သည့် column သည် Database ဇယား၏ primary key ဖြစ်မည်ကို သတ်မှတ်ပေးပါသည်	   
   * - **Geometry column name** (**ဂျီဩမေတြီ column အမည်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``GEOCOLUMN``
     - [string]

       Default: 'geom'
     - ဂျီဩမေတြီ သတင်းအချက်အလက်ကို မည်သည့် attriute columne ထဲတွင်သိမ်းဆည်းမည်ကို သတ်မှတ်ပေးပါသည်
   * - **Vector dimensions** (**Vector ရှုထောင့်များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``DIM``
     - [enumeration]

       Default: 0 (2D)
     - ထည့်သွင်းအသုံးပြုမည့် vector file သည် နှစ်ဖက်မြင် သို့မဟုတ် သုံးဖက်မြင် data များရှိ/မရှိ သတ်မှတ်ပေးပါသည်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် - 

       * 0 --- 2D
       * 1 --- 3D

   * - **Distance tolerance for simplification** (**ရိုးရှင်းအောင်ပြုလုပ်ခြင်းအတွက် အကွာအဝေးပမာဏ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SIMPLIFY``
     - [string]

       Default: ''
     - ထည့်သွင်းမည့် vector ဂျီဩမေတြီများကို အမှတ်များနည်းသွားပြီး feature ကိုရိုးရှင်းအောင်ပြုလုပ်ခြင်းအတွက် အကွာအဝေး ကိုသတ်မှတ်ပေးပါသည်။ Default အားဖြင့် ရိုးရှင်းအောင်ပြုလုပ်ခြင်း မရှိပါ။
   * - **Maximum distance between 2 nodes (densification)** (**ဆုံချက်နှစ်ခုအကြား အဝေးဆုံးအကွာအဝေး (အမှတ်များတိုးများလာပြီး သိပ်သည်းအောင် ပြုလုပ်ခြင်း)**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SEGMENTIZE``
     - [string]

       Default: ''
     - ဆုံချက်နှစ်ခုအကြား အဝေးဆုံးအကွာအဝေး။ ကြားထဲတွင် အမှတ်များဖန်တီးရန် အသုံးပြုပါသည်။ Default အားဖြင့် အမှတ်များတိုးများလာပြီးသိပ်သည်းအောင် ပြုလုပ်ခြင်း မရှိပါ။
   * - **Select features by extent (defined in input layer CRS)** (**Extent ဖြင့် feature များကိုရွေးချယ်ခြင်း (input layer CRS ထဲတွင်သတ်မှတ်ထားသော)**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SPAT``
     - [extent]

       Default: None
     - သတ်မှတ်ထားသော extent တစ်ခုမှ feature များကို ရွေးချယ်နိုင်ပြီး ၎င်းတို့သည် Output ဇယားထဲတွင်ရှိနေလိမ့်မည်ဖြစ်သည်။

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Clip the input layer using the above (rectangle) extent** (**အထက်တွင်ဖော်ပြခဲ့သော ထောင့်မှန်စတုဂံ extent ကို အသုံးပြုပြီး input layer ကိုဖြတ်ထုတ်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``CLIP``
     - [boolean]


       Default: False
     - ရှေ့တွင်သတ်မှတ်ခဲ့သော extent ဖြင့် input layer ကို ဖြတ်ထုတ်ပါမည်။
   * - **Select features using a SQL "WHERE" statement (Ex: column="value")** (**SQL "WHERE" statement ကိုအသုံးပြုပြီး feature များကိုရွေးချယ်ခြင်း (ဥပမာ- column="value")**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``WHERE``
     - [string]

       Default: ''
     - Input layer မှ မည်သည့် feature များကို ရွေးချယ်သင့်သည်ကို SQL "WHERE" statement တစ်ခုအသုံးပြုပြီး သတ်မှတ်ပေးပါသည်
   * - **Group N features per transaction (Default: 2000)** (**လုပ်ဆောင်မှုတစ်ခုချင်းအလိုက် အုပ်စုဖွဲ့မည့် feature အရေအတွက် (မူရင်း - 2000)**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``GT``
     - [string]

       Default: ''
     - လုပ်ဆောင်မှုများတွင် input feature များအား အုပ်စုဖွဲ့နိုင်ပြီး N သည်အရွယ်အစားကို သတ်မှတ်ပေးပါသည်။ မူရင်းအားဖြင့် N သည် လုပ်ဆောင်မှုအရွယ်အစားကို 20000 feature အထိ ကန့်သတ်ပါသည်။
   * - **Overwrite existing table** (**ရှိနေပြီးသား ဇယားကို အစားထိုးပြင်ဆင်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OVERWRITE``
     - [boolean]

       Default: True
     - Database ထဲတွင် နာမည်တူသော ဇယားတစ်ခုရှိနေပြီး ၎င်းနည်းလမ်းကို အမှန်အဖြစ်ထားလျှင် ဇယားကို အစားထိုးပြင်ဆင်ပါလိမ့်မည်။
   * - **Append to existing table** (**ရှိနေပြီးသား ဇယားတွင် နောက်ဆက်တွဲထည့်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``APPEND``
     - [boolean]


       Default: False 
     - အမှန်ခြစ်ထားလျှင်/True ဖြစ်နေလျှင် vector data ကို ရှိနေပြီးသားဇယားထဲသို့ နောက်ဆက်တွဲထည့်ပါလိမ့်မည်။ Input layer ထဲတွင် တွေ့ရသော column အသစ်များကို လျှစ်လျူရှုပါသည်။ သာမန်အားဖြင့် ဇယားအသစ်တစ်ခုကို ဖန်တီးပါလိမ့်မည်။
   * - **Append and add new fields to existing table** (**ရှိနေပြီးသားဇယားသို့ column အသစ်များ နောက်ဆက်တွဲထည့်ခြင်းနှင့် ပေါင်းထည့်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``ADDFIELDS``
     - [boolean]

       Default: False
     - ဖွင့်ထားလျှင် vector layer ကို ရှိနေပြီးသားဇယားသို့ နောက်ဆက်တွဲထည့်မည်ဖြစ်ပြီး ဇယားအသစ်ကိုဖန်တီးပေးမည် မဟုတ်ပါ။ Input layer တွင် တွေ့ရသော column အသစ်များကို ဇယားတွင်ပေါင်းထည့်ပေးပါသည်။ မူရင်းအားဖြင့် ဇယားအသစ်တစ်ခုကို ဖန်တီးပေးပါသည်။
   * - **Do not launder columns/table names** (**Column များ/ဇယား အမည်များကို သန့်စင်အောင်မလုပ်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``LAUNDER``
     - [boolean]

       Default: False
     - ယခုနည်းလမ်းကိုအသုံးပြုလျှင် မူရင်းလုပ်ဆောင်မှု (column အမည်များကို စာလုံးအသေးအဖြစ် ပြောင်းလဲခြင်း၊ space နှင့်အခြား အသုံးပြုလို့မရသော သင်္ကေတများကို ဖယ်ထုတ်ခြင်း) ကို လုပ်ဆောင်မည်မဟုတ်ပါ 
   * - **Do not create Spatial Index** (**တည်နေရာဆိုင်ရာအညွှန်းကိုမဖန်တီးခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``INDEX``
     - [boolean]

       Default: False
     - Output ဇယားအတွက် spatial index တစ်ခုကို ဖန်တီးပေးမည်မဟုတ်ပါ။ မူရင်းအားဖြင့် spatial index တစ်ခုကိုပေါင်းထည့်ပါသည်။
   * - **Continue after a failure, skipping the failed feature** (**မအောင်မြင်မှုဖြစ်ပြီးနောက် ဆက်လက်လုပ်ဆောင်ခြင်း၊ လုပ်ဆောင်မှုမအောင်မြင်သော feature များကိုကျော်ပစ်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SKIPFAILURES``
     - [boolean]

       Default: False
     - 
   * - **Promote to Multipart** (**အစိတ်အပိုင်းများစွာအဖြစ် မြှင့်တင်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``PROMOTETOMULTI``
     - [boolean]

       Default: True
     - Feature ဂျီဩမေတြီ အမျိုးအစားကို output ဇယားထဲတွင် အစိတ်အပိုင်းများစွာအဖြစ် လုပ်ဆောင်ပေးပါသည်
   * - **Keep width and precision of input attributes** (**Input attribute များ၏ အကျယ် (အလုံးအရေအတွက်) နှင့် တိကျမှု (ဒဿမကိန်းအရေအတွက်) ကို ထိန်းထားခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``PRECISION``
     - [boolean]

       Default: True
     - Column attribute များကို input data နှင့်ကိုက်ညီစေရန် မွမ်းမံပြင်ဆင်မှုကို ရှောင်ရှားခြင်း။
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးခြင်း နည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: '' (အခြားထပ်ဆောင်းရွေးချယ်စရာ မရှိပါ)
     - ထပ်ဆောင်း GDAL ဖန်တီးခြင်း နည်းလမ်းများ

Outputs (ရလာဒ်များ)
....................

ဤ Algorithm သည် output မရှိပါ။

Python code
............

**Algorithm ID**: ``gdal:importvectorintopostgisdatabasenewconnection``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalogrinfo:

Vector Information (Vector သတင်းအချက်အလက်)
-------------------------------------------

OGR မှလုပ်ဆောင်ပေးနိုင်သော data ရင်းမြစ်တစ်ခုအကြောင်း သတင်းအချက်အလက်များကို စာရင်းပြုသော သတင်းအချက်အလက် file တစ်ခုကိုဖန်တီးပေးပါသည်။ Output ကို 'Result' window ထဲတွင်ပြသမည်ဖြစ်ပြီး HTML-file အဖြစ် ရေးသားနိုင်ပါသည်။ သတင်းအချက်အလက်ထဲတွင် ဂျီဩမေတြီ အမျိုးအစား၊ feature အရေအတွက်၊ ပထဝီဆိုင်ရာ အကျယ်အဝန်း၊ projection နှင့်ပတ်သက်သော သတင်းအချက်အလက်များနှင့် အခြားအကြောင်းအရာများစွာ ပါဝင်ပါသည်။

Algorithm ကို `GDAL ogrinfo utility <https://gdal.org/programs/ogrinfo.html>`_  မှ ရယူပါသည်။

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
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Summary output only** (**အကျဉ်းချုပ် output မျှသာ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SUMMARY_ONLY``
     - [boolean]

       Default: True
     - 
   * - **Suppress metadata info** (**Metadata သတင်းအချက်အလက်ကို ချုံ့ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``NO_METADATA``
     - [boolean]

       Default: False
     - 
   * - **Layer information** (**Layer သတင်းအချက်အလက်**)
     - ``OUTPUT``
     - [html]

       Default: ``[Save to temporary file]``
     - File သတင်းအချက်အလက်ပါဝင်သော output HTML file ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

       HTML-file ကိုသတ်မှတ်မထားလျှင် output ကိုယာယီ file အဖြစ်ရေးသားဖန်တီးမည်ဖြစ်သည်။


Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်

   * - **Layer information** (**Layer သတင်းအချက်အလက်**)
     - ``OUTPUT``
     - [html]
     - File သတင်းအချက်ပါဝင်သော output HTML-file

Python code
............

**Algorithm ID**: ``gdal:ogrinfo``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**
