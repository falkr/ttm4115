



---
type: nav
prev: ["All extensions", "extensions.html"]
---





# Extension figure

Include figures and images.

Figures are included by referring to their file.
The source attribute refers to the image file, relative to the page. 
Usually it is a good idea to collect all images of a page or group of page in one folder, like shown below. 
Files are copied during the build process.

:tree:
- site/
    - pages/
        - index.md
        - hello.md
        - unit-1/
            - figures/
                - image.png
            - index.md
            - preparation.md

Formats can be `jpg`, `png`, `pdf`. 

Captions are recommended.


<table class="table"></table>




<table class="table"><tbody><td>Python type</td><td>Figure</td>
<tr></tr>
<td>type</td><td>figure</td>
<tr></tr>
<td>Language</td><td><a href="#">YAML</a></td>
<tr></tr>
<td>Required fields</td><td>source</td>
<tr></tr>
<td>Optional fields</td><td>caption, link</td>
<tr></tr>
<td>Post-Yaml Section</td><td>no</td>
<tr></tr></tbody></table>






# Example 1

---
type: figure
source: _placeholder 800 x 200
caption: "The TCP protocol uses state machines to describe parts of its behavior."
---






## Source Code

```yaml
---
type: figure
source: _placeholder 800 x 200
caption: "The TCP protocol uses state machines to describe parts of its behavior."
---
```



