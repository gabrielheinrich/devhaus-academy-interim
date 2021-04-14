# Media Queries & Responsive Web Design

## The meta viewport tag

The HTML boilerplate created with emmet contains the following meta tag:

```html
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
```
- `width=device-width`: instructs the page to match the screen's width in device independent pixels [Documentation](https://developer.mozilla.org/en-US/docs/Mozilla/Mobile/Viewport_meta_tag)
- `initial-scale=1.0`: instructs browser to establish a 1:1 relation between device independen pixels and CSS pixels

[Device Independent Pixels vs. Hardware Pixels](https://www.youtube.com/watch?v=6P9uLyvcd3Y)

CSS pixels are what we are used to working with most of the time and the only one we need to worry about.

---

## Media Queries

A responsive website changes based on the size of the device that is used to visit the site. This means that your sites need to apply different styles (font sizes, layouts etc.) for different devices. **Media Queries** are an easy way to selectively apply CSS based on the viewport width, height or device pixel ratio. In this course we are going to focus on the width of a device, namely the 3 most prevalent device types smart phone, tablet and desktop.

### Defining a media query

#### In HTML

We can set a `media` attribute in a link to a stylesheet.
The styles in the `over500.css` stylesheet are only being applied if the viewport is larger than 500px.

```html
  <link 
    media="screen and (min-width:500px)" 
    rel="stylesheet" 
    href="over500.css" />
```

#### In CSS

```css
@media screen and (min-width: 500px) {
    body {
        background-color: paleturquoise;
    }
}
```

### Picking the right breakpoints

Responsive Web Design is an art, not a science. Many times you have to go through trial and error, do mockups and try different sizes of elements before determining the ideal breakpoints. If needed, set individual breakpoints for certain elements.

Generally we can use the following setup for most of our projects:

```html
<!-- mobile styling  -->
<link rel="stylesheet" media="screen and (max-width:750px)" href="../styles/mobile.css">
<!-- tablet styling -->
<link rel="stylesheet" media="screen and (min-width:751px)" href="../styles/tablet.css">
<!-- desktop styling -->
<link rel="stylesheet" media="screen and (min-width:1150px)" href="../styles/desktop.css">

```

or respectively in CSS

```css
@media screen and (max-width: 750px) {
    /* mobile styling */
}

@media screen and (min-width: 751px) {
    /* tablet styling */
}

@media screen and (min-width: 1150px) {
    /* desktop styling */
}
```

--- 

## Exercises
**Flexbox Layout**
- [Flexbox Review Part 1](https://www.youtube.com/watch?v=iazYC5ffw8Y)
- [Flexbox Review Part 2](https://www.youtube.com/watch?v=JepRvCVL2WI)
- [Flex-Box Challenge](https://www.youtube.com/watch?v=acvExar2axw)

---

## Resources
- [Common Responsive Design Patterns](https://developers.google.com/web/fundamentals/design-and-ux/responsive/patterns)
- [Media Queries MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries) 
- [How to build a responsive nav bar (simple)](https://medium.com/@dineshsri28/how-to-build-a-responsive-navigation-bar-for-mobile-and-desktop-using-html-css-and-javascript-e72f0e887f0d)