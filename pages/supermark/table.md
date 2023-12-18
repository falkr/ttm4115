



---
type: nav
prev: ["All extensions", "extensions.html"]
---





# Extension table

Tables in Wikimedia syntax.
The table in the file must use the [mediawiki syntax for tables](https://www.mediawiki.org/wiki/Help:Tables), with an example shown below.
The optional class attribute places a `<div>` element around the table for styling with the given class.

The optional format attribute allows to select the markup within the cells. Examples are html, markdown, wikimedia, latex.

A different way to include tables is to include HTML chunks with tables. 



```yaml
---
type: table
file: tables/table.mw
class: rubric
caption: "Table with a caption."
---
```

The file tables/table.mw contains the table:
```mediawiki
{|
|Orange
|Apple
|-
|Bread
|Pie
|-
|Butter
|Ice cream 
|}
```
<table class="table"></table>




<table class="table"><tbody><td>Python type</td><td>Table</td>
<tr></tr>
<td>type</td><td>table</td>
<tr></tr>
<td>Language</td><td><a href="#">YAML</a></td>
<tr></tr>
<td>Required fields</td><td></td>
<tr></tr>
<td>Optional fields</td><td>file, class, caption, format</td>
<tr></tr>
<td>Post-Yaml Section</td><td>required</td>
<tr></tr></tbody></table>






# Example 1

---
type: table
class: rubric
caption: "Table with a caption."
---
{|
|Orange
|Apple
|-
|Bread
|Pie
|-
|Butter
|Ice cream 
|}







## Source Code

```yaml
---
type: table
class: rubric
caption: "Table with a caption."
---
{|
|Orange
|Apple
|-
|Bread
|Pie
|-
|Butter
|Ice cream 
|}

```



