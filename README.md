# Corner ribbon

Attention-seeking ribbons for when generic, horizontal titles just aren't enough.

<img width="448" alt="screen shot 2018-10-13 at 20 17 16" src="https://user-images.githubusercontent.com/9323190/46905366-4a2cf500-cf25-11e8-8ee4-c11a5e7c8ae6.png">

```html
<span class="corner-ribbon-container">
  <span class="corner-ribbon">
    I'm a default ribbon!
  </span>
  
  <span class="corner-ribbon corner-ribbon--top-right">
    I'm up on the top right!
  </span>
</span>

<span class="corner-ribbon-container corner-ribbon-container--tight">
  <span class="corner-ribbon corner-ribbon--dark">
    I'm all dark and tight…
  </span>
</span>
```

Why 2 divs for this simple little ribbon, you ask?

Well, the first, containing span crops the corners off've the ribbons, making them look that awesome ribbony shape and not like big blocks clawing onto your container. That's why.

Notice that, because the container is the one controlling the cropping, you can have as many of the same tightness ribbons inside of a single container as you'd like! Neato… right? <sup>right? <sub>right?</sub></sup>

## Using your own colours in your own CSS files

Make sure the parent of the ribbons is `position: relative | absolute | fixed;`.

Use the `css/corner-ribbons.css` file directly for instant super-yellow and garish-red (`--dark`) ribbons.

Or, better still, set the `$corner-ribbon-x` variables to your hearts' desire and then use:

```sass
@import "path/to/tools/_print-all-ribbon-styles";

$corner-ribbon-colors: (
  default: (
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

I heard you came to us to fix your styles, not dirty up your beautiful HTML with our dirty, dirty classes. That's ok. we can help! <sub>…maybe <sup>…at least a little.</sup></sub>

You'll still need both of the elements, but at least you can change the base classes to better fit the rest of your code.

Try something like:

For example, if you only have one ribbon colour:
```sass
@import "path/to/tools/_print-all-ribbon-styles";

$corner-ribbon-ribbon-selector: "i";
$corner-ribbon-container-selector: "b";

@include print-all-ribbon-styles;
```

And you can cut your markup down to as little as:
```html
<b><i>Look at my ribbons!</i></b>
```
<sub><sup>But please don't, this is atrocious…</sup></sub>

### Alignment

You don't like your ribbons on the top left? Oh, come on.
… ok, fine. We'll allow you to move it to the top right.

Use this markup instead:
```html
<span class="corner-ribbon-container">
  <span class="corner-ribbon corner-ribbon--dark  corner-ribbon--top-right">
    Look at my ribbons!
  </span>
</span>
```

What's that you say?
Your ribbons are *mostly* top-right, so you don't want to type all of that?
Ok, cool, then revert your markup back to the default and add this variable to your sass:

```sass
@import "path/to/tools/_print-all-ribbon-styles";

$default-alignment: top-right;

@include print-all-ribbon-styles;
```

You what?
Your ribbons are *ALWAYS* top-right, so you don't even want to include the <sub><sup>(5 lines of)</sup></sub> CSS for the top left?
I'm still with ya! Do this instead:
```sass
@import "path/to/tools/_print-all-ribbon-styles";

@include print-ribbon-styles-for(top-right);
```

On the bottom, you say?
Well… do WE have a solution for you?!

… no. No is the answer there. If enough requests come in, I'll look into it, though!

### MHOAR OPTIONS!!!

Whoa! Ha… you're getting a little excited there… <sub>and just a tad scary… <sup>could you brush your teeth before you do that again, please?</sup></sub>

There actually ARE more options… but I'll let you find them for yourself as they're all quite edge case and, hopefully, quite easy to decipher.

Look through the files in `scss/settings` and you should be flying.

## License

Copyright © 2018 [Brook Jordan](https://brookjordan.co.uk/)
Licensed under the [MIT license](http://www.opensource.org/licenses/MIT).
