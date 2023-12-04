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
| Playbooks | https://translate.mattermost.com/projects/playbooks/ |
| Desktop app | https://translate.mattermost.com/projects/mattermost/mattermost-desktop/ |
| Mobile app | https://translate.mattermost.com/projects/mattermost/mattermost-mobile-v2/ |
| Calls | https://translate.mattermost.com/projects/calls/ |


The general localization process is described in the following sections on this page. 

## Translate English product strings into additional languages

Mattermost is developed in US English, and officially supports 20 additional languages. Getting started is easy.

### Join the [Mattermost translation server](http://translate.mattermost.com)

**Important note:** While it's common to contribute to Mattermost in GitHub, product translations is a notable exception. You must contribute to Mattermost translations on the Mattermost translation server. Please don't attempt to submit translations in GitHub via pull requests (PRs) as your translations will be overwritten with the next PR update.

### Confirm whether the language you want to translate is one we officially support or is a work-in-progress (WIP) language. To contribute to the supported languages you need extra permissions, this is a safety measure. 
Requesting these permissions can be done in the [Mattermost localization channel](https://community.mattermost.com/core/channels/localization) or with a direct message to Carrie Warner or Tom De Moor.

Only supported languages are available in-product by selecting **Settings > Display > Language**. Any language that isn't officially supported is considered a work-in-progress language. Work-in-progress languages become officially supported languages when the following two conditions are met:
* The (WIP) language reaches or exceeds the Beta translation quality threshold across three consecutive releases; and,
* A language expert is available for at least six months of maintenance updates.

See the section on [translation quality](https://handbook.mattermost.com/contributors/join-us/localization#translation-quality) for further details.

**Tip:** We encourage translators to help us support additional languages and regional variants.

### Review translation rules written by localization leads, when applicable

Translation rules and glossaries are available for the following languages:

   * [German \(Regeln zur Übersetzung von Mattermost\)](https://gist.github.com/der-test/6e04bff8a173e053811cb93e08838ca2).
   * [French \(Règles pour la traduction francophone de Mattermost\)](https://github.com/wget/mattermost-localization-french-translation-rules).
   * [Dutch translation rules for Mattermost](https://github.com/ctlaltdieliet/mattermost-localization-dutch-translation-rules).

**Tip:** We welcome rules and guidelines for all supported languages. If these translation assets don't exist for the language you're interested in, perhaps you'd be open to help create them?

## Omit error strings from localization process

When an error string isn’t visible to end users, engineering teams must use ``model.NoTranslation`` as the error id to implement a ``model.AppError`` without a translation. See examples of this approach in the [mattermost/mattermost-server](https://translate.mattermost.com/projects/mattermost/server/) repository on GitHub.

Error strings that use ``model.NoTranslation`` as the error id are omitted from Mattermost translation workflows, and aren't surfaced up in Weblate to translators.

## Product localization process

The following flow diagram outlines the product localization flow from the translation server to the Mattermost codebase:

![Mattermost product localization flow diagram](../../../.gitbook/assets/i18n-flow.png)

1. New and updated US English source strings are automatically added to the translation server each time a GitHub PR containing string changes is merged by Mattermost Engineering.
2. The translation server pulls the latest string changes as they are committed to the codebase.
3. Translators are notified when strings are new or changed.
4. Translators add and update string translations.
5. Each Monday, at 22:00 GMT, a job opens PRs in GitHub to the main branches of the [mattermost-server and mattermost-webapp](https://github.com/mattermost/mattermost/), [mattermost-mobile](https://github.com/mattermost/mattermost-mobile/), and [mattermost-desktop](https://github.com/mattermost/desktop) repositories. Weekly PRs contain several commits, one per modified language. Changes are merged back into each branch after a security/consistency review. 

PRs will also be submitted on the day of major feature complete, code complete, and release candidates to ensure latest translations are included in the release.

## Translation PR review process

Translation PRs are created automatically on Mondays. These PRs are also posted to the [i18n PRs channel](https://community.mattermost.com/core/channels/i18n-prs). Engineering PR reviews focus on ensuring that unexpected characters aren't injected into strings. If security concerns are found, Engineering notifies the Security team.

The translation PRs should be reviewed and merged as soon as possible to avoid blocking translators. 

**Important Note:** Engineering teams must merge these PRs into the codebase using "merge commit" (technically also known as "rebase and merge"), and /never/ "squash and commit". The latter breaks the automated translation server flow, locks the translations, and forces manual fixes.

### Cherry-pick translation PRs to release branches

Amy Blais will notify the team if the PR should be cherry-picked to a release branch (e.g. ``release x.x``).

PR review owners:
  - Server translations PRs - Owner: Guillermo
  - Mobile translations PRs - Owner: Guillermo
  - Desktop app translations PRs - Owner: Devin

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

[react-intl](https://formatjs.io/docs/react-intl) is used to format localized messages in React packages of [mattermost](https://github.com/mattermost/mattermost-server). This library uses the ICU MessageFormat syntax, which is a Unicode standard used in many programming languages.

[ICU Message syntax guide](https://formatjs.io/docs/core-concepts/icu-syntax/) is a good resource to familiarize yourself with. What's most important here is to read the sections dedicated to Quoting/Escaping, and how placeholders are managed, including placeholder arguments such as `plural`, `select`, `number`, and so on.

The [Mattermost translation server](http://translate.mattermost.com) will automatically check and validate translations in the editor. If there are any failing checks, you will want to review them to spot any potential typos or errors. These checks can be quite helpful in spotting subtle issues in long or more complex translation strings.

Additionally, [Online ICU Message Editor](https://format-message.github.io/icu-message-format-for-translators/editor.html) is a good resource that supports live-editing. It's great for previewing how a string will appear in context, don't hesitate to use it.

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

* [mattermost-server and mattermost-webapp](https://github.com/mattermost/mattermost/blob/master/i18n/en.json)
* [mattermost-mobile](https://github.com/mattermost/mattermost-mobile/blob/master/assets/base/i18n/en.json)
* [mattermost-desktop](https://github.com/mattermost/desktop/blob/master/i18n/en.json)

Each Mattermost GitHub repository above will contain additional resource files for each supported language. If a string appears in the `en.json` file, but displays in English in a localized resource file, that string likely isn't translated yet. An English string in the `en.json` file that is translated in its associated localized resource file likely indicates that the workspace hasn't been updated yet to include that translation.

If you discover a missing translation, please let us know in the [Mattermost localization channel](https://community.mattermost.com/core/channels/localization). 

## Translation maintenance

Product translations require updates on a monthly basis as features are added and changed. Weekly updates and deadlines are announced in the [Mattermost localization channel](https://community.mattermost.com/core/channels/localization).

Below are current official reviewers and maintainers for officially supported languages. Official reviewers submit final translations for languages; maintainers suggest translations and step in when official reviewers aren't able to help in a certain release.

If you're interested in contributing to the process, please join the [Mattermost localization channel to discuss](https://community.mattermost.com/core/channels/localization). 

| Language | Official Reviewer\(s\) | Maintainers |
| :--- | :--- | :--- |
| Bulgarian | TBD (Open role) | TBD (Open role) |
| Deutsch - German | [JtheBAB \(jthebab\)](https://translate.mattermost.com/user/JtheBAB/) | [Jan-Peter Rusch \(jprusch\)](https://translate.mattermost.com/user/jprusch/) |
| English - Australian | [Matthew Williams \(matthew.williams\)](https://translate.mattermost.com/user/matthew-w/) | TBD (Open role) |
| Español - Spanish | TBD (Open role) | TBD (Open role) |
| Français - French | TBD (Open role) | TBD (Open role) |
| Magyar - Hungarian | TBD (Open role) | TBD (Open role) |
| Italiano - Italian | TBD (Open role) | TBD (Open role) |
| 日本語 - Japanese | [Yusuke Nemoto \(kaakaa\)](https://github.com/kaakaa) | TBD (Open role) |
| 한국어 - Korean | TBD \(Open role\) | TBD (Open role) |
| Nederlands - Dutch | [Tom De Moor \(ctlaltdieliet\)](https://github.com/ctlaltdieliet) | TBD (Open role) |
| Polski - Poland | [Master7 \(markar\)](https://translate.mattermost.com/user/Master7) | TBD (Open role) |
| Português do Brasil - Portuguese | TBD (Open role) | TBD (Open role) |
| Română - Romanian | TBD \(Open Role\) | TBD (Open role) |
| Svenska - Swedish | [Martin Johnson \(johnsonbrothers\)](https://github.com/johnsonbrothers) | TBD (Open role) |
| Türkçe - Turkish | [Kaya Zeren \(kaya\_zeren\)](https://twitter.com/kaya_zeren) | TBD (Open role) |
| Pусский - Russian | [Konstantin Talalov \(eleferen\)](https://translate.mattermost.com/user/Eleferen/) | TBD (Open role) |
| Yкраїнська - Ukrainian | TBD \(Open role\) | TBD (Open role) |
| 中文 \(简体\) - Simplified Chinese | [Sharuru \(Sharuru\)](http://translate.mattermost.com/user/Sharuru) | [ThrRip \(ThrRip\)](http://translate.mattermost.com/user/ThrRip) |
| 中文 \(繁體\) - Traditional Chinese | TBD (Open role) | TBD (Open role) |

## Administrative tasks

Translation server admins must grant all new translators specific Weblate permissions before translators can start contributing to official supported languages. Translation server admins can reach the server's administration tools by going to https://translate.mattermost.com/admin/.

**Note:** Admin tools on the translation server are being updated to make roles and permissions maintenance easier. If you require translation permissions, please let us know in the [Mattermost localization channel](https://community.mattermost.com/core/channels/localization).

To add a new WIP language:

1. Go to [https://translate.mattermost.com/projects/mattermost](https://translate.mattermost.com/projects/mattermost).
2. Select a component on the resulting page, then select **Tools > Start new translation**. 
3. Select the languages you want to add, then **Start new translation**.


## Translators permissions scheme 
The goal of the permissions scheme is to be as open as possible to new contributors and keeping the product as safe as possible.
Therefor everybody who joins our translation server is able to make translations for the WIP languages and add suggestions to the shipped languages.
Our shipped language translators can translate their language, add suggestions to other shipped languages, and add translations to WIP languages.

Mattermost@DefaultUserTranslateWIP: everybody who joins the server is automatically added to this group and is able to translate WIP languages.
Mattermost@DefaultUserSuggestionsToShipped: everybody who joins the server is automaticly added to this group and is able to make suggestions to the shipped languages
mattermost@Translators [language]: A group for each shipped language. Add translators for each language here. 


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

### Step 3 - Give translators access to your project

Access for the shipped languages is restricted to approved users. You must give access to your project on a per-language basis.

![image](https://user-images.githubusercontent.com/6507750/232693426-d0ff9143-1e4a-4181-aaeb-eedd7fb62983.png)

### Step 4 - Repository hooks

Repository hooks (usually GitHub hooks) are needed to keep the translation files on Weblate in sync with the ones commited to the project repository. 

![image](https://user-images.githubusercontent.com/1832946/227048773-db198f4b-4f73-4e20-a89c-a1b8492bf0df.png)

You can create a ticket for the Release team to request enabling the hooks.
