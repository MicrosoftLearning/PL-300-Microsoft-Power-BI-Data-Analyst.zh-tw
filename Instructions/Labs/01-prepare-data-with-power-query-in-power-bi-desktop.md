---
lab:
  title: 在 Power BI Desktop 中取得數據
  module: Get Data in Power BI
---

# 在 Power BI Desktop 中取得數據

## **實驗室案例**

此實驗室旨在介紹 Power BI Desktop 應用程式、如何連線到資料、以及如何使用資料預覽技術來瞭解來源資料的特性和品質。 學習目標是：

- 開啟 Power BI Desktop
- 線上到不同的數據來源
- 使用 Power Query 預覽源數據
- 在 Power Query 中使用數據分析功能

**此實驗室大約需要30分鐘的時間。**

## 開始使用 Power BI Desktop

若要完成此練習，請先開啟網頁瀏覽器，然後輸入下列 URL 以下載 zip 資料夾：

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/01-prepare-data-with-power-query-in-power-bi-desktop/01-prepare-data.zip`

將資料夾解壓縮至 **C：\Users\Student\Downloads\01-prepare-data** 資料夾。

**開啟 01-Starter-Sales Analysis.pbix** 檔案。

- 此入門檔案已特別設定，可協助您完成實驗室。 入門檔案中已停用下列報表層級設定：

  - 數據載入>第一次載入時從數據源匯入關聯性
  - 數據載入>載入數據之後自動偵測新的關聯性

## 從 SQL Server 取得資料

此工作會教導您如何連線到 SQL Server 資料庫並匯入數據表，以在 Power Query 中建立查詢。

1. 在 [首頁]**** 功能區索引標籤上，從 [資料]**** 群組內選取 [SQL Server]****。

     ![SQL Server 取得數據圖示](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image11.png)

1. 在 [**SQL Server 資料庫] 視窗中的 [伺服器 **]** 方塊中**，輸入 **localhost** 並將 [資料庫 **] 保留**空白，然後選取 [**確定**]。

    > ***注意**：在此實驗室中，您將使用 **localhost** 線上到 SQL Server 資料庫，因為閘道數據源無法解析 **localhost**。 建立您自己的解決方案時，這不是建議的做法。*

1. 如果系統提示您輸入認證，請選取 [Windows > [使用我目前的認證 **]，然後**選取 **[連線**]。

1. 如果您收到無法建立加密連線的警告，請選取 [ **確定** ]。

1. 在 [ **導覽器]** 窗格中，展開 **AdventureWorksDW2020** 資料庫。

    > ***注意：**AdventureWorksDW2020** 資料庫是以 AdventureWorksDW2017** 範例資料庫為基礎****。 它已修改為支援課程實驗室的學習目標。*

1. **選取 DimEmployee** 數據表，並注意數據表數據的預覽。

     ![指出具有 DimEmployee 的 AdventureWorksDW2020 資料庫](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image18.png)

    > ***注意**：預覽數據可讓您查看數據行和數據列範例。*

1. 若要匯入數據表數據， **請選取下表旁的複選框** ：

    - DimEmployee
    - DimEmployeeSalesTerritory
    - DimProduct
    - DimReseller
    - DimSalesTerritory
    - FactResellerSales

1. 選取 **[轉換數據**] 以完成此工作，這會開啟 Power Query 編輯器 - 讓下一個工作保持開啟狀態。

您現在已從 SQL Server 資料庫連線到六個數據表。

## **預覽 Power Query 編輯器 中的數據**

此工作引進 Power Query 編輯器，並可讓您檢閱及分析數據。 這可協助您判斷稍後如何清除和轉換數據。 您也會檢閱前置詞為 「Dim」 的維度數據表，以及前置詞為 「Fact」 的事實數據表。

1. 在 [Power Query 編輯器]**** 視窗中的左側，注意 [查詢]**** 窗格。 [查詢]**** 窗格針對每個選取的資料表皆包含一個查詢。

     ![已載入的查詢清單](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image20.png)

1. 選取第一個查詢：[DimEmployee]****。

    > ***SQL Server 資料庫中的 DimEmployee** 數據表會為每個員工儲存一個數據列。此數據表中數據列的子集代表銷售人員，這會與您即將開發的模型相關。*

1. 在狀態列的左下角，會提供一些數據表統計數據：數據表有 33 個數據行和 296 個數據列。

     ![33 個數據行、296 個數據列的計數](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image22.png)

1. 在資料預覽窗格中，水平捲動以檢閱所有資料行。 請注意，最後五個資料行包含**資料表**或**值**連結。

    > *這五個數據行代表資料庫中其他數據表的關聯性。它們可用來將數據表聯結在一起。您將在 Power BI Desktop** 實驗室的**載入轉換資料中聯結資料表。*

1. 若要評估資料行品質，請在 [檢視]**** 功能區索引標籤上，從 [資料預覽]**** 群組內，選取 [資料行品質]****。 資料行品質功能可讓您輕鬆地判斷資料行中有效、錯誤或空白值的百分比。

     ![功能區中的數據行質量選取](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image23.png)

1. 請注意， **Position** 數據行有 94% 空白 （Null） 資料列。

     ![顯示 94% 空白資料列的數據行品質](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image24.png)

1. 若要評估資料行散發，請在 [檢視]**** 功能區索引標籤上，從 [資料預覽]**** 群組內部，檢查 [資料行散發]****。

1. 再次檢閱 [職位]**** 資料行，並注意有四個相異值與一個唯一值。

1. 檢閱 EmployeeKey** 數據行的數據**行分佈—有 296 個相異值，以及 296 個唯一值。

     ![顯示296個相異、296個唯一值的數據行分佈](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image26.png)

    > ***注意**：當相異和唯一計數相同時，表示數據行包含唯一值。 建立模型時，某些模型資料表必須包含唯一資料行。 這些唯一的數據行可用來建立一對多關聯性，您將在Power BI Desktop**實驗室的**模型數據中執行此關聯性。*

1. 在 [查詢]**** 窗格中，選取 **DimProduct** 查詢。

    > ***DimProduct** 數據表包含公司銷售的每個產品一個數據列。*

1. 在 [查詢]**** 窗格中，選取 **DimReseller** 查詢。

    > ***DimReseller** 資料表包含每個轉銷商一個數據列。轉銷商銷售、散發或增值至 Adventure Works 產品。*

1. 若要檢視資料行值，請在 [檢視]**** 功能區索引標籤上，從 [資料預覽]**** 群組內部，檢查 [資料行設定檔]****。

1. **選取 BusinessType** 數據行標頭，並注意數據預覽窗格下方的新窗格。 檢閱資料預覽窗格中的資料行統計資料和值分布。

    > *請注意數據質量問題：倉儲有兩個標籤（**倉儲**和拼錯的 **Ware House**）。*

     ![BusinessType 數據行的值分佈](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image31.png)

1. 將游標停在 [Ware House]**** 列上方，並注意有五個具有此值的資料列。

1. 在 [查詢]**** 窗格中，選取 **DimSalesTerritory** 查詢。  

    > ***DimSalesTerritory** 數據表包含每個銷售區域的一個數據列，包括**公司總部**（總部）。區域會指派給國家/地區，並將國家/地區指派給群組。在 **Power BI Desktop** 實驗室的模型數據中，您將建立階層以支援區域、國家/地區或群組層級的分析。*

1. 在 [查詢]**** 窗格中，選取 **FactResellerSales** 查詢。

    > ***FactResellerSales** 數據表會針對每個銷售訂單明細包含一個數據列，銷售訂單包含一或多個明細專案。*

1. 檢閱 **TotalProductCost** 資料行的資料行品質，並注意有 8% 的資料列為空白。

    > *遺漏 **TotalProductCost** 資料行值是數據質量問題。*

## **從 CSV 檔案取得數據**

在這項工作中，您將根據 CSV 檔案建立新的查詢。

1. 若要新增查詢，請在 [Power Query 編輯器]**** 視窗的 [首頁]**** 功能區索引標籤上，從 [新增查詢]**** 群組內選取 [新增來源]**** 向下箭號，然後選取 [文字/CSV]****。

1. 流覽至 **01-prepare-data > ResellerSalesTargets.csv** 檔案。 選取**開啟**。

1. 在 [ResellerSalesTargets.csv]**** 視窗中，檢閱預覽資料。 選取 [確定]。

1. 在 [查詢]**** 窗格中，注意 **ResellerSalesTargets** 查詢的加入。

    > ***ResellerSalesTargets** CSV 檔案包含每個銷售人員每年一個數據列。每個數據列都會記錄 12 個每月銷售目標（以千為單位表示）。Adventure Works 公司的營業年將於 7 月 1 日開始。*

1. 請注意，沒有任何資料行包含空白值。  當沒有每月銷售目標時，會改為儲存連字號字元。

1. 檢閱每個資料行標頭中的圖示 (在資料行名稱的左側)。 圖示代表資料行資料類型。 **123** 是整數，而 **ABC** 是文字。

     ![資料行資料類型](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image38.png)

1. 重複步驟，根據 **ColorFormats.csv** 檔案建立查詢。

    > ***ColorFormats** CSV 檔案包含每個產品色彩一個數據列。每個數據列都會記錄 HEX 程式代碼，以格式化背景和字型色彩。*

您現在應該有兩個新的查詢 **：ResellerSalesTargets** 和 **ColorFormats**。

 ![查詢清單](Linked_image_Files/01-all-queries-loaded.png)

## 實驗室完成
