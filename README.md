# Website Performance Optimization portfolio project

PageSpeed Score

* index.html achieves a PageSpeed score of at least 90 for Mobile and Desktop.

Getting Rid of Jank

* Optimizations made to views/js/main.js make views/pizza.html render with a consistent frame-rate at 60fps when scrolling.
* Time to resize pizzas is less than 5 ms using the pizza size slider on the views/pizza.html page.

##Run this project

You can check the performance Optimizations made on this project by comparing the [optimized version](https://asalcedo07.github.io/frontend-nanodegree-website-optimization/) with the original version in the Source directory of this repository or hosted [here](https://github.com/udacity/frontend-nanodegree-mobile-portfolio).You can explore the differences using Chrome DevTools.

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
