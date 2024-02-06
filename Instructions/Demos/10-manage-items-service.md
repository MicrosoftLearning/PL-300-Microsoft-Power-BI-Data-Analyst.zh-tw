---
demo:
  course: PL-300
  title: 在 Power BI 中管理檔案和語意模型
  module: Deploy and manage Power BI service items
---
# 在 Power BI 中管理檔案和語意模型

## 準備閘道資料重新整理

> **請注意** ，在個人模式中使用數據閘道時，不需要下列步驟。 您可以直接進入下一個目標 (設定閘道)。

1. 在 Power BI Desktop 中，開啟 Power Query 編輯器視窗，然後選取 **ProductCost** 查詢。

1. 編輯 [來源] 步驟，然後修改檔案路徑以使用檔案共用，如下所示：

    `\\DATA-AI\Data\ProductCost.xlsx`

1. 關閉並套用 Power Query 編輯器視窗。

1. 儲存 Power BI Desktop 檔案。

1. 將 Power BI Desktop 檔案發佈至工作區，覆寫服務中的語意模型和報表。

## 設定閘道 (個人模式)

1. 在講師的 Power BI 服務 中，重載 [F5] 語意模型設定頁面。

1. 展開 [閘道 連線 ion] 區段，並指出未安裝任何閘道。

1. 使用下載下拉式清單 (位於右上方)，然後選取 [資料閘道]。

1. 在新網頁中下載個人模式閘道。

1. 下載完畢後，開啟下載的檔案。

1. 使用講師帳戶的登入資訊來完成閘道設定。

1. 設定之後，返回並重載語意模型設定頁面。

1. 指派個人閘道，並編輯兩個資料來源的認證。

1. 針對這兩個資料來源，將驗證方法設定為 **WindowsWithoutImpersonation**，並將隱私權等級設定為 [組織]****。

1. 您可以選擇性展開 [排程重新整理]**** 區段，並示範如何設定週期性排程。

## 重新整理語意模型

1. 重新整理語意模型之前，請先開啟 **[銷售監視]** 儀錶板。

1. 編輯 Sales、Profit Margin 圖格的詳細數據，以顯示上次重新整理時間。

1. 以滑鼠右鍵按兩下 `D:\Allfiles\Demo\Resources\UpdateDatabase-LoadAdditionalSales.ps1` 檔案，然後使用PowerShell執行。 *此腳本會將 2020 年 12 月的銷售數據載入資料庫中。*

1. 在講師的 Power BI 服務 中，從 [流覽] 窗格重新整理 **[銷售分析**] 語意模型。

1. 重新整理完成時，指出儀錶板磚 **2020** 年 12 月數據行的顯示方式，以及重新整理時間現在是 **現在**。
