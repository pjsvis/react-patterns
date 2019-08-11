## svelte

- [svelte draggable grid](https://github.com/vaheqelyan/svelte-grid)
- [textarea autosize](https://jsbin.com/qizepev/edit?html,css,js,output) with css and js
- [purgeCss](https://github.com/FullHuman/purgecss)
- [tailwind css template](https://github.com/alexdilley/tailwindcss-sveltejs-component-template)
- [svelte material ui](https://github.com/hperrin/svelte-material-ui)
- [star wars resources](https://www.telerik.com/blogs/5-star-wars-resources-for-developers) see also lorem ispum stuff
- [smelte crud app](https://github.com/Kiho/smelte-crud-app)
- [checkbox treeview](https://svelte.dev/repl/3db8fdf6abfe4b2097a419ebf8e8eca7?version=3.6.10)
- [use web components](https://www.robinwieruch.de/react-web-components/) in react
- [smelte](https://smelte.matyunya.now.sh) material design components for svelte)
- [svelte](https://svelte.dev)
- [webcomponents.dev](https://webcomponents.dev)
- [awesome svelte](https://github.com/CalvinWalzel/awesome-svelte)
- [cosmic js](https://cosmicjs.com/headless-cms) headless cms
- [svelte and cosmic js](https://cosmicjs.com/articles/build-a-simple-todo-app-using-svelte-and-cosmic-js)
- [netlify](https://www.netlify.com/)
- [reactive programming with svelte](https://blog.logrocket.com/truly-reactive-programming-with-svelte-3-0-321b49b75969/)

## .eslintrc.js

- [ref](https://gist.github.com/jimjones26/ab4f680aa26fd952185c19766e79178b)

```json
/* module.exports = {
  env: {
    browser: true,
    es6: true,
  },
  extends: [
    'airbnb-base',
  ],
  globals: {
    Atomics: 'readonly',
    SharedArrayBuffer: 'readonly',
  },
  parserOptions: {
    ecmaVersion: 2018,
    sourceType: 'module',
  },
  rules: {
  },
};
 */
module.exports = {
  extends: [
    'airbnb-base',
    'eslint:recommended',
    'plugin:import/errors',
    'plugin:import/typescript',
    'plugin:import/warnings',
    'prettier'
  ],
  parser: 'babel-eslint',
  parserOptions: {
    ecmaVersion: 2019,
    sourceType: 'module'
  },
  env: {
    browser: true,
    node: true,
    jest: true,
    es6: true
  },
  root: true,
  rules: {
    'import/prefer-default-export': 2,
    semi: ['error', 'never'],
    'prettier/prettier': [
      2,
      {
        arrowParens: 'avoid',
        bracketSpacing: true,
        endOfLine: 'lf',
        printWidth: 80,
        semi: false,
        singleQuote: true,
        svelteBracketNewLine: true,
        svelteSortOrder: 'scripts-styles-markup',
        svelteStrictMode: true,
        tabWidth: 2,
        useTabs: false
      }
    ]
  },
  plugins: ['html', 'prettier', 'svelte3'],
  overrides: [
    {
      files: ['**/*.svelte'],
      processor: 'svelte3/svelte3'
    }
  ]
```
