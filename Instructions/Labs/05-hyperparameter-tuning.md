---
lab:
  title: Azure Databricks を使用したハイパーパラメーターの調整
  module: Optional exercise
ms.openlocfilehash: 9e306580175e11fdeca127b2a7fc6e2a7ed1de0f
ms.sourcegitcommit: e397eba14f6dd257b83e0584f42e459cfe84bfbd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "138100310"
---
# <a name="set-up-for-hyperparameter-tuning"></a>ハイパーパラメーター調整の設定

まず、対話型クラスターを使用して Azure Databricks ワークスペースにアクセスできる必要があります。 ワークスペースや必要なクラスターがない場合は、次の手順を実行します。 それ以外の場合は、以下の **[データのアップロード]** セクションにスキップすることができます。 2 つの演習を完了するには、**2 つの異なるデータセット** をアップロードする必要があることに注意してください。

## <a name="create-azure-databricks-resources"></a>Azure Databricks リソースの作成

Azure Databricks を使用するには、まず Azure サブスクリプションで Azure Databricks ワークスペースをデプロイし、ノートブックとコードを実行するクラスターを作成する必要があります。 その後、ワークスペースで実験するデータとノートブックをアップロードできます。

### <a name="deploy-an-azure-databricks-workspace"></a>Azure Databricks ワークスペースをデプロイする

1. [Azure portal](https://portal.azure.com) で、次の設定を指定して新しい **Azure Databricks** リソースを作成します。
   - **[サブスクリプション]** : *ワークスペースをデプロイする Azure サブスクリプションを選択します。*
   - **[リソース グループ]** : *新しいリソース グループを作成します。*
   - **[ワークスペース名]** : *ワークスペースの名前を指定します。*
   - **[リージョン]** : *デプロイ用としてお近くの場所を選択します。Azure Databricks でサポートされているリージョンのリストについては、[リージョン別の利用可能な Azure サービス](https://azure.microsoft.com/regions/services/)に関するページを参照してください。*
   - **[価格レベル]** :Standard

1. ワークスペースが作成されるまで待機します。 ワークスペースの作成には数分かかります。 ワークスペース作成時に、ポータルの右側に [Submitting deployment for Azure Databricks](Azure Databricks のデプロイを送信しています) タイルが表示されます。 このタイルを表示するために、ダッシュボードを右へスクロールしなければならない場合があります。 スクリーンの上部に進行状況バーも表示されます。 いずれかの領域で進行状況を確認できます。

### <a name="create-a-cluster"></a>クラスターの作成

1. Azure Databricks ワークスペース リソースが作成されたら、ポータルでリソースに移動し、 **[ワークスペースの起動]** を選択して新しいタブで Databricks ワークスペースを開き、メッセージが表示されたらサインインします。

1. Databricks ワークスペースの左側のメニューで **[コンピューティング]** を選択してから、 **[+ クラスターの作成]** を選択して、次の構成で新しいクラスターを追加します。
   - **[名前]** : *一意の名前を入力します。*
   - **クラスター モード**:単一ノード
   - **プール**:None
   - **Databricks ランタイムのバージョン**: *ランタイムの利用可能な最新バージョンの **ML** エディションを選択します。バージョンが選択されていることを確認します:*
      - *GPU を使用 **しない***
      - *Scala > **2.11** を含める*
      - *Spark > **3.0** を含める*
   - **終了までの時間**: 120 分間操作しないとロックする
   - **ノードの種類**: Standard_DS3_v2

1. クラスターが作成されるまで待ちます。数分かかる場合があります。 クラスターは自動的に開始され、最終的にクラスター名の横にある回転している *保留中* のインジケーターが緑色の丸に変化し、*実行中* の状態であることが示されます。

### <a name="upload-dataset-exercise-1"></a>データセットのアップロード演習 1

1. `https://github.com/MicrosoftDocs/ml-basics/blob/master/challenges/data/real_estate.csv` をコンピューターにダウンロードし、任意のフォルダーに **real_estate.csv** として保存します。

1. Databricks ワークスペースの **[データ]** ページで、 **[テーブルの作成]** オプションを選択します。

1. **[ファイル]** 領域で、 **[参照]** を選択し、ダウンロードした **real_estate.csv** ファイルを参照します。

1. ファイルがワークスペースにアップロードされたら、 **[UI を使用してテーブルの作成]** を選択します。 次に、クラスターを選択し、 **[テーブルのプレビュー]** を選択します。

1. 次のテーブル属性を指定して、 **[テーブルの作成]** を選択します。

    - **テーブル名**: real_estate
    - **データベースで作成する**: 既定値
    - **ファイル タイプ**:CSV
    - **列区切り記号**: *コンマ* (,)
    - **最初の行はヘッダーです**: *オン*
    - **推論スキーマ**: *オン*
    - **複数行**: *オフ*

1. テーブルが作成されたら、ワークスペースでそれを表示します。

### <a name="upload-dataset-exercise-2"></a>データセットのアップロード演習 2

1. `https://github.com/MicrosoftDocs/ml-basics/blob/master/challenges/data/wine.csv` をご利用のコンピューターにダウンロードし、任意のフォルダーに **wine.csv** として保存します。

1. Databricks ワークスペースの **[データ]** ページで、 **[テーブルの作成]** オプションを選択します。

1. **[ファイル]** 領域で、 **[参照]** を選択し、ダウンロードした **wine.csv** ファイルを参照します。

1. ファイルがワークスペースにアップロードされたら、 **[UI を使用してテーブルの作成]** を選択します。 次に、クラスターを選択し、 **[テーブルのプレビュー]** を選択します。

1. 次のテーブル属性を指定して、 **[テーブルの作成]** を選択します。

    - **テーブル名**: wine
    - **データベースで作成する**: 既定値
    - **ファイル タイプ**:CSV
    - **列区切り記号**: *コンマ* (,)
    - **最初の行はヘッダーです**: *オン*
    - **推論スキーマ**: *オン*
    - **複数行**: *オフ*

1. テーブルが作成されたら、ワークスペースでそれを表示します。

### <a name="import-databricks-notebooks"></a>Databricks ノートブックをインポートする

1. Azure Databricks ワークスペースで、左側のコマンドバーを使用して、 **[ワークスペース]** を選択します。 次に、 **[ユーザー]** 、**&#9751; *your_user_name*** の順に選択します。

1. 表示されるブレード内で、自分の名前の横にある下向きシェブロン (**v**) を選択し、 **[インポート]** を選択します。

1. **[ノートブックのインポート]** ダイアログで、次の URL からノートブック アーカイブをインポートします。アーカイブ名のフォルダーが作成され、2 つのノートブックが含まれていることに注目してください。
   - `https://github.com/MicrosoftLearning/dp-090-databricks-ml/blob/master/05%20-%20Hyperparameter%20Tuning.dbc`

## <a name="explore-automated-mlflow-hyperparameter-tuning"></a>自動 MLflow でのハイパーパラメーターのチューニングを調べる

この演習では、ハイパーパラメーター調整に自動 MLflow を使用する方法について説明します。

1. ワークスペースの **05 - Hyperparameter tuning** フォルダーで、**1.0 Automated MLflow Hyperparameter Tuning** ノートブックを開きます。

1. 左上のドロップダウン メニューで、ノートブックをそのクラスターに接続するクラスターを選択します。 *(または、接続されていないノートブックで最初のセルを実行すると、クラスターを接続するように求められます)。*

1. ノートブック内の注意事項を読み、各コード セルを順番に実行します。

## <a name="explore-hyperopt-for-hyperparameter-tuning"></a>ハイパーパラメーターのチューニングに対する Hyperopt を調べる

この演習では、ハイパーパラメーター調整に自動 MLflow を使用する方法について説明します。

1. ワークスペースの **05 - Hyperparameter tuning** フォルダーで、**2.0 Automated MLflow Hyperparameter Tuning** ノートブックを開きます。

1. 左上のドロップダウン メニューで、ノートブックをそのクラスターに接続するクラスターを選択します。 *(または、接続されていないノートブックで最初のセルを実行すると、クラスターを接続するように求められます)。*

1. ノートブック内の注意事項を読み、各コード セルを順番に実行します。

## <a name="clean-up"></a>クリーンアップ

今のところ Azure Databricks の操作が終了している場合は、Azure Databricks ワークスペースの **[コンピューティング]** ページで、クラスターを選択し、 **[&#9632; Terminate]** を選択して、シャットダウンします。 それ以外の場合は、次の演習のために実行したままにします。