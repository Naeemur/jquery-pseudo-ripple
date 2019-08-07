# jQuery Pseudo Ripple
Material ripple plugin for jQuery web applications.
Examples are given below with code snippets.

## Why?
Usual ripple plugin inserts an empty div / span element to render the ripple. This may cause bugs due to the following problems -

- addtion of unnecessary elements in the DOM
- element.innerHTML becomes different than expected when read
- can not set element.innerHTML without caution
- not easily append / prepend elements without causing positioning problems

This is where this plugin shines. It uses CSS pseudo ::after element for rendering the ripple. So this keeps the DOM and innerHTML clean.
As ripples are only for design, I think it is best to do this using CSS.

## Dependencies
- jQuery

## Demo
[Live demo](https://naeemur.github.io/jquery-pseudo-ripple/)

## Simple use
```
// HTML
<div class="ripple-1">Hello Ripple</div>
// JS
$('.ripple-1').ripple()
```

## Styling with CSS
```
// HTML
<div class="ripple-2">Hello Color</div>
// css
.ripple-2::after {
background: rgba(0,210,255,0.5);
}
// JS
$('.ripple-2').ripple()
```

## API usage
```
// HTML
<div class="ripple-3">API usage</div>
<div class="ripple-4">2x slow + on click</div>
<div class="ripple-5">Centered ripple</div>
<div><span class="ic ic-play type-icon"></span> Click icon</div>
<div class="type-trigger"><span class="ic ic-play ripple-target"></span> <span>Click anywhere</span></div>
// JS
$('.ripple-3').ripple({
ease: 'cubic-bezier(.4,0,.2,1)',
duration: 2000, // default 400. could be ms in nummber or multiples of the default ('2x'|'3x'|'4x'|...|'10x')
onclick: false, // if false, ripples on mousedown
disable: false,
type: 'pointed', // 'centered' | 'icon' | 'trigger' | 'target'
size: 1, // integer upto 10. use greater than 1 for elements wihh greater height than width
})
$('.ripple-4').ripple({
duration: '2x',
onclick: true,
})
$('.ripple-5').ripple({
type: 'centered',
})
$('.type-icon').ripple({
type: 'icon',
})
$('.type-trigger').ripple({
type: 'trigger',// ripples in .ripple-target element inside
})
```

## Consider compact
If you do not plan to use multiples for duration and size other than 1, you should use <b>jquery-pseudo-ripple-compact.css</b> instead of <b>jquery-pseudo-ripple.css</b>

## License
The MIT License (MIT)

Copyright (c) 2019 Md. Naeemur Rahman (https://naeemur.github.io)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
