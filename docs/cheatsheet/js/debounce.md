# Debounce

## Example
```javascript
const debounce = (callback, wait) => {
  let timeoutId = null
  return (...args) => {
    window.clearTimeout(timeoutId)
    timeoutId = window.setTimeout(() => {
      callback.apply(null, args)
    }, wait)
  }
}
```

## Example usage

```javascript
const handleMouseMove = debounce((e) => {
  // Do stuff with the event!
}, 250)
window.addEventListener('mousemove', handleMouseMove)
```

```javascript
window.addEventListener('resize', debounce((e) => {
	// Do stuff with the event!
}, 250))
```
