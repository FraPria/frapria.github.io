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

togli l'elenco puntito nei tag <li>

# Non ho ancora provato
https://jekyllcodex.org/without-plugin/image-gallery/#



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

## How to add highlightinh
https://bnhr.xyz/2017/03/25/add-syntax-highlighting-to-your-jekyll-site-with-rouge.html

demo page to choose the right highlighting 
https://spsarolkar.github.io/rouge-theme-preview/