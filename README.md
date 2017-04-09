# Website Performance Optimization

## Overview
Optimize the critical rendering path and make a given page render as quickly as possible.

PageSpeed Score
* index.html achieves a PageSpeed score of at least 90 for Mobile and Desktop.

Getting Rid of Jank
* Optimizations made to views/js/main.js make views/pizza.html render with a consistent frame-rate at 60fps when scrolling.
* Time to resize pizzas is less than 5 ms using the pizza size slider on the views/pizza.html page.

Project was evaluated by a Udacity reviewer according to this [rubric](https://review.udacity.com/#!/rubrics/16/view)

## Run this project

- Clone or download the ZIP
- Open index.html in Production directory to see [optimized version](https://asalcedo07.github.io/frontend-nanodegree-website-optimization/)
- Open index.html in Source directory to see [original version](https://github.com/udacity/frontend-nanodegree-mobile-portfolio)
    - Examine the original unoptimized version provided by [Udacity](https://github.com/udacity/frontend-nanodegree-mobile-portfolio)

## Optimizations to index.html:

* Minify stylesheets
* Inline critical CSS
* Add print media query to print.css & inline
* Inline media query
* Load Javascript asynchronously
* Load js/perfmatter.js using defer attribute
* Optimize images via [GIMP 2](https://www.gimp.org/downloads/)
* Defer webfont loading

## Optimizations to pizza main.js:

* optimize images via [GIMP 2](https://www.gimp.org/downloads/)
* `Use Strict;`
* Change querySelectorAll to getElementsByClassName
* Change querySelector to getElementsById
* Delete helper function determineDx
* In `updatePositions`, move line `var scrolltop = document.body.scrollTop / 1250;` & `var items = document.getElementsByClassName('mover');` outside of the for loop to avoid triggering forced synchronous layouts.
* Precalculate the 5 different values of phase before the for-loop in `updatePositions`.
* Use CSS `translateX` to achieve pizza animation
* Reduced amount of pizzas rendered
* Optimized pizza slider calculations
* Move repeated query for `#movingPizzas1` out of for-loop in `DOMContentLoaded` event listener.
* Remove `determineDx` function and replaced with simple percentage sizes.
* Move repeated query for `#randomPizzas` out of for-loop for `var pizzasDiv` in `resizePizzas` function.
* Resolve forced synchronous layouts relating to for-loop in `changePizzaSizes` function.
