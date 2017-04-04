# api documentation for  [docxtemplater (v3.0.11)](https://github.com/open-xml-templating/docxtemplater#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-docxtemplater.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-docxtemplater) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-docxtemplater.svg)](https://travis-ci.org/npmdoc/node-npmdoc-docxtemplater)
#### .docx generator working with templates and data (like Mustache)

[![NPM](https://nodei.co/npm/docxtemplater.png?downloads=true)](https://www.npmjs.com/package/docxtemplater)

[![apidoc](https://npmdoc.github.io/node-npmdoc-docxtemplater/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-docxtemplater_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-docxtemplater/build/apidoc.html)

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
            "name": "edi9999",
            "email": "hipp.edg@gmail.com"
        }
    ],
    "name": "docxtemplater",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
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



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module docxtemplater](#apidoc.module.docxtemplater)
1.  [function <span class="apidocSignatureSpan">docxtemplater.</span>XmlMatcher (content, tagsXmlArray)](#apidoc.element.docxtemplater.XmlMatcher)
1.  [function <span class="apidocSignatureSpan">docxtemplater.</span>XmlTemplater (content, options)](#apidoc.element.docxtemplater.XmlTemplater)
1.  [function <span class="apidocSignatureSpan">docxtemplater.</span>scope_manager (options)](#apidoc.element.docxtemplater.scope_manager)
1.  object <span class="apidocSignatureSpan">docxtemplater.</span>DocUtils
1.  object <span class="apidocSignatureSpan">docxtemplater.</span>DocUtils.defaults
1.  object <span class="apidocSignatureSpan">docxtemplater.</span>DocUtils.traits
1.  object <span class="apidocSignatureSpan">docxtemplater.</span>Errors
1.  object <span class="apidocSignatureSpan">docxtemplater.</span>FileTypeConfig
1.  object <span class="apidocSignatureSpan">docxtemplater.</span>lexer
1.  object <span class="apidocSignatureSpan">docxtemplater.</span>parser

#### [module docxtemplater.DocUtils](#apidoc.module.docxtemplater.DocUtils)
1.  [function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>cloneDeep (obj)](#apidoc.element.docxtemplater.DocUtils.cloneDeep)
1.  [function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>concatArrays (arrays)](#apidoc.element.docxtemplater.DocUtils.concatArrays)
1.  [function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>convertSpaces (s)](#apidoc.element.docxtemplater.DocUtils.convertSpaces)
1.  [function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>decodeUtf8 (s)](#apidoc.element.docxtemplater.DocUtils.decodeUtf8)
1.  [function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>encodeUtf8 (s)](#apidoc.element.docxtemplater.DocUtils.encodeUtf8)
1.  [function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>escapeRegExp (str)](#apidoc.element.docxtemplater.DocUtils.escapeRegExp)
1.  [function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>getLeft (parsed, element, index)](#apidoc.element.docxtemplater.DocUtils.getLeft)
1.  [function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>getRight (parsed, element, index)](#apidoc.element.docxtemplater.DocUtils.getRight)
1.  [function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>mergeObjects ()](#apidoc.element.docxtemplater.DocUtils.mergeObjects)
1.  [function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>moduleWrapper (module)](#apidoc.element.docxtemplater.DocUtils.moduleWrapper)
1.  [function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>pregMatchAll (regex, content)](#apidoc.element.docxtemplater.DocUtils.pregMatchAll)
1.  [function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>sizeOfObject (obj)](#apidoc.element.docxtemplater.DocUtils.sizeOfObject)
1.  [function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>str2xml (str, errorHandler)](#apidoc.element.docxtemplater.DocUtils.str2xml)
1.  [function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>utf8ToWord (string)](#apidoc.element.docxtemplater.DocUtils.utf8ToWord)
1.  [function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>wordToUtf8 (string)](#apidoc.element.docxtemplater.DocUtils.wordToUtf8)
1.  [function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>xml2str (xmlNode)](#apidoc.element.docxtemplater.DocUtils.xml2str)
1.  object <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>charMap
1.  object <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>charMapRegexes
1.  object <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>defaults
1.  object <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>traits

#### [module docxtemplater.DocUtils.defaults](#apidoc.module.docxtemplater.DocUtils.defaults)
1.  [function <span class="apidocSignatureSpan">docxtemplater.DocUtils.defaults.</span>nullGetter (part)](#apidoc.element.docxtemplater.DocUtils.defaults.nullGetter)
1.  [function <span class="apidocSignatureSpan">docxtemplater.DocUtils.defaults.</span>parser ()](#apidoc.element.docxtemplater.DocUtils.defaults.parser)
1.  object <span class="apidocSignatureSpan">docxtemplater.DocUtils.defaults.</span>delimiters

#### [module docxtemplater.DocUtils.traits](#apidoc.module.docxtemplater.DocUtils.traits)
1.  [function <span class="apidocSignatureSpan">docxtemplater.DocUtils.traits.</span>expandToOne (postparsed, options)](#apidoc.element.docxtemplater.DocUtils.traits.expandToOne)
1.  [function <span class="apidocSignatureSpan">docxtemplater.DocUtils.traits.</span>getExpandToDefault (parts)](#apidoc.element.docxtemplater.DocUtils.traits.getExpandToDefault)

#### [module docxtemplater.Errors](#apidoc.module.docxtemplater.Errors)
1.  [function <span class="apidocSignatureSpan">docxtemplater.Errors.</span>XTError (message)](#apidoc.element.docxtemplater.Errors.XTError)
1.  [function <span class="apidocSignatureSpan">docxtemplater.Errors.</span>XTInternalError (message)](#apidoc.element.docxtemplater.Errors.XTInternalError)
1.  [function <span class="apidocSignatureSpan">docxtemplater.Errors.</span>XTScopeParserError (message)](#apidoc.element.docxtemplater.Errors.XTScopeParserError)
1.  [function <span class="apidocSignatureSpan">docxtemplater.Errors.</span>XTTemplateError (message)](#apidoc.element.docxtemplater.Errors.XTTemplateError)

#### [module docxtemplater.lexer](#apidoc.module.docxtemplater.lexer)
1.  [function <span class="apidocSignatureSpan">docxtemplater.lexer.</span>parse (xmlparsed, delimiters)](#apidoc.element.docxtemplater.lexer.parse)
1.  [function <span class="apidocSignatureSpan">docxtemplater.lexer.</span>xmlparse (content, xmltags)](#apidoc.element.docxtemplater.lexer.xmlparse)

#### [module docxtemplater.parser](#apidoc.module.docxtemplater.parser)
1.  [function <span class="apidocSignatureSpan">docxtemplater.parser.</span>parse (lexed, modules)](#apidoc.element.docxtemplater.parser.parse)
1.  [function <span class="apidocSignatureSpan">docxtemplater.parser.</span>postparse (parsed, modules)](#apidoc.element.docxtemplater.parser.postparse)

#### [module docxtemplater.scope_manager](#apidoc.module.docxtemplater.scope_manager)
1.  [function <span class="apidocSignatureSpan">docxtemplater.</span>scope_manager (options)](#apidoc.element.docxtemplater.scope_manager.scope_manager)
1.  [function <span class="apidocSignatureSpan">docxtemplater.scope_manager.</span>createBaseScopeManager (_ref)](#apidoc.element.docxtemplater.scope_manager.createBaseScopeManager)



# <a name="apidoc.module.docxtemplater"></a>[module docxtemplater](#apidoc.module.docxtemplater)

#### <a name="apidoc.element.docxtemplater.XmlMatcher"></a>[function <span class="apidocSignatureSpan">docxtemplater.</span>XmlMatcher (content, tagsXmlArray)](#apidoc.element.docxtemplater.XmlMatcher)
- description and source-code
```javascript
XmlMatcher = function (content, tagsXmlArray) {
	return DocUtils.cloneDeep(memoized(content, tagsXmlArray));
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.docxtemplater.XmlTemplater"></a>[function <span class="apidocSignatureSpan">docxtemplater.</span>XmlTemplater (content, options)](#apidoc.element.docxtemplater.XmlTemplater)
- description and source-code
```javascript
function XmlTemplater(content, options) {
		_classCallCheck(this, XmlTemplater);

		this.fromJson(options);
		this.setModules({ inspect: { filePath: this.filePath } });
		this.load(content);
	}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.docxtemplater.scope_manager"></a>[function <span class="apidocSignatureSpan">docxtemplater.</span>scope_manager (options)](#apidoc.element.docxtemplater.scope_manager)
- description and source-code
```javascript
function ScopeManager(options) {
		_classCallCheck(this, ScopeManager);

		this.scopePath = options.scopePath;
		this.scopeList = options.scopeList;
		this.parser = options.parser;
	}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.docxtemplater.DocUtils"></a>[module docxtemplater.DocUtils](#apidoc.module.docxtemplater.DocUtils)

#### <a name="apidoc.element.docxtemplater.DocUtils.cloneDeep"></a>[function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>cloneDeep (obj)](#apidoc.element.docxtemplater.DocUtils.cloneDeep)
- description and source-code
```javascript
cloneDeep = function (obj) {
	return JSON.parse(JSON.stringify(obj));
}
```
- example usage
```shell
...
	});
	return handleRecursiveCase(res);
}

var memoized = memoize(xmlMatcher);

module.exports = function (content, tagsXmlArray) {
	return DocUtils.cloneDeep(memoized(content, tagsXmlArray));
};
...
```

#### <a name="apidoc.element.docxtemplater.DocUtils.concatArrays"></a>[function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>concatArrays (arrays)](#apidoc.element.docxtemplater.DocUtils.concatArrays)
- description and source-code
```javascript
concatArrays = function (arrays) {
	return arrays.reduce(function (result, array) {
		Array.prototype.push.apply(result, array);
		return result;
	}, []);
}
```
- example usage
```shell
...
		position: start === 1 ? "start" : "end"
	};
}

function tagMatcher(content, textMatchArray, othersMatchArray) {
	var cursor = 0;
	var contentLength = content.length;
	var allMatches = DocUtils.concatArrays([textMatchArray.map(function (tag) {
		return { tag: tag, text: true };
	}), othersMatchArray.map(function (tag) {
		return { tag: tag, text: false };
	})]).reduce(function (allMatches, t) {
		allMatches[t.tag] = t.text;
		return allMatches;
	}, {});
...
```

#### <a name="apidoc.element.docxtemplater.DocUtils.convertSpaces"></a>[function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>convertSpaces (s)](#apidoc.element.docxtemplater.DocUtils.convertSpaces)
- description and source-code
```javascript
convertSpaces = function (s) {
	return s.replace(spaceRegexp, " ");
}
```
- example usage
```shell
...
var _render = require("./render.js");

function _getFullText(content, tagsXmlArray) {
	var matcher = xmlMatcher(content, tagsXmlArray);
	var result = matcher.matches.map(function (match) {
		return match.array[2];
	});
	return DocUtils.wordToUtf8(DocUtils.convertSpaces(result.join("")));
}

module.exports = function () {
	function XmlTemplater(content, options) {
		_classCallCheck(this, XmlTemplater);

		this.fromJson(options);
...
```

#### <a name="apidoc.element.docxtemplater.DocUtils.decodeUtf8"></a>[function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>decodeUtf8 (s)](#apidoc.element.docxtemplater.DocUtils.decodeUtf8)
- description and source-code
```javascript
decodeUtf8 = function (s) {
	try {
		if (s === undefined) {
			return undefined;
		}
		// replace Ascii 160 space by the normal space, Ascii 32
		return decodeURIComponent(escape(DocUtils.convertSpaces(s)));
	} catch (e) {
		var err = new Error("End");
		err.properties.data = s;
		err.properties.explanation = "Could not decode string to UTF8";
		throw err;
	}
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.docxtemplater.DocUtils.encodeUtf8"></a>[function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>encodeUtf8 (s)](#apidoc.element.docxtemplater.DocUtils.encodeUtf8)
- description and source-code
```javascript
encodeUtf8 = function (s) {
	return unescape(encodeURIComponent(s));
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.docxtemplater.DocUtils.escapeRegExp"></a>[function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>escapeRegExp (str)](#apidoc.element.docxtemplater.DocUtils.escapeRegExp)
- description and source-code
```javascript
escapeRegExp = function (str) {
	return str.replace(regexStripRegexp, "\\$&");
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.docxtemplater.DocUtils.getLeft"></a>[function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>getLeft (parsed, element, index)](#apidoc.element.docxtemplater.DocUtils.getLeft)
- description and source-code
```javascript
getLeft = function (parsed, element, index) {
	for (var i = index; i >= 0; i--) {
		var part = parsed[i];
		if (part.value.indexOf("<" + element) === 0 && [">", " "].indexOf(part.value[element.length + 1]) !== -1) {
			return i;
		}
	}
	throwXmlTagNotFound({ position: "left", element: element, parsed: parsed, index: index });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.docxtemplater.DocUtils.getRight"></a>[function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>getRight (parsed, element, index)](#apidoc.element.docxtemplater.DocUtils.getRight)
- description and source-code
```javascript
getRight = function (parsed, element, index) {
	for (var i = index, l = parsed.length; i < l; i++) {
		var part = parsed[i];
		if (part.value === "</" + element + ">") {
			return i;
		}
	}
	throwXmlTagNotFound({ position: "right", element: element, parsed: parsed, index: index });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.docxtemplater.DocUtils.mergeObjects"></a>[function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>mergeObjects ()](#apidoc.element.docxtemplater.DocUtils.mergeObjects)
- description and source-code
```javascript
mergeObjects = function () {
	var resObj = {};
	var obj = void 0,
	    keys = void 0;
	for (var i = 0; i < arguments.length; i += 1) {
		obj = arguments[i];
		keys = Object.keys(obj);
		for (var j = 0; j < keys.length; j += 1) {
			resObj[keys[j]] = obj[keys[j]];
		}
	}
	return resObj;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.docxtemplater.DocUtils.moduleWrapper"></a>[function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>moduleWrapper (module)](#apidoc.element.docxtemplater.DocUtils.moduleWrapper)
- description and source-code
```javascript
moduleWrapper = function (module) {
	var defaults = {
		set: emptyFun,
		parse: emptyFun,
		render: emptyFun,
		getTraits: emptyFun,
		optionsTransformer: identity,
		getRenderedMap: identity,
		postparse: identity
	};
	if (Object.keys(defaults).every(function (key) {
		return !module[key];
	})) {
		throw new Error("This module cannot be wrapped, because it doesn't define any of the necessary functions");
	}
	Object.keys(defaults).forEach(function (key) {
		module[key] = module[key] || defaults[key];
	});
	return module;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.docxtemplater.DocUtils.pregMatchAll"></a>[function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>pregMatchAll (regex, content)](#apidoc.element.docxtemplater.DocUtils.pregMatchAll)
- description and source-code
```javascript
pregMatchAll = function (regex, content) {
	<span class="apidocCodeCommentSpan">/* regex is a string, content is the content. It returns an array of all matches with their offset, for example:
 	 regex=la
 	 content=lolalolilala
 returns: [{array: {0: 'la'},offset: 2},{array: {0: 'la'},offset: 8},{array: {0: 'la'} ,offset: 10}]
 */
</span>	var matchArray = [];
	var match = void 0;
	while ((match = regex.exec(content)) != null) {
		matchArray.push({ array: match, offset: match.index });
	}
	return matchArray;
}
```
- example usage
```shell
...

function xmlMatcher(content, tagsXmlArray) {
	var res = {};
	res.content = content;
	res.tagsXmlArray = tagsXmlArray;
	res.tagsXmlArrayJoined = res.tagsXmlArray.join("|");
	var regexp = new RegExp("(<(?:" + res.tagsXmlArrayJoined + ")[^>]*>)([^<>]*)</(?:" + res.tagsXmlArrayJoined + ")>", "g");
	res.matches = DocUtils.pregMatchAll(regexp, res.content);
	res.charactersAddedCumulative = res.matches.map(function () {
		return 0;
	});
	res.charactersAdded = res.matches.map(function () {
		return 0;
	});
	return handleRecursiveCase(res);
...
```

#### <a name="apidoc.element.docxtemplater.DocUtils.sizeOfObject"></a>[function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>sizeOfObject (obj)](#apidoc.element.docxtemplater.DocUtils.sizeOfObject)
- description and source-code
```javascript
sizeOfObject = function (obj) {
	return Object.keys(obj).length;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.docxtemplater.DocUtils.str2xml"></a>[function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>str2xml (str, errorHandler)](#apidoc.element.docxtemplater.DocUtils.str2xml)
- description and source-code
```javascript
str2xml = function (str, errorHandler) {
	var parser = new DOMParser({ errorHandler: errorHandler });
	return parser.parseFromString(str, "text/xml");
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.docxtemplater.DocUtils.utf8ToWord"></a>[function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>utf8ToWord (string)](#apidoc.element.docxtemplater.DocUtils.utf8ToWord)
- description and source-code
```javascript
utf8ToWord = function (string) {
	if (typeof string !== "string") {
		string = string.toString();
	}
	var r = void 0;
	for (var i = 0, l = DocUtils.charMapRegexes.length; i < l; i++) {
		r = DocUtils.charMapRegexes[i];
		string = string.replace(r.rend, r.start);
	}
	return string;
}
```
- example usage
```shell
...
			return moduleRendered.value;
		}
		if (part.type === "placeholder") {
			var value = options.scopeManager.getValue(part.value);
			if (value == null) {
				value = options.nullGetter(part);
			}
			return DocUtils.utf8ToWord(value);
		}
		if (part.type === "content" || part.type === "tag") {
			return part.value;
		}
		throw new Error("Unimplemented tag type \"" + part.type + "\"");
	}).join("");
}
...
```

#### <a name="apidoc.element.docxtemplater.DocUtils.wordToUtf8"></a>[function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>wordToUtf8 (string)](#apidoc.element.docxtemplater.DocUtils.wordToUtf8)
- description and source-code
```javascript
wordToUtf8 = function (string) {
	var r = void 0;
	for (var i = 0, l = DocUtils.charMapRegexes.length; i < l; i++) {
		r = DocUtils.charMapRegexes[i];
		string = string.replace(r.rstart, r.end);
	}
	return string;
}
```
- example usage
```shell
...
		var inPlaceHolder = false;
		var placeHolderContent = void 0;
		var tailParts = [];
		return lexed.reduce(function (parsed, token) {
			if (token.type === "delimiter") {
				inPlaceHolder = token.position === "start";
				if (token.position === "end") {
					placeHolderContent = DocUtils.wordToUtf8(placeHolderContent);
					if (!moduleParse(placeHolderContent, parsed)) {
						parsed.push({ type: "placeholder", value: placeHolderContent });
					}
					Array.prototype.push.apply(parsed, tailParts);
					tailParts = [];
					return parsed;
				}
...
```

#### <a name="apidoc.element.docxtemplater.DocUtils.xml2str"></a>[function <span class="apidocSignatureSpan">docxtemplater.DocUtils.</span>xml2str (xmlNode)](#apidoc.element.docxtemplater.DocUtils.xml2str)
- description and source-code
```javascript
xml2str = function (xmlNode) {
	var a = new XMLSerializer();
	return a.serializeToString(xmlNode);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.docxtemplater.DocUtils.defaults"></a>[module docxtemplater.DocUtils.defaults](#apidoc.module.docxtemplater.DocUtils.defaults)

#### <a name="apidoc.element.docxtemplater.DocUtils.defaults.nullGetter"></a>[function <span class="apidocSignatureSpan">docxtemplater.DocUtils.defaults.</span>nullGetter (part)](#apidoc.element.docxtemplater.DocUtils.defaults.nullGetter)
- description and source-code
```javascript
function nullGetter(part) {
		if (!part.module) {
			return "undefined";
		}
		if (part.module === "rawxml") {
			return "";
		}
		return "";
	}
```
- example usage
```shell
...
		var moduleRendered = moduleRender(part, options);
		if (moduleRendered) {
			return moduleRendered.value;
		}
		if (part.type === "placeholder") {
			var value = options.scopeManager.getValue(part.value);
			if (value == null) {
				value = options.nullGetter(part);
			}
			return DocUtils.utf8ToWord(value);
		}
		if (part.type === "content" || part.type === "tag") {
			return part.value;
		}
		throw new Error("Unimplemented tag type \"" + part.type + "\"");
...
```

#### <a name="apidoc.element.docxtemplater.DocUtils.defaults.parser"></a>[function <span class="apidocSignatureSpan">docxtemplater.DocUtils.defaults.</span>parser ()](#apidoc.element.docxtemplater.DocUtils.defaults.parser)
- description and source-code
```javascript
function cachedfun() {
		var hash = stringifyJson(arguments);
		return hash in cache ? cache[hash] : cache[hash] = func.apply(this, arguments);
	}
```
- example usage
```shell
...
			// search in the scopes (in reverse order) and keep the first defined value
			this.num = num == null ? this.scopeList.length - 1 : num;
			var err = void 0;
			var parser = void 0;
			var result = void 0;
			var scope = this.scopeList[this.num];
			try {
				parser = this.parser(tag);
			} catch (error) {
				err = new Errors.XTScopeParserError("Scope parser compilation failed");
				err.properties = {
					id: "scopeparser_compilation_failed",
					tag: tag,
					explanation: "The scope parser for the tag " + tag + " failed to compile",
					rootError: error
...
```



# <a name="apidoc.module.docxtemplater.DocUtils.traits"></a>[module docxtemplater.DocUtils.traits](#apidoc.module.docxtemplater.DocUtils.traits)

#### <a name="apidoc.element.docxtemplater.DocUtils.traits.expandToOne"></a>[function <span class="apidocSignatureSpan">docxtemplater.DocUtils.traits.</span>expandToOne (postparsed, options)](#apidoc.element.docxtemplater.DocUtils.traits.expandToOne)
- description and source-code
```javascript
function expandToOne(postparsed, options) {
	var expandToElements = postparsed.reduce(function (elements, part) {
		if (part.type === "placeholder" && part.module === options.moduleName) {
			elements.push(part);
		}
		return elements;
	}, []);

	expandToElements.forEach(function (part) {
		postparsed = expandOne(part, postparsed, options);
	});
	return postparsed;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.docxtemplater.DocUtils.traits.getExpandToDefault"></a>[function <span class="apidocSignatureSpan">docxtemplater.DocUtils.traits.</span>getExpandToDefault (parts)](#apidoc.element.docxtemplater.DocUtils.traits.getExpandToDefault)
- description and source-code
```javascript
function getExpandToDefault(parts) {
	var xmlElements = getListXmlElements(parts);
	for (var i = 0; i < xmlElements.length; i++) {
		var xmlElement = xmlElements[i];
		if (xmlElement.tag.indexOf("<w:tc") === 0) {
			return "w:tr";
		}
		if (xmlElement.tag.indexOf("<a:tc") === 0) {
			return "a:tr";
		}
	}
	return false;
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.docxtemplater.Errors"></a>[module docxtemplater.Errors](#apidoc.module.docxtemplater.Errors)

#### <a name="apidoc.element.docxtemplater.Errors.XTError"></a>[function <span class="apidocSignatureSpan">docxtemplater.Errors.</span>XTError (message)](#apidoc.element.docxtemplater.Errors.XTError)
- description and source-code
```javascript
function XTError(message) {
	this.name = "GenericError";
	this.message = message;
	this.stack = new Error(message).stack;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.docxtemplater.Errors.XTInternalError"></a>[function <span class="apidocSignatureSpan">docxtemplater.Errors.</span>XTInternalError (message)](#apidoc.element.docxtemplater.Errors.XTInternalError)
- description and source-code
```javascript
function XTInternalError(message) {
	this.name = "InternalError";
	this.properties = { explanation: "InternalError" };
	this.message = message;
	this.stack = new Error(message).stack;
}
```
- example usage
```shell
...
		this.load(content);
	}

	_createClass(XmlTemplater, [{
		key: "load",
		value: function load(content) {
			if (typeof content !== "string") {
				var err = new Errors.XTInternalError("Content must be a string");
				err.properties.id = "xmltemplater_content_must_be_string";
				throw err;
			}
			this.content = content;
		}
	}, {
		key: "setTags",
...
```

#### <a name="apidoc.element.docxtemplater.Errors.XTScopeParserError"></a>[function <span class="apidocSignatureSpan">docxtemplater.Errors.</span>XTScopeParserError (message)](#apidoc.element.docxtemplater.Errors.XTScopeParserError)
- description and source-code
```javascript
function XTScopeParserError(message) {
	this.name = "ScopeParserError";
	this.message = message;
	this.stack = new Error(message).stack;
}
```
- example usage
```shell
...
			var err = void 0;
			var parser = void 0;
			var result = void 0;
			var scope = this.scopeList[this.num];
			try {
				parser = this.parser(tag);
			} catch (error) {
				err = new Errors.XTScopeParserError("Scope parser compilation failed");
				err.properties = {
					id: "scopeparser_compilation_failed",
					tag: tag,
					explanation: "The scope parser for the tag " + tag + " failed to compile",
					rootError: error
				};
				throw err;
...
```

#### <a name="apidoc.element.docxtemplater.Errors.XTTemplateError"></a>[function <span class="apidocSignatureSpan">docxtemplater.Errors.</span>XTTemplateError (message)](#apidoc.element.docxtemplater.Errors.XTTemplateError)
- description and source-code
```javascript
function XTTemplateError(message) {
	this.name = "TemplateError";
	this.message = message;
	this.stack = new Error(message).stack;
}
```
- example usage
```shell
...
		totalMatches.push({ type: "tag", position: position, text: text, offset: offset, value: tagText });
	}

	return totalMatches;
}

function throwUnopenedTagException(options) {
	var err = new Errors.XTTemplateError("Unopened tag");
	err.properties = {
		xtag: options.xtag.split(" ")[0],
		id: "unopened_tag",
		context: options.xtag,
		explanation: "The tag beginning with '" + options.xtag.substr(0, 10) + "' is unclosed"
	};
	throw err;
...
```



# <a name="apidoc.module.docxtemplater.lexer"></a>[module docxtemplater.lexer](#apidoc.module.docxtemplater.lexer)

#### <a name="apidoc.element.docxtemplater.lexer.parse"></a>[function <span class="apidocSignatureSpan">docxtemplater.lexer.</span>parse (xmlparsed, delimiters)](#apidoc.element.docxtemplater.lexer.parse)
- description and source-code
```javascript
function parse(xmlparsed, delimiters) {
		var inTextTag = false;
		var innerContentParts = [];
		xmlparsed.forEach(function (part) {
			inTextTag = updateInTextTag(part, inTextTag);
			if (inTextTag && part.type === "content") {
				innerContentParts.push(part.value);
			}
		});
		var reader = new Reader(innerContentParts);
		reader.parseDelimiters(delimiters);

		var newArray = [];
		var index = 0;
		xmlparsed.forEach(function (part) {
			inTextTag = updateInTextTag(part, inTextTag);
			if (part.type === "content") {
				part.position = inTextTag ? "insidetag" : "outsidetag";
			}
			if (inTextTag && part.type === "content") {
				Array.prototype.push.apply(newArray, reader.parsed[index].map(function (p) {
					if (p.type === "content") {
						p.position = "insidetag";
					}
					return p;
				}));
				index++;
			} else {
				newArray.push(part);
			}
		});
		return newArray;
	}
```
- example usage
```shell
...
		return postparse(parsed);
	},
	parse: function parse(lexed, modules) {
		function moduleParse(placeHolderContent, parsed) {
			var moduleParsed = void 0;
			for (var i = 0, l = modules.length; i < l; i++) {
				var _module = modules[i];
				moduleParsed = _module.parse(placeHolderContent);
				if (moduleParsed) {
					parsed.push(moduleParsed);
					return moduleParsed;
				}
			}
			return null;
		}
...
```

#### <a name="apidoc.element.docxtemplater.lexer.xmlparse"></a>[function <span class="apidocSignatureSpan">docxtemplater.lexer.</span>xmlparse (content, xmltags)](#apidoc.element.docxtemplater.lexer.xmlparse)
- description and source-code
```javascript
function xmlparse(content, xmltags) {
		var matches = tagMatcher(content, xmltags.text, xmltags.other);
		var cursor = 0;
		var parsed = matches.reduce(function (parsed, match) {
			var value = content.substr(cursor, match.offset - cursor);
			if (value.length > 0) {
				parsed.push({ type: "content", value: value });
			}
			cursor = match.offset + match.value.length;
			delete match.offset;
			if (match.value.length > 0) {
				parsed.push(match);
			}
			return parsed;
		}, []);
		var value = content.substr(cursor);
		if (value.length > 0) {
			parsed.push({ type: "content", value: value });
		}
		return parsed;
	}
```
- example usage
```shell
...
			this.modules.forEach(function (module) {
				module.set(obj);
			});
		}
	}, {
		key: "parse",
		value: function parse() {
			this.xmllexed = Lexer.xmlparse(this.content, { text: this.fileTypeConfig.tagsXmlTextArray, other: this.fileTypeConfig.tagsXmlLexedArray
 });
			this.setModules({ inspect: { xmllexed: this.xmllexed } });
			this.lexed = Lexer.parse(this.xmllexed, this.delimiters);
			this.setModules({ inspect: { lexed: this.lexed } });
			this.parsed = Parser.parse(this.lexed, this.modules);
			this.setModules({ inspect: { parsed: this.parsed } });
			this.postparsed = Parser.postparse(this.parsed, this.modules);
			return this;
...
```



# <a name="apidoc.module.docxtemplater.parser"></a>[module docxtemplater.parser](#apidoc.module.docxtemplater.parser)

#### <a name="apidoc.element.docxtemplater.parser.parse"></a>[function <span class="apidocSignatureSpan">docxtemplater.parser.</span>parse (lexed, modules)](#apidoc.element.docxtemplater.parser.parse)
- description and source-code
```javascript
function parse(lexed, modules) {
		function moduleParse(placeHolderContent, parsed) {
			var moduleParsed = void 0;
			for (var i = 0, l = modules.length; i < l; i++) {
				var _module = modules[i];
				moduleParsed = _module.parse(placeHolderContent);
				if (moduleParsed) {
					parsed.push(moduleParsed);
					return moduleParsed;
				}
			}
			return null;
		}

		var inPlaceHolder = false;
		var placeHolderContent = void 0;
		var tailParts = [];
		return lexed.reduce(function (parsed, token) {
			if (token.type === "delimiter") {
				inPlaceHolder = token.position === "start";
				if (token.position === "end") {
					placeHolderContent = DocUtils.wordToUtf8(placeHolderContent);
					if (!moduleParse(placeHolderContent, parsed)) {
						parsed.push({ type: "placeholder", value: placeHolderContent });
					}
					Array.prototype.push.apply(parsed, tailParts);
					tailParts = [];
					return parsed;
				}
				placeHolderContent = "";
				return parsed;
			}
			if (inPlaceHolder) {
				if (token.type === "content" && token.position === "insidetag") {
					placeHolderContent += token.value;
				} else {
					tailParts.push(token);
				}
				return parsed;
			}
			parsed.push(token);
			return parsed;
		}, []);
	}
```
- example usage
```shell
...
		return postparse(parsed);
	},
	parse: function parse(lexed, modules) {
		function moduleParse(placeHolderContent, parsed) {
			var moduleParsed = void 0;
			for (var i = 0, l = modules.length; i < l; i++) {
				var _module = modules[i];
				moduleParsed = _module.parse(placeHolderContent);
				if (moduleParsed) {
					parsed.push(moduleParsed);
					return moduleParsed;
				}
			}
			return null;
		}
...
```

#### <a name="apidoc.element.docxtemplater.parser.postparse"></a>[function <span class="apidocSignatureSpan">docxtemplater.parser.</span>postparse (parsed, modules)](#apidoc.element.docxtemplater.parser.postparse)
- description and source-code
```javascript
function postparse(parsed, modules) {
		function getTraits(traitName, parsed) {
			return modules.map(function (module) {
				return module.getTraits(traitName, parsed);
			});
		}
		function postparse(parsed) {
			return modules.reduce(function (parsed, module) {
				return module.postparse(parsed, { postparse: postparse, getTraits: getTraits });
			}, parsed);
		}
		return postparse(parsed);
	}
```
- example usage
```shell
...
		function getTraits(traitName, parsed) {
			return modules.map(function (module) {
				return module.getTraits(traitName, parsed);
			});
		}
		function postparse(parsed) {
			return modules.reduce(function (parsed, module) {
				return module.postparse(parsed, { postparse: postparse, getTraits: getTraits });
			}, parsed);
		}
		return postparse(parsed);
	},
	parse: function parse(lexed, modules) {
		function moduleParse(placeHolderContent, parsed) {
			var moduleParsed = void 0;
...
```



# <a name="apidoc.module.docxtemplater.scope_manager"></a>[module docxtemplater.scope_manager](#apidoc.module.docxtemplater.scope_manager)

#### <a name="apidoc.element.docxtemplater.scope_manager.scope_manager"></a>[function <span class="apidocSignatureSpan">docxtemplater.</span>scope_manager (options)](#apidoc.element.docxtemplater.scope_manager.scope_manager)
- description and source-code
```javascript
function ScopeManager(options) {
		_classCallCheck(this, ScopeManager);

		this.scopePath = options.scopePath;
		this.scopeList = options.scopeList;
		this.parser = options.parser;
	}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.docxtemplater.scope_manager.createBaseScopeManager"></a>[function <span class="apidocSignatureSpan">docxtemplater.scope_manager.</span>createBaseScopeManager (_ref)](#apidoc.element.docxtemplater.scope_manager.createBaseScopeManager)
- description and source-code
```javascript
createBaseScopeManager = function (_ref) {
	var parser = _ref.parser,
	    tags = _ref.tags;

	var options = { parser: parser, tags: tags };
	options.scopePath = [];
	options.scopeList = [tags];
	return new ScopeManager(options);
}
```
- example usage
```shell
...
	return false;
}

function render(options) {
	options.render = render;
	options.modules = options.modules;
	if (!options.scopeManager) {
		options.scopeManager = ScopeManager.createBaseScopeManager(options);
	}
	return options.compiled.map(function (part) {
		var moduleRendered = moduleRender(part, options);
		if (moduleRendered) {
			return moduleRendered.value;
		}
		if (part.type === "placeholder") {
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
