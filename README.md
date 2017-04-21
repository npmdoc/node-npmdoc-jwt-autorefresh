# npmdoc-jwt-autorefresh

#### api documentation for  [jwt-autorefresh (v0.2.4)](http://jwt-autorefresh.js.org)  [![npm package](https://img.shields.io/npm/v/npmdoc-jwt-autorefresh.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-jwt-autorefresh) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-jwt-autorefresh.svg)](https://travis-ci.org/npmdoc/node-npmdoc-jwt-autorefresh)

#### Factory to schedule and execute calls to refresh token endpoints in advance of token expiration.

[![NPM](https://nodei.co/npm/jwt-autorefresh.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/jwt-autorefresh)

- [https://npmdoc.github.io/node-npmdoc-jwt-autorefresh/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-jwt-autorefresh/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-jwt-autorefresh/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-jwt-autorefresh/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-jwt-autorefresh/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-jwt-autorefresh/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "name": "jwt-autorefresh",
    "version": "0.2.4",
    "description": "Factory to schedule and execute calls to refresh token endpoints in advance of token expiration.",
    "main": "lib/index.js",
    "files": [
        "lib",
        "src",
        "doc"
    ],
    "keywords": [
        "jwt",
        "refresh",
        "token",
        "openid",
        "oauth",
        "expiration",
        "exp",
        "keepalive",
        "unauthorized"
    ],
    "scripts": {
        "clean": "rimraf lib doc",
        "prebuild": "npm run clean",
        "build": "babel src/lib -d lib --ignore __tests__,__mocks__",
        "test": "jest",
        "prerelease": "run-p build test",
        "release": "npm version patch && npm publish",
        "postrelease": "npm run release-gh-pages",
        "prerelease-gh-pages": "npm run doc",
        "release-gh-pages": "run-s gh-pages-subtree gh-pages-push gh-pages-delete",
        "postrelease-gh-pages": "npm run clean && npm run git-save -- clean && git push -u origin master --follow-tags",
        "predoc": "rimraf doc",
        "doc": "esdoc -c ./esdoc.json && ncp CNAME doc/CNAME",
        "postdoc": "npm run git-save -- doc",
        "gh-pages-subtree": "git subtree split --prefix doc -b gh-pages",
        "gh-pages-push": "git push -f origin gh-pages:gh-pages",
        "gh-pages-delete": "git branch -D gh-pages",
        "git-save": "git add -A && git commit -am "
    },
    "dependencies": {
        "chai": "^3.5.0",
        "bunyan": "^1.8.1",
        "jwt-simple": "^0.5.0",
        "npm-run-all": "^2.1.1"
    },
    "devDependencies": {
        "babel-cli": "^6.7.7",
        "babel-preset-latest": "^6.6.0",
        "babel-preset-stage-2": "^6.5.0",
        "esdoc": "^0.4.6",
        "esdoc-es7-plugin": "0.0.3",
        "jest": "^16.0.1",
        "ncp": "^2.0.0",
        "npm-run-all": "^2.1.1",
        "rimraf": "^2.5.2"
    },
    "author": "Cole Chamberlain <cole.chamberlain@gmail.com> (https://github.com/cchamberlain)",
    "bugs": {
        "url": "https://github.com/cchamberlain/jwt-autorefresh/issues"
    },
    "homepage": "http://jwt-autorefresh.js.org",
    "license": "MIT",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/cchamberlain/jwt-autorefresh.git"
    }
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
