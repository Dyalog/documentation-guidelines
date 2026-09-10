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

When there is no other natural order, list the rows of a reference table in alphabetical order. Every row must earn its place, and every column must carry meaningful content for that row; do not list an item (for example, a deprecated facility) with no useful entry in a column. Use `&nbsp;` for a cell that is intentionally empty. Keep the wording of related rows parallel, for example, matching "enabled" and "disabled" descriptions.

Introduce a table with a sentence that says what it summarises. Where fuller detail follows the table, say so, for example, "each option is described in more detail below the table".

Keep terminal punctuation consistent across parallel cells, matching the neighbouring entries, and remove any stray trailing space at the end of a cell.

When a reference table mixes functions and operators, group all functions before all operators rather than interleaving them by another sort key.

Give a value table, such as a variant-option or flags table, a heading row, and mark the default value in its cell with `<small>(default)</small>`.

## Captions and References

To caption a table, add a line beginning with "Table&#58; " just before the table (separated from the table by a blank line), and assign an id using an attribute list. Write the caption in sentence case, capitalising only the first word and any proper nouns, for example, "Time numbers" or "Built-in languages":

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

Where a table documents one part of a larger thing, the caption names both, so that the caption identifies the table on its own. Write "Table: Configuration dialog box – General tab" rather than "Table: General", and where a tab is divided into panels, name the panel too, as in "Table: Configuration dialog box – Windows tab (Edit Windows panel)". Separate the container from the part with an en-dash.

To reference a table based on its id, insert a Markdown link to the id, with an empty anchor:

<pre>
As shown in [](#MyTable), yadda yadda.
</pre>

where the anchor text should be filled in by the extension:

As shown in [](#MyTable), yadda yadda.