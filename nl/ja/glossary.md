---

copyright:
  years: 2017, 2018
lastupdated: "2018-06-14"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# 用語集
{: #glossary}

{{site.data.keyword.blockchainfull}}・プラットフォームは、ブロックチェーンでのやりとりを簡素化します。 このトピックでは、この資料に記載されている用語を定義し、ブロックチェーンの概念を紹介します。 用語について詳しくは、[Hyperledger Fabric ![「外部リンク」アイコン](images/external_link.svg "「外部リンク」アイコン")](http://hyperledger-fabric.readthedocs.io/en/master/glossary.html) を参照してください。
{:shortdesc}

## 資産
ブロックチェーン・ネットワーク上で取引されるアイテムとして表される有形または無形の商品、サービス、またはプロパティー。

## ブロック
順序付けられたトランザクション集合。チャネル上の先行ブロックに暗号的にリンクされます。

## ビジネス・ネットワーク
ブロックチェーン・ネットワークの定義。これには、ブロックチェーン・ソリューションのデータ・モデル、トランザクション・ロジック、およびアクセス制御ルールが含まれます。 ビジネス・ネットワーク定義は、[Hyperledger Composer](#hyperledger-composer) を使用して作成されます。 ビジネス・ネットワーク定義は、デプロイ可能な **.bna** (ビジネス・ネットワーク・アーカイブ) ファイルにパッケージ化されます。

## CA
認証局。 すべての参加メンバーに証明書を発行するブロックチェーン・ネットワーク・リソースです。 これらの証明書は、メンバーの ID を表します。 ネットワーク内のすべてのエンティティー (ピア、順序付けサービス、クライアントなど) には、通信や認証やトランザクションで使用する ID が必要です。 これらの ID は、ブロックチェーン・ネットワークの直接的な参加者すべてに必要です。 CA 用のビジネス・ネットワーク・カードを作成できます。 その後に [CA カード](develop_starter.html#developing-business-networks-with-starter-plan)をインポートし、そのカードを使用してスターター・プランの認証局から有効な証明書の管理秘密鍵を交換します。

## チェーン
台帳のチェーンは、トランザクションのハッシュ・リンク・ブロックとして構造化されたトランザクション・ログです。 ピアは順序付けサービスからトランザクションのブロックを受け取り、エンドースメント・ポリシーおよび並行性違反に基づいてブロックに有効または無効のマークを付け、そのブロックをピアのファイル・システム上のハッシュ・チェーンの末尾に追加します。

## チェーンコード
チェーンコードはスマート・コントラクトとも呼ばれ、台帳を照会または更新するための一連の関数を含むソフトウェアです。

## チャネル
プライベートに取引するネットワーク・メンバーのサブセットで構成されます。 チャネルは、チャネルのメンバーが特定の規則と、チャネル・メンバーのみがアクセスできる個別の台帳を作成できるようにすることにより、データの分離と機密性を提供します。 ピアは、組織のトランザクション・エンドポイントとして機能するノードであり、チャネルに結合されます。

## クライアント
クライアントは、ユーザーに代わって行動するエンティティーを表します。 ブロックチェーンと通信するには、ピアに接続する必要があります。 クライアントは、任意のピアに接続できます。 クライアントはトランザクションを作成して呼び出します。 クライアントは、実際のトランザクション呼び出しをエンドーサーに送信し、トランザクション・プロポーザルを順序付けサービスにブロードキャストします。

## 接続プロファイル
接続プロファイルは、 **「接続プロファイル」**ボタンをクリックすると、ネットワーク・モニターの「概要」画面に表示されます。 この情報は JSON フォーマットで使用可能で、ネットワーク・リソース (ピア、順序付けプログラム、CA) の API エンドポイント情報と 登録 ID/秘密鍵が含まれています。 アプリケーションはこれらの API エンドポイントを介してネットワーク・リソースと対話します。

## コンセンサス
台帳トランザクションをネットワーク全体で同期させるためのコラボレーション・プロセス。 コンセンサスにより、適切な参加者がトランザクションを承認するときにのみ台帳が更新され、また、同じ順序の同じトランザクションにより、台帳が更新されます。 コンセンサスを達成するためのアルゴリズム的な方法はいろいろあります。

## CouchDB
スターター・プラン・ネットワークで台帳データベースに使用される文書ストア。CouchDB は LevelDB と並んで、エンタープライズ・プラン・ネットワークのオプションでもあります。CouchDB は索引の使用をサポートしており、ピア上のデータに対してリッチ・クエリーを発行できます。

## 現在の状態
台帳の現在の状態は、チェーン・トランザクション・ログに含まれるすべてのキーの最新の値を表します。 現在の状態は、チャネルに認識されているすべての最新のキー値を表すため、「ワールド・ステート」と呼ばれることもあります。 チェーンコードは、現在の状態のデータに対してトランザクション・プロポーザルを実行します。 キーの値が変更されるか、新しいキーが追加されるたびに現在の状態は変化します。 現在の状態はトランザクション・フローにとって重要です。最新のキーと値のペアを変更するには、そのペアが既知でなければならないからです。 ピアは、ブロック内の有効なトランザクションごとに、最新の値を台帳の現在の状態にコミットします。 現在の状態はピアの台帳データベースに格納されます。

## 動的メンバーシップ
**「登録」**特権を持つユーザーは、メンバーを動的にネットワークに追加することができます。 また、メンバーには役割や属性も割り当てられます。これは、ネットワークでのアクセスと権限を制御します。 ただし、役割も属性も動的に割り当てることはできません。 Hyperledger Fabric は、ネットワーク全体の運用を損なうことなく、メンバー、ピア、および順序付けサービス・ノードの追加や削除をサポートします。 動的メンバーシップは、さまざまな理由でビジネス関係の調整や、エンティティーを追加または削除する必要がある場合に重要です。

## エンドースメント
チェーンコード・トランザクションを検証するプロセス。 エンドースメント・ルールは、エンドースメント・ポリシーを指定することによって実装されます。

## エンドースメント・ポリシー
特定のチェーンコード・アプリケーションに接続されたトランザクションを実行する必要があるチャネル上のピア・ノード、および必要な応答の組み合わせ (エンドースメント) を定義します。 ポリシーでは、承認ピアの最小数、承認ピアの最小パーセンテージ、または特定のチェーンコード・アプリケーションに割り当てられているすべての承認ピアによって、トランザクションを承認しなければならない場合があります。 ポリシーは、意図的であるかどうかにかかわらず、アプリケーションおよび不正行為に対して必要な回復力レベルに基づいて、承認ピアにより調達できます。 送信されるトランザクションは、関わっているピアにより有効とマーク付けされる前に、このエンドースメント・ポリシーを満たす必要があります。 トランザクションをインストールおよびインスタンス化するための別のエンドースメント・ポリシーも必要です。

## ジェネシス・ブロック
ブロックチェーン・ネットワークまたはチャネルを初期化し、チェーンの最初のブロックとしても機能する構成ブロック。

## HSM
ハードウェア・セキュリティー・モジュール。 オンデマンド暗号化、鍵管理、および鍵格納をマネージド・サービスとして提供します。 HSM は、リソース集中型の暗号化処理タスクを処理し、アプリケーションの待ち時間を削減する物理アプライアンスです。 詳しくは、[ハードウェア・セキュリティー・モジュール![「外部リンク」アイコン](images/external_link.svg "「外部リンク」アイコン」")](https://www.ibm.com/cloud/hardware-security-module) を参照してください。

## Hyperledger Composer
[Hyperledger Composer ![「外部リンク」アイコン](images/external_link.svg "「外部リンク」アイコン")](https://hyperledger.github.io/composer/latest/introduction/introduction.html) は、オープン・ソースの開発ツール・セットです。 これは、JavaScript トランザクションと結合された bespoke モデリング言語と、ブロックチェーン・ビジネス・ネットワークを完全にモデル化するためのアクセス制御ルールを使用します。 Hyperledger Composer を使用して、既存のシステムおよびデータをブロックチェーン・アプリケーションと統合してから、実際のブロックチェーンにデプロイすることができます。

## Hyperledger Fabric
[Hyperledger Fabric ![「外部リンク」アイコン](images/external_link.svg "「外部リンク」アイコン")](http://hyperledger-fabric.readthedocs.io/en/master/) は Linux Foundation がホストするビジネス・ブロックチェーン・フレームワークで、ブロックチェーン・アプリケーションまたはソリューションを、モジュラー・アーキテクチャーで開発するための基盤として機能します。 コンセンサス・サービスやメンバーシップ・サービスなどの Hyperledger Fabric コンポーネントは、プラグ・アンド・プレイです。

## インストール
チェーンコードをピアのファイル・システムに配置するプロセス。 このチェーンコードを実行するすべてのピアにチェーンコードをインストールする必要があります。

## インスタンス化
特定のチャネルでチェーンコード・コンテナーを開始および初期化するプロセス。 チェーンコードがピアにインストールされ、すべてのピアがチャネルに参加したら、チェーンコードをチャネル上でインスタンス化する必要があります。 インスタンス化は、チェーンコードの初期状態を構成するキーと値のペアの設定を含む、チェーンコードの必要な初期化を実行します。 インスタンス化の後、チェーンコードがインストールされているピアはチェーンコード呼び出しを受け入れることができます。

## Kafka
ブロックチェーン・ネットワーク内で順序付けサービス・ノードのクラスターとなる Hyperledger Fabric のコンセンサス・プラグイン実装。 kafka 実装は、実動ネットワークのためのものです。

## 台帳
トランザクションの不変のシーケンス・レコードと、現在の状態を維持するための状態データベースを保管する、文字どおり「ブロックのチェーン」から構成されています。 チャネルごとに 1 つの台帳があり、それに対する更新は、特定のチャネルのポリシーに従ってコンセンサス・プロセスによって管理されます。

## 台帳データベース (Ledger database)
現在の状態のデータは、チェーンコードからの効率的な読み取りとクエリーのためにピアのデータベースに格納されます。スターター・プラン・ネットワークは台帳データベースとして CouchDB を使用します。エンタープライズ・プラン・ネットワークは LevelDB または CouchDB のいずれかを使用できます。

## LevelDB
CouchDB とともに、エンタープライズ・プラン・ネットワークの台帳データベースのオプションであるキー値ストア。LevelDB は現在の状態をキー値ペアとして格納し、索引やリッチ・クエリーの使用はサポートしていません。

## メンバー
「組織」とも呼ばれ、ブロックチェーン・ネットワーク内のメンバーは、グループのメンバーと同じように、ネットワークの構造を形成します。 メンバーは多国籍企業のような大きな場合も、個人のように小さい場合もあります。 メンバーは、ネットワークをサービス・プロバイダー (証明書の発行、トランザクションの検証/順序付けなど) またはコンシューマーとして使用する許可を付与する証明書を使用して、ネットワークに登録されます。 前者は、トランザクション検証、トランザクションの順序付け、および証明書管理サービスを含む基本的なブロックチェーン・サービスを提供します。 コンシューマー・メンバーは、ネットワークを使用して、分散台帳に対してトランザクションを呼び出します。 メンバーは複数のピアを持つことができます。

## MSP
メンバーシップ・サービス・プロバイダー。  ブロックチェーン・ネットワーク全体で証明書および ID を発行および検証するための暗号メカニズムおよびプロトコルのセット。 メンバーシップ・サービス・プロバイダーの範囲内で発行された ID は、そのメンバーシップ・サービス・プロバイダーのルール検証ポリシー内で評価できます。 MSP は各チャネル・ピアにインストールされ、ピアに対して発行されるトランザクション要求が、必ず認証済みの許可ユーザー・アイデンティティーから発信されるようにします。

## ネットワーク
{{site.data.keyword.cloud_notm}} 上の {{site.data.keyword.blockchainfull_notm}} プラットフォーム・サービスのインスタンス。

## ネットワーク資格情報
ネットワーク・モニターの「API」画面で確認できます。 資格情報には、Swagger UI に「key」 (ユーザー名) と「secret」 (パスワード) が含まれます。 REST API を試す前に、これらのネットワーク資格情報を使用して認証する必要があります。

## ネットワーク・モニター
ブロックチェーン・ネットワークを表示および管理するために {{site.data.keyword.blockchainfull_notm}} プラットフォームが提供する GUI ダッシュボード。

## ノード
ブロックチェーンの通信エンティティー。 ノードには CA、ピア、順序付けサービス (チャネルの順序付けの集合) の 3 つのタイプがあります。

## 順序付けプログラム
順序付けサービスのノード。 クライアント認証サービスを提供するブロックチェーン・ネットワーク・リソースです。 さらに、トランザクションの順序付けとブロードキャストするサービスも提供します。

## 組織
「[メンバー](#member)」を参照。

## 順序付けサービス
各ブロックチェーン・ネットワークには 1 つの順序付けサービスが必要です。 順序付けサービスはネットワーク・メンバーからトランザクションを収集し、トランザクションを順序付けてブロックにバンドルします。 次に、順序付けサービスは新規ブロックをピアに配布します。ピアはブロックを検証し、それを各チャネルの台帳に追加します。 順序付けサービスはネットワーク全体の共通バインディングでもあります。 これには、各メンバーに紐付けられた暗号 ID 情報が含まれており、ネットワークにアクセスするためのクライアントおよびピアの ID を認証します。

## 参加者
ブロックチェーン・ネットワークと対話する任意の組織、個人、アプリケーション、またはデバイス。 「参加者」というくくりの中に、メンバーとユーザーという 2 つのグループがあります。

## ピア
トランザクションの実行と検証、および台帳の保守を行うサービスを提供するブロックチェーン・ネットワーク・リソース。 ピアはチェーンコードを実行します。また、トランザクションの履歴情報やネットワーク・チャネルに存在する資産の現在の状態に関する情報の保有者です。 これらは組織によって所有および管理され、チャネルに結合されます。

## サービス資格情報
サービス資格情報は JSON 形式で記述されており、ピアや順序付けノード、CA などネットワーク・リソースの API エンドポイント情報と登録 ID/秘密鍵が含まれています。 アプリケーションはこれらの API エンドポイントを介してネットワーク・リソースと対話します。

## SDK
Hyperledger Fabric は 2 つの Software Development Kit (SDK) をサポートします。 ノード SDK および Java SDK です。  ノード SDK は NPM を介して、Java SDK は Maven を介してインストールできます。  SDK には独自の git リポジトリー、つまり [ファブリック・ノード SDK ![「外部リンク」アイコン](images/external_link.svg "「外部リンク」アイコン")](https://github.com/hyperledger/fabric-sdk-node) および[ファブリック Java SDK ![「外部リンク」アイコン](images/external_link.svg "「外部リンク」アイコン")](https://github.com/hyperledger/fabric-sdk-java) があり、使用可能な API の資料が付いています。 Hyperledger Fabric のクライアント SDK は、クライアント・アプリケーションとブロックチェーン・ネットワーク間の対話を可能にします。

## SOLO
ブロックチェーン・ネットワーク内で単一の順序付けサービス・ノードとなる Hyperledger Fabric のコンセンサス・プラグイン実装。 スターター・プラン・ネットワークは SOLO 実装を使用します。 SOLO 実装は実動ネットワーク用ではありません。 SOLO に代わるものとして Kafka クラスターがあります。

## トランザクション
ブロックチェーン・ネットワーク上の参加者が資産と対話するために使用するメカニズム。 トランザクションは新規チェーンコードを作成するか、既存のチェーンコードで操作を呼び出します。

## ユーザー
ユーザーは、ブロックチェーン・ネットワークの既存のメンバーとの信頼関係に基づいて台帳に間接的にアクセスできる参加者です。

## ワールド・ステート
[現在の状態](#current-state)を参照してください。