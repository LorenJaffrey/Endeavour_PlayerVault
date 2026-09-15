```js-engine
if(document.head) {
	const style = document.createElement('style');
	style.type = 'text/css';
	
	style.innerHTML = `
		.callout-content {
			justify-content: Center;
		}
	`;
	
	document.head.appendChild(style);
}
```