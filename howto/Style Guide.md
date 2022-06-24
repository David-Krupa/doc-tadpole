
Welcome to the Style Guide! This is meant to be a helpful, friendly, easy to understand, and collaborative guide to making communication easier and clearer between BrainGu and its users and customers. Discussion around changes/additions/suggestions to this guide should be directed to the #flame-tadpole Slack channel.


## Basic Guidelines

### References

*   [About This Guide | Salesforce Style Guide for Documentation and User Interface Text](https://developer.salesforce.com/docs/atlas.en-us.salesforce_pubs_style_guide.meta/salesforce_pubs_style_guide/overview.htm)
*   [Google developer documentation style guide](https://developers.google.com/style/)
*   [Other editorial resources | Google developer documentation style guide](https://developers.google.com/style/resources)
*   [ASD-STE100 official home page](https://github.com/braingu/tadpole/blob/master/documents/ASD-STE100%20-%20ISSUE%207.pdf)
*   [International System of Units / SI Brochure: The International System of Units (SI)](https://www.bipm.org/en/publications/si-brochure/)


### Dictionaries

*   [Merriam-Webster’s Online Dictionary](https://learnersdictionary.com/), or any print edition.

### Style Manuals

This guide takes precedence over all other sources. Having said that, we’re mostly inspired by

*   [The Chicago Manual of Style](https://www.chicagomanualofstyle.org/)
*   [Conscious Style Guide](https://consciousstyleguide.com/)
*   [Inclusive Design at Microsoft](https://www.microsoft.com/design/inclusive/)


## Rules of Engagement

### Audience

*   Before you begin authoring a document or response, be sure to accurately identify your intended audience. Where possible, stick to Simplified English, and avoid jargon.
*   Avoid cliches and cultural references. Write as plainly and in as straightforward a manner as possible.
*   At all times, maintain gender neutrality. Remember that ours is a diverse audience, and inclusion is critical. If you have any uncertainty about how to address this, the [Diversity Style Guide](https://www.diversitystyleguide.com/) is your resource. The [Wikipedia article on gender-neutral language](https://en.wikipedia.org/wiki/Gender-neutral_language) is oversimplistic (naturally) but straightforward.
*   Finally, remember that your guiding light with language and documentation is to improve usability. In everything you write, ask yourself, “will this make life easier for the reader?” Make sure you prioritize technical accuracy first, then usability, then fine points of grammar. Missing a semicolon is mostly academic, while missing a step in a procedure is catastrophic.


### Tone

Friendly, but professional, and have a casual tone that keeps in mind that your reader is a human being.

From the _Salesforce Guide_,

*   Concise
    *   Don’t add text if it’s not needed.
    *   Use as few words as possible.
    *   Focus on users’ tasks; write only what is necessary for users to complete them. Avoid unnecessary and redundant information.
    *   Keep tasks short.
*   Conversational
    *   Use language you would use with a business colleague.
    *   Contractions are OK
    *   Focus on the user — write from the users’ perspective to help them accomplish tasks.
    *   Know your user — end user tasks can have a more informal tone than administrator tasks.
    *   Use plain English.
    *   Avoid buzzwords, jargon, and words you wouldn’t say in person.


### Voice

Use active voice whenever possible. Be careful not to change the meaning of a sentence when rewording from passive to active voice.

Passive voice can be appropriate in some cases — when using active voice would create an awkward construction, when the subject is unknown or not the focus of the sentence, when you want to avoid blaming the user, or when trying to convey an impersonal tone for a technical audience.

**Correct (active)**:
    Each product group requires a unique name

**Incorrect (passive)**: A unique name is required for each product group.

**Acceptable (passive)**: No number was specified. Enter a number and try again.

Rebecca Johnson ([see Grammarly’s excellent discussion](https://www.grammarly.com/blog/passive-voice)) has pointed out that if you can insert “by zombies” after the verb, you have passive voice. And really, who wants to deal with zombies?


### Clarity and Minimalism

While it's important to include enough detail so that the user is clear on your intent, when you have the opportunity to simplify, do so. For example,

1. Select **Maintenance & Troubleshooting**, click **OK** or press **Enter**.
2. Select **Maintain Disk and Logs**, click **OK** or press **Enter**.
3. Select **Clear System Update Caches**, click **OK** or press **Enter**.

In this set of instructions, the user is being told to do a very specific set of things. But it's a pretty safe bet that our users are able to navigate a screen menu without being told repeatedly to press enter. This cluttered set of instructions can be happily reduced down to more closely resemble this:

1. Select **Maintenance & Troubleshooting**.
2. Select **Maintain Disk and Logs**.
3. Select **Clear System Update Caches**.

Think about your readers, think about what they most likely know, and make sure you're not trying to teach them that which they probably already understand.

General considerations like whether to use Latinisms (don’t), how to format UI elements versus key names (bold and not), and how to handle capitals in generic words like “web” (yes when it’s World Wide Web, and not if it isn’t), please consult the _Salesforce Guide_.

### Avoid Ambiguity

Don’t ever use “should”, “might”, or other ambiguous language. Technical communications need to be authoritative.

### Titles

#### Headings

When writing First-Level headings, use an uppercase initial letter for all nouns, verbs, and adjectives. Use an uppercase initial letter for all conjunctions and prepositions longer than 4 characters. Use all lowercase letters for conjunctions and prepositions shorter than 4 characters. Second-Level and below headings are sentence-capped.

### Structural

Be mindful of links. Always describe where they’re going, and consider whether it’s relevant to put them in-page. Blind linking is discouraged (that’s where you provide a link, but no context for the user as to why they’re going there or what they’ll find when they arrive.)

Paths should be **item > item > item**.

## Style Choices


### Abbreviations and Acronyms

When you first use an acronym in a document, write out the full term and enclose the acronym in parentheses immediately after the term.


### Comma

Oxford. Always.

Example: Item A, B, and C.


### Latinisms

Latinisms (e.g., i.e., v., etc.) are not used in simplified English. Say what you mean in English. Instead of "e.g.", you say "for example" because that's what exempli gratia means. The abbreviation "i.e." for the Latin "id est" means "in other words," so just say "in other words." Also, “etc.” is a sign of sloppy thinking: make your lists complete, and eliminate the use of this term entirely.


### Punctuation

As per American usage rules

*   Commas and periods go inside quotations

    Example: For example, a set of steps that immediately follows the title Editing a File does not need the introductory phrase “To edit a file.”

*   Parentheses go outside if it's a complete sentence inside the parentheses (see Grammar Girl's explanation.)

    Footnotes go outside, because they're not part of the sentence.


_Note Bene_: if you ever choose to localize outside of American English, these rules all change.

In sentences in text, colons only come after things that are complete sentences. If you can’t use a period, don’t use a colon. The point of a colon is to tie together two logical sentences that continue one idea.

**Example**: The team worked really hard: they deserved that promotion.

In statements that introduce material following (like a code sample, ordinal or unordered lists, tables of contents), the colon is unnecessary, because its function is to alert the reader that there's more information coming, which, if you stop midsentence, is obvious.


### Em dashes ( — ), En dashes ( – ), Minuses (), and Hyphens ( - )

These four things are completely different typographic symbols, with completely different uses.


#### Em dash

An Em dash (—) is the longest of these, and can be used to replace commas, parentheses, or ellipses. Two or more em dashes indicate missing text.

MacOX: option-shift-hyphen

Windows: command+shift+hyphen

...or Insert > Special Characters


#### En dash

These are more complicated. They indicate an equal relationship or a combative relationship between things (replaces versus). It also shows a range. I

love this description from Grammarist: Note that an en dash can alter the meaning markedly. For example, the Spanish-American War (i.e., the war that

took place in Spanish America) is different from the Spanish–American War (i.e., the war between Spain and America).

Mac OS X: option - hyphen.

WIndows: one or two spaced hyphens, or control-hyphen.


#### Minus

This is only used to indicate the mathematical operation. You can get to it from the Special Characters menu, the unicode is 2212.


#### Hyphen

This is used to join words and separate symbols.

Em dashes should have spaces on either side of them, for the benefit of mobile readers.

Do not use any of these as hardcoded bullets for bulleted lists ever. Only use the bullet function in whatever program you're using.


### Units of measure

Per the International System of Units, the numerical value always precedes the unit, and a space is always used to separate the unit from the number. So:

6 GB not 6GB.


## Terminology

There are many technical terms unique to the environment and used in specific ways, and it’s critical to the user experience that definitions for terms be consistent across all materials.


### User Interface

*   Use bold text when referring to buttons: Click **Save**.
*   In documentation, use bold font and a symbol, such as a bracket ( > ), to display menu option selections or sequences of user interface clicks. For example, **File > Print** indicates that a user selects the Print option from the File menu.
*   Include edition names in bold text. For example: **Enterprise Edition**.
*   Never highlight a sentence in boldface text.
*   Never directly reference the item (button, menu), just reference the label.

    Correct: “File” or “Return”

    Incorrect: “File menu” or “Return button”

*   No “click on.” Just “click”.

    Correct: “Click save”

    Incorrect: "Click on save"

*   Code terms are in `monospace` font.


### Code and Command Line Examples


#### Command Line

*   Bold the code that needs to be typed.
*   For a command being executed as a user use the default $ prompt.
*   For a command being executed as a superuser/root use the default # prompt.

The surrounding text should also clearly indicate which user level the command should be executed as. Do not rely on the command prompt alone to convey this potentially critical information.


### Code

When formatting code blocks, configuration data, or other preformatted text

*   Trim line lengths to less than 80 characters
*   Don't include actual prompts for command line examples, as doing so can be troublesome for readers who copy and paste command line examples.
*   Variables in code should be enclosed in angle brackets, and not italicized.


### Abbreviating Code Prompts

When command line examples are given, sometimes the prompt is long, and that makes the text in the doc somewhat unreadable. Add a convention statement at the beginning of any given doc, so that the user knows what to expect:

The prompt will be displayed as myprompt:~# but is shortened here to just # for clarity.

Example:

```
myprompt:/my/path# more device.sql
```

would be shortened to

```
# more device.sql
```


Customized prompts will not always be consistent in a user deployment. It’s cleaner to simplify the prompt so the user can focus on the command they need to enter.


## Notes, Warnings, Recommendations

For more clarity on what should be a note and what should be a warning, please check the Simplified English guidelines. Here's the general idea:

Why do we have warnings, cautions, and notes? Warnings and cautions tell the users that parts of the procedures can be dangerous and/or cause damage.

*   A warning means that injury or death is possible if the instructions are not obeyed.
*   Notes are added to give more information, usually in a procedure. They should not be written in the form of instructions. In other words, notes should not contain a command.
