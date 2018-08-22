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
<!-- development version, includes helpful console warning -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
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
message: 'Hello Vue!',
otherMessage: 'other message'
}
})
```
el - HTML element where the app is rendered
data - where the data is

---
# Hello Vue
---

### What happened here?
- We instantiated an App component to create our Vue app  `new Vue({ ... definition })`
- We used interpolation {{}} - to show data

---