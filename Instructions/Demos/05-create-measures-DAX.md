---
demo:
  title: 在 Power BI 中使用 DAX 建立量值
  module: Create measures using DAX in Power BI
---
# 在 Power BI 中使用 DAX 建立量值

> **提示**：您可以從 D：\Allfiles\Demo\Resources\Snippets-Demo-05.txt 檔案複製所有計算。

## 建立計算資料表

1. 使用下列運算式建立計算資料表：

```dax
Date = CALENDARAUTO()
```

1. 切換至 [資料] 檢視，然後檢閱包含單一日期資料行的資料表。

建立計算結果欄

1. 將計算結果欄新增至 Date 資料表：

```dax
Year = "CY" & YEAR('Date'[Date])
```

1. 將另一個計算結果欄新增至 Date 資料表：

```dax
Month = FORMAT('Date'[Date], "YYYY-MM")
```

1. 在 [模型] 檢視中，將 Date 資料表的 Date 資料行拖曳至 Sales 資料表的 OrderDate 資料行，以建立關聯性。

1. 隱藏 Sales 資料表的 OrderDate 資料行。

1. 在 [日期] 資料表中，使用 [年] 和 [月] 階層建立 [行事曆] 階層。

1. 在 [報表] 檢視中，使用 [日期] 資料行將 [日期] 資料表標示為日期資料表。

1. 在矩陣視覺效果中，移除 Products 階層，然後以 Calendar 階層取代。

1. 將計算結果欄新增至 Sales 資料表：

```dax
Cost = 'Sales'[Quantity] * RELATED('Product'[Cost])
```

1. 將 Cost 資料行格式設為兩位小數位數。

## 建立快速量值

1. 將快速量值新增至 Sales 數據表，從 Sales 數據行減去成本數據行。

1. 將量值重新命名為 Profit。

1. 說明量值不會將資料儲存在模型中。

建立一般量值

1. 將量值新增至 Sales 資料表：

```dax
Profit Margin = DIVIDE([Profit], SUM('Sales'[Sales]))
```

1. 將 Profit Margin 資料行格式設為百分比。

1. 將另一個量值新增至 Sales 資料表：

```dax
Sales YTD = TOTALYTD(SUM('Sales'[Sales]), 'Date'[Date])
```

1. 將 Sales YTD 資料行格式設為兩位小數位數。

## 使用矩陣視覺效果驗證計算結果

1. 將 Cost、Profit、Profit Margin 和 Sales YTD 欄位新增至矩陣視覺效果。

1. 儲存 Power BI Desktop 檔案。

1. 讓 Power BI Desktop 檔案保持開啟，供之後的示範使用。
