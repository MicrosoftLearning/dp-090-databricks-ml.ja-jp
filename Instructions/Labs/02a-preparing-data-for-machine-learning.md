---
lab:
  title: 機械学習用のデータの準備
  module: Module 2 - Training and Evaluating Machine Learning Models
ms.openlocfilehash: c779c63d3b34c05606a93671ba800fd848bed439
ms.sourcegitcommit: e397eba14f6dd257b83e0584f42e459cfe84bfbd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "138100269"
---
# <a name="preparing-data-for-machine-learning"></a>機械学習用のデータの準備

機械学習は主に、アプリケーションに予測サービスを提供するために使用できるモデルのトレーニングに関するものです。 この演習では、Azure Databricks を使用して、機械学習用のトレーニング データを準備する方法について説明します。

## <a name="prerequisites"></a>前提条件

このラボを開始する前に、「**Azure Databricks の概要**」ラボを完了し、ご自分の Azure Databricks 環境を設定し、必要なデータとノートブックをインポートします。

## <a name="prepare-data-for-machine-learning"></a>機械学習用のデータの準備

この演習では、Azure Databricks 環境内でデータを読み込んで操作する方法について説明します。

1. Web ブラウザーで、Azure Databricks ワークスペースを開きます。

1. クラスターが実行されていない場合は、**コンピューティング** ページでクラスターを選択し、 **&#9654; [スタート]** ボタンを使用して起動します

1. Azure Databricks ワークスペースで、左側のコマンド バーを使用して、 **[ワークスペース]** を選択します。 次に、 **[ユーザー]** 、**&#9751; *your_user_name*** の順に選択します。 次に、**02 - 機械学習モデルのトレーニングと評価** という名前のフォルダーで、 **[1.0 特徴付け]** ノートブックを開きます。

1. クラスターにノートブックをアタッチします。 次に、ノートブック内の注意事項を読み、各コード セルを順番に実行します。

## <a name="clean-up"></a>クリーンアップ

現時点で Azure Databricks の操作が終了している場合は、Azure Databricks ワークスペースの **[コンピューティング]** ページで、クラスターを選択し、 **&#9632; [終了]** を選択して、シャットダウンします。 それ以外の場合は、次の演習のために実行したままにします。
