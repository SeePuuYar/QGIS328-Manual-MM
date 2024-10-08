.. _processing_console:

Using processing algorithms from the console (Console မှ processing algorithm များကို အသုံးပြုခြင်း)
=====================================================================================================

.. only:: html

   .. contents::
      :local:

Console တွင် processing framework ၏ အခြား GUI element များကိုအသုံးပြုပြီး မလုပ်ဆောင်နိုင်သော ရှုပ်ထွေးသည့်လုပ်ငန်းဆောင်တာများကို ကျွမ်းကျင်အသုံးပြုသူများမှ အဆင့်မြင့်လုပ်ဆောင်နိုင်ပြီး လုပ်ငန်းကိုပိုမိုထိရောက်စေပါသည်။ Algorithm များစွာပါသော model များကို command-line interface ကိုအသုံးပြုပြီးသတ်မှတ်နိုင်ပြီး ထပ်ခါထပ်ခါလုပ်ဆောင်သော loop များနှင့် အခြေအနေအရလုပ်ဆောင်သော စာတန်းများ (Conditional sentences) ကဲ့သို့ အခြားလုပ်ငန်းများကို ထပ်ဖြည့်ပြီး ပိုမိုလိုက်လျောညီထွေဖြစ်ပြီး လုပ်ဆောင်နိုင်စွမ်းများသော workflow (လုပ်ငန်းအဆင့်များ) များကို ဖန်တီးပေးပါသည်။

QGIS တွင် processing console ပါဝင်ခြင်းမရှိပါ။ သို့သော် QGIS ၏မူရင်းပါသော :ref:`Python console <console>` မှ processing command များအားလုံးကိုအသုံးပြုနိုင်ပါသည်။ ဆိုလိုသည်မှာ ၎င်း command များကို မိမိ၏ console လုပ်ငန်းများနှင့် ပူးတွဲလုပ်ဆောင်နိုင်ပြီး processing algorithm များကို ရနိုင်သော အခြား feature များ (QGIS API မှ နည်းလမ်းများအပါအဝင်) နှင့် ချိတ်ဆက်နိုင်ပါသည်။

သီးခြား processing method တစ်ခုခုကို ခေါ်ယူအသုံးမပြုလျှင်တောင်မှ python console မှ စေခိုင်းလုပ်ဆောင်နိုင်သော code ကို အခြား algorithm ဖြင့်လုပ်ဆောင်သကဲ့သို့ နောက်ပိုင်းတွင် toolbox၊ graphical modeler သို့မဟုတ် အခြား component များမှ ခေါ်ယူအသုံးပြုနိုင်သော algorithm တစ်ခုအဖြစ် ပြောင်းလဲနိုင်ပါသည်။ တကယ်တော့ toolbox ထဲတွင်တွေ့ရသော အချို့သော algorithm များသည် လွယ်ကူရိုးရှင်းသော script များဖြစ်ပါသည်။

ဤ section တွင် QGIS Python console မှ processing algorithm များကို မည်သို့အသုံးပြုရမည် နှင့် Python ကိုအသုံးပြုပြီး algorithm များမည်သို့ရေးရမည် ဆိုသည်ကို တွေ့ရမည်ဖြစ်ပါသည်။

Calling algorithms from the Python console (Python console မှ algorithm များကို ခေါ်ယူအသုံးပြုခြင်း)
-----------------------------------------------------------------------------------------------------

ပထမဆုံးလုပ်ဆောင်ရမည့် အဆင့်မှာ အောက်ပါ စာကြောင်းဖြင့် processing function များကိုထည့်သွင်းရန်ဖြစ်သည်-

::

    >>> from qgis import processing

ယခုလက်ရှိတွင် Console မှ လုပ်ဆောင်နိုင်သော (စိတ်ဝင်စားစရာကောင်းသော) အရာတစ်မျိုးသာရှိပါသည် - algorithm ကို စေခိုင်းလုပ်ဆောင်ခြင်း (execute) ဖြစ်ပါသည်။ Algorithm ၏အမည်ကို ၎င်း၏ပထမဆုံး parameter အဖြစ် စေခိုင်းလုပ်ဆောင်သည့် :meth:`run() <qgis.core.QgsProcessingAlgorithm.run>` နည်းလမ်းကိုအသုံးပြုပြီး လုပ်ဆောင်ပါသည်။ ထို့နောက် algorithm ၏ လိုအပ်ချက်များပေါ် မူတည်ပြီး အခြား parameter များ၏ variable အရေအတွက်ကိုလုပ်ဆောင်ပါသည်။ ထို့ကြောင့် စေခိုင်းလုပ်ဆောင်ရန်အတွက် ပထမဆုံးသိရမည့်အချက်မှာ algorithm ၏ အမည်ဖြစ်ပါသည်။ Toolbox ထဲတွင်တွေ့ရသော အမည်မဟုတ်ပါ၊ တမူထူးခြားသော command-line အမည်ဖြစ်ပါသည်။ Algorithm ၏အမည်အမှန်ကိုရှာရန် :class:`processingRegistry <qgis.core.QgsProcessingRegistry>` ကိုအသုံးပြုနိုင်ပါသည်။ Console ထဲတွင် အောက်ပါစာကြောင်းကိုရိုက်ထည့်ပါ-

::

    >>> for alg in QgsApplication.processingRegistry().algorithms():
            print(alg.id(), "->", alg.displayName())

အောက်တွင်ဖော်ပြထားသည့်အတိုင်း တွေ့ရမည်ဖြစ်ပါသည် (ဖတ်ရလွယ်ကူစေရန် dash များပိုထည့်ပြီး ညှိပေးထားပါသည်)။

::

   3d:tessellate --------------> Tessellate
   gdal:aspect ----------------> Aspect
   gdal:assignprojection ------> Assign projection
   gdal:buffervectors ---------> Buffer vectors
   gdal:buildvirtualraster ----> Build Virtual Raster
   gdal:cliprasterbyextent ----> Clip raster by extent
   gdal:cliprasterbymasklayer -> Clip raster by mask layer
   gdal:clipvectorbyextent ----> Clip vector by extent
   gdal:clipvectorbypolygon ---> Clip vector by mask layer
   gdal:colorrelief -----------> Color relief
   gdal:contour ---------------> Contour
   gdal:convertformat ---------> Convert format
   gdal:dissolve --------------> Dissolve
   ...

၎င်းတို့၏သက်ဆိုင်ရာအမည်များအလိုက် provider အမည်နှင့် algorithm အမည်များဖြင့် စီစဉ်ထားသော အသုံးပြုနိုင်သော algorithm ID များအားလုံး၏ စာရင်းဖြစ်ပါသည်။

Algorithm ၏ command-line အမည်ကို သိသည်နှင့် နောက်ထပ်လုပ်ဆောင်ရမည့်အဆင့်မှာ စေခိုင်းလုပ်ဆောင်ရန်အတွက် မှန်ကန်သော syntax (ဝါကျဖွဲ့ပုံ) ကိုဆုံးဖြတ်ရန်ဖြစ်ပါသည်။ ``run()`` နည်းလမ်းကိုအသုံးပြုသောအခါ မည်သည့် parameter များလိုအပ်သည်ကို သိခြင်းကို ဆိုလိုပါသည်။

Algorithm တစ်ခုမှ လိုအပ်သော parameter များစာရင်းကိုရရန်နှင့် ထွက်လာမည့် ရလာဒ်များရရှိရန် အသုံးပြုနိုင်သော algorithm တစ်ခုကိုအသေးစိတ်ဖော်ပြသည့် နည်းလမ်းတစ်ခုရှိပါသည်။ ၎င်းသတင်းအချက်အလက်ကို ရယူရန် ``algorithmHelp(id_of_the_algorithm)`` နည်းလမ်းကိုအသုံးပြုနိုင်ပါသည်။ Algorithm ၏ ID ကိုအသုံးပြုပါ၊ ဖော်ပြနာမည်အပြည့်အစုံကို သုံးရန်မလိုအပ်ပါ။ 

နည်းလမ်းကို parameter (``qgis:buffer`` သည် ``native:buffer`` အတွက် နာမည်ပွားဖြစ်ပြီး အလုပ်လည်း လုပ်ဆောင်ပေးပါသည်) အဖြစ် ``native:buffer`` နှင့်ခေါ်ယူအသုံးပြုခြင်းဖြင့် အောက်ပါ ဖော်ပြချက်ကို ရရှိမည်ဖြစ်ပါသည်-

::

     >>> processing.algorithmHelp("native:buffer")
     Buffer (native:buffer)
     
	   ဤ algorithm သည် ပုံသေ သို့မဟုတ် ပြောင်းလဲနေသော အကွာအဝေးကို အသုံးပြုပြီး input layer တစ်ခုအတွင်းရှိ feature များအားလုံးအတွက် buffer area ကိုတွက်ထုတ်ပေးပါသည်။
     
	   Segments (မျဉ်းပိုင်းများ) parameter သည် ထောင့်ကွေးများတွင် offset (အရွေ့) များဖန်တီးသောအခါ စက်ဝိုင်း၏လေးပုံတစ်ပုံခန့်ကိုဖန်တီးရန် အသုံးပြုသော line segment အရေအတွက်ကို ထိန်းချုပ်ပေးပါသည်။
     
	   အဆုံးသတ် အဝိုက် (cap) style parameter သည် buffer ထဲတွင် မျဉ်းအဆုံးသတ်များကို မည်သို့ ကိုင်တွယ်မည်ဆိုသည်ကို ထိန်းချုပ်ပေးပါသည်။
     
 	   Line တစ်ခုတွင် ထောင့်များကို offset လုပ်သောအခါ round (စောင်းလုံး)၊ miter (စောင်းတိ) သို့မဟုတ် bevel (စောင်းသတ်) အဆက်များ အသုံးပြုသင့်သည်ကို joint style parameter ကဆုံးဖြတ်ပေးပါသည်။
	 
	   Miter ကန့်သတ်ချက် parameter သည် miter (စောင်းတိ) ဆက်သော style များအတွက်သာအသုံးပြုနိုင်ပြီး miter (စောင်းတိ) join တစ်ခုဖန်တီးသောအခါ အသုံးပြုရန် offset အကွေးမှ အဝေးဆုံးအကွာအဝေးကို ထိန်းချုပ်ပေးပါသည်။     
     

     ----------------------------------------------------------------
     Input parameters (ထည့်သွင်းအသုံးပြုသော parameter များ)
     ----------------------------------------------------------------
     
     INPUT: Input layer (ထည့်သွင်းအသုံးပြုသော layer)
     
     	Parameter type:	QgsProcessingParameterFeatureSource
     
     	Accepted data types:
     		- str: layer ID
     		- str: layer name
     		- str: layer source
     		- QgsProcessingFeatureSourceDefinition
     		- QgsProperty
     		- QgsVectorLayer
     
     DISTANCE: Distance (အကွာအဝေး)
     
     	Parameter type:	QgsProcessingParameterDistance
     
     	Accepted data types:
     		- int
     		- float
     		- QgsProperty
     
     SEGMENTS: Segments (မျဉ်းပိုင်းများ)
     
     	Parameter type:	QgsProcessingParameterNumber
     
     	Accepted data types:
     		- int
     		- float
     		- QgsProperty
     
     END_CAP_STYLE: End cap style (အဆုံးသတ် အဝိုက် style)
     
     	Parameter type:	QgsProcessingParameterEnum
     
     	Available values:
     		- 0: Round
     		- 1: Flat
     		- 2: Square
     
     	Accepted data types:
     		- int
     		- str: as string representation of int, e.g. '1'
     		- QgsProperty
     
     JOIN_STYLE: Join style (မျဉ်း နှစ်ခုဆက်သော style)

	Parameter type:	QgsProcessingParameterEnum

	Available values:
		- 0: Round
		- 1: Miter
		- 2: Bevel

	Accepted data types:
		- int
		- str: as string representation of int, e.g. '1'
		- QgsProperty
     
     MITER_LIMIT: Miter limit (Miter ကန့်သတ်ချက်)
     
     	Parameter type:	QgsProcessingParameterNumber
     
     	Accepted data types:
     		- int
     		- float
     		- QgsProperty
     
     DISSOLVE: Dissolve result (ပျော်ဝင်ပေါင်းစည်းသွားသော/ရောနှောသွားသော ရလာဒ်)
     
     	Parameter type:	QgsProcessingParameterBoolean
     
     	Accepted data types:
		- bool
		- int
		- str
		- QgsProperty
          
     OUTPUT: Buffered
     
     	Parameter type:	QgsProcessingParameterFeatureSink
     
     	Accepted data types:
     		- str: destination vector file, e.g. 'd:/test.shp'
     		- str: 'memory:' to store result in temporary memory layer
     		- str: using vector provider ID prefix and destination URI,
                       e.g. 'postgres:...' to store result in PostGIS table
     		- QgsProcessingOutputLayerDefinition
     		- QgsProperty
     
     ------------------------------------------------
     Outputs (ရလာဒ်များ)
     ------------------------------------------------
     
     OUTPUT:  <QgsProcessingOutputVectorLayer>
     	Buffered
     
     
Now you have everything you need to run any algorithm. As we have
already mentioned, algorithms can be run using: ``run()``.
Its syntax is as follows:

ယခုဆိုလျှင် မည်သည့် algorithm ကိုမဆို လုပ်ဆောင်ရန်အတွက် လိုအပ်သောအရာများ အားလုံးရှိနေပြီဖြစ်ပါသည်။ အထက်တွင်ဖော်ပြခဲ့သည့်အတိုင်း ``run()`` ကို အသုံးပြုပြီး algorithm များကို စေခိုင်းလုပ်ဆောင်နိုင်ပါသည်။ ၎င်း၏ syntax မှာအောက်ပါအတိုင်းဖြစ်ပါသည်-

::

    >>> processing.run(name_of_the_algorithm, parameters)

Parameter များသည် ကိုယ်လုပ်ဆောင်လိုသော algorithm ပေါ်မူတည်သော parameter များ၏ dictionary တစ်ခုဖြစ်ပြီး ``algorithmHelp()`` နည်းလမ်းမှ ပေးသော စာရင်းအတိအကျအတိုင်း ဖြစ်ပါသည်။။

.. code-block:: python
   :linenos:

    >>> processing.run("native:buffer", {'INPUT': '/data/lines.shp',
                  'DISTANCE': 100.0,
                  'SEGMENTS': 10,
                  'DISSOLVE': True,
                  'END_CAP_STYLE': 0,
                  'JOIN_STYLE': 0,
                  'MITER_LIMIT': 10,
                  'OUTPUT': '/data/buffers.shp'})


Parameter သည် optional (အသုံးမပြုလည်းရ) ဖြစ်ပြီး မိမိကလည်းအသုံးမပြုလိုလျှင် ၎င်းကို dictionary တွင် မထည့်ပါနှင့်။

Parameter တန်ဖိုးကို သတ်မှတ်မပေးထားလျှင် software မှပေးသော မူရင်းတန်ဖိုးကိုအသုံးပြုမည် ဖြစ်ပါသည်။

Parameter အမျိုးအစားပေါ်မူတည်ပြီး တန်ဖိုးများကို ကွဲပြားစွာထည့်ပေးပါသည်။ နောက်ဖော်ပြပေးမည့်စာရင်းသည် ထည့်သွင်းအသုံးပြုမည့် parameter တစ်ခုချင်းစီအတွက် တန်ဖိုးများကို မည်သို့ထည့်သွင်းရမည်ဆိုသော နည်းလမ်းကို သုံးသပ်ဖော်ပြပေးပါမည်-

* Raster Layer ၊ Vector Layer သို့မဟုတ် Table ။ အသုံးပြုမည့် data object (QGIS Table of Contents ထဲတွင်ရှိနေသော ၎င်း၏အမည်) သို့မဟုတ် file အမည်တစ်ခု (သက်ဆိုင်ရာ layer ကို ဖွင့်မထားလျှင် ၎င်းကိုဖွင့်မည်ဖြစ်ပြီး မြေပုံမြင်ကွင်းထဲသို့ ထည့်သွင်းမည်မဟုတ်ပါ) ကိုခွဲခြားပေးသော အမည်စာသားတစ်ခုကို ရိုးရှင်းစွာအသုံးပြုပါ။ Layer ကိုကိုယ်စားပြုသော QGIS object တစ်ခု ဥပမာ ရှိလျှင် ၎င်းကို parameter အဖြစ် အသုံးပြုနိုင်ပါသည်။
* တစ်ခုချင်းစီသီးခြားဖော်ပြခြင်း (Enumeration) ။ Algorithm တစ်ခုတွင် enumeration parameter တစ်ခုရှိလျှင် ကိန်းပြည့်ဂဏန်းတစ်ခုကို အသုံးပြုပြီး ၎င်း parameter ၏တန်ဖိုးကို ထည့်သွင်းသင့်ပါသည်။ အသုံးပြုနိုင်သော နည်းလမ်းများကို သိလိုလျှင် အထက်မှာဖော်ပြခဲ့သည့်အတိုင်း ``algorithmHelp()`` command ကိုအသုံးပြုနိုင်ပါသည်။ ဥပမာ- ``native:buffer`` algorithm တွင် JOIN_STYLE ဟုခေါ်သော enumeration တစ်ခုရှိပါသည်-

  ::

     JOIN_STYLE: Join style (မျဉ်း နှစ်ခုဆက်သော style)

	Parameter type:	QgsProcessingParameterEnum

	Available values:
		- 0: Round
		- 1: Miter
		- 2: Bevel

	Accepted data types:
		- int
		- str: as string representation of int, e.g. '1'
		- QgsProperty
     
  ယခုဥပမာတွင် parameter တွင်ရွေးချယ်စရာ သုံးမျိုးရှိပါသည်။ အစီအစဉ်မှာ သုညမှ စတင်ထားသည်ကို သတိပြုပါ။
  
* Boolean။ ``အမှန်`` သို့မဟုတ် ``အမှား`` ကိုအသုံးပြုပါ။
* ထည့်သွင်းအသုံးပြုသောအရာ များစွာရှိခြင်း။ တန်ဖိုးသည် semicolons (``;``) ဖြင့်ပိုင်းခြားထားသော စာသားဖြင့် ရေးသားဖော်ပြထားခြင်း ဖြစ်ပါသည်။ Layer တစ်ခုတည်း သို့မဟုတ် ဇယားများပါသော အခါတွင် ထည့်သွင်းအသုံးပြုသော ရေးသားဖော်ပြချက်သည် data object အမည် သို့မဟုတ် ၎င်း၏ file လမ်းကြောင်း ဖြစ်နိုင်ပါသည်။
* XXX မှ ဇယား၏ field။ အသုံးပြုမည့် field ၏အမည်ဖြင့် စာသားတစ်ခုကို အသုံးပြုပါ။ ၎င်း parameter သည် စာလုံးအကြီးအသေး (case-sensitive) ဂရုပြုရမည်ဖြစ်သည်။
* ပုံသေသတ်မှတ်ထားသော ဇယား။ Commas (``,``) နှင့်ခြားထားပြီး quotes (``"``) ထဲတွင်ထည့်ရေးထားသော ဇယားမှတန်ဖိုးများအားလုံး၏ စာရင်းကို စာရိုက်ထည့်ပါ။ အပေါ်ပိုင်း row မှ တန်ဖိုးများစတင်ပြီး ဘယ်မှညာဘက်ကို ရွေ့သွားပါသည်။ ဇယားကိုကိုယ်စားပြုသော တန်ဖိုးများ၏ နှစ်ဖက်မြင်ကိန်းတန်း (2-D array) ကိုလည်း အသုံးပြုနိုင်ပါသည်။
* CRS။ အသုံးပြုလိုသော CRS ၏ EPSG code နံပါတ်ကို ထည့်သွင်းပါ။
* စတုဂံပုံအကျယ်အဝန်းနယ် (Extent)။ Commas (``,``) ဖြင့်ခြားထားသော ``အနည်းဆုံး x တန်ဖိုး`` ၊ ``အများဆုံး x တန်ဖိုး`` ၊ ``အနည်းဆုံး y တန်ဖိုး`` နှင့် ``အများဆုံး y တန်ဖိုး`` များဖြင့် စာသားတစ်ခုကို အသုံးပြုရပါမည်။

Boolean ၊ file ၊ စာသား နှင့် ကိန်းဂဏန်း parameter များသည် ထပ်ဆောင်းဖြည့်စွက်ရှင်းလင်းချက်များ မလိုအပ်ပါ။

စာသား၊ boolean သို့မဟုတ် ကိန်းဂဏန်းတန်ဖိုးများကဲ့သို့ input parameter များတွင် မူရင်း (default) တန်ဖိုးများ ရှိပါသည်။ ထည့်ပေးရမည့် သက်ဆိုင်ရာ parameter များထည့်မထားလျှင် ၎င်းမူရင်းတန်ဖိုးကို ထည့်သွင်းအသုံးပြုပါသည်။

ရလာဒ် object များအတွက် toolbox တွင်လုပ်ဆောင်သလိုမျိုး သိမ်းဆည်းရမည့် file လမ်းကြောင်းကိုထည့်သွင်းရေးသားပါ။ ရလာဒ် object ကိုသတ်မှတ်မပေးလျှင် ရလာဒ်ကို ယာယီ file တွင်သိမ်းဆည်းမည်ဖြစ်ပါသည် (မဖြစ်မနေသိမ်းပေးရမည့် ရလာဒ်မျိုးမဟုတ်လျှင် သိမ်းဆည်းမပေးတော့ပါ)။ File ၏ extension သည် file format ကိုဆုံးဖြတ်ပေးပါသည်။ Algorithm ကလုပ်ဆောင်မပေးနိုင်သော file extension ကိုထည့်သွင်းအသုံးပြုလျှင် ၎င်းရလာဒ်အမျိုးအစားအတွက် မူရင်း (default) format ကိုအသုံးပြုပါလိမ့်မည်။ ထို့နောက် ၎င်းနှင့်သက်ဆိုင်သော extension ကို ထည့်သွင်းပေးထားသော file လမ်းကြောင်းတွင် ထည့်ပေါင်းပေးပါသည်။

Toolbox မှ algorithm တစ်ခုကိုစေခိုင်းလုပ်ဆောင်ခြင်းနှင့်မတူဘဲ :meth:`run() <qgis.core.QgsProcessingAlgorithm.run>` ကိုအသုံးပြုပြီး Python console မှ တူညီသော algorithm ကို စေခိုင်းလုပ်ဆောင်လျှင် ရလာဒ်ကို မြေပုံမြင်ကွင်းထဲတွင် ထည့်သွင်းဖော်မပြပါ။ သို့သော် ``runAndLoadResults()`` ကိုအသုံးပြုလျှင် မြေပုံတွင် ထည့်သွင်းဖော်ပြပေးပါသည်။

:meth:`run() <qgis.core.QgsProcessingAlgorithm.run>` နည်းလမ်းသည် key များနှင့် ရလာဒ်များ၏ file လမ်းကြောင်းများအဖြစ် တစ်ခု သို့မဟုတ် ပိုများသော ရလာဒ်နာမည်များ (algorithm ဖော်ပြချက်တွင် ပြသထားသောအရာများ) ဖြင့် dictionary တစ်ခုကို တန်ဖိုးများအနေဖြင့် ပြန်ထုတ်ပေးပါသည် -

.. code-block:: python
   :linenos:

    >>> myresult = processing.run("native:buffer", {'INPUT': '/data/lines.shp',
                  'DISTANCE': 100.0,
                  'SEGMENTS': 10,
                  'DISSOLVE': True,
                  'END_CAP_STYLE': 0,
                  'JOIN_STYLE': 0,
                  'MITER_LIMIT': 10,
                  'OUTPUT': '/data/buffers.shp'})
    >>> myresult['OUTPUT']
    /data/buffers.shp

သက်ဆိုင်ရာ file လမ်းကြောင်းများကို ``load()`` သို့ပို့ဆောင်သော နည်းလမ်းကိုအသုံးပြုပြီး Feature ရလာဒ်ကို ခေါ်ယူထည့်သွင်းနိုင်ပါသည်။ သို့မဟုတ် ၎င်းတို့ကို ချက်ချင်းခေါ်ယူထည့်သွင်းရန်အတွက် :meth:`run() <qgis.core.QgsProcessingAlgorithm.run>` အစား ``runAndLoadResults()`` ကိုအသုံးပြုနိုင်ပါသည်။

Console မှ algorithm dialog ကိုဖွင့်လိုလျှင် ``createAlgorithmDialog`` နည်းလမ်းကိုအသုံးပြုနိုင်ပါသည်။ မဖြစ်မနေထည့်ရမည့် parameter မှာ algorithm နာမည်ဖြစ်ပြီး dialog ကိုအလိုအလျှောက်ဖြည့်စွက်စေရန် parameter များ၏ dictionary ကိုလည်း သတ်မှတ်ပေးနိုင်ပါသည်-

.. code-block:: python
   :linenos:

    >>> my_dialog = processing.createAlgorithmDialog("native:buffer", {
                  'INPUT': '/data/lines.shp',
                  'DISTANCE': 100.0,
                  'SEGMENTS': 10,
                  'DISSOLVE': True,
                  'END_CAP_STYLE': 0,
                  'JOIN_STYLE': 0,
                  'MITER_LIMIT': 10,
                  'OUTPUT': '/data/buffers.shp'})
    >>> my_dialog.show()

``execAlgorithmDialog`` နည်းလမ်းသည် dialog ကိုချက်ချင်းပွင့်စေပါသည် - 

.. code-block:: python
   :linenos:

    >>> processing.execAlgorithmDialog("native:buffer", {
                  'INPUT': '/data/lines.shp',
                  'DISTANCE': 100.0,
                  'SEGMENTS': 10,
                  'DISSOLVE': True,
                  'END_CAP_STYLE': 0,
                  'JOIN_STYLE': 0,
                  'MITER_LIMIT': 10,
                  'OUTPUT': '/data/buffers.shp'})


Creating scripts and running them from the toolbox (Script များဖန်တီးခြင်းနှင့် ၎င်းတို့ကို toolbox မှ လုပ်ဆောင်စေခြင်း)
-------------------------------------------------------------------------------------------------------------------------

Python code များရေးသားပြီး ကိုယ်ပိုင် algorithm များဖန်တီးနိုင်ပါသည်။ Processing script များသည် :class:`QgsProcessingAlgorithm <qgis.core.QgsProcessingAlgorithm>` ကိုချဲ့ထွင်ပေးပါသည်။ ထို့ကြောင့် မဖြစ်မနေလုပ်ဆောင်ရမည့် လုပ်ဆောင်ချက်များကို အကောင်အထည်ဖော်ရန် code တွင် စာကြောင်းအချို့ဖြည့်စွက်ရေးသားရန်လိုအပ်ပါသည်။ Processing toolbox ၏ အပေါ်ထိပ်တွင်ရှိသော :guilabel:`Scripts` dropdown menu အောက်တွင် :guilabel:`Create new script` (clean sheet) နှင့် :guilabel:`Create New Script from Template` (:class:`QgsProcessingAlgorithm <qgis.core.QgsProcessingAlgorithm>` ၏ မဖြစ်မနေလုပ်ဆောင်ရမည့် လုပ်ဆောင်ချက်များအတွက် code များပါဝင်သော template) များကို တွေ့နိုင်ပါသည်။ ထို script ကို :file:`.py` extension ဖြင့် :file:`scripts` folder (File သိမ်းဆည်းခြင်း dialog ကို ဖွင့်လျှင် ပေါ်လာသော default folder) ထဲတွင်သိမ်းဆည်းလိုက်ခြင်းသည် သက်ဆိုင်ရာ algorithm ကိုဖန်တီးသင့်ပါသည်။

Algorithm ၏ အမည် (toolbox ထဲတွင်တွေ့ရမည့်တစ်ခု) ကို code ထဲတွင် သတ်မှတ်ပါသည်။

Layer ကိုပထမအဆင့် ချောမွေ့အောင်လုပ်ပြီးနောက် အသုံးပြုသူမှရွေးချယ်သတ်မှတ်သော vector layer ပေါ်တွင် သတ်မှတ် buffer အကွာအဝေးဖြင့် buffer ကိုလုပ်ဆောင်ပေးသော Processing algorithm တစ်ခုကိုသတ်မှတ်ပေးသည့် အောက်ဖော်ပြပါ code ကိုတစ်ချက်ကြည့်ကြည့်ပါ။


.. code-block:: python
  :linenos:

  from qgis.core import (QgsProcessingAlgorithm, 
         QgsProcessingParameterNumber,
         QgsProcessingParameterFeatureSource,
         QgsProcessingParameterFeatureSink)

  from qgis import processing

  class algTest(QgsProcessingAlgorithm):
      INPUT_BUFFERDIST = 'BUFFERDIST'
      OUTPUT_BUFFER = 'OUTPUT_BUFFER'
      INPUT_VECTOR = 'INPUT_VECTOR'

      def __init__(self):
          super().__init__()

      def name(self):
          return "algTest"

      def displayName(self):
          return "algTest script"

      def createInstance(self):
          return type(self)()

      def initAlgorithm(self, config=None):
          self.addParameter(QgsProcessingParameterFeatureSource(
              self.INPUT_VECTOR, "Input vector"))
          self.addParameter(QgsProcessingParameterNumber(
              self.INPUT_BUFFERDIST, "Buffer distance", 
              QgsProcessingParameterNumber.Double,
              100.0))
          self.addParameter(QgsProcessingParameterFeatureSink(
              self.OUTPUT_BUFFER, "Output buffer"))

      def processAlgorithm(self, parameters, context, feedback):
          #DO SOMETHING
          algresult = processing.run("native:smoothgeometry",
              {'INPUT': parameters[self.INPUT_VECTOR],
               'ITERATIONS':2,
               'OFFSET':0.25,
               'MAX_ANGLE':180,
               'OUTPUT': 'memory:'},
              context=context, feedback=feedback, is_child_algorithm=True)
          smoothed = algresult['OUTPUT']
          algresult = processing.run('native:buffer',
              {'INPUT': smoothed,
              'DISTANCE': parameters[self.INPUT_BUFFERDIST],
              'SEGMENTS': 5,
              'END_CAP_STYLE': 0,
              'JOIN_STYLE': 0,
              'MITER_LIMIT': 10,
              'DISSOLVE': True,
              'OUTPUT': parameters[self.OUTPUT_BUFFER]},
              context=context, feedback=feedback, is_child_algorithm=True)
          buffered = algresult['OUTPUT']
          return {self.OUTPUT_BUFFER: buffered}

မဖြစ်မနေလိုအပ်သော ထည့်သွင်းမှုများပြုလုပ်ပြီးနောက် အောက်ပါ :class:`QgsProcessingAlgorithm <qgis.core.QgsProcessingAlgorithm>` လုပ်ဆောင်ချက်များကို သတ်မှတ်ပါသည် -

* :meth:`name() <qgis.core.QgsProcessingAlgorithm.name>` - Algorithm ၏ id (စာလုံးအသေး) 
* :meth:`displayName() <qgis.core.QgsProcessingAlgorithm.displayName>` - Algorithm အတွက် ဖတ်ရှုနိုင်သော အမည်တစ်ခု။
* :meth:`createInstance() <qgis.core.QgsProcessingAlgorithm.createInstance>` - Algorithm အမျိုးအစား၏ ဖြစ်စဉ် (instance) တစ်ခုကို ဖန်တီးပေးပါသည်။ 
* :meth:`initAlgorithm() <qgis.core.QgsProcessingAlgorithm.initAlgorithm>` - parameterDefinition နှင့် outputDefinition များကို ပြင်ဆင်သတ်မှတ်ပါသည်။

  Algorithm ၏ parameter များနှင့် ရလာဒ်များကို ဤတွင်ဖော်ပြပါသည်။ ဒီကိစ္စတွင် ထည့်သွင်းအသုံးပြုသော အချက်အလက်အတွက် feature source တစ်ခု၊ ရလာဒ်အတွက် feature sink နှင့် buffer အကွာအဝေးအတွက် နံပါတ်တစ်ခု။
* :meth:`processAlgorithm() <qgis.core.QgsProcessingAlgorithm.processAlgorithm>` - အလုပ်ကိုလုပ်ဆောင်ပါသည်။

  Geometry ကိုချောမွေ့စေရန် ``smoothgeometry`` algorithm ကိုပထမဆုံး လုပ်ဆောင်ပါသည်။ ထို့နောက် ချောမွေ့အောင်ပြုလုပ်ထားသော ရလာဒ်ပေါ်တွင် ``buffer`` algorithm ကိုလုပ်ဆောင်ပါသည်။ အခြား algorithm အတွင်းတွင် algorithm များကိုလုပ်ဆောင်နိုင်ရန် ``is_child_algorithm`` argument ကို :const:`True` ကို သတ်မှတ်ပေးရန်လိုအပ်ပါသည်။ ထည့်သွင်းအသုံးပြုသောနှင့် ထွက်လာသော parameter များကို ``smoothgeometry`` နှင့် ``buffer`` algorithm များအတွက် parameter များအဖြစ် မည်သို့အသုံးပြုသည်ကို တွေ့နိုင်ပါသည်။

Input နှင့် output များအတွက် parameter အမျိုးအစားများစွာရှိပါသည်။ အောက်တွင် အက္ခရာစဉ်အလိုက် စီစဉ်ပြသထားပါသည် -

.. list-table:: Input နှင့် output algorithm parameter အမျိုးအစားများ စာရင်း
   :class: longtable

   * - :class:`QgsProcessingParameterAggregate <qgis.core.QgsProcessingParameterAggregate>`
     - :class:`QgsProcessingParameterAnnotationLayer <qgis.core.QgsProcessingParameterAnnotationLayer>`
     - :class:`QgsProcessingParameterAuthConfig <qgis.core.QgsProcessingParameterAuthConfig>`
     - :class:`QgsProcessingParameterBand <qgis.core.QgsProcessingParameterBand>`
   * - :class:`QgsProcessingParameterBoolean <qgis.core.QgsProcessingParameterBoolean>`
     - :class:`QgsProcessingParameterColor <qgis.core.QgsProcessingParameterColor>`
     - :class:`QgsProcessingParameterCoordinateOperation <qgis.core.QgsProcessingParameterCoordinateOperation>`
     - :class:`QgsProcessingParameterCrs <qgis.core.QgsProcessingParameterCrs>`
   * - :class:`QgsProcessingParameterDatabaseSchema <qgis.core.QgsProcessingParameterDatabaseSchema>`
     - :class:`QgsProcessingParameterDatabaseTable <qgis.core.QgsProcessingParameterDatabaseTable>`
     - :class:`QgsProcessingParameterDateTime <qgis.core.QgsProcessingParameterDateTime>`
     - :class:`QgsProcessingParameterDistance <qgis.core.QgsProcessingParameterDistance>`
   * - :class:`QgsProcessingParameterEnum <qgis.core.QgsProcessingParameterEnum>`
     - :class:`QgsProcessingParameterExpression <qgis.core.QgsProcessingParameterExpression>`
     - :class:`QgsProcessingParameterExtent <qgis.core.QgsProcessingParameterExtent>`
     - :class:`QgsProcessingParameterFeatureSink <qgis.core.QgsProcessingParameterFeatureSink>`
   * - :class:`QgsProcessingParameterFeatureSource <qgis.core.QgsProcessingParameterFeatureSource>`
     - :class:`QgsProcessingParameterField <qgis.core.QgsProcessingParameterField>`
     - :class:`QgsProcessingParameterFieldMapping  <qgis.core.QgsProcessingParameterFieldMapping>`
     - :class:`QgsProcessingParameterFile <qgis.core.QgsProcessingParameterFile>`
   * - :class:`QgsProcessingParameterFileDestination <qgis.core.QgsProcessingParameterFileDestination>`
     - :class:`QgsProcessingParameterFolderDestination <qgis.core.QgsProcessingParameterFolderDestination>`
     - :class:`QgsProcessingParameterGeometry <qgis.core.QgsProcessingParameterGeometry>`
     - :class:`QgsProcessingParameterLayout <qgis.core.QgsProcessingParameterLayout>`
   * - :class:`QgsProcessingParameterLayoutItem <qgis.core.QgsProcessingParameterLayoutItem>`
     - :class:`QgsProcessingParameterMapLayer <qgis.core.QgsProcessingParameterMapLayer>`
     - :class:`QgsProcessingParameterMapTheme <qgis.core.QgsProcessingParameterMapTheme>`
     - :class:`QgsProcessingParameterMatrix <qgis.core.QgsProcessingParameterMatrix>`
   * - :class:`QgsProcessingParameterMeshLayer <qgis.core.QgsProcessingParameterMeshLayer>`
     - :class:`QgsProcessingParameterMultipleLayers <qgis.core.QgsProcessingParameterMultipleLayers>`
     - :class:`QgsProcessingParameterNumber <qgis.core.QgsProcessingParameterNumber>`
     - :class:`QgsProcessingParameterPoint <qgis.core.QgsProcessingParameterPoint>`
   * - :class:`QgsProcessingParameterPointCloudAttribute <qgis.core.QgsProcessingParameterPointCloudAttribute>`
     - :class:`QgsProcessingParameterPointCloudLayer <qgis.core.QgsProcessingParameterPointCloudLayer>`
     - :class:`QgsProcessingParameterProviderConnection <qgis.core.QgsProcessingParameterProviderConnection>`
     - :class:`QgsProcessingParameterRange <qgis.core.QgsProcessingParameterRange>`
   * - :class:`QgsProcessingParameterRasterDestination <qgis.core.QgsProcessingParameterRasterDestination>`
     - :class:`QgsProcessingParameterRasterLayer <qgis.core.QgsProcessingParameterRasterLayer>`
     - :class:`QgsProcessingParameterScale <qgis.core.QgsProcessingParameterScale>`
     - :class:`QgsProcessingParameterString <qgis.core.QgsProcessingParameterString>`
   * - :class:`QgsProcessingParameterVectorDestination <qgis.core.QgsProcessingParameterVectorDestination>`
     - :class:`QgsProcessingParameterVectorLayer <qgis.core.QgsProcessingParameterVectorLayer>`
     - :class:`QgsProcessingParameterVectorTileDestination <qgis.core.QgsProcessingParameterVectorTileDestination>`
     - :class:`QgsProcessingParameterVectorTileWriterLayers <qgis.core.QgsProcessingParameterVectorTileWriterLayers>`


Constructor များအတွက် ပထမဆုံး parameter မှာ parameter ၏အမည်ဖြစ်ပြီး ဒုတိယမှာ paramter ၏ ရေးသားဖော်ပြချက်ဖြစ်ပါသည် (User Interface အတွက်)။ Constructor parameter များ၏ကျန်ရှိသောအရာများမှာ သီးခြား parameter အမျိုးအစားများ ဖြစ်ပါသည်။

:class:`QgsProcessingAlgorithm <qgis.core.QgsProcessingAlgorithm>` ၏ ``parameterAs`` function များကိုအသုံးပြုပြီး input များကို QGIS အမျိုးအစားများအဖြစ် ပြောင်းလဲနိုင်ပါသည်။ ဥပမာ- buffer အကွာအဝေးအတွက် အသုံးပြုသောနံပါတ်ကို double အဖြစ်ရရန်-

::
  self.parameterAsDouble(parameters, self.INPUT_BUFFERDIST, context)).

``processAlgorithm`` function သည် algorithm မှသတ်မှတ်ထားသော ရလာဒ်တိုင်းအတွက် တန်ဖိုးများပါဝင်သော dictionary တစ်ခုကို ပြန်ထုတ်ပေးသင့်ပါသည်။ ၎င်းသည် တူညီသော model ထဲတွင် ပါဝင်သော အခြား algorithm များအပါအဝင် အခြား algorithm များမှ ရလာဒ်များကို ဝင်ရောက်အသုံးပြုနိုင်အောင် လုပ်ဆောင်ပေးပါသည်။

ကောင်းကောင်းမွန်မွန် အလုပ်လုပ်ဆောင်သော algorithm များသည် အဓိပ္ပါယ်ရှိသလောက် ရလာဒ်များများကို သတ်မှတ်ပြီး ပြန်ထုတ်ပေးသင့်ပါသည်။ ကိန်းဂဏန်းများ နှင့် စာသားများ ကဲ့သို့ non-feature ရလာဒ်များကို model အတွင်းရှိ နောက်ဆက်တွဲ algorithm များအတွက် ထည့်သွင်းအသုံးပြုသော parameter များအဖြစ် အသုံးပြုနိုင်သောကြောင့် algorithm ကို ပိုကြီးမားသော model တစ်ခု၏ အစိတ်အပိုင်းတစ်ခုအဖြစ် အသုံးပြုသောအခါ အလွန်အသုံးဝင်ပါသည်။ Process လုပ်ဆောင်ထားသော feature အရေအတွက်၊ ကြုံတွေ့ရသည့် ဆီလျော်မှုမရှိသော feature အရေအတွက်၊ ရလာဒ် feature အရေအတွက် ကဲ့သို့ အရာများအတွက် ကိန်းဂဏန်းရလာဒ်များ ပေါင်းထည့်ခြင်းကို ထည့်သွင်းစဉ်းစားပါ။ ရလာဒ်များများထွက်လာလေလေ algorithm ကပိုပြီး အသုံးဝင်လေလေ ဖြစ်ပါသည်။

Feedback (တုန့်ပြန်မှု)
........................

:meth:`processAlgorithm() <qgis.core.QgsProcessingAlgorithm.processAlgorithm>` ဆီသို့လွှဲပြောင်းပေးသော :class:`feedback <qgis.core.QgsProcessingFeedback>` object ကို အသုံးပြုသူ တုန့်ပြန်မှု/အပြန်အလှန်လုပ်ဆောင်မှု အတွက် အသုံးပြုသင့်ပါသည်။ Algorithm ၏ပြီးစီးမှုပမာဏကို အသုံးပြုသူများသိစေရန် ပြီးစီးမှုပြ bar (Progress bar) (0 မှ 100) ကို update ပြုလုပ်ရန်အတွက် :class:`feedback <qgis.core.QgsProcessingFeedback>` object ၏ :meth:`setProgress() <qgis.core.QgsFeedback.setProgress>` function ကိုအသုံးပြုနိုင်ပါသည်။ မိမိလုပ်ဆောင်နေသော algorithm သည် အချိန်ကြာမြင့်စွာ လုပ်ဆောင်ရလျှင် ဒီနည်းလမ်းသည် အလွန်အသုံးဝင်ပါသည်။

:class:`feedback <qgis.core.QgsProcessingFeedback>` object တွင် အသုံးပြုသူမှ algorithm ကို ရပ်တန့်နိုင်စေရန် စောင့်ကြည့်ပေးသင့်သော :meth:`isCanceled() <qgis.core.QgsFeedback.isCanceled>` နည်းလမ်းတစ်ခု ပါရှိပါသည်။ ::class:`feedback <qgis.core.QgsProcessingFeedback>` ၏ :meth:`pushInfo() <qgis.core.QgsProcessingFeedback.pushInfo>` နည်းလမ်းကို အသုံးပြုသူထံသို့ သတင်းအချက်အလက်ပို့ရန် အသုံးပြုနိုင်ပြီး :meth:`reportError() <qgis.core.QgsProcessingFeedback.reportError>` သည် ဆိုးဆိုးရွားရွားမဟုတ်သော အမှားများကို အသုံးပြုသူထံ ပို့ဆောင်ခြင်းအတွက် လွယ်ကူပါသည်။

Statement များကို print ထုတ်ခြင်း သို့မဟုတ် :class:`QgsMessageLog <qgis.core.QgsMessageLog>` တွင် မှတ်တမ်းသိမ်းခြင်း (logging) ကဲ့သို့ အခြား ပုံစံများအသုံးပြုပြီး အသုံးပြုသူများထံသို့ feedback ပေးပို့ခြင်းကို algorithm များမှရှောင်ရှားသင့်ပါသည်။ ၎င်းသည် algorithm အတွက် ကြာရှည်သော logging ကိုခွင့်ပြုပေးပြီး thread-safe လည်းဖြစ်ပါသည် (အရေးကြီးပြီး algorithm များသည် များသောအားဖြင့် နောက်ကွယ်တွင်လုပ်ဆောင်ကြပါသည်)။

Handling errors (အမှားများကိုင်တွယ်ဖြေရှင်းခြင်း )
...................................................

ဆီလျော်မှုမရှိသော input တန်ဖိုးများ သို့မဟုတ် ပြန်လည်ပြင်ဆင်၍မရသော အခြားသောအခြေအနေများကဲ့သို့ ပြဿနာတစ်ခုခုရှိနေပြီး algroithm ကိုစေခိုင်းလုပ်ဆောင်၍မရသောအခါ :class:`QgsProcessingException <qgis.core.QgsProcessingException>` တစ်ခုကို လုပ်ဆောင်သင့်ပါသည်။ 
E.g.::

  if feature['value'] < 20:
    raise QgsProcessingException('Invalid input value {}, must be >= 20'.format(feature['value']))

ဆိုးဆိုးရွားရွားမဟုတ်သော အမှားများ (non-fatal errors) အတွက် (ဥပမာ- feature တစ်ခုသည် null geometry ရှိနေသောအခါ) :class:`QgsProcessingException <qgis.core.QgsProcessingException>` အသုံးပြုခြင်းကို မလုပ်ဆောင်သင့်ပါ၊ ၎င်းကိုအသုံးပြုမည့်အစား ဆိုးဆိုးရွားရွားမဟုတ်သော အမှားများကို ``feedback.reportError()`` မှတဆင့် တင်ပြပြီး ၎င်း feature ကို ကျော်ပစ်လိုက်ပါ။ ၎င်းသည် ဆိုးဆိုးရွားရွားမဟုတ်သောအမှားတစ်ခု ကြုံတွေ့ရသောအခါ algorithm တစ်ခုလုံး၏လုပ်ဆောင်မှုကို ရပ်တန့်ပစ်ခြင်းမှရှောင်ရှားပေးသောကြောင့် သင့် algorithm အား "model-friendly" ဖြစ်စေပါသည်။

Documenting your scripts (မိမိ၏ script များကို မှတ်တမ်းပြုစုခြင်း)
...................................................................

Model များနှင့်လုပ်ဆောင်သောအခါ script များနှင့်ပတ်သက်ပြီး ၎င်းတို့ မည်သည့်အရာများလုပ်ဆောင်သည်နှင့် ၎င်းတို့အားမည်သို့အသုံးပြုရမည်ကို ရှင်းပြရန် မိမိ၏ script များအတွက် ဖြည့်စွက်မှတ်တမ်းများ ဖန်တီးနိုင်ပါသည်။

ထိုသို့ရေးသားရန်အတွက် :class:`QgsProcessingAlgorithm <qgis.core.QgsProcessingAlgorithm>` သည် :meth:`helpString() <qgis.core.QgsProcessingAlgorithm.helpString>`၊ :meth:`shortHelpString() <qgis.core.QgsProcessingAlgorithm.shortHelpString>` နှင့် :meth:`helpUrl() <qgis.core.QgsProcessingAlgorithm.helpUrl>` function များကို လုပ်ဆောင်ပေးပါသည်။ အသုံးပြုသူများအတွက် အကူအညီပိုမိုရရှိစေရန် ၎င်းတို့ကို သတ်မှတ်ဖော်ပြ/အစားထိုးဖော်ပြပေးပါ။

Toolbox ထဲရှိ algorithm ပေါ်တွင် mouse ကိုတင်ထားသောအခါ စာသားဖော်ပြသည့် tooltip ထဲတွင် :meth:`shortDescription() <qgis.core.QgsProcessingAlgorithm.shortDescription>` ကိုအသုံးပြုပါသည်။

Pre- and post-execution script hooks (စေခိုင်းလုပ်ဆောင်ခြင်းမတိုင်မီ နှင့် စေခိုင်းလုပ်ဆောင်ခြင်းအပြီး script ချိတ်များ)
-------------------------------------------------------------------------------------------------------------------------

Script များကို algorithm လုပ်ဆောင်ခြင်းမတိုင်မီနှင့် လုပ်ဆောင်ခြင်းအပြီးတွင် လုပ်ဆောင်ပေးသော pre-execution (စေခိုင်းလုပ်ဆောင်ခြင်းမတိုင်မီ) နှင့် post-execution (စေခိုင်းလုပ်ဆောင်ခြင်းအပြီး) script hook များအဖြစ်လည်း အသုံးပြုနိုင်ပါသည်။ Algorithm တစ်ခုကိုစေခိုင်းလုပ်ဆောင်သည့်အချိန်တိုင်း လုပ်ဆောင်သင့်သည့် task များကို အလိုအလျှောက်အလုပ်လုပ်စေရန် ၎င်းကို အသုံးပြုနိုင်ပါသည်။

Syntax သည် အပေါ်ရှင်းပြခဲ့သော syntax နှင့်တစ်ပုံစံတည်းတူပါသည်၊ သို့သော် စေခိုင်းလုပ်ဆောင်ပြီးသော (သို့မဟုတ် စေခိုင်းလုပ်ဆောင်တော့မည့်) algorithm ကိုကိုယ်စားပြုသော ``alg`` ဟုခေါ်သည့် global variable တစ်ခုကိုအသုံးပြုနိုင်ပါသည်။

ကိစ္စတစ်ခုစီတွင် လုပ်ဆောင်မည့် script များ၏ filename များကိုထည့်သွင်းနိုင်သော :guilabel:`Pre-execution script` နှင့် :guilabel:`Post-execution script` entry နှစ်ခုကို Processing options dialog ၏ :guilabel:`General` အုပ်စုထဲတွင် တွေ့ရပါလိမ့်မည်။