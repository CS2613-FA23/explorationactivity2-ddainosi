# Overview
The library I chose for my second exploration activity was jQuery. I showcased some of the uses for the library using JavaScript.

## About jQuery
jQuery was first developed in 2005 and released in 2006 by John Resig, an expert in JavaScript programming [[ref]](https://blog.logrocket.com/the-history-and-legacy-of-jquery/). The purpose of the library is to help make using JavaScript easier when it comes to web development. jQuery includes features such as HTML/DOM manipulation, CSS manipulation, effects and animations, and HTML event methods [[ref]](https://www.w3schools.com/jquery/jquery_intro.asp).

### How is it used/Functionalities (From my Program)
**Modifying DOM Elements**
- The `html()` method changes the inner html text of an element
    - `%("span.letters").html(names[randomNum]);`
        - E.g. `<span class="letters">(Winner name)</span>` --> `<span class="letters"><Randomly generated name></span>`
- The `css()` method visually changes an element
    - `$("span.letters").css("color", "black");` changes the text colour of the _span.letters_ element to black
- The `removeAttr()` method removes the specified attribute from a specified html tag
    - `$(this).removeAttr('style');` removes the style attribute from the _span.letters_ tag, returning the element back to its original state.

**Animations**
- The `fadeIn()` method makes the specified element fade in for a specified duration of seconds (in milliseconds)
    - `$("h1#nav-title").fadeIn(5000);` makes the text on the navbar fade in for a duration of 5 seconds
- The `fadeOut()` method makes the specified element fade out for a specified duration of seconds (in milliseconds)
    - `$("h1#nav-title").fadeOut(5000);` makes the text on the navbar fade out for a duration of 5 seconds
- The `slideUp()` method makes the specified element slide up for a specified duration of seconds (in milliseconds)
    - `$("span.navbar-text").slideUp(1000);` slides the text in the navbar up for 1 second
- The `slideDown()` method makes the specified element slide down for a specified duration of seconds (in milliseconds)
    - `$("span.navbar-text").slideDown(1000);` slides the text in the navbar down for 1 second
- The `animate()` method runs a custom animation on the specified element
    - The section of code below makes the logo grow to the specified height and width:
    ```javascript
                    $("img#logo").animate({
                        height: "200px",
                        width: "530px",
                    }, 1000);
    ```
- The `mouseover()` method executes the code passed as a parameter when the mouse is hovering over the specified element
    - The section of code below changes the generated name to the specified colour when the mouse is hovering over the element:
    ```javascript
                $("span.letters").mouseover(function(){
                    $("span.letters").css("color", "#a4332b");
                });
    ```
- The `mouseout()` method executes the code passed as a parameter when the mouse is **not** hovering over the specified element
    - The section of code below changes the generated name to the colour black when the mouse is **not** hovering over the element:
    ```javascript
                $("span.letters").mouseout(function(){
                    $("span.letters").css("color", "black");
                });
    ```


**Other**
- The `ready()` method ensures that the page's DOM is safe to modify.
- The `click()` method executes the code passed as a parameter after the specified element is clicked.
    - The section of code below chooses a random name from the textarea after the **Generate** button is clicked:
    ```javascript
                    $("button#generate-button").click(function(){
                    const names = document.getElementById("textarea-names").value.split("\n");
                    const randomNum = Math.floor(Math.random() * names.length);
                    $("span.letters").html(names[randomNum]);
                    $("span.letters").animate({
                        fontSize: "3rem",
                        fontFamily: "Verdana, Geneva, Tahoma, sans-serif",
                    }, 1000, function(){$(this).removeAttr('style');} );
                });
    ```

You can read about the different jQuery effect methods [here](https://www.w3schools.com/jquery/jquery_ref_effects.asp).

### Personal Overview
I selected this package because I wanted to learn more about web development. I wanted to take advantage of this project and make it a learning experience about not only creating a dynamic website but to also learn more about programming in JavaScript. 

Learning the library has helped me gain more of an understanding about functional programming as I had to pass in functions as parameters when a certain event happens. jQuery also taught me more about manipulating DOM elements to change how they appeared to a user viewing the website. While HTML and CSS are not a part of this course, thanks to the library, I was able to gain experience in learning how JavaScript coincides with the markup and style sheet languages.

I would absolutely recommend this library to anyone starting out with web development. jQuery helps a lot with enhancing the UI in such an easy way for beginners to grasp. Since I had a great time using the library, I will continue to use it when I create more web projects. The part I had the most difficulty with was creating the animations. A lot of research had to go into looking at how to keep the animations playing if the mouse was hovering over the component or if it was possible to loop animations. Nonetheless, I hope to soon become familiar with its more difficult features and to make more visually pleasing animations.
