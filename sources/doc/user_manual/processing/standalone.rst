.. _processing_standalone:

Using processing from the command line (Command line မှ processing ကိုအသုံးပြုခြင်း)
=====================================================================================

.. only:: html

   .. contents::
      :local:

QGIS Desktop ကိုဖွင့်ရန်မလိုအပ်ပဲ command line မှတဆင့် processing algorithm များနှင့် model များ (မူရင်းပါသော သို့မဟုတ် plugins ဖြင့်ထည့်သွင်းထားသော) ကိုတိုက်ရိုက်လုပ်ဆောင်နိုင်သော ``QGIS Processing Executor`` ဟုခေါ်သည့် tool တစ်ခု QGIS တွင်ပါဝင်ပါသည်။

Command line tool မှ ``qgis_process`` ကို run ပြီးလျှင် အောက်ပါအတိုင်း ရရှိသင့်ပါသည် - 

.. code-block:: bash

  QGIS Processing Executor - 3.27.0-Master 'Master' (3.27.0-Master)
  Usage: C:\OSGeo4W\apps\qgis-dev\bin\qgis_process.exe [--help] [--version] [--json] [--verbose] [--no-python] [command] [algorithm id, path to model file, or path to Python script] [parameters]

  Options (ရွေးချယ်စရာနည်းလမ်းများ):

    --help or -h      Output the help (အကူအညီကို ထုတ်ပေးပါသည်)
    --version or -v   Output all versions related to QGIS Process (QGIS Process နှင့်ဆက်စပ်သော version များအားလုံးကို ထုတ်ပေးပါသည်)
    --json            Output results as JSON objects (ရလာဒ်များကို JSON object များအဖြစ် ထုတ်ပေးပါသည်)
    --verbose         Output verbose logs (ရှည်လျားသော log များကို ထုတ်ပေးပါသည်)
    --no-python       Disable Python support (results in faster startup) (Python အကူအညီကို ပိတ်ပေးပါသည် (စပွင့်သောအခါ ပိုမြန်စေပါသည်))

  Available commands (အသုံးပြုနိုင်သော command များ):

    plugins          အသုံးပြုနိုင်သော plugin များကို စာရင်းပြုစုပေးပါသည်
    plugins enable   ထည့်သွင်းထားသော plugin တစ်ခုကိုအသုံးပြုနိုင်စေရန်ဖွင့်ပေးပါသည်။ Plugin ၏နာမည်ကို တိတိကျကျပေးထားရပါမည်၊ ဥပမာ- "plugins enable cartography_tools"
    plugins disable  ထည့်သွင်းထားသော plugin ကို အသုံးပြုလို့မရအောင် ပိတ်ထားပေးပါသည်။ Plugin ၏နာမည်ကို တိတိကျကျပေးထားရပါမည်၊ ဥပမာ "plugins disable cartography_tools"
    list             အသုံးပြုနိုင်သော processing algorithm များအားလုံးကို စာရင်းပြုစုပေးပါသည်
    help             Algorithm တစ်ခုအတွက် အကူအညီကို ပြသပေးပါသည်။ Algorithm ID သို့မဟုတ် Model file တစ်ခုဆီသို့ လမ်းကြောင်းကို တိတိကျကျ ဖော်ပြထားရပါမည်
    run              Algorithm ကို စေခိုင်းလုပ်ဆောင်ပါသည်။ Algorithm ID သို့မဟုတ် Model File တစ်ခုဆီသို့ လမ်းကြောင်း နှင့် parameter တန်ဖိုးများကို တိတိကျကျ ဖော်ပြထားရပါမည်
                     Parameter တန်ဖိုးများကို -- ၏နောက်တွင် PARAMETER=VALUE syntax ဖြင့် သတ်မှတ်ပေးပါ။ 
                     Parameter အကြိမ်များစွာကို သတ်မှတ်ပေးခြင်းဖြင့် Parameter တစ်ခုအတွက် စီစဉ်ထားသော စာရင်းတန်ဖိုးများကို ဖန်တီးနိုင်ပါသည် (ဥပမာ - --LAYERS=layer1.shp --LAYERS=layer2.shp)
                     တခြားနည်းအားဖြင့် Parameters agrunment ၏နေရာထဲရှိ '-' character သည် parameter များကို JSON object တစ်ခုအဖြစ် STDIN မှ ဖတ်သင့်သည်ဟု ညွှန်းဆိုပါသည်။
                     ထည့်သွင်းအသုံးပြုသော parameter တန်ဖိုးများ၏ မြေပုံကိုသတ်မှတ်ပေးသော အနည်းဆုံး "ထည့်သွင်းအသုံးပြုသည့်အချက်အလက်များ" key တစ်ခုပါဝင်သော မြေပုံတစ်ခုအဖြစ် JSON ကိုတည်ဆောက်သင့်ပါသည်။ 
                     ၎င်းသည် ရလာဒ်အတွက် JSON object တစ်ခုအဖြစ် --json ကို သွယ်ဝိုက်ညွှန်းဆိုပါသည်။ 
                     လိုအပ်လျှင် အကွာအဝေးနှင့် ဧရိယာတွက်ချက်ခြင်းများအတွက် ellipsoid ကို "--ELLIPSOID=name" argument မှတဆင့် သတ်မှတ်ပေးနိုင်ပါသည်။ 
                     လိုအပ်လျှင် algorithm စေခိုင်းလုပ်ဆောင်စဉ်တွင် အသုံးပြုမည့် ရှိနေပြီးသား QGIS project ကို "--PROJECT_PATH=path" argument မှတဆင့် သတ်မှတ်ပေးနိုင်ပါသည်။


.. note::
  :file:`metadata.txt` file ထဲတွင် ``hasProcessingProvider=yes`` ကိုဖော်ပြသော ထည့်သွင်းထားသည့် plugin များကိုသာ အသိအမှတ်ပြုပြီး အသုံးပြုနိုင်အောင်ဖွင့်နိုင်သည် သို့မဟုတ် qgis_process tool မှထည့်သွင်းအသုံးပြုနိုင်ပါသည်။

အသုံးပြုနိုင်သော provider များနှင့် algorithm များအားလုံး၏စာရင်းကို ရရန် ``list`` command ကိုအသုံးပြုနိုင်ပါသည်။

.. code-block:: bash

   qgis_process list

Command များနှင့် algorithm များအကြောင်းကို ပိုမိုသိရှိနိုင်ရန် ``help`` command ကိုအသုံးပြုနိုင်ပါသည်။

.. code-block:: bash

   qgis_process help qgis:regularpoints

Algorithm သို့မဟုတ် model ကိုစေခိုင်းလုပ်ဆောင်ရန် ``run`` command ကိုအသုံးပြုနိုင်ပါသည်။ Algorithm ၏နာမည် သို့မဟုတ် model တစ်ခုဆီသို့ လမ်းကြောင်းကို ပထမဆုံး parameter အဖြစ် သတ်မှတ်ပေးပါ။

.. code-block:: bash

   qgis_process run native:buffer -- INPUT=source.shp DISTANCE=2 OUTPUT=buffered.shp

တန်ဖိုးများ၏ စာရင်းကို parameter ကလက်ခံသောအခါ တူညီသော variable ကိုအကြိမ်များစွာ သတ်မှတ်ပါ။

.. code-block:: bash

   qgis_process run native:mergevectorlayers -- LAYERS=input1.shp LAYERS=input2.shp OUTPUT=merged.shp

Algorithm ကိုစေခိုင်းလုပ်ဆောင်နေစဉ်တွင် စာသားဖြင့်ဖော်ပြသော အကြောင်းပြန်သည့် bar တစ်ခုပေါ်လာပြီး လုပ်ဆောင်နေမှုကို :kbd:`CTRL+C` မှတဆင့် ရပ်တန့်နိုင်ပါသည်။

``run`` command သည် အခြား parameter များကိုလည်း လုပ်ဆောင်ပေးပါသည်။

- ``--json`` သည် JSON ဖွဲ့စည်းထားသော နည်းလမ်းတစ်ခုဖြင့် stdout ရလာဒ်ကို format ပြုလုပ်ပေးပါလိမ့်မည်။
- ``--ellipsoid`` သည် သတ်မှတ်ပေးထားသော တစ်ခုဆီသို့ ellipsoid ကို ချမှတ်ပေးပါလိမ့်မည်။
- ``--distance_units`` သည် သတ်မှတ်ထားသောအကွာအဝေးယူနစ်များကို အသုံးပြုပါလိမ့်မည်။
- ``--area_units`` သည် သတ်မှတ်ထားသောဧရိယာယူနစ်များကို အသုံးပြုပါလိမ့်မည်။
- ``--project_path`` သည် algorithm ကိုလုပ်ဆောင်ရန်အတွက် သတ်မှတ်ထားသော project ကို ခေါ်ယူထည့်သွင်းပေးပါလိမ့်မည်။

ရှုပ်ထွေးသော ထည့်သွင်းအသုံးပြုသည့် parameter များ (algorithm များအတွက် dictionary အမျိုးအစား object တစ်ခုအဖြစ် ၎င်းတို့ကိုယ်တိုင် သတ်မှတ်ထားသော parameter အမျိုးအစားများကို ဆိုလိုပါသည်) ကို qgis_process မှလုပ်ဆောင်ပေးပါသည်။ stdin မှတဆင့် သတ်မှတ်မည့် parameter များကို ညွှန်ပြရန်အတွက် qgis_process command သည် format အတိုင်းလုပ်ဆောင်မည်ဖြစ်သည် (လုပ်ရိုးလုပ်စဉ် arguments စာရင်း၏ နေရာထဲရှိ ``-`` လမ်းကြောင်းတစ်ခုနှင့်)

.. code-block:: bash

   qgis_process run algorithmId -


JSON object တွင် ထည့်သွင်းအသုံးပြုသော parameter တန်ဖိုးများ၏ မြေပုံတစ်ခုဖြစ်သော "inputs" key တစ်ခု ပါဝင်ရပါမည်။ ဥပမာ-

.. code-block:: bash

   echo "{'inputs': {'INPUT': 'my_shape.shp', 'DISTANCE': 5}}" | qgis_process run native:buffer -

ထို့အပြင် အကွာအဝေးယူနစ်၊ ဧရိယာယူနစ်၊ ellipsoid နှင့် project လမ်းကြောင်းတို့လိုမျိုး အခြား setting များသည် ဤ JSON object ထဲတွင် ပါဝင်နိုင်ပါသည်-

.. code-block:: bash

   {
    'ellipsoid': 'EPSG:7019',
    'distance_units': 'feet',
    'area_units': 'ha',
    'project_path': 'C:/temp/my_project.qgs'
    'inputs': {'DISTANCE': 5, 'SEGMENTS': 8 ... }
   }

stdin မှတဆင့် ထည့်သွင်းအသုံးပြုသည့် parameter များကို သတ်မှတ်ခြင်းသည် ရလာဒ်များအတွက် :file:`JSON` ရလာဒ် format ကို အလိုအလျှောက်ညွှန်းဆိုပေးပါသည်။

