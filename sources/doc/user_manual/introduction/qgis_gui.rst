﻿.. Purpose: This chapter aims to describe only the interface of the default
.. QGIS interface. Details should be written in other parts with a link toward it.


.. _`label_qgismainwindow`:


**************************
QGIS GUI (QGIS မျက်နှာပြင်)
**************************

.. only:: html

   .. contents::
      :local:


.. index::
   single: Main window

QGIS graphical user interface (QGIS အသုံးပြုသူမှ မြင်ရသည့်မျက်နှာပြင် - GUI) ကို ပုံတွင်ဖော်ပြထားသည့်အတိုင်း တွေ့ရမည်ဖြစ်ပြီး အဝါရောင်စက်ဝိုင်းများနှင့် ဖော်ပြထားသော နံပါတ် ၁ မှ ၅ သည် QGIS GUI ၏ အရေးကြီးသော အစိတ်အပိုင်းများဖြစ်ပါသည်။ ၎င်းတို့ကို အောက်တွင် ဆက်လက်ဆွေးနွေးသွားပါမည်။

.. _figure_startup:

.. figure:: img/startup.png
   :align: center


   Alaska sample data ကိုအသုံးပြုထားသည့် QGIS GUI

.. note:: ကွန်ပျူတာတွင် တွေ့မြင်ရသည့်မျက်နှာပြင်အပြင်အဆင် (ခေါင်းစဉ် bar၊ အစရှိသည်) သည် ကွန်ပျူတာလုပ်ဆောင်သည့်စနစ် (operating system) နှင့် window manager ပေါ်မူတည်၍ အမျိုးမျိုးကွဲပြားနိုင်ပါသည်။

အဓိက QGIS GUI (:numref:`figure_startup`) တွင် အပိုင်း (၅)ပိုင်း ပါဝင်ပါသည်။ ၎င်းတို့မှာ- 

#. :ref:`Menu Bar (Menu များကိုဖော်ပြသည့်ဘား) <label_menubar>`
#. :ref:`Toolbars (Tool ဘား) <sec_panels_and_toolbars>`
#. :ref:`Panels (Panel များ) <sec_panels_and_toolbars>`
#. :ref:`Map View (မြေပုံမြင်ကွင်း) <label_mapview>`
#. :ref:`Status Bar (အခြေအနေပြဘား) <label_statusbar>`

ဖော်ပြပါ အကြောင်းအရာများ၏ အသေးစိတ်ရှင်းလင်းချက်များအတွက် အောက်တွင်ဆက်ကြည့်ပါ။ 

.. index:: Menu
.. _label_menubar:

Menu Bar (Menu များကိုဖော်ပြသည့် bar)
======================================

Menu bar သည် QGIS ၏ လုပ်ဆောင်ချက်များကို Standard hierarchical menu (စံအဆင့်ဆင့် လုပ်ဆောင်ချက်) များအတိုင်း ဝင်ရောက်လုပ်ဆောင်နိုင်ပါသည်။ Menu များ၊ ၎င်းတွင် ပါဝင်သည့် ရွေးချယ်စရာများ၊ ဆက်စပ် icon များနှင့် ကီးဘုတ်အတိုကောက်များ (Keyboard shortcut) ကို အောက်တွင်ဖော်ပြထားပါသည်။ Keyboard shortcut များကို :menuselection:`Settings --> Keyboard Shortcuts` တွင် ပြန်လည်ပြင်ဆင်သတ်မှတ်နိုင်ပါသည်။

Menu option (ရွေးချယ်မှု) အများစုတွင် ၎င်းနှင့်ဆက်စပ်လျက်ရှိသော tool တစ်ခုစီရှိပြီး အဆိုပါ tool တစ်ခုချင်းစီသည်လည်း Menu option များဖြင့် အပြန်အလှန် ဆက်စပ်လျက်ရှိပါသည်။ သို့သော် Menu များသည် toolbar များကဲ့သို့ အတိအကျ စီစဉ်ဖွဲ့စည်းထားခြင်းမရှိပါ။ Toolbar ထဲရှိ Menu option များ၏ တည်နေရာကို အောက်ဖော်ပြပါဇယားတွင်ပြသထားပါသည်။ Plugin (လုပ်ဆောင်ချက်အသစ်များကို ဆောင်ရွက်နိုင်ရန် ထပ်မံထည့်သွင်းထားသည့်အရာ) များအသုံးပြုခြင်းဖြင့် option အသစ်များကို menu ထဲသို့ ထပ်ထည့်နိုင်ပါသည်။ Tool နှင့် Toolbar များအကြောင်း ပိုမိုသိရှိရန် :ref:`label_toolbars` တွင် ကြည့်ရှုနိုင်ပါသည်။

.. note:: QGIS သည် cross-platform application (Platform အားလုံးတွင် အသုံးပြု၍ရနိုင်သော application) တစ်ခုဖြစ်ပါသည်။ ယေဘုယျအားဖြင့် Tool များကို platform အားလုံးတွင် အသုံးပြုနိုင်သော်လည်း မိမိကွန်ပျူတာ၏ operating system ပေါ်မူတည်၍ Tool များသည် menu အမျိုးမျိုးတွင် တည်ရှိနေနိုင်ပါသည်။ အောက်ဖော်ပြပါစာရင်းတွင် အသုံးအများဆုံး Tool များ၏ တည်နေရာများကို ဖော်ပြထားပါသည်။

.. index:: Project

Project (ပရောဂျက်)
-------------------

:menuselection:`Project` menu သည် :ref:`project files <sec_projects>` များကို ရယူသုံးစွဲရန်နှင့်ပြန်ထွက်ရန်အတွက် အသုံးပြုနိုင်ပြီး ၎င်းတွင် အောက်ပါလုပ်ဆောင်ချက်များအတွက် Tool များ ပါဝင်ပါသည်- 

* :guilabel:`New` project file ကိုနှိပ်၍ Project အသစ်တစ်ခုကို ဖန်တီးနိုင်ပြီး အခြား project file တစ်ခုကိုလည်း template (နမူနာပုံစံ) အဖြစ် အသုံးပြု၍ ဖွင့်နိုင်ပါသည်။ (Template ပုံစံ ပြင်ဆင်မှုများကို :ref:`Project files options <projectfiles_options>` တွင် ဝင်ရောက်ကြည့်ရှုနိုင်ပါသည်။)
* :guilabel:`Open...`  ကို အသုံးပြု၍ File၊ GeoPackage၊  PostgreSQL နှင့် Oracle database များမှ project တစ်ခုကို ဖွင့်နိုင်ပါသည်။ 
* :guilabel:`Close` ကို အသုံးပြု၍ Project တစ်ခုကို ပိတ်ခြင်း သို့မဟုတ် နောက်ဆုံးသိမ်းဆည်းထားခဲ့သည့် အခြေအနေသို့ရောက်စေခြင်း ပြုလုပ်နိုင်ပါသည်။ 
* Project တစ်ခုကို :file:`.qgs` သို့မဟုတ် :file:`.qgz` ဖိုင်အမျိုးအစားများအဖြစ်သိမ်းဆည်းပြီး file တစ်ခုအဖြစ်လည်းကောင်း၊ GeoPackage၊ PostgreSQL သို့မဟုတ် Oracle database အတွင်းတွင်လည်းကောင်း :guilabel:`Save` ကိုအသုံးပြု၍ သိမ်းဆည်းနိုင်ပါသည်။ 
* Map canvas (မြေပုံ မြင်ကွင်း) ကို ဖိုင်ပုံစံအမျိုးမျိူးအဖြစ်သို့ ပြောင်း၍ထုတ်နိုင်ပြီး ပိုမိုရှုပ်ထွေးသော ရလာဒ်(output)များအတွက် :ref:`print layout <label_printlayout>` ကို အသုံးပြုနိုင်ပါသည်။
* Geometry editing (ဂျီဩမေတြီ ပြုပြင်မှုများ) လုပ်ဆောင်ရန်အတွက် project properties (ပရောဂျက်၏ဂုဏ်သတ္တိများ) နှင့် snapping option (အနီးအနားရှိအရာများနှင့် ဆွဲကပ်ခြင်းဆိုင်ရာ ရွေးချယ်စရာများ) များကို သတ်မှတ်နိုင်ပါသည်။ 


.. list-table:: Project menu တွင် ပါဝင်သည့် item များ
   :header-rows: 1
   :widths: 40 20 10 30


   * - Menu ရွေးချယ်စရာများ
     - ဖြတ်လမ်းနည်း
     - Toolbar
     - အကိုးအကား
   * - |fileNew| :guilabel:`New`
     - :kbd:`Ctrl+N`
     - :guilabel:`Project`
     - :ref:`sec_projects`
   * - :menuselection:`New from template -->`
     -
     -
     - :ref:`sec_projects`
   * - |fileOpen| :guilabel:`Open...`
     - :kbd:`Ctrl+O`
     - :guilabel:`Project`
     - :ref:`sec_projects`
   * - :menuselection:`Open from -->`
     -
     -
     - :ref:`sec_projects`
   * - :menuselection:`--> GeoPackage...`
     -
     -
     - :ref:`sec_projects`
   * - :menuselection:`--> PostgreSQL...`
     -
     -
     - :ref:`sec_projects`
   * - :menuselection:`--> Oracle...`
     -
     -
     - :ref:`sec_projects`
   * - :menuselection:`Open Recent -->`
     - :kbd:`Alt+J` + :kbd:`R`
     -
     - :ref:`sec_projects`
   * - :guilabel:`Close`
     -
     -
     - :ref:`sec_projects`
   * - |fileSave| :guilabel:`Save`
     - :kbd:`Ctrl+S`
     - :guilabel:`Project`
     - :ref:`sec_projects`
   * - |fileSaveAs| :guilabel:`Save As...`
     - :kbd:`Ctrl+Shift+S`
     - :guilabel:`Project`
     - :ref:`sec_projects`
   * - :menuselection:`Save to -->`
     -
     -
     - :ref:`sec_projects`
   * - :menuselection:`--> Templates...`
     -
     -
     - :ref:`sec_projects`
   * - :menuselection:`--> GeoPackage...`
     -
     -
     - :ref:`sec_projects`
   * - :menuselection:`--> PostgreSQL...`
     -
     -
     - :ref:`sec_projects`
   * - :guilabel:`Revert...`
     -
     -
     -
   * - |projectProperties| :guilabel:`Properties...`
     - :kbd:`Ctrl+Shift+P`
     -
     - :ref:`project_properties`
   * - :guilabel:`Snapping Options...`
     -
     -
     - :ref:`snapping_options`
   * - :menuselection:`Import/Export -->`
     -
     -
     -
   * - :menuselection:`-->` |saveMapAsImage|
       :guilabel:`Export Map to Image...`
     -
     -
     - :ref:`exportingmapcanvas`
   * - :menuselection:`-->` |saveAsPDF|
       :guilabel:`Export Map to PDF...`
     -
     -
     - :ref:`exportingmapcanvas`
   * - :menuselection:`--> Export Project to DXF...`
     -
     -
     - :ref:`create_dxf_files`
   * - :menuselection:`--> Import Layers from DWG/DXF...`
     -
     -
     - :ref:`import_dxfdwg`
   * - |newLayout| :guilabel:`New Print Layout...`
     - :kbd:`Ctrl+P`
     - :guilabel:`Project`
     - :ref:`label_printlayout`
   * - |newReport| :guilabel:`New Report...`
     -
     -
     - :ref:`create-reports`
   * - |layoutManager| :guilabel:`Layout Manager...`
     -
     - :guilabel:`Project`
     - :ref:`label_printlayout`
   * - :menuselection:`Layouts -->`
     -
     -
     - :ref:`label_printlayout`
   * - :menuselection:`Models -->`
     -
     -
     - :ref:`processing.modeler`
   * - |fileExit| :guilabel:`Exit QGIS`
     - :kbd:`Ctrl+Q`
     -
     -


|osx| macOS တွင် :guilabel:`Exit QGIS` command သည် :menuselection:`QGIS --> Quit QGIS` (:kbd:`Cmd+Q`) နှင့်တူညီပါသည်။

Edit (တည်းဖြတ်ပြင်ဆင်ခြင်း)
----------------------------

:menuselection:`Edit` menu တွင် layer attribute (Layer ၏အချက်အလက်) များ သို့မဟုတ် ဂျီဩမေတြီများကို ပြင်ဆင်ရန် လိုအပ်သော အခြေခံအကျဆုံး tool များပါရှိပြီး :menuselection:`Edit` menu options ကိုအသုံးပြုရန် |toggleEditing| :sup:`Toggle editing` ကို နှိပ်ခြင်းအားဖြင့် editing mode (တည်းဖြတ်ပြင်ဆင်ခြင်း mode) ကို ဖွင့်နိုင်ပါသည်။ (အသေးစိတ်သိရှိလိုပါက :ref:`editingvector` တွင်ကြည့်ရှုနိုင်ပါသည်။)

.. list-table:: Edit menu တွင် ပါဝင်သည့် item များ
   :header-rows: 1
   :widths: 45 18 13 24


   * - Menu ရွေးချယ်စရာများ
     - ဖြတ်လမ်းနည်း
     - Toolbar
     - အကိုးအကား
   * - |undo| :guilabel:`Undo`
     - :kbd:`Ctrl+Z`
     - :guilabel:`Digitizing`
     - :ref:`undoredo_edits`
   * - |redo| :guilabel:`Redo`
     - :kbd:`Ctrl+Shift+Z`
     - :guilabel:`Digitizing`
     - :ref:`undoredo_edits`
   * - |editCut| :guilabel:`Cut Features`
     - :kbd:`Ctrl+X`
     - :guilabel:`Digitizing`
     - :ref:`clipboard_feature`
   * - |editCopy| :guilabel:`Copy Features`
     - :kbd:`Ctrl+C`
     - :guilabel:`Digitizing`
     - :ref:`clipboard_feature`
   * - |editPaste| :guilabel:`Paste Features`
     - :kbd:`Ctrl+V`
     - :guilabel:`Digitizing`
     - :ref:`clipboard_feature`
   * - :menuselection:`Paste Features as -->`
     -
     -
     - :ref:`sec_attribute_table`
   * - :menuselection:`--> New Vector Layer...`
     -
     -
     - :ref:`sec_attribute_table`
   * - :menuselection:`--> Temporary Scratch Layer...`
     - :kbd:`Ctrl+Alt+V`
     -
     - :ref:`sec_attribute_table`
   * - |deleteSelectedFeatures| :guilabel:`Delete Selected`
     -
     - :guilabel:`Digitizing`
     - :ref:`delete_feature`
   * - :menuselection:`Select -->`
     -
     -
     - :ref:`sec_selection`
   * - :menuselection:`-->`
       |selectRectangle| :guilabel:`Select Feature(s)`
     -
     - :guilabel:`Selection`
     - :ref:`sec_selection`
   * - :menuselection:`-->`
       |selectPolygon| :guilabel:`Select Features by Polygon`
     -
     - :guilabel:`Selection`
     - :ref:`sec_selection`
   * - :menuselection:`-->`
       |selectFreehand| :guilabel:`Select Features by Freehand`
     -
     - :guilabel:`Selection`
     - :ref:`sec_selection`
   * - :menuselection:`-->`
       |selectRadius| :guilabel:`Select Features by Radius`
     -
     - :guilabel:`Selection`
     - :ref:`sec_selection`
   * - :menuselection:`-->`
       |formSelect| :guilabel:`Select Features by Value...`
     - :kbd:`F3`
     - :guilabel:`Selection`
     - :ref:`sec_selection`
   * - :menuselection:`-->` |expressionSelect|
       :guilabel:`Select Features by Expression...`
     - :kbd:`Ctrl+F3`
     - :guilabel:`Selection`
     - :ref:`sec_selection`
   * - :menuselection:`-->`
       |deselectAll| :guilabel:`Deselect Features from All Layers`
     - :kbd:`Ctrl+Alt+A`
     - :guilabel:`Selection`
     - :ref:`sec_selection`
   * - :menuselection:`-->`
       |deselectActiveLayer| :guilabel:`Deselect Features from the Current Active Layer`
     - :kbd:`Ctrl+Shift+A`
     - :guilabel:`Selection`
     - :ref:`sec_selection`
   * - :menuselection:`--> Reselect Features`
     -
     -
     - :ref:`sec_selection`
   * - :menuselection:`-->`
       |selectAll| :guilabel:`Select All Features`
     - :kbd:`Ctrl+A`
     - :guilabel:`Selection`
     - :ref:`sec_selection`
   * - :menuselection:`-->`
       |invertSelection| :guilabel:`Invert Feature Selection`
     -
     - :guilabel:`Selection`
     - :ref:`sec_selection`
   * - |newTableRow| :guilabel:`Add Record`
     - :kbd:`Ctrl+.`
     - :guilabel:`Digitizing`
     -
   * - |capturePoint| :guilabel:`Add Point Feature`
     - :kbd:`Ctrl+.`
     - :guilabel:`Digitizing`
     - :ref:`add_feature`
   * - |captureLine| :guilabel:`Add Line Feature`
     - :kbd:`Ctrl+.`
     - :guilabel:`Digitizing`
     - :ref:`add_feature`
   * - |capturePolygon| :guilabel:`Add Polygon Feature`
     - :kbd:`Ctrl+.`
     - :guilabel:`Digitizing`
     - :ref:`add_feature`
   * - |circularStringCurvePoint| :guilabel:`Add Circular String`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`add_circular_string`
   * - |circularStringRadius| :guilabel:`Add Circular String by Radius`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`add_circular_string`
   * - :menuselection:`Add Circle -->`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`draw_circles`
   * - :menuselection:`-->`
       |circle2Points| :guilabel:`Add Circle from 2 Points`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`draw_circles`
   * - :menuselection:`-->`
       |circle3Points| :guilabel:`Add Circle from 3 Points`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`draw_circles`
   * - :menuselection:`-->`
       |circle3Tangents| :guilabel:`Add Circle from 3 Tangents`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`draw_circles`
   * - :menuselection:`-->`
       |circle2TangentsPoint|
       :guilabel:`Add Circle from 2 Tangents and a Point`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`draw_circles`
   * - :menuselection:`-->`
       |circleCenterPoint|
       :guilabel:`Add Circle by a Center Point and Another Point`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`draw_circles`
   * - :menuselection:`Add Rectangle -->`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`draw_rectangles`
   * - :menuselection:`-->`
       |rectangleExtent| :guilabel:`Add Rectangle from Extent`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`draw_rectangles`
   * - :menuselection:`-->`
       |rectangleCenter|
       :guilabel:`Add Rectangle from Center and a Point`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`draw_rectangles`
   * - :menuselection:`-->`
       |rectangle3PointsProjected|
       :guilabel:`Add Rectangle from 3 Points (Distance from 2nd and 3rd point)`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`draw_rectangles`
   * - :menuselection:`-->`
       |rectangle3PointsDistance|
       :guilabel:`Add Rectangle from 3 Points (Distance from projected point on segment p1 and p2)`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`draw_rectangles`
   * - :menuselection:`Add Regular Polygon -->`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`draw_regular_polygons`
   * - :menuselection:`-->`
       |regularPolygonCenterPoint|
       :guilabel:`Add Regular Polygon from Center and a Point`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`draw_regular_polygons`
   * - :menuselection:`-->`
       |regularPolygonCenterCorner|
       :guilabel:`Add Regular Polygon from Center and a Corner`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`draw_regular_polygons`
   * - :menuselection:`-->`
       |regularPolygon2Points|
       :guilabel:`Add Regular Polygon from 2 Points`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`draw_regular_polygons`
   * - :menuselection:`Add Ellipse -->`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`draw_ellipses`
   * - :menuselection:`-->`
       |ellipseCenter2Points|
       :guilabel:`Add Ellipse from Center and 2 Points`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`draw_ellipses`
   * - :menuselection:`-->`
       |ellipseCenterPoint|
       :guilabel:`Add Ellipse from Center and a Point`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`draw_ellipses`
   * - :menuselection:`-->`
       |ellipseExtent| :guilabel:`Add Ellipse from Extent`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`draw_ellipses`
   * - :menuselection:`-->`
       |ellipseFoci| :guilabel:`Add Ellipse from Foci`
     -
     - :guilabel:`Shape Digitizing`
     - :ref:`draw_ellipses`
   * - :menuselection:`Add Annotation -->`
     -
     -
     - :ref:`sec_annotations`
   * - :menuselection:`-->` |textAnnotation| :menuselection:`Text Annotation`
     -
     - :guilabel:`Annotations`
     - :ref:`sec_annotations`
   * - :menuselection:`-->` |formAnnotation| :menuselection:`Form Annotation`
     -
     - :guilabel:`Annotations`
     - :ref:`sec_annotations`
   * - :menuselection:`-->` |htmlAnnotation| :menuselection:`HTML Annotation`
     -
     - :guilabel:`Annotations`
     - :ref:`sec_annotations`
   * - :menuselection:`-->` |svgAnnotation| :menuselection:`SVG Annotation`
     -
     - :guilabel:`Annotations`
     - :ref:`sec_annotations`
   * - :menuselection:`Edit Attributes -->`
     -
     -
     -
   * - :menuselection:`-->` |multiEdit|
       :guilabel:`Modify Attributes of Selected Features`
     -
     - :guilabel:`Digitizing`
     - :ref:`calculate_fields_values`
   * - :menuselection:`-->` |mergeFeatureAttributes|
       :guilabel:`Merge Attributes of Selected Features`
     -
     - :guilabel:`Advanced Digitizing`
     - :ref:`mergeattributesfeatures`
   * - :menuselection:`Edit Geometry -->`
     -
     -
     -
   * - :menuselection:`-->` |moveFeature| :guilabel:`Move Feature(s)`
     -
     - :guilabel:`Advanced Digitizing`
     - :ref:`move_feature`
   * - :menuselection:`-->` |moveFeatureCopy|
       :guilabel:`Copy and Move Feature(s)`
     -
     - :guilabel:`Advanced Digitizing`
     - :ref:`move_feature`
   * - :menuselection:`-->` |rotateFeature| :guilabel:`Rotate Feature(s)`
     -
     - :guilabel:`Advanced Digitizing`
     - :ref:`rotate_feature`
   * - :menuselection:`-->` |scaleFeature| :guilabel:`Scale Feature(s)`
     -
     - :guilabel:`Advanced Digitizing`
     - :ref:`scale_feature`
   * - :menuselection:`-->` |simplify| :guilabel:`Simplify Feature`
     -
     - :guilabel:`Advanced Digitizing`
     - :ref:`simplify_feature`
   * - :menuselection:`-->` |addRing| :guilabel:`Add Ring`
     -
     - :guilabel:`Advanced Digitizing`
     - :ref:`add_ring`
   * - :menuselection:`-->` |addPart| :guilabel:`Add Part`
     -
     - :guilabel:`Advanced Digitizing`
     - :ref:`add_part`
   * - :menuselection:`-->` |fillRing| :guilabel:`Fill Ring`
     -
     - :guilabel:`Advanced Digitizing`
     - :ref:`fill_ring`
   * - :menuselection:`-->` |deleteRing| :guilabel:`Delete Ring`
     -
     - :guilabel:`Advanced Digitizing`
     - :ref:`delete_ring`
   * - :menuselection:`-->` |deletePart| :guilabel:`Delete Part`
     -
     - :guilabel:`Advanced Digitizing`
     - :ref:`delete_part`
   * - :menuselection:`-->` |reshape| :guilabel:`Reshape Features`
     -
     - :guilabel:`Advanced Digitizing`
     - :ref:`reshape_feature`
   * - :menuselection:`-->` |offsetCurve| :guilabel:`Offset Curve`
     -
     - :guilabel:`Advanced Digitizing`
     - :ref:`offset_curve`
   * - :menuselection:`-->` |splitFeatures| :guilabel:`Split Features`
     -
     - :guilabel:`Advanced Digitizing`
     - :ref:`split_feature`
   * - :menuselection:`-->` |splitParts| :guilabel:`Split Parts`
     -
     - :guilabel:`Advanced Digitizing`
     - :ref:`split_part`
   * - :menuselection:`-->` |mergeFeatures| :guilabel:`Merge Selected Features`
     -
     - :guilabel:`Advanced Digitizing`
     - :ref:`mergeselectedfeatures`
   * - :menuselection:`-->` |vertexTool| :guilabel:`Vertex Tool (All Layers)`
     -
     - :guilabel:`Digitizing`
     - :ref:`vertex_tool`
   * - :menuselection:`-->` |vertexToolActiveLayer|
       :guilabel:`Vertex Tool (Current Layer)`
     -
     - :guilabel:`Digitizing`
     - :ref:`vertex_tool`
   * - :menuselection:`-->` |reverseLine| :guilabel:`Reverse Line`
     -
     - :guilabel:`Advanced Digitizing`
     - :ref:`reverse_line`
   * - :menuselection:`-->` |trimExtend| :guilabel:`Trim/extend Feature`
     -
     - :guilabel:`Advanced Digitizing`
     - :ref:`trim_extend_feature`
   * - |rotatePointSymbols| :guilabel:`Rotate Point Symbols`
     -
     - :guilabel:`Advanced Digitizing`
     - :ref:`rotate_symbol`
   * - |offsetPointSymbols| :guilabel:`Offset Point Symbols`
     -
     - :guilabel:`Advanced Digitizing`
     - :ref:`offset_symbol`


ရွေးချယ်ထားသော Layer ၏ ဂျီဩမေတြီ အမျိုးအစား (point ၊ polyline သို့မဟုတ် polygon စသည်တို့) ပေါ်တွင် မူတည်၍ အသုံးပြုနိုင်သော Tool များမှာ ပြောင်းလဲနေမည်ဖြစ်သည်-


.. list-table:: "Move feature" ဂျီဩမေတြီ အခြေခံသော icon များ
   :header-rows: 1
   :widths: 40 15 15 15


   * - Menu ရွေးချယ်စရာများ
     - Point
     - Polyline
     - Polygon
   * - :guilabel:`Move Feature(s)`
     - |moveFeaturePoint|
     - |moveFeatureLine|
     - |moveFeature|
   * - :guilabel:`Copy and Move Feature(s)`
     - |moveFeatureCopyPoint|
     - |moveFeatureCopyLine|
     - |moveFeatureCopy|


.. _view_menu:


View (မြင်ကွင်း)
-----------------

မြေပုံကို map view (မြေပုံမြင်ကွင်း) တွင် ပုံဖော်ပြသပြီး :menuselection:`View` tool များကိုအသုံးပြု၍ မြင်ကွင်းအမျိုးမျိုးကို ပြောင်းလဲကြည့်ရှုနိုင်ပါသည်။ ဥပမာအားဖြင့် အောက်ဖော်ပြပါ လုပ်ဆောင်ချက်များ ဆောင်ရွက်နိုင်ပါသည်-


* ပင်မ map canvas ဘေးတွင် နှစ်ဖက်မြင်မြေပုံ (2D) သို့မဟုတ် သုံးဖက်မြင်မြေပုံ (3D) မြင်ကွင်းပုံစံအသစ်များ ဖန်တီးခြင်း
* မည်သည့် နေရာကိုမဆို :ref:`Zoom or pan <zoom_pan>` (Zoom အချုံ့/အချဲ့ သို့မဟုတ် ရွေ့ခြင်း) လုပ်ခြင်း
* ပြသထားသည့် feature (အရာဝတ္ထု) ၏ attribute သို့မဟုတ် ဂျီဩမေတြီ ကို ရွေးချယ်ကြည့်ရှု (Query) ခြင်း
* Map view ကို ကြိုတင်ကြည့်ရှုခြင်းနည်းလမ်းများ၊ မှတ်ချက်များ သို့မဟုတ် တန်ဆာဆင်မှုများထည့်သွင်း၍ ပိုမိုကောင်းမွန်အောင် ဆောင်ရွက်ခြင်း
* မည်သည့် panel သို့မဟုတ် toolbar ကိုမဆို ဝင်ရောက်အသုံးပြုနိုင်ခြင်း

Menu သည် QGIS interface ကို အောက်ဖော်ပြပါလုပ်ဆောင်မှုများဖြင့် ၎င်းကိုယ်တိုင် ပြန်လည်စုစည်းစေနိုင်သည်-

* :guilabel:`Toggle Full Screen Mode` သည် title bar (ခေါင်းစဉ်ဘား) ကို ဖျောက်ထား၍ မျက်နှာပြင်တစ်ခုလုံးကို ကြည့်ရှုရန် အသုံးပြုနိုင်ပါသည်။ 
* :guilabel:`Toggle Panel Visibility` သည် အသုံးပြုနေသော :ref:`panels <panels_tools>` များကို ပြသရန် သို့မဟုတ် ဖျောက်ထားရန် အသုံးပြုနိုင်သည်။ ၎င်းသည် feature များကို digitizing (မြေပုံအချက်အလက်များရေးဆွဲခြင်း) ပြုလုပ်ရာတွင် (အကောင်းဆုံးမြင်ကွင်းရရှိရန်) အသုံးဝင်ရုံသာမက QGIS ၏ map canvas ကိုအသုံးပြု၍ (Projected/ Recorded) တင်ပြမှုများ ပြုလုပ်ရာတွင် အသုံးဝင်ပါသည်။
* :guilabel:`Toggle Map Only` ကို အသုံးပြုသည့်အခါ panel၊ toolbar၊ menu နှင့် အခြေအနေပြဘားတို့ကို ပိတ်ထား၍ map canvas ကိုသာ ဖော်ပြမည် ဖြစ်ပါသည်။ Full screen option (မျက်နှာပြင်အပြည့်ကြည့်ခြင်း) နှင့် တွဲ၍အသုံးပြုပါက screen ပေါ်တွင် မြေပုံတစ်ခုတည်းကိုသာ ဖော်ပြမည်ဖြစ်ပါသည်။

.. list-table:: View menu တွင် ပါဝင်သည့် item များ
   :header-rows: 1
   :widths: 42 22 12 24


   * - Menu ရွေးချယ်စရာများ
     - ဖြတ်လမ်းနည်း
     - Toolbar
     - အကိုးအကား
   * - |newMap| :guilabel:`New Map View`
     - :kbd:`Ctrl+M`
     - :guilabel:`Map Navigation`
     - :ref:`label_mapview`
   * - :menuselection:`3D Map Views -->`
     -
     -
     - :ref:`label_3dmapview`
   * - :menuselection:`-->` |new3DMap| :guilabel:`New 3D Map View`
     - :kbd:`Ctrl+Alt+M`
     - :guilabel:`Map Navigation`
     - :ref:`label_3dmapview`
   * - :menuselection:`--> Manage 3D Map Views`
     -
     -
     - :ref:`label_3dmapview`
   * - |pan| :guilabel:`Pan Map`
     -
     - :guilabel:`Map Navigation`
     - :ref:`zoom_pan`
   * - |panToSelected| :guilabel:`Pan Map to Selection`
     -
     - :guilabel:`Map Navigation`
     - :ref:`zoom_pan`
   * - |zoomIn| :guilabel:`Zoom In`
     - :kbd:`Ctrl+Alt++`
     - :guilabel:`Map Navigation`
     - :ref:`zoom_pan`
   * - |zoomOut| :guilabel:`Zoom Out`
     - :kbd:`Ctrl+Alt+-`
     - :guilabel:`Map Navigation`
     - :ref:`zoom_pan`
   * - |identify| :guilabel:`Identify Features`
     - :kbd:`Ctrl+Shift+I`
     - :guilabel:`Attributes`
     - :ref:`identify`
   * - :menuselection:`Measure -->`
     -
     - :guilabel:`Attributes`
     - :ref:`sec_measure`
   * - :menuselection:`-->` |measure|
       :guilabel:`Measure Line`
     - :kbd:`Ctrl+Shift+M`
     - :guilabel:`Attributes`
     - :ref:`sec_measure`
   * - :menuselection:`-->` |measureArea|
       :guilabel:`Measure Area`
     - :kbd:`Ctrl+Shift+J`
     - :guilabel:`Attributes`
     - :ref:`sec_measure`
   * - :menuselection:`-->` |measureBearing|
       :guilabel:`Measure Bearing`
     -
     - :guilabel:`Attributes`
     - :ref:`sec_measure`   
   * - :menuselection:`-->` |measureAngle|
       :guilabel:`Measure Angle`
     -
     - :guilabel:`Attributes`
     - :ref:`sec_measure`
   * - |sum| :guilabel:`Statistical Summary`
     -
     - :guilabel:`Attributes`
     - :ref:`statistical_summary`
   * - |newElevationProfile| :guilabel:`Elevation Profile`
     -
     -
     - :ref:`label_elevation_profile_view`
   * - |zoomFullExtent| :guilabel:`Zoom Full`
     - :kbd:`Ctrl+Shift+F`
     - :guilabel:`Map Navigation`
     - :ref:`zoom_pan`
   * - |zoomToSelected| :guilabel:`Zoom To Selection`
     - :kbd:`Ctrl+J`
     - :guilabel:`Map Navigation`
     - :ref:`zoom_pan`
   * - |zoomToLayer| :guilabel:`Zoom To Layer(s)`
     -
     - :guilabel:`Map Navigation`
     - :ref:`zoom_pan`
   * - |zoomActual| :guilabel:`Zoom To Native Resolution (100%)`
     -
     - :guilabel:`Map Navigation`
     - :ref:`zoom_pan`
   * - |zoomLast| :guilabel:`Zoom Last`
     -
     - :guilabel:`Map Navigation`
     - :ref:`zoom_pan`
   * - |zoomNext| :guilabel:`Zoom Next`
     -
     - :guilabel:`Map Navigation`
     - :ref:`zoom_pan`
   * - :menuselection:`Decorations -->`
     - :kbd:`Alt+V` + :kbd:`D`
     -
     - :ref:`decorations`
   * - :menuselection:`-->` |addGrid|
       :guilabel:`Grid...`
     -
     -
     - :ref:`grid_decoration`
   * - :menuselection:`-->` |scaleBar|
       :guilabel:`Scale Bar...`
     -
     -
     - :ref:`scalebar_decoration`
   * - :menuselection:`-->` |addImage|
       :guilabel:`Image...`
     -
     -
     - :ref:`image_decoration`
   * - :menuselection:`-->` |northArrow|
       :guilabel:`North Arrow...`
     -
     -
     - :ref:`northarrow_decoration`
   * - :menuselection:`-->` |titleLabel|
       :guilabel:`Title Label...`
     -
     -
     - :ref:`titlelabel_decoration`
   * - :menuselection:`-->` |copyrightLabel|
       :guilabel:`Copyright Label...`
     -
     -
     - :ref:`copyright_decoration`
   * - :menuselection:`-->` |addMap|
       :guilabel:`Layout Extents...`
     -
     -
     - :ref:`layoutextents_decoration`
   * - :menuselection:`Preview mode -->`
     -
     -
     -
   * - :menuselection:`--> Normal`
     -
     -
     -
   * - :menuselection:`--> Simulate Monochrome`
     -
     -
     -
   * - :menuselection:`--> Simulate Achromatopsia Color Blindness (Grayscale)`
     -
     -
     -
   * - :menuselection:`--> Simulate Protanopia Color Blindness (No Red)`
     -
     -
     -
   * - :menuselection:`--> Simulate Deuteranopia Color Blindness (No Green)`
     -
     -
     -
   * - :menuselection:`--> Simulate Tritanopia Color Blindness (No Blue)`
     -
     -
     -
   * - |mapTips| :guilabel:`Show Map Tips`
     -
     - :guilabel:`Attributes`
     - :ref:`maptips`
   * - |newBookmark| :guilabel:`New Spatial Bookmark...`
     - :kbd:`Ctrl+B`
     - :guilabel:`Map Navigation`
     - :ref:`sec_bookmarks`
   * - |showBookmarks| :guilabel:`Show Spatial Bookmarks`
     - :kbd:`Ctrl+Shift+B`
     - :guilabel:`Map Navigation`
     - :ref:`sec_bookmarks`
   * - |showBookmarks| :guilabel:`Show Spatial Bookmark Manager`
     -
     -
     - :ref:`sec_bookmarks`
   * - |refresh| :guilabel:`Refresh`
     - :kbd:`F5`
     - :guilabel:`Map Navigation`
     -
   * - :menuselection:`Layer Visibility -->`
     -
     -
     - :ref:`label_legend`
   * - :menuselection:`-->` |showAllLayers| :guilabel:`Show All Layers`
     - :kbd:`Ctrl+Shift+U`
     -
     - :ref:`label_legend`
   * - :menuselection:`-->` |hideAllLayers| :guilabel:`Hide All Layers`
     - :kbd:`Ctrl+Shift+H`
     -
     - :ref:`label_legend`
   * - :menuselection:`-->` |showSelectedLayers|
       :guilabel:`Show Selected Layers`
     -
     -
     - :ref:`label_legend`
   * - :menuselection:`-->` |hideSelectedLayers|
       :guilabel:`Hide Selected Layers`
     -
     -
     - :ref:`label_legend`
   * - :menuselection:`-->` |toggleSelectedLayers|
       :guilabel:`Toggle Selected Layers`
     -
     -
     - :ref:`label_legend`
   * - :menuselection:`-->` :guilabel:`Toggle Selected Layers Independently`
     -
     -
     - :ref:`label_legend`
   * - :menuselection:`-->` |hideDeselectedLayers|
       :guilabel:`Hide Deselected Layers`
     -
     -
     - :ref:`label_legend`
   * - :menuselection:`Panels -->`
     -
     -
     - :ref:`sec_panels_and_toolbars`
   * - :menuselection:`Toolbars -->`
     -
     -
     - :ref:`sec_panels_and_toolbars`
   * - :guilabel:`Toggle Full Screen Mode`
     - :kbd:`F11`
     -
     -
   * - :guilabel:`Toggle Panel Visibility`
     - :kbd:`Ctrl+Tab`
     -
     -
   * - :guilabel:`Toggle Map Only`
     - :kbd:`Ctrl+Shift+Tab`
     -
     -


|kde| Linux KDE ကွန်ပျူတာစနစ်တွင် :menuselection:`Panels -->` ၊ :menuselection:`Toolbars -->` နှင့် :guilabel:`Toggle Full Screen Mode` (မျက်နှာပြင်အပြည့်ကြည့်ခြင်းကို အဖွင့်အပိတ်လုပ်ခြင်း) များကို  :menuselection:`Settings` menu တွင် တွေ့နိုင်ပါသည်။ 


Layer (အလွှာ)
--------------

:menuselection:`Layer` menu သည်  data အရင်းအမြစ်များကို :ref:`create (ဖန်တီး)<sec_create_vector>` လုပ်ရန် tool များစွာ ပါရှိပြီး ၎င်းတို့ကို project တစ်ခုထဲသို့ :ref:`add (ထည့်သွင်း) <opening_data>` လုပ်ရန် သို့မဟုတ် ၎င်းတို့ကို :ref:`save modifications (လက်ရှိ layerကို ပြင်ဆင်တည်းဖြတ်ပြီး သိမ်းဆည်းခြင်း) <sec_edit_existing_layer>` များ ပြုလုပ်နိုင်ပါသည်။ တူညီသည့် ဒေတာအရင်းအမြစ်များကိုအသုံးပြု၍ အောက်ပါတို့ကိုလည်း ပြုလုပ်နိုင်ပါသည်-

* :guilabel:`Duplicate` သည် Layer တစ်ခု၏ အမည်၊ style (ပုံစံ) (သင်္ကေတ၊ အညွှန်းများစသည့်)၊ joins (ချိတ်ဆက်မှုများ) တို့ကို စိတ်ကြိုက်ပြင်ဆင်နိုင်သည့် Layer မိတ္တူတစ်ခု ထုတ်ပေးပါသည်။ ၎င်း Layer မိတ္တူသည် မူလ Layer ကဲ့သို့ တူညီသော ဒေတာအရင်းအမြစ်ကို အသုံးပြုပါသည်။ 
* :guilabel:`Copy` နှင့် :guilabel:`Paste` သည် Project တစ်ခုမှ တစ်ခုသို့ Layer နှင့် group များကို ကူးယူရာတွင် အသုံးပြုသည်။ ၎င်း၏ ဂုဏ်ရည်အချက်များကို မူရင်း Layer အား ထိခိုက်မှုမရှိစေဘဲ စိတ်ကြိုက်ပြင်ဆင်နိုင်မည်ဖြစ်သည်။ *Duplicate* လုပ်လျှင်မူ Layer များသည် မူလ Layer နှင့်တူညီသော data အရင်းအမြစ်ကိုသာ အသုံးပြုပါသည်။
* သို့မဟုတ် အခြား Project တစ်ခုမှ  :guilabel:`Embed Layers and Groups...` (layer များနှင့် group များကို ထည့်သွင်းခြင်း) ပြုလုပ်နိုင်သည်။ သို့သော် ၎င်းတို့သည် ပြင်ဆင်မှုတည်းဖြတ်မှုများ မပြုလုပ်နိုင်သည့် read-only မိတ္တူများဖြစ်သည်။ (:ref:`nesting_projects` တွင် ကြည့်ရှုနိုင်ပါသည်။)

:menuselection:`Layer` menu တွင် Layer property များ (style ၊ အချိုးအစား ၊ ကိုဩဒိနိတ်စနစ် (CRS)...) ကို ကူးယူခြင်း သို့မဟုတ် ပြင်ဆင်သတ်မှတ်ခြင်းပြုလုပ်နိုင်သည့် tool များလည်း ပါဝင်ပါသည်။ 


.. list-table:: Layer menu တွင် ပါဝင်သည့် item များ
   :header-rows: 1
   :widths: 37 18 18 27


   * - Menu ရွေးချယ်စရာများ
     - ဖြတ်လမ်းနည်း
     - Toolbar
     - အကိုးအကား
   * - |dataSourceManager| :guilabel:`Data Source Manager`
     - :kbd:`Ctrl+L`
     - :guilabel:`Data Source Manager`
     - :ref:`Opening Data <datasourcemanager>`
   * - :menuselection:`Create Layer -->`
     -
     -
     - :ref:`sec_create_vector`
   * - :menuselection:`-->` |newGeoPackageLayer|
       :guilabel:`New GeoPackage Layer...`
     - :kbd:`Ctrl+Shift+N`
     - :guilabel:`Data Source Manager`
     - :ref:`vector_create_geopackage`
   * - :menuselection:`-->` |newVectorLayer|
       :guilabel:`New Shapefile Layer...`
     -
     - :guilabel:`Data Source Manager`
     - :ref:`vector_create_shapefile`
   * - :menuselection:`-->` |newSpatiaLiteLayer|
       :guilabel:`New SpatiaLite Layer...`
     -
     - :guilabel:`Data Source Manager`
     - :ref:`vector_create_spatialite`
   * - :menuselection:`-->` |createMemory|
       :guilabel:`New Temporary Scratch Layer...`
     -
     - :guilabel:`Data Source Manager`
     - :ref:`vector_new_scratch_layer`
   * - :menuselection:`-->` |newMeshLayer|
       :guilabel:`New Mesh Layer...`
     -
     - :guilabel:`Data Source Manager`
     - :ref:`vector_create_mesh`
   * - :menuselection:`-->` |createGPX|
       :guilabel:`New GPX Layer...`
     -
     - :guilabel:`Data Source Manager`
     - :ref:`vector_create_gpx`
   * - :menuselection:`-->` |newVirtualLayer|
       :guilabel:`New Virtual Layer...`
     -
     - :guilabel:`Data Source Manager`
     - :ref:`vector_virtual_layers`
   * - :menuselection:`Add Layer -->`
     -
     -
     - :ref:`opening_data`
   * - :menuselection:`-->` |addOgrLayer|
       :guilabel:`Add Vector Layer......`
     - :kbd:`Ctrl+Shift+V`
     - :guilabel:`Manage Layers`
     - :ref:`loading_file`
   * - :menuselection:`-->` |addRasterLayer|
       :guilabel:`Add Raster Layer...`
     - :kbd:`Ctrl+Shift+R`
     - :guilabel:`Manage Layers`
     - :ref:`loading_file`
   * - :menuselection:`-->` |addMeshLayer|
       :guilabel:`Add Mesh Layer...`
     -
     - :guilabel:`Manage Layers`
     - :ref:`mesh_loading`
   * - :menuselection:`-->` |addDelimitedTextLayer|
       :guilabel:`Add Delimited Text Layer...`
     - :kbd:`Ctrl+Shift+T`
     - :guilabel:`Manage Layers`
     - :ref:`vector_loading_csv`
   * - :menuselection:`-->` |addPostgisLayer|
       :guilabel:`Add PostGIS Layer...`
     - :kbd:`Ctrl+Shift+D`
     - :guilabel:`Manage Layers`
     - :ref:`db_tools`
   * - :menuselection:`-->` |addSpatiaLiteLayer|
       :guilabel:`Add SpatiaLite Layer...`
     - :kbd:`Ctrl+Shift+L`
     - :guilabel:`Manage Layers`
     - :ref:`label_spatialite`
   * - :menuselection:`-->` |addMssqlLayer|
       :guilabel:`Add MS SQL Server Layer...`
     -
     - :guilabel:`Manage Layers`
     - :ref:`db_tools`
   * - :menuselection:`-->` |addOracleLayer|
       :guilabel:`Add Oracle Spatial Layer...`
     -
     - :guilabel:`Manage Layers`
     - :ref:`db_tools`
   * - :menuselection:`-->` |addHanaLayer|
       :guilabel:`Add SAP HANA Spatial Layer...`
     -
     - :guilabel:`Manage Layers`
     - :ref:`db_tools`
   * - :menuselection:`-->` |addVirtualLayer|
       :guilabel:`Add/Edit Virtual Layer...`
     -
     - :guilabel:`Manage Layers`
     - :ref:`vector_virtual_layers`
   * - :menuselection:`-->` |addWmsLayer|
       :guilabel:`Add WMS/WMTS Layer...`
     - :kbd:`Ctrl+Shift+W`
     - :guilabel:`Manage Layers`
     - :ref:`ogc-wms-layers`
   * - :menuselection:`-->` |addXyzLayer|
       :guilabel:`Add XYZ Layer...`
     -
     -
     - :ref:`xyz_tile`
   * - :menuselection:`-->` |addWcsLayer|
       :guilabel:`Add WCS Layer...`
     -
     - :guilabel:`Manage Layers`
     - :ref:`ogc-wcs`
   * - :menuselection:`-->` |addWfsLayer|
       :guilabel:`Add WFS / OGC API - Features Layer...`
     -
     - :guilabel:`Manage Layers`
     - :ref:`ogc-wfs`
   * - :menuselection:`-->` |addAfsLayer|
       :guilabel:`Add ArcGIS REST Server Layer...`
     -
     - :guilabel:`Manage Layers`
     - :ref:`arcgis_rest`
   * - :menuselection:`-->` |addVectorTileLayer|
       :guilabel:`Add Vector Tile Layer...`
     -
     -
     - :ref:`vector_tiles`
   * - :menuselection:`-->` |addPointCloudLayer|
       :guilabel:`Add Point Cloud Layer...`
     -
     -
     - :ref:`working_with_point_clouds`
   * - :menuselection:`-->` |addGpsLayer|
       :guilabel:`Add GPX Layer...`
     -
     -
     - :ref:`gps_data`
   * - :guilabel:`Embed Layers and Groups...`
     -
     -
     - :ref:`nesting_projects`
   * - :guilabel:`Add from Layer Definition File...`
     -
     -
     - :ref:`layer_definition_file`
   * - |georefRun| :guilabel:`Georeferencer...`
     -
     -
     - :ref:`georef`
   * - |editCopy| :guilabel:`Copy Style`
     -
     -
     - :ref:`save_layer_property`
   * - |editPaste| :guilabel:`Paste Style`
     -
     -
     - :ref:`save_layer_property`
   * - |editCopy| :guilabel:`Copy Layer`
     -
     -
     -
   * - |editPaste| :guilabel:`Paste Layer/Group`
     -
     -
     -
   * - |openTable| :guilabel:`Open Attribute Table`
     - :kbd:`F6`
     - :guilabel:`Attributes`
     - :ref:`sec_attribute_table`
   * - :menuselection:`Filter Attribute Table -->`
     -
     -
     - :ref:`sec_attribute_table`
   * - :menuselection:`-->` |openTableSelected| :menuselection:`Open Attribute Table (Selected Features)`
     - :kbd:`Shift+F6`
     - :guilabel:`Attributes`
     - :ref:`sec_attribute_table`
   * - :menuselection:`-->` |openTableVisible| :menuselection:`Open Attribute Table (Visible Features)`
     - :kbd:`Ctrl+F6`
     - :guilabel:`Attributes`
     - :ref:`sec_attribute_table`
   * - :menuselection:`-->` |openTableEdited| :menuselection:`Open Attribute Table (Edited and New Features)`
     -
     - :guilabel:`Attributes`
     - :ref:`sec_attribute_table`
   * - |toggleEditing| :guilabel:`Toggle Editing`
     -
     - :guilabel:`Digitizing`
     - :ref:`sec_edit_existing_layer`
   * - |fileSave| :guilabel:`Save Layer Edits`
     -
     - :guilabel:`Digitizing`
     - :ref:`save_feature_edits`
   * - |allEdits| :menuselection:`Current Edits -->`
     -
     - :guilabel:`Digitizing`
     - :ref:`save_feature_edits`
   * - :menuselection:`--> Save for Selected Layer(s)`
     -
     - :guilabel:`Digitizing`
     - :ref:`save_feature_edits`
   * - :menuselection:`--> Rollback for Selected Layer(s)`
     -
     - :guilabel:`Digitizing`
     - :ref:`save_feature_edits`
   * - :menuselection:`--> Cancel for Selected Layer(s)`
     -
     - :guilabel:`Digitizing`
     - :ref:`save_feature_edits`
   * - :menuselection:`--> Save for all Layers`
     -
     - :guilabel:`Digitizing`
     - :ref:`save_feature_edits`
   * - :menuselection:`--> Rollback for all Layers`
     -
     - :guilabel:`Digitizing`
     - :ref:`save_feature_edits`
   * - :menuselection:`--> Cancel for all Layers`
     -
     - :guilabel:`Digitizing`
     - :ref:`save_feature_edits`
   * - :guilabel:`Save As...`
     -
     -
     - :ref:`general_saveas`
   * - :guilabel:`Save As Layer Definition File...`
     -
     -
     - :ref:`layer_definition_file`
   * - |removeLayer| :guilabel:`Remove Layer/Group`
     - :kbd:`Ctrl+D`
     -
     -
   * - |duplicateLayer| :guilabel:`Duplicate Layer(s)`
     -
     -
     -
   * - :guilabel:`Set Scale Visibility of Layer(s)`
     -
     -
     - :ref:`label_scaledepend`
   * - :guilabel:`Set CRS of Layer(s)`
     - :kbd:`Ctrl+Shift+C`
     -
     - :ref:`layer_crs`
   * - :guilabel:`Set Project CRS from Layer`
     -
     -
     - :ref:`project_crs`
   * - :guilabel:`Layer Properties...`
     -
     -
     - :ref:`vector_properties_dialog`,
       :ref:`raster_properties_dialog`,
       :ref:`label_meshproperties`,
       :ref:`point_clouds_properties`,
       :ref:`vectortiles_properties`
   * - :guilabel:`Filter...`
     - :kbd:`Ctrl+F`
     -
     - :ref:`vector_query_builder`
   * - |labelingSingle| :guilabel:`Labeling`
     -
     -
     - :ref:`vector_labels_tab`
   * - |inOverview| :guilabel:`Show in Overview`
     -
     -
     - :ref:`overview_panels`
   * - |addAllToOverview| :guilabel:`Show All in Overview`
     -
     -
     - :ref:`overview_panels`
   * - |removeAllFromOverview| :guilabel:`Hide All from Overview`
     -
     -
     - :ref:`overview_panels`




Settings (ပြင်ဆင်သတ်မှတ်ခြင်းများ)
-----------------------------------


.. list-table:: Settings menu တွင် ပါဝင်သည့် item များ
   :header-rows: 1
   :widths: 50 50


   * - ‌Menu ရွေးချယ်စရာများ
     - အကိုးအကား
   * - :menuselection:`User Profiles -->`
     - :ref:`user_profiles`
   * - :menuselection:`--> default`
     - :ref:`user_profiles`
   * - :menuselection:`--> Open Active Profile Folder`
     - :ref:`user_profiles`
   * - :menuselection:`--> New Profile...`
     - :ref:`user_profiles`
   * - |styleManager| :guilabel:`Style Manager...`
     - :ref:`vector_style_manager`
   * - |customProjection| :guilabel:`Custom Projections...`
     - :ref:`sec_custom_projections`
   * - |keyboardShortcuts| :guilabel:`Keyboard Shortcuts...`
     - :ref:`shortcuts`
   * - |interfaceCustomization|
       :guilabel:`Interface Customization...`
     - :ref:`sec_customization`
   * - |options| :guilabel:`Options...`
     - :ref:`gui_options`


|kde| Linux KDE ကွန်ပျူတာစနစ်တွင် :menuselection:`Panels -->` ၊ :menuselection:`Toolbars -->` နှင့် :guilabel:`Toggle Full Screen Mode` ကဲ့သို့သော tool များကို :menuselection:`Settings` menu ၌ ရှာဖွေအသုံးပြုနိုင်ပါသည်။

Plugins (လုပ်‌ဆောင်ချက်အသစ်များကို ဆောင်ရွက်နိုင်ရန် ထပ်မံထည့်သွင်းထားသည့် Tool များ)
--------------------------------------------------------------------------------------


.. list-table:: Plugins menu တွင် ပါဝင်သည့် item များ
   :header-rows: 1
   :widths: 36 17 17 30


   * - Menu ရွေးချယ်စရာများ
     - ဖြတ်လမ်းနည်း
     - Toolbar
     - အကိုးအကား
   * - |showPluginManager| :guilabel:`Manage and Install Plugins...`
     -
     -
     - :ref:`managing_plugins`
   * - "|pythonFile| :guilabel:`Python Console`
     - :kbd:`Ctrl+Alt+P`
     - :guilabel:`Plugins`
     - :ref:`console`


QGIS ကို ပထမဆုံးအကြိမ် အသုံးပြုခြင်းဖြစ်လျှင် ၎င်း၌ ပင်မ plugin များအားလုံး ပါရှိဦးမည်မဟုတ်ပါ။

Vector (Point၊ Line၊ Polygon vector များ)
------------------------------------------

ဤပုံစံသည် ပင်မ plugin များအားလုံးကိုဖွင့်ထားလိုက်လျှင် :guilabel:`Vector` menu ကို မြင်တွေ့ရမည့်ပုံစံ ဖြစ်ပါသည်။


.. list-table:: Vector menu တွင် ပါဝင်သည့် item များ
   :header-rows: 1
   :widths: 40 15 10 35


   * - Menu ရွေးချယ်စရာများ
     - ဖြတ်လမ်းနည်းများ
     - Toolbar
     - အကိုးအကား
   * - |geometryChecker| :guilabel:`Check Geometries...`
     -
     -
     - :ref:`geometry_checker`
   * - |topologyChecker| :guilabel:`Topology Checker`
     -
     - :guilabel:`Vector`
     - :ref:`topology`
   * - :menuselection:`Geoprocessing Tools -->`
     - :kbd:`Alt+O` + :kbd:`G`
     -
     -
   * - :menuselection:`-->` |buffer| :menuselection:`Buffer...`
     -
     -
     - :ref:`qgisbuffer`
   * - :menuselection:`-->` |clip| :menuselection:`Clip...`
     -
     -
     - :ref:`qgisclip`
   * - :menuselection:`-->` |convexHull| :menuselection:`Convex Hull...`
     -
     -
     - :ref:`qgisconvexhull`
   * - :menuselection:`-->` |difference| :menuselection:`Difference...`
     -
     -
     - :ref:`qgisdifference`
   * - :menuselection:`-->` |dissolve| :menuselection:`Dissolve...`
     -
     -
     - :ref:`qgisdissolve`
   * - :menuselection:`-->` |intersect| :menuselection:`Intersection...`
     -
     -
     - :ref:`qgisintersection`
   * - :menuselection:`-->` |symmetricalDifference| :menuselection:`Symmetrical Difference...`
     -
     -
     - :ref:`qgissymmetricaldifference`
   * - :menuselection:`-->` |union| :menuselection:`Union...`
     -
     -
     - :ref:`qgisunion`
   * - :menuselection:`-->` |dissolve| :menuselection:`Eliminate Selected Polygons...`
     -
     -
     - :ref:`qgiseliminateselectedpolygons`
   * - :menuselection:`Geometry Tools -->`
     - :kbd:`Alt+O` + :kbd:`E`
     -
     -
   * - :menuselection:`-->` |centroids| :menuselection:`Centroids...`
     -
     -
     - :ref:`qgiscentroids`
   * - :menuselection:`-->` |collect| :menuselection:`Collect Geometries...`
     -
     -
     - :ref:`qgiscollect`
   * - :menuselection:`-->` |extractVertices| :menuselection:`Extract Vertices...`
     -
     -
     - :ref:`qgisextractvertices`
   * - :menuselection:`-->` |multiToSingle| :menuselection:`Multipart to Singleparts...`
     -
     -
     - :ref:`qgismultiparttosingleparts`
   * - :menuselection:`-->` |polygonToLine| :menuselection:`Polygons to Lines...`
     -
     -
     - :ref:`qgispolygonstolines`
   * - :menuselection:`-->` |simplify_2| :menuselection:`Simplify...`
     -
     -
     - :ref:`qgissimplifygeometries`
   * - :menuselection:`-->` |checkGeometry| :menuselection:`Check Validity...`
     -
     -
     - :ref:`qgischeckvalidity`
   * - :menuselection:`-->` |delaunay| :menuselection:`Delaunay Triangulation...`
     -
     -
     - :ref:`qgisdelaunaytriangulation`
   * - :menuselection:`-->` |processingAlgorithm| :menuselection:`Densify by Count...`
     -
     -
     - :ref:`qgisdensifygeometries`
   * - :menuselection:`-->` |addGeometryAttributes| :menuselection:`Add Geometry Attributes...`
     -
     -
     - :ref:`qgisexportaddgeometrycolumns`
   * - :menuselection:`-->` |lineToPolygon| :menuselection:`Lines to Polygons...`
     -
     -
     - :ref:`qgislinestopolygons`
   * - :menuselection:`-->` |voronoi| :menuselection:`Voronoi Polygons...`
     -
     -
     - :ref:`qgisvoronoipolygons`
   * - :menuselection:`Analysis Tools -->`
     - :kbd:`Alt+O` + :kbd:`A`
     -
     -
   * - :menuselection:`-->` |lineIntersections| :menuselection:`Line Intersection...`
     -
     -
     - :ref:`qgislineintersections`
   * - :menuselection:`-->` |meanCoordinates| :menuselection:`Mean Coordinate(s)...`
     -
     -
     - :ref:`qgismeancoordinates`
   * - :menuselection:`-->` |basicStatistics| :menuselection:`Basic Statistics for Fields...`
     -
     -
     - :ref:`qgisbasicstatisticsforfields`
   * - :menuselection:`-->` |sumPoints| :menuselection:`Count Points in Polygon...`
     -
     -
     - :ref:`qgiscountpointsinpolygon`
   * - :menuselection:`-->` |distanceMatrix| :menuselection:`Distance Matrix...`
     -
     -
     - :ref:`qgisdistancematrix`
   * - :menuselection:`-->` |uniqueValues| :menuselection:`List Unique Values...`
     -
     -
     - :ref:`qgislistuniquevalues`
   * - :menuselection:`-->` |nearestNeighbour| :menuselection:`Nearest Neighbour Analysis...`
     -
     -
     - :ref:`qgisnearestneighbouranalysis`
   * - :menuselection:`-->` |sumLengthLines| :menuselection:`Sum Line Lengths...`
     -
     -
     - :ref:`qgissumlinelengths`
   * - :menuselection:`Data Management Tools -->`
     - :kbd:`Alt+O` + :kbd:`D`
     -
     -
   * - :menuselection:`-->` |mergeLayers| :menuselection:`Merge Vector Layers...`
     -
     -
     - :ref:`qgismergevectorlayers`
   * - :menuselection:`-->` |processingAlgorithm| :menuselection:`Reproject Layer...`
     -
     -
     - :ref:`qgisreprojectlayer`
   * - :menuselection:`-->` |processingAlgorithm| :menuselection:`Create Spatial Index...`
     -
     -
     - :ref:`qgiscreatespatialindex`
   * - :menuselection:`-->` |processingAlgorithm| :menuselection:`Join Attributes by Location...`
     -
     -
     - :ref:`qgisjoinattributesbylocation`
   * - :menuselection:`-->` |splitLayer| :menuselection:`Split Vector Layer...`
     -
     -
     - :ref:`qgissplitvectorlayer`
   * - :menuselection:`Research Tools -->`
     - :kbd:`Alt+O` + :kbd:`R`
     -
     -
   * - :menuselection:`-->` |createGrid| :menuselection:`Create Grid...`
     -
     -
     - :ref:`qgiscreategrid`
   * - :menuselection:`-->` |extractLayerExtent| :menuselection:`Extract Layer Extent...`
     -
     -
     - :ref:`qgispolygonfromlayerextent`
   * - :menuselection:`-->` |randomPointsWithinExtent| :menuselection:`Random Points in Extent...`
     -
     -
     - :ref:`qgisrandompointsinextent`
   * - :menuselection:`-->` |randomPointsInPolygons| :menuselection:`Random Points in Polygons...`
     -
     -
     - :ref:`qgisrandompointsinpolygons`
   * - :menuselection:`-->` |randomPointsOnLines| :menuselection:`Random Points on Lines...`
     -
     -
     - :ref:`qgisrandompointsonlines`
   * - :menuselection:`-->` |selectLocation| :menuselection:`Select by Location...`
     -
     -
     - :ref:`qgisselectbylocation`
   * - :menuselection:`-->` |selectDistance| :menuselection:`Select Within Distance...`
     -
     -
     - :ref:`qgisselectwithindistance`
   * - :menuselection:`-->` |randomPointsWithinExtent| :menuselection:`Random Points in Layer Bounds...`
     -
     -
     - :ref:`qgisrandompointsinlayerbounds`
   * - :menuselection:`-->` |randomPointsWithinPolygon| :menuselection:`Random Points Inside Polygons...`
     -
     -
     - :ref:`qgisrandompointsinsidepolygons`
   * - :menuselection:`-->` |selectRandom| :menuselection:`Random Selection...`
     -
     -
     - :ref:`qgisrandomselection`
   * - :menuselection:`-->` |selectRandom| :menuselection:`Random Selection Within Subsets...`
     -
     -
     - :ref:`qgisrandomselectionwithinsubsets`
   * - :menuselection:`-->` |regularPoints| :menuselection:`Regular Points...`
     -
     -
     - :ref:`qgisregularpoints`



QGIS သည် ပုံမှန်အားဖြင့်  :guilabel:`Vector` menu ထဲတွင် :ref:`Processing <sec_processing_intro>` algorithm များကို menu ခွဲများအဖြစ် အုပ်စုဖွဲ့၍ ထည့်သွင်းထားပါသည်။ ၎င်းတွင် provider အမျိုးမျိုးမှ vector ကို အခြေခံသည့် အသုံးများသော GIS လုပ်ဆောင်ချက်များအတွက် ဖြတ်လမ်းနည်းများကို ပံ့ပိုးပေးထားပါသည်။ အကယ်၍ ထို menu ခွဲများအားလုံးကို မရရှိပါက :menuselection:`Plugins --> Manage and Install Plugins...` ထဲရှိ Processing plugin ကို ဖွင့်၍ အသုံးပြုနိုင်ပါသည်။ 

Algorithm များစာရင်း နှင့် ၎င်း၏ menu များကို Processing algorithms တစ်ခုခု ( :ref:`processing.options` ကို ဖတ်ရှုပါ) သို့မဟုတ် အချို့သောပြင်ပ :ref:`plugins <plugins>` များဖြင့် ပြင်ဆင်ခြင်း၊ တိုးချဲ့လုပ်ဆောင်ခြင်းများ ပြုလုပ်နိုင်ပါသည်။


Raster (ပထဝီဝင်ဆိုင်ရာဒေတာများကို Pixel များဖြင့်ဖော်ပြသော Raster များ)
------------------------------------------------------------------------

ဤပုံစံသည် ပင်မ plugin များအားလုံးကိုဖွင့်ထားလျှင် :guilabel:`Raster` menu ကို မြင်တွေ့ရမည့် ပုံစံဖြစ်ပါသည်။


.. list-table:: Raster menu တွင် ပါဝင်သည့် item များ
   :header-rows: 1
   :widths: 40 15 8 38


   * - Menu ရွေးချယ်စရာများ
     - ဖြတ်လမ်းနည်း
     - Toolbar
     - အကိုးအကား
   * - |showRasterCalculator| :guilabel:`Raster calculator...`
     -
     -
     - :ref:`label_raster_calc`
   * - :guilabel:`Align Raster...`
     -
     -
     - :ref:`label_raster_align`
   * - :menuselection:`Analysis -->`
     -
     -
     -
   * - :menuselection:`-->` |providerGdal| :menuselection:`Aspect...`
     -
     -
     - :ref:`gdalaspect`
   * - :menuselection:`-->` |providerGdal| :menuselection:`Fill nodata...`
     -
     -
     - :ref:`gdalfillnodata`
   * - :menuselection:`-->` |grid| :menuselection:`Grid (Moving Average)...`
     -
     -
     - :ref:`gdalgridaverage`
   * - :menuselection:`-->` |grid| :menuselection:`Grid (Data Metrics)...`
     -
     -
     - :ref:`gdalgriddatametrics`
   * - :menuselection:`-->` |grid| :menuselection:`Grid (Inverse Distance to a Power)...`
     -
     -
     - :ref:`gdalgridinversedistance`
   * - :menuselection:`-->` |grid| :menuselection:`Grid (Nearest Neighbor)...`
     -
     -
     - :ref:`gdalgridinversedistancenearestneighbor`
   * - :menuselection:`-->` |nearblack| :menuselection:`Near Black...`
     -
     -
     - :ref:`gdalnearblack`
   * - :menuselection:`-->` |providerGdal| :menuselection:`Hillshade...`
     -
     -
     - :ref:`gdalhillshade`
   * - :menuselection:`-->` |proximity| :menuselection:`Proximity (Raster Distance)...`
     -
     -
     - :ref:`gdalproximity`
   * - :menuselection:`-->` |providerGdal| :menuselection:`Roughness...`
     -
     -
     - :ref:`gdalroughness`
   * - :menuselection:`-->` |sieve| :menuselection:`Sieve...`
     -
     -
     - :ref:`gdalsieve`
   * - :menuselection:`-->` |providerGdal| :menuselection:`Slope...`
     -
     -
     - :ref:`gdalslope`
   * - :menuselection:`-->` |providerGdal| :menuselection:`Topographic Position Index (TPI)...`
     -
     -
     - :ref:`gdaltpitopographicpositionindex`
   * - :menuselection:`-->` |providerGdal| :menuselection:`Terrain Ruggedness Index (TRI)...`
     -
     -
     - :ref:`gdaltriterrainruggednessindex`
   * - :menuselection:`Projections -->`
     -
     -
     -
   * - :menuselection:`-->` |projectionAdd| :menuselection:`Assign Projection...`
     -
     -
     - :ref:`gdalassignprojection`
   * - :menuselection:`-->` |projectionExport| :menuselection:`Extract Projection...`
     -
     -
     - :ref:`gdalextractprojection`
   * - :menuselection:`-->` |warp| :menuselection:`Warp (Reproject)...`
     -
     -
     - :ref:`gdalwarpreproject`
   * - :menuselection:`Miscellaneous -->`
     -
     -
     -
   * - :menuselection:`-->` |vrt| :menuselection:`Build Virtual Raster...`
     -
     -
     - :ref:`gdalbuildvirtualraster`
   * - :menuselection:`-->` |rasterInfo| :menuselection:`Raster Information...`
     -
     -
     - :ref:`gdalgdalinfo`
   * - :menuselection:`-->` |merge| :menuselection:`Merge...`
     -
     -
     - :ref:`gdalmerge`
   * - :menuselection:`-->` |rasterOverview| :menuselection:`Build Overviews (Pyramids)...`
     -
     -
     - :ref:`gdaloverviews`
   * - :menuselection:`-->` |tiles| :menuselection:`Tile Index...`
     -
     -
     - :ref:`gdaltileindex`
   * - :menuselection:`Extraction -->`
     -
     -
     -
   * - :menuselection:`-->` |rasterClip| :menuselection:`Clip Raster by Extent...`
     -
     -
     - :ref:`gdalcliprasterbyextent`
   * - :menuselection:`-->` |rasterClip| :menuselection:`Clip Raster by Mask Layer...`
     -
     -
     - :ref:`gdalcliprasterbymasklayer`
   * - :menuselection:`-->` |contour| :menuselection:`Contour...`
     -
     -
     - :ref:`gdalcontour`
   * - :menuselection:`Conversion -->`
     -
     -
     -
   * - :menuselection:`-->` |8To24Bits| :menuselection:`PCT to RGB...`
     -
     -
     - :ref:`gdalpcttorgb`
   * - :menuselection:`-->` |polygonize| :menuselection:`Polygonize (Raster to Vector)...`
     -
     -
     - :ref:`gdalpolygonize`
   * - :menuselection:`-->` |rasterize| :menuselection:`Rasterize (Vector to Raster)...`
     -
     -
     - :ref:`gdalrasterize`
   * - :menuselection:`-->` |24To8Bits| :menuselection:`RGB to PCT...`
     -
     -
     - :ref:`gdalrgbtopct`
   * - :menuselection:`-->` |translate| :menuselection:`Translate (Convert Format)...`
     -
     -
     - :ref:`gdaltranslate`


GIS သည် ပုံမှန်အားဖြင့် :guilabel:`Raster` menu ထဲတွင် :ref:`Processing <sec_processing_intro>` algorithm များကို menu ခွဲများအဖြစ် အုပ်စုဖွဲ့၍ ထည့်သွင်းထားပြီး provider အမျိုးမျိုးမှ raster ကို အခြေခံသည့် အသုံးများသည့် GIS လုပ်ဆောင်ချက်များအတွက် ဖြတ်လမ်းနည်းများကိုလည်း ပံ့ပိုးပေးထားပါသည်။ အကယ်၍ ထို Menu ခွဲများအားလုံးကို မရရှိသေးလျှင် :menuselection:`Plugins --> Manage and Install Plugins...` ထဲရှိ  Processing plugin ကို ဖွင့်၍ အသုံးပြုနိုင်သည်။

Algorithm များစာရင်းနှင့် ၎င်း၏ menu များကို Processing algorithms တစ်ခုခု ( :ref:`processing.options` ကို ဖတ်ရှုပါ) သို့မဟုတ် အချို့သောပြင်ပ :ref:`plugins <plugins>` ဖြင့် ပြင်ဆင်ခြင်း၊ တိုးချဲ့လုပ်ဆောင်ခြင်းများ ပြုလုပ်နိုင်ပါသည်။


Database
---------

ဤပုံစံသည် ပင်မ plugin များအားလုံးကိုဖွင့်ထားလျှင် :guilabel:`Database` menu ကို မြင်တွေ့ရမည့် ပုံစံဖြစ်ပါသည်။ အကယ်၍ database plugin များ ကိုဖွင့်ထားခြင်းမရှိလျှင် :guilabel:`Database` menu ကိုမြင်တွေ့ရမည်မဟုတ်ပါ။ 


.. list-table:: Database menu တွင် ပါဝင်သည့် item များ
   :header-rows: 1
   :widths: 40 15 15 30


   * - Menu ရွေးချယ်စရာများ
     - ဖြတ်လမ်းနည်း
     - Toolbar
     - အကိုးအကား
   * - :guilabel:`Offline editing...`
     - :kbd:`Alt+D` + :kbd:`O`
     -
     - :ref:`offlinedit`
   * - :menuselection:`-->`
       |offlineEditingCopy| :guilabel:`Convert to Offline Project...`
     -
     - :guilabel:`Database`
     - :ref:`offlinedit`
   * - :menuselection:`-->`
       |offlineEditingSync| :guilabel:`Synchronize`
     -
     - :guilabel:`Database`
     - :ref:`offlinedit`
   * - |dbManager| :guilabel:`DB Manager...`
     -
     - :guilabel:`Database`
     - :ref:`dbmanager`


QGIS ကို ပထမဆုံးအကြိမ် အသုံးပြုခြင်းဖြစ်လျှင် ၎င်းတွင် ပင်မ plugin များအားလုံး ပါရှိဦးမည်မဟုတ်ပါ။

Web
----

ဤပုံစံသည် ပင်မ plugin များအားလုံးကိုဖွင့်ထားလျှင် :guilabel:`Web`  menu ကို မြင်တွေ့ရမည့် ပုံစံဖြစ်ပါသည်။ အကယ်၍ web plugin များကိုဖွင့်ထားခြင်းမရှိလျှင်  :guilabel:`Web` menu ကိုမြင်တွေ့ရမည်မဟုတ်ပါ။ 


.. list-table:: Web menu တွင် ပါဝင်သည့် item များ
   :header-rows: 1
   :widths: 30 15 15 40


   * - Menu ရွေးချယ်စရာများ
     - ဖြတ်လမ်းနည်း
     - Toolbar
     - အကိုးအကား
   * - :menuselection:`MetaSearch -->`
     - :kbd:`Alt+W` + :kbd:`M`
     -
     - :ref:`metasearch`
   * - :menuselection:`-->`
       |metasearch| :guilabel:`Metasearch`
     -
     - :guilabel:`Web`
     - :ref:`metasearch`
   * - :menuselection:`--> Help`
     -
     -
     - :ref:`metasearch`


QGIS ကို ပထမဆုံးအကြိမ် အသုံးပြုခြင်းဖြစ်လျှင် ၎င်းတွင် ပင်မ plugin များအားလုံး ပါရှိဦးမည်မဟုတ်ပါ။


Mesh (ဝါယာပုံစံကွန်ယက်ဖြင့် ဖော်ပြထားသည့် အရာများ)
---------------------------------------------------

:menuselection:`Mesh` menu သည် :ref:`mesh layers <label_meshdata>` ကို ကိုင်တွယ်အသုံးပြုရန်ရန်လိုအပ်သော tool များကို ပံ့ပိုးပေးထားပါသည်။ Third-party plugin များကိုအသုံးပြု၍လည်း item များကို ဤ menu ထဲသို့ ထည့်သွင်းနိုင်ပါသည်။ 

.. list-table::  Mesh menu တွင် ပါဝင်သည့် item များ
   :header-rows: 1
   :widths: 40 15 15 30
   :stub-columns: 0


   * - Menu ရွေးချယ်စရာများ
     - ဖြတ်လမ်းနည်း
     - Toolbar
     - အကိုးအကား
   * - |showMeshCalculator| :menuselection:`Mesh Calculator...`
     -
     -
     - :ref:`mesh_calculator`
   * - |meshReindex| :menuselection:`Reindex Faces and Vertices`
     -
     -
     - :ref:`reindex_mesh`


Processing (လုပ်ငန်းစဉ်များဆောင်ရွက်ခြင်း)
-------------------------------------------


.. list-table:: Processing menu တွင် ပါဝင်သည့် item များ
   :header-rows: 1
   :widths: 30 20 10 40


   * - Menu ရွေးချယ်စရာများ
     - ဖြတ်လမ်းနည်း
     - Toolbar
     - အကိုးအကား
   * - |processingAlgorithm| :guilabel:`Toolbox`
     - :kbd:`Ctrl+Alt+T`
     -
     - :ref:`processing.toolbox`
   * - |processingModel| :guilabel:`Model Designer...`
     - :kbd:`Ctrl+Alt+G`
     -
     - :ref:`processing.modeler`
   * - |processingHistory| :guilabel:`History...`
     - :kbd:`Ctrl+Alt+H`
     -
     - :ref:`processing.history`
   * - |processingResult| :guilabel:`Results Viewer`
     - :kbd:`Ctrl+Alt+R`
     -
     - :ref:`processing.results`
   * - |processSelected| :guilabel:`Edit Features In-Place`
     -
     -
     - :ref:`processing_inplace_edit`


QGIS ကို ပထမဆုံးအကြိမ် အသုံးပြုခြင်းဖြစ်လျှင် ၎င်းတွင် ပင်မ plugin များအားလုံး ပါရှိဦးမည်မဟုတ်ပါ။


Help (အကူအညီ)
--------------


.. list-table:: Help menu တွင် ပါဝင်သည့် item များ
   :header-rows: 1
   :widths: 40 15 15 30


   * - Menu ရွေးချယ်စရာများ
     - ဖြတ်လမ်းနည်း
     - Toolbar
     - အကိုးအကား
   * - |helpContents| :guilabel:`Help Contents`
     - :kbd:`F1`
     - :guilabel:`Help`
     -
   * - :guilabel:`API Documentation`
     -
     -
     -
   * - :menuselection:`Plugins -->`
     -
     -
     -
   * - :guilabel:`Report an Issue`
     -
     -
     -
   * - :guilabel:`Need commercial support?`
     -
     -
     -
   * - |qgisHomePage| :guilabel:`QGIS Home Page`
     - :kbd:`Ctrl+H`
     -
     -
   * - |success| :guilabel:`Check QGIS Version`
     -
     -
     -
   * - |logo| :guilabel:`About`
     -
     -
     -
   * - |helpSponsors| :guilabel:`QGIS Sustaining Members`
     -
     -
     -

QGIS
-----

ဤ menu သည် |osx| macOS တွင်သာ ရရှိနိုင်ပြီး OS နှင့်ပတ်သက်သည့် command (ခိုင်းစေချက်) အချို့လည်း ပါဝင်ပါသည်။ 


.. csv-table::  QGIS menu တွင် ပါဝင်သည့် item များ
   :header: "Menu ရွေးချယ်စရာများ", "ဖြတ်လမ်းနည်း"
   :widths: auto


   ":guilabel:`Preferences`"
   ":guilabel:`About QGIS`"
   ":guilabel:`Hide QGIS`" 
   ":guilabel:`Show All`"
   ":guilabel:`Hide Others`"
   ":guilabel:`Quit QGIS`", ":kbd:`Cmd+Q`"

အခြား platform များအတွက် :guilabel:`Preferences` (ကြိုက်နှစ်သက်ရာများ) သည် အခြား OS များရှိ :menuselection:`Settings --> Options` နှင့်သက်ဆိုင်ပါသည်၊ :guilabel:`About QGIS` (QGIS အကြောင်း) သည် :menuselection:`Help --> About` နှင့်လည်းကောင်း၊ :guilabel:`Quit QGIS` (QGIS မှထွက်ခြင်း) သည် :menuselection:`Project --> Exit QGIS` နှင့်သက်ဆိုင်ပါသည်။

.. _sec_panels_and_toolbars:


Panels and Toolbars (Panel များနှင့် Toolbar များ)
===================================================

QGIS widget များဖြစ်သော (:menuselection:`Panels -->`) နှင့် toolbar (:menuselection:`Toolbars -->`) တို့ကို :menuselection:`View` menu (သို့မဟုတ် |kde| :menuselection:`Settings`)မှ အဖွင့်/အပိတ် ပြုလုပ်နိုင်ပါသည်။ ၎င်းတို့ကို အဖွင့်/အပိတ် ပြုလုပ်လိုလျှင် menu bar သို့မဟုတ် toolbar ကို right-click နှိပ်ပြီး မိမိအလိုရှိသော item ကိုရွေးချယ်၍ ပြုလုပ်နိုင်ပါသည်။ Panel နှင့် toolbar များကို QGIS interface တွင် မိမိထားချင်သည့်နေရာသို့ ရွှေ့ခြင်း၊ နေရာချခြင်းများ ပြုလုပ်နိုင်ပါသည်။ စာရင်းများကို :ref:`Core or external plugins <plugins>` (ပင်မ plugin သို့မဟုတ် ပြင်ပမှထည့်သွင်းသည့် plugin)ကို ဖွင့်၍ ထပ်မံထည့်သွင်းနိုင်ပါသည်။ 


.. index:: Toolbars
.. _`label_toolbars`:


Toolbars
---------

Toolbar သည် menu ထဲရှိ လုပ်ဆောင်ချက် (function) အများစုကို ဝင်ရောက်အသုံးပြုနိုင်ခြင်းအပြင် မြေပုံနှင့်သက်ဆိုင်သည့် အခြား tool များကိုလည်း ပံ့ပိုးပေးထားပါသည်။ Toolbar ထဲရှိ item တစ်ခုချင်းစီတွင် လိုအပ်သည့် အကူအညီများကိုရရှိနိုင်သော pop-up များ ပါဝင်ပါသည်။ Item ပေါ်တွင် mouse ကို တင်လိုက်လျှင် tool ၏ အသုံးပြုပုံအကျဉ်းချုပ်ကို မြင်တွေ့ရမည်ဖြစ်ပါသည်။ 

ရရှိနိုင်သည့် toolbar များမှာ-


.. csv-table:: QGIS Toolbar များ
   :header: "Toolbar အမည်", "Tool များအတွက် အဓိက အကိုးအကား"
   :widths: auto


   ":guilabel:`Advanced Digitizing`", ":ref:`sec_advanced_edit`"
   ":guilabel:`Annotations`", ":ref:`sec_annotations`"
   ":guilabel:`Attributes`", ":ref:`sec_attribute_table`, :ref:`general_tools`"
   ":guilabel:`Data Source Manager`", ":ref:`manage_data_source`"
   ":guilabel:`Database`", ":ref:`dbmanager`"
   ":guilabel:`Digitizing`", ":ref:`sec_edit_existing_layer`"
   ":guilabel:`GRASS`", ":ref:`sec_grass`"
   ":guilabel:`Help`"
   ":guilabel:`Label`", ":ref:`label_toolbar`"
   ":guilabel:`Manage Layers`", ":ref:`opening_data`"
   ":guilabel:`Map Navigation`", ":ref:`zoom_pan`"
   ":guilabel:`Mesh Digitizing`", ":ref:`editing_mesh`"
   ":guilabel:`Plugins`", ":ref:`plugins.index`"
   ":guilabel:`Project`", ":ref:`project_files`, :ref:`label_printlayout`, :ref:`vector_symbol_library`"
   ":guilabel:`Processing Algorithms`", ":ref:`processing.options`"
   ":guilabel:`Raster`", ":ref:`plugins.index`"
   ":guilabel:`Selection`",":ref:`sec_selection`"
   ":guilabel:`Shape digitizing`", ":ref:`shape_edit`"
   ":guilabel:`Snapping`",":ref:`snapping_tolerance`"
   ":guilabel:`Vector`", ":ref:`plugins.index`"
   ":guilabel:`Web`", ":ref:`plugins.index`, :ref:`metasearch`"

.. note:: Third-party plugin (ပြင်ပမှထည့်သွင်းသည့် plugin) များသည် ပုံသေ tool များတွင် ၎င်းတို့၏  tool များပေါင်းထည့်စေခြင်းအပြင် ၎င်းတို့၏ ကိုယ်ပိုင် toolbar ကိုလည်း ပံ့ပိုးပေးပါသည်။

.. index::
   single: Toolbars; Layout

.. tip:: **Toolbar များကို ပြန်လည်ရယူခြင်း**

   အကယ်၍ toolbar တစ်ခုကို မတော်တဆဖယ်ရှားမိပါက :menuselection:`View --> Toolbars -->` (သို့မဟုတ် |kde| :menuselection:`Settings --> Toolbars -->`) ကိုအသုံးပြု၍ ပြန်လည်ရယူနိုင်ပါသည်။ အချို့သော အကြောင်းအရာများကြောင့် QGIS မျက်နှာပြင်မှ toolbar တစ်ခု (သို့မဟုတ် အခြားသော widget) လုံးဝပျောက်ကွယ်သွားမည်ဆိုလျှင် :ref:`restoring initial GUI <tip_restoring_configuration>` တွင် ပြန်လည်ရရှိနိုင်မည့် အချက်အလက်များကို ရှာဖွေရမည်ဖြစ်ပါသည်။ 


.. index:: Panels
.. _panels_tools:

Panels
-------

QGIS တွင် Panel များစွာပါရှိပြီး ၎င်း Panel များသည် ရွေးချယ်စရာများကို ရွေးချယ်ခြင်း၊ လေးထောင့်ကွက်(box)များကို အမှန်ခြစ်ပြုလုပ်ခြင်း၊ တန်ဖိုးများကိုထည့်သွင်းခြင်း..စသည့် ပိုမိုရှုပ်ထွေးသည့်လုပ်ငန်းဆောင်တာများ လုပ်ဆောင်နိုင်သည့် သီးသန့် widget များဖြစ်ပါသည်။ 

QGIS တွင် ပုံသေအားဖြင့်တွေ့နိုင်သည့် panel များကို အောက်တွင် ဖော်ပြထားပါသည်- 


.. list-table:: QGIS Panel များ
   :header-rows: 1
   :widths: auto


   * - Panel အမည်
     - ဖြတ်လမ်းနည်း
     - အကိုးအကား
   * - :guilabel:`Advanced Digitizing`
     - :kbd:`Ctrl+4`
     - :ref:`advanced_digitizing_panel`
   * - :guilabel:`Browser`
     - :kbd:`Ctrl+2`
     - :ref:`browser_panel`
   * - :guilabel:`Browser (2)`
     -
     - :ref:`browser_panel`
   * - :guilabel:`Debugging/Development Tools`
     - :kbd:`F12`
     - :ref:`debug_dev_tools`
   * - :guilabel:`Elevation Profile`
     -
     -
   * - :guilabel:`Geometry Validation`
     -
     - :ref:`digitizingmenu`
   * - :guilabel:`GPS Information`
     - :kbd:`Ctrl+0`
     - :ref:`sec_gpstracking`
   * - :guilabel:`GRASS Tools`
     -
     - :ref:`sec_grass`
   * - :guilabel:`Layer Order`
     - :kbd:`Ctrl+9`
     - :ref:`layer_order`
   * - :guilabel:`Layer Styling`
     - :kbd:`Ctrl+3`
     - :ref:`layer_styling_panel`
   * - :guilabel:`Layers`
     - :kbd:`Ctrl+1`
     - :ref:`label_legend`
   * - :guilabel:`Log Messages`
     -
     - :ref:`log_message_panel`
   * - :guilabel:`Overview`
     - :kbd:`Ctrl+8`
     - :ref:`overview_panels`
   * - :guilabel:`Processing Toolbox`
     -
     - :ref:`processing.toolbox`
   * - :guilabel:`Results Viewer`
     -
     - :ref:`processing.toolbox`
   * - :guilabel:`Snapping and Digitizing Options`
     -
     - :ref:`snapping_tolerance`
   * - :guilabel:`Spatial Bookmark Manager`
     - :kbd:`Ctrl+7`
     - :ref:`sec_bookmarks`
   * - :guilabel:`Statistics`
     - :kbd:`Ctrl+6`
     - :ref:`statistical_summary`
   * - :guilabel:`Temporal Controller`
     -
     - :ref:`temporal_controller`
   * - :guilabel:`Tile Scale`
     -
     - :ref:`tilesets`
   * - :guilabel:`Undo/Redo`
     - :kbd:`Ctrl+5`
     - :ref:`undo_redo_panel`
   * - :guilabel:`Vertex Editor`
     -
     - :ref:`vertex_editor_panel`


.. _`label_statusbar`:

Status Bar (အခြေအနေပြဘား)
==========================

Status bar တွင် မြေပုံမြင်ကွင်း၊ ဆောင်ရွက်ပြီးစီးသည့် သို့မဟုတ် ရရှိနိုင်သည့် လုပ်ဆောင်ချက်များနှင့်ပတ်သက်သည့် ယေဘုယျအချက်အလက်များကို ဖော်ပြပေးပြီး မြေပုံမြင်ကွင်းကို ကိုင်တွယ်စီမံနိုင်သည့် tool များကိုလည်း တွေ့ရှိနိုင်သည်။

.. _`locator_bar`:

Locator bar (တည်နေရာပြဘား)
---------------------------

Status bar ၏ ဘယ်ဘက်ရှိ တည်နေရာပြ bar သည် QGIS တွင် လုပ်ဆောင်နိုင်သော feature နှင့် ရွေးချယ်စရာများကို အလွယ်တကူရှာဖွေနိုင်သည့် widget တစ်ခုဖြစ်ပါသည်။ 


#. တည်နေရာပြ bar တွင် ရှာဖွေမူကို ဖွင့်ရန် text widget (စာသားရိုက်ရမည့် widget) ကို နှိပ်ပါ။ သို့မဟုတ် :kbd:`Ctrl+K` ကို နှိပ်၍ဖွင့်ပါ။
#. မိမိရှာဖွေလိုသော item နှင့်ပတ်သက်သည့် စာသား (အမည်၊ တွဲလုံး၊ အဓိကစကားလုံး စသည်) တို့ကို ရိုက်ထည့်ပါ။ ပုံသေအနေဖြင့် locator filter (တည်နေရာစစ်ထုတ်ခြင်း) များအတွက် အဖြေရရှိနိုင်သော်လည်း  :ref:`locator filters <locator_options>` ၏ prefix (ရှေ့ဆက်စကားလုံး) ဖြင့် ရှာဖွေလိုသည့်အကြောင်းအရာကို ကန့်သတ်ထားနိုင်ပါသည်။ ဆိုလိုသည်မှာ ``l cad`` ဟု ရိုက်ထည့်ပါက နာမည်တွင် ``cad`` ပါဝင်သည့် Layer များကိုသာ ထုတ်ပေးမည်ဖြစ်ပါသည်။ 


   Locator widget ရှိ menu ကို နှစ်ချက်နှိပ်၍ အသုံးပြုမည့် filter ကို ရွေးချယ်နိုင်ပါသည်။ 

#. Item အမျိုးအစားပေါ်မူတည်၍ သက်ဆိုင်ရာလုပ်ဆောင်ချက်များကို လုပ်ဆောင်ရန် ရလာဒ် (result) ပေါ်တွင် နှိပ်ပါ။ 


.. tip:: **လက်ရှိအသုံးပြုနေသော Layer ၏ သီးသန့် field များကို ရှာဖွေမှုကို ကန့်သတ်ခြင်း**

  ပုံမှန်အားဖြင့် "active layer features" (လက်ရှိအသုံးပြုလျက်ရှိသော Layer ၏ အရာဝတ္ထုများ) filter (``f``) ဖြင့် ရှာဖွေမှုသည် Layer ၏ attribute table (အချက်အလက်ဇယား) တစ်ခုလုံးကို ဖော်ပြစေပြီး သီးသန့် field တစ်ခုချင်းစီကို ရှာဖွေရန် ``@`` prefix ကို အသုံးပြု၍ ကန့်သတ်ထားနိုင်ပါသည်။ ဥပမာ- ``f @name sal`` သို့မဟုတ် ``@name sal`` ဟုရိုက်၍ ရှာဖွေပါက "name" attribute တွင် 'sal' ပါဝင်သည့် feature များကိုသာ ရရှိစေမည်ဖြစ်ပါသည်။ :kbd:`Tab` key ကို အသုံးပြု၍ အလိုအလျောက် စာသားပြည့်စုံအောင် ပြုလုပ်နိုင်ပါသည်။

  Query လုပ်ထားသော field များကို ပိုမိုအဆင့်မြင့်စွာ ထိန်းချုပ်ရန် Layer ၏ :guilabel:`Fields` tab တွင် တွေ့ရှိနိုင်မည်ဖြစ်ပြီး အသေးစိတ်သိရှိလိုသည်များအတွက် :ref:`vector_fields_menu` တွင် ဖတ်ရှုနိုင်ပါသည်။ 


Item များကို မြန်ဆန်စွာ ရှာဖွေရန် thread များကို အသုံးပြုနိုင်ပြီး နှေးကွေးသော search filter ကိုသုံး၍ရှာဖွေသည့်အချိန်တွင်လည်း ပိုမိုမြန်ဆန်စေရန် အသုံးပြုနိုင်ပါသည်။ ၎င်းတို့သည် Filter တစ်ခုကို အသုံးပြုလိုက်သည်နှင့်ပေါ်လာမည်ဖြစ်သည်။ ဆိုလိုသည်မှာ ဖိုင်တွဲတစ်ခုကို scan ဖတ်လိုက်လျှင် ရလာဒ်များသည် တစ်ခုပြီးတစ်ခု ထွက်ပေါ်လာလိမ့်မည်။ အွန်လိုင်းကို အသုံးပြု၍ ရှာဖွေသည့် အလွန်နှေးကွေးသော search filter များရှိနေလျှင်ပင် UI (user interface) ကို အမြဲတမ်းတုံ့ပြန်မှုရှိစေပါသည်။

.. note:: Nominatim locator tool (nominatim တည်နေရာပြ tool) သည် OpenStreetMap Nominatim `usage policy <https:// operations.osmfoundation.org/policies/nominatim/>`_ (OpenStreetMap Nominatim ၏ အသုံးပြုမှုမူဝါဒ)နှင့်အညီ ကွဲပြားစွာ လုပ်ဆောင်ပေးပါသည်။ (အလိုအလျောက်ပြီးမြောက်စေသော ရှာဖွေခြင်း၊ ထွက်ပေါ်လာမည့် ရလာဒ်များရယူရန် ကြန့်ကြာစေခြင်း..စသည်)


.. tip:: **Locator ၏ configurations (ပြင်ဆင်သတ်မှတ်ခြင်း) ကို အလွယ်တကူရောက်ရှိစေခြင်း** 


  အသုံးပြုနိုင်သည့် filter စာရင်းကို ပြသရန် status bar ပေါ်ရှိ locator widget ထဲမှ |search| icon ကို နှိပ်ပါ။ ထို့နောက် :guilabel:`Configure` entry ကို နှိပ်၍ :menuselection:`Settings -->Options...` menu ရှိ  :guilabel:`Locator` tab ကို ပွင့်လာစေပါသည်။ 


Reporting actions (အစီရင်ခံခြင်းလုပ်ဆောင်ချက်များ)
---------------------------------------------------

Locator bar ဘေးရှိနေရာတွင် ဆောင်ရွက်ပြီးသော လုပ်ဆောင်ချက်များ (Layer တစ်ခုတွင် feature တစ်ခုကို ရွေးချယ်ခြင်း၊ Layer ကိုဖယ်ရှားခြင်း၊ Pan အကွာအဝေးနှင့်လားရာ စသည်) ၏အကျဉ်းချုပ်ကို လိုအပ်လျှင် ကြည့်ရှုနိုင်ပြီး tool များပေါ်တွင် mouse တင်လိုက်ပါက ၎င်းတို့၏ ရှင်းလင်းချက်ကိုလည်း တွေ့ရမည်ဖြစ်သည်။ (သို့သော် tool များအားလုံးတွင် ရရှိနိုင်မည်မဟုတ်ပေ။)

Raster layer များမှ စာရင်းအင်းအချက်အလက်များကို စုဆောင်းခြင်း၊ Processing algorithms ကို ဆောင်ရွက်ခြင်း သို့မဟုတ် မြေပုံမြင်ကွင်းတွင် Layer များစွာကို rendering (ပုံဖော်ပြသခြင်း) ပြုလုပ်ခြင်း ကဲ့သို့သော ကြာရှည်စွာလုပ်ဆောင်ရမည့် လုပ်ငန်းများအတွက် လုပ်ဆောင်နေကြောင်းပြသသည့် progress bar ကို status bar တွင် ပြသမည်ဖြစ်ပါသည်။ 


Control the map canvas (မြေပုံမြင်ကွင်းကို ထိန်းချုပ်ခြင်း)
------------------------------------------------------------

|tracking| :guilabel:`Coordinate` option သည် မြေပုံမြင်ကွင်းတစ်လျှောက် mouse ရောက်ရှိသည့်နေရာကို ပြသပြီး :menuselection:`Project --> Properties... --> General` tab ထဲတွင် ယူနစ်များ (နှင့် တိကျမှု) ကို သတ်မှတ်နိုင်သည်။ Textbox ၏ဘယ်ဘက်ရှိ ခလုတ်ငယ်ကို နှိပ်၍ coordinate option (ကိုဩဒိနိတ်ရွေးချယ်မှု) နှင့် |extents| :guilabel:`Extents` option (မြေပုံ၏နယ်ပယ်အကျယ်အဝန်း) တို့အကြား တစ်လှည့်စီအဖွင့်အပိတ်ပြုလုပ်နိုင်သည်။ |extents| :guilabel:`Extents` option သည် လက်ရှိမြေပုံမြင်ကွင်း၏ ဘယ်ဘက်အောက်ခြေနှင့် ညာဘက်ထိပ်၏ ကိုဩဒိနိတ်များကို မြေပုံယူနစ်ဖြင့် ဖော်ပြပေးပါသည်။


ကိုဩဒိနိတ် ပြသမှုဘေးတွင် မြေပုံမြင်ကွင်း၏ :guilabel:`Scale` (စကေး) ပြသမှုကို တွေ့ရမည် ဖြစ်သည်။ ၎င်းအပြင် :ref:`predefined and custom scales <predefinedscales>` (ကြိုတင်သတ်မှတ်ထားသည့်မြေပုံစကေးနှင့် စိတ်ကြိုက်သတ်မှတ်ထားသည့်မြေပုံစကေး) နှစ်ခုအကြား စကေးရွေးချယ်နိုင်သည့်အရာတစ်ခုရှိပါသည်။ 


.. index:: Magnification
.. _magnifier:

စကေးပြသမှု၏ ညာဘက်ဘေးတွင် စကေးကိုပိတ်၍ မြေပုံကို ချုံ့ /ချဲ့ကြည့်နိုင်ရန် |lockedGray| ခလုတ်ကိုနှိပ်ပါ။ Magnifier (မှန်ဘီလူး) သည် မြေပုံစကေးကို မပြောင်းလဲစေဘဲ မြေပုံကို ချဲ့ကြည့်နိုင်ပြီး သင်္ကေတနှင့် အညွှန်းများကို ပြောင်းလဲရာတွင် လွယ်ကူစေရန် ကူညီပေးသည်။ Magnifier သည် ချဲ့ကြည့်နိုင်သည့်အဆင့်ကို ရာခိုင်နှုန်းဖြင့်ဖော်ပြပြီး အကယ်၍ :guilabel:`Magnifier` သည် ၁၀၀ ရာခိုင်နှုန်းသို့ ရောက်ရှိနေပါက လက်ရှိမြေပုံကို ချဲ့ကြည့်တော့မည်မဟုတ်ပါ။ ဆိုလိုသည်မှာ လက်ရှိမြေပုံကို monitor (ကွန်ပျူတာဖန်သားပြင်) ၏ resolution (ကြည်လင်ပြတ်သားမှု) (DPI) နှင့်သက်ဆိုင်သည့် စကေးအတိအကျ၌ ပုံဖော်ပြသနေခြင်းဖြစ်သည်။ ချဲ့ကြည့်နိုင်သည့်တန်ဖိုးကို ပုံသေသတ်မှတ်လိုပါက  :menuselection:`Settings --> Options --> Rendering --> Rendering Behavior` တွင် ဆောင်ရွက်နိုင်ပြီး ၎င်းသည် ကြည်လင်ပြတ်သားမှုမြင့်သည့် screen များတွင် သေးငယ်သောသင်္ကေတများကို ကြီးမားအောင်ပြောင်းလဲရာတွင် အလွန်အသုံးဝင်ပါသည်။ ထို့အပြင်  :menuselection:`Settings --> Options --> Canvas & Legend --> DPI` ထဲရှိ setting တစ်ခုသည် QGIS တွင် monitor ၏ Physical DPI သို့မဟုတ် system ၏ Logical DPI အသုံးပြုခြင်းကို ထိန်းချုပ်ပေးပါသည်။

Magnifier tool ၏ ညာဘက်တွင် မြေပုံမြင်ကွင်းကို နာရီလက်တံအတိုင်းလှည့်မည့် လှည့်ထောင့်ကို ဒီဂရီဖြင့် သတ်မှတ်ပေးနိုင်ပါသည်။

Status bar ၏ ညာဘက်ရှိ |checkbox| :guilabel:`Render` သည် မြေပုံမြင်ကွင်း rendering ပြုလုပ်ခြင်းကို ယာယီရပ်တန့်ထားလိုသောအခါ အသုံးပြုနိုင်သည်။ (အသေးစိတ်ကို :ref:`redraw_events` အပိုင်းတွင် ကြည့်ရှုနိုင်ပါသည်။)


|checkbox| :guilabel:`Render` function ၏ ညာဘက်တွင် လက်ရှိအသုံးပြုနေသော project  ၏ CRS (ကိုဩဒိနိတ်ရည်ညွှန်းစနစ်) ကိုပြသနေသော |projectionEnabled| :guilabel:`EPSG:code` ခလုတ်ကို တွေ့နိုင်ပါသည်။ ၎င်းကို နှိပ်လိုက်လျှင် :guilabel:`Project Properties` dialog ပွင့်လာပြီး မြေပုံမြင်ကွင်းကို reproject (အရိပ်ချစနစ်ပြောင်းလဲခြင်း) လုပ်ခြင်း သို့မဟုတ် project property (ပရောဂျက်၏ဂုဏ်သတ္တိများ) တစ်ခုခုကို ချိန်ညှိခြင်း စသည်တို့ကို ပြုလုပ်နိုင်ပါသည်။


.. index::
   single: Scale calculate


.. tip::
   **မြေပုံမြင်ကွင်း၏ မှန်ကန်သော စကေးကို တွက်ယူခြင်း**


   QGIS ကိုစတင်အသုံးပြုသောအခါ CRS သည် ပုံသေအားဖြင့် ``WGS 84 (EPSG 4326)`` ဖြစ်ပြီး ယူနစ်မှာ ဒီဂရီ ဖြစ်ပါသည်။ ဆိုလိုသည်မှာ QGIS သည် အသုံးပြုလိုက်သော Layer ရှိ မည်သည့်ကိုဩဒိနိတ်ကိုမဆို ဒီဂရီအဖြစ်ဖော်ပြသွားမည်ဖြစ်သည်။ မှန်ကန်သောစကေးတန်ဖိုးရရှိရန် :menuselection:`Project --> Properties...` အောက်ရှိ :guilabel:`General` tab တွင်ရှိသော setting (ဥပမာ- မီတာသို့) ကိုပြောင်းလဲ၍သော်လည်းကောင်း အထက်တွင်ဖော်ပြခဲ့သော |projectionEnabled| :sup:`EPSG:code` icon ကိုအသုံးပြု၍သော်လည်းကောင်း ဆောင်ရွက်နိုင်ပါသည်။ ဒုတိယနည်းလမ်းကို အသုံးပြုပါက project ၏ projection တွင်သတ်မှတ်ထားသည့် ယူနစ်များအတိုင်း သတ်မှတ်မည်ဖြစ်ပါသည်။ (ဥပမာ - ``+units=us-ft``)

   စတင်အသုံးပြုသည့်အချိန် CRS ရွေးချယ်ခြင်းကို :menuselection:`Settings --> Options --> CRS Handling` ထဲတွင် သတ်မှတ်နိုင်ပါသည်။


Messaging (စာတိုပြသခြင်း)
--------------------------

CRS icon ဘေးတွင်ရှိသော |messageLog| :sup:`Messages` ခလုတ်သည် ဆောင်ရွက်ဆဲ လုပ်ငန်းဆောင်တာ (QGIS startup ၊ plugins loading ၊ processing tools...စ‌သော) များနှင့်ပတ်သက်သည့် အချက်အလက်များကို ဖော်ပြသည့် :guilabel:`Log Messages Panel` ကိုပွင့်လာစေပါသည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
 This will be automatically updated by the find_set_subst.py script. If you need to create a new substitution manually, please add it also to the substitutions.txt file in the source folder.


.. |24To8Bits| image:: /static/common/24-to-8-bits.png
   :width: 1.5em
.. |8To24Bits| image:: /static/common/8-to-24-bits.png
   :width: 1.5em
.. |addAfsLayer| image:: /static/common/mActionAddAfsLayer.png
   :width: 1.5em
.. |addAllToOverview| image:: /static/common/mActionAddAllToOverview.png
   :width: 1.5em
.. |addDelimitedTextLayer| image:: /static/common/mActionAddDelimitedTextLayer.png
   :width: 1.5em
.. |addGeometryAttributes| image:: /static/common/mAlgorithmAddGeometryAttributes.png
   :width: 1.5em
.. |addGpsLayer| image:: /static/common/mActionAddGpsLayer.png
   :width: 1.5em
.. |addGrid| image:: /static/common/add_grid.png
   :width: 1.5em
.. |addHanaLayer| image:: /static/common/mActionAddHanaLayer.png
   :width: 1.5em
.. |addImage| image:: /static/common/mActionAddImage.png
   :width: 1.5em
.. |addMap| image:: /static/common/mActionAddMap.png
   :width: 1.5em
.. |addMeshLayer| image:: /static/common/mActionAddMeshLayer.png
   :width: 1.5em
.. |addMssqlLayer| image:: /static/common/mActionAddMssqlLayer.png
   :width: 1.5em
.. |addOgrLayer| image:: /static/common/mActionAddOgrLayer.png
   :width: 1.5em
.. |addOracleLayer| image:: /static/common/mActionAddOracleLayer.png
   :width: 1.5em
.. |addPart| image:: /static/common/mActionAddPart.png
   :width: 1.5em
.. |addPointCloudLayer| image:: /static/common/mActionAddPointCloudLayer.png
   :width: 1.5em
.. |addPostgisLayer| image:: /static/common/mActionAddPostgisLayer.png
   :width: 1.5em
.. |addRasterLayer| image:: /static/common/mActionAddRasterLayer.png
   :width: 1.5em
.. |addRing| image:: /static/common/mActionAddRing.png
   :width: 2em
.. |addSpatiaLiteLayer| image:: /static/common/mActionAddSpatiaLiteLayer.png
   :width: 1.5em
.. |addVectorTileLayer| image:: /static/common/mActionAddVectorTileLayer.png
   :width: 1.5em
.. |addVirtualLayer| image:: /static/common/mActionAddVirtualLayer.png
   :width: 1.5em
.. |addWcsLayer| image:: /static/common/mActionAddWcsLayer.png
   :width: 1.5em
.. |addWfsLayer| image:: /static/common/mActionAddWfsLayer.png
   :width: 1.5em
.. |addWmsLayer| image:: /static/common/mActionAddWmsLayer.png
   :width: 1.5em
.. |addXyzLayer| image:: /static/common/mActionAddXyzLayer.png
   :width: 1.5em
.. |allEdits| image:: /static/common/mActionAllEdits.png
   :width: 1.5em
.. |basicStatistics| image:: /static/common/mAlgorithmBasicStatistics.png
   :width: 1.5em
.. |buffer| image:: /static/common/mAlgorithmBuffer.png
   :width: 1.5em
.. |captureLine| image:: /static/common/mActionCaptureLine.png
   :width: 1.5em
.. |capturePoint| image:: /static/common/mActionCapturePoint.png
   :width: 1.5em
.. |capturePolygon| image:: /static/common/mActionCapturePolygon.png
   :width: 1.5em
.. |centroids| image:: /static/common/mAlgorithmCentroids.png
   :width: 1.5em
.. |checkGeometry| image:: /static/common/mAlgorithmCheckGeometry.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |circle2Points| image:: /static/common/mActionCircle2Points.png
   :width: 1.5em
.. |circle2TangentsPoint| image:: /static/common/mActionCircle2TangentsPoint.png
   :width: 1.5em
.. |circle3Points| image:: /static/common/mActionCircle3Points.png
   :width: 1.5em
.. |circle3Tangents| image:: /static/common/mActionCircle3Tangents.png
   :width: 1.5em
.. |circleCenterPoint| image:: /static/common/mActionCircleCenterPoint.png
   :width: 1.5em
.. |circularStringCurvePoint| image:: /static/common/mActionCircularStringCurvePoint.png
   :width: 1.5em
.. |circularStringRadius| image:: /static/common/mActionCircularStringRadius.png
   :width: 1.5em
.. |clip| image:: /static/common/mAlgorithmClip.png
   :width: 1.5em
.. |collect| image:: /static/common/mAlgorithmCollect.png
   :width: 1.5em
.. |contour| image:: /static/common/contour.png
   :width: 1.5em
.. |convexHull| image:: /static/common/mAlgorithmConvexHull.png
   :width: 1.5em
.. |copyrightLabel| image:: /static/common/copyright_label.png
   :width: 1.5em
.. |createGPX| image:: /static/common/create_gpx.png
   :width: 1.5em
.. |createGrid| image:: /static/common/mAlgorithmCreateGrid.png
   :width: 1.5em
.. |createMemory| image:: /static/common/mActionCreateMemory.png
   :width: 1.5em
.. |customProjection| image:: /static/common/mActionCustomProjection.png
   :width: 1.5em
.. |dataSourceManager| image:: /static/common/mActionDataSourceManager.png
   :width: 1.5em
.. |dbManager| image:: /static/common/dbmanager.png
   :width: 1.5em
.. |delaunay| image:: /static/common/mAlgorithmDelaunay.png
   :width: 1.5em
.. |deletePart| image:: /static/common/mActionDeletePart.png
   :width: 2em
.. |deleteRing| image:: /static/common/mActionDeleteRing.png
   :width: 2em
.. |deleteSelectedFeatures| image:: /static/common/mActionDeleteSelectedFeatures.png
   :width: 1.5em
.. |deselectActiveLayer| image:: /static/common/mActionDeselectActiveLayer.png
   :width: 1.5em
.. |deselectAll| image:: /static/common/mActionDeselectAll.png
   :width: 1.5em
.. |difference| image:: /static/common/mAlgorithmDifference.png
   :width: 1.5em
.. |dissolve| image:: /static/common/mAlgorithmDissolve.png
   :width: 1.5em
.. |distanceMatrix| image:: /static/common/mAlgorithmDistanceMatrix.png
   :width: 1.5em
.. |duplicateLayer| image:: /static/common/mActionDuplicateLayer.png
   :width: 1.5em
.. |editCopy| image:: /static/common/mActionEditCopy.png
   :width: 1.5em
.. |editCut| image:: /static/common/mActionEditCut.png
   :width: 1.5em
.. |editPaste| image:: /static/common/mActionEditPaste.png
   :width: 1.5em
.. |ellipseCenter2Points| image:: /static/common/mActionEllipseCenter2Points.png
   :width: 1.5em
.. |ellipseCenterPoint| image:: /static/common/mActionEllipseCenterPoint.png
   :width: 1.5em
.. |ellipseExtent| image:: /static/common/mActionEllipseExtent.png
   :width: 1.5em
.. |ellipseFoci| image:: /static/common/mActionEllipseFoci.png
   :width: 1.5em
.. |expressionSelect| image:: /static/common/mIconExpressionSelect.png
   :width: 1.5em
.. |extents| image:: /static/common/extents.png
   :width: 1.5em
.. |extractLayerExtent| image:: /static/common/mAlgorithmExtractLayerExtent.png
   :width: 1.5em
.. |extractVertices| image:: /static/common/mAlgorithmExtractVertices.png
   :width: 1.5em
.. |fileExit| image:: /static/common/mActionFileExit.png
.. |fileNew| image:: /static/common/mActionFileNew.png
   :width: 1.5em
.. |fileOpen| image:: /static/common/mActionFileOpen.png
   :width: 1.5em
.. |fileSave| image:: /static/common/mActionFileSave.png
   :width: 1.5em
.. |fileSaveAs| image:: /static/common/mActionFileSaveAs.png
   :width: 1.5em
.. |fillRing| image:: /static/common/mActionFillRing.png
   :width: 1.5em
.. |formAnnotation| image:: /static/common/mActionFormAnnotation.png
   :width: 1.5em
.. |formSelect| image:: /static/common/mIconFormSelect.png
   :width: 1.5em
.. |geometryChecker| image:: /static/common/geometrychecker.png
   :width: 1.5em
.. |georefRun| image:: /static/common/mGeorefRun.png
   :width: 1.5em
.. |grid| image:: /static/common/grid.png
   :width: 1.5em
.. |helpContents| image:: /static/common/mActionHelpContents.png
   :width: 1.5em
.. |helpSponsors| image:: /static/common/mActionHelpSponsors.png
   :width: 1.5em
.. |hideAllLayers| image:: /static/common/mActionHideAllLayers.png
   :width: 1.5em
.. |hideDeselectedLayers| image:: /static/common/mActionHideDeselectedLayers.png
   :width: 1.5em
.. |hideSelectedLayers| image:: /static/common/mActionHideSelectedLayers.png
   :width: 1.5em
.. |htmlAnnotation| image:: /static/common/mActionHtmlAnnotation.png
   :width: 1.5em
.. |identify| image:: /static/common/mActionIdentify.png
   :width: 1.5em
.. |inOverview| image:: /static/common/mActionInOverview.png
   :width: 1.5em
.. |interfaceCustomization| image:: /static/common/mActionInterfaceCustomization.png
   :width: 1.5em
.. |intersect| image:: /static/common/mAlgorithmIntersect.png
   :width: 1.5em
.. |invertSelection| image:: /static/common/mActionInvertSelection.png
   :width: 1.5em
.. |kde| image:: /static/common/kde.png
   :width: 1.5em
.. |keyboardShortcuts| image:: /static/common/mActionKeyboardShortcuts.png
   :width: 1.5em
.. |labelingSingle| image:: /static/common/labelingSingle.png
   :width: 1.5em
.. |layoutManager| image:: /static/common/mActionLayoutManager.png
   :width: 1.5em
.. |lineIntersections| image:: /static/common/mAlgorithmLineIntersections.png
   :width: 1.5em
.. |lineToPolygon| image:: /static/common/mAlgorithmLineToPolygon.png
   :width: 1.5em
.. |lockedGray| image:: /static/common/lockedGray.png
   :width: 1.2em
.. |logo| image:: /static/common/logo.png
   :width: 1.5em
.. |mapTips| image:: /static/common/mActionMapTips.png
   :width: 1.5em
.. |meanCoordinates| image:: /static/common/mAlgorithmMeanCoordinates.png
   :width: 1.5em
.. |measure| image:: /static/common/mActionMeasure.png
   :width: 1.5em
.. |measureAngle| image:: /static/common/mActionMeasureAngle.png
   :width: 1.5em
.. |measureArea| image:: /static/common/mActionMeasureArea.png
   :width: 1.5em
.. |measureBearing| image:: /static/common/mActionMeasureBearing.png
   :width: 1.5em
.. |merge| image:: /static/common/merge.png
   :width: 1.5em
.. |mergeFeatureAttributes| image:: /static/common/mActionMergeFeatureAttributes.png
   :width: 1.5em
.. |mergeFeatures| image:: /static/common/mActionMergeFeatures.png
   :width: 1.5em
.. |mergeLayers| image:: /static/common/mAlgorithmMergeLayers.png
   :width: 1.5em
.. |meshReindex| image:: /static/common/mActionMeshReindex.png
   :width: 1.5em
.. |messageLog| image:: /static/common/mMessageLog.png
   :width: 1.5em
.. |metasearch| image:: /static/common/MetaSearch.png
   :width: 1.5em
.. |moveFeature| image:: /static/common/mActionMoveFeature.png
   :width: 1.5em
.. |moveFeatureCopy| image:: /static/common/mActionMoveFeatureCopy.png
   :width: 1.5em
.. |moveFeatureCopyLine| image:: /static/common/mActionMoveFeatureCopyLine.png
   :width: 1.5em
.. |moveFeatureCopyPoint| image:: /static/common/mActionMoveFeatureCopyPoint.png
   :width: 1.5em
.. |moveFeatureLine| image:: /static/common/mActionMoveFeatureLine.png
   :width: 1.5em
.. |moveFeaturePoint| image:: /static/common/mActionMoveFeaturePoint.png
   :width: 1.5em
.. |multiEdit| image:: /static/common/mActionMultiEdit.png
   :width: 1.5em
.. |multiToSingle| image:: /static/common/mAlgorithmMultiToSingle.png
   :width: 1.5em
.. |nearblack| image:: /static/common/nearblack.png
   :width: 1.5em
.. |nearestNeighbour| image:: /static/common/mAlgorithmNearestNeighbour.png
   :width: 1.5em
.. |new3DMap| image:: /static/common/mActionNew3DMap.png
   :width: 1.5em
.. |newBookmark| image:: /static/common/mActionNewBookmark.png
   :width: 1.5em
.. |newElevationProfile| image:: /static/common/mActionNewElevationProfile.png
   :width: 1.5em
.. |newGeoPackageLayer| image:: /static/common/mActionNewGeoPackageLayer.png
   :width: 1.5em
.. |newLayout| image:: /static/common/mActionNewLayout.png
   :width: 1.5em
.. |newMap| image:: /static/common/mActionNewMap.png
   :width: 1.5em
.. |newMeshLayer| image:: /static/common/mActionNewMeshLayer.png
   :width: 1.5em
.. |newReport| image:: /static/common/mActionNewReport.png
   :width: 1.5em
.. |newSpatiaLiteLayer| image:: /static/common/mActionNewSpatiaLiteLayer.png
   :width: 1.5em
.. |newTableRow| image:: /static/common/mActionNewTableRow.png
   :width: 1.5em
.. |newVectorLayer| image:: /static/common/mActionNewVectorLayer.png
   :width: 1.5em
.. |newVirtualLayer| image:: /static/common/mActionNewVirtualLayer.png
   :width: 1.5em
.. |northArrow| image:: /static/common/north_arrow.png
   :width: 1.5em
.. |offlineEditingCopy| image:: /static/common/offline_editing_copy.png
   :width: 1.5em
.. |offlineEditingSync| image:: /static/common/offline_editing_sync.png
   :width: 1.5em
.. |offsetCurve| image:: /static/common/mActionOffsetCurve.png
   :width: 1.5em
.. |offsetPointSymbols| image:: /static/common/mActionOffsetPointSymbols.png
   :width: 1.5em
.. |openTable| image:: /static/common/mActionOpenTable.png
   :width: 1.5em
.. |openTableEdited| image:: /static/common/mActionOpenTableEdited.png
   :width: 1.5em
.. |openTableSelected| image:: /static/common/mActionOpenTableSelected.png
   :width: 1.5em
.. |openTableVisible| image:: /static/common/mActionOpenTableVisible.png
   :width: 1.5em
.. |options| image:: /static/common/mActionOptions.png
   :width: 1em
.. |osx| image:: /static/common/osx.png
   :width: 1em
.. |pan| image:: /static/common/mActionPan.png
   :width: 1.5em
.. |panToSelected| image:: /static/common/mActionPanToSelected.png
   :width: 1.5em
.. |polygonToLine| image:: /static/common/mAlgorithmPolygonToLine.png
   :width: 1.5em
.. |polygonize| image:: /static/common/polygonize.png
   :width: 1.5em
.. |processSelected| image:: /static/common/mActionProcessSelected.png
   :width: 1.5em
.. |processingAlgorithm| image:: /static/common/processingAlgorithm.png
   :width: 1.5em
.. |processingHistory| image:: /static/common/history.png
   :width: 1.5em
.. |processingModel| image:: /static/common/processingModel.png
   :width: 1.5em
.. |processingResult| image:: /static/common/processingResult.png
   :width: 1.5em
.. |projectProperties| image:: /static/common/mActionProjectProperties.png
   :width: 1.5em
.. |projectionAdd| image:: /static/common/projection-add.png
   :width: 1.5em
.. |projectionEnabled| image:: /static/common/mIconProjectionEnabled.png
   :width: 1.5em
.. |projectionExport| image:: /static/common/projection-export.png
   :width: 1.5em
.. |providerGdal| image:: /static/common/providerGdal.png
   :width: 1.5em
.. |proximity| image:: /static/common/proximity.png
   :width: 1.5em
.. |pythonFile| image:: /static/common/mIconPythonFile.png
   :width: 1.5em
.. |qgisHomePage| image:: /static/common/mActionQgisHomePage.png
   :width: 1.5em
.. |randomPointsInPolygons| image:: /static/common/mAlgorithmRandomPointsInPolygons.png
   :width: 1.5em
.. |randomPointsOnLines| image:: /static/common/mAlgorithmRandomPointsOnLines.png
   :width: 1.5em
.. |randomPointsWithinExtent| image:: /static/common/mAlgorithmRandomPointsWithinExtent.png
   :width: 1.5em
.. |randomPointsWithinPolygon| image:: /static/common/mAlgorithmRandomPointsWithinPolygon.png
   :width: 1.5em
.. |rasterClip| image:: /static/common/raster-clip.png
   :width: 1.5em
.. |rasterInfo| image:: /static/common/raster-info.png
   :width: 1.5em
.. |rasterOverview| image:: /static/common/raster-overview.png
   :width: 1.5em
.. |rasterize| image:: /static/common/rasterize.png
   :width: 1.5em
.. |rectangle3PointsDistance| image:: /static/common/mActionRectangle3PointsDistance.png
   :width: 1.5em
.. |rectangle3PointsProjected| image:: /static/common/mActionRectangle3PointsProjected.png
   :width: 1.5em
.. |rectangleCenter| image:: /static/common/mActionRectangleCenter.png
   :width: 1.5em
.. |rectangleExtent| image:: /static/common/mActionRectangleExtent.png
   :width: 1.5em
.. |redo| image:: /static/common/mActionRedo.png
   :width: 1.5em
.. |refresh| image:: /static/common/mActionRefresh.png
   :width: 1.5em
.. |regularPoints| image:: /static/common/mAlgorithmRegularPoints.png
   :width: 1.5em
.. |regularPolygon2Points| image:: /static/common/mActionRegularPolygon2Points.png
   :width: 1.5em
.. |regularPolygonCenterCorner| image:: /static/common/mActionRegularPolygonCenterCorner.png
   :width: 1.5em
.. |regularPolygonCenterPoint| image:: /static/common/mActionRegularPolygonCenterPoint.png
   :width: 1.5em
.. |removeAllFromOverview| image:: /static/common/mActionRemoveAllFromOverview.png
   :width: 1.5em
.. |removeLayer| image:: /static/common/mActionRemoveLayer.png
   :width: 1.5em
.. |reshape| image:: /static/common/mActionReshape.png
   :width: 1.5em
.. |reverseLine| image:: /static/common/mActionReverseLine.png
   :width: 1.5em
.. |rotateFeature| image:: /static/common/mActionRotateFeature.png
   :width: 1.5em
.. |rotatePointSymbols| image:: /static/common/mActionRotatePointSymbols.png
   :width: 1.5em
.. |saveAsPDF| image:: /static/common/mActionSaveAsPDF.png
   :width: 1.5em
.. |saveMapAsImage| image:: /static/common/mActionSaveMapAsImage.png
   :width: 1.5em
.. |scaleBar| image:: /static/common/mActionScaleBar.png
   :width: 1.5em
.. |scaleFeature| image:: /static/common/mActionScaleFeature.png
   :width: 1.5em
.. |search| image:: /static/common/search.png
   :width: 1.5em
.. |selectAll| image:: /static/common/mActionSelectAll.png
   :width: 1.5em
.. |selectDistance| image:: /static/common/mAlgorithmSelectDistance.png
   :width: 1.5em
.. |selectFreehand| image:: /static/common/mActionSelectFreehand.png
   :width: 1.5em
.. |selectLocation| image:: /static/common/mAlgorithmSelectLocation.png
   :width: 1.5em
.. |selectPolygon| image:: /static/common/mActionSelectPolygon.png
   :width: 1.5em
.. |selectRadius| image:: /static/common/mActionSelectRadius.png
   :width: 1.5em
.. |selectRandom| image:: /static/common/mAlgorithmSelectRandom.png
   :width: 1.5em
.. |selectRectangle| image:: /static/common/mActionSelectRectangle.png
   :width: 1.5em
.. |showAllLayers| image:: /static/common/mActionShowAllLayers.png
   :width: 1.5em
.. |showBookmarks| image:: /static/common/mActionShowBookmarks.png
   :width: 1.5em
.. |showMeshCalculator| image:: /static/common/mActionShowMeshCalculator.png
   :width: 1.5em
.. |showPluginManager| image:: /static/common/mActionShowPluginManager.png
   :width: 1.5em
.. |showRasterCalculator| image:: /static/common/mActionShowRasterCalculator.png
   :width: 1.5em
.. |showSelectedLayers| image:: /static/common/mActionShowSelectedLayers.png
   :width: 1.5em
.. |sieve| image:: /static/common/sieve.png
   :width: 1.5em
.. |simplify| image:: /static/common/mActionSimplify.png
   :width: 1.5em
.. |simplify_2| image:: /static/common/mAlgorithmSimplify.png
   :width: 1.5em
.. |splitFeatures| image:: /static/common/mActionSplitFeatures.png
   :width: 1.5em
.. |splitLayer| image:: /static/common/mAlgorithmSplitLayer.png
   :width: 1.5em
.. |splitParts| image:: /static/common/mActionSplitParts.png
   :width: 1.5em
.. |styleManager| image:: /static/common/mActionStyleManager.png
   :width: 1.5em
.. |success| image:: /static/common/mIconSuccess.png
   :width: 1em
.. |sum| image:: /static/common/mActionSum.png
   :width: 1.2em
.. |sumLengthLines| image:: /static/common/mAlgorithmSumLengthLines.png
   :width: 1.5em
.. |sumPoints| image:: /static/common/mAlgorithmSumPoints.png
   :width: 1.5em
.. |svgAnnotation| image:: /static/common/mActionSvgAnnotation.png
   :width: 1.5em
.. |symmetricalDifference| image:: /static/common/mAlgorithmSymmetricalDifference.png
   :width: 1.5em
.. |textAnnotation| image:: /static/common/mActionTextAnnotation.png
   :width: 1.5em
.. |tiles| image:: /static/common/tiles.png
   :width: 1.5em
.. |titleLabel| image:: /static/common/title_label.png
   :width: 1.5em
.. |toggleEditing| image:: /static/common/mActionToggleEditing.png
   :width: 1.5em
.. |toggleSelectedLayers| image:: /static/common/mActionToggleSelectedLayers.png
   :width: 1.5em
.. |topologyChecker| image:: /static/common/mActionTopologyChecker.png
   :width: 1.5em
.. |tracking| image:: /static/common/tracking.png
   :width: 1.5em
.. |translate| image:: /static/common/translate.png
   :width: 1.5em
.. |trimExtend| image:: /static/common/mActionTrimExtend.png
   :width: 1.5em
.. |undo| image:: /static/common/mActionUndo.png
   :width: 1.5em
.. |union| image:: /static/common/mAlgorithmUnion.png
   :width: 1.5em
.. |uniqueValues| image:: /static/common/mAlgorithmUniqueValues.png
   :width: 1.5em
.. |vertexTool| image:: /static/common/mActionVertexTool.png
   :width: 1.5em
.. |vertexToolActiveLayer| image:: /static/common/mActionVertexToolActiveLayer.png
   :width: 1.5em
.. |voronoi| image:: /static/common/mAlgorithmVoronoi.png
   :width: 1.5em
.. |vrt| image:: /static/common/vrt.png
   :width: 1.5em
.. |warp| image:: /static/common/warp.png
   :width: 1.5em
.. |zoomActual| image:: /static/common/mActionZoomActual.png
   :width: 1.5em
.. |zoomFullExtent| image:: /static/common/mActionZoomFullExtent.png
   :width: 1.5em
.. |zoomIn| image:: /static/common/mActionZoomIn.png
   :width: 1.5em
.. |zoomLast| image:: /static/common/mActionZoomLast.png
   :width: 1.5em
.. |zoomNext| image:: /static/common/mActionZoomNext.png
   :width: 1.5em
.. |zoomOut| image:: /static/common/mActionZoomOut.png
   :width: 1.5em
.. |zoomToLayer| image:: /static/common/mActionZoomToLayer.png
   :width: 1.5em
.. |zoomToSelected| image:: /static/common/mActionZoomToSelected.png
   :width: 1.5em