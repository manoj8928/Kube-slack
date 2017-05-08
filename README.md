# Kube-slack

Create a new bot user integration on Slack and get the token
Create secret using below command and refer it in your deployment yaml file.

kubectl create secret generic kubebot --from-literal=token=<your_token_here> --from-literal=channel=<your_channel_id_here>

set kubebot_slack_token with the token you got
set kubebot_slack_admins_nicknames with the nicknames (without @) of the users that you want to be able to interact with Kubebot (use a space as separator)
set kubebot_slack_channels_ids with the IDs of the channels you want kubebot to interact (use a space as separator). You can get the ids of your team's channels in https://slack.com/api/channels.list?token={REPLACE WITH YOUR TOKEN}.
[optional] You can edit kubebot_slack_valid_commands to change which commands Kubebot is able to run.

Now run your deployment file and try few commands

Note: you need to pass "!" sign before every command in slack channel.
e.g !kubectl get deployment --all-namespaces ,!kubectl get pods --all-namespaces
