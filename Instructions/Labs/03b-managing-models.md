---
lab:
    title: 'モデルを管理する'
    module: 'モジュール 3 - 実験とモデルを管理する'
---

# モデルを管理する

Azure Databricks モデル レジストリは、モデルの登録、モデルのバージョン管理、デプロイ用のモデルのタグ付けのための強力なツールです。  この演習では、ユーザー インターフェイスと MLflow API の両方を使用して、モデル レジストリを使用する方法を学習します。まず、対話型クラスターを使用して Azure Databricks ワークスペースにアクセスできる必要があります。ワークスペースや必要なクラスターがない場合は、次の手順を実行します。それ以外の場合は、[Databricks ノートブック アーカイブのアップロード](#Upload-the-Databricks-notebook-archive)のセクションにスキップできます。

## 前提条件

このラボを開始する前に、**Azure Databricks の概要**のラボを完了して、Azure Databricks 環境をセットアップし、必要なデータとノートブックをインポートしてください。

## 機械学習モデルのトレーニングと検証

この演習では、AzureDatabricks 環境内でデータを読み込んで操作する方法を学習します。

1. Web ブラウザーで、Azure Databricks ワークスペースを開きます。

1. クラスターが実行されていない場合は、「**コンピューティング**」ページでクラスターを選択し、「**&#9654;開始**」ボタンを使用してクラスターを開始します

1. Azure Databricks ワークスペースで、左側のコマンド バーを使用して、「**ワークスペース**」を選択します。次に、「**ユーザー**」を選択し、**&#9751; *your_user_name*** を選択します。次に、**03 - 実験とモデルを管理する**という名前のフォルダーで、**02 - モデルを管理する**のノートブックを開きます。

1. ノートブックをクラスターに接続します。次に、ノートブック内の注意事項を読み、各コード セルを順番に実行します。

> **ヒント**: 最初のセクション、**ユーザー インターフェイスを介してモデルを管理する**では、実行するアクションについて説明します。これらのアクションの多くは、ノートブックの範囲外で実行されるためです。  ブラウザーで 2 番目のタブを開き、ノートブックの指示を確認しながら、そのタブでこれらのアクションを実行するのが最も簡単な場合があります。

## クリーンアップ

今のところ Azure Databricks の操作が終了している場合は、Azure Databricks ワークスペースの「**コンピューティング**」ページで、クラスターを選択し、「**&#9632;終了**」を選択して、シャットダウンします。それ以外の場合は、次の演習のために実行したままにします。
