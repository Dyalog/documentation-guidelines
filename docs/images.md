# Figures with Captions

!!! Info "Information"
    We use the [caption](https://github.com/tobiasah/mkdocs-caption#readme) plugin to automatically number and cross-reference figures and tables in Material for MkDocs.

## When to Use an Image

Prefer describing UI layout and behaviour in prose. A screenshot carries a maintenance overhead and dates quickly, so include an image only when it conveys something text cannot, such as an icon. Remove images that merely show a menu or window layout, that duplicate describable content, or that are not referenced by the document, and delete the unused image files. Crop or size a screenshot so the relevant content fills the frame rather than being lost in whitespace.

Keep a set of related diagrams, on a page and across sibling pages, in one consistent visual style; if one is redrawn, match the others to it. Order a set of diagrams to match the order of the list or paragraph that introduces them.

## Adding an Image

The Markdown way to add an image is a Markdown link preceded by an exclamation mark:

```other
![alt text here](image url)
```

By using the [attribute list](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown/#attribute-lists) syntax we can add CSS classes, id, attributes etc, without resorting to HTML.

```other
![caption text here](image url){ width=300px #MyImgId }
```

Here is an example:

```other
![An elephant at sunset](https://interactive-examples.mdn.mozilla.net/media/cc0-images/elephant-660-480.jpg){ width=300px #MyElephant}
```

![An elephant at sunset](https://interactive-examples.mdn.mozilla.net/media/cc0-images/elephant-660-480.jpg){ width=300px #MyElephant}

Like with [tables](tables.md), we reference the image by its id by an "empty" link:

```
The beautiful specimen in [](#MyElephant) is a bull with the name of Kevin.
```

The beautiful specimen in [](#MyElephant) is a bull with the name of Kevin.