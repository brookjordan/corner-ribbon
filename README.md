# Corner label
<code><sup>from 360 bytes <sub>minified & gzipped</sub></sup></code>

Attention-seeking labels for when generic, horizontal titles just aren't enough.

<img width="448" alt="screen shot 2018-10-13 at 20 17 16" src="https://user-images.githubusercontent.com/9323190/46905366-4a2cf500-cf25-11e8-8ee4-c11a5e7c8ae6.png">

```html
<span class="corner-label-container">
  <span class="corner-label">
    I'm a default label!
  </span>

  <span class="corner-label corner-label--top-right">
    I'm up on the top right!
  </span>
</span>

<span class="corner-label-container corner-label-container--tight">
  <span class="corner-label corner-label--dark">
    I'm all dark and tight…
  </span>
</span>
```

Why 2 divs for this simple little label, you ask?

Well, the first, containing span crops the corners off've the labels, making them look that awesome labely shape and not like big blocks clawing onto your container. That's why.

Notice that, because the container is the one controlling the cropping, you can have as many of the same tightness labels inside of a single container as you'd like! Neato… right? <sup>right? <sub>right?</sub></sup>

## Using your own colours in your own CSS files

Make sure the parent of the labels is `position: relative | absolute | fixed;`.

Use the `css/corner-labels.css` file directly for instant super-yellow and garish-red (`--dark`) labels.

Or, better still, set the `$corner-label-x` variables to your hearts' desire and then use:

```scss
@use "path/to/settings/colors" with (
  $themes: (
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
  ),
);
@use "path/to/tools/label-styles";

@include label-styles.all;
```

## Customisation

### Colours
`$themes`

Often you won't want to use bright yellow and medium blue banners. (We get it. Managers can be super uptight about branding an all that. It's cool, we've got ya back!)

This accepts an object which describes all the colours of label you'll want to use in your app.

For example, if you only have one label colour:
```scss
@use "path/to/settings/colors" with (
  $themes: (
    colour-class-suffix: (
      color: $color,
      background-color: $background-color,
      hover-background-color: $hover-background-color,
      shadow-color: $shadow-color,
    ),
  ),
);
@use "path/to/tools/label-styles";

@include label-styles.all;
```

`colour-class-suffix` is the secondary class you would use on your label in the HTML.
ie. `<span class="corner-label corner-label--colour-class-suffix">`
 - `color` is the text colour of the label
 - `background-color` the base background colour of the label
 - `hover-background-color` the background colour of the label when hovered - ignored if `$corner-label-change-background-on-hover` is false
 - `shadow-color` the background colour of label folds


### Selectors
`$label`
`$label-container`

I heard you came to us to fix your styles, not dirty up your beautiful HTML with our dirty, dirty classes. That's ok. we can help! <sub>…maybe <sup>…at least a little.</sup></sub>

You'll still need both of the elements, but at least you can change the base classes to better fit the rest of your code.

Try something like:

For example, if you only have one label colour:
```scss
@use "path/to/settings/selectors" with (
  $label: i,
  $label-container: b,
);
@use "path/to/tools/label-styles";

@include label-styles.all;
```

And you can cut your markup down to as little as:
```html
<b><i>Look at my ribbons!</i></b>
```
However, please bear in mind that in order to use colours and tightnesses other than the default you'll need to use `.class`es as the selectors.

<sub><sup>plus, disregaring that fact, this markup is horribly unreadable…</sup></sub>

### Alignment

You don't like your labels on the top left? Oh, come on.
… ok, fine. We'll allow you to move it to the top right.

Use this markup instead:
```html
<span class="corner-label-container">
  <span class="corner-label corner-label--dark  corner-label--top-right">
    Look at my labels!
  </span>
</span>
```

What's that you say?
Your labels are *mostly* top-right, so you don't want to type all of that?
Ok, cool, then revert your markup back to the default and add this variable to your scss:

```scss
@use "path/to/settings/selectors" with (
  $default-alignment: top-right,
);
@use "path/to/tools/label-styles";

@include label-styles.all;
```

You what?
Your labels are *ALWAYS* top-right, so you don't even want to include the <sub><sup>(5 lines of)</sup></sub> CSS for the top left?
I'm still with ya! Do this instead:
```scss
@use "path/to/tools/label-styles";

@include label-styles.for(top-right);
```

On the bottom, you say?
Well… do WE have a solution for you?!

… no. No is the answer there. If enough requests come in, I'll look into it, though!

### MHOAR OPTIONS!!!

Whoa! Ha… you're getting a little excited there… <sub>and just a tad scary…</sub> <sup>could you brush your teeth before you do that again,<sub> please?</sup></sub>

There actually ARE more options… but I'll let you find them for yourself as they're all quite edge case and, hopefully, quite easy to decipher.

Look through the files in `scss/settings` and you should be flying.

## License

Copyright © 2020 [Brook Jordan](https://brook.dev/)
Licensed under the [MIT license](http://www.opensource.org/licenses/MIT/).
