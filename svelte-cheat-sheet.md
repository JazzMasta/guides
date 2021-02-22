
### Add prop

`export let myProp`


### Add dynamic expressions (e.g. based on props)
```svelte
$: calculatedValue = prop1 * 10
$: title = title || 'No title provided'
```

### Dynamic CSS classes
```svelte
<div class:has-error={ hasError } />
```

### Two-way binding
```svelte
<input type="text" bind:value={ myVariable } />
```

### Output HTML
```svelte
<p>{ @html variableWithHtmlContent }</p>
```

## Conditional output

### if, else, if-else
```svelte
{#if state === 'done' }
  content goes here
{:else if state === 'error' }
  alternative content
{:else }
  else content
{/if }
```

### each loop, (with else and index)
```svelte
{#each contentArray as item, index}
  <ContentCard title={ (index+1) + '. ' + item.title } body={ item.body } />
{:else }
  Content to show if the array is empty
{/each }
```


