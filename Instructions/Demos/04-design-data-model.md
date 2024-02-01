---
demo:
  course: 'PL-300, DP-605'
  title: 在 Power BI 中設計資料模型
  module: Design a data model in Power BI
---
# 在 Power BI 中設計資料模型

## 檢閱程式碼

1. 在 [數據] 窗格中，展開所有數據表以顯示所有欄位。

1. 在 Sales 資料表中，指出自動建立的 OrderDate 階層。

1. 說明將在下一個示範中建立 Date 資料表。

1. 在 [模型] 檢視中，將游標停留在兩個資料表之間自動建立的關聯性上。

1. 說明篩選條件如何從 Product 資料表傳播至 Sales 資料表。

## 建立階層

1. 根據 Product 資料表的 Category 資料行建立階層。

1. 將階層重新命名為 Products。

1. 將 Product 資料行新增為第二層。

## 設定模型屬性

1. 隱藏兩個 ProductID 資料行。

1. 將 Quantity 資料行格式設為使用千位分隔符。

1. 複選 Sales 和 Unit Price 資料行，將其格式設為使用兩位小數位數。

## 使用矩陣視覺效果驗證模型設計

1. 在 [報表] 檢視中，將矩陣視覺效果新增至頁面，然後調整大小以填滿整個頁面。

1. 將 Products 階層新增至資料列，然後新增 Quantity、Sales 和 Unit Price 欄位。

1. 展開 Products 階層的所有層級。

1. 指出 Unit Price 值是價格的加總，這並不正確。

1. 在 [數據] 窗格中，選取 [單位價格] 字段，並將其摘要設定為使用 [平均值]。

1. 從矩陣視覺效果中移除 Sum of Unit Price 資料行，然後再次新增 Unit Price 欄位。

1. 儲存 Power BI Desktop 檔案。

1. 讓 Power BI Desktop 檔案保持開啟，供下一個示範使用。
