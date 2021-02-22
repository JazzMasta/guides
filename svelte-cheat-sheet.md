
### Add prop

`export let myProp`


### Add dynamic expressions (e.g. based on props)
```
$: calculatedValue = prop1 * 10
$: title = title || 'No title provided'
```

### Dynamic CSS classes
```
<div class:has-error={ hasError } />
```

