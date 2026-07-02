# Frontend Mentor - Bento grid solution

This is a solution to the [Bento grid challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/bento-grid-RMydElrlOj). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the interface depending on their device's screen size

### Screenshot

![](./screenshot.png)


### Links

- Solution URL: https://github.com/lenka-limberkova/bento-grid
- Live Site URL: https://lenka-limberkova.github.io/bento-grid/

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties (variables for colors and fonts)
- Flexbox
- CSS Grid, specifically `grid-template-areas`
- Mobile-first workflow (mobile styles as the default, desktop handled via `@media (min-width: 768px)`)

### What I learned

While building this bento grid, the biggest thing I learned was working with `grid-template-areas`. Instead of calculating `grid-column`/`grid-row` for every single card, I defined a named "map" of the grid, which is much easier to read and adjust:

```css
.grid-container {
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: 1.3fr 1fr 1fr;
    grid-template-areas:
        "left social social schedule"
        "left manage maintain schedule"
        "left audience grow grow";
}

.social {
    grid-area: social;
}
```

I also got clearer on the difference between styling by HTML tag (`h1`, `h2`) versus by class. For headings that need different appearances across cards, I created my own classes (`.heading-large`, `.heading-medium`, `.heading-small`) and styled through those instead of the tag itself — keeping the tag purely semantic:

```css
.heading-small {
    font-size: 1.6rem;
    font-weight: 500;
    line-height: 0.8;
    letter-spacing: -0.07em;
}
```

I also sorted out when to use `padding` versus `margin` — `padding-top` for spacing inside an element (typically for cards with a colored background), and `margin`/`gap` for spacing between elements.

### Continued development

I want to move on from static HTML and CSS toward JavaScript and SQL, so I can build more interactive and functional things, not just visual layouts.

### Useful resources

- [MDN - grid-template-areas](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-areas) - helped me understand exactly how areas are defined and why they need to form a rectangle.
