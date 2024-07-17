---
lab:
  course: PL-300
  title: 強制執行資料列層級安全性
  module: Enforce Row-Level Security
---


# **強制執行資料列層級安全性**

## **實驗室案例**

在此實驗室中，您將強制執行數據列層級安全性，以確保銷售人員只能分析其指派區域的銷售數據。

在此實驗室中，您將了解如何：

- 強制執行資料列層級安全性
- 選擇動態和靜態方法

**此實驗室大約需要 20 分鐘的時間。**

## **開始**

在這項工作中，您將設定實驗室的環境。

*重要事項：如果您繼續執行先前的實驗室（且您已成功完成該實驗室），請勿完成這項工作;相反地，請從下一個工作繼續。*

1. 開啟 Power BI Desktop。

    ![Power BI Desktop 圖示](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

1. 若要開啟入門 Power BI Desktop 檔案，請選取 **[開啟>瀏覽此裝置**。

1. 在 [ **開啟]** 視窗中，流覽至 **D：\Allfiles\Labs\10-row-level-security\Starter** 資料夾，然後開啟 **[銷售分析** ] 檔案。

   *注意：此時，如果您尚未登入，Power BI 會要求您登入。您可以登入或選取 [ **取消** ]，然後繼續實驗室。*

1. 關閉任何可能開啟的資訊視窗。

1. 請注意功能區下方的警告訊息。 *此訊息會提醒您查詢尚未套用為模型數據表載入的事實。您稍後會在此實驗室中套用查詢。*
    
    *若要關閉警告訊息，請在警告訊息右側選取 **[X**]。*

1. 若要建立檔案的複本，請移至 [檔案] > [ **另存新** 檔]，然後儲存至 **D：\Allfiles\MySolution** 資料夾。

1. 如果系統提示您套用變更，請選取 [稍後套用]****。

## **強制執行數據列層級安全性**

在這項工作中，您將強制執行數據列層級安全性，以確保銷售人員只能查看其指派區域中的銷售量。

1. 切換至 [數據表] 檢視。

   ![圖片 5701](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image20.png)

1. 在 [ **數據]** 窗格中，選取 **Salesperson （Performance）** 數據表。


1. 檢閱資料，請注意 Michael Blythe (EmployeeKey 281) 具有以下 UPN 值：**michael-blythe@adventureworks.com**
    
    *您可能還記得 Michael Blythe 已指派給三個銷售區域：美國東北部、美國中部和美國東南部。*

1. 在 [ **首頁** ] 功能區索引標籤的 **[安全組** ] 內，選取 [ **管理角色**]。

    ![圖片 5700](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image21.png)

1. 在 [**管理安全性角色] 視窗中的 **[角色****] 區段中，選取 [**新增**]。

1. 在方塊中，將選取的文字取代為角色的名稱： **Salespeople**，然後按 **Enter**。

   ![圖片 5703](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image23.png)

1. 若要指派篩選，請選取 **Salesperson （Performance）** 數據表，然後選取 [篩選數據 **] 區段中的 **[**切換至 DAX 編輯器**]。

   ![螢幕快照 2024-04-18 144345](https://github.com/afelix-95/PL-300-Microsoft-Power-BI-Data-Analyst/assets/148110824/1308d47f-2cca-4f88-9237-b02b66b4cf1e)

1. 在 [DAX 編輯器] 方塊中，輸入下列表示式：

    **DAX**

    ```
    [UPN] = USERPRINCIPALNAME()
    ```
    
    *USERPRINCIPALNAME（） 是數據分析表達式 （DAX） 函式，會傳回已驗證用戶的名稱。這表示 **Salesperson （Performance）** 數據表會依查詢模型之使用者的用戶主體名稱 （UPN） 進行篩選。*

   ![圖片 11](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image25.png)

1. 選取 [ **儲存** 並 **關閉**]。

1. 若要測試安全性角色，請在 [**首頁] 功能區索引卷標的 [安全組 **] 內**，選取 [**檢視身分****]。

   ![圖片 5708](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image27.png)

1. 在 [以角色身分檢視]**** 視窗中，選取 [其他使用者]**** 項目，然後在對應的方塊中輸入：**michael-blythe@adventureworks.com**

1. **檢查 Salespeople** 角色，然後**確定**。
    
    *此設定會導致使用 [Salespeople]**** 角色，並以 Michael Blythe 的姓名模擬使用者。*

   ![圖片 5709](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image28.png)

1. 請注意報表頁面上方的黃色橫幅，其中描述測試安全性內容。

   ![圖片 13](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image30.png)

1. 在資料表視覺效果中，請注意只會列出銷售人員 **Michael Blythe**。

   ![圖片 5713](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image31.png)

1. 若要停止測試，請選取黃色橫幅右側的 [停止檢視]****。

   ![圖片 5712](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image32.png)

1. 若要刪除 Salespeople** 角色，請在 [首頁 **] 功能區索引標籤的 ****[安全組**] 內，選取 [**管理角色**]。**

   ![圖片 16](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image33.png)

1. 在 [**管理安全性角色]** 視窗中，選取 Salespeople** 角色上的**省略號 （...），然後選取 [**刪除**]。 當系統提示您確認刪除時，請選取 [是]、[ **刪除**]。

   ![螢幕快照 2024-04-18 145556](https://github.com/afelix-95/PL-300-Microsoft-Power-BI-Data-Analyst/assets/148110824/deeb4eac-b639-433d-a9d4-29c8e127008e)

### **完成時間**

在此工作中，您將完成實驗室。

1. 選取 [ **儲存**]，然後儲存 Power BI Desktop 檔案以結束實驗室。

*注意：當 Power BI Desktop 檔案發行至 Power BI 服務 時，您必須完成發行後工作，才能將安全性主體對應至 **Salespeople** 角色。在此實驗室中，您不會這麼做。*
