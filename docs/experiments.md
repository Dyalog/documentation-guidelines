# Experiments
Temporary page to try out styles.

## Admonitions

!!! Hint "Hints and Recommendations"
    If both DOSLimit and BufferSize are set, then the smaller value applies. Dyalog Ltd recommends using a modest BufferSize and not setting EnableBufferSizeHttp to ensure that abnormally large headers are not processed, then setting an appropriate DOSLimit to accommodate the expected size messages.

!!! Info "Information"
    The .NET interface only works with the Unicode edition of Dyalog; Classic edition is not supported.

When referring to keyboard shortcuts, such as those controlled by on Microsoft Windows, put the code in angle brackets. When referring to keyboard shortcuts, such as Windows controlled by ⎕KLong on Microsoft Windows, put the code in angle brackets. When referring to keyboard shortcuts, such as those controlled by on Microsoft Windows, put the code in angle brackets.

!!! Warning "Warning"
    The structure under the SALT directory must not be modified and the five sub-directories must not be renamed.

When referring to keyboard shortcuts, such as those controlled by on Microsoft Windows, put the code in angle brackets. When referring to keyboard shortcuts, such as Windows controlled by ⎕KLong on Microsoft Windows, put the code in angle brackets. When referring to keyboard shortcuts, such as those controlled by on Microsoft Windows, put the code in angle brackets.

When referring to keyboard shortcuts, such as those controlled by on Microsoft Windows, put the code in angle brackets. When referring to keyboard shortcuts, such as Windows controlled by ⎕KLong on Microsoft Windows, put the code in angle brackets. When referring to keyboard shortcuts, such as those controlled by on Microsoft Windows, put the code in angle brackets.

!!! Legacy "Legacy"
    Although .dyapp files are supported for backwards compatibility, Dyalog Ltd recommends launching the interpreter directly from any APL source or configuration file (functionality introduced with Dyalog version 18.0) rather than through the now-superseded .dyapp file mechanism.

When referring to keyboard shortcuts, such as those controlled by on Microsoft Windows, put the code in angle brackets. When referring to keyboard shortcuts, such as Windows controlled by ⎕KLong on Microsoft Windows, put the code in angle brackets. When referring to keyboard shortcuts, such as those controlled by on Microsoft Windows, put the code in angle brackets.

!!! linux "Dyalog on Linux"
    The MyUCMDs directory is located directly under the **$HOME** directory

When referring to keyboard shortcuts, such as those controlled by on Microsoft Windows, put the code in angle brackets. When referring to keyboard shortcuts, such as Windows controlled by ⎕KLong on Microsoft Windows, put the code in angle brackets. When referring to keyboard shortcuts, such as those controlled by on Microsoft Windows, put the code in angle brackets.

!!! note "Note"
    The MyUCMDs directory is located directly under the **$HOME** directory

### All together
!!! Hint "Hints and Recommendations"
    If both DOSLimit and BufferSize are set, then the smaller value applies. Dyalog Ltd recommends using a modest BufferSize and not setting EnableBufferSizeHttp to ensure that abnormally large headers are not processed, then setting an appropriate DOSLimit to accommodate the expected size messages.

!!! Info "Information"
    The .NET interface only works with the Unicode edition of Dyalog; Classic edition is not supported.

!!! Warning "Warning"
    The structure under the SALT directory must not be modified and the five sub-directories must not be renamed.

!!! Legacy "Legacy"
    Although .dyapp files are supported for backwards compatibility, Dyalog Ltd recommends launching the interpreter directly from any APL source or configuration file (functionality introduced with Dyalog version 18.0) rather than through the now-superseded .dyapp file mechanism.

!!! linux "Dyalog on Linux"
    The MyUCMDs directory is located directly under the **$HOME** directory

!!! note "Note"
    The MyUCMDs directory is located directly under the **$HOME** directory

## Keyboard
Sometimes it is relevant to include an icon. For example, when describing a combination of key presses. Sometimes it is relevant to include an icon. For example, when describing a combination of key presses. Sometimes it is <kbd>Enter</kbd> to include an icon. <kbd markdown="1">:material-apple-keyboard-command:</kbd> + <kbd>C</kbd> to copy text For example, when describing a combination of key presses. Sometimes it is relevant to include an icon. For example, when describing a combination of key presses. Sometimes it is relevant to include an icon. For example, when describing a combination of key presses.

The keyboard text Enter + C and icons :material-apple-keyboard-command: inline.

## Lists
This is some text:

- and a list
- second item
    - nested item
    - second nested item
        - doubly nested item
    - third nested item
- third ite

paragraph text paragraph text paragraph text paragraphparagraph text paragraph text paragraph text paragraphparagraph text paragraph text paragraph text paragraphparagraph text paragraph text paragraph text paragraphparagraph text paragraph text paragraph text paragraph

<ul>
<li>and a list</li>
<li>second item<ul>
<li>nested item</li>
<li>second nested item<ul>
<li>doubly nested item</li>
</ul>
</li>
<li>third nested item</li>
</ul>
</li>
<li>third ite</li>
</ul>

paragraph text paragraph text paragraph text paragraph text paragraph text paragraph text paragraph text paragraph text paragraph text paragraph text paragraph text paragraph text paragraph text paragraph text paragraph text paragraph text paragraph text 

1. first item
1. first item
    1. first item
    1. first item
1. first item
1. first item
    1. first item
        1. first item
            1. first item
        1. first item
        1. first item
    1. first item
1. first item

## Headings (2)
Here is some text Here is some text Here is some text Here is some text Here is some text Here is some text Here is some text Here is some text Here is some text Here is some text Here is some text Here is some text Here is some text Here is some text 

### Heading 3
Here is some text Here is some text Here is some text Here is some text Here is some text Here is some text Here is some text 

#### Heading 4
Here is some text Here is some text Here is some text Here is some text Here is some text Here is some text Here is some text Here is some text Here is some text Here is some text Here is some text Here is some text 

## Code Blocks
```apl
      ([(1 2 3) 'abc'
        3 4]
       [5 6
        7 8])
┌───────────┬───┐
│┌─────┬───┐│5 6│
││1 2 3│abc││7 8│
│├─────┼───┤│   │
││3    │4  ││   │
│└─────┴───┘│   │
└───────────┴───┘
```

```
this is just a plain code block with no particular language
```

```cs
class Program
{
  static void MyMethod() 
  {
    // code to be executed
  }
}
```

and some text

```nonAPL
This block is explicitly language-nonAPL.
class Program
{
  static void MyMethod() 
  {
    // code to be executed
  }
}
It has no highlighting, but renders as class="language-text" or "language-nonAPL" depending on the renderer.
```

```python
function python(args):
    return stuff
```

```text
this is a text one
```

```ial4oijf
this is some garbage
```

Default to `APL (+⌿÷≢)` for inline code. This sentence has some <code class="language-nonAPL">inline non-APL code</code> in a line.

And what about a pre?

<pre><code class="language-nonAPL">
# this is supposed to be nonAPL

function foo {
    main
}
</code></pre>

## Table
Table: Cells with content with content with content with content with content { #experiments-table-1 }

| heading 1 | heading 2 | 
| --------- | --------- | 
| content 1 | content 2 |
| content 3 | content 4 | 