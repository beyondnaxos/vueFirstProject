# vue-project

This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```


ref permet de récupérer une référence sur un élément du DOM : exemple : 
```js
const count = ref(0)
```

reactive permet de créer une variable reactive : exemple : 
```js
const state = reactive({
  count: 0
})
```

computed permet de créer une variable calculée : exemple : 
```js
const count = ref(0)
const plusOne = computed(() => count.value + 1)
```

watch permet de créer un watcher : exemple : 
```js
const count = ref(0)
watch(count, (count, prevCount) => {
  /* ... */
})
```

watchEffect permet de créer un watcher qui s'execute au moins une fois : exemple : 
```js
const count = ref(0)
watchEffect((onInvalidate) => {
  /* ... */
})
```

onMounted permet d'executer une fonction au moment du montage du composant : exemple : 
```js
onMounted(() => {
  /* ... */
})
```

emit permet d'envoyer un événement à un composant parent : exemple : 
```js
const count = ref(0)
const increment = () => {
  count.value++
  emit('increment')
}
```

