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


# 如何确保停机时间为零？
{: #zero-downtime}

您的全球战略非常重要。您可以选择特定数据中心或位置，以在全球合适的地方为客户部署数据。
{:shortdesc}

{{site.data.keyword.Bluemix}} 平台服务是自我管理的服务。这意味着，应用程序的部署位置可以跨多个数据中心分布工作负载。您可以确保落实故障转移设计，即应用程序始终启动并运行供客户使用。对于基础架构资源，可以选择部署资源的各个数据中心。 

所有 {{site.data.keyword.Bluemix_notm}} 资源都在全球范围的各数据中心位置进行托管。并非所有服务都可使用高可用性和灾难恢复功能，因此可用的高可用性和灾难恢复类型取决于您使用的服务。  

## 灾难恢复
{: #disaster-recovery}

灾难恢复是指如何在一个位置发生灾难性故障或不可用时进行恢复。为确保落实灾难恢复，必须在多个位置部署多个 {{site.data.keyword.Bluemix_notm}} 环境，从而避免单点故障。这些环境可以是 Public、Dedicated 或 Local 平台的组合。  

### 灾难恢复计划 
{: #dr-plan}

{{site.data.keyword.Bluemix_notm}} 遵循灾难规划的需求，每个应用程序都有一个计划可供您在发生灾难事件后恢复或重新启动。恢复是通过恢复中心的电子备份或用于恢复计算的备用计算设施来实现的。灾难恢复计划包含在发生任何潜在灾难之前，针对硬件、软件、网络连接和非现场备份功能的系统和托管需求。

以下列表包含灾难恢复计划的需求：

- 对于负载均衡，有一个文档用于说明计算服务如何保持可用。 
- 如果执行多站点故障转移，那么灾难恢复计划必须说明由谁执行哪些操作来实现故障转移并确保重新启动。 
- 灾难恢复计划必须定义解决方案如何运作以及定义数据丢失。 
- 必须确认如何满足“最长可容忍停机时间”并将其存储在灾难恢复计划数据库中。  
- 灾难恢复计划指定对在灾难方式下运行（如果运行的内容不同于生产环境中运行的内容）的安全控制措施。 

### 管理灾难恢复计划 
{: #dr-plan-mgmt}

{{site.data.keyword.Bluemix}} 遵循的需求包括： 

- 在任何重大基础架构更改、应用程序主发行版和任何测试之后，必须更新灾难恢复计划。 
- 必须每年审批一次。 

## 资源部署的位置 
{: #ov_intro_reg}

您可以在不同位置创建应用程序和服务实例，而使用相同的 {{site.data.keyword.cloud_notm}} 基础架构来管理应用程序，以及使用相同的使用情况详细信息视图来进行计费。您可以将应用程序部署至离客户最近的位置，以实现最短应用程序等待时间。 

要解决安全问题，还可选择希望在其中保留应用程序数据的位置。如果在多个位置构建应用程序，那么当一个位置变为不可用时，其他位置的应用程序会继续运行。您的资源限额对于您使用的每个位置都是相同的。有关平台资源及其可用位置的更多信息，请参阅[服务可用性](/docs/resources?topic=resources-services_region)。

{{site.data.keyword.cloud_notm}} 控制台的全局负载均衡可确保如果您最接近的地理位置不可用，那么控制台将显示下一个最接近位置的信息。这样一来，您无需执行任何操作就可始终访问控制台，从而访问您所需的资源。

缺省情况下，可以从控制台中的资源列表视图中查看所有位置中的所有资源。如果要查看和使用特定位置中的资源，请展开**位置**菜单，然后从列表中选择一个位置。通过展开特定地理位置，可以选择按各个数据中心、区域或专区进行过滤。

![位置层次结构，其中显示的地理位置包含一个大城市，该大城市包含数据中心和带有专区的区域](images/Location_hierarchy.svg)

例如，如果您在伦敦 2 (eu-gb-2) 专区中部署有资源，那么可以过滤资源列表以仅显示这些资源。专区位于区域内，区域按其大城市位置进行组织。要过滤列表以仅显示伦敦 2 (eu-gb-2) 专区，请展开**伦敦**大城市选项，然后展开**伦敦 (eu-gb)** 区域选项。在该区域中，可以从可用专区列表中进行选择。如果在特定数据中心部署了资源，那么可以通过特定的大城市位置和字母数字代码来确定数据中心，例如伦敦 02 (lon02)。

您还可能拥有全球分布的资源。**全球**选项意味着仅将一个全球可访问的逻辑服务实例（独立于任何区域或专区）发布到客户应用程序。这些类型的资源可以从一个全球端点进行访问。

## 数据中心
{: #data_center}

部署基础架构资源时，您对数据的存储位置拥有更多选择。您可以选择一个位置，也可以从 {{site.data.keyword.Bluemix_notm}} 数据中心列表中进行选择。*数据中心*是一个物理位置，其中托管了用于服务和应用程序的电源、散热、计算、网络和存储资源。数据中心不会提供与一个位置中多个专区类似的本地故障的隔离。有关更多信息，请参阅 [Global locations for your global business ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/data-centers/){: new_window}。

{{site.data.keyword.Bluemix_notm}} 在全球许多位置提供数据中心。 


![可用数据中心的地图](images/Global-View.svg)


有关每个数据中心的特定代码，请参阅下表。 

|数据中心| 代码|
|------------------|-------|
|达拉斯 01|dal01|
|达拉斯 05|dal05|
|达拉斯 06|dal06|
|达拉斯 07|dal07|
|达拉斯 09|dal09|
|达拉斯 10|dal10|
|达拉斯 12|dal12|
|达拉斯 13|dal13|
|休斯顿 01|hou01|
|墨西哥 01|mex01|
|蒙特利尔 01|mon01|
|圣何塞 01|sjc01|
|圣何塞 03|sjc03|
|圣何塞 04|sjc04|
|圣保罗 01|sao01|
|西雅图 01|sea01|
|多伦多 01|tor01|
|华盛顿特区 01|wdc01|
|华盛顿特区 04|wdc04|
|华盛顿特区 06|wdc06|
|华盛顿特区 07|wdc07|
{: caption="表 1. 北美和南美的数据中心" caption-side="top"}
{: #americas}
{: tab-title="Americas"}
{: tab-group="dcs"}
{: class="simple-tab-table"}
{: summary="Use the buttons before the table to change the context of the table. The column headers identify the data centers located in the specific greographical area."}

|数据中心| 代码|
|------------------|-------|
|阿姆斯特丹 01|ams01|
|阿姆斯特丹 03|ams03|
|法兰克福 02|fra02|
|法兰克福 04|fra04|
|法兰克福 05|fra05|
|伦敦 02|lon02|
|伦敦 04|lon04|
|伦敦 05|lon05|
|伦敦 06|lon06|
|米兰 01|mil01|
|奥斯陆 01|osl01|
|巴黎 01|par01|
{: caption="表 1. 欧洲的数据中心" caption-side="top"}
{: #europe}
{: tab-title="Europe"}
{: tab-group="dcs"}
{: class="simple-tab-table"}
{: summary="Use the buttons before the table to change the context of the table. The column headers identify the data centers located in the specific greographical area."}

|数据中心| 代码|
|------------------|-------|
|香港 02|hkg02|
|墨尔本 01|mel01|
|首尔 01|seo01|
|新加坡 01|sng01|
|悉尼 01|syd01|
|悉尼 04|syd04|
|悉尼 05|syd05|
|东京 01|tok02| 
|东京 04|tok04|
|东京 05|tok05|
{: caption="表 1. 亚太地区的数据中心" caption-side="top"}
{: #asiapacific}
{: tab-title="Asia Pacific"}
{: tab-group="dcs"}
{: class="simple-tab-table"}
{: summary="Use the buttons before the table to change the context of the table. The column headers identify the data centers located in the specific greographical area."}

## 服务级别协议 (SLA)
{: #SLAs} 

{{site.data.keyword.Bluemix_notm}} 为单个专用或本地环境中的平台服务的多个实例提供 99.5% 的可用性服务级别。

要提交对停机时间的索赔，请联系 [{{site.data.keyword.Bluemix_notm}} 支持人员 ](https://cloud.ibm.com/unifiedsupport/supportcenter){: new_window}![外部链接图标](../icons/launch-glyph.svg "外部链接图标")。

{{site.data.keyword.Bluemix_notm}} 为 {{site.data.keyword.Bluemix_notm}} 服务提供了 SLA，因此您可能有资格获得发至您帐户的信用值。SLA 是解决 {{site.data.keyword.Bluemix_notm}} 无法满足指定服务级别的问题的唯一方法。{{site.data.keyword.Bluemix_notm}} 为单个专用或本地环境中的平台服务的多个实例提供 99.5% 的可用性服务级别。

有关专用环境的更多信息，请参阅 [IBM Cloud Dedicated](/docs/hybrid?topic=dedicated-dedicated)；有关本地环境的更多信息，请参阅 [Bluemix Local](/docs/hybrid?topic=local-local)。 

{{site.data.keyword.Bluemix_notm}} 的完整服务描述在 [Cloud Services terms](http://www-03.ibm.com/software/sla/sladb.nsf/sla/bm){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标") 上提供。

### 可用性停机时间 SLA 
{: #avail-downtime}

如果停机时间低于 99.5% 的可用性，那么您有资格获得发至您帐户的信用值。可用性停机时间是指无法连接到任何服务实例的总分钟数。总停机时间（分钟）从提交中断事件报告起算，到至少一个受影响的实例可供使用时为止。

{{site.data.keyword.Bluemix_notm}} 针对以下项提供 99.95% 的可用性 SLA： 
- 公共环境中配置为高可用性的云服务，高可用性与目录详细信息中所述的每个服务的高可用性一致。 
- 位于地理上分隔的数据中心内的多个专用或本地环境中的云服务。 

|类型|描述|支持详细信息|
|-------------------------------------------------------------------------------|--------------------|----------------|
|高可用性公共环境或多个专用/本地环境|其他环境|信用值|
| <99.95%                                                                       |<99.5%              |10%             |
| <99.90%                                                                       |<99.0%              |25%             |
{: caption="表 2. 每月可用性服务级别" caption-side="top"}

可用性百分比的计算方法为：合约月份内的总分钟数减去该月内停机时间的总分钟数，再除以该月内的总分钟数。 

例如，在包含 31 天的月份中，总分钟数为 44,640。如果遇到 6 小时的可用性停机时间，那么停机分钟数为 360 分钟。如果停机时间只有 6 小时，那么可用性为 99.19%。由于 99.19% 低于 99.90%，因此您有资格在公共或本地环境中获得 25% 的信用值。   

```
= (该月总分钟数 44,640 - 停机分钟数 360) / 该月总分钟数 44,640
= (实际可用分钟数 44,280) / 该月总分钟数 44,640
= 99.19% 可用性
```

SLA 不包含与指定的排除项相关的停机时间或故障时间、{{site.data.keyword.Bluemix_notm}} UI 不可用的时间，也不包含重新装入、配置、启用或访问内容的时间。

可用性停机时间 SLA 不包括 {{site.data.keyword.Bluemix_notm}} 基础架构服务。
{: note}

### 基础架构服务 SLA
{: #iaas-slas}

基础架构服务包括裸机和虚拟服务器服务、联网服务、存储服务和安全服务。要查找基础架构服务的完整列表，请使用 `iaas` 标记搜索 {{site.data.keyword.Bluemix_notm}}“目录”。 

停机时间是指由于公用网络、专用网络以及冗余基础架构电源和 HVAC 中断造成的服务中断，而导致客户确定的基础架构服务不可用的总分钟数。总停机时间（分钟）从确定影响服务的已验证中断时起算，到服务可用时为止。 

停机时间不包括执行安排的维护或通知的维护的时间。对于每个连续的 30 分钟停机时间，您将获取金额为中断直接影响的所确定服务每月费用 5% 的信用值。如果停机时间短于连续的 30 分钟，那么您没有资格获得信用值。可能不会组合不同中断类型的停机时间以满足此计算方式。 

### 基础架构硬件更换和升级 SLA
{: #hw-replaceupgrade-sla}

{{site.data.keyword.Bluemix_notm}} 在更换发生故障的硬件时或执行安排的硬件升级时，会尽量缩短停机时间。 

{{site.data.keyword.Bluemix_notm}} 针对以下情况提供信用值： 
- 根据从 {{site.data.keyword.Bluemix_notm}} 验证了客户报告的硬件故障时起算的更换时间，为硬件更换提供信用值。
- 根据接收升级的服务的总停机时间，为计划的硬件升级提供信用值。 

服务级别时间段不包括重装操作系统或应用程序所需的任何时间，也不包括服务性能可能下降的时间。如果 {{site.data.keyword.Bluemix_notm}} 无法满足指定的服务级别时间段，您将有资格根据硬件更换或升级所影响服务的每月费用获取信用值。

|服务级别时间段| 信用值百分比|
|---------------------------|----------------|
|2 小时之内|无|
|> 2 小时| 20%            |
|> 6 小时| 40%            |
|> 10 小时| 60%            |
|> 14 小时| 80%            |
|> 18 小时| 80%            |
{: caption="表 3. 基于硬件更换或升级所影响服务的每月费用的信用值" caption-side="top"}

### 索赔
{: #claims}

您应在未满足服务级别的合约月份结束后 60 天内提交索赔。请提供用于确定受影响服务的足够信息、错误消息和验证索赔所需的其他信息。 

信用值是根据合约月份内受影响服务的累积可用性确定的最高适用赔偿，使用此受影响服务的每月费用进行计算。信用值不得超过每月费用的 25%。

要提交对停机时间的索赔，请联系 [{{site.data.keyword.Bluemix_notm}} 支持人员 ](https://cloud.ibm.com/unifiedsupport/supportcenter){: new_window}![外部链接图标](../icons/launch-glyph.svg "外部链接图标")。

### 排除项
{: #exclusions}

出于以下原因，不会因无法满足 SLA 而提供信用值：
- 与客户或社区提供的内容、技术、设计或指示信息相关的问题
- Beta、试验性或免费云服务
- 非 IBM 构建包
- 不支持的系统配置和平台
- 客户基础架构故障，包括网络、硬件、设施或电源
- 客户系统管理操作、命令或文件传输
- 要提供所需信息或访问权才能解决中断的客户错误或故障
- 客户造成的安全事件或安全测试
- 其他超出 IBM 合理控制范围之外的原因
