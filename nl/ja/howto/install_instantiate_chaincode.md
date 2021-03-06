---

copyright:
  years: 2017
lastupdated: "2017-08-14"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:pre: .pre}

# チェーンコードのインストールとインスタンス化

チェーンコードとは、台帳内の資産を作成して変更するためのビジネス・ロジックとトランザクション命令がカプセル化されている、Go または Java で記述されたソフトウェアです。チェーンコードは、これと対話する必要のある任意のピアに関連付けられた Docker コンテナーで実行されます。チェーンコードの開発方法について詳しくは、[Chaincode Tutorials ![外部リンク・アイコン](../images/external_link.svg "外部リンク・アイコン")](http://hyperledger-fabric.readthedocs.io/en/latest/chaincode.html) を参照してください。
{:shortdesc}

チェーンコードは、まずピアのファイル・システムにインストールされてから、チャネルでインスタンス化されます。すべてのチャネル・メンバーは、このチェーンコードを実行するすべてのピアにチェーンコードをインストールする必要があります。チャネル・メンバーが同じチェーンコードを使用するには、チェーンコードのインストール中に、チェーンコードに対して同じ名前とバージョンを指定する必要があります。インスタンス化のステップには、キー値ペアの初期化とチェーンコード・コンテナーのデプロイメントが含まれます。アプリケーションがチェーンコードと対話する際に経由するすべてのピアには、ピアのファイル・システム上にインストールされたチェーンコードと、実行中のチェーンコード・コンテナーが必要です。ただし、ピアが複数のチャネルで同じチェーンコードを使用する場合も、必要なチェーンコード・コンテナーのインスタンスは 1 つだけです。  

インストールとインスタンス化の組み合わせは強力な機能です。これにより、ピアが複数のチャネルで同じチェーンコード・コンテナーと対話できるからです。前提条件は、ピアのファイル・システムに実際のチェーンコードのソース・ファイルをインストールことのみです。そのため、共通のチェーンコードの断片が数十個のチャネルにわたって使用されている場合でも、ピアがすべてのチャネル台帳で読み取り/書き込みを実行するために必要なチェーンコード・コンテナーの数は 1 つのみです。ネットワークが拡大してチェーンコードがより複雑化していけば、この軽量なアプローチが計算のパフォーマンスおよびスループットの面で有効であることが明らかになります。  

## チェーンコードのインストール
このチェーンコードを実行するすべてのピアにチェーンコードをインストールする必要があります。以下の手順を実行して、チェーンコードをインストールします。
1. ネットワーク・モニターの「チェーンコード (Chaincode)」画面で、チェーンコードのインストール先のピアをドロップダウン・リストから選択します。**「チェーンコードのインストール (Install Chaincode)」**ボタンをクリックします。 ![チェーンコード画面](../images/chaincode_install_overview.png "チェーンコード画面")  
  
2. **「チェーンコードのインストール (Install Chaincode)」**ポップアップ・パネルで、チェーンコードの名前とバージョンを入力します。この名前とバージョンのストリングは、インストールされたチェーンコードと対話するためにアプリケーションで使用されることに**注意**してください。**「参照」**ボタンをクリックし、ローカル・ファイル・システムでチェーンコードのソースが格納されている場所にナビゲートします。ピアにインストールするチェーンコードのソース・ファイルを 1 つ以上選択します。この例は、`fabric-peer-org2-17439a` ピアにインストールされる、名前が `Chaincode1` でバージョンが `v001` のチェーンコードのソース・ファイル `fabcar.go` を示しています。![チェーンコードのインストール](../images/chaincode_install.png "チェーンコードのインストール")

## チェーンコードのインスタンス化
チャネルに参加するすべてのピアのファイル・システムにチェーンコードがインストールされた後、チャネル上でチェーンコードをインスタンス化して、ピアがチェーンコード・コンテナーを介して台帳と対話できるようにする必要があります。このインスタンス化により、必要なチェーンコードの初期化が実行されます。多くの場合、これにはチェーンコードの初期ワールド・ステートを構成するキー値ペアの設定が含まれます。  

チェーンコードをインスタンス化するには、チャネルに対する**オペレーター**または**ライター**の権限が必要です。複数の異なるピア上にある同じ名前とバージョンのチェーンコードは、チェーンコード・コンテナーをデプロイするために 1 回だけインスタンス化する必要があります。以下の手順を実行して、チェーンコードをインスタンス化します。
1. ネットワーク・モニターの「チェーンコード (Chaincode)」画面で、チェーンコードをインストールしたピアを選択し、インスタンス化するチェーンコードをチェーンコード表から見つけます。その後、**「アクション」**ヘッダーの下にある**「インスタンス化」**ボタンをクリックします。  
  ![チェーンコードのインスタンス化](../images/chaincode_instantiate.png "チェーンコードのインスタンス化")  
  
2. **「チェーンコードのインスタンス化 (Instantaite Chaincode)」**ポップアップ・パネルで、チェーンコードの初期化の引数としてキーと値のペアを設定し、インスタンス化するチャネルを選択します。**「送信」**をクリックします。![チェーンコードのインスタンス化のパネル](../images/chaincode_instantiate_panel.png "チェーンコードのインスタンス化のパネル")   
