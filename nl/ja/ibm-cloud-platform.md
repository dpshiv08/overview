---


copyright:
  years: 2016, 2019
lastupdated: "2019-06-20"

keywords: console, platform overview, overview

subcollection: overview

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# {{site.data.keyword.Bluemix_notm}} プラットフォームとは何ですか?
{: #whatis-platform}

IBM のクラウド・プラットフォームは、Platform as a Service (PaaS) と Infrastructure as a Service (IaaS) を組み合わせて、統合エクスペリエンスを提供します。 このプラットフォームは、小規模な開発チームと組織、および大規模な企業ビジネスの両方を拡大およびサポートします。 世界中のデータ・センターにグローバルにデプロイされる、{{site.data.keyword.cloud}} で構築するソリューションは、テスト済みでサポートされた、信頼できる環境で、高速かつ確実に稼働します。
{: .shortdesc}

下の図に示されているように、{{site.data.keyword.Bluemix_notm}} プラットフォームは、連携する複数のコンポーネントで構成されており、一貫性のある信頼できるクラウド・エクスペリエンスを提供します。 

  * クラウド・リソースの作成、表示、管理のフロントエンドとして機能する堅固なコンソール
  * 両方のプラットフォーム・サービスのユーザーを安全に認証し、{{site.data.keyword.Bluemix_notm}} 全体で一貫してリソースへのアクセスを制御する ID およびアクセス管理コンポーネント
  * 数百の {{site.data.keyword.Bluemix_notm}} オファリングで構成されるカタログ
  * リソースをフィルタリングおよび識別するための検索およびタグ付けのメカニズム
  * 価格設定プランおよびセキュア・クレジット・カード詐欺防止のために正確な使用量を提供するアカウントおよび請求管理システム
  
![{{site.data.keyword.cloud_notm}} プラットフォームのコンポーネント。](images/IBM-Cloud-Platform.svg "{{site.data.keyword.cloud_notm}} プラットフォームの主なコンポーネントを示す図")

最新化してクラウドに取り入れる[既存のコード](/docs/apps/tutorials?topic=creating-apps-tutorial-byoc#tutorial-byoc)があるか、[まったく新しいアプリケーション](/docs/apps/tutorials?topic=creating-apps-tutorial-starterkit)を開発しているかにかかわらず、開発者は、{{site.data.keyword.Bluemix_notm}} で使用可能なサービスおよびランタイム・フレームワークの急速に成長しているエコシステムを活用できます。

## アカウントのセットアップ
{: #set-up-account}

{{site.data.keyword.Bluemix_notm}} を単に試用している場合は、すぐにカタログに移動して、検討したいオファリングの確認を開始して、ライト・アカウントに追加することができます。 ただし、開発者グループ用または組織全体用の環境で開始して、アプリを実動環境で実行する準備ができている場合は、ご使用のアカウントに以下の基本を設定することを検討してください。

* ユーザーおよびサービス ID を 1 つのエンティティーに編成して、アクセス権の割り当てを、合理化されたプロセスにするためのユーザー・アクセス・グループ。
* リソースを編成してリソース・セットへのアクセス権の割り当てを素早く簡単にするためのリソース・グループ。
* IAM アクセス・ポリシーまたは Cloud Foundry の組織とスペースの役割を必要とするアクセス・グループまたは個々の開発者のアクセス・ポリシー。

詳しくは、『[アカウントをセットアップするためのベスト・プラクティス](/docs/account?topic=account-account_setup)』および『[アクセス権限を割り当てるためのベスト・プラクティス](/docs/iam?topic=iam-account_setup)』を参照してください。 

## 価格設定および請求処理
{: #pricing-billing}

アカウント・タイプに関係なく、無料の割り当て量を提供するサービスに対してライト・プランを使用して {{site.data.keyword.Bluemix_notm}} を探索できます。 カタログからサービスを選択してタイルを選択するときに、別のタイプの使用可能プランがある場合は、価格設定情報の詳細を表示できます。 有料プランでサービス・プランを選択する場合は、コスト見積もりツールを使用してコストを見積もることができます。 詳しくは、[コストの見積もり](/docs/billing-usage?topic=billing-usage-cost)を参照してください。

{{site.data.keyword.Bluemix_notm}} の請求処理は、{{site.data.keyword.Bluemix_notm}} プラットフォームが価格設定、アカウント、使用量などを安全に管理できるようにする複数のサービスを提供しています。

### アカウント管理
{: #account-mgmt}

アカウント管理は、顧客との請求関係を維持します。 各アカウントは、1 人の顧客を表す請求エンティティーです。 このサービスは、アカウントのライフサイクル、サブスクリプション、ユーザー関係、および組織を制御します。

### 料金
{: #pricing}

価格設定プラットフォーム・サービスは、ユーザーが {{site.data.keyword.Bluemix_notm}} カタログ内のリソースの価格情報を定義、管理、および取得するのに役立ちます。

### 使用量の計量
{: #metering}

使用量の計算により、サービス・プロバイダーは、{{site.data.keyword.Bluemix_notm}} ユーザーによってプロビジョンされたリソース・インスタンスに関して収集されたメトリックを送信することができます。 統合請求サービスを提供するサード・パーティー・サービス・プロバイダーは、すべてのアクティブ・サービス・インスタンスの使用量を 1 時間ごとに送信する必要があります。 

### 使用状況レポート
{: #usage}

使用状況レポートは、指定した月のアカウントのサマリーを返します。 アカウント請求管理者は、これらのレポートへのアクセスを許可されています。

## {{site.data.keyword.Bluemix_notm}} カタログ
{: #catalog}

{{site.data.keyword.Bluemix_notm}} カタログは、{{site.data.keyword.Bluemix_notm}} コンソールにあるリソースのオファリング定義 (説明、機能、イメージ、URL など) を保管します。 オファリングは、SoR (Systems of Record、定型業務処理システム) として複数の地域にまたがって管理されます。 カタログは、コマンド・ライン・インターフェース (CLI) および RESTful API をサポートします。ユーザーはこれらで、既存のオファリングに関する情報を取得し、それらのオファリングのリソースを作成、管理、および削除することができます。 詳しくは、[カタログの管理](/docs/overview?topic=overview-manage-catalog)を参照してください。

## リソースの作成
{: #provisioning-layer}

リソース・コントローラーは、アカウント内の {{site.data.keyword.Bluemix_notm}} リソースのライフサイクルを管理する、次世代の {{site.data.keyword.Bluemix_notm}} プラットフォーム・プロビジョニング・レイヤーです。 リソースは、アカウント有効範囲内でグローバルにプロビジョンされます。 リソース・コントローラーは、リソースの同期および非同期の両方のプロビジョニングをサポートします。 リソースの例としては、データベース、アカウント、プロセッサー、メモリー、およびストレージ制限などがあります。 

一般に、プロビジョニング・レイヤーでトラッキングされるリソースは、使用量メトリックと請求を関連付けるよう意図されていますが、必ずしもそうとは限りません。 場合によっては、リソース・ライフサイクルをアカウント・ライフサイクルとともに管理できるように、リソースがプロビジョニング・レイヤーに関連付けられていることがあります。 リソース・コントローラーは、プロビジョニング・レイヤーに対して実行されるアクションの認証および許可のために {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) を使用します。

### リソース・ライフサイクルの管理
{: #lifecycle}

リソース・コントローラーは、インスタンスの作成からアクセス資格情報の作成、アクセス権限の削除、インスタンスの削除までのリソースのライフサイクルを制御するための一般的な API を提供します。

## リソースの管理
{: #resource-manager}

リソースの集合は、[リソース・グループ](/docs/overview?topic=overview-whatis-rgs)によって管理されます。 リソース・グループは、アカウントに関連付けられています。 すべての {{site.data.keyword.Bluemix_notm}} リソースは、リソース・グループに割り当てられている必要があります。 アカウントを作成すると、ユーザーのためにデフォルトのリソース・グループが作成されます。 {{site.data.keyword.Bluemix_notm}} IAM 対応リソースはすべて、リソース・グループ内でプロビジョンする必要があります。 ライト・アカウントを使用している場合は、1 つのリソース・グループしか持てません。 従量課金 (PAYG) アカウントまたはサブスクリプション・アカウントを使用している場合は、複数のリソース・グループを作成できます。 アカウントが中断されると、対応するリソース・グループも中断され、リソース・グループ内のすべてのリソースが中断されます。 

## リソースの検索とタグ付け
{: #search-and-tag}

検索サービスは、{{site.data.keyword.Bluemix_notm}} プラットフォーム内に統合されるグローバルの共有リソース・プロパティー・リポジトリーです。 これはクラウド・リソースの属性を保管および検索するために使用され、リソースの分類を行います。 リソースは、[クラウド・リソース名 (CRN)](/docs/overview?topic=overview-crn) ID によって一意的に識別されます。 リソースのプロパティーには、タグとシステム・プロパティーが含まれます。 どちらのプロパティーも {{site.data.keyword.Bluemix_notm}} 請求アカウント内で定義され、多くの地域にまたがっています。

このサービスは、リソースに関連付けられたタグも管理します。 タグ付け API を使用して、タグの作成、削除、検索、添付、または切り離しを行うことができます。 タグは、CRN ID によって一意的に識別されます。 タグには名前があります。その名前は、請求アカウント内で固有でなければなりません。 タグは、key:value ペア、またはラベル形式で作成できます。

## リソースのモニタリング
{: #resources_observability}

プログラム識別情報によって、{{site.data.keyword.Bluemix_notm}} 内のアプリケーションおよびサービスを 1 カ所でモニターおよび監視できます。 

{{site.data.keyword.la_full}} サービスでは、ユーザーの {{site.data.keyword.Bluemix_notm}} アーキテクチャーにログ管理機能を追加でき、システム・ログおよびアプリケーション・ログを管理できます。 また、モニター、トラブルシューティング、アラートの定義、カスタム・ダッシュボードの設計を行うための拡張機能もあります。 {{site.data.keyword.la_full_notm}} は、{{site.data.keyword.IBM_notm}} とのパートナーシップにより LogDNA で運用されます。 詳しくは、『[{{site.data.keyword.la_full_notm}} 概説](/docs/services/Log-Analysis-with-LogDNA?topic=LogDNA-getting-started)』を参照してください。

{{site.data.keyword.mon_full_notm}} サービスにより、アプリケーション、サービス、およびプラットフォームのパフォーマンスと正常性に関して、運用の可視化が可能になります。 また、モニター、トラブルシューティング、アラートの定義、カスタム・ダッシュボードの設計のための拡張機能により、フルスタック・テレメトリーが提供されます。 {{site.data.keyword.mon_full_notm}} は、{{site.data.keyword.IBM_notm}} との協力関係のもと、Sysdig によって運用されます。 詳しくは、『[IBM Cloud Monitoring with Sysdig サービス概説](/docs/services/Monitoring-with-Sysdig?topic=Sysdig-getting-started#getting-started)』を参照してください。

## アカウントのモニタリング 
{: #account_observability}

{{site.data.keyword.at_full}} サービスを使用すると、ご使用の {{site.data.keyword.Bluemix_notm}} アカウントのアクティビティーをモニターし、異常なアクティビティーや重要なアクションを調査し、規定された監査要件に準拠することができます。 さらに、アクションが発生した際にそれに関するアラートを通知させるようにできます。 収集されるイベントは、Cloud Auditing Data Federation (CADF) 標準に準拠しています。 詳しくは、『[{{site.data.keyword.at_full_notm}} 概説](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started)』を参照してください。
