.. index:: Layout; Label item
.. _layout_label_item:

The Label Item (အညွှန်း Item)
==============================

.. only:: html

   .. contents::
      :local:

:guilabel:`Label` item သည် မြေပုံကိုနားလည်စေရန် ခေါင်းစဉ်၊ မြေပုံပြင်ဆင်သူ၊ data အရင်းအမြစ်များနှင့်အခြားအချက်အလက်များ ကဲ့သို့သောစာများထည့်သွင်း အလှဆင်ရန်ကူညီပေးသည့် tool တစ်ခုဖြစ်သည်။ :ref:`Item များဖန်တီးခြင်းဆိုင်ရာ ညွှန်ကြားချက်များ <create_layout_item>` များအတိုင်း |label| :guilabel:`Add Label` tool ကိုအသုံးပြု၍ label (အညွှန်း)တစ်ခုထည့်သွင်းနိုင်ပြီး ၎င်းကို :ref:`interact_layout_item` တွင်ရှင်းပြထားသည့်အတိုင်း ကိုင်တွယ်နိုင်မည်ဖြစ်သည်။

Default အားဖြင့် label item တွင်၎င်း၏ :guilabel:`Item Properties` panel အားအသုံးပြု၍ စိတ်ကြိုက်ပြင်ဆင်နိုင်သည့် ကြိုတင်သတ်မှတ်စာသားတစ်ခုပါရှိသည်။ :ref:`Item များ၏ common ဂုဏ်သတ္တိများ <item_common_properties>` များအပြင် ဤ feature တွင် အောက်ပါလုပ်ဆောင်ချက်များပါ ရှိသည် (:numref:`figure_layout_label` ကိုကြည့်ပါ)-

.. _figure_layout_label:

.. figure:: img/label_mainproperties.png
   :align: center

   Label Item ဂုဏ်သတ္တိများ Panel

.. _layout_label_main_properties:

Main properties (အဓိက ဂုဏ်သတ္တိများ)
-------------------------------------

:guilabel:`Main properties` အုပ်စုသည် label အတွက် စာသားထည့်သွင်းနိုင်သည့်နေရာဖြစ်သည်။ စာသားများကို အသေသတ်မှတ်ထားနိုင် (static) သကဲ့သို့ :ref:`expression <expression_builder>` ၏ လုပ်ဆောင်ချက်များ၊ ကိန်းရှင်များအလိုက် ပြောင်းလဲနိုင် (dynamic) ပြီး HTML ဖြင့်ပုံစံချထားသည်။ Label တစ်ခု၏ Dynamic အစိတ်အပိုင်းများကို အဓိပ္ပာယ်ဖော်ပြီး  တွက်ထုတ်အဖြေရှာနိုင်ရန် ``[%`` နှင့် ``%]`` အတွင်း ထည့်ထားရန်လိုအပ်ပါသည်။ 

* Label များတွင် expression များအားအသုံးပြုရန် :guilabel:`Insert/Edit Expression...` ခလုတ်အား click နှိပ်နိုင်ပြီး ပုံမှန်အတိုင်း ပုံသေနည်းကိုရေး၍ dialog အား အသုံးပြုသည့်အခါ QGIS သည် အဖွင့်အပိတ် သင်္ကေတစာလုံးများကို အလိုအလျောက်ထည့်သွင်းပေးမည်ဖြစ်သည်။
   
  .. hint:: Textbox ထဲတွင် ဘာတစ်ခုမျှရွေးချယ်ထားခြင်းမရှိဘဲ :guilabel:`Insert/Edit Expression...` ခလုတ်အား click နှိပ်ပါက ရှိပြီးသားစာသားနောက်တွင် expression အသစ်အား ဆက်တွဲပေါင်းထည့်မည်ဖြစ်သည်။ ရှိပြီးသား expression တစ်ခုအားပြုပြင်မွမ်းမံလိုလျှင် ပထမဆုံးအနေနှင့် ပြုပြင်မွမ်းမံလိုသော အစိတ်အပိုင်းကိုရွေးချယ်ရန်လိုအပ်သည်။ 

  များသောအားဖြင့် မြေပုံများတွင် အသုံးများသော အချက်အလက်စာသားအချို့ (ရက်စွဲ၊ မြေပုံပြင်ဆင်သူ၊ ခေါင်းစဉ်နှင့် စာမျက်နှာနံပါတ်...) ပါဝင်သောကြောင့် QGIS တွင် သက်ဆိုင်ရာ  expression များ သို့မဟုတ် variable များကို တိုက်ရိုက်ဝင်ရောက်ကြည့်ရှုနိုင်သည်- ၎င်းတို့ကိုရွေးချယ်၍ label ထဲသို့ထည့်သွင်းရန် :guilabel:`Dynamic text` ခလုတ်ကို နှိပ်ပါ။
 
  .. tip::  ရွေးချယ်ထားသော ကြိုတင်သတ်မှတ်ထားသည့် expression ဖြင့် ဖြည့်ထားသော label အသစ်တစ်ခုကို ဖန်တီးရန် ထိပ်ဆုံး menu မှ :menuselection:`Add Item --> Add Dynamic Text -->` အားအသုံးပြုနိုင်ပါသည်။
  
  Dynamic label တစ်ခုအား static label တစ်ခုအဖြစ်ပြောင်းလဲနိုင်သည် -  :guilabel:`Insert/Edit Expression...` ခလုတ်ဘေးမှ drop-down (ရွေးချယ်နိုင်သော) မြှားအားနှိပ်၍ :guilabel:`Convert to Static` အားရွေးချယ်ပါ။ Label အကြောင်းအရာများ၏ မည်သည့် dynamic အစိတ်အပိုင်းများကိုမဆို ဖော်ထုတ်၍ ၎င်းတို့၏လက်ရှိ တန်ဖိုးများနှင့်အစားထိုးမည်ဖြစ်သည်။ ထို့နောက်တွင်   ရရှိလာသည့်စာသားများကို ကိုယ်တိုင် လိုအပ်သလို ချိန်ညှိနိုင်မည်ဖြစ်သည်။

* Label များကို HTML code အဖြစ်အဓိပ္ပာယ်ဖော်နိုင်ပါသည် - |checkbox|:guilabel:`Render as HTML` တွင် အမှန်ခြစ်ပါ။ ယခုအခါ  HTML tag များ သို့မဟုတ် style များ၊ URL၊ web စာမျက်နှာတစ်ခုဆီသို့ချိတ်ဆက်ထားသော click နှိပ်၍ရသည့် ရုပ်ပုံတစ်ခု သို့မဟုတ် ပိုမိုရှုပ်ထွေးသည့်အရာများကို စသည်တို့ကို ထည့်သွင်းနိုင်ပြီဖြစ်သည်။

အောက်ပါ codeသည် အဆင့်မြင့် label တပ်ခြင်းတစ်ခုအတွက် HTML rendering နှင့် expression များကို ပေါင်းစပ်ပြီး ရလာဒ် အနေဖြင့် :numref:`figure_layout_label_html` အားထုတ်လုပ်ပေးမည်ဖြစ်သည်-
 
.. code-block:: css

 <html>
  <head>
    <style>
       /* Define some custom styles, with attribute-based size */
       name {color:red; font-size: [% ID %]px; font-family: Verdana; text-shadow: grey 1px 0 10px;}
       use {color:blue;}
    </style>
  </head>

  <body>
    <!-- Information to display -->
    <u>Feature Information</u>
    <ul style="list-style-type:disc">
      <li>Feature Id: [% ID %]</li>
      <li>Airport: <name>[% NAME %]</name></li>
      <li>Main use: <use>[% USE %]</use></li>
    </ul>
    Last check: [% concat( format_date( "control_date", 'yyyy-MM-dd'), ' by <b><i>', @user_full_name, '</i></b>' ) %]

    <!-- Insert an image -->
    <p align=center><img src="path/to/logos/qgis-logo-made-with-color.svg" alt="QGIS icon" style="width:80px;height:50px;"</p>
  </body>
 </html>

.. _figure_layout_label_html:

.. figure:: img/label_htmlexpression.png
   :align: center

   HTML style အားအသုံးပြု၍ label တစ်ခုကို မြင်သာစေရန် စိတ်ကြိုက်ပြင်ဆင်ခြင်း


Appearance (ပုံစံသွင်ပြင်)
---------------------------

*  :guilabel:`Font` ခလုတ်ပေါ်တွင် click နှိပ်ခြင်းဖြင့် စာသားများ၏ စာလုံးဖောင့်နှင့် style တို့ကိုသတ်မှတ်နိုင်သည်။ :guilabel:`Label Font` menuထဲတွင်  :ref:`Formatting the label text <text_format>` (Label စာသားများ format ပြင်ဆင်ခြင်း) အတွက် ရွေးချယ်စရာများထဲမှအချို့ကို အသုံးပြုနိုင်သည်။
  
* မတူညီသော အလျားလိုက်အနားသတ် (horizontal margin) နှင့် ဒေါင်လိုက်အနားသတ် (vertical margin) များကို ``mm`` ဖြင့် သတ်မှတ်နိုင်သည်။ ၎င်းသည် layout item ၏ အစွန်းမှ အနားသတ်ဖြစ်သည်။ Label အား ၎င်း၏ဘောင်များကိုကျော်လွန်၍ နေရာချထားနိုင်ပါသည်၊ ဥပမာအားဖြင့် label အား အခြား item များနှင့် တစ်တန်းတည်းဖြစ်စေရန်ချိန်ညှိရာတွင် ဖြစ်သည်။ ဤနေရာတွင် အနားသတ်အတွက် အနုတ်တန်ဖိုးများကို အသုံးပြုရန်လိုအပ်ပါသည်။
* Label အားနေရာချထားရန် အခြားနည်းလမ်းတစ်ခုမှာ text alignment (စာသားချိန်ညှိမှု) ကို အသုံးပြုခြင်းဖြစ်သည်။ စာသားချိန်ညှိမှုမှာ အောက်ပါအတိုင်းဖြစ်နိုင်ပါသည်-

  * :guilabel:`Horizontal alignment` (အလျားလိုက်ချိန်ညှိမှု) အတွက်:guilabel:`Left`၊ :guilabel:`Center`၊ :guilabel:`Right` သို့မဟုတ် :guilabel:`Justify`
  * နှင့် :guilabel:`Vertical alignment` (ဒေါင်လိုက်လိုက်ချိန်ညှိမှု) အတွက် :guilabel:`Top`၊ :guilabel:`Middle`၊  :guilabel:`Bottom`
     
.. _layout_label_expressions:

Exploring expressions in a label item (Label item တစ်ခုထဲရှိ expression များကိုစူးစမ်းလေ့လာခြင်း)
--------------------------------------------------------------------------------------------------

Label item အားစိတ်ဝင်စားဖွယ်အချက်အလက်များနှင့်ဖြည့်စွက်ရန် အသုံးပြုနိုင်မည့် expression ဥပမာအချို့ကိုအောက်တွင်ဖော်ပြထားပါသည်။ သတိပြုရမည့်အချက်မှာ :guilabel:`Main properties` frame ထဲတွင် code သို့မဟုတ် အနည်းဆုံးအနေဖြင့် တွက်ချက်ထားသော အပိုင်းအား ``[%`` နှင့် ``%]`` ထဲတွင်ထည့်သွင်းထားရန်ဖြစ်သည်။


* "field1" ထဲရှိ လက်ရှိ atlas feature တန်ဖိုးဖြင့် ခေါင်းစဉ်တစ်ခုကို ပြပါ-

  ::

    'This is the map for ' || "field1"

  သို့မဟုတ် :guilabel:`Main properties` အပိုင်းတွင်ထည့်သွင်းရန်မှာ-

  ::

    This is the map for [% "field1" %]

* လုပ်ဆောင်ပြီးသော atlas feature များအတွက်စာမျက်နှာနံပါတ်များထည့်သွင်းခြင်း (ဥပမာ- ``Page 1/10``)-

  ::

    concat( 'Page ', @atlas_featurenumber, '/', @atlas_totalfeatures )

* လက်ရှိ atlas region ရှိ လေဆိပ်များ၏ အမည်များကို ၎င်းတို့၏ common ဖြစ်သော attribute များအပေါ် အခြေခံ၍ ရယူပါ-
  

  ::

    aggregate( layer := 'airports',
               aggregate := 'concatenate',
               expression := "NAME",
               filter := fk_regionId = attribute( @atlas_feature, 'ID' ),
               concatenator := ', '
             )

  သို့မဟုတ် :ref:`attributes relation <vector_relations>` (Attribute ဆက်နွယ်မှု) အားသတ်မှတ်အသုံးပြုလျှင်-

  ::

    relation_aggregate( relation := 'airports_in_region_relation',
                        aggregate := 'concatenate',
                        expression := "NAME",
                        concatenator := ', '
                      )

* လက်ရှိ atlas region ရှိ လေဆိပ်များ၏ အမည်များကို ၎င်းတို့၏ spatial relationship (တည်နေရာဆိုင်ရာဆက်စပ်မှု) ပေါ်မူတည်၍ ရယူပါ-

  ::

    aggregate( layer := 'airports',
               aggregate := 'concatenate',
               expression := "NAME",
               filter := contains( geometry( @parent ), $geometry ),
               concatenator := ', '
             )

  သို့မဟုတ်::

    array_to_string( array:= overlay_contains( layer := 'airports',
                                               expression := "NAME" ),
                     delimiter:= ', '
                   )

* ``Map 1`` item အကျယ်အဝန်းနယ်နိမိတ်၏  X ကိုသြဒိနိတ် အနိမ့်တန်ဖိုးကို ရယူပါ-

  ::

    x_min( map_get( item_variables( 'Map 1' ), 'map_extent' ) )

* လက်ရှိ layout ``Map 1`` item တွင်ပါဝင်သော layer များ၏အမည်များကိုရယူ၍ အမည်တစ်ခုစီကို တစ်ကြောင်းစီဖြင့်ပုံစံချပါ-
  

  ::

   array_to_string(
    array_foreach(
     map_get( item_variables( 'Map 1' ), 'map_layers' ), -- retrieve the layers list
     layer_property( @element, 'name' ) -- retrieve each layer name
    ),
    '\n' -- converts the list to string separated by breaklines
   )

* Layout ``Map 1`` item တစ်ခုရှိ layer များစာရင်းအား ၎င်းတို့၏လိုင်စင်စာကြောင်းများ(အသုံးပြုခွင့်) ဖြင့် စာရင်းပြုစုပြသပါ။ Layer များ၏ :ref:`Access metadata <metadatamenu>` ဂုဏ်သတ္တိများကို ဦးစွာဖြည့်ရန်လိုအပ်သည်-

  ::

   array_to_string( map_credits( 'Map 1', true ) )


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |label| image:: /static/common/mActionLabel.png
   :width: 1.5em
