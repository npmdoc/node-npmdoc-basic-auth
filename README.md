# api documentation for  [basic-auth (v1.1.0)](https://github.com/jshttp/basic-auth)  [![npm package](https://img.shields.io/npm/v/npmdoc-basic-auth.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-basic-auth) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-basic-auth.svg)](https://travis-ci.org/npmdoc/node-npmdoc-basic-auth)
#### node.js basic auth parser

[![NPM](https://nodei.co/npm/basic-auth.png?downloads=true)](https://www.npmjs.com/package/basic-auth)

[![apidoc](https://npmdoc.github.io/node-npmdoc-basic-auth/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-basic-auth_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-basic-auth/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-basic-auth/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-basic-auth/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "bugs": {
        "url": "https://github.com/jshttp/basic-auth/issues"
    },
    "dependencies": {},
    "description": "node.js basic auth parser",
    "devDependencies": {
        "eslint": "3.10.2",
        "eslint-config-standard": "6.2.1",
        "eslint-plugin-markdown": "1.0.0-beta.3",
        "eslint-plugin-promise": "3.4.0",
        "eslint-plugin-standard": "2.0.1",
        "istanbul": "0.4.5",
        "mocha": "1.21.5"
    },
    "directories": {},
    "dist": {
        "shasum": "45221ee429f7ee1e5035be3f51533f1cdfd29884",
        "tarball": "https://registry.npmjs.org/basic-auth/-/basic-auth-1.1.0.tgz"
    },
    "engines": {
        "node": ">= 0.6"
    },
    "files": [
        "HISTORY.md",
        "LICENSE",
        "index.js"
    ],
    "gitHead": "5a0fcd9f4dbf72e2a105d4e815987d3492925875",
    "homepage": "https://github.com/jshttp/basic-auth",
    "keywords": [
        "basic",
        "auth",
        "authorization",
        "basicauth"
    ],
    "license": "MIT",
    "maintainers": [
        {
            "name": "dougwilson",
            "email": "doug@somethingdoug.com"
        },
        {
            "name": "jonathanong",
            "email": "jonathanrichardong@gmail.com"
        },
        {
            "name": "jongleberry",
            "email": "jonathanrichardong@gmail.com"
        },
        {
            "name": "tjholowaychuk",
            "email": "tj@vision-media.ca"
        }
    ],
    "name": "basic-auth",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/jshttp/basic-auth.git"
    },
    "scripts": {
        "lint": "eslint --plugin markdown --ext js,md .",
        "test": "mocha --check-leaks --reporter spec --bail",
        "test-cov": "istanbul cover node_modules/mocha/bin/_mocha -- --reporter dot --check-leaks test/",
        "test-travis": "istanbul cover node_modules/mocha/bin/_mocha --report lcovonly -- --reporter spec --check-leaks test/"
    },
    "version": "1.1.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module basic-auth](#apidoc.module.basic-auth)
1.  [function <span class="apidocSignatureSpan">basic-auth.</span>parse (string)](#apidoc.element.basic-auth.parse)



# <a name="apidoc.module.basic-auth"></a>[module basic-auth](#apidoc.module.basic-auth)

#### <a name="apidoc.element.basic-auth.parse"></a>[function <span class="apidocSignatureSpan">basic-auth.</span>parse (string)](#apidoc.element.basic-auth.parse)
- description and source-code
```javascript
function parse(string) {
  if (typeof string !== 'string') {
    return undefined
  }

  // parse header
  var match = CREDENTIALS_REGEXP.exec(string)

  if (!match) {
    return undefined
  }

  // decode user pass
  var userPass = USER_PASS_REGEXP.exec(decodeBase64(match[1]))

  if (!userPass) {
    return undefined
  }

  // return credentials object
  return new Credentials(userPass[1], userPass[2])
}
```
- example usage
```shell
...

### auth(req)

Get the basic auth credentials from the given request. The 'Authorization'
header is parsed and if the header is invalid, 'undefined' is returned,
otherwise an object with 'name' and 'pass' properties.

### auth.parse(string)

Parse a basic auth authorization header string. This will return an object
with 'name' and 'pass' properties, or 'undefined' if the string is invalid.

## Example

Pass a node request or koa Context object to the module exported. If
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
