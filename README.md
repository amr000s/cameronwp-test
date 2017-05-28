# Website Performance Optimization Project

To see a live WebOptimized Project demo, please visit https://amr000s.github.io/cameronwp-webOptimized/

PageSpeed Insights has calculated a score of **95** for Mobile and **96** for Desktop.

## Part 1: Optimizing PageSpeed Insight score for index.html

**Optimizations:**

- Replaced the jpg file with png and reduced the size using tinypng.com
- Add style elements into html file
- Minified style.css, renamed it style-min.css and inlined the styel-min.css within index.html
- Added async to the JS script tags and moved them to the bottom of index.html
- Added Web Font loader to bottom of index.html
- Added google anylatics to bottom of index.html

## Part 2: Optimizing Frames per Second in main.js

**Optimization:**

- Reduced for-loop calculation by:
  - Placing (document.body.scrollTop / 1250) into a variable (`var top = document.body.scrollTop / 1250`) outside the loop but still in the updatePosition function.
  - Pushed items.length into variable (`var cachedLength = items.length`)
  - Created `var items` and placed it above the `var pizzaIngredients = {}`
  - items = documents.getElementsByClassName('mover') created and placed above updatePositions () because we only need to query items after they're made and before they need to be used.
  - Created `var phase` and `var topSide`.
  - The for-loop contains constArray.push(Math.sin(top + i)); allowing it to run faster.
- Repositioned pizzas with this:
  - `inserted items[i].style.transform = 'translateX(' + (100 * phase) + 'px)';`
- Replaced querySelector's with getElementById to increase scroll and page rendering.
- Saved the array length , which is part of the condition statement, in a local variable (`var len`), so the array's length property is not accessed to check its value at each iteration. (i.e. more efficiency).
- Declared the pizzasDiv variable (`var pizzasDiv`) outside the loop, so only DOM call is made.
- Calculated the number of pizzas needed to fill the screen, based on browser window resolution.
- Declared `var elem` outside the for-loop to prevent it from being created every time the loop is executed.
- Declared `var movingPizzas` outside for-loop as var movingPizzas = document.getElementById('movingPizzas1');
   - /** Inside the for statement / loop – this line*/
   - movingPizzas.appendChild(elem);
- Created `var newWidth` and placed it above function changePizzaSlices(size)

## Part 3: Optimizing Pizza slider in main.js

**Optimization:**
- Replaced previous for-loop function with new loop.
- Added a switch case element to increase slider speed.
- Put `var pizzasDiv` outside of for-loop function to increase efficiency.
- Made `var randomPizzas` and changed the querySelectorAll element to getElementsByClassName.
