# Open Sky Law Website 
A static site / blog created in HTML, CSS, Bootstrap, and Jekyll <br>
created by goeun park (contact: goeuntothepark@gmail.com), march 2019

## About the site 
A jekyll project consists of `_layout`, `_includes`, `assets`, and content files in markdown (e.g. `about.md`) which automatically renders the HTML code in the `_site` directory. The contents in `_site` should not be touched directly. The styling for the entire site is defined in `assets/style.css`. The informational content must be formatted in markdown, here's a [quick primer](https://guides.github.com/features/mastering-markdown/). Markdown supports HTML tags. 

The logos in the navigation bar and footer are not images but vectors defined in `<svg>` tags. Vectors are great to work with because they don't pixelate when users zoom in, however, they are trickier to edit. The logos are saved in `_includes` as `logoname.html` and `footer_logoname.html` and starts off like this:
```
<?xml version="1.0" standalone="no"?><!-- Generator: Gravit.io --><svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" style="isolation:isolate" viewBox="0 130 316 50" width="200" height="35"><defs><clipPath id="_clipPath_rPeWnwEgeSq6Ly3oTIs2pukIIVkdJYSg"><rect width="315.866" height="180.134"/></clipPath></defs><g clip-path="url(#_clipPath_rPeWnwEgeSq6Ly3oTIs2pukIIVkdJYSg)"><clipPath id="_clipPath_hBTpHHWNOuOgMvcmQ8EqS7CUDQAZFI0i"><path d=" M 0 0 L 0 180.134 L 315.866 180.134 L 315.866 0 L 0 0 Z " fill="rgb(255,255,255)"/></clipPath> 
... followed by ~50 lines of <g> tags 
```
To edit the dimensions of the logo, make changes to the width and height variables of the viewBox (`viewBox="0 130 316 50" width="200" height="35"`) in the `<svg>` tag.

## Editing a page for written content 
Edits in content should be made in markdown files in the root directory (e.g., `about.md` refers to the About page). All markdown files start with a table like this: 
``` 
---
title: About Us
layout: about
---
```
This is part of the jekyll configuration and should not be deleted. 

## Embedding images 
Add images (e.g., flying_birds.jpg) directly in the `assets` folder. Images can be embedded via markdown: 
```
![This is the alt tag for folks who use screen readers to navigate the web. A short description like 'Photo of birds in the sky' will suffice.](flying_birds.jpg)
```

## Adding a page 
1. The navigation bar is defined in `_includes/header.html` as a HTML list `<li>`. Copy this format to create a new page (replace `new_page` with the name of your file):
```
<li class="nav-item">
<a class="nav-link" href="new_page.html">New Page</a>
</li>
```
2. In `_layouts`, create a file `new_page.html` and paste this template:
```
---
layout: default
---

<div class="content">
  {{content}}
</div>
```
3. In the root directory, create a file `new_page.md` and paste this template:
```
---
title: New Page
layout: new_page
---
```

## Deleting a page 
1. If you wish to keep the page but remove the link from the navigation bar, delete the appropriate `<li>` element in `_includes/header.html`. Deleting this would take out About from navigation: 
 
```
<li class="nav-item">
<a class="nav-link" href="about.html">About</a>
</li>
```
2. To delete the page entirely, remove the corresponding HTML file from `_layouts` and the markdown file from root directory.
  
## Team Page Styling 
The `team.md` file is in HTML, not Markdown due to the styling tags required in embedding photos. To add a new team member, copy this code: 
```
<div class="bio">
<img src="/assets/[BIO_IMAGE_FILE]" class="bio-photo" alt="Photo of [NAME]">
<h2> [NAME] </h2>
<p>
[BIO TEXT]
</p>
</div>
```
The `[BIO_IMAGE_FILE]` is the file name for the bio photo (must be 273x381px) added into the assets folder. `[NAME]` and `[BIO TEXT]` should be replaced with corresponding information. Every paragraph in the Bio should be wrapped in a paragaraph tag: `<p>This is a paragraph.</p><p>This is a new paragraph.</p>`

To add links to internal resources such as cv (ideally a pdf file), add the file to `assets` and link as follows: 

```
<a href="/assets/2019_CV_Neha.pdf">CV</a>
``` 
