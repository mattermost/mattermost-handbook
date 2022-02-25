# Mobile Feature Guidelines

New product features should consider the mobile client at the same level of importance as the web app client. For new features implemented on the server or web app, please consider the mobile client through these lenses:

## Are mobile app code changes needed?

A good rule of thumb is that if there are web app repo code changes \(outside of the System Console UI\), mobile code changes are needed to support the feature.

While not every web app feature needs parity with mobile, this is a discussion to have with the Product Managers and UX team, and a decision to be made in the requirements gathering phase of feature design.

* If a feature requires mobile code changes, the Mobile team PM \(Eric Sethna\) should be made aware of the feature before it’s committed to the feature team's quarterly roadmap. Please involve the Mobile team PM in roadmap planning and quarterly OKR planning discussions. The same applies even if the feature team will be doing the mobile implementation themselves, given that the Mobile team will be involved in code reviews, testing, and should provide guidance on the feature implementation.
* During design and spec development of any feature that will involve mobile code changes, please involve the Mobile PM \(Eric Sethna\) and Mobile dev lead \(Elias Nahum\) at all stakeholder checkpoints including requirements gathering, design option exploration, and final design review.
* Set deliverables taking into account the limitation that a team may not have enough skills to develop features for mobile. Consider the impact if the feature is left out from mobile, document the reasons, and set goals to cover the mobile space. The feature should be [released as beta or experimental](https://handbook.mattermost.com/operations/research-and-development/product/product-management-team-handbook#can-we-take-this-feature-out-of-beta) and any documentation should clearly communicate the impact of not having mobile support as well as when mobile support is expected.
* If a feature is related to authentication, such as Single Sign-On \(SSO\), plan to release the feature on Mobile Apps prior to Cloud to avoid users from being blocked from using the Mobile Apps.

## Backward compatibility

* Mobile releases must be backward compatible with at least all server versions back to the [oldest supported ESR](https://docs.mattermost.com/upgrade/extended-support-release.html). An important question to ask during design is: _What is the expected behavior on a new server with an old app, or a new app with an old server?_

Here's an example:

* **New mobile app with an old server:** If the server is running older code and does not support the new feature, we can’t allow users to access the feature from a new mobile app.
  * Example: Hide the “Mark as Unread” option if the server is older than v5.18.
    * [Use the isMinimumServerVersion helper function](https://github.com/mattermost/mattermost-mobile/blob/master/app/screens/post_options/index.js#L49)
* **New server with an old mobile app:** Users will not be able access the new features from their mobile device since it’s running older code, but the new server code should not cause regressions to a user's experience on an older mobile app.
  * Example: Users cannot see the “Mark as Unread” option in an older mobile app that does not contain that code, but marking a channel unread on a webapp running v5.20 or later should still mark the channel as unread on mobile, and not cause any mobile app regressions for a user running an old app.

Ideally any new features should be tested on all server versions back to the [oldest supported ESR](https://docs.mattermost.com/administration/extended-support-release.html?highlight=esr). However, since testing mana is limited, feel free to work with your QA representative to determine the most effective testing approach based on the risks of your feature. At a minimum, new mobile app features should be tested on all supported server ESRs and the latest three server versions.

For new features, consider a `minserverversion` check that only executes the code if the server connected to the app is newer than xyz. [See example to disable or not the position field when editing the profile](https://github.com/mattermost/mattermost-mobile/blob/ee4b85edcfee8316db08c31ec5b2a26afb343bd3/app/screens/edit_profile/index.js#L29).

Bonus: Legacy servers \(i.e. &lt; v5.0\) don't have post metadata, don't rely on it.

## Variable network conditions

* API requests will fail on mobile because network conditions are much more variable than on desktop. As such defaults need to be carefully chosen to avoid failing requests breaking or blocking core user functionality. As an example, if the default for a channel is set to be read-only until a permission API request grants the user permissions, this is likely to result in a poor user experience in bad networks.

When in doubt, [the default if an API request fails should not change existing behavior, or a failed API request should either do nothing or notify the user somehow](https://github.com/mattermost/mattermost-mobile/blob/master/app/mm-redux/actions/preferences.ts#L18).

* [Retries should be added to important API requests](https://github.com/mattermost/mattermost-mobile/blob/master/app/actions/views/channel.js#L607).

## Client performance impact

* Mobile devices vary significantly in their computing capabilities, as such performance should be top of mind when developing mobile features.
* Minimize requests where possible, make requests in parallel if possible, batch dispatches wherever possible.

  [https://github.com/mattermost/mattermost-mobile/blob/master/app/actions/views/user.js\#L79](https://github.com/mattermost/mattermost-mobile/blob/master/app/actions/views/user.js#L79)

* Do NOT track requests. Examples:
  * Here we are fetching the needed data in sequence but holding dispatching any action, and then once we have all the required data we dispatch an action batch. With this we ensure that the redux store is being updated only once and that every `mapStateToProps` of mounted connected components runs once instead of multiple times, this will then reduce computation time: [https://github.com/mattermost/mattermost-mobile/blob/master/app/actions/views/user.js\#L51](https://github.com/mattermost/mattermost-mobile/blob/master/app/actions/views/user.js#L51).
  * Here we are fetching data from the server in sequential order and then in parallel, as we need data from one request and then all others are not dependent on each other. The use of `Promise.all` will help wait on all responses but take into consideration if one of them fails, everything will fail \(do add retries if needed\). In the end we batch the actions as we do in the example above: [https://github.com/mattermost/mattermost-mobile/blob/master/app/actions/views/user.js\#L79](https://github.com/mattermost/mattermost-mobile/blob/master/app/actions/views/user.js#L79).
  * Don’t do this: Here we are using a bind function or an action created that is dispatching at least two actions in total, one for tracking the start of the request and then if the requests succeeded or failed. That means that calling that function will update the store twice instead of once:
    * [https://github.com/mattermost/mattermost-mobile/blob/master/app/mm-redux/actions/teams.ts\#L67](https://github.com/mattermost/mattermost-mobile/blob/master/app/mm-redux/actions/teams.ts#L67)
    * [https://github.com/mattermost/mattermost-mobile/blob/master/app/mm-redux/actions/teams.ts\#L103](https://github.com/mattermost/mattermost-mobile/blob/master/app/mm-redux/actions/teams.ts#L103)

