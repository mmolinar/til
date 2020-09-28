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

### Dropdown menus
You may also utilize dropdowns in your navbar nav. Dropdown menus require a wrapping element for positioning, so be sure to use separate and nested elements for .nav-item and .nav-link as shown below. Otherwise you can avoid the <li> all together.
```
<div class="collapse navbar-collapse" id="navbarNavDropdown">
```
AND 
```
<li class="nav-item dropdown">
        <a class="nav-link dropdown-toggle" href="#" id="navbarDropdownMenuLink" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
          Dropdown link
        </a>
        <div class="dropdown-menu" aria-labelledby="navbarDropdownMenuLink">
          <a class="dropdown-item" href="#">Action</a>
          <a class="dropdown-item" href="#">Another action</a>
          <a class="dropdown-item" href="#">Something else here</a>
        </div>
      </li>
```
  
## Jumbotron (Hero)
To give the hero an image in the background.
```
.jumbotron-hero {
  /* Choisis la hauteur ici */
  height: 500px;

  /* Tu lui donnes une image de background */
  background-image: url("ton_image.jpg");

  /* Centre l'image et la met bien sur tous les écrans */
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}
```
