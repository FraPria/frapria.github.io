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

togli l'elenco puntito nei tag <li>

# Non ho ancora provato
https://jekyllcodex.org/without-plugin/image-gallery/#