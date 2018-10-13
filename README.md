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

Often you won't want to use bright yellow and medium blue banners. (We get it. Managers can be super uptight about branding an all that. It's cool, we've got ya back!)

This accepts an object which describes all the colours of ribbon you'll want to use in your app.

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
ie. `<span class="corner-ribbon corner-ribbon--colour-class-suffix">`
 - `color` is the text colour of the ribbon
 - `background-color` the base background colour of the ribbon
 - `hover-background-color` the background colour of the ribbon when hovered - ignored if `$corner-ribbon-change-background-on-hover` is false
 - `shadow-color` the background colour of ribbon folds
 

### Selectors
`$corner-ribbon-ribbon-selector`  
`$corner-ribbon-container-selector`

I heard you came to us to fix your styles, not to make you change-up your HTML? That's ok, we can… maybe help a little bit.
You'll still need both of the elements, but at least you can change the base classes to better fit the rest of your code.

Try something like:

For example, if you only have one ribbon colour:
```sass
@import "path/to/tools/_print-all-ribbon-styles";

$corner-ribbon-ribbon-selector: ".r";
$corner-ribbon-container-selector: ".c";

@include print-all-ribbon-styles;
```

And you've cut your markup down to:
```html
<span class="c">
  <span class="r r--dark">
    Look at my ribbons!
  </span>
</span>
```

In future I'm looking to even remove the `--dark`!
Stay tuned.x

## License

Copyright © 2018 [Brook Jordan](https://brookjordan.co.uk/)
Licensed under the [MIT license](http://www.opensource.org/licenses/MIT).
