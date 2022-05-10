---
lab:
  title: Azure Machine Learning にモデルを配置する
  module: Module 4 - Integrating Azure Databricks and Azure Machine Learning
ms.openlocfilehash: 3d1af4dc5af8a66548c81e00f5d6012db1cb8f00
ms.sourcegitcommit: dd49d0d418bf18117549cc0ea1542b754ace865c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2022
ms.locfileid: "139217555"
---
# <a name="deploying-models-in-azure-machine-learning"></a>Azure Machine Learning にモデルを配置する

機械学習は主に、アプリケーションに予測サービスを提供するために使用できるモデルのトレーニングに関するものです。 この演習、Azure Databricks でモデルをトレーニングし、Azure Machine Learning にモデルをデプロイする方法を学習します。

## <a name="prerequisites"></a>前提条件

このラボを開始する前に、「**Azure Databricks の概要**」と「**ラボ: Azure Machine Learning で実験を実行する**」を完了して、Azure Databricks と Azure 機械学習の環境を設定します。

## <a name="install-libraries-on-the-azure-databricks-cluster"></a>Azure Databricks クラスターにライブラリをインストールする

実行するノートブックは、クラスターにインストールする必要がある特定の Python ライブラリによって異なります。 次の手順では、これらの依存関係を追加する手順について説明します。

- Azure Databricks ワークスペース内の、 **[クラスター]** セクションからクラスターを選択します。 クラスターの状態が **[実行中]** であることを確認します。
- **[ライブラリ]** リンクを選択し、次に **[新規インストール]** を選択します。
- ライブラリ ソースで **[PyPi]** を選択し、 **[パッケージ]** テキスト ボックスに `azureml-sdk[databricks]` と入力して、 **[インストール]** を選択します。
- 次に、`sklearn-pandas==2.1.0` をインストールします
- 次に、`azureml-mlflow` をインストールします

## <a name="deploy-a-model-in-azure-machine-learning"></a>Azure Machine Learning でモデルをデプロイする

この演習では、Azure Databricks 環境内でデータを読み込んで操作する方法について説明します。

1. Web ブラウザーで、Azure Databricks ワークスペースを開きます。

1. クラスターが実行されていない場合は、**コンピューティング** ページでクラスターを選択し、 **&#9654; [スタート]** ボタンを使用して起動します

1. Azure Databricks ワークスペースで、左側のコマンド バーを使用して、 **[ワークスペース]** を選択します。 次に、 **[ユーザー]** 、**&#9751; *your_user_name*** の順に選択します。 次に、**モジュール 04 - Azure Databricks と Azure Machine Learning の統合** という名前のフォルダーで、 **[2.0 Azure Machine Learning にモデルを配置する]** ノートブックを開きます。

1. クラスターにノートブックをアタッチします。 次に、ノートブック内の注意事項を読み、各コード セルを順番に実行します。

## <a name="clean-up"></a>クリーンアップ

現時点で Azure Databricks の操作が終了している場合は、Azure Databricks ワークスペースの **[コンピューティング]** ページで、クラスターを選択し、 **&#9632; [終了]** を選択して、シャットダウンします。

Azure Databricks の探索が終了したら、Azure Databricks と Azure Machine Learning リソースを含む Azure サブスクリプション内のリソース グループを削除できます。
