# SCSS Structure

When styling your components, we opt to not nest classnames as this can cause the code to become unreadable, unsearchable, and can often cause issues when wanting to override styling.

It is also preferable to write your styling in the order of the elements on the front-end so it is easy to follow.

## 7DOTS Example
```scss
.list {
  list-style: none;
  margin: 0;
  padding: 0;
  width: 100%;
}

.list__item {
  background-color: lightslategray;
  padding: 2rem;
}

.card {
  background-color: white;
  border-radius: 2rem;
}

.card__header {
  padding: 2rem;
}

.card__title {
  color: black;
}
```

## Bad Example
```scss
.list {
  list-style: none;
  margin: 0;
  padding: 0;
  width: 100%;
  
  &__item {
    background-color: lightslategray;
    padding: 2rem;
  }
}

.card {
  background-color: white;
  border-radius: 2rem;
  
  &__header {
    padding: 2rem;
    
    &__title {
      color: black;
    }
  }
}
```
