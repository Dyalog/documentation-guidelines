# Dyalog Documentation Style Guide

## To Do
- references in HTML vs. PDF
- consider linking to specific document versions in references to other documents

## Markdown and HTML
This document, and the documentation to which it refers, is written in Markdown.

Markdown is a markup language for formatting text documents. It is designed to be simple and legible even in raw form. For example, compare

```markdown
# My Heading
This is some **bold** text with [a link](#).
```

and

```HTML
<h1>My Heading</h1>
This is some <strong>bold</strong> text with <a href="#">a link</a>.
```

For more examples of markdown and equivalent HTML, see the [basic syntax page on markdownguide.org](https://www.markdownguide.org/basic-syntax/_).

Not only does Markdown render to HTML so that it can be viewed on any web browser, but you can also use HTML inside Markdown documents in order to apply custom styling with CSS or to create layouts which aren't possible with just Markdown.

In general, it is best to try and stick to just Markdown where possible because maintaining a set of custom CSS classes and styles can be cumbersome. Sometimes it is convenient to [include markdown inside HTML tags](./style.md#markdown-inside-html).

## Resources

* [MkDocs](https://www.mkdocs.org/)
* [MkDocs Material](https://squidfunk.github.io/mkdocs-material/) theme
* [Markdown extensions](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown/) available in Material
* [Attribute lists](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown/?h=attribute+lists#attribute-lists)
* [GitHub Flavored Markdown Spec](https://github.github.com/gfm/)
* [Extended Markdown tables](https://github.com/fumbles/tables_extended)
* [Captions](https://github.com/tobiasah/mkdocs-caption#readme)
