# circleci-dynamic-ip
Control Node：ubuntu(WSL)  
Target Node：EC2(Amazon Linux2)  

dynamic-inventoryを用いてパブリックIPアドレスを動的に取得し、IPアドレスの変更にも対応できるように設定しました。

以下の工程をCircleCIで自動化しています：  
① CloudFormationの構文チェック  
② CloudFormationスタック実行（EC2、ALB、RDS、S3作成）  
③ AnsibleでEC2インスタンスにサンプルアプリケーションの環境構築  
④ Serverspecで環境のテスト  

Elastic IPでの固定化はこちら:  
[circleci_lecture13](https://github.com/taemimizukura/circleci_lecture13)
