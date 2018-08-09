---
title: Vue
category: JavaScript libraries
---

{% raw %}

### Lists

```html
<li v-for="todo in todos">
  {{ todo.text }}
  {{ $index }}
</li>
```

### Events

```html
<button v-on:click='submit'>Go</button>
```

### Binding (Classes, Styles)

Variables in the data object can be evaluated inside binding
```
<div v-bind:class="{ active: isActive }"></div>
<div v-bind:class="[{ active: isActive }, errorClass]"></div>
```

Binding Styles
```
<div v-bind:style="{ color: activeColor, fontSize: fontSize + 'px' }"></div>
```

```
<div v-bind:style="styleObject"></div>
data: {
  styleObject: {
    color: 'red',
    fontSize: '13px'
  }
}
```

### Rendering
```
<h1 v-if="ok">Yes</h1>
or
<h1 v-if="ok">Yes</h1>
<h1 v-else>No</h1>
```

v-show is for frequently toggled items
```
<h1 v-show="ok">Hello!</h1>
```

```
<ul id="example-1">
  <li v-for="item in items">
    {{ item.message }}
  </li>
</ul>
```

```
<div v-for="item in items" :key="item.id">
  <!-- content -->
</div>
```

```
<li v-for="todo in todos" v-if="!todo.isComplete">
  {{ todo }}
</li>
```

### Form Bindings
```
<input v-model="message" placeholder="edit me">
<p>Message is: {{ message }}</p>
```

### Components

```js
new Vue({
  components: { app: App }
})
```

## API

```js
Vue.extend({ ... })        // creating components
Vue.nextTick(() => {...})

Vue.set(object, key, val)  // reactive
Vue.delete(object, key)

Vue.directive('my-dir', { bind, update, unbind })
// <div v-my-dir='...'></div>

Vue.elementDirective('my-dir', { bind, update, unbind })
// <my-dir>...</my-dir>

Vue.component('my-component', Vue.extend({ .. }))

Vue.partial('my-partial', '<div>hi {{msg}}</div>')
// <partial name='my-partial'></partial>
```

```js
new Vue({
  data: { ... }
  props: ['size'],
  props: { size: Number },
  computed: { fullname() { return this.name + ' ' + this.lastName } },
  methods: { go() { ... } },
  watch: { a (val, oldVal) { ... } },
  el: '#foo',
  template: '...',
  replace: true, // replace element (default true)

  // lifecycle
  created () {},
  beforeCompile () {},
  compiled () {},
  ready () {}, // $el is inserted for the first time
  attached () {},
  detached () {},
  beforeDestroy () {},
  destroyed () {},

  // options
  directives: {},
  elementDirectives: {},
  filters: {},
  components: {},
  transitions: {},
  partials: {}
})
```

## Vue templates
Via [vueify](https://www.npmjs.com/package/vueify)

```js
// app.vue
<template>
  <h1 class="red">{{msg}}</h1>
</template>
 
<script>
  module.exports = {
    data () {
      return {
        msg: 'Hello world!'
      }
    }
  }
</script> 
```

Also

```html
<template lang='jade'>
h1(class='red') {{msg}}
</template>
```

{% endraw %}
