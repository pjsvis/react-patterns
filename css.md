## css

- [unobtrusive scrollbar](https://codepen.io/zachleat/pen/oNvprpX)
- [focus-within](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-within)
- [focus-within using flexbox](https://stackoverflow.com/questions/21154616/on-input-focus-change-color-of-label-how)
- smooth easings from [david kouresh video](https://www.youtube.com/watch?v=zVbLR7rI8ZU) and [css-tricks article](https://css-tricks.com/animating-layouts-with-the-flip-technique/)
```css
.enter {
  animation-timing-function: cubic-beziez(0, 0.5, 0.5, 1);)
}

.move {
  animation-timing-function: cubic-beziez(0.5, 0, 0.5, 1);)
}

.exit {
  animation-timing-function: cubic-beziez(0.5, 0, 0, 1);)
}
```

```css
.sinful-layout-animation {
  transition height: 0.3s ease-in-out;
  /* no layout reflow */
  contain: layout;
}
```

### style links

```css
a[href$=".pdf"] {
  background: url('https://i.imgur.com/n8EHrrI.png')
  0 50% no-repeat;
  padding-left: 20px;
}
```

- [css grid demos](https://tobireif.com/demos/grid/) and [article](https://tobireif.com/posts/layout_fun_with_css_grid/)
- [more css grid](https://www.freecodecamp.org/news/css-grid-changes-how-we-can-think-about-structuring-our-content/?ref=heydesigner)
- [clickable area](https://ishadeed.com/article/clickable-area/)
- [theme-ui](https://theme-ui.com/) and [theme-ui types](https://github.com/DefinitelyTyped/DefinitelyTyped/blob/master/types/theme-ui/index.d.ts)
- [more chrome devtools tips](https://dev.to/lpellis/things-you-may-not-know-about-chrome-devtools-53k6)
