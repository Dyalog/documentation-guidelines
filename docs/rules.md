# Rules for Writing Documentation

## Language

The documentation uses U.K. English for spellings and grammar.

Abbreviations should not be used (for example, shouldn't, can't, won't) and neither should emoticons.

Address the reader as "you". Do not write in the first person: "you will see later that ..." rather than "we shall see later that ...".

Describe behaviour in the present tense: "clicking the column heading sorts the list", not "will sort the list". The future tense is acceptable where it reads more naturally, or where it is genuinely about something that happens later.

Although the documents are not currently translated, they should be written as if they could be. That means consideration of the language used...can it be understood and translated unambiguously? For example, "configure" should be used rather than "set up" as "set up" can be misunderstood. This might sound silly, but translation is not always done in context, and people can put single words into Google Translate (for example) and get random results! Idioms, colloquialisms, and foreign expressions (including Latin) should also be avoided; for example, use "exactly" or "precisely" rather than the Latin "verbatim".

Language style will vary between documents. For example, the Language Reference Guide needs to be very precise and official whereas a User Guide can include less formal statements such as "You might notice that...".

Do **not** use an apostrophe when pluralising an acronym ("CPU's today are..." = WRONG)

Try to make documents future-proof (especially with respect to dates/version numbers, "coming soon", and so on). Variables can help with this!

Write so that a sentence cannot be misread. Avoid "so" when you mean "therefore", which is ambiguous; use "therefore", "meaning that", or another unambiguous connective. Set connectives such as "therefore" and "that is" off with commas, for example, "the setting is, therefore, still in effect".

Gloss a short code or abbreviation the first time it is shown, for example, "if `Format` is `'D'` (which stands for *Data*)".

Use the Oxford (serial) comma before the final item in a list of three or more items, for example, "the major release, minor release, and build number". Do not put a comma before "and" (or "or") when it joins only two items; the serial comma is only for lists of three or more.

Keep the phrasing of parallel items consistent: entries in a list, rows in a table, or the descriptions of two related things should share the same structure and wording so the reader can compare them easily.

When documenting an interface, present its parts in the order the software presents them. Sections describing the tabs of a dialog box follow the tab order, and rows describing the fields of a tab follow the order of the fields. A reader working through the dialog box should be able to work down the page in step with it.

When you change or move documentation of an interface, check that every cross-reference into it still names something that exists. A reference to a field that has since been renamed or removed is worse than no reference, because it sends the reader looking for something that is not there.

State what is true now, not how it came to be. Prefer "X is also known as Y" to "X was previously (or formerly) called Y". The one exception is when history explains why current behaviour departs from a standard; there a brief note is warranted, for example, "in its initial implementation Dyalog evaluated this left-to-right because ...".

Use "that" to introduce a restrictive clause and "which" for a non-restrictive one; use "if" for a condition and "whether" for a choice between alternatives. Prefer "when" for a situation that will occur and "if" for a genuine condition; avoid "where" for either.

Do not use "for example" and "and so on" in the same list: give a few examples or trail off with "and so on", but not both.

Do not open a sentence with an ambiguous "It ..."; start with "This ..." or the specific noun so the subject is clear.

Do not use minimising filler such as "simply", "just", or "merely"; state the step plainly. Drop "actually" and "in fact" where the sentence already carries the contrast, for example, in "however, the event is actually reported by each page".

Write "whether" rather than "whether or not"; keep "or not" only where both values are given, as in "whether (`1`) or not (`0`)".

Do not preface a sentence with "Note that" or "Note also that", nor say "in order to" where "to" suffices; state the point directly.

Do not use capitalisation for emphasis: write "only", not "ONLY".

Set an introductory subordinate clause off with a comma, for example, "If `Ragged` is not set, then ...", "..., even if ...", and open a consequence with "Similarly, ...".

## Terminology

The following table lists correct terminology and terms to avoid. A complete list of the [approved names for glyphs and primitive functions/operators](https://docs.dyalog.com/latest/CheatSheet%20-%20Nomenclature%20-%20Functions%20and%20Operators.pdf) is also available.

**NOTE:** Although these terms are the correct ones to use, the documentation must always reflect the software. For example, if a field in the software uses "pdf" then the documentation should also use "pdf" when referring to that field content; the software usage always takes precedence.

|**Use**|**Avoid**|
|---|---|
|large-span file|64-bit file|
|small-span file|32-bit file|
|Dyalog (referring to the product)|Dyalog APL|
|Dyalog Ltd (referring to the company)|Dyalog|
|PDF|pdf|
|.NET|.Net, .net, any other variation|
|dfn (Dfn when starting a sentence)|dynamic function, d-fn, D-fn, Dfn (unless starting a sentence)|
|dop (Dop when starting a sentence)|dynamic operator, d-op, D-op|
|dialog box|dialog (as a noun)|
|Edit window (a window); the Editor (the tool)|Edit Window|
|Trace window (a window); the Debugger (the tool, docked in Standard mode)|Trace Window, Tracer|
|for example|eg, e.g., eg.|
|that is|ie, i.e., ie.|
|note|NB, N.B.|
|and so on|etc, etc., and so forth|
|Boolean|boolean|
|Unix|UNIX, unix|
|configuration parameter|environment variable|
|32-bit width, 64-bit width (of the interpreter)|32-bit, 64-bit (as a noun)|
|curly braces `{ }`|curly brackets|
|round parentheses `( )`|round brackets|
|square brackets `[ ]`|square braces|

"Editor" and "Debugger" name the tools; "Edit window" and "Trace window" name individual windows. Use "Session window" when you mean the window; bare "Session" is ambiguous, as it can also mean the session file, the session object (`⎕SE`), or the running interpreter. When introducing a configuration parameter, use the full term "configuration parameter", not just "parameter". Link a configuration parameter inline to its own page (for example, `configuration-parameters/cfext/`), not to the general configuration-parameters page.

Write a version with a lower-case "v", for example, "v19.0", not "V19.0".

"System function" is the umbrella term: use it even for the sub-categories, as a system variable or system constant is still a system function; this keeps the documentation consistent.

Write "variant operator" and "variant option" in lower case (capitalised only at the start of a sentence), and italicise the operator itself as the _variant_ operator. Refer to an option as a "variant option", not a bare "variant".

Name a context specifically: avoid the vague "In APL" and write, for example, "In the Session".

  
Best practice:

|**Use**|**Avoid**|
|---|---|
|can, might|may|
|want|wish|

## Dyalog-specific Terms

"Dyalog":

- Dyalog = the product
- Dyalog APL = the language
- Dyalog Ltd = the company

Name a version as "Dyalog v" followed by the number, for example, "Dyalog v20.0" or "from Dyalog v14.1 onwards". Do not write "Version 14.1" alone, and do not write "Dyalog APL version 20.0", which names the language where the product is meant.

Syntax:

- System functions should be written in upper case, for example, ⎕OFF
- System commands should be written in upper case, for example, )CLEAR
- User commands should be written in upper camel case, with user command groups wtirren in upper case, for example, ]LINK.GetItemName
- Configuration parameters should be written in upper case if cross-platform; some of them are written in mixed case on Microsoft Windows, although this not case sensitive so upper case works there too. See the appropriate _Dyalog for `<operating system>` Installation and Configuration Guide_ for operating-system-specific casing if you're documenting a configuration parameter on a particular platform.

## Acronyms

Industry-standard abbreviations and acronyms can be used without explanation, for example, HTTP or XML.

When you use an acronym that is not an industry standard for the first time, write the full word or phrase in its entirety and then enclose its abbreviation or acronym in parentheses. Afterwards, use the abbreviation or acronym alone. For example, "...the Dyalog Remote Communicator (DRC). The DRC can be...". When you expand an acronym, capitalise the letters that form it to show its origin, for example, "Globally Unique IDentifier (GUID)".

## Ordinal Numbers

**NOTE:** The documentation, like the default Dyalog Session, uses an index origin of 1.

Ordinal numbers:

- should have postscripts rather than superscripts as superscripts can be hard to read, for example, 3rd.
- should be written as numbers rather than words when referring to something that is 11 or greater OR that is in a list, for example, "the 75th element in the vector" or "the 4th line of code"
- should be written as words rather than numbers when referring to something that is 10 or smaller AND not part of a list, for example, "the first time you do this" or "on the sixth day".

If an algebraic term is being used instead of the number, then it should be italicised to distinguish it from the postscript, for example, "the _i_th term" or "the _n_th time".

## Imaginary Numbers

The imaginary part should be prefixed with a capital letter J (that is how the session returns it), for example, 0J4.

## Lists

Lists can ordered or unordered. You should:

- use an ordered (numbered) list when the order in which steps are taken is important.
- use an unordered (bulleted) list when the order does not matter.

Lists can be nested to a depth of three.

Use full stops for your list items if they complete a sentence (in this situation the list items should start with lower case letters), otherwise leave them without a full stop. In all ordered lists and most unordered lists, full stops will usually be appropriate.

A list is not a single sentence split across its items. Where the items share a common logic, state it once in the lead-in line (or an admonition) above the list and let each item stand alone, rather than stringing the items together with connective phrases or trailing semicolons. For example, introduce a precedence order with "Each source overrides those below it:" and then list the bare source names.

Do not use a numbered list where the numbering could imply an order or precedence that does not exist; use a bulleted list. If the numbers are genuinely part of each item's name, fold them into the item text and keep the list bulleted.

## Third-party Products

Legally, the owner of the product ought to be included the first time that a product is mentioned - this applies to every paragraph. For example, when writing about something that's on the Windows system, "Microsoft Windows" must be used the first time in the paragraph and just "Windows" can be used after that. However, if Windows is referred to in the subsequent paragraph, it needs to be "Microsoft Windows" again.

Write "Unix", not "UNIX", when referring generically to non-Windows systems: "UNIX" is a trademark and names the certified operating system rather than the family. Product names keep their own spelling, so AIX remains "AIX". "Unix" already covers macOS and Linux, so write "Unix" alone rather than "Unix and macOS" or "UNIX/macOS"; name macOS separately only where its behaviour differs, in which case it takes its own `macos` admonition.

## Describing Parameters and Values

State a parameter's default value inline, in parentheses, for example, "(default)". In a table's value column, mark it as `<small>(default)</small>`.

A configuration parameter's page carries as many of these blocks as apply, in this order: any restriction on when the parameter is relevant; the description, linking the system functions, parameters, and concepts it mentions; the valid values; the default; and links to related parameters. Open the description with "Whether ..." for a Boolean parameter and "The ..." for one that names a path or a value, rather than "This parameter specifies ...".

Write "The default is `X`", not "If unset, the default is `X`": a default is by definition what applies when the parameter is not set, so the condition adds nothing.

Give a default that differs between operating systems for each one, and never state one platform's default as though it were universal. Before documenting a parameter in a platform's guide, confirm that it applies on that platform at all; a parameter that only has an effect on some platforms is documented in those guides and not the others.

Describe a Boolean parameter with a parallel "whether ... or not" phrase that gives both values and marks the default, for example, "specifies whether (`1`) or not (`0`, default) to enable multi-line input". Where it helps, add a sentence explaining what the default means, for example, "the default is `1`, meaning that multi-line input is enabled".

Set argument, option, and result *values* in code wherever they appear, not only the names: "`0` if the object is not an operator", "if `X` is `1`", "always reported as `0`". Counts and quantities stay plain: "0 or more names", "a 4-element vector". Where a table cell lists the alternative values of one element, separate them with commas rather than running them together.

When a system function is documented as two pages, one per form, each page reaches the other through an organic link on the form itself ("the [dyadic form](x-dyadic.md) closely emulates APL2"), not through a trailing "for the other form, see ...". The disambiguation page opens with a single sentence on what the function does, common to both forms, before naming either.

Introduce a function's arguments and result with consistent lead phrasing, for example, "`Y` is specified as either a character vector or a vector of character vectors", "The result `R` is a two-element vector consisting of ...", or "`X` must be omitted". Argument and result names (`X`, `Y`, `R`) are set in code spans wherever they appear, in prose as well as in code.

Where an argument or option takes a set of values, list them as "value – meaning" pairs (en-dash) and mark the default inline, for example:

- `0` – sub-directories are not scanned (default).
- `1` – sub-directories are scanned.

### Variant Options

A system function's variant options are documented under a "Variant Options" H2, with each option as an H3 named "Variant Option: `<Name>`". Set option names and their values in code font (`Wildcard`, `0`), open each with "The `<Name>` variant option ...", state the value constraints, and end with "The default is `<value>`." (state it plainly, not as "... if not specified"). Name the principal option explicitly ("The principal option is `Wildcard`"); if there is none, write "There is no principal option". State an absent option's assumed value, for example, "if `Unique` is not present, it is assumed to be `0`". 

Open the H2 with an introductory line that is consistent across all the system-function pages: name the _variant_ operator, list the options (in code font, with a serial comma), and link to a captioned summarising table by an empty cross-reference, for example, "`⎕FCHK` supports three variant options, `Task`, `Repair`, and `Force`, specified using the _variant_ operator [`⍠`](#), summarised in [](#variantoptionsforfchk), and described in detail beneath it. The principal option is `Repair`." Give that table a caption, "Table: Variant options for `⎕FCHK` { #variantoptionsforfchk }". When several options share one H3, the heading stays singular: "Variant Option: `A`, `B`, and `C`".

## Deprecations

Describe a deprecated feature consistently:

- state that it has been deprecated and is scheduled for removal in a future release;
- do not date the deprecation with a version (avoid "from Version 16.0"); state what is true now;
- name the replacement (or the configuration parameter that reinstates the previous behaviour) and link to it;
- link to the relevant _Release Notes_ for guidance on identifying the deprecated usage in existing code.

For example: "`739⌶` has been deprecated and is scheduled for removal in a future release. Its functionality is now provided by [`⎕SYSTEM.Directories.Temp`](#)."

A feature that still works but is superseded is different from a deprecated one: describe it with the fixed phrase "retained for backwards compatibility purposes" and, where it is an aside, present it in a `!!! Legacy "Legacy"` admonition.

## Notes

Various icons are used in the documentation to emphasise specific material. Notes are also used to differentiate between operating-system-specific behaviour in cross-platform documents. See [Notes](./style.md#notes).

Do not overuse notes. Only use an admonition when the content is a genuine aside (a hint, a warning, a piece of information set apart from the main flow). Content that belongs in the main narrative should be written as an ordinary paragraph, not wrapped in an admonition. In particular, do not use a Warning for a condition that merely raises an error message (for example, giving a name in the wrong case); write it as an ordinary sentence.

## Links

When linking within a sub-site (from one page to another in the same guide, for example, within the _Language Reference Guide_), reference the target file by its path including the `.md` extension, for example, `[Notes](../primitive-functions/notes.md)`. This form is always safe: the file is resolved and rewritten to the correct URL.

When linking between sub-sites (from one guide to another), use the extension-less directory form, for example, `[⎕SIGNAL](../../language-reference-guide/system-functions/signal/)`.

Using the file form for sub-site-internal links and the directory form for cross-sub-site links gives a useful practical distinction: the presence of a `.md` extension shows at a glance whether a link stays within the current guide.

Punctuation that belongs to the sentence goes outside the link text, not inside it. Write "[Chromium Embedded Framework (CEF)](https://example.com)." rather than "[Chromium Embedded Framework (CEF).](https://example.com)". Link only the words that name the target, so a trailing full stop, comma, or closing bracket stays unlinked.

## Miscellaneous

Full stops should be followed by a single space, not a double space. Do not put a space before a full stop or comma, including immediately after a code span.

When using a dash in a sentence, use an en-dash not a hyphen. Write a numeric range with an unspaced en-dash, for example, "1–2147483647".

Separate paragraphs with a single blank line. Do not leave two or more consecutive blank lines, as it makes the source messy.

Number footnotes in the order in which they are first referenced on the page. Better still, avoid footnotes: put essential information in the text and cut the rest.

Refer to files supplied under the installation directory using the `[DYALOG]` placeholder, for example, **[DYALOG]/ws/dfns.dws**.

Make sure visible (rendered) parentheses are balanced.

## Contributing

- Associate every pull request with an issue.
- Name a branch after the issue it addresses, as `<issue-id>-slug`.
- Close the issue from the merge message (`Closes #N`), not from a commit message.

## Libraries: Operating System Differences

- Microsoft Windows: Dynamic Link Library (.dll)
- Linux or macOS: Shared library (.so or .dylib)
- AIX: Static library (.a)
