---
lab:
  title: 保護 Power BI 中的數據存取
  module: Secure data access in Power BI
---

# 保護 Power BI 中的數據存取

## 實驗室案例

在此實驗室中，您將強制執行數據列層級安全性，以確保銷售人員只能分析其指派區域的銷售數據。

在此實驗室中，您會了解如何：

- 強制執行數據列層級安全性。
- 選擇動態和靜態方法。

**此實驗室大約需要 20 分鐘的時間。**

## 開始使用

若要完成此練習，請先開啟網頁瀏覽器，然後輸入下列 URL 以下載 zip 資料夾：

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/11-secure-data-access/11-secure-data.zip`

將資料夾解壓縮至 **C：\Users\Student\Downloads\11-secure-data** 資料夾。

**開啟 11-Starter-Sales Analysis.pbix** 檔案。

> ***注意**：您可以選取 **[取消**] 來關閉登入。 關閉任何其他信息視窗。 如果系統提示您套用變更，請選取 **[稍後**套用]。

## 強制執行資料列層級安全性

在這項工作中，您將強制執行數據列層級安全性，以確保銷售人員只能查看其指派區域中的銷售量。

1. 切換至 [數據表] 檢視。

   ![圖片 5701](Linked_image_Files/11-secure-data-access_image20.png)

1. 在 [ **數據]** 窗格中，選取 **Salesperson （Performance）** 數據表。

1. 檢閱資料，請注意 Michael Blythe (EmployeeKey 281) 具有以下 UPN 值：**`michael-blythe@adventureworks.com`**
    
    > *您可能還記得 Michael Blythe 已指派給三個銷售區域：美國東北部、美國中部和美國東南部。*

1. 在 [ **首頁** ] 功能區索引標籤的 **[安全組** ] 內，選取 [ **管理角色**]。

    ![圖片 5700](Linked_image_Files/11-secure-data-access_image21.png)

1. 在 [**管理安全性角色] 視窗中的 **[角色****] 區段中，選取 [**新增**]。

1. 在方塊中，將選取的文字取代為角色的名稱： **Salespeople**，然後按 **Enter**。

   ![圖片 5703](Linked_image_Files/11-secure-data-access_image23.png)

1. 若要指派篩選，請選取 **Salesperson （Performance）** 數據表，然後選取 [篩選數據 **] 區段中的 **[**切換至 DAX 編輯器**]。

   ![圖片 5703](Linked_image_Files/11-secure-data-access_image24.png)

1. 在 [DAX 編輯器] 方塊中，輸入下列表示式：

    ```DAX
    [UPN] = USERPRINCIPALNAME()
    ```

   ![圖片 11](Linked_image_Files/11-secure-data-access_image25.png)

    > *USERPRINCIPALNAME（） 是數據分析表達式 （DAX） 函式，會傳回已驗證用戶的名稱。這表示 **Salesperson （Performance）** 數據表會依查詢模型之使用者的用戶主體名稱 （UPN） 進行篩選。*

1. 選取 [ **儲存** 並 **關閉**]。

1. 若要測試安全性角色，請在 [**首頁] 功能區索引卷標的 [安全組 **] 內**，選取 [**檢視身分****]。

   ![圖片 5708](Linked_image_Files/11-secure-data-access_image27.png)

1. 在 [以角色身分檢視]**** 視窗中，選取 [其他使用者]**** 項目，然後在對應的方塊中輸入：**`michael-blythe@adventureworks.com`**

1. **檢查 Salespeople** 角色，然後**確定**。
    
    > *此設定會導致使用 [Salespeople]**** 角色，並以 Michael Blythe 的姓名模擬使用者。*

   ![圖片 5709](Linked_image_Files/11-secure-data-access_image28.png)

1. 請注意報表頁面上方的黃色橫幅，其中描述測試安全性內容。

   ![圖片 13](Linked_image_Files/11-secure-data-access_image30.png)

1. 在資料表視覺效果中，請注意只會列出銷售人員 **Michael Blythe**。

   ![圖片 5713](Linked_image_Files/11-secure-data-access_image31.png)

1. 若要停止測試，請選取黃色橫幅右側的 [停止檢視]****。

   ![圖片 5712](Linked_image_Files/11-secure-data-access_image32.png)

1. 若要刪除 Salespeople** 角色，請在 [首頁 **] 功能區索引標籤的 ****[安全組**] 內，選取 [**管理角色**]。**

   ![圖片 16](Linked_image_Files/11-secure-data-access_image33.png)

1. 在 [**管理安全性角色]** 視窗中，選取 Salespeople** 角色上的**省略號 （...），然後選取 [**刪除**]。 當系統提示您確認刪除時，請選取 [是]、[ **刪除**]。

   ![圖片 34](Linked_image_Files/11-secure-data-access_image34.png)

*注意：當 Power BI Desktop 檔案發佈至 Power BI 服務 時，您必須完成發行後工作，才能將安全性主體對應至 **Salespeople** 角色。在此實驗室中，您不會這麼做。*

## 實驗室完成
