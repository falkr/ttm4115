



---
type: nav
prev: ["All extensions", "extensions.html"]
---





# Extension rubrics

Table style for rubrics.
<table></table>




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
---
{|
!
! Excellent
! Good
! Sufficient
! Not rateable
|-
| Layout
| Layout follows a strategy that helps to understand the diagram.
| Layout is structured.
| Layout is structured.
| Layout is unstructured and random.
|-
| Syntax
| Correct syntax.
| Correct Syntax.
| Overall good syntax, with a few minor errors.
| Major syntactical flaws.
|-
| Level of Detail
| Consistent and intentional level of detail.
| Adequate detailing.
| Some inconsistencies, too much focus on some details on the expense of others.
|
|}






## Source Code

```yaml
---
type: table
class: rubric
---
{|
!
! Excellent
! Good
! Sufficient
! Not rateable
|-
| Layout
| Layout follows a strategy that helps to understand the diagram.
| Layout is structured.
| Layout is structured.
| Layout is unstructured and random.
|-
| Syntax
| Correct syntax.
| Correct Syntax.
| Overall good syntax, with a few minor errors.
| Major syntactical flaws.
|-
| Level of Detail
| Consistent and intentional level of detail.
| Adequate detailing.
| Some inconsistencies, too much focus on some details on the expense of others.
|
|}
```



