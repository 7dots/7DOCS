# BEM - Block Element Modifier

At 7DOTS we use the BEM methodology for creating our class names.

However, we do it slightly differently in the sense that we don't chain on modifiers to our class names and prefer to use a modifier class e.g. `-blue`. We also try to keep class names as short and meaningful as possible, so it's best to avoid double underscores and double hyphens to prevent the class names from becoming too long.

Below you can see the 7DOTS BEM example, and a generic BEM example to see the difference, and see how much more readable/manageable it is.

## 7DOTS BEM Example
```html
<ul class="list">
    <li class="list__item">
        <div class="card">
            <div class="card__header">
                <h2 class="card__title -blue">I'm a title</h2>
            </div>
            <div class="card__content">
                <p class="card__description">I'm a description</p>
            </div>
        </div>
    </li>
    <li class="list__item">
        <div class="card">
            <div class="card__header">
                <h2 class="card__title -blue">I'm a title</h2>
            </div>
            <div class="card__content">
                <p class="card__description">I'm a description</p>
            </div>
        </div>
    </li>
</ul>
```

When styling we can then use the modifier class to style the element:
```scss
.card__title {
  &.-blue {
    color: blue;
  }
}
```

## Generic BEM Example
```html
<ul class="list">
    <li class="list__item">
        <div class="list__item-card">
            <div class="list__item-card__header">
                <h2 class="list__item-card__header-title">I'm a title</h2>
            </div>
            <div class="list__item-card__content">
                <p class="list__item-card__content-description">I'm a description</p>
            </div>
        </div>
    </li>
    <li class="list__item">
        <div class="list__item-card">
            <div class="list__item-card__header">
                <h2 class="list__item-card__header-title">I'm a title</h2>
            </div>
            <div class="list__item-card__content">
                <p class="list__item-card__content-description">I'm a description</p>
            </div>
        </div>
    </li>
</ul>
```

**Note**

A good source for reference is: [https://www.smashingmagazine.com/2016/06/battling-bem-extended-edition-common-problems-and-how-to-avoid-them/](https://www.smashingmagazine.com/2016/06/battling-bem-extended-edition-common-problems-and-how-to-avoid-them/)
