# Corner ribbon

Attention-seeking ribbons for when generic horizontal titles just aren't enough

<img width="381" alt="screen shot 2018-10-13 at 18 59 36" src="https://user-images.githubusercontent.com/9323190/46904663-80b14280-cf1a-11e8-9184-fba709bbc388.png">

```html
<span class="corner-ribbon-container corner-ribbon-container--loose">
  <span class="corner-ribbon corner-ribbon--dark">
    Look at my ribbons!
  </span>
</span>
```


## Install

## Usage

Use the `css/corner-ribbons.css` file directly for instant, garish red (`--dark`) and yellow (`--light`) ribbons

Or, better still, set the `$corner-ribbon-x` variables to your hearts' desire and then run

```sass
@import "path/to/tools/_print-all-ribbon-styles";

$corner-ribbon-colors: (
  light: (
    color: black,
    background-color: yellow,
    hover-background-color: orange,
    shadow-color: darkorange,
  ),

  dark: (
    color: white,
    background-color: blue,
    hover-background-color: darkblue,
    shadow-color: navy,
  ),
);

@include print-all-ribbon-styles;
```

## Customisation

### Colours
`$corner-ribbon-colors`

This accepts an object which describes all of the colours of ribbon you'll want to use in your app.

For example, if you only have one ribbon colour:
```sass
$corner-ribbon-colors: (
  colour-class-suffix: (
    color: $color,
    background-color: $background-color,
    hover-background-color: $hover-background-color,
    shadow-color: $shadow-color,
  ),
);
```

`colour-class-suffix` is the secondary class you would use on your ribbon in the HTML.  
ie. `<span class="corner-ribbon corner-ribbon--dark">`
 - `color` is the text colour of the ribbon
 - `background-color` the base background colour of the ribbon
 - `hover-background-color` the background colour of the ribbon when hovered - ignored if `$corner-ribbon-change-background-on-hover` is false
 - `shadow-color` the background colour of ribbon folds

## License

Copyright © 2018 [Brook Jordan](https://brookjordan.co.uk/)
Licensed under the [MIT license](http://www.opensource.org/licenses/MIT).
