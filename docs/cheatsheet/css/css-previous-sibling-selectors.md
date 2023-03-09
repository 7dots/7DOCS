# CSS Previous sibling selectors and how to fake them

## Example HTML structure
```html
<nav class="nav">
    <ul class="nav__items">
        <li class="nav__item">
            <a href="/">Home</a>
        </li>
        <li class="nav__item">
            <a href="/about">About</a>
        </li>
        <li class="nav__item">
            <a href="/work">Work</a>
        </li>
        <li class="nav__item">
            <a href="/contact-us">Contact us</a>
        </li>
    </ul>
</nav>
```

## Example SCSS structure
```scss
.nav__items {
  // The faking magic - the hover effect will now only take place when hovering on a child element.
  pointer-events: none;

  &:hover {
    > .nav__item a {
      opacity: 0.4;
    }

    > .nav__item:hover a {
      opacity: 1;
    }
  }
}

.nav__item {
  // The faking magic.
  pointer-events: auto;
}
```

## Live example
<iframe height="500" width="100%" scrolling="no" title="CSS Previous sibling selectors and how to fake them" src="https://codepen.io/jackkemm/embed/preview/XWPzNZK?default-tab=result&theme-id=default" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/jackkemm/pen/XWPzNZK">
  CSS Previous sibling selectors and how to fake them</a> by Jack Kemmish (<a href="https://codepen.io/jackkemm">@jackkemm</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>
