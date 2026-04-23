# Frontend Mentor - Product preview card component solution

This is a solution to the [Product preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/product-preview-card-component-GO7UmttRfa).

## Table of contents

- [Overview](#overview)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
  - [AI Collaboration](#ai-collaboration)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview

A responsive product preview card with two layouts — stacked on mobile, side-by-side on desktop.

### Screenshot

![Product preview card solution screenshot](./screenshot.png)

### Links

- Solution URL: [Frontend Mentor solution](https://www.frontendmentor.io/solutions/product-preview-card-component-sass-flexbox-picture-element-yOT5M2K6Go)
- Live Site URL: [https://maxi1993-tech.github.io/product-preview-card-component/](https://maxi1993-tech.github.io/product-preview-card-component/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Mobile-first workflow
- Sass (SCSS)
- `<picture>` element for responsive images

### What I learned

First time using Sass on a real project. The main benefit is nesting — keeping related styles together instead of scattered selectors:

```scss
.card {
    background-color: var(--neutral-white);

    button {
        background-color: var(--primary-green-500);

        &:hover {
            background-color: var(--primary-green-700);
        }
    }
}
```

The `<picture>` element lets you serve different images depending on screen size — cleaner than toggling `display: none` with CSS:

```html
<picture>
    <source srcset="./images/image-product-desktop.jpg" media="(min-width: 37.5rem)" />
    <img src="./images/image-product-mobile.jpg" alt="..." />
</picture>
```

`overflow: hidden` on the card is what makes `border-radius` work on the image — without it the corners bleed through:

```css
.card {
    border-radius: 8px;
    overflow: hidden;
}
```

Specificity matters in media queries — if base styles use `.card picture img`, the media query needs the same selector to override them.

### Continued development

Media queries gave me trouble — I need to understand specificity better and how flex properties interact across breakpoints. Also want to get more comfortable with Sass and start building a consistent personal workflow (commits, accessibility, HTML structure).

### Useful resources

- [MDN Web Docs](https://developer.mozilla.org) - Go-to reference for everything.
- [Figma](https://figma.com) - Used to extract dimensions and compare against the design.

### AI Collaboration

Worked with Claude again on this one. Same deal as last time — questions instead of answers, which is frustrating in the moment but forces you to actually think. The Sass setup and the `<picture>` element were both new to me and Claude pointed me in the right direction without just writing it. The media query section was rough and I needed more direct help there than I'd like — something to work on.

## Author

- Frontend Mentor - [@maxi1993-tech](https://www.frontendmentor.io/profile/maxi1993-tech)
- GitHub - [maxi1993-tech](https://github.com/maxi1993-tech)

## Acknowledgments

Thanks to Frontend Mentor for the challenge. Clean design, good difficulty step up from the previous one.