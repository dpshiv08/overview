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

# クラウド・リソース名
{: #crn}

クラウド・リソース名 (CRN: Cloud Resource Name) は、{{site.data.keyword.Bluemix_notm}} リソースを一意的に識別します。 CRN は、あいまいさがなく、グローバルに固有であることが保証されるようにリソースを指定するために、例えば {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) のポリシーや、クラウド・カタログにリストされたサービスにおいて使用されます。

CRN は、リソース、そのロケーション、それが属しているサービスを階層的に識別する「セグメント」を連結したもので形成されます。 セグメントの区切り文字は「:」(コロン文字) に設定されています。 すべての CRN はセグメント識別子 `crn` で始まります。


## CRN のフォーマット
{: #format-crn}

CRN の基本正規フォーマットは、次のとおりです。

`   crn:version:cname:ctype:service-name:location:scope:service-instance:resource-type:resource
   `


## version
{: #version-crn}

`version` セグメントは、CRN フォーマットのバージョンを識別します。 現在のところ、有効な version セグメント値は `v1` のみです。


## cname
{: #cname-crn}

`cname` セグメントは、クラウド・インスタンスを識別します。これは、リソースを含んでいるクラウド・インスタンスを一意的に識別する、英数字の識別子です。 `cname` は、識別されたリソースを所有する独立コントロール・プレーンを効果的に識別します。 {{site.data.keyword.Bluemix_notm}} ユーザーの場合は、`cname` セグメントの値は `bluemix` でなければなりません。


## ctype
{: #ctype-crn}

`ctype` セグメントは、指定された `cname` セグメントによって表されるクラウド・インスタンスのタイプを識別します。

 有効な値は以下のとおりです。
  - `public`: パブリック・カタログから使用可能なすべてのサービス
  - `dedicated`: 現行の {{site.data.keyword.Bluemix_notm}} 専用環境の場合のみ
  - `local`: local - ユーザー独自の環境にローカルにデプロイされたすべてのサービス


## service-name
{: #service-name-crn}

`service-name` セグメントは、クラウドによって提供される機能 (サービス、コンポーネント、製品) を一意的に識別します。 機能は、{{site.data.keyword.Bluemix_notm}} カタログにリストされているサービスや {{site.data.keyword.Bluemix_notm}} 機能にとって重要な内部アーキテクチャー・コンポーネントなどと共に、ユーザー提供のサービスとすることができます。

`service-name` セグメントはリソースが属しているサービスを識別し、{{site.data.keyword.Bluemix_notm}} はサービス名がグローバルに固有であるようにします。 `service-name` セグメントには、小文字の英数字を使用しなければならず、スペースも「-」以外の特殊文字も使用できません。

{{site.data.keyword.Bluemix_notm}} カタログに登録済みのサービスの場合、`service-name` セグメントは、{{site.data.keyword.Bluemix_notm}} グローバル・カタログ・サービスに登録されたサービスの 1 つに対応していなければなりません。 それは、対応するリソース・インスタンスに対して {{site.data.keyword.Bluemix_notm}} グローバル・カタログ・サービス API `GET https://globalcatalog.cloud.ibm.com/api/v1/{id}` によって返される `name` プロパティーであるか、または、コマンド・ライン・インターフェース `ibmcloud service offerings` によって列 `service` に表示される `service-name` 値です。


## location
{: #location-crn}

リソースが存在している、クラウドのジオグラフィー/地域/ゾーン/データ・センター。

`location` セグメントは、以下のいずれかの値でなければなりません。

### グローバル
{: #global-crn}

 * `global`

### ジオグラフィー
{: #geos-crn}

 * `us`
 * `eu`
 * `cn`
 * `ap`

### 地域
{: #regions-crn}

 * `us-south`
 * `us-east`
 * `au-syd`
 * `eu-gb`
 * `eu-de`
 * `jp-tok`

### データ・センター
{: #dc-crn}

 * `AMS01`
 * `AMS03`
 * `CHE01`
 * `DAL01`
 * `DAL05`
 * `DAL06`
 * `DAL07`
 * `DAL09`
 * `DAL10`
 * `DAL12`
 * `DAL13`
 * `FRA02`
 * `HKG02`
 * `HOU02`
 * `LON02`
 * `MEL01`
 * `MEX01`
 * `MIL01`
 * `MON01`
 * `OSL01`
 * `PAR01`
 * `SJC01`
 * `SJC03`
 * `SAO01`
 * `SEA01`
 * `SEO01`
 * `SNG01`
 * `SYD01`
 * `TOK02`
 * `TOR01`
 * `WDC01`
 * `WDC04`
 * `WDC06`
 * `WDC07`

地域を必要としないリソースもあります (そういったリソースはグローバルであると判断できます)。この場合、`region` セグメントは `global` に設定されます。
{: tip}


## scope
{: #scope-crn}

`scope` セグメントは、リソースを包含しているもの、またはリソースの所有者を識別します。 所有者を必要としないリソースもあります (そういったリソースは`グローバル`であると判断できます)。 この場合、`scope` セグメントは空 (空ストリング) に設定されます。

`scope` セグメントの値は、`{scopePrefix}`/`{id}` という形式でなければなりません。 `scopePrefix` は、所有者または包含しているものを識別するために使用されるフォーマットを表します。 `id` は、`scopePrefix` に固有のフォーマットで、所有者または包含しているものの ID を表します。

| スコープ・タイプ | スコープ・プレフィックス | 使用法 | 例 |
| --- | --- | --- | --- |
| アカウント | a/`{account id}` | リソースが作成されたアカウント。 | `a/292558` |
| 組織 | o/`{org guid}` | リソースが割り当てられた {{site.data.keyword.Bluemix_notm}} 組織。 | `o/4716e2d1-35b7-431f-891a-b552bf0b3c66` |
| スペース | s/`{space guid}` | リソースが割り当てられた {{site.data.keyword.Bluemix_notm}} スペース。 | `s/48b3cdcd-e804-4398-9032-73065863ad7c` |
{: caption="表 1. scope の使用法" caption-side="top"}



## service-instance
{: #service-instance-crn}

`service-instance` セグメントは、サービス・インスタンスを一意的に識別します。 `service-instance` セグメントのフォーマットは、サービスによって異なります。 各サービスは、サービス・メタデータの一部として `service_instance` セグメントのフォーマットを文書化する必要があります。 サービスによってはインスタンスがないものがあります。インスタンスがグローバルであるためであり、この場合は `service-instance` フィールドはブランクになります。

`service-instance` には、小文字の英数字を使用しなければならず、スペースも「-」と「/」以外の特殊文字も使用できません。

例えば、作業項目を追跡および計画する DevOps ツールでは単純な `GUID` インスタンス ID ("1234-5678-9012-3456") になり、autoscale グループ・サービスのポリシー・コンポーネントは階層的命名規則を使用でき、`service-id` セグメントは次のようになるといった例が考えられます。

>`c7a27f55-d35e-4153-b044-8ca9155fc467/my-test-asg1/my-scaleout-policy`

以下の CLI コマンドを使用して {{site.data.keyword.Bluemix_notm}} リソースから CRN を取得することもできます。
```
ibmcloud resource service-instance
```
{: codeblock}

## resource-type、resource
{: #resource-type-crn}

`resource-type` セグメントおよび `resource` セグメントの値は、サービスによって異なります。 各サービスは、サービス・メタデータの一部として、サポートされる `resource type` セグメントと、`resource` セグメントのフォーマットを文書化する必要があります。

例えば、Object Storage サービス内のカスタマー領収書コンテナー中のイメージの `resource-type` セグメントが `object`、`resource` 値が `CustomerReceipts/clientdinner.png` であるといった例が考えられます。

`resource-type` セグメントには、小文字の英数字を使用しなければならず、スペースも「-」以外の特殊文字も使用できません。 サービスは `resource-type` セグメントがオプションであると決定することができ、その場合は空白のままになります。


## CRN の例
{: #crn_examples}

次の表に、CRN の例を示します。

| 例 | 値 |
| --- | --- |
| Kubernetes ワーカー | `crn:v1:bluemix:public:containers-kubernetes:us-south:a/59bcbfa6ea2f006b4ed7094c1a08dcdd:8042b2a8af6a4a5cbf6dbe09e07311d2:worker:kube-hou02-pa8042b2a8af6a4a5cbf6dbe09e07311d2-w1` |
| リソース・グループ | `crn:v1:bluemix:public:resource-controller: global:a/59bcbfa6ea2f006b4ed7094c1a08dcdd:resource-group:59bcbfa6ea2f006b4ed7094c1a08dcdd` |
| サービス・インスタンス | `crn:v1:bluemix:public:cloud-object-storage:global:a/59bcbfa6ea2f006b4ed7094c1a08dcdd:1a0ec336-f391-4091-a6fb-5e084a4c56f4::` |
| バケット | `crn:v1:bluemix:public:cloud-object-storage:global:a/59bcbfa6ea2f006b4ed7094c1a08dcdd:1a0ec336-f391-4091-a6fb-5e084a4c56f4:bucket:mybucket` |
{: caption="表 2. CRN の例" caption-side="top"}
