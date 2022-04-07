# Localization

The goal of the localization process is to consistently produce high quality translations release after release through collaboration between the international community, translators, project managers, language leads, and the core team.

## Translation process

If you're interested in contributing translations to Mattermost, please join the [Mattermost localization channel to discuss](https://community.mattermost.com/core/channels/localization). Below are descriptions of the overall localization process.

## Initial translation

To translate a language:

1. Join the [Mattermost Translation Server](http://translate.mattermost.com).
2. Check whether the language you want to help translate is listed in the [Translation Server](https://translate.mattermost.com/projects/).

   * If it is, perhaps offer to help translate or review and make suggestions.
   * If not, ask to setup your language on the [Mattermost localization channel](https://community.mattermost.com/core/channels/localization), so you can start helping with the translation.

   **Note:** Languages are grouped either as "shipped" or "work in progress". A language [ships in Mattermost](https://docs.mattermost.com/help/settings/account-settings.html#language) if it meets specified translation quality.

3. Review translation rules written by localization leads, when applicable:
   * [German \(Regeln zur Übersetzung von Mattermost\)](https://gist.github.com/der-test/6e04bff8a173e053811cb93e08838ca2).
   * [French \(Règles pour la traduction francophone de Mattermost\)](https://github.com/wget/mattermost-localization-french-translation-rules).
   * [Dutch translation rules for Mattermost](https://github.com/ctlaltdieliet/mattermost-localization-dutch-translation-rules).

## Translation updates

1. New and updated source strings are automatically added to the translation server each time a GitHub pull request containing string changes is merged.
2. A new pull request with latest translations that reach at least Beta quality is submitted to the [mattermost-mobile](https://github.com/mattermost/mattermost-mobile), [mattermost-server](https://github.com/mattermost/mattermost-server), and [mattermost-webapp](https://github.com/mattermost/mattermost-webapp) repos each Monday at 22:00 GMT.
   * A pull request will also be submitted on the day of major feature complete and code complete to ensure latest translations are included in the release.
   * A pull request may also be submitted for a release candidate.

**Important:** Please do **not** submit translations directly via a pull request as they may be lost with the next pull request update from the Mattermost Translation Server.

## Translation quality

In order for users to understand the accuracy and coverage of language translations, quality levels are explicitly defined for each language:

### Official

* 100% of translation verified by someone deeply knowledgeable in Mattermost functionality.
* 100% of translation verified by someone deeply knowledgeable in target language.
* No translation may be out-of-date due to changes to English-language text since the last translation and review cycle.
* Language must have at least one official reviewer who maintains the language with updated strings imported to the [Translation Server](http://translate.mattermost.com) over time.
* Language must have been in use for **at least three full release cycles** where end users in target language can share feedback and corrections.

Official languages are listed in **Account Settings &gt; Display &gt; Language**.

### Beta

* At least 90% of string translation verified by someone deeply knowledgeable in Mattermost functionality and in the target language. Languages at risk for ongoing maintenance can require a higher translation threshold closer to 100%.
* Up to 10% of translation may be out-of-date due to changes to English-language text since the last translation and review cycle.

Beta languages are listed in **Account Settings &gt; Display &gt; Language** appended with **\(Beta\)**.

### Alpha

* Translation has not yet reached Beta quality.

An official language may be changed back to Beta or Alpha if the specified requirements are not met for a release. Similarly, Beta languages may be dropped back to Alpha.

## Message syntax

To format localized messages, [mattermost-webapp](https://github.com/mattermost/mattermost-webapp) uses the [react-intl](https://formatjs.io/docs/react-intl), a Javascript library from [FormatJS](https://formatjs.io). This library uses the [ICU Message syntax](http://userguide.icu-project.org/formatparse/messages), which is the standard syntax for many programming languages.

If you don't know about the ICU syntax, please familiarize yourself by reading the [ICU Message Syntax simplified documentation](https://formatjs.io/docs/core-concepts/icu-syntax/) and [Formatting Messages](https://unicode-org.github.io/icu/userguide/format_parse/messages/). What's most important here is to read the sections dedicated to how plural terms are managed.

In order to ease the manipulation of strings like these with a special syntax \(ICU as a reminder\), a developer has created an online tool allowing to test an ICU string. This tool, called [Online ICU Message Editor](https://format-message.github.io/icu-message-format-for-translators/editor.html), is displayed as a live editor previewing how a string will appear in context. This tool has been reported by some members of our community as really helpful to translate strings containing an ICU syntax. Don't hesitate to use it.

## Knowledge base

Some terms used in Mattermost may be technical. If you don't know how to translate a specific term:

* If applicable, check how the term has been translated in other locations of the translation you are contributing to.
* Use a translation engine to know how others have translated the term.
* Use the [Microsoft open linguistic portal](https://www.microsoft.com/en-us/language/Search).
* Ask your question on the [Mattermost localization channel](https://community.mattermost.com/core/channels/localization).

## Test translations

If you'd like to review and verify translations prior to achieving Beta quality status, you can follow these steps:

1. Build Mattermost on your machine following the [Developer Machine Setup Guides](https://docs.mattermost.com/developer/dev-setup.html).
2. Download a copy of your translations to your local machine by going to the language of your choice, e.g. [German](https://translate.mattermost.com/projects/mattermost/mattermost-server_master/de/), then **Files &gt; Download original translation file \(go-i18n JSON file\)**.
3. Copy the generated `[locale].json` files to the corresponding directories:
   * For the server, copy the files to the i18n directory of the `mattermost-server` project.
   * For the webapp, copy the files to the i18n directory of the `mattermost-webapp` project.
4. Modify the file `i18n/i18n.jsx` in the `mattermost-webapp` project to include your translated strings.
5. Compile and run **Mattermost** to confirm everything works. You can then review and verify translations from your machine.

If you find a string that has not been translated, search for the string in the respective localization file to confirm it's included for translations. You can find the English version for server, webapp, and mobile projects below:

* [https://github.com/mattermost/mattermost-server/blob/master/i18n/en.json](https://github.com/mattermost/mattermost-server/blob/master/i18n/en.json)
* [https://github.com/mattermost/mattermost-webapp/blob/master/i18n/en.json](https://github.com/mattermost/mattermost-webapp/blob/master/i18n/en.json)
* [https://github.com/mattermost/mattermost-mobile/blob/master/assets/base/i18n/en.json](https://github.com/mattermost/mattermost-mobile/blob/master/assets/base/i18n/en.json)

If it’s included in the file, then most likely it hasn't been translated yet, but is in [https://translate.mattermost.com](https://translate.mattermost.com). If you want to confirm whether it's translated, you can check for the respective `.json file` in the `/i18n` folder.

## Translation maintenance

Translations require updates on a monthly basis as features are added and changed.

While the formal process for updates has yet to be determined, currently the Release Manager notifies one of the official translation reviewers who then forwards the message to the community of translators. This reminder tends to induce a virtuous cycle of motivation into the community of translators.

Below are current official reviewers and maintainers for languages that have reached at least Beta-quality. Official reviewers submit final translations for languages; maintainers suggest translations and step in when official reviewers aren't able to help in a certain release.

If you're interested in contributing to the process, please join the [Mattermost localization channel to discuss](https://community.mattermost.com/core/channels/localization). Creating localization channels is also encouraged - see examples of current channels including [Italian](https://community.mattermost.com/core/channels/i18n-italian), [German](https://community.mattermost.com/core/channels/i18n-german), and [Swedish](https://community.mattermost.com/core/channels/i18n-swedish).

| Language | Official Reviewer\(s\) | Maintainers |
| :--- | :--- | :--- |
| Bulgarian | [Nikolai Zahariev \(nikolaiz\)](https://translate.mattermost.com/user/nikolaiz/) | |
| Deutsch - German | [JtheBAB \(jthebab\)](https://translate.mattermost.com/user/JtheBAB/) | [Jan-Peter Rusch \(jprusch\)](https://translate.mattermost.com/user/jprusch/) |
| English - Australian | [Matthew Williams \(matthew.williams\)](https://translate.mattermost.com/user/matthew-w/) |  |
| Español - Spanish | [Elias Nahum \(enahum\)](https://github.com/enahum) | [Jesús Espino \(jespino\)](https://github.com/jespino) |
| Français - French | [William Gathoye \(wget\)](https://github.com/wget) |  [Nathanaël Houn \(nathanaelhoun\)](https://translate.mattermost.com/user/nathanaelhoun/) |
| Magyar - Hungarian | [Zsolt Godó \(sakaitsu\)](https://translate.mattermost.com/user/sakaitsu) | [Csaba Tóth \(tsabi\)](https://translate.mattermost.com/user/tsabi) |
| Italiano - Italian | [Michael Longo \(mlongo4290\)](https://github.com/mlongo4290) | [Ema Panz \(thepanz\)](https://github.com/thepanz) |
| 日本語 - Japanese | [Yusuke Nemoto \(kaakaa\)](https://github.com/kaakaa) |  |
| 한국어 - Korean | TBD \(Open Role\) |  |
| Nederlands - Dutch | [Tom De Moor \(ctlaltdieliet\)](https://github.com/ctlaltdieliet) |  |
| Polski - Poland | [Daniel Burzmiński \(hectorskypl\)](https://github.com/hectorskypl) | [Tomasz Gruca \(gruceqq\)](https://translate.mattermost.com/user/gruceqq) |
| Português do Brasil - Portuguese | [Rodrigo Corsi \(rodcorsi\)](https://github.com/rodcorsi) | [Carlos Tadeu Panato Junior \(cpanato\)](https://github.com/cpanato) |
| Română - Romanian | TBD \(Open Role\) |  |
| Svenska - Swedish | [Martin Johnson \(johnsonbrothers\)](https://github.com/johnsonbrothers) |  |
| Türkçe - Turkish | [Kaya Zeren \(kaya\_zeren\)](https://twitter.com/kaya_zeren) |  |
| Pусский - Russian | [Alexey Napalkov \(flynbit\)](https://github.com/flynbit) |  |
| Yкраїнська - Ukrainian | TBD \(Open Role\) |  |
| 中文 \(简体\) - Simplified Chinese | [aeomin \(aeomin\)](http://translate.mattermost.com/user/aeomin) |  |
| 中文 \(繁體\) - Traditional Chinese | [Tze-Kei Lee \(chikei\)](https://github.com/chikei) |  |

## Administrative tasks

To grant trusted translators additional permissions as Weblate admin, add the user to the `mattermost@TrustedReviewers` group in Weblate:

1. Select **Admin interface** \(tool icon in Weblate header\).
2. Go to **Users &gt; Django Admin Interface**.
3. Select the user you want to grant permissions to.
4. Go to **Groups**.
5. Add the user to the `mattermost@TrustedReviewers` group.
6. Select **Save**.

To add a new language:

1. Go to [https://translate.mattermost.com/projects/i18n-wip](https://translate.mattermost.com/projects/i18n-wip).
2. Select any of the components on the resulting page, then select **Tools &gt; Start new translation**. 
3. Select the languages you want to add, then **Start new translation**.
4. Repeat step 2 for every component in [https://translate.mattermost.com/projects/i18n-wip](https://translate.mattermost.com/projects/i18n-wip).

## Translation PRs review process

The translation PRs get automatically opened once a week on Mondays. They also get posted to the [i18n PRs channel](https://community.mattermost.com/core/channels/i18n-prs).

PR reviews need to focus on ensuring that unexpected characters aren't injected into strings. If security concerns are found, notify the Security team.

The translation PRs should be reviewed and merged as soon as possible to avoid alerts from Weblate. Note that it is critical that teams merge these PRs using "merge commit" (or technically also "rebase and merge"), but /never/ "squash and commit". The latter breaks the weblate flow, locking the translations, and forcing a manual fix.

Amy Blais will notify the team if the PR should be cherry-picked to a release branch (e.g. ``cloud``).

PR review owners:
  - Server translations PRs - Channels/Suite Users teams (Owners: Guillermo and Zef)
  - Webapp translations PRs - Channels/Suite Users teams (Owners: Guillermo and Zef)
  - Mobile translations PRs - Channels/Suite Users teams (Owners:  Guillermo and Zef)
  - Boards translations PRs - Boards team (Owners: Scott and Jesus)
  - Playbooks translations PRs - Playbooks team (Owners: Jesse and Caleb)
