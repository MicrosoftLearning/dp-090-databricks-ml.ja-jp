---
lab:
  title: Azure Databricks の概要
  module: Module 1 - Introduction to Azure Databricks
ms.openlocfilehash: 2f80eb26cad18d2b6aee094392406d8529a6c419
ms.sourcegitcommit: dd49d0d418bf18117549cc0ea1542b754ace865c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2022
ms.locfileid: "139217558"
---
# <a name="getting-started-with-azure-databricks"></a>Azure Databricks の概要

Azure Databricks は、Spark ベースの高速で簡単なコラボレーション型分析サービスです。 ビッグ データ分析、人工知能、パフォーマンスの高いデータ レイク、対話型データ サイエンス、機械学習、コラボレーションを加速するために使用します。
Azure Databricks 環境とその周辺の主要なトピック (ワークスペース、クラスター、ノートブック) を見ていきます。

まず、対話型クラスターを使用して Azure Databricks ワークスペースにアクセスできる必要があります。 ワークスペースや必要なクラスターがない場合は、次の手順を実行します。 それ以外の場合は、以下の **[データのアップロード]** セクションにスキップすることができます。

## <a name="create-azure-databricks-resources"></a>Azure Databricks リソースの作成

Azure Databricks を使用するには、まず Azure サブスクリプションで Azure Databricks ワークスペースをデプロイし、ノートブックとコードを実行するクラスターを作成する必要があります。 その後、ワークスペースで実験するデータとノートブックをアップロードできます。

### <a name="deploy-an-azure-databricks-workspace"></a>Azure Databricks ワークスペースをデプロイする

1. Azure portal 'https://portal.azure.com ' で、次の設定を指定して新しい **Azure Databricks** リソースを作成します。
   - **[サブスクリプション]** : "*ワークスペースをデプロイする Azure サブスクリプションを選択します。* "
   - **[リソース グループ]** : "*新しいリソース グループを作成します。* "
   - **[ワークスペース名]** : "*ワークスペースの名前を指定します。* "
   - **[リージョン]** : "*デプロイ用としてお近くの場所を選択します。Azure Databricks でサポートされているリージョンのリストについては、[リージョン別の利用可能な Azure サービス](https://azure.microsoft.com/regions/services/)に関するページを参照してください。* "
   - **[価格レベル]** :Standard

1. ワークスペースが作成されるまで待機します。 ワークスペースの作成には数分かかります。 ワークスペース作成時に、ポータルの右側に [Submitting deployment for Azure Databricks](Azure Databricks のデプロイを送信しています) タイルが表示されます。 このタイルを表示するために、ダッシュボードを右へスクロールしなければならない場合があります。 スクリーンの上部に進行状況バーも表示されます。 いずれかの領域で進行状況を確認できます。

### <a name="create-a-cluster"></a>クラスターの作成

1. Azure Databricks ワークスペース リソースが作成されたら、ポータルでリソースに移動し、 **[ワークスペースの起動]** を選択して新しいタブで Databricks ワークスペースを開き、メッセージが表示されたらサインインします。

1. Databricks ワークスペースの左側のメニューで **[コンピューティング]** を選択してから、 **[+ クラスターの作成]** を選択して、次の構成で新しいクラスターを追加します。
   - **[名前]** : "*一意の名前を入力します。* "
   - **クラスター モード**:単一ノード
   - **Databricks ランタイムのバージョン**:"*ランタイムの利用可能な最新バージョンの **ML** エディションを選択します。バージョンが選択されていることを確認します:* "
      - "*GPU を使用 **しない***"
      - "*Scala > **2.11** を含める*"
      - "*Spark > **3.0** を含める*"
   - **終了までの時間**:120 分間操作しないとロックする
   - **ノードの種類**:Standard_DS3_v2

1. クラスターが作成されるまで待ちます。数分かかる場合があります。 クラスターは自動的に開始され、最終的にクラスター名の横にある回転している "*保留中*" のインジケーターが緑色の丸に変化し、"*実行中*" の状態であることが示されます。

### <a name="upload-data"></a>データをアップロードする

1. `https://raw.githubusercontent.com/MicrosoftLearning/dp-090-databricks-ml/master/data/nyc-taxi.csv` をご利用のコンピューターにダウンロードし、任意のフォルダーに **nyc-taxi.csv** として保存します。

1. Databricks ワークスペースの **[データ]** ページで、 **[テーブルの作成]** オプションを選択します。

1. **[ファイル]** 領域で、 **[参照]** を選択し、ダウンロードした **nyc-taxi.csv** ファイルを参照します。

1. ファイルがワークスペースにアップロードされたら、 **[UI を使用してテーブルの作成]** を選択します。 次に、クラスターを選択し、 **[テーブルのプレビュー]** を選択します。

1. 次のテーブル属性を指定します。

    - **テーブル名**: nyc_taxi
    - **データベースで作成する**: 既定値
    - **ファイル タイプ**:CSV
    - **列区切り記号**:" *コンマ*" (,)
    - **最初の行はヘッダーです**: "*オン*"
    - **推論スキーマ**: "*オン*"
    - **複数行**: "*オフ*"

1. 各列の適切なデータ型を設定します。**passengerCount** 列を見つけます。 ドロップダウン メニューで、この列を **INT** に設定します。

    - passengerCount:**INT**
    - tripDistance:**DOUBLE**
    - hour_of_day:**INT**
    - day_of_week:**INT**
    - month_num:**INT**
    - normalizeHolidayName:**STRING**
    - isPaidTimeOff:**BOOLEAN**
    - snowDepth:**DOUBLE**
    - precipTime:**DOUBLE**
    - precipDepth:**DOUBLE**
    - temperature:**DOUBLE**
    - totalAmount:**DOUBLE**

1. **[テーブルの作成]** をクリックします。

1. テーブルが作成されたら、ワークスペースでそれを表示します。

### <a name="import-databricks-notebooks"></a>Databricks ノートブックをインポートする

1. Azure Databricks ワークスペースで、左側のコマンドバーを使用して、 **[ワークスペース]** を選択します。 次に、 **[ユーザー]** 、**&#9751; *your_user_name*** の順に選択します。

1. 表示されるブレード内で、自分の名前の横にある下向きシェブロン (**v**) を選択し、 **[インポート]** を選択します。

1. **[ノートブックのインポート]** ダイアログで、次の URL からノートブック アーカイブをインポートします。アーカイブ名のフォルダーが作成され、1 つ以上のノートブックが含まれていることに注目してください。
   - `https://github.com/MicrosoftLearning/dp-090-databricks-ml/raw/master/01%20-%20Introduction%20to%20Azure%20Databricks.dbc`

1. 前の手順を繰り返して、次のノートブック アーカイブをインポートします。インポート時にアーカイブごとにフォルダーが作成されます。

   - `https://github.com/MicrosoftLearning/dp-090-databricks-ml/raw/master/02%20-%20Training%20and%20Evaluating%20Machine%20Learning%20Models.dbc`
   - `https://github.com/MicrosoftLearning/dp-090-databricks-ml/raw/master/03%20-%20Managing%20Experiments%20and%20Models.dbc`
   - `https://github.com/MicrosoftLearning/dp-090-databricks-ml/raw/master/04%20-%20Integrating%20Azure%20Databricks%20and%20Azure%20Machine%20Learning.dbc`

## <a name="explore-azure-databricks"></a>Azure Databricks を探索する

この演習では、Azure Databricks 環境を探索します。

1. ワークスペースの **[01 - Azure Databricks の概要]** フォルダーで、 **[Azure Databricks の開始]** ノートブックを開きます。

1. 左上のドロップダウン メニューで、ノートブックをそのクラスターに接続するクラスターを選択します " *(または、接続されていないノートブックで最初のセルを実行すると、クラスターを接続するように求められます)。* "

1. ノートブック内の注意事項を読み、各コード セルを順番に実行します。

## <a name="clean-up"></a>クリーンアップ

今のところ Azure Databricks の操作が終了している場合は、Azure Databricks ワークスペースの **[コンピューティング]** ページで、クラスターを選択し、 **[&#9632; Terminate]** を選択して、シャットダウンします。 それ以外の場合は、次の演習のために実行したままにします。
