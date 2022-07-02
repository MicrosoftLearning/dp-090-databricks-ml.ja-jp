---
lab:
  title: 'ラボ: Azure Machine Learning で実験を実行する'
  module: Module 4 - Integrating Azure Databricks and Azure Machine Learning
ms.openlocfilehash: 164163c5477a4116e4f46d432f84058e6c420e52
ms.sourcegitcommit: e397eba14f6dd257b83e0584f42e459cfe84bfbd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "138100309"
---
# <a name="running-experiments-in-azure-machine-learning"></a>ラボ: Azure Machine Learning で実験を実行する

機械学習は主に、アプリケーションに予測サービスを提供するために使用できるモデルのトレーニングに関するものです。 この演習では、Azure Databricks から Azure Machine Learning の実験を実行する方法について学習します。

## <a name="prerequisites"></a>前提条件

このラボを開始する前に、「**Azure Databricks の概要**」ラボを完了し、ご自分の Azure Databricks 環境を設定し、必要なデータとノートブックをインポートします。

## <a name="install-libraries-on-the-azure-databricks-cluster"></a>Azure Databricks クラスターにライブラリをインストールする

実行するノートブックは、クラスターにインストールする必要がある特定の Python ライブラリによって異なります。 次の手順では、これらの依存関係を追加する手順について説明します。

- Azure Databricks ワークスペース内の、 **[クラスター]** セクションからクラスターを選択します。 クラスターの状態が **[実行中]** であることを確認します。
- **[ライブラリ]** リンクを選択し、次に **[新規インストール]** を選択します。
- ライブラリ ソースで **[PyPi]** を選択し、 **[パッケージ]** テキスト ボックスに `azureml-sdk[databricks]` と入力して、 **[インストール]** を選択します。
- 次に、`sklearn-pandas==2.1.0` をインストールします
- 次に、`azureml-mlflow` をインストールします

## <a name="deploy-an-azure-machine-learning-workspace"></a>Azure Machine Learning ワークスペースをデプロイする

1. ご自分のサブスクリプションで、既に Azure Machine Learning ワークスペースを作成してある場合は、「[演習:Azure Machine Learning で実験を実行する](#Exercise-Running-experiments-in-Azure-Machine-Learning)」セクションにスキップできます。

1. [Azure portal](https://portal.azure.com/#home) で、新しいリソースを作成します。**Machine Learning**

1. 表示される [Machine Learning ワークスペースの作成] ダイアログで、次の値を指定します。

   - **サブスクリプション**:Azure サブスクリプションを選択します。
   - **[リソース グループ]** : Azure Databricks ワークスペースをデプロイするリソース グループを選択します。
   - **ワークスペース名**: aml-ws
   - **[リージョン]** : 最も近くのリージョンを選択します (Azure Databricks ワークスペースと Azure Machine Learning ワークスペースが異なる場所にあっても構いません)。

1. Azure Machine Learning ワークスペースの作成を確認して完了します。

## <a name="run-an-experiment-in-azure-machine-learning"></a>Azure Machine Learning で実験を行う

この演習では、Azure Databricks 環境内でデータを読み込んで操作する方法について説明します。

1. Web ブラウザーで、Azure Databricks ワークスペースを開きます。

1. クラスターが実行されていない場合は、**コンピューティング** ページでクラスターを選択し、 **&#9654; [スタート]** ボタンを使用して起動します

1. Azure Databricks ワークスペースで、左側のコマンドバーを使用して、 **[ワークスペース]** を選択します。 次に、 **[ユーザー]** 、**&#9751; *your_user_name*** の順に選択します。 次に、**04 - Integrating Azure Databricks and Azure Machine Learning** という名前のフォルダーで、**1.0 Running experiments in Azure Machine Learning** \(1.0 Azure Machine Learning で実験を行う\) ノートブックを開きます。

1. クラスターにノートブックをアタッチします。 次に、ノートブック内の注意事項を読み、各コード セルを順番に実行します。

## <a name="clean-up"></a>クリーンアップ

今のところ Azure Databricks の操作が終了している場合は、Azure Databricks ワークスペースの **[コンピューティング]** ページで、クラスターを選択し、 **[&#9632; Terminate]** を選択して、シャットダウンします。 それ以外の場合は、次の演習のために実行したままにします。
