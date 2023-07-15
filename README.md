# ⛸️ @figured-layout-css/tailwindcss-plugin

## Easy-to-understand layout classes modeled after Figma's Auto Layout combined with the power of Tailwind CSS

|
[Getting Started](#getting-started) |
[Usage](#usage) |
[Layout and Alignment](#layout-and-alignment) |
[Component Sizing](#component-resizing) |
[Options](#options) |
[Demo]() |
[FAQs]() |

Say goodbye to flexbox or grid headaches and create HTML layouts with ease!

Yes - you can center a div with ease - we've.... figured (out the) layout 😉.

Figured Layout CSS makes it a breeze to layout you HTML with it's easy-to-understand CSS layout classes, modeled after Figma's Auto Layout.
As a Tailwind CSS plugin, you can combine Figured Layout's intuitive layout classes with the power of Tailwind CSS.
<br/>

<hr/>

#### Getting Started

ℹ️ This guide assume you have Tailwind already setup and configured.

#### Install package

`npm i -D @figured-layout-css/tailwindcss`

#### Add plugin to your tailwind.config.js

```js
/** @type {import('tailwindcss').Config} */

module.exports = {
  plugins: [require('@figured-layout-css/tailwindcss')],
};
```

#### Add a layout class to the parent container.

<!-- prettier-ignore -->
```html
<div class="layout-packed-mc-x">
  <div>Hello World</div>
</div>
```

🎉 The above will center a div horizontally and vertically 🎉
<br/>
<br/>

#### Add a sizing class

<!-- prettier-ignore -->
```html
<!-- Sizing Class on the Parent -->
<div class="layout-packed-mc-x w-fill w-fill">
  <!-- Sizing Class on the Parent -->
  <div class="h-fixed-24 w-fixed-24">Hello World</div>
</div>
```

🎉 The above displays at full screen height and width with a 96px x 96px centered div. 🎉

**Note:** Sizing classes are designed to work anywhere regarless of whether or not a layout class is present on the parent element.
<br/>
<br/>

#### Default behavior

- Elements without a layout class will respect default html block & inline element behavior.
- `body` & `html` both have `width` and `height` set to `100%`

<hr/>

#### Usage

### Control the layout and how the child components resize

Figma is a popular tool for designing websites and apps. The Auto Layout Feature dyanmically arranges elements on the page so you don't have to manually position everything when resizing a component.

The folloing image features the Auto Layout controls in Figma. The table details what can be done out-of-the box with Tailwind CSS and where the Figured Layout CSS is required.

![Figma Controls](/docs/images/figma-control/explaination.png)

| Figma Control                                                                             | CSS Approach                                                                 |
| ----------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| <span style="color:">1.a.</span> Horizontal resizing <br> 1.b. Verical resizing           | @figured-layout-css/tailwindcss <br>[Figma Component Resizing](#sizing)      |
| 2. Corner radius                                                                          | Tailwind CSS <br>[Border Radius](https://tailwindcss.com/docs/border-radius) |
| 3. Visability if overflow                                                                 | Tailwind CSS <br>[Overflow](https://tailwindcss.com/docs/overflow)           |
| 4.a. Direction child components flow <br> 4.b. Alignment of child components in container | @figured-layout-css/tailwindcss <br> [Figma Component Alignment](#sizing)    |
| 5. Space between child components                                                         | Tailwind CSS <br> [Gap](https://tailwindcss.com/docs/gap)                    |
| 6.a. Horizontal padding, 6.b. Vertical padding                                            | Tailwind CSS <br> [Padding](https://tailwindcss.com/docs/padding)            |

##### Example

The image below is controled by the html below.

![Example](docs/images/layout-example/explaination.png)

###### HTML

<!-- prettier-ignore -->
```html
<div class="layout-packed-tl-x gap-4 p-4 overflow-hidden w-fill h-fixed-40">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-fill">div</div>
  <span class="w-fill h-fixed-48">span</span>
</div>
```

<br/>

#### Layout and Alignment

<hr>

### Layout Class Structure

A layout class is made up of up to two parts `LayoutType-AlignmentType` e.g. `layout-packed-tl-x`

#### Layout Types

`layout-packed`: packs the child elemnts together in the container.

`layout-spaced`: spaces the child elemnts across the full width of the container.

`layout-grid`: spaces the child elements within the cell of a grid.

#### Alignment Types

`layout-packed-[horizontal][vertical]-[axis]` has three properties: horizontal alignment, vertical alignment and axis

- Vertical Alignment: Top `t` | Middle `m` | Bottom `b`
- Horizontal Alignment: Left `l` | Center `c` | Right `r`
- Axis: X `x` | Y `y`

`layout-spaced-[alignment]` has one property alignment

- Alignment: Top `t` | Middle `m` | Bottom `b` | Left `l` | Center `c` | Right `r`

`layout-grid-[horizontal][vertical]` has two properties: horizontal alignment and vertical alignment.

- Vertical Alignment: Top `t` | Middle `m` | Bottom `b`
- Horizontal Alignment: Left `l` | Center `c` | Right `r`

<br/>
<br/>

### Layouts Classes

#### 📐 Layout: Packed Top-Left across the X-axis

Use `layout-packed-tl-x` to align child elements at the top left of the container with them packed together.

![Example of layout-packed-tl-x](/docs/images/layout-example/layout-packed-tl-x.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-packed-tl-x gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-fill">div</div>
  <span class="w-hug h-fixed-48">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-packed-tl-x](docs/images/figma-control/layout-packed-tl-x.png)

<br>
<br>

#### 📐 Layout: Packed Top-Center across the X-axis

Use `layout-packed-tc-x` to align child elements at the top center of the container with them packed together.

![Example of layout-packed-tc-x](/docs/images/layout-example/layout-packed-tc-x.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-packed-tc-x gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-packed-tc-x](docs/images/figma-control/layout-packed-tc-x.png)

<br>
<br>

#### 📐 Layout: Packed Top-Right across the X-axis

Use `layout-packed-tr-x` to align child elements at the top right of the container with them packed together.

![Example of layout-packed-tr-x](/docs/images/layout-example/layout-packed-tr-x.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-packed-tr-x gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-packed-tr-x](docs/images/figma-control/layout-packed-tr-x.png)

<br>
<br>

#### 📐 Layout: Packed Middle-Left across the X-axis

Use `layout-packed-ml-x` to align child elements at the middle left of the container with them packed together.

![Example of layout-packed-ml-x](/docs/images/layout-example/layout-packed-ml-x.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-packed-ml-x gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-packed-ml-x](docs/images/figma-control/layout-packed-ml-x.png)

<br>
<br>

#### 📐 Layout: Packed Middle-Center across the X-axis

Use `layout-packed-mc-x` to align child elements at the middle center of the container with them packed together.

![Example of layout-packed-mc-x](/docs/images/layout-example/layout-packed-mc-x.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-packed-mc-x gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-packed-mc-x](docs/images/figma-control/layout-packed-mc-x.png)

<br>
<br>

#### 📐 Layout: Packed Middle-Right across the X-axis

Use `layout-packed-mr-x` to align child elements at the middle right of the container with them packed together.

![Example of layout-packed-mr-x](/docs/images/layout-example/layout-packed-mr-x.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-packed-mr-x gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-packed-mr-x](docs/images/figma-control/layout-packed-mr-x.png)

<br>
<br>

#### 📐 Layout: Packed Bottom-Left across the X-axis

Use `layout-packed-bl-x` to align child elements at the bottom left of the container with them packed together.

![Example of layout-packed-bl-x](/docs/images/layout-example/layout-packed-bl-x.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-packed-bl-x gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-packed-bl-x](docs/images/figma-control/layout-packed-bl-x.png)

<br>
<br>

#### 📐 Layout: Packed Bottom-Center across the X-axis

Use `layout-packed-bc-x` to align child elements at the bottom center of the container with them packed together.

![Example of layout-packed-bc-x](/docs/images/layout-example/layout-packed-bc-x.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-packed-bc-x gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-packed-bc-x](docs/images/figma-control/layout-packed-bc-x.png)

<br>
<br>

#### 📐 Layout: Packed Bottom-Right across the X-axis

Use `layout-packed-br-x` to align child elements at the bottom right of the container with them packed together.

![Example of layout-packed-br-x](/docs/images/layout-example/layout-packed-br-x.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-packed-br-x gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-packed-br-x](docs/images/figma-control/layout-packed-br-x.png)

<br>
<br>

#### 📐 Layout: Packed Top-Left across the Y-axis

Use `layout-packed-tl-y` to align child elements at the top left of the container with them packed together.

![Example of layout-packed-tl-y](/docs/images/layout-example/layout-packed-tl-y.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-packed-tl-y gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-packed-tl-y](docs/images/figma-control/layout-packed-tl-y.png)

<br>
<br>

#### 📐 Layout: Packed Top-Center across the Y-axis

Use `layout-packed-tc-y` to align child elements at the top center of the container with them packed together.

![Example of layout-packed-tc-y](/docs/images/layout-example/layout-packed-tc-y.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-packed-tc-y gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-packed-tc-y](docs/images/figma-control/layout-packed-tc-y.png)

<br>
<br>

#### 📐 Layout: Packed Top-Right across the Y-axis

Use `layout-packed-tr-y` to align child elements at the top right of the container with them packed together.

![Example of layout-packed-tr-y](/docs/images/layout-example/layout-packed-tr-y.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-packed-tr-y gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-packed-tr-y](docs/images/figma-control/layout-packed-tr-y.png)

<br>
<br>

#### 📐 Layout: Packed Middle-Left across the Y-axis

Use `layout-packed-ml-y` to align child elements at the middle left of the container with them packed together.

![Example of layout-packed-ml-y](/docs/images/layout-example/layout-packed-ml-y.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-packed-ml-y gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-packed-ml-y](docs/images/figma-control/layout-packed-ml-y.png)

<br>
<br>

#### 📐 Layout: Packed Middle-Center across the Y-axis

Use `layout-packed-mc-y` to align child elements at the middle center of the container with them packed together.

![Example of layout-packed-mc-y](/docs/images/layout-example/layout-packed-mc-y.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-packed-mc-y gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-packed-mc-y](docs/images/figma-control/layout-packed-mc-y.png)

<br>
<br>

#### 📐 Layout: Packed Middle-Right across the Y-axis

Use `layout-packed-mr-y` to align child elements at the middle right of the container with them packed together.

![Example of layout-packed-mr-y](/docs/images/layout-example/layout-packed-mr-y.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-packed-mr-y gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-packed-bl-y](docs/images/figma-control/layout-packed-mr-y.png)

<br>
<br>

#### 📐 Layout: Packed Bottom-Left across the Y-axis

Use `layout-packed-bl-y` to align child elements at the bottom left of the container with them packed together.

![Example of layout-packed-bl-y](/docs/images/layout-example/layout-packed-bl-y.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-packed-bl-y gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-packed-bl-y](docs/images/figma-control/layout-packed-bl-y.png)

<br>
<br>

#### 📐 Layout: Packed Bottom-Center across the Y-axis

Use `layout-packed-bc-y` to align child elements at the bottom center of the container with them packed together.

![Example of layout-packed-bc-y](/docs/images/layout-example/layout-packed-bc-y.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-packed-bc-y gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-packed-bc-y](docs/images/figma-control/layout-packed-bc-y.png)

<br>
<br>

#### 📐 Layout: Packed Bottom-Right across the Y-axis

Use `layout-packed-br-y` to align child elements at the bottom right of the container with them packed together.

![Example of layout-packed-br-y](/docs/images/layout-example/layout-packed-br-y.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-packed-br-y gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-packed-br-y](docs/images/figma-control/layout-packed-br-y.png)

<br>
<br>

#### 📐 Layout: Spaced down the Left

Use `layout-spaced-l` to space child elements down along the left of the container.

![Example of layout-spaced-l](/docs/images/layout-example/layout-spaced-l.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-spaced-l p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-spaced-l](docs/images/figma-control/layout-spaced-l.png)

<br>
<br>

#### 📐 Layout: Spaced down the Center

Use `layout-spaced-c` to space child elements down along the center of the container.

![Example of layout-spaced-c](/docs/images/layout-example/layout-spaced-c.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-spaced-c p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-spaced-c](docs/images/figma-control/layout-spaced-c.png)

<br>
<br>

#### 📐 Layout: Spaced down the Right

Use `layout-spaced-r` to space child elements down along the right of the container.

![Example of layout-spaced-r](/docs/images/layout-example/layout-spaced-r.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-spaced-r p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-spaced-r](docs/images/figma-control/layout-spaced-r.png)

<br>
<br>

#### 📐 Layout: Spaced across the Top

Use `layout-spaced-t` to space child elements across the top of the container.

![Example of layout-spaced-t](/docs/images/layout-example/layout-spaced-t.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-spaced-t p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-spaced-t](docs/images/figma-control/layout-spaced-t.png)

<br>
<br>

#### 📐 Layout: Spaced across the Middle

Use `layout-spaced-m` to space child elements across the middle of the container.

![Example of layout-spaced-m](/docs/images/layout-example/layout-spaced-m.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-spaced-m p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-spaced-m](docs/images/figma-control/layout-spaced-m.png)

<br>
<br>

#### 📐 Layout: Spaced across the Bottom

Use `layout-spaced-b` to space child elements across the bottom of the container.

![Example of layout-spaced-b](/docs/images/layout-example/layout-spaced-b.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-spaced-b p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <p class="w-hug h-hug">paragraph</p>
  <div class="w-hug h-hug">div</div>
  <span class="w-hug h-hug">span</span>
</div>
```

##### Figma Auto Layout Settings

![Figmat Auto Layout Example of layout-spaced-b](docs/images/figma-control/layout-spaced-b.png)

### ⭐️ Bonus ⭐️ : Auto Layout Grids

Figma doesn't have a capability for Grids in Auto Layout - this is my attempt at how it could work. These component classes are aimed at simplifying the use of CSS Grid Layout with Tailwind CSS.
<br/>
<br/>

<br>
<br>

#### 📐 Layout: Grid with items in the cell's Top Left

Use `layout-grid-tl` to align child elements at the top left of each cell in the grid.

![Example of layout-spaced-b](/docs/images/layout-example/layout-grid-tl.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-grid-tl grid-cols-3 gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <div class="w-hug h-hug">0A</div>
  <div class="w-hug h-hug">0B</div>
  <div class="w-hug h-hug">0C</div>
  <div class="w-hug h-hug">1A</div>
  <div class="w-hug h-fill">1B</div>
  <div class="w-fill h-hug">1C</div>
  <div class="w-fill h-fill">2A</div>
  <div class="w-fill h-fill">2B</div>
  <div class="w-fill h-fill">2C</div>
</div>
```

<br>
<br>

#### 📐 Layout: Grid with items in the cell's Top Center

Use `layout-grid-tc` to align child elements at the top center of each cell in the grid.

![Example of layout-spaced-b](/docs/images/layout-example/layout-grid-tc.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-grid-tc grid-cols-3 gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <div class="w-hug h-hug">0A</div>
  <div class="w-hug h-hug">0B</div>
  <div class="w-hug h-hug">0C</div>
  <div class="w-hug h-hug">1A</div>
  <div class="w-hug h-fill">1B</div>
  <div class="w-fill h-hug">1C</div>
  <div class="w-fill h-fill">2A</div>
  <div class="w-fill h-fill">2B</div>
  <div class="w-fill h-fill">2C</div>
</div>
```

<br>
<br>

#### 📐 Layout: Grid with items in the cell's Top Right

Use `layout-grid-tr` to align child elements at the top right of each cell in the grid.

![Example of layout-spaced-b](/docs/images/layout-example/layout-grid-tr.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-grid-tr grid-cols-3 gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <div class="w-hug h-hug">0A</div>
  <div class="w-hug h-hug">0B</div>
  <div class="w-hug h-hug">0C</div>
  <div class="w-hug h-hug">1A</div>
  <div class="w-hug h-fill">1B</div>
  <div class="w-fill h-hug">1C</div>
  <div class="w-fill h-fill">2A</div>
  <div class="w-fill h-fill">2B</div>
  <div class="w-fill h-fill">2C</div>
</div>
```

<br>
<br>

#### 📐 Layout: Grid with items in the cell's Middle Left

Use `layout-grid-ml` to align child elements at the middle left of each cell in the grid.

![Example of layout-spaced-b](/docs/images/layout-example/layout-grid-ml.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-grid-ml grid-cols-3 gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <div class="w-hug h-hug">0A</div>
  <div class="w-hug h-hug">0B</div>
  <div class="w-hug h-hug">0C</div>
  <div class="w-hug h-hug">1A</div>
  <div class="w-hug h-fill">1B</div>
  <div class="w-fill h-hug">1C</div>
  <div class="w-fill h-fill">2A</div>
  <div class="w-fill h-fill">2B</div>
  <div class="w-fill h-fill">2C</div>
</div>
```

<br>
<br>

#### 📐 Layout: Grid with items in the cell's Middle Center

Use `layout-grid-mc` to align child elements at the middle center of each cell in the grid.

![Example of layout-spaced-b](/docs/images/layout-example/layout-grid-mc.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-grid-mc grid-cols-3 gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <div class="w-hug h-hug">0A</div>
  <div class="w-hug h-hug">0B</div>
  <div class="w-hug h-hug">0C</div>
  <div class="w-hug h-hug">1A</div>
  <div class="w-hug h-fill">1B</div>
  <div class="w-fill h-hug">1C</div>
  <div class="w-fill h-fill">2A</div>
  <div class="w-fill h-fill">2B</div>
  <div class="w-fill h-fill">2C</div>
</div>
```

<br>
<br>

#### 📐 Layout: Grid with items in the cell's Middle Right

Use `layout-grid-mr` to align child elements at the middle right of each cell in the grid.

![Example of layout-spaced-b](/docs/images/layout-example/layout-grid-mr.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-grid-mr grid-cols-3 gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <div class="w-hug h-hug">0A</div>
  <div class="w-hug h-hug">0B</div>
  <div class="w-hug h-hug">0C</div>
  <div class="w-hug h-hug">1A</div>
  <div class="w-hug h-fill">1B</div>
  <div class="w-fill h-hug">1C</div>
  <div class="w-fill h-fill">2A</div>
  <div class="w-fill h-fill">2B</div>
  <div class="w-fill h-fill">2C</div>
</div>
```

<br>
<br>

#### 📐 Layout: Grid with items in the cell's Bottom Left

Use `layout-grid-bc` to align child elements at the bottom left of each cell in the grid.

![Example of layout-spaced-b](/docs/images/layout-example/layout-grid-bl.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-grid-bl grid-cols-3 gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <div class="w-hug h-hug">0A</div>
  <div class="w-hug h-hug">0B</div>
  <div class="w-hug h-hug">0C</div>
  <div class="w-hug h-hug">1A</div>
  <div class="w-hug h-fill">1B</div>
  <div class="w-fill h-hug">1C</div>
  <div class="w-fill h-fill">2A</div>
  <div class="w-fill h-fill">2B</div>
  <div class="w-fill h-fill">2C</div>
</div>
```

<br>
<br>

#### 📐 Layout: Grid with items in the cell's Bottom Center

Use `layout-grid-bc` to align child elements at the bottom center of each cell in the grid.

![Example of layout-spaced-b](/docs/images/layout-example/layout-grid-bc.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-grid-bc grid-cols-3 gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <div class="w-hug h-hug">0A</div>
  <div class="w-hug h-hug">0B</div>
  <div class="w-hug h-hug">0C</div>
  <div class="w-hug h-hug">1A</div>
  <div class="w-hug h-fill">1B</div>
  <div class="w-fill h-hug">1C</div>
  <div class="w-fill h-fill">2A</div>
  <div class="w-fill h-fill">2B</div>
  <div class="w-fill h-fill">2C</div>
</div>
```

<br>
<br>

#### 📐 Layout: Grid with items in the cell's Bottom Right

Use `layout-grid-br` to align child elements at the bottom right of each cell in the grid.

![Example of layout-spaced-b](/docs/images/layout-example/layout-grid-br.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-grid-br grid-cols-3 gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <div class="w-hug h-hug">0A</div>
  <div class="w-hug h-hug">0B</div>
  <div class="w-hug h-hug">0C</div>
  <div class="w-hug h-hug">1A</div>
  <div class="w-hug h-fill">1B</div>
  <div class="w-fill h-hug">1C</div>
  <div class="w-fill h-fill">2A</div>
  <div class="w-fill h-fill">2B</div>
  <div class="w-fill h-fill">2C</div>
</div>
```

<br/>

#### 📐 Layout: Inital HTML

Use `layout-initial-html` sets the html defaults using the CSS `inital` property.

<br/>

#### 📐 Layout: Revert HTML

Use `layout-revert-html` sets the html defaults using the CSS `revert` property.

<br/>
<hr/>

##### Component Resizing

<br/>

Controlling size and resizing behavior in CSS through the specification of properties on both parent and child elements can be challenging. ⛸️ Figured Layout CSS simplifies this process by giving control to the child component for resizing within the parent. This library shares the same opinion as Figma, advocating for child components to dictate their own resizing behavior.

🚨 Attention: The use of Tailwind CSS size utility classes such as h-full or w-full, h-{number}, and w-{number} may not produce expected results when combined with Figured Layout classes. This is due to the abstracted hiding complexity of setting width in flex-box, flex-direction, and grid.

### ↔️ Width

`w-hug` the element hugs the width of it's content.

`w-fill` the element fills the remaining width of it's parent element.

`w-fixed-{number}` fixed width based on sizes set in Tailwind CSS Config.

`w-fixed-[css-size]` fixed width based on Tailwind CSS JIT.

![Width Examples](docs/images/layout-example/width.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class="layout-packed-tl-x gap-4 p-2 overflow-hidden w-fill h-fixed-40 rounded-lg">
  <div class="w-hug h-hug">w-hug</div>
  <div class="w-fill h-hug">w-fill</div>
  <div class="w-fixed-44 h-hug">w-fixed-44</div>
  <div class="w-fixed-[160px] h-hug">w-fixed-[160px]</div>
</div>
```

### ↕ Height

`h-hug` the element hugs the height of it's content.

`h-fill` the element fills the remaining height of it's parent element.

`h-fixed-{number}` fixed height based on sizes set in Tailwind CSS Config.

`h-fixed-[css-size]` fixed height based on Tailwind CSS JIT.

![Height Examples](docs/images/layout-example/height.png)

##### HTML

<!-- prettier-ignore -->
```html
<div class=" gap-4 p-2 overflow-hidden w-fill h-hug rounded-lg">
  <div class="w-fill h-hug">h-hug</div>
  <div class="w-fill h-fill">h-fill</div>
  <div class="w-fill h-fixed-20">h-fixed-44</div>
  <div class="w-fill h-fixed-[64px]">h-fixed-[160px]</div>
</div>
```

<br/>

### 🔲 Size

Shorthand helper class for setting the same width and height property.

`s-hug` the element hugs the width and height of it's content.

`s-fill` the element fills the remaining width and height of it's parent element.

<br/>

##### Options

Note: To make things easy and consistne t Figured layout sets css the following overrides which can be configured off if need be :

###### Html and Body elements maximum a height and width

In most cases it's desirable to have the top most elements fill the entire viewport.

It can be disable by configuring one or both of the following:

```javascript
// ./tailwind.config.js
module.exports = {
  plugins: [
    require(@figured-layout-css/tailwindcss)({
      pageHeightDefaultFill: false,  // Default TRUE
      pageWidthDefaultFill: false,   // Default TRUE
    }),
  ],
};
```

###### Elements hug content for width and height by default

This overrides the default block and inline behavior of elements.

It can be disable by configuring one or both of the following:

```javascript
// ./tailwind.config.js
module.exports = {
  plugins: [
    require(@figured-layout-css/tailwindcss)({
      widthDefaultHug: false,     // Default TRUE
      heightDefaultHug: false,    // Default TRUE
    }),
  ],
};
```

###### Default layout

This allows you to set the layout behavior of all your elements, default is set to `layout-packed-tl-y` you can change it back to the default behavior by using either

- `layout-initial-html`: sets layout behavior to the default of the element.
- `layout-revert-html`: sets layout behavior to the value the property would have had if no changes had been made by the current style orgin.

```javascript
// ./tailwind.config.js
module.exports = {
  plugins: [
    require(@figured-layout-css/tailwindcss)({
      layoutDefault: 'layout-initial-html', // Default 'layout-packed-tl-y'
    }),
  ],
};
```

###### Disable all overrides

Allows you to reset all the above setting to the html defaults.

```javascript
// ./tailwind.config.js
module.exports = {
  plugins: [
    require(@figured-layout-css/tailwindcss)({
      ignoreAllResets: false, // Default TRUE
    }),
  ],
};
```

<br>

#### Demo

If you are interested in comparing layouts with and without check out the following Tailwind CSS play links:

- ❌ [Without Figured Layout](https://) [Coming Soon]

- ✅ [With Figured Layout](https://) [Coming Soon]

<br>

#### FAQs

This is a list of questions so far. Join the [Tailwind Discord]("https://tailwindcss.com/discord") for more and to share your ideas and feedback in the plugins channel.

<br>

##### Q: Do I need Tailwind CSS to use this plugin?

A: Short answer Yes - however we are working on a pure CSS file containing the core concepts

<br>

##### Q: Why not just learn how CSS Felxbox and Grid work?

A: Personally I have read the reference many times for over a decade and still don't remember which indicates these concepts as they are in the specification are intuative enough. Figma's model for thinking about layout is more intuative.

<br>

##### Q: What's with the name and the icon?

A: It's a multifacited pun, because I really enjoy needlessly deep puns:

- **Figured**
  - In reference _Figma_ because of the inspiration from Figma's Auto Layout
  - In reference to the shapes, structure etc
- **Figured Layout** playing on the word of Figured Out how to lay things out in css
- ⛸️ Ice skate becuase it alludes to figure skaters who are both elegent and precise.