.. _`processing.modeler`:

The model designer (Model design ရေးဆွဲပေးသည့်အရာ)
===================================================

.. only:: html

   .. contents::
      :local:

*Model designer* သည် ရိုးရှင်း၍ အသုံးပြုရလွယ်သော interface တစ်ခုကိုအသုံးပြုပြီး ရှုပ်ထွေးသော model များကိုတည်ဆောက်နိုင်ပါသည်။ GIS နှင့်အလုပ်လုပ်သောအခါ လေ့လာဆန်းစစ်ခြင်းများသည် အများသောအားဖြင့် တစ်ခုတည်းသီးသန့် လုပ်ဆောင်ရခြင်းမဟုတ်ဘဲ လုပ်ငန်းများစွာနှင့် ပူးတွဲလုပ်ဆောင်ရခြင်းများဖြစ်ပါသည်။ များစွာသောလုပ်ငန်း အဆင့်ဆင့်များကို တစ်ခုတည်းဖြစ်အောင်ပေါင်းပေးနိုင်သော model designer ကိုအသုံးပြုခြင်းဖြင့် ထည့်သွင်းအသုံးပြုသော အချက်အလက်အမျိုးမျိုးကို နောက်ပိုင်းတွင် အလွယ်တကူ စေခိုင်းလုပ်ဆောင်စေနိုင်ပါသည်။ အဆင့်များနှင့် မတူညီသော algorithm များ ဘယ်လောက်များများ ပါဝင်သည်ဖြစ်စေ model တစ်ခုကို algorithm တစ်ခုတည်းအဖြစ် စေခိုင်းလုပ်ဆောင်ပေးတာကြောင့် အချိန်ကုန် လူပင်ပန်း သက်သာစေပါသည်။ 

Model designer ကို Processing menu (:menuselection:`Processing --> Model Designer`) မှဖွင့်နိုင်ပါသည်။

The model designer interface (Model designer ၏ interface)
----------------------------------------------------------

.. _figure_modeler:

.. figure:: img/modeler_canvas.png
   :align: center

   Model designer

၎င်း၏ အဓိကအပိုင်းတွင် modeler ၏ ဖွဲ့စည်းမှုနှင့် modeler အား ကိုယ်စားပြုသည့် workflow ကိုပြင်ဆင်တည်ဆောက်နိုင်သော working canvas (အလုပ်လုပ်သောနေရာ) တစ်ခုရှိပါသည်။

Dialog ၏အပေါ်ဘက်တွင် menu အမျိုးမျိုးနှင့် :guilabel:`Navigation` toolbar တို့မှ များစွာသော tool များကိုခေါ်ယူအသုံးပြုနိုင်ပါသည်။ 

Model menu
...........

.. list-table::
   :header-rows: 1
   :widths: 25 12 12 50

   * - အညွှန်း
     - ဖြတ်လမ်းနည်း
     - Navigation Toolbar
     - ရှင်းလင်းဖော်ပြချက်
   * - |success| :guilabel:`Validate Model (Model ကို အတည်ပြုခြင်း)`
     -
     -
     - Model ထဲတွင် ထည့်သွင်းအသုံးပြုသော algorithm များနှင့် ထည့်သွင်းအသုံးပြုသော အချက်အလက်များ ရှိ/မရှိကို စစ်ဆေးပေးပါသည်။ Model ကို အသုံးမပြုမီ စစ်ဆေးခြင်းက အဆင်ပြေစေပါသည်။
   * - |play| :guilabel:`Run Model...` (Model ကိုလုပ်ဆောင်ခြင်း)
     - :kbd:`F5`
     - |checkbox|
     - Model ကိုစေခိုင်းလုပ်ဆောင်ပေးပါသည်။
   * - :guilabel:`Reorder Model Inputs...` (Model ထည့်သွင်းထားမှုကို ပြန်လည်စီစဉ်ခြင်း)
     -
     -
     - Algorithm dialog ထဲတွင် အသုံးပြုသူကို ပြသမည့် input များ၏အစီအစဉ်ကို သတ်မှတ်ပေးပါသည်။
   * - :guilabel:`Reorder Output Layers...` (ရလာဒ် layer များကို ပြန်လည်စီစဉ်ခြင်း)
     -
     -
     - ထွက်လာမည့် ရလာဒ်ကို project ထဲသို့ထည့်သွင်းသောအခါ model မှ ထွက်လာမည့် ရလာဒ်ကိုမဖြစ်မနေအသုံးပြုရမည့် သီးသန့်အစီအစဉ်တစ်ခုကို သတ်မှတ်ပေးပါသည်။
   * - |fileOpen| :guilabel:`Open Model...` (Model ကိုဖွင့်ပါ)
     - :kbd:`Ctrl+O`
     - |checkbox|
     - တည်းဖြတ်ပြင်ဆင်ရန် သို့မဟုတ် စေခိုင်းလုပ်ဆောင်ရန် :file:`.model3` file ကိုဖွင့်ပေးပါသည်။
   * - |fileSave| :guilabel:`Save Model` (Model ကိုသိမ်းဆည်းပါ)
     - :kbd:`Ctrl+S`
     - |checkbox|
     - Model ကို ကွန်ပျူတာထဲတွင် :file:`.model3` file တစ်ခုအဖြစ်သိမ်းဆည်းပေးပါသည်။
   * - |fileSaveAs| :guilabel:`Save Model as...` (Model ကို တစ်ခုခုအဖြစ် သိမ်းဆည်းပါ)
     - :kbd:`Ctrl+Shift+S`
     - |checkbox|
     - Model ကို ကွန်ပျူတာထဲတွင် :file:`.model3` file အသစ်တစ်ခုအဖြစ်သိမ်းဆည်းပေးပါသည်။
   * - |fileSave| :guilabel:`Save Model in project` (Model ကို project ထဲတွင်သိမ်းဆည်းပါ)
     -
     - |checkbox|
     - Model ကို project file ထဲတွင် ထည့်မြှပ်ထားခြင်းသည် project file ကိုမျှဝေသောအခါ model ပါ ပါသွားသောကြောင့် အခြားသူများလည်း အသုံးပြုနိုင်ပါသည်။
   * - |helpContents| :guilabel:`Edit Model Help...` (Model တည်းဖြတ်ပြင်ဆင်ခြင်းအတွက် အကူအညီရယူရန်)
     -
     - |checkbox|
     - Model၊ algorithm များ၊ parameter များ၊ ထွက်လာမည့်ရလာဒ်များ၊ ဖန်တီးသူနှင့် version များအကြောင်းကို မှတ်တမ်းပြုစုရန် interface ဖြစ်ပါသည်။
   * - :menuselection:`Export -->` (ထုတ်ယူပါ)
     -
     -
     -
   * - |saveMapAsImage| :menuselection:`--> Export as Image...` (ဓာတ်ပုံအဖြစ်ထုတ်ယူပါ)
     -
     - |checkbox|
     - Model ၏ graphical design ကို ဓာတ်ပုံ file format (သရုပ်ပြခြင်းအတွက်) အဖြစ်သိမ်းဆည်းပေးပါသည်။
   * - |saveAsPDF|:menuselection:`--> Export as PDF...` (PDF အဖြစ်ထုတ်ယူပါ)
     -
     -
     - Model ၏ graphical design ကို :file:`PDF` file format (သရုပ်ပြခြင်းအတွက်) အဖြစ်သိမ်းဆည်းပေးပါသည်။
   * - |saveAsSVG|:menuselection:`--> Export as SVG...` (SVG အဖြစ်ထုတ်ယူပါ)
     -
     -
     -  Model ၏ graphical design ကို :file:`SVG` file format (သရုပ်ပြခြင်းအတွက်) အဖြစ်သိမ်းဆည်းပေးပါသည်။
   * - |fileSave|:menuselection:`--> Export as Script Algorithm...` (Script Algorithm အဖြစ်ထုတ်ယူပါ)
     -
     - |checkbox|
     - Model ၏ လမ်းညွှန်များပါဝင်သော python script file ကိုထုတ်ပေးပါသည်။

Edit menu (တည်းဖြတ်ပြင်ဆင်ခြင်း Menu)
......................................

.. list-table::
   :header-rows: 1
   :widths: 25 12 12 50

   * - အညွှန်း
     - ဖြတ်လမ်းနည်း
     - Navigation Toolbar
     - ရှင်းလင်းဖော်ပြချက်
   * - |selectAll| :guilabel:`Select All` (အားလုံးကိုရွေးချယ်ပါ)
     - :kbd:`Ctrl+A`
     -
     - Designer ထဲရှိ model component များအားလုံးကိုရွေးချယ်ပေးပါသည်။
   * - :guilabel:`Snap selected components to Grid` (ရွေးချယ်ထားသော component များကို grid ဆီသို့ ဆွဲကပ်ပါ)
     -
     -
     - Element များကို grid ဆီသို့ဆွဲကပ်ပြီး ညီညာအောင် ပြုလုပ်ပေးပါသည်။
   * - |redo| :guilabel:`Redo (ပြန်လည်လုပ်ဆောင်ခြင်း)`
     - :kbd:`Ctrl+Y`
     - |checkbox|
     - နောက်ဆုံးမကြိုက်လို့ ပယ်ဖျက်ခဲ့သောလုပ်ဆောင်ချက်ကို ပြန်လည်ရယူခြင်း။ :guilabel:`Undo/Redo` panel တွင်ကြည့်ပါ။
   * - |undo| :guilabel:`Undo (မလုပ်တော့ပါ)`
     - :kbd:`Ctrl+Z`
     - |checkbox|
     - နောက်ဆုံးလုပ်ခဲ့သော အပြောင်းအလဲကို ပယ်ဖျက်ခြင်း။ :guilabel:`Undo/Redo` panel တွင်ကြည့်ပါ။
   * - |editCut| :guilabel:`Cut`
     - :kbd:`Ctrl+X`
     -
     - Model မှ Component များ၏ရွေးချယ်ထားမှုကို ရွှေ့ပြောင်းပေးပါသည်။
   * - |editCopy| :guilabel:`Copy`
     - :kbd:`Ctrl+C`
     -
     - Model မှ Component များ၏ရွေးချယ်ထားမှုကို မိတ္တူပွားပေးပါသည်။။
   * - |editPaste| :guilabel:`Paste`
     - :kbd:`Ctrl+V`
     -
     - Model တစ်ခုမှ တူညီသော model အတွင်း သို့မဟုတ် အခြား model တစ်ခုသို့ ရွှေ့ပြောင်းထားသော သို့မဟုတ် ကူးယူထားသော ရွေးချယ်မှုအစိတ်အပိုင်းများကို နေရာချပေးပါသည်။ ရွေးချယ်ထားသောအစိတ်အပိုင်းများသည် ၎င်းတို့၏မူလဂုဏ်သတ္တိများနှင့်မှတ်ချက်များကို ဆက်လက်ထားရှိမည်ဖြစ်သည်။
   * - |deleteSelected| :guilabel:`Delete selected components` (ရွေးချယ်ထားသော အစိတ်အပိုင်းများကို ဖျက်ပစ်ခြင်း)
     - :kbd:`Del`
     -
     - Model မှ အစိတ်အပိုင်းတစ်ခုကို ဖယ်ထုတ်ခြင်း။
   * - :guilabel:`Add Group Box` (အုပ်စု box ထည့်ခြင်း)
     -
     -
     - ဆက်စပ်သော အစိတ်အပိုင်းများကို မြင်သာစွာအုပ်စုဖွဲ့ရန် ၎င်းတို့၏ နောက်ခံတွင် box တစ်ခုထည့်ထားခြင်း။ ကြီးမားသော Model များတွင် workflow ကို ရှင်းရှင်းလင်းလင်းရှိစေရန် အသုံးပြုနိုင်ပါသည်။

View menu (ကြည့်ရှုခြင်းမြင်ကွင်းဆိုင်ရာ menu)
...............................................

.. list-table::
   :header-rows: 1
   :widths: 25 12 12 50

   * - အညွှန်း
     - ဖြတ်လမ်းနည်း
     - Navigation Toolbar
     - ရှင်းလင်းဖော်ပြချက်
   * - :menuselection:`Zoom To -->` (သို့ ချဲ့ကြည့်ခြင်း)
     -
     -
     - ရွေးချယ်ထားသော အုပ်စု၏အကျယ်အဝန်းအတိုင်း ချဲ့ကြည့်ခြင်း။
   * - |zoomIn| :guilabel:`Zoom In` (ချဲ့ကြည့်ခြင်း)
     - :kbd:`Ctrl++`
     - |checkbox|
     -
   * - |zoomOut| :guilabel:`Zoom Out` (ချုံ့ကြည့်ခြင်း)
     - :kbd:`Ctrl+-`
     - |checkbox|
     -
   * - |zoomActual| :guilabel:`Zoom to 100%` (ရာနှုန်းပြည့် မြင်ကွင်းကို ချဲ့ကြည့်ခြင်း)
     - :kbd:`Ctrl+1`
     - |checkbox|
     -
   * - |zoomFullExtent| :guilabel:`Zoom Full` (အပြည့်ချဲ့ကြည့်ခြင်း)
     - :kbd:`Ctrl+0`
     - |checkbox|
     - Designer ၏လက်ရှိ canvas တွင်ရှိနေသော အစိတ်အပိုင်းများအားလုံးကို ပြသပေးပါသည်။
   * - |checkbox| :guilabel:`Show Comments` (Comment များကိုပြသခြင်း)
     -
     -
     - Algorithm တိုင်း သို့မဟုတ် model desinger ထဲတွင်ထည့်သွင်းအသုံးပြုသော အချက်အလက်များနှင့် ဆက်စပ်သော မှတ်ချက်များကို ပြသပေးပါသည်။
   * - |unchecked| :guilabel:`Enable Snapping` (ဆွဲကပ်ခြင်းကို ဖွင့်ပေးခြင်း)
     -
     -
     -
   * - |unchecked| :guilabel:`Toggle Panel Visibility` (Panel မြင်ရနိုင်ခြင်းကို အဖွင့်အပိတ်လုပ်ခြင်း)
     - :kbd:`Ctrl+Tab`
     -
     - Designer ထဲရှိ :ref:`panels <modelerpanels>` (ဘောင်ကွက်များ) ကို အဖွင့်၊ အပိတ် လုပ်ဆောင်ပေးပါသည်။


.. _modelerpanels:

Panels
.......

Window ၏ဘယ်ဘက်အခြမ်းသည် model တွင် element အသစ်များထည့်ပေါင်းခြင်းအတွက် အသုံးပြုနိုင်သော panel ၅ ခုရှိသည့် section ဖြစ်ပါသည်-

#. :guilabel:`Model Properties` - Model ၏အမည် (မဖြစ်မနေလိုအပ်ပါသည်) နှင့် :ref:`Processing Toolbox <processing.toolbox>` ထဲတွင်ဖော်ပြမည့် အုပ်စု တို့ကိုသတ်မှတ်ပါ။
#. :guilabel:`Inputs` - Model ကိုပုံဖော်နိုင်သော :ref:`input parameters <processing_inputs>` များအားလုံး
#. :guilabel:`Algorithms` - အသုံးပြုနိုင်သော :ref:`Processing algorithms <processing_algs>` များ
#. :guilabel:`Variables` - Model များတွင် တမူထူးခြားပြီး ၎င်းတို့သာအသုံးပြုနိုင်သော :ref:`variables <general_tools_variables>` များပါဝင်နိုင်ပါသည်။ ၎င်း variable များကို model အတွင်း အသုံးပြုသော မည်သည့် expression နှင့်မဆို အသုံးပြုနိုင်ပါသည်။ ၎င်းတို့သည် model တစ်ခုအတွင်းရှိ algorithm များကိုထိန်းချုပ်ခြင်း နှင့် variable တစ်ခုကိုပြောင်းလဲခြင်းဖြင့် model ၏ aspect များစွာကိုထိန်းချုပ်ခြင်း တို့အတွက် အသုံးဝင်ပါသည်။ Variable များကို :guilabel:`Variables` panel ထဲတွင် ကြည့်နိုင်ပြီး မွမ်းမံပြင်ဆင်နိုင်ပါသည်။
#. :guilabel:`Undo History` - Modeler ထဲတွင်ဖြစ်ပျက်ခဲ့သော အရာအားလုံးကို ဤ panel ထဲတွင်မှတ်တမ်းတင်ထားပြီး အမှားလုပ်မိသောအရာများကို ပယ်ဖျက်ရန်အတွက် လွယ်ကူစေပါသည်။

About available algorithms (အသုံးပြုနိုင်သော algorithm များအကြောင်း)
.....................................................................

Model တစ်ခုကို ဒီဇိုင်းဆွဲသောအခါ toolbox မှ စေခိုင်းလုပ်ဆောင်နိုင်သော တချို့သော algorithm များသည် အသုံးပြုနိုင်သော algorithm များစာရင်းတွင် ပေါ်နေမည်မဟုတ်ပါ။ Model တစ်ခုထဲတွင် ပါဝင်စေရန် algorithm တစ်ခုသည် မှန်ကန်သော ဝေါဟာရ (semantic) ရှိရပါမည်။ Algorithm သည် ထိုကဲ့သို့ ကောင်းကောင်းမွန်မွန်သတ်မှတ်ထားသော ဝေါဟာရ (semantic) မရှိလျှင် (ဥပမာ - output layer များအရေအတွက်ကို ကြိုတင်မသိနိုင်ခြင်း) ၎င်းကို model  တစ်ခုထဲတွင်အသုံးမပြုနိုင်သလို modeler dialog ထဲတွင် တွေ့နိုင်သော algorithm စာရင်းတွင်လည်း ပေါ်နေမည် မဟုတ်ပါ။ တနည်းအားဖြင့် အချို့သော algorithm များသည် modeler အတွက် သီးသန့်များဖြစ်ကြပါသည်။ ထို algorithm များသည် 'Modeler Tools' အုပ်စုထဲတွင် ရှိပါသည်။

Creating a model (Model တစ်ခုဖန်တီးခြင်း)
------------------------------------------

Model တစ်ခုဖန်တီးခြင်းတွင် အခြေခံအဆင့် နှစ်ဆင့်ပါဝင်ပါသည် -

#. *မဖြစ်မနေလိုအပ်သော input များသတ်မှတ်ခြင်း*။ ထို input များကို parameter window တွင် ပေါင်းထည့်ပေးမည်ဖြစ်သည်၊ သို့မှသာ အသုံးပြုသူများသည် model ကိုစေခိုင်းလုပ်ဆောင်သောအခါ တန်ဖိုးများကို သတ်မှတ်နိုင်မည်ဖြစ်သည်။ Model ကိုယ်တိုင်ပင် algorithm တစ်ခုဖြစ်သည်။ ထို့ကြောင့် Processing framework ထဲတွင် အသုံးပြုနိုင်သော algorithm များအားလုံးအတွက်ကဲ့သို့ parameter window ကိုအလိုအလျှောက် ဖန်တီးပေးပါသည်။
#. *Workflow သတ်မှတ်ခြင်း*။ Model ၏ input data များကို အသုံးပြုပြီး algorithm များထည့်ပေါင်းခြင်းနှင့် သတ်မှတ်ထားသည့် input များ သို့မဟုတ် model ထဲရှိ အခြား algorithm များမှထုတ်ပေးသော output များကို မည်သို့အသုံးချမည်ကိုရွေးချယ်ခြင်းအားဖြင့် workflow ကို သတ်မှတ်ပါသည်။

.. _processing_inputs:

Definition of inputs (ထည့်သွင်းအသုံးပြုသော အချက်အလက်များကို သတ်မှတ်ခြင်း)
..........................................................................

ပထမဆုံးလုပ်ဆောင်ရမည့်အဆင့်မှာ model အတွက် input များကို သတ်မှတ်ပေးရန်ဖြစ်ပါသည်။ Modeler window ၏ ဘယ်ဘက်ခြမ်းထဲက :guilabel:`Inputs` panel တွင် အောက်ပါ element များတွေ့ရပါမည်-

.. list-table:: Model တည်ဆောက်ခြင်းအတွက် parameter အမျိုးအစားများ၏ စာရင်း
   :class: longtable

   * - :class:`Annotation Layer <qgis.core.QgsProcessingParameterAnnotationLayer>`
     - :class:`Authentication Configuration <qgis.core.QgsProcessingParameterAuthConfig>`
     - :class:`Boolean <qgis.core.QgsProcessingParameterBoolean>`
     - :class:`Color <qgis.core.QgsProcessingParameterColor>`
     - :class:`Connection Name <qgis.core.QgsProcessingParameterProviderConnection>`
   * - :class:`Coordinate Operation <qgis.core.QgsProcessingParameterCoordinateOperation>`
     - :class:`CRS <qgis.core.QgsProcessingParameterCrs>`
     - :class:`Database Schema <qgis.core.QgsProcessingParameterDatabaseSchema>`
     - :class:`Database Table <qgis.core.QgsProcessingParameterDatabaseTable>`
     - :class:`Datetime <qgis.core.QgsProcessingParameterDateTime>`
   * - :class:`Distance <qgis.core.QgsProcessingParameterDistance>`
     - :class:`Duration <qgis.core.QgsProcessingParameterDuration>`
     - :class:`DXF Layers <qgis.core.QgsProcessingParameterDxfLayers>`
     - :class:`Enum <qgis.core.QgsProcessingParameterEnum>`
     - :class:`Expression <qgis.core.QgsProcessingParameterExpression>`
   * - :class:`Extent <qgis.core.QgsProcessingParameterExtent>`
     - :class:`Field Aggregates <qgis.core.QgsProcessingParameterAggregate>`
     - :class:`Fields Mapper <qgis.core.QgsProcessingParameterFieldMapping>`
     - :class:`File/Folder <qgis.core.QgsProcessingParameterFile>`
     - :class:`Geometry <qgis.core.QgsProcessingParameterGeometry>`
   * - :class:`Map Layer <qgis.core.QgsProcessingParameterMapLayer>`
     - :class:`Map Theme <qgis.core.QgsProcessingParameterMapTheme>`
     - :class:`Matrix <qgis.core.QgsProcessingParameterMatrix>`
     - :class:`Mesh Dataset Groups <qgis.core.QgsProcessingParameterMeshDatasetGroups>`
     - :class:`Mesh Dataset Time <qgis.core.QgsProcessingParameterMeshDatasetTime>`
   * - :class:`Mesh Layer <qgis.core.QgsProcessingParameterMeshLayer>`
     - :class:`Multiple Input <qgis.core.QgsProcessingParameterMultipleLayers>`
     - :class:`Number <qgis.core.QgsProcessingParameterNumber>`
     - :class:`Point <qgis.core.QgsProcessingParameterPoint>`
     - :class:`Point Cloud Attribute <qgis.core.QgsProcessingParameterPointCloudAttribute>`
   * - :class:`Point Cloud Layer <qgis.core.QgsProcessingParameterPointCloudLayer>`
     - :class:`Print Layout <qgis.core.QgsProcessingParameterLayout>`
     - :class:`Print Layout Item <qgis.core.QgsProcessingParameterLayoutItem>`
     - :class:`Range <qgis.core.QgsProcessingParameterRange>`
     - :class:`Raster Band <qgis.core.QgsProcessingParameterBand>`
   * - :class:`Raster Layer <qgis.core.QgsProcessingParameterRasterLayer>`
     - :class:`Scale <qgis.core.QgsProcessingParameterScale>`
     - :class:`String <qgis.core.QgsProcessingParameterString>`
     - :class:`TIN Creation Layers <qgis.core.QgsProcessingParameterTinInputLayers>`
     - :class:`Vector Features <qgis.core.QgsProcessingParameterFeatureSource>`
   * - :class:`Vector Field <qgis.core.QgsProcessingParameterField>`
     - :class:`Vector Layer <qgis.core.QgsProcessingParameterVectorLayer>`
     - :class:`Vector Tile Writer Layers <qgis.core.QgsProcessingParameterVectorTileWriterLayers>`
     -
     -
  
.. note:: Input များပေါ်တွင် mouse ကိုတင်ထားလျှင် ထပ်ဆောင်းအချက်အလက်များကို tooltip (ယာယီပေါ်လာသော စာသား box) ဖြင့် ဖော်ပြပေးပါလိမ့်မည်။

Element တစ်ခုပေါ်တွင် double-click နှိပ်သောအခါ ၎င်း၏ ဝိသေသလက္ခဏာများကို သတ်မှတ်ပေးနိုင်သော dialog တစ်ခုပေါ်လာပါမည်။ Parameter ပေါ်တွင်မူတည်ပြီး dialog သည် အနည်းဆုံး element တစ်ခုပါဝင်ပါလိမ့်မည် (model ကိုစေခိုင်းလုပ်ဆောင်သောအခါ အသုံးပြုသူများ မြင်ရမည့် ရှင်းလင်းဖော်ပြချက်ဖြစ်ပါသည်)။ ဥပမာ- ဂဏန်းတန်ဖိုးတစ်ခုကို ထည့်လျှင် အောက်ပါပုံတွင်ပြထားသည့်အတိုင်း parameter ၏ရှင်းလင်းဖော်ပြချက်အပြင် မူရင်းတန်ဖိုးတစ်ခု နှင့် ဆီလျော်သောတန်ဖိုးအပိုင်းအခြားကို သတ်မှတ်ပေးရမည်ဖြစ်ပါသည်။

.. _figure_model_parameter:

.. figure:: img/models_parameters.png
   :align: center

   Model Parameter များသတ်မှတ်ခြင်း

|checkbox| ``Mandatory`` option ကိုအမှန်ခြစ်ခြင်းဖြင့် မိမိ၏ model အတွက် input ကို မဖြစ်မနေထည့်သွင်းရမည့်အရာအဖြစ် သတ်မှတ်နိုင်ပြီး |unchecked| ``Advanced`` ကိုအမှန်ခြစ် ခြစ်ထားလျှင် input များကို ``Advanced`` section အတွင်း ရှိစေရန် သတ်မှတ်နိုင်ပါသည်။ Model တွင် parameter များစွာရှိနေပြီး အချို့သည် အရေးမကြီးသော်လည်း ၎င်းတို့ကို ရွေးချယ်လိုသောအခါ ဤနည်းလမ်းသည် အသုံးဝင်ပါသည်။

ပေါင်းထည့်ထားသော input တစ်ခုချင်းစီအတွက် model canvas တွင် element အသစ်တစ်ခုကို ထည့်သွင်းပေးပါသည်။

.. _figure_model_parameter_canvas:

.. figure:: img/models_parameters2.png
   :align: center

   Model Parameter များ

စာရင်းမှ input အမျိုးအစားကို model canvas ထဲ ထားချင်သောနေရာတွင် ဆွဲယူထည့်ပြီးနေရာချခြင်းဖြင့်လည်း input များကို ထည့်သွင်းနိုင်ပါသည်။ ရှိနေပြီးသား input တစ်ခု၏ parameter တစ်ခုကို ပြောင်းလဲလိုလျှင် ၎င်းကို double-click နှိပ်လိုက်ပါက တူညီသော dialog ပေါ်လာပါလိမ့်မည်။

အခြား model ထဲတွင် model တစ်ခုကိုအသုံးပြုသာအခါ လိုအပ်သော input များနှင့် output များကို canvas ထဲတွင်ပြသပေးပါလိမ့်မည်။

Definition of the workflow (Workflow ကိုသတ်မှတ်ခြင်း)
......................................................

အောက်ပါဥပမာတွင် input နှစ်ခုနှင့် algorithm နှစ်ခုကို ထည့်သွင်းအသုံးပြုပါမည်။ ဤ model ၏ရည်ရွယ်ချက်မှာ ``Drape`` algorithm ကိုအသုံးပြုပြီး DEM raster layer တစ်ခုမှ မြေမျက်နှာအနိမ့်အမြင့်တန်ဖိုးများကို line layer တစ်ခုသို့ ကူးထည့်ရန်နှင့် ``Climb Along Line`` algorithm ကိုအသုံးပြုပြီး line layer ၏ စုစုပေါင်း တိုးလာမှု (ascent) ကိုတွက်ချက်ရန် ဖြစ်ပါသည်။

:guilabel:`Inputs` tab ထဲတွင် line အတွက် ``Vector Layer`` နှင့် DEM အတွက် ``Raster Layer`` အနေဖြင့် input နှစ်မျိုးကို ရွေးချယ်ပါ။ Workflow ထဲသို့ algorithm များကို ပေါင်းထည့်နိုင်ပြီ ဖြစ်သည်။

Algorithm များကို :guilabel:`Algorithms` panel တွင်တွေ့ရမည်ဖြစ်ပြီး ၎င်းတို့ကိုလည်း Processing toolbox ထဲတွင်အုပ်စုဖွဲ့ထားသကဲ့သို့ ပုံစံတူ လုပ်ထားပါသည်။

.. _figure_model_parameter_inputs:

.. figure:: img/models_parameters3.png
   :align: center

   Model Input များ


Model တစ်ခုသို့ algorithm တစ်ခုပေါင်းထည့်ရန်အတွက် အခြား input များကဲ့သို့ ၎င်း၏အမည်ကို double-click နှိပ်ပါ သို့မဟုတ် ၎င်းကိုဆွဲထည့်ပါ။ Input များအတွက် algorithm ၏ ရှင်းလင်းဖော်ပြချက်ကို ပြင်ဆင်ရေးသားနိုင်ပြီး comment တစ်ခုထည့်သွင်းနိုင်ပါသည်။ Algorithm တစ်ခုထည့်သွင်းသောအခါ စေခိုင်းလုပ်ဆောင်မှု panel တစ်ခု ပေါ်လာမည်ဖြစ်ပြီး ၎င်း panel တွင် toolbox မှ algorithm ကိုစေခိုင်းလုပ်ဆောင်သောအခါ ပေါ်လာသည့်အရာနှင့်ဆင်တူသော အကြောင်းအရာတစ်ခုပါရှိပါသည်။ အောက်ပါဓာတ်ပုံသည် ``Drape (set Z value from raster)`` နှင့် ``Climb along line`` algorithm dialog နှစ်ခုလုံးကို ပြသပေးပါသည်။

.. _figure_model_parameter_alg:

.. figure:: img/models_parameters4.png
   :align: center

   Model Algorithm parameter များ


မြင်တွေ့ရသည့်အတိုင်း ကွဲပြားမှုအချို့တော့ ရှိပါသည်။ Parameter တစ်ခုချင်းစီတွင် workflow လုပ်ဆောင်နေစဉ် မည်သို့လုပ်ဆောင်မည်ကို ထိန်းချုပ်နိုင်သော drop-down menu တစ်ခုရှိပါသည်- 

* |fieldInteger| :sup:`Value` - Parameter တွင် အငြိမ် (static) တန်ဖိုးတစ်ခု သတ်မှတ်ပေးနိုင်ပါသည်။ Parameter အမျိုးအစားပေါ် မူတည်ပြီး widget ကိုအသုံးပြုပြီး ဂဏန်းတစ်ခု (``5.0``)၊ စာသားတစ်ခု (``mytext``) ထည့်သွင်းခြင်း၊ QGIS project သို့မဟုတ် folder တစ်ခုမှ ခေါ်ယူထည့်သွင်းထားသည့် layer (များ) ကိုရွေးချယ်ခြင်း၊ စာရင်းတစ်ခုမှ item များကို ရွေးချယ်ခြင်းများကို လုပ်ဆောင်နိုင်ပါသည်။
* |expression| :sup:`Pre-calculated Value` - :ref:`Expression Builder <vector_expressions>` dialog ကိုပွင့်စေပြီး parameter ကိုဖြည့်သွင်းရန် expression တစ်ခုကိုသတ်မှတ်ပေးနိုင်ပါသည်။ အခြား layer ၏စာရင်းအင်းကိန်းဂဏန်းအချို့ဖြင့် model input များကို **variables** အဖြစ်အသုံးပြုနိုင်ပြီး Expression Builder ၏ ရှာဖွေခြင်း (search) dialog ၏အပေါ်ဘက်တွင် စာရင်းပြုစုထားပါသည်။ Algorithm အခွဲ (Child algorithm) ကို စေခိုင်းမလုပ်ဆောင်မီ expression ကို တစ်ကြိမ်အကဲဖြတ်မည်ဖြစ်ပြီး ထို algroithm ကို စေခိုင်းလုပ်ဆောင်စဉ်တွင် အသုံးပြုပါသည်။
* |processingModel| :sup:`Model Input` - Model ကိုပေါင်းထည့်သော input ကို parameter အဖြစ်အသုံးပြုနိုင်ပါသည်။ Click နှိပ်လိုက်သည်နှင့် parameter အတွက်သင့်တော်သော input များ အားလုံးကို စာရင်းပြုစုပေးပါသည်။
* |processingAlgorithm| :sup:`Algorithm Output` - အခြား algorithm မှထွက်လာမည့် output ကို လက်ရှိ algorithm ၏ input တစ်ခုအဖြစ် အသုံးပြုနိုင်ပါသည်။ Model input များအဖြစ် parameter အတွက်သင့်တော်သော input အားလုံးကို စာရင်းပြုစုပေးပါလိမ့်မည်။

* The **output parameter** also has the above options in its drop-down menu:
* **Output parameter** တွင်လည်း ၎င်း၏ drop-down menu ထဲ၌ အထက်တွင်ဖော်ပြခဲ့သော ရွေးချယ်စရာနည်းလမ်းများ ရှိပါသည်-

  * Child algorithm များအတွက် မပြောင်းလဲသော (static) output များကိုထည့်ပေါင်းခြင်း။ ဥပမာ- child algorithm ၏ output တစ်ခုကို ကြိုတင်သတ်မှတ်ထားသော geopackage သို့မဟုတ် postgres layer တစ်ခုတွင်အမြဲတမ်းသိမ်းဆည်းခြင်း။
  * Child algorithm များအတွက် expression ကိုအခြေခံသော output တန်ဖိုးများကို အသုံးပြုခြင်း။ ဥပမာ- လုပ်ဆောင်သောနေ့စွဲကို အသုံးပြုပြီး file အမည်ကိုအလိုအလျှောက်ဖန်တီးပြီး ၎င်း file ထဲတွင် output များကို သိမ်းဆည်းခြင်း။
  * Model input တစ်ခုကို အသုံးပြုခြင်း။ ဥပမာ- Output file တစ်ခုသို့မဟုတ် folder တစ်ခု ကိုသတ်မှတ်ရန် *File/Folder* model input။
  * အခြား algorithm output ကိုအသုံးပြုခြင်း။ ဥပမာ- *Create directory* algorithm (*Modeler tools* မှ) ၏ output။
  * ထပ်ပေါင်း |modelOutput| :sup:`Model Output` နည်းလမ်းတစ်ခုသည် algorithm ၏ output ကို model ထဲတွင် အသုံးပြုနိုင်အောင် လုပ်ဆောင်ပေးပါသည်။ Algorithm မှဖန်တီးပေးသော layer ကို အခြား algorithm တွင် input အဖြစ်သာ အသုံးပြုမည်ဆိုလျှင် ၎င်းစာသား box ကိုတည်းဖြတ်ပြင်ဆင်မှုမလုပ်ပါနှင့်။
  
  အေက်ပါပုံတွင် ``Model Input`` နှင့် ယာယီ output layer အဖြစ်သတ်မှတ်ထားသော input parameter နှစ်မျိုးကို တွေ့မြင်ရမည်ဖြစ်သည်-

  .. figure:: img/models_parameters5.png
     :align: center

     Algorithm Input နှင့် Output parameter များ

Algorithm ကို toolbox မှခေါ်ယူအသုံးပြုသောအခါ မရရှိနိုင်သော :guilabel:`Dependencies` ဟုခေါ်သည့် အခြား parameter တစ်ခုကိုလည်း တွေ့ရမည်ဖြစ်ပါသည်။ Algorithm တစ်ခုကို ယခုလက်ရှိ alogrithm ၏ *parent* အဖြစ် သတ်မှတ်ခြင်းဖြင့် algorithm များကိုစေခိုင်းလုပ်ဆောင်မည့် အစီအစဉ်ကို သတ်မှတ်နိုင်စေရန် ဤ parameter မှလုပ်ဆောင်ပေးပါသည်။ ၎င်းသည် လက်ရှိ algorithm ကိုမလုပ်ဆောင်မီ *parent* algorithm ကိုတွန်းအားပေး စေခိုင်းလုပ်ဆောင်ပါလိမ့်မည်။

ရှေ့တွင်လုပ်ဆောင်ခဲ့သော algorithm ၏ output ကို မိမိ algorithm ၏ input အဖြစ် အသုံးပြုသောအခါ ၎င်းသည် ရှေ့တွင်လုပ်ဆောင်ခဲ့သော algorithm ကို လက်ရှိတစ်ခု၏ parent အဖြစ်အကြွင်းမဲ့သတ်မှတ်ပါသည် (modeler canvas ထဲတွင် သက်ဆိုင်ရာ မြှားကိုနေရာချထည့်သွင်းပေးပါသည်)။ သို့သော် အချို့ကိစ္စများတွင် algorithm တစ်ခုသည် ၎င်းမှထွက်လာသော မည်သည့် output ကိုမှ အသုံးမပြုလျှင်တောင် ၎င်း algorithm သည် အခြားတစ်ခုပေါ်တွင် မှီခိုနေနိုင်ပါသည် (ဥပမာ SQL sentence ကို PostGIS database ပေါ်တွင်စေခိုင်းလုပ်ဆောင်သော algorithm တစ်ခုနှင့် layer တစ်ခုကို ထိုတူညီသော database ထဲသို့ ထည့်သွင်းပေးသောအခြားတစ်ခု)။ ထိုသို့သောအခါမျိုးတွင် *Dependencies* parameter ထဲတွင် ရှေ့တွင်လုပ်ဆောင်ခဲ့သော algorithm ကိုရွေးချယ်ပါ၊ ၎င်းတို့ကို မှန်ကန်သော အစီအစဉ်ဖြင့် စေခိုင်းလုပ်ဆောင်စေပါလိမ့်မည်။

Parameter များအားလုံးကို ဆီလျော်သော တန်ဖိုးများသတ်မှတ်ပြီးသည်နှင့် :guilabel:`OK` ကိုနှိပ်ခြင်းဖြင့် algorithm ကို canvas ထဲတွင် ထည့်သွင်းပေးပါလိမ့်မည်။ ၎င်းသည် algorithm အတွက် input များအဖြစ် အသုံးပြုသော object များကို ထောက်ပံ့ပေးထားသော canvas ထဲရှိ element များ (algorithm များ သို့မဟုတ် input များ) နှင့် ချိတ်ဆက်သွားပါလိမ့်မည်။

|select| :sup:`Select/Move Item` tool ကိုအသုံးပြုပြီး canvas ပေါ်တွင် element များကို ဖိဆွဲရွှေ့ပြီး စိတ်ကြိုက်နေရာချထားနိုင်ပါသည်။ Model ကို ပိုပြီး ရှင်းရှင်းလင်းလင်းဖြစ်စေရန် ဤနည်းလမ်းသည် အသုံးဝင်ပါသည်။ Element များ၏အနားများကို ချဲ့ကားခြင်း၊ ချုံ့ခြင်းဖြင့် ၎င်းတို့၏ အရွယ်အစားကိုလည်း ပြောင်းလဲနိုင်ပါသည်။ Input သို့မဟုတ် algorithm ၏ရှင်းလင်းဖော်ပြချက်သည် ရှည်နေလျှင် ၎င်းသည် အသုံးဝင်ပါသည်။ :menuselection:`View --> Enable snapping` ကိုအမှန်ခြစ် ခြစ်ထားလျှင် item များကိုအရွယ်အစားပြောင်းလဲခြင်းနှင့် နေရာချထားခြင်းများကို virtual grid တွင် တွဲကပ်ထားနိုင်ပြီး အမြင်အရ ကောင်းစွာဖွဲ့စည်းထားသော algorithm ဒီဇိုင်းတစ်ခု ဖြစ်စေပါသည်။ 

Element များအကြား ချိတ်ဆက်မှု (link) များကို အလိုအလျှောက် update ပြုလုပ်ပေးပြီး algorithm တစ်ခုချင်းစီ၏ အပေါ်ဘက်နှင့် အောက်ခြေတွင် ``+`` ခလုတ်ကိုတွေ့နိုင်ပါသည်။ ထိုခလုတ်ကိုနှိပ်လျှင် အမြန်ခြုံငုံကြည့်ရှုနိုင်ရန်အတွက် algorithm ၏ input များနှင့် output များအားလုံးကို စာရင်းပြုစုပေးပါလိမ့်မည်။


.. _figure_model_model:

.. figure:: img/models_model.png
   :align: center

   ပြီးပြည့်စုံသော model တစ်ခု

:menuselection:`Edit --> Add Group Box` tool ကိုအသုံးပြုပြီး canvas တွင် ဖိဆွဲရွှေ့နိုင်သော *box* တစ်ခုကို ထည့်သွင်းနိုင်ပါသည်။ ကြီးမားသော Model များတွင် modeler canvas ထဲ၌ ဆက်စပ် element များကိုအုပ်စုဖွဲ့ရန်နှင့် workflow ကိုရှင်းရှင်းလင်းလင်း ဖြစ်စေရန် ဤ feature သည် အလွန်အသုံးဝင်ပါသည်။ ဥပမာအားဖြင့် အောက်ပါ နမူနာထဲရှိ input များအားလုံးကို အုပ်စုဖွဲ့ပြပါမည်-

.. figure:: img/model_group_box.png
   :align: center

   Model Group Box

Box များ၏အမည်နှင့် အရောင်ကိုပြောင်းလဲနိုင်ပါသည်။ အုပ်စုဖြစ်နေသော box များသည် :menuselection:`View --> Zoom To -->` tool ဖြင့်တွဲဖက်အသုံးပြုသောအခါ အလွန်အသုံးဝင်ပြီး model ၏ သီးသန့်အစိတ်အပိုင်းတစ်ခုအထိ zoom ဆွဲကြည့်နိုင်ပါသည်။ Mouse ၏ဘီးကို အသုံးပြုပြီးလည်း zoom အချုံ့၊ အချဲ့လုပ်ဆောင်နိုင်ပါသည်။

Input များ၏ အစီအစဉ် (order) နှင့် အဓိက dialog ထဲတွင် ၎င်းတို့ကို မည်သို့စာရင်းပြုစုထားသည်ကို ပြောင်းလဲချင်သောအခါများ ရှိနိုင်ပါလိမ့်မည်။ ``Input`` panel ၏အောက်ခြေတွင် ``Reorder Model Inputs...`` ခလုတ်ရှိပါသည်။ ၎င်းကိုနှိပ်လျှင် input များ၏ အစီအစဉ်ကို ပြောင်းလဲနိုင်သော dialog အသစ်တစ်ခုပွင့်လာပါမည်-

.. figure:: img/model_reorder_inputs.png
   :align: center

   Model input များ၏အစီအစဉ်ကို ပြန်လည်သတ်မှတ်ခြင်း

ရလာဒ်များကို project ထဲသို့ထည့်သွင်းသောအခါ model မှ output များကို အသုံးပြုရမည့် သီးသန့်အစီအစဉ်တစ်ခုကိုလည်း သတ်မှတ်ပေးနိုင်ပါသည်။ ထိုသို့သတ်မှတ်ခြင်းသည် vector layer output ကို raster layer output ပေါ်တွင် ထားခြင်း သို့မဟုတ် point layer ကို polygon layer ပေါ်တွင်ထားခြင်းကဲ့သို့သော model တစ်ခုကိုလုပ်ဆောင်သောအခါ layer များကို canvas ထဲတွင် ယုတ္တိရှိရှိ စီစဉ်ခြင်းဖြစ်အောင် model ဖန်တီးသူကို အထောက်အကူပြုပါသည်။ Model ဖန်တီးသူသည် အုပ်စုအသစ်ဖန်တီးခြင်း သို့မဟုတ် ရှိနေပြီးသားအုပ်စုထဲသို့ထည့်သွင်းခြင်းဖြင့် layer ဖွဲ့စည်းပုံအတွင်း output များကို အလိုအလျှောက်အုပ်စုဖွဲ့စေရန် output များအတွက် "အုပ်စုအမည်" ကိုလည်း သတ်မှတ်ပေးနိုင်ပါသည်။ ``Model`` menu ထဲတွင် ``Reorder Output Layers...`` ရှိပြီး ၎င်းကိုနှိပ်လျှင် output layer များ၏ အစီအစဉ်ကို ပြောင်းလဲပေးနိုင်သော dialog အသစ်တစ်ခုပေါ်လာမည်ဖြစ်သည်-

.. figure:: img/model_reorder_output_layers.png
   :align: center

   Output layer များ၏အစီအစဉ်ကို ပြန်လည်သတ်မှတ်ခြင်း

Modeler ထဲတွင်ရှိသော input များ သို့မဟုတ် algorithm များတွင် comment (မှတ်ချက်) များလည်း ထည့်ရေးနိုင်ပါသည်။ ၎င်းကို Item ၏ :guilabel:`Comment` tab တွင်ဝင်ရောက်ပြီးလုပ်နိုင်သလို right-click နှိပ်ပြီးလည်း လုပ်ဆောင်နိုင်ပါသည်။ ထို tab ထဲမှာပင် model comment တစ်ခုချင်းစီအတွက် အရောင်ကို စိတ်ကြိုက်သတ်မှတ်ပေးနိုင်ပါသည်။ Comment များကို modeler canvas ထဲတွင်သာ မြင်နိုင်ပြီး နောက်ဆုံးရလာမည့် algorithm dialog ထဲတွင် မြင်နိုင်မည်မဟုတ်ပါ။ :menuselection:`View --> Show Comments` ကိုပိတ်ထားပြီး ၎င်းတို့ကို ဖျောက်ထားနိုင်ပါသည်။

|start| :sup:`Run model` ခလုတ်ကိုနှိပ်ပြီး algorithm ကိုမည်သည့်အချိန်တွင်မဆို လုပ်ဆောင်နိုင်ပါသည်။ Model တစ်ခုကိုစေခိုင်းလုပ်ဆောင်ရန် အတွက် editor ကိုအသုံးပြုသောအခါ မူရင်းမဟုတ်သော (non-default) မည်သည့်တန်ဖိုးများမဆို input များထဲတွင် သိမ်းဆည်းပေးမည်ဖြစ်ပါသည်။ ဆိုလိုသည်မှာ model ကို နောင်တချိန်၌ editor မှ  စေခိုင်းလုပ်ဆောင်ခြင်းသည် နောက်ပိုင်းလုပ်ဆောင်မည့် လုပ်ငန်းများတွင် ထိုတန်ဖိုးများကို dialog ထဲတွင် ကြိုတင်ထည့်သွင်းထားပေးမည်ဖြစ်သည်။

Algorithm ကို toolbox မှအသုံးပြုရန်အတွက် toolbox ၏ မာတိကာကို refresh လုပ်စေရန်အတွက် ၎င်းကိုအရင်သိမ်းဆည်းထားပြီး modeler dialog ကိုပိတ်ပေးရပါမည်။


Documenting your model (Model ကိုမှတ်တမ်းပြုစုရေးသားခြင်း)
...........................................................

Model ကိုမှတ်တမ်းပြုစုရေးသားထားရန် လိုအပ်ပြီး ၎င်းကို modeler ထဲတွင်လုပ်ဆောင်နိုင်ပါသည်။ |editHelpContent|:sup:`Edit model help` ခလုတ်ကိုနှိပ်ပါ၊ ပုံထဲတွင်ဖော်ပြထားသကဲ့သို့ dialog တစ်ခုပွင့်လာပါမည်။

.. _figure_help_edition:

.. figure:: img/help_edition.png
   :align: center

   Editing Help (တည်းဖြတ်ပြင်ဆင်ခြင်း အကူအညီ)

ညာဘက်ခြမ်းတွင် Model ၏အထွေထွေရှင်းလင်းဖော်ပြချက် သို့မဟုတ် model ဖန်တီးထားသူအကြောင်းကဲ့သို့သော အခြားသောအချက်အလက်များနှင့်အတူ algorithm ၏ input parameter များနှင့် output များ၏ ရှင်းလင်းဖော်ပြချက်ကိုအသုံးပြုပြီး ဖန်တီးထားသော ရိုးရှင်းသည့် HTML စာမျက်နှာ တစ်ခုရှိပါသည်။ Model အသုံးပြုနည်းကိုရှင်းပြသော ကိုယ်ပိုင်ဥပမာများကိုထည့်သွင်းနိုင်သော ဥပမာ section တစ်ခုလည်းရှိပါသည်။ အကူအညီ editor ကိုပထမဆုံးအကြိမ် ဖွင့်သောအခါ ထိုရှင်းလင်းဖော်ပြချက်များအားလုံးသည် ဗလာဖြစ်နေပါမည်၊ သို့သော် dialog ၏ဘယ်ဘက်တွင်ရှိသော element များကိုအသုံးပြုပြီး ၎င်းတို့ကို တည်းဖြတ်ပြင်ဆင်နိုင်ပါသည်။ အပေါ်ဘက်တွင်ရှိသော element ကိုရွေးချယ်ပါ၊ ထို့နောက် အောက်တွင်ရှိသော text box ထဲတွင် ၎င်း၏ရှင်းလင်းဖော်ပြချက်ကို ရေးသားပါ။

Model အကူအညီကို model ၏အစိတ်အပိုင်းတစ်ခုအဖြစ် သိမ်းဆည်းထားပေးမည်ဖြစ်သည်။


Saving and loading models (Model များကိုသိမ်းဆည်းခြင်းနှင့် ခေါ်ယူထည့်သွင်းခြင်း)
----------------------------------------------------------------------------------

Saving models (Model များကိုသိမ်းဆည်းခြင်း)
............................................

ယခုလက်ရှိလုပ်ဆောင်နေသော model ကိုသိမ်းဆည်းရန်အတွက် |fileSave|:sup:`Save model` ခလုတ်ကိုနှိပ်ပြီး ရှေ့တွင်သိမ်းဆည်းခဲ့သော model ကိုဖွင့်ရန်အတွက် |fileOpen|:sup:`Open Model` ခလုတ်ကိုနှိပ်ပါ။ Model များကို :file:`.model3` extension ဖြင့်သိမ်းဆည်းပါသည်။ Model ကို modeler window မှသိမ်းဆည်းပြီးသွားလျှင် သိမ်းဆည်းမည့် file အမည်ကို ထပ်ထည့်ခိုင်းမည်မဟုတ်ပါ။ Model နှင့်ဆက်စပ်သော file တစ်ခုရှိနေပြီးသားဖြစ်သောကြောင့် နောက်ပိုင်းသိမ်းဆည်းမှုများအတွက် ထို file ကိုအသုံးပြုမည်ဖြစ်ပါသည်။

Model တစ်ခုကိုမသိမ်းဆည်းမီ window ၏အပေါ်ဘက်ရှိ text box များထဲတွင် ၎င်းအတွက် အမည်တစ်ခု သို့မဟုတ် အုပ်စုတစ်ခု ထည့်ပေးရပါမည်။

:file:`Models` folder (model ကိုသိမ်းဆည်းရန်အတွက် file အမည်မေးသော မူရင်း folder) ထဲတွင်သိမ်းဆည်းခဲ့သော model များသည် သက်ဆိုင်ရာ အခွဲများထဲရှိ toolbox ထဲတွင်ပေါ်နေပါလိမ့်မည်။ Toolbox ကိုမှီငြမ်းအသုံးပြုသောအခါ :file:`.model3` extension ဖြင့် file များအတွက် :file:`models` folder တွင်ရှာဖွေပြီး ၎င်းတို့ပါဝင်သော model များကိုခေါ်ယူထည့်သွင်းပါသည်။ Model တစ်ခုသည် ၎င်းကိုယ်တိုင်ပင် algorithm ဖြစ်သောကြောင့် အခြား algorithm ကဲ့သို့ ၎င်းကို toolbox ထဲသို့ထည့်သွင်းနိုင်ပါသည်။

|addToProject|:sup:`Save model in project` ခလုတ်ကိုအသုံးပြုပြီး model များကို project file ထဲတွင် သိမ်းဆည်းနိုင်ပါသည်။ ဤနည်းလမ်းကိုအသုံးပြုပြီး သိမ်းဆည်းခဲ့သော model များကို ကွန်ပျူတာထဲတွင် :file:`.model3` file များအဖြစ် ရေးသားသိမ်းဆည်းမည်မဟုတ်ပဲ project file ထဲတွင် ထည့်မြှုပ်ထားပါမည်။

Project model များကို toolbox ၏ |qgsProjectFile|:guilabel:`Project models` menu နှင့် :menuselection:`Project --> Models` menu item ထဲတွင်တွေ့ရပါမည်။

Models folder ကို :guilabel:`Modeler` အုပ်စုအောက်ရှိ Processing ပြင်ဆင်သတ်မှတ်ခြင်း dialog မှ သတ်မှတ်ပေးနိင်ပါသည်။

:file:`Models` folder မှခေါ်ယူအသုံးပြုသော model များသည် toolbox မှာတင်မကပဲ modeler window ၏ :guilabel:`Algorithms` tab ထဲရှိ algorithm ဖွဲ့စည်းပုံထဲတွင်လည်း ပေါ်နေပါသည်။ အခြား algorithm များကဲ့သို့ပင် model တစ်ခုကို ပိုကြီးမားသော model တစ်ခု၏ အစိတ်အပိုင်းတစ်ခုအဖြစ် ပူးပေါင်းလုပ်ဆောင်နိုင်သည်ဟု ဆိုလိုပါသည်။

Model များသည် :ref:`Browser <browser_panel>` panel တွင်ပေါ်နေမည်ဖြစ်ပြီး ထိုနေရာမှ စေခိုင်းလုပ်ဆောင်နိုင်ပါသည်။

Exporting a model as a Python script (Model တစ်ခုကို Python script တစ်ခုအဖြစ်ထုတ်ယူခြင်း)
..........................................................................................

နောက်အခန်းတွင်တွေ့ရမည့်အတိုင်း Processing algorithm များကို QGIS Python console မှ ခေါ်ယူအသုံးပြုနိုင်ပြီး Python ကိုအသုံးပြုပြီး Processing algorithm အသစ်များကို ဖန်တီးနိုင်ပါသည်။ ထိုကဲ့သို့သော Python script ကို အမြန်ဖန်တီးရန်နည်းလမ်းမှာ model တစ်ခုဖန်တီးပြီး ၎င်းကို Python file အဖြစ်ထုတ်ယူခြင်း ဖြစ်ပါသည်။

ထို့ကဲ့သို့လုပ်ဆောင်ရန် modeler canvas ထဲရှိ |saveAsPython|:sup:`Export as Script Algorithm...` ကိုနှိပ်ပါ သို့မဟုတ် Processing Toolbox ထဲရှိ model ၏အမည်ပေါ်တွင် right click နှိပ်ပြီး |saveAsPython|:sup:`Export Model as Python Algorithm...` ကိုရွေးချယ်ပါ။

Exporting a model as an image, PDF or SVG (Model တစ်ခုကို ဓာတ်ပုံ၊ PDF သို့မဟုတ် SVG အဖြစ်ထုတ်ယူခြင်း)
.......................................................................................................

|saveMapAsImage|:sup:`Export as image`၊ |saveAsPDF|:sup:`Export as PDF` သို့မဟုတ် |saveAsSVG|:sup:`Export as SVG` ကိုနှိပ်ပြီး model တစ်ခုကို ဓာတ်ပုံ၊ SVG သို့မဟုတ် PDF အဖြစ်လည်းထုတ်ယူနိုင်ပါသည် (သရုပ်ဖော်ရန်အတွက်)


Editing a model (Model တစ်ခုကိုတည်းဖြတ်ပြင်ဆင်ခြင်း)
-----------------------------------------------------

Workflow နှင့်၊ algorithm များနှင့် model ကိုသတ်မှတ်ပေးသော input များကြား ချိတ်ဆက်မှုများကို ပြန်လည်သတ်မှတ်ခြင်းဖြင့် လက်ရှိဖန်တီးနေသော model ကိုတည်းဖြတ်ပြင်ဆင်နိုင်ပါသည်။

Canvas ထဲရှိ algorithm တစ်ခု ပေါ်တွင် right-click နှိပ်လျှင် အောက်တွင်ဖော်ပြထားသလို menu တစ်ခုပေါ်လာပါမည် -

.. _figure_model_right_click:

.. figure:: img/modeler_right_click.png
   :align: center

   Modeler Right Click နှိပ်ခြင်း

:guilabel:`Remove` ကိုအသုံးပြုလျှင် ရွေးချယ်ထားသော algorithm ကိုဖယ်ထုတ်ပေးပါမည်။ Algorithm တစ်ခုကိုဖယ်ထုတ်ချင်လျှင် ၎င်းကိုမှီခိုပြီး လုပ်ဆောင်နေသော အခြား algorithm များမရှိမှသာ ဖယ်ထုတ်နိုင်ပါသည်။ ဆိုလိုသည်မှာ algorithm မှ output ကို တခြားတစ်ခုတွင် input အနေဖြင့် အသုံးမပြုမှသာ ဖယ်ထုတ်နိုင်ပါသည်။ အကယ်၍ အခြား algorithm များကမှီခိုပြီးလုပ်ဆောင်နေသော algorithm တစ်ခုကို ဖယ်ထုတ်မိလျှင် အောက်တွင်ပြထားသကဲ့သို့ သတိပေးစာသားတစ်ခု ပေါ်လာပါမည်-

.. _figure_cannot_delete_alg:

.. figure:: img/cannot_delete_alg.png
   :align: center

   Algorithm ကိုမဖျက်နိုင်ခြင်း

:guilabel:`Edit...` ကိုအသုံးပြုလျှင် algorithm ၏ parameter dialog တစ်ခုပေါ်လာပြီး input များနှင့် parameter တန်ဖိုးများကိုပြောင်းလဲနိုင်ပါသည်။ Model ထဲတွင်ရှိသော input element များအားလုံးတော့ အသုံးပြုနိုင်သည့် input များအဖြစ် ပေါ်နေမည် မဟုတ်ပါ။ Model ဖြင့်သတ်မှတ်ပေးထားသော workflow ထဲရှိ ပိုမိုအဆင့်မြင့်သော အဆင့်၌ ဖန်တီးထားသော layer သို့မဟုတ် တန်ဖိုးများသည် အချင်းချင်းပြန်လည်မှီခိုမှုများဖြစ်နေလျှင် အသုံးပြုနိုင်မည်မဟုတ်ပါ။

တန်ဖိုးအသစ်များကိုရွေးချယ်ပြီး :guilabel:`OK` ကိုနှိပ်ပါ။ Model element များအကြားချိတ်ဆက်မှုများသည် modeler canvas ထဲတွင် အခြေအနေအရ ပြောင်းလဲသွားပါမည်။

:guilabel:`Add comment...` ကိုအသုံးပြုလျှင် လုပ်ဆောင်မှုကို ပိုမိုကောင်းမွန်အောင်ရှင်းလင်းဖော်ပြနိုင်ရန်အတွက် algorithm တွင် comment ထည့်ပေါင်းရေးသားနိုင်ပါသည်။

Model တစ်ခု၏ algorithm အချို့ကို ပိတ်ထား (Deactivate) ပြီး တစ်စိတ်တစ်ပိုင်းပဲ စေခိုင်းအသုံးပြုနိုင်ပါသည်။ ထို့သို့လုပ်ဆောင်ရန်အတွက် Algorithm element ပေါ်တွင် right-click နှိပ်သောအခါ ပေါ်လာသည့် menu တွင် :guilabel:`Deactivate` ကိုရွေးချယ်ပါ။ ရွေးချယ်ထားသော algorithm နှင့် ၎င်းကိုမှီခိုနေသော model ထဲရှိအခြားအရာများအားလုံး အရောင်မှိန်သွားပြီး model ၏အစိတ်အပိုင်းတစ်ခုအဖြစ် လုပ်ဆောင်ပေးတော့မည် မဟုတ်ပါ။

.. _figure_cannot_model_deactivate:

.. figure:: img/deactivated.png
   :align: center

   ပိတ်ထားသော algorithm များဖြင့် model

ပိတ်ထားသော algorithm တစ်ခုပေါ်တွင် right-click နှိပ်သောအခါ ပြန်လည်အသုံးပြုနိုင်အောင် (reactive) လုပ်ဆောင်ပေးသော :guilabel:`Activate` menu ကိုတွေ့ရမည်ဖြစ်ပါသည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |addToProject| image:: /static/common/mAddToProject.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |deleteSelected| image:: /static/common/mActionDeleteSelected.png
   :width: 1.5em
.. |editCopy| image:: /static/common/mActionEditCopy.png
   :width: 1.5em
.. |editCut| image:: /static/common/mActionEditCut.png
   :width: 1.5em
.. |editHelpContent| image:: /static/common/mActionEditHelpContent.png
   :width: 1.5em
.. |editPaste| image:: /static/common/mActionEditPaste.png
   :width: 1.5em
.. |expression| image:: /static/common/mIconExpression.png
   :width: 1.5em
.. |fieldInteger| image:: /static/common/mIconFieldInteger.png
   :width: 1.5em
.. |fileOpen| image:: /static/common/mActionFileOpen.png
   :width: 1.5em
.. |fileSave| image:: /static/common/mActionFileSave.png
   :width: 1.5em
.. |fileSaveAs| image:: /static/common/mActionFileSaveAs.png
   :width: 1.5em
.. |helpContents| image:: /static/common/mActionHelpContents.png
   :width: 1.5em
.. |modelOutput| image:: /static/common/mIconModelOutput.png
   :width: 1.5em
.. |play| image:: /static/common/mActionPlay.png
   :width: 1.5em
.. |processingAlgorithm| image:: /static/common/processingAlgorithm.png
   :width: 1.5em
.. |processingModel| image:: /static/common/processingModel.png
   :width: 1.5em
.. |qgsProjectFile| image:: /static/common/mIconQgsProjectFile.png
   :width: 1.5em
.. |redo| image:: /static/common/mActionRedo.png
   :width: 1.5em
.. |saveAsPDF| image:: /static/common/mActionSaveAsPDF.png
   :width: 1.5em
.. |saveAsPython| image:: /static/common/mActionSaveAsPython.png
   :width: 1.5em
.. |saveAsSVG| image:: /static/common/mActionSaveAsSVG.png
   :width: 1.5em
.. |saveMapAsImage| image:: /static/common/mActionSaveMapAsImage.png
   :width: 1.5em
.. |select| image:: /static/common/mActionSelect.png
   :width: 1.5em
.. |selectAll| image:: /static/common/mActionSelectAll.png
   :width: 1.5em
.. |start| image:: /static/common/mActionStart.png
   :width: 1.5em
.. |success| image:: /static/common/mIconSuccess.png
   :width: 1em
.. |unchecked| image:: /static/common/unchecked.png
   :width: 1.3em
.. |undo| image:: /static/common/mActionUndo.png
   :width: 1.5em
.. |zoomActual| image:: /static/common/mActionZoomActual.png
   :width: 1.5em
.. |zoomFullExtent| image:: /static/common/mActionZoomFullExtent.png
   :width: 1.5em
.. |zoomIn| image:: /static/common/mActionZoomIn.png
   :width: 1.5em
.. |zoomOut| image:: /static/common/mActionZoomOut.png
   :width: 1.5em
