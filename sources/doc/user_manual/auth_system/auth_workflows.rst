.. _authentication_workflow:

User Authentication Workflows (အသုံးပြုသူ စစ်မှန်ကြောင်းအသိအမှတ်ပြုခြင်း လုပ်ငန်းစဉ်များ)
==========================================================================================

.. only:: html

   .. contents::
      :local:

.. _figure_authusage:

.. figure:: img/auth-user-usage.png
   :align: center

   ယေဘုယျ အသုံးပြုသူ လုပ်ငန်းစဉ်

HTTP(S) authentication (HTTP(S) စစ်မှန်ကြောင်းအသိအမှတ်ပြုခြင်း)
----------------------------------------------------------------

အရင်းအမြစ်များနှင့် ချိတ်ဆက်မှုအတွက် အသုံးအများဆုံးနည်းလမ်းများထဲမှ တစ်ခုမှာ web mapping servers များကဲ့သို့ HTTP(S) မှတစ်ဆင့်သွားရခြင်း ဖြစ်ပြီး အများအားဖြင့် ထိုချိတ်ဆက်မှုအမျိုးအစားများအတွက် authentication method (စစ်မှန်ကြောင်းအသိအမှတ်ပြုခြင်းနည်းလမ်း) plugin များသည် အလုပ်ဖြစ်ပါသည်။ ဤ plugin များဖြင့် HTTP request object (တောင်းဆိုမှုအရာဝတ္တု) သို့ ဝင်ရောက် ကြည့်ရှုနိုင်ပြီး တောင်းဆိုချက်သာမက ၎င်း၏ခေါင်းစီးများကိုပါ ကိုင်တွယ်နိုင်ပါသည်။ ၎င်းသည် အမျိုးမျိုးသော အင်တာနက်အခြေခံသည့် authentication ပုံစံများစွာကို ခွင့်ပြုသည်။ HTTP(S) မှတစ်ဆင့် စံ အသုံးပြုသူအမည်/စကားဝှက် authentication နည်းလမ်းအားအသုံးပြု၍ ချိတ်ဆက်သည့်အခါ ချိတ်ဆက်မှုအတွင်း HTTP BASIC authentication အား ကြိုးပမ်းမည်ဖြစ်သည်။


.. _figure_auth_https:

.. figure:: img/auth-http-basic-wms.png
   :align: center

   HTTP BASIC အတွက် WMS ချိတ်ဆက်မှုတစ်ခုအား ပြင်ဆင်သတ်မှတ်ခြင်း

Database authentication (Database စစ်မှန်ကြောင်းအသိအမှတ်ပြုခြင်း)
------------------------------------------------------------------

Database အရင်းအမြစ်များနှင့်ချိတ်ဆက်ထားမှုများကို အများအားဖြင့် ``key=value`` အတွဲများအဖြစ်သိမ်းဆည်းပါသည်။ အကယ်၍ authentication configuration တစ်ခုအားအသုံးပြုနေခြင်း *မဟုတ်* ပါက အသုံးပြုသူအမည်များ နှင့် စကားဝှက်များကိုဖော်ထုတ်ပြသနေလိမ့်မည်။ authentication စနစ်ဖြင့် ပြင်ဆင်သတ်မှတ်လိုက်သောအခါ credential (အထောက်အထား) များကို ``key=value`` များဖြင့် ကိုယ်စားပြုဖော်ပြမည်ဖြစ်သည်။ (ဥပမာ ``authfg=81t21b9``)


.. _figure_auth_database:

.. figure:: img/auth-db-ssl-pki.png
   :align: center

   Postgres SSL-with-PKI ချိတ်ဆက်မှုအား ပြင်ဆင်သတ်မှတ်ခြင်း

PKI authentication (PKI စစ်မှန်ကြောင်းအသိအမှတ်ပြုခြင်း)
--------------------------------------------------------

Authentication စနစ်အတွင်းရှိ PKI (Public Key Infrastructure) အစိတ်အပိုင်းများကို ပြင်ဆင်သတ်မှတ်သောအခါတွင် ရွေးချယ်စရာအနေဖြင့် component များကို database သို့ importလုပ်ခြင်း သို့မဟုတ် ဖိုင်စနစ်တွင် သိမ်းဆည်းထားသော components ဖိုင်များကို reference (အကိုးအကား) လုပ်ခြင်းတို့ရှိပါသည်။ Reference လုပ်ခြင်းသည် ထိုသို့သော component များ မကြာခဏပြောင်းလဲလျှင် အသုံးဝင်နိုင်သလို system administrator မှ component များကို အစားထိုးမည့်နေရာတွင်လည်းအသုံးဝင်နိုင်ပါသည်။ ရွေးချယ်စရာတစ်မျိုးမဟုတ်တစ်မျိုးတွင် database အတွင်းရှိ private key များသို့ ဝင်ရောက်ရန်အတွက် လိုအပ်သော စကားဝှက်ကို သိမ်းဆည်းထားရန် လိုအပ်ပါမည်။

.. _figure_auth_pki_config:

.. figure:: img/auth-pki-config.png
   :align: center

   PKI ပြင်ဆင်သတ်မှတ်ခြင်းလုပ်ငန်းစဉ်

QGIS `Options` dialog (:menuselection:`Settings --> Options`) မှ :guilabel:`Authentication` tab တွင် :guilabel:`Manage Certificates` ခလုတ်အား click နှိပ်ခြင်းဖြင့် **Certificate Manager** သို့ဝင်ရောက်နိုင်ပြီး ၎င်းအတွင်းရှိ သီးခြား editors များတွင် PKI component များအားလုံးကိုစီမံခန့်ခွဲနိုင်မည်ဖြစ်သည်။

.. _figure_auth_pki_certif:

.. figure:: img/auth-open-Certificate-manager.png
   :align: center

   Certificate Manager အားဖွင့်ခြင်း


:guilabel:`Certificate Manager` ထဲတွင်  **Identities** ၊ **Servers** နှင့် **Authorities** တို့အတွက် editor (တည်းဖြတ်ပြင်ဆင်ရေးကိရိယာ) များရှိသည်။ ၎င်းတို့တစ်ခုချင်းစီအတွက် ကိုယ်ပိုင် tab များထဲတွင်ရှိပြီး အပေါ်ရှိ လုပ်ငန်းစဉ် ဇယားထဲတွင် ကြုံတွေ့ရမည့် ဝါစဉ်အတိုင်းဖော်ပြထားမည်ဖြစ်သည်။ လုပ်ငန်းစဉ်နှင့် ကျင့်သားရသွားသည်နှင့်တစ်ပြိုင်နက် မိမိအသုံးများသည့် editor များအတိုင်း tab order (ဝါစဉ်) အားစီထားပေးမည်ဖြစ်သည်။

.. note::

   Authentication စနစ်တွင်ပြုလုပ်ထားသော အားလုံးသောပြောင်းလဲမှုများကို authentication database တွင် ချက်ချင်းသိမ်းဆည်းသောကြောင့် ပြောင်းလဲမှုမှန်သမျှအား :guilabel:`Options` dialog မှ :guilabel:`OK` ခလုတ်အား click နှိပ်၍ သိမ်းဆည်းရန် မလိုခြင်းသည် Options dialog ထဲရှိ အခြား setting များနှင့်မတူသည့် အချက်ဖြစ်သည်။


Authorities (အခွင့်အာဏာများ)
.............................

QGIS **Options** dialog ၏ **Authentication** tab မှတစ်ဆင့် **Certificate manager** ထဲရှိ **Authorities** tab ကိုသွား၍ Certificate Authorities (CAs) များကိုစီမံခန့်ခွဲနိုင်သည်။

အထက်ဖော်ပြပါ လုပ်ငန်းစဉ်တွင် ညွှန်းဆိုခဲ့သည့်အတိုင်း ပထမအဆင့်အနေဖြင့် CAs ဖိုင်တစ်ခုကို import သို့မဟုတ် reference လုပ်ရန်ဖြစ်သည်။ ဤအဆင့်သည် (optional) မလုပ်လျှင်လည်းရပြီး PKI trust chain သည် စီးပွားဖြစ် လက်မှတ်ရောင်းချသူထံမှ လက်မှတ်ကဲ့သို့ Operating System တွင် ထည့်သွင်းထားပြီးသော root CA များမှ စတင်ပါက ၎င်းအဆင့်မလိုအပ်နိုင်ပါ။ မိမိ၏ authenticating root CA သည် Operating System ၏ ယုံကြည်စိတ်ချရသည့် root CA များထဲတွင် မပါခဲ့လျှင် ၎င်းအား import လုပ်ရန် သို့မဟုတ် ၎င်း၏ဖိုင်စနစ် လမ်းကြောင်းအား ရည်ညွှန်းပေးရန်လိုအပ်ပါလိမ့်မည်။ (မသေချာလျှင် မိမိ system administrator အားဆက်သွယ်ပါ။ )

.. _figure_auth_pki_editor:

.. figure:: img/auth-editor-authorities.png
   :align: center

   Authorities editor

Operating System တွင် root CAs များသည် default အတိုင်းရှိနေမည်ဖြစ်သော်လည်း ၎င်းတို့၏ trust setting များသည် အလိုအလျောက်ဆက်ခံရရှိမည်မဟုတ်ပါ။ အထူးသဖြင့် OS root CA တို့၏မူဝါဒများအား ချိန်ညှိထားပြီးလျှင် certificate trust policy setting များအား စစ်ဆေးကြည့်သင့်ပါသည်။ သက်တမ်းကုန်ဆုံးသွားသည့် မည်သည့် certificate မဆို မယုံကြည်ရ ဟုသတ်မှတ်မည်ဖြစ်ပြီး ၎င်း၏ ယုံကြည်ရမှုမူဝါဒ ကို အစားထိုးရေးသားထားခြင်း မရှိသမျှ လုံခြုံစိတ်ချရသော ဆာဗာချိတ်ဆက်မှုများတွင် အသုံးပြုမည်မဟုတ်ပါ။ မည်သည့် certificate တစ်ခုအတွက်မဆို QGIS မှ ရှာဖွေတွေ့ရှိနိုင်သည့် trust chain ကိုကြည့်ရှုရန် ၎င်းအား ရွေးချယ်ပြီး |metadata| :sup:`Show information for certificate` ပေါ်တွင် click နှိပ်ပါ။

.. _figure_auth_pki_info:

.. figure:: img/auth-authority-imported_cert-info-chain.png
   :align: center

   Certificate အချက်အလက် dialog


Chain အတွင်းတွင် ရွေးချယ်ထားသော မည်သည့် certificate အတွက်မဆို :guilabel:`Trust policy` |selectString| အားတည်းဖြတ်ပြင်ဆင်နိုင်သည်။ ရွေးချယ်ထားသော certification *တစ်ခုချင်း* အတွက် |fileSave|:sup:`Save certificate trust policy change to database` ခလုတ်အား click မနှိပ်ပါက ၎င်းအတွက် မည်သည့် trust policy အပြောင်းအလဲကိုမျှ database ထဲတွင်သိမ်းဆည်းပေးမည်မဟုတ်ပါ။ Dialog အားပိတ်လိုက်ရုံဖြင့် policy အပြောင်းအလဲများကို သက်ရောက်စေမည် **မဟုတ်** ပါ။

.. _figure_auth_pki_policy:

.. figure:: img/auth-authority-edit-trust_save-not-close.png
   :align: center

   Trust policy အပြောင်းအလဲများကို သိမ်းဆည်းခြင်း

လုံခြုံစိတ်ချရသော ချိတ်ဆက်မှုများအတွက် စစ်ထုတ်ထားသော ယုံကြည်စိတ်ချရသည့် CA များ (intermediate နှင့်  root certificates နှစ်မျိုးလုံး)ကို စစ်ဆေးနိုင်မည်ဖြစ်သကဲ့သို့ |transformSettings| **Options** ခလုတ်ပေါ်တွင် click နှိပ်ခြင်းဖြင့် default trust policy အား ပြောင်းလဲနိုင်မည်ဖြစ်သည်။


.. warning::
   Default trust policy အားပြောင်းလဲလိုက်ခြင်းသည် လုံခြုံစိတ်ချရသော connection များနှင့်ပတ်သက်၍ ပြဿနာများဖြစ်ပေါ်စေနိုင်သည်။


.. _figure_auth_pki_options:

.. figure:: img/auth-editor-authorities_utilities-menu.png
   :align: center

   Authorities ရွေးချယ်စရာများ menu

Certificate Authorities များကို import လုပ်နိုင်ပါသည် သို့မဟုတ် Certificate Authorities အများအပြားရှိသော ဖိုင်တစ်ခုမှ ဖိုင်စနစ်လမ်းကြောင်းကို သိမ်းဆည်းနိုင်သည် သို့မဟုတ် CAs တစ်ခုချင်းစီကို import ပြုလုပ်နိုင်ပါသည်။ CA chain certification များစွာပါသော ဖိုင်များအတွက် စံ PEM ပုံစံသည် ဖိုင်၏အောက်ခြေ၌ root cert ပါရှိပြီး အထက်တွင် လက်မှတ်ထိုးထားသော child certificate များအားလုံးပါရှိကာ ဖိုင်၏အစဘက်သို့ဦးတည်ပါသည်။

CA certificate import dialog တွင် ဖိုင်အတွင်းရှိ CA certificate များအားလုံးကို တွေ့နိုင် (order ကိုထည့်သွင်းမစဉ်းစားပဲ) ပြီး ၎င်း dialog တွင် ကိုက်ညီမှုမရှိဟုယူဆသည့် certificate များကို import လုပ်ရန် ရွေးချယ်ခွင့်လည်းရှိသည် (အကယ်၍ ၎င်းတို့၏ trust policy အား အစားထိုးပြင်ဆင်ရေးသားလိုလျှင်)။ Trust policy အား အစားထိုးပြင်ဆင်ရေးသားခြင်းကို import လုပ်နေစဉ်အတွင်း ပြုလုပ်နိုင်သကဲ့သို့ နောက်ပိုင်းမှ **Authorities** editor အတွင်းတွင် ပြုလုပ်နိုင်သည်။

.. _figure_auth_pki_import:

.. figure:: img/auth-authority-import.png
   :align: center

   Certificate များ ထည့်သွင်းခြင်း dialog

.. note::
   အကယ်၍ :guilabel:`PEM text` အကွက်ထဲသို့ certificate အချက်အလက်များကို paste လုပ်မည်ဆိုပါက encrypt လုပ်ထားသော certificate များကို ထောက်ပံ့ပေးမည်မဟုတ်ကြောင်းသတိပြုပါ။

Identities (အထောက်အထားများ)
............................

QGIS **Options** dialog ၏  **Authentication** tab မှ :guilabel:`Certificate manager` သို့သွား၍ :guilabel:`Identities` tab မှတစ်ဆင့် client identity အစုများ (bundles) ကိုစီမံခန့်ခွဲနိုင်သည်။ Identity တစ်ခုသည် PKI-ရရှိသော ဝန်ဆောင်မှုအတွက် အထောက်အထားရှိကြောင်းကို အတည်ပြုပေးသည့်အရာတစ်ခုဖြစ်သည်။ ပုံမှန်အားဖြင့် ၎င်းတွင် client certificate တစ်ခုနှင့် private key သည် သီးခြားဖိုင်များအဖြစ် သို့မဟုတ် အစုလိုက်ဖိုင်တစ်ခုအဖြစ် ပေါင်းစပ်ပါဝင်သည်။ အစုလိုက်ဖိုင် သို့မဟုတ် private key များကို အများအားဖြင့် စကားဝှက်ဖြင့် ကာကွယ်ထားပါသည်။

Certificate Authorities (CAs) တစ်ခုကို import လုပ်ပြီးနောက် မည်သည့် identity bundle များကိုမဆို authentication database ထဲသို့ import ပြုလုပ်နိုင်ပါသည်။ အကယ်၍ identity များကိုသိမ်းဆည်းခြင်းမပြုလိုပါက authentication configuration တစ်ခုချင်းစီအတွင်းတွင် ၎င်းတို့၏ component ဖိုင်စနစ် လမ်းကြောင်းများအားရည်ညွှန်းထားနိုင်သည်။



.. _figure_auth_pki_identities:

.. figure:: img/auth-editor-identities.png
   :align: center

   Identities editor

Identity bundle တစ်ခုအား import လုပ်ရာတွင် စကားဝှက်ဖြင့် ကာကွယ်ထားခြင်းဖြစ်နိုင်သကဲ့သို့ မကာကွယ်ထားခြင်းလည်းဖြစ်နိုင်ပြီး trust chain တစ်ခုအားဖွဲ့စည်းသည့် CA certificate များပါဝင်နိုင်သည်။ Trust chain certification များကို ဤနေရာတွင် import လုပ်မည်မဟုတ်ဘဲ ၎င်းတို့ကို :guilabel:`Authorities` tab ၏အောက်တွင် သီးခြားစီ ထည့်နိုင်မည်ဖြစ်သည်။

Import လုပ်ပြီးနောက် bundle ၏ certificate နှင့် private key ကို QGIS မာစတာစကားဝှက်ဖြင့် encrypt ပြုလုပ်ထားသော key ၏သိုလှောင်မှုနှင့်အတူ database တွင် သိမ်းဆည်းမည်ဖြစ်သည်။ နောက်ပိုင်းတွင် database မှ သိမ်းဆည်းထားသော bundle ကို အသုံးပြုသောအခါ မာစတာစကားဝှက်ကို ထည့်သွင်းရန်သာ လိုအပ်မည်ဖြစ်သည်။

PEM/DER (.pem/.der) နှင့် PKCS#12 (.p12/.pfx) အစိတ်အပိုင်းများပါဝင်သော တစ်ကိုယ်ရည်သုံး (personal) identity bundle များကိုထောက်ပံ့ပေးပါသည်။ အကယ်၍ key တစ်ခု သို့မဟုတ်  bundle တစ်ခုအား စကားဝှက်ဖြင့်ကာကွယ်ထားပါက import မလုပ်မီ အစိတ်အပိုင်းအားအတည်ပြုရန်အတွက် စကားဝှက်လိုအပ်မည်ဖြစ်သည်။ အလားတူပင် bundle ထဲရှိ client certificate သည် မမှန်ကန်ပါက (ဥပမာအားဖြင့် ၎င်း၏ သက်တမ်းသည်အသက်မဝင်သေးလျှင် သို့မဟုတ် သက်တမ်းကျော်လွန်သွားလျှင်) bundle အား import လုပ်၍ရမည်မဟုတ်ပါ။


.. _figure_auth_pki_identities_import:

.. figure:: img/auth-identity-import_paths.png
   :align: center

   PEM/DER identit ထည့်သွင်းခြင်း

.. _figure_auth_pki_identities_import_2:

.. figure:: img/auth-identity-import_bundle-valid.png
   :align: center

   PKCS#12 identity ထည့်သွင်းခြင်း

Handling bad layers (ကောင်းမွန်မှုမရှိသော layer များကိုကိုင်တွယ်ခြင်း)
-----------------------------------------------------------------------

အခါအားလျော်စွာ project file တစ်ခုထဲရှိ သိမ်းဆည်းထားသော authentication configuration ID သည် လျော်ကန်မှုမရှိတော့သည်ကိုတွေ့ရနိုင်ပါသည်။ ဖြစ်နိုင်သည့်အကြောင်းအရင်းတစ်ခုမှာ လက်ရှိ authentication database သည် project ကိုနောက်ဆုံး သိမ်းဆည်းခဲ့စဉ်ကနှင့် မတူကွဲပြားနေသောကြောင့် သို့မဟုတ် credential များ ကွာဟနေမှုကြောင့်ဖြစ်နိုင်ပါသည်။ ထိုကဲ့သို့ ကြုံသောအခါ QGIS ကိုစတင်လိုက်သည်နှင့် :guilabel:`Handle bad layers` dialog ကိုတွေ့ရမည်ဖြစ်သည်။


.. _figure_auth_pki_badlayers:

.. figure:: img/auth-handle-bad-layers.png
   :align: center

   Authentication ဖြင့် ကောင်းမွန်မှုမရှိသော layer များကို ကိုင်တွယ်ခြင်း

အကယ်၍ အချက်အလက်ရင်းမြစ်တစ်ခုတွင် ၎င်းနှင့်ဆက်စပ်နေသည့် authentication configuration ID တစ်ခုရှိနေပါက ၎င်းကို တည်းဖြတ်ပြင်ဆင်နိုင်လိမ့်မည်။ ထိုသို့ပြုလုပ်ခြင်းဖြင့် data အရင်းအမြစ် string (စာသား) အား အလိုအလျောက်တည်းဖြတ်ပြင်ဆင်သွားမည်ဖြစ်သည်။ Text editor တစ်ခုထဲတွင် project file အားဖွင့်၍ string အားတည်းဖြတ်ပြင်ဆင်ခြင်းနှင့် များစွာဆင်တူသည်။


.. _figure_auth_pki_badlayers_edit:

.. figure:: img/auth-handle-bad-layers-edit.png
   :align: center

   ကောင်းမွန်မှုမရှိသော layer ၏ authentication config ID ကို တည်းဖြတ်ပြင်ဆင်ခြင်း

Changing authentication config ID (စစ်မှန်ကြောင်းအသိအမှတ်ပြုခြင်းဆိုင်ရာ ပြင်ဆင်သတ်မှတ်ခြင်း ID အားပြောင်းလဲခြင်း)
-------------------------------------------------------------------------------------------------------------------

အခါအားလျော်စွာ အရင်းအမြစ်တစ်ခုအား ဝင်ရောက်ကြည့်ရှုခြင်းနှင့် ဆက်စပ်နေသော authentication configuration ID ကို ပြောင်းလဲရန် လိုအပ်နိုင်ပါသည်။ ထိုသို့ပြောင်းလဲခြင်းသည် အောက်ပါအခြေအနေများတွင် အသုံးဝင်နိုင်ပါသည်-

* **အရင်းအမြစ်၏ auth config ID သည် ဆီလျော်မှုမရှိတော့ခြင်း** - Authentication database များ ပြောင်းလဲသောအခါနှင့် အရင်းအမြစ်တစ်ခုနှင့် ဆက်စပ်ထားပြီးဖြစ်သည့် ID တွင် configuration အသစ်တစ်ခုကို *ချိန်ညှိ* ရန် လိုအပ်သောအခါမျိုးတွင် ဤအရာဖြစ်ပွားနိုင်ပါသည်။
* **Project file များအားမျှဝေသုံးထားခြင်း** - Project များအား မျှဝေထားသော ဖိုင်ဆာဗာမှတဆင့် အခြားအသုံးပြုသူများနှင့် မျှဝေရန် စီစဉ်ထားပါက အရင်းအမြစ်နှင့် ဆက်စပ်သော စာလုံး-၇လုံးပါသည့် ကုဒ် (**a-z** နှင့်/သို့မဟုတ် **0-9** တို့ပါဝင်သော) အား *ကြိုတင်သတ်မှတ်* နိုင်သည်။ ထို့နောက် အသုံးပြုသူတစ်ယောက်ချင်းအနေဖြင့် ၎င်းတို့၏ အရင်းအမြစ် credential များအလိုက် သီးသန့် authentication configuration ID ကို ပြောင်းလဲနိုင်သည်။ Project အားဖွင့်လိုက်သောအခါ authentication database ထဲတွင် ID အား တွေ့ရမည်ဖြစ်သော်လည်း credential များသည် အသုံးပြုသူ တစ်ဦးချင်းစီအလိုက်ကွဲပြားနိုင်ပါသည်။

.. _figure_auth_id:

.. figure:: img/auth-change-config-id.png
   :align: center

   Layer တစ်ခု၏ authentication config ID အားပြောင်းလဲခြင်း (သော့ဖွင့်ထားသော အဝါရောင်စာသားအကွက်)


.. warning::
   Auth config ID အားပြောင်းလဲခြင်းကို အဆင့်မြင့်လုပ်ငန်းစဉ်တစ်ခုအဖြစ်ယူဆပြီး ၎င်းသည် အဘယ်ကြောင့် လိုအပ်ကြောင်း အပြည့်အဝ နားလည်မှသာ လုပ်ဆောင်သင့်ပါသည်။ ထိုအတွက်ကြောင့် ID ကိုတည်းဖြတ်ပြင်ဆင်ခြင်းမပြုမီ ID ၏စာသားအကွက်ကို ဖွင့်ရန် click နှိပ်ပေးရမည့် သော့ခလောက် ခလုတ်တစ်ခုရှိနေခြင်းဖြစ်သည်။


QGIS Server support (QGIS ဆာဗာ ထောက်ပံ့ပေးမှု)
-----------------------------------------------

QGIS server တွင် မြေပုံတစ်ခုအတွက် authentication configuration များပါရှိသော layer များဖြင့် project file တစ်ခုကို အခြေခံအနေဖြင့် အသုံးပြုသောအခါ အရင်းအမြစ်များကို loading လုပ်ရန်အတွက် QGIS အတွက် ထပ်မံလိုအပ်သော setup အဆင့် နှစ်ခု ရှိပါသည်-

* Authentication database အားဝင်ရောက်အသုံးပြုနိုင်ရန်လိုအပ်သည်
* Authentication database ၏ မာစတာစကားဝှက် အားရရှိရန်လိုအပ်သည်

Authentication စနစ်ကို ထည့်သွင်းသောအခါ QGIS server သည် :file:`qgis-auth.db` file ကို ပွင့်လျက်ရှိသည့် :ref:`user profile <user_profiles>` ထဲတွင် သို့မဟုတ် ``QGIS_AUTH_DB_DIR_PATH`` environment variable မှသတ်မှတ်ထားသော ဖိုင်လမ်းကြောင်းတွင် ဖန်တီးပါလိမ့်မည် သို့မဟုတ် အသုံးပြုပါလိမ့်မည်။ Server ၏ အသုံးပြုသူတွင် HOME directory မရှိပါက server ၏အသုံးပြုသူမှ ဖတ်ခြင်း/ရေးသားပြင်ဆင်ခြင်း ပြုလုပ်နိုင်ပြီး web မှတစ်ဆင့် ဝင်ရောက်နိုင်သော လမ်းကြောင်းများအတွင်း မတည်ရှိသော လမ်းကြောင်း (directory) တစ်ခုကိုသတ်မှတ်ရန် environment variable ကိုအသုံးပြုပါ။

မာစတာစကားဝှက်အား server သို့ပေးရန် server လုပ်ငန်းစဉ်များအသုံးပြုသူမှဖတ်နိုင်ပြီး ``QGIS_AUTH_PASSWORD_FILE`` environment variable အားအသုံးပြု၍သတ်မှတ်ထားသော ဖိုင်စနစ်ပေါ်ရှိလမ်းကြောင်းတစ်ခု၌ ဖိုင်၏ ပထမစာကြောင်းတွင် ၎င်းကို ရေးသားပါ။ File အား server ၏ လုပ်ငန်းစဉ်အသုံးပြုသူမှသာ ဖတ်၍ရနိုင်အောင်ကန့်သတ်ထားရန်နှင့် web မှတစ်ဆင့် ဝင်ရောက်နိုင်သော လမ်းကြောင်းများအတွင်း သိမ်းဆည်းမထားစေရန် သေချာအောင်ပြုလုပ်ပါ။

.. note::

   အသုံးပြုပြီးနောက် ``QGIS_AUTH_PASSWORD_FILE`` variable အား server ၏ environment မှချက်ချင်းဖယ်ရှားပစ်မည်ဖြစ်သည်။

SSL server exceptions (SSL server ခြွင်းချက်များ)
--------------------------------------------------

.. _figure_auth_server:

.. figure:: img/auth-ssl-config.png
   :align: center

   SSL server ခြွင်းချက်

QGIS **Options** dialog ၏ **Authentication** အပိုင်းထဲရှိ **Servers** tab မှတစ်ဆင့် SSL server configuration များနှင့် ခြွင်းချက်များကို စီမံခန့်ခွဲနိုင်သည်။

တစ်ခါတစ်ရံ SSL server တစ်ခုအား ချိတ်ဆက်သည့်အခါ SSL"handshake" သို့မဟုတ်  server ၏ certificate နှင့်ပတ်သက်သည့် ပြဿနာ များရှိတတ်ပါသည်။ ထိုပြဿနာများကို လျစ်လျူရှုနိုင်သကဲ့သို့ SSL server configuration တစ်ခုအား ခြွင်းချက်တစ်ခုအနေဖြင့်ဖန်တီးထားနိုင်သည်။ ဤအချက်သည် web browser များတွင် SSL အမှားအယွင်းများကို အစားထိုးလုပ်ဆောင်ပုံနှင့် ဆင်တူသော်လည်း ပိုမိုအကြမ်းဆန်သည့် ထိန်းချုပ်နိုင်မှုဖြင့် ရှိမည်ဖြစ်သည်။

.. warning::
   Server နှင့် client အကြားရှိ SSL setup တစ်ခုလုံးကို အပြည့်အဝနားမလည်လျှင် SSL server configuration တစ်ခုအားမဖန်တီးသင့်ပါ။ ထိုအစား ပြဿနာကို server administrator ထံသို့ သတင်းပို့ပါ။
  

.. note::
   အချို့သော PKI setup များသည် client များ၏အထောက်အထားများကိုအတည်ပြုရန် SSL server certificate အား အတည်ပြုရန်သုံးသော chain ကိုအသုံးပြုခြင်းထက် လုံးဝကွဲပြားသော CA trust chain ကိုအသုံးပြုပါသည်။ ထိုကဲ့သို့သော အခြေအနေများတွင် ချိတ်ဆက်ထားသောဆာဗာအတွက် ဖန်တီးထားသော မည်သည့် configuration မဆိုသည် client identity အတည်ပြုခြင်းဆိုင်ရာ ပြဿနာတစ်ခုကို ဖြေရှင်းနိုင်မည်မဟုတ်ဘဲ client identity အား ထုတ်ပေးသူ သို့မဟုတ် server administrator ကသာ ထိုပြဿနာအားဖြေရှင်းပေးနိုင်မည်ဖြစ်သည်။

|symbologyAdd| ခလုတ်အား click နှိပ်ခြင်းဖြင့် SSL server configuration တစ်ခုအား ကြိုတင်ပြင်ဆင်သတ်မှတ်နိုင်ပါသည်။ အခြားနည်းမှာ ချိတ်ဆက်မှု တစ်ခုအတွင်း SSL အမှားအယွင်းတစ်ခုပေါ်ပေါက်လာသောအခါ configuration တစ်ခုကိုထည့်သွင်းနိုင်မည်ဖြစ်ပြီး **SSL Error** dialog တစ်ခုအားပြသထားမည်ဖြစ်သည် (၎င်း dialog တွင် ထိုအမှားအယွင်းအား ယာယီလျစ်လျူရှုရန် သို့မဟုတ် database ထဲသို့ သိမ်းဆည်းပြီး လျစ်လျူရှုရန် ရွေးချယ်နိုင်သည်)-

.. _figure_auth_server_config:

.. figure:: img/auth-server-exception.png
   :align: center

   Configuration ကို ကိုယ်တိုင်ထည့်သွင်းခြင်း

.. _figure_auth_server_error:

.. figure:: img/auth-server-error-add-exception.png
   :align: center

   SSL error ပေါ်ပေါက်နေစဉ်အတွင်း configuration ထည့်သွင်းခြင်း

SSL configuration တစ်ခုအား database ထဲတွင် သိမ်းဆည်းပြီးသည်နှင့် ၎င်းကို တည်းဖြတ်ပြင်ဆင်နိုင်သကဲ့သို့ ဖျက်ပစ်နိုင်ပါသည်။

.. _figure_auth_server_ssl:

.. figure:: img/auth-editor-servers.png
   :align: center

   ရှိနှင့်ပြီးသား SSL configuration

.. _figure_auth_server_ssledit:

.. figure:: img/auth-server-edit.png
   :align: center

   ရှိနှင့်ပြီးသား SSL configuration တစ်ခုအားတည်းဖြတ်ပြင်ဆင်ခြင်း

အကယ်၍ SSL configuration တစ်ခုအား pre-configure (ကြိုတင်ပြင်ဆင်သတ်မှတ်ခြင်း) ပြုလုပ်လိုပြီး  import dialog သည် server ၏ connection အတွက် အလုပ်မလုပ်ပါက **Python Console** မှတစ်ဆင့်အောက်ပါ ကုဒ်အား run ၍ ချိတ်ဆက်မှုတစ်ခုကို မိမိကိုယ်တိုင် စတင်နိုင်မည်ဖြစ်သည်။ (``https://bugreports.qt-project.org`` အား မိမိ server ၏ URL ဖြင့်အစားထိုးရမည်)-


.. code-block:: python

   from qgis.PyQt.QtNetwork import QNetworkRequest
   from qgis.PyQt.QtCore import QUrl
   from qgis.core import QgsNetworkAccessManager

   req = QNetworkRequest(QUrl('https://bugreports.qt-project.org'))
   reply = QgsNetworkAccessManager.instance().get(req)

အမှားအယွင်းတစ်စုံတစ်ရာ ဖြစ်ပေါ်ပါက SSL error dialog ပေါ်လာမည်ဖြစ်ပြီး ၎င်းမှတစ်ဆင့်  configuration ကို database တွင်သိမ်းဆည်းရန် ရွေးချယ်နိုင်မည်ဖြစ်သည်။

.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |fileSave| image:: /static/common/mActionFileSave.png
   :width: 1.5em
.. |metadata| image:: /static/common/metadata.png
   :width: 1.5em
.. |selectString| image:: /static/common/selectstring.png
   :width: 2.5em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
.. |transformSettings| image:: /static/common/mActionTransformSettings.png
   :width: 1.5em
