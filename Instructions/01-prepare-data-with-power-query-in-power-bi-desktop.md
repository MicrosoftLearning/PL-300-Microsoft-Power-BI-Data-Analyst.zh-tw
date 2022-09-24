---
lab:
  title: 在 Power BI Desktop 中準備資料
  module: Module 2 - Get Data in Power BI
---

# <a name="prepare-data-in-power-bi-desktop"></a>**在 Power BI Desktop 中準備資料**

**完成實驗室的估計時間為 45 分鐘**

In this lab you commence the development of a Power BI Desktop solution for the Adventure Works company. It involves connecting to source data, previewing the data, and using data preview techniques to understand the characteristics and quality of the source data.

在此實驗室中，您將了解如何：

- 開啟 Power BI Desktop

- 設定 Power BI Desktop 選項

- 連線至來源資料

- 預覽來源資料

- 使用資料預覽技術進一步了解資料

### <a name="lab-story"></a>**實驗室案例**

This lab is one of many in a series of labs that was designed as a complete story from data preparation to publication as reports and dashboards. You can complete the labs in any order. However, if you intend to work through multiple labs, for the first 10 labs, we suggest you do them in the following order:

1. **在 Power BI Desktop 中準備資料**

2. 在 Power BI Desktop 中載入資料

3. 在 Power BI Desktop 中設計資料模型

5. 在 Power BI Desktop 中建立 DAX 計算，第 1 部分

6. 在 Power BI Desktop 中建立 DAX 計算，第 2 部分

7. 在 Power BI Desktop 中設計報表，第 1 部分

8. 在 Power BI Desktop 中設計報表，第 2 部分

9. 建立 Power BI 儀表板

10. 在 Power BI Desktop 中執行資料分析

11. 強制執行資料列層級安全性

## <a name="exercise-1-prepare-data"></a>**練習 1：準備資料**

In this exercise you will create eight Power BI Desktop queries. Six queries will source data from SQL Server, and two from CSV files.

### <a name="task-1-save-the-power-bi-desktop-file"></a>**工作 1：儲存 Power BI Desktop 檔案**

在此工作中，您會先儲存 Power BI Desktop 檔案。

1. 若要開啟 Power BI Desktop，請在工作列上按一下 [Microsoft Power BI Desktop] 捷徑。

    ![圖 2](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image1.png)

1. 若要關閉 [開始使用] 視窗，請按一下視窗右上角的 [X]。

    ![圖 3](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image2.png)

1. 若要儲存檔案，請按一下 [檔案] 功能區索引標籤，以開啟 Backstage 檢視。

1. 選取 [儲存]。

    ![圖片 4](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image3.png)

1. 在 [另存新檔] 視窗中，瀏覽至 **D:\PL300\MySolution** 資料夾。

1. 在 [檔案名稱] 方塊中，輸入**銷售分析**。

    ![圖片 14](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image4.png)

1. 按一下 [儲存]。

    ![圖 17](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image5.png)

    提示：您也可以按一下位於左上角的 [儲存] 圖示來儲存檔案。

    ![圖 18](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image6.png)

### <a name="task-2-set-power-bi-desktop-options"></a>**工作 2：設定 Power BI Desktop 選項**

在此工作中，您將設定 Power BI Desktop 選項。

1. 在 Power BI Desktop 中，按一下 [檔案] 功能區索引標籤以開啟 Backstage 檢視。

1. 在左側，選取 [選項及設定]，然後選取 [選項]。

    ![圖片 1](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image7.png)

1. 在 [選項] 視窗中，在左側的 [目前的檔案] 群組中，選取 [資料載入]。

    ![圖 5](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image8.png)

    目前檔案的 [資料載入] 設定可讓您設定在建立模型時決定預設行為的選項。

1. 在 [關聯性] 群組中，取消選取兩個已經選取的選項。

    ![圖片 7](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image9.png)

    While having these two options enabled can be helpful when developing a data model, you disabled them earlier to support the lab experience. When you create relationships in the <bpt id="p1">**</bpt>Load Data in Power BI Desktop<ept id="p1">**</ept> lab, you’ll learn why you are adding each one.

1. 按一下 [確定]。

    ![圖 9](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image10.png)

1. 儲存 Power BI Desktop 檔案。

### <a name="task-3-get-data-from-sql-server"></a>**工作 3：從 SQL Server 取得資料**

在此工作中，您將根據 SQL Server 資料表建立查詢。

1. 在 [首頁] 功能區索引標籤上，從 [資料] 群組內，按一下 [SQL Server]。

    ![圖 19](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image11.png)

2. 在 [SQL Server 資料庫] 視窗的 [伺服器] 方塊中，輸入 **localhost**。

    ![圖 21](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image12.png)

    在此實驗室中，您會開始為 Adventure Works 公司開發 Power BI Desktop 解決方案。

3. 按一下 [確定]。

    ![圖 22](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image13.png)

4. 在 [導覽器] 視窗中，展開左側的 **AdventureWorksDW2020** 資料庫。

    這牽涉到連線到來源資料、預覽資料，以及使用資料預覽技術來了解來源資料的特性與品質。

    ![圖片 28](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image17.png)

5. 選取 (但不要核取) [DimEmployee] 資料表。

    ![圖 29](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image18.png)

6. 在右窗格中，請注意資料表資料的預覽。

    預覽資料可讓您判斷資料行與資料列範例。

7. 若要建立查詢，請選取下列六個資料表旁邊的核取方塊：

    - DimEmployee

    - DimEmployeeSalesTerritory

    - DimProduct

    - DimReseller

    - DimSalesTerritory

    - FactResellerSales

8. 若要將轉換套用至所選取資料表的資料，請按一下 [轉換資料]。

    You won’t be transforming the data in this lab. The objectives of this lab focus on exploring and profiling the data in the <bpt id="p1">**</bpt>Power Query Editor<ept id="p1">**</ept> window.

    ![圖片 30](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image19.png)

### <a name="task-4-preview-sql-server-queries"></a>**工作 4：預覽 SQL Server 查詢**

In this task you will preview the data of the SQL Server queries. First, you will learn relevant information about the data. You will also use column quality, column distribution, and column profile tools to understand the data and to assess data quality.

1. 在 [Power Query 編輯器] 視窗中的左側，注意 [查詢] 窗格。

    ![圖 31](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image20.png)

    [查詢] 窗格針對每個選取的資料表皆包含一個查詢。

2. 選取第一個查詢：[DimEmployee]。

    ![圖片 33](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image21.png)

    The <bpt id="p1">**</bpt>DimEmployee<ept id="p1">**</ept> table in the SQL Server database stores one row for each employee. A subset of the rows from this table represents the salespeople, which will be relevant to the model you’ll develop.

3. 在左下角的狀態列中，請注意資料表統計資料：資料表有 33 個資料行與 296 個資料列。

    ![圖 36](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image22.png)

4. 在資料預覽窗格中，水平捲動以檢閱所有資料行。

5. 請注意，最後五個資料行包含**資料表**或**值**連結。

    These five columns represent relationships to other tables in the database. They can be used to join tables together. You’ll join tables in the <bpt id="p1">**</bpt>Load Data in Power BI Desktop<ept id="p1">**</ept> lab.

6. 若要評估資料行品質，請在 [檢視] 功能區索引標籤上，從 [資料預覽] 群組內，選取 [資料行品質]。

    ![圖 35](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image23.png)

    資料行品質功能可讓您輕鬆地判斷資料行中有效、錯誤或空白值的百分比。

7. 針對 Position 資料行(第六個資料行)，請注意 94% 的資料列是空的 (Null)。

    ![圖片 38](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image24.png)

8. 若要評估資料行散發，請在 [檢視] 功能區索引標籤上，從 [資料預覽] 群組內部，檢查 [資料行散發]。

    ![圖片 40](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image25.png)

9. 再次檢閱 [職位] 資料行，並注意有四個相異值與一個唯一值。

10. 檢閱 **EmployeeKey** (第一個) 資料行的資料行散發，有 296 個相異值與 296 個唯一值。

    ![圖片 43](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image26.png)

    When the distinct and unique counts are the same, it means the column contains unique values. When modeling, it’s important that some model tables have unique columns. These unique columns can be used to create one-to-many relationships, which you will do in the <bpt id="p1">**</bpt>Model Data in Power BI Desktop, Part 1<ept id="p1">**</ept> lab.

11. 在 [查詢] 窗格中，選取 **DimEmployeeSalesTerritory** 查詢。

    ![圖片 44](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image27.png)

    The <bpt id="p1">**</bpt>DimEmployeeSalesTerritory<ept id="p1">**</ept> table stores one row for each employee and the sales territory regions they manage. The table supports relating many regions to a single employee. Some employees manage one, two, or possibly more regions. When you model this data, you’ll need to define a many-to-many relationship, which you’ll do in the <bpt id="p1">**</bpt>Model Data in Power BI Desktop, Part 2<ept id="p1">**</ept> lab.

12. 在 [查詢] 窗格中，選取 **DimProduct** 查詢。

    ![圖片 46](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image28.png)

    **DimProduct** 資料表會針對由公司銷售的每個產品，各包含一個資料列。

13. 水平捲動以顯示後面的資料行。

14. 請注意 **DimProductSubcategory** 資料行。

    當您於**在 Power BI Desktop 中載入資料**實驗室內將轉換新增至此查詢時，將會使用 **DimProductSubcategory** 資料行來聯結資料表。

15. 在 [查詢] 窗格中，選取 **DimReseller** 查詢。

    ![圖片 49](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image29.png)

    The <bpt id="p1">**</bpt>DimReseller<ept id="p1">**</ept> table contains one row per reseller. Resellers sell, distribute, or value add to the Adventure Works products.

16. 若要檢視資料行值，請在 [檢視] 功能區索引標籤上，從 [資料預覽] 群組內部，檢查 [資料行設定檔]。

    ![圖 41](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image30.png)

17. 選取 **BusinessType** 資料行標題。

18. 請注意，新的窗格會出現在 [資料預覽] 窗格下方。

19. 檢閱資料預覽窗格中的資料行統計資料和值分布。

20. 請注意資料品質問題：倉儲有兩個標籤 (**Warehouse** 與拼錯的 **Ware House**)。

    ![圖片 51](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image31.png)

21. 將游標停在 [Ware House] 列上方，並注意有五個具有此值的資料列。

    您將套用轉換，於**在 Power BI Desktop 中載入資料**實驗室內，將這五個資料列重新標記。

22. 在 [查詢] 窗格中，選取 **DimSalesTerritory** 查詢。

    ![圖片 52](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image32.png)

    The <bpt id="p1">**</bpt>DimSalesTerritory<ept id="p1">**</ept> table contains one row per sales region, including <bpt id="p2">**</bpt>Corporate HQ<ept id="p2">**</ept> (headquarters). Regions are assigned to a country, and countries are assigned to groups. In the <bpt id="p1">**</bpt>Model Data in Power BI Desktop, Part 1<ept id="p1">**</ept> lab, you’ll create a hierarchy to support analysis at region, country, or group level.

23. 在 [查詢] 窗格中，選取 **FactResellerSales** 查詢。

    ![圖片 54](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image33.png)

    [FactResellerSales] 資料表針對每個銷售訂單明細都會包含一個資料列；銷售訂單會包含一或多個明細項目。

24. 檢閱 **TotalProductCost** 資料行的資料行品質，並注意有 8% 的資料列是空的。

    ![圖片 63](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image34.png)

    此實驗室為一系列實驗室的其中之一，其設計用意是完整呈現資料準備到報表和儀表板發行的整個過程。

### <a name="task-5-get-data-from-a-csv-file"></a>**工作 5：從 CSV 檔案取得資料**

在此工作中，您將會根據 CSV 檔案建立查詢。

1. 若要加入新的查詢，請在 [Power Query 編輯器] 視窗的 [首頁] 功能區索引標籤上，從 [新增查詢] 群組內，按一下 [新增來源] 向下箭號，然後選取 [文字/CSV]。

    ![圖片 70](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image35.png)

2. 在 [開啟] 視窗中，瀏覽至 **D:\PL300\Resources** 資料夾，然後選取 **ResellerSalesTargets.csv** 檔案。

3. 按一下 [開啟]。

4. 在 [ResellerSalesTargets.csv] 視窗中，檢閱預覽資料。

5. 按一下 [確定]。

    ![圖片 71](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image36.png)

  
‎ 

6. 在 [查詢] 窗格中，注意 **ResellerSalesTargets** 查詢的加入。

    ![圖片 72](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image37.png)

    您可以依照任何順序完成實驗室。

7. 請注意，沒有任何資料行包含空白值。

    當沒有每月銷售目標時，會改為儲存連字號字元。

8. 檢閱每個資料行標頭中的圖示 (在資料行名稱的左邊)。

    ![圖片 74](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image38.png)

    然而，若您想要逐步完成多個實驗室，建議您依照下列順序完成前 10 個實驗室：

    您將會套用許多轉換，以達成僅由三個資料行所組成的不同圖形化結果：**在 Power BI Desktop 中載入資料**實驗室內的 **Date**、**EmployeeKey** 與 **TargetAmount**。

### <a name="task-6-get-additional-data-from-a-csv-file"></a>**工作 6：從 CSV 檔案取得其他資料**

在此工作中，您將根據不同的 CSV 檔案建立額外的查詢。

1. 使用先前工作中的步驟，依據 **D:\PL300\Resources\ColorFormats.csv** 檔案建立查詢。

    ![圖片 75](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image39.png)

    The <bpt id="p1">**</bpt>ColorFormats<ept id="p1">**</ept> CSV file contains one row per product color. Each row records the HEX codes to format background and font colors. You’ll integrate this data with the <bpt id="p1">**</bpt>DimProduct<ept id="p1">**</ept> query data in the <bpt id="p2">**</bpt>Load Data in Power BI Desktop<ept id="p2">**</ept> lab.

### <a name="task-7-finish-up"></a>**工作 7：完成**

在此工作中，您將完成實驗室。

1. 在 [檢視] 功能區索引標籤上，從 [資料預覽] 群組內，取消選取先前在此實驗室中啟用的三個資料預覽選項：

    - 資料行品質

    - 資料行散發

    - 資料行設定檔

    ![圖片 76](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image40.png)

2. 若要儲存 Power BI Desktop 檔案，請在 [Power Query 編輯器] 視窗中的 [檔案] Backstage 檢視上，選取 [儲存]。

    ![圖片 77](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image41.png)

3. 當系統提示您套用查詢時，請按一下 [稍後套用]。

    ![圖片 86](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image42.png)

    Applying the queries will load their data to the data model. You’re not ready to do that, as there are many transformations that must be applied first.

4. 若您想要開始下一個實驗室，請讓 Power BI Desktop 保持開啟狀態。

    您將會於《在 Power BI Desktop 中載入資料》實驗室中將各種轉換套用至查詢，接著套用這些查詢以將其載入資料模型中。
