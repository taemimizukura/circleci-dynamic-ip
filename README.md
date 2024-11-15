# circleci-dynamic-ip
dynamic-inventoryを用いてパブリックIPアドレスを動的に取得し、IPアドレスの変更にも対応できるように設定しました。

## 概要
このリポジトリでは以下の自動化プロセスをCircleCIで実行します：
1. **CloudFormationの構文チェック**
2. **CloudFormationスタック実行**  
   - VPC、EC2、ALB、RDS、S3の作成を含むAWSインフラの構築
3. **Ansibleによる環境構築**
   - EC2インスタンス上でサンプルアプリケーションのセットアップ
4. **Serverspecでのテスト**  
   - EC2インスタンスの環境確認および動作テスト  

CircleCI実行結果はこちら：  
[CircleCI Execution Result]()

## 実行環境
Control Node：ubuntu(WSL)  
Target Node：EC2(Amazon Linux2)  

### 必要なソフトウェア
- CircleCI CLI
- AWS CLI
- Ansible
- Serverspec

Elastic IPでの固定化はこちら：  
[circleci_lecture13](https://github.com/taemimizukura/circleci_lecture13)


