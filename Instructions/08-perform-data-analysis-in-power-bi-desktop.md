---
lab:
  title: 使用 AI 視覺效果執行進階分析
  module: Perform Data Analysis in Power BI
---


# **在 Power BI 中執行資料分析**

## **實驗室案例**

在此實驗室中，您將建立**銷售探索**報表。

在此實驗室中，您將了解如何：

- 建立動畫散佈圖
- 使用視覺效果來預測值

**此實驗室大約需要 30 分鐘的時間。**

## **開始使用 – 登入**

在這項工作中，您將藉由登入 Power BI 來設定實驗室的環境。

*注意：如果您已經登入 Power BI，請跳至下一個工作。*

1. 若要開啟 Microsoft Edge，請選取工作列上的 Microsoft Edge 程式捷徑。

     ![圖 12](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image1.png)

1. 在 Microsoft Edge 瀏覽器視窗中，瀏覽至 **https://app.powerbi.com**。

    *提示：您也可以使用 Microsoft Edge [我的最愛] 列上的 [Power BI 服務] 我的最愛項目。*

1. 使用您的組織 (或提供) 認證來完成登入程式。 如果 Microsoft Edge 提示您保持登入，請選取 [是]。

1. 在 Microsoft Edge 瀏覽器視窗中，從 Power BI 服務的 [瀏覽] 窗格，展開 [我的工作區]。 讓 Microsoft Edge 瀏覽器視窗保持開啟。

     ![圖 22](Linked_image_Files/07-my-workspace-new.png)

## **開始使用 – 建立資料集**

在這項工作中，您將藉由建立資料集來設定實驗室的環境。 *如果您已經發佈資料集，請移至下一個工作。*

1. 在 Microsoft Edge 瀏覽器視窗中的 [Power BI 服務] 中，流覽至 **[我的工作區**]。

1. 選取 **[上傳>流覽**]。

1. 流覽至 **D：\PL300\Labs\08-perform-data-analysis-in-power-bi-desktop\Starter** 資料夾。

1. 選取 **Sales Analysis.pbix** 檔案，然後選取 [開啟]。

    *如果系統提示您取代資料集，請選取 [ **取代資料集**]。*

*這個方法會建立報表和資料集。我們只會使用此資料集在此練習中建立新的報表。這個相同的程式可以使用不同報表中的現有資料集來完成，而不是上傳新的資料集。此外，如果您未使用報表，工作區最佳做法會建議您刪除不必要的檔案。*

## **建立報表**

在這項工作中，您將建立與上一個工作中建立之 Power BI 資料集的即時連線，然後建立新的 **銷售探索** 報表。

1. 開啟 Power BI Desktop。

    ![Power BI Desktop圖示](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

    *重要：如果您已開啟 (來自先前實驗室的) Power BI Desktop，請關閉該執行個體。*

    *提示：根據預設，[消費者入門] 對話方塊會在Power BI Desktop前面開啟。您可以選擇登入，然後關閉快顯。*

1. 在 [首頁] 功能區中，選取 [ **取得資料> Power BI 資料集**]。

1. 在 [**資料中樞**] 視窗中，選取 **[我的工作區**] 中的 **[銷售分析**] 資料集 **，然後按一下或**按兩下以載入資料集。

1. 流覽至 **[檔案] > [儲存**] 並將檔案名儲存為**D：\PL300\MySolution**資料夾中**的銷售探索**。

*您現在將會建立兩個報表頁面，並在每個頁面上使用不同的視覺效果來分析及探索資料。*

## **建立動畫散佈圖**

在此工作中，您將建立能夠以動畫方式顯示的散佈圖。

1. 將**第 1 頁**重新命名為**散佈圖**。

1. 將 [散佈圖] 視覺效果新增至報表頁面，然後調整視覺效果的位置及大小，使其填滿整個頁面。
    
    *將欄位新增至 [播放軸] 區域時，此圖表就能以動畫方式顯示。*

     ![圖 18](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image15.png)

     ![圖片 75](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image16.png)

1. 將下列欄位新增至視覺效果區域：
    
    *實驗室會使用簡短標記法來參考欄位。看起來會像這樣： **轉銷商** **\|** **商務類型**。在此範例中， **Reseller** 是資料表名稱， **而商務類型** 是功能變數名稱。*

     - X 軸：**Sales \| Sales**
     - Y 軸：**Sales \| Profit Margin**
     - 圖例：**Reseller \| Business Type**
     - 大小：**Sales \| Quantity**
     - 播放軸：**Date \| Quarter**

1. 在 [篩選] 窗格中，將 [Product \| Category] 欄位新增至 [此頁面上的篩選] 區域。

1. 在篩選卡片中，依 [自行車] 進行篩選。

1. 若要讓圖表產生動畫效果，請選取左下角的 **[播放**]。

    ![圖 41](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image19.png)

1. 監看從 **FY2018 Q1** 到 **FY2020 Q4** 的整個動畫週期。
    
    *散佈圖可供同時了解量值：在本案例中為訂單數量、銷售營收和獲利率。*
    
    *每個泡泡都代表轉銷商商務類型。泡泡大小變化則反映增加或減少的訂單數量。水平移動表示銷售營收增加/減少，而垂直移動表示獲利率增加/減少。*

1. 當動畫停止時，選取其中一個泡泡可顯示一段時間的追蹤。

1. 將游標暫留在任何泡泡上方，以顯示工具提示，描述該時間點的轉銷商類型量值。

1. 在 [篩選] 窗格中，僅依 [服裝] 進行篩選，請注意其產生的結果完全不同。

1. 儲存 Power BI Desktop 檔案。


## **建立預測**

在這項工作中，您將建立預測，以判斷未來的銷售營收。

1. 新增頁面，然後將此頁面重新命名為**預測**。

1. 將 [折線圖] 視覺效果新增至報表頁面，然後調整視覺效果的位置及大小，使其填滿整個頁面。

     ![圖 19](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image21.png)

     ![圖片 74](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image22.png)

1. 將下列欄位新增至視覺效果區域：

     - X 軸：**Date \| Date**
     - Y 軸：**Sales \| Sales**

1. 在 [篩選] 窗格中，將 [Date \| Year] 欄位新增至 [此頁面上的篩選] 區域。

1. 在篩選卡片中，依兩年進行篩選：**FY2019** 和 **FY2020**。
    
    *在一段時間內預測時，您需要至少兩個週期 (年的資料) ，才能產生精確的穩定預測。*

1. 同時將 [Product \| Category] 欄位新增至 [此頁面上的篩選] 區域，並依 [Bikes] 進行篩選。

1. 若要新增預測，請在 [視覺效果] 窗格底下，選取**分析**窗格。

     ![圖 20](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image26.png)

8. 展開 [預測] 區段。
    
    *如果 [ **預測]** 區段無法使用，可能是因為視覺效果尚未正確設定。只有在符合兩個條件時，才會提供預測：軸具有日期類型的單一欄位，而且只有一個值欄位。*

1. 將 [預測] 選項切換為 [開啟]。

1. 設定下列預測屬性，然後 **套用**：

    - 單位： **月**
    - 預測長度： **1 個月**
    - 季節性： **365**
    - 信賴區間： **80%**

    ![圖片 52](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image29.png)

1. 在折線圖視覺效果中，請注意，預測已超出歷程記錄資料一個月。
    
    *灰色區域代表信賴度。信賴度越廣，穩定性就越差，因此預測的準確性可能會越差。*
    
    *當知道週期的長度時 (在本案例中為年度)，則應該輸入季節性點。有時可能是每週 (7)，有時可能是每月 (30)。*

1. 在 [篩選] 窗格中，僅依 [服裝] 進行篩選，請注意其將產生不同的結果。

### **完成**

在這項工作中，您將完成Power BI Desktop中的實驗室。

1. 選取 [散佈圖] 頁面。

1. 儲存 Power BI Desktop 檔案。

1. 若要將檔案發佈至 **我的工作區**，請在 [ **首頁** ] 功能區索引標籤的 **[共用** ] 群組內，選取 [ **發佈** ]，然後選取 [ **選取** 以發佈]。

    ![圖 23](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image46.png)

1. 關閉 Power BI Desktop。
