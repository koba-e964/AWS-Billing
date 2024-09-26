# AWS-Billing

事前作業

```
SLACK_WEBHOOK_URL=(Webhook's URL)
sam build
```

ローカルで動かす

```
sam local invoke --parameter-overrides SlackWebhookUrl=${SLACK_WEBHOOK_URL}
```

SLACK_WEBHOOK_URL を設定していれば Slack に情報がポストされるのでそれを確認する。
それが確認できない場合は、標準出力に JSON が吐かれるので、コピーして以下で情報を取る。

```
pbpaste | jq -r .body | jq -r .detail
```

デプロイ

```
sam deploy --parameter-overrides SlackWebhookUrl=${SLACK_WEBHOOK_URL} --config-env billing-python
```

# 参考資料

https://dev.classmethod.jp/articles/notify-slack-aws-billing/
