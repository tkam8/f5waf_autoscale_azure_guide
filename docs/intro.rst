ようこそ
-------

本ガイドでは、F5 WAF (LTM + ASM) の自動スケールとService Discovery(プールメンバーの自動追加)機能のデプロイ方法について説明します。 そして、既存のネットワーク（Vnet）への展開を実施するためのテンプレートを使用します。
https://github.com/F5Networks/f5-azure-arm-templates/tree/master/supported/solutions/autoscale/waf/existing_stack

新規ネットワーク（Vnet）への展開を実施される場合は、以下のテンプレートをご利用ください。
https://github.com/F5Networks/f5-azure-arm-templates/tree/master/supported/solutions/autoscale/waf/new_stack

Azure の要件

- Azure 従量課金 (Pay-As-You-Go) サブスクリプション契約があること 
- Azure サブスクリプションでアプリケーションを共同作成者 (Contributor) ロールに割り当てるためのアクセス権が必要です。 詳細は以下のリンクをご参照下さい。 
  - https://docs.microsoft.com/ja-jp/azure/azure-resource-manager/resource-group-create-service-principal-portal 


  
このガイドのコンテンツは、完全なDevOps CI / CDパイプラインを活用しており、以下のGitHubリポジトリから取得可能です。

https://github.com/tkam8/f5waf_autoscale_azure_guide 

バグまたは新規機能のリクエストは、以下の２つ方法で実施可能です。

- GitHubのリポジトリをフォーク（Fork）して、　プルリクエスト（Pull Request）で修正を送信
  
  - http://cuaoar.jp/2013/03/github-fork-pull-request.html　

- GitHubのリポジトリ上で `Issue <https://github.com/tkam8/f5waf_autoscale_azure_guide/issues>`_ を開く

