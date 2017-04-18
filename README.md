# npmdoc-docxtemplater

#### api documentation for  [docxtemplater (v3.0.11)](https://github.com/open-xml-templating/docxtemplater#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-docxtemplater.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-docxtemplater) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-docxtemplater.svg)](https://travis-ci.org/npmdoc/node-npmdoc-docxtemplater)

#### .docx generator working with templates and data (like Mustache)

[![NPM](https://nodei.co/npm/docxtemplater.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/docxtemplater)

- [https://npmdoc.github.io/node-npmdoc-docxtemplater/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-docxtemplater/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-docxtemplater/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-docxtemplater/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-docxtemplater/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-docxtemplater/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Edgar Hipp"
    },
    "bin": {
        "docxtemplater": "./js/cli.js"
    },
    "bugs": {
        "url": "https://github.com/open-xml-templating/docxtemplater/issues"
    },
    "contributors": [
        {
            "name": "Edgar Hipp"
        }
    ],
    "dependencies": {
        "xmldom": "^0.1.27"
    },
    "description": ".docx generator working with templates and data (like Mustache)",
    "devDependencies": {
        "angular-expressions": "^0.3.0",
        "babel-cli": "^6.22.2",
        "babel-eslint": "^7.1.0",
        "babel-preset-es2015": "^6.22.0",
        "browserify": "^14.0.0",
        "chai": "^3.5.0",
        "docxtemplater-image-module": "^3.0.2",
        "eslint": "^3.14.1",
        "eslint-plugin-dependencies": "^2.2.0",
        "image-size": "^0.5.1",
        "istanbul": "^0.4.5",
        "jszip": "^2.6.1",
        "lodash": "^4.17.4",
        "mkdirp": "^0.5.1",
        "mocha": "^3.2.0",
        "mustache": "^2.1.3",
        "rimraf": "^2.5.3",
        "uglifyjs": "^2.4.10"
    },
    "directories": {},
    "dist": {
        "shasum": "fab5fcd289a7e435a95aa4d04d892eb9fd20ad28",
        "tarball": "https://registry.npmjs.org/docxtemplater/-/docxtemplater-3.0.11.tgz"
    },
    "engines": {
        "node": ">=0.10"
    },
    "gitHead": "1beec56d90882a262fdb86e4586e124cafc7f744",
    "homepage": "https://github.com/open-xml-templating/docxtemplater#readme",
    "keywords": [
        "docx",
        "templates",
        "generation",
        "microsoft word"
    ],
    "license": "MIT",
    "main": "js/docxtemplater.js",
    "maintainers": [
        {
            "name": "edi9999"
        }
    ],
    "name": "docxtemplater",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git+https://github.com/open-xml-templating/docxtemplater.git"
    },
    "scripts": {
        "babel": "babel es6 --out-dir js",
        "browserify": "npm run browserify:test && npm run browserify:lib && npm run browserify:demo",
        "browserify:demo": "node create-min.js examples/main.js > browser/main.js",
        "browserify:lib": "node create-min.js js/docxtemplater.js > build/docxtemplater.js",
        "browserify:test": "browserify --insert-global-vars __filename,__dirname -r ./js/tests/docxtemplater.js -s DocxtemplaterTest > browser/docxtemplater-test.js",
        "check-casing": "./check-casing.bash",
        "compile": "npm run convertto:es5 && node examples/compile-site.js",
        "convertto:es5": "rimraf js -rf && mkdirp js && npm run babel",
        "convertto:es5:watch": "npm run babel -- --watch",
        "generate:doc": "cd docs; rm build/ -rf ; make html",
        "lint": "./check-casing.bash && eslint .",
        "mocha": "mocha js/tests/docxtemplater.js",
        "preversion": "npm test && npm run check-casing && npm run lint && rimraf build && mkdirp build && npm run compile && npm run browserify && npm run uglify && npm run verifypublishsize",
        "profile": "./profile.bash",
        "test": "npm run convertto:es5 && npm run mocha",
        "test:coverage": "istanbul cover _mocha --  es6/tests/docxtemplater.js",
        "test:es5": "npm test",
        "test:es6": "mocha es6/tests/docxtemplater.js",
        "uglify": "npm run uglify:lib && npm run uglify:demo",
        "uglify:demo": "uglifyjs browser/main.js > browser/main.min.js",
        "uglify:lib": "uglifyjs build/docxtemplater.js > build/docxtemplater.min.js",
        "verifypublishsize": "./verifypublishsize.bash"
    },
    "version": "3.0.11"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
