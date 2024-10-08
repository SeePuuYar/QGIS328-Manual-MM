.. _gps_algorithms:

GPS (ကမ္ဘာလုံးဆိုင်ရာတည်နေရာပြစနစ်)
====================================

.. only:: html

   .. contents::
      :local:
      :depth: 1

.. _qgisconvertgpsdata:

Convert GPS data (GPS data များကိုပြောင်းလဲခြင်း)
--------------------------------------------------

GPS data file တစ်ခုကို format အမျိုးမျိုးမှ GPX စံ format အဖြစ်သို့ပြောင်းလဲရန် `GPSBabel tool <https://www.gpsbabel.org/index.html>`_ ကိုအသုံးပြုပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input file** (**ထည့်သွင်းအသုံးပြုသော file**)
     - ``INPUT``
     - [file]
     - ပြောင်းလဲရန် data များပါဝင်သော file
   * - **Format**
     - ``FORMAT``
     - [enumeration]
     - `ဤစာရင်း <https://www.gpsbabel.org/capabilities.html>`_ မှ ပြောင်းလဲမည့် file format 
   * - **Feature type** (**Feature အမျိုးအစား**)
     - ``FEATURE_TYPE``
     - [enumeration]

       Default: 0
     - ပြောင်းလဲမည့် data အမျိုးအစား

       * 0 --- Waypoints (အမှတ်များ)
       * 1 --- Routes (ခရီးစဉ်လမ်းကြောင်းများ)
       * 2 --- Tracks (ခြေရာခံလမ်းကြောင်းများ)

   * - **Output** (**ရလာဒ်များ**)
     - ``OUTPUT``
     - [vector: any]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Output GPX file ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output layer**
     - ``OUTPUT_LAYER``
     - [vector: any]
     - GPX standard format ဖြင့် data များပါဝင်သော output layer

Python code
............

**Algorithm ID**: ``native:convertgpsdata``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisconvertgpxfeaturetype:

Convert GPX feature type (GPX feature အမျိုးအစားကို ပြောင်းလဲခြင်း)
--------------------------------------------------------------------

GPX feature များကို အမျိုးအစားတစ်ခုမှ အခြားအမျိုးအစားသို့ပြောင်းလဲရန် (ဥပမာ- waypoint များအားလုံးကို route တစ်ခုအဖြစ်ပြောင်းလဲခြင်း) `GPSBabel tool <https://www.gpsbabel.org/index.html>`_ ကိုအသုံးပြုပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input file** (**ထည့်သွင်းအသုံးပြုသော file**)
     - ``INPUT``
     - [file]
     - ပြောင်းလဲရန် data များပါဝင်သော file
   * - **Conversion** (**ပြောင်းလဲခြင်း**)
     - ``CONVERSION``
     - [enumeration]

       Default: 0
     - အသုံးပြုမည့် ပြောင်းလဲခြင်း အမျိုးအစား

       * 0 --- Waypoints from a route (Route တစ်ခုမှ Waypoint များသို့)
       * 1 --- Waypoints from a track (Track တစ်ခုမှ Waypoint များသို့)
       * 2 --- Routes from waypoints (Waypoint များမှ Route များသို့)
       * 3 --- Tracks from waypoints (Waypoint များမှ Track များသို့)

   * - **Output** (**ရလာဒ်များ**)
     - ``OUTPUT``
     - [vector: point သို့မဟုတ် line]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Output file ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output**
     - ``OUTPUT``
     - [vector: any]
     - ပြောင်းလဲထားသော GPX feature များဖြင့် output layer

Python code
............

**Algorithm ID**: ``native:convertgpxfeaturetype``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisdownloadgpsdata:

Download GPS data from device (GPS ကိရိယာမှ GPS data များကို download ရယူခြင်း)
--------------------------------------------------------------------------------

GPS ကိရိယာမှ data များကို GPX စံ format ဖြင့် download ရယူရန် `GPSBabel tool <https://www.gpsbabel.org/index.html>`_ ကိုအသုံးပြုပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Device**
     - ``DEVICE``
     - [enumeration]

       Default:`Garmin serial`
     - Data ဖန်တီးရန်အသုံးပြုသော GPS ကိရိယာ ။ :ref:`GPS Settings <defining_new_device>` dialog ထဲတွင် အတိအလင်းဖော်ပြပေးထားရပါမည်။
   * - **Port** (**ချိတ်ဆက်မည့်နေရာ**)
     - ``PORT``
     - [enumeration]
     - GPS ကိရိယာ ချိတ်ဆက်မည့်နေရာ။ အသုံးပြုနိုင်သော port များသည် OS ပေါ်တွင် မူတည်ပါသည်။
   * - **Feature type** (**Feature အမျိုးအစား**)
     - ``FEATURE_TYPE``
     - [enumeration]

       Default: 0
     - ပြောင်းလဲရန် data အမျိုးအစား

       * 0 --- Waypoints
       * 1 --- Routes
       * 2 --- Tracks

   * - **Output** (**ရလာဒ်များ**)
     - ``OUTPUT``
     - [vector: any]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Output file ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output layer** (**ရလာဒ် layer**)
     - ``OUTPUT_LAYER``
     - [vector: any]
     - GPX စံ format ဖြင့် data များပါဝင်သော output layer

Python code
............

**Algorithm ID**: ``native:downloadgpsdata``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisuploadgpsdata:

Upload GPS data to device (GPS ကိရိယာထဲသို့ GPS data များထည့်ခြင်း)
--------------------------------------------------------------------

GPX စံ format မှ data များကို GPS ကိရိယာထဲသို့ထည့်သွင်းရန် `GPSBabel tool <https://www.gpsbabel.org/index.html>` ကိုအသုံးပြုပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input file** (**ထည့်သွင်းအသုံးပြုသော file**)
     - ``INPUT``
     - [file]
     - ထည့်သွင်းရန် data များပါဝင်သော :file:`.GPX` file
   * - **Device**
     - ``DEVICE``
     - [enumeration]

       Default:`Garmin serial`
     - Data ထည့်သွင်းလိုသော GPS ကိရိယာ။ :ref:`GPS Settings <defining_new_device>` dialog ထဲတွင် အတိအလင်းဖော်ပြထားရပါမည်။
   * - **Port** (**ချိတ်ဆက်မည့်နေရာ**)
     - ``PORT``
     - [enumeration]
     - GPS ကိရိယာ ချိတ်ဆက်မည့်နေရာ။ အသုံးပြုနိုင်သော port များသည် OS ပေါ်တွင် မူတည်ပါသည်။
   * - **Feature type** (**Feature အမျိုးအစား**)
     - ``FEATURE_TYPE``
     - [enumeration]

       Default: 0
     - ထည့်သွင်းမည့် data အမျိုးအစား

       * 0 --- Waypoints
       * 1 --- Routes
       * 2 --- Tracks

Outputs (ရလာဒ်များ)
....................

Output မရှိပါ။ လုပ်ဆောင်ပြီးသွားလျှင် data များကို ကိရိယာထဲသို့ထည့်သွင်းပြီးသား ဖြစ်သွားပါလိမ့်မည်။

Python code
............

**Algorithm ID**: ``native:uploadgpsdata``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**

