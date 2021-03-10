# Props

### Add prop

`export let myProp`

### Default value (Making prop optional)
```
let prop1 = 'default value'
```

### Spread props from Object data
```svelte
const data = { id:'123', title:'Title', body:'Some text' }
</script>

<SomeComponent {...data} />
```
### Named slots

`<h1 slot="header">Title in slot "header"</h1>`


### Add dynamic expressions (e.g. based on props)
```svelte
$: calculatedValue = prop1 * 10
$: title = title || 'No title provided'
```



# CSS

### Dynamic CSS classes
```svelte
<div class:has-error={ hasError } />
```




# Forms and Elements

### Two-way binding
```svelte
<input type="text" bind:value={ myVariable } />
```

### Reference an HTML element

```
// Use this only for _reading_ values from an element. Do not manipulate elements this way
<input type="text" bind:this={ inputReference } />
```




# Events

### Event binding
```svelte
<button on:click={ eventHandlerMethod } />
```

### Event modifiers
```svelte 
<button on:click|preventDefault={ eventHandlerMethod } />
```

`preventDefault`: calls event.preventDefault() before running the handler. Useful for client-side form handling, for example.

`stopPropagation`: calls event.stopPropagation(), preventing the event reaching the next element

`passive`: improves scrolling performance on touch/wheel events (Svelte will add it automatically where it's safe to do so)

`nonpassive`: explicitly set passive: false

`capture`: fires the handler during the capture phase instead of the bubbling phase ()

`once`: remove the handler after the first time it runs

`self`: only trigger handler if event.target is the element itself


### Forward input event to parent component
Used when creating custom input components with two-way binding
```svelte
<input type="text" value="{value}" on:input />
```

### Emit custom event
```svelte
import { createEventDispatcher } from 'svelte';

const dispatchEvent = createEventDispatcher();

function onClickDelete () {
  // dispatch event with id 'delete' and some custom data
  dispatchEvent('delete', { itemId: 14802 })
}
```
Extract the event data with `event.detail`


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

### each loop, (with else, index, and key)
```svelte
{#each contentArray as item, index (item.uniqueId)}
  <ContentCard title={ (index+1) + '. ' + item.title } body={ item.body } />
{:else }
  Content to show if the array is empty
{/each }
```


# Sapper

## Run script on backend
```
<script context="module">
  // This will run on backend before sending response to frontend
</script>
```

## fetch on backend

Use `this.fetch` to use the fetch function on the backend






