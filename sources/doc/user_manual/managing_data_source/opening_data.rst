.. index:: Vector, OGR, Raster, GDAL, Data, Format, QLR
.. index:: PostGreSQL, PostGIS, GeoPackage, SpatiaLite, GRASS, DXF
.. index:: ArcInfo Binary Grid, ArcInfo ASCII Grid, GeoTIFF, Erdas Imagine

.. _opening_data:

***********************************
Opening Data (Data ကို ဖွင့်ခြင်း)
***********************************

.. only:: html

   .. contents::
      :local:

Open Source Software ecosystem တစ်ခု၏ တစ်စိတ်တစ်ပိုင်းဖြစ်သည့်အားလျော်စွာ QGIS ကို formats အများစုအား ရေးသားရန်နှင့် ဖတ်ရှုရန် စွမ်းဆောင်ရည်များ (capabilities) ကို ပံ့ပိုးပေးသည့် ၎င်း၏ ကိုယ်ပိုင် providers (GIS addressing နှင့် mapping အတွက် data ကို ဖန်တီးရန်နှင့်စီမံခန့်ခွဲသည့် တစ်ဦးတစ်ယောက်၊ အဖွဲ့အစည်း သို့မဟုတ် အေဂျင်စီ) များနှင့်ပေါင်းစပ်၍ မတူညီသော libraries (ကြိုတင်စုစည်းထားသည့်ဖိုင်များ၊ ပြန်လည်အသုံးချနိုင်သည့်ဖိုင်များ၊ ပြုမူဆောင်ရွက်ချက် (function) များ ၊ script များ ၊ routine များနှင့် အခြားသောရင်းမြစ်များ စုစည်းထားသည့်နေရာ) များအပေါ်တွင် တည်ဆောက်ထားပါသည်။ 

* Vector data formats များတွင် GeoPackage ၊ GML ၊ GeoJSON ၊ GPX ၊ KML ၊ Comma Separated Values ၊ ESRI formats (Shapefile, Geodatabase...)၊ MapInfo နှင့် MicroStation file formats ၊ AutoCAD DWG/DXF ၊ GRASS နှင့်  နောက်ထပ်အခြားသော format များပါဝင်ပါသည်။ `supported vector formats <https://gdal.org/drivers/vector/index.html>`_  စာရင်းအပြည့်အစုံကို ဖတ်ရှုပါ။ 
* Raster data formats များတွင် GeoTIFF ၊ JPEG ၊ ASCII Gridded XYZ ၊ MBTiles ၊ R or Idrisi rasters ၊ GDAL Virtual ၊ SRTM ၊ Sentinel Data ၊ ERDAS IMAGINE ၊ ArcInfo Binary Grid ၊ ArcInfo ASCII Grid နှင့် နောက်ထပ်အခြားသော format များပါဝင်ပါသည်။ `supported vector formats <https://gdal.org/drivers/vector/index.html>`_ စာရင်းအပြည့်အစုံကို ဖတ်ရှုပါ။ 
* Database formats များတွင် PostgreSQL/PostGIS ၊ SQLite/SpatiaLite ၊ Oracle ၊ MS SQL Server ၊ SAP HANA ၊ MySQL... တို့ပါဝင်ပါသည်။ 
* Web map နှင့် data services (WM(T)S ၊ WFS ၊ WCS ၊ CSW ၊ XYZ tiles ၊ ArcGIS services ၊ ...) များကိုလည်း QGIS providers များမှ ကိုင်တွယ်ဆောင်ရွက်နိုင်ပါသည်။ ဤထဲမှအချို့၏ နောက်ထပ်အချက်အလက်များအတွက် :ref:`working_with_ogc` ကို ကြည့်ရှုပါ။ 
* Archived folder (မှတ်တမ်းအဖြစ်သိမ်းဆည်းထားသော folder များ) များမှ supported files (ပံ့ပိုးသည့်ဖိုင်များ) ကို ဖတ်ရှုနိုင်ပြီး QML files (:ref:`qgisstylefile`) နှင့် virtual layers (advanced query တစ်ခု၏ရလဒ်အဖြစ် layer တစ်ခုကို သတ်မှတ်ရန်ခွင့်ပြုသည့် အထူး vector layer အမျိုးအစားတစ်ခု) နှင့် memory layers (memory layer တစ်ခုသည် အခြားသော vector layer ကဲ့သို့ပင်ဖြစ်သော်လည်း ၎င်းသည် disk အပေါ်တွင်မရှိဘဲ QGIS ကိုထွက်လိုက်သည်နှင့် ပျောက်ကွယ်သွားမည်ဖြစ်ပါသည်။) ကဲ့သို့သော QGIS native formats (QGIS ၏ မူလ format များ) များကို အသုံးပြုနိုင်ပါသည်။ 

Vector format (၈၀) ကျော် နှင့် raster format (၁၄၀) ကျော်ကို `GDAL <https://gdal.org/>`_ နှင့် QGIS native providers (QGIS ၏ မူလပံ့ပိုးသူများ) များမှပံ့ပိုးပေးထားပါသည်။ 

.. note::

   စာရင်းပြုစုထားသည့် format များအားလုံးတိုင်း အကြောင်းအမျိုးမျိုးကြောင့် QGIS တွင် အလုပ်လုပ်နိုင်မည်မဟုတ်ပါ။ ဥပမာ - အချို့သည် ပြင်ပ proprietary libraries (stockholding proprietors နှင့် subscribers မှ ပံ့ပိုးပေးလေ့ရှိသော library) များလိုအပ်မည်ဖြစ်ပြီး သို့မဟုတ် အချို့သည် သင်အသုံးပြုလိုသော format ကို ပံ့ပိုးရန် သင့်ကွန်ပျူတာ OS တွင် GDAL/OGR ထည့်သွင်းတည်ဆောက်မှု (installation) မရှိပါက ၎င်းကို ထည့်သွင်းရန် လိုအပ်ပါသည်။ ရရှိနိုင်သည့် formats စာရင်းများကို ကြည့်ရန် command line  ``ogrinfo --formats`` (vector အတွက်) နှင့် ``gdalinfo --formats`` (raster အတွက်) ကို run (ဆောင်ရွက်) ပါ။ သို့မဟုတ် QGIS ထဲရှိ :menuselection:`Settings --> Options --> GDAL` menu ကို check ပြုလုပ်ပါ။ 

.. _datasourcemanager:

QGIS တွင် data format အလိုက် dataset တစ်ခုကိုဖွင့်ရန် အမျိုးမျိုးသော tools များရှိပါသည်။ 
၎င်းတို့ကို အဓိကအားဖြင့် :menuselection:`Layer --> Add Layer -->` menu သို့မဟုတ် :guilabel:`Manage Layers` toolbar (:menuselection:`View --> Toolbars` menu ကို ဖွင့်ခြင်းဖြင့်) မှရရှိနိုင်ပါသည်။
သို့ရာတွင် ဤ tools များအားလုံးသည် unique dialog (သိသာထင်ရှားသည့်သီးခြားဒိုင်ယာလော့ခ်) :guilabel:`Data Source Manager` dialog တစ်ခုကိုညွှန်ပြပါသည်။ ၎င်းကို :guilabel:`Data Source Manager Toolbar` တွင် ရရှိနိုင်သည့်  |dataSourceManager|:sup:`Open Data Source Manager` button ဖြင့် သို့မဟုတ် :kbd:`Ctrl+L` ကို နှိပ်ခြင်းဖြင့် ဖွင့်နိုင်ပါသည်။ :guilabel:`Data Source Manager` dialog (:numref:`figure_datasource_manager`) သည် QGIS မှ ပံ့ပိုးပေးထားသည့် web services သို့မဟုတ် database များအပြင် file-based data များကိုဖွင့်ရန် unified interface (မည်သည့် စခရင်အရွယ်အစား၊ စက်ပစ္စည်း သို့မဟုတ် orientation များအတွက် အကောင်းဆုံးသော  ကြည့်ရှုမှုနှင့်ပေါင်းစည်းဆောင်ရွက်မှုကိုပံ့ပိုးရန်အတွက် တုံ့ပြန်မှုရှိသည့် web design principles ကို အသုံးပြုသည့် interface။) တစ်ခုကို ပံ့ပိုးပေးပါသည်။

.. _figure_datasource_manager:

.. figure:: img/datasource_manager.png
   :align: center

   QGIS Data Source စီမံခန့်ခွဲမှုဆိုင်ရာ Dialog

ဤ အဓိက entry point အပြင် ချိတ်ဆက်ထားသည့် (connected) databases များကို ဆန်းစစ်လေ့လာရန် (analyze) နှင့်ကိုင်တွယ်ဆောင်ရွက်ရန် (manipulate) အထူးစွမ်းဆောင်ရည်များ (advanced capabilities) ကိုပံ့ပိုးပေးသည့် :guilabel:`DB Manager` plugin လည်းပါရှိပါသည်။ 
DB Manager ၏ စွမ်းဆောင်ရည်များနှင့်ဆက်စပ်သည့် နောက်ထပ်အချက်အလက်များကို :ref:`dbmanager` တွေ့နိုင်ပါသည်။ 

အမျိုးမျိုးသော data formats များကို ဖွင့်ရန်ကူညီနိုင်သည့် အခြားသော tools များ၊ native (မူရင်း) သို့မဟုတ် third-party (သီးခြား) plugins များရှိပါသည်။ 

ဤအခန်းသည် data များကိုထည့်သွင်းရန်အတွက် QGIS မှ ပုံမှန်(default) ပံ့ပိုးထားသည့် tools များကိုသာ ဖော်ပြသွားမည်ဖြစ်ပါသည်။ ၎င်းသည် tab တစ်ခုချင်းစီကို ဖော်ပြခြင်းထက် :guilabel:`Data Source Manager` dialog အပေါ်တွင် အဓိကအလေးပေးသွားမည်ဖြစ်ပါသည်။ ၎င်းသည် data provider သို့မဟုတ် format specificities (format သတ်မှတ်ချက်များ) အပေါ်တွင် အခြေခံသည့် tool များကို ဖော်ထုတ်လေ့လာသွားမည်ဖြစ်ပါသည်။ 

.. index:: Browse data, Add layers
.. _browser_panel:

The Browser Panel (QGIS အရင်းအမြစ်များကို ရှာဖွေခြင်း၊ စစ်ဆေးခြင်း၊ ကော်ပီကူးယူခြင်းနှင့် ထည့်သွင်းခြင်းတို့ဆောင်ရွက်နိုင်သည့် Panel)
======================================================================================================================================

:guilabel:`Browser` သည် projects များထဲသို့ data များကို လွယ်ကူလျှင်မြန်စွာထည့်သွင်းနိုင်သည့် အဓိကနည်းလမ်းများထဲမှ တစ်ခုဖြစ်ပါသည်။ ၎င်းကို ဖော်ပြအတိုင်းရရှိနိုင်ပါသည်-

* :guilabel:`Data Source Manager` tab တစ်ခု အဖြစ်၊ |dataSourceManager| :sup:`Open Data Source Manager` button (:kbd:`Ctrl+L`) ကို နှိပ်ခြင်းဖြင့် ဆောင်ရွက်နိုင်ပါသည်။ 
* :menuselection:`View --> Panels` menu (သို့မဟုတ် |kde| :menuselection:`Settings --> Panels`)  မှ သို့မဟုတ် :kbd:`Ctrl+2` ကို နှိပ်ခြင်းဖြင့် ဖွင့်နိုင်သည့် QGIS panel တစ်ခုအဖြစ်။

ကိစ္စရပ်နှစ်ခုလုံးတွင် :guilabel:`Browser` သည် layer ၏ အမျိုးအစား (raster ၊ vector ၊ table(ဇယား)) သို့မဟုတ် datasource format (plain သို့မဟုတ် compressed files ၊ databases ၊ web services) နှင့်မသက်ဆိုင်ဘဲ ဖိုင်စနစ်ထဲတွင် navigate  (တည်နေရာနှင့်တစ်နေရာမှတစ်နေရာသို့ သွားလာသည့်လမ်းကြောင်းများကို ထိန်းချုပ်ကိုင်တွယ်ခြင်း) ပြုလုပ်ခြင်းနှင့် geodata (GIS ဖြင့်အသုံးပြုနိုင်သည့် format တစ်ခုထဲတွင် သိမ်းဆည်းထားသော ပထဝီဝင်ဆိုင်ရာတည်နေရာများနှင့်စပ်လျဉ်းသည့် အချက်အလက်) အား စီမံခန့်ခွဲခြင်းကို ကူညီပါသည်။

Exploring the Interface (Interface ကို စူးစမ်းလေ့လာရှာဖွေဖော်ထုတ်ခြင်း)
------------------------------------------------------------------------

Browser panel ၏ ထိပ်ဘက်တွင် ဖော်ပြပါတို့ကို ဆောင်ရွက်ရန် ကူညီနိုင်သည့် buttons (ခလုတ်များ) အချို့ကို တွေ့နိုင်ပါသည်- 

* |addLayer| :sup:`Add Selected Layers` - Layer ၏ context menu (အသုံးပြုသူများမှ ဆောင်ရွက်လိုသည့် လုပ်ဆောင်ချက်များအတွက် shortcuts များပံ့ပိုးပေးထားသည့် pop-up menu တစ်ခု) မှ  **Add selected layer(s)** ကို ရွေးချယ်ခြင်းဖြင့် data ကို map canvas (မြေပုံရေးဆွဲမည့်နေရာ) ထဲသို့ ထည့်သွင်းနိုင်ပါသည်။ 
* |refresh| :sup:`Refresh` - browser tree ကို refresh ပြုလုပ်ပါသည်။
* သီးသန့် data (specific data) များကို ရှာဖွေရန် |filterMap| :sup:`Filter Browser`။ ရှာဖွေမည့်စကားလုံး သို့မဟုတ် wildcards (``?`` နှင့်/သို့မဟုတ် ``*`` ကာရိုက်တာများ (characters)) များကို ထည့်သွင်းပါ။ Browser သည်  အခြား data သို့မဟုတ် folders များကို ပြသသွားမည်မဟုတ်ဘဲ DB tables များ ၊ ဖိုင်အမည်များ သို့မဟုတ် folders များ နှင့်ကိုက်ညီမှုရှိသည့် လမ်းကြောင်းများ (paths) ကိုသာပြသရန် tree ကို စစ်ထုတ်သွားမည်ဖြစ်ပါသည်။ :numref:`figure_browser_panels` ထဲရှိ Browser Panel(2) နမူနာကို ကြည့်ရှုပါ။ နှိုင်းယှဉ်မှု (comparison) သည် case-sensitive (စာလုံးအကြီးအသေးအတိုင်း အတိအကျဖြစ်မှု)  ဖြစ်ကောင်းဖြစ်နိုင်သည် သို့မဟုတ် မဖြစ်နိုင်ပါ။ ၎င်းကိုဖော်ပြပါအတိုင်း သတ်မှတ်နိုင်ပါသည်-
  * :guilabel:`Normal` - ရှာဖွေသည့်စာသား (search text) ပါဝင်သည့် items များကိုပြသသည်။
  * :guilabel:`Wildcard(s)` - ရှာဖွေသည့်စာသား၏ တည်နေရာကို သတ်မှတ်ရန် ``?`` နှင့်/သို့မဟုတ် ``*`` ကာရိုက်တာများ (characters)ကို အသုံးပြု၍ ရှာဖွေမှုကိုချောမွေ့စေသည်။
  * :guilabel:`Regular expression`
* |collapseTree| :sup:`Collapse All` - Tree တစ်ခုလုံးကို Collapse (စုစည်း) ပြုလုပ်ခြင်း
* |metadata| :sup:`Enable/disable properties widget` - ဖွင့်ထားသည့်အခါတွင် select ပြုလုပ်ထားသည့် item အတွက် metadata (အခြားသော data ၏ အချက်အလက်များကို ဖော်ပြသည့် data အစုအဝေး) များ ရှိနေပါက ၎င်းတို့ကို ဖော်ပြထားသော widget အသစ်တစ်ခုကို panel ၏ အောက်ခြေတွင် ထည့်သွင်းသွားမည်ဖြစ်ပါသည်။ 

:guilabel:`Browser` panel ထဲရှိ entries များကို အဆင့်အတန်းအလိုက် (hierarchically) ဖွဲ့စည်းထားပြီး top level (ထိပ်ပိုင်းအဆင့်) entries များစွာရှိပါသည်- 

#. :guilabel:`Favorites` - မကြာခဏအသုံးပြုသည့် locations (တည်နေရာများ) အတွက် shortcuts များကို ဤနေရာမှတဆင့် ထည့်သွင်းနိုင်ပါသည်။ 
#. :guilabel:`Spatial Bookmarks` - မကြာခဏ အသုံးပြုသည့် map extents (မြေပုံအတိုင်းအတာနယ်ပယ်) များကို သိမ်းဆည်းနိုင်သည့်နေရာဖြစ်ပါသည်။ (:ref:`sec_bookmarks` တွင် ကြည့်ပါ)
#. :guilabel:`Project Home` - Project နှင့်သက်ဆိုင်သည့် data (အများစု) ကိုသိမ်းဆည်းထားသည့် folder တစ်ခုကို လျင်မြန်စွာ access (ရယူသုံးစွဲ) ရရှိရန်အတွက်ဖြစ်ပါသည်။ ပုံမှန်တန်ဖိုး (default value) သည် project file တည်ရှိသည့် directory (လမ်းညွှန်) ဖြစ်ပါသည်။ 
#. ဖိုင်စနစ်ထဲရှိ :guilabel:`Home` directory နှင့် filesystem root directory (hierarchy တစ်ခုထဲရှိ first or top-most directory) 
#. ချိတ်ဆက်ထားသည့် Local သို့မဟုတ် network drives များ။
#. ထို့နောက် ပလက်ဖောင်း (platform) နှင့် underlying libraries (ရင်းခံ libraries) များအပေါ်မူတည်၍ number of container (နိုင်ငံတကာတွင် ကွန်တိန်နာများကို ခွဲခြားသတ်မှတ်ရန်အတွက် အသုံးပြုသည့် ဂဏန်းခုနစ်လုံးနှင့် စာလုံးလေးလုံးတို့၏ သီးသန့် အယ်လ်ဖာဂဏန်းများ ပေါင်းစပ်မှု)/ database အမျိုးအစားများ နှင့် service protocols (ဝန်ဆောင်မှုဆိုင်ရာကျင့်ဝတ်) များ ပါရှိပါသည်-

   * |geoPackage| :guilabel:`GeoPackage`
   * |spatialite| :guilabel:`SpatiaLite`
   * |postgis| :guilabel:`PostgreSQL`
   * |hana| :guilabel:`SAP HANA`
   * |mssql| :guilabel:`MS SQL Server`
   * |oracle| :guilabel:`Oracle`
   * |wms| :guilabel:`WMS/WMTS`
   * |vectorTileLayer| :guilabel:`Vector Tiles`
   * |xyz| :guilabel:`XYZ Tiles`
   * |wcs| :guilabel:`WCS`
   * |wfs| :guilabel:`WFS/OGC API-Features`
   * |afs| :guilabel:`ArcGIS REST Server`

Interacting with the Browser items (Browser items များနှင့်အပြန်အလှန် လုပ်ကိုင်ဆောင်ရွက်ခြင်း)
-----------------------------------------------------------------------------------------------

Browser သည် browser မှ canvas အတွင်း နှင့် :guilabel:`Layers` panel အတွင်းသို့ ၊ :guilabel:`Layers` panel မှ browser ထဲရှိ layer containers (ဥပမာ- GeoPackage) များသို့နှင့် browser အတွင်းသို့ drag and drop (ဖိဆွဲ၍နေရာချခြင်း) ကို ပံ့ပိုးပေးပါသည်။

Browser ထဲရှိ Project file items များကို အဆိုပါ project အတွင်းတွင် ပါရှိသည့် layer tree (groups များအပါအဝင်) ကို အပြည့်ပြသခြင်းနှင့်အတူ ချဲ့ထွင် (expand) နိုင်ပါသည်။ ၎င်းတို့ကို browser ထဲတွင် drag and drop (ဖိဆွဲ၍နေရာချခြင်း) (ဥပမာ- layer item တစ်ခုကို geopackage file တစ်ခုသို့ ကော်ပီကူးယူရန်) ပြုလုပ်နိုင်ရန် သို့မဟုတ် ၎င်းတို့ကို လက်ရှိ project ထဲသို့ drag and drop (ဖိဆွဲ၍နေရာချခြင်း) သို့မဟုတ် double click မှတဆင့် ထည့်သွင်းရန် project items များကို browser ထဲရှိ အခြားသော items များကဲ့သို့ပင် တူညီစွာလုပ်ဆောင်ပေးပါသည်။ 

:guilabel:`Browser` panel ထဲရှိ element (တစ်စုံတစ်ခု၏ အရေးပါသည့်အစိတ်အပိုင်း သို့မဟုတ် ဝိသေသလက္ခဏာ) 
တစ်ခု၏ context menu ကို ၎င်းအပေါ်တွင် right-clicking ပြုလုပ်ခြင်းဖြင့် ဖွင့်နိုင်ပါသည်။ 

File system directory entries များအတွက် context menu သည် အောက်ပါတို့ကို ပံ့ပိုးပေးပါသည်- 

* :menuselection:`New -->` Select ပြုလုပ်ထားသည့် entry ထဲတွင် အောက်ပါတို့ကို ဖန်တီးရန်-
  * :guilabel:`Directory...`
  * :guilabel:`GeoPackage...`
  * :guilabel:`ShapeFile...`
* :guilabel:`Add as a Favorite`(Favourite တစ်ခုအဖြစ်ပေါင်းထည့်ခြင်း) - စိတ်ကြိုက် folders (favorite folders) များကို (:guilabel:`Rename favorite...`) အမည်ပြန်လည်ပြင်ဆင်နိုင်ပါသည်။ သို့မဟုတ် မည့်သည့်အချိန်တွင်မဆို (:guilabel:`Remove favorite`) ဖယ်ရှားနိုင်ပါသည်။ 
* :guilabel:`Hide from Browser` (Browser မှ ဖျောက်ထားခြင်း) - ဖျောက်ထားသည့် folders များကို မြင်တွေ့နိုင်အောင် :menuselection:`Settings --> Options --> Data Sources --> Hidden browser paths` setting တွင် အဖွင့်အပိတ်ပြုလုပ်နိုင်ပါသည်။ 
* :guilabel:`Fast Scan this Directory` (Directory ကို အမြန် scan လုပ်ခြင်း)
* :guilabel:`Open Directory` (Directory ကို ဖွင့်ခြင်း)
* :guilabel:`Open in Terminal` (Terminal အတွင်း ဖွင့်ခြင်း)
* :guilabel:`Properties...` (ဂုဏ်သတ္တိများ)
* :guilabel:`Directory Properties...` (Directory ဆိုင်ရာ ဂုဏ်သတ္တိများ)

Project ထဲတွင် layer များအဖြစ် ဆောင်ရွက်နိုင်သည့် leaf entries များအတွက် context menu တွင် supporting entries (ပံ့ပိုးပေးထားသည့် entries) များပါရှိမည်ဖြစ်ပါသည်။ 
ဥပမာ - non-database ၊ non-service-based vector ၊ raster နှင့် mesh data sources များအတွက်-
* :menuselection:`Export Layer --> To File...` (Layer ကို file အဖြစ်သို့ export လုပ်ခြင်း)
* :guilabel:`Add Layer to Project` (Project အတွင်းသို့ layer ထည့်သွင်းခြင်း)
* :guilabel:`Layer Properties` (Layer ၏ ဂုဏ်သတ္တိများ)
* :menuselection:`Manage --> Rename "<name of file>"...` သို့မဟုတ် :guilabel:`Delete "<name of file>"...` (File နာမည်များ အမည်ပြောင်းခြင်း သို့မဟုတ် ဖျက်ပစ်ခြင်း)
* :guilabel:`Show in Files` (Files တွင် ပြသခြင်း)
* :guilabel:`File Properties` (Files ၏ ဂုဏ်သတ္တိများ)

:guilabel:`Layer properties` entry ထဲတွင် အောက်ပါတို့ကို ရှာဖွေတွေ့ရှိနိုင်ပါသည် (Project ထဲသို့ layer များကို ထည့်သွင်းသည်နှင့်တစ်ပြိုင်နက် :ref:`vector <vector_properties_dialog>` နှင့် :ref:`raster <raster_properties_dialog>` layer properties များထဲတွင် တွေ့မြင်ရသည့်အရာများနှင့်ဆင်တူသည့်) -

* Layer အတွက် :guilabel:`Metadata`။ Metadata အုပ်စုများ - :guilabel:`Information from provider` (အကယ်၍ ဖြစ်နိုင်ပါက :guilabel:`Path` သည် အဆိုပါ ရင်းမြစ် (source) အတွက် hyperlink တစ်ခုဖြစ်မည်ဖြစ်ပါသည်)၊ :guilabel:`Identification` ၊ :guilabel:`Extent` ၊ :guilabel:`Access` ၊ :guilabel:`Fields` (vector layer များအတွက်) ၊ :guilabel:`Bands` (raster layer များအတွက်) ၊ :guilabel:`Contacts` ၊ :guilabel:`Links` (vector layer များအတွက်) ၊ :guilabel:`References` (raster layer များအတွက်) ၊ :guilabel:`History` ။
* :guilabel:`Preview` panel တစ်ခု
* Vector sources (:guilabel:`Attributes` panel ထဲတွင် ) များအတွက် attribute table  

:guilabel:`Browser` ကို အသုံးပြု၍ project ထဲသို့ layer တစ်ခုကို ထည့်သွင်းရန် -

#. အထက်တွင်ဖော်ပြထားသည့်အတိုင်း :guilabel:`Browser` ကို ဖွင့်ပါ။
   File system ၊ databases နှင့် web services များနှင့်အတူ browser tree တစ်ခုကို ပြသမည်ဖြစ်ပါသည်။ ၎င်းတို့မပေါ်လာခင်တွင် databases များနှင့်  web services များကို ချိတ်ဆက်ထားရန်လိုအပ်မည်ဖြစ်ပါသည်။ (သီးသန့်ကဏ္ဍများတွင်ကြည့်ပါ)
#. စာရင်းထဲတွင် layer ကို ရှာဖွေပါ။
#. Context menu ကိုအသုံးပြုပါ။ ၎င်း၏အမည်ကို double-click နှိပ်ပါ။ သို့မဟုတ် :ref:`map canvas <label_mapview>` ထဲသို့ drag-and-drop ပြုလုပ်ပါ။ Layer ကို လက်ရှိတွင် :ref:`Layers panel <label_legend>` ထဲသို့ ထည့်သွင်းသွားမည်ဖြစ်ပြီး map canvas (မြေပုံရေးဆွဲသည့်နေရာ) အပေါ်တွင်ကြည့်ရှုနိုင်ပါသည်။ 

   .. tip:: **QGIS project တစ်ခုကို browser မှ တိုက်ရိုက်ဖွင့်ပါ**  

    QGIS project တစ်ခုကို ၎င်း၏အမည်အပေါ်တွင် double-clicking နှိပ်ခြင်း သို့မဟုတ် map canvas ထဲသို့ drag-and-drop ပြုလုပ်ခြင်းဖြင့် browser မှ တိုက်ရိုက်ဖွင့်နိုင်ပါသည်။ 

File တစ်ခုကို ထည့်သွင်းလိုက်သည်နှင့်တစ်ပြိုင်နက် map navigation tools (မြေပုံ၏တည်နေရာနှင့် လမ်းကြောင်းများကို ထိန်းချုပ်သည့် ကိရိယာများ) များကို အသုံးပြု၍ ၎င်းနှင့်အနီးတဝိုက်ကို zoom (ချုံ့ခြင်း/ချဲ့ခြင်း) ပြုလုပ်နိုင်ပါသည်။ Layer တစ်ခု၏ style ကို ပြောင်းလဲပြင်ဆင်မှုများပြုလုပ်ရန် context menu မှ :menuselection:`Properties` ကို ရွေးချယ်ပြီး layer ၏ အမည်အပေါ်တွင်  double-clicking နှိပ်ခြင်း  သို့မဟုတ် legend (ရည်ညွှန်းချက်) ထဲရှိ အမည်ကို right-clicking ပြုလုပ်ခြင်းဖြင့် :guilabel:`Layer Properties` dialog ကို ဖွင့်ပါ။ Vector layer များအတွက် သင်္ကေတများသတ်မှတ်ခြင်းနှင့်သက်ဆိုင်သည့် နောက်ထပ်အချက်အလက်များအတွက် :ref:`vector_style_menu` section ကို ကြည့်ပါ။ 

Browser ထဲရှိ item တစ်ခုကို right-clicking ပြုလုပ်ခြင်းသည် အောက်ပါတို့ကို ကူညီမည်ဖြစ်ပါသည်-

* ဖိုင်တစ်ခု သို့မဟုတ် table (ဇယား) တစ်ခုအတွက်။ ၎င်း၏ metadata ကို ပြသပေးခြင်း သို့မဟုတ် ၎င်းကို project ထဲတွင်ဖွင့်ခြင်း လုပ်ဆောင်နိုင်ပါသည်။ Table များကို အမည်ပြန်လည်ပြင်ဆင်ခြင်း၊ ဖျက်ခြင်း သို့မဟုတ် ဖြတ်တောက်ခြင်း (truncated) ပြုလုပ်နိုင်သည်။
* Folder တစ်ခုအတွက် ၎င်းကို စိတ်ကြိုက်များ (favourites) ထဲတွင် bookmark (အမှတ်အသား) ပြုလုပ်ခြင်း သို့မဟုတ် browser tree ထဲမှ ၎င်းကိုဖျောက်ထားခြင်း လုပ်ဆောင်နိုင်ပါသည်။ မမြင်အောင်ဖျောက်ထားသည့် folders များကို :menuselection:`Settings --> Options --> Data Sources` tab  မှ စီမံခန့်ခွဲနိုင်ပါသည်။
* :ref:`spatial bookmarks <sec_bookmarks>` ကိုစီမံခန့်ခွဲခြင်း - bookmarks များကို ``XML`` files များအဖြစ်သို့ ဖန်တီးပေးခြင်း၊ export နှင့် import ပြုလုပ်ခြင်းများ လုပ်ဆောင်ပေးနိုင်ပါသည်။
* Database တစ်ခု သို့မဟုတ် web service တစ်ခုသို့ ချိတ်ဆက်ရန် ချိတ်ဆက်မှု (connection) တစ်ခုဖန်တီးပေးပါသည်။
* Schema (အစီအစဉ်တစ်ခု သို့မဟုတ် သီအိုရီတစ်ခုကို မော်ဒယ်တစ်ခုသို့မဟုတ် outline တစ်ခုအဖြစ်ကိုယ်စားပြုဖော်ပြချက်) တစ်ခုကို ပြန်လည်ဆန်းသစ်ခြင်း (refresh) ပြုလုပ်ခြင်း၊ အမည်ပြန်လည်ပေးခြင်း သို့မဟုတ် ဖျက်ပစ်ခြင်းများ လုပ်ဆောင်ပေးနိုင်ပါသည်။ 

File များကို databases ထဲသို့ import ပြုလုပ်ခြင်း သို့မဟုတ် schema/database တစ်ခုမှ အခြားတစ်ခုသို့ ရိုးရှင်းသည့် drag-and-drop ပြုလုပ်ခြင်းဖြင့် ဇယားများကို ကူးယူခြင်းများဆောင်ရွက်နိုင်သည်။ ဖိ၍ဆွဲနေစဉ် (dragging) အတွင်း  ကြာရှည်သည့် scrolling ပြုလုပ်ခြင်းကို ရှောင်ရှားရန် ဒုတိယ browser panel တစ်ခုရှိပါသည်။ File ကို select ပြုလုပ်ပြီး panel တစ်ခုမှ အခြားတစ်ခုသို့ drag-and-drop ပြုလုပ်ရုံသာဖြစ်ပါသည်။ 

.. _figure_browser_panels:

.. figure:: img/browser_panels.png
   :align: center

   ဘေးချင်းကပ်လျက်ရှိသည့် QGIS Browser panel များ


.. tip:: ** OS file browser မှ ရိုးရှင်းသည့် drag-and-drop ပြုလုပ်ခြင်းဖြင့် QGIS ထဲသို့ layers များကို ထည့်သွင်းပါ**

   Operating system file browser မှ :guilabel: `Layers Panel` ထဲသို့ သို့မဟုတ် map canvas ထဲသို့ drag-and-drop ပြုလုပ်ပြီး ဖိုင်(များ)ကို project ထဲသို့ ထည့်သွင်းနိုင်ပါသည်။ 

.. index:: DB Manager

The DB Manager (Database များစီမံခန့်ခွဲသည့်အရာ)
=================================================

:guilabel:`DB Manager` plugin  သည် QGIS (PostGIS ၊ SpatiaLite ၊ GeoPackage ၊ Oracle Spatial ၊ MS SQL Server ၊ Virtual layers) မှ ပံ့ပိုးထားသည့် spatial database format များကို ပေါင်းစပ်မှုများပြုလုပ်ခြင်း (integrating) နှင့် စီမံခန့်ခွဲခြင်း (managing) များပြုလုပ်ခြင်းတို့အတွက် အခြား tool တစ်ခုဖြစ်ပါသည်။ ၎င်းကို :menuselection:`Plugins --> Manage and Install Plugins...` menu မှတဆင့် အသက်ဝင်လာအောင် (activate) ဆောင်ရွက်နိုင်ပါသည်။ 

|dbManager| :sup:`DB Manager` plugin သည် ဖော်ပြပါ features (တစ်စုံတစ်ခု၏ ထူးခြားသော အရည်အချင်း သို့မဟုတ် အသွင်အပြင်တစ်ခု) အမျိုးမျိုးကို ပံ့ပိုးပေးထားပါသည်-

* Database များနှင့်ချိတ်ဆက်ပြီး ၎င်းတို့၏ဖွဲ့စည်းတည်ဆောက်ထားရှိမှုပုံစံ (structure) နှင့် ပါဝင်သည့်အကြောင်းအရာများ (contents) ကို ပြသသည်။
* Database များ၏ table များကို ကြိုတင်ကြည့်ရှုခြင်း (preview) လုပ်ဆောင်နိုင်သည်။
* Double-clicking ပြုလုပ်ခြင်း သို့မဟုတ် drag-and-drop ပြုလုပ်ခြင်းဖြင့် map canvas ထဲသို့ layer များကို ထည့်သွင်းနိုင်သည်။
* QGIS Browser သို့မဟုတ် အခြားသော database မှ database တစ်ခုထဲသို့ layer များကို ထည့်သွင်းနိုင်သည်။
* SQL queries များကို ဖန်တီးပြီး ၎င်းတို့၏ ထွက်ရှိလာသည့် output ကို map canvas ထဲသို့ထည့်သွင်းနိုင်သည်။
* :ref:`virtual layer <vector_virtual_layers>` များကိုဖန်တီးနိုင်သည်။ 

DB Manager ၏ စွမ်းဆောင်ရည် (DB Manager capabilities) များနှင့်သက်ဆိုင်သည့် နောက်ထပ်အချက်အလက်များကို :ref:`dbmanager` ထဲတွင် ရှာဖွေတွေ့ရှိနိုင်ပါသည်။ 

.. _figure_db_manager_bis:

.. figure:: img/db_manager.png
   :align: center

   DB Manager dialog


Provider-based loading tools (Provider အခြေပြုထည့်သွင်းထားသည့် ကိရိယာတန်ဆာပလာများ)
===================================================================================

Layers များ ထည့်သွင်းရန် QGIS မှ ပံ့ပိုးထားသည့် အဓိက tools များဖြစ်သော Browser Panel နှင့်  DB Manager များအပြင် data provider များနှင့်သက်ဆိုင်သည့် သီးခြား tools များကိုလည်း ရှာဖွေ့တွေ့ရှိနိုင်ပါသည်။

.. note::

  :ref:`External plugins <plugins>` အချို့သည်လည်း QGIS ထဲတွင် သီးသန့် (specific) format files များကို ဖွင့်ရန် tools များကို ပံ့ပိုးပေးထားပါသည်။


.. index:: Loading vector, Loading raster
.. index:: ODBC, OGDI, Esri Personal Geodatabase, MySQL
.. _loading_file:

Loading a layer from a file (ဖိုင်တစ်ခုမှ layer တစ်ခုကို ထည့်သွင်းခြင်း)
-------------------------------------------------------------------------

ဖိုင်တစ်ခုမှ layer တစ်ခုကို ထည့်သွင်းရန်-

#. :guilabel:`Data Source Manager` dialog ထဲရှိ layer type tab ကိုဖွင့်ပါ။ ဆိုလိုသည်မှာ |dataSourceManager| :sup:`Open Data Source Manager` button (သို့မဟုတ် :kbd:`Ctrl+L` ကိုနှိပ်ပါ) ကို click နှိပ်ပြီး target tab ကို ဖွင့်ပါ။ သို့မဟုတ်-

   * Vector data အတွက် (ဥပမာ- GML ၊ ESRI Shapefile ၊ Mapinfo and DXF layers) - :kbd:`Ctrl+Shift+V` ကိုနှိပ်ပါ။ :menuselection:`Layer --> Add Layer -->` |addOgrLayer| :guilabel:`Add Vector Layer` menu option ကို select ပြုလုပ်ပါ။ သို့မဟုတ် |addOgrLayer| :sup:`Add Vector Layer` toolbar button ကို click နှိပ်ပါ။ 

     .. _figure_vector_add:

     .. figure:: img/addvectorlayerdialog.png
        :align: center

        Vector Layer Dialog ထည့်သွင်းခြင်း

   * Raster data အတွက် (ဥပမာ- GeoTiff ၊ MBTiles ၊ GRIdded Binary နှင့် DWG layers)- :kbd:`Ctrl+Shift+R` ကိုနှိပ်ပါ။ :menuselection:`Layer --> Add Layer -->`|addRasterLayer| :guilabel:`Add Raster Layer` menu option ကို select ပြုလုပ်ပါ။  
     သို့မဟုတ် |addRasterLayer| :sup:`Add Raster Layer` toolbar button ကို click နှိပ်ပါ။ 

     .. _figure_raster_add:

     .. figure:: img/addrasterlayerdialog.png
        :align: center

        Raster Layer Dialog ထည့်သွင်းခြင်း

#. |radioButtonOn| :guilabel:`File` source type ကို အမှန်ခြစ်ပါ။ 
#. :guilabel:`...` :sup:`Browse` button အပေါ်တွင် Click နှိပ်ပါ။
#. File system ကို navigate (လမ်းညွှန်မှု) ပြုလုပ်ပြီး supported data source (ပံ့ပိုးပေးထားသည့် ဒေတာရင်းမြစ်) တစ်ခုကို ထည့်သွင်းပါ။ တစ်ချိန်တည်းတွင် တစ်ခုထက်ပိုသော layer များကို :kbd:`Ctrl` key ကိုဖိထား၍ dialog ထဲရှိ multiple items များအပေါ်တွင် ကလစ်နှိပ်ခြင်းဖြင့်ဖြစ်စေ သို့မဟုတ် range (အပိုင်းအခြား) ထဲရှိ ပထမဆုံးနှင့်နောက်ဆုံး items များကို ကလစ်နှိပ်ထားပြီး items များ၏ range ကို ပြုလုပ်ရန်အတွက် :kbd:`Shift` key  ကို ဖိထားခြင်းဖြင့်ဖြစ်စေ ထည့်သွင်းနိုင်ပါသည်။ ကောင်းစွာစမ်းသပ်ခြင်းခံထားရသည့် format များသာ formats filter တွင် ပေါ်လာမည်ဖြစ်ပါသည်။ အခြားသော format များအား ``All files`` (pull-down menu ထဲရှိ ထိပ်ဆုံး item) ကို select ပြုလုပ်ခြင်းဖြင့် ထည့်သွင်းနိုင်ပါသည်။
#. :guilabel:`Data Source Manager` dialog ထဲသို့ select ပြုလုပ်ထားသည့် ဖိုင်ကို ထည့်သွင်းရန် :guilabel:`Open` ကိုနှိပ်ပါ။ 

   .. _figure_vector_layer_open_options:

   .. figure:: img/openoptionsvectorlayer.png
      :align: center

      Open options (ဖွင့်ရန်နည်းလမ်းများ) များနှင့်အတူ Shapefile တစ်ခုကိုထည့်သွင်းခြင်း 

#. QGIS ထဲတွင် ဖိုင်ကို ထည့်ရန်နှင့် ၎င်းတို့ကို map view (မြေပုံမြင်ကွင်း) ထဲတွင် ပြသရန် :guilabel:`Add` ကို နှိပ်ပါ။ :numref:`figure_vector_loaded` သည် :file:`alaska.shp` file ကို ထည့်သွင်းပြီးနောက် QGIS ကို ပြသပါသည်။ 

   .. _figure_vector_loaded:

   .. figure:: img/shapefileloaded.png
      :align: center

      Alaska ၏ Shapefile ထည့်သွင်းထားသည့် QGIS

.. note::

 Vector နှင့် raster ဖိုင်များကို ထည့်သွင်းရန်အတွက် GDAL driver သည် open options (ဖွင့်ရန်နည်းလမ်းများ) များကို သတ်မှတ်ရန် လုပ်ဆောင်ပေးပါသည်။ ၎င်းကို ဖိုင်တစ်ခု select ပြုလုပ်ပြီးသည့်အခါတွင် ပြသမည်ဖြစ်ပါသည်။ နည်းလမ်း (Options) များကို https://gdal.org/drivers/vector/ ၊ https://gdal.org/drivers/raster တွင် အသေးစိတ်ဖော်ပြထားပြီး အကယ်၍ QGIS ထဲတွင် ဖိုင်တစ်ခုသည် select ပြုလုပ်ခြင်းခံရပါက hyperlink ပါဝင်သည့် စာသားတစ်ခုသည် select ပြုလုပ်ခြင်းခံရသည့် ဖိုင်အမျိုးအစား၏ documentation (မှတ်တမ်းမှတ်ရာ) ဆီသို့ တိုက်ရိုက်ရောက်ရှိသွားစေမည်ဖြစ်ပါသည်။ 

.. note::
 MapInfo (ဥပမာ- :file:`.tab`) သို့မဟုတ် Autocad (:file:`.dxf`) ကဲ့သို့သော အချို့ format များသည် မတူညီသည့် geometry အမျိုးအစားများကို ဖိုင်တစ်ခု (single file) တွင် ပေါင်းစပ်ခြင်း (mixing) ကို ခွင့်ပြုသောကြောင့် အဆိုပါ datasets များကို ထည့်သွင်းခြင်းသည် layer တစ်ခုစီအလိုက် geometry တစ်ခုရရှိစေရန်အလို့ငှာ အသုံးပြုမည့် geometries များကို select ပြုလုပ်ရန်အတွက် dialog တစ်ခုကို ပွင့်စေပါသည်။

.. index:: ArcInfo Binary Coverage, Tiger Format, UK National Transfer Format
.. index:: US Census Bureau

|addOgrLayer| :sup:`Add Vector Layer` နှင့် |addRasterLayer| :sup:`Add Raster Layer` tabs များသည် :guilabel:`File` ထက် source types များမှ layers များ ထည့်သွင်းခြင်းကို ခွင့်ပြုပါသည်- 

* ``ArcInfo Binary Coverage`` ၊ ``UK. National Transfer Format`` ကဲ့သို့သော သီးသန့် vector formats အပြင် ``US Census Bureau`` ၏ raw TIGER format  သို့မဟုတ် ``OpenfileGDB`` များကို ထည့်သွင်းနိုင်ပါသည်။ ထိုသို့ဆောင်ရွက်ရန် |radioButtonOn| :guilabel:`Directory` ကို :guilabel:`Source type` အဖြစ် select ပြုလုပ်ပါ။ ဤဖြစ်ရပ်တွင် :guilabel:`...` :sup:`Browse` ကို နှိပ်ပြီးနောက် dialog ထဲတွင် directory တစ်ခုကို select ပြုလုပ်နိုင်ပါသည်။ 
* |radioButtonOn| :guilabel:`Database` source အမျိုးအစား ဖြင့် လက်ရှိရှိနေသည့် database connection တစ်ခုကို select ပြုလုပ်ခြင်း သို့မဟုတ် select ပြုလုပ်ထားသည့် database အမျိုးအစားအတွက် database connection တစ်ခုကို ဖန်တီးခြင်း ဆောင်ရွက်နိုင်ပါသည်။ ဖြစ်နိုင်သည့် database အမျိုးအစားအချို့မှာ ``ODBC`` ၊ ``Esri Personal Geodatabase`` ၊ ``MS SQL Server`` အပြင် ``PostgreSQL`` သို့မဟုတ် ``MySQL`` တို့ဖြစ်ပါသည်။ 

  :guilabel:`New` button ကို နှိပ်ခြင်းသည် :guilabel:`Create a New OGR Database Connection` dialog ကိုပွင့်စေပြီး ၎င်း၏ သတ်မှတ်ချက် (parameters) များသည် :ref:`vector_create_stored_connection` ထဲတွင် ရှာဖွေတွေ့ရှိနိုင်သည်များထဲမှ ဖြစ်ပါသည်။ :guilabel:`Open` ကို နှိပ်ခြင်းသည် ရရှိနိုင်သည့် ဇယားများမှ select ပြုလုပ်ခြင်းကိုခွင့်ပြုမည်ဖြစ်ပါသည်။ ဥပမာ- PostGIS လုပ်ဆောင်နိုင်သော databases များ။ 

* |radioButtonOn| :guilabel:`Protocol: HTTP(S), cloud, etc.` source အမျိုးအစားသည် locally (ကွန်ပျူတာထဲတွင်သိမ်းဆည်းထားသည်) သို့မဟုတ် network တွင် သိမ်းဆည်းထားသည့် data (အများသူငှာကြည့်ရှုဝင်ရောက်ကြည့်ရှုသုံးစွဲနိုင်သည်(publicly accessible))  သို့မဟုတ် စီးပွားရေးလုပ်ငန်းသုံး cloud storage services များ၏ private buckets (Buckets များသည်ဒေတာများကို သိမ်းထားသည့် အခြေခံ containers များဖြစ်ပြီး Cloud Storage တွင် သိမ်းဆည်းသမျှအားလုံးသည် bucket တစ်ခုထဲတွင် ပါဝင်ရမည်ဖြစ်ပါသည်) များတွင် သိမ်းဆည်းထားသည့် data ကိုပွင့်စေပါသည်။ ပံ့ပိုးပေးထားသည့် protocol အမျိုးအစားများမှာ-

  * ``HTTP/HTTPS/FTP`` ၊ :guilabel:`URI` တစ်ခုနှင့်အတူ၊ လိုအပ်ပါက :ref:`authentication <authentication_index>` တစ်ခု။
  * ``AWS S3`` ၊ ``Google Cloud Storage`` ၊ ``Microsoft Azure Blob`` ၊ ``Alibaba OSS Cloud`` ၊ ``Open Stack Swift Storage`` ကဲ့သို့သော Cloud storage။ :guilabel:`Bucket or container` နှင့် :guilabel:`Object key` များဖြည့်သွင်းရန်လိုအပ်ပါသည်။       
  * ``CouchDB`` database အပေါ်တွင်အခြေခံထားသည့် သို့မဟုတ် ``GeoJSON`` သို့မဟုတ် ``GEOJSON - Newline Delimited`` format များကိုအသုံးပြုပြီး OGC ``WFS 3`` (စမ်းသပ်ဆဲ) ကို ပံ့ပိုးပေးနေသည့် ဝန်ဆောင်မှု။ ရွေးချယ်နိုင်သော (optional) :ref:`authentication <authentication_index>` နှင့်အတူ :guilabel:`URI` တစ်ခုလိုအပ်ပါသည်။ 
  * Vector source အမျိုးအစားများအားလုံးအတွက် :guilabel:`Encoding` ကို သတ်မှတ်ရန် သို့မဟုတ် :menuselection:`Automatic -->` setting ကို အသုံးပြုရန် ဖြစ်ကောင်းဖြစ်နိုင်ပါသည်။ 

.. _mesh_loading: 

Loading a mesh layer (Mesh layer တစ်ခုကို ထည့်သွင်းခြင်း)
----------------------------------------------------------

Mesh တစ်ခုဆိုသည်မှာ ယာယီ (temporal) နှင့် အခြားသော (components) အစိတ်အပိုင်းများပါရှိသည့် ဖွဲ့စည်းမှုပုံစံနည်းစနစ်တကျမရှိသောဇယားကွက် (unstructured grid) တစ်ခုဖြစ်ပါသည်။ Spatial component ထဲတွင် 2D သို့မဟုတ် 3D space ထဲရှိ vertices (မျဉ်းအဆစ်များ) ၊ edges (အစွန်များ) နှင့် faces (မျက်နှာများ) များပါရှိသည့် အစုအဝေးတစ်ခုပါဝင်ပါသည်။ Mesh layer များနှင့်သက်ဆိုင်သည့် နောက်ထပ်အချက်အလက်များကို :ref:`label_meshdata` တွင် ကြည့်ရှုနိုင်ပါသည်။

Mesh layer တစ်ခုကို QGIS ထဲသို့ထည့်သွင်းရန်-

#. :menuselection:`Layer -->` menu မှ ၎င်းကို select ပြုလုပ်ခြင်း သို့မဟုတ် |dataSourceManager| :sup:`Open Data Source Manager` button ကို click ပြုလုပ်ခြင်းဖြင့် :menuselection:`Data Source Manager` dialog ကို ဖွင့်ပါ။
#. Left panel (ဘယ်ဘက်ဘောင်) အပေါ်ရှိ |addMeshLayer| :guilabel:`Mesh` tab ကို ဖွင့်ပါ။
#. ဖိုင်ကို select ပြုလုပ်ရန်  :guilabel:`...` :sup:`Browse` ကို နှိပ်ပါ။ 
   :ref:`Various formats <mesh_supported_formats>` များကို ပံ့ပိုးပေးထားပါသည်။
#. ဖိုင်ကို select ပြုလုပ်ပြီး :guilabel:`Add` ကို နှိပ်ပါ။
   Layer ကို native mesh rendering (မူရင်း mesh ပုံဖော်ခြင်း) အသုံးပြုပြီး ထည့်သွင်းသွားမည်ဖြစ်ပါသည်။
#. အကယ်၍ select ပြုလုပ်ထားသည့် ဖိုင်တွင် mesh layers များစွာ ပါဝင်နေပါက 
   ထည့်သွင်းရန်အတွက် sublayer (layer အခွဲများ) များကို ရွေးချယ်ရန် dialog တစ်ခုဖြင့် သတိပေး (prompt) သွားမည်ဖြစ်ပါသည်။
   ရွေးချယ်ခြင်း (selection) ကိုပြုလုပ်ပြီး :guilabel:`OK` ကိုနှိပ်ပါ။ Layers များကို native mesh rendering အသုံးပြုပြီး ထည့်သွင်းသွားမည်ဖြစ်ပါသည်။ ၎င်းတို့ကို group(အုပ်စု) တစ်ခုထဲတွင်လည်း ထည့်သွင်းရန် ဖြစ်ကောင်းဖြစ်နိုင်ပါသည်။ 

   
.. _figure_mesh_datasource_manager:

.. figure:: img/mesh_datasource_manager.png
   :align: center

   Data Source Manager (ဒေတာများကိုစီမံခန့်ခွဲရာနေရာ) ထဲရှိ Mesh tab 


.. index:: CSV, Delimited text files
   see: Comma Separated Values; CSV
.. _vector_loading_csv:


Importing a delimited text file (Delimited text file တစ်ခုကို import ပြုလုပ်ခြင်း) 
------------------------------------------------------------------------------------

(Delimited text file ဆိုသည်မှာ ၎င်းတွင် line တစ်ခုချင်းစီသည် စာအုပ်တစ်အုပ်၊ ကုမ္ပဏီတစ်ခု သို့မဟုတ် အခြားအရာတစ်ခုကို ကိုယ်စားပြုပြီး line တစ်ခုချင်းစီတွင် delimiter ဖြင့် ပိုင်းခြားထားသော fields များပါရှိသည့် data ကိုသိမ်းဆည်းရန် အသုံးပြုသည့် စာသားဖိုင်တစ်ခု ဖြစ်ပါသည်။)

Delimited text files (ဥပမာ :file:`.txt` ၊ :file:`.csv` ၊ :file:`.dat` ၊ :file:`.wkt`) များကို အထက်တွင်ဖော်ပြထားသည့် tools (ကိရိယာတန်ဆာပလာများ) များအသုံးပြုပြီး ထည့်သွင်းနိုင်ပါသည်။ ဤနည်းအားဖြင့် ၎င်းတို့သည် ရိုးရှင်းသောဇယားများ (simple tables) အဖြစ်  ပေါ်လာမည်ဖြစ်သည်။ တစ်ခါတစ်ရံတွင် delimited text files များတွင် ပုံဖော်ပြသ (visualize) လိုသည့် coordinates / geometries များ ပါဝင်နိုင်ပါသည်။ ၎င်းသည် |addDelimitedTextLayer|:guilabel:`Add Delimited Text Layer` ကို ဒီဇိုင်းရေးဆွဲထားရသည့် အချက်ပင်ဖြစ်သည်။ 

#. :guilabel:`Data Source Manager` dialog ကိုဖွင့်ရန် |dataSourceManager| :sup:`Open Data Source Manager` icon ကို click နှိပ်ပါ။
#. |addDelimitedTextLayer| :guilabel:`Delimited Text` tab ကို ဖွင့်ပါ။
#. :guilabel:`...` :sup:`Browse` button ကိုနှိပ်ပြီး import ပြုလုပ်မည့် delimited text file (ဥပမာ- :file:`qgis_sample_data/csv/elevp.csv`) ကို Select ပြုလုပ်ပါ။
#. :guilabel:`Layer name` field ထဲတွင် project ထဲရှိ layer အတွက် အသုံးပြုမည့် အမည်ကို ထည့်သွင်းပံ့ပိုးပါ။ (ဥပမာ- :file:`Elevation`)
#. Dataset ကို တွေ့ရှိရန်နှင့် လိုအပ်ချက်များကို ဖြည့်ဆည်းရန် အောက်တွင်ပြထားသည့်အတိုင်း setting များကို ပြင်ဆင်သတ်မှတ် (Configure) ပါ။ 


.. _figure_delimited_text:

.. figure:: img/delimited_text_dialog.png
   :align: center

   Delimited Text Dialog

File format (ဖိုင်ပုံစံ) 
..........................

ဖိုင်ကို select ပြုလုပ်ပြီးသည်နှင့်တပြိုင်နက် QGIS သည် fields နှင့် rows များကို သတ်မှတ်ပြီး လတ်တလောတွင် အများဆုံးအသုံးပြုထားသည့် delimiter(စာသားများကို ပိုင်းခြားသည့် တစ်ခုသို့မဟုတ် တစ်ခုထက်ပိုသည့် character) ဖြင့် ဖိုင်ကို ခွဲခြမ်းစိတ်ဖြာခြင်း (parse) ပြုလုပ်ရန် ကြိုးပမ်းမည်ဖြစ်ပါသည်။ QGIS အနေဖြင့် ဖိုင်ကို တိကျမှန်ကန်စွာခွဲခြမ်းစိတ်ဖြာနိုင်ရန်အတွက် မှန်ကန်သည့် delimiter ကို select ပြုလုပ်ရန်မှာ အလွန်ပင်အရေးကြီးပါသည်။ Delimiter တစ်ခုကို အောက်ပါတို့အကြားတွင် ရွေးချယ်ခြင်းဖြင့် သတ်မှတ်နိုင်ပါသည်- 

* |radioButtonOn|:guilabel:`CSV (comma separated values)` comma character (,) ကို အသုံးပြုရန်။ 
* |radioButtonOff|:guilabel:`Regular expression delimiter` နှင့် :guilabel:`Expression` field ထဲတွင် စာသား (text) ကို ထည့်သွင်းပါ။ ဥပမာ- delimiter ကို tab သို့ပြောင်းလဲရန် ``\t`` ကို (၎င်းကို tab character အတွက် ပုံမှန်ဖော်ပြချက်များ (regular expressions) တွင်အသုံးပြုပါသည်) အသုံးပြုပါ။
* |radioButtonOff|:guilabel:`Custom delimiters` ၊ ``comma`` ၊ ``space`` ၊ ``tab`` ၊ ``semicolon`` ၊ .... ကဲ့သို့သော ကြိုတင်သတ်မှတ်ထားသည့် (predefined) delimiters များထဲမှ ရွေးချယ်ခြင်း 


Records and fields (မှတ်တမ်းများ နှင့် field များ)
...................................................

Data recognition (Data recognition ဆိုသည်မှာ capture ပြုလုပ်လိုသည့် field များကို နေရာချထားပြီး ၎င်းတို့ကို character-based data များအဖြစ်သို့ပြောင်းလဲသည့်အဆင့်ဖြစ်ပါသည်) အတွက် အဆင်ပြေသည့် အခြားနည်းလမ်းများကို အသုံးပြုနိုင်ပါသည်- 

* :guilabel:`Number of header lines to discard` - ပထမဆုံး lines များသည် လိုင်းအလွတ်များ (blank lines) သို့မဟုတ် အခြားသော formatting များ ဖြစ်နေသည့်အတွက် Import ထဲတွင် ဖိုင်မှ ပထမဆုံး line များကို ရှောင်ရှားလိုသည့်အခါတွင် အဆင်ပြေစေပါသည်။ 
* |checkbox|:guilabel:`First record has field names` - ပထမဆုံး line ထဲရှိ တန်ဖိုးများ (values) ကို field names (field အမည်များ) များအဖြစ်သို့အသုံးပြုပါသည်။ ထိုသို့မဟုတ်ပါက QGIS သည် field အမည်များကို  ``field_1``, ``field_2``... စသည်ဖြင့် အသုံးပြုပါသည်။
* |checkbox|:guilabel:`Detect field types` - Field type (field အမျိုးအစား) ကို အလိုအလျောက်အသိအမှတ်ပြု (recognize) သည်။ အကယ်၍ uncheck ပြုလုပ်ထားပါက attributes အားလုံးကို text(စာသား) fields များအဖြစ် ပြုမှုဆောင်ရွက်မည်ဖြစ်သည်။ 
* |checkbox|:guilabel:`Decimal separator is comma` - Decimal separator (ဒဿမကိန်း အခွဲအခြား) ကို comma တစ်ခုဖြစ်စေရန် တွန်းအားပေးဖြစ်ပေါ်စေပါသည်။
* |checkbox|:guilabel:`Trim fields` - Field များမှ leading and trailing spaces (ဖိုင်တစ်ခုသို့မဟုတ် folder တစ်ခု၏ အမည်၏ အရှေ့နှင့်အနောက်ရှိ space character) များကို trim (မလိုအပ်သည်များကိုဖြတ်ထုတ်ခြင်း)  ပြုလုပ်ခြင်းကိုခွင့်ပြုသည်။ 
* |checkbox|:guilabel:`Discard empty fields` (လွတ်နေသော field များကို ဖယ်ထုတ်ခြင်း)
* :guilabel:`Custom boolean literals` - Boolean values (TRUE သို့မဟုတ် FALSE ဆိုသည့်တန်ဖိုးအား ကိုယ်စားပြုဖော်ပြသည့်တန်ဖိုး) များအဖြစ်တွေ့ရှိရမည်ဖြစ်သည့် စိတ်ကြိုက် string (programming အသုံးပြုသည့် ဒေတာအမျိုးအစား၊ နံပါတ်များထက် စာသားကို ကိုယ်စားပြုရန် အသုံးပြုသည်) တစ်စုံကို ထည့်သွင်းခြင်းအား ခွင့်ပြုသည်။ 


Field type detection (Field အမျိုးအစားအား ရှာဖွေဖော်ထုတ်ခြင်း)
...............................................................

QGIS သည် ရွေးချယ်နိုင်သော sidecar (ပင်မအက်ပလီကေးရှင်းနှင့်အတူယှဉ်တွဲရှိသည့် ဝန်ဆောင်မှုများ သို့မဟုတ် လုပ်ငန်းစဉ်များ) CSVT file (`GeoCSV specification <https://giswiki.hsr.ch/GeoCSV#CSVT_file_format_specification>`_ တွင်ကြည့်ပါ) ၏ အကြောင်းအရာများကို စစ်ဆေး (examining) ပြီး တန်ဖိုးအားလုံးသည် မည်သည့်အမှား (errors) မျိုးမျှမပါဝင်ဘဲ အမှန်တကယ်ပြောင်းလဲခြင်းပြုလုပ်နိုင်သည်ကို သေချာစေရန် ဖိုင်တစ်ခုလုံးကို scanning ပြုလုပ်ခြင်းဖြင့် field အမျိုးအစားများကို အလိုအလျောက်ရှာဖွေဖော်ထုတ်ရန် ကြိုးပမ်းမည်ဖြစ်သည်။ (အကယ်၍ |checkbox|:guilabel:`Detect field types` ကို အမှန်ခြစ်ထားပါက) fall-back field (ပြန်လည်ရရှိသည့် field) အမျိုးအစားသည် စာသား (text) ဖြစ်ပါသည်။ 

ရှာဖွေတွေ့ရှိသည့် field အမျိုးအစား သည် sample data preview table (နမူနာ data ကို ကြိုတင်ကြည့်ရှုနိုင်သည့်ဇယား) ထဲရှိ field အမည်အောက်တွင် ပေါ်လာမည်ဖြစ်ပြီး လိုအပ်ပါက ကိုယ်တိုင် (manually) ဖြင့် ပြောင်းလဲပြင်ဆင်မှုများပြုလုပ်နိုင်ပါသည်။ 

အောက်ဖော်ပြပါ field အမျိုးအစားများကို ပံ့ပိုးပေးထားပါသည်-

* ``Boolean`` - Boolean values (boolean တန်ဖိုးများ) အဖြစ်သို့ အဓိပ္ပာယ်ဖွင့်ဆိုထားသည့် case-insensitive (စာလုံးအကြီးအသေးအတိုင်း အတိအကျဖြစ်ရန်မလိုသော) literal couples (case-insensitive literal couples များအား code များကို ဖတ်ရှုရန်နှင့်စီမံခန့်ခွဲရာတွင်ပိုမိုအဆင်ပြေစေရန် programming languages များတွင် အသုံးပြုလေ့ရှိပါသည်။) များမှာ  ``1``/ ``0`` ၊ ``true``/ ``false`` ၊ ``t``/ ``f`` ၊ ``yes``/ ``no`` တို့ဖြစ်ပါသည်။
* ``Whole Number (integer)`` (ကိန်းပြည့်)
* ``Whole Number (integer - 64 bit)`` (ကိန်းပြည့် - 64 bit)
* ``Decimal Number`` - ဒဿမနှစ်နေရာအထိ တိကျသော floating point number (ဒဿမအမှတ်များပါဝင်သည့် အပေါင်းသို့မဟုတ် အနုတ်ကိန်းပြည့်များ) 
* ``Date`` (ရက်စွဲ)
* ``Time`` (အချိန်)
* ``Date and Time`` (ရက်စွဲနှင့်အချိန်)
* ``Text`` (စာသား)


Geometry definition (Geometry အဓိပ္ပာယ်ဖွင့်ဆိုသတ်မှတ်ချက်)
............................................................

ဖိုင်ကို ခွဲခြမ်းစိတ်ဖြာသည်နှင့်တစ်ပြိုက်နက် :guilabel:`Geometry definition` ကို အောက်ပါများအဖြစ်သို့ သတ်မှတ်ပါ-


* |radioButtonOn|:guilabel:`Point coordinates` နှင့် အကယ်၍ layer သည် point geometry အမျိုးအစားဖြစ်ပြီး ထိုကဲ့သို့သော field များပါဝင်ပါက :guilabel:`X field` ၊ :guilabel:`Y field` ၊ :guilabel:`Z field`(3-dimensional data အတွက်) နှင့် :guilabel:`M field` (အတိုင်းအတာများကို တိုင်းတာရန်အတွက်) ကိုထည့်သွင်းပါ။ အကယ်၍ coordinates (ကိုဩဒိနိတ်များ) ကို degrees/minutes/seconds (ဒီဂရီများ/မိနစ်များ/စက္ကန့်များ) အဖြစ်သို့ သတ်မှတ်ထားပါက |checkbox|:guilabel:`DMS coordinates` checkbox ကို activate (အသက်ဝင်အောင်ဆောင်ရွက်ခြင်း) ပြုလုပ်ပါ။ |setProjection|:sup:`Select CRS` widget ကိုအသုံးပြု၍ သင့်လျော်သည့် :guilabel:`Geometry CRS` ကိုထည့်သွင်းပါ။
* Spatial information (Spatial information ဆိုသည်မှာ တည်နေရာ၊ လူများနှင့် လှုပ်ရှားမှုများအကြားရှိ ဒစ်ဂျစ်တယ်ချိတ်ဆက်မှုဖြစ်ပါသည်) ကို WKT အဖြစ်ကိုယ်စားပြုဖော်ပြထားပါက |radioButtonOn|:guilabel:`Well known text (WKT)` option - WKT geometry ပါဝင်သည့် :guilabel:`Geometry field` ကို select ပြုလုပ်ပြီး သင့်လျော်သည့် :guilabel:`Geometry field` ကို ရွေးချယ်ပါ။ သို့မဟုတ် QGIS ကို ၎င်းအား အလိုအလျောက်ရှာဖွေတွေ့ရှိခြင်း (auto-detect) ဆောင်ရွက်ရန် ခွင့်ပြုပါ။
  :sup:`Select CRS` widget ကို အသုံးပြု၍ သင့်လျော်သည့် :guilabel:`Geometry CRS` ကိုအသုံးပြုပါ။ 
* အကယ်၍ ဖိုင်တွင် non-spatial data ပါဝင်ပါက |radioButtonOn| :guilabel:`No eometry (attribute only table)` ကို activate ပြုလုပ်ပါ။ ၎င်းကို ပုံမှန်ဇယား (ordinary table) တစ်ခုအဖြစ် ထည့်သွင်းသွားမည်ဖြစ်ပါသည်။

Layer settings (Layer အပြင်အဆင်များ)
.....................................

အပိုဆောင်းအနေဖြင့် အောက်ပါတို့ကိုဆောင်ရွက်နိုင်ပါသည်-

* |checkbox|:guilabel:`Use spatial index` - Features များကို spatially selecting (spatial အရ ရွေးချယ်ခြင်း) ပြုလုပ်ခြင်းနှင့် ပြသခြင်း ဆိုင်ရာ စွမ်းဆောင်ရည် (performance) ကိုမြှင့်တင်ရန်။
* |checkbox|:guilabel:`Use subset index` - :ref:`subset filters <vector_query_builder>` ၏ စွမ်းဆောင်ရည်(performance) ကိုမြှင့်တင်ရန် (layer properties များထဲတွင်သတ်မှတ်ထားသည့်အခါ)။
* |checkbox|:guilabel:`Watch file` - QGIS ကို အသုံးပြုနေစဉ်အတွင်း အခြားသော application များကြောင့် ဖိုင်တွင် အပြောင်းအလဲများဖြစ်ပွားသည်ကို စောင့်ကြည့်ရန်။ 

အဆုံးတွင် map (မြေပုံ)ထဲသို့ layer ကိုထည့်သွင်းရန် :guilabel:`Add` ကို click  နှိပ်ပါ။
နမူနာတွင် ``Elevation`` ဟုအမည်တွင်သည့် point layer တစ်ခုကို project ထဲသို့ ထည့်သွင်းပြီး QGIS ရှိ အခြားသော map layer (မြေပုံ layer) ကဲ့သို့ ပြုမူဆောင်ရွက်ပါ။
ဤ layer သည် :file:`.csv` source file (၎င်းကို ချိတ်ဆက်ထားသည့်) ပေါ်ရှိ query တစ်ခု၏ ရလဒ်ဖြစ်ပြီး disk အပေါ်တွင် spatial layer တစ်ခုကို ရရှိရန် :ref:`to be saved <general_saveas>` ကို လိုအပ်မည်ဖြစ်ပါသည်။ 

Sample Data (နမူနာဒေတာ)
........................

ခွဲခြမ်းစိတ်ဖြာခြင်းဆိုင်ရာဂုဏ်သတ္တိများ (parser properties) ကို သတ်မှတ်ထားပါက sample data preview (နမူနာဒေတာအားကြိုတင်ကြည့်ရှုခြင်း) သည် အသုံးပြုထားသည့် settings နှင့်အညီ update ပြုလုပ်မည်ဖြစ်ပါသည်။ 

Sample Data Table (နမူနာဒေတာဇယား) တွင်လည်း အလိုအလျောက်ဆုံးဖြတ်သတ်မှတ်ထားသည့် column အမျိုးအစားများကို ပြန်လည်ပြင်ဆင်ရေးသား (override) နိုင်ပါသည်။ 


.. _import_dxfdwg:

Importing a DXF or DWG file (DXF သို့မဟုတ် DWG file တစ်ခုကို Import ပြုလုပ်ခြင်း)
----------------------------------------------------------------------------------

:file:`DXF` နှင့်  :file:`DWG` files များကို Browser Panel မှ ရိုးရှင်းသည့် drag-and-drop ပြုလုပ်ခြင်းဖြင့် QGIS ထဲသို့ ထည့်သွင်းနိုင်ပါသည်။ Project ထဲသို့ ထည့်သွင်းလိုသည့် sub-layers (layerအခွဲများ) များကို select ပြုလုပ်ရန် အသိပေးမည်ဖြစ်ပါသည်။ Layers များကို ကြုံရာ style properties (စတိုင်ဂုဏ်သတ္တိများ) များဖြင့် ထည့်သွင်းသွားမည်ဖြစ်ပါသည်။ 

.. note:: အမျိုးမျိုးသော geometry အမျိုးအစားများ (point ၊ line နှင့်/သို့ polygon) ပါဝင်သော DXF files များအတွက် layer များ၏ အမည်ကို  *<filename.dxf> entities <geometry type>* အဖြစ် ထုတ်လုပ် (generate) သွားမည်ဖြစ်ပါသည်။ 

QGIS တွင် dxf/dwg ဖိုင်ဖွဲ့စည်းတည်ဆောက်ပုံနှင့် ၎င်း၏ သင်္ကေတများ (symbology) ကို သိမ်းထားရန်အတွက် သီးသန့် :menuselection:`Project --> Import/Export --> Import Layers from DWG/DXF...` tool ကို အသုံးပြုလိုမည်ဖြစ်ပါသည်။ ၎င်း tool သည် ဖော်ပြပါတို့ကို ခွင့်ပြုပေးပါသည်- 

#. Drawing file (ပုံဆွဲသားထားသည့်ဖိုင်) မှ element များကို GeoPackage database တစ်ခုထဲသို့ import ပြုလုပ်ရန်။ 
#. Import ပြုလုပ်ထားသည့် element များကို Project ထဲသို့ ထည့်သွင်းရန်။ 

:guilabel:`DWG/DXF Import` dialog တွင် drawing file (ပုံဆွဲသားထားသည့်ဖိုင်) ပါ အကြောင်းအရာများ (contents)ကို import ပြုလုပ်ရန်-

#. :guilabel:`Source drawing` ၏ တည်နေရာကို ထည့်သွင်းပါ။ ဥပမာ- import ပြုလုပ်မည့် DWG/DXF drawing file
#. Drawing file (ပုံဆွဲသားထားသည့်ဖိုင်) ထဲရှိ data ၏ coordinate reference system (ကိုဩဒိနိတ်စနစ်) ကို သတ်မှတ်ပါ။
#. :guilabel:`Target package` ၏ တည်နေရာကိုထည့်သွင်းပါ။ ဥပမာ- data ကို သိမ်းဆည်းမည့် GeoPackage file။ ရှိပြီးသားဖိုင်ကို ပံ့ပိုးထားပါက ၎င်းကို ပြန်လည်ပြင်ဆင်ရေးသားသွားမည်ဖြစ်ပါသည်။
#. သီးသန့် combobox (ဆက်စပ် popup တစ်ခုပါရှိသည့် input widget တစ်ခု) နှင့်အတူ ``blocks`` များကို မည်သို့ import ပြုလုပ်မည်ကို ရွေးချယ်ပါ။-

   * :guilabel:`Expand Block Geometries` - Drawing file (ပုံဆွဲသားထားသည့်ဖိုင်) ထဲရှိ blocks များကို ပုံမှန် element များအဖြစ်သို့ import ပြုလုပ်သည်။ 
   * :guilabel:`Expand Block Geometries and Add Insert Points` - Drawing file (ပုံဆွဲသားထားသည့်ဖိုင်) ထဲရှိ blocks များကို ပုံမှန် element များအဖြစ်သို့ import ပြုလုပ်ပြီး insertion point (ဆုံမှတ်)  ကို point layer တစ်ခုအဖြစ်ထည့်သွင်းသည်။
   * :guilabel:`Add Only Insert Points` - Blocks insertion point (blocks ဆုံမှတ်များ) များကို point layer တစ်ခုအဖြစ်ထည့်သွင်းသည်။ 

#. Import ပြုလုပ်ထားသည့် layers များကို ``curved`` geometry အမျိုးအစားတစ်ခုအဖြစ်သို့ ဆောင်ရွက်ရန် |checkbox| :guilabel:`Use curves` ကို အမှန်ခြစ်ပါ။ 
#. ဦးတည်ရာ GeoPackage file ထဲသို့ drawing (ပုံ) ကို import ပြုလုပ်ရန် :guilabel:`Import` button  ကို အသုံးပြုပါ။ GeoPackage database ကို drawing file (ပုံဆွဲသားထားသည့်ဖိုင်) ပါ အကြောင်းအရာများ(content) ဖြင့် အလိုအလျောက်ဖြည့်သွင်းသွားမည်ဖြစ်သည်။ ဖိုင်အရွယ်အစားအလိုက် အချိန်အနည်းငယ်ကြာမြင့်မည်ဖြစ်ပါသည်။

:file:`.dwg` သို့မဟုတ် :file:`.dxf` data ကို GeoPackage database ထဲသို့ import ပြုလုပ်ပြီးပါက dialog ၏ အောက်ပိုင်းတစ်ဝက်ရှိဘောင် (frame) ကို imported file (import ပြုလုပ်ထားသည့်ဖိုင်) မှ layers စာရင်း (list)ဖြင့် ဖြည့်သွင်းသွားမည်ဖြစ်ပါသည်။ ထိုနေရာတွင် QGIS project ထဲသို့ မည်သည့် layer များ ထည့်သွင်းမည်ကို select ပြုလုပ်နိုင်ပါသည်- 

#. ထိပ်ဘက်တွင် project ထဲတွင် drawing files များကို အုပ်စုဖွဲ့ရန် :guilabel:`Group name` ကို သတ်မှတ်ပါ။ ပုံမှန်အားဖြင့် ၎င်းကို source (မူရင်း) drawing file ၏ ဖိုင်အမည်အဖြစ်သတ်မှတ်ထားပါသည်။ 
#. Layer များကို ပြသရန် အမှန်ခြစ်ပါ။ Select ပြုလုပ်ထားသည့် layer တစ်ခုချင်းစီကို point (အမှတ်) ၊ line(မျဉ်း) ၊ label(အညွှန်း) နှင့် ဧရိယာ features များအတွက် vector layers များပါဝင်သော ad hoc group ထဲသို့ထည့်သွင်းမည်ဖြစ်ပါသည်။ Layer များ၏ စတိုင်သည် ၎င်းတို့အနေဖြင့် \*CAD ထဲတွင် နဂိုရှိခဲ့သည့်မူလပုံစံအတိုင်း အလားတူရှိမည်ဖြစ်ပါသည်။ 
#. စဖွင့်ဖွင့်ခြင်း layer ကို တွေ့မြင်သင့်သည်ဟု ယူဆပါက ရွေးချယ်ပါ။ 
#. |checkbox| :guilabel:`Merge layers` option ကို အမှန်ခြစ်ခြင်းသည် layers များအားလုံးကို single group တစ်ခုထဲတွင် ထားရှိသွားမည်ဖြစ်ပါသည်။  
#. QGIS ထဲတွင် layers များကို ဖွင့်ရန် :guilabel:`OK` ကိုနှိပ်ပါ။ 


.. _figure_dwg_dxf_import:

.. figure:: img/dwg_dxf_import_dialog.png
    :align: center

    DWG/DXF files များအတွက် Import dialog 


.. index:: OSM (OpenStreetMap)
.. _openstreetmap:

Importing OpenStreetMap Vectors (OpenStreetMap Vector များကို import ပြုလုပ်ခြင်း)
-----------------------------------------------------------------------------------

နိုင်ငံအများအပြားတွင် ဒီဂျစ်တယ်လမ်းမြေပုံများ (digital road maps) ကဲ့သို့သော အခမဲ့ geodata များမရရှိနိုင်သည့်အတွက် OpenStreetMap project သည် လူသိများထင်ရှားပါသည်။ OSM project ၏ ရည်ရွယ်ချက်မှာ GPS data ၊ aerial photography (ကောင်းကင်ဓာတ်ပုံ) နှင့် local knowledge (ဒေသန္တရဗဟုသုတအချက်အလက်များ) များမှ အခမဲ့ပြင်ဆင်နိုင်သည့် ကမ္ဘာကြီး၏မြေပုံ (free editable map of the world) အား ဖန်တီးရန်ဖြစ်ပါသည်။ အဆိုပါရည်ရွယ်ချက်ကို ပံ့ပိုးရန် QGIS သည် OSM data အတွက် ပံ့ပိုးမှု (support) ကို ထောက်ပံ့ပေးထားပါသည်။

:guilabel:`Browser Panel` ကို အသုံးပြု၍ map canvas ထဲတွင် :file:`.osm` ဖိုင်တစ်ခုကို ထည့်သွင်းနိုင်ပါသည်။ အဆိုပါကိစ္စရပ်တွင် geometry အမျိုးအစားအပေါ်အခြေခံ၍ sublayer (layers အခွဲများ) များကို select ပြုလုပ်ရန် dialog တစ်ခုကို ရရှိမည်ဖြစ်ပါသည်။ ထည့်သွင်းထားသည့် layer များသည် :file:`.osm` file ထဲရှိ အဆိုပါ geometry အမျိုးအစား၏ data အားလုံးပါဝင်ပြီး :file:`osm` ဖိုင်ဒေတာဖွဲ့စည်းတည်ဆောက်မှုပုံစံကို သိမ်းဆည်းထားမည်ဖြစ်ပါသည်။ 


.. index::
   pair: SpatiaLite; SQLite
.. _label_spatialite:

SpatiaLite Layers (Single file တစ်ခုထဲတွင် spatial database တစ်ခုလုံးကို ကိုင်တွယ်ဆောင်ရွက်ရလွယ်ကူစေရန် ဖန်တီးထားသည့် layer များ)
----------------------------------------------------------------------------------------------------------------------------------

|addSpatiaLiteLayer| ပထမဆုံးအကြိမ်အဖြစ် SpatiaLite database တစ်ခုမှ data ကို ထည့်သွင်းရာတွင်အောက်ပါတို့ဖြင့် စတင်ဆောင်ရွက်နိုင်ပါသည်။-

* |addSpatiaLiteLayer| :sup:`Add SpatiaLite Layer` toolbar button ကို click ပြုလုပ်ခြင်း
* :menuselection:`Layer --> Add Layer` menu မှ |addSpatiaLiteLayer| :menuselection:`Add SpatiaLite Layer...` option ကို select ပြုလုပ်ခြင်း
* သို့မဟုတ် :kbd:`Ctrl+Shift+L` ကို နှိပ်ခြင်း 

၎င်းသည် QGIS သို့ သိရှိပြီးသားဖြစ်သည့် SpatiaLite database တစ်ခုနှင့် ချိတ်ဆက်ရန် (drop-down menu မှ ရွေးချယ်ထားသည့်အရာ) သို့မဟုတ် database အသစ်တစ်ခုကို ချိတ်ဆက်မှုအသစ်တစ်ခု (new connection) ဖြင့် သတ်မှတ်ချိတ်ဆက်ရန် ခွင့်ပြုသည့် window တစ်ခုကို ပေါ်လာစေမည်ဖြစ်ပါသည်။ ချိတ်ဆက်မှုအသစ်တစ်ခု (new connection) ကို သတ်မှတ်ရန် :guilabel:`New` အပေါ်တွင် click နှိပ်ပြီး သင့်၏ SpatiaLite database ကို ညွှန်ပြရန် file browser ကို အသုံးပြုပါ။ ၎င်းသည် :file:`.sqlite` extension ဖြင့်ရှိသည့် ဖိုင်တစ်ခုဖြစ်ပါသည်။

QGIS သည် SpatiaLite ထဲတွင် ပြန်လည်ပြင်ဆင်နိုင်သည့်မြင်ကွင်းများ (editable views) ကိုလည်းပံ့ပိုးပေးပါသည်။ 


GPS (Global Positioning System- ကမ္ဘာလုံးဆိုင်ရာ တည်နေရာပြစနစ်)
----------------------------------------------------------------

GPS data များကိုသိမ်းဆည်းရန် ဒါဇင်နှင့်ချီသည့် အမျိုးမျိုးသော file format များရှိပါသည်။ QGIS မှ အသုံးပြုသည့် format ကို GPX (GPS eXchange format) ဟုခေါ်ဆိုပြီး ၎င်းသည် တူညီသည့်ဖိုင်ထဲတွင် waypoints (လမ်းခရီးတစ်ခုတွင်ရပ်နားသည့်နေရာများ) ၊ routes (စမှတ်မှဆုံးမှတ်သို့ရောက်ရှိရန်သတ်မှတ်ထားသည့်လမ်းကြောင်းများ) နှင့် tracks (သွားသည့်ခရီးတလျှောက် မှတ်ထားသော လမ်းကြောင်းများ) များပါဝင်နိုင်သော စံသတ်မှတ်ထားသည့် interchange format တစ်ခုဖြစ်ပါသည်။ 

GPX file ကို select ပြုလုပ်ရန် :guilabel:`...` :sup:`Browse` button ကို အသုံးပြုပါ။ 
ထို့နောက် အဆိုပါ GPX file မှ ထည့်သွင်းလိုသည့် feature အမျိုးအစားများကို select ပြုလုပ်ရန် check boxes များကို အသုံးပြုပါ။
Feature အမျိုးအစားတစ်ခုချင်းစီကို သီးခြား layer တစ်ခုထဲတွင် ထည့်သွင်းသွားမည်ဖြစ်ပါသည်။ 

GPS data ကိုင်တွယ်ဆောင်ရွက်ပုံနှင့်စပ်လျဉ်း၍ နောက်ထပ်အကြောင်းအရာများကို :ref:`working_gps` တွင်ကြည့်ရှုပါ။ 

.. _figure_gps_datasource_manager:

.. figure:: img/gps_datasource.png
   :align: center

   GPS Data ထည့်သွင်းခြင်း Dialog


GRASS (Geographic Resources Analysis Support System - GRASS GIS)
-----------------------------------------------------------------

GRASS vector data များဖြင့် လုပ်ဆောင်ခြင်းကို :ref:`sec_grass` section တွင်ဖော်ပြထားပါသည်။ 

.. index:: Database tools, MSSQL Spatial
.. _db_tools:

Database related tools (Database နှင့်ဆက်စပ်နေသည့် ကိရိယာတန်ဆာပလာများ)
-----------------------------------------------------------------------

.. index:: Database; Connecting
.. _vector_create_stored_connection:

Creating a stored Connection (သိမ်းဆည်းထားသည့် ချိတ်ဆက်မှုတစ်ခုကိုဖန်တီးခြင်း)
...............................................................................

QGIS မှ ပံ့ပိုးပေးသည့် database format တစ်ခုမှ tables (ဇယားများ) ကို ဖတ်ရှုရန်နှင့်ရေးသားရန် အဆိုပါ database နှင့် ချိတ်ဆက်မှု (connection) တစ်ခုကို ဖန်တီးရမည်ဖြစ်ပါသည်။ Database များကို ချိတ်ဆက်ရန်နှင့်အသုံးပြုရန် :ref:`QGIS Browser Panel <browser_panel>` သည် အရိုးရှင်းဆုံးနှင့် ထောက်ခံမှုအများဆုံးရရှိထားသည့် နည်းလမ်းတစ်ခုဖြစ်ပြီး QGIS သည် ၎င်းတို့ထဲမှ တစ်ခုချင်းစီသို့ ချိတ်ဆက်ရန်နှင့် ၎င်းတို့၏ဇယားများကို ထည့်သွင်းရန် အခြားသော tool (ကိရိယာတန်ဆာပလာများ) များကို ပံ့ပိုးပေးထားပါသည်။-

* |addPostgisLayer| :menuselection:`Add PostGIS Layer...` သို့မဟုတ် :kbd:`Ctrl+Shift+D` နှိပ်ခြင်း၊ 
* |addMssqlLayer| :menuselection:`Add MS SQL Server Layer`
* |addOracleLayer| :menuselection:`Add Oracle Spatial Layer...` သို့မဟုတ် :kbd:`Ctrl+Shift+O` နှိပ်ခြင်း၊
* |addHanaLayer| :menuselection:`Add SAP HANA Spatial Layer...` သို့မဟုတ် :kbd:`Ctrl+Shift+G` နှိပ်ခြင်း၊

ဖော်ပြပါ tools များကို :guilabel:`Manage Layers Toolbar` နှင့် :menuselection:`Layer --> Add Layer -->` menu မှ ဝင်ရောက်ကြည့်ရှုသုံးစွဲ (accessible) နိုင်ပါသည်။ SpatialLite database ကို ချိတ်ဆက်ခြင်းအကြောင်းကို :ref:`label_spatialite` တွင် ဖော်ပြထားပါသည်။


.. tip:: **QGIS Browser Panel မှ database သို့ ချိတ်ဆက်မှု (connection) ဖန်တီးသည်**

   Browser tree ထဲရှိ သက်ဆိုင်ရာ database ကို Select ပြုလုပ်ခြင်း၊ right-clicking (ညာဘက်ကလစ်နှိပ်ခြင်း) ပြုလုပ်ခြင်းနှင့်  ချိတ်ဆက်မှု (connect) ကို ရွေးချယ်ခြင်းသည် database connection dialog (database ချိတ်ဆက်မှုဆိုင်ရာဒိုင်ယာလော့ခ်) ကို ပံ့ပိုးပေးမည်ဖြစ်ပါသည်။ 

Connection dialogs အများစုသည် PostgreSQL database tool ကို နမူနာအဖြစ်အသုံးပြုမည့် အောက်တွင်ဖော်ပြထားသော ဖြစ်လေ့ဖြစ်ထရှိသည့် အခြေခံသဘောတရား (common basis) ကို လိုက်နာပါသည်။ အခြားပံ့ပိုးသူများ (providers) အတွက် သီးသန့်အပိုဆောင်း setting များကို ဖော်ပြပါ သက်ဆိုင်ရာဖော်ပြချက်များတွင် တွေ့ရှိနိုင်ပါသည်-

* :ref:`create_ms_sql_server_connection` (MS SQL Server သို့ ချိတ်ဆက်ခြင်း)၊
* :ref:`create_oracle_connection` (Oracle Spatial သို့ ချိတ်ဆက်ခြင်း)၊
* :ref:`create_hana_connection` (SAP HANA သို့ ချိတ်ဆက်ခြင်း)

PostGIS data source ကို ပထမဆုံးအကြိမ် စတင်အသုံးပြုသည့်အချိန်တွင် data များပါဝင်သည့် database တစ်ခုကို ချိတ်ဆက်မှု (connection) တစ်ခုဖန်တီးရမည်ဖြစ်ပါသည်။ အထက်ဖော်ပြပါ သက်ဆိုင်ရာ button (ခလုတ်) ကို နှိပ်ခြင်းသည် :guilabel:`Add PostGIS Table(s)` dialog ကို ပွင့်စေမည်ဖြစ်ပါသည်။ (:numref:`figure_add_postgis_tables` တွင် ကြည့်ပါ) Connection manager (ချိတ်ဆက်မှုကိုစီမံခန့်ခွဲမှုများပြုလုပ်သည့်နေရာ) ကို ဝင်ရောက်ကြည့်ရှုသုံးစွဲခွင့် (access) ရရှိရန် :guilabel:`Create a New PostGIS Connection` dialog ကို ပြသရန်အတွက် :guilabel:`New` button အပေါ်တွင် click နှိပ်ပါ။ 

.. _figure_new_postgis_connection:

.. figure:: img/newpostgisconnection.png
   :align: center

   PostGIS Connection အသစ်တစ်ခုကိုဖန်တီးသည့် Dialog


PostGIS ဆိုင်ရာ ချိတ်ဆက်မှုတစ်ခုအတွက် လိုအပ်သော သတ်မှတ်ချက်များ (parameters) ကို အောက်တွင်ဖော်ပြထားပါသည်။
အခြားသော database အမျိုးအစားများအတွက် ကွာခြားချက်များကို :ref:`db_requirements` တွင်ကြည့်ရှုပါ။

* :guilabel:`Name` - ဤချိတ်ဆက်မှုအတွက်အမည်တစ်ခု။ ၎င်းသည် :guilabel:`Database` နှင့် အတူတူပင်ဖြစ်နိုင်ပါသည်။ 
* :guilabel:`Service` - hostname/port (database ဖြစ်ကောင်းဖြစ်နိုင်ပါသည်) သို့ နောက်တစ်မျိုးဖြင့်အသုံးပြုမည့် ဝန်ဆောင်မှုဆိုင်ရာသတ်မှတ်ချက် (Service parameter)။ ၎င်းကို :file:`pg_service.conf` တွင် သတ်မှတ်နိုင်ပါသည်။ အခြားသောအသေးစိတ်အချက်အလက်များအတွက် :ref:`pg-service-file` section ကို ကြည့်ပါ။
* :guilabel:`Host` - Database host ၏ အမည်။ ၎င်းသည် TCP/IP connection တစ်ခုကိုဖွင့်ရန် သို့မဟုတ် host သည် IP ကွန်ရက်တစ်ခုအတွင်း ဆက်သွယ်နိုင်မှုရှိမရှိ စမ်းသပ်ခြင်း (ping) ပြုလုပ်ရန် အသုံးပြုနိုင်သည့် resolvable host name (တစ်ခု သို့မဟုတ် တစ်ခုထက်ပိုသော IP addresses များကို ဖြေရှင်းနိုင်သော host အမည်) တစ်ခုဖြစ်ရမည်ဖြစ်ပါသည်။ အကယ်၍ database သည် QGIS ကဲ့သို့ တူညီသည့်ကွန်ပျူတာပေါ်တွင်ရှိပါက ဤနေရာတွင် *localhost* ကို ထည့်သွင်းပါ။ 
* :guilabel:`Port` - PostgreSQL database server တွင် စာရင်းပြုစုထားသည့် Port နံပါတ်။ PostGIS အတွက် ပုံမှန် port မှာ ``5432`` ဖြစ်ပါသည်။  
* :guilabel:`Database` - Database ၏ အမည်။
* :guilabel:`SSL mode` - SSL encryption setup။ ဖော်ပြပါနည်းလမ်းများကိုလည်းရရှိနိုင်ပါသည်- 

  * :guilabel:`Prefer` (ပုံမှန်) - မိမိအနေဖြင့် encryption (ဒေတာများ ခိုးယူခံရခြင်း၊ ပြောင်းလဲခြင်း သို့မဟုတ်ထိခိုက်အောင်ပြုလုပ်ခံရခြင်းမှ ကာကွယ်ရန်အတွက် အသုံးပြုသည်) ကို အလေးမထားပါ။ သို့သော် အကယ်၍ server သည် ၎င်းကိုပံ့ပိုးပေးထားပါက encryption ၏ overhead (မူရင်းပက်ကေ့ခ်ျများထဲသို့ IPsec ကထပ်ထည့်ပေးထားသည့် အပိုဒေတာနှင့် processing) အတွက်ပေးရန် ဆန္ဒရှိပါသည်။ 
  * :guilabel:`Require` - မိမိ၏ ဒေတာများကို encrypt ပြုလုပ်လိုပြီး overhead ကိုလက်ခံပါသည်။ ကွန်ယက်သည် မိမိအလိုရှိသည့် server အား အမြဲချိတ်ဆက်မှုပြုလုပ်စေမည်ကို ယုံကြည်ပါသည်။ 
  * :guilabel:`Verify CA` - မိမိ၏ ဒေတာများကို encrypt ပြုလုပ်လိုပြီး overhead ကိုလက်ခံပါသည်။ မိမိအနေဖြင့် ကွန်ယက်သည် မိမိယုံကြည်ရသည့် server ကိုချိတ်ဆက်နေသည်ကို သေချာစေလိုပါသည်။
  * :guilabel:`Verify Full` - မိမိ၏ ဒေတာများကို encrypt ပြုလုပ်လိုပြီး overhead ကိုလက်ခံပါသည်။ မိမိအနေဖြင့် ကွန်ယက်သည် မိမိယုံကြည်ရသည့် server တစ်ခုကို ချိတ်ဆက်ထားပြီး ၎င်းသည် မိမိမှ သတ်မှတ်ထားသည့် server ဖြစ်သည်ကို သေချာစေလိုပါသည်။ 
  * :guilabel:`Allow` - မိမိအနေဖြင့် လုံခြုံရေး (security) ကို ဂရုမစိုက်ပါ။ သို့သော် server ကတောင်းဆိုပါက overhead ကို ပေးမည်ဖြစ်ပါသည်။
  * :guilabel:`Disable` - မိမိအနေဖြင့် လုံခြုံရေး (security) ကို ဂရုမစိုက်ပါ။ encryption ၏ overhead ကို ပေးရန်လည်း ဆန္ဒမရှိပါ။ 

* :guilabel:`Authentication`- အခြေခံအားဖြင့်။ 

  * :guilabel:`User name` - Database သို့ လော့ဂ်အင် (log in) ဝင်ရန်အသုံးပြုသည့် အသုံးပြုသူ၏အမည် (User name)
  * :guilabel:`Password` - Database သို့ ချိတ်ဆက်ရန် *Username* နှင့်အတူအသုံးပြုမည့် Password (စကားဝှက်)

  ``User name`` နှင့် ``Password`` သတ်မှတ်ချက်များကို တစ်ခုတည်းကိုဖြစ်စေ၊ နှစ်ခုလုံးကိုဖြစ်စေ သိမ်းဆည်းနိုင်ပါသည်။ ထိုသို့သိမ်းဆည်းပါက သင့်အနေဖြင့် ဤ database ကို ချိတ်ဆက်သည့်အချိန်တစ်ခုစီတိုင်းတွင် ၎င်းတို့ကို ပုံမှန် (default) အဖြစ်အသုံးပြုသွားမည်ဖြစ်ပါသည်။ အကယ်၍ သိမ်းဆည်းမထားပါက နောက် QGIS sessions တွင် database ကိုချိတ်ဆက်ရန်အတွက် လိုအပ်သည့်အထောက်အထားများ (credentials) ကို ပံ့ပိုးပေးရန် အသိပေးခြင်းခံရမည်ဖြစ်ပါသည်။ သင်ထည့်သွင်းလိုက်သည့် ချိတ်ဆက်မှုဆိုင်ရာသတ်မှတ်ချက်များ (connection parameters) ကို temporary(ယာယီ) internal cache (CPU Chip တွင်တည်ဆောက်ထားသော Memory bank တစ်ခု) ထဲတွင်သိမ်းဆည်းထားပြီး လက်ရှိ  QGIS session ကို အပြီးမသတ်သေးခင် (end) အချိန်အထိ တူညီသည့် database အတွက် username (အသုံးပြုသူအမည်)/password (စကားဝှက်) ကို တောင်းခံသည့်အခါတိုင်းတွင် ပြန်လည်ရောက်ရှိမည်ဖြစ်ပါသည်။ 

  .. warning:: **QGIS အသုံးပြုသူဆိုင်ရာ Settings နှင့် လုံခြုံစိတ်ချရမှု**

   :guilabel:`Authentication` tab ထဲတွင် **username** နှင့် **password** ကို သိမ်းဆည်းခြင်းသည် ကာကွယ်ထားခြင်းမရှိသည့် အထောက်အထားများ (credentials) ကို connection configuration (Diameter nodes များအကြား ယုံကြည်စိတ်ချရသည့် သယ်ယူပို့ဆောင်မှုများကို ပံ့ပိုးပေးသည့် ချိတ်ဆက်မှုတစ်ခု) ထဲတွင် သိမ်းဆည်းထားလိမ့်မည်ဖြစ်ပါသည်။ ဥပမာ- project ဖိုင်ကို အခြားသူနှင့် မျှဝေခြင်းပြုလုပ်သည့်အခါတွင် အဆိုပါ အထောက်အထားများကို မြင်နိုင်မည် (**credentials will be visible**) ဖြစ်ပါသည်။ ၎င်းအစား အထောက်အထားများ (credentials) ကို *Authentication configuration* (:guilabel:`Configurations` tab- အခြားသောအသေးစိတ်အချက်အလက်များအတွက် :ref:`authentication_index` ကို ကြည့်ပါ) ထဲတွင် သိမ်းဆည်းရန် သို့မဟုတ် service connection file တစ်ခုထဲတွင် သိမ်းဆည်းရန် (နမူနာအနေဖြင့် :ref:`pg-service-file` ကို ကြည့်ပါ။) အကြံပြုပါသည်။ 

* :guilabel:`Authentication` ၊ ပြင်ဆင်သတ်မှတ်ခြင်းများ။ Authentication configuration (system ကို အသုံးပြုသူများအတွက် စစ်မှန်ကြောင်းအတည်ပြုမှုကိုဖန်တီးသတ်မှတ်ခြင်း) တစ်ခုကိုရွေးချယ်ပါ။ |symbologyAdd| button ကို အသုံးပြု၍ ပြင်ဆင်သတ်မှတ်ခြင်းများကို ထည့်သွင်းနိုင်ပါသည်။ ရွေးချယ်စရာများမှာ-

  * Basic authentication (အခြေခံအားဖြင့် စစ်မှန်ကြောင်းအတည်ပြုမှု)
  * PKI PKCS#12 authentication (PKI PKCS#12 စစ်မှန်ကြောင်းအတည်ပြုမှု)
  * PKI paths authentication (PKI paths စစ်မှန်ကြောင်းအတည်ပြုမှု)
  * PKI stored identity certificate (PKI သက်သေခံအထောက်အထားလက်မှတ်ကို သိမ်းဆည်းထားသည်)

Database အမျိုးအစားအလိုက် ဖော်ပြပါ checkbox များကို အသက်ဝင်အောင်ဆောင်ရွက်ခြင်း (activate) ပြုလုပ်နိုင်ပါသည်-

* |checkbox| :guilabel:`Only show layers in the layer registries` (layer စာရင်းသွင်းထားမှုများ (layer registries) ထဲရှိ layers များကိုသာပြသသည်။)
* |checkbox| :guilabel:`Don't resolve type of unrestricted columns (GEOMETRY)` (ကန့်သတ်မထားသော(unrestricted) ကော်လံအမျိုးအစားများကိုဖြေရှင်းခြင်းမပြုရန် (GEOMETRY))
* |checkbox| :guilabel:`Only look in the 'public' schema` (Public schema ထဲတွင်သာ ကြည့်သည်။)
* |checkbox| :guilabel:`Also list tables with no geometry` (Geometry မပါရှိသည့် ဇယားများကို စာရင်းပြုစုသည်။)
* |checkbox| :guilabel:`Use estimated table metadata` (ခန့်မှန်းတွက်ချက်ထားသည့် table metadata ကို အသုံးပြုသည်။)
* |checkbox| :guilabel:`Allow saving/loading QGIS projects in the database` (Database ထဲတွင် QGIS projects များကို သိမ်းဆည်းခြင်း/ထည့်သွင်းခြင်းများခွင့်ပြုသည်။) - အသေးစိတ်ကို :ref:`here <saveprojecttodb>` တွင် ကြည့်ရှုရန်
* |checkbox| :guilabel:`Allow saving/loading QGIS layer metadata in the database` (database ထဲတွင် QGIS layer metadata များကို သိမ်းဆည်းခြင်း/ထည့်သွင်းခြင်းများခွင့်ပြုသည်) - အသေးစိတ်ကို :ref:`ဤ <savemetadatatodb>` တွင် ကြည့်ရှုရန်။

.. tip:: **လုပ်ငန်းဆောင်တာများ (operations) ကို မြန်ဆန်စေ (speed up) ရန် ခန့်မှန်းတွက်ချက်ထားသည့် table metadata ကို အသုံးပြုသည်**  

   Layers များကို စတင်ဆောင်ရွက်သောအခါ၌ database ဇယားတွင် သိမ်းဆည်းထားသော geometries များ၏ ဝိသေသလက္ခဏာများ (characteristics)ကို သတ်မှတ်ရန် အမျိုးမျိုးသော queries များကို လိုအပ်မည်ဖြစ်ပါသည်။ :guilabel:`Use estimated table metadata` ကို အမှန်ခြစ်ထားပါက အဆိုပါ queries များသည် ဇယားတစ်ခုလုံးထက် row များ၏ နမူနာ sample တစ်ခုကိုသာ စစ်ဆေးပြီး table statistics(ကိန်းဂဏန်းများကို စနစ်တကျစီစဉ်၍ mass processess အချို့ကို ဖော်ပြပြီး စာရင်းအင်းဆိုင်ရာအချက်အလက်များကိုဖော်ပြရန် အသုံးပြုသည့်နည်းလမ်း) များကို အသုံးပြုပါသည်။ ၎င်းသည် ကြီးမားသည့် datasets များအပေါ် လုပ်ငန်းဆောင်တာများ (operations) လည်ပတ်ခြင်းကို မြန်ဆန်စေပါသည်။ သို့ရာတွင် layers များ၏ မှန်ကန်မှုမရှိသည့် ဝိသေသလက္ခဏာများကို (incorrect characterization) ရရှိစေနိုင်မည်ဖြစ်ပြီး (ဥပမာ- စစ်ထုတ်ထားသည့် layer များ၏ feature count (feature အရေအတွက်) ကို တိကျစွာဆုံးဖြတ်နိုင်ခြင်းရှိမည်မဟုတ်ပါ) အမှန်တကယ်တွင် ထူးခြားမှုရှိသည့် column များကို ထူးခြားခြင်းမရှိပါဟု ယူဆလိုက်ပါက ထူးဆန်းသည့် ပြုမှုဆောင်ရွက်မှုများ (behaviour) ကိုပင်ဖြစ်စေပါသည်။

သတ်မှတ်ချက်များနှင့် နည်းလမ်းများအားလုံးကို သတ်မှတ်ပြီးပါက ချိတ်ဆက်မှု (connection) အား :guilabel:`Test Connection` ကို click နှိပ်ခြင်းဖြင့် သို့မဟုတ် :guilabel:`OK` button ကို click နှိပ်ပြီး ၎င်းအား apply ပြုလုပ်ခြင်းဖြင့် စမ်းသပ်စစ်ဆေးနိုင်ပါသည်။ :guilabel:`Add PostGIS Table(s)` မှ :guilabel:`Connect` အပေါ်တွင် click နှိပ်ပါ။ Dialog ကို select ပြုလုပ်ထားသည့် database မှ ဇယားများဖြင့် ဖြည့်သွင်းသွားမည်ဖြစ်ပါသည်။ (:numref:`figure_add_postgis_tables` တွင် ပြသထားသကဲ့သို့)


.. _db_requirements:

Particular Connection requirements (သီးခြားချိတ်ဆက်မှုဆိုင်ရာလိုအပ်ချက်များ)
.............................................................................

Database အမျိုးအစားများ၏ ထူးခြားမှုများ (particularities) ကြောင့် ထည့်သွင်းပံ့ပိုးပေးထားသည့် နည်းလမ်းများ (options) မှာလည်း တူညီမှုရှိမည်မဟုတ်ပါ။ Database specific options (Database ဆိုင်ရာ သီးခြားနည်းလမ်း) များကို အောက်တွင်ဖော်ပြထားပါသည်- 

.. _pg-service-file:

PostgreSQL Service connection file (PostgreSQL ဝန်ဆောင်မှု အချိတ်အဆက်ဖိုင်)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Service connection file သည် PostgreSQL connection parameters (PostgreSQL ချိတ်ဆက်မှုဆိုင်ရာသတ်မှတ်ချက်များ) ကို 
service name (၎င်း၏အမည်သည် " . service " ဖြင့်အဆုံးသတ်ပြီး system မှ ထိန်းချုပ်ကွပ်ကဲထားသည့် လုပ်ငန်းစဉ်တစ်ခု‌အကြောင်း encode ပြုလုပ်သည့် unit configuration file တစ်ခု) တစ်ခုနှင့် ဆက်စပ်မှုရှိစေရန် ခွင့်ပြုပါသည်။ Service name ကို နောက်ပိုင်းတွင် client မှ ပြန်လည်သတ်မှတ်နိုင်ပြီး သက်ဆိုင်ရာ ဆက်စပ် settings များကို အသုံးပြုသွားမည်ဖြစ်ပါသည်။ 

၎င်းကို \*nix systems (GNU/Linux ၊ macOS အစရှိသည်) အောက်တွင် :file:`.pg_service.conf` ဟုခေါ်ဆိုပြီး 
Windows များအပေါ်တွင် :file:`pg_service.conf`  ဟုခေါ်ဆိုပါသည်။ 

Service file ကို အောက်ပါအတိုင်းတွေ့မြင်နိုင်ပါသည်-

 [water_service]
 host=192.168.0.45
 port=5433
 dbname=gisdb
 user=paul
 password=paulspass

 [wastewater_service]
 host=dbserver.com
 dbname=water
 user=waterpass


.. note:: အထက်ဖော်ပြပါ နမူနာများတွင် service (၂) ခုရှိပါသည်- ``water_service`` နှင့် ``wastewater_service`` တို့ဖြစ်ပါသည်။ ချိတ်ဆက်လိုသည့် service ၏ အမည်ကို သတ်မှတ်ပေးရုံဖြင့် (ကွင်းပိတ်များမပါဘဲ) QGIS ၊ pgAdmin စသည်တို့မှ ချိတ်ဆက်ရန် ၎င်းတို့ကို အသုံးပြုနိုင်ပါသည်။ Service ကို ``psql`` နှင့်အတူ အသုံးပြုလိုပါက psql commands (အမိန့်ပေးစေခိုင်းမှုများ) ကို ဆောင်ရွက်ခြင်းမပြုမီတွင် ``export PGSERVICE=water_service`` ကဲ့သို့သော အချို့အရာများကို လုပ်ဆောင်ရန်လိုအပ်ပါသည်။ 

  PostgreSQL parameters များအားလုံးကို `ဤတွင် <https://www.postgresql.org/docs/current/libpq-connect.html#LIBPQ-PARAMKEYWORDS>`_ တွေ့ရှိနိုင်ပါသည်။

.. note:: အကယ်၍ passwords ကို service file ထဲတွင် သိမ်းဆည်းလိုခြင်းမရှိပါက `.pg_pass <https://www.postgresql.org/docs/current/libpq-pgpass.html>`_ နည်းလမ်းကို အသုံးပြုနိုင်ပါသည်။

\*nix operating systems (GNU/Linux ၊ macOS အစရှိသည်) များတွင် :file:`.pg_service.conf` file ကို အသုံးပြုသူ (user) ၏ 
home directory (system ၏ ပေးထားသည့် အသုံးပြုသူအတွက် ဖိုင်များ ပါဝင်သော multi-user operating system ရှိ ဖိုင်စနစ်လမ်းညွှန် တစ်ခု ဖြစ်သည်) ထဲတွင် သိမ်းဆည်းနိုင်ပြီး PostgreSQL clients များသည် ၎င်းကို အလိုအလျောက်သတိပြုမိမည်ဖြစ်ပါသည်။ ဥပမာ- အကယ်၍ logged user (အကောင့်ဝင်ထားသည့် အသုံးပြုသူ) သည် ``web`` ဖြစ်ပါက လုပ်ငန်းဆောင်တာများကို တိုက်ရိုက်ဆောင်ရွက်နိုင်ရန် (အခြားသော environment variables(ကွန်ပျူတာပေါ်တွင် လုပ်ဆောင်နေသည့် လုပ်ငန်းစဉ်များလုပ်ဆောင်ပုံအပေါ် သက်ရောက်မှုရှိနိုင်သည့် အသုံးပြုသူမှ သတ်မှတ်နိုင်သော တန်ဖိုးတစ်ခု) ကို သတ်မှတ်ခြင်းမရှိဘဲ) :file:`.pg_service.conf` ကို :file:`/home/web/` directory ထဲတွင် သိမ်းဆည်းမည်ဖြစ်ပါသည်။

Service file ၏ တည်နေရာကို ``PGSERVICEFILE`` environment variable တစ်ခုကိုဖန်တီးခြင်းဖြင့် သတ်မှတ်နိုင်ပါသည်။ (ဥပမာ- ``PGSERVICEFILE`` variable (ကိန်းရှင်) ကို ယာယီသတ်မှတ်ရန် သင့် \*nix OS အောက်ရှိ ``export PGSERVICEFILE=/home/web/.pg_service.conf`` command ကို run ပါ။)

Service file ကို  ``pg_config --sysconfdir`` ထဲရှိ :file:`.pg_service.conf` ဖိုင်ကို ထားရှိခြင်း သို့မဟုတ် service file ပါဝင်သည့်  directory ကို သတ်မှတ်ရန် ``PGSYSCONFDIR`` environment variable ကို ထည့်သွင်းခြင်းဖြင့် system-wide (အသုံးပြုသူအားလုံး) ဖြစ်စေရန်ဆောင်ရွက်နိုင်ပါသည်။ အကယ်၍ service definitions သည် user file(အသုံးပြုသူမှဖန်တီးထားသည့်ဖိုင်)နှင့် system file (operating system သို့မဟုတ် device driver တစ်ခု၏အစိတ်အပိုင်းဖြစ်သည့် အရေးကြီးသည့်ဖိုင်) ထဲတွင် တူညီသည့်အမည်ဖြင့်ရှိနေပါက user file ကို ဦးစားပေးပါသည်။

.. warning::

  Windows များအောက်တွင် သတိပေးချက် (caveat) အချို့ရှိပါသည်-

  * Service file ကို :file:`pg_service.conf` အဖြစ်သိမ်းဆည်းသင့်ပြီး :file:`.pg_service.conf` အဖြစ်မသိမ်းဆည်းသင့်ပါ။ 
  * လုပ်ငန်းဆောင်တာများဆောင်ရွက်ရန် service file ကို Unix format ဖြင့် သိမ်းဆည်းသင့်ပါသည်။ ထိုသို့လုပ်ဆောင်ရန် နည်းလမ်းတစ်ခုမှာ ၎င်းကို `Notepad++ <https://notepad-plus-plus.org/>`_  နှင့် :menuselection:`Edit --> EOL Conversion --> UNIX Format --> File save` ဖြင့် ဖွင့်ခြင်းဖြစ်ပါသည်။ 
  * Environmental variables (ကွန်ပျူတာပေါ်တွင် လုပ်ဆောင်နေသည့် လုပ်ငန်းစဉ်များလုပ်ဆောင်ပုံအပေါ် သက်ရောက်မှုရှိနိုင်သည့် အသုံးပြုသူမှ သတ်မှတ်နိုင်သော တန်ဖိုးတစ်ခု) များကို နည်းလမ်းများစွာဖြင့် ထည့်သွင်းနိုင်ပါသည်။ ယုံကြည်စိတ်ချရပြီး စမ်းသပ်ထားသည့်နည်းလမ်းတစ်ခုမှာ ဖိုင်လမ်းကြောင်း - ဥပမာ- :file:`C:\\Users\\John\\pg_service.conf`  နှင့်အတူ  ``PGSERVICEFILE`` ကိုထည့်သွင်းသည့် :menuselection:`Control Panel --> System and Security -->System --> Advanced system settings --> Environment Variables`  ဖြစ်ပါသည်။ 
  * Environment variable တစ်ခုကို ထည့်သွင်းပြီးပါက ကွန်ပျူတာကို restart လုပ်ရန်လိုအပ်မည်ဖြစ်ပါသည်။ 


.. _create_oracle_connection:

Connecting to Oracle Spatial (Oracle Spatial အားချိတ်ဆက်ခြင်း)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Oracle Spatial ထဲရှိ spatial features များသည် အသုံးပြုသူကို Oracle database တစ်ခုအတွင်းတွင် native type (မူရင်းအမျိုးအစား) ဖြင့် ပထဝီဝင်နှင့်တည်နေရာဆိုင်ရာဒေတာအချက်အလက် (geographic and location data) များကို စီမံခန့်ခွဲရာတွင် ကူညီပါသည်။ :ref:`vector_create_stored_connection` ထဲရှိ နည်းလမ်းအချို့အပြင် connection dialog (ရှိပြီးသား Server Connection Definition အတွက် ချိတ်ဆက်မှုဒေတာကို ဖန်တီးရန် သို့မဟုတ် ပြင်ဆင်ရန် အသုံးပြုသည့် dialog) သည် အောက်ဖော်ပြပါတို့ကို အဆိုပြုပါသည်- 

* **Database** - Oracle instance (Oracle instance တစ်ခုတွင် Oracle database ကို ဆောင်ရွက်စေသည့် shared memory structures နှင့် background processesများ ပါဝင်ပါသည်) ၏  SID သို့မဟုတ် SERVICE_NAME 
* **Port** - Oracle database server တွင် စာရင်းပြုစုဖော်ပြထားသည့် နံပါတ်။ ပုံမှန်နံပါတ် (defaultport) မှာ ``1521`` ဖြစ်ပါသည်။ 
* **Options** - Oracle connection specific options (Oracle ချိတ်ဆက်မှု ဆိုင်ရာသီးသန့်နည်းလမ်းများ) (ဥပမာ OCI_ATTR_PREFETCH_ROWS ၊ OCI_ATTR_PREFETCH_MEMORY)။ Options string ၏ format မှာ semicolon ဖြင့်ပိုင်းခြားထားသည့် နည်းလမ်းများ၏အမည်စာရင်း (semicolon separated list of option names) သို့မဟုတ် option=value pairs; ဖြစ်ပါသည်။ 
* **Workspace** - Workspace ပြောင်းလဲရန်
* **Schema** - Data များကိုသိမ်းဆည်းထားသည့် Schema 

ရွေးချယ်လိုပါကရွေးချယ်နိုင်ပါသည်။ အောက်ပါ checkboxes များကို အသက်ဝင်အောင်ဆောင်ရွက်ခြင်း (activate) ပြုလုပ်နိုင်ပါသည်-

* |checkbox| :guilabel:`Only look in metadata table (Metadata table ထဲတွင်သာကြည့်ရန်)` - ``all_sdo_geom_metadata`` view ထဲရှိ ပြသထားသည့်ဇယား (displayed tables) များကို ကန့်သတ် (restrict) ပါသည်။ ၎င်းသည် spatial tables များအစပြုပြသမှု (initial display) ကို မြန်ဆန်စေပါသည်။ 
* |checkbox| :guilabel:`Only look for user's tables (User table များကိုသာရှာဖွေခြင်း)` - Spatial tables များကို ရှာဖွေရာတွင် အသုံးပြုသူမှပိုင်ဆိုင်သည့် tables (ဇယားများ) သို့ ရှာဖွေခြင်းအား ကန့်သတ်ပါသည်။ 
* |checkbox| :guilabel:`Also list tables with no geometry (Geometry မပါသည့် table များစာရင်းပြုစုခြင်း)` - Default အနေဖြင့်  geometry မပါရှိသည့် table များကိုလည်း စာရင်းပြုစုသင့်သည်ကို ညွှန်ပြပါသည်။ 
* |checkbox| :guilabel:`Use estimated table statistics for the layer metadata (Layer metadata အတွက် ခန့်မှန်း table ကိန်းဂဏန်းစာရင်းအင်း ကိုအသုံးပြုခြင်း)` - Layer ကို သတ်မှတ်သည့်အခါတွင် အမျိုးမျိုးသော metadata များကို Oracle table အတွက် လိုအပ်မည်ဖြစ်ပါသည်။ ၎င်းတွင် data ၏ table row count (ဇယားအတန်းအရေအတွက်) ၊ geometry type (geometry အမျိုးအစား) နှင့် spatial extents (နယ်ပယ်အတိုင်းအတာပမာဏ) ကဲ့သို့သော အချက်အလက်များပါဝင်ပါသည်။ အကယ်၍ table သည် rows အရေအတွက်များ အများအပြားပါဝင်ပါက အဆိုပါ metadata ကို ဆုံးဖြတ်ခြင်းသည် အချိန်ကုန်မည်ဖြစ်ပါသည်။ ဤနည်းလမ်းကို အသက်ဝင်အောင်ဆောင်ရွက်ခြင်း (activating) သည် ဖော်ပြပါ မြန်ဆန်သည့် table metadata ဆိုင်ရာ လုပ်ငန်းဆောင်တာများလည်ပတ်ခြင်း (table metadata operations) ကို ဆောင်ရွက်ပြီးဖြစ်မည်ဖြစ်ပါသည်။ Row count (ဇယားအတန်းအရေအတွက်) ကို ``all_tables.num_rows`` မှ ဆုံးဖြတ်ပါသည်။ အကယ်၍ layer filter (layer အား စစ်ထုတ်မှု) ပြုလုပ်ထားစေကာမူ Table extents (ဇယား၏နယ်ပယ်အတိုင်းအတာပမာဏ) ကို SDO_TUNE.EXTENTS_OF function ဖြင့် အမြဲဆုံးဖြတ်ပါသည်။ Table geometry ကို table ထဲရှိ ပထမဆုံး non-null geometry rows (၁၀၀) မှ ဆုံးဖြတ်ပါသည်။ 
* |checkbox| :guilabel:`Only existing geometry types (တည်ရှိနေပြီးသား geometry အမျိုးအစားများသာ)` - လက်ရှိရှိနေသည့် geometry အမျိုးအစားများကိုသာ စာရင်းပြုစုမည်ဖြစ်ပြီး အခြားအမျိုးအစားများကို ထည့်သွင်းမည်မဟုတ်ပါ။
* |checkbox| :guilabel:`Include additional geometry attributes (အခြားအပိုဆောင်း geometry attribute များ ပါဝင်စေခြင်း)`

.. _tip_ORACLE_Spatial_layers:

.. tip:: **Oracle Spatial Layer များ**

   ပုံမှန်အားဖြင့် Oracle Spatial layer တစ်ခုကို **USER_SDO_METADATA** table ထဲတွင် entry တစ်ခုဖြင့် သတ်မှတ်ပါသည်။ 

   Selection ပြုလုပ်သည့် tools သည် ကောင်းစွာအလုပ်လုပ်သည်ကို သေချာမှုရှိစေရန် tables တွင် **primary key** တစ်ခုရှိရန်အကြံပြုအပ်ပါသည်။

 
.. _create_ms_sql_server_connection:

Connecting to MS SQL Server (MS SQL Server သို့ ချိတ်ဆက်ခြင်း)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

:ref:`vector_create_stored_connection` ထဲရှိ နည်းလမ်းအချို့အပြင် MS SQL Server connection dialog အသစ်တစ်ခုကို ဖန်တီးခြင်းသည် **Provider/DSN** အမည်ကို ဖြည့်စွက်စေပါလိမ့်မည်ဖြစ်ပါသည်။ ရရှိနိုင်သည့် databases များကိုလည်းပြသနိုင်ပါသည်။ 

.. _create_hana_connection:

Connecting to SAP HANA (SAP HANA သို့ချိတ်ဆက်ခြင်း)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. note:: SAP HANA Client ကိုလိုအပ်မည်ဖြစ်ပါသည်။ သင့်ပလက်ဖောင်းအတွက် SAP HANA Client ကို `SAP Development Tools website <https://tools.hana.ondemand.com/#hanatools>`_ မှ ဒေါင်းလုပ်ရယူနိုင်ပါသည်။ 

.. _figure_new_hana_connection:

.. figure:: img/newhanaconnection.png
   :align: center

   SAP HANA Connection Dialog အသစ်တစ်ခုကို ဖန်တီးခြင်း 

ဖော်ပြပါသတ်မှတ်ချက်များကို ထည့်သွင်းနိုင်ပါသည်-

* :guilabel:`Name` - ဤချိတ်ဆက်မှုအတွက် အမည်တစ်ခု
* :guilabel:`Driver` |win| - HANA ODBC driver ၏ အမည်။ အကယ်၍ 64-bit QGIS ကို အသုံးပြုနေပါက ၎င်းသည် ``HDBODBC`` ဖြစ်ပြီး 32-bit QGIS ကို အသုံးပြုနေပါက ``HDBODBC32`` ဖြစ်ပါသည်။ သင့်လျော်သည့် driver ၏ အမည်ကို အလိုအလျောက်ထည့်သွင်းထားမည်ဖြစ်ပါသည်။

* :guilabel:`Driver` |nix| |osx| - :file:`/etc/odbcinst.ini` ထဲတွင် စာရင်းသွင်းထားသည့် SAP HANA ODBC driver အောက်ရှိ အမည် သို့မဟုတ် SAP HANA ODBC driver ရှိရာ လမ်းကြောင်း (path) အပြည့်အစုံ။ ပုံမှန်အားဖြင့် SAP HANA Client installer သည် ODBC driver ကို  :file:`/usr/sap/hdbclient/libodbcHDB.so` ထဲသို့ ထည့်သွင်းတည်ဆောက်သွားမည်ဖြစ်ပါသည်။

* :guilabel:`Host` - Database host ၏ အမည်

* :guilabel:`Identifier` - Host အပေါ်တွင် ချိတ်ဆက်ရန် instance (physical or virtual server တစ်ခုအပေါ်တွင် လုပ်ဆောင်နေသည့် ဆော့ဖ်ဝဲတစ်ခု၏မိတ္တူတစ်ခု) တစ်ခုကို သတ်မှတ်သည်။ ၎င်းသည် :guilabel:`Instance Number` သို့မဟုတ် :guilabel:`Port Number` ဖြစ်နိုင်ပါသည်။ Instance Number တွင် ဂဏန်းနှစ်လုံး (two digits) ပါဝင်ပြီး နံပါတ်များသည်  1 မှ 65,535 ထိ အတွင်းရှိ range ထဲတွင်ရှိပါသည်။

* :guilabel:`Mode` - SAP HANA instance များ run ပြုလုပ်မည့် mode ကို သတ်မှတ်သည်။ ဤ setting သည် :guilabel:`Identifier` ကို :guilabel:`Instance Number` အဖြစ်သို့ သတ်မှတ်ထားမှသာ ထည့်သွင်းစဉ်းစားလိမ့်မည်ဖြစ်သည်။ အကယ်၍ database သည် containers များစွာကို လက်ခံဆောင်ရွက် (host) ပေးပါက :guilabel:`Tenant database` တွင် ပေးထားသည့်အမည်ဖြင့် tenant (software instance များသို့ သီးသန့်အခွင့်ခံစားမှုများနှင့်အတူ common access ကို မျှဝေပြီး သုံးစွဲသည့် သုံးစွဲသူအုပ်စု) တစ်ခုသို့ ချိတ်ဆက်နိုင်မည် သို့မဟုတ် system database သို့ ချိတ်ဆက်နိုင်မည်ဖြစ်ပါသည်။

* :guilabel:`Schema` - ဤသတ်မှတ်ချက်သည် စိတ်ကြိုက်ရွေးချယ်မှု (optional) ဖြစ်ပါသည်။ အကယ်၍ schema အမည်တစ်ခုကိုပေးထားပါက QGIS သည် အဆိုပါ schema ထဲရှိ data ကိုသာရှာဖွေမည်ဖြစ်ပါသည်။ အကယ်၍ ဤ field ကို ကွက်လပ်ထားခဲ့ပါက QGIS သည် data ကို schemas အားလုံးထဲတွင် ရှာဖွေမည်ဖြစ်ပါသည်။

* :menuselection:`Authentication --> Basic`
  * :guilabel:`User name` - Database ကို ချိတ်ဆက်ရန် အသုံးပြုသူ၏အမည် (User name)
  * :guilabel:`Password` - Database ကို ချိတ်ဆက်ရန် စကားဝှက် (Password)

* :guilabel:`SSL Settings`
  * |checkbox| :guilabel:`Enable TLS/SSL encryption` - TLS 1.1 - TLS1.2 encryption ကို ဖွင့်ပါ။ Server သည် ရရှိနိုင်သည်များထဲမှ အမြင့်ဆုံးကို ရွေးချယ်မည်ဖြစ်ပါသည်။ 
  * :guilabel:`Provider` - SSL communication အတွက် အသုံးပြုသည့် cryptographic library provider ကို သတ်မှတ်ပါသည်။ :guilabel:`sapcrypto` သည် ပလက်ဖောင်းအားလုံးတွင် ကောင်းစွာအလုပ်လုပ်သင့်ပါသည်။ :guilabel:`openssl` သည် |nix| |osx| အပေါ်တွင် ၊ :guilabel:`mscrypto` သည် |win| အပေါ်တွင် ကောင်းစွာအလုပ်လုပ်သင့်ပါသည်။ :guilabel:`commoncrypto` သည် CommonCryptoLib ကို ထည့်သွင်းတည်ဆောက်ထားရန်လိုအပ်ပါသည်။ 
  * |checkbox| :guilabel:`Validate SSL certificate` - အကယ်၍ အမှန်ခြစ်ထားပါက :guilabel:`Trust store file with public key` ထဲတွင် ပေးထားသည့် truststore ကိုအသုံးပြုပြီး SSL certificate ကို အတည်ပြုမည် (validate) ဖြစ်ပါသည်။ 
  * :guilabel:`Override hostname in certificate` - Server ၏ အထောက်အထား (identity) ကို သက်သေပြရန် host အမည် ကို သတ်မှတ်သည်။ ဤနေရာတွင် သတ်မှတ်ထားသည့် host အမည်သည် ချိတ်ဆက်မှုကို တည်ဆောက်ထားသည့် host အမည်အစား server ၏ အထောက်အထား (identity) ကို သက်သေပြ (verify) ပါသည်။ အကယ်၍ ``*`` ကို host အမည် အဖြစ်သတ်မှတ်ပါက server ၏ host အမည် မှန်ကန်ကြောင်းအတည်ပြုနိုင်မည်မဟုတ်ပါ။ အခြားသော wildcard များကို ခွင့်ပြုထားခြင်းမရှိပါ။ 
  * :guilabel:`Keystore file with private key` - လက်ရှိတွင် လျစ်လျူရှုထားပါသည်။ ဤ သတ်မှတ်ချက်သည် နောင်တွင် user နှင့် password အစား အသိအမှတ်ပြုအထောက်အထား (certificate) မှတဆင့် မှန်ကန်ကြောင်းအတည်ပြုစစ်ဆေးခြင်း (authenticate) ကိုဆောင်ရွက်ရန်ခွင့်ပြုပါသည်။ 
  * :guilabel:`Trust store file with public key` - အကယ်၍ OpenSSL ကို အသုံးပြုနေပါက server ၏ public certificates များပါဝင်သည့် trust store file သို့ လမ်းကြောင်းကို သတ်မှတ်ပါသည်။ ယေဘုယျအားဖြင့် trust store တွင် root certificate သို့မဟုတ် server ၏ public certificate များကို လက်မှတ်ရေးထိုးထားသည့် အသိအမှတ်ပြုလက်မှတ်ဆိုင်ရာအာဏာပိုင်၏ အသိအမှတ်ပြုလက်မှတ် ပါဝင်ပါသည်။ အကယ်၍ cryptographic library CommonCryptoLib သို့မဟုတ် msCrypto ကို အသုံးပြုနေပါက ဤ property ကို အလွတ်ထားပါ။
* |checkbox| :guilabel:`Only look for user's tables` - အကယ်၍ အမှန်ခြစ်ထားပါက QGIS ရှာဖွေမှုများသည် database ကို ချိတ်ဆက်ထားပြီး အသုံးပြုသူမှ ပိုင်ဆိုင်ထားသည့် tables နှင့် views ကိုသာရှာဖွေမည်ဖြစ်ပါသည်။
* |checkbox| :guilabel:`Also list tables with no geometries` - အကယ်၍ အမှန်ခြစ်ထားပါက QGIS ရှာဖွေမှုများသည် spatial column တစ်ခုမပါရှိသည့် tables နှင့် views ကိုပါရှာဖွေမည်ဖြစ်ပါသည်။ 

.. tip:: **SAP HANA Cloud ကို ချိတ်ဆက်ခြင်း**

   SAP HANA Cloud instance တစ်ခုကို ချိတ်ဆက်လိုပါက များသောအားဖြင့် :guilabel:`Port Number` ကို ``443`` သို့ သတ်မှတ်ရမည်ဖြစ်ပြီး :guilabel:`Enable TLS/SSL encryption` ကို အမှန်ခြစ်ပြုလုပ်ရမည်ဖြစ်ပါသည်။ 

.. _vector_loading_database:

Loading a Database Layer (Database Layer တစ်ခုကို ထည့်သွင်းခြင်း)
..................................................................

Database တစ်ခုသို့ သတ်မှတ်ထားသည့် တစ်ခု သို့မဟုတ် တစ်ခုထက်ပိုသော ချိတ်ဆက်မှုများ (connections) များရှိပါက (:ref:`vector_create_stored_connection` section ကိုကြည့်ရှုပါ) layer များကို ၎င်းမှ ထည့်သွင်းနိုင်ပါသည်။ အဆိုပါ data များသည် available ဖြစ်ရန် လိုအပ်ပါသည်။ Data ကို PostGIS database တစ်ခုထဲသို့ import ပြုလုပ်ခြင်းအပေါ် ဆွေးနွေးထားသည့် ဆွေးနွေးချက်တစ်ခုအတွက် :ref:`vector_import_data_in_postgis` section ကိုကြည့်ပါ။ 

Database တစ်ခုမှ layer တစ်ခုကို ထည့်သွင်းရန် အောက်ဖော်ပြပါအဆင့်များကို ဆောင်ရွက်နိုင်ပါသည်-

#. "Add <database> table(s)" dialog ကိုဖွင့်ပါ။ (:ref:`vector_create_stored_connection` တွင်ကြည့်ပါ)
#. Drop-down list မှ ချိတ်ဆက်မှု (connection) ကို ရွေးချယ်ပြီး :guilabel:`Connect` ကို ကလစ်နှိပ်ပါ။ 
#. |checkbox| :guilabel:`Also list tables with no geometry` ကို Select သို့မဟုတ် unselect ပြုလုပ်ပါ။ 
#. ရွေးချယ်မှုအနေဖြင့် ရှာဖွေမှုနှင့် ကိုက်ညီသော table များစာရင်းကို လျှော့ချရန် |checkbox| :guilabel:`Search Options` အချို့ကို အသုံးပြုပါ။ ဤနည်းလမ်းကို  :guilabel:`Connect` button အား မနှိပ်မီတွင် သတ်မှတ်နိုင်ပါသည်။ ၎င်းသည် database များ ကူးပြောင်းခြင်း (database fetching) ကို မြန်ဆန်စေမည်ဖြစ်ပါသည်။ 
#. ရရှိနိုင်သည့် layer များစာရင်းထဲတွင် ထည့်သွင်းလိုသည့် layer (များ) ကို ရှာဖွေပါ။ 
#. ၎င်းအပေါ်တွင် ကလစ်နှိပ်ခြင်းဖြင့် ၎င်းကို select ပြုလုပ်ပါ။ ကလစ်ပြုလုပ်နေစဉ်တွင် :kbd:`Shift` သို့မဟုတ် :kbd:`Ctrl` key ကို ဖိထားပြီး တစ်ခုထက်ပိုသော layer များ (multiple layers) ကို select ပြုလုပ်နိုင်ပါသည်။ 
#. ရရှိနိုင်ပါက :guilabel:`Query Builder` dialog ကို စတင်ရန် (:ref:`vector_query_builder` section တွင် ကြည့်ပါ) နှင့် select ပြုလုပ်ထားသည့် layer မှ မည်သည့် features များ ထည့်သွင်းမည်ကို သတ်မှတ်ရန် :guilabel:`Set Filter` button ကို အသုံးပြုပါ။(သို့မဟုတ် layer ကို ကလစ်နှစ်ချက်နှိပ်ခြင်း) Filter expression သည်  ``sql`` column ထဲတွင် ပေါ်လာမည်ဖြစ်ပါသည်။ ဤသတ်မှတ်ချက်ကို :menuselection:`Layer Properties --> General --> Provider Feature Filter` frame ထဲတွင် ဖယ်ရှားခြင်း (remove) သို့မဟုတ် ပြန်လည်ပြင်ဆင်ခြင်း (edit) ပြုလုပ်နိုင်ပါသည်။ 
#. ပုံမှန်အားဖြင့် activate ပြုလုပ်ထားသည့် ``Select at id`` column ရှိ checkbox သည် attribute များမပါရှိဘဲ feature ids များကို ရရှိစေပြီး data များထည့်သွင်းခြင်းကို မြန်ဆန်စေပါသည်။ 
#. Layer ကို map ထဲသို့ ထည့်သွင်းရန် :guilabel:`Add` button အပေါ်တွင် click နှိပ်ပါ။


.. _figure_add_postgis_tables:

.. figure:: img/addpostgistables.png
   :align: center

   PostGIS ဇယား(များ) ထည့်သွင်းခြင်း Dialog


.. tip:: **Database table(s) များ ထည့်သွင်းခြင်းကို မြန်ဆန်စေရန် Browser Panel ကိုအသုံးပြုပါ။**

  :guilabel:`Data Source Manager` မှ DB tables (DB ဇယားများ) ကို ထည့်သွင်းခြင်းသည် QGIS အနေဖြင့် ဇယားတစ်ခုချင်းစီအတွက် statistics (စာရင်းဇယားများ) နှင့် properties (ဂုဏ်သတ္တိများ) (ဥပမာ- geometry အမျိုးအစားနှင့် field ၊ CRS ၊ features အရေအတွက်များ) ကို ကြိုတင်ကူးပြောင်း (fetches) ရသည့်အတွက် တစ်ခါတစ်ရံတွင် အချိန်ကုန် (time consuming) စေပါသည်။
  ၎င်းကို ရှောင်ရှားရန် :ref:`the connection is set (ချိတ်ဆက်မှုသတ်မှတ်ခြင်း) <vector_create_stored_connection>` ကို ဆောင်ရွက်ပြီးသည်နှင့်တစ်ပြိုင်နက် database ဇယားများ ကို map canvas ထဲသို့ drag and drop ပြုလုပ်ပြီး ထည့်သွင်းရန်အတွက် 
  :ref:`Browser Panel <browser_panel>` သို့မဟုတ် :ref:`DB Manager <dbmanager>` ကို အသုံးပြုခြင်းသည် ပိုမိုကောင်းမွန်ပါသည်။ 
   
.. _layer_metadata_search_panel:

The Layer Metadata Search Panel (Layer ၏ Metadata များကို ရှာဖွေသည့် Panel)
============================================================================

Layer ၏ Metadata များကို ရှာဖွေသည့် Panel (The Layer Metadata Search Panel) သည် စာရင်းသွင်းထားသည့် metadata providers များထဲတွင် layers metadata များကို ရှာဖွေကြည့်ရှုခြင်း (browse) နှင့် ၎င်းတို့ကို project ထဲသို့ ထည့်သွင်းခြင်းကို ခွင့်ပြုပါသည်။ 

စာရင်း (list) ကို စာသားဖြင့်၊ လက်ရှိ project ဖြင့်၊ map canvas (မြေပုံရေးဆွဲသည့်နေရာ) ၏ နယ်ပယ်အတိုင်းအတာပမာဏ (extent) ဖြင့်  စစ်ထုတ်နိုင်ပါသည်။ 

Plugin များဖြင့် ထပ်မံချဲ့ထွင်နိုင်သည့် layer metadata provider system တစ်ခု မှတစ်ဆင့် Metadata ၏ ရင်းမြစ်များ (sources) ကို အကောင်အထည်ဖော်ရွက်ခြင်း ပြုလုပ်နိုင်ပါသည်။ 

QGIS သည် metadata သိမ်းဆည်းသိုလှောင်မှု (storage) ကို ခွင့်ပြုသည့် ချိတ်ဆက်မှုများ (connections) မှ metadata ကို ပြန်လည်ရယူခြင်း (retrieve) ပြုလုပ်နိုင်ရန် out of the box layer metadata providers များကို ပံ့ပိုးပေးပါသည်။ (နောက်ထပ်အသေးစိတ်အချက်အလက်များကို :ref:`save metadata to the database <savemetadatatodb>` တွင်ကြည့်ရှုရန်)

.. figure:: img/layer_metadata_search_panel.png
   :align: center

   Layer ၏ Metadata များကို ရှာဖွေသည့် Panel

QGIS Custom formats (QGIS ၏ စိတ်ကြိုက် formats များ)
=====================================================

QGIS သည် ဖော်ပြပါ custom (စိတ်ကြိုက်) formats (၂) မျိုးကို အဆိုပြုပါသည်-

* Temporary Scratch Layer - Project နှင့် ချိတ်ဆက်ထားသည့် memory layer တစ်ခု (နောက်ထပ်အချက်အလက်များအတွက် :ref:`vector_new_scratch_layer` တွင်ကြည့်ရှုပါ။)
* Virtual Layers - အခြားသော layer (များ) အပေါ်ရှိ query တစ်ခုထံမှ ရရှိလာသည့် layer တစ်ခု (နောက်ထပ်အချက်အလက်များအတွက် :ref:`vector_virtual_layers` တွင်ကြည့်ရှုပါ။)

.. index:: QGIS Layer Definition File, QLR file

QLR - QGIS Layer Definition File
=================================

Layer definitions (layer အတွက် QGIS style information အပြင် layer data source ဆီသို့ ညွှန်ပြမှုပါဝင်သည့် XML file တစ်ခု) များကို layer context menu ထဲရှိ :menuselection:`Export --> Save As Layer Definition File...`  ကို အသုံးပြု၍ 
:ref:`Layer Definition File <qgislayerdefinitionfile>` (QLR - :file:`.qlr`) (Layer definition file ဆိုသည်မှာ layer တစ်ခုချင်းစီကို ပြင်ဆင်ထည့်သွင်းပြီး အခြားသူများနှင့်မျှဝေရန်၊ layer များ၏ color များ၊ symbol များနှင့် label များကို ဖန်တီးထားပြီး ပြင်ဆင်ထားသောဖိုင်တစ်ခုဖြစ်ပါသည်) တစ်ခုအဖြစ်သို့သိမ်းဆည်းနိုင်ပါသည်။

QLR format သည် လုံးဝပြီးပြည့်စုံမှုရှိသည့် "complete" QGIS layers များကို အခြားသော QGIS အသုံးပြုသူများနှင့် မျှဝေနိုင်မည်ဖြစ်ပါသည်။ QLR files များတွင် data sources သို့ ချိတ်ဆက်ထားသည့် links များ နှင့် layer တစ်ခုကို ဆင်ယင်မှု(style) ပြုလုပ်ရန် လိုအပ်သည့် QGIS style information များ ပါဝင်ပါသည်။

QLR files များကို Browser Panel ထဲတွင် ပြသထားပြီး Layers Panel ထဲသို့ layers များ (၎င်းတို့၏သိမ်းဆည်းထားသည့်စတိုင်များနှင့်အတူ) ကို ထည့်သွင်းရန် အသုံးပြုနိုင်ပါသည်။ System file manager (system file များကို စီမံခန့်ခွဲသည့်နေရာ) မှ map canvas ထဲသို့ QLR files များကို drag and drop လည်းပြုလုပ်နိုင်ပါသည်။

Connecting to web services (Web service များသို့ ချိတ်ဆက်ခြင်း)
================================================================

QGIS ဖြင့် အမျိုးမျိုးသော OGC web services (WM(T)S ၊ WFS(-T) ၊ WCS ၊ CSW ၊ ...) များကို ဝင်ရောက်ကြည့်ရှုသုံးစွဲခွင့် (access) ကို ရရှိနိုင်ပါသည်။ QGIS Server ကြောင့် အဆိုပါဝန်ဆောင်မှုများ (services) ကိုလည်း ဖြန့်ဝေ (publish) နိုင်ပါသည်။ :ref:`QGIS-Server-manual` တွင် အဆိုပါ စွမ်းဆောင်ရည်များ (capabilities) ၏ ဖော်ပြချက်များ (descriptions) ပါဝင်ပါသည်။

.. index:: Vector Tiles services
.. _vector_tiles:

Using Vector Tiles services (Vector Tiles service များကို အသုံးပြုခြင်း)
-------------------------------------------------------------------------

Vector Tile services (vector tiles များနှင့် vector tile style resources များကို ဝင်ရောက်အသုံးပြုခွင့်ပံ့ပိုးပေးပြီး သိမ်းဆည်းပေးသည့် data service အမျိုးအစားတစ်ခု) များကို :guilabel:`Data Source Manager` dialog ၏ |addVectorTileLayer| :guilabel:`Vector Tiles` tab သို့မဟုတ် :guilabel:`Browser` panel ထဲရှိ :guilabel:`Vector Tiles` entry ၏ contextual menu မှတစ်ဆင့် ထည့်သွင်းနိုင်ပါသည်။ Service များသည် :guilabel:`New Generic Connection...`  တစ်ခု သို့မဟုတ် :guilabel:`New ArcGIS Vector Tile Service Connection...` တစ်ခု ဖြစ်နိုင်ပါသည်။ 

Service တစ်ခုကို ဖော်ပြပါတို့ကို ထည့်သွင်းခြင်းဖြင့် သတ်မှတ်နိုင်ပါသည်-

* :guilabel:`Name` (နာမည်) တစ်ခု
* Generic services အတွက် ``http://example.com/{z}/{x}/{y}.pbf`` အမျိုးအစား၏ :guilabel:`URL` နှင့် 
  ArcGIS အခြေပြု services များအတွက် ``http://example.com/arcgis/rest/services/Layer/VectorTileServer``။ Service သည် tiles များကို  :file:`.pbf` format ဖြင့် ပံ့ပိုးပေးရမည်ဖြစ်ပါသည်။
* |checkbox|:guilabel:`Min. Zoom Level` နှင့်  |checkbox|:guilabel:`Max. Zoom Level`
  Vector Tiles (web ပေါ်တွင် ကူးပြောင်းမှုများအတွက် ကြိုတင်သတ်မှတ်ထားသော အကြမ်းဖျင်းအားဖြင့် စတုရန်းပုံသဏ္ဍာန်ရှိသော "tiles" များအဖြစ်သို့ စုစည်းထားသည့် geographic data ပက်ကေ့ချ်များ) များသည် ပိရမစ်ပုံစံဖွဲ့စည်းတည်ဆောက်မှုရှိပါသည်။ ဤနည်းလမ်းများအား အသုံးပြုခြင်းဖြင့် tile pyramid မှ layers များကို တစ်ခုချင်းစီ ထုတ်လုပ် (generate) နိုင်သည့် အခွင့်အရေးရှိမည်ဖြစ်ပါသည်။ အဆိုပါ layer များကို QGIS ထဲတွင် Vector Tile ကို render ဆောင်ရွက်ရန်အတွက် နောက်ပိုင်းတွင် အသုံးပြုလိမ့်မည်ဖြစ်ပါသည်။

  Mercator projection အတွက် (OpenStreetMap Vector Tiles များမှ အသုံးပြုပါသည်) Zoom Level 0 သည် ကမ္ဘာကြီးတစ်ခုလုံးကို 1:500.000.000 စကေးအတိုင်းအတာဖြင့် ကိုယ်စားပြုဖော်ပြပါသည်။ Zoom Level 14 သည် ကမ္ဘာကြီးတစ်ခုလုံးကို 1:35.000 စကေးအတိုင်းအတာဖြင့် ကိုယ်စားပြုဖော်ပြပါသည်။
* :guilabel:`Style URL` - MapBox GL JSON style configuration တစ်ခုသို့ URL။ အကယ်၍ ပံ့ပိုးပေးထားပါက ချိတ်ဆက်မှု (connection) ရှိ layer များကို QGIS ထဲသို့ ထည့်သွင်းသည့်အခါတိုင်းတွင် အဆိုပါ style ကို အသုံးပြုမည်ဖြစ်ပါသည်။ Arcgis vector tile service connection များတွင် URL သည် server configuration တွင် သတ်မှတ်ထားသည့် default style configuration ကို ပြန်လည်ပြင်ဆင်ပါသည်။ 
* လိုအပ်ပါက :ref:`authentication <authentication_index>` configuration
* :guilabel:`Referer` တစ်ခု

:numref:`figure_vector_tiles_maptilerplanet` သည် MapTiler planet Vector Tiles service ပြင်ဆင်သတ်မှတ်ခြင်း dialog ကိုပြသသည်။ 

.. _figure_vector_tiles_maptilerplanet:

.. figure:: img/vector_tiles_maptilerplanet.png
   :align: center

   Vector Tiles - Maptiler Planet ပြင်ဆင်သတ်မှတ်ခြင်း 

Configuration များကို :guilabel:`Browser` panel ထဲရှိ ၎င်း၏ context menu မှတစ်ဆင့် သို့မဟုတ် 
:guilabel:`Data Source Manager` dialog ထဲရှိ :guilabel:`Vector Tiles` entry မှတစ်ဆင့် :file:`.XML` file (:guilabel:`Save Connections`) ထဲသို့ သိမ်းဆည်းနိုင်ပါသည်။ ထို့နည်းတူစွာပင် ၎င်းတို့ကို (:guilabel:`Load Connections`) ဖိုင်တစ်ခုမှ ထည့်သွင်းနိုင်ပါသည်။

Vector tile service တစ်ခုသို့ ချိတ်ဆက်မှု (connection) တစ်ခုကို သတ်မှတ်ပြီးသည်နှင့်တစ်ပြိုက်နက် အောက်ပါတို့ကို ဆောင်ရွက်နိုင်ပါသည်- 

* Vector tile connection settings ကို :guilabel:`Edit` ပြုလုပ်ခြင်း
* ချိတ်ဆက်မှု (connection) ကို :guilabel:`Remove` ပြုလုပ်ခြင်း
* :guilabel:`Browser` panel မှ entry အပေါ်တွင် right-click ပြုလုပ်ပြီး အောက်ပါတို့ကိုလည်း ဆောင်ရွက်နိုင်ပါသည်-

  * :guilabel:`Add layer to project` - Double-click ပြုလုပ်ခြင်းသည် layer ကို ထည့်သွင်းမည်ဖြစ်ပါသည်။ 
  * :guilabel:`Layer Properties...` ကြည့်ရှုပြီး service မှ ပံ့ပိုးထားသည့် data ကို ကြိုတင်ကြည့်ရှုခြင်း (preview) နှင့် metadata သို့ ဝင်ရောက်ကြည့်ရှုသုံးစွဲခြင်း (access) တို့ကို ရယူပါ။ Project ထဲသို့ layer ကို ထည့်သွင်းသည့်အခါတွင် နောက်ထပ် setting များကို ရရှိမည်ဖြစ်ပါသည်။
    
.. index:: XYZ Tile services
.. _xyz_tile:

Using XYZ Tile services (XYZ Tile service များကို အသုံးပြုခြင်း)
-----------------------------------------------------------------

XYZ Tile services များကို :guilabel:`Data Source Manager` dialog ၏ |addXyzLayer| :guilabel:`XYZ` tab မှတစ်ဆင့် 
သို့မဟုတ် :guilabel:`Browser` panel ထဲရှိ :guilabel:`XYZ Tiles` entry ၏ contextual menu မှတစ်ဆင့် ထည့်သွင်းနိုင်သည်။ 
:guilabel:`New` (သက်ဆိုင်ရာ :guilabel:`New Connection`) ကို နှိပ်ပြီး အောက်ပါတို့ကို ထည့်သွင်းပါ- 

* :guilabel:`Name` (နာမည်) တစ်ခု
* :guilabel:`URL`
* လိုအပ်ပါက :ref:`authentication <authentication_index>` configuration 
* :guilabel:`Min. Zoom level` နှင့် :guilabel:`Max. Zoom level` (အနိမ့်ဆုံး zoom level နှင့် အမြင့်ဆုံး zoom level)
* :guilabel:`Referer` တစ်ခု
* :guilabel:`Tile Resolution` - ဖြစ်နိုင်သောတန်ဖိုးများမှာ :guilabel:`Unknown (not scaled)` ၊ :guilabel:`Standard (256x256 / 96DPI)`နှင့် :guilabel:`High (512x512 / 192DPI)` တို့ဖြစ်ပါသည်။ 

.. _interpretation:

* :guilabel:`Interpretation` - WMTS/XYZ raster datasets များကို ကြိုတင်သတ်မှတ်ထားသော encoding scheme တစ်ခုကို လိုက်နာသည့် single band float type (ရောင်စဉ်တစ်ခုသာပါဝင်ပြီး ဒဿမပွိုင့်များပါဝင်သည့် အပေါင်းသို့မဟုတ် အနုတ်ကိန်းပြည့်အမျိုးအစား) raster layer တစ်ခု အဖြစ်သို့ ပြောင်းလဲသည်။ ပံ့ပိုးပေးထားသည့် schemes များမှာ :guilabel:`Default` (မည်သည့်ပြောင်းလဲမှု(conversion) ကိုမှ ဆောင်ရွက်ထားခြင်းမရှိပါ)၊ :guilabel:`MapTiler Terrain RGB` နှင့် :guilabel:`Terrarium Terrain RGB` တို့ဖြစ်ပါသည်။ Select ပြုလုပ်ထားသည့် converter သည် pixel တစ်ခုချင်းစီအတွက် RGB source values (အနီရောင်၊ အစိမ်းနှင့် အပြာရောင်များ၏ ရင်းမြစ်များ၏တန်ဖိုးများ) များကို float values (ဒဿမပွိုင့်များပါဝင်သည့် အပေါင်းသို့မဟုတ် အနုတ်ကိန်းပြည့်များ) များအဖြစ်သို့ပြောင်းလဲမည်ဖြစ်သည်။ ထည့်သွင်းလိုက်သည်နှင့်တစ်ပြိုင်နက် layer သည် QGIS ၏ ပုံမှန် :ref:`raster renderers <raster_rendering>` ကို အသုံးပြု၍ styling အတွက် အဆင်သင့်ဖြစ်နေသည့် single band floating point raster layer အဖြစ်ကိုယ်စားပြုဖော်ပြမည်ဖြစ်ပါသည်။ 

ပုံမှန်အားဖြင့် QGIS သည် default အချို့နှင့် အဆင်သင့်အသုံးပြုနိုင် (ready-to-use) သည့် XYZ Tiles services များကို ပံ့ပိုးပေးထားပါသည်-

* |xyz| :guilabel:`Mapzen Global Terrain` - Projects များအတွက် ကမ္ဘာလုံးဆိုင်ရာ DEM source များအား ချက်ချင်းဝင်ရောက်သုံးစွဲကြည့်ရှုခွင့်ကို ခွင့်ပြုသည်။ နောက်ထပ်အသေးစိတ်အချက်အလက်များနှင့် resources(အရင်းအမြစ်များ)ကို  https://registry.opendata.aws/terrain-tiles/ တွင် ကြည့်ရှုပါ။ 
* |xyz| :guilabel:`OpenStreetMap` - ကမ္ဘာကြီး၏ 2D မြေပုံကို ဝင်ရောက်သုံးစွဲကြည့်ရှုခွင့် (access) ရရှိရန်။ :numref:`figure_xyz_tiles_openstreetmap` သည် OpenStreetMap XYZ Tile service configuration ပါဝင်သည့် dialogကိုပြသပါသည်။ 
  
.. _figure_xyz_tiles_openstreetmap:
.. figure:: img/xyz_tiles_dialog_osm.png
     :align: center

     XYZ Tiles - OpenStreetMap ပြင်ဆင်သတ်မှတ်ခြင်း

Configuration များကို :guilabel:`Browser` panel ထဲရှိ ၎င်း၏ context menu မှတစ်ဆင့် သို့မဟုတ် 
:guilabel:`Data Source Manager` dialog ထဲရှိ :guilabel:`XYZ Tiles`entry မှတစ်ဆင့် :file:`.XML` file (:guilabel:`Save Connections`) ထဲသို့ သိမ်းဆည်းနိုင်ပါသည်။ ထို့နည်းတူစွာပင် ၎င်းတို့ကို (:guilabel:`Load Connections`) ဖိုင်တစ်ခုမှထည့်သွင်းနိုင်ပါသည်။

OpenStreetMap အတွက် XML file သည် အောက်ပါအတိုင်းဖြစ်ပါသည်-

.. code-block:: xml

  <!DOCTYPE connections>
  <qgsXYZTilesConnections version="1.0">
    <xyztiles url="https://tile.openstreetmap.org/{z}/{x}/{y}.png"
     zmin="0" zmax="19" tilePixelRatio="0" password="" name="OpenStreetMap"
     username="" authcfg="" referer=""/>
  </qgsXYZTilesConnections>

XYZ tile service တစ်ခုသို့ ချိတ်ဆက်မှု (connection) တစ်ခုကို သတ်မှတ်ပြီးသည်နှင့်တစ်ပြိုက်နက် အောက်ပါတို့ကို ဆောင်ရွက်နိုင်ပါသည်-

* XYZ connection settings ကို :guilabel:`Edit` ပြုလုပ်ခြင်း
* Connection ကို :guilabel:`Remove` ပြုလုပ်ခြင်း
* :guilabel:`Browser` panel - Entry အပေါ်တွင် right-click ပြုလုပ်ပြီး အောက်ပါတို့ကိုလည်း ဆောင်ရွက်နိုင်ပါသည်- 

  * :menuselection:`Export layer... --> To File` - :ref:`saving it as a raster (Raster တစ်ခုအနေဖြင့် သိမ်းဆည်းခြင်း)
    <general_saveas>`
  * :guilabel:`Add layer to project` - Double-click ပြုလုပ်ခြင်းသည် layer ကို ထည့်သွင်းမည်ဖြစ်ပါသည်။ 
  * :guilabel:`Layer Properties...` ကြည့်ရှုပြီး service မှ ပံ့ပိုးထားသည့် dataကို ကြိုတင်ကြည့်ရှုခြင်း (preview) နှင့် 
    metadata သို့ ဝင်ရောက်သုံးစွဲခွင့်ရှိခြင်း (access) တို့ကို ရယူပါ။ Project ထဲသို့ layer ကို ထည့်သွင်းသည့်အခါတွင် နောက်ထပ် setting များကို ရရှိမည်ဖြစ်ပါသည်။

XYZ Tile services နမူနာများမှာ-

* OpenStreetMap Monochrome -
  :guilabel:`URL`: ``http://tiles.wmflabs.org/bw-mapnik/{z}/{x}/{y}.png``,
  :guilabel:`Min. Zoom Level (အနိမ့်ဆုံး zoom level)`: 0, :guilabel:`Max. Zoom Level (အမြင့်ဆုံး zoom level)`: 19.
* Google Maps -
  :guilabel:`URL`: ``https://mt1.google.com/vt/lyrs=m&x={x}&y={y}&z={z}``,
  :guilabel:`Min. Zoom Level (အနိမ့်ဆုံး zoom level)`: 0, :guilabel:`Max. Zoom Level (အမြင့်ဆုံး zoom level)`: 19.
* Open Weather Map Temperature -
  :guilabel:`URL`: ``http://tile.openweathermap.org/map/temp_new/{z}/{x}/{y}.png?appid={api_key}``
  :guilabel:`Min. Zoom Level (အနိမ့်ဆုံး zoom level)`: 0, :guilabel:`Max. Zoom Level (အမြင့်ဆုံး zoom level)`: 19.


.. index:: ArcGIS REST Servers
.. _arcgis_rest:

Using ArcGIS REST Servers (ArcGIS REST Servers များကို အသုံးပြုခြင်း)
----------------------------------------------------------------------

ArcGIS REST Servers များကို :guilabel:`Data Source Manager` dialog ၏ |addAfsLayer| :guilabel:`ArcGIS REST Server` tab မှတစ်ဆင့် သို့မဟုတ် :guilabel:`Browser` panelထဲရှိ :guilabel:`ArcGIS REST Servers` entry ၏ contextual menu မှတစ်ဆင့် ထည့်သွင်းနိုင်ပါသည်။ :guilabel:`New` (သက်ဆိုင်ရာ :guilabel:`New Connection`) ကိုနှိပ်ပြီး ဖော်ပြပါတို့ကို ထည့်သွင်းပါ-

* :guilabel:`Name` (နာမည်) တစ်ခု
* :guilabel:`URL`
* :guilabel:`Community endpoint URL` တစ်ခု
* :guilabel:`Content endpoint URL` တစ်ခု
* လိုအပ်ပါက :ref:`authentication <authentication_index>` configuration 
* :guilabel:`Referer` တစ်ခု 

.. note::

   သက်ဆိုင်ရာ Portal endpoint URLS set များပါရှိသည့် ArcGIS Feature Service connections များကို browser panel ထဲရှိ content groups (content များပါရှိသည့်အုပ်စုများ) များဖြင့် ရှာဖွေလေ့လာဖော်ထုတ်နိုင်ပါသည်။ 

   အကယ်၍ ချိတ်ဆက်မှု (connection) တစ်ခုတွင်  Portal endpoints set ပါရှိပါက browser ထဲရှိ ချိတ်ဆက်မှု(connection) အား ဖြန့်ချခြင်း(expanding) သည် ပုံမှန်ပြသလေ့ရှိသည့် services စာရင်းအပြည့်အစုံအစား “Groups(အုပ်စုများ)” နှင့် “Services(ဝန်ဆောင်မှုများ)” folder တစ်ခုကို ပြသမည်ဖြစ်ပါသည်။ Groups folder (အုပ်စုများပါရှိသည့် folder) ကို ဖြန့်ချခြင်း(expanding) သည် အသုံးပြုသူမှ အဖွဲ့ဝင်ဖြစ်နေသည့် content groups အားလုံး၏ စာရင်းကို ပြသမည်ဖြစ်ပြီး အဆိုပါ group နှင့် သက်ဆိုင်သည့် service items များကို ပြသရန် ၎င်းတို့ထဲမှ တစ်ခုချင်းစီကို ဖြန့်ချခြင်း(expanding) ပြုလုပ်နိုင်ပါသည်။ 

Configuration များကို :guilabel:`Data Source Manager` dialog ထဲရှိ :guilabel:`ArcGIS REST Server` entry မှတစ်ဆင့် :file:`.XML` file (:guilabel:`Save Connections`) ထဲသို့သိမ်းဆည်းနိုင်ပါသည်။ အလားတူပင် ၎င်းတို့ကို (:guilabel:`Load Connections`) ဖိုင်တစ်ခုမှ ထည့်သွင်းနိုင်ပါသည်။ 

ArcGIS REST Server သို့ ချိတ်ဆက်မှု (connection) တစ်ခုကို သတ်မှတ်ပြီးသည်နှင့်တစ်ပြိုင်နက် ဖော်ပြပါတို့ကို ဆောင်ရွက်ရန်ဖြစ်နိုင်ပါသည်-

* ArcGIS REST Server connection settings ကို :guilabel:`Edit`  ပြုလုပ်သည်။
* ချိတ်ဆက်မှု (connection) ကို :guilabel:`Remove` (ဖယ်ရှား) ပြုလုပ်သည်။
* ချိတ်ဆက်မှု (connection) ကို :guilabel:`Refresh` ပြုလုပ်သည်။
* ရရှိနိုင်သည့် layers များအတွက် filter (စစ်ထုတ်ခြင်း) တစ်ခုကို အသုံးပြုသည်။
* |checkbox|:guilabel:`Only request features overlapping the current view extent (လက်ရှိမြင်ကွင်း extent နှင့် ထပ်နေသည့် feature များကိုသာ တောင်းဆိုခြင်း)` နည်းလမ်းနှင့်အတူ ရရှိနိုင်သည့် layer list တစ်ခုမှ ရွေးချယ်နိုင်သည်။ 

* :guilabel:`Browser` panel မှ connection entry (ချိတ်ဆက်ခြင်းဆိုင်ရာ entry) အပေါ်တွင် right-click ပြုလုပ်ပြီး အောက်ပါတို့ကို ဆောင်ရွက်နိုင်ပါသည်-

  * :guilabel:`Refresh` ပြုလုပ်ခြင်း
  * :guilabel:`Edit connection...` ပြုလုပ်ခြင်း
  * :guilabel:`Remove connection...` ပြုလုပ်ခြင်း
  * :guilabel:`View Service Info` default web browser ကိုဖွင့်မည်ဖြစ်ပြီး Service Info (ဝန်ဆောင်မှုဆိုင်ရာအချက်အလက်) ကိုပြသမည်ဖြစ်ပါသည်။ 
  
* Layer entry အပေါ်တွင် Right-click ပြုလုပ်ပြီး ဖော်ပြပါတို့ကိုဆောင်ရွက်နိုင်ပါသည်-

  * :guilabel:`View Service Info` - ၎င်းသည် default web browser ကိုဖွင့်မည်ဖြစ်ပြီး Service Info(ဝန်ဆောင်မှုဆိုင်ရာအချက်အလက်) ကိုပြသနိုင်ပါသည်။
  * :menuselection:`Export layer... --> To File` (Layer ကို file အဖြစ်သို့ export ပြုလုပ်ခြင်း)
  * :guilabel:`Add layer to project` - Double-click ဖြင့်လည်း layer ကို ထည့်သွင်းနိုင်မည်ဖြစ်ပါသည်။
  * :guilabel:`Layer Properties...` ကို ကြည့်ရှုပြီး metadata နှင့် service မှ ပံ့ပိုးထားသည့် data အား preview (ကြိုတင်ကြည့်ရှုခြင်း) ကို ဝင်ရောက်ကြည့်ရှုသုံးစွဲခွင့်ကိုရရှိပါသည်။ Project ထဲသို့ layer ကို ထည့်သွင်းပြီးသည့်အခါတွင် နောက်ထပ် settings များကို ရရှိနိုင်ပါသည်။ 



.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |addAfsLayer| image:: /static/common/mActionAddAfsLayer.png
   :width: 1.5em
.. |addDelimitedTextLayer| image:: /static/common/mActionAddDelimitedTextLayer.png
   :width: 1.5em
.. |addHanaLayer| image:: /static/common/mActionAddHanaLayer.png
   :width: 1.5em
.. |addLayer| image:: /static/common/mActionAddLayer.png
   :width: 1.5em
.. |addMeshLayer| image:: /static/common/mActionAddMeshLayer.png
   :width: 1.5em
.. |addMssqlLayer| image:: /static/common/mActionAddMssqlLayer.png
   :width: 1.5em
.. |addOgrLayer| image:: /static/common/mActionAddOgrLayer.png
   :width: 1.5em
.. |addOracleLayer| image:: /static/common/mActionAddOracleLayer.png
   :width: 1.5em
.. |addPostgisLayer| image:: /static/common/mActionAddPostgisLayer.png
   :width: 1.5em
.. |addRasterLayer| image:: /static/common/mActionAddRasterLayer.png
   :width: 1.5em
.. |addSpatiaLiteLayer| image:: /static/common/mActionAddSpatiaLiteLayer.png
   :width: 1.5em
.. |addVectorTileLayer| image:: /static/common/mActionAddVectorTileLayer.png
   :width: 1.5em
.. |addXyzLayer| image:: /static/common/mActionAddXyzLayer.png
   :width: 1.5em
.. |afs| image:: /static/common/mIconAfs.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |collapseTree| image:: /static/common/mActionCollapseTree.png
   :width: 1.5em
.. |dataSourceManager| image:: /static/common/mActionDataSourceManager.png
   :width: 1.5em
.. |dbManager| image:: /static/common/dbmanager.png
   :width: 1.5em
.. |filterMap| image:: /static/common/mActionFilterMap.png
   :width: 1.5em
.. |geoPackage| image:: /static/common/mGeoPackage.png
   :width: 1.5em
.. |hana| image:: /static/common/mIconHana.png
   :width: 1.5em
.. |kde| image:: /static/common/kde.png
   :width: 1.5em
.. |metadata| image:: /static/common/metadata.png
   :width: 1.5em
.. |mssql| image:: /static/common/mIconMssql.png
   :width: 1.5em
.. |nix| image:: /static/common/nix.png
   :width: 1em
.. |oracle| image:: /static/common/mIconOracle.png
   :width: 1.5em
.. |osx| image:: /static/common/osx.png
   :width: 1em
.. |postgis| image:: /static/common/mIconPostgis.png
   :width: 1.5em
.. |radioButtonOff| image:: /static/common/radiobuttonoff.png
   :width: 1.5em
.. |radioButtonOn| image:: /static/common/radiobuttonon.png
   :width: 1.5em
.. |refresh| image:: /static/common/mActionRefresh.png
   :width: 1.5em
.. |setProjection| image:: /static/common/mActionSetProjection.png
   :width: 1.5em
.. |spatialite| image:: /static/common/mIconSpatialite.png
   :width: 1.5em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
.. |vectorTileLayer| image:: /static/common/mIconVectorTileLayer.png
   :width: 1.5em
.. |wcs| image:: /static/common/mIconWcs.png
   :width: 1.5em
.. |wfs| image:: /static/common/mIconWfs.png
   :width: 1.5em
.. |win| image:: /static/common/win.png
   :width: 1em
.. |wms| image:: /static/common/mIconWms.png
   :width: 1.5em
.. |xyz| image:: /static/common/mIconXyz.png
   :width: 1.5em
