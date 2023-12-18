



---
type: nav
prev: ["All extensions", "extensions.html"]
---





# Extension video

Include videos from Youtube by referring to the video ID.
<table class="table"></table>




<table class="table"><tbody><td>Python type</td><td>Video</td>
<tr></tr>
<td>type</td><td>youtube</td>
<tr></tr>
<td>Language</td><td><a href="#">YAML</a></td>
<tr></tr>
<td>Required fields</td><td>video</td>
<tr></tr>
<td>Optional fields</td><td>start, caption, position</td>
<tr></tr>
<td>Post-Yaml Section</td><td>no</td>
<tr></tr></tbody></table>






# Example 1

---
type: youtube
video: wupToqz1e2g
caption: "The Pale Blue Dot."
start: 80
---






## Source Code

```yaml
---
type: youtube
video: wupToqz1e2g
caption: "The Pale Blue Dot."
start: 80
---
```






# Example 2

---
type: youtube
video: wupToqz1e2g
caption: "The Pale Blue Dot."
start: 80
position: aside
---






## Source Code

```yaml
---
type: youtube
video: wupToqz1e2g
caption: "The Pale Blue Dot."
start: 80
position: aside
---
```



