# Figures with Captions

!!! Info "Information"
    We use the [caption](https://github.com/tobiasah/mkdocs-caption#readme) plugin to automatically number and cross-reference figures and tables in Material for MkDocs.

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