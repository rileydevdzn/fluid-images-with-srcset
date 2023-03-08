# Marketing statistics card

Building a responsive web component using Flexbox, the CSS mix-blend-mode property to blend backgrounds, and responsive images with the `<img>` element and `srcset` attributes.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshots](#screenshots)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

This is a solution to the [Stats preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/stats-preview-card-component-8JqbgoU62).

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- Extra challenge: view the optimal image based on device screen size (responsive images)

The source files for this project included images for desktop and mobile that were identical in content, but of different sizes. This was an opportunity for me to add an additional challenge for myself and explore responsive images using the `srcset` and `sizes` attributes of the `<img>` element (resolution switching). 

### Screenshots

<img
  src="Stats card - desktop.png"
  alt="Marketing card outlining how data statistics can help a business grow"
  title="Marketing statistics card, desktop version"
  width="500px">

<img
  src="Stats card - mobile.png"
  alt="Marketing card outlining how data statistics can help a business grow"
  title="Marketing statistics card, mobile version"
  width="150px">
  
### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)

## My process

### Built with

- Semantic HTML5 markup
- Responsive images using the `<img>` element with "srcset" and "media" attributes
- CSS variables
- CSS mix-blend-mode for blending backgrounds
- Flexbox
- Responsive design
- Realistic workflow, building from professional Figma design files (design-to-code)

### What I learned

To make the image responsive, I focused on resolution switching – using an `<img>` element with the "srcset" and "media" attributes – so that the smaller image would display on mobile and the larger image would display on desktop. This worked well, but I wasn't done yet.

A styling challenge for this project was overlapping (blending) an image with the brand color. I chose to tackle this after exploring responsive images, in case I needed to make changes. This also allowed me to explore both options and decide which provided the better solution.

I had previously done text overlays over images using colors and opacity, but that solution did not work here. The image was dark and difficult to make out. So I dug into the Figma design file. The designer used two backgrounds, one color and one image, and added mix-blend-mode to blend the layers. After some research, I discovered CSS also has this capability, with options for both background-blend-mode and mix-blend-mode properties.

I chose mix-blend-mode based on how my markup was already configured. For the responsive image, I used an `<img>` element inside a parent container, like this:

```html
<div class="insights-img-wrapper">
    <img class="insights-deco-img" 
       srcset="https://assets.codepen.io/3270335/FEM3-image-header-desktop.jpg 540w, https://assets.codepen.io/3270335/FEM3-image-header-mobile.jpg 654w"
       sizes="(max-width: 599px) 327px, 270px"
       src="https://assets.codepen.io/3270335/FEM3-image-header-desktop.jpg"
       alt="Group of professional women working on laptops at a large table in an open office space"/>
</div>
```

First, I swapped out the `<img>` element for a `<div>` with a background image. Then I added a background color to the parent element, and used the mix-blend-mode property to blend the two, following the Figma design file for the settings (multiply and opacity 0.75) to match the design exactly. 

```html
<div class="insights-img-wrapper">
    <div class="insights-deco-img"></div>
</div>
```

```CSS
.insights-img-wrapper {
  background-color: var(--accent-violet);
}

.insights-deco-img {
  background-image: url("https://assets.codepen.io/3270335/FEM3-image-header-desktop.jpg");
  mix-blend-mode: multiply;
  opacity: 0.75;
}
```

Another option would have been to remove the parent element and use multiple backgrounds with the background-blend-mode CSS property. I chose to keep my markup as-is, since I'm interested in figuring out if there's a way to also make background images responsive. 

### Continued development

I found the resolution switching solution for responsive images useful for this project; I'm adding responsive images to my toolkit for my builds going forward. I also found the mix-blend-mode really interesting and its something I'd like to play with and refine my skills. I'm also interested in finding a way to make background images responsive so that I can combine both approaches for the best of both worlds.

### Useful resources

- [CSS Tricks: Basics of blend mode](https://css-tricks.com/basics-css-blend-modes/) - This introductory article includes lots of examples and explains just a few of the possibilities you can create with blend-mode. CSS-Tricks is another of my go-to resources when I want to figure out how to apply a new technique correctly. 
- [CodePen search for blend mode](https://codepen.io/search/pens?q=blend+mode) - You can find lots of examples of really cool things people are creating using blend-mode (or anything else) on CodePen. Great for inspiration, and my favorite part is being able to view the source code to figure out exactly how they did it so I can see different ways to solve the same problem.

## Author

- Website - [rileydevdzn](https://rileydevdzn.webflow.io)
- Frontend Mentor - [@devrileymk](https://www.frontendmentor.io/profile/devrileymk)
