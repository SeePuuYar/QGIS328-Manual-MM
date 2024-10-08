.. _`3dsymbols`:

*************************************************
Creating 3D Symbols (3D သင်္ကေတများ ဖန်တီးခြင်း)
*************************************************

.. only:: html

   .. contents::
      :local:

:guilabel:`Style Manager` သည် :ref:`3D map view <label_3dmapview>` တွင် ပုံဖော်ရန် ဂျီဩမေတြီ အမျိုးအစားတိုင်းအတွက် 3D သင်္ကေတများကို ဖန်တီးသိမ်းဆည်းရန် ကူညီပေးသည်။

အခြား ဂျီဩမေတြီ အမျိုးအစားများဖန်တီးရန် |3d| :guilabel:`3D Symbols` tab ကိုဖွင့်ပြီး |symbologyAdd| ကို နှိပ်ပါ-

* :ref:`3D point symbols <3d_pointlayers>` (3D Point သင်္ကေတ)
* :ref:`3D line symbols <3d_linelayers>` (3D Line သင်္ကေတ)
* :ref:`3D polygon symbols <3d_polygonlayers>` (3D Polygon သင်္ကေတ)

.. _`3d_pointlayers`:

Point Layers (Point အလွှာများ)
===============================

.. _figure_3d_point_symbol:

.. figure:: img/3d_point_symbol.png
   :align: center
   
   3D Point Symbol တစ်ခု၏ ဂုဏ်သတ္တိများ
   
* Point symbol များအတွက် အသုံးပြုရန် မတူညီသော 3D :guilabel:`Shape` အမျိုးအစားများကို သတ်မှတ်နိုင်ပါသည်။ ထို point symbol များကို အဓိကအားဖြင့် project ၏ CRS မှ ရည်ညွှန်းထားသည့် အတိုင်းအတာယူနစ်အသုံးပြုထားသော ၎င်းတို့၏ dimension (ရှုထောင့်) များဖြင့် သတ်မှတ်ပါသည်။ ရရှိနိုင်သည့်အမျိုးအစားများမှာ-

  * :guilabel:`Sphere` ကို :guilabel:`Radius` တစ်ခုဖြင့် သတ်မှတ်သည်။
  * :guilabel:`Cylinder` ကို :guilabel:`Radius` နှင့်  :guilabel:`Length` ဖြင့် ပေါင်းစပ်သတ်မှတ်သည်။
  * :guilabel:`Cube` ကို :guilabel:`Size` တစ်ခုဖြင့် သတ်မှတ်သည်။
  * :guilabel:`Cone` ကို :guilabel:`Top radius` ၊ :guilabel:`Bottom radius` နှင့် :guilabel:`Length` များဖြင့် ပေါင်းစပ်သတ်မှတ်သည်။
  * :guilabel:`Plane` ကို :guilabel:`Size` တစ်ခုဖြင့် သတ်မှတ်သည်။
  * :guilabel:`Torus` ကို :guilabel:`Radius` နှင့် :guilabel:`Minor radius` ဖြင့် ပေါင်းစပ်သတ်မှတ်သည်။
  * :guilabel:`3D Model` 3D ပုံစံအသုံပြုထားသောဖိုင်တစ်ခုတွင် wavefront :file:`.obj` ၊ :file:`.glTF` နှင့် :file:`.fbx` စသည့်  format သုံးမျိုးဖြင့် ပံ့ပိုးထားသည်။ ထို 3D ပုံစံများသည် ကွန်ပျူတာပေါ်တွင်ရှိသော ဖိုင်တစ်ခု၊ remote URL တစ်ခု သို့မဟုတ် :ref:`project ထဲတွင် ထည့်သွင်းမြှုပ်နှံထားသည့် <embedded_file_selector>` ဖြစ်နိုင်ပါသည်။ လူအများပူးပေါင်းပါဝင် ဖန်တီးထားသော 3D model များကို https://plugins.qgis.org/wavefronts ရှိ QGIS Hub တွင် မျှဝေထားပါသည်။
  * :guilabel:`Billboard` ကို :guilabel:`Billboard height` နှင့် :guilabel:`Billboard symbol` ဖြင့် (များသောအားဖြင့် :ref:`marker symbol <vector_marker_symbols>` ကိုအခြေခံ၍) သတ်မှတ်ထားပါသည်။ Symbol သည် တည်ငြိမ်သောအရွယ်အစားရှိပြီး 3D point cloud များကို ကြည့်ရှုရာတွင် အဆင်ပြေစေပါသည်။
* :guilabel:`Altitude clamping` ကို :guilabel:`Absolute` နှင့် :guilabel:`Relative` သို့မဟုတ် :guilabel:`Terrain` ဟု သတ်မှတ်နိုင်သည်။ 3D vector များ၏ အမြင့်တန်ဖိုးများသည် သုည (0) မှ ပကတိအတိုင်းအတာအဖြစ် ထောက်ပံ့ပေးသည့်အခါ :guilabel:`absolute` setting ကို အသုံးပြုနိုင်ပါသည်။ :guilabel:`Relative` နှင့် :guilabel:`Terrain` သည် အောက်ခံမြေမျက်နှာသွင်ပြင်အမြင့်ထဲတွင် ပေးထားသော အမြင့်တန်ဖိုးများ ပေါင်းထည့်ခြင်းဖြစ်သည်။
* :ref:`Shading (အမှောင်ရိပ်ထည့်ခြင်း) <shading_texture>` ဂုဏ်သတ္တိများကို သတ်မှတ်နိုင်ပါသည်။
* :guilabel:`Transformations` frame အောက်တွင် symbol များကို affine transformation (ပုံသဏ္ဍာန်မပျက် အသွင်ပြောင်းခြင်း) အသုံးပြုနိုင်ပါသည်-

  * :guilabel:`Translation` သည် Object များကို x ၊ y နှင့် z ဝင်ရိုးတွင် ရွှေ့ရန်ဖြစ်သည်။
  * :guilabel:`Scale` သည် 3D ပုံသဏ္ဍာန်များကို အရွယ်အစားပြောင်းရန်ဖြစ်သည်။
  * :guilabel:`Rotation` သည် x ၊ y နှင့် z ဝင်ရိုးကို လှည့်ရန်ဖြစ်သည်။


.. _`3d_linelayers`:

Line Layers (Line အလွှာများ)
=============================

.. _figure_3d_line_symbol:

.. figure:: img/3d_line_symbol.png
   :align: center

   3D Line symbol တစ်ခု၏ ဂုဏ်သတ္တိများ

* :guilabel:`Width` နှင့် :guilabel:`Height` setting အောက်တွင် vector line များ၏ :guilabel:`Extrusion` ကို သတ်မှတ်နိုင်သည်။ ထို vector lines များတွင် Z တန်ဖိုးများမရှိပါက 3D volumes setting ဖြင့်သတ်မှတ်နိုင်သည်။
* 3D line များတွင် raster elevation data သို့မဟုတ် အခြားသော 3D vector များ ပါဝင်ပါက အောက်ခံမြေမျက်နှာသွင်ပြင်နှင့် ဆက်စပ်နေသည့်  3D line များ၏ တည်နေရာကို :guilabel:`Altitude clamping` ဖြင့် သတ်မှတ်နိုင်သည်။
* :guilabel:`Altitude binding` သည် feature နှင့် မြေမျက်နှာသွင်ပြင် မည်သို့ချိတ်ဆက်နေသည်ကို သတ်မှတ်ပေးပါသည်။ ထိုသို့ feature နှင့် မြေမျက်နှာပြင်ချိတ်ဆက်ရာတွင် feature ၏  :guilabel:`Vertex` တိုင်းဖြင့် ချိတ်ဆက်ခြင်း ပြုလုပ်နိုင်သလို :guilabel:`Centroid` မှလည်း ချိတ်ဆက်နိုင်ပါသည်။
* |checkbox|:guilabel:`Render as simple 3D lines` သည် ရိုးရှင်းသော 3D lines များအဖြစ် ပုံဖော်ပေးပါသည်။
* :ref:`Shading (အမှောင်ရိပ်ထည့်ခြင်း) <shading_texture>` ဂုဏ်သတ္တိများကို သတ်မှတ်နိုင်သည်။


.. _`3d_polygonlayers`:

Polygon Layers (Polygon အလွှာများ)
===================================

.. _figure_3d_polygon_symbol:

.. figure:: img/3d_polygon_symbol.png
   :align: center
   
   3D Polygon symbol တစ်ခု၏ ဂုဏ်သတ္တိများ

* အခြား geometry အမျိုးအစားများဖန်တီးရန် :guilabel:`Height` ကို CRS ယူနစ်များတွင် သတ်မှတ်နိုင်သည်။ အသုံးပြုသူမှ ဖန်တီးထားသော ဖော်ပြချက်တန်ဖိုးတစ်ခု၊ 
  ကိန်းရှင်တန်ဖိုးတစ်ခု သို့မဟုတ် attribute table ၏ ပထဝီဆိုင်ရာအချက်အလက်များ ပြန်လည်ထည့်သွင်းရန် |dataDefine| buttom ကိုအသုံးပြုနိုင်ပါသည်။

* :guilabel:`Extrusion` သည် ပျောက်နေသည့် Z တန်ဖိုးများအတွက် ဖြစ်နိုင်ပါသည်။ Polygon တစ်ခုချင်းစီတွင် မတူညီသော result များ ရရှိရန်နှင့် 
  vector layer ၏ တန်ဖိုးများကို အသုံးပြုရန်အလို့ဌာ extrusion (ထုထည်ဖော်ခြင်း) အတွက် |dataDefine| buttom ကို အသုံးပြုနိုင်ပါသည်။

  .. figure:: img/3d_extrusion.png
     :align: center

     သတ်မှတ် data အသုံးပြုထားသည့် extrusion

* :guilabel:`Altitude clamping` နှင့် :guilabel:`Altitude binding` တို့ကို အထက်တွင်ရှင်းပြထားသည့်အတိုင်းသတ်မှတ်နိုင်သည်။
* :guilabel:`Culling mode` ကို symbol အတွက်အသုံးပြုရာတွင်-

  * :guilabel:`No Culling` သည် polygonZ/multipatch data များ၏ vertex များသည် အစဥ်အလိုက် တသမတ်တည်း မရှိသောအခါ 
    (ဥပမာ - နာရီလက်တံအတိုင်း သို့မဟုတ် နာရီလက်တံပြောင်းပြန်အတိုင်း) ပျောက်နေပုံရသော မျက်နှာပြင်များကို ရှောင်ရှားရန် ကူညီပေးနိုင်ပါသည်။
  * :guilabel:`Front` (အရှေ့ဘက်)
  * သို့မဟုတ် :guilabel:`Back` (အနောက်ဘက်)
* :guilabel:`Rendered facade` သည်  မျက်နှာပြင်များကို ပြသရန် ဆုံးဖြတ်သည်။ ဖြစ်နိုင်ချေတန်ဖိုးများမှာ 
  :guilabel:`No facades`၊ :guilabel:`Walls`၊ :guilabel:`Roofs` သို့မဟုတ် :guilabel:`Walls and roofs` တို့ဖြစ်သည်။
* |checkbox| :guilabel:`Add back faces` သည် တြိဂံတစ်ခုစီအတွက် vertex data အရေအတွက် တိုးလာစေခြင်းဖြင့်
  မှန်ကန်သောပုံမှန်ပုံစံများဖြင့် ရှေ့နှင့်နောက်မျက်နှာနှစ်ခုလုံးကို ဖန်တီးသည်။ Shading ပြဿနာများကို ဖြေရှင်းရန် ထို option ကို အသုံးပြုနိုင်ပါသည်။
  (ဥပမာ - vertex များ အစဥ်အလိုက် တသမတ်တည်း မရှိသည့် data များကြောင့်)
* |checkbox| :guilabel:`Invert normals (experimental)` သည်
  နာရီလက်တံအတိုင်း/နာရီလက်တံပြောင်းပြန်အတိုင်း vertex အစဥ်လိုက်ပြင်ဆင်ရန်အတွက် အသုံးဝင်ပါသည်။
* :ref:`Shading <shading_texture>` ဂုဏ်သတ္တိများကို သတ်မှတ်နိုင်သည်။
* Symbol များ၏ |checkbox| :guilabel:`Edges` ကိုပြသနိုင်ပြီး :guilabel:`Width` နှင့် :guilabel:`Color` တို့ကို သတ်မှတ်ပေးနိုင်ပါသည်။

.. hint:: **3D data များကို အကောင်းဆုံးပုံဖော်နိုင်ရန်အတွက် ပေါင်းစပ်မှုများ**
 
 :guilabel:`Culling mode`၊ :guilabel:`Add back faces` နှင့် :guilabel:`Invert normals` များသည် မှားနေသော 3D ဒေတာများကို အမှန်ပြင်ရန် ဖြစ်သည်။ ပုံမှန်အားဖြင့် data အချို့ကို တင်လိုက်သည့်အခါ ``culling mode=back`` နှင့် ``add back faces=disabled`` ကို ဦးစွာကြိုးစားသည်မှာ အကောင်းဆုံးဖြစ်သည်။ ၎င်းသည် အထိရောက်ဆုံးဖြစ်သည်။ ပုံဖော်ခြင်းသည် မှန်ကန်စွာမပြသပါက ``add back faces=enabled`` လုပ်ထားပြီး ``culling mode=no culling`` အဖြစ် ဆက်ထားပါ။ အခြားပေါင်းစပ်မှုများသည် ပိုမိုအဆင့်မြင့်ပြီး input dataset မည်သို့ရောနှောထားသည်ကိုအခြေခံထားသည့် အချို့သောအခြေအနေများတွင်သာ အသုံးဝင်ပါသည်။

.. _shading_texture:

Shading the texture (မျက်နှာပြင်အကြမ်း/အချော ကို အရိပ်ထည့်ခြင်း)
=================================================================

Shading လုပ်ခြင်းဖြင့် အလင်းရောင်ကြောင့် ဖုံးကွယ်နေသော object ၏ 3D အသေးစိတ်ကို ဖော်ထုတ်ပြသရန် ကူညီပေးနိုင်သည်။ 
အခြေခံအားဖြင့် feature များကို ပုံဖော်ကြည့်ရှုရန် သင့်လျော်သော scene lighting များ ချမှတ်ခြင်းနှင့်ပတ်သက်ပြီး စိုးရိမ်စရာ မလိုသောကြောင့် လုပ်ကိုင်ရလွယ်ကူပါသည်။

QGIS တွင် အမျိုးမျိုးသော Shading နည်းပညာများကို အသုံးပြုထားပြီး ၎င်းတို့၏ ရရှိနိုင်မှုမှာ symbol ၏ ဂျီဩမေတြီ အမျိုးအစားပေါ် မူတည်ပါသည်-

* :guilabel:`Realistic (Phong)` သည် ကြမ်းတမ်းသောမျက်နှာပြင်များ၏ ရောင်ပြန်ဟပ်မှု :guilabel:`Diffuse` နှင့် 
  တောက်ပသောမျက်နှာပြင်များ၏ :guilabel:`Specular` ရောင်ပြန်ဟပ်မှု (:guilabel:`Shininess`) တို့ကို ပေါင်းစပ်ကာ မျက်နှာပြင်တစ်ခု၏ အလင်းရောင်ပြန်ဟပ်မှုကို ဖော်ပြပေးပါသည်။
  မြင်ကွင်းတစ်ခုလုံးတွင် ပြန့်ကျဲနေသော အလင်းအနည်းငယ်ကို ထည့်သွင်းစဉ်းစားနိုင်ရန် :guilabel:`Ambient` option လည်းပါဝင်သည်။
  3D တွင် တစ်စိတ်တစ်ပိုင်း ဖောက်ထွင်းမြင်ရသော object များကို ပုံဖော်ရန် :guilabel:`Opacity` slider ကိုသုံးပါ။
  https://en.wikipedia.org/wiki/Phong_reflection_model#Description တွင် ပိုမိုဖတ်ရှုနိုင်ပါသည်။
* :guilabel:`Realistic Textured (Phong)` သည် image တစ်ခုကို :guilabel:`Diffuse Texture` အဖြစ်အသုံးပြုသည်မှလွဲ၍ :guilabel:`Realistic (Phong)` နှင့် အတူတူပင်ဖြစ်ပါသည်။
  Image သည် ကွန်ပျူတာပေါ်တွင်ရှိသော ဖိုင်တစ်ခု၊ remote URL တစ်ခု သို့မဟုတ်  :ref:`project ထဲတွင် ထည့်သွင်းမြှုပ်နှံထားသည့် <embedded_file_selector>` အဖြစ် ဖြစ်နိုင်ပါသည်။  :guilabel:`Texture scale` နှင့် :guilabel:`Texture rotation` လိုအပ်ပါသည်။ 3D တွင် တစ်စိတ်တစ်ပိုင်း ဖောက်ထွင်းမြင်ရသော object များကို ပုံဖော်ရန် :guilabel:`Opacity` slider ကိုသုံးပါ။
* :guilabel:`CAD (Gooch)` သည် အနားသတ်မျဥ်းများနှင့် highlight များကို အမြင်အရထင်ရှားမှု ရှိနေစေရန် mid-tones များတွင်သာ shading ပြုလုပ်ရသော နည်းပညာဖြစ်ပါသည်။
  :guilabel:`Diffuse`၊ :guilabel:`Specular`၊ :guilabel:`Shininess` option များနှင့်အတူ 
  :guilabel:`Warm` color  (အလင်းကို မျက်နှာမူနေသောမျက်နှာပြင်များအတွက်) နှင့် 
  :guilabel:`Cool` color (အဝေးကို မျက်နှာမူထားသော မျက်နှာပြင်များအတွက်) လုပ်ဆောင်ပေးရန်လိုအပ်ပါသည်။
  ထို့အပြင် diffuse color ဖြင့် warm color နှင့် cold color များတွင် ဆက်စပ်ပါဝင်မှုများကို :guilabel:`Alpha` နှင့် :guilabel:`Beta` ဂုဏ်သတ္တိများ အသီးသီးဖြင့် ထိန်းချုပ်ထားပါသည်။
  https://en.wikipedia.org/wiki/Gooch_shading ကိုလည်း ကြည့်ရှုပါ။
* 3D models ပုံသဏ္ဍာန် ဖြင့် :guilabel:`Embedded Textures`


Application example (အသုံးချမှုဥပမာ)
=====================================

အထက်တွင် ရှင်းလင်းဖော်ပြထားသော setting များကို စေ့စပ်သေချာစွာနားလည်စေရန် https://app.merginmaps.com/projects/saber/luxembourg/tree တွင် ကြည့်ရှုနိုင်ပါသည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |3d| image:: /static/common/3d.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |dataDefine| image:: /static/common/mIconDataDefine.png
   :width: 1.5em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
