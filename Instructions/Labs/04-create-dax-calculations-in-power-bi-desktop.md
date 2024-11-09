---
lab:
  title: 在 Power BI Desktop 中建立 DAX 計算
  module: Create Model Calculations using DAX in Power BI
---


# 在 Power BI Desktop 中建立 DAX 計算

## **實驗室案例**

在此實驗室中，您將使用數據分析表達式 （DAX） 建立匯出數據表、計算結果列和簡單量值。

在此實驗室中，您將了解如何：

- 建立導出資料表
- 建立計算結果欄
- 建立量值

**此實驗室大約需要45分鐘的時間。**

## 開始使用

若要完成此練習，請先開啟網頁瀏覽器，然後輸入下列 URL 以下載 zip 資料夾：

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/04-create-dax-calculations-in-power-bi-desktop\04-intro-dax.zip`

將資料夾解壓縮至 **C：\Users\Student\Downloads\04-intro-dax** 資料夾。

**開啟 04-Starter-Sales Analysis.pbix** 檔案。

> ***注意**：您可以選取 **[取消**] 來關閉登入。 關閉任何其他信息視窗。 如果系統提示您套用變更，請選取 **[稍後**套用]。

## 建立 Salesperson 匯出數據表

在這項工作中，您將建立 **Salesperson** 匯出數據表（與 Sales** 的**直接關聯性）。

建立導出資料表的方式是先輸入資料表名稱，後面接著等號 (=)，然後是傳回資料表的 DAX 公式。 資料表名稱不可已存在於資料模型中。

公式列支援輸入有效的 DAX 公式， 其中包含自動完成、Intellisense 和色彩編碼等功能，可讓您快速且正確地輸入公式。

1. 在 Power BI Desktop 的 [報表] 檢視中，從 [模型]**** 功能區的 [計算]**** 群組內，選取 [新增資料表]****。

     ![圖片 1](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image9.png)

2. 在公式列 (在建立或編輯計算時直接在功能區下方開啟) 中，輸入 **Salesperson =**，按 **Shift+Enter**，輸入 **'Salesperson (Performance)'**，然後按 **Enter** 鍵。

    > **注意**： *為了方便起見，此實驗室中的所有DAX定義都可以從位於 **04-intro-dax\Snippets.txt**的代碼段檔案複製。*

     ![圖片 4](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image10.png)

    > *此數據表定義會建立 Salesperson （Performance）** 數據表的**複本。它只會複製數據，但是不會複製模型屬性，例如可見度、格式等。*

1. 在 [ **數據** ] 窗格中，請注意數據表圖示前面有額外的計算機（表示計算數據表）。

    ![圖片 10](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image11.png)

    > ***注意**：匯出數據表是使用會傳回數據表的DAX公式來定義。 請務必了解，導出資料表會將值具體化並加以儲存，因此會增加資料模型的大小。 每當重新整理公式相依性時，就會重新計算，當新的 （未來） 日期值載入數據表時，此數據模型的情況也會如此。*
    >
    > *不同於 Power Query 來源數據表，匯出數據表無法用來從外部數據源載入數據。他們只能根據已載入數據模型的內容來轉換數據。*

1. 切換至 [模型] 檢視，並注意到 **Salesperson** 數據表可供使用（您可能需要重設檢視以尋找數據表）。

1. 建立從 [銷售人員 \| EmployeeKey] **** 資料行到 [銷售額 \| EmployeeKey] **** 資料行的關聯性。

1. 以滑鼠右鍵按一下 [銷售人員 (效能)]**** 資料表與 [銷售]**** 資料表之間的非作用中關聯性，然後選取 [刪除]****。 當系統提示您確認刪除時，請選取 [ **是**]。

1. 在 ****[銷售人員] 資料表中，多重選取下列資料行，然後將這些資料行隱藏 (將 [隱藏]**** 屬性設為 [是]****)：

    - EmployeeID
    - EmployeeKey
    - UPN

1. 在模型圖表中，選取 [銷售人員]**** 資料表。

1. 在 [**屬性]** 窗格中的 [描述 **] 方塊中**，輸入：**與 Sales 相關的 Salesperson**
    
    > *當使用者將游標停留在 **資料表或欄位上時，您可能會記得描述會顯示為 [資料** ] 窗格中的工具提示。*

1. **針對 Salesperson （Performance）** 數據表，將描述設定為：**與 region（s） 相關的 Salesperson**

*數據模型現在會在分析銷售人員時提供兩個替代方案。 **Salesperson** 數據表允許分析銷售人員所做的銷售，而 **Salesperson （Performance）** 數據表則允許分析指派給銷售人員之銷售區域中的銷售量。*

## 建立日期資料表

在此工作中，您將建立 [日期]**** 資料表。

1. 切換至 [數據表] 檢視。 在 [常用]**** 功能區索引標籤上，從 [計算]**** 群組內選取 [新增資料表]****。

    ![圖 5](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image15.png)

1. 在公式列中，輸入下列 DAX：

    ```DAX
    Date =  
    CALENDARAUTO(6)
    ```

    ![圖片 6](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image16.png)

    > *CALENDARAUTO（） 函式會傳回由日期值組成的單一數據行數據表。「自動」行為會掃描所有數據模型日期數據行，以判斷儲存在數據模型中的最早和最新的日期值。然後，它會在此範圍內為每個日期建立一個數據列，以任一方向擴充範圍，以確保儲存整年的數據。*
    >
    > *此函式可以採用單一選擇性自變數，也就是一年的最後一個月數目。省略時，此值為12，表示12月是年度的最後一個月。在此案例中，輸入 6，表示 6 月是年度的最後一個月。*

1. 請注意使用美國地區設定格式化的日期值數據行（也就是mm/dd/yyyy）。

    ![圖片 7](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image17.png)

1. 在左下角的狀態列中查看資料表統計資料，確認已產生 1826 個資料列，這代表五個完整年度的資料。

    ![圖 9](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image18.png)

## 建立計算結果欄

在這項工作中，您將新增更多數據行，以啟用依不同時段的篩選和分組。 您也會建立一個計算結果欄，以控制其他資料行的排序順序。

> **注意**： *為了方便起見，此實驗室中的所有DAX定義都可以從 **Snippets.txt** 檔案複製。*

1. 在 [資料表工具]**** 內容功能區中，從 [計算]**** 群組內選取 [新增資料行]****。

    > *計算結果列的建立方式是先輸入數據行名稱，後面接著等於符號 （=），後面接著會傳回單一值結果的DAX公式。數據表中還不能有數據行名稱。*

    ![圖片 11](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image19.png)

1. 在公式列中輸入下列內容 (或從程式碼片段檔案複製)，然後按 **Enter**：
    > *公式會使用日期的年份值，但在當月份在 6 月之後時，將一個新增至年份值。這是 Adventure Works 的會計年度計算方式。*

   ```DAX
   Year =
   "FY" & YEAR('Date'[Date]) + IF(MONTH('Date'[Date]) > 6, 1)
   ```



1. 使用程式碼片段檔案定義，為 [日期]**** 資料表建立下列兩個計算結果欄：

    - 季
    - Month

1. 確認已新增數據行。

    ![圖片 14](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image21.png)

1. 若要驗證計算，請切換至 [報表] 檢視。

1. 若要建立新的報表頁面，請選取第 1 頁旁的加號圖示。

    ![圖片 15](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image22.png)

1. 若要將矩陣視覺效果新增至新的報表頁面，請在 [視覺效果]**** 窗格中選取矩陣視覺效果類型。

    > *提示：您可以將游標暫留在每個圖示上，以顯示描述視覺效果類型的工具提示。*

    ![圖片 51](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image23.png)

1. 在 [**數據] 窗格中，從 [日期] 數據表內部 **，將 **[年**] 字段拖曳到 **** [數據**** 列] 井/區域。

    ![圖 17](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image24.png)

1. 將 [月份]**** 欄位拖曳至 [資料列]**** 井/區域中，放在 [年度]**** 欄位的正下方。

1. 在矩陣視覺效果的右上方（或底部，視視覺效果的位置而定），選取分叉雙箭號圖示（這會向下展開所有年份一個層級）。

    ![圖 19](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image26.png)

1. 請注意，年度會展開為月份，而月份會依字母順序排序，而不是按時間順序。

    ![圖片 20](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image27.png)

    > *根據預設，文字值會依字母順序排序、數位從最小到最大排序，而日期會從最早排序到最新。*

1. 若要自定義 [ **月份]** 字段排序順序，請切換至 [數據表檢視]。

1. 將 **MonthKey** 資料行新增至 [日期]**** 資料表。

    ```DAX
    MonthKey =
    (YEAR('Date'[Date]) * 100) + MONTH('Date'[Date])
    ```

    > *此公式會計算每年/月組合的數值。*

1. 在 [數據表] 檢視中，確認新的數據行包含數值（例如，2017 年 7 月的 201707 等等）。

    ![圖 21](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image28.png)

1. 切換回 [報表] 檢視。 在 [ **數據]** 窗格中，選取 [ **月份**]。

1. 在 [資料行工具]**** 內容功能區中，從 [排序]**** 群組內選取 [依資料行排序]****，然後選取 [MonthKey]****。

    ![圖 22](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image29.png)

1. 在矩陣視覺效果中，您會發現月份此時依時間排序。

    ![圖 23](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image30.png)

## 完成日期資料表

在此工作中，您將隱藏資料行並建立階層，以完成 [日期]**** 資料表的設計。 接著，您會建立 [銷售]**** 和 [目標]**** 資料表的關聯性。

1. 切換至 [模型] 檢視。 在 [日期]**** 資料表中，將 [MonthKey]**** 資料行隱藏 (將 [隱藏]**** 設為 [是]****)。

1. 在 [ **數據** ] 右側窗格上，選取 **[日期** ] 數據表，以滑鼠右鍵按兩下 **[年** ] 資料行，然後選取 [ **建立階層**]。

1. 選取 [重新命名] 和 **[重新命名]，將新建立的階層重新命名**為 **[會計**]。

1. 在 [數據] 窗格中選取**下列兩個其餘欄位，以滑鼠右鍵按兩下 [新增至階層 Fiscal]，**以將下列兩個其餘字段新增至會計**階層。****** -> 

    - 季
    - Month

    ![圖 24](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image31.png)

1. 建立下列兩個模型關聯性：

    - **日期 \| 日期**與**銷售額 \| OrderDate**
    - **日期 \| 日期**與**目標 \| TargetMonth**


    > *實驗室會使用速記表示法來參考欄位。看起來會像這樣： **銷售 \| 單價**。在此範例中， **Sales** 是數據表名稱，而 **Unit Price** 是功能變數名稱。*

1. 隱藏以下兩個資料行：

    - 銷售額 \| OrderDate
    - 目標 \| TargetMonth

## 標示日期資料表

在此工作中，您會將 [日期]**** 資料表標示為日期資料表。

1. 切換至 [報表] 檢視。 在 [**數據]** 窗格中，選取 **[日期] 數據表 （而非 **[** 日期]** 字段。

1. 在 [數據表工具 **] 內容功能區上，從 [** 行事曆]** 群組內部**，選取 [**標示為日期數據表**]。

1. 在 [**標示為日期數據表**] 視窗中，將 [標示為日期數據表 **] 屬性投影**片到 **[是**]，然後在 [**選擇日期數據行**] 下拉式清單中，選取 **[日期**]。 選取**儲存**。

    ![標示為日期資料表](Linked_image_Files/04-create-dax-calculations-in-power-bi-desktop_date-table.png)

1. 儲存 Power BI Desktop 檔案。

> *Power BI Desktop 現在瞭解此數據表會定義日期（時間）。當您的數據源中沒有日期數據表時，適用於日期數據表的設計方法。如果您有數據倉儲，則適合從其日期維度數據表載入日期數據，而不是在數據模型中「重新定義」日期邏輯。*

## 建立簡單量值

在此工作中，您將建立簡單量值。 簡單量值會彙總資料表中單一資料行或計數資料列中的值。

1. 在 [報表檢視] **的 [第 2**** 頁] 的 [數據**] 窗格中，將 **[銷售\|單價**] 字段拖曳到矩陣視覺效果中。

    ![圖 27](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image35.png)

1. 在視覺效果欄位窗格 （位於 [視覺效果 **] 窗格下方**的 **[值**] 字段井/區域中，請注意 **[單價] 會列為 **[單價**] 的 [平均]。** 選取 **Unit Price** 的向下箭號，並留意可用的功能表選項。

    ![圖片 30](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image37.png)

    > *可見的數值數據行允許報表作者在報表設計時間決定數據行值如何摘要（或不摘要）。這可能會導致不適當的報告。不過，有些數據模型器不喜歡讓事情有機會，並選擇隱藏這些數據行，而是公開量值中定義的匯總邏輯。這是您現在在此實驗室中採用的方法。*

1. 若要建立量值，請在 [ **數據** ] 窗格中，以滑鼠右鍵按兩下 **[銷售** ] 資料表，然後選取 [ **新增量值**]。

1. 在公式列中，新增下列量值定義：

    ```DAX
    Avg Price =  
    AVERAGE(Sales[Unit Price])
    ```

1. 將 **Avg Price 量值新增至矩陣視覺效果，並注意它會產生與 **[單價****] 數據行相同的結果（但格式不同）。

1. 在 [**值**] 中，開啟 [平均價格 **] 字段的操作功能表**，並注意無法變更匯總技術。

    ![圖片 32](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image39.png)

    > *您無法修改量值的彙總行為。*

1. 使用程式碼片段檔案定義，為 [銷售]**** 資料表建立下列五個量值：

    - 中間價格
    - 最低價格
    - 最高價格
    - 訂單
    - 訂單明細

    > *Orders** 量值中使用的 **DISTINCTCOUNT（） 函式只會計算訂單一次（忽略重複專案）。Order Lines** 量值中使用的 **COUNTROWS（） 函式會在數據表上運作。*
    >
    > *在此案例中，訂單數是透過計算相異的 **SalesOrderNumber** 資料行值所得出，而訂單明細的數目就是資料表資料列的數目 (每個資料列分別是訂單的一行)。*

1. 切換至 [模型] 檢視，然後複選四個價格量值：[平均價格]****、[最高價格]****、[中間價格]**** 和 [最低價格]****。

11. 複選量值時，請設定下列需求：

    - 將格式設定為兩個小數位數

    - 指派給名為 **Pricing** 的顯示資料夾

    ![圖片 33](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image40.png)

12. 隱藏 [單價]**** 資料行。

    > *報表 **作者現在無法使用 [單價]** 數據行。他們必須使用您已新增至模型的定價量值。此設計方法可確保報表作者不會藉由加總來不適當地匯總價格。*

13. 複選 [訂單明細]**** 和 [訂單]**** 量值，並設定下列需求：

    - 設定使用千位分隔符號的格式

    - 指派給名為 **Counts** 的顯示資料夾

    ![圖片 36](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image41.png)

14. 在 [報表] 檢視中，在矩陣視覺效果的 [ **值** ] 區/區域中，選取 **[單位價格** ] 字段的 **[X** ] 將其移除。

15. 增加矩陣視覺效果的大小，以符合頁面寬度和高度。

16. 將下列五個量值新增至矩陣視覺效果：

    - 中間價格
    - 最低價格
    - 最高價格
    - 訂單
    - 訂單明細

17. 確認結果看起來很合理，且格式正確。

    ![圖片 39](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image43.png)

## 建立其他量值

在這項工作中，您將建立更多使用複雜公式的量值。

1. 在 [報表] 檢視中，選取 **[第 1** 頁] 並檢閱數據表視覺效果，並注意到 [目標]** 數據行的**總計。

    ![圖片 41](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image45.png)

1. 選取資料表視覺效果，然後在 [視覺效果]**** 窗格中，移除 [目標]**** 欄位。

1. 將 [目標 \| 目標]**** 資料行重新命名為 [目標 \| TargetAmount]****。

    > *提示：在 [報表] 檢視中重新命名數據行的方法有數種：在 **[數據** ] 窗格中，您可以以滑鼠右鍵按兩下數據行，然後選取 **[重新命名**]，或按兩下資料行，或按 **F2**。*

1. 在 [目標]**** 資料表上建立下列量值：

    ```DAX
    Target =
    IF(
    HASONEVALUE('Salesperson (Performance)'[Salesperson]),
    SUM(Targets[TargetAmount])
    )
    ```

    > *HASONEVALUE（） 函式會測試是否已篩選 Salesperson** 數據行中的**單一值。若為 true，表達式會傳回目標金額的總和（僅針對該銷售人員）。若為 false，則會傳回 BLANK。*

1. 將 [目標]**** 量值格式化為零個小數位數。

    > *提示：您可以使用 **量值工具** 內容相關功能區。*

1. 隱藏 **TargetAmount** 資料行。

    > *提示：您可以在 [數據 **] 窗格中以滑鼠右鍵按兩下數據行**，然後選取 [**隱藏**]。*

1. 將 [目標]**** 量值新增至資料表視覺效果。

1. 請注意，[目標]**** 資料行的總計此時是空白的。

    ![圖片 43](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image47.png)

1. 使用程式碼片段檔案定義，為 [目標]**** 資料表建立下列兩個量值：

    - 變異數
    - 變異數邊界

1. 將 [變異數]**** 量值格式化為零個小數位數。

1. 將 [變異數邊界]**** 量值格式化為具有兩個小數位數的百分比。

1. 將 [變異數]**** 和 [變異數邊界]**** 量值新增至資料表視覺效果。

1. 調整資料表視覺效果的大小，以便看到所有資料行與資料列。

    ![圖片 44](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image48.png)

    > *雖然所有銷售人員都不符合目標，但請記住，數據表視覺效果尚未依特定時段進行篩選。您將產生銷售績效報告，以在Power BI Desktop**實驗室中**依使用者選取的時間週期進行篩選。*

1. 在 [數據 **] 窗格右上角**折迭，然後展開開啟窗格。

    > *折疊並重新開啟窗格會重設內容。*

1. 請注意，[目標]**** 資料表此時會出現在清單頂端。

    ![圖片 46](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image50.png)

    *只包含可見量值的數據表會自動列在清單頂端。*

## 實驗室完成
