## Creation of the gallery

Follow these instructions:
https://github.com/alexivkin/Jekyll-Art-Gallery-Plugin

brew install libmagickwand libmagick
gem install rmagick exifr

Then follow also these instructions:
http://jekyllcodex.org/without-plugin/lightbox/ 
So download lightbox.jss and lightbox.css and put it in assets and add the two lines in _layouts/footer.html

<script type="text/javascript" src="/assets/js/lightbox.js"></script>
<link rel="stylesheet" href="/assets/css/lightbox.css">

add in Gemfile:
gem 'rmagick'

problem: I cannot give names to the pictures
it does not work in github pages 
https://github.com/ggreer/jekyll-gallery-generator/issues/20

togli l'elenco puntato nei tag <li>


## Tentativo 2
http://jekyllcodex.org/without-plugin/lightbox/#
Step 1. Download the file lightbox.js and lightbox.css
Step 2. Save the file in the ‘/js’ and ‘/css’ directory of your project
Step 3. Make sure the footer of your layout document looks like this:

...
<script type="text/javascript" src="/js/lightbox.js"></script>
<link rel="stylesheet" href="/css/lightbox.css">
</body>
</html>


https://jekyllcodex.org/without-plugin/image-gallery/#
Step 1. Download the file image-gallery.html
Step 2. Save the file in the ‘_includes’ directory of your project
Step 3. Add the following line to your layout on the place where you want the image gallery to appear:

{% include image-gallery.html folder="/uploads/album" %}


problem: broken images

## How to add highlighting
https://bnhr.xyz/2017/03/25/add-syntax-highlighting-to-your-jekyll-site-with-rouge.html

demo page to choose the right highlighting 
https://spsarolkar.github.io/rouge-theme-preview/


## gallery da provare

https://jekyllcodex.org/without-plugin/image-gallery/#

https://github.com/opieters/jekyll-image-gallery-example

https://github.com/gautamkrishnar/github-pages-gallery?tab=readme-ov-file

https://www.youtube.com/watch?v=uYh7b2V0pyA 


-------------
ChatGPT:

Hi, I have a personal website hosted by GitHub pages. I used Jekyll to build it. I would like to add a gallery for my photographies. How can I do? Without using plugins


Certainly! If you prefer not to use plugins, you can create a simple gallery manually using Jekyll and HTML. Here's an alternative approach:

Step 1: Organize Your Photos
Just like before, organize your photos in a specific folder within your Jekyll project (e.g., _photos).

Step 2: Create a Gallery Page
Create a new markdown file (e.g., gallery.md) in your _pages folder with the following content:

markdown
Copy code
---
layout: page
title: Photo Gallery
---

<h1>Photo Gallery</h1>

<div class="gallery">
  {% for photo in site.static_files %}
    {% if photo.path contains '/_photos/' %}
      <img src="{{ site.baseurl }}{{ photo.path }}" alt="{{ photo.name }}">
    {% endif %}
  {% endfor %}
</div>
Step 3: Style Your Gallery
Create a new CSS file (e.g., styles.css) in your _sass folder or in the root of your project. Add some basic styles for your gallery:

css
Copy code
/* _sass/styles.css */

.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 16px;
}

.gallery img {
  width: 100%;
  height: auto;
}
Step 4: Link the Stylesheet
In your _layouts/default.html file, link the stylesheet by adding the following line inside the <head> section:

html
Copy code
<head>
  <!-- other head elements -->
  <link rel="stylesheet" href="{{ site.baseurl }}/styles.css">
</head>
Step 5: Run Jekyll Locally
Run your Jekyll site locally:

bash
Copy code
bundle exec jekyll serve
Visit http://localhost:4000/gallery in your browser to see the preview of your photo gallery.

Step 6: Push Changes to GitHub
Commit and push your changes to GitHub:

bash
Copy code
git add .
git commit -m "Add photo gallery without plugins"
git push origin master
This method manually iterates through static files and includes images from the specified folder, creating a simple gallery without relying on external plugins. Adjust the styles and layout based on your preferences.