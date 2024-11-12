# circleci-dynamic-ip
Control Node：ローカルPCのubuntu  
Target Node：EC2（Amazon Linux2）  

Elastic IPでIPを固定せず、パブリックIPアドレスを動的に割り当て、cfnでIPを取得し、ansibleに渡して実行する方法にしました。  

以下の工程をCircleCIで自動化しました。  
① CloudFormationの構文チェック  
② CloudFormationスタック実行（EC2、ALB、RDS、S3追加）  
③ ターゲットノードのEC2インスタンスにサンプルアプリケーションの動作環境構築  
④ ターゲットノードの環境をテストする  

※Elastic IPでIPを固定化した実行方法  
[circleci_lecture13](https://github.com/taemimizukura/circleci_lecture13)
