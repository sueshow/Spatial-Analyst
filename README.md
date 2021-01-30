# Spatial-Analyst

## 發展
* GIS (地理資訊系統)
* GPS (全球定位系統)：讓地面位置發出電磁波後，透過已知位置的衛星接收電磁波的時間，來推算他們之間的距離，而只要有了四顆衛星接收到距離資訊並回傳後，就能夠用地面點與衛星之間的方位與距離，推算出地面點的實際座標位置
* RS (Remote Sensing，遙測)：透過衛星影像接受到地表反射出的光與電磁波，不僅能夠單純紀錄平面的地表影像，還能夠利用這些不同波長、反射角度的光進行計算，不僅能夠計算出地表的起伏、土地利用型態、植被茂密程度等等特徵，而且，由於衛星的繞行是週期性的，又能夠在短時間獲取大範圍的資訊，比起過去的航照圖之外，更能夠長期監控同一區域的地表特徵，也能夠透過GIS來進行大尺度的空間分析
<br>

## 方法
* 視覺化處理 (Visualization) 
* 空間探索分析 (Exploratory Spatial Data Analysis)
  * 工具：主題圖、直方圖、盒狀圖、散佈圖、PCP (parallel coordinate plot) 圖 (用於顯示各地區在不同時間點、或不
同變數間的排名變化情形)、Moran’s I 散佈圖、LISA (Local Indicator of Spatial Association) 地區自相關分析
  * 重要概念：空間自相關 (vs 樣本獨立)、空間異質性 (vs 誤差變異) 
* 空間計量或空間迴歸模型 (Spatial Modeling/Regression)
  * 空間統計 (Spatial Statistic)：描述資料的空間特性
  * 空間計量 (Spatial Econometrics)：建立迴歸模型，探討自變數與因變數間的關係或影響程度
    * 空間變數使用消除誤差的自相關
    * 模型估計捨棄傳統慣用的最小平方法，以最大概似法替代之
    * 個別自變數顯著檢定，代之以Wald test
    * 總體適合度方面常用：Log likelihood (愈大愈好)、Akaike Info Criterion (愈小愈好)、Schwarz Criterion(愈小愈好)
<br>

## 分析
* 條件分析：在輸入圖層中設定條件，進一步去控制輸出圖層的數值。而這些條件可以利用屬性查詢，或是以在條件陳述狀態下的條件來設定。
* 距離分析：以各樣本點為基準，藉由不同的演算法，分別計算各像元與最近樣本點之間的距離關係、配置情形及方向。
* 密度分析：可對某個觀測現象的已知量進行分析，並依其所在位置的空間關聯性，將預測的分佈狀況分散至整個平面上的一種分析方式。
* 內插計算：內插計算提供使用者，可利用空間中的樣點資料，來推估其他未知區域的相關數據。
* 地表分析：主要透過對於地表高程的深入分析，獲取如等值線、坡度、坡向等額外的附加資訊。
* 水文分析：用於輔助使用者建立地表逕流模型。配合數值高程模型，可單獨或依序使用此模組分析獲取地表逕流模型之水流方向、累積流量，作為相關進階應用 (區域規劃、農業、林業) 的基礎。
* 局部分析：以輸出圖層中每一網格數值為輸入數值的函數之概念去做運算。當使用者在計算局部分析時，可以合併輸入圖層、計算統計值、或是在多張輸入圖層中設定條件數值，去求得輸出網格數值。
* 鄰域分析：以每一像元位置的數值和特定鄰域中辨識出來的數值為基礎，針對每一網格位置去建立輸出值。
* 區域分析：拿一張網格圖層作為輸入來源，藉用連續、相同的像元數值or量化輸入區域的幾何特徵來劃分區域，並加以計算、統計的分析方式。
* 概括化分析：將過於瑣碎或繁雜的資訊，藉由不同的遮罩及演算法，略去枝微末節，並將之歸併精簡的方式。
* 抽出分析：可藉由像元數值或其空間位置，來抽出一組子集網格，類似網格式資料的裁切功能。
* 重分類：為了簡化或合併某些類別而將網格中不同的像元數值歸為同一類；或是將多個像元數據按照敏感度、優先權等，藉由統一的類別級距，重新進行分類。
* 網格計算：提供使用者在執行多項任務時，能同時針對不同的影像圖層，進行數學方程式的邏輯運算，使原本的多張影像圖層，轉變為另一張影像圖層資料。
<br> 


# GPS vs. LBS
* GPS (Global Positioning System，全球定位系統)
  * 優點：
    * 定位精確，誤差在5米以內的定位
    * 應用主要進行車載定位
  * 缺點：
    * 只有在能看得到天空的地方接收信號，其他地方比如高樓密集的城市、高架橋下、室內等無法接收到GPS信號或者是信號很差
    * 容易受天氣影響
  * 業務市場
    * 防止車輛的丟失
    * 很多車輛被政府部門強制安裝GPS車載定位系統 (比如長途客運車輛、很多大中城市的出租汽車、或者特殊行業的特種車輛如消防車、運鈔車、危險品運輸車等等)
  * 計算方法
    * 觀測3個非共面且已知位置的衛星(利用星曆來確認衛星位置)，利用電碼的時間延遲來估算偽距
<br> 

* AGPS (Assisted GPS，輔助型GPS)
  * 介於 GPS 與 LBS 之間
  * 計算方法
    * 多個數據基地台來取得不同基地台的星曆、時間和距離，再加上都卜勒效應、頻率等多餘觀測量來同步檢核數據的精準性，最後得到的參數再利用 GPS 接收器求得該點位置
<br> 

* LBS (Location Based Service，移動位置服務)：基站定位，它是通過電信移動運營商的網絡 (如GSM網) 獲取移動終端用戶的位置信息(經緯度坐標)
  * 優點：
    * 方便、成本低，理論上，計算三個基站的信號差異，就可以判斷出該設備所在的位置，而不受天氣、高樓、位置等影響
  * 缺點：
    * 定位精度不及GPS
    * 使用範圍較窄，不太適合野外使用
    * 定位精度隨所處位置基站數不同會有變化，基站數越大，誤差越小
    * 受環境影響較大，市區會經過折射或反射，定位範圍為100～200米，響應時間在3～6s之間；郊區定位可在範圍為10～20米
    * 高速行使當中，基站如果切換太快反而影響定位效果
  * 業務市場
    * 手機位置的定位，即可提供手機持有者現在的具體位置。這種服務涉及到個人隱私
    * 服務場所的顯示。即通過手機定位，可以查找附近的各類服務場所（如酒店、餐廳以及其它特殊場所等），滿足用戶選擇的需要
    * 路線導航服務。即手機定位可以顯示出從A地至B地的最佳路線。這種服務方式已經類似於GPS的定位服務。但同樣涉及到地圖及數據更新問題，運營成本極高
    * 特殊定位服務。運營商製作出特涉的、小型化的定位終端，放在小孩、老人的身上，當他們超越規定的地理範圍時，就會向監護人發出告警，提醒引起注意
  * 原理
    * 指紋定位 (Fingerprint Positioning) 
    * 交遞信令 (Handoff) 定位 
    * 近場通訊 (Near Field Communication, NFC) 和射頻識別 (Radio Frequency Identification, RFID) 刷卡定位

* 定位方法
  * 全球定位系統
    * GPS
      * ![GPS](https://github.com/sueshow/Spatial-Analyst/blob/main/picture/GPS.JPG)
    * AGPS
      * ![AGPS](https://github.com/sueshow/Spatial-Analyst/blob/main/picture/AGPS.JPG)
    * LBS
  * 行動掃瞄報告  
    * 接收信號角度 (Angle of Arrival, AOA) 定位：利用具方向性的天線所量測的訊息，得出主動式標籤訊號的來源方向
      * ![AOA](https://github.com/sueshow/Spatial-Analyst/blob/main/picture/AOA.JPG)
    * 到達時間 (Time of Arrival, TOA) 定位：
      * 使用3個天線做定位時，主動式標籤和天線i (i=1, 2, 3...)的距離 ri 定義為 (ti-t0)ri，其中 t0 為讀取器開始發射到標籤的時間常數， t1 為天線訊號到達主動式標籤的時間，c 為光速
      * ![TOA](https://github.com/sueshow/Spatial-Analyst/blob/main/picture/TOA.png)
    * 到達時差 (Time Difference Of Arrivals, TDOA)定位 
      * ![TDOA](https://github.com/sueshow/Spatial-Analyst/blob/main/picture/TDOA.JPG)
    * 接收訊號強度定位
      * 透過訊號強度和已知的頻道衰弱模型來估計參考點與待測點的距離，根據多個距離值就可以利用類似TOA定位法原理得到待測點的位置
      * 公式
      RSSI = 10 * log(\frac{P_r}{P_ref}) where \P_r 為接收功率(dB),\P_ref 為1mW
      * ![接收功率(實際 vs 理論)](https://github.com/sueshow/Spatial-Analyst/blob/main/picture/%E6%8E%A5%E6%94%B6%E8%A8%8A%E8%99%9F%E5%BC%B7%E5%BA%A6%E5%AE%9A%E4%BD%8D.JPG)
  * 資料庫查詢
    * 細胞識別碼(Cell Id)定位：利用3組具方向性且各佔120度的天線，以基地台為中心，來搜尋巢狀內的使用者用戶位置
      * 完整的 Cell-ID 包含 MCC(Mobile Country Code，移動國家代碼) + MNC (Mobile Network Code，行動網路號碼) + LAC (Location Area Identity，地區識別碼) + CI (Cell Identity，基地台識別碼)
      * Location Area 由 LAI（Location Area Id）來標識，LAI 由 MCC、MNC、LAC 組成，其中 MCC 是 3 位的 Mobile Country Code，中國為460；MNC 是 2 位 Mobile Network Code，在國家內分配，中國移動為00，中國聯通為01，中國電信為02；LAC 為 Location Area Code，在 network 內分配；可見 LAI 是全世界唯一的
      * 在一個location area中設置一個或多個基站，基站天線的信號覆蓋一定的區域，稱為cell（小區）；根據天線的不同，每個基站可能包含1個或多個cell，定向天線的 信號覆蓋一個扇形範圍，多個天線的扇區為不同的cell
      * BSSS (Base station signal strength)：基站信號強度
    * E-CID (Enhanced Cell ID)的定位方法，除了使用服務基地台的地理座標的資訊，同時利用量測的資訊，主要是：參考訊號功率 (Reference Signal Received Power，RSRP)，或者到達時間差 (TDOA) 和時間前置 (Timing Advance，TADV) 的量測，或者來回時間 (Round Trip Time，RTT) 來估測使用者終端與基地台之間的距離，甚至可以利用到達角度 (Angle-of-Arrival，AoA) 的資訊來進行定位
<br>

## 參考資料
* http://www.geog.ucsb.edu/~sgao/data/SpatialDataAnalysisPython.pdf
* GPS vs. LBS：https://kknews.cc/zh-tw/tech/pxx3pze.html
* 中華電信：https://tp2rc.tanet.edu.tw/node/80
* https://huenlil.pixnet.net/blog/post/24194408
* E-CID：https://note-on-clouds.blogspot.com/2016/10/lte-positioning-3-ecid.html
* http://homepage.ntu.edu.tw/~ntuccs/uploads/research/paper-11.pdf
* 空間分析模組簡介：https://www.supergeotek.com/tw/manuals/SA/ch1_1.htm
