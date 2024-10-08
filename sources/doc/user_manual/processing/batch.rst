.. _processing_batch:

The batch processing interface (အစုအစည်းအလိုက်လုပ်ဆောင်ခြင်းဆိုင်ရာ Interface)
===============================================================================

.. only:: html

   .. contents::
      :local:

Introduction (မိတ်ဆက်)
-----------------------

Model များအပါအဝင် algorithm များအားလုံးကို တစ်စုတစ်စည်းတည်း (batch) အဖြစ် စုပေါင်းစေခိုင်းနိုင်ပါသည်။ ထည့်သွင်းအသုံးပြုသော data တစ်စုတည်းအသုံးပြုပြီးလုပ်ဆောင်ရုံတင်မကဘဲ အများအပြားကို လိုအပ်သလောက် အကြိမ်အရေအတွက်ထိ လုပ်ဆောင်နိုင်ပါသည်။ Algorithm ကို toolbox မှ အကြိမ်များစွာ ဖွင့်ပြီးလုပ်ဆောင်ရန်မလိုသောကြောင့် data အများကြီးကို processing လုပ်ဆောင်သောအခါ ဒီနည်းလမ်းသည် အသုံးဝင်ပါသည်။

Algorithm ကို တစ်စုတစ်စည်းတည်းအဖြစ် စုပေါင်းစေခိုင်းရန် toolbox ထဲရှိ နာမည်ကို right-click နှိပ်ပြီး ပေါ်လာသော menu မှ :guilabel:`Execute as batch process` ကိုရွေးချယ်ပါ။

.. _figure_processing_batch_start:

.. figure:: img/batch_processing_right_click.png
   :align: center

   Right-click နှိပ်ခြင်းမှ Batch processing

Algorithm ၏ လုပ်ဆောင်မှု dialog ကိုဖွင့်ထားပြီးလျှင် :guilabel:`Run as batch process...` ခလုတ်ကို နှိပ်ပြီး batch processing ကို စတင်နိုင်ပါသည်။

.. _figure_processing_batch_start2:

.. figure:: img/parameters_dialog.png
   :align: center

   Algorithm Dialog မှ Batch processing

The parameters table  (Parameter များ ဇယား)
--------------------------------------------

Batch processing လုပ်ခြင်းသည် algorithm တစ်ခု၏ တစ်ခုစာ လုပ်ဆောင်ခြင်းနှင့် ဆင်တူပါသည်။ Parameter တန်ဖိုးများကိုသတ်မှတ်ပေးရပါမည်၊ သို့သော် ယခုဥပမာတွင် parameter တစ်ခုချင်းစီအတွက် တန်ဖိုးတစ်ခုကိုသာ လိုအပ်သည်မဟုတ်ပဲ တစ်စုတစ်စည်းလုံးစာအတွက် လိုအပ်ပြီး algorithm တစ်ခါလုပ်ဆောင်တိုင်းအတွက် တစ်ခုလိုအပ်ပါသည်။ တန်ဖိုးများကို ပြသထားသော ဇယားပုံစံမျိုးကိုအသုံးပြုပြီး ထည့်သွင်းပါသည်။ ဇယားထဲတွင် row တစ်ခုချင်းစီသည် iteration (row တစ်ခုကို တစ်ခါလုပ်ဆောင်ခြင်း) ဖြစ်ပြီး column များသည် algorithm ၏ parameter များဖြစ်ပါသည်။

.. _figure_processing_batch_parameters:

.. figure:: img/batch_processing.png
   :align: center

   Batch Processing


အပေါ်ဘက်တွင်ရှိသော toolbar မှ အောက်ပါတို့ကိုလုပ်ဆောင်နိုင်ပါသည် -

* |symbologyAdd| :sup:`Add row` - ပြင်ဆင်သတ်မှတ်ခြင်းအတွက် processing entry အသစ်တစ်ခုထည့်ခြင်း။
* |symbologyRemove| :sup:`Remove row(s)` - ဇယားမှ ရွေးချယ်ထားသော row များကိုဖယ်ရှားပစ်ခြင်း။ ဘယ်ဘက်ရှိ ဂဏန်းပေါ်တွင် click နှိပ်ခြင်းဖြင့် row ကိုရွေးချယ်နိုင်ပါသည်။ :ref:`keyboard combination <interacting_features_table>` ကိုအသုံးပြုပြီး row များစွာရွေးချယ်နိုင်ပါသည်။
* |fileOpen| :sup:`Open` - Batch Processing ပြင်ဆင်သတ်မှတ်ခြင်း file တစ်ခုကို ဖွင့်ခြင်း
* |fileSave| :sup:`Save` - Batch Processing ပြင်ဆင်ထားခြင်းကို နောက်ပိုင်းတွင် အသုံးပြုနိုင်သော :file:`.JSON` file ထဲတွင် သိမ်းဆည်းထားခြင်း

ပုံမှန်အားဖြင့် ဇယားသည် row နှစ်ခုသာ ပါဝင်ပါသည် -

* ပထမ row တွင် အောက်တွင် cell များကိုအမြန်ဖြည့်ရန် :ref:`options <batch_parameters>` များဖြင့် :menuselection:`Autofill... -->` drop-down menu တစ်ခုကို cell တစ်ခုချင်းဆီတွင် ဖော်ပြပေးပါသည်။ ရရှိနိုင်သော option များသည် parameter အမျိုးအစားပေါ်တွင် မူတည်ပါသည်။
* ဒုတိယ row သည် (ကပ်လျက်ဖြစ်သော row တစ်ခုစီတိုင်းလည်း) algorithm ၏ တစ်ခုချင်း စေခိုင်းလုပ်ဆောင်မှုကို ကိုယ်စားပြုပြီး cell တစ်ခုချင်းသည် parameter များထဲမှ တစ်ခု၏ တန်ဖိုးပါဝင်ပါသည်။ Toolbox မှ algorithm တစ်ခုကို စေခိုင်းလုပ်ဆောင်သောအခါ မြင်ရသော parameters dialog နှင့် ဆင်တူသော်လည်း စီစဉ်ထားမှုမတူညီပါ။

ဇယား၏အောက်ခြေတွင် |checkbox| :guilabel:`Load layers on completion` ကို အမှန်ခြစ်ထား/မခြစ်ထားမည်ကို သတ်မှတ်ပေးနိုင်ပါသည်။

ဇယား၏အရွယ်အစားသတ်မှတ်ပြီးသည်နှင့် လိုချင်သောတန်ဖိုးများကို ထည့်သွင်းပေးရပါမည်။

.. _batch_parameters:

Filling the parameters table (Parameter များ ဇယားကို အချက်အလက် ထည့်သွင်းခြင်း)
-------------------------------------------------------------------------------

Parameter အများစုအတွက် တန်ဖိုးသတ်မှတ်ခြင်းသည် အရေးမကြီးပါ။ :ref:`single process dialog <algorithm_widgets>` ထဲကနှင့်အတူတူဖြစ်သော သင့်တော်သော widget ပါဝင်ပြီး တန်ဖိုးများကို စာရိုက်ထည့်သွင်းလို့ရပါသည်၊ သို့မဟုတ် parameter အမျိုးအစားပေါ်မူတည်ပြီး ဖြစ်နိုင်သောတန်ဖိုးများ စာရင်းမှ ရွေးချယ်နိုင်ပါသည်။ ကိုက်ညီမှုရှိသောအခါ data-define (Data ဖြင့်သတ်မှတ်ထားသော) widget လည်းပါဝင်ပါသည်။

Batch process သတ်မှတ်ခြင်းကို အလိုအလျှောက်လုပ်ဆောင်ရန်နှင့် ဇယားကို cell တစ်ခုချင်း ထည့်သွင်းခြင်းကို ရှောင်ရှားရန် parameter တစ်ခု၏ :guilabel:`Autofill...` menu ကို နှိပ်ရမည် ဖြစ်ပြီး column ထဲရှိတန်ဖိုးများကို အစားထိုးရန် အောက်ပါနည်းလမ်းများထဲမှ တစ်ခုခုကိုရွေးချယ်ရပါမည်-

* :guilabel:`Fill Down` သည် ပထမ process အတွက် ထည့်သွင်းအသုံးပြုသောတန်ဖိုးကို ရယူပြီး အခြား process များအတွက် ၎င်းတန်ဖိုးကိုထည့်သွင်းပါသည်။
* |calculateField| :guilabel:`Calculate by Expression...` သည် column တစ်ခုအတွင်း ရှိနေပြီးသား တန်ဖိုးများကို အသစ်ပြင်ဆင်ရန် QGIS expression တစ်ခုကိုရေးရန် လုပ်ဆောင်ပေးပါသည်။ ရှိနေပြီးသား parameter တန်ဖိုးများ (အခြား column မှတန်ဖိုးများလည်းပါဝင်သည်) ကို :ref:`variables <general_tools_variables>` မှတဆင့် expression ထဲတွင် ထည့်သွင်းအသုံးပြုနိုင်ပါသည်။ ဥပမာ- layer တစ်ခုချင်းစီ၏ buffer အကွာအဝေးပေါ်အခြေခံပြီး segment (အပိုင်း) များ၏အရေအတွက်ကို သတ်မှတ်ခြင်း-

  ::

     CASE WHEN @DISTANCE > 20 THEN 12 ELSE 8 END

* :guilabel:`Add Values by Expression...` သည် expression တစ်ခုမှ တန်ဖိုးများကိုအသုံးပြုပြီး row အသစ်များထည့်ပေါင်းပေးကာ array တစ်ခုကိုဖန်တီးပေးပါသည် (ရှိနေပြီးသား row များကိုသာအသုံးပြုသော :guilabel:`Calculate  by Expression...` နှင့်ဆန့်ကျင်ဘက်)။ ရည်ရွယ်ထားသော အသုံးပြုမှုမှာ ရှုပ်ထွေးသော ကိန်းဂဏန်းစဉ်များကို အသုံးပြုပြီး batch dialog ကိုလုပ်ဆောင်ရန်ဖြစ်ပါသည်။ ဥပမာ- row အသစ်များထဲတွင် 100၊ 150၊ 200၊ .... 1000 တန်ဖိုးများနှင့် အကွာအဝေး parameter ရလာဒ်များအတွက် ``generate_series(100, 1000, 50)`` expression ကိုအသုံးပြုပြီး batch buffer လုပ်ဆောင်ရန်အတွက် row အသစ်များထည့်ပေါင်းခြင်း။

* File တစ်ခု သို့မဟုတ် layer parameter တစ်ခုကို သတ်မှတ်သောအခါ ရွေးချယ်စရာများစွာ ရှိပါသည် -

  * :guilabel:`Add Files by Pattern...` - Folder တစ်ခုထဲတွင် :guilabel:`Look in (ကြည့်ရန်)` :guilabel:`File pattern` တစ်ခုနှင့်ကိုက်ညီသော file များအတွက် ဇယားတွင် row အသစ်များ ထည့်ပေးပါသည်။ ဥပမာ- folder ထဲရှိ :file:`SHP` file များအားလုံးကို စာရင်းထဲတွင် ``*.shp`` ကိုပေါင်းထည့်ပါလိမ့်မည်။ |checkbox| :guilabel:`Search recursively` ကိုအမှန်ခြစ်ခြင်းဖြင့် folder အခွဲများ အတွင်းပါ ရှာဖွေနိုင်ပါသည်။
  * :guilabel:`Directory တစ်ခုမှ file များအားလုံးကိုထည့်ခြင်း` 
  *  အသုံးပြုနေသော project ထဲရှိ :guilabel:`ဖွင့်ထားသော Layer များမှ ရွေးချယ်ခြင်း` 

Algorithm ကို single process အဖြစ်စေခိုင်းလုပ်ဆောင်သောအခါ ထွက်လာသော ရလာဒ်များ၏ parameter သည် တူညီသော လုပ်နိုင်စွမ်းများကို ဖော်ပြပေးပါသည်။ Algorithm ပေါ်မူတည်ပြီး ရလာဒ်များသည် အောက်ပါအတိုင်း ဖြစ်နိုင်ပါသည် -

* Cell က ဘာမှမရှိလျှင် ကျော်လိုက်ခြင်း။
* ယာယီ file အဖြစ်သိမ်းခြင်း - cell ကို ``TEMPORARY_OUTPUT (ယာယီရလာဒ်)`` ဖြင့်ဖြည့်စွက်မည်ဖြစ်ပြီး |checkbox| :guilabel:`Load layers on completion` checkbox ကို အမှန်ခြစ် ခြစ်ထားရန် မမေ့ပါနှင့်။
* တစ်ခုခုမလုပ်ဆောင်ခင်တွင် :guilabel:`Autofill` နည်းလမ်းများဖြင့် file လမ်းကြောင်းကိုသတ်မှတ်ပေးသော plain file (:file:`.SHP` ၊ :file:`.GPKG` ၊ :file:`.XML` ၊ :file:`.PDF` ၊ :file:`.JPG` ၊...) တစ်ခုအဖြစ် သိမ်းဆည်းခြင်း။ ဥပမာ- ရှုပ်ထွေးသော expression များကို ထွက်လာမည့် file အမည်များကို သတ်မှတ်ပေးရန် :guilabel:`Calculate by Expression...` ကို အသုံးပြုခြင်း-

  ::

     '/home/me/stuff/buffer_' || left(@INPUT, 30) || '_' || @DISTANCE || '.shp'

  File လမ်းကြောင်းကို လက်ဖြင့်တိုက်ရိုက်စာရိုက်ထည့်နိုင်သလို :guilabel:`...` ခလုတ်ကို နှိပ်လျှင်ပေါ်လာသော file ရွေးချယ်သော dialog ကိုလည်း အသုံးပြုနိုင်ပါသည်။ File ကိုရွေးပြီးသည်နှင့် column တစ်ခုတည်းရှိ (parameter တစ်ခုတည်း) အခြား cell များကို အလိုအလျှောက်ပြီးဆုံးအောင်လုပ်ခြင်းအတွက် dialog တစ်ခုပေါ်လာပါသည်။

  .. _figure_processing_save:

  .. figure:: img/batch_processing_save.png
     :align: center

     Batch Processing ကို သိမ်းဆည်းခြင်း

  မူရင်းတန်ဖိုး (:guilabel:`Do not autofill`) ကိုရွေးချယ်ထားလျှင် parameter ဇယားမှ ရွေးချယ်ထားသော cell ထဲရှိ ရွေးချယ်ထားသော file အမည် ကိုထည့်ပေးပါလိမ့်မည်။ အခြားရွေးချယ်စရာများထဲမှတစ်ခုခုကို ရွေးချယ်ထားလျှင် ရွေးချယ်ထားသောတစ်ခု၏ **အောက်တွင်** ရှိနေသော cell အားလုံးကို သတ်မှတ်ထားသော စံနှုန်းပေါ်မူတည်ပြီး အလိုအလျောက်ဖြည့်စွက်ပေးပါသည်-

  * :guilabel:`Fill with numbers` - file အမည်နောက်တွင် ဂဏန်းတစ်ခုကို တစ်ခုချင်းတိုးပြီး ပေါင်းထည့်ပေးပါသည်။
  * :guilabel:`Fill with parameter values` - file အမည်တွင်ပေါင်းထည့်ပေးမည့် တူညီသော row ထဲရှိ parameter တန်ဖိုးကို ရွေးချယ်နိုင်ပါသည်။ ထည့်သွင်းအသုံးပြုသော အချက်အလက်များပေါ်မူတည်ပြီး ရလာသော ရလာဒ်များကို နာမည်ပေးချင်သောအခါ ဒီနည်းလမ်းသည် အသုံးဝင်ပါသည်။

* Database container ထဲတွင် layer တစ်ခုအနေဖြင့် သိမ်းဆည်းခြင်း -

  ::

    # Indicate a layer within a GeoPackage file 
    ogr:dbname='C:/Path/To/Geopackage.gpkg' table="New_Table" (geom)

    # Use the "Calculate By Expression" to output to different layers in a GeoPackage
    'ogr:dbname=\'' || @project_folder || '/Buffers.gpkg\' table="' || @INPUT || '_' || @DISTANCE || '" (geom)'


Executing the batch process (Batch process ကို စေခိုင်းလုပ်ဆောင်ခြင်း)
-----------------------------------------------------------------------

မဖြစ်မနေလိုအပ်သော တန်ဖိုးများထည့်သွင်းပြီးနောက် batch process ကိုစေခိုင်းလုပ်ဆောင်ရန် :guilabel:`Run` ခလုတ်ကိုနှိပ်ပါ။ :guilabel:`Log` panel ပွင့်လာပြီး လုပ်ဆောင်နေသော အဆင့်များကို အသေးစိတ်ဖော်ပြပေးပါလိမ့်မည်။ Batch process ၏ ပြီးစီးနေသောပမာဏကို dialog ၏အောက်ခြေရှိ progress bar တွင် ပြသနေပါမည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |calculateField| image:: /static/common/mActionCalculateField.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |fileOpen| image:: /static/common/mActionFileOpen.png
   :width: 1.5em
.. |fileSave| image:: /static/common/mActionFileSave.png
   :width: 1.5em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
.. |symbologyRemove| image:: /static/common/symbologyRemove.png
   :width: 1.5em
