# circleci-dynamic-ip
コントロールノードをローカルPCのubuntu(WSL)とし、ターゲットノードをEC2としました。 
固定のEIPではなくパブリックIPアドレスの自動割り当てにして、cfnでIPを動的に取得し、ansibleに渡して実行する方法にしました。  
以下の工程をCircleCIで自動化しました。  
① CloudFormationの構文チェック  
② CloudFormationスタック実行（EC2、ALB、RDS、S3追加）  
③ ターゲットノードのEC2インスタンスにサンプルアプリケーションの動作環境構築  
④ ターゲットノードの環境をテストする  
