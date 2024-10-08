.. index:: QGIS File Formats
.. _qgisfileformats_appendix:

Appendix C: QGIS File Formats (နောက်ဆက်တွဲ ဂ - QGIS file ပုံစံအမျိုးအစားများ)
------------------------------------------------------------------------------

.. index:: QGIS Project File
.. index:: QGS
.. index:: QGZ
.. index:: QGD
.. _qgisprojectfile:

QGS/QGZ - The QGIS Project File Format (QGS/QGZ - QGIS project file ပုံစံအမျိုးအစား)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**QGS** format သည် QGIS project များကို သိမ်းဆည်းခြင်းအတွက် XML format တစ်ခုဖြစ်ပါသည်။ **QGZ** format သည် QGS file တစ်ခုနှင့် QGD file တစ်ခုပါဝင်သော ချုံ့ထားသည့် (zip) မှတ်တမ်းတစ်ခု ဖြစ်ပါသည်။ **QGD** file သည် QGIS project အတွက် auxiliary (အရန်) data များပါဝင်သော ဆက်စပ် sqlite database ဖြစ်သည်။ Auxiliary (အရန်) data များမရှိပါက QGD file သည် အလွတ်ဖြစ်နေပါမည်။

QGIS file တစ်ခုတွင် QGIS project တစ်ခုသိမ်းဆည်းရန်အတွက် လိုအပ်သော အရာအားလုံးပါဝင်ပါသည်။ ၎င်းတို့မှာ-

* Project ခေါင်းစဉ်
* Project ၏ CRS - ရည်ညွှန်းကိုဩဒိနိတ်စနစ်
* Layer ဖွဲ့စည်းပုံ
* တစ်ခုနှင့်တစ်ခု ဆွဲကပ်ခြင်းဆိုင်ရာ setting များ
* ဆက်စပ်မှုများ
* မြေပုံမြင်ကွင်းအကျယ်အဝန်းနယ်
* Project model များ
* ရည်ညွှန်းချက်
* မြေပုံမြင်ကွင်းနေရာများ (2D နှင့် 3D)
* အရင်းအမြစ် dataset များနှင့်ချိတ်ဆက်နေသော layer များနှင့် အကျယ်အဝန်းနယ်၊ SRS ၊ ချိတ်ဆက်မှုများ ၊ style များ ၊ ပုံဖော်ပြသပေးသည့်အရာ၊ ရောစပ်ခြင်းနည်းလမ်း ၊ အလင်းပိတ်နှုန်း နှင့် နောက်ထပ်အရာများပါဝင်သော အခြား layer ဂုဏ်သတ္တိများ
* Project ၏ ဂုဏ်သတ္တိများ

အောက်ဖော်ပြပါ ပုံများသည် QGS file တစ်ခုထဲရှိ ထိပ်ပိုင်းအဆင့်ပူးတွဲများ (top level tag) နှင့် အကျယ်ဖြန့်ထားသော ``ProjectLayers`` tag ကို ပြသထားပါသည်။

.. _figure_qgs_toplevel:

.. figure:: img/qgstoplevel.png
   :align: center

   QGS file တစ်ခုအတွင်းရှိ top level tag များ

.. _figure_qgs_projectlayers:

.. figure:: img/qgsprojectlayers.png
   :align: center

   QGS file တစ်ခု၏ အကျယ်ဖြန့်ထားသော top level ProjectLayers tag


.. index:: QGIS Layer Definition File
.. index:: QLR
.. _qgislayerdefinitionfile:

QLR - The QGIS Layer Definition file (QLR - QGIS layer အဓိပ္ပါယ်သတ်မှတ်ချက် file)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Layer Definition file (QLR) သည် layer အတွက် QGIS style အချက်အလက်အပြင် layer ၏ data အရင်းအမြစ်ကို ညွှန်ပြပေးသည့်အရာ ပါဝင်သော XML file တစ်ခုဖြစ်ပါသည်။

ထို file ၏အသုံးပြုပုံမှာ ရိုးရှင်းပါသည်- data အရင်းအမြစ်တစ်ခုကို သက်ဆိုင်ရာ style အချက်အလက်များနှင့်အတူ ဖွင့်ရန်အတွက် file တစ်ခုရှိစေရန်ဖြစ်ပါသည်။ QLR file များသည် file များအလွယ်တကူပွင့်စေရန် ရှိနေပြီးသား data အရင်းအမြစ်များကို ဖုံးအုပ် (mask) ပေးနိုင်ပါသည်။

QLR အသုံးပြုမှုဥပမာ တစ်ခုမှာ MS SQL layer များကို ဖွင့်ရန်အတွက်ဖြစ်သည်။ MS SQL ချိတ်ဆက်မှု dialog ကို ဖွင့်ပြီး ချိတ်ဆက်ခြင်း၊ ရွေးချယ်ခြင်း၊ ထည့်သွင်းခြင်းနှင့် style ပြင်ဆင်ခြင်းများ ပြုလုပ်မည့်အစား .qlr file တစ်ခုကို ထည့်သွင်းလိုက်ရုံဖြင့် လိုအပ်သော style များအားလုံးပါဝင်သည့် မှန်ကန်သော MS SQL layer သို့ ညွှန်ပြပေးနိုင်ပါသည်။

အနာဂတ်တွင် .qlr file သည် တစ်ခုထက်ပိုသော layer များအတွက် အကိုးအကားကို ထိန်းသိမ်းပေးကောင်းပေးနိုင်ပါလိမ့်မည်။

.. _figure_qlrtop:

.. figure:: img/qlr.png
   :align: center
   
   QLR file တစ်ခု၏ top level tag များ


.. index:: QGIS Style File
.. index:: QML
.. _qgisstylefile:

QML - The QGIS Style File Format (QML - QGIS style file ပုံစံအမျိုးအစား)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

QML သည် layer style များသိမ်းဆည်းခြင်းအတွက် XML format တစ်ခုဖြစ်သည်။

QML file တစ်ခုတွင် QGIS မှကိုင်တွယ်လုပ်ဆောင်နိုင်သော feature ဂျီဩမေတြီများ ပုံဖော်ပြသခြင်းဆိုင်ရာ အချက်အလက်အားလုံးပါဝင်ပါသည်။ Feature ဂျီဩမေတြီများ ပုံဖော်ပြသခြင်းဆိုင်ရာများတွင် သင်္ကေတဆိုင်ရာသတ်မှတ်ချက်များ၊ အရွယ်အစားများနှင့် အလှည့်များ၊ အညွှန်းတပ်ခြင်း၊ အလင်းပိတ်နှုန်း၊ ရောစပ်ခြင်းနည်းလမ်း နှင့်အခြားသောအရာများ ပါဝင်ပါသည်။

အောက်ဖော်ပြပါ ပုံသည် QML file တစ်ခု၏ ထိပ်ပိုင်းအဆင့် (top level) tag များကို ပြသထားပါသည် (``renderer_v2`` နှင့် အကျယ်ဖြန့်ထားသော ၎င်း၏ ``symbol`` tag သာ)။

.. _figure_qml:

.. figure:: img/qml.png
   :align: center

   QML file တစ်ခု၏ ထိပ်ပိုင်းအဆင့် (top level) tag များ (၎င်း၏ symbol tag ဖြင့် renderer_v2 tag ကိုသာ အကျယ်ဖြန့်ထားပါသည်)