.. index:: GPS tracking
.. _`sec_gpstracking`:

GPS ဖြင့် live လမ်းကြောင်းခြေရာခံဆွဲခြင်း (Live GPS tracking)
==============================================================

.. only:: html

   .. contents::
      :local:

QGIS ထဲတွင် live GPS tracking ကိုဖွင့်ရန်အတွက် :menuselection:`View --> Panels` |checkbox| :guilabel:`GPS Information Panel` ကိုရွေးချယ်ပါ သို့မဟုတ် :kbd:`Ctrl+0` ကိုနှိပ်ပါ။ Canvas ၏ ဘယ်ဘက်ခြမ်းတွင် ကပ်ပြီးပွင့်လာသော (dock) window အသစ်တစ်ခုပေါ်လာပါလိမ့်မည်။ 

GPS tracking window ထဲတွင် ဖြစ်နိုင်ခြေရှိသော screen ၃ မျိုးရှိပါသည် -

* |metadata| :sup:`Position` - GPS နေရာတန်ဖိုးများနှင့် vertex (ထောင့်မှတ်) များနှင့် feature များကို လက်ဖြင့် ရိုက်ထည့်ရန် interface တစ်ခု။ 
* |gpsTrackBarChart| :sup:`Signal` - ဂြိုလ်တုချိတ်ဆက်မှုများ၏ အချက်ပြမှုပြင်းအား (signal strength)
* |options| :sup:`Options` - GPS options screen (see :numref:`figure_gps_options`)
* |options| :sup:`Options` - GPS နှင့်ပတ်သက်သော ရွေးချယ်စရာများ screen (:numref:`figure_gps_options` တွင်ကြည့်ရှပါ)

မိမိစက်ရဲ့ operation system တွင် အလုပ်လုပ်နိုင်သော plugged-in GPS receiver ကိုသုံး၍ :guilabel:`Connect` ကို နှိပ်လိုက်လျှင် GPS ကနေ QGIS ကိုလွယ်ကူစွာချိတ်ဆက်စေပါသည်။ ထို့နောက် ကွန်ပျူတာမှ GPS receiver ကနေ ပြန်ဖြုတ်လိုလျှင် :guilabel:`Disconnect` ကို နှိပ်ပါ။ GNU/Linux အတွက် GPS receiver အများစုကို ချိတ်ဆက်နိုင်ရန် gpsd လုပ်ဆောင်နိုင်မှုကို ပူးပေါင်းလုပ်ဆောင်ထားပါသည်။ ထို့ကြောင့် QGIS ကိုချိတ်ဆက်ရန် gpsd ကို ပထမဆုံး သေချာစွာပြင်ဆင်ထားရန်လိုအပ်ပါသည်။

:guilabel:`Recenter` (အလယ်ပြန်ရောက်ခြင်း) ကို အသုံးပြုလျှင် မြေပုံသည် ယခုလက်ရှိ GPS တည်နေရာဆီသို့ ရွေ့သွားမည်ဖြစ်ပါသည်။

.. warning::
   Canvas ပေါ်တွင် တည်နေရာကိုမှတ်တမ်းတင်ထားချင်လျှင် ပထမဆုံးအနေဖြင့် vector layer တစ်ခုဖန်တီးရမည်ဖြစ်ပြီး ၎င်း vector ကို ပြင်ဆင်တည်းဖြတ်နိုင်သော (editable) အနေအထားသို့ ပြောင်းထားပြီးမှ လမ်းကြောင်းကို ထည့်သွင်းမှတ်တမ်းတင်လို့ရမည်ဖြစ်ပါသည်။   

GPS စက်တစ်လုံးကိုချိတ်ဆက်လိုက်ပြီး mouse cursor ကို map canvas ပေါ်တွင် ရွှေ့လိုက်သောအခါ mouse cursor နှင့် GPS တည်နေရာ အကွာအဝေးနှင့် bearing (လားရာအညွှန်းထောင့်) ကို live (အချိန်နှင့်တပြေးညီ) message ဖြင့် ပြသပေးပါသည်။ Project အကွာဝေးနှင့် bearing အပြင်အဆင်များကို ဤမျက်နှာပြင်တွင် ပြသပေးပါသည်။

.. tip:: **Touch Screen Devices (Touch screen အသုံးပြုနိုင်သော စက်များ)**

 Touch screen အသုံးပြုနိုင်သော စက်များတွင် live status ကိုကြည့်ရန်အတွက် ထိပြီးဖိထားလိုက်ပါ။

Position and additional attributes (တည်နေရာနှင့် ထပ်ပေါင်းအချက်အလက်များ)
-------------------------------------------------------------------------

|metadata| GPS သည် ဂြိုလ်တုမှ အချက်ပြမှုများကို လက်ခံရယူနေလျှင် တည်နေရာ၏ လတ္တီကျု၊ လောင်ဂျီကျု နှင့် အမြင့် များကို ထပ်ပေါင်းအချက်အလက်များနှင့်အတူ တွေ့မြင်ရပါမည်။

.. _figure_gps_position:

.. figure:: img/gpstrack_main.png
   :align: center

   တည်နေရာကို GPS ဖြင့် ခြေရာခံဆွဲခြင်း နှင့် ထပ်ပေါင်းအချက်အလက်များ

GPS signal strength (GPS အချက်ပြမှုပြင်းအား)
---------------------------------------------

|gpsTrackBarChart| တွင် အချက်ပြမှုများ ရယူနေသော ဂြိုလ်တုများ၏ အချက်ပြမှုပြင်းအား (signal strength) ကို မြင်တွေ့နိုင်ပါသည်။

.. _figure_gps_strength:

.. figure:: img/gpstrack_strength.png
   :align: center

   GPS ဖြင့်ခြေရာခံခြင်း အချက်ပြမှုပြင်းအား


GPS options (GPS နှင့် ပတ်သက်သော ရွေးချယ်စရာများ)
--------------------------------------------------

.. _figure_gps_options:

.. figure:: img/gpstrack_options.png
   :align: center

   GPS ခြေရာခံခြင်း ရွေးချယ်စရာများ window

အောက်တွင်အသေးစိတ် သတ်မှတ်နိုင်ပါသည်- 

* :guilabel:`Connection (ချိတ်ဆက်မှု)`

  * ချိတ်ဆက်မှုပြဿနာရှိနေလျှင် အောက်ပါတို့ထဲမှ တစ်ခုခုကိုပြောင်းလဲ ရွေးချယ်အသုံးပြုနိုင်ပါသည်- 

    * |radioButtonOn| :guilabel:`Autodetect (အလိုလျှောက်ရှာဖွေခြင်း)`
    * |radioButtonOff| :guilabel:`Serial device` (GPS စက်အသစ်တစ်လုံးချိတ်ဆက်လျှင် reload လုပ်ပေးရန်လိုအပ်ပါသည်)
	  * |radioButtonOff| :guilabel:`gpsd` (Host (လက်ခံ)၊ Port (အပေါက်) နှင့် GPS ချိတ်ဆက်ထားသော စက်များကို ရွေးချယ်ခြင်း) 

  * :guilabel:`Connect` ကိုထပ်နှိပ်လျှင် GPS receiver နှင့် ချိတ်ဆက်မှု စတင်ပါသည်။

* :guilabel:`Digitizing (မြေပုံအချက်အလက်ရေးဆွဲခြင်း)`

  * တည်းဖြတ်ပြင်ဆင်ခြင်း (editing) mode တွင်ရှိနေလျှင် |checkbox| :menuselection:`Automatically save added features (အသစ်ထည့်လိုက်သော feature များကို အလိုအလျှောက်သိမ်းဆည်းခြင်း)` ကိုအမှန်ခြစ် ခြစ်ထားနိုင်ပါသည်။ သို့မဟုတ် map canvas ထဲသို့ သေချာသော အထူနှင့် အရောင်တို့ဖြင့် အမှတ်များအလိုအလျှောက်ထည့်ရန် |checkbox|:guilabel:`Automatically add points` ကို အမှန်ခြစ် ခြစ်ထားနိုင်ပါသည်။
  * Device သည် လွဲမှားနေသော bearing တိုင်းတာမှုများကိုပြသနေလျှင် :guilabel:`Calculate bearing from travel direction (သွားနေသောဦးတည်ရာမှ bearing တွက်ချက်ခြင်း)` ကိုအသုံးပြုနိုင်ပါသည်။ ၎င်းသည် ရှေ့ကတိုင်းတာခဲ့သော တည်နေရာနှစ်ခုပေါ်တွင် အခြေခံ၍ GPS bearing ကိုတွက်ထုတ်ပေးမည်ဖြစ်ပါသည်။

* :guilabel:`Cursor` - Canvas (မြင်ကွင်း) ပေါ်တွင် cursor တည်နေရာကို ကျုံ့ရန် နှင့် ချဲ့ရန်အတွက် slider |slider| ကိုအသုံးပြုနိုင်ပါသည်။

* :guilabel:`Filtering` - Receiver သည် တည်ငြိမ်သောအခြေနေများတွင်ရှိနေသောအခါ cursor ကို အသက်ဝင်နေစေရန် :guilabel:`Acquisition interval (seconds) (လက်ခံရယူရန်ကြာချိန် (စက္ကန့်))` နှင့် :guilabel:`Distance threshold (meters) (အကွာအဝေး သတ်မှတ်တန်ဖိုး (မီတာ))` parameter များကို သတ်မှတ်ပေးနိုင်ပါသည်။

* :guilabel:`Map Centering and Rotation (မြေပုံကို အလယ်ဗဟိုတည့်အောင်ပြုလုပ်ခြင်း နှင့် လှည့်ခြင်း)`

  * |radioButtonOn| :guilabel:`Map centering` ကို ဖွင့်ထားခြင်းသည် canvas ကို မည်သည့်ပုံစံဖြင့် update (နောက်ဆုံးရောက်အခြေအနေရအောင်ပြုလုပ်ခြင်း) ပြုလုပ်မည်ကို ဆုံးဖြတ်ပေးနိုင်ပါသည်။ မှတ်သားထားသော တည်နေရာတန်ဖိုးများသည် canvas ၏ အပြင်ဘက်သို့ရောက်နေလျှင် 'always (အမြဲတမ်း)'၊ 'when leaving (ထွက်သွားသောအခါ)'၊  သို့မဟုတ် မြေပုံ extent (စတုဂံပုံအကျယ်အဝန်း) အတိုင်းထားရန် 'never (ဘယ်တော့မှ မရွှေ့ခြင်း)' တို့ပါဝင်ပါသည်။
  * :guilabel:`Rotate map to match GPS direction (GPS ၏ဦးတည်ရာအတိုင်းကိုက်ညီစေရန် မြေပုံကိုလှည့်ခြင်း)` ကို ဖွင့်ထားခြင်းသည် GPS bearing ၏ ဦးတည်ရာအတိုင်း တူညီသောဘက်ကို မျက်နှာမူစေရန် map canvas ကို အလိုလျှောက်လှည့်ပေးပါသည်။


* :guilabel:`Show Bearing Line (Bearing မျဉ်းကို ပြသပါ)` ကို ဖွင့်ထားခြင်းသည် GPS ၏ လက်ရှိ လမ်းကြောင်းဦးတည်ရာထဲတွင် GPS တည်နေရာမှ လမ်းကြောင်းတစ်ခုကိုပြသပေးပါမည်။

* နောက်ဆုံးအနေဖြင့် |checkbox| :guilabel:`Log file` ကိုဖွင့်ထားပေးနိုင်ပြီး လမ်းကြောင်းတစ်ခုနှင့် GPS ခြေရာခံခြင်းနှင့်သက်ဆိုင်သော အချက်အလက်များမှတ်ထားမည့် file တစ်ခုကို သတ်မှတ်ပေးပါ။

Feature တစ်ခုကို စိတ်ကြိုက်သတ်မှတ်လိုလျှင် |metadata|:sup:`Position` ကို ပြန်သွားရမည်ဖြစ်ပြီး :guilabel:`Add Point (Point ပေါင်းထည့်ပါ)` သို့မဟုတ် :guilabel:`Add Track Point (လမ်းကြောင်း Point ပေါင်းထည့်ပါ)` ကို နှိပ်ပါ။

Connect to a Bluetooth GPS for live tracking (Live လမ်းကြောင်းခြေရာခံရန်အတွက် bluetooth GPS သို့ချိတ်ဆက်ခြင်း)
---------------------------------------------------------------------------------------------------------------

ကွင်း data များကောက်ယူစုဆောင်းခြင်းအတွက် QGIS နှင့် bluetooth GPS ကိုချိတ်ဆက်နိုင်ပါသည်။ ထိုသို့လုပ်ဆောင်ရန် GPS Bluetooth device တစ်ခုနှင့် ကွန်ပျူတာတွင် Bluetooth receiver တစ်ခုလိုအပ်ပါသည်။

ပထမဆုံးအနေခြင့် GPS device ကို ကွန်ပျူတာက သိအောင်လုပ်ပြီး ကွန်ပျူတာနှင့် ချိတ်ဆက်ရပါမည်။ GPS ကိုဖွင့်ပြီး notification area ထဲရှိ Bluetooth icon ကိုသွား၍ device အသစ်တစ်ခုကိုရှာပါ။

အသုံးပြုနိုင်သောစာရင်းထဲတွင် မိမိ၏ GPS ပေါ်နေစေရန် Device ၏ ညာဘက်ခြမ်းတွင် ရွေးချယ်ခြင်း mask သည် device များအားလုံးရွေးချယ်ထားခြင်းကို သေချာအောင်လုပ်ဆောင်ပေးပါသည်။ နောက်တစ်ဆင့်တွင် serial connecion service ရရှိသင့်မည်ဖြစ်ပြီး ၎င်းကိုရွေးချယ်ကာ :guilabel:`Configure (စိတ်ကြိုက်ပြင်ဆင်ခြင်း)` ခလုတ်ကိုနှိပ်ပါ။

Bluetooth property များဖြင့်ရလာသော GPS ချိတ်ဆက်မှုကိုသတ်မှတ်ပေးထားသော COM port အရေအတွက်ကို မှတ်သားထားပါ။

GPS ကို ကွန်ပျူတာမှ သိရှိပြီးသည်နှင့် ချိတ်ဆက်ခြင်းလုပ်ဆောင်ပါ။ များသောအားဖြင့် ချိတ်ဆက်ရန်အသုံးပြုသော ဂဏန်းမှာ ``0000`` ဖြစ်ပါသည်။

:guilabel:`GPS information` panel ကိုဖွင့်ပြီး |options| GPS options screen သို့ပြောင်းလဲပါ။ GPS ချိတ်ဆက်မှုအတွက် သတ်မှတ်ပေးထားသော COM port ကိုရွေးချယ်ပြီး :guilabel:`Connect (ချိတ်ဆက်ပါ)` ကို နှိပ်ပါ။ ခဏကြာပြီးနောက် မိမိ၏တည်နေရာကိုဖော်ပြနေသည့် cursor တည်နေရာတစ်ခု ပေါ်လာပါလိမ့်မည်။

QGIS သည် GPS data များကိုလက်မခံနိုင်လျှင် GPS ကို ပိတ်ပြီးပြန်ဖွင့်သင့်ပါသည်။ ၅ စက္ကန့်မှ ၁၀ စက္ကန့်လောက်ထိ စောင့်ပြီး ထပ်မံချိတ်ဆက်ကြည့်ပါ။ များသောအားဖြင့် ဒီနည်းလမ်းဖြင့် ပြဿနာကိုဖြေရှင်းနိုင်ပါသည်။ ချိတ်ဆက်မှုပြဿနာထပ်မံရှိနေဆဲဆိုလျှင် ၎င်း GPS ချိတ်ဆက်နေသော တခြား Bluetooth device တစ်ခု အနီးအနားတွင် ရှိမရှိ စစ်ဆေးပြီး ချိတ်ဆက်မှုဖြုတ်ပစ်ပါ။

Using GPSMAP 60cs (GPSMAP 60cs ကိုအသုံးပြုခြင်း)
-------------------------------------------------

MS Windows
...........

၎င်းအလုပ်လုပ်ဆောင်ရန် အလွယ်ကူဆုံးနည်းလမ်းမှာ `GPSGate <https://gpsgate.com/gpsgate-splitter>` ဟုခေါ်သော middleware (freeware၊ not open) ကိုအသုံးပြုခြင်းဖြစ်ပါသည်။

Program ကိုဖွင့်ပြီး GPS device များကိုရှာပါ (USB နှင့် bluetooth ၂ မျိုးလုံးအတွက် အလုပ်လုပ်ပါသည်)၊ ထို့နောက် QGIS ထဲတွင် |radioButtonOn| :guilabel:`Autodetect` mode ကိုအသုံးပြုပြီး Live tracking panel ထဲရှိ :guilabel:`Connect` ကိုနှိပ်ပါ။

Ubuntu/Mint GNU/Linux
......................

Window ကွန်ပျူတာများအတွက်ကဲ့သို့ အလွယ်ကူဆုံးနည်းလမ်းမှာ အလယ်ရှိ server တစ်ခုကို အသုံးပြုရန်ဖြစ်ပြီး ယခု OS များအတွက်တော့ GPSD ဖြစ်ပါသည်။ ထို့ကြောင့် - 

::

  sudo apt install gpsd

ထို့နောက် ``garmin_gps`` kernel module ကိုခေါ်ယူထည့်သွင်းပါ။

::

  sudo modprobe garmin_gps

ထို့နောက် unit ကိုချိတ်ဆက်ပါ။ Unit မှ အသုံးပြုနေသော တကယ့် device ကို ``dmesg`` ဖြင့်စစ်ဆေးပါ၊ ဥပမာ- ``/dev/ttyUSB0``။ ထို့နောက် gpsd ကို စတင်ဖွင့်နိုင်ပါပြီ။

::

  gpsd /dev/ttyUSB0

နောက်ဆုံးအဆင့်အဖြစ် QGIS live tracking tool နှင့်ချိတ်ဆက်ပါ။

Using BTGP-38KM datalogger (only Bluetooth) (BTGP-38KM datalogger ကိုအသုံးပြုခြင်း (Bluetooth ပစ္စည်းများအတွက်သာ))
-------------------------------------------------------------------------------------------------------------------

Linux အတွက် GPSD ကို အသုံးပြုခြင်း သို့မဟုတ် Window အတွက် GPSGate သည် အားစိုက်ထုတ်ရန်မလိုအပ်ပါ။

Using BlueMax GPS-4044 datalogger (both BT and USB) (BlueMax GPS-4044 datalogger ကိုအသုံးပြုခြင်း (Bluetooth နှင့် USB ၂ မျိုးလုံးအတွက် အလုပ်လုပ်သည်))
-------------------------------------------------------------------------------------------------------------------------------------------------------

MS Windows
...........

GPSGate သို့မဟုတ် ၎င်းမပါလျှင်ပင် live tracking သည် USB နှင့် Bluetooth ၂ မျိုးလုံးအတွက် အလုပ်လုပ်ပါသည်။ |radioButtonOn| :guilabel:`Autodetect` mode ကို အသုံးပြုပါ သို့မဟုတ် မှန်ကန်သော port ကို ညွှန်ပေးပါ။

Ubuntu/Mint GNU/Linux
......................

**USB အတွက် (For USB)**

Live tracking သည် GPSD သုံးခြင်း သို့မဟုတ် GPSD မသုံးပဲ QGIS live tracking ကို device နှင့် တိုက်ရိုက်ချိတ်ဆက်ခြင်း ၂ မျိုးလုံးနှင့် အလုပ်လုပ်ပါသည်။ (ဥပမာ- ``/dev/ttyACM3``)

::

  gpsd /dev/ttyACM3


**Bluetooth အတွက် (For Bluetooth)**

Live tracking သည် GPSD သုံးခြင်း သို့မဟုတ် GPSD မသုံးပဲ QGIS live tracking ကို device နှင့် တိုက်ရိုက်ချိတ်ဆက်ခြင်း ၂ မျိုးလုံးနှင့် အလုပ်လုပ်ပါသည်။ (ဥပမာ- ``/dev/rfcomm0``)

::

  gpsd /dev/rfcomm0


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |gpsTrackBarChart| image:: /static/common/gpstrack_barchart.png
   :width: 1.5em
.. |metadata| image:: /static/common/metadata.png
   :width: 1.5em
.. |options| image:: /static/common/mActionOptions.png
   :width: 1em
.. |radioButtonOff| image:: /static/common/radiobuttonoff.png
   :width: 1.5em
.. |radioButtonOn| image:: /static/common/radiobuttonon.png
   :width: 1.5em
.. |slider| image:: /static/common/slider.png
