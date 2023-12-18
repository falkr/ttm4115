



---
type: nav
prev: ["All extensions", "extensions.html"]
---





# Extension weekplan

A table that is suitable for creating weekplans.

The css styling automatically highlights the cells that are used to ensure good readability.
<table></table>




<table class="table"><tbody><td>Python type</td><td>Table</td>
<tr></tr>
<td>type</td><td>table/weekplan</td>
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
type: table/weekplan
format: html
---
{|
! Time
! Mon
! Tue
! Wed
! Thu
! Fri

|-
| 08:15
| 
| rowspan="4" | Team Activities 
|
|
|
|-
| 09:15
| RATs
|
|
|
|-
| 10:15
| 
|
|
|
|-
| 11:15
|
|
|
|
|-
| 12:15
|
|
|
|
|
|-
| 13:15
|
|
|
|
| Summary
|-
| 14:15
|
|
|
|
|
|-
| 15:15
|
|
|
|
|
|-
| 16:15
|
|
|
|
|
|}






## Source Code

```yaml
---
type: table/weekplan
format: html
---
{|
! Time
! Mon
! Tue
! Wed
! Thu
! Fri

|-
| 08:15
| 
| rowspan="4" | Team Activities 
|
|
|
|-
| 09:15
| RATs
|
|
|
|-
| 10:15
| 
|
|
|
|-
| 11:15
|
|
|
|
|-
| 12:15
|
|
|
|
|
|-
| 13:15
|
|
|
|
| Summary
|-
| 14:15
|
|
|
|
|
|-
| 15:15
|
|
|
|
|
|-
| 16:15
|
|
|
|
|
|}
```



