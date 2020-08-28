# Prism Theme - One Light and One Dark

<p>
  <a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License: MIT"/></a>
</p>

This package provides light and dark themes based on Atom's [One Light](https://github.com/atom/one-light-syntax) and [One Dark](https://github.com/atom/one-dark-syntax) themes, respectively. 

*Note*: Due to some limitations of Prism's syntax highlighting, there will be slight differences in syntax highlighting between these themes and the originals provided by Atom.

## Installation

```bash
$ npm install --save prism-theme-one-light-dark
```

If the web application uses the Webpack loaders [`style-loader`](https://webpack.js.org/loaders/style-loader/) and [`css-loader`](https://webpack.js.org/loaders/css-loader/), then the themes can be imported like a module.

Import One Dark theme.

```js
import 'prism-theme-one-light-dark/prism-onedark.css';
```

Import One Light theme.

```js
import 'prism-theme-one-light-dark/prism-onelight.css';
```

## Toggle Between Themes (Webpack-Based Projects)

If the web application supports toggling between light and dark themes, then to inject the corresponding Prism theme, use [`raw-loader`](https://webpack.js.org/loaders/raw-loader/), a Webpack loader for importing a file as a raw text string.

*Note*: Since Webpack is one of the core software packages that powers Gatsby, Gatsby automatically provides `raw-loader` to developers.

```js
// Assumption: `theme` argument can only be set to "dark" or "light."
function togglePrismTheme(theme) {
  let prismTheme;

  try {
    prismTheme = require(`!raw-loader!prism-theme-one-light-dark/prism-one${theme}.css`); 
  } catch(e) {
    console.error(e);
  }

  return prismTheme;
}
```

## Customization

To customize the themes:

1. Fork this repository [here](https://github.com/kenchandev/prism-theme-one-light-dark/fork).
2. Place the custom SCSS code in `src/overrides.scss`.
3. Execute `npm run build` to generate the customized themes.

## Preview

Below are screenshots of each theme applied to a snippet of TypeScript code.

For additional previews of other code snippets (Markup, SCSS and JavaScript), download and open the demo files in the `demo` folder.

### TypeScript

![One Light Theme - TypeScript Preview](https://www.dl.dropboxusercontent.com/s/t4058tep40c690j/Screen%20Shot%202020-08-26%20at%2010.55.08%20PM.png)

![One Dark Theme - TypeScript Preview](https://www.dl.dropboxusercontent.com/s/8vbqbskp3sgyu83/Screen%20Shot%202020-08-26%20at%2010.56.12%20PM.png)

### License

MIT