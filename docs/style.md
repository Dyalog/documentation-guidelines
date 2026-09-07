# Style Guide
When using [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)

## Document Structure and General Style Guidelines

!!! Info "Information"
    [Style_Guide_and_Best_Practice](https://wiki.bramley.dyalog.com/index.php/Style_Guide_and_Best_Practice) on the internal wiki covers:

    - The structure to use for documents
    - General rules to follow when writing, including language-related guidelines such as the use of Dyalog-specific terms, how to mention third-party products, and the use of abbreviations and acronyms.

    Please make sure you follow these as well as the styles detailed on this page.

Some aspects have been adapted in this document for use with Material for MkDocs:

- [Headings](#headings)
- [Code](#code)
- [Notes](#notes)

## Document structure

In a MkDocs site, the left panel is defined by the organisation of the documentation source files and directories. Strive to keep this simple, and aim for fewer, larger files, instead of many smaller ones. The right panel is defined by each document's internal semantic structure (its headings sequence). We want a balance between the left and right navigation panels for several reasons:

1. Fewer HTTP requests means a decrease in perceived latency.
2. The MkDocs Material theme is designed with the two-panel navigation in mind. This means that if you write many, small documents with no internal sections, the presentation lools weird with large areas of whitespace.
3. Especially for large sites, a large, multi-tiered left side is harder to operate, as opening large folded sections soon becomes confusing.

Aim for a flatish structure, grouping logically related aspects into single Markdown documents.

Give a document a file name that matches its page title (the H1), and update any table-of-contents entry to match.

Where an overview introduces items that are then described in their own sub-sections, link the introductory bullets to those sub-sections, and keep the order of parallel constructs (an introductory list, any following list, and the sub-sections that expand them) identical throughout the page.

Do not repeat content that already appears in another section; move it to the section where it belongs. Merge a stranded one-line paragraph into the adjacent paragraph. Deliberate repetition is acceptable where it genuinely helps the reader.

Place hidden search keywords, deprecated material, and other less-relevant content at the end of the page.

When a change affects a parallel configuration file (for example, both `mkdocs.yml` and `print_mkdocs.yml`), make the same change in each.

Place an example, or any content, in the section describing the specific feature it illustrates, not in a general section. Conversely, write a section generically when its mechanism is general rather than tying it to one instance.

Open a reference page with a brief statement of what the function or feature does, before the argument or case detail.

Do not search-boost summary, by-category, or index pages; consider excluding them from search instead of boosting them.

## Headings
Headings are denoted by a number of octothorpes (hashes) corresponding to the heading level.

```
# Heading 1 (H1)
## Heading 2 (H2)
###### Heading 6 (H6)
```

Headings should be written in [title case](https://en.wikipedia.org/wiki/Title_case#Chicago_Manual_of_Style). In a hyphenated compound, capitalise the first element but keep the second element lower case, for example, "Pattern-matching Rules" and "Two-digit Years". (Table captions, by contrast, use sentence case; see [Tables](./tables.md).)

Headings must be meaningful and descriptive; revisit any heading that does not clearly describe its section.

Try to avoid multiple consecutive headings with no intervening text. If two consecutive headings sit at the same level with no content on the first, merge them, remove one, or add intervening text. Place a subsection under the section it logically belongs to, not at the same level as its parent; content that is not specific to the current topic belongs in the more general parent section.

Crucially, every document *must* start with an H1, and the heading sequence should never have gaps: when increasing nesting depth, an H{X} should only be followed by H{X+1}. Headings describe the semantic (the "meaning") structure of the document, not the layout. MkDocs rely on the semantic structure to lay out its left, and right navigational panels. 

Additionally, the MkDocs source may be used to render the documentation in different formats, such as CHM and PDF, and these conversions may depend on the correct semantic documentation structure.

## Italics
Use italics when:

- introducing a new term, or using a defined technical term as a gloss, for example, a *shy* result, a *lossy* conversion, the *prototype*, a *pass-through* value
- naming a function or operator by its English name
- an algebraic term is being used instead of the number, then it should be italicised to distinguish it from the postscript, for example, "the ith term" or "the nth time".

When naming a primitive, give its English name in italics followed by its glyph in a code span, and link the first mention to the primitive's page, for example, [*format* (`⍕`)](#). Name any other glyph the same way, dropping the link where there is no page to link to, for example, "_quad_ (`⎕`)" rather than "the Quad symbol".

Italics are denoted by single asterisks or underscores surrounding the text.

``` { .example}
The word *asterisks* is italicised.

The word _asterisks_ is italicised.
```

The word *asterisks* is italicised.
{ .example-output }

## Bold
Bold text is denoted by double asterisks surrounding text.

Bold text is used for:

- file names
- file paths
- directory and folder names
- file extensions
- configuration parameter names (for example, **edit_first_x**)
- UI components such as menus, menu items, tabs, dialog boxes, checkboxes, and field labels (but not buttons)

``` { .example }
Go to the **file** menu
```

Go to the **file** menu
{ .example-output}

Do not use bold to emphasise ordinary words in running text; reserve it for the categories above.

## Hyperlinks
Used to create links to other parts of the same document, [other documents](#references) or external sources.

Link text is surrounded by square brackets and the link URL is in round parentheses.

Link text carries no leading or trailing space: write `[StatusOnEdit](...)`, never `[ StatusOnEdit](...)`. The stray space is rendered as part of the link, so it underlines oddly and makes the link text no longer match the thing it names.

Where the link text names a field, tab, or other part of the interface, it must match the software exactly. If the link text instead describes the destination, say what the reader will arrive at, as in "the **⎕WX** field on the **Session** tab", rather than naming the field alone and leaving the reader to guess where it lives.

### Internal links
Links can use text other than the URL when linking to:

- a place within the same page
- a page within the same document
- a page or document within the same project
- another document in a different Dyalog project

<h4 class="example">Example</h4>

```
See the [Link User Guide](https://dyalog.github.io/link) and...
```

<div class="example-output" markdown="1">
See the [Link User Guide](https://dyalog.github.io/link) and...
</div>

### Other links
Other links should be phrased so that the link is the URL for clarity.

```
Link can be downloaded from [https://github.com/Dyalog/link](https://github.com/Dyalog/link)
```

<div class="example-output" markdown="1">
Link can be downloaded from [https://github.com/Dyalog/link](https://github.com/Dyalog/link)
</div>

## Mixing HTML and Markdown

All HTML is valid Markdown, which on occasion provides a helpful escape hatch to create more elaborate constructs not supported directly in Markdown. However, avoid this unless absolutely necessary. The justifications for this are:

1. It's rarely required, and usually a sign that what you're doing can be simplified. 
2. It represents a contribution barrier. Markdown is designed to be read and written by humans first; HTML is not.

We have added extensions to make the use of HTML avoidable:

* Extended table syntax to allow the use of headerless [tables](./tables.md) with row-, and col-spans. 
* Attribute lists, such as `{ .example}` to allow for assigning CSS classes and IDs to elements without encasing them in HTML tags.

## Markdown inside HTML
Sometimes it might be useful to use Markdown inside HTML tags. For example, when including links inside a table.

Set `markdown="1"` inside the opening tag.

<p class="example">Example</p>

```
<p class="myClass" markdown="1">
Markdown renders in here. For example, *italicised text*.
</p>
```

<div class="example-output" markdown="1">
<p class="myclass" markdown="1">
Markdown renders in here. For example, *italicised text*.
</p>
</div>

## Notes

### Creating a Note
Notes are implemented as MkDocs [admonitions](https://squidfunk.github.io/mkdocs-material/reference/admonitions/).

They are denoted by three exclamation marks followed by the note type and title text. On subsequent lines, note content is indented by four spaces.

We use a fixed set of admonition types for consistency.

**Do not forget** to include the title text. The title text must be as shown below.

### Note types

#### General Notes for Emphasis
Notes are used to highlight important information.

- Hints and Recommendations
    
    Hints, tips, best practice and recommendations from Dyalog Ltd

    ``` { .example}
    !!! Hint "Hints and Recommendations"
        If both DOSLimit and BufferSize are set, then the smaller value applies. Dyalog Ltd recommends using a modest BufferSize and not setting EnableBufferSizeHttp to ensure that abnormally large headers are not processed, then setting an appropriate DOSLimit to accommodate the expected size messages.
    ```

    <div class="example-output" markdown="1">

    !!! Hint "Hints and Recommendations"
        If both DOSLimit and BufferSize are set, then the smaller value applies. Dyalog Ltd recommends using a modest BufferSize and not setting EnableBufferSizeHttp to ensure that abnormally large headers are not processed, then setting an appropriate DOSLimit to accommodate the expected size messages.
    
    </div>

- Information

    Highlighting material of particular significance or relevance

    <p class="example">example</p>

    ```
    !!! Info "Information"
        The .NET interface only works with the Unicode edition of Dyalog; Classic edition is not supported.
    ```

    <div class="example-output" markdown="1">

    !!! Info "Information"
        The .NET interface only works with the Unicode edition of Dyalog; Classic edition is not supported.
    
    </div>

- Warning

    Warnings about actions that can impact the behaviour of Dyalog or have unforeseen consequences

    <p class="example">example</p>

    ```
    !!! Warning "Warning"
        The structure under the SALT directory must not be modified and the five sub-directories must not be renamed.
    ```

    <div class="example-output" markdown="1">

    !!! Warning "Warning"
        The structure under the SALT directory must not be modified and the five sub-directories must not be renamed.
    
    </div>

- Legacy

    Legacy information pertaining to behaviour in earlier releases of Dyalog or to functionality that still exists but has been superseded and is no longer recommended

    <p class="example">example</p>

    ```
    !!! Legacy "Legacy"
        Although .dyapp files are supported for backwards compatibility, Dyalog Ltd recommends launching the interpreter directly from any APL source or configuration file (functionality introduced with Dyalog version 18.0) rather than through the now-superseded .dyapp file mechanism.
    ```

    <div class="example-output" markdown="1">

    !!! Legacy "Legacy"
        Although .dyapp files are supported for backwards compatibility, Dyalog Ltd recommends launching the interpreter directly from any APL source or configuration file (functionality introduced with Dyalog version 18.0) rather than through the now-superseded .dyapp file mechanism.
    
    </div>

#### Operating-system-specific Behaviour
Notes are also used to differentiate between operating-system-specific behaviour in cross-platform documents:

- Dyalog on Linux

    Behaviour specific to Dyalog on Linux

    <p class="example">example</p>

    ```
    !!! linux "Dyalog on Linux"
        The MyUCMDs directory is located directly under the **$HOME** directory
    ```

    <div class="example-output" markdown="1">

    !!! linux "Dyalog on Linux"
        The MyUCMDs directory is located directly under the **$HOME** directory
    
    </div>

- Dyalog on Unix

    Behaviour specific to Dyalog on Unix

    <p class="example">example</p>

    ```
    !!! unix "Dyalog on Unix"
        By default, the cache file is located in **$HOME/.dyalog/**
    ```

    <div class="example-output" markdown="1">

    !!! unix "Dyalog on Unix"
        By default, the cache file is located in **$HOME/.dyalog/**
    
    </div>

- Dyalog on macOS

    Behaviour specific to Dyalog on macOS

    <p class="example">example</p>

    ```
    !!! macos "Dyalog on macOS"
        By default, the cache file is located in **Users/<name\>/.dyalog/**
    ```

    <div class="example-output" markdown="1">

    !!! macos "Dyalog on macOS"
        By default, the cache file is located in **Users/<name\>/.dyalog/**
    
    </div>

- Dyalog on Microsoft Windows

    Behaviour specific to Dyalog on Microsoft Windows

    <p class="example">example</p>

    ```
    !!! windows "Dyalog on Microsoft Windows"
        By default, the cache file is located in **Documents\\Dyalog APL <version> Files\\**
    ```

    <div class="example-output" markdown="1">

    !!! windows "Dyalog on Microsoft Windows"
        By default, the cache file is located in **Documents\\Dyalog APL <version> Files\\**
    
    </div>

For behaviour specific to Dyalog on AIX, use the `unix` admonition type with the title "Dyalog on AIX": `!!! unix "Dyalog on AIX"`.

Place a warning about temporary or experimental (I-beam) functionality at the top of its page.

Present a glyph's Classic-edition replacement in an `!!! Info "Information"` admonition, for example, noting that `⍛` is unavailable in Classic edition and that the *behind* operator is represented by `⎕U235B` instead.

## Actions and Instructions
Instructions are used when there is a logical sequence of steps to do something.

Instructions are written as an ordered list. Blocks that contain instructions should be surrounded by horizontal rules. The introductory line ("To do...") should be **bold** and should not end with any punctuation.

<span class="example">Example</span>

```markdown
---

**To do this thing**

1. Do this thing
2. Then do this thing

---
```

<div class="example-output" markdown="1">

---

**To do this thing**

1. Do this thing
2. Then do this thing

---

</div>>

## Examples
Examples are used to demonstrate the functionality discussed.

Introduce full examples with:

```
<h* class="example">Example</h*>
```

Where `<h*>` is a heading one level below the containing section. You must use an HTML `<h>` tag, both to include the `example` class and because headings written in HTML will not appear in the table of contents. Use "Example" for a single example and "Examples" when the section contains more than one.

Exception – if there are several consecutive examples illustrating different things, they can each be introduced with "Example: <text\>" if that helps to clarify things for the reader. Precede every example, and every example sub-heading, with a brief explanation of what it demonstrates; do not show output for its own sake. An example's label may carry a platform qualifier, for example, "Example (Microsoft Windows)".

!!! Info "Information"
    The examples in this document use `<div class="example-output" markdown="1">` to provide a grey background that distinguishes examples from normal text. However, we do not use this convention in our actual documentation.
```
<h3 class="example">Example</h3>

This is an example
```

<h3 class="example">Example</h3>

This is an example

## Code
Inline code and code blocks render in APL font unless the class "language-nonAPL" is used.

End the sentence that introduces a code block with a colon, not a full stop, so that the block reads as part of it. Where the sentence would otherwise end and a separate remark follows, join them with a semicolon and keep the colon at the end, as in "You can change MultiLine dynamically, using `⎕WS`:".

Syntax highlighting is not enabled.

Use a code span for every APL glyph, system name, code identifier, and literal value, for example, `⎕IO`, `X`, `0`, `1`, and `'en'`. Within a single example, list, or table, treat comparable items consistently: do not put some in a code span and leave others in plain text. Render non-APL literals with the `language-nonAPL` class, for example, <code class="language-nonAPL">true</code>, <code class="language-nonAPL">false</code>, and <code class="language-nonAPL">null</code>. Choose the font by the token's language: APL names and expressions go in an APL code span, while foreign type, class, and interface names (for example, .NET types) go in `language-nonAPL`, and file names go in bold. Do not place a code span inside an `example`-class element; the combination renders badly.

#### Inline code
Inline, use `<code>[your code here]</code>` or single backticks `` `[your code here]` ``.

<p class="example">Example: APL code</p>

```html
The average of a vector (`+⌿÷≢`) is the sum divided by the tally.
```

<div class="example-output" markdown="1">

The average of a vector (`+⌿÷≢`) is the sum divided by the tally.

</div>>

<p class="example">Example: non-APL code</p>

```html
<code class="language-nonAPL">getpid()</code> is common to all Unix platforms.
```

<div class="example-output" markdown="1">

<code class="language-nonAPL">getpid()</code> is common to all Unix platforms.

</div>>

#### APL Code blocks
Code blocks use triple backticks with "apl" (lowercase) to denote the language.


```apl
      3+⍳10
4 5 6 7 8 9 10 11 12 13
```

<p class="example">Example: Using backticks</p>

```````
```apl
      3+⍳10
4 5 6 7 8 9 10 11 12 13
```
```````

```apl
      3+⍳10
4 5 6 7 8 9 10 11 12 13
```

#### Non-APL Code Blocks
Use triple backticks with "nonAPL".

<p class="example">Example: Using backticks</p>

``````
```nonAPL
>>> print("hello")   # Code block example
hello
```
``````

```nonAPL
>>> print("hello")   # Code block example
hello
```

### APL Code <span class="language-apl">+⌿÷≢⌹</span> in Titles
Try to avoid using APL code in headings – although it is rendered in APL font on the page, it is not rendered correctly in the navigation menus.

If it is essential, use `<span class="language-apl">` to add code to titles. 

<p class="example">Example</p>

```markdown
### APL Code <span class="language-apl">+⌿÷≢⌹</span> in Titles
```

## References
Always use meaningful link text. Never use "see [here](#)".

Make the term itself the link within the running sentence; do not append a trailing "(see [Name])" parenthetical. (Reserve "See also" for pointing to a separate, closely related page.)

Link the first mention of a function, operator, configuration parameter, or defined term to its reference page. When the target is a specific subsection, link to that subsection's anchor, not to the page as a whole.

On repeated mentions, link only the first; later mentions of the same target stay plain. A request to "link X" is already satisfied if the page links X earlier, so check the whole page before adding one; where the earlier mention is the better place for it, move the link rather than adding a second.

Make a link relative to the current file, not an absolute site path. When the exact target cannot be linked (for example, it sits inside a collapsible), link to the containing page instead.

Companion reference pages should cross-link reciprocally: each page's "See also" points to the others. Where link text pairs a code identifier with a gloss, separate them with an en-dash, for example, [`109⌶` – deprecated-feature log file](#).

A version-specific document, such as the Release Notes for a release, is the exception to the rule against version numbers in links: pin that release's version in its links rather than using "latest", so the historical page keeps pointing at the matching version.

Do not refer to another part of a document by position. Replace phrases such as "the table below", "the following table", "see above", and "as shown below" with an actual cross-reference to the anchored target (see [Captions and References](./tables.md#captions-and-references)).

Do not over-link. Judge whether a link adds value before adding it, and do not link every item in a set (for example, every sub-option of an option) where doing so would clutter the text.

Do not put a version number in an internal link; start the link after the version segment so that it does not go stale.

Link out to an authoritative external source (for example, an ISO standard or a Wikipedia article) where it helps the reader.

Use a "See also" link to point to a closely related page, such as a companion configuration parameter.

### Within the same document
Reference to another section within the same document.

```
See [Note Types](#note-types)
```

<div class="example-output" markdown="1">
See [Note Types](#note-types)
</div>>

### To another document
References to other documents should correctly name the document and be italicised. Ideally they should link to the document.

<p class="example">Example</p>

```
For more information on the _Clean_ function, see the [_SALT User Guide_](https://docs.dyalog.com/latest/SALT%20User%20Guide.pdf).
```

<div class="example-output" markdown="1">

For more information on the _Clean_ function, see the [_SALT User Guide_](https://docs.dyalog.com/latest/SALT%20User%20Guide.pdf).

</div>>

## Command Codes and Keys
When referring to keyboard shortcuts, such as those controlled by `⎕KL` on Microsoft Windows, put the code in angle brackets and make it bold.

Closing angle brackets must be escaped with a backslash (e.g. `**<keycode\>**`). This applies to any literal `<` in prose, not only keycodes: escape it as `&lt;`, because unescaped angle-bracket content is silently stripped as an HTML tag when rendered. Introduce a command by its italicised English name followed by the bold command code in parentheses, then use the bold code alone thereafter, for example, "the *Reformat* command (**<RD\>**)".

Example
{ .example}

```
**<TC\>** is the command code for trace.
```

**<TC\>** is the command code for trace.
{ .example-output}

## Keyboard keys
Use the `<kbd>` tag to refer to keys. This is a case where using HTML markup is unavoidable.

example
{ .example}

```
Press the <kbd>Enter</kbd> key.
```

Press the <kbd>Enter</kbd> key.
{ .example-output}

## Icons
Sometimes it is relevant to include an icon. For example, when describing a combination of key presses.

Icons are included using a special name surrounded by colons.

Here is the list of icons used in our documentation.

- Apple icons:
    - Apple key: :material-apple: (`:material-apple:`)
    - Command Key: :material-apple-keyboard-command: (`:material-apple-keyboard-command:`)
    - Option key: :material-apple-keyboard-option: (`:material-apple-keyboard-option:`)
- Windows Key: :fontawesome-brands-windows: (`:fontawesome-brands-windows:`) 

<p class="example">Example</p>

```
Use <kbd markdown="1">:material-apple-keyboard-command:</kbd> + <kbd>C</kbd> to copy text
```

<div class="example-output" markdown="1">
Use <kbd markdown="1">:material-apple-keyboard-command:</kbd> + <kbd>C</kbd> to copy text
</div>>
