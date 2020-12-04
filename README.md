# Slack Notification

Github [composite action](https://docs.github.com/en/free-pro-team@latest/actions/creating-actions/creating-a-composite-run-steps-action) that sends a build notification to a Slack channel.

Compared to other available slack notification actions uses bash shell calls instead of docker or Node.js implementations, which results in much faster execution time.

The only thing that needs to tbe configured is a Slack webbook. The following data will be grabbed from job execution context and added to the message:

 - User who made last commit/merge
 - Last commit message
 - Org/Repository name
 - Ref/branch name
 - Job run number (aka build number)
 - Job execution status (also used to set Slack's message bar color)

### Instructions 

Add the action call to your build script YAML and provide your Slack [webhook](https://api.slack.com/messaging/webhooks) URL:

```
- name: Slack notification  
  uses: PressCentric/Actions-Slack-Notify@master
  with:
    webhook-url: ${{ secrets.SLACK_WEBHOOK_URL }}
```
