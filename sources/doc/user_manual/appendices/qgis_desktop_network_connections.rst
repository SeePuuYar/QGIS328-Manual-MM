************************************************************************************************************
Appendix E: QGIS Application Network Connections (နောက်ဆက်တွဲ င - QGIS Application ကွန်ရက် ချိတ်ဆက်မှုများ)
************************************************************************************************************

အောက်ပါစာရင်းသည် QGIS မှပြုလုပ်ထားသော ကြိုပြင်သတ်မှတ်ထားသော/အလိုအလျောက်ဖြစ်သော ကွန်ရက်ချိတ်ဆက်မှုများ စာရင်းဖြစ်ပါသည်။ အချို့ချိတ်ဆက်မှုများသည် စတင်လုပ်ဆောင်ရန် အသုံးပြုသူမှ လုပ်ဆောင်ချက် (action) များပြုလုပ်ပေးရန် လိုအပ်ပါသည်။ တခြားအရာများသည် အလိုအလျောက် လုပ်ဆောင်မည်ဖြစ်သည်။

.. list-table::
   :header-rows: 1
   :widths: auto

   * - အမည်
     - ရည်ရွယ်ချက်
     - UX mode
     - Server
     - Server သို့ ပေးပို့သော အချက်အလက်များ
     - Server တွင် သိမ်းဆည်းထားသော အချက်အလက်များ
   * - **qgis.org**
     -
     -
     -
     -
     -
   * - Python API help
     - PyQGIS documentation ကိုဖွင့်ရန်
     - အသုံးပြုသူမှ စတင်လုပ်ဆောင်ရသော
     - https://qgis.org/pyqgis/%1/search.html?q=%2
     - IP, QGIS version, OS
     - IP in server log
   * - **version.qgis.org**
     -
     -
     -
     -
     -
   * - New version check
     - QGIS version အသစ်များ ရရှိမှုကို အသုံးပြုသူအား အသိပေးရန်
     - အလိုအလျောက်ဖြစ်သော
     - https://version.qgis.org
     - IP, QGIS version, OS
     - IP in server log
   * - **feed.qgis.org**
     -
     -
     -
     -
     -
   * - QGIS Feed
     - QGIS သတင်းများကို ရယူပေးရန်
     - အလိုအလျောက်ဖြစ်သော
     - https://feed.qgis.org
     - IP, QGIS version, language code, last download timestamp, OS
     - IP in server log; QGIS version ၊ OS နှင့် IP များကိုစုစည်းပြီး စာရင်းအင်းအချက်အလက်များစုဆောင်းရန် အသုံးပြုသည်။
   * - **plugins.qgis.org**
     -
     -
     -
     -
     -
   * - Check for plugin updates
     - Plugin update များအကြောင်း အသုံးပြုသူအား အသိပေးရန်
     - အသုံးပြုသူမှ စတင်လုပ်ဆောင်ရသော/အလိုအလျောက်ဖြစ်သော (ပြင်ဆင်သတ်မှတ်နိုင်သည်)
     - https://plugins.qgis.org
     - IP, QGIS version, OS
     - IP in server log
   * - Plugins list
     - Plugin များစာရင်းကို ရယူပေးရန်
     - အသုံးပြုသူမှ စတင်လုပ်ဆောင်ရသော
     - https://plugins.qgis.org
     - IP, QGIS version, OS
     - IP in server log
   * - Plugin installation
     - Plugin package တစ်ခုကို download ရယူခြင်းနှင့်ထည့်သွင်းခြင်း
     - အသုံးပြုသူမှ စတင်လုပ်ဆောင်ရသော
     - https://plugins.qgis.org
     - IP, QGIS version, OS
     - Plugin download အရေအတွက် ရေတွက်ပေးသည့်အရာတွင် တစ်ခုတိုးစေသည်
   * - Styles
     - အသုံးပြုသူများမှ ပါဝင်ကူညီရေးဆွဲထားသော style များစာရင်း
     - အသုံးပြုသူမှ စတင်လုပ်ဆောင်ရသော
     - https://plugins.qgis.org/styles
     - IP, QGIS version, OS
     - Download အရေအတွက် တွက်ချက်ပေးသည့်အရာတွင် တစ်ခုတိုးစေသည်
   * - **3rd party**
     -
     -
     -
     -
     -
   * - Terrain data
     - ၃ ဘက်မြင် မြင်ကွင်းများအတွက် DEM တစ်ခုကို ထုတ်ပေးရန်
     - အသုံးပြုသူမှ စတင်လုပ်ဆောင်ရသော
     - https://s3.amazonaws.com/elevation-tiles-prod/terrarium/{z}/{x}/{y}.png
     - IP, QGIS version, OS
     - Amazon TOS တွင်ကြည့်ပါ
   * - Google Map Geocoder
     - Geocoding services
     - အသုံးပြုသူမှ စတင်လုပ်ဆောင်ရသော
     - https://maps.googleapis.com/maps/api/geocode/json
     - IP, QGIS version, OS
     - google maps API TOS တွင်ကြည့်ပါ
   * - Nominatim Geocoder
     - Geocoding services
     - အသုံးပြုသူမှ စတင်လုပ်ဆောင်ရသော
     - https://nominatim.qgis.org/ui/search.html
     - IP, QGIS version, OS
     -
   * - Geodetic grid
     - PROJ grid အသစ်တစ်ခုပေါင်းထည့်ရန်
     - အသုံးပြုသူမှ စတင်လုပ်ဆောင်ရသော
     - https://cdn.proj.org
     - IP, PROJ version
     - တစ်ရက်ကြာပြီးလျှင် ဝင်ရောက်သုံးစွဲသည့်မှတ်တမ်းများကို ထာဝရဖျက်ပစ်သည်

