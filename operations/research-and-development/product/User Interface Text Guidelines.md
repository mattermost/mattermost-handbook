# User Interface Text Guidelines

This is the Mattermost style guide for text used in the Mattermost
product. Use these guidelines to ensure text on the Mattermost user
interface (UI) is consistent and clear. These guidelines cover two types
of UI text:

  - Messages triggered because something happened
  - Static text on the user interface

<div class="note">

<div class="title">

</div>

</div>

Contributions that do not adhere to this style guide will receive edit
requests; we'll merge your contribution once you edit the text to
conform to these guidelines. You might want to look at the [UX design
guidelines]() as well.

-----

<div class="contents" data-depth="2">

</div>

## General principles for in-product text

  - Keep in mind that your users are from all over the world. Use words
    that are clear and easy to understand.

  - Be concise.

  - Use the active voice, except for these cases:
    
    >   - If you'll end up blaming the user. For example, don't say *You
    >     entered an incorrect password*. Instead, say *The password is
    >     incorrect*.
    >   - If you're describing what just happened. For example, it's
    >     okay to say *Your incoming webhook is set up*.
    >   - If the subject (the doer of an action) is the Mattermost
    >     application itself. For example, it's okay to say *The image
    >     is deleted* instead of *The server deleted the image*.

  - Use the present tense to describe a current state or condition, and
    the future tense to state something that is very definitely going to
    happen.

  - If you're asking the user to do or not do something, use imperatives
    (command phrases). For example, say *Do not change the Hostname*
    instead of saying *It is not recommended to change the Hostname*.
    Better still, explain what could go wrong if they do or don't do
    something. For example, say *Do not change the Hostname because if
    you do so \<this bad thing will happen\>.*

## Guidelines for messages

Don't blame the user. Inform them about what happened, explain why it
happened, and suggest a way forward.

Try to use complete sentences in your messages. A sentence phrase (an
incomplete sentence) might sound okay in English but could present
internationalization challenges.

If a message contains variables (tokens):

  - Do not use verbs or adjectives as variables.
  - Do not create plurals of variables by adding an *s*.
  - If the variable is a noun, use a qualifier after the variable. For
    example, say *The {channel\_name} channel was created* instead of
    saying *The {channel\_name} was created*.

Messages can be of the following types: notification, confirmation,
warning, and error. The following sections contain guidelines that are
specific to each of these types.

### Notification messages

A notification message is for informing somebody about something that
happened. Such messages do not need any user input, and do not prevent a
user from continuing to use Mattermost.

  - Use either a complete sentence or a sentence phrase.
  - If using a complete sentence
