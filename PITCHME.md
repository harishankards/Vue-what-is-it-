# VUE - WHAT IS IT?
____
HARISHANKAR

---

## WHY SHOULD YOU CARE?
- Vue.js - 1,10,000 stars on github, React.js - 1,08,000 stars on github, Angular - 39,500 stars on github. --- **Oh come on?! Even a thing is this?**
- It's really easy, great documentation --- **so?**
- Flexibility. Because it’s JS. --- **So what? React et al has it.**
- Very small in size. --- **How much, 100 KB? No. 18-21 KB. Wow right? No**
- MVVM architecure. --- **Angular has it. Shut up dude!**
- Combines the advantages of Angular and React.  


---
## VUE BASICS
---
### Let's start with the DOM

```html
<html>
<body>
<div id="app">
{{ message }} {{ other message }}
</div>
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js">
</script>
<script src="app.js"></script>
</body>
</html>
```
---
### Now let's create our Vue app !

```js
var app = new Vue({
  el: '#app',
  data: {
    message: 'Hello Spritle!',
    otherMessage: 'other message'
  }
})
```
el - HTML element where the app is rendered

data - where the data is

---
# Hello Spritle!
---

### What happened here?

- We instantiated an App component to create our Vue app  ```new Vue({ ... definition })```
- We used interpolation {{ }} - to show data

---

### How do we render a list?

---

- Use the structural directive **v-for**
- Add a list to our data property

---

```js
var app = new Vue({
  el: '#app',
  data: {
    message: 'Hello Spritle!',
    items: [{ id: 1, title: 'Bingo' }, { id: 2, title: 'Pringles'}]
  }
})
```
---
### **v-for** renders list

```html
  <div v-for="item in items">
    {{item.title}}
  </div>
```
---

### How do we do Conditional rendering?

---

```html
<div v-if="hasError">
  {{ error }}
</div>
<div v-else>
  All good here
</div>
```

---

### WORKING WITH FORM CONTROLS

---

**v-model** two-way binding

```html
<div id='example-3'>
<input type="checkbox" id="Donatello" value="Donatello"
v-model="checkedTurtles">
<label for="Donatello">Donatello</label>

<input type="checkbox" id="Michelangelo" value="Michelangelo"
v-model="checkedTurtles">
<label for="Michelangelo">Michelangelo</label>

<input type="checkbox" id="Rafael" value="Rafael"
v-model="checkedTurtles">
<label for="Rafael">Rafael</label>
<br>
<span>Checked turtles: {{ checkedTurtles }}</span>
</div>
```

---

What about **Methods**?

---

script:
```js
data: {
  newItem: ''
},
methods: {
  save() {
    console.log('value of input ' + this.newItem);
  }
}
```
template:
```html
<button v-on:click="save">Save</button>
```

---

 So we learned the Vue basics on creating an app, structural directives and so on. Can we wind up the session already?

---

 Oops, we need to learn about **Components** first

---

### Components

---

#### Vue.component()

```js
  Vue.component('componentName', {
  ... object definition
  })
```
---

```js
Vue.component('counter', {
  template: `
    <div>
      {{this.count}}
      <button v-on:click="adder">Increase</button>
    </div>
  `,
  data() { 
    return {
      count: 0 
    } 
  },
  methods: {
    adder () {
      this.count++
    }
  }
})
```
---

### Component with a child component

---

```js
Vue.component('parent', {
  template: `
    <div>
    Parent: <child />
    </div>
  `
})

Vue.component('child', {
  template: `
    <div>
    <strong>Child</strong>
    </div>
  `
})
```
---

Argh! Enough of these, can we jump to something interesting?

---

### CREATING COMPONENTS WITH ES6 MODULE/ VUE-CLI APPROACH

---

#### 1 file = 1 component

Component consists of the following:
- template - tag , this is where your HTML markup
 lives
- script - tag, this is where the component JS lives
- style - tag , this is where the styles are defined

---

```html
<template>
  <div class="hello"><h1>{{ msg }}</h1></div>
</template>

<script>
  export default {
    name: 'HelloWorld',
    data () { 
      return {
        msg: 'Hello Spritle' 
      } 
    }
  }
</script>

<style scoped>
  .hello {
  padding: 10px;
  }
</style>
```
---

How do we deal with child components?

---

To be able to use child component we need to:
- import the child component
- register it with its parent component

---
```js
import Test from './Test.vue'

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Hello Spritle'
    }
  },
  components: {
    Test
  }
}
```

import - import module

components - place child component here

---

```html
<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <test></test>
  </div>
</template>
```
---

# Questions?

---

 **Thank you for your patience :)**