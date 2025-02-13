# CSS Notes

- [CSS Notes](#css-notes)
  - [Set Text Inside a Polygon Using `shape-outside` Property](#set-text-inside-a-polygon-using-shape-outside-property)
  - [`direction` Property](#direction-property)

## Set Text Inside a Polygon Using `shape-outside` Property

In order to set a text inside a polygon you can use below sample code. It has some customizable and optional properties like size, background color and text color and polygon shape. Make sure to keep other values as it is.

```css
/* Example */
.text-inside-polygon {
  position: relative;
  margin: 0;
  /* Customizable */
  width: 200px;
  height: 200px;
  /* Optional */
  color: white;
  background: orangered;
  clip-path: polygon(49% 0%, 100% 50%, 50% 100%, 0% 50%);
}

.text-inside-polygon::before {
  content: "";
  /* Don't use absolute here, else the effect won't work */
  /* position: absolute; */
  width: 50%;
  height: 100%;
  float: left;
  /* Customizable */
  shape-outside: polygon(0% 0%, 100% 0%, 0% 50%, 100% 100%, 0% 100%);
  /* shape-margin: 5%; */
}

.text-inside-polygon p {
  margin: 0;
  height: 100%;
  text-align: center;
}

.text-inside-polygon p::before {
  content: "";
  width: 50%;
  height: 100%;
  float: right;
  /* Customizable */
  shape-outside: polygon(0% 0%, 100% 0%, 100% 100%, 0% 100%, 100% 50%);
  /* shape-margin: 5%; */
}
```

HTML Code w.r.t above code is as given below

```html
<div class="text-inside-polygon">
  <p>
    This is an example of a text placed inside some polygon using css. Using
    shape-outside we can do it
  </p>
</div>
```

You can also use `shape-outside` property to align / arrange text around an image or diagram.

> Example [Link](text-inside-polygon/) & [Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/shape-outside)

---

## `direction` Property

The `direction` CSS property sets the direction of text, table columns, and horizontal overflow. Use `rtl` for languages written from right to left (like Hebrew or Arabic), and `ltr` for those written from left to right (like English and most other languages).

```css
/* Keyword values */
.test {
  direction: ltr;
  direction: rtl;
}
```

| Value | Description                                                               |
| ----- | ------------------------------------------------------------------------- |
| ltr   | Text and other elements go from left to right. This is the default value. |
| rtl   | Text and other elements go from right to left.                            |

You can also use this to reverse the order of div element inside the target div, which has this property applied. [Example](https://developer.mozilla.org/en-US/docs/Web/CSS/direction)

---
