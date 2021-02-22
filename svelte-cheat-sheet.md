
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

### Two-way binding
```
<input type="text" bind:value={ myVariable } />
```

### Output HTML
```
<p>{ @html variableWithHtmlContent }</p>
```

## Conditional output

```
{#if state === 'done' }
  content goes here
{:else if state === 'error' }
  alternative content
{:else }
  else content
{/if }
```

