---
lab:
  title: 設定您自己的環境
  module: Set up your own environment
---

# 設定本機實驗室環境

在理想情況下，您應該在託管的實驗室環境中完成這些實驗室。 如果您想要在自己的電腦上完成這些練習，您可以藉由安裝下列軟體達成。

- 所有設定及資源檔案都可以從 [GitHub 下載](https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/AllfilesDownload.zip)。
  - 將 'AllFilesDownload' 資料夾解壓縮至 D：/ 並將它重新命名為 'D：\Allfiles\'。

您可能會在使用自有環境時遇到預期之外的對話和行為。由於本機設定有各種可能情況，課程團隊無法針對您在自有環境中所遭遇的問題提供支援。******

## 使用 Windows 11 的相關指示

> 下列指示適用於 Windows 11 計算機。 如果從不同的 OS 進行連線，可能不會獲得相同的體驗。

### Power BI Desktop

1. 從 Microsoft Store 下載並安裝。 若您無權存取 Microsoft Store，請從[此網頁](https://www.microsoft.com/download/details.aspx?id=58494)下載。 Power BI Desktop 是這些實驗室適用的主要應用程式。

    - 使用安裝程式中的預設選項。

### Microsoft 365 開發人員帳戶

在進行部分練習時，您必須以組織帳戶登入 Power BI。 您可以使用自己的帳戶，但如果您沒有存取權，您可以建立免費的 [Microsoft 365 開發人員帳戶](https://developer.microsoft.com/microsoft-365/dev-program)。

### SQL Server Database Engine

1. 實驗室會連線到 localhost SQL Server 執行個體。 下列指示可協助您安裝 SQL Server 及設定預設選項。 您只需安裝資料庫引擎功能。

    - 下載免費的[安裝媒體開發人員版](https://www.microsoft.com/sql-server/sql-server-downloads?SilentAuth=1&f=255&MSPPError=-2147217396&rtc=1)
    - [從安裝精靈安裝 SQL Server 2016 (安裝程式)](https://learn.microsoft.com/sql/database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup)

> 如果您有存取權，則可以使用現有的 SQL Server 實例，而不是安裝本機版本。 不過，您必須將連接字串從 "localhost" 修改為您的執行個體名稱。

### Microsoft Edge

1. 安裝最新版的 [Microsoft Edge](https://microsoft.com/edge)，以在線上存取 Power BI 服務。
