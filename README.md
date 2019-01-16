# CakePHP 1.3 for PHP 7.2
An unofficial port of CakePHP 1.3.21 to PHP 7.2.

**:warning: Only use this code, if you have an active CakePHP 1.3 version that you have to port to PHP 7!
Otherwise use a [current CakePHP version](https://cakephp.org/)!**

[![Build Status](https://travis-ci.org/littleant/cakephp-1.3.21.svg?branch=travis)](https://travis-ci.org/littleant/cakephp-1.3.21)

## Getting Started
1. Make sure your code is PHP 7.2 ready. [php7cc](https://github.com/sstalle/php7cc) is a good start, just exclude the cake-directory in your scans.
2. If you made any changes in the cake-directory, that you want to reapply in the PHP 7-version, write them down.
3. Delete your cake-directory.
4. Copy **only** the cake-directory from this repository to your existing installation.
5. Reapply the changes you wrote down in step 2.
6. Find and fix problems related to the changes described below.

Porting CakePHP to PHP 7.2 required the introduction of some breaking changes.
Make sure you update your own code accord to the following changes:

### Renamed classes
Two classes had to be renamed:
- The class `String` has been renamed to `CakeString`
- The class `Object` has been renamed to `CakeObject`

### Renamed class functions
Three class functions had to be renamed:
- `JsHelper->value()` has been renamed to `JsHelper->jsonValue()`
- `JavascriptHelper->value()` has been renamed to `JavascriptHelper->jsonValue()`
- `JsBaseEngineHelper->value()` has been renamed to `JsBaseEngineHelper->jsonValue()`

### Removed database drivers
Two database drivers had to be removed:
- "mysql" (replace with "mysqli")
- "mssql"

### Necessary configuration changes
One configuration variable has to be changed:
- "Security.cipherSeed" must be a valid `int` instead of a string. Make sure, it is small enough to be treated like an int, and not like a float on your system. Otherwise cookies will not be decoded correctly!

## Running the tests
Tests have not yet been ported to PHP 7.

## Contributing
Please issue a pull request if you want to contribute.
