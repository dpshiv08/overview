---

copyright:
  years: 2018, 2019
lastupdated: "2019-06-20"

keywords: HA, failover, DR, high availability, disaster recovery, locations, data centers

subcollection: overview

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:note: .deprecated}


# 如何確保運作零中斷？
{: #zero-downtime}

您的全球策略很重要。您可以選取特定的資料中心或位置，在全球的正確位置上為您的客戶部署資料。
{:shortdesc}

{{site.data.keyword.Bluemix}} 平台服務會自主管理。這表示您部署應用程式的位置，可以將工作負載擴散到各資料中心。而且，您可以確保失效接手設計已就緒，這表示您的應用程式隨時都能為客戶執行工作。對於基礎架構資源，您可以選取要在其中部署資源的個別資料中心。 

所有 {{site.data.keyword.Bluemix_notm}} 資源都是在全球的資料中心位置進行管理。高可用性和災難回復並未普遍存在於所有服務中，因此，可用的高可用性和災難回復類型將取決於您所使用的服務。  

## 災難回復
{: #disaster-recovery}

災難回復是關於如何在單一位置發生災難性失效或失去可用性時維持運作。為了確保災難回復已就緒，必須在多個位置部署數個 {{site.data.keyword.Bluemix_notm}} 環境，以避免單一失敗點。這些環境可以是「公用」、「專用」或「本端」平台的組合。  

### 災難回復計劃 
{: #dr-plan}

{{site.data.keyword.Bluemix_notm}} 遵循需求來針對災難進行規劃，每個應用程式都有一個計劃，供您在發生災難事件之後回復或重新啟動。回復是從回復中心或還原運算之替代運算設備的電子備份中進行。在發生任何潛在的災難之前，災難回復計劃包含了對於硬體、軟體、網路連線功能及離站備份功能的系統及管理需求。

下列清單包含災難回復計劃的需求：

- 對於負載平衡，有一份文件說明運算服務如何保持可用。 
- 當發生多站台失效接手時，災難回復計劃必須說明誰做什麼以讓失效接手發生，並確保重新啟動。 
- 災難回復計劃必須定義解決方案的運作方式，以及資料損失為何。 
- 它必須確認如何符合「最大可容忍運作中斷時間」，並且必須儲存在「災難回復計劃」資料庫中。  
- 災難回復計劃會指定在災難模式下執行時的安全控制措施（如果它們與在正式作業中執行時的安全控制措施不同）。 

### 災難回復計劃的管理 
{: #dr-plan-mgmt}

以下是 {{site.data.keyword.Bluemix}} 遵循的需求： 

- 在任何重大基礎架構變更、重大應用程式版本及任何測試之後，都必須更新災難回復計劃。 
- 它必須每年通過核准。 

## 資源部署的位置 
{: #ov_intro_reg}

您可以在不同的位置建立應用程式和服務實例，而使用相同的 {{site.data.keyword.cloud_notm}} 基礎架構進行應用程式管理，以及使用相同的用量詳細資料視圖處理計費。您可以將應用程式部署至最接近客戶的位置，以縮短應用程式的延遲時間。 

為了解決安全問題，您也可以選取想要保留應用程式資料的位置。在多個位置建置應用程式時，如果其中一個位置變成無法使用，則位於其他位置的應用程式會繼續執行。您所用每個位置的資源額度都相同。如需平台資源及其可用位置的相關資訊，請參閱[服務可用性](/docs/resources?topic=resources-services_region)。

{{site.data.keyword.cloud_notm}} 主控台的廣域負載平衡可確保如果離您最近的地理位置無法使用，主控台會顯示下一個最近位置的資訊。如此一來，您隨時都可以存取主控台，而不需要採取任何動作來存取所需的資源。

依預設，您可以從主控台的資源清單視圖中檢視所有位置的所有資源。如果您要檢視及使用特定位置的資源，請展開**位置**功能表，並從清單選取某個位置。展開特定地理位置，即可選擇依個別資料中心、地區或區域進行過濾。

![位置階層，其中顯示的地理位置包含一個都會區，都會區中包含資料中心和具有區域的地區](images/Location_hierarchy.svg){: caption="圖 1. 位置選項階層" caption-side="bottom"}

比方說，如果您有部署在倫敦 2 (eu-gb-2) 區域的資源，則可以過濾資源清單，只顯示這些資源。區域位於某個地區內，而地區是依其都會位置進行組織。若要將清單過濾到倫敦 2 (eu-gb-2) 區域，請展開**倫敦**都會選項，然後展開**倫敦 (eu-gb)** 地區選項。在該地區內，您可以從可用的區域清單中進行選擇。如果您已在特定資料中心內部署了資源，則可以透過特定的都會位置及英數代碼識別資料中心，例如倫敦 02 (lon02)。

您還可以擁有位於全球的資源。**廣域**選項表示只有一個邏輯上可廣域存取的服務實例（與任何地區或區域無關）發佈到自訂應用程式。可以從廣域端點存取這些類型的資源。

## 資料中心
{: #data_center}

當您部署基礎架構資源時，有更多關於資料所在位置的選項。您可以選取一個位置，或者可以從 {{site.data.keyword.Bluemix_notm}} 的資料中心清單進行選取。*資料中心* 是管理服務及應用程式所使用之電源、散熱、運算、網路及儲存空間資源的實體位置。資料中心並不像一個位置中的多個區域那樣，提供對本端失敗的隔離。如需相關資訊，請參閱 [Global locations for your global business ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")](https://www.ibm.com/cloud/data-centers/){: new_window}。

{{site.data.keyword.Bluemix_notm}} 在全球許多位置提供資料中心。 


![可用資料中心的地圖](images/Global-View.svg){: caption="圖 2. 資料中心位置" caption-side="bottom"}


如需每個資料中心的特定代碼，請參閱下表。 

|資料中心| 代碼 |
|------------------|-------|
|達拉斯 01|dal01|
|達拉斯 05|dal05|
|達拉斯 06|dal06|
|達拉斯 07|dal07|
|達拉斯 09|dal09|
|達拉斯 10|dal10|
|達拉斯 12|dal12|
|達拉斯 13|dal13|
|休斯頓 01|hou01|
|墨西哥 01|mex01|
|蒙特婁 01|mon01|
|聖荷西 01|sjc01|
|聖荷西 03|sjc03|
|聖荷西 04|sjc04|
|聖保羅 01|sao01|
|西雅圖 01|sea01|
|多倫多 01|tor01|
|華盛頓特區 01|wdc01|
|華盛頓特區 04|wdc04|
|華盛頓特區 06|wdc06|
|華盛頓特區 07|wdc07|
{: caption="表 1. 北美洲及南美洲的資料中心" caption-side="top"}
{: #americas}
{: tab-title="Americas"}
{: tab-group="dcs"}
{: class="simple-tab-table"}
{: summary="Use the buttons before the table to change the context of the table. The column headers identify the data centers located in the specific greographical area."}

|資料中心| 代碼 |
|------------------|-------|
|阿姆斯特丹 01|ams01|
|阿姆斯特丹 03|ams03|
|法蘭克福 02|fra02|
|法蘭克福 04|fra04|
|法蘭克福 05|fra05|
|倫敦 02|lon02|
|倫敦 04|lon04|
|倫敦 05|lon05|
|倫敦 06|lon06|
|米蘭 01|mil01|
|奧斯陸 01|osl01|
|巴黎 01|par01|
{: caption="表 1. 歐洲的資料中心" caption-side="top"}
{: #europe}
{: tab-title="Europe"}
{: tab-group="dcs"}
{: class="simple-tab-table"}
{: summary="Use the buttons before the table to change the context of the table. The column headers identify the data centers located in the specific greographical area."}

|資料中心| 代碼 |
|------------------|-------|
|香港 02|hkg02|
|墨爾本 01|mel01|
|首爾 01|seo01|
|新加坡 01|sng01|
|雪梨 01|syd01|
|雪梨 04|syd04|
|雪梨 05|syd05|
|東京 01|tok02| 
|東京 04|tok04|
|東京 05|tok05|
{: caption="表 1. 亞太地區的資料中心" caption-side="top"}
{: #asiapacific}
{: tab-title="Asia Pacific"}
{: tab-group="dcs"}
{: class="simple-tab-table"}
{: summary="Use the buttons before the table to change the context of the table. The column headers identify the data centers located in the specific greographical area."}

## 服務水準合約 (SLA)
{: #SLAs} 

{{site.data.keyword.Bluemix_notm}} 針對單一專用或本端環境內平台服務的多個實例，提供 99.5% 的可用性服務水準。

若要提交運作中斷時間索賠，請與 [{{site.data.keyword.Bluemix_notm}} 支援中心 ](https://cloud.ibm.com/unifiedsupport/supportcenter){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示") 聯絡。

{{site.data.keyword.Bluemix_notm}} 提供 {{site.data.keyword.Bluemix_notm}} 服務的 SLA，可能讓您符合在帳戶獲得額度的資格。SLA 是您解決 {{site.data.keyword.Bluemix_notm}} 未能達到指定服務水準的唯一方式。{{site.data.keyword.Bluemix_notm}} 針對單一專用或本端環境內平台服務的多個實例，提供 99.5% 的可用性服務水準。

如需專用環境的相關資訊，請參閱 [IBM Cloud Dedicated](/docs/hybrid?topic=dedicated-dedicated)，至於本端環境，請參閱 [Bluemix Local](/docs/hybrid?topic=local-local)。 

如需 {{site.data.keyword.Bluemix_notm}} 的完整服務說明，請參閱 [Cloud Services terms](http://www-03.ibm.com/software/sla/sladb.nsf/sla/bm){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")。

### 可用性運作中斷時間 SLA 
{: #avail-downtime}

如果您遇到不足 99.5% 的可用性運作中斷時間，您就符合在帳戶獲得額度的資格。可用性運作中斷時間是指您無法連接至任何服務實例的總分鐘數。運作中斷時間總分鐘數的計算從您提交中斷事件的報告開始，並在至少有一個受影響實例可供使用時截止。

{{site.data.keyword.Bluemix_notm}} 針對以下各項提供 99.95% 的可用性 SLA： 
- 公用環境中已進行高可用性配置的雲端服務，如各服務的型錄詳細資料中所述。 
- 在不同地理位置的資料中心裡，數個專用或本端環境之間的雲端服務。 

|類型	|說明	|支援詳細資料|
|-------------------------------------------------------------------------------|--------------------|----------------|
|高可用性公用環境或多個專用/本端環境 |其他環境 |額度|
| <99.95%                                                                       |<99.5%              |10%             |
| <99.90%                                                                       |<99.0%              |25%             |
{: caption="表 2. 按月可用性服務等級" caption-side="top"}

可用性百分比的計算方式，是將合約月份中的總分鐘數，減去該月份運作中斷時間總分鐘數，然後除以該月份總分鐘數。 

例如，如果這個月有 31 天，您的總分鐘數為 44,640。如果您遇到六小時的可用性運作中斷時間，則運作中斷時間分鐘數為 360。在運作中斷時間只有六小時的情況下，您的可用性為 99.19%。由於 99.19% 小於 99.90%，因此您有資格獲得公用環境或本端環境 25% 的額度。   

```
= (44,640 total minutes in month - 360 downtime minutes) / 44,640 total minutes in month
= (44,280 actual minutes available) / 44,640 total minutes in month
= 99.19% availability
```

SLA 不包括與指定排除項目、{{site.data.keyword.Bluemix_notm}} 使用者介面無法使用、重新載入、配置、啟用或存取內容之時間相關的運作中斷時間或失敗。

可用性運作中斷時間 SLA 不包括 {{site.data.keyword.Bluemix_notm}} 基礎架構服務。
{: note}

### 基礎架構服務 SLA
{: #iaas-slas}

基礎架構服務是指裸機伺服器和虛擬伺服器、網路、儲存空間及安全服務。若要尋找基礎架構服務的完整清單，請使用 `iaas` 標籤來搜尋 {{site.data.keyword.Bluemix_notm}} 型錄。 

「運作中斷時間」是指因為「公用網路」、「專用網路」及「備援基礎架構」電力和 HVAC（暖通空調）中斷而造成服務中斷，導致客戶認為基礎架構服務無法使用的總分鐘數。運作中斷時間總分鐘數的計算是從識別影響服務的已驗證中斷之時開始，一直到服務可用時截止。 

運作中斷時間不包括已排定或已公告維護的時間。針對每連續 30 分鐘的運作中斷時間，您會獲得受中斷直接影響之已識別服務每月費用 5% 的額度。如果運作中斷時間少於連續 30 分鐘，則不符合獲得額度的資格。不同中斷類型的運作中斷時間無法合併進行此計算。 

### 基礎架構硬體更換及升級 SLA
{: #hw-replaceupgrade-sla}

{{site.data.keyword.Bluemix_notm}} 會在更換故障的硬體或執行排定的硬體升級時，嘗試將運作中斷時間縮到最短。 

{{site.data.keyword.Bluemix_notm}} 針對以下狀況提供額度： 
- 硬體更換，根據從 {{site.data.keyword.Bluemix_notm}} 確認客戶已報告硬體故障的時間算起的更換時間。
- 計劃性的硬體升級，根據獲得升級之服務的總運作中斷時間。 

服務水準時段會排除重新載入作業系統或應用程式所需的任何時間，或效能可能欠佳的時間。如果 {{site.data.keyword.Bluemix_notm}} 無法符合指定的服務水準時段，則您符合根據受硬體更換或升級影響之服務每月費用計算的額度資格。

|服務水準時段 |額度百分比|
|---------------------------|----------------|
|≤ 2 小時 |無|
|> 2 小時 | 20%            |
|> 6 小時 | 40%            |
|> 10 小時 | 60%            |
|> 14 小時 | 80%            |
|> 18 小時 | 80%            |
{: caption="表 3. 根據受硬體更換或升級影響之服務每月收費的額度" caption-side="top"}

### 索賠
{: #claims}

請在未達到服務水準的合約月份結束 60 天內提出索賠。請提供足夠的資訊以識別受影響的服務、錯誤訊息，以及驗證索賠所需的其他資訊。 

此額度是根據受影響服務在合約月份期間內之累計可用性，並使用該等受影響服務之每月費用所計算出的最高適用補償。額度不得超過每月費用的 25%。

若要提交運作中斷時間索賠，請與 [{{site.data.keyword.Bluemix_notm}} 支援中心 ](https://cloud.ibm.com/unifiedsupport/supportcenter){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示") 聯絡。

### 排除適用
{: #exclusions}

因為下列原因而未達到 SLA，將不提供額度：
- 客戶或社群提供的內容、技術、設計或指示有問題
- 測試版、實驗性或免費雲端服務
- 非 IBM 建置套件
- 不受支援的系統配置和平台
- 客戶基礎架構故障，包括網路、硬體、設備或電力
- 客戶系統管理動作、指令或檔案傳送
- 客戶錯誤，或未能提供所需的資訊或存取權來解決中斷問題
- 客戶造成的資安事件或安全測試
- 超出 IBM 合理控制範圍的其他原因
