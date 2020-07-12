# How I Built My Portfolio Website

I was really inspired by [Tom Nick's](https://tomnick.org/) website (after seeing his Pokemon battle cry website) to make something clean and simple, but also still looking relatively modern (and also low-effort, but not CMS style).

After about a month of me feeling like I didn't have the right _front-end skills_ to make something _fancy_, and a bunch of YouTube videos later, I remembered a very important truth:

> It is better to make something than to not make anything at all.

Ah, yes. A generic adage about how if I continue to do nothing, there is nothing to improve upon. So let's just accept the fact that my website isn't going to be the _fanciest_, but rather a constant work in progress. Once I get the basic content done, then I can work towards improving its fanciness.

## 1. The Basics

The basic layout was all done with Bootstrap and CSS, along with some extra dependencies like [Google Fonts](https://fonts.google.com/) and [Font Awesome](https://fontawesome.com/) icons.

1. Hero gradient was done with [CSS Gradient](https://cssgradient.io/) web app.

As of right now, I still don't know how to do basic page navigation that looks nice (not a hard refresh). I also still am unsure how to do navigation without JS.

## 2. The Basics+

1. Using the [Live Sass Compiler](https://marketplace.visualstudio.com/items?itemName=ritwickdey.live-sass) extension to edit Bootstrap Sass. It's important to import the "necessary" files, make overrides, and then import the main bootstrap folder. See the [Bootstrap docs](https://getbootstrap.com/docs/4.1/getting-started/theming/#sass). This is how you can change things like the primary and secondary colors.

2. Animated the hero section using the [Keyframes](https://keyframes.app/) Chrome Extension.

3. Used [Grayscale The Web](https://chrome.google.com/webstore/detail/grayscale-the-web-save-si/mblmpdpfppogibmoobibfannckeeleag?hl=en) Chrome Extension to see if there's any glaring contrast issues.

4. Used an svg for a default favicon, and also included favicons for other platforms in case svg is not supported (used [favicon.io](https://favicon.io/) to convert svg to favicon file formats like .png and .ico).

## 3. The Not-So-Basics

1. I used [Affinity Designer](https://affinity.serif.com/en-us/designer/) to create a logo-like graphic placed next to left of my name in the navbar. I exported as an SVG without background for highest web quality, and inserted the `<svg>` HTML element only into a `<div>` that I made inline-block so I could place it next to my name. Since trying to place the svg into the `<a>` tag for the navbar-brand proved difficult, it's in a separate `<div>`. I also animated it on hover.

2. I then made a watermark version of the svg (60% opacity on the back stroke, fill is white). I put it within the hero jumbotron (in a div), made the inner `<div>` with `position: absolute` and the jumbotron `position: relative` with `overflow: hidden` to prevent it from bleeding over the jumbotron.

3. Used an outline version of the svg and placed it within the footer. Realized that it was getting clipped by the elements in the grid, so I made it's z-index 1, but then you couldn't click the elements. Eventually learned that you have to make elements use the position attribute to use z-index, so I made the other footer elements have a z-index of 2 and made their backgrounds transparent.
