# VUE - WHAT IS IT?
____
HARISHANKAR

---

## WHY SHOULD YOU CARE?
- Vue.js 93000 stars on github, React 95000 stars on
github, Angular 36000 stars on github AngularJS
58000 stars on github
- It's really easy, great documentation
- The interest is there, now we are just waiting for
adoption

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
<button v-on:click="save">Save</button>

