.. _`label_meshdata`:

*********************************************************************
Working with Mesh Data (Mesh Data များနှင့် အလုပ်လုပ်ခြင်း) 
*********************************************************************

.. only:: html

   .. contents::
      :local:

What's a mesh? (Mesh ဆိုတာဘာလဲ)
================================

Mesh တစ်ခုဆိုသည်မှာ အချိန်ဆိုင်ရာ နှင့်တခြား အစိတ်အပိုင်းများပါရှိသည့် unstructured gird (ဖွဲ့စည်းပုံမရှိသောအကွက်) တစ်ခုကို ခေါ်ပါသည်။ တည်နေရာဆိုင်ရာ အစိတ်အပိုင်း (Spatial component) တွင် vertex (မျဉ်းအဆစ်) များ၊ edge (အနားသတ်) များ နှင့်/သို့မဟုတ် surface (မျက်နှာပြင်) များ စုစည်းမှုတစ်ခုသည် 2D သို့မဟုတ် 3D အနေဖြင့် ပါရှိပါသည်- 

* **vertices (မျဉ်းအဆစ်များ)** - XY(Z) အမှတ်များ (layer ၏ coordinate reference system ထဲတွင်)
* **edges (အနားသတ်များ)** သည် Vertex ၂ ခုကို ဆက်ထားပါသည်။
* **faces (မျက်နှာပြင်များ)** - အပိတ်ပုံသဏ္ဍာန်ဖြစ်ပေါ်စေသော Edge (အစွန်း) များကို ဆက်ထားသော အစုအဖွဲ့ကို ဆိုလိုသည်။ များသောအားဖြင့် တြိဂံ သို့မဟုတ် လေးထောင့်ပုံ ဖြစ်ပြီး vertex ပိုများသော polygon များလည်း ရှိတတ်ပါသည်။

ထို့ကြောင့် mesh layer များသည် ပုံသဏ္ဍာန်အမျိုးမျိုးရှိနိုင်ပါသည်-

* ၁ ဘက်မြင် (1D) Mesh များ - Vertex များ နှင့် edge များပါဝင်ပါသည်။ Edge တစ်ခုသည် vertex နှစ်ခုကို ဆက်ထားခြင်းဖြစ်ပြီး ၎င်းပေါ်တွင် data (scalar သို့မဟုတ် vector) များသတ်မှတ်ပေးနိုင်ပါသည်။ ဥပမာ 1D mesh ကို မြို့ပြ၏ရေနှုတ်မြောင်းစနစ်တစ်ခု ရေးဆွဲရာတွင် အသုံးပြုနိုင်ပါသည်။
* ၂ ဘက်မြင် (2D) Mesh များ - တြိဂံများ၊ ပုံမှန် သို့မဟုတ် ဖွဲ့စည်းပုံမရှိသော လေးထောင့်ကွက်များပါဝင်သော မျက်နှာပြင်များကို ဆိုလိုပါသည်။
* ၃ ဘက်မြင် (3D) Mesh များ - ဖွဲ့စည်းပုံမရှိသော 2D mesh များစွာကို ထပ်ထားပြီး တစ်ခုစီကို ဒေါင်လိုက် ကိုဩဒိနိတ်တစ်ခုဖြင့် ဒေါင်လိုက် (vertical) လားရာ (level - အဆင့်) အတိုင်း ထုထည်ဖော်ထားပါသည်။ Vertical အဆင့် တစ်ခုချင်းစီတွင် vertex များနှင့် surface များသည် တူညီသည့် topology (ဆက်စပ်တည်ရှိမှုအရဖွဲ့စည်းပုံ) ရှိကြပါသည်။ ယေဘုယျအားဖြင့် Mesh အဓိပ္ပါယ်ဖွင့်ဆိုချက် (vertical အဆင့် ထုထည်ဖော်ခြင်း) သည် အချိန်အရပြောင်းလဲနိုင်ပါသည်။ Data ကို ထုထည်ဗဟို သို့မဟုတ် parametric function (သတ်မှတ်ချက်ဖြင့်လုပ်ဆောင်ခြင်း) တချို့ဖြင့် သတ်မှတ်လေ့ရှိပါသည်။

.. _figure_mesh_grid_types:

.. figure:: img/mesh_grid_types.png
   :align: center

   မတူညီသော Mesh အမျိုးအစားများ

Mesh သည် တည်နေရာဆိုင်ရာ ဖွဲ့စည်းမှုများ (spatial structure) များအတွက် သတင်းအချက်အလက်များကို ထောက်ပံ့ပေးပါသည်။ ထို့အပြင် mesh သည် vertex တိုင်းအတွက် တန်ဖိုးသတ်မှတ်ထားသော dataset (data အစုအဖွဲ့များ) လည်းရှိပါသည်။ ဥပမာ- အောက်ပါပုံတွင်ပြထားသည့်အတိုင်း နံပါတ်တပ်ထားသော vertex များဖြင့် တြိဂံ mesh တစ်ခုရှိခြင်း-

.. _figure_triangual_grid_with_numered_vertices:

.. figure:: img/triangual_grid_with_numered_vertices.png
   :align: center

   နံပါတ်တပ်ထားသော vertex များဖြင့် တြိဂံ grid

Vertex တစ်ခုစီတိုင်းသည် မတူညီသည့် dataset (ပမာဏများများ) ကိုသိမ်းဆည်းထားနိုင်ပြီး ၎င်း dataset များတွင် အချိန် dimension (ရှုထောင့်) တစ်ခုလည်း ရှိနိုင်ပါသည်။ ထို့ကြောင့် file တစ်ခုတွင် များစွာသော dataset များပါဝင်နိုင်ပါသည်။

အောက်ပါဇယားသည် mesh dataset များတွင် သိမ်းဆည်းထားနိုင်သော သတင်းအချက်အလက်များကို ဖော်ပြပေးပါသည်။ ဇယား၏ အတိုင်များ (columns) သည် mesh vertex များ၏ index များကို ကိုယ်စားပြုပြီး အတန်း (row) တစ်ခုချင်းဆီသည် dataset တစ်ခုကို ကိုယ်စားပြုပါသည်။ Dataset များတွင် data အမျိုးအစား အမျိုးမျိုးရှိနိုင်ပါသည်။ ယခုဥပမာတွင် dataset သည် အချိန် (t1 ၊ t2 ၊ t3) အတွင်း ကာလတစ်ခုစီရှိ 10 မီတာ လေတိုက်နှုန်းများကို သိမ်းဆည်းထားပါသည်။

အလားတူစွာ Mesh dataset များသည် vertex တစ်ခုချင်းစီအတွက် vector တန်ဖိုးများကိုလည်း သိမ်းဆည်းနိုင်ပါသည်။ ဥပမာ အချိန်တစ်ခုတွင် လေတိုက်သည့်လားရာကိုပြသသည့် vector (wind direction vector)-

.. table:: Mesh dataset ဥပမာ

  =============================== ========= ========= ========= =====
  10 metre wind                   1         2         3         ...
  =============================== ========= ========= ========= =====
  10 metre speed at time=t1       17251     24918     32858     ...
  10 metre speed at time=t2       19168     23001     36418     ...
  10 metre speed at time=t3       21085     30668     17251     ...
  ...                             ...       ...       ...       ...
  10m wind direction time=t1      [20,2]    [20,3]    [20,4.5]  ...
  10m wind direction time=t2      [21,3]    [21,4]    [21,5.5]  ...
  10m wind direction time=t3      [22,4]    [22,5]    [22,6.5]  ...
  ...                             ...       ...       ...       ...
  =============================== ========= ========= ========= =====

တန်ဖိုးများကို အရောင်သတ်မှတ်ပေးပြီး data များကို ကြည့်ရှုနိုင်ပါသည် (:ref:`Singleband pseudocolor <label_colormaptab>` raster အရောင်ခြယ်ပုံဖော်ပြသခြင်း (rendering) ဖြင့်လုပ်ဆောင်ခြင်းနှင့် ဆင်တူပါသည်)။ ထို့အပြင် mesh topology အရ vertex များအကြား data များကို interpolate (တွက်ချက်ဖြည့်စွက်ခြင်း) ပြုလုပ်ခြင်းဖြင့် ကြည့်ရှုနိုင်ပါသည်။ တချို့ အရေအတွက်များသည် ရိုးရှင်းသည့် scale တန်ဖိုးဖြစ်ခြင်းထက် 2D vector များဖြစ်ကြသည်မှာ များပါသည်။ (ဥပမာ- လေတိုက်သည့်လားရာ)။ အဆိုပါ အရေအတွက်များအတွက် လားရာကိုညွှန်ပြနေသည့် မြှားများဖြင့် ဖော်ပြတတ်ကြပါသည်။

.. _figure_mesh_visualisation:

.. figure:: img/mesh_visualisation.png
   :align: center

   Mesh data များကို ပုံဖော်ကြည့်ရှုနည်း

.. _mesh_supported_formats:

Supported formats (အသုံးပြုနိုင်သော format များ)
=================================================

QGIS သည် `MDAL drivers <https://github.com/lutraconsulting/MDAL>`_ ကိုအသုံးပြုပြီး mesh data များကို ရယူအသုံးပြုပြီး `formats အမျိုးမျိုး <https://github.com/lutraconsulting/MDAL#supported-formats>`_ ကိုလည်း အသုံးပြုနိုင်ပါသည်။ QGIS သည် mesh layer ကို တည်းဖြတ်ပြင်ဆင်မှု လုပ်နိုင်/မလုပ်နိုင် ဆိုသည်မှာ အသုံးပြုထားသော format နှင့် mesh တည်ဆောက်ပုံ အမျိုးအစားတို့အပေါ်တွင် မူတည်ပါသည်။

QGIS ထဲသို့ mesh dataset တစ်ခုထည့်သွင်းရန် :guilabel:`Data Source Manager` dialog ထဲမှ |addMeshLayer| :guilabel:`Mesh` tab ကိုအသုံးပြုပါ။ :ref:`mesh_loading` တွင် ပိုမို၍အသေးစိတ်ဖတ်ရှုနိုင်ပါသည်။

.. _`label_meshproperties`:

Mesh Dataset Properties (Mesh dataset ၏ ဂုဏ်သတ္တိများ)
=======================================================

Mesh layer ၏ :guilabel:`Layer Properties` dialog တွင် layer ၏ dataset အုပ်စုများကို စီမံခန့်ခွဲခြင်းနှင့် ၎င်းတို့ကို ပုံဖော်ပြသခြင်း (dataset အုပ်စုများ၊ symbology၊ 2D နှင့် 3D ပုံဖော်ပြသခြင်း) များ လုပ်ဆောင်နိုင်ရန် အထွေထွေ setting များပါရှိပါသည်။ Layer နှင့်ပတ်သက်သော သတင်းအချက်အလက်များလည်း ပါဝင်ပါသည်။

:guilabel:`Layer Properties` dialog ကို အသုံးပြုနိုင်ရန် - 

* :guilabel:`Layers` panel ထဲတွင် layer ပေါ်ကို double-click သို့မဟုတ် right-click နှိပ်ပြီး ပေါ်လာသည့် menu မှ :guilabel:`Properties...` ကို ရွေးချယ်ပါ။
* Layer ကိုရွေးချယ်ထားပြီး :menuselection:`Layer --> Layer Properties...` ကို သွားပါ။

Mesh :guilabel:`Layer Properties` dialog တွင် အောက်ပါတို့ပါဝင်ပါသည်-

.. list-table:: Mesh Layer ဂုဏ်သတ္တိများ၏ tab များ

   * - |metadata| :ref:`Information <meshinformation>`
     - |system| :ref:`Source <meshsource>`
     - |symbology| :ref:`Symbology <meshsymbology>`:sup:`[1]`
   * - |3d| :ref:`3D View <mesh3dview>`:sup:`[1]`
     - |temporal| :ref:`Temporal <meshtemporal>`
     - |elevationscale| :ref:`Elevation <meshelevation>`
   * - |rendering| :ref:`Rendering <meshrendering>`
     - |editMetadata| :ref:`Metadata <meshmetadata>`
     -


:sup:`[1]` :ref:`Layer styling panel <layer_styling_panel>` တွင်လည်း ရရှိနိုင်ပါသည်။

.. note:: 
   Dialog ၏ အောက်ခြေရှိ :guilabel:`Style` menu ကိုအသုံးပြုပြီး mesh layer ၏ properties အများစုကို :file:`.qml` file အဖြစ် သိမ်းဆည်းထားနိုင်သလို သိမ်းဆည်းထားသည့် :file:`.qml` file မှလည်း ယူသုံးနိုင်ပါသည်။ :ref:`manage_custom_style` တွင် အသေးစိတ်ဖတ်ရှုနိုင်ပါသည်။
 

.. _meshinformation:

Information Propertie (သတင်းအချက်အလက်ဆိုင်ရာ ဂုဏ်သတ္တိများ)
------------------------------------------------------------

.. _figure_mesh_info_properties:

.. figure:: img/mesh_info_properties.png
   :align: center

   Mesh Layer ၏ သတင်းအချက်အလက်ဆိုင်ရာ ဂုဏ်သတ္တိများ

|metadata| :guilabel:`Information` tab သည် ဖတ်ရှုနိုင်ရုံသာဖြစ်ပြီး လက်ရှိ layer ၏ အကျဉ်းချုပ် သတင်းအချက်အလက်များကို အမြန်ဆုံးဖော်ပြပေးနိုင်သော နေရာတစ်ခုဖြစ်ပါသည်။ သိနိုင်သော သတင်းအချက်အလက်များမှာ - 

* Project ထဲရှိ အမည်၊ file တစ်ခု၏ မူလလမ်းကြောင်းနေရာ၊ အရန် file များစာရင်း၊ နောက်ဆုံးသိမ်းဆည်းခဲ့သော အချိန်နှင့် အရွယ်အစား၊ data ပံ့ပိုးပေးသူ ကဲ့သို့သော အခြေခံ အချက်အလက်များ။
* Layer ၏ ပံ့ပိုးသူပေါ်မူတည်၍ - အကျယ်အဝန်း (extent) ၊ vertex ၊ မျက်နှာပြင် (face)၊ edge များနှင့်/သို့မဟုတ် dataset အုပ်စုအရေအတွက်
* Coordinate Reference System - အမည်၊ ယူနစ်များ၊ နည်းလမ်း၊ တိကျမှု၊ အကိုးအကား (ပုံသေအငြိမ်ဖြစ်သော (static) သို့မဟုတ် ပြောင်းလဲနိုင်သော (dynamic) ကိုဆိုလိုပါသည်)
* ဖြည့်သွင်းထားသော :ref:`metadata <meshmetadata>` မှ ထုတ်ယူထားသော - အသုံးပြုခွင့်၊ အကျယ်အဝန်း၊ အချိတ်အဆက်များ (links)၊ အဆက်အသွယ်၊ data ၏သမိုင်းကြောင်း၊ အစရှိသည်....


.. _meshsource:

Source Properties (အရင်းအမြစ်ဆိုင်ရာ ဂုဏ်သတ္တိများ)
----------------------------------------------------

|system| :guilabel:`Source` tab သည် ရွေးချယ်ထားသည့် mesh နှင့်ပတ်သက်သော အခြေခံသတင်းအချက်အလက်များကို ဖော်ပြပေးပါသည်။ ဖော်ပြပေးသော အချက်အလက်များမှာ - 

.. _figure_mesh_source:

.. figure:: img/mesh_source.png
   :align: center

   Mesh Layer အရင်းအမြစ်ဆိုင်ရာ ဂုဏ်သတ္တိများ

* :guilabel:`Layers` panel တွင်ပြသပေးသော layer အမည်
* Coordinate Reference System နှင့်ပတ်သက်သော setting များ - :ref:`လက်ရှိအသုံးပြုနေသော Coordinate Reference System (CRS) <layer_crs>` ကိုပြသပေးပါသည်။ Drop-down list မှတဆင့် မကြာသေးခင်က အသုံးပြုခဲ့သော CRS တစ်ခုကို ‌ရွေးချယ်ခြင်း သို့မဟုတ် |setProjection| :guilabel:`Select CRS` ခလုတ်ကိုနှိပ်ပြီး layer ၏ CRS ကိုပြောင်းလဲနိုင်ပါသည် (:ref:`crs_selector` တွင်ကြည့်ပါ)။ လက်ရှိအသုံးပြုနေသော CRS က မှားနေသောအခါ သို့မဟုတ် မည်သည့် CRS မှ သတ်မှတ်မထားသည့်အခါများတွင်သာ ဒီနည်းလမ်းကို အသုံးပြုရပါမည်။
* :guilabel:`Available datasets` frame သည် mesh layer ထဲရှိ dataset အုပ်စုအားလုံး (အုပ်စုခွဲများအပါအဝင်) ကို ၎င်းတို့၏ အမျိုးအစားနှင့် ဖော်ပြချက်များကို စာရင်းပြုစုပါသည်။ ဖိုင်ထဲတွင်သိမ်းဆည်းပေးထားသော ပုံမှန် dataset များနှင့် လုပ်ဆောင်နေစဉ်တွင် ယာယီဖန်တီးပေးသည့် virtual dataset (:ref:`on-the-fly တွက်ချက်ပေးသော <mesh_calculator>`) များကိုလည်း စာရင်းပြုစုပေးပါသည်။

  * လက်ရှိ mesh layer ကို အုပ်စုအသစ်များထပ်ထည့်ရန် |add| :guilabel:`Assign extra dataset to mesh` ခလုတ်ကိုနှိပ်ပါ။
  * အဆင့်ဆင့်ထည့်သွင်းထားသည့် အစုအဖွဲ့များရှိသည့်အခါ အားလုံးကို အကျယ်ဖြန့်ကြည့်ခြင်းနှင့် အားလုံးကို ပြန်စုစည်းခြင်းအတွက် :guilabel:`အားလုံးကို ပြန်စုစည်းပါ (Collapse all)` နှင့် |expandTree| :guilabel:`အားလုံးကိုအကျယ်ဖြန့်ပါ (Expand all)` ကို အသုံးပြုပါ။
  * Dataset အနည်းအကျဉ်းကိုသာ အသုံးပြုလိုလျှင် မလိုသည်များကို ဖြုတ်ထားပြီး project ထဲတွင် မပေါ်အောင် လုပ်ထားပါ။
  * နာမည်ပေါ်တွင် double-click နှိပ်ပြီး dataset ကို နာမည်အသစ်ပေးနိုင်ပါသည်။
  * |refresh| :guilabel:`Reset to defaults` - အစုအဖွဲ့များအားလုံးကို အမှန်ခြစ် ခြစ်ထားပြီး သူတို့၏ မူရင်းနာမည်အဖြစ် ပြန်ပြောင်းလဲပါသည်။
  * Virtual dataset အုပ်စုပေါ်တွင် right-click နှိပ်ပြီး အောက်ပါတို့ကို လုပ်ဆောင်နိုင်ပါသည် -

    * Project မှ :guilabel:`Remove dataset group` (Dataset အုပ်စုကိုဖယ်ထုတ်ပါ)
    * :guilabel:`Save dataset group as...` ကိုနှိပ်ပြီး အသုံးပြုလို့ရသော format ထဲက နှစ်သက်ရာကိုရွေးချယ်ပြီး ကွန်ပျူတာထဲတွင် file အသစ်တစ်ခုအဖြစ်သိမ်းဆည်းနိုင်ပါသည်။ အသစ်ရလာသည့် file ကို project ထဲတွင် လက်ရှိအသုံးပြုနေသည့် mesh layer အဖြစ် သတ်မှတ်ပေးပါသည်။
	
* |unchecked| :guilabel:`Treat as static dataset` group ကို အမှန်ခြစ် ခြစ်ထားလျှင် mesh layer ကို ပုံဖော်ပြသနေစဉ်တွင် :ref:`map temporal navigation <maptimecontrol>` (မြေပုံ၏ အချိန်အပိုင်းအခြားဆိုင်ရာ ညွှန်ပြခြင်း) properties ကို လျစ်လျူရှုထားနိုင်ပါသည်။ ဖွင့်ထားသော (active ဖြစ်နေသော) dataset အစုအဖွဲ့တစ်ခုချင်းဆီအတွက် (|symbology| :menuselection:`Symbology -->` |general| :guilabel:`Datasets` tab ထဲတွင် ရွေးချယ်ထားသည့်အတိုင်း) အောက်ပါတို့ကို လုပ်ဆောင်နိုင်ပါသည်-

  * :guilabel:`None` အဖြစ်ထားခြင်း - dataset အစုအဖွဲ့ကို လုံးဝ ပြသပေးမည်မဟုတ်ပါ။
  * :guilabel:`Display dataset` - ဥပမာ- အချိန်ကာလဆိုင်ရာ မပါရှိသည့် "မြေမျက်နှာသွင်ပြင် အနိမ့်အမြင့် (bed elevation)" အတွက်	
  * အချိန်၊ ရက်စွဲ တစ်ခုခုကို ဆွဲထုတ်ခြင်း - ပေးထားသော အချိန်နှင့် ကိုက်ညီသော dataset ကို ပြသခြင်းနှင့် map navigation (မြေပုံ ညွှန်ပြခြင်း) လုပ်နေစဉ်တွင် အငြိမ်ထားခြင်း။	


.. _meshsymbology:

Symbology Properties (သင်္ကေတဆိုင်ရာ ဂုဏ်သတ္တိများ)
----------------------------------------------------

Symbology dialog ကိုဖွင့်ရန် |symbology| :guilabel:`Symbology` ခလုတ်ကိုနှိပ်ပါ။ Symbology properties ထဲတွင် tab များစွာခွဲထားပါသည်-

* :ref:`Datasets <mesh_symbology_datasets>`
* :ref:`ကွန်တိုများ (Contours) <mesh_symbology_contours>`
* :ref:`Vectors <mesh_symbology_vectors>`
* :ref:`ပုံဖော်ပြသခြင်း (Rendering) <mesh_symbology_rendering>`
* :ref:`ထပ်ထားသော mesh များကို ပျမ်းမျှပြုလုပ်ခြင်းနည်းလမ်း (Stacked mesh averaging method) <mesh_stacked_averaging>` တို့ဖြစ်ကြပါသည်။

.. _mesh_symbology_datasets:

Datasets
.........

|general| :sup:`Datasets` tab သည် ထိန်းချုပ်ခြင်းနှင့် layer အတွက် မည်သည့် dataset များအသုံးပြုမည်ဆိုသည်ကို ထိန်းချုပ်ရန်နှင့် သတ်မှတ်ရန် အဓိကနေရာဖြစ်ပါသည်။ အောက်ပါအချက်များပါဝင်ပါသည်-

* :guilabel:`Groups` available in the mesh dataset, with whether they provide:
* Mesh dataset ထဲတွင် :guilabel:`Groups` (အစုအဖွဲ့များ) ပါဝင်ပြီး အောက်ပါနှစ်မျိုးထဲမှ တစ်မျိုးမျိုးဖြင့် ထောက်ပံ့ပေးထားပါသည်-

  * |meshcontoursoff| scalar dataset သို့မဟုတ်
  * |meshvectorsoff| vector dataset - ပုံမှန်အားဖြင့် vector dataset တစ်ခုစီတွင် အလိုအလျောက်ဖန်တီးပေးသည့် ၎င်း၏ပမာဏကို ကိုယ်စားပြုသည့် scalar dataset တစ်ခုရှိပါသည်။

  ကိုယ်စားပြုမည့် Data အစုအဖွဲ့နှင့် အမျိုးအစားကို ‌ရွေးချယ်ရန် dataset နာမည်ဘေးတွင်ရှိသော သင်္ကေတ (icon) ကိုနှိပ်ပါ။

* :guilabel:`ရွေးချယ်ထားသော dataset အစုအဖွဲ့များ၏ metadata` တွင် အောက်ပါအသေးစိတ်များပါဝင်ပါသည်-

  * Mesh အမျိုးအစား - Edge များ သို့မဟုတ် face များ
  * Data အမျိုးအစား - Vertex များ ၊ edge များ ၊ face များ သို့မဟုတ် ထုထည်
  * Vector အမျိုးအစား ဟုတ်၊ မဟုတ်
  * Mesh layer ထဲရှိ မူရင်းနာမည်
  * ယူနစ် (အသုံးပြုလို့ရလျှင်)
* ရွေးချယ်ထားသော dataset များအတွက် ရရှိနိုင်သော :ref:`blending mode <blend-modes>` (ရောစပ်ခြင်းနည်းလမ်းများ)

.. _figure_mesh_symbology_datasets:

.. figure:: img/mesh_symbology_datasets.png
   :align: center

   Mesh Layer Dataset များ


နောက်ထပ် tab များကိုအသုံးပြုပြီး ရွေးချယ်ထားသော vector နှင့်/သို့မဟုတ် scalar အစုအဖွဲ့များတွင် symbology ကိုအသုံးချနိုင်ပါသည်။

.. _mesh_symbology_contours:

Contours Symbology (ကွန်တို သင်္ကေတဆိုင်ရာများ)
................................................

.. note:: |general| :guilabel:`Datasets` tab ထဲတွင် scalar dataset တစ်ခုခုကိုရွေးချယ်ထားမှသာ |meshcontours| :sup:`Contours` tab ကို အသုံးပြုနိုင်ပါသည်။

အောက်ပါ :numref:`figure_mesh_symbology_contours` တွင်ပြသထားသည့်အတိုင်း ရွေးချယ်ထားသော အစုအဖွဲ့အတွက် ကွန်တိုများ၏ လက်ရှိ အသွင်အပြင်များကို |meshcontours| :sup:`Contours` tab ထဲတွင် မြင်နိုင်၊ ပြောင်းလဲနိုင်ပါသည်-

.. _figure_mesh_symbology_contours:

.. figure:: img/mesh_symbology_contours.png
   :align: center

   Mesh Layer တစ်ခုထဲတွင် ကွန်တိုများကို style ပြင်ဆင်ခြင်း

* 1D mesh အတွက် edge များ၏ :guilabel:`Stroke width (လိုင်းအထူ)` ကိုသတ်မှတ်ပါ။ Dataset တစ်ခုလုံးအတွက် ပုံသေအရွယ်အစားဖြစ်နိုင်သလို ဂျီဩမေတြီ တစ်လျှောက်ပြောင်းလဲခြင်းလည်း ဖြစ်နိုင်ပါသည် (:ref:`interpolated line renderer <interpolated_line_symbol>` တွင် အသေးစိတ်ဖတ်ရှုနိုင်ပါသည်။)
* 2D mesh အမျိုးအစားဖြစ်လျှင် လက်ရှိအသုံးပြုနေသော အစုအဖွဲ့၏  :guilabel:`Opacity (အလင်းပိတ်နှုန်း)` ကို သတ်မှတ်ရန် ဘယ်ညာရွေ့နိုင်သည့် slider ကို အသုံးပြုပါ သို့မဟုတ် ဘေးရှိ spinbox တွင် ဂဏန်းတန်ဖိုးကို ထည့်ပေးပါ။
* လက်ရှိအစုအဖွဲ့အတွက် အသုံးပြုလိုသော တန်ဖိုးအပိုင်းအခြားများကို ရိုက်ထည့်ပါ။ လက်ရှိအသုံးပြုနေသော အစုအဖွဲ့၏ အနည်းဆုံး နှင့် အများဆုံး တန်ဖိုးများကို တွက်ထုတ်ရန် |refresh| :sup:`Load` ကို အသုံးပြုပါ သို့မဟုတ် တချို့သောတန်ဖိုးများ မပါဝင်လိုလျှင် စိတ်ကြိုက်တန်ဖိုးကိုရိုက်ထည့်ပါ။
* 2D/3D mesh များအတွက် :guilabel:`Neighbour average` နည်းလမ်းကိုအသုံးပြုပြီး ပတ်ပတ်လည်ရှိ vertex များပေါ်ရှိတန်ဖိုးများမှ face များသို့ interpolate ပြုလုပ်ရန် :guilabel:`Resampling method` ကိုရွေးချယ်ပါ (သို့မဟုတ် ပတ်ပတ်လည် face များမှ vertex များသို့)။ Dataset သည် vertex များပေါ်တွင် (သို့မဟုတ် face များပေါ်တွင်) သတ်မှတ်ထား/မထား ပေါ်မူတည်ပြီး QGIS သည် vertex များပေါ်ရှိတန်ဖိုးများကို အသုံးပြုရန်နှင့် မူရင်းပုံဖော်ပြသခြင်းကို ချော‌ချောမွေ့မွေ့ဖြစ်စေရန် ဤ setting ကို :guilabel:`None` (face များပေါ်တွင် ဖြစ်လျှင် :guilabel:`Neighbour average` အဖြစ်) အဖြစ်သတ်မှတ်ပေးပါသည်။ 
* Dataset ကို :ref:`color ramp shader <color_ramp_shader>` အတန်းအစားခွဲခြားခြင်း (classification) ကို အသုံးပြု၍ အတန်းအစားခွဲခြား (Classify) ပါ။

.. _mesh_symbology_vectors:

Vectors Symbology (Vector သင်္ကေတဆိုင်ရာများ)
..............................................

.. note:: |general| :guilabel:`Datasets` tab ထဲတွင် vector dataset တစ်ခုခုကိုရွေးချယ်ထားမှသာ |meshvectors| :sup:`Vectors` tab ကိုအသုံးပြုနိုင်ပါမည်။

အောက်ပါ :numref:`figure_mesh_symbology_vectors` တွင်ပြထားသည့်အတိုင်း တွင်ပြသထားသည့်အတိုင်း ရွေးချယ်ထားသော အစုအဖွဲ့အတွက် ကွန်တိုများ၏ လက်ရှိ အသွင်အပြင်များကို |meshvectors| :sup:`Vectors` tab ထဲတွင် မြင်နိုင်၊ ပြောင်းလဲနိုင်ပါသည်-

.. _figure_mesh_symbology_vectors:

.. figure:: img/mesh_symbology_vectors.png
   :align: center

   Mesh Layer တစ်ခုထဲတွင် Vector များကို မြှားများဖြင့် style ပြင်ဆင်ခြင်း

Mesh vector dataset ကို :guilabel:`Symbology` အမျိုးအစားအမျိုးမျိူးသုံးပြီး style ပြင်ဆင်နိုင်ပါသည် -

* **Arrows (မြှားများ)** - Vector များကို raw datset (element များ၏ node များ သို့မဟုတ် အလယ်ဗဟိုကို ဆိုလိုသည်) တွင်သတ်မှတ်ထားသောကြောင့် သို့မဟုတ် အသုံးပြုသူသတ်မှတ်ပေးသည့် grid ပေါ်တွင် (အချိုးညီဖြန့်ဝေထားသည်) သတ်မှတ်ထားသောကြောင့် တူညီသည့်နေရာတွင် vector များကို မြှားများဖြင့်ကိုယ်စားပြုပါသည်။ မြှား၏အရှည်သည် raw data တွင် သတ်မှတ်ထားသည့်အတိုင်း မြှား၏ပမာဏနှင့် အချိုးကျပါသည်။ သို့သော် နည်းလမ်းများစွာဖြင့် scale ချိန်ညှိနိုင်ပါသည်။
* **Streamlines (အဆက်မပြတ်ရွေ့လျားလိုင်းများ)** - Vector များကို အစမှတ်မှ စတင်ကာ streamline များဖြင့်ကိုယ်စားပြုပါသည်။ အစမှတ်များသည် mesh ၏ vertex များမှ အစပျိုးနိုင်သလို အသုံးပြုသူ ဖန်တီးထားသော grid သို့မဟုတ် ကျပန်းအနေဖြင့် စတင်နိုင်ပါသည်။ 
* **Traces** - Streamline များ၏ ပိုကောင်းသည့် လှုပ်ရှားမှု animation ဖြစ်ပါသည်။ ရေထဲကို သဲများ ပစ်ထည့်လိုက်သည့်အခါ သဲများမည်သည့်နေရာသို့ စီးကျသွားသည်ကို ကြည့်ရသည့် effect မျိုးဖြစ်ပါသည်။

အောက်ပါ ဇယားတွင် ပြထားသည့်အတိုင်း အသုံးပြုနိုင်သော property များသည် ရွေးချယ်ထားသည့် symbology ပေါ်တွင် မူတည်ပါသည်။


.. list-table:: Vector symbology property များ၏အသုံးပြုနိုင်မှု နှင့် အဓိပ္ပါယ်
   :header-rows: 1
   :widths: 20 100 20 20 20
   :class: longtable

   * - အညွှန်း
     - ရှင်းလင်းဖော်ပြချက်နှင့် ဂုဏ်သတ္တိများ
     - Arrow
     - Streamlines
     - Traces
   * - :guilabel:`Line width`
     - Vector ကိုယ်စားပြုများ၏ အကျယ်
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Coloring method`
     - * Vector များအားလုံးကို သတ်မှတ်ပေးသော :guilabel:`Single color` (အရောင်တစ်မျိုးတည်း) တစ်ခု
       * သို့မဟုတ် :ref:`Color ramp shader <color_ramp_shader>` ကို အသုံးပြုပြီး vector များ၏ ပမာဏပေါ်မူတည်ပြီး ပြောင်းလဲနိုင်သော အရောင်
     - |checkbox|
     - |checkbox|
     - |checkbox|
   * - :guilabel:`Filter by magnitude`
     -   :guilabel:`အနည်းဆုံး` နှင့် :guilabel:`အများဆုံး` တန်ဖိုး အပိုင်းအခြားအတွင်းဝင်သော ရွေးချယ်ထားသည့် dataset အတွက် အလျားပါရှိသော vector များကိုသာ ပြသပေးသည်။
     - |checkbox|
     - |checkbox|
     -
   * - :guilabel:`Display on user grid`
     - :guilabel:`X spacing` နှင့် :guilabel:`Y spacing` တို့ကို စိတ်ကြိုက်တန်ဖိုး ပေးထားသည့် grid ကွက်ပေါ်တွင် vector ကို နေရာချထားလိုက်ပြီး ပတ်ဝန်းကျင်ရှိ အရာများပေါ်အခြေခံပြီး ၎င်းတို့၏ အလျားကို တွက်ထုတ်ပါသည်။
     - |checkbox|
     - |checkbox|
     -
   * - :guilabel:`Head options`
     - မြှားတံ၏အရိုးအရှည်၏ ရာခိုင်နှုန်းပေါ်မူတည်ပြီး မြှားခေါင်း၏ :guilabel:`အလျား` နှင့် :guilabel:`အကျယ်` ကို သတ်မှတ်ပါသည်။
     - |checkbox|
     -
     -
   * - :guilabel:`Arrow length`
     - * **အနည်းဆုံး/အများဆုံးတန်ဖိုးဖြင့် သတ်မှတ်ခြင်း**- မြှားအရှည်အတွက် အနည်းဆုံး/အများဆုံး တန်ဖိုးများကို သတ်မှတ်ပေးပြီး အသုံးပြုနေသော vector ၏ ပမာဏပေါ်အခြေခံပြီး QGIS သည် မြှား၏အရွယ်အစားကိုတွက်ထုတ်ပေးပါသည်။
       * **ပမာဏနှင့် အချိုးကျခြင်း** - မြှား၏အရှည်သည် ၎င်း၏ vector ပမာဏနှင့် အချိုးကျပါသည်။
       * **ပုံသေအရွယ်အစား** - Vector များအားလုံးကို တူညီသောမြှားအရှည်ဖြင့် ပြပါသည်။
     - |checkbox|
     -
     -
   * - :guilabel:`Streamlines seeding method`
     - * **mesh/grid ကွက်ပေါ်တွင်**- Vector များကို ပြသရန် အသုံးပြုသူဖန်တီးထားသည့် grid ကွက်ပေါ်တွင် အမှီပြုထားပါသည်။
       * **ကျပန်း**- အရမ်းသိပ်သည်းမနေအောင် vector များကို ကျပန်းနေရာချပေးပါသည်။
     -
     - |checkbox|
     -
   * - :guilabel:`Particles count`
     - ပုံဖော်ကြည့်ရှုသည့်အထဲတွင် ထည့်ချင်သော 'sand' ပမာဏ။
     -
     -
     - |checkbox|
   * - :guilabel:`Max tail length`
     - Particle များပျောက်ကွယ်မသွားခင်ထိ အချိန်။
     -
     -
     - |checkbox|

.. _mesh_symbology_rendering:

Rendering (ပုံဖော်ပြသခြင်း)
............................

|meshframe| :sup:`Rendering` tab ထဲတွင် mesh structure ကို ပြသနိုင်သလို စိတ်ကြိုက်ပြင်ဆင်နိုင်ပါသည်။ :guilabel:`Line အထူ` နှင့် :guilabel:`Line အရောင်` များအား အောက်ပါတို့ကို ကိုယ်စားပြုရန်အတွက် သတ်မှတ်နိုင်ပါသည်-

* 1D mesh များအတွက် edge များ
* 2D mesh များအတွက် - 

  * :guilabel:`Native mesh rendering` - Layer မှ မူရင်း face များနှင့် edge များကို ပြသပေးပါသည်။
  * :guilabel:`Triangular mesh rendering` - Edge များ ပိုပေါင်းထည့်ပြီး face များကို တြိဂံများအဖြစ် ပြသပေးပါသည်။

.. _figure_mesh_symbology_grid:

.. figure:: img/mesh_symbology_grid.png
   :align: center

   2D Mesh ပုံဖော်ပြသခြင်း


.. _mesh_stacked_averaging:

Stacked mesh averaging method (ထပ်ထားသော mesh များကို ပျမ်းမျှပြုလုပ်ခြင်းနည်းလမ်း)
....................................................................................

၃ ဘက်မြင် (3D) Mesh များတွင် ဖွဲ့စည်းပုံမရှိသော ထပ်ထားသည့် 2D mesh များပါဝင်ပြီး တစ်ခုချင်းစီကို ဒေါင်လိုက် (vertical) ကိုဩဒိနိတ်တစ်ခုအသုံးပြု၍ ဒေါင်လိုက်လားရာ (vertical direction) အတိုင်း ထုထည်ဖော်ထားပါသည်။ Vertical level တစ်ခုချင်းစီတွင် vertex များနှင့် face များသည် တူညီသည့် topology ရှိကြပါသည်။ များသောအားဖြင့် တန်ဖိုးများကို အောက်ခြေ 2d mesh တွင် ပုံမှန်ထပ်ထားသော ထုထည်များပေါ်တွင် သိမ်းဆည်းထားပါသည်။ ၎င်းတို့ကို 2D canvas တွင်ကြည့်ရှုရန် ထုထည် (3D) ပေါ်ရှိ တန်ဖိုးများကို mesh layer တွင် ပြသပေးနိုင်သော face (2D) များပေါ်ရှိ တန်ဖိုးများအဖြစ် ပြောင်းလဲပေးရန်လိုအပ်ပါသည်။ ထိုအရာကို ကိုင်တွယ်နိုင်ရန် |meshaveraging| :sup:`Stacked mesh averaging method` တွင် မတူညီသော averaging/interpolation နည်းလမ်းများ ပါရှိပါသည်။ 

2D dataset များနှင့် ၎င်း၏သက်ဆိုင်သော parameter များ (level index၊ အနက် သို့မဟုတ် အနိမ့်အမြင့် တန်ဖိုးများ) ကိုရရှိရန် နည်းလမ်းကို ရွေးချယ်နိုင်ပါသည်။ နည်းလမ်းတစ်ခုချင်းစီအတွက် အသုံးပြုနည်းဥပမာကို dialog ထဲတွင်ပြသပေးထားပါသည်။ နည်းလမ်းများအကြောင်း ပိုမိုဖတ်ရှုလိုလျှင် https://fvwiki.tuflow.com/index.php?title=Depth_Averaging_Results တွင်ဖတ်ရှုနိုင်ပါသည်။

.. index:: 3D
.. _mesh3dview:

3D View Properties (၃ ဘက်မြင် မြင်ကွင်း ဂုဏ်သတ္တိများ)
-------------------------------------------------------

Mesh layer များကို ၎င်း၏ vertex Z တန်ဖိုးများပေါ်မူတည်ပြီး :ref:`terrain in a 3D map view <scene_configuration>` (၃ ဘက်မြင် မြေမျက်နှာသွင်ပြင်) အဖြစ်အသုံးပြုနိုင်ပါသည်။ |3d| :guilabel:`3D View` properties tab မှလည်း တူညီသော 3D မြင်ကွင်းဖြင့် mesh layer ၏ dataset ကို ပုံဖော်ပြသနိုင်ပါသည်။ ထို့ကြောင့် vertex များ၏ ဒေါင်လိုက် အစိတ်အပိုင်းများကို dataset တန်ဖိုးများ (ဥပမာ- ရေမျက်နှာပြင် level) နှင့်တူအောင်ထားနိုင်ပြီး mesh ၏ အနုအကြမ်းကို အရောင်များဖြင့်ပုံဖော်ပြသရန် တခြား dataset တန်ိဖုးများကို သတ်မှတ်နိုင်ပါသည်။ (ဥပမာ အလျင်)

.. _figure_mesh_3d:

.. figure:: img/mesh_3d.png
   :align: center

   Mesh dataset 3D ဂုဏ်သတ္တိများ

|checkbox| :guilabel:`Enable 3D Renderer` ကို အမှန်ခြစ် ခြစ်ထားပြီး အောက်ပါတို့ကို တည်းဖြတ်ပြင်ဆင်နိုင်ပါသည်-

* :guilabel:`တြိဂံ setting` များအောက်တွင်

  * :guilabel:`Smooth triangles` - 3D ရုပ်ထွက် ပိုကောင်းစေရန်အတွက် ကပ်လျှက်ဖြစ်နေသော တြိဂံ နှစ်ခုကြားက ထောင့်ကို ပြေပြစ်အောင်လုပ်ပေးပါသည်။
  * :guilabel:`လိုင်းအထူ` နှင့် :guilabel:`အရောင်` တို့ကိုသတ်မှတ်ပေးပြီး :guilabel:`Show wireframe` (ဝါယာသဏ္ဍာန်ကွန်ရက်) ကိုပြသနိုင်ပါသည်။
  
  .. _levelofdetail:

  * :guilabel:`Level of detail` - Mesh layer ကို ပုံဖော်ပြသရန် မည်မျှ :ref:`simplified (ရိုးရှင်းအောင်) <meshrendering>` ဖြစ်သင့်သည်ကို ထိန်းချုပ်ပါသည်။ ညာဘက်အဝေးတွင် အခြေခံ mesh ဖြစ်ပြီး ဘယ်ဘက်ကို ပိုရောက်လေလေ layer သည် ပိုမိုရိုးရှင်းသွားလေလေဖြစ်ပြီး အသေးစိတ်ပုံဖော်ပြသမှု ပိုလျော့သွားပါသည်။	:guilabel:`Rendering` tab အောက်ရှိ :guilabel:`Simplify mesh` option ကို ဖွင့်ထားမှသာလျှင် ဤ ရွေးချယ်မှုကို အသုံးပြုနိုင်မည်ဖြစ်သည်။
* :guilabel:`Vertical settings` - ပုံဖော်ပြသထားသည့် တြိဂံ၏ vertex များ၏ ဒေါင်လိုက်အစိတ်အပိုင်းများ၏ အပြုအမူကို ထိန်းချုပ်ရန်ဖြစ်ပါသည်။   

  * :guilabel:`Dataset group for vertical value` - Mesh ၏‌ ဒေါင်လိုက်အစိတ်အပိုင်းများအတွက် အသုံးပြုမည့် dataset အစုအဖွဲ့ဖြစ်ပါသည်။	
  * |unchecked|:guilabel:`Dataset value relative to vertices Z value` - Dataset တန်ဖိုးများကို ပကတိ Z ကိုဩဒိနိတ်အဖြစ် ယူဆမည် သို့မဟုတ် vertex များ၏ မူရင်း Z တန်ဖိုး၏ နှိုင်းရတန်ဖိုးအဖြစ် ယူဆမည်ကို ရွေးချယ်နိုင်ပါသည်။	
  * :guilabel:`Vertical scale` - Dataset Z တန်ဖိုးများအတွက် အသုံးပြုမည့် တန်ဖိုး	
  
* :ref:`mesh_symbology_contours` (:guilabel:`2D contour color ramp shader`) တွင် သတ်မှတ်ထားသည့် color ramp shader ပေါ်တွင် အခြေခံထားသည့် :guilabel:`Rendering style` တစ်ခုဖြင့် :guilabel:`Rendering color settings` သို့မဟုတ် သက်ဆိုင်ရာ :guilabel:`Mesh color` တစ်ခုဖြင့် :guilabel:`Single color` (အရောင်တစ်မျိုးတည်း) အနေဖြင့်၊
* :guilabel:`Show arrows` - :ref:`Vector 2D rendering <mesh_symbology_vectors>` (Vector 2D ပုံဖော်ပြသခြင်း) တွင် အသုံးပြုသော တူညီသည့် vector dataset အစုအဖွဲ့ပေါ်တွင် အခြေခံပြီး mesh layer dataset 3D entity တွင် မြှားတွေကို ပြသပေးပါသည်။ 2D အရောင် setting ကိုအသုံးပြုပြီး ၎င်းတို့ကို ပြသပါသည်။ :guilabel:`Fixed size (ပုံသေအရွယ်အစား)` သို့မဟုတ် ပမာဏပေါ်မူတည်ပြီး စကေးကိုက်ဖြစ်လျှင် :guilabel:`Arrow spacing (မြှားတစ်ခုနှင့်တစ်ခု အကွာ)` ကိုလည်းသတ်မှတ်ပေးနိုင်ပါသည်။ မြှားများသည် တစ်ခုနှင့်တစ်ခု ထပ်နေ၍ မရသောကြောင့် spacing setting တွင် မြှားများ၏ အများဆုံးအရွယ်အစားကိုလည်း သတ်မှတ်ပေးနိုင်သည်။

.. index:: Rendering; Scale dependent visibility
.. _meshrendering:

Rendering Properties (ပုံဖော်ပြသခြင်းဆိုင်ရာ ဂုဏ်သတ္တိများ)
------------------------------------------------------------

.. _figure_mesh_rendering:

.. figure:: img/mesh_rendering.png
   :align: center

   Mesh ပုံဖော်ပြသခြင်းဆိုင်ရာ ဂုဏ်သတ္တိများ

:guilabel:`Scale dependent visibility` (စကေးပေါ်မူတည်သည့် မြင်ရနိုင်မှု) အစုအဖွဲ့ box အောက်တွင် :guilabel:`အများဆုံး (သူ့အောက်ဆိုရင် မြင်ရ)` နှင့် :guilabel:`အနည်းဆုံး (သူ့အောက်ဆိုရင် မမြင်ရ)` စကေးကို သတ်မှတ်ပေးနိုင်ပါသည်။ ၎င်းသည် mesh element များကိုမြင်ရနိုင်သော စကေးအပိုင်းအခြားကို သတ်မှတ်ပေးမည်ဖြစ်သည်။ ထိုစကေးအပိုင်းအခြားအတွင်း မဝင်လျှင် layer များကို မြင်ရမည်မဟုတ်ပါ။ |mapIdentification| :sup:`Set to current canvas scale` (လက်ရှိမြေပုံ canvas စကေးအတိုင်းသတ်မှတ်ခြင်း) ခလုတ်ကိုနှိပ်ပြီး လက်ရှိမြေပုံ canvas စကေးကို မြင်ရနိုင်သည့် စကေးအပိုင်းအခြားအဖြစ်သတ်မှတ်ပေးနိုင်ပါသည်။ ပိုမိုသိရှိလိုသည်များအတွက် :ref:`label_scaledepend` တွင် ကြည့်ရှုပါ။

.. note::

   :guilabel:`Layers` panel ထဲရှိ layer ပေါ်တွင် right-click နှိပ်ပြီး ပေါ်လာသည့် menu တွင် :guilabel:`Set Layer Scale Visibility` ကို ရွေးချယ်ပြီးလည်း ထို layer အတွက် စကေးပေါ်မူတည်သည့် မြင်ရနိုင်မှုကို သတ်မှတ်ပေးနိုင်ပါသည်။

Mesh layer များတွင် face များ သန်းချီပြီး ပါရှိသောကြောင့် ၎င်းတို့ကို ပုံဖော်ပြသရာတွင် တခါတရံ အလွန်နှေးကွေးနိုင်ပါသည်။ အထူးသဖြင့် သေးသယ်သော face များအားလုံးကို မြင်ကွင်းတွင် ပြသရသည့်အခါမျိုးတွင် ဖြစ်တတ်ပါသည်။ ပိုပြီးမြန်ဆန်စေရန် mesh layer ကို ရိုးရှင်းသွားအောင် ပြုလုပ်ခြင်းဖြင့် :ref:`levels of detail (အသေးစိတ်ပြသမှုအဆင့်များ) <levelofdetail>` အမျိုးမျိုးကိုကိုယ်စားပြုသည့် တစ်ခု သို့မဟုတ် တစ်ခုထက်ပိုသော mesh များရရှိလာပြီး မည်သည့် အသေးစိတ်မှုအဆင့်တွင် mesh layer အား QGIS တွင် ပုံဖော်ပြသစေမည်ဆိုသည်ကို ရွေးချယ်နိုင်ပါသည်။ ရိုးရှင်းအောင်လုပ်လိုက်သည့် mesh တွင် တြိဂံ face သာ ပါဝင်မည်ဖြစ်သည်။

|rendering| :guilabel:`Rendering` tab မှ :guilabel:`Simplify mesh` ကို အမှန်ခြစ် ခြစ်ထားပြီး အောက်ပါတို့ကို သတ်မှတ်ပါ -

* a :guilabel:`Reduction factor` (လျှော့ချခြင်း factor) - ရိုးရှင်းအောင်လုပ်ထားသော mesh များ၏ ဆက်တိုက်ဖြစ်နေသော အဆင့်များဖန်တီးခြင်းကို ထိန်းချုပ်ခြင်း။ ဥပမာ- အခြေခံ mesh တွင် face ၅ သန်းရှိပြီး reduction factor ဂဏန်း မှာ ၁၀ ဖြစ်မည်ဆိုလျှင် ပထမအဆင့် ရိုးရှင်းအောင်လုပ်ထားသည့် mesh တွင် ပျှမ်းမျှ face ၅ သိန်းရှိမည်ဖြစ်ပြီး ဒုတိယအဆင့်တွင် face ၅၀၀၀၀ နှင့် တတိယအဆင့်တွင် face ၅၀၀၀ တို့အသီးသီးရှိကြမည် ဖြစ်ပါသည်။ Reduction factor တန်ဖိုးကြီးကြီးဖြင့် mesh များကို မြန်မြန် ရိုးရှင်းအောင် လုပ်လျှင် (တြိဂံအရွယ်အစားပိုကြီးခြင်းကို ဆိုလိုသည်) အသေးစိတ်ပြသမှုအဆင့်များလည်း လျော့သွားမည်ဖြစ်သည်။။   
* :guilabel:`Minimum triangle size` (အသေးဆုံး တြိဂံအရွယ်အစား) - ပြသနိုင်သော တြိဂံများ၏ ပျမ်းမျှအရွယ်အစား (pixel ဖြင့်)။ အကယ်၍ mesh ၏ ပျမ်းမျှအရွယ်အစားသည် ဒီတန်ဖိုးထက် နည်းနေလျှင် အသေးစိတ်ပြသမှုအဆင့် အနိမ့်ဖြင့် ပုံဖော်ပြသမည်ဖြစ်ပါသည်။


.. index:: Temporal
.. _meshtemporal:

Temporal Properties (အချိန်နှင့် ပတ်သက်သော ဂုဏ်သတ္တိများ)
----------------------------------------------------------

|temporal| :guilabel:`Temporal` tab တွင် အချိန်နှင့်အမျှ layer ပုံဖော်ပြသခြင်းကို လုပ်ဆောင်နိုင်ပါသည်။ အသုံးပြုနိုင်သော dataset အစုအဖွဲ့များ၏ အချိန်နှင့်ပတ်သက်သော တန်ဖိုးများကို အမျိုးမျိုးပြသလို့ရပါသည်။ ထိုသို့ အမျိုးမျိုးပုံဖော်ပြသခြင်းအတွက် map canvas တွင် :ref:`temporal navigation <maptimecontrol>` ကိုဖွင့်ထားပေးရန် လိုအပ်ပါသည်။

.. _figure_mesh_temporal:

.. figure:: img/mesh_temporal.png
   :align: center

   Mesh layer ၏ အချိန်နှင့်ပတ်သက်သော ဂုဏ်သတ္တိများ

**Layer temporal settings (Layer ၏ အချိန်နှင့်ပတ်သက်သော setting များ)**

* ပကတိ ရက်စွဲအချိန် တစ်ခုအဖြစ် dataset အစုအဖွဲ့၏ :guilabel:`Reference time` (အချိန်အကိုးအကား)။ ပုံမှန်အားဖြင့် QGIS သည် မူရင်း layer ကိုဖန်တီးပြီး layer ၏ dataset အစုအဖွဲ့ထဲတွင် ပထမဆုံး ဆီလျော်သော အချိန်အကိုးအကားတစ်ခုကို ပြန်ပေးပါသည်။ ထိုသို့ မရရှိခဲ့လျှင် တန်ဖိုးကို project ၏ အချိန်အပိုင်းအခြားဖြင့် သတ်မှတ်မည် သို့မဟုတ် လက်ရှိ ရက်စွဲ ဖြင့် သတ်မှတ်မည်ဖြစ်သည်။ ထို့နောက် dataset ၏ အတွင်းပိုင်း timestamp step များအ‌ပေါ် အခြေခံပြီး :guilabel:`စတင်ချိန်` နှင့် :guilabel:`အဆုံးသတ်ချိန်` ကို တွက်ထုတ်ပေးပါသည်။
  
  စိတ်ကြိုက် :guilabel:`အချိန်အကိုးအကား` (ထို့နောက်တွင် အချိန် အပိုင်းအခြား) ကိုသတ်မှတ်ပေးရန် ဖြစ်နိုင်ပြီး |refresh| :sup:`Reload from provider` ခလုတ်ကိုအသုံးပြုပြီး ပြောင်းလဲထားတာတွေကို မူရင်းအတိုင်းပြန်ထားနိုင်ပါသည်။ |checkbox| :guilabel:`Always take reference time from data source`  (မူရင်း data မှ အချိန်အကိုးအကားကို အမြဲတမ်းယူပါ) ကို အမှန်ခြစ် ခြစ်ထားလျှင် layer ကို ပြန်ထည့်သွင်းတိုင်း သို့မဟုတ် project ကိုပြန်ဖွင့်သည့်အခါတိုင်း အချိန်နှင့်ပတ်သက်သော property များကို file မှယူ၍ update လုပ်ပေးမည်ဖြစ်သည်။ 
* :guilabel:`Dataset matching method` - ပေးထားသည့်အချိန်တွင် dataset ကိုပြသပေးရန် ဆုံးဖြတ်ပေးပါသည်။ ရွေးချယ်စရာများမှာ :guilabel:`Find closest dataset before requested time` (တောင်းဆိုထားသောအချိန်မတိုင်မီ အနီးဆုံး dataset ကိုရှာပါ) သို့မဟုတ် :guilabel:`Find closest dataset from requested time (after or before)` (တောင်းဆိုထားသော အချိန် (မတိုင်မီ သို့မဟုတ် ပြီးနောက်)မှ အနီးဆုံး dataset ကိုရှာပါ) တို့ဖြစ်ကြပါသည်။

**Provider time settings (Provider အချိန်နှင့်ပတ်သက်သော setting များ)**

* :guilabel:`Time unit` ကို မူရင်း data မှ ထုတ်ယူပါသည် သို့မဟုတ် အသုံးပြုသူမှ သတ်မှတ်ပါသည်။ Project ထဲတွင် မြေပုံအချိန်နှင့်ပတ်သက်သော လမ်းညွှန်ခြင်းတွေလုပ်နေစဉ်အတွင်း ဒီနည်းလမ်းကိုအသုံးပြုပြီး mesh layer ၏ အမြန်နှုန်းကို အခြား layer များဖြင့် ညီအောင်ညှိနိုင်ပါသည်။ အသုံးပြုနိုင်သော ယူနစ်များမှာ :guilabel:`Seconds (စက္ကန့်)`၊ :guilabel:`Minutes (မိနစ်)`၊ :guilabel:`Hours (နာရီ)` နှင့် :guilabel:`Days (ရက်)` တို့ဖြစ်ကြပါသည်။

.. index:: Elevation, Terrain
.. _meshelevation:

Elevation Properties (မြေမျက်နှာသွင်ပြင် အနိမ့်အမြင့်ဆိုင်ရာ ဂုဏ်သတ္တိများ)
----------------------------------------------------------------------------

|elevationscale| :guilabel:`Elevation` tab သည် :ref:`3D map view <label_3dmapview>` တစ်ခုအတွင်းရှိ layer ၏ မြေမျက်နှာသွင်ပြင် အနိမ့်အမြင့် property များကို ထိန်းချုပ်နိုင်ပြီး :ref:`profile tool charts <label_elevation_profile_view>` ထဲရှိ ၎င်း၏ အသွင်အပြင်များကိုလည်း မှာထိန်းချုပ်နိုင်ပါသည်။ အတိအကျအားဖြင့် အောက်ပါတို့ကို သတ်မှတ်နိုင်ပါသည် - 

.. _figure_mesh_elevation:

.. figure:: img/mesh_elevation.png
   :align: center

   Mesh မြေမျက်နှာသွင်ပြင် အနိမ့်အမြင့်ဆိုင်ရာ ဂုဏ်သတ္တိများ

* :guilabel:`Elevation Surface` (အမြင့်မျက်နှာပြင်) - Mesh layer vertex များ၏ အမြင့် Z တန်ဖိုးများကို မြေမျက်နှာသွင်ပြင် အမြင့်တန်ဖိုးများအဖြစ် မည်သို့အဓိပ္ပါယ်ဖော်သင့်သည်ဆိုသည်ကို လုပ်ဆောင်ပေးပါသည်။ :guilabel:`Scale` factor တစ်ခုနှင့် :guilabel:`Offset` (အရွေ့) တစ်ခုတို့ကို အသုံးပြုနိုင်ပါသည်။
* :guilabel:`Profile Chart Appearance`: controls the rendering
  :guilabel:`Style` the mesh elevation will use when drawing a profile chart.
  It can be set as:
* :guilabel:`Profile Chart Appearance` - Profile chart တစ်ခုရေးဆွဲသောအခါ mesh ၏ မြေမျက်နှာသွင်ပြင် အနိမ့်အမြင့်အတွက် ပုံဖော်ပြသခြင်း :guilabel:`Style` ကို ထိန်းချုပ်ပေးပါသည်။ ၎င်းတို့ကို အောက်ပါတို့အဖြစ် သတ်မှတ်ပေးနိုင်ပါသည်- 

  * :ref:`မျဉ်းစတိုင် (line style) <vector_line_symbols>` ဖြင့် profile :guilabel:`မျဉ်း (Line)`  တစ်ခုအဖြစ်
  * သက်ဆိုင်ရာ :ref:`fill style <vector_fill_symbols>` (အဖြည့် style) ဖြင့် :guilabel:`Fill below` (အောက်တွင်အရောင်ဖြည့်ထားခြင်း) လုပ်ထားသော မျက်နှာပြင် တစ်ခုအဖြစ်


.. index:: Metadata, Metadata editor, Keyword
.. _meshmetadata:

Metadata Properties (Metadata ဂုဏ်သတ္တိများ)
---------------------------------------------

|editMetadata| :guilabel:`Metadata` tab တွင် layer နှင့်ပတ်သက်သော metadata report ဖန်တီးခြင်းနှင့် တည်းဖြတ်ပြင်ဆင်ခြင်းတို့ကို လုပ်ဆောင်နိုင်ပါသည်။ ပိုမိုသိရှိလိုသည်များအတွက် :ref:`metadatamenu` တွင် ကြည့်ရှုပါ။

.. _editing_mesh:

Editing a mesh layer (Mesh layer တစ်ခုကို တည်းဖြတ်ပြင်ဆင်ခြင်း)
================================================================

QGIS သည် :ref:`mesh layer တစ်ခုကို <vector_create_mesh>` ဘာမှမရှိသည့် အသစ်ကနေဖန်တီးနိုင်သလို ရှိနေပြီးသား layer တစ်ခုပေါ်မူတည်ပြီး ဖန်တီးနိုင်ပါသည်။ နောက်မှ dataset များသတ်မှတ်ပေးနိုင်သော layer အသစ်တစ်ခု၏ ဂျီဩမေတြီ များကို အသစ်ဖန်တီးနိုင်သလို မွမ်းမံခြင်းလည်း ပြုလုပ်နိုင်ပါသည်။ ရှိပြီးသား mesh layer ကိုလည်း တည်းဖြတ်ပြင်ဆင်နိုင်ပါသည်။ တည်းဖြတ်ပြင်ဆင်ခြင်း သည် frames-only layer တစ်ခုလိုအပ်သောကြောင့် တခြား ဆက်စပ် dataset များကို ဖယ်ပစ်မည်လား (၎င်းတို့ကိုလိုအပ်နေသေးလျှင် အသုံးပြုနိုင်ရန်ထားပါ) သို့မဟုတ် layer ကို (ဂျီဩမေတြီ များသာ) မိတ္တူတစ်ခုပွားထားမည်လား မေးပါလိမ့်မည်။

.. note:: QGIS သည် mesh layer များပေါ်တွင် edge များကို digitize (မြေပုံအချက်အလက်များရေးဆွဲ) ပြုလုပ်ခွင့်မပေးပါ။ Vertex များနှင့် face များကိုသာ ဖန်တီးနိုင်ပါသည်။ Mesh format များအားလုံးတိုင်းလည်း QGIS တွင် တည်းဖြတ်ပြင်ဆင်ခြင်း မပြုလုပ်နိုင်ပါ (`permissions <https://github.com/lutraconsulting/MDAL#supported-formats>`__ တွင်ကြည့်ပါ။)

Overview of the mesh digitizing tools (Mesh layer ၏ digitizing tool များ အကျဉ်း)
---------------------------------------------------------------------------------

အခြေခံ mesh layer element တစ်ခုနှင့် အပြန်အလှန် လုပ်ဆောင်ရန် သို့မဟုတ် တည်းဖြတ်ပြင်ဆင်ရန်အတွက် အောက်ပါ tool များကို အသုံးပြုနိုင်ပါသည်။

.. list-table:: Mesh layer အတွက် digitizing tool များ
   :header-rows: 1

   * - အညွှန်း
     - ရည်ရွယ်ချက်
     - တည်နေရာ
   * - |allEdits| :sup:`Current Edits`
     - တည်းဖြတ်ပြင်ဆင်ထားမှုများ သိမ်းရန်၊ layer များအားလုံး သို့မဟုတ် ရွေးချယ်ထားသော layer များအားလုံး၏ ပြင်ဆင်ထားမှုကို မသိမ်းထားပဲ မူရင်းအတိုင်း ပြန်ထားရန်။
     - :guilabel:`Digitizing` toolbar
   * - |toggleEditing| :sup:`Toggle to Edit`
     - Layer တည်းဖြတ်ပြင်ဆင်မှုကို အဖွင့်/အပိတ် လုပ်ရန်
     - :guilabel:`Digitizing` toolbar
   * - |saveEdits| :sup:`Save Edits`
     - Layer ကို အပြောင်းအလဲများ၊ ပြင်ဆင်မှုများ ပြုလုပ်ပြီးနောက် ပြင်ဆင်ထားမှုများကို သိမ်းရန်
     - :guilabel:`Digitizing` toolbar
   * - |undo| :sup:`Undo`
     - နောက်ဆုံးပြုလုပ်ခဲ့သော ပြင်ဆင်မှုကို တစ်ဆင့်နောက်ပြန်ဆုတ်ရန် - :kbd:`Ctrl+Z`
     - :guilabel:`Digitizing` toolbar
   * - |redo| :sup:`Redo`
     - နောက်ဆုံးပြုလုပ်ခဲ့သော undo ကို ပြန်ရယူရန် - :kbd:`Ctrl+Shift+Z`
     - :guilabel:`Digitizing` toolbar
   * - |cad| :sup:`Enable Advanced Digitizing tools`
     - :ref:`အဆင့်မြင့် Digitizing Panel (Advanced Digitizing Panel) <advanced_digitizing_panel>` ကို ဖွင့်ရန်၊ ပိတ်ရန်
     - :guilabel:`Advanced Digitizing` toolbar
   * - |meshReindex| :sup:`Reindex Faces and Vertices`
     - Mesh element များဖြစ်သည့် vertex၊ edge၊ face များကို အကောင်းဆုံးဖြစ်စေရန် index နှင့် နံပတ်များကို ပြန်လည်ဖန်တီးရန်
     - :guilabel:`Mesh` menu
   * - |meshDigitizing| :sup:`Digitize Mesh Elements`
     - Vertex များနှင့် face များကို ရွေးချယ်ရန်နှင့် ဖန်တီးရန်
     - :guilabel:`Mesh Digitizing` toolbar
   * - |meshSelectPolygon| :sup:`Select Mesh Elements by Polygon`
     - ရေးဆွဲထားသော Polygon အဝန်းအဝိုင်းတစ်ခုနှင့် ထပ်နေသော vertex များနှင့် face များကို ရွေးချယ်ရန်
     - :guilabel:`Mesh Digitizing` toolbar
   * - |meshSelectExpression| :sup:`Select Mesh Elements by Expression`
     - Expression code များရေးသားပြီး vertex များနှင့် face များကို‌ ရွေးချယ်ရန်
     - :guilabel:`Mesh Digitizing` toolbar
   * - |meshTransformByExpression| :sup:`Transform Vertices Coordinates`
     - ရွေးချယ်ထားသော Vertex များ၏ ကိုဩဒိနိတ်များကို ပြုပြင်မွမ်းမံခြင်း
     - :guilabel:`Mesh Digitizing` toolbar
   * - |meshEditForceByVectorLines| :sup:`Force by Selected Geometries`
     - Face များကို ခွဲထုတ်ပြီး အဖြောင့် ဂျီဩမေတြီ တစ်ခုကိုအသုံးပြုကာ အမြင့် Z တန်ဖိုးကို ကန့်သတ်ရန်
     - :guilabel:`Mesh Digitizing` toolbar

Exploring the Z value assignment logic (အမြင့် Z တန်ဖိုးသတ်မှတ်ခြင်း logic ကို လေ့လာကြည့်ခြင်း)
------------------------------------------------------------------------------------------------

Mesh layer ကို တည်းဖြတ်ပြင်ဆင်သည့်အခါ :guilabel:`Vertex Z value (Vertex ၏ အမြင့်တန်ဖိုး)` widget သည် map canvas ၏ ညာဘက်အထက်ထောင့်တွင် ပွင့်လာပါမည်။ ပုံမှန်အားဖြင့် ၎င်းတန်ဖိုးသည် :menuselection:`Settings --> Options --> Digitizing` tab ထဲတွင် သတ်မှတ်ထားသည့် :guilabel:`မူရင်းအမြင့်တန်ဖိုး Z` နှင့်တူပါသည်။ ရွေးချယ်ထားသော vertex များရှိသောအခါ wideget သည် ရွေးချယ်ထားသော vertex များ၏ ပျမ်းမျှ အမြင့် Z တန်ဖိုးကို ပြပေးပါသည်။

တည်းဖြတ်ပြင်ဆင်နေစဉ်တွင် :guilabel:`အမှတ်၏ အမြင့် Z တန်ဖိုး` ကို vertex အသစ်များတွင် သွားပြီးသတ်မှတ်ပါသည်။ စိတ်ကြိုက်တန်ဖိုးတစ်ခုကို သတ်မှတ်ပေးနိုင်ပါသည် - widget ကို တည်းဖြတ်ပြင်ဆင်ပြီး :kbd:`Enter` ကိုနှိပ်ပါ။ မူရင်းတန်ဖိုးကို အစားထိုးသွားပြီး အသစ်ထည့်ရေးလိုက်သော တန်ဖိုးကို digitizing process တွင်အသုံးပြုမည်ဖြစ်ပါသည်။ ထိုတန်ဖိုးများကို မူလတန်ဖိုးအဖြစ်သို့ ပြန်လည်ပြောင်းလဲရန် widget ထဲရှိ |clearText| icon ကိုနှိပ်ပါ။

Rules of assignment (သတ်မှတ်ခြင်း စည်းကမ်းများ)
................................................

Vertex အသစ်တစ်ခု **ဖန်တီး** သောအခါ mesh layer ထဲရှိ ရွေးချယ်ထားမှုနှင့် ၎င်း၏ တည်နေရာပေါ်မူတည်ပြီး အမြင့် Z တန်ဖိုး ပြောင်းလဲနိုင်ပါသည်။ အောက်ပါဇယားတွင် ပေါင်းစပ်မှု အမျိုးမျိုးကိုပြသပေးထားပါသည်။


.. list-table:: Vertex အသစ်တွင် အမြင့် Z တန်ဖိုးသတ်မှတ်ခြင်း ဇယား
   :header-rows: 1

   * - Vertex များဖန်တီးခြင်း
     - Mesh layer ထဲတွင် ရွေးချယ်ထားသော vertex များရှိပါသလား
     - သတ်မှတ်ထားသော တန်ဖိုး၏မူရင်း
     - သတ်မှတ်ထားသော အမြင့် Z တန်ဖိုး
   * - မည်သည့် face သို့မဟုတ် face တစ်ခု၏ edge နှင့်မှ ချိတ်ဆက်မထားသော "Free" vertex
     - မရှိပါ
     - :guilabel:`Vertex Z value` (Vertex အမြင့် Z တန်ဖိုး)
     - Default သို့မဟုတ် အသုံးပြုသူမှသတ်မှတ်ထားသော
   * -
     -
     - :guilabel:`Advanced Digitizing Panel` (အဆင့်မြင့် digitizing panel) (အကယ်၍ :guilabel:`z` widget သည် |locked| :sup:`Locked` (သော့ခတ်ထားသော) အခြေအနေတွင်ရှိနေလျှင်)
     - |locked| :sup:`Locked` (သော့ခတ်ထားသော) အခြေအနေတွင်ရှိနေလျှင် :guilabel:`z` widget
   * -
     - ရှိပါသည်
     - :guilabel:`Vertex Z value` (Vertex အမြင့် Z တန်ဖိုး)
     - ရွေးချယ်ထားသော vertex များ၏ ပျမ်းမျှ
   * - Edge တစ်ခုပေါ်ရှိ vertex
     - ---
     - Mesh layer
     - Edge ၏ vertex များမှ ဖြည့်သွင်းတွက်ထုတ် (interpolate) သည်
   * - Face တစ်ခုပေါ်ရှိ vertex
     - ---
     - Mesh layer
     - Face ၏ vertex များမှ ဖြည့်သွင်းတွက်ထုတ် (interpolate) သည်
   * - 2D vector feature တစ်ခုကို ဆွဲကပ်ထားသော vertex
     - ---
     - :guilabel:`Vertex Z value` (Vertex အမြင့် Z တန်ဖိုး)
     - Default သို့မဟုတ် အသုံးပြုသူမှသတ်မှတ်ထားသော
   * - 3D vector feature တစ်ခုကို ဆွဲကပ်ထားသော vertex
     - ---
     - Vector layer
     - Vertex
   * - 3D vector မျဉ်းပိုင်း (segment) တစ်ခုကို ဆွဲကပ်ထားသော vertex
     - ---
     - Vector layer
     - Vector segment တစ်လျှောက် ဖြည့်သွင်းတွက်ထုတ် (interpolate) ထားသော


.. note:: :ref:`Advanced Digitizing Panel <advanced_digitizing_panel>` ကိုဖွင့်ထားသော်လည်း mesh element တစ်ခုမှရွေးမထားလျှင် :guilabel:`Vertex Z value` widget သည် ပိတ်သွားပါမည်။ ထို့နောက် Mesh element ၏ :guilabel:`z` widget သည် အမြင့် Z တန်ဖိုးသတ်မှတ်မှုကို လုပ်ဆောင်သွားပါမည်။

Modifying Z value of existing vertices (ရှိနေပြီးသား vertex များ၏ အမြင့် Z တန်ဖိုးများကို မွမ်းမံခြင်း)
........................................................................................................

Vertex များ၏ အမြင့် Z တန်ဖိုးကို မွမ်းမံရန် အရိုးရှင်းဆုံးနည်းလမ်းမှာ - 

#. Vertex တစ်ခုသို့မဟုတ် တစ်ခုထက်ပိုသော vertex များကိုရွေးချယ်ပါ။ :guilabel:`Vertex Z value` widget သည် ရွေးချယ်ထားသည်များ၏ ပျမ်းမျှ အမြင့်ကို ပြသပါလိမ့်မည်။
#. Widget ထဲရှိ တန်ဖိုးကိုပြောင်းလဲပါ။
#. :kbd:`Enter` ကိုနှိပ်ပါ။ ရိုက်ထည့်လိုက်သောတန်ဖိုးကို vertex များဆီတွင် သတ်မှတ်ပေးပြီး နောက်လာမည့် vertex များအတွက်၏ default တန်ဖိုးဖြစ်သွားပါမည်။

Vertex တစ်ခု၏ အမြင့် Z တန်ဖိုးကိုပြောင်းလဲရန်အတွက် တခြားနည်းလမ်းမှာ နေရာရွှေ့ပြီး Z တန်ဖိုးလုပ်ဆောင်နိုင်စွမ်းဖြင့် vector layer feature တစ်ခုပေါ်တွင် ‌ဆွဲကပ်ခြင်းဖြစ်ပါသည်။ Vertex တစ်ခုထက်ပိုရွေးထားလျှင် ဒီနည်းလမ်းအတိုင်း အမြင့် Z တန်ဖိုးကို မပြောင်းလဲနိုင်ပါ။

:ref:`Mesh vertex များ ပြောင်းလဲခြင်း <transform_meshvertices>` dialog သည် ရွေးချယ်ထားသော vertex များ (၎င်းတို့၏ X နှင့် Y တန်ဖိုးများဖြင့်) ၏ Z တန်ဖိုးကို မွမ်းမံရန် နည်းလမ်းများ ထောက်ပံ့ပေးပါသည်။

.. _select_mesh_elements:

Selecting mesh elements (Mesh element များ ရွေးချယ်ခြင်း)
----------------------------------------------------------

:guilabel:`Digitize Mesh Elements` ကိုအသုံးပြုခြင်း
....................................................

|meshDigitizing| :sup:`Digitize Mesh Elements` tool ကို ဖွင့်ပါ။ Element တစ်ခုပေါ်တွင် mouse တင်ထားလိုက်လျှင် ၎င်း element ကို အရောင်တစ်ခုဖြင့် ထင်ရှားအောင်ပြသပေးပြီး ၎င်းကိုရွေးချယ်နိုင်မည်ဖြစ်သည်။

* Vertex တစ်ခုကို click နှိပ်လိုက်ပါ၊ ၎င်းကိုရွေးချယ်ပြီးသားဖြစ်သွားပါလိမ့်မည်။
* Face တစ်ခု သို့မဟုတ် edge တစ်ခု၏ အလယ်ဗဟိုရှိ စတုရန်းသေးသေးလေးကို click နှိပ်ပါ၊ ၎င်းကို ရွေးချယ်ပြီးသားဖြစ်သွားပါမည်။ ချိတ်ဆက်ထားသော vertex များကိုလည်း ရွေးချယ်ပြီးသားဖြစ်သွားပါမည်။ အပြန်အလှန်အားဖြင့် edge သို့မဟုတ် face တစ်ခု၏ vertex များအားလုံးကို ရွေးချယ်လိုက်ခြင်းသည်လည်း ထို element ကိုရွေးချယ်ခြင်းဖြစ်ပါသည်။
* ထပ်နေသည့် element (ရွေးချယ်ထားသော face နှင့် ၎င်း၏ vertex များအားလုံး) များကိုရွေးချယ်ရန် ထောင့်မှန်စတုဂံတစ်ခု ဆွဲလိုက်ပါ။ အပြည့်အစုံပါသော element များကိုသာရွေးချယ်လိုပါက :kbd:`Alt` ကိုနှိပ်ပါ။ 
* ရွေးချယ်ထားမှုထဲကို element များထပ်ဖြည့်လိုပါက ရွေးချယ်နေစဉ်တွင် :kbd:`Shift` ကို နှိပ်ပါ။
* ရွေးချယ်ထားမှုထဲမှ element တစ်ခုကို ဖယ်ထုတ်လိုလျှင် :kbd:`Ctrl` ကိုနှိပ်ပြီး နောက်တကြိမ် ထပ်ရွေးချယ်လိုက်ပါ။ Face တစ်ခုကို deselect (မရွေးချယ်) လုပ်လိုက်လျှင် ၎င်း၏ vertex များအားလုံးကို မရွေးချယ်ပြီးသားဖြစ်သွားပါမည်။

:guilabel:`Polygon ဖြင့် mesh element များကို ရွေးချယ်နည်း` ကို အသုံးပြုခြင်း
..............................................................................

|meshSelectPolygon| :sup:`Select Mesh Elements by Polygon` tool ကိုဖွင့်ပါ၊ ထို့နောက် - 

* Mesh ဂျီဩမေတြီ များပေါ်တွင် polygon တစ်ခုဆွဲပါ (Vertex တစ်ခုထည့်ရန် left-click ကိုနှိပ်ပါ၊ နောက်ဆုံးထည့်ခဲ့သော vertex ကို ဖျက်ရန် :kbd:`Backspace`၊ polygon ကို မကြိုက်လို့ ဖျက်လိုလျှင် :kbd:`Esc` ကို နှိပ်ပါ၊ polygon ကိုအဆုံးသတ်ရန် right-click ကိုနှိပ်ပါ)။ တစ်စိတ်တစ်ပိုင်းထပ်နေသော vertex များနှင့် face များကို ရွေးချယ်ပြီးသားဖြစ်သွားပါလိမ့်မည်။ အပြည့်အစုံပါသော element များကိုသာ ရွေးချယ်လိုလျှင် ဆွဲနေစဉ်တွင် :kbd:`Alt` ကို နှိပ်ပါ။
* Vector layer feature ၏ ဂျီဩမေတြီ ပေါ်တွင် right-click နှိပ်ပါ၊ ပေါ်လာသည့် စာရင်းထဲမှ ရွေးချယ်လိုက်ပါ။ Mesh layer ၏ တစ်စိတ်တစ်ပိုင်းထပ်နေသော vertex များနှင့် face များကို ရွေးချယ်ပြီးသား ဖြစ်သွားပါလိမ့်မည်။ အပြည့်အစုံပါသော element များကိုသာ ရွေးချယ်လိုလျှင် ဆွဲနေစဉ်တွင် :kbd:`Alt` ကို နှိပ်ပါ။
* ရွေးချယ်ထားမှုထဲကို element များထပ်ထည့်လိုလျှင် ၎င်းတို့ကိုရွေးချယ်နေစဉ်တွင် :kbd:`Shift` ကိုနှိပ်ပါ။
* ရွေးချယ်ထားမှုထဲမှ element တစ်ခုကို ဖယ်ထုတ်လိုလျှင် ရွေးချယ်ထားသော polygon အပေါ် ရေးဆွဲနေချိန်တွင် :kbd:`Ctrl` ကိုနှိပ်ထားပါ။

:guilabel:`Expression ဖြင့် mesh element များကို ရွေးချယ်နည်း` ကို အသုံးပြုခြင်း
.................................................................................

Mesh element များကိုရွေးချယ်နိုင်သော တခြားနည်းလမ်းမှာ |meshSelectExpression|:sup:`Select Mesh Elements by Expression` ဖြစ်ပါသည်။ ၎င်းကိုနှိပ်လိုက်လျှင် mesh :ref:`expression selector dialog <vector_expressions>` ပွင့်လာမည်ဖြစ်ပြီး ၎င်း dialog တွင် -

#. ရွေးချယ်ခြင်းနည်းလမ်းကို ရွေးပါ - 

   * :guilabel:`Vertex များဖြင့် ရွေးချယ်ခြင်း (Select by vertices)` - ရေးထားသော expression ကို vertex များအတွက် အသုံးပြုပါ၊ Expression နှင့်ကိုက်ညီသော vertex များအပြင် ၎င်းနှင့်ဆက်စပ်သော edge/face များကိုပါ ရွေးထုတ်ပေးပါသည်။ 
   * :guilabel:`Face များဖြင့် ရွေးချယ်ခြင်း (Select by faces)` - ရေးထားသော expression ကို face များအတွက် အသုံးပြုပါ၊ Expression နှင့်ကိုက်ညီသော face များအပြင် ၎င်းနှင့်ဆက်စပ်သော edge/vertex များကိုပါ ရွေးထုတ်ပေးပါသည်။ 
#. Write the expression of selection. Depending on the selected method,
   available functions in the :ref:`Meshes group <expression_function_meshes>`
   will be filtered accordingly.
#. ရွေးချယ်ခြင်းအတွက် expression တစ်ခုရေးပါ။ ရွေးချယ်ထားသော နည်းလမ်းပေါ်မူတည်ပြီး :ref:`Meshes group <expression_function_meshes>` ထဲရှိ အသုံးပြုနိုင်သော လုပ်ဆောင်မှုများ (functions) ကိုသာ စစ်ထုတ်ပေးမည်ဖြစ်သည်။
#. Run the query by setting how the selection should behave and pressing:
#. ရွေးချယ်မှု မည်သို့လုပ်ဆောင်မည်ဆိုသည်ကို သတ်မှတ်ပြီး အောက်ပါတို့ကို နှိပ်ကာ Query ကို run ပါ-

   * |expressionSelect| :guilabel:`Select` - Layer ထဲရှိ ရွေးချယ်ထားပြီးသားကို အစားထိုးခြင်း။
   * |selectAdd| :guilabel:`Add to current selection` (ရွေးချယ်ထားမှုထဲကို ထပ်ပေါင်းထည့်ခြင်း)
   * |selectRemove| :guilabel:`Remove from current selection` (ရွေးချယ်ထားမှုထဲက ဖယ်ထုတ်ခြင်း)

Modifying mesh elements (Mesh element များကို မွမ်းမံခြင်း)
------------------------------------------------------------

Adding vertices (Vertex များ ပေါင်းထည့်ခြင်း)
..............................................

Mesh layer တစ်ခုထဲသို့ vertex များထည့်ရန်အတွက် - 

#. |meshDigitizing| :sup:`Digitize mesh elements` ခလုတ်ကိုနှိပ်ပါ။
#. Map canvas ၏ အထက်ညာဘက်ထောင့်တွင် :guilabel:`Vertex Z value` widget ပေါ်လာပါမည်။ ဤတန်ဖိုးကို နောက်လာမည့် vertex များအတွက် သတ်မှတ်ချင်သော အမြင့် Z ကိုဩဒိနိတ်တန်ဖိုးအဖြစ် သတ်မှတ်ပါ။
#. ထို့နောက် double-click နှိပ်ပါ။ 

   * Face တစ်ခု၏ အပြင်ဘက်တွင် - မည်သည့် face နှင့်မျှ ချိတ်ဆက်မထားသော "free vertex" တစ်ခုပေါင်းထည့်ပါ။ Layer သည် ပြုပြင်ခြင်း (editing) mode တွင်ရှိနေလျှင် ထို vertex ကို အနီရောင် အစက်တစ်ခု အဖြစ် ပြသမည်ဖြစ်သည်။
   * ရှိနေပြီးသား face(s) ၏ edge ပေါ်တွင် - Edge ပေါ်တွင် vertex တစ်ခုပေါင်းထည့်ပါ၊ ထိစပ်နေသော face များကို vertex အသစ်နှင့်ချိတ်ဆက်နေသော တြိဂံများအဖြစ် ခွဲထုတ်ပါ။
   * Face တစ်ခု၏အတွင်းထဲတွင် - တြိဂံများအဖြစ် face များကို ခွဲထုတ်ပြီး ထို တြိဂံများ၏ edge များသည် အနီးအနားရှိ vertex များကို vertex အသစ်နှင့် ချိတ်ဆက်ပေးပါသည်။

Adding faces (Face များ ပေါင်းထည့်ခြင်း)
.........................................

Mesh layer တွင် face များပေါင်းထည့်ရန် - 

#. |meshDigitizing| :sup:`Digitize mesh elements` ခလုတ်ကိုနှိပ်ပါ။
#. Map canvas ၏ အထက်ညာဘက်ထောင့်တွင် :guilabel:`Vertex Z value` widget ပေါ်လာပါမည်။ ဤတန်ဖိုးကို နောက်လာမည့် vertex များအတွက် သတ်မှတ်ချင်သော အမြင့် Z ကိုဩဒိနိတ်တန်ဖိုးအဖြစ် သတ်မှတ်ပါ။   
#. Vertex တစ်ခုပေါ်တွင် mouse ကိုတင်ထားလိုက်ပါ၊ ထို့နောက် ဘေးတွင်ပေါ်လာသော တြိဂံသေးသေးလေးကို click နှိပ်ပါ။
#. နောက်ထပ် အမှတ်တစ်ခု၏ တည်နေရာဆီသို့ mouse ကိုရွှေ့ပါ၊ ရှိနေပြီးသား vertex ကို စွဲကပ်နိုင်သလို အသစ်တစ်ခုပေါင်းထည့်ရန် left-click ကိုနှိပ်နိုင်ပါသည်။
#. Face ထဲတွင် ကိုယ်ထည့်ချင်သလောက် vertex များထည့်ရန် အထက်ပါနည်းလမ်းအတိုင်း လုပ်ဆောင်ပါ။ နောက်ဆုံး vertex ကို ဖျက်ရန် :kbd:`Backspace` ခလုတ်ကိုနှိပ်ပါ။
#. Mouse ကိုရွှေ့နေစဉ်တွင် face ၏ပုံစံဖြစ်သော သရေကွင်း ပုံစံတစ်ခုပေါ်လာပါမည်။ ၎င်းသည် အစိမ်းရောင်ဖြစ်နေလျှင် face သည် ဆီလျော်မှန်ကန်ပြီး mesh တွင်ပေါင်းထည့်ရန် right-click ကိုနှိပ်ပါ။ အနီရောင်ဖြစ်နေလျှင် face သည် ဆီလျော်ခြင်းမရှိပဲ(ကိုယ့်ဟာကိုယ်ပြန်ဖြတ်နေခြင်း၊ ရှိနေပြီးသား face သို့မဟုတ် vertex နှင့် ထပ်နေခြင်း၊ အပေါက်ဖြစ်နေခြင်း၊ စသဖြင့်) mesh တွင် ထည့်ပေါင်းလို့မရနိုင်ပါ။ တချို့ vertex များကို undo ပြုလုပ်ပြီး ဂျီဩမေတြီကို ပြင်ရပါမည်။
#. Face digitizing ကို ပယ်ဖျက်လိုလျှင် :kbd:`Esc` ကိုနှိပ်ပါ။
#. Face ကိုအပြီးသတ်ရန် right-click ကိုနှိပ်ပါ။

.. _figure_invalid_mesh:

.. figure:: img/invalid_mesh.png
   :align: center

   ဆီလျော်မှုမရှိသော mesh ဥပမာများ

.. _remove_mesh_items:

Removing mesh elements (Mesh element များကို ဖယ်ထုတ်ခြင်း)
...........................................................

#. :ref:`ဖယ်လိုသော element များကို ရွေးချယ်ပါ <select_mesh_elements>`
#. |meshDigitizing| :sup:`Digitize mesh elements` tool ကိုအသုံးပြုလို့ရအောင် ဖွင့်ပါ။ 
#. Right-click ကိုနှိပ်ပြီး အောက်ပါတို့ကို ရွေးချယ်ပါ -

   * :guilabel:`ရွေးချယ်ထား‌သော vertex များကိုဖယ်ရှားပြီး အပေါက်များကိုဖြည့်ပါ` သို့မဟုတ် :kbd:`Ctrl+Del` ကိုနှိပ်ပါ - ပတ်ဝန်းကျင်ရှိ vertex များကိုအခြေခံတွက်ထုတ်ပြီး vertex များနှင့် ချိတ်ဆက်ထားသော face များကို ဖယ်ရှားပြီး အပေါက်များကိုဖြည့်ပါသည်။
   * :guilabel:`အပေါက်များကို မဖြည့်ဘဲ ရွေးချယ်ထားသော vertexများကို ဖယ်ရှားပါ` သို့မဟုတ် :kbd:`Ctrl+Shift+Del` ကိုနှိပ်ပါ - vertex များနှင့် ချိတ်ဆက်ထားသော face များကို ဖယ်ရှားပြီး အပေါက်များကို မဖြည့်ပါ။
   * :guilabel:`ရွေးချယ်ထားသော Face များကို ဖယ်ရှားပါ` သို့မဟုတ် :kbd:`Shift+Del` ကိုနှိပ်ပါ - face များကို ဖယ်ရှားပါသည် သို့သော် vertex များကို ချန်ထားပါသည်။

Item တစ်ခုကို မရွေးချယ်ပဲ ထိုပေါ်တွင် mouse တင်ထားသောအခါ ပေါ်လာသည့် menu မှလည်း အထက်တွင်ဖော်ပြခဲ့သည့် အချက်တွေကိုလုပ်ဆောင်နိုင်ပါသည်။

Moving mesh elements (Mesh element များကိုနေရာရွှေ့ခြင်း)
..........................................................

Mesh layer တစ်ခု၏ vertex များနှင့် face များကိုနေရာရွှေ့ရန် -

#. :ref:`ဖယ်လိုသော element များကို ရွေးချယ်ပါ <select_mesh_elements>`
#. |meshDigitizing| :sup:`Digitize mesh elements` tool ကိုအသုံးပြုလို့ရအောင် ဖွင့်ပါ 
#. Element ကိုစတင်ရွှေ့ရန် face/edge ၏အလည်ဗဟိုရှိ vertex ကို click နှိပ်ပါ။
#. ရောက်စေချင်သောနေကို mouse ဖြင့်ရွှေ့ပါ (vector feature များဆီကို စွဲကပ်နိုင်ပါသည်)။
#. နေရာအသစ်သည် :ref:`ဆီလျော်မှုမရှိသော mesh <figure_invalid_mesh>` ကို မဖြစ်လျှင် ရွှေ့လိုက်သော element များသည် အစိမ်းရောင်ဖြစ်နေပါမည်။ ထိုနေရာတွင် နေရာချထားရန် click ထပ်နှိပ်ပါ။ Vertex အားလုံးကိုရွေးချယ်ထားသော face များကို ပြောင်းလဲလိုက်သောကြောင့် ၎င်းတို့၏ပတ်ဝန်းကျင်ရှိအရာများသည် အလိုအလျောက်ပုံစံပြောင်းသွားမည်ဖြစ်ပါသည်။

.. _transform_meshvertices:

Transforming mesh vertice (Mesh vertex များကို ပုံစံပြောင်းလဲခြင်း)
....................................................................

Expression များ၏အကျိုးကျေးဇူးကြောင့် X၊ Y၊ Z တန်ဖိုးများကို တည်းဖြတ်ပြင်ဆင်ခြင်းဖြင့် |meshTransformByExpression| :sup:`Transform Vertices Coordinates` tool သည် ပိုပြီးအဆင့်မြင့်သည့် နည်းလမ်းဖြင့် vertex များကို နေရာရွှေ့နိင်ပါသည်။

#. ကိုဩဒိနိတ် ပြင်ဆင်လိုသော vertex များကို ရွေးချယ်ပါ။ 
#. |meshTransformByExpression| :sup:`Transform Vertices Coordinates` ကိုနှိပ်ပါ။ ရွေးချယ်ထားသော vertex များ၏ အရေအတွက်ကိုဖော်ပြပေးသော dialog တစ်ခုပွင့်လာပါမည်။ ရွေးချယ်မှုထဲသို့ vertex များအသစ်ပေါင်းထည့်နိုင်သလို ရွေးချယ်မှုထဲမှ vertex များကို ဖယ်ရှားလို့လည်း ရပါသည်။
#. ပြင်ဆင်မွမ်းမံလိုသော property များပေါ်မူတည်ပြီး :guilabel:`X တည်နေရာ`၊ :guilabel:`Y တည်နေရာ` နှင့် :guilabel:`Z တန်ဖိုး` များကို စစ်ဆေးရန်လိုအပ်ပါသည်။
#. ထို့နောက် ရွှေ့လိုသောနေရာတန်ဖိုးကိုဖြည့်ပါ။ ဂဏန်းတန်ဖိုးများဖြည့်လို့ရသလို |expression| :sup:`Expression dialog` ကိုအသုံးပြုပြီး expression နည်းလမ်းဖြင့်လည်း ရပါသည်။
#. |vertexCoordinates| :sup:`Import Coordinates of the Selected Vertex (ရွေးချယ်ထားသော vertex မှ တည်နေရာတန်ဖိုးများကို ထည့်သွင်းခြင်း)` ကိုနှိပ်လိုက်တာနဲ့ vertex တစ်ခုကို ရွေးချယ်လိုက်တိုင်း X၊ Y၊ Z တန်ဖိုးများကို အလိုအလျှောက်ဖြည့်ပြီးသား ဖြစ်သွားပါမည်။ Vertex တစ်ခုချင်းကို ပြင်ဆင်ရန်အတွက် လွယ်ကူလျှင်မြန်သော နည်းလမ်းဖြစ်ပါသည်။
#. Vertex များ၏ တည်နေရာအသစ်ကိုစမ်းသပ်ကြည့်ရှုရန်နှင့် mesh ပုံစံပြောင်းလဲမှုကို ကြိုတင်ကြည့်ရှုနိုင်ရန် :guilabel:`Preview Transform (ပုံစံပြောင်းလဲမှုကို ကြိုတင်ကြည့်ရှုခြင်း)` ကို နှိပ်ပါ။

   * ကြိုတင်ကြည့်ရှုမှုသည် စိမ်းနေလျှင် ပုံစံပြောင်းလဲထားသော mesh သည် အမှားကင်းပြီး ပြောင်းလဲမှုကို ဆက်လက်လုပ်ဆောင်နိုင်ပါသည်။
   * ကြိုတင်ကြည့်ရှုမှုသည် နီနေလျှင် ပုံစံပြောင်းလဲထားသော mesh တွင် အမှားများရှိနေပြီး အမှားကင်းစင်အောင် ပြင်ဆင်မှုမလုပ်မချင်း ပြောင်းလဲမှုကို ဆက်လက်လုပ်ဆောင်လို့မရနိုင်ပါ။
#. Vertex အစုလိုက် အတွက် ရွေးချယ်ထားသော တည်နေရာတန်ဖိုးများကို ပြင်ဆင်ရန် :guilabel:`Apply Transform` ကိုနှိပ်ပါ။

Reshaping mesh geometry (Mesh ဂျီဩမေတြီ ကို ပုံသဏ္ဍာန်ပြောင်းလဲခြင်း)
......................................................................

အကြောင်းအရာဆိုင်ရာ menu
^^^^^^^^^^^^^^^^^^^^^^^^

#. |meshDigitizing| :sup:`Digitize mesh elements` ကို အသုံးပြုလို့ရအောင်ဖွင့်ပါ။
#. Mesh item ကို ရွေးချယ်ပါ သို့မဟုတ်
#. Mesh element တစ်ခုပေါ်တွင် mouse တင်ထားပါ၊ အရောင်တစ်ခုဖြင့် ထင်ရှားအောင်ပြသပေးပါမည်။
#. Right-click နှိပ်ပြီး အောက်ပါတို့ကိုလုပ်ဆောင်နိုင်ပါသည်-

   * :ref:`item များကိုဖယ်ရှားခြင်း <remove_mesh_items>`
   * :guilabel:`ရွေးချယ်ထားသော Face များကို ပိုင်းဖြတ်ခြင်း` (:guilabel:`Split Current Face`) - mouse တင်ထားသော face သို့မဟုတ် ရွေးချယ်ထားသော ‌လေးထောင့်ပုံစံ mesh face တစ်ခုစီကို တြိဂံနှစ်ခုအဖြစ် ပိုင်းဖြတ်ခြင်း။
   * :guilabel:`ရွေးချယ်ထားသော vertex များဖြင့် Delaunay Triangulation ပြုလုပ်ခြင်း (Delaunay Triangulation with Selected vertices)` - ရွေးချယ်ထားသော vertex များအသုံးပြု၍ တြိဂံ face များ တည်ဆောက်ခြင်း
   * :guilabel:`ရွေးချယ်ထားသော face များကို အချောပြင်ခြင်း (Refine Selected Face(s))` (:guilabel:`Refine Current Face`) - edge တစ်ခုချင်းစီ၏ အလယ်တွင် vertex တစ်ခုထည့်ပြီး (တြိဂံတစ်ခုသည် တြိဂံများအဖြစ်၊ စတုဂံတစ်ခုသည် စတုဂံများအဖြစ်) face တစ်ခုကို face လေးခုအဖြစ် ပိုင်းဖြတ်ပါသည်၊ vertex အသစ်များနှင့် ချိတ်ဆက်နေသော ကပ်လျက် face များကိုလည်း triangulation နည်းဖြင့် တွက်ထုတ်ပါသည်။

The edge markers (Edge အမှတ်အသားများ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

|meshDigitizing| :sup:`Digitize mesh elements` ကိုဖွင့်ထားသောအခါ edge တစ်ခုပေါ်တွင် mouse ကိုတင်ထားလျှင် ၎င်း edge ကို အရောင်ထင်ရှားအောင်ပြသပြီး အပြန်အလှန်လုပ်ဆောင်မှုများ စတင်လုပ်ဆောင်နိုင်ပါသည်။ အခြေအနေပေါ်မူတည်ပြီး အောက်ပါ အမှတ်အသားများကို အသုံးပြုနိုင်ပါသည်-

* **စတုရန်း** တစ်ခု၊ edge ၏ အလယ်ဗဟိုတွင် - အစွန်တွင်ရောက်နေသော vertex များကို ရွေးချယ်ရန် ၎င်းကို click နှိပ်ပါ။
* **ကြက်ခြေခတ်** တစ်ခု၊ တစ်ဖက်စီတွင်ရှိနေသော face နှစ်ခုကို ပေါင်းနိုင်လျှင် - Edge ကိုဖျက်ပြီး face များကို ပေါင်းလိုလျှင် ၎င်းကို click နှိပ်ပါ။
* **စက်ဝိုင်း** တစ်ခု၊ edge သည် တြိဂံနှစ်ခုကြားတွင်ရှိနေလျှင် - edge ကို စမှတ်နှင့်ဆုံးမှတ် နေရာလဲလိုလျှင် ၎င်းကို click နှိပ်ပါ။ ဆိုလိုသည်မှာ face များ၏ အခြား "free" vertex နှစ်ခုနှင့် ၎င်းကို ချိတ်ဆက်ခြင်းဖြစ်သည်။

The :guilabel:`Force by Selected Geometries` tool (ရွေးချယ်ထားသော ဂျီဩမေတြီ များဖြင့် တွန်းအားပေးလုပ်စေသော tool)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

|meshEditForceByVectorLines| :sup:`Force by Selected Geometries` tool သည် မျဉ်း ဂျီဩမေတြီကိုအသုံးပြုပြီး မျဉ်းများကို ခွဲထုတ်ရန် ပိုကောင်းသည့်နည်းလမ်းများကို ဖန်တီးပေးပါသည်။ ခွဲထုတ်ပေးသည့်မျဉ်းသည် မျဉ်းကြောင်းတစ်လျှောက်တွင် edge များရှိစေရန် mesh ကိုတွန်းအားပေးလုပ်ဆောင်စေပါသည်။ လုပ်ဆောင်မှုပြီးသွားသည့်အခါ ခွဲထုတ်ပေးသည့် မျဉ်း ရှိတော့မည်မဟုတ်ပါ။ ရရှိလာသည့် edge များသည် အတားအဆီးအခက်အခဲများ ဖြစ်မနေတော့ဘဲ တခြား edge များလို ပြုပြင်ပြောင်းလဲနိုင်ပါသည်။ ဥပမာ တိကျသည့်မျဉ်းများ (မြစ်ကမ်း သို့မဟုတ် တာတမံလမ်း၏နယ်နိမိတ်) ပါသည့် mesh layer ကို ပြုပြင်မွမ်းမံရန်အတွက် ဒီနည်းလမ်းကိုအသုံးပြုနိုင်ပါသည်။

#. |meshEditForceByVectorLines| :sup:`Force by Selected Geometries` tool ကိုအသုံးပြုလို့ရအောင်ဖွင့်ပါ။
#. ဂျီဩမေတြီ ကို "တွန်းအားပေးဖြတ်တောက်မည့် မျဉ်း (forcing line)" အဖြစ်အသုံးပြုပါ။ ၎င်းသည် -

   * Map canvas ရှိ line သို့မဟုတ် polygon feature တစ်ခုမှ ရယူနိုင်ပါသည် - vector feature ပေါ်တွင် right-click နှိပ်ပါ၊ ထို့နောက် ပေါ်လာသော menu ၏ စာရင်းမှ ၎င်းကိုရွေးချယ်ပါ။
   * Mesh frame ပေါ်တွင် ဆွဲထားသော ယာယီမျဉ်းတစ်ခု ဖြစ်နိုင်ပါသည် - vertex များပေါင်းထည့်ရန် left-click ကိုနှိပ်ပါ၊ အဆုံးသတ်ရန် right-click ကိုနှိပ်ပါ။ Vertex များ၏ အမြင့် Z တန်ဖိုးကို :guilabel:`Vertex Z value` widget သို့မဟုတ် :guilabel:`Advanced Digitizing Panel` ကိုဖွင့်ထားလျှင် :guilabel:`အမြင့် z` widget မှ သတ်မှတ်ပေးနိုင်ပါသည်။ မျဉ်းသည် mesh vertex သို့မဟုတ် 3D vector feature ၏ vertex သို့မဟုတ် အမှတ်နှစ်ခုကြားရှိမျဉ်းပိုင်း (segment) ကို ဆွဲကပ်ထားလျှင် vertex အသစ်သည် ဆွဲကပ်မိထားသည့် element ၏ အမြင့် Z တန်ဖိုးကိုယူပြီးအသုံးပြုပါသည်။

Line ဂျီဩမေတြီ သို့မဟုတ် polygon နယ်နိမိတ် နှင့် ထပ်နေသော mesh face များသည် |meshEditForceByVectorLines| :sup:`Force by Selected Geometries` tool drop-down menu မှ သတ်မှတ်နိုင်သော ရွေးချယ်စရာများအပေါ်မူတည်ပြီး အကျိုးသက်ရောက်ပါလိမ့်သည်-

* |checkbox| :guilabel:`Add new vertex on intersecting edges (ဖြတ်မိသော edge များတွင် vertex အသစ်တစ်ခု ထည့်ခြင်း)` - ဤနည်းလမ်းဖြင့် တွန်းအားပေးပြီး ဖြတ်တောက်သည့်မျဉ်းသည် edge ကိုဖြတ်တိုင်း vertex တစ်ခုဖန်တီးပေးပါသည်။ ဒီနည်းလမ်းဖြင့် face များကို ဖြတ်မိသည့်အခါတိုင်း မျဉ်းတစ်လျှောက် အပိုင်းများ ပိုင်းဖြတ်စေပါသည်။

  ဤနည်းလမ်းမသုံးလျှင် ဖြတ်မိသည့် face များကို ဖယ်ရှားပစ်ပြီး ရှိနေပြီးသား vertex များနှင့် တွန်းအားပေးဖြတ်တောက်သည့် မျဉ်း (တွန်းအားပေးဖြတ်တောက်သောမျဉ်းနှင့် ဖြတ်မိသော နယ်နိမိတ် edge ပေါ်တွင်လည်း vertex အသစ်များ ဖန်တီးပါသည်)၏ vertex များပေါင်းပြီး တွက်ထုတ်ထားသည့် triangulation မှရရှိလာသော face များဖြင့် အစားထိုးလိုက်ပါသည်။ 

  .. _figure_force_mesh_geometry:

  .. figure:: img/force_mesh_geometry.png
     :align: center

     Line ဂျီဩမေတြီ တစ်ခုကိုအသုံးပြုထားသော Force mesh - edge ဖြတ်တောက်မှုပေါ်တွင် vertex အသစ် မပါသောရလာဒ် (အလယ်) နှင့် vertex အသစ် ပါသောရလာဒ် (ညာဘက်)

* :guilabel:`Interpolate Z value from (အမြင့် Z တန်ဖိုးကို ဖြည့်စွက်တွက်ထုတ်ခြင်း)` - Vertex အသစ်များ၏ အမြင့် Z တန်ဖိုးကို မည်သို့တွက်ချက်မည်ကို သတ်မှတ်ပေးပါသည်။ အောက်ပါတို့မှ တွက်ချက်နိုင်ပါသည်-

  * :guilabel:`Mesh` ကိုယ်တိုင်မှ - Face အတွင်းတွင်ကျရောက်နေသော vertex များမှ vertex အသစ်များ၏ အမြင့် Z တန်ဖိုးကို တွက်ထုတ်ပါသည်။	
  * သို့မဟုတ် :guilabel:`Forcing line` - မျဉ်းကို 3D vector feature	သို့မဟုတ် ဆွဲထားသော မျဉ်းမှ သတ်မှတ်မည်ဆိုလျှင် vertex အသစ်များ၏ အမြင့် Z တန်ဖိုးကို ၎င်း၏ ဂျီဩမေတြီ မှ တွက်ထုတ်ပါသည်။ 2D line feature အတွက်ဆိုရင် vertex အသစ်များ၏ အမြင့် Z တန်ဖိုးသည် :guilabel:`Vertex Z value` ဖြစ်ပါသည်။

* :guilabel:`Tolerance` - ရှိနေသော mesh vertex တစ်ခုသည် tolerance တန်ဖိုးထက်ကျော်လွန်ပြီး မျဉ်းနှင့် ပိုနီးနေသောအခါ မျဉ်းပေါ်တွင် vertex အသစ်ဖန်တီးမ‌ပေးတော့ပဲ ရှိနေပြီးသား vertex ကိုပဲ အသုံးပြုပါသည်။ :guilabel:`Meters at Scale` (စကေးမီတာ) သို့မဟုတ် :guilabel:`Map Units` (မြေပုံယူနစ်) ဖြင့် တန်ဖိုးကို သတ်မှတ်ပေးနိုင်ပါသည်။ (:ref:`unit_selector` တွင်အသေးစိတ်ကြည့်ရှုပါ)

.. _reindex_mesh:

Reindexing meshes (Mesh များကို index ပြန်သတ်မှတ်ခြင်း)
--------------------------------------------------------

တည်းဖြတ်ပြင်ဆင်နေစဉ်တွင် undo/redo များကို မြန်ဆန်စွာလုပ်ဆောင်နိုင်စေရန် QGIS သည် ဖျက်လိုက်သည့် element များအတွက် နေရာလွတ်များ ထားရှိပေးသောကြောင့် memory အသုံးပြုမှုများတက်လာပြီး mesh တည်ဆောက်မှုတွင် မလုံလောက်မှုများ ဖြစ်စေပါသည်။ :menuselection:`Mesh -->` |meshReindex| :menuselection:`Reindex Faces and Vertices (Face နှင့် Vertice များကို ပြန်လည် index တပ်ခြင်း)` tool သည် face နှင့် vertex များကို ဆက်တိုက် အစီအစဉ်အတိုင်းဖြစ်နေစေရန် အပေါက်များကိုဖယ်ရှားပစ်ပြီး ၎င်းတို့၏ index နံပတ်များပြန်တပ်နိုင်ရန် ဖန်တီးထားပါသည်။ ဤနည်းလမ်းကြောင့် face နှင့် vertex များအကြား ချိတ်ဆက်မှု ကောင်းမွန်လာစေပြီး တွက်ချက်မှုစွမ်းရည် တိုးတက်စေပါသည်။

.. note:: |meshReindex| :guilabel:`Reindex Faces and Vertices` tool သည် layer ကိုသာ သိမ်းထားပေးပြီး undo/redo အဆင့်များကို ရှင်းလင်းပစ်သောကြောင့် နောက်ပြန်သွားလို့မရနိုင်ပါ။

.. _mesh_calculator:

Mesh Calculator (Mesh များ တွက်ချက်ပေးသည့်အရာ)
===============================================

:menuselection:`Mesh` menu ၏ထိပ်တွင်ရှိသော :guilabel:`Mesh Calculator` tool သည် ရှိနေပြီးသား dataset အစုအဖွဲ့များ မှတဆင့် dataset အစုအဖွဲ့အသစ်များ ဖန်တီးရန် arithmetic နှင့် logical တွက်ချက်မှုများ လုပ်ဆောင်နိုင်ပါသည်။ (:numref:`figure_mesh_calculator` တွင်ကြည့်ပါ)

.. _figure_mesh_calculator:

.. figure:: img/mesh_calculator.png
   :align: center

   Mesh များ တွက်ချက်ပေးသည့်အရာ

:guilabel:`Datasets` စာရင်းတွင် အသုံးပြုနေသော mesh layer ထဲတွင်ရှိသော dataset အုပ်စုများအားလုံး ပါဝင်ပါသည်။ Expression ထဲတွင် dataset အုပ်စု တစ်ခုကိုအသုံးပြုရန် စာရင်းထဲရှိ ၎င်း၏နာမည်ကို double-click နှိပ်လျှင် :guilabel:`Mesh calculator expression` field ထဲသို့ ပေါင်းထည့်သွားပါလိမ့်မည်။ ထို့နောက် တွက်ချက်မှု expression များ လုပ်ဆောင်ရန် operators (ပေါင်း၊ နှုတ်၊ မြှောက်၊ စား) ကိုအသုံးပြုနိုင်သည် သို့မဟုတ် box ထဲတွင် စာရိုက်ထည့်နိုင်ပါသည်။

:guilabel:`Result Layer` ဖြင့် ရလာဒ် layer ၏ property များကို ပြင်ဆင်သတ်မှတ်နိုင်ပါသည်-

* |checkbox| :guilabel:`Create on-the-fly dataset group instead of writing layer to disk` (ကွန်ပျူတာထဲတွင် Layer ဖန်တီးသိမ်းဆည်းမည့်အစား ယာယီ dataset အစုအဖွဲ့ကို ဖန်တီးခြင်း) -

  * အမှတ်ခြစ် ဖြုတ်ထားလျှင် ရလာဒ် file ကို plain file တစ်ခုအဖြစ် ကွန်ပျူတာထဲတွင် သိမ်းဆည်းမည်ဖြစ်သည်။ :guilabel:`ရလာဒ် File` သိမ်းမည့်လမ်းကြောင်းနှင့် :guilabel:`ရလာဒ် Format` တို့ဖြည့်ပေးရန် လိုအပ်ပါသည်။
  * အမှန်ခြစ် ခြစ်ထားလျှင် mesh layer ထဲတွင် dataset အစုအဖွဲ့ အသစ်တစ်ခု ထပ်ပေါင်းထည့်ပေးပါသည်။ Dataset အစုအဖွဲ့၏ တန်ဖိုးများကို ကွန်ပျူတာ မှတ်ဉာဏ်ထဲတွင် သိမ်းပေးထားခြင်းမဟုတ်ပါ သို့သော် dataset တစ်ခုစီကို လိုအပ်သည့်အခါ mesh calculator ထဲရှိ formula များဖြင့် တွက်ချက်ပေးပါသည်။ ယာယီ dataset အုပ်စုကို project ထဲတွင်ပဲ သိမ်းထားပေးပြီး လိုအပ်လျှင် ဖယ်ထုတ်ပစ်ခြင်း သို့မဟုတ် layer :guilabel:`Source` properties tab မှတဆင့် file ကို အမြဲတမ်းအတွက် သိမ်းထားနိုင်ပါသည်။

  ဘယ်နည်းကိုပဲအသုံးပြုသည်ဖြစ်ပါစေ ရလာဒ် dataset အစုအဖွဲ့အတွက် :guilabel:`Group Name` (အစုအဖွဲ့အမည်) ပေးထားသင့်ပါသည်။

* တွက်ချက်မှုအတွက် ထည့်သွင်းစဉ်းစားရမည့် :guilabel:`Spatial extent` (တည်နေရာဆိုင်ရာ အကျယ်အဝန်း) သည် အောက်ပါအတိုင်းဖြစ်နိုင်ပါသည်-

  * :guilabel:`အနည်းဆုံး X တန်ဖိုး`၊ :guilabel:`အများဆုံး X တန်ဖိုး`၊ :guilabel:`အနည်းဆုံး Y တန်ဖိုး`၊ :guilabel:`အများဆုံး Y တန်ဖိုး` များ ရိုက်ထည့်ထားသော သို့မဟုတ် ရှိနေပြီးသား dataset အုပ်စုမှ ထုတ်နှုတ်ယူထားသော (အထက်တွင်ဖော်ပြခဲ့သော တည်နေရာတန်ဖိုး field တွင်ဖြည့်သွင်းရန် စာရင်းထဲကရွေးချယ်ပြီး :guilabel:`Use selected layer extent` (ရွေးချယ်ထားသော layer ၏အကျယ်အဝန်းကိုအသုံးပြုခြင်း) ကိုနှိပ်ပါ) ဖြင့် :guilabel:`Custom extent` (စိတ်ကြိုက် အကျယ်အဝန်း) တစ်ခု
  * Project ၏ polygon layer (:guilabel:`Mask layer`) ဖြင့်သတ်မှတ်ခြင်း - Mesh layer dataset များကိုဖြတ်ထုတ်ရန်အတွက် polygon feature ဂျီဩမေတြီများကိုအသုံးပြုပါသည်။

* ရှိနေပြီးသား dataset အစုအဖွဲ့များ၏ timestep များမှ ရွေးချယ်ထားသော :guilabel:`စချိန်` နှင့် :guilabel:`ဆုံးချိန်` တို့ဖြင့် dataset ကို သတ်မှတ်နိုင်ရန် :guilabel:`Temporal extent` (အချိန်ကာလ အတိုင်းအတာ) ကိုအသုံးပြုပါသည်။ :guilabel:`Use all selected dataset times` (ရွေးချယ်ထားသော dataset အားလုံး၏ အချိန်ကိုအသုံးပြုခြင်း) ခလုတ်ကိုနှိပ်ပြီး တန်ဖိုးများကိုဖြည့်နိုင်ပါသည်။ 

:guilabel:`Operators` အပိုင်းတွင် အသုံးပြုနိုင်သော operator များအားလုံးပါဝင်ပါသည်။ Mesh calculator Expression box ထဲသို့ operator တစ်ခုထည့်ရန်အတွက် သင့်လျော်သော ခလုတ်ကို click နှိပ်ပါ။ သင်္ချာတွက်ချက်မှုများအတွက် (``+``၊ ``-``၊ ``*``၊ ... ) နှင့် statistics (စာရင်းအင်းအချက်အလက်) ဆိုင်ရာတွက်ချက်မှုများအတွက် (``အနည်းဆုံး``၊ ``အများဆုံး``၊ ``ပေါင်းခြင်း (aggr)``၊ ``ပျမ်းမျှ (aggr)``၊ ... ) များကို အသုံးပြုနိုင်ပါသည်။ အခြေအနေပေါ် မူတည်ပြီးလုပ်ဆောင်သည့် expression များဖြစ်သည့် (``=``၊ ``!=``၊ ``<``၊ ``>=``၊ ``IF``၊ ``AND``၊ ``NOT``၊ ... ) ကို အသုံးပြုလျှင် အမှားအတွက် 0 နှင့် အမှန်အတွက် 1 တန်ဖိုးတစ်ခုခုကို ထုတ်ပေးပါသည်။ ထို့ကြောင့် ၎င်းတို့ကို တခြား operator နှင့် function များနှင့် ပူးတွဲအသုံးပြုနိုင်ပါသည်။ Expression ထဲတွင် ``NODATA`` တန်ဖိုးကိုလည်း အသုံးပြုနိုင်ပါသည်။

:guilabel:`Mesh Calculator Expression` widget တွင် expression ကို ပြသခြင်း၊ ပြုပြင်ခြင်း၊ အသုံးပြုခိုင်းစေခြင်းများ လုပ်‌ဆောင်နိုင်ပါသည်။

.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |3d| image:: /static/common/3d.png
   :width: 1.5em
.. |add| image:: /static/common/mActionAdd.png
   :width: 1.5em
.. |addMeshLayer| image:: /static/common/mActionAddMeshLayer.png
   :width: 1.5em
.. |allEdits| image:: /static/common/mActionAllEdits.png
   :width: 1.5em
.. |cad| image:: /static/common/cad.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |clearText| image:: /static/common/mIconClearText.png
   :width: 1.5em
.. |collapseTree| image:: /static/common/mActionCollapseTree.png
   :width: 1.5em
.. |editMetadata| image:: /static/common/editmetadata.png
   :width: 1.2em
.. |elevationscale| image:: /static/common/elevationscale.png
   :width: 1.5em
.. |expandTree| image:: /static/common/mActionExpandTree.png
   :width: 1.5em
.. |expression| image:: /static/common/mIconExpression.png
   :width: 1.5em
.. |expressionSelect| image:: /static/common/mIconExpressionSelect.png
   :width: 1.5em
.. |general| image:: /static/common/general.png
   :width: 1.5em
.. |locked| image:: /static/common/locked.png
   :width: 1.5em
.. |mapIdentification| image:: /static/common/mActionMapIdentification.png
   :width: 1.5em
.. |meshDigitizing| image:: /static/common/mActionMeshDigitizing.png
   :width: 1.5em
.. |meshEditForceByVectorLines| image:: /static/common/mActionMeshEditForceByVectorLines.png
   :width: 1.5em
.. |meshReindex| image:: /static/common/mActionMeshReindex.png
   :width: 1.5em
.. |meshSelectExpression| image:: /static/common/mActionMeshSelectExpression.png
   :width: 1.5em
.. |meshSelectPolygon| image:: /static/common/mActionMeshSelectPolygon.png
   :width: 1.5em
.. |meshTransformByExpression| image:: /static/common/mActionMeshTransformByExpression.png
   :width: 1.5em
.. |meshaveraging| image:: /static/common/meshaveraging.png
   :width: 1.5em
.. |meshcontours| image:: /static/common/meshcontours.png
   :width: 1.5em
.. |meshcontoursoff| image:: /static/common/meshcontoursoff.png
   :width: 1.5em
.. |meshframe| image:: /static/common/meshframe.png
   :width: 1.5em
.. |meshvectors| image:: /static/common/meshvectors.png
   :width: 1.5em
.. |meshvectorsoff| image:: /static/common/meshvectorsoff.png
   :width: 1.5em
.. |metadata| image:: /static/common/metadata.png
   :width: 1.5em
.. |redo| image:: /static/common/mActionRedo.png
   :width: 1.5em
.. |refresh| image:: /static/common/mActionRefresh.png
   :width: 1.5em
.. |rendering| image:: /static/common/rendering.png
   :width: 1.5em
.. |saveEdits| image:: /static/common/mActionSaveEdits.png
   :width: 1.5em
.. |selectAdd| image:: /static/common/mIconSelectAdd.png
   :width: 1.5em
.. |selectRemove| image:: /static/common/mIconSelectRemove.png
   :width: 1.5em
.. |setProjection| image:: /static/common/mActionSetProjection.png
   :width: 1.5em
.. |symbology| image:: /static/common/symbology.png
   :width: 2em
.. |system| image:: /static/common/system.png
   :width: 1.5em
.. |temporal| image:: /static/common/temporal.png
   :width: 1.5em
.. |toggleEditing| image:: /static/common/mActionToggleEditing.png
   :width: 1.5em
.. |unchecked| image:: /static/common/unchecked.png
   :width: 1.3em
.. |undo| image:: /static/common/mActionUndo.png
   :width: 1.5em
.. |vertexCoordinates| image:: /static/common/mIconVertexCoordinates.png
   :width: 1.5em
