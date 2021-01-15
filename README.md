# Spatial-Analyst

## 
* 條件分析：在輸入圖層中設定條件，進一步去控制輸出圖層的數值。而這些條件可以利用屬性查詢，或是以在條件陳述狀態下的條件來設定。
* 距離分析：以各樣本點為基準，藉由不同的演算法，分別計算各像元與最近樣本點之間的距離關係、配置情形及方向。
* 密度分析：可對某個觀測現象的已知量進行分析，並依其所在位置的空間關聯性，將預測的分佈狀況分散至整個平面上的一種分析方式。
* 內插計算：內插計算提供使用者，可利用空間中的樣點資料，來推估其他未知區域的相關數據。
* 地表分析：主要透過對於地表高程的深入分析，獲取如等值線、坡度、坡向等額外的附加資訊。
* 水文分析：用於輔助使用者建立地表逕流模型。配合數值高程模型，可單獨或依序使用此模組分析獲取地表逕流模型之水流方向、累積流量，作為相關進階應用（區域規劃、農業、林業）的基礎。
* 局部分析：以輸出圖層中每一網格數值為輸入數值的函數之概念去做運算。當使用者在計算局部分析時，可以合併輸入圖層、計算統計值、或是在多張輸入圖層中設定條件數值，去求得輸出網格數值。
* 鄰域分析：以每一像元位置的數值和特定鄰域中辨識出來的數值為基礎，針對每一網格位置去建立輸出值。
* 區域分析：拿一張網格圖層作為輸入來源，藉用連續、相同的像元數值or量化輸入區域的幾何特徵來劃分區域，並加以計算、統計的分析方式。
* 概括化分析：將過於瑣碎或繁雜的資訊，藉由不同的遮罩及演算法，略去枝微末節，並將之歸併精簡的方式。
* 抽出分析：可藉由像元數值或其空間位置，來抽出一組子集網格，類似網格式資料的裁切功能。
* 重分類：為了簡化或合併某些類別而將網格中不同的像元數值歸為同一類；或是將多個像元數據按照敏感度、優先權等，藉由統一的類別級距，重新進行分類。
* 網格計算：提供使用者在執行多項任務時，能同時針對不同的影像圖層，進行數學方程式的邏輯運算，使原本的多張影像圖層，轉變為另一張影像圖層資料。
 
# GPS vs. LBS
* GPS (Global Positioning System，全球定位系統)
  * 優點：
    * 定位精確，誤差在5米以內的定位
  * 缺點：
    * 只有在能看得到天空的地方接收信號，其他地方比如高樓密集的城市、高架橋下、室內等無法接收到GPS信號或者是信號很差
    * 容易受天氣影響
* LBS (Location Based Service，移動位置服務)：基站定位，它是通過電信移動運營商的網絡 (如GSM網) 獲取移動終端用戶的位置信息(經緯度坐標)
  * 優點：
    * 方便、成本低，理論上，計算三個基站的信號差異，就可以判斷出該設備所在的位置，而不受天氣、高樓、位置等影響
  * 缺點：
    * 定位精度不及GPS
    * 使用範圍較窄
    * 定位精度隨所處位置基站數不同會有變化，基站數越大，誤差越小




## 參考資料
* http://www.geog.ucsb.edu/~sgao/data/SpatialDataAnalysisPython.pdf
* GPS vs. LBS：https://kknews.cc/zh-tw/tech/pxx3pze.html
