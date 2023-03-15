<div align="center">
  <img
  src="Stats card - desktop.png"
  alt="Marketing card outlining how data statistics can help a business grow"
  height="350px">
</div>

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
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

<div align="center">
  <img 
    src="Stats card - desktop.png"
    alt="Marketing card outlining how data statistics can help a business grow, desktop version horizontal display with product description with statistics on the left and decorative image on the right"
    height="300px">
  <img 
    src="Stats card - mobile.png"
    alt="Marketing card outlining how data statistics can help a business grow, mobile version vertical display with decorative image on top and product description with statistics on the bottom"
    height="400px">
    <p><em>Desktop (horizontal) and mobile (vertical) designs</em></p>
</div> 


### Links

- Solution URL: [Marketing statistics preview card](https://rileydevdzn.github.io/marketing-statistics-card/)

## My process

### Built with

- Semantic HTML5 markup
- Responsive images using the `<img>` element with `srcset` and `media` attributes
- CSS variables
- CSS `mix-blend-mode` for blending backgrounds
- Flexbox
- Responsive design
- Realistic workflow, building from professional Figma design files (design-to-code)

### What I learned

To make the image responsive, I focused on resolution switching – using an `<img>` element with the `srcset` and `media` attributes – so that the smaller image would display on mobile and the larger image would display on desktop. This worked well, but I wasn't done yet.

Another styling challenge for this project was overlapping (blending) an image with the brand color. I had previously done text overlays over images using colors and opacity, but that solution did not work here. The image was dark and difficult to make out. So I dug into the Figma design file. The designer used two backgrounds, one color and one image, and added `mix-blend-mode` to blend the layers. After some research, I discovered CSS also has this capability, with options for both `background-blend-mode` and `mix-blend-mode` properties.

I chose `mix-blend-mode` based on how my markup was already configured. For the responsive image, I used an `<img>` element inside a parent container, like this:

```html
<div class="insights-img-wrapper">
  <img class="insights-deco-img"
    srcset="/mktstats-image-header-desktop.jpg 540w, ./mktstats-image-header-mobile.jpg 654w"
    sizes="(max-width: 600px) 327px, 270px"
    src="/mktstats-image-header-desktop.jpg"
    alt="Group of professional women working on laptops at a large table in an office space">
</div>
```

Then I added a background color to the parent element, and used the `mix-blend-mode` property to blend the two, following the Figma design file for the settings (multiply and opacity 0.75) to match the design. 

```CSS
.insights-img-wrapper {
  background-color: var(--accent-violet);
}

.insights-deco-img {
  mix-blend-mode: multiply;
  opacity: 0.75;
}
```

### Continued development

I found the resolution switching solution for responsive images useful for this project; I'm adding responsive images to my toolkit for my builds going forward. I also found the `mix-blend-mode` really interesting and its something I'd like to play with and refine my skills. I'm also curious if there's a way to make background images responsive in a similar manner, something to investigate on a future project. 

### Useful resources

- [CSS Tricks: Basics of blend mode](https://css-tricks.com/basics-css-blend-modes/) - This introductory article includes lots of examples and explains just a few of the possibilities you can create with blend-mode. CSS-Tricks is one of my go-to resources when I want to figure out how to apply a new technique correctly. 
- [CodePen search for blend mode](https://codepen.io/search/pens?q=blend+mode) - You can find lots of examples of really cool things people are creating using blend-mode (or anything else) on CodePen. Great for inspiration, and my favorite part is being able to view the source code to figure out exactly how they did it so I can see different ways to solve the same problem.

## Author

- Website - [E. Riley](https://rileydevdzn.webflow.io)
- Frontend Mentor - [@rileydevdzn](https://www.frontendmentor.io/profile/rileydevdzn)
