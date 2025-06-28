---
lab:
  title: 在 Power BI 中使用 DAX 時間智慧函式
  module: Use DAX time intelligence functions in Power BI
---

# 在 Power BI 中使用 DAX 時間智慧函式

## 實驗室案例

在此實驗室中，您將使用涉及時間智慧的 DAX 運算式來建立量值。

在此實驗室中，瞭解如何：

 - 使用各種時間智慧函式來作特定關注日期的篩選內容。

**此實驗室大約需要 15 分鐘的時間。**

## 開始使用

若要完成此練習，請先開啟網頁瀏覽器，然後輸入下列 URL 以下載 zip 檔案：

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/06-use-dax-time-intelligence/06-time-intelligence.zip`

將檔案解壓縮到 **C：\Users\Student\Downloads\06-time-intelligence** 資料夾。

**開啟 06-Starter-Sales Analysis.pbix** 檔案。

> _**注意**：您可以選取 **[取消**] 來關閉登入。關閉任何其他信息視窗。如果系統提示您套用變更，請選取 [ **稍後**套用]。_

## 建立 YTD 量值

在這項工作中，您將使用時間智慧函式來建立銷售年度到最新（YTD）量值。

1. 在 Power BI Desktop 的 [報表] 檢視中 **，在 [第 2** 頁] 上，請注意矩陣視覺效果，該矩陣視覺效果會在數據列上分組的年份和月份顯示各種量值。

2. 根據下列表達式，將量值新增至 `Sales` 數據表，並格式化為零小數位數：

    ```dax
    Sales YTD =
    TOTALYTD(
        SUM(Sales[Sales]),
        'Date'[Date],
        "6-30"
    )
    ```

    > _函 `TOTALYTD` 式會評估指定日期數據行的表達式，在此案例中是數據行的總 `Sales` 和。日期數據行必須屬於標示為日期數據表的日期數據表。_
    >
    > _函式也可以採用第三個選擇性自變數，代表一年的最後一個日期。沒有這個日期表示 12 月 31 日是年份的最後一個日期。對於 Adventure Works，6 月是他們年度的最後一個月，因此會使用 “6-30”。_

3. 將 `Sales` 欄位和 `Sales YTD` 量值新增至矩陣視覺效果。

4. 請注意年度內銷售值的累積。

    ![圖片 1](Linked_image_Files/06-use-dax-time-intelligence-functions_image21.png)

> _函 `TOTALYTD` 式會執行篩選作，特別是時間篩選作。例如，若要計算 2017 年 9 月的 YTD 銷售額（會計年度的第三個月），數據表上 `Date` 的所有篩選都會移除，並取代為從年初開始的新日期篩選（2017 年 7 月 1 日），並延伸至內容日期期間的最後日期（2017 年 9 月 30 日）。_
>
> _DAX 提供許多 [時間智慧函](/dax/time-intelligence-functions-dax/?azure-portal=true) 式，以支援常見的時間篩選作。_

## 建立 YoY 成長量值

在這項工作中，您將使用變數建立銷售 YoY 成長量值。

> 變數可協助您簡化公式，並在公式內多次使用邏輯時更有效率。 變數會以唯一的名稱宣告，而量值表達式必須在 關鍵詞之後 `RETURN` 輸出。 不同於其他一些編碼語言變數，DAX 變數只能在單一formula._

1. 根據下列表達式，將另一個量值新增至 `Sales` 數據表：

    ```dax
    Sales YoY Growth =
    VAR SalesPriorYear =
        CALCULATE(
            SUM(Sales[Sales]),
            PARALLELPERIOD(
                'Date'[Date],
                -12,
                MONTH
            )
        )
    RETURN
        SalesPriorYear
    ```

    > _變數 `SalesPriorYear` 會指派表示式，以計算修改內容中的數據行總和 `Sales` 。該內容會使用 函 `PARALLELPERIOD` 式，從篩選內容中的每個日期移回 12 個月。_

1. 將 `Sales YoY Growth` 量值新增至矩陣視覺效果。

1. 請注意，新量值會傳回 `BLANK` 前 12 個月（因為 2017 財年之前沒有記錄的銷售量）。

1. 請注意，`Sales YoY Growth`2018 年 7 月的量值_是 2017 年_ 7 月_的銷售值_。

    ![圖 2](Linked_image_Files/06-use-dax-time-intelligence-functions_image22.png)

    > _既然公式的「困難部分」已經過測試，您可以使用計算成長結果的最終公式來覆寫量值。_

1. 若要完成量值，請使用此公式覆 `Sales YoY Growth` 寫量值，並將它格式化為具有兩個小數字數的百分比：

    ```dax
    Sales YoY Growth =
    VAR SalesPriorYear =
        CALCULATE(
            SUM(Sales[Sales]),
            PARALLELPERIOD(
                'Date'[Date],
                -12,
                MONTH
            )
        )
    RETURN
        DIVIDE(
            (SUM(Sales[Sales]) - SalesPriorYear),
            SalesPriorYear
        )
    ```

1. 在公式的 子句中 `RETURN` ，請注意變數會參考兩次。

1. 確認 2018 年 7 月_的同比增長率_為 392.83%。

    ![圖 3](Linked_image_Files/06-use-dax-time-intelligence-functions_image23.png)

    > _同比增長量值指出，上一年同期銷售額增長近400%（或4倍）。_

1. 在 [模型] 檢視中，將這兩個新量值放入名為 Time intelligence_ 的_顯示資料夾中。

    ![圖片 4](Linked_image_Files/06-use-dax-time-intelligence-functions_image24.png)

1. 儲存 Power BI Desktop 檔案。

## 實驗室完成
