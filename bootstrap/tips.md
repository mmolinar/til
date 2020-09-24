## Images
### img-fluid
In Internet Explorer 10, SVG images with .img-fluid are disproportionately sized. To fix this, add width: 100% \9; where necessary. This fix improperly sizes other image formats, so Bootstrap doesn’t apply it automatically.

### mx-auto d-block 
Align images with the helper float classes or text alignment classes. block-level images can be centered using the .mx-auto margin utility class.

### float-left (.float-right)
To make the image elements float to either side

## Media
### d-flex
Flexbug #12: Inline elements aren’t treated as flex items
Internet Explorer 10-11 do not render inline elements like links or images (or ::before and ::after pseudo-elements) as flex items. The only workaround is to set a non-inline display value (e.g., block, inline-block, or flex). We suggest using .d-flex, one of our display utilities, as an easy fix.

## Navbar
### navbar-expand-lg (md or sm)
Here’s an example of all the sub-components included in a responsive light-themed navbar that automatically collapses at the lg (large) breakpoint.
```
<nav class="navbar navbar-expand-lg navbar-light bg-light">>
```
