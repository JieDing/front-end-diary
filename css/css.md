# CSS

## Introduction

- CSS stands for Cascading Style Sheets
- CSS describes how HTML elements are to be displayed on screen, paper, or in other media

## Role

HTML was created to describe the content of a web page

When tags like <font>, and color attributes were added to the HTML 3.2 specification, it started a nightmare for web developers. 

## Syntax

A CSS rule consists of a selector and a declaration block.

![img.png](../static/images/css-syntax.png)

The selector points to the HTML element you want to style.

The declaration block contains one or more declarations separated by semicolons.

Each declaration includes a CSS property name and a value, separated by a colon.

Multiple CSS declarations are separated with semicolons, and declaration blocks are surrounded by curly braces.

```css
p {
  color: red;
  text-align: center;
}
```
- `p` is a selector in CSS (it points to the HTML element you want to style: <p>).
- color is a property, and red is the property value
- text-align is a property, and center is the property value

## Selector

A CSS selector selects the HTML element(s) you want to style.

CSS selectors are used to "find" (or select) the HTML elements you want to style.

We can divide CSS selectors into five categories:
- Simple selectors (select elements based on name, id, class)
- Combinator selectors (select elements based on a specific relationship between them)
- Pseudo-class selectors (select elements based on a certain state)
- Pseudo-elements selectors (select and style a part of an element)
- Attribute selectors (select elements based on an attribute or attribute value)

### The CSS id Selector

To select an element with a specific id, write a hash (#) character, followed by the id of the element.

The CSS rule below will be applied to the HTML element with id="para1": 

```css
#para1 {
  text-align: center;
  color: red;
}
```
### The CSS class Selector

To select elements with a specific class, write a period (.) character, followed by the class name.

In this example, all HTML elements with class="center" will be red and center-aligned: 

```css
.center {
  text-align: center;
  color: red;
}
```

You can also specify that only specific HTML elements should be affected by a class.

In this example, only <p> elements with class="center" will be red and center-aligned:

```css
p.center {
  text-align: center;
  color: red;
}
```

### The CSS Grouping Selector

The grouping selector selects all the HTML elements with the same style definitions.

To group selectors, separate each selector with a comma.

```css
h1, h2, p {
  text-align: center;
  color: red;
}
```

## Three Ways to Insert CSS

There are three ways of inserting a style sheet:

- External CSS
- Internal CSS
- Inline CSS

### External CSS

With an external style sheet, you can change the look of an entire website by changing just one file!

Each HTML page must include a reference to the external style sheet file inside the <link> element, inside the head section.

```html
<!DOCTYPE html>
<html>
<head>
<link rel="stylesheet" href="mystyle.css">
</head>
```

An external style sheet can be written in any text editor, and must be saved with a .css extension.

The external .css file should not contain any HTML tags.

```css
body {
  background-color: lightblue;
}

h1 {
  color: navy;
  margin-left: 20px;
}
```

### Internal CSS

An internal style sheet may be used if one single HTML page has a unique style.

The internal style is defined inside the <style> element, inside the head section.

```html
<!DOCTYPE html>
<html>
<head>
<style>
body {
  background-color: linen;
}

h1 {
  color: maroon;
  margin-left: 40px;
}
</style>
</head>
```

### Inline CSS

An inline style may be used to apply a unique style to a single element.

To use inline styles, add the style attribute to the relevant element. The style attribute can contain any CSS property.

```html
<!DOCTYPE html>
<html>
<body>

<h1 style="color:blue;text-align:center;">This is a heading</h1>
<p style="color:red;">This is a paragraph.</p>

</body>
</html>
```

### Cascading Order

If some properties have been defined by the same selector (element) in different style sheets, the value from the last read style sheet will be used. 

All the styles on a page will "cascade" into a new "virtual" style sheet by the following rules, where number one has the highest priority:

1. Inline style (inside an HTML element)
2. External and internal style sheets (in the head section)
3. Browser default

## CSS Comments

A CSS comment starts with /* and ends with */:

```css
/* This is a single-line comment */
p {
  color: red;
}
```

## CSS Colors

Colors are specified using predefined color names, or RGB, HEX, HSL, RGBA, HSLA values.

### CSS Background Color

```html
<h1 style="background-color:DodgerBlue;">Hello World</h1>
```

### CSS Text Color

```html
<h1 style="color:Tomato;">Hello World</h1>
```

### CSS Border Color

```html
<h1 style="border:2px solid Tomato;">Hello World</h1>
```

### CSS Color Values

In CSS, colors can also be specified using RGB values, HEX values, HSL values, RGBA values, and HSLA values:

```html
<h1 style="background-color:rgb(255, 99, 71);">...</h1>
<h1 style="background-color:#ff6347;">...</h1>
<h1 style="background-color:hsl(9, 100%, 64%);">...</h1>
```

## CSS Backgrounds

### CSS background-color

The background-color property specifies the background color of an element.

```css
body {
  background-color: lightblue;
}
```

### Opacity / Transparency

The opacity property specifies the opacity/transparency of an element. It can take a value from 0.0 - 1.0. The lower value, the more transparent:

```css
div {
  background-color: green;
  opacity: 0.3;
}
```

### Transparency using RGBA

```css
div {
  background: rgba(0, 128, 0, 0.3) /* Green background with 30% opacity */
}
```

## CSS Border

### CSS Border Style

```css
p.dotted {border-style: dotted;}
p.dashed {border-style: dashed;}
p.solid {border-style: solid;}
p.double {border-style: double;}
p.groove {border-style: groove;}
p.ridge {border-style: ridge;}
p.inset {border-style: inset;}
p.outset {border-style: outset;}
p.none {border-style: none;}
p.hidden {border-style: hidden;}
p.mix {border-style: dotted dashed solid double;}
```
![img.png](../static/images/border-style.png)

### CSS Border Width

The border-width property can have from one to four values (for the top border, right border, bottom border, and the left border):

Four values are assigned to four sides clockwise. If one value is missing, get the value from the value of its symmetrical side. 
If symmetrical value is missing as well, get the value from previous one.

```css
p.one {
  border-style: solid;
  border-width: 5px; /* 5px for top bottom left right */
}

p.two {
  border-style: solid;
  border-width: 5px 10px; /* 5px top and bottom, 10px on the sides */
}

p.three {
  border-style: solid;
  border-width: 5px 10px 15px; /* 5px top, 10px for right, 15 for bottom */
}
p.four {
    border-style: solid;
    border-width: 5px 10px 15px 20px; /* 5px top, 10px for right, 15 for bottom, 20 for left */
}
```

### CSS Border Color

The border-color property is used to set the color of the four borders.

The border-color property can have from one to four values (for the top border, right border, bottom border, and the left border). 

Four values are assigned to four sides clockwise. If one value is missing, get the value from the value of its symmetrical side.
If symmetrical value is missing as well, get the value from previous one.

```css
p.one {
  border-style: solid;
  border-color: red green blue yellow; /* red top, green right, blue bottom and yellow left */
}
```

### CSS Border Sides

In CSS, there are also properties for specifying each of the borders (top, right, bottom, and left):

```css
p {
  border-top-style: dotted;
  border-right-style: solid;
  border-bottom-style: dotted;
  border-left-style: solid;
}
```

The example above gives the same result as this:

```css
p {
  border-style: dotted solid;
}
```

### CSS Border - Shorthand Property

The border property is a shorthand property for the following individual border properties:

- border-width
- border-style (required)
- border-color

```css
p {
  border: 5px solid red;
}
```

### CSS Rounded Borders

The border-radius property is used to add rounded borders to an element:

```css
p {
  border: 2px solid red;
  border-radius: 5px;
}
```

