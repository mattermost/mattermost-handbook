# Localization

The goal of the localization process is to consistently produce high quality translations release after release through collaboration between the international community, translators, project managers, language leads, and the core team.

## Interested in contributing to product translations?

If you're interested in contributing translations to Mattermost, learn more about getting started with Mattermost translations by visiting the [translation contribution](https://developers.mattermost.com/contribute/why-contribute/#you-want-to-help-with-product-translation) documentation. 

### Join us on the Mattermost Community server

We strongly encourage all translators to join us in the [Mattermost localization channel](https://community.mattermost.com/core/channels/localization) on the Mattermost Community server. 

In the localization channel, you can:
- Discuss translation questions, concerns, and best practices with both Mattermost staff and the Mattermost translation community.
- Learn more about string context, including audience and product area.
- Review important translation timelines, deadlines, announcements, and notifications.
- Escalate any challenges you're experiencing as a product translator.

**Tip:** We also encourage language experts to create language-specific localization channels on the Mattermost Community Server. See examples of current channels including [Italian](https://community.mattermost.com/core/channels/i18n-italian), [German](https://community.mattermost.com/core/channels/i18n-german), and [Swedish](https://community.mattermost.com/core/channels/i18n-swedish).

### Active translation projects

You can contribute to the following active translation projects:

| **Translation project** | **Translation server URL** |
| :--- | :--- |
| Channels | https://translate.mattermost.com/projects/mattermost/ |
| Focalboard | https://translate.mattermost.com/projects/focalboard/ |
| Playbooks | https://translate.mattermost.com/projects/playbooks/ |
| Desktop app | https://translate.mattermost.com/projects/mattermost/mattermost-desktop/ |
| Mobile app v2 | https://translate.mattermost.com/projects/mattermost/mattermost-mobile-v2/ |
| Mattermost WIP languages | https://translate.mattermost.com/projects/i18n-wip/ |

The general localization process is described in the following sections on this page. 

## Translate English product strings into additional languages

Mattermost is developed in US English, and officially supports 20 additional languages. Getting started is easy.

### Join the [Mattermost translation server](http://translate.mattermost.com)

**Important note:** While it's common to contribute to Mattermost in GitHub, product translations is a notable exception. You must contribute to Mattermost translations on the Mattermost translation server. Please don't attempt to submit translations in GitHub via pull requests (PRs) as your translations will be overwritten with the next PR update.

### Confirm whether the language you want to translate is one we [officially support](https://translate.mattermost.com/projects/mattermost/#languages) or is a [work-in-progress (WIP) language](https://translate.mattermost.com/projects/i18n-wip/#languages)

Only supported languages are available in-product by selecting **Settings > Display > Language**. Any language that isn't officially supported is considered a work-in-progress language. Work-in-progress languages become officially supported languages when the following two conditions are met:
* The (WIP) language reaches or exceeds the Beta translation quality threshold across three consecutive releases; and,
* A language expert is available for at least six months of maintenance updates.

See the section on [translation quality](https://handbook.mattermost.com/contributors/join-us/localization#translation-quality) for further details.

**Tip:** We encourage translators to add additional languages to the WIP language list. Before adding a new language, always check to ensure that the language you're interested in isn't already defined as an officially supported langauge or a WIP language on the translation server.

### Review translation rules written by localization leads, when applicable

Translation rules and glossaries are available for the following languages:

   * [German \(Regeln zur Übersetzung von Mattermost\)](https://gist.github.com/der-test/6e04bff8a173e053811cb93e08838ca2).
   * [French \(Règles pour la traduction francophone de Mattermost\)](https://github.com/wget/mattermost-localization-french-translation-rules).
   * [Dutch translation rules for Mattermost](https://github.com/ctlaltdieliet/mattermost-localization-dutch-translation-rules).

**Tip:** We welcome rules, glossaries, and guidelines for all supported languages. If these translation assets don't exist for the language you're interested in, perhaps you'd be open to help create them?

## Omit error strings from localization process

When an error string isn’t visible to end users, engineering teams must use ``model.NoTranslation`` as the error id to implement a ``model.AppError`` without a translation. See examples of this approach in the [mattermost/mattermost-server](https://github.com/mattermost/mattermost-server) repository on GitHub.

Error strings that use ``model.NoTranslation`` as the error id are omitted from Mattermost translation workflows, and aren't surfaced up in Weblate to translators.

## Product localization process

The following flow diagram outlines the product localization flow from the translation server to the Mattermost codebase:

![Mattermost product localization flow diagram](../../../.gitbook/assets/i18n-flow.png)

1. New and updated US English source strings are automatically added to the translation server each time a GitHub PR containing string changes is merged by Mattermost Engineering.
2. The translation server pulls the latest string changes as they are committed to the codebase.
3. Translators are notified when strings are new or changed.
4. Translators add and update string translations.
5. Each Monday, at 22:00 GMT, a job opens PRs in GitHub to the main branches of the [mattermost-server](https://github.com/mattermost/mattermost-server), [mattermost-webapp](https://github.com/mattermost/mattermost-webapp), [mattermost-mobile-v2](https://github.com/mattermost/mattermost-mobile/tree/gekidou), and [mattermost-desktop](https://github.com/mattermost/mattermost-desktop) repositories. Weekly PRs contain several commits, one per modified language. Changes are merged back into each branch after a security/consistency review. 

PRs will also be submitted on the day of major feature complete, code complete, and release candidates to ensure latest translations are included in the release.

## Translation PR review process

Translation PRs are created automatically on Mondays. These PRs are also posted to the [i18n PRs channel](https://community.mattermost.com/core/channels/i18n-prs). Engineering PR reviews focus on ensuring that unexpected characters aren't injected into strings. If security concerns are found, Engineering notifies the Security team.

The translation PRs should be reviewed and merged as soon as possible to avoid blocking translators. 

**Important Note:** Engineering teams must merge these PRs into the codebase using "merge commit" (technically also known as "rebase and merge"), and /never/ "squash and commit". The latter breaks the automated translation server flow, locks the translations, and forces manual fixes.

### Cherry-pick translation PRs to release branches

Amy Blais will notify the team if the PR should be cherry-picked to a release branch (e.g. ``cloud``).

PR review owners:
  - Server translations PRs - Channels/Suite Users teams (Owners: Pantelis and Guillermo)
  - Webapp translations PRs - Channels/Suite Users teams (Owners: Pantelis and Guillermo)
  - Mobile translations PRs - Channels/Suite Users teams (Owners: Pantelis and Guillermo)
  - Desktop app translations PRs - Platform team (Owner: Devin)
  - Boards translations PRs - Boards team (Owners: Scott and Jesus)
  - Playbooks translations PRs - Playbooks team (Owners: Jesse and Caleb)

## Translation quality

In order for users to understand the accuracy and coverage of language translations, quality levels are explicitly defined for each language as one of: Official, Beta, or Alpha.

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

* Translation has not yet reached Beta quality. An official language may be changed back to Beta or Alpha if the specified requirements are not met for a release. Similarly, Beta languages may be dropped back to Alpha.

Alpha languages are listed in **Account Settings &gt; Display &gt; Language** appended with **\(Alpha\)**.

## Message syntax

To format localized messages, [mattermost-webapp](https://github.com/mattermost/mattermost-webapp) uses the [react-intl](https://formatjs.io/docs/react-intl), a Javascript library from [FormatJS](https://formatjs.io). This library uses the [ICU Message syntax](http://userguide.icu-project.org/formatparse/messages), which is the standard syntax for many programming languages.

If you don't know about the ICU syntax, please familiarize yourself by reading the [ICU Message Syntax simplified documentation](https://formatjs.io/docs/core-concepts/icu-syntax/) and [Formatting Messages](https://unicode-org.github.io/icu/userguide/format_parse/messages/). What's most important here is to read the sections dedicated to how plural terms are managed.

In order to ease the manipulation of strings like these with a special syntax \(ICU as a reminder\), a developer has created an online tool for testing ICU strings. This tool, called [Online ICU Message Editor](https://format-message.github.io/icu-message-format-for-translators/editor.html), is displayed as a live editor that previews how a string will appear in context. This tool has been reported by some members of our community as really helpful to translate strings containing an ICU syntax. Don't hesitate to use it.

## Resources for translating technical terms

Some terms used in Mattermost may be technical. If you don't know how to translate a specific term:

* Where applicable, review how the term has been translated in other locations of the translation you are contributing to.
* Where applicable, review machine translation suggestions provided via the Deep-L integration.
* Use a translation engine to learn how others have translated the term.
* Use the [Microsoft open linguistic portal](https://www.microsoft.com/en-us/language/Search).
* Ask your question in the [Mattermost localization channel](https://community.mattermost.com/core/channels/localization).

## Test translations

A [Mattermost Cloud workspace](https://localization.cloud.mattermost.com/) is available for all Mattermost translators to understand string context, including the target user and the task the user is performing when they encounter the string. This workspace is updated weekly; however, translations can lag behind Cloud releases by up to two weeks.

### Missed translations

If you encounter a product string that hasn't yet been translated in the Mattermost Cloud workspace, the string is either not yet translated, or the workspace hasn't been updated yet to include that translated string. 

You can search for strings in the English localization resource file within a respective GitHub repository to confirm whether a missed translation or an outdated workspace. The following resource files are available for US English strings:

* [mattermost-server](https://github.com/mattermost/mattermost-server/blob/master/i18n/en.json)
* [mattermost-webapp](https://github.com/mattermost/mattermost-webapp/blob/master/i18n/en.json)
* [mattermost-mobile-v2](https://github.com/mattermost/mattermost-mobile/blob/master/assets/base/i18n/en.json)
* [mattermost-desktop](https://github.com/mattermost/desktop/blob/master/i18n/en.json)

Each Mattermost GitHub repository above will contain additional resource files for each supported language. If a string appears in the `en.json` file, but displays in English in a localized resource file, that string likely isn't translated yet. An English string in the `en.json` file that is translated in its associated localized resource file likely indicates that the workspace hasn't been updated yet to include that translation.

If you discover a missing translation, please let us know in the [Mattermost localization channel](https://community.mattermost.com/core/channels/localization). 

## Translation maintenance

Product translations require updates on a monthly basis as features are added and changed. Weekly updates and deadlines are announced in the [Mattermost localization channel](https://community.mattermost.com/core/channels/localization).

Below are current official reviewers and maintainers for officially supported languages. Official reviewers submit final translations for languages; maintainers suggest translations and step in when official reviewers aren't able to help in a certain release.

If you're interested in contributing to the process, please join the [Mattermost localization channel to discuss](https://community.mattermost.com/core/channels/localization). 

| Language | Official Reviewer\(s\) | Maintainers |
| :--- | :--- | :--- |
| Bulgarian | [Nikolai Zahariev \(nikolaiz\)](https://translate.mattermost.com/user/nikolaiz/) | TBD (Open role) |
| Deutsch - German | [JtheBAB \(jthebab\)](https://translate.mattermost.com/user/JtheBAB/) | [Jan-Peter Rusch \(jprusch\)](https://translate.mattermost.com/user/jprusch/) |
| English - Australian | [Matthew Williams \(matthew.williams\)](https://translate.mattermost.com/user/matthew-w/) | TBD (Open role) |
| Español - Spanish | [Elias Nahum \(enahum\)](https://github.com/enahum) | [Jesús Espino \(jespino\)](https://github.com/jespino) |
| Français - French | [William Gathoye \(wget\)](https://github.com/wget) | TBD (Open role) |
| Magyar - Hungarian | TBD (Open role) | TBD (Open role) |
| Italiano - Italian | [Michael Longo \(mlongo4290\)](https://github.com/mlongo4290) | [Ema Panz \(thepanz\)](https://github.com/thepanz) |
| 日本語 - Japanese | [Yusuke Nemoto \(kaakaa\)](https://github.com/kaakaa) | TBD (Open role) |
| 한국어 - Korean | TBD \(Open role\) | TBD (Open role) |
| Nederlands - Dutch | [Tom De Moor \(ctlaltdieliet\)](https://github.com/ctlaltdieliet) | TBD (Open role) |
| Polski - Poland | [Daniel Burzmiński \(hectorskypl\)](https://github.com/hectorskypl) | [Tomasz Gruca \(gruceqq\)](https://translate.mattermost.com/user/gruceqq) |
| Português do Brasil - Portuguese | [Rodrigo Corsi \(rodcorsi\)](https://github.com/rodcorsi) | TBD (Open role) |
| Română - Romanian | TBD \(Open Role\) | TBD (Open role) |
| Svenska - Swedish | [Martin Johnson \(johnsonbrothers\)](https://github.com/johnsonbrothers) | TBD (Open role) |
| Türkçe - Turkish | [Kaya Zeren \(kaya\_zeren\)](https://twitter.com/kaya_zeren) | TBD (Open role) |
| Pусский - Russian | [Konstantin Talalov \(eleferen\)](https://translate.mattermost.com/user/Eleferen/) | TBD (Open role) |
| Yкраїнська - Ukrainian | TBD \(Open role\) | TBD (Open role) |
| 中文 \(简体\) - Simplified Chinese | [aeomin \(aeomin\)](http://translate.mattermost.com/user/aeomin) | TBD (Open role) |
| 中文 \(繁體\) - Traditional Chinese | [Tze-Kei Lee \(chikei\)](https://github.com/chikei) | TBD (Open role) |

## Administrative tasks

Translation server admins must grant all new translators with specific permissions to enable translators to start working on Mattermost strings. Translation server admins can reach the server's administration tools by going to https://translate.mattermost.com/admin/.

**Note:** Admin tools on the translation server are being updated to make roles and permissions maintenance easier. If you require translation permissions, please let us know in the [Mattermost localization channel](https://community.mattermost.com/core/channels/localization).

To add a new WIP language:

1. Go to [https://translate.mattermost.com/projects/i18n-wip](https://translate.mattermost.com/projects/i18n-wip).
2. Select a component on the resulting page, then select **Tools > Start new translation**. 
3. Select the languages you want to add, then **Start new translation**.
4. Repeat step 2 for every component within the [https://translate.mattermost.com/projects/i18n-wip](https://translate.mattermost.com/projects/i18n-wip) project.

## Setting up new translations on Weblate

### Step 0 - Permissions

Register an account and request admin permissions to the [Weblate server](https://translate.mattermost.com/) from Carrie Warner or Tom De Moor.

### Step 1 - Create a new Project (optional)

This step makes sense when the project has its own repository (e.g. Calls) or if it's helpful to have a separate translation entry point. Another option is to simply skip this step, and add a new component to an existing project.

**Note:** Make sure to enable reviews for the project. In Weblate, go to **Project Settings**, select the **Workflow** tab, and select **Enable Reviews**:

![image](https://user-images.githubusercontent.com/1832946/227036224-cb42bbd5-f101-4d42-b18d-fe5d8f3f44c4.png)

### Step 2 - Add component(s)

Add a new component under the project.

![image](https://user-images.githubusercontent.com/1832946/227037904-2165a769-0d6d-4b4e-8b6e-2260c2061d60.png)

Base configuration should look as follows:

- *Version control system* should be set to *Github pull request*.
- *Source code repository* should be set to the GitHub repository where the translation files are stored.
- *Repository branch* should be set to the primary branch where translations should get merged into (usually either `master` or `main`).

When you select **Continue**, Weblate will attempt to scan the repository to find any existing translation files paths. You can now select the one you'd like to cover with this component.

Uncheck *Edit base file* as it will prevent contributors from modifying the default language file and prevent potential conflicts.

![image](https://user-images.githubusercontent.com/1832946/227040250-2dec9c1e-da44-41b4-ae12-2ebe3f85681d.png)

Set *Translation flags* to `ignore-inconsistent, ignore-same, icu-message-format`.

![image](https://user-images.githubusercontent.com/1832946/227045392-ca3640bd-d0c1-48d2-86ee-657b40e068b2.png)

### Step 3 - Repository hooks

Repository hooks (usually GitHub hooks) are needed to keep the translation files on Weblate in sync with the ones commited to the project repository. 

![image](https://user-images.githubusercontent.com/1832946/227048773-db198f4b-4f73-4e20-a89c-a1b8492bf0df.png)

You can create a ticket for the Release team if you need Admin permissions on the repository.
