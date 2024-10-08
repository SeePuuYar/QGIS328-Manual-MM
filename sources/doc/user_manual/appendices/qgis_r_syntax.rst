.. index::
   pair: R; Syntax
.. _r-syntax:

*****************************************************************************
Appendix D: QGIS R script syntax (နောက်ဆက်တွဲ ဃ - QGIS R script ဝါကျဖွဲ့ပုံ)
*****************************************************************************

Matteo Ghetta မှ ပါဝင်ကူညီထားပြီး `Scuola Superiore Sant'Anna
<https://www.santannapisa.it/en/istituto/scienze-della-vita/istituto-di-scienze-della-vita>`_ မှ ငွေကြေးထောက်ပံ့ပေးထားပါသည်။

လုပ်ငန်းဆောင်တာများလုပ်ဆောင်ခြင်း (Processing) တွင် R script များရေးသားခြင်းသည် အထူးဝါကျရေးဖွဲ့ပုံ (special syntax) များကြောင့် အနည်းငယ်ရှုပ်ထွေးပါသည်။

Processing R script တစ်ခုသည် ၎င်း၏ **Inputs (ထည့်သွင်းချက်များ)** နှင့် **Outputs (ရလာဒ်များ)** ကို သတ်မှတ်ပေးခြင်းနှင့်စတင်ပြီး တစ်ခုချင်းစီ၏ရှေ့တွင် (``##``) သင်္ကေတများပါဝင်ပါသည်။

Input များ မစတင်မီတွင် algorithm ထားရှိမည့် အုပ်စုကို သတ်မှတ်ပေးနိုင်ပါသည်။ အုပ်စုသည် ရှိနေပြီးသားဖြစ်လျှင် algorithm ကို ၎င်းရှိပြီးသား အုပ်စုထဲသို့ ပေါင်းထည့်သွားမည်ဖြစ်ပြီး မရှိသေးလျှင် အုပ်စုကို ဖန်တီးပါလိမ့်မည်။ အောက်ဖော်ပြပါ ဥပမာတွင် အုပ်စု၏အမည်သည် *My group* ဖြစ်ပါသည်-

``##My Group=group``

Inputs (ထည့်သွင်းချက်များ)
===========================

ထည့်သွင်းမည့် data နှင့် parameter (သတ်မှတ်ချက်) များအားလုံးကို သီးခြားသတ်မှတ်ပေးရပါမည်။ Input အမျိုးအစား များစွာရှိပါသည်-

* vector: ``##Layer = vector``
* vector field: ``##F = Field Layer`` (`Layer` သည် field နှင့်သက်ဆိုင်သည့် input vector layer ၏ အမည်ဖြစ်သည်)
* raster: ``##r = raster``
* table (ဇယား): ``##t = table``
* number (ကိန်းဂဏန်း): ``##Num = number``
* string (စာသား): ``##Str = string``
* boolean (အမှန်/အမှား): ``##Bol = boolean``
* Drop down (ရွေးချယ်ရန်စရာ) menu ထဲရှိ element များ။ Item များကို semicolons ``;`` ဖြင့် ပိုင်းခြားထားရမည်ဖြစ်သည်: ``##type=selection point;lines;point+lines``

Outputs (ရလာဒ်များ)
====================

Input များအတွက်ကဲ့သို့ပင် output (ရလာဒ်) တစ်ခုချင်းစီကို Script ၏အစပိုင်းတွင် သတ်မှတ်ပေးထားရမည်ဖြစ်သည်-

* vector: ``##output= output vector``
* raster: ``##output= output raster``
* table (ဇယား): ``##output= output table``
* plots (အကွက်များ): ``##output_plots_to_html`` (အစောပိုင်း version များတွင် ##showplots ဖြစ်သည်)
* *Result Viewer* (ရလာဒ်ကြည့်ရှုသည့်နေရာ) ထဲတွင် R output များကိုပြသရန်အတွက် ပြသလိုသည့် output ၏ command ရှေ့တွင် ``>`` ကိုထည့်ပေးပါ။

.. index::
   pair: R; Syntax summary
.. _r-syntax-table:

Syntax Summary for QGIS R scripts (QGIS R script များအတွက် Syntax အနှစ်ချုပ်)
==============================================================================

.. :note: Module contributed by Matteo Ghetta - funded by
   `Scuola Superiore Sant'Anna <http://www.santannapisa.it/it/istituto/scienze-della-vita/agricultural-water-management>`_

Input နှင့် output parameter အမျိုးအစားများစွာ ရှိပါသည်။

Input parameter အမျိုးအစားများ
-------------------------------

.. list-table::
   :header-rows: 1
   :widths: 20 20 40
   :class: longtable

   * - Parameter
     - Syntax ဥပမာ
     - ပြန်လည်ရရှိလာမည့် object များ
   * - vector
     - Layer = vector
     - sf object (သို့မဟုတ် SpatialDataFrame object ၊ ##load_vector_using_rgdal ကို သီးခြားသတ်မှတ်ထားလျှင်)
   * - vector point
     - Layer = vector point
     - sf object (သို့မဟုတ် SpatialDataFrame object ၊ ##load_vector_using_rgdal ကို သီးခြားသတ်မှတ်ထားလျှင်)
   * - vector line
     - Layer = vector line
     - sf object (သို့မဟုတ် SpatialDataFrame object ၊ ##load_vector_using_rgdal ကို သီးခြားသတ်မှတ်ထားလျှင်)
   * - vector polygon
     - Layer = vector polygon
     - sf object (သို့မဟုတ် SpatialPolygonsDataFrame object ၊ ##load_vector_using_rgdal ကို သီးခြားသတ်မှတ်ထားလျှင်)
   * - multiple vector
     - Layer = multiple vector
     - sf object (သို့မဟုတ် SpatialDataFrame objects ၊ ##load_vector_using_rgdal ကို သီးခြားသတ်မှတ်ထားလျှင်)
   * - table
     - Layer = table
     - CSV မှ dataframe သို့ပြောင်းလဲခြင်း ၊ ``read.csv`` function ၏ ပုံမှန် object
   * - field
     - Field = Field Layer
     - ရွေးချယ်ထားသော Field ၏အမည် ၊ ဥပမာ- ``"Area"``
   * - raster
     - Layer = raster
     - RasterBrick object ၊ ``raster`` package ၏ ပုံမှန် object
   * - multiple raster
     - Layer = multiple raster
     - RasterBrick objects ၊ ``raster`` package ၏ ပုံမှန် object
   * - number
     - N = number
     - ရွေးချယ်ထားသော integer (ကိန်းပြည့်) သို့မဟုတ် floating (ဒဿမကိန်း) ဂဏန်း
   * - string
     - S = string
     - Box ထဲတွင် ထည့်သွင်းထားသော စာသား
   * - longstring
     - LS = longstring
     - Box ထဲတွင် ထည့်သွင်းထားသော စာသား ၊ ပုံမှန်စာသားထက် ပိုမိုရှည်နိုင်သည်
   * - selection
     - S = selection first;second;third
     - Dropdown menu ထဲတွင် ရွေးချယ်ထားသော item ၏ စာသား
   * - crs
     - C = crs
     - ရွေးချယ်ထားသော CRS ၏စာသား ။ ``"EPSG:4326"`` format ဖြင့်
   * - extent
     - E = extent
     - ``raster`` package ၏ extent ၊ ``E@xmin`` အနေဖြင့် တန်ဖိုးကို ထုတ်ယူနိုင်သည်
   * - point
     - P = point
     - မြေပုံပေါ်တွင် click နှိပ်သောအခါ point ၏ ကိုဩဒိနိတ်ကို ရရှိမည်ဖြစ်သည်
   * - file
     - F = file
     - ရွေးချယ်ထားသော ဖိုင်လမ်းကြောင်း ၊ ဥပမာ- "/home/matteo/file.txt"
   * - folder
     - F = folder
     - ရွေးချယ်ထားသော folder လမ်းကြောင်း ၊ ဥပမာ- "/home/matteo/Downloads"


Parameter တစ်ခုသည် **OPTIONAL** (ရွေးချယ်ခွင့်ရှိသော) ဖြစ်နိုင်သည်။ ဆိုလိုသည်မှာ မည်သည့်အရာမှ မရွေးချယ်ပဲ လျစ်လျူရှုထားနိုင်သည်။

Input တစ်ခုကို optional အနေဖြင့် သတ်မှတ်ရန်အတွက် input ရှေ့တွင် ``optional`` စာသားကို ထည့်ပေးပါ။ ဥပမာ-

::

  ##Layer = vector
  ##Field1 = Field Layer
  ##Field2 = optional Field Layer


Output parameter types (ရလာဒ် parameter အမျိုးအစားများ)
--------------------------------------------------------

+----------------+----------------------------------+
| Parameter      | Syntax ဥပမာ                      |
+================+==================================+
| vector         | Output = output vector           |
+----------------+----------------------------------+
| raster         | Output = output raster           |
+----------------+----------------------------------+
| table          | Output = output table            |
+----------------+----------------------------------+
| file           | Output = output file             |
+----------------+----------------------------------+

.. note:: 
  
   Plot များကို *Processing Result Viewer* မှတဆင့် ``png`` အနေဖြင့် သိမ်းဆည်းနိုင်ပါသည်၊ သို့မဟုတ် algorithm interface (မျက်နှာပြင်) မှ plot များကို တိုက်ရိုက်သိမ်းဆည်းနိုင်ပါသည်။


Script body (Script စာကိုယ်)
-----------------------------

Script body သည် R syntax အတိုင်းလုပ်ဆောင်ပြီး script နှင့်ပတ်သက်ပြီး အမှားတစ်စုံတရာ ရှိမရှိကို **Log** panel တွင်ကြည့်ရှုနိုင်ပါသည်။

Script ထဲတွင် ထပ်ဆောင်း library များအားလုံးကို ထည့်သွင်းထားရမည်ကို **သတိရပါ**။
::

  library(sp)

.. index::
   pair: R scripts; Examples

Examples (ဥပမာများ)
====================

Vector output ဥပမာ
-------------------

Input layer တစ်ခု၏ extent (အကျယ်အဝန်းအတိုင်းအတာ) မှ ကျပန်း point များကို ဖန်တီးပေးမည့် online မှ algorithm တစ်ခုကို ယူသုံးကြည့်ကြပါစို့-

::

  ##Point pattern analysis=group
  ##Layer=vector polygon
  ##Size=number 10
  ##Output=output vector
  library(sp)
  spatpoly = as(Layer, "Spatial")
  pts=spsample(spatpoly,Size,type="random")
  spdf=SpatialPointsDataFrame(pts, as.data.frame(pts))
  Output=st_as_sf(spdf)

ရှင်းလင်းချက် (Script ထဲရှိ လိုင်းတစ်ကြောင်းချင်းစီအတွက်)-

1. ``Point pattern analysis`` သည် algorithm ၏အုပ်စုဖြစ်သည်။
2. ``Layer`` သည် input **vector** layer ဖြစ်သည်။
3. ``Size`` သည် ပုံသေတန်ဖိုးအနေဖြင့် ၁၀ ဖြစ်သော **numerical (ကိန်းဂဏန်း)** parameter တစ်ခုဖြစ်သည်။
4. ``Output`` သည် algorithm မှ ဖန်တီးပေးမည့် **vector** layer ဖြစ်သည်။
5. ``library(sp)`` သည် **sp** ဟုခေါ်သော library ကိုထည့်သွင်းခြင်းဖြစ်သည်။
6. ``spatpoly = as(Layer, "Spatial")`` သည် sp object တစ်ခုသို့ ဘာသာပြန်ဆိုခြင်းဖြစ်သည်။
7. ``sp`` library ၏ ``spsample`` function ကိုခေါ်ယူပြီး အထက်တွင်သတ်မှတ်ထားသော input များ (``Layer`` နှင့် ``Size``) ကိုအသုံးပြု၍ လုပ်ဆောင် (run) စေသည်။
8. ``SpatialPointsDataFrame`` function ကိုအသုံးပြု၍ *SpatialPointsDataFrame* object တစ်ခုကို ဖန်တီးပါသည်။
9. ``st_as_sf`` function ကိုအသုံးပြု၍ output vector layer ကိုဖန်တီးပါသည်။


ဒါပါပဲ။ QGIS legend (ရည်ညွှန်းချက်) ထဲရှိ vector layer တစ်ခုဖြင့် algorithm ကို run ပြီး ကျပန်း point အရေအတွက်ကို ရွေးချယ်ပေးပါ။ ထွက်ရှိလာသော ရလာဒ် layer ကို မြေပုံထဲသို့ ထည့်သွင်းပေးပါလိမ့်မည်။

Raster output ဥပမာ
-------------------

``automap`` R package ၏ ``autoKrige`` function ကို အသုံးပြုပြီး input point vector layer ၏ သီးခြား field တစ်ခုမှ interpolate  (ရှိပြီးသားတန်ဖိုးများကိုသုံး၍မရှိသေးသောတန်ဖိုးများကိုတွက်ထုတ်ပေးသော) လုပ်ထားသောတန်ဖိုးများ၏ raster မြေပုံတစ်ခုကို ဖန်တီးရန် အောက်ဖော်ပြပါ script သည် အခြေခံ ordinay kriging ကို လုပ်ဆောင်ပေးပါလိမ့်မည်-

::

  ##Basic statistics=group
  ##Layer=vector point
  ##Field=Field Layer
  ##Output=output raster
  ##load_vector_using_rgdal
  require("automap")
  require("sp")
  require("raster")
  table=as.data.frame(Layer)
  coordinates(table)= ~coords.x1+coords.x2
  c = Layer[[Field]]
  kriging_result = autoKrige(c~1, table)
  prediction = raster(kriging_result$krige_output)
  Output<-prediction


``##load_vector_using_rgdal`` ကိုအသုံးပြုခြင်းအားဖြင့် input vector layer ကို ``SpatialDataFrame`` object တစ်ခုအနေဖြင့် ရရှိစေမည်ဖြစ်သောကြောင့် ၎င်းကို ``sf`` object တစ်ခုမှ ဘာသာပြန်ဆိုခြင်းအားလုပ်ဆောင်ရန်မလိုအပ်တော့ပါ။

Table output ဥပမာ
------------------

Output သည် table file (csv) တစ်ခုဖြစ်စေရန်အလို့ငှာ ``Summary Statistics`` algorithm ကို ပြင်ဆင်ကြည့်ကြပါစို့။

Script body သည် အောက်ပါအတိုင်းဖြစ်သည်-

::

  ##Basic statistics=group
  ##Layer=vector
  ##Field=Field Layer
  ##Stat=Output table
  Summary_statistics<-data.frame(rbind(
      sum(Layer[[Field]]),
      length(Layer[[Field]]),
      length(unique(Layer[[Field]])),
      min(Layer[[Field]]),
      max(Layer[[Field]]),
      max(Layer[[Field]])-min(Layer[[Field]]),
      mean(Layer[[Field]]),
      median(Layer[[Field]]),
      sd(Layer[[Field]])),
    row.names=c("Sum:","Count:","Unique values:","Minimum value:","Maximum value:","Range:","Mean value:","Median value:","Standard deviation:"))
  colnames(Summary_statistics)<-c(Field)
  Stat<-Summary_statistics


တတိယမြောက်စာကြောင်းသည် input ထဲရှိ **Vector Field** ကိုသတ်မှတ်ခြင်းဖြစ်ပြီး စတုတ္ထစာကြောင်းသည် algorithm ၏ output သည် table တစ်ခုဖြစ်သင့်ကြောင်း ပြောခြင်းဖြစ်သည်။

နောက်ဆုံးစာကြောင်းသည် script မှ ဖန်တီးထားသော ``Stat`` object ကိုယူ၍ ``csv`` table အဖြစ်သို့ ပြောင်းလဲပေးမည်ဖြစ်သည်။

Console output ဥပမာ
--------------------

အရှေ့ ဥပမာကို အသုံးပြု၍ table တစ်ခုဖန်တီးမည့်အစား **Result Viewer** ထဲတွင် ရလာဒ်ကို print ပြုလုပ်နိုင်ပါသည်-

::

  ##Basic statistics=group
  ##Layer=vector
  ##Field=Field Layer
  Summary_statistics<-data.frame(rbind(
  sum(Layer[[Field]]),
  length(Layer[[Field]]),
  length(unique(Layer[[Field]])),
  min(Layer[[Field]]),
  max(Layer[[Field]]),
  max(Layer[[Field]])-min(Layer[[Field]]),
  mean(Layer[[Field]]),
  median(Layer[[Field]]),
  sd(Layer[[Field]])),row.names=c("Sum:","Count:","Unique values:","Minimum value:","Maximum value:","Range:","Mean value:","Median value:","Standard deviation:"))
  colnames(Summary_statistics)<-c(Field)
  >Summary_statistics


Script တွင် ပြင်ဆင်မှု နှစ်ခုပြုလုပ်သည်မှလွဲ၍ အထက်ဖော်ပြပါ script နှင့်တထပ်တည်းဖြစ်ပါသည်-

#. Output ကိုသီးခြားမသတ်မှတ်ထားပါ (စတုတ္ထမြောက်စာကြောင်းကို ဖယ်ရှားလိုက်ပါသည်)
#. နောက်ဆုံးစာကြောင်းကို ``>`` ဖြင့် အစပြုထားပါသည်။ Result viewer ထဲတွင် output ကို ကြည့်ရှုနိုင်စေရန်အတွက် Processing (လုပ်ဆောင်မှု) ကို ခိုင်းစေလိုက်ခြင်းဖြစ်ပါသည်။ 

Plot ဥပမာ
----------

Plot များဖန်တီးရန် အောက်ဖော်ပြပါ script အတိုင်း ``##output_plots_to_html`` parameter ကို အသုံးပြုရပါမည်-

::

  ##Basic statistics=group
  ##Layer=vector
  ##Field=Field Layer
  ##output_plots_to_html
  ####output_plots_to_html
  qqnorm(Layer[[Field]])
  qqline(Layer[[Field]])

Script သည် input အနေဖြင့် vector layer (``Layer``) တစ်ခု၏ field (``Field``) တစ်ခုကို အသုံးပြုပြီး *QQ Plot* တစ်ခုကို ဖန်တီးပေးပါသည်။ (ပြန့်နှံ့မှု ပုံမှန်ဖြစ်မဖြစ် (Normality of the distribution) ကို စမ်းသပ်ရန်)

Processing *Result Viewer* ထဲတွင် plot ကို အလိုအလျောက်ထည့်သွင်းပေးသွားပါသည်။