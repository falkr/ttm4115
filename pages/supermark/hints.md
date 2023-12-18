



---
type: nav
prev: ["All extensions", "extensions.html"]
---





# Extension hints

Hints are boxes with information that is only visible when the reader clicks on the header.

The top of the hint is specified with a YAML section. 
The content of the hint is provided as post-YAML section, directly following the YAML header.
It ends after two consecutive empty lines.
<table class="table"></table>




<table class="table"><tbody><td>Python type</td><td>Hint</td>
<tr></tr>
<td>type</td><td>hint</td>
<tr></tr>
<td>Language</td><td><a href="#">YAML</a></td>
<tr></tr>
<td>Required fields</td><td></td>
<tr></tr>
<td>Optional fields</td><td>title, image</td>
<tr></tr>
<td>Post-Yaml Section</td><td>optional</td>
<tr></tr></tbody></table>






# Example 1

---
type: hint
title: Hint about Something
---
Within the content you can have lists:

* 10.0.0.0/8
* 172.16.0.0/12
* 192.168.0.0/16






## Source Code

```yaml
---
type: hint
title: Hint about Something
---
Within the content you can have lists:

* 10.0.0.0/8
* 172.16.0.0/12
* 192.168.0.0/16
```






# Example 2

---
type: hint
title: Hint about Something
image: hint.png
---






## Source Code

```yaml
---
type: hint
title: Hint about Something
image: hint.png
---
```



