# User Interface Text Guidelines

## UX Writing Principles

Following the Writing Guidelines below will ensure communications to our users feel like they are coming from the same voice.

**Concise**

Use short words and sentences. Avoid unnecessary fluff.

**Clear**

Always write for clarity and simplicity. Err on the side of simple language that can be understood by novice users and avoid vague terms.

**Consistent**

Be consistent with terminology across the product. Although we may have different terms for the same things internally, always use the same language to describe the same thing within the product.

## User interface text guidelines 

These guidelines cover two types of UI text:
- Messages triggered because something happened
- Static text on the user interface

### General principles for UI (in-product) text

- Keep in mind that your users are from all over the world. 
- Use the present tense to describe a current state or condition, and the future tense to state something that is very definitely going to happen.
- Use the active voice, except for these cases:
  - If you’ll end up blaming the user. For example, don’t say **You entered an incorrect password**. Instead, say **The password is incorrect**.
  - If you’re describing what just happened. For example, it’s okay to say **Your incoming webhook is set up**.
  - If the subject (the doer of an action) is the Mattermost application itself. For example, it’s okay to say **The image is deleted** instead of **The server deleted the image**.
- If you’re asking the user to do or not do something, use imperatives (command phrases). For example, say **Do not change the Hostname** instead of saying **It is not recommended to change the Hostname**. Better still, explain what could go wrong if they do or don’t do something. For example, say **Do not change the Hostname because if you do so <this bad thing will happen>**.

### Guidelines for System Messages

Don’t blame the user. Inform them about what happened, explain why it happened, and suggest a way forward. Try to use complete sentences in your messages. A sentence phrase (an incomplete sentence) might sound okay in English but could present internationalization challenges.

If a System Message contains variables (tokens):
- Do not use verbs or adjectives as variables.
- Do not create plurals of variables by adding an s.
- If the variable is a noun, use a qualifier after the variable. For example, say **The {channel_name} channel was created** instead of saying **The {channel_name} was created**.

System Messages can be of the following types: **notification**, **confirmation**, **warning**, and **error**. The following sections contain guidelines that are specific to each of these types.

### Notification messages

A notification message is for informing somebody about something that happened. Such messages do not need any user input, and do not prevent a user from continuing to use Mattermost.

- Use either a complete sentence or a sentence phrase.
- If using a complete sentence, end it with a period.
- Examples:
  - **Member added to channel.**
  - **The plugin was installed.**

### Confirmation messages

A confirmation message is for asking somebody to confirm whether the immediately preceding command should be proceeded with. The user cannot use Mattermost until a confirmation is given or denied.

- Use complete sentences.
- Include a question that has a Yes/No answer.
- Examples:
  - **Are you sure you want to delete this channel?**
  - **A plugin with this ID already exists. Would you like to overwrite it?**

### Warning messages

A warning message is for alerting somebody about something that might go wrong. The user can continue using Mattermost unless the warning message needs an explicit user input.

- Use complete sentences.
- Explain what has happened or can happen, and what can go wrong as a consequence.
- Examples:
  - **The Enterprise license expires in 2 days. If you do not renew it, some features will be disabled on licence expiry.**
  - **If you claim this AD/LDAP account, you will no longer be able to log in with your email.**

### Error messages

An error message is for telling somebody that something went wrong. Errors prevent a user from doing a task or accessing a feature till the error is resolved.

- Use complete sentences.
- If what went wrong isn’t obvious, explain in one sentence.
- If a solution or workaround isn’t obvious, suggest one.
- Examples:
  - **Messages must have fewer than 120 characters.**
  - **A connection to the marketplace server could not be established. Check your settings on the [System Console](<hyperlink>)**. 
  
## Button labels and links

Button labels should always use action words and describe the action as concisely as possible. They should be limited to four words or less. Examples: “Log In”, “Send Invitation”.

## Navigation labels

Navigation labels should be as short as possible and support the user in finding their way.

### Input labels

Input labels should be as short and concise as possible and describe the input field.

### Capitalization

**Titles** 

Titles should use Sentence case. Exceptions would be when proper nouns are being used.

**Button labels, input labels and navigation labels** 

These labels should use Sentence case. Exceptions would be when proper nouns are being used.

### Punctuation

**Titles**

Titles should omit periods unless the headline is more than one sentence.

**Paragraphs**

Paragraphs should always use proper punctuation.

**Bullets**

Bullets should omit periods unless the bullet text is more than one sentence.

**Button labels**

Button labels should always omit periods or punctuation.
