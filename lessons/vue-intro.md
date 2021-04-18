## Resources

[Vue Cheatsheet](https://www.vuemastery.com/pdf/Vue-Essentials-Cheat-Sheet.pdf)

[Vue Documentation](https://vuejs.org/v2/guide/)

## Frontend Frameworks

- Angular
- React
- Vue
- Svelte
- Ember

### Features of Frontend Frameworks

#### Reactivity: Data-Bindings

The DOM Tree gets automatically updated when the state of some javascript
variables changes.

#### Templating & Virtual DOM

Instead of creating elements programatically, a template syntax almost
indistinguishable to html is used.

#### Components

You can create new custom html tags like `<home>`, `<menu>` etc...

#### Single Page Applications: Routing

Instead of requesting individual pages from the server, Javascript is used
to update the content of the page if you browse through the sub pages of a website.

## Vue Tooling

### Vue CLI

Most Vue projects are powered by the Vue CLI, which manages the initialization and bundling process of your repository

```
sudo yarn global add @vue/cli
vue create my-first-vue-project
```

### VS Code Extensions

- Vetur
- Sarah Dresner's Vue Code Snippets

### Vue Dev Tools Browser Extension

[Install in Chrome](https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd?hl=en)

## Vue Component Structure

Home.vue

```vue
// html template
<template>
  <div>
    <h1>Home</h1>
    <p>{{ message }}</p>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  // Within this object you configure your Vue component, including its properties, methods and life cycle hooks
  name: "Home",
  data() {
    // This is the javascript data that's available in your template
    return {
      message: "Hello World",
    };
  },
});
</script>

<style>
p {
  color: blue;
}
</style>
```
