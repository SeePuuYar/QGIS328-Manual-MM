.. _`label_projections`:

****************************************************************
Working with Projections (အရိပ်ချခြင်းများဖြင့် အလုပ်လုပ်ခြင်း)
****************************************************************

.. only:: html

   .. contents::
      :local:

.. index:: Projections, CRS (Coordinate Reference System)

Coordinate Reference System (ကိုဩဒိနိတ်အညွှန်းပြစနစ်) သို့မဟုတ် CRS သည် ကမ္ဘာ့မြေမျက်နှာပြင်ပေါ်ရှိ တည်နေရာကို Coordinate (ကိုဩဒိနိတ်) ကိန်းဂဏန်းများဖြင့် ဆက်စပ်ဖော်ပြထားသော နည်းလမ်းတစ်ခုဖြစ်သည်။ QGIS သည် ခန့်မှန်းခြေအားဖြင့် စံ CRS စနစ်ပေါင်း 7,000 ကို ပံ့ပိုးပေးပြီး၊ မတူညီသည့်အသုံးပြုမှုများ၊ အားသာချက်များနှင့် အားနည်းချက်များလည်း ရှိကြပါသည်။ ဒေတာများနှင့် QGIS project များအတွက် သင့်လျော်သော reference system အား ရွေးချယ်ခြင်းသည် ရှုပ်ထွေးသည့် လုပ်ငန်းဆောင်တာတစ်ခု ဖြစ်နိုင်သည်။ သို့သော် ကံကောင်းစွာ QGIS သည် ထိုရွေးချယ်မှုအား လုပ်ဆောင်ရန် ကူညီဖြေရှင်းပေးပြီး၊ မတူညီသည့် CRS များနှင့် အလုပ်လုပ်ခြင်းကို ဖြစ်နိုင်သမျှ တိကျမှုရှင်းလင်းမှုနှင့် နားလည်မှုများကို ပေးနိုင်ပါသည်။ 

.. index:: EPSG (European Petroleum Search Group), IGNF (Institut Geographique National de France)

Overview of Projection Support (Projection ၏ ပံ့ပိုးမှုများအား ခြုံငုံသုံးသပ်ခြင်း)
====================================================================================

QGIS သည် CRS လို့ခေါ်သည့် စနစ်ပေါင်း 7,000 နီးပါးအား ပံ့ပိုးပေးပါသည်။ ယင်း standard CRS များကို European Petroleum Search Group (EPSG)နှင့်  
Institut Geographique National de France (IGNF) တို့က သတ်မှတ်ထားသည့် စံနှုန်းသတ်မှတ်ချက်များပေါ်မူတည်၍ အခြေခံသတ်မှတ်ထားသည်။
အဆိုပါ စနစ်များအား QGIS ရှိ "Proj" projection library ထဲတွင် ရယူနိုင်ပါသည်။ ယေဘုယျအားဖြင့် အဆိုပါ standard projection စနစ်များကို 
တရားဝင်ဖန်တီးခွင့်အရ သတ်မှတ်ထားပြီး၊ code များဖြင့် ပေါင်းစပ်ထားသည်။ ယင်းတွင် တရားဝင်ဖန်တီးခွင့်ဆိုသည်မှာ "IGNF" သို့မဟုတ် "EPSG"  လို့ခေါ်သည့် 
အဖွဲ့အစည်း၏ အမည်ဖြစ်ပါသည်။ Code ဆိုသည်မှာ သီးသန့် CRS တစ်ခုစီနှင့် သက်ဆိုင်သည့် ကိန်းဂဏန်းဖြစ်သည်။ 
ဉပမာအားဖြင့် - အသုံးများသော WGS 84 latitude/longitude CRS အား code ``EPSG:4326`` ဖြင့် သတ်မှတ်ထားရှိပြီး၊
web mapping standard CRS code ကို ``EPSG:3857`` ဖြင့် သတ်မှတ်ထားသည်။

အသုံးပြုသူများ ဖန်တီးထားသော CRS များကို အသုံးပြုသူ၏ CRS database တွင် သိမ်းဆည်းထားပါသည်။ 
ကိုယ်တိုင်စိတ်ကြိုက် ဖန်တီးထားသော coordinate reference system များအား စီမံလုပ်ဆောင်ခြင်းဆိုင်ရာ အချက်အလက်များအတွက် 
:ref:`sec_custom_projections` အပိုင်းတွင် ကြည့်ရှု့နိုင်ပါသည်။ 

.. _layer_crs:

Layer Coordinate Reference Systems (Layer ၏ Coordinate Reference System များ)
==============================================================================

Data များကို မိမိသတ်မှတ်လိုသည့် CRS စနစ်တစ်ခုသို့ မှန်ကန်တိကျစွာ project လုပ်လိုလျှင် data တွင် coordinate reference system နှင့် ပတ်သက်သော ကိန်းဂဏန်းအချက်အလက်များ ပါဝင်ရမည်ဖြစ်သည်။ သို့မဟုတ် layer တွင် မှန်ကန်သော CRS ကိုသတ်မှတ်ပေးရန် လိုအပ်ပါသည်။ PostGIS layer များအတွက် ၎င်း PostGIS layer များကို ရေးဆွဲသည့်အခါ QGIS သည် တိကျစွာ သတ်မှတ်ထားသော spatial reference identifier ကိန်းဂဏန်းတန်ဖိုးများကို အသုံးပြုသည်။ GDAL မှ ထောက်ပံ့ပေးထားသော  data များအတွက် QGIS သည် CRS သီးခြားသတ်မှတ်ခြင်း၏ အသိအမှတ်ပြုထားသောနည်းလမ်းများ တည်ရှိမှုပေါ်တွင် မူတည်သည်။ ဥပမာအားဖြင့် - Shapefile format အတွက် layer ၏ CRS ကို ကိုယ်စားပြုသည့် (ESRI အသိအမှတ်ပြုထားသော စာသား) ESRI Well-Known Text(:index:`WKT`) ပါဝင်သော ဖိုင်တစ်ခု ပါဝင်ပါသည်။ အဆိုပါ projection file သည် :file:`.shp` file နှင့် :file:`.prj` extension များနှင့် နာမည်တူညီပါသည်။ ဉပမာအားဖြင့် - :file:`alaska.shp` တွင် :file:`alaska.prj` ဟု အမည်ရသော သက်ဆိုင်ရာ projection file ပါရှိပါသည်။ 

QGIS အတွင်းသို့ layer တစ်ခုအား ထည့်သွင်းလိုက်သည့်အခါတိုင်း  QGIS သည် အလိုအလျောက် အဆိုပါ layer အတွက် မှန်ကန်သော  
CRS စနစ်ကို ပြောင်းလဲပေးသည်။ အချို့ကိစ္စများတွင် လုပ်ဆောင်မပေးနိုင်ပါ၊ ဉပမာ - layer သည် CRS အချက်အလက်များပါဝင်မှုမရှိသည့်အခါ။ Layer တစ်ခု အတွက် မှန်ကန်သည့် CRS စနစ်ကို အလိုအလျောက်မဆုံးဖြတ်နိုင်သည့်အခါ QGIS တွင် ပြင်ဆင်သတ်မှတ်နိုင်သည်-

#. :menuselection:`Settings -->` |options| :menuselection:`Options... --> CRS` ကိုဖွင့်ပါ-

   .. _figure_projection_options:

   .. figure:: ../introduction/img/options_crs.png
      :align: center

      QGIS options dialog အတွင်းရှိ CRS tab

#. :guilabel:`CRS for layers` group အောက်တွင် :guilabel:`when a new layer is created, or when a layer is loaded that has no CRS` လုပ်ဆောင်ရန်အတွက် အောက်ဖော်ပြပါများထဲမှ တစ်ခုကို ရွေးချယ်ပါ-

   * |radioButtonOn| :guilabel:`Leave as unknown CRS (take no action)` -
     Layer တစ်ခုအား CRS စနစ် မပါပဲ ထည့်သွင်းသည့်အခါ CRS စနစ်တစ်ခုကို ချက်ချင်းရွေးချယ်ရန် မလိုအပ်ပါ။ နောက်မှ CRS စနစ်အား  ရွေးချယ်သတ်မှတ်နိုင်ပါသည်။ တစ်ကြိမ်တည်းနှင့် layer များစွာ ထည့်သွင်းသည့်အခါ အဆင်ပြေပါသည်။ အဆိုပါ layer များကို :guilabel:`Layers` panel ထဲရှိ layer ၏ ဘေးတွင် |indicatorNoCRS| icon ကိုကြည့်ခြင်းအားဖြင့် သိနိုင်မည်ဖြစ်ပါသည်။ ထို layer များအားလုံးသည် georeference မပါရှိပဲ ရှိနေမည်ဖြစ်သည်။ Layer တွင်ပါရှိသော coordinate များကို ကမ္ဘာပေါ် ရှိတည်နေရာနှင့် မသက်ဆိုင်သည့်၊ ကိန်းဂဏန်းသက်သက်အဖြစ်သာ မှတ်ယူမည်ဖြစ်သည်။ ဆိုလိုသည်မှာ :ref:`project ကို CRS မသတ်မှတ်ပဲ <project_crs>` ထားရှိသည့် layer များဖြစ်သွားသည့် အတိုင်းဖြစ်မည်ဖြစ်သည်။ 
   * |radioButtonOff| :guilabel:`Prompt for CRS` - သည် CRS ကို ရွေးချယ်ရန်ဖော်ပြပေးပါမည်။ ရွေးချယ်မှုမှားလျှင် ကမ္ဘာမြေပြင်ရှိ တည်နေရာအလွဲကို ရွေးချယ်သွားလိမ့်မည်ဖြစ်သဖြင့် မှန်ကန်စွာရွေးချယ်မိစေရန် အလွန်အရေးကြီးပါသည်။ တခါတရံ metadata နှင့်အတူ ပါလာသည့်အချက်အလက်များသည် layer အား မှန်ကန်သော CRS ကို ဖော်ပြပေးပါသည်။ သို့သော် အချို့အခြေအနေများတွင်မှု မှန်ကန်သော CRS ကို ဆုံးဖြတ်ရန် မူရင်း data ဖန်တီးသူအား ဆက်သွယ်မေးမြန်းရန် လိုအပ်ပါသည်။
   * |radioButtonOff| :guilabel:`Use project CRS` (Project ၏ CRS အတိုင်းအသုံးပြုခြင်း)
   * |radioButtonOff| :guilabel:`Use default layer CRS` (Default layer ၏ CRS အတိုင်းအသုံးပြုခြင်း)၊ အပေါ်တွင်ရှိသည့် :guilabel:`Default CRS for layers` combobox တွင်သတ်မှတ်ထားသည့်အတိုင်းအသုံးပြုပါသည်။ 

.. tip::

   လုပ်ဆောင်မှုများတွင် မှားယွင်းသော CRS စနစ် ရှိသော သို့မဟုတ် မည်သည့် CRS စနစ်မျှ မပါရှိသော layer မျိုးစုံအား တူညီသော CRS စနစ်အဖြစ် သတ်မှတ်ရာတွင်-

   #. :guilabel:`Layers` panel ထဲရှိ layer များအား ရွေးပါ။
   #. :kbd:`Ctrl+Shift+C` ကိုနှိပ်ပါ။ ရွေးထားသော layer များထဲမှ တစ်ခုပေါ်တွင် right-click နှိပ်နိုင်သည် သို့မဟုတ် :menuselection:`Layer --> Set CRS of layer(s)` ကို ရွေးချယ်နိုင်ပါသည်။
   #. အသုံးပြုရန် CRS အမှန်အား ရှာဖွေရွေးချယ်ပါ။
   #. ထို့နောက် :guilabel:`OK` ကိုနှိပ်ပါ။  layers properties dialog ၏ :guilabel:`Source` tab ထဲတွင် ရွေးချယ်ထားသော CRS မှန် မမှန် အတည်ပြုနိုင်သည်။ 

   မှတ်သားထားရမည်မှာ - Setting ထဲရှိ CRS စနစ်ကို ပြောင်းထားခြင်းသည် တည်ရှိနေသော data source အား ပြောင်းလဲမသွားစေနိုင်ပါ၊ လက်ရှိလုပ်ဆောင်နေသော QGIS project ရှိ layer မှ မူရင်း ကိုဩဒိနိတ်များကို QGIS က မည်သို့အဓိပ္ပါယ်ဖော်မည်ဆိုသည့် အရာကိုပဲ ပြောင်းလဲပေးခြင်းဖြစ်ပါသည်။ 


.. index:: CRS, Proj, On-the-fly transformation
   single: CRS; Default CRS
.. _project_crs:

Project Coordinate Reference Systems (Project ၏ Coordinate Reference System များ)
==================================================================================

QGIS ရှိ  project တိုင်းတွင် သက်ဆိုင်ရာ Coordinate Reference System စနစ်တစ်ခု ရှိပါသည်။ QGIS map canvas အတွင်း ၎င်း၏မူရင်း ကိုဩဒိနိတ်များမှ မြေပုံအပြန့်အနေအထားသို့ render လုပ်ရန် data များကို မည်ကဲ့သို့ project (ပုံရိပ်ချ) လုပ်မည်ဆိုသည်ကို project CRS က ဆုံးဖြတ်ပေးသည်။ 

QGIS သည် raster data နှင့် vector data နှစ်မျိုးလုံးအတွက် "on the fly" CRS transformation (လုပ်ဆောင်နေစဉ် CRS ပြောင်းလဲခြင်း) ကို ထောက်ပံ့ပေးသည်။
ဆိုလိုသည်မှာ လုပ်ဆောင်နေသော project ထဲရှိ သီးခြား map layer များ၏ CRS အခြေအနေများကို ထည့်သွင်းမစဉ်းစားဘဲ၊ လုပ်ဆောင်နေသော project
အတွက် အသုံးများသည့် CRS စနစ်အား အလိုအလျောက်ပြောင်းပေးပါသည်။ နောက်ကွယ်တွင် layer များအား တစ်ခုနှင့်တစ်ခု တိကျသော တည်နေရာများ ရရှိစေရန်
QGIS သည် project အတွင်း ရှိသော layer များအားလုံးကို project ၏ CRS အဖြစ်သို့ ပြောင်းပေးပါသည်။ 
 
QGIS project များအတွက် သင့်လျော်သော CRS စနစ်ရွေးချယ်မှုတစ်ခုကို ပြုလုပ်ရန် အရေးကြီးပါသည်။ 
CRS စနစ်အား မမှန်မကန်ရွေးချယ်ထားမှုသည် မြေပုံများအား တွန့်လိမ်စေသည့်အပြင် ကမ္ဘာ့မြေပြင်ရှိ အရာဝတ္ထုများ၏ တည်နေရာများနှင့် အရွယ်အစားများကို ဖော်ပြမှုတွင် လက်ရှိမြေမျက်နှာပြင်နှင့်ဆက်စပ်သောတိကျမှုကို အားနည်းစေသည်။ ပုံမှန်အားဖြင့် ပိုမိုသေးငယ်သော တည်နေရာများတွင် ပြုလုပ်ဆောင်ရွက်မည်ဆိုလျှင် အုပ်ချုပ်မှုနယ်နိမိတ်ဧရိယာ သို့မဟုတ် သီးခြားနိုင်ငံတစ်ခု အတွင်း အသုံးပြုသော စံ CRS များ ရှိပါလိမ့်မည်။ မြေပုံရေးဆွဲနေသည့် ဧရိယာအတွက် သင့်လျော်သော CRS တစ်ခု သို့မဟုတ် စံ CRS ရွေးချယ်မှုသည် အရေးကြီးပါသည်။ သို့မှသာ QGIS project သည် အဆိုပါ စံနှုန်းများအတိုင်း လုပ်ဆောင်မည်ဖြစ်ပါသည်။ 

ပုံမှန်အားဖြင့် QGIS သည် ကမ္ဘာလုံးဆိုင်ရာ ပုံမှန် (default) projection စနစ်ကို အသုံးပြုပြီး project အသစ်တစ်ခုကို စတင်ဖွင့်ပါသည်။ ၎င်း default CRS သည်  ``EPSG:4326`` ဖြစ်သည် ("WGS 84" စနစ်ဟုလည်း ခေါ်ဆိုပါသည်)၊ အဆိုပါစနစ်သည် latitude/longitude ကိုအခြေခံထားသည့် ကမ္ဘာသုံး (ဘုံသုံး) reference system တစ်ခုဖြစ်ပါသည်။ အဆိုပါ default CRS စနစ်ကို :menuselection:`Settings -->` |options| :menuselection:`Options...` အောက်ရှိ :guilabel:`CRS` tab ထဲတွင် :guilabel:`CRS for New Projects` မှတဆင့် ပြောင်းလဲနိုင်ပါသည်။ (:numref:`figure_projection_options` ပုံတွင် ကြည့်ရှုနိုင်ပါသည်) Project အသစ်တစ်ခုတွင် သွင်းထားသော ပထမ layer ၏ CRS စနစ်နှင့် ကိုက်ညီရန်အတွက် project ၏ CRS စနစ်ကို အလိုအလျောက်ပြောင်းနိုင်သော နည်းလမ်း တစ်ခုရှိသည်။ သို့မဟုတ် အသစ်ပြုလုပ်ထားသော project များအတွက် အသုံးပြုရန် မတူညီသည့် default CRS တစ်ခုကို ရွေးချယ် အသုံးပြုနိုင်ပါသည်။ ဤရွေးချယ်မှုကို  နောက်အသုံးပြုမည့် QGIS ကဏ္ဍများတွင် အဆင်သင့်အသုံးပြုရန် သိမ်းဆည်ထားမည်ဖြစ်ပါသည်။ 

Project CRS ကို :menuselection:`Project --> Properties...` dialog ၏ :guilabel:`CRS` tab မှတဆင့် သတ်မှတ်နိုင်ပါသည်။ ၎င်းကို QGIS status bar ၏ ညာဘက်အောက်ခြေတွင် တွေ့မြင်နိုင်သည်။ 

.. _figure_projection_project:

.. figure:: img/projectionDialog.png
   :align: center

   Project ဂုဏ်သတ္တိများ Dialog

ရွေးချယ်စရာနည်းလမ်းများမှာ-

* |unchecked| :guilabel:`No CRS (or unknown/non-Earth projection)` - ဤ setting တွင် အမှန်ခြစ်ပေးခြင်းသည် GIS project အတွင်းရှိ projection အားလုံးကို ရပ်တန့်စေသည်။ ၎င်းသည် ကမ္ဘာမြေပြင်ပေါ်ရှိတည်နေရာများနှင့် ချိတ်ဆက်ခြင်းမရှိတော့ပဲ layer များနှင့်  မြေပုံ ကိုဩဒိနိတ်များအားလုံးကို ရိုးရိုး 2D Cartesian ကိုဩဒိနိတ်များကဲ့သို့ ဖြစ်သွားစေပါသည်။ ၎င်းကို layer CRS တစ်ခု အား ခန့်မှန်းသိရှိရန် (၎င်း၏ မူရင်း ကိုဩဒိနိတ်များပေါ်တွင် အခြေခံပြီး) သို့မဟုတ် အသေးအမွှားအရာများမြေပုံဆွဲခြင်း၊ အဆောက်အဦးမြေပုံများဆွဲခြင်းနှင့် role-playing game မြေပုံများကဲ့သို့ ကမ္ဘာမြေပြင်နှင့်မသက်ဆိုင်သည့် (non earth) ကိစ္စများအတွက် QGIS ကိုဖန်တီးသည့်အခါ အသုံးပြုနိုင်ပါသည်။ ဤကိစ္စတွင်-
  
  * Feature များအား ၎င်းတို့၏ သက်ဆိုင်ရာ မူရင်း ကိုဩဒိနိတ်များကို အသုံးပြုပြီး ရေးဆွဲထားသဖြင့် layer များအား ပုံဖော်ပြသနေစဉ် reprojection ပြုလုပ်မည်မဟုတ်ပါ။
  * Ellipsoid ကို ပိတ်ထားပြီး ``None/Planimetric`` ကို ဖြစ်စေပါသည်။ 
  * အကွာအဝေး တိုင်းတာမှုများ၊ ဧရိယာတိုင်းတာမှုများနှင့် ကိုဩဒိနိတ် ပြသမှုများကို ပိတ်ထားပြီး "unknown units" (ယူနစ်မသိ) ဖြစ်စေပါသည်။ အတိုင်းအတာများအားလုံးသည် unknown map unit များတွင် လုပ်ဆောင်သဖြင့် အတိုင်းအတာပြောင်းလဲမှုများပြုလုပ်ရန် မဖြစ်နိုင်ပါ။ 
	
* သို့မဟုတ်  *geographic* ၊ *projected* ၊ သို့မဟုတ် *user-defined* ဖြစ်နိုင်သည့် ရှိနေပြီးသား coordinate reference system စနစ်တစ်ခု။ ကမ္ဘာမြေပြင်ရှိ CRS extent (နယ်ပယ်အကျယ်အဝန်း) ကို အကြိုပြသပေးထားသည့်အရာ (preview) သည်  သင့်လျော်သော စနစ်တစ်ခုခုအား ရွေးချယ်ရန် အထောက်အကူပြုပါသည်။ Project ထဲသို့ ထည့်သွင်းလိုက်သည့် layer များကို ၎င်းတို့၏ မူလ CRS များကို မစဉ်းစားပဲ layer များထပ်နိုင်ရန်အတွက် ရွေးချယ်ထားသော CRS အဖြစ်သို့ ရွှေ့ပြောင်းပေးပါသည်။ ယူနစ်အတိုင်းအတာများအသုံးပြုမှုနှင့် ellipsoid setting များကို ချိန်ညှိနိုင်ပြီး၊ တွက်ချက်တိုင်းတာမှုများလည်း  ဆောင်ရွက်နိုင်ပါသည်။ 
   
QGIS project အတွက် CRS အသစ်အား ရွေးချယ်သည့်အခါတိုင်း ရွေးချယ်ထားသော CRS စနစ်နှင့် ကိုက်ညီရန်အတွက် :guilabel:`Project properties` dialog(:menuselection:`Project --> Properties...`) ရှိ :guilabel:`General` tab ထဲတွင် အတိုင်းအတာယူနစ်များကို အလိုအလျောက် ပြောင်းပေးပါသည်။ ဉပမာအားဖြင့် - အချို့ CRS များသည်  ၎င်းတို့၏ ကိုဩဒိနိတ်များကို မီတာ (ယူနစ်) အစား ပေ (ယူနစ်) ဖြင့်သတ်မှတ်သည်။ ထို့ကြောင့် QGIS project ကို ၎င်း CRS များထဲမှ တစ်ခုဖြင့် သတ်မှတ်ခြင်းသည် project အတွင်းတိုင်းတာမှုများအတွက် ပေ (ယူနစ်)ကို ပုံမှန် (default) ယူနစ်ဖြစ်စေပါသည်။

.. tip:: **Layer တစ်ခု၏ CRS ဖြင့် Project အတွက် CRS သတ်မှတ်ခြင်း**

   Layer CRS စနစ်တစ်ခုအား အသုံးပြုပြီး project ရှိ CRS စနစ် အား သတ်မှတ်နိုင်သည်-

   #. :guilabel:`Layers` panel ထဲတွင် CRS အသုံးပြုလိုသည့် layer ပေါ်တွင် right-click နှိပ်ပါ။
   #. :guilabel:`Set project CRS from Layer` ကိုရွေးချယ်ပါ။ 

   Layer ၏ CRS ကို အသုံးပြုပြီး project ၏ CRS ကို ပြန်လည်သတ်မှတ်ပေးပါသည်။ မြေပုံမြင်ကွင်း extent ၊ ကိုဩဒိနိတ် တန်ဖိုးပြသမှုနှင့် project အတွင်းရှိ layer များအားလုံးသည် project CRS အသစ်ပေါ်မူတည်ပြီး update ဖြစ်သွားပါမည်။

.. index:: CRS Selection
.. _crs_selector:

Coordinate Reference System Selector (Coordinate Reference System ရွေးချယ်နိုင်သည့်အရာ)
========================================================================================

.. _figure_crs_selector:

.. figure:: img/crs_selector.png
   :align: center

   CRS Selector 

ယခု dialog သည် project တစ်ခု သို့မဟုတ် layer တစ်ခု၏ Coordinate Reference System တစ်ခုအား သတ်မှတ်ပေးရန် ကူညီပေးပြီး projection databases တစ်ခုလည်း ပါရှိပါသည်။ Dialog ထဲရှိ အရာများမှာ-

*  **Filter (စစ်ထုတ်ခြင်း)** - Coordinate Reference System အတွက် EPSG ကုဒ် ၊ identifier သို့မဟုတ် အမည်ကို သိလျှင် search feature ကို အသုံးပြုပြီး ရှာဖွေနိုင်သည်။ ထို့နောက် EPSG ကုဒ် ၊ identifier သို့မဟုတ် အမည် တစ်ခုခုအား ရိုက်ထည့်ပါ။ 
*  **Recently used coordinate reference systems (မကြာသေးမီကသုံးခဲ့သော CRS များ)** - နေ့စဉ် GIS အလုပ် လုပ်ဆောင်ချက်များတွင် မကြာခဏ အသုံးပြုနေသော အချို့ CRS များရှိလျှင်၊ ၎င်း CRS များကို စာရင်းထဲတွင် ဖော်ပြပါလိမ့်မည်။ ထို့နောက် ဆက်စပ်သော CRS တစ်ခုကို ရွေးချယ်ရန် ၎င်းအရာများထဲမှ တစ်ခုအား Click နှိပ်ပြီး ရွေးချယ်ပါ။ 
*  **Coordinate reference systems of the world (ကမ္ဘာကြီး၏ CRS များ)** - ၎င်းသည် QGIS တွင်လုပ်ဆောင်နိုင်သော CRS များအားလုံး၏စာရင်း ဖြစ်ပါသည်။ ၎င်းတွင် Geographic ၊  Projected နှင့်  Custom coordinate reference system များ အားလုံးပါဝင်ပါသည်။ CRS တစ်ခုခုအား ရွေးချယ်သတ်မှတ်ရန်အတွက် သင့်လျော်သော node (ဆုံချက်) အား ဖြန့်ကြည့်ခြင်းအားဖြင့် ၎င်းစာရင်းထဲမှ CRS တစ်ခုကို ရွေးချယ်ပါ။ လက်ရှိအသက်ဝင်နေသည့် CRS သည် ရွေးချယ်ပြီးသား ဖြစ်နေပါမည်။ 
*  **PROJ text (Projection စာသား)** - ၎င်းသည် PROJ projection engine မှ အသုံးပြုသော CRS string ဖြစ်ပါသည်။ ၎င်းစာသားသည် ဖတ်ရှုရန်သာဖြစ်ပြီး သတင်းအချက်အလက်ထောက်ပံ့ပေးနိုင်ရန်အတွက် ဖြစ်ပါသည်။ 


ယခင်အသုံးပြုထားခဲ့သည့် စာရင်းထဲမှ CRS ကို ဖယ်ထုတ်ခြင်း ပြုလုပ်ရန်အတွက် နည်းလမ်းများစွာရှိပါသည်-

* ညာဘက်ပိုင်းရှိ |clearItem| :sup:`Remove from recently used CRS` ခလုတ်အားနှိပ်ပါ။ 
* မိမိဖယ်ထုတ်ချင်သော CRS အား ရွေးချယ်ပြီးနောက် :kbd:`Del` အားနှိပ်ပါ။ 
* ယခင်အသုံးပြုထားသော  CRS အား Right-click နှိပ်ပြီး၊ ရွေးချယ်ထားသော CRS အား ဖယ်ရှားရန် |clearItem| :guilabel:`Remove selected CRS from recently used CRS` အား ရွေးချယ်ပါ သို့မဟုတ် ယခင်အသုံးပြုထားသော CRS အားလုံးကို ဖယ်ရှားရန် |clearConsole| :guilabel:`Clear all recently used CRS` အား ရွေးချယ်ပါ။ 
   

CRS selector သည် အသုံးပြုရန် ရွေးချယ်ထားသော CRS အတွက် ပထဝီဝင်တည်နေရာအား အကြမ်းမျဉ်း (preview) ကြိုတင်ပြသပေးပါသည်။ 
CRS များစွာကို အရွယ်အစားသေးသော ပထဝီဝင်တည်နေရာများအတွက်သာ ပုံဖော်ဖန်တီးထားပြီး၊ ပုံဖော်ဖန်တီးထားခဲ့သော တည်နေရာ၏အပြင်ဘက်များ အသုံးမပြုသင့်ပါ။  စာရင်းထဲမှ CRS စနစ်တစ်ခုအား ရွေးချယ်သည့်အခါတိုင်း ကြိုတင်ပြသထားသော မြေပုံများက သင့်လျော်သော အသုံးပြုတည်နေရာအား ပုံဖော်ပေးသည်။ ထို့အပြင် ၎င်းကြိုတင်ပြသထားသော မြေပုံသည် လက်ရှိအဓိက canvas ၏ မြေပုံ extent ကိုဖော်ပြပေးသည့် အညွှန်းကိန်းတစ်ခုကိုလည်း ပြသပေးသည်။

.. index:: CRS
   single: CRS; Custom CRS

.. _sec_custom_projections:

Custom Coordinate Reference System (စိတ်ကြိုက်သတ်မှတ်ထားသည့် Coordinate Reference System)
==========================================================================================

QGIS က လိုအပ်သည့် coordinate reference system အား မထောက့်ပံ့နိုင်လျှင်၊ စိတ်ကြိုက် CRS တစ်ခု (Custom CRS) ကို သတ်မှတ်အသုံးပြုနိုင်ပါသည်။ CRS စနစ်အား သတ်မှတ်ရန်အတွက် :menuselection:`Settings` menu ထဲမှ |customProjection|
:guilabel:`Custom CRS...` ကို ရွေးချယ်ပါ။ Custom CRS များကို QGIS user database ထဲတွင် သိမ်းဆည်းထားပါသည်။ ထို database ထဲတွင် custom CRS များအပြင် spatial bookmark များနှင့် အခြားသော custom data များ ပါဝင်ပါသည်။ 

QGIS တွင် custom CRS အား သတ်မှတ်ရာတွင် ROJ projection library အား ကောင်းကောင်း နားလည်သဘောပေါက်ရန် လိုအပ်ပါသည်။ စတင်လေ့လာရန်အတွက်  "Cartographic Projection Procedures for the UNIX Environment - A User's Manual" by Gerald I. Evenden, U.S. Geological Survey Open-File Report 90-284, 1990 စာအုပ်ကို ကိုးကားပါ။ (https://pubs.usgs.gov/of/1990/of90-284/ofr90-284.pdf တွင် ရယူနိုင်ပါသည်)

ဤ manual စာအုပ်သည် ``proj`` အသုံးပြုပုံနှင့် ဆက်နွယ်သော command line အသုံးပြုပုံများအား ဖော်ပြပေးထားသည်။ ``proj`` ဖြင့်အသုံးပြုထားသော cartographic parameter (မြေပုံရေးဆွဲခြင်းနှင့်ဆိုင်သည့် သတ်မှတ်ချက်) များကို ဤအသုံးပြုသူ manual စာအုပ်တွင် ဖော်ပြထားရှိပြီး ၎င်းသည် QGIS က အသုံးပြုနေသော အရာများနှင့် တူပါသည်။ 

User CRS အတွက် သတ်မှတ်ရန် :guilabel:`Custom Coordinate Reference System Definition` dialog သည်
parameter ၂ ခုသာလျှင်လိုအပ်သည်-

#. A descriptive name (ဖော်ပြပေးမည့် နာမည်တစ်ခု)
#. The cartographic parameters in PROJ or WKT format (PROJ သို့မဟုတ် WKT format ဖြင့် cartographic parameter များ)

CRS စနစ် အသစ်တစ်ခုအား ဖန်တီးထည့်သွင်းရန်-

#. |symbologyAdd| :sup:`Add new CRS` button အား click နှိပ်ပါ။ 
#. ဖော်ပြမည့် အမည်တစ်ခု ထည့်သွင်းပါ။
#. Format ကို ရွေးချယ်ပါ။ ၎င်းသည်  :guilabel:`Proj String` သို့မဟုတ်  :guilabel:`WKT` ဖြစ်နိုင်သည်။
#. CRS :guilabel:`Parameters` များထည့်သွင်းပါ။

   .. note:: **CRS definition များကို WKT format ဖြင့်သိမ်းဆည်းခြင်းကို ဦးစားပေးပါ**

	``Proj String`` နှင့် ``WKT`` format များအား ထောက်ပံ့ပေးထားသော်လည်း WKT format ထဲတွင် projection အဓိပ္ပါယ်သတ်မှတ်ချက်များကို သိမ်းဆည်းထားခြင်းကို အထူးအကြံပြုပါသည်။ ထို့ကြောင့် အဓိပ္ပါယ်သတ်မှတ်ချက် proj format ဖြင့်ရှိနေလျှင် ၎င်း format အား ရွေးချယ်ပြီး	parameter များအားထည့်သွင်းပါ။ ထို့နောက် WKT format အား ပြောင်းလိုက်ပါ။ QGIS က WKT format သို့ အဓိပ္ပါယ်သတ်မှတ်ချက်ကို ပြောင်းပေးပြီး ၎င်းကို နောက်ပိုင်းတွင် သိမ်းဆည်းထားနိုင်ပါသည်။ 
	
#. CRS အဓိပ္ပါယ်သတ်မှတ်ချက်သည် လက်ခံနိုင်သော projection အဓိပ္ပါယ်သတ်မှတ်ချက် ဖြစ်မဖြစ်ကို စစ်ဆေးရန် :guilabel:`Validate` အား
   click နှိပ်ပါ။ 
   
.. _figure_projection_custom:

.. figure:: img/customProjectionDialog.png
   :align: center

   စိတ်ကြိုက် CRS တစ်ခုဖန်တီးခြင်း Dialog

ကောင်းမွန်သောရလာဒ်များ ဖြစ်မဖြစ်ကိုကြည့်ရှုရန် CRS parameter များကို စမ်းသပ်နိုင်သည်။ ထိုသို့လုပ်ဆောင်ရန်အတွက် :guilabel:`North` နှင့် :guilabel:`East` fields ထဲတွင် သိရှိပြီးသား WGS 84 latitude နှင့် longitude တန်ဖိုးများ ထည့်သွင်းပါ။ :guilabel:`Calculate` အား click နှိပ်ပြီး ယခင် coordinate reference system ရှိ သိရှိပြီးသားတန်ဖိုးများနှင့် ရလဒ်များအား နှိုင်းယှဉ်ပါ။ 

Integrate an NTv2-transformation in QGIS (NTv2-transformation ကို QGIS တွင် ပေါင်းစပ်အသုံးပြုခြင်း)
----------------------------------------------------------------------------------------------------

QGIS တွင် NTv2 transformation file တစ်ခုကို ပေါင်းစပ်အသုံးပြုရန် နောက်ထပ်အဆင့်တစ်ဆင့်လိုအပ်ပါသည်-

#. QGIS မှ အသုံးပြုသည့် CRS/Proj folder ထဲတွင် NTv2 file (.gsb) ကိုထားပါ။ 
   (ဉပမာ - Window အသုံးပြုသူများအတွက် :file:`C:\\OSGeo4W64\\share\\proj`)
#. :guilabel:`Custom Coordinate Reference System Definition` (:menuselection:`Settings --> Custom Projections...`) ၏ 
   :guilabel:`Parameters` field ရှိ Proj definition တွင် **nadgrids** (``+nadgrids=nameofthefile.gsb``) ကို ပေါင်းထည့်ပါ။ 

   .. _figure_nadgrids:

   .. figure:: img/nadgrids_example.png
      :align: center

      NTv2 transformation တစ်ခုကို ပြင်ဆင်သတ်မှတ်ခြင်း


.. index:: Datum transformation
.. _datum_transformation:

Datum Transformations (မူတည်မျက်နှာပြင် အပြောင်းအလဲပြုလုပ်ခြင်း)
=================================================================

QGIS တွင် 'on-the-fly' CRS transformation ကို default အနေဖြင့်ထည့်သွင်းပေးထားပါသည်။ ဆိုလိုသည်မှာ 
မတူညီသော coordinate system များဖြင့် layer များကို အသုံးပြုသည့်အချိန်တိုင်း QGIS သည် ၎င်းတို့ကို project CRS
သို့ ပြန်လည်ပြောင်းပေးပါသည်။ အချို့သော CRS များအတွက် project ၏ CRS သို့ reproject ပြုလုပ်ပေးနိုင်သော ဖြစ်နိုင်ခြေရှိသည့်ပြောင်းလဲမှုများ အများအပြားရှိပါသည်။

ပုံမှန်အားဖြင့် QGIS သည် ရရှိနိုင်သည့် အတိကျဆုံး transformation ကို အသုံးပြုရန် ပြုလုပ်ပါလိမ့်မည်။ သို့သော် အချို့သော ဖြစ်ရပ်များ၊ ဥပမာအားဖြင့် - transformation တစ်ခုကို အသုံးပြုရန် အပို ပံ့ပိုးဖြည့်ဆည်းပေးသော file (support file) များလိုအပ်သည့်ဖြစ်ရပ်များတွင် မဖြစ်နိုင်ပါ။ လက်ရှိအသုံးပြုရန် အဆင်သင့်မဖြစ်သေးသော်လည်း ပိုမိုတိကျသော transformation တစ်ခု ရနိုင်သည့်အချိန်တိုင်း QGIS က ပိုမိုတိကျသော transformation ကို အသုံးပြုရန် သတိပေး message ကိုဖော်ပြပေးပြီး  မိမိ system ထဲ၌ မည်သို့ အသုံးပြုရမည်ဆိုသည့် နည်းလမ်းကိုပါ ပြသပေးလိမ့်မည်။ ပုံမှန်အားဖြင့် ၎င်းသည် ပြင်ပ transformation support file package တစ်ခု download ပြုလုပ်ရန် လိုအပ်ပြီး အဆိုပါ file များကို မိမိ QGIS ရှိ :ref:`user profile <user_profiles>` folder အောက်တွင်ရှိသည့် :file:`proj` folder ထဲတွင် ထည့်သွင်းထားရပါမည်။

ဆန္ဒရှိမည်ဆိုလျှင် CRS နှစ်ခုကြားတွင် ဖြစ်နိုင်သမျှ transformation မျိုးစုံကို ပြုလုပ်နိုင်သည့်အချိန်တိုင်း QGIS သည် တိုက်တွန်းပေးနိုင်ပြီး မိမိ data အတွက် အသင့်လျော်ဆုံးဖြစ်သော transformation ကို ရွေးချယ်နိုင်စေပါသည်။ 

ဤ စိတ်ကြိုက်ပြင်ဆင်ခြင်းကို :guilabel:`Default datum transformations` အုပ်စုအောက်ရှိ 
:menuselection:`Settings -->` |options|:menuselection:`Options --> Transformations` tab menu ထဲတွင် ပြုလုပ်ပါသည်။

* |checkbox| :guilabel:`Ask for datum transformation if several are available` ကို အသုံးပြုခြင်း - 
  မူလဇစ်မြစ်/ ပြုလုပ်လိုသော CRS အတွဲတစ်ခုအတွက် သင့်လျော်သော datum transformation တစ်ခုထက်မက တည်ရှိသည့်အခါ project တွင်အသုံးပြုရန် အသုံးပြုသူများအနေဖြင့် မည်သည့် datum transformation ကို ရွေးချယ်နိုင်စေရန် dialog တစ်ခု အလိုအလျောက် ပွင့်လာပါလိမ့်မည်။ ၎င်း dialog မှ transformation တစ်ခုကို ရွေးချယ်ပြီးသည့်အခါ :guilabel:`Make default` checkbox ကို အမှန်ခြစ်ပေးထားပါက ထိုရွေးချယ်ထားမှုကို မှတ်ထားပေးပြီး အသစ်ပြုလုပ်လိုက်သော QGIS project တိုင်းတွင် အလိုအလျောက် အသုံးပြုသွားမည်ဖြစ်ပါသည်။ 
* Project တစ်ခုထဲသို့ layer တစ်ခုထည့်သွင်းခြင်း သို့မဟုတ် layer တစ်ခုကို reproject (projection တစ်ခုမှတစ်ခုသို့ ပြောင်းလဲခြင်း) ပြုလုပ်သည့်အခါ default အနေဖြင့် အသုံးပြုနိုင်ရန် သင့်လျော်သော Datum transformation စာရင်းတစ်ခုကို သတ်မှတ်ပေးထားခြင်း။
  
  :guilabel:`Select Datum Transformations` dialog ကို ဖွင့်ရန် |symbologyAdd| ခလုတ်ကို အသုံးပြုပါ။ ထို့နောက်-
	
  #. Drop-down menu သို့မဟုတ် |setProjection| :sup:`Select CRS` widget ကို အသုံးပြုပြီး layer ၏ :guilabel:`Source CRS` ကို ရွေးချယ်ပါ၊ 
  #. ထိုနည်းအတိုင်း :guilabel:`Destination CRS` ကိုလည်း ပြုလုပ်ပေးပါ။ 
  #. Source မှ destination သို့ ပြောင်းရန် ရနိုင်သော transformation များ စာရင်းကို ဇယားတွင် ပေးပါလိမ့်မည်။ Row တစ်ခုခုကို click ပြုလုပ်ခြင်းသည် transformation ၏ လက်ရှိအသုံးပြုထားသည့် setting များ၊ သက်ဆိုင်ရာ တိကျမှုနှင့် ဧရိယာဆိုင်ရာ အသေးစိတ်အချက်အလက်များကို ပြသပေးပါသည်။
	 
     .. _figure_projection_datum:

     .. figure:: img/datumTransformation.png
        :align: center

        နှစ်သက်ရာ default datum transformation တစ်ခုကို ရွေးချယ်ခြင်း 

     အချို့သော ဖြစ်ရပ်များတွင်မူ မိမိ system တွင် အသုံးပြုရန်အတွက် transformation သည် ရရှိနိုင်လိမ့်မည်မဟုတ်ပါ။  ဤဖြစ်ရပ်တွင် transformation ကို စာရင်းထဲတွင် (မီးခိုးရောင်) ဖြင့် ပြသနေလိမ့်မည်။ သို့သော် transformation ကို အထောက်အပံ့ပေးသော လိုအပ်သည့် package ကို install (ထည့်သွင်း) မလုပ်မချင်း ၎င်းကို အသုံးပြု၍မရနိုင်ပါ။ ပုံမှန်အားဖြင့် သက်ဆိုင်ရာ grid ကို install (ထည့်သွင်း) လုပ်ရန် နှင့် download ပြုလုပ်ရန် ခလုတ်တစ်ခုကို ဖော်ပြပေးထားပြီး ၎င်းကို :ref:`user profile <user_profiles>` directory ရှိ :file:`proj` folder ထဲတွင် သိမ်းဆည်းထားပါသည်။ 
	 
  #. မိမိနှစ်သက်သော transformation ကို ရှာဖွေပြီး၊ ရွေးချယ်ပါ။ 
  #. |checkbox| :guilabel:`Allow fallback transforms if preferred operation fails` ကို အမှန်ခြစ်/မဖြစ် သတ်မှတ်ပါ။ 
  #. :guilabel:`OK` ကိုနှိပ်ပါ။ 

	 Transformation အတွက် အသုံးပြုသည့် :guilabel:`Destination CRS` ၊ :guilabel:`Operation` ၊ :guilabel:`Source CRS` များနှင့် :guilabel:`Allow fallback Transforms` ကိုခွင့်ပြုထားခြင်းရှိ/မရှိ နှင့်သက်ဆိုင်သော အချက်အလက်များပါဝင်သည့် row တစ်ခုကို :guilabel:`Default Datum Transformations` အောက်ရှိ table ထဲသို့ ထပ်ပေါင်းထည့်ပေးပါသည်။ 

  ယခုမှစ၍ စာရင်းထဲရှိ entry (|toggleEditing|) ကို ပြောင်းလိုက်ခြင်း သို့မဟုတ် စာရင်းထဲမှ (|symbologyRemove|)ဖယ်ထုတ်လိုက်ခြင်း မပြုလုပ်မချင်း QGIS သည် CRS စနစ် ၂ ခုကြားတွင် နောက်လာမည့် transformation အတွက် ရွေးချယ်ထားသော datum transformation များကို အလိုအလျောက် အသုံးပြုပါသည်။ 
  
မိမိ system တွင်  အသစ်ပြုလုပ်ဖန်တီးလိုက်သော QGIS project များ အားလုံးသည် :menuselection:`Settings -->` |options|
:menuselection:`Options --> Transformations` tab တွင် သတ်မှတ်ထားသော Datum transformation များကို ဆက်လက်အသုံးပြုသွားမည်ဖြစ်ပါသည်။ ထို့အပြင် အခြား သီးခြား project တစ်ခုတွင် :guilabel:`Project properties` dialog
(:menuselection:`Project --> Properties...`) ၏ :guilabel:`CRS` tab မှတဆင့် ကိုယ်ပိုင် သီးခြားပြုလုပ်ထားသော transformation များရှိနိုင်ပါသည်။ အဆိုပါ setting များသည် လက်ရှိ လုပ်ဆောင်နေသော project ကိုသာ သက်ရောက်မှုရှိပါသည်။

 
.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |clearConsole| image:: /static/common/iconClearConsole.png
   :width: 1.5em
.. |clearItem| image:: /static/common/mIconClearItem.png
   :width: 1.5em
.. |customProjection| image:: /static/common/mActionCustomProjection.png
   :width: 1.5em
.. |indicatorNoCRS| image:: /static/common/mIndicatorNoCRS.png
   :width: 1.5em
.. |options| image:: /static/common/mActionOptions.png
   :width: 1em
.. |radioButtonOff| image:: /static/common/radiobuttonoff.png
   :width: 1.5em
.. |radioButtonOn| image:: /static/common/radiobuttonon.png
   :width: 1.5em
.. |setProjection| image:: /static/common/mActionSetProjection.png
   :width: 1.5em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
.. |symbologyRemove| image:: /static/common/symbologyRemove.png
   :width: 1.5em
.. |toggleEditing| image:: /static/common/mActionToggleEditing.png
   :width: 1.5em
.. |unchecked| image:: /static/common/unchecked.png
   :width: 1.3em
