.. index:: Raster, Layer properties
.. _raster_properties_dialog:

*******************************************************
Raster Properties Dialog (Raster ဂုဏ်သတ္တိများ Dialog)
*******************************************************

.. only:: html

   .. contents::
      :local:

Raster layer တစ်ခုအတွက် property များကို ကြည့်ရန်နှင့် သတ်မှတ်ပေးရန်အတွက် မြေပုံရည်ညွှန်းချက်ထဲရှိ layer name ပေါ်တွင် double click နှိပ်ပါ သို့မဟုတ် layer name ပေါ်ကို right-click နှိပ်ပြီး ပေါ်လာသော menu မှ :guilabel:`Properties` ကိုရွေးပါ။ ထိုသို့ နှိပ်လိုက်ပါက :guilabel:`Raster Layer Properties` dialog ပွင့်လာပါမည်။

Dialog ထဲတွင် tab များစွာရှိပါသည်-

.. list-table::

  * - |metadata| :ref:`Information <raster_information>`
    - |system| :ref:`Source <raster_sourcetab>`
    - |symbology| :ref:`Symbology <raster_symbology>`:sup:`[1]`
  * - |transparency| :ref:`Transparency <raster_transparency>`:sup:`[1]`
    - |rasterHistogram| :ref:`Histogram <raster_histogram>`:sup:`[1]`
    - |rendering| :ref:`Rendering <raster_rendering>`
  * - |temporal| :ref:`Temporal <raster_temporal>`
    - |elevationscale| :ref:`Elevation <raster_elevation>`
    - |pyramids| :ref:`Pyramids <raster_pyramids>`
  * - |editMetadata| :ref:`Metadata <raster_metadata>`
    - |legend| :ref:`Legend <raster_server>`
    - |overlay| :ref:`QGIS Server <raster_server>`
  * - :ref:`External plugins <plugins>`:sup:`[2]` tabs
    -
    -

:sup:`[1]` :ref:`Layer styling panel <layer_styling_panel>` တွင်လည်းရရှိနိုင်ပါသည်။

:sup:`[2]` :ref:` အပြင်မှထည့်သွင်းထားသည့် plugins <plugins>` တွေကိုလည်း ဤ dialog တွင် tab တွေထည့်ထားလို့ရပါသည်။ ဤစာအုပ်ထဲမှာတော့ အဆိုပါအကြောင်းအရာတွေ ထည့်ရေးမထားပါဘူး။ ၎င်းတို့၏ သီးသန့်စာတမ်းများကို ကိုးကားပါ။

.. tip:: **Live update rendering**

   :ref:`layer_styling_panel` က Layer properties dialog ရဲ့ အသုံးများသည့် feature များကို ထောက်ပံ့ပေးပြီး layer စတိုင်များပြင်ဆင်ခြင်းကို ပိုမိုမြန်ဆန်စေရုံမကဘဲ map canvas ထဲကအပြောင်းအလဲများကို ကြည့်ရှုရာတွင် အသုံးဝင်သည့် widget တစ်ခုဖြစ်ပါသည်။

.. note::

   ထည့်မြှုပ်ထားသော layer များ (embedded layers) (:ref:`nesting_projects` တွင်ကြည့်ပါ) ၏ property များဖြစ်သည့် symbology ၊ label ၊ actions ၊ default values ၊ forms များကို 
   မူရင်း project file ကနေ ဆွဲထုတ်သည့်အတွက် လုပ်ဆောင်နေစဉ် ရပ်တန့်သွားမှုများ မဖြစ်ပေါ်စေရန် ထို layer များအတွက် layer properties dialog ကို အသုံးမပြုနိုင်ပါ။

.. _raster_information:

Information Properties (အချက်အလက်ဆိုင်ရာ ဂုဏ်သတ္တိများ)
========================================================

|metadata| :guilabel:`Information` သည် ဖတ်ရှုရုံအတွက်သာဖြစ်ပြီး လက်ရှိ layer ရဲ့ metadata နှင့် အကျဉ်းချုပ်သတင်းအချက်အလက်ကို အမြန်ကြည့်ရှုနိုင်သည့် စိတ်ဝင်စားစရာနေရာတစ်ခုဖြစ်ပါသည်။
ကြည့်ရှုနိုင်သော သတင်းအချက်လက်များမှာ - 

* Project ထဲရှိနာမည် ၊ file များသိမ်းထားသည့်လမ်းကြောင်း ၊ auxiliary file (တွဲဖက်ဖိုင်) များစာရင်း ၊ နောက်ဆုံးသိမ်းဆည်းခဲ့သော အချိန်နှင့်အရွယ်အစား၊ data ဖန်တီးသူ စသည့် အခြေခံအချက်လက်များ၊
* Data ဖန်တီးသူရဲ့ ထည့်သွင်းခဲ့တဲ့ အချက်အလက်ပေါ်မူတည်ပြီး အကျယ်အဝန်း၊ အကျယ်နှင့်အမြင့်၊ data အမျိုးအစားများ၊ GDAL driver နှင့် band များ၏ ကိန်းဂဏန်းများ၊
* Coordinate Reference System - နာမည်၊ ယူနစ်များ၊ နည်းလမ်း၊ တိကျမှု၊ အညွှန်း (ကိန်းဂဏန်း သို့မဟုတ် ကွဲပြားမှုများ)
* Layer proprties မှ ဖတ်ရှုနိုင်သည့် data အမျိုးအစား၊ အကျယ်အဝန်း၊ အကျယ်/အမြင့်၊ ချုံ့ထားမှု၊ pixel အရွယ်အစား၊ band များရဲ့ ကိန်းဂဏန်းများ၊ column များအရေအတွက်၊ raster ရဲ့ row (အတန်း)များနှင့် no-data တန်ဖိုးများ၊
* :ref:`filled metadata <raster_metadata>` ကနေရယူထားသည့် အသုံးပြုနိုင်စွမ်း၊ အကျယ်အဝန်း၊ ချိတ်ဆက်မှုများ၊ အဆက်အသွယ်လိပ်စာများ၊ သမိုင်းကြောင်းများ တို့ဖြစ်ပါသည်။

.. _raster_sourcetab:

Source Properties (အရင်းအမြစ်ဆိုင်ရာ ဂုဏ်သတ္တိများ)
====================================================

|system| :guilabel:`Source` tab သည် ရွေးချယ်ထားသော raster ရဲ့ အခြေခံသတင်းအချက်လက်များကို ဖော်ပြပေးပါသည်။ ဖော်ပြပေးသော အချက်အလက်များမှာ-

* :guilabel:`Layers Panel` ထဲတွင် ပြသပေးသော :guilabel:`Layer name`
* :guilabel:`Coordinate Reference System` သည် layer ရဲ့ :ref:`Coordinate Reference System (CRS) <layer_crs>` ကိုဖော်ပြပေးပါသည်။ Drop-down စာရင်းတွင်ပေါ်နေသည့် မကြာသေးမီက သုံးထားသော CRS ကိုရွေးချယ်ခြင်း သို့မဟုတ် |setProjection|:sup:`Select CRS` ကိုနှိပ်ခြင်းဖြင့် layer ရဲ့ CRS ကိုပြောင်းလဲနိုင်ပါသည်။ (:ref:`crs_selector` တွင်ကြည့်ပါ) 
  Layer ရဲ့ CRS မှားနေသည့်အခါ သို့မဟုတ် သတ်မှတ်မထားသည့်အခါမှသာ ဤနည်းလမ်းကိုအသုံးပြုပါ။ Data ကို reproject ပြန်လုပ်လိုပါက Processing မှ reprojection algorithm အသုံးပြုပါ သို့မဟုတ် :ref:`Save it as new dataset (Dataset အသစ်တစ်ခုအဖြစ်သိမ်းဆည်းခြင်း) <general_saveas>` ကိုအသုံးပြုပါ။

.. _figure_raster_properties:

.. figure:: img/rasterPropertiesDialog.png
   :align: center

   Raster Layer Properties - Source Dialog


.. index:: Symbology, Single Band Raster, Three Band Color Raster,
   Multi Band Raster

.. _raster_symbology:

Symbology Properties (သင်္ကေတဆိုင်ရာ ဂုဏ်သတ္တိများ)
====================================================

Raster layer ၏ symbology tab တွင် မတူညီသည့် အပိုင်း ၃ ပိုင်းရှိပါသည်-

* အသုံးပြုမည့် render (အရောင်ချယ်ခြင်း၊ အမြင်ပြင်ဆင်ခြင်းများ) အမျိုးအစားကို ထိန်းချုပ်ရန်အတွက် :guilabel:`Band rendering`
* Render data ပေါ်တွင် effect များထည့်ရန်အတွက် :guilabel:`Layer rendering`
* မြေပုံပေါ်တွင် rendering လုပ်ခြင်းကို အကောင်းဆုံးဖြစ်စေရန်အတွက် :guilabel:`Resampling` နည်းလမ်းများ

Band rendering (Band များကို Rendering ပြုလုပ်ခြင်း)
-----------------------------------------------------

QGIS တွင် :guilabel:`Render types` (Render အမျိုးအစား) အမျိုးမျိုးရှိပါသည်။ အသုံးပြုမည့် data အမျိုးအစားနှင့် မီးမောင်းထိုးပြချင်သော သတင်းအချက်အလက်ပေါ်မူတည်ပြီး renderer အမျိုးအစားကို ရွေးချယ်နိုင်ပါသည်။

#. :ref:`Multiband color <multiband_color>` - File တွင် များပြားသော band များပါဝင်လျှင် (ဥပမာ - band အများကြီးပါသော ဂြိုလ်တုဓာတ်ပုံ)
#. :ref:`Paletted/Unique values <paletted>` - Indexed palette တစ်ခုဖြင့် band တစ်ခုတည်းပါသော file များအတွက် (ဥပမာ - digital topographic မြေပုံများ) သို့မဟုတ် raster layer များ rendering လုပ်ရန်အတွက် palette များကို ယေဘုယျအသုံးပြုခြင်းအတွက်
#. :ref:`Singleband gray <singleband_gray>` - ဓာတ်ပုံရဲ့ band တစ်ခုတည်းကို မီးခိုးရောင်အဖြစ် ပြသပေးပါသည်။ File သည် band အများကြီးလည်း မပါသလို paletted လည်းမဟုတ်လျှင် QGIS က ဤ render နည်းကို အသုံးပြုပါသည်။ (ဥပမာ - မြေမျက်နှာသွင်ပြင် အနိမ့်အမြင့်များပြသောမြေပုံ)
#. :ref:`Singleband pseudocolor <label_colormaptab>` - တစ်ဆက်တည်းဖြစ်နေသည့် palette (continuous palette) သို့မဟုတ် အ‌ရောင်မြေပုံများအတွက် ဤ renderer ကို အသုံးပြုနိုင်ပါသည်။ (ဥပမာ - ပင်လယ်ရေမျက်နှာပြင် အနိမ့်အမြင့်ပြ မြေပုံ)   
#. :ref:`Hillshade <hillshade_renderer>` - Band တစ်ခုမှ hillshade ဖန်တီးသည့်အခါ အသုံးပြုပါသည်။   
#. :ref:`Contours <raster_contours>` - Raster band တစ်ခုအတွက် ကွန်တိုများ (အနိမ့်အမြင့်ပြမျဉ်းများ) ကို on the fly (အလျှင်အမြန်/ချက်ချင်း) ဖန်တီးသည့်အခါတွင် အသုံးပြုပါသည်။


.. _multiband_color:

Multiband color (Band မျိုးစုံအရောင်)
......................................

Band မျိုးစုံဖြင့် အရောင်စုံမြေပုံပြင်ဆင်ခြင်းတွင် ဓာတ်ပုံမှ band ၃ ခုကို ရွေးချယ်ပြီး အနီ၊ အစိမ်း သို့မဟုတ် အပြာ အဖြစ် အသုံးပြုပါသည်။ Raster ၏ band တစ်ခုချင်းဆီအတွက် :guilabel:`Min` နှင့် :guilabel:`Max` တန်ဖိုးများကို အလိုလျောက် တွက်ထုတ်ပြီး သင့်တော်သော အရောင်များကိုထည့်ပေးပါသည်။ တန်ဖိုးများကို :ref:`Min/Max Value Settings <minmaxvalues>` အပိုင်းတွင် ထိန်းချုပ်နိုင်ပါသည်။

:guilabel:`အရောင်ကွဲပြားထင်ရှားမှုမြှင့်တင်ခြင်း (Contrast enhancement)` ကိုလည်းအသုံးပြုနိုင်ပါသေးသည်။ နည်းလမ်းများမှာ - 
'ဘာမှမလုပ်ဘဲအရှိအတိုင်းထားခြင်း (No enhancement)' ၊ 'အနည်းဆုံးနှင့်အများဆုံးတန်ဖိုးများပေါ်မူတည်ပြီး ဖြန့်ထုတ်ခြင်း (Stretch to MinMax)' ၊ 'ဖြန့်ထုတ်ပြီးနောက် အနည်းဆုံးနှင့်အများဆုံးတန်ဖိုးများကိုဖြတ်ထုတ်ခြင်း (Stretch and clip to MinMax)' နှင့် 'အနည်းဆုံးအများဆုံးတန်ဖိုးများကိုဖြတ်ထုတ်ခြင်း (Clip to min max)' တို့ဖြစ်ပါသည်။

.. index:: Contrast enhancement

.. note:: **အရောင်ကွဲပြားထင်ရှားမှုမြှင့်တင်ခြင်း (Contrast enhancement)**

   GRASS raster များကိုထည့်သောအခါ QGIS က အ‌ရောင်ကွဲပြားမှုမြှင့်တင်ခြင်းအတွက် *Stretch to min max* ကို အလိုလျောက် အသုံးပြုပါလိမ့်မည်။
   
.. _figure_raster_multiband:

.. figure:: img/rasterMultibandColor.png
   :align: center

   Raster Symbology - Multiband color rendering (Multiband color rendering ပြုလုပ်ခြင်း)


.. tip:: **Band မျိုးစုံပါသော raster တစ်ခုရဲ့ band တစ်ခုတည်းကို ကြည့်ရှုခြင်း (Viewing a Single Band of a Multiband Raster)**

   Band မျိုးစုံပါသော raster တစ်ခုရဲ့ band တစ်ခုတည်းကို (ဥပမာ - အနီရောင်) ကြည့်လိုလျှင် အစိမ်းနှင့်အပြာ band ကို :guilabel:`Not Set` ကိုထားရမည်လို့ ထင်ကောင်းထင်ပါလိမ့်မည်။
   သို့သော် အဖြစ်သင့်ဆုံးနည်းလမ်းသည် ဓာတ်ပုံကို :ref:`Singleband gray <singleband_gray>` သို့ သတ်မှတ်လိုက်ပြီး အနီရောင် band ကို :guilabel:`Gray band` အဖြစ်ထားလိုက်ခြင်း ဖြစ်ပါသည်။

.. _paletted:

Paletted/Unique values (သီးခြားတန်ဖိုးများ)
............................................

အရောင်ဇယားပါဝင်သော band တစ်ခုတည်းဖြစ်သည့် ဓာတ်ပုံများကို ပြသသော ပုံမှန်နည်းလမ်းဖြစ်ပါသည်။ ဤပုံများတွင် pixel တန်ဖိုးတစ်ခုချင်းစီတိုင်းကို အရောင်သတ်မှတ်ပေးပါသည်။ ဓာတ်ပုံကို စထည့်လိုက်တာနှင့် ကျပန်းအရောင်တွဲစပ်မှုကို အလိုလျောက်ထည့်ပေးပါသည်။

ဤနည်းလမ်းကို raster band အမျိုးအစားအားလုံးအတွက် အသုံးပြုနိုင်ပြီး raster တန်ဖိုးတစ်ခုကို အရောင်တစ်မျိုးသတ်မှတ်ပေးပါသည်။

အရောင်ပြောင်းလဲလိုလျှင် အရောင်ပေါ်တွင် double-click နှိပ်လိုက်သည်နှင့် :guilabel:`အရောင်ရွေးချယ်ပါ (Select color)` ဆိုတဲ့ dialog ပေါ်လာပါမည်။

ဘယ်အရောင်က ဘာအမျိုးအစား ဖြစ်ပါသည်ဆိုသည့် အညွှန်းကိုလည်း သတ်မှတ်ပေးလို့ရပါသည်။ သတ်မှတ်ပေးထားသော အညွှန်းသည် raster layer ရဲ့ ရည်ညွှန်းချက်တွင် ပေါ်နေပါလိမ့်မည်။

အရောင်ဇယားအတွင်းရှိ ရွေးချယ်ထားသည့် row များပေါ်တွင် right-click နှိပ်လိုက်သည့်အခါ menu တစ်ခုပေါ်လာပါလိမ့်မည်-

* :guilabel:`Change Color...` (ရွေးချယ်ထားသောအရာကို အရောင်ပြောင်းလဲပါ)
* :guilabel:`Change Opacity...` (ရွေးချယ်ထားသောအရာကို ဖောက်ထွင်းမြင်နိုင်မှုပြောင်းလဲပါ)
* :guilabel:`Change Label...` (ရွေးချယ်ထားသောအရာကို အညွှန်းပြောင်းလဲပါ)

.. _figure_raster_paletted_unique:

.. figure:: img/rasterPalettedUniqueValue.png
   :align: center

   Raster သင်္ကေတဆိုင်ရာ - Paletted unique value rendering

အရောင်မြေပုံ (color map) ၏ ညာဘက်အောက်က :guilabel:`...` (:sup:`Advanced options`) နှိပ်လိုက်ပါက pulldown menu တွင် သိမ်းထားသော file ကို color map ထဲသို့ထည့်ခြင်း (:guilabel:`Load Color Map from File...`) နှင့် Color map ကို file အဖြစ်သိမ်းထားခြင်း (:guilabel:`Export Color Map to File...`) နှင့် GIS ထဲက layer တစ်ခုဆီကနေ class များကို ထည့်သွင်းခြင်း (:guilabel:`Load Classes from Layer`) တို့ လုပ်ဆောင်နိုင်ပါသည်။

.. _singleband_gray:

Singleband gray (မီးခိုးရောင်တစ်မျိုးတည်းသာပြသသော Singleband)
..............................................................

ဤ rendering နည်းလမ်းသည် :guilabel:`Color gradient` - 'အမဲကနေအဖြူ' သို့မဟုတ် 'အဖြုကနေအမဲ' ဖြင့် band တစ်မျိုးတည်းကို အသုံးပြုပါသည်။ 
:ref:`Min/Max Value Settings (အနည်းဆုံး/အများဆုံး) <minmaxvalues>` ထဲတွင် အရောင်များအတွက် (:guilabel:`Min (အနည်းဆုံး)` and :guilabel:`Max (အများဆုံး)`) တန်ဖိုးများ ပြောင်းလဲနိုင်ပါသည်။

:guilabel:`Contrast enhancement (အရောင်ကွဲပြားထင်ရှားမှုမြှင့်တင်ခြင်း)` နည်းလမ်းကိုလည်း အသုံးပြုလို့ရပါသည်။ နည်းလမ်းများမှာ -
'ဘာမှမလုပ်ဘဲအရှိအတိုင်းထားခြင်း (No enhancement)' ၊ 'အနည်းဆုံးနှင့်အများဆုံးတန်ဖိုးများပေါ်မူတည်ပြီး ဖြန့်ထုတ်ခြင်း (Stretch to MinMax)' ၊ 'ဖြန့်ထုတ်ပြီးနောက် အနည်းဆုံးနှင့်အများဆုံးတန်ဖိုးများကိုဖြတ်ထုတ်ခြင်း (Stretch and clip to MinMax)' နှင့် 'အနည်းဆုံးအများဆုံးတန်ဖိုးများကိုဖြတ်ထုတ်ခြင်း (Clip to min max)' တို့ဖြစ်ပါသည်။

.. _figure_raster_gray:

.. figure:: img/rasterSingleBandGray.png
   :align: center

   Raster သင်္ကေတဆိုင်ရာ - Singleband gray rendering

ရွေးချယ်ထားသည့် color gradient (အရောင်အဆင့်ဆင့်) ပေါ်မူတည်ပြီး pixel များကို အရောင်သတ်မှတ်ပေးခြင်းဖြစ်ပြီး layer ရဲ့ ရည်ညွှန်းချက်တွင် (:guilabel:`Layers` panel ထဲနှင့် layout :ref:`legend
item <layout_legend_item>` ထဲ) တစ်ဆက်တည်းဖြစ်နေသည့် color ramp (အရောင်အစုအဖွဲ့) ဖြင့် ပြသပါသည်။ Setting များကိုပြင်ဆင်လိုလျှင် :guilabel:`Legend settings...` ကိုနှိပ်ပါ။ :ref:`raster_legend_settings` တွင်အသေးစိတ်ဖတ်ရှုနိုင်ပါသည်။ 


.. index:: Color map, Color interpolation, Discrete
.. _label_colormaptab:

Singleband pseudocolor (အ‌ရောင်အတုဖြင့်ပြသသော Singleband)
..........................................................

တစ်ဆက်တည်းဖြစ်နေသည့်အရောင်အစဉ် (continuous palette) ပါဝင်ပြီး band တစ်ခုတည်းပါရှိသည့် file များအတွက် rendering option တစ်ခုဖြစ်ပါသည်။ Multiband raster တစ်ခု၏ band တစ်ခုအတွက် color map များဖန်တီးရာတွင်လည်း အသုံးပြုနိုင်ပါသည်။

.. _figure_raster_pseudocolor:

.. figure:: img/rasterSingleBandPseudocolor.png
   :align: center

   Raster သင်္ကေတဆိုင်ရာ - Singleband pseudocolor rendering


Layer တစ်ခု၏ band နှင့် :ref:`values range (တန်ဖိုးအတိုင်းအတာ) <minmaxvalues>` အသုံးပြုပြီး အတန်းအစား (classes) များအတွင်း pixel များအတွက် ကိုယ်စားပြုအရောင်များကို interpolate (ဖြည့်စွက်ထည့်သွင်းခြင်း) နှင့် သတ်မှတ်ခြင်းများကို လုပ်ဆောင်နိုင်ပါသည်။ :ref:`color_ramp_shader` တွင်ထပ်မံဖတ်ရှုနိုင်ပါသည်။

ရွေးချယ်ထားသည့် color ramp ပေါ်မူတည်ပြီး pixel များကို အရောင်သတ်မှတ်ပေးခြင်းဖြစ်ပြီး layer ရဲ့ ရည်ညွှန်းချက်တွင် (:guilabel:`Layers` panel ထဲနှင့် layout :ref:`legend
item <layout_legend_item>` ထဲ) တစ်ဆက်တည်းဖြစ်နေသည့် color ramp ဖြင့် ပြသပါသည်။ Setting များကိုပြင်ဆင်လိုလျှင် :guilabel:`Legend settings...` ကိုနှိပ်ပါ။ :ref:`raster_legend_settings` တွင်အသေးစိတ်ဖတ်ရှုနိုင်ပါသည်။ 

.. index:: Hillshade
.. _hillshade_renderer:

Hillshade (တောင်အရိပ်)
.......................

Hillshading (တောင်အရိပ်များထည့်ခြင်း) ကိုအသုံးပြုပြီး raster layer ၏ band တစ်ခုကို rendering ပြုလုပ်ပေးပါသည်။

.. _figure_raster_hillshade:

.. figure:: img/rasterHillshade.png
   :align: center

   Raster သင်္ကေတဆိုင်ရာ - Hillshade rendering

ရွေးချယ်စရာနည်းလမ်းများမှာ - 

* :guilabel:`Band` - Raster band ကို အသုံးပြုခြင်း။
* :guilabel:`Altitude` - အလင်းရောင်အရင်းအမြစ်၏အမြင့်ထောင့် (ပုံမှန်ဆိုလျှင် ``၄၅°`` ဖြစ်ပါသည်)။
* :guilabel:`Azimuth` - အလင်းရောင်အရင်းအမြစ်၏ မြောက်အရပ်မှလက်ယာရစ်တိုင်း၍ ရလာသော ထောင့် (Azimuth) (ပုံမှန်ဆိုလျှင် ``၃၁၅°`` အနောက်မြောက်ထောင့် ဖြစ်ပါသည်)။ 
* :guilabel:`Z Factor` - Raster ရဲ့မူရင်းအမြင့်တန်ဖိုးများကို ဆတိုးမြှောက်ပေးသော တန်ဖိုးဖြစ်သည် (ပုံမှန်ဆိုလျှင် ၁ ဖြစ်သည်၊ မြေမျက်နှာသွင်ပြင်က ပြင်ညီအရမ်းဆန်နေလျှင် ၁ ထက်ပိုကြီးသော ဂဏန်းကို အသုံးပြုသင့်ပါသည်)။
* |checkbox| :guilabel:`Multidirectional` - အရပ်မျက်နှာဘက်ပေါင်းစုံမှ တောင်အရိပ်ဖန်တီးခြင်းတွင် အသုံးပြုပါသည် (ပုံမှန်ဆိုလျှင် ၎င်းလုပ်ဆောင်ချက်ကို ပိတ်ထားပါသည်)။

.. _raster_contours:

Contours (ကွန်တိုများ)
.......................

ဤ renderer ကို မူရင်း raster band မှ တွက်ချက်ပြီး ကွန်တိုမျဉ်းများ ဖန်တီးရာတွင် အသုံးပြုပါသည်။


.. _figure_raster_contours:

.. figure:: img/rasterContours.png
   :align: center

   Raster Symbology - Contours rendering (ကွန်တိုမျဉ်းများ Rendering ပြုလုပ်ခြင်း)

ရွေးချယ်စရာနည်းလမ်းများမှာ - 

* :guilabel:`Input band` - အသုံးပြုမည့် Raster band၊
* :guilabel:`Contour interval` - ကပ်လျှက်ရှိသောကွန်တိုမျဉ်း နှစ်ခုကြား အကွာအဝေး၊
* :guilabel:`Contour symbol` - ကွန်တိုမျဉ်း များအတွက် အသုံးပြုရန် :ref:`symbol <vector_line_symbols>` (သင်္ကေတ)၊
* :guilabel:`Index contour interval` - ကပ်လျှက်ရှိသော **index contours** နှစ်ခုကြား အကွာအဝေး။ Index cotours ဆိုသည်မှာ ရှာဖွေရ/ဖတ်ရလွယ်ကူစေရန် ပိုပြီးထင်ရှားအောင် အခြားကွန်တိုမျဉ်းများထက် အရောင်ပိုထင်းထားပြီး အမြင့်တန်ဖိုးကိုလည်း မျဥ်းပေါ်မှာ ရေးသားဖော်ပြထားပါသည်။
* :guilabel:`Index contour symbol` - Index contour lines များအတွက် အသုံးပြုသော symbol ၊
* :guilabel:`Input downscaling` - အသုံးပြုမည့် data ဘယ်လောက်ထိ ပမာဏလျှော့ချမလဲဆိုသည့်တန်ဖိုး ဖြစ်ပါသည်။ (ပုံမှန်အားဖြင့် ``4.0`` ဖြစ်ပါသည်)

  ဥပမာအားဖြင့် အသုံးပြုသော raster နှင့် ထွက်လာမည့် raster အရွယ်အစားကို အတူတူထားပြီး ကွန်တိုမျဉ်းများကို ဖန်တီးမည်ဆိုလျှင် ကွန်တိုမျဉ်းတွေ အများကြီးရလာမှာဖြစ်ပြီး အရမ်းကိုပြွတ်သိပ်နေမည်ဖြစ်ပါသည်။ ဤသို့ ပြွတ်သိပ်နေမှု မဖြစ်စေရန် မူရင်း raster ကို ကြည်လင်ပြတ်သားမှု (resolution) လျော့ချပြီး အသုံးပြုရလွယ်ကူအောင်လုပ်တဲ့ တန်ဖိုးကို "downscale" factor ဟုခေါ်ပါသည်။ အကျယ် 1000 x 500 ရှိတဲ့ raster ပုံကို downscale တန်ဖိုး ၁၀ အသုံးပြုမည်ဆိုလျှင် မူရင်း raster ကို 100 x 50 အနေနဲ့ပဲအသုံးပြုမှာဖြစ်ပါသည်။ Downscale ဂဏန်းတန်ဖိုး ပိုကြီးလေလေ ကွန်တူမျဉ်းများ လျော့နည်းသွားပြီး ကိုင်တွယ်ရတာ ပိုလွယ်ကူလေလေ ဖြစ်ပါသည် (သို့သော် အားနည်းချက်အနေဖြင့် တချို့အသေးစိတ်တန်ဖိုးများ ပျောက်ကွယ်သွားပါမည်)။

.. _minmaxvalues:

Setting the min and max values (အနည်းဆုံးနှင့် အများဆုံးတန်ဖိုးများ သတ်မှတ်ခြင်း)
..................................................................................

ပုံမှန်အားဖြင့် QGIS သည် raster band အားလုံး၏ :guilabel:`အနည်းဆုံး` နှင့် :guilabel:`အများဆုံး` တန်ဖိုးများကို တွက်ထုတ်ပေးပါသည်။ အရမ်းနိမ့်လွန်း/မြင့်လွန်းသော တန်ဖိုးများသည် raster ကို ပုံဖော်ပြသခြင်း လုပ်ဆောင်သည့်နေရာတွင် အမှားများ၊ အခက်အခဲများ ဖြစ်စေနိုင်ပါသည်။ :guilabel:`Min/Max Value Settings` ကိုအသုံးပြုပြီး ပုံဖော်ပြသခြင်းကို လွယ်ကူအောင်လုပ်နိုင်ပါသည်။

.. _figure_raster_minmaxvalues:

.. figure:: img/rasterMinMaxValues.png
   :align: center

   Raster Symbology - အနည်းဆုံး နှင့် အများဆုံး တန်ဖိုးများ Settings


ရွေးချယ်စရာနည်းလမ်းများမှာ - 

* |radioButtonOff| :guilabel:`User defined` (အသုံးပြုသူမှသတ်မှတ်သော) - Band များ၏ မူရင်း :guilabel:`အနည်းဆုံး` နှင့် :guilabel:`အများဆုံး` တန်ဖိုးများကို ပြင်ဆင်ရေးသားနိုင်ပါသည်။
* |radioButtonOff| :guilabel:`Cumulative count cut` (အစုအရေအတွက်အရဖြတ်တောက်ခြင်း) - အစွန်းရောက်တန်ဖိုးများ (outliers) ကို ဖျက်ပေးသည်။ စံသတ်မှတ်ထားသည့် တန်ဖိုးအတိုင်းအတာမှာ ``၂%`` မှ ``၉၈%`` ထိဖြစ်ပြီး လိုအပ်သလိုလည်း ပြင်ဆင်နိုင်ပါသည်။
* |radioButtonOn| :guilabel:`Min / max` (အနည်းဆုံး/အများဆုံး) - ဓာတ်ပုံ၏ band တွင် ပါဝင်လာသည့် တန်ဖိုးအတိုင်းအတာတစ်ခုလုံးကို အသုံးပြုပါသည်။
* |radioButtonOff| :guilabel:`Mean +/- standard deviation x` (ပျမ်းမျှစံသွေဖယ်ကိန်း) - စံသွေဖယ်မှု သို့မဟုတ် များစွာသော စံသွေဖယ်မှု များအတွင်းကျရောက်သော တန်ဖိုးများကိုသာ အသုံးပြုသော အရောင်ဇယား တစ်ခုကိုဖန်တီးပေးပါသည်။ 
  Raster rendering ကို ထိခိုက်နိုင်သော ပုံမှန်မဟုတ်သည့် ကြီးမားသောတန်ဖိုးများရှိသည့် cell တစ်ခု သို့မဟုတ် နှစ်ခုကို ပါဝင်နေသည့်အခါ ဒီနည်းလမ်းသည် အသုံးဝင်ပါသည်။

Band များရဲ့ အနည်းဆုံးနှင့် အများဆုံးတန်ဖိုးများကို တွက်ချက်ခြင်းများသည် အောက်ပါတို့ကို အခြေခံပါသည်-

* :guilabel:`Statistics extent (Statistics အကျယ်အဝန်း)` - :guilabel:`Whole raster (Raster တစ်ခုလုံး)` ၊ :guilabel:`Current canvas (လက်ရှိမြင်နေရသော canvas အကျယ်)` သို့မဟုတ် :guilabel:`Updated canvas (အသစ်နေရာရွှေ့လိုက်သည့် canvas အကျယ်)` တို့အတွက် အသုံးပြုနိုင်ပါသည်။ 
  :guilabel:`Updated canvas (အသစ်နေရာရွှေ့လိုက်သည့် canvas အကျယ်)` ဆိုသည်မှာ rendering အတွက် အသုံးပြုသော အနည်းဆုံး/အများဆုံး တန်ဖိုးများသည် canvas ရဲ့ အကျယ်အဝန်းအတိုင်း ပြောင်းလဲနေခြင်းကို ဆိုလိုပါသည်။
* :guilabel:`Accuracy (တိကျမှု)` - :guilabel:`ခန့်မှန်း (ပိုမြန်)` သို့မဟုတ် :guilabel:`အရှိအတိုင်း (ပိုနှေး)` ဖြစ်နိုင်ပါသည်။

.. note:: တချို့ setting များအတွက် အမှန်တကယ်ရှိသည့် အနည်းဆုံး/အများဆုံး တန်ဖိုးများကို ဖော်ပြရန် layer properties dialog မှ :guilabel:`Apply` ကို နှိပ်ပေးရန် လိုအပ်ပါသည်။

.. _color_ramp_shader:

Color ramp shader classification (Color ramp shader အတန်းအစားခွဲခြားခြင်း)
...........................................................................

Scalar dataset (raster သို့မဟုတ် mesh contour) များကို အတန်းအစားခွဲခြားခြင်းနှင့် ကိုယ်စားပြုခြင်းများအတွက် ဒီနည်းလမ်းကို အသုံးပြုလို့ရပါသည်။ 
:ref:`color ramp <color-ramp>` တစ်ခုကို အတန်းအစား (classes) အရေအတွက်နှင့် တွဲပေးလိုက်လျှင် အတန်းအစားအရေအတွက်အတိုင်း သင့်တော်သော မြေပုံတစ်ခု ဖန်တီးပေးပါသည်။ 
တန်ဖိုးအတိုင်းအတာများနှင့် အတန်းအစားခွဲခြားခြင်းနည်းလမ်း (classification mode) ပေါ်မူတည်ပြီး အရောင်တစ်ခုချင်းဆီကို စီစဉ်ပြီးထည့်သွားပါမည်။ 
ထို့နောက် အတန်းအစားပေါ်မူတည်ပြီး scalar dataset element များကို အရောင်သတ်မှတ်ပေးပါသည်။

.. _figure_raster_colorrampshader:

.. figure:: img/color_ramp_shader.png
   :align: center

   Color ramp shader ဖြင့် dataset တစ်ခုကို အတန်းအစားခွဲခြားခြင်း

#. :guilabel:`အနည်းဆုံး` နှင့် :guilabel:`အများဆုံး` တန်ဖိုးများကို သတ်မှတ်ပေးရမည်ဖြစ်ပြီး အတန်းအစားများရဲ့ အကျယ်တန်ဖိုးများတွက်ထုတ်ရာတွင်အသုံးပြုပါသည်။ 
   ပုံမှန်အားဖြင့် QGIS သည် ၎င်းတန်ဖိုးများကို dataset မှ တွက်ထုတ်ပေးပါသည်၊ သို့သော် စိတ်ကြိုက်ပြင်ဆင် သတ်မှတ်လို့ရပါသည်။ 
#. Scalar element များကို ဘယ်လိုအ‌ရောင်သတ်မှတ်ပေးမည်ဆိုသည်ကို :guilabel:`Interpolation` (ရှိပြီးသားတန်ဖိုးများကိုအသုံးပြု၍ တန်ဖိုးမရှိသေးသည့်အရာများအတွက်ဖော်ထုတ်ခြင်း) ထည့်သွင်းမှုက သတ်မှတ်ပေးပါသည်-

   * :guilabel:`Discrete` (:guilabel:`Value` column ရဲ့ခေါင်းစည်းမှာပေါ်နေတဲ့ ``<=`` သင်္ကေတတစ်ခု) - တန်းတူ သို့မဟုတ် အမြင့်ဆုံးတန်ဖိုး ပါဝင်သည့် အနီးစပ်ဆုံး အရောင်မြေပုံ (color map) မှ အရောင်ကို အသုံးပြုပါသည်။	 
   * :guilabel:`Linear` - Pixel တန်ဖိုး၏ အထက်နှင့်အောက်မှာရှိသည့် color map entry များကို အဖြောင့်အတိုင်း (linearly) interpolate ပြုလုပ်ပြီး အရောင်သတ်မှတ်ပေးပါသည်။ ဆိုလိုသည်မှာ dataset တစ်ခုစီတိုင်းသည် သီးခြားအရောင်တစ်မျိုးရှိခြင်း ဖြစ်ပါသည်။
   * :guilabel:`Exact` - (:guilabel:`Value` column ရဲ့ခေါင်းစည်းမှာပေါ်နေတဲ့ ``=`` သင်္ကေတတစ်ခု) - color map entry တန်ဖိုးများနှင့် တစ်ထပ်တည်းတူညီတဲ့ pixel များကိုသာ အရောင်သတ်မှတ်ပေးပါသည်။ တခြား pixel များကို rendering လုပ်မည်မဟုတ်ပါ။	 
#. :guilabel:`Color ramp` widget သည် dataset အတွက် သတ်မှတ်မည့် color ramp ကို ရွေးချယ်ရာတွင်လွယ်ကူအောင်ပြုလုပ်ပေးပါသည်။ 
   :ref:`Color ramp widget <color_ramp_widget>` ပုံစံအတိုင်း အသစ်တစ်ခုကိုဖန်တီးနိုင်သလို လက်ရှိရွေးချယ်ထားသည်ကိုလည်း တည်းဖြတ်ပြင်ဆင်ပြီး သိမ်းဆည်းထားနိုင်ပါသည်။ 
   Color ramp ၏ နာမည်ကို configuration ထဲတွင် သိမ်းဆည်းပေးထားပါသည်။
#. The :guilabel:`Label unit suffix` သည် ရည်ညွှန်းချက်တွင် တန်ဖိုး၏နောက်မှ label တစ်ခုထည့်ပေးပါသည်။ :guilabel:`Label precision` ဖြင့် label ‌ပြသရာတွင် ဒဿမ ဂဏန်းအရေအတွက်ကို ထိန်းချုပ်နိုင်ပါသည်။   
#. Classification :guilabel:`Mode` (အတန်းအစားခွဲခြားခြင်းနည်းလမ်း) သည် အတန်းအစားများအတွက် တန်ဖိုးများကို မည်သို့ခွဲဝေပိုင်းခြားမလဲဆိုသည်ကို လွယ်ကူအောင် ကူညီပေးပါသည်-

   * :guilabel:`Equal interval` (တူညီသည့်အပိုင်းအခြား) - အတန်းအစားများတွင် တူညီသည့် ပမာဏရှိစေရန် အကန့်အသတ်တန်ဖိုးများဖြင့် :guilabel:`Number of classes (အတန်းအစားအရေအတွက်)` ကို သတ်မှတ်ပေးပါသည်။	 
   * :guilabel:`Continuous` (တဆက်တစပ်တည်း) - အတန်းအစားအရေအတွက်နှင့် အရောင်များကို color ramp stops (color ramp အဖြတ်များ) မှ ရယူပါသည်။ 
     တန်ဖိုးကန့်သတ်ချက်များကို color map တွင်ရှိသည့် stops (အဖြတ်များ) ပေါ်မူတည်ပြီး သတ်မှတ်ပါသည်။ 
   * :guilabel:`Quantile` (ပမာဏအလိုက်) - အတန်းအစားများတွင် တူညီသည့် element အရေအတွက်ရှိစေရန် အကန့်အသတ်တန်ဖိုးများဖြင့် :guilabel:`Number of classes` (အတန်းအစားအရေအတွက်) ကို သတ်မှတ်ပေးပါသည်။ 
     :ref:`mesh layers <mesh_symbology_contours>` များတွင် အသုံးပြုနိုင်မည်မဟုတ်ပါ။
#. ထို့နောက် :guilabel:`Classify` (အတန်းအစားခွဲခြင်း) သို့မဟုတ် အတန်းအစားများကိုညှိနှိုင်းပြင်ဆင်ခြင်း လုပ်ဆောင်နိုင်ပါသည်-

   * |symbologyAdd| :sup:`Add values manually` (တန်ဖိုးများ ရိုက်ထည့်ခြင်း) ဖြင့် ဇယားထဲကို တန်ဖိုးတစ်ခုထည့်သွင်းနိုင်ပါသည်။
   * |symbologyRemove| :sup:`Remove selected row` (ရွေးချယ်ထားသော row အားဖျက်ခြင်း) ဖြင့် ဇယားမှရွေးချယ်ထားသော တန်ဖိုးများကိုဖျက်နိုင်ပါသည်။  
   * :guilabel:`Value` column ကို double click နှိပ်ပြီး အတန်းအစားတန်ဖိုးကို ပြင်ဆင်နိုင်ပါသည်။   
   * :guilabel:`Color` column ကို double click နှိပ်ပြီး :guilabel:`Change color` (အရောင်ပြောင်းလဲခြင်း) dialog ကိုဖွင့်ပါ။ ထို့နောက် ထိုတန်ဖိုးအတွက် ကြိုက်နှစ်သက်ရာအရောင်ကို ရွေးချယ်နိုင်ပါသည်။	 
   * :guilabel:`Label` column ကို double click နှိပ်ပြီး အတန်းအစား၏ အညွှန်းကိုပြင်ဆင်နိုင်ပါသည်။ သို့သော် Idenfity feature tool ကို အသုံးပြုသောအခါ ပြင်လိုက်သည့် တန်ဖိုးကို ပြသနေလိမ့်မည်မဟုတ်ပါ။	 
   * အရောင်မြေပုံ (color map) ထဲရှိ ရွေးချယ်ထားသည့် row များပေါ်တွင် right-click နှိပ်လိုက်လျှင် ထိုရွေးချယ်ထားသည်များအတွက် :guilabel:`Change Color...` (အရောင်ပြောင်းလဲရန်) နှင့် :guilabel:`Change Opacity...` (အလင်းဖောက်နိုင်မှုပြောင်းလဲရန်) menu တစ်ခုပေါ်လာမည် ဖြစ်ပါသည်။

   ရှိနေပြီးသား color table တစ်ခုကိုထည့်သွင်းရန် |fileOpen| :sup:`Load color map from file` သို့မဟုတ် နောက်မှအသုံးပြုနိုင်ရန် color table တစ်ခုကိုသိမ်းဆည်းရန်အတွက် |fileSaveAs| :sup:`Export color map to file` ခလုတ်များကို အသုံးပြုနိုင်ပါသည်။

#. Linear (မျဥ်းဖြောင့်အတိုင်း) :guilabel:`Interpolation` ဖြင့် အောက်ပါတို့ကိုလည်း စိတ်ကြိုက်ပြင်ဆင်နိုင်ပါသည်-

   * |checkbox| :guilabel:`Clip out of range values` - ပုံမှန်အားဖြင့် linear နည်းလမ်းသည် ပထမဆုံးအတန်းအစား (နောက်ဆုံးအတန်းအစားအထိ) အရောင်ကို သတ်မှတ်ထားသည့် :guilabel:`Min` တန်ဖိုး (သတ်မှတ်ထားသည့် :guilabel:`Max` တန်ဖိုးအထိ) အောက် နည်းသည့် တန်ဖိုးများအတွက် သတ်မှတ်ပေးပါသည်။ ဤတန်ဖိုးများကို အသုံးပြုပြီး rendering မလုပ်လိုလျှင် ဤ setting ကို စမ်းသုံးကြည့်ပါ။
   * :guilabel:`Legend settings` - :guilabel:`Layers` panel နှင့် layout :ref:`legend item <layout_legend_item>` ထဲတွင် ဖော်ပြရန်။ :ref:`raster_legend_settings` တွင် အသေးစိတ်ကြည့်ရှိနိုင်ပါသည်။
   
   
.. _raster_legend_settings:

Customize raster legend (Raster ရည်ညွှန်းချက်များကို စိတ်ကြိုက်ပြင်ဆင်ခြင်း)
.............................................................................

Raster တစ်ခု သို့မဟုတ် mesh layer တစ်ခုကို color ramp တစ်ခု သတ်မှတ်ပေးသည့်အခါ ဘယ်အရောင်က ဘာကိုဆိုလိုသလဲ ဆိုသည်ကိုရှင်းပြရန် legend (ရည်ညွှန်းချက်) တစ်ခု ပြသရန်လိုအပ်ပါသည်။ 
ပုံမှန်အားဖြင့် QGIS သည် :guilabel:`Layers` panel နှင့် layout :ref:`legend item <layout_legend_item>` ထဲတွင် အနည်းဆုံး/အများဆုံး တန်ဖိုးများဖြင့် တစ်ဆက်တည်းဖြစ်နေသည့် color ramp တစ်ခုဖြင့် ပြသပေးပါသည်။ 
ထိုမူရင်းပြသချက်ကို မကြိုက်လျှင် classification widget ထဲရှိ :guilabel:`Legend settings` မှာ စိတ်ကြိုက်ပြင်ဆင်နိုင်ပါသည်။

.. _figure_raster_legend_settings:

.. figure:: img/raster_legend_settings.png
   :align: center

   Raster ရည်ညွှန်းချက်တစ်ခုကို ပြင်ဆင်ခြင်း

ဤ dialog ထဲတွင် |checkbox|:guilabel:`Use continuous legend` ကို အမှန်ခြစ်ပြီး ဆက်တိုက်ရည်ညွှန်းချက်များကို အသုံးပြုလို့ရပါသည်။ 
အမှန်ခြစ် ဖြုတ်ထားလျှင် မတူညီသောအတန်းအစားများနှင့်သက်ဆိုင်သည့် သီးခြားအရောင်များဖြင့် ဖော်ပြပေးပါသည်။ 
:ref:`singleband gray <singleband_gray>` ဖြစ်သည့် raster symbology အတွက် ဤနည်းလမ်းကို အသုံးပြု၍မရနိုင်ပါ။

:guilabel:`Use continuous legend` ကိုအမှန်ခြစ်ထားလျှင် ရည်ညွှန်းချက်၏ label (အညွှန်း) များတင်မက layout properties (အပြင်အဆင်ဆိုင်ရာ) ကိုပါ စိတ်ကြိုက်ပြင်ဆင်လို့ရနိုင်ပါသည်။

**Labels (အညွှန်းများ)**

* Label များတွင် :guilabel:`Prefix (ရှိပြီးသားစာလုံးကို ရှေ့မှစာလုံးထပ်ဖြည့်ခြင်း)` နှင့် :guilabel:`Suffix (ရှိပြီးသားစာလုံးကို နောက်မှစာလုံးထပ်ဖြည့်ခြင်း)` ထည့်ခြင်း
* Legend တွင် :guilabel:`အနည်းဆုံး` နှင့် :guilabel:`အများဆုံး` တန်ဖိုးများ ပြရန် ပြင်ဆင်ခြင်း
* :guilabel:`Number format (ကိန်းဂဏန်း format)` များ :ref:`Customize (ပြင်ဆင်ခြင်း) <number_formatting>` ပြုလုပ်ခြင်း
* Print layout legend (မြေပုံအပြင်အဆင်ထဲရှိ ရည်ညွှန်းချက်) တွင်အသုံးပြုရန် :guilabel:`Text format (စာသား format)` များ :ref:`Customize (ပြင်ဆင်ခြင်း) <text_format>` ပြုလုပ်ခြင်း

**Layout (မြေပုံအပြင်အဆင်)**

* Legend color ramp ၏ :guilabel:`Orientation (မျက်နှာမူရာ)` ကို ထိန်းချုပ်ခြင်း၊ **Vertical (ဒေါင်လိုက်)** သို့မဟုတ် **Horizontal (ရေပြင်ညီ)** အတိုင်းဖြစ်နိုင်ပါသည်။
* မျက်နှာမူရာပေါ်မူတည်ပြီး တန်ဖိုးများ၏ :guilabel:`Direction (လားရာ)` ကိုထိန်းချုပ်ပါသည်-

  * ဒေါင်လိုက်ဖြစ်လျှင် **အပေါ်ဘက်တွင် အများဆုံးတန်ဖိုး** သို့မဟုတ် **အပေါ်ဘက်တွင် အနည်းဆုံးတန်ဖိုး** ကို ပြသနိုင်ပါသည်။
  * ရေပြင်ညီဖြစ်လျှင် **ညာဘက်တွင် အများဆုံးတန်ဖိုး** သို့မဟုတ် **ညာဘက်တွင် အနည်းဆုံးတန်ဖိုး** ကို ပြသနိုင်ပါသည်။


Layer rendering (Layer ကို ပုံဖော်ပြသခြင်း)
--------------------------------------------

Raster file တစ်ခုလုံးစာအတွက် အထူးပုံဖော်ပြသပြင်ဆင်ခြင်း အထူးပြုလုပ်ချက်များ (special rendering effects) ကိုရရှိနိုင်ရန် Layer band များကို အသုံးပြုလိုက်သည့် symbology အမျိုးအစားပေါ်တွင်လုပ်ဆောင်နိုင်ပါသည်-

* Blending modes (ပေါင်းစပ်နည်းလမ်းများ) ထဲရှိ တစ်မျိုးမျိုးကို အသုံးပြုပါ (:ref:`blend-modes` တွင်ကြည့်ပါ)။
* အရောင်များ၏ :guilabel:`Brightness (အလင်းအမှောင်)` ၊ :guilabel:`Saturation (အရောင်တောက်ပမှုပမာဏ)` ၊ :guilabel:`Gamma (အလင်းတန်ဖိုး)` နှင့် :guilabel:`Contrast (အရောင်ကွဲပြားထင်ရှားမှု)` ကို စိတ်ကြိုက်ပြင်ဆင်ပါ။
* |checkbox|:guilabel:`Invert colors (ပြောင်းပြန်အရောင်များ)` ကို အမှန်ခြစ်ခြင်းဖြင့် layer ကို ဆန့်ကျင်ဘက်အရောင်များဖြင့် rendering လုပ်ဆောင်ပါမည်။ ဥပမာ - အကျုံးမဝင်သည့် OpenStreetMap tile များကို အနက်ရောင် (dark mode) အဖြစ်ပြောင်းလဲခြင်းတွင်အသုံးဝင်ပါသည်။
* :guilabel:`Grayscale (မီးခိုးရောင် )` option သို့ 'By lightness' ၊ 'By luminosity' သို့မဟုတ် 'By average' တစ်နည်းနည်းကို အသုံးပြု၍ ပြောင်းပါ။
* :guilabel:`Colorize (အ‌ရောင်ထည့်ခြင်း)` ပြုလုပ်ပါ၊ ထို့နောက် အရောင်ဇယားထဲရှိ :guilabel:`Hue (အရောင်အဆင်း)` ၏ :guilabel:`Strength (ပြင်းအား)` ကို ချိန်ညှိပါ။

Layer rendering တွင် ပြုလုပ်ခဲ့သည့် အပြောင်းအလဲများအားလုံးကို ဖယ်ရှားရန် :guilabel:`Reset` ကို နှိပ်ပါ။

.. _figure_raster_resampling:

.. figure:: img/rasterRenderAndResampling.png
   :align: center

   Raster သင်္ကေတဆိုင်ရာ - Layer ပုံဖော်ပြသခြင်းနှင့် and Resampling setting များ


Resampling (ဓာတ်ပုံ၏ pixel အရွယ်အစားကို ပြင်ဆင်ပြီး resolution ပြောင်းလဲခြင်း)
-------------------------------------------------------------------------------

ဓာတ်ပုံကို ချဲ့ကြည့်၊ ချုံကြည့်သည့်အခါမျိုးတွင် :guilabel:`Resampling` သည် သက်ရောက်မှုများ ရှိပါသည်။ Resampling နည်းလမ်းများသည် မြေပုံရဲ့အသွင်အပြင်ကို အကောင်းဆုံးဖြစ်အောင် ပြင်ဆင်ပေးနိုင်ပါသည်။ 
၎င်းနည်းလမ်းများသည် ဘူမိဗေဒဆိုင်ရာ ပြောင်းလဲမှုများ (Geomeric transformation) မှတစ်ဆင့် gray value matrix အသစ်တစ်ခုကို တွက်ချက်ပေးပါသည်။ 

'Nearest neighbour' နည်းလမ်းကိုအသုံးပြုလျှင် ချဲ့ကြည့်သည့်အခါ မြေပုံသည် pixelated structure ကို ရရှိမှာဖြစ်ပါသည်။ 
ထင်ရှားပြတ်သားနေသည့် အစွန်းများကို ဝါးတားတားဖြစ်သွားအောင် ပြုလုပ်သည့် 'Bilinear' သို့မဟုတ် 'Cubic' နည်းလမ်းကို အသုံးပြုပြီး ဤအသွင်အပြင်ကို ကောင်းမွန်စေနိုင်ပါသည်။ 
ထိုသို့ပြင်လိုက်လျှင် ဓာတ်ပုံသည် ကြည့်ရတာပိုအဆင်ပြေချောမွေ့သွားပါသည်။ ဥပမာ - Digital topographic raster မြေပုံများတွင် ဤနည်းလမ်းကို အသုံးပြုနိုင်ပါသည်။

|checkbox| :guilabel:`Early resampling` ကို အမှန်ခြစ်ထားလျှင် မူရင်းဓာတ်ပုံ၏ resolution ကို သိသောအဆင့်တွင် raster randering တွက်ချက်လို့ရပါသည်။ 
ထို့အပြင် QGIS custom styling (စိတ်ကြိုက် style များပြင်ဆင်ခြင်း) ဖြင့် ပိုကောင်းသည့် zoom ချဲ့ကြည့်ခြင်း မျိုးရရှိစေပါသည်။ 
:ref:`interpretation method (အဓိပ္ပါယ်ဖော်ခြင်းနည်းလမ်း) <interpretation>` ကို အသုံးပြုပြီး ထည့်သွင်းထားသည့် tile raster များအတွက် အမှန်တကယ် အဆင်ပြေစေပါသည်။


.. index:: Transparency
.. _raster_transparency:

Transparency Properties (ဖောက်ထွင်းမြင်ရမှုဆိုင်ရာ ဂုဏ်သတ္တိများ)
==================================================================

|transparency| Raster layer တစ်ခုအတွက် transparency level (ဖောက်ထွင်းမြင်ရမှုအဆင့်အတန်း) ကို သတ်မှတ်ရန် QGIS က လုပ်ဆောင်ပေးနိုင်ပါသည်။

ထပ်ထားသည့် layer များရှိလျှင် ယခုလက်ရှိအသုံးပြုနေသော အပေါ်ဆုံး raster layer ကိုဖောက်ထွင်းပြီး အောက်ရှိ layer ကို ဘယ်လောက်ပမာဏအထိ မြင်ရနိုင်မည်ကို သတ်မှတ်ရန်အတွက် 
:guilabel:`Global opacity` ကိုအသုံးပြုနိုင်ပါသည်။ Layer များထပ်ထားသည့်အခါ ဤနည်းလမ်းသည် အလွန်အသုံးဝင်ပါသည်။ 
(ဥပမာ - Shaded relief map (မြေမျက်နှာသွင်ပြင် အနိမ့်အမြင့်များပြသောမြေပုံ) တစ်ခုပေါ်တွင် classified (အတန်းအစားခွဲထားသော) raster map တစ်ခု ထပ်ထားသောအခါ) 
ဤသို့ လုပ်ဆောင်ခြင်းသည် မြေပုံကို ပိုမိုပြီး သုံးဘက်မြင် ဆန်ဆန်ဖြစ်စေပါသည်။ Raster ၏ အလင်းဖောက်ထွင်းနိုင်မှု (opacity) သည် data-defined (တန်ဖိုးဖြင့်သတ်မှတ်ခြင်း) ဖြစ်နိုင်ပြီး 
အခြား layer ၏ မြင်နိုင်မှု၊ အချိန်နှင့်ဆိုင်သော ပြောင်းလဲနိုင်သည့်အရာများ၊ atlas (မြေပုံပေါင်းချုပ်) တစ်ခု၏ မတူညီသောစာမျက်နှာများ ပေါ်မူတည်ပြီး ပြောင်းလဲနိုင်ပါသည်။

.. _figure_raster_transparency:

.. figure:: img/rasterTransparency.png
   :align: center

   Raster ဖောက်ထွင်းမြင်ရမှု

|checkbox| :guilabel:`No data value` ကို အမှန်ခြစ်ထားလျှင် မူရင်း no data value များ (သို့မဟုတ် သတ်မှတ်ထားသည်များ) ကို rendering တွင် ထည့်သွင်းမစဉ်းစားပါ။ ထို့အပြင် raster မှာ မမြင်ချင်သည့် တန်ဖိုး (ဥပမာ - ၂၅၅) ကို :guilabel:`Additional no data value` အတွင်း ထည့်ရိုက်ပြီး အရောင်ဖျောက်ထားပြီး ကြည့်လို့ရပါသည်။ 
No data value များအတွက် မူရင်းပြပေးသည့် အလင်းဖောက် (အရောင်ဖျောက်ကြည့်ခြင်း) အစား စိတ်ကြိုက်အရောင်တစ်ခု ထည့်သုံးလိုလျှင် :guilabel:`Display no data as` တွင် အရောင်ရွေးချယ်လို့ရပါသည်။

ဖောက်ထွင်းမြင်ရမှုကို စိတ်ကြိုက်ပြင်ဆင်နိုင်သည့် နည်းလမ်းကို :guilabel:`Custom transparency options (ဖောက်ထွင်းမြင်ရမှု စိတ်ကြိုက်ပြင်ဆင်ခြင်း)` အပိုင်းတွင်တွေ့နိုင်ပါသည်-

* Band တစ်ခုလုံးကို ဖောက်ထွင်းကြည့်ရှုနိုင်အောင် :guilabel:`Transparency band` ကို အသုံးပြုပါ။
* သက်ဆိုင်ရာ transparency level များအလိုက် ဖောက်ထွင်းမြင်ရမှုများ လုပ်ဆောင်မည့် pixel များရဲ့စာရင်းတစ်ခု ပြုလုပ်ပါ-

  #. |symbologyAdd| :sup:`Add values manually (တန်ဖိုးများကိုရိုက်ထည့်ခြင်း)` ခလုတ်ကိုနှိပ်ပါ။ Pixel စာရင်းတွင် row (အတန်း) အသစ်တစ်ခုပေါ်လာပါလိမ့်မည်။
  #. Pixel ရဲ့ **အနီ** ၊ **အစိမ်း** နှင့် **အပြာ** တန်ဖိုးများကို ရိုက်ထည့်ပါ၊ ထို့နောက် **Percent Transparent (ဖောက်ထွင်းမြင်ရမှု ရာခိုင်နှုန်း)** ကို ချိန်ညှိပါ။	 
  #. နောက်တစ်နည်းမှာ |contextHelp| :sup:`Add values from display` ခလုတ်ကိုနှိပ်ပြီး raster မှ pixel တန်ဖိုးများကို တိုက်ရိုက်ရယူနိုင်ပါသည်။ ထို့နောက် ဖောက်ထွင်းမြင်ရမှု တန်ဖိုးကို ရိုက်ထည့်ပါ။
  #. စိတ်ကြိုက်ဖောက်ထွင်းမြင်ရမှု အတွက် တခြားတန်ဖိုးများကို သုံးလိုလျှင် အထက်ပါအဆင့်များအတိုင်း ထပ်မံလုပ်ဆောင်ပါ။
  #. :guilabel:`Apply` ခလုတ်ကို နှိပ်ပြီး ရလာသော မြေပုံကို ကြည့်ရှုပါ။

  တွေ့ရသည့်အတိုင်း ဖောက်ထွင်းမြင်ရမှုကို စိတ်ကြိုက်ပြင်ဆင်ခြင်းသည် အလွန်လွယ်ကူပါသည်။ သို့သော် လုပ်ဆောင်ရသည့်အဆင့်များ များပြားနိုင်ပါသည်။ 
  ထို့ကြောင့် ထပ်ခါထပ်ခါ မလုပ်ရစေရန် လုပ်ထားပြီးသား transparency list ကိုသိမ်းဆည်းထားရန်အတွက် |fileSave| :sup:`Export to file` ခလုတ်ကိုအသုံးပြုနိုင်ပါသည်။ 
  |fileOpen| :sup:`Import from file` ခလုတ်သည် သိမ်းဆည်းထားသည့် transparency setting ကိုထည့်သွင်းနိုင်ပြီး လက်ရှိ raster layer တွင်အသုံးပြုနိုင်ပါသည်။

.. index:: Histogram
.. _raster_histogram:

Histogram Properties (ကြိမ်နှုန်းပြဂရပ်ဆိုင်ရာ ဂုဏ်သတ္တိများ)
==============================================================

|rasterHistogram| :guilabel:`Histogram` tab ကိုအသုံးပြုပြီး raster ထဲရှိ တန်ဖိုးများ၏ ပြန့်နှံ့မှုကို ကြည့်ရှုနိုင်ပါသည်။ :guilabel:`Compute Histogram` ခလုတ်ကိုနှိပ်ပြီး histogram ကိုဖန်တီးနိုင်ပါသည်။ 
|fileSave| ခလုတ်ကိုနှိပ်ပြီး histogram ကို ဓာတ်ပုံအဖြစ်သိမ်းဆည်းနိုင်ပါသည်။

Histogram ၏ အောက်ခြေတွင် drop-down menu မှတဆင့် raster band တစ်ခုကိုရွေးချယ်နိုင်ပြီး ၎င်းအတွက် အနည်းဆုံး/အများဆုံး style သတ်မှတ်နိုင်ပါသည်။ (:guilabel:`Set min/max style for`) 
|actionRun| :guilabel:`Prefs/Actions` drop-down menu သည် histogram ကို စိတ်ကြိုက်ပြင်ဆင်ရန် အဆင့်မြင့်ရွေးချယ်မှုများပိုမိုလုပ်ဆောင်နိုင်ပါသည်-

* :guilabel:`Visibility` ကိုအသုံးပြုပြီး band တစ်ခုချင်းဆီအတွက် histogram များကြည့်ရှုနိုင်ပါသည်။ |radioButtonOff| :guilabel:`Show selected band` ကို ရွေးချယ်ထားရန် လိုအပ်ပါလိမ့်မည်။
* :guilabel:`Min/max options` သည်  'Always show min/max markers' (အနည်းဆုံး/အများဆုံး အမှတ်သားများကိုပြသခြင်း) ၊ 'Zoom to min/max' (အနည်းဆုံး/အများဆုံး များကို zoom ဆွဲကြည့်ခြင်း) နှင့် 'Update style to min/max' (အနည်းဆုံး/အများဆုံး အတိုင်း style ကိုပြင်ဆင်ခြင်း) များကို လုပ်ဆောင်ပေးပါသည်။
* Band (များ) ၏ အနည်းဆုံး/အများဆုံး တန်ဖိုးများကို ပြောင်းလဲပြီးနောက် 'မူရင်းအတိုင်းပြန်ထားချင်သည့်အခါ' သို့မဟုတ် 'histogram ကို ပြန်တွက်ထုတ်ချင်သည့်အခါ' :guilabel:`Actions` ကို အသုံးပြုနိုင်ပါသည်။

.. _figure_raster_histogram:

.. figure:: img/rasterHistogram.png
   :align: center

   Raster Histogram (Raster ကြိမ်နှုန်းပြဂရပ်)


.. index:: Rendering
.. _raster_rendering:

Rendering Properties (ပုံဖော်ပြသခြင်းဆိုင်ရာ ဂုဏ်သတ္တိများ)
============================================================

|rendering| :guilabel:`Rendering` tab တွင် အောက်ပါတို့ကို လုပ်ဆောင်နိုင်ပါသည်-

* Layer အတွက် :guilabel:`Scale dependent visibility (စကေးပေါ်မူတည်ပြီး မြင်ရနိုင်စွမ်း)` ကိုသတ်မှတ်နိုင်ပါသည်။ :guilabel:`Maximum (inclusive) - အများဆုံး (ဤတန်ဖိုးအောက်ဆိုလျှင်မြင်ရခြင်း)` နှင့် :guilabel:` Minimum (exclusive) - အနည်းဆုံး (ဤတန်ဖိုးအောက်ဆိုလျှင်မမြင်ရခြင်း)` တို့ကိုသတ်မှတ်ပေးပြီး ဘယ်လောက်စကေးအတွင်းသာ layer များကို မြင်နိုင်ရမည်ဆိုသည်ကို သတ်မှတ်ပေးနိုင်ပါသည်။ 
  သတ်မှတ်ပေးထားသည့် အတိုင်းအတာအတွင်း မဝင်သည့်အခါ မြေပုံပေါ်တွင် ပေါ်လာမည်မဟုတ်ပါ။ |mapIdentification| :sup:`Set to current canvas scale` ခလုတ်ကို နှိပ်ပြီး ယခုလက်ရှိ map canvas စကေးကို အသုံးပြုနိုင်ပါသည်။
  ထပ်မံကြည့်ရှုလိုသည်များအတွက် :ref:`label_scaledepend` တွင်ကြည့်ရှုပါ။

  .. note::

   :guilabel:`Layers` panel ထဲရှိ layer တစ်ခုပေါ်တွင် right-click နှိပ်ပြီး ပေါ်လာသည့် menu တွင် :guilabel:`Set Layer Scale Visibility` ကိုရွေးချယ်ပြီး layer တစ်ခုဟာ မည်သည့်စကေးတွင် မြင်ရနိုင်မည်ဆိုသည်ကို သတ်မှတ်ပေးလို့ရနိုင်ပါသည်။


* :guilabel:`Refresh layer at interval (seconds)` (သတ်မှတ်ထားသည့် အချိန်စက္ကန့်အပိုင်းအခြား၌ layer refresh ပြုလုပ်ခြင်း) ကိုအသုံးပြုပြီး layer တစ်ခုချင်းအတွက် အချိန်ဘယ်လောက်အကြာတွင် အလိုလျှောက် refresh လုပ်ပေးမည်ဆိုသည်ကို သတ်မှတ်ပေးထားလို့ရပါသည်။ 
  Layer တစ်ခုထက်ပိုပြီး auto update interval သတ်မှတ်ချက်ပြုလုပ်ထားလျှင် ကြိမ်ဖန်များစွာ refresh ပြုလုပ်ခြင်းကို ရှောင်ရှားရန်အတွက် canvas update ပြုလုပ်ခြင်းကို ဆိုင်းငံ့ထားမည်ဖြစ်ပါသည်။

.. _figure_raster_rendering:

.. figure:: img/rasterRendering.png
   :align: center

   Raster Rendering ဆိုင်ရာ ဂုဏ်သတ္တိများ


.. index:: Temporal
.. _raster_temporal:

Temporal Properties (အချိန်နှင့်ပတ်သက်သော ဂုဏ်သတ္တိများ)
=========================================================

|temporal| :guilabel:`Temporal` tab ကိုအသုံးပြုပြီး layer ၏ rendering ကို အချိန်နှင့်အမျှ ထိန်းချုပ်ခြင်းများလုပ်ဆောင်နိုင်ပါသည်။ 
ထိုသို့သော dynamic rendering မျိုးကို map canvas ပေါ်တွင်ရရှိနိုင်စေရန် :ref:`temporal navigation <maptimecontrol>` ကိုလိုအပ်မည်ဖြစ်ပါသည်။

.. _figure_raster_temporal:

.. figure:: img/rasterTemporal.png
   :align: center

   Raster ၏ အချိန်နှင့်ပတ်သက်သော ဂုဏ်သတ္တိများ

|checkbox| :guilabel:`Dynamic Temporal Control` ကို အမှန်ခြစ်ထားလိုက်ပြီး အောက်ပါထဲမှမည်သည့်အရာဖြင့် layer redraw လုပ်သင့်သည်ကို သတ်မှတ်ပါ-

* :guilabel:`Automatic` (အလိုအလျောက်) - အချိန်နှင့်ပတ်သက်သော data များပါလျှင် rendering ကို အသုံးပြုနေသည့် data ကထိန်းချုပ်ပါသည်။ ဥပမာ - WMS-T layer များ သို့မဟုတ် PostGIS raster များအတွက် အသုံးဝင်ပါသည်။

  .. A bit more info on this automatic option would be necessary.
   I guess it has to do with wms-t that I don't use so precision welcome

* :guilabel:`Fixed time range` (သတ်မှတ်အချိန်အတွင်း) - Animation (လှုပ်ရှားပုံရိပ်) အချိန်သည် :guilabel:`Start date (စရက်)` နှင့် :guilabel:`End date (ဆုံးရက်)` အတွင်းရှိမှသာ raster layer ကို ပြသပေးပါသည်။
* :guilabel:`Redraw layer only` (layer ကိုသာ redraw လုပ်ခြင်း) - Animation frame အသစ်တစ်ခုစီတိုင်းမှာ layer ကို ပြန်ဆွဲပါသည်။ 
  Rendering setting များအတွက် time-based expression တန်ဖိုးများကို အသုံးပြုမှသာ ဤနည်းလမ်းဟာ အသုံးဝင်ပါသည်။ 
  (ဥပမာ - Raster layer တစ်ခုကို မှိန်သွားစေရန်အတွက် data-defined renderer opacity)

.. index:: Elevation, Terrain
.. _raster_elevation:

Elevation Properties (မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့်ဆိုင်ရာ ဂုဏ်သတ္တိများ)
===========================================================================

|elevationscale| :guilabel:`Elevation` tab ကိုအသုံးပြုပြီး :ref:`3D map view (သုံးဘက်မြင်မြေပုံမြင်ကွင်း) <label_3dmapview>` တစ်ခုထဲတွင် layer ၏ အနိမ့်အမြင့် property များနှင့် :ref:`profile tool charts <label_elevation_profile_view>` ထဲရှိ ပုံပန်းသွင်ပြင်ကို ထိန်းချုပ်နိုင်ပါသည်။ 
အောက်ပါတို့ကို သတ်မှတ်ပေးနိုင်ပါသည်-

.. _figure_raster_elevation:

.. figure:: img/rasterElevation.png
   :align: center

   Raster ၏ မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့်ဆိုင်ရာ ဂုဏ်သတ္တိများ

* |unchecked| :guilabel:`Represents Elevation Surface` တွင် Raster layer သည် မျက်နှာပြင်အမြင့် (ဥပမာ - DEM) တစ်ခုကို ကိုယ်စားပြုသလား နှင့် pixel တန်ဖိုးများကို မြေမျက်နှာပြင်အနိမ့်အမြင့် အဖြစ် ဘာသာပြန်သင့်သလား ဆိုသည်ကို လုပ်ဆောင်နိုင်ပါသည်။ Raster တစ်ခုကို :ref:`elevation profile view <label_elevation_profile_view>` ဖြင့်ကြည့်လိုလျှင် ဤ option ကို အမှန်ခြစ်ပါ။ :guilabel:`Band` တန်ဖိုးကိုလည်းဖြည့်ထားရန်လိုအပ်ပါသည်။ ထို့နောက် :guilabel:`Scale` factor တစ်ခုနှင့် :guilabel:`Offset` တစ်ခုထည့်သွင်းအသုံးပြုနိုင်ပါသည်။
* :guilabel:`Profile Chart Appearance` သည် profile chart တစ်ခုရေးဆွဲသည့်အခါ raster elevation ၏ rendering :guilabel:`Style` ကို ထိန်းချုပ်ပေးပါသည်။ အောက်ပါအတိုင်းသတ်မှတ်နိုင်ပါသည်-

  * :ref:`line style <vector_line_symbols>` တစ်ခုအသုံးပြုထားသည့် profile :guilabel:`Line` တစ်ခု
  * :guilabel:`Fill below` လုပ်ထားသည့် မျက်နှာပြင်တစ်ခုနှင့် သက်ဆိုင်ရာ :ref:`fill style <vector_fill_symbols>` တစ်ခုတို့ဖြစ်ပါသည်။
  
.. index:: Pyramids
.. _raster_pyramids:

Pyramids Properties (ပိရမစ် ဂုဏ်သတ္တိများ)
===========================================

QGIS တွင် ကြည်လင်ပြတ်သားသည့် (high resolution) ဓာတ်ပုံများကို ရွှေ့ပြီးကြည့်လျှင် နှေးကွေးနိုင်ပါသည်။ 
ထို့ကြောင့် ကြည်လင်ပြတ်သားမှု နိမ့်သော data မိတ္တူများ (ပိရမစ်များ) ဖန်တီးပြီး အသုံးပြုခြင်းသည် လုပ်ဆောင်မှုသိသိသာသာမြန်ဆန်လာတာကို တွေ့ရပါသည်။ 
အဘယ်ကြောင့်ဆိုသော် ကိုယ်အသုံးပြုနေသည့် zoom level ပေါ်မူတည်ပြီး အသင့်တော်ဆုံး ကြည်လင်ပြတ်သားမှုကို ရွေးချယ်အသုံးပြုခြင်းကြောင့်ဖြစ်ပါသည်။ 
(ဆိုလိုသည်မှာ ဧရိယာအကျယ်ကြီးကို ခြုံငုံကြည့်လိုလျှင် resolution အရမ်းအကောင်းကြီးမလိုသောကြောင့် resolution ချပြီးကြည့်လိုက်သည့်အခါ ပုံရဲ့ file အရွယ်အစားသေးသွားတာကြောင့် နေရာရွှေ့ရတာ ပိုမြန်ဆန်သွားခြင်း ဖြစ်ပါသည်။)

ပိရမစ် ဖန်တီးရန်အတွက် မူရင်း data သိမ်းဆည်းထားသည့်နေရာတွင် data ကို ပြင်ဆင်ပိုင်ခွင့် (‌ရေးနိုင်တဲ့ အခွင့်အရေး) ရှိရန် လိုအပ်ပါသည်။

:guilabel:`Resolutions` စာရင်းမှ ဖန်တီးလိုသည့် ပိရမစ် level အတွက် resolution ကို click လုပ်ပြီး ရွေးချယ်ပါ။

:guilabel:`Overview format` drop-down menu မှတဆင့် **Internal (လုပ်ခွင့်ပေးမှသာ)** ကိုရွေးထားလျှင် QGIS သည် ပိရမစ်ကို မူရင်းဖိုင်ထဲတွင်ထည့်ပြီး ဖန်တီးပေးပါသည်။

.. note::

   ပိရမစ်များ ဖန်တီးလိုက်ခြင်းသည် မူရင်း data ကိုအမြဲတမ်းပြောင်းလဲလိုက်ခြင်းဖြစ်ပြီး တစ်ခါဖန်တီးလိုက်သည်နှင့် ပြန်ဖျက်လို့ မရနိုင်တော့ပါ။ 
   အကယ်၍ မူရင်း data ကိုမပျက်စီးစေဘဲ သိမ်းဆည်းထားချင်လျှင် ပိရမစ် မဖန်တီးခင် မူရင်း data ကို မိတ္တူပွားထားပါ။

**External** နှင့် **External (Erdas Imagine)** ကို ရွေးထားလျှင် မူရင်း raster file နှင့်နာမည်တူပြီး :file:`.ovr` extension ဖြင့် file အသစ်တစ်ခုကို မူရင်း folder မှာ ဖန်တီးပေးပါသည်။

ပိရမစ် တွက်ထုတ်ခြင်းအတွက် :guilabel:`Resampling methods` အမျိုးမျိုးကို အသုံးပြုလို့ရပါသည်-

* Nearest Neighbour
* Average
* Gauss
* Cubic
* Cubic Spline
* Laczos
* Mode
* None

နောက်ဆုံးအနေနဲ့ ပိရမစ် စပြီးဖန်တီးရန် :guilabel:`Build Pyramids` ကို နှိပ်ပါ။

.. _figure_raster_pyramids:

.. figure:: img/rasterPyramids.png
   :align: center

   Raster ပိရမစ်များ ဖန်တီးခြင်း


.. index:: Metadata, Metadata editor, Keyword
.. _raster_metadata:

Metadata Properties (Metadata ဂုဏ်သတ္တိများ)
=============================================

|editMetadata| :guilabel:`Metadata` tab တွင် ဖန်တီးလိုက်သည့် layer နှင့်ပတ်သက်သော metadata (ဥပမာ - projection၊ ဖန်တီးသူ၊ ဖန်တီးခဲ့သောရက်စွဲ) တို့ကို ဖန်တီးနိုင်သလို တည်းဖြတ်ပြင်ဆင်လို့ ရပါသည်။ 
ပိုမိုသိရှိလိုပါက :ref:`metadatamenu` တွင် ဖတ်ရှုနိုင်ပါသည်။

.. _figure_raster_metadata:

.. figure:: img/rasterMetadata.png
   :align: center

   Raster Metadata


.. index:: Legend, Embedded widget
.. _raster_legend:

Legend Properties (ရည်ညွှန်းချက်ဆိုင်ရာ ဂုဏ်သတ္တိများ)
=======================================================

|legend| :guilabel:`Legend` tab တွင် :ref:`Layers panel <label_legend>` နှင့် :ref:`print layout legend <layout_legend_item>` တို့အတွက် ပိုပြီးအဆင့်မြင့်သည့် setting များပါဝင်ပါသည်။ ၎င်းတို့မှာ - 

* Layer တွင်အသုံးပြုလိုက်သော symbology ပေါ်မူတည်ပြီး legend ထဲတွင် ထည့်သွင်းစရာများကောင်းများနေနိုင်ပါသည်။ ပေါ်နေသည့်အရာအားလုံးသည် အသုံးဝင်ချင်မှ ဝင်ပါလိမ့်မည်။ 
  :guilabel:`Legend placeholder image` သည် အစားထိုးရန်အတွက် :ref:`select an image (ဓာတ်ပုံတစ်ခုရွေးချယ်ခြင်း)
  <embedded_file_selector>` ပြုလုပ်နိုင်ပြီး :guilabel:`Layers` panel နှင့် မြေပုံထုတ်ဖို့ပြင်ဆင်ထားသည့်နေရာရှိ legend တွင်လည်း ဖော်ပြပေးနိုင်ပါသည်။
* |legend| :guilabel:`Embedded widgets in Legend` သည် Layers panel ရှိ layer တွေအများကြီးထဲတွင် embed (ထည့်မြှုပ်ထား) လုပ်ထားနိုင်သည့် စာရင်းတစ်ခုကို ဖန်တီးပေးပါသည်။ 
  Layer များတွင်မကြာခဏ လုပ်လေ့ရှိသော လုပ်ဆောင်ချက်များ (ဖောက်ထွင်းမြင်ရမှု၊ စစ်ထုတ်ခြင်း၊ ရွေးထုတ်ခြင်း၊ style နှင့် တခြားအရာများ) ကို လွယ်လွယ်ကူကူ မြန်မြန်ဆန်ဆန် လုပ်ဆောင်နိုင်ရန်အတွက် ဖြစ်ပါသည်။ 

  ပုံမှန်အားဖြင့် QGIS တွင် ဖောက်ထွင်းမြင်ရမှု (transparency) widget ပါဝင်ပေမယ့် layer များတွင် အသုံးပြုလိုသော လုပ်ဆောင်ချက်များအတွက် ကိုယ်ပိုင် widget များဖြင့် အသုံးပြုနိုင်ရန် plugin များ ထပ်ဖြည့်သွင်းလို့ရပါသည်။

.. _figure_raster_legend:

.. figure:: img/rasterLegend.png
   :align: center

   Raster ရည်ညွှန်းချက်


.. index:: QGIS Server
.. _raster_server:

QGIS Server Properties (QGIS Server ဆိုင်ရာ ဂုဏ်သတ္တိများ)
===========================================================

|overlay| :guilabel:`QGIS Server` tab တွင် :ref:`QGIS Server <QGIS-Server-manual>` ပေါ်တွင် အများပြည်သူအသုံးပြုနိုင်ရန် ဖြန့်ဝေပေးထားသည့် data များ၏ setting ကို ပြင်ဆင်နိုင်ပါသည်။ ပြင်ဆင်မှုများနှင့် ပတ်သက်သည်များမှာ-

* :guilabel:`Description` သည် :guilabel:`Short name (အတိုကောက်နာမည်)` ၊ :guilabel:`Title (ခေါင်းစဉ်)` ၊ :guilabel:`Summary (အနှစ်ချုပ်)` ၊ :guilabel:`List of Keywords (Keyword များစာရင်း)` နှင့် ``text/html``၊ ``text/plain`` သို့မဟုတ် ``application/pdf`` :guilabel:`Type (အမျိုးအစား)` များဖြစ်နိုင်သည့် :guilabel:`Data URL (Data ရဲ့ မူရင်းသိမ်းဆည်းထားသောနေရာ)` တို့လို အချက်အလက်များကို ဖော်ပြပေးပါသည်။
* :guilabel:`Attribution` တွင် data ဖန်တီးသူကို ဖော်ပြရန် :guilabel:`Title` နှင့် :guilabel:`Data URL` များပါဝင်ပါသည်။
* :guilabel:`Metadata URL` တွင် ``FGDC`` သို့မဟုတ် ``TC211`` :guilabel:`Type` ဖြစ်နိုင်သော metadata များအတွက်  ``text/plain`` သို့မဟုတ် ``text/xml`` :guilabel:`Format` ဖြင့် :guilabel:`URL` စာရင်းတစ်ခု ပါဝင်ပါသည်။
* :guilabel:`Legend URL` တွင် ``image/png`` သို့မဟုတ် ``image/jpeg`` :guilabel:`Format` ဖြင့် legend အတွက် :guilabel:`URL` တစ်ခု ပါဝင်ပါသည်။

.. note::
   Server တွင် ဖြန့်ဝေလိုသည့် raster layer သည် web service တစ်ခုမှ ပံ့ပိုးပြီးသားဖြစ်နေလျှင် setting များအတွက် တခြား :ref:`properties <wms_server_properties>` များကို လုပ်ဆောင်နိုင်ပါသည်။

.. _figure_raster_server:

.. figure:: img/rasterServer.png
   :align: center

   Raster Properties ထဲရှိ QGIS Server


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |actionRun| image:: /static/common/mAction.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |contextHelp| image:: /static/common/mActionContextHelp.png
   :width: 1.5em
.. |editMetadata| image:: /static/common/editmetadata.png
   :width: 1.2em
.. |elevationscale| image:: /static/common/elevationscale.png
   :width: 1.5em
.. |fileOpen| image:: /static/common/mActionFileOpen.png
   :width: 1.5em
.. |fileSave| image:: /static/common/mActionFileSave.png
   :width: 1.5em
.. |fileSaveAs| image:: /static/common/mActionFileSaveAs.png
   :width: 1.5em
.. |legend| image:: /static/common/legend.png
   :width: 1.2em
.. |mapIdentification| image:: /static/common/mActionMapIdentification.png
   :width: 1.5em
.. |metadata| image:: /static/common/metadata.png
   :width: 1.5em
.. |overlay| image:: /static/common/overlay.png
   :width: 1.5em
.. |pyramids| image:: /static/common/pyramids.png
   :width: 1.5em
.. |radioButtonOff| image:: /static/common/radiobuttonoff.png
   :width: 1.5em
.. |radioButtonOn| image:: /static/common/radiobuttonon.png
   :width: 1.5em
.. |rasterHistogram| image:: /static/common/rasterHistogram.png
   :width: 1.5em
.. |rendering| image:: /static/common/rendering.png
   :width: 1.5em
.. |setProjection| image:: /static/common/mActionSetProjection.png
   :width: 1.5em
.. |symbology| image:: /static/common/symbology.png
   :width: 2em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
.. |symbologyRemove| image:: /static/common/symbologyRemove.png
   :width: 1.5em
.. |system| image:: /static/common/system.png
   :width: 1.5em
.. |temporal| image:: /static/common/temporal.png
   :width: 1.5em
.. |transparency| image:: /static/common/transparency.png
   :width: 1.5em
.. |unchecked| image:: /static/common/unchecked.png
   :width: 1.3em
