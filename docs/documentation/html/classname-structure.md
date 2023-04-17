# Classname Structure

When building out components, we use the `||` separator to create difference in our classnames. This makes reading your classnames much easier.

The structure is as follows: `custom-classes || bootstrap-classes || js-classes`

## Example
```html
<div class="block || container || js-block">
    <div class="block__row || row">
        <div class="block__header">
            <h2 class="block__title || js-block-title">I'm a title</h2>
        </div>
    </div>
</div>
```

**Note**

We use `.js-` classes to decouple from the styling of a component. This is particularly useful if you have to update styled classnames without the need to update the `.js-` classnames too.
