---

copyright:

  years: 2017, 2019

lastupdated: "2019-05-06"

keywords: crn, cloud resource name

subcollection: overview

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# 클라우드 리소스 이름
{: #crn}

클라우드 리소스 이름(CRN)은 {{site.data.keyword.Bluemix_notm}} 리소스를 고유하게 식별합니다. CRN을 사용하면 클라우드 카탈로그에 나열된 {{site.data.keyword.Bluemix_notm}} Identity and Access Management(IAM) 정책 및 서비스에서와 같이 명료하고 글로벌한 고유성이 보장된 방식으로 리소스를 지정할 수 있습니다.

CRN은 리소스, 해당 위치 및 소속된 서비스를 계층 구조로 식별하는 "세그먼트"의 연결을 통해 구성됩니다. 세그먼트 구분 기호는 ':'(콜론 문자)로 설정됩니다. 모든 CRN은 세그먼트 ID `crn`으로 시작됩니다.


## CRN 형식
{: #format-crn}

CRN의 기본적인 표준 형식은 다음과 같습니다.

`crn:version:cname:ctype:service-name:location:scope:service-instance:resource-type:resource`


## version
{: #version-crn}

`version` 세그먼트는 CRN 형식의 버전을 식별합니다. 현재 유일하게 유효한 버전 세그먼트 값은 `v1`입니다.


## cname
{: #cname-crn}

`cname` 세그먼트는 클라우드 인스턴스를 식별하며 리소스가 포함된 클라우드 인스턴스를 고유하게 식별하는 영숫자 ID입니다. `cname`은 식별된 리소스를 소유하는 독립적인 제어 영역을 식별합니다. {{site.data.keyword.Bluemix_notm}} 사용자의 경우 `cname` 세그먼트의 값은 `bluemix`여야 합니다.


## ctype
{: #ctype-crn}

`ctype` 세그먼트는 지정된 `cname` 세그먼트에서 표시하는 클라우드 인스턴스의 유형을 식별합니다.

 올바른 값:
  - `public`: 퍼블릭 카탈로그에서 사용 가능한 모든 서비스
  - `dedicated`: 현재 {{site.data.keyword.Bluemix_notm}} 데디케이티드 환경의 경우에만
  - `local`: 사용자의 환경에 로컬로 배치된 모든 서비스


## service-name
{: #service-name-crn}

`service-name` 세그먼트는 클라우드에서 제공하는 기능(서비스, 컴포넌트, 제품)을 고유하게 식별합니다. 이 기능은 {{site.data.keyword.Bluemix_notm}} 카탈로그에 나열된 서비스와 같은 사용자 제공 서비스이거나 {{site.data.keyword.Bluemix_notm}} 기능에 중요한 내부 아키텍처 컴포넌트일 수 있습니다.

`service-name` 세그먼트는 리소스가 속한 서비스를 표시하며 {{site.data.keyword.Bluemix_notm}}는 서비스 이름의 글로벌 고유성을 적용합니다. `service-name` 세그먼트는 영숫자 또는 소문자여야 하며 공백 또는 '-' 이외의 특수 문자는 사용될 수 없습니다.

{{site.data.keyword.Bluemix_notm}} 카탈로그에 등록된 서비스의 경우, `service-name` 세그먼트는 {{site.data.keyword.Bluemix_notm}} Global Catalog 서비스에 등록된 서비스 중 하나에 대응해야 합니다. 이는 해당 리소스 인스턴스에 대해 {{site.data.keyword.Bluemix_notm}} Global Catalog 서비스 API `GET https://globalcatalog.cloud.ibm.com/api/v1/{id}`에서 리턴한 `name` 특성이거나 명령행 인터페이스에서 `ibmcloud service offerings`를 실행했을 때 `service` 열에 표시되는 `service-name` 값입니다.


## location
{: #location-crn}

리소스가 상주하는 클라우드 지리적 위치/지역/구역/데이터 센터입니다.

`location` 세그먼트는 다음 값 중 하나여야 합니다.

### 글로벌
{: #global-crn}

 * `global`

### 지리적 위치
{: #geos-crn}

 * `us`
 * `eu`
 * `cn`
 * `ap`

### 지역
{: #regions-crn}

 * `us-south`
 * `us-east`
 * `au-syd`
 * `eu-gb`
 * `eu-de`
 * ` jp-tok `

### 데이터 센터
{: #dc-crn}

 * `AMS01  `
 * `AMS03  `
 * `CHE01  `
 * `DAL01  `
 * `DAL05  `
 * `DAL06  `
 * `DAL07  `
 * `DAL09  `
 * `DAL10  `
 * `DAL12  `
 * `DAL13  `
 * `FRA02  `
 * `HKG02  `
 * `HOU02  `
 * `LON02  `
 * `MEL01  `
 * `MEX01  `
 * `MIL01  `
 * `MON01  `
 * `OSL01  `
 * `PAR01  `
 * `SJC01  `
 * `SJC03  `
 * `SAO01  `
 * `SEA01  `
 * `SEO01  `
 * `SNG01  `
 * `SYD01  `
 * `TOK02  `
 * `TOR01  `
 * `WDC01  `
 * `WDC04  `
 * `WDC06  `
 * `WDC07  `

일부 리소스는 글로벌로 간주될 수 있으므로 지역이 필요하지 않습니다. 이 경우에는 `region` 세그먼트가 `global`로 설정됩니다.
{: tip}


## 범위(scope)
{: #scope-crn}

`scope` 세그먼트는 리소스의 소유자 또는 포함을 식별합니다. 일부 리소스에서는 소유자가 필요하지 않습니다(`global`로 간주될 수 있음). 이 경우에는 `scope` 세그먼트가 비어 있습니다(공백 문자열).

`scope` 세그먼트의 값은 `{scopePrefix}`/`{id}`로 형식화되어야 합니다. `scopePrefix`는 소유자 또는 포함을 식별하는 데 사용되는 형식을 표시합니다. `id`는 `scopePrefix`에 특정한 형식의 포함 또는 소유자의 ID를 표시합니다.

|범위 유형 |범위 접두부 | 사용법 |예 |
| --- | --- | --- | --- |
|계정 |a/`{account id}` | 리소스가 작성된 계정입니다. | `a/292558` |
|조직 |o/`{org guid}` | 리소스가 지정된 {{site.data.keyword.Bluemix_notm}} 조직입니다. | `o/4716e2d1-35b7-431f-891a-b552bf0b3c66` |
|영역 |s/`{space guid}` | 리소스가 지정된 {{site.data.keyword.Bluemix_notm}} 영역입니다. | `s/48b3cdcd-e804-4398-9032-73065863ad7c` |
{: caption="표 1. `범위` 사용" caption-side="top"}



## service-instance
{: #service-instance-crn}

`service-instance` 세그먼트는 서비스 인스턴스를 고유하게 식별합니다. `service-instance` 세그먼트의 형식은 서비스별로 다양합니다. 각 서비스는 해당 서비스 메타데이터의 일부로서 해당 `service_instance` 세그먼트의 형식을 문서화해야 합니다. 인스턴스가 글로벌인 서비스에는 인스턴스가 없으며, 이 경우 `service-instance` 필드는 공백입니다.

`service-instance`는 영숫자 또는 소문자여야 하며 공백이나 '-' 및 '/' 이외의 특수 문자가 없어야 합니다.

예를 들어, 작업 항목을 추적하고 계획하기 위한 DevOps 도구에는 단순한 `GUID` 인스턴스 ID("1234-5678-9012-3456")가 있을 수 있습니다. 여기서 오토스케일 그룹 서비스의 정책 컴포넌트는 계층 구조의 이름 지정 규칙을 사용할 수 있으며 다음의 `service-id` 세그먼트를 보유할 수 있습니다.

>`c7a27f55-d35e-4153-b044-8ca9155fc467/my-test-asg1/my-scaleout-policy`

다음 CLI 명령을 사용하여 {{site.data.keyword.Bluemix_notm}} 리소스에서 CRN을 얻을 수 있습니다.
```
ibmcloud resource service-instance
```
{: codeblock}

## resource-type, resource
{: #resource-type-crn}

`resource-type` 및 `resource` 세그먼트의 값은 서비스별로 다양합니다. 서비스는 지원되는 `resource types` 세그먼트와 `resource` 세그먼트의 형식을 해당 서비스 메타데이터의 일부로서 문서화해야 합니다.

예를 들어, Object Storage 서비스에 속한 고객 영수증 컨테이너에 포함된 이미지의 경우에는 `resource-type` 세그먼트가 `object`이고 `resource` 값이 `CustomerReceipts/clientdinner.png`일 수 있습니다.

`resource-type` 세그먼트는 영숫자 또는 소문자여야 하며 공백 또는 '-' 이외의 특수 문자는 사용될 수 없습니다. 서비스는 `resource-type` 세그먼트의 선택사항 여부를 결정할 수 있으며, 선택사항인 경우에는 공백이 유지됩니다.


## CRN 예
{: #crn_examples}

다음 표에는 CRN 예 목록이 나열되어 있습니다. 

|예 |값 |
| --- | --- |
| Kubernetes 작업자 |`crn:v1:bluemix:public:containers-kubernetes:us-south:a/59bcbfa6ea2f006b4ed7094c1a08dcdd:8042b2a8af6a4a5cbf6dbe09e07311d2:worker:kube-hou02-pa8042b2a8af6a4a5cbf6dbe09e07311d2-w1` |
|리소스 그룹 |`crn:v1:bluemix:public:resource-controller: global:a/59bcbfa6ea2f006b4ed7094c1a08dcdd:resource-group:59bcbfa6ea2f006b4ed7094c1a08dcdd` |
|서비스 인스턴스 |`crn:v1:bluemix:public:cloud-object-storage:global:a/59bcbfa6ea2f006b4ed7094c1a08dcdd:1a0ec336-f391-4091-a6fb-5e084a4c56f4::` |
|버킷 |`crn:v1:bluemix:public:cloud-object-storage:global:a/59bcbfa6ea2f006b4ed7094c1a08dcdd:1a0ec336-f391-4091-a6fb-5e084a4c56f4:bucket:mybucket` |
{: caption="표 2. CRN 예" caption-side="top"}
