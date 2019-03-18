# Open Sky Law Website 
A static site / blog created in HTML, CSS, Bootstrap, and Jekyll <br>
created by goeun park (contact: goeuntothepark@gmail.com) march 2019

## About the site 
A jekyll project consists of `_layout`, `_includes`, `assets`, and content files in markdown (e.g. `about.md`) which automatically renders the HTML code in the `_site` directory. The contents in `_site` should not be touched directly. The styling for the entire site is defined in `assets/style.css`. The informational content must be formatted in markdown, here's a [quick primer](https://guides.github.com/features/mastering-markdown/). Markdown supports HTML tags. 

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
Add images (e.g., flying_birds.jpg) directly in the `assets/images` folder. Images can be embedded via markdown: 
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
1. If you wish to keep the page but delete the page from the navigation bar, delete the appropriate `<li>` element in `_includes/header.html`. Deleting this would take out About from navigation: 
 
```
<li class="nav-item">
<a class="nav-link" href="about.html">About</a>
</li>
```
2. To delete the page entirely, remove the corresponding HTML file from `_layouts` and the markdown file from root directory.
  
## Documentation To-do 
- how to add documents (pdf, word files) 

