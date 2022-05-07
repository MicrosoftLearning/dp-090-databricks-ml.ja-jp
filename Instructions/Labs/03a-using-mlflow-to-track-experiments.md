---
lab:
  title: MLflow を使用した実験の追跡
  module: Module 3 - Managing Experiments and Models
ms.openlocfilehash: 931fc6d405a591dab6f2539e590eb11ba0b8c7ba
ms.sourcegitcommit: e397eba14f6dd257b83e0584f42e459cfe84bfbd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "138100272"
---
# <a name="using-mlflow-to-track-experiments"></a>MLflow を使用した実験の追跡

MLflow は、完全な機能を備えたモデル追跡およびレジストリ システムです。  この演習では、MLflow を使用してモデル トレーニングの成果物、メトリック、パラメーターを収集します。  その後、Azure Databricks UI またはプログラムを使用して、これらの出力を表示できるようになります。 まず、対話型クラスターを使用して Azure Databricks ワークスペースにアクセスできる必要があります。 ワークスペースや必要なクラスターがない場合は、次の手順を実行します。 それ以外の場合は、「[Databricks ノートブックのアーカイブのアップロード](#Upload-the-Databricks-notebook-archive)」セクションに進むことができます。

## <a name="prerequisites"></a>前提条件

このラボを開始する前に、「[**Azure Databricks の概要**](Instructions/Labs/01a-introduction-to-azure-databricks.md)」ラボを完了し、ご自分の Azure Databricks 環境を設定し、必要なデータとノートブックをインポートします。 MLflow を使用するには、セットアップ ラボの指示に従って、**ML Databricks Runtime** バージョンのコンピューティング クラスターを使用する必要があります。 このランタイムには、MLflow のインストールが既に含まれています。

## <a name="use-mlflow-to-track-experiments"></a>MLflow を使用して実験を追跡する

この演習では、Azure Databricks 環境内でデータを読み込んで操作する方法について説明します。

1. Web ブラウザーで、Azure Databricks ワークスペースを開きます。

1. クラスターが実行されていない場合は、**コンピューティング** ページでクラスターを選択し、 **&#9654; [スタート]** ボタンを使用して起動します

1. Azure Databricks ワークスペースで、左側のコマンドバーを使用して、 **[ワークスペース]** を選択します。 次に、 **[ユーザー]** 、**&#9751; *your_user_name*** の順に選択します。 次に、**03 - Managing Experiments and Models** という名前のフォルダーで、**01 - Using MLflow to Track Experiments** \(01 - MLflow を使って実験を追跡する\) ノートブックを開きます。

1. クラスターにノートブックをアタッチします。 次に、ノートブック内の注意事項を読み、各コード セルを順番に実行します。

> **ヒント**: 「**Databricks UI を使用した実験、実行、および実行の詳細の表示**」というタイトルのセクションで、実行するアクションについて説明します。これらのアクションは、ノートブックの範囲外で実行されるためです。  ブラウザーで 2 番目のタブを開き、ノートブックの手順を確認しながら、そのタブでこれらのアクションを実行するのが最も簡単な方法かもしれません。

## <a name="clean-up"></a>クリーンアップ

今のところ Azure Databricks の操作が終了している場合は、Azure Databricks ワークスペースの **[コンピューティング]** ページで、クラスターを選択し、 **[&#9632; Terminate]** を選択して、シャットダウンします。 それ以外の場合は、次の演習のために実行したままにします。
