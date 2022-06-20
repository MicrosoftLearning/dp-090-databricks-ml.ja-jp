---
lab:
  title: Azure Databricks でデータを操作する
  module: Module 1 - Introduction to Azure Databricks
ms.openlocfilehash: bfcfa2b977cac7df5284ffbced8fa94c516f7829
ms.sourcegitcommit: e397eba14f6dd257b83e0584f42e459cfe84bfbd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "138100270"
---
# <a name="working-with-data-in-azure-databricks"></a>Azure Databricks でデータを操作する

DBFS を使用してデータを読み込み、Spark データフレームを使用してデータを操作する方法について説明します。
Databricks File System (DBFS) は、Databricks ワークスペースにマウントされ、Databricks クラスター上で使用できる分散ファイル システムです。
データフレームは、データの分散コレクションであり、これを使用すると、大量のデータを処理することができます。

## <a name="prerequisites"></a>前提条件

このラボを開始する前に、「**Azure Databricks の概要**」ラボを完了し、ご自分の Azure Databricks 環境を設定し、必要なデータとノートブックをインポートします。

## <a name="work-with-data-in-azure-databricks"></a>Azure Databricks でデータを操作する

この演習では、Azure Databricks 環境内でデータを読み込んで操作する方法について説明します。

1. Web ブラウザーで、Azure Databricks ワークスペースを開きます。

1. クラスターが実行されていない場合は、**コンピューティング** ページでクラスターを選択し、 **&#9654; [スタート]** ボタンを使用して起動します

1. Azure Databricks ワークスペースで、左側のコマンドバーを使用して、 **[ワークスペース]** を選択します。 次に、 **[ユーザー]** 、**&#9751; *your_user_name*** の順に選択します。 その後、**01 - Azure Databricks の概要** という名前のフォルダーで、 **[Azure Databricks でデータを操作する]** ノートブックを開きます。

1. クラスターにノートブックをアタッチします。 次に、ノートブック内の注意事項を読み、各コード セルを順番に実行します。

## <a name="clean-up"></a>クリーンアップ

今のところ Azure Databricks の操作が終了している場合は、Azure Databricks ワークスペースの **[コンピューティング]** ページで、クラスターを選択し、 **[&#9632; Terminate]** を選択して、シャットダウンします。 それ以外の場合は、次の演習のために実行したままにします。
