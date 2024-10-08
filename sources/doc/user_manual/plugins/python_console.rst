﻿.. index::
   single: Python


.. _console:

************************************************************************************
QGIS Python console (QGIS တွင် Python code များရေးသားရာ၌ အသုံးပြုသည့်နေရာ)
************************************************************************************


.. only:: html


   .. contents::
      :local:


ဤအခန်း၏ နောက်ပိုင်းတွင် တွေ့မြင်ရမည့်အတိုင်း QGIS ကို plugin တည်ဆောက်မှုပုံစံဖြင့် ဒီဇိုင်းရေးဆွဲထားပါသည်။ Plugin များကို ပထဝီဝင်ဆိုင်ရာ နယ်ပယ်တွင် ‌အလွန်လူသိများသော ဘာသာစကားဖြစ်သည့် Python ဖြင့် ရေးသားနိုင်ပါသည်။ 

QGIS သည် အသုံးပြုသူများကို ၎င်း၏ object များ (layer များ၊ feature သို့မဟုတ် အသုံးပြုသူမျက်နှာပြင်) နှင့် အပြန်အလှန်လုပ်ဆောင်နိုင်စေရန် Python API တစ်ခုကို ဆောင်ကျဉ်းပေးပါသည်။ (Code နမူနာများအတွက် :ref:`PyQGIS Developer Cookbook <PyQGIS-Developer-Cookbook>` တွင် ကြည့်ရှုလေ့လာနိုင်ပါသည်။) QGIS တွင် Python console တစ်ခုလည်း ရှိပါသည်။ 

QGIS Python Console သည် python ညွှန်ကြားချက်များကို ဆောင်ရွက်ရန် အပြန်အလှန်လုပ်ဆောင်နိုင်သော နေရာတစ်ခုဖြစ်ပါသည်။ ၎င်းတွင် python script များကို ပြင်ဆင်တည်းဖြတ်ခြင်းနှင့် သိမ်းဆည်းခြင်းများ လုပ်ဆောင်နိုင်သော python ဖိုင်ပြင်ဆင်တည်းဖြတ်ပေးသည့်အရာလည်း ရှိပါသည်။ Console နှင့် editor (ပြင်ဆင်တည်းဖြတ်မှုပေးသည့်အရာ) နှစ်ခုလုံးသည် PyQScintilla2 package ပေါ်တွင် အခြေခံထားပါသည်။ Console ကို ဖွင့်လှစ်ရန် :menuselection:`Plugins --> Python Console` သို့ ဝင်ရောက်ပါ (:kbd:`Ctrl+Alt+P` ကိုအသုံးပြု၍ ဖွင့်နိုင်ပါသည်)။


.. _interactive_console:


The Interactive Console (အပြန်အလှန် လုပ်ဆောင်နိုင်သော Console)
===============================================================

အပြန်အလှန် လုပ်ဆောင်နိုင်သော Console တွင် လုပ်ဆောင်ချက်ဘား (toolbar)၊ input ထည့်သွင်းနိုင်သည့်နေရာနှင့် ရလာဒ်ထုတ်ပေးသည့်နေရာတို့ ပါဝင်ပါသည်။

Toolbar
--------

Toolbar တွင် အောက်ပါ tool များပါရှိပါသည်- 

* |clearConsole| :sup:`Clear Console` (Console အား ရှင်းလင်းခြင်း) သည် ရလာဒ်ဧရိယာကို ရှင်းလင်းရန် ဖြစ်ပါသည်၊ 
* |runConsole| :sup:`Run Command` (Command ကိုလုပ်ဆောင်ခြင်း) ကို input ထည့်သွင်းသည့်နေရာတွင် တွေ့နိုင်ပြီး ကီးဘုတ်တွင် :kbd:`Enter` ကိုနှိပ်ခြင်းနှင့်အတူတူပင်ဖြစ်ပါသည်၊
* |showEditorConsole| :sup:`Show Editor` (ပြင်ဆင်တည်းဖြတ်ပေးသည့်အရာကိုပြသခြင်း) သည် :ref:`console_editor` ၏ မြင်ကွင်းကို အဖွင့်အပိတ်ပြုလုပ်နိုင်ပါသည်၊
* |options| :sup:`Options...` (ရွေးချယ်စရာများ) သည် console ၏ ဂုဏ်သတ္တိများကို ပြင်ဆင်သတ်မှတ်ရန် dialog တစ်ခုကို ပွင့်လာစေပါသည် (:ref:`console_options` ကိုကြည့်ပါ)၊ 
* |helpContents| :sup:`Help...` (အကူအညီ) တွင် လက်ရှိမှတ်တမ်းမှတ်ရာများကို ရှာဖွေနိုင်ပါသည်။ 


Console
--------

Console ၏ အဓိကအင်္ဂါရပ်များမှာ-

* အောက်ပါ API များအတွက် ကုဒ်ပြီးမြောက်စေခြင်း၊ ဝါကျဖွဲ့ပုံ (syntax) အား ထင်ရှားအောင်ပြသခြင်းနှင့်အကြံပြုချက်များ တို့ဖြစ်သည်-

  * Python
  * PyQGIS
  * PyQt5
  * QScintilla2
  * osgeo-gdal-ogr

* :ref:`console_options` ကိုဖွင့်ထားပါက အလိုအလျောက် ပြီးမြောက်ခြင်း (auto-completion) စာရင်းကို ကြည့်ရှုရန် :kbd:`Ctrl+Alt+Space` ကို နှိပ်ပါ။
* Input ထည့်သွင်းသည့် နေရာတွင် စာရိုက်၍ :kbd:`Enter` သို့မဟုတ် :guilabel:`Run Command` ကို နှိပ်၍ code အပိုင်းအစများကို စေခိုင်းလုပ်ဆောင် (execute) ပါ-  
* Contextual menu (အကြောင်းအရာ မီနူး) မှ :guilabel:`Enter Selected` ကို အသုံးပြုခြင်း သို့မဟုတ် :kbd:`Ctrl+E` ကို နှိပ်ခြင်းဖြင့် ရလာဒ်ထုတ်ပေးသော နေရာမှ code အပိုင်းအစများကို စေခိုင်းလုပ်ဆောင်ပါ၊
* Input ထည့်သွင်းသည့်နေရာတွင် :kbd:`Up` (အပေါ်) နှင့် :kbd:`Down` (အောက်) မြှားများကိုအသုံးပြု၍ command မှတ်တမ်းကို ရှာဖွေပြီးနောက် အလိုရှိသော command ကို စေခိုင်းလုပ်ဆောင်ပါ။
* Command မှတ်တမ်းကို ကြည့်ရှုရန် :kbd:`Ctrl+Shift+Space` ကို နှိပ်ပြီး row (အတန်း) တစ်ခုကို click နှစ်ချက်နှိပ်လိုက်ပါက ထို command ကို စေခိုင်းလုပ်ဆောင်ပါလိမ့်မည်။ :guilabel:`Command History` dialog ကို input ထည့်သွင်းသည့် နေရာ၏ context menu (အကြောင်းအရာ menu) မှလည်း ဝင်ရောက်နိုင်ပါသည်။
* Command မှတ်တမ်းကို သိမ်းဆည်းပြီးနောက် ရှင်းလင်းပါ။ ထိုမှတ်တမ်းကို လက်ရှိအသုံးပြုနေသော :ref:`user profile (အသုံးပြုသူလမ်းကြောင်း) <user_profiles>` folder အောက်ရှိ :file:`console_history.txt` ဖိုင်ထဲတွင် သိမ်းဆည်းသွားမည်ဖြစ်ပါသည်၊ 

* ``_api``  ဟု စာရိုက်၍ :api:`QGIS C++ API <>` မှတ်တမ်းမှတ်ရာများကိုဖွင့်နိုင်သည်။
* ``_pyqgis`` ဟု စာရိုက်၍ :pyqgis:`QGIS Python API <>` မှတ်တမ်းမှတ်ရာကို ဖွင့်နိုင်သည်။
* ``_cookbook`` ဟု စာရိုက်၍ :ref:`PyQGIS Cookbook <PyQGIS-Developer-Cookbook>` ကိုဖွင့်နိုင်သည်။

.. tip:: **ရလာဒ် panel မှ လုပ်ဆောင်ပြီးသား command များကို ပြန်လည်အသုံးပြုခြင်း**

 ရလာဒ် panel မှ code အချို့ကို ရွေးချယ်၍ :kbd:`Ctrl+E` ကို နှိပ်ခြင်းဖြင့် code အပိုင်းအစများကို စေခိုင်းလုပ်ဆောင်နိုင်ပါသည်။ အကယ်၍ ရွေးချယ်ထားသော စာသားတွင် interpreter prompt (ကြားခံလမ်းညွှန်ချက်) (``>>>`` ၊ ``...``) များပါဝင်နေပါကလည်း ပြဿနာတစ်စုံတစ်ရာမရှိပေ။


.. _figure_python_console:

.. figure:: img/python_console.png
   :align: center

   Python Console

.. _console_editor:


The Code Editor (Code ပြင်ဆင်တည်းဖြတ်ပေးသည့်အရာ)
=================================================

Editor widget ကို ဖွင့်ရန် |showEditorConsole| :sup:`Show Editor` ခလုတ်ကို အသုံးပြုပါ။ ၎င်းသည် Python ဖိုင်များကို ပြင်ဆင်တည်းဖြတ်ခြင်းနှင့် သိမ်းဆည်းခြင်းများကို လုပ်ဆောင်နိုင်ပြီး မိမိ၏ code များကို ကိုင်တွယ်စီမံရန် အဆင်မြင့်လုပ်ဆောင်ချက်များကိုလည်း ပေးစွမ်းနိုင်ပါသည် (code များကိုမှတ်ချက်ပေးခြင်း နှင့် မှတ်ချက်ပြန်ဖျက်ခြင်း၊ ဝါကျဖွဲ့ပုံ (syntax) ကိုစစ်ဆေးခြင်း၊ GitHub မှတဆင့် code မျှဝေခြင်းနှင့် အခြားသောအရာများ)။ အဓိကအင်္ဂါရပ်များမှာ-

* အောက်ပါ API များအတွက် code ပြီးမြောက်စေခြင်း၊ syntax များနှင့်အကြံပြုချက်များအား ထင်ရှားအောင်ပြသခြင်း တို့ဖြစ်သည်-


  * Python
  * PyQGIS
  * PyQt5
  * QScintilla2
  * osgeo-gdal-ogr

* အလိုအလျောက်ပြီးမြောက်ခြင်း (auto-completion) စာရင်းကို ကြည့်ရှုရန် :kbd:`Ctrl+Space` ကိုနှိပ်ပါ။
* :ref:`GitHub <console_options>` မှ တဆင့် code များကို မျှဝေခြင်း။ 
* :kbd:`Ctrl+4` ဖြင့် syntax စစ်ဆေးခြင်း
* ရှာဖွေမှုဘား (Default ကွန်ပျူတာ ဖြတ်လမ်းနည်း ဖြစ်သော :kbd:`Ctrl+F` ဖြင့် ဖွင့်ပါ)-

  * နောက်ထပ်/ ယခင်က အရာများကို ရှာဖွေရန် default ကွန်ပျူတာဖြတ်လမ်းနည်းဖြစ်သော (:kbd:`Ctrl+G` နှင့် :kbd:`Shift+Ctrl+G`) တို့ကို အသုံးပြုပါ၊ 
  * ရှာဖွေမှု box တွင် စာရိုက်ထည့်သည့်အခါ ပထမဆုံး ကိုက်ညီမှုကို အလိုအလျောက် ရှာဖွေပါ၊ 
  * ရှာဖွေမှုကို ဖွင့်သောအခါ ရွေးချယ်မှုတွင် အစရှာဖွေမှုစာလုံးကို သတ်မှတ်ပါ၊
  * ရှာဖွေမှုဘားကို ပိတ်ရန် :kbd:`Esc` ကို နှိပ်ပါ။ 

* Object inspector- အတန်းအစား (class) နှင့် လုပ်ဆောင်ချက် (function) ကို ရှာဖွေနိုင်သည့်အရာ၊ 
* Object အဓိပ္ပါယ်သတ်မှတ်ချက်ကို သိရှိရန် မောက်စ်ဖြင့်တစ်ချက်နှိပ်ပါ (Object inspector မှ)၊
* Contextual menu (အကြောင်းအရာ menu) ထဲရှိ |runConsole| :guilabel:`Run Selected` command ဖြင့် code အပိုင်းအစများကို စေခိုင်းလုပ်ဆောင်ပါ၊ 
* |start| :guilabel:`Run Script` command ဖြင့် script တစ်ခုလုံးကို စေခိုင်းလုပ်ဆောင်ပါ (၎င်းသည် :file:`.pyc` extension ဖြင့် byte-compiled ဖိုင် (byte များစုစည်းထားသည့်ဖိုင်) တစ်ခုကို ဖန်တီးပေးပါသည်)

.. note::

 :guilabel:`Code Editor` မှ script တစိတ်တပိုင်းကို ဖြစ်စေ၊ script အားလုံးကိုဖြစ်စေ လုပ်ဆောင်ပါက Console ရလာဒ်ဧရိယာတွင် ရလာဒ်များကို ထုတ်ပေးမည်ဖြစ်ပါသည်။ 

.. _figure_python_console_editor:

.. figure:: img/python_console_editor.png
   :align: center

   Python Console editor

.. tip:: **ရွေးချယ်စရာများကို သိမ်းဆည်းခြင်း**

   Console ရှိ widget များ၏ အခြေအနေကို သိမ်းဆည်းရန် Python Console ကို close button (ပိတ်သည့် ခလုတ်) မှ ပိတ်ရပါမည်။ ထိုသို့ပြုလုပ်ခြင်းသည် ဂျီဩမေတြီကို သိမ်းဆည်းပေးနိုင်ပြီး နောက်တစ်ကြိမ်ပြန်လည်စတင်ရာတွင် ၎င်းတို့ကို ပြန်လည်ရယူနိုင်ပါသည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.


.. |clearConsole| image:: /static/common/iconClearConsole.png
   :width: 1.5em
.. |helpContents| image:: /static/common/mActionHelpContents.png
   :width: 1.5em
.. |options| image:: /static/common/mActionOptions.png
   :width: 1em
.. |runConsole| image:: /static/common/iconRunConsole.png
   :width: 1.5em
.. |showEditorConsole| image:: /static/common/iconShowEditorConsole.png
   :width: 1.5em
.. |start| image:: /static/common/mActionStart.png
   :width: 1.5em