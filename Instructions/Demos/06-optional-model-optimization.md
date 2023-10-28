---
lab:
  "\_\_ title": (Optional) Optimize model performance in Power BI
  "\_\_ module": Optimize model performance in Power BI
---

#  (選擇性) 優化模型效能

## 檢閱 DirectQuery 模型設計

> **注意**：此示範會使用不同的Power BI Desktop檔案。

1. 開啟 D:\PL300\Demo\Resources\AW Sales Analysis.pbix 檔案。

1. 如果系統提示您連線至資料來源，請按一下 [連線]。

1. 在右下角指出資料模型包含 DirectQuery 資料表。

1. 將 Power BI Desktop 檔案儲存至 D:\PL300\Demo\MySolution 資料夾。

1. 在 [模型] 檢視中，介紹包括兩個相關資料表的模型設計。

1. 在 [報表] 檢視中，選取 Fiscal Year 交叉分析篩選器中的不同項目來與報表互動。

1. 在任何月份的資料行上鑽研，以顯示訂單詳細資料。

1. 返回 [銷售摘要] 頁面。

## 檢閱查詢效能

1. 在 [檢視] 功能區索引標籤上，顯示 [效能分析器] 窗格。

1. 重新整理視覺效果，然後依月份視覺效果展開交叉分析篩選器和 Sales。

1. 指出他們使用了 DirectQuery 模式， (資料來源) 要求資料。

## 設定雙重儲存資料表

1. 在 [模型] 檢視中 ，選取 Date 資料表，然後選取儲存模式為 [雙重]。

1. 資料匯入後，切換至 [報表] 檢視，然後在 [效能分析器] 窗格中重新整理視覺效果。

1. 指出現在會從模型快取查詢 Date 資料表。

## 建立彙總

1. 開啟 Power Query 編輯器視窗，然後在 [查詢] 窗格中複製 Reseller Sales 查詢。

1. 將新的查詢重新命名為 Reseller Sales Agg。

1. 依轉換套用群組，如下所示：

    - 依 OrderDate 分組。

    - 新增資料行：Sales，這是 SalesAmount 資料行的加總。

1. 關閉並套用查詢。

1. 在 [模型] 檢視中，將 Reseller Sales Agg 資料表的儲存模式設定為 [匯入]。

1. 建立從 Date 資料表 Date 資料行對應到 Reseller Sales Agg 資料表 OrderDate 資料行的關聯性 — 請確定資料行基數已設定為一對多，且 Date 資料表是一的那方。

1. 管理 Reseller Sales Agg 資料表上的彙總：

    - OrderDate：依 Reseller Sales 資料表 OrderDate 資料行分組。

    - Sales：加總 Reseller Sales 資料表 SalesAmount 資料行。

1. 指出彙總資料表現在已隱藏。

1. 切換至 [報表] 檢視，然後在 [效能分析器] 窗格中重新整理視覺效果。

1. 指出現在會從模型快取查詢 Sales by Month 資料表。

1. 從任何月份鑽研，並指出資料表中的詳細資料是作為 DirectQuery 從資料來源要求所得來。

1. 儲存 Power BI Desktop 檔案。

1. 關閉 Power BI Desktop。

> **注意**：您不會再次使用此Power BI Desktop解決方案。
