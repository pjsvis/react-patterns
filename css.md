## css

-  I'm also particularly impressed with the simplest of CSS that will make almost any webpage look good. [ref](https://responsivedesign.is/articles/rwd-weekly-433/?utm_source=Responsive+Design+Weekly&utm_campaign=4e437a1ff5-RWD_Newsletter_433&utm_medium=email&utm_term=0_df65b6d7c8-4e437a1ff5-52081993)

```css
html {
  max-width:70ch;
  padding:2ch;
  margin:auto;
  color:#333;
  font-size:1.2em;
}
```

- [css frameworks](https://alexmercedcoder.medium.com/ultimate-2021-list-of-css-frameworks-and-component-libraries-for-angular-react-vue-and-svelte-696ef7ca0032)
- [things you can do with css now](https://www.smashingmagazine.com/2021/02/things-you-can-do-with-css-today/)
- [just in case mindset](https://ishadeed.com/article/the-just-in-case-mindset-css/)
- [custom css styles for form inputs](https://moderncss.dev/custom-css-styles-for-form-inputs-and-textareas/)
- [myths of color contrast accessibility](https://uxmovement.com/buttons/the-myths-of-color-contrast-accessibility/)
- [arrow type recursive mono & sans](https://github.com/arrowtype/recursive)
- [fixing font variability inheritance](https://pixelambacht.nl/2019/fixing-variable-font-inheritance/)
- [the evolution of material-design's text field](https://medium.com/google-design/the-evolution-of-material-designs-text-fields-603688b3fe03)
- [grid cheatsheet](http://grid.malven.co/)
- [lobotomised owl selectors](https://alistapart.com/article/axiomatic-css-and-lobotomized-owls/) for sensible margins -doesn't seem to work well with flex
- [ascii emoticons](https://upli.st/l/list-of-all-ascii-emoticons) ( ͡° ͜ʖ ͡°)
- [unobtrusive scrollbar](https://codepen.io/zachleat/pen/oNvprpX)
- [focus-within](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-within)
- [focus-within using flexbox](https://stackoverflow.com/questions/21154616/on-input-focus-change-color-of-label-how)
- smooth easings from [david kouresh video](https://www.youtube.com/watch?v=zVbLR7rI8ZU) and [css-tricks article](https://css-tricks.com/animating-layouts-with-the-flip-technique/)
```css
.enter {
  animation-timing-function: cubic-bezier(0, 0.5, 0.5, 1);)
}

.move {
  animation-timing-function: cubic-bezier(0.5, 0, 0.5, 1);)
}

.exit {
  animation-timing-function: cubic-bezier(0.5, 0, 0, 1);)
}

.sinful-layout-animation {
  transition height: 0.3s ease-in-out;
  /* no layout reflow */
  contain: layout;
}
```

- [Using easing for more than just CSS transitions](https://kilianvalkhof.com/2020/css-html/using-easing-for-more-than-just-css-transitions/)
- [printer friendly pages](https://www.sitepoint.com/css-printer-friendly-pages/)

### style links

```css
a[href$=".pdf"] {
  background: url('https://i.imgur.com/n8EHrrI.png')
  0 50% no-repeat;
  padding-left: 20px;
}
```

- [grid layout techniques](https://www.youtube.com/watch?v=KOvGeFUHAC0)
- [responsive tables](https://uglyduck.ca/responsive-tables/) with minimal css
- [css grid demos](https://tobireif.com/demos/grid/) and [article](https://tobireif.com/posts/layout_fun_with_css_grid/)
- [more css grid](https://www.freecodecamp.org/news/css-grid-changes-how-we-can-think-about-structuring-our-content/?ref=heydesigner)
- [clickable area](https://ishadeed.com/article/clickable-area/)
- [theme-ui](https://theme-ui.com/) and [theme-ui types](https://github.com/DefinitelyTyped/DefinitelyTyped/blob/master/types/theme-ui/index.d.ts)
- [more chrome devtools tips](https://dev.to/lpellis/things-you-may-not-know-about-chrome-devtools-53k6)
- [managing layers with css variables](https://dev.to/seibmacdaniel/an-incredibly-easy-way-to-manage-layers-in-scss-42c1)
- [small css tips](https://dev.to/seibmacdaniel/3-easy-to-apply-css-improvements-that-you-can-use-in-your-project-right-now-208e)
