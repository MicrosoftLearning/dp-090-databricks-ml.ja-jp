---
lab:
    title: 'Azure Machine Learning でモデルをデプロイする'
    module: 'モジュール 4 - Azure Databricks と Azure Machine Learning を統合する'
---

# Azure Machine Learning でモデルをデプロイする

機械学習は主に、アプリケーションに予測サービスを提供するために使用できるモデルのトレーニングに関するものです。この演習では、Azure Databricks でモデルをトレーニングしてから、Azure Machine Learning でモデルをデプロイする方法を学習します。

## 前提条件

このラボを開始する前に、**Azure Databricks の概要**と **Azure Machine Learning で実験を実行する**のラボを完了して、Azure Databricks と Azure Machine Learning 環境をセットアップしてください。

## Azure Machine Learning にモデルをデプロイする

この演習では、AzureDatabricks 環境内でデータを読み込んで操作する方法を学習します。

1. Web ブラウザーで、Azure Databricks ワークスペースを開きます。

1. クラスターが実行されていない場合は、「**コンピューティング**」ページでクラスターを選択し、「**&#9654;開始**」ボタンを使用してクラスターを開始します

1. Azure Databricks ワークスペースで、左側のコマンド バーを使用して、「**ワークスペース**」を選択します。次に、「**ユーザー**」を選択し、**&#9751; *your_user_name*** を選択します。次に、**04 - Azure Databricks と Azure Machine Learning を統合する**という名前のフォルダーで、**2.0 Azure Machine Learning でモデルをデプロイする**のノートブックを開きます。

1. ノートブックをクラスターに接続します。次に、ノートブック内の注意事項を読み、各コード セルを順番に実行します。

## クリーンアップ

今のところ Azure Databricks の操作が終了している場合は、Azure Databricks ワークスペースの「**コンピューティング**」ページで、クラスターを選択し、「**&#9632;終了**」を選択して、シャットダウンします。

Azure Databricks の探索が終了したら、Azure Databricks および Azure Machine Learning リソースを含む Azure サブスクリプションのリソース グループを削除できます。
