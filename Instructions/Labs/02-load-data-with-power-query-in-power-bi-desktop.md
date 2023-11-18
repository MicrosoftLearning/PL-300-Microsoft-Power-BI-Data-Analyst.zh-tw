---
lab:
  title: 在 Power BI Desktop 中載入轉換的資料
  module: 'Clean, Transform, and Load Data in Power BI'
---

# 在 Power BI Desktop 中載入轉換的資料

## **實驗室案例**

在此實驗室中，您將使用資料清理和轉換技術開始塑造資料模型。 接著，您將會把每項查詢載入為資料模型的資料表。

在此實驗室中，您將了解如何：

- 套用各種轉換
- 將查詢載入資料模型

**此實驗室大約需要 45 分鐘的時間。**

## **開始使用**

在這項工作中，您將設定實驗室的環境。

*重要事項：如果您已完成相同 VM 中的上一個實驗室，請跳至下一個工作。*

1. 開啟 Power BI Desktop。

    *提示：根據預設，[使用者入門] 對話方塊會在 Power BI Desktop 前面開啟。您可以選擇登入，然後關閉快顯。*

    ![Power BI Desktop 圖示](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

1. 若要開啟入門 Power BI Desktop 檔案，請選取 ** [檔案] > [開啟報表] > [流覽報表 ** ]。

1. 在 [ ** 開啟] ** 視窗中，流覽至 ** D：\PL300\Labs\02-load-data-with-power-query-in-power-bi-desktop\Starter ** 資料夾，然後開啟 ** [銷售分析 ** ] 檔案。

1. 關閉任何可能開啟的資訊視窗。

1. 注意功能區下方的黃色警告訊息。

    *此訊息會提醒您查詢尚未套用為模型資料表載入的事實。您稍後會在此實驗室中套用查詢。*

    若要關閉此警告訊息，請選取黃色警告訊息右側的 **X**。

1. 若要建立檔案的複本，請移至 [檔案] > [ ** 另存新 ** 檔]，然後儲存至 ** D：\PL300\MySolution ** 資料夾。

1. 如果系統提示您套用變更，請選取 [稍後套用]****。

## **設定 Salesperson 查詢**

在這項工作中，您將使用 Power Query 編輯器 來設定 ** Salesperson ** 查詢。

*重要：當指示重新命名資料行時，請務必完全如所述重新命名資料行。*

1. 若要開啟 [Power Query 編輯器]**** 視窗，請在 [首頁]**** 功能區索引標籤上，從 [查詢]**** 群組中選取**轉換資料**圖示。

     ![轉換首頁上的資料功能區](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image10.png)

1. 在 [Power Query 編輯器]**** 視窗的 [查詢]**** 窗格中，選取 [DimEmployee]**** 查詢。

     ![圖片 1](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image11.png)

1. 若要重新命名查詢，請在 [查詢設定]**** 窗格 (位於右側) 的 [名稱]**** 方塊中，將文字取代為 **Salesperson**，然後按 **Enter**。 然後確認名稱已在 [查詢 ** ] 窗格中更新 ** 。

    *查詢名稱會決定模型資料表名稱。建議您定義簡潔且易記的名稱。*

1. 若要找出特定資料行，請在 [ ** 首頁 ** ] 功能區索引標籤上，選取 ** [管理 ** 資料行] 向下箭號，選取 ** [選擇 ** 資料行向下箭號]，然後選取 ** [移至資料行 ** ]。

    *移至 [資料行] 是許多資料行的實用功能。否則，您可以水準捲動尋找資料行。*

     ![管理資料行>選擇資料行>移至資料行](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image13.png)

1. 在 [ ** 移至資料行 ** ] 視窗中，若要依資料行名稱排序清單，請選取 ** [AZ ** 排序] 按鈕，然後選取 [名稱 ** ] 和 ** [ ** SalesPersonFlag ** ]。 按一下 [確定]****。

     ![移至資料行排序選項](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image14.png)

1. **找出 SalesPersonFlag ** 資料行，然後篩選資料行，只選取 Salespeople （也就是 ** TRUE ** ），然後按一下 [ ** 確定 ** ]。

1. 在 [查詢設定]**** 窗格的 [套用的步驟]**** 清單中，注意新增的 [已篩選資料列]**** 步驟。

    *您建立的每個轉換都會產生另一個步驟邏輯。可以編輯或刪除步驟。您也可以選取步驟，在查詢轉換的該階段預覽查詢結果。*

     ![套用的步驟](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image17.png)

1. 若要移除資料行，請在 [ ** 首頁 ** ] 功能區索引標籤上，選取 ** [管理資料 ** 行] 群組，選取 [ ** 選擇資料行 ** ] 圖示。

1. 在 [選擇資料行]**** 視窗中，若要取消選取所有資料行，請取消選取 [(選取所有資料行)]**** 項目。

1. 若要包含資料行，請核取下列六個資料行：

    - EmployeeKey
    - EmployeeNationalIDAlternateKey
    - FirstName
    - LastName
    - Title
    - EmailAddress

1. 在 [套用的步驟]**** 清單中，請注意新增的另一個查詢步驟。

     ![已移除其他資料行步驟](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image21.png)

1. 若要建立單一名稱資料行，請先選取 [FirstName]**** 資料行標頭。 按下 **Ctrl** 鍵的同時，選取 [LastName]**** 資料行。

     ![多重選取兩個數據行以建立單一資料行](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image22.png)

1. 以滑鼠右鍵按一下其中一個選取的資料行標頭，然後在操作功能表中選取 [合併資料行]****。

    *您可以在資料行標頭上按一下滑鼠右鍵，然後從操作功能表選擇它們，以套用許多常見的轉換。不過請注意，功能區中有更多轉換可供使用。*

1. 在 [合併資料行]**** 視窗的 [分隔符號]**** 下拉式清單中，選取 [空格]****。

1. 在 [新資料行名稱]**** 方塊中，將文字取代為 **Salesperson**。

1. 若要重新命名 ** EmployeeNationalIDAlternateKey 資料行，請按兩下 ** EmployeeNationalIDAlternateKey ** ** 資料行標頭，並將文字取代為 ** EmployeeID ** ，然後按 ** Enter ** 。

1. 使用前面的步驟，將 **EmailAddress** 資料行重新命名為 **UPN**。

    *UPN 是使用者主體名稱的縮寫。*

1. 在左下的狀態列中，確認該查詢具有五個資料行和 18 個資料列。

## **設定 SalespersonRegion 查詢**

在這項工作中，您將設定 **SalespersonRegion** 查詢。

1. 在 [查詢]**** 窗格中，選取 **DimEmployeeSalesTerritory** 查詢。

1. 在 [查詢設定]**** 窗格中，將查詢重新命名為 **SalespersonRegion**。

1. 若要移除最後兩個資料行，請先選取 **DimEmployee** 資料行標頭。

1. 按下 **Ctrl** 鍵時，請選取 **DimSalesTerritory** 資料行標頭。

1. 以滑鼠右鍵按一下其中一個選取資料行標頭，然後在操作功能表中選取 [移除資料行]****。

1. 在狀態列中，驗證該查詢具有兩個資料行和 39 個資料列。

## **設定產品查詢**

在這項工作中，您將設定 **Product** 查詢。

*重要事項：提供詳細指示後，實驗室步驟將提供更簡潔的指示。如果您需要詳細的指示，您可以回到先前工作的步驟。*

1. **選取 DimProduct ** 查詢，並將查詢重新命名為 ** Product ** 。

1. 找出 **FinishedGoodsFlag** 資料行，然後篩選該資料行以擷取屬於成品 (亦即 TRUE) 的產品。

1. 移除所有資料行， ** 但下列專案除外 ** ：

    - ProductKey
    - EnglishProductName
    - StandardCost
    - Color
    - DimProductSubcategory

1. 請注意，**DimProductSubcategory** 資料行代表相關資料表 (其中包含 **Value** 連結)。

1. 在 [DimProductSubcategory]**** 資料行標頭中，選取資料行名稱右側的展開按鈕。

    ![資料行展開圖示](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image31.png)

1. 請參閱資料行的完整清單，然後選取 [ ** 選取所有資料 ** 行] 方塊以取消選取所有資料行。
2. 選取 ** [EnglishProductSubcategoryName ** ] 和 ** [DimProductCategory ** ]，然後取消核取 [ ** 使用原始資料行名稱做為前置詞 ** ] 核取方塊，然後選取 [ ** 確定 ** ]。

    *藉由選取這兩個數據行，將會套用轉換以聯結至 ** DimProductSubcategory ** 資料表，然後包含這些資料行。DimProductCategory 資料 ** 行 ** 實際上是資料來源中另一個相關資料表。*

    *查詢資料行名稱必須一律是唯一的。如果選取左方，此核取方塊會在每個資料行前面加上展開的資料行名稱（在此案例 ** 中為 DimProductSubcategory ** ）。由於已知選取的資料行名稱不會與 Product ** 查詢中的資料 ** 行名稱相撞，因此會取消選取選項。*

1. 請注意，轉換會導致新增兩個資料行，而且已移除 [DimProductSubcategory]**** 資料行。

1. 展開 **DimProductCategory** 資料行，然後只引進 **EnglishProductCategoryName** 資料行。

1. 將下列四個資料行重新命名：

    - 將 **EnglishProductName** 重新命名為 **Product**
    - 將 **StandardCost** 重新命名為 **Standard Cost** (包含空格)
    - 將 **EnglishProductSubcategoryName** 重新命名為 **Subcategory**
    - 將 **EnglishProductCategoryName** 重新命名為 **Category**

1. 在狀態列中，確認該查詢具有六個資料行和 397 個資料列。

## **設定轉銷商查詢**

在這項工作中，您將設定 ** Reseller ** 查詢。

1. **選取 DimReseller ** 查詢，然後重新命名為 ** Reseller ** 。

1. 移除所有資料行， ** 但下列專案除外 ** ：

    - ResellerKey
    - BusinessType
    - ResellerName
    - DimGeography

1. **展開 DimGeography ** 資料行，只 ** 包含 ** 下列三個數據行：

    - 縣/市
    - StateProvinceName
    - EnglishCountryRegionName

1. 在 [ ** 商務類型 ** ] 資料行標頭上，選取向下箭號，然後檢閱不同的資料行值，並注意 Warehouse ** 和 ** Ware House ** 值 ** 。

1. 以滑鼠右鍵按一下 **Business Type** 資料行標頭，然後選取 [取代值]****。

1. 在 [ ** 取代值] ** 視窗中，設定下列值：

    - 在 [要尋找的值]**** 方塊中，輸入 **Ware House**
    - 在 [取代為]**** 方塊中，輸入 ****

     ![取代值對話方塊](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image40.png)

1. 將下列四個資料行重新命名：

    - 將 **BusinessType** 重新命名為 **Business Type** (包含空格)
    - 將 **ResellerName** 重新命名為 **Reseller**
    - 將 **StateProvinceName** 重新命名為 **State-Province**
    - 將 **EnglishCountryRegionName** 重新命名為 **Country-Region**

1. 在狀態列中，確認該查詢具有六個資料行和 701 個資料列。

## **設定區域查詢**

在此工作中，您將設定 **Region** 查詢。

1. **選取 DimSalesTerritory ** 查詢，並將查詢重新命名為 ** Region ** 。

1. 將篩選套用至 **SalesTerritoryAlternateKey** 資料行，以移除值 0 (零)。

    *這會移除一個資料列。*

1. 移除所有資料行， ** 但下列專案除外 ** ：

    - SalesTerritoryKey
    - SalesTerritoryRegion
    - SalesTerritoryCountry
    - SalesTerritoryGroup

1. 重新命名下列三筆資料行：

    - 將 **SalesTerritoryRegion** 重新命名為 **Region**
    - 將 **SalesTerritoryCountry** 重新命名為 **Country**
    - 將 **SalesTerritoryGroup** 重新命名為 **Group**

1. 在狀態列中，確認該查詢具有四個資料行和 10 個資料列。

## **設定 Sales 查詢**

在這項工作中，您將設定 ** Sales ** 查詢。

1. **選取 FactResellerSales ** 查詢，並將其重新命名為 ** Sales ** 。

1. 移除所有資料行， ** 但下列專案除外 ** ：

    - SalesOrderNumber
    - OrderDate
    - ProductKey
    - ResellerKey
    - EmployeeKey
    - SalesTerritoryKey
    - OrderQuantity
    - UnitPrice
    - TotalProductCost
    - SalesAmount
    - DimProduct

        *注意：您可能會在 Power BI Desktop ** 實驗室的準備資料中 ** 召回一小部分 ** FactResellerSales 資料 ** 列遺漏 ** TotalProductCost ** 值。**已包含 DimProduct ** 資料行來擷取產品標準成本資料行，以協助修正遺漏值。*

1. 展開 [DimProduct]**** 資料行、取消選取所有資料行，然後僅包括 [StandardCost]**** 資料行。

1. 若要建立自訂資料行，請在 [新增資料行]**** 功能區索引標籤上，從 [一般]**** 群組中選取 [自訂資料行]****。

     ![圖片 5664](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image47.png)

1. 在 [自訂資料行]**** 視窗的 [新資料行名稱]**** 方塊中，將文字取代為 **Cost**。

1. 在 [自訂資料行公式]**** 方塊中，(在等號後面) 輸入下列運算式：
    - *您可以從 D：\PL300\Labs\02-load-data-with-power-query-in-power-bi-desktop\Assets\Snippets.txt ** 檔案複製運算式 ** 。*
    - *此運算式會測試 TotalProductCost ** 值是否 ** 遺失。如果遺漏，它會藉由將 OrderQuantity ** 值乘 ** 以 ** StandardCost ** 值來產生值，否則會使用現有的 ** TotalProductCost ** 值。*


    `
    if [TotalProductCost] = null then [OrderQuantity] * [StandardCost] else [TotalProductCost]
    `

1. 移除下列兩筆資料行：

    - TotalProductCost
    - StandardCost

1. 重新命名下列三筆資料行：

    - **OrderQuantity** 改為 **Quantity**
    - **UnitPrice** 改為 **Unit Price** (包含空格)
    - **SalesAmount** 改為 **Sales**

1. 若要修改資料行的資料類型，請在 [Quantity]**** 資料行標頭中，選取資料行名稱左側的 **1.2** 圖示，然後選取 [整數]****。

    *設定正確的資料類型很重要。當資料行包含數值時，如果您預期要執行數學計算，也請務必選擇正確的類型。*

     ![圖片 5667](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image50.png)

1. 將下列三個資料行資料類型修改為 [固定的小數位數]****。

    *固定的十進位數資料類型允許 19 位數，並允許更精確，以避免四捨五入錯誤。請務必針對財務值或匯率（例如匯率）使用固定的十進位數類型。*

    - 單價
    - 銷售
    - 成本

1. 在狀態列中，確認該查詢具有 10 個資料行和 999+ 個資料列。

    *每個查詢的預覽資料最多會載入 1000 個數據列。*

## **設定目標查詢**

在這項工作中，您將設定 **Targets** 查詢。

1. **選取 ResellerSalesTargets ** 查詢，然後重新命名為 ** [目標 ** ]。

1. 若要取消 12 個月資料行 (**M01**-**M12**) 樞紐，請先複選 [Year]**** 和 [EmployeeID]**** 資料行標頭。

1. 以滑鼠右鍵按一下其中一個選取資料行標頭，然後在操作功能表中選取 [取消其他資料行樞紐]****。

1. 請注意，資料行名稱現在會顯示在 [Attribute]**** 資料行中，而值會出現在 [Value]**** 資料行中。

1. 將篩選套用至 [Value]**** 資料行，以移除連字號 (-) 值。

    *您可能還記得來源 CSV 檔案中使用連字號字元來表示零 （0）。*

1. 重新命名下列兩筆資料行：

    - **MonthNumber ** 的屬性 ** ** （沒有空格）
    - **Value** 改為 **Target**

1. 若要準備 **MonthNumber** 資料行值，請以滑鼠右鍵按一下 [MonthNumber]**** 資料行標頭，然後選取 [取代值]****。

    *您現在會套用轉換來產生日期資料行。日期會衍生自 ** Year ** 和 ** MonthNumber ** 資料行。您將使用 ** [來自範例 ** 的資料行] 功能來建立資料行。*

1. 在 [取代值] ** 視窗中的 [ ** 值到尋找 ** ] 方塊中 ** ，輸入 ** M ** ，並將 ** [取代為 ** 空白]。

1. 將 [MonthNumber]**** 資料行的資料類型修改為 [整數]****。

1. 在 [新增資料行]**** 功能區索引標籤上，從 [一般]**** 群組中選取**來自範例的資料行**圖示。

    ![圖片 5675](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image59.png)

1. 請注意，第一個資料列是適用於 **2017** 年和 **7** 月。

1. 在 [Column1]**** 資料行的第一個格線儲存格中，開始輸入 **7/1/2017**，然後按 **Enter**。

    *虛擬機器會使用美國區域設定，因此此日期實際上是 2017 年 7 月 1 日。其他區域設定可能需要 ** 日期之前的 0 ** 。*

1. 請注意，方格儲存格會使用預測的值更新。

    *此功能已正確預測您正在結合 Year ** 和 MonthNumber ** 資料行的值 ** ** 。*

1. 另請注意查詢方格上方顯示的公式。

     ![圖片 5679](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image60.png)

1. 若要重新命名新的資料行，請按兩下 ** [ ** 合併的資料行] 標頭，並將資料行重新命名為 ** TargetMonth ** 。

1. 移除下列資料行：

    - 年份
    - MonthNumber

1. 修改下列資料行的資料類型：

    - **Target** 為固定的小數位數
    - **TargetMonth** 為日期

1. 若要將 **Target** 值乘以 1000，請選取 [Target]**** 資料行標頭，然後在 [轉換]**** 功能區索引標籤上，從 [數字資料行]**** 群組中選取 [標準]****，然後選取 [乘]****。

    *您可能會回想一下，目標值已儲存為數千個。*

     ![圖片 5682](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image63.png)

1. 在 [ ** 乘法 ** ] 視窗中的 [值 ** ] 方塊中 ** ，輸入 ** 1000 ** ，然後選取 [ ** 確定 ** ]。

1. 在狀態列中，確認該查詢具有三個資料行和 809 個資料列。

## **設定 ColorFormats 查詢**

在這項工作中，您將設定 **ColorFormats** 查詢。

1. **選取 ColorFormats ** 查詢，並注意第一個資料列包含資料行名稱。

1. 在 [首頁]**** 功能區索引標籤上，從 [轉換]**** 群組中選取 [使用第一個資料列作為標頭]****。

     ![圖片 5688](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image68.png)

1. 在狀態列中，確認該查詢具有三個資料行和 10 個資料列。

## **更新產品查詢**

在這項工作中，您將藉由合併 **ColorFormats** 查詢來更新 **Product** 查詢。

1. 選取 [Product]**** 查詢。

1. 若要合併 ColorFormats ** 查詢，請在 [ ** 首頁 ** ] 功能區索引標籤上，選取 ** [合併 ** 向下箭號]，然後選取 [ ** 合併查詢 ** ]。 **

    *合併查詢允許整合資料，在此案例中是來自不同資料來源 (SQL Server 和 CSV 檔案) 的資料。*

     ![圖片 5654](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image71.png)

1. 在 [合併]**** 視窗的 [Product]**** 查詢格線中，選取 [Color]**** 資料行標頭。

     ![圖片 5655](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image72.png)

1. 在 [Product]**** 查詢格線下的下拉式清單中，選取 [ColorFormats]**** 查詢。

     ![圖 21](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image73.png)

1. 在 [ColorFormats]**** 查詢格線中，選取 [Color]**** 資料行標頭。

1. 當 [ ** 隱私權等級 ** ] 視窗開啟時，針對這兩個數據源，在對應的下拉式清單中選取 [組織 ** ]，然後 ** 選取 ** [儲存 ** ]。

    *您可以為資料來源設定隱私權層級，以判斷是否可以在來源之間共用資料。視需要將每個資料來源設定為 ** 組織 ** ，即可共用資料。私人資料來源永遠無法與其他資料來源共用。這並不表示無法共用私人資料;這表示 Power Query 引擎無法在來源之間共用資料。*

     ![圖片 5691](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image74.png)

1. 在 [ ** 合併 ** ] 視窗中，使用預設 ** 的 [聯結種類 ** - 維護左外部] 的選取範圍，然後選取 [ ** 確定 ** ]。

1. 展開 [ColorFormats]**** 資料行，以包括下列兩個資料行：

    - 背景色彩格式
    - 字型色彩格式

1. 在狀態列中，確認該查詢現在具有八個資料行和 397 個資料列。

## **更新 ColorFormats 查詢**

在這項工作中，您將更新 **ColorFormats** 以停用載入。

1. 選取 [ColorFormats]**** 查詢。

1. 在 [查詢設定]**** 窗格中，選取 [所有屬性]**** 連結。

     ![圖片 322](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image80.png)

1. 在 [查詢屬性]**** 視窗中，取消選取 [啟用載入至報告]**** 核取方塊。

    *停用載入表示不會將它當做資料表載入資料模型。這樣做是因為查詢已與 ** Product 查詢合併，而 Product ** 查詢會啟用以載入資料模型。*

     ![圖片 323](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image81.png)

### **完成時間**

在此工作中，您將完成實驗室。

1. 請驗證您有八項查詢，並正確命名如下：

    - 銷售人員
    - SalespersonRegion
    - Products
    - 轉售商
    - 區域
    - Sales
    - 目標
    - ColorFormats (不會載入至資料模型)

1. 若要載入資料模型，請在 [檔案]**** Backstage 檢視上，選取 [關閉並套用]****。

    *所有啟用載入的查詢現在都會載入至資料模型。*

     ![圖片 326](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image83.png)

1. 在 [ ** 資料 ** ] 窗格中（位於右側），請注意載入至資料模型的七個數據表。

     ![圖 3](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image84.png)

1. 儲存 Power BI Desktop 檔案。

*您將於《在 Power BI Desktop 中設計資料模型》**** 實驗室中，設定資料模型的資料表和關聯性。*
