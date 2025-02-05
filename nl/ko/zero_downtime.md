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


# 작동 중단이 발생하지 않도록 하는 방법
{: #zero-downtime}

사용자의 글로벌 전략은 중요합니다. 고객을 위해 전세계의 올바른 지역에 데이터를 배치하도록 특정 데이터 센터 또는 위치를 선택할 수 있습니다. 
{:shortdesc}

{{site.data.keyword.Bluemix}} 플랫폼 서비스는 자체적으로 관리됩니다. 즉, 앱을 배치하는 위치에서 데이터 센터 간에 워크로드를 분산할 수 있습니다. 또한 고객을 위해 앱이 항상 시작되어 실행 중임을 의미하는 장애 복구 디자인을 갖추고 있는지 확인할 수 있습니다. 인프라 리소스의 경우 리소스가 배치되는 개별 데이터 센터를 선택할 수 있습니다. 

모든 {{site.data.keyword.Bluemix_notm}} 리소스는 전세계의 데이터 센터 위치에서 호스팅됩니다. 고가용성 및 재해 복구는 모든 서비스에서 보편적이지 않으므로 사용 가능한 고가용성 및 재해 복구의 유형은 사용 중인 서비스에 따라 다릅니다.  

## 재해 복구
{: #disaster-recovery}

재해 복구는 단일 위치에서 치명적인 장애 또는 가용성 손실을 극복하는 것입니다. 재해 복구가 제대로 수행되도록 하려면 단일 장애 지점을 방지하기 위해 여러 {{site.data.keyword.Bluemix_notm}} 환경을 다중 위치에 배치해야 합니다. 이러한 환경은 퍼블릭, 데디케이티드 또는 로컬 플랫폼의 조합일 수 있습니다.  

### 재해 복구 플랜 
{: #dr-plan}

{{site.data.keyword.Bluemix_notm}}는 재해 복구를 계획하기 위한 요구사항을 따르며 모든 애플리케이션에는 재배 복구 이벤트 후 복구하거나 다시 시작하는 플랜이 있습니다. 복구는 복구 센터에서 전자 백업으로부터 수행되거나 컴퓨팅을 복원하는 대체 컴퓨팅 기능에서 수행됩니다. 잠재적인 재해가 발생하기 전에 재해 복구 플랜에 하드웨어, 소프트웨어, 네트워킹 연결 및 오프사이트 백업 기능에 대한 시스템 및 호스팅 요구사항이 포함됩니다.

다음 목록에는 재해 복구 플랜의 요구사항이 포함되어 있습니다.

- 로드 밸런싱을 위해 컴퓨팅 서비스가 사용 가능한 상태로 유지되는 방법을 설명하는 문서가 있습니다. 
- 다중 사이트 장애 복구가 발생하는 경우 재해 복구 플랜에 장애 복구를 위해 누가 어떤 작업을 수행하는지가 설명되고 다시 시작되도록 해야 합니다. 
- 재해 복구 플랜에 솔루션 작동 방법과 데이터 손실의 개념이 정의되어야 합니다. 
- 이는 최대 허용 중단 시간이 충족되는 방식을 확인하고 재해 복구 플랜 데이터베이스에 저장되어야 합니다.  
- 재해 복구 플랜에 재해 모드에서 실행하기 위한 보안 제어가 지정되어 있습니다(프로덕션에서 실행 중인 보안 제어와 다른 경우). 

### 재해 복구 플랜 관리 
{: #dr-plan-mgmt}

{{site.data.keyword.Bluemix}}에서 따르는 요구사항은 다음과 같습니다. 

- 주요 인프라 변경, 주요 애플리케이션 릴리스 및 테스트 이후 재해 복구 플랜이 업데이트되어야 합니다. 
- 수동으로 승인되어야 합니다. 

## 리소스 배치를 위한 위치 
{: #ov_intro_reg}

애플리케이션 관리를 위한 동일한 {{site.data.keyword.cloud_notm}} 인프라 및 요금 청구를 위한 동일한 사용량 세부사항을 사용하여 다른 위치에 앱 및 서비스 인스턴스를 작성할 수 있습니다. 애플리케이션 대기 시간을 낮추기 위해 고객과 가장 가까운 위치에 앱을 배치할 수 있습니다. 

보안 문제를 해결하기 위해 애플리케이션 데이터를 보관할 위치를 선택할 수도 있습니다. 앱을 둘 이상의 위치에서 빌드할 경우 이 중 한 위치가 사용 불가능하면 다른 위치에 있는 앱은 계속 실행됩니다. 허용되는 리소스 양은 사용하는 위치마다 동일합니다. 플랫폼 리소스 및 사용 가능한 위치에 대한 자세한 정보는 [서비스 가용성](/docs/resources?topic=resources-services_region)을 참조하십시오.

{{site.data.keyword.cloud_notm}} 콘솔의 글로벌 로드 밸런싱은 사용자에게 가장 가까운 지리적 위치가 사용 불가능하게 되면 다음으로 가장 가까운 위치에 대한 정보가 콘솔에 표시됩니다. 이 방식을 사용하면 사용자가 필요한 리소스에 액세스하기 위한 조치를 수행하지 않고 항상 콘솔에 액세스할 수 있습니다.

기본적으로 콘솔의 리소스 목록 보기에서 모든 위치의 모든 리소스를 볼 수 있습니다. 특정 위치의 리소스를 보고 이에 대해 작업하려면 **위치** 메뉴를 펼친 다음 목록에서 위치를 선택하십시오. 특정 지역을 펼쳐 개별 데이터 센터, 지역 또는 구역을 기준으로 필터링하도록 선택할 수 있습니다.

![지역이 있는 데이터 센터 및 구역을 포함하는 지하철 관련 지리적 위치를 표시하는 위치 계층 구조](images/Location_hierarchy.svg){: caption="Figure 1. Location options hierarchy" caption-side="bottom"}

예를 들어, 런던 2(eu-gb-2) 구역에 배치된 리소스가 있는 경우에는 이러한 리소스만 표시하도록 리소스 목록을 필터링할 수 있습니다. 특정 구역은 특정 지역에 있으며 특정 지역은 해당 메트로 위치로 구성됩니다. 런던 2(eu-gb-2) 구역만 나열하도록 목록을 필터링하려면 **런던** 메트로 옵션을 펼친 후 **런던(eu-gb)** 지역 옵션을 펼치십시오. 해당 지역에서 사용 가능한 구역의 목록 중 원하는 항목을 선택할 수 있습니다. 특정 데이터 센터에 배치된 리소스가 있는 경우에는 특정 메트로 위치 및 영숫자 코드(예: 런던 02(lon02))로 해당 데이터 센터를 식별할 수 있습니다.

전 세계에 위치한 리소스를 보유할 수도 있습니다. **글로벌** 옵션은 지역 또는 구역과 무관한, 전 세계에서 액세스할 수 있는 하나의 논리 서비스 인스턴스만 고객 애플리케이션에 공개됨을 의미합니다. 이러한 리소스 유형은 글로벌 엔드포인트에서 액세스할 수 있습니다.

## 데이터 센터
{: #data_center}

인프라 리소스를 배치하는 경우 데이터가 있는 위치에 대한 더 많은 옵션이 있습니다. 위치를 선택하거나 {{site.data.keyword.Bluemix_notm}} 데이터 센터의 목록에서 선택할 수 있습니다. *데이터 센터*는 서비스 및 앱에 사용되는 전원, 냉각, 컴퓨팅, 네트워크 및 스토리지 리소스를 호스팅하는 실제 위치입니다. 데이터 센터는 한 위치에서 다중 구역과 유사한 로컬 장애로부터의 격리를 제공하지 않습니다. 자세한 정보는 [Global locations for your global business ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/data-centers/){: new_window}를 참조하십시오.

{{site.data.keyword.Bluemix_notm}}에서는 전 세계 많은 위치에서 데이터 센터를 제공합니다. 


![사용 가능한 데이터 센터 지도](images/Global-View.svg){: caption="Figure 2. Data center locations" caption-side="bottom"}


데이터 센터별 특정 코드는 다음 표를 참조하십시오. 

| 데이터 센터 | 코드  |
|------------------|-------|
|댈러스 01        |dal01 |
|댈러스 05        |dal05 |
|댈러스 06        |dal06 |
|댈러스 07        |dal07 |
|댈러스 09        |dal09 |
|댈러스 10        |dal10 |
|댈러스 12        |dal12 |
|댈러스 13        |dal13 |
|휴스턴 01       |hou01 |
|멕시코 01        |mex01 |
|몬트리올 01      |mon01 |
|산호세 01      |sjc01 |
|산호세 03      |sjc03 |
|산호세 04      |sjc04 |
|상파울루 01     |sao01 |
|시애틀 01       |sea01 |
|토론토 01       |tor01 |
|워싱턴 DC 01 |wdc01 |
|워싱턴 DC 04 |wdc04 |
|워싱턴 DC 06 |wdc06 |
|워싱턴 DC 07 |wdc07 |
{: caption="표 1. 북미 및 남미의 데이터 센터" caption-side="top"}
{: #americas}
{: tab-title="Americas"}
{: tab-group="dcs"}
{: class="simple-tab-table"}
{: summary="Use the buttons before the table to change the context of the table. The column headers identify the data centers located in the specific greographical area."}

| 데이터 센터 | 코드  |
|------------------|-------|
|암스테르담 01     |ams01 |
|암스테르담 03     |ams03 |
|프랑크푸르트 02     |fra02 |
|프랑크푸르트 04     |fra04 |
|프랑크푸르트 05     |fra05 |
|런던 02        |lon02 |
|런던 04        |lon04 |
|런던 05        |lon05 |
|런던 06        |lon06 |
|밀라노 01         |mil01 |
|오슬로 01          |osl01 |
|파리 01         |par01 |
{: caption="표 1. 유럽의 데이터 센터" caption-side="top"}
{: #europe}
{: tab-title="Europe"}
{: tab-group="dcs"}
{: class="simple-tab-table"}
{: summary="Use the buttons before the table to change the context of the table. The column headers identify the data centers located in the specific greographical area."}

| 데이터 센터 | 코드  |
|------------------|-------|
|홍콩 02     |hkg02 |
|멜버른 01     |mel01 |
|서울 01         |seo01 |
|싱가포르 01     |sng01 |
|시드니 01        |syd01 |
|시드니 04        |syd04 |
|시드니 05        |syd05 |
|도쿄 01         |tok02 | 
|도쿄 04         |tok04 |
|도쿄 05         |tok05 |
{: caption="표 1. 아시아 태평양의 데이터 센터" caption-side="top"}
{: #asiapacific}
{: tab-title="Asia Pacific"}
{: tab-group="dcs"}
{: class="simple-tab-table"}
{: summary="Use the buttons before the table to change the context of the table. The column headers identify the data centers located in the specific greographical area."}

## SLA(Service Level Agreement)
{: #SLAs} 

{{site.data.keyword.Bluemix_notm}}는 단일 데디케이티드 또는 로컬 환경 내에서 플랫폼 서비스의 여러 인스턴스에 대해 99.5% 가용성 서비스 레벨을 제공합니다.

작동 중단 시간에 대한 청구를 제출하려면 [{{site.data.keyword.Bluemix_notm}} 지원 센터 ](https://cloud.ibm.com/unifiedsupport/supportcenter){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")에 문의하십시오.

{{site.data.keyword.Bluemix_notm}}는 계정에 대한 크레딧을 받을 수 있도록 하는 {{site.data.keyword.Bluemix_notm}} 서비스에 대한 SLA를 제공합니다. SLA는 지정된 서비스 레벨을 충족하지 못한 {{site.data.keyword.Bluemix_notm}}의 오류를 해결하는 유일한 방법입니다. {{site.data.keyword.Bluemix_notm}}는 단일 데디케이티드 또는 로컬 환경 내에서 플랫폼 서비스의 여러 인스턴스에 대해 99.5% 가용성 서비스 레벨을 제공합니다.

데디케이티드 환경에 대한 자세한 정보는 [IBM Cloud Dedicated](/docs/hybrid?topic=dedicated-dedicated)를 참조하고 로컬 환경에 대해서는 [Bluemix Local](/docs/hybrid?topic=local-local)을 참조하십시오. 

{{site.data.keyword.Bluemix_notm}}에 대한 전체 서비스 설명은 [Cloud Services terms](http://www-03.ibm.com/software/sla/sladb.nsf/sla/bm){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")에 있습니다.

### 가용성 중단 시간 SLA  
{: #avail-downtime}

99.5% 미만의 가용성으로 작동 중단이 발생하는 경우 계정에 대한 크레딧을 제공받을 수 있습니다. 가용성 중단 시간은 서비스 인스턴스에 연결할 수 없는 총 시간(분)입니다. 총 중단 시간(분)은 사용자가 가동 중단 이벤트에 대한 보고서를 제출할 때 시작되고 영향을 받는 인스턴스 중 하나 이상이 사용 가능하게 될 때 종료됩니다.

{{site.data.keyword.Bluemix_notm}}에서는 다음에 대한 99.95% 가용성 SLA를 제공합니다. 
- 각 서비스에 대한 카탈로그 세부사항에 설명된 대로 고가용성을 위해 구성된 퍼블릭 환경의 클라우드 서비스 
- 지리적으로 분리된 데이터 센터에 있는 여러 데디케이티드 또는 로컬 환경의 클라우드 서비스 

|유형	 |설명	 |지원 세부사항|
|-------------------------------------------------------------------------------|--------------------|----------------|
|고가용성 퍼블릭 환경 또는 다중 데디케이티드/로컬 환경 |기타 환경 |크레딧         |
| <99.95%                                                                       |<99.5%              |10%             |
| <99.90%                                                                       |<99.0%              |25%             |
{: caption="표 2. 월별 가용성 서비스 레벨" caption-side="top"}

가용률은 약정된 월의 총 시간(분)에서 해당 월의 총 중단 시간(분)을 차감한 후 이를 해당 월의 총 시간(분)으로 나누어 계산합니다. 

예를 들어, 31일이 있는 월에서 총 시간이 44,640분입니다. 6시간의 가용성 중단이 발생하는 경우 중단 시간은 360분입니다. 중단 시간이 6시간이면 가용성이 99.19%입니다. 99.19%는 99.90% 미만이므로 퍼블릭 또는 로컬 환경에서 25% 크레딧을 제공받을 수 있습니다.   

```
= (월별 총 44,640분 - 작동 중단 360분) / 월별 총 44,640분
= (실제 사용 가능한 44,280분) / 월별 총 44,640분
= 99.19% 가용성
```

지정된 제외사항, {{site.data.keyword.Bluemix_notm}} UI 비가용성, 컨텐츠를 다시 로드, 구성, 사용 설정 또는 액세스하는 시간과 관련된 작동 중단이나 장애는 SLA에 포함되지 않습니다.

가용성 중단 시간 SLA에는 {{site.data.keyword.Bluemix_notm}} 인프라 서비스가 포함되어 있지 않습니다. 
{: note}

### 인프라 서비스 SLA
{: #iaas-slas}

인프라 서비스는 Bare Metal Server, 가상 서버, 네트워킹, 스토리지 및 보안 서비스입니다. 인스라 서비스의 전체 목록을 찾으려면 `iaas` 태그를 사용하여 {{site.data.keyword.Bluemix_notm}} 카탈로그를 검색하십시오. 

중단 시간은 공용 네트워크, 사설 네트워크, 중복 인프라 전원 및 HAVC 가동 중단에 따른 서비스 중단으로 인해 고객이 식별한 인프라 서비스가 사용 불가능한 총 시간(분)입니다. 서비스에 영향을 주는 유효성 검증된 가동 중단이 식별되면 서비스가 사용 가능한 시간까지 총 중단 시간(분) 계산이 시작됩니다. 

스케줄되거나 공지된 유지보수 시간은 중단 시간에 포함되지 않습니다. 30분 동안의 연속 중간 시간마다 가동 중단에 직접 영향을 받는 식별된 서비스에 대한 월별 요금의 5%에 해당하는 크레딧을 받습니다. 중단 시간이 연속 30분 미만이면 크레딧을 받을 수 있는 자격이 없습니다. 다른 가동 중단 유형의 중단 시간은 이 계산을 충족하기 위해 결합되지 않을 수 있습니다. 

### 인프라 하드웨어 교체 및 업그레이드 SLA
{: #hw-replaceupgrade-sla}

{{site.data.keyword.Bluemix_notm}}에서는 고장난 하드웨어를 교체하거나 스케줄된 하드웨어 업그레이드를 수행할 때 작동 중단 시간을 최소화하려고 합니다. 

{{site.data.keyword.Bluemix_notm}}에서는 다음에 대한 크레딧을 제공합니다. 
- 하드웨어 교체({{site.data.keyword.Bluemix_notm}}에서 고객이 하드웨어 장애를 보고했음을 확인한 시간부터의 교체 시간 기준)
- 계획된 하드웨어 업그레이드(업그레이드를 받는 서비스의 총 중단 시간 기준) 

운영 체제 또는 애플리케이션을 다시 로드하는 데 필요한 시간 또는 성능이 저하될 수 있는 시간은 서비스 레벨 시간에서 제외됩니다. {{site.data.keyword.Bluemix_notm}}가 지정된 서비스 레벨 기간을 충족하지 못한 경우 하드웨어 교체 또는 업그레이드에 영향을 받는 서비스에 대한 월별 요금을 기준으로 크레딧을 받을 수 있습니다.

|서비스 레벨 기간 | 크레딧 백분율 |
|---------------------------|----------------|
|≤ 2시간                 |없음           |
|> 2시간                 | 20%            |
|> 6시간                 | 40%            |
|> 10시간                | 60%            |
|> 14시간                | 80%            |
|> 18시간                | 80%            |
{: caption="표 3. 하드웨어 교체 또는 업그레이드에 영향을 받는 서비스에 대한 월별 요금을 기준으로 하는 크레딧" caption-side="top"}

### 청구
{: #claims}

서비스 레벨이 충족되지 못한 경우 약정 월의 말일로부터 60일 이내에 청구를 제출하십시오. 영향을 받은 서비스, 오류 메시지 및 청구의 유효성을 검증하는 데 필요한 기타 정보를 식별하기에 충분한 정보를 제공하십시오. 

크레딧은 약정 월 동안 영향을 받은 서비스의 누적 가용성을 기준으로 적용 가능한 최대의 보상이며, 영향을 받은 서비스의 월별 요금을 사용하여 계산합니다. 크레딧은 월별 요금의 25%를 초과할 수 없습니다.

작동 중단 시간에 대한 청구를 제출하려면 [{{site.data.keyword.Bluemix_notm}} 지원 센터 ](https://cloud.ibm.com/unifiedsupport/supportcenter){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")에 문의하십시오.

### 제외사항
{: #exclusions}

다음과 같은 이유로 SLA를 충족하지 못하면 크레딧이 제공되지 않습니다.
- 고객 또는 커뮤니티에서 제공한 컨텐츠, 기술, 디자인 또는 지시사항에 대한 문제점
- 베타, 시범 또는 무료 클라우드 서비스
- 비IBM 빌드팩
- 지원되지 않는 시스템 구성 및 플랫폼
- 네트워크, 하드웨어, 설비 또는 전원을 포함한 고객 인프라 장애
- 고객 시스템 관리 조치, 명령 또는 파일 전송
- 고객 오류 또는 가동 중단을 해결하는 데 필요한 정보나 액세스 제공 실패
- 고객으로 인한 보안 사고 또는 보안 테스트
- IBM의 합리적인 통제를 벗어난 기타 원인
