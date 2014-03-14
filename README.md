# Animate(d).sass
*A streamlined Sass port (featuring the best) of Dan Eden's Animate.css*

Here's the deal: [Dan Eden's](http://daneden.me) [Animate.css](http://daneden.github.io/animate.css/) is a wonderful little library. Some of the animations are a little "too much" for my taste and many of the projects I work on. I know there are Sass ports out there ([animate.sass](https://github.com/adamstac/animate.sass) and [this updated fork](https://github.com/polikin/animate.sass)), but I wanted a simpler port to Sass that I could build on.

Here is the fruit of this work.

## Usage

1. Use `@include "animated";` to bring the library into your Sass project.
2. Use the `animation mixin globally for every animation you want to include: `@include animation(animation-name);`. This is important as it brings in the appropriate `keyframe` animation for use in your elements. (_Note: the keyframe animation needs to be global in your Sass, and not under any speficic selector, class, ID, or other mixin_).
3. Use the `animate` mixin within any element to setup the animation: `@include animate(animation-name, animation-duration, animation-delay);`.

Here is an example Sass file:

```
@import "animated";

@include animation(fade-in-down);
@include animation(fade-in);

nav {
  @include animate(fade-in-down, 1s);
}

.masthead {
  @include animate(fade-in, 1s, 500ms);
}
```

From this we can see that we have our `nav` element coming in using the `fade-in-down` animation with a duration of 1 second. The `.masthead` also fades in with a 1 second duration, but the effect is delayed in its start by 500 milliseconds.

That's it! You can tweak `animation-name` in your `animate` mixin call, as well as `animation-duration` and `animation-delay` to get your desired effect.

### Animation Mixin

The `animation` mixin has a single attribute and must be called globally in your Sass project:

- `animation-name`: required

### Animate Mixin

The `animate` mixin must be called within an element and it has three attributes:

- `animation-name`: required; no default
- `animation-duration`: optional; accepts milliseconds or seconds (e.g. `500ms` or `1s`); default value is 1s
- `animation-delay`: optional; accepts milliseconds or seconds (e.g. `500ms` or `1s`); no default

## Animations

Here is a list of all animations included in this library. Reference [Dan Eden's original project](http://daneden.github.io/animate.css/) for animation examples. Use the strings below in Sass in place of the `animation-name` in the `animation` and `animate` mixins:

### Attention Seekers

- `bounce`
- `pulse`
- `rubber band`
- `shake`
- `wobble`

### Bouncing Entrances

- `bounce-in`
- `bounce-in-down`
- `bounce-in-left`
- `bounce-in-right`
- `bounce-in-up`

### Bouncing Exits

- `bounce-out`
- `bounce-out-down`
- `bounce-out-left`
- `bounce-out-right`
- `bounce-out-up`

### Fading Entrances

- `fade-in`
- `fade-in-down`
- `fade-in-down-big`
- `fade-in-left`
- `fade-in-left-big`
- `fade-in-right`
- `fade-in-right-big`
- `fade-in-up`
- `fade-in-up-big`

### Fading Exits

- `fade-out`
- `fade-out-down`
- `fade-out-down-big`
- `fade-out-left`
- `fade-out-left-big`
- `fade-out-right`
- `fade-out-right-big`
- `fade-out-up`
- `fade-out-up-big`

### Flippers

- `flip-in-x`

### Sliders

- `slide-in-down`
- `slide-in-left`
- `slide-in-right`
- `slide-out-left`
- `slide-out-right`
- `slide-out-up`

## Custom "One-Off" Animations

I also created a simple mixin to handle simpler, "one-off" animations. This mixin doesn't have any keyframe animations so it just needs to be added to any selector, class, or ID in your Sass. Here are usage instructions:

1. Call `animate-simple` in your Sass, supplying a CSS element, an animation duration (in seconds or milliseconds), and an [animation timing function](http://www.w3.org/TR/css3-animations/#animation-timing-function-property).

### Animate Simple Mixin

The `animate-simple` mixin must be called within any CSS element and it has three attributes:

- `css-attribute`: optional; defaults to `color` if no attribute is specified (examples are `background-color`, `border-color`, anc `color` although any CSS attribute can be used)
- `animation-duration`: optional; accepts milliseconds or seconds (e.g. `500ms` or `1s`); default value is 300ms
- `animation-timing-function`: optional; defaults to `ease-in-out`

Here is a sample piece of code:

```
a {
  &:hover {
    @include animate-simple();
    @include animate-simple(border-color, 200ms, ease-in);
  }
}
```

In this code, you can see that there are two animations being called. The first call animates the `<a>` element on hover with the default CSS attribute `color` with an animation-duration of `300ms` and the default timing function: `ease-in-out`. The second animation animates the link's `border-color` with a duration of `200ms` and the animation timing function: `ease-in`.

## Changes

This project is a work in progress and my first Sass plugin. Feel free to get in touch if you want to see changes. My arm could probably be twisted to include Dan Eden's entire library. I just chose these animations because there is a subtlty to them that I appreciate and will be able to utilize in my projects. If it's helpful to you, great! If there is a better way to Sassify this project, feel free to reach out as I'm always willing to learn better ways to do things. I have done here what makes sense and hopefully it is helpful to you in some small way.

## Credits

Major thanks go to [@daneden](http://github.com/daneden) for the awesome CSS library of animations he compiled. Also thanks to [@polikin](https://github.com/polikin) for the inspiration. Also, thank you to [Sache](http://sache.in) and the wonderful [Sass community](http://sass-lang.com/community) for helping make the web a better, more organized, and more beautiful place.

## License

Copyright &copy; 2014 Jonathan Simcoe

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.