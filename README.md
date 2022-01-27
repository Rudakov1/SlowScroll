# Slow Scroll
The script is written in the  programming language Java Script using the jQuery library. With it, your site can get smooth scrolling when the button is clicked.

 For it to work, you need the ***jQuery*** library version 3.6.0 (the script has not been tested on earlier versions). And its correct use in the code.

 ___

 In order for the page to scroll to the desired block, you need to correctly position the ***id*** of the section from which we want to scroll and to which one.
 ```html
<div class="scroll_start">
    <button>Your Text</button>
</div>
 ```
 ___

For this example, I'll create a second div and move it 1500px down and I will center our button in the css file, lowering it a little more down

```html
<div class="scroll_final">
    <button>Your Text</button>
</div>  
```

```css
.scroll_start{
    text-align: center;
    margin-top: 10px;
}

.scroll_final{
    text-align: center;
    margin-top: 1500px;
}

```
You can style the button according to your preferences and feel free to move on to connecting scripts.

```html
 <script src="jquery-3.6.0.min.js"></script>
 <script type="text/javascript" src="main.js"></script>
```
___

Let's go back to the html code again and do what we came here for.

Let's give our divs a universal id, and set the ***onclick*** condition with the name of our function, and in parentheses indicate the block to which you want to scroll the page

```html
<div id="block1" onclick="slowScroll(block2)" class="scroll_start">
    <button>Your Text</button>
</div>

<div id="block2" onclick="slowScroll(block1)" class="scroll_final">
    <button>Your Text</button>
</div>  
```
If desired, change the scroll speed. For example, from 1000 to 2000 in the main.js

```js
function slowScroll(id) { 
    var offset = 0;
    $('html, body').animate({ 
         scrollTop: $(id).offset().top - offset 
    }, 2000); //Speed scroll
    return false; 
}
```
Go to our website and see the end result:

![2022-01-27 15-30-11 (2)](https://user-images.githubusercontent.com/97966535/151344544-33be32ae-39d4-4b65-a4ab-205c66444c46.gif)
