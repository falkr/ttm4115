



---
type: nav
prev: ["All extensions", "extensions.html"]
---





# Extension coursetable

A table style for study plans.


### Legend


```css
.legend li::before {
  content:"";
  width: 16px;
  height: 16px;
  margin: 0.1rem 0.2rem 0.1rem 0.1rem;
  float: left;
  clear: both;
}
.legend li {
  font-size: 0.8rem;
  font-weight: 400;
  color: grey;
}
.e1::before {
  background-color: #cfdaf1;
  
}
.e1e::before {
  background: repeating-linear-gradient(
    45deg,
    #ffffff00,
    #ffffff00 10px,
    #ffffffCC 10px,
    #ffffffCC 20px
  ), #cfdaf1;
  border: 1px #cfdaf1 solid;
}
```

```html
<div class="container">
<div class="legend float-end">
  <ol class="list-inline">
    <li class="list-inline-item e1">e1</li>
    <li class="list-inline-item e2">e2</li>
    <li class="list-inline-item e3">e3</li>
    <li class="list-inline-item e4">e4</li>
    <li class="list-inline-item e1e">e1e</li>
    <li class="list-inline-item e2e">e2e</li>
    <li class="list-inline-item e3e">e3e</li>
    <li class="list-inline-item e4e">e4e</li>
  </ol>
</div>
</div>
```
<table></table>



