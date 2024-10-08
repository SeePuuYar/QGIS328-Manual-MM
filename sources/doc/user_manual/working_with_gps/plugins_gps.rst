.. _gps_data:

Introducing GNSS/GPS Data (GNSS/GPS data များကိုမိတ်ဆက်ခြင်း)
==============================================================

.. only:: html

   .. contents::
      :local:

.. _`whatsgps`:

What is GPS? (GPS ဆိုတာဘာလဲ)
-----------------------------

GPS **Global Positioning System** ဆိုသည်မှာ GPS receiver ရှိသော မည်သူမဆို ကမ္ဘာကြီးရဲ့ မည်သည့်နေရာတွင်ရှိနေသည်ဖြစ်စေ ဂြိုလ်တုများကို အသုံးပြုပြီး ၎င်းတို့၏တိကျသော တည်နေရာကို ဖော်ပြပေးနိုင်သော စနစ်ဖြစ်ပါသည်။ GPS ကို လမ်းညွှန်ပြသရာတွင် ထောက်ကူပစ္စည်းအဖြစ် အသုံးပြုပါသည်။ ဥပမာ - လေယာဉ်၊ လှေ နှင့် တောင်တက်သူများ။ GPS receiver သည် ၎င်းရဲ့ လတ္တီကျု၊ လောင်ဂျီကျု နှင့် (တခါတရံ) အမြင့်တို့ကို တွက်ချက်ရန်အတွက် ဂြိုလ်တုများမှ အချက်ပြမှုကို ဖမ်းယူလုပ်ဆောင်ပါသည်။ Receiver အများစုသည် အောက်ပါအချက်အလက်များကို သိမ်းဆည်းထားနိုင်စွမ်းရှိပါသည်-

* တည်နေရာများ (**waypoint** များဟုခေါ်ပါသည်)
* စီစဉ်ထားသော **route (လမ်းကြောင်း)** တစ်ခုကိုဖြစ်ပေါ်စေသော တည်နေရာအဆက်များ
* အချိန်နှင့်အမျှ receiver ၏ ရွှေ့လျားခဲ့သော **track (ခြေရာခံလမ်းကြောင်း)** မှတ်တမ်း

Waypoint များ၊ route များ နှင့် track များတို့သည် GPS data ထဲတွင် အခြေခံ feature အမျိုးအစား ၃ မျိုးဖြစ်ပါသည်။ QGIS သည် waypoint များကို point layer များအဖြစ် ဖော်ပြပြီး routes နှင့် tracks များကို linestring layer များအဖြစ် ဖော်ပြပါသည်။

.. note:: QGIS သည် GNSS receiver များနှင့်လည်း အလုပ်လုပ်နိုင်ပါသည်။ သို့သော် ဤ documentation တွင် GNSS အစား GPS ဆိုသည့် အသုံးအနှုန်းကို ဆက်လက်သုံးစွဲသွားပါမည်။

Defining GPS device types (GPS device အမျိုးအစားများကို သတ်မှတ်ခြင်း)
----------------------------------------------------------------------

GPS device အမျိုးအစားများစွာရှိပါသည်။ QGIS သည် ကိုယ်ပိုင် device အမျိုးအစားကိုသတ်မှတ်နိုင်ပြီး :menuselection:`Settings --> Options --> GPS --> GPSBabel` tab အောက်တွင် parameter များသတ်မှတ်နိုင်ပါသည်။ အသေးစိတ်အတွက် :ref:`defining_new_device` တွင်ဖတ်ရှုပါ။

Device အမျိုးအစားအသစ်တစ်ခု ဖန်တီးလိုက်သည်နှင့် download နှင့် upload tool များအတွက် device စာရင်းများထဲတွင် device အသစ်ကို ဖော်ပြပေးမည်ဖြစ်သည်။

.. _`label_loadgps`:

Transferring or loading GPS data (ရွှေ့ပြောင်းခြင်း သို့မဟုတ် GPS data များခေါ်ယူထည့်သွင်းခြင်း)
-------------------------------------------------------------------------------------------------

GPS data များကိုသိမ်းဆည်းခြင်းအတွက် file format အမျိုးအစားများစွာရှိပါသည်။ QGIS မှ အသုံးပြုသော format မှာ GPX (GPS eXchange format) ဖြစ်ပြီး file တစ်ခုတည်းတွင် waypoint များ၊ route များ နှင့် track များပါဝင်သော ဖလှယ်နိုင်သည့် standard (စံ) format တစ်ခုဖြစ်ပါသည်။

:file:`GPX` file တစ်ခုကို ခေါ်ယူထည့်သွင်းရန်အတွက်- 

#. :guilabel:`Data Source Manager` dialog ထဲမှ :guilabel:`GPS` tab ကို ဖွင့်ပါ။ ဆိုလိုသည်မှာ-
   * Toolbar ပေါ်ရှိ |dataSourceManager| :sup:`Open Data Source Manager` ခလုတ်ကိုနှိပ်ပြီး (သို့မဟုတ် :kbd:`Ctrl+L` ကိုနှိပ်ပါ) target tab ကို အသုံးပြုနိုင်ရန်ဖွင့်ပါ။
   * သို့မဟုတ် :menuselection:`Layer --> Add Layer -->` |addGpsLayer|:menuselection:`Add GPX Layer...` ကိုရွေးချယ်ပါ။
#. GPX file ကိုရွေးချယ်ရန် :guilabel:`GPX dataset` ရဲ့ဘေးရှိ :guilabel:`...` :sup:`Browse` ခလုတ်ကိုအသုံးပြုပါ
#. File မှတဆင့် ခေါ်ယူထည့်သွင်းလိုသော :guilabel:`Feature types` (Feature အမျိုးအစား) ကိုရွေးချယ်ရန် check box (အမှန်ခြစ်ခြစ်ရသောနေရာများ) ကိုအသုံးပြုပါ။ Feature အမျိုးအစား တစ်မျိုးချင်းစီ (:guilabel:`Waypoints`၊ :guilabel:`Tracks` သို့မဟုတ် :guilabel:`Routes`) များကို သီးခြား layer တစ်ခုချင်းစီတွင် ခေါ်ယူထည့်သွင်းပါလိမ့်မည်။

.. figure:: ../managing_data_source/img/gps_datasource.png
   :align: center

   GPS Data များခေါ်ယူထည့်သွင်းခြင်း dialog

QGIS သည် GPX file များကိုအသုံးပြုသောကြောင့် အခြား GPS file format များကို GPX format အဖြစ်ပြောင်းလဲဖို့လိုအပ်ပါသည်။ Format များစွာကနေ ပြောင်းလဲခြင်းအတွက် အခမဲ့ အသုံးပြုနိုင်သော `GPSBabel <https://www.gpsbabel.org>` program ကို အသုံးပြုနိုင်ပါသည်။ ဤ program သည် GPS data များကို ကွန်ပျူတာနှင့် GPS device အကြား အကူးအပြောင်းပြုလုပ်ခြင်းအတွက်လည်း အသုံးပြုနိုင်ပါသည်။ ၎င်းတို့ကိုလုပ်ဆောင်ရန်အတွက် QGIS သည် GPSBael ပေါ်တွင် မှီခိုအားထားပြီး :ref:`GPS group <gps_algorithms>` အောက်တွင် အသုံးပြုနိုင်သော processing algorithm များ ကိုထောက်ပံ့ပေးပါသည်။

.. note::
   GPS များတွင် data များကို coordinate system အမျိုးမျိုးဖြင့် သိမ်းဆည်းထားနိင်ပါသည်။ GPX file တစ်ခုကို (GPS သို့မဟုတ် web site မှ) download ရယူပြီး QGIS ထဲသို့ ခေါ်ယူထည့်သွင်းသောအခါ GPX file ထဲတွင် သိမ်းဆည်းထားသော data များသည် WGS 84 (latitude/longitude) ဖြစ်နေရန်လိုအပ်ပါသည်။ QGIS သည် ထိုကဲ့သို့ဖြစ်မည်ဟု မျှော်လင့်ထားပြီး ၎င်းသည် အသုံးများသော (ပုံမှန်အသုံးပြုသော) GPX specification (သတ်မှတ်ချက်) ဖြစ်ပါသည်။ `GPX 1.1 Schema Documentation <https://www.topografix.com/GPX/1/1/>` တွင်ကြည့်ရှုပါ။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |addGpsLayer| image:: /static/common/mActionAddGpsLayer.png
   :width: 1.5em
.. |dataSourceManager| image:: /static/common/mActionDataSourceManager.png
   :width: 1.5em
