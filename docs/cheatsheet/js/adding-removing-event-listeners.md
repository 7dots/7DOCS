# Adding and removing event listeners with parameters

```javascript
const coolNumber = (number) => {
	console.log(number)
	coolButton.removeEventListener('click', wrapperFunction)
}
const coolButton = document.querySelector('.js-cool-button')
let wrapperFunction = null // Define a variable to remember the function name to be removed

// Set the main function to the variable to be removed
wrapperFunction = () => coolNumber(8)

coolButton.addEventListener('click', wrapperFunction)
```
