Demonstrates a bug in OnsenUI for React.

## Steps:

1. clone this repo
1. run `npm install` to install packages
1. run `npm run build` to build the app

## Expected outcome:

1. Running `npm run build` should succeed without errors and generate a `compiled.js` file. The actual command being run is: `browserify source.jsx -o compiled.js -t [ babelify --presets [ env react ] ]` as per browserify/babelify docs (see `package.json`).
1. Opening index.html in a browser should display "asd".

## Actual outcome:

Running `npm run build` triggers the error below, where `[project-path]` is the absolute path to the project location on disk. 

```
Error: Cannot find module './factoryWithTypeCheckers' from '[project-path]\node_modules\react-onsenui\dist'
    at [project-path]\node_modules\browser-resolve\node_modules\resolve\lib\async.js:55:21
    at load ([project-path]\node_modules\browser-resolve\node_modules\resolve\lib\async.js:69:43)
    at onex ([project-path]\node_modules\browser-resolve\node_modules\resolve\lib\async.js:92:31)
    at [project-path]\node_modules\browser-resolve\node_modules\resolve\lib\async.js:22:47
    at FSReqWrap.oncomplete (fs.js:114:15)
```
