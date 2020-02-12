##### Simple Bundling JS Server & Web Boilerplate


###### Goals:
* Simple/Minimal
* Reload webpage for frontend change
* Reload server for backend change


###### Setup details:
* Backend uses expressjs for the server
* The express view engine used is [liquid](https://github.com/harttle/liquidjs/wiki/Use-with-Expressjs)
* Using [nodemon](https://github.com/remy/nodemon/) for reloading the server on backend changes
* [Parcel](https://parceljs.org/hmr.html) for reloading the web page on frontend changes
* Parcel also minifies on build
* Using [jest](https://jestjs.io/) for tests
* The `run-s` in the package.json script is just a shortcut for the `npm-run-all` program. It runs the scripts in serial (one after the other).
* We are using the following babel plugins, presets and macros:
  * `@babel/preset-env` https://babeljs.io/docs/en/babel-preset-env
  * `@babel/preset-react` https://babeljs.io/docs/en/babel-preset-react
  * `inline-replace-variables` to replace the `ISDEV` variable with whether or not `process.env.NODE_ENV !== 'production'` : https://github.com/wssgcg1213/babel-plugin-inline-replace-variables
  * `param.macro`  https://github.com/citycide/param.macro
  * `ms.macro` https://github.com/knpwrs/ms.macro#readme
* The `watchreload` key in package.json is for [parcel-plugin-watch-reload](https://github.com/hirasso/parcel-plugin-watch-reload), it allows us to reload the page on server change too.

###### Additional notes:
* Try to lessen the use of external libraries as it all adds up
* Can use the [dynamic imports](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import#Dynamic_Imports) to load external libraries after the page has loaded
