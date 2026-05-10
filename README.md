# Frontend Mentor - Social Links Profile Solution

This is a solution to the [Social links profile challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/social-links-profile-UG32l9m6dQ).

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

### Screenshot

![Screenshot of Social Links Profile solution](./screenshot.jpg)

### Links

- Solution URL: https://github.com/levilex-kilobytes/social-links-profile
- Live Site URL: https://vercel.com/levilex-kilobytes-projects/social-links-profile

## My process

### Built with

- Semantic HTML5 markup
- CSS without custom properties
- BEM naming convention
- Flexbox
- Mobile-first workflow
- Accessibility best practices

### What I learned

I learned a better way to handle reduced motion. Instead of disabling
transitions after the fact, I keep them off by default and only enable
them for users who have no motion preference:

```css
/* Transitions off by default */
.links__btn {
  /* no transition here */
}

/* Only enable for users comfortable with motion */
@media (prefers-reduced-motion: no-preference) {
  .links__btn {
    transition:
      background-color 0.2s ease,
      color 0.2s ease;
  }
}
```

I also learned to always place media queries at the bottom of the
CSS file — mobile breakpoints first, reduced motion last:

```css
/* Mobile */
@media (max-width: 25em) {
  .profile {
    padding: 1.5rem 1.25rem;
  }
}

/* Reduced motion — always last */
@media (prefers-reduced-motion: no-preference) {
  .links__btn {
    transition:
      background-color 0.2s ease,
      color 0.2s ease;
  }
}
```

And I practiced BEM naming convention consistently:

```html
<article class="profile">
  <div class="profile__avatar-wrapper">
    <img class="profile__avatar" />
  </div>
  <div class="profile__info">
    <h1 class="profile__name">Jessica Randall</h1>
    <p class="profile__location">London, United Kingdom</p>
    <p class="profile__bio">"Front-end developer and avid reader."</p>
  </div>
  <ul class="links">
    <li class="links__item">
      <a class="links__btn">GitHub</a>
    </li>
  </ul>
</article>
```

### Continued development

- Adding `aria-label` attributes to links for better screen reader support
- Supporting `prefers-color-scheme: light` for users who prefer light mode
- Learning more about CSS logical properties like `margin-block-start`
- Improving Git workflow — always run `git add .` before `git commit`

### Useful resources

- [MDN - prefers-reduced-motion](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion) - Helped me understand the difference between `reduce` and `no-preference` approaches.
- [BEM Methodology](https://getbem.com/) - Reference for Block, Element, Modifier naming.
- [MDN - focus-visible](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-visible) - Helped me add keyboard focus styles correctly.
- [MDN - CSS Logical Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_logical_properties_and_values) - Helped me understand `margin-block-start` vs `margin-top`.

### AI Collaboration

I used **Claude (Anthropic)** throughout this project:

- **Accessibility** — Claude explained the difference between
  `prefers-reduced-motion: reduce` vs `no-preference` and why
  the `no-preference` approach is safer and more accessible.

## Author

- Frontend Mentor -https://www.frontendmentor.io/profile/levilex-kilobytes
- Twitter -https://x.com/Itzlevi005

## Acknowledgments

Thanks to [Frontend Mentor](https://www.frontendmentor.io) for this
challenge
