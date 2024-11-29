# User guide: a basic guide to use of the new CSS properties

## 1. Container Queries

Media queries allow you to style your CSS based on the devices media type. This can change the screen resolution or oriantation

### Example of usage

```css
/* Example of a container query */
#feature-container {
   position: relative;
   max-width: 100%;
   width: 100%;
   height: 600px;
}

@media (max-width: 600px) {
  #feature-container {
      height: 250px;
  }
}
```

## 2. Subgrid
By applying display: grid to a grid container, only its direct children turn into grid items and can be positioned within the grid you've defined. The descendants of these grid items will still be arranged using the normal document flow.

### Exsample

```css
.parent-grid {
  display: grid;
  grid-template-columns: 1fr 2fr;
  gap: 10px;
}

.child-grid {
  display: grid;
  grid-template-columns: subgrid;
}
```

## 3. The :has() Pseudo-Class
The :has() pseudo-class allows you to style an element based on its children or contents. It acts as a parent selector, which was something previously missing in CSS.

### Exsample

```css
h2:has(+ p) {
  color: gray;
  background-color: gold;
  border: 2px dotted red;
}
```

## 4. The :is() Pseudo-Clas
The :is() pseudo-class is a way to simplify multiple selectors that need the same style. It reduces repetition and makes CSS more concise.
```css
ol {
  list-style-type: upper-alpha;
  color: darkblue;
}

/* stylelint-disable-next-line selector-pseudo-class-no-unknown */
:is(ol, ul, menu:unsupported) :is(ol, ul) {
  color: green;
}

:is(ol, ul) :is(ol, ul) ol {
  list-style-type: lower-greek;
  color: chocolate;
}
```