# Parallax Scroll Effect

Parallax scrolling, an effect that allows sections of a website to scroll at different speeds, is an effect that has gone through various stages of popularity over the last few years. We'll just be delving into how to implement such a feature in our code without the use of the Javascript plugin.

There’s a popular plugin called parallax.js that can quickly and easily take care of your parallax needs if you choose to use it. However, this plugin has a lot of features you might not use, and we can get the core functionality of parallax in about 100 bytes if we write our own code (down from 11 KB). All you need is a containing element, a contained element with a background image, and a few lines of jQuery.

# Container

We’re going to create a outer element and call it .parallax-container. This class simply sets the height of the parallax window. We’re going to set it to position: relative.

# Image

Now we’re going to create an inner div that will contain the actual parallax background image. The div will be set to position: absolute, which means it will become attached to the nearest relative element (which in this case is the parallax-container).

The variable in this class is height: 200%. We have to apply a width: 100% since the element is now absolute. Finally, a negative z-index needs to be set so that the image remains contained to the height of parallax-container. The z-index simply determines the stack layout relative to other objects.

# Content

All HTML layout elements have a transparent background by default. If you choose to use parallax, simply setting your background color on the body element won’t be enough anymore – you’ll have to place all of your non-parallax content inside of elements with a background color. I’m going to create a .content class that simply has a background color so that my content will always appear over the parallax image.

# HTML

I’m going to create a top and bottom empty section to create scroll for demonstration purposes.

On the .parallax div, I edit the style attribute and add a background image.

The background image will be horizontally and vertically centered in the div, cover the entire div, and not repeat.

# Javascript (jQuery)

We'll be using jQuery for this project. So we linked it in the HTML file. We’re going to create a variable for the parallax class, and count all instances using .length.

Next, we’ll create a scroll function and then we'll do an animation using requestAnimationFrame. We'll then create a for loop, capturing each parallax element in currentElement, and how much has been scrolled with scrolled.

Finally, we'll multiply how much has been scrolled with a negative pixel value, and apply that to the transform: translate3D of the CSS of the individual parallax element.
