---

copyright:
  years: 2017
lastupdated: "2017-03-16"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:pre: .pre}


# HSBN vNext 測試版網路概觀
{: #v10_netoverview}


「HSBN vNext 測試版」服務運用 Hyperledger Fabric 1.0 版來提供安全且具有許可權的區塊鏈網路，而鑑別成員可以在其上輕鬆地定義資產，並且建立商業解決方案來修改及交換資產。
{:shortdesc}

此服務可**大幅簡化**引導企業級區塊鏈網路的難解且繁瑣的程序。我們提供架構及工具來邀請成員、聚集各種加密身分資料、建立控管規則等作業。這些複雜程序會變得直覺而且更不費力。只要幾分鐘您就可以使用商業邏輯的通道、原則及不同特性來大量產生完整運作的高安全網路。  

網路必要元件（對等節點、排序服務、憑證管理中心、鏈碼）的**高可用性**可排除因單一失敗點而引發的嚴重後果。內建儀表板監視器可讓您輕鬆地管理這些元件，並提供功能強大的機制來視覺化資產及智慧型合約。

Hyperledger Fabric 1.0 版架構的**模組性**及特殊網路角色分隔提供啟用可擴充性及高效能運算的基礎架構。  

整個交易生命週期發生的檢查及平衡可確保一致且完整審查過的結果；而且分類帳會透過實作已知的聊天通訊協定來持續保持同步。身分及存取控制是透過網路上不斷發生的**簽署/驗證**作業輕鬆地施行。  

**控管工具**的提供可讓成員管理其網路的重要商業規則。例如，您可能想要實作原則，而此原則定義必須要有多少位網路成員同意，新成員才能加入。或者，可能有需要每個參與者都背書才能進行修改的資產。控管規則是任何類型的商業網路的基本必要項目，而且常常會詳盡闡述。控管工具（例如，原則編輯器）可大幅簡化此程序。

此服務會在不含網路元件的外部存取權（包括 root 存取權）的**高安全及隔離**環境中執行。會加密進行中及靜止的資料，而且硬體安全模組支援容許根據企業規定來保護數位金鑰。**專用運算**是針對網路互動而提供，進而確保高效能及資料保護。雜湊、簽署/驗證作業及元件間通訊是透過進階加密法實作來加速。

**圖 1** 說明已部署區塊鏈網路的範例，而此網路包含四個成員（各自擁有兩個對等節點）、一個負責配送加密身分資料的「憑證管理中心」，以及一個定義原則及網路參與者的「排序服務」。藍色通道包含這四個網路成員，而黃色通道限制為成員 2、3 及 4：

![區塊鏈網路](images/blockchain_network.png "區塊鏈網路範例")

*圖 2. 包含運用通道來隔離資料的四個成員的區塊鏈網路範例*

如需所有 Hyperledger Fabric 1.0 版特性及功能的完整詳細資料，請參閱位於下列網址的完整版本文件：http://hyperledger-fabric.readthedocs.io/en/latest/