# Tables

!!! note "Tables are not standard Markdown"
    Tables were not part of the original Markdown specification, but was popularised by the widely used [GitHub-Flavoured Markdown](https://github.github.com/gfm/) (GFM) dialect. 
    
GFM table syntax only allows for the most basic of tables. To remedy this, we use the [Tables-Extended](https://github.com/fumbles/tables_extended) Markdown extension to allow for more elaborate tables, and the [caption](https://github.com/tobiasah/mkdocs-caption#readme) plugin for captions, automatic numbering and references.

In its most basic form, a GFM table must have a header row:

```other
| heading 1 | heading 2 | 
| --------- | --------- | 
| content 1 | content 2 |
| content 3 | content 4 | 
```

which renders as:

| heading 1 | heading 2 | 
| --------- | --------- | 
| content 1 | content 2 |
| content 3 | content 4 | 

With the extension, we can make headerless tables in a natural way:

```other
| --------- | --------- | 
| content 1 | content 2 |
| content 3 | content 4 | 
```

which renders as:

| --------- | --------- | 
| content 1 | content 2 |
| content 3 | content 4 | 

You can also create row-, and col-spans with easily accessible syntax. See the [Tables-Extended](https://github.com/fumbles/tables_extended) documentation for details. 

!!! note "Tables are for data, not layout"
    Tables should be used for data, not document structure or layout. Unless you have a good reason not to, do name your columns. Complex tables are hard to read on a screen. If you find yourself reaching for more complex table layouts, consider if there are better ways to present the information.

## Captions and References

To caption a table, add a line beginning with "Table: " just before the table, and assign an id using an attribute list:

<pre>
Table&#58; Cells with content { #MyTable }

| heading 1 | heading 2 | 
| --------- | --------- | 
| content 1 | content 2 |
| content 3 | content 4 | 
</pre>

which should render as:

Table: Cells with content { #MyTable }

| heading 1 | heading 2 | 
| --------- | --------- | 
| content 1 | content 2 |
| content 3 | content 4 | 

You, the author, are responsible for choosing a unique table id (the `#MyTable` in this case) which is unique and appropriate for the table.

To reference a table based on its id, insert a Markdown link to the id, with an empty anchor:

<pre>
As shown in [](#MyTable), yadda yadda.
</pre>

where the anchor text should be filled in by the extension:

As shown in [](#MyTable), yadda yadda.