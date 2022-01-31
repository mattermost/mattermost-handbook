# Cloud churn process

When a Mattermost Cloud customer requests their workspace to be deleted, the following steps are taken:

1. Customer sends a request to delete workspace.
2. Support team asks for:

  - Cloud URL and workspace admin email
  - Churn-related information:

      - Why are you no longer interested using Mattermost?
      - What tool/product will you use instead of Mattermost?
      - Would anything have changed your decision?

3. Support team opens a private Jira ticket with information from step 2 and tags SRE and Product Manager.
4. SRE checks if workspace had 5 or more active users in the last 7 days:

  - If yes, ask Support to introduce Product Manager to the customer via email. Produt Manager then owns trying to keep the customer working with Customer Success as appropriate, or get more detailed information on why they are discontinuing Mattermost.
  - Else, delete workspace.
