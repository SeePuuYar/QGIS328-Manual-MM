.. index:: Layout; 3D Map item
.. _layout_map3d_item:

The 3D Map Item (သုံးဘက်မြင်မြေပုံ Item)
=========================================

.. only:: html

   .. contents::
      :local:

3D Map (သုံးဘက်မြင်မြေပုံ) item အား :ref:`3D မြေပုံမြင်ကွင်း <label_3dmapview>` တစ်ခုကို ပြသရန်အသုံးပြုသည်။ |add3DMap| :guilabel:`Add 3D Map` ခလုတ်ကိုအသုံးပြု၍ :ref:`item များဖန်တီးခြင်းညွှန်ကြားချက်များ <create_layout_item>` အားလိုက်နာပြီး နောင်တွင်  :ref:`interact_layout_item` တွင်ဖော်ပြထားသည့်နည်းလမ်းအတိုင်း ကိုင်တွယ်နိုင်မည့် 3D Map item အသစ်တစ်ခုကိုထည့်သွင်းနိုင်ပါသည်။
 
Default အားဖြင့် 3D Map item အသစ်တစ်ခုသည် အလွတ်ဖြစ်သည်။ 3D မြင်ကွင်း၏ ဂုဏ်သတ္တိများကိုသတ်မှတ်နိုင်ပြီး ၎င်းကို :guilabel:`Item Properties` panel ထဲတွင် စိတ်ကြိုက်ပြင်ဆင်နိုင်မည်ဖြစ်ပါသည်။ ဤ feature တွင် :ref:`common ဂုဏ်သတ္တိများ <item_common_properties>` အပြင် အောက်ပါ လုပ်ဆောင်ချက်များပါရှိသည်(:numref:`figure_layout_3dmap_prop`) -
 

.. _figure_layout_3dmap_prop:

.. figure:: img/3dmap_properties.png
   :align: center
   :width: 20em

   3D မြေပုံ Item ဂုဏ်သတ္တိများ


.. _`layout_3dmap_scene_settings`:

Scene settings (မြင်ကွင်းချိန်ညှိမှုများ)
------------------------------------------

ပြသလိုသည့် သုံးဘက်မြင်မြေပုံမြင်ကွင်းကိုရွေးချယ်ရန် :guilabel:`Copy Settings from a 3D View...` ကိုနှိပ်ပါ။

3D မြေပုံမြင်ကွင်းအား ၎င်း၏လက်ရှိ configuration (layer များ ၊ မြေမျက်နှာသွင်ပြင်၊ အလင်းအမှောင်များ၊ ကင်မရာအနေအထား နှင့်ရှုထောင့်...) ဖြင့် ပုံဖော်ပြသမည်ဖြစ်သည်။


.. _`layout_3dmap_camera_pose`:

Camera pose (ကင်မရာ အနေအထား)
-----------------------------

* :guilabel:`Center X` သည် ကင်မရာချိန်ထားသည့် အမှတ်၏ X ကိုဩဒိနိတ်အားသတ်မှတ်ပေးသည်။
* :guilabel:`Center Y` သည် ကင်မရာချိန်ထားသည့် အမှတ်၏ Y ကိုဩဒိနိတ်အားသတ်မှတ်ပေးသည်။
* :guilabel:`Center Z` သည် ကင်မရာချိန်ထားသည့် အမှတ်၏ Z ကိုဩဒိနိတ်အားသတ်မှတ်ပေးသည်။
* :guilabel:`Distance` သည် ကင်မရာအလယ်ဗဟိုမှ ကင်မရာချိန်ထားသည့် အမှတ်ကြားအကွာအဝေးကိုသတ်မှတ်ပေးသည်။
* :guilabel:`Pitch` သည် X-ဝင်ရိုးတွင် ကင်မရာ၏ အလှည့်ကိုသတ်မှတ်ပေးသည် (ဒေါင်လိုက် အလှည့်)။ တန်ဖိုးများမှာ 0 မှ 360 (ဒီဂရီ) အထိဖြစ်သည်။ 0° - အပေါ်မှတန်းတန်းမြင်ရသည့်မြေမျက်နှာသွင်ပြင်၊ 90° - ရေပြင်ညီ (ဘေးဘက်မှ)၊ 180° - အောက်မှတန်းတန်းမြင်ရသည်၊ 270° - ရေပြင်ညီ၊ ပြောင်းပြန်၊ 360° - အပေါ်မှတန်းတန်းမြင်ရသည်။
* :guilabel:`Heading` သည် Y-ဝင်ရိုးတွင် ကင်မရာ၏ အလှည့်ကိုသတ်မှတ်ပေးသည် (ရေပြင်ညီအလှည့် - 0 မှ 360 ဒီဂရီ)။ 0°/360° - မြောက် ၊ 90° - အနောက်၊ 180° - တောင်၊ 270° - အရှေ့။

:guilabel:`Set from a 3D View...` pull-down menu ဖြင့် 3D မြင်ကွင်းတစ်ခု၏ parameter များပါဝင်သော item များကို ထုတ်နိုင်မည်ဖြစ်ပါသည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |add3DMap| image:: /static/common/mActionAdd3DMap.png
   :width: 1.5em
