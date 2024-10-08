.. _supported_format:

*******************************************************************************************
Exploring Data Formats and Fields (Data Format များနှင့် Field များကို လေ့လာဖော်ထုတ်ခြင်း)
*******************************************************************************************

.. only:: html

   .. contents::
      :local:

.. The aim of this chapter is to describe and add information on particular
   formats read/written by QGIS. Also their characteristics (particular geometry
   type, fields type...) would be exposed. The idea is to give keys to the
   reader to understand what he should be aware of when working with these
   formats or how he could improve working with them in QGIS.


Raster data
============

GIS raster data များသည် ကမ္ဘာ့မြေမျက်နှာပြင် အထက် သို့မဟုတ် အောက်ရှိ features (geometryနှင့် attribute data များပါဝင်သည့် entity တစ်ခု)/phenomena (ဖြစ်စဉ်များ) ကို ကိုယ်စားပြုဖော်ပြသည့် discrete cell များ (ပုံစံ သို့မဟုတ် သဘောတရားအားဖြင့် ကွဲပြားနေသည့် ဆဲလ်များ) ၏ matrices (data များအား စတုဂံပုံစုစည်းထားရှိမှု၊ matrices များကို raster data များကို သိမ်းဆည်းရန်အသုံးပြုပါသည်) များဖြစ်ပါသည်။ Raster grid ထဲရှိ ဆဲလ် (cell) တစ်ခုချင်းစီသည် တူညီသည့် အရွယ်အစား (size) ရှိပြီး ပုံမှန်အားဖြင့် ထောင့်မှန်စတုဂံများ (QGIS တွင် ၎င်းတို့သည် အမြဲ ထောင့်မှန်စတုဂံ ဖြစ်မည်ဖြစ်ပါသည်) ဖြစ်ပါသည်။ ပုံမှန် raster dataset များတွင် ကောင်းကင်ဓာတ်ပုံ (aerial photography) သို့မဟုတ် ဂြိုလ်တုဓာတ်ပုံ (satellite imagery) ကဲ့သို့သော အဝေးမှစူးစမ်းလေ့လာသည့်ဒေတာ (remote sensing data) နှင့် အမြင့် (elevation) သို့မဟုတ် အပူချိန် (temperature) ကဲ့သို့သော model ပြုလုပ်ထားသည့် data (modelled data) များပါဝင်ပါသည်။ 

Vector data နှင့်မတူသည်မှာ raster data တွင် ပုံမှန်အားဖြင့် ဆဲလ် (cell) တစ်ခုချင်းစီအတွက် ဆက်စပ်နေသည့် (associated) database record တစ်ခုမရှိပါ။ ၎င်းတို့ကို pixel resolution (pixel ကြည်လင်ပြတ်သားမှု) နှင့် raster layer ၏ ထောင့်ရှိ pixel (corner pixel) ၏ X/Y coordinate ဖြင့် geocode ပြုလုပ်ပါသည်။ (Geocode ပြုလုပ်သည်ဆိုသည်မှာ တည်နေရာတစ်ခုနှင့်ဆက်စပ်နေသည့် ပထဝီဝင်ဆိုင်ရာ ကိုဩဒိနိတ်များကို ပံ့ပိုးပေးခြင်းဖြစ်ပါသည်) ၎င်းသည် QGIS ကို map canvas အပေါ်တွင် data ကို မှန်ကန်စွာနေရာချနိုင်ရန် ခွင့်ပြုပေးပါသည်။ 

GeoPackage format (.gpkg extension ပါဝင်သည့် SQLite Database file တစ်ခု) သည် QGIS နှင့်လုပ်ငန်းဆောင်တာများဆောင်ရွက်သည့်အခါတွင် raster data များကို သိမ်းဆည်းရန်အတွက် အဆင်ပြေစေပါသည်။ လူသိများပြီး အစွမ်းထက် (powerful) သော GeoTiff format သည် ကောင်းမွန်သည့် နည်းလမ်း (alternative) တစ်ခုဖြစ်ပါသည်။

QGIS သည် data ကို မှန်ကန်စွာဖော်ပြရန် raster layer ထဲရှိ georeference information (ဥပမာ- :index:`GeoTiff`) သို့မဟုတ် သက်ဆိုင်ရာ *world file* တစ်ခုကို အသုံးပြုပါသည်။ 

.. if there are particularities for some raster formats that are worth mention,
   put them here. Maybe some comments on working with vrt, landsat data...?


Vector Data
============

QGIS တွင် ရရှိနိုင်သည့် features နှင့် tool များသည် vector data ရင်းမြစ် (source) မခွဲခြားပဲ တူညီစွာပင် အလုပ်လုပ်ပါသည်။ သို့ရာတွင် format specifications (သီးခြားကန့်သတ်သတ်မှတ်ချက်များ) များအကြား မတူညီမှုများကြောင့် (GeoPackage ၊ ESRI Shapefile ၊ MapInfo and MicroStation file formats ၊ AutoCAD DXF ၊ PostGIS ၊ SpatiaLite ၊ Oracle Spatial ၊ MS SQL Server SAP HANA Spatial databases နှင့် နောက်ထပ်အခြားသော) QGIS သည် ၎င်းတို့၏ ဂုဏ်သတ္တိများ (properties) ထဲမှ အချို့ကို ကွဲပြားစွာ ကိုင်တွယ်ပါသည်။ ထောက်ပံ့မှု (Support) ကို `GDAL vector drivers <https://gdal.org/drivers/vector/index.html>`_ မှ ပံ့ပိုးပေးပါသည်။ ဤ section သည် အဆိုပါ သတ်မှတ်ချက်များ (specifics) နှင့် မည်သို့ ဆောင်ရွက်ရမည်ကို ဖော်ပြပါသည်။

.. note::

   QGIS သည် (multi)point ၊  (multi)line ၊ (multi)polygon ၊ CircularString ၊ CompoundCurve ၊ CurvePolygon ၊ MultiCurve ၊ MultiSurface feature အမျိုးအစားများကို ပံ့ပိုးပေးပြီး ၎င်းတို့အားလုံးတွင် ရွေးချယ်နိုင်သည့် Z နှင့်/သို့မဟုတ် M တန်ဖိုးများပါရှိပါသည်။ 

   အချို့ drivers များသည် CircularString ၊ CompoundCurve ၊ CurvePolygon ၊ MultiCurve ၊ MultiSurface feature အမျိုးအစားများကို မပံ့ပိုးသည်ကို သတိပြုရမည်ဖြစ်ပါသည်။ QGIS သည် ၎င်းတို့ကို ပြောင်းလဲပေးမည် (convert) ဖြစ်ပါသည်။ 

.. index:: GeoPackage
.. _vector_geopackage:

GeoPackage
-----------

`GeoPackage <https://www.geopackage.org/>`_ (GPKG) format သည် platform-independent (ပလက်ဖောင်းကိုမီခိုသော) ဖြစ်ပြီး SQLite database container အဖြစ် အကောင်အထည်ဖော်ပါသည်။ ၎င်းကို vector နှင့် raster data များကို သိမ်းဆည်းရန်အသုံးပြုပါသည်။ Format ကို Open Geospatial Consortium (OGC) မှ သတ်မှတ်ခဲ့ပြီး ၂၀၁၄ ခုနှစ်တွင် ထုတ်ပြန်ခဲ့ (publish) ပါသည်။ 

GeoPackage အား SQLite database တစ်ခုထဲတွင် အောက်ဖော်ပြပါတို့ကို သိမ်းဆည်းရန် အသုံးပြုနိုင်ပါသည်- 

* **Vector** features (vector features များတွင် point ၊ line သို့မဟုတ် polygon geometry အမျိုးအစားများပါဝင်ပါသည်)
* **tile matrix sets of imagery** (ပုံရိပ်များ၏ tile matrix sets များ) နှင့် **raster** map များ
* Attribute များ (non-spatial data)
* Extension များ

QGIS version 3.8 မှစ၍ GeoPackage သည် QGIS project များကိုလည်း သိမ်းဆည်းနိုင်ပါသည်။ GeoPackage layer များတွင် JSON fields များပါရှိပါသည်။ (JavaScript Object Notation (JSON) သည် ArcGIS နှင့် အခြားစနစ်များအကြား GIS ဒေတာကို မျှဝေရန်အတွက် text-based ၊ lightweight ၊ data interchange format တစ်ခုဖြစ်ပါသည်)

GeoPackage သည် QGIS ထဲရှိ vector data အတွက် default format ဖြစ်ပါသည်။ 

.. index:: ESRI Shapefile format, GDAL
.. _vector_shapefiles:

ESRI Shapefile format (ESRI Shapefile format သည် data set တစ်ခုထဲရှိ spatial features များအတွက် nontopological geometry  နှင့် attribute information များကို သိမ်းဆည်းရန် special-purpose dataset တစ်ခုဖြစ်ပါသည်)
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

ESRI Shapefile format သည် GeoPackage နှင့် SpatiaLite စသည်တို့နှင့် နှိုင်းယှဉ်ပါက ကန့်သတ်ချက်အချို့ရှိသော်လည်း  အများဆုံးအသုံးပြုနေသည့် vector file format များထဲမှတစ်ခုဖြစ်နေပါသေးသည်။

ESRI Shapefile format dataset  တစ်ခုတွင် ဖိုင်များစွာပါဝင်ပါသည်။ 
အောက်ဖော်ပြပါ (၃) ခုကိုလိုအပ်မည်ဖြစ်ပါသည်။-

#. Feature geometries များပါဝင်သည့် :file:`.shp` ဖိုင်
#. dBase format တွင် attributes များပါဝင်သည့် :file:`.dbf` ဖိုင်
#. :file:`.shx` index file (indexed file သည် ၎င်း၏ file key ပေးထားသည့် မည်သည့်မှတ်တမ်းကိုမဆို အလွယ်တကူ ကျပန်းဝင်ရောက်ခွင့်ပြုသည့် index တစ်ခုပါရှိသော ကွန်ပျူတာဖိုင်တစ်ခုဖြစ်သည်)

ESRI Shapefile format dataset တစ်ခုတွင် :file:`.prj` နောက်ဆက်တွဲပါရှိသည့် ဖိုင်တစ်ခုလည်းပါဝင်ပါသည်။ ၎င်းတွင် projection ဆိုင်ရာအချက်အလက်များပါဝင်ပါသည်။ Projection file တစ်ခုရှိခြင်းသည် အလွန်အသုံးဝင်သော်လည်း မဖြစ်မနေရှိရန်မလိုအပ်ပါ။ 
Shapefile format dataset တစ်ခုတွင် ထပ်ဆောင်းအပိုဖိုင်များ ပါဝင်ပါသည်။ နောက်ထပ်အသေးစိတ်အချက်အလက်များအတွက် ESRI `technical specification <https://www.esri.com/content/dam/esrisites/sitecore-archive/Files/Pdfs/library/whitepapers/pdfs/shapefile.pdf>`_ တွင် ကြည့်ရှုပါ။ 

GDAL သည် compressed ပြုလုပ်ထားသည့် ESRI Shapefile format (:file:`shz` နှင့် :file:`shp.zip`) အတွက် ဖတ်ရှုခြင်း-ရေးသားခြင်းပံ့ပိုးမှု (read-write support) ပါရှိပါသည်။ 

**ESRI Shapefile format dataset များအတွက် စွမ်းဆောင်ရည် (Performance) ကောင်းမွန်စေခြင်း**

ESRI Shapefile format တစ်ခုအတွက် ပုံရေးဆွဲခြင်းဆိုင်ရာစွမ်းဆောင်ရည် (drawing performance) ကို တိုးတက်ကောင်းမွန်စေရန် Spatial index တစ်ခုကို ဖန်တီးနိုင်ပါသည်။
Spatial index တစ်ခုသည် (spatial index ဆိုသည်မှာ GIS ထဲရှိ multidimensional space တစ်ခုတွင်ရှိနေသည့် point များ ၊ line များနှင့် polygon များကဲ့သို့သော spatial data ၏ querying နှင့် retrieval ကို အကျိုးရှိစေသည့် data structure တစ်ခုဖြစ်ပါသည်) zooming  နှင့် panning ပြုလုပ်ခြင်း၏ အလျင် (speed)ကို တိုးတက်ကောင်းမွန်စေမည်ဖြစ်ပါသည်။
QGIS မှ အသုံးပြုသည့် Spatial index များတွင် :file:`.qix` extension တစ်ခုပါရှိပါသည်။ 
  
အညွှန်း (index) ကိုဖန်တီးရန် အောက်ပါအဆင့်များကို အသုံးပြုပါ-

#. ESRI Shapefile format dataset (:ref:`browser_panel` တွင် ကြည့်ပါ) တစ်ခုကို ထည့်သွင်းပါ။
#. မြေပုံရည်ညွှန်းချက် (legend) ထဲရှိ layer အမည်အပေါ်ကို double-clicking သို့မဟုတ် right-clicking ပြုလုပ်ပြီး context menu မှ :menuselection:`Properties...` ကို ရွေးချယ်ပြီး :guilabel:`Layer Properties` dialog ကိုဖွင့်ပါ။ 
#. :guilabel:`Source` tab ထဲတွင် :guilabel:`Create Spatial Index` button ကို click နှိပ်ပါ။

**.prj file တစ်ခုကို loading ပြုလုပ်ရာတွင် ကြုံတွေ့ရသည့်ပြဿနာ**

အကယ်၍ ESRI Shapefile format dataset တစ်ခုကို :file:`.prj` file ဖြင့် ထည့်သွင်းပါက QGIS သည် အဆိုပါဖိုင်မှ coordinate reference system (ကိုဩဒိနိတ်ရည်ညွှန်းစနစ်) ကို မဖတ်ရှုနိုင်သည့်အခါတွင် |setProjection| :sup:`Select CRS` button ကို click နှိပ်ခြင်းဖြင့် layer ၏ :menuselection:`Layer Properties --> Source` tab ထဲတွင် သင့်လျော်ရာ projection ကို ကိုယ်တိုင်(manually) သတ်မှတ်ရန် လိုအပ်ပါသည်။ ထိုသို့ဖြစ်ရခြင်းမှာ :file:`.prj` file များသည် :guilabel:`CRS` dialog တွင် စာရင်းပြုစုဖော်ပြထားသည့်အတိုင်းနှင့် QGIS တွင် အသုံးပြုထားသည့်အတိုင်း projection ဆိုင်ရာသတ်မှတ်ချက် (projection parameters) အပြည့်အစုံကို ပံ့ပိုးခြင်း မရှိသည့်အတွက်ကြောင့် ဖြစ်ပါသည်။ 

ထို့နည်းတူစွာပင် အကယ်၍ ESRI Shapefile format dataset အသစ်တစ်ခုကို QGIS ဖြင့်ဖန်တီးပါက တူညီမှုမရှိသော ဖိုင်(၂)ခုဖြစ်သည့် ESRI software နှင့်ကိုက်ညီပြီး ကန့်သတ်ထား (limit) သည့် projection parameter များ ပါရှိသည့် :file:`.prj` တစ်ခုနှင့် CRS ၏ သတ်မှတ်ချက် (parameters) အားလုံးကို ပံ့ပိုးပေးထားသည့် :file:`.qpj` file တစ်ခုကို ဖန်တီးမည်ဖြစ်ပါသည်။ 

QGIS သည် :file:`.qpj` file ကို ရှာဖွေတွေ့ရှိသည့်အခါတွင် ၎င်းကို :file:`.prj` အစား အသုံးပြုမည်ဖြစ်ပါသည်။ 


.. index:: CSV, Delimited text files
   see: Comma Separated Values; CSV
.. _vector_csv:

Delimited Text Files (Delimited Text ဖိုင်များ)
------------------------------------------------

Delimited text files များသည် ၎င်းတို့၏ ရိုးရှင်းမှု (simplicity) နှင့် ဖတ်ရှုရလွယ်ကူမှု (readability) တို့ကြောင့် ပုံမှန်တွေ့ရလေ့ရှိပြီး ကျယ်ပြန့်စွာအသုံးပြုခြင်း ခံရပါသည်။ Data ကို ရိုးရှင်းသည့် text editor (စာသားများပြင်ဆင်သည့်ဆော့ဖ်ဝဲလ်) ဖြင့်ပင် ပြင်ဆင်နိုင်ပြီး ကြည့်ရှုနိုင်ပါသည်။ Delimited text file သည် သတ်မှတ်ထား (defined)သည့် character တစ်ခုဖြင့် ပိုင်းခြားထားသည့် column များနှင့် line break (စာကြောင်းတစ်ကြောင်းအဆုံးသတ်ပြီး စာကြောင်းအသစ်စတင်သည့်နေရာ) များဖြင့် ပိုင်းခြားထားသည့် row များပါရှိသော tabular data (columns သို့မဟုတ် tables(ဇယားများ) ပါရှိသည့် ဒေတာ)ဖြစ်ပါသည်။ ပထမဆုံး row တွင် များသောအားဖြင့် column ၏ အမည်များပါဝင်ပါသည်။ တွေ့ရလေ့ရှိသည့် delimited text file အမျိုးအစားတစ်ခုမှာ column များကို ကော်မာ (,) များဖြင့် ပိုင်းခြားထားသော CSV (Comma Separated Values) တစ်ခုဖြစ်ပါသည်။ Delimited text file များတွင် positional information (တည်နေရာနှင့်ဆိုင်သောအချက်အလက်) လည်း ပါဝင်နိုင်ပါသည်။ (:ref:`csv_geometry` တွင် ကြည့်ရှပါ)

QGIS သည် delimited text file တစ်ခုကို layer တစ်ခုအဖြစ် သို့မဟုတ် ပုံမှန်ဇယား (ordinary table) တစ်ခုအဖြစ်သို့ ထည့်သွင်းခြင်းကို ခွင့်ပြုပါသည်။ (:ref:`browser_panel` သို့မဟုတ် :ref:`vector_loading_csv` တွင် ကြည့်ပါ) ပထမဦးစွာ ဖိုင်များသည် အောက်ဖော်ပြပါ လိုအပ်ချက်များ (requirements) နှင့် ကိုက်ညီမှုရှိကြောင်း စစ်ဆေးရမည်ဖြစ်ပါသည်-

#. ဖိုင်တွင် field အမည်များ၏ delimited header row တစ်ခုရှိရမည်ဖြစ်ပါသည်။ ၎င်းသည် data ၏ ပထမဆုံးစာကြောင်းဖြစ်ရမည်ဖြစ်ပါသည်။ (ယေဘုယျအားဖြင့် စာသားဖိုင်ထဲရှိ ပထမဆုံး row)
#. အကယ်၍ geometry ကို ဖွင့်ထားပါက ဖိုင်တွင် geometry ကို သတ်မှတ်ထားသည့် field(s) များပါဝင်ရမည်ဖြစ်ပါသည်။ ဤ field(s) များတွင် မည်သည့်အမည်မဆို ပေးနိုင်ပါသည်။ 
#. X နှင့် Y ကိုဩဒိနိတ် field များ (X and Y coordinates fields) (အကယ်၍ geometry ကို coordinates များဖြင့် သတ်မှတ်ထားပါက) 
   ကို ကိန်းဂဏန်းနံပါတ်များ (numbers) အဖြစ်သို့ သတ်မှတ်ရမည်ဖြစ်ပါသည်။ ကိုဩဒိနိတ်စနစ်သည် အရေးမကြီးပါ။
#. Non-string column များပါရှိသည့် CSV file တစ်ခုရှိပါက ၎င်းနှင့်အတူ CSVT file တစ်ခုရှိနိုင်ပါသည်။ (:ref:`csvt_files` section တွင် ကြည့်ပါ)

QGIS sample (နမူနာ) dataset ထဲရှိ elevation point data file (အမြင့်အမှတ်ဒေတာဖိုင်) :file:`elevp.csv`(:ref:`label_sampledata` section တွင် ကြည့်ပါ) သည် valid text file (valid text file သည် ရိုးရှင်းသည့်အင်္ဂလိပ်စာသားပါဝင်သည့် မည်သည့်ဖိုင်မဆိုဖြစ်ပြီး Valid file extensions များသည် .txt သို့မဟုတ် .csv ဖြစ်ကြပါသည်) တစ်ခု၏ နမူနာတစ်ခုဖြစ်ပါသည်-


::

 X;Y;ELEV
 -300120;7689960;13
 -654360;7562040;52
 1640;7512840;3
 [...]

စာသားဖိုင် (text file) နှင့် စပ်လျဉ်း၍ မှတ်သားထားရမည့်အရာအချို့-

#. နမူနာ စာသားဖိုင် (text file) သည် ``;`` (semicolon) ကို delimiter (စာလုံးများ၊ တန်ဖိုးများကို ခွဲခြားပေးသည့် space သို့မဟုတ် comma (,) ကဲ့သို့သော character များ) အဖြစ်အသုံးပြုပါသည်။ (မည်သည့် character ကို မဆို field များကို delimit ပြုလုပ်ရန် အသုံးပြုနိုင်ပါသည်)
#. ပထမဆုံး row သည် header row (ခေါင်းစီးအတန်း) ဖြစ်ပါသည်။ ၎င်းတွင် ``X`` ၊ ``Y`` နှင့် ``ELEV`` field များပါဝင်ပါသည်။ 
#. No quotes (``"``) များကို text field များအား delimit ပြုလုပ်ရန် အသုံးပြုပါသည်။
#. ``X`` field ထဲတွင် X coordinates များ ပါဝင်ပါသည်။
#. ``Y`` field ထဲတွင် Y coordinates များ ပါဝင်ပါသည်။

.. _csv_geometry:

Storing geometry information in delimited text files (Delimited text file များအတွင်း geometry ဆိုင်ရာအချက်အလက်များ သိမ်းဆည်းခြင်း)
...................................................................................................................................

Delimited text file များတွင် geometry information (အချက်အလက်) များသည် အဓိကပုံစံ(၂) မျိုးဖြင့်ပါရှိနိုင်ပါသည်-
  
* Point geometry data အတွက် သီးခြားကော်လံတိုင်များ (separate columns) ထဲရှိ coordinates များအဖြစ် (ဥပမာ ``Xcol`` ၊ ``Ycol``... )
* မည်သည့် geometry အမျိုးအစားအတွက်မဆို single ကော်လံတိုင် (column) တစ်ခုထဲတွင် geometry ကို ကိုယ်စားပြုပြန်လည်ဖော်ပြသော well-known text (WKT) အဖြစ်၊

အကွေးများပါရှိသည့် geometry များ (CircularString ၊ CurvePolygon နှင့် CompoundCurve) ပါရှိသည့် Feature များကို ပံ့ပိုးပေးပါသည်။
ဖော်ပြပါတို့သည် geometry များကို WKT အဖြစ် code ပြုလုပ်ထားသည့် delimited text file တစ်ခုထဲရှိ geometry အမျိုးအစားများ၏ နမူနာအချို့ဖြစ်ပါသည်-

::

  Label;WKT_geom
  LineString;LINESTRING(10.0 20.0, 11.0 21.0, 13.0 25.5)
  CircularString;CIRCULARSTRING(268 415,227 505,227 406)
  CurvePolygon;CURVEPOLYGON(CIRCULARSTRING(1 3, 3 5, 4 7, 7 3, 1 3))
  CompoundCurve;COMPOUNDCURVE((5 3, 5 13), CIRCULARSTRING(5 13, 7 15,
    9 13), (9 13, 9 3), CIRCULARSTRING(9 3, 7 1, 5 3))

Delimited text file များသည် geometry များထဲရှိ Z နှင့် M coordinates များကိုလည်း ပံ့ပိုးပေးပါသည်။

::

  LINESTRINGZ(10.0 20.0 30.0, 11.0 21.0 31.0, 11.0 22.0 30.0)


.. index:: CSV, CSVT
.. _csvt_files:

Using CSVT file to control field formatting (Field အား format ချထားခြင်းကို ထိန်းချုပ်ရန် CSVT file ကို အသုံးပြုခြင်း)
.......................................................................................................................

CSV files များကို ထည့်သွင်းရာတွင် အခြားတစ်ခုအဖြစ်မဖော်ပြပါက GDAL driver သည် fields အားလုံးကို string (ဥပမာ- စာသား) များဟု ယူဆပါသည်။ မတူညီသော column များ၏ data အမျိုးအစားကို GDAL (နှင့် QGIS) အား ဖော်ပြရန် CSVT file တစ်ခုကို ဖန်တီးနိုင်ပါသည်- 

.. csv-table::
    :header: "Type"(အမျိုးအစား), "Name"(အမည်), "Example"(နမူနာ)

    "Whole number", "Integer", 4
    "Boolean", "Integer(Boolean)", true
    "Decimal number", "Real", 3.456
    "Date", "Date (YYYY-MM-DD)", 2016-07-28
    "Time", "Time (HH:MM:SS+nn)", 18:33:12+00
    "Date & Time", "DateTime (YYYY-MM-DD HH:MM:SS+nn)", 2016-07-28 18:33:12+00
    "CoordX", "CoordX", 8.8249
    "CoordY", "CoordY", 47.2274
    "Point(X)", "Point(X)", 8.8249
    "Point(Y)", "Point(Y)", 47.2274
    "WKT", "WKT", POINT(15 20)

CSVT file သည် comma များဖြင့် ပိုင်းခြားထားပြီး quotes ဖြင့်ရှိသည့် data အမျိုးအစားများပါဝင်သည့် **ONE line** plain text file တစ်ခုဖြစ်ပါသည်။ ဥပမာ- 

::

 "Integer","Real","String"

Column တစ်ခုချင်းစီ၏ width (အကျယ်) နှင့် precision (တိကျမှု) ကိုပင် သတ်မှတ်နိုင်ပါသည်။ ဥပမာ-

::

 "Integer(6)","Real(5.5)","String(22)"

ဤဖိုင်ကို တူညီသည့် folder ထဲတွင် တူညီသည့်အမည်ဖြင့် :file:`.csv` file အဖြစ်သို့ သိမ်းဆည်းနိုင်ပါသည်။ 
သို့ရာတွင် :file:`.csvt` ကို extension အဖြစ် သိမ်းဆည်းရမည်ဖြစ်ပါသည်။

*နောက်ထပ် အချက်အလက်များကို `GDAL CSV Driver <https://gdal.org/drivers/vector/csv.html>`_ တွင် ရှာဖွေတွေ့ရှိနိုင်ပါသည်။*

.. _tip_detect_field_types:

.. tip:: **Field အမျိုးအစားများကို ရှာဖွေဖော်ထုတ်နိုင်ပါသည်**

   Data အမျိုးအစားများအား ဖော်ပြရန် CSVT file တစ်ခုကို အသုံးပြုခြင်းအစား QGIS သည် field အမျိုးအစားများကို အလိုအလျောက် ရှာဖွေဖော်ထုတ်ရန် နှင့် ယူဆလိုက်သည့် field အမျိုးအစားများသို့ ပြောင်းလဲရန် ဖြစ်နိုင်ခြေများ (possibility) ကို ပံ့ပိုးပေးပါသည်။ 


.. index:: PostGIS, PostgreSQL
.. _label_postgis:

PostGIS Layers (PostGIS Layer များ)
------------------------------------

PostGIS layer များကို PostgreSQL database တစ်ခုထဲတွင် သိမ်းဆည်းပါသည်။ PostGIS ၏ ကောင်းကျိုးများမှာ spatial indexing (indexing ပြုလုပ်ခြင်းသည် သီးခြားမှတ်တမ်းတစ်ခုကို ရှာဖွေရန် လျင်မြန်စွာ traverse ပြုနိုင်သည့် search tree ထဲသို့ ဒေတာများကို စုစည်းခြင်းဖြင့် ရှာဖွေမှုကို အရှိန်မြှင့်စေသည်)၊ filtering (စစ်ထုတ်ခြင်း) နှင့် querying capabilities (စွမ်းဆောင်ရည်များကို query ပြုလုပ်ခြင်း) တို့ဖြစ်ပါသည်။ PostGIS ကို အသုံးပြုပြီး select ပြုလုပ်ခြင်းနှင့် သတ်မှတ်ခြင်း(identify) ကဲ့သို့သော vector function များကို လုပ်ဆောင်ရာတွင် အဆိုပါဆောင်ရွက်မှုများကို QGIS တွင် GDAL layer များနှင့်လုပ်ဆောင်သည်ထက် ပိုမိုတိကျစွာဆောင်ရွက်နိုင်ပါသည်။ 


.. _tip_postgis_layers:

.. tip:: **PostGIS Layers**

   ပုံမှန်အားဖြင့် PostGIS layer တစ်ခုကို geometry_columns table ထဲရှိ entry တစ်ခုဖြင့် သတ်မှတ်ပါသည်။ QGIS သည် geometry_columns table ထဲရှိ entry တစ်ခုမပါသည့် layer များကို ထည့်သွင်းနိုင်ပါသည်။ ၎င်းတွင် table များနှင့် view များ ပါဝင်ပါသည်။ View များအား ဖန်တီးခြင်းနှင့်စပ်လျဉ်းသည့် အချက်အလက်များအတွက် PostgreSQL လမ်းညွှန် (manual) ကို ကိုးကားပါ။ 

ဤ section တွင် QGIS သည် PostgreSQL layers များကို မည်သို့ accesses ပြုလုပ်သည်နှင့်စပ်လျဉ်း၍ အချက်အလက်အချို့ပါဝင်ပါသည်။ အချိန်အများစုတွင် QGIS သည် ထည့်သွင်းနိုင်သည့် database tables(ဇယား) စာရင်းတစ်ခုဖြင့် ရိုးရှင်းစွာ ပံ့ပိုးသင့်ပြီး တောင်းဆိုမှု (request) ပြုလုပ်သည့်အခါတွင် ၎င်းတို့ကို ထည့်သွင်းသွားမည်ဖြစ်ပါသည်။ သို့ရာတွင် PostgreSQL table တစ်ခုကို QGIS ထဲသို့ ထည့်သွင်းရာတွင် အခက်အခဲများရှိနေပါက အောက်ဖော်ပြပါ အချက်အလက်များသည် QGIS ၏အသိပေးချက်များကို နားလည်သဘောပေါက်စေရန် နှင့် ၎င်းကို QGIS အတွင်းထည့်သွင်းနိုင်စေရန် PostgreSQL table သို့မဟုတ် view definition ကို ပြင်ဆင်ခြင်း (modifying) အတွက် လမ်းညွှန်ချက်များကို ပေးသွားမည်ဖြစ်ပါသည်။   

.. note::

   PostgreSQL database တစ်ခုသည် QGIS project များကိုလည်း သိမ်းဆည်းနိုင်ပါသည်။

Primary key (အဓိက Key)
.......................

QGIS အနေဖြင့် layer အတွက် သိသာထင်ရှားသည့် key (unique key) တစ်ခုအဖြစ် အသုံးပြုနိုင်သည့် column တစ်ခုပါဝင်သော PostgreSQL layer များကို လိုအပ်ပါသည်။ Table သည် primary key တစ်ခု သို့မဟုတ် ၎င်းအပေါ်တွင် သိသာသည့် ကန့်သတ်ချက် (constraint) ပါရှိသည့် column တစ်ခုကို လိုအပ်သည်ဟု ဆိုလိုပါသည်။ QGIS တွင် ဤ column သည် int4 အမျိုးအစား (အရွယ်အစား 4 bytes ရှိသည့် integer တစ်ခု) ဖြစ်ရန်လိုအပ်ပါသည်။ တစ်နည်းအားဖြင့် ctid column ကို primary key အဖြစ်အသုံးပြုနိုင်ပါသည်။ အကယ်၍ table သည် ဤ item များမပါရှိပါက ၎င်းအစား oid column ကို အသုံးပြုမည်ဖြစ်ပါသည်။ Column ကို index (ညွှန်းဆိုဖော်ပြခြင်း) ပြုလုပ်ထားပါက စွမ်းဆောင်ရည် (Performance) ကို ကောင်းမွန်အောင် ဆောင်ရွက်နိုင်မည်ဖြစ်ပါသည်။
(Primary key များသည် PostgreSQL တွင် အလိုအလျောက် index (ညွှန်းဆိုဖော်ပြခြင်း) ပြုလုပ်သည်ကို သတိပြုရမည်ဖြစ်ပါသည်)

QGIS သည် **Select at id** checkbox တစ်ခုကို ပံ့ပိုးပြီး ၎င်းကို ပုံမှန် (default) အနေဖြင့် activate ပြုလုပ်ထားပါသည်။
ဤ နည်းလမ်းသည် id များကို attribute များမပါရှိဘဲ ရရှိစေပြီး ထိုသို့မပါရှိခြင်းသည် ကိစ္စရပ်အများစုတွင် ပိုမိုမြန်ဆန်မှုဖြစ်စေပါသည်။ 


View (မြင်ကွင်း)
.................

အကယ်၍ PostgreSQL layer သည် view တစ်ခုဖြစ်ပါက တူညီသော လိုအပ်ချက် (requirement) ရှိမည်ဖြစ်ပါသည်။ သို့သော် view များတွင် primary key များ သို့မဟုတ် ၎င်းတို့အပေါ်တွင် သိသာသည့် constraints (ကန့်သတ်ချက်များ) များဖြင့် column များ အမြဲတမ်း မပါရှိပါ။ View ကို မထည့်သွင်းမီတွင် QGIS dialog ထဲ၌ primary key field (integer တစ်ခုဖြစ်ရပါမည်) တစ်ခုကို သတ်မှတ်ရန်လိုအပ်မည်ဖြစ်ပါသည်။ အကယ်၍ view ထဲတွင် သင့်လျော်သည့် column တစ်ခုရှိမနေပါက QGIS သည် layer ကို ထည့်သွင်းမည်မဟုတ်ပါ။ ဤသို့ဖြစ်ပွားပါက ဖြေရှင်းနိုင်သည့်နည်းလမ်းမှာ သင့်လျော်သည့် column တစ်ခုပါရှိစေရန် (integer အမျိုးအစားတစ်ခုဖြစ်ပြီး primary key သို့မဟုတ် unique constraint တစ်ခု၊ ဖြစ်နိုင်ပါက index ပြုလုပ်ထားခြင်းကိုလိုလားပါသည်) view ကို ပြောင်းလဲခြင်းဖြစ်ပါသည်။ 

Table အတွက် **Select at id** checkbox တစ်ခုကို ပံ့ပိုးပြီး ၎င်းကို ပုံမှန် (default) အနေဖြင့် activate ပြုလုပ်ထားပါသည်။ (checkbox ၏ အဓိပ္ပါယ်ကို အပေါ်တွင် ကြည့်ရှုပါ။) Expensive view များကို အသုံးပြုသောအခါတွင် ဤ နည်းလမ်းကို ပိတ်ထားခြင်း(disable) သည် ပို၍ အဓိပ္ပါယ်ရှိပါသည်။ 

.. note:: **PostgreSQL foreign table**

   PostgreSQL foreign table (PostgreSQL foreign table တစ်ခုသည် PostgreSQL ဆာဗာတွင် ပေါ်တွင် storage မရှိပါ) များကို PostgreSQL provider မှ အထူးတလည်ပံ့ပိုးထားခြင်းမရှိဘဲ view တစ်ခုကဲ့သို့ ကိုင်တွယ်ဆောင်ရွက်သွားမည်ဖြစ်ပါသည်။ 

.. _layer_style_backup:

QGIS layer_style table and database backup (QGIS layer_style ဇယားနှင့် database အရန်သိမ်းဆည်းခြင်း)
....................................................................................................

အကယ်၍ :file:`pg_dump` နှင့် :file:`pg_restore` command (အမိန့်ပေးစေခိုင်းချက်) များကို အသုံးပြု၍ PostGIS database ၏ backup တစ်ခုကို ပြုလုပ်လိုပြီး နောက်ပိုင်းတွင် QGIS မှ သိမ်းဆည်းထားသည့် default layer style များသည် restore  (ပြန်လည်ရယူခြင်း) မပြုလုပ်နိုင်သည့်အခါတွင် restore command မတိုင်ခင် XML option ကို :file:`DOCUMENT` သို့ သတ်မှတ်ရမည်ဖြစ်ပါသည်။

#. ``layer_style`` table ၏ PLAIN backup တစ်ခုကို ပြုလုပ်ပါ။ 
#. Text editor တစ်ခုအတွင်းတွင် ဖိုင်ကိုဖွင့်ပါ။ 
#. ``SET xmloption = content;`` စာကြောင်းကို ``SET XML OPTION DOCUMENT;`` အဖြစ်သို့ ပြောင်းလဲပါ။ 
#. File ကို သိမ်းဆည်းပါ။
#. Database အသစ်ထဲတွင် table ကို restore (ပြန်လည်ရယူခြင်း) ဆောင်ရွက်ရန် psql ကို အသုံးပြုပါ။


Filter database side (Database ဘက်ခြမ်းမှ filter လုပ်ခြင်း)
............................................................

QGIS သည် server side (server-side သည် ဆာဗာပေါ်တွင် လုပ်ဆောင်သည့် ပရိုဂရမ်များနှင့် လုပ်ဆောင်ချက်များကို ရည်ညွှန်းသည်) တွင် ရှိနေပြီးသားဖြစ်သည့် features များကို စစ်ထုတ်ရန် (filter) ခွင့်ပြုပါသည်။ ထိုသို့ဆောင်ရွက်ရန် :menuselection:`Settings --> Options --> Data Sources -->` |checkbox| :menuselection:`Execute expressions on server-side if possible` ကို အမှန်ခြစ်ပါ။ ပံ့ပိုးပေးထားသည့် expression (Expression များသည် geometry style ၊ label ၏ တည်နေရာ သို့မဟုတ် ပါဝင်သည့်အကြောင်းအရာ ၊ diagram အတွက် တန်ဖိုး ၊ layout item တစ်ခု၏ အမြင့် ၊ features အချို့ကို select ပြုလုပ်ခြင်း ၊ virtual field များကို ဖန်တီးခြင်း ၊ စသည်တို့ကိုဆောင်ရွက်ရန်အတွက် attribute value ၊ geometry နှင့် variablesကို ကိုင်တွယ်ဆောင်ရွက်ရန် အားကောင်းသည့် နည်းလမ်းတစ်ခုဖြစ်ပါသည်) များကိုသာ database ထဲသို့ ပေးပို့သွားမည်ဖြစ်ပါသည်။ ပံ့ပိုးထားခြင်းမရှိသည့် operator များ သို့မဟုတ် function (လုပ်ဆောင်ချက်များ) ကို အသုံးပြုထားသည့် Expression များသည် local evaluation သို့ ပြန်လည်ရောက်ရှိမည်ဖြစ်ပါသည်။


Support of PostgreSQL data types (PostgreSQL data အမျိုးအစားများ၏ ပံ့ပိုးမှု)
..............................................................................

PostgreSQL provider မှ ပံ့ပိုးထားသည့် data အမျိုးအစားတွင်- integer (သုည အပါအဝင် အပေါင်း သို့မဟုတ် အနုတ်ပါဝင်သည့် အပြည့်ကိန်းများ) ၊ float (ဒဿမကိန်းများပါရှိသည့် အပေါင်း သို့မဟုတ် အနုတ်ကိန်းများ) ၊ boolean (true (1) သို့မဟုတ် false (0) ပါဝင်သည့် ဒေတာအမျိုးအစား) ၊ binary object (binary data ကို single entity အဖြစ် သိမ်းဆည်းထားသည့် အရာဝတ္ထုများ) ၊ varchar (variable-length character data အမျိုးအစား) ၊ geometry (two-dimensional flat surface တစ်ခုအပေါ်တွင် ပုံဖော်ထားသည့် spatial data အမျိုးအစား) ၊ timestamp (ကွန်ပျူတာဖြင့် မှတ်တမ်းတင်ထားသော အဖြစ်အပျက်တစ်ခု၏ လက်ရှိအချိန်ဖြစ်သည်) ၊ array (element အစုအဖွဲ့တစ်ခုကို ကိုယ်စားပြုသည့် object) ၊ hstore (ဆဲလ်တစ်ခုတည်းတွင် key-value အတွဲများကို သိမ်းဆည်းနိုင်စေမည့် data အမျိုးအစား) နှင့် json (JavaScript object syntax ကို အခြေခံ၍ တည်ဆောက်ထားသော data ကို ကိုယ်စားပြုရန်အတွက် စံ text-based format တစ်ခု) တို့ပါဝင်ပါသည်။

.. index:: shp2pgsql
   single: PostGIS; shp2pgsql
.. _vector_import_data_in_postgis:

Importing Data into PostgreSQL (PostgreSQL ထဲသို့ Data ကို ပြုလုပ်ခြင်း)
-------------------------------------------------------------------------

DB Manager plugin အပါအဝင် များစွာသော tool များနှင့် shp2pgsql နှင့် ogr2ogr command line tool များ အသုံးပြုပြီး PostgreSQL/PostGIS ထဲသို့ Data ကို import ပြုလုပ်နိုင်ပါသည်။

DB Manager (Database များစီမံခန့်ခွဲသည့်နေရာ)
..............................................

QGIS သည် |dbManager| :sup:`DB Manager` ဟု အမည်တွင်သည့် အဓိက (core) plugin ဖြင့် လာပါသည်။ ၎င်းကို data အား ထည့်သွင်းရန်အသုံးပြုနိုင်ပြီး schemas (plan သို့မဟုတ် theory တစ်ခုကို utline သို့မဟုတ် model ပုံစံဖြင့် ကိုယ်စားပြုဖော်ပြချက်တစ်ခု) များအတွက် ပံ့ပိုးမှုများပါဝင်ပါသည်။ နောက်ထပ်အချက်အလက်များအတွက် :ref:`dbmanager` section တွင် ကြည့်ရှုပါ။ 

shp2pgsql
..........

PostGIS တွင် **shp2pgsql** ဟု ခေါ်ဆိုသည့် utility တစ်ခုပါဝင်ပြီး ၎င်းကို PostGIS-enabled database (PostGIS ဆောင်ရွက်နိုင်သည့် database) တစ်ခုထဲသို့ Shapefile format datasets များကို import ပြုလုပ်ရန် အသုံးပြုနိုင်ပါသည်။
ဥပမာ- :file:`lakes.shp` ဟု အမည်တွင်သည့် Shapefile format တစ်ခုကို ``gis_data`` ဟု အမည်တွင်သည့် PostgreSQL database တစ်ခုထဲသို့ import ပြုလုပ်ရန် အောက်ဖော်ပြပါ command (အမိန့်ပေးစေခိုင်းချက်) ကို အသုံးပြုပါ-

:: 

  shp2pgsql -s 2964 lakes.shp lakes_new | psql gis_data

၎င်းသည် ``gis_data`` database ထဲတွင် ``lakes_new`` ဟုခေါ်ဆိုသည့် layer အသစ်တစ်ခုကို ဖန်တီးပါသည်။ Layer အသစ်တွင် 2964 ဆိုသည့် spatial reference identifier (SRID) (spatial reference identifier (SRID) သည် တိကျသော ကိုသြဒိနိတ်စနစ်၊ tolerance နှင့် resolution တို့နှင့် ဆက်စပ်နေသည့် unique identifier တစ်ခုဖြစ်ပါသည်) တစ်ခု ရှိမည်ဖြစ်ပါသည်။ Spatial reference system များ၊ projection များနှင့်သက်ဆိုင်သည့် နောက်ထပ်အချက်အလက်များအတွက် :ref:`label_projections` section တွင် ကြည့်ရှုပါ။ 

.. index:: pgsql2shp

.. _tip_export_from_postgis:

.. tip:: **PostGIS မှ dataset များကို export ထုတ်ခြင်း**

   PostGIS datasets ကို Shapefile format: **pgsql2shp** သို့ export ပြုလုပ်ရန် tool တစ်ခုရှိပါသည်။ ၎င်းကို သင့်၏ PostGIS distribution (PostGIS ဆိုင်ရာ ဖြန့်ဖြူးခြင်း) အတွင်းတွင် တင်ပို့ခြင်း (shipped) ပြုလုပ်ပါသည်။ 

.. index:: ogr2ogr
   single: PostGIS; ogr2ogr


ogr2ogr
........

**shp2pgsql** နှင့် **DB Manager** တို့အပြင် geographical data (ပထဝီဝင်ဆိုင်ရာအချက်အလက်များ) ကို PostGIS ထဲသို့ ထည့်သွင်းရန်အတွက် **ogr2ogr** ဆိုသည့် နောက်ထပ် tool တစ်ခုရှိပါသည်။ ၎င်းသည် GDAL ထည့်သွင်းတည်ဆောက်မှု (installation) ၏ တစ်စိတ်တစ်ပိုင်းဖြစ်ပါသည်။

Shapefile format dataset တစ်ခုကို PostGIS ထဲသို့ import ပြုလုပ်ရန် အောက်ပါတို့ကိုလုပ်ဆောင်ပါ- 

::

  ogr2ogr -f "PostgreSQL" PG:"dbname=postgis host=myhost.de user=postgres
  password=topsecret" alaska.shp

၎င်းသည် user (အသုံးပြုသူ) *postgres* နှင့် password *topsecret* ကို အသုံးပြု၍ host server (မူရင်းဆာဗာ) *myhost.de* အပေါ်ရှိ PostGIS database *postgis* ထဲသို့ Shapefile format dataset :file:`alaska.shp` ကို  import ပြုလုပ်ပါသည်။ 

PostGIS အားပံ့ပိုးရန်အတွက် GDAL ကို PostgreSQL နှင့်အတူထည့်သွင်းရန် သတိပြုရမည်ဖြစ်ပါသည်၊
(|nix|) တွင် အောက်ပါအတိုင်းရိုက်ထည့်ခြင်းဖြင့် ၎င်းကို verify (အသိအမှတ်ပြု) လုပ်နိုင်ပါသည်- 

::

  ogrinfo --formats | grep -i post


PostgreSQL ၏ **COPY** command ကို ပုံမှန်(default) **INSERT INTO**  နည်းလမ်းအစား ပို၍ အသုံးပြုလိုပါက အောက်ဖော်ပြပါ environment variable (ကွန်ပျူတာပေါ်တွင် လုပ်ဆောင်နေသည့် လုပ်ငန်းစဉ်များလုပ်ဆောင်ပုံအပေါ် သက်ရောက်မှုရှိနိုင်သည့် အသုံးပြုသူမှ သတ်မှတ်နိုင်သော တန်ဖိုးတစ်ခု) ကို export ပြုလုပ်နိုင်ပါသည်။ (|nix| နှင့် |osx| အပေါ်တွင်ရရှိနိုင်ပါသည်)

::

  export PG_USE_COPY=YES

**ogr2ogr** သည် **shp2pgsl** ကဲ့သို့ spatial index များကို ဖန်တီးမည်မဟုတ်ပါ။ နောက်ပိုင်းတွင် အပိုအဆင့်တစ်ခုအဖြစ် ပုံမှန် (normal) SQL command **CREATE INDEX** ကို အသုံးပြု၍ ၎င်းတို့ကို ကိုယ်တိုင် (manually) ဖန်တီးရန် လိုအပ်ပါသည်။ (နောက် :ref:`vector_improving_performance` section တွင် ဖော်ပြထားသကဲ့သို့)

.. index:: Spatial index; GiST index
   single: PostGIS; Spatial index
.. _vector_improving_performance:

Improving Performance (စွမ်းဆောင်ရည်များကို တိုးတက်ကောင်းမွန်အောင်ဆောင်ရွက်ခြင်း)
..................................................................................

PostgreSQL database မှ features များကို ပြန်လည်ရယူခြင်း (Retrieving) သည် အချိန်ကုန်စေပါသည်။ အထူးသဖြင့် network(ကွန်ယက်) တစ်ခုအပေါ်တွင်ဆိုပါက ပို၍အချိန်ကုန်ပါသည်။ PostgreSQL layers များ၏ ပုံရေးဆွဲခြင်းဆိုင်ရာစွမ်းဆောင်ရည်(drawing performance) ကို database ထဲရှိ layer တစ်ခုချင်းစီအပေါ်တွင် PostGIS spatial index တစ်ခု ရှိနေစေခြင်းဖြင့် တိုးတက်ကောင်းမွန်အောင်ဆောင်ရွက်နိုင်ပါသည်။ PostGIS သည် spatial searching ကို မြန်ဆန်စေရန် GiST (Generalized Search Tree) (GiST သည် disk-based search tree အမျိုးမျိုးကို တည်ဆောက်ရန် အသုံးပြုနိုင်သည့် ဒေတာဖွဲ့စည်းပုံနှင့် API တစ်ခုဖြစ်သည်။) တစ်ခုဖန်တီးခြင်းကို ပံ့ပိုးပေးပါသည်။ (GiST index information (GIS ညွှန်းကိန်းအချက်အလက်များ) ကို https://postgis.net တွင် ရရှိနိုင်သည့် PostGIS documentation (စာရွက်စာတမ်းများ) မှ ရယူထားပါသည်)

.. tip:: DBManager ကို layer အတွက် index (ညွှန်းကိန်း) တစ်ခုကိုဖန်တီးရန် အသုံးပြုပါသည်။ 
   Layer ကို ပထမဆုံး select ပြုလုပ်သင့်ပြီး :menuselection:`Table --> Edit table` အပေါ်တွင် click ပြုလုပ်ပါ။ :menuselection:`Indexes` tab ကိုသွားပြီး :guilabel:`Add Spatial Index` အပေါ်တွင် click ပြုလုပ်ပါ။

   GiST index တစ်ခုကို ဖန်တီးရန် syntax မှာ- 

::

   CREATE INDEX [indexname] ON [tablename]
     USING GIST ( [geometryfield] GIST_GEOMETRY_OPS );

ကြီးမားသည့် table များအတွက် index (အညွှန်း) တစ်ခုကို ဖန်တီးခြင်းသည် အချိန်ယူရမည်ဖြစ်သည်ကို သတိပြုရမည်ဖြစ်ပါသည်။ 
Index ကို ဖန်တီးလိုက်သည်နှင့်တစ်ပြိုင်နက် ``VACUUM ANALYZE`` တစ်ခုကို ဆောင်ရွက်သင့်ပါသည်။
နောက်ထပ်အချက်အလက်များအတွက် PostGIS documentation (:ref:`literature_and_web` ထဲရှိ POSTGIS-PROJECT) ကို ကြည့်ရှုပါ။ 

ဖော်ပြပါ နမူနာသည် GiST index တစ်ခုကိုဖန်တီးပါသည်- 

::

  gsherman@madison:~/current$ psql gis_data
  Welcome to psql 8.3.0, the PostgreSQL interactive terminal.

  Type:  \copyright for distribution terms
         \h for help with SQL commands
         \? for help with psql commands
         \g or terminate with semicolon to execute query
         \q to quit

  gis_data=# CREATE INDEX sidx_alaska_lakes ON alaska_lakes
  gis_data-# USING GIST (the_geom GIST_GEOMETRY_OPS);
  CREATE INDEX
  gis_data=# VACUUM ANALYZE alaska_lakes;
  VACUUM
  gis_data=# \q
  gsherman@madison:~/current$


.. index:: SpatiaLite, SQLite
.. _spatialite_data:

SpatiaLite Layers (SpatiaLite layer များ)
------------------------------------------

Vector layer တစ်ခုအား SpatiaLite format ကို အသုံးပြု၍ သိမ်းဆည်းလိုပါက :ref:`general_saveas` တွင် ပါရှိသည့် လမ်းညွှန်ချက်များ (instructions) ကို လိုက်နာခြင်းဖြင့် ဆောင်ရွက်နိုင်ပါသည်။ :guilabel:`Format` အဖြစ် ``SpatiaLite`` ကို select ပြုလုပ်ပြီး :guilabel:`File name` နှင့် :guilabel:`Layer name` နှစ်ခုစလုံးကို ထည့်သွင်းပါ။

``SQLite`` ကိုလည်း format အနေဖြင့် select ပြုလုပ်နိုင်ပြီး :menuselection:`Custom Options --> Data source` field ထဲတွင် ``SPATIALITE=YES`` ကို ထည့်သွင်းပါ။ ၎င်းသည် GDAL အား SpatiaLite database တစ်ခုကို ဖန်တီးရန် အသိပေးပါသည်။ https://gdal.org/drivers/vector/sqlite.html တွင်လည်း ကြည့်ရှုပါ။ 

QGIS သည် SpatiaLite ထဲတွင် ပြန်လည်ပြင်ဆင်နိုင်သည့်မြင်ကွင်းများ (editable views) ကို ပံ့ပိုးပေးပါသည်။ SpatiaLite data များကို စီမံခန့်ခွဲခြင်းအတွက် အဓိက (core) plugin :ref:`DB Manager <dbmanager>` ကိုလည်း အသုံးပြုနိုင်ပါသည်။

အကယ်၍ SpatiaLite layer အသစ်တစ်ခုကို ဖန်တီးလိုပါက :ref:`vector_create_spatialite` section ကို ရည်ညွှန်းကိုးကားပါ။ 


.. index:: GeoJSON Export
.. _export_geojson_files:


GeoJSON specific parameters (GeoJSON ဆိုင်ရာ သီးသန့်သတ်မှတ်ချက်များ)
---------------------------------------------------------------------

GeoJSON သို့ layer များကို export ပြုလုပ် (:ref:`exporting layers <general_saveas>`) သောအခါတွင် သီးသန့် :guilabel:`Layer Options (ရွေးချယ်မှုများ)` အချို့ကို ရရှိနိုင်ပါသည်။ အဆိုပါ option များသည် GDAL မှ လာပြီး ဖိုင်ကို ရေးသားရာတွင် အရေးပါပါသည်- 

* :guilabel:`COORDINATE_PRECISION` - ကိုဩဒိနိတ်များ (coordinates) ထဲတွင် ရေးသားရန် ဒဿမကိန်းခြားနားချက်(decimal separator) နောက်ရှိ အများဆုံးရှိနိုင်သည့် ဂဏန်းအရေအတွက်။ ပုံမှန်(Defaults) သည် ၁၅ ဖြစ်ပါသည်။ (မှတ်စု- Lat Lon coordinate များအတွက် ၆ သည် လုံလောက်သည်ဟု ယူဆပါသည်) နောက်ရှိ သုညများ (trailing zeros) ကို ဖယ်ရှားရန် တိုအောင်ဖြတ်တောက်ခြင်း (Truncation) လုပ်ဆောင်ပါလိမ့်သည်။ 
* :guilabel:`RFC7946` - ပုံမှန်(default) အားဖြင့် GeoJSON 2008 ကိုအသုံးပြုမည်ဖြစ်ပါသည်။ YES ကို သတ်မှတ်ထားပါက update ပြုလုပ်ထားသည့် RFC 7946 စံသတ်မှတ်ချက်ကို အသုံးပြုမည်ဖြစ်ပါသည်။ Default သည် NO ဖြစ်ပါသည်။ (ထို့ကြောင့် GeoJSON 2008) အဓိက ကွဲပြားခြားနားချက်များအတွက် https://gdal.org/drivers/vector/geojson.html#rfc-7946-write-support တွင်ကြည့်ပါ။ အတိုချုံးပြောရလျှင် EPSG:4326 ကိုသာ ခွင့်ပြုထားပါသည်။ အခြား crs များကို အသွင်ပြောင်းခြင်း (transform) ပြုလုပ်မည်ဖြစ်ပြီး ဦးတည်ရာ (orientation) အတွက် polygon များအား right-hand rule လိုက်နာရန် စသည်ဖြင့် ရေးသားမည်ဖြစ်ပါသည်။ "bbox" တစ်ခု၏ array တန်ဖိုးများမှာ [west(အနောက်) ၊ south(တောင်) ၊ east(အရှေ့) ၊ north(မြောက်)] ဖြစ်ပြီး [minx, miny, maxx, maxy] မဟုတ်ပါ။ အချို့သော extension member အမည်များကို FeatureCollection(Feature များစုစည်းထားရှိမှု)၊ Feature နှင့် Geometry objects များထဲတွင် တားမြစ်ထား (forbidden) ပြီး ပုံမှန်(default) ကိုဩဒိနိတ် တိကျမှု (coordinate precision) မှာ ဒဿမကိန်း ၇ လုံးဖြစ်ပါသည်။ 
* Feature နှင့် feature များစုဆောင်းသည့် အဆင့်တွင် geometries များ၏ bounding box ပါဝင်ရန် :guilabel:`WRITE_BBOX` ကို YES သို့ သတ်မှတ်ပါ။

GeoJSON အပြင် "GeoJSON - Newline Delimited" သို့ export ပြုလုပ်ရန် နည်းလမ်းတစ်ခုလည်း ရှိပါသေးသည်။
(https://gdal.org/drivers/vector/geojsonseq.html တွင် ကြည့်ရှုပါ)
Feature များပါဝင်သည့် FeatureCollection (Featureများစုစည်းထားရှိမှု) အစား newline များဖြင့် အစီအစဉ်တကျ ပိုင်းခြားထားသည့် အမျိုးအစားတစ်မျိုး (Features များသာ ဖြစ်နိုင်ပါသည်) ကို ကူးပြောင်းနိုင်ပါသည်။ 

GeoJSON - Newline Delimited (Newline Delimited ဆိုသည်မှာ transformationနှင့် processing အတွက် အထူးအဆင်ပြေသည့် စာသားအခြေခံ geospatial ဖိုင် format တစ်ခုဖြစ်ပါသည်) တွင် သီးသန့် option အချို့လည်း ရရှိနိုင်ပါသေးသည်-

* :guilabel:`COORDINATE_PRECISION` အပေါ်တွင်ကြည့်ရှုပါ (GeoJSON အတွက်လည်း အတူတူဖြစ်ပါသည်။)
* :guilabel:`RS` - RS=0x1E character ဖြင့် မှတ်တမ်းများ (records) ကို စတင်ရန် ရှိ/မရှိ။ Feature များကို မည်ကဲ့သို့ ခွဲခြားထားသည်လဲ - :newline (LF) character (Newline Delimited JSON ၊ geojsonl) ဖြင့်သာ သို့မဟုတ် record-separator (RS) character ( GeoJSON Text Sequences ၊ geojsons ကို ပေးထားခြင်း) တစ်ခုကို ထည့်သွင်းခြင်းတို့ ပေါ်မူတည်ပြီး ကွာခြားပါသည်။ NO ကို Default ထားပါ။ အကယ်၍ extension များကို မပံ့ပိုးပေးထားပါက ဖိုင်များကို :file:`.json` extension ဖြင့်ထားရှိပါသည်။ 


.. index:: SAP HANA Spatial
.. _label_hana_spatial:

SAP HANA Spatial Layers (SAP HANA Spatial Layer များ)
------------------------------------------------------

ဤ section တွင် QGIS သည် SAP HANA layers များကို မည်သို့ ဝင်ရောက်ကြည့်ရှုသုံးစွဲ (access) နိုင်သည်နှင့် စပ်လျဉ်းသော အသေးစိတ်အချက်အလက်အချို့ ပါဝင်ပါသည်။ အချိန်အများစုတွင် QGIS သည် ထည့်သွင်းနိုင်သည့် database table များနှင့် view များ  စာရင်းတစ်ခုဖြင့် ရိုးရှင်းစွာ ပံ့ပိုးပေးသင့်ပြီး ၎င်းတို့ကို တောင်းခံမှု (request) ပြုလုပ်သည့်အခါတွင် ထည့်သွင်းသွားမည်ဖြစ်ပါသည်။ သို့ရာတွင် QGIS ထဲသို့ SAP HANA table သို့မဟုတ် view တစ်ခုကို ထည့်သွင်းရာတွင် အခက်အခဲ ရှိနေပါက အောက်ဖော်ပြပါ အချက်အလက်များသည် ဖြစ်ပွားရသည့် အရင်းခံအကြောင်းအရင်း (root cause) ကို နားလည်စေရန်နှင့် ပြဿနာ(issue) ကို ဖြေရှင်းရာတွင် ကူညီပေးနိုင်မည်ဖြစ်ပါသည်။ 

Feature Identification (Feature သတ်မှတ်ခြင်း)
..............................................

QGIS ၏ feature အား ပြန်လည်ပြင်ဆင်နိုင်သည့် စွမ်းဆောင်ရည် (feature editing capabilities) အားလုံးကို အသုံးပြုလိုပါက QGIS သည် layer တစ်ခုထဲရှိ feature တစ်ခုချင်းစီကို ရှင်းလင်းတိကျစွာ (unambiguously) သတ်မှတ်နိုင်ရမည်ဖြစ်ပါသည်။ 
အတွင်းပိုင်း (Internally) တွင် QGIS သည် feature များကို သတ်မှတ်ရန် 64-bit signed integer (64-bit signed integer type ကို အပေါင်း သို့မဟုတ် အနုတ် ကိန်းပြည့်များကို သိမ်းဆည်းရန် အသုံးပြုသည်) တစ်ခုကို အသုံးပြုပြီး negative range (အနုတ် အပိုင်းအခြား) ကို အထူးရည်ရွယ်ချက်များ (special purposes) အတွက် အရန်သိမ်းဆည်းထားပါသည်။

ထို့အတွက်ကြောင့် QGIS ၏ feature အား ပြန်လည်ပြင်ဆင်နိုင်သည့် စွမ်းဆောင်ရည် (feature editing capabilities) များကို အပြည့်အဝ ပံ့ပိုးရန် positive 64-bit integer အဖြစ်သို့ map (ဖော်ပြ) လုပ်ပေးနိုင်သည့် unique key (သိသာထင်ရှားသော key) တစ်ခုကို လိုအပ်မည်ဖြစ်ပါသည်။ အကယ်၍ ထိုကဲ့သို့သော mapping တစ်ခုကို ဖန်တီးရန် မဖြစ်နိုင်ပါက သင့်အနေဖြင့် features များကို ကြည့်ရှုနိုင်သေးသော်လည်း ပြန်လည်ပြင်ဆင်ခြင်း (editing) ကိုမူ ဆောင်ရွက်နိုင်မည်မဟုတ်ပါ။ 

Adding tables (ဇယားများထည့်သွင်းခြင်း)
.......................................

Table တစ်ခုကို layer တစ်ခုအဖြစ် ထည့်သွင်းသောအခါတွင် SAP HANA provider သည် table ၏ primary key ကို သိသာထင်ရှား (unique) သော feature id တစ်ခုအဖြစ် ဖော်ပြရန် အသုံးပြုပါသည်။ ထို့အတွက်ကြောင့် အပြည့်အဝပြန်လည်ပြင်ဆင်နိုင်သည့် ပံ့ပိုးမှု (full feature editing support)ကို ရရှိရန်အတွက် table definition (အဓိပ္ပါယ်ဖွင့်ဆိုသတ်မှတ်ချက်)တွင် primary key တစ်ခုရှိရန် လိုအပ်ပါသည်။ 

SAP HANA provider သည် multi-column primary key (column များစွာကိုအသုံးပြု၍ ဖွဲ့စည်းထားသော primary key များ) များကို ထောက်ပံ့ပေးပါသည်။ သို့ရာတွင် အကောင်းဆုံးသော စွမ်းဆောင်ရည်ကို ရရှိလိုပါက primary key သည် ``INTEGER`` အမျိုးအစားဖြစ်သည့် single column တစ်ခုဖြစ်သင့်ပါသည်။ 

Adding views (မြင်ကွင်းများကို ထည့်သွင်းခြင်း)
...............................................

View တစ်ခုကို layer တစ်ခုအဖြစ်ထည့်သွင်းသည့်အခါတွင် SAP HANA provider သည် feature တစ်ခုကို ရှင်းလင်းတိကျစွာသတ်မှတ်ဖော်ပြသည့် column များကို အလိုအလျောက်သတ်မှတ်ခြင်းမပြုနိုင်ပါ။ ထို့အပြင် view အချို့ သည် 
read-only (ဖတ်ရှုယုံမျှသာ) ဖြစ်ပြီး ပြန်လည်ပြင်ဆင်ခြင်း(edit) ဆောင်ရွက်နိုင်မည်မဟုတ်ပါ။ 

အပြည့်အဝပြန်လည်ပြင်ဆင်နိုင်သည့်ပံ့ပိုးမှု (full feature editing support) ကိုရရှိရန် View သည် updatable (update လုပ်ဆောင်နိုင်သော) ဖြစ်ရမည်ဖြစ်ပြီး (View အတွက် system view ``SYS.VIEWS`` ထဲရှိ ``IS_READ_ONLY`` column ကို check ပြုလုပ်ပါ) QGIS အား feature တစ်ခုကို သတ်မှတ်သည့် တစ်ခု သို့မဟုတ် တစ်ခုထက်ပိုသော column များဖြင့် ကိုယ်တိုင်(manually) ထည့်သွင်းပေးရမည်ဖြစ်သည်။ Column များကို :menuselection:`Layer --> Add Layer --> Add SAP HANA Spatial Layer` အား အသုံးပြုပြီး :guilabel:`Feature id` column ထဲရှိ column များကို select ပြုလုပ်ခြင်းဖြင့် ထည့်သွင်းပေးနိုင်ပါသည်။ အကောင်းဆုံးသော စွမ်းဆောင်ရည် (performance) အတွက် :guilabel:`Feature id` တန်ဖိုးသည် single ``INTEGER`` column တစ်ခုဖြစ်သင့်ပါသည်။

.. index:: PostGIS; ST_Shift_Longitude

Layers crossing 180° longitude (180 ဒီဂရီ လောင်ဂျီတွဒ်ကို ဖြတ်သန်းသည့် Layer များ)
===================================================================================

GIS ပက်ကေ့ချ် အတော်များများသည် 180 ဒီဂရီ လောင်ဂျီတွဒ်မျဉ်းကို ဖြတ်သန်းသည့် ပထဝီဝင်ဆိုင်ရာရည်ညွှန်းကိုးကားစနစ်(geographic reference system) (lat/lon) တစ်ခုဖြင့် layer များကို သိမ်းဆည်းထုပ်ပိုး (wrap) ထားမည်မဟုတ်ပါ။ 
ရလဒ်အနေဖြင့် QGIS ထဲတွင် အဆိုပါ layer တစ်ခုကို ဖွင့်ပါက တစ်ခုနှင့်တစ်ခုနီးကပ်စွာရှိသင့်သည့် တည်နေရာနှစ်ခုကို အလွန်ဝေးကွာခြားနားသည့် တည်နေရာနှစ်ခုတွင် တွေ့မြင်ရမည်ဖြစ်ပါသည်။ 
:numref:`Figure_vector_crossing` တွင် map canvas ၏ ဘယ်ဘက်တွင်ရှိသော သေးငယ်သည့်အမှတ် (Chatham ကျွန်းများ) သည် New Zealand အဓိကကျွန်းများ၏ ညာဘက်ရှိ ဂရစ်ကွက်အတွင်းတွင် ရှိသင့်ပါသည်။ 

.. _figure_vector_crossing:

.. figure:: img/vectorNotWrapping.png
   :align: center

   Map in lat/lon crossing the 180° longitude line
   180 ဒီဂရီ လောင်ဂျီတွဒ်မျဉ်းကို ဖြတ်သန်းသည့် lat/lon ဖြင့် မြေပုံ

Solving in PostGIS (PostGIS တွင် ဖြေရှင်းခြင်းများဆောင်ရွက်ခြင်း)
------------------------------------------------------------------

လုပ်ဆောင်ရမည့်တစ်ချက်သည် PostGIS နှင့် `ST_ShiftLongitude <https://postgis.net/docs/ST_Shift_Longitude.html>`_ function (လုပ်ဆောင်ချက်) ကို အသုံးပြုပြီး လောင်ဂျီတွဒ် တန်ဖိုးများကို အသွင်ကူးပြောင်းမှုများပြုလုပ်ရန် (transform) ဖြစ်ပါသည်။ ဤ function သည် geometry တစ်ခုထဲရှိ feature တစ်ခုချင်းစီ၏ အစိတ်အပိုင်း (component) တစ်ခုချင်းစီထဲရှိ point (အမှတ်)/vertex (ထောင့်မှတ်) တစ်ခုချင်းစီကို ဖတ်ရှုပြီး ၎င်း၏ လောင်ဂျီတွဒ် ကိုဩဒိနိတ် (longitude coordinate) ကို -180..0 ဒီဂရီ မှ 180..360 ဒီဂရီ သို့ ကူးပြောင်းပေးပြီး ဤ ranges (အပိုင်းအခြား) အတွင်းဖြစ်ပါက အပြန်အလှန် (vice versa) ကူးပြောင်းခြင်းဆောင်ရွက်ပါသည်။ ဤ function သည် အချိုးကျ (symmetrical) ဖြစ်သည့်အတွက် ရလဒ်အနေဖြင့် 0..360 ဒီဂရီ data သည် -180..180 ဒီဂရီ data ၏ ကိုယ်စားပြုဖော်ပြချက် (representation) ဖြစ်ပြီး -180..180 ဒီဂရီ data သည် 0..360 ဒီဂရီ data ၏ ကိုယ်စားပြုဖော်ပြချက်ဖြစ်ပါသည်။ 

.. _figure_vector_crossing_map:

.. figure:: img/vectorWrapping.png
   :align: center
   :width: 25em

   **ST_ShiftLongitude** function ကို အသုံးပြုပြီး 180 ဒီဂရီ လောင်ဂျီတွဒ်ကို ဖြတ်သန်းခြင်း 

#. ဥပမာ- DB Manager plugin ကို အသုံးပြုပြီး PostGIS ထဲသို့ data ကို Importပြုလုပ်ပါ။  (:ref:`vector_import_data_in_postgis`) 
#. အောက်ဖော်ပြပါ command ကို ထုတ်ပြန်ရန်အတွက် PostGIS command line interface ကို အသုံးပြုပါ- 

   .. code-block:: sql

      -- In this example, "TABLE" is the actual name of your PostGIS table
      update TABLE set geom=ST_ShiftLongitude(geom);

#. အရာအားလုံးသည် အဆင်ပြေချောမွေ့နေပါက update ပြုလုပ်လိုက်သည့် feature များ၏ အရေအတွက်နှင့်
   ပတ်သက်ပြီး အတည်ပြုချက် (confirmation) တစ်ခုကို ရရှိသင့်ပါသည်။ ထို့နောက် သင့်အနေဖြင့် map (မြေပုံ) ကို ထည့်သွင်းနိုင်မည်ဖြစ်ပြီး ကွဲပြားခြားနားချက်ကို တွေ့မြင်နိုင်မည်ဖြစ်ပါသည်။ (Figure_vector_crossing_map_) 



.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |dbManager| image:: /static/common/dbmanager.png
   :width: 1.5em
.. |nix| image:: /static/common/nix.png
   :width: 1em
.. |osx| image:: /static/common/osx.png
   :width: 1em
.. |setProjection| image:: /static/common/mActionSetProjection.png
   :width: 1.5em
