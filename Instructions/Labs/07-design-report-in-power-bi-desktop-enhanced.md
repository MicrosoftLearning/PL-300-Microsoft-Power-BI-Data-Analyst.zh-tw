---
lab:
  title: 在 Power BI Desktop 中增強報表
  module: Create Reports in Power BI desktop
---


# 在 Power BI Desktop 中增強報表

## **實驗室案例**

在此實驗室中，您將使用進階設計功能來增強 ** 銷售分析 ** 。

在此實驗室中，您將了解如何：

- 同步交叉分析篩選器
- 建立鑽研頁面
- 套用條件式格式設定
- 建立和使用書籤

**此實驗室大約需要 45 分鐘的時間。**

## **開始使用 – 登入**

在這項工作中，您會登入 Power BI 來設定實驗室的環境。

*注意：如果您已經登入 Power BI，請跳至下一個工作。*

1. 若要開啟 Microsoft Edge，請選取工作列上的 Microsoft Edge 程式捷徑。

     ![圖 12](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image1.png)

1. 在 Microsoft Edge 瀏覽器視窗中，瀏覽至 **https://app.powerbi.com**。

    *提示：您也可以在 Microsoft Edge 我的最愛列上使用 Power BI 服務我的最愛。*

1. 使用組織認證完成登入程式（或提供給您的認證）。 若 Microsoft Edge 提示您保持登入，請選取 [是]****。

1. 在 Microsoft Edge 瀏覽器視窗中，從 Power BI 服務的 [瀏覽]**** 窗格，展開 [我的工作區]****。 讓 Microsoft Edge 瀏覽器視窗保持開啟。

     ![圖 22](Linked_image_Files/07-my-workspace-new.png)

## **開始使用 – 開啟報表**

在這項工作中，您將開啟入門報表來設定實驗室的環境。

*重要事項：如果您繼續執行先前的實驗室（且您已成功完成該實驗室），請勿完成這項工作;請改為跳至下一個工作。*

1. 開啟 Power BI Desktop。

    ![Power BI Desktop 圖示](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

    *提示：根據預設，[使用者入門] 對話方塊會在 Power BI Desktop 前面開啟。您可以選擇登入，然後關閉快顯。*

1. 若要開啟入門 Power BI Desktop 檔案，請選取 ** [檔案] > [開啟報表] > [流覽報表 ** ]。

1. 在 [ ** 開啟] ** 視窗中，流覽至 ** D：\PL300\Labs\07-design-report-in-power-bi-desktop-enhanced\Starter ** 資料夾，然後開啟 ** [銷售分析 ** ] 檔案。

1. 關閉任何可能開啟的資訊視窗。

1. 注意功能區下方的黃色警告訊息。

    *此訊息會提醒您查詢尚未套用為模型資料表載入的事實。您稍後會在此實驗室中套用查詢。*

    *若要關閉警告訊息，請在黃色警告訊息右側選取 ** [X ** ]。*

1. 若要建立檔案的複本，請移至 [檔案] > [ ** 另存新 ** 檔]，然後儲存至 ** D：\PL300\MySolution ** 資料夾。

1. 如果系統提示您套用變更，請選取 [稍後套用]****。

## **同步交叉分析篩選器**

在這項工作中 ** ，您將同步處理 Year ** 和 ** Region ** 交叉分析篩選器，繼續開發在 Power BI Desktop ** 實驗室中 ** 設計報表中建立的報表。

1. 在 Power BI Desktop 的 [概觀]**** 頁面上，將 [年度]**** 交叉分析篩選器設定為 [FY2018]****。

1. 移至 [我的效能]**** 頁面，然後注意 [年度]**** 交叉分析篩選器是不同的值。

    *當交叉分析篩選器未同步處理時，可能會造成報表使用者的資料歪曲和挫折。您現在會同步處理報表交叉分析篩選器。*

1. 返回 [概觀]**** 頁面，然後選取 [年度]**** 交叉分析篩選器。

1. 在 [檢視]**** 功能區索引標籤上，從 [顯示窗格]**** 群組中，選取 [同步交叉分析篩選器]****。

     ![圖片 1](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image13.png)

1. 在 [同步交叉分析篩選器]**** 窗格的 (位於 [視覺效果]**** 窗格的左側) 的第二個資料行 (代表同步處理) 中，勾選 [概觀]**** 和 [我的效能]**** 頁面的核取方塊。

     ![圖片 93](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image14.png)

1. 在 [概觀]**** 頁面上，選取 [區域]**** 交叉分析篩選器。

1. 同步處理交叉分析篩選器與 [概觀]**** 和 [利潤]**** 頁面。

     ![圖片 94](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image15.png)

1. 選取不同的篩選選項，然後驗證已同步的交叉分析篩選器是否依相同的選項篩選，以測試同步交叉分析篩選器。

1. 若要關閉 [同步交叉分析篩選器]**** 頁面，請選取窗格右上角的 [X]****。

## **設定鑽研**

在此練習中，您將建立新的頁面，並將其設定為鑽研頁面。 當您完成設計時，此頁面會如下所示：

![新頁面的影像，其中包含一個卡片視覺效果和資料表視覺效果。](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image17.png)

## **建立鑽研頁面**

在這項工作中，您將建立新的頁面，並將其設定為鑽研頁面。

1. 新增名為 [產品詳細資料]**** 的新報告頁面。

1. 以滑鼠右鍵按一下 [產品詳細資料]**** 頁面索引標籤，然後選取 [隱藏頁面]****。

    *報表使用者無法直接前往鑽研頁面。他們需要從其他頁面上的視覺效果存取它。您將瞭解如何在此實驗室的最後一個練習中鑽研至頁面。*

1. 在 [視覺效果]**** 窗格下方的 [鑽研]**** 區段中，將 [Product \| Category]**** 欄位新增至 [在此處新增鑽研欄位]**** 方塊。

    *實驗室會使用速記標記法來參考欄位。看起來會像這樣： ** 產品 \| 類別 ** 。在此範例中， ** Product ** 是資料表名稱，而 ** Category ** 是功能變數名稱。*

     ![圖片 96](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image20.png)

1. 若要測試鑽研頁面，請在鑽研篩選卡片中選取 [自行車]****。

     ![圖片 99](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image21.png)

1. 在報告頁面的左上方，注意箭號按鈕。

    *當欄位新增至鑽研井/區域時，會自動新增箭頭按鈕。它可讓報表使用者巡覽回他們鑽研的頁面。*

1. 在頁面中新增 [卡片]**** 視覺效果，然後調整其大小和位置，使其位於按鈕的右邊並填滿頁面的剩餘寬度。

    ![圖片 13](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image23.png)

    ![圖片 101](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image24.png)

1. 將 [Product \| Category]**** 欄位拖曳到卡片視覺效果中。

1. 設定視覺效果的格式選項，然後將 [類別標籤]**** 屬性切換為 [關閉]****。

     ![圖片 103](Linked_image_Files/07-design-report-in-power-bi-desktop_image36b.png)

1. 將 ** Effects > Background ** 色彩屬性設定為淺灰色陰影，例如 * 白色，20% 較 * 深。

     ![圖片 103](Linked_image_Files/07-design-report-in-power-bi-desktop_image36c.png)

1. 在頁面中新增 [資料表]**** 視覺效果，然後調整其大小和位置，使其位於卡片視覺效果的下方並填滿頁面的剩餘空間。

     ![圖片 14](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image26.png)

     ![圖片 105](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image27.png)

1. 將下列欄位新增至視覺效果：

     - Product \| Subcategory
     - Product \| Color
     - Sales \| Quantity
     - Sales \| Sales
     - Sales \| Profit Margin

1. 設定視覺效果的格式選項，然後在 [值]**** 區段中，將 [文字大小]**** 屬性設為 [20pt]****。

*鑽研頁面的設計幾乎已完成。您將在下一個練習中使用條件式格式設定來增強頁面。*

## **新增條件式格式設定**

在此練習中，您將使用條件式格式設定來增強鑽研頁面。 當您完成設計時，此頁面會如下所示：

![已更新頁面的影像，顯示色彩格式化的值和圖示。](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image28.png)

## **新增條件式格式設定**

在這項工作中，您將使用條件式格式設定來增強鑽研頁面。

1. 選取資料表視覺效果。 在視覺效果窗格中，選取 [利潤邊界] 值上的 ** 向下箭號，然後選取 [ ** 條件式格式設定 \| 圖示 ** ]。 **

    ![圖片 107](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image29.png)

1. 在 [圖示 – Profit Margin]**** 視窗的 [圖示版面配置]**** 下拉式清單中，選取 [資料右邊]****。

     ![圖片 108](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image30.png)

1. 若要刪除中間規則，請在黃色三角形右側選取 ** [X ** ]。

     ![圖片 109](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image31.png)

1. 設定第一個規則 (紅色菱形)，如下所示：

    - 在第二個控制項中，移除此值
    - 在第三個控制項中，選取 [數字]****
    - 在第五個控制項中，輸入 **0**
    - 在第六個控制項中，選取 [數字]****

1. 設定第二個規則 （綠色圓形），如下所示，然後選取 [ ** 確定 ** ]：

    *規則可以解釋如下：如果利潤率值小於 0，則顯示紅色菱形；否則，如果此值很大或等於零，則會顯示綠色圓形。*

     - 在第二個控制項中，輸入 **0**
     - 在第三個控制項中，選取 [數字]****
     - 在第五個控制項中，移除此值
     - 在第六個控制項中，選取 [數字]****

     ![圖片 110](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image32.png)

1. 在資料表視覺效果中，確認已顯示正確的圖示。

     ![圖片 112](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image34.png)

1. 設定 [色彩]**** 欄位的背景色彩條件式格式設定。

1. 在 [背景色彩 – 色彩]**** 視窗的 [設定樣式格式]**** 下拉式清單中，選取 [欄位值]****。

1. 在 [ ** 我們應該以此為基礎的哪些欄位？ ** ] 下拉式清單中，選取 [產品 \| 格式 \| 設定背景色彩格式 ** ]，然後選取 ** [ ** 確定 ** ]。

     ![圖片 114](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image36.png)

1. 重複上述步驟，以使用 [Product \| 格式設定 \| 字型色彩格式]**** 欄位，設定 [色彩]**** 欄位的字型色彩條件式格式設定

*您可能還記得，背景和字型色彩是來自《在 Power BI Desktop 中準備資料》**** 實驗室的 **ColorFormats.csv** 檔案，再將其與《在 Power BI Desktop 中載入資料》**** 實驗室的 **Product** 查詢整合。*

## **新增書簽和按鈕**

在此練習中，您將使用按鈕來增強 ** [我的效能] ** 頁面，讓報表使用者選取要顯示的視覺效果類型。 當您完成設計時，此頁面會如下所示：

![已更新之第 3 頁的影像，其顯示兩個按鈕，且現在只有兩個視覺效果。](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image38.png)

## **新增書簽**

在這項工作中，您將新增兩個書簽，一個用來顯示每個每月銷售/目標視覺效果。

1. 移至 [我的效能]**** 頁面。 在 [檢視]**** 功能區索引標籤上，從 [顯示窗格]**** 群組中，選取 [書籤]****。

     ![圖片 118](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image39.png)

1. 在 [檢視]**** 功能區索引標籤上，從 [顯示窗格]**** 群組中，選取 [選取範圍]****。

1. 在 [選取範圍]**** 窗格中，選取 [依月份的銷售額] 和 [依月份的目標]**** 項目旁邊的眼睛圖示，以隱藏視覺效果。

     ![圖片 120](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image41.png)

1. 在 [書籤]**** 窗格中，選取 [新增]****。

    *若要重新命名書簽，請按兩下書簽。*

     ![圖片 121](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image42.png)

1. 如果可見的圖表是橫條圖，請將書籤重新命名為 [開啟橫條圖]****，否則將書籤重新命名為 [開啟直條圖]****。

1. 若要編輯書簽，請在 ** [書簽 ** ] 窗格中，將游標暫留在書簽上方，選取省略號，然後選取 [ ** 資料 ** ]。
     
     *停用 [ ** 資料] ** 選項表示書簽不會使用目前的篩選狀態。這很重要，因為書簽會永久鎖定 Year ** 交叉分析篩選器目前套用的 ** 篩選。*

     ![圖片 16](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image43.png)

1. 若要更新書簽，請再次選取省略號，然後選取 [ ** 更新 ** ]。

     *在下列步驟中，您將建立並設定第二個書簽以顯示第二個視覺效果。*

1. 在 [選取範圍]**** 窗格中，切換 [依月份的銷售額] 和 [依月份的目標]**** 兩個項目的可見度。

     *換句話說，讓可見的視覺效果隱藏，並讓隱藏的視覺效果可見。*

     ![圖片 122](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image45.png)

1. 建立第二個書籤並適當地命名 ([開啟直條圖]**** 或 [開啟橫條圖]**)**。

     ![圖片 123](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image46.png)

1. 設定第二個書籤以忽略篩選 ([資料]**** 選項關閉)，並更新書籤。

1. 在 [選取範圍]**** 窗格中，若要讓這兩個視覺效果均可見，只要顯示隱藏的視覺效果即可。

1. 調整這兩個視覺效果的大小和位置，使其填滿多張卡片視覺效果下方的頁面，且彼此完全重疊。

    *若要選取涵蓋的視覺效果，請在 [選取範圍 ** ] 窗格中加以選取 ** 。*

    ![圖片 124](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image47.png)

1. 在 [書籤]**** 窗格中，選取每個書籤，並注意只有其中一個視覺效果看得見。

*下一個階段的設計是將兩個按鈕新增至頁面，這可讓報表使用者選取書簽。*

## **新增按鈕**

在此工作中，您將新增兩個按鈕，並將書簽動作指派給每個按鈕。

1. 在 [插入]**** 功能區中，從 [元素]**** 群組中，選取 [按鈕]****，然後選取 [空白]****。

     ![圖片 125](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image48.png)

1. 將此按鈕放置在 [年度]**** 交叉分析篩選器的正下方。

1. 選取按鈕，然後在 ** [格式] 按鈕 ** 窗格中，選取 ** [按鈕 ** ]，展開 ** [樣式 ** ] 區段， ** 然後將 [文字 ** ] 屬性 ** ** 開啟。

     ![圖片 126](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image49b.png)

1. 展開 [ ** 文字 ** ] 區段，然後在 [文字方塊 ** ] 中 ** 輸入 ** 橫條圖 ** 。

1. **展開 [填滿] ** 區段，然後使用互補色彩設定填滿色彩。

1. 選取 ** [按鈕 ** ]， ** 然後將 [動作 ** ] 屬性 ** ** 開啟。

    ![圖片 127](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image50.png)

1. 展開 [動作]**** 區段，然後將 [類型]**** 下拉式清單設定為 [書籤]****。

1. 在 [書籤]**** 下拉式清單中，選取 [開啟橫條圖]****。

    ![圖片 128](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image51.png)

1. 使用複製並貼上來建立按鈕的複本，然後設定新按鈕，如下所示：

    *提示：複製和貼上的快捷方式命令為 ** Ctrl+C ** ， ** 後面接著 Ctrl+V ** 。*

    - 將 [按鈕文字]**** 屬性設定為 [直條圖]****
    - 在 [動作]**** 區段中，將 [書籤]**** 下拉式清單設定為 [開啟直條圖]****

*銷售分析報表的設計現已完成。*

## **發佈報表**

在這項工作中，您將發佈報表。

1. 選取 [概觀]**** 頁面。

1. 在 [年度]**** 交叉分析篩選器中，選取 [FY2020]****。

1. 在 [區域]**** 交叉分析篩選器中，選取 [全選]****。

1. 儲存 Power BI Desktop 檔案。

    *發行至Power BI 服務之前，必須先儲存檔案。*

1. 在 [首頁]**** 功能區索引標籤上，從 [共用]**** 群組內選取 [發佈]****。

     ![圖 21](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image52.png)

1. 請注意，在 [發佈至 Power BI]**** 視窗中已選取 [我的工作區]****。

1. 若要發佈報表，請選取 [ ** 選取 ** ]。
    1. 當系統提示您取代資料集時，請選取 [取代]****。
    1. 當發佈成功時，請選取 [確認]****。

1. 關閉 Power BI Desktop。

*您將在下一個練習的Power BI 服務中探索報表。*

## **探索報表**

在這項工作中，您將探索Power BI 服務中的報表。

1. 在 Microsoft Edge 瀏覽器視窗中，流覽至 [我的工作區] Power BI 服務 > ** ，然後選取 ** [銷售分析 ** ] ** 報表。

1. 若要測試鑽研功能，請流覽至 ** ** [概觀] 頁面，> ** [依類別 ** 排序的數量] 視覺效果。 然後以 ** 滑鼠右鍵按一下 [服裝 ** ] 列，然後選取 ** [鑽研 \| 產品詳細資料 ** ]。

     ![圖片 130](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image55.png)

1. 請注意，[產品詳細資料]**** 頁面適用於 [服裝]****。

1. 若要返回來源頁面，請在頁面左上角選取箭號按鈕。

1. 選取 [我的效能]**** 頁面。

    *選取每個按鈕，然後注意到會顯示不同的視覺效果。*

### **完成時間**

在此工作中，您將完成實驗室。

若要返回工作區，請在視窗網頁的橫幅中，選取 ** [我的工作區 ** ]。

![圖 23](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image56.png)