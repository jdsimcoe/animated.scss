# Animated.sass
*A streamlined Sass port (featuring the best) of Dan Eden's Animate.css*

Here's the deal: [Dan Eden's](http://daneden.me) [Animate.css](http://daneden.github.io/animate.css/) is a wonderful little library. Some of the animations are a little "too much" for my taste and many of the projects I work on. I know there are Sass ports out there ([animate.sass](https://github.com/adamstac/animate.sass) and [this updated fork](https://github.com/polikin/animate.sass)), but I wanted a simpler port to Sass that I could build on.

Here is the fruit of this work.

## Usage

1. Use `@include "animate"` to bring the library into your Sass project.
2. Use `@include animation(animation-name);` globally for every animation you want to include. This step is important as it brings in the appropriate `keyframe` animation for use in your elements.
3. Use `@include animate(animation-name, animation-duration, animation-delay);` within any element to setup the animation.

That's it! Make sure to use the correct `animation-name`, `animation-duration`, and `animation-delay` to get the desired effect.

### Animate Mixin

Please note that the `animate` mixin (above) has three attributes:

- `animation-name`: required
- `animation-duration`: optional; accepts milliseconds or seconds (e.g. `500ms` or `1s`)
- `animation-delay`: optional; accepts milliseconds or seconds (e.g. `500ms` or `1s`)

## Animations

More to come here soon...


## Credits

Major thanks go to [@daneden](http://github.com/daneden) for the awesome CSS library of animations he compiled. Also thanks to [@polikin](https://github.com/polikin) for the inspiration. Also, thank you to [Sache](http://sache.in) and the wonderful [Sass community](http://sass-lang.com/community) for helping make the web a better, more organized, and more beautiful place.

## License

Copyright &copy; 2013 Jonathan Simcoe

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE