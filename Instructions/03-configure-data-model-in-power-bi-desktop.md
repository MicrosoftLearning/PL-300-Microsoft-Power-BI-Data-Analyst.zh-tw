---
lab:
  title: 在 Power BI 中設計資料模型
  module: 4 - Design a Data Model in Power BI
---


# 在 Power BI 中設計資料模型

**實驗室的完成時間估計為 45 分鐘。**

在此實驗室中，您將開始開發資料模型。 這會牽涉到在資料表之間建立關聯性，然後設定資料表與資料行屬性，以改善資料模型的易懂性與可用性。 您也會建立階層並建立快速量值。

在此實驗室中，您將了解如何：

- 建立模型關聯性
- 設定資料表與資料行屬性
- 建立階層

### **實驗室案例**

此實驗室為一系列實驗室的其中之一，其設計用意是完整呈現資料準備到報表和儀表板發行的整個過程。 您可以依照任何順序完成實驗室。 然而，若您想要逐步完成多個實驗室，建議您依照下列順序加以完成：

1. 在 Power BI Desktop 中準備資料
1. 在 Power BI Desktop 中載入資料
1. **在 Power BI 中設計資料模型**
1. 在 Power BI Desktop 中建立 DAX 計算
1. 在 Power BI Desktop 中建立進階 DAX 計算
1. 在 Power BI Desktop 中設計報表
1. 增強Power BI Desktop中的報表
1. 在 Power BI 中執行資料分析
1. 建立 Power BI 儀表板
1. 強制執行資料列層級安全性

## **練習 1：建立模型關聯性**

在此練習中，您將建立模型關聯性。

### **工作 1：開始作業**

在這項工作中，您將設定實驗室的環境。

1. 開啟 Power BI Desktop。

    ![Power BI Desktop圖示](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

    *提示：根據預設，消費者入門對話方塊會在Power BI Desktop前面開啟。您可以選擇登入，然後關閉快顯視窗。*

1. 若要開啟入門Power BI Desktop檔案，請選取 [檔案 **] > [開啟報表] > [流覽報表**]。

1. 流覽至 **D：\PL300\Labs\03-configure-data-model-in-power-bi-desktop\Starter** 資料夾，然後選取 **[銷售分析** ] 檔案。

1. 關閉任何可能開啟的資訊視窗。

1. 移至 [ **檔案] >** [另存新檔]，並將檔案儲存至 **D：\PL300\MySolution** 資料夾。

### **工作 2：建立模型關聯性**

在此工作中，您將建立模型關聯性。 檔案已設定為無法識別先前實驗室中資料表之間的關聯性。 這不是預設設定，但建議您避免額外工作為您的模型建立正確的關聯性。

*重要事項：實驗室會使用速記標記法來參考欄位。看起來會像這樣： **產品 \| 類別**。在此範例中， **Product** 是資料表名稱， **而 Category** 是功能變數名稱。*

1. 在 Power BI Desktop 中，選取左側的 [模型] 檢視圖示。

     ![圖片 1](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image9.png)

1. 如果您沒有看到所有七個數據表，請水準捲動到右邊，然後拖曳和排列資料表更緊密地一起，以便同時看到它們。

     *提示：您也可以使用位於視窗底部的縮放控制項。*

1. 若要返回 [報表] 檢視，請選取左側的 **[報表** 檢視] 圖示。

     ![圖片 327](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image10.png)

1. 若要檢視所有資料表欄位，請在 [欄位] 窗格中，以滑鼠右鍵按一下空白區域，然後選取 [全部展開]。

1. 若要建立資料表視覺效果，請在 [欄位] 窗格中，從 [Product] 資料表內，選取 [Category] 欄位。

1. 若要將另一個資料行新增至資料表，請在 [ **欄位** ] 窗格中，檢查 **[銷售銷售 \| ** ] 欄位。

1. 請注意，資料表視覺效果會列出四個產品類別，而且每個項目的銷售值與總計都是相同的。
    
    *問題在於資料表是以不同資料表的欄位為基礎。預期每個產品類別都會顯示該類別的銷售量。不過，因為這些資料表之間沒有模型關聯性，所以不會篩選 **Sales** 資料表。您現在會新增關聯性，以在資料表之間傳播篩選。*

     ![圖片 330](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image13.png)

1. 在 [模型] 功能區索引標籤上，從 [關聯性] 群組中選取 [管理關聯性]。

     ![圖片 331](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image14.png)

1. 在 [管理關聯性] 視窗中，請注意尚未定義任何關聯性。

1. 若要建立關聯性，請選取 [新增]。

1. 在 [建立關聯性] 視窗的第一個下拉式清單中，選取 [Product] 資料表。

     ![圖片 333](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image16.png)

1. 在第二個下拉式清單中 (在 [產品] 資料表方格底下)，選取 [Product] 資料表。

     ![圖片 334](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image17.png)

1. 請注意，已自動選取每個資料表中的 [ProductKey] 資料行。
    
    *已選取資料行，因為它們共用相同的名稱和資料類型。您可能需要在實際資料中找到具有不同名稱的相符資料行。*

1. 在 [基數] 下拉式清單中，請注意已選取 [一對多 (1:*)]。
    
    *系統會自動偵測基數，因為 Power BI 了解來自 [Product] 資料表的 [ProductKey] 資料行包含唯一值。一對多關聯性是最常見的基數，而且您在此實驗室中建立的所有關聯性都是這種類型。*

1. 在 [交叉篩選方向] 下拉式清單中，請注意已選取 [單一]。
    
    *單一篩選方向表示篩選會從「一端」傳播到「多端」。在此案例中，這表示套用至 [Product] 資料表的篩選將會傳播至 [Sales] 資料表，但不會朝相反方向傳播。*

1. 請注意，已選取 [將此關聯性設為作用中]。
    
    *作用中的關聯性會傳播篩選。您可以將關聯性標示為非作用中，這樣就不會傳播篩選。當資料表之間有多個關聯性路徑時，可能會有非作用中的關聯性存在。在此案例中，模型計算可以使用特殊函式來啟用這些關聯性。*

1. 選取 **[確定**]，請注意**管理關聯性**視窗中列出新的關聯性，然後選取 [**關閉**]。

1. 請注意，這兩個數據表之間現在有一個連接器， (如果資料表位於彼此旁邊) 並不重要。
    1. 您可以解譯 **1** 和 ** (*) ** 指標所代表的基數。
    1. 篩選方向是以箭頭箭鏃來表示。
    1. 實線代表作用中的關聯性;虛線代表非作用中的關聯性。
    1. 將游標暫留在關聯性上方，以醒目提示相關的資料行。

     ![圖片 338](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image21.png)

     建立關聯性的方法比較簡單。 在模型圖表中，您可以拖放資料行建立新的關聯性。

1. 若要使用不同的技術建立新的關聯性，請從 Reseller 資料表將**ResellerKey**資料行拖曳至**Sales**資料表的**ResellerKey**資料行。** **
    
    *提示：有時候，您會無法拖曳資料行。如果發生這種情況，請選取不同的資料行，然後再次選取您想要拖曳的資料行，然後再試一次。請確定您可以看到新的關聯性已新增至圖表。*

     ![將 ResellerKey 從 Reseller 資料表拖曳到 Sales |ResellerKey](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image22.png)

1. 使用這個新技巧來建立下列兩個模型關聯性：

     - [Region \| SalesTerritoryKey] 至 [Sales \| SalesTerritoryKey]
     - [Salesperson \| EmployeeKey] 至 [Sales \| EmployeeKey]

1. 在圖表中，請排列資料表，讓 [Sales] 資料表位於圖表中央，並將相關的資料表排列到其周圍。 將未連接的資料表置於一旁。

     ![模型檢視中的星型架構設計](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image23.png)

1. 請注意，在報表檢視中，資料表視覺效果已更新，以顯示每個產品類別的不同值。
    
    *套用至 [Product] 資料表的篩選現在會傳播至 [Sales] 資料表。*

     ![已更新具有新關聯性的類別和銷售編號。](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image20.png)

1. 儲存 Power BI Desktop 檔案。

## **練習 2：設定資料表**

在此練習中，您將藉由建立階層和隱藏、格式化和分類資料行來設定每個資料表。

### **工作 1：設定 [Product] 資料表**

在此工作中，您將設定 **Product** 資料表。

1. 在 [模型] 檢視的 [欄位] 窗格中，如有必要，請展開 [Product] 資料表以顯示所有欄位。

1. 若要建立階層，請在 [欄位] 窗格中，以滑鼠右鍵按一下 [Category] 資料行，然後選取 [建立階層]。

     ![建立階層對話方塊。](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image24.png)

1. 在 [屬性] 窗格中 (在 [欄位] 窗格的左側)，於 [名稱] 方塊中，將文字取代為 **Products**。

1. 若要在階層中新增第二個層級，請在 [屬性] 窗格的 [階層] 下拉式清單中選取 [子類別] (您可能需要在窗格內向下捲動)。

1. 若要將第三個層級新增至階層，請在 [階層] 下拉式清單中，選取 [Product]。

1. 若要完成階層設計，請選取 [套用層級變更]。

     ![圖片 343](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image26.png)

    *提示：別忘了選取 [ **套用層級變更**]，這是忽略此步驟的常見錯誤。*

1. 在 [欄位] 窗格中，注意 [Products] 階層。

     ![圖片 347](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image27.png)

1. 若要顯示階層層級，請展開 [Products] 階層。

     ![圖片 346](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image28.png)

1. 若要將資料行組織到顯示資料夾中，在 [欄位] 窗格中，先選取 [背景色彩格式] 資料行。

1. 按下 **Ctrl** 鍵的同時，選取 [字型色彩格式] 資料行。

1. 在 [屬性] 窗格的 [顯示資料夾] 方塊中，輸入**格式**。

     ![圖片 348](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image29.png)

1. 在 [欄位] 窗格中，請注意這兩個資料行現在位於資料夾內。
    
    *顯示資料夾是解碼資料表的絕佳方式，特別是針對組成許多欄位的資料表。它們只是邏輯呈現。*

     ![圖片 349](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image30.png)

### **工作 2：設定 [Region] 資料表**

在此工作中，您將設定 **Region** 資料表。

1. 在 [Region] 資料表中，建立名為 [Regions] 的階層，其中包含下列三個層級：

     - Group
     - Country
     - 區域

     ![圖片 350](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image31.png)

1. 選取 [Country] 資料行 (而不是 [Country] 階層層級)。

1. 在 [屬性] 窗格中，展開 [進階] 區段 (位於窗格底部)，然後在 [資料類別] 下拉式清單中選取 [國家/地區]。
    
    *資料分類可以提供提示給報表設計師。在此案例中，將資料行分類為國家或地區可在 Power BI 轉譯地圖視覺效果時為其提供更精確的資訊。*

     ![圖片 352](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image32.png)

### **工作 3：設定 [Reseller] 資料表**

在此工作中，您將設定 **Reseller** 資料表。

1. 在 [Reseller] 資料表中，建立名為 [Resellers] 的階層，其中包含下列兩個層級：

     - Business Type
     - Reseller

1. 建立名為 [Geography] 的第二個階層，其具有下列四個層級：

     - Country-Region
     - State-Province
     - City
     - Reseller

1. 將 [Country-Region]、[State-Province] 和 [City] 資料行 (非階層層級) 的 [資料類別] 分別設定為 [國家/地區]、[州或省] 和 [城市]。

### **工作 4：設定 [Sales] 資料表**

在此工作中，您將設定 **Sales** 資料表。

1. 在 [Sales] 資料表中，選取 [Cost] 資料行。

1. 在 [ **屬性]** 窗格的 [ **描述]** 方塊中，輸入： *根據標準成本*。
    
    *可以將描述套用至資料表、資料行、階層或量值。在 [欄位] 窗格中，當報表作者將游標停留在欄位上方時，描述文字會顯示在工具提示中。*

1. 選取 [Quantity] 資料行。

1. 在 [屬性] 窗格中，從 [格式] 區段中，將 [千位分隔符號] 屬性滑動到 [是]。

1. 選取 [Unit Price] 資料行。

1. 在 [屬性] 窗格中，從 [格式] 區段中，將 [小數位數] 屬性設定為 [2]。

1. 在 [進階] 群組中 (您可能需要向下捲動捲動以找到它)，在 [摘要方式] 下拉式清單中，選取 [平均]。
    
    *根據預設，數值資料行會藉由將值加總在一起來摘要。此預設行為不適用於代表費率的資料行，例如 **單價**。將預設摘要設定為平均值會產生有意義的結果。*

### **工作 5：大量更新屬性**

在這項工作中，您將使用單一大量更新來更新多個資料行。 您將使用此方法來隱藏資料行，以及格式化資料行值。

1. 在 [欄位] 窗格中，選取 [Product \| ProductKey] 資料行。

1. 按下 **Ctrl** 鍵時，選取下列 13 個資料行 (跨多個資料表)：

     - Region \| SalesTerritoryKey
     - Reseller \| ResellerKey
     - Sales \| EmployeeKey
     - Sales \| ProductKey
     - Sales \| ResellerKey
     - Sales \| SalesOrderNumber
     - Sales \| SalesTerritoryKey
     - Salesperson \| EmployeeID
     - Salesperson \| EmployeeKey
     - Salesperson \| UPN
     - SalespersonRegion \| EmployeeKey
     - SalespersonRegion \| SalesTerritoryKey
     - Targets \| EmployeeID

1. 在 [屬性] 窗格中，將 [已隱藏] 屬性滑動到 [是]。
    
    *資料行已隱藏，因為其是由關聯性使用，或是用於資料列層級安全性設定或計算邏輯。*

    *您將在 Power BI Desktop 實驗室中**建立 DAX 計算**中的計算中使用**SalesOrderNumber**。*

1. 複選以下三個資料行：

     - Product \| Standard Cost
     - Sales \| Cost
     - Sales \| Sales

1. 在 [屬性] 窗格中，從 [格式] 區段中，將 [小數位數] 屬性滑動到 [0] \(零\)。

## **練習 3：檢閱模型介面**

在此練習中，您將切換至 [報表] 檢視，並檢閱模型介面。

### **工作 1：檢閱模型介面**

在此工作中，您將切換至 [報表] 檢視，並檢閱模型介面。

1. 切換至 [報表] 檢視。

1. 在 [欄位] 窗格中，注意下列項目：

     - 資料行、階層與其層級都是欄位，可以用來設定報表視覺效果
     - 只會顯示與報表製作相關的欄位
     - 看不到 **SalespersonRegion** 資料表，因為其所有欄位都會隱藏
     - [Region] 與 [Reseller] 資料表中的空間欄位已使用空間圖示來裝置
     - 以 Sigma 符號 (Ʃ) 裝飾的欄位依預設會彙總
     - 將游標停留在 [Sales \| Cost] 欄位上方時會出現工具提示

1. 展開 [Sales \| OrderDate] 欄位，然後注意其會顯示日期階層。
    
    *[ **目標目標 \| ][月** ] 欄位會傳遞類似的階層。這些階層不是由您建立的。它們會自動建立。不過，有問題。Adventure Works 財務年度將于每年 7 月 1 日開始。但是，在這些自動建立日期階層中，每年的 1 月 1 日開始日期階層年度。*

     ![圖片 359](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image40.png)

 您現在將會關閉此自動行為。 在**Power BI Desktop 實驗室中建立 DAX 計算**中，您將使用 DAX 來建立日期資料表，並設定它定義 Adventure Works 的行事曆。

1. 若要關閉自動/日期時間，請流覽至 [ **檔案] > [選項和設定] > [選項] > [目前檔案** ] 群組，然後選取 [ **資料載入**]。
    1. 在 [時間智慧] 區段中，取消選取 [自動日期/時間]。

     ![圖片 362](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image43.png)

1. 在 [欄位] 窗格中，請注意日期階層已無法再使用。

     ![圖片 363](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image45.png)

## **練習 4：建立快速量值**

在此練習中，您將建立兩個快速量值。

### **工作 1：建立快速量值**

在這項工作中，您將建立兩個快速量值來計算收益和利潤。

*快速量值會為您建立計算公式。為了簡單且常見的計算，它們很容易且快速建立。您將在 Power BI Desktop 實驗室中建立**DAX 計算**中不使用此工具來建立量值。*

1. 在 [欄位] 窗格中，以滑鼠右鍵按一下 [Sales] 資料表，然後選取 [新增快速量值]。

     ![圖片 366](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image46.png)

1. 在 [快速量值] 視窗的 [計算] 下拉式清單中，從 [數學運算] 群組內選取 [減法]。

     ![圖片 367](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image47.png)

1. 在 [快速量值] 視窗的 [欄位] 窗格中，展開 [Sales] 資料表。

1. 將 [Sales] 欄位拖曳至 [基底值] 方塊中。

1. 將 [Cost] 欄位拖曳至 [要相減的值] 方塊。

     ![圖片 368](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image48.png)

1. 在 [欄位] 窗格的 [Sales] 資料表內，請注意新的量值。
    1. *量值會使用計算機圖示。*

     ![圖片 370](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image50.png)

1. 若要重新命名量值，請以滑鼠右鍵按一下該量值，選取 [ **重新**命名]，然後重新命名為 **Profit**。
    
    *提示：若要重新命名欄位，您也可以在其上方按兩下，或選取該欄位，然後按 **F2**。*

1. 在 [Sales] 資料表中，根據下列需求，新增另一個快速量值：

     - 使用 [除法] 數學運算
     - 將 [分子] 設定為 [Sales \| Profit] 欄位
     - 將 [分母] 設定為 [Sales \| Sales] 欄位
     - 將量值重新命名為 **Profit Margin**

1. 請確定已選取 [獲利率] 量值，然後在 [量值工具] 內容功能區上，將格式設定為 [百分比]，並使用兩位小數。

     ![圖片 374](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image54.png)

1. 若要測試這兩個量值，請先選取報表頁面上的 **資料表** 視覺效果。

1. 在 [欄位] 窗格中，檢查兩個量值。

     ![圖片 375](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image55.png)

1. 選取並拖曳右邊的輔助線，以擴大資料表視覺效果。

     ![圖片 376](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image56.png)

1. 確認量值能產生格式正確的合理結果。

     ![圖片 378](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image57.png)

### **工作 2：建立多對多關聯性**

在這項工作中，您將建立 **Salesperson** 資料表與 **Sales** 資料表之間的多對多關聯性。

 *實驗室使用速記標記法來參考欄位。其看起來將會像下面這樣：**Salesperson \| Salesperson**在此範例中，[Salesperson] 是資料表名稱，而 [Salesperson] 是欄位名稱。*

1. 在Power BI Desktop中，在 [報表] 檢視的 [**欄位**] 窗格中，檢查下列兩個欄位以建立**資料表**視覺效果。

     - Salesperson \| Salesperson
     - Sales \| Sales

     ![圖片 1](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image9.png)

     *資料表會顯示每位銷售人員的銷售額。不過，銷售人員與銷售額之間還有另一個關聯性。某些銷售人員屬於一個、兩個或可能更多個銷售區域。此外，銷售區域也可以獲指派多位銷售人員。*

     *從效能管理的觀點來看，銷售人員的銷售額 (根據其獲指派的領域) 必須經過分析，並與銷售目標進行比較。您將在下一個練習中建立支援此分析的關聯性。*

1. 請注意， **Michael Blythe** 已銷售幾乎 9 百萬美元。

1. 切換至 [模型] 檢視，然後將 **SalespersonRegion** 資料表拖曳至 **[區域** ] 和 **[Salesperson]** 資料表之間。

1. 使用拖放技術建立下列兩個模型關聯性：

     - [Salesperson \| EmployeeKey] 至 [SalespersonRegion \| EmployeeKey]
     - [Region \| SalesTerritoryKey] 至 [SalespersonRegion \| SalesTerritoryKey]

    *[SalespersonRegion] 資料表可以視為橋接資料表。*

1. 切換至 [報表] 檢視，然後注意到視覺效果尚未更新—Michael Blythe 的銷售結果尚未變更。

1. 切換回 [模型] 檢視，然後遵循 **Salesperson** 資料表中的關聯性篩選方向 (箭頭)。 
    
    *請考慮 **Salesperson** 資料表會篩選 **Sales** 資料表。它也會篩選 **SalespersonRegion** 資料表，但不會繼續將篩選傳播至 **Region** 資料表， (箭頭指向錯誤的方向) 。*

     ![圖片 380](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image11.png)

1. 若要編輯 **Region** 和 **SalespersonRegion** 資料表之間的關聯性，請按兩下關聯性。

1. 在 [編輯關聯性] 視窗的 [交叉篩選方向] 下拉式清單中，選取 [兩者]。

1. 核 **取 [雙向套用安全性篩選器** ] 核取方塊，然後選取 [確定]。

     ![圖片 381](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image12.png)

1. 請注意，關聯性現在有雙箭頭。

     ![圖片 382](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image14.png)

1. 切換至 [報表] 檢視，然後注意銷售值仍尚未變更。
    
    *問題現在與**Salesperson**和**Sales**資料表之間有兩個可能的篩選傳播路徑有關。根據「最少的資料表數目」評估，在內部解析此模棱兩可。明確而言，您不應該設計這種模棱兩可的模型，此問題將在本實驗室稍後的一部分解決，並在**Power BI Desktop 實驗室中完成建立 DAX 計算**。*

1. 切換至 [模型] 檢視，以強制透過橋接資料表傳播篩選。  (按兩下) **Salesperson** 與 **Sales** 資料表之間的關聯性。

1. 在 [ **編輯關聯性** ] 視窗中，取消核取 [ **將此關聯性設為使用中]** 核取方塊，然後選取 [ **確定**]。
    
    *篩選傳播現在將會遵循唯一的作用中路徑。*

1. 請注意，在圖表中，非作用中的關聯性是以虛線表示。

     ![圖片 5697](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image17.png)

1. 切換至 [報表] 檢視，然後注意到 Michael Blythe 的銷售額現在接近 $22 百萬美元。

     ![圖片 5698](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image18.png)

1. 另請注意，每個銷售人員的銷售額若相加，將會超過資料表總計。

     *這是多對多關聯性的常見觀察，因為雙精度浮點數、三重等。區域銷售結果的計數。請考慮 Brian Welcker，這是列出的第二位銷售人員。他的銷售金額等於總銷售額。這是正確的結果，因為他是銷售經理;銷售量是由所有區域的銷售額來測量。*

     *雖然多對多關聯性現已運作，但現在無法分析銷售人員 (所做的銷售，因為關聯性非作用中) 。當您引進匯出資料表時，您將能夠重新啟用關聯性，以允許在銷售領域中分析銷售 () 指派給銷售人員 (，以便在 Power BI Desktop 實驗室中**建立 DAX 計算**中) 效能分析。*

1. 切換至 [模型] 檢視，然後在圖表中選取 **Salesperson** 資料表。

1. 在 [內容] 窗格的 [名稱] 方塊中，將文字取代為 **Salesperson (Performance)**。

*重新命名的資料表現在會反映其用途：其是用來根據其獲指派銷售區域的銷售額來報告和分析銷售人員的績效。*

### **工作 3：建立與 Targets 資料表的關聯性**

在此工作中，您將建立 **與 Targets** 資料表的關聯性

1. 建立從 [Salesperson (Performance) \| EmployeeID] 資料行到 [Targets \| EmployeeID] 資料行的關聯性。

1. 在 [報表] 檢視中，將 [Targets \| Target] 欄位新增至資料表視覺效果。

1. 調整資料表視覺效果的大小，讓所有資料行都可見。

     ![圖片 5699](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image19.png)

 *現在可以將銷售與目標視覺化，但請小心兩個原因。首先，沒有時間週期的篩選準則，因此目標也會包含未來的目標數量。其次，目標不會加總，因此不應該顯示總計。您可以藉由格式化視覺效果或使用計算邏輯來移除它們。您將遵循第二種方法，方法是在 Power BI Desktop 實驗室中建立進**階 DAX 計算**中建立目標量值，以在篩選多個銷售人員時傳回 BLANK。*

### **工作 4：完成**

在此工作中，您將完成實驗室。

儲存Power BI Desktop檔案，並在系統提示您套用查詢時選取 [**稍後**套用]。
