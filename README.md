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

デプロイ

```
sam deploy --parameter-overrides SlackWebhookUrl=${SLACK_WEBHOOK_URL} --config-env billing-python
```

# 参考資料

https://dev.classmethod.jp/articles/notify-slack-aws-billing/
