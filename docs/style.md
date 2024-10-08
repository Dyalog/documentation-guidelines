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

## Headings
Headings are denoted by a number of octothorpes (hashes) corresponding to the heading level.

```
# Heading 1 (H1)
## Heading 2 (H2)
###### Heading 6 (H6)
```

Headings should be written in [title case](https://en.wikipedia.org/wiki/Title_case#Chicago_Manual_of_Style).

Try to avoid multiple consecutive headings with no intervening text.

Crucially, every document *must* start with an H1, and the heading sequence should never have gaps: when increasing nesting depth, an H{X} should only be followed by H{X+1}. Headings describe the semantic (the "meaning") structure of the document, not the layout. MkDocs rely on the semantic structure to lay out its left, and right navigational panels. 

Additionally, the MkDocs source may be used to render the documentation in different formats, such as CHM and PDF, and these conversions may depend on the correct semantic documentation structure.

## Italics
Use italics when:

- introducing a new term
- naming a function or operator
- an algebraic term is being used instead of the number, then it should be italicised to distinguish it from the postscript, for example, "the ith term" or "the nth time".

Italics are denoted by single asterisks surrounding the text.

``` { .example}
The word *asterisks* is italicised.
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
- UI components (not buttons)

``` { .example }
Go to the **file** menu
```

Go to the **file** menu
{ .example-output}

## Hyperlinks
Used to create links to other parts of the same document, [other documents](#references) or external sources.

Link text is surrounded by square brackets and the link URL is in round parentheses.

- <span class="example">Example: link text is URL</span>
    ```
    Link can be downloaded from [https://github.com/Dyalog/link](https://github.com/Dyalog/link)
    ```
    Link can be downloaded from [https://github.com/Dyalog/link](https://github.com/Dyalog/link)

- <span class="example">Example: alternative link text</span>
    ```
    Download [Link](https://github.com/Dyalog/link) and...
    ```
    Download [Link](https://github.com/Dyalog/link) and...

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
    !!! Tip "Hints and Recommendations"
        If both DOSLimit and BufferSize are set, then the smaller value applies. Dyalog Ltd recommends using a modest BufferSize and not setting EnableBufferSizeHttp to ensure that abnormally large headers are not processed, then setting an appropriate DOSLimit to accommodate the expected size messages.
    ```

    <div class="example-output" markdown="1">

    !!! Tip "Hints and Recommendations"
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

- Dyalog on UNIX

    Behaviour specific to Dyalog on UNIX

    <p class="example">example</p>

    ```
    !!! unix "Dyalog on UNIX"
        By default, the cache file is located in **$HOME/.dyalog/**
    ```

    <div class="example-output" markdown="1">

    !!! unix "Dyalog on UNIX"
        By default, the cache file is located in **$HOME/.dyalog/**
    
    </div>

- Dyalog on macOS

    Behaviour specific to Dyalog on macOS

    <p class="example">example</p>

    ```
    !!! macOS "Dyalog on macOS"
        By default, the cache file is located in **Users/<name\>/.dyalog/**
    ```

    <div class="example-output" markdown="1">

    !!! macOS "Dyalog on macOS"
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

## Actions and Instructions
Instructions are used when there is a logical sequence of steps to do something.

Instructions are written as an ordered list. Blocks that contain instructions should be surrounded by horizontal rules. The introductory line ("To do...") should be **bold** and should not end with any punctuation.

<span class="example">Example</span>

```
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
example (or examples)
{ .example}
```

which renders as `<p class="example">example</p>`.

Exception – if there are several consecutive examples illustrating different things, they can each be introduced with "Example: <text\>" if that helps to clarify things for the reader.

!!! Info "Information"
    The examples in this document use `<div class="example-output" markdown="1">` to provide a grey background that distinguishes examples from normal text. However, we do not use this convention in our actual documentation.

```
example
{ .example}

This is an example
```

<div class="example-output" markdown="1">

example
{ .example}

This is an example

</div>

## Code
Inline code and code blocks render in APL font unless the class "language-other" is used.

Syntax highlighting is not enabled.

#### Inline code
Inline, use `<code>[your code here]</code>` or single backticks `` `[your code here]` ``.

<p class="example">Example: APL code</p>

```html
The average of a vector (<code class="language-apl">+⌿÷≢</code>) is the sum divided by the tally.
```

<div class="example-output" markdown="1">

The average of a vector (<code class="language-apl">+⌿÷≢</code>) is the sum divided by the tally.

</div>>

<p class="example">Example: non-APL code</p>

```html
<code class="language-other">getpid()</code> is common to all UNIX platforms.
```

<div class="example-output" markdown="1">

<code class="language-other">getpid()</code> is common to all UNIX platforms.

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
Use triple backticks with the name of the language or format, or "other" (lowercase).

<p class="example">Example: Using backticks</p>

``````
```python
>>> print("hello")   # Code block example
hello
```
``````

```pythom
>>> print("hello")   # Code block example
hello
```

### APL Code <span class="language-apl">+⌿÷≢⌹</span> in Titles
Try to avoid using APL code in headings – although it is rendered in APL font on the page, it is not rendered correctly in the navigation menus.

If it is essential, use `<span class="language-apl">` to add code to titles. 

<p class="example">Example</p>

```
### APL Code <span class="language-apl">+⌿÷≢⌹</span> in Titles
```

## References
Always use meaningful link text. Never use "see [here](#)".

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
For more information on the *Clean* function, see the [*SALT User Guide*](https://docs.dyalog.com/latest/SALT%20User%20Guide.pdf).
```

<div class="example-output" markdown="1">

For more information on the *Clean* function, see the [*SALT User Guide*](https://docs.dyalog.com/latest/SALT%20User%20Guide.pdf).

</div>>

## Command Codes and Keys
When referring to keyboard shortcuts, such as those controlled by `⎕KL` on Microsoft Windows, put the code in angle brackets.

Closing angle brackets must be escaped with a backslash (e.g. `<keycode\>`).

Example
{ .example}

```
<TC\> is the command code for trace.
```

<TC\> is the command code for trace.
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
