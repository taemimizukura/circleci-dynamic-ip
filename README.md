# circleci-dynamic-ip
Ansibleのdynamic-inventoryを用いてパブリックIPアドレスを動的に取得し、IPアドレスの変更にも対応できるように設定しました。
![構成図](image/img-01_ubuntu.drawio.png)
## 概要
このリポジトリでは以下の自動化プロセスをCircleCIで実行します：  
![push](https://github.com/user-attachments/assets/6246eae0-1a34-41cf-8a6a-71e88f41ca96)

1. **CloudFormationの構文チェック**  
2. **CloudFormationスタック実行**  
   - VPC、EC2、ALB、RDS、S3の作成を含むAWSインフラの構築  
   ![cfn](https://github.com/user-attachments/assets/2d9cbc8a-28dd-435f-a729-b2776dfdc4aa)
3. **Ansibleによる環境構築**  
   - EC2インスタンス上でサンプルアプリケーションのセットアップ  
   ![ansible](https://github.com/user-attachments/assets/035bc220-6058-4e76-bce7-b367a354d271)
4. **Serverspecでのテスト**  
   - EC2インスタンスの環境確認および動作テスト  
   ![serverspec](https://github.com/user-attachments/assets/08636bb1-8a9c-4d2a-9dd2-4c6abc2a5d9a)

CircleCI実行結果はこちら：  
[CircleCI Execution Result](https://app.circleci.com/pipelines/github/taemimizukura/circleci-dynamic-ip/70/workflows/80438b08-69fb-4c66-ab19-c149d055a44b)  

証跡画像はこちら：  
[evidence-image.md](evidence-image.md)
## 実行環境
Control Node：ubuntu(WSL)  
Target Node：EC2(Amazon Linux2)  

### インストールしたツール（Control Node: Ubuntu on WSL）
- Ansible 2.16.3
- AWS CLI 2.19.4
- Ruby 3.2.3
- Bundler 2.5.23
- Serverspec 2.42.3
- CircleCI CLI

Elastic IPでの固定化はこちら：  
[circleci_lecture13](https://github.com/taemimizukura/circleci_lecture13)


