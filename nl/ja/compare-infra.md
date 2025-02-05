---
copyright:
  years: 2019
lastupdated: "2019-06-05"

keywords: understanding infrastructure, vpc, classic infrastructure, cloud environment

subcollection: overview

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}
{:note: .note}

# {{site.data.keyword.cloud_notm}} インフラストラクチャー環境の比較
{: #compare-infrastructure}

ワークロードおよびアプリケーションに最も適しているのはどの環境なのかを判断するため、{{site.data.keyword.cloud}} インフラストラクチャー環境の主な相違点を比較します。
{: shortdesc}

環境タイプについてよく知らない場合は、以下の説明をお読みください。

* クラシック・インフラストラクチャーは、以前からある IaaS プラットフォームです。 この環境は、「リフトアンドシフト」方式のワークロードに最適であり、アプリケーションを素早く移動すること、および同じアーキテクチャーを保つことを可能にします。
* VPC インフラストラクチャーは、新しい IaaS プラットフォームであり、ソフトウェア定義ネットワーキングに基づいていて、クラウド・ネイティブのアプリケーションにとって理想的です。

クラシック・インフラストラクチャーと VPC インフラストラクチャーのコストは中立的であるため、どの環境が自分のニーズに最適であるかということに注視できます。
{: note}

## コンピュートに関する差異
{: #compare-compute}

以下の表に、クラシックと VPC のコンピュートに関する相違点を示します。 

| カテゴリー   |  クラシック・インフラストラクチャー   | VPC インフラストラクチャー |
| ---------- | ------------------------- | ------------------ |
|  サービス  |{{site.data.keyword.baremetal_short}}、{{site.data.keyword.BluVirtServers_short}} インスタンス、VMware、SAP など、カタログにあるすべてのサービス | {{site.data.keyword.BluVirtServers_short}} インスタンスのみ |
| パフォーマンスおよび可用性 | | より優れた可用性がゾーン・アーキテクチャーによって実現可能 |
| 料金 | 時間単位および月単位の請求、および請求処理中断機能 | 時間単位の請求、請求処理中断、および継続使用割引 |
| 仮想サーバー・ファミリー | パブリック、専用、一時、予約済み | パブリックのみ |
| プロファイル | GPU プロファイルも含めて、すべてのプロファイル | より大きな RAM および vCPU オプションを伴う、平衡型プロファイル、コンピュート・プロファイル、メモリー・プロファイル |
| サポートされるイメージ | 事前にストックされたイメージの完全セット、およびカスタム・イメージ | 事前にストックされたイメージの限定セット|
| プラットフォーム統合 | | 統一されたエクスペリエンスのための IAM とリソース・グループの統合 |
{: row-headers}
{: class="comparison-table"}
{: caption="表 1. コンピュート比較" caption-side="top"}
{: summary="This table has row and column headers. The row headers identify possible features. The column headers indentify the differentiators between classic infrastructure and VPC infrastructure. To understand the differences between environments, navigate to the row and find the details for the feature that you're interested in."}

## ネットワークに関する差異
{: #compare-network}

以下の表に、クラシックと VPC のネットワーキングに関する相違点を示します。  

| カテゴリー   |  クラシック・インフラストラクチャー   | VPC インフラストラクチャー |
| ---------- | ------------------------- | ------------------ |
| ロケーション構成体    | データ・センターと POD <br>(2 つの異なるポッド/データ・センターを接続するために VLAN スパンニングが必要な場合があり、また、トラフィックの制御およびルーティングのためにゲートウェイの購入が必要な場合があります) | インフラストラクチャーを抽象する地域モデルであるため、ポッドのロケーションについて心配する必要はありません。|
| ネットワーク機能およびサービス |複数のベンダーからの物理アプライアンスおよび仮想アプライアンス | クラウド・ネイティブなネットワーク機能 (VPN、LBaaS)<br>(VPC 分離、パブリック・クラウドから切り分けられた専用リソース、VPN と LBaaS のためのより多くのオプション、複数の vNIC インスタンス、より大きいサブネット・サイズ) |
| IP アドレス | IPv6 アドレスがサポートされます | IPv4 アドレスのみ |
| ゲートウェイ・ルーティング | 仮想ネットワーク・アプライアンスまたは物理ネットワーク・アプライアンス (仮想ルーター・アプライアンス、Vyatta、Juniper vSRX、Fortinet FSA) を使用 | トラフィックのルーティングは、パブリック・ゲートウェイおよび浮動 IP サービスによって処理されます |
| ネットワーク・アドレス変換 (NAT) | 仮想ネットワーク・アプライアンスまたは物理ネットワーク・アプライアンス (仮想ルーター・アプライアンス、Vyatta、Juniper vSRX、Fortinet FSA) を使用 | BYOIP (Bring-your-own-IP: ユーザー所有の IP を持ち込む) 機能によってサポートされます  |
| IPsec 仮想プライベート・ネットワーク (VPN) | 仮想ネットワーク・アプライアンスまたは物理ネットワーク・アプライアンス (仮想ルーター・アプライアンス、Vyatta、Juniper vSRX、Fortinet FSA) を使用 | VPN-as-a-service オファリングとともにサポートされます |
|  エラスティック・ロード・バランシング | Cloud Load Balancer  | Load Balancer for VPC |
| グローバル・ロード・バランシング| Cloud Internet Services、Citrix Netscaler MPX | Cloud Internet Services |
|ハイブリッド接続 | IBM Cloud とユーザー IT 環境の間のブリッジとしての NAT ソリューション | NAT または IPSec トンネルなしに、ユーザー所有のプライベート IP アドレスを持ち込み <br>注: クラシック・インフラストラクチャー・リソースにアクセスするようにユーザーの VPC を有効にすることができます。|
{: row-headers}
{: class="comparison-table"}
{: caption="表 2. ネットワーク比較" caption-side="top"}
{: summary="This table has row and column headers. The row headers identify possible features. The column headers indentify the differentiators between classic infrastructure and VPC infrastructure. To understand the differences between environments, navigate to the row and find the details for the feature that you're interested in."}

## ストレージに関する差異
{: #compare-storage}

以下の表に、クラシックと VPC のストレージに関する相違点を示します。

|  クラシック・インフラストラクチャー   | VPC インフラストラクチャー |
| ------------------------- | ------------------ |
|ストレージ・サービス、ブロック・ストレージ (iSCSI) およびファイル・ストレージ (NFS ベース) のオファリングの堅固なセット| 1 次ブート・ディスクとしてのブロック・ストレージ (基本的なライフサイクル管理あり)、および 2 次データ・ボリューム  <br> 注: プロビジョニング時にボリューム暗号化が使用可能です。|
{: caption="表 3. ストレージ比較" caption-side="top"}

## セキュリティーに関する差異
{: #compare-security}

以下の表に、クラシックと VPC のセキュリティーに関する相違点を示します。

|  クラシック・インフラストラクチャー   | VPC インフラストラクチャー |
| ---------- | ------------------------- |
|Vyatta、Fortigate、Juniper vSRX、VSI 用セキュリティー・グループ| セキュリティー・グループ、ネットワーク・アクセス制御リスト (ACL)|
{: caption="表 4. セキュリティー比較" caption-side="top"}

## API に関する差異
{: #compare-apis}

以下の表に、クラシックと VPC の API に関する相違点を示します。

|  クラシック・インフラストラクチャー   | VPC インフラストラクチャー |
| ------------------------- | ------------------ |
|既存の {{site.data.keyword.slapi_short}} (SLAPI)| 開発者向けの REST ベースの新しい API |
{: caption="表 5. API 比較" caption-side="top"}

## 次のステップ
{: #compare-nextsteps}

すべての VPC インフラストラクチャー機能を検討するには、『[仮想プライベート・クラウドについて](/docs/vpc-on-classic?topic=vpc-on-classic-about)』を参照してください。 インフラストラクチャー全体を検討するには、『[インフラストラクチャーの構築](/docs/overview?topic=overview-first-steps-it-ops)』を参照してください。
