---
lab:
  title: 增強 Power BI 報表設計
  module: Enhance Power BI report designs for the user experience
---

# 增強 Power BI 報表設計

## 實驗室案例

在此實驗室中，您將使用進階設計功能來增強 _銷售分析_ 報表。

在此實驗室中，您會了解如何：

- 建立鑽研頁面。
- 套用條件式格式設定。
- 建立和使用書籤和按鈕。

**此實驗室大約需要45分鐘的時間。**

## 開始使用

若要完成此練習，請先開啟網頁瀏覽器，然後輸入下列 URL 以下載 zip 檔案：

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/09-enhance-power-bi-reports/09-enhanced-report.zip`

將檔案解壓縮到 **C：\Users\Student\Downloads\09-enhanced-report** 資料夾。

**開啟 09-Starter-Sales Analysis.pbix** 檔案。

> _**注意**：您可以選取 **[取消**] 來關閉登入。關閉任何其他信息視窗。如果系統提示您套用變更，請選取 [ **稍後**套用]。_

## 設定鑽研頁面

在此練習中，您將建立新的頁面，並將其設定為鑽研頁面。 當您完成設計時，此頁面會如下所示：

![新頁面的螢幕快照，其中包含卡片視覺效果和數據表視覺效果。](Linked_image_Files/09-enhance-power-bi-reports_image17.png)

1. 建立新的頁面，並將其重新命名為 _產品詳細數據_。

1. 以滑鼠右鍵按一下 [產品詳細資料]**** 頁面索引標籤，然後選取 [隱藏頁面]****。

    > _報表用戶無法直接前往鑽研頁面。相反地，他們會從其他頁面上的視覺效果存取它。您將瞭解如何在此實驗室的最後一個練習中鑽研至頁面。_

1. 在 [**視覺效果]** 窗格下方的 **[鑽研**] 區段中，將字段新增`Product | Category`至此處**的 **[新增鑽研字段] 方塊。

    > _實驗室會使用速記表示法來參考欄位。看起來會像這樣： `Product | Category`。在此範例中， `Product` 是數據表名稱，而 `Category` 是功能變數名稱。_

    ![圖片 1](Linked_image_Files/09-enhance-power-bi-reports_image20.png)

1. 若要測試鑽研頁面，請在鑽研篩選卡片中選取 [自行車]__。

    ![圖 2](Linked_image_Files/09-enhance-power-bi-reports_image21.png)

1. 在報表頁面的左上方，請注意箭頭按鈕。

    > _當欄位新增至鑽研井時，報表設計師會自動新增箭頭按鈕。它可讓報表用戶巡覽回他們鑽研的頁面。_

1. 在頁面中新增 [卡片]**** 視覺效果，然後調整其大小和位置，使其位於按鈕的右邊並填滿頁面的剩餘寬度。

    ![圖 3](Linked_image_Files/09-enhance-power-bi-reports_image23.png)

    ![圖片 4](Linked_image_Files/09-enhance-power-bi-reports_image24.png)

1. 將 `Product | Category` 欄位拖曳到卡片視覺效果中。

1. 設定視覺效果的格式選項，將 [類別卷標] 屬性設為 ****[關閉**]。**

    ![圖 5](Linked_image_Files/09-enhance-power-bi-reports_image36b.png)

1. 在 [一般 **] 索引標籤的 **[** 效果]** 區段中，將背景色彩屬性設定為淺灰色（例如_白色，10% 深色_）以提供對比。

    ![圖片 6](Linked_image_Files/09-enhance-power-bi-reports_image36c.png)

1. 在頁面中新增 [資料表]**** 視覺效果，然後調整其大小和位置，使其位於卡片視覺效果的下方並填滿頁面的剩餘空間。

    ![圖片 7](Linked_image_Files/09-enhance-power-bi-reports_image26.png)

    ![圖 8](Linked_image_Files/09-enhance-power-bi-reports_image27.png)

1. 將下列欄位新增至視覺效果：

    - `Product | Subcategory`
    - `Product | Color`
    - `Sales | Quantity`
    - `Sales | Sales`
    - `Sales | Profit Margin`

1. 若要設定視覺效果的格式選項，請在 **Grid** 區段中，將 **[全域字型大小]** 屬性設定為 **20pt**。

    > _鑽研頁面的設計幾乎已完成。您將在下一個練習中使用條件式格式設定來增強頁面。_

## 新增條件式格式設定

在此練習中，您將使用條件式格式設定來增強鑽研頁面。 當您完成設計時，此頁面會如下所示：

![已更新頁面的螢幕快照，其中顯示色彩格式化的值和圖示。](Linked_image_Files/09-enhance-power-bi-reports_image28.png)

1. 選取資料表視覺效果。 在 **[數據行**] 中，選取 [利潤邊界 **] 欄位中的向下箭號**，然後選取 **[條件式格式設定] > [圖示**]。

    ![圖 9](Linked_image_Files/09-enhance-power-bi-reports_image29.png)

1. 在 [圖示 – Profit Margin]**** 視窗的 [圖示版面配置]**** 下拉式清單中，選取 [資料右邊]****。

    ![圖片 11](Linked_image_Files/09-enhance-power-bi-reports_image30.png)

1. 若要刪除中間規則，請在黃色三角形右側選取 **[X**]。

    ![圖 12](Linked_image_Files/09-enhance-power-bi-reports_image31.png)

1. 設定第一個規則 (紅色菱形)，如下所示：

    - 在第二個控制項中，移除此值
    - 在第三個控制項中，選取 [數字]****
    - 在第五個控制項中，輸入 **0**
    - 在第六個控制項中，選取 [數字]****

1. 設定第二個規則 (綠色圓形)，如下所示：

    - 在第二個控制項中，輸入 **0**
    - 在第三個控制項中，選取 [數字]****
    - 在第五個控制項中，移除此值
    - 在第六個控制項中，選取 [數字]****

    ![圖片 13](Linked_image_Files/09-enhance-power-bi-reports_image32.png)

    > _規則可以解譯如下：如果獲利率值小於 0，則顯示紅色菱形;否則，如果值大於或等於零，則顯示綠色圓形。_

1. 在 [ **圖示 – 利潤邊界** ] 視窗的 **[套用至** ] 下拉式清單中，選取 **[值和總計**]。

    ![圖片 10](Linked_image_Files/09-enhance-power-bi-reports_image30a.png)

1. 選取 [確定]。

1. 在數據表視覺效果中，確認已顯示正確的圖示。

    ![圖片 14](Linked_image_Files/09-enhance-power-bi-reports_image34.png)

1. 設定 [色彩]**** 欄位的背景色彩條件式格式設定。

1. 在 [背景色彩 – 色彩]**** 視窗的 [設定樣式格式]**** 下拉式清單中，選取 [欄位值]****。

    ![圖片 15](Linked_image_Files/09-enhance-power-bi-reports_image36a.png)

1. 在 [ **我們應該根據哪一個字段？** ] 下拉式清單中，選取 _[所有數據_ ] 群組中的 `Product | Formatting | Background Color Format` 字段。

    ![圖片 16](Linked_image_Files/09-enhance-power-bi-reports_image36.png)

1. 重複上述步驟，使用 `Product | Formatting | Font Color Format` 字段來設定 [色彩 **] 欄位的**字型色彩條件式格式設定。

 > _您可能還記得背景和字型色彩來自 **Power BI Desktop** 實驗室中**準備數據的ColorFormats.csv**檔案，然後與 **Power BI Desktop** 實驗室中的 **[載入數據] 中的 [產品**] 查詢整合。_

## 新增書籤和按鈕

在此練習中，您將使用按鈕增強 _[我的效能]_ 頁面，讓報表用戶選取要顯示的視覺效果類型。 當您完成設計時，此頁面會如下所示：

![已更新第 3 頁的螢幕快照，其中顯示兩個按鈕，而現在只有兩個視覺效果。](Linked_image_Files/09-enhance-power-bi-reports_image38.png)

1. 移至 [我的效能]__ 頁面。

1. 在 [檢視]**** 功能區索引標籤上，從 [顯示窗格]**** 群組中，選取 [書籤]****。

    ![圖 17](Linked_image_Files/09-enhance-power-bi-reports_image39.png)

1. 在 [檢視]**** 功能區索引標籤上，從 [顯示窗格]**** 群組中，選取 [選取範圍]****。

    ![圖 18](Linked_image_Files/09-enhance-power-bi-reports_image40.png)

1. 在 [選取範圍]**** 窗格中，選取 [依月份的銷售額] 和 [依月份的目標]__ 項目旁邊的眼睛圖示，以隱藏視覺效果。

    ![圖 19](Linked_image_Files/09-enhance-power-bi-reports_image41.png)

1. 在 [書籤]**** 窗格中，選取 [新增]****。

    ![圖片 20](Linked_image_Files/09-enhance-power-bi-reports_image42.png)

    > _提示：若要重新命名書籤，請按兩下書籤。_

1. 如果可見的圖表是橫條圖，請將書籤重新命名為 [開啟橫條圖]__，否則將書籤重新命名為 [開啟直條圖]__。

1. 若要編輯書籤，請在 **[書籤** ] 窗格中，將游標暫留在書籤上方，選取省略號，然後選取 [ **數據**]。

    > _停用 [ **數據]** 選項表示書籤不會使用目前的篩選狀態。這很重要，因為書籤會永久鎖定 Year 交叉分析篩選器目前套用的篩選。_

    ![圖 21](Linked_image_Files/09-enhance-power-bi-reports_image43.png)

1. 若要更新書籤，請再次選取省略號，然後選取 [ **更新**]。

    > _在下列步驟中，您將建立並設定第二個書籤以顯示第二個視覺效果。_

1. 在 [選取範圍]**** 窗格中，切換 [依月份的銷售額] 和 [依月份的目標]__ 兩個項目的可見度。

    > _換句話說，讓可見的視覺效果隱藏，並讓隱藏的視覺效果可見。_

    ![圖 22](Linked_image_Files/09-enhance-power-bi-reports_image45.png)

1. 建立第二個書籤，並適當地命名它（ _柱形圖 ON_ 或 _條形圖 ON_。

    ![圖 23](Linked_image_Files/09-enhance-power-bi-reports_image46.png)

1. 設定第二個書籤以忽略篩選 ([資料]**** 選項關閉)，並更新書籤。

1. 在 [選取範圍]**** 窗格中，若要讓這兩個視覺效果均可見，只要顯示隱藏的視覺效果即可。

1. 調整這兩個視覺效果的大小和位置，使其填滿多張卡片視覺效果下方的頁面，且彼此完全重疊。

    > _若要選取涵蓋的視覺效果，請在 [選取範圍 **] 窗格中加以選取**。_

    ![圖 24](Linked_image_Files/09-enhance-power-bi-reports_image47.png)

1. 在 [書籤]**** 窗格中，選取每個書籤，並注意只有其中一個視覺效果看得見。

    > _下一個階段的設計是將兩個按鈕新增至頁面。這些按鈕可讓報表用戶選取書籤。_

1. 在 [插入]**** 功能區中，從 [元素]**** 群組中，選取 [按鈕]****，然後選取 [空白]****。

    ![圖 25](Linked_image_Files/09-enhance-power-bi-reports_image48.png)

1. 將此按鈕放置在 [年度]__ 交叉分析篩選器的正下方。

1. 選取按鈕，然後在 **[格式] 按鈕** 窗格中，展開 **[樣式** ] 區段，然後將 [ **文字** ] 區段設定為 **[開啟**]。

    ![圖片 26](Linked_image_Files/09-enhance-power-bi-reports_image49b.png)

1. 在 [**文字]** 區段中的 [文字盒 **] 中，** 輸入_條形圖_。

1. 將 **[填滿]** 區段設定為 **[開啟**]，然後使用互補色彩來設定色彩。

1. 將 [**動作]** 區段設定為 **[開啟**]，然後將 Type** 屬性設定**為 **Bookmark**。

1. 選取 **[按鈕**]，**然後將 [動作**] 屬性**** 開啟。

1. 展開 [動作]**** 區段，然後將 [類型]**** 下拉式清單設定為 [書籤]****。

1. 在 [書籤]**** 下拉式清單中，選取 [開啟橫條圖]****。

    ![圖 27](Linked_image_Files/09-enhance-power-bi-reports_image51.png)

1. 使用複製並貼上來建立按鈕的複本，然後設定新按鈕，如下所示：

    > _提示：複製和貼上的快捷方式命令為 **Ctrl+C** ， **後面接著 Ctrl+V**。_

    - 將按鈕文字設定為 _柱形圖_。
    - 將動作書籤設定為 **[柱形圖 ON**]。

    > _銷售分析報表的設計現已完成。_

## 發佈和探索報表

在此練習中，您將將報表發佈至 Power BI 服務，並探索已發佈的報表行為。

> _**注意**：您至少需要 Power **BI 免費** 授權才能發佈報表。 開啟 Microsoft Edge 瀏覽器，然後在 登入 `https://app.powerbi.com`。 當系統要求您解決謎題，或啟動免費的 Fabric 試用版時，您可以略過此專案並關閉瀏覽器。

> _**注意**：即使您無法存取 Power BI 服務 直接執行工作，您仍可檢閱練習的其餘部分。_

1. 選取 [概觀]__ 頁面。

1. 在 [年度]__ 交叉分析篩選器中，選取 [FY2020]****。

1. 在 [ _區域_ 交叉分析篩選器] 中，確定未選取任何區域。

1. 儲存 Power BI Desktop 檔案。

1. 在 [首頁]**** 功能區索引標籤上，從 [共用]**** 群組內選取 [發佈]****。

    > _如果您尚未登入 Power BI Desktop，您必須先登入，才能發佈報表。_

    ![圖片 28](Linked_image_Files/09-enhance-power-bi-reports_image52.png)

1. 在 [ **發佈至 Power BI** ] 視窗中，請注意 _已選取 [我的工作區_ ]。

1. 若要發佈報表，請選取 [ **選取**]。 等候發行集完成。

1. 當發行集成功時，請選取 [ **取得它**]。

1. 關閉 Power BI Desktop。

1. 開啟 Microsoft Edge 瀏覽器，然後登入 `https://app.powerbi.com` （或使用現有的瀏覽器會話）。

1. 在瀏覽器視窗中，在 [Power BI 服務] **的 [流覽**] 窗格中，選取 [我的工作區 **] （位於左側，可以折疊**它）。

1. 若要探索報表，請選取 _[09-Starter-Sales 分析_ ] 報表。

1. 若要測試鑽研功能，請在 __ [概觀] 頁面的 _[依類別_數量總和] 視覺效果中，以滑鼠右鍵按兩下 _[服裝_] 列，然後選取 **[鑽研>產品詳細數據**]。

    ![圖片 29](Linked_image_Files/09-enhance-power-bi-reports_image55.png)

1. 請注意，[_產品詳細數據_] 頁面會篩選 [服裝 _] 的_視覺效果。

1. 若要返回來源頁面，請在頁面左上角選取箭號按鈕。

1. 移至 [我的效能]__ 頁面。

1. 選取每個按鈕，然後注意顯示的不同視覺效果。

## 實驗室完成
