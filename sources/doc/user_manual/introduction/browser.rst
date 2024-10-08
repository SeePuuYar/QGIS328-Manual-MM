﻿.. Purpose: This chapter aims to present the Browser panel in
.. all its glory.

.. index:: Browser panel
.. _`label_browserpanel`:

The Browser panel (ရှာဖွေကြည့်ရှုသည့် Panel)
=============================================


.. contents::
   :local:
   :depth: 2

QGIS Browser panel သည် QGIS တွင် ကိုင်တွယ်အသုံးပြုနိုင်သော GIS အရင်းအမြစ်များကို ရှာဖွေခြင်း၊
စစ်‌ဆေးခြင်း၊ ကူးယူခြင်းနှင့် ထည့်သွင်းအသုံးပြုခြင်းများပြုလုပ်ရာတွင် ထိရောက်ကောင်းမွန်သော Tool တစ်ခုဖြစ်သည်။
ထို Broswer ထဲတွင် QGIS မှကိုင်တွယ်လုပ်နိုင်သည့် အရာများကိုသာ ဖော်ပြထားပါသည်။

QGIS Browser panel ကို :ref:`browser_panel` တွင်ဖော်ပြထားသည့်အတိုင်း  မိမိ၏ Project တွင်
GIS ဒေတာများကို ရှာဖွေထည့်သွင်းခြင်း၊ စစ်ဆေးခြင်းများ ပြုလုပ်ရာတွင် အသုံးပြုနိုင်သည်။ ထို့အပြင် Project files ၊ Python scripts ၊ Processing scripts
နှင့် Processing models များကို ဖိဆွဲ၍ ထည့်သွင်းနိုင်ပါသည်။

Python scripts ၊ Processing scripts နှင့် Processing models များကို ပြင်ပ Editor Tool တစ်ခုခု
သို့မဟုတ် Graphical Modeller တို့တွင် Edit ပြုလုပ်ရန်အတွက်လည်း အသုံးပြုနိုင်ပါသည်။ 

ထို့အပြင် :guilabel:`Layers` Panel မှ :guilabel:`Browser` Panel အတွင်းသို့ Layer များကို ဖိဆွဲ၍ထည့်သွင်းနိုင်ပါသည်။
ဥပမာ - GeoPackage သို့မဟုတ် PostGIS database အတွင်းသို့ ထည့်သွင်းနိုင်ပါသည်။ 

.. _figure_browser_panel:

.. figure:: img/browser_panel.png
   :align: center

   Browser panel

Browser panel ( :numref:`figure_browser_panel` ) တွင် browser မှ ကိုင်တွယ်အသုံးပြုနိုင်သည့်အရင်းအမြစ်များကို စုစည်းထားသည့် ထိပ်ဆုံးအဆင့်အရင်းအမြစ် (Entry) များကို
အဆင့်ဆင့်ဖွင့်နိုင်သည့်ပုံစံဖြင့် ဖော်ပြထားသည်။ Entry နာမည်၏ ဘယ်ဘက်ရှိ |browserExpand| ကိုနှိပ်ပြီး အောက်တွင်ပါဝင်သည်များကို ဖြန့်ချနိုင်ပြီး |browserCollapse| ကို နှိပ်၍ ပြန်လည်စုစည်းထားနိုင်သည်။
|collapseTree| :sup:`Collapse All` ကိုနှိပ်ခြင်းဖြင့် ထိပ်ဆုံးအဆင့် entry အားလုံးကို ပြန်စုစည်းနိုင်သည်။

:menuselection:`Settings --> Interface Customization` သည် GIS အရင်းအမြစ်များကို ပိတ်ထားရာတွင် အသုံးပြုနိုင်သည်။
ဥပမာ - Browser အတွင်း Python scripts များကို မဖော်ပြစေလိုလျှင် :menuselection:`Browser --> py` ကို ပိတ်နိုင်ပြီး
ကွန်ပျူတာ၏မူရင်း folder ကို browser အတွင်းမှ ဖယ်ရှားလိုပါက :menuselection:`Browser --> special:Home` ကို အမှန်ခြစ်ဖြုတ်၍ ဖယ်ရှားနိုင်သည်။

Filter (စစ်ထုတ်မှု) (|filterMap| :sup:`Filter Browser`) ကို entry နာမည်ပေါ်မူတည်၍ ရှာဖွေရာတွင် အသုံးပြုနိုင်ပါသည်။ (Hierarchy ထဲရှိ leaf entry များနှင့် node entry နှစ်မျိုးစလုံး) 
Filter ဘေးရှိ |options| :sup:`Options` ကို နှိပ်၍ အောက်သို့ဆွဲချလိုက်လျှင်-

* :guilabel:`Case Sensitive` search (စာလုံးအကြီးအသေးအရရှာခြင်း) ကို အဖွင့်အပိတ်ပြုလုပ်နိုင်ခြင်း၊
* :guilabel:`Filter pattern syntax` (စစ်လိုသည့်ပုံစံတည်ဆောက်ခြင်း)ကို အောက်ပါတို့မှ တစ်ခုခုတို့တွင် သတ်မှတ်နိုင်ခြင်း-

  * :guilabel:`Normal` (ပုံမှန်အတိုင်း)
  * :guilabel:`Wildcard(s)` ( * နှင့် ? များအသုံးပြုခြင်း)
  * :guilabel:`Regular Expressions`

Entry တစ်ချို့အကြောင်း အသုံးဝင်သည့် အချက်အလက်များကို ဖော်ပြပေးသည့် *Properties widget* ကို |metadata|:sup:`Enable/disable properties widget` ခလုတ်ကို အသုံးပြု၍ အဖွင့်အပိတ်ပြုလုပ်နိုင်ပါသည်။
ဖွင့်လိုက်ပါက ၎င်းနှင့်ပတ်သက်သောအချက်အလက်များသည် Browser Panel ၏ အောက်ခြေ၌ :numref:`figure_properties_widget` တွင် ဖော်ပြထားသည့်အတိုင်း ပေါ်လာလိမ့်မည်။

.. _figure_properties_widget:

.. figure:: img/browser_p_properties_w.png
   :align: center

   Properties widget

:menuselection:`View --> Panels` တွင် :guilabel:`Browser (2)` ကိုဖွင့်ပေးခြင်းဖြင့် နောက်ထပ် Browser panel တစ်ခုကို ပွင့်လာစေပါမည်။
ထိုသို့ Browser panel နှစ်ခုဖွင့်ထားခြင်းသည် Folder တစ်ခုစီ၌ရှိသော Layer များကို ကူးယူရာတွင် အသုံးဝင်ပါသည်။


Resources that can be opened / run from the Browser (Browser မှ ဖွင့်နိုင်သော/ လုပ်ဆောင်နိုင်သော အရင်းအမြစ်များ)
-----------------------------------------------------------------------------------------------------------------
 
Browser Panel တွင် အောက်တွင် ဖော်ပြထားသည့်အတိုင်း လုပ်ငန်းဆောင်တာများစွာကို ဆောင်ရွက်နိုင်ပါသည်- 

* Vector ၊ raster နှင့် mesh layres များကို မိမိ၏ map အတွင်းသို့ double-click နှိပ်၍လည်းကောင်း၊
  Map Canvas ပေါ်သို့ အရင်းအမြစ်ဖိုင်များကို တိုက်ရိုက်ဖိဆွဲယူ၍လည်းကောင်း သို့မဟုတ်
  ထည့်သွင်းလိုသော layers များကို ရွေးချယ်ပြီးနောက် |addLayer|:sup:`Add Selected Layers` ကို click နှိပ်၍ လည်းကောင်း ထည့်သွင်းနိုင်ပါသည်။ 
* Processing algorithms များပါဝင်သော Python scripts များကို double-click နှိပ်၍လည်းကောင်း၊ map canvas ပေါ်သို့
  အရင်းအမြစ်ဖိုင်များကို တိုက်ရိုက်ဖိဆွဲယူ၍ Run နိုင်သည်။
* Models များကို double-click နှိပ်၍လည်းကောင်း၊ မြေပုံနောက်ခံမျက်နှာပြင်ပေါ်သို့ အရင်းအမြစ်ဖိုင်များကို တိုက်ရိုက်ဖိဆွဲယူ၍လည်းကောင်း Run နိုင်သည်။ 
* Context menu (အကြောင်းအရာ menu) အသုံးပြု၍ QGIS Project ဖိုင်မှ :guilabel:`Extract Symbols...` (Symbol များ ထုတ်ယူခြင်း) ပြုလုပ်နိုင်ပါသည်။ 
* Context Menu ထဲရှိ :guilabel:`Open <file type> Externally...` သို့ ဝင်ရောက်၍ ပုံမှန်သတ်မှတ်ထားသည့်
  application များဖြင့် ဖိုင်များကို ဖွင့်နိုင်သည်။ ဥပမာ - HTML files ၊ spreadsheets ၊ images ၊ PDFs ၊ text files အမျိုးအစားများဖြစ်ပါသည်။ 
* အရင်းအမြစ်(Entry) များကို ကူးယူနိုင်သည်။ 
* Layers များကို အမည်ပြောင်းလဲခြင်း၊ ဖျက်ခြင်းများပြုလုပ်လိုပါက Context menu မှ :menuselection:`Manage -->` သို့ဝင်ရောက်၍ ပြုလုပ်နိုင်ပါသည်။ 
* :guilabel:`Show in Files` ကို နှိပ်ပါက file explorer window ပွင့်လာပြီးနောက် ဖိုင်တည်နေရာကို
  သိရှိနိုင်ပြီး ဖိုင်ကို တိုက်ရိုက်ရွေးချယ်နိုင်ပါသည်။ 

အောက်တွင်ဖော်ပြထားသည့် ထိပ်ပိုင်းအဆင့် entry များအောက်တွင် စဉ်ထားသည့်အရင်းအမြစ်အုပ်စုအမျိုးမျိုးအတွက် Resource specific action (အရင်းအမြစ်နှင့်ပတ်သက်သည့် သီးသန့်လုပ်ဆောင်ချက်) များကို စာရင်းပြုလုပ်ထားပါသည်။ 


Browser panel top-level entries (Browser panel ရှိ ထိပ်ပိုင်းအဆင့် Entry များ)
-------------------------------------------------------------------------------

Favorites (နှစ်သက်ရာများ)
..........................

မကြာခဏ အသုံးပြုလေ့ရှိသော ဖိုင်တည်နေရာများကို နှစ်သက်ရာများ (Favorites) အဖြစ် မှတ်သားထားနိုင်သည်။
ထိုသို့ မှတ်သားထားသော ဖိုင်များသည် ဤနေရာတွင် ပေါ်လာမည်ဖြစ်သည်။ 

Home တွင် ပါဝင်သော လုပ်ဆောင်ချက်များအပြင် Context menu မှတဆင့် အမည်ပြောင်းလဲလိုပါက
:guilabel:`Rename Favorite...` ဖြင့် နှစ်သက်ရာများကို အမည်ပြောင်းလဲနိုင်ပြီး ဖယ်ရှားလိုပါက :guilabel:`Remove Favorite` ဖြင့်
နှစ်သက်ရာများကို ဖယ်ရှားခြင်း ပြုလုပ်နိုင်ပါသည်။ 


Spatial Bookmarks (တည်နေရာမှတ်သားသိမ်းဆည်းထားသည်များ)
......................................................

ဤနေရာတွင် အလုပ်လုပ်နေသော Project ရှိ မိမိသိမ်းဆည်းလိုသော တည်နေရာများကို မှတ်သားနိုင်သည်။
ထိုတည်နေရာများကို Project Bookmarks နှင့် User Bookmarks ဟူ၍ နှစ်မျိုးခွဲခြားနိုင်ပြီး Project အတွင်း၌ တည်နေရာများကို
သိမ်းဆည်းလိုပါက :guilabel:`Project Bookmarks` တွင် မှတ်သားနိုင်၍ မိမိကိုယ်ပိုင်ကွန်ပျူတာ တွင် သိမ်းဆည်းလိုပါက
:guilabel:`User Bookmarks` တွင် မှတ်သားနိုင်ပါသည်။

ထိပ်ပိုင်းအဆင့် context menu မှ  Bookmark တစ်ခု (:guilabel:`New Spatial Bookmark...`) ဖန်တီးနိုင်ပြီး ၊ :guilabel:`Show the Spatial Bookmark Manager` ၊
:guilabel:`Import Spatial Bookmarks...` နှင့် :guilabel:`Export Spatial Bookmarks...` တို့မှတဆင့်
Bookmark တစ်ခုကို ဖန်တီးသိမ်းဆည်းနိုင်သည်။ 

မှတ်သားထားသော Spatial Bookmark Group Entry များကိုမူ Bookmark အသစ်တစ်ခုပြောင်းလဲထုတ်ယူလိုပါက
:guilabel:`Export Spatial Bookmarks...` ကိုပြုလုပ်၍လည်းကောင်း၊
အသစ်တစ်ခုဖန်တီးလိုပါက :guilabel:`New Spatial Bookmark...` ကို ပြုလုပ်၍လည်းကောင်း၊ 
အမည်ပြောင်းလဲလိုပါက :guilabel:`Rename Bookmark Group` ကို ပြုလုပ်၍လည်းကောင်း၊ 
Bookmark Group အား ပယ်ဖျက်လိုပါက :guilabel:`Delete Bookmark Group` ကိုပြုလုပ်၍လည်းကောင်း အသုံးပြုနိုင်သည်။

Bookmark Entry များအတွက် Bookmark များနေရာသို့ Zoom ချဲ့ ကြည့်ရန် :guilabel:`Zoom to Bookmark` ကိုပြုလုပ်ခြင်း၊
တည်းဖြတ်ပြင်ဆင်ခြင်းအတွက် :guilabel:`Edit Spatial Bookmark...` နှင့် ပယ်ဖျက်ခြင်းအတွက် :guilabel:`Delete Spatial Bookmark` တို့ကိုပြုလုပ်နိုင်သည်။


Project Home (Project တည်ရှိရာနေရာ)
....................................

Project Home သည် လုပ်ဆောင်နေသော Project ဖိုင်တစ်ခုအား သိမ်းဆည်းပြီးပါက ထိုဖိုင်တွင် အသုံးပြုခဲ့သော data များ၊
script၊ models နှင့် text ကဲ့သို့သော အခြားအကြောင်းအရာများကို မှတ်သားထားသော နေရာဖြစ်သည်။ ထို့ကြောင့် ထို Project အတွင်းရှိ
data များကို ပြန်လည်အသုံးပြုလိုပါက :guilabel:`Browser` panel အတွင်းရှိ Project Home အောက်တွင် အလွယ်တကူရှာဖွေတွေ့ရှိနိုင်ပါသည်။ 

Project Home သည် သိမ်းဆည်းထားသော Project များ၏ ပုံမှန်သိမ်းဆည်းရာလမ်းကြောင်းဖြစ်သော်လည်း
၎င်းအား :menuselection:`Project --> Properties... --> General --> Project home` မှတဆင့်
ပြောင်းလဲနိုင်သည်။ နောက်တစ်နည်းအားဖြင့် Browser Panel ရှိ :guilabel:`Project Home` အား right-click နှိပ်၍
:guilabel:`Set project home...` မှတဆင့် ဖိုင်သိမ်းဆည်းရာလမ်းကြောင်းအား သတ်မှတ်ပေးနိုင်သည်။ အထူးသဖြင့် Folder အား
သိမ်းဆည်းရာလမ်းကြောင်းစိတ်ကြိုက်ရွေးချယ်သတ်မှတ်ခြင်းသည် Project ဖိုင်များအား  dataset များနှင့်အတူ မူရင်း Folder တွင်
မသိမ်းဆည်းထားသည့်အခါ အလွန်အသုံးဝင်ပါသည်။


Drives and file system (ဖိုင်သိမ်းဆည်းရာနေရာများ နှင့် ဖိုင်စနစ်)
..................................................................

Browser Panel တွင် နောက်ထပ်ပါဝင်သည့် item များသည် အသုံးပြုသည့် ကွန်ပျူတာလုပ်ဆောင်မှုစနစ် (Operating System - OS) ပေါ်တွင် မူတည်ပြီး ၎င်း file system ၏ ထိပ်ပိုင်းအဆင့် entry များနှင့်သက်ဆိုင်ပါသည်။

အဓိကအားဖြင့်-

* အသုံးပြုသူ၏လက်ရှိ home folder ကို ရည်ညွှန်းသော :guilabel:`Home` folder
* Unix ကို အခြေခံသော ကွန်ပျူတာလုပ်ဆောင်မှုစနစ် (OS) ပါရှိသည့် ကွန်ပျူတာများတွင် root :guilabel:`/` folder 
* ချိတ်ဆက်ထားသော Drives များ - ကွန်ပျူတာအတွင်း သို့မဟုတ် ကွန်ယက် (Network)။ OS ပေါ်မူတည်ပြီး တိုက်ရိုက် (ဥပမာ - ``C:\` ၊ ``D:\``) သို့မဟုတ် ``/Volumes`` entry ကိုဖြတ်၍ list လုပ်ထားပါသည်။ 

Folder နှင့် Drives တစ်ခုချင်းစီ၏ အကြောင်းအရာ menu မှ ဆက်လက်လုပ်ဆောင်နိုင်သော function များမှာ အောက်ပါအတိုင်းဖြစ်သည်-

* ပါဝင်သောအကြောင်းအရာများကို  Refresh ပြန်လုပ်နိုင်သည်။
* :menuselection:`New -->` tab မှတဆင့် ဖိုင်သိမ်းဆည်းရာလမ်းကြောင်းအသစ် :guilabel:`Directory` ၊ GIS data format များဖြစ်သည့် :guilabel:`GeoPackage` နှင့် ESRI :guilabel:`Shapefile` တို့ကို အသီးသီးဖန်တီးနိုင်သည်။
* Browser Panel မှ ဖိုင်သိမ်းဆည်းရာလမ်းကြောင်းအား ဖျောက်ထားခြင်း (:guilabel:`Hide from Browser`) ကိုလုပ်ဆောင်နိုင်သည်။
* Browser Panel ရှိ အခြား folder များနှင့်မတူညီဘဲ အလွယ်တကူရှာ‌ဖွေနိုင်ရန် မိမိစိတ်ကြိုက်အရောင်ပြောင်းလိုပါက :guilabel:`Set color` ကိုအသုံးပြု၍ လုပ်ဆောင်နိုင်သည်။
* :guilabel:`Scanning` ကို လုပ်ဆောင်နိုင်သည်-

  * သီးသန့်ဖိုင်သိမ်းဆည်းရာလမ်းကြောင်း (Particular Directory) ကို စောင့်ကြည့်ပေးရန်နှင့် အလိုအလျောက် update ပြုလုပ်ပေးရန် |checkbox| :guilabel:`Monitor for changes` ကိုအသုံးပြုနိုင်သည်။ ဤ Setting သည် ရွေးချယ်ထားသော Directory နှင့် ၎င်း Directory အောက်ရှိ ဖိုင်အခွဲများအားလုံးအပေါ် သက်ရောက်စေနိုင်ပါသည်။ အကယ်၍ မိမိ Project တွင် ပါဝင်သော Network drives များတွင် မည်သည့်ပြဿနာမှမပါရှိကြောင်း သေချာလျှင် |checkbox| :guilabel:`Monitor for changes` အား အသုံးပြုနိုင်ပြီး အကြောင်းအမျိုးမျိုးကြောင့် Directory များအား အလိုအလျောက် update မပြုလုပ်လိုပါက ပြန်ဖြုတ်ထားနိုင်သည်။ ပုံမှန်အားဖြင့် Network drives များကို အလိုအလျောက် Update ပြုလုပ်မည်မဟုတ်ပါ။ 
  * Directory အား အမြန် scan ဖတ်လိုလျှင် |unchecked| :guilabel:`Fast scan this directory` မှတဆင့် ပြုလုပ်နိုင်သည်။
* File Manager မှ Directory အား ဖွင့်လိုပါက :guilabel:`Open Directory...` ကို နှိပ်၍ ဖွင့်နိုင်သည်။
* Directory အား Terminal window ဖြင့် ဖွင့်လိုပါက :guilabel:`Open in Terminal...` မှတဆင့် ဖွင့်နိုင်သည်။
* Folder ၏ Properties အား သိလိုလျှင် :guilabel:`Properties...` ကို နှိပ်၍ ကြည့်နိုင်ပြီး မူရင်း Folder ကြီးတစ်ခုလုံး၏ Properties ကို ကြည့်လိုလျှင် :guilabel:`Directory  Properties...` မှတဆင့် ကြည့်နိုင်သည်။


Database entries (Database ထည့်သွင်းမှုများ)
.............................................

အသုံးပြုသည့် OS နှင့် ကွန်ပျူတာအတွင်း ထည့်သွင်းထားသည့် Drivers များပေါ် မူတည်၍ QGIS တွင် Database ပုံစံအမျိုးမျိုးကို အသုံးပြုနိုင်သည်။
အောက်တွင် Dataset tree ၏ အဆင့်တစ်ခုချင်းစီအလိုက် ပါဝင်သော အကြောင်းအရာ menu များကို ဖော်ပြထားသည်။

.. You might want to use https://www.tablesgenerator.com/text_tables (Text tab) to update the next table. Particularly useful if you need to add, resize or move columns

+---------------+--------------------------------------------+------------------------------------------------------------------------------------+
| Level         | Context menu                               |                                  Type of database                                  |
|               |                                            +--------------+--------------+------------+------------+---------------+------------+
|               |                                            | |geoPackage| | |spatialite| | |postgis|  | |hana|     | |mssql|       | |oracle|   |
|               |                                            | GeoPackage   | SpatiaLite   | PostGIS    | SAP HANA   | MS SQL Server | Oracle     |
|               |                                            | ([1]_)       |              |            |            |               |            |
+---------------+--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
| Top menu      | Create a :guilabel:`New Connection…`       | |checkbox|   | |checkbox|   | |checkbox| | |checkbox| | |checkbox|    | |checkbox| |
|               | to an existing database                    |              |              |            |            |               |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | :guilabel:`Create Database…`               | |checkbox|   | |checkbox|   |            |            |               |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | :guilabel:`Save Connections…` details      |              |              | |checkbox| | |checkbox| | |checkbox|    |            |
|               | to a file                                  |              |              |            |            |               |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | :guilabel:`Load Connections…`              |              |              | |checkbox| | |checkbox| | |checkbox|    |            |
+---------------+--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
| Connection    | :guilabel:`Refresh` a connection           |              |              | |checkbox| | |checkbox| | |checkbox|    |            |
| / Database    +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | :guilabel:`Edit Connection…` settings      |              |              | |checkbox| | |checkbox| | |checkbox|    |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | :guilabel:`Remove Connection`              | |checkbox|   | |checkbox|   | |checkbox| | |checkbox| | |checkbox|    |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | :guilabel:`Delete <database_name>`         | |checkbox|   | |checkbox|   |            |            |               |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | :guilabel:`Compact Database (VACUUM)`      | |checkbox|   |              |            |            |               |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | Create a :guilabel:`New Schema…`           |              |              | |checkbox| | |checkbox| | |checkbox|    |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | Create a :guilabel:`New Table…`            | |checkbox|   | |checkbox|   | |checkbox| | |checkbox| |               |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | :guilabel:`Execute SQL…` query             | |checkbox|   | |checkbox|   | |checkbox| | |checkbox| |               |            |
+---------------+--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
| Schema        | :guilabel:`Refresh` a schema               |              |              | |checkbox| | |checkbox| | |checkbox|    |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | :menuselection:`Schema Operations -->      |              |              |            |            |               |            |
|               | Rename Schema…`                            |              |              | |checkbox| | |checkbox| | |checkbox|    |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | :menuselection:`Schema Operations -->      |              |              |            |            |               |            |
|               | Delete Schema…`                            |              |              | |checkbox| | |checkbox| | |checkbox|    |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | Create a :guilabel:`New Table…`            |              |              | |checkbox| | |checkbox| |               |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | :guilabel:`Execute SQL…` query             |              |              | |checkbox| | |checkbox| |               |            |
+---------------+--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
| Table / Layer | :menuselection:`Table Operations -->       |              |              |            |            |               |            |
|               | Rename Table…`                             |              |              | |checkbox| | |checkbox| | |checkbox|    |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | :menuselection:`Table Operations -->       |              |              |            |            |               |            |
|               | Truncate Table…`                           |              |              | |checkbox| |            | |checkbox|    |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | :guilabel:`Execute SQL…` query             | |checkbox|   | |checkbox|   | |checkbox| |            |               |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | :menuselection:`Export Layer --> To file…` | |checkbox|   | |checkbox|   | |checkbox| | |checkbox| | |checkbox|    |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | :menuselection:`Manage -->                 |              |              |            |            |               |            |
|               | Rename Layer <layer_name>…`                | |checkbox|   | |checkbox|   |            |            |               |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | :menuselection:`Manage -->                 |              |              |            |            |               |            |
|               | Delete Layer <layer_name>…`                | |checkbox|   | |checkbox|   | |checkbox| | |checkbox| | |checkbox|    |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | :menuselection:`Manage -->                 | |checkbox|   | |checkbox|   | |checkbox| | |checkbox| | |checkbox|    |            |
|               | Delete Selected Layers`                    |              |              |            |            |               |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | :menuselection:`Manage -->                 | |checkbox|   | |checkbox|   | |checkbox| | |checkbox| | |checkbox|    |            |
|               | Add Layer to Project`                      |              |              |            |            |               |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | :menuselection:`Manage -->                 | |checkbox|   | |checkbox|   | |checkbox| | |checkbox| | |checkbox|    |            |
|               | Add Selected Layers to Project`            |              |              |            |            |               |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | Open :guilabel:`Layer Properties…` dialog  | |checkbox|   | |checkbox|   | |checkbox| | |checkbox| | |checkbox|    |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | Open :guilabel:`File Properties…` dialog   | |checkbox|   |              |            |            |               |            |
+---------------+--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
| Fields        | :guilabel:`Add New Field…`                 | |checkbox|   | |checkbox|   | |checkbox| | |checkbox| |               |            |
+---------------+--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
| Field         | :guilabel:`Set Alias…`                     | |checkbox|   |              |            |            |               |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | :guilabel:`Set Comment…`                   | |checkbox|   |              | |checkbox| |            |               |            |
|               +--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+
|               | :guilabel:`Delete Field…`                  | |checkbox|   | |checkbox|   | |checkbox| | |checkbox| |               |            |
+---------------+--------------------------------------------+--------------+--------------+------------+------------+---------------+------------+


.. [1] GDAL (Geospatial Data Abstraction Library) မှ ထောက်ပံ့ပေးထားသည့် `vector file formats <https://gdal.org/drivers/vector/index.html>`_ များဖြစ်သည့် ESRI File Geodatabase ၊ FlatGeobuf ၊ GeoParquet ၊ NetCDF ကဲ့သို့သော Entry အမျိုးမျိုးကိုလည်း ဆီလျော်ပါက အသုံးပြုနိုင်သည်။


Tiles and Web Services (Tiles များနှင့် Web ဝန်ဆောင်မှုများ)
.............................................................

+---------------+----------------------------------------------+-----------------------------------------------------------------------------------------+
| Level         | Context menu                                 |                                               Type of services                          |
|               |                                              +------------+-------------------+------------+------------+----------------+-------------+
|               |                                              | |wms|      | |vectorTileLayer| | |xyz|      | |wcs|      | |wfs|          | |afs|       |
|               |                                              | WMS / WMTS | Vector Tiles      | XYZ Tiles  | WCS        | WFS / OGC      | ArcGIS REST |
|               |                                              |            |                   |            |            | API - Features | Servers     |
+===============+==============================================+============+===================+============+============+================+=============+
| Top menu      | Create a :guilabel:`New Connection…`         | |checkbox| |                   | |checkbox| | |checkbox| | |checkbox|     | |checkbox|  |
|               +----------------------------------------------+------------+-------------------+------------+------------+----------------+-------------+
|               | Create a :guilabel:`New Generic Connection…` |            | |checkbox|        |            |            |                |             |
|               +----------------------------------------------+------------+-------------------+------------+------------+----------------+-------------+
|               | Create a :guilabel:`New ArcGIS Vector Tile   |            | |checkbox|        |            |            |                |             |
|               | Service Connection…`                         |            |                   |            |            |                |             |
|               +----------------------------------------------+------------+-------------------+------------+------------+----------------+-------------+
|               | :guilabel:`Save Connections…` details        | |checkbox| | |checkbox|        | |checkbox| | |checkbox| | |checkbox|     | |checkbox|  |
|               | to a file                                    |            |                   |            |            |                |             |
|               +----------------------------------------------+------------+-------------------+------------+------------+----------------+-------------+
|               | :guilabel:`Load Connections…`                | |checkbox| | |checkbox|        | |checkbox| | |checkbox| | |checkbox|     | |checkbox|  |
+---------------+----------------------------------------------+------------+-------------------+------------+------------+----------------+-------------+
| Connection    | :guilabel:`Refresh` connection               | |checkbox| |                   | |checkbox| | |checkbox| | |checkbox|     | |checkbox|  |
|               +----------------------------------------------+------------+-------------------+------------+------------+----------------+-------------+
|               | :guilabel:`Edit…` connection settings        | |checkbox| | |checkbox|        | |checkbox| | |checkbox| | |checkbox|     | |checkbox|  |
|               +----------------------------------------------+------------+-------------------+------------+------------+----------------+-------------+
|               | :guilabel:`Delete` connection                | |checkbox| | |checkbox|        | |checkbox| | |checkbox| | |checkbox|     | |checkbox|  |
|               +----------------------------------------------+------------+-------------------+------------+------------+----------------+-------------+
|               | :guilabel:`View Service Info` in Web browser |            |                   |            |            |                | |checkbox|  |
+---------------+----------------------------------------------+------------+-------------------+------------+------------+----------------+-------------+
| Table / Layer | :menuselection:`Export Layer --> To File...` | |checkbox| |                   | |checkbox| | |checkbox| | |checkbox|     | |checkbox|  |
|               +----------------------------------------------+------------+-------------------+------------+------------+----------------+-------------+
|               | :guilabel:`Add layer to Project`             | |checkbox| | |checkbox|        | |checkbox| | |checkbox| | |checkbox|     | |checkbox|  |
|               +----------------------------------------------+------------+-------------------+------------+------------+----------------+-------------+
|               | Open :guilabel:`Layer properties…` dialog    | |checkbox| | |checkbox|        | |checkbox| | |checkbox| | |checkbox|     | |checkbox|  |
|               +----------------------------------------------+------------+-------------------+------------+------------+----------------+-------------+
|               | :guilabel:`View Service Info` in Web browser |            |                   |            |            |                | |checkbox|  |
+---------------+----------------------------------------------+------------+-------------------+------------+------------+----------------+-------------+



Resources (အရင်းအမြစ်များ)
---------------------------

* QGIS Project file တွင် ပါဝင်သော အကြောင်းအရာ menu မှ အောက်ပါတို့ကို လုပ်ဆောင်နိုင်သည်-

  * :guilabel:`Open Project` ကိုသုံး၍ Project ကို ဖွင့်နိုင်သည်။
  * :guilabel:`Extract Symbols...` ကိုနှိပ်ပါက သင်္ကေတများကို ထုတ်ယူနိုင်ရန် style manager ပေါ်လာမည်ဖြစ်ပြီး ထို style manager မှတဆင့် သင်္ကေတများကို XML file အဖြစ် ပြောင်းလဲထုတ်ယူခြင်း၊ ပုံမှန်သုံးမည့် Default သင်္ကေတ အဖြစ် သတ်မှတ်ခြင်းနှင့် PNG သို့မဟုတ် SVG format အဖြစ် ထုတ်ယူခြင်းတို့ကို ဆောင်ရွက်နိုင်သည်။
  *  Project ၏ properties များကို ကြည့်ရှုရန် :guilabel:`File Properties...` သို့ ဝင်ရောက်နိုင်သည်။

  Project တွင်ပါဝင်သော  Layers များကိုမြင်နိုင်ရန် Project File ကို ဖြန့်ထုတ်နိုင်သည်။
  Layer ၏ Context Menu သည် Browser Panel ရှိ အခြား Entry များလိုပင် အလားတူလုပ်ဆောင်ချက်များကို ဆောင်ရွက်ပေးနိုင်သည်။

* QGIS Layer Definition Files (QLR) များအတွက် Context Menu မှ အောက်ဖော်ပြပါ လုပ်ငန်းများဆောင်ရွက်နိုင်ပါသည်-

  * :menuselection:`Export Layer --> To file` ကိုအသုံးပြု၍ export ထုတ်ယူခြင်း၊
  * :guilabel:`Add Layer to Project` ကိုအသုံးပြု၍ project အတွင်းသို့ ထည့်သွင်းအသုံးပြုခြင်း၊
  * :guilabel:`Layer Properties...` ကိုအသုံးပြု၍ Properties များကို ကြည့်ရှုစစ်ဆေးခြင်း၊

* Processing models (စနစ်တကျလုပ်ဆောင်သည့် model များ) (.model3) များအတွက် Context Menu မှ အောက်ဖော်ပြပါ လုပ်ငန်းများဆောင်ရွက်နိုင်ပါသည်-

  * :guilabel:`Run Model...`  (Model ကို အလုပ်လုပ်စေခြင်း)
  * :guilabel:`Edit Model...` (Model ကို ပြင်ဆင်မှုများ လုပ်ဆောင်ခြင်း)

* QGIS Print Composer templates (မြေပုံ Layout အတွက် အသင့်အသုံးပြုနိုင်သည့်ပုံစံများ) (QPT) များအတွက် Context Menu မှ အောက်ဖော်ပြပါ လုပ်ငန်းများဆောင်ရွက်နိုင်ပါသည်-

  * :guilabel:`New Layout from Template` ကိုအသုံးပြု၍ Layout အသစ် ဖန်တီးခြင်း

* Python scripts (.py) များအတွက် Context Menu မှ အောက်ဖော်ပြပါ လုပ်ငန်းများဆောင်ရွက်နိုင်ပါသည်-

  * :guilabel:`Run script...` ကိုအသုံးပြု၍ Script အား အလုပ်လုပ်စေခြင်း၊
  * :guilabel:`Open in External Editor` ကိုအသုံးပြု၍ ပြင်ပ Editor tool တစ်ခုခုတွင် Script အား Edit ပြုလုပ်ခြင်း၊

* အသိအမှတ်ပြုထားသည့် Raster format များအတွက် Context Menu မှ အောက်ဖော်ပြပါ လုပ်ငန်းများဆောင်ရွက်နိုင်ပါသည်-

  * :guilabel:`Delete File <dataset name>` ကိုအသုံးပြု၍ ဖိုင်များကို ပယ်ဖျက်ခြင်း၊
  * :menuselection:`Export Layer --> To file` ကိုအသုံးပြု၍ Layer များကို ထုတ်ယူခြင်း၊
  * :guilabel:`Add Layer to Project` ကိုအသုံးပြု၍ project အတွင်းသို့ ထည့်သွင်းအသုံးပြုခြင်း၊
  * :guilabel:`Layer Properties...` ကိုအသုံးပြု၍ Properties များကို ကြည့်ရှုစစ်ဆေးခြင်း၊

  အခြား format များအတွက် :guilabel:`Open <file type> Externally...` ကိုအသုံးပြု၍ လုပ်ဆောင်နိုင်ပါသည်။

* အသိအမှတ်ပြုထားသည့် Vector format များအတွက် Context Menu မှ အောက်ဖော်ပြပါ လုပ်ငန်းများဆောင်ရွက်နိုင်ပါသည်-

  * :guilabel:`Delete File <dataset name>` ကိုအသုံးပြု၍ ဖိုင်များကို ပယ်ဖျက်ခြင်း၊
  * :menuselection:`Export Layer --> To file` ကိုအသုံးပြု၍ Layer များကို ထုတ်ယူခြင်း၊
  * :guilabel:`Add Layer to Project` ကိုအသုံးပြု၍ project အတွင်းသို့ ထည့်သွင်းအသုံးပြုခြင်း၊
  * :guilabel:`Layer Properties...` ကိုအသုံးပြု၍ Properties များကို ကြည့်ရှုစစ်ဆေးခြင်း၊

  အခြား format များအတွက် :guilabel:`Open <file type> Externally...` ကိုအသုံးပြု၍ လုပ်ဆောင်နိုင်ပါသည်။
   
   
.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |addLayer| image:: /static/common/mActionAddLayer.png
   :width: 1.5em
.. |afs| image:: /static/common/mIconAfs.png
   :width: 1.5em
.. |browserCollapse| image:: /static/common/browser_collapse.png
   :width: 1.5em
.. |browserExpand| image:: /static/common/browser_expand.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |collapseTree| image:: /static/common/mActionCollapseTree.png
   :width: 1.5em
.. |filterMap| image:: /static/common/mActionFilterMap.png
   :width: 1.5em
.. |geoPackage| image:: /static/common/mGeoPackage.png
   :width: 1.5em
.. |hana| image:: /static/common/mIconHana.png
   :width: 1.5em
.. |metadata| image:: /static/common/metadata.png
   :width: 1.5em
.. |mssql| image:: /static/common/mIconMssql.png
   :width: 1.5em
.. |options| image:: /static/common/mActionOptions.png
   :width: 1em
.. |oracle| image:: /static/common/mIconOracle.png
   :width: 1.5em
.. |postgis| image:: /static/common/mIconPostgis.png
   :width: 1.5em
.. |spatialite| image:: /static/common/mIconSpatialite.png
   :width: 1.5em
.. |unchecked| image:: /static/common/unchecked.png
   :width: 1.3em
.. |vectorTileLayer| image:: /static/common/mIconVectorTileLayer.png
   :width: 1.5em
.. |wcs| image:: /static/common/mIconWcs.png
   :width: 1.5em
.. |wfs| image:: /static/common/mIconWfs.png
   :width: 1.5em
.. |wms| image:: /static/common/mIconWms.png
   :width: 1.5em
.. |xyz| image:: /static/common/mIconXyz.png
   :width: 1.5em