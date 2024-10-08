# CSS

CSS, or [Cascading Style Sheets](https://en.wikipedia.org/wiki/CSS), define the presentation layer of a website. Our aim at Dyalog is that as a documentation contributor, you should not need to get your hands dirty at this level. Moreover, any CSS changes need to be discussed as a wider group, as there are more aspects (beyond MkDocs) to the documentation build pipeline that rely on the CSS, like the CHM and PDF versions of the documentation. CSS that you write is not automatically picked up (paged media CSS is very different).

## Dyalog MkDocs CSS

The CSS defining the Dyalog-specific customisations are found in the locations specified in the `mkdocs.yml` file. Typically, that means `docs/style`. In there, you'll see two files of interest:

1. **main.css**
2. **extra.css**

These are not mandated by MkDocs, but any CSS files found in the directories specified in the `mkdocs.yml` file will be included. Note, however, that there is a lot more CSS injected as part of the rendering pipeline, specific to the [MkDocs Material](https://github.com/squidfunk/mkdocs-material) theme, defining things like navigation panels etc. There _are_ ways to hook into that, but this is not something we should encourage.

As a "run of the mill" documentation contributor, you should rarely need to consider the CSS.