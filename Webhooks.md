Fyipe can be configured to send notifications related to incidents into Slack and Microsoft Teams channels.
# Slack
## Create incoming hooks
The first step is to configure an incoming webhook in the channels that you want to be used by Fyipe. If you didn't do it that before, you can follow the first three steps in this [tutorial](https://api.slack.com/messaging/webhooks#getting_started). Save the Webhook url from the third step as you'll need it to configure fyipe.
## Configure Fyipe
Once the incoming hooks is configure, go to the dashboard and select the monitor that you want to target from the component.
![](./screenshots/screenshot_slack.png)

Scroll down to the Slack integration section and click on add webhook.
![](./screenshots/screenshot_slack_1.png)

Paste the webhook url, and check the events that you want to be notified about. 

![](./screenshots/screenshot_slack_2.png)

Now, you should receive notifications on your channel.

![](./screenshots/screenshot_slack_3.png)

# Microsoft Teams
The same steps are required to integrate Microsoft teams. 
## Create incoming hooks

This [tutorial](https://docs.microsoft.com/en-us/microsoftteams/platform/webhooks-and-connectors/how-to/add-incoming-webhook#add-an-incoming-webhook-to-a-teams-channel) explain how to create an incoming hook.

## Configure Fyipe
As with Slack integration, go to the dashboard, select a monitor, and scroll down to the MS Teams integration.

![](./screenshots/screenshot_msteams.png)

Paste the webhook url, and check the events that you want to be notified about. 

![](./screenshots/screenshot_msteams_1.png)

Now, you should receive notifications on your channel.

![](./screenshots/screenshot_msteams_2.png)
