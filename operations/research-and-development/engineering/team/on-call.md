# On-Call

## Onboarding

### Find out when you’re on-call

To find out when you’re on call follow the below checklist:

1. Add the SET calendar to your Google Calendar
   1. Log in to OpsGenie via Okta.
   2. Open each of the following schedules that are relevant to you:
      * [Sustained Engineering\_schedule](https://mattermost.app.opsgenie.com/settings/schedule/detail/cc2b2e08-b690-434b-a8a0-b4943f8eb3d2)
      * [Backup Sustained Engineering\_Schedule](https://mattermost.app.opsgenie.com/settings/schedule/detail/967e7812-e594-4d0f-8f26-8b2e98f43906)
      * [Lead Sustained Engineering\_schedule](https://mattermost.app.opsgenie.com/settings/schedule/detail/a121cd12-2961-47bb-8fb0-7d7252a18fb6)
   3. For each click the litte "Open Calendar" calendar button that appears when you hover over the calendar. This will open a `webcal://` link, copy this link
   4. In Google calendar \(or your prefered calendaring app\) Go to “Add Calendar”, select “From URL” and paste the `webcal` URL. After it's added, rename it to something appropriate.
2. Find yourself on the calendar
   1. At the top right of Google Calendar click the search icon.
   2. Type in the below based on your rotation for SET: “\ Engineering\_schedule”.
   3. The results should show you the dates you’re on call.

### What if I'm unavailable?

If you've been scheduled for SET duty but aren't available, e.g. because of PTO:

1. Try to find a replacement yourself, e.g. by asking team mates or by asking in [~Sustained Engineering](https://community-daily.mattermost.com/core/channels/sustained-engineering) for volunteers.
2. If you fail to find anybody, reach out to @zef.hemel he'll try to help you.
3. Once you find a replacement, you can override the specific shift in OpsGenie. If you're having trouble, reach out to @zef.hemel to help you.

### Before your first day on-call

There’s a few things you should set up before your first day on call. Work through the following checklist a couple days before you start on-call:

1. Log in to OpsGenie
   1. Go to [https://mattermost.okta.com/app/UserHome](https://mattermost.okta.com/app/UserHome) and log in.
   2. Search for and select the OpsGenie icon.
2. Install the OpsGenie app on your phone
   1. Search “OpsGenie” in the Apple App Store or Google Play Store.
   2. Open the app and type in your email, **making sure to select US as the data center region**.
   3. For organization, enter “mattermost”.
   4. This should redirect you to Okta to complete the log in.
3. Configure your OpsGenie notification rules in your desktop browser
   1. Go to [https://mattermost.app.opsgenie.com/settings/user/notification](https://mattermost.app.opsgenie.com/settings/user/notification).
   2. Under **Contact methods** add your phone number for SMS and/or voice.
   3. Under **Notification rules** you should configure the rules for:
      1. New Alert
      2. Schedule Start
      3. Schedule End
   4. How you want to configure your notifications is up to you but **make sure it’s configured in a way that will get your attention**.
      1. An example configuration is:
         1. Notify mobile immediately
         2. Notify via SMS after 5 minutes
         3. Notify via phone call after 10 minutes
   5. Test your notification rules by creating a test alert
      1. Go to [https://mattermost.app.opsgenie.com/alert/list](https://mattermost.app.opsgenie.com/alert/list).
      2. Select **Create alert** in the top right.
      3. Name the alert **Test Alert**.
      4. Add yourself under **Responders**.
      5. Select **Create**.
      6. Confirm that your notification rules are followed.
      7. Acknowledge the alert.
      8. Close the alert.
4. Join [~Incidents Status](https://community.mattermost.com/private-core/channels/incidents) channels on community.mattermost.com.
5. Read [Incident Response](https://docs.google.com/document/d/1-AWQJQelgKvGVSP6sOIi9EOSVjxXVlJlwNuJlkcXKGA/edit#heading=h.uk4q4qkm81h0) to familiarize yourself with the response process.
6. Create a test incident to familiarize yourself with playbooks
   1. On community.mattermost.com, select the clipboard icon in the channel header.
   2. Click the “+” to start a new incident.
   3. Choose playbook:
      1. For SET, use “Sustained Engineering”
      2. For Cloud, use “Cloud Incident Response Playbook”
   4. End the incident.

### Your first day on-call

On your first day on call, do the following:

1. Check if you’re on-call as primary or back up
   1. Log in to OpsGenie.
   2. Go to [https://mattermost.app.opsgenie.com/schedule/whoIsOnCall](https://mattermost.app.opsgenie.com/schedule/whoIsOnCall) and click on the schedule for the rotation you’re on.
   3. You’re on-call as primary if you’re listed under one of the rotations that has “Primary” in the name.
2. Start your shift
   1. OpsGenie will notify you when your shift starts or [check the schedule](https://mattermost.app.opsgenie.com/schedule/whoIsOnCall).
3. Watch for alerts from OpsGenie and follow [Incident Response](https://docs.google.com/document/d/1-AWQJQelgKvGVSP6sOIi9EOSVjxXVlJlwNuJlkcXKGA/edit#heading=h.uk4q4qkm81h0) to respond to any alerts.
4. End your shift
   1. OpsGenie will notify you when your shift ends or [check the schedule](https://mattermost.app.opsgenie.com/schedule/whoIsOnCall).
