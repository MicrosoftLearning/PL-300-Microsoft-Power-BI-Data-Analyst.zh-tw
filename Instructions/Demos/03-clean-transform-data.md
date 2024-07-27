---
demo:
  title: 在 Power BI 中清除、轉換及載入資料
  module: 'Clean, transform, and load data in Power BI'
---

# 在 Power BI 中清除、轉換及載入資料

## 套用查詢轉換

1. 首先，將轉換套用至Product查詢。

1. 移除 RetailPrice、Photo 和 Sales 資料行。

1. 將 Channels 資料行的資料類型變更為 [整數]。

1. 重新命名下列資料行：

    - ProductSKU 改為 SKU

    - ProductName 改為 Product

    - ProductCategory 改為 Category

    - ItemGroup 改為 Item Group

    - KitType 改為 Kit Type

1. 其次，將轉換套用至 Sales 查詢。

1. 移除所有資料行，下列項目除外：

    - OrderDate

    - ProductID

    - Quantity

    - UnitPrice

1. 將 UnitPrice 資料行的資料類型變更為 [固定小數位數]。

1. 將 UnitPrice 資料行重新命名為 Unit Price。

1. 複選 Quantity 和 Unit Price 資料行，然後根據複選數新增資料行。

1. 將新資料行重新命名為 Sales。

## 整合查詢

1. 使用 Excel 連接器建立新的查詢，並連線到 D：\Allfiles\Demo\Data\ProductCost.xlsx 檔案。

1. 移除 Product 資料行。

1. 將 ProductCost 資料行的資料類型變更為 [固定十進位數]。

1. 選取 Product 查詢，然後與 ProductCost 查詢合併，並與 SKU 資料行建立關聯。

1. 在 [隱私權等級] 視窗中，將 D：\ 的隱私權等級設定為 [組織]。

1. 展開 ProductCost 資料行，納入 ProductCost 資料行 (來自 ProductCost 查詢)。

1. 將新資料行重新命名為 Cost。

## 停用查詢並將其載入數據模型

1. 在 [查詢] 窗格中，停用 ProductCost 查詢。

1. 在 [首頁] 功能區索引標籤上，按兩下 [關閉與套用] 圖示。

1. 在 Power BI Desktop 中，指出 [數據] 窗格中的兩個數據表。

1. 儲存 Power BI Desktop 檔案。

1. 讓 Power BI Desktop 檔案保持開啟，供下一個示範使用。
