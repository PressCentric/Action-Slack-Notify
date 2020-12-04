# Slack Notification

[Composite run steps action](https://docs.github.com/en/free-pro-team@latest/actions/creating-actions/creating-a-composite-run-steps-action) for sending build notification into a Slack channel.

Compared to other available slack notification actions uses bash shell calls instead of docket or Node.js implementations, which results in much faster execution time.

### Instructions 

Create an org-level secret `SLACK_WEBHOOK_BUILDS` with Slack [webhook](https://api.slack.com/messaging/webhooks) URL.

Add the action call to your build script YAML:`

```
- name: Slack Notification  
  uses: PressCentric/Actions-Slack-Notify@v1
```
