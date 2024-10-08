Vector Tiles (Vector အကွက်များ)
================================

.. only:: html

   .. contents::
      :local:
      :depth: 1


.. _qgisdownloadvectortiles:

Download vector tiles (Vector tile များ ဒေါင်းလုဒ်ပြုလုပ်ခြင်း)
----------------------------------------------------------------
|332|

Input vector tile layer တစ်ခု၏ vector tile များကို ‌ဒေါင်းလုပ်ပြုလုပ်မည်ဖြစ်ပြီး ၎င်းတို့ကို မိမိစက်ထဲရှိ vector tile ဖိုင်တစ်ခုထဲတွင် သိမ်းဆည်းပေးမည် ဖြစ်ပါသည်။

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
     - [vector tiles]
     - အချို့ tile များကို ထုတ်ယူရန် vector tile layer
   * - **Extent** **(နယ်ပယ်အကျယ်အဝန်း)**
     - ``EXTENT``
     - [extent]
     - ဒေါင်းလုပ်ပြုလုပ်မည့် ဧရိယာ၏ extent (နယ်ပယ်အကျယ်အဝန်း) ကို သတ်မှတ်ပါ။ ၎င်းသည် Tile အရွယ်အစား၏ အဆင့်ဆင့်အလိုက် တိုးချဲ့သွားမည်ဖြစ်သည်။

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Maximum zoom level to download** **(ဒေါင်းလုဒ်ပြုလုပ်မည့် အများဆုံး zoom အဆင့်)**
     - ``MAX_ZOOM``
     - [number]

       Default: 10
     - Tile များမှ ‌ဒေတာရယူရန်နှင့် မြင်ကွင်းချဲ့ရန် မည်မျှကွာဝေးသည်ကို သတ်မှတ်ပါသည်။
   * - **Tile limit** **(Tile အကန့်အသတ်)**
     - ``TILE_LIMIT``
     - [number]

       Default: 100
     - ဒေါင်းလုပ်ပြုလုပ်ရန် အများဆုံး tile များအရေအတွက်၊ zoom level များနှင့် extent (နယ်ပယ်အကျယ်အဝန်း) ကို ထည့်သွင်းစဉ်းစားပါသည်။
   * - **Output** **(ရလာဒ်)**
     - ``OUTPUT``
     - [vector tiles]

       Default: [Save to temporary file]
     - Output vector tile ဖိုင်၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Outputs (ရလာဒ်)
................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output** **(ရလာဒ်)**
     - ``OUTPUT``
     - [vector tiles]
     - ဒေါင်းလုဒ်ပြုလုပ်ထားသည့် tile များ သိမ်းဆည်းထားသည့် local vector tile ဖိုင်တစ်ခု

Python code
...........

**Algorithm ID**: ``native:downloadvectortiles``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiswritevectortiles_mbtiles:

Write vector tiles (MBTiles) (Vector tile များ ရေးသားခြင်း (MBTiles))
----------------------------------------------------------------------

တစ်ခု သို့မဟုတ် တစ်ခုထက်ပိုသော vector layer များကို vector tile များအဖြစ် ထုတ်ယူပေးပါသည်၊ data အရွယ်အစားသေးငယ်ပြီး မြေပုံ ပုံဖော်ပြသရာတွင် မြန်ဆန်သော အကောင်းဆုံး data format တစ်ခုဖြစ်ပါသည်။

MBTiles သည် ချက်ချင်းအသုံးပြုရန် နှင့် ကူးပြောင်းပေးရန်အတွက် SQLite database များထဲသို့ tile map data များကို သိမ်းဆည်းရန်အတွက် သီးခြားသတ်မှတ်ချက်တစ်ခု ဖြစ်ပါသည်။ MBTiles ဖိုင်များကို tileset များဟုလည်း သိကြပါသည်။

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
     - ``INPUT``
     - [vector: any] [list]
     - Vector tile များ ထုတ်ရန်အတွက် ပေါင်းစပ်ရမည့် layer များစာရင်းတစ်ခု
   * - **Minimum zoom level** **(အနည်းဆုံး zoom အဆင့်)**
     - ``MIN_ZOOM``
     - [number]

       Default: 0
     - Tileset မှ data များ ပံ့ပိုးပေးရန်အတွက် အနိမ့်ဆုံးမြင်ကွင်းအဆင့်။ 0 မှ 24 အကြား သတ်မှတ်ပါ။
   * - **Maximum zoom level** **(အများဆုံး zoom အဆင့်)**
     - ``MAX_ZOOM``
     - [number]

       Default: 3
     - Tileset မှ data များ ပံ့ပိုးပေးရန်အတွက် အများဆုံးမြင်ကွင်းအဆင့်။ 0 မှ 24 အကြား သတ်မှတ်ပါ။
   * - **Extent** **(နယ်ပယ်အကျယ်အဝန်း)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``EXTENT``
     - [extent]

       Default: Not set
     - ပုံဖော်ပြသသော မြေပုံ ဧရိယာ၏ အများဆုံး extent ။ Zoom အဆင့်အားလုံး လွှမ်းခြုံသော ဧရိယာတစ်ခုကို သတ်မှတ်ရပါမည်။
     
   * - **Metadata: Name** **(Metadata- အမည်)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``META_NAME``
     - [string]
     - Tileset အမည်
   * - **Metadata: Description** **(Metadata- ရှင်းလင်းဖော်ပြချက်)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``META_DESCRIPTION``
     - [string]
     - Tileset ၏ အကြောင်းအရာ ဖော်ပြချက်တစ်ခု
   * - **Metadata: Attribution** **(Metadata- အချက်အလက်)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``META_ATTRIBUTION``
     - [string]
     - အချက်အလက်ဆိုင်ရာစာသားတစ်ခု၊ ၎င်းသည် မြေပုံအတွက် data အရင်းအမြစ်များ နှင့်/သို့မဟုတ် style များအကြောင်း ရှင်းပြပါသည်။
   * - **Metadata: Version** **(Metadata- ဗားရှင်း)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``META_VERSION``
     - [string]
     - Tileset ၏ ဗားရှင်း ။ ၎င်းသည် tileset ကိုယ်တိုင်၏ revision (ပြန်လည်စိစစ်မှု) တစ်ခုကို ရည်ညွှန်းပြီး၊ MBTiles သီးခြားသတ်မှတ်ချက်၏ revision တစ်ခုမဟုတ်ပါ။
   * - **Metadata: Type** **(Metadata- အမျိုးအစား)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``META_TYPE``
     - [string]
     - Tileset အမျိုးအစား ။ ဖြစ်နိုင်သော တန်ဖိုးများမှာ ``overlay`` သို့မဟုတ် ``baselayer`` ။
   * - **Metadata: Center** **(Metadata- အလယ်ဗဟို)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``META_CENTER``
     - [string]
     - မြေပုံမူလမြင်ကွင်း၏ အလယ် (comma ဖြင့်ပိုင်းခြားထားသော ဂဏန်းများဖြင့် စာသားများ - လတ္တီကျု၊ လောင်ဂျီကျု နှင့် zoom အဆင့်)။ ဥပမာ - ``-122.1906,37.7599,11``
   * - **Destination MBTiles** **(MBTile များသိမ်းဆည်းမည့်နေရာ)**
     - ``OUTPUT``
     - [vector tiles]

       Default: [Save to temporary file]
     - Output MBTile ဖိုင်၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Outputs (ရလာဒ်)
................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Destination MBTiles** **(MBTile များသိမ်းဆည်းမည့်နေရာ)**
     - ``OUTPUT``
     - [file]
     - Output vector tiles :file:`.mbtiles` ဖိုင်

Python code
...........

**Algorithm ID**: ``native:writevectortiles_mbtiles``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiswritevectortiles_xyz:

Write vector tiles (XYZ) (Vector tile များ ရေးသားခြင်း (XYZ))
--------------------------------------------------------------

တစ်ခု သို့မဟုတ် တစ်ခုထက်ပိုသော vector layer များကို vector tile များအဖြစ် ထုတ်ယူပေးပါသည်၊ data အရွယ်အစားသေးငယ်ပြီး မြေပုံ ပုံဖော်ပြသရာတွင် မြန်ဆန်သော အကောင်းဆုံး data format တစ်ခုဖြစ်ပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **File template** **(ဖိုင် နမူနာပုံစံ)**
     - ``XYZ_TEMPLATE``
     - [string]

       Default: '{z}/{x}/{y}.pbf'
     - Vector tiles url ထုတ်ရန် template
   * - **Input layers** **(ထည့်သွင်းအသုံးပြုသော layer များ)**
     - ``INPUT``
     - [vector: any] [list]
     - Vector tile များ ထုတ်ရန်အတွက် ပေါင်းစပ်မည့် layer များစာရင်းတစ်ခု။
   * - **Minimum zoom level** **(အနည်းဆုံး zoom အဆင့်)**
     - ``MIN_ZOOM``
     - [number]

       Default: 0
     - Tileset မှ data များ ပံ့ပိုးပေးရန်အတွက် အနိမ့်ဆုံးမြင်ကွင်းအဆင့်။ 0 မှ 24 အကြား သတ်မှတ်ပါ။
   * - **Maximum zoom level** **(အများဆုံး zoom အဆင့်)**
     - ``MAX_ZOOM``
     - [number]

       Default: 3
     - Tileset မှ data များ ပံ့ပိုးပေးရန်အတွက် အများဆုံးမြင်ကွင်းအဆင့်။ 0 မှ 24 အကြား သတ်မှတ်ပါ။
   * - **Extent** **(နယ်ပယ်အကျယ်အဝန်း)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``EXTENT``
     - [extent]

       Default: Not set
     - ပုံဖော်ပြသသော မြေပုံ ဧရိယာ၏ အများဆုံး extent ။ Zoom အဆင့်အားလုံး လွှမ်းခြုံသော ဧရိယာတစ်ခုကို သတ်မှတ်ရပါမည်။
   * - **Output directory** **(ရလာဒ် ထားရှိမည့်လမ်းကြောင်း)**
     - ``OUTPUT_DIRECTORY``
     - [folder]

       Default: [Save to temporary folder]
     - Output vector tiles folder ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့မှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Output directory** **(ရလာဒ် ထားရှိမည့်လမ်းကြောင်း)**
     - ``OUTPUT_DIRECTORY``
     - [folder]
     - Zoom အဆင့်များအလိုက် folder အခွဲများထဲတွင် သိမ်းဆည်းထားသည့် Vector tiles ဖိုင် အစု (subset) များ (:file:`.pbf`) အမျိုးမျိုးပါဝင်သည့် folder တစ်ခု။

Python code
...........

**Algorithm ID**: ``native:writevectortiles_xyz``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |332| replace:: ``NEW in 3.32``
