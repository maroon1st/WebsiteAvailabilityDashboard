# WebsiteAvailabilityDashboard

Dashboard for website availability by Amazon CloudFormation

## Dependency

CLIを使用する場合はaws-cliが必要

[aws/aws-cli](https://github.com/aws/aws-cli)

## Usage

### AWS CLIを使用する場合

Virginiaリージョンで以下を実行します。

``` bash
$ aws cloudformation create-stack --region us-east-1 --stack-name <Stack Name> \
    --template-body file://WebsiteAvailabilityDashboard.template \
    --parameters ParameterKey=SiteName,ParameterValue=<Site Name> ParameterKey=Type,ParameterValue=<HTTP or HTTPS> ParameterKey=ResourcePath,ParameterValue=<Check Target Path> ParameterKey=CheckSourceRegions,ParameterValue=<AsiaOnly or WorldWide> ParameterKey=Port,ParameterValue=<Port Number> ParameterKey=TargetDomain,ParameterValue=<Check Target Domain>
```

### AWSコンソールを使用する場合

VirginiaリージョンのAWS CloudFormationのコンソールを開きます。

[CloudFormation Management Console](https://console.aws.amazon.com/cloudformation/home?region=us-east-1)

以下の手順に従いスタックを作成します。

[Creating a Stack on the AWS CloudFormation Console](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-console-create-stack.html)

スタックパラメータは、以下の内容となります。

|No.|パラメータ名|内容|
|---|---|---|---|
|1|CheckSourceRegions|アクセス元地域 AsiaOnly or WorldWide|
|2|Port|使用するポート番号|
|3|ResourcePath|チェック対象のパス 例:/index.html|
|4|SiteName|チェック対象の名称|
|5|TargetDomain|チェック対象のパス 例:example.com|
|6|Type|使用するプロトコル HTTP or HTTPS|

## License

This software is released under the MIT License, see LICENSE.

## Authors

maroon1st
