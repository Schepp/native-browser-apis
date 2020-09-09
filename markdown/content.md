<!-- .slide: data-background="" data-state="inverted" -->

# The Breakthrough of Native Browser APIs
---
<!-- .slide: data-background="images/backgrounds/fireworks.gif" data-state="inverted" -->

# Happy [12th birthday, jQuery](https://johnresig.com/blog/10th-anniversary-of-jquery/)!
---
# Why jQuery?

<ul>
    <li class="fragment">mapped to W3C and IE DOM API (especially event handling)</li>
    <li class="fragment">fixed (IE 6 & 7) browser bugs</li>
    <li class="fragment">offered unique CSS selector style DOM selection & traversal API (Sizzle)</li>
    <li class="fragment">offered convenient API with [method chaining + method pattern](https://www.smashingmagazine.com/2012/10/designing-javascript-apis-usability/)</li>
    <li class="fragment">offered convenient API for animations</li>
    <li class="fragment"><blink>_</blink></li>
</ul>
---
<!-- .slide: data-background="images/backgrounds/mum-boy.jpg" data-state="inverted faded" -->

<br><br><br><br><br><br>
# Thank you jQuery for protecting us from the outside world!
---
# The advantages nowadays?

<ul>
    <li class="fragment"><del>maps to W3C and IE DOM API</del></li>
    <li class="fragment">fixes <del>(IE 6 & 7) browser bugs</del> <span class="fragment">mobile browser bugs</span></li>
    <li class="fragment">offers <del>unique</del> CSS selector style DOM selection & traversal API</del></li>
    <li class="fragment">still offers convenient API with [method chaining + method pattern](https://www.smashingmagazine.com/2012/10/designing-javascript-apis-usability/)</li>
    <li class="fragment">still offers convenient API for animations</li>
    <li class="fragment">comes with a huge ecosystem of plugins</li>
    <li class="fragment"><blink>_</blink></li>
</ul>
---
# Any drawbacks?

<table>
    <thead>
    <tr>
        <th>jQuery version</th>
        <th>file size</th>
        <th>minified</th>
        <th>minified + gzipped</th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <th>1.2</th>
        <td>79,259</td>
        <td>45,707</td>
        <td>14,472</td>
    </tr>
    <tr>
        <th>1.4.2</th>
        <td>163,855</td>
        <td>72,174</td>
        <td>24,558</td>
    </tr>
    <tr>
        <th>1.12.0</th>
        <td>294,161</td>
        <td>97,362</td>
        <td>33,878</td>
    </tr>
    <tr>
        <th>2.0.0</th>
        <td>240,196</td>
        <td>83,095</td>
        <td>29,002</td>
    </tr>
    <tr>
        <th>2.1.3</th>
        <td>247,387</td>
        <td>84,320</td>
        <td>29,562</td>
    </tr>
    <tr>
        <th>3.0.0-alpha1</th>
        <td>255,567</td>
        <td>84,522</td>
        <td>29,475</td>
    </tr>
    </tbody>
</table>

[Source](https://mathiasbynens.be/demo/jquery-size)
---
<p>30 KB JavaScript? Who cares?!?</p>

<blockquote class="twitter-tweet" data-lang="de"><p lang="en" dir="ltr">Images account for 63% of page weight (avg 687k) <a href="http://t.co/XPPhGE73">http://t.co/XPPhGE73</a> so: 1) a bit silly to whine over 30k of JS 2) going retina? use vector</p>&mdash; Paul Irish (@paul_irish) <a href="https://twitter.com/paul_irish/status/228815997438672896">27. Juli 2012</a></blockquote>
---
<p><i>You</i> should!</p>

<blockquote class="twitter-tweet" data-lang="de"><p lang="en" dir="ltr"><a href="https://twitter.com/paul_irish">@paul_irish</a> OTOH, JS blocks rendering, so JS KB &quot;costs&quot; more than img KB in terms of perf</p>&mdash; Yoav Weiss (@yoavweiss) <a href="https://twitter.com/yoavweiss/status/228818180917833729">27. Juli 2012</a></blockquote>
---
<p>Parse times of 1MB (uncompressed) JavaScript</p>

![Parse times of 1MB JavaScript](images/javascript-parse-times-moto-g4.jpg)

<p>up to 1.5 seconds on a mainstream Motorola G4</p>
<p class="fragment">and up to 6.5 seconds on lowend devices</p>
---
Remember:

<table>
    <thead>
    <tr>
        <th>jQuery version</th>
        <th>file size</th>
        <th>minified</th>
        <th>minified + gzipped</th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <th>3.0.0-alpha1</th>
        <td style="font-size: 1.5em; font-weight: bold; color: rgba(255, 255, 255, 0.5)">255,567</td>
        <td>84,522</td>
        <td>29,475</td>
    </tr>
    </tbody>
</table>

<p class="fragment">= 375 ms parse time on a Motorola Moto G4<p>
<p class="fragment">~ <a href="http://carlos.bueno.org/2010/02/measuring-javascript-parse-and-load.html#minifi">half the time for the minified version</a><p>
---
<blockquote><p lang="en" dir="ltr">The default global baseline is a ~$200 Android device on a 400Kbps link with a 400ms round-trip-time (“RTT”).<br><br>This translates into a budget of ~130-170KB of critical-path resources, depending on composition — the more JS you include, the smaller the bundle must be.</p>&mdash; Alex Russell <a href="https://infrequently.org/2017/10/can-you-afford-it-real-world-web-performance-budgets/">22. Oktober 2017</a></blockquote>

<p class="fragment">Document + Stylesheets + Fonts + JavaScript <= 130/170 KB</p>
---
Also, native code is always faster than interpreted / just in time compiled code!
---
# A lot happened since 2006

<ul>
    <li class="fragment">IE 7, 8 and 9 phased out</span></li>
    <li class="fragment">Modern IEs like 10, 11 and Edge came</li>
    <li class="fragment">Android browser came and went away again<span class="fragment"> (phew!)</span></li>
    <li class="fragment">W3C Document Object Model Level 3</li>
    <li class="fragment">W3C Selectors API Level 1 & 2 came to be</li>
    <li class="fragment">CSS 3</li>
    <li class="fragment">ES5, ES2015, ES2016 and ES2017</li>
    <li class="fragment">and many more standards were established since</li>
    <li class="fragment"><blink>_</blink></li>
</ul>
---
<!-- .slide: data-background="images/backgrounds/man.jpg" data-state="inverted faded" -->

<br><br><br><br><br><br>
# Time to stand on our own feet!
---
# DOM Selection and Traversal

querySelector()

```
var firstExternalLink = querySelector('a[target="_blank"]');
```
---
# DOM Selection and Traversal

querySelectorAll()

```
function $(selector, elem = document) {
  return [...elem.querySelectorAll(selector)];
}

var links = $('a');

links.forEach(...); <- yay, forEach on a NodeList
```
---
# DOM Selection and Traversal

Ways to convert NodeLists into iterable arrays:

ES5:
```
var arr = [].slice.call(document.querySelectorAll(selector));
```

ES2015 (a):

```
const arr = [...document.querySelectorAll(selector)]
```

ES2015 (b):
```
const arr = Array.from(document.querySelectorAll(selector));
```
---
# DOM Selection and Traversal

<table>
    <thead>
    <tr>
        <th>jQuery version</th>
        <th>Vanilla JavaScript</th>
    </tr>
    </thead>
    <tbody>
    <tr class="fragment">
        <td>`.parent()`</td>
        <td><span>`.parentNode`</td>
    </tr>
    <tr class="fragment">
        <td><span>`.prev()`</td>
        <td>`.previousSibling`</td>
    </tr>
    <tr class="fragment">
        <td>`.next()`</td>
        <td>`.nextSibling`</td>
    </tr>
    <tr class="fragment">
        <td>`.siblings(selector)`</td>
        <td>`$(selector, elem.parentNode)`</td>
    </tr>
    <tr class="fragment">
        <td>`.closest(selector)`</td>
        <td>`.closest(selector)`</td>
    </tr>
    <tr class="fragment">
        <td colspan="2"><blink>_</blink></td>
    </tr>
    </tbody>
</table>
---
# DOM Manipulation

<table>
    <thead>
    <tr>
        <th>jQuery version</th>
        <th>Vanilla JavaScript</th>
    </tr>
    </thead>
    <tbody>
    <tr class="fragment">
        <td>`.append()`</td>
        <td>`.appendChild()`</td>
    </tr>
    <tr class="fragment">
        <td>`.prepend()`</td>
        <td>`.prepend()` (needs [Polyfill](https://developer.mozilla.org/de/docs/Web/API/ParentNode/prepend#Polyfill))</td>
    </tr>
    <tr class="fragment">
        <td>`.insertBefore()`</td>
        <td>`.before()`</td>
    </tr>
    <tr class="fragment">
        <td>`.insertAfter()`</td>
        <td>`.after()`</td>
    </tr>
    <tr class="fragment">
        <td>`.replaceWith()`</td>
        <td>`.replaceWith()` (needs [Polyfill](https://developer.mozilla.org/en-US/docs/Web/API/ChildNode/replaceWith#Polyfill))</td>
    </tr>
    <tr class="fragment">
        <td colspan="2"><blink>_</blink></td>
    </tr>
    </tbody>
</table>
---
# Working with CSS Classes

```
elem.classList.add('hidden');
elem.classList.remove('hidden');
elem.classList.toggle('hidden');
elem.classList.contains('hidden');
```
---
# Setting CSS Styles

Adding multiple styles in one go:

```
Object.assign(elem.style, { 
    color: '#fff', 
    fontSize: '1rem', 
});
```

Removing multiple styles in one go:

```
Object.assign(elem.style, { 
    color: '', 
    fontSize: '', 
});
```
---
# Event delegation

Use the `.matches()` method:

```
const delegate = (eventName, selector, callback) => {
    document.addEventListener(eventName, (e) => {
        if (e.target.matches(selector)) {
            callback(e);
        }
    }, false);
}

delegate('click', 'a', (e) => {
    console.log(e.target.href);
});
```
---
# Event delegation

What to do with events that do not bubble up? 🤔

---
# Event delegation

Catch the event in the capture phase and [it will magically work](https://www.quirksmode.org/blog/archives/2008/04/delegating_the.html)! 

```
const delegate = (eventName, selector, callback) => {
    document.addEventListener(eventName, (e) => {
        if (e.target.matches(selector)) {
            callback(e);
        }
    }, true); // <- true!
}

delegate('blur', 'input', (e) => {
    console.log(e.target.value); // works!
});
```
😍
---
# Web Animations API

If you cannot live with CSS Animations or Transitions alone...

```
elem.animate(
  [
    { transform: 'translate(-50%, -50%) scale(.5)' },
    { transform: 'translate(-50%, -50%) scale(2)' }   
  ], {
    duration: 8000,
    easing: 'ease-in-out',
    fill: 'both'
  });
```
<div class="fragment">
<p>Works in Chrome and Firefox</p>

<p>[Polyfill](https://github.com/web-animations/web-animations-js)</p>
</div> 
---
# Fetch is the new Ajax

```
fetch(url, options).then((response) => {
  ... 
});
```

<span class="fragment">Older browsers need a [polyfill](https://github.com/github/fetch)</span>
---
# Working with Arrays lodash-Style

<ul style="font-size: 0.8em">
    <li class="fragment">`.forEach()` (ES5)</li>
    <li class="fragment">`.filter()` (ES5)</li>
    <li class="fragment">`.map()` (ES5)</li>
    <li class="fragment">`.reduce()` (ES5)</li>
    <li class="fragment">`.sort()` (ES5)</li>
    <li class="fragment">`.every()` (ES5)</li>
    <li class="fragment">`.find()` and `.findIndex()` (ES2015)</li>
    <li class="fragment">`.entries()` and `.values()` (ES2015)</li>
    <li class="fragment">`.includes()` (ES2016)</li>
    <li class="fragment">`.flatMap()` and `.flat()` (ES2019?)</li>
    <li class="fragment"><blink>_</blink></li>
</ul>
---
![mootools logo](images/mootools-logo.png)

As a side note: mootools suck!
---
Few examples:

```
// Check if every array item matches a test
[1, 2, 3, 4].every(e => e < 5); // -> true
```

```
// Find the first array item bigger than 2 and return its value
[1, 2, 3, 4].find(e => e > 2); // -> 3
```

```
// Find the first array item bigger than 2 and return its index
[1, 2, 3, 4].findIndex(e => e > 2); // -> 2
```

Copied from Das Surma's [underdash page](https://surma.github.io/underdash/)
---
# Elegantly working with Objects

<ul>
    <li class="fragment">`.assign()` (ES2015)</li>
    <li class="fragment">`.keys()` (ES2015)</li>
    <li class="fragment">`.entries()` (?)</li>
    <li class="fragment">`.values()` (?)</li>
    <li class="fragment"><blink>_</blink></li>
</ul>
---
Few examples:

```
// Get all of an objects (own) keys
Object.keys({
  'a': 1,
  'b': 2,
  'c': 3,
}); // -> ['a', 'b', 'c']
```

```
// Get all of an objects (own) values
Object.values({
  'a': 1,
  'b': 2,
  'c': 3,
}); // -> [1, 2, 3]
```

```
// Get all of an objects (own) keys + values
Object.entries({
  'a': 1,
  'b': 2,
  'c': 3,
}); // -> [['a', 1], ['b', 2], ['c', 3]]
```
---
# Building a slider with CSS Scroll Snap Points 

<video width=318 height=478 controls autoplay muted loop style="float: left; margin-right: 40px">
    <source src="https://yannickweiss.com/post/scroll-snap-iOS/showcase.mp4" type="video/mp4">
</video>

```
.wrapper {
    -webkit-overflow-scrolling: touch;
    overflow-x: auto;
    scroll-snap-type: mandatory;
    scroll-snap-destination: 50% 50%;
}

.flex-container {
    display: inline-flex;
}

.flex-item {
    width: 100vw;
    height: 100%;
    scroll-snap-coordinate: 50% 50%;
}
```

[Source](https://yannickweiss.com/post/scroll-snap-iOS/)
---
# Smooth (anchor) scrolling with CSS only

```
.scrollarea {
    scroll-behavior: smooth;
}
```

<img src="https://res.cloudinary.com/css-tricks/image/upload/c_scale,w_900,f_auto,q_auto/v1492202937/alamanac-css-scroll-behavior-smooth_tenf1s.gif" width="1600" height="400">

Source: [CSS Tricks](https://css-tricks.com/almanac/properties/s/scroll-behavior/)

<span class="fragment">Works in Firefox, and in Chrome</span> 
---
# CSS Font Loading API

Replaces Fontface Observer & similar libraries.

```
var root = document.documentElement;

if (document.fonts) {
    document.fonts.ready.then(() => {
      root.classList.add('fonts-loaded');
    });
} else {
      root.classList.add('fonts-loaded');
}
```
---
# Lazyloading

Imagine, you want to lazy load images:

```
<img src="data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7" 
     data-src="//image.jpg" 
     alt="" 
     width="400" 
     height="300">
```
---
# jQuery / traditional JavaScript lazyloaders

A truckload of *scroll events* or *setInterval calls* working in conjunction with `window.innerHeight`, `window.scrollY`, `Element.offsetTop`, `Element.offsetHeight` or `Element.getClientBoundingRect()` to figure out when an element enters the viewport.

<p class="fragment">LAYOUT TRASHING GALORE!</p>
---
<!-- .slide: data-background="images/layout-thrashing.png" data-state="inverted" -->
---
# Enters: Intersection Observer

<blockquote>The Intersection Observer API provides a way to asynchronously observe changes in the intersection of a target element with an ancestor element or with a top-level document's viewport.</blockquote>

[MDN](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API)

<p class="fragment"><blink>asynchronous!</blink></p>
---
```
const callback = (entries, observer) => {
  ...
});

const iObserver = new IntersectionObserver(callback, { 
  root: null, // intersection root element (null -> viewport)
  rootMargin: 0 0 500px 0, // hit area is expanded 500px more to the bottom  
  threshold: 0.1, // react when intersection ratio surpasses or drops below 0.1 / 10% 
});

iObserver.observe(document.querySelector('#theone'));
iObserver.observe(document.querySelector('#theother'));
```
---
```
const callback = (entries, observer) => {
  entries.forEach((entry) => {
    if (entry.isIntersecting) {
      // we have an intersection!
      const elem = entry.target;
      observer.unobserve(elem); // if we want to stop observing the elem 
    }
  });
});

const iObserver = new IntersectionObserver(callback, { 
  root: null, // intersection root element (null -> viewport)
  rootMargin: 0 0 500px 0, // hit area is expanded 500px more to the bottom  
  threshold: 0.1, // react when intersection ratio surpasses or drops below 0.1 / 10% 
});

iObserver.observe(document.querySelector('#whatever'));
```
---
# jQuery lazyload - but in efficient
```
const $ = selector => [...document.querySelectorAll(selector)]; 

const callback = (entries, observer) => {
    entries.forEach((entry) => {
        if (entry.isIntersecting) {
            entry.target.src = entry.target.getAttribute('data-src');
            observer.unobserve(entry.target);
        }
    });
}

const iObserver = new IntersectionObserver(callback, { threshold: 0.1 });

document.addEventListener('DOMContentLoaded', () => {
    $('img[data-src]').forEach((elem) => { iObserver.observe(elem); });
});
```
---
Oh wait, did I just use  
`document.addEventListener('DOMContentLoaded')`  
for real?

<p class="fragment">Sort of like `$(document).ready()`?</p>

<p class="fragment">This is so last decade!</p>
---
# Enters: Mutation Observer

<blockquote>The MutationObserver interface provides the ability to watch for changes being made to the DOM tree.</blockquote>

[MDN](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver)
---
```
const mObserver = new MutationObserver((mutations) => {
  mutations.forEach((mutation) => {
    // mutation.addedNodes <- look!
    // mutation.removedNodes
    // mutation.attributeName
    // mutation.oldValue
  });
});

mObserver.observe(document.documentElement, {
  attributes: false,
  childList: true,
  characterData: false,
  subtree: true,
});
```

<span class="fragment">Works in Chrome, Firefox, Edge and IE11!</span> 
---
Example:
```
const mObserver = new MutationObserver((mutations) => {
  mutations.forEach((mutation) => {
    const addedNodes = [...mutation.addedNodes];
    
    addNodes.filter(node => node.nodeType === 1).forEach((node) => {
      if (node.matches('img[data-src]') {
        prepareLazyload(node); // initialize lazyloading
      }
      if (node.matches('#whatever') {
        // do something else
      }
    });
  });
});

mObserver.observe(document.documentElement, { childList: true, subtree: true });
```
---
# Advantages

<ul>
  <li class="fragment">You can initialize elements as soon as they drop into the DOM, not just on DOMContentLoaded</li>
  <li class="fragment">Elements added later to the DOM also get their treatment</li>
  <li class="fragment">No one forgets to initialize an element</li>
</ul>
  
---
# Caveats

but...
---
Caveat 1: Mutation Observer doesn't register DOM nodes created via `.innerHTML` method. Just the most outer one of the pack. 😫
---
Solution: query every new DOM node for children and add them to the list.

```
const mObserver = new MutationObserver((mutations) => {
  mutations.forEach((mutation) => {
    const addedNodes = [...mutation.addedNodes]
      .filter(node => node.nodeType === 1)
      .reduce((acc, node) => {
        return acc.concat([node], [...node.getElementsByTagName('*')]);
      }, []);
  });
});
mObserver.observe(document.documentElement, { childList: true, subtree: true });
```
---
Use a WeakSet as a "node memory" to make sure you never process any node twice: 

```
const processedNodes = new WeakSet();

const mObserver = new MutationObserver((mutations) => {
  mutations.forEach((mutation) => {
    const addedNodes = [...mutation.addedNodes]
      .filter(node => node.nodeType === 1)
      .reduce((acc, node) => {
        return acc.concat([node], [...node.getElementsByTagName('*')]);
      }, [])
      .filter(node => !processedNodes.has(node)) // <- discard already known node
      .forEach(node => { // <- remember node for the future
        processedNodes.add(node);
        return node;
      });
  });
});
mObserver.observe(document.documentElement, { childList: true, subtree: true });
```
---
Caveat 2: 

<blockquote>An unoptimized MutationObserver callback can add a few seconds to page load time if the page is big and complex</blockquote>

[wOxxOm on Stack Overflow](https://stackoverflow.com/a/39332340)
---
Solution: only use Mutation Observer as a trigger together with DOM polling

```
const processedNodes = new WeakMap();
const mObserver = new MutationObserver(() => { domChanged = true });
let domChanged = false;

window.setInterval(() => {
  if (!domChanged) return;
  domChanged = false;
  const addedNodes = [...document.getElementsByTagName('*')]
    .filter(node => !processedNodes.has(node)) // <- discard already known node
    .forEach(node => { // <- remember node for the future
      processedNodes.add(node);
      return node;
    });    
  // do something with the newly added nodes
}, 250);

mObserver.observe(document.documentElement, { childList: true, subtree: true });
```
---
<!-- .slide: data-background="images/backgrounds/8207553734_1cacc702f3_o.jpg" data-state="inverted faded" -->

<br><br><br><br><br><br>
<div class="fragment">
  <h2>Have fun and thank you for listening!</h2>
  
  <ul>
   <li>Slides: [http://schepp.github.io/native-browser-apis](http://schepp.github.io/native-browser-apis)</li>
   <li>Twitter: [@derSchepp](https://twitter.com/derSchepp) (English)</li>
   <li>Meetup: [Webworker NRW](http://workingdraft.de) (German)</li>
   <li>Podcast: [Working Draft](http://workingdraft.de) (German)</li>
  </ul>
</div>
