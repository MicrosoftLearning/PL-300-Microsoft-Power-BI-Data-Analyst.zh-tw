---
lab:
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

## **開始使用**

在這項工作中，您將設定實驗室的環境。

*重要事項：如果您繼續執行先前的實驗室（且您已成功完成該實驗室），請勿完成這項工作;相反地，請從下一個工作繼續。*

1. 開啟 Power BI Desktop。

    ![Power BI Desktop 圖示](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

    *提示：根據預設，[用戶入門] 對話框會在 Power BI Desktop 前面開啟。**** 登入，然後關閉快顯。*

1. 若要開啟入門 Power BI Desktop 檔案，請選取 **[檔案] > [開啟報表] > [瀏覽報表**]。

1. 在 [ **開啟]** 視窗中，流覽至 **D：\PL300\Labs\10-row-level-security\Starter** 資料夾，然後開啟 **[銷售分析** ] 檔案。

1. 關閉任何可能開啟的資訊視窗。

1. 注意功能區下方的黃色警告訊息。 *此訊息會提醒您查詢尚未套用為模型數據表載入的事實。您稍後會在此實驗室中套用查詢。*
    
    *若要關閉警告訊息，請在黃色警告訊息右側選取 **[X**]。*

1. 若要建立檔案的複本，請移至 [檔案] > [ **另存新** 檔]，然後儲存至 **D：\PL300\MySolution** 資料夾。

1. 如果系統提示您套用變更，請選取 [稍後套用]****。

## **強制執行數據列層級安全性**

在這項工作中，您將強制執行數據列層級安全性，以確保銷售人員只能查看其指派區域中的銷售量。

1. 切換至 [資料] 檢視。

   ![圖片 5701](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image20.png)

1. 在 [ **數據]** 窗格中，選取 **Salesperson （Performance）** 數據表。


1. 檢閱資料，請注意 Michael Blythe (EmployeeKey 281) 具有以下 UPN 值：**michael-blythe@adventureworks.com**
    
    *您可能還記得 Michael Blythe 已指派給三個銷售區域：美國東北部、美國中部和美國東南部。*

1. 在 [ **模型]** 功能區索引卷標的 **[安全組** ] 內，選取 [ **管理角色**]。

    ![圖片 5700](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image21.png)

1. 在 [管理角色]**** 視窗中，選取 [建立]****。

1. 在方塊中，將選取的文字取代為角色的名稱： **Salespeople**，然後按 **Enter**。

   ![圖片 5703](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image23.png)

1. 若要指派篩選，請針對 **Salesperson （Performance）** 數據表選取省略號 （...） 字元，然後選取 [ **新增篩選 \| [UPN]**。

   ![圖片 5704](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image24.png)

1. 在 [**數據表篩選 DAX 表達式**] 方塊中，將 “Value”** 取代**為 **USERPRINCIPALNAME（），** 然後**** 儲存，以修改表達式。
    
    *USERPRINCIPALNAME（） 是數據分析表達式 （DAX） 函式，會傳回已驗證用戶的名稱。這表示 **Salesperson （Performance）** 數據表會依查詢模型之使用者的用戶主體名稱 （UPN） 進行篩選。*

   ![圖片 11](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image25.png)

1. 若要測試安全性角色，請在 [模型]**** 功能區索引標籤上，從 [安全性]**** 群組中選取 [檢視身分]****。

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

1. 若要刪除 Salespeople 角色，請在 [**模型]** 功能區索引標籤的**** [安全組**] 內，選取 **[管理角色**]。**

   ![圖片 16](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image33.png)

1. 在 [管理角色]**** 視窗中，選取 [刪除]****。 當系統提示您確認刪除時，請選取 [是]、[ **刪除**]。

   ![圖 17](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image34.png)

### **完成時間**

在此工作中，您將完成實驗室。

1. 選取 [ **儲存**]，然後儲存 Power BI Desktop 檔案以結束實驗室。

*注意：當 Power BI Desktop 檔案發行至 Power BI 服務 時，您必須完成發行後工作，才能將安全性主體對應至 **Salespeople** 角色。在此實驗室中，您不會這麼做。*
