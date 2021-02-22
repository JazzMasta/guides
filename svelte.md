
## VS Code extension

https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode


# Init project 

(js)

### With typescript support
```
npx degit sveltejs/template svelte-typescript-app
cd svelte-typescript-app
node scripts/setupTypeScript.js

npm install
```

### Run dev
```
npm run dev
```

### Build (and serve)
```
npm run build
npm run start
```

### Run in SPA mode
Modify `package.json`
```
"start": "sirv public --single"
```


## About Typescript support

- You can use TypeScript inside your <script> blocks — just add the `lang="ts"` attribute
- Components with TypeScript can be type-checked with the svelte-check command
- You get autocompletion hints and type-checking as you're writing components, even in expressions inside markup
- TypeScript files understand the Svelte component API — no more red squiggles when you import a .svelte file into a .ts module

More info:
https://svelte.dev/blog/svelte-and-typescript


# Components

Component props are created by "exporting" variables in a component
```
<script>
  export let username;
</script>
```

and are used like:
```
<script>
  let username = '';
</script>

...

<input type="text" bind:value={ username } />   // Two-way binding of inputfield to variable
<MyComponent username={ username } />
```



## Conditionals

If-else
```
{ #if myVar === true }
  <p>Hello</p>
{ :else }
  <p>Goodbye</p>
{ /if }
```

Each
```
{ #each contacts as contact }
<Card name={ contact.name } />
```

