.. index:: Attribute table
.. _sec_attribute_table:

************************************************************************
Working with the Attribute Table (အချက်အလက်ပြဇယား နှင့် အလုပ်လုပ်ခြင်း)
************************************************************************

Attribute (အချက်အလက်ပြ)ဇယား သည် ရွေးချယ်ထားသော Layer (အလွှာ)တစ်ခု၏ feature များဆိုင်ရာ အချက်အလက်များကို ပြသသည်။ ဇယားရှိ row တစ်ခုစီသည် feature တစ်ခု (ဂျီသြမေတြီနှင့် သို့မဟုတ် ဂျီသြမေတြီမပါဘဲ) ကိုကိုယ်စားပြုပြီး column တစ်ခုစီတွင် feature နှင့်ပတ်သက်သည့် အချက်အလက်အပိုင်းအစတစ်ခုစီပါရှိသည်။ ဇယားရှိ feature များကို ရှာဖွေခြင်း၊ ရွေးချယ်ခြင်း၊ ရွှေ့ခြင်း သို့မဟုတ် ပြုပြင်ခြင်းတို့ကို ပြုလုပ်နိုင်သည်။

.. only:: html

   .. contents::
      :local:

.. index:: Non Spatial Attribute Tables, Geometryless Data
.. _non_spatial_attribute_tables:

Foreword: Spatial and non-spatial tables (စကားချီး- Spatial (တည်နေရာနှင့်သက်ဆိုင်သော) နှင့် non-spatial (တည်နေရာနှင့်မသက်ဆိုင်သော) ဇယားများ)
=============================================================================================================================================

QGIS သည် spatial နှင့် non-spatial layer များကို ထည့်သွင်းနိုင်သည်။ ၄င်းတွင် လက်ရှိ GDAL က ထောက်ပံ့ပေးထားသည့် ဇယားများနှင့် PostgreSQL၊ MS SQL Server၊ SpatiaLite နှင့် Oracle providers (ထောက်ပံ့ပေးသူများ) အပြင် delimited text များ ပါဝင်ပါသည်။ ထည့်သွင်းထားသည့် layer များကို :guilabel:`Layers` (အလွှာများ) panel (ဘောင်ကွက်) တွင် စာရင်းပြုလုပ်ထားပါသည်။ Layer တစ်ခုသည် တည်နေရာနှင့်သက်ဆိုင်ခြင်း ရှိ/မရှိသည် မြေပုံပေါ်တွင် ၄င်းနှင့် အပြန်အလှန်လုပ်ဆောင်ခြင်း ရှိ/မရှိကို ဆုံးဖြတ်ပေးသည်။

Atrtibute ဇယား မြင်ကွင်း (view) ကို အသုံးပြု၍ non-spatial ဇယားများကို ရှာဖွေပြီး ပြုပြင်နိုင်သည်။ ထို့အပြင် ၄င်းတို့ကို field ရှာဖွေမှုများတွင် အသုံးပြုနိုင်သည်။ ဥပမာအားဖြင့်- attribute တန်ဖိုးများကို သတ်မှတ်ရန် non-spatial ဇယား၏ column များကို အသုံးပြုနိုင်သည် သို့မဟုတ် digitize (မြေပုံအချက်အလက်များ ရေးဆွဲခြင်း) လုပ်နေချိန်တွင် သတ်မှတ်ထားသည့် vector layer တစ်ခုသို့ ထည့်သွင်းထားသော တန်ဖိုးအပိုင်းအခြား တစ်ခုကို အသုံးပြုနိုင်သည်။
ပိုမိုသိရှိရန် :ref:`vector_attributes_menu` အခန်းတွင် edit (ပြုပြင်မွမ်းမံ) နိုင်သည့် widget (အထားအသိုပုံစံ) ကို ကြည့်ရှုပါ။

.. _attribute_table_overview:

Introducing the attribute table interface (Attribute ဇယားပုံစံသွင်ပြင်အား မိတ်ဆက်ခြင်း)
========================================================================================

Vector layer တစ်ခုအတွက် အချက်အလက်ဇယား ဖွင့်ရန်၊ :ref:`label_legend` ထဲတွင်ရှိသော layer ကို နှိပ်လိုက်ပြီးနောက် အဓိက :menuselection:`Layer`  menu မှ |openTable| :menuselection:`Open Attribute Table`ကို ရွေးချယ်ပြီး ဖွင့်နိုင်ပါသည်။ Layer ပေါ်တွင် right-click နှိပ်ပြီး drop-down (ရွေးချယ်ရန်) menu မှ |openTable| :menuselection:`Open Attribute Table`(အချက်အလက်ဇယားဖွင့်ခြင်း) ကို ရွေးပြီး၊ သို့မဟုတ် အချက်အလက် toolbar ထဲရှိ |openTable| :guilabel:`Open Attribute Table` (အချက်အလက်ဇယားဖွင့်ခြင်း) ခလုတ်ပေါ်တွင် နှိပ်၍လည်း ဖွင့်နိုင်ပါသည်။ Shortcut (အမြန်နည်းလမ်း) များအသုံးပြုလိုပါက ကီးဘုတ်ရှိ :kbd:`F6` ကို အသုံးပြုပြီး အချက်အလက်ဇယားကို ဖွင့်နိုင်ပါမည်။ :kbd:`Shift+F6`  ကို အသုံးပြုပါက ရွေးချယ်ထားသည့် feature များကို စစ်ထုတ်ထား (filter) သော အချယ်အလက်ဇယား ပွင့်လာမည်ဖြစ်ပြီး :kbd:`Ctrl+F6` ကို အသုံးပြုပါက မြင်ရနိုင်သော feature များကို စစ်ထုတ်ထား (filter) သော အချက်အလက်ဇယား ပွင့်လာမည်ဖြစ်သည်။

အဆိုပါနည်းလမ်းများအတိုင်းဆောင်ရွက်လျှင် layer အတွက် feature အချက်အလက်များကို ဖော်ပြသော window အသစ်တစ်ခု ပွင့်လာမည်ဖြစ်သည် (figure_attributes_table_)။ :menuselection:`Settings --> Options --> Data sources` menu တွင်ရှိသော setting အရ အချက်အလက်ဇယားသည် ချိတ်ဆက်ထားသည့် (docked) window တစ်ခု သို့မဟုတ်
ပုံမှန် (regular) window တစ်ခုထဲတွင် ပွင့်လာမည်ဖြစ်သည်။ Layer အတွင်းရှိ စုစုပေါင်း feature အရေအတွက်နှင့် လက်ရှိ ရွေးချယ်ထားသော/စစ်ထုတ်ထားသော feature အရေအတွက်သည် layer ကို တည်နေရာအရကန့်သတ်ထားလျှင်လည်း အချက်အလက်ဇယားခေါင်းစဉ်ထဲတွင် ပြသပေးမည်ဖြစ်သည်။


.. _figure_attributes_table:

.. figure:: img/vectorAttributeTable.png
   :align: center

   နေရာဒေသများ (Regions) layer အတွက် အချက်အလက်ဇယား

.. note:: Depending on the format of the data and the GDAL library built with
   your QGIS version, some tools may not be available.

အချက်အလက်ဇယား window ၏ ထိပ်ဆုံးတွင်ရှိသည့် ခလုတ်များသည် အောက်ပါလုပ်ဆောင်ချက်များကို ထောက်ပံ့ပေးထားပါသည်-

.. _table_attribute_1:

.. csv-table:: Available Tools
   :header: "Icon", "Label (အညွှန်း)", "Purpose (ရည်ရွယ်ချက်)", "Default Shortcut"
   :widths: auto
   :class: longtable

   "|toggleEditing|", "Toggle editing mode (ပြင်ဆင်ခြင်း mode အဖွင့်အပိတ်)", "လုပ်ဆောင်ချက်များကို ပြင်ဆင်ရန် ဆောင်ရွက်ခြင်း", ":kbd:`Ctrl+E`"
   "|multiEdit|", "Toggle multi edit mode (အများအပြားပြင်ဆင်ခြင်း mode အဖွင့်အပိတ်)", "Feature များ၏ field အများအပြားကို ပြင်ဆင်ခြင်း"
   "|saveEdits|", "Save Edits (ပြင်ဆင်ခြင်းများကိုသိမ်းဆည်းခြင်း)", "လက်ရှိပြုပြင်မွမ်းမံခြင်းများကို သိမ်းဆည်းခြင်း"
   "|refresh|", "Reload the table (ဇယားကို refresh လုပ်ခြင်း)"
   "|newTableRow|", "Add feature (feature ထည့်သွင်းခြင်း)", "ဂျီဩမေတြီဆိုင်ရာအချက်အလက်များမပါဝင်သော feature အသစ်ထည့်သွင်းခြင်း"
   "|deleteSelectedFeatures|", "Delete selected features (ရွေးချယ်ထားသည့် feature ကို ဖျက်ခြင်း)", "Layer မှ ရွေးချယ်ထားသော feature များကို ဖယ်ရှားခြင်း"
   "|editCut|", "Cut selected features to clipboard (ရွေးချယ်ထားသည့် feature များကို clipboard သို့ ရွေ့ခြင်း)", "", ":kbd:`Ctrl+X`"
   "|copySelected|", "Copy selected features to clipboard (ရွေးချယ်ထားသည့် feature များကို clipboard သို့  ကော်ပီကူးခြင်း)", "", ":kbd:`Ctrl+C`"
   "|editPaste|", "Paste features from clipboard (Clipboard မှ Paste လုပ်ခြင်း)", "ကူးထားသည်များမှ feature အသစ်များကို ထည့်သွင်းခြင်း", ":kbd:`Ctrl+V`"
   "|expressionSelect|", "Select features using an Expression (ခိုင်းစေချက်တစ်ခုကို အသုံးပြုပြီး feature များကိုရွေးချယ်ခြင်း"
   "|selectAll|", "Select All (အားလုံးကိုရွေးချယ်ခြင်း)", "Layer အတွင်းရှိ feature အားလုံးကို ရွေးချယ်ခြင်း", ":kbd:`Ctrl+A`"
   "|invertSelection|", "Invert selection (ပြောင်းပြန်ရွေးချယ်ခြင်း)", "Layer အတွင်း လက်ရှိရွေးချယ်ထားမှုများကို ပြောင်းပြန်ပြုလုပ်ခြင်း", ":kbd:`Ctrl+R`"
   "|deselectActiveLayer|", "Deselect all (အားလုံးကိုရွေးချယ်ထားခြင်းမှပယ်ဖျက်ခြင်း)", "လက်ရှိ layer အတွင်းရှိ feature အားလုံးကို ရွေးချယ်ထားခြင်းမှ ပယ်ဖျက်ခြင်း", ":kbd:`Ctrl+Shift+A`"
   "|filterMap|", "Filter/Select features using form (ပုံစံ (form) ကို အသုံးပြုပြီး feature များကို ရွေးချယ်ခြင်း/စစ်ထုတ်ခြင်း)", "", ":kbd:`Ctrl+F`"
   "|selectedToTop|", "Move selected to top (ရွေးချယ်ထားသည်ကို ထိပ်ဆုံးသို့ ရွေ့ခြင်း)", "ရွေးချယ်ထားသည့် အတန်း(row) များကို ဇယား၏ထိပ်ဆုံးသို့ ရွေ့ခြင်း"
   "|panToSelected|", "Pan map to the selected rows (ရွေးချယ်ထားသည့် row များဆီသို့ မြေပုံကိုရွေ့ခြင်း)", "", ":kbd:`Ctrl+P`"
   "|zoomToSelected|", "Zoom map to the selected rows (ရွေးချယ်ထားသည့် row များဆီသို့ မြေပုံကို မြင်ကွင်းချဲ့ခြင်း", "", ":kbd:`Ctrl+J`"
   "|newAttribute|", "New field (Field အသစ်)", "ဒေတာအရင်းမြစ်ထဲသို့ field အသစ်တစ်ခု ထည့်သွင်းခြင်း", ":kbd:`Ctrl+W`"
   "|deleteAttribute|", "Delete field (Field ကို ဖျက်ခြင်း)", "ဒေတာအရင်းမြစ်မှ field တစ်ခုကို ဖယ်ရှားခြင်း"
   "|editTable|", "Organize columns (ကော်လံများ (column)ကို စုစည်းခြင်း)", "အချက်အလက်ဇယား မှ field များကို ပြသခြင်း/ဖျောက်ထားခြင်း"
   "|calculateField|", "Open field calculator (Field calculator ဖွင့်ခြင်း)", "Row တစ်ခုထဲရှိ feature များအတွက် field ကို ပြုပြင်မွမ်းမံခြင်း", ":kbd:`Ctrl+I`"
   "|conditionalFormatting|", "Conditional formatting (အခြေအနေအရဖြစ်သော format ပြင်ဆင်ခြင်း)", "ဇယား format ပြင်ဆင်ခြင်းကို လုပ်ဆောင်စေခြင်း"
   "|dock|", "Dock attribute table (အချက်အလက်ဇယား ချိတ်တွဲခြင်း)", "အချက်အလက်ဇယားကို ချိတ်တွဲရန်/ဖြုတ်ရန် ခွင့်ပြုခြင်း"
   "|actionRun|", "Actions (လုပ်ဆောင်ချက်များ)", "Layer နှင့်ဆက်စပ်နေသည့် လုပ်ဆောင်ချက်များကို စာရင်းပြုစုခြင်း"


.. note:: ဒေတာ၏ ပုံစံ (format) နှင့် QGIS ဗားရှင်းတွင်ပါဝင်သော GDAL library အပေါ်မူတည်၍ အချို့ tool များသည် အသုံးပြု၍ ရနိုင်မည်မဟုတ်ပါ။

ဤခလုတ်များ၏အောက်တွင် Quick Field Calculation bar (field တွက်ချက်ခြင်း ကိုအမြန်ပြုလုပ်ခြင်း) ရှိပါသည်။ (:ref:`edit mode <sec_edit_existing_layer>` တွင်သာ လုပ်ဆောင်မည်ဖြစ်သည်။) ၎င်းသည် layer ထဲရှိ feature များအားလုံး သို့မဟုတ် feature အစိတ်အပိုင်းများ တွက်ချက်ခြင်းကို လျှင်မြန်စွာအသုံးချနိုင်ရန် ခွင့်ပြုပေးမည်ဖြစ်သည်။ ထို bar သည် |calculateField| :sup:`Field Calculator` (field တွက်ချက်ခြင်း) ကဲ့သို့ တူညီသည့် :ref:`expressions <vector_expressions>` ကို အသုံးပြုပါသည်။ (:ref:`calculate_fields_values` တွင် ကြည့်ရှုပါ။)


.. _attribute_table_view:

Table view vs Form view (Tabel ပုံစံမြင်ကွင်း နှင့် Form ပုံစံမြင်ကွင်း)
-------------------------------------------------------------------------

QGIS တွင် attribute ဇယားအတွင်းရှိ ဒေတာများကို လွယ်ကူစွာကိုင်တွယ်နိုင်ရန် မြင်ကွင်းပုံစံနှစ်ခု ထောက်ပံ့ပေးထားပါသည်-

* |openTable| :sup:`Table view` သည် Table ပုံစံမြင်ကွင်းတွင် feature အများအပြား၏ တန်ဖိုးများကို ဇယားပုံစံတစ်ခုထဲတွင် ဖော်ပြမည် ဖြစ်ပါသည်။ အတန်း (row) အသီးသီးသည် feature တစ်ခုကို ကိုယ်စားပြုပြီး၊ တိုင် (column) အသီးသီးသည် field တစ်ခုကို ကိုယ်စားပြုပါသည်။ Column ၏ခေါင်းစီးပေါ်တွင် right-click နှိပ်ခြင်းဖြင့် ():ref:`configure the table display <configure_table_columns>`) ဇယားပြသခြင်းကို ပြင်ဆင်သတ်မှတ်ရန် ခွင့်ပြုမည်ဖြစ်ပြီး၊ ဆဲလ် (cell) တစ်ခုပေါ်တွင် right-click နှိပ်ခြင်းဖြင့် (:ref:`interaction with the feature <interacting_features_table>`) feature နှင့် အပြန်အလှန်ဆောင်ရွက်ခြင်းကို ထောက်ပံ့ပေးမည်ဖြစ်သည်။

  Attribute ဇယားတွင် table မြင်ကွင်းပုံစံထဲရှိ ဒေါင်လိုက်နှင့် အလျားလိုက် scroll (mouse ၏ဘီးလုံးကို လှိမ့်ခြင်း) ပြုလုပ်သည့်ရွေ့လျားမှုများကို ပြောင်းလဲရန် :kbd:`Shift+Mouse Wheel` scroll ပြုလုပ်ခြင်းကို ခွင့်ပြုထားပါသည်။ ထိုသို့လုပ်ဆောင်ခြင်းကို MacOS ပေါ်ရှိ trackpad ကို mouse အစားထိုးအသုံးပြုခြင်းဖြင့် ဆောင်ရွက်နိုင်သည်။

* |formView| :sup:`Form view` Form ပုံစံမြင်ကွင်းသည် ပထမ panel တစ်ခုထဲတွင် :ref:`feature identifiers <maptips>` ကို ပြသမည်ဖြစ်ပြီး၊ ဒုတိယတစ်ခုထဲတွင် ကလစ်နှိပ်ထားသည့် identifier ၏ attribute များကိုသာ ဖော်ပြပေးမည်ဖြစ်သည်။ ပထမ panel ၏ ထိပ်ပိုင်းတွင် pull-down (အောက်သို့ဆွဲချသည့်) menu တစ်ခုရှိပါသည်။ ထိုနေရာတွင် identifier ကို attribute တစ်ခု (:guilabel:`Column preview`) သို့မဟုတ် :guilabel:`Expression` တစ်ခုကို အသုံးပြုပြီး သတ်မှတ်နိုင်ပါသည်။ ပြန်လည်အသုံးပြုရန်အတွက် pull-down တွင်နောက်ဆုံးအသုံးပြုခဲ့သော expression ၁၀ ခုလည်း ပါဝင်ပါသည်။ Form ပုံစံမြင်ကွင်းကို layer field များ ပြင်ဆင်သတ်မှတ်ရာတွင် အသုံးပြုပါသည်။ (:ref:`vector_attributes_menu` တွင်ကြည့်ရှုပါ။)

  ပထမ panel ၏ အောက်ခြေတွင်ရှိသော မြှားဖြင့် feature identifier များကို ကြည့်ရှုနိုင်ပါသည်။ မိမိ ဆောင်ရွက်သလို ဒုတိယ panel ထဲတွင် feature attribute များ အသစ်ပြုပြင်သွားမည် (update) ဖြစ်ပါသည်။ ၎င်းသည် အောက်ခြေတွင်ရှိသော ခလုတ်ကို ဆွဲချခြင်းဖြင့် မြေပုံ canvas ထဲရှိ active ဖြစ်သည့် feature ကို ခွဲခြားရန် သို့မဟုတ် ရွှေ့ရန် လုပ်ဆောင်နိုင်ပါသည်။

  * မြေပုံ canvas ထဲတွင် မြင်နိုင်လျှင် |highlightFeature| :sup:`Highlight current feature` (လက်ရှိ feature ကို ထင်ရှားအောင်ဖော်ပြခြင်း) ကိုအသုံးပြုနိုင်သည်။
  * |panTo| :sup:`Automatically pan to current feature` (လက်ရှိ feature သို့ အလိုအလျောက်ရောက်ရှိအောင် ရွှေ့ခြင်း)
  * |zoomTo| :sup:`Zoom to current feature` (လက်ရှိ feature သို့ မြင်ကွင်း ချုံ့/ချဲ့ ပြုလုပ်ခြင်း)

Dialog ၏ ညာဘက်အောက်ခြေတွင်ရှိသော သက်ဆိုင်သည့် icon ကို နှိပ်ခြင်းအားဖြင့် ပုံစံ (mode) တစ်ခုမှ အခြားတစ်ခုသို့ ပြောင်းလဲနိုင်သည်။။

Attribute ဇယားပွင့်လာလျှင်အသုံးပြုမည့် :guilabel:`Default view` (မူရင်းအမြင်) mode ကိုလည်း :menuselection:`Settings --> Options --> Data Sources` menu ထဲတွင်သတ်မှတ်နိုင်ပါသည်။
ထိုအရာသည် 'Remember last view (နောက်ဆုံးမြင်ကွင်းကိုမှတ်သားထားခြင်း)'၊ 'Table view (ဇယားပုံစံမြင်ကွင်း)' သို့မဟုတ် 'Form view (Form ပုံစံမြင်ကွင်း)' ဖြစ်နိုင်ပါသည်။

.. _figure_attribute_table_views:

.. figure:: img/attribute_table_views.png
   :align: center

   ဇယားပုံစံမြင်ကွင်း (အပေါ်) နှင့် Form ပုံစံမြင်ကွင်း (အောက်) ထဲရှိ attribute ဇယား


.. index:: Sort columns, Add actions
   pair: Attributes; Columns
.. _configure_table_columns:

Configuring the columns (Column များကို ပြင်ဆင်သတ်မှတ်ခြင်း)
-------------------------------------------------------------

အောက်ပါတို့ကို ထိန်းချုပ်နိုင်သည့် ကိရိယာများ (tools) ကို အသုံးပြုနိုင်စေရန် Table ပုံစံမြင်ကွင်းတွင် column တစ်ခု၏ခေါင်းစီးတွင် right-click နှိပ်ပါ-

* :ref:`column(s) size <resize_columns>` (column ၏ အရွယ်အစား)
* :ref:`column(s) visibility and order <organize_columns>` (column ၏ မြင်ရနိုင်မှု နှင့် အစီအစဉ်)
* :ref:`sort order of the data <sort_columns>` (ဒေတာ၏ အစီအစဉ်ကို ခွဲထားခြင်း)

.. _resize_columns:

Resizing columns widths (Column ၏အကျယ်ကို အရွယ်အစားပြန်လည်ပြင်ဆင်ခြင်း)
........................................................................

Column များ၏ အကျယ်ကို column ခေါင်းစီးပေါ်တွင် right-click နှိပ်ပြီး သတ်မှတ်နိုင်ပြီး၊ အောက်ပါတို့မှ တစ်ခုခုကို ရွေးချယ်ပါ-

* :guilabel:`Set width...` (အကျယ်ကို သတ်မှတ်ခြင်း) ဆန္ဒရှိသည့်တန်ဖိုးကို ထည့်သွင်းရန်။ Default အားဖြင့် လက်ရှိတန်ဖိုးကို widget ထဲတွင် ဖော်ပြနေမည် ဖြစ်သည်။
* :guilabel:`Set all column widths...` (Column အားလုံး၏ အကျယ်ကို သတ်မှတ်ခြင်း) Column အားလုံး၏အကျယ်ကို တူညီသည့်တန်ဖိုးများ သတ်မှတ်ရန်။
* :guilabel:`Autosize` (အရွယ်အစားကို အလိုအလျောက်ထားရှိခြင်း) Column ၏ အကျယ်ကို အကောင်းဆုံးကိုက်ညီသည့် အရွယ်အစားကို ပြန်လည်ပြင်ဆင်ရန်။
* :guilabel:`Autosize all columns` (Column အားလုံး၏ အရွယ်အစားကို အလိုအလျောက်ထားရှိခြင်း)

Column တစ်ခု၏အရွယ်အစားကို ၎င်း၏ခေါင်းစီး ညာဘက်အနားသတ်ဘောင်ကို ဆွဲချဲ့ခြင်းဖြင့်လည်း ပြောင်းလဲနိုင်ပါသည်။ Column အရွယ်အစားအသစ်ကို layer အတွက် ထိန်းသိမ်းထားမည် ဖြစ်ပြီး  attribute ဇယား ထပ်မံဖွင့်သောအခါ ၎င်းအတိုင်း ပြန်လည်အသုံးချပေးမည် ဖြစ်ပါသည်။

.. _organize_columns:

Hiding and organizing columns and enabling actions (Column များကို ဖျောက်ထားခြင်းနှင့် စုစည်းခြင်း၊ လုပ်ဆောင်ချက်များကို ဖြစ်ပေါ်စေခြင်း)
..........................................................................................................................................

Attribute ဇယား ("table view (ဇယားပုံစံမြင်ကွင်း)" တွင်)မှ Column ခေါင်းစီးတစ်ခုထဲတွင် right-click နှိပ်ခြင်းအားဖြင့် :guilabel:`Hide column` (Column ကို ဖျောက်ထားခြင်း) ကို ရွေးချယ်နိုင်ပါသည်။ ပိုမိုအဆင့်မြင့်သည့် ထိန်းချုပ်မှုများအတွက် dialog toolbar မှ |editTable| :sup:`Organize columns...` (Column များကို စုစည်းခြင်း...) ခလုတ်ကို နှိပ်ပါ သို့မဟုတ် Contextual menu (attribute table ၏ မူလ menu) ထဲရှိ :guilabel:`Organize columns...` (Column များကို စုစည်းခြင်း...) ကို ရွေးပါ။ Dialog အသစ်ထဲတွင် အောက်ပါတို့ကို ဆောင်ရွက်နိုင်သည်-

* ဖော်ပြလိုခြင်း သို့မဟုတ် ဖျောက်ထားလိုသည့် column များကို အမှန်ခြစ်ထည့်ခြင်း/ဖြုတ်ခြင်း- ဖျောက်ထားသော column တစ်ခုသည် ၎င်းကို ပြန်လည် restore မလုပ်ခင်အချိန်ထိ attribute ဇယား dialog ၏ ဖြစ်စဉ်တိုင်းတွင် ကွယ်ပျောက်နေမည် ဖြစ်ပါသည်။
* Attribute ဇယားထဲတွင် column များကို ပြန်လည်အစီစဉ်ချရန် drag and drop ပြုလုပ်နိုင်သည် (drag-and-drop items)။ မှတ်သားထားရန်မှာ ထိုသို့ပြောင်းလဲမှုသည် ဇယားဖော်ပြမှုအတွက်ဖြစ်ပြီး၊ layer ဒေတာအရင်းမြစ်ထဲရှိ field အစီစဉ်ချထားမှုများ ပြောင်းလဲမည် မဟုတ်ပါ။
* Virtual :guilabel:`Actions`(လုပ်ဆောင်ချက်) column အသစ်တစ်ခုကို ထည့်သွင်းနိုင်သည်။ ထိုအရာသည် row အသီးသီးတွင် drop-down box သို့မဟုတ် လုပ်ဆောင်နိုင်သည့် action များ စာရင်းခလုတ် (button list) တစ်ခုစီ ဖော်ပြပေးမည်ဖြစ်သည်။ Action များနှင့်ပတ်သက်သည့် အချက်အလက်များပိုမိုသိရှိလိုပါက :ref:`actions_menu` တွင်ကြည့်ပါ။

.. _sort_columns:

Sorting columns (Column များကို အမျိုးအစားအလိုက်ခွဲခြားခြင်း)
..............................................................

ဇယားကို column ခေါင်းစီးပေါ်တွင် နှိပ်ခြင်းအားဖြင့် sort လုပ်နိုင်ပါသည်။ သေးငယ်သည့် မြှားတစ်ခုသည် sort order (အစီစဉ်ချထားခြင်း) ကို ညွှန်ပြပါသည်။ (မြှားသည် အောက်ဘက်သို့ ဦးတည်နေခြင်းမှာထိပ်ဆုံးအတန်းမှအောက်သို့ တန်ဖိုးများ ကြီးစဉ်ငယ်လိုက် စဉ်ထားခြင်းကို ဆိုလိုပြီး၊ မြှားသည် အပေါ်ဘက်သို့ ဦးတည်နေခြင်းမှာ ထိပ်ဆုံးအတန်းမှအောက်သို့ တန်ဖိုးများ ငယ်စဉ်ကြီးလိုက် စဉ်ထားခြင်းကို ဆိုလိုပါသည်။)
Row များကို sort လုပ်ရန် column ခေါင်းစီးနှင့်ဆက်စပ်သည့် menu ရှိ :guilabel:`Sort...` (ခွဲခြားခြင်း) option ကိုအသုံးပြုခြင်း နှင့် expression တစ်ခု ရေးသားခြင်း ကို ရွေးချယ်နိုင်သည်။ ဥပမာ- column အများအပြားကို အသုံးပြုပြီး rows များကို sort လုပ်ရန် ``concat(col0, col1)`` expression ကို ရေးသားနိုင်ပါသည်။

Form ပုံစံမြင်ကွင်းတွင် feature identifier ကို |sort| :guilabel:`Sort by preview expression` (အစမ်းကြည့်ရှုသည့် expression ဖြင့် ခွဲခြားခြင်း) option ကို အသုံးပြုပြီး sort ပြုလုပ်နိုင်ပါသည်။

.. _tip_sortcolumns:

.. tip:: **Column ပုံစံအမျိုးမျိုးအပေါ်အခြေခံ၍ ခွဲခြားခြင်း (Sorting based on columns of different types)**

  စာသား (string) နှင့် ဂဏန်း (numeric) အမျိုးအစား၏ column ပေါ် အခြေခံပြီး attribute ဇယားတစ်ခုကို sort (ခွဲခြား) ပြုလုပ်ရန် ကြိုးစားခြင်းသည် မျှော်လင့်မထားသောရလဒ်များကို ဖြစ်ပေါ်စေနိုင်ပါသည်။ အဘယ့်ကြောင့်ဆိုသော် ``concat("USE", "ID")`` expression တစ်ခုသည် စာသားတန်ဖိုးများ (string values) ကို ထုတ်ပေးမှာ ဖြစ်ပါသည် (ဆိုလိုသည်မှာ ``'Borough105' < 'Borough6'``)။ ဥပမာ- ``concat("USE", lpad("ID", 3, 0))`` expression ကို အသုံးပြုခြင်းဖြင့် ရလာဒ်သည် ``'Borough105' > 'Borough006'`` ကို ထုတ်ပေးမည်ဖြစ်ပြီး ပြဿနာကို ဖြေရှင်းနိုင်ပါသည်။


.. index:: Conditional formatting
.. _conditional_formatting:

Formatting of table cells using conditions (အခြေအနေများကို အသုံးပြုပြီး ဇယားရှိ cells များကို ပုံစံချခြင်း)
------------------------------------------------------------------------------------------------------------

Conditional formatting setting (အခြေအနေအလိုက် ပုံစံချခြင်း အပြင်အဆင်) များကို attribute ဇယားထဲရှိ သီးခြားအာရုံစိုက်လိုသော feature များကို အသားပေးဖော်ပြရန် အသုံးပြုနိုင်ပါသည်။ အောက်ပါ feature များ၏အချက်အလက်များပေါ်တွင် စိတ်ကြိုက် condition များအသုံးပြုခြင်းဖြင့် ဆောင်ရွက်နိုင်သည်-

* ဂျီဩမေတြီ (ဥပမာ၊ feature များ၏ တစ်ခုထက်ပိုသော အစိတ်အပိုင်းများကို ခွဲခြားသတ်မှတ်ခြင်း၊ သေးငယ်သော ဧရိယာတစ်ခု သို့မဟုတ် သတ်မှတ်ထားသော မြေပုံအတိုင်းအတာထဲရှိ....)
* သို့မဟုတ်  field တန်ဖိုး (ဥပမာ၊ သတ်မှတ်ထားသည့်အဆင့်တစ်ခုထိ တန်ဖိုးများကို နှိုင်းယှဉ်ခြင်း၊ cell အလွတ်များကို ခွဲခြားသတ်မှတ်ခြင်း)

Table ပုံစံမြင်ကွင်း (Form ပုံစံမြင်ကွင်းတွင် အသုံးပြု၍မရပါ) ထဲရှိ attribute window ၏ အပေါ်ညာဘက်တွင်ရှိသော |conditionalFormatting| ကို နှိပ်ခြင်းဖြင့် 
အခြေအနေအလိုက် ပုံစံချခြင်း (conditional formatting) panel ကို စတင်လုပ်ဆောင်နိုင်ပါသည်။

Panel အသစ်တွင် |radioButtonOn|:guilabel:`Field` သို့မဟုတ် |radioButtonOff|:guilabel:`Full row` တို့၏ ပုံဖော်ပြသခြင်းကို ပုံစံချရန်အတွက် စည်းမျဉ်းအသစ်ထည့်သွင်းနိုင်မည်ဖြစ်သည်။ စည်းမျဉ်းအသစ်ထည့်သွင်းခြင်းသည် အောက်ပါတို့ကို သတ်မှတ်ရန် form တစ်ခုကို ပွင့်စေပါသည်-

* စည်းမျဉ်း၏အမည်၊
* :ref:`expression builder <vector_expressions>` လုပ်ဆောင်ချက် (function) များ၏ တစ်ခုခုကို အသုံးပြုခြင်း အခြေအနေတစ်ခု၊
* ပုံစံချမှတ်ခြင်း- ၄င်းသည် ကြိုတင်ချမှတ်ထားသော ပုံစံများ သို့မဟုတ် အောက်ပါ properties ပေါ်တွင် အခြေခံပြီး ဖန်တီးထားသော ပုံစံများ စာရင်းတစ်ခုမှ ရွေးချယ်ခြင်း ခံရနိုင်သည်-

  * နောက်ခံမြင်ကွင်းနှင့်စာသား အရောင်များ၊
  * icon အသုံးပြုမှု၊
  * bold (စာလုံးထင်းခြင်း) ၊ italic (စာလုံးစောင်းခြင်း)၊ underline (စာသားအောက်မျဉ်းသားခြင်း)၊ သို့မဟုတ် strikeout (စာသားကိုဖြတ်၍ မျဉ်းသားခြင်း)၊
  * ဖောင့်

.. _figure_conditional_format:

.. figure:: img/attribute_table_conditional_formating.png
   :align: center

   Attribute ဇယားတစ်ခု၏ အခြေအနေအလိုက် ပုံစံချခြင်း (Conditional formatting)

.. index::
   pair: Attributes; Selection
.. _interacting_features_table:

Interacting with features in an attribute table (အချက်အလက်ဇယားတစ်ခုရှိ feature များနှင့် အပြန်အလှန်လုပ်ဆောင်ခြင်း)
===================================================================================================================

Selecting features (Feature များရွေးချယ်ခြင်း)
-----------------------------------------------

ဇယားပုံစံမြင်ကွင်းတွင်၊ attribute ဇယား၏ row တစ်ခုချင်းစီသည် layer တွင်ရှိသော သီးသန့် feature တစ်ခု၏ 
အချက်အလက်များကို ဖော်ပြသည်။ Row တစ်ခုအားရွေးချယ်ခြင်းသည် feature ကိုရွေးချယ်ခြင်းဖြစ်ပြီး အလားတူပင်
မြေပုံ canvas ရှိ feature တစ်ခု (ဂျီသြမေတြီပါရှိသည့် layer အတွက်) ကို ရွေးချယ်ခြင်းသည် အချက်အလက်ဇယားရှိ row တစ်ခုကို ရွေးချယ်ခြင်းဖြစ်သည်။ မြေပုံ canvas မှ (သို့မဟုတ် အချက်အလက်ဇယားမှဖြစ်စေ) ရွေးချယ်ထားသည့် feature များကို ပြောင်းလဲမှုပြုလုပ်ပါက ထိုရွေးချယ်ထားသည့် feature များကို အချက်အလက်ဇယား (သို့မဟုတ် မြေပုံ canvas) တွင်လည်း ကိုက်ညီမှုရှိအောင် ပြုပြင်ပြောင်းလဲမည် ဖြစ်သည်။

Row ၏ ဘယ်ဘက်အခြမ်းရှိ row နံပါတ်များကို နှိပ်၍ row များကို ရွေးချယ်နိုင်ပါသည်။ ကွန်ပျူတာရှိ :kbd:`Ctrl` key ကို ဖိထား၍ **row များစွာ** ကို အမှတ်အသားပြုရွေးချယ်နိုင်သည်။ ကွန်ပျူတာရှိ :kbd:`Shift` key ကို ဖိထား၍ row များ၏ ဘယ်ဘက်အခြမ်းရှိ row ခေါင်းစဉ်များစွာကို နှိပ်ခြင်းဖြင့် **တစ်ဆက်တည်းရွေးချယ်မှု** ကို ပြုလုပ်နိုင်သည်။ လက်ရှိ cursor (ကွန်ပျူတာဖန်သားပြင်ရှိ ညွှန်းမြှား) ရှိရာနေရာနှင့် click နှိပ်ထားသော row အကြားရှိ row အားလုံးကို ရွေးချယ်မည်ဖြစ်သည်။ ဇယားရှိ cell (ဆဲအကွက်) တစ်ခုကို နှိပ်ခြင်းဖြင့် cursor အနေအထားကို ရွှေ့ပြောင်းခြင်းသည် row ရွေးချယ်ထားမှုကို ပြောင်းလဲမည်မဟုတ်ပါ။ အဓိက မြေပုံ canvas ရှိ ရွေးချယ်ထားမှုကို ပြောင်းလဲခြင်းသည် attibute ဇယားရှိ cursor အနေအထားကို ရွေ့ပြောင်းစေမည်မဟုတ်ပါ။

Attribute ဇယား၏ form မြင်ကွင်းတွင်၊ feature များသည် ၎င်းတို့၏ ပြသထားသော field တန်ဖိုးအလိုက် left panel တွင် default အနေဖြင့် ခွဲခြားဖော်ပြမည်ဖြစ်သည်။ (:ref:`maptips` (မြေပုံအကြံပြုချက်များ) တွင် ကြည့်ပါ။ ဤခွဲခြားဖော်ပြသည့်အရာ (identifier) ကို panel ၏ အပေါ်ဘက်ရှိ drop-down စာရင်းကို အသုံးပြု၍၊ ရှိပြီးသား field ကို ရွေးချယ်၍သော်လည်းကောင်း စိတ်ကြိုက် ခိုင်းစေချက် (expression) တစ်ခုကို အသုံးပြု၍လည်းကောင်း ရွေးချယ်၍ အစားထိုးပြောင်းလဲနိုင်သည်။ Drop-down menu မှ feature များစာရင်းကို sort ပြုလုပ်ထားရန်လည်း ရွေးချယ်နိုင်သည်။

Feature ၏ အချက်အလက်များကို ညာဘက်တွင်ပြသရန် ဘယ်ဘက် panel ရှိ တန်ဖိုးတစ်ခုကို နှိပ်ပါ။ Feature တစ်ခုကို ရွေးချယ်ရန် identifier ၏ ဘယ်ဘက်ရှိ စတုရန်းသင်္ကေတအတွင်းတွင် နှိပ်ရန် လိုအပ်သည်။ ပုံမှန်အားဖြင့် သင်္ကေတသည် အဝါရောင်သို့ ပြောင်းလဲသွားပါသည်။ ဇယားပုံစံမြင်ကွင်းတွင် မြင်တွေ့ရသကဲ့သို့ပင် ယခင်က ဖော်ပြခဲ့သော
ကွန်ပျူတာကီးဘုတ် (keyboard) ကို ပေါင်းစပ်အသုံးပြု၍ feature ရွေးချယ်မှုများစွာကို လုပ်ဆောင်နိုင်သည်။

.. actually, it looks like there's a difference in keyboard usage but i feel
   it's a bug. Report at https://issues.qgis.org/issues/16553.

Feature များကို ကွန်ပျူတာ မောက်စ် (mouse) ဖြင့် ရွေးချယ်ခြင်းအပြင် အလိုအလျောက်ရွေးချယ်ခြင်းကို attribute ဇယား toolbar ရှိ အောက်ဖော်ပြပါ tool များကိုအသုံးပြု၍ feature ၏ အချက်အလက်အပေါ် အခြေခံ၍ လုပ်ဆောင်နိုင်ပါသည် (:ref:`automatic_selection` ကဏ္ဍတွင် ကြည့်ရှုပြီး နောက်ထပ်အချက်အလက်များနှင့် အသုံးချကိစ္စရပ်များအတွက် အောက်ဖော်ပြပါတို့ကို ကြည့်ရှုပါ)-

* |expressionSelect| :guilabel:`Select By Expression...` (ခိုင်းစေချက်အားဖြင့် ရွေးချယ်ခြင်း)
* |formSelect| :guilabel:`Select Features By Value...` (တန်ဖိုးအားဖြင့် feature များ ရွေးချယ်ခြင်း)
* |deselectActiveLayer| :guilabel:`Deselect All Features from the Layer` (Layer မှ feature အားလုံးကို ရွေးချယ်မှုမှ ပယ်ဖျက်ခြင်း)
* |selectAll| :guilabel:`Select All Features` (Feature အားလုံးကို ရွေးချယ်ခြင်း)
* |invertSelection| :guilabel:`Invert Feature Selection` (Feature ရွေးချယ်မှုကို ပြောင်းပြန်လှန်ခြင်း)

:ref:`filter_select_form` ကိုအသုံးပြု၍ feature များကို ‌‌ရွေးချယ်နိုင်ပါသည်။

.. _filter_features:

Filtering features (Feature များကို စစ်ထုတ်ခြင်း)
--------------------------------------------------

Attribute ဇယားရှိ feature များကို ရွေးချယ်ပြီးသည်နှင့် ဇယားတွင် ၎င်းတို့ကိုသာ ပြသနိုင်သည်။ Attribute ဇယား dialog ၏ ဘယ်ဘက်အောက်ခြေရှိ drop-down စာရင်းမှ :guilabel:`Show Selected Features` (ရွေးချယ်ထားသော feature များကို ပြသခြင်း) ကို အသုံးပြု၍ အလွယ်တကူ လုပ်ဆောင်နိုင်သည်။ ထိုစာရင်းသည် အောက်ပါ စစ်ထုတ်မှုများကို လုပ်ဆောင်ပေးသည်-

* |openTable| :guilabel:`Show All Features` (Feature များအားလုံးကို ပြသပါ)
* |openTableSelected| :guilabel:`Show Selected Features` (ရွေးချယ်ထားသော feature များကို ပြသခြင်း) သည် :guilabel:`Layer` ရွေးချယ်စရာစာရင်းမှ :guilabel:`Open Attribute Table (Selected Features)` (Attribute ဇယားကို ဖွင့်ပါ (ရွေးချယ်ထားသော Feature များ)) ကို အသုံးပြုခြင်း သို့မဟုတ် :guilabel:`Attributes Toolbar` (အချက်အလက်ဇယား toolbar) ကို အသုံးပြုခြင်း သို့မဟုတ် :kbd:`Shift+F6` (ကွန်ပျူတာကီးဘုတ်ရှိ Shift ခလုတ်နှင့် F6 ခလုတ်ကို တွဲ၍နှိပ်ခြင်း) ကို အသုံးပြုခြင်းနှင့် အတူတူပင်ဖြစ်သည်။ 
* |openTableVisible| :guilabel:`Show Features visible on map` (မြေပုံတွင် ပြသနိုင်သော feature များကို ပြသခြင်း) သည် :guilabel:`Layer` ရွေးချယ်စရာစာရင်းမှ :guilabel:`Open Attribute Table (Visible Features)` (Attribute ဇယားကို ဖွင့်ပါ (မြင်ရသော feature များ)) ကို အသုံးပြုခြင်း သိုမဟုတ် :guilabel:`Attributes Toolbar` (အချက်အလက်ဇယား toolbar) ကို အသုံးပြုခြင်း သို့မဟုတ် :kbd:`Ctrl+F6` (ကွန်ပျူတာကီးဘုတ်ရှိ Ctrl ခလုတ်နှင့် F6 ခလုတ်ကို တွဲ၍နှိပ်ခြင်း) ကို အသုံးပြုခြင်းနှင့် အတူတူပင်ဖြစ်သည်။
* |openTableInvalid| :guilabel:`Show Features with Failing Constraints` (ကန့်သတ်ချက်မအောင်မြင်သော feature များကို ပြသခြင်း) သည် :ref:`constraints <constraints>` (ကန့်သတ်ချက်များ) မအောင်မြင်သော feature များကိုသာ စစ်ထုတ်ပြသမည်ဖြစ်သည်။ မအောင်မြင်သော ကန့်သတ်ချက် အနည်း သို့မဟုတ် အများအပေါ်မူတည်၍ မအောင်မြင်သည့် field တန်ဖိုးများကို လိမ္မော်ရောင် အဖျော့ သို့မဟုတ် အရင့်ဖြင့် အသီးသီး ဖော်ပြသည်။
* |openTableEdited| :guilabel:`Show Edited and New Features` (တည်းဖြတ်ပြီး feature များနှင့် feature အသစ်များ ကို ပြသခြင်း) သည် :guilabel:`Layer` ရွေးချယ်စရာစာရင်းမှ သို့မဟုတ် :guilabel:`Attributes Toolbar` (အချက်အလက်ဇယား toolbar) မှ :guilabel:`Open Attribute Table (Edited and New Features)` (Attribute ဇယားကို ဖွင့်ပါ(တည်းဖြတ်ပြီး feature များနှင့် feature အသစ်များ)) ကို အသုံးပြုခြင်းနှင့် အတူတူပင် ဖြစ်သည်။
* :guilabel:`Field Filter` (Field ကို စစ်ထုတ်ခြင်း) သည် Field (Attribute ဇယား၏ column) တစ်ခုရှိ တန်ဖိုးအပေါ် အခြေခံ၍ စစ်ထုတ်ခြင်းဖြစ်သည်။ စစ်ထုတ်ခြင်း ဆောင်ရွက်ရန် attribute ဇယားရှိ column တစ်ခုကို ရွေးချယ်ပါ၊ တန်ဖိုးတစ်ခုကို ရိုက်ထည့် သို့မဟုတ် ရွေးချယ်ပြီး :kbd:`Enter` (ကွန်ပျူတာကီးဘုတ်မှ Enter ခလုတ်) ကို နှိပ်ပါ။ ထို့နောက် ``num_field = value`` သို့မဟုတ် ``string_field ilike '%value%'`` expression များနှင့် ကိုက်ညီသော feature များကိုသာ attribute ဇယားတွင် ဖော်ပြမည် ဖြစ်သည်။ String များနှင့်ပတ်သက်၍ ခွင့်ပြုမှုနည်းပါးစေရန် |checkbox| :guilabel:`Case sensitive` (စာလုံးအကြီးအသေးသတိထားခြင်း) ကို အမှန်ခြစ်ထားနိုင်ပါသည်။
* |filterMap| :guilabel:`Advanced filter (Expression)` (အဆင့်မြင့် စစ်ထုတ်ခြင်း (ခိုင်းစေချက်)) - Expression တည်ဆောက်ပေးသည့် dialog ကို ဖွင့်စေပါသည်။ ၎င်းအတွင်း၌ ဇယားရှိ row များနှင့် ကိုက်ညီစေရန် :ref:`complex expressions (ခက်ခဲရှုပ်ထွေးသော expression များ) <vector_expressions>` ကို ဖန်တီးနိုင်သည်။ ဥပမာအားဖြင့်- Field တစ်ခုထက်ပို၍ အသုံးပြုပြီး ဇယားကို စစ်ထုတ်နိုင်သည်။ အသုံးပြုရာတွင် စစ်ထုတ်မည့် expression ကို ပုံစံ (form) ၏ အောက်ခြေတွင် ပြသမည် ဖြစ်သည်။
* |handleStoreFilterExpressionChecked| :menuselection:`Stored filter expressions -->` - (သိမ်းဆည်းထားသော စစ်ထုတ်မှု expression များ) သည် attribute ဇယားကို စစ်ထုတ်ရန် မကြာခဏအသုံးပြုလေ့ရှိသည့် :ref:`saved expressions (သိမ်းဆည်းထားသော expression များ) <store_filter>` သို့ ရောက်မည့် ဖြတ်လမ်း တစ်ခုဖြစ်သည်။
  
:ref:`filter features using forms (ပုံစံများအသုံးပြု၍ feature များကို စစ်ထုတ်ခြင်း) <filter_select_form>` ကိုလည်း ဆောင်ရွက်နိုင်သည်။

.. note::

  Attribute ဇယားမှ မှတ်တမ်းများကို စစ်ထုတ်ခြင်းသည် feature များကို layer ၏အပြင်ဘက်သို့ စစ်ထုတ်ခြင်း မဟုတ်ပါ။ ၎င်း မှတ်တမ်းများကို ဇယားမှ ယာယီ ကွယ်ဝှက်ထားပြီး မြေပုံ canvas မှ ဝင်ရောက်ကြည့်ရှုနိုင်သည် သို့မဟုတ် 
  စစ်ထုတ်ခြင်းကို ဖယ်ရှားခြင်းဖြင့် ပြန်လည်ရယူနိုင်မည်ဖြစ်သည်။ Layer မှ feature များကို ဖျောက်ထားနိုင်သော စစ်ထုတ်ခြင်းများအတွက် :ref:`Query Builder (Query Builder) <vector_query_builder>` ကို အသုံးပြုပါ။

.. tip:: **``Show Features Visible on Map`` ဖြင့် မူလ Data အရင်းအမြစ် စစ်ထုတ်ခြင်းအား update လုပ်ပါ**

  စွမ်းဆောင်ရည်ပိုင်းဆိုင်ရာ အကြောင်းပြချက်များကြောင့် attribute ဇယားတွင် ပြသထားသည့် feature များအား စဖွင့်ရာတွင် မြေပုံ canvas extent (အကျယ်အဝန်း) ဖြင့် တည်နေရာအရ ကန့်သတ်ထားပါသည်။ (မည်သို့ဆောင်ရွက်ရမည်ကို :ref:`Data Source Options (ဒေတာအရင်းအမြစ်ရွေးချယ်မှုများ) <tip_table_filtering>` တွင်ကြည့်ပါ။) :guilabel:`Show Features Visible on Map` (မြေပုံတွင် မြင်ရသော feature များကို ပြသခြင်း) ကို မြေပုံ canvas extent (အကျယ်အဝန်း) အသစ်တွင် ရွေးချယ်ခြင်းသည် တည်နေရာအရကန့်သတ်ချက်ကို ပြင်ဆင်နိုင်ပါသည်။


.. index:: Expression filter
.. _store_filter:

Storing filter expressions (စစ်ထုတ်မှု expression များကို သိမ်းဆည်းခြင်း)
--------------------------------------------------------------------------

Attribute ဇယားကို စစ်ထုတ်ခြင်းအတွက် အသုံးပြုသည့် expression များကို နောက်ထပ်ခေါ်ဆိုမှုများအတွက် သိမ်းဆည်းထားနိုင်ပါသည်။ :guilabel:`Field Filter` (Attribute ဇယား၏ column မှ စစ်ထုတ်ခြင်း) သို့မဟုတ် :guilabel:`Advanced Filter (expression)` (အဆင့်မြင့် စစ်ထုတ်ခြင်း (expression)) - ထည့်သွင်းမှုများ၊ အသုံးပြုထားသော expression ကို attribute ဇယား dialog အောက်ခြေရှိ စာသားအထားအသိုနေရာပုံစံတစ်ခုတွင် ပြသထားသည်။
Project ထဲတွင် expression ကိုသိမ်းဆည်းရန် box ၏ဘေးရှိ |handleStoreFilterExpressionUnchecked| :sup:`Save expression with text as name` (expression အား စာသားဖြင့် အမည်အတိုင်း သိမ်းဆည်းခြင်း) ကိုနှိပ်ပါ။ ခလုတ်ဘေးရှိ Drop-down ရွေးချယ်စရာစာရင်းကို နှိပ်၍ ဖော်ပြချက်ကို စိတ်ကြိုက်အမည်တစ်ခု (:guilabel:`Save expression as...`) ဖြင့် သိမ်းဆည်းနိုင်သည်။ သိမ်းဆည်းထားသော expression ကို ပြသပြီးသည်နှင့် |handleStoreFilterExpressionChecked| ခလုတ်ကို ပွင့်သွားမည်ဖြစ်ပြီး ၎င်း၏ drop-down ရွေးချယ်စရာစာရင်းမှ :guilabel:`Edit the expression` (expression ကို တည်းဖြတ်ခြင်း) နှင့် အမည်တစ်ခုပေးခြင်း၊ သို့မဟုတ် :guilabel:`Delete stored expression` (သိမ်းဆည်းထားပြီး expression ကို ပယ်ဖျက်ခြင်း) တို့ကို လုပ်ဆောင်နိုင်သည်။

သိမ်းဆည်းထားသော စစ်ထုတ်မှု expression များကို ပရောဂျက်တွင် သိမ်းဆည်းထားပြီး attribute ဇယား၏ :guilabel:`Stored filter expressions` (သိမ်းဆည်းထားသော စစ်ထုတ်မှု expression များ) menu မှတဆင့် ရယူနိုင်သည်။ ၎င်းတို့သည် :ref:`user expressions (အသုံးပြုသူ expression များ) <user_expressions_functions>` နှင့် ကွဲပြားပြီး အသုံးပြုသူပရိုဖိုင်၏ 
ပရောဂျက်အားလုံးမှ မျှဝေထားပါသည်။

.. _filter_select_form:

Filtering and selecting features using forms (Form (ပုံစံ) များကို အသုံးပြုပြီး feature များကို စစ်ထုတ်ခြင်းနှင့် ရွေးခြယ်ခြင်း)
---------------------------------------------------------------------------------------------------------------------------------

|filterMap| :sup:`Filter/Select features using form` (ပုံစံကို အသုံးပြု၍ featureများကို စစ်ထုတ်/ရွေးချယ်ခြင်း) နှိပ်ခြင်း သို့မဟုတ် :kbd:`Ctrl+F` ကို နှိပ်ခြင်းသည် attribute ဇယား dialog ကို form view အဖြစ်ပြောင်းစေပြီး ၎င်း၏ ရှာဖွေမှုကွဲလွဲချက်ဖြင့် (search variant) widget (အထားအသိုပုံစံ) တစ်ခုစီကို အစားထိုးပါမည်။

ဤအချက်မှစတင်၍ ဤကိရိယာ၏လုပ်ဆောင်နိုင်စွမ်းသည် :ref:`select_by_value` (တန်ဖိုးအရရွေးချယ်ခြင်း) တွင် ဖော်ပြထားသည့် အရာနှင့်ဆင်တူပြီး operator အားလုံးနှင့် ရွေးချယ်ခြင်း mode (နည်းလမ်း) များ၏ ဖော်ပြချက်အားလုံးကို တွေ့နိုင်ပါသည်။

.. _figure_filter_select_form:

.. figure:: img/tableFilteredForm.png
    :align: center

    Filter form (စစ်ထုတ်ခြင်း ပုံစံ) ဖြင့် attribute ဇယားများကို စစ်ထုတ်ခြင်း

Attribute ဇယား မှ feature များကို စစ်ထုတ်ခြင်းများ/ရွေးချယ်ခြင်းများ ပြုလုပ်သည့်အချိန်တွင် :guilabel:`Filter features` (feature များကို စစ်ထုတ်ခြင်း) ခလုတ်သည် စစ်ထုတ်မှုများကို ခွဲခြားသတ်မှတ်ခြင်းနှင့် သန့်စင်မှုများကို ပြုလုပ်ပေးသည်။ ၄င်းကို အသုံးပြုမှုသည် :guilabel:`Advanced filter (Expression)` (အဆင့်မြင့် စစ်ထုတ်မှု (Expression)) option ကို စတင်နိုင်ပြီး form ၏ အောက်ခြေရှိ ပြုပြင်နိုင်သော 
စာသား widget တွင် သက်ဆိုင်ရာ စစ်ထုတ်ခြင်း expression များကို ပြသပေးသည်။


Feature များကို စစ်ထုတ်ပြီးလျှင် :guilabel:`Filter features` (Feature များကို စစ်ထုတ်ခြင်း) ခလုတ်ဘေးရှိ drop-down စာရင်းကို အသုံးပြု၍ စစ်ထုတ်မှုများကို သန့်စင်နိုင်သည်။ ရွေးချယ်စရာများမှာ-

* :guilabel:`Filter within ("AND")` (အထဲမှ စစ်ထုတ်ခြင်း ("AND"))
* :guilabel:`Extend filter ("OR")` (စစ်ထုတ်မှုကို တိုးချဲ့ခြင်း ("OR"))

စစ်ထုတ်မှုများကို ရှင်းလင်းရန်အတွက် အောက်ခြေဘယ်ဘက် pull-down menu (ဆွဲချထားသော စာရင်း) မှ :guilabel:`Show all features` (feature များအားလုံးကို ပြသခြင်း) option ကို ရွေးချယ်ပါ သို့မဟုတ် expression ကိုရှင်းပြီး :guilabel:`Apply` ကို နှိပ်ပါ သို့မဟုတ် :kbd:`Enter` ကိုနှိပ်ပါ။

Using action on features (Feature များပေါ်တွင် action (လုပ်ဆောင်ချက်) များ အသုံးပြုခြင်း)
==========================================================================================

အသုံးပြုသူများသည် contextual menu (ဆက်စပ်ရွေးချယ်စရာစာရင်း) ဖြင့် feature များကို ကိုင်တွယ်ဆောင်ရွက်နိုင်ပါသည်-

* Feature များအားလုံးကို ရွေးချယ်ခြင်း :guilabel:`Select all` (:kbd:`Ctrl+A`)၊
* :guilabel:`Copy cell content` (cell အကြောင်းအရာကို ကူးယူပါ) ဖြင့် clipboard ထဲတွင် cell တစ်ခု၏ content (အကြောင်းအရာ) ကို copy ပြုလုပ်ခြင်း၊
* ကြိုရွေးစရာမလိုဘဲ feature များကို မြင်ကွင်းချဲ့ခြင်း :guilabel:`Zoom to feature`၊
* ကြိုရွေးစရာမလိုဘဲ feature များနေရာသို့ ရွေ့ခြင်း :guilabel:`Pan to feature`၊
* :guilabel:`Flash feature` (feature များကို သိသာအောင်ပြသခြင်း)- Map canvas ထဲတွင် feature များကို highlight (သိသာထင်ရှားအောင်) ပြုလုပ်ရန်၊
* :guilabel:`Open form` ( form ကို ဖွင့်ပါ) - ၄င်းသည် နှိပ်ထားသည့် feature ပေါ်တွင် focus (အာရုံစိုက်ခြင်း) လုပ်ထားပြီး attribute ဇယား မှ form view သို့ ပြောင်းပေးသည်။

.. _figure_copy_cell:

.. figure:: img/copyCellContent.png
    :align: center

    Cell Content ကို copy လုပ်ခြင်း

ပြင်ပ program (အစီအစဥ်) များတွင် attribute ဒေတာ ကို အသုံးပြုလိုလျှင် (Excel၊
LibreOffice၊ QGIS သို့မဟုတ် custom (စိတ်ကြိုက်) web application တစ်ခု)၊ row တစ်ခု သို့မဟုတ် row များကို ရွေးချယ်ပြီး |copySelected| :sup:`Copy selected rows to clipboard`('ရွေးချယ်ထားသော row များကို ကလစ်ဘုတ်သို့ကူးယူပါ') ခလုတ်ကို အသုံးပြုပါ သို့မဟုတ်
:kbd:`Ctrl+C` ကို နှိပ်ပါ။

.. _geometry_format:

:menuselection:`Settings --> Options --> Data Sources` menu တွင် 
:guilabel:`Copy features as` drop-down စာရင်းဖြင့် paste လုပ်မည့် format ကို သတ်မှတ်နိုင်သည်-

* Plain text (ရိုးရိုးစာသား)၊ geometry မရှိခြင်း၊
* Plain text (ရိုးရိုးစာသား)၊ WKT geometry၊
* GeoJSON

ဤ contextual menu တွင် action များစာရင်းတစ်ခုကို ပြသနိုင်သည်။ ၄င်းကို
:menuselection:`Layer properties --> Actions` tab တွင် ဖွင့်နိုင်သည်။
action များနှင့်ပတ်သက်သည့် အချက်အလက်များအတွက် :ref:`actions_menu` တွင် ကြည့်ရှုပါ။

Saving selected features as new layer (ရွေးချယ်ထားသည့် feature များကို layer အသစ်အနေဖြင့် သိမ်းဆည်းခြင်း)
----------------------------------------------------------------------------------------------------------

ရွေးချယ်ထားသည့် feature များကို OGR ထောက်ပံ့ပေးသည့် vector format တစ်ခုခုဖြင့် သိမ်းဆည်းနိုင်ပြီး တခြား CRS ကိုလည်း ပြောင်းလဲနိုင်သည်။ ရလာဒ် dataset ၏ နာမည်၊ format နှင့် CRS ကို သတ်မှတ်ရန် :guilabel:`Layers` panel မှ layer ၏ contextual menu ရှိ :menuselection:`Export --> Save selected features as...` ကို နှိပ်ပါ (:ref:`general_saveas` အခန်းကိုကြည့်ပါ)။ |checkbox| :menuselection:`Save only selected features` (ရွေးချယ်ထားသည့် feature များကိုသာ သိမ်းဆည်းခြင်း) ကို အမှန်ခြစ်ထားသည်ကို သတိပြုမိပါလိမ့်မည်။ Dialog အတွင်း GDAL ဖန်တီးမှုရွေးချယ်စရာများကို သတ်မှတ်ရန်လည်း လုပ်ဆောင်နိုင်သည်။

.. index:: Field Calculator, Derived Fields, Virtual Fields, Fields edit
.. _calculate_fields_values:

Editing attribute values (အချက်အလက်တန်ဖိုးများကို ပြင်ဆင်တည်းဖြတ်ခြင်း)
========================================================================

အချက်အလက်တန်ဖိုးများ (attribute values) ပြင်ဆင်တည်းဖြတ်ခြင်းကို အောက်ဖော်ပြပါတို့ဖြင့် လုပ်ဆောင်နိုင်ပါသည်-

* အချက်အလက်ဇယား (attribute table) သည် ဇယားပုံစံ (table view) တွင်ဖြစ်စေ သို့မဟုတ် ပုံစံမြင်ကွင်း (form view) တွင်ဖြစ်စေ တန်ဖိုးအသစ်ကို ဆဲလ် (cell)အတွင်း တိုက်ရိုက် ရိုက်ထည့်ခြင်း။ ထို့ကြောင့် အပြောင်းအလဲများကို cell တစ်ခုစီအလိုက် (cell by cell) ၊ feature တစ်ခုစီအလိုက် (feature by feature) ပြုလုပ်သည်။
* :ref:`field calculator <vector_field_calculator>` ကို အသုံးပြု၍ row တစ်ခုတွင်ရှိသော feature များစွာ (multiple features) အတွက် ရှိပြီးသား field တစ်ခု သို့မဟုတ် ဖန်တီးမည့် field တစ်ခုကို update လုပ်နိုင်သည်။ ၎င်းကို virtual field များ ဖန်တီးရန် အသုံးပြုနိုင်သည်။
* Quick field :ref:`calculation bar <quick_field_calculation_bar>` အသုံးပြုခြင်းသည် အထက်ဖော်ပြပါ field calculator နှင့်အသုံးပြုပုံချင်း တူညီသော်လည်း  ရှိပြီးသား field များ အတွက်သာ အသုံးပြုနိုင်သည်။
* သို့မဟုတ် :ref:`multi edit <multi_edit_fields>` mode ကို အသုံးပြု၍ feature များစွာ (multiple features) အတွက် field များစွာကို Row တစ်ခုတွင် update လုပ်နိုင်ပါသည်။


.. _vector_field_calculator:

Using the Field Calculator (Field Calculator ကို အသုံးပြုခြင်း)
----------------------------------------------------------------

အချက်အလက်ဇယား (attribute table) မှ |calculateField| :sup:`Field Calculator` ခလုတ်သည် ရှိပြီးသား အချက်အလက်တန်ဖိုးများ (attribute values) သို့မဟုတ် သတ်မှတ်ထားသော လုပ်ဆောင်ချက်များကို အခြေခံ၍ တွက်ချက်မှုများကို လုပ်ဆောင်နိုင်သည်။ ဥပမာအားဖြင့် ဂျီသြမေတြီ featureများ (geometry features) ၏ အလျား (length) သို့မဟုတ် ဧရိယာ (area) ကို တွက်ချက်နိုင်သည်။ တွက်ချက်၍ ရရှိလာသော ရလာဒ်များကို ရှိပြီးသား field တစ်ခုကို update လုပ်ရန် သို့မဟုတ် field အသစ်တစ်ခုတွင် ရေးသွင်းခြင်း လုပ်ဆောင်နိုင်ပါသည် (၎င်းသည် :ref:`virtual <virtual_field>` တစ်ခု ဖြစ်နိုင်သည်)။

Field calculator သည် ပြင်ဆင်တည်းဖြတ်ခြင်းလုပ်နိုင်သည့် မည်သည့် layer တွင်မဆို ရနိုင်ပါသည်။ Field calculator icon ကို နှိပ်လိုက်သောအခါ dialog တစ်ခုပွင့်လာမည် (:numref:`figure_field_calculator` တွင် ကြည့်ပါ)။ Layer သည် တည်းဖြတ်မှု (edit) mode တွင် ရှိမနေပါက သတိပေးချက်တစ်ခု ပြသမည်ဖြစ်ပြီး Field calculator ကို အသုံးပြုခြင်းသည် တွက်ချက်မှုမပြုလုပ်မီ edit mode တွင် layer ကို ထားရှိမည်ဖြစ်သည်။

:ref:`Expression Builder <functions_list>` dialog ကို အခြေခံ၍ Field calculator dialog သည် expression တစ်ခုကို သတ်မှတ်ရန် ပြီးပြည့်စုံသော interface တစ်ခု ပံ့ပိုးပေးပြီး ထို interface ကို ရှိပြီးသား field တစ်ခု သို့မဟုတ် အသစ်ဖန်တီးထားသော field တစ်ခုတွင် အသုံးချနိုင်ပါသည်။ Field calculator dialog ကို အသုံးပြုရန် ပြုလုပ်လိုသည့်အရာကို ရွေးချယ်ရပါမည်-

#. Layer တစ်ခုလုံးတွင် တွက်ချက်မှု ပြုလုပ်ခြင်း သို့မဟုတ် ရွေးချယ်ထားသော feature များပေါ်တွင်သာ တွက်ချက်မှု ပြုလုပ်ခြင်း။
#. တွက်ချက်မှုအတွက် field အသစ်တစ်ခု ဖန်တီးခြင်း သို့မဟုတ် ရှိပြီးသား field ကို update လုပ်ခြင်း။

.. _figure_field_calculator:

.. figure:: img/fieldcalculator.png
   :align: center

   Field Calculator

Field အသစ် တစ်ခုကို ထည့်လိုပါက field အမည်တစ်ခု၊ field အမျိုးအစားတစ်ခု (ကိန်းပြည့်၊ ကိန်းစစ်၊ ရက်စွဲ သို့မဟုတ် စာကြောင်း) ထည့်သွင်းရန် လိုအပ်ပြီး စုစုပေါင်း field length (အရှည်) နှင့် field precision (တိကျမှု) တို့ကို ထည့်သွင်းရပါမည်။ ဥပမာအားဖြင့် field length ကို ၁၀ နှင့် field precision ကို ၃ ကို ရွေးချယ်လိုပါက ဒဿမကိန်း အရှေ့တွင် ဂဏန်း ၇ လုံးရှိပြီး ဒဿမကိန်း အနောက်တွင် ဂဏန်း ၃ လုံးရှိသည်ဟု ဆိုလိုသည်။

ဥပမာအနေဖြင့် :guilabel:`Expression` tab ကို အသုံးပြုသောအခါ field calculator တွင် မည်သို့ လုပ်ဆောင်သည်ကို ဖော်ပြထားပါသည်။ QGIS နမူနာဒေတာအတွဲ (sample dataset) မှ ``railroads`` layer ၏ ကီလိုမီတာအလျားကို တွက်ချက်လိုသောအခါ-

#. QGIS တွင် shapefile :file:`railroads.shp` ကိုထည့်သွင်းပြီး |openTable|:sup:`Open Attribute Table` ကို နှိပ်ပါ။
#. |toggleEditing| :sup:`Toggle editing mode` ကို နှိပ်၍ |calculateField| :sup:`Field Calculator` dialog ကိုဖွင့်ပါ။
#. |checkbox| :guilabel:`Create a new field` checkbox ကို ရွေးချယ်၍ တွက်ချက်မှုများကို field အသစ်တွင် သိမ်းဆည်းရန် အမှန်ခြစ်ပေးပါ။
#. :guilabel:`Output field name` ကို ``length_km`` အဖြစ်သတ်မှတ်ပါ။
#. ``Decimal number (real)`` ကို :guilabel:`Output field type` အဖြစ် ရွေးချယ်ပါ။
#. :guilabel:`Output field length` ကို ``10`` နှင့် :guilabel:`Precision` ကို  ``3`` ဟုသတ်မှတ်ပါ။
#. Field calculator expression box တွင် ဂျီသြမေတြီ၏ အရှည်ကို ထည့်ရန် :guilabel:`Geometry` အုပ်စုရှိ ``$length`` ကို နှစ်ချက်နှိပ်ပါ (ရလာဒ်ကို အစမ်းကြည့်ရှုမှုတွင် စာလုံး ၆၀ အထိ မြင်တွေ့နိုင်ပြီး expression box ကို အချိန်နှင့်တပြေးညီ update လုပ်နေသည်)။
#. Expression ကို အပြီးသတ်ရန် Field calculator expression box တွင် ``/ 1000`` ကို ရိုက်ထည့်၍ :guilabel:`OK` ကို နှိပ်ပါ။
#. အချက်အလက်ဇယား (attribute table) ထဲတွင် :guilabel:`length_km` field အသစ်ကို တွေ့နိုင်မည်ဖြစ်သည်။

.. _virtual_field:

Creating a Virtual Field (Virtual Field တစ်ခု ဖန်တီးခြင်း)
-----------------------------------------------------------

Virtual Field သည် လုပ်ဆောင်နေစဉ် (on the fly) တွက်ချက်ပေးသော expression တစ်ခုအပေါ် အခြေခံထားသည့် field တစ်ခုဖြစ်ပြီး နောက်ခံသတ်မှတ်ချက် (parameter) တစ်ခုပြောင်းလဲပြီးသည်နှင့် ၎င်း၏တန်ဖိုးကို အလိုအလျောက် update လုပ်ပေးမည်ဖြစ်သည်။ အဆိုပါ ခိုင်းစေချက် (expression) ကိုတစ်ကြိမ်သတ်မှတ်ပြီးသည်နှင့် မူလအရင်းခံတန်ဖိုးများ ပြောင်းလဲသည့်အခါတိုင်း field ကို ပြန်လည်တွက်ချက်ရန် မလိုအပ်တော့ပါ။ ဥပမာအားဖြင့် digitize (မြေပုံအချက်အလက်ရေးဆွဲခြင်း) ပြုလုပ်ထားသော feature များ၏ဧရိယာကို လိုအပ်ပါက သို့မဟုတ် ပြောင်းလဲနိုင်သည့် ရက်စွဲများအကြား ကြာမြင့်သည့် ကာလကို အလိုအလျောက် တွက်ချက်ရန် (ဥပမာ ``now()``  လုပ်ဆောင်ချက်ကို အသုံးပြုခြင်း) virtual field တစ်ခုကို အသုံးပြုပါသည်။

.. note:: **Virtual Field များအသုံးပြုမှု**

   * Virtual Fields များသည် layer အချက်အလက်များ (Layer attributes) တွင် အမြဲတမ်း တည်ရှိမနေသောကြောင့် ၎င်းတို့ကို သိမ်းဆည်းခြင်းသာ ပြုလုပ်နိုင်ပြီး ၎င်းတို့ကိုဖန်တီးထားသော ပရောဂျက်ဖိုင်တွင်သာ ရရှိနိုင်သည်။
   * Field တစ်ခုကို ၎င်း၏ဖန်တီးမှုတွင်သာ virtual အဖြစ် သတ်မှတ်နိုင်သည်။ Virtual field များကို ပုံမှန်ရုပ်ပိုင်းဆိုင်ရာ သို့မဟုတ် ချိတ်ဆက်ထားသော field များမှ ခွဲခြားသိရှိနိုင်ရန် layer ဂုဏ်သတ္တိများ dialog ၏ field tab အတွင်း ခရမ်းရောင်နောက်ခံဖြင့် အမှတ်အသားပြုလုပ်နိုင်ပါသည်။ မှတ်ချက် column (comment column) ရှိ expression ခလုတ်ကို နှိပ်ခြင်းဖြင့် ၎င်းတို့၏ expression များကို နောက်ပိုင်းတွင် ပြင်ဆင်တည်းဖြတ်နိုင်ပါသည်။ Virtual field ၏ expression များကို ချိန်ညှိရန် expression များကို ပြင်ဆင်တည်းဖြတ်သည့် window (expression editor window) ပွင့်လာမည်ဖြစ်သည်။

.. _quick_field_calculation_bar:

Using the Quick Field Calculation Bar (Quick Field Calculation Bar ကို အသုံးပြုခြင်း)
--------------------------------------------------------------------------------------

Field calculator သည် အမြဲတမ်းရရှိနိုင်သော်လည်း layer သည် edit mode တွင်ရှိနေမှသာ အချက်အလက်ဇယား (attribute table) ၏ထိပ်ရှိ  (quick field calculation bar) ကိုမြင်နိုင်သည်။ Expression engine ကြောင့် ရှိပြီးသား field ကို တည်းဖြတ်ရန် ပိုမိုမြန်ဆန်စွာ ဝင်ရောက်ခွင့်ပေးပါသည်-

#. Drop-down list တွင် update လုပ်ရန် field ကို ရွေးပါ။
#. Expression တစ်ခုကို တိုက်ရိုက်ရေးသားခြင်း သို့မဟုတ် |expression| expression ခလုတ်ကို အသုံးပြု၍ expression တစ်ခုကို တည်ဆောက်ခြင်းဖြင့် textbox တွင်တန်ဖိုးတစ်ခု ဖြည့်ပါ။
#. :guilabel:`Update All` (အားလုံးကို update လုပ်မည်)၊ :guilabel:`Update Selected` (ရွေးချယ်ထားသည်များကို update လုပ်မည်) သို့မဟုတ် :guilabel:`Update Filtered` (စစ်ထုတ်ထားသည်များကို update လုပ်မည်) စသည့် ခလုတ်များကို လိုအပ်သည့်အတိုင်း ရွေးချယ်၍နှိပ်ပါ။

.. _figure_field_calculator_bar:

.. figure:: img/fieldcalculatorbar.png
   :align: center

   Quick Field Calculation Bar

.. index:: Multi edit
.. _multi_edit_fields:

Editing multiple fields (Field များစွာကို ပြင်ဆင်တည်းဖြတ်ခြင်း)
----------------------------------------------------------------

ယခင် tool များနှင့်မတူဘဲ မျိုးစုံတည်းဖြတ် mode (multi edit mode) သည် မတူကွဲပြားခြားနားသော feature များ၏ များစွာသောအချက်အလက်များ (multiple attributes) များကို တစ်ပြိုင်နက် တည်းဖြတ်နိုင်ပါသည်။ Layer ကို တည်းဖြတ်ရန် အဖွင့်အပိတ်လုပ်သောအခါ များစွာတည်းဖြတ်မှု (multi edit) စွမ်းရည်များကို ရရှိနိုင်သည်-

* အချက်အလက်ဇယား dialog (attribute table dialog) အတွင်းရှိ toolbar မှ  |multiEdit| :sup:`Toggle multi edit mode` ကို အသုံးပြုခြင်း။
* သို့မဟုတ် :menuselection:`Edit -->` |multiEdit| :menuselection:`Modify attributes of selected features` ကို ရွေးချယ်ခြင်း။

.. note:: အချက်အလက်ဇယား (attribute table) မှ tool နှင့်မတူဘဲ :menuselection:`Edit --> Modify Attributes of Selected Features` ရွေးချယ်မှု (option) သည် အချက်အလက်ပြောင်းလဲမှုများကို ဖြည့်စွက်ရန် modal dialog တစ်ခု ပေးပါသည်။ ထို့ကြောင့် လုပ်ဆောင်မှုမပြုမီ feature ရွေးချယ်မှု လိုအပ်ပါသည်။

Row တစ်ခုထဲတွင် field များစွာ (multiple fields) ကို ပြင်ဆင်တည်းဖြတ်ရန်-

#. ပြင်ဆင်တည်းဖြတ်လိုသော feature များကို ရွေးပါ။
#. အချက်အလက်ဇယား (attribute table) toolbar မှ |multiEdit| ကိုနှိပ်ပါ။ ၎င်းသည် dialog ကို ၎င်း၏ form မြင်ကွင်း (form view) သို့ ပြောင်းပေးမည်ဖြစ်သည်။ ဤအဆင့်တွင် feature ရွေးချယ်မှုကိုလည်း ပြုလုပ်နိုင်သည်။
#. အချက်အလက်ဇယား (attribute table) ၏ ညာဘက်တွင် ရွေးထားသည့် feature များ၏ field များ (နှင့် တန်ဖိုးများ)ကို ပြသထားပါသည်။ လက်ရှိ multi edit အခြေအနေအား ပြသရန် field တစ်ခုစီ၏ဘေးတွင် widget အသစ်များ ပေါ်လာမည်ဖြစ်သည်-

   * |multiEditMixedValues| Field တွင် ရွေးချယ်ထားသော feature များအတွက် မတူညီသော တန်ဖိုးများ ပါရှိသည်။ ၎င်းကို ဗလာကျင်းပြသထားပြီး feature တစ်ခုစီသည် ၎င်း၏ မူရင်းတန်ဖိုးကို ထိန်းသိမ်းထားမည်ဖြစ်သည်။ Widget ၏ drop-down list မှ field ၏တန်ဖိုးကို reset (မူလအတိုင်းပြန်သတ်မှတ်) ပြုလုပ်နိုင်သည်။
   * |multiEditSameValues| ရွေးချယ်ထားသော feature အားလုံးသည် ထို field အတွက် တူညီသောတန်ဖိုးများရှိကြပြီး ပုံစံ (form) တွင်ပြသထားသည့်တန်ဖိုးကို သိမ်းဆည်းထားမည်ဖြစ်သည်။
   * |multiEditChangedValues| Field ကို တည်းဖြတ်ပြီးသည်နှင့် ထည့်သွင်းထားသောတန်ဖိုးကို ရွေးချယ်ထားသည့် feature အားလုံးတွင် သက်ရောက်မည်ဖြစ်သည်။ Dialog ၏ထိပ်တွင် ပြုပြင်မွမ်းမံမှုကို အသုံးချရန် သို့မဟုတ် ပြန်လည်သတ်မှတ်ရန် ဖော်ပြသည့် မက်ဆေ့ချ်တစ်ခု ပေါ်လာမည်ဖြစ်သည်။

ဤ widget များထဲမှ တစ်ခုခုကို နှိပ်ခြင်းဖြင့် field အတွက် လက်ရှိတန်ဖိုးကို သတ်မှတ်ရန် သို့မဟုတ် မူရင်းတန်ဖိုးသို့ ပြန်လည်သတ်မှတ်နိုင်သည်။ ဆိုလိုသည်မှာ ပြောင်းလဲမှုများကို field အလိုက် ပြန်လည်လုပ်ဆောင်စေနိုင်ပါသည်။


   .. _figure_field_multiedit:

   .. figure:: img/attribute_multiedit.png
      :align: center

      များစွာသော feature များ၏ field များကိုတည်းဖြတ်ခြင်း

#. အလိုရှိသော field များကို အပြောင်းအလဲ ပြုလုပ်ပါ။
#. အပေါ်မက်ဆေ့ခ်ျစာသား သို့မဟုတ် ဘယ်ဘက်အကွက် (left panel) ရှိ အခြား feature များတွင် **Apply changes** ကိုနှိပ်ပါ။

ပြောင်းလဲမှုများသည် **ရွေးချယ်ထားသော feature များအားလုံး** တွင် သက်ရောက်မှုရှိပါမည်။ Feature ကို ရွေးချယ်ထားခြင်းမရှိပါက ပြောင်းလဲမှုများကို ဇယားတစ်ခုလုံးတွင် update လုပ်ပါမည်။ ပြုပြင်မွမ်းမံမှုများကို တစ်ခုတည်းသော တည်းဖြတ်သည့် ခိုင်းစေချက် (single edit command) အဖြစ် ပြုလုပ်သည်။ |undo| :sup:`Undo` သည် ရွေးချယ်ထားသော feature အားလုံးအတွက် ပြောင်းလဲမှုမလုပ်မီ အခြေအနေသို့ ပြန်လည်ရောက်ရှိစေမည်ဖြစ်သည်။

.. note::

  Multi edit mode ကို အလိုအလျောက်ထုတ်ပေးပြီး ဆွဲထည့်ပေးသည့်ပုံစံများ (drag and drop forms) အတွက်သာ ရနိုင်သည် (:ref:`customize_form` ကိုကြည့်ပါ)။ ၎င်းကို custom ui form (စိတ်ကြိုက်ပြင်ဆင်ထားသော User interface ပုံစံ) များဖြင့် အသုံးမပြုနိုင်ပါ။


.. index:: Relations, Foreign key
.. _vector_relations:

Creating one or many to many relations (တစ်ခုမှ အများ သို့မဟုတ် အများမှ အများ ဆက်သွယ်ချက်များကို ဖန်တီးခြင်း)
==============================================================================================================

ဆက်သွယ်ချက် (Relations) များသည် database တွင် အသုံးများသော နည်းပညာတစ်ခုဖြစ်သည်။ အယူအဆမှာ မတူညီသော layer များ (ဇယားများ)၏ feature များ (row များ) သည် တစ်ခုနှင့်တစ်ခု သက်ဆိုင်သည်ဟု ယူဆပါသည်။ 

.. _one_to_many_relation:

Introducing 1-N relations (1-N ဆက်သွယ်ချက်များကို မိတ်ဆက်ခြင်း)
----------------------------------------------------------------

ဥပမာအနေဖြင့် အချို့သော attribute များ၏အမည်၊ ဒေသအမျိုးအစား (region type) နှင့် သီးသန့်အိုင်ဒီ (unique id) (primary key အဖြစ် လုပ်ဆောင်သည့်) ရှိသော ဒေသအားလုံး၏ alaska (polygon)ဖြင့် layerတစ်ခု ကိုပေးထားသည်။

ထို့နောက် ဒေသများတွင်ရှိသော လေဆိပ်များအကြောင်း အချက်အလက်ပါသည့် အခြားအမှတ် (point) layer သို့မဟုတ် ဇယားကို ရရှိပြီး ၎င်းတို့ကိုလည်း ခြေရာခံနိုင်ပါသည်။ ၎င်းတို့ကို ဒေသ layer တွင် ထည့်သွင်းလိုပါက၊ ဒေသအများစုတွင် လေဆိပ်များစွာရှိသောကြောင့် foreign (ပြင်ပ) key များကို အသုံးပြု၍ တစ်ခုနှင့်အများ ဆက်စပ်မှုတစ်ခုကို ဖန်တီးရန် လိုအပ်ပါသည်။

.. _figure_relations_map:

.. figure:: img/relations1.png
   :align: center

   လေဆိပ်များ ပါဝင်သော Alaska ဒေသ 

Layers in 1-N relations (1-N ဆက်သွယ်ချက်များရှိ layer များ)
............................................................

QGIS တွင် ဇယားတစ်ခုနှင့် vector layer အကြား ကွာခြားချက်မရှိပါ။ အခြေခံအားဖြင့်၊ vector layerသည် ဂျီသြမေတြီပါသော ဇယားတစ်ခုဖြစ်သည်။ ထို့ကြောင့် ဇယားကို vector layer အဖြစ် ထည့်သွင်းနိုင်သည်။ 1-N ဆက်သွယ်ချက်ကို သရုပ်ပြရန် foreign key field (``fk_region``) ပါဝင်သော :file:`regions`(‌ဒေသများ) shapefile နှင့် :file:`airports` (လေဆိပ်) shapefile ကို ဒေသ layer များအတွင်းသို့ ထည့်သွင်းပါ။ ဆိုလိုသည်မှာ ဒေသတစ်ခုချင်းစီတွင် လေဆိပ်များစွာ (တစ်ခုနှင့် အများ ဆက်သွယ်ချက်) ရှိနိုင်သော်လည်း လေဆိပ်တစ်ခုချင်းစီသည် ဒေသတစ်ခုစီနှင့်သာသက်ဆိုင်သည်။

Foreign keys in 1-N relations (1-N ဆက်သွယ်ချက်များရှိ Foreign key များ)
........................................................................

လေယာဥ်ကွင်းများပါဝင်သော attribute ဇယားထဲရှိ ရှိပြီးသား attribute များအပြင် foreign key ကဲ့သို့ ဆောင်ရွက်သော ``fk_region`` field လိုအပ်ပါသည်။ (Database တစ်ခုရှိပါက ကန့်သတ်ချက်ကို သတ်မှတ်နိုင်ပါသည်။)

၎င်း fk_region field တွင် ဒေသတစ်ခု၏ id တစ်ခု အမြဲပါဝင်ပါမည်။ ၎င်းသည် သက်ဆိုင်ရာဒေသကို ညွှန်ပြသည့်အရာကဲ့သို့ဖြစ်သည်။ ထို့နောက် ပြင်ဆင်ခြင်းအတွက် စိတ်ကြိုက် ဒီဇိုင်းဆွဲနိုင်ပြီး QGIS သည် ဆက်လက်လုပ်ဆောင်သွားပါမည်။ ၎င်းသည် မတူညီသော provider များနှင့် ဆောင်ရွက်နိုင်သည်။ (ထို့ကြောင့် ၎င်းကို shapefile နှင့် csv ဖိုင်များဖြင့်လည်း သုံးနိုင်သည်။) ထိုသို့ဆောင်ရွက်ရန် ဇယားများကြားရှိဆက်သွယ်ချက်များကို QGIS သို့ ထည့်သွင်းရန်သာ လိုအပ်ပါသည်။

Defining 1-N relations (1-N ဆက်သွယ်ချက်ကို သတ်မှတ်ခြင်း)
.........................................................

Layer များကြားရှိ ဆက်သွယ်ချက်ကို QGIS ထဲ ထည့်သွင်းရန် ပထမဆုံးလုပ်ဆောင်ရပါမည်။ ၄င်းကို :menuselection:`Project --> Properties...` ထဲတွင်လုပ်ဆောင်နိုင်ပါသည်။ :guilabel:`Relations` tab ကိုဖွင့်ပြီး |symbologyAdd| :guilabel:`Add Relation` (ဆက်သွယ်ချက် ထည့်သွင်းခြင်း) ကိုနှိပ်ပါ။

* **Name (အမည်)** ကို ခေါင်းစဥ်အဖြစ် အသုံးပြုသည်။ ၎င်းသည် ဖတ်နိုင်သော စာကြောင်းဖြစ်သင့်ပြီး ၎င်းသည် ဆက်သွယ်ချက်ကို မည့်သည့်အတွက် အသုံးပြုကြောင်းကို ဖော်ပြသင့်သည်။ ဤကိစ္စတွင် **လေယာဥ်ကွင်း ဆက်သွယ်ချက်** ဟုသာခေါ်ဆိုပါမည်။
* **Referenced (ကိုးကားခံ) layer (ပင်မ)** သည် ပင်မ (parent) layer အဖြစ် ယူဆထားသည်။ Primary key တစ်ခုဖြစ်သောကြောင့် ဤနေရာတွင် ``regions (ဒေသများ)`` layer ဖြစ်သည်။ ကိုးကားခံသည့် layer ၏ primary key ကို သတ်မှတ်ရန်လိုအပ်သည်။ ထို့ကြောင့် ၎င်းသည် ``ID`` ဖြစ်သည်။
* **Referenced (ကိုးကားခံ) layer (အပွား)** ကိုလည်း အပွား (child) layer အဖြစ် မှတ်ယူသည်။ ၄င်းပေါ်တွင် foreign key field ပါရှိသည်။ ဤအခြေအနေတွင် ၄င်းသည် ``airports (လေဆိပ်များ)`` layer ဖြစ်သည်။ ဤ layer အတွက် အခြား layer သို့ညွှန်ပြသည့် ကိုးကားချက်ရယူသည့် field ကို ပေါင်းထည့်ရန်လိုအပ်သည်။ ထို့ကြောင့် ၎င်းသည် ``fk_region`` ဖြစ်သည်။

  .. note:: တစ်ခါတစ်ရံတွင် layer တစ်ခုရှိ feature များကို သီးခြားခွဲခြားသတ်မှတ်ရန် field တစ်ခုထက်ပို၍ လိုအပ်သည်။ ထိုသို့သော layer တစ်ခုနှင့် ဆက်သွယ်ချက်တစ်ခုဖန်တီးရန် **ပေါင်းစပ်ထားသော (composite) key** လိုအပ်သည်။ ၄င်းသည် ကိုက်ညီသော field အတွဲတစ်ခုထက် ပိုပါသည်။ ကိုအသုံးပြုပါ။ များစွာသော အတွဲများလိုအပ်သလိုထည့်ရန် |symbologyAdd| :sup:`Add new field pair as part of a composite foreign key` (ပေါင်းစပ်ထားသော foreign key အစိတ်အပိုင်းအဖြစ် field အသစ်တွဲကို ပေါင်းထည့်ခြင်း) ခလုတ် ကိုနှိပ်ပါ။

* **Id** ကို အတွင်းပိုင်း ရည်ရွယ်ချက်များအတွက် အသုံးပြုမည်ဖြစ်ပြီး သီးသန့်ဖြစ်ရပါမည်။ ၄င်းကို :ref:`custom forms <customize_form>` ပြုလုပ်ရန် လိုအပ်နိုင်ပါသည်။ ၎င်းကို ကွက်လပ်အနေဖြင့် ထားခဲ့ပါက တစ်ခုကို ထုတ်ပေးမည်ဖြစ်သော်လည်း ကိုင်တွယ်ရပိုမိုလွယ်ကူစေရန် ကိုယ်တိုင် သတ်မှတ်ပေးနိုင်ပါသည်။

* **Relationship strength (ဆက်သွယ်ချက် ခိုင်မာမှုအား)** သည် parent နှင့် child layer ကြား ဆက်သွယ်ချက်၏ ခိုင်မာမှုကို သတ်မှတ်သည်။ ပုံသေ :guilabel:`Association` (အဖွဲ့) အမျိုးအစားသည် parent layer သည် child layer ကို *ရိုးရှင်းစွာ* ချိတ်ဆက်ခြင်းဖြစ်ပြီး :guilabel:`Composition` (ဖွဲ့စည်းမှု) အမျိုးအစားသည် parent layer များကို ပွားလိုက်လျှင် child feature များကိုပါ ပွားပေးနိုင်ပြီး feature တစ်ခုကို ဖျက်လိုက်လျှင် child feature များပါ ပျက်သွားမည်ဖြစ်သည်။ ရလာဒ်တွင် အဆင့်များ အားလုံးကို အစီစဥ်တကျ လုပ်ဆောင်သွားမည်ဖြစ်သည်။ (ဆိုလိုသည်မှာ အပွား၏ အပွား ....များကို ဖျက်လိုက်ခြင်းဖြစ်သည်)

.. _figure_relations_manager:

.. figure:: img/relations2.png
   :align: center

   ဒေသများနှင့် လေဆိပ် layer များကြား ဆက်စပ်မှုကို ထည့်သွင်းခြင်း။

:guilabel:`Relations`(ဆက်သွယ်ချက်) tab မှ |symbologyAdd|:guilabel:`Discover Relation` (ဆက်သွယ်ချက် ရှာဖွေခြင်း) ခလုတ်ကို နှိပ်ခြင်းအားဖြင့် ထည့်သွင်းထားသော layer များ၏ provider များထံမှရရှိနိုင်သော ဆက်သွယ်ချက်များကို များကိုရယူနိုင်သည်။ Layer များကို PostgreSQL သို့မဟုတ် SpatiaLite ပုံစံကဲ့သို့ provider များတွင် သိမ်းဆည်းထားနိုင်သည်။

.. index:: Feature form, Linked forms, Embedded form

Forms for 1-N relations (1-N ဆက်သွယ်ချက်အတွက် ပုံစံများ)
.........................................................

ယခုအခါ QGIS သည် ဆက်သွယ်ချက်များကိုသိရှိသွားမည်ဖြစ်ပြီး ၎င်းကို ထုတ်လုပ်သည့်ပုံစံများကို ပိုမိုကောင်းမွန်စေရန်အတွက် အသုံးပြုမည်ဖြစ်သည်။ ပုံသေပုံစံနည်းလမ်း (အလိုအလျောက်ထုတ်လုပ်ထားသော) ကိုမပြောင်းလဲသောကြောင့် ပုံစံတွင် widget (အထားအသိုနေရာပုံစံ) အသစ်တစ်ခု ထပ်ထည့်ပါမည်။ မြေပုံရည်ညွှန်းချက်ထဲရှိ ဒေသ layer ကို ရွေးပြီး identify tool ကို အသုံးပြုနိုင်ပါသည်။ အပြင်အဆင် (setting) များပေါ်မူတည်၍ ပုံစံသည် တိုက်ရိုက်ဖွင့်လာနိုင်သည် သို့မဟုတ် လုပ်ဆောင်ချက်များအောက်ရှိ identification dialog တွင် ၎င်းကိုဖွင့်ရန် ရွေးချယ်ရမည်ဖြစ်သည်။

.. _figure_embedded_form:

.. figure:: img/relations3.png
   :align: center

   လေဆိပ်များနှင့် ဆက်စပ်သော ဒေသများ Identification dialog

မြင်တွေ့ရသည့်အတိုင်း ဒေသအတွက် သတ်မှတ်ထားသော လေဆိပ်များအားလုံးကို ဇယားတစ်ခုတွင် ပြသထားသည်။ ခလုတ်တချို့လည်း ပါဝင်ပါသည်။ ၄င်းတို့ကို အတိုချုပ် သုံးသပ်ကြည့်ပါက-

* |toggleEditing| ခလုတ်သည် ပြင်ဆင်ခြင်း (edit) mode ကို အဖွင့်အပိတ်လုပ်ရန်ဖြစ်သည်။ ဒေသ layer မှ feature တစ်ခု၏ feature form တွင် ရှိနေသော်လည်း ၎င်းသည် လေဆိပ် layer ၏ edit mode ကို အဖွင့်အပိတ်လုပ်သွားနိုင်သည်ကို သတိပြုပါ။ သို့သော် ဇယားသည် လေဆိပ် layer ၏ feature များကို ကိုယ်စားပြုသည်။
* |saveEdits| ခလုတ်သည် အပွား layer (လေဆိပ်) ရှိ ပြင်ဆင်ချက်များအားလုံးကို သိမ်းဆည်းရန်အတွက် ဖြစ်သည်။
* |capturePoint| ခလုတ်သည် မြေပုံ canvas ရှိ လေဆိပ် ဂျီဩမေတြီကို digitize ပြုလုပ်နိုင်ပြီး feature အသစ်ကို လက်ရှိဒေသသို့ default အနေဖြင့် သတ်မှတ်ပေးသည်။ Icon သည် ဂျီသြမေတြီ အမျိုးအစားအလိုက် ပြောင်းလဲသွားမည်ကို သတိပြုပါ။
* |newTableRow| ခလုတ်သည် လေဆိပ် layer attribute ဇယားတွင်မှတ်တမ်းအသစ်တစ်ခုကို ပေါင်းထည့်ပြီး feature အသစ်ကို လက်ရှိဒေသသို့ default အနေဖြင့် သတ်မှတ်ပေးသည်။ ဂျီသြမေတြီကို :guilabel:`Add part` (အပိုင်းများ ပေါင်းထည့်ခြင်း) digitize ပြုလုပ်သည့်ကိရိယာ ဖြင့် နောက်ပိုင်းတွင် ရေးဆွဲနိုင်သည်။
* |duplicateFeature| ခလုတ်သည် child layer အတွင်း တစ်ခု သို့မဟုတ် တစ်ခုထက်ပိုသော child feature များကို ကူးယူပြီး ထည့်နိုင်သည်။ ၎င်းတို့ကို နောက်ပိုင်းတွင် မတူညီသော parent feature တစ်ခု အဖြစ်လုပ်ဆောင်နိုင်သည် သို့မဟုတ် ၎င်းတို့၏ attribute များကို ပြုပြင်မွမ်းမံနိုင်သည်။
* |deleteSelectedFeatures| ခလုတ်သည် ရွေးချယ်ထားသော လေဆိပ်(များ)ကို အပြီးတိုင် ဖျက်ပစ်သည်။
* |link| သင်္ကေတသည် လက်ရှိဒေသအတွက် သတ်မှတ်ပေးမည့် လက်ရှိလေဆိပ်ကို ရွေးချယ်နိုင်သည့် dialog အသစ်ကို ဖွင့်ပေးသည်။ ၎င်းသည် မှားယွင်းသောဒေသတွင် လေဆိပ်ကို မတော်တဆ ဖန်တီးမိပါက အဆင်ပြေစေရန်ဆောင်ရွက်ပေးသည်။
* |unlink| သင်္ကေတသည် ရွေးချယ်ထားသော လေဆိပ်(များ)ကို လက်ရှိဒေသမှ ချိတ်ဆက်မှုဖြုတ်ပေးနိုင်ပြီး သတ်မှတ်မှုများမပါရှိစေတော့ပါ (Foreign key ကို NULL ဟုသတ်မှတ်လိုက်သည်)။
* |zoomToSelected| ခလုတ်ကို အသုံးပြု၍ ရွေးချယ်ထားသော child feature များသို့ မြေပုံကို ချဲ့ကြည့်နိုင်သည်။
* ခလုတ်နှစ်ခုဖြစ်သော |formView| နှင့် |openTable| သည် သက်ဆိုင်ရာ child feature များ၏ :ref:`table
  view and form view <attribute_table_view>` (table view နှင့် form view) အကြား ကူးပြောင်းပေးသည်။

ဒေသ feature များအတွက် :ref:`Drag and Drop Designer <customize_form>` ကိုအသုံးပြုပါက မည်သည့် tool များ အသုံးပြုနိုင်သည်ကို ရွေးချယ်နိုင်ပါသည်။ :guilabel:`Force hide form on add feature` option (ပေါင်းထည့်ထားသော feature ပေါ်တွင် form ကို ဖျောက်ထားပေးခြင်း) ကို အသုံးပြု၍ feature အသစ်တစ်ခုကို ထည့်သွင်းသည့်အခါ form အသစ်တစ်ခုဖွင့်မည်/မဖွင့်မည်ကို ဆုံးဖြတ်နိုင်သည်။ ဤ option သည် null မဟုတ်သော attribute များသည် သင့်တော်သော မူလတန်ဖိုးတစ်ခုကို ယူရမည်ဆိုသည့် သဘောသက်ရောက်သည်ကိုသတိပြုပါ။

.. _figure_select_relation_tools:

.. figure:: img/relations11.png
   :align: center

   ဒေသများ-လေဆိပ်များဆိုင်ရာ ဆက်စပ်မှု tool များကို ပြင်ဆင်သတ်မှတ်ရန်အတွက် Drag and Drop Designer

.. Todo: It could be nice that those advanced widgets get a description one day

အထက်ဖော်ပြပါ ဥပမာတွင် ကိုးကားချက်ရယူသည့် layer တွင် ဂျီသြမေတြီများ ရှိသည်။ (ထို့ကြောင့် ၎င်းသည် အက္ခရာဂဏန်း ဇယားတစ်ခုမျှသာမဟုတ်ပါ) ထို့ကြောင့် အထက်ဖော်ပြပါအဆင့်များသည် သက်ဆိုင်ရာ ဂျီဩမေတြီ feature မရှိသော layer attribute table တွင် entry (ထည့်သွင်းခြင်း) တစ်ခုကို ဖန်တီးပေးလိမ့်မည်ဖြစ်သည်။ ဂျီသြမေတြီကို ထည့်ရန်-

#. ကိုးကားချက်ရယူသည့် layer အတွက် |openTable| :menuselection:`Open Attribute Table` (attribute ဇယား ဖွင့်ခြင်း) ကိုရွေးပါ။
#. ကိုးကားခံသည့် layer ၏ feature form အတွင်း ယခင်က ထည့်သွင်းထားသည့် မှတ်တမ်းကို ရွေးပါ။
#. ရွေးချယ်ထားသော attribute ဇယားမှတ်တမ်းတွင် ဂျီသြမေတြီတစ်ခုကို ပူးတွဲရန် |addPart| :sup:`Add Part` (အပိုင်း ပေါင်းထည့်ခြင်း) digitize ပြုလုပ်နိုင်သော tool ကိုသုံးပါ။

အကယ်၍ လေဆိပ်ဇယားပေါ်တွင် လုပ်ဆောင်နေပါက ``fk_region`` field အတွက် ဆက်သွယ်မှု အကိုးအကား widget သည် အလိုအလျောက် သတ်မှတ်သွားမည်ဖြစ်သည်။ (``fk_region`` field သည် ဆက်သွယ်ချက်ကို ဖန်တီးရန် အသုံးပြုသည့် field ဖြစ်သည်) :ref:`Relation Reference widget <configure_field>` (ဆက်သွယ်မှု အကိုးအကား widget) တွင် ကြည့်ရှုပါ။

.. Todo: It could be nice that those advanced widgets get a description one day

လေဆိပ် form တွင် |formView| ခလုတ်ကို ``fk_region`` field ၏ ညာဘက်ခြမ်းတွင် တွေ့နိုင်ပါသည်။ ခလုတ်ကို နှိပ်လိုက်ပါက ဒေသ layer ၏ form ကို ဖွင့်ပေးမည်ဖြစ်သည်။ ဤ widgetသည် ချိတ်ဆက်ထားသော parent feature များ၏ form များကို လွယ်ကူလျင်မြန်စွာ ဖွင့်စေနိုင်ပါသည်။

.. _figure_linked_forms:

.. figure:: img/relations4.png
   :align: center

   ဒေသများ နှင့် ဆက်စပ်သော လေဆိပ် Identification dialog

ဆက်သွယ်မှု အကိုးအကား widget တွင် child layer တစ်ခုအတွင်း parent layer ၏ form ကို ထည့်သွင်းနိုင်ပါသည်။ ၎င်းကို လေဆိပ် layer ၏  :menuselection:`Properties --> Attributes Form`(attribute ပုံစံ) menu တွင် ရနိုင်သည်။ ``fk_region`` field ကိုရွေးချယ်ပါ ထို့နောက် ``Show embedded form`` ‌ကို အမှန်ခြစ်ပါ။

Feature dialog ကို ကြည့်ရှုပါက၊ ဒေသ၏ form သည် လေဆိပ်များ form တွင် ထည့်သွင်းထားပြီး လက်ရှိလေဆိပ်ကို အခြားဒေသသို့ သတ်မှတ်ပေးနိုင်သည့် combobox (ခလုတ်များစွာပါဝင်သော box) တစ်ခုပါရှိမည်ကို တွေ့ရပါမည်။

.. _figure_linked_forms_embedded:

.. figure:: img/relations5.png
   :align: center

ထို့အပြင် အကယ်၍ လေဆိပ် layer ၏ edit mode ကို အဖွင့်အပိတ်ပြုလုပ်ပါက ``fk_region`` field တွင်
အလိုအလျှောက်ဆောင်ရွက်သည့် လုပ်ဆောင်ချက်လည်း ပါရှိသည်- စာရိုက်နေစဉ်တွင် ဒေသ layer ``id`` field ၏ တန်ဖိုးအားလုံးကို မြင်တွေ့ရမည်ဖြစ်သည်။ အကယ်၍ လေဆိပ် layer ၏ :menuselection:`Properties --> Attributes Form`(attribute များ ပုံစံ) menu တွင် ``Allow adding new features`` (feature အသစ်များ ပေါင်းထည့်ခြင်းကို ခွင့်ပြုခြင်း) ကိုရွေးချယ်ပါက |symbologyAdd| ခလုတ်ကို အသုံးပြု၍ ဒေသ layer အတွက် polygon တစ်ခုကို digitize လုပ်နိုင်သည်။

Child layer များ၏ attribute များအပေါ် အခြေခံ၍ parent layer ၏ feature များကို ရွေးချယ်ရန်အတွက် 
:ref:`select_by_value` tool  တွင်လည်း child layer ကို အသုံးပြုနိုင်သည်။

:numref:`figure_select_by_value` တွင် လေဆိပ်များ၏ပျမ်းမျှအမြင့်ပေသည် ပင်လယ်ရေမျက်နှာပြင်အထက်
မီတာ 500 ထက်ကြီးသောဒေသအားလုံးကိုရွေးချယ်ထားသည်။

Form ထဲတွင် မတူညီသော ပေါင်းစပ်လုပ်ဆောင်ချက်များစွာကို တွေ့ရပါမည်။

.. _figure_select_by_value:

.. figure:: img/relation_select_by_value.png
   :align: center

   Child တန်ဖိုးများဖြင့် parent feature များကို ရွေးချယ်ခြင်း


.. index:: Many-to-many relation; Relation
.. _many_to_many_relation:

Introducing many-to-many (N-M) relations (အများနှင့် အများ (N-M) ဆက်သွယ်ချက်ကို မိတ်ဆက်ခြင်း)
----------------------------------------------------------------------------------------------

N-M ဆက်သွယ်ချက်သည် ဇယားနှစ်ခုကြားတွင် အများနှင့်အများ ဆက်သွယ်ချက်ဖြစ်သည်။ ဥပမာအားဖြင့် ``airports(လေဆိပ်)`` နှင့်  ``airlines(လေကြောင်းလိုင်းများ)`` layerများ- လေဆိပ်တစ်ခုသည် လေကြောင်းလိုင်းကုမ္ပဏီအများအပြားကို လက်ခံရရှိပြီး လေကြောင်းလိုင်းကုမ္ပဏီတစ်ခုသည် လေဆိပ်အများအပြားသို့ ပျံသန်းသွားပါသည်။

ဤ SQL ကုဒ်သည် *တည်နေရာများ* ဟုအမည်ပေးထားသော PostgreSQL/PostGIS schema ရှိ N-M ဆက်သွယ်ချက်အတွက် လိုအပ်သော ဇယားသုံးခုကို ဖန်တီးပေးပါသည်။ PostGIS အတွက် :menuselection:`Database --> DB Manager…` သို့မဟုတ် `pgAdmin <https://www.pgadmin.org>`_ ကဲ့သို့သော ပြင်ပ tool များကို အသုံးပြု၍ code ကို လုပ်ဆောင်နိုင်သည်။ လေဆိပ်ဇယားတွင် ``airports(လေဆိပ်)`` layer ကို သိမ်းဆည်းထားပြီး လေကြောင်းလိုင်းများ ဇယားတွင် ``airlines(လေကြောင်းလိုင်းများ)``  layer ကို သိမ်းဆည်းထားသည်။ ဇယားနှစ်ခုစလုံးတွင် ရှင်းလင်းစေရန်အတွက် field အနည်းငယ်ကို အသုံးပြုထားသည်။ *လှည့်ကွက်ရှိသော* အပိုင်းသည် ``airports_airlines(လေဆိပ်_လေကြောင်းလိုင်းများ)`` ဇယားဖြစ်သည်။ ၎င်းကို လေဆိပ်အားလုံးအတွက် လေကြောင်းလိုင်းအားလုံးကို စာရင်းပြုစုရန် လိုအပ်ပါသည် (သို့မဟုတ် အပြန်အလှန်အားဖြင့်)။ ထိုသို့သောဇယားမျိုးကို *ဆုံချက် ဇယား (pivot table)* ဟုခေါ်သည်။ ဤဇယားရှိ *ကန့်သတ်ချက်များ* သည် လေဆိပ်တစ်ခုအား ၎င်းတို့၏ layer များတွင် လေဆိပ်တစ်ခုနှင့် လေကြောင်းလိုင်းတစ်ခု ရှိပြီးသားဖြစ်မှသာလျှင် ထိုနှစ်ခုကို ချိတ်ဆက်နိုင်မည်ဖြစ်သည်။

.. code-block:: sql

   CREATE SCHEMA locations;

   CREATE TABLE locations.airports
   (
      id serial NOT NULL,
      geom geometry(Point, 4326) NOT NULL,
      airport_name text NOT NULL,
      CONSTRAINT airports_pkey PRIMARY KEY (id)
   );

   CREATE INDEX airports_geom_idx ON locations.airports USING gist (geom);

   CREATE TABLE locations.airlines
   (
      id serial NOT NULL,
      geom geometry(Point, 4326) NOT NULL,
      airline_name text NOT NULL,
      CONSTRAINT airlines_pkey PRIMARY KEY (id)
   );

   CREATE INDEX airlines_geom_idx ON locations.airlines USING gist (geom);

   CREATE TABLE locations.airports_airlines
   (
      id serial NOT NULL,
      airport_fk integer NOT NULL,
      airline_fk integer NOT NULL,
      CONSTRAINT airports_airlines_pkey PRIMARY KEY (id),
      CONSTRAINT airports_airlines_airport_fk_fkey FOREIGN KEY (airport_fk)
         REFERENCES locations.airports (id)
         ON DELETE CASCADE
         ON UPDATE CASCADE
         DEFERRABLE INITIALLY DEFERRED,
      CONSTRAINT airports_airlines_airline_fk_fkey FOREIGN KEY (airline_fk)
         REFERENCES locations.airlines (id)
         ON DELETE CASCADE
         ON UPDATE CASCADE
         DEFERRABLE INITIALLY DEFERRED
    );

PostgreSQL အစား GeoPackage ကိုသုံးနိုင်သည်။ ဤကိစ္စတွင် :menuselection:`Database --> DB Manager…` ကိုအသုံးပြု၍ ဇယားသုံးခုကို ကိုယ်တိုင်ဖန်တီးနိုင်သည်။ GeoPackage တွင် schema (အစီအစဥ်များ) များ မပါရှိသောကြောင့် *တည်နေရာများ* prefix (‌ရှေ့အစ) ကို မလိုအပ်ပါ။

``airports_airlines(လေဆိပ်_လေကြောင်းလိုင်း)`` ဇယားရှိ foreign key ကန့်သတ်ချက်များကို :menuselection:`Table --> Create Table…` သို့မဟုတ် :menuselection:`Table --> Edit Table…` ကို အသုံးပြု၍ ဖန်တီးမရနိုင်သောကြောင့် ၎င်းတို့ကို :menuselection:`Database --> SQL Window…` ကို အသုံးပြု၍ ဖန်တီးသင့်ပါသည်။ GeoPackage သည် *ADD CONSTRAINT* ထုတ်ပြန်ချက်များကို မပံ့ပိုးနိုင်သောကြောင့် ``airports_airlines(လေဆိပ်_လေကြောင်းလိုင်း)`` ဇယားကို ဖော်ပြပါအဆင့်နှစ်ဆင့်ဖြင့် ဖန်တီးသင့်သည်-

#. :menuselection:`Table --> Create Table…` ကို အသုံးပြု၍ ဇယားကို ``id`` field ဖြင့်သာ သတ်မှတ်ပါ။
#. :menuselection:`Database --> SQL Window…` ကို အသုံးပြု၍ ဤ SQL ကုဒ်ကို ရိုက်ထည့်ပြီး လုပ်ဆောင်ပါ-

   .. code-block:: sql

      ALTER TABLE airports_airlines
         ADD COLUMN airport_fk INTEGER
         REFERENCES airports (id)
         ON DELETE CASCADE
         ON UPDATE CASCADE
         DEFERRABLE INITIALLY DEFERRED;

      ALTER TABLE airports_airlines
         ADD COLUMN airline_fk INTEGER
         REFERENCES airlines (id)
         ON DELETE CASCADE
         ON UPDATE CASCADE
         DEFERRABLE INITIALLY DEFERRED;


ထို့နောက် QGIS တွင် အထက်တွင်ဖော်ပြခဲ့သည့်အတိုင်း :ref:`one-to-many relations <one_to_many_relation>` နှစ်ခုကို သတ်မှတ်သင့်သည်-

* ``airlines`` (လေကြောင်းလိုင်းများ) ဇယားနှင့် pivot ဇယား ကြားဆက်သွယ်ချက် နှင့်
* ``airports`` (လေဆိပ်များ) ဇယားနှင့် pivot ဇယား ကြားဆက်သွယ်ချက် ကိုသတ်မှတ်သင့်သည်။

ပိုမိုလွယ်ကူသော နည်းလမ်းမှာ (PostgreSQL တစ်ခုတည်းအတွက်သာ) :menuselection:`Project --> Properties --> Relations` ထဲရှိ :guilabel:`Discover Relations` ကို အသုံးပြုခြင်းဖြစ်သည်။ QGIS သည် database အတွင်းရှိ ဆက်သွယ်ချက်အားလုံးကို အလိုအလျှောက် ဖတ်ရှုသွားမည်ဖြစ်ပြီး လိုအပ်သော နှစ်ခုကို ရွေးချယ်ပေးရန်သာ လိုအပ်ပါသည်။ ပထမဆုံး QGIS project တွင် ဇယားသုံးခုကို ထည့်ပေးရန် သတိပြုပါ။

.. _figure_setup_relations:

.. figure:: img/relations6.png
   :align: center

   ဆက်သွယ်ချက်နှင့် အလိုအလျှောက်ရှာဖွေမှု

``airport(လေဆိပ်)`` တစ်ခုသို့မဟုတ် ``airline(လေကြောင်းလိုင်း)`` တစ်ခုကို ဖယ်ရှားလိုပါက QGIS သည် ``airports_airlines (လေဆိပ်_လေကြောင်းလိုင်း)`` ဇယားရှိ ဆက်စပ်မှတ်တမ်း(များ)ကို ဖယ်ရှားမည်မဟုတ်ပါ။ လက်ရှိနမူနာတွင်ရှိသကဲ့သို့ pivot ဇယားဖန်တီးမှုတွင် မှန်ကန်သော *ကန့်သတ်ချက်များ* ကို သတ်မှတ်ပါက ၄င်းလုပ်ဆောင်ချက်ကို database မှ လုပ်ဆောင်မည်ဖြစ်သည်။

.. note:: ** N-M ဆက်သွယ်ချက်ကို အလိုအလျောက် ကူးပြောင်းခြင်း (transaction) အဖွဲ့ နှင့် ပေါင်းစပ်ခြင်း**

  ထိုသို့သောအခြေအနေတွင်အလုပ်လုပ်သောအခါ :menuselection:`Project Properties--> Data Sources -->` တွင်‌ transaction mode ကို ဖွင့်ပေးသင့်သည်။ QGIS သည် ဇယားအားလုံး (လေကြောင်းလိုင်းများ၊ လေဆိပ်များနှင့် pivot ဇယားများ) တွင် row (များ) ကို ထည့်ခြင်း သို့မဟုတ် update လုပ်ခြင်းများ လုပ်ဆောင်နိုင်ပါသည်။

နောက်ဆုံးတွင် ``airports(လေဆိပ်များ)`` နှင့် ``airlines(လေကြောင်းလိုင်းများ)`` layer များအတွက် :menuselection:`Layer Properties --> Attributes Form` တွင် မှန်ကန်သော cardinality (အစုအဖွဲ့) ကို ရွေးချယ်ရပါမည်။ ပထမတစ်ခုအတွက် **လေကြောင်းလိုင်းများ (id)** ကိုရွေးချယ်သင့်ပြီး ဒုတိယတစ်ခုအတွက် 
**လေဆိပ် (id)** ကို ရွေးချယ်သင့်သည်။

.. _figure_cardinality:

.. figure:: img/relations7.png
   :align: center

   ဆက်သွယ်ချက် cardinality (အစုအဖွဲ့)ကို သတ်မှတ်ခြင်း 

ယခုအခါ form အခွဲများတွင် :guilabel:`Add child feature` သို့မဟုတ် :guilabel:`Link existing child feature` ကို အသုံးပြု၍ လေဆိပ်တစ်ခုနှင့် လေကြောင်းလိုင်းတစ်ခု (သို့မဟုတ် လေကြောင်းလိုင်းတစ်ခု နှင့် လေဆိပ်တစ်ခု ချိတ်ဆက်နိုင်ပြီဖြစ်ပါသည်။ ``airports_airlines (လေဆိပ်_လေကြောင်းလိုင်း)`` ဇယားတွင် မှတ်တမ်းတစ်ခု အလိုအလျောက် ထည့်သွင်းသွားမည်ဖြစ်သည်။

.. _figure_relationship_working:

.. figure:: img/relations8.png
   :align: center

   လေဆိပ်များနှင့် လေကြောင်းလိုင်းများ အကြား N-M ဆက်သွယ်ချက်

.. note::  **အများမှ တစ်ခုဆက်သွယ်ချက်** cardinality (အစုအဖွဲ့)ကို အသုံးပြုခြင်း။

  တစ်ခါတစ်ရံ N-M ဆက်သွယ်ချက်တွင် pivot ဇယားကို  ဖျောက်ထားခြင်းသည် မသင့်လျော်ပါ။ အဓိကအကြောင်းမှာ ဆက်သွယ်ချက် တစ်ခုတည်ဆောက်သည့်အခါ ဆက်သွယ်ချက်ထဲတွင် တန်ဖိုးများသာရှိနိုင်သော attribute များရှိနေသောကြောင့်ဖြစ်သည်။ အကယ်၍ ဇယားများသည် layer များဖြစ်လျှင် (ဂျီသြမေတြီ field တစ်ခုပါရှိသော) pivot ဇယားရှိ foreign key feild များအတွက် :guilabel:`On map identification` option (:menuselection:`Layer Properties --> Attributes Form --> Available widgets --> Fields`) ကို ဖွင့်ပေးနိုင်ပါသည်။

.. note:: **Pivot ဇယား မူလ key**

  Pivot ဇယားရှိ primary key တွင် field ပေါင်းများစွာ အသုံးပြုခြင်းကို ရှောင်ပါ။ QGIS သည် primary key တစ်ခုတည်းကို ယူဆသောကြောင့် ``constraint airports_airlines_pkey primary key (airport_fk, airline_fk)`` ကဲ့သို့ ကန့်သတ်ချက်တစ်ခုသည် လုပ်ဆောင်နိုင်မည်မဟုတ်ပါ။


.. index:: Polymorphic relation; Relation
.. _polymorphic_relation:

Introducing polymorphic relations (Polymorphic (ကွဲပြားသည့်ပုံစံမျိုးစုံဖြင့် ဖြစ်ပေါ်နေသော) ဆက်သွယ်ချက်များ ကို မိတ်ဆက်ခြင်း)
-------------------------------------------------------------------------------------------------------------------------------

Polymorphic ဆက်သွယ်ချက်သည် 1-N ဆက်သွယ်ချက်၏ အထူးကိစ္စရပ်ဖြစ်ပြီး၊ တစ်ခုတည်းသော ကိုးကားချက်ရယူသည့် (စာရွက်စာတမ်း) layer (referencing layer) တစ်ခုတွင် ကိုးကားခံသည့် layer များစွာ (multiple referenced layer) အတွက် feature များပါရှိသည်။ ၄င်းသည် ပုံမှန်ဆက်သွယ်ချက်နှင့် မတူညီပဲ ကိုးကားခံသည့် layer တစ်ခုစီအတွက် မတူညီသော ကိုးကားချက်ရယူသည့် layer လိုအပ်သည်။ ကိုးကားချက်ရယူသည့် (စာရွက်စာတမ်း) layer တွင် ထပ်တိုး ``layer_field`` column ပေါင်းထည့်ခြင်းဖြင့် ကိုးကားချက်ရယူသည့် (စာရွက်စာတမ်း) layer တစ်ခုကိုရရှိနိုင်သည်။ ၄င်းသည် ကိုးကားခံသည့် layer ကို ခွဲခြားနိုင်ရန် အချက်အလက်များကို သိမ်းဆည်းထားသည်။ ၎င်း၏ အရိုးရှင်းဆုံးပုံစံတွင် ကိုးကားချက်ရယူသည့် (စာရွက်စာတမ်း) layer သည် ထို field ထဲသို့ ကိုးကားခံသည့် layer ၏အမည်ကို ပေါင်းထည့်လိုက်ပါသည်။

ပိုမိုတိတိကျကျဆိုရလျှင် polymorphic ဆက်သွယ်ချက်သည် dynamically (ပုံသေမဟုတ်စွာ) သတ်မှတ်ထားသော ကိုးကားခံသည့် layer ရှိသော်လည်း တူညီသော ကိုးကားချက်ရယူသည့် layer များပါရှိသော ပုံမှန်ဆက်သွယ်ချက်များ အစုတစ်ခုဖြစ်သည်။ Layer ၏ polymorphic setting အား expression တစ်ခုကို အသုံးပြုခြင်းဖြင့် ဖြေရှင်းပါသည်။ ၎င်းသည် ဇယားအမည်၊ layer id၊ layer အမည်ကဲ့သို့သော ကိုးကားခံသည့် layer ၏ ဂုဏ်သတ္တိအချို့နှင့် ကိုက်ညီမှုရှိရန် လိုအပ်သည်။

ပန်းခြံသို့ သွားပြီး မြင်တွေ့ရသော ``plants(အပင်)`` နှင့်  ``animals(တိရစ္ဆာန်)`` အမျိုးမျိုးကို ဓါတ်ပုံရိုက်မည်ဟု မှန်းဆကြည့်ပါ။ အပင် သို့မဟုတ် တိရိစ္ဆာန်တစ်ခုစီတွင် ၎င်းနှင့်ဆက်စပ်သော ဓါတ်ပုံများစွာပါရှိသည်၊ ထို့ကြောင့် ဓါတ်ပုံများကို သိမ်းဆည်းရန် ပုံမှန် 1:N ဆက်သွယ်ချက်ကို အသုံးပြုမယ်ဆိုပါက ``animal_images(တိရစ္ဆာန်_ဓါတ်ပုံများ)`` နှင့် ``plant_images(အပင်_ဓါတ်ပုံများ)`` သီးခြားဇယားနှစ်ခု လိုအပ်ပါမည်။ ၄င်းသည် ဇယား ၂ ခုအတွက် ပြဿနာတစ်ခုမဟုတ်သော်လည်း မှိုများ၊ ငှက်များ စသည်တို့အတွက် သီးခြားဓာတ်ပုံရိုက်လိုသည်ဆိုပါက ပြဿနာတစ်ခုဖြစ်နိုင်ပါသည်။

Polymorphic ဆက်သွယ်ချက်သည် ကိုးကားချက်ရယူသည့် feature အားလုံးကို ``documents(စာရွက်စာတမ်းများ)`` ဇယားတစ်ခုတည်းတွင် သိမ်းဆည်းထားသောကြောင့် ဤပြဿနာကို ဖြေရှင်းပေးပါသည်။ Feature တစ်ခုစီအတွက် ကိုးကားခံသည့် layer ကို ``referenced_layer`` field တွင် သိမ်းဆည်းထားပြီး ``referenced_fk`` field တွင် ကိုးကားခံသည့် feature id ကို သိမ်းဆည်းထားသည်။


Defining polymorphic relations (Polymorphic ဆက်သွယ်ချက်များကို သတ်မှတ်ခြင်း)
.............................................................................

ပထမဦးစွာ layer များအကြား polymorphic ဆက်သွယ်ချက်များကို QGIS မှသိစေရန် ဆောင်ရွက်ပါ။ ၄င်းကို :menuselection:`Project --> Properties...` တွင် လုပ်ဆောင်နိုင်သည်။ :guilabel:`Relations`(ဆက်သွယ်ချက်) tab ကိုဖွင့်ပြီး |symbologyAdd| :guilabel:`Add Relation`(ဆက်သွယ်ချက်ပေါင်းထည့်ခြင်း) ခလုတ်ဘေးရှိ အောက်မြှားလေးကို နှိပ်ပါ။ ထို့အခါ အသစ်ပေါ်လာသော dropdown မှ :guilabel:`Add Polymorphic Relation` (polymorphic ဆက်သွယ်ချက် ပေါင်းထည့်ခြင်း) option ကို ရွေးချယ်နိုင်သည်။

.. _figure_define_polymorphic_relation:

.. figure:: img/relations9.png
   :align: center

   ``documents(စာရွက်စာတမ်းများ) `` layer ကို ကိုးကားချက်ရယူသည့် layer အဖြစ်အသုံးပြုပြီး ``animals(တိရစ္ဆာန်များ)`` နှင့် ``plants(အပင်များ)`` layer များကို ကိုးကားခံသည့် layer အဖြစ် အသုံးပြု၍ polymorphic ဆက်သွယ်ချက်တစ်ခုကို ထည့်သွင်းခြင်း
  

* **Id**  ကို အတွင်းပိုင်း ရည်ရွယ်ချက်များအတွက် အသုံးပြုမည်ဖြစ်ပြီး သီးသန့်ဖြစ်ရပါမည်။ ၄င်းကို :ref:`custom forms <customize_form>` တည်ဆောက်ရာတွင် လိုအပ်ပါသည်။ ၄င်းကို ကွက်လပ်ထားရှိခဲ့ပါက Id တစ်ခုကို ထုတ်ပေးမည်ဖြစ်သော်လည်း လုပ်ဆောင်ရလွယ်ကူစေရန် မိမိကိုယ်တိုင် သတ်မှတ်ပေးနိုင်ပါသည်။

* **Referencing Layer (child) (ကိုးကားချက်ရယူသည့် layer)** ကို child layer အဖြစ် ယူဆသည်။ ၄င်းပေါ်တွင် foreign field ရှိသည်။ ယခုကိစ္စတွင် ၄င်းသည် ``documents(စာရွက်စာတမ်းများ)`` layer ဖြစ်သည်။ ဤ layer အတွက် အခြား layer သို့ညွှန်ပြသည့် ကိုးကားချက်ရယူသည့် field တစ်ခုကို ပေါင်းထည့်ရန်လိုအပ်သည်၊ ထို့ကြောင့် ၎င်းသည် ``referenced_fk`` ဖြစ်သည်။

  .. note:: တစ်ခါတစ်ရံတွင်၊ layer တစ်ခုရှိ feature များကို သီးခြားခွဲခြားသတ်မှတ်ရန် field တစ်ခုထက်ပို၍ လိုအပ်ပါသည်။ ထိုသို့သော layer တစ်ခုနှင့် ဆက်သွယ်ချက်တစ်ခုဖန်တီးခြင်းသည် ကိုက်ညီသော field တစ်စုံ ထက်ပိုသော **composite key** တစ်ခု လိုအပ်သည်။ လိုအပ်သလို အတွဲများထည့်ရန် |symbologyAdd| :sup:`Add new field pair as part of a composite foreign key` ခလုတ်ကို အသုံးပြုပါ။

* **Layer Field** သည် layer expression ၏ ရလာဒ်ကို သိမ်းဆည်းထားသည့် ကိုးကားချက်ရယူသည့်ဇယားရှိ field ဖြစ်သည်။ ၄င်းသည် feature နှင့်ဆိုင်သော ကိုးကားချက်ရယူသည့်ဇယားဖြစ်သည်။ ဤ ဥပမာတွင် ၄င်းသည် ``referenced_layer`` field ဖြစ်လိမ့်မည်။

* **Layer expression** သည် layer ၏ သီးသန့် ခွဲခြားဖော်ထုတ်ပေးသည့်အရာ (unique identifier) တစ်ခုကို အကဲဖြတ်သည်။ ၄င်းသည် layer အမည်  ``@layer_name``၊ layer id  ``@layer_id``၊ layer ၏ ဇယားအမည် ``decode_uri(@layer, 'table')`` သို့မဟုတ် layer တစ်ခုကို သီးသန့် ခွဲခြားဖော်ထုတ်ပေးနိုင်သော မည်သည့်အရာမဆို ဖြစ်နိုင်သည်။

* **Relationship strength (ဆက်သွယ်ချက် ခိုင်မာမှုအား)** သည် parent နှင့် child layer ကြား ဆက်သွယ်ချက်၏ ခိုင်မာမှုကို သတ်မှတ်သည်။ ပုံသေ :guilabel:`Association` (အဖွဲ့) အမျိုးအစားသည် parent layer သည် child layer ကို *ရိုးရှင်းစွာ* ချိတ်ဆက်ခြင်းဖြစ်ပြီး :guilabel:`Composition` (ဖွဲ့စည်းမှု) အမျိုးအစားသည် parent layer များကို ပွားလိုက်လျှင် child feature များကိုပါ ပွားပေးနိုင်ပြီး feature တစ်ခုကို ဖျက်လိုက်လျှင် child feature များပါ ပျက်သွားမည်ဖြစ်သည်။ ရလာဒ်တွင် အဆင့်များ အားလုံးကို အစီစဥ်တကျ လုပ်ဆောင်သွားမည်ဖြစ်သည်။ (ဆိုလိုသည်မှာ အပွား၏ အပွား ....များကို ဖျက်လိုက်ခြင်းဖြစ်သည်)

* **Referenced Layers (ကိုးကားခံသည့် layer များ)** ကိုလည်း ပင်မ layer များအဖြစ် ယူဆကြပြီး၊ ညွှန်ပြထားသော primary key ပါရှိသော layer များဖြစ်သောကြောင့် ဤနေရာတွင် ၎င်းတို့သည် ``plants(အပင်များ)`` နှင့် ``animals(တိရစ္ဆာန်များ)`` layer များဖြစ်ပါမည်။ Dropdown မှ ကိုးကားခံသည့် layer များ၏ primary key ကို သတ်မှတ်ရန်လိုအပ်ပါသည်၊ ထို့ကြောင့်၎င်းသည် ``fid`` ဖြစ်သည်။ မှန်ကန်သော primary key တစ်ခုသတ်မှတ်ချက်သည် ကိုးကားခံသည့် layer အားလုံးတွင် ထိုအမည်ဖြင့် field တစ်ခုရှိရန် လိုအပ်သည်ကို သတိပြုပါ။ ထိုကဲ့သို့သော field မရှိလျှင် polymorphic ဆက်သွယ်ချက်တစ်ခုကို သိမ်းဆည်းနိုင်မည်မဟုတ်ပါ။

ထည့်သွင်းပြီးသည်နှင့် polymorphic ဆက်သွယ်ချက်ကို :guilabel:`Edit Polymorphic Relation` (polymorphic ဆက်သွယ်ချက် ပြင်ဆင်ခြင်း) menu ထည့်သွင်းမှုမှတစ်ဆင့် ပြင်ဆင်တည်းဖြတ်နိုင်သည်။

.. _figure_list_polymorphic_relations:

.. figure:: img/relations10.png
   :align: center

   အသစ်ဖန်တီးထားသော polymorphic ဆက်သွယ်ချက်နှင့် တိရိစ္ဆာန်များနှင့် အပင်များအတွက် ၄င်း၏ child ဆက်သွယ်ချက်များကို အကြိုကြည့်ရှုခြင်း။


အထက်ဖော်ပြပါ ဥပမာသည် အောက်ပါ database schema ကို အသုံးပြုထားသည်-

.. code-block:: sql

   CREATE SCHEMA park;

   CREATE TABLE park.animals
   (
      fid serial NOT NULL,
      geom geometry(Point, 4326) NOT NULL,
      animal_species text NOT NULL,
      CONSTRAINT animals_pkey PRIMARY KEY (fid)
   );

   CREATE INDEX animals_geom_idx ON park.animals USING gist (geom);

   CREATE TABLE park.plants
   (
      fid serial NOT NULL,
      geom geometry(Point, 4326) NOT NULL,
      plant_species text NOT NULL,
      CONSTRAINT plants_pkey PRIMARY KEY (fid)
   );

   CREATE INDEX plants_geom_idx ON park.plants USING gist (geom);

   CREATE TABLE park.documents
   (
      fid serial NOT NULL,
      referenced_layer text NOT NULL,
      referenced_fk integer NOT NULL,
      image_filename text NOT NULL,
      CONSTRAINT documents_pkey PRIMARY KEY (fid)
   );

.. index:: External Storage, WebDAV
.. _external_storage:

Storing and fetching an external resource (ပြင်ပအရင်းအမြစ်တစ်ခုကို သိမ်းဆည်းခြင်းနှင့် ရယူခြင်း)
=================================================================================================

Field တစ်ခုသည် ပြင်ပသိုလှောင်မှုစနစ်တွင် သိမ်းဆည်းထားသော အရင်းအမြစ်တစ်ခုကို ပစ်မှတ်ထားနိုင်သည်။ Attribute form များကို ပြင်ဆင်သတ်မှတ်နိုင်သည်။ ထို့ကြောင့် ၎င်းတို့သည် သုံးစွဲသူများ၏ လိုအပ်ချက်အရ အဆိုပါအရင်းအမြစ်များကို form များမှ တိုက်ရိုက် သိမ်းဆည်းပြီး ရယူရန်အတွက် ပြင်ပသိုလှောင်မှုစနစ်တွင် သုံးစွဲသူ (client) တစ်ဦးအဖြစ် လုပ်ဆောင်သည်။

.. _external_storage_configuration:

Configuring an external storage (ပြင်ပသိုလှောင်မှုတစ်ခုကို ပြင်ဆင်သတ်မှတ်ခြင်း)
--------------------------------------------------------------------------------

ပြင်ပသိုလှောင်မှုတစ်ခု ပြင်ဆင်သတ်မှတ်ရန်အတွက် vector :ref:`attribute form properties <edit_widgets>` (vector attribute form ဂုဏ်သတ္တိများ) မှ ၄င်းကို ဦးစွာ ပြင်ဆင်သတ်မှတ်ရမည်ဖြစ်ပြီး :guilabel:`Attachment` widget ကိုရွေးချယ်ပါ။

.. _figure_external_storage_configuration:

.. figure:: img/external_storage_configuration.png
   :align: center

   ပေးထားသော field တစ်ခုအတွက် WebDAV ပြင်ပသိုလှောင်မှုတစ်ခု ပြုပြင်ခြင်း

:guilabel:`Attachment` widget မှ :guilabel:`Storage type` (သိုလှောင်မှုပုံစံ) ကို ဦးစွာရွေးချယ်ရပါမည်-

* :guilabel:`Select Existing File` (ရှိပြီးသား ဖိုင်ကို ရွေးချယ်ခြင်း) - ဦးတည်မည့် URL ရှိပြီးသားဖြစ်လိမ့်မည်။ အရင်းအမြစ်တစ်ခုကို ရွေးချယ်သောအခါ၊ သိုလှောင်လုပ်ဆောင်မှု မရရှိသေးပဲ attribute ကို URL ဖြင့် ရိုးရှင်းစွာ update ပြုလုပ်ပါသည်။

* :guilabel:`Simple Copy` (ရိုးရှင်းစွာ ကူးယူခြင်း) - File disk destination (ဖိုင်လမ်းကြောင်းဦးတည်ရာ) တစ်ခုပေါ်တွင် အရင်းအမြစ်၏ မိတ္တူ တစ်ခုကို သိုလှောင်သည်။ (ကွန်ပျူတာအတွင်းရှိ file စနစ်တစ်ခု သို့မဟုတ် network shared file system (ကွန်ယက်မျှဝေထားသော file စနစ်) ဖြစ်နိုင်သည်) နှင့် attribute ကို ကူးယူထားသည့် လမ်းကြောင်းဖြင့် update ပြုလုပ်ပါသည်။ 

* :guilabel:`WebDAV Storage` (WebDAV သိုလှောင်မှု) - အရင်းအမြစ်ကို `WebDAV <https://en.wikipedia.org/wiki/WebDAV>`_ protocol ကို ထောက်ပံ့ပေးထားသည့် HTTP server တစ်ခုသို့ ပို့ဆောင်ပြီး attribute ကို ၄င်း၏ URL ဖြင့် update ပြုလုပ်ပါသည်။ `Nextcloud <https://nextcloud.com/>`_ ၊ `Pydio <https://pydio.com>`_ သို့မဟုတ် အခြား file hosting (လက်ခံပေးသော) software သည် ဤ protocol ကို ထောက်ပံ့‌ပေးပါသည်။

* :guilabel:`AWS S3` - အရင်းအမြစ်သည် `AWS Simple Storage Service <https://en.wikipedia.org/wiki/Amazon_S3>`_ protocol ကိုထောက်ပံ့ပေးသည့် server တစ်ခုသို့ ပို့ဆောင်ပေးပြီး attribute ကို ၄င်း၏ URL ဖြင့် update ပြုလုပ်ပါသည်။ Amazon Web Service နှင့် `MinIO <https://en.wikipedia.org/wiki/MinIO>`_ hosting software သည် ဤ protocol ကို ထောက်ပံ့‌ပေးပါသည်။

ထို‌နောက် အရင်းအမြစ်တစ်ခု အသစ်ကို သိုလှောင်ရန် လိုအပ်သည့်အချိန်တွင် အသုံးပြုမည့် URL ကို ပံ့ပိုးပေးသည့် :guilabel:`Store URL` (URL သိုလှောင်ခြင်း) parameter (ကန့်သတ်ချက်များ) ကို သတ်မှတ်ရန်လိုအပ်ပါသည်။ Feature attribute အလိုက် သတ်မှတ်တန်ဖိုးရရှိရန် :ref:`data defined override widget <data_defined>` (Data သတ်မှတ်၍ အစားထိုးရေးသားသော widget) အသုံးပြု၍ expression တစ်ခု သတ်မှတ်နိုင်သည်။

**@selected_file_path** ဆိုသည့် variable ကို ထို expression တွင် အသုံးပြုနိုင်ပြီး အသုံးပြုသူရွေးချယ်ထားသော file ၏ ပကတိ file path (ဖိုင်လမ်းကြောင်း) ကို ကိုယ်စားပြုသည် (file selector အသုံးပြုခြင်း သို့မဟုတ် drag and drop ပြုလုပ်ခြင်း)။

.. note::

  **WebDAV** သို့မဟုတ် **AWS S3** ပြင်ပသိုလှောင်ခန်းကို အသုံးပြုခြင်းသည် URL သည် "/" နှင့် အဆုံးသတ်ပါက ၄င်းအား ဖိုင်တွဲ (folder) တစ်ခုအဖြစ် သတ်မှတ်ပြီး နောက်ဆုံး URL ကိုရရှိရန် ရွေးချယ်ထားသော file အမည်ကို နောက်တွင် ဆက်တွဲပေးမည်ဖြစ်သည်။


ပြင်ပ သိုလှောင်မှုစနစ်အတွက် လိုအပ်လျှင် :ref:`authentication <authentication>` (စစ်မှန်ကြောင်းအထောက်အထားပြခြင်း) တစ်ခုကို ပြင်ဆင်သတ်မှတ်နိုင်သည်။

.. note::

   **AWS S3** ပြင်ပသိုလှောင်မှု အသုံးပြုရန်  **AWS S3** authentication အမျိုးအစား တစ်ခု အသုံးပြုရမည်။

.. _external_storage_use:

Using an external storage (ပြင်ပသိုလှောင်မှု တစ်ခု အသုံးပြုခြင်း)
------------------------------------------------------------------

ပြင်ဆင်သတ်မှတ်မှုများ ပြုလုပ်ပြီးသည်နှင့် feature ၏ attribute တစ်ခုကို ပြုပြင်သည့်အချိန် :guilabel:`...` ခလုတ်ကို အသုံးပြုပြီး local file တစ်ခုကို ရွေးချယ်နိုင်သည်။ ပြင်ဆင်သတ်မှတ်ထားသည့် :ref:`storage type <external_storage_configuration>` (သိုလှောင်မှုအမျိုးအစား) ပေါ်မူတည်၍ file သည် ပြင်ပသိုလှောင်မှု စနစ်တွင် သိုလှောင်သွားလိမ့်မည်ဖြစ်ပြီး (:guilabel:`Select existing file` (ရှိပြီးသားဖိုင်ကို ရွေးချယ်ခြင်း) မှလွဲ၍) field ကို အရင်းအမြစ် URL အသစ်ဖြင့် update ပြုလုပ်သွားပါမည်။

.. _figure_external_storage_store:

.. figure:: img/external_storage_store.png
   :align: center

   File တစ်ခုကို WebDAV ပြင်ပသိုလှောင်မှု တစ်ခုတွင် သိုလှောင်ခြင်း

.. note::

   အသုံးပြုသူသည် ပူးတွဲပါ widget တစ်ခုလုံးပေါ်တွင် file တစ်ခုကို drag and drop ပြုလုပ်လျှင်လည်း တူညီသည့် ရလာဒ်ကို ရရှိနိုင်သည်။

သိမ်းဆည်းခြင်း လုပ်ငန်းစဥ်ကို ပယ်ဖျက်ရန် |taskCancel| :sup:`Cancel` (ဖယ်ရှားခြင်း) ခလုတ်ကို အသုံးပြုပါ။ :guilabel:`Integrated document viewer`(ပေါင်းစပ်ထားသည့်စာရွက်စာတမ်းများကိုကြည့်ရှုသည့်အရာ)ကို အသုံးပြု၍ viewer တစ်ခုကို ပြင်ဆင်သတ်မှတ်နိုင်သည်။ ထို့ကြောင့် အရင်းအမြစ်ကို ပြင်ပသိုလှောင်မှုစနစ်မှ အလိုအလျောက် ထုတ်ယူပြီး URL အောက်တွင် တိုက်ရိုက်ပြသမည်ဖြစ်သည်။ အထက်ပါ |warning| icon သည် ပြင်ပသိုလှောင်မှုစနစ်မှ အရင်းအမြစ်ကို ထုတ်ယူ၍ မရကြောင်းကို ဖော်ပြသည်။ ထိုကိစ္စတွင် အသေးစိတ်အချက်အလက်များကို :ref:`log_message_panel` တွင် ဖော်ပြမည်ဖြစ်သည်။

.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |actionRun| image:: /static/common/mAction.png
   :width: 1.5em
.. |addPart| image:: /static/common/mActionAddPart.png
   :width: 1.5em
.. |calculateField| image:: /static/common/mActionCalculateField.png
   :width: 1.5em
.. |capturePoint| image:: /static/common/mActionCapturePoint.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |conditionalFormatting| image:: /static/common/mActionConditionalFormatting.png
   :width: 1.5em
.. |copySelected| image:: /static/common/mActionCopySelected.png
   :width: 1.5em
.. |deleteAttribute| image:: /static/common/mActionDeleteAttribute.png
   :width: 1.5em
.. |deleteSelectedFeatures| image:: /static/common/mActionDeleteSelectedFeatures.png
   :width: 1.5em
.. |deselectActiveLayer| image:: /static/common/mActionDeselectActiveLayer.png
   :width: 1.5em
.. |dock| image:: /static/common/dock.png
   :width: 1.5em
.. |duplicateFeature| image:: /static/common/mActionDuplicateFeature.png
   :width: 1.5em
.. |editCut| image:: /static/common/mActionEditCut.png
   :width: 1.5em
.. |editPaste| image:: /static/common/mActionEditPaste.png
   :width: 1.5em
.. |editTable| image:: /static/common/mActionEditTable.png
   :width: 1.5em
.. |expression| image:: /static/common/mIconExpression.png
   :width: 1.5em
.. |expressionSelect| image:: /static/common/mIconExpressionSelect.png
   :width: 1.5em
.. |filterMap| image:: /static/common/mActionFilterMap.png
   :width: 1.5em
.. |formSelect| image:: /static/common/mIconFormSelect.png
   :width: 1.5em
.. |formView| image:: /static/common/mActionFormView.png
   :width: 1.2em
.. |handleStoreFilterExpressionChecked| image:: /static/common/mActionHandleStoreFilterExpressionChecked.png
   :width: 1.5em
.. |handleStoreFilterExpressionUnchecked| image:: /static/common/mActionHandleStoreFilterExpressionUnchecked.png
   :width: 1.5em
.. |highlightFeature| image:: /static/common/mActionHighlightFeature.png
   :width: 1.5em
.. |invertSelection| image:: /static/common/mActionInvertSelection.png
   :width: 1.5em
.. |link| image:: /static/common/mActionLink.png
   :width: 1.5em
.. |multiEdit| image:: /static/common/mActionMultiEdit.png
   :width: 1.5em
.. |multiEditChangedValues| image:: /static/common/multieditChangedValues.png
   :width: 1.5em
.. |multiEditMixedValues| image:: /static/common/multieditMixedValues.png
   :width: 1.5em
.. |multiEditSameValues| image:: /static/common/multieditSameValues.png
   :width: 1.5em
.. |newAttribute| image:: /static/common/mActionNewAttribute.png
   :width: 1.5em
.. |newTableRow| image:: /static/common/mActionNewTableRow.png
   :width: 1.5em
.. |openTable| image:: /static/common/mActionOpenTable.png
   :width: 1.5em
.. |openTableEdited| image:: /static/common/mActionOpenTableEdited.png
   :width: 1.5em
.. |openTableInvalid| image:: /static/common/mActionOpenTableInvalid.png
   :width: 1.5em
.. |openTableSelected| image:: /static/common/mActionOpenTableSelected.png
   :width: 1.5em
.. |openTableVisible| image:: /static/common/mActionOpenTableVisible.png
   :width: 1.5em
.. |panTo| image:: /static/common/mActionPanTo.png
   :width: 1.5em
.. |panToSelected| image:: /static/common/mActionPanToSelected.png
   :width: 1.5em
.. |radioButtonOff| image:: /static/common/radiobuttonoff.png
   :width: 1.5em
.. |radioButtonOn| image:: /static/common/radiobuttonon.png
   :width: 1.5em
.. |refresh| image:: /static/common/mActionRefresh.png
   :width: 1.5em
.. |saveEdits| image:: /static/common/mActionSaveEdits.png
   :width: 1.5em
.. |selectAll| image:: /static/common/mActionSelectAll.png
   :width: 1.5em
.. |selectedToTop| image:: /static/common/mActionSelectedToTop.png
   :width: 1.5em
.. |sort| image:: /static/common/sort.png
   :width: 1.5em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
.. |taskCancel| image:: /static/common/mTaskCancel.png
   :width: 1.5em
.. |toggleEditing| image:: /static/common/mActionToggleEditing.png
   :width: 1.5em
.. |undo| image:: /static/common/mActionUndo.png
   :width: 1.5em
.. |unlink| image:: /static/common/mActionUnlink.png
   :width: 1.5em
.. |warning| image:: /static/common/mIconWarning.png
   :width: 1.5em
.. |zoomTo| image:: /static/common/mActionZoomTo.png
   :width: 1.5em
.. |zoomToSelected| image:: /static/common/mActionZoomToSelected.png
   :width: 1.5em
