# aws-multi-account-iam-design-with-jump-account
AWSマルチアカウントにおけるJumpアカウントを用いたIMA設計のCloudFormationテンプレートです。

## 概要
AWSでマルチアカウント構成にした際に、Jumpアカウント方式で各AWSアカウントにログインする手法があります。  
利用者は、まずJumpアカウントにログインし、各AWSアカウントへスイッチロールすることでログインすることができます。  
各AWSアカウントでどのような操作を許可するかは、スイッチ先のロールに対して必要な権限を付与します。  
アーキテクチャは以下に示す通りで、ハイライトされた部分がハンズオンのスコープです。

![](./images/jump-account-architecture.png)

## 各種ファイル

| ファイル名 | 説明 |
| ------------- | ------------- |
| IAM-Jump.yaml | Jumpアカウントに展開するCloudFormationテンプレート |
| IAM-SwitchRole-Dev.yaml | Devアカウントに展開するCloudFormationテンプレート |
| IAM-SwitchRole-Stg.yaml | Stgアカウントに展開するCloudFormationテンプレート |
| IAM-SwitchRole-Prod.yaml | Prodアカウントに展開するCloudFormationテンプレート |

## 使い方

[こちらのブログ](https://yuj1osm.hatenablog.com/entry/2025/01/12/162426)を参考にしてください。