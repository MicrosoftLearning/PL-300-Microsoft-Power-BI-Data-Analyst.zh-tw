---
demo:
  title: 在 Power BI 中強制執行資料列層級安全性
  module: Secure data access in Power BI
---

# 在 Power BI 中強制執行資料列層級安全性

## 將安全性資料表新增至模型

1. 在 Power BI Desktop 中，開啟 [Power Query 編輯器] 視窗。

1. 根據檔案新增`D:\Demo\Data\**ManagerCategory**.xlsx` 查詢。

1. 使用**檔案中的 ManagerCategory** 表格。

1. 移除**Manager** 資料行。

1. 以分號分隔符號分割**Category** 資料行，並分割成多個資料列 (進階選項)。

1. 在 電子郵件 欄**中，將值**<ty-johnston@tailspintoys.com>** 取代為收件者帳戶 （來自MySettings.txt檔案）。**

1. 指出該用戶能夠看到三個產品類別：**集體推介、訓練師和戰鳥**。

1. 關閉並套用查詢。

1. 在 [模型] 檢視中，在 [類別]** 資料行相關的**[ManagerCategory]**** 和 [產品] 資料表之間建立關聯性。

1. 將交叉篩選方向設定為單一 （**ManagerCategory** 篩選產品）。

1. 隱藏**ManagerCategory** 資料表。

## 新增角色

1. 在報表檢視中，開啟 [管理角色]，然後建立名為 [管理員 **] 的角色**。

1. 在角色中，篩選**ManagerCategory** 資料表 [電子郵件地址] 資料行，如下所示：

  ```dax
   [Email] = USERPRINCIPALNAME()
   ```

1. **儲存**。

## 驗證角色

1. 開啟 [檢視身分]，然後設定下列項目：

    - 其他使用者：勾選，然後輸入收件者帳戶。

    - 管理員角色：檢查

1. 指出篩選器視覺效果只顯示了三個產品類別。

1. 使用檢視身分選項停止檢視報表。

1. 儲存 Power BI Desktop 檔案。

1. 將 Power BI Desktop 檔案發佈至工作區，覆寫服務中的語意模型和報表。

1. 關閉 Power BI Desktop。

## 設定語意模型安全性

1. 在講師的 Power BI 服務中，從 [導覽] 窗格中，開啟 [銷售分析 **] 語意模型的**安全性頁面。

1. 在 [成員]**** 區段中，輸入收件者帳戶 (代表 Ty Johnston)。

1. 添加並保存。

## 在應用程式中測試資料列層級安全性

1. 在收件者的 Power BI 服務中，重新整理儀表板 (從先前示範開始就保持開啟狀態)。

1. 在 [利潤率 **] 儀表板磚中**，確認只能看到三個產品類別。
