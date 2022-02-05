---
lab:
    title: 'Azure Machine Learning で実験を実行する'
    module: 'モジュール 4 - Azure Databricks と Azure Machine Learning を統合する'
---

# Azure Machine Learning で実験を実行する

機械学習は主に、アプリケーションに予測サービスを提供するために使用できるモデルのトレーニングに関するものです。この演習では、Azure Databricks から Azure Machine Learning で実験を実行する方法を学習します。

## 前提条件

このラボを開始する前に、**Azure Databricks　の概要**のラボを完了して、Azure Databricks 環境をセットアップし、必要なデータとノートブックをインポートしてください。

## Azure Databricks クラスター上にライブラリをインストールする

実行するノートブックは、クラスターにインストールする必要がある特定の Python ライブラリによって異なります。次の手順では、これらの依存関係を追加する手順を説明します。

- Azure Databricks ワークスペース内の「**クラスター**」セクションで、クラスターを選択します。クラスターの状態が**実行中**であることを確認してください。
- 「**ライブラリ**」リンクを選択してから、「**新規インストール**」を選択します。
- 「ライブラ リソース」で「**PyPi**」を選択し、「**パッケージ**」テキスト ボックスに`azureml-sdk[databricks]` と入力して、「**インストール**]を選択します。
- 次に、`sklearn-pandas==2.1.0` をインストールします
- 次に、`azureml-mlflow` をインストールします

## Azure Machine Learning ワークスペースをデプロイする

1. サブスクリプションで Azure Machine Learning ワークスペースを既に作成している場合は、[演習: Azure Machine Learning で実験を実行する](#Exercise-Running-experiments-in-Azure-Machine-Learning)のセクションにスキップできます。

1. [Azure Portal](https://portal.azure.com/#home) で、新しいリソースを作成します。**機械学習**

1. 表示される「機械学習ワークスペースの作成」ダイアログで、次の値を入力します。

   - **サブスクリプション**: Azure サブスクリプションを選択します。
   - **リソース グループ**: Azure Databricks ワークスペースをデプロイしたリソースグループを選択します。
   - **ワークスペース名**: aml-ws
   - **リージョン**: 最も近いリージョンを選択します (Azure Databricks ワークスペースと Azure Machine Learning ワークスペースが異なる場所にある場合は問題ありません)。

1. Azure Machine Learning ワークスペースの作成を確認して完了します。

## Azure Machine Learning で実験を実行する

この演習では、AzureDatabricks 環境内でデータを読み込んで操作する方法を学習します。

1. Web ブラウザーで、Azure Databricks ワークスペースを開きます。

1. クラスターが実行されていない場合は、「**コンピューティング**」ページでクラスターを選択し、「**&#9654;開始**」ボタンを使用してクラスターを開始します

1. Azure Databricks ワークスペースで、左側のコマンド バーを使用して、「**ワークスペース**」を選択します。次に、「**ユーザー**」を選択し、**&#9751; *your_user_name*** を選択します。次に、**04 - Azure Databricks と Azure Machine Learning を統合する**という名前のフォルダーで、**1.0 Azure Machine Learning で実験を実行示する**のノートブックを開きます。

1. ノートブックをクラスターに接続します。次に、ノートブック内の注意事項を読み、各コード セルを順番に実行します。

## クリーンアップ

今のところ Azure Databricks の操作が終了している場合は、Azure Databricks ワークスペースの「**コンピューティング**」ページで、クラスターを選択し、「**&#9632;終了**」を選択して、シャットダウンします。それ以外の場合は、次の演習のために実行したままにします。
